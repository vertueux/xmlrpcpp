<html>
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1">
		<meta http-equiv="Content-language" content="en-US">
		<meta name="author" content="Chris Morley">
		<meta name="copyright" content="Copyright � 2003 by Chris Morley">
	</head>
	<body>
		<H3>XmlRpc++ Library</H3>
		<P>This is version 0.7 of XmlRpc++, an implementation of the <A HREF="http://www.xmlrpc.org">
			XmlRpc protocol</A> written in C++, based upon Shilad Sen's excellent <A HREF="http://py-xmlrpc.sourceforge.net">
			py-xmlrpc library</A>. XmlRpc++ is designed to make it easy to incorporate 
			XmlRpc client and server support into C++ applications. Or use both client and 
			server objects in your app for easy peer-to-peer support.
		</P>
		<H3>Features</H3>
		<UL>
			<li>
				<STRONG>Easy</STRONG> &nbsp; This library is easy to incorporate into C++ 
				applications. No other libraries are required, other than your system's socket 
				libraries. Simple XML parsing and HTTP support are built in.<br>
			<li>
				<STRONG>Fast</STRONG> &nbsp; All IO is non-blocking, so a slow client or 
				network will not slow down the server.<br>
			<li>
				<STRONG>Portable</STRONG> Written in standard C++ to the POSIX and Windows 
				sockets APIs. You do need a fairly recent compiler (g++ 3.1 or MSVC++ .Net or 
				MSVC++ 6 with the <A href="http://www.dinkumware.com/vc_fixes.html">STL patches</A>.)
			</li>
			<li>
				<STRONG>Free</STRONG> &nbsp; This library is released under the <a href="http://www.gnu.org/">
					GNU</a> <a href="http://www.gnu.org/copyleft/lesser.html">LGPL</a>.<br>
				<br>
			</li>
		</UL>
		<P>&nbsp;</P>
		<h3>Changes</h3>
		<UL>
			<li>
				Better handling of fault responses: server methods can throw an 
				XmlRpcException to return a fault and XmlRpcClient has a new method to 
				test whether the last response was a fault.</li>
			<li>
				Support for system.listMethods and system.methodHelp from the introspection 
				API.</li>
			<li>
				Support for system.multicall to process multiple requests in a single transaction.</li>
			<li>
				Fixed a problem in the XmlRpcServer destructor (it should not have been deleting the methods).</li>
			<li>
				The server ensures a valid result value is returned even if the method does not
				set the result. The default result is an empty string.</li>
			<li>
				Doxygen comments in header files and a doc target in the makefile.</li>
		</UL>
		<P>
		<P>&nbsp;</P>
		<h3>Installation</h3>
		<P>
			There are VC++ 6 and VC++ .Net project files building on Windows. If you are 
			using VC++ 6, you should apply SP3 and the fixes at <A href="http://www.dinkumware.com/vc_fixes.html">
				http://www.dinkumware.com/vc_fixes.html</A>. Be sure to set the appropriate 
			code generation switches. In particular, ensure that the runtime library 
			(single/multi-threaded, static library/DLL) used is the same for the XmlRpc++ 
			code and whatever application it will be linked to.</P>
		<P>
			For Linux, Solaris, and other Unix-like platforms there is a GNU Makefile which 
			can be edited to suit your system. Specify your C++ compiler, compiler flags, 
			and your system's socket libraries.
		</P>
		<p>In the test directory there are various test programs that are built by default. 
			To verify that the library built correctly, you can start the HelloServer 
			example:<br>
			<pre>HelloServer 8000
			</pre>
			and the HelloClient example in another terminal window:<br>
			<pre>HelloClient localhost 8000
			</pre>
		<P>
			You should see two Hello messages and a sum displayed (amongst a bunch of debug 
			output). You can also try the XML server validator program (eg, "Validator 80") 
			and then attempt to connect to it from <A href="http://validator.xmlrpc.com">http://validator.xmlrpc.com</A>
			(if you have access to the internet and are not behind a firewall etc).
		</P>
		<H3>Author</H3>
		<P><A href="mailto:cmorley@users.sourceforge.net">Chris Morley</A>
		</P>
		<P>Although no code was re-used, the design and structure of the library is based 
			upon the py-xmlrpc library implementation.<BR>
			The base64 decoder/encoder is by <A href="mailto:lostd@ukr.net">Konstantin 
				Pilipchuk</A>.</P>
		<P></P>
		<H3>License</H3>
		<p>A full copy of the LGPL license is included in the file COPYING. The source code 
			is Copyright (c) 2002-2003 by Chris Morley. This library is free software; you 
			can redistribute it and/or modify it under the terms of the GNU Lesser General 
			Public License as published by the Free Software Foundation; either version 2.1 
			of the License, or (at your option) any later version. This library is 
			distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; 
			without even the implied warranty of MERCHANTABILITY or FITNESS FOR A 
			PARTICULAR PURPOSE. See the GNU Lesser General Public License for more details. 
			You should have received a copy of the GNU Lesser General Public License along 
			with this library; if not, write to the Free Software Foundation, Inc., 59 
			Temple Place, Suite 330, Boston, MA 02111-1307 USA
		</p>
	</body>
</html>

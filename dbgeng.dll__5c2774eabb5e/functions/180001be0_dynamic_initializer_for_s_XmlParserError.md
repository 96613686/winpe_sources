# _dynamic_initializer_for__s_XmlParserError__

- ea: `0x180001be0`
- end: `0x18000233b`
- name: `_dynamic_initializer_for__s_XmlParserError__`
- size: `1883`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18008c764`
- `0x1800f0f40`
- `0x1800f13cc`

## string_xrefs

- `0x1800020e1`: `Non default namespace with empty uri`
- `0x180001e74`: `Leading "xml"`
- `0x1800021b3`: `Writer: namespace is not declared`
- `0x1800020fd`: `"xmlns" prefix is reserved for use by XML`
- `0x18000217b`: `Writer: cannot redefine the xmlns prefix`
- `0x180001f70`: `xml:space attribute that has invalid value`
- `0x180002127`: `Element depth exceeds limit in XmlReaderProperty_MaxElementDepth`
- `0x180001e90`: `Incorrect xml declaration syntax`
- `0x180002119`: `xmlns namespace URI (http://www.w3.org/2000/xmlns/) is reserved.`
- `0x1800021a5`: `Writer: xmlns namespace URI (http://www.w3.org/2000/xmlns/) is reserved `
- `0x180001e66`: `Text/xmldecl not at the beginning of input`
- `0x180001ca9`: `Illegal xml character`
- `0x18000216d`: `Writer: duplicate attribute`
- `0x18000215f`: `Writer: it is not allowed to declare a namespace prefix with empty URI (for example xmlns:p="")`
- `0x180002143`: `Writer: specified string is not white space`
- `0x1800021c1`: `Writer: invalid value of xml:space attribute (allowed values are "default" and "preserve")`
- `0x180001f54`: `Not all chunks of value have been read`
- `0x180002135`: `Entity expansion exceeds limit in XmlReaderProperty_MaxEntityExpansion`
- `0x1800021cf`: `Writer: performing the requested action would result in invalid XML document`
- `0x180001cd5`: `Incorrect comment syntax`
- `0x180002197`: `Writer: xml namespace URI (http://www.w3.org/XML/1998/namespace) must be assigned only to prefix "xml"`
- `0x180002189`: `Writer: xml prefix must have the http://www.w3.org/XML/1998/namespace URI`
- `0x1800021dd`: `Writer: input contains invalid or incomplete surrogate pair`
- `0x18000210b`: `xml namespace URI (http://www.w3.org/XML/1998/namespace) must be assigned only to prefix "xml"`
- `0x180002151`: `Writer: namespace prefix is already declared with a different namespace`
- `0x1800020ef`: `"xml" prefix is reserved and must have the http://www.w3.org/XML/1998/namespace URI`

## pseudocode

```c
int __fastcall dynamic_initializer_for__s_XmlParserError__(__int64 a1)
{
  _QWORD v2[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v3; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v4; // [rsp+38h] [rbp-C8h]
  int v5; // [rsp+40h] [rbp-C0h]
  const wchar_t *v6; // [rsp+48h] [rbp-B8h]
  int v7; // [rsp+50h] [rbp-B0h]
  const wchar_t *v8; // [rsp+58h] [rbp-A8h]
  int v9; // [rsp+60h] [rbp-A0h]
  const wchar_t *v10; // [rsp+68h] [rbp-98h]
  int v11; // [rsp+70h] [rbp-90h]
  const wchar_t *v12; // [rsp+78h] [rbp-88h]
  int v13; // [rsp+80h] [rbp-80h]
  const wchar_t *v14; // [rsp+88h] [rbp-78h]
  int v15; // [rsp+90h] [rbp-70h]
  const wchar_t *v16; // [rsp+98h] [rbp-68h]
  int v17; // [rsp+A0h] [rbp-60h]
  const wchar_t *v18; // [rsp+A8h] [rbp-58h]
  int v19; // [rsp+B0h] [rbp-50h]
  const wchar_t *v20; // [rsp+B8h] [rbp-48h]
  int v21; // [rsp+C0h] [rbp-40h]
  const wchar_t *v22; // [rsp+C8h] [rbp-38h]
  int v23; // [rsp+D0h] [rbp-30h]
  const wchar_t *v24; // [rsp+D8h] [rbp-28h]
  int v25; // [rsp+E0h] [rbp-20h]
  const wchar_t *v26; // [rsp+E8h] [rbp-18h]
  int v27; // [rsp+F0h] [rbp-10h]
  const wchar_t *v28; // [rsp+F8h] [rbp-8h]
  int v29; // [rsp+100h] [rbp+0h]
  const wchar_t *v30; // [rsp+108h] [rbp+8h]
  int v31; // [rsp+110h] [rbp+10h]
  const wchar_t *v32; // [rsp+118h] [rbp+18h]
  int v33; // [rsp+120h] [rbp+20h]
  const wchar_t *v34; // [rsp+128h] [rbp+28h]
  int v35; // [rsp+130h] [rbp+30h]
  const wchar_t *v36; // [rsp+138h] [rbp+38h]
  int v37; // [rsp+140h] [rbp+40h]
  const wchar_t *v38; // [rsp+148h] [rbp+48h]
  int v39; // [rsp+150h] [rbp+50h]
  const wchar_t *v40; // [rsp+158h] [rbp+58h]
  int v41; // [rsp+160h] [rbp+60h]
  const wchar_t *v42; // [rsp+168h] [rbp+68h]
  int v43; // [rsp+170h] [rbp+70h]
  const wchar_t *v44; // [rsp+178h] [rbp+78h]
  int v45; // [rsp+180h] [rbp+80h]
  const wchar_t *v46; // [rsp+188h] [rbp+88h]
  int v47; // [rsp+190h] [rbp+90h]
  const wchar_t *v48; // [rsp+198h] [rbp+98h]
  int v49; // [rsp+1A0h] [rbp+A0h]
  const wchar_t *v50; // [rsp+1A8h] [rbp+A8h]
  int v51; // [rsp+1B0h] [rbp+B0h]
  const wchar_t *v52; // [rsp+1B8h] [rbp+B8h]
  int v53; // [rsp+1C0h] [rbp+C0h]
  const wchar_t *v54; // [rsp+1C8h] [rbp+C8h]
  int v55; // [rsp+1D0h] [rbp+D0h]
  const wchar_t *v56; // [rsp+1D8h] [rbp+D8h]
  int v57; // [rsp+1E0h] [rbp+E0h]
  const wchar_t *v58; // [rsp+1E8h] [rbp+E8h]
  int v59; // [rsp+1F0h] [rbp+F0h]
  const wchar_t *v60; // [rsp+1F8h] [rbp+F8h]
  int v61; // [rsp+200h] [rbp+100h]
  const wchar_t *v62; // [rsp+208h] [rbp+108h]
  int v63; // [rsp+210h] [rbp+110h]
  const wchar_t *v64; // [rsp+218h] [rbp+118h]
  int v65; // [rsp+220h] [rbp+120h]
  const wchar_t *v66; // [rsp+228h] [rbp+128h]
  int v67; // [rsp+230h] [rbp+130h]
  const wchar_t *v68; // [rsp+238h] [rbp+138h]
  int v69; // [rsp+240h] [rbp+140h]
  const wchar_t *v70; // [rsp+248h] [rbp+148h]
  int v71; // [rsp+250h] [rbp+150h]
  const wchar_t *v72; // [rsp+258h] [rbp+158h]
  int v73; // [rsp+260h] [rbp+160h]
  const wchar_t *v74; // [rsp+268h] [rbp+168h]
  int v75; // [rsp+270h] [rbp+170h]
  const wchar_t *v76; // [rsp+278h] [rbp+178h]
  int v77; // [rsp+280h] [rbp+180h]
  const wchar_t *v78; // [rsp+288h] [rbp+188h]
  int v79; // [rsp+290h] [rbp+190h]
  const wchar_t *v80; // [rsp+298h] [rbp+198h]
  int v81; // [rsp+2A0h] [rbp+1A0h]
  const wchar_t *v82; // [rsp+2A8h] [rbp+1A8h]
  int v83; // [rsp+2B0h] [rbp+1B0h]
  const wchar_t *v84; // [rsp+2B8h] [rbp+1B8h]
  int v85; // [rsp+2C0h] [rbp+1C0h]
  const wchar_t *v86; // [rsp+2C8h] [rbp+1C8h]
  int v87; // [rsp+2D0h] [rbp+1D0h]
  const wchar_t *v88; // [rsp+2D8h] [rbp+1D8h]
  int v89; // [rsp+2E0h] [rbp+1E0h]
  const wchar_t *v90; // [rsp+2E8h] [rbp+1E8h]
  int v91; // [rsp+2F0h] [rbp+1F0h]
  const wchar_t *v92; // [rsp+2F8h] [rbp+1F8h]
  int v93; // [rsp+300h] [rbp+200h]
  const wchar_t *v94; // [rsp+308h] [rbp+208h]
  int v95; // [rsp+310h] [rbp+210h]
  const wchar_t *v96; // [rsp+318h] [rbp+218h]
  int v97; // [rsp+320h] [rbp+220h]
  const wchar_t *v98; // [rsp+328h] [rbp+228h]
  int v99; // [rsp+330h] [rbp+230h]
  const wchar_t *v100; // [rsp+338h] [rbp+238h]
  int v101; // [rsp+340h] [rbp+240h]
  const wchar_t *v102; // [rsp+348h] [rbp+248h]
  int v103; // [rsp+350h] [rbp+250h]
  const wchar_t *v104; // [rsp+358h] [rbp+258h]
  int v105; // [rsp+360h] [rbp+260h]
  const wchar_t *v106; // [rsp+368h] [rbp+268h]
  int v107; // [rsp+370h] [rbp+270h]
  const wchar_t *v108; // [rsp+378h] [rbp+278h]
  int v109; // [rsp+380h] [rbp+280h]
  const wchar_t *v110; // [rsp+388h] [rbp+288h]
  int v111; // [rsp+390h] [rbp+290h]
  const wchar_t *v112; // [rsp+398h] [rbp+298h]
  int v113; // [rsp+3A0h] [rbp+2A0h]
  const wchar_t *v114; // [rsp+3A8h] [rbp+2A8h]
  int v115; // [rsp+3B0h] [rbp+2B0h]
  const wchar_t *v116; // [rsp+3B8h] [rbp+2B8h]
  int v117; // [rsp+3C0h] [rbp+2C0h]
  const wchar_t *v118; // [rsp+3C8h] [rbp+2C8h]
  int v119; // [rsp+3D0h] [rbp+2D0h]
  const wchar_t *v120; // [rsp+3D8h] [rbp+2D8h]
  int v121; // [rsp+3E0h] [rbp+2E0h]
  const wchar_t *v122; // [rsp+3E8h] [rbp+2E8h]
  int v123; // [rsp+3F0h] [rbp+2F0h]
  const wchar_t *v124; // [rsp+3F8h] [rbp+2F8h]
  int v125; // [rsp+400h] [rbp+300h]
  const wchar_t *v126; // [rsp+408h] [rbp+308h]
  int v127; // [rsp+410h] [rbp+310h]
  const wchar_t *v128; // [rsp+418h] [rbp+318h]
  int v129; // [rsp+420h] [rbp+320h]
  const wchar_t *v130; // [rsp+428h] [rbp+328h]
  int v131; // [rsp+430h] [rbp+330h]
  const wchar_t *v132; // [rsp+438h] [rbp+338h]
  int v133; // [rsp+440h] [rbp+340h]
  const wchar_t *v134; // [rsp+448h] [rbp+348h]
  int v135; // [rsp+450h] [rbp+350h]
  const wchar_t *v136; // [rsp+458h] [rbp+358h]
  int v137; // [rsp+460h] [rbp+360h]
  const wchar_t *v138; // [rsp+468h] [rbp+368h]
  int v139; // [rsp+470h] [rbp+370h]
  const wchar_t *v140; // [rsp+478h] [rbp+378h]
  int v141; // [rsp+480h] [rbp+380h]
  const wchar_t *v142; // [rsp+488h] [rbp+388h]
  int v143; // [rsp+490h] [rbp+390h]
  const wchar_t *v144; // [rsp+498h] [rbp+398h]
  int v145; // [rsp+4A0h] [rbp+3A0h]
  const wchar_t *v146; // [rsp+4A8h] [rbp+3A8h]
  int v147; // [rsp+4B0h] [rbp+3B0h]
  const wchar_t *v148; // [rsp+4B8h] [rbp+3B8h]
  int v149; // [rsp+4C0h] [rbp+3C0h]
  const wchar_t *v150; // [rsp+4C8h] [rbp+3C8h]
  int v151; // [rsp+4D0h] [rbp+3D0h]
  const wchar_t *v152; // [rsp+4D8h] [rbp+3D8h]
  int v153; // [rsp+4E0h] [rbp+3E0h]
  const wchar_t *v154; // [rsp+4E8h] [rbp+3E8h]
  int v155; // [rsp+4F0h] [rbp+3F0h]
  const wchar_t *v156; // [rsp+4F8h] [rbp+3F8h]
  int v157; // [rsp+500h] [rbp+400h]
  const wchar_t *v158; // [rsp+508h] [rbp+408h]
  int v159; // [rsp+510h] [rbp+410h]
  const wchar_t *v160; // [rsp+518h] [rbp+418h]
  __int64 v161; // [rsp+520h] [rbp+420h] BYREF

  v3 = -1072894463;
  v4 = L"Unexpected end of input";
  v6 = L"Unrecognized encoding";
  v8 = L"Unable to switch the encoding";
  v10 = L"Unrecognized input signature";
  v12 = L"White space expected";
  v14 = L"Semicolon expected";
  v16 = L"'>' expected";
  v18 = L"Quote expected";
  v20 = L"Equal expected";
  v22 = L"Well-formedness constraint: no '<' in attribute value";
  v24 = L"Hexadecimal digit expected";
  v26 = L"Decimal digit expected";
  v28 = L"'[' expected";
  v30 = L"'(' expected";
  v32 = L"Illegal xml character";
  v34 = L"Illegal name character";
  v36 = L"Incorrect document syntax";
  v38 = L"Incorrect CDATA section syntax";
  v40 = L"Incorrect comment syntax";
  v42 = L"Incorrect conditional section syntax";
  v44 = L"Incorrect ATTLIST declaration syntax";
  v46 = L"Incorrect DOCTYPE declaration syntax";
  v48 = L"Incorrect ELEMENT declaration syntax";
  v50 = L"Incorrect ENTITY declaration syntax";
  v52 = L"Incorrect NOTATION declaration syntax";
  v54 = L"NDATA expected";
  v56 = L"PUBLIC expected";
  v5 = -1072894462;
  v7 = -1072894461;
  v9 = -1072894460;
  v11 = -1072894431;
  v13 = -1072894430;
  v15 = -1072894429;
  v17 = -1072894428;
  v19 = -1072894427;
  v21 = -1072894426;
  v23 = -1072894425;
  v25 = -1072894424;
  v27 = -1072894423;
  v29 = -1072894422;
  v31 = -1072894421;
  v33 = -1072894420;
  v35 = -1072894419;
  v37 = -1072894418;
  v39 = -1072894417;
  v41 = -1072894416;
  v43 = -1072894415;
  v45 = -1072894414;
  v47 = -1072894413;
  v49 = -1072894412;
  v51 = -1072894411;
  v53 = -1072894410;
  v55 = -1072894409;
  v57 = -1072894408;
  v58 = L"SYSTEM expected";
  v60 = L"Name expected";
  v62 = L"One root element";
  v64 = L"Well-formedness constraint: element type match";
  v66 = L"Well-formedness constraint: unique attribute spec";
  v68 = L"Text/xmldecl not at the beginning of input";
  v70 = L"Leading \"xml\"";
  v72 = L"Incorrect text declaration syntax";
  v74 = L"Incorrect xml declaration syntax";
  v76 = L"Incorrect encoding name syntax";
  v78 = L"Incorrect public identifier syntax";
  v80 = L"Well-formedness constraint: pes in internal subset";
  v82 = L"Well-formedness constraint: pes between declarations";
  v84 = L"Well-formedness constraint: no recursion";
  v86 = L"Entity content not well formed";
  v88 = L"Well-formedness constraint: undeclared entity ";
  v90 = L"Well-formedness constraint: parsed entity";
  v92 = L"Well-formedness constraint: no external entity references";
  v94 = L"Incorrect processing instruction syntax";
  v96 = L"Incorrect system identifier syntax";
  v98 = L"'?' expected";
  v100 = L"No ']]>' in element content";
  v102 = L"Not all chunks of value have been read";
  v104 = L"DTD was found but is prohibited";
  v106 = L"xml:space attribute that has invalid value";
  v108 = L"Illegal qualified name character";
  v110 = L"Multiple colons in qualified name";
  v59 = -1072894407;
  v61 = -1072894406;
  v63 = -1072894405;
  v65 = -1072894404;
  v67 = -1072894403;
  v69 = -1072894402;
  v71 = -1072894401;
  v73 = -1072894400;
  v75 = -1072894399;
  v77 = -1072894398;
  v79 = -1072894397;
  v81 = -1072894396;
  v83 = -1072894395;
  v85 = -1072894394;
  v87 = -1072894393;
  v89 = -1072894392;
  v91 = -1072894391;
  v93 = -1072894390;
  v95 = -1072894389;
  v97 = -1072894388;
  v99 = -1072894387;
  v101 = -1072894386;
  v103 = -1072894385;
  v105 = -1072894384;
  v107 = -1072894367;
  v109 = -1072894366;
  v111 = -1072894365;
  v112 = L"Colon in name";
  v113 = -1072894364;
  v114 = L"Declared prefix";
  v116 = L"Undeclared prefix";
  v118 = L"Non default namespace with empty uri";
  v120 = L"\"xml\" prefix is reserved and must have the http://www.w3.org/XML/1998/namespace URI";
  v122 = L"\"xmlns\" prefix is reserved for use by XML";
  v124 = L"xml namespace URI (http://www.w3.org/XML/1998/namespace) must be assigned only to prefix \"xml\"";
  v126 = L"xmlns namespace URI (http://www.w3.org/2000/xmlns/) is reserved.";
  v128 = L"Element depth exceeds limit in XmlReaderProperty_MaxElementDepth";
  v130 = L"Entity expansion exceeds limit in XmlReaderProperty_MaxEntityExpansion";
  v132 = L"Writer: specified string is not white space";
  v134 = L"Writer: namespace prefix is already declared with a different namespace";
  v136 = L"Writer: it is not allowed to declare a namespace prefix with empty URI (for example xmlns:p=\"\")";
  v138 = L"Writer: duplicate attribute";
  v140 = L"Writer: cannot redefine the xmlns prefix";
  v142 = L"Writer: xml prefix must have the http://www.w3.org/XML/1998/namespace URI";
  v144 = L"Writer: xml namespace URI (http://www.w3.org/XML/1998/namespace) must be assigned only to prefix \"xml\"";
  v146 = L"Writer: xmlns namespace URI (http://www.w3.org/2000/xmlns/) is reserved ";
  v148 = L"Writer: namespace is not declared";
  v150 = L"Writer: invalid value of xml:space attribute (allowed values are \"default\" and \"preserve\")";
  v152 = L"Writer: performing the requested action would result in invalid XML document";
  v154 = L"Writer: input contains invalid or incomplete surrogate pair";
  v156 = L"Character in character entity is not a decimal digit as was expected";
  v158 = L"Character in character entity is not a hexadecimal digit as was expected";
  v160 = L"Character entity has invalid Unicode value";
  v2[0] = &v3;
  v2[1] = &v161;
  v115 = -1072894363;
  v117 = -1072894362;
  v119 = -1072894361;
  v121 = -1072894360;
  v123 = -1072894359;
  v125 = -1072894358;
  v127 = -1072894335;
  v129 = -1072894334;
  v131 = -1072894207;
  v133 = -1072894206;
  v135 = -1072894205;
  v137 = -1072894204;
  v139 = -1072894203;
  v141 = -1072894202;
  v143 = -1072894201;
  v145 = -1072894200;
  v147 = -1072894199;
  v149 = -1072894198;
  v151 = -1072894197;
  v153 = -1072894196;
  v155 = -1072898019;
  v157 = -1072898018;
  v159 = -1072898017;
  std::unordered_map<long,unsigned short const *>::unordered_map<long,unsigned short const *>(a1, v2);
  return atexit(dynamic_atexit_destructor_for__s_XmlParserError__);
}

```

## disassembly

```asm
0x180001be0  push    rbp
0x180001be2  lea     rbp, [rsp-430h]
0x180001bea  sub     rsp, 530h
0x180001bf1  mov     rax, cs:__security_cookie
0x180001bf8  xor     rax, rsp
0x180001bfb  mov     [rbp+430h+var_10], rax
0x180001c02  lea     rax, aUnexpectedEndO; "Unexpected end of input"
0x180001c09  mov     [rsp+530h+var_500], 0C00CEE01h
0x180001c11  mov     [rsp+530h+var_4F8], rax
0x180001c16  lea     rax, aUnrecognizedEn; "Unrecognized encoding"
0x180001c1d  mov     [rsp+530h+var_4E8], rax
0x180001c22  lea     rax, aUnableToSwitch; "Unable to switch the encoding"
0x180001c29  mov     [rsp+530h+var_4D8], rax
0x180001c2e  lea     rax, aUnrecognizedIn; "Unrecognized input signature"
0x180001c35  mov     [rsp+530h+var_4C8], rax
0x180001c3a  lea     rax, aWhiteSpaceExpe; "White space expected"
0x180001c41  mov     [rsp+530h+var_4B8], rax
0x180001c46  lea     rax, aSemicolonExpec; "Semicolon expected"
0x180001c4d  mov     [rbp+430h+var_4A8], rax
0x180001c51  lea     rax, aExpected_5; "'>' expected"
0x180001c58  mov     [rbp+430h+var_498], rax
0x180001c5c  lea     rax, aQuoteExpected; "Quote expected"
0x180001c63  mov     [rbp+430h+var_488], rax
0x180001c67  lea     rax, aEqualExpected; "Equal expected"
0x180001c6e  mov     [rbp+430h+var_478], rax
0x180001c72  lea     rax, aWellFormedness_0; "Well-formedness constraint: no '<' in a"...
0x180001c79  mov     [rbp+430h+var_468], rax
0x180001c7d  lea     rax, aHexadecimalDig; "Hexadecimal digit expected"
0x180001c84  mov     [rbp+430h+var_458], rax
0x180001c88  lea     rax, aDecimalDigitEx; "Decimal digit expected"
0x180001c8f  mov     [rbp+430h+var_448], rax
0x180001c93  lea     rax, aExpected_12; "'[' expected"
0x180001c9a  mov     [rbp+430h+var_438], rax
0x180001c9e  lea     rax, aExpected_0; "'(' expected"
0x180001ca5  mov     [rbp+430h+var_428], rax
0x180001ca9  lea     rax, aIllegalXmlChar; "Illegal xml character"
0x180001cb0  mov     [rbp+430h+var_418], rax
0x180001cb4  lea     rax, aIllegalNameCha; "Illegal name character"
0x180001cbb  mov     [rbp+430h+var_408], rax
0x180001cbf  lea     rax, aIncorrectDocum; "Incorrect document syntax"
0x180001cc6  mov     [rbp+430h+var_3F8], rax
0x180001cca  lea     rax, aIncorrectCdata; "Incorrect CDATA section syntax"
0x180001cd1  mov     [rbp+430h+var_3E8], rax
0x180001cd5  lea     rax, aIncorrectComme; "Incorrect comment syntax"
0x180001cdc  mov     [rbp+430h+var_3D8], rax
0x180001ce0  lea     rax, aIncorrectCondi; "Incorrect conditional section syntax"
0x180001ce7  mov     [rbp+430h+var_3C8], rax
0x180001ceb  lea     rax, aIncorrectAttli; "Incorrect ATTLIST declaration syntax"
0x180001cf2  mov     [rbp+430h+var_3B8], rax
0x180001cf6  lea     rax, aIncorrectDocty; "Incorrect DOCTYPE declaration syntax"
0x180001cfd  mov     [rbp+430h+var_3A8], rax
0x180001d04  lea     rax, aIncorrectEleme; "Incorrect ELEMENT declaration syntax"
0x180001d0b  mov     [rbp+430h+var_398], rax
0x180001d12  lea     rax, aIncorrectEntit; "Incorrect ENTITY declaration syntax"
0x180001d19  mov     [rbp+430h+var_388], rax
0x180001d20  lea     rax, aIncorrectNotat; "Incorrect NOTATION declaration syntax"
0x180001d27  mov     [rbp+430h+var_378], rax
0x180001d2e  lea     rax, aNdataExpected; "NDATA expected"
0x180001d35  mov     [rbp+430h+var_368], rax
0x180001d3c  lea     rax, aPublicExpected; "PUBLIC expected"
0x180001d43  mov     [rbp+430h+var_358], rax
0x180001d4a  mov     [rsp+530h+var_4F0], 0C00CEE02h
0x180001d52  mov     [rsp+530h+var_4E0], 0C00CEE03h
0x180001d5a  mov     [rsp+530h+var_4D0], 0C00CEE04h
0x180001d62  mov     [rsp+530h+var_4C0], 0C00CEE21h
0x180001d6a  mov     [rbp+430h+var_4B0], 0C00CEE22h
0x180001d71  mov     [rbp+430h+var_4A0], 0C00CEE23h
0x180001d78  mov     [rbp+430h+var_490], 0C00CEE24h
0x180001d7f  mov     [rbp+430h+var_480], 0C00CEE25h
0x180001d86  mov     [rbp+430h+var_470], 0C00CEE26h
0x180001d8d  mov     [rbp+430h+var_460], 0C00CEE27h
0x180001d94  mov     [rbp+430h+var_450], 0C00CEE28h
0x180001d9b  mov     [rbp+430h+var_440], 0C00CEE29h
0x180001da2  mov     [rbp+430h+var_430], 0C00CEE2Ah
0x180001da9  mov     [rbp+430h+var_420], 0C00CEE2Bh
0x180001db0  mov     [rbp+430h+var_410], 0C00CEE2Ch
0x180001db7  mov     [rbp+430h+var_400], 0C00CEE2Dh
0x180001dbe  mov     [rbp+430h+var_3F0], 0C00CEE2Eh
0x180001dc5  mov     [rbp+430h+var_3E0], 0C00CEE2Fh
0x180001dcc  mov     [rbp+430h+var_3D0], 0C00CEE30h
0x180001dd3  mov     [rbp+430h+var_3C0], 0C00CEE31h
0x180001dda  mov     [rbp+430h+var_3B0], 0C00CEE32h
0x180001de4  mov     [rbp+430h+var_3A0], 0C00CEE33h
0x180001dee  mov     [rbp+430h+var_390], 0C00CEE34h
0x180001df8  mov     [rbp+430h+var_380], 0C00CEE35h
0x180001e02  mov     [rbp+430h+var_370], 0C00CEE36h
0x180001e0c  mov     [rbp+430h+var_360], 0C00CEE37h
0x180001e16  lea     rax, aSystemExpected; "SYSTEM expected"
0x180001e1d  mov     [rbp+430h+var_350], 0C00CEE38h
0x180001e27  mov     [rbp+430h+var_348], rax
0x180001e2e  lea     rax, aNameExpected; "Name expected"
0x180001e35  mov     [rbp+430h+var_338], rax
0x180001e3c  lea     rax, aOneRootElement; "One root element"
0x180001e43  mov     [rbp+430h+var_328], rax
0x180001e4a  lea     rax, aWellFormedness_6; "Well-formedness constraint: element typ"...
0x180001e51  mov     [rbp+430h+var_318], rax
0x180001e58  lea     rax, aWellFormedness_5; "Well-formedness constraint: unique attr"...
0x180001e5f  mov     [rbp+430h+var_308], rax
0x180001e66  lea     rax, aTextXmldeclNot; "Text/xmldecl not at the beginning of in"...
0x180001e6d  mov     [rbp+430h+var_2F8], rax
0x180001e74  lea     rax, aLeadingXml; "Leading \"xml\""
0x180001e7b  mov     [rbp+430h+var_2E8], rax
0x180001e82  lea     rax, aIncorrectTextD; "Incorrect text declaration syntax"
0x180001e89  mov     [rbp+430h+var_2D8], rax
0x180001e90  lea     rax, aIncorrectXmlDe; "Incorrect xml declaration syntax"
0x180001e97  mov     [rbp+430h+var_2C8], rax
0x180001e9e  lea     rax, aIncorrectEncod; "Incorrect encoding name syntax"
0x180001ea5  mov     [rbp+430h+var_2B8], rax
0x180001eac  lea     rax, aIncorrectPubli; "Incorrect public identifier syntax"
0x180001eb3  mov     [rbp+430h+var_2A8], rax
0x180001eba  lea     rax, aWellFormedness; "Well-formedness constraint: pes in inte"...
0x180001ec1  mov     [rbp+430h+var_298], rax
0x180001ec8  lea     rax, aWellFormedness_1; "Well-formedness constraint: pes between"...
0x180001ecf  mov     [rbp+430h+var_288], rax
0x180001ed6  lea     rax, aWellFormedness_2; "Well-formedness constraint: no recursio"...
0x180001edd  mov     [rbp+430h+var_278], rax
0x180001ee4  lea     rax, aEntityContentN; "Entity content not well formed"
0x180001eeb  mov     [rbp+430h+var_268], rax
0x180001ef2  lea     rax, aWellFormedness_7; "Well-formedness constraint: undeclared "...
0x180001ef9  mov     [rbp+430h+var_258], rax
0x180001f00  lea     rax, aWellFormedness_4; "Well-formedness constraint: parsed enti"...
0x180001f07  mov     [rbp+430h+var_248], rax
0x180001f0e  lea     rax, aWellFormedness_3; "Well-formedness constraint: no external"...
0x180001f15  mov     [rbp+430h+var_238], rax
0x180001f1c  lea     rax, aIncorrectProce; "Incorrect processing instruction syntax"
0x180001f23  mov     [rbp+430h+var_228], rax
0x180001f2a  lea     rax, aIncorrectSyste; "Incorrect system identifier syntax"
0x180001f31  mov     [rbp+430h+var_218], rax
0x180001f38  lea     rax, aExpected_3; "'?' expected"
0x180001f3f  mov     [rbp+430h+var_208], rax
0x180001f46  lea     rax, aNoInElementCon; "No ']]>' in element content"
0x180001f4d  mov     [rbp+430h+var_1F8], rax
0x180001f54  lea     rax, aNotAllChunksOf; "Not all chunks of value have been read"
0x180001f5b  mov     [rbp+430h+var_1E8], rax
0x180001f62  lea     rax, aDtdWasFoundBut; "DTD was found but is prohibited"
0x180001f69  mov     [rbp+430h+var_1D8], rax
0x180001f70  lea     rax, aXmlSpaceAttrib; "xml:space attribute that has invalid va"...
0x180001f77  mov     [rbp+430h+var_1C8], rax
0x180001f7e  lea     rax, aIllegalQualifi; "Illegal qualified name character"
0x180001f85  mov     [rbp+430h+var_1B8], rax
0x180001f8c  lea     rax, aMultipleColons; "Multiple colons in qualified name"
0x180001f93  mov     [rbp+430h+var_1A8], rax
0x180001f9a  mov     [rbp+430h+var_340], 0C00CEE39h
0x180001fa4  mov     [rbp+430h+var_330], 0C00CEE3Ah
0x180001fae  mov     [rbp+430h+var_320], 0C00CEE3Bh
0x180001fb8  mov     [rbp+430h+var_310], 0C00CEE3Ch
0x180001fc2  mov     [rbp+430h+var_300], 0C00CEE3Dh
0x180001fcc  mov     [rbp+430h+var_2F0], 0C00CEE3Eh
0x180001fd6  mov     [rbp+430h+var_2E0], 0C00CEE3Fh
0x180001fe0  mov     [rbp+430h+var_2D0], 0C00CEE40h
0x180001fea  mov     [rbp+430h+var_2C0], 0C00CEE41h
0x180001ff4  mov     [rbp+430h+var_2B0], 0C00CEE42h
0x180001ffe  mov     [rbp+430h+var_2A0], 0C00CEE43h
0x180002008  mov     [rbp+430h+var_290], 0C00CEE44h
0x180002012  mov     [rbp+430h+var_280], 0C00CEE45h
0x18000201c  mov     [rbp+430h+var_270], 0C00CEE46h
0x180002026  mov     [rbp+430h+var_260], 0C00CEE47h
0x180002030  mov     [rbp+430h+var_250], 0C00CEE48h
0x18000203a  mov     [rbp+430h+var_240], 0C00CEE49h
0x180002044  mov     [rbp+430h+var_230], 0C00CEE4Ah
0x18000204e  mov     [rbp+430h+var_220], 0C00CEE4Bh
0x180002058  mov     [rbp+430h+var_210], 0C00CEE4Ch
0x180002062  mov     [rbp+430h+var_200], 0C00CEE4Dh
0x18000206c  mov     [rbp+430h+var_1F0], 0C00CEE4Eh
0x180002076  mov     [rbp+430h+var_1E0], 0C00CEE4Fh
0x180002080  mov     [rbp+430h+var_1D0], 0C00CEE50h
0x18000208a  mov     [rbp+430h+var_1C0], 0C00CEE61h
0x180002094  mov     [rbp+430h+var_1B0], 0C00CEE62h
0x18000209e  lea     rax, aColonInName; "Colon in name"
0x1800020a5  mov     [rbp+430h+var_1A0], 0C00CEE63h
0x1800020af  mov     [rbp+430h+var_198], rax
0x1800020b6  lea     rdx, [rsp+530h+var_510]
0x1800020bb  lea     rax, aDeclaredPrefix; "Declared prefix"
0x1800020c2  mov     [rbp+430h+var_190], 0C00CEE64h
0x1800020cc  mov     [rbp+430h+var_188], rax
0x1800020d3  lea     rax, aUndeclaredPref; "Undeclared prefix"
0x1800020da  mov     [rbp+430h+var_178], rax
0x1800020e1  lea     rax, aNonDefaultName; "Non default namespace with empty uri"
0x1800020e8  mov     [rbp+430h+var_168], rax
0x1800020ef  lea     rax, aXmlPrefixIsRes; "\"xml\" prefix is reserved and must hav"...
0x1800020f6  mov     [rbp+430h+var_158], rax
0x1800020fd  lea     rax, aXmlnsPrefixIsR; "\"xmlns\" prefix is reserved for use by"...
0x180002104  mov     [rbp+430h+var_148], rax
0x18000210b  lea     rax, aXmlNamespaceUr; "xml namespace URI (http://www.w3.org/XM"...
0x180002112  mov     [rbp+430h+var_138], rax
0x180002119  lea     rax, aXmlnsNamespace; "xmlns namespace URI (http://www.w3.org/"...
0x180002120  mov     [rbp+430h+var_128], rax
0x180002127  lea     rax, aElementDepthEx; "Element depth exceeds limit in XmlReade"...
0x18000212e  mov     [rbp+430h+var_118], rax
0x180002135  lea     rax, aEntityExpansio; "Entity expansion exceeds limit in XmlRe"...
0x18000213c  mov     [rbp+430h+var_108], rax
0x180002143  lea     rax, aWriterSpecifie; "Writer: specified string is not white s"...
0x18000214a  mov     [rbp+430h+var_F8], rax
0x180002151  lea     rax, aWriterNamespac_0; "Writer: namespace prefix is already dec"...
0x180002158  mov     [rbp+430h+var_E8], rax
0x18000215f  lea     rax, aWriterItIsNotA; "Writer: it is not allowed to declare a "...
0x180002166  mov     [rbp+430h+var_D8], rax
0x18000216d  lea     rax, aWriterDuplicat; "Writer: duplicate attribute"
0x180002174  mov     [rbp+430h+var_C8], rax
0x18000217b  lea     rax, aWriterCannotRe; "Writer: cannot redefine the xmlns prefi"...
0x180002182  mov     [rbp+430h+var_B8], rax
0x180002189  lea     rax, aWriterXmlPrefi; "Writer: xml prefix must have the http:/"...
0x180002190  mov     [rbp+430h+var_A8], rax
0x180002197  lea     rax, aWriterXmlNames; "Writer: xml namespace URI (http://www.w"...
0x18000219e  mov     [rbp+430h+var_98], rax
0x1800021a5  lea     rax, aWriterXmlnsNam; "Writer: xmlns namespace URI (http://www"...
0x1800021ac  mov     [rbp+430h+var_88], rax
0x1800021b3  lea     rax, aWriterNamespac; "Writer: namespace is not declared"
0x1800021ba  mov     [rbp+430h+var_78], rax
0x1800021c1  lea     rax, aWriterInvalidV; "Writer: invalid value of xml:space attr"...
0x1800021c8  mov     [rbp+430h+var_68], rax
0x1800021cf  lea     rax, aWriterPerformi; "Writer: performing the requested action"...
0x1800021d6  mov     [rbp+430h+var_58], rax
0x1800021dd  lea     rax, aWriterInputCon; "Writer: input contains invalid or incom"...
0x1800021e4  mov     [rbp+430h+var_48], rax
0x1800021eb  lea     rax, aCharacterInCha_0; "Character in character entity is not a "...
0x1800021f2  mov     [rbp+430h+var_38], rax
0x1800021f9  lea     rax, aCharacterInCha; "Character in character entity is not a "...
0x180002200  mov     [rbp+430h+var_28], rax
0x180002207  lea     rax, aCharacterEntit; "Character entity has invalid Unicode va"...
0x18000220e  mov     [rbp+430h+var_18], rax
0x180002215  lea     rax, [rsp+530h+var_500]
0x18000221a  mov     [rsp+530h+var_510], rax
0x18000221f  lea     rax, [rbp+430h+var_10]
0x180002226  mov     [rsp+530h+var_508], rax
0x18000222b  mov     [rbp+430h+var_180], 0C00CEE65h
0x180002235  mov     [rbp+430h+var_170], 0C00CEE66h
0x18000223f  mov     [rbp+430h+var_160], 0C00CEE67h
0x180002249  mov     [rbp+430h+var_150], 0C00CEE68h
0x180002253  mov     [rbp+430h+var_140], 0C00CEE69h
0x18000225d  mov     [rbp+430h+var_130], 0C00CEE6Ah
0x180002267  mov     [rbp+430h+var_120], 0C00CEE81h
0x180002271  mov     [rbp+430h+var_110], 0C00CEE82h
0x18000227b  mov     [rbp+430h+var_100], 0C00CEF01h
0x180002285  mov     [rbp+430h+var_F0], 0C00CEF02h
0x18000228f  mov     [rbp+430h+var_E0], 0C00CEF03h
0x180002299  mov     [rbp+430h+var_D0], 0C00CEF04h
0x1800022a3  mov     [rbp+430h+var_C0], 0C00CEF05h
0x1800022ad  mov     [rbp+430h+var_B0], 0C00CEF06h
0x1800022b7  mov     [rbp+430h+var_A0], 0C00CEF07h
0x1800022c1  mov     [rbp+430h+var_90], 0C00CEF08h
0x1800022cb  mov     [rbp+430h+var_80], 0C00CEF09h
0x1800022d5  mov     [rbp+430h+var_70], 0C00CEF0Ah
0x1800022df  mov     [rbp+430h+var_60], 0C00CEF0Bh
0x1800022e9  mov     [rbp+430h+var_50], 0C00CEF0Ch
0x1800022f3  mov     [rbp+430h+var_40], 0C00CE01Dh
0x1800022fd  mov     [rbp+430h+var_30], 0C00CE01Eh
0x180002307  mov     [rbp+430h+var_20], 0C00CE01Fh
0x180002311  call    ??0?$unordered_map@JPEBGU?$hash@J@std@@U?$equal_to@J@2@V?$allocator@U?$pair@$$CBJPEBG@std@@@2@@std@@QEAA@V?$initializer_list@U?$pair@$$CBJPEBG@std@@@1@@Z; std::unordered_map<long,ushort const *>::unordered_map<long,ushort const *>(std::initializer_list<std::pair<long const,ushort const *>>)
0x180002316  lea     rcx, _dynamic_atexit_destructor_for__s_XmlParserError__; void (__cdecl *)()
0x18000231d  call    atexit
0x180002322  mov     rcx, [rbp+430h+var_10]
0x180002329  xor     rcx, rsp; StackCookie
0x18000232c  call    __security_check_cookie
0x180002331  add     rsp, 530h
0x180002338  pop     rbp
0x180002339  retn
```

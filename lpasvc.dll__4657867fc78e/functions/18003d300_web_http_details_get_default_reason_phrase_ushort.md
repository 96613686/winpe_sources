# web::http::details::get_default_reason_phrase(ushort)

- ea: `0x18003d300`
- end: `0x18003db2b`
- name: `?get_default_reason_phrase@details@http@web@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z`
- size: `2091`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033ab0`

## callees

- `0x18000e410`
- `0x18003d300`
- `0x180057b50`
- `0x180057bb8`
- `0x180063668`
- `0x1800747a0`

## string_xrefs

- `0x18003d3f9`: `Switching Protocols`
- `0x18003d439`: `Created`
- `0x18003d519`: `Already Reported`
- `0x18003d579`: `Moved Permanently`
- `0x18003d619`: `Temporary Redirect`
- `0x18003d819`: `Request Uri Too Large`
- `0x18003da19`: `Service Unavailable`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
__int64 *__fastcall web::http::details::get_default_reason_phrase(__int64 *a1, __int16 a2)
{
  __int64 *v4; // rax
  __int64 *v6; // rdx

  if ( dword_1801736A8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1801736A8);
    if ( dword_1801736A8 == -1 )
    {
      std::wstring::wstring(qword_180171EB8, L"Continue");
      word_180171ED8 = 101;
      std::wstring::wstring(qword_180171EE0, L"Switching Protocols");
      word_180171F00 = 200;
      std::wstring::wstring(qword_180171F08, L"OK");
      word_180171F28 = 201;
      std::wstring::wstring(qword_180171F30, L"Created");
      word_180171F50 = 202;
      std::wstring::wstring(qword_180171F58, L"Accepted");
      word_180171F78 = 203;
      std::wstring::wstring(qword_180171F80, L"Non-Authoritative Information");
      word_180171FA0 = 204;
      std::wstring::wstring(qword_180171FA8, L"No Content");
      word_180171FC8 = 205;
      std::wstring::wstring(qword_180171FD0, L"Reset Content");
      word_180171FF0 = 206;
      std::wstring::wstring(qword_180171FF8, L"Partial Content");
      word_180172018 = 207;
      std::wstring::wstring(qword_180172020, L"Multi-Status");
      word_180172040 = 208;
      std::wstring::wstring(qword_180172048, L"Already Reported");
      word_180172068 = 226;
      std::wstring::wstring(qword_180172070, L"IM Used");
      word_180172090 = 300;
      std::wstring::wstring(qword_180172098, L"Multiple Choices");
      word_1801720B8 = 301;
      std::wstring::wstring(qword_1801720C0, L"Moved Permanently");
      word_1801720E0 = 302;
      std::wstring::wstring(qword_1801720E8, L"Found");
      word_180172108 = 303;
      std::wstring::wstring(qword_180172110, L"See Other");
      word_180172130 = 304;
      std::wstring::wstring(qword_180172138, L"Not Modified");
      word_180172158 = 305;
      std::wstring::wstring(qword_180172160, L"Use Proxy");
      word_180172180 = 307;
      std::wstring::wstring(qword_180172188, L"Temporary Redirect");
      word_1801721A8 = 308;
      std::wstring::wstring(qword_1801721B0, L"Permanent Redirect");
      word_1801721D0 = 400;
      std::wstring::wstring(qword_1801721D8, L"Bad Request");
      word_1801721F8 = 401;
      std::wstring::wstring(qword_180172200, L"Unauthorized");
      word_180172220 = 402;
      std::wstring::wstring(qword_180172228, L"Payment Required");
      word_180172248 = 403;
      std::wstring::wstring(qword_180172250, L"Forbidden");
      word_180172270 = 404;
      std::wstring::wstring(qword_180172278, L"Not Found");
      word_180172298 = 405;
      std::wstring::wstring(qword_1801722A0, L"Method Not Allowed");
      word_1801722C0 = 406;
      std::wstring::wstring(qword_1801722C8, L"Not Acceptable");
      word_1801722E8 = 407;
      std::wstring::wstring(qword_1801722F0, L"Proxy Authentication Required");
      word_180172310 = 408;
      std::wstring::wstring(qword_180172318, L"Request Time-out");
      word_180172338 = 409;
      std::wstring::wstring(qword_180172340, L"Conflict");
      word_180172360 = 410;
      std::wstring::wstring(qword_180172368, L"Gone");
      word_180172388 = 411;
      std::wstring::wstring(qword_180172390, L"Length Required");
      word_1801723B0 = 412;
      std::wstring::wstring(qword_1801723B8, L"Precondition Failed");
      word_1801723D8 = 413;
      std::wstring::wstring(qword_1801723E0, L"Request Entity Too Large");
      word_180172400 = 414;
      std::wstring::wstring(qword_180172408, L"Request Uri Too Large");
      word_180172428 = 415;
      std::wstring::wstring(qword_180172430, L"Unsupported Media Type");
      word_180172450 = 416;
      std::wstring::wstring(qword_180172458, L"Requested range not satisfiable");
      word_180172478 = 417;
      std::wstring::wstring(qword_180172480, L"Expectation Failed");
      word_1801724A0 = 421;
      std::wstring::wstring(qword_1801724A8, L"Misdirected Request");
      word_1801724C8 = 422;
      std::wstring::wstring(qword_1801724D0, L"Unprocessable Entity");
      word_1801724F0 = 423;
      std::wstring::wstring(qword_1801724F8, L"Locked");
      word_180172518 = 424;
      std::wstring::wstring(qword_180172520, L"Failed Dependency");
      word_180172540 = 426;
      std::wstring::wstring(qword_180172548, L"Upgrade Required");
      word_180172568 = 428;
      std::wstring::wstring(qword_180172570, L"Precondition Required");
      word_180172590 = 429;
      std::wstring::wstring(qword_180172598, L"Too Many Requests");
      word_1801725B8 = 431;
      std::wstring::wstring(qword_1801725C0, L"Request Header Fields Too Large");
      word_1801725E0 = 451;
      std::wstring::wstring(qword_1801725E8, L"Unavailable For Legal Reasons");
      word_180172608 = 500;
      std::wstring::wstring(qword_180172610, L"Internal Error");
      word_180172630 = 501;
      std::wstring::wstring(qword_180172638, L"Not Implemented");
      word_180172658 = 502;
      std::wstring::wstring(qword_180172660, L"Bad Gateway");
      word_180172680 = 503;
      std::wstring::wstring(qword_180172688, L"Service Unavailable");
      word_1801726A8 = 504;
      std::wstring::wstring(qword_1801726B0, L"Gateway Time-out");
      word_1801726D0 = 505;
      std::wstring::wstring(qword_1801726D8, L"HTTP Version not supported");
      word_1801726F8 = 506;
      std::wstring::wstring(qword_180172700, L"Variant Also Negotiates");
      word_180172720 = 507;
      std::wstring::wstring(qword_180172728, L"Insufficient Storage");
      word_180172748 = 508;
      std::wstring::wstring(qword_180172750, L"Loop Detected");
      word_180172770 = 510;
      std::wstring::wstring(qword_180172778, L"Not Extended");
      word_180172798 = 511;
      std::wstring::wstring(qword_1801727A0, L"Network Authentication Required");
      atexit(web::http::details::get_default_reason_phrase_::_2_::_dynamic_atexit_destructor_for__idToPhraseMap__);
      Init_thread_footer(&dword_1801736A8);
    }
  }
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 7;
  *(_WORD *)a1 = 0;
  v4 = &qword_180171EB0;
  while ( *(_WORD *)v4 != a2 )
  {
    v4 += 5;
    if ( v4 == (__int64 *)&Init_global_epoch )
      return a1;
  }
  if ( a1 != v4 + 1 )
  {
    if ( (unsigned __int64)v4[4] <= 7 )
      v6 = v4 + 1;
    else
      v6 = (__int64 *)v4[1];
    std::wstring::_Assign<unsigned short>(a1, v6, v4[3]);
  }
  return a1;
}

```

## disassembly

```asm
0x18003d300  mov     [rsp+arg_8], rbx
0x18003d305  mov     [rsp+arg_0], rcx
0x18003d30a  push    rdi
0x18003d30b  sub     rsp, 30h
0x18003d30f  movzx   edi, dx
0x18003d312  mov     rbx, rcx
0x18003d315  mov     [rsp+38h+var_18], 0
0x18003d31d  mov     r8d, cs:_tls_index
0x18003d324  mov     rax, gs:58h
0x18003d32d  mov     ecx, 4
0x18003d332  mov     rax, [rax+r8*8]
0x18003d336  mov     eax, [rcx+rax]
0x18003d339  cmp     cs:dword_1801736A8, eax
0x18003d33f  jg      short loc_18003D3C0
0x18003d341  xorps   xmm0, xmm0
0x18003d344  movups  xmmword ptr [rbx], xmm0
0x18003d347  mov     qword ptr [rbx+10h], 0
0x18003d34f  mov     qword ptr [rbx+18h], 7
0x18003d357  xor     eax, eax
0x18003d359  mov     [rbx], ax
0x18003d35c  mov     [rsp+38h+var_18], 1
0x18003d364  lea     rax, qword_180171EB0
0x18003d36b  lea     rcx, _Init_global_epoch
0x18003d372  cmp     [rax], di
0x18003d375  jz      short loc_18003D38E
0x18003d377  add     rax, 28h ; '('
0x18003d37b  cmp     rax, rcx
0x18003d37e  jnz     short loc_18003D372
0x18003d380  mov     rax, rbx
0x18003d383  mov     rbx, [rsp+38h+arg_8]
0x18003d388  add     rsp, 30h
0x18003d38c  pop     rdi
0x18003d38d  retn
0x18003d38e  lea     r8, [rax+8]
0x18003d392  cmp     rbx, r8
0x18003d395  jz      short loc_18003D3B2
0x18003d397  cmp     qword ptr [r8+18h], 7
0x18003d39c  jbe     short loc_18003D3A3
0x18003d39e  mov     rdx, [r8]
0x18003d3a1  jmp     short loc_18003D3A6
0x18003d3a3  mov     rdx, r8
0x18003d3a6  mov     r8, [r8+10h]
0x18003d3aa  mov     rcx, rbx
0x18003d3ad  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003d3b2  mov     rax, rbx
0x18003d3b5  mov     rbx, [rsp+38h+arg_8]
0x18003d3ba  add     rsp, 30h
0x18003d3be  pop     rdi
0x18003d3bf  retn
0x18003d3c0  lea     rcx, dword_1801736A8
0x18003d3c7  call    _Init_thread_header
0x18003d3cc  cmp     cs:dword_1801736A8, 0FFFFFFFFh
0x18003d3d3  jnz     loc_18003D341
0x18003d3d9  lea     rdx, aContinue; "Continue"
0x18003d3e0  lea     rcx, qword_180171EB8
0x18003d3e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d3ec  nop
0x18003d3ed  mov     eax, 65h ; 'e'
0x18003d3f2  mov     cs:word_180171ED8, ax
0x18003d3f9  lea     rdx, aSwitchingProto; "Switching Protocols"
0x18003d400  lea     rcx, qword_180171EE0
0x18003d407  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d40c  nop
0x18003d40d  mov     eax, 0C8h
0x18003d412  mov     cs:word_180171F00, ax
0x18003d419  lea     rdx, aOk; "OK"
0x18003d420  lea     rcx, qword_180171F08
0x18003d427  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d42c  nop
0x18003d42d  mov     eax, 0C9h
0x18003d432  mov     cs:word_180171F28, ax
0x18003d439  lea     rdx, aCreated; "Created"
0x18003d440  lea     rcx, qword_180171F30
0x18003d447  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d44c  nop
0x18003d44d  mov     eax, 0CAh
0x18003d452  mov     cs:word_180171F50, ax
0x18003d459  lea     rdx, aAccepted; "Accepted"
0x18003d460  lea     rcx, qword_180171F58
0x18003d467  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d46c  nop
0x18003d46d  mov     eax, 0CBh
0x18003d472  mov     cs:word_180171F78, ax
0x18003d479  lea     rdx, aNonAuthoritati; "Non-Authoritative Information"
0x18003d480  lea     rcx, qword_180171F80
0x18003d487  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d48c  nop
0x18003d48d  mov     eax, 0CCh
0x18003d492  mov     cs:word_180171FA0, ax
0x18003d499  lea     rdx, aNoContent; "No Content"
0x18003d4a0  lea     rcx, qword_180171FA8
0x18003d4a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d4ac  nop
0x18003d4ad  mov     eax, 0CDh
0x18003d4b2  mov     cs:word_180171FC8, ax
0x18003d4b9  lea     rdx, aResetContent; "Reset Content"
0x18003d4c0  lea     rcx, qword_180171FD0
0x18003d4c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d4cc  nop
0x18003d4cd  mov     eax, 0CEh
0x18003d4d2  mov     cs:word_180171FF0, ax
0x18003d4d9  lea     rdx, aPartialContent; "Partial Content"
0x18003d4e0  lea     rcx, qword_180171FF8
0x18003d4e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d4ec  nop
0x18003d4ed  mov     eax, 0CFh
0x18003d4f2  mov     cs:word_180172018, ax
0x18003d4f9  lea     rdx, aMultiStatus; "Multi-Status"
0x18003d500  lea     rcx, qword_180172020
0x18003d507  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d50c  nop
0x18003d50d  mov     eax, 0D0h
0x18003d512  mov     cs:word_180172040, ax
0x18003d519  lea     rdx, aAlreadyReporte; "Already Reported"
0x18003d520  lea     rcx, qword_180172048
0x18003d527  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d52c  nop
0x18003d52d  mov     eax, 0E2h
0x18003d532  mov     cs:word_180172068, ax
0x18003d539  lea     rdx, aImUsed; "IM Used"
0x18003d540  lea     rcx, qword_180172070
0x18003d547  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d54c  nop
0x18003d54d  mov     eax, 12Ch
0x18003d552  mov     cs:word_180172090, ax
0x18003d559  lea     rdx, aMultipleChoice; "Multiple Choices"
0x18003d560  lea     rcx, qword_180172098
0x18003d567  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d56c  nop
0x18003d56d  mov     eax, 12Dh
0x18003d572  mov     cs:word_1801720B8, ax
0x18003d579  lea     rdx, aMovedPermanent; "Moved Permanently"
0x18003d580  lea     rcx, qword_1801720C0
0x18003d587  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d58c  nop
0x18003d58d  mov     eax, 12Eh
0x18003d592  mov     cs:word_1801720E0, ax
0x18003d599  lea     rdx, aFound; "Found"
0x18003d5a0  lea     rcx, qword_1801720E8
0x18003d5a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d5ac  nop
0x18003d5ad  mov     eax, 12Fh
0x18003d5b2  mov     cs:word_180172108, ax
0x18003d5b9  lea     rdx, aSeeOther; "See Other"
0x18003d5c0  lea     rcx, qword_180172110
0x18003d5c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d5cc  nop
0x18003d5cd  mov     eax, 130h
0x18003d5d2  mov     cs:word_180172130, ax
0x18003d5d9  lea     rdx, aNotModified; "Not Modified"
0x18003d5e0  lea     rcx, qword_180172138
0x18003d5e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d5ec  nop
0x18003d5ed  mov     eax, 131h
0x18003d5f2  mov     cs:word_180172158, ax
0x18003d5f9  lea     rdx, aUseProxy; "Use Proxy"
0x18003d600  lea     rcx, qword_180172160
0x18003d607  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d60c  nop
0x18003d60d  mov     eax, 133h
0x18003d612  mov     cs:word_180172180, ax
0x18003d619  lea     rdx, aTemporaryRedir; "Temporary Redirect"
0x18003d620  lea     rcx, qword_180172188
0x18003d627  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d62c  nop
0x18003d62d  mov     eax, 134h
0x18003d632  mov     cs:word_1801721A8, ax
0x18003d639  lea     rdx, aPermanentRedir; "Permanent Redirect"
0x18003d640  lea     rcx, qword_1801721B0
0x18003d647  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d64c  nop
0x18003d64d  mov     eax, 190h
0x18003d652  mov     cs:word_1801721D0, ax
0x18003d659  lea     rdx, aBadRequest; "Bad Request"
0x18003d660  lea     rcx, qword_1801721D8
0x18003d667  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d66c  nop
0x18003d66d  mov     eax, 191h
0x18003d672  mov     cs:word_1801721F8, ax
0x18003d679  lea     rdx, aUnauthorized; "Unauthorized"
0x18003d680  lea     rcx, qword_180172200
0x18003d687  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d68c  nop
0x18003d68d  mov     eax, 192h
0x18003d692  mov     cs:word_180172220, ax
0x18003d699  lea     rdx, aPaymentRequire; "Payment Required"
0x18003d6a0  lea     rcx, qword_180172228
0x18003d6a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d6ac  nop
0x18003d6ad  mov     eax, 193h
0x18003d6b2  mov     cs:word_180172248, ax
0x18003d6b9  lea     rdx, aForbidden; "Forbidden"
0x18003d6c0  lea     rcx, qword_180172250
0x18003d6c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d6cc  nop
0x18003d6cd  mov     eax, 194h
0x18003d6d2  mov     cs:word_180172270, ax
0x18003d6d9  lea     rdx, aNotFound_0; "Not Found"
0x18003d6e0  lea     rcx, qword_180172278
0x18003d6e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d6ec  nop
0x18003d6ed  mov     eax, 195h
0x18003d6f2  mov     cs:word_180172298, ax
0x18003d6f9  lea     rdx, aMethodNotAllow; "Method Not Allowed"
0x18003d700  lea     rcx, qword_1801722A0
0x18003d707  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d70c  nop
0x18003d70d  mov     eax, 196h
0x18003d712  mov     cs:word_1801722C0, ax
0x18003d719  lea     rdx, aNotAcceptable; "Not Acceptable"
0x18003d720  lea     rcx, qword_1801722C8
0x18003d727  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d72c  nop
0x18003d72d  mov     eax, 197h
0x18003d732  mov     cs:word_1801722E8, ax
0x18003d739  lea     rdx, aProxyAuthentic; "Proxy Authentication Required"
0x18003d740  lea     rcx, qword_1801722F0
0x18003d747  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d74c  nop
0x18003d74d  mov     eax, 198h
0x18003d752  mov     cs:word_180172310, ax
0x18003d759  lea     rdx, aRequestTimeOut; "Request Time-out"
0x18003d760  lea     rcx, qword_180172318
0x18003d767  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d76c  nop
0x18003d76d  mov     eax, 199h
0x18003d772  mov     cs:word_180172338, ax
0x18003d779  lea     rdx, aConflict; "Conflict"
0x18003d780  lea     rcx, qword_180172340
0x18003d787  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d78c  nop
0x18003d78d  mov     eax, 19Ah
0x18003d792  mov     cs:word_180172360, ax
0x18003d799  lea     rdx, aGone; "Gone"
0x18003d7a0  lea     rcx, qword_180172368
0x18003d7a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d7ac  nop
0x18003d7ad  mov     eax, 19Bh
0x18003d7b2  mov     cs:word_180172388, ax
0x18003d7b9  lea     rdx, aLengthRequired; "Length Required"
0x18003d7c0  lea     rcx, qword_180172390
0x18003d7c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d7cc  nop
0x18003d7cd  mov     eax, 19Ch
0x18003d7d2  mov     cs:word_1801723B0, ax
0x18003d7d9  lea     rdx, aPreconditionFa; "Precondition Failed"
0x18003d7e0  lea     rcx, qword_1801723B8
0x18003d7e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d7ec  nop
0x18003d7ed  mov     eax, 19Dh
0x18003d7f2  mov     cs:word_1801723D8, ax
0x18003d7f9  lea     rdx, aRequestEntityT; "Request Entity Too Large"
0x18003d800  lea     rcx, qword_1801723E0
0x18003d807  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d80c  nop
0x18003d80d  mov     eax, 19Eh
0x18003d812  mov     cs:word_180172400, ax
0x18003d819  lea     rdx, aRequestUriTooL; "Request Uri Too Large"
0x18003d820  lea     rcx, qword_180172408
0x18003d827  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d82c  nop
0x18003d82d  mov     eax, 19Fh
0x18003d832  mov     cs:word_180172428, ax
0x18003d839  lea     rdx, aUnsupportedMed; "Unsupported Media Type"
0x18003d840  lea     rcx, qword_180172430
0x18003d847  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d84c  nop
0x18003d84d  mov     eax, 1A0h
0x18003d852  mov     cs:word_180172450, ax
0x18003d859  lea     rdx, aRequestedRange; "Requested range not satisfiable"
0x18003d860  lea     rcx, qword_180172458
0x18003d867  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d86c  nop
0x18003d86d  mov     eax, 1A1h
0x18003d872  mov     cs:word_180172478, ax
0x18003d879  lea     rdx, aExpectationFai; "Expectation Failed"
0x18003d880  lea     rcx, qword_180172480
0x18003d887  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d88c  nop
0x18003d88d  mov     eax, 1A5h
0x18003d892  mov     cs:word_1801724A0, ax
0x18003d899  lea     rdx, aMisdirectedReq; "Misdirected Request"
0x18003d8a0  lea     rcx, qword_1801724A8
0x18003d8a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d8ac  nop
0x18003d8ad  mov     eax, 1A6h
0x18003d8b2  mov     cs:word_1801724C8, ax
0x18003d8b9  lea     rdx, aUnprocessableE; "Unprocessable Entity"
0x18003d8c0  lea     rcx, qword_1801724D0
0x18003d8c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d8cc  nop
0x18003d8cd  mov     eax, 1A7h
0x18003d8d2  mov     cs:word_1801724F0, ax
0x18003d8d9  lea     rdx, aLocked; "Locked"
0x18003d8e0  lea     rcx, qword_1801724F8
0x18003d8e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d8ec  nop
0x18003d8ed  mov     eax, 1A8h
0x18003d8f2  mov     cs:word_180172518, ax
0x18003d8f9  lea     rdx, aFailedDependen; "Failed Dependency"
  ... truncated ...
```

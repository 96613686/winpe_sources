# web::http::details::get_default_reason_phrase(ushort)

- ea: `0x1800c7690`
- end: `0x1800c7ebb`
- name: `?get_default_reason_phrase@details@http@web@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z`
- size: `2091`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b9d30`

## callees

- `0x180019568`
- `0x18001971c`
- `0x180019784`
- `0x1800c7690`
- `0x1800e53ec`
- `0x1800e68b0`

## string_xrefs

- `0x1800c7789`: `Switching Protocols`
- `0x1800c77c9`: `Created`
- `0x1800c78a9`: `Already Reported`
- `0x1800c7909`: `Moved Permanently`
- `0x1800c79a9`: `Temporary Redirect`
- `0x1800c7ba9`: `Request Uri Too Large`
- `0x1800c7da9`: `Service Unavailable`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
__int64 *__fastcall web::http::details::get_default_reason_phrase(__int64 *a1, __int16 a2)
{
  __int64 *v4; // rax
  __int64 *v6; // rdx

  if ( dword_1802652D0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1802652D0);
    if ( dword_1802652D0 == -1 )
    {
      std::wstring::wstring(qword_18025B9F8, L"Continue");
      word_18025BA18 = 101;
      std::wstring::wstring(qword_18025BA20, L"Switching Protocols");
      word_18025BA40 = 200;
      std::wstring::wstring(qword_18025BA48, L"OK");
      word_18025BA68 = 201;
      std::wstring::wstring(qword_18025BA70, L"Created");
      word_18025BA90 = 202;
      std::wstring::wstring(qword_18025BA98, L"Accepted");
      word_18025BAB8 = 203;
      std::wstring::wstring(qword_18025BAC0, L"Non-Authoritative Information");
      word_18025BAE0 = 204;
      std::wstring::wstring(qword_18025BAE8, L"No Content");
      word_18025BB08 = 205;
      std::wstring::wstring(qword_18025BB10, L"Reset Content");
      word_18025BB30 = 206;
      std::wstring::wstring(qword_18025BB38, L"Partial Content");
      word_18025BB58 = 207;
      std::wstring::wstring(qword_18025BB60, L"Multi-Status");
      word_18025BB80 = 208;
      std::wstring::wstring(qword_18025BB88, L"Already Reported");
      word_18025BBA8 = 226;
      std::wstring::wstring(qword_18025BBB0, L"IM Used");
      word_18025BBD0 = 300;
      std::wstring::wstring(qword_18025BBD8, L"Multiple Choices");
      word_18025BBF8 = 301;
      std::wstring::wstring(qword_18025BC00, L"Moved Permanently");
      word_18025BC20 = 302;
      std::wstring::wstring(qword_18025BC28, L"Found");
      word_18025BC48 = 303;
      std::wstring::wstring(qword_18025BC50, L"See Other");
      word_18025BC70 = 304;
      std::wstring::wstring(qword_18025BC78, L"Not Modified");
      word_18025BC98 = 305;
      std::wstring::wstring(qword_18025BCA0, L"Use Proxy");
      word_18025BCC0 = 307;
      std::wstring::wstring(qword_18025BCC8, L"Temporary Redirect");
      word_18025BCE8 = 308;
      std::wstring::wstring(qword_18025BCF0, L"Permanent Redirect");
      word_18025BD10 = 400;
      std::wstring::wstring(qword_18025BD18, L"Bad Request");
      word_18025BD38 = 401;
      std::wstring::wstring(qword_18025BD40, L"Unauthorized");
      word_18025BD60 = 402;
      std::wstring::wstring(qword_18025BD68, L"Payment Required");
      word_18025BD88 = 403;
      std::wstring::wstring(qword_18025BD90, L"Forbidden");
      word_18025BDB0 = 404;
      std::wstring::wstring(qword_18025BDB8, L"Not Found");
      word_18025BDD8 = 405;
      std::wstring::wstring(qword_18025BDE0, L"Method Not Allowed");
      word_18025BE00 = 406;
      std::wstring::wstring(qword_18025BE08, L"Not Acceptable");
      word_18025BE28 = 407;
      std::wstring::wstring(qword_18025BE30, L"Proxy Authentication Required");
      word_18025BE50 = 408;
      std::wstring::wstring(qword_18025BE58, L"Request Time-out");
      word_18025BE78 = 409;
      std::wstring::wstring(qword_18025BE80, L"Conflict");
      word_18025BEA0 = 410;
      std::wstring::wstring(qword_18025BEA8, L"Gone");
      word_18025BEC8 = 411;
      std::wstring::wstring(qword_18025BED0, L"Length Required");
      word_18025BEF0 = 412;
      std::wstring::wstring(qword_18025BEF8, L"Precondition Failed");
      word_18025BF18 = 413;
      std::wstring::wstring(qword_18025BF20, L"Request Entity Too Large");
      word_18025BF40 = 414;
      std::wstring::wstring(qword_18025BF48, L"Request Uri Too Large");
      word_18025BF68 = 415;
      std::wstring::wstring(qword_18025BF70, L"Unsupported Media Type");
      word_18025BF90 = 416;
      std::wstring::wstring(qword_18025BF98, L"Requested range not satisfiable");
      word_18025BFB8 = 417;
      std::wstring::wstring(qword_18025BFC0, L"Expectation Failed");
      word_18025BFE0 = 421;
      std::wstring::wstring(qword_18025BFE8, L"Misdirected Request");
      word_18025C008 = 422;
      std::wstring::wstring(qword_18025C010, L"Unprocessable Entity");
      word_18025C030 = 423;
      std::wstring::wstring(qword_18025C038, L"Locked");
      word_18025C058 = 424;
      std::wstring::wstring(qword_18025C060, L"Failed Dependency");
      word_18025C080 = 426;
      std::wstring::wstring(qword_18025C088, L"Upgrade Required");
      word_18025C0A8 = 428;
      std::wstring::wstring(qword_18025C0B0, L"Precondition Required");
      word_18025C0D0 = 429;
      std::wstring::wstring(qword_18025C0D8, L"Too Many Requests");
      word_18025C0F8 = 431;
      std::wstring::wstring(qword_18025C100, L"Request Header Fields Too Large");
      word_18025C120 = 451;
      std::wstring::wstring(qword_18025C128, L"Unavailable For Legal Reasons");
      word_18025C148 = 500;
      std::wstring::wstring(qword_18025C150, L"Internal Error");
      word_18025C170 = 501;
      std::wstring::wstring(qword_18025C178, L"Not Implemented");
      word_18025C198 = 502;
      std::wstring::wstring(qword_18025C1A0, L"Bad Gateway");
      word_18025C1C0 = 503;
      std::wstring::wstring(qword_18025C1C8, L"Service Unavailable");
      word_18025C1E8 = 504;
      std::wstring::wstring(qword_18025C1F0, L"Gateway Time-out");
      word_18025C210 = 505;
      std::wstring::wstring(qword_18025C218, L"HTTP Version not supported");
      word_18025C238 = 506;
      std::wstring::wstring(qword_18025C240, L"Variant Also Negotiates");
      word_18025C260 = 507;
      std::wstring::wstring(qword_18025C268, L"Insufficient Storage");
      word_18025C288 = 508;
      std::wstring::wstring(qword_18025C290, L"Loop Detected");
      word_18025C2B0 = 510;
      std::wstring::wstring(qword_18025C2B8, L"Not Extended");
      word_18025C2D8 = 511;
      std::wstring::wstring(qword_18025C2E0, L"Network Authentication Required");
      atexit(web::http::details::get_default_reason_phrase_::_2_::_dynamic_atexit_destructor_for__idToPhraseMap__);
      Init_thread_footer(&dword_1802652D0);
    }
  }
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 7;
  *(_WORD *)a1 = 0;
  v4 = &qword_18025B9F0;
  while ( *(_WORD *)v4 != a2 )
  {
    v4 += 5;
    if ( v4 == (__int64 *)&_scrt_ucrt_dll_is_in_use )
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
0x1800c7690  mov     [rsp+arg_8], rbx
0x1800c7695  mov     [rsp+arg_0], rcx
0x1800c769a  push    rdi
0x1800c769b  sub     rsp, 30h
0x1800c769f  movzx   edi, dx
0x1800c76a2  mov     rbx, rcx
0x1800c76a5  mov     [rsp+38h+var_18], 0
0x1800c76ad  mov     r8d, cs:_tls_index
0x1800c76b4  mov     rax, gs:58h
0x1800c76bd  mov     ecx, 4
0x1800c76c2  mov     rax, [rax+r8*8]
0x1800c76c6  mov     eax, [rcx+rax]
0x1800c76c9  cmp     cs:dword_1802652D0, eax
0x1800c76cf  jg      short loc_1800C7750
0x1800c76d1  xorps   xmm0, xmm0
0x1800c76d4  movups  xmmword ptr [rbx], xmm0
0x1800c76d7  mov     qword ptr [rbx+10h], 0
0x1800c76df  mov     qword ptr [rbx+18h], 7
0x1800c76e7  xor     eax, eax
0x1800c76e9  mov     [rbx], ax
0x1800c76ec  mov     [rsp+38h+var_18], 1
0x1800c76f4  lea     rax, qword_18025B9F0
0x1800c76fb  lea     rcx, __scrt_ucrt_dll_is_in_use
0x1800c7702  cmp     [rax], di
0x1800c7705  jz      short loc_1800C771E
0x1800c7707  add     rax, 28h ; '('
0x1800c770b  cmp     rax, rcx
0x1800c770e  jnz     short loc_1800C7702
0x1800c7710  mov     rax, rbx
0x1800c7713  mov     rbx, [rsp+38h+arg_8]
0x1800c7718  add     rsp, 30h
0x1800c771c  pop     rdi
0x1800c771d  retn
0x1800c771e  lea     r8, [rax+8]
0x1800c7722  cmp     rbx, r8
0x1800c7725  jz      short loc_1800C7742
0x1800c7727  cmp     qword ptr [r8+18h], 7
0x1800c772c  jbe     short loc_1800C7733
0x1800c772e  mov     rdx, [r8]
0x1800c7731  jmp     short loc_1800C7736
0x1800c7733  mov     rdx, r8
0x1800c7736  mov     r8, [r8+10h]
0x1800c773a  mov     rcx, rbx
0x1800c773d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c7742  mov     rax, rbx
0x1800c7745  mov     rbx, [rsp+38h+arg_8]
0x1800c774a  add     rsp, 30h
0x1800c774e  pop     rdi
0x1800c774f  retn
0x1800c7750  lea     rcx, dword_1802652D0
0x1800c7757  call    _Init_thread_header
0x1800c775c  cmp     cs:dword_1802652D0, 0FFFFFFFFh
0x1800c7763  jnz     loc_1800C76D1
0x1800c7769  lea     rdx, aContinue; "Continue"
0x1800c7770  lea     rcx, qword_18025B9F8
0x1800c7777  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c777c  nop
0x1800c777d  mov     eax, 65h ; 'e'
0x1800c7782  mov     cs:word_18025BA18, ax
0x1800c7789  lea     rdx, aSwitchingProto; "Switching Protocols"
0x1800c7790  lea     rcx, qword_18025BA20
0x1800c7797  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c779c  nop
0x1800c779d  mov     eax, 0C8h
0x1800c77a2  mov     cs:word_18025BA40, ax
0x1800c77a9  lea     rdx, aOk; "OK"
0x1800c77b0  lea     rcx, qword_18025BA48
0x1800c77b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c77bc  nop
0x1800c77bd  mov     eax, 0C9h
0x1800c77c2  mov     cs:word_18025BA68, ax
0x1800c77c9  lea     rdx, aCreated; "Created"
0x1800c77d0  lea     rcx, qword_18025BA70
0x1800c77d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c77dc  nop
0x1800c77dd  mov     eax, 0CAh
0x1800c77e2  mov     cs:word_18025BA90, ax
0x1800c77e9  lea     rdx, aAccepted; "Accepted"
0x1800c77f0  lea     rcx, qword_18025BA98
0x1800c77f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c77fc  nop
0x1800c77fd  mov     eax, 0CBh
0x1800c7802  mov     cs:word_18025BAB8, ax
0x1800c7809  lea     rdx, aNonAuthoritati; "Non-Authoritative Information"
0x1800c7810  lea     rcx, qword_18025BAC0
0x1800c7817  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c781c  nop
0x1800c781d  mov     eax, 0CCh
0x1800c7822  mov     cs:word_18025BAE0, ax
0x1800c7829  lea     rdx, aNoContent; "No Content"
0x1800c7830  lea     rcx, qword_18025BAE8
0x1800c7837  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c783c  nop
0x1800c783d  mov     eax, 0CDh
0x1800c7842  mov     cs:word_18025BB08, ax
0x1800c7849  lea     rdx, aResetContent; "Reset Content"
0x1800c7850  lea     rcx, qword_18025BB10
0x1800c7857  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c785c  nop
0x1800c785d  mov     eax, 0CEh
0x1800c7862  mov     cs:word_18025BB30, ax
0x1800c7869  lea     rdx, aPartialContent; "Partial Content"
0x1800c7870  lea     rcx, qword_18025BB38
0x1800c7877  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c787c  nop
0x1800c787d  mov     eax, 0CFh
0x1800c7882  mov     cs:word_18025BB58, ax
0x1800c7889  lea     rdx, aMultiStatus; "Multi-Status"
0x1800c7890  lea     rcx, qword_18025BB60
0x1800c7897  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c789c  nop
0x1800c789d  mov     eax, 0D0h
0x1800c78a2  mov     cs:word_18025BB80, ax
0x1800c78a9  lea     rdx, aAlreadyReporte; "Already Reported"
0x1800c78b0  lea     rcx, qword_18025BB88
0x1800c78b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c78bc  nop
0x1800c78bd  mov     eax, 0E2h
0x1800c78c2  mov     cs:word_18025BBA8, ax
0x1800c78c9  lea     rdx, aImUsed; "IM Used"
0x1800c78d0  lea     rcx, qword_18025BBB0
0x1800c78d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c78dc  nop
0x1800c78dd  mov     eax, 12Ch
0x1800c78e2  mov     cs:word_18025BBD0, ax
0x1800c78e9  lea     rdx, aMultipleChoice; "Multiple Choices"
0x1800c78f0  lea     rcx, qword_18025BBD8
0x1800c78f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c78fc  nop
0x1800c78fd  mov     eax, 12Dh
0x1800c7902  mov     cs:word_18025BBF8, ax
0x1800c7909  lea     rdx, aMovedPermanent; "Moved Permanently"
0x1800c7910  lea     rcx, qword_18025BC00
0x1800c7917  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c791c  nop
0x1800c791d  mov     eax, 12Eh
0x1800c7922  mov     cs:word_18025BC20, ax
0x1800c7929  lea     rdx, aFound; "Found"
0x1800c7930  lea     rcx, qword_18025BC28
0x1800c7937  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c793c  nop
0x1800c793d  mov     eax, 12Fh
0x1800c7942  mov     cs:word_18025BC48, ax
0x1800c7949  lea     rdx, aSeeOther; "See Other"
0x1800c7950  lea     rcx, qword_18025BC50
0x1800c7957  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c795c  nop
0x1800c795d  mov     eax, 130h
0x1800c7962  mov     cs:word_18025BC70, ax
0x1800c7969  lea     rdx, aNotModified; "Not Modified"
0x1800c7970  lea     rcx, qword_18025BC78
0x1800c7977  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c797c  nop
0x1800c797d  mov     eax, 131h
0x1800c7982  mov     cs:word_18025BC98, ax
0x1800c7989  lea     rdx, aUseProxy; "Use Proxy"
0x1800c7990  lea     rcx, qword_18025BCA0
0x1800c7997  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c799c  nop
0x1800c799d  mov     eax, 133h
0x1800c79a2  mov     cs:word_18025BCC0, ax
0x1800c79a9  lea     rdx, aTemporaryRedir; "Temporary Redirect"
0x1800c79b0  lea     rcx, qword_18025BCC8
0x1800c79b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c79bc  nop
0x1800c79bd  mov     eax, 134h
0x1800c79c2  mov     cs:word_18025BCE8, ax
0x1800c79c9  lea     rdx, aPermanentRedir; "Permanent Redirect"
0x1800c79d0  lea     rcx, qword_18025BCF0
0x1800c79d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c79dc  nop
0x1800c79dd  mov     eax, 190h
0x1800c79e2  mov     cs:word_18025BD10, ax
0x1800c79e9  lea     rdx, aBadRequest; "Bad Request"
0x1800c79f0  lea     rcx, qword_18025BD18
0x1800c79f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c79fc  nop
0x1800c79fd  mov     eax, 191h
0x1800c7a02  mov     cs:word_18025BD38, ax
0x1800c7a09  lea     rdx, aUnauthorized; "Unauthorized"
0x1800c7a10  lea     rcx, qword_18025BD40
0x1800c7a17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7a1c  nop
0x1800c7a1d  mov     eax, 192h
0x1800c7a22  mov     cs:word_18025BD60, ax
0x1800c7a29  lea     rdx, aPaymentRequire; "Payment Required"
0x1800c7a30  lea     rcx, qword_18025BD68
0x1800c7a37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7a3c  nop
0x1800c7a3d  mov     eax, 193h
0x1800c7a42  mov     cs:word_18025BD88, ax
0x1800c7a49  lea     rdx, aForbidden; "Forbidden"
0x1800c7a50  lea     rcx, qword_18025BD90
0x1800c7a57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7a5c  nop
0x1800c7a5d  mov     eax, 194h
0x1800c7a62  mov     cs:word_18025BDB0, ax
0x1800c7a69  lea     rdx, aNotFound; "Not Found"
0x1800c7a70  lea     rcx, qword_18025BDB8
0x1800c7a77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7a7c  nop
0x1800c7a7d  mov     eax, 195h
0x1800c7a82  mov     cs:word_18025BDD8, ax
0x1800c7a89  lea     rdx, aMethodNotAllow; "Method Not Allowed"
0x1800c7a90  lea     rcx, qword_18025BDE0
0x1800c7a97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7a9c  nop
0x1800c7a9d  mov     eax, 196h
0x1800c7aa2  mov     cs:word_18025BE00, ax
0x1800c7aa9  lea     rdx, aNotAcceptable; "Not Acceptable"
0x1800c7ab0  lea     rcx, qword_18025BE08
0x1800c7ab7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7abc  nop
0x1800c7abd  mov     eax, 197h
0x1800c7ac2  mov     cs:word_18025BE28, ax
0x1800c7ac9  lea     rdx, aProxyAuthentic; "Proxy Authentication Required"
0x1800c7ad0  lea     rcx, qword_18025BE30
0x1800c7ad7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7adc  nop
0x1800c7add  mov     eax, 198h
0x1800c7ae2  mov     cs:word_18025BE50, ax
0x1800c7ae9  lea     rdx, aRequestTimeOut; "Request Time-out"
0x1800c7af0  lea     rcx, qword_18025BE58
0x1800c7af7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7afc  nop
0x1800c7afd  mov     eax, 199h
0x1800c7b02  mov     cs:word_18025BE78, ax
0x1800c7b09  lea     rdx, aConflict; "Conflict"
0x1800c7b10  lea     rcx, qword_18025BE80
0x1800c7b17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7b1c  nop
0x1800c7b1d  mov     eax, 19Ah
0x1800c7b22  mov     cs:word_18025BEA0, ax
0x1800c7b29  lea     rdx, aGone; "Gone"
0x1800c7b30  lea     rcx, qword_18025BEA8
0x1800c7b37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7b3c  nop
0x1800c7b3d  mov     eax, 19Bh
0x1800c7b42  mov     cs:word_18025BEC8, ax
0x1800c7b49  lea     rdx, aLengthRequired; "Length Required"
0x1800c7b50  lea     rcx, qword_18025BED0
0x1800c7b57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7b5c  nop
0x1800c7b5d  mov     eax, 19Ch
0x1800c7b62  mov     cs:word_18025BEF0, ax
0x1800c7b69  lea     rdx, aPreconditionFa; "Precondition Failed"
0x1800c7b70  lea     rcx, qword_18025BEF8
0x1800c7b77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7b7c  nop
0x1800c7b7d  mov     eax, 19Dh
0x1800c7b82  mov     cs:word_18025BF18, ax
0x1800c7b89  lea     rdx, aRequestEntityT; "Request Entity Too Large"
0x1800c7b90  lea     rcx, qword_18025BF20
0x1800c7b97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7b9c  nop
0x1800c7b9d  mov     eax, 19Eh
0x1800c7ba2  mov     cs:word_18025BF40, ax
0x1800c7ba9  lea     rdx, aRequestUriTooL; "Request Uri Too Large"
0x1800c7bb0  lea     rcx, qword_18025BF48
0x1800c7bb7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7bbc  nop
0x1800c7bbd  mov     eax, 19Fh
0x1800c7bc2  mov     cs:word_18025BF68, ax
0x1800c7bc9  lea     rdx, aUnsupportedMed; "Unsupported Media Type"
0x1800c7bd0  lea     rcx, qword_18025BF70
0x1800c7bd7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7bdc  nop
0x1800c7bdd  mov     eax, 1A0h
0x1800c7be2  mov     cs:word_18025BF90, ax
0x1800c7be9  lea     rdx, aRequestedRange; "Requested range not satisfiable"
0x1800c7bf0  lea     rcx, qword_18025BF98
0x1800c7bf7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7bfc  nop
0x1800c7bfd  mov     eax, 1A1h
0x1800c7c02  mov     cs:word_18025BFB8, ax
0x1800c7c09  lea     rdx, aExpectationFai; "Expectation Failed"
0x1800c7c10  lea     rcx, qword_18025BFC0
0x1800c7c17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7c1c  nop
0x1800c7c1d  mov     eax, 1A5h
0x1800c7c22  mov     cs:word_18025BFE0, ax
0x1800c7c29  lea     rdx, aMisdirectedReq; "Misdirected Request"
0x1800c7c30  lea     rcx, qword_18025BFE8
0x1800c7c37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7c3c  nop
0x1800c7c3d  mov     eax, 1A6h
0x1800c7c42  mov     cs:word_18025C008, ax
0x1800c7c49  lea     rdx, aUnprocessableE; "Unprocessable Entity"
0x1800c7c50  lea     rcx, qword_18025C010
0x1800c7c57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7c5c  nop
0x1800c7c5d  mov     eax, 1A7h
0x1800c7c62  mov     cs:word_18025C030, ax
0x1800c7c69  lea     rdx, aLocked; "Locked"
0x1800c7c70  lea     rcx, qword_18025C038
0x1800c7c77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7c7c  nop
0x1800c7c7d  mov     eax, 1A8h
0x1800c7c82  mov     cs:word_18025C058, ax
0x1800c7c89  lea     rdx, aFailedDependen; "Failed Dependency"
  ... truncated ...
```

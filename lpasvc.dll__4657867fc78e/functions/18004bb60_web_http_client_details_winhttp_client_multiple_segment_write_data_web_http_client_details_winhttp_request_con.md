# `web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_::operator()(pplx::task<unsigned __int64>)

- ea: `0x18004bb60`
- end: `0x18004be4e`
- name: `??R_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@3456@@Z@QEBA@V?$task@_K@pplx@@@Z`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x18004de10`

## callees

- `0x18000df90`
- `0x18000e430`
- `0x18000e46c`
- `0x18000eab2`
- `0x180032c30`
- `0x180035460`
- `0x180038ff0`
- `0x18004bb60`
- `0x18004fbe0`
- `0x180063668`
- `0x18006511c`
- `0x1800a6b60`
- `0x1800c175c`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd10`
- `WINHTTP!WinHttpWriteData` at `0x18004bd02`
- `WINHTTP!WinHttpWriteData` at `0x18004bd02`

## string_xrefs

- `0x18004bd53`: `WinHttpWriteData`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall `web::http::client::details::winhttp_client::_multiple_segment_write_data'::`21'::_lambda_1_::operator()(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v4; // rax
  void *v5; // rax
  const struct std::nothrow_t *v6; // rdx
  void *v7; // rcx
  volatile signed __int32 *v8; // rdi
  __int64 v9; // rcx
  const void *v10; // rdx
  DWORD LastError; // ebx
  __int64 v12; // r8
  const struct std::nothrow_t *v13; // rdx
  void *v14; // rcx
  __int64 v15; // rax
  __int128 v18; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-98h]
  __int64 v20; // [rsp+48h] [rbp-90h]
  void *Src[3]; // [rsp+50h] [rbp-88h] BYREF
  unsigned __int64 v22; // [rsp+68h] [rbp-70h]
  void **v23; // [rsp+70h] [rbp-68h] BYREF
  __int128 v24; // [rsp+78h] [rbp-60h] BYREF
  int v25; // [rsp+88h] [rbp-50h]
  void ***v26; // [rsp+90h] [rbp-48h]
  _BYTE v27[40]; // [rsp+98h] [rbp-40h] BYREF

  try
  {
    v4 = pplx::task<unsigned __int64>::get(a2);
  }
  catch ( ... )
  {
    v15 = std::current_exception(&v18);
    web::http::client::details::request_context::report_exception(*a1, v15);
    pplx::task<long>::~task<long>(a2);
    return;
  }
  if ( v4 )
  {
    *(_QWORD *)(*a1 + 144LL) -= v4;
    if ( !*(_QWORD *)(*a1 + 144LL) )
      *(_DWORD *)(*a1 + 136LL) = 0;
    v9 = *a1;
    v10 = *(const void **)(*a1 + 216LL);
    if ( !v10 )
      v10 = *(const void **)(v9 + 224);
    if ( WinHttpWriteData(*(HINTERNET *)(v9 + 104), v10, v4, 0) )
      goto LABEL_9;
    LastError = GetLastError();
    v18 = 0;
    *(_QWORD *)&v18 = operator new(0x20u);
    v19 = 16;
    v20 = 31;
    strcpy((char *)v18, "WinHttpWriteData");
    v12 = web::http::client::details::build_error_msg(Src);
    web::http::client::details::request_context::report_error(*a1, LastError, v12);
    if ( v22 > 0xF )
    {
      v13 = (const struct std::nothrow_t *)(v22 + 1);
      if ( v22 + 1 < 0x1000 )
      {
        v14 = Src[0];
      }
      else
      {
        v14 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v14 - 8) > 0x1F )
          __fastfail(5u);
        v13 = (const struct std::nothrow_t *)(v22 + 40);
      }
      operator delete(v14, v13);
    }
    Src[2] = 0;
    v22 = 15;
    LOBYTE(Src[0]) = 0;
    v5 = (void *)v18;
    v6 = (const struct std::nothrow_t *)(v20 + 1);
    if ( (unsigned __int64)(v20 + 1) >= 0x1000 )
    {
      v7 = *(void **)(v18 - 8);
      if ( (unsigned __int64)(v18 - (_QWORD)v7 - 8) <= 0x1F )
      {
        v6 = (const struct std::nothrow_t *)(v20 + 40);
        goto LABEL_8;
      }
      goto LABEL_29;
    }
LABEL_7:
    v7 = v5;
    goto LABEL_8;
  }
  std::wstring::wstring(Src, L"Unexpected end of request body stream encountered before Content-Length met.");
  v24 = 0;
  v23 = &web::http::http_exception::`vftable';
  v25 = 0;
  v26 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  utility::conversions::to_utf8string(v27, Src);
  web::http::client::details::request_context::report_exception<web::http::http_exception>(*a1, &v23);
  std::tuple<char const *,std::string>::~tuple<char const *,std::string>(v27);
  v23 = &std::exception::`vftable';
  o___std_exception_destroy_0(&v24);
  if ( v22 > 7 )
  {
    v5 = Src[0];
    v6 = (const struct std::nothrow_t *)(2 * v22 + 2);
    if ( (unsigned __int64)v6 >= 0x1000 )
    {
      v7 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v7 - 8) <= 0x1F )
      {
        v6 = (const struct std::nothrow_t *)(2 * v22 + 41);
LABEL_8:
        operator delete(v7, v6);
        goto LABEL_9;
      }
LABEL_29:
      __fastfail(5u);
    }
    goto LABEL_7;
  }
LABEL_9:
  v8 = (volatile signed __int32 *)a2[1];
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
}

```

## disassembly

```asm
0x18004bb60  mov     [rsp+arg_10], rbx
0x18004bb65  mov     [rsp+arg_18], rsi
0x18004bb6a  push    rdi
0x18004bb6b  sub     rsp, 0D0h
0x18004bb72  mov     rax, cs:__security_cookie
0x18004bb79  xor     rax, rsp
0x18004bb7c  mov     [rsp+0D8h+var_18], rax
0x18004bb84  mov     rsi, rdx
0x18004bb87  mov     rdi, rcx
0x18004bb8a  mov     [rsp+0D8h+var_B8], rcx
0x18004bb8f  mov     [rsp+0D8h+var_B0], rdx
0x18004bb94  mov     rcx, rdx
0x18004bb97  call    ?get@?$task@_K@pplx@@QEBA_KXZ; pplx::task<unsigned __int64>::get(void)
0x18004bb9c  mov     r8, rax; dwNumberOfBytesToWrite
0x18004bb9f  test    r8, r8
0x18004bba2  jnz     loc_18004BCC4
0x18004bba8  lea     rdx, aUnexpectedEndO_0; "Unexpected end of request body stream e"...
0x18004bbaf  lea     rcx, [rsp+0D8h+Src]
0x18004bbb4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004bbb9  nop
0x18004bbba  xorps   xmm0, xmm0
0x18004bbbd  movups  [rsp+0D8h+var_60], xmm0
0x18004bbc2  lea     rax, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x18004bbc9  mov     [rsp+0D8h+var_68], rax
0x18004bbce  mov     [rsp+0D8h+var_50], 0
0x18004bbd9  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18004bbe0  mov     [rsp+0D8h+var_48], rax
0x18004bbe8  lea     rdx, [rsp+0D8h+Src]
0x18004bbed  lea     rcx, [rsp+0D8h+var_40]
0x18004bbf5  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x18004bbfa  nop
0x18004bbfb  lea     rdx, [rsp+0D8h+var_68]
0x18004bc00  mov     rcx, [rdi]
0x18004bc03  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x18004bc08  nop
0x18004bc09  lea     rcx, [rsp+0D8h+var_40]
0x18004bc11  call    ??1?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@XZ; std::tuple<char const *,std::string>::~tuple<char const *,std::string>(void)
0x18004bc16  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18004bc1d  mov     [rsp+0D8h+var_68], rax
0x18004bc22  lea     rcx, [rsp+0D8h+var_60]
0x18004bc27  call    _o___std_exception_destroy_0
0x18004bc2c  nop
0x18004bc2d  mov     rdx, [rsp+0D8h+var_70]
0x18004bc32  cmp     rdx, 7
0x18004bc36  jbe     short loc_18004BC72
0x18004bc38  mov     rax, [rsp+0D8h+Src]
0x18004bc3d  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x18004bc45  cmp     rdx, 1000h
0x18004bc4c  jb      short loc_18004BC69
0x18004bc4e  mov     rcx, [rax-8]
0x18004bc52  sub     rax, rcx
0x18004bc55  sub     rax, 8
0x18004bc59  cmp     rax, 1Fh
0x18004bc5d  ja      loc_18004BE18
0x18004bc63  add     rdx, 27h ; '''
0x18004bc67  jmp     short loc_18004BC6C
0x18004bc69  mov     rcx, rax; void *
0x18004bc6c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004bc71  nop
0x18004bc72  mov     rdi, [rsi+8]
0x18004bc76  test    rdi, rdi
0x18004bc79  jz      loc_18004BE29
0x18004bc7f  mov     ebx, 0FFFFFFFFh
0x18004bc84  mov     eax, ebx
0x18004bc86  lock xadd [rdi+8], eax
0x18004bc8b  cmp     eax, 1
0x18004bc8e  jnz     loc_18004BE29
0x18004bc94  mov     rax, [rdi]
0x18004bc97  mov     rcx, rdi
0x18004bc9a  mov     rax, [rax]
0x18004bc9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bca2  lock xadd [rdi+0Ch], ebx
0x18004bca7  cmp     ebx, 1
0x18004bcaa  jnz     loc_18004BE29
0x18004bcb0  mov     rax, [rdi]
0x18004bcb3  mov     rcx, rdi
0x18004bcb6  mov     rax, [rax+8]
0x18004bcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcbf  jmp     loc_18004BE29
0x18004bcc4  mov     rax, [rdi]
0x18004bcc7  sub     [rax+90h], r8
0x18004bcce  mov     rax, [rdi]
0x18004bcd1  cmp     qword ptr [rax+90h], 0
0x18004bcd9  jnz     short loc_18004BCE5
0x18004bcdb  mov     dword ptr [rax+88h], 0
0x18004bce5  mov     rcx, [rdi]
0x18004bce8  mov     rdx, [rcx+0D8h]
0x18004bcef  test    rdx, rdx
0x18004bcf2  jnz     short loc_18004BCFB
0x18004bcf4  mov     rdx, [rcx+0E0h]; lpBuffer
0x18004bcfb  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x18004bcfe  mov     rcx, [rcx+68h]; hRequest
0x18004bd02  call    cs:__imp_WinHttpWriteData
0x18004bd08  test    eax, eax
0x18004bd0a  jnz     loc_18004BC72
0x18004bd10  call    cs:__imp_GetLastError
0x18004bd16  mov     ebx, eax
0x18004bd18  xorps   xmm0, xmm0
0x18004bd1b  movups  [rsp+0D8h+var_A8], xmm0
0x18004bd20  mov     [rsp+0D8h+var_98], 0
0x18004bd29  mov     [rsp+0D8h+var_90], 0
0x18004bd32  mov     ecx, 20h ; ' '; Size
0x18004bd37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004bd3c  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18004bd41  mov     [rsp+0D8h+var_98], 10h
0x18004bd4a  mov     [rsp+0D8h+var_90], 1Fh
0x18004bd53  movups  xmm0, xmmword ptr cs:aWinhttpwriteda_0; "WinHttpWriteData"
0x18004bd5a  movups  xmmword ptr [rax], xmm0
0x18004bd5d  mov     byte ptr [rax+10h], 0
0x18004bd61  lea     r8, [rsp+0D8h+var_A8]
0x18004bd66  mov     edx, ebx
0x18004bd68  lea     rcx, [rsp+0D8h+Src]; Src
0x18004bd6d  call    web__http__client__details__build_error_msg
0x18004bd72  nop
0x18004bd73  mov     r8, rax
0x18004bd76  mov     edx, ebx
0x18004bd78  mov     rcx, [rdi]
0x18004bd7b  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18004bd80  nop
0x18004bd81  mov     rdx, [rsp+0D8h+var_70]
0x18004bd86  cmp     rdx, 0Fh
0x18004bd8a  jbe     short loc_18004BDC3
0x18004bd8c  mov     rax, [rsp+0D8h+Src]
0x18004bd91  inc     rdx; struct std::nothrow_t *
0x18004bd94  cmp     rdx, 1000h
0x18004bd9b  jb      short loc_18004BDBB
0x18004bd9d  mov     rcx, [rax-8]
0x18004bda1  sub     rax, rcx
0x18004bda4  sub     rax, 8
0x18004bda8  cmp     rax, 1Fh
0x18004bdac  ja      short loc_18004BDB4
0x18004bdae  add     rdx, 27h ; '''
0x18004bdb2  jmp     short loc_18004BDBE
0x18004bdb4  mov     ecx, 5
0x18004bdb9  int     29h; Win8: RtlFailFast(ecx)
0x18004bdbb  mov     rcx, rax; void *
0x18004bdbe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004bdc3  mov     [rsp+0D8h+var_78], 0
0x18004bdcc  mov     [rsp+0D8h+var_70], 0Fh
0x18004bdd5  mov     byte ptr [rsp+0D8h+Src], 0
0x18004bdda  mov     rdx, [rsp+0D8h+var_90]
0x18004bddf  cmp     rdx, 0Fh
0x18004bde3  jbe     loc_18004BC72
0x18004bde9  mov     rax, qword ptr [rsp+0D8h+var_A8]
0x18004bdee  inc     rdx
0x18004bdf1  cmp     rdx, 1000h
0x18004bdf8  jb      loc_18004BC69
0x18004bdfe  mov     rcx, [rax-8]
0x18004be02  sub     rax, rcx
0x18004be05  sub     rax, 8
0x18004be09  cmp     rax, 1Fh
0x18004be0d  ja      short loc_18004BE18
0x18004be0f  add     rdx, 27h ; '''
0x18004be13  jmp     loc_18004BC6C
0x18004be18  mov     ecx, 5
0x18004be1d  int     29h; Win8: RtlFailFast(ecx)
0x18004be1f  mov     rcx, [rsp+0D8h+var_B0]; void *
0x18004be24  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18004be29  mov     rcx, [rsp+0D8h+var_18]
0x18004be31  xor     rcx, rsp; StackCookie
0x18004be34  call    __security_check_cookie
0x18004be39  lea     r11, [rsp+0D8h+var_8]
0x18004be41  mov     rbx, [r11+20h]
0x18004be45  mov     rsi, [r11+28h]
0x18004be49  mov     rsp, r11
0x18004be4c  pop     rdi
0x18004be4d  retn
```

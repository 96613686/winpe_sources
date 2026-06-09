# `web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_::operator()(pplx::task<unsigned __int64>)

- ea: `0x1800d4bf0`
- end: `0x1800d4ede`
- name: `??R_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@3456@@Z@QEBA@V?$task@_K@pplx@@@Z`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x1800d69b0`

## callees

- `0x180019080`
- `0x1800190a4`
- `0x180019588`
- `0x180019ede`
- `0x1800224c0`
- `0x180048c30`
- `0x180065e80`
- `0x1800baeb0`
- `0x1800be5f0`
- `0x1800d4bf0`
- `0x1800d7b70`
- `0x1800e68b0`
- `0x1800e7b88`
- `0x180193010`

## import_xrefs

- `WINHTTP!WinHttpWriteData` at `0x1800d4d92`
- `WINHTTP!WinHttpWriteData` at `0x1800d4d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4da0`

## string_xrefs

- `0x1800d4de3`: `WinHttpWriteData`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall `web::http::client::details::winhttp_client::_multiple_segment_write_data'::`21'::_lambda_1_::operator()(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v4; // rax
  void *v5; // rax
  void *v6; // rcx
  volatile signed __int32 *v7; // rdi
  __int64 v8; // rcx
  const void *v9; // rdx
  DWORD LastError; // ebx
  __int64 v11; // r8
  void *v12; // rcx
  __int64 v13; // rax
  __int128 v16; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-98h]
  __int64 v18; // [rsp+48h] [rbp-90h]
  void *Block[3]; // [rsp+50h] [rbp-88h] BYREF
  unsigned __int64 v20; // [rsp+68h] [rbp-70h]
  void **v21; // [rsp+70h] [rbp-68h] BYREF
  __int128 v22; // [rsp+78h] [rbp-60h] BYREF
  int v23; // [rsp+88h] [rbp-50h]
  void ***v24; // [rsp+90h] [rbp-48h]
  _BYTE v25[40]; // [rsp+98h] [rbp-40h] BYREF

  try
  {
    v4 = pplx::task<unsigned __int64>::get(a2);
  }
  catch ( ... )
  {
    v13 = std::current_exception(&v16);
    web::http::client::details::request_context::report_exception(*a1, v13);
    pplx::task<long>::~task<long>(a2);
    return;
  }
  if ( v4 )
  {
    *(_QWORD *)(*a1 + 144LL) -= v4;
    if ( !*(_QWORD *)(*a1 + 144LL) )
      *(_DWORD *)(*a1 + 136LL) = 0;
    v8 = *a1;
    v9 = *(const void **)(*a1 + 216LL);
    if ( !v9 )
      v9 = *(const void **)(v8 + 224);
    if ( WinHttpWriteData(*(HINTERNET *)(v8 + 104), v9, v4, 0) )
      goto LABEL_9;
    LastError = GetLastError();
    v16 = 0;
    *(_QWORD *)&v16 = operator new(0x20u);
    v17 = 16;
    v18 = 31;
    strcpy((char *)v16, "WinHttpWriteData");
    v11 = web::http::client::details::build_error_msg(Block);
    web::http::client::details::request_context::report_error(*a1, LastError, v11);
    if ( v20 > 0xF )
    {
      if ( v20 + 1 < 0x1000 )
      {
        v12 = Block[0];
      }
      else
      {
        v12 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v12 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v12);
    }
    Block[2] = 0;
    v20 = 15;
    LOBYTE(Block[0]) = 0;
    v5 = (void *)v16;
    if ( (unsigned __int64)(v18 + 1) >= 0x1000 )
    {
      v6 = *(void **)(v16 - 8);
      if ( (unsigned __int64)(v16 - (_QWORD)v6 - 8) > 0x1F )
        goto LABEL_26;
LABEL_8:
      operator delete(v6);
      goto LABEL_9;
    }
LABEL_7:
    v6 = v5;
    goto LABEL_8;
  }
  std::wstring::wstring(Block, L"Unexpected end of request body stream encountered before Content-Length met.");
  v22 = 0;
  v21 = &web::http::http_exception::`vftable';
  v23 = 0;
  v24 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  utility::conversions::to_utf8string(v25, Block);
  web::http::client::details::request_context::report_exception<web::http::http_exception>(*a1, &v21);
  std::string::~string(v25);
  v21 = &std::exception::`vftable';
  o___std_exception_destroy_0(&v22);
  if ( v20 > 7 )
  {
    v5 = Block[0];
    if ( 2 * v20 + 2 >= 0x1000 )
    {
      v6 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v6 - 8) <= 0x1F )
        goto LABEL_8;
LABEL_26:
      __fastfail(5u);
    }
    goto LABEL_7;
  }
LABEL_9:
  v7 = *(volatile signed __int32 **)(a2 + 8);
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
}

```

## disassembly

```asm
0x1800d4bf0  mov     [rsp+arg_10], rbx
0x1800d4bf5  mov     [rsp+arg_18], rsi
0x1800d4bfa  push    rdi
0x1800d4bfb  sub     rsp, 0D0h
0x1800d4c02  mov     rax, cs:__security_cookie
0x1800d4c09  xor     rax, rsp
0x1800d4c0c  mov     [rsp+0D8h+var_18], rax
0x1800d4c14  mov     rsi, rdx
0x1800d4c17  mov     rdi, rcx
0x1800d4c1a  mov     [rsp+0D8h+var_B8], rcx
0x1800d4c1f  mov     [rsp+0D8h+var_B0], rdx
0x1800d4c24  mov     rcx, rdx
0x1800d4c27  call    ?get@?$task@_K@pplx@@QEBA_KXZ; pplx::task<unsigned __int64>::get(void)
0x1800d4c2c  mov     r8, rax; dwNumberOfBytesToWrite
0x1800d4c2f  test    r8, r8
0x1800d4c32  jnz     loc_1800D4D54
0x1800d4c38  lea     rdx, aUnexpectedEndO_0; "Unexpected end of request body stream e"...
0x1800d4c3f  lea     rcx, [rsp+0D8h+Block]
0x1800d4c44  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d4c49  nop
0x1800d4c4a  xorps   xmm0, xmm0
0x1800d4c4d  movups  [rsp+0D8h+var_60], xmm0
0x1800d4c52  lea     rax, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x1800d4c59  mov     [rsp+0D8h+var_68], rax
0x1800d4c5e  mov     [rsp+0D8h+var_50], 0
0x1800d4c69  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1800d4c70  mov     [rsp+0D8h+var_48], rax
0x1800d4c78  lea     rdx, [rsp+0D8h+Block]
0x1800d4c7d  lea     rcx, [rsp+0D8h+var_40]
0x1800d4c85  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x1800d4c8a  nop
0x1800d4c8b  lea     rdx, [rsp+0D8h+var_68]
0x1800d4c90  mov     rcx, [rdi]
0x1800d4c93  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x1800d4c98  nop
0x1800d4c99  lea     rcx, [rsp+0D8h+var_40]
0x1800d4ca1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800d4ca6  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800d4cad  mov     [rsp+0D8h+var_68], rax
0x1800d4cb2  lea     rcx, [rsp+0D8h+var_60]
0x1800d4cb7  call    _o___std_exception_destroy_0
0x1800d4cbc  nop
0x1800d4cbd  mov     rdx, [rsp+0D8h+var_70]
0x1800d4cc2  cmp     rdx, 7
0x1800d4cc6  jbe     short loc_1800D4D02
0x1800d4cc8  mov     rax, [rsp+0D8h+Block]
0x1800d4ccd  lea     rdx, ds:2[rdx*2]
0x1800d4cd5  cmp     rdx, 1000h
0x1800d4cdc  jb      short loc_1800D4CF9
0x1800d4cde  mov     rcx, [rax-8]
0x1800d4ce2  sub     rax, rcx
0x1800d4ce5  sub     rax, 8
0x1800d4ce9  cmp     rax, 1Fh
0x1800d4ced  ja      loc_1800D4EA8
0x1800d4cf3  add     rdx, 27h ; '''
0x1800d4cf7  jmp     short loc_1800D4CFC
0x1800d4cf9  mov     rcx, rax; Block
0x1800d4cfc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d4d01  nop
0x1800d4d02  mov     rdi, [rsi+8]
0x1800d4d06  test    rdi, rdi
0x1800d4d09  jz      loc_1800D4EB9
0x1800d4d0f  mov     ebx, 0FFFFFFFFh
0x1800d4d14  mov     eax, ebx
0x1800d4d16  lock xadd [rdi+8], eax
0x1800d4d1b  cmp     eax, 1
0x1800d4d1e  jnz     loc_1800D4EB9
0x1800d4d24  mov     rax, [rdi]
0x1800d4d27  mov     rcx, rdi
0x1800d4d2a  mov     rax, [rax]
0x1800d4d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4d32  lock xadd [rdi+0Ch], ebx
0x1800d4d37  cmp     ebx, 1
0x1800d4d3a  jnz     loc_1800D4EB9
0x1800d4d40  mov     rax, [rdi]
0x1800d4d43  mov     rcx, rdi
0x1800d4d46  mov     rax, [rax+8]
0x1800d4d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4d4f  jmp     loc_1800D4EB9
0x1800d4d54  mov     rax, [rdi]
0x1800d4d57  sub     [rax+90h], r8
0x1800d4d5e  mov     rax, [rdi]
0x1800d4d61  cmp     qword ptr [rax+90h], 0
0x1800d4d69  jnz     short loc_1800D4D75
0x1800d4d6b  mov     dword ptr [rax+88h], 0
0x1800d4d75  mov     rcx, [rdi]
0x1800d4d78  mov     rdx, [rcx+0D8h]
0x1800d4d7f  test    rdx, rdx
0x1800d4d82  jnz     short loc_1800D4D8B
0x1800d4d84  mov     rdx, [rcx+0E0h]; lpBuffer
0x1800d4d8b  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x1800d4d8e  mov     rcx, [rcx+68h]; hRequest
0x1800d4d92  call    cs:__imp_WinHttpWriteData
0x1800d4d98  test    eax, eax
0x1800d4d9a  jnz     loc_1800D4D02
0x1800d4da0  call    cs:__imp_GetLastError
0x1800d4da6  mov     ebx, eax
0x1800d4da8  xorps   xmm0, xmm0
0x1800d4dab  movups  [rsp+0D8h+var_A8], xmm0
0x1800d4db0  mov     [rsp+0D8h+var_98], 0
0x1800d4db9  mov     [rsp+0D8h+var_90], 0
0x1800d4dc2  mov     ecx, 20h ; ' '; Size
0x1800d4dc7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d4dcc  mov     qword ptr [rsp+0D8h+var_A8], rax
0x1800d4dd1  mov     [rsp+0D8h+var_98], 10h
0x1800d4dda  mov     [rsp+0D8h+var_90], 1Fh
0x1800d4de3  movups  xmm0, xmmword ptr cs:aWinhttpwriteda; "WinHttpWriteData"
0x1800d4dea  movups  xmmword ptr [rax], xmm0
0x1800d4ded  mov     byte ptr [rax+10h], 0
0x1800d4df1  lea     r8, [rsp+0D8h+var_A8]
0x1800d4df6  mov     edx, ebx
0x1800d4df8  lea     rcx, [rsp+0D8h+Block]; Src
0x1800d4dfd  call    web__http__client__details__build_error_msg
0x1800d4e02  nop
0x1800d4e03  mov     r8, rax
0x1800d4e06  mov     edx, ebx
0x1800d4e08  mov     rcx, [rdi]
0x1800d4e0b  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800d4e10  nop
0x1800d4e11  mov     rdx, [rsp+0D8h+var_70]
0x1800d4e16  cmp     rdx, 0Fh
0x1800d4e1a  jbe     short loc_1800D4E53
0x1800d4e1c  mov     rax, [rsp+0D8h+Block]
0x1800d4e21  inc     rdx
0x1800d4e24  cmp     rdx, 1000h
0x1800d4e2b  jb      short loc_1800D4E4B
0x1800d4e2d  mov     rcx, [rax-8]
0x1800d4e31  sub     rax, rcx
0x1800d4e34  sub     rax, 8
0x1800d4e38  cmp     rax, 1Fh
0x1800d4e3c  ja      short loc_1800D4E44
0x1800d4e3e  add     rdx, 27h ; '''
0x1800d4e42  jmp     short loc_1800D4E4E
0x1800d4e44  mov     ecx, 5
0x1800d4e49  int     29h; Win8: RtlFailFast(ecx)
0x1800d4e4b  mov     rcx, rax; Block
0x1800d4e4e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d4e53  mov     [rsp+0D8h+var_78], 0
0x1800d4e5c  mov     [rsp+0D8h+var_70], 0Fh
0x1800d4e65  mov     byte ptr [rsp+0D8h+Block], 0
0x1800d4e6a  mov     rdx, [rsp+0D8h+var_90]
0x1800d4e6f  cmp     rdx, 0Fh
0x1800d4e73  jbe     loc_1800D4D02
0x1800d4e79  mov     rax, qword ptr [rsp+0D8h+var_A8]
0x1800d4e7e  inc     rdx
0x1800d4e81  cmp     rdx, 1000h
0x1800d4e88  jb      loc_1800D4CF9
0x1800d4e8e  mov     rcx, [rax-8]
0x1800d4e92  sub     rax, rcx
0x1800d4e95  sub     rax, 8
0x1800d4e99  cmp     rax, 1Fh
0x1800d4e9d  ja      short loc_1800D4EA8
0x1800d4e9f  add     rdx, 27h ; '''
0x1800d4ea3  jmp     loc_1800D4CFC
0x1800d4ea8  mov     ecx, 5
0x1800d4ead  int     29h; Win8: RtlFailFast(ecx)
0x1800d4eaf  mov     rcx, [rsp+0D8h+var_B0]
0x1800d4eb4  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x1800d4eb9  mov     rcx, [rsp+0D8h+var_18]
0x1800d4ec1  xor     rcx, rsp; StackCookie
0x1800d4ec4  call    __security_check_cookie
0x1800d4ec9  lea     r11, [rsp+0D8h+var_8]
0x1800d4ed1  mov     rbx, [r11+20h]
0x1800d4ed5  mov     rsi, [r11+28h]
0x1800d4ed9  mov     rsp, r11
0x1800d4edc  pop     rdi
0x1800d4edd  retn
```

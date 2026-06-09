# `web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_::operator()(pplx::task<unsigned __int64>)

- ea: `0x1800d4a50`
- end: `0x1800d4d3e`
- name: `??R_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@3456@@Z@QEBA@V?$task@_K@pplx@@@Z`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x1800d6810`

## callees

- `0x180019000`
- `0x180019024`
- `0x180019508`
- `0x180019e4e`
- `0x1800223e0`
- `0x180048b10`
- `0x180065d10`
- `0x1800bad10`
- `0x1800be450`
- `0x1800d4a50`
- `0x1800d79d0`
- `0x1800e66dc`
- `0x1800e79d4`
- `0x180191010`

## import_xrefs

- `WINHTTP!WinHttpWriteData` at `0x1800d4bf2`
- `WINHTTP!WinHttpWriteData` at `0x1800d4bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4c00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4c00`

## string_xrefs

- `0x1800d4c43`: `WinHttpWriteData`

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
0x1800d4a50  mov     [rsp+arg_10], rbx
0x1800d4a55  mov     [rsp+arg_18], rsi
0x1800d4a5a  push    rdi
0x1800d4a5b  sub     rsp, 0D0h
0x1800d4a62  mov     rax, cs:__security_cookie
0x1800d4a69  xor     rax, rsp
0x1800d4a6c  mov     [rsp+0D8h+var_18], rax
0x1800d4a74  mov     rsi, rdx
0x1800d4a77  mov     rdi, rcx
0x1800d4a7a  mov     [rsp+0D8h+var_B8], rcx
0x1800d4a7f  mov     [rsp+0D8h+var_B0], rdx
0x1800d4a84  mov     rcx, rdx
0x1800d4a87  call    ?get@?$task@_K@pplx@@QEBA_KXZ; pplx::task<unsigned __int64>::get(void)
0x1800d4a8c  mov     r8, rax; dwNumberOfBytesToWrite
0x1800d4a8f  test    r8, r8
0x1800d4a92  jnz     loc_1800D4BB4
0x1800d4a98  lea     rdx, aUnexpectedEndO_0; "Unexpected end of request body stream e"...
0x1800d4a9f  lea     rcx, [rsp+0D8h+Block]
0x1800d4aa4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d4aa9  nop
0x1800d4aaa  xorps   xmm0, xmm0
0x1800d4aad  movups  [rsp+0D8h+var_60], xmm0
0x1800d4ab2  lea     rax, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x1800d4ab9  mov     [rsp+0D8h+var_68], rax
0x1800d4abe  mov     [rsp+0D8h+var_50], 0
0x1800d4ac9  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1800d4ad0  mov     [rsp+0D8h+var_48], rax
0x1800d4ad8  lea     rdx, [rsp+0D8h+Block]
0x1800d4add  lea     rcx, [rsp+0D8h+var_40]
0x1800d4ae5  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x1800d4aea  nop
0x1800d4aeb  lea     rdx, [rsp+0D8h+var_68]
0x1800d4af0  mov     rcx, [rdi]
0x1800d4af3  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x1800d4af8  nop
0x1800d4af9  lea     rcx, [rsp+0D8h+var_40]
0x1800d4b01  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800d4b06  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800d4b0d  mov     [rsp+0D8h+var_68], rax
0x1800d4b12  lea     rcx, [rsp+0D8h+var_60]
0x1800d4b17  call    _o___std_exception_destroy_0
0x1800d4b1c  nop
0x1800d4b1d  mov     rdx, [rsp+0D8h+var_70]
0x1800d4b22  cmp     rdx, 7
0x1800d4b26  jbe     short loc_1800D4B62
0x1800d4b28  mov     rax, [rsp+0D8h+Block]
0x1800d4b2d  lea     rdx, ds:2[rdx*2]
0x1800d4b35  cmp     rdx, 1000h
0x1800d4b3c  jb      short loc_1800D4B59
0x1800d4b3e  mov     rcx, [rax-8]
0x1800d4b42  sub     rax, rcx
0x1800d4b45  sub     rax, 8
0x1800d4b49  cmp     rax, 1Fh
0x1800d4b4d  ja      loc_1800D4D08
0x1800d4b53  add     rdx, 27h ; '''
0x1800d4b57  jmp     short loc_1800D4B5C
0x1800d4b59  mov     rcx, rax; Block
0x1800d4b5c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d4b61  nop
0x1800d4b62  mov     rdi, [rsi+8]
0x1800d4b66  test    rdi, rdi
0x1800d4b69  jz      loc_1800D4D19
0x1800d4b6f  mov     ebx, 0FFFFFFFFh
0x1800d4b74  mov     eax, ebx
0x1800d4b76  lock xadd [rdi+8], eax
0x1800d4b7b  cmp     eax, 1
0x1800d4b7e  jnz     loc_1800D4D19
0x1800d4b84  mov     rax, [rdi]
0x1800d4b87  mov     rcx, rdi
0x1800d4b8a  mov     rax, [rax]
0x1800d4b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4b92  lock xadd [rdi+0Ch], ebx
0x1800d4b97  cmp     ebx, 1
0x1800d4b9a  jnz     loc_1800D4D19
0x1800d4ba0  mov     rax, [rdi]
0x1800d4ba3  mov     rcx, rdi
0x1800d4ba6  mov     rax, [rax+8]
0x1800d4baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4baf  jmp     loc_1800D4D19
0x1800d4bb4  mov     rax, [rdi]
0x1800d4bb7  sub     [rax+90h], r8
0x1800d4bbe  mov     rax, [rdi]
0x1800d4bc1  cmp     qword ptr [rax+90h], 0
0x1800d4bc9  jnz     short loc_1800D4BD5
0x1800d4bcb  mov     dword ptr [rax+88h], 0
0x1800d4bd5  mov     rcx, [rdi]
0x1800d4bd8  mov     rdx, [rcx+0D8h]
0x1800d4bdf  test    rdx, rdx
0x1800d4be2  jnz     short loc_1800D4BEB
0x1800d4be4  mov     rdx, [rcx+0E0h]; lpBuffer
0x1800d4beb  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x1800d4bee  mov     rcx, [rcx+68h]; hRequest
0x1800d4bf2  call    cs:__imp_WinHttpWriteData
0x1800d4bf8  test    eax, eax
0x1800d4bfa  jnz     loc_1800D4B62
0x1800d4c00  call    cs:__imp_GetLastError
0x1800d4c06  mov     ebx, eax
0x1800d4c08  xorps   xmm0, xmm0
0x1800d4c0b  movups  [rsp+0D8h+var_A8], xmm0
0x1800d4c10  mov     [rsp+0D8h+var_98], 0
0x1800d4c19  mov     [rsp+0D8h+var_90], 0
0x1800d4c22  mov     ecx, 20h ; ' '; Size
0x1800d4c27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d4c2c  mov     qword ptr [rsp+0D8h+var_A8], rax
0x1800d4c31  mov     [rsp+0D8h+var_98], 10h
0x1800d4c3a  mov     [rsp+0D8h+var_90], 1Fh
0x1800d4c43  movups  xmm0, xmmword ptr cs:aWinhttpwriteda; "WinHttpWriteData"
0x1800d4c4a  movups  xmmword ptr [rax], xmm0
0x1800d4c4d  mov     byte ptr [rax+10h], 0
0x1800d4c51  lea     r8, [rsp+0D8h+var_A8]
0x1800d4c56  mov     edx, ebx
0x1800d4c58  lea     rcx, [rsp+0D8h+Block]; Src
0x1800d4c5d  call    web__http__client__details__build_error_msg
0x1800d4c62  nop
0x1800d4c63  mov     r8, rax
0x1800d4c66  mov     edx, ebx
0x1800d4c68  mov     rcx, [rdi]
0x1800d4c6b  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800d4c70  nop
0x1800d4c71  mov     rdx, [rsp+0D8h+var_70]
0x1800d4c76  cmp     rdx, 0Fh
0x1800d4c7a  jbe     short loc_1800D4CB3
0x1800d4c7c  mov     rax, [rsp+0D8h+Block]
0x1800d4c81  inc     rdx
0x1800d4c84  cmp     rdx, 1000h
0x1800d4c8b  jb      short loc_1800D4CAB
0x1800d4c8d  mov     rcx, [rax-8]
0x1800d4c91  sub     rax, rcx
0x1800d4c94  sub     rax, 8
0x1800d4c98  cmp     rax, 1Fh
0x1800d4c9c  ja      short loc_1800D4CA4
0x1800d4c9e  add     rdx, 27h ; '''
0x1800d4ca2  jmp     short loc_1800D4CAE
0x1800d4ca4  mov     ecx, 5
0x1800d4ca9  int     29h; Win8: RtlFailFast(ecx)
0x1800d4cab  mov     rcx, rax; Block
0x1800d4cae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d4cb3  mov     [rsp+0D8h+var_78], 0
0x1800d4cbc  mov     [rsp+0D8h+var_70], 0Fh
0x1800d4cc5  mov     byte ptr [rsp+0D8h+Block], 0
0x1800d4cca  mov     rdx, [rsp+0D8h+var_90]
0x1800d4ccf  cmp     rdx, 0Fh
0x1800d4cd3  jbe     loc_1800D4B62
0x1800d4cd9  mov     rax, qword ptr [rsp+0D8h+var_A8]
0x1800d4cde  inc     rdx
0x1800d4ce1  cmp     rdx, 1000h
0x1800d4ce8  jb      loc_1800D4B59
0x1800d4cee  mov     rcx, [rax-8]
0x1800d4cf2  sub     rax, rcx
0x1800d4cf5  sub     rax, 8
0x1800d4cf9  cmp     rax, 1Fh
0x1800d4cfd  ja      short loc_1800D4D08
0x1800d4cff  add     rdx, 27h ; '''
0x1800d4d03  jmp     loc_1800D4B5C
0x1800d4d08  mov     ecx, 5
0x1800d4d0d  int     29h; Win8: RtlFailFast(ecx)
0x1800d4d0f  mov     rcx, [rsp+0D8h+var_B0]
0x1800d4d14  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x1800d4d19  mov     rcx, [rsp+0D8h+var_18]
0x1800d4d21  xor     rcx, rsp; StackCookie
0x1800d4d24  call    __security_check_cookie
0x1800d4d29  lea     r11, [rsp+0D8h+var_8]
0x1800d4d31  mov     rbx, [r11+20h]
0x1800d4d35  mov     rsi, [r11+28h]
0x1800d4d39  mov     rsp, r11
0x1800d4d3c  pop     rdi
0x1800d4d3d  retn
```

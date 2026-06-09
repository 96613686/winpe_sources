# `web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data(web::http::client::details::winhttp_request_context *)'::`2'::_lambda_1_::operator()(pplx::task<unsigned __int64>)

- ea: `0x18004b560`
- end: `0x18004bb58`
- name: `??R_lambda_1_@?1??_transfer_encoding_chunked_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@3456@@Z@QEBA@V?$task@_K@pplx@@@Z`
- size: `1528`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, service_task`

## callers

- `0x18004ddd0`
- `0x18004f290`

## callees

- `0x18000df90`
- `0x18000e430`
- `0x18000e46c`
- `0x18000eab2`
- `0x18000ec30`
- `0x1800198b0`
- `0x180032c30`
- `0x180035460`
- `0x180038ff0`
- `0x18003d200`
- `0x180049f40`
- `0x18004b560`
- `0x18004fbe0`
- `0x1800577a0`
- `0x180063668`
- `0x18006511c`
- `0x180065130`
- `0x1800a64d8`
- `0x1800a6b60`
- `0x1800a7ebc`
- `0x1800c175c`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b99c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b99c`
- `WINHTTP!WinHttpWriteData` at `0x18004b98e`
- `WINHTTP!WinHttpWriteData` at `0x18004b98e`

## string_xrefs

- `0x18004b9d9`: `WinHttpWriteData`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall `web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data'::`2'::_lambda_1_::operator()(
        void **a1,
        _QWORD *a2)
{
  unsigned __int64 v4; // r9
  __int64 v5; // r14
  _QWORD *v6; // rcx
  __int64 v7; // r10
  __int64 v8; // r8
  __int64 v9; // rax
  volatile signed __int32 *v10; // rbx
  web::http::details::chunked_encoding *v11; // rcx
  unsigned __int8 *v12; // rdx
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // r12
  __int64 v15; // rcx
  void *v16; // rcx
  __int64 v17; // r8
  _QWORD *v18; // r8
  __int64 v19; // rdx
  void *v20; // rcx
  void *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  const struct std::nothrow_t *v24; // rdx
  void *v25; // rcx
  void *v26; // rdx
  volatile signed __int32 *v27; // rcx
  volatile signed __int32 *v28; // rbx
  volatile signed __int32 *v29; // rbx
  void (__fastcall ***v30)(_QWORD, __int64); // rcx
  void *v31; // rcx
  __int64 v32; // rax
  DWORD LastError; // ebx
  __int64 v34; // r8
  const struct std::nothrow_t *v35; // rdx
  void *v36; // rcx
  const struct std::nothrow_t *v37; // rdx
  void *v38; // rcx
  volatile signed __int32 *v39; // rbx
  __int64 v40; // rax
  __int64 v41; // [rsp+30h] [rbp-138h] BYREF
  volatile signed __int32 *v42; // [rsp+38h] [rbp-130h]
  void **v43; // [rsp+48h] [rbp-120h]
  void *v44[2]; // [rsp+50h] [rbp-118h] BYREF
  __int64 v45; // [rsp+60h] [rbp-108h]
  void *v46; // [rsp+68h] [rbp-100h]
  void **v47; // [rsp+70h] [rbp-F8h] BYREF
  __int128 v48; // [rsp+78h] [rbp-F0h]
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-E0h] BYREF
  void *v50[2]; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-B8h]
  unsigned __int64 v52; // [rsp+B8h] [rbp-B0h]
  void *Src[2]; // [rsp+C0h] [rbp-A8h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-98h]
  unsigned __int64 v55; // [rsp+D8h] [rbp-90h]
  void **v56; // [rsp+E0h] [rbp-88h] BYREF
  __int128 v57; // [rsp+E8h] [rbp-80h] BYREF
  int v58; // [rsp+F8h] [rbp-70h]
  void ***v59; // [rsp+100h] [rbp-68h]
  _BYTE v60[40]; // [rsp+108h] [rbp-60h] BYREF

  v43 = a1;
  v46 = a2;
  try
  {
    v5 = pplx::task<unsigned __int64>::get();
    v6 = *a1;
    v7 = *((_QWORD *)*a1 + 24);
    if ( v7 && !*(_QWORD *)a1[2] )
    {
      v8 = v6[27];
      if ( !v8 )
        v8 = v6[28];
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, __int64))(*(_QWORD *)v7 + 112LL))(
             *((_QWORD *)*a1 + 24),
             &v41,
             v8 + 10,
             v5);
      pplx::task<unsigned __int64>::wait(v9);
      v10 = v42;
      if ( v42 )
      {
        if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
    }
    v11 = (web::http::details::chunked_encoding *)*((_QWORD *)*a1 + 27);
    if ( !v11 )
      v11 = (web::http::details::chunked_encoding *)*((_QWORD *)*a1 + 28);
    v12 = (unsigned __int8 *)a1[1] + 12;
    v13 = v5;
  }
  catch ( ... )
  {
    v40 = std::current_exception(&v41);
    web::http::client::details::request_context::report_exception(*v43, v40);
    v16 = v46;
    goto LABEL_63;
  }
  v14 = web::http::details::chunked_encoding::add_chunked_delimiters(v11, v12, v13, v4);
  if ( !*(_QWORD *)a1[2] )
  {
    v15 = *((_QWORD *)*a1 + 18);
    if ( v15 != -1 )
    {
      if ( !v5 && v15 )
      {
        std::wstring::wstring(v50, L"Unexpected end of request body stream encountered before expected length met.");
        v57 = 0;
        v56 = &web::http::http_exception::`vftable';
        v58 = 0;
        v59 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        utility::conversions::to_utf8string(v60, v50);
        std::destroy_at<std::pair<std::wstring const,_GUID>>(v50);
        web::http::client::details::request_context::report_exception<web::http::http_exception>(*a1, &v56);
        std::tuple<char const *,std::string>::~tuple<char const *,std::string>(v60);
        v56 = &std::exception::`vftable';
        o___std_exception_destroy_0(&v57);
        v16 = a2;
LABEL_63:
        pplx::task<long>::~task<long>(v16);
        return;
      }
      *((_QWORD *)*a1 + 18) = v15 - v5;
    }
  }
  if ( !v5 )
  {
    *((_DWORD *)*a1 + 34) = 0;
    v17 = *((_QWORD *)*a1 + 24);
    if ( v17 )
    {
      v18 = *(_QWORD **)(v17 + 8);
      if ( !v18 )
      {
        std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "Invalid streambuf object");
        throw (std::invalid_argument *)pExceptionObject;
      }
      v19 = v18[8];
      v18[8] = 0;
      v20 = (void *)v18[7];
      v18[7] = 0;
      v21 = (void *)v18[6];
      v18[6] = 0;
      v43 = v44;
      v45 = 0;
      v44[1] = 0;
      v44[0] = 0;
      Src[0] = v21;
      Src[1] = v20;
      v54 = v19;
      v22 = Concurrency::streams::container_buffer<std::vector<unsigned char>>::container_buffer<std::vector<unsigned char>>(
              v50,
              Src,
              1);
      v47 = &Concurrency::streams::streambuf<unsigned char>::`vftable';
      v48 = 0;
      v23 = *(_QWORD *)(v22 + 16);
      if ( v23 )
        _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
      v48 = *(_OWORD *)(v22 + 8);
      Concurrency::streams::basic_istream<unsigned char>::basic_istream<unsigned char>(&v41, &v47);
      Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v50);
      if ( v44[0] )
      {
        v24 = (const struct std::nothrow_t *)(v45 - (unsigned __int64)v44[0]);
        if ( v45 - (unsigned __int64)v44[0] < 0x1000 )
        {
          v25 = v44[0];
        }
        else
        {
          v25 = (void *)*((_QWORD *)v44[0] - 1);
          if ( (unsigned __int64)((char *)v44[0] - (char *)v25 - 8) > 0x1F )
            goto LABEL_56;
          v24 = (const struct std::nothrow_t *)((char *)v24 + 39);
        }
        operator delete(v25, v24);
        *(_OWORD *)v44 = 0;
        v45 = 0;
      }
      v26 = *a1;
      v27 = v42;
      if ( v42 )
      {
        _InterlockedIncrement(v42 + 2);
        v27 = v42;
      }
      *((_QWORD *)v26 + 22) = v41;
      v28 = (volatile signed __int32 *)*((_QWORD *)v26 + 23);
      *((_QWORD *)v26 + 23) = v27;
      if ( v28 )
      {
        if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
      v29 = v42;
      if ( v42 )
      {
        if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
          if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
        }
      }
      v30 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)*a1 + 24);
      *((_QWORD *)*a1 + 24) = 0;
      if ( v30 )
        (**v30)(v30, 1);
    }
  }
  v31 = *a1;
  v32 = *((_QWORD *)*a1 + 27);
  if ( !v32 )
    v32 = *((_QWORD *)v31 + 28);
  if ( WinHttpWriteData(*((HINTERNET *)v31 + 13), (LPCVOID)(v14 + v32), v5 - v14 + 12, 0) )
    goto LABEL_59;
  LastError = GetLastError();
  *(_OWORD *)v50 = 0;
  v50[0] = operator new(0x20u);
  v51 = 16;
  v52 = 31;
  strcpy((char *)v50[0], "WinHttpWriteData");
  v34 = web::http::client::details::build_error_msg(Src);
  web::http::client::details::request_context::report_error(*a1, LastError, v34);
  if ( v55 > 0xF )
  {
    v35 = (const struct std::nothrow_t *)(v55 + 1);
    if ( v55 + 1 < 0x1000 )
    {
      v36 = Src[0];
    }
    else
    {
      v36 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v36 - 8) > 0x1F )
        __fastfail(5u);
      v35 = (const struct std::nothrow_t *)(v55 + 40);
    }
    operator delete(v36, v35);
  }
  v54 = 0;
  v55 = 15;
  LOBYTE(Src[0]) = 0;
  if ( v52 <= 0xF )
    goto LABEL_59;
  v37 = (const struct std::nothrow_t *)(v52 + 1);
  if ( v52 + 1 < 0x1000 )
  {
    v38 = v50[0];
    goto LABEL_58;
  }
  v38 = (void *)*((_QWORD *)v50[0] - 1);
  if ( (unsigned __int64)((char *)v50[0] - (char *)v38 - 8) > 0x1F )
LABEL_56:
    __fastfail(5u);
  v37 = (const struct std::nothrow_t *)(v52 + 40);
LABEL_58:
  operator delete(v38, v37);
LABEL_59:
  v39 = (volatile signed __int32 *)a2[1];
  if ( v39 )
  {
    if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
      if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
    }
  }
}

```

## disassembly

```asm
0x18004b560  mov     [rsp+arg_10], rbx
0x18004b565  mov     [rsp+arg_18], rsi
0x18004b56a  push    rdi
0x18004b56b  push    r12
0x18004b56d  push    r13
0x18004b56f  push    r14
0x18004b571  push    r15
0x18004b573  sub     rsp, 140h
0x18004b57a  mov     rax, cs:__security_cookie
0x18004b581  xor     rax, rsp
0x18004b584  mov     [rsp+168h+var_38], rax
0x18004b58c  mov     r15, rdx
0x18004b58f  mov     rdi, rcx
0x18004b592  mov     [rsp+168h+var_120], rcx
0x18004b597  mov     [rsp+168h+var_100], rdx
0x18004b59c  xor     r13d, r13d
0x18004b59f  mov     rcx, rdx
0x18004b5a2  call    ?get@?$task@_K@pplx@@QEBA_KXZ; pplx::task<unsigned __int64>::get(void)
0x18004b5a7  mov     r14, rax
0x18004b5aa  mov     rcx, [rdi]
0x18004b5ad  mov     r10, [rcx+0C0h]
0x18004b5b4  test    r10, r10
0x18004b5b7  jz      loc_18004B644
0x18004b5bd  mov     rax, [rdi+10h]
0x18004b5c1  cmp     [rax], r13
0x18004b5c4  jnz     short loc_18004B644
0x18004b5c6  mov     r8, [rcx+0D8h]
0x18004b5cd  test    r8, r8
0x18004b5d0  jnz     short loc_18004B5D9
0x18004b5d2  mov     r8, [rcx+0E0h]
0x18004b5d9  mov     rax, [r10]
0x18004b5dc  add     r8, 0Ah
0x18004b5e0  mov     r9, r14
0x18004b5e3  lea     rdx, [rsp+168h+var_138]
0x18004b5e8  mov     rcx, r10
0x18004b5eb  mov     rax, [rax+70h]
0x18004b5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b5f4  nop
0x18004b5f5  mov     rcx, rax
0x18004b5f8  call    ?wait@?$task@_K@pplx@@QEBA?AW4task_group_status@2@XZ; pplx::task<unsigned __int64>::wait(void)
0x18004b5fd  nop
0x18004b5fe  mov     rbx, [rsp+168h+var_130]
0x18004b603  test    rbx, rbx
0x18004b606  jz      short loc_18004B644
0x18004b608  mov     esi, 0FFFFFFFFh
0x18004b60d  mov     eax, esi
0x18004b60f  lock xadd [rbx+8], eax
0x18004b614  cmp     eax, 1
0x18004b617  jnz     short loc_18004B649
0x18004b619  mov     rax, [rbx]
0x18004b61c  mov     rcx, rbx
0x18004b61f  mov     rax, [rax]
0x18004b622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b627  mov     eax, esi
0x18004b629  lock xadd [rbx+0Ch], eax
0x18004b62e  cmp     eax, 1
0x18004b631  jnz     short loc_18004B649
0x18004b633  mov     rax, [rbx]
0x18004b636  mov     rcx, rbx
0x18004b639  mov     rax, [rax+8]
0x18004b63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b642  jmp     short loc_18004B649
0x18004b644  mov     esi, 0FFFFFFFFh
0x18004b649  mov     rax, [rdi]
0x18004b64c  mov     rcx, [rax+0D8h]
0x18004b653  test    rcx, rcx
0x18004b656  jnz     short loc_18004B65F
0x18004b658  mov     rcx, [rax+0E0h]; this
0x18004b65f  mov     rdx, [rdi+8]
0x18004b663  add     rdx, 0Ch; unsigned __int8 *
0x18004b667  mov     r8, r14; unsigned __int64
0x18004b66a  call    ?add_chunked_delimiters@chunked_encoding@details@http@web@@YA_KPEAE_K1@Z; web::http::details::chunked_encoding::add_chunked_delimiters(uchar *,unsigned __int64,unsigned __int64)
0x18004b66f  mov     r12, rax
0x18004b672  mov     rcx, [rdi+10h]
0x18004b676  cmp     qword ptr [rcx], 0
0x18004b67a  jnz     loc_18004B75C
0x18004b680  mov     rdx, [rdi]
0x18004b683  mov     rcx, [rdx+90h]
0x18004b68a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004b68e  jz      loc_18004B75C
0x18004b694  test    r14, r14
0x18004b697  jnz     loc_18004B752
0x18004b69d  test    rcx, rcx
0x18004b6a0  jz      loc_18004B752
0x18004b6a6  lea     rdx, aUnexpectedEndO; "Unexpected end of request body stream e"...
0x18004b6ad  lea     rcx, [rsp+168h+var_C8]
0x18004b6b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004b6ba  nop
0x18004b6bb  xorps   xmm0, xmm0
0x18004b6be  movups  [rsp+168h+var_80], xmm0
0x18004b6c6  lea     rax, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x18004b6cd  mov     [rsp+168h+var_88], rax
0x18004b6d5  mov     [rsp+168h+var_70], r13d
0x18004b6dd  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18004b6e4  mov     [rsp+168h+var_68], rax
0x18004b6ec  lea     rdx, [rsp+168h+var_C8]
0x18004b6f4  lea     rcx, [rsp+168h+var_60]
0x18004b6fc  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x18004b701  nop
0x18004b702  lea     rcx, [rsp+168h+var_C8]; void *
0x18004b70a  call    ??$destroy_at@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@std@@YAXQEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@0@@Z; std::destroy_at<std::pair<std::wstring const,_GUID>>(std::pair<std::wstring const,_GUID> * const)
0x18004b70f  lea     rdx, [rsp+168h+var_88]
0x18004b717  mov     rcx, [rdi]
0x18004b71a  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x18004b71f  nop
0x18004b720  lea     rcx, [rsp+168h+var_60]
0x18004b728  call    ??1?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@XZ; std::tuple<char const *,std::string>::~tuple<char const *,std::string>(void)
0x18004b72d  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18004b734  mov     [rsp+168h+var_88], rax
0x18004b73c  lea     rcx, [rsp+168h+var_80]
0x18004b744  call    _o___std_exception_destroy_0
0x18004b749  nop
0x18004b74a  mov     rcx, r15
0x18004b74d  jmp     loc_18004BAFD
0x18004b752  sub     rcx, r14
0x18004b755  mov     [rdx+90h], rcx
0x18004b75c  test    r14, r14
0x18004b75f  jnz     loc_18004B966
0x18004b765  mov     rax, [rdi]
0x18004b768  mov     [rax+88h], r13d
0x18004b76f  mov     rax, [rdi]
0x18004b772  mov     r8, [rax+0C0h]
0x18004b779  test    r8, r8
0x18004b77c  jz      loc_18004B966
0x18004b782  mov     r8, [r8+8]
0x18004b786  test    r8, r8
0x18004b789  jz      loc_18004BB2F
0x18004b78f  mov     rdx, [r8+40h]
0x18004b793  mov     [r8+40h], r13
0x18004b797  mov     rcx, [r8+38h]
0x18004b79b  mov     [r8+38h], r13
0x18004b79f  mov     rax, [r8+30h]
0x18004b7a3  mov     [r8+30h], r13
0x18004b7a7  lea     r8, [rsp+168h+var_118]
0x18004b7ac  mov     [rsp+168h+var_120], r8
0x18004b7b1  mov     [rsp+168h+var_108], r13
0x18004b7b6  mov     [rsp+168h+var_118+8], r13
0x18004b7bb  mov     [rsp+168h+var_118], r13
0x18004b7c0  mov     [rsp+168h+Src], rax
0x18004b7c8  mov     [rsp+168h+var_A0], rcx
0x18004b7d0  mov     [rsp+168h+var_98], rdx
0x18004b7d8  mov     r8d, 1
0x18004b7de  lea     rdx, [rsp+168h+Src]
0x18004b7e6  lea     rcx, [rsp+168h+var_C8]
0x18004b7ee  call    ??0?$container_buffer@V?$vector@EV?$allocator@E@std@@@std@@@streams@Concurrency@@QEAA@V?$vector@EV?$allocator@E@std@@@std@@H@Z; Concurrency::streams::container_buffer<std::vector<uchar>>::container_buffer<std::vector<uchar>>(std::vector<uchar>,int)
0x18004b7f3  mov     rdx, rax
0x18004b7f6  lea     rax, ??_7?$streambuf@E@streams@Concurrency@@6B@; const Concurrency::streams::streambuf<uchar>::`vftable'
0x18004b7fd  mov     [rsp+168h+var_F8], rax
0x18004b802  xorps   xmm0, xmm0
0x18004b805  movdqu  [rsp+168h+var_F0], xmm0
0x18004b80b  mov     rcx, [rdx+10h]
0x18004b80f  test    rcx, rcx
0x18004b812  jz      short loc_18004B818
0x18004b814  lock inc dword ptr [rcx+8]
0x18004b818  mov     rax, [rdx+8]
0x18004b81c  mov     qword ptr [rsp+168h+var_F0], rax
0x18004b821  mov     rax, [rdx+10h]
0x18004b825  mov     qword ptr [rsp+168h+var_F0+8], rax
0x18004b82d  lea     rdx, [rsp+168h+var_F8]
0x18004b832  lea     rcx, [rsp+168h+var_138]
0x18004b837  call    ??$?0E@?$basic_istream@E@streams@Concurrency@@QEAA@V?$streambuf@E@12@@Z; Concurrency::streams::basic_istream<uchar>::basic_istream<uchar>(Concurrency::streams::streambuf<uchar>)
0x18004b83c  nop
0x18004b83d  lea     rcx, [rsp+168h+var_C8]
0x18004b845  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x18004b84a  nop
0x18004b84b  mov     rax, [rsp+168h+var_118]
0x18004b850  test    rax, rax
0x18004b853  jz      short loc_18004B897
0x18004b855  mov     rdx, [rsp+168h+var_108]
0x18004b85a  sub     rdx, rax; struct std::nothrow_t *
0x18004b85d  cmp     rdx, 1000h
0x18004b864  jb      short loc_18004B881
0x18004b866  mov     rcx, [rax-8]
0x18004b86a  sub     rax, rcx
0x18004b86d  sub     rax, 8
0x18004b871  cmp     rax, 1Fh
0x18004b875  ja      loc_18004BAAA
0x18004b87b  add     rdx, 27h ; '''
0x18004b87f  jmp     short loc_18004B884
0x18004b881  mov     rcx, rax; void *
0x18004b884  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004b889  xorps   xmm0, xmm0
0x18004b88c  movdqu  xmmword ptr [rsp+168h+var_118], xmm0
0x18004b892  mov     [rsp+168h+var_108], r13
0x18004b897  mov     rdx, [rdi]
0x18004b89a  mov     rcx, [rsp+168h+var_130]
0x18004b89f  test    rcx, rcx
0x18004b8a2  jz      short loc_18004B8AD
0x18004b8a4  lock inc dword ptr [rcx+8]
0x18004b8a8  mov     rcx, [rsp+168h+var_130]
0x18004b8ad  mov     rax, [rsp+168h+var_138]
0x18004b8b2  mov     [rdx+0B0h], rax
0x18004b8b9  mov     rbx, [rdx+0B8h]
0x18004b8c0  mov     [rdx+0B8h], rcx
0x18004b8c7  test    rbx, rbx
0x18004b8ca  jz      short loc_18004B901
0x18004b8cc  mov     eax, esi
0x18004b8ce  lock xadd [rbx+8], eax
0x18004b8d3  cmp     eax, 1
0x18004b8d6  jnz     short loc_18004B901
0x18004b8d8  mov     rax, [rbx]
0x18004b8db  mov     rcx, rbx
0x18004b8de  mov     rax, [rax]
0x18004b8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8e6  mov     eax, esi
0x18004b8e8  lock xadd [rbx+0Ch], eax
0x18004b8ed  cmp     eax, 1
0x18004b8f0  jnz     short loc_18004B901
0x18004b8f2  mov     rax, [rbx]
0x18004b8f5  mov     rcx, rbx
0x18004b8f8  mov     rax, [rax+8]
0x18004b8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b901  mov     rbx, [rsp+168h+var_130]
0x18004b906  test    rbx, rbx
0x18004b909  jz      short loc_18004B940
0x18004b90b  mov     eax, esi
0x18004b90d  lock xadd [rbx+8], eax
0x18004b912  cmp     eax, 1
0x18004b915  jnz     short loc_18004B940
0x18004b917  mov     rax, [rbx]
0x18004b91a  mov     rcx, rbx
0x18004b91d  mov     rax, [rax]
0x18004b920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b925  mov     eax, esi
0x18004b927  lock xadd [rbx+0Ch], eax
0x18004b92c  cmp     eax, 1
0x18004b92f  jnz     short loc_18004B940
0x18004b931  mov     rax, [rbx]
0x18004b934  mov     rcx, rbx
0x18004b937  mov     rax, [rax+8]
0x18004b93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b940  mov     rax, [rdi]
0x18004b943  mov     rcx, [rax+0C0h]
0x18004b94a  mov     [rax+0C0h], r13
0x18004b951  test    rcx, rcx
0x18004b954  jz      short loc_18004B966
0x18004b956  mov     rax, [rcx]
0x18004b959  mov     edx, 1
0x18004b95e  mov     rax, [rax]
0x18004b961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b966  sub     r14, r12
0x18004b969  lea     r8, [r14+0Ch]; dwNumberOfBytesToWrite
0x18004b96d  mov     rcx, [rdi]
0x18004b970  mov     rax, [rcx+0D8h]
0x18004b977  test    rax, rax
0x18004b97a  jnz     short loc_18004B983
0x18004b97c  mov     rax, [rcx+0E0h]
0x18004b983  lea     rdx, [r12+rax]; lpBuffer
0x18004b987  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x18004b98a  mov     rcx, [rcx+68h]; hRequest
0x18004b98e  call    cs:__imp_WinHttpWriteData
0x18004b994  test    eax, eax
0x18004b996  jnz     loc_18004BABA
0x18004b99c  call    cs:__imp_GetLastError
0x18004b9a2  mov     ebx, eax
0x18004b9a4  xorps   xmm0, xmm0
0x18004b9a7  movups  xmmword ptr [rsp+168h+var_C8], xmm0
0x18004b9af  mov     ecx, 20h ; ' '; Size
0x18004b9b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b9b9  mov     [rsp+168h+var_C8], rax
0x18004b9c1  mov     [rsp+168h+var_B8], 10h
0x18004b9cd  mov     [rsp+168h+var_B0], 1Fh
0x18004b9d9  movups  xmm0, xmmword ptr cs:aWinhttpwriteda_0; "WinHttpWriteData"
0x18004b9e0  movups  xmmword ptr [rax], xmm0
0x18004b9e3  mov     byte ptr [rax+10h], 0
0x18004b9e7  lea     r8, [rsp+168h+var_C8]
0x18004b9ef  mov     edx, ebx
0x18004b9f1  lea     rcx, [rsp+168h+Src]; Src
0x18004b9f9  call    web__http__client__details__build_error_msg
0x18004b9fe  nop
0x18004b9ff  mov     r8, rax
0x18004ba02  mov     edx, ebx
0x18004ba04  mov     rcx, [rdi]
0x18004ba07  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18004ba0c  nop
0x18004ba0d  mov     rdx, [rsp+168h+var_90]
0x18004ba15  cmp     rdx, 0Fh
0x18004ba19  jbe     short loc_18004BA55
0x18004ba1b  mov     rax, [rsp+168h+Src]
0x18004ba23  inc     rdx; struct std::nothrow_t *
0x18004ba26  cmp     rdx, 1000h
0x18004ba2d  jb      short loc_18004BA4D
0x18004ba2f  mov     rcx, [rax-8]
0x18004ba33  sub     rax, rcx
0x18004ba36  sub     rax, 8
0x18004ba3a  cmp     rax, 1Fh
0x18004ba3e  ja      short loc_18004BA46
0x18004ba40  add     rdx, 27h ; '''
0x18004ba44  jmp     short loc_18004BA50
0x18004ba46  mov     ecx, 5
0x18004ba4b  int     29h; Win8: RtlFailFast(ecx)
0x18004ba4d  mov     rcx, rax; void *
0x18004ba50  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004ba55  mov     [rsp+168h+var_98], r13
0x18004ba5d  mov     [rsp+168h+var_90], 0Fh
0x18004ba69  mov     byte ptr [rsp+168h+Src], 0
0x18004ba71  mov     rdx, [rsp+168h+var_B0]
0x18004ba79  cmp     rdx, 0Fh
0x18004ba7d  jbe     short loc_18004BABA
0x18004ba7f  mov     rax, [rsp+168h+var_C8]
  ... truncated ...
```

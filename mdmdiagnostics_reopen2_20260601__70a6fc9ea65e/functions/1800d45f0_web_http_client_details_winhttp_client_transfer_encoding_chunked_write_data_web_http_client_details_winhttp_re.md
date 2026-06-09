# `web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data(web::http::client::details::winhttp_request_context *)'::`2'::_lambda_1_::operator()(pplx::task<unsigned __int64>)

- ea: `0x1800d45f0`
- end: `0x1800d4be8`
- name: `??R_lambda_1_@?1??_transfer_encoding_chunked_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@3456@@Z@QEBA@V?$task@_K@pplx@@@Z`
- size: `1528`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800d6970`
- `0x1800d73c0`

## callees

- `0x180019080`
- `0x1800190a4`
- `0x180019588`
- `0x180019ede`
- `0x18001a084`
- `0x180020550`
- `0x1800224c0`
- `0x180024770`
- `0x180046040`
- `0x180048c30`
- `0x18004c350`
- `0x180065e80`
- `0x180071d50`
- `0x1800baeb0`
- `0x1800be5f0`
- `0x1800c7590`
- `0x1800d45f0`
- `0x1800d7b70`
- `0x1800e68b0`
- `0x1800e7b88`
- `0x1800e7ba0`
- `0x180193010`

## import_xrefs

- `WINHTTP!WinHttpWriteData` at `0x1800d4a1e`
- `WINHTTP!WinHttpWriteData` at `0x1800d4a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4a2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4a2c`

## string_xrefs

- `0x1800d4a69`: `WinHttpWriteData`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall `web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data'::`2'::_lambda_1_::operator()(
        void **a1,
        __int64 a2)
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
  __int64 v16; // rcx
  __int64 v17; // r8
  _QWORD *v18; // r8
  __int64 v19; // rdx
  void *v20; // rcx
  void *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  void *v24; // rcx
  void *v25; // rdx
  volatile signed __int32 *v26; // rcx
  volatile signed __int32 *v27; // rbx
  volatile signed __int32 *v28; // rbx
  void (__fastcall ***v29)(_QWORD, __int64); // rcx
  void *v30; // rcx
  __int64 v31; // rax
  DWORD LastError; // ebx
  __int64 v33; // r8
  void *v34; // rcx
  void *v35; // rcx
  volatile signed __int32 *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // [rsp+30h] [rbp-138h] BYREF
  volatile signed __int32 *v39; // [rsp+38h] [rbp-130h]
  void **v40; // [rsp+48h] [rbp-120h]
  void *Block[2]; // [rsp+50h] [rbp-118h] BYREF
  __int64 v42; // [rsp+60h] [rbp-108h]
  __int64 v43; // [rsp+68h] [rbp-100h]
  void **v44; // [rsp+70h] [rbp-F8h] BYREF
  __int128 v45; // [rsp+78h] [rbp-F0h]
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-E0h] BYREF
  void *v47[2]; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-B8h]
  unsigned __int64 v49; // [rsp+B8h] [rbp-B0h]
  void *Src[2]; // [rsp+C0h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+D0h] [rbp-98h]
  unsigned __int64 v52; // [rsp+D8h] [rbp-90h]
  void **v53; // [rsp+E0h] [rbp-88h] BYREF
  __int128 v54; // [rsp+E8h] [rbp-80h] BYREF
  int v55; // [rsp+F8h] [rbp-70h]
  void ***v56; // [rsp+100h] [rbp-68h]
  _BYTE v57[40]; // [rsp+108h] [rbp-60h] BYREF

  v40 = a1;
  v43 = a2;
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
             &v38,
             v8 + 10,
             v5);
      pplx::task<unsigned __int64>::wait(v9);
      v10 = v39;
      if ( v39 )
      {
        if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
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
    v37 = std::current_exception(&v38);
    web::http::client::details::request_context::report_exception(*v40, v37);
    v16 = v43;
    goto LABEL_61;
  }
  v14 = web::http::details::chunked_encoding::add_chunked_delimiters(v11, v12, v13, v4);
  if ( !*(_QWORD *)a1[2] )
  {
    v15 = *((_QWORD *)*a1 + 18);
    if ( v15 != -1 )
    {
      if ( !v5 && v15 )
      {
        std::wstring::wstring(v47, L"Unexpected end of request body stream encountered before expected length met.");
        v54 = 0;
        v53 = &web::http::http_exception::`vftable';
        v55 = 0;
        v56 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        utility::conversions::to_utf8string(v57, v47);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)v47);
        web::http::client::details::request_context::report_exception<web::http::http_exception>(*a1, &v53);
        std::string::~string(v57);
        v53 = &std::exception::`vftable';
        o___std_exception_destroy_0(&v54);
        v16 = a2;
LABEL_61:
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
      v40 = Block;
      v42 = 0;
      Block[1] = 0;
      Block[0] = 0;
      Src[0] = v21;
      Src[1] = v20;
      v51 = v19;
      v22 = Concurrency::streams::container_buffer<std::vector<unsigned char>>::container_buffer<std::vector<unsigned char>>(
              v47,
              Src,
              1);
      v44 = &Concurrency::streams::streambuf<unsigned char>::`vftable';
      v45 = 0;
      v23 = *(_QWORD *)(v22 + 16);
      if ( v23 )
        _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
      v45 = *(_OWORD *)(v22 + 8);
      Concurrency::streams::basic_istream<unsigned char>::basic_istream<unsigned char>(&v38, &v44);
      Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v47);
      if ( Block[0] )
      {
        if ( v42 - (unsigned __int64)Block[0] < 0x1000 )
        {
          v24 = Block[0];
        }
        else
        {
          v24 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v24 - 8) > 0x1F )
            goto LABEL_54;
        }
        operator delete(v24);
        *(_OWORD *)Block = 0;
        v42 = 0;
      }
      v25 = *a1;
      v26 = v39;
      if ( v39 )
      {
        _InterlockedIncrement(v39 + 2);
        v26 = v39;
      }
      *((_QWORD *)v25 + 22) = v38;
      v27 = (volatile signed __int32 *)*((_QWORD *)v25 + 23);
      *((_QWORD *)v25 + 23) = v26;
      if ( v27 )
      {
        if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      v28 = v39;
      if ( v39 )
      {
        if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
      v29 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)*a1 + 24);
      *((_QWORD *)*a1 + 24) = 0;
      if ( v29 )
        (**v29)(v29, 1);
    }
  }
  v30 = *a1;
  v31 = *((_QWORD *)*a1 + 27);
  if ( !v31 )
    v31 = *((_QWORD *)v30 + 28);
  if ( !WinHttpWriteData(*((HINTERNET *)v30 + 13), (LPCVOID)(v14 + v31), v5 - v14 + 12, 0) )
  {
    LastError = GetLastError();
    *(_OWORD *)v47 = 0;
    v47[0] = operator new(0x20u);
    v48 = 16;
    v49 = 31;
    strcpy((char *)v47[0], "WinHttpWriteData");
    v33 = web::http::client::details::build_error_msg(Src);
    web::http::client::details::request_context::report_error(*a1, LastError, v33);
    if ( v52 > 0xF )
    {
      if ( v52 + 1 < 0x1000 )
      {
        v34 = Src[0];
      }
      else
      {
        v34 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v34 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v34);
    }
    v51 = 0;
    v52 = 15;
    LOBYTE(Src[0]) = 0;
    if ( v49 > 0xF )
    {
      if ( v49 + 1 < 0x1000 )
      {
        v35 = v47[0];
      }
      else
      {
        v35 = (void *)*((_QWORD *)v47[0] - 1);
        if ( (unsigned __int64)((char *)v47[0] - (char *)v35 - 8) > 0x1F )
LABEL_54:
          __fastfail(5u);
      }
      operator delete(v35);
    }
  }
  v36 = *(volatile signed __int32 **)(a2 + 8);
  if ( v36 )
  {
    if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
      if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
    }
  }
}

```

## disassembly

```asm
0x1800d45f0  mov     [rsp+arg_10], rbx
0x1800d45f5  mov     [rsp+arg_18], rsi
0x1800d45fa  push    rdi
0x1800d45fb  push    r12
0x1800d45fd  push    r13
0x1800d45ff  push    r14
0x1800d4601  push    r15
0x1800d4603  sub     rsp, 140h
0x1800d460a  mov     rax, cs:__security_cookie
0x1800d4611  xor     rax, rsp
0x1800d4614  mov     [rsp+168h+var_38], rax
0x1800d461c  mov     r15, rdx
0x1800d461f  mov     rdi, rcx
0x1800d4622  mov     [rsp+168h+var_120], rcx
0x1800d4627  mov     [rsp+168h+var_100], rdx
0x1800d462c  xor     r13d, r13d
0x1800d462f  mov     rcx, rdx
0x1800d4632  call    ?get@?$task@_K@pplx@@QEBA_KXZ; pplx::task<unsigned __int64>::get(void)
0x1800d4637  mov     r14, rax
0x1800d463a  mov     rcx, [rdi]
0x1800d463d  mov     r10, [rcx+0C0h]
0x1800d4644  test    r10, r10
0x1800d4647  jz      loc_1800D46D4
0x1800d464d  mov     rax, [rdi+10h]
0x1800d4651  cmp     [rax], r13
0x1800d4654  jnz     short loc_1800D46D4
0x1800d4656  mov     r8, [rcx+0D8h]
0x1800d465d  test    r8, r8
0x1800d4660  jnz     short loc_1800D4669
0x1800d4662  mov     r8, [rcx+0E0h]
0x1800d4669  mov     rax, [r10]
0x1800d466c  add     r8, 0Ah
0x1800d4670  mov     r9, r14
0x1800d4673  lea     rdx, [rsp+168h+var_138]
0x1800d4678  mov     rcx, r10
0x1800d467b  mov     rax, [rax+70h]
0x1800d467f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4684  nop
0x1800d4685  mov     rcx, rax
0x1800d4688  call    ?wait@?$task@_K@pplx@@QEBA?AW4task_group_status@2@XZ; pplx::task<unsigned __int64>::wait(void)
0x1800d468d  nop
0x1800d468e  mov     rbx, [rsp+168h+var_130]
0x1800d4693  test    rbx, rbx
0x1800d4696  jz      short loc_1800D46D4
0x1800d4698  mov     esi, 0FFFFFFFFh
0x1800d469d  mov     eax, esi
0x1800d469f  lock xadd [rbx+8], eax
0x1800d46a4  cmp     eax, 1
0x1800d46a7  jnz     short loc_1800D46D9
0x1800d46a9  mov     rax, [rbx]
0x1800d46ac  mov     rcx, rbx
0x1800d46af  mov     rax, [rax]
0x1800d46b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d46b7  mov     eax, esi
0x1800d46b9  lock xadd [rbx+0Ch], eax
0x1800d46be  cmp     eax, 1
0x1800d46c1  jnz     short loc_1800D46D9
0x1800d46c3  mov     rax, [rbx]
0x1800d46c6  mov     rcx, rbx
0x1800d46c9  mov     rax, [rax+8]
0x1800d46cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d46d2  jmp     short loc_1800D46D9
0x1800d46d4  mov     esi, 0FFFFFFFFh
0x1800d46d9  mov     rax, [rdi]
0x1800d46dc  mov     rcx, [rax+0D8h]
0x1800d46e3  test    rcx, rcx
0x1800d46e6  jnz     short loc_1800D46EF
0x1800d46e8  mov     rcx, [rax+0E0h]; this
0x1800d46ef  mov     rdx, [rdi+8]
0x1800d46f3  add     rdx, 0Ch; unsigned __int8 *
0x1800d46f7  mov     r8, r14; unsigned __int64
0x1800d46fa  call    ?add_chunked_delimiters@chunked_encoding@details@http@web@@YA_KPEAE_K1@Z; web::http::details::chunked_encoding::add_chunked_delimiters(uchar *,unsigned __int64,unsigned __int64)
0x1800d46ff  mov     r12, rax
0x1800d4702  mov     rcx, [rdi+10h]
0x1800d4706  cmp     qword ptr [rcx], 0
0x1800d470a  jnz     loc_1800D47EC
0x1800d4710  mov     rdx, [rdi]
0x1800d4713  mov     rcx, [rdx+90h]
0x1800d471a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d471e  jz      loc_1800D47EC
0x1800d4724  test    r14, r14
0x1800d4727  jnz     loc_1800D47E2
0x1800d472d  test    rcx, rcx
0x1800d4730  jz      loc_1800D47E2
0x1800d4736  lea     rdx, aUnexpectedEndO; "Unexpected end of request body stream e"...
0x1800d473d  lea     rcx, [rsp+168h+var_C8]
0x1800d4745  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d474a  nop
0x1800d474b  xorps   xmm0, xmm0
0x1800d474e  movups  [rsp+168h+var_80], xmm0
0x1800d4756  lea     rax, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x1800d475d  mov     [rsp+168h+var_88], rax
0x1800d4765  mov     [rsp+168h+var_70], r13d
0x1800d476d  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1800d4774  mov     [rsp+168h+var_68], rax
0x1800d477c  lea     rdx, [rsp+168h+var_C8]
0x1800d4784  lea     rcx, [rsp+168h+var_60]
0x1800d478c  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x1800d4791  nop
0x1800d4792  lea     rcx, [rsp+168h+var_C8]; this
0x1800d479a  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x1800d479f  lea     rdx, [rsp+168h+var_88]
0x1800d47a7  mov     rcx, [rdi]
0x1800d47aa  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x1800d47af  nop
0x1800d47b0  lea     rcx, [rsp+168h+var_60]
0x1800d47b8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800d47bd  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800d47c4  mov     [rsp+168h+var_88], rax
0x1800d47cc  lea     rcx, [rsp+168h+var_80]
0x1800d47d4  call    _o___std_exception_destroy_0
0x1800d47d9  nop
0x1800d47da  mov     rcx, r15
0x1800d47dd  jmp     loc_1800D4B8D
0x1800d47e2  sub     rcx, r14
0x1800d47e5  mov     [rdx+90h], rcx
0x1800d47ec  test    r14, r14
0x1800d47ef  jnz     loc_1800D49F6
0x1800d47f5  mov     rax, [rdi]
0x1800d47f8  mov     [rax+88h], r13d
0x1800d47ff  mov     rax, [rdi]
0x1800d4802  mov     r8, [rax+0C0h]
0x1800d4809  test    r8, r8
0x1800d480c  jz      loc_1800D49F6
0x1800d4812  mov     r8, [r8+8]
0x1800d4816  test    r8, r8
0x1800d4819  jz      loc_1800D4BBF
0x1800d481f  mov     rdx, [r8+40h]
0x1800d4823  mov     [r8+40h], r13
0x1800d4827  mov     rcx, [r8+38h]
0x1800d482b  mov     [r8+38h], r13
0x1800d482f  mov     rax, [r8+30h]
0x1800d4833  mov     [r8+30h], r13
0x1800d4837  lea     r8, [rsp+168h+Block]
0x1800d483c  mov     [rsp+168h+var_120], r8
0x1800d4841  mov     [rsp+168h+var_108], r13
0x1800d4846  mov     [rsp+168h+Block+8], r13
0x1800d484b  mov     [rsp+168h+Block], r13
0x1800d4850  mov     [rsp+168h+Src], rax
0x1800d4858  mov     [rsp+168h+var_A0], rcx
0x1800d4860  mov     [rsp+168h+var_98], rdx
0x1800d4868  mov     r8d, 1
0x1800d486e  lea     rdx, [rsp+168h+Src]
0x1800d4876  lea     rcx, [rsp+168h+var_C8]
0x1800d487e  call    ??0?$container_buffer@V?$vector@EV?$allocator@E@std@@@std@@@streams@Concurrency@@QEAA@V?$vector@EV?$allocator@E@std@@@std@@H@Z; Concurrency::streams::container_buffer<std::vector<uchar>>::container_buffer<std::vector<uchar>>(std::vector<uchar>,int)
0x1800d4883  mov     rdx, rax
0x1800d4886  lea     rax, ??_7?$streambuf@E@streams@Concurrency@@6B@; const Concurrency::streams::streambuf<uchar>::`vftable'
0x1800d488d  mov     [rsp+168h+var_F8], rax
0x1800d4892  xorps   xmm0, xmm0
0x1800d4895  movdqu  [rsp+168h+var_F0], xmm0
0x1800d489b  mov     rcx, [rdx+10h]
0x1800d489f  test    rcx, rcx
0x1800d48a2  jz      short loc_1800D48A8
0x1800d48a4  lock inc dword ptr [rcx+8]
0x1800d48a8  mov     rax, [rdx+8]
0x1800d48ac  mov     qword ptr [rsp+168h+var_F0], rax
0x1800d48b1  mov     rax, [rdx+10h]
0x1800d48b5  mov     qword ptr [rsp+168h+var_F0+8], rax
0x1800d48bd  lea     rdx, [rsp+168h+var_F8]
0x1800d48c2  lea     rcx, [rsp+168h+var_138]
0x1800d48c7  call    ??$?0E@?$basic_istream@E@streams@Concurrency@@QEAA@V?$streambuf@E@12@@Z; Concurrency::streams::basic_istream<uchar>::basic_istream<uchar>(Concurrency::streams::streambuf<uchar>)
0x1800d48cc  nop
0x1800d48cd  lea     rcx, [rsp+168h+var_C8]
0x1800d48d5  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x1800d48da  nop
0x1800d48db  mov     rax, [rsp+168h+Block]
0x1800d48e0  test    rax, rax
0x1800d48e3  jz      short loc_1800D4927
0x1800d48e5  mov     rdx, [rsp+168h+var_108]
0x1800d48ea  sub     rdx, rax
0x1800d48ed  cmp     rdx, 1000h
0x1800d48f4  jb      short loc_1800D4911
0x1800d48f6  mov     rcx, [rax-8]
0x1800d48fa  sub     rax, rcx
0x1800d48fd  sub     rax, 8
0x1800d4901  cmp     rax, 1Fh
0x1800d4905  ja      loc_1800D4B3A
0x1800d490b  add     rdx, 27h ; '''
0x1800d490f  jmp     short loc_1800D4914
0x1800d4911  mov     rcx, rax; Block
0x1800d4914  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d4919  xorps   xmm0, xmm0
0x1800d491c  movdqu  xmmword ptr [rsp+168h+Block], xmm0
0x1800d4922  mov     [rsp+168h+var_108], r13
0x1800d4927  mov     rdx, [rdi]
0x1800d492a  mov     rcx, [rsp+168h+var_130]
0x1800d492f  test    rcx, rcx
0x1800d4932  jz      short loc_1800D493D
0x1800d4934  lock inc dword ptr [rcx+8]
0x1800d4938  mov     rcx, [rsp+168h+var_130]
0x1800d493d  mov     rax, [rsp+168h+var_138]
0x1800d4942  mov     [rdx+0B0h], rax
0x1800d4949  mov     rbx, [rdx+0B8h]
0x1800d4950  mov     [rdx+0B8h], rcx
0x1800d4957  test    rbx, rbx
0x1800d495a  jz      short loc_1800D4991
0x1800d495c  mov     eax, esi
0x1800d495e  lock xadd [rbx+8], eax
0x1800d4963  cmp     eax, 1
0x1800d4966  jnz     short loc_1800D4991
0x1800d4968  mov     rax, [rbx]
0x1800d496b  mov     rcx, rbx
0x1800d496e  mov     rax, [rax]
0x1800d4971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4976  mov     eax, esi
0x1800d4978  lock xadd [rbx+0Ch], eax
0x1800d497d  cmp     eax, 1
0x1800d4980  jnz     short loc_1800D4991
0x1800d4982  mov     rax, [rbx]
0x1800d4985  mov     rcx, rbx
0x1800d4988  mov     rax, [rax+8]
0x1800d498c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4991  mov     rbx, [rsp+168h+var_130]
0x1800d4996  test    rbx, rbx
0x1800d4999  jz      short loc_1800D49D0
0x1800d499b  mov     eax, esi
0x1800d499d  lock xadd [rbx+8], eax
0x1800d49a2  cmp     eax, 1
0x1800d49a5  jnz     short loc_1800D49D0
0x1800d49a7  mov     rax, [rbx]
0x1800d49aa  mov     rcx, rbx
0x1800d49ad  mov     rax, [rax]
0x1800d49b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d49b5  mov     eax, esi
0x1800d49b7  lock xadd [rbx+0Ch], eax
0x1800d49bc  cmp     eax, 1
0x1800d49bf  jnz     short loc_1800D49D0
0x1800d49c1  mov     rax, [rbx]
0x1800d49c4  mov     rcx, rbx
0x1800d49c7  mov     rax, [rax+8]
0x1800d49cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d49d0  mov     rax, [rdi]
0x1800d49d3  mov     rcx, [rax+0C0h]
0x1800d49da  mov     [rax+0C0h], r13
0x1800d49e1  test    rcx, rcx
0x1800d49e4  jz      short loc_1800D49F6
0x1800d49e6  mov     rax, [rcx]
0x1800d49e9  mov     edx, 1
0x1800d49ee  mov     rax, [rax]
0x1800d49f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d49f6  sub     r14, r12
0x1800d49f9  lea     r8, [r14+0Ch]; dwNumberOfBytesToWrite
0x1800d49fd  mov     rcx, [rdi]
0x1800d4a00  mov     rax, [rcx+0D8h]
0x1800d4a07  test    rax, rax
0x1800d4a0a  jnz     short loc_1800D4A13
0x1800d4a0c  mov     rax, [rcx+0E0h]
0x1800d4a13  lea     rdx, [r12+rax]; lpBuffer
0x1800d4a17  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x1800d4a1a  mov     rcx, [rcx+68h]; hRequest
0x1800d4a1e  call    cs:__imp_WinHttpWriteData
0x1800d4a24  test    eax, eax
0x1800d4a26  jnz     loc_1800D4B4A
0x1800d4a2c  call    cs:__imp_GetLastError
0x1800d4a32  mov     ebx, eax
0x1800d4a34  xorps   xmm0, xmm0
0x1800d4a37  movups  xmmword ptr [rsp+168h+var_C8], xmm0
0x1800d4a3f  mov     ecx, 20h ; ' '; Size
0x1800d4a44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d4a49  mov     [rsp+168h+var_C8], rax
0x1800d4a51  mov     [rsp+168h+var_B8], 10h
0x1800d4a5d  mov     [rsp+168h+var_B0], 1Fh
0x1800d4a69  movups  xmm0, xmmword ptr cs:aWinhttpwriteda; "WinHttpWriteData"
0x1800d4a70  movups  xmmword ptr [rax], xmm0
0x1800d4a73  mov     byte ptr [rax+10h], 0
0x1800d4a77  lea     r8, [rsp+168h+var_C8]
0x1800d4a7f  mov     edx, ebx
0x1800d4a81  lea     rcx, [rsp+168h+Src]; Src
0x1800d4a89  call    web__http__client__details__build_error_msg
0x1800d4a8e  nop
0x1800d4a8f  mov     r8, rax
0x1800d4a92  mov     edx, ebx
0x1800d4a94  mov     rcx, [rdi]
0x1800d4a97  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800d4a9c  nop
0x1800d4a9d  mov     rdx, [rsp+168h+var_90]
0x1800d4aa5  cmp     rdx, 0Fh
0x1800d4aa9  jbe     short loc_1800D4AE5
0x1800d4aab  mov     rax, [rsp+168h+Src]
0x1800d4ab3  inc     rdx
0x1800d4ab6  cmp     rdx, 1000h
0x1800d4abd  jb      short loc_1800D4ADD
0x1800d4abf  mov     rcx, [rax-8]
0x1800d4ac3  sub     rax, rcx
0x1800d4ac6  sub     rax, 8
0x1800d4aca  cmp     rax, 1Fh
0x1800d4ace  ja      short loc_1800D4AD6
0x1800d4ad0  add     rdx, 27h ; '''
0x1800d4ad4  jmp     short loc_1800D4AE0
0x1800d4ad6  mov     ecx, 5
0x1800d4adb  int     29h; Win8: RtlFailFast(ecx)
0x1800d4add  mov     rcx, rax; Block
0x1800d4ae0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d4ae5  mov     [rsp+168h+var_98], r13
0x1800d4aed  mov     [rsp+168h+var_90], 0Fh
0x1800d4af9  mov     byte ptr [rsp+168h+Src], 0
0x1800d4b01  mov     rdx, [rsp+168h+var_B0]
0x1800d4b09  cmp     rdx, 0Fh
0x1800d4b0d  jbe     short loc_1800D4B4A
0x1800d4b0f  mov     rax, [rsp+168h+var_C8]
  ... truncated ...
```

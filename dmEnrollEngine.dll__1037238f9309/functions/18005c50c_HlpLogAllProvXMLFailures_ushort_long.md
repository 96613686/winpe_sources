# HlpLogAllProvXMLFailures(ushort *,long *)

- ea: `0x18005c50c`
- end: `0x18005c8f7`
- name: `?HlpLogAllProvXMLFailures@@YAJPEAGPEAJ@Z`
- size: `1003`
- prototype: `__int64 __fastcall(unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004ff88`

## callees

- `0x18000e508`
- `0x1800140d0`
- `0x180016508`
- `0x18001aec8`
- `0x18004c594`
- `0x180057e28`
- `0x180057e50`
- `0x180059f0c`
- `0x18005b7f0`
- `0x18005c50c`
- `0x180071b88`
- `0x1800725fc`
- `0x18007b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c75d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c75d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005c56c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005c56c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18005c6ec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18005c6ec`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c6a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c6a6`
- `OLEAUT32!__imp_VariantInit` at `0x18005c6ba`
- `OLEAUT32!__imp_VariantInit` at `0x18005c80f`
- `OLEAUT32!__imp_VariantInit` at `0x18005c873`
- `OLEAUT32!__imp_VariantInit` at `0x18005c6ba`
- `OLEAUT32!__imp_VariantInit` at `0x18005c80f`
- `OLEAUT32!__imp_VariantInit` at `0x18005c873`
- `OLEAUT32!__imp_VariantClear` at `0x18005c819`
- `OLEAUT32!__imp_VariantClear` at `0x18005c87d`
- `OLEAUT32!__imp_VariantClear` at `0x18005c819`
- `OLEAUT32!__imp_VariantClear` at `0x18005c87d`

## string_xrefs

- `0x18005c537`: `HlpLogAllProvXMLFailures`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall HlpLogAllProvXMLFailures(unsigned __int16 *a1, int *a2)
{
  HRESULT v4; // ebx
  unsigned int i; // esi
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  ATL::CComBSTR *v8; // rax
  const unsigned __int16 *v9; // rdi
  __int64 *j; // rbx
  int v11; // r14d
  CEnrollmentLogger *Logger; // rax
  CEnrollmentLogger *v13; // rax
  __int64 v14; // rdx
  __int64 v16; // [rsp+30h] [rbp-89h] BYREF
  __int64 v17; // [rsp+38h] [rbp-81h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-79h] BYREF
  __int64 v19; // [rsp+58h] [rbp-61h] BYREF
  __int64 v20; // [rsp+60h] [rbp-59h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-51h] BYREF
  VARIANTARG v22; // [rsp+70h] [rbp-49h] BYREF
  int v23; // [rsp+88h] [rbp-31h] BYREF
  unsigned __int16 *v24[4]; // [rsp+90h] [rbp-29h] BYREF
  _QWORD v25[2]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int16 *v26[4]; // [rsp+C0h] [rbp+7h] BYREF
  BSTR bstrString[2]; // [rsp+E0h] [rbp+27h] BYREF
  __int16 v28; // [rsp+130h] [rbp+77h] BYREF
  int ParentNodeAsString; // [rsp+138h] [rbp+7Fh] BYREF

  ParentNodeAsString = 0;
  v25[0] = "HlpLogAllProvXMLFailures";
  v25[1] = &ParentNodeAsString;
  ppv = 0;
  v4 = CoCreateInstance(
         &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
         &ppv);
  ParentNodeAsString = v4;
  if ( v4 >= 0 )
  {
    v28 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, a1, &v28);
    ParentNodeAsString = v4;
    if ( v4 >= 0 )
    {
      if ( v28 )
      {
        v20 = 0;
        ParentNodeAsString = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 288LL))(
                               ppv,
                               L"//parm-error | //characteristic-error",
                               &v20);
        if ( ParentNodeAsString >= 0 && v20 )
        {
          v23 = 0;
          v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 64LL))(v20, &v23);
          ParentNodeAsString = v4;
          if ( v4 >= 0 )
          {
            for ( i = 0; (int)i < v23; ++i )
            {
              v19 = 0;
              ParentNodeAsString = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 56LL))(
                                     v20,
                                     i,
                                     &v19);
              if ( ParentNodeAsString >= 0 )
              {
                v16 = 0;
                ParentNodeAsString = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 136LL))(v19, &v16);
                if ( ParentNodeAsString >= 0 )
                {
                  v17 = 0;
                  v6 = v16;
                  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 56LL);
                  v8 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"hresult");
                  ParentNodeAsString = v7(v6, *(_QWORD *)v8, &v17);
                  SysFreeString(bstrString[0]);
                  if ( ParentNodeAsString >= 0 )
                  {
                    VariantInit(&pvarg);
                    ParentNodeAsString = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v17 + 64LL))(
                                           v17,
                                           &pvarg);
                    if ( ParentNodeAsString >= 0 && lstrcmpW(pvarg.bstrVal, L"0x86000009") )
                    {
                      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v24);
                      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v26);
                      ParentNodeAsString = GetParentNodeAsString(v19, 0, v26, v24);
                      if ( ParentNodeAsString >= 0 )
                      {
                        if ( a2 )
                        {
                          if ( !*a2 )
                          {
                            v9 = v26[0];
                            if ( v26[0] != v26[1] )
                            {
                              for ( j = (__int64 *)&mapping; j != WP_ENROLLMENT_CLIENT_PROVIDER_Context; j += 2 )
                              {
                                v11 = *((_DWORD *)j + 2);
                                if ( !(unsigned int)_o__wcsicmp(*j, v9) )
                                  goto LABEL_23;
                              }
                              Logger = CEnrollmentLogger::GetLogger();
                              CEnrollmentLogger::LogEnrollConfigMgrUnknownCSPFailure(Logger, v9);
                              v11 = -2145910750;
LABEL_23:
                              *a2 = v11;
                            }
                          }
                        }
                        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                                 v24,
                                                 L"\" hresult=\"",
                                                 11)
                          || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                                 v24,
                                                 pvarg.llVal)
                          || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                                 v24,
                                                 L"\">",
                                                 2) )
                        {
                          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)v26);
                          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)v24);
                          v22 = pvarg;
                          VariantInit(&pvarg);
                          VariantClear(&v22);
                          wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v17);
                          wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v16);
                          wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v19);
                          wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v20);
                          v4 = -2147024882;
                          goto LABEL_36;
                        }
                        v13 = CEnrollmentLogger::GetLogger();
                        CEnrollmentLogger::LogEnrollProvisioningXMLError(v13, v24[0]);
                      }
                      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)v26);
                      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)v24);
                    }
                    v22 = pvarg;
                    VariantInit(&pvarg);
                    VariantClear(&v22);
                  }
                  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v17);
                }
                wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v16);
              }
              wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v19);
              v4 = ParentNodeAsString;
            }
          }
        }
        else
        {
          v4 = -2147467259;
          ParentNodeAsString = -2147467259;
        }
        wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v20);
      }
    }
  }
LABEL_36:
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&ppv);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v25, v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005c50c  mov     [rsp-8+arg_0], rbx
0x18005c511  mov     [rsp-8+arg_8], rsi
0x18005c516  push    rbp
0x18005c517  push    rdi
0x18005c518  push    r12
0x18005c51a  push    r14
0x18005c51c  push    r15
0x18005c51e  lea     rbp, [rsp-37h]
0x18005c523  sub     rsp, 0F0h
0x18005c52a  mov     r15, rdx
0x18005c52d  mov     rdi, rcx
0x18005c530  xor     r12d, r12d
0x18005c533  mov     [rbp+57h+arg_18], r12d
0x18005c537  lea     rax, aHlplogallprovx; "HlpLogAllProvXMLFailures"
0x18005c53e  mov     [rbp+57h+var_60], rax
0x18005c542  lea     rax, [rbp+57h+arg_18]
0x18005c546  mov     [rbp+57h+var_58], rax
0x18005c54a  mov     [rbp+57h+var_A8], r12
0x18005c54e  lea     rax, [rbp+57h+var_A8]
0x18005c552  mov     [rsp+110h+ppv], rax; ppv
0x18005c557  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18005c55e  xor     edx, edx; pUnkOuter
0x18005c560  lea     r8d, [r12+1]; dwClsContext
0x18005c565  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18005c56c  call    cs:__imp_CoCreateInstance
0x18005c572  mov     ebx, eax
0x18005c574  mov     [rbp+57h+arg_18], eax
0x18005c577  test    eax, eax
0x18005c579  js      loc_18005C8C6
0x18005c57f  mov     [rbp+57h+arg_10], r12w
0x18005c584  mov     rcx, [rbp+57h+var_A8]
0x18005c588  mov     rax, [rcx]
0x18005c58b  lea     r8, [rbp+57h+arg_10]
0x18005c58f  mov     rdx, rdi
0x18005c592  mov     rax, [rax+208h]
0x18005c599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c59e  mov     ebx, eax
0x18005c5a0  mov     [rbp+57h+arg_18], eax
0x18005c5a3  test    eax, eax
0x18005c5a5  js      loc_18005C8C6
0x18005c5ab  cmp     [rbp+57h+arg_10], r12w
0x18005c5b0  jz      loc_18005C8C6
0x18005c5b6  mov     [rbp+57h+var_B0], r12
0x18005c5ba  mov     rcx, [rbp+57h+var_A8]
0x18005c5be  mov     rax, [rcx]
0x18005c5c1  lea     r8, [rbp+57h+var_B0]
0x18005c5c5  lea     rdx, aParmErrorChara; "//parm-error | //characteristic-error"
0x18005c5cc  mov     rax, [rax+120h]
0x18005c5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5d8  mov     [rbp+57h+arg_18], eax
0x18005c5db  test    eax, eax
0x18005c5dd  js      loc_18005C8B4
0x18005c5e3  mov     rcx, [rbp+57h+var_B0]
0x18005c5e7  test    rcx, rcx
0x18005c5ea  jz      loc_18005C8B4
0x18005c5f0  mov     [rbp+57h+var_88], r12d
0x18005c5f4  mov     rax, [rcx]
0x18005c5f7  lea     rdx, [rbp+57h+var_88]
0x18005c5fb  mov     rax, [rax+40h]
0x18005c5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c604  mov     ebx, eax
0x18005c606  mov     [rbp+57h+arg_18], eax
0x18005c609  test    eax, eax
0x18005c60b  js      loc_18005C8BC
0x18005c611  mov     esi, r12d
0x18005c614  cmp     esi, [rbp+57h+var_88]
0x18005c617  jge     loc_18005C8BC
0x18005c61d  mov     [rbp+57h+var_B8], r12
0x18005c621  mov     rcx, [rbp+57h+var_B0]
0x18005c625  mov     rax, [rcx]
0x18005c628  lea     r8, [rbp+57h+var_B8]
0x18005c62c  mov     edx, esi
0x18005c62e  mov     rax, [rax+38h]
0x18005c632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c637  mov     [rbp+57h+arg_18], eax
0x18005c63a  test    eax, eax
0x18005c63c  js      loc_18005C836
0x18005c642  mov     [rsp+110h+var_E0], r12
0x18005c647  mov     rcx, [rbp+57h+var_B8]
0x18005c64b  mov     rax, [rcx]
0x18005c64e  lea     rdx, [rsp+110h+var_E0]
0x18005c653  mov     rax, [rax+88h]
0x18005c65a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c65f  mov     [rbp+57h+arg_18], eax
0x18005c662  test    eax, eax
0x18005c664  js      loc_18005C82B
0x18005c66a  mov     [rsp+110h+var_D8], r12
0x18005c66f  mov     rdi, [rsp+110h+var_E0]
0x18005c674  mov     rax, [rdi]
0x18005c677  mov     rbx, [rax+38h]
0x18005c67b  lea     rdx, aHresult_0; "hresult"
0x18005c682  lea     rcx, [rbp+57h+bstrString]; this
0x18005c686  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18005c68b  nop
0x18005c68c  lea     r8, [rsp+110h+var_D8]
0x18005c691  mov     rdx, [rax]
0x18005c694  mov     rcx, rdi
0x18005c697  mov     rax, rbx
0x18005c69a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c69f  mov     [rbp+57h+arg_18], eax
0x18005c6a2  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18005c6a6  call    cs:__imp_SysFreeString
0x18005c6ac  cmp     [rbp+57h+arg_18], r12d
0x18005c6b0  jl      loc_18005C820
0x18005c6b6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005c6ba  call    cs:__imp_VariantInit
0x18005c6c0  nop
0x18005c6c1  mov     rcx, [rsp+110h+var_D8]
0x18005c6c6  mov     rax, [rcx]
0x18005c6c9  lea     rdx, [rbp+57h+pvarg]
0x18005c6cd  mov     rax, [rax+40h]
0x18005c6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c6d6  mov     [rbp+57h+arg_18], eax
0x18005c6d9  test    eax, eax
0x18005c6db  js      loc_18005C7F9
0x18005c6e1  lea     rdx, a0x86000009; "0x86000009"
0x18005c6e8  mov     rcx, qword ptr [rbp+57h+pvarg+8]; lpString1
0x18005c6ec  call    cs:__imp_lstrcmpW
0x18005c6f2  test    eax, eax
0x18005c6f4  jz      loc_18005C7F9
0x18005c6fa  lea     rcx, [rbp+57h+var_80]
0x18005c6fe  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18005c703  nop
0x18005c704  lea     rcx, [rbp+57h+var_50]
0x18005c708  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18005c70d  nop
0x18005c70e  lea     r9, [rbp+57h+var_80]
0x18005c712  lea     r8, [rbp+57h+var_50]
0x18005c716  xor     edx, edx
0x18005c718  mov     rcx, [rbp+57h+var_B8]
0x18005c71c  call    GetParentNodeAsString
0x18005c721  mov     [rbp+57h+arg_18], eax
0x18005c724  test    eax, eax
0x18005c726  js      loc_18005C7E5
0x18005c72c  test    r15, r15
0x18005c72f  jz      short loc_18005C786
0x18005c731  cmp     [r15], r12d
0x18005c734  jnz     short loc_18005C786
0x18005c736  mov     rdi, [rbp+57h+var_50]
0x18005c73a  cmp     rdi, [rbp+57h+var_48]
0x18005c73e  jz      short loc_18005C786
0x18005c740  lea     rbx, ?mapping@@3PAUCSPPair@@A; CSPPair near * mapping
0x18005c747  lea     rax, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x18005c74e  cmp     rbx, rax
0x18005c751  jz      short loc_18005C76D
0x18005c753  mov     r14d, [rbx+8]
0x18005c757  mov     rdx, rdi
0x18005c75a  mov     rcx, [rbx]
0x18005c75d  call    cs:__imp__o__wcsicmp
0x18005c763  test    eax, eax
0x18005c765  jz      short loc_18005C783
0x18005c767  add     rbx, 10h
0x18005c76b  jmp     short loc_18005C747
0x18005c76d  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005c772  mov     rdx, rdi; unsigned __int16 *
0x18005c775  mov     rcx, rax; this
0x18005c778  call    ?LogEnrollConfigMgrUnknownCSPFailure@CEnrollmentLogger@@QEAAXPEBG@Z; CEnrollmentLogger::LogEnrollConfigMgrUnknownCSPFailure(ushort const *)
0x18005c77d  mov     r14d, 80180022h
0x18005c783  mov     [r15], r14d
0x18005c786  mov     r8d, 0Bh
0x18005c78c  lea     rdx, aHresult; "\" hresult=\""
0x18005c793  lea     rcx, [rbp+57h+var_80]
0x18005c797  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18005c79c  test    al, al
0x18005c79e  jz      loc_18005C849
0x18005c7a4  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x18005c7a8  lea     rcx, [rbp+57h+var_80]
0x18005c7ac  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18005c7b1  test    al, al
0x18005c7b3  jz      loc_18005C849
0x18005c7b9  mov     r8d, 2
0x18005c7bf  lea     rdx, asc_18009707C; "\">"
0x18005c7c6  lea     rcx, [rbp+57h+var_80]
0x18005c7ca  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18005c7cf  test    al, al
0x18005c7d1  jz      short loc_18005C849
0x18005c7d3  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005c7d8  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x18005c7dc  mov     rcx, rax; this
0x18005c7df  call    ?LogEnrollProvisioningXMLError@CEnrollmentLogger@@QEAAXPEBG@Z; CEnrollmentLogger::LogEnrollProvisioningXMLError(ushort const *)
0x18005c7e4  nop
0x18005c7e5  lea     rcx, [rbp+57h+var_50]
0x18005c7e9  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18005c7ee  nop
0x18005c7ef  lea     rcx, [rbp+57h+var_80]
0x18005c7f3  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18005c7f8  nop
0x18005c7f9  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18005c7fd  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18005c802  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18005c806  movsd   qword ptr [rbp+57h+var_A0+10h], xmm1
0x18005c80b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005c80f  call    cs:__imp_VariantInit
0x18005c815  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18005c819  call    cs:__imp_VariantClear
0x18005c81f  nop
0x18005c820  lea     rcx, [rsp+110h+var_D8]
0x18005c825  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005c82a  nop
0x18005c82b  lea     rcx, [rsp+110h+var_E0]
0x18005c830  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005c835  nop
0x18005c836  lea     rcx, [rbp+57h+var_B8]
0x18005c83a  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005c83f  inc     esi
0x18005c841  mov     ebx, [rbp+57h+arg_18]
0x18005c844  jmp     loc_18005C614
0x18005c849  lea     rcx, [rbp+57h+var_50]
0x18005c84d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18005c852  nop
0x18005c853  lea     rcx, [rbp+57h+var_80]
0x18005c857  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18005c85c  nop
0x18005c85d  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18005c861  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18005c866  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18005c86a  movsd   qword ptr [rbp+57h+var_A0+10h], xmm1
0x18005c86f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005c873  call    cs:__imp_VariantInit
0x18005c879  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18005c87d  call    cs:__imp_VariantClear
0x18005c883  nop
0x18005c884  lea     rcx, [rsp+110h+var_D8]
0x18005c889  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005c88e  nop
0x18005c88f  lea     rcx, [rsp+110h+var_E0]
0x18005c894  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005c899  nop
0x18005c89a  lea     rcx, [rbp+57h+var_B8]
0x18005c89e  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005c8a3  nop
0x18005c8a4  lea     rcx, [rbp+57h+var_B0]
0x18005c8a8  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005c8ad  mov     ebx, 8007000Eh
0x18005c8b2  jmp     short loc_18005C8C6
0x18005c8b4  mov     ebx, 80004005h
0x18005c8b9  mov     [rbp+57h+arg_18], ebx
0x18005c8bc  lea     rcx, [rbp+57h+var_B0]
0x18005c8c0  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005c8c5  nop
0x18005c8c6  lea     rcx, [rbp+57h+var_A8]
0x18005c8ca  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005c8cf  nop
0x18005c8d0  lea     rcx, [rbp+57h+var_60]; this
0x18005c8d4  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18005c8d9  mov     eax, ebx
0x18005c8db  lea     r11, [rsp+110h+var_20]
0x18005c8e3  mov     rbx, [r11+30h]
0x18005c8e7  mov     rsi, [r11+38h]
0x18005c8eb  mov     rsp, r11
0x18005c8ee  pop     r15
0x18005c8f0  pop     r14
0x18005c8f2  pop     r12
0x18005c8f4  pop     rdi
0x18005c8f5  pop     rbp
0x18005c8f6  retn
```

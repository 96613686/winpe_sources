# _lambda_7ae5644b0bef50eecf3a34aed9b03a32_::operator()(Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<HSTRING__ *>> &)

- ea: `0x1800a7460`
- end: `0x1800a76a3`
- name: `??R_lambda_7ae5644b0bef50eecf3a34aed9b03a32_@@QEBAJAEAV?$CMarshaledInterfaceResult@U?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Internal@Windows@@@Z`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800abec0`

## callees

- `0x180007bbc`
- `0x180008544`
- `0x18001ad08`
- `0x18003e478`
- `0x18007ec64`
- `0x18009e294`
- `0x1800a7460`
- `0x1800ad494`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a757f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a758a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a757f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a758a`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800a75f5`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800a75f5`

## string_xrefs

- `0x1800a7691`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800a7496`: `shell\oobe\machine\plugins\adapters\winrt\oobeexpeditedupdate.cpp`
- `0x1800a74e3`: `shell\oobe\machine\plugins\adapters\winrt\oobeexpeditedupdate.cpp`
- `0x1800a7609`: `shell\oobe\machine\plugins\adapters\winrt\oobeexpeditedupdate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall _lambda_7ae5644b0bef50eecf3a34aed9b03a32_::operator()(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  int i; // eax
  __int64 (__fastcall *v9)(__int64 *, _QWORD, HSTRING *); // rbx
  int v10; // eax
  __int64 *v11; // rcx
  __int64 v12; // rax
  int AgileReference; // eax
  __int64 v14; // rdx
  __int64 v15; // rdi
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  int v19; // [rsp+20h] [rbp-50h]
  __int64 v20; // [rsp+30h] [rbp-40h] BYREF
  __int64 v21; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v22; // [rsp+40h] [rbp-30h]
  unsigned int v23; // [rsp+48h] [rbp-28h]
  HSTRING string; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v25[8]; // [rsp+58h] [rbp-18h] BYREF
  int v26; // [rsp+60h] [rbp-10h]
  HSTRING v27; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  __int64 *v29; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v30; // [rsp+B0h] [rbp+40h] BYREF
  __int64 *v31; // [rsp+B8h] [rbp+48h] BYREF

  CloudExperienceHostAPI::OobeExpeditedUpdateManagerStatics::_getExpeditedUpdateManager(*(_QWORD *)a1, &v31);
  if ( !v31 )
  {
    v5 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E3,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobeexpeditedupdate.cpp",
      (const char *)0x8000FFFFLL,
      v19);
LABEL_16:
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v31);
    return v5;
  }
  v29 = 0;
  v6 = *v31;
  v29 = 0;
  LOBYTE(v4) = *(_BYTE *)(a1 + 16);
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, __int64 **))(v6 + 128))(
         v31,
         v4,
         *(unsigned int *)(a1 + 20),
         &v29);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E6,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobeexpeditedupdate.cpp",
      (const char *)(unsigned int)v7,
      v19);
LABEL_15:
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v29);
    goto LABEL_16;
  }
  v22 = v29;
  v23 = 0;
  string = 0;
  Windows::Foundation::Collections::end<HSTRING__ *>((__int64)v25, v29);
  for ( i = 0; i != v26; i = ++v23 )
  {
    v9 = *(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING *))(*v22 + 48);
    WindowsDeleteString(string);
    string = 0;
    v10 = v9(v22, v23, &string);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v10,
        v19);
    (*(void (__fastcall **)(_QWORD, HSTRING))(**(_QWORD **)(a1 + 8) + 104LL))(*(_QWORD *)(a1 + 8), string);
  }
  WindowsDeleteString(v27);
  WindowsDeleteString(string);
  v30 = 0;
  v11 = *(__int64 **)(a1 + 8);
  v12 = *v11;
  v30 = 0;
  AgileReference = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v12 + 64))(v11, &v30);
  v5 = AgileReference;
  if ( AgileReference < 0 )
  {
    v14 = 749;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobeexpeditedupdate.cpp",
      (const char *)(unsigned int)AgileReference,
      v19);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v30);
    goto LABEL_15;
  }
  v15 = v30;
  v20 = a2 + 16;
  v16 = (_QWORD *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v20);
  v17 = v16;
  if ( v15 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v16);
    AgileReference = RoGetAgileReference(0, &GUID_2f13c006_a03a_5f69_b090_75a43e33423e, v15, v17);
    v5 = AgileReference;
    if ( AgileReference < 0 )
    {
      v14 = 750;
      goto LABEL_14;
    }
  }
  else
  {
    v21 = 0;
    v20 = *v16;
    *v16 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  }
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v30);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v29);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v31);
  return 0;
}

```

## disassembly

```asm
0x1800a7460  push    rbp
0x1800a7462  push    rbx
0x1800a7463  push    rsi
0x1800a7464  push    rdi
0x1800a7465  push    r14
0x1800a7467  mov     rbp, rsp
0x1800a746a  sub     rsp, 70h
0x1800a746e  mov     r14, rdx
0x1800a7471  mov     rsi, rcx
0x1800a7474  lea     rdx, [rbp+arg_18]
0x1800a7478  mov     rcx, [rcx]
0x1800a747b  call    ?_getExpeditedUpdateManager@OobeExpeditedUpdateManagerStatics@CloudExperienceHostAPI@@AEAA?AV?$com_ptr_t@UIOobeExpeditedUpdateManager@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@XZ; CloudExperienceHostAPI::OobeExpeditedUpdateManagerStatics::_getExpeditedUpdateManager(void)
0x1800a7480  nop
0x1800a7481  mov     rcx, [rbp+arg_18]
0x1800a7485  test    rcx, rcx
0x1800a7488  jnz     short loc_1800A74AC
0x1800a748a  mov     rcx, [rbp+28h]; this
0x1800a748e  mov     ebx, 8000FFFFh
0x1800a7493  mov     r9d, ebx; char *
0x1800a7496  lea     r8, aShellOobeMachi_1; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800a749d  mov     edx, 2E3h; void *
0x1800a74a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a74a7  jmp     loc_1800A762E
0x1800a74ac  mov     [rbp+arg_0], 0
0x1800a74b4  mov     rax, [rcx]
0x1800a74b7  mov     [rbp+arg_0], 0
0x1800a74bf  lea     r9, [rbp+arg_0]
0x1800a74c3  mov     r8d, [rsi+14h]
0x1800a74c7  mov     dl, [rsi+10h]
0x1800a74ca  mov     rax, [rax+80h]
0x1800a74d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a74d6  mov     ebx, eax
0x1800a74d8  test    eax, eax
0x1800a74da  jns     short loc_1800A74F9
0x1800a74dc  mov     rcx, [rbp+28h]; this
0x1800a74e0  mov     r9d, eax; char *
0x1800a74e3  lea     r8, aShellOobeMachi_1; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800a74ea  mov     edx, 2E6h; void *
0x1800a74ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a74f4  jmp     loc_1800A7624
0x1800a74f9  mov     rdx, [rbp+arg_0]
0x1800a74fd  mov     [rbp+var_30], rdx
0x1800a7501  mov     [rbp+var_28], 0
0x1800a7508  mov     [rbp+string], 0
0x1800a7510  lea     rcx, [rbp+var_18]
0x1800a7514  call    ??$end@PEAUHSTRING__@@@Collections@Foundation@Windows@@YA?AVvector_iterator@?$vector_range@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@PEAU?$IVector@PEAUHSTRING__@@@012@@Z; Windows::Foundation::Collections::end<HSTRING__ *>(Windows::Foundation::Collections::IVector<HSTRING__ *> *)
0x1800a7519  nop
0x1800a751a  mov     eax, [rbp+var_28]
0x1800a751d  cmp     eax, [rbp+var_10]
0x1800a7520  jz      short loc_1800A757B
0x1800a7522  mov     rdi, [rbp+var_30]
0x1800a7526  mov     rax, [rdi]
0x1800a7529  mov     rbx, [rax+30h]
0x1800a752d  mov     rcx, [rbp+string]; string
0x1800a7531  call    cs:__imp_WindowsDeleteString
0x1800a7537  mov     [rbp+string], 0
0x1800a753f  lea     r8, [rbp+string]
0x1800a7543  mov     edx, [rbp+var_28]
0x1800a7546  mov     rcx, rdi
0x1800a7549  mov     rax, rbx
0x1800a754c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7551  mov     rcx, [rbp+28h]; this
0x1800a7555  test    eax, eax
0x1800a7557  js      loc_1800A768E
0x1800a755d  mov     rcx, [rsi+8]
0x1800a7561  mov     rax, [rcx]
0x1800a7564  mov     rdx, [rbp+string]
0x1800a7568  mov     rax, [rax+68h]
0x1800a756c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7571  mov     eax, [rbp+var_28]
0x1800a7574  inc     eax
0x1800a7576  mov     [rbp+var_28], eax
0x1800a7579  jmp     short loc_1800A751D
0x1800a757b  mov     rcx, [rbp+var_8]; string
0x1800a757f  call    cs:__imp_WindowsDeleteString
0x1800a7585  nop
0x1800a7586  mov     rcx, [rbp+string]; string
0x1800a758a  call    cs:__imp_WindowsDeleteString
0x1800a7590  mov     [rbp+arg_10], 0
0x1800a7598  mov     rcx, [rsi+8]
0x1800a759c  mov     rax, [rcx]
0x1800a759f  mov     [rbp+arg_10], 0
0x1800a75a7  lea     rdx, [rbp+arg_10]
0x1800a75ab  mov     rax, [rax+40h]
0x1800a75af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a75b4  mov     ebx, eax
0x1800a75b6  test    eax, eax
0x1800a75b8  jns     short loc_1800A75C1
0x1800a75ba  mov     edx, 2EDh
0x1800a75bf  jmp     short loc_1800A7606
0x1800a75c1  mov     rdi, [rbp+arg_10]
0x1800a75c5  lea     rax, [r14+10h]
0x1800a75c9  mov     [rbp+var_40], rax
0x1800a75cd  lea     rcx, [rbp+var_40]
0x1800a75d1  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x1800a75d6  mov     rbx, rax
0x1800a75d9  test    rdi, rdi
0x1800a75dc  jz      short loc_1800A763B
0x1800a75de  mov     rcx, rax
0x1800a75e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a75e6  mov     r9, rbx
0x1800a75e9  mov     r8, rdi
0x1800a75ec  lea     rdx, _GUID_2f13c006_a03a_5f69_b090_75a43e33423e
0x1800a75f3  xor     ecx, ecx
0x1800a75f5  call    cs:__imp_RoGetAgileReference
0x1800a75fb  mov     ebx, eax
0x1800a75fd  test    eax, eax
0x1800a75ff  jns     short loc_1800A7664
0x1800a7601  mov     edx, 2EEh; void *
0x1800a7606  mov     r9d, eax; char *
0x1800a7609  lea     r8, aShellOobeMachi_1; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800a7610  mov     rcx, [rbp+28h]; this
0x1800a7614  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7619  nop
0x1800a761a  lea     rcx, [rbp+arg_10]
0x1800a761e  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800a7623  nop
0x1800a7624  lea     rcx, [rbp+arg_0]
0x1800a7628  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800a762d  nop
0x1800a762e  lea     rcx, [rbp+arg_18]
0x1800a7632  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800a7637  mov     eax, ebx
0x1800a7639  jmp     short loc_1800A7683
0x1800a763b  mov     [rbp+var_38], 0
0x1800a7643  mov     rax, [rax]
0x1800a7646  mov     [rbp+var_40], rax
0x1800a764a  mov     qword ptr [rbx], 0
0x1800a7651  lea     rcx, [rbp+var_40]
0x1800a7655  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a765a  lea     rcx, [rbp+var_38]
0x1800a765e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7663  nop
0x1800a7664  lea     rcx, [rbp+arg_10]
0x1800a7668  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800a766d  nop
0x1800a766e  lea     rcx, [rbp+arg_0]
0x1800a7672  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800a7677  nop
0x1800a7678  lea     rcx, [rbp+arg_18]
0x1800a767c  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800a7681  xor     eax, eax
0x1800a7683  add     rsp, 70h
0x1800a7687  pop     r14
0x1800a7689  pop     rdi
0x1800a768a  pop     rsi
0x1800a768b  pop     rbx
0x1800a768c  pop     rbp
0x1800a768d  retn
0x1800a768e  mov     r9d, eax; char *
0x1800a7691  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a7698  mov     edx, 1CBEh; void *
0x1800a769d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

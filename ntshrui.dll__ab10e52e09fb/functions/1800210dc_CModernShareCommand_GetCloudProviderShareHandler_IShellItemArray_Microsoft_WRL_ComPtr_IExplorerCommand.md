# CModernShareCommand::GetCloudProviderShareHandler(IShellItemArray *,Microsoft::WRL::ComPtr<IExplorerCommand> &)

- ea: `0x1800210dc`
- end: `0x1800214c5`
- name: `?GetCloudProviderShareHandler@CModernShareCommand@@QEAAJPEAUIShellItemArray@@AEAV?$ComPtr@UIExplorerCommand@@@WRL@Microsoft@@@Z`
- size: `1001`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f880`
- `0x18003d194`

## callees

- `0x180008900`
- `0x18001ade4`
- `0x18001c064`
- `0x18001d18c`
- `0x18001ee88`
- `0x1800210dc`
- `0x1800214cc`
- `0x180021618`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002135a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002135a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800212fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800212fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002143e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002143e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002132e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002132e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021126`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800211f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021275`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800211f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021275`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021496`

## string_xrefs

- `0x180021139`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180021181`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x1800211d9`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180021247`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18002139d`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CModernShareCommand::GetCloudProviderShareHandler(RTL_SRWLOCK *a1, __int64 a2, __int64 a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, __int64); // rbx
  __int64 v12; // rax
  int v13; // eax
  LPVOID v14; // rbx
  __int64 (__fastcall *v15)(LPVOID, GUID *, __int64 *); // rdi
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, LPVOID, __int64 *, _QWORD); // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64); // rbx
  __int64 v22; // rax
  RTL_SRWLOCK *v23; // rbx
  RTL_SRWLOCK *v24; // r14
  LPCWCH *v25; // r15
  LPVOID v26; // rsi
  __int64 (__fastcall *v27)(LPVOID, LPVOID, GUID *, __int64); // rdi
  int v28; // eax
  unsigned int v29; // edi
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  LPVOID v33; // rcx
  int *ppv; // [rsp+20h] [rbp-58h]
  __int64 v36; // [rsp+30h] [rbp-48h] BYREF
  __int64 v37; // [rsp+38h] [rbp-40h] BYREF
  __int64 v38; // [rsp+40h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-30h] BYREF
  LPCWCH lpString2; // [rsp+50h] [rbp-28h] BYREF
  LPVOID v41; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v42[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  int v44; // [rsp+D8h] [rbp+60h] BYREF

  v41 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v41);
  v6 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_9cb181e7_8ea8_49ea_833b_1a2981643682, &v41);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x859,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v6,
      (int)ppv);
LABEL_43:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v41);
    return v7;
  }
  v36 = 0;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 64LL);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v36);
  v9 = v8(a2, 0, &v36);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85C,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v9,
      (int)ppv);
LABEL_5:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v36);
    goto LABEL_43;
  }
  pv = 0;
  v10 = v36;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v36 + 40LL);
  v12 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  v13 = v11(v10, 2147844096LL, v12);
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85E,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v13,
      (int)ppv);
LABEL_8:
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_5;
  }
  lpString2 = 0;
  v38 = 0;
  v44 = 0;
  v37 = 0;
  v14 = v41;
  v15 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v41;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v37);
  v16 = v15(v14, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v37);
  v7 = v16;
  if ( v16 < 0 )
  {
    v17 = 2149;
    goto LABEL_12;
  }
  v18 = v37;
  v19 = *(__int64 (__fastcall **)(__int64, LPVOID, __int64 *, _QWORD))(*(_QWORD *)v37 + 32LL);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v38);
  ppv = &v44;
  v16 = v19(v18, pv, &v38, 0);
  v7 = v16;
  if ( v16 < 0 )
  {
    v17 = 2150;
    goto LABEL_12;
  }
  v20 = v38;
  v21 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 40LL);
  v22 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpString2);
  v16 = v21(v20, v22);
  v7 = v16;
  if ( v16 < 0 )
  {
    v17 = 2151;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v16,
      (int)ppv);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v38);
    if ( lpString2 )
      CoTaskMemFree((LPVOID)lpString2);
    goto LABEL_8;
  }
  v23 = a1 + 24;
  AcquireSRWLockShared(a1 + 24);
  v42[0] = a1 + 24;
  v24 = a1 + 25;
  v25 = (LPCWCH *)&a1[26];
  if ( a1[25].Ptr && CompareStringOrdinal(*v25, -1, lpString2, -1, 1) == 2 )
  {
    Microsoft::WRL::ComPtr<IExplorerCommand>::operator=(a3, &a1[25]);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v42);
LABEL_38:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v38);
    if ( lpString2 )
      CoTaskMemFree((LPVOID)lpString2);
    if ( pv )
      CoTaskMemFree(pv);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v36);
    v7 = 0;
    goto LABEL_43;
  }
  if ( a1 != (RTL_SRWLOCK *)-192LL )
    ReleaseSRWLockShared(a1 + 24);
  v26 = v41;
  v27 = *(__int64 (__fastcall **)(LPVOID, LPVOID, GUID *, __int64))(*(_QWORD *)v41 + 24LL);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(a3);
  v28 = v27(v26, pv, &GUID_a08ce4d0_fa25_44ab_b57c_c7b1c323e0b9, a3);
  v29 = v28;
  if ( v28 >= 0 )
  {
    AcquireSRWLockExclusive(v23);
    v42[0] = v23;
    Microsoft::WRL::ComPtr<IExplorerCommand>::operator=(v24, a3);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
      v25,
      &lpString2);
    CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)v42);
    goto LABEL_38;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x873,
    (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
    (const char *)(unsigned int)v28,
    (int)ppv);
  v30 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  if ( lpString2 )
    CoTaskMemFree((LPVOID)lpString2);
  if ( pv )
    CoTaskMemFree(pv);
  v32 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
  }
  return v29;
}

```

## disassembly

```asm
0x1800210dc  push    rbp
0x1800210de  push    rbx
0x1800210df  push    rsi
0x1800210e0  push    rdi
0x1800210e1  push    r12
0x1800210e3  push    r13
0x1800210e5  push    r14
0x1800210e7  push    r15
0x1800210e9  mov     rbp, rsp
0x1800210ec  sub     rsp, 78h
0x1800210f0  mov     r12, r8
0x1800210f3  mov     rdi, rdx
0x1800210f6  mov     rsi, rcx
0x1800210f9  xor     r13d, r13d
0x1800210fc  mov     [rbp+var_20], r13
0x180021100  lea     rcx, [rbp+var_20]
0x180021104  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180021109  lea     rax, [rbp+var_20]
0x18002110d  mov     [rsp+78h+ppv], rax; int
0x180021112  lea     r9, _GUID_9cb181e7_8ea8_49ea_833b_1a2981643682; riid
0x180021119  xor     edx, edx; pUnkOuter
0x18002111b  lea     r8d, [r13+1]; dwClsContext
0x18002111f  lea     rcx, CLSID_SyncRootManager; rclsid
0x180021126  call    cs:__imp_CoCreateInstance
0x18002112c  mov     ebx, eax
0x18002112e  test    eax, eax
0x180021130  jns     short loc_18002114F
0x180021132  mov     rcx, [rbp+40h]; this
0x180021136  mov     r9d, eax; char *
0x180021139  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180021140  mov     edx, 859h; void *
0x180021145  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002114a  jmp     loc_1800214A9
0x18002114f  mov     [rbp+var_48], r13
0x180021153  mov     rax, [rdi]
0x180021156  mov     rbx, [rax+40h]
0x18002115a  lea     rcx, [rbp+var_48]
0x18002115e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180021163  lea     r8, [rbp+var_48]
0x180021167  xor     edx, edx
0x180021169  mov     rcx, rdi
0x18002116c  mov     rax, rbx
0x18002116f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021174  mov     ebx, eax
0x180021176  test    eax, eax
0x180021178  jns     short loc_1800211A1
0x18002117a  mov     rcx, [rbp+40h]; this
0x18002117e  mov     r9d, eax; char *
0x180021181  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180021188  mov     edx, 85Ch; void *
0x18002118d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021192  nop
0x180021193  lea     rcx, [rbp+var_48]
0x180021197  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002119c  jmp     loc_1800214A9
0x1800211a1  mov     [rbp+pv], r13
0x1800211a5  mov     rdi, [rbp+var_48]
0x1800211a9  mov     rax, [rdi]
0x1800211ac  mov     rbx, [rax+28h]
0x1800211b0  lea     rcx, [rbp+pv]
0x1800211b4  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800211b9  mov     r8, rax
0x1800211bc  mov     edx, 80058000h
0x1800211c1  mov     rcx, rdi
0x1800211c4  mov     rax, rbx
0x1800211c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211cc  mov     ebx, eax
0x1800211ce  test    eax, eax
0x1800211d0  jns     short loc_1800211FC
0x1800211d2  mov     rcx, [rbp+40h]; this
0x1800211d6  mov     r9d, eax; char *
0x1800211d9  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x1800211e0  mov     edx, 85Eh; void *
0x1800211e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800211ea  nop
0x1800211eb  mov     rcx, [rbp+pv]; pv
0x1800211ef  test    rcx, rcx
0x1800211f2  jz      short loc_180021193
0x1800211f4  call    cs:__imp_CoTaskMemFree
0x1800211fa  jmp     short loc_180021193
0x1800211fc  mov     [rbp+lpString2], r13
0x180021200  mov     [rbp+var_38], r13
0x180021204  mov     [rbp+arg_18], r13d
0x180021208  mov     [rbp+var_40], r13
0x18002120c  mov     rbx, [rbp+var_20]
0x180021210  mov     rax, [rbx]
0x180021213  mov     rdi, [rax]
0x180021216  lea     rcx, [rbp+var_40]
0x18002121a  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002121f  lea     r8, [rbp+var_40]
0x180021223  lea     rdx, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64
0x18002122a  mov     rcx, rbx
0x18002122d  mov     rax, rdi
0x180021230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021235  mov     ebx, eax
0x180021237  test    eax, eax
0x180021239  jns     short loc_180021280
0x18002123b  mov     edx, 865h; void *
0x180021240  mov     rcx, [rbp+40h]; this
0x180021244  mov     r9d, eax; char *
0x180021247  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18002124e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021253  nop
0x180021254  lea     rcx, [rbp+var_40]
0x180021258  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002125d  nop
0x18002125e  lea     rcx, [rbp+var_38]
0x180021262  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180021267  nop
0x180021268  mov     rcx, [rbp+lpString2]; pv
0x18002126c  test    rcx, rcx
0x18002126f  jz      loc_1800211EB
0x180021275  call    cs:__imp_CoTaskMemFree
0x18002127b  jmp     loc_1800211EB
0x180021280  mov     rdi, [rbp+var_40]
0x180021284  mov     rax, [rdi]
0x180021287  mov     rbx, [rax+20h]
0x18002128b  lea     rcx, [rbp+var_38]
0x18002128f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180021294  lea     rax, [rbp+arg_18]
0x180021298  mov     [rsp+78h+ppv], rax; int
0x18002129d  xor     r9d, r9d
0x1800212a0  lea     r8, [rbp+var_38]
0x1800212a4  mov     rdx, [rbp+pv]
0x1800212a8  mov     rcx, rdi
0x1800212ab  mov     rax, rbx
0x1800212ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212b3  mov     ebx, eax
0x1800212b5  test    eax, eax
0x1800212b7  jns     short loc_1800212C0
0x1800212b9  mov     edx, 866h
0x1800212be  jmp     short loc_180021240
0x1800212c0  mov     rdi, [rbp+var_38]
0x1800212c4  mov     rax, [rdi]
0x1800212c7  mov     rbx, [rax+28h]
0x1800212cb  lea     rcx, [rbp+lpString2]
0x1800212cf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800212d4  mov     rdx, rax
0x1800212d7  mov     rcx, rdi
0x1800212da  mov     rax, rbx
0x1800212dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212e2  mov     ebx, eax
0x1800212e4  test    eax, eax
0x1800212e6  jns     short loc_1800212F2
0x1800212e8  mov     edx, 867h
0x1800212ed  jmp     loc_180021240
0x1800212f2  lea     rbx, [rsi+0C0h]
0x1800212f9  mov     rcx, rbx; SRWLock
0x1800212fc  call    cs:__imp_AcquireSRWLockShared
0x180021302  mov     [rbp+var_18], rbx
0x180021306  lea     r14, [rsi+0C8h]
0x18002130d  lea     r15, [rsi+0D0h]
0x180021314  cmp     [r14], r13
0x180021317  jz      short loc_180021352
0x180021319  mov     dword ptr [rsp+78h+ppv], 1; bIgnoreCase
0x180021321  or      edx, 0FFFFFFFFh; cchCount1
0x180021324  mov     r9d, edx; cchCount2
0x180021327  mov     r8, [rbp+lpString2]; lpString2
0x18002132b  mov     rcx, [r15]; lpString1
0x18002132e  call    cs:__imp_CompareStringOrdinal
0x180021334  cmp     eax, 2
0x180021337  jnz     short loc_180021352
0x180021339  mov     rdx, r14
0x18002133c  mov     rcx, r12
0x18002133f  call    ??4?$ComPtr@UIExplorerCommand@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IExplorerCommand>::operator=(Microsoft::WRL::ComPtr<IExplorerCommand> const &)
0x180021344  lea     rcx, [rbp+var_18]
0x180021348  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002134d  jmp     loc_180021469
0x180021352  test    rbx, rbx
0x180021355  jz      short loc_180021360
0x180021357  mov     rcx, rbx; SRWLock
0x18002135a  call    cs:__imp_ReleaseSRWLockShared
0x180021360  mov     rsi, [rbp+var_20]
0x180021364  mov     rax, [rsi]
0x180021367  mov     rdi, [rax+18h]
0x18002136b  mov     rcx, r12
0x18002136e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180021373  mov     r9, r12
0x180021376  lea     r8, _GUID_a08ce4d0_fa25_44ab_b57c_c7b1c323e0b9
0x18002137d  mov     rdx, [rbp+pv]
0x180021381  mov     rcx, rsi
0x180021384  mov     rax, rdi
0x180021387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002138c  mov     edi, eax
0x18002138e  test    eax, eax
0x180021390  jns     loc_18002143B
0x180021396  mov     rcx, [rbp+40h]; this
0x18002139a  mov     r9d, eax; char *
0x18002139d  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x1800213a4  mov     edx, 873h; void *
0x1800213a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800213ae  nop
0x1800213af  mov     rcx, [rbp+var_40]
0x1800213b3  test    rcx, rcx
0x1800213b6  jz      short loc_1800213C9
0x1800213b8  mov     [rbp+var_40], r13
0x1800213bc  mov     rax, [rcx]
0x1800213bf  mov     rax, [rax+10h]
0x1800213c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213c8  nop
0x1800213c9  mov     rcx, [rbp+var_38]
0x1800213cd  test    rcx, rcx
0x1800213d0  jz      short loc_1800213E3
0x1800213d2  mov     [rbp+var_38], r13
0x1800213d6  mov     rax, [rcx]
0x1800213d9  mov     rax, [rax+10h]
0x1800213dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213e2  nop
0x1800213e3  mov     rcx, [rbp+lpString2]; pv
0x1800213e7  test    rcx, rcx
0x1800213ea  jz      short loc_1800213F3
0x1800213ec  call    cs:__imp_CoTaskMemFree
0x1800213f2  nop
0x1800213f3  mov     rcx, [rbp+pv]; pv
0x1800213f7  test    rcx, rcx
0x1800213fa  jz      short loc_180021403
0x1800213fc  call    cs:__imp_CoTaskMemFree
0x180021402  nop
0x180021403  mov     rcx, [rbp+var_48]
0x180021407  test    rcx, rcx
0x18002140a  jz      short loc_18002141D
0x18002140c  mov     [rbp+var_48], r13
0x180021410  mov     rax, [rcx]
0x180021413  mov     rax, [rax+10h]
0x180021417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002141c  nop
0x18002141d  mov     rcx, [rbp+var_20]
0x180021421  test    rcx, rcx
0x180021424  jz      short loc_180021437
0x180021426  mov     [rbp+var_20], r13
0x18002142a  mov     rax, [rcx]
0x18002142d  mov     rax, [rax+10h]
0x180021431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021436  nop
0x180021437  mov     eax, edi
0x180021439  jmp     short loc_1800214B4
0x18002143b  mov     rcx, rbx; SRWLock
0x18002143e  call    cs:__imp_AcquireSRWLockExclusive
0x180021444  mov     [rbp+var_18], rbx
0x180021448  mov     rdx, r12
0x18002144b  mov     rcx, r14
0x18002144e  call    ??4?$ComPtr@UIExplorerCommand@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IExplorerCommand>::operator=(Microsoft::WRL::ComPtr<IExplorerCommand> const &)
0x180021453  lea     rdx, [rbp+lpString2]
0x180021457  mov     rcx, r15
0x18002145a  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002145f  lea     rcx, [rbp+var_18]; this
0x180021463  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x180021468  nop
0x180021469  lea     rcx, [rbp+var_40]
0x18002146d  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180021472  nop
0x180021473  lea     rcx, [rbp+var_38]
0x180021477  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002147c  nop
0x18002147d  mov     rcx, [rbp+lpString2]; pv
0x180021481  test    rcx, rcx
0x180021484  jz      short loc_18002148D
0x180021486  call    cs:__imp_CoTaskMemFree
0x18002148c  nop
0x18002148d  mov     rcx, [rbp+pv]; pv
0x180021491  test    rcx, rcx
0x180021494  jz      short loc_18002149D
0x180021496  call    cs:__imp_CoTaskMemFree
0x18002149c  nop
0x18002149d  lea     rcx, [rbp+var_48]
0x1800214a1  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800214a6  mov     ebx, r13d
0x1800214a9  lea     rcx, [rbp+var_20]
0x1800214ad  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800214b2  mov     eax, ebx
0x1800214b4  add     rsp, 78h
0x1800214b8  pop     r15
0x1800214ba  pop     r14
0x1800214bc  pop     r13
0x1800214be  pop     r12
0x1800214c0  pop     rdi
0x1800214c1  pop     rsi
0x1800214c2  pop     rbx
0x1800214c3  pop     rbp
0x1800214c4  retn
```

# CInplaceShareEngine::_GetUncPath(ushort const *,ushort *,ulong)

- ea: `0x180008f68`
- end: `0x180009339`
- name: `?_GetUncPath@CInplaceShareEngine@@AEAAJPEBGPEAGK@Z`
- size: `977`
- prototype: `int(CInplaceShareEngine *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800093d0`
- `0x18000d380`
- `0x1800567a0`
- `0x18005c1d0`

## callees

- `0x180008750`
- `0x180008900`
- `0x180008f68`
- `0x180009340`
- `0x18001d18c`
- `0x1800214cc`
- `0x1800254e0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180008fb6`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180008fd1`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180008fb6`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180008fd1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000903e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000903e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000917d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000929e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009307`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000917d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000929e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009307`
- `SHELL32!__imp_PathComparePaths` at `0x180008feb`
- `SHELL32!__imp_PathComparePaths` at `0x180008feb`

## string_xrefs

- `0x180009054`: `shell\osshell\lmui\ntshrui\dll\shrengine.cpp`
- `0x18000915f`: `shell\osshell\lmui\ntshrui\dll\shrengine.cpp`
- `0x180009223`: `shell\osshell\lmui\ntshrui\dll\shrengine.cpp`
- `0x180009280`: `shell\osshell\lmui\ntshrui\dll\shrengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CInplaceShareEngine::_GetUncPath(
        CInplaceShareEngine *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  _QWORD *v6; // rbx
  HRESULT Instance; // eax
  int v8; // ebx
  LPVOID v9; // rcx
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, __int64, LPVOID *); // rbx
  LPVOID v13; // rcx
  LPVOID v14; // rcx
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, __int64); // rbx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  LPVOID v20; // rdi
  __int64 (__fastcall *v21)(LPVOID, __int64); // rbx
  __int64 v22; // rax
  LPVOID v23; // rdx
  int v24; // eax
  __int64 *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  LPVOID *ppvb; // [rsp+20h] [rbp-E0h]
  LPVOID v31; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v33[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v34[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  if ( PathCchCanonicalize(pszPathOut, 0x104u, (PCWSTR)this + 556) < 0
    || PathCchCanonicalize(v34, 0x104u, a2) < 0
    || (PathComparePaths(pszPathOut, v34) & 8) == 0 )
  {
    v31 = 0;
    pv = 0;
    v25 = (__int64 *)*((_QWORD *)this + 8);
    v26 = *v25;
    pv = 0;
    v31 = 0;
    ppvb = &pv;
    v8 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, _QWORD, LPVOID *))(v26 + 72))(v25, a2, 0, &v31);
    if ( v8 >= 0 )
    {
      LODWORD(ppvb) = (_DWORD)pv;
      v8 = StringCchPrintfW(a3, 0x104u, L"\\\\%s\\%s", v31);
      if ( v8 >= 0 )
      {
        if ( pv )
          CoTaskMemFree(pv);
        if ( v31 )
          CoTaskMemFree(v31);
        return 0;
      }
      v27 = 1485;
    }
    else
    {
      v27 = 1484;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shrengine.cpp",
      (const char *)(unsigned int)v8,
      (int)ppvb);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v31 )
      CoTaskMemFree(v31);
    return (unsigned int)v8;
  }
  if ( *((_QWORD *)this + 205) )
  {
    v6 = (_QWORD *)((char *)this + 1632);
    goto LABEL_26;
  }
  v33[0] = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v33);
  Instance = CoCreateInstance(
               &CLSID_SharingConfigurationManager,
               0,
               1u,
               &GUID_a4341687_7593_47aa_9554_4b0ffc8b2214,
               v33);
  v8 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BB,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shrengine.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    v9 = v33[0];
    if ( v33[0] )
    {
      v33[0] = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return (unsigned int)v8;
  }
  v31 = 0;
  v11 = v33[0];
  v12 = *(__int64 (__fastcall **)(LPVOID, __int64, LPVOID *))(*(_QWORD *)v33[0] + 24LL);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v31);
  v8 = v12(v11, 1, &v31);
  if ( v8 < 0 )
  {
    v13 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v33[0];
    if ( v33[0] )
    {
      v33[0] = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)v8;
  }
  pv = 0;
  v15 = v31;
  v16 = *(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v31 + 80LL);
  v17 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  v18 = v16(v15, v17);
  v8 = v18;
  if ( v18 < 0 )
  {
    v19 = 1473;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shrengine.cpp",
      (const char *)(unsigned int)v18,
      ppv);
    if ( pv )
      CoTaskMemFree(pv);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v33);
    return (unsigned int)v8;
  }
  v20 = v31;
  v21 = *(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v31 + 32LL);
  v22 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put((char *)this + 1640);
  v18 = v21(v20, v22);
  v8 = v18;
  if ( v18 < 0 )
  {
    v19 = 1474;
    goto LABEL_20;
  }
  v23 = pv;
  pv = 0;
  v6 = (_QWORD *)((char *)this + 1632);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (char *)this + 1632,
    v23);
  if ( pv )
    CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v33);
LABEL_26:
  v24 = StringCchPrintfW(a3, 0x104u, L"\\\\%s\\%s%s", *v6, *((_QWORD *)this + 205), &a2[*((unsigned int *)this + 412)]);
  v8 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C6,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shrengine.cpp",
      (const char *)(unsigned int)v24,
      ppva);
    return (unsigned int)v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180008f68  mov     [rsp-8+arg_18], rbx
0x180008f6d  push    rbp
0x180008f6e  push    rsi
0x180008f6f  push    rdi
0x180008f70  push    r12
0x180008f72  push    r13
0x180008f74  push    r14
0x180008f76  push    r15
0x180008f78  lea     rbp, [rsp-380h]
0x180008f80  sub     rsp, 480h
0x180008f87  mov     rax, cs:__security_cookie
0x180008f8e  xor     rax, rsp
0x180008f91  mov     [rbp+3B0h+var_40], rax
0x180008f98  mov     r12, r8
0x180008f9b  mov     r15, rdx
0x180008f9e  mov     rsi, rcx
0x180008fa1  lea     r8, [rcx+458h]; pszPathIn
0x180008fa8  mov     edi, 104h
0x180008fad  mov     edx, edi; cchPathOut
0x180008faf  lea     rcx, [rbp+3B0h+pszPathOut]; pszPathOut
0x180008fb6  call    cs:__imp_PathCchCanonicalize
0x180008fbc  xor     r13d, r13d
0x180008fbf  test    eax, eax
0x180008fc1  js      loc_180009239
0x180008fc7  mov     r8, r15; pszPathIn
0x180008fca  mov     edx, edi; cchPathOut
0x180008fcc  lea     rcx, [rsp+4B0h+var_460]; pszPathOut
0x180008fd1  call    cs:__imp_PathCchCanonicalize
0x180008fd7  test    eax, eax
0x180008fd9  js      loc_180009239
0x180008fdf  lea     rdx, [rsp+4B0h+var_460]
0x180008fe4  lea     rcx, [rbp+3B0h+pszPathOut]
0x180008feb  call    cs:__imp_PathComparePaths
0x180008ff1  test    al, 8
0x180008ff3  jz      loc_180009239
0x180008ff9  lea     r14, [rsi+668h]
0x180009000  cmp     [r14], r13
0x180009003  jz      short loc_180009011
0x180009005  lea     rbx, [rsi+660h]
0x18000900c  jmp     loc_1800091E3
0x180009011  mov     [rsp+4B0h+var_470], r13
0x180009016  lea     rcx, [rsp+4B0h+var_470]
0x18000901b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180009020  lea     rax, [rsp+4B0h+var_470]
0x180009025  mov     [rsp+4B0h+ppv], rax; int
0x18000902a  lea     r9, _GUID_a4341687_7593_47aa_9554_4b0ffc8b2214; riid
0x180009031  xor     edx, edx; pUnkOuter
0x180009033  lea     r8d, [rdx+1]; dwClsContext
0x180009037  lea     rcx, CLSID_SharingConfigurationManager; rclsid
0x18000903e  call    cs:__imp_CoCreateInstance
0x180009044  mov     ebx, eax
0x180009046  test    eax, eax
0x180009048  jns     short loc_180009089
0x18000904a  mov     rcx, [rbp+3B8h]; this
0x180009051  mov     r9d, eax; char *
0x180009054  lea     r8, aShellOsshellLm; "shell\\osshell\\lmui\\ntshrui\\dll\\shr"...
0x18000905b  mov     edx, 5BBh; void *
0x180009060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009065  nop
0x180009066  mov     rcx, [rsp+4B0h+var_470]
0x18000906b  test    rcx, rcx
0x18000906e  jz      short loc_180009082
0x180009070  mov     [rsp+4B0h+var_470], r13
0x180009075  mov     rax, [rcx]
0x180009078  mov     rax, [rax+10h]
0x18000907c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009081  nop
0x180009082  mov     eax, ebx
0x180009084  jmp     loc_18000930F
0x180009089  mov     [rsp+4B0h+var_480], r13
0x18000908e  mov     rdi, [rsp+4B0h+var_470]
0x180009093  mov     rax, [rdi]
0x180009096  mov     rbx, [rax+18h]
0x18000909a  lea     rcx, [rsp+4B0h+var_480]
0x18000909f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800090a4  lea     r8, [rsp+4B0h+var_480]
0x1800090a9  mov     edx, 1
0x1800090ae  mov     rcx, rdi
0x1800090b1  mov     rax, rbx
0x1800090b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090b9  mov     ebx, eax
0x1800090bb  test    eax, eax
0x1800090bd  jns     short loc_1800090F9
0x1800090bf  mov     rcx, [rsp+4B0h+var_480]
0x1800090c4  test    rcx, rcx
0x1800090c7  jz      short loc_1800090DB
0x1800090c9  mov     [rsp+4B0h+var_480], r13
0x1800090ce  mov     rdx, [rcx]
0x1800090d1  mov     rax, [rdx+10h]
0x1800090d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090da  nop
0x1800090db  mov     rcx, [rsp+4B0h+var_470]
0x1800090e0  test    rcx, rcx
0x1800090e3  jz      short loc_1800090F7
0x1800090e5  mov     [rsp+4B0h+var_470], r13
0x1800090ea  mov     rax, [rcx]
0x1800090ed  mov     rax, [rax+10h]
0x1800090f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f6  nop
0x1800090f7  jmp     short loc_180009082
0x1800090f9  mov     [rsp+4B0h+pv], r13
0x1800090fe  mov     rdi, [rsp+4B0h+var_480]
0x180009103  mov     rax, [rdi]
0x180009106  mov     rbx, [rax+50h]
0x18000910a  lea     rcx, [rsp+4B0h+pv]
0x18000910f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180009114  mov     rdx, rax
0x180009117  mov     rcx, rdi
0x18000911a  mov     rax, rbx
0x18000911d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009122  mov     ebx, eax
0x180009124  test    eax, eax
0x180009126  jns     short loc_18000912F
0x180009128  mov     edx, 5C1h
0x18000912d  jmp     short loc_18000915C
0x18000912f  mov     rdi, [rsp+4B0h+var_480]
0x180009134  mov     rax, [rdi]
0x180009137  mov     rbx, [rax+20h]
0x18000913b  mov     rcx, r14
0x18000913e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180009143  mov     rdx, rax
0x180009146  mov     rcx, rdi
0x180009149  mov     rax, rbx
0x18000914c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009151  mov     ebx, eax
0x180009153  test    eax, eax
0x180009155  jns     short loc_18000919E
0x180009157  mov     edx, 5C2h; void *
0x18000915c  mov     r9d, eax; char *
0x18000915f  lea     r8, aShellOsshellLm; "shell\\osshell\\lmui\\ntshrui\\dll\\shr"...
0x180009166  mov     rcx, [rbp+3B8h]; this
0x18000916d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009172  nop
0x180009173  mov     rcx, [rsp+4B0h+pv]; pv
0x180009178  test    rcx, rcx
0x18000917b  jz      short loc_180009184
0x18000917d  call    cs:__imp_CoTaskMemFree
0x180009183  nop
0x180009184  lea     rcx, [rsp+4B0h+var_480]
0x180009189  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000918e  nop
0x18000918f  lea     rcx, [rsp+4B0h+var_470]
0x180009194  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180009199  jmp     loc_180009082
0x18000919e  mov     rdx, [rsp+4B0h+pv]
0x1800091a3  mov     [rsp+4B0h+pv], r13
0x1800091a8  lea     rbx, [rsi+660h]
0x1800091af  mov     rcx, rbx
0x1800091b2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800091b7  nop
0x1800091b8  mov     rcx, [rsp+4B0h+pv]; pv
0x1800091bd  test    rcx, rcx
0x1800091c0  jz      short loc_1800091C9
0x1800091c2  call    cs:__imp_CoTaskMemFree
0x1800091c8  nop
0x1800091c9  lea     rcx, [rsp+4B0h+var_480]
0x1800091ce  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800091d3  nop
0x1800091d4  lea     rcx, [rsp+4B0h+var_470]
0x1800091d9  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800091de  mov     edi, 104h
0x1800091e3  mov     eax, [rsi+670h]
0x1800091e9  lea     rdx, [r15+rax*2]
0x1800091ed  mov     [rsp+4B0h+var_488], rdx
0x1800091f2  mov     rax, [r14]
0x1800091f5  mov     [rsp+4B0h+ppv], rax; int
0x1800091fa  mov     r9, [rbx]
0x1800091fd  lea     r8, aSSS; "\\\\%s\\%s%s"
0x180009204  mov     rdx, rdi; unsigned __int64
0x180009207  mov     rcx, r12; unsigned __int16 *
0x18000920a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000920f  mov     ebx, eax
0x180009211  test    eax, eax
0x180009213  jns     loc_18000930D
0x180009219  mov     rcx, [rbp+3B8h]; this
0x180009220  mov     r9d, eax; char *
0x180009223  lea     r8, aShellOsshellLm; "shell\\osshell\\lmui\\ntshrui\\dll\\shr"...
0x18000922a  mov     edx, 5C6h; void *
0x18000922f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009234  jmp     loc_180009082
0x180009239  mov     [rsp+4B0h+var_480], r13
0x18000923e  mov     [rsp+4B0h+pv], r13
0x180009243  mov     rcx, [rsi+40h]
0x180009247  mov     rax, [rcx]
0x18000924a  mov     [rsp+4B0h+pv], r13
0x18000924f  mov     [rsp+4B0h+var_480], r13
0x180009254  lea     r8, [rsp+4B0h+pv]
0x180009259  mov     [rsp+4B0h+ppv], r8; int
0x18000925e  lea     r9, [rsp+4B0h+var_480]
0x180009263  xor     r8d, r8d
0x180009266  mov     rdx, r15
0x180009269  mov     rax, [rax+48h]
0x18000926d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009272  mov     ebx, eax
0x180009274  test    eax, eax
0x180009276  jns     short loc_1800092BE
0x180009278  mov     edx, 5CCh; void *
0x18000927d  mov     r9d, ebx; char *
0x180009280  lea     r8, aShellOsshellLm; "shell\\osshell\\lmui\\ntshrui\\dll\\shr"...
0x180009287  mov     rcx, [rbp+3B8h]; this
0x18000928e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009293  nop
0x180009294  mov     rcx, [rsp+4B0h+pv]; pv
0x180009299  test    rcx, rcx
0x18000929c  jz      short loc_1800092A5
0x18000929e  call    cs:__imp_CoTaskMemFree
0x1800092a4  nop
0x1800092a5  mov     rcx, [rsp+4B0h+var_480]; pv
0x1800092aa  test    rcx, rcx
0x1800092ad  jz      loc_180009082
0x1800092b3  call    cs:__imp_CoTaskMemFree
0x1800092b9  jmp     loc_180009082
0x1800092be  mov     rax, [rsp+4B0h+pv]
0x1800092c3  mov     [rsp+4B0h+ppv], rax
0x1800092c8  mov     r9, [rsp+4B0h+var_480]
0x1800092cd  lea     r8, aSS_0; "\\\\%s\\%s"
0x1800092d4  mov     rdx, rdi; unsigned __int64
0x1800092d7  mov     rcx, r12; unsigned __int16 *
0x1800092da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800092df  mov     ebx, eax
0x1800092e1  test    eax, eax
0x1800092e3  jns     short loc_1800092EC
0x1800092e5  mov     edx, 5CDh
0x1800092ea  jmp     short loc_18000927D
0x1800092ec  mov     rcx, [rsp+4B0h+pv]; pv
0x1800092f1  test    rcx, rcx
0x1800092f4  jz      short loc_1800092FD
0x1800092f6  call    cs:__imp_CoTaskMemFree
0x1800092fc  nop
0x1800092fd  mov     rcx, [rsp+4B0h+var_480]; pv
0x180009302  test    rcx, rcx
0x180009305  jz      short loc_18000930D
0x180009307  call    cs:__imp_CoTaskMemFree
0x18000930d  xor     eax, eax
0x18000930f  mov     rcx, [rbp+3B0h+var_40]
0x180009316  xor     rcx, rsp; StackCookie
0x180009319  call    __security_check_cookie
0x18000931e  mov     rbx, [rsp+4B0h+arg_18]
0x180009326  add     rsp, 480h
0x18000932d  pop     r15
0x18000932f  pop     r14
0x180009331  pop     r13
0x180009333  pop     r12
0x180009335  pop     rdi
0x180009336  pop     rsi
0x180009337  pop     rbp
0x180009338  retn
```

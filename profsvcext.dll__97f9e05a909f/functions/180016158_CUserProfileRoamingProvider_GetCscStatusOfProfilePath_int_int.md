# CUserProfileRoamingProvider::_GetCscStatusOfProfilePath(int *,int *)

- ea: `0x180016158`
- end: `0x1800165e8`
- name: `?_GetCscStatusOfProfilePath@CUserProfileRoamingProvider@@AEAAJPEAH0@Z`
- size: `1168`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this, int *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180016a1c`

## callees

- `0x180006a80`
- `0x180006a9c`
- `0x18000927c`
- `0x18001134c`
- `0x180013a20`
- `0x180013aac`
- `0x180016158`
- `0x180016df8`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016226`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016226`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800161b8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800161b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001625e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016316`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800165c3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001625e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016316`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800165c3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18001632e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180016385`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18001632e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180016385`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18001633c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18001633c`

## string_xrefs

- `0x1800161dd`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180016239`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800162eb`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800163bd`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180016401`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180016443`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180016529`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserProfileRoamingProvider::_GetCscStatusOfProfilePath(
        CUserProfileRoamingProvider *this,
        int *a2,
        int *a3)
{
  void *v6; // rax
  int v7; // eax
  HRESULT v8; // ebx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  bool v11; // si
  HRESULT v12; // eax
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, __int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 v15; // rax
  CUserProfileRoamingProvider *v16; // rcx
  const unsigned __int16 *v17; // rax
  int v18; // eax
  HRESULT v19; // edi
  WCHAR *v20; // rdi
  CUserProfileRoamingProvider *v21; // rcx
  LPVOID v22; // rbx
  __int64 (__fastcall *v23)(LPVOID, WCHAR *, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // r15
  __int64 (__fastcall ***v24)(_QWORD, GUID *, _QWORD *); // rcx
  CUserProfileRoamingProvider *v25; // rcx
  int IsNotFoundError; // eax
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  void *v32; // rax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rdx
  int v36; // ecx
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  int v40; // [rsp+30h] [rbp-48h] BYREF
  __int64 (__fastcall ***v41)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-40h] BYREF
  LPVOID v42; // [rsp+40h] [rbp-38h] BYREF
  __int64 v43; // [rsp+48h] [rbp-30h] BYREF
  __int64 v44; // [rsp+50h] [rbp-28h] BYREF
  __int64 v45; // [rsp+58h] [rbp-20h] BYREF
  char v46; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  BOOL v48; // [rsp+C8h] [rbp+50h] BYREF
  LPWSTR pszPath; // [rsp+D0h] [rbp+58h] BYREF
  int v50; // [rsp+D8h] [rbp+60h] BYREF

  *a2 = 0;
  *a3 = 0;
  v45 = 0;
  v46 = 0;
  v6 = (void *)(***((__int64 (__fastcall ****)(_QWORD))this + 1))(*((_QWORD *)this + 1));
  v7 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v45, v6);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = (unsigned int)v7;
    v10 = 1273;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)v9,
      ppv);
    goto LABEL_57;
  }
  v8 = CoInitializeEx(0, 4u);
  if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147417850 )
  {
    v9 = (unsigned int)v8;
    v10 = 1276;
    goto LABEL_6;
  }
  v11 = v8 != -2147417850;
  v48 = v8 != -2147417850;
  v42 = 0;
  v12 = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 1u, &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5, &v42);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x506,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v12,
      ppva);
    goto LABEL_9;
  }
  v41 = 0;
  v13 = v42;
  v14 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v42 + 80LL);
  v41 = 0;
  v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1));
  v8 = v14(v13, v15, 2, &v41);
  if ( !(unsigned int)CUserProfileRoamingProvider::_IsNotFoundError(v16, v8) )
  {
    if ( v8 < 0 )
    {
      v27 = (unsigned int)v8;
      v28 = 1333;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)v27,
        ppva);
      goto LABEL_25;
    }
    v43 = 0;
    v29 = (**v41)(v41, &GUID_623c58a2_42ed_4ad7_b69a_0f1b30a72d0d, &v43);
    v8 = v29;
    if ( v29 >= 0 )
    {
      LODWORD(pszPath) = 0;
      v29 = (*(__int64 (__fastcall **)(__int64, LPWSTR *))(*(_QWORD *)v43 + 24LL))(v43, &pszPath);
      v8 = v29;
      if ( v29 >= 0 )
      {
        v50 = 0;
        v29 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 64LL))(v43, &v50);
        v8 = v29;
        if ( v29 >= 0 )
        {
          if ( (_DWORD)pszPath || (v31 = 0, v50) )
            v31 = 1;
          *a2 = v31;
          wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v43);
          goto LABEL_41;
        }
        v30 = 1343;
      }
      else
      {
        v30 = 1340;
      }
    }
    else
    {
      v30 = 1337;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v29,
      ppva);
    wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v43);
    goto LABEL_25;
  }
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v45);
  pszPath = 0;
  v17 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1));
  v18 = HeapDupStr(v17, &pszPath);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x521,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v18,
      ppva);
    wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v41);
    wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v42);
    if ( v11 )
      CoUninitialize();
    v8 = v19;
    goto LABEL_57;
  }
  v20 = pszPath;
  PathRemoveFileSpecW(pszPath);
  do
  {
    if ( PathIsUNCServerW(v20) )
      break;
    v22 = v42;
    v23 = *(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v42 + 80LL);
    v24 = v41;
    v41 = 0;
    if ( v24 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v24)[2])(v24);
    v8 = v23(v22, v20, 0x80000000LL, &v41);
    PathRemoveFileSpecW(v20);
  }
  while ( (unsigned int)CUserProfileRoamingProvider::_IsNotFoundError(v25, v8) );
  IsNotFoundError = CUserProfileRoamingProvider::_IsNotFoundError(v21, v8);
  v11 = v48;
  if ( !IsNotFoundError )
  {
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x531,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v8,
        ppva);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
LABEL_25:
      wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v41);
LABEL_9:
      wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v42);
      if ( v11 )
        CoUninitialize();
      goto LABEL_57;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
LABEL_41:
    if ( !v41 )
      goto LABEL_54;
    v32 = (void *)(***((__int64 (__fastcall ****)(_QWORD))this + 1))(*((_QWORD *)this + 1));
    v33 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v45, v32);
    v8 = v33;
    if ( v33 < 0 )
    {
      v27 = (unsigned int)v33;
      v28 = 1353;
      goto LABEL_29;
    }
    v44 = 0;
    v34 = (**v41)(v41, &GUID_efb23a09_a867_4be8_83a6_86969a7d0856, &v44);
    v8 = v34;
    if ( v34 < 0 )
    {
      v35 = 1356;
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v34,
        ppva);
      wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v44);
      goto LABEL_25;
    }
    v48 = 0;
    v40 = 0;
    v34 = (*(__int64 (__fastcall **)(__int64, BOOL *, int *))(*(_QWORD *)v44 + 24LL))(v44, &v48, &v40);
    v8 = v34;
    if ( v34 == -2147020546 || v34 == -2147024891 )
    {
      v36 = 1;
      v48 = 1;
    }
    else
    {
      if ( v34 < 0 )
      {
        v35 = 1375;
        goto LABEL_46;
      }
      v36 = v48;
    }
    *a3 = v36 == 1;
    wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v44);
    goto LABEL_54;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
LABEL_54:
  wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v41);
  wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v42);
  if ( v11 )
    CoUninitialize();
  v8 = 0;
LABEL_57:
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v45);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016158  push    rbp
0x18001615a  push    rbx
0x18001615b  push    rsi
0x18001615c  push    rdi
0x18001615d  push    r12
0x18001615f  push    r13
0x180016161  push    r14
0x180016163  push    r15
0x180016165  mov     rbp, rsp
0x180016168  sub     rsp, 78h
0x18001616c  mov     r12, r8
0x18001616f  mov     r15, rdx
0x180016172  mov     r14, rcx
0x180016175  xor     r13d, r13d
0x180016178  mov     [rdx], r13d
0x18001617b  mov     [r8], r13d
0x18001617e  mov     [rbp+var_20], r13
0x180016182  mov     [rbp+var_18], r13b
0x180016186  mov     rcx, [rcx+8]
0x18001618a  mov     rax, [rcx]
0x18001618d  mov     rax, [rax]
0x180016190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016195  mov     rdx, rax; void *
0x180016198  lea     rcx, [rbp+var_20]; this
0x18001619c  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x1800161a1  mov     ebx, eax
0x1800161a3  test    eax, eax
0x1800161a5  jns     short loc_1800161B1
0x1800161a7  mov     r9d, eax
0x1800161aa  mov     edx, 4F9h
0x1800161af  jmp     short loc_1800161DD
0x1800161b1  mov     edx, 4; dwCoInit
0x1800161b6  xor     ecx, ecx; pvReserved
0x1800161b8  call    cs:__imp_CoInitializeEx
0x1800161be  mov     ebx, eax
0x1800161c0  mov     eax, 80000000h
0x1800161c5  lea     ecx, [rbx+rax]
0x1800161c8  mov     edx, 80010106h
0x1800161cd  test    eax, ecx
0x1800161cf  jnz     short loc_1800161F2
0x1800161d1  cmp     ebx, edx
0x1800161d3  jz      short loc_1800161F2
0x1800161d5  mov     r9d, ebx; char *
0x1800161d8  mov     edx, 4FCh; void *
0x1800161dd  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800161e4  mov     rcx, [rbp+40h]; this
0x1800161e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800161ed  jmp     loc_1800165CC
0x1800161f2  mov     ecx, 1
0x1800161f7  mov     esi, ecx
0x1800161f9  cmp     ebx, edx
0x1800161fb  cmovz   esi, r13d
0x1800161ff  mov     [rbp+arg_8], esi
0x180016202  mov     [rbp+arg_0], sil
0x180016206  mov     [rbp+var_38], r13
0x18001620a  lea     rax, [rbp+var_38]
0x18001620e  mov     qword ptr [rsp+78h+ppv], rax; int
0x180016213  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x18001621a  mov     r8d, ecx; dwClsContext
0x18001621d  xor     edx, edx; pUnkOuter
0x18001621f  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x180016226  call    cs:__imp_CoCreateInstance
0x18001622c  mov     ebx, eax
0x18001622e  test    eax, eax
0x180016230  jns     short loc_180016269
0x180016232  mov     rcx, [rbp+40h]; this
0x180016236  mov     r9d, eax; char *
0x180016239  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180016240  mov     edx, 506h; void *
0x180016245  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001624a  nop
0x18001624b  lea     rcx, [rbp+var_38]
0x18001624f  call    ??1?$com_ptr_t@UIOfflineFilesCache@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(void)
0x180016254  nop
0x180016255  test    sil, sil
0x180016258  jz      loc_1800165CC
0x18001625e  call    cs:__imp_CoUninitialize
0x180016264  jmp     loc_1800165CC
0x180016269  mov     [rbp+var_40], r13
0x18001626d  mov     rdi, [rbp+var_38]
0x180016271  mov     rax, [rdi]
0x180016274  mov     rbx, [rax+50h]
0x180016278  mov     [rbp+var_40], r13
0x18001627c  mov     rcx, [r14+8]
0x180016280  mov     rdx, [rcx]
0x180016283  mov     rax, [rdx+38h]
0x180016287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001628c  lea     r9, [rbp+var_40]
0x180016290  mov     r8d, 2
0x180016296  mov     rdx, rax
0x180016299  mov     rcx, rdi
0x18001629c  mov     rax, rbx
0x18001629f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162a4  mov     ebx, eax
0x1800162a6  mov     edx, eax; int
0x1800162a8  call    ?_IsNotFoundError@CUserProfileRoamingProvider@@AEAAHJ@Z; CUserProfileRoamingProvider::_IsNotFoundError(long)
0x1800162ad  test    eax, eax
0x1800162af  jz      loc_1800163F5
0x1800162b5  lea     rcx, [rbp+var_20]; this
0x1800162b9  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800162be  mov     [rbp+pszPath], r13
0x1800162c2  mov     rcx, [r14+8]
0x1800162c6  mov     rax, [rcx]
0x1800162c9  mov     rax, [rax+38h]
0x1800162cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162d2  mov     rcx, rax; unsigned __int16 *
0x1800162d5  lea     rdx, [rbp+pszPath]; unsigned __int16 **
0x1800162d9  call    ?HeapDupStr@@YAJPEBGPEAPEAG@Z; HeapDupStr(ushort const *,ushort * *)
0x1800162de  mov     edi, eax
0x1800162e0  test    eax, eax
0x1800162e2  jns     short loc_180016323
0x1800162e4  mov     rcx, [rbp+40h]; this
0x1800162e8  mov     r9d, eax; char *
0x1800162eb  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800162f2  mov     edx, 521h; void *
0x1800162f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800162fc  nop
0x1800162fd  lea     rcx, [rbp+var_40]
0x180016301  call    ??1?$com_ptr_t@UIOfflineFilesCache@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(void)
0x180016306  nop
0x180016307  lea     rcx, [rbp+var_38]
0x18001630b  call    ??1?$com_ptr_t@UIOfflineFilesCache@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(void)
0x180016310  nop
0x180016311  test    sil, sil
0x180016314  jz      short loc_18001631C
0x180016316  call    cs:__imp_CoUninitialize
0x18001631c  mov     ebx, edi
0x18001631e  jmp     loc_1800165CC
0x180016323  mov     rdi, [rbp+pszPath]
0x180016327  mov     [rbp+pszPath], rdi
0x18001632b  mov     rcx, rdi; pszPath
0x18001632e  call    cs:__imp_PathRemoveFileSpecW
0x180016334  mov     esi, 80000000h
0x180016339  mov     rcx, rdi; pszPath
0x18001633c  call    cs:__imp_PathIsUNCServerW
0x180016342  test    eax, eax
0x180016344  jnz     short loc_180016396
0x180016346  mov     rbx, [rbp+var_38]
0x18001634a  mov     rax, [rbx]
0x18001634d  mov     r15, [rax+50h]
0x180016351  mov     rcx, [rbp+var_40]
0x180016355  mov     [rbp+var_40], r13
0x180016359  test    rcx, rcx
0x18001635c  jz      short loc_18001636B
0x18001635e  mov     rdx, [rcx]
0x180016361  mov     rax, [rdx+10h]
0x180016365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001636a  nop
0x18001636b  lea     r9, [rbp+var_40]
0x18001636f  mov     r8d, esi
0x180016372  mov     rdx, rdi
0x180016375  mov     rcx, rbx
0x180016378  mov     rax, r15
0x18001637b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016380  mov     ebx, eax
0x180016382  mov     rcx, rdi; pszPath
0x180016385  call    cs:__imp_PathRemoveFileSpecW
0x18001638b  mov     edx, ebx; int
0x18001638d  call    ?_IsNotFoundError@CUserProfileRoamingProvider@@AEAAHJ@Z; CUserProfileRoamingProvider::_IsNotFoundError(long)
0x180016392  test    eax, eax
0x180016394  jnz     short loc_180016339
0x180016396  mov     edx, ebx; int
0x180016398  call    ?_IsNotFoundError@CUserProfileRoamingProvider@@AEAAHJ@Z; CUserProfileRoamingProvider::_IsNotFoundError(long)
0x18001639d  test    eax, eax
0x18001639f  mov     esi, [rbp+arg_8]
0x1800163a2  jz      short loc_1800163B2
0x1800163a4  lea     rcx, [rbp+pszPath]
0x1800163a8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800163ad  jmp     loc_1800165AA
0x1800163b2  test    ebx, ebx
0x1800163b4  jns     short loc_1800163E7
0x1800163b6  mov     rcx, [rbp+40h]; this
0x1800163ba  mov     r9d, ebx; char *
0x1800163bd  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800163c4  mov     edx, 531h; void *
0x1800163c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800163ce  nop
0x1800163cf  lea     rcx, [rbp+pszPath]
0x1800163d3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800163d8  nop
0x1800163d9  lea     rcx, [rbp+var_40]
0x1800163dd  call    ??1?$com_ptr_t@UIOfflineFilesCache@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(void)
0x1800163e2  jmp     loc_18001624B
0x1800163e7  lea     rcx, [rbp+pszPath]
0x1800163eb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800163f0  jmp     loc_1800164C8
0x1800163f5  test    ebx, ebx
0x1800163f7  jns     short loc_180016413
0x1800163f9  mov     r9d, ebx; char *
0x1800163fc  mov     edx, 535h; void *
0x180016401  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180016408  mov     rcx, [rbp+40h]; this
0x18001640c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016411  jmp     short loc_1800163D9
0x180016413  mov     [rbp+var_30], r13
0x180016417  mov     rcx, [rbp+var_40]
0x18001641b  mov     rax, [rcx]
0x18001641e  lea     r8, [rbp+var_30]
0x180016422  lea     rdx, _GUID_623c58a2_42ed_4ad7_b69a_0f1b30a72d0d
0x180016429  mov     rax, [rax]
0x18001642c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016431  mov     ebx, eax
0x180016433  test    eax, eax
0x180016435  jns     short loc_18001645E
0x180016437  mov     edx, 539h; void *
0x18001643c  mov     rcx, [rbp+40h]; this
0x180016440  mov     r9d, eax; char *
0x180016443  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x18001644a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001644f  nop
0x180016450  lea     rcx, [rbp+var_30]
0x180016454  call    ??1?$com_ptr_t@UIOfflineFilesCache@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(void)
0x180016459  jmp     loc_1800163D9
0x18001645e  mov     dword ptr [rbp+pszPath], r13d
0x180016462  mov     rcx, [rbp+var_30]
0x180016466  mov     rax, [rcx]
0x180016469  lea     rdx, [rbp+pszPath]
0x18001646d  mov     rax, [rax+18h]
0x180016471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016476  mov     ebx, eax
0x180016478  test    eax, eax
0x18001647a  jns     short loc_180016483
0x18001647c  mov     edx, 53Ch
0x180016481  jmp     short loc_18001643C
0x180016483  mov     [rbp+arg_18], r13d
0x180016487  mov     rcx, [rbp+var_30]
0x18001648b  mov     rax, [rcx]
0x18001648e  lea     rdx, [rbp+arg_18]
0x180016492  mov     rax, [rax+40h]
0x180016496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001649b  mov     ebx, eax
0x18001649d  test    eax, eax
0x18001649f  jns     short loc_1800164A8
0x1800164a1  mov     edx, 53Fh
0x1800164a6  jmp     short loc_18001643C
0x1800164a8  cmp     dword ptr [rbp+pszPath], r13d
0x1800164ac  jnz     short loc_1800164B7
0x1800164ae  cmp     [rbp+arg_18], r13d
0x1800164b2  mov     eax, r13d
0x1800164b5  jz      short loc_1800164BC
0x1800164b7  mov     eax, 1
0x1800164bc  mov     [r15], eax
0x1800164bf  lea     rcx, [rbp+var_30]
0x1800164c3  call    ??1?$com_ptr_t@UIOfflineFilesCache@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(void)
0x1800164c8  cmp     [rbp+var_40], r13
0x1800164cc  jz      loc_1800165AA
0x1800164d2  mov     rcx, [r14+8]
0x1800164d6  mov     rax, [rcx]
0x1800164d9  mov     rax, [rax]
0x1800164dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164e1  mov     rdx, rax; void *
0x1800164e4  lea     rcx, [rbp+var_20]; this
0x1800164e8  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x1800164ed  mov     ebx, eax
0x1800164ef  test    eax, eax
0x1800164f1  jns     short loc_180016500
0x1800164f3  mov     r9d, eax
0x1800164f6  mov     edx, 549h
0x1800164fb  jmp     loc_180016401
0x180016500  mov     [rbp+var_28], r13
0x180016504  mov     rcx, [rbp+var_40]
0x180016508  mov     rax, [rcx]
0x18001650b  lea     r8, [rbp+var_28]
0x18001650f  lea     rdx, _GUID_efb23a09_a867_4be8_83a6_86969a7d0856
0x180016516  mov     rax, [rax]
0x180016519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001651e  mov     ebx, eax
0x180016520  test    eax, eax
0x180016522  jns     short loc_18001654B
0x180016524  mov     edx, 54Ch; void *
0x180016529  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180016530  mov     r9d, eax; char *
0x180016533  mov     rcx, [rbp+40h]; this
0x180016537  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001653c  nop
0x18001653d  lea     rcx, [rbp+var_28]
0x180016541  call    ??1?$com_ptr_t@UIOfflineFilesCache@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(void)
0x180016546  jmp     loc_1800163D9
0x18001654b  mov     [rbp+arg_8], r13d
0x18001654f  mov     [rbp+var_48], r13d
0x180016553  mov     rcx, [rbp+var_28]
0x180016557  mov     rax, [rcx]
0x18001655a  lea     r8, [rbp+var_48]
0x18001655e  lea     rdx, [rbp+arg_8]
0x180016562  mov     rax, [rax+18h]
0x180016566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001656b  mov     ebx, eax
0x18001656d  cmp     eax, 800710FEh
0x180016572  jz      short loc_18001658B
0x180016574  cmp     eax, 80070005h
0x180016579  jz      short loc_18001658B
0x18001657b  test    eax, eax
0x18001657d  jns     short loc_180016586
0x18001657f  mov     edx, 55Fh
0x180016584  jmp     short loc_180016529
0x180016586  mov     ecx, [rbp+arg_8]
0x180016589  jmp     short loc_180016593
0x18001658b  mov     ecx, 1
0x180016590  mov     [rbp+arg_8], ecx
0x180016593  mov     eax, r13d
  ... truncated ...
```

# CModernShareCommand::TryGetStorageProviderShareLinkSource(IShellItemArray *,int,winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource &)

- ea: `0x18004f394`
- end: `0x18004f6c4`
- name: `?TryGetStorageProviderShareLinkSource@CModernShareCommand@@AEAAJPEAUIShellItemArray@@HAEAUIStorageProviderShareLinkSource@Provider@Storage@Windows@winrt@@@Z`
- size: `816`
- prototype: `int(CModernShareCommand *__hidden this, struct IShellItemArray *, int, struct winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f880`
- `0x180047af0`

## callees

- `0x18001d18c`
- `0x1800214cc`
- `0x18002cdd0`
- `0x1800386e8`
- `0x18004f394`
- `0x180052930`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004f3d1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004f3d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f4c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f628`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f65d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f692`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f4c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f628`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f65d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f692`

## string_xrefs

- `0x18004f3e8`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004f43b`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004f4ac`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004f601`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CModernShareCommand::TryGetStorageProviderShareLinkSource(
        CModernShareCommand *this,
        struct IShellItemArray *a2,
        int a3,
        struct winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource *a4)
{
  HRESULT Instance; // eax
  unsigned int v8; // ebx
  __int64 result; // rax
  struct IShellItemArrayVtbl *lpVtbl; // rax
  __int64 (*GetItemAt)(void); // rax
  int v12; // eax
  unsigned int v13; // ebx
  const char *v14; // r9
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, __int64); // rbx
  __int64 v17; // r8
  int v18; // eax
  int v19; // ebx
  __int64 v20; // rax
  _QWORD *v21; // rax
  int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64 *, void **); // rbx
  struct IUnknown *v26; // rdx
  void **v27; // rax
  int v28; // [rsp+20h] [rbp-68h]
  __int64 *v29; // [rsp+30h] [rbp-58h] BYREF
  __int64 v30; // [rsp+38h] [rbp-50h] BYREF
  __int64 v31; // [rsp+40h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-40h] BYREF
  _BYTE v33[56]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  CModernShareCommand *v35; // [rsp+90h] [rbp+8h] BYREF

  v35 = this;
  v29 = 0;
  Instance = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, (LPVOID *)&v29);
  v8 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B0,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)Instance,
      v28);
    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v29);
    return v8;
  }
  lpVtbl = a2->lpVtbl;
  v31 = 0;
  GetItemAt = (__int64 (*)(void))lpVtbl->GetItemAt;
  try
  {
    v12 = GetItemAt();
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B3,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)v12,
        v28);
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v31);
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v29);
      return v13;
    }
    pv = 0;
    v15 = v31;
    v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v31 + 40LL);
    v17 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
    v18 = v16(v15, 2147844096LL, v17);
    v19 = v18;
    if ( v18 >= 0 )
    {
      v30 = 0;
      LODWORD(v35) = 0;
      v20 = *v29;
      v30 = 0;
      v19 = (*(__int64 (__fastcall **)(__int64 *, LPVOID, __int64 *, _QWORD))(v20 + 32))(v29, pv, &v30, 0);
      if ( v19 >= 0 )
      {
        v21 = (_QWORD *)wil::com_ptr_t<IStorageProviderInfo,wil::err_exception_policy>::query<IStorageProviderShareLinkSourceInfo>(
                          &v30,
                          v33);
        v22 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 40LL))(*v21);
        wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(v33);
        if ( !v22 )
          goto LABEL_18;
        if ( !a3 )
        {
          wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v30);
          if ( pv )
            CoTaskMemFree(pv);
          wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v31);
          wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v29);
          return 1;
        }
        v23 = wil::com_ptr_t<IStorageProviderInfo,wil::err_exception_policy>::query<IStorageProviderShareLinkSourceInfo>(
                &v30,
                v33);
        v24 = *(_QWORD *)v23;
        v25 = *(__int64 (__fastcall **)(__int64, __int64 *, void **))(**(_QWORD **)v23 + 32LL);
        v27 = winrt::put_abi(a4, v26);
        v19 = v25(v24, winrt::impl::guid_v<winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource>, v27);
        wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(v33);
        if ( v19 >= 0 )
        {
LABEL_18:
          wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v30);
          if ( pv )
            CoTaskMemFree(pv);
          wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v31);
          wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v29);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8C5,
          (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
          (const char *)(unsigned int)v19,
          (int)&v35);
        wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v30);
        if ( !pv )
          goto LABEL_23;
        goto LABEL_22;
      }
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v30);
      if ( pv )
LABEL_22:
        CoTaskMemFree(pv);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B5,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)v18,
        v28);
      if ( pv )
        goto LABEL_22;
    }
LABEL_23:
    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v31);
    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v29);
    result = (unsigned int)v19;
  }
  catch ( ... )
  {
    LODWORD(v35) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x8CC,
                     (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
                     v14);
    return (unsigned int)v35;
  }
  return result;
}

```

## disassembly

```asm
0x18004f394  mov     r11, rsp
0x18004f397  mov     [r11+8], rcx
0x18004f39b  push    rbx
0x18004f39c  push    rsi
0x18004f39d  push    rdi
0x18004f39e  push    r14
0x18004f3a0  sub     rsp, 68h
0x18004f3a4  mov     r14, r9
0x18004f3a7  mov     esi, r8d
0x18004f3aa  mov     rdi, rdx
0x18004f3ad  mov     qword ptr [r11-58h], 0
0x18004f3b5  lea     rax, [r11-58h]
0x18004f3b9  mov     [r11-68h], rax
0x18004f3bd  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x18004f3c4  xor     edx, edx; pUnkOuter
0x18004f3c6  lea     r8d, [rdx+1]; dwClsContext
0x18004f3ca  lea     rcx, CLSID_SyncRootManager; rclsid
0x18004f3d1  call    cs:__imp_CoCreateInstance
0x18004f3d7  mov     ebx, eax
0x18004f3d9  test    eax, eax
0x18004f3db  jns     short loc_18004F40B
0x18004f3dd  mov     rcx, [rsp+88h]; this
0x18004f3e5  mov     r9d, eax; char *
0x18004f3e8  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004f3ef  mov     edx, 8B0h; void *
0x18004f3f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f3f9  nop
0x18004f3fa  lea     rcx, [rsp+88h+var_58]
0x18004f3ff  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f404  mov     eax, ebx
0x18004f406  jmp     loc_18004F6B9
0x18004f40b  mov     rax, [rdi]
0x18004f40e  mov     [rsp+88h+var_48], 0
0x18004f417  lea     r8, [rsp+88h+var_48]
0x18004f41c  xor     edx, edx
0x18004f41e  mov     rcx, rdi
0x18004f421  mov     rax, [rax+40h]
0x18004f425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f42a  mov     ebx, eax
0x18004f42c  test    eax, eax
0x18004f42e  jns     short loc_18004F469
0x18004f430  mov     rcx, [rsp+88h]; this
0x18004f438  mov     r9d, eax; char *
0x18004f43b  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004f442  mov     edx, 8B3h; void *
0x18004f447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f44c  nop
0x18004f44d  lea     rcx, [rsp+88h+var_48]
0x18004f452  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f457  nop
0x18004f458  lea     rcx, [rsp+88h+var_58]
0x18004f45d  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f462  mov     eax, ebx
0x18004f464  jmp     loc_18004F6B9
0x18004f469  mov     [rsp+88h+pv], 0
0x18004f472  mov     rdi, [rsp+88h+var_48]
0x18004f477  mov     rax, [rdi]
0x18004f47a  mov     rbx, [rax+28h]
0x18004f47e  lea     rcx, [rsp+88h+pv]
0x18004f483  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18004f488  mov     r8, rax
0x18004f48b  mov     edx, 80058000h
0x18004f490  mov     rcx, rdi
0x18004f493  mov     rax, rbx
0x18004f496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f49b  mov     ebx, eax
0x18004f49d  test    eax, eax
0x18004f49f  jns     short loc_18004F4EB
0x18004f4a1  mov     rcx, [rsp+88h]; this
0x18004f4a9  mov     r9d, eax; char *
0x18004f4ac  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004f4b3  mov     edx, 8B5h; void *
0x18004f4b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f4bd  nop
0x18004f4be  mov     rcx, [rsp+88h+pv]; pv
0x18004f4c3  test    rcx, rcx
0x18004f4c6  jz      short loc_18004F4CF
0x18004f4c8  call    cs:__imp_CoTaskMemFree
0x18004f4ce  nop
0x18004f4cf  lea     rcx, [rsp+88h+var_48]
0x18004f4d4  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f4d9  nop
0x18004f4da  lea     rcx, [rsp+88h+var_58]
0x18004f4df  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f4e4  mov     eax, ebx
0x18004f4e6  jmp     loc_18004F6B9
0x18004f4eb  mov     [rsp+88h+var_50], 0
0x18004f4f4  mov     dword ptr [rsp+88h+arg_0], 0
0x18004f4ff  mov     rcx, [rsp+88h+var_58]
0x18004f504  mov     rax, [rcx]
0x18004f507  mov     [rsp+88h+var_50], 0
0x18004f510  lea     rdx, [rsp+88h+arg_0]
0x18004f518  mov     qword ptr [rsp+88h+var_68], rdx; int
0x18004f51d  xor     r9d, r9d
0x18004f520  lea     r8, [rsp+88h+var_50]
0x18004f525  mov     rdx, [rsp+88h+pv]
0x18004f52a  mov     rax, [rax+20h]
0x18004f52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f533  mov     ebx, eax
0x18004f535  test    eax, eax
0x18004f537  js      loc_18004F67D
0x18004f53d  lea     rdx, [rsp+88h+var_38]
0x18004f542  lea     rcx, [rsp+88h+var_50]
0x18004f547  call    ??$query@UIStorageProviderShareLinkSourceInfo@@@?$com_ptr_t@UIStorageProviderInfo@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIStorageProviderShareLinkSourceInfo@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IStorageProviderInfo,wil::err_exception_policy>::query<IStorageProviderShareLinkSourceInfo>(void)
0x18004f54c  nop
0x18004f54d  mov     rcx, [rax]
0x18004f550  mov     rax, [rcx]
0x18004f553  mov     rax, [rax+28h]
0x18004f557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f55c  mov     ebx, eax
0x18004f55e  lea     rcx, [rsp+88h+var_38]
0x18004f563  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f568  test    ebx, ebx
0x18004f56a  jz      loc_18004F648
0x18004f570  test    esi, esi
0x18004f572  jnz     short loc_18004F5AF
0x18004f574  lea     rcx, [rsp+88h+var_50]
0x18004f579  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f57e  nop
0x18004f57f  mov     rcx, [rsp+88h+pv]; pv
0x18004f584  test    rcx, rcx
0x18004f587  jz      short loc_18004F590
0x18004f589  call    cs:__imp_CoTaskMemFree
0x18004f58f  nop
0x18004f590  lea     rcx, [rsp+88h+var_48]
0x18004f595  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f59a  nop
0x18004f59b  lea     rcx, [rsp+88h+var_58]
0x18004f5a0  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f5a5  mov     eax, 1
0x18004f5aa  jmp     loc_18004F6B9
0x18004f5af  lea     rdx, [rsp+88h+var_38]
0x18004f5b4  lea     rcx, [rsp+88h+var_50]
0x18004f5b9  call    ??$query@UIStorageProviderShareLinkSourceInfo@@@?$com_ptr_t@UIStorageProviderInfo@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIStorageProviderShareLinkSourceInfo@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IStorageProviderInfo,wil::err_exception_policy>::query<IStorageProviderShareLinkSourceInfo>(void)
0x18004f5be  nop
0x18004f5bf  mov     rdi, [rax]
0x18004f5c2  mov     rax, [rdi]
0x18004f5c5  mov     rbx, [rax+20h]
0x18004f5c9  mov     rcx, r14; this
0x18004f5cc  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18004f5d1  mov     r8, rax
0x18004f5d4  lea     rdx, ??$guid_v@UIStorageProviderShareLinkSource@Provider@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource>
0x18004f5db  mov     rcx, rdi
0x18004f5de  mov     rax, rbx
0x18004f5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5e6  mov     ebx, eax
0x18004f5e8  lea     rcx, [rsp+88h+var_38]
0x18004f5ed  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f5f2  test    ebx, ebx
0x18004f5f4  jns     short loc_18004F648
0x18004f5f6  mov     rcx, [rsp+88h]; this
0x18004f5fe  mov     r9d, ebx; char *
0x18004f601  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004f608  mov     edx, 8C5h; void *
0x18004f60d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f612  nop
0x18004f613  lea     rcx, [rsp+88h+var_50]
0x18004f618  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f61d  nop
0x18004f61e  mov     rcx, [rsp+88h+pv]; pv
0x18004f623  test    rcx, rcx
0x18004f626  jz      short loc_18004F62F
0x18004f628  call    cs:__imp_CoTaskMemFree
0x18004f62e  nop
0x18004f62f  lea     rcx, [rsp+88h+var_48]
0x18004f634  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f639  nop
0x18004f63a  lea     rcx, [rsp+88h+var_58]
0x18004f63f  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f644  mov     eax, ebx
0x18004f646  jmp     short loc_18004F6B9
0x18004f648  lea     rcx, [rsp+88h+var_50]
0x18004f64d  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f652  nop
0x18004f653  mov     rcx, [rsp+88h+pv]; pv
0x18004f658  test    rcx, rcx
0x18004f65b  jz      short loc_18004F664
0x18004f65d  call    cs:__imp_CoTaskMemFree
0x18004f663  nop
0x18004f664  lea     rcx, [rsp+88h+var_48]
0x18004f669  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f66e  nop
0x18004f66f  lea     rcx, [rsp+88h+var_58]
0x18004f674  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f679  xor     eax, eax
0x18004f67b  jmp     short loc_18004F6B9
0x18004f67d  lea     rcx, [rsp+88h+var_50]
0x18004f682  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f687  nop
0x18004f688  mov     rcx, [rsp+88h+pv]; pv
0x18004f68d  test    rcx, rcx
0x18004f690  jz      short loc_18004F699
0x18004f692  call    cs:__imp_CoTaskMemFree
0x18004f698  nop
0x18004f699  lea     rcx, [rsp+88h+var_48]
0x18004f69e  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f6a3  nop
0x18004f6a4  lea     rcx, [rsp+88h+var_58]
0x18004f6a9  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004f6ae  mov     eax, ebx
0x18004f6b0  jmp     short loc_18004F6B9
0x18004f6b2  mov     eax, dword ptr [rsp+88h+arg_0]
0x18004f6b9  add     rsp, 68h
0x18004f6bd  pop     r14
0x18004f6bf  pop     rdi
0x18004f6c0  pop     rsi
0x18004f6c1  pop     rbx
0x18004f6c2  retn
```

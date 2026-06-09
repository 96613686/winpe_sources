# WUInfo::GetMDMAppAutoUpdatePolicy(void)

- ea: `0x1800948c0`
- end: `0x180094970`
- name: `?GetMDMAppAutoUpdatePolicy@WUInfo@@AEBAIXZ`
- size: `176`
- prototype: `unsigned int __fastcall(WUInfo *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x1800948c0`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800948e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800948e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180094907`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180094907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094956`

## string_xrefs

- `0x1800948da`: `policymanager.dll`
- `0x180094917`: `AllowAppStoreAutoUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WUInfo::GetMDMAppAutoUpdatePolicy(WUInfo *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  unsigned int v3; // ebx
  signed int LastError; // eax
  int v6; // edx
  unsigned int v7; // r8d
  const int *v8; // [rsp+20h] [rbp-18h] BYREF
  HMODULE v9; // [rsp+28h] [rbp-10h]
  int v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = -1;
  Library = LoadLibraryExW(L"policymanager.dll", 0, 0x800u);
  v8 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v9 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "PolicyManager_GetPolicyInt");
    if ( ProcAddress )
      ((void (__fastcall *)(const wchar_t *, const wchar_t *, int *))ProcAddress)(
        L"ApplicationManagement",
        L"AllowAppStoreAutoUpdate",
        &v10);
  }
  v3 = v10;
  v8 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v9 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v8) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v6, v7);
    JUMPOUT(0x18009496FLL);
  }
  return v3;
}

```

## disassembly

```asm
0x1800948c0  mov     [rsp+arg_0], rbx
0x1800948c5  push    rdi
0x1800948c6  sub     rsp, 30h
0x1800948ca  mov     [rsp+38h+arg_8], 0FFFFFFFFh
0x1800948d2  xor     edx, edx; hFile
0x1800948d4  mov     r8d, 800h; dwFlags
0x1800948da  lea     rcx, aPolicymanagerD; "policymanager.dll"
0x1800948e1  call    cs:__imp_LoadLibraryExW
0x1800948e7  lea     rdi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800948ee  mov     [rsp+38h+var_18], rdi
0x1800948f3  mov     [rsp+38h+var_10], rax
0x1800948f8  test    rax, rax
0x1800948fb  jz      short loc_18009492A
0x1800948fd  lea     rdx, aPolicymanagerG_2; "PolicyManager_GetPolicyInt"
0x180094904  mov     rcx, rax; hModule
0x180094907  call    cs:__imp_GetProcAddress
0x18009490d  test    rax, rax
0x180094910  jz      short loc_18009492A
0x180094912  lea     r8, [rsp+38h+arg_8]
0x180094917  lea     rdx, aAllowappstorea; "AllowAppStoreAutoUpdate"
0x18009491e  lea     rcx, aApplicationman; "ApplicationManagement"
0x180094925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009492a  mov     ebx, [rsp+38h+arg_8]
0x18009492e  mov     [rsp+38h+var_18], rdi
0x180094933  cmp     [rsp+38h+var_10], 0
0x180094939  jz      short loc_180094949
0x18009493b  lea     rcx, [rsp+38h+var_18]
0x180094940  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180094945  test    al, al
0x180094947  jz      short loc_180094956
0x180094949  mov     eax, ebx
0x18009494b  mov     rbx, [rsp+38h+arg_0]
0x180094950  add     rsp, 30h
0x180094954  pop     rdi
0x180094955  retn
0x180094956  call    cs:__imp_GetLastError
0x18009495c  test    eax, eax
0x18009495e  jle     short loc_180094968
0x180094960  movzx   eax, ax
0x180094963  or      eax, 80070000h
0x180094968  mov     ecx, eax; this
0x18009496a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

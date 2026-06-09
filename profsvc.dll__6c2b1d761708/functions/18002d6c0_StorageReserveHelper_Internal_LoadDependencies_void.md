# StorageReserveHelper::Internal::LoadDependencies(void)

- ea: `0x18002d6c0`
- end: `0x18002d87a`
- name: `?LoadDependencies@Internal@StorageReserveHelper@@YAJXZ`
- size: `442`
- prototype: `__int64 __fastcall(StorageReserveHelper::Internal *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036840`

## callees

- `0x18002d6c0`
- `0x18002d88c`
- `0x18002df48`
- `0x18002e03c`
- `0x180032e60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d722`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d762`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d7a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d837`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d722`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d762`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d7a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d837`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002d6cd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002d7db`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002d6cd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002d7db`

## string_xrefs

- `0x18002d7d4`: `ntdll.dll`
- `0x18002d6c6`: `kernelbase.dll`
- `0x18002d758`: `PathAllocCombine`
- `0x18002d718`: `PathCchCombineEx`
- `0x18002d830`: `RtlIsNonEmptyDirectoryReparsePointAllowed`
- `0x18002d79b`: `PathAllocCanonicalize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageReserveHelper::Internal::LoadDependencies(StorageReserveHelper::Internal *this)
{
  HMODULE LibraryW; // rax
  const char *v2; // r9
  HMODULE v3; // rbx
  unsigned int LastError; // ebx
  wil::details *v6; // rcx
  HMODULE v7; // rax
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+30h] [rbp+8h] BYREF

  LibraryW = LoadLibraryW(L"kernelbase.dll");
  v3 = LibraryW;
  hModule = LibraryW;
  if ( !LibraryW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x19,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
                  v2);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
    return LastError;
  }
  if ( !StorageReserveHelper::Internal::pfnPathCchCombineEx )
  {
    StorageReserveHelper::Internal::pfnPathCchCombineEx = (int (*)(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, unsigned int))GetProcAddress(LibraryW, "PathCchCombineEx");
    if ( !StorageReserveHelper::Internal::pfnPathCchCombineEx )
      goto LABEL_15;
  }
  if ( !StorageReserveHelper::Internal::pfnPathAllocCombine )
  {
    StorageReserveHelper::Internal::pfnPathAllocCombine = (int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **))GetProcAddress(v3, "PathAllocCombine");
    if ( !StorageReserveHelper::Internal::pfnPathAllocCombine )
      goto LABEL_15;
  }
  if ( !StorageReserveHelper::Internal::pfnPathAllocCanonicalize )
  {
    StorageReserveHelper::Internal::pfnPathAllocCanonicalize = (int (*)(const unsigned __int16 *, unsigned int, unsigned __int16 **))GetProcAddress(v3, "PathAllocCanonicalize");
    if ( !StorageReserveHelper::Internal::pfnPathAllocCanonicalize )
      goto LABEL_15;
  }
  v7 = LoadLibraryW(L"ntdll.dll");
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    &hModule,
    v7);
  if ( !hModule )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2E,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
                  v8);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
    return LastError;
  }
  if ( !StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed )
  {
    StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed = (unsigned __int8 (*)(unsigned int))GetProcAddress(hModule, "RtlIsNonEmptyDirectoryReparsePointAllowed");
    if ( !StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed )
    {
LABEL_15:
      LastError = wil::details::GetLastErrorFailHr(v6);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
      return LastError;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
  return 0;
}

```

## disassembly

```asm
0x18002d6c0  push    rbx
0x18002d6c2  sub     rsp, 20h
0x18002d6c6  lea     rcx, ModuleName; "kernelbase.dll"
0x18002d6cd  call    cs:__imp_LoadLibraryW
0x18002d6d4  nop     dword ptr [rax+rax+00h]
0x18002d6d9  mov     rbx, rax
0x18002d6dc  mov     [rsp+28h+hModule], rax
0x18002d6e1  test    rax, rax
0x18002d6e4  jnz     short loc_18002D70E
0x18002d6e6  mov     rcx, [rsp+28h]; this
0x18002d6eb  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002d6f2  lea     edx, [rax+19h]; void *
0x18002d6f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d6fa  mov     ebx, eax
0x18002d6fc  lea     rcx, [rsp+28h+hModule]
0x18002d701  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002d706  nop
0x18002d707  mov     eax, ebx
0x18002d709  jmp     loc_18002D873
0x18002d70e  cmp     cs:?pfnPathCchCombineEx@Internal@StorageReserveHelper@@3P6AJPEAG_KPEBG2K@ZEA, 0; long (*StorageReserveHelper::Internal::pfnPathCchCombineEx)(ushort *,unsigned __int64,ushort const *,ushort const *,ulong)
0x18002d716  jnz     short loc_18002D74E
0x18002d718  lea     rdx, aPathcchcombine; "PathCchCombineEx"
0x18002d71f  mov     rcx, rbx; hModule
0x18002d722  call    cs:__imp_GetProcAddress
0x18002d729  nop     dword ptr [rax+rax+00h]
0x18002d72e  mov     cs:?pfnPathCchCombineEx@Internal@StorageReserveHelper@@3P6AJPEAG_KPEBG2K@ZEA, rax; long (*StorageReserveHelper::Internal::pfnPathCchCombineEx)(ushort *,unsigned __int64,ushort const *,ushort const *,ulong)
0x18002d735  test    rax, rax
0x18002d738  jnz     short loc_18002D74E
0x18002d73a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002d73f  mov     ebx, eax
0x18002d741  lea     rcx, [rsp+28h+hModule]
0x18002d746  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002d74b  nop
0x18002d74c  jmp     short loc_18002D707
0x18002d74e  cmp     cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA, 0; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x18002d756  jnz     short loc_18002D791
0x18002d758  lea     rdx, aPathalloccombi; "PathAllocCombine"
0x18002d75f  mov     rcx, rbx; hModule
0x18002d762  call    cs:__imp_GetProcAddress
0x18002d769  nop     dword ptr [rax+rax+00h]
0x18002d76e  mov     cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA, rax; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x18002d775  test    rax, rax
0x18002d778  jnz     short loc_18002D791
0x18002d77a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002d77f  mov     ebx, eax
0x18002d781  lea     rcx, [rsp+28h+hModule]
0x18002d786  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002d78b  nop
0x18002d78c  jmp     loc_18002D707
0x18002d791  cmp     cs:?pfnPathAllocCanonicalize@Internal@StorageReserveHelper@@3P6AJPEBGKPEAPEAG@ZEA, 0; long (*StorageReserveHelper::Internal::pfnPathAllocCanonicalize)(ushort const *,ulong,ushort * *)
0x18002d799  jnz     short loc_18002D7D4
0x18002d79b  lea     rdx, aPathalloccanon; "PathAllocCanonicalize"
0x18002d7a2  mov     rcx, rbx; hModule
0x18002d7a5  call    cs:__imp_GetProcAddress
0x18002d7ac  nop     dword ptr [rax+rax+00h]
0x18002d7b1  mov     cs:?pfnPathAllocCanonicalize@Internal@StorageReserveHelper@@3P6AJPEBGKPEAPEAG@ZEA, rax; long (*StorageReserveHelper::Internal::pfnPathAllocCanonicalize)(ushort const *,ulong,ushort * *)
0x18002d7b8  test    rax, rax
0x18002d7bb  jnz     short loc_18002D7D4
0x18002d7bd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002d7c2  mov     ebx, eax
0x18002d7c4  lea     rcx, [rsp+28h+hModule]
0x18002d7c9  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002d7ce  nop
0x18002d7cf  jmp     loc_18002D707
0x18002d7d4  lea     rcx, LibFileName; "ntdll.dll"
0x18002d7db  call    cs:__imp_LoadLibraryW
0x18002d7e2  nop     dword ptr [rax+rax+00h]
0x18002d7e7  mov     rdx, rax
0x18002d7ea  lea     rcx, [rsp+28h+hModule]
0x18002d7ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18002d7f4  mov     rcx, [rsp+28h+hModule]; hModule
0x18002d7f9  test    rcx, rcx
0x18002d7fc  jnz     short loc_18002D826
0x18002d7fe  mov     rcx, [rsp+28h]; this
0x18002d803  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002d80a  mov     edx, 2Eh ; '.'; void *
0x18002d80f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d814  mov     ebx, eax
0x18002d816  lea     rcx, [rsp+28h+hModule]
0x18002d81b  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002d820  nop
0x18002d821  jmp     loc_18002D707
0x18002d826  cmp     cs:?pfnRtlIsNonEmptyDirectoryReparsePointAllowed@Internal@StorageReserveHelper@@3P6AEK@ZEA, 0; uchar (*StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed)(ulong)
0x18002d82e  jnz     short loc_18002D866
0x18002d830  lea     rdx, aRtlisnonemptyd; "RtlIsNonEmptyDirectoryReparsePointAllow"...
0x18002d837  call    cs:__imp_GetProcAddress
0x18002d83e  nop     dword ptr [rax+rax+00h]
0x18002d843  mov     cs:?pfnRtlIsNonEmptyDirectoryReparsePointAllowed@Internal@StorageReserveHelper@@3P6AEK@ZEA, rax; uchar (*StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed)(ulong)
0x18002d84a  test    rax, rax
0x18002d84d  jnz     short loc_18002D866
0x18002d84f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002d854  mov     ebx, eax
0x18002d856  lea     rcx, [rsp+28h+hModule]
0x18002d85b  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002d860  nop
0x18002d861  jmp     loc_18002D707
0x18002d866  lea     rcx, [rsp+28h+hModule]
0x18002d86b  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002d870  nop
0x18002d871  xor     eax, eax
0x18002d873  add     rsp, 20h
0x18002d877  pop     rbx
0x18002d878  retn
```

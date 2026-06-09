# StorageReserveHelper::Internal::LoadDependencies(void)

- ea: `0x18002f920`
- end: `0x18002facf`
- name: `?LoadDependencies@Internal@StorageReserveHelper@@YAJXZ`
- size: `431`
- prototype: `__int64 __fastcall(StorageReserveHelper::Internal *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800361d4`

## callees

- `0x18002db38`
- `0x18002f920`
- `0x18002fae4`
- `0x180030e58`
- `0x180030ebc`
- `0x1800321f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fa3a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fa3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f980`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f9ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f9f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fa8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f980`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f9ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f9f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fa8e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002f931`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002fa24`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002f931`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002fa24`

## string_xrefs

- `0x18002fa1d`: `ntdll.dll`
- `0x18002f92a`: `kernelbase.dll`
- `0x18002f976`: `PathCchCombineEx`
- `0x18002f9b0`: `PathAllocCombine`
- `0x18002f9ea`: `PathAllocCanonicalize`
- `0x18002fa84`: `RtlIsNonEmptyDirectoryReparsePointAllowed`

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
  HMODULE v7; // rdi
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE v10; // [rsp+30h] [rbp+8h] BYREF

  LibraryW = LoadLibraryW(L"kernelbase.dll");
  v3 = LibraryW;
  v10 = LibraryW;
  if ( !LibraryW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x19,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
                  v2);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v10);
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
  wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
  FreeLibrary(v3);
  wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
  v10 = v7;
  if ( !v7 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2E,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
                  v8);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v10);
    return LastError;
  }
  if ( !StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed )
  {
    StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed = (unsigned __int8 (*)(unsigned int))GetProcAddress(v7, "RtlIsNonEmptyDirectoryReparsePointAllowed");
    if ( !StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed )
    {
LABEL_15:
      LastError = wil::details::GetLastErrorFailHr(v6);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v10);
      return LastError;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v10);
  return 0;
}

```

## disassembly

```asm
0x18002f920  mov     [rsp+arg_8], rbx
0x18002f925  push    rdi
0x18002f926  sub     rsp, 20h
0x18002f92a  lea     rcx, ModuleName; "kernelbase.dll"
0x18002f931  call    cs:__imp_LoadLibraryW
0x18002f937  mov     rbx, rax
0x18002f93a  mov     [rsp+28h+arg_0], rax
0x18002f93f  test    rax, rax
0x18002f942  jnz     short loc_18002F96C
0x18002f944  mov     rcx, [rsp+28h]; this
0x18002f949  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002f950  lea     edx, [rax+19h]; void *
0x18002f953  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f958  mov     ebx, eax
0x18002f95a  lea     rcx, [rsp+28h+arg_0]
0x18002f95f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002f964  nop
0x18002f965  mov     eax, ebx
0x18002f967  jmp     loc_18002FAC4
0x18002f96c  cmp     cs:?pfnPathCchCombineEx@Internal@StorageReserveHelper@@3P6AJPEAG_KPEBG2K@ZEA, 0; long (*StorageReserveHelper::Internal::pfnPathCchCombineEx)(ushort *,unsigned __int64,ushort const *,ushort const *,ulong)
0x18002f974  jnz     short loc_18002F9A6
0x18002f976  lea     rdx, aPathcchcombine; "PathCchCombineEx"
0x18002f97d  mov     rcx, rbx; hModule
0x18002f980  call    cs:__imp_GetProcAddress
0x18002f986  mov     cs:?pfnPathCchCombineEx@Internal@StorageReserveHelper@@3P6AJPEAG_KPEBG2K@ZEA, rax; long (*StorageReserveHelper::Internal::pfnPathCchCombineEx)(ushort *,unsigned __int64,ushort const *,ushort const *,ulong)
0x18002f98d  test    rax, rax
0x18002f990  jnz     short loc_18002F9A6
0x18002f992  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002f997  mov     ebx, eax
0x18002f999  lea     rcx, [rsp+28h+arg_0]
0x18002f99e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002f9a3  nop
0x18002f9a4  jmp     short loc_18002F965
0x18002f9a6  cmp     cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA, 0; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x18002f9ae  jnz     short loc_18002F9E0
0x18002f9b0  lea     rdx, aPathalloccombi; "PathAllocCombine"
0x18002f9b7  mov     rcx, rbx; hModule
0x18002f9ba  call    cs:__imp_GetProcAddress
0x18002f9c0  mov     cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA, rax; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x18002f9c7  test    rax, rax
0x18002f9ca  jnz     short loc_18002F9E0
0x18002f9cc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002f9d1  mov     ebx, eax
0x18002f9d3  lea     rcx, [rsp+28h+arg_0]
0x18002f9d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002f9dd  nop
0x18002f9de  jmp     short loc_18002F965
0x18002f9e0  cmp     cs:?pfnPathAllocCanonicalize@Internal@StorageReserveHelper@@3P6AJPEBGKPEAPEAG@ZEA, 0; long (*StorageReserveHelper::Internal::pfnPathAllocCanonicalize)(ushort const *,ulong,ushort * *)
0x18002f9e8  jnz     short loc_18002FA1D
0x18002f9ea  lea     rdx, aPathalloccanon; "PathAllocCanonicalize"
0x18002f9f1  mov     rcx, rbx; hModule
0x18002f9f4  call    cs:__imp_GetProcAddress
0x18002f9fa  mov     cs:?pfnPathAllocCanonicalize@Internal@StorageReserveHelper@@3P6AJPEBGKPEAPEAG@ZEA, rax; long (*StorageReserveHelper::Internal::pfnPathAllocCanonicalize)(ushort const *,ulong,ushort * *)
0x18002fa01  test    rax, rax
0x18002fa04  jnz     short loc_18002FA1D
0x18002fa06  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002fa0b  mov     ebx, eax
0x18002fa0d  lea     rcx, [rsp+28h+arg_0]
0x18002fa12  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002fa17  nop
0x18002fa18  jmp     loc_18002F965
0x18002fa1d  lea     rcx, LibFileName; "ntdll.dll"
0x18002fa24  call    cs:__imp_LoadLibraryW
0x18002fa2a  mov     rdi, rax
0x18002fa2d  lea     rcx, [rsp+28h+arg_0]; this
0x18002fa32  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002fa37  mov     rcx, rbx; hLibModule
0x18002fa3a  call    cs:__imp_FreeLibrary
0x18002fa40  lea     rcx, [rsp+28h+arg_0]; this
0x18002fa45  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002fa4a  mov     [rsp+28h+arg_0], rdi
0x18002fa4f  test    rdi, rdi
0x18002fa52  jnz     short loc_18002FA7A
0x18002fa54  mov     rcx, [rsp+28h]; this
0x18002fa59  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002fa60  lea     edx, [rdi+2Eh]; void *
0x18002fa63  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002fa68  mov     ebx, eax
0x18002fa6a  lea     rcx, [rsp+28h+arg_0]
0x18002fa6f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002fa74  nop
0x18002fa75  jmp     loc_18002F965
0x18002fa7a  cmp     cs:?pfnRtlIsNonEmptyDirectoryReparsePointAllowed@Internal@StorageReserveHelper@@3P6AEK@ZEA, 0; uchar (*StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed)(ulong)
0x18002fa82  jnz     short loc_18002FAB7
0x18002fa84  lea     rdx, aRtlisnonemptyd; "RtlIsNonEmptyDirectoryReparsePointAllow"...
0x18002fa8b  mov     rcx, rdi; hModule
0x18002fa8e  call    cs:__imp_GetProcAddress
0x18002fa94  mov     cs:?pfnRtlIsNonEmptyDirectoryReparsePointAllowed@Internal@StorageReserveHelper@@3P6AEK@ZEA, rax; uchar (*StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed)(ulong)
0x18002fa9b  test    rax, rax
0x18002fa9e  jnz     short loc_18002FAB7
0x18002faa0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002faa5  mov     ebx, eax
0x18002faa7  lea     rcx, [rsp+28h+arg_0]
0x18002faac  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002fab1  nop
0x18002fab2  jmp     loc_18002F965
0x18002fab7  lea     rcx, [rsp+28h+arg_0]
0x18002fabc  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002fac1  nop
0x18002fac2  xor     eax, eax
0x18002fac4  mov     rbx, [rsp+28h+arg_8]
0x18002fac9  add     rsp, 20h
0x18002facd  pop     rdi
0x18002face  retn
```

# OpenFunctionPointers(wddm_version_helper_fn_ptrs &)

- ea: `0x18006eddc`
- end: `0x18006eece`
- name: `?OpenFunctionPointers@@YAJAEAUwddm_version_helper_fn_ptrs@@@Z`
- size: `242`
- prototype: `signed int __fastcall(HMODULE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18006ebb0`

## callees

- `0x1800218ac`
- `0x1800218cc`
- `0x18006eb84`
- `0x18006eddc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ee31`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ee31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006ee04`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006ee04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ee7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ee94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006eead`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ee7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ee94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006eead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ee60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ee60`

## string_xrefs

- `0x18006edfd`: `gdi32.dll`
- `0x18006ee74`: `D3DKMTOpenAdapterFromLuid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall OpenFunctionPointers(HMODULE *a1)
{
  HMODULE Library; // rsi
  HMODULE v3; // rdi
  signed int result; // eax
  FARPROC ProcAddress; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  char v9; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 )
    return 0;
  Library = LoadLibraryExW(L"gdi32.dll", 0, 0);
  v8[0] = Library;
  if ( a1 != v8 )
  {
    v3 = *a1;
    if ( *a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
      FreeLibrary(v3);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
    }
    *a1 = Library;
    v8[0] = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v8);
  if ( *a1 )
  {
    ProcAddress = GetProcAddress(*a1, "D3DKMTOpenAdapterFromLuid");
    a1[1] = (HMODULE)ProcAddress;
    if ( ProcAddress )
    {
      v6 = GetProcAddress(*a1, "D3DKMTCloseAdapter");
      a1[2] = (HMODULE)v6;
      if ( v6 )
      {
        v7 = GetProcAddress(*a1, "D3DKMTQueryAdapterInfo");
        a1[3] = (HMODULE)v7;
        if ( v7 )
          return 0;
      }
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18006eddc  mov     [rsp+arg_8], rbx
0x18006ede1  mov     [rsp+arg_10], rsi
0x18006ede6  push    rdi
0x18006ede7  sub     rsp, 30h
0x18006edeb  mov     rbx, rcx
0x18006edee  cmp     qword ptr [rcx], 0
0x18006edf2  jnz     loc_18006EEBC
0x18006edf8  xor     r8d, r8d; dwFlags
0x18006edfb  xor     edx, edx; hFile
0x18006edfd  lea     rcx, LibFileName; "gdi32.dll"
0x18006ee04  call    cs:__imp_LoadLibraryExW
0x18006ee0a  mov     rsi, rax
0x18006ee0d  mov     [rsp+38h+var_18], rax
0x18006ee12  lea     rax, [rsp+38h+var_18]
0x18006ee17  cmp     rbx, rax
0x18006ee1a  jz      short loc_18006EE4E
0x18006ee1c  mov     rdi, [rbx]
0x18006ee1f  test    rdi, rdi
0x18006ee22  jz      short loc_18006EE42
0x18006ee24  lea     rcx, [rsp+38h+arg_0]; this
0x18006ee29  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006ee2e  mov     rcx, rdi; hLibModule
0x18006ee31  call    cs:__imp_FreeLibrary
0x18006ee37  lea     rcx, [rsp+38h+arg_0]; this
0x18006ee3c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006ee41  nop
0x18006ee42  mov     [rbx], rsi
0x18006ee45  mov     [rsp+38h+var_18], 0
0x18006ee4e  lea     rcx, [rsp+38h+var_18]
0x18006ee53  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18006ee58  mov     rcx, [rbx]; hModule
0x18006ee5b  test    rcx, rcx
0x18006ee5e  jnz     short loc_18006EE74
0x18006ee60  call    cs:__imp_GetLastError
0x18006ee66  test    eax, eax
0x18006ee68  jle     short loc_18006EEBE
0x18006ee6a  movzx   eax, ax
0x18006ee6d  or      eax, 80070000h
0x18006ee72  jmp     short loc_18006EEBE
0x18006ee74  lea     rdx, aD3dkmtopenadap; "D3DKMTOpenAdapterFromLuid"
0x18006ee7b  call    cs:__imp_GetProcAddress
0x18006ee81  mov     [rbx+8], rax
0x18006ee85  test    rax, rax
0x18006ee88  jz      short loc_18006EE60
0x18006ee8a  lea     rdx, aD3dkmtcloseada; "D3DKMTCloseAdapter"
0x18006ee91  mov     rcx, [rbx]; hModule
0x18006ee94  call    cs:__imp_GetProcAddress
0x18006ee9a  mov     [rbx+10h], rax
0x18006ee9e  test    rax, rax
0x18006eea1  jz      short loc_18006EE60
0x18006eea3  lea     rdx, aD3dkmtqueryada; "D3DKMTQueryAdapterInfo"
0x18006eeaa  mov     rcx, [rbx]; hModule
0x18006eead  call    cs:__imp_GetProcAddress
0x18006eeb3  mov     [rbx+18h], rax
0x18006eeb7  test    rax, rax
0x18006eeba  jz      short loc_18006EE60
0x18006eebc  xor     eax, eax
0x18006eebe  mov     rbx, [rsp+38h+arg_8]
0x18006eec3  mov     rsi, [rsp+38h+arg_10]
0x18006eec8  add     rsp, 30h
0x18006eecc  pop     rdi
0x18006eecd  retn
```

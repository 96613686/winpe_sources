# OpenFunctionPointers(wddm_version_helper_fn_ptrs &)

- ea: `0x1800c99f4`
- end: `0x1800c9ae5`
- name: `?OpenFunctionPointers@@YAJAEAUwddm_version_helper_fn_ptrs@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(struct wddm_version_helper_fn_ptrs *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800c986c`

## callees

- `0x1800432a0`
- `0x18005671c`
- `0x1800c9840`
- `0x1800c99f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c9a49`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c9a49`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c9a1c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c9a1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c9a92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c9aab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c9ac4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c9a92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c9aab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c9ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9a77`

## string_xrefs

- `0x1800c9a13`: `gdi32.dll`
- `0x1800c9a8b`: `D3DKMTOpenAdapterFromLuid`

## pseudocode

```c
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
0x1800c99f4  mov     [rsp+arg_8], rbx
0x1800c99f9  mov     [rsp+arg_10], rsi
0x1800c99fe  push    rdi
0x1800c99ff  sub     rsp, 30h
0x1800c9a03  cmp     qword ptr [rcx], 0
0x1800c9a07  mov     rbx, rcx
0x1800c9a0a  jnz     loc_1800C9AD3
0x1800c9a10  xor     r8d, r8d; dwFlags
0x1800c9a13  lea     rcx, LibFileName; "gdi32.dll"
0x1800c9a1a  xor     edx, edx; hFile
0x1800c9a1c  call    cs:__imp_LoadLibraryExW
0x1800c9a22  mov     rsi, rax
0x1800c9a25  mov     [rsp+38h+var_18], rax
0x1800c9a2a  lea     rax, [rsp+38h+var_18]
0x1800c9a2f  cmp     rbx, rax
0x1800c9a32  jz      short loc_1800C9A65
0x1800c9a34  mov     rdi, [rbx]
0x1800c9a37  test    rdi, rdi
0x1800c9a3a  jz      short loc_1800C9A59
0x1800c9a3c  lea     rcx, [rsp+38h+arg_0]; this
0x1800c9a41  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800c9a46  mov     rcx, rdi; hLibModule
0x1800c9a49  call    cs:__imp_FreeLibrary
0x1800c9a4f  lea     rcx, [rsp+38h+arg_0]; this
0x1800c9a54  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800c9a59  mov     [rbx], rsi
0x1800c9a5c  mov     [rsp+38h+var_18], 0
0x1800c9a65  lea     rcx, [rsp+38h+var_18]
0x1800c9a6a  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800c9a6f  mov     rcx, [rbx]; hModule
0x1800c9a72  test    rcx, rcx
0x1800c9a75  jnz     short loc_1800C9A8B
0x1800c9a77  call    cs:__imp_GetLastError
0x1800c9a7d  test    eax, eax
0x1800c9a7f  jle     short loc_1800C9AD5
0x1800c9a81  movzx   eax, ax
0x1800c9a84  or      eax, 80070000h
0x1800c9a89  jmp     short loc_1800C9AD5
0x1800c9a8b  lea     rdx, aD3dkmtopenadap; "D3DKMTOpenAdapterFromLuid"
0x1800c9a92  call    cs:__imp_GetProcAddress
0x1800c9a98  mov     [rbx+8], rax
0x1800c9a9c  test    rax, rax
0x1800c9a9f  jz      short loc_1800C9A77
0x1800c9aa1  mov     rcx, [rbx]; hModule
0x1800c9aa4  lea     rdx, aD3dkmtcloseada; "D3DKMTCloseAdapter"
0x1800c9aab  call    cs:__imp_GetProcAddress
0x1800c9ab1  mov     [rbx+10h], rax
0x1800c9ab5  test    rax, rax
0x1800c9ab8  jz      short loc_1800C9A77
0x1800c9aba  mov     rcx, [rbx]; hModule
0x1800c9abd  lea     rdx, aD3dkmtqueryada; "D3DKMTQueryAdapterInfo"
0x1800c9ac4  call    cs:__imp_GetProcAddress
0x1800c9aca  mov     [rbx+18h], rax
0x1800c9ace  test    rax, rax
0x1800c9ad1  jz      short loc_1800C9A77
0x1800c9ad3  xor     eax, eax
0x1800c9ad5  mov     rbx, [rsp+38h+arg_8]
0x1800c9ada  mov     rsi, [rsp+38h+arg_10]
0x1800c9adf  add     rsp, 30h
0x1800c9ae3  pop     rdi
0x1800c9ae4  retn
```

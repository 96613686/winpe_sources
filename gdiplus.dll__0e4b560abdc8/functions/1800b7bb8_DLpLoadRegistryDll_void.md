# DLpLoadRegistryDll(void)

- ea: `0x1800b7bb8`
- end: `0x1800b7c2a`
- name: `?DLpLoadRegistryDll@@YAKXZ`
- size: `114`
- prototype: `unsigned int(void)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1800346a4`
- `0x1800b765c`
- `0x1800b7934`
- `0x1800b79e8`
- `0x1800b7aac`
- `0x1800b7b1c`
- `0x18016bfe0`
- `0x18016c094`
- `0x18016c174`
- `0x18016c230`
- `0x18016c2b8`
- `0x18016c354`
- `0x18016c3f8`

## callees

- `0x1800b7bb8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b7bd6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b7bfb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b7bd6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b7bfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7c13`

## string_xrefs

- `0x1800b7bcf`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800b7bf4`: `advapi32.dll`

## pseudocode

```c
__int64 DLpLoadRegistryDll(void)
{
  unsigned int v0; // ebx

  v0 = 0;
  if ( !g_hInstRegistryDLL )
  {
    g_hInstRegistryDLL = LoadLibraryExW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll", 0, 8u);
    if ( !g_hInstRegistryDLL )
    {
      g_hInstRegistryDLL = LoadLibraryExW(L"advapi32.dll", 0, 8u);
      if ( !g_hInstRegistryDLL )
        return GetLastError();
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800b7bb8  push    rbx
0x1800b7bba  sub     rsp, 20h
0x1800b7bbe  xor     ebx, ebx
0x1800b7bc0  cmp     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstRegistryDLL
0x1800b7bc7  jnz     short loc_1800B7C21
0x1800b7bc9  xor     edx, edx; hFile
0x1800b7bcb  lea     r8d, [rbx+8]; dwFlags
0x1800b7bcf  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800b7bd6  call    cs:__imp_LoadLibraryExW
0x1800b7bdd  nop     dword ptr [rax+rax+00h]
0x1800b7be2  mov     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstRegistryDLL
0x1800b7be9  test    rax, rax
0x1800b7bec  jnz     short loc_1800B7C21
0x1800b7bee  xor     edx, edx; hFile
0x1800b7bf0  lea     r8d, [rbx+8]; dwFlags
0x1800b7bf4  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800b7bfb  call    cs:__imp_LoadLibraryExW
0x1800b7c02  nop     dword ptr [rax+rax+00h]
0x1800b7c07  mov     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstRegistryDLL
0x1800b7c0e  test    rax, rax
0x1800b7c11  jnz     short loc_1800B7C21
0x1800b7c13  call    cs:__imp_GetLastError
0x1800b7c1a  nop     dword ptr [rax+rax+00h]
0x1800b7c1f  mov     ebx, eax
0x1800b7c21  mov     eax, ebx
0x1800b7c23  add     rsp, 20h
0x1800b7c27  pop     rbx
0x1800b7c28  retn
```

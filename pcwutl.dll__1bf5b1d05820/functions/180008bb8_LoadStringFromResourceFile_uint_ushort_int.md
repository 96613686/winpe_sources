# LoadStringFromResourceFile(uint,ushort *,int)

- ea: `0x180008bb8`
- end: `0x180008c32`
- name: `?LoadStringFromResourceFile@@YAHIPEAGH@Z`
- size: `122`
- prototype: `__int64 __fastcall(UINT uID, LPWSTR lpBuffer, int cchBufferMax)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008c38`
- `0x1800096e0`

## callees

- `0x180008bb8`
- `0x18000e240`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180008c21`
- `KERNEL32!FreeLibrary` at `0x180008c21`
- `KERNEL32!LoadLibraryExW` at `0x180008bf8`
- `KERNEL32!LoadLibraryExW` at `0x180008bf8`
- `USER32!LoadStringW` at `0x180008c11`
- `USER32!LoadStringW` at `0x180008c11`

## string_xrefs

- `0x180008bed`: `pcwutl.dll`

## pseudocode

```c
HMODULE __fastcall LoadStringFromResourceFile(UINT uID, LPWSTR lpBuffer, int cchBufferMax)
{
  HMODULE result; // rax
  HMODULE v7; // rdi
  BOOL v8; // ebx

  AslLogCallPrintf(3, "LoadStringFromResourceFile", 477, "String id: %u", uID);
  result = LoadLibraryExW(L"pcwutl.dll", 0, 0x20u);
  v7 = result;
  if ( result )
  {
    v8 = LoadStringW(result, uID, lpBuffer, cchBufferMax) != 0;
    FreeLibrary(v7);
    return (HMODULE)v8;
  }
  return result;
}

```

## disassembly

```asm
0x180008bb8  push    rbx
0x180008bba  push    rbp
0x180008bbb  push    rsi
0x180008bbc  push    rdi
0x180008bbd  sub     rsp, 38h
0x180008bc1  mov     esi, r8d
0x180008bc4  mov     [rsp+58h+var_38], ecx
0x180008bc8  mov     rbp, rdx
0x180008bcb  lea     r9, aStringIdU; "String id: %u"
0x180008bd2  mov     ebx, ecx
0x180008bd4  lea     rdx, aLoadstringfrom; "LoadStringFromResourceFile"
0x180008bdb  mov     r8d, 1DDh
0x180008be1  mov     ecx, 3
0x180008be6  call    AslLogCallPrintf
0x180008beb  xor     edx, edx; hFile
0x180008bed  lea     rcx, aPcwutlDll_0; "pcwutl.dll"
0x180008bf4  lea     r8d, [rdx+20h]; dwFlags
0x180008bf8  call    cs:__imp_LoadLibraryExW
0x180008bfe  mov     rdi, rax
0x180008c01  test    rax, rax
0x180008c04  jz      short loc_180008C29
0x180008c06  mov     r9d, esi; cchBufferMax
0x180008c09  mov     r8, rbp; lpBuffer
0x180008c0c  mov     edx, ebx; uID
0x180008c0e  mov     rcx, rdi; hInstance
0x180008c11  call    cs:__imp_LoadStringW
0x180008c17  xor     ebx, ebx
0x180008c19  mov     rcx, rdi; hLibModule
0x180008c1c  test    eax, eax
0x180008c1e  setnz   bl
0x180008c21  call    cs:__imp_FreeLibrary
0x180008c27  mov     eax, ebx
0x180008c29  add     rsp, 38h
0x180008c2d  pop     rdi
0x180008c2e  pop     rsi
0x180008c2f  pop     rbp
0x180008c30  pop     rbx
0x180008c31  retn
```

# _bidLoadEntryPoint

- ea: `0x1800c8338`
- end: `0x1800c83ed`
- name: `_bidLoadEntryPoint`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800c8730`

## callees

- `0x1800c8338`
- `0x1800c8688`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800c8361`
- `msvcrt!_wcsicmp` at `0x1800c8361`
- `KERNEL32!LoadLibraryExW` at `0x1800c8380`
- `KERNEL32!LoadLibraryExW` at `0x1800c8380`
- `KERNEL32!GetProcAddress` at `0x1800c83b6`
- `KERNEL32!GetProcAddress` at `0x1800c83b6`

## string_xrefs

- `0x1800c8357`: `MSDADIAG.dll`
- `0x1800c8379`: `MSDADIAG.dll`
- `0x1800c83ac`: `DllBidEntryPoint`

## pseudocode

```c
FARPROC bidLoadEntryPoint()
{
  LPCWSTR v0; // rbx
  DWORD v1; // r8d
  const WCHAR *v2; // rcx
  HMODULE Library; // rax
  FARPROC result; // rax

  v0 = lpOutputString;
  if ( lpOutputString
    && (!dword_180122C38
      ? (Library = hLibModule)
      : (_wcsicmp(lpOutputString, L"MSDADIAG.dll") ? (v1 = 8, v2 = v0) : (v1 = 2048, v2 = L"MSDADIAG.dll"),
         Library = LoadLibraryExW(v2, 0, v1),
         hLibModule = Library),
        Library) )
  {
    result = GetProcAddress(Library, "DllBidEntryPoint");
    bidpEntryPoint = result;
    if ( !result )
      return (FARPROC)bidUnloadEntryPoint();
  }
  else
  {
    result = (FARPROC)ImplBidEntryPoint;
    bidpEntryPoint = ImplBidEntryPoint;
  }
  return result;
}

```

## disassembly

```asm
0x1800c8338  push    rbx
0x1800c833a  sub     rsp, 20h
0x1800c833e  mov     rbx, cs:lpOutputString
0x1800c8345  test    rbx, rbx
0x1800c8348  jz      loc_1800C83D8
0x1800c834e  cmp     cs:dword_180122C38, 0
0x1800c8355  jz      short loc_1800C83A0
0x1800c8357  lea     rdx, aMsdadiagDll; "MSDADIAG.dll"
0x1800c835e  mov     rcx, rbx; String1
0x1800c8361  call    cs:__imp__wcsicmp
0x1800c8368  nop     dword ptr [rax+rax+00h]
0x1800c836d  xor     edx, edx; hFile
0x1800c836f  test    eax, eax
0x1800c8371  jnz     short loc_1800C8395
0x1800c8373  mov     r8d, 800h; dwFlags
0x1800c8379  lea     rcx, aMsdadiagDll; "MSDADIAG.dll"
0x1800c8380  call    cs:__imp_LoadLibraryExW
0x1800c8387  nop     dword ptr [rax+rax+00h]
0x1800c838c  mov     cs:hLibModule, rax
0x1800c8393  jmp     short loc_1800C83A7
0x1800c8395  mov     r8d, 8
0x1800c839b  mov     rcx, rbx
0x1800c839e  jmp     short loc_1800C8380
0x1800c83a0  mov     rax, cs:hLibModule
0x1800c83a7  test    rax, rax
0x1800c83aa  jz      short loc_1800C83D8
0x1800c83ac  lea     rdx, ProcName; "DllBidEntryPoint"
0x1800c83b3  mov     rcx, rax; hModule
0x1800c83b6  call    cs:__imp_GetProcAddress
0x1800c83bd  nop     dword ptr [rax+rax+00h]
0x1800c83c2  mov     cs:_bidpEntryPoint, rax
0x1800c83c9  test    rax, rax
0x1800c83cc  jnz     short loc_1800C83E6
0x1800c83ce  add     rsp, 20h
0x1800c83d2  pop     rbx
0x1800c83d3  jmp     _bidUnloadEntryPoint
0x1800c83d8  lea     rax, ImplBidEntryPoint
0x1800c83df  mov     cs:_bidpEntryPoint, rax
0x1800c83e6  add     rsp, 20h
0x1800c83ea  pop     rbx
0x1800c83eb  retn
```

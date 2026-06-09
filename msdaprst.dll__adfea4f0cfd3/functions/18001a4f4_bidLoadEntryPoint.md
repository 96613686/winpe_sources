# _bidLoadEntryPoint

- ea: `0x18001a4f4`
- end: `0x18001a5a9`
- name: `_bidLoadEntryPoint`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a8f0`

## callees

- `0x18001a4f4`
- `0x18001a848`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001a51d`
- `msvcrt!_wcsicmp` at `0x18001a51d`
- `KERNEL32!GetProcAddress` at `0x18001a572`
- `KERNEL32!GetProcAddress` at `0x18001a572`
- `KERNEL32!LoadLibraryExW` at `0x18001a53c`
- `KERNEL32!LoadLibraryExW` at `0x18001a53c`

## string_xrefs

- `0x18001a513`: `MSDADIAG.dll`
- `0x18001a535`: `MSDADIAG.dll`
- `0x18001a568`: `DllBidEntryPoint`

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
    && (!dword_180046794
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
0x18001a4f4  push    rbx
0x18001a4f6  sub     rsp, 20h
0x18001a4fa  mov     rbx, cs:lpOutputString
0x18001a501  test    rbx, rbx
0x18001a504  jz      loc_18001A594
0x18001a50a  cmp     cs:dword_180046794, 0
0x18001a511  jz      short loc_18001A55C
0x18001a513  lea     rdx, aMsdadiagDll; "MSDADIAG.dll"
0x18001a51a  mov     rcx, rbx; String1
0x18001a51d  call    cs:__imp__wcsicmp
0x18001a524  nop     dword ptr [rax+rax+00h]
0x18001a529  xor     edx, edx; hFile
0x18001a52b  test    eax, eax
0x18001a52d  jnz     short loc_18001A551
0x18001a52f  mov     r8d, 800h; dwFlags
0x18001a535  lea     rcx, aMsdadiagDll; "MSDADIAG.dll"
0x18001a53c  call    cs:__imp_LoadLibraryExW
0x18001a543  nop     dword ptr [rax+rax+00h]
0x18001a548  mov     cs:hLibModule, rax
0x18001a54f  jmp     short loc_18001A563
0x18001a551  mov     r8d, 8
0x18001a557  mov     rcx, rbx
0x18001a55a  jmp     short loc_18001A53C
0x18001a55c  mov     rax, cs:hLibModule
0x18001a563  test    rax, rax
0x18001a566  jz      short loc_18001A594
0x18001a568  lea     rdx, ProcName; "DllBidEntryPoint"
0x18001a56f  mov     rcx, rax; hModule
0x18001a572  call    cs:__imp_GetProcAddress
0x18001a579  nop     dword ptr [rax+rax+00h]
0x18001a57e  mov     cs:_bidpEntryPoint, rax
0x18001a585  test    rax, rax
0x18001a588  jnz     short loc_18001A5A2
0x18001a58a  add     rsp, 20h
0x18001a58e  pop     rbx
0x18001a58f  jmp     _bidUnloadEntryPoint
0x18001a594  lea     rax, ImplBidEntryPoint
0x18001a59b  mov     cs:_bidpEntryPoint, rax
0x18001a5a2  add     rsp, 20h
0x18001a5a6  pop     rbx
0x18001a5a7  retn
```

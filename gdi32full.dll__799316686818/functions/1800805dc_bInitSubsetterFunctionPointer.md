# bInitSubsetterFunctionPointer

- ea: `0x1800805dc`
- end: `0x180080666`
- name: `bInitSubsetterFunctionPointer`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800802e0`
- `0x18008066c`

## callees

- `0x1800805dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008064c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008064c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180080605`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180080605`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080632`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080632`
- `ntdll!RtlEncodePointer` at `0x18008063b`
- `ntdll!RtlEncodePointer` at `0x18008063b`

## string_xrefs

- `0x1800805fc`: `fontsub.dll`
- `0x180080624`: `CreateFontPackage`

## pseudocode

```c
__int64 __fastcall bInitSubsetterFunctionPointer(PVOID *a1)
{
  unsigned int v2; // ebx
  HMODULE Library; // rdi
  const CHAR *v4; // rdx
  FARPROC ProcAddress; // rax
  PVOID v6; // rax

  v2 = 1;
  if ( !*a1 )
  {
    Library = LoadLibraryExW(L"fontsub.dll", 0, 0);
    if ( !Library )
      return 0;
    v4 = "CreateFontPackage";
    if ( a1 != &gfpCreateFontPackage )
      v4 = "MergeFontPackage";
    ProcAddress = GetProcAddress(Library, v4);
    v6 = RtlEncodePointer(ProcAddress);
    *a1 = v6;
    if ( !v6 )
    {
      FreeLibrary(Library);
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800805dc  mov     [rsp+arg_0], rbx
0x1800805e1  mov     [rsp+arg_8], rsi
0x1800805e6  push    rdi
0x1800805e7  sub     rsp, 20h
0x1800805eb  cmp     qword ptr [rcx], 0
0x1800805ef  mov     rsi, rcx
0x1800805f2  mov     ebx, 1
0x1800805f7  jnz     short loc_180080654
0x1800805f9  xor     r8d, r8d; dwFlags
0x1800805fc  lea     rcx, aFontsubDll; "fontsub.dll"
0x180080603  xor     edx, edx; hFile
0x180080605  call    cs:__imp_LoadLibraryExW
0x18008060b  mov     rdi, rax
0x18008060e  test    rax, rax
0x180080611  jz      short loc_180080652
0x180080613  lea     rcx, gfpCreateFontPackage
0x18008061a  cmp     rsi, rcx
0x18008061d  lea     rax, aMergefontpacka; "MergeFontPackage"
0x180080624  lea     rdx, aCreatefontpack; "CreateFontPackage"
0x18008062b  mov     rcx, rdi; hModule
0x18008062e  cmovnz  rdx, rax; lpProcName
0x180080632  call    cs:__imp_GetProcAddress
0x180080638  mov     rcx, rax; Pointer
0x18008063b  call    cs:__imp_RtlEncodePointer
0x180080641  mov     [rsi], rax
0x180080644  test    rax, rax
0x180080647  jnz     short loc_180080654
0x180080649  mov     rcx, rdi; hLibModule
0x18008064c  call    cs:__imp_FreeLibrary
0x180080652  xor     ebx, ebx
0x180080654  mov     rsi, [rsp+28h+arg_8]
0x180080659  mov     eax, ebx
0x18008065b  mov     rbx, [rsp+28h+arg_0]
0x180080660  add     rsp, 20h
0x180080664  pop     rdi
0x180080665  retn
```

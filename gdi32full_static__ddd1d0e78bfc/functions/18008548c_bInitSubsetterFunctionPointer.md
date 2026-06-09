# bInitSubsetterFunctionPointer

- ea: `0x18008548c`
- end: `0x18008552f`
- name: `bInitSubsetterFunctionPointer`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180085150`
- `0x180085538`

## callees

- `0x18008548c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008550e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008550e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800854b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800854b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800854e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800854e8`
- `ntdll!RtlEncodePointer` at `0x1800854f7`
- `ntdll!RtlEncodePointer` at `0x1800854f7`

## string_xrefs

- `0x1800854ac`: `fontsub.dll`
- `0x1800854da`: `CreateFontPackage`

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
0x18008548c  mov     [rsp+arg_0], rbx
0x180085491  mov     [rsp+arg_8], rsi
0x180085496  push    rdi
0x180085497  sub     rsp, 20h
0x18008549b  cmp     qword ptr [rcx], 0
0x18008549f  mov     rsi, rcx
0x1800854a2  mov     ebx, 1
0x1800854a7  jnz     short loc_18008551C
0x1800854a9  xor     r8d, r8d; dwFlags
0x1800854ac  lea     rcx, aFontsubDll; "fontsub.dll"
0x1800854b3  xor     edx, edx; hFile
0x1800854b5  call    cs:__imp_LoadLibraryExW
0x1800854bc  nop     dword ptr [rax+rax+00h]
0x1800854c1  mov     rdi, rax
0x1800854c4  test    rax, rax
0x1800854c7  jz      short loc_18008551A
0x1800854c9  lea     rcx, gfpCreateFontPackage
0x1800854d0  cmp     rsi, rcx
0x1800854d3  lea     rax, aMergefontpacka; "MergeFontPackage"
0x1800854da  lea     rdx, aCreatefontpack; "CreateFontPackage"
0x1800854e1  mov     rcx, rdi; hModule
0x1800854e4  cmovnz  rdx, rax; lpProcName
0x1800854e8  call    cs:__imp_GetProcAddress
0x1800854ef  nop     dword ptr [rax+rax+00h]
0x1800854f4  mov     rcx, rax; Pointer
0x1800854f7  call    cs:__imp_RtlEncodePointer
0x1800854fe  nop     dword ptr [rax+rax+00h]
0x180085503  mov     [rsi], rax
0x180085506  test    rax, rax
0x180085509  jnz     short loc_18008551C
0x18008550b  mov     rcx, rdi; hLibModule
0x18008550e  call    cs:__imp_FreeLibrary
0x180085515  nop     dword ptr [rax+rax+00h]
0x18008551a  xor     ebx, ebx
0x18008551c  mov     rsi, [rsp+28h+arg_8]
0x180085521  mov     eax, ebx
0x180085523  mov     rbx, [rsp+28h+arg_0]
0x180085528  add     rsp, 20h
0x18008552c  pop     rdi
0x18008552d  retn
```

# ValidColorMatchingModule

- ea: `0x18003ce28`
- end: `0x18003cebc`
- name: `ValidColorMatchingModule`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003d6a0`

## callees

- `0x18003ce28`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ceab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ceab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ce50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ce94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ce50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ce94`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003ce38`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003ce38`

## pseudocode

```c
__int64 __fastcall ValidColorMatchingModule(int a1, const WCHAR *a2)
{
  unsigned int v3; // esi
  HMODULE LibraryW; // rax
  HMODULE v5; // rdi
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v7)(__int64); // rbx
  unsigned int i; // ebx

  v3 = 0;
  LibraryW = LoadLibraryW(a2);
  v5 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, gszCMMReqFns);
    v7 = (unsigned int (__fastcall *)(__int64))ProcAddress;
    if ( ProcAddress && ((unsigned int (__fastcall *)(__int64))ProcAddress)(4) >= 0x50000 && v7(1) == a1 )
    {
      for ( i = 1; i < 8; ++i )
      {
        if ( !GetProcAddress(v5, (&gszCMMReqFns)[i]) )
          goto LABEL_10;
      }
      v3 = 1;
    }
LABEL_10:
    FreeLibrary(v5);
  }
  return v3;
}

```

## disassembly

```asm
0x18003ce28  push    rbx
0x18003ce2a  push    rbp
0x18003ce2b  push    rsi
0x18003ce2c  push    rdi
0x18003ce2d  sub     rsp, 28h
0x18003ce31  mov     ebp, ecx
0x18003ce33  xor     esi, esi
0x18003ce35  mov     rcx, rdx; lpLibFileName
0x18003ce38  call    cs:__imp_LoadLibraryW
0x18003ce3e  mov     rdi, rax
0x18003ce41  test    rax, rax
0x18003ce44  jz      short loc_18003CEB1
0x18003ce46  mov     rdx, cs:gszCMMReqFns; lpProcName
0x18003ce4d  mov     rcx, rax; hModule
0x18003ce50  call    cs:__imp_GetProcAddress
0x18003ce56  mov     rbx, rax
0x18003ce59  test    rax, rax
0x18003ce5c  jz      short loc_18003CEA8
0x18003ce5e  lea     ecx, [rsi+4]
0x18003ce61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce66  cmp     eax, 50000h
0x18003ce6b  jb      short loc_18003CEA8
0x18003ce6d  lea     ecx, [rsi+1]
0x18003ce70  mov     rax, rbx
0x18003ce73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce78  cmp     eax, ebp
0x18003ce7a  jnz     short loc_18003CEA8
0x18003ce7c  lea     ebx, [rsi+1]
0x18003ce7f  cmp     ebx, 8
0x18003ce82  jnb     short loc_18003CEA3
0x18003ce84  lea     rax, gszCMMReqFns
0x18003ce8b  mov     edx, ebx
0x18003ce8d  mov     rcx, rdi; hModule
0x18003ce90  mov     rdx, [rax+rdx*8]; lpProcName
0x18003ce94  call    cs:__imp_GetProcAddress
0x18003ce9a  test    rax, rax
0x18003ce9d  jz      short loc_18003CEA8
0x18003ce9f  inc     ebx
0x18003cea1  jmp     short loc_18003CE7F
0x18003cea3  mov     esi, 1
0x18003cea8  mov     rcx, rdi; hLibModule
0x18003ceab  call    cs:__imp_FreeLibrary
0x18003ceb1  mov     eax, esi
0x18003ceb3  add     rsp, 28h
0x18003ceb7  pop     rdi
0x18003ceb8  pop     rsi
0x18003ceb9  pop     rbp
0x18003ceba  pop     rbx
0x18003cebb  retn
```

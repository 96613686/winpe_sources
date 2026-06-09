# try_cor_exit_process

- ea: `0x18001582c`
- end: `0x180015893`
- name: `try_cor_exit_process`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001570c`
- `0x1800157f8`

## callees

- `0x18001582c`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180015854`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180015854`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001586a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001586a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015886`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015886`

## string_xrefs

- `0x18001584b`: `mscoree.dll`

## pseudocode

```c
int __fastcall try_cor_exit_process(unsigned int a1)
{
  FARPROC ProcAddress; // rax
  HMODULE v3; // rcx
  HMODULE phModule; // [rsp+48h] [rbp+10h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExW(0, L"mscoree.dll", &phModule);
  v3 = phModule;
  if ( (_DWORD)ProcAddress )
  {
    ProcAddress = GetProcAddress(phModule, "CorExitProcess");
    if ( ProcAddress )
      LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(a1);
    v3 = phModule;
  }
  if ( v3 )
    LODWORD(ProcAddress) = FreeLibrary(v3);
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x18001582c  push    rbx
0x18001582e  sub     rsp, 30h
0x180015832  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001583b  mov     ebx, ecx
0x18001583d  mov     [rsp+38h+phModule], 0
0x180015846  lea     r8, [rsp+38h+phModule]; phModule
0x18001584b  lea     rdx, ModuleName; "mscoree.dll"
0x180015852  xor     ecx, ecx; dwFlags
0x180015854  call    cs:__imp_GetModuleHandleExW
0x18001585a  mov     rcx, [rsp+38h+phModule]; hModule
0x18001585f  test    eax, eax
0x180015861  jz      short loc_180015881
0x180015863  lea     rdx, ProcName; "CorExitProcess"
0x18001586a  call    cs:__imp_GetProcAddress
0x180015870  test    rax, rax
0x180015873  jz      short loc_18001587C
0x180015875  mov     ecx, ebx
0x180015877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001587c  mov     rcx, [rsp+38h+phModule]; hLibModule
0x180015881  test    rcx, rcx
0x180015884  jz      short loc_18001588D
0x180015886  call    cs:__imp_FreeLibrary
0x18001588c  nop
0x18001588d  add     rsp, 30h
0x180015891  pop     rbx
0x180015892  retn
```

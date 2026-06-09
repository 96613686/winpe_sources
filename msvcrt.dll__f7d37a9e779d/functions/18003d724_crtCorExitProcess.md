# __crtCorExitProcess

- ea: `0x18003d724`
- end: `0x18003d780`
- name: `__crtCorExitProcess`
- size: `92`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003d788`
- `0x18003d7e0`
- `0x18003dcb8`

## callees

- `0x18003d724`
- `0x1800798c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003d743`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003d743`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d767`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d767`

## string_xrefs

- `0x18003d73c`: `mscoree.dll`

## pseudocode

```c
int __fastcall _crtCorExitProcess(unsigned int a1)
{
  FARPROC ProcAddress; // rax
  HMODULE v3; // rcx
  HMODULE phModule; // [rsp+38h] [rbp+10h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExW(0, L"mscoree.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    v3 = phModule;
  }
  else
  {
    v3 = 0;
    phModule = 0;
  }
  if ( v3 )
  {
    ProcAddress = GetProcAddress(v3, "CorExitProcess");
    if ( ProcAddress )
      LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(a1);
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x18003d724  push    rbx
0x18003d726  sub     rsp, 20h
0x18003d72a  mov     ebx, ecx
0x18003d72c  mov     [rsp+28h+phModule], 0
0x18003d735  xor     ecx, ecx; dwFlags
0x18003d737  lea     r8, [rsp+28h+phModule]; phModule
0x18003d73c  lea     rdx, aMscoreeDll; "mscoree.dll"
0x18003d743  call    cs:__imp_GetModuleHandleExW
0x18003d749  test    eax, eax
0x18003d74b  jnz     short loc_18003D756
0x18003d74d  xor     ecx, ecx
0x18003d74f  mov     [rsp+28h+phModule], rcx
0x18003d754  jmp     short loc_18003D75B
0x18003d756  mov     rcx, [rsp+28h+phModule]; hModule
0x18003d75b  test    rcx, rcx
0x18003d75e  jz      short loc_18003D77A
0x18003d760  lea     rdx, aCorexitprocess; "CorExitProcess"
0x18003d767  call    cs:__imp_GetProcAddress
0x18003d76d  test    rax, rax
0x18003d770  jz      short loc_18003D77A
0x18003d772  mov     ecx, ebx
0x18003d774  call    cs:__guard_dispatch_icall_fptr
0x18003d77a  add     rsp, 20h
0x18003d77e  pop     rbx
0x18003d77f  retn
```

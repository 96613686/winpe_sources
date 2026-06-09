# try_cor_exit_process

- ea: `0x1800fb14c`
- end: `0x1800fb1b8`
- name: `try_cor_exit_process`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800faf94`
- `0x1800fb100`

## callees

- `0x18001f050`
- `0x1800fb14c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800fb182`
- `KERNEL32!GetProcAddress` at `0x1800fb182`
- `KERNEL32!FreeLibrary` at `0x1800fb1a7`
- `KERNEL32!FreeLibrary` at `0x1800fb1a7`
- `KERNEL32!GetModuleHandleExW` at `0x1800fb16c`
- `KERNEL32!GetModuleHandleExW` at `0x1800fb16c`

## string_xrefs

- `0x1800fb163`: `mscoree.dll`

## pseudocode

```c
int __fastcall try_cor_exit_process(unsigned int a1)
{
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+38h] [rbp+10h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExW(0, L"mscoree.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    ProcAddress = GetProcAddress(phModule, "CorExitProcess");
    if ( ProcAddress )
      LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(a1);
  }
  if ( phModule )
    LODWORD(ProcAddress) = FreeLibrary(phModule);
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x1800fb14c  mov     [rsp+arg_0], rbx
0x1800fb151  push    rdi
0x1800fb152  sub     rsp, 20h
0x1800fb156  and     [rsp+28h+phModule], 0
0x1800fb15c  lea     r8, [rsp+28h+phModule]; phModule
0x1800fb161  mov     edi, ecx
0x1800fb163  lea     rdx, aMscoreeDll
0x1800fb16a  xor     ecx, ecx; dwFlags
0x1800fb16c  call    cs:__imp_GetModuleHandleExW
0x1800fb172  test    eax, eax
0x1800fb174  jz      short loc_1800FB19D
0x1800fb176  mov     rcx, [rsp+28h+phModule]; hModule
0x1800fb17b  lea     rdx, aCorexitprocess
0x1800fb182  call    cs:__imp_GetProcAddress
0x1800fb188  mov     rbx, rax
0x1800fb18b  test    rax, rax
0x1800fb18e  jz      short loc_1800FB19D
0x1800fb190  mov     rcx, rax
0x1800fb193  call    cs:__guard_check_icall_fptr
0x1800fb199  mov     ecx, edi
0x1800fb19b  call    rbx
0x1800fb19d  mov     rcx, [rsp+28h+phModule]; hLibModule
0x1800fb1a2  test    rcx, rcx
0x1800fb1a5  jz      short loc_1800FB1AD
0x1800fb1a7  call    cs:__imp_FreeLibrary
0x1800fb1ad  mov     rbx, [rsp+28h+arg_0]
0x1800fb1b2  add     rsp, 20h
0x1800fb1b6  pop     rdi
0x1800fb1b7  retn
```

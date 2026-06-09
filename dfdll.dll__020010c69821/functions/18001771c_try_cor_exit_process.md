# try_cor_exit_process

- ea: `0x18001771c`
- end: `0x180017788`
- name: `try_cor_exit_process`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017564`
- `0x1800176d0`

## callees

- `0x180012bf0`
- `0x18001771c`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180017777`
- `KERNEL32!FreeLibrary` at `0x180017777`
- `KERNEL32!GetProcAddress` at `0x180017752`
- `KERNEL32!GetProcAddress` at `0x180017752`
- `KERNEL32!GetModuleHandleExW` at `0x18001773c`
- `KERNEL32!GetModuleHandleExW` at `0x18001773c`

## string_xrefs

- `0x180017733`: `mscoree.dll`

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
0x18001771c  mov     [rsp+arg_0], rbx
0x180017721  push    rdi
0x180017722  sub     rsp, 20h
0x180017726  and     [rsp+28h+phModule], 0
0x18001772c  lea     r8, [rsp+28h+phModule]; phModule
0x180017731  mov     edi, ecx
0x180017733  lea     rdx, aMscoreeDll_0
0x18001773a  xor     ecx, ecx; dwFlags
0x18001773c  call    cs:__imp_GetModuleHandleExW
0x180017742  test    eax, eax
0x180017744  jz      short loc_18001776D
0x180017746  mov     rcx, [rsp+28h+phModule]; hModule
0x18001774b  lea     rdx, aCorexitprocess
0x180017752  call    cs:__imp_GetProcAddress
0x180017758  mov     rbx, rax
0x18001775b  test    rax, rax
0x18001775e  jz      short loc_18001776D
0x180017760  mov     rcx, rax
0x180017763  call    cs:__guard_check_icall_fptr
0x180017769  mov     ecx, edi
0x18001776b  call    rbx
0x18001776d  mov     rcx, [rsp+28h+phModule]; hLibModule
0x180017772  test    rcx, rcx
0x180017775  jz      short loc_18001777D
0x180017777  call    cs:__imp_FreeLibrary
0x18001777d  mov     rbx, [rsp+28h+arg_0]
0x180017782  add     rsp, 20h
0x180017786  pop     rdi
0x180017787  retn
```

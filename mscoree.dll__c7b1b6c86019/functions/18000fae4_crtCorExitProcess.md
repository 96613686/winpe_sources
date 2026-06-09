# __crtCorExitProcess

- ea: `0x18000fae4`
- end: `0x18000fb40`
- name: `__crtCorExitProcess`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fb48`

## callees

- `0x18000fae4`
- `0x180041b90`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000fb27`
- `KERNEL32!GetProcAddress` at `0x18000fb27`
- `KERNEL32!GetModuleHandleExW` at `0x18000fb03`
- `KERNEL32!GetModuleHandleExW` at `0x18000fb03`

## string_xrefs

- `0x18000fafc`: `mscoree.dll`

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
0x18000fae4  push    rbx
0x18000fae6  sub     rsp, 20h
0x18000faea  mov     ebx, ecx
0x18000faec  mov     [rsp+28h+phModule], 0
0x18000faf5  xor     ecx, ecx; dwFlags
0x18000faf7  lea     r8, [rsp+28h+phModule]; phModule
0x18000fafc  lea     rdx, aMscoreeDll_0; "mscoree.dll"
0x18000fb03  call    cs:__imp_GetModuleHandleExW
0x18000fb09  test    eax, eax
0x18000fb0b  jnz     short loc_18000FB16
0x18000fb0d  xor     ecx, ecx
0x18000fb0f  mov     [rsp+28h+phModule], rcx
0x18000fb14  jmp     short loc_18000FB1B
0x18000fb16  mov     rcx, [rsp+28h+phModule]; hModule
0x18000fb1b  test    rcx, rcx
0x18000fb1e  jz      short loc_18000FB3A
0x18000fb20  lea     rdx, aCorexitprocess_1; "CorExitProcess"
0x18000fb27  call    cs:__imp_GetProcAddress
0x18000fb2d  test    rax, rax
0x18000fb30  jz      short loc_18000FB3A
0x18000fb32  mov     ecx, ebx
0x18000fb34  call    cs:__guard_dispatch_icall_fptr
0x18000fb3a  add     rsp, 20h
0x18000fb3e  pop     rbx
0x18000fb3f  retn
```

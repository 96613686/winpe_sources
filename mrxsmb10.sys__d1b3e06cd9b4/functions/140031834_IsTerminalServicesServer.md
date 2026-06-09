# IsTerminalServicesServer

- ea: `0x140031834`
- end: `0x140031901`
- name: `IsTerminalServicesServer`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140032114`

## callees

- `0x140016560`
- `0x1400169c0`
- `0x140031834`

## import_xrefs

- `ntoskrnl!VerSetConditionMask` at `0x14003187c`
- `ntoskrnl!VerSetConditionMask` at `0x1400318bc`
- `ntoskrnl!VerSetConditionMask` at `0x14003187c`
- `ntoskrnl!VerSetConditionMask` at `0x1400318bc`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x140031895`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x1400318d5`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x140031895`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x1400318d5`

## pseudocode

```c
__int64 IsTerminalServicesServer()
{
  ULONGLONG v0; // rax
  ULONGLONG v1; // rax
  struct _OSVERSIONINFOEXW VersionInfo; // [rsp+20h] [rbp-138h] BYREF

  memset(&VersionInfo, 0, sizeof(VersionInfo));
  VersionInfo.dwOSVersionInfoSize = 156;
  VersionInfo.wSuiteMask = 16;
  v0 = VerSetConditionMask(0, 0x40u, 6u);
  if ( RtlVerifyVersionInfo(&VersionInfo, 0x40u, v0) < 0 )
    return 0;
  VersionInfo.wSuiteMask = 256;
  v1 = VerSetConditionMask(0, 0x40u, 6u);
  return (unsigned int)RtlVerifyVersionInfo(&VersionInfo, 0x40u, v1) >> 31;
}

```

## disassembly

```asm
0x140031834  sub     rsp, 158h
0x14003183b  mov     rax, cs:__security_cookie
0x140031842  xor     rax, rsp
0x140031845  mov     [rsp+158h+var_18], rax
0x14003184d  xor     edx, edx; Val
0x14003184f  lea     rcx, [rsp+158h+VersionInfo]; void *
0x140031854  mov     r8d, 11Ch; Size
0x14003185a  call    memset
0x14003185f  mov     eax, 10h
0x140031864  mov     [rsp+158h+VersionInfo.dwOSVersionInfoSize], 9Ch
0x14003186c  mov     r8b, 6; Condition
0x14003186f  mov     [rsp+158h+VersionInfo.wSuiteMask], ax
0x140031877  xor     ecx, ecx; ConditionMask
0x140031879  lea     edx, [rax+30h]; TypeMask
0x14003187c  call    cs:__imp_VerSetConditionMask
0x140031883  nop     dword ptr [rax+rax+00h]
0x140031888  mov     edx, 40h ; '@'; TypeMask
0x14003188d  lea     rcx, [rsp+158h+VersionInfo]; VersionInfo
0x140031892  mov     r8, rax; ConditionMask
0x140031895  call    cs:__imp_RtlVerifyVersionInfo
0x14003189c  nop     dword ptr [rax+rax+00h]
0x1400318a1  test    eax, eax
0x1400318a3  js      short loc_1400318E6
0x1400318a5  mov     eax, 100h
0x1400318aa  mov     r8b, 6; Condition
0x1400318ad  mov     edx, 40h ; '@'; TypeMask
0x1400318b2  mov     [rsp+158h+VersionInfo.wSuiteMask], ax
0x1400318ba  xor     ecx, ecx; ConditionMask
0x1400318bc  call    cs:__imp_VerSetConditionMask
0x1400318c3  nop     dword ptr [rax+rax+00h]
0x1400318c8  mov     edx, 40h ; '@'; TypeMask
0x1400318cd  lea     rcx, [rsp+158h+VersionInfo]; VersionInfo
0x1400318d2  mov     r8, rax; ConditionMask
0x1400318d5  call    cs:__imp_RtlVerifyVersionInfo
0x1400318dc  nop     dword ptr [rax+rax+00h]
0x1400318e1  shr     eax, 1Fh
0x1400318e4  jmp     short loc_1400318E8
0x1400318e6  xor     eax, eax
0x1400318e8  mov     rcx, [rsp+158h+var_18]
0x1400318f0  xor     rcx, rsp; StackCookie
0x1400318f3  call    __security_check_cookie
0x1400318f8  add     rsp, 158h
0x1400318ff  retn
```

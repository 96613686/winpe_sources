# UlpCaptureSecurityDescriptor

- ea: `0x1400ffd4c`
- end: `0x1400ffe45`
- name: `UlpCaptureSecurityDescriptor`
- size: `249`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400fd210`
- `0x140100518`
- `0x140101848`

## callees

- `0x1400ffd4c`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400ffdd3`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400ffdd3`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400ffdef`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400ffdef`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1400ffdb7`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1400ffdb7`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400ffda0`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400ffda0`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1400ffe23`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1400ffe23`

## pseudocode

```c
__int64 __fastcall UlpCaptureSecurityDescriptor(__int64 a1, __int64 a2, PSECURITY_DESCRIPTOR *a3, ULONG *a4)
{
  ULONG *v4; // rdi
  char v6; // bp
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  ULONG v10; // r14d
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+8h] BYREF

  *a3 = 0;
  v4 = a4;
  *a4 = 0;
  SecurityDescriptor = 0;
  v6 = a2;
  if ( a1 )
  {
    LOBYTE(a4) = 1;
    v7 = SeCaptureSecurityDescriptor(a1, a2, 1, a4, &SecurityDescriptor);
    if ( v7 >= 0 )
    {
      if ( RtlValidSecurityDescriptor(SecurityDescriptor)
        && (v10 = RtlLengthSecurityDescriptor(SecurityDescriptor),
            RtlValidRelativeSecurityDescriptor(SecurityDescriptor, v10, 5u)) )
      {
        *a3 = SecurityDescriptor;
        *v4 = v10;
        SecurityDescriptor = 0;
      }
      else
      {
        v7 = -1073741811;
      }
    }
    if ( SecurityDescriptor )
    {
      LOBYTE(v9) = 1;
      LOBYTE(v8) = v6;
      SeReleaseSecurityDescriptor(SecurityDescriptor, v8, v9);
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400ffd4c  mov     [rsp+arg_8], rbx
0x1400ffd51  mov     [rsp+arg_10], rbp
0x1400ffd56  push    rsi
0x1400ffd57  push    rdi
0x1400ffd58  push    r14
0x1400ffd5a  sub     rsp, 30h
0x1400ffd5e  mov     qword ptr [r8], 0
0x1400ffd65  mov     rdi, r9
0x1400ffd68  mov     dword ptr [r9], 0
0x1400ffd6f  mov     rsi, r8
0x1400ffd72  mov     [rsp+48h+SecurityDescriptor], 0
0x1400ffd7b  mov     bpl, dl
0x1400ffd7e  test    rcx, rcx
0x1400ffd81  jnz     short loc_1400FFD8D
0x1400ffd83  mov     ebx, 0C000000Dh
0x1400ffd88  jmp     loc_1400FFE2F
0x1400ffd8d  lea     rax, [rsp+48h+SecurityDescriptor]
0x1400ffd92  mov     r9b, 1
0x1400ffd95  mov     r8d, 1
0x1400ffd9b  mov     [rsp+48h+var_28], rax
0x1400ffda0  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400ffda7  nop     dword ptr [rax+rax+00h]
0x1400ffdac  mov     ebx, eax
0x1400ffdae  test    eax, eax
0x1400ffdb0  js      short loc_1400FFE13
0x1400ffdb2  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1400ffdb7  call    cs:__imp_RtlValidSecurityDescriptor
0x1400ffdbe  nop     dword ptr [rax+rax+00h]
0x1400ffdc3  test    al, al
0x1400ffdc5  jnz     short loc_1400FFDCE
0x1400ffdc7  mov     ebx, 0C000000Dh
0x1400ffdcc  jmp     short loc_1400FFE13
0x1400ffdce  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1400ffdd3  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400ffdda  nop     dword ptr [rax+rax+00h]
0x1400ffddf  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptorInput
0x1400ffde4  mov     r8d, 5; RequiredInformation
0x1400ffdea  mov     edx, eax; SecurityDescriptorLength
0x1400ffdec  mov     r14d, eax
0x1400ffdef  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1400ffdf6  nop     dword ptr [rax+rax+00h]
0x1400ffdfb  test    al, al
0x1400ffdfd  jz      short loc_1400FFDC7
0x1400ffdff  mov     rax, [rsp+48h+SecurityDescriptor]
0x1400ffe04  mov     [rsi], rax
0x1400ffe07  mov     [rdi], r14d
0x1400ffe0a  mov     [rsp+48h+SecurityDescriptor], 0
0x1400ffe13  mov     rcx, [rsp+48h+SecurityDescriptor]
0x1400ffe18  test    rcx, rcx
0x1400ffe1b  jz      short loc_1400FFE2F
0x1400ffe1d  mov     r8b, 1
0x1400ffe20  mov     dl, bpl
0x1400ffe23  call    cs:__imp_SeReleaseSecurityDescriptor
0x1400ffe2a  nop     dword ptr [rax+rax+00h]
0x1400ffe2f  mov     rbp, [rsp+48h+arg_10]
0x1400ffe34  mov     eax, ebx
0x1400ffe36  mov     rbx, [rsp+48h+arg_8]
0x1400ffe3b  add     rsp, 30h
0x1400ffe3f  pop     r14
0x1400ffe41  pop     rdi
0x1400ffe42  pop     rsi
0x1400ffe43  retn
```

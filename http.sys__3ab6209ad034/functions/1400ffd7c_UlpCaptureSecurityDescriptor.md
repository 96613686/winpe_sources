# UlpCaptureSecurityDescriptor

- ea: `0x1400ffd7c`
- end: `0x1400ffe75`
- name: `UlpCaptureSecurityDescriptor`
- size: `249`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400fd240`
- `0x140100548`
- `0x140101878`

## callees

- `0x1400ffd7c`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400ffe03`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400ffe03`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400ffe1f`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400ffe1f`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1400ffde7`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1400ffde7`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400ffdd0`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400ffdd0`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1400ffe53`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1400ffe53`

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
0x1400ffd7c  mov     [rsp+arg_8], rbx
0x1400ffd81  mov     [rsp+arg_10], rbp
0x1400ffd86  push    rsi
0x1400ffd87  push    rdi
0x1400ffd88  push    r14
0x1400ffd8a  sub     rsp, 30h
0x1400ffd8e  mov     qword ptr [r8], 0
0x1400ffd95  mov     rdi, r9
0x1400ffd98  mov     dword ptr [r9], 0
0x1400ffd9f  mov     rsi, r8
0x1400ffda2  mov     [rsp+48h+SecurityDescriptor], 0
0x1400ffdab  mov     bpl, dl
0x1400ffdae  test    rcx, rcx
0x1400ffdb1  jnz     short loc_1400FFDBD
0x1400ffdb3  mov     ebx, 0C000000Dh
0x1400ffdb8  jmp     loc_1400FFE5F
0x1400ffdbd  lea     rax, [rsp+48h+SecurityDescriptor]
0x1400ffdc2  mov     r9b, 1
0x1400ffdc5  mov     r8d, 1
0x1400ffdcb  mov     [rsp+48h+var_28], rax
0x1400ffdd0  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400ffdd7  nop     dword ptr [rax+rax+00h]
0x1400ffddc  mov     ebx, eax
0x1400ffdde  test    eax, eax
0x1400ffde0  js      short loc_1400FFE43
0x1400ffde2  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1400ffde7  call    cs:__imp_RtlValidSecurityDescriptor
0x1400ffdee  nop     dword ptr [rax+rax+00h]
0x1400ffdf3  test    al, al
0x1400ffdf5  jnz     short loc_1400FFDFE
0x1400ffdf7  mov     ebx, 0C000000Dh
0x1400ffdfc  jmp     short loc_1400FFE43
0x1400ffdfe  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1400ffe03  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400ffe0a  nop     dword ptr [rax+rax+00h]
0x1400ffe0f  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptorInput
0x1400ffe14  mov     r8d, 5; RequiredInformation
0x1400ffe1a  mov     edx, eax; SecurityDescriptorLength
0x1400ffe1c  mov     r14d, eax
0x1400ffe1f  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1400ffe26  nop     dword ptr [rax+rax+00h]
0x1400ffe2b  test    al, al
0x1400ffe2d  jz      short loc_1400FFDF7
0x1400ffe2f  mov     rax, [rsp+48h+SecurityDescriptor]
0x1400ffe34  mov     [rsi], rax
0x1400ffe37  mov     [rdi], r14d
0x1400ffe3a  mov     [rsp+48h+SecurityDescriptor], 0
0x1400ffe43  mov     rcx, [rsp+48h+SecurityDescriptor]
0x1400ffe48  test    rcx, rcx
0x1400ffe4b  jz      short loc_1400FFE5F
0x1400ffe4d  mov     r8b, 1
0x1400ffe50  mov     dl, bpl
0x1400ffe53  call    cs:__imp_SeReleaseSecurityDescriptor
0x1400ffe5a  nop     dword ptr [rax+rax+00h]
0x1400ffe5f  mov     rbp, [rsp+48h+arg_10]
0x1400ffe64  mov     eax, ebx
0x1400ffe66  mov     rbx, [rsp+48h+arg_8]
0x1400ffe6b  add     rsp, 30h
0x1400ffe6f  pop     r14
0x1400ffe71  pop     rdi
0x1400ffe72  pop     rsi
0x1400ffe73  retn
```

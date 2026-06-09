# UlpCaptureSecurityDescriptor

- ea: `0x1c011f454`
- end: `0x1c011f541`
- name: `UlpCaptureSecurityDescriptor`
- size: `237`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c00325a8`
- `0x1c0033c2c`
- `0x1c003478c`

## callees

- `0x1c011f454`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1c011f49f`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1c011f49f`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1c011f4b6`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1c011f4b6`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c011f4d2`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c011f4d2`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1c011f4ee`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1c011f4ee`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c011f51f`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c011f51f`

## pseudocode

```c
__int64 __fastcall UlpCaptureSecurityDescriptor(__int64 a1, __int64 a2, _QWORD *a3, ULONG *a4)
{
  ULONG *v4; // rdi
  char v6; // bp
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  ULONG v10; // r14d
  PSECURITY_DESCRIPTOR v11; // rax
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
        v11 = SecurityDescriptor;
        SecurityDescriptor = 0;
        *a3 = v11;
        *v4 = v10;
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
0x1c011f454  mov     [rsp+arg_8], rbx
0x1c011f459  mov     [rsp+arg_10], rbp
0x1c011f45e  push    rsi
0x1c011f45f  push    rdi
0x1c011f460  push    r14
0x1c011f462  sub     rsp, 30h
0x1c011f466  and     qword ptr [r8], 0
0x1c011f46a  mov     rdi, r9
0x1c011f46d  and     dword ptr [r9], 0
0x1c011f471  mov     rsi, r8
0x1c011f474  and     [rsp+48h+SecurityDescriptor], 0
0x1c011f47a  mov     bpl, dl
0x1c011f47d  test    rcx, rcx
0x1c011f480  jnz     short loc_1C011F48C
0x1c011f482  mov     ebx, 0C000000Dh
0x1c011f487  jmp     loc_1C011F52B
0x1c011f48c  lea     rax, [rsp+48h+SecurityDescriptor]
0x1c011f491  mov     r9b, 1
0x1c011f494  mov     r8d, 1
0x1c011f49a  mov     [rsp+48h+var_28], rax
0x1c011f49f  call    cs:__imp_SeCaptureSecurityDescriptor
0x1c011f4a6  nop     dword ptr [rax+rax+00h]
0x1c011f4ab  mov     ebx, eax
0x1c011f4ad  test    eax, eax
0x1c011f4af  js      short loc_1C011F50F
0x1c011f4b1  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1c011f4b6  call    cs:__imp_RtlValidSecurityDescriptor
0x1c011f4bd  nop     dword ptr [rax+rax+00h]
0x1c011f4c2  test    al, al
0x1c011f4c4  jnz     short loc_1C011F4CD
0x1c011f4c6  mov     ebx, 0C000000Dh
0x1c011f4cb  jmp     short loc_1C011F50F
0x1c011f4cd  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1c011f4d2  call    cs:__imp_RtlLengthSecurityDescriptor
0x1c011f4d9  nop     dword ptr [rax+rax+00h]
0x1c011f4de  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptorInput
0x1c011f4e3  mov     r8d, 5; RequiredInformation
0x1c011f4e9  mov     edx, eax; SecurityDescriptorLength
0x1c011f4eb  mov     r14d, eax
0x1c011f4ee  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1c011f4f5  nop     dword ptr [rax+rax+00h]
0x1c011f4fa  test    al, al
0x1c011f4fc  jz      short loc_1C011F4C6
0x1c011f4fe  mov     rax, [rsp+48h+SecurityDescriptor]
0x1c011f503  and     [rsp+48h+SecurityDescriptor], 0
0x1c011f509  mov     [rsi], rax
0x1c011f50c  mov     [rdi], r14d
0x1c011f50f  mov     rcx, [rsp+48h+SecurityDescriptor]
0x1c011f514  test    rcx, rcx
0x1c011f517  jz      short loc_1C011F52B
0x1c011f519  mov     r8b, 1
0x1c011f51c  mov     dl, bpl
0x1c011f51f  call    cs:__imp_SeReleaseSecurityDescriptor
0x1c011f526  nop     dword ptr [rax+rax+00h]
0x1c011f52b  mov     rbp, [rsp+48h+arg_10]
0x1c011f530  mov     eax, ebx
0x1c011f532  mov     rbx, [rsp+48h+arg_8]
0x1c011f537  add     rsp, 30h
0x1c011f53b  pop     r14
0x1c011f53d  pop     rdi
0x1c011f53e  pop     rsi
0x1c011f53f  retn
```

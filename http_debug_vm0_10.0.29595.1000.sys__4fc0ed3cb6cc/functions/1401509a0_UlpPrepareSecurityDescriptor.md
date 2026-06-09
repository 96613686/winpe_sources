# UlpPrepareSecurityDescriptor

- ea: `0x1401509a0`
- end: `0x140150b1b`
- name: `UlpPrepareSecurityDescriptor`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401503f0`

## callees

- `0x1401307bc`
- `0x1401509a0`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140150a44`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140150a44`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x140150a5c`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x140150a5c`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140150a26`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140150a26`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140150a0c`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140150a82`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140150a0c`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140150a82`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140150ad3`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140150af5`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140150ad3`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140150af5`

## pseudocode

```c
__int64 __fastcall UlpPrepareSecurityDescriptor(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        PSECURITY_DESCRIPTOR *a4,
        ULONG *a5)
{
  ULONG *v5; // r14
  PSECURITY_DESCRIPTOR *v6; // rdi
  char v8; // r12
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rdx
  ULONG v12; // r15d
  __int64 v13; // r9
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+30h] BYREF
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF

  v5 = a5;
  v6 = a4;
  SecurityDescriptor = 0;
  v16 = 0;
  v8 = a2;
  *a3 = 0;
  *v5 = 0;
  *a4 = 0;
  if ( !a1 )
    return (unsigned int)-1073741811;
  LOBYTE(a4) = 1;
  v9 = SeCaptureSecurityDescriptor(a1, a2, 1, a4, &SecurityDescriptor);
  if ( v9 < 0 )
    goto LABEL_13;
  if ( RtlValidSecurityDescriptor(SecurityDescriptor)
    && (v12 = RtlLengthSecurityDescriptor(SecurityDescriptor),
        RtlValidRelativeSecurityDescriptor(SecurityDescriptor, v12, 0)) )
  {
    LOBYTE(v13) = 1;
    v9 = SeCaptureSecurityDescriptor(SecurityDescriptor, 0, 1, v13, &v16);
    if ( v9 < 0 )
    {
LABEL_10:
      v16 = 0;
      goto LABEL_11;
    }
    v9 = UlMapGenericMask(v16);
    if ( v9 >= 0 )
    {
      *a3 = v16;
      *v6 = SecurityDescriptor;
      *v5 = v12;
      SecurityDescriptor = 0;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = -1073741811;
  }
LABEL_11:
  if ( !SecurityDescriptor )
    goto LABEL_14;
  LOBYTE(v10) = 1;
  LOBYTE(v11) = v8;
  SeReleaseSecurityDescriptor(SecurityDescriptor, v11, v10);
LABEL_13:
  SecurityDescriptor = 0;
LABEL_14:
  if ( v16 )
  {
    LOBYTE(v10) = 1;
    SeReleaseSecurityDescriptor(v16, 0, v10);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1401509a0  mov     [rsp-28h+arg_8], rbx
0x1401509a5  mov     [rsp-28h+arg_18], rsi
0x1401509aa  push    rbp
0x1401509ab  push    rdi
0x1401509ac  push    r12
0x1401509ae  push    r14
0x1401509b0  push    r15
0x1401509b2  mov     rbp, rsp
0x1401509b5  sub     rsp, 30h
0x1401509b9  mov     r14, [rbp+arg_20]
0x1401509bd  mov     rdi, r9
0x1401509c0  mov     [rbp+SecurityDescriptor], 0
0x1401509c8  mov     rsi, r8
0x1401509cb  mov     [rbp+arg_10], 0
0x1401509d3  mov     r12b, dl
0x1401509d6  mov     qword ptr [r8], 0
0x1401509dd  mov     dword ptr [r14], 0
0x1401509e4  mov     qword ptr [r9], 0
0x1401509eb  test    rcx, rcx
0x1401509ee  jnz     short loc_1401509FA
0x1401509f0  mov     ebx, 0C000000Dh
0x1401509f5  jmp     loc_140150B01
0x1401509fa  lea     rax, [rbp+SecurityDescriptor]
0x1401509fe  mov     r9b, 1
0x140150a01  mov     r8d, 1
0x140150a07  mov     [rsp+30h+var_10], rax
0x140150a0c  call    cs:__imp_SeCaptureSecurityDescriptor
0x140150a13  nop     dword ptr [rax+rax+00h]
0x140150a18  mov     ebx, eax
0x140150a1a  test    eax, eax
0x140150a1c  js      loc_140150ADF
0x140150a22  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140150a26  call    cs:__imp_RtlValidSecurityDescriptor
0x140150a2d  nop     dword ptr [rax+rax+00h]
0x140150a32  test    al, al
0x140150a34  jnz     short loc_140150A40
0x140150a36  mov     ebx, 0C000000Dh
0x140150a3b  jmp     loc_140150AC4
0x140150a40  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140150a44  call    cs:__imp_RtlLengthSecurityDescriptor
0x140150a4b  nop     dword ptr [rax+rax+00h]
0x140150a50  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptorInput
0x140150a54  xor     r8d, r8d; RequiredInformation
0x140150a57  mov     edx, eax; SecurityDescriptorLength
0x140150a59  mov     r15d, eax
0x140150a5c  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x140150a63  nop     dword ptr [rax+rax+00h]
0x140150a68  test    al, al
0x140150a6a  jz      short loc_140150A36
0x140150a6c  mov     rcx, [rbp+SecurityDescriptor]
0x140150a70  lea     rax, [rbp+arg_10]
0x140150a74  xor     edx, edx
0x140150a76  mov     [rsp+30h+var_10], rax
0x140150a7b  mov     r9b, 1
0x140150a7e  lea     r8d, [rdx+1]
0x140150a82  call    cs:__imp_SeCaptureSecurityDescriptor
0x140150a89  nop     dword ptr [rax+rax+00h]
0x140150a8e  mov     ebx, eax
0x140150a90  test    eax, eax
0x140150a92  js      short loc_140150ABC
0x140150a94  mov     rcx, [rbp+arg_10]
0x140150a98  call    UlMapGenericMask
0x140150a9d  mov     ebx, eax
0x140150a9f  test    eax, eax
0x140150aa1  js      short loc_140150AC4
0x140150aa3  mov     rax, [rbp+arg_10]
0x140150aa7  mov     [rsi], rax
0x140150aaa  mov     rax, [rbp+SecurityDescriptor]
0x140150aae  mov     [rdi], rax
0x140150ab1  mov     [r14], r15d
0x140150ab4  mov     [rbp+SecurityDescriptor], 0
0x140150abc  mov     [rbp+arg_10], 0
0x140150ac4  mov     rcx, [rbp+SecurityDescriptor]
0x140150ac8  test    rcx, rcx
0x140150acb  jz      short loc_140150AE7
0x140150acd  mov     r8b, 1
0x140150ad0  mov     dl, r12b
0x140150ad3  call    cs:__imp_SeReleaseSecurityDescriptor
0x140150ada  nop     dword ptr [rax+rax+00h]
0x140150adf  mov     [rbp+SecurityDescriptor], 0
0x140150ae7  mov     rcx, [rbp+arg_10]
0x140150aeb  test    rcx, rcx
0x140150aee  jz      short loc_140150B01
0x140150af0  mov     r8b, 1
0x140150af3  xor     edx, edx
0x140150af5  call    cs:__imp_SeReleaseSecurityDescriptor
0x140150afc  nop     dword ptr [rax+rax+00h]
0x140150b01  mov     rsi, [rsp+30h+arg_18]
0x140150b06  mov     eax, ebx
0x140150b08  mov     rbx, [rsp+30h+arg_8]
0x140150b0d  add     rsp, 30h
0x140150b11  pop     r15
0x140150b13  pop     r14
0x140150b15  pop     r12
0x140150b17  pop     rdi
0x140150b18  pop     rbp
0x140150b19  retn
```

# KappxCheckTrustLabelAce

- ea: `0x18005da64`
- end: `0x18005dc0f`
- name: `KappxCheckTrustLabelAce`
- size: `427`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005d550`

## callees

- `0x18002bf20`
- `0x18005da64`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18005daff`
- `ntoskrnl!ExAllocatePool2` at `0x18005daff`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005dbdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005dbdd`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005dadc`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005db53`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005dadc`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005db53`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005daa9`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005db25`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005daa9`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005db25`
- `ntoskrnl!RtlFindAceByType` at `0x18005dba7`
- `ntoskrnl!RtlFindAceByType` at `0x18005dba7`

## pseudocode

```c
__int64 __fastcall KappxCheckTrustLabelAce(HANDLE Handle, _BYTE *a2)
{
  NTSTATUS v4; // edi
  __int16 *v5; // rbx
  __int16 *Pool2; // rax
  __int16 v7; // ax
  _BYTE *v8; // rcx
  __int64 v9; // rax
  __int64 AceByType; // rax
  ULONG Length; // [rsp+30h] [rbp-69h] BYREF
  int v13[3]; // [rsp+34h] [rbp-65h] BYREF
  _BYTE SecurityDescriptor[128]; // [rsp+40h] [rbp-59h] BYREF

  Length = 128;
  *a2 = 0;
  v13[0] = 0;
  v4 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v5 = (__int16 *)SecurityDescriptor;
  v4 = ZwQuerySecurityObject(Handle, 0x80u, SecurityDescriptor, Length, &Length);
  if ( v4 == -1073741789 )
  {
    Pool2 = (__int16 *)ExAllocatePool2(256, Length, 1483763777);
    v5 = Pool2;
    if ( !Pool2 )
      return (unsigned int)-1073741801;
    v4 = RtlCreateSecurityDescriptor(Pool2, 1u);
    if ( v4 < 0 )
    {
LABEL_23:
      if ( v5 != (__int16 *)SecurityDescriptor )
        ExFreePoolWithTag(v5, 0x58707041u);
      return (unsigned int)v4;
    }
    v4 = ZwQuerySecurityObject(Handle, 0x80u, v5, Length, &Length);
  }
  if ( v4 >= 0 )
  {
    if ( !v5 )
      return (unsigned int)-1073739509;
    while ( 1 )
    {
      v7 = v5[1];
      if ( (v7 & 0x10) == 0 )
        goto LABEL_13;
      if ( v7 >= 0 )
      {
        v8 = (_BYTE *)*((_QWORD *)v5 + 3);
        goto LABEL_18;
      }
      v9 = *((unsigned int *)v5 + 3);
      if ( (_DWORD)v9 )
        v8 = (char *)v5 + v9;
      else
LABEL_13:
        v8 = 0;
LABEL_18:
      AceByType = RtlFindAceByType(v8, 20, v13);
      if ( AceByType && (*(_BYTE *)(AceByType + 1) & 8) == 0 )
      {
        *a2 = 1;
        goto LABEL_23;
      }
      ++v13[0];
      if ( !AceByType )
        goto LABEL_23;
    }
  }
  v4 = 0;
  if ( v5 )
    goto LABEL_23;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005da64  mov     [rsp-8+arg_10], rbx
0x18005da69  push    rbp
0x18005da6a  push    rsi
0x18005da6b  push    rdi
0x18005da6c  push    r14
0x18005da6e  push    r15
0x18005da70  lea     rbp, [rsp-37h]
0x18005da75  sub     rsp, 0D0h
0x18005da7c  mov     rax, cs:__security_cookie
0x18005da83  xor     rax, rsp
0x18005da86  mov     [rbp+57h+var_30], rax
0x18005da8a  xor     r15d, r15d
0x18005da8d  mov     [rbp+57h+Length], 80h
0x18005da94  mov     r14, rdx
0x18005da97  mov     [rdx], r15b
0x18005da9a  mov     rsi, rcx
0x18005da9d  mov     [rbp+57h+var_BC], r15d
0x18005daa1  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18005daa5  lea     edx, [r15+1]; Revision
0x18005daa9  call    cs:__imp_RtlCreateSecurityDescriptor
0x18005dab0  nop     dword ptr [rax+rax+00h]
0x18005dab5  mov     edi, eax
0x18005dab7  test    eax, eax
0x18005dab9  js      loc_18005DBE9
0x18005dabf  mov     r9d, [rbp+57h+Length]; Length
0x18005dac3  lea     rax, [rbp+57h+Length]
0x18005dac7  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18005dacb  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x18005dad0  mov     edx, 80h; SecurityInformation
0x18005dad5  lea     rbx, [rbp+57h+SecurityDescriptor]
0x18005dad9  mov     rcx, rsi; Handle
0x18005dadc  call    cs:__imp_ZwQuerySecurityObject
0x18005dae3  nop     dword ptr [rax+rax+00h]
0x18005dae8  mov     edi, eax
0x18005daea  cmp     eax, 0C0000023h
0x18005daef  jnz     short loc_18005DB61
0x18005daf1  mov     edx, [rbp+57h+Length]
0x18005daf4  mov     ecx, 100h
0x18005daf9  mov     r8d, 58707041h
0x18005daff  call    cs:__imp_ExAllocatePool2
0x18005db06  nop     dword ptr [rax+rax+00h]
0x18005db0b  mov     rbx, rax
0x18005db0e  test    rax, rax
0x18005db11  jnz     short loc_18005DB1D
0x18005db13  mov     edi, 0C0000017h
0x18005db18  jmp     loc_18005DBE9
0x18005db1d  mov     edx, 1; Revision
0x18005db22  mov     rcx, rbx; SecurityDescriptor
0x18005db25  call    cs:__imp_RtlCreateSecurityDescriptor
0x18005db2c  nop     dword ptr [rax+rax+00h]
0x18005db31  mov     edi, eax
0x18005db33  test    eax, eax
0x18005db35  js      loc_18005DBCC
0x18005db3b  mov     r9d, [rbp+57h+Length]; Length
0x18005db3f  lea     rax, [rbp+57h+Length]
0x18005db43  mov     r8, rbx; SecurityDescriptor
0x18005db46  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x18005db4b  mov     edx, 80h; SecurityInformation
0x18005db50  mov     rcx, rsi; Handle
0x18005db53  call    cs:__imp_ZwQuerySecurityObject
0x18005db5a  nop     dword ptr [rax+rax+00h]
0x18005db5f  mov     edi, eax
0x18005db61  test    edi, edi
0x18005db63  jns     short loc_18005DB6F
0x18005db65  mov     edi, r15d
0x18005db68  test    rbx, rbx
0x18005db6b  jz      short loc_18005DBE9
0x18005db6d  jmp     short loc_18005DBCC
0x18005db6f  test    rbx, rbx
0x18005db72  jnz     short loc_18005DB7B
0x18005db74  mov     edi, 0C000090Bh
0x18005db79  jmp     short loc_18005DBE9
0x18005db7b  movzx   eax, word ptr [rbx+2]
0x18005db7f  test    al, 10h
0x18005db81  jnz     short loc_18005DB88
0x18005db83  mov     rcx, r15
0x18005db86  jmp     short loc_18005DB9E
0x18005db88  test    ax, ax
0x18005db8b  jns     short loc_18005DB9A
0x18005db8d  mov     eax, [rbx+0Ch]
0x18005db90  test    eax, eax
0x18005db92  jz      short loc_18005DB83
0x18005db94  lea     rcx, [rbx+rax]
0x18005db98  jmp     short loc_18005DB9E
0x18005db9a  mov     rcx, [rbx+18h]
0x18005db9e  lea     r8, [rbp+57h+var_BC]
0x18005dba2  mov     edx, 14h
0x18005dba7  call    cs:__imp_RtlFindAceByType
0x18005dbae  nop     dword ptr [rax+rax+00h]
0x18005dbb3  test    rax, rax
0x18005dbb6  jz      short loc_18005DBBE
0x18005dbb8  test    byte ptr [rax+1], 8
0x18005dbbc  jz      short loc_18005DBC8
0x18005dbbe  inc     [rbp+57h+var_BC]
0x18005dbc1  test    rax, rax
0x18005dbc4  jnz     short loc_18005DB7B
0x18005dbc6  jmp     short loc_18005DBCC
0x18005dbc8  mov     byte ptr [r14], 1
0x18005dbcc  lea     rax, [rbp+57h+SecurityDescriptor]
0x18005dbd0  cmp     rbx, rax
0x18005dbd3  jz      short loc_18005DBE9
0x18005dbd5  mov     edx, 58707041h; Tag
0x18005dbda  mov     rcx, rbx; P
0x18005dbdd  call    cs:__imp_ExFreePoolWithTag
0x18005dbe4  nop     dword ptr [rax+rax+00h]
0x18005dbe9  mov     eax, edi
0x18005dbeb  mov     rcx, [rbp+57h+var_30]
0x18005dbef  xor     rcx, rsp; StackCookie
0x18005dbf2  call    __security_check_cookie
0x18005dbf7  mov     rbx, [rsp+0F0h+arg_10]
0x18005dbff  add     rsp, 0D0h
0x18005dc06  pop     r15
0x18005dc08  pop     r14
0x18005dc0a  pop     rdi
0x18005dc0b  pop     rsi
0x18005dc0c  pop     rbp
0x18005dc0d  retn
```

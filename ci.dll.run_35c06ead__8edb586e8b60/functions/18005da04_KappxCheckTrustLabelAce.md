# KappxCheckTrustLabelAce

- ea: `0x18005da04`
- end: `0x18005dbaf`
- name: `KappxCheckTrustLabelAce`
- size: `427`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005d4f0`

## callees

- `0x18002c0d0`
- `0x18005da04`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18005da9f`
- `ntoskrnl!ExAllocatePool2` at `0x18005da9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005db7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005db7d`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005da7c`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005daf3`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005da7c`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005daf3`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005da49`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005dac5`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005da49`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005dac5`
- `ntoskrnl!RtlFindAceByType` at `0x18005db47`
- `ntoskrnl!RtlFindAceByType` at `0x18005db47`

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
0x18005da04  mov     [rsp-8+arg_10], rbx
0x18005da09  push    rbp
0x18005da0a  push    rsi
0x18005da0b  push    rdi
0x18005da0c  push    r14
0x18005da0e  push    r15
0x18005da10  lea     rbp, [rsp-37h]
0x18005da15  sub     rsp, 0D0h
0x18005da1c  mov     rax, cs:__security_cookie
0x18005da23  xor     rax, rsp
0x18005da26  mov     [rbp+57h+var_30], rax
0x18005da2a  xor     r15d, r15d
0x18005da2d  mov     [rbp+57h+Length], 80h
0x18005da34  mov     r14, rdx
0x18005da37  mov     [rdx], r15b
0x18005da3a  mov     rsi, rcx
0x18005da3d  mov     [rbp+57h+var_BC], r15d
0x18005da41  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18005da45  lea     edx, [r15+1]; Revision
0x18005da49  call    cs:__imp_RtlCreateSecurityDescriptor
0x18005da50  nop     dword ptr [rax+rax+00h]
0x18005da55  mov     edi, eax
0x18005da57  test    eax, eax
0x18005da59  js      loc_18005DB89
0x18005da5f  mov     r9d, [rbp+57h+Length]; Length
0x18005da63  lea     rax, [rbp+57h+Length]
0x18005da67  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18005da6b  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x18005da70  mov     edx, 80h; SecurityInformation
0x18005da75  lea     rbx, [rbp+57h+SecurityDescriptor]
0x18005da79  mov     rcx, rsi; Handle
0x18005da7c  call    cs:__imp_ZwQuerySecurityObject
0x18005da83  nop     dword ptr [rax+rax+00h]
0x18005da88  mov     edi, eax
0x18005da8a  cmp     eax, 0C0000023h
0x18005da8f  jnz     short loc_18005DB01
0x18005da91  mov     edx, [rbp+57h+Length]
0x18005da94  mov     ecx, 100h
0x18005da99  mov     r8d, 58707041h
0x18005da9f  call    cs:__imp_ExAllocatePool2
0x18005daa6  nop     dword ptr [rax+rax+00h]
0x18005daab  mov     rbx, rax
0x18005daae  test    rax, rax
0x18005dab1  jnz     short loc_18005DABD
0x18005dab3  mov     edi, 0C0000017h
0x18005dab8  jmp     loc_18005DB89
0x18005dabd  mov     edx, 1; Revision
0x18005dac2  mov     rcx, rbx; SecurityDescriptor
0x18005dac5  call    cs:__imp_RtlCreateSecurityDescriptor
0x18005dacc  nop     dword ptr [rax+rax+00h]
0x18005dad1  mov     edi, eax
0x18005dad3  test    eax, eax
0x18005dad5  js      loc_18005DB6C
0x18005dadb  mov     r9d, [rbp+57h+Length]; Length
0x18005dadf  lea     rax, [rbp+57h+Length]
0x18005dae3  mov     r8, rbx; SecurityDescriptor
0x18005dae6  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x18005daeb  mov     edx, 80h; SecurityInformation
0x18005daf0  mov     rcx, rsi; Handle
0x18005daf3  call    cs:__imp_ZwQuerySecurityObject
0x18005dafa  nop     dword ptr [rax+rax+00h]
0x18005daff  mov     edi, eax
0x18005db01  test    edi, edi
0x18005db03  jns     short loc_18005DB0F
0x18005db05  mov     edi, r15d
0x18005db08  test    rbx, rbx
0x18005db0b  jz      short loc_18005DB89
0x18005db0d  jmp     short loc_18005DB6C
0x18005db0f  test    rbx, rbx
0x18005db12  jnz     short loc_18005DB1B
0x18005db14  mov     edi, 0C000090Bh
0x18005db19  jmp     short loc_18005DB89
0x18005db1b  movzx   eax, word ptr [rbx+2]
0x18005db1f  test    al, 10h
0x18005db21  jnz     short loc_18005DB28
0x18005db23  mov     rcx, r15
0x18005db26  jmp     short loc_18005DB3E
0x18005db28  test    ax, ax
0x18005db2b  jns     short loc_18005DB3A
0x18005db2d  mov     eax, [rbx+0Ch]
0x18005db30  test    eax, eax
0x18005db32  jz      short loc_18005DB23
0x18005db34  lea     rcx, [rbx+rax]
0x18005db38  jmp     short loc_18005DB3E
0x18005db3a  mov     rcx, [rbx+18h]
0x18005db3e  lea     r8, [rbp+57h+var_BC]
0x18005db42  mov     edx, 14h
0x18005db47  call    cs:__imp_RtlFindAceByType
0x18005db4e  nop     dword ptr [rax+rax+00h]
0x18005db53  test    rax, rax
0x18005db56  jz      short loc_18005DB5E
0x18005db58  test    byte ptr [rax+1], 8
0x18005db5c  jz      short loc_18005DB68
0x18005db5e  inc     [rbp+57h+var_BC]
0x18005db61  test    rax, rax
0x18005db64  jnz     short loc_18005DB1B
0x18005db66  jmp     short loc_18005DB6C
0x18005db68  mov     byte ptr [r14], 1
0x18005db6c  lea     rax, [rbp+57h+SecurityDescriptor]
0x18005db70  cmp     rbx, rax
0x18005db73  jz      short loc_18005DB89
0x18005db75  mov     edx, 58707041h; Tag
0x18005db7a  mov     rcx, rbx; P
0x18005db7d  call    cs:__imp_ExFreePoolWithTag
0x18005db84  nop     dword ptr [rax+rax+00h]
0x18005db89  mov     eax, edi
0x18005db8b  mov     rcx, [rbp+57h+var_30]
0x18005db8f  xor     rcx, rsp; StackCookie
0x18005db92  call    __security_check_cookie
0x18005db97  mov     rbx, [rsp+0F0h+arg_10]
0x18005db9f  add     rsp, 0D0h
0x18005dba6  pop     r15
0x18005dba8  pop     r14
0x18005dbaa  pop     rdi
0x18005dbab  pop     rsi
0x18005dbac  pop     rbp
0x18005dbad  retn
```

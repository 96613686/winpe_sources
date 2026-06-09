# UlpQueryLogFileSecurity

- ea: `0x140101cc8`
- end: `0x140101e9c`
- name: `UlpQueryLogFileSecurity`
- size: `468`
- prototype: `__int64 __fastcall(HANDLE Handle, PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005bc8c`
- `0x1401002ac`

## callees

- `0x1400ffc60`
- `0x140101cc8`
- `0x14012fd5c`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ZwSetSecurityObject` at `0x140101e44`
- `ntoskrnl!ZwSetSecurityObject` at `0x140101e44`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140101d0b`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140101dd0`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140101d0b`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140101dd0`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140101d4a`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140101daf`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140101d4a`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140101daf`
- `ntoskrnl!RtlEqualSid` at `0x140101dfb`
- `ntoskrnl!RtlEqualSid` at `0x140101dfb`
- `ntoskrnl!ExAllocatePool3` at `0x140101d7c`
- `ntoskrnl!ExAllocatePool3` at `0x140101d7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101e60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101e60`

## pseudocode

```c
__int64 __fastcall UlpQueryLogFileSecurity(HANDLE Handle, PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  NTSTATUS OwnerSecurityDescriptor; // ebx
  void *Pool3; // rsi
  PSID Owner; // [rsp+30h] [rbp-40h] BYREF
  PSID Sid2; // [rsp+38h] [rbp-38h] BYREF
  _OWORD SecurityDescriptora[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v10; // [rsp+60h] [rbp-10h]
  unsigned __int8 OwnerDefaulted; // [rsp+A8h] [rbp+38h] BYREF
  unsigned __int8 v12; // [rsp+B0h] [rbp+40h] BYREF
  ULONG Length; // [rsp+B8h] [rbp+48h] BYREF

  Sid2 = 0;
  v12 = 0;
  Length = 0;
  Owner = 0;
  OwnerDefaulted = 0;
  if ( SecurityDescriptor )
  {
    OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_18;
    if ( !Owner )
      goto LABEL_4;
  }
  if ( ZwQuerySecurityObject(Handle, 1u, 0, 0, &Length) == -1073741789 && Length )
  {
    Pool3 = (void *)ExAllocatePool3(258, Length, 1146317909, UxLowPriorityPool, 1);
    if ( Pool3 )
    {
      OwnerSecurityDescriptor = ZwQuerySecurityObject(Handle, 1u, Pool3, Length, &Length);
      if ( OwnerSecurityDescriptor >= 0 )
      {
        OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(Pool3, &Sid2, &v12);
        if ( OwnerSecurityDescriptor >= 0 )
        {
          if ( Sid2 )
          {
            if ( SecurityDescriptor )
            {
              OwnerSecurityDescriptor = RtlEqualSid(Owner, Sid2) == 0 ? 0xC000005A : 0;
            }
            else
            {
              memset(SecurityDescriptora, 0, sizeof(SecurityDescriptora));
              v10 = 0;
              OwnerSecurityDescriptor = UlpBuildSecurityToLogFile(SecurityDescriptora);
              if ( OwnerSecurityDescriptor >= 0 )
              {
                OwnerSecurityDescriptor = ZwSetSecurityObject(Handle, 4u, SecurityDescriptora);
                UlCleanupSecurityDescriptor(SecurityDescriptora);
              }
            }
          }
          else
          {
            OwnerSecurityDescriptor = -1073741811;
          }
        }
      }
      ExFreePoolWithTag(Pool3, 0);
    }
    else
    {
      OwnerSecurityDescriptor = -1073741670;
    }
  }
  else
  {
LABEL_4:
    OwnerSecurityDescriptor = -1073741811;
  }
LABEL_18:
  if ( (BYTE9(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_d(1291, 40, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids, (unsigned int)OwnerSecurityDescriptor);
  return (unsigned int)OwnerSecurityDescriptor;
}

```

## disassembly

```asm
0x140101cc8  push    rbp
0x140101cca  push    rbx
0x140101ccb  push    rsi
0x140101ccc  push    rdi
0x140101ccd  push    r14
0x140101ccf  mov     rbp, rsp
0x140101cd2  sub     rsp, 70h
0x140101cd6  mov     [rbp+Sid2], 0
0x140101cde  mov     rdi, rdx
0x140101ce1  mov     [rbp+arg_10], 0
0x140101ce5  mov     r14, rcx
0x140101ce8  mov     [rbp+Length], 0
0x140101cef  mov     [rbp+Owner], 0
0x140101cf7  mov     [rbp+OwnerDefaulted], 0
0x140101cfb  test    rdx, rdx
0x140101cfe  jz      short loc_140101D32
0x140101d00  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140101d04  mov     rcx, rdi; SecurityDescriptor
0x140101d07  lea     rdx, [rbp+Owner]; Owner
0x140101d0b  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140101d12  nop     dword ptr [rax+rax+00h]
0x140101d17  mov     ebx, eax
0x140101d19  test    eax, eax
0x140101d1b  js      loc_140101E6C
0x140101d21  cmp     [rbp+Owner], 0
0x140101d26  jnz     short loc_140101D32
0x140101d28  mov     ebx, 0C000000Dh
0x140101d2d  jmp     loc_140101E6C
0x140101d32  xor     r9d, r9d; Length
0x140101d35  lea     rax, [rbp+Length]
0x140101d39  xor     r8d, r8d; SecurityDescriptor
0x140101d3c  mov     [rsp+70h+LengthNeeded], rax; LengthNeeded
0x140101d41  mov     rcx, r14; Handle
0x140101d44  lea     ebx, [r9+1]
0x140101d48  mov     edx, ebx; SecurityInformation
0x140101d4a  call    cs:__imp_ZwQuerySecurityObject
0x140101d51  nop     dword ptr [rax+rax+00h]
0x140101d56  cmp     eax, 0C0000023h
0x140101d5b  jnz     short loc_140101D28
0x140101d5d  mov     eax, [rbp+Length]
0x140101d60  test    eax, eax
0x140101d62  jz      short loc_140101D28
0x140101d64  mov     edx, eax
0x140101d66  mov     dword ptr [rsp+70h+LengthNeeded], ebx
0x140101d6a  lea     r9, UxLowPriorityPool
0x140101d71  mov     ecx, 102h
0x140101d76  mov     r8d, 44536C55h
0x140101d7c  call    cs:__imp_ExAllocatePool3
0x140101d83  nop     dword ptr [rax+rax+00h]
0x140101d88  mov     rsi, rax
0x140101d8b  test    rax, rax
0x140101d8e  jnz     short loc_140101D9A
0x140101d90  mov     ebx, 0C000009Ah
0x140101d95  jmp     loc_140101E6C
0x140101d9a  mov     r9d, [rbp+Length]; Length
0x140101d9e  lea     rax, [rbp+Length]
0x140101da2  mov     r8, rsi; SecurityDescriptor
0x140101da5  mov     [rsp+70h+LengthNeeded], rax; LengthNeeded
0x140101daa  mov     edx, ebx; SecurityInformation
0x140101dac  mov     rcx, r14; Handle
0x140101daf  call    cs:__imp_ZwQuerySecurityObject
0x140101db6  nop     dword ptr [rax+rax+00h]
0x140101dbb  mov     ebx, eax
0x140101dbd  test    eax, eax
0x140101dbf  js      loc_140101E5B
0x140101dc5  lea     r8, [rbp+arg_10]; OwnerDefaulted
0x140101dc9  mov     rcx, rsi; SecurityDescriptor
0x140101dcc  lea     rdx, [rbp+Sid2]; Owner
0x140101dd0  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140101dd7  nop     dword ptr [rax+rax+00h]
0x140101ddc  mov     ebx, eax
0x140101dde  test    eax, eax
0x140101de0  js      short loc_140101E5B
0x140101de2  mov     rdx, [rbp+Sid2]; Sid2
0x140101de6  test    rdx, rdx
0x140101de9  jnz     short loc_140101DF2
0x140101deb  mov     ebx, 0C000000Dh
0x140101df0  jmp     short loc_140101E5B
0x140101df2  test    rdi, rdi
0x140101df5  jz      short loc_140101E15
0x140101df7  mov     rcx, [rbp+Owner]; Sid1
0x140101dfb  call    cs:__imp_RtlEqualSid
0x140101e02  nop     dword ptr [rax+rax+00h]
0x140101e07  neg     al
0x140101e09  sbb     ebx, ebx
0x140101e0b  not     ebx
0x140101e0d  and     ebx, 0C000005Ah
0x140101e13  jmp     short loc_140101E5B
0x140101e15  xorps   xmm0, xmm0
0x140101e18  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140101e1c  xor     eax, eax
0x140101e1e  xor     r8d, r8d
0x140101e21  movups  [rbp+SecurityDescriptor], xmm0
0x140101e25  mov     [rbp+var_10], rax
0x140101e29  movups  [rbp+var_20], xmm0
0x140101e2d  call    UlpBuildSecurityToLogFile
0x140101e32  mov     ebx, eax
0x140101e34  test    eax, eax
0x140101e36  js      short loc_140101E5B
0x140101e38  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140101e3c  mov     edx, 4; SecurityInformation
0x140101e41  mov     rcx, r14; Handle
0x140101e44  call    cs:__imp_ZwSetSecurityObject
0x140101e4b  nop     dword ptr [rax+rax+00h]
0x140101e50  lea     rcx, [rbp+SecurityDescriptor]
0x140101e54  mov     ebx, eax
0x140101e56  call    UlCleanupSecurityDescriptor
0x140101e5b  xor     edx, edx; Tag
0x140101e5d  mov     rcx, rsi; P
0x140101e60  call    cs:__imp_ExFreePoolWithTag
0x140101e67  nop     dword ptr [rax+rax+00h]
0x140101e6c  test    byte ptr cs:xmmword_1401A2CA0+9, 8
0x140101e73  jz      short loc_140101E8E
0x140101e75  mov     edx, 28h ; '('
0x140101e7a  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x140101e81  mov     ecx, 50Bh
0x140101e86  mov     r9d, ebx
0x140101e89  call    WPP_SF_d
0x140101e8e  mov     eax, ebx
0x140101e90  add     rsp, 70h
0x140101e94  pop     r14
0x140101e96  pop     rdi
0x140101e97  pop     rsi
0x140101e98  pop     rbx
0x140101e99  pop     rbp
0x140101e9a  retn
```

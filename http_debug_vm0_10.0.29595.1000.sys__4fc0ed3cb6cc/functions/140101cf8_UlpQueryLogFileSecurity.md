# UlpQueryLogFileSecurity

- ea: `0x140101cf8`
- end: `0x140101ecc`
- name: `UlpQueryLogFileSecurity`
- size: `468`
- prototype: `__int64 __fastcall(HANDLE Handle, PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005bc6c`
- `0x1401002dc`

## callees

- `0x1400ffc90`
- `0x140101cf8`
- `0x14012fe4c`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ZwSetSecurityObject` at `0x140101e74`
- `ntoskrnl!ZwSetSecurityObject` at `0x140101e74`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140101d3b`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140101e00`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140101d3b`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140101e00`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140101d7a`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140101ddf`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140101d7a`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140101ddf`
- `ntoskrnl!RtlEqualSid` at `0x140101e2b`
- `ntoskrnl!RtlEqualSid` at `0x140101e2b`
- `ntoskrnl!ExAllocatePool3` at `0x140101dac`
- `ntoskrnl!ExAllocatePool3` at `0x140101dac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101e90`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101e90`

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
0x140101cf8  push    rbp
0x140101cfa  push    rbx
0x140101cfb  push    rsi
0x140101cfc  push    rdi
0x140101cfd  push    r14
0x140101cff  mov     rbp, rsp
0x140101d02  sub     rsp, 70h
0x140101d06  mov     [rbp+Sid2], 0
0x140101d0e  mov     rdi, rdx
0x140101d11  mov     [rbp+arg_10], 0
0x140101d15  mov     r14, rcx
0x140101d18  mov     [rbp+Length], 0
0x140101d1f  mov     [rbp+Owner], 0
0x140101d27  mov     [rbp+OwnerDefaulted], 0
0x140101d2b  test    rdx, rdx
0x140101d2e  jz      short loc_140101D62
0x140101d30  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140101d34  mov     rcx, rdi; SecurityDescriptor
0x140101d37  lea     rdx, [rbp+Owner]; Owner
0x140101d3b  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140101d42  nop     dword ptr [rax+rax+00h]
0x140101d47  mov     ebx, eax
0x140101d49  test    eax, eax
0x140101d4b  js      loc_140101E9C
0x140101d51  cmp     [rbp+Owner], 0
0x140101d56  jnz     short loc_140101D62
0x140101d58  mov     ebx, 0C000000Dh
0x140101d5d  jmp     loc_140101E9C
0x140101d62  xor     r9d, r9d; Length
0x140101d65  lea     rax, [rbp+Length]
0x140101d69  xor     r8d, r8d; SecurityDescriptor
0x140101d6c  mov     [rsp+70h+LengthNeeded], rax; LengthNeeded
0x140101d71  mov     rcx, r14; Handle
0x140101d74  lea     ebx, [r9+1]
0x140101d78  mov     edx, ebx; SecurityInformation
0x140101d7a  call    cs:__imp_ZwQuerySecurityObject
0x140101d81  nop     dword ptr [rax+rax+00h]
0x140101d86  cmp     eax, 0C0000023h
0x140101d8b  jnz     short loc_140101D58
0x140101d8d  mov     eax, [rbp+Length]
0x140101d90  test    eax, eax
0x140101d92  jz      short loc_140101D58
0x140101d94  mov     edx, eax
0x140101d96  mov     dword ptr [rsp+70h+LengthNeeded], ebx
0x140101d9a  lea     r9, UxLowPriorityPool
0x140101da1  mov     ecx, 102h
0x140101da6  mov     r8d, 44536C55h
0x140101dac  call    cs:__imp_ExAllocatePool3
0x140101db3  nop     dword ptr [rax+rax+00h]
0x140101db8  mov     rsi, rax
0x140101dbb  test    rax, rax
0x140101dbe  jnz     short loc_140101DCA
0x140101dc0  mov     ebx, 0C000009Ah
0x140101dc5  jmp     loc_140101E9C
0x140101dca  mov     r9d, [rbp+Length]; Length
0x140101dce  lea     rax, [rbp+Length]
0x140101dd2  mov     r8, rsi; SecurityDescriptor
0x140101dd5  mov     [rsp+70h+LengthNeeded], rax; LengthNeeded
0x140101dda  mov     edx, ebx; SecurityInformation
0x140101ddc  mov     rcx, r14; Handle
0x140101ddf  call    cs:__imp_ZwQuerySecurityObject
0x140101de6  nop     dword ptr [rax+rax+00h]
0x140101deb  mov     ebx, eax
0x140101ded  test    eax, eax
0x140101def  js      loc_140101E8B
0x140101df5  lea     r8, [rbp+arg_10]; OwnerDefaulted
0x140101df9  mov     rcx, rsi; SecurityDescriptor
0x140101dfc  lea     rdx, [rbp+Sid2]; Owner
0x140101e00  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140101e07  nop     dword ptr [rax+rax+00h]
0x140101e0c  mov     ebx, eax
0x140101e0e  test    eax, eax
0x140101e10  js      short loc_140101E8B
0x140101e12  mov     rdx, [rbp+Sid2]; Sid2
0x140101e16  test    rdx, rdx
0x140101e19  jnz     short loc_140101E22
0x140101e1b  mov     ebx, 0C000000Dh
0x140101e20  jmp     short loc_140101E8B
0x140101e22  test    rdi, rdi
0x140101e25  jz      short loc_140101E45
0x140101e27  mov     rcx, [rbp+Owner]; Sid1
0x140101e2b  call    cs:__imp_RtlEqualSid
0x140101e32  nop     dword ptr [rax+rax+00h]
0x140101e37  neg     al
0x140101e39  sbb     ebx, ebx
0x140101e3b  not     ebx
0x140101e3d  and     ebx, 0C000005Ah
0x140101e43  jmp     short loc_140101E8B
0x140101e45  xorps   xmm0, xmm0
0x140101e48  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140101e4c  xor     eax, eax
0x140101e4e  xor     r8d, r8d
0x140101e51  movups  [rbp+SecurityDescriptor], xmm0
0x140101e55  mov     [rbp+var_10], rax
0x140101e59  movups  [rbp+var_20], xmm0
0x140101e5d  call    UlpBuildSecurityToLogFile
0x140101e62  mov     ebx, eax
0x140101e64  test    eax, eax
0x140101e66  js      short loc_140101E8B
0x140101e68  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140101e6c  mov     edx, 4; SecurityInformation
0x140101e71  mov     rcx, r14; Handle
0x140101e74  call    cs:__imp_ZwSetSecurityObject
0x140101e7b  nop     dword ptr [rax+rax+00h]
0x140101e80  lea     rcx, [rbp+SecurityDescriptor]
0x140101e84  mov     ebx, eax
0x140101e86  call    UlCleanupSecurityDescriptor
0x140101e8b  xor     edx, edx; Tag
0x140101e8d  mov     rcx, rsi; P
0x140101e90  call    cs:__imp_ExFreePoolWithTag
0x140101e97  nop     dword ptr [rax+rax+00h]
0x140101e9c  test    byte ptr cs:xmmword_1401A2CA0+9, 8
0x140101ea3  jz      short loc_140101EBE
0x140101ea5  mov     edx, 28h ; '('
0x140101eaa  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x140101eb1  mov     ecx, 50Bh
0x140101eb6  mov     r9d, ebx
0x140101eb9  call    WPP_SF_d
0x140101ebe  mov     eax, ebx
0x140101ec0  add     rsp, 70h
0x140101ec4  pop     r14
0x140101ec6  pop     rdi
0x140101ec7  pop     rsi
0x140101ec8  pop     rbx
0x140101ec9  pop     rbp
0x140101eca  retn
```

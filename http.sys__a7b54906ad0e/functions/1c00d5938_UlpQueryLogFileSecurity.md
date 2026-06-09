# UlpQueryLogFileSecurity

- ea: `0x1c00d5938`
- end: `0x1c00d5a9a`
- name: `UlpQueryLogFileSecurity`
- size: `354`
- prototype: `__int64 __fastcall(HANDLE Handle, PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0017ce8`
- `0x1c0017e30`

## callees

- `0x1c0018040`
- `0x1c008f374`
- `0x1c00d5938`
- `0x1c00d5aa0`

## import_xrefs

- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1c00d5972`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1c00d5a24`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1c00d5972`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1c00d5a24`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1c00d59ab`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1c00d5a07`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1c00d59ab`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1c00d5a07`
- `ntoskrnl!RtlEqualSid` at `0x1c00d5a4c`
- `ntoskrnl!RtlEqualSid` at `0x1c00d5a4c`
- `ntoskrnl!ZwSetSecurityObject` at `0x1c00fd5ad`
- `ntoskrnl!ZwSetSecurityObject` at `0x1c00fd5ad`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d59da`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d59da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d5a69`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d5a69`

## pseudocode

```c
__int64 __fastcall UlpQueryLogFileSecurity(HANDLE Handle, PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  NTSTATUS OwnerSecurityDescriptor; // ebx
  PVOID PoolWithTagPriority; // rsi
  PSID Owner; // [rsp+30h] [rbp-40h] BYREF
  PSID Sid2; // [rsp+38h] [rbp-38h] BYREF
  _OWORD SecurityDescriptora[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v10; // [rsp+60h] [rbp-10h]
  unsigned __int8 OwnerDefaulted; // [rsp+A8h] [rbp+38h] BYREF
  unsigned __int8 v12; // [rsp+B0h] [rbp+40h] BYREF
  ULONG Length; // [rsp+B8h] [rbp+48h] BYREF

  Sid2 = 0;
  Length = 0;
  Owner = 0;
  v12 = 0;
  OwnerDefaulted = 0;
  if ( SecurityDescriptor )
  {
    OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_13;
    if ( !Owner )
      goto LABEL_17;
  }
  if ( ZwQuerySecurityObject(Handle, 1u, 0, 0, &Length) == -1073741789 && Length )
  {
    PoolWithTagPriority = ExAllocatePoolWithTagPriority(PagedPool, Length, 0x44536C55u, LowPoolPriority);
    if ( PoolWithTagPriority )
    {
      OwnerSecurityDescriptor = ZwQuerySecurityObject(Handle, 1u, PoolWithTagPriority, Length, &Length);
      if ( OwnerSecurityDescriptor >= 0 )
      {
        OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(PoolWithTagPriority, &Sid2, &v12);
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
      ExFreePoolWithTag(PoolWithTagPriority, 0);
    }
    else
    {
      OwnerSecurityDescriptor = -1073741670;
    }
  }
  else
  {
LABEL_17:
    OwnerSecurityDescriptor = -1073741811;
  }
LABEL_13:
  if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x400) != 0 )
    WPP_SF_D(38, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids);
  return (unsigned int)OwnerSecurityDescriptor;
}

```

## disassembly

```asm
0x1c00d5938  push    rbp
0x1c00d593a  push    rbx
0x1c00d593b  push    rsi
0x1c00d593c  push    rdi
0x1c00d593d  push    r14
0x1c00d593f  mov     rbp, rsp
0x1c00d5942  sub     rsp, 70h
0x1c00d5946  and     [rbp+Sid2], 0
0x1c00d594b  mov     rdi, rdx
0x1c00d594e  and     [rbp+Length], 0
0x1c00d5952  mov     r14, rcx
0x1c00d5955  and     [rbp+Owner], 0
0x1c00d595a  mov     [rbp+arg_10], 0
0x1c00d595e  mov     [rbp+OwnerDefaulted], 0
0x1c00d5962  test    rdx, rdx
0x1c00d5965  jz      short loc_1C00D5993
0x1c00d5967  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1c00d596b  mov     rcx, rdi; SecurityDescriptor
0x1c00d596e  lea     rdx, [rbp+Owner]; Owner
0x1c00d5972  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1c00d5979  nop     dword ptr [rax+rax+00h]
0x1c00d597e  mov     ebx, eax
0x1c00d5980  test    eax, eax
0x1c00d5982  js      loc_1C00D5A75
0x1c00d5988  cmp     [rbp+Owner], 0
0x1c00d598d  jz      loc_1C00FD566
0x1c00d5993  xor     r9d, r9d; Length
0x1c00d5996  lea     rax, [rbp+Length]
0x1c00d599a  xor     r8d, r8d; SecurityDescriptor
0x1c00d599d  mov     [rsp+70h+LengthNeeded], rax; LengthNeeded
0x1c00d59a2  mov     rcx, r14; Handle
0x1c00d59a5  lea     ebx, [r9+1]
0x1c00d59a9  mov     edx, ebx; SecurityInformation
0x1c00d59ab  call    cs:__imp_ZwQuerySecurityObject
0x1c00d59b2  nop     dword ptr [rax+rax+00h]
0x1c00d59b7  cmp     eax, 0C0000023h
0x1c00d59bc  jnz     loc_1C00FD566
0x1c00d59c2  mov     eax, [rbp+Length]
0x1c00d59c5  test    eax, eax
0x1c00d59c7  jz      loc_1C00FD566
0x1c00d59cd  mov     edx, eax; NumberOfBytes
0x1c00d59cf  xor     r9d, r9d; Priority
0x1c00d59d2  mov     r8d, 44536C55h; Tag
0x1c00d59d8  mov     ecx, ebx; PoolType
0x1c00d59da  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00d59e1  nop     dword ptr [rax+rax+00h]
0x1c00d59e6  mov     rsi, rax
0x1c00d59e9  test    rax, rax
0x1c00d59ec  jz      loc_1C00FD570
0x1c00d59f2  mov     r9d, [rbp+Length]; Length
0x1c00d59f6  lea     rax, [rbp+Length]
0x1c00d59fa  mov     r8, rsi; SecurityDescriptor
0x1c00d59fd  mov     [rsp+70h+LengthNeeded], rax; LengthNeeded
0x1c00d5a02  mov     edx, ebx; SecurityInformation
0x1c00d5a04  mov     rcx, r14; Handle
0x1c00d5a07  call    cs:__imp_ZwQuerySecurityObject
0x1c00d5a0e  nop     dword ptr [rax+rax+00h]
0x1c00d5a13  mov     ebx, eax
0x1c00d5a15  test    eax, eax
0x1c00d5a17  js      short loc_1C00D5A64
0x1c00d5a19  lea     r8, [rbp+arg_10]; OwnerDefaulted
0x1c00d5a1d  mov     rcx, rsi; SecurityDescriptor
0x1c00d5a20  lea     rdx, [rbp+Sid2]; Owner
0x1c00d5a24  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1c00d5a2b  nop     dword ptr [rax+rax+00h]
0x1c00d5a30  mov     ebx, eax
0x1c00d5a32  test    eax, eax
0x1c00d5a34  js      short loc_1C00D5A64
0x1c00d5a36  mov     rdx, [rbp+Sid2]; Sid2
0x1c00d5a3a  test    rdx, rdx
0x1c00d5a3d  jz      short loc_1C00D5A93
0x1c00d5a3f  test    rdi, rdi
0x1c00d5a42  jz      loc_1C00FD57A
0x1c00d5a48  mov     rcx, [rbp+Owner]; Sid1
0x1c00d5a4c  call    cs:__imp_RtlEqualSid
0x1c00d5a53  nop     dword ptr [rax+rax+00h]
0x1c00d5a58  neg     al
0x1c00d5a5a  sbb     ebx, ebx
0x1c00d5a5c  not     ebx
0x1c00d5a5e  and     ebx, 0C000005Ah
0x1c00d5a64  xor     edx, edx; Tag
0x1c00d5a66  mov     rcx, rsi; P
0x1c00d5a69  call    cs:__imp_ExFreePoolWithTag
0x1c00d5a70  nop     dword ptr [rax+rax+00h]
0x1c00d5a75  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 400h
0x1c00d5a7f  jnz     loc_1C00FD5CA
0x1c00d5a85  mov     eax, ebx
0x1c00d5a87  add     rsp, 70h
0x1c00d5a8b  pop     r14
0x1c00d5a8d  pop     rdi
0x1c00d5a8e  pop     rsi
0x1c00d5a8f  pop     rbx
0x1c00d5a90  pop     rbp
0x1c00d5a91  retn
0x1c00d5a93  mov     ebx, 0C000000Dh
0x1c00d5a98  jmp     short loc_1C00D5A64
0x1c00fd566  mov     ebx, 0C000000Dh
0x1c00fd56b  jmp     loc_1C00D5A75
0x1c00fd570  mov     ebx, 0C000009Ah
0x1c00fd575  jmp     loc_1C00D5A75
0x1c00fd57a  xorps   xmm0, xmm0
0x1c00fd57d  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1c00fd581  xor     eax, eax
0x1c00fd583  xor     r8d, r8d
0x1c00fd586  movups  [rbp+SecurityDescriptor], xmm0
0x1c00fd58a  mov     [rbp+var_10], rax
0x1c00fd58e  movups  [rbp+var_20], xmm0
0x1c00fd592  call    UlpBuildSecurityToLogFile
0x1c00fd597  mov     ebx, eax
0x1c00fd599  test    eax, eax
0x1c00fd59b  js      loc_1C00D5A64
0x1c00fd5a1  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1c00fd5a5  mov     edx, 4; SecurityInformation
0x1c00fd5aa  mov     rcx, r14; Handle
0x1c00fd5ad  call    cs:__imp_ZwSetSecurityObject
0x1c00fd5b4  nop     dword ptr [rax+rax+00h]
0x1c00fd5b9  lea     rcx, [rbp+SecurityDescriptor]
0x1c00fd5bd  mov     ebx, eax
0x1c00fd5bf  call    UlCleanupSecurityDescriptor
0x1c00fd5c4  nop
0x1c00fd5c5  jmp     loc_1C00D5A64
0x1c00fd5ca  mov     ecx, 26h ; '&'
0x1c00fd5cf  lea     rdx, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids
0x1c00fd5d6  mov     r8d, ebx
0x1c00fd5d9  call    WPP_SF_D
0x1c00fd5de  nop
0x1c00fd5df  jmp     loc_1C00D5A85
```

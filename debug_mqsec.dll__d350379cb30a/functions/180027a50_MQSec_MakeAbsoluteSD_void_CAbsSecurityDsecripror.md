# MQSec_MakeAbsoluteSD(void *,CAbsSecurityDsecripror *)

- ea: `0x180027a50`
- end: `0x180027b8b`
- name: `?MQSec_MakeAbsoluteSD@@YA_NPEAXPEAUCAbsSecurityDsecripror@@@Z`
- size: `315`
- prototype: `bool __fastcall(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, struct CAbsSecurityDsecripror *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027ca0`
- `0x180027ed0`

## callees

- `0x18001722c`
- `0x180027398`
- `0x180027a50`

## import_xrefs

- `ADVAPI32!MakeAbsoluteSD` at `0x180027acb`
- `ADVAPI32!MakeAbsoluteSD` at `0x180027b65`
- `ADVAPI32!MakeAbsoluteSD` at `0x180027acb`
- `ADVAPI32!MakeAbsoluteSD` at `0x180027b65`

## pseudocode

```c
bool __fastcall MQSec_MakeAbsoluteSD(
        PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor,
        struct CAbsSecurityDsecripror *a2)
{
  void *v4; // rax
  unsigned __int64 v5; // rcx
  void *v6; // rax
  unsigned __int64 v7; // rcx
  DWORD dwDaclSize; // [rsp+60h] [rbp-10h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize[3]; // [rsp+64h] [rbp-Ch] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+98h] [rbp+28h] BYREF
  DWORD dwOwnerSize; // [rsp+A0h] [rbp+30h] BYREF
  DWORD dwSaclSize; // [rsp+A8h] [rbp+38h] BYREF

  dwAbsoluteSecurityDescriptorSize[0] = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  MakeAbsoluteSD(
    pSelfRelativeSecurityDescriptor,
    0,
    dwAbsoluteSecurityDescriptorSize,
    0,
    &dwDaclSize,
    0,
    &dwSaclSize,
    0,
    &dwOwnerSize,
    0,
    &dwPrimaryGroupSize);
  v4 = MmAllocate(dwAbsoluteSecurityDescriptorSize[0]);
  v5 = dwOwnerSize;
  *((_QWORD *)a2 + 4) = v4;
  v6 = MmAllocate(v5);
  v7 = dwPrimaryGroupSize;
  *(_QWORD *)a2 = v6;
  *((_QWORD *)a2 + 1) = MmAllocate(v7);
  if ( dwDaclSize )
    *((_QWORD *)a2 + 2) = MmAllocate(dwDaclSize);
  if ( dwSaclSize )
    *((_QWORD *)a2 + 3) = MmAllocate(dwSaclSize);
  return MakeAbsoluteSD(
           pSelfRelativeSecurityDescriptor,
           *((PSECURITY_DESCRIPTOR *)a2 + 4),
           dwAbsoluteSecurityDescriptorSize,
           *((PACL *)a2 + 2),
           &dwDaclSize,
           *((PACL *)a2 + 3),
           &dwSaclSize,
           *(PSID *)a2,
           &dwOwnerSize,
           *((PSID *)a2 + 1),
           &dwPrimaryGroupSize)
      || LogGleAssertReturnFalse(0x78u);
}

```

## disassembly

```asm
0x180027a50  mov     r11, rsp
0x180027a53  mov     [r11+8], rbx
0x180027a57  push    rbp
0x180027a58  push    rsi
0x180027a59  push    rdi
0x180027a5a  mov     rbp, rsp
0x180027a5d  sub     rsp, 70h
0x180027a61  lea     rax, [rbp+dwPrimaryGroupSize]
0x180027a65  mov     [rbp+dwAbsoluteSecurityDescriptorSize], 0
0x180027a6c  mov     [r11-38h], rax
0x180027a70  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180027a74  mov     qword ptr [r11-40h], 0
0x180027a7c  lea     rax, [rbp+dwOwnerSize]
0x180027a80  mov     [r11-48h], rax
0x180027a84  mov     rbx, rdx
0x180027a87  mov     qword ptr [r11-50h], 0
0x180027a8f  lea     rax, [rbp+dwSaclSize]
0x180027a93  mov     [r11-58h], rax
0x180027a97  xor     r9d, r9d; pDacl
0x180027a9a  lea     rax, [rbp+dwDaclSize]
0x180027a9e  mov     qword ptr [r11-60h], 0
0x180027aa6  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180027aa8  mov     [r11-68h], rax
0x180027aac  mov     rsi, rcx
0x180027aaf  mov     [rbp+dwDaclSize], 0
0x180027ab6  mov     [rbp+dwSaclSize], 0
0x180027abd  mov     [rbp+dwOwnerSize], 0
0x180027ac4  mov     [rbp+dwPrimaryGroupSize], 0
0x180027acb  call    cs:__imp_MakeAbsoluteSD
0x180027ad1  mov     ecx, [rbp+dwAbsoluteSecurityDescriptorSize]; unsigned __int64
0x180027ad4  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180027ad9  mov     ecx, [rbp+dwOwnerSize]; unsigned __int64
0x180027adc  mov     [rbx+20h], rax
0x180027ae0  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180027ae5  mov     ecx, [rbp+dwPrimaryGroupSize]; unsigned __int64
0x180027ae8  mov     [rbx], rax
0x180027aeb  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180027af0  mov     [rbx+8], rax
0x180027af4  mov     eax, [rbp+dwDaclSize]
0x180027af7  test    eax, eax
0x180027af9  jz      short loc_180027B06
0x180027afb  mov     ecx, eax; unsigned __int64
0x180027afd  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180027b02  mov     [rbx+10h], rax
0x180027b06  mov     eax, [rbp+dwSaclSize]
0x180027b09  test    eax, eax
0x180027b0b  jz      short loc_180027B18
0x180027b0d  mov     ecx, eax; unsigned __int64
0x180027b0f  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180027b14  mov     [rbx+18h], rax
0x180027b18  mov     r9, [rbx+10h]; pDacl
0x180027b1c  lea     rax, [rbp+dwPrimaryGroupSize]
0x180027b20  mov     rdx, [rbx+20h]; pAbsoluteSecurityDescriptor
0x180027b24  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180027b28  mov     [rsp+70h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180027b2d  mov     rcx, rsi; pSelfRelativeSecurityDescriptor
0x180027b30  mov     rax, [rbx+8]
0x180027b34  mov     [rsp+70h+pPrimaryGroup], rax; pPrimaryGroup
0x180027b39  lea     rax, [rbp+dwOwnerSize]
0x180027b3d  mov     [rsp+70h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180027b42  mov     rax, [rbx]
0x180027b45  mov     [rsp+70h+pOwner], rax; pOwner
0x180027b4a  lea     rax, [rbp+dwSaclSize]
0x180027b4e  mov     [rsp+70h+lpdwSaclSize], rax; lpdwSaclSize
0x180027b53  mov     rax, [rbx+18h]
0x180027b57  mov     [rsp+70h+pSacl], rax; pSacl
0x180027b5c  lea     rax, [rbp+dwDaclSize]
0x180027b60  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x180027b65  call    cs:__imp_MakeAbsoluteSD
0x180027b6b  test    eax, eax
0x180027b6d  jnz     short loc_180027B79
0x180027b6f  lea     ecx, [rax+78h]; unsigned __int16
0x180027b72  call    ?LogGleAssertReturnFalse@@YA_NG@Z; LogGleAssertReturnFalse(ushort)
0x180027b77  jmp     short loc_180027B7B
0x180027b79  mov     al, 1
0x180027b7b  mov     rbx, [rsp+70h+arg_0]
0x180027b83  add     rsp, 70h
0x180027b87  pop     rdi
0x180027b88  pop     rsi
0x180027b89  pop     rbp
0x180027b8a  retn
```

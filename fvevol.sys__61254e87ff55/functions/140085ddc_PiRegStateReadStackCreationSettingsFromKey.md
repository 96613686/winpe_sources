# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140085ddc`
- end: `0x140085fbb`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140085fc4`

## callees

- `0x1400216ec`
- `0x140085ddc`
- `0x1400862ac`
- `0x140086544`
- `0x1400867f4`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140085e84`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140085e84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085ead`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085eef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085f83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085ead`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085eef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085f83`

## string_xrefs

- `0x140085e1e`: `Security`

## pseudocode

```c
__int64 __fastcall PiRegStateReadStackCreationSettingsFromKey(HANDLE KeyHandle, __int64 a2)
{
  _DWORD *v2; // r13
  _DWORD *v3; // r15
  _DWORD *v4; // r12
  PVOID v7; // rsi
  NTSTATUS inited; // ebx
  __int64 v9; // r8
  void *v10; // r10
  int FullBuffer; // eax
  __int64 v12; // r9
  PVOID v13; // rax
  int Dword; // eax
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  void *v19; // rcx
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 v23; // [rsp+98h] [rbp+48h] BYREF
  int v24; // [rsp+A0h] [rbp+50h] BYREF
  PVOID SecurityDescriptor; // [rsp+A8h] [rbp+58h] BYREF

  v2 = (_DWORD *)(a2 + 4);
  v3 = (_DWORD *)(a2 + 16);
  *(_DWORD *)a2 = 0;
  v4 = (_DWORD *)(a2 + 20);
  *(_QWORD *)(a2 + 8) = 0;
  SecurityDescriptor = 0;
  v24 = 0;
  v23 = 0;
  P = 0;
  *(_DWORD *)(a2 + 4) = 0;
  v7 = 0;
  *(_DWORD *)(a2 + 16) = 0;
  *(_DWORD *)(a2 + 20) = 0;
  DestinationString = 0;
  inited = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Security");
  if ( inited < 0
    || (FullBuffer = CmRegUtilUcValueGetFullBuffer(KeyHandle, &DestinationString, (__int64)&P),
        v7 = P,
        v10 = 0,
        inited = FullBuffer,
        FullBuffer < 0) )
  {
    if ( inited == -1073741772 )
    {
      SecurityDescriptor = v10;
      inited = (int)v10;
    }
  }
  else
  {
    LOBYTE(v12) = 1;
    inited = SeCaptureSecurityDescriptor((char *)P + *((unsigned int *)P + 2), 0, 1, v12, &SecurityDescriptor);
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( inited < 0 )
    goto LABEL_24;
  if ( SecurityDescriptor )
  {
    inited = SeUtilSecurityInfoFromSecurityDescriptor(SecurityDescriptor, &v23, &v24);
    if ( inited < 0 )
      goto LABEL_24;
    if ( v23 )
    {
      ExFreePoolWithTag(SecurityDescriptor, 0);
    }
    else
    {
      v13 = SecurityDescriptor;
      *(_DWORD *)a2 |= 2u;
      *(_QWORD *)(a2 + 8) = v13;
    }
  }
  Dword = CmRegUtilWstrValueGetDword(KeyHandle, L"DeviceType", v9, v2);
  inited = Dword;
  if ( Dword < 0 )
  {
    if ( Dword != -1073741772 )
      goto LABEL_24;
  }
  else
  {
    *(_DWORD *)a2 |= 1u;
  }
  v16 = CmRegUtilWstrValueGetDword(KeyHandle, L"DeviceCharacteristics", v15, v3);
  inited = v16;
  if ( v16 < 0 )
  {
    if ( v16 != -1073741772 )
      goto LABEL_24;
  }
  else
  {
    *(_DWORD *)a2 |= 4u;
  }
  v18 = CmRegUtilWstrValueGetDword(KeyHandle, L"Exclusive", v17, v4);
  inited = v18;
  if ( v18 >= 0 )
  {
    *(_DWORD *)a2 |= 8u;
    return (unsigned int)inited;
  }
  if ( v18 == -1073741772 )
    return 0;
LABEL_24:
  v19 = *(void **)(a2 + 8);
  if ( v19 )
    ExFreePoolWithTag(v19, 0);
  *(_DWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *v2 = 0;
  *v3 = 0;
  *v4 = 0;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140085ddc  mov     [rsp-38h+arg_0], rbx
0x140085de1  push    rbp
0x140085de2  push    rsi
0x140085de3  push    rdi
0x140085de4  push    r12
0x140085de6  push    r13
0x140085de8  push    r14
0x140085dea  push    r15
0x140085dec  mov     rbp, rsp
0x140085def  sub     rsp, 50h
0x140085df3  xor     r10d, r10d
0x140085df6  lea     r13, [rdx+4]
0x140085dfa  lea     r15, [rdx+10h]
0x140085dfe  mov     [rdx], r10d
0x140085e01  lea     r12, [rdx+14h]
0x140085e05  mov     [rdx+8], r10
0x140085e09  mov     rdi, rdx
0x140085e0c  mov     [rbp+SecurityDescriptor], r10
0x140085e10  mov     r14, rcx
0x140085e13  mov     [rbp+arg_10], r10d
0x140085e17  xorps   xmm0, xmm0
0x140085e1a  mov     [rbp+arg_8], r10b
0x140085e1e  lea     rdx, aSecurity; "Security"
0x140085e25  mov     [rbp+P], r10
0x140085e29  lea     rcx, [rbp+DestinationString]; DestinationString
0x140085e2d  mov     [r13+0], r10d
0x140085e31  mov     esi, r10d
0x140085e34  mov     [r15], r10d
0x140085e37  mov     [r12], r10d
0x140085e3b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140085e3f  call    WdmlibRtlInitUnicodeStringEx
0x140085e44  mov     ebx, eax
0x140085e46  test    eax, eax
0x140085e48  js      short loc_140085E94
0x140085e4a  lea     rax, [rbp+P]
0x140085e4e  mov     rcx, r14; KeyHandle
0x140085e51  lea     rdx, [rbp+DestinationString]; ValueName
0x140085e55  mov     [rsp+50h+var_30], rax; __int64
0x140085e5a  call    CmRegUtilUcValueGetFullBuffer
0x140085e5f  mov     rsi, [rbp+P]
0x140085e63  xor     r10d, r10d
0x140085e66  mov     ebx, eax
0x140085e68  test    eax, eax
0x140085e6a  js      short loc_140085E94
0x140085e6c  mov     ecx, [rsi+8]
0x140085e6f  lea     rax, [rbp+SecurityDescriptor]
0x140085e73  add     rcx, rsi
0x140085e76  mov     [rsp+50h+var_30], rax
0x140085e7b  mov     r9b, 1
0x140085e7e  lea     r8d, [r10+1]
0x140085e82  xor     edx, edx
0x140085e84  call    cs:__imp_SeCaptureSecurityDescriptor
0x140085e8b  nop     dword ptr [rax+rax+00h]
0x140085e90  mov     ebx, eax
0x140085e92  jmp     short loc_140085EA3
0x140085e94  cmp     ebx, 0C0000034h
0x140085e9a  jnz     short loc_140085EA3
0x140085e9c  mov     [rbp+SecurityDescriptor], r10
0x140085ea0  mov     ebx, r10d
0x140085ea3  test    rsi, rsi
0x140085ea6  jz      short loc_140085EB9
0x140085ea8  xor     edx, edx; Tag
0x140085eaa  mov     rcx, rsi; P
0x140085ead  call    cs:__imp_ExFreePoolWithTag
0x140085eb4  nop     dword ptr [rax+rax+00h]
0x140085eb9  xor     esi, esi
0x140085ebb  test    ebx, ebx
0x140085ebd  js      loc_140085F78
0x140085ec3  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140085ec7  test    rcx, rcx
0x140085eca  jz      short loc_140085F08
0x140085ecc  lea     r8, [rbp+arg_10]
0x140085ed0  lea     rdx, [rbp+arg_8]
0x140085ed4  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140085ed9  mov     ebx, eax
0x140085edb  test    eax, eax
0x140085edd  js      loc_140085F78
0x140085ee3  cmp     [rbp+arg_8], sil
0x140085ee7  jz      short loc_140085EFD
0x140085ee9  mov     rcx, [rbp+SecurityDescriptor]; P
0x140085eed  xor     edx, edx; Tag
0x140085eef  call    cs:__imp_ExFreePoolWithTag
0x140085ef6  nop     dword ptr [rax+rax+00h]
0x140085efb  jmp     short loc_140085F08
0x140085efd  mov     rax, [rbp+SecurityDescriptor]
0x140085f01  or      dword ptr [rdi], 2
0x140085f04  mov     [rdi+8], rax
0x140085f08  mov     r9, r13
0x140085f0b  lea     rdx, aDevicetype; "DeviceType"
0x140085f12  mov     rcx, r14
0x140085f15  call    CmRegUtilWstrValueGetDword
0x140085f1a  mov     ebx, eax
0x140085f1c  test    eax, eax
0x140085f1e  js      short loc_140085F25
0x140085f20  or      dword ptr [rdi], 1
0x140085f23  jmp     short loc_140085F2C
0x140085f25  cmp     eax, 0C0000034h
0x140085f2a  jnz     short loc_140085F78
0x140085f2c  mov     r9, r15
0x140085f2f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140085f36  mov     rcx, r14
0x140085f39  call    CmRegUtilWstrValueGetDword
0x140085f3e  mov     ebx, eax
0x140085f40  test    eax, eax
0x140085f42  js      short loc_140085F49
0x140085f44  or      dword ptr [rdi], 4
0x140085f47  jmp     short loc_140085F50
0x140085f49  cmp     eax, 0C0000034h
0x140085f4e  jnz     short loc_140085F78
0x140085f50  mov     r9, r12
0x140085f53  lea     rdx, aExclusive; "Exclusive"
0x140085f5a  mov     rcx, r14
0x140085f5d  call    CmRegUtilWstrValueGetDword
0x140085f62  mov     ebx, eax
0x140085f64  test    eax, eax
0x140085f66  js      short loc_140085F6D
0x140085f68  or      dword ptr [rdi], 8
0x140085f6b  jmp     short loc_140085FA0
0x140085f6d  cmp     eax, 0C0000034h
0x140085f72  jnz     short loc_140085F78
0x140085f74  mov     ebx, esi
0x140085f76  jmp     short loc_140085FA0
0x140085f78  mov     rcx, [rdi+8]; P
0x140085f7c  test    rcx, rcx
0x140085f7f  jz      short loc_140085F8F
0x140085f81  xor     edx, edx; Tag
0x140085f83  call    cs:__imp_ExFreePoolWithTag
0x140085f8a  nop     dword ptr [rax+rax+00h]
0x140085f8f  mov     [rdi], esi
0x140085f91  mov     [rdi+8], rsi
0x140085f95  mov     [r13+0], esi
0x140085f99  mov     [r15], esi
0x140085f9c  mov     [r12], esi
0x140085fa0  mov     eax, ebx
0x140085fa2  mov     rbx, [rsp+50h+arg_0]
0x140085faa  add     rsp, 50h
0x140085fae  pop     r15
0x140085fb0  pop     r14
0x140085fb2  pop     r13
0x140085fb4  pop     r12
0x140085fb6  pop     rdi
0x140085fb7  pop     rsi
0x140085fb8  pop     rbp
0x140085fb9  retn
```

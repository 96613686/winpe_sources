# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140011d2c`
- end: `0x140011f0b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140011f14`

## callees

- `0x1400037b8`
- `0x140011d2c`
- `0x1400121fc`
- `0x140012494`
- `0x140012744`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140011dd4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140011dd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011dfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011ed3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011dfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011ed3`

## string_xrefs

- `0x140011d6e`: `Security`

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
0x140011d2c  mov     [rsp-38h+arg_0], rbx
0x140011d31  push    rbp
0x140011d32  push    rsi
0x140011d33  push    rdi
0x140011d34  push    r12
0x140011d36  push    r13
0x140011d38  push    r14
0x140011d3a  push    r15
0x140011d3c  mov     rbp, rsp
0x140011d3f  sub     rsp, 50h
0x140011d43  xor     r10d, r10d
0x140011d46  lea     r13, [rdx+4]
0x140011d4a  lea     r15, [rdx+10h]
0x140011d4e  mov     [rdx], r10d
0x140011d51  lea     r12, [rdx+14h]
0x140011d55  mov     [rdx+8], r10
0x140011d59  mov     rdi, rdx
0x140011d5c  mov     [rbp+SecurityDescriptor], r10
0x140011d60  mov     r14, rcx
0x140011d63  mov     [rbp+arg_10], r10d
0x140011d67  xorps   xmm0, xmm0
0x140011d6a  mov     [rbp+arg_8], r10b
0x140011d6e  lea     rdx, aSecurity; "Security"
0x140011d75  mov     [rbp+P], r10
0x140011d79  lea     rcx, [rbp+DestinationString]; DestinationString
0x140011d7d  mov     [r13+0], r10d
0x140011d81  mov     esi, r10d
0x140011d84  mov     [r15], r10d
0x140011d87  mov     [r12], r10d
0x140011d8b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140011d8f  call    WdmlibRtlInitUnicodeStringEx
0x140011d94  mov     ebx, eax
0x140011d96  test    eax, eax
0x140011d98  js      short loc_140011DE4
0x140011d9a  lea     rax, [rbp+P]
0x140011d9e  mov     rcx, r14; KeyHandle
0x140011da1  lea     rdx, [rbp+DestinationString]; ValueName
0x140011da5  mov     [rsp+50h+var_30], rax; __int64
0x140011daa  call    CmRegUtilUcValueGetFullBuffer
0x140011daf  mov     rsi, [rbp+P]
0x140011db3  xor     r10d, r10d
0x140011db6  mov     ebx, eax
0x140011db8  test    eax, eax
0x140011dba  js      short loc_140011DE4
0x140011dbc  mov     ecx, [rsi+8]
0x140011dbf  lea     rax, [rbp+SecurityDescriptor]
0x140011dc3  add     rcx, rsi
0x140011dc6  mov     [rsp+50h+var_30], rax
0x140011dcb  mov     r9b, 1
0x140011dce  lea     r8d, [r10+1]
0x140011dd2  xor     edx, edx
0x140011dd4  call    cs:__imp_SeCaptureSecurityDescriptor
0x140011ddb  nop     dword ptr [rax+rax+00h]
0x140011de0  mov     ebx, eax
0x140011de2  jmp     short loc_140011DF3
0x140011de4  cmp     ebx, 0C0000034h
0x140011dea  jnz     short loc_140011DF3
0x140011dec  mov     [rbp+SecurityDescriptor], r10
0x140011df0  mov     ebx, r10d
0x140011df3  test    rsi, rsi
0x140011df6  jz      short loc_140011E09
0x140011df8  xor     edx, edx; Tag
0x140011dfa  mov     rcx, rsi; P
0x140011dfd  call    cs:__imp_ExFreePoolWithTag
0x140011e04  nop     dword ptr [rax+rax+00h]
0x140011e09  xor     esi, esi
0x140011e0b  test    ebx, ebx
0x140011e0d  js      loc_140011EC8
0x140011e13  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140011e17  test    rcx, rcx
0x140011e1a  jz      short loc_140011E58
0x140011e1c  lea     r8, [rbp+arg_10]
0x140011e20  lea     rdx, [rbp+arg_8]
0x140011e24  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140011e29  mov     ebx, eax
0x140011e2b  test    eax, eax
0x140011e2d  js      loc_140011EC8
0x140011e33  cmp     [rbp+arg_8], sil
0x140011e37  jz      short loc_140011E4D
0x140011e39  mov     rcx, [rbp+SecurityDescriptor]; P
0x140011e3d  xor     edx, edx; Tag
0x140011e3f  call    cs:__imp_ExFreePoolWithTag
0x140011e46  nop     dword ptr [rax+rax+00h]
0x140011e4b  jmp     short loc_140011E58
0x140011e4d  mov     rax, [rbp+SecurityDescriptor]
0x140011e51  or      dword ptr [rdi], 2
0x140011e54  mov     [rdi+8], rax
0x140011e58  mov     r9, r13
0x140011e5b  lea     rdx, aDevicetype; "DeviceType"
0x140011e62  mov     rcx, r14
0x140011e65  call    CmRegUtilWstrValueGetDword
0x140011e6a  mov     ebx, eax
0x140011e6c  test    eax, eax
0x140011e6e  js      short loc_140011E75
0x140011e70  or      dword ptr [rdi], 1
0x140011e73  jmp     short loc_140011E7C
0x140011e75  cmp     eax, 0C0000034h
0x140011e7a  jnz     short loc_140011EC8
0x140011e7c  mov     r9, r15
0x140011e7f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140011e86  mov     rcx, r14
0x140011e89  call    CmRegUtilWstrValueGetDword
0x140011e8e  mov     ebx, eax
0x140011e90  test    eax, eax
0x140011e92  js      short loc_140011E99
0x140011e94  or      dword ptr [rdi], 4
0x140011e97  jmp     short loc_140011EA0
0x140011e99  cmp     eax, 0C0000034h
0x140011e9e  jnz     short loc_140011EC8
0x140011ea0  mov     r9, r12
0x140011ea3  lea     rdx, aExclusive; "Exclusive"
0x140011eaa  mov     rcx, r14
0x140011ead  call    CmRegUtilWstrValueGetDword
0x140011eb2  mov     ebx, eax
0x140011eb4  test    eax, eax
0x140011eb6  js      short loc_140011EBD
0x140011eb8  or      dword ptr [rdi], 8
0x140011ebb  jmp     short loc_140011EF0
0x140011ebd  cmp     eax, 0C0000034h
0x140011ec2  jnz     short loc_140011EC8
0x140011ec4  mov     ebx, esi
0x140011ec6  jmp     short loc_140011EF0
0x140011ec8  mov     rcx, [rdi+8]; P
0x140011ecc  test    rcx, rcx
0x140011ecf  jz      short loc_140011EDF
0x140011ed1  xor     edx, edx; Tag
0x140011ed3  call    cs:__imp_ExFreePoolWithTag
0x140011eda  nop     dword ptr [rax+rax+00h]
0x140011edf  mov     [rdi], esi
0x140011ee1  mov     [rdi+8], rsi
0x140011ee5  mov     [r13+0], esi
0x140011ee9  mov     [r15], esi
0x140011eec  mov     [r12], esi
0x140011ef0  mov     eax, ebx
0x140011ef2  mov     rbx, [rsp+50h+arg_0]
0x140011efa  add     rsp, 50h
0x140011efe  pop     r15
0x140011f00  pop     r14
0x140011f02  pop     r13
0x140011f04  pop     r12
0x140011f06  pop     rdi
0x140011f07  pop     rsi
0x140011f08  pop     rbp
0x140011f09  retn
```

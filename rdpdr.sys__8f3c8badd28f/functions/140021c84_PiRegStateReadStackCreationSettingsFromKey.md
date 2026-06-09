# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140021c84`
- end: `0x140021e63`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140021e6c`

## callees

- `0x140005d08`
- `0x140021c84`
- `0x140022154`
- `0x1400223ec`
- `0x14002269c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021d55`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021d97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021e2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021d55`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021d97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021e2b`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140021d2c`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140021d2c`

## string_xrefs

- `0x140021cc6`: `Security`

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
0x140021c84  mov     [rsp-38h+arg_0], rbx
0x140021c89  push    rbp
0x140021c8a  push    rsi
0x140021c8b  push    rdi
0x140021c8c  push    r12
0x140021c8e  push    r13
0x140021c90  push    r14
0x140021c92  push    r15
0x140021c94  mov     rbp, rsp
0x140021c97  sub     rsp, 50h
0x140021c9b  xor     r10d, r10d
0x140021c9e  lea     r13, [rdx+4]
0x140021ca2  lea     r15, [rdx+10h]
0x140021ca6  mov     [rdx], r10d
0x140021ca9  lea     r12, [rdx+14h]
0x140021cad  mov     [rdx+8], r10
0x140021cb1  mov     rdi, rdx
0x140021cb4  mov     [rbp+SecurityDescriptor], r10
0x140021cb8  mov     r14, rcx
0x140021cbb  mov     [rbp+arg_10], r10d
0x140021cbf  xorps   xmm0, xmm0
0x140021cc2  mov     [rbp+arg_8], r10b
0x140021cc6  lea     rdx, aSecurity; "Security"
0x140021ccd  mov     [rbp+P], r10
0x140021cd1  lea     rcx, [rbp+DestinationString]; DestinationString
0x140021cd5  mov     [r13+0], r10d
0x140021cd9  mov     esi, r10d
0x140021cdc  mov     [r15], r10d
0x140021cdf  mov     [r12], r10d
0x140021ce3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140021ce7  call    WdmlibRtlInitUnicodeStringEx
0x140021cec  mov     ebx, eax
0x140021cee  test    eax, eax
0x140021cf0  js      short loc_140021D3C
0x140021cf2  lea     rax, [rbp+P]
0x140021cf6  mov     rcx, r14; KeyHandle
0x140021cf9  lea     rdx, [rbp+DestinationString]; ValueName
0x140021cfd  mov     [rsp+50h+var_30], rax; __int64
0x140021d02  call    CmRegUtilUcValueGetFullBuffer
0x140021d07  mov     rsi, [rbp+P]
0x140021d0b  xor     r10d, r10d
0x140021d0e  mov     ebx, eax
0x140021d10  test    eax, eax
0x140021d12  js      short loc_140021D3C
0x140021d14  mov     ecx, [rsi+8]
0x140021d17  lea     rax, [rbp+SecurityDescriptor]
0x140021d1b  add     rcx, rsi
0x140021d1e  mov     [rsp+50h+var_30], rax
0x140021d23  mov     r9b, 1
0x140021d26  lea     r8d, [r10+1]
0x140021d2a  xor     edx, edx
0x140021d2c  call    cs:__imp_SeCaptureSecurityDescriptor
0x140021d33  nop     dword ptr [rax+rax+00h]
0x140021d38  mov     ebx, eax
0x140021d3a  jmp     short loc_140021D4B
0x140021d3c  cmp     ebx, 0C0000034h
0x140021d42  jnz     short loc_140021D4B
0x140021d44  mov     [rbp+SecurityDescriptor], r10
0x140021d48  mov     ebx, r10d
0x140021d4b  test    rsi, rsi
0x140021d4e  jz      short loc_140021D61
0x140021d50  xor     edx, edx; Tag
0x140021d52  mov     rcx, rsi; P
0x140021d55  call    cs:__imp_ExFreePoolWithTag
0x140021d5c  nop     dword ptr [rax+rax+00h]
0x140021d61  xor     esi, esi
0x140021d63  test    ebx, ebx
0x140021d65  js      loc_140021E20
0x140021d6b  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140021d6f  test    rcx, rcx
0x140021d72  jz      short loc_140021DB0
0x140021d74  lea     r8, [rbp+arg_10]
0x140021d78  lea     rdx, [rbp+arg_8]
0x140021d7c  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140021d81  mov     ebx, eax
0x140021d83  test    eax, eax
0x140021d85  js      loc_140021E20
0x140021d8b  cmp     [rbp+arg_8], sil
0x140021d8f  jz      short loc_140021DA5
0x140021d91  mov     rcx, [rbp+SecurityDescriptor]; P
0x140021d95  xor     edx, edx; Tag
0x140021d97  call    cs:__imp_ExFreePoolWithTag
0x140021d9e  nop     dword ptr [rax+rax+00h]
0x140021da3  jmp     short loc_140021DB0
0x140021da5  mov     rax, [rbp+SecurityDescriptor]
0x140021da9  or      dword ptr [rdi], 2
0x140021dac  mov     [rdi+8], rax
0x140021db0  mov     r9, r13
0x140021db3  lea     rdx, aDevicetype; "DeviceType"
0x140021dba  mov     rcx, r14
0x140021dbd  call    CmRegUtilWstrValueGetDword
0x140021dc2  mov     ebx, eax
0x140021dc4  test    eax, eax
0x140021dc6  js      short loc_140021DCD
0x140021dc8  or      dword ptr [rdi], 1
0x140021dcb  jmp     short loc_140021DD4
0x140021dcd  cmp     eax, 0C0000034h
0x140021dd2  jnz     short loc_140021E20
0x140021dd4  mov     r9, r15
0x140021dd7  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140021dde  mov     rcx, r14
0x140021de1  call    CmRegUtilWstrValueGetDword
0x140021de6  mov     ebx, eax
0x140021de8  test    eax, eax
0x140021dea  js      short loc_140021DF1
0x140021dec  or      dword ptr [rdi], 4
0x140021def  jmp     short loc_140021DF8
0x140021df1  cmp     eax, 0C0000034h
0x140021df6  jnz     short loc_140021E20
0x140021df8  mov     r9, r12
0x140021dfb  lea     rdx, aExclusive; "Exclusive"
0x140021e02  mov     rcx, r14
0x140021e05  call    CmRegUtilWstrValueGetDword
0x140021e0a  mov     ebx, eax
0x140021e0c  test    eax, eax
0x140021e0e  js      short loc_140021E15
0x140021e10  or      dword ptr [rdi], 8
0x140021e13  jmp     short loc_140021E48
0x140021e15  cmp     eax, 0C0000034h
0x140021e1a  jnz     short loc_140021E20
0x140021e1c  mov     ebx, esi
0x140021e1e  jmp     short loc_140021E48
0x140021e20  mov     rcx, [rdi+8]; P
0x140021e24  test    rcx, rcx
0x140021e27  jz      short loc_140021E37
0x140021e29  xor     edx, edx; Tag
0x140021e2b  call    cs:__imp_ExFreePoolWithTag
0x140021e32  nop     dword ptr [rax+rax+00h]
0x140021e37  mov     [rdi], esi
0x140021e39  mov     [rdi+8], rsi
0x140021e3d  mov     [r13+0], esi
0x140021e41  mov     [r15], esi
0x140021e44  mov     [r12], esi
0x140021e48  mov     eax, ebx
0x140021e4a  mov     rbx, [rsp+50h+arg_0]
0x140021e52  add     rsp, 50h
0x140021e56  pop     r15
0x140021e58  pop     r14
0x140021e5a  pop     r13
0x140021e5c  pop     r12
0x140021e5e  pop     rdi
0x140021e5f  pop     rsi
0x140021e60  pop     rbp
0x140021e61  retn
```

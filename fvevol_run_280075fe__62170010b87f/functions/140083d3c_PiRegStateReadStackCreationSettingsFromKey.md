# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140083d3c`
- end: `0x140083f1b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140083f24`

## callees

- `0x140020cdc`
- `0x140083d3c`
- `0x14008420c`
- `0x1400844a4`
- `0x140084754`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140083de4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140083de4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083e0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083e4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083ee3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083e0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083e4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083ee3`

## string_xrefs

- `0x140083d7e`: `Security`

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
0x140083d3c  mov     [rsp-38h+arg_0], rbx
0x140083d41  push    rbp
0x140083d42  push    rsi
0x140083d43  push    rdi
0x140083d44  push    r12
0x140083d46  push    r13
0x140083d48  push    r14
0x140083d4a  push    r15
0x140083d4c  mov     rbp, rsp
0x140083d4f  sub     rsp, 50h
0x140083d53  xor     r10d, r10d
0x140083d56  lea     r13, [rdx+4]
0x140083d5a  lea     r15, [rdx+10h]
0x140083d5e  mov     [rdx], r10d
0x140083d61  lea     r12, [rdx+14h]
0x140083d65  mov     [rdx+8], r10
0x140083d69  mov     rdi, rdx
0x140083d6c  mov     [rbp+SecurityDescriptor], r10
0x140083d70  mov     r14, rcx
0x140083d73  mov     [rbp+arg_10], r10d
0x140083d77  xorps   xmm0, xmm0
0x140083d7a  mov     [rbp+arg_8], r10b
0x140083d7e  lea     rdx, aSecurity; "Security"
0x140083d85  mov     [rbp+P], r10
0x140083d89  lea     rcx, [rbp+DestinationString]; DestinationString
0x140083d8d  mov     [r13+0], r10d
0x140083d91  mov     esi, r10d
0x140083d94  mov     [r15], r10d
0x140083d97  mov     [r12], r10d
0x140083d9b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140083d9f  call    WdmlibRtlInitUnicodeStringEx
0x140083da4  mov     ebx, eax
0x140083da6  test    eax, eax
0x140083da8  js      short loc_140083DF4
0x140083daa  lea     rax, [rbp+P]
0x140083dae  mov     rcx, r14; KeyHandle
0x140083db1  lea     rdx, [rbp+DestinationString]; ValueName
0x140083db5  mov     [rsp+50h+var_30], rax; __int64
0x140083dba  call    CmRegUtilUcValueGetFullBuffer
0x140083dbf  mov     rsi, [rbp+P]
0x140083dc3  xor     r10d, r10d
0x140083dc6  mov     ebx, eax
0x140083dc8  test    eax, eax
0x140083dca  js      short loc_140083DF4
0x140083dcc  mov     ecx, [rsi+8]
0x140083dcf  lea     rax, [rbp+SecurityDescriptor]
0x140083dd3  add     rcx, rsi
0x140083dd6  mov     [rsp+50h+var_30], rax
0x140083ddb  mov     r9b, 1
0x140083dde  lea     r8d, [r10+1]
0x140083de2  xor     edx, edx
0x140083de4  call    cs:__imp_SeCaptureSecurityDescriptor
0x140083deb  nop     dword ptr [rax+rax+00h]
0x140083df0  mov     ebx, eax
0x140083df2  jmp     short loc_140083E03
0x140083df4  cmp     ebx, 0C0000034h
0x140083dfa  jnz     short loc_140083E03
0x140083dfc  mov     [rbp+SecurityDescriptor], r10
0x140083e00  mov     ebx, r10d
0x140083e03  test    rsi, rsi
0x140083e06  jz      short loc_140083E19
0x140083e08  xor     edx, edx; Tag
0x140083e0a  mov     rcx, rsi; P
0x140083e0d  call    cs:__imp_ExFreePoolWithTag
0x140083e14  nop     dword ptr [rax+rax+00h]
0x140083e19  xor     esi, esi
0x140083e1b  test    ebx, ebx
0x140083e1d  js      loc_140083ED8
0x140083e23  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140083e27  test    rcx, rcx
0x140083e2a  jz      short loc_140083E68
0x140083e2c  lea     r8, [rbp+arg_10]
0x140083e30  lea     rdx, [rbp+arg_8]
0x140083e34  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140083e39  mov     ebx, eax
0x140083e3b  test    eax, eax
0x140083e3d  js      loc_140083ED8
0x140083e43  cmp     [rbp+arg_8], sil
0x140083e47  jz      short loc_140083E5D
0x140083e49  mov     rcx, [rbp+SecurityDescriptor]; P
0x140083e4d  xor     edx, edx; Tag
0x140083e4f  call    cs:__imp_ExFreePoolWithTag
0x140083e56  nop     dword ptr [rax+rax+00h]
0x140083e5b  jmp     short loc_140083E68
0x140083e5d  mov     rax, [rbp+SecurityDescriptor]
0x140083e61  or      dword ptr [rdi], 2
0x140083e64  mov     [rdi+8], rax
0x140083e68  mov     r9, r13
0x140083e6b  lea     rdx, aDevicetype; "DeviceType"
0x140083e72  mov     rcx, r14
0x140083e75  call    CmRegUtilWstrValueGetDword
0x140083e7a  mov     ebx, eax
0x140083e7c  test    eax, eax
0x140083e7e  js      short loc_140083E85
0x140083e80  or      dword ptr [rdi], 1
0x140083e83  jmp     short loc_140083E8C
0x140083e85  cmp     eax, 0C0000034h
0x140083e8a  jnz     short loc_140083ED8
0x140083e8c  mov     r9, r15
0x140083e8f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140083e96  mov     rcx, r14
0x140083e99  call    CmRegUtilWstrValueGetDword
0x140083e9e  mov     ebx, eax
0x140083ea0  test    eax, eax
0x140083ea2  js      short loc_140083EA9
0x140083ea4  or      dword ptr [rdi], 4
0x140083ea7  jmp     short loc_140083EB0
0x140083ea9  cmp     eax, 0C0000034h
0x140083eae  jnz     short loc_140083ED8
0x140083eb0  mov     r9, r12
0x140083eb3  lea     rdx, aExclusive; "Exclusive"
0x140083eba  mov     rcx, r14
0x140083ebd  call    CmRegUtilWstrValueGetDword
0x140083ec2  mov     ebx, eax
0x140083ec4  test    eax, eax
0x140083ec6  js      short loc_140083ECD
0x140083ec8  or      dword ptr [rdi], 8
0x140083ecb  jmp     short loc_140083F00
0x140083ecd  cmp     eax, 0C0000034h
0x140083ed2  jnz     short loc_140083ED8
0x140083ed4  mov     ebx, esi
0x140083ed6  jmp     short loc_140083F00
0x140083ed8  mov     rcx, [rdi+8]; P
0x140083edc  test    rcx, rcx
0x140083edf  jz      short loc_140083EEF
0x140083ee1  xor     edx, edx; Tag
0x140083ee3  call    cs:__imp_ExFreePoolWithTag
0x140083eea  nop     dword ptr [rax+rax+00h]
0x140083eef  mov     [rdi], esi
0x140083ef1  mov     [rdi+8], rsi
0x140083ef5  mov     [r13+0], esi
0x140083ef9  mov     [r15], esi
0x140083efc  mov     [r12], esi
0x140083f00  mov     eax, ebx
0x140083f02  mov     rbx, [rsp+50h+arg_0]
0x140083f0a  add     rsp, 50h
0x140083f0e  pop     r15
0x140083f10  pop     r14
0x140083f12  pop     r13
0x140083f14  pop     r12
0x140083f16  pop     rdi
0x140083f17  pop     rsi
0x140083f18  pop     rbp
0x140083f19  retn
```

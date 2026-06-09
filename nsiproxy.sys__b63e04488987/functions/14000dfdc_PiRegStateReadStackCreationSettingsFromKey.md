# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x14000dfdc`
- end: `0x14000e1bb`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000e1c4`

## callees

- `0x140006430`
- `0x14000dfdc`
- `0x14000e4ac`
- `0x14000e744`
- `0x14000e9f4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e0ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e0ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e183`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e0ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e0ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e183`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000e084`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000e084`

## string_xrefs

- `0x14000e01e`: `Security`

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
0x14000dfdc  mov     [rsp-38h+arg_0], rbx
0x14000dfe1  push    rbp
0x14000dfe2  push    rsi
0x14000dfe3  push    rdi
0x14000dfe4  push    r12
0x14000dfe6  push    r13
0x14000dfe8  push    r14
0x14000dfea  push    r15
0x14000dfec  mov     rbp, rsp
0x14000dfef  sub     rsp, 50h
0x14000dff3  xor     r10d, r10d
0x14000dff6  lea     r13, [rdx+4]
0x14000dffa  lea     r15, [rdx+10h]
0x14000dffe  mov     [rdx], r10d
0x14000e001  lea     r12, [rdx+14h]
0x14000e005  mov     [rdx+8], r10
0x14000e009  mov     rdi, rdx
0x14000e00c  mov     [rbp+SecurityDescriptor], r10
0x14000e010  mov     r14, rcx
0x14000e013  mov     [rbp+arg_10], r10d
0x14000e017  xorps   xmm0, xmm0
0x14000e01a  mov     [rbp+arg_8], r10b
0x14000e01e  lea     rdx, aSecurity; "Security"
0x14000e025  mov     [rbp+P], r10
0x14000e029  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e02d  mov     [r13+0], r10d
0x14000e031  mov     esi, r10d
0x14000e034  mov     [r15], r10d
0x14000e037  mov     [r12], r10d
0x14000e03b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e03f  call    WdmlibRtlInitUnicodeStringEx
0x14000e044  mov     ebx, eax
0x14000e046  test    eax, eax
0x14000e048  js      short loc_14000E094
0x14000e04a  lea     rax, [rbp+P]
0x14000e04e  mov     rcx, r14; KeyHandle
0x14000e051  lea     rdx, [rbp+DestinationString]; ValueName
0x14000e055  mov     [rsp+50h+var_30], rax; __int64
0x14000e05a  call    CmRegUtilUcValueGetFullBuffer
0x14000e05f  mov     rsi, [rbp+P]
0x14000e063  xor     r10d, r10d
0x14000e066  mov     ebx, eax
0x14000e068  test    eax, eax
0x14000e06a  js      short loc_14000E094
0x14000e06c  mov     ecx, [rsi+8]
0x14000e06f  lea     rax, [rbp+SecurityDescriptor]
0x14000e073  add     rcx, rsi
0x14000e076  mov     [rsp+50h+var_30], rax
0x14000e07b  mov     r9b, 1
0x14000e07e  lea     r8d, [r10+1]
0x14000e082  xor     edx, edx
0x14000e084  call    cs:__imp_SeCaptureSecurityDescriptor
0x14000e08b  nop     dword ptr [rax+rax+00h]
0x14000e090  mov     ebx, eax
0x14000e092  jmp     short loc_14000E0A3
0x14000e094  cmp     ebx, 0C0000034h
0x14000e09a  jnz     short loc_14000E0A3
0x14000e09c  mov     [rbp+SecurityDescriptor], r10
0x14000e0a0  mov     ebx, r10d
0x14000e0a3  test    rsi, rsi
0x14000e0a6  jz      short loc_14000E0B9
0x14000e0a8  xor     edx, edx; Tag
0x14000e0aa  mov     rcx, rsi; P
0x14000e0ad  call    cs:__imp_ExFreePoolWithTag
0x14000e0b4  nop     dword ptr [rax+rax+00h]
0x14000e0b9  xor     esi, esi
0x14000e0bb  test    ebx, ebx
0x14000e0bd  js      loc_14000E178
0x14000e0c3  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000e0c7  test    rcx, rcx
0x14000e0ca  jz      short loc_14000E108
0x14000e0cc  lea     r8, [rbp+arg_10]
0x14000e0d0  lea     rdx, [rbp+arg_8]
0x14000e0d4  call    SeUtilSecurityInfoFromSecurityDescriptor
0x14000e0d9  mov     ebx, eax
0x14000e0db  test    eax, eax
0x14000e0dd  js      loc_14000E178
0x14000e0e3  cmp     [rbp+arg_8], sil
0x14000e0e7  jz      short loc_14000E0FD
0x14000e0e9  mov     rcx, [rbp+SecurityDescriptor]; P
0x14000e0ed  xor     edx, edx; Tag
0x14000e0ef  call    cs:__imp_ExFreePoolWithTag
0x14000e0f6  nop     dword ptr [rax+rax+00h]
0x14000e0fb  jmp     short loc_14000E108
0x14000e0fd  mov     rax, [rbp+SecurityDescriptor]
0x14000e101  or      dword ptr [rdi], 2
0x14000e104  mov     [rdi+8], rax
0x14000e108  mov     r9, r13
0x14000e10b  lea     rdx, aDevicetype; "DeviceType"
0x14000e112  mov     rcx, r14
0x14000e115  call    CmRegUtilWstrValueGetDword
0x14000e11a  mov     ebx, eax
0x14000e11c  test    eax, eax
0x14000e11e  js      short loc_14000E125
0x14000e120  or      dword ptr [rdi], 1
0x14000e123  jmp     short loc_14000E12C
0x14000e125  cmp     eax, 0C0000034h
0x14000e12a  jnz     short loc_14000E178
0x14000e12c  mov     r9, r15
0x14000e12f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x14000e136  mov     rcx, r14
0x14000e139  call    CmRegUtilWstrValueGetDword
0x14000e13e  mov     ebx, eax
0x14000e140  test    eax, eax
0x14000e142  js      short loc_14000E149
0x14000e144  or      dword ptr [rdi], 4
0x14000e147  jmp     short loc_14000E150
0x14000e149  cmp     eax, 0C0000034h
0x14000e14e  jnz     short loc_14000E178
0x14000e150  mov     r9, r12
0x14000e153  lea     rdx, aExclusive; "Exclusive"
0x14000e15a  mov     rcx, r14
0x14000e15d  call    CmRegUtilWstrValueGetDword
0x14000e162  mov     ebx, eax
0x14000e164  test    eax, eax
0x14000e166  js      short loc_14000E16D
0x14000e168  or      dword ptr [rdi], 8
0x14000e16b  jmp     short loc_14000E1A0
0x14000e16d  cmp     eax, 0C0000034h
0x14000e172  jnz     short loc_14000E178
0x14000e174  mov     ebx, esi
0x14000e176  jmp     short loc_14000E1A0
0x14000e178  mov     rcx, [rdi+8]; P
0x14000e17c  test    rcx, rcx
0x14000e17f  jz      short loc_14000E18F
0x14000e181  xor     edx, edx; Tag
0x14000e183  call    cs:__imp_ExFreePoolWithTag
0x14000e18a  nop     dword ptr [rax+rax+00h]
0x14000e18f  mov     [rdi], esi
0x14000e191  mov     [rdi+8], rsi
0x14000e195  mov     [r13+0], esi
0x14000e199  mov     [r15], esi
0x14000e19c  mov     [r12], esi
0x14000e1a0  mov     eax, ebx
0x14000e1a2  mov     rbx, [rsp+50h+arg_0]
0x14000e1aa  add     rsp, 50h
0x14000e1ae  pop     r15
0x14000e1b0  pop     r14
0x14000e1b2  pop     r13
0x14000e1b4  pop     r12
0x14000e1b6  pop     rdi
0x14000e1b7  pop     rsi
0x14000e1b8  pop     rbp
0x14000e1b9  retn
```

# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140150dcc`
- end: `0x140150fab`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140150fb4`

## callees

- `0x140078840`
- `0x140150dcc`
- `0x14015129c`
- `0x140151534`
- `0x1401517e4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140150e9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150edf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150f73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150e9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150edf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150f73`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140150e74`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140150e74`

## string_xrefs

- `0x140150e0e`: `Security`

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
  void *v10; // r9
  int FullBuffer; // eax
  PVOID v12; // rax
  int Dword; // eax
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // r8
  int v17; // eax
  void *v18; // rcx
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 v22; // [rsp+98h] [rbp+48h] BYREF
  int v23; // [rsp+A0h] [rbp+50h] BYREF
  PVOID SecurityDescriptor; // [rsp+A8h] [rbp+58h] BYREF

  v2 = (_DWORD *)(a2 + 4);
  *(_DWORD *)a2 = 0;
  v3 = (_DWORD *)(a2 + 16);
  *(_QWORD *)(a2 + 8) = 0;
  v4 = (_DWORD *)(a2 + 20);
  SecurityDescriptor = 0;
  v23 = 0;
  v22 = 0;
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
    LOBYTE(v10) = 1;
    inited = SeCaptureSecurityDescriptor((char *)P + *((unsigned int *)P + 2), 0, 1, v10, &SecurityDescriptor);
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( inited < 0 )
    goto LABEL_24;
  if ( SecurityDescriptor )
  {
    inited = SeUtilSecurityInfoFromSecurityDescriptor(SecurityDescriptor, &v22, &v23);
    if ( inited < 0 )
      goto LABEL_24;
    if ( v22 )
    {
      ExFreePoolWithTag(SecurityDescriptor, 0);
    }
    else
    {
      v12 = SecurityDescriptor;
      *(_DWORD *)a2 |= 2u;
      *(_QWORD *)(a2 + 8) = v12;
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
  v15 = CmRegUtilWstrValueGetDword(KeyHandle, L"DeviceCharacteristics", v14, v3);
  inited = v15;
  if ( v15 < 0 )
  {
    if ( v15 != -1073741772 )
      goto LABEL_24;
  }
  else
  {
    *(_DWORD *)a2 |= 4u;
  }
  v17 = CmRegUtilWstrValueGetDword(KeyHandle, L"Exclusive", v16, v4);
  inited = v17;
  if ( v17 >= 0 )
  {
    *(_DWORD *)a2 |= 8u;
    return (unsigned int)inited;
  }
  if ( v17 == -1073741772 )
    return 0;
LABEL_24:
  v18 = *(void **)(a2 + 8);
  if ( v18 )
    ExFreePoolWithTag(v18, 0);
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
0x140150dcc  mov     [rsp-38h+arg_0], rbx
0x140150dd1  push    rbp
0x140150dd2  push    rsi
0x140150dd3  push    rdi
0x140150dd4  push    r12
0x140150dd6  push    r13
0x140150dd8  push    r14
0x140150dda  push    r15
0x140150ddc  mov     rbp, rsp
0x140150ddf  sub     rsp, 50h
0x140150de3  xor     r9d, r9d
0x140150de6  lea     r13, [rdx+4]
0x140150dea  mov     [rdx], r9d
0x140150ded  lea     r15, [rdx+10h]
0x140150df1  mov     [rdx+8], r9
0x140150df5  lea     r12, [rdx+14h]
0x140150df9  mov     r14, rcx
0x140150dfc  mov     [rbp+SecurityDescriptor], r9
0x140150e00  mov     rdi, rdx
0x140150e03  mov     [rbp+arg_10], r9d
0x140150e07  xorps   xmm0, xmm0
0x140150e0a  mov     [rbp+arg_8], r9b
0x140150e0e  lea     rdx, aSecurity; "Security"
0x140150e15  mov     [rbp+P], r9
0x140150e19  lea     rcx, [rbp+DestinationString]; DestinationString
0x140150e1d  mov     [r13+0], r9d
0x140150e21  mov     esi, r9d
0x140150e24  mov     [r15], r9d
0x140150e27  mov     [r12], r9d
0x140150e2b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140150e2f  call    WdmlibRtlInitUnicodeStringEx
0x140150e34  mov     ebx, eax
0x140150e36  test    eax, eax
0x140150e38  js      short loc_140150E84
0x140150e3a  lea     rax, [rbp+P]
0x140150e3e  mov     rcx, r14; KeyHandle
0x140150e41  lea     rdx, [rbp+DestinationString]; ValueName
0x140150e45  mov     [rsp+50h+var_30], rax; __int64
0x140150e4a  call    CmRegUtilUcValueGetFullBuffer
0x140150e4f  mov     rsi, [rbp+P]
0x140150e53  xor     r9d, r9d
0x140150e56  mov     ebx, eax
0x140150e58  test    eax, eax
0x140150e5a  js      short loc_140150E84
0x140150e5c  mov     ecx, [rsi+8]
0x140150e5f  lea     rax, [rbp+SecurityDescriptor]
0x140150e63  xor     edx, edx
0x140150e65  mov     [rsp+50h+var_30], rax
0x140150e6a  add     rcx, rsi
0x140150e6d  mov     r9b, 1
0x140150e70  lea     r8d, [rdx+1]
0x140150e74  call    cs:__imp_SeCaptureSecurityDescriptor
0x140150e7b  nop     dword ptr [rax+rax+00h]
0x140150e80  mov     ebx, eax
0x140150e82  jmp     short loc_140150E93
0x140150e84  cmp     ebx, 0C0000034h
0x140150e8a  jnz     short loc_140150E93
0x140150e8c  mov     [rbp+SecurityDescriptor], r9
0x140150e90  mov     ebx, r9d
0x140150e93  test    rsi, rsi
0x140150e96  jz      short loc_140150EA9
0x140150e98  xor     edx, edx; Tag
0x140150e9a  mov     rcx, rsi; P
0x140150e9d  call    cs:__imp_ExFreePoolWithTag
0x140150ea4  nop     dword ptr [rax+rax+00h]
0x140150ea9  xor     esi, esi
0x140150eab  test    ebx, ebx
0x140150ead  js      loc_140150F68
0x140150eb3  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140150eb7  test    rcx, rcx
0x140150eba  jz      short loc_140150EF8
0x140150ebc  lea     r8, [rbp+arg_10]
0x140150ec0  lea     rdx, [rbp+arg_8]
0x140150ec4  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140150ec9  mov     ebx, eax
0x140150ecb  test    eax, eax
0x140150ecd  js      loc_140150F68
0x140150ed3  cmp     [rbp+arg_8], sil
0x140150ed7  jz      short loc_140150EED
0x140150ed9  mov     rcx, [rbp+SecurityDescriptor]; P
0x140150edd  xor     edx, edx; Tag
0x140150edf  call    cs:__imp_ExFreePoolWithTag
0x140150ee6  nop     dword ptr [rax+rax+00h]
0x140150eeb  jmp     short loc_140150EF8
0x140150eed  mov     rax, [rbp+SecurityDescriptor]
0x140150ef1  or      dword ptr [rdi], 2
0x140150ef4  mov     [rdi+8], rax
0x140150ef8  mov     r9, r13
0x140150efb  lea     rdx, aDevicetype; "DeviceType"
0x140150f02  mov     rcx, r14
0x140150f05  call    CmRegUtilWstrValueGetDword
0x140150f0a  mov     ebx, eax
0x140150f0c  test    eax, eax
0x140150f0e  js      short loc_140150F15
0x140150f10  or      dword ptr [rdi], 1
0x140150f13  jmp     short loc_140150F1C
0x140150f15  cmp     eax, 0C0000034h
0x140150f1a  jnz     short loc_140150F68
0x140150f1c  mov     r9, r15
0x140150f1f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140150f26  mov     rcx, r14
0x140150f29  call    CmRegUtilWstrValueGetDword
0x140150f2e  mov     ebx, eax
0x140150f30  test    eax, eax
0x140150f32  js      short loc_140150F39
0x140150f34  or      dword ptr [rdi], 4
0x140150f37  jmp     short loc_140150F40
0x140150f39  cmp     eax, 0C0000034h
0x140150f3e  jnz     short loc_140150F68
0x140150f40  mov     r9, r12
0x140150f43  lea     rdx, aExclusive; "Exclusive"
0x140150f4a  mov     rcx, r14
0x140150f4d  call    CmRegUtilWstrValueGetDword
0x140150f52  mov     ebx, eax
0x140150f54  test    eax, eax
0x140150f56  js      short loc_140150F5D
0x140150f58  or      dword ptr [rdi], 8
0x140150f5b  jmp     short loc_140150F90
0x140150f5d  cmp     eax, 0C0000034h
0x140150f62  jnz     short loc_140150F68
0x140150f64  mov     ebx, esi
0x140150f66  jmp     short loc_140150F90
0x140150f68  mov     rcx, [rdi+8]; P
0x140150f6c  test    rcx, rcx
0x140150f6f  jz      short loc_140150F7F
0x140150f71  xor     edx, edx; Tag
0x140150f73  call    cs:__imp_ExFreePoolWithTag
0x140150f7a  nop     dword ptr [rax+rax+00h]
0x140150f7f  mov     [rdi], esi
0x140150f81  mov     [rdi+8], rsi
0x140150f85  mov     [r13+0], esi
0x140150f89  mov     [r15], esi
0x140150f8c  mov     [r12], esi
0x140150f90  mov     eax, ebx
0x140150f92  mov     rbx, [rsp+50h+arg_0]
0x140150f9a  add     rsp, 50h
0x140150f9e  pop     r15
0x140150fa0  pop     r14
0x140150fa2  pop     r13
0x140150fa4  pop     r12
0x140150fa6  pop     rdi
0x140150fa7  pop     rsi
0x140150fa8  pop     rbp
0x140150fa9  retn
```

# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140009f4c`
- end: `0x14000a12b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000a134`

## callees

- `0x140002350`
- `0x140009f4c`
- `0x14000a41c`
- `0x14000a6b4`
- `0x14000a964`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a01d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a05f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a0f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a01d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a05f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a0f3`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140009ff4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140009ff4`

## string_xrefs

- `0x140009f8e`: `Security`

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
0x140009f4c  mov     [rsp-38h+arg_0], rbx
0x140009f51  push    rbp
0x140009f52  push    rsi
0x140009f53  push    rdi
0x140009f54  push    r12
0x140009f56  push    r13
0x140009f58  push    r14
0x140009f5a  push    r15
0x140009f5c  mov     rbp, rsp
0x140009f5f  sub     rsp, 50h
0x140009f63  xor     r10d, r10d
0x140009f66  lea     r13, [rdx+4]
0x140009f6a  lea     r15, [rdx+10h]
0x140009f6e  mov     [rdx], r10d
0x140009f71  lea     r12, [rdx+14h]
0x140009f75  mov     [rdx+8], r10
0x140009f79  mov     rdi, rdx
0x140009f7c  mov     [rbp+SecurityDescriptor], r10
0x140009f80  mov     r14, rcx
0x140009f83  mov     [rbp+arg_10], r10d
0x140009f87  xorps   xmm0, xmm0
0x140009f8a  mov     [rbp+arg_8], r10b
0x140009f8e  lea     rdx, aSecurity; "Security"
0x140009f95  mov     [rbp+P], r10
0x140009f99  lea     rcx, [rbp+DestinationString]; DestinationString
0x140009f9d  mov     [r13+0], r10d
0x140009fa1  mov     esi, r10d
0x140009fa4  mov     [r15], r10d
0x140009fa7  mov     [r12], r10d
0x140009fab  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140009faf  call    WdmlibRtlInitUnicodeStringEx
0x140009fb4  mov     ebx, eax
0x140009fb6  test    eax, eax
0x140009fb8  js      short loc_14000A004
0x140009fba  lea     rax, [rbp+P]
0x140009fbe  mov     rcx, r14; KeyHandle
0x140009fc1  lea     rdx, [rbp+DestinationString]; ValueName
0x140009fc5  mov     [rsp+50h+var_30], rax; __int64
0x140009fca  call    CmRegUtilUcValueGetFullBuffer
0x140009fcf  mov     rsi, [rbp+P]
0x140009fd3  xor     r10d, r10d
0x140009fd6  mov     ebx, eax
0x140009fd8  test    eax, eax
0x140009fda  js      short loc_14000A004
0x140009fdc  mov     ecx, [rsi+8]
0x140009fdf  lea     rax, [rbp+SecurityDescriptor]
0x140009fe3  add     rcx, rsi
0x140009fe6  mov     [rsp+50h+var_30], rax
0x140009feb  mov     r9b, 1
0x140009fee  lea     r8d, [r10+1]
0x140009ff2  xor     edx, edx
0x140009ff4  call    cs:__imp_SeCaptureSecurityDescriptor
0x140009ffb  nop     dword ptr [rax+rax+00h]
0x14000a000  mov     ebx, eax
0x14000a002  jmp     short loc_14000A013
0x14000a004  cmp     ebx, 0C0000034h
0x14000a00a  jnz     short loc_14000A013
0x14000a00c  mov     [rbp+SecurityDescriptor], r10
0x14000a010  mov     ebx, r10d
0x14000a013  test    rsi, rsi
0x14000a016  jz      short loc_14000A029
0x14000a018  xor     edx, edx; Tag
0x14000a01a  mov     rcx, rsi; P
0x14000a01d  call    cs:__imp_ExFreePoolWithTag
0x14000a024  nop     dword ptr [rax+rax+00h]
0x14000a029  xor     esi, esi
0x14000a02b  test    ebx, ebx
0x14000a02d  js      loc_14000A0E8
0x14000a033  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000a037  test    rcx, rcx
0x14000a03a  jz      short loc_14000A078
0x14000a03c  lea     r8, [rbp+arg_10]
0x14000a040  lea     rdx, [rbp+arg_8]
0x14000a044  call    SeUtilSecurityInfoFromSecurityDescriptor
0x14000a049  mov     ebx, eax
0x14000a04b  test    eax, eax
0x14000a04d  js      loc_14000A0E8
0x14000a053  cmp     [rbp+arg_8], sil
0x14000a057  jz      short loc_14000A06D
0x14000a059  mov     rcx, [rbp+SecurityDescriptor]; P
0x14000a05d  xor     edx, edx; Tag
0x14000a05f  call    cs:__imp_ExFreePoolWithTag
0x14000a066  nop     dword ptr [rax+rax+00h]
0x14000a06b  jmp     short loc_14000A078
0x14000a06d  mov     rax, [rbp+SecurityDescriptor]
0x14000a071  or      dword ptr [rdi], 2
0x14000a074  mov     [rdi+8], rax
0x14000a078  mov     r9, r13
0x14000a07b  lea     rdx, aDevicetype; "DeviceType"
0x14000a082  mov     rcx, r14
0x14000a085  call    CmRegUtilWstrValueGetDword
0x14000a08a  mov     ebx, eax
0x14000a08c  test    eax, eax
0x14000a08e  js      short loc_14000A095
0x14000a090  or      dword ptr [rdi], 1
0x14000a093  jmp     short loc_14000A09C
0x14000a095  cmp     eax, 0C0000034h
0x14000a09a  jnz     short loc_14000A0E8
0x14000a09c  mov     r9, r15
0x14000a09f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x14000a0a6  mov     rcx, r14
0x14000a0a9  call    CmRegUtilWstrValueGetDword
0x14000a0ae  mov     ebx, eax
0x14000a0b0  test    eax, eax
0x14000a0b2  js      short loc_14000A0B9
0x14000a0b4  or      dword ptr [rdi], 4
0x14000a0b7  jmp     short loc_14000A0C0
0x14000a0b9  cmp     eax, 0C0000034h
0x14000a0be  jnz     short loc_14000A0E8
0x14000a0c0  mov     r9, r12
0x14000a0c3  lea     rdx, aExclusive; "Exclusive"
0x14000a0ca  mov     rcx, r14
0x14000a0cd  call    CmRegUtilWstrValueGetDword
0x14000a0d2  mov     ebx, eax
0x14000a0d4  test    eax, eax
0x14000a0d6  js      short loc_14000A0DD
0x14000a0d8  or      dword ptr [rdi], 8
0x14000a0db  jmp     short loc_14000A110
0x14000a0dd  cmp     eax, 0C0000034h
0x14000a0e2  jnz     short loc_14000A0E8
0x14000a0e4  mov     ebx, esi
0x14000a0e6  jmp     short loc_14000A110
0x14000a0e8  mov     rcx, [rdi+8]; P
0x14000a0ec  test    rcx, rcx
0x14000a0ef  jz      short loc_14000A0FF
0x14000a0f1  xor     edx, edx; Tag
0x14000a0f3  call    cs:__imp_ExFreePoolWithTag
0x14000a0fa  nop     dword ptr [rax+rax+00h]
0x14000a0ff  mov     [rdi], esi
0x14000a101  mov     [rdi+8], rsi
0x14000a105  mov     [r13+0], esi
0x14000a109  mov     [r15], esi
0x14000a10c  mov     [r12], esi
0x14000a110  mov     eax, ebx
0x14000a112  mov     rbx, [rsp+50h+arg_0]
0x14000a11a  add     rsp, 50h
0x14000a11e  pop     r15
0x14000a120  pop     r14
0x14000a122  pop     r13
0x14000a124  pop     r12
0x14000a126  pop     rdi
0x14000a127  pop     rsi
0x14000a128  pop     rbp
0x14000a129  retn
```

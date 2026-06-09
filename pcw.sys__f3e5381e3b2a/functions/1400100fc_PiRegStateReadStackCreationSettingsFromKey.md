# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x1400100fc`
- end: `0x1400102db`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400102e4`

## callees

- `0x140001208`
- `0x14000f248`
- `0x1400100fc`
- `0x14001072c`
- `0x1400109dc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400101cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001020f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400102a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400101cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001020f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400102a3`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400101a4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400101a4`

## string_xrefs

- `0x14001013e`: `Security`

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
0x1400100fc  mov     [rsp-38h+arg_0], rbx
0x140010101  push    rbp
0x140010102  push    rsi
0x140010103  push    rdi
0x140010104  push    r12
0x140010106  push    r13
0x140010108  push    r14
0x14001010a  push    r15
0x14001010c  mov     rbp, rsp
0x14001010f  sub     rsp, 50h
0x140010113  xor     r10d, r10d
0x140010116  lea     r13, [rdx+4]
0x14001011a  lea     r15, [rdx+10h]
0x14001011e  mov     [rdx], r10d
0x140010121  lea     r12, [rdx+14h]
0x140010125  mov     [rdx+8], r10
0x140010129  mov     rdi, rdx
0x14001012c  mov     [rbp+SecurityDescriptor], r10
0x140010130  mov     r14, rcx
0x140010133  mov     [rbp+arg_10], r10d
0x140010137  xorps   xmm0, xmm0
0x14001013a  mov     [rbp+arg_8], r10b
0x14001013e  lea     rdx, aSecurity; "Security"
0x140010145  mov     [rbp+P], r10
0x140010149  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001014d  mov     [r13+0], r10d
0x140010151  mov     esi, r10d
0x140010154  mov     [r15], r10d
0x140010157  mov     [r12], r10d
0x14001015b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001015f  call    WdmlibRtlInitUnicodeStringEx
0x140010164  mov     ebx, eax
0x140010166  test    eax, eax
0x140010168  js      short loc_1400101B4
0x14001016a  lea     rax, [rbp+P]
0x14001016e  mov     rcx, r14; KeyHandle
0x140010171  lea     rdx, [rbp+DestinationString]; ValueName
0x140010175  mov     [rsp+50h+var_30], rax; __int64
0x14001017a  call    CmRegUtilUcValueGetFullBuffer
0x14001017f  mov     rsi, [rbp+P]
0x140010183  xor     r10d, r10d
0x140010186  mov     ebx, eax
0x140010188  test    eax, eax
0x14001018a  js      short loc_1400101B4
0x14001018c  mov     ecx, [rsi+8]
0x14001018f  lea     rax, [rbp+SecurityDescriptor]
0x140010193  add     rcx, rsi
0x140010196  mov     [rsp+50h+var_30], rax
0x14001019b  mov     r9b, 1
0x14001019e  lea     r8d, [r10+1]
0x1400101a2  xor     edx, edx
0x1400101a4  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400101ab  nop     dword ptr [rax+rax+00h]
0x1400101b0  mov     ebx, eax
0x1400101b2  jmp     short loc_1400101C3
0x1400101b4  cmp     ebx, 0C0000034h
0x1400101ba  jnz     short loc_1400101C3
0x1400101bc  mov     [rbp+SecurityDescriptor], r10
0x1400101c0  mov     ebx, r10d
0x1400101c3  test    rsi, rsi
0x1400101c6  jz      short loc_1400101D9
0x1400101c8  xor     edx, edx; Tag
0x1400101ca  mov     rcx, rsi; P
0x1400101cd  call    cs:__imp_ExFreePoolWithTag
0x1400101d4  nop     dword ptr [rax+rax+00h]
0x1400101d9  xor     esi, esi
0x1400101db  test    ebx, ebx
0x1400101dd  js      loc_140010298
0x1400101e3  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400101e7  test    rcx, rcx
0x1400101ea  jz      short loc_140010228
0x1400101ec  lea     r8, [rbp+arg_10]
0x1400101f0  lea     rdx, [rbp+arg_8]
0x1400101f4  call    SeUtilSecurityInfoFromSecurityDescriptor
0x1400101f9  mov     ebx, eax
0x1400101fb  test    eax, eax
0x1400101fd  js      loc_140010298
0x140010203  cmp     [rbp+arg_8], sil
0x140010207  jz      short loc_14001021D
0x140010209  mov     rcx, [rbp+SecurityDescriptor]; P
0x14001020d  xor     edx, edx; Tag
0x14001020f  call    cs:__imp_ExFreePoolWithTag
0x140010216  nop     dword ptr [rax+rax+00h]
0x14001021b  jmp     short loc_140010228
0x14001021d  mov     rax, [rbp+SecurityDescriptor]
0x140010221  or      dword ptr [rdi], 2
0x140010224  mov     [rdi+8], rax
0x140010228  mov     r9, r13
0x14001022b  lea     rdx, aDevicetype; "DeviceType"
0x140010232  mov     rcx, r14
0x140010235  call    CmRegUtilWstrValueGetDword
0x14001023a  mov     ebx, eax
0x14001023c  test    eax, eax
0x14001023e  js      short loc_140010245
0x140010240  or      dword ptr [rdi], 1
0x140010243  jmp     short loc_14001024C
0x140010245  cmp     eax, 0C0000034h
0x14001024a  jnz     short loc_140010298
0x14001024c  mov     r9, r15
0x14001024f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140010256  mov     rcx, r14
0x140010259  call    CmRegUtilWstrValueGetDword
0x14001025e  mov     ebx, eax
0x140010260  test    eax, eax
0x140010262  js      short loc_140010269
0x140010264  or      dword ptr [rdi], 4
0x140010267  jmp     short loc_140010270
0x140010269  cmp     eax, 0C0000034h
0x14001026e  jnz     short loc_140010298
0x140010270  mov     r9, r12
0x140010273  lea     rdx, aExclusive; "Exclusive"
0x14001027a  mov     rcx, r14
0x14001027d  call    CmRegUtilWstrValueGetDword
0x140010282  mov     ebx, eax
0x140010284  test    eax, eax
0x140010286  js      short loc_14001028D
0x140010288  or      dword ptr [rdi], 8
0x14001028b  jmp     short loc_1400102C0
0x14001028d  cmp     eax, 0C0000034h
0x140010292  jnz     short loc_140010298
0x140010294  mov     ebx, esi
0x140010296  jmp     short loc_1400102C0
0x140010298  mov     rcx, [rdi+8]; P
0x14001029c  test    rcx, rcx
0x14001029f  jz      short loc_1400102AF
0x1400102a1  xor     edx, edx; Tag
0x1400102a3  call    cs:__imp_ExFreePoolWithTag
0x1400102aa  nop     dword ptr [rax+rax+00h]
0x1400102af  mov     [rdi], esi
0x1400102b1  mov     [rdi+8], rsi
0x1400102b5  mov     [r13+0], esi
0x1400102b9  mov     [r15], esi
0x1400102bc  mov     [r12], esi
0x1400102c0  mov     eax, ebx
0x1400102c2  mov     rbx, [rsp+50h+arg_0]
0x1400102ca  add     rsp, 50h
0x1400102ce  pop     r15
0x1400102d0  pop     r14
0x1400102d2  pop     r13
0x1400102d4  pop     r12
0x1400102d6  pop     rdi
0x1400102d7  pop     rsi
0x1400102d8  pop     rbp
0x1400102d9  retn
```

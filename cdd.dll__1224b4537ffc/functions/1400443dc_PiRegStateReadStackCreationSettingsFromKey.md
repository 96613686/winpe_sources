# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x1400443dc`
- end: `0x1400445bb`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400445c4`

## callees

- `0x14003707c`
- `0x1400443dc`
- `0x1400448ac`
- `0x140044b44`
- `0x140044df4`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140044484`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140044484`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400444ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400444ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044583`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400444ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400444ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044583`

## string_xrefs

- `0x14004441e`: `Security`

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
0x1400443dc  mov     [rsp-38h+arg_0], rbx
0x1400443e1  push    rbp
0x1400443e2  push    rsi
0x1400443e3  push    rdi
0x1400443e4  push    r12
0x1400443e6  push    r13
0x1400443e8  push    r14
0x1400443ea  push    r15
0x1400443ec  mov     rbp, rsp
0x1400443ef  sub     rsp, 50h
0x1400443f3  xor     r10d, r10d
0x1400443f6  lea     r13, [rdx+4]
0x1400443fa  lea     r15, [rdx+10h]
0x1400443fe  mov     [rdx], r10d
0x140044401  lea     r12, [rdx+14h]
0x140044405  mov     [rdx+8], r10
0x140044409  mov     rdi, rdx
0x14004440c  mov     [rbp+SecurityDescriptor], r10
0x140044410  mov     r14, rcx
0x140044413  mov     [rbp+arg_10], r10d
0x140044417  xorps   xmm0, xmm0
0x14004441a  mov     [rbp+arg_8], r10b
0x14004441e  lea     rdx, aSecurity; "Security"
0x140044425  mov     [rbp+P], r10
0x140044429  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004442d  mov     [r13+0], r10d
0x140044431  mov     esi, r10d
0x140044434  mov     [r15], r10d
0x140044437  mov     [r12], r10d
0x14004443b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004443f  call    WdmlibRtlInitUnicodeStringEx
0x140044444  mov     ebx, eax
0x140044446  test    eax, eax
0x140044448  js      short loc_140044494
0x14004444a  lea     rax, [rbp+P]
0x14004444e  mov     rcx, r14; KeyHandle
0x140044451  lea     rdx, [rbp+DestinationString]; ValueName
0x140044455  mov     [rsp+50h+var_30], rax; __int64
0x14004445a  call    CmRegUtilUcValueGetFullBuffer
0x14004445f  mov     rsi, [rbp+P]
0x140044463  xor     r10d, r10d
0x140044466  mov     ebx, eax
0x140044468  test    eax, eax
0x14004446a  js      short loc_140044494
0x14004446c  mov     ecx, [rsi+8]
0x14004446f  lea     rax, [rbp+SecurityDescriptor]
0x140044473  add     rcx, rsi
0x140044476  mov     [rsp+50h+var_30], rax
0x14004447b  mov     r9b, 1
0x14004447e  lea     r8d, [r10+1]
0x140044482  xor     edx, edx
0x140044484  call    cs:__imp_SeCaptureSecurityDescriptor
0x14004448b  nop     dword ptr [rax+rax+00h]
0x140044490  mov     ebx, eax
0x140044492  jmp     short loc_1400444A3
0x140044494  cmp     ebx, 0C0000034h
0x14004449a  jnz     short loc_1400444A3
0x14004449c  mov     [rbp+SecurityDescriptor], r10
0x1400444a0  mov     ebx, r10d
0x1400444a3  test    rsi, rsi
0x1400444a6  jz      short loc_1400444B9
0x1400444a8  xor     edx, edx; Tag
0x1400444aa  mov     rcx, rsi; P
0x1400444ad  call    cs:__imp_ExFreePoolWithTag
0x1400444b4  nop     dword ptr [rax+rax+00h]
0x1400444b9  xor     esi, esi
0x1400444bb  test    ebx, ebx
0x1400444bd  js      loc_140044578
0x1400444c3  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400444c7  test    rcx, rcx
0x1400444ca  jz      short loc_140044508
0x1400444cc  lea     r8, [rbp+arg_10]
0x1400444d0  lea     rdx, [rbp+arg_8]
0x1400444d4  call    SeUtilSecurityInfoFromSecurityDescriptor
0x1400444d9  mov     ebx, eax
0x1400444db  test    eax, eax
0x1400444dd  js      loc_140044578
0x1400444e3  cmp     [rbp+arg_8], sil
0x1400444e7  jz      short loc_1400444FD
0x1400444e9  mov     rcx, [rbp+SecurityDescriptor]; P
0x1400444ed  xor     edx, edx; Tag
0x1400444ef  call    cs:__imp_ExFreePoolWithTag
0x1400444f6  nop     dword ptr [rax+rax+00h]
0x1400444fb  jmp     short loc_140044508
0x1400444fd  mov     rax, [rbp+SecurityDescriptor]
0x140044501  or      dword ptr [rdi], 2
0x140044504  mov     [rdi+8], rax
0x140044508  mov     r9, r13
0x14004450b  lea     rdx, aDevicetype; "DeviceType"
0x140044512  mov     rcx, r14
0x140044515  call    CmRegUtilWstrValueGetDword
0x14004451a  mov     ebx, eax
0x14004451c  test    eax, eax
0x14004451e  js      short loc_140044525
0x140044520  or      dword ptr [rdi], 1
0x140044523  jmp     short loc_14004452C
0x140044525  cmp     eax, 0C0000034h
0x14004452a  jnz     short loc_140044578
0x14004452c  mov     r9, r15
0x14004452f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140044536  mov     rcx, r14
0x140044539  call    CmRegUtilWstrValueGetDword
0x14004453e  mov     ebx, eax
0x140044540  test    eax, eax
0x140044542  js      short loc_140044549
0x140044544  or      dword ptr [rdi], 4
0x140044547  jmp     short loc_140044550
0x140044549  cmp     eax, 0C0000034h
0x14004454e  jnz     short loc_140044578
0x140044550  mov     r9, r12
0x140044553  lea     rdx, aExclusive; "Exclusive"
0x14004455a  mov     rcx, r14
0x14004455d  call    CmRegUtilWstrValueGetDword
0x140044562  mov     ebx, eax
0x140044564  test    eax, eax
0x140044566  js      short loc_14004456D
0x140044568  or      dword ptr [rdi], 8
0x14004456b  jmp     short loc_1400445A0
0x14004456d  cmp     eax, 0C0000034h
0x140044572  jnz     short loc_140044578
0x140044574  mov     ebx, esi
0x140044576  jmp     short loc_1400445A0
0x140044578  mov     rcx, [rdi+8]; P
0x14004457c  test    rcx, rcx
0x14004457f  jz      short loc_14004458F
0x140044581  xor     edx, edx; Tag
0x140044583  call    cs:__imp_ExFreePoolWithTag
0x14004458a  nop     dword ptr [rax+rax+00h]
0x14004458f  mov     [rdi], esi
0x140044591  mov     [rdi+8], rsi
0x140044595  mov     [r13+0], esi
0x140044599  mov     [r15], esi
0x14004459c  mov     [r12], esi
0x1400445a0  mov     eax, ebx
0x1400445a2  mov     rbx, [rsp+50h+arg_0]
0x1400445aa  add     rsp, 50h
0x1400445ae  pop     r15
0x1400445b0  pop     r14
0x1400445b2  pop     r13
0x1400445b4  pop     r12
0x1400445b6  pop     rdi
0x1400445b7  pop     rsi
0x1400445b8  pop     rbp
0x1400445b9  retn
```

# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x14004669c`
- end: `0x14004687b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140046884`

## callees

- `0x140030d6c`
- `0x14004669c`
- `0x140046b6c`
- `0x140046e04`
- `0x1400470b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004676d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400467af`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046843`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004676d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400467af`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046843`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140046744`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140046744`

## string_xrefs

- `0x1400466de`: `Security`

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
0x14004669c  mov     [rsp-38h+arg_0], rbx
0x1400466a1  push    rbp
0x1400466a2  push    rsi
0x1400466a3  push    rdi
0x1400466a4  push    r12
0x1400466a6  push    r13
0x1400466a8  push    r14
0x1400466aa  push    r15
0x1400466ac  mov     rbp, rsp
0x1400466af  sub     rsp, 50h
0x1400466b3  xor     r10d, r10d
0x1400466b6  lea     r13, [rdx+4]
0x1400466ba  lea     r15, [rdx+10h]
0x1400466be  mov     [rdx], r10d
0x1400466c1  lea     r12, [rdx+14h]
0x1400466c5  mov     [rdx+8], r10
0x1400466c9  mov     rdi, rdx
0x1400466cc  mov     [rbp+SecurityDescriptor], r10
0x1400466d0  mov     r14, rcx
0x1400466d3  mov     [rbp+arg_10], r10d
0x1400466d7  xorps   xmm0, xmm0
0x1400466da  mov     [rbp+arg_8], r10b
0x1400466de  lea     rdx, aSecurity; "Security"
0x1400466e5  mov     [rbp+P], r10
0x1400466e9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400466ed  mov     [r13+0], r10d
0x1400466f1  mov     esi, r10d
0x1400466f4  mov     [r15], r10d
0x1400466f7  mov     [r12], r10d
0x1400466fb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400466ff  call    WdmlibRtlInitUnicodeStringEx
0x140046704  mov     ebx, eax
0x140046706  test    eax, eax
0x140046708  js      short loc_140046754
0x14004670a  lea     rax, [rbp+P]
0x14004670e  mov     rcx, r14; KeyHandle
0x140046711  lea     rdx, [rbp+DestinationString]; ValueName
0x140046715  mov     [rsp+50h+var_30], rax; __int64
0x14004671a  call    CmRegUtilUcValueGetFullBuffer
0x14004671f  mov     rsi, [rbp+P]
0x140046723  xor     r10d, r10d
0x140046726  mov     ebx, eax
0x140046728  test    eax, eax
0x14004672a  js      short loc_140046754
0x14004672c  mov     ecx, [rsi+8]
0x14004672f  lea     rax, [rbp+SecurityDescriptor]
0x140046733  add     rcx, rsi
0x140046736  mov     [rsp+50h+var_30], rax
0x14004673b  mov     r9b, 1
0x14004673e  lea     r8d, [r10+1]
0x140046742  xor     edx, edx
0x140046744  call    cs:__imp_SeCaptureSecurityDescriptor
0x14004674b  nop     dword ptr [rax+rax+00h]
0x140046750  mov     ebx, eax
0x140046752  jmp     short loc_140046763
0x140046754  cmp     ebx, 0C0000034h
0x14004675a  jnz     short loc_140046763
0x14004675c  mov     [rbp+SecurityDescriptor], r10
0x140046760  mov     ebx, r10d
0x140046763  test    rsi, rsi
0x140046766  jz      short loc_140046779
0x140046768  xor     edx, edx; Tag
0x14004676a  mov     rcx, rsi; P
0x14004676d  call    cs:__imp_ExFreePoolWithTag
0x140046774  nop     dword ptr [rax+rax+00h]
0x140046779  xor     esi, esi
0x14004677b  test    ebx, ebx
0x14004677d  js      loc_140046838
0x140046783  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140046787  test    rcx, rcx
0x14004678a  jz      short loc_1400467C8
0x14004678c  lea     r8, [rbp+arg_10]
0x140046790  lea     rdx, [rbp+arg_8]
0x140046794  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140046799  mov     ebx, eax
0x14004679b  test    eax, eax
0x14004679d  js      loc_140046838
0x1400467a3  cmp     [rbp+arg_8], sil
0x1400467a7  jz      short loc_1400467BD
0x1400467a9  mov     rcx, [rbp+SecurityDescriptor]; P
0x1400467ad  xor     edx, edx; Tag
0x1400467af  call    cs:__imp_ExFreePoolWithTag
0x1400467b6  nop     dword ptr [rax+rax+00h]
0x1400467bb  jmp     short loc_1400467C8
0x1400467bd  mov     rax, [rbp+SecurityDescriptor]
0x1400467c1  or      dword ptr [rdi], 2
0x1400467c4  mov     [rdi+8], rax
0x1400467c8  mov     r9, r13
0x1400467cb  lea     rdx, aDevicetype; "DeviceType"
0x1400467d2  mov     rcx, r14
0x1400467d5  call    CmRegUtilWstrValueGetDword
0x1400467da  mov     ebx, eax
0x1400467dc  test    eax, eax
0x1400467de  js      short loc_1400467E5
0x1400467e0  or      dword ptr [rdi], 1
0x1400467e3  jmp     short loc_1400467EC
0x1400467e5  cmp     eax, 0C0000034h
0x1400467ea  jnz     short loc_140046838
0x1400467ec  mov     r9, r15
0x1400467ef  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x1400467f6  mov     rcx, r14
0x1400467f9  call    CmRegUtilWstrValueGetDword
0x1400467fe  mov     ebx, eax
0x140046800  test    eax, eax
0x140046802  js      short loc_140046809
0x140046804  or      dword ptr [rdi], 4
0x140046807  jmp     short loc_140046810
0x140046809  cmp     eax, 0C0000034h
0x14004680e  jnz     short loc_140046838
0x140046810  mov     r9, r12
0x140046813  lea     rdx, aExclusive; "Exclusive"
0x14004681a  mov     rcx, r14
0x14004681d  call    CmRegUtilWstrValueGetDword
0x140046822  mov     ebx, eax
0x140046824  test    eax, eax
0x140046826  js      short loc_14004682D
0x140046828  or      dword ptr [rdi], 8
0x14004682b  jmp     short loc_140046860
0x14004682d  cmp     eax, 0C0000034h
0x140046832  jnz     short loc_140046838
0x140046834  mov     ebx, esi
0x140046836  jmp     short loc_140046860
0x140046838  mov     rcx, [rdi+8]; P
0x14004683c  test    rcx, rcx
0x14004683f  jz      short loc_14004684F
0x140046841  xor     edx, edx; Tag
0x140046843  call    cs:__imp_ExFreePoolWithTag
0x14004684a  nop     dword ptr [rax+rax+00h]
0x14004684f  mov     [rdi], esi
0x140046851  mov     [rdi+8], rsi
0x140046855  mov     [r13+0], esi
0x140046859  mov     [r15], esi
0x14004685c  mov     [r12], esi
0x140046860  mov     eax, ebx
0x140046862  mov     rbx, [rsp+50h+arg_0]
0x14004686a  add     rsp, 50h
0x14004686e  pop     r15
0x140046870  pop     r14
0x140046872  pop     r13
0x140046874  pop     r12
0x140046876  pop     rdi
0x140046877  pop     rsi
0x140046878  pop     rbp
0x140046879  retn
```

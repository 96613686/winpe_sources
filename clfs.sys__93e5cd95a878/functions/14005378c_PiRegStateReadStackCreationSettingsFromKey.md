# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x14005378c`
- end: `0x14005396b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140053974`

## callees

- `0x140017cc4`
- `0x14005378c`
- `0x140053c5c`
- `0x140053ef4`
- `0x1400541a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005385d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005389f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053933`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005385d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005389f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053933`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140053834`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140053834`

## string_xrefs

- `0x1400537ce`: `Security`

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
  UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
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
0x14005378c  mov     [rsp-38h+arg_0], rbx
0x140053791  push    rbp
0x140053792  push    rsi
0x140053793  push    rdi
0x140053794  push    r12
0x140053796  push    r13
0x140053798  push    r14
0x14005379a  push    r15
0x14005379c  mov     rbp, rsp
0x14005379f  sub     rsp, 50h
0x1400537a3  xor     r10d, r10d
0x1400537a6  lea     r13, [rdx+4]
0x1400537aa  lea     r15, [rdx+10h]
0x1400537ae  mov     [rdx], r10d
0x1400537b1  lea     r12, [rdx+14h]
0x1400537b5  mov     [rdx+8], r10
0x1400537b9  mov     rdi, rdx
0x1400537bc  mov     [rbp+SecurityDescriptor], r10
0x1400537c0  mov     r14, rcx
0x1400537c3  mov     [rbp+arg_10], r10d
0x1400537c7  xorps   xmm0, xmm0
0x1400537ca  mov     [rbp+arg_8], r10b
0x1400537ce  lea     rdx, aSecurity; "Security"
0x1400537d5  mov     [rbp+P], r10
0x1400537d9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400537dd  mov     [r13+0], r10d
0x1400537e1  mov     esi, r10d
0x1400537e4  mov     [r15], r10d
0x1400537e7  mov     [r12], r10d
0x1400537eb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400537ef  call    WdmlibRtlInitUnicodeStringEx
0x1400537f4  mov     ebx, eax
0x1400537f6  test    eax, eax
0x1400537f8  js      short loc_140053844
0x1400537fa  lea     rax, [rbp+P]
0x1400537fe  mov     rcx, r14; KeyHandle
0x140053801  lea     rdx, [rbp+DestinationString]; ValueName
0x140053805  mov     [rsp+50h+var_30], rax; __int64
0x14005380a  call    CmRegUtilUcValueGetFullBuffer
0x14005380f  mov     rsi, [rbp+P]
0x140053813  xor     r10d, r10d
0x140053816  mov     ebx, eax
0x140053818  test    eax, eax
0x14005381a  js      short loc_140053844
0x14005381c  mov     ecx, [rsi+8]
0x14005381f  lea     rax, [rbp+SecurityDescriptor]
0x140053823  add     rcx, rsi
0x140053826  mov     [rsp+50h+var_30], rax
0x14005382b  mov     r9b, 1
0x14005382e  lea     r8d, [r10+1]
0x140053832  xor     edx, edx
0x140053834  call    cs:__imp_SeCaptureSecurityDescriptor
0x14005383b  nop     dword ptr [rax+rax+00h]
0x140053840  mov     ebx, eax
0x140053842  jmp     short loc_140053853
0x140053844  cmp     ebx, 0C0000034h
0x14005384a  jnz     short loc_140053853
0x14005384c  mov     [rbp+SecurityDescriptor], r10
0x140053850  mov     ebx, r10d
0x140053853  test    rsi, rsi
0x140053856  jz      short loc_140053869
0x140053858  xor     edx, edx; Tag
0x14005385a  mov     rcx, rsi; P
0x14005385d  call    cs:__imp_ExFreePoolWithTag
0x140053864  nop     dword ptr [rax+rax+00h]
0x140053869  xor     esi, esi
0x14005386b  test    ebx, ebx
0x14005386d  js      loc_140053928
0x140053873  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140053877  test    rcx, rcx
0x14005387a  jz      short loc_1400538B8
0x14005387c  lea     r8, [rbp+arg_10]
0x140053880  lea     rdx, [rbp+arg_8]
0x140053884  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140053889  mov     ebx, eax
0x14005388b  test    eax, eax
0x14005388d  js      loc_140053928
0x140053893  cmp     [rbp+arg_8], sil
0x140053897  jz      short loc_1400538AD
0x140053899  mov     rcx, [rbp+SecurityDescriptor]; P
0x14005389d  xor     edx, edx; Tag
0x14005389f  call    cs:__imp_ExFreePoolWithTag
0x1400538a6  nop     dword ptr [rax+rax+00h]
0x1400538ab  jmp     short loc_1400538B8
0x1400538ad  mov     rax, [rbp+SecurityDescriptor]
0x1400538b1  or      dword ptr [rdi], 2
0x1400538b4  mov     [rdi+8], rax
0x1400538b8  mov     r9, r13
0x1400538bb  lea     rdx, aDevicetype; "DeviceType"
0x1400538c2  mov     rcx, r14
0x1400538c5  call    CmRegUtilWstrValueGetDword
0x1400538ca  mov     ebx, eax
0x1400538cc  test    eax, eax
0x1400538ce  js      short loc_1400538D5
0x1400538d0  or      dword ptr [rdi], 1
0x1400538d3  jmp     short loc_1400538DC
0x1400538d5  cmp     eax, 0C0000034h
0x1400538da  jnz     short loc_140053928
0x1400538dc  mov     r9, r15
0x1400538df  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x1400538e6  mov     rcx, r14
0x1400538e9  call    CmRegUtilWstrValueGetDword
0x1400538ee  mov     ebx, eax
0x1400538f0  test    eax, eax
0x1400538f2  js      short loc_1400538F9
0x1400538f4  or      dword ptr [rdi], 4
0x1400538f7  jmp     short loc_140053900
0x1400538f9  cmp     eax, 0C0000034h
0x1400538fe  jnz     short loc_140053928
0x140053900  mov     r9, r12
0x140053903  lea     rdx, aExclusive; "Exclusive"
0x14005390a  mov     rcx, r14
0x14005390d  call    CmRegUtilWstrValueGetDword
0x140053912  mov     ebx, eax
0x140053914  test    eax, eax
0x140053916  js      short loc_14005391D
0x140053918  or      dword ptr [rdi], 8
0x14005391b  jmp     short loc_140053950
0x14005391d  cmp     eax, 0C0000034h
0x140053922  jnz     short loc_140053928
0x140053924  mov     ebx, esi
0x140053926  jmp     short loc_140053950
0x140053928  mov     rcx, [rdi+8]; P
0x14005392c  test    rcx, rcx
0x14005392f  jz      short loc_14005393F
0x140053931  xor     edx, edx; Tag
0x140053933  call    cs:__imp_ExFreePoolWithTag
0x14005393a  nop     dword ptr [rax+rax+00h]
0x14005393f  mov     [rdi], esi
0x140053941  mov     [rdi+8], rsi
0x140053945  mov     [r13+0], esi
0x140053949  mov     [r15], esi
0x14005394c  mov     [r12], esi
0x140053950  mov     eax, ebx
0x140053952  mov     rbx, [rsp+50h+arg_0]
0x14005395a  add     rsp, 50h
0x14005395e  pop     r15
0x140053960  pop     r14
0x140053962  pop     r13
0x140053964  pop     r12
0x140053966  pop     rdi
0x140053967  pop     rsi
0x140053968  pop     rbp
0x140053969  retn
```

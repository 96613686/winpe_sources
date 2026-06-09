# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x14001854c`
- end: `0x14001872b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140018734`

## callees

- `0x140007e0c`
- `0x14001854c`
- `0x140018a1c`
- `0x140018c7c`
- `0x140018f2c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001861d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001865f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400186f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001861d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001865f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400186f3`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400185f4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400185f4`

## string_xrefs

- `0x14001858e`: `Security`

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
0x14001854c  mov     [rsp-38h+arg_0], rbx
0x140018551  push    rbp
0x140018552  push    rsi
0x140018553  push    rdi
0x140018554  push    r12
0x140018556  push    r13
0x140018558  push    r14
0x14001855a  push    r15
0x14001855c  mov     rbp, rsp
0x14001855f  sub     rsp, 50h
0x140018563  xor     r10d, r10d
0x140018566  lea     r13, [rdx+4]
0x14001856a  lea     r15, [rdx+10h]
0x14001856e  mov     [rdx], r10d
0x140018571  lea     r12, [rdx+14h]
0x140018575  mov     [rdx+8], r10
0x140018579  mov     rdi, rdx
0x14001857c  mov     [rbp+SecurityDescriptor], r10
0x140018580  mov     r14, rcx
0x140018583  mov     [rbp+arg_10], r10d
0x140018587  xorps   xmm0, xmm0
0x14001858a  mov     [rbp+arg_8], r10b
0x14001858e  lea     rdx, aSecurity; "Security"
0x140018595  mov     [rbp+P], r10
0x140018599  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001859d  mov     [r13+0], r10d
0x1400185a1  mov     esi, r10d
0x1400185a4  mov     [r15], r10d
0x1400185a7  mov     [r12], r10d
0x1400185ab  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400185af  call    WdmlibRtlInitUnicodeStringEx
0x1400185b4  mov     ebx, eax
0x1400185b6  test    eax, eax
0x1400185b8  js      short loc_140018604
0x1400185ba  lea     rax, [rbp+P]
0x1400185be  mov     rcx, r14; KeyHandle
0x1400185c1  lea     rdx, [rbp+DestinationString]; ValueName
0x1400185c5  mov     [rsp+50h+var_30], rax; __int64
0x1400185ca  call    CmRegUtilUcValueGetFullBuffer
0x1400185cf  mov     rsi, [rbp+P]
0x1400185d3  xor     r10d, r10d
0x1400185d6  mov     ebx, eax
0x1400185d8  test    eax, eax
0x1400185da  js      short loc_140018604
0x1400185dc  mov     ecx, [rsi+8]
0x1400185df  lea     rax, [rbp+SecurityDescriptor]
0x1400185e3  add     rcx, rsi
0x1400185e6  mov     [rsp+50h+var_30], rax
0x1400185eb  mov     r9b, 1
0x1400185ee  lea     r8d, [r10+1]
0x1400185f2  xor     edx, edx
0x1400185f4  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400185fb  nop     dword ptr [rax+rax+00h]
0x140018600  mov     ebx, eax
0x140018602  jmp     short loc_140018613
0x140018604  cmp     ebx, 0C0000034h
0x14001860a  jnz     short loc_140018613
0x14001860c  mov     [rbp+SecurityDescriptor], r10
0x140018610  mov     ebx, r10d
0x140018613  test    rsi, rsi
0x140018616  jz      short loc_140018629
0x140018618  xor     edx, edx; Tag
0x14001861a  mov     rcx, rsi; P
0x14001861d  call    cs:__imp_ExFreePoolWithTag
0x140018624  nop     dword ptr [rax+rax+00h]
0x140018629  xor     esi, esi
0x14001862b  test    ebx, ebx
0x14001862d  js      loc_1400186E8
0x140018633  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140018637  test    rcx, rcx
0x14001863a  jz      short loc_140018678
0x14001863c  lea     r8, [rbp+arg_10]
0x140018640  lea     rdx, [rbp+arg_8]
0x140018644  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140018649  mov     ebx, eax
0x14001864b  test    eax, eax
0x14001864d  js      loc_1400186E8
0x140018653  cmp     [rbp+arg_8], sil
0x140018657  jz      short loc_14001866D
0x140018659  mov     rcx, [rbp+SecurityDescriptor]; P
0x14001865d  xor     edx, edx; Tag
0x14001865f  call    cs:__imp_ExFreePoolWithTag
0x140018666  nop     dword ptr [rax+rax+00h]
0x14001866b  jmp     short loc_140018678
0x14001866d  mov     rax, [rbp+SecurityDescriptor]
0x140018671  or      dword ptr [rdi], 2
0x140018674  mov     [rdi+8], rax
0x140018678  mov     r9, r13
0x14001867b  lea     rdx, aDevicetype; "DeviceType"
0x140018682  mov     rcx, r14
0x140018685  call    CmRegUtilWstrValueGetDword
0x14001868a  mov     ebx, eax
0x14001868c  test    eax, eax
0x14001868e  js      short loc_140018695
0x140018690  or      dword ptr [rdi], 1
0x140018693  jmp     short loc_14001869C
0x140018695  cmp     eax, 0C0000034h
0x14001869a  jnz     short loc_1400186E8
0x14001869c  mov     r9, r15
0x14001869f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x1400186a6  mov     rcx, r14
0x1400186a9  call    CmRegUtilWstrValueGetDword
0x1400186ae  mov     ebx, eax
0x1400186b0  test    eax, eax
0x1400186b2  js      short loc_1400186B9
0x1400186b4  or      dword ptr [rdi], 4
0x1400186b7  jmp     short loc_1400186C0
0x1400186b9  cmp     eax, 0C0000034h
0x1400186be  jnz     short loc_1400186E8
0x1400186c0  mov     r9, r12
0x1400186c3  lea     rdx, aExclusive; "Exclusive"
0x1400186ca  mov     rcx, r14
0x1400186cd  call    CmRegUtilWstrValueGetDword
0x1400186d2  mov     ebx, eax
0x1400186d4  test    eax, eax
0x1400186d6  js      short loc_1400186DD
0x1400186d8  or      dword ptr [rdi], 8
0x1400186db  jmp     short loc_140018710
0x1400186dd  cmp     eax, 0C0000034h
0x1400186e2  jnz     short loc_1400186E8
0x1400186e4  mov     ebx, esi
0x1400186e6  jmp     short loc_140018710
0x1400186e8  mov     rcx, [rdi+8]; P
0x1400186ec  test    rcx, rcx
0x1400186ef  jz      short loc_1400186FF
0x1400186f1  xor     edx, edx; Tag
0x1400186f3  call    cs:__imp_ExFreePoolWithTag
0x1400186fa  nop     dword ptr [rax+rax+00h]
0x1400186ff  mov     [rdi], esi
0x140018701  mov     [rdi+8], rsi
0x140018705  mov     [r13+0], esi
0x140018709  mov     [r15], esi
0x14001870c  mov     [r12], esi
0x140018710  mov     eax, ebx
0x140018712  mov     rbx, [rsp+50h+arg_0]
0x14001871a  add     rsp, 50h
0x14001871e  pop     r15
0x140018720  pop     r14
0x140018722  pop     r13
0x140018724  pop     r12
0x140018726  pop     rdi
0x140018727  pop     rsi
0x140018728  pop     rbp
0x140018729  retn
```

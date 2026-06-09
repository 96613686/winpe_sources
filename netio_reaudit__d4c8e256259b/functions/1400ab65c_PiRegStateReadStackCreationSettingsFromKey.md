# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x1400ab65c`
- end: `0x1400ab83b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400ab844`

## callees

- `0x140076dc8`
- `0x1400ab65c`
- `0x1400abb2c`
- `0x1400abdc4`
- `0x1400ac074`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab72d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab76f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab803`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab72d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab76f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab803`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400ab704`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400ab704`

## string_xrefs

- `0x1400ab69e`: `Security`

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
0x1400ab65c  mov     [rsp-38h+arg_0], rbx
0x1400ab661  push    rbp
0x1400ab662  push    rsi
0x1400ab663  push    rdi
0x1400ab664  push    r12
0x1400ab666  push    r13
0x1400ab668  push    r14
0x1400ab66a  push    r15
0x1400ab66c  mov     rbp, rsp
0x1400ab66f  sub     rsp, 50h
0x1400ab673  xor     r10d, r10d
0x1400ab676  lea     r13, [rdx+4]
0x1400ab67a  lea     r15, [rdx+10h]
0x1400ab67e  mov     [rdx], r10d
0x1400ab681  lea     r12, [rdx+14h]
0x1400ab685  mov     [rdx+8], r10
0x1400ab689  mov     rdi, rdx
0x1400ab68c  mov     [rbp+SecurityDescriptor], r10
0x1400ab690  mov     r14, rcx
0x1400ab693  mov     [rbp+arg_10], r10d
0x1400ab697  xorps   xmm0, xmm0
0x1400ab69a  mov     [rbp+arg_8], r10b
0x1400ab69e  lea     rdx, aSecurity; "Security"
0x1400ab6a5  mov     [rbp+P], r10
0x1400ab6a9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400ab6ad  mov     [r13+0], r10d
0x1400ab6b1  mov     esi, r10d
0x1400ab6b4  mov     [r15], r10d
0x1400ab6b7  mov     [r12], r10d
0x1400ab6bb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400ab6bf  call    WdmlibRtlInitUnicodeStringEx
0x1400ab6c4  mov     ebx, eax
0x1400ab6c6  test    eax, eax
0x1400ab6c8  js      short loc_1400AB714
0x1400ab6ca  lea     rax, [rbp+P]
0x1400ab6ce  mov     rcx, r14; KeyHandle
0x1400ab6d1  lea     rdx, [rbp+DestinationString]; ValueName
0x1400ab6d5  mov     [rsp+50h+var_30], rax; __int64
0x1400ab6da  call    CmRegUtilUcValueGetFullBuffer
0x1400ab6df  mov     rsi, [rbp+P]
0x1400ab6e3  xor     r10d, r10d
0x1400ab6e6  mov     ebx, eax
0x1400ab6e8  test    eax, eax
0x1400ab6ea  js      short loc_1400AB714
0x1400ab6ec  mov     ecx, [rsi+8]
0x1400ab6ef  lea     rax, [rbp+SecurityDescriptor]
0x1400ab6f3  add     rcx, rsi
0x1400ab6f6  mov     [rsp+50h+var_30], rax
0x1400ab6fb  mov     r9b, 1
0x1400ab6fe  lea     r8d, [r10+1]
0x1400ab702  xor     edx, edx
0x1400ab704  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400ab70b  nop     dword ptr [rax+rax+00h]
0x1400ab710  mov     ebx, eax
0x1400ab712  jmp     short loc_1400AB723
0x1400ab714  cmp     ebx, 0C0000034h
0x1400ab71a  jnz     short loc_1400AB723
0x1400ab71c  mov     [rbp+SecurityDescriptor], r10
0x1400ab720  mov     ebx, r10d
0x1400ab723  test    rsi, rsi
0x1400ab726  jz      short loc_1400AB739
0x1400ab728  xor     edx, edx; Tag
0x1400ab72a  mov     rcx, rsi; P
0x1400ab72d  call    cs:__imp_ExFreePoolWithTag
0x1400ab734  nop     dword ptr [rax+rax+00h]
0x1400ab739  xor     esi, esi
0x1400ab73b  test    ebx, ebx
0x1400ab73d  js      loc_1400AB7F8
0x1400ab743  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400ab747  test    rcx, rcx
0x1400ab74a  jz      short loc_1400AB788
0x1400ab74c  lea     r8, [rbp+arg_10]
0x1400ab750  lea     rdx, [rbp+arg_8]
0x1400ab754  call    SeUtilSecurityInfoFromSecurityDescriptor
0x1400ab759  mov     ebx, eax
0x1400ab75b  test    eax, eax
0x1400ab75d  js      loc_1400AB7F8
0x1400ab763  cmp     [rbp+arg_8], sil
0x1400ab767  jz      short loc_1400AB77D
0x1400ab769  mov     rcx, [rbp+SecurityDescriptor]; P
0x1400ab76d  xor     edx, edx; Tag
0x1400ab76f  call    cs:__imp_ExFreePoolWithTag
0x1400ab776  nop     dword ptr [rax+rax+00h]
0x1400ab77b  jmp     short loc_1400AB788
0x1400ab77d  mov     rax, [rbp+SecurityDescriptor]
0x1400ab781  or      dword ptr [rdi], 2
0x1400ab784  mov     [rdi+8], rax
0x1400ab788  mov     r9, r13
0x1400ab78b  lea     rdx, aDevicetype; "DeviceType"
0x1400ab792  mov     rcx, r14
0x1400ab795  call    CmRegUtilWstrValueGetDword
0x1400ab79a  mov     ebx, eax
0x1400ab79c  test    eax, eax
0x1400ab79e  js      short loc_1400AB7A5
0x1400ab7a0  or      dword ptr [rdi], 1
0x1400ab7a3  jmp     short loc_1400AB7AC
0x1400ab7a5  cmp     eax, 0C0000034h
0x1400ab7aa  jnz     short loc_1400AB7F8
0x1400ab7ac  mov     r9, r15
0x1400ab7af  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x1400ab7b6  mov     rcx, r14
0x1400ab7b9  call    CmRegUtilWstrValueGetDword
0x1400ab7be  mov     ebx, eax
0x1400ab7c0  test    eax, eax
0x1400ab7c2  js      short loc_1400AB7C9
0x1400ab7c4  or      dword ptr [rdi], 4
0x1400ab7c7  jmp     short loc_1400AB7D0
0x1400ab7c9  cmp     eax, 0C0000034h
0x1400ab7ce  jnz     short loc_1400AB7F8
0x1400ab7d0  mov     r9, r12
0x1400ab7d3  lea     rdx, aExclusive; "Exclusive"
0x1400ab7da  mov     rcx, r14
0x1400ab7dd  call    CmRegUtilWstrValueGetDword
0x1400ab7e2  mov     ebx, eax
0x1400ab7e4  test    eax, eax
0x1400ab7e6  js      short loc_1400AB7ED
0x1400ab7e8  or      dword ptr [rdi], 8
0x1400ab7eb  jmp     short loc_1400AB820
0x1400ab7ed  cmp     eax, 0C0000034h
0x1400ab7f2  jnz     short loc_1400AB7F8
0x1400ab7f4  mov     ebx, esi
0x1400ab7f6  jmp     short loc_1400AB820
0x1400ab7f8  mov     rcx, [rdi+8]; P
0x1400ab7fc  test    rcx, rcx
0x1400ab7ff  jz      short loc_1400AB80F
0x1400ab801  xor     edx, edx; Tag
0x1400ab803  call    cs:__imp_ExFreePoolWithTag
0x1400ab80a  nop     dword ptr [rax+rax+00h]
0x1400ab80f  mov     [rdi], esi
0x1400ab811  mov     [rdi+8], rsi
0x1400ab815  mov     [r13+0], esi
0x1400ab819  mov     [r15], esi
0x1400ab81c  mov     [r12], esi
0x1400ab820  mov     eax, ebx
0x1400ab822  mov     rbx, [rsp+50h+arg_0]
0x1400ab82a  add     rsp, 50h
0x1400ab82e  pop     r15
0x1400ab830  pop     r14
0x1400ab832  pop     r13
0x1400ab834  pop     r12
0x1400ab836  pop     rdi
0x1400ab837  pop     rsi
0x1400ab838  pop     rbp
0x1400ab839  retn
```

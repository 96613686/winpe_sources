# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140043a6c`
- end: `0x140043c4b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140043c54`

## callees

- `0x14002811c`
- `0x140043a6c`
- `0x140043f3c`
- `0x14004419c`
- `0x14004444c`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140043b14`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140043b14`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043b3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043b7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043c13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043b3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043b7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043c13`

## string_xrefs

- `0x140043aae`: `Security`

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
0x140043a6c  mov     [rsp-38h+arg_0], rbx
0x140043a71  push    rbp
0x140043a72  push    rsi
0x140043a73  push    rdi
0x140043a74  push    r12
0x140043a76  push    r13
0x140043a78  push    r14
0x140043a7a  push    r15
0x140043a7c  mov     rbp, rsp
0x140043a7f  sub     rsp, 50h
0x140043a83  xor     r10d, r10d
0x140043a86  lea     r13, [rdx+4]
0x140043a8a  lea     r15, [rdx+10h]
0x140043a8e  mov     [rdx], r10d
0x140043a91  lea     r12, [rdx+14h]
0x140043a95  mov     [rdx+8], r10
0x140043a99  mov     rdi, rdx
0x140043a9c  mov     [rbp+SecurityDescriptor], r10
0x140043aa0  mov     r14, rcx
0x140043aa3  mov     [rbp+arg_10], r10d
0x140043aa7  xorps   xmm0, xmm0
0x140043aaa  mov     [rbp+arg_8], r10b
0x140043aae  lea     rdx, aSecurity; "Security"
0x140043ab5  mov     [rbp+P], r10
0x140043ab9  lea     rcx, [rbp+DestinationString]; DestinationString
0x140043abd  mov     [r13+0], r10d
0x140043ac1  mov     esi, r10d
0x140043ac4  mov     [r15], r10d
0x140043ac7  mov     [r12], r10d
0x140043acb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140043acf  call    WdmlibRtlInitUnicodeStringEx
0x140043ad4  mov     ebx, eax
0x140043ad6  test    eax, eax
0x140043ad8  js      short loc_140043B24
0x140043ada  lea     rax, [rbp+P]
0x140043ade  mov     rcx, r14; KeyHandle
0x140043ae1  lea     rdx, [rbp+DestinationString]; ValueName
0x140043ae5  mov     [rsp+50h+var_30], rax; __int64
0x140043aea  call    CmRegUtilUcValueGetFullBuffer
0x140043aef  mov     rsi, [rbp+P]
0x140043af3  xor     r10d, r10d
0x140043af6  mov     ebx, eax
0x140043af8  test    eax, eax
0x140043afa  js      short loc_140043B24
0x140043afc  mov     ecx, [rsi+8]
0x140043aff  lea     rax, [rbp+SecurityDescriptor]
0x140043b03  add     rcx, rsi
0x140043b06  mov     [rsp+50h+var_30], rax
0x140043b0b  mov     r9b, 1
0x140043b0e  lea     r8d, [r10+1]
0x140043b12  xor     edx, edx
0x140043b14  call    cs:__imp_SeCaptureSecurityDescriptor
0x140043b1b  nop     dword ptr [rax+rax+00h]
0x140043b20  mov     ebx, eax
0x140043b22  jmp     short loc_140043B33
0x140043b24  cmp     ebx, 0C0000034h
0x140043b2a  jnz     short loc_140043B33
0x140043b2c  mov     [rbp+SecurityDescriptor], r10
0x140043b30  mov     ebx, r10d
0x140043b33  test    rsi, rsi
0x140043b36  jz      short loc_140043B49
0x140043b38  xor     edx, edx; Tag
0x140043b3a  mov     rcx, rsi; P
0x140043b3d  call    cs:__imp_ExFreePoolWithTag
0x140043b44  nop     dword ptr [rax+rax+00h]
0x140043b49  xor     esi, esi
0x140043b4b  test    ebx, ebx
0x140043b4d  js      loc_140043C08
0x140043b53  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140043b57  test    rcx, rcx
0x140043b5a  jz      short loc_140043B98
0x140043b5c  lea     r8, [rbp+arg_10]
0x140043b60  lea     rdx, [rbp+arg_8]
0x140043b64  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140043b69  mov     ebx, eax
0x140043b6b  test    eax, eax
0x140043b6d  js      loc_140043C08
0x140043b73  cmp     [rbp+arg_8], sil
0x140043b77  jz      short loc_140043B8D
0x140043b79  mov     rcx, [rbp+SecurityDescriptor]; P
0x140043b7d  xor     edx, edx; Tag
0x140043b7f  call    cs:__imp_ExFreePoolWithTag
0x140043b86  nop     dword ptr [rax+rax+00h]
0x140043b8b  jmp     short loc_140043B98
0x140043b8d  mov     rax, [rbp+SecurityDescriptor]
0x140043b91  or      dword ptr [rdi], 2
0x140043b94  mov     [rdi+8], rax
0x140043b98  mov     r9, r13
0x140043b9b  lea     rdx, aDevicetype; "DeviceType"
0x140043ba2  mov     rcx, r14
0x140043ba5  call    CmRegUtilWstrValueGetDword
0x140043baa  mov     ebx, eax
0x140043bac  test    eax, eax
0x140043bae  js      short loc_140043BB5
0x140043bb0  or      dword ptr [rdi], 1
0x140043bb3  jmp     short loc_140043BBC
0x140043bb5  cmp     eax, 0C0000034h
0x140043bba  jnz     short loc_140043C08
0x140043bbc  mov     r9, r15
0x140043bbf  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140043bc6  mov     rcx, r14
0x140043bc9  call    CmRegUtilWstrValueGetDword
0x140043bce  mov     ebx, eax
0x140043bd0  test    eax, eax
0x140043bd2  js      short loc_140043BD9
0x140043bd4  or      dword ptr [rdi], 4
0x140043bd7  jmp     short loc_140043BE0
0x140043bd9  cmp     eax, 0C0000034h
0x140043bde  jnz     short loc_140043C08
0x140043be0  mov     r9, r12
0x140043be3  lea     rdx, aExclusive; "Exclusive"
0x140043bea  mov     rcx, r14
0x140043bed  call    CmRegUtilWstrValueGetDword
0x140043bf2  mov     ebx, eax
0x140043bf4  test    eax, eax
0x140043bf6  js      short loc_140043BFD
0x140043bf8  or      dword ptr [rdi], 8
0x140043bfb  jmp     short loc_140043C30
0x140043bfd  cmp     eax, 0C0000034h
0x140043c02  jnz     short loc_140043C08
0x140043c04  mov     ebx, esi
0x140043c06  jmp     short loc_140043C30
0x140043c08  mov     rcx, [rdi+8]; P
0x140043c0c  test    rcx, rcx
0x140043c0f  jz      short loc_140043C1F
0x140043c11  xor     edx, edx; Tag
0x140043c13  call    cs:__imp_ExFreePoolWithTag
0x140043c1a  nop     dword ptr [rax+rax+00h]
0x140043c1f  mov     [rdi], esi
0x140043c21  mov     [rdi+8], rsi
0x140043c25  mov     [r13+0], esi
0x140043c29  mov     [r15], esi
0x140043c2c  mov     [r12], esi
0x140043c30  mov     eax, ebx
0x140043c32  mov     rbx, [rsp+50h+arg_0]
0x140043c3a  add     rsp, 50h
0x140043c3e  pop     r15
0x140043c40  pop     r14
0x140043c42  pop     r13
0x140043c44  pop     r12
0x140043c46  pop     rdi
0x140043c47  pop     rsi
0x140043c48  pop     rbp
0x140043c49  retn
```

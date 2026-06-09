# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140157d6c`
- end: `0x140157f4b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140157f54`

## callees

- `0x14007df10`
- `0x140157d6c`
- `0x14015823c`
- `0x1401584d4`
- `0x140158784`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140157e3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157e7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157f13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157e3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157e7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157f13`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140157e14`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140157e14`

## string_xrefs

- `0x140157dae`: `Security`

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
0x140157d6c  mov     [rsp-38h+arg_0], rbx
0x140157d71  push    rbp
0x140157d72  push    rsi
0x140157d73  push    rdi
0x140157d74  push    r12
0x140157d76  push    r13
0x140157d78  push    r14
0x140157d7a  push    r15
0x140157d7c  mov     rbp, rsp
0x140157d7f  sub     rsp, 50h
0x140157d83  xor     r9d, r9d
0x140157d86  lea     r13, [rdx+4]
0x140157d8a  mov     [rdx], r9d
0x140157d8d  lea     r15, [rdx+10h]
0x140157d91  mov     [rdx+8], r9
0x140157d95  lea     r12, [rdx+14h]
0x140157d99  mov     r14, rcx
0x140157d9c  mov     [rbp+SecurityDescriptor], r9
0x140157da0  mov     rdi, rdx
0x140157da3  mov     [rbp+arg_10], r9d
0x140157da7  xorps   xmm0, xmm0
0x140157daa  mov     [rbp+arg_8], r9b
0x140157dae  lea     rdx, aSecurity; "Security"
0x140157db5  mov     [rbp+P], r9
0x140157db9  lea     rcx, [rbp+DestinationString]; DestinationString
0x140157dbd  mov     [r13+0], r9d
0x140157dc1  mov     esi, r9d
0x140157dc4  mov     [r15], r9d
0x140157dc7  mov     [r12], r9d
0x140157dcb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140157dcf  call    WdmlibRtlInitUnicodeStringEx
0x140157dd4  mov     ebx, eax
0x140157dd6  test    eax, eax
0x140157dd8  js      short loc_140157E24
0x140157dda  lea     rax, [rbp+P]
0x140157dde  mov     rcx, r14; KeyHandle
0x140157de1  lea     rdx, [rbp+DestinationString]; ValueName
0x140157de5  mov     [rsp+50h+var_30], rax; __int64
0x140157dea  call    CmRegUtilUcValueGetFullBuffer
0x140157def  mov     rsi, [rbp+P]
0x140157df3  xor     r9d, r9d
0x140157df6  mov     ebx, eax
0x140157df8  test    eax, eax
0x140157dfa  js      short loc_140157E24
0x140157dfc  mov     ecx, [rsi+8]
0x140157dff  lea     rax, [rbp+SecurityDescriptor]
0x140157e03  xor     edx, edx
0x140157e05  mov     [rsp+50h+var_30], rax
0x140157e0a  add     rcx, rsi
0x140157e0d  mov     r9b, 1
0x140157e10  lea     r8d, [rdx+1]
0x140157e14  call    cs:__imp_SeCaptureSecurityDescriptor
0x140157e1b  nop     dword ptr [rax+rax+00h]
0x140157e20  mov     ebx, eax
0x140157e22  jmp     short loc_140157E33
0x140157e24  cmp     ebx, 0C0000034h
0x140157e2a  jnz     short loc_140157E33
0x140157e2c  mov     [rbp+SecurityDescriptor], r9
0x140157e30  mov     ebx, r9d
0x140157e33  test    rsi, rsi
0x140157e36  jz      short loc_140157E49
0x140157e38  xor     edx, edx; Tag
0x140157e3a  mov     rcx, rsi; P
0x140157e3d  call    cs:__imp_ExFreePoolWithTag
0x140157e44  nop     dword ptr [rax+rax+00h]
0x140157e49  xor     esi, esi
0x140157e4b  test    ebx, ebx
0x140157e4d  js      loc_140157F08
0x140157e53  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140157e57  test    rcx, rcx
0x140157e5a  jz      short loc_140157E98
0x140157e5c  lea     r8, [rbp+arg_10]
0x140157e60  lea     rdx, [rbp+arg_8]
0x140157e64  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140157e69  mov     ebx, eax
0x140157e6b  test    eax, eax
0x140157e6d  js      loc_140157F08
0x140157e73  cmp     [rbp+arg_8], sil
0x140157e77  jz      short loc_140157E8D
0x140157e79  mov     rcx, [rbp+SecurityDescriptor]; P
0x140157e7d  xor     edx, edx; Tag
0x140157e7f  call    cs:__imp_ExFreePoolWithTag
0x140157e86  nop     dword ptr [rax+rax+00h]
0x140157e8b  jmp     short loc_140157E98
0x140157e8d  mov     rax, [rbp+SecurityDescriptor]
0x140157e91  or      dword ptr [rdi], 2
0x140157e94  mov     [rdi+8], rax
0x140157e98  mov     r9, r13
0x140157e9b  lea     rdx, aDevicetype; "DeviceType"
0x140157ea2  mov     rcx, r14
0x140157ea5  call    CmRegUtilWstrValueGetDword
0x140157eaa  mov     ebx, eax
0x140157eac  test    eax, eax
0x140157eae  js      short loc_140157EB5
0x140157eb0  or      dword ptr [rdi], 1
0x140157eb3  jmp     short loc_140157EBC
0x140157eb5  cmp     eax, 0C0000034h
0x140157eba  jnz     short loc_140157F08
0x140157ebc  mov     r9, r15
0x140157ebf  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140157ec6  mov     rcx, r14
0x140157ec9  call    CmRegUtilWstrValueGetDword
0x140157ece  mov     ebx, eax
0x140157ed0  test    eax, eax
0x140157ed2  js      short loc_140157ED9
0x140157ed4  or      dword ptr [rdi], 4
0x140157ed7  jmp     short loc_140157EE0
0x140157ed9  cmp     eax, 0C0000034h
0x140157ede  jnz     short loc_140157F08
0x140157ee0  mov     r9, r12
0x140157ee3  lea     rdx, aExclusive; "Exclusive"
0x140157eea  mov     rcx, r14
0x140157eed  call    CmRegUtilWstrValueGetDword
0x140157ef2  mov     ebx, eax
0x140157ef4  test    eax, eax
0x140157ef6  js      short loc_140157EFD
0x140157ef8  or      dword ptr [rdi], 8
0x140157efb  jmp     short loc_140157F30
0x140157efd  cmp     eax, 0C0000034h
0x140157f02  jnz     short loc_140157F08
0x140157f04  mov     ebx, esi
0x140157f06  jmp     short loc_140157F30
0x140157f08  mov     rcx, [rdi+8]; P
0x140157f0c  test    rcx, rcx
0x140157f0f  jz      short loc_140157F1F
0x140157f11  xor     edx, edx; Tag
0x140157f13  call    cs:__imp_ExFreePoolWithTag
0x140157f1a  nop     dword ptr [rax+rax+00h]
0x140157f1f  mov     [rdi], esi
0x140157f21  mov     [rdi+8], rsi
0x140157f25  mov     [r13+0], esi
0x140157f29  mov     [r15], esi
0x140157f2c  mov     [r12], esi
0x140157f30  mov     eax, ebx
0x140157f32  mov     rbx, [rsp+50h+arg_0]
0x140157f3a  add     rsp, 50h
0x140157f3e  pop     r15
0x140157f40  pop     r14
0x140157f42  pop     r13
0x140157f44  pop     r12
0x140157f46  pop     rdi
0x140157f47  pop     rsi
0x140157f48  pop     rbp
0x140157f49  retn
```

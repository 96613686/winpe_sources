# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140150a94`
- end: `0x140150c32`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401502bc`

## callees

- `0x1400e6240`
- `0x1400e65c0`
- `0x140150474`
- `0x140150a94`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140150b94`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140150b94`
- `ntoskrnl!RtlInitUnicodeString` at `0x140150ac0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140150ac0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140150ad0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140150ad0`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140150b5b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140150b5b`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140150b42`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140150b42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150bba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150bd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150c21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150bba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150bd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150c21`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140150b7c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140150c09`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140150b7c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140150c09`

## string_xrefs

- `0x140150aab`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall SepSddlSecurityDescriptorFromSDDLString(__int64 a1, ULONG a2, __int64 a3)
{
  __int64 (__fastcall *SystemRoutineAddress)(__int64, __int64, __int64); // rax
  __int64 v6; // rdx
  __int64 result; // rax
  void *v8; // rdi
  NTSTATUS v9; // ebx
  PVOID PoolWithTag; // rax
  PACL Dacl; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-38h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14; // [rsp+68h] [rbp-8h]
  ULONG BufferLength; // [rsp+98h] [rbp+28h] BYREF
  int v16; // [rsp+A8h] [rbp+38h] BYREF

  BufferLength = a2;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"SeConvertStringSecurityDescriptorToSecurityDescriptor");
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, __int64, __int64))MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
  {
    v14 = 0;
    v16 = 0;
    memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
    BufferLength = 0;
    v8 = 0;
    Dacl = 0;
    *(_QWORD *)a3 = 0;
    v9 = SepSddlDaclFromSDDLString(a1, v6, &v16, &Dacl);
    if ( v9 >= 0 )
    {
      RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
      WORD1(SecurityDescriptor[0]) |= v16;
      BufferLength = 0;
      RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, BufferLength, 0x64536553u);
      v8 = PoolWithTag;
      if ( PoolWithTag )
      {
        memset(PoolWithTag, 0, BufferLength);
        v9 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v8, &BufferLength);
        if ( v9 >= 0 )
        {
          ExFreePoolWithTag(Dacl, 0);
          *(_QWORD *)a3 = v8;
          return (unsigned int)v9;
        }
      }
      else
      {
        v9 = -1073741670;
      }
    }
    if ( Dacl )
      ExFreePoolWithTag(Dacl, 0);
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
    return (unsigned int)v9;
  }
  result = SystemRoutineAddress(a1, 1, a3);
  if ( (int)result >= 0 )
    *(_WORD *)(*(_QWORD *)a3 + 2LL) |= 8u;
  return result;
}

```

## disassembly

```asm
0x140150a94  mov     [rsp-18h+arg_0], rbx
0x140150a99  mov     [rsp-18h+BufferLength], edx
0x140150a9d  push    rbp
0x140150a9e  push    rdi
0x140150a9f  push    r14
0x140150aa1  mov     rbp, rsp
0x140150aa4  sub     rsp, 70h
0x140150aa8  mov     rbx, rcx
0x140150aab  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140150ab2  xorps   xmm0, xmm0
0x140150ab5  lea     rcx, [rbp+DestinationString]; DestinationString
0x140150ab9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140150abd  mov     r14, r8
0x140150ac0  call    cs:__imp_RtlInitUnicodeString
0x140150ac7  nop     dword ptr [rax+rax+00h]
0x140150acc  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140150ad0  call    cs:__imp_MmGetSystemRoutineAddress
0x140150ad7  nop     dword ptr [rax+rax+00h]
0x140150adc  mov     rcx, rbx
0x140150adf  test    rax, rax
0x140150ae2  jz      short loc_140150B08
0x140150ae4  xor     r9d, r9d
0x140150ae7  mov     r8, r14
0x140150aea  lea     edx, [r9+1]
0x140150aee  call    _guard_dispatch_icall
0x140150af3  test    eax, eax
0x140150af5  js      loc_140150BDE
0x140150afb  mov     rcx, [r14]
0x140150afe  or      word ptr [rcx+2], 8
0x140150b03  jmp     loc_140150BDE
0x140150b08  xor     eax, eax
0x140150b0a  lea     r9, [rbp+Dacl]
0x140150b0e  xorps   xmm0, xmm0
0x140150b11  mov     [rbp+var_8], rax
0x140150b15  lea     r8, [rbp+arg_18]
0x140150b19  mov     [rbp+arg_18], eax
0x140150b1c  movups  [rbp+SecurityDescriptor], xmm0
0x140150b20  mov     [rbp+BufferLength], eax
0x140150b23  xor     edi, edi
0x140150b25  movups  [rbp+var_18], xmm0
0x140150b29  mov     [rbp+Dacl], rax
0x140150b2d  mov     [r14], rax
0x140150b30  call    SepSddlDaclFromSDDLString
0x140150b35  mov     ebx, eax
0x140150b37  test    eax, eax
0x140150b39  js      short loc_140150BAD
0x140150b3b  lea     edx, [rdi+1]; Revision
0x140150b3e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140150b42  call    cs:__imp_RtlCreateSecurityDescriptor
0x140150b49  nop     dword ptr [rax+rax+00h]
0x140150b4e  mov     r8, [rbp+Dacl]; Dacl
0x140150b52  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140150b56  xor     r9d, r9d; DaclDefaulted
0x140150b59  mov     dl, 1; DaclPresent
0x140150b5b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140150b62  nop     dword ptr [rax+rax+00h]
0x140150b67  movzx   eax, word ptr [rbp+arg_18]
0x140150b6b  lea     r8, [rbp+BufferLength]; BufferLength
0x140150b6f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140150b73  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140150b77  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140150b79  mov     [rbp+BufferLength], edi
0x140150b7c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140150b83  nop     dword ptr [rax+rax+00h]
0x140150b88  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140150b8b  lea     ecx, [rdi+1]; PoolType
0x140150b8e  mov     r8d, 64536553h; Tag
0x140150b94  call    cs:__imp_ExAllocatePoolWithTag
0x140150b9b  nop     dword ptr [rax+rax+00h]
0x140150ba0  mov     rdi, rax
0x140150ba3  test    rax, rax
0x140150ba6  jnz     short loc_140150BF0
0x140150ba8  mov     ebx, 0C000009Ah
0x140150bad  cmp     [rbp+Dacl], 0
0x140150bb2  jz      short loc_140150BC6
0x140150bb4  mov     rcx, [rbp+Dacl]; P
0x140150bb8  xor     edx, edx; Tag
0x140150bba  call    cs:__imp_ExFreePoolWithTag
0x140150bc1  nop     dword ptr [rax+rax+00h]
0x140150bc6  test    rdi, rdi
0x140150bc9  jz      short loc_140150BDC
0x140150bcb  xor     edx, edx; Tag
0x140150bcd  mov     rcx, rdi; P
0x140150bd0  call    cs:__imp_ExFreePoolWithTag
0x140150bd7  nop     dword ptr [rax+rax+00h]
0x140150bdc  mov     eax, ebx
0x140150bde  mov     rbx, [rsp+70h+arg_0]
0x140150be6  add     rsp, 70h
0x140150bea  pop     r14
0x140150bec  pop     rdi
0x140150bed  pop     rbp
0x140150bee  retn
0x140150bf0  mov     r8d, [rbp+BufferLength]; Size
0x140150bf4  xor     edx, edx; Val
0x140150bf6  mov     rcx, rdi; void *
0x140150bf9  call    memset
0x140150bfe  lea     r8, [rbp+BufferLength]; BufferLength
0x140150c02  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140150c05  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140150c09  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140150c10  nop     dword ptr [rax+rax+00h]
0x140150c15  mov     ebx, eax
0x140150c17  test    eax, eax
0x140150c19  js      short loc_140150BAD
0x140150c1b  mov     rcx, [rbp+Dacl]; P
0x140150c1f  xor     edx, edx; Tag
0x140150c21  call    cs:__imp_ExFreePoolWithTag
0x140150c28  nop     dword ptr [rax+rax+00h]
0x140150c2d  mov     [r14], rdi
0x140150c30  jmp     short loc_140150BDC
```

# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x14000dca4`
- end: `0x14000de42`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d4cc`

## callees

- `0x140006610`
- `0x140006980`
- `0x14000d684`
- `0x14000dca4`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000dd52`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000dd52`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000dd6b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000dd6b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000dcd0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000dcd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ddca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dde0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000de31`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ddca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dde0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000de31`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000dce0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000dce0`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000dd8c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000de19`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000dd8c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000de19`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000dda4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000dda4`

## string_xrefs

- `0x14000dcbb`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x14000dca4  mov     [rsp-18h+arg_0], rbx
0x14000dca9  mov     [rsp-18h+BufferLength], edx
0x14000dcad  push    rbp
0x14000dcae  push    rdi
0x14000dcaf  push    r14
0x14000dcb1  mov     rbp, rsp
0x14000dcb4  sub     rsp, 70h
0x14000dcb8  mov     rbx, rcx
0x14000dcbb  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x14000dcc2  xorps   xmm0, xmm0
0x14000dcc5  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000dcc9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000dccd  mov     r14, r8
0x14000dcd0  call    cs:__imp_RtlInitUnicodeString
0x14000dcd7  nop     dword ptr [rax+rax+00h]
0x14000dcdc  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000dce0  call    cs:__imp_MmGetSystemRoutineAddress
0x14000dce7  nop     dword ptr [rax+rax+00h]
0x14000dcec  mov     rcx, rbx
0x14000dcef  test    rax, rax
0x14000dcf2  jz      short loc_14000DD18
0x14000dcf4  xor     r9d, r9d
0x14000dcf7  mov     r8, r14
0x14000dcfa  lea     edx, [r9+1]
0x14000dcfe  call    _guard_dispatch_icall
0x14000dd03  test    eax, eax
0x14000dd05  js      loc_14000DDEE
0x14000dd0b  mov     rcx, [r14]
0x14000dd0e  or      word ptr [rcx+2], 8
0x14000dd13  jmp     loc_14000DDEE
0x14000dd18  xor     eax, eax
0x14000dd1a  lea     r9, [rbp+Dacl]
0x14000dd1e  xorps   xmm0, xmm0
0x14000dd21  mov     [rbp+var_8], rax
0x14000dd25  lea     r8, [rbp+arg_18]
0x14000dd29  mov     [rbp+arg_18], eax
0x14000dd2c  movups  [rbp+SecurityDescriptor], xmm0
0x14000dd30  mov     [rbp+BufferLength], eax
0x14000dd33  xor     edi, edi
0x14000dd35  movups  [rbp+var_18], xmm0
0x14000dd39  mov     [rbp+Dacl], rax
0x14000dd3d  mov     [r14], rax
0x14000dd40  call    SepSddlDaclFromSDDLString
0x14000dd45  mov     ebx, eax
0x14000dd47  test    eax, eax
0x14000dd49  js      short loc_14000DDBD
0x14000dd4b  lea     edx, [rdi+1]; Revision
0x14000dd4e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000dd52  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000dd59  nop     dword ptr [rax+rax+00h]
0x14000dd5e  mov     r8, [rbp+Dacl]; Dacl
0x14000dd62  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000dd66  xor     r9d, r9d; DaclDefaulted
0x14000dd69  mov     dl, 1; DaclPresent
0x14000dd6b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000dd72  nop     dword ptr [rax+rax+00h]
0x14000dd77  movzx   eax, word ptr [rbp+arg_18]
0x14000dd7b  lea     r8, [rbp+BufferLength]; BufferLength
0x14000dd7f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x14000dd83  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14000dd87  xor     edx, edx; SelfRelativeSecurityDescriptor
0x14000dd89  mov     [rbp+BufferLength], edi
0x14000dd8c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14000dd93  nop     dword ptr [rax+rax+00h]
0x14000dd98  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x14000dd9b  lea     ecx, [rdi+1]; PoolType
0x14000dd9e  mov     r8d, 64536553h; Tag
0x14000dda4  call    cs:__imp_ExAllocatePoolWithTag
0x14000ddab  nop     dword ptr [rax+rax+00h]
0x14000ddb0  mov     rdi, rax
0x14000ddb3  test    rax, rax
0x14000ddb6  jnz     short loc_14000DE00
0x14000ddb8  mov     ebx, 0C000009Ah
0x14000ddbd  cmp     [rbp+Dacl], 0
0x14000ddc2  jz      short loc_14000DDD6
0x14000ddc4  mov     rcx, [rbp+Dacl]; P
0x14000ddc8  xor     edx, edx; Tag
0x14000ddca  call    cs:__imp_ExFreePoolWithTag
0x14000ddd1  nop     dword ptr [rax+rax+00h]
0x14000ddd6  test    rdi, rdi
0x14000ddd9  jz      short loc_14000DDEC
0x14000dddb  xor     edx, edx; Tag
0x14000dddd  mov     rcx, rdi; P
0x14000dde0  call    cs:__imp_ExFreePoolWithTag
0x14000dde7  nop     dword ptr [rax+rax+00h]
0x14000ddec  mov     eax, ebx
0x14000ddee  mov     rbx, [rsp+70h+arg_0]
0x14000ddf6  add     rsp, 70h
0x14000ddfa  pop     r14
0x14000ddfc  pop     rdi
0x14000ddfd  pop     rbp
0x14000ddfe  retn
0x14000de00  mov     r8d, [rbp+BufferLength]; Size
0x14000de04  xor     edx, edx; Val
0x14000de06  mov     rcx, rdi; void *
0x14000de09  call    memset
0x14000de0e  lea     r8, [rbp+BufferLength]; BufferLength
0x14000de12  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x14000de15  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14000de19  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14000de20  nop     dword ptr [rax+rax+00h]
0x14000de25  mov     ebx, eax
0x14000de27  test    eax, eax
0x14000de29  js      short loc_14000DDBD
0x14000de2b  mov     rcx, [rbp+Dacl]; P
0x14000de2f  xor     edx, edx; Tag
0x14000de31  call    cs:__imp_ExFreePoolWithTag
0x14000de38  nop     dword ptr [rax+rax+00h]
0x14000de3d  mov     [r14], rdi
0x14000de40  jmp     short loc_14000DDEC
```

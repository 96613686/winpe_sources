# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x1400119f4`
- end: `0x140011b92`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001121c`

## callees

- `0x140003a00`
- `0x140003d80`
- `0x1400113d4`
- `0x1400119f4`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140011a30`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140011a30`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140011abb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140011abb`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140011adc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140011b69`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140011adc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140011b69`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140011af4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140011af4`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140011aa2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140011aa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011b1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011b30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011b81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011b1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011b30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011b81`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011a20`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011a20`

## string_xrefs

- `0x140011a0b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x1400119f4  mov     [rsp-18h+arg_0], rbx
0x1400119f9  mov     [rsp-18h+BufferLength], edx
0x1400119fd  push    rbp
0x1400119fe  push    rdi
0x1400119ff  push    r14
0x140011a01  mov     rbp, rsp
0x140011a04  sub     rsp, 70h
0x140011a08  mov     rbx, rcx
0x140011a0b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140011a12  xorps   xmm0, xmm0
0x140011a15  lea     rcx, [rbp+DestinationString]; DestinationString
0x140011a19  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140011a1d  mov     r14, r8
0x140011a20  call    cs:__imp_RtlInitUnicodeString
0x140011a27  nop     dword ptr [rax+rax+00h]
0x140011a2c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140011a30  call    cs:__imp_MmGetSystemRoutineAddress
0x140011a37  nop     dword ptr [rax+rax+00h]
0x140011a3c  mov     rcx, rbx
0x140011a3f  test    rax, rax
0x140011a42  jz      short loc_140011A68
0x140011a44  xor     r9d, r9d
0x140011a47  mov     r8, r14
0x140011a4a  lea     edx, [r9+1]
0x140011a4e  call    _guard_dispatch_icall
0x140011a53  test    eax, eax
0x140011a55  js      loc_140011B3E
0x140011a5b  mov     rcx, [r14]
0x140011a5e  or      word ptr [rcx+2], 8
0x140011a63  jmp     loc_140011B3E
0x140011a68  xor     eax, eax
0x140011a6a  lea     r9, [rbp+Dacl]
0x140011a6e  xorps   xmm0, xmm0
0x140011a71  mov     [rbp+var_8], rax
0x140011a75  lea     r8, [rbp+arg_18]
0x140011a79  mov     [rbp+arg_18], eax
0x140011a7c  movups  [rbp+SecurityDescriptor], xmm0
0x140011a80  mov     [rbp+BufferLength], eax
0x140011a83  xor     edi, edi
0x140011a85  movups  [rbp+var_18], xmm0
0x140011a89  mov     [rbp+Dacl], rax
0x140011a8d  mov     [r14], rax
0x140011a90  call    SepSddlDaclFromSDDLString
0x140011a95  mov     ebx, eax
0x140011a97  test    eax, eax
0x140011a99  js      short loc_140011B0D
0x140011a9b  lea     edx, [rdi+1]; Revision
0x140011a9e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140011aa2  call    cs:__imp_RtlCreateSecurityDescriptor
0x140011aa9  nop     dword ptr [rax+rax+00h]
0x140011aae  mov     r8, [rbp+Dacl]; Dacl
0x140011ab2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140011ab6  xor     r9d, r9d; DaclDefaulted
0x140011ab9  mov     dl, 1; DaclPresent
0x140011abb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140011ac2  nop     dword ptr [rax+rax+00h]
0x140011ac7  movzx   eax, word ptr [rbp+arg_18]
0x140011acb  lea     r8, [rbp+BufferLength]; BufferLength
0x140011acf  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140011ad3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140011ad7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140011ad9  mov     [rbp+BufferLength], edi
0x140011adc  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140011ae3  nop     dword ptr [rax+rax+00h]
0x140011ae8  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140011aeb  lea     ecx, [rdi+1]; PoolType
0x140011aee  mov     r8d, 64536553h; Tag
0x140011af4  call    cs:__imp_ExAllocatePoolWithTag
0x140011afb  nop     dword ptr [rax+rax+00h]
0x140011b00  mov     rdi, rax
0x140011b03  test    rax, rax
0x140011b06  jnz     short loc_140011B50
0x140011b08  mov     ebx, 0C000009Ah
0x140011b0d  cmp     [rbp+Dacl], 0
0x140011b12  jz      short loc_140011B26
0x140011b14  mov     rcx, [rbp+Dacl]; P
0x140011b18  xor     edx, edx; Tag
0x140011b1a  call    cs:__imp_ExFreePoolWithTag
0x140011b21  nop     dword ptr [rax+rax+00h]
0x140011b26  test    rdi, rdi
0x140011b29  jz      short loc_140011B3C
0x140011b2b  xor     edx, edx; Tag
0x140011b2d  mov     rcx, rdi; P
0x140011b30  call    cs:__imp_ExFreePoolWithTag
0x140011b37  nop     dword ptr [rax+rax+00h]
0x140011b3c  mov     eax, ebx
0x140011b3e  mov     rbx, [rsp+70h+arg_0]
0x140011b46  add     rsp, 70h
0x140011b4a  pop     r14
0x140011b4c  pop     rdi
0x140011b4d  pop     rbp
0x140011b4e  retn
0x140011b50  mov     r8d, [rbp+BufferLength]; Size
0x140011b54  xor     edx, edx; Val
0x140011b56  mov     rcx, rdi; void *
0x140011b59  call    memset
0x140011b5e  lea     r8, [rbp+BufferLength]; BufferLength
0x140011b62  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140011b65  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140011b69  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140011b70  nop     dword ptr [rax+rax+00h]
0x140011b75  mov     ebx, eax
0x140011b77  test    eax, eax
0x140011b79  js      short loc_140011B0D
0x140011b7b  mov     rcx, [rbp+Dacl]; P
0x140011b7f  xor     edx, edx; Tag
0x140011b81  call    cs:__imp_ExFreePoolWithTag
0x140011b88  nop     dword ptr [rax+rax+00h]
0x140011b8d  mov     [r14], rdi
0x140011b90  jmp     short loc_140011B3C
```

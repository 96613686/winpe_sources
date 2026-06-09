# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140085aa4`
- end: `0x140085c42`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400852cc`

## callees

- `0x140022cd0`
- `0x140023040`
- `0x140085484`
- `0x140085aa4`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140085b52`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140085b52`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140085b6b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140085b6b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140085ae0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140085ae0`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140085b8c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140085c19`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140085b8c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140085c19`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140085ba4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140085ba4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085bca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085be0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085c31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085bca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085be0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085c31`
- `ntoskrnl!RtlInitUnicodeString` at `0x140085ad0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140085ad0`

## string_xrefs

- `0x140085abb`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140085aa4  mov     [rsp-18h+arg_0], rbx
0x140085aa9  mov     [rsp-18h+BufferLength], edx
0x140085aad  push    rbp
0x140085aae  push    rdi
0x140085aaf  push    r14
0x140085ab1  mov     rbp, rsp
0x140085ab4  sub     rsp, 70h
0x140085ab8  mov     rbx, rcx
0x140085abb  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140085ac2  xorps   xmm0, xmm0
0x140085ac5  lea     rcx, [rbp+DestinationString]; DestinationString
0x140085ac9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140085acd  mov     r14, r8
0x140085ad0  call    cs:__imp_RtlInitUnicodeString
0x140085ad7  nop     dword ptr [rax+rax+00h]
0x140085adc  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140085ae0  call    cs:__imp_MmGetSystemRoutineAddress
0x140085ae7  nop     dword ptr [rax+rax+00h]
0x140085aec  mov     rcx, rbx
0x140085aef  test    rax, rax
0x140085af2  jz      short loc_140085B18
0x140085af4  xor     r9d, r9d
0x140085af7  mov     r8, r14
0x140085afa  lea     edx, [r9+1]
0x140085afe  call    _guard_dispatch_icall
0x140085b03  test    eax, eax
0x140085b05  js      loc_140085BEE
0x140085b0b  mov     rcx, [r14]
0x140085b0e  or      word ptr [rcx+2], 8
0x140085b13  jmp     loc_140085BEE
0x140085b18  xor     eax, eax
0x140085b1a  lea     r9, [rbp+Dacl]
0x140085b1e  xorps   xmm0, xmm0
0x140085b21  mov     [rbp+var_8], rax
0x140085b25  lea     r8, [rbp+arg_18]
0x140085b29  mov     [rbp+arg_18], eax
0x140085b2c  movups  [rbp+SecurityDescriptor], xmm0
0x140085b30  mov     [rbp+BufferLength], eax
0x140085b33  xor     edi, edi
0x140085b35  movups  [rbp+var_18], xmm0
0x140085b39  mov     [rbp+Dacl], rax
0x140085b3d  mov     [r14], rax
0x140085b40  call    SepSddlDaclFromSDDLString
0x140085b45  mov     ebx, eax
0x140085b47  test    eax, eax
0x140085b49  js      short loc_140085BBD
0x140085b4b  lea     edx, [rdi+1]; Revision
0x140085b4e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140085b52  call    cs:__imp_RtlCreateSecurityDescriptor
0x140085b59  nop     dword ptr [rax+rax+00h]
0x140085b5e  mov     r8, [rbp+Dacl]; Dacl
0x140085b62  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140085b66  xor     r9d, r9d; DaclDefaulted
0x140085b69  mov     dl, 1; DaclPresent
0x140085b6b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140085b72  nop     dword ptr [rax+rax+00h]
0x140085b77  movzx   eax, word ptr [rbp+arg_18]
0x140085b7b  lea     r8, [rbp+BufferLength]; BufferLength
0x140085b7f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140085b83  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140085b87  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140085b89  mov     [rbp+BufferLength], edi
0x140085b8c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140085b93  nop     dword ptr [rax+rax+00h]
0x140085b98  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140085b9b  lea     ecx, [rdi+1]; PoolType
0x140085b9e  mov     r8d, 64536553h; Tag
0x140085ba4  call    cs:__imp_ExAllocatePoolWithTag
0x140085bab  nop     dword ptr [rax+rax+00h]
0x140085bb0  mov     rdi, rax
0x140085bb3  test    rax, rax
0x140085bb6  jnz     short loc_140085C00
0x140085bb8  mov     ebx, 0C000009Ah
0x140085bbd  cmp     [rbp+Dacl], 0
0x140085bc2  jz      short loc_140085BD6
0x140085bc4  mov     rcx, [rbp+Dacl]; P
0x140085bc8  xor     edx, edx; Tag
0x140085bca  call    cs:__imp_ExFreePoolWithTag
0x140085bd1  nop     dword ptr [rax+rax+00h]
0x140085bd6  test    rdi, rdi
0x140085bd9  jz      short loc_140085BEC
0x140085bdb  xor     edx, edx; Tag
0x140085bdd  mov     rcx, rdi; P
0x140085be0  call    cs:__imp_ExFreePoolWithTag
0x140085be7  nop     dword ptr [rax+rax+00h]
0x140085bec  mov     eax, ebx
0x140085bee  mov     rbx, [rsp+70h+arg_0]
0x140085bf6  add     rsp, 70h
0x140085bfa  pop     r14
0x140085bfc  pop     rdi
0x140085bfd  pop     rbp
0x140085bfe  retn
0x140085c00  mov     r8d, [rbp+BufferLength]; Size
0x140085c04  xor     edx, edx; Val
0x140085c06  mov     rcx, rdi; void *
0x140085c09  call    memset
0x140085c0e  lea     r8, [rbp+BufferLength]; BufferLength
0x140085c12  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140085c15  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140085c19  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140085c20  nop     dword ptr [rax+rax+00h]
0x140085c25  mov     ebx, eax
0x140085c27  test    eax, eax
0x140085c29  js      short loc_140085BBD
0x140085c2b  mov     rcx, [rbp+Dacl]; P
0x140085c2f  xor     edx, edx; Tag
0x140085c31  call    cs:__imp_ExFreePoolWithTag
0x140085c38  nop     dword ptr [rax+rax+00h]
0x140085c3d  mov     [r14], rdi
0x140085c40  jmp     short loc_140085BEC
```

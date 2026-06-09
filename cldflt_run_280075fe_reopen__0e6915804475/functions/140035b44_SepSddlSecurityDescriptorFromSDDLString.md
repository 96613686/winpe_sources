# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140035b44`
- end: `0x140035ce2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140082050`

## callees

- `0x14001e220`
- `0x14001e580`
- `0x140035b44`
- `0x140041ee8`

## import_xrefs

- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140035c2c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140035cb9`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140035c2c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140035cb9`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140035bf2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140035bf2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140035c44`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140035c44`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140035c0b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140035c0b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140035b80`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140035b80`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035b70`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035b70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035c6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035c80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035cd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035c6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035c80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035cd1`

## string_xrefs

- `0x140035b5b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140035b44  mov     [rsp-18h+arg_0], rbx
0x140035b49  mov     [rsp-18h+BufferLength], edx
0x140035b4d  push    rbp
0x140035b4e  push    rdi
0x140035b4f  push    r14
0x140035b51  mov     rbp, rsp
0x140035b54  sub     rsp, 70h
0x140035b58  mov     rbx, rcx
0x140035b5b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140035b62  xorps   xmm0, xmm0
0x140035b65  lea     rcx, [rbp+DestinationString]; DestinationString
0x140035b69  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140035b6d  mov     r14, r8
0x140035b70  call    cs:__imp_RtlInitUnicodeString
0x140035b77  nop     dword ptr [rax+rax+00h]
0x140035b7c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140035b80  call    cs:__imp_MmGetSystemRoutineAddress
0x140035b87  nop     dword ptr [rax+rax+00h]
0x140035b8c  mov     rcx, rbx
0x140035b8f  test    rax, rax
0x140035b92  jz      short loc_140035BB8
0x140035b94  xor     r9d, r9d
0x140035b97  mov     r8, r14
0x140035b9a  lea     edx, [r9+1]
0x140035b9e  call    _guard_dispatch_icall
0x140035ba3  test    eax, eax
0x140035ba5  js      loc_140035C8E
0x140035bab  mov     rcx, [r14]
0x140035bae  or      word ptr [rcx+2], 8
0x140035bb3  jmp     loc_140035C8E
0x140035bb8  xor     eax, eax
0x140035bba  lea     r9, [rbp+Dacl]
0x140035bbe  xorps   xmm0, xmm0
0x140035bc1  mov     [rbp+var_8], rax
0x140035bc5  lea     r8, [rbp+arg_18]
0x140035bc9  mov     [rbp+arg_18], eax
0x140035bcc  movups  [rbp+SecurityDescriptor], xmm0
0x140035bd0  mov     [rbp+BufferLength], eax
0x140035bd3  xor     edi, edi
0x140035bd5  movups  [rbp+var_18], xmm0
0x140035bd9  mov     [rbp+Dacl], rax
0x140035bdd  mov     [r14], rax
0x140035be0  call    SepSddlDaclFromSDDLString
0x140035be5  mov     ebx, eax
0x140035be7  test    eax, eax
0x140035be9  js      short loc_140035C5D
0x140035beb  lea     edx, [rdi+1]; Revision
0x140035bee  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140035bf2  call    cs:__imp_RtlCreateSecurityDescriptor
0x140035bf9  nop     dword ptr [rax+rax+00h]
0x140035bfe  mov     r8, [rbp+Dacl]; Dacl
0x140035c02  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140035c06  xor     r9d, r9d; DaclDefaulted
0x140035c09  mov     dl, 1; DaclPresent
0x140035c0b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140035c12  nop     dword ptr [rax+rax+00h]
0x140035c17  movzx   eax, word ptr [rbp+arg_18]
0x140035c1b  lea     r8, [rbp+BufferLength]; BufferLength
0x140035c1f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140035c23  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140035c27  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140035c29  mov     [rbp+BufferLength], edi
0x140035c2c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140035c33  nop     dword ptr [rax+rax+00h]
0x140035c38  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140035c3b  lea     ecx, [rdi+1]; PoolType
0x140035c3e  mov     r8d, 64536553h; Tag
0x140035c44  call    cs:__imp_ExAllocatePoolWithTag
0x140035c4b  nop     dword ptr [rax+rax+00h]
0x140035c50  mov     rdi, rax
0x140035c53  test    rax, rax
0x140035c56  jnz     short loc_140035CA0
0x140035c58  mov     ebx, 0C000009Ah
0x140035c5d  cmp     [rbp+Dacl], 0
0x140035c62  jz      short loc_140035C76
0x140035c64  mov     rcx, [rbp+Dacl]; P
0x140035c68  xor     edx, edx; Tag
0x140035c6a  call    cs:__imp_ExFreePoolWithTag
0x140035c71  nop     dword ptr [rax+rax+00h]
0x140035c76  test    rdi, rdi
0x140035c79  jz      short loc_140035C8C
0x140035c7b  xor     edx, edx; Tag
0x140035c7d  mov     rcx, rdi; P
0x140035c80  call    cs:__imp_ExFreePoolWithTag
0x140035c87  nop     dword ptr [rax+rax+00h]
0x140035c8c  mov     eax, ebx
0x140035c8e  mov     rbx, [rsp+70h+arg_0]
0x140035c96  add     rsp, 70h
0x140035c9a  pop     r14
0x140035c9c  pop     rdi
0x140035c9d  pop     rbp
0x140035c9e  retn
0x140035ca0  mov     r8d, [rbp+BufferLength]; Size
0x140035ca4  xor     edx, edx; Val
0x140035ca6  mov     rcx, rdi; void *
0x140035ca9  call    memset
0x140035cae  lea     r8, [rbp+BufferLength]; BufferLength
0x140035cb2  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140035cb5  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140035cb9  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140035cc0  nop     dword ptr [rax+rax+00h]
0x140035cc5  mov     ebx, eax
0x140035cc7  test    eax, eax
0x140035cc9  js      short loc_140035C5D
0x140035ccb  mov     rcx, [rbp+Dacl]; P
0x140035ccf  xor     edx, edx; Tag
0x140035cd1  call    cs:__imp_ExFreePoolWithTag
0x140035cd8  nop     dword ptr [rax+rax+00h]
0x140035cdd  mov     [r14], rdi
0x140035ce0  jmp     short loc_140035C8C
```

# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140083a04`
- end: `0x140083ba2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14008322c`

## callees

- `0x1400219a0`
- `0x140021d00`
- `0x1400833e4`
- `0x140083a04`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140083ab2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140083ab2`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140083acb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140083acb`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140083a40`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140083a40`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140083aec`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140083b79`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140083aec`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140083b79`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140083b04`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140083b04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083b2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083b40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083b91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083b2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083b40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083b91`
- `ntoskrnl!RtlInitUnicodeString` at `0x140083a30`
- `ntoskrnl!RtlInitUnicodeString` at `0x140083a30`

## string_xrefs

- `0x140083a1b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140083a04  mov     [rsp-18h+arg_0], rbx
0x140083a09  mov     [rsp-18h+BufferLength], edx
0x140083a0d  push    rbp
0x140083a0e  push    rdi
0x140083a0f  push    r14
0x140083a11  mov     rbp, rsp
0x140083a14  sub     rsp, 70h
0x140083a18  mov     rbx, rcx
0x140083a1b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140083a22  xorps   xmm0, xmm0
0x140083a25  lea     rcx, [rbp+DestinationString]; DestinationString
0x140083a29  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140083a2d  mov     r14, r8
0x140083a30  call    cs:__imp_RtlInitUnicodeString
0x140083a37  nop     dword ptr [rax+rax+00h]
0x140083a3c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140083a40  call    cs:__imp_MmGetSystemRoutineAddress
0x140083a47  nop     dword ptr [rax+rax+00h]
0x140083a4c  mov     rcx, rbx
0x140083a4f  test    rax, rax
0x140083a52  jz      short loc_140083A78
0x140083a54  xor     r9d, r9d
0x140083a57  mov     r8, r14
0x140083a5a  lea     edx, [r9+1]
0x140083a5e  call    _guard_dispatch_icall
0x140083a63  test    eax, eax
0x140083a65  js      loc_140083B4E
0x140083a6b  mov     rcx, [r14]
0x140083a6e  or      word ptr [rcx+2], 8
0x140083a73  jmp     loc_140083B4E
0x140083a78  xor     eax, eax
0x140083a7a  lea     r9, [rbp+Dacl]
0x140083a7e  xorps   xmm0, xmm0
0x140083a81  mov     [rbp+var_8], rax
0x140083a85  lea     r8, [rbp+arg_18]
0x140083a89  mov     [rbp+arg_18], eax
0x140083a8c  movups  [rbp+SecurityDescriptor], xmm0
0x140083a90  mov     [rbp+BufferLength], eax
0x140083a93  xor     edi, edi
0x140083a95  movups  [rbp+var_18], xmm0
0x140083a99  mov     [rbp+Dacl], rax
0x140083a9d  mov     [r14], rax
0x140083aa0  call    SepSddlDaclFromSDDLString
0x140083aa5  mov     ebx, eax
0x140083aa7  test    eax, eax
0x140083aa9  js      short loc_140083B1D
0x140083aab  lea     edx, [rdi+1]; Revision
0x140083aae  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140083ab2  call    cs:__imp_RtlCreateSecurityDescriptor
0x140083ab9  nop     dword ptr [rax+rax+00h]
0x140083abe  mov     r8, [rbp+Dacl]; Dacl
0x140083ac2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140083ac6  xor     r9d, r9d; DaclDefaulted
0x140083ac9  mov     dl, 1; DaclPresent
0x140083acb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140083ad2  nop     dword ptr [rax+rax+00h]
0x140083ad7  movzx   eax, word ptr [rbp+arg_18]
0x140083adb  lea     r8, [rbp+BufferLength]; BufferLength
0x140083adf  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140083ae3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140083ae7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140083ae9  mov     [rbp+BufferLength], edi
0x140083aec  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140083af3  nop     dword ptr [rax+rax+00h]
0x140083af8  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140083afb  lea     ecx, [rdi+1]; PoolType
0x140083afe  mov     r8d, 64536553h; Tag
0x140083b04  call    cs:__imp_ExAllocatePoolWithTag
0x140083b0b  nop     dword ptr [rax+rax+00h]
0x140083b10  mov     rdi, rax
0x140083b13  test    rax, rax
0x140083b16  jnz     short loc_140083B60
0x140083b18  mov     ebx, 0C000009Ah
0x140083b1d  cmp     [rbp+Dacl], 0
0x140083b22  jz      short loc_140083B36
0x140083b24  mov     rcx, [rbp+Dacl]; P
0x140083b28  xor     edx, edx; Tag
0x140083b2a  call    cs:__imp_ExFreePoolWithTag
0x140083b31  nop     dword ptr [rax+rax+00h]
0x140083b36  test    rdi, rdi
0x140083b39  jz      short loc_140083B4C
0x140083b3b  xor     edx, edx; Tag
0x140083b3d  mov     rcx, rdi; P
0x140083b40  call    cs:__imp_ExFreePoolWithTag
0x140083b47  nop     dword ptr [rax+rax+00h]
0x140083b4c  mov     eax, ebx
0x140083b4e  mov     rbx, [rsp+70h+arg_0]
0x140083b56  add     rsp, 70h
0x140083b5a  pop     r14
0x140083b5c  pop     rdi
0x140083b5d  pop     rbp
0x140083b5e  retn
0x140083b60  mov     r8d, [rbp+BufferLength]; Size
0x140083b64  xor     edx, edx; Val
0x140083b66  mov     rcx, rdi; void *
0x140083b69  call    memset
0x140083b6e  lea     r8, [rbp+BufferLength]; BufferLength
0x140083b72  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140083b75  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140083b79  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140083b80  nop     dword ptr [rax+rax+00h]
0x140083b85  mov     ebx, eax
0x140083b87  test    eax, eax
0x140083b89  js      short loc_140083B1D
0x140083b8b  mov     rcx, [rbp+Dacl]; P
0x140083b8f  xor     edx, edx; Tag
0x140083b91  call    cs:__imp_ExFreePoolWithTag
0x140083b98  nop     dword ptr [rax+rax+00h]
0x140083b9d  mov     [r14], rdi
0x140083ba0  jmp     short loc_140083B4C
```

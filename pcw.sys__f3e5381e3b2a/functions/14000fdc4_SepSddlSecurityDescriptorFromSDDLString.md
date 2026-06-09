# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x14000fdc4`
- end: `0x14000ff62`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f5dc`

## callees

- `0x140001450`
- `0x1400017c0`
- `0x14000f794`
- `0x14000fdc4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000feea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ff00`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ff51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000feea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ff00`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ff51`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000fdf0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000fdf0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000fe72`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000fe72`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000fe8b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000fe8b`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000feac`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000ff39`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000feac`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000ff39`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000fe00`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000fe00`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000fec4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000fec4`

## string_xrefs

- `0x14000fddb`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x14000fdc4  mov     [rsp-18h+arg_0], rbx
0x14000fdc9  mov     [rsp-18h+BufferLength], edx
0x14000fdcd  push    rbp
0x14000fdce  push    rdi
0x14000fdcf  push    r14
0x14000fdd1  mov     rbp, rsp
0x14000fdd4  sub     rsp, 70h
0x14000fdd8  mov     rbx, rcx
0x14000fddb  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x14000fde2  xorps   xmm0, xmm0
0x14000fde5  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000fde9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000fded  mov     r14, r8
0x14000fdf0  call    cs:__imp_RtlInitUnicodeString
0x14000fdf7  nop     dword ptr [rax+rax+00h]
0x14000fdfc  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000fe00  call    cs:__imp_MmGetSystemRoutineAddress
0x14000fe07  nop     dword ptr [rax+rax+00h]
0x14000fe0c  mov     rcx, rbx
0x14000fe0f  test    rax, rax
0x14000fe12  jz      short loc_14000FE38
0x14000fe14  xor     r9d, r9d
0x14000fe17  mov     r8, r14
0x14000fe1a  lea     edx, [r9+1]
0x14000fe1e  call    _guard_dispatch_icall
0x14000fe23  test    eax, eax
0x14000fe25  js      loc_14000FF0E
0x14000fe2b  mov     rcx, [r14]
0x14000fe2e  or      word ptr [rcx+2], 8
0x14000fe33  jmp     loc_14000FF0E
0x14000fe38  xor     eax, eax
0x14000fe3a  lea     r9, [rbp+Dacl]
0x14000fe3e  xorps   xmm0, xmm0
0x14000fe41  mov     [rbp+var_8], rax
0x14000fe45  lea     r8, [rbp+arg_18]
0x14000fe49  mov     [rbp+arg_18], eax
0x14000fe4c  movups  [rbp+SecurityDescriptor], xmm0
0x14000fe50  mov     [rbp+BufferLength], eax
0x14000fe53  xor     edi, edi
0x14000fe55  movups  [rbp+var_18], xmm0
0x14000fe59  mov     [rbp+Dacl], rax
0x14000fe5d  mov     [r14], rax
0x14000fe60  call    SepSddlDaclFromSDDLString
0x14000fe65  mov     ebx, eax
0x14000fe67  test    eax, eax
0x14000fe69  js      short loc_14000FEDD
0x14000fe6b  lea     edx, [rdi+1]; Revision
0x14000fe6e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000fe72  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000fe79  nop     dword ptr [rax+rax+00h]
0x14000fe7e  mov     r8, [rbp+Dacl]; Dacl
0x14000fe82  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000fe86  xor     r9d, r9d; DaclDefaulted
0x14000fe89  mov     dl, 1; DaclPresent
0x14000fe8b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000fe92  nop     dword ptr [rax+rax+00h]
0x14000fe97  movzx   eax, word ptr [rbp+arg_18]
0x14000fe9b  lea     r8, [rbp+BufferLength]; BufferLength
0x14000fe9f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x14000fea3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14000fea7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x14000fea9  mov     [rbp+BufferLength], edi
0x14000feac  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14000feb3  nop     dword ptr [rax+rax+00h]
0x14000feb8  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x14000febb  lea     ecx, [rdi+1]; PoolType
0x14000febe  mov     r8d, 64536553h; Tag
0x14000fec4  call    cs:__imp_ExAllocatePoolWithTag
0x14000fecb  nop     dword ptr [rax+rax+00h]
0x14000fed0  mov     rdi, rax
0x14000fed3  test    rax, rax
0x14000fed6  jnz     short loc_14000FF20
0x14000fed8  mov     ebx, 0C000009Ah
0x14000fedd  cmp     [rbp+Dacl], 0
0x14000fee2  jz      short loc_14000FEF6
0x14000fee4  mov     rcx, [rbp+Dacl]; P
0x14000fee8  xor     edx, edx; Tag
0x14000feea  call    cs:__imp_ExFreePoolWithTag
0x14000fef1  nop     dword ptr [rax+rax+00h]
0x14000fef6  test    rdi, rdi
0x14000fef9  jz      short loc_14000FF0C
0x14000fefb  xor     edx, edx; Tag
0x14000fefd  mov     rcx, rdi; P
0x14000ff00  call    cs:__imp_ExFreePoolWithTag
0x14000ff07  nop     dword ptr [rax+rax+00h]
0x14000ff0c  mov     eax, ebx
0x14000ff0e  mov     rbx, [rsp+70h+arg_0]
0x14000ff16  add     rsp, 70h
0x14000ff1a  pop     r14
0x14000ff1c  pop     rdi
0x14000ff1d  pop     rbp
0x14000ff1e  retn
0x14000ff20  mov     r8d, [rbp+BufferLength]; Size
0x14000ff24  xor     edx, edx; Val
0x14000ff26  mov     rcx, rdi; void *
0x14000ff29  call    memset
0x14000ff2e  lea     r8, [rbp+BufferLength]; BufferLength
0x14000ff32  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x14000ff35  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14000ff39  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14000ff40  nop     dword ptr [rax+rax+00h]
0x14000ff45  mov     ebx, eax
0x14000ff47  test    eax, eax
0x14000ff49  js      short loc_14000FEDD
0x14000ff4b  mov     rcx, [rbp+Dacl]; P
0x14000ff4f  xor     edx, edx; Tag
0x14000ff51  call    cs:__imp_ExFreePoolWithTag
0x14000ff58  nop     dword ptr [rax+rax+00h]
0x14000ff5d  mov     [r14], rdi
0x14000ff60  jmp     short loc_14000FF0C
```

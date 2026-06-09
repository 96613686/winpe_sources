# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x14002194c`
- end: `0x140021aea`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002118c`

## callees

- `0x140006560`
- `0x1400068c0`
- `0x140021344`
- `0x14002194c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021a72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021ad9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021ad9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021978`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021978`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140021988`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140021988`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400219fa`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400219fa`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140021a13`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140021a13`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140021a34`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140021ac1`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140021a34`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140021ac1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140021a4c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140021a4c`

## string_xrefs

- `0x140021963`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x14002194c  mov     [rsp-18h+arg_0], rbx
0x140021951  mov     [rsp-18h+BufferLength], edx
0x140021955  push    rbp
0x140021956  push    rdi
0x140021957  push    r14
0x140021959  mov     rbp, rsp
0x14002195c  sub     rsp, 70h
0x140021960  mov     rbx, rcx
0x140021963  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x14002196a  xorps   xmm0, xmm0
0x14002196d  lea     rcx, [rbp+DestinationString]; DestinationString
0x140021971  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140021975  mov     r14, r8
0x140021978  call    cs:__imp_RtlInitUnicodeString
0x14002197f  nop     dword ptr [rax+rax+00h]
0x140021984  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140021988  call    cs:__imp_MmGetSystemRoutineAddress
0x14002198f  nop     dword ptr [rax+rax+00h]
0x140021994  mov     rcx, rbx
0x140021997  test    rax, rax
0x14002199a  jz      short loc_1400219C0
0x14002199c  xor     r9d, r9d
0x14002199f  mov     r8, r14
0x1400219a2  lea     edx, [r9+1]
0x1400219a6  call    _guard_dispatch_icall
0x1400219ab  test    eax, eax
0x1400219ad  js      loc_140021A96
0x1400219b3  mov     rcx, [r14]
0x1400219b6  or      word ptr [rcx+2], 8
0x1400219bb  jmp     loc_140021A96
0x1400219c0  xor     eax, eax
0x1400219c2  lea     r9, [rbp+Dacl]
0x1400219c6  xorps   xmm0, xmm0
0x1400219c9  mov     [rbp+var_8], rax
0x1400219cd  lea     r8, [rbp+arg_18]
0x1400219d1  mov     [rbp+arg_18], eax
0x1400219d4  movups  [rbp+SecurityDescriptor], xmm0
0x1400219d8  mov     [rbp+BufferLength], eax
0x1400219db  xor     edi, edi
0x1400219dd  movups  [rbp+var_18], xmm0
0x1400219e1  mov     [rbp+Dacl], rax
0x1400219e5  mov     [r14], rax
0x1400219e8  call    SepSddlDaclFromSDDLString
0x1400219ed  mov     ebx, eax
0x1400219ef  test    eax, eax
0x1400219f1  js      short loc_140021A65
0x1400219f3  lea     edx, [rdi+1]; Revision
0x1400219f6  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400219fa  call    cs:__imp_RtlCreateSecurityDescriptor
0x140021a01  nop     dword ptr [rax+rax+00h]
0x140021a06  mov     r8, [rbp+Dacl]; Dacl
0x140021a0a  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140021a0e  xor     r9d, r9d; DaclDefaulted
0x140021a11  mov     dl, 1; DaclPresent
0x140021a13  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140021a1a  nop     dword ptr [rax+rax+00h]
0x140021a1f  movzx   eax, word ptr [rbp+arg_18]
0x140021a23  lea     r8, [rbp+BufferLength]; BufferLength
0x140021a27  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140021a2b  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140021a2f  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140021a31  mov     [rbp+BufferLength], edi
0x140021a34  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140021a3b  nop     dword ptr [rax+rax+00h]
0x140021a40  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140021a43  lea     ecx, [rdi+1]; PoolType
0x140021a46  mov     r8d, 64536553h; Tag
0x140021a4c  call    cs:__imp_ExAllocatePoolWithTag
0x140021a53  nop     dword ptr [rax+rax+00h]
0x140021a58  mov     rdi, rax
0x140021a5b  test    rax, rax
0x140021a5e  jnz     short loc_140021AA8
0x140021a60  mov     ebx, 0C000009Ah
0x140021a65  cmp     [rbp+Dacl], 0
0x140021a6a  jz      short loc_140021A7E
0x140021a6c  mov     rcx, [rbp+Dacl]; P
0x140021a70  xor     edx, edx; Tag
0x140021a72  call    cs:__imp_ExFreePoolWithTag
0x140021a79  nop     dword ptr [rax+rax+00h]
0x140021a7e  test    rdi, rdi
0x140021a81  jz      short loc_140021A94
0x140021a83  xor     edx, edx; Tag
0x140021a85  mov     rcx, rdi; P
0x140021a88  call    cs:__imp_ExFreePoolWithTag
0x140021a8f  nop     dword ptr [rax+rax+00h]
0x140021a94  mov     eax, ebx
0x140021a96  mov     rbx, [rsp+70h+arg_0]
0x140021a9e  add     rsp, 70h
0x140021aa2  pop     r14
0x140021aa4  pop     rdi
0x140021aa5  pop     rbp
0x140021aa6  retn
0x140021aa8  mov     r8d, [rbp+BufferLength]; Size
0x140021aac  xor     edx, edx; Val
0x140021aae  mov     rcx, rdi; void *
0x140021ab1  call    memset
0x140021ab6  lea     r8, [rbp+BufferLength]; BufferLength
0x140021aba  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140021abd  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140021ac1  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140021ac8  nop     dword ptr [rax+rax+00h]
0x140021acd  mov     ebx, eax
0x140021acf  test    eax, eax
0x140021ad1  js      short loc_140021A65
0x140021ad3  mov     rcx, [rbp+Dacl]; P
0x140021ad7  xor     edx, edx; Tag
0x140021ad9  call    cs:__imp_ExFreePoolWithTag
0x140021ae0  nop     dword ptr [rax+rax+00h]
0x140021ae5  mov     [r14], rdi
0x140021ae8  jmp     short loc_140021A94
```

# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140043734`
- end: `0x1400438d2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140042f4c`

## callees

- `0x14002c710`
- `0x14002cbc0`
- `0x140043104`
- `0x140043734`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400437fb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400437fb`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14004381c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400438a9`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14004381c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400438a9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043834`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043834`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400437e2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400437e2`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140043770`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140043770`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043760`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043760`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004385a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043870`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400438c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004385a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043870`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400438c1`

## string_xrefs

- `0x14004374b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140043734  mov     [rsp-18h+arg_0], rbx
0x140043739  mov     [rsp-18h+BufferLength], edx
0x14004373d  push    rbp
0x14004373e  push    rdi
0x14004373f  push    r14
0x140043741  mov     rbp, rsp
0x140043744  sub     rsp, 70h
0x140043748  mov     rbx, rcx
0x14004374b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140043752  xorps   xmm0, xmm0
0x140043755  lea     rcx, [rbp+DestinationString]; DestinationString
0x140043759  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004375d  mov     r14, r8
0x140043760  call    cs:__imp_RtlInitUnicodeString
0x140043767  nop     dword ptr [rax+rax+00h]
0x14004376c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140043770  call    cs:__imp_MmGetSystemRoutineAddress
0x140043777  nop     dword ptr [rax+rax+00h]
0x14004377c  mov     rcx, rbx
0x14004377f  test    rax, rax
0x140043782  jz      short loc_1400437A8
0x140043784  xor     r9d, r9d
0x140043787  mov     r8, r14
0x14004378a  lea     edx, [r9+1]
0x14004378e  call    _guard_dispatch_icall
0x140043793  test    eax, eax
0x140043795  js      loc_14004387E
0x14004379b  mov     rcx, [r14]
0x14004379e  or      word ptr [rcx+2], 8
0x1400437a3  jmp     loc_14004387E
0x1400437a8  xor     eax, eax
0x1400437aa  lea     r9, [rbp+Dacl]
0x1400437ae  xorps   xmm0, xmm0
0x1400437b1  mov     [rbp+var_8], rax
0x1400437b5  lea     r8, [rbp+arg_18]
0x1400437b9  mov     [rbp+arg_18], eax
0x1400437bc  movups  [rbp+SecurityDescriptor], xmm0
0x1400437c0  mov     [rbp+BufferLength], eax
0x1400437c3  xor     edi, edi
0x1400437c5  movups  [rbp+var_18], xmm0
0x1400437c9  mov     [rbp+Dacl], rax
0x1400437cd  mov     [r14], rax
0x1400437d0  call    SepSddlDaclFromSDDLString
0x1400437d5  mov     ebx, eax
0x1400437d7  test    eax, eax
0x1400437d9  js      short loc_14004384D
0x1400437db  lea     edx, [rdi+1]; Revision
0x1400437de  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400437e2  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400437e9  nop     dword ptr [rax+rax+00h]
0x1400437ee  mov     r8, [rbp+Dacl]; Dacl
0x1400437f2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400437f6  xor     r9d, r9d; DaclDefaulted
0x1400437f9  mov     dl, 1; DaclPresent
0x1400437fb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140043802  nop     dword ptr [rax+rax+00h]
0x140043807  movzx   eax, word ptr [rbp+arg_18]
0x14004380b  lea     r8, [rbp+BufferLength]; BufferLength
0x14004380f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140043813  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140043817  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140043819  mov     [rbp+BufferLength], edi
0x14004381c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140043823  nop     dword ptr [rax+rax+00h]
0x140043828  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x14004382b  lea     ecx, [rdi+1]; PoolType
0x14004382e  mov     r8d, 64536553h; Tag
0x140043834  call    cs:__imp_ExAllocatePoolWithTag
0x14004383b  nop     dword ptr [rax+rax+00h]
0x140043840  mov     rdi, rax
0x140043843  test    rax, rax
0x140043846  jnz     short loc_140043890
0x140043848  mov     ebx, 0C000009Ah
0x14004384d  cmp     [rbp+Dacl], 0
0x140043852  jz      short loc_140043866
0x140043854  mov     rcx, [rbp+Dacl]; P
0x140043858  xor     edx, edx; Tag
0x14004385a  call    cs:__imp_ExFreePoolWithTag
0x140043861  nop     dword ptr [rax+rax+00h]
0x140043866  test    rdi, rdi
0x140043869  jz      short loc_14004387C
0x14004386b  xor     edx, edx; Tag
0x14004386d  mov     rcx, rdi; P
0x140043870  call    cs:__imp_ExFreePoolWithTag
0x140043877  nop     dword ptr [rax+rax+00h]
0x14004387c  mov     eax, ebx
0x14004387e  mov     rbx, [rsp+70h+arg_0]
0x140043886  add     rsp, 70h
0x14004388a  pop     r14
0x14004388c  pop     rdi
0x14004388d  pop     rbp
0x14004388e  retn
0x140043890  mov     r8d, [rbp+BufferLength]; Size
0x140043894  xor     edx, edx; Val
0x140043896  mov     rcx, rdi; void *
0x140043899  call    memset
0x14004389e  lea     r8, [rbp+BufferLength]; BufferLength
0x1400438a2  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x1400438a5  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400438a9  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400438b0  nop     dword ptr [rax+rax+00h]
0x1400438b5  mov     ebx, eax
0x1400438b7  test    eax, eax
0x1400438b9  js      short loc_14004384D
0x1400438bb  mov     rcx, [rbp+Dacl]; P
0x1400438bf  xor     edx, edx; Tag
0x1400438c1  call    cs:__imp_ExFreePoolWithTag
0x1400438c8  nop     dword ptr [rax+rax+00h]
0x1400438cd  mov     [r14], rdi
0x1400438d0  jmp     short loc_14004387C
```

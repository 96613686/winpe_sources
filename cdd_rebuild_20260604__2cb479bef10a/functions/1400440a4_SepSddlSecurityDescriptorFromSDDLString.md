# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x1400440a4`
- end: `0x140044242`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400438cc`

## callees

- `0x1400372d0`
- `0x140037640`
- `0x140043a84`
- `0x1400440a4`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140044152`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140044152`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400441a4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400441a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400441ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400441e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044231`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400441ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400441e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044231`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400440d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400440d0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400440e0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400440e0`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004416b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004416b`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14004418c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140044219`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14004418c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140044219`

## string_xrefs

- `0x1400440bb`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x1400440a4  mov     [rsp-18h+arg_0], rbx
0x1400440a9  mov     [rsp-18h+BufferLength], edx
0x1400440ad  push    rbp
0x1400440ae  push    rdi
0x1400440af  push    r14
0x1400440b1  mov     rbp, rsp
0x1400440b4  sub     rsp, 70h
0x1400440b8  mov     rbx, rcx
0x1400440bb  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x1400440c2  xorps   xmm0, xmm0
0x1400440c5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400440c9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400440cd  mov     r14, r8
0x1400440d0  call    cs:__imp_RtlInitUnicodeString
0x1400440d7  nop     dword ptr [rax+rax+00h]
0x1400440dc  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x1400440e0  call    cs:__imp_MmGetSystemRoutineAddress
0x1400440e7  nop     dword ptr [rax+rax+00h]
0x1400440ec  mov     rcx, rbx
0x1400440ef  test    rax, rax
0x1400440f2  jz      short loc_140044118
0x1400440f4  xor     r9d, r9d
0x1400440f7  mov     r8, r14
0x1400440fa  lea     edx, [r9+1]
0x1400440fe  call    _guard_dispatch_icall
0x140044103  test    eax, eax
0x140044105  js      loc_1400441EE
0x14004410b  mov     rcx, [r14]
0x14004410e  or      word ptr [rcx+2], 8
0x140044113  jmp     loc_1400441EE
0x140044118  xor     eax, eax
0x14004411a  lea     r9, [rbp+Dacl]
0x14004411e  xorps   xmm0, xmm0
0x140044121  mov     [rbp+var_8], rax
0x140044125  lea     r8, [rbp+arg_18]
0x140044129  mov     [rbp+arg_18], eax
0x14004412c  movups  [rbp+SecurityDescriptor], xmm0
0x140044130  mov     [rbp+BufferLength], eax
0x140044133  xor     edi, edi
0x140044135  movups  [rbp+var_18], xmm0
0x140044139  mov     [rbp+Dacl], rax
0x14004413d  mov     [r14], rax
0x140044140  call    SepSddlDaclFromSDDLString
0x140044145  mov     ebx, eax
0x140044147  test    eax, eax
0x140044149  js      short loc_1400441BD
0x14004414b  lea     edx, [rdi+1]; Revision
0x14004414e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140044152  call    cs:__imp_RtlCreateSecurityDescriptor
0x140044159  nop     dword ptr [rax+rax+00h]
0x14004415e  mov     r8, [rbp+Dacl]; Dacl
0x140044162  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140044166  xor     r9d, r9d; DaclDefaulted
0x140044169  mov     dl, 1; DaclPresent
0x14004416b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140044172  nop     dword ptr [rax+rax+00h]
0x140044177  movzx   eax, word ptr [rbp+arg_18]
0x14004417b  lea     r8, [rbp+BufferLength]; BufferLength
0x14004417f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140044183  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140044187  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140044189  mov     [rbp+BufferLength], edi
0x14004418c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140044193  nop     dword ptr [rax+rax+00h]
0x140044198  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x14004419b  lea     ecx, [rdi+1]; PoolType
0x14004419e  mov     r8d, 64536553h; Tag
0x1400441a4  call    cs:__imp_ExAllocatePoolWithTag
0x1400441ab  nop     dword ptr [rax+rax+00h]
0x1400441b0  mov     rdi, rax
0x1400441b3  test    rax, rax
0x1400441b6  jnz     short loc_140044200
0x1400441b8  mov     ebx, 0C000009Ah
0x1400441bd  cmp     [rbp+Dacl], 0
0x1400441c2  jz      short loc_1400441D6
0x1400441c4  mov     rcx, [rbp+Dacl]; P
0x1400441c8  xor     edx, edx; Tag
0x1400441ca  call    cs:__imp_ExFreePoolWithTag
0x1400441d1  nop     dword ptr [rax+rax+00h]
0x1400441d6  test    rdi, rdi
0x1400441d9  jz      short loc_1400441EC
0x1400441db  xor     edx, edx; Tag
0x1400441dd  mov     rcx, rdi; P
0x1400441e0  call    cs:__imp_ExFreePoolWithTag
0x1400441e7  nop     dword ptr [rax+rax+00h]
0x1400441ec  mov     eax, ebx
0x1400441ee  mov     rbx, [rsp+70h+arg_0]
0x1400441f6  add     rsp, 70h
0x1400441fa  pop     r14
0x1400441fc  pop     rdi
0x1400441fd  pop     rbp
0x1400441fe  retn
0x140044200  mov     r8d, [rbp+BufferLength]; Size
0x140044204  xor     edx, edx; Val
0x140044206  mov     rcx, rdi; void *
0x140044209  call    memset
0x14004420e  lea     r8, [rbp+BufferLength]; BufferLength
0x140044212  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140044215  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140044219  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140044220  nop     dword ptr [rax+rax+00h]
0x140044225  mov     ebx, eax
0x140044227  test    eax, eax
0x140044229  js      short loc_1400441BD
0x14004422b  mov     rcx, [rbp+Dacl]; P
0x14004422f  xor     edx, edx; Tag
0x140044231  call    cs:__imp_ExFreePoolWithTag
0x140044238  nop     dword ptr [rax+rax+00h]
0x14004423d  mov     [r14], rdi
0x140044240  jmp     short loc_1400441EC
```

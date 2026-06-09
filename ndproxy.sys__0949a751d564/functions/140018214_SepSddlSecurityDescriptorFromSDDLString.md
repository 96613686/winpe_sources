# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140018214`
- end: `0x1400183b2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140017a4c`

## callees

- `0x140008000`
- `0x1400084c0`
- `0x140017c04`
- `0x140018214`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140018250`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140018250`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018240`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018240`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001833a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018350`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400183a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001833a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018350`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400183a1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400182db`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400182db`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400182fc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140018389`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400182fc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140018389`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018314`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018314`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400182c2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400182c2`

## string_xrefs

- `0x14001822b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140018214  mov     [rsp-18h+arg_0], rbx
0x140018219  mov     [rsp-18h+BufferLength], edx
0x14001821d  push    rbp
0x14001821e  push    rdi
0x14001821f  push    r14
0x140018221  mov     rbp, rsp
0x140018224  sub     rsp, 70h
0x140018228  mov     rbx, rcx
0x14001822b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140018232  xorps   xmm0, xmm0
0x140018235  lea     rcx, [rbp+DestinationString]; DestinationString
0x140018239  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001823d  mov     r14, r8
0x140018240  call    cs:__imp_RtlInitUnicodeString
0x140018247  nop     dword ptr [rax+rax+00h]
0x14001824c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140018250  call    cs:__imp_MmGetSystemRoutineAddress
0x140018257  nop     dword ptr [rax+rax+00h]
0x14001825c  mov     rcx, rbx
0x14001825f  test    rax, rax
0x140018262  jz      short loc_140018288
0x140018264  xor     r9d, r9d
0x140018267  mov     r8, r14
0x14001826a  lea     edx, [r9+1]
0x14001826e  call    _guard_dispatch_icall
0x140018273  test    eax, eax
0x140018275  js      loc_14001835E
0x14001827b  mov     rcx, [r14]
0x14001827e  or      word ptr [rcx+2], 8
0x140018283  jmp     loc_14001835E
0x140018288  xor     eax, eax
0x14001828a  lea     r9, [rbp+Dacl]
0x14001828e  xorps   xmm0, xmm0
0x140018291  mov     [rbp+var_8], rax
0x140018295  lea     r8, [rbp+arg_18]
0x140018299  mov     [rbp+arg_18], eax
0x14001829c  movups  [rbp+SecurityDescriptor], xmm0
0x1400182a0  mov     [rbp+BufferLength], eax
0x1400182a3  xor     edi, edi
0x1400182a5  movups  [rbp+var_18], xmm0
0x1400182a9  mov     [rbp+Dacl], rax
0x1400182ad  mov     [r14], rax
0x1400182b0  call    SepSddlDaclFromSDDLString
0x1400182b5  mov     ebx, eax
0x1400182b7  test    eax, eax
0x1400182b9  js      short loc_14001832D
0x1400182bb  lea     edx, [rdi+1]; Revision
0x1400182be  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400182c2  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400182c9  nop     dword ptr [rax+rax+00h]
0x1400182ce  mov     r8, [rbp+Dacl]; Dacl
0x1400182d2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400182d6  xor     r9d, r9d; DaclDefaulted
0x1400182d9  mov     dl, 1; DaclPresent
0x1400182db  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400182e2  nop     dword ptr [rax+rax+00h]
0x1400182e7  movzx   eax, word ptr [rbp+arg_18]
0x1400182eb  lea     r8, [rbp+BufferLength]; BufferLength
0x1400182ef  or      word ptr [rbp+SecurityDescriptor+2], ax
0x1400182f3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400182f7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x1400182f9  mov     [rbp+BufferLength], edi
0x1400182fc  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140018303  nop     dword ptr [rax+rax+00h]
0x140018308  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x14001830b  lea     ecx, [rdi+1]; PoolType
0x14001830e  mov     r8d, 64536553h; Tag
0x140018314  call    cs:__imp_ExAllocatePoolWithTag
0x14001831b  nop     dword ptr [rax+rax+00h]
0x140018320  mov     rdi, rax
0x140018323  test    rax, rax
0x140018326  jnz     short loc_140018370
0x140018328  mov     ebx, 0C000009Ah
0x14001832d  cmp     [rbp+Dacl], 0
0x140018332  jz      short loc_140018346
0x140018334  mov     rcx, [rbp+Dacl]; P
0x140018338  xor     edx, edx; Tag
0x14001833a  call    cs:__imp_ExFreePoolWithTag
0x140018341  nop     dword ptr [rax+rax+00h]
0x140018346  test    rdi, rdi
0x140018349  jz      short loc_14001835C
0x14001834b  xor     edx, edx; Tag
0x14001834d  mov     rcx, rdi; P
0x140018350  call    cs:__imp_ExFreePoolWithTag
0x140018357  nop     dword ptr [rax+rax+00h]
0x14001835c  mov     eax, ebx
0x14001835e  mov     rbx, [rsp+70h+arg_0]
0x140018366  add     rsp, 70h
0x14001836a  pop     r14
0x14001836c  pop     rdi
0x14001836d  pop     rbp
0x14001836e  retn
0x140018370  mov     r8d, [rbp+BufferLength]; Size
0x140018374  xor     edx, edx; Val
0x140018376  mov     rcx, rdi; void *
0x140018379  call    memset
0x14001837e  lea     r8, [rbp+BufferLength]; BufferLength
0x140018382  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140018385  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140018389  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140018390  nop     dword ptr [rax+rax+00h]
0x140018395  mov     ebx, eax
0x140018397  test    eax, eax
0x140018399  js      short loc_14001832D
0x14001839b  mov     rcx, [rbp+Dacl]; P
0x14001839f  xor     edx, edx; Tag
0x1400183a1  call    cs:__imp_ExFreePoolWithTag
0x1400183a8  nop     dword ptr [rax+rax+00h]
0x1400183ad  mov     [r14], rdi
0x1400183b0  jmp     short loc_14001835C
```

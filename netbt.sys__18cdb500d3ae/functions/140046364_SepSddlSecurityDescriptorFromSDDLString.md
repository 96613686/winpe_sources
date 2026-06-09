# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140046364`
- end: `0x140046502`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140045b8c`

## callees

- `0x140030f80`
- `0x140031440`
- `0x140045d44`
- `0x140046364`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140046390`
- `ntoskrnl!RtlInitUnicodeString` at `0x140046390`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400463a0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400463a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004648a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400464a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400464f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004648a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400464a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400464f1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004642b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004642b`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14004644c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400464d9`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14004644c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400464d9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046464`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046464`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140046412`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140046412`

## string_xrefs

- `0x14004637b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140046364  mov     [rsp-18h+arg_0], rbx
0x140046369  mov     [rsp-18h+BufferLength], edx
0x14004636d  push    rbp
0x14004636e  push    rdi
0x14004636f  push    r14
0x140046371  mov     rbp, rsp
0x140046374  sub     rsp, 70h
0x140046378  mov     rbx, rcx
0x14004637b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140046382  xorps   xmm0, xmm0
0x140046385  lea     rcx, [rbp+DestinationString]; DestinationString
0x140046389  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004638d  mov     r14, r8
0x140046390  call    cs:__imp_RtlInitUnicodeString
0x140046397  nop     dword ptr [rax+rax+00h]
0x14004639c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x1400463a0  call    cs:__imp_MmGetSystemRoutineAddress
0x1400463a7  nop     dword ptr [rax+rax+00h]
0x1400463ac  mov     rcx, rbx
0x1400463af  test    rax, rax
0x1400463b2  jz      short loc_1400463D8
0x1400463b4  xor     r9d, r9d
0x1400463b7  mov     r8, r14
0x1400463ba  lea     edx, [r9+1]
0x1400463be  call    _guard_dispatch_icall
0x1400463c3  test    eax, eax
0x1400463c5  js      loc_1400464AE
0x1400463cb  mov     rcx, [r14]
0x1400463ce  or      word ptr [rcx+2], 8
0x1400463d3  jmp     loc_1400464AE
0x1400463d8  xor     eax, eax
0x1400463da  lea     r9, [rbp+Dacl]
0x1400463de  xorps   xmm0, xmm0
0x1400463e1  mov     [rbp+var_8], rax
0x1400463e5  lea     r8, [rbp+arg_18]
0x1400463e9  mov     [rbp+arg_18], eax
0x1400463ec  movups  [rbp+SecurityDescriptor], xmm0
0x1400463f0  mov     [rbp+BufferLength], eax
0x1400463f3  xor     edi, edi
0x1400463f5  movups  [rbp+var_18], xmm0
0x1400463f9  mov     [rbp+Dacl], rax
0x1400463fd  mov     [r14], rax
0x140046400  call    SepSddlDaclFromSDDLString
0x140046405  mov     ebx, eax
0x140046407  test    eax, eax
0x140046409  js      short loc_14004647D
0x14004640b  lea     edx, [rdi+1]; Revision
0x14004640e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140046412  call    cs:__imp_RtlCreateSecurityDescriptor
0x140046419  nop     dword ptr [rax+rax+00h]
0x14004641e  mov     r8, [rbp+Dacl]; Dacl
0x140046422  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140046426  xor     r9d, r9d; DaclDefaulted
0x140046429  mov     dl, 1; DaclPresent
0x14004642b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140046432  nop     dword ptr [rax+rax+00h]
0x140046437  movzx   eax, word ptr [rbp+arg_18]
0x14004643b  lea     r8, [rbp+BufferLength]; BufferLength
0x14004643f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140046443  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140046447  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140046449  mov     [rbp+BufferLength], edi
0x14004644c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140046453  nop     dword ptr [rax+rax+00h]
0x140046458  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x14004645b  lea     ecx, [rdi+1]; PoolType
0x14004645e  mov     r8d, 64536553h; Tag
0x140046464  call    cs:__imp_ExAllocatePoolWithTag
0x14004646b  nop     dword ptr [rax+rax+00h]
0x140046470  mov     rdi, rax
0x140046473  test    rax, rax
0x140046476  jnz     short loc_1400464C0
0x140046478  mov     ebx, 0C000009Ah
0x14004647d  cmp     [rbp+Dacl], 0
0x140046482  jz      short loc_140046496
0x140046484  mov     rcx, [rbp+Dacl]; P
0x140046488  xor     edx, edx; Tag
0x14004648a  call    cs:__imp_ExFreePoolWithTag
0x140046491  nop     dword ptr [rax+rax+00h]
0x140046496  test    rdi, rdi
0x140046499  jz      short loc_1400464AC
0x14004649b  xor     edx, edx; Tag
0x14004649d  mov     rcx, rdi; P
0x1400464a0  call    cs:__imp_ExFreePoolWithTag
0x1400464a7  nop     dword ptr [rax+rax+00h]
0x1400464ac  mov     eax, ebx
0x1400464ae  mov     rbx, [rsp+70h+arg_0]
0x1400464b6  add     rsp, 70h
0x1400464ba  pop     r14
0x1400464bc  pop     rdi
0x1400464bd  pop     rbp
0x1400464be  retn
0x1400464c0  mov     r8d, [rbp+BufferLength]; Size
0x1400464c4  xor     edx, edx; Val
0x1400464c6  mov     rcx, rdi; void *
0x1400464c9  call    memset
0x1400464ce  lea     r8, [rbp+BufferLength]; BufferLength
0x1400464d2  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x1400464d5  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400464d9  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400464e0  nop     dword ptr [rax+rax+00h]
0x1400464e5  mov     ebx, eax
0x1400464e7  test    eax, eax
0x1400464e9  js      short loc_14004647D
0x1400464eb  mov     rcx, [rbp+Dacl]; P
0x1400464ef  xor     edx, edx; Tag
0x1400464f1  call    cs:__imp_ExFreePoolWithTag
0x1400464f8  nop     dword ptr [rax+rax+00h]
0x1400464fd  mov     [r14], rdi
0x140046500  jmp     short loc_1400464AC
```

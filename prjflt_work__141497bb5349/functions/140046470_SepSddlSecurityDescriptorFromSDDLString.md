# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140046470`
- end: `0x14004660e`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140045c88`

## callees

- `0x14000bb00`
- `0x14000be80`
- `0x140045e40`
- `0x140046470`

## import_xrefs

- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140046558`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400465e5`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140046558`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400465e5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046570`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046570`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14004651e`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14004651e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046596`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400465ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400465fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046596`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400465ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400465fd`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400464ac`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400464ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004649c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004649c`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140046537`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140046537`

## string_xrefs

- `0x140046487`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140046470  mov     [rsp-18h+arg_0], rbx
0x140046475  mov     [rsp-18h+BufferLength], edx
0x140046479  push    rbp
0x14004647a  push    rdi
0x14004647b  push    r14
0x14004647d  mov     rbp, rsp
0x140046480  sub     rsp, 70h
0x140046484  mov     rbx, rcx
0x140046487  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x14004648e  xorps   xmm0, xmm0
0x140046491  lea     rcx, [rbp+DestinationString]; DestinationString
0x140046495  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140046499  mov     r14, r8
0x14004649c  call    cs:__imp_RtlInitUnicodeString
0x1400464a3  nop     dword ptr [rax+rax+00h]
0x1400464a8  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x1400464ac  call    cs:__imp_MmGetSystemRoutineAddress
0x1400464b3  nop     dword ptr [rax+rax+00h]
0x1400464b8  mov     rcx, rbx
0x1400464bb  test    rax, rax
0x1400464be  jz      short loc_1400464E4
0x1400464c0  xor     r9d, r9d
0x1400464c3  mov     r8, r14
0x1400464c6  lea     edx, [r9+1]
0x1400464ca  call    _guard_dispatch_icall
0x1400464cf  test    eax, eax
0x1400464d1  js      loc_1400465BA
0x1400464d7  mov     rcx, [r14]
0x1400464da  or      word ptr [rcx+2], 8
0x1400464df  jmp     loc_1400465BA
0x1400464e4  xor     eax, eax
0x1400464e6  lea     r9, [rbp+Dacl]
0x1400464ea  xorps   xmm0, xmm0
0x1400464ed  mov     [rbp+var_8], rax
0x1400464f1  lea     r8, [rbp+arg_18]
0x1400464f5  mov     [rbp+arg_18], eax
0x1400464f8  movups  [rbp+SecurityDescriptor], xmm0
0x1400464fc  mov     [rbp+BufferLength], eax
0x1400464ff  xor     edi, edi
0x140046501  movups  [rbp+var_18], xmm0
0x140046505  mov     [rbp+Dacl], rax
0x140046509  mov     [r14], rax
0x14004650c  call    SepSddlDaclFromSDDLString
0x140046511  mov     ebx, eax
0x140046513  test    eax, eax
0x140046515  js      short loc_140046589
0x140046517  lea     edx, [rdi+1]; Revision
0x14004651a  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14004651e  call    cs:__imp_RtlCreateSecurityDescriptor
0x140046525  nop     dword ptr [rax+rax+00h]
0x14004652a  mov     r8, [rbp+Dacl]; Dacl
0x14004652e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140046532  xor     r9d, r9d; DaclDefaulted
0x140046535  mov     dl, 1; DaclPresent
0x140046537  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14004653e  nop     dword ptr [rax+rax+00h]
0x140046543  movzx   eax, word ptr [rbp+arg_18]
0x140046547  lea     r8, [rbp+BufferLength]; BufferLength
0x14004654b  or      word ptr [rbp+SecurityDescriptor+2], ax
0x14004654f  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140046553  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140046555  mov     [rbp+BufferLength], edi
0x140046558  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14004655f  nop     dword ptr [rax+rax+00h]
0x140046564  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140046567  lea     ecx, [rdi+1]; PoolType
0x14004656a  mov     r8d, 64536553h; Tag
0x140046570  call    cs:__imp_ExAllocatePoolWithTag
0x140046577  nop     dword ptr [rax+rax+00h]
0x14004657c  mov     rdi, rax
0x14004657f  test    rax, rax
0x140046582  jnz     short loc_1400465CC
0x140046584  mov     ebx, 0C000009Ah
0x140046589  cmp     [rbp+Dacl], 0
0x14004658e  jz      short loc_1400465A2
0x140046590  mov     rcx, [rbp+Dacl]; P
0x140046594  xor     edx, edx; Tag
0x140046596  call    cs:__imp_ExFreePoolWithTag
0x14004659d  nop     dword ptr [rax+rax+00h]
0x1400465a2  test    rdi, rdi
0x1400465a5  jz      short loc_1400465B8
0x1400465a7  xor     edx, edx; Tag
0x1400465a9  mov     rcx, rdi; P
0x1400465ac  call    cs:__imp_ExFreePoolWithTag
0x1400465b3  nop     dword ptr [rax+rax+00h]
0x1400465b8  mov     eax, ebx
0x1400465ba  mov     rbx, [rsp+70h+arg_0]
0x1400465c2  add     rsp, 70h
0x1400465c6  pop     r14
0x1400465c8  pop     rdi
0x1400465c9  pop     rbp
0x1400465ca  retn
0x1400465cc  mov     r8d, [rbp+BufferLength]; Size
0x1400465d0  xor     edx, edx; Val
0x1400465d2  mov     rcx, rdi; void *
0x1400465d5  call    memset
0x1400465da  lea     r8, [rbp+BufferLength]; BufferLength
0x1400465de  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x1400465e1  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400465e5  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400465ec  nop     dword ptr [rax+rax+00h]
0x1400465f1  mov     ebx, eax
0x1400465f3  test    eax, eax
0x1400465f5  js      short loc_140046589
0x1400465f7  mov     rcx, [rbp+Dacl]; P
0x1400465fb  xor     edx, edx; Tag
0x1400465fd  call    cs:__imp_ExFreePoolWithTag
0x140046604  nop     dword ptr [rax+rax+00h]
0x140046609  mov     [r14], rdi
0x14004660c  jmp     short loc_1400465B8
```

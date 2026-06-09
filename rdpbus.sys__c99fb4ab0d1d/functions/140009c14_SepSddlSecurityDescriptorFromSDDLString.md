# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140009c14`
- end: `0x140009db2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000943c`

## callees

- `0x140002560`
- `0x140002940`
- `0x1400095f4`
- `0x140009c14`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140009c40`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009c40`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140009c50`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140009c50`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140009cdb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140009cdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009d3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009d50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009da1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009d3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009d50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009da1`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140009cc2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140009cc2`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140009cfc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140009d89`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140009cfc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140009d89`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140009d14`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140009d14`

## string_xrefs

- `0x140009c2b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140009c14  mov     [rsp-18h+arg_0], rbx
0x140009c19  mov     [rsp-18h+BufferLength], edx
0x140009c1d  push    rbp
0x140009c1e  push    rdi
0x140009c1f  push    r14
0x140009c21  mov     rbp, rsp
0x140009c24  sub     rsp, 70h
0x140009c28  mov     rbx, rcx
0x140009c2b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140009c32  xorps   xmm0, xmm0
0x140009c35  lea     rcx, [rbp+DestinationString]; DestinationString
0x140009c39  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140009c3d  mov     r14, r8
0x140009c40  call    cs:__imp_RtlInitUnicodeString
0x140009c47  nop     dword ptr [rax+rax+00h]
0x140009c4c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140009c50  call    cs:__imp_MmGetSystemRoutineAddress
0x140009c57  nop     dword ptr [rax+rax+00h]
0x140009c5c  mov     rcx, rbx
0x140009c5f  test    rax, rax
0x140009c62  jz      short loc_140009C88
0x140009c64  xor     r9d, r9d
0x140009c67  mov     r8, r14
0x140009c6a  lea     edx, [r9+1]
0x140009c6e  call    _guard_dispatch_icall
0x140009c73  test    eax, eax
0x140009c75  js      loc_140009D5E
0x140009c7b  mov     rcx, [r14]
0x140009c7e  or      word ptr [rcx+2], 8
0x140009c83  jmp     loc_140009D5E
0x140009c88  xor     eax, eax
0x140009c8a  lea     r9, [rbp+Dacl]
0x140009c8e  xorps   xmm0, xmm0
0x140009c91  mov     [rbp+var_8], rax
0x140009c95  lea     r8, [rbp+arg_18]
0x140009c99  mov     [rbp+arg_18], eax
0x140009c9c  movups  [rbp+SecurityDescriptor], xmm0
0x140009ca0  mov     [rbp+BufferLength], eax
0x140009ca3  xor     edi, edi
0x140009ca5  movups  [rbp+var_18], xmm0
0x140009ca9  mov     [rbp+Dacl], rax
0x140009cad  mov     [r14], rax
0x140009cb0  call    SepSddlDaclFromSDDLString
0x140009cb5  mov     ebx, eax
0x140009cb7  test    eax, eax
0x140009cb9  js      short loc_140009D2D
0x140009cbb  lea     edx, [rdi+1]; Revision
0x140009cbe  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140009cc2  call    cs:__imp_RtlCreateSecurityDescriptor
0x140009cc9  nop     dword ptr [rax+rax+00h]
0x140009cce  mov     r8, [rbp+Dacl]; Dacl
0x140009cd2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140009cd6  xor     r9d, r9d; DaclDefaulted
0x140009cd9  mov     dl, 1; DaclPresent
0x140009cdb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140009ce2  nop     dword ptr [rax+rax+00h]
0x140009ce7  movzx   eax, word ptr [rbp+arg_18]
0x140009ceb  lea     r8, [rbp+BufferLength]; BufferLength
0x140009cef  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140009cf3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140009cf7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140009cf9  mov     [rbp+BufferLength], edi
0x140009cfc  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140009d03  nop     dword ptr [rax+rax+00h]
0x140009d08  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140009d0b  lea     ecx, [rdi+1]; PoolType
0x140009d0e  mov     r8d, 64536553h; Tag
0x140009d14  call    cs:__imp_ExAllocatePoolWithTag
0x140009d1b  nop     dword ptr [rax+rax+00h]
0x140009d20  mov     rdi, rax
0x140009d23  test    rax, rax
0x140009d26  jnz     short loc_140009D70
0x140009d28  mov     ebx, 0C000009Ah
0x140009d2d  cmp     [rbp+Dacl], 0
0x140009d32  jz      short loc_140009D46
0x140009d34  mov     rcx, [rbp+Dacl]; P
0x140009d38  xor     edx, edx; Tag
0x140009d3a  call    cs:__imp_ExFreePoolWithTag
0x140009d41  nop     dword ptr [rax+rax+00h]
0x140009d46  test    rdi, rdi
0x140009d49  jz      short loc_140009D5C
0x140009d4b  xor     edx, edx; Tag
0x140009d4d  mov     rcx, rdi; P
0x140009d50  call    cs:__imp_ExFreePoolWithTag
0x140009d57  nop     dword ptr [rax+rax+00h]
0x140009d5c  mov     eax, ebx
0x140009d5e  mov     rbx, [rsp+70h+arg_0]
0x140009d66  add     rsp, 70h
0x140009d6a  pop     r14
0x140009d6c  pop     rdi
0x140009d6d  pop     rbp
0x140009d6e  retn
0x140009d70  mov     r8d, [rbp+BufferLength]; Size
0x140009d74  xor     edx, edx; Val
0x140009d76  mov     rcx, rdi; void *
0x140009d79  call    memset
0x140009d7e  lea     r8, [rbp+BufferLength]; BufferLength
0x140009d82  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140009d85  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140009d89  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140009d90  nop     dword ptr [rax+rax+00h]
0x140009d95  mov     ebx, eax
0x140009d97  test    eax, eax
0x140009d99  js      short loc_140009D2D
0x140009d9b  mov     rcx, [rbp+Dacl]; P
0x140009d9f  xor     edx, edx; Tag
0x140009da1  call    cs:__imp_ExFreePoolWithTag
0x140009da8  nop     dword ptr [rax+rax+00h]
0x140009dad  mov     [r14], rdi
0x140009db0  jmp     short loc_140009D5C
```

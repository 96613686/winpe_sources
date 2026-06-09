# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140053454`
- end: `0x1400535f2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140052c7c`

## callees

- `0x140017f20`
- `0x140018280`
- `0x140052e34`
- `0x140053454`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140053502`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140053502`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14005351b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14005351b`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14005353c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400535c9`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14005353c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400535c9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140053490`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140053490`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053480`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053480`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005357a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053590`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400535e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005357a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053590`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400535e1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053554`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053554`

## string_xrefs

- `0x14005346b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
  UNICODE_STRING DestinationString; // [rsp+38h] [rbp-38h] BYREF
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
0x140053454  mov     [rsp-18h+arg_0], rbx
0x140053459  mov     [rsp-18h+BufferLength], edx
0x14005345d  push    rbp
0x14005345e  push    rdi
0x14005345f  push    r14
0x140053461  mov     rbp, rsp
0x140053464  sub     rsp, 70h
0x140053468  mov     rbx, rcx
0x14005346b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140053472  xorps   xmm0, xmm0
0x140053475  lea     rcx, [rbp+DestinationString]; DestinationString
0x140053479  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14005347d  mov     r14, r8
0x140053480  call    cs:__imp_RtlInitUnicodeString
0x140053487  nop     dword ptr [rax+rax+00h]
0x14005348c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140053490  call    cs:__imp_MmGetSystemRoutineAddress
0x140053497  nop     dword ptr [rax+rax+00h]
0x14005349c  mov     rcx, rbx
0x14005349f  test    rax, rax
0x1400534a2  jz      short loc_1400534C8
0x1400534a4  xor     r9d, r9d
0x1400534a7  mov     r8, r14
0x1400534aa  lea     edx, [r9+1]
0x1400534ae  call    _guard_dispatch_icall
0x1400534b3  test    eax, eax
0x1400534b5  js      loc_14005359E
0x1400534bb  mov     rcx, [r14]
0x1400534be  or      word ptr [rcx+2], 8
0x1400534c3  jmp     loc_14005359E
0x1400534c8  xor     eax, eax
0x1400534ca  lea     r9, [rbp+Dacl]
0x1400534ce  xorps   xmm0, xmm0
0x1400534d1  mov     [rbp+var_8], rax
0x1400534d5  lea     r8, [rbp+arg_18]
0x1400534d9  mov     [rbp+arg_18], eax
0x1400534dc  movups  [rbp+SecurityDescriptor], xmm0
0x1400534e0  mov     [rbp+BufferLength], eax
0x1400534e3  xor     edi, edi
0x1400534e5  movups  [rbp+var_18], xmm0
0x1400534e9  mov     [rbp+Dacl], rax
0x1400534ed  mov     [r14], rax
0x1400534f0  call    SepSddlDaclFromSDDLString
0x1400534f5  mov     ebx, eax
0x1400534f7  test    eax, eax
0x1400534f9  js      short loc_14005356D
0x1400534fb  lea     edx, [rdi+1]; Revision
0x1400534fe  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140053502  call    cs:__imp_RtlCreateSecurityDescriptor
0x140053509  nop     dword ptr [rax+rax+00h]
0x14005350e  mov     r8, [rbp+Dacl]; Dacl
0x140053512  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140053516  xor     r9d, r9d; DaclDefaulted
0x140053519  mov     dl, 1; DaclPresent
0x14005351b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140053522  nop     dword ptr [rax+rax+00h]
0x140053527  movzx   eax, word ptr [rbp+arg_18]
0x14005352b  lea     r8, [rbp+BufferLength]; BufferLength
0x14005352f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140053533  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140053537  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140053539  mov     [rbp+BufferLength], edi
0x14005353c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140053543  nop     dword ptr [rax+rax+00h]
0x140053548  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x14005354b  lea     ecx, [rdi+1]; PoolType
0x14005354e  mov     r8d, 64536553h; Tag
0x140053554  call    cs:__imp_ExAllocatePoolWithTag
0x14005355b  nop     dword ptr [rax+rax+00h]
0x140053560  mov     rdi, rax
0x140053563  test    rax, rax
0x140053566  jnz     short loc_1400535B0
0x140053568  mov     ebx, 0C000009Ah
0x14005356d  cmp     [rbp+Dacl], 0
0x140053572  jz      short loc_140053586
0x140053574  mov     rcx, [rbp+Dacl]; P
0x140053578  xor     edx, edx; Tag
0x14005357a  call    cs:__imp_ExFreePoolWithTag
0x140053581  nop     dword ptr [rax+rax+00h]
0x140053586  test    rdi, rdi
0x140053589  jz      short loc_14005359C
0x14005358b  xor     edx, edx; Tag
0x14005358d  mov     rcx, rdi; P
0x140053590  call    cs:__imp_ExFreePoolWithTag
0x140053597  nop     dword ptr [rax+rax+00h]
0x14005359c  mov     eax, ebx
0x14005359e  mov     rbx, [rsp+70h+arg_0]
0x1400535a6  add     rsp, 70h
0x1400535aa  pop     r14
0x1400535ac  pop     rdi
0x1400535ad  pop     rbp
0x1400535ae  retn
0x1400535b0  mov     r8d, [rbp+BufferLength]; Size
0x1400535b4  xor     edx, edx; Val
0x1400535b6  mov     rcx, rdi; void *
0x1400535b9  call    memset
0x1400535be  lea     r8, [rbp+BufferLength]; BufferLength
0x1400535c2  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x1400535c5  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400535c9  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400535d0  nop     dword ptr [rax+rax+00h]
0x1400535d5  mov     ebx, eax
0x1400535d7  test    eax, eax
0x1400535d9  js      short loc_14005356D
0x1400535db  mov     rcx, [rbp+Dacl]; P
0x1400535df  xor     edx, edx; Tag
0x1400535e1  call    cs:__imp_ExFreePoolWithTag
0x1400535e8  nop     dword ptr [rax+rax+00h]
0x1400535ed  mov     [r14], rdi
0x1400535f0  jmp     short loc_14005359C
```

# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140157a34`
- end: `0x140157bd2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14015725c`

## callees

- `0x1400eb460`
- `0x1400eb7c0`
- `0x140157414`
- `0x140157a34`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140157b34`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140157b34`
- `ntoskrnl!RtlInitUnicodeString` at `0x140157a60`
- `ntoskrnl!RtlInitUnicodeString` at `0x140157a60`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140157a70`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140157a70`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140157afb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140157afb`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140157ae2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140157ae2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157b5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157b70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157bc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157b5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157b70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157bc1`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140157b1c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140157ba9`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140157b1c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140157ba9`

## string_xrefs

- `0x140157a4b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140157a34  mov     [rsp-18h+arg_0], rbx
0x140157a39  mov     [rsp-18h+BufferLength], edx
0x140157a3d  push    rbp
0x140157a3e  push    rdi
0x140157a3f  push    r14
0x140157a41  mov     rbp, rsp
0x140157a44  sub     rsp, 70h
0x140157a48  mov     rbx, rcx
0x140157a4b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140157a52  xorps   xmm0, xmm0
0x140157a55  lea     rcx, [rbp+DestinationString]; DestinationString
0x140157a59  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140157a5d  mov     r14, r8
0x140157a60  call    cs:__imp_RtlInitUnicodeString
0x140157a67  nop     dword ptr [rax+rax+00h]
0x140157a6c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140157a70  call    cs:__imp_MmGetSystemRoutineAddress
0x140157a77  nop     dword ptr [rax+rax+00h]
0x140157a7c  mov     rcx, rbx
0x140157a7f  test    rax, rax
0x140157a82  jz      short loc_140157AA8
0x140157a84  xor     r9d, r9d
0x140157a87  mov     r8, r14
0x140157a8a  lea     edx, [r9+1]
0x140157a8e  call    _guard_dispatch_icall
0x140157a93  test    eax, eax
0x140157a95  js      loc_140157B7E
0x140157a9b  mov     rcx, [r14]
0x140157a9e  or      word ptr [rcx+2], 8
0x140157aa3  jmp     loc_140157B7E
0x140157aa8  xor     eax, eax
0x140157aaa  lea     r9, [rbp+Dacl]
0x140157aae  xorps   xmm0, xmm0
0x140157ab1  mov     [rbp+var_8], rax
0x140157ab5  lea     r8, [rbp+arg_18]
0x140157ab9  mov     [rbp+arg_18], eax
0x140157abc  movups  [rbp+SecurityDescriptor], xmm0
0x140157ac0  mov     [rbp+BufferLength], eax
0x140157ac3  xor     edi, edi
0x140157ac5  movups  [rbp+var_18], xmm0
0x140157ac9  mov     [rbp+Dacl], rax
0x140157acd  mov     [r14], rax
0x140157ad0  call    SepSddlDaclFromSDDLString
0x140157ad5  mov     ebx, eax
0x140157ad7  test    eax, eax
0x140157ad9  js      short loc_140157B4D
0x140157adb  lea     edx, [rdi+1]; Revision
0x140157ade  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140157ae2  call    cs:__imp_RtlCreateSecurityDescriptor
0x140157ae9  nop     dword ptr [rax+rax+00h]
0x140157aee  mov     r8, [rbp+Dacl]; Dacl
0x140157af2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140157af6  xor     r9d, r9d; DaclDefaulted
0x140157af9  mov     dl, 1; DaclPresent
0x140157afb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140157b02  nop     dword ptr [rax+rax+00h]
0x140157b07  movzx   eax, word ptr [rbp+arg_18]
0x140157b0b  lea     r8, [rbp+BufferLength]; BufferLength
0x140157b0f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140157b13  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140157b17  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140157b19  mov     [rbp+BufferLength], edi
0x140157b1c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140157b23  nop     dword ptr [rax+rax+00h]
0x140157b28  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140157b2b  lea     ecx, [rdi+1]; PoolType
0x140157b2e  mov     r8d, 64536553h; Tag
0x140157b34  call    cs:__imp_ExAllocatePoolWithTag
0x140157b3b  nop     dword ptr [rax+rax+00h]
0x140157b40  mov     rdi, rax
0x140157b43  test    rax, rax
0x140157b46  jnz     short loc_140157B90
0x140157b48  mov     ebx, 0C000009Ah
0x140157b4d  cmp     [rbp+Dacl], 0
0x140157b52  jz      short loc_140157B66
0x140157b54  mov     rcx, [rbp+Dacl]; P
0x140157b58  xor     edx, edx; Tag
0x140157b5a  call    cs:__imp_ExFreePoolWithTag
0x140157b61  nop     dword ptr [rax+rax+00h]
0x140157b66  test    rdi, rdi
0x140157b69  jz      short loc_140157B7C
0x140157b6b  xor     edx, edx; Tag
0x140157b6d  mov     rcx, rdi; P
0x140157b70  call    cs:__imp_ExFreePoolWithTag
0x140157b77  nop     dword ptr [rax+rax+00h]
0x140157b7c  mov     eax, ebx
0x140157b7e  mov     rbx, [rsp+70h+arg_0]
0x140157b86  add     rsp, 70h
0x140157b8a  pop     r14
0x140157b8c  pop     rdi
0x140157b8d  pop     rbp
0x140157b8e  retn
0x140157b90  mov     r8d, [rbp+BufferLength]; Size
0x140157b94  xor     edx, edx; Val
0x140157b96  mov     rcx, rdi; void *
0x140157b99  call    memset
0x140157b9e  lea     r8, [rbp+BufferLength]; BufferLength
0x140157ba2  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140157ba5  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140157ba9  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140157bb0  nop     dword ptr [rax+rax+00h]
0x140157bb5  mov     ebx, eax
0x140157bb7  test    eax, eax
0x140157bb9  js      short loc_140157B4D
0x140157bbb  mov     rcx, [rbp+Dacl]; P
0x140157bbf  xor     edx, edx; Tag
0x140157bc1  call    cs:__imp_ExFreePoolWithTag
0x140157bc8  nop     dword ptr [rax+rax+00h]
0x140157bcd  mov     [r14], rdi
0x140157bd0  jmp     short loc_140157B7C
```

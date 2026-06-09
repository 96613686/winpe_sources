# NbtReadLinkageInformation

- ea: `0x140049ba0`
- end: `0x140049d10`
- name: `NbtReadLinkageInformation`
- size: `368`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, HANDLE KeyHandle@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400493c4`

## callees

- `0x140049ba0`
- `0x14004a990`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140049bd3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049bd3`
- `ntoskrnl!ZwQueryValueKey` at `0x140049bfe`
- `ntoskrnl!ZwQueryValueKey` at `0x140049c65`
- `ntoskrnl!ZwQueryValueKey` at `0x140049bfe`
- `ntoskrnl!ZwQueryValueKey` at `0x140049c65`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049cde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049d02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049cde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049d02`
- `ntoskrnl!ExAllocatePool2` at `0x140049c2e`
- `ntoskrnl!ExAllocatePool2` at `0x140049c2e`

## pseudocode

```c
__int64 __fastcall NbtReadLinkageInformation(
        PCWSTR SourceString,
        HANDLE KeyHandle,
        __int64 a3,
        unsigned int **a4,
        __int64 a5)
{
  unsigned int *Pool2; // rax
  unsigned int *v8; // rbx
  NTSTATUS v9; // esi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+60h] [rbp+18h] BYREF

  ResultLength = 0;
  *a4 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, 0, 0, &ResultLength) != -1073741789
    || !ResultLength )
  {
    return 3221225824LL;
  }
  Pool2 = (unsigned int *)ExAllocatePool2(64, ResultLength, 859005518);
  v8 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v9 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, Pool2, ResultLength, &ResultLength);
  if ( v9 >= 0 )
  {
    if ( ResultLength )
    {
      *a4 = v8;
      NbtParseMultiSzEntries((PCWSTR)((char *)v8 + v8[2]), a5);
      return 0;
    }
    ExFreePoolWithTag(v8, 0);
    return 3221225824LL;
  }
  ExFreePoolWithTag(v8, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140049ba0  mov     [rsp+arg_0], rbx
0x140049ba5  mov     [rsp+arg_8], rsi
0x140049baa  mov     [rsp+arg_10], r8d
0x140049baf  push    rdi
0x140049bb0  sub     rsp, 40h
0x140049bb4  mov     rsi, rdx
0x140049bb7  xorps   xmm0, xmm0
0x140049bba  mov     rdx, rcx; SourceString
0x140049bbd  xor     ebx, ebx
0x140049bbf  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x140049bc4  mov     [rsp+48h+arg_10], ebx
0x140049bc8  mov     rdi, r9
0x140049bcb  mov     [r9], rbx
0x140049bce  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x140049bd3  call    cs:__imp_RtlInitUnicodeString
0x140049bda  nop     dword ptr [rax+rax+00h]
0x140049bdf  lea     rax, [rsp+48h+arg_10]
0x140049be4  xor     r9d, r9d; KeyValueInformation
0x140049be7  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140049bec  lea     rdx, [rsp+48h+DestinationString]; ValueName
0x140049bf1  mov     r8d, 1; KeyValueInformationClass
0x140049bf7  mov     [rsp+48h+Length], ebx; Length
0x140049bfb  mov     rcx, rsi; KeyHandle
0x140049bfe  call    cs:__imp_ZwQueryValueKey
0x140049c05  nop     dword ptr [rax+rax+00h]
0x140049c0a  cmp     eax, 0C0000023h
0x140049c0f  jnz     loc_140049CD2
0x140049c15  mov     eax, [rsp+48h+arg_10]
0x140049c19  test    eax, eax
0x140049c1b  jz      loc_140049CD2
0x140049c21  mov     edx, eax
0x140049c23  mov     ecx, 40h ; '@'
0x140049c28  mov     r8d, 3333624Eh
0x140049c2e  call    cs:__imp_ExAllocatePool2
0x140049c35  nop     dword ptr [rax+rax+00h]
0x140049c3a  mov     rbx, rax
0x140049c3d  test    rax, rax
0x140049c40  jz      short loc_140049CBC
0x140049c42  lea     rax, [rsp+48h+arg_10]
0x140049c47  mov     r9, rbx; KeyValueInformation
0x140049c4a  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140049c4f  lea     rdx, [rsp+48h+DestinationString]; ValueName
0x140049c54  mov     eax, [rsp+48h+arg_10]
0x140049c58  mov     r8d, 1; KeyValueInformationClass
0x140049c5e  mov     rcx, rsi; KeyHandle
0x140049c61  mov     [rsp+48h+Length], eax; Length
0x140049c65  call    cs:__imp_ZwQueryValueKey
0x140049c6c  nop     dword ptr [rax+rax+00h]
0x140049c71  mov     esi, eax
0x140049c73  test    eax, eax
0x140049c75  js      short loc_140049CD9
0x140049c77  cmp     [rsp+48h+arg_10], 0
0x140049c7c  jz      short loc_140049CFD
0x140049c7e  mov     [rdi], rbx
0x140049c81  mov     r9, rdi
0x140049c84  mov     eax, [rbx+8]
0x140049c87  mov     r8d, 80h
0x140049c8d  mov     edx, [rbx+0Ch]
0x140049c90  add     rdx, rax
0x140049c93  add     rdx, rbx
0x140049c96  lea     rcx, [rax+rbx]; SourceString
0x140049c9a  mov     rax, [rsp+48h+arg_20]
0x140049c9f  mov     qword ptr [rsp+48h+Length], rax; __int64
0x140049ca4  call    NbtParseMultiSzEntries
0x140049ca9  xor     eax, eax
0x140049cab  mov     rbx, [rsp+48h+arg_0]
0x140049cb0  mov     rsi, [rsp+48h+arg_8]
0x140049cb5  add     rsp, 40h
0x140049cb9  pop     rdi
0x140049cba  retn
0x140049cbc  mov     eax, 0C000009Ah
0x140049cc1  mov     rbx, [rsp+48h+arg_0]
0x140049cc6  mov     rsi, [rsp+48h+arg_8]
0x140049ccb  add     rsp, 40h
0x140049ccf  pop     rdi
0x140049cd0  retn
0x140049cd2  mov     eax, 0C0000160h
0x140049cd7  jmp     short loc_140049CAB
0x140049cd9  xor     edx, edx; Tag
0x140049cdb  mov     rcx, rbx; P
0x140049cde  call    cs:__imp_ExFreePoolWithTag
0x140049ce5  nop     dword ptr [rax+rax+00h]
0x140049cea  mov     rbx, [rsp+48h+arg_0]
0x140049cef  mov     eax, esi
0x140049cf1  mov     rsi, [rsp+48h+arg_8]
0x140049cf6  add     rsp, 40h
0x140049cfa  pop     rdi
0x140049cfb  retn
0x140049cfd  xor     edx, edx; Tag
0x140049cff  mov     rcx, rbx; P
0x140049d02  call    cs:__imp_ExFreePoolWithTag
0x140049d09  nop     dword ptr [rax+rax+00h]
0x140049d0e  jmp     short loc_140049CD2
```

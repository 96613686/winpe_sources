# NbtReadSingleParameter

- ea: `0x14004b260`
- end: `0x14004b37e`
- name: `NbtReadSingleParameter`
- size: `286`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14004aaf4`
- `0x14004abd4`
- `0x14004b384`

## callees

- `0x140014910`
- `0x14004b260`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14004b293`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004b293`
- `ntoskrnl!ZwQueryValueKey` at `0x14004b2c9`
- `ntoskrnl!ZwQueryValueKey` at `0x14004b30d`
- `ntoskrnl!ZwQueryValueKey` at `0x14004b2c9`
- `ntoskrnl!ZwQueryValueKey` at `0x14004b30d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b327`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b327`

## pseudocode

```c
__int64 __fastcall NbtReadSingleParameter(HANDLE KeyHandle, const WCHAR *a2, unsigned int a3, unsigned int a4)
{
  __int64 v8; // rcx
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+18h] BYREF

  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, &qword_1400385B0, 0xF0u, &ResultLength) >= 0
    && dword_1400385BC == 4 )
  {
    result = *(unsigned int *)((char *)&qword_1400385B0 + (unsigned int)dword_1400385B8);
    if ( (unsigned int)result < a4 )
      return a4;
  }
  else
  {
    if ( (int)NbtAppendString(v8, a2, &DestinationString) >= 0 )
    {
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValueFullInformation,
             &qword_1400385B0,
             0xF0u,
             &ResultLength) >= 0
        && dword_1400385BC == 4 )
      {
        a3 = *(_DWORD *)((char *)&qword_1400385B0 + (unsigned int)dword_1400385B8);
        if ( a3 < a4 )
          a3 = a4;
      }
      ExFreePoolWithTag(DestinationString.Buffer, 0x3033624Eu);
    }
    return a3;
  }
  return result;
}

```

## disassembly

```asm
0x14004b260  mov     [rsp+arg_0], rbx
0x14004b265  mov     [rsp+arg_8], rbp
0x14004b26a  push    rsi
0x14004b26b  push    rdi
0x14004b26c  push    r14
0x14004b26e  sub     rsp, 40h
0x14004b272  mov     rdi, rcx
0x14004b275  mov     [rsp+58h+arg_10], 0
0x14004b27d  xorps   xmm0, xmm0
0x14004b280  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14004b285  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14004b28a  mov     ebp, r9d
0x14004b28d  mov     esi, r8d
0x14004b290  mov     rbx, rdx
0x14004b293  call    cs:__imp_RtlInitUnicodeString
0x14004b29a  nop     dword ptr [rax+rax+00h]
0x14004b29f  lea     rax, [rsp+58h+arg_10]
0x14004b2a4  mov     r8d, 1; KeyValueInformationClass
0x14004b2aa  mov     [rsp+58h+ResultLength], rax; ResultLength
0x14004b2af  lea     r14, qword_1400385B0
0x14004b2b6  mov     r9, r14; KeyValueInformation
0x14004b2b9  mov     [rsp+58h+Length], 0F0h; Length
0x14004b2c1  lea     rdx, [rsp+58h+DestinationString]; ValueName
0x14004b2c6  mov     rcx, rdi; KeyHandle
0x14004b2c9  call    cs:__imp_ZwQueryValueKey
0x14004b2d0  nop     dword ptr [rax+rax+00h]
0x14004b2d5  test    eax, eax
0x14004b2d7  jns     short loc_14004B349
0x14004b2d9  lea     r8, [rsp+58h+DestinationString]
0x14004b2de  mov     rdx, rbx
0x14004b2e1  call    NbtAppendString
0x14004b2e6  test    eax, eax
0x14004b2e8  js      short loc_14004B333
0x14004b2ea  lea     rax, [rsp+58h+arg_10]
0x14004b2ef  mov     r9, r14; KeyValueInformation
0x14004b2f2  mov     [rsp+58h+ResultLength], rax; ResultLength
0x14004b2f7  lea     rdx, [rsp+58h+DestinationString]; ValueName
0x14004b2fc  mov     r8d, 1; KeyValueInformationClass
0x14004b302  mov     [rsp+58h+Length], 0F0h; Length
0x14004b30a  mov     rcx, rdi; KeyHandle
0x14004b30d  call    cs:__imp_ZwQueryValueKey
0x14004b314  nop     dword ptr [rax+rax+00h]
0x14004b319  test    eax, eax
0x14004b31b  jns     short loc_14004B364
0x14004b31d  mov     rcx, [rsp+58h+DestinationString.Buffer]; P
0x14004b322  mov     edx, 3033624Eh; Tag
0x14004b327  call    cs:__imp_ExFreePoolWithTag
0x14004b32e  nop     dword ptr [rax+rax+00h]
0x14004b333  mov     eax, esi
0x14004b335  mov     rbx, [rsp+58h+arg_0]
0x14004b33a  mov     rbp, [rsp+58h+arg_8]
0x14004b33f  add     rsp, 40h
0x14004b343  pop     r14
0x14004b345  pop     rdi
0x14004b346  pop     rsi
0x14004b347  retn
0x14004b349  cmp     cs:dword_1400385BC, 4
0x14004b350  jnz     short loc_14004B2D9
0x14004b352  mov     eax, cs:dword_1400385B8
0x14004b358  mov     eax, [rax+r14]
0x14004b35c  cmp     eax, ebp
0x14004b35e  jnb     short loc_14004B335
0x14004b360  mov     eax, ebp
0x14004b362  jmp     short loc_14004B335
0x14004b364  cmp     cs:dword_1400385BC, 4
0x14004b36b  jnz     short loc_14004B31D
0x14004b36d  mov     eax, cs:dword_1400385B8
0x14004b373  mov     esi, [rax+r14]
0x14004b377  cmp     esi, ebp
0x14004b379  cmovb   esi, ebp
0x14004b37c  jmp     short loc_14004B31D
```

# MupiReadRegistryValue

- ea: `0x140013c54`
- end: `0x140013d2f`
- name: `MupiReadRegistryValue`
- size: `219`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400138d4`
- `0x140013d38`

## callees

- `0x140013c54`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140013c77`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013c77`
- `ntoskrnl!ExAllocatePool2` at `0x140013cc6`
- `ntoskrnl!ExAllocatePool2` at `0x140013cc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013d12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013d12`
- `ntoskrnl!ZwQueryValueKey` at `0x140013ca0`
- `ntoskrnl!ZwQueryValueKey` at `0x140013cfd`
- `ntoskrnl!ZwQueryValueKey` at `0x140013ca0`
- `ntoskrnl!ZwQueryValueKey` at `0x140013cfd`

## pseudocode

```c
void *__fastcall MupiReadRegistryValue(HANDLE KeyHandle, const WCHAR *a2)
{
  void *Pool2; // rbx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+60h] [rbp+18h] BYREF

  ResultLength = 0;
  ValueName = 0;
  Pool2 = 0;
  RtlInitUnicodeString(&ValueName, a2);
  if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &ResultLength) == -1073741789 )
  {
    Pool2 = (void *)ExAllocatePool2(258, ResultLength + 2LL, 544240973);
    if ( Pool2 )
    {
      if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, Pool2, ResultLength, &ResultLength) < 0 )
      {
        ExFreePoolWithTag(Pool2, 0);
        return 0;
      }
    }
  }
  return Pool2;
}

```

## disassembly

```asm
0x140013c54  mov     rax, rsp
0x140013c57  mov     [rax+8], rbx
0x140013c5b  push    rdi
0x140013c5c  sub     rsp, 40h
0x140013c60  mov     rdi, rcx
0x140013c63  mov     dword ptr [rax+18h], 0
0x140013c6a  xorps   xmm0, xmm0
0x140013c6d  lea     rcx, [rax-18h]; DestinationString
0x140013c71  movups  xmmword ptr [rax-18h], xmm0
0x140013c75  xor     ebx, ebx
0x140013c77  call    cs:__imp_RtlInitUnicodeString
0x140013c7e  nop     dword ptr [rax+rax+00h]
0x140013c83  lea     rax, [rsp+48h+arg_10]
0x140013c88  xor     r9d, r9d; KeyValueInformation
0x140013c8b  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140013c90  lea     r8d, [rbx+1]; KeyValueInformationClass
0x140013c94  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140013c99  mov     [rsp+48h+Length], ebx; Length
0x140013c9d  mov     rcx, rdi; KeyHandle
0x140013ca0  call    cs:__imp_ZwQueryValueKey
0x140013ca7  nop     dword ptr [rax+rax+00h]
0x140013cac  cmp     eax, 0C0000023h
0x140013cb1  jnz     short loc_140013D20
0x140013cb3  mov     edx, [rsp+48h+arg_10]
0x140013cb7  mov     ecx, 102h
0x140013cbc  add     rdx, 2
0x140013cc0  mov     r8d, 2070754Dh
0x140013cc6  call    cs:__imp_ExAllocatePool2
0x140013ccd  nop     dword ptr [rax+rax+00h]
0x140013cd2  mov     rbx, rax
0x140013cd5  test    rax, rax
0x140013cd8  jz      short loc_140013D20
0x140013cda  mov     ecx, [rsp+48h+arg_10]
0x140013cde  lea     rax, [rsp+48h+arg_10]
0x140013ce3  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140013ce8  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140013ced  mov     [rsp+48h+Length], ecx; Length
0x140013cf1  mov     r9, rbx; KeyValueInformation
0x140013cf4  mov     rcx, rdi; KeyHandle
0x140013cf7  mov     r8d, 1; KeyValueInformationClass
0x140013cfd  call    cs:__imp_ZwQueryValueKey
0x140013d04  nop     dword ptr [rax+rax+00h]
0x140013d09  test    eax, eax
0x140013d0b  jns     short loc_140013D20
0x140013d0d  xor     edx, edx; Tag
0x140013d0f  mov     rcx, rbx; P
0x140013d12  call    cs:__imp_ExFreePoolWithTag
0x140013d19  nop     dword ptr [rax+rax+00h]
0x140013d1e  xor     ebx, ebx
0x140013d20  mov     rax, rbx
0x140013d23  mov     rbx, [rsp+48h+arg_0]
0x140013d28  add     rsp, 40h
0x140013d2c  pop     rdi
0x140013d2d  retn
```

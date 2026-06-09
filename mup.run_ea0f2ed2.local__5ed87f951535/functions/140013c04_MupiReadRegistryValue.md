# MupiReadRegistryValue

- ea: `0x140013c04`
- end: `0x140013cdf`
- name: `MupiReadRegistryValue`
- size: `219`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140013884`
- `0x140013ce8`

## callees

- `0x140013c04`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140013c27`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013c27`
- `ntoskrnl!ExAllocatePool2` at `0x140013c76`
- `ntoskrnl!ExAllocatePool2` at `0x140013c76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013cc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013cc2`
- `ntoskrnl!ZwQueryValueKey` at `0x140013c50`
- `ntoskrnl!ZwQueryValueKey` at `0x140013cad`
- `ntoskrnl!ZwQueryValueKey` at `0x140013c50`
- `ntoskrnl!ZwQueryValueKey` at `0x140013cad`

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
0x140013c04  mov     rax, rsp
0x140013c07  mov     [rax+8], rbx
0x140013c0b  push    rdi
0x140013c0c  sub     rsp, 40h
0x140013c10  mov     rdi, rcx
0x140013c13  mov     dword ptr [rax+18h], 0
0x140013c1a  xorps   xmm0, xmm0
0x140013c1d  lea     rcx, [rax-18h]; DestinationString
0x140013c21  movups  xmmword ptr [rax-18h], xmm0
0x140013c25  xor     ebx, ebx
0x140013c27  call    cs:__imp_RtlInitUnicodeString
0x140013c2e  nop     dword ptr [rax+rax+00h]
0x140013c33  lea     rax, [rsp+48h+arg_10]
0x140013c38  xor     r9d, r9d; KeyValueInformation
0x140013c3b  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140013c40  lea     r8d, [rbx+1]; KeyValueInformationClass
0x140013c44  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140013c49  mov     [rsp+48h+Length], ebx; Length
0x140013c4d  mov     rcx, rdi; KeyHandle
0x140013c50  call    cs:__imp_ZwQueryValueKey
0x140013c57  nop     dword ptr [rax+rax+00h]
0x140013c5c  cmp     eax, 0C0000023h
0x140013c61  jnz     short loc_140013CD0
0x140013c63  mov     edx, [rsp+48h+arg_10]
0x140013c67  mov     ecx, 102h
0x140013c6c  add     rdx, 2
0x140013c70  mov     r8d, 2070754Dh
0x140013c76  call    cs:__imp_ExAllocatePool2
0x140013c7d  nop     dword ptr [rax+rax+00h]
0x140013c82  mov     rbx, rax
0x140013c85  test    rax, rax
0x140013c88  jz      short loc_140013CD0
0x140013c8a  mov     ecx, [rsp+48h+arg_10]
0x140013c8e  lea     rax, [rsp+48h+arg_10]
0x140013c93  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140013c98  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140013c9d  mov     [rsp+48h+Length], ecx; Length
0x140013ca1  mov     r9, rbx; KeyValueInformation
0x140013ca4  mov     rcx, rdi; KeyHandle
0x140013ca7  mov     r8d, 1; KeyValueInformationClass
0x140013cad  call    cs:__imp_ZwQueryValueKey
0x140013cb4  nop     dword ptr [rax+rax+00h]
0x140013cb9  test    eax, eax
0x140013cbb  jns     short loc_140013CD0
0x140013cbd  xor     edx, edx; Tag
0x140013cbf  mov     rcx, rbx; P
0x140013cc2  call    cs:__imp_ExFreePoolWithTag
0x140013cc9  nop     dword ptr [rax+rax+00h]
0x140013cce  xor     ebx, ebx
0x140013cd0  mov     rax, rbx
0x140013cd3  mov     rbx, [rsp+48h+arg_0]
0x140013cd8  add     rsp, 40h
0x140013cdc  pop     rdi
0x140013cdd  retn
```

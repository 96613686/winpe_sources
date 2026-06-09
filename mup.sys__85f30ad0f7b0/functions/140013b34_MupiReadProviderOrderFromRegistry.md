# MupiReadProviderOrderFromRegistry

- ea: `0x140013b34`
- end: `0x140013c4b`
- name: `MupiReadProviderOrderFromRegistry`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140012560`
- `0x140013610`

## callees

- `0x1400056c0`
- `0x140013b34`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140013b59`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013b59`
- `ntoskrnl!ExAllocatePool2` at `0x140013bb7`
- `ntoskrnl!ExAllocatePool2` at `0x140013bb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013c2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013c2e`
- `ntoskrnl!ZwQueryValueKey` at `0x140013b8d`
- `ntoskrnl!ZwQueryValueKey` at `0x140013bef`
- `ntoskrnl!ZwQueryValueKey` at `0x140013b8d`
- `ntoskrnl!ZwQueryValueKey` at `0x140013bef`

## pseudocode

```c
_DWORD *MupiReadProviderOrderFromRegistry()
{
  _DWORD *Pool2; // rdi
  unsigned int v1; // eax
  unsigned __int64 v2; // rbx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+50h] [rbp+8h] BYREF

  ResultLength = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, L"ProviderOrder");
  if ( ZwQueryValueKey(MupiOrderKeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &ResultLength) != -1073741789 )
    return 0;
  Pool2 = (_DWORD *)ExAllocatePool2(258, ResultLength + 2LL, 544240973);
  if ( Pool2 )
  {
    if ( !ZwQueryValueKey(MupiOrderKeyHandle, &ValueName, KeyValueFullInformation, Pool2, ResultLength, &ResultLength)
      && Pool2[1] == 1 )
    {
      v1 = Pool2[3];
      if ( (v1 & 1) == 0 )
      {
        v2 = v1;
        memmove(Pool2, (char *)Pool2 + (unsigned int)Pool2[2], v1);
        *((_WORD *)Pool2 + (v2 >> 1)) = 0;
        return Pool2;
      }
    }
    ExFreePoolWithTag(Pool2, 0);
    return 0;
  }
  return Pool2;
}

```

## disassembly

```asm
0x140013b34  mov     rax, rsp
0x140013b37  mov     [rax+10h], rbx
0x140013b3b  push    rdi
0x140013b3c  sub     rsp, 40h
0x140013b40  xorps   xmm0, xmm0
0x140013b43  mov     dword ptr [rax+8], 0
0x140013b4a  lea     rdx, aProviderorder; "ProviderOrder"
0x140013b51  lea     rcx, [rax-18h]; DestinationString
0x140013b55  movups  xmmword ptr [rax-18h], xmm0
0x140013b59  call    cs:__imp_RtlInitUnicodeString
0x140013b60  nop     dword ptr [rax+rax+00h]
0x140013b65  mov     rcx, cs:MupiOrderKeyHandle; KeyHandle
0x140013b6c  lea     rax, [rsp+48h+arg_0]
0x140013b71  xor     r9d, r9d; KeyValueInformation
0x140013b74  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140013b79  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140013b7e  mov     [rsp+48h+Length], 0; Length
0x140013b86  lea     ebx, [r9+1]
0x140013b8a  mov     r8d, ebx; KeyValueInformationClass
0x140013b8d  call    cs:__imp_ZwQueryValueKey
0x140013b94  nop     dword ptr [rax+rax+00h]
0x140013b99  cmp     eax, 0C0000023h
0x140013b9e  jnz     loc_140013C3A
0x140013ba4  mov     edx, [rsp+48h+arg_0]
0x140013ba8  mov     ecx, 102h
0x140013bad  add     rdx, 2
0x140013bb1  mov     r8d, 2070754Dh
0x140013bb7  call    cs:__imp_ExAllocatePool2
0x140013bbe  nop     dword ptr [rax+rax+00h]
0x140013bc3  mov     rdi, rax
0x140013bc6  test    rax, rax
0x140013bc9  jz      short loc_140013C3C
0x140013bcb  mov     ecx, [rsp+48h+arg_0]
0x140013bcf  lea     rax, [rsp+48h+arg_0]
0x140013bd4  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140013bd9  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140013bde  mov     [rsp+48h+Length], ecx; Length
0x140013be2  mov     r9, rdi; KeyValueInformation
0x140013be5  mov     rcx, cs:MupiOrderKeyHandle; KeyHandle
0x140013bec  mov     r8d, ebx; KeyValueInformationClass
0x140013bef  call    cs:__imp_ZwQueryValueKey
0x140013bf6  nop     dword ptr [rax+rax+00h]
0x140013bfb  test    eax, eax
0x140013bfd  jnz     short loc_140013C29
0x140013bff  cmp     [rdi+4], ebx
0x140013c02  jnz     short loc_140013C29
0x140013c04  mov     eax, [rdi+0Ch]
0x140013c07  test    bl, al
0x140013c09  jnz     short loc_140013C29
0x140013c0b  mov     edx, [rdi+8]
0x140013c0e  mov     r8d, eax; Size
0x140013c11  add     rdx, rdi; Src
0x140013c14  mov     rcx, rdi; void *
0x140013c17  mov     ebx, eax
0x140013c19  call    memmove
0x140013c1e  shr     rbx, 1
0x140013c21  xor     eax, eax
0x140013c23  mov     [rdi+rbx*2], ax
0x140013c27  jmp     short loc_140013C3C
0x140013c29  xor     edx, edx; Tag
0x140013c2b  mov     rcx, rdi; P
0x140013c2e  call    cs:__imp_ExFreePoolWithTag
0x140013c35  nop     dword ptr [rax+rax+00h]
0x140013c3a  xor     edi, edi
0x140013c3c  mov     rbx, [rsp+48h+arg_8]
0x140013c41  mov     rax, rdi
0x140013c44  add     rsp, 40h
0x140013c48  pop     rdi
0x140013c49  retn
```

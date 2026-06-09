# MupiReadProviderOrderFromRegistry

- ea: `0x140013ae4`
- end: `0x140013bfb`
- name: `MupiReadProviderOrderFromRegistry`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140012510`
- `0x1400135c0`

## callees

- `0x1400056c0`
- `0x140013ae4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140013b09`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013b09`
- `ntoskrnl!ExAllocatePool2` at `0x140013b67`
- `ntoskrnl!ExAllocatePool2` at `0x140013b67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013bde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013bde`
- `ntoskrnl!ZwQueryValueKey` at `0x140013b3d`
- `ntoskrnl!ZwQueryValueKey` at `0x140013b9f`
- `ntoskrnl!ZwQueryValueKey` at `0x140013b3d`
- `ntoskrnl!ZwQueryValueKey` at `0x140013b9f`

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
0x140013ae4  mov     rax, rsp
0x140013ae7  mov     [rax+10h], rbx
0x140013aeb  push    rdi
0x140013aec  sub     rsp, 40h
0x140013af0  xorps   xmm0, xmm0
0x140013af3  mov     dword ptr [rax+8], 0
0x140013afa  lea     rdx, aProviderorder; "ProviderOrder"
0x140013b01  lea     rcx, [rax-18h]; DestinationString
0x140013b05  movups  xmmword ptr [rax-18h], xmm0
0x140013b09  call    cs:__imp_RtlInitUnicodeString
0x140013b10  nop     dword ptr [rax+rax+00h]
0x140013b15  mov     rcx, cs:MupiOrderKeyHandle; KeyHandle
0x140013b1c  lea     rax, [rsp+48h+arg_0]
0x140013b21  xor     r9d, r9d; KeyValueInformation
0x140013b24  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140013b29  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140013b2e  mov     [rsp+48h+Length], 0; Length
0x140013b36  lea     ebx, [r9+1]
0x140013b3a  mov     r8d, ebx; KeyValueInformationClass
0x140013b3d  call    cs:__imp_ZwQueryValueKey
0x140013b44  nop     dword ptr [rax+rax+00h]
0x140013b49  cmp     eax, 0C0000023h
0x140013b4e  jnz     loc_140013BEA
0x140013b54  mov     edx, [rsp+48h+arg_0]
0x140013b58  mov     ecx, 102h
0x140013b5d  add     rdx, 2
0x140013b61  mov     r8d, 2070754Dh
0x140013b67  call    cs:__imp_ExAllocatePool2
0x140013b6e  nop     dword ptr [rax+rax+00h]
0x140013b73  mov     rdi, rax
0x140013b76  test    rax, rax
0x140013b79  jz      short loc_140013BEC
0x140013b7b  mov     ecx, [rsp+48h+arg_0]
0x140013b7f  lea     rax, [rsp+48h+arg_0]
0x140013b84  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140013b89  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140013b8e  mov     [rsp+48h+Length], ecx; Length
0x140013b92  mov     r9, rdi; KeyValueInformation
0x140013b95  mov     rcx, cs:MupiOrderKeyHandle; KeyHandle
0x140013b9c  mov     r8d, ebx; KeyValueInformationClass
0x140013b9f  call    cs:__imp_ZwQueryValueKey
0x140013ba6  nop     dword ptr [rax+rax+00h]
0x140013bab  test    eax, eax
0x140013bad  jnz     short loc_140013BD9
0x140013baf  cmp     [rdi+4], ebx
0x140013bb2  jnz     short loc_140013BD9
0x140013bb4  mov     eax, [rdi+0Ch]
0x140013bb7  test    bl, al
0x140013bb9  jnz     short loc_140013BD9
0x140013bbb  mov     edx, [rdi+8]
0x140013bbe  mov     r8d, eax; Size
0x140013bc1  add     rdx, rdi; Src
0x140013bc4  mov     rcx, rdi; void *
0x140013bc7  mov     ebx, eax
0x140013bc9  call    memmove
0x140013bce  shr     rbx, 1
0x140013bd1  xor     eax, eax
0x140013bd3  mov     [rdi+rbx*2], ax
0x140013bd7  jmp     short loc_140013BEC
0x140013bd9  xor     edx, edx; Tag
0x140013bdb  mov     rcx, rdi; P
0x140013bde  call    cs:__imp_ExFreePoolWithTag
0x140013be5  nop     dword ptr [rax+rax+00h]
0x140013bea  xor     edi, edi
0x140013bec  mov     rbx, [rsp+48h+arg_8]
0x140013bf1  mov     rax, rdi
0x140013bf4  add     rsp, 40h
0x140013bf8  pop     rdi
0x140013bf9  retn
```

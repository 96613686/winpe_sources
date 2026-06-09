# StSecpReadSealedKeyBlob

- ea: `0x14000e104`
- end: `0x14000e279`
- name: `StSecpReadSealedKeyBlob`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000eb20`

## callees

- `0x140003b80`
- `0x14000df34`
- `0x14000e104`
- `0x1400122e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000e156`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e156`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e184`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e1ee`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e184`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e1ee`
- `ntoskrnl!ExAllocatePool2` at `0x14000e1b5`
- `ntoskrnl!ExAllocatePool2` at `0x14000e20f`
- `ntoskrnl!ExAllocatePool2` at `0x14000e1b5`
- `ntoskrnl!ExAllocatePool2` at `0x14000e20f`
- `ntoskrnl!ZwClose` at `0x14000e245`
- `ntoskrnl!ZwClose` at `0x14000e245`

## pseudocode

```c
__int64 __fastcall StSecpReadSealedKeyBlob(_QWORD *a1, unsigned int *a2)
{
  _DWORD *Pool2; // rdi
  int v5; // ebx
  NTSTATUS v6; // eax
  unsigned int v7; // r14d
  void *v8; // rax
  void *v9; // r15
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  ULONG Length; // [rsp+80h] [rbp+40h] BYREF
  HANDLE KeyHandle; // [rsp+88h] [rbp+48h] BYREF

  KeyHandle = 0;
  Pool2 = 0;
  DestinationString = 0;
  Length = 0;
  v5 = StSecpOpenMasterKeyHandle(&KeyHandle);
  if ( v5 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"MK");
    v6 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, 0, Length, &Length);
    v5 = v6;
    if ( v6 == -2147483643 || v6 == -1073741789 )
    {
      Pool2 = (_DWORD *)ExAllocatePool2(256, Length, 1884517459);
      if ( !Pool2 )
      {
LABEL_5:
        v5 = -1073741801;
        goto LABEL_9;
      }
      v5 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Pool2, Length, &Length);
      if ( v5 >= 0 )
      {
        v7 = Pool2[2];
        v8 = (void *)ExAllocatePool2(256, v7, 1884517459);
        v9 = v8;
        if ( !v8 )
          goto LABEL_5;
        memmove(v8, Pool2 + 3, v7);
        *a1 = v9;
        *a2 = v7;
      }
    }
  }
LABEL_9:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Pool2 )
    StSecFree(Pool2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000e104  mov     [rsp-28h+arg_0], rbx
0x14000e109  mov     [rsp-28h+arg_8], rdi
0x14000e10e  push    rbp
0x14000e10f  push    r12
0x14000e111  push    r13
0x14000e113  push    r14
0x14000e115  push    r15
0x14000e117  mov     rbp, rsp
0x14000e11a  sub     rsp, 40h
0x14000e11e  mov     r13, rcx
0x14000e121  mov     [rbp+KeyHandle], 0
0x14000e129  xorps   xmm0, xmm0
0x14000e12c  lea     rcx, [rbp+KeyHandle]
0x14000e130  xor     edi, edi
0x14000e132  mov     r12, rdx
0x14000e135  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e139  mov     [rbp+arg_10], edi
0x14000e13c  call    StSecpOpenMasterKeyHandle
0x14000e141  mov     ebx, eax
0x14000e143  test    eax, eax
0x14000e145  js      loc_14000E23A
0x14000e14b  lea     rdx, aMk; "MK"
0x14000e152  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e156  call    cs:__imp_RtlInitUnicodeString
0x14000e15d  nop     dword ptr [rax+rax+00h]
0x14000e162  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e166  lea     rax, [rbp+arg_10]
0x14000e16a  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14000e16f  lea     r14d, [rdi+2]
0x14000e173  mov     eax, [rbp+arg_10]
0x14000e176  lea     rdx, [rbp+DestinationString]; ValueName
0x14000e17a  xor     r9d, r9d; KeyValueInformation
0x14000e17d  mov     [rsp+40h+Length], eax; Length
0x14000e181  mov     r8d, r14d; KeyValueInformationClass
0x14000e184  call    cs:__imp_ZwQueryValueKey
0x14000e18b  nop     dword ptr [rax+rax+00h]
0x14000e190  mov     ebx, eax
0x14000e192  cmp     eax, 80000005h
0x14000e197  jz      short loc_14000E1A4
0x14000e199  cmp     eax, 0C0000023h
0x14000e19e  jnz     loc_14000E23A
0x14000e1a4  mov     edx, [rbp+arg_10]
0x14000e1a7  mov     r15d, 70537453h
0x14000e1ad  mov     r8d, r15d
0x14000e1b0  mov     ecx, 100h
0x14000e1b5  call    cs:__imp_ExAllocatePool2
0x14000e1bc  nop     dword ptr [rax+rax+00h]
0x14000e1c1  mov     rdi, rax
0x14000e1c4  test    rax, rax
0x14000e1c7  jnz     short loc_14000E1D0
0x14000e1c9  mov     ebx, 0C0000017h
0x14000e1ce  jmp     short loc_14000E23A
0x14000e1d0  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e1d4  lea     rax, [rbp+arg_10]
0x14000e1d8  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14000e1dd  lea     rdx, [rbp+DestinationString]; ValueName
0x14000e1e1  mov     eax, [rbp+arg_10]
0x14000e1e4  mov     r9, rdi; KeyValueInformation
0x14000e1e7  mov     r8d, r14d; KeyValueInformationClass
0x14000e1ea  mov     [rsp+40h+Length], eax; Length
0x14000e1ee  call    cs:__imp_ZwQueryValueKey
0x14000e1f5  nop     dword ptr [rax+rax+00h]
0x14000e1fa  mov     ebx, eax
0x14000e1fc  test    eax, eax
0x14000e1fe  js      short loc_14000E23A
0x14000e200  mov     r14d, [rdi+8]
0x14000e204  mov     r8d, r15d
0x14000e207  mov     edx, r14d
0x14000e20a  mov     ecx, 100h
0x14000e20f  call    cs:__imp_ExAllocatePool2
0x14000e216  nop     dword ptr [rax+rax+00h]
0x14000e21b  mov     r15, rax
0x14000e21e  test    rax, rax
0x14000e221  jz      short loc_14000E1C9
0x14000e223  lea     rdx, [rdi+0Ch]; Src
0x14000e227  mov     r8d, r14d; Size
0x14000e22a  mov     rcx, rax; void *
0x14000e22d  call    memmove
0x14000e232  mov     [r13+0], r15
0x14000e236  mov     [r12], r14d
0x14000e23a  cmp     [rbp+KeyHandle], 0
0x14000e23f  jz      short loc_14000E251
0x14000e241  mov     rcx, [rbp+KeyHandle]; Handle
0x14000e245  call    cs:__imp_ZwClose
0x14000e24c  nop     dword ptr [rax+rax+00h]
0x14000e251  test    rdi, rdi
0x14000e254  jz      short loc_14000E25E
0x14000e256  mov     rcx, rdi
0x14000e259  call    StSecFree
0x14000e25e  mov     rdi, [rsp+40h+arg_8]
0x14000e263  mov     eax, ebx
0x14000e265  mov     rbx, [rsp+40h+arg_0]
0x14000e26a  add     rsp, 40h
0x14000e26e  pop     r15
0x14000e270  pop     r14
0x14000e272  pop     r13
0x14000e274  pop     r12
0x14000e276  pop     rbp
0x14000e277  retn
```

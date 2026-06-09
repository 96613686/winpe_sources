# StSecpWriteSealedKeyBlob

- ea: `0x14000e280`
- end: `0x14000e338`
- name: `StSecpWriteSealedKeyBlob`
- size: `184`
- prototype: `__int64 __fastcall(PVOID Data, ULONG DataSize)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000eb20`

## callees

- `0x14000df34`
- `0x14000e280`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000e2bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e2bf`
- `ntoskrnl!ZwSetValueKey` at `0x14000e2e7`
- `ntoskrnl!ZwSetValueKey` at `0x14000e2e7`
- `ntoskrnl!ZwFlushKey` at `0x14000e2fe`
- `ntoskrnl!ZwFlushKey` at `0x14000e2fe`
- `ntoskrnl!ZwClose` at `0x14000e319`
- `ntoskrnl!ZwClose` at `0x14000e319`

## pseudocode

```c
__int64 __fastcall StSecpWriteSealedKeyBlob(PVOID Data, ULONG DataSize)
{
  int v4; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+60h] [rbp+18h] BYREF

  KeyHandle = 0;
  DestinationString = 0;
  v4 = StSecpOpenMasterKeyHandle(&KeyHandle);
  if ( v4 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"MK");
    v4 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, Data, DataSize);
    if ( v4 >= 0 )
      v4 = ZwFlushKey(KeyHandle);
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000e280  mov     rax, rsp
0x14000e283  mov     [rax+8], rbp
0x14000e287  mov     [rax+10h], rsi
0x14000e28b  push    rdi
0x14000e28c  sub     rsp, 40h
0x14000e290  mov     rbp, rcx
0x14000e293  mov     qword ptr [rax+18h], 0
0x14000e29b  xorps   xmm0, xmm0
0x14000e29e  lea     rcx, [rax+18h]
0x14000e2a2  movups  xmmword ptr [rax-18h], xmm0
0x14000e2a6  mov     esi, edx
0x14000e2a8  call    StSecpOpenMasterKeyHandle
0x14000e2ad  mov     edi, eax
0x14000e2af  test    eax, eax
0x14000e2b1  js      short loc_14000E30C
0x14000e2b3  lea     rdx, aMk; "MK"
0x14000e2ba  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14000e2bf  call    cs:__imp_RtlInitUnicodeString
0x14000e2c6  nop     dword ptr [rax+rax+00h]
0x14000e2cb  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14000e2d0  lea     rdx, [rsp+48h+DestinationString]; ValueName
0x14000e2d5  mov     r9d, 3; Type
0x14000e2db  mov     [rsp+48h+DataSize], esi; DataSize
0x14000e2df  xor     r8d, r8d; TitleIndex
0x14000e2e2  mov     [rsp+48h+Data], rbp; Data
0x14000e2e7  call    cs:__imp_ZwSetValueKey
0x14000e2ee  nop     dword ptr [rax+rax+00h]
0x14000e2f3  mov     edi, eax
0x14000e2f5  test    eax, eax
0x14000e2f7  js      short loc_14000E30C
0x14000e2f9  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14000e2fe  call    cs:__imp_ZwFlushKey
0x14000e305  nop     dword ptr [rax+rax+00h]
0x14000e30a  mov     edi, eax
0x14000e30c  cmp     [rsp+48h+KeyHandle], 0
0x14000e312  jz      short loc_14000E325
0x14000e314  mov     rcx, [rsp+48h+KeyHandle]; Handle
0x14000e319  call    cs:__imp_ZwClose
0x14000e320  nop     dword ptr [rax+rax+00h]
0x14000e325  mov     rbp, [rsp+48h+arg_0]
0x14000e32a  mov     eax, edi
0x14000e32c  mov     rsi, [rsp+48h+arg_8]
0x14000e331  add     rsp, 40h
0x14000e335  pop     rdi
0x14000e336  retn
```

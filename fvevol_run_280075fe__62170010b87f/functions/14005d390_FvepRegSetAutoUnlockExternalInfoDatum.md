# FvepRegSetAutoUnlockExternalInfoDatum

- ea: `0x14005d390`
- end: `0x14005d477`
- name: `FvepRegSetAutoUnlockExternalInfoDatum`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14005c52c`

## callees

- `0x14005d274`
- `0x14005d390`
- `0x140094a08`

## import_xrefs

- `ntoskrnl!ZwFlushKey` at `0x14005d41c`
- `ntoskrnl!ZwFlushKey` at `0x14005d41c`
- `ntoskrnl!ZwDeleteKey` at `0x14005d447`
- `ntoskrnl!ZwDeleteKey` at `0x14005d447`
- `ntoskrnl!ZwClose` at `0x14005d45d`
- `ntoskrnl!ZwClose` at `0x14005d45d`
- `ntoskrnl!ZwSetValueKey` at `0x14005d405`
- `ntoskrnl!ZwSetValueKey` at `0x14005d405`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d3bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d3bc`

## pseudocode

```c
__int64 __fastcall FvepRegSetAutoUnlockExternalInfoDatum(const GUID *a1, unsigned __int16 *a2)
{
  int v4; // ebx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+60h] [rbp+18h] BYREF

  KeyHandle = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, L"Data");
  v4 = FvepRegOpenKey(a1, 0x30006u, 2, &KeyHandle);
  if ( v4 < 0
    || (v4 = ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, a2, *a2), v4 < 0)
    || (v4 = ZwFlushKey(KeyHandle), v4 < 0) )
  {
    if ( !KeyHandle )
      return (unsigned int)v4;
    FvepRegSecureOverwriteValueKey(KeyHandle, &ValueName);
    ZwDeleteKey(KeyHandle);
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14005d390  mov     rax, rsp
0x14005d393  mov     [rax+8], rbx
0x14005d397  push    rdi
0x14005d398  sub     rsp, 40h
0x14005d39c  mov     rdi, rdx
0x14005d39f  mov     qword ptr [rax+18h], 0
0x14005d3a7  mov     rbx, rcx
0x14005d3aa  lea     rdx, aData_0; "Data"
0x14005d3b1  xorps   xmm0, xmm0
0x14005d3b4  lea     rcx, [rax-18h]; DestinationString
0x14005d3b8  movups  xmmword ptr [rax-18h], xmm0
0x14005d3bc  call    cs:__imp_RtlInitUnicodeString
0x14005d3c3  nop     dword ptr [rax+rax+00h]
0x14005d3c8  lea     r9, [rsp+48h+KeyHandle]
0x14005d3cd  mov     edx, 30006h
0x14005d3d2  mov     r8d, 2
0x14005d3d8  mov     rcx, rbx
0x14005d3db  call    FvepRegOpenKey
0x14005d3e0  mov     ebx, eax
0x14005d3e2  test    eax, eax
0x14005d3e4  js      short loc_14005D42E
0x14005d3e6  movzx   eax, word ptr [rdi]
0x14005d3e9  lea     rdx, [rsp+48h+ValueName]; ValueName
0x14005d3ee  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14005d3f3  mov     r9d, 3; Type
0x14005d3f9  mov     [rsp+48h+DataSize], eax; DataSize
0x14005d3fd  xor     r8d, r8d; TitleIndex
0x14005d400  mov     [rsp+48h+Data], rdi; Data
0x14005d405  call    cs:__imp_ZwSetValueKey
0x14005d40c  nop     dword ptr [rax+rax+00h]
0x14005d411  mov     ebx, eax
0x14005d413  test    eax, eax
0x14005d415  js      short loc_14005D42E
0x14005d417  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14005d41c  call    cs:__imp_ZwFlushKey
0x14005d423  nop     dword ptr [rax+rax+00h]
0x14005d428  mov     ebx, eax
0x14005d42a  test    eax, eax
0x14005d42c  jns     short loc_14005D453
0x14005d42e  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14005d433  test    rcx, rcx
0x14005d436  jz      short loc_14005D469
0x14005d438  lea     rdx, [rsp+48h+ValueName]; ValueName
0x14005d43d  call    FvepRegSecureOverwriteValueKey
0x14005d442  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14005d447  call    cs:__imp_ZwDeleteKey
0x14005d44e  nop     dword ptr [rax+rax+00h]
0x14005d453  mov     rcx, [rsp+48h+KeyHandle]; Handle
0x14005d458  test    rcx, rcx
0x14005d45b  jz      short loc_14005D469
0x14005d45d  call    cs:__imp_ZwClose
0x14005d464  nop     dword ptr [rax+rax+00h]
0x14005d469  mov     eax, ebx
0x14005d46b  mov     rbx, [rsp+48h+arg_0]
0x14005d470  add     rsp, 40h
0x14005d474  pop     rdi
0x14005d475  retn
```

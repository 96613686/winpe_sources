# FvepRegSetAutoUnlockExternalInfoDatum

- ea: `0x14005f410`
- end: `0x14005f4f7`
- name: `FvepRegSetAutoUnlockExternalInfoDatum`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14005e5ac`

## callees

- `0x14005f2f4`
- `0x14005f410`
- `0x140096ab8`

## import_xrefs

- `ntoskrnl!ZwFlushKey` at `0x14005f49c`
- `ntoskrnl!ZwFlushKey` at `0x14005f49c`
- `ntoskrnl!ZwDeleteKey` at `0x14005f4c7`
- `ntoskrnl!ZwDeleteKey` at `0x14005f4c7`
- `ntoskrnl!ZwClose` at `0x14005f4dd`
- `ntoskrnl!ZwClose` at `0x14005f4dd`
- `ntoskrnl!ZwSetValueKey` at `0x14005f485`
- `ntoskrnl!ZwSetValueKey` at `0x14005f485`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f43c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f43c`

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
0x14005f410  mov     rax, rsp
0x14005f413  mov     [rax+8], rbx
0x14005f417  push    rdi
0x14005f418  sub     rsp, 40h
0x14005f41c  mov     rdi, rdx
0x14005f41f  mov     qword ptr [rax+18h], 0
0x14005f427  mov     rbx, rcx
0x14005f42a  lea     rdx, aData_0; "Data"
0x14005f431  xorps   xmm0, xmm0
0x14005f434  lea     rcx, [rax-18h]; DestinationString
0x14005f438  movups  xmmword ptr [rax-18h], xmm0
0x14005f43c  call    cs:__imp_RtlInitUnicodeString
0x14005f443  nop     dword ptr [rax+rax+00h]
0x14005f448  lea     r9, [rsp+48h+KeyHandle]
0x14005f44d  mov     edx, 30006h
0x14005f452  mov     r8d, 2
0x14005f458  mov     rcx, rbx
0x14005f45b  call    FvepRegOpenKey
0x14005f460  mov     ebx, eax
0x14005f462  test    eax, eax
0x14005f464  js      short loc_14005F4AE
0x14005f466  movzx   eax, word ptr [rdi]
0x14005f469  lea     rdx, [rsp+48h+ValueName]; ValueName
0x14005f46e  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14005f473  mov     r9d, 3; Type
0x14005f479  mov     [rsp+48h+DataSize], eax; DataSize
0x14005f47d  xor     r8d, r8d; TitleIndex
0x14005f480  mov     [rsp+48h+Data], rdi; Data
0x14005f485  call    cs:__imp_ZwSetValueKey
0x14005f48c  nop     dword ptr [rax+rax+00h]
0x14005f491  mov     ebx, eax
0x14005f493  test    eax, eax
0x14005f495  js      short loc_14005F4AE
0x14005f497  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14005f49c  call    cs:__imp_ZwFlushKey
0x14005f4a3  nop     dword ptr [rax+rax+00h]
0x14005f4a8  mov     ebx, eax
0x14005f4aa  test    eax, eax
0x14005f4ac  jns     short loc_14005F4D3
0x14005f4ae  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14005f4b3  test    rcx, rcx
0x14005f4b6  jz      short loc_14005F4E9
0x14005f4b8  lea     rdx, [rsp+48h+ValueName]; ValueName
0x14005f4bd  call    FvepRegSecureOverwriteValueKey
0x14005f4c2  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14005f4c7  call    cs:__imp_ZwDeleteKey
0x14005f4ce  nop     dword ptr [rax+rax+00h]
0x14005f4d3  mov     rcx, [rsp+48h+KeyHandle]; Handle
0x14005f4d8  test    rcx, rcx
0x14005f4db  jz      short loc_14005F4E9
0x14005f4dd  call    cs:__imp_ZwClose
0x14005f4e4  nop     dword ptr [rax+rax+00h]
0x14005f4e9  mov     eax, ebx
0x14005f4eb  mov     rbx, [rsp+48h+arg_0]
0x14005f4f0  add     rsp, 40h
0x14005f4f4  pop     rdi
0x14005f4f5  retn
```

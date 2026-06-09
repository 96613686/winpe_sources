# FveSetRegistryValue

- ea: `0x140065ac0`
- end: `0x140065c1c`
- name: `FveSetRegistryValue`
- size: `348`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140065954`
- `0x140065c24`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x1400651c0`
- `0x140065ac0`

## import_xrefs

- `ntoskrnl!ZwFlushKey` at `0x140065b93`
- `ntoskrnl!ZwFlushKey` at `0x140065b93`
- `ntoskrnl!ZwDeleteValueKey` at `0x140065ba3`
- `ntoskrnl!ZwDeleteValueKey` at `0x140065ba3`
- `ntoskrnl!ZwClose` at `0x140065bc6`
- `ntoskrnl!ZwClose` at `0x140065bc6`
- `ntoskrnl!ZwSetValueKey` at `0x140065b72`
- `ntoskrnl!ZwSetValueKey` at `0x140065b72`

## pseudocode

```c
__int64 __fastcall FveSetRegistryValue(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        ULONG a3,
        char a4,
        PVOID Data,
        ULONG DataSize,
        char a7)
{
  int v11; // ebx
  HANDLE KeyHandle; // [rsp+30h] [rbp-48h] BYREF

  KeyHandle = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
  }
  KeyHandle = 0;
  if ( a4 || Data )
  {
    v11 = FveRegOpenCreateKey(a1, (__int64)a2, &KeyHandle);
    if ( v11 >= 0 )
    {
      if ( a4 )
      {
        v11 = ZwDeleteValueKey(KeyHandle, a2);
        if ( v11 == -1073741772 )
          v11 = 0;
      }
      else
      {
        v11 = ZwSetValueKey(KeyHandle, a2, 0, a3, Data, DataSize);
        if ( v11 >= 0 && a7 )
          v11 = ZwFlushKey(KeyHandle);
      }
    }
    if ( KeyHandle )
    {
      ZwClose(KeyHandle);
      KeyHandle = 0;
    }
  }
  else
  {
    v11 = -1073741811;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids, (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140065ac0  push    rbx
0x140065ac2  push    rbp
0x140065ac3  push    rsi
0x140065ac4  push    rdi
0x140065ac5  push    r12
0x140065ac7  push    r14
0x140065ac9  sub     rsp, 48h
0x140065acd  mov     sil, r9b
0x140065ad0  mov     [rsp+78h+KeyHandle], 0
0x140065ad9  mov     r14d, r8d
0x140065adc  mov     rbp, rdx
0x140065adf  mov     rbx, rcx
0x140065ae2  mov     rcx, cs:WPP_GLOBAL_Control
0x140065ae9  lea     r12, WPP_GLOBAL_Control
0x140065af0  cmp     rcx, r12
0x140065af3  jz      short loc_140065B17
0x140065af5  mov     eax, [rcx+2Ch]
0x140065af8  test    al, 8
0x140065afa  jz      short loc_140065B17
0x140065afc  cmp     byte ptr [rcx+29h], 5
0x140065b00  jb      short loc_140065B17
0x140065b02  mov     rcx, [rcx+18h]
0x140065b06  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140065b0d  mov     edx, 3Bh ; ';'
0x140065b12  call    WPP_SF_
0x140065b17  mov     rdi, [rsp+78h+arg_20]
0x140065b1f  mov     [rsp+78h+KeyHandle], 0
0x140065b28  test    sil, sil
0x140065b2b  jnz     short loc_140065B3C
0x140065b2d  test    rdi, rdi
0x140065b30  jnz     short loc_140065B3C
0x140065b32  mov     ebx, 0C000000Dh
0x140065b37  jmp     loc_140065BDB
0x140065b3c  lea     r8, [rsp+78h+KeyHandle]
0x140065b41  mov     rcx, rbx
0x140065b44  call    FveRegOpenCreateKey
0x140065b49  mov     ebx, eax
0x140065b4b  test    eax, eax
0x140065b4d  js      short loc_140065BBC
0x140065b4f  mov     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x140065b54  mov     rdx, rbp; ValueName
0x140065b57  test    sil, sil
0x140065b5a  jnz     short loc_140065BA3
0x140065b5c  mov     eax, [rsp+78h+arg_28]
0x140065b63  mov     r9d, r14d; Type
0x140065b66  mov     [rsp+78h+DataSize], eax; DataSize
0x140065b6a  xor     r8d, r8d; TitleIndex
0x140065b6d  mov     [rsp+78h+Data], rdi; Data
0x140065b72  call    cs:__imp_ZwSetValueKey
0x140065b79  nop     dword ptr [rax+rax+00h]
0x140065b7e  mov     ebx, eax
0x140065b80  test    eax, eax
0x140065b82  js      short loc_140065BBC
0x140065b84  cmp     [rsp+78h+arg_30], sil
0x140065b8c  jz      short loc_140065BBC
0x140065b8e  mov     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x140065b93  call    cs:__imp_ZwFlushKey
0x140065b9a  nop     dword ptr [rax+rax+00h]
0x140065b9f  mov     ebx, eax
0x140065ba1  jmp     short loc_140065BBC
0x140065ba3  call    cs:__imp_ZwDeleteValueKey
0x140065baa  nop     dword ptr [rax+rax+00h]
0x140065baf  mov     ebx, eax
0x140065bb1  xor     eax, eax
0x140065bb3  cmp     ebx, 0C0000034h
0x140065bb9  cmovz   ebx, eax
0x140065bbc  mov     rcx, [rsp+78h+KeyHandle]; Handle
0x140065bc1  test    rcx, rcx
0x140065bc4  jz      short loc_140065BDB
0x140065bc6  call    cs:__imp_ZwClose
0x140065bcd  nop     dword ptr [rax+rax+00h]
0x140065bd2  mov     [rsp+78h+KeyHandle], 0
0x140065bdb  mov     rcx, cs:WPP_GLOBAL_Control
0x140065be2  cmp     rcx, r12
0x140065be5  jz      short loc_140065C0C
0x140065be7  mov     eax, [rcx+2Ch]
0x140065bea  test    al, 8
0x140065bec  jz      short loc_140065C0C
0x140065bee  cmp     byte ptr [rcx+29h], 5
0x140065bf2  jb      short loc_140065C0C
0x140065bf4  mov     rcx, [rcx+18h]
0x140065bf8  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140065bff  mov     edx, 3Ch ; '<'
0x140065c04  mov     r9d, ebx
0x140065c07  call    WPP_SF_d
0x140065c0c  mov     eax, ebx
0x140065c0e  add     rsp, 48h
0x140065c12  pop     r14
0x140065c14  pop     r12
0x140065c16  pop     rdi
0x140065c17  pop     rsi
0x140065c18  pop     rbp
0x140065c19  pop     rbx
0x140065c1a  retn
```

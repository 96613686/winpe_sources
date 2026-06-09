# FveSetRegistryValue

- ea: `0x140063a40`
- end: `0x140063b9c`
- name: `FveSetRegistryValue`
- size: `348`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400638d4`
- `0x140063ba4`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140063140`
- `0x140063a40`

## import_xrefs

- `ntoskrnl!ZwFlushKey` at `0x140063b13`
- `ntoskrnl!ZwFlushKey` at `0x140063b13`
- `ntoskrnl!ZwDeleteValueKey` at `0x140063b23`
- `ntoskrnl!ZwDeleteValueKey` at `0x140063b23`
- `ntoskrnl!ZwClose` at `0x140063b46`
- `ntoskrnl!ZwClose` at `0x140063b46`
- `ntoskrnl!ZwSetValueKey` at `0x140063af2`
- `ntoskrnl!ZwSetValueKey` at `0x140063af2`

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
0x140063a40  push    rbx
0x140063a42  push    rbp
0x140063a43  push    rsi
0x140063a44  push    rdi
0x140063a45  push    r12
0x140063a47  push    r14
0x140063a49  sub     rsp, 48h
0x140063a4d  mov     sil, r9b
0x140063a50  mov     [rsp+78h+KeyHandle], 0
0x140063a59  mov     r14d, r8d
0x140063a5c  mov     rbp, rdx
0x140063a5f  mov     rbx, rcx
0x140063a62  mov     rcx, cs:WPP_GLOBAL_Control
0x140063a69  lea     r12, WPP_GLOBAL_Control
0x140063a70  cmp     rcx, r12
0x140063a73  jz      short loc_140063A97
0x140063a75  mov     eax, [rcx+2Ch]
0x140063a78  test    al, 8
0x140063a7a  jz      short loc_140063A97
0x140063a7c  cmp     byte ptr [rcx+29h], 5
0x140063a80  jb      short loc_140063A97
0x140063a82  mov     rcx, [rcx+18h]
0x140063a86  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140063a8d  mov     edx, 3Bh ; ';'
0x140063a92  call    WPP_SF_
0x140063a97  mov     rdi, [rsp+78h+arg_20]
0x140063a9f  mov     [rsp+78h+KeyHandle], 0
0x140063aa8  test    sil, sil
0x140063aab  jnz     short loc_140063ABC
0x140063aad  test    rdi, rdi
0x140063ab0  jnz     short loc_140063ABC
0x140063ab2  mov     ebx, 0C000000Dh
0x140063ab7  jmp     loc_140063B5B
0x140063abc  lea     r8, [rsp+78h+KeyHandle]
0x140063ac1  mov     rcx, rbx
0x140063ac4  call    FveRegOpenCreateKey
0x140063ac9  mov     ebx, eax
0x140063acb  test    eax, eax
0x140063acd  js      short loc_140063B3C
0x140063acf  mov     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x140063ad4  mov     rdx, rbp; ValueName
0x140063ad7  test    sil, sil
0x140063ada  jnz     short loc_140063B23
0x140063adc  mov     eax, [rsp+78h+arg_28]
0x140063ae3  mov     r9d, r14d; Type
0x140063ae6  mov     [rsp+78h+DataSize], eax; DataSize
0x140063aea  xor     r8d, r8d; TitleIndex
0x140063aed  mov     [rsp+78h+Data], rdi; Data
0x140063af2  call    cs:__imp_ZwSetValueKey
0x140063af9  nop     dword ptr [rax+rax+00h]
0x140063afe  mov     ebx, eax
0x140063b00  test    eax, eax
0x140063b02  js      short loc_140063B3C
0x140063b04  cmp     [rsp+78h+arg_30], sil
0x140063b0c  jz      short loc_140063B3C
0x140063b0e  mov     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x140063b13  call    cs:__imp_ZwFlushKey
0x140063b1a  nop     dword ptr [rax+rax+00h]
0x140063b1f  mov     ebx, eax
0x140063b21  jmp     short loc_140063B3C
0x140063b23  call    cs:__imp_ZwDeleteValueKey
0x140063b2a  nop     dword ptr [rax+rax+00h]
0x140063b2f  mov     ebx, eax
0x140063b31  xor     eax, eax
0x140063b33  cmp     ebx, 0C0000034h
0x140063b39  cmovz   ebx, eax
0x140063b3c  mov     rcx, [rsp+78h+KeyHandle]; Handle
0x140063b41  test    rcx, rcx
0x140063b44  jz      short loc_140063B5B
0x140063b46  call    cs:__imp_ZwClose
0x140063b4d  nop     dword ptr [rax+rax+00h]
0x140063b52  mov     [rsp+78h+KeyHandle], 0
0x140063b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140063b62  cmp     rcx, r12
0x140063b65  jz      short loc_140063B8C
0x140063b67  mov     eax, [rcx+2Ch]
0x140063b6a  test    al, 8
0x140063b6c  jz      short loc_140063B8C
0x140063b6e  cmp     byte ptr [rcx+29h], 5
0x140063b72  jb      short loc_140063B8C
0x140063b74  mov     rcx, [rcx+18h]
0x140063b78  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140063b7f  mov     edx, 3Ch ; '<'
0x140063b84  mov     r9d, ebx
0x140063b87  call    WPP_SF_d
0x140063b8c  mov     eax, ebx
0x140063b8e  add     rsp, 48h
0x140063b92  pop     r14
0x140063b94  pop     r12
0x140063b96  pop     rdi
0x140063b97  pop     rsi
0x140063b98  pop     rbp
0x140063b99  pop     rbx
0x140063b9a  retn
```

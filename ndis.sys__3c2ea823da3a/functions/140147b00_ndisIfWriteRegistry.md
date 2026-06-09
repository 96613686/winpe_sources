# ndisIfWriteRegistry

- ea: `0x140147b00`
- end: `0x140147cba`
- name: `ndisIfWriteRegistry`
- size: `442`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140165770`
- `0x140167130`

## callees

- `0x1400e6160`
- `0x140147b00`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140147bcb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140147bcb`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140147bdf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140147bdf`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140147b54`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140147b54`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140147c45`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140147c79`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140147c45`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140147c79`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140147bf3`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140147bf3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140147b79`
- `ntoskrnl!RtlInitUnicodeString` at `0x140147b79`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140147c0b`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140147c0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140147c92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140147c92`
- `ntoskrnl!ExAllocatePool2` at `0x140147bae`
- `ntoskrnl!ExAllocatePool2` at `0x140147bae`

## pseudocode

```c
__int64 __fastcall ndisIfWriteRegistry(__int64 a1)
{
  ULONG v2; // ecx
  unsigned int RegistryKey; // ebx
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-39h] BYREF
  int ValueData; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING String; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-11h] BYREF
  char v9; // [rsp+68h] [rbp-1h] BYREF

  *(_QWORD *)&String.Length = 2621440;
  *(_QWORD *)&Destination.Length = 0;
  Destination.Buffer = 0;
  v2 = *(unsigned __int16 *)(a1 + 16);
  ValueData = 0;
  String.Buffer = (wchar_t *)&v9;
  DestinationString = 0;
  if ( RtlIntegerToUnicodeString(v2, 0xAu, &String)
    || (RtlInitUnicodeString(&DestinationString, L"Ndis\\IfTypes\\"),
        Destination.Length = 0,
        Destination.MaximumLength = String.Length + DestinationString.Length + 4,
        (Destination.Buffer = (wchar_t *)ExAllocatePool2(64, Destination.MaximumLength, 538985550)) == 0) )
  {
    RegistryKey = -1073741670;
  }
  else
  {
    RtlCopyUnicodeString(&Destination, &DestinationString);
    RtlAppendUnicodeStringToString(&Destination, &String);
    if ( !RtlCheckRegistryKey(1u, Destination.Buffer)
      || (RegistryKey = RtlCreateRegistryKey(1u, Destination.Buffer)) == 0 )
    {
      ValueData = *(unsigned __int16 *)(a1 + 16);
      RegistryKey = RtlWriteRegistryValue(1u, Destination.Buffer, L"IfType", 4u, &ValueData, 4u);
      if ( !RegistryKey )
        RegistryKey = RtlWriteRegistryValue(
                        1u,
                        Destination.Buffer,
                        L"IfUsedNetLuidIndices",
                        3u,
                        *(PVOID *)(a1 + 56),
                        *(_DWORD *)(a1 + 40));
    }
  }
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0);
  return RegistryKey;
}

```

## disassembly

```asm
0x140147b00  push    rbp
0x140147b02  push    rbx
0x140147b03  push    rdi
0x140147b04  push    r15
0x140147b06  lea     rbp, [rsp-3Fh]
0x140147b0b  sub     rsp, 0A8h
0x140147b12  mov     rax, cs:__security_cookie
0x140147b19  xor     rax, rsp
0x140147b1c  mov     [rbp+57h+var_30], rax
0x140147b20  xor     eax, eax
0x140147b22  mov     qword ptr [rbp+57h+String.Length], 280000h
0x140147b2a  mov     qword ptr [rbp+57h+Destination.Length], rax
0x140147b2e  lea     r8, [rbp+57h+String]; String
0x140147b32  mov     [rbp+57h+Destination.Buffer], rax
0x140147b36  mov     rdi, rcx
0x140147b39  movzx   ecx, word ptr [rcx+10h]; Value
0x140147b3d  xorps   xmm0, xmm0
0x140147b40  mov     [rbp+57h+var_80], eax
0x140147b43  mov     edx, 0Ah; Base
0x140147b48  lea     rax, [rbp+57h+var_58]
0x140147b4c  mov     [rbp+57h+String.Buffer], rax
0x140147b50  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140147b54  call    cs:__imp_RtlIntegerToUnicodeString
0x140147b5b  nop     dword ptr [rax+rax+00h]
0x140147b60  test    eax, eax
0x140147b62  jz      short loc_140147B6E
0x140147b64  mov     ebx, 0C000009Ah
0x140147b69  jmp     loc_140147C87
0x140147b6e  lea     rdx, aNdisIftypes; "Ndis\\IfTypes\\"
0x140147b75  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140147b79  call    cs:__imp_RtlInitUnicodeString
0x140147b80  nop     dword ptr [rax+rax+00h]
0x140147b85  xor     eax, eax
0x140147b87  mov     r15d, 4
0x140147b8d  mov     [rbp+57h+Destination.Length], ax
0x140147b91  mov     r8d, 2020444Eh
0x140147b97  movzx   eax, [rbp+57h+DestinationString.Length]
0x140147b9b  add     ax, [rbp+57h+String.Length]
0x140147b9f  add     ax, r15w
0x140147ba3  lea     ecx, [r15+3Ch]
0x140147ba7  movzx   edx, ax
0x140147baa  mov     [rbp+57h+Destination.MaximumLength], dx
0x140147bae  call    cs:__imp_ExAllocatePool2
0x140147bb5  nop     dword ptr [rax+rax+00h]
0x140147bba  mov     [rbp+57h+Destination.Buffer], rax
0x140147bbe  test    rax, rax
0x140147bc1  jz      short loc_140147B64
0x140147bc3  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x140147bc7  lea     rcx, [rbp+57h+Destination]; DestinationString
0x140147bcb  call    cs:__imp_RtlCopyUnicodeString
0x140147bd2  nop     dword ptr [rax+rax+00h]
0x140147bd7  lea     rdx, [rbp+57h+String]; Source
0x140147bdb  lea     rcx, [rbp+57h+Destination]; Destination
0x140147bdf  call    cs:__imp_RtlAppendUnicodeStringToString
0x140147be6  nop     dword ptr [rax+rax+00h]
0x140147beb  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140147bef  lea     ecx, [r15-3]; RelativeTo
0x140147bf3  call    cs:__imp_RtlCheckRegistryKey
0x140147bfa  nop     dword ptr [rax+rax+00h]
0x140147bff  test    eax, eax
0x140147c01  jz      short loc_140147C1D
0x140147c03  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140147c07  lea     ecx, [r15-3]; RelativeTo
0x140147c0b  call    cs:__imp_RtlCreateRegistryKey
0x140147c12  nop     dword ptr [rax+rax+00h]
0x140147c17  mov     ebx, eax
0x140147c19  test    eax, eax
0x140147c1b  jnz     short loc_140147C87
0x140147c1d  movzx   eax, word ptr [rdi+10h]
0x140147c21  lea     r8, aIftype; "IfType"
0x140147c28  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140147c2c  mov     r9d, r15d; ValueType
0x140147c2f  mov     [rbp+57h+var_80], eax
0x140147c32  mov     ecx, 1; RelativeTo
0x140147c37  lea     rax, [rbp+57h+var_80]
0x140147c3b  mov     [rsp+0C0h+ValueLength], r15d; ValueLength
0x140147c40  mov     [rsp+0C0h+ValueData], rax; ValueData
0x140147c45  call    cs:__imp_RtlWriteRegistryValue
0x140147c4c  nop     dword ptr [rax+rax+00h]
0x140147c51  mov     ebx, eax
0x140147c53  test    eax, eax
0x140147c55  jnz     short loc_140147C87
0x140147c57  mov     eax, [rdi+28h]
0x140147c5a  lea     r9d, [rbx+3]; ValueType
0x140147c5e  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140147c62  lea     r8, aIfusednetluidi; "IfUsedNetLuidIndices"
0x140147c69  mov     [rsp+0C0h+ValueLength], eax; ValueLength
0x140147c6d  lea     ecx, [rbx+1]; RelativeTo
0x140147c70  mov     rax, [rdi+38h]
0x140147c74  mov     [rsp+0C0h+ValueData], rax; ValueData
0x140147c79  call    cs:__imp_RtlWriteRegistryValue
0x140147c80  nop     dword ptr [rax+rax+00h]
0x140147c85  mov     ebx, eax
0x140147c87  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x140147c8b  test    rcx, rcx
0x140147c8e  jz      short loc_140147C9E
0x140147c90  xor     edx, edx; Tag
0x140147c92  call    cs:__imp_ExFreePoolWithTag
0x140147c99  nop     dword ptr [rax+rax+00h]
0x140147c9e  mov     eax, ebx
0x140147ca0  mov     rcx, [rbp+57h+var_30]
0x140147ca4  xor     rcx, rsp; StackCookie
0x140147ca7  call    __security_check_cookie
0x140147cac  add     rsp, 0A8h
0x140147cb3  pop     r15
0x140147cb5  pop     rdi
0x140147cb6  pop     rbx
0x140147cb7  pop     rbp
0x140147cb8  retn
```

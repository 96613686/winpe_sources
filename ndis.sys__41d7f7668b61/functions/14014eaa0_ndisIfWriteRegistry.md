# ndisIfWriteRegistry

- ea: `0x14014eaa0`
- end: `0x14014ec5a`
- name: `ndisIfWriteRegistry`
- size: `442`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14016c700`
- `0x14016dfd0`

## callees

- `0x1400eb380`
- `0x14014eaa0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14014eb6b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14014eb6b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14014eb7f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14014eb7f`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14014eaf4`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14014eaf4`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14014ebe5`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14014ec19`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14014ebe5`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14014ec19`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14014eb93`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14014eb93`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014eb19`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014eb19`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14014ebab`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14014ebab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014ec32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014ec32`
- `ntoskrnl!ExAllocatePool2` at `0x14014eb4e`
- `ntoskrnl!ExAllocatePool2` at `0x14014eb4e`

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
0x14014eaa0  push    rbp
0x14014eaa2  push    rbx
0x14014eaa3  push    rdi
0x14014eaa4  push    r15
0x14014eaa6  lea     rbp, [rsp-3Fh]
0x14014eaab  sub     rsp, 0A8h
0x14014eab2  mov     rax, cs:__security_cookie
0x14014eab9  xor     rax, rsp
0x14014eabc  mov     [rbp+57h+var_30], rax
0x14014eac0  xor     eax, eax
0x14014eac2  mov     qword ptr [rbp+57h+String.Length], 280000h
0x14014eaca  mov     qword ptr [rbp+57h+Destination.Length], rax
0x14014eace  lea     r8, [rbp+57h+String]; String
0x14014ead2  mov     [rbp+57h+Destination.Buffer], rax
0x14014ead6  mov     rdi, rcx
0x14014ead9  movzx   ecx, word ptr [rcx+10h]; Value
0x14014eadd  xorps   xmm0, xmm0
0x14014eae0  mov     [rbp+57h+var_80], eax
0x14014eae3  mov     edx, 0Ah; Base
0x14014eae8  lea     rax, [rbp+57h+var_58]
0x14014eaec  mov     [rbp+57h+String.Buffer], rax
0x14014eaf0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14014eaf4  call    cs:__imp_RtlIntegerToUnicodeString
0x14014eafb  nop     dword ptr [rax+rax+00h]
0x14014eb00  test    eax, eax
0x14014eb02  jz      short loc_14014EB0E
0x14014eb04  mov     ebx, 0C000009Ah
0x14014eb09  jmp     loc_14014EC27
0x14014eb0e  lea     rdx, SourceString; "Ndis\\IfTypes\\"
0x14014eb15  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14014eb19  call    cs:__imp_RtlInitUnicodeString
0x14014eb20  nop     dword ptr [rax+rax+00h]
0x14014eb25  xor     eax, eax
0x14014eb27  mov     r15d, 4
0x14014eb2d  mov     [rbp+57h+Destination.Length], ax
0x14014eb31  mov     r8d, 2020444Eh
0x14014eb37  movzx   eax, [rbp+57h+DestinationString.Length]
0x14014eb3b  add     ax, [rbp+57h+String.Length]
0x14014eb3f  add     ax, r15w
0x14014eb43  lea     ecx, [r15+3Ch]
0x14014eb47  movzx   edx, ax
0x14014eb4a  mov     [rbp+57h+Destination.MaximumLength], dx
0x14014eb4e  call    cs:__imp_ExAllocatePool2
0x14014eb55  nop     dword ptr [rax+rax+00h]
0x14014eb5a  mov     [rbp+57h+Destination.Buffer], rax
0x14014eb5e  test    rax, rax
0x14014eb61  jz      short loc_14014EB04
0x14014eb63  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14014eb67  lea     rcx, [rbp+57h+Destination]; DestinationString
0x14014eb6b  call    cs:__imp_RtlCopyUnicodeString
0x14014eb72  nop     dword ptr [rax+rax+00h]
0x14014eb77  lea     rdx, [rbp+57h+String]; Source
0x14014eb7b  lea     rcx, [rbp+57h+Destination]; Destination
0x14014eb7f  call    cs:__imp_RtlAppendUnicodeStringToString
0x14014eb86  nop     dword ptr [rax+rax+00h]
0x14014eb8b  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x14014eb8f  lea     ecx, [r15-3]; RelativeTo
0x14014eb93  call    cs:__imp_RtlCheckRegistryKey
0x14014eb9a  nop     dword ptr [rax+rax+00h]
0x14014eb9f  test    eax, eax
0x14014eba1  jz      short loc_14014EBBD
0x14014eba3  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x14014eba7  lea     ecx, [r15-3]; RelativeTo
0x14014ebab  call    cs:__imp_RtlCreateRegistryKey
0x14014ebb2  nop     dword ptr [rax+rax+00h]
0x14014ebb7  mov     ebx, eax
0x14014ebb9  test    eax, eax
0x14014ebbb  jnz     short loc_14014EC27
0x14014ebbd  movzx   eax, word ptr [rdi+10h]
0x14014ebc1  lea     r8, aIftype; "IfType"
0x14014ebc8  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x14014ebcc  mov     r9d, r15d; ValueType
0x14014ebcf  mov     [rbp+57h+var_80], eax
0x14014ebd2  mov     ecx, 1; RelativeTo
0x14014ebd7  lea     rax, [rbp+57h+var_80]
0x14014ebdb  mov     [rsp+0C0h+ValueLength], r15d; ValueLength
0x14014ebe0  mov     [rsp+0C0h+ValueData], rax; ValueData
0x14014ebe5  call    cs:__imp_RtlWriteRegistryValue
0x14014ebec  nop     dword ptr [rax+rax+00h]
0x14014ebf1  mov     ebx, eax
0x14014ebf3  test    eax, eax
0x14014ebf5  jnz     short loc_14014EC27
0x14014ebf7  mov     eax, [rdi+28h]
0x14014ebfa  lea     r9d, [rbx+3]; ValueType
0x14014ebfe  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x14014ec02  lea     r8, aIfusednetluidi; "IfUsedNetLuidIndices"
0x14014ec09  mov     [rsp+0C0h+ValueLength], eax; ValueLength
0x14014ec0d  lea     ecx, [rbx+1]; RelativeTo
0x14014ec10  mov     rax, [rdi+38h]
0x14014ec14  mov     [rsp+0C0h+ValueData], rax; ValueData
0x14014ec19  call    cs:__imp_RtlWriteRegistryValue
0x14014ec20  nop     dword ptr [rax+rax+00h]
0x14014ec25  mov     ebx, eax
0x14014ec27  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x14014ec2b  test    rcx, rcx
0x14014ec2e  jz      short loc_14014EC3E
0x14014ec30  xor     edx, edx; Tag
0x14014ec32  call    cs:__imp_ExFreePoolWithTag
0x14014ec39  nop     dword ptr [rax+rax+00h]
0x14014ec3e  mov     eax, ebx
0x14014ec40  mov     rcx, [rbp+57h+var_30]
0x14014ec44  xor     rcx, rsp; StackCookie
0x14014ec47  call    __security_check_cookie
0x14014ec4c  add     rsp, 0A8h
0x14014ec53  pop     r15
0x14014ec55  pop     rdi
0x14014ec56  pop     rbx
0x14014ec57  pop     rbp
0x14014ec58  retn
```

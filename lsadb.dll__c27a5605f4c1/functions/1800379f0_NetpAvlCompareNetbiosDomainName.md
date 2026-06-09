# NetpAvlCompareNetbiosDomainName

- ea: `0x1800379f0`
- end: `0x180037a5a`
- name: `NetpAvlCompareNetbiosDomainName`
- size: `106`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800379f0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180037a3c`
- `ntdll!RtlCompareUnicodeString` at `0x180037a3c`
- `ntdll!RtlInitUnicodeString` at `0x180037a15`
- `ntdll!RtlInitUnicodeString` at `0x180037a24`
- `ntdll!RtlInitUnicodeString` at `0x180037a15`
- `ntdll!RtlInitUnicodeString` at `0x180037a24`

## pseudocode

```c
__int64 __fastcall NetpAvlCompareNetbiosDomainName(
        struct _RTL_AVL_TABLE *Table,
        __int64 *FirstStruct,
        __int64 *SecondStruct)
{
  __int64 v3; // rdx
  __int64 v4; // rbx
  unsigned int v5; // ebx
  LONG v6; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  v3 = *FirstStruct;
  v4 = *SecondStruct;
  DestinationString = 0;
  String2 = 0;
  RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v3 + 24));
  RtlInitUnicodeString(&String2, *(PCWSTR *)(v4 + 24));
  v5 = 1;
  v6 = RtlCompareUnicodeString(&DestinationString, &String2, 1u);
  if ( v6 <= 0 )
  {
    v5 = 2;
    if ( v6 < 0 )
      return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800379f0  push    rbx
0x1800379f2  sub     rsp, 40h
0x1800379f6  mov     rdx, [rdx]
0x1800379f9  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1800379fe  mov     rbx, [r8]
0x180037a01  xorps   xmm0, xmm0
0x180037a04  xorps   xmm1, xmm1
0x180037a07  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x180037a0c  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x180037a11  mov     rdx, [rdx+18h]; SourceString
0x180037a15  call    cs:__imp_RtlInitUnicodeString
0x180037a1b  mov     rdx, [rbx+18h]; SourceString
0x180037a1f  lea     rcx, [rsp+48h+String2]; DestinationString
0x180037a24  call    cs:__imp_RtlInitUnicodeString
0x180037a2a  mov     ebx, 1
0x180037a2f  lea     rdx, [rsp+48h+String2]; String2
0x180037a34  mov     r8b, bl; CaseInsensitive
0x180037a37  lea     rcx, [rsp+48h+DestinationString]; String1
0x180037a3c  call    cs:__imp_RtlCompareUnicodeString
0x180037a42  test    eax, eax
0x180037a44  jg      short loc_180037A52
0x180037a46  xor     ecx, ecx
0x180037a48  mov     ebx, 2
0x180037a4d  test    eax, eax
0x180037a4f  cmovs   ebx, ecx
0x180037a52  mov     eax, ebx
0x180037a54  add     rsp, 40h
0x180037a58  pop     rbx
0x180037a59  retn
```

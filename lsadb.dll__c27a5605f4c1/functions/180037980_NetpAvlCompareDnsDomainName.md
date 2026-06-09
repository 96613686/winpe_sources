# NetpAvlCompareDnsDomainName

- ea: `0x180037980`
- end: `0x1800379ea`
- name: `NetpAvlCompareDnsDomainName`
- size: `106`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180037980`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800379cc`
- `ntdll!RtlCompareUnicodeString` at `0x1800379cc`
- `ntdll!RtlInitUnicodeString` at `0x1800379a5`
- `ntdll!RtlInitUnicodeString` at `0x1800379b4`
- `ntdll!RtlInitUnicodeString` at `0x1800379a5`
- `ntdll!RtlInitUnicodeString` at `0x1800379b4`

## pseudocode

```c
__int64 __fastcall NetpAvlCompareDnsDomainName(
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
  RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v3 + 16));
  RtlInitUnicodeString(&String2, *(PCWSTR *)(v4 + 16));
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
0x180037980  push    rbx
0x180037982  sub     rsp, 40h
0x180037986  mov     rdx, [rdx]
0x180037989  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18003798e  mov     rbx, [r8]
0x180037991  xorps   xmm0, xmm0
0x180037994  xorps   xmm1, xmm1
0x180037997  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18003799c  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x1800379a1  mov     rdx, [rdx+10h]; SourceString
0x1800379a5  call    cs:__imp_RtlInitUnicodeString
0x1800379ab  mov     rdx, [rbx+10h]; SourceString
0x1800379af  lea     rcx, [rsp+48h+String2]; DestinationString
0x1800379b4  call    cs:__imp_RtlInitUnicodeString
0x1800379ba  mov     ebx, 1
0x1800379bf  lea     rdx, [rsp+48h+String2]; String2
0x1800379c4  mov     r8b, bl; CaseInsensitive
0x1800379c7  lea     rcx, [rsp+48h+DestinationString]; String1
0x1800379cc  call    cs:__imp_RtlCompareUnicodeString
0x1800379d2  test    eax, eax
0x1800379d4  jg      short loc_1800379E2
0x1800379d6  xor     ecx, ecx
0x1800379d8  mov     ebx, 2
0x1800379dd  test    eax, eax
0x1800379df  cmovs   ebx, ecx
0x1800379e2  mov     eax, ebx
0x1800379e4  add     rsp, 40h
0x1800379e8  pop     rbx
0x1800379e9  retn
```

# CloudAPCompareStrings(ushort const *,ushort const *)

- ea: `0x180003e70`
- end: `0x180003eed`
- name: `?CloudAPCompareStrings@@YAHPEBG0@Z`
- size: `125`
- prototype: `LONG __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800035b4`
- `0x180003ef4`
- `0x180004e80`
- `0x18002b6dc`
- `0x1800307d0`
- `0x180037240`
- `0x18003de28`
- `0x18004cf50`
- `0x18004d294`
- `0x18004e7b0`
- `0x18004f600`

## callees

- `0x180003e70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180003e93`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180003e93`
- `ntdll!RtlInitUnicodeString` at `0x180003eb1`
- `ntdll!RtlInitUnicodeString` at `0x180003ebf`
- `ntdll!RtlInitUnicodeString` at `0x180003eb1`
- `ntdll!RtlInitUnicodeString` at `0x180003ebf`
- `ntdll!RtlCompareUnicodeString` at `0x180003ed2`
- `ntdll!RtlCompareUnicodeString` at `0x180003ed2`

## pseudocode

```c
LONG __fastcall CloudAPCompareStrings(PCWSTR SourceString, PCWSTR a2)
{
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  DestinationString = 0;
  String2 = 0;
  if ( (g_ulTestFlags & 2) != 0 )
    return _o__wcsicmp(SourceString, a2);
  if ( !SourceString )
    return -(a2 != 0);
  if ( !a2 )
    return 1;
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&String2, a2);
  return RtlCompareUnicodeString(&DestinationString, &String2, 1u);
}

```

## disassembly

```asm
0x180003e70  push    rbx
0x180003e72  sub     rsp, 40h
0x180003e76  mov     eax, cs:?g_ulTestFlags@@3KA; ulong g_ulTestFlags
0x180003e7c  xorps   xmm0, xmm0
0x180003e7f  xorps   xmm1, xmm1
0x180003e82  mov     rbx, rdx
0x180003e85  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x180003e8a  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x180003e8f  test    al, 2
0x180003e91  jz      short loc_180003E9F
0x180003e93  call    cs:__imp__o__wcsicmp
0x180003e99  add     rsp, 40h
0x180003e9d  pop     rbx
0x180003e9e  retn
0x180003e9f  test    rcx, rcx
0x180003ea2  jz      short loc_180003EDA
0x180003ea4  test    rbx, rbx
0x180003ea7  jz      short loc_180003EE6
0x180003ea9  mov     rdx, rcx; SourceString
0x180003eac  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180003eb1  call    cs:__imp_RtlInitUnicodeString
0x180003eb7  mov     rdx, rbx; SourceString
0x180003eba  lea     rcx, [rsp+48h+String2]; DestinationString
0x180003ebf  call    cs:__imp_RtlInitUnicodeString
0x180003ec5  mov     r8b, 1; CaseInsensitive
0x180003ec8  lea     rdx, [rsp+48h+String2]; String2
0x180003ecd  lea     rcx, [rsp+48h+DestinationString]; String1
0x180003ed2  call    cs:__imp_RtlCompareUnicodeString
0x180003ed8  jmp     short loc_180003E99
0x180003eda  xor     eax, eax
0x180003edc  sub     rax, rbx
0x180003edf  neg     rax
0x180003ee2  sbb     eax, eax
0x180003ee4  jmp     short loc_180003E99
0x180003ee6  mov     eax, 1
0x180003eeb  jmp     short loc_180003E99
```

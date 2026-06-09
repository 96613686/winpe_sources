# Common::GenericMapCaseInsensitiveCompare(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x180009bb0`
- end: `0x180009c15`
- name: `?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `101`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009bb0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180009bf7`
- `ntdll!RtlCompareUnicodeString` at `0x180009bf7`
- `ntdll!RtlInitUnicodeString` at `0x180009bd1`
- `ntdll!RtlInitUnicodeString` at `0x180009bdf`
- `ntdll!RtlInitUnicodeString` at `0x180009bd1`
- `ntdll!RtlInitUnicodeString` at `0x180009bdf`

## pseudocode

```c
__int64 __fastcall Common::GenericMapCaseInsensitiveCompare(
        struct _RTL_AVL_TABLE *Table,
        const WCHAR **FirstStruct,
        const WCHAR **SecondStruct)
{
  const WCHAR *v3; // rdx
  const WCHAR *v4; // rbx
  unsigned int v5; // ebx
  LONG v6; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  v3 = *FirstStruct;
  v4 = *SecondStruct;
  DestinationString = 0;
  String2 = 0;
  RtlInitUnicodeString(&DestinationString, v3);
  RtlInitUnicodeString(&String2, v4);
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
0x180009bb0  push    rbx
0x180009bb2  sub     rsp, 40h
0x180009bb6  mov     rdx, [rdx]; SourceString
0x180009bb9  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180009bbe  mov     rbx, [r8]
0x180009bc1  xorps   xmm0, xmm0
0x180009bc4  xorps   xmm1, xmm1
0x180009bc7  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x180009bcc  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x180009bd1  call    cs:__imp_RtlInitUnicodeString
0x180009bd7  mov     rdx, rbx; SourceString
0x180009bda  lea     rcx, [rsp+48h+String2]; DestinationString
0x180009bdf  call    cs:__imp_RtlInitUnicodeString
0x180009be5  mov     ebx, 1
0x180009bea  lea     rdx, [rsp+48h+String2]; String2
0x180009bef  mov     r8b, bl; CaseInsensitive
0x180009bf2  lea     rcx, [rsp+48h+DestinationString]; String1
0x180009bf7  call    cs:__imp_RtlCompareUnicodeString
0x180009bfd  test    eax, eax
0x180009bff  jg      short loc_180009C0D
0x180009c01  xor     ecx, ecx
0x180009c03  mov     ebx, 2
0x180009c08  test    eax, eax
0x180009c0a  cmovs   ebx, ecx
0x180009c0d  mov     eax, ebx
0x180009c0f  add     rsp, 40h
0x180009c13  pop     rbx
0x180009c14  retn
```

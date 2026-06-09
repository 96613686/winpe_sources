# EapInitConditionParams

- ea: `0x180009bec`
- end: `0x180009c8b`
- name: `EapInitConditionParams`
- size: `159`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009ff0`

## callees

- `0x180009bec`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180009c23`
- `ntdll!RtlCompareUnicodeString` at `0x180009c64`
- `ntdll!RtlCompareUnicodeString` at `0x180009c23`
- `ntdll!RtlCompareUnicodeString` at `0x180009c64`

## pseudocode

```c
__int64 __fastcall EapInitConditionParams(PCUNICODE_STRING String2, __int64 a2)
{
  UNICODE_STRING v5; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)&v5.Length = 524296;
  v5.Buffer = L"AND";
  String1 = 0;
  if ( RtlCompareUnicodeString(&v5, String2, 1u) )
  {
    *(_DWORD *)&String1.Length = 393222;
    String1.Buffer = L"OR";
    if ( RtlCompareUnicodeString(&String1, String2, 1u) )
    {
      *(_DWORD *)a2 = 0;
      return 0;
    }
    *(_QWORD *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)(a2 + 8) = 0;
  }
  *(_DWORD *)a2 = 1;
  *(_QWORD *)(a2 + 16) = 0;
  return 0;
}

```

## disassembly

```asm
0x180009bec  mov     r11, rsp
0x180009bef  mov     [r11+8], rbx
0x180009bf3  push    rdi
0x180009bf4  sub     rsp, 40h
0x180009bf8  mov     rbx, rdx
0x180009bfb  mov     qword ptr [r11-28h], 80008h
0x180009c03  mov     rdx, rcx; String2
0x180009c06  lea     rax, EA_STORE_PREDICATE_AND_STRING; "AND"
0x180009c0d  mov     rdi, rcx
0x180009c10  mov     [r11-20h], rax
0x180009c14  xorps   xmm0, xmm0
0x180009c17  lea     rcx, [r11-28h]; String1
0x180009c1b  mov     r8b, 1; CaseInsensitive
0x180009c1e  movups  xmmword ptr [rsp+48h+String1.Length], xmm0
0x180009c23  call    cs:__imp_RtlCompareUnicodeString
0x180009c29  test    eax, eax
0x180009c2b  jnz     short loc_180009C45
0x180009c2d  mov     qword ptr [rbx+8], 0
0x180009c35  mov     dword ptr [rbx], 1
0x180009c3b  mov     qword ptr [rbx+10h], 0
0x180009c43  jmp     short loc_180009C7E
0x180009c45  lea     rax, EA_STORE_PREDICATE_OR_STRING; "OR"
0x180009c4c  mov     dword ptr [rsp+48h+String1.Length], 60006h
0x180009c54  mov     r8b, 1; CaseInsensitive
0x180009c57  mov     [rsp+48h+String1.Buffer], rax
0x180009c5c  mov     rdx, rdi; String2
0x180009c5f  lea     rcx, [rsp+48h+String1]; String1
0x180009c64  call    cs:__imp_RtlCompareUnicodeString
0x180009c6a  test    eax, eax
0x180009c6c  jnz     short loc_180009C78
0x180009c6e  mov     qword ptr [rbx+8], 1
0x180009c76  jmp     short loc_180009C35
0x180009c78  mov     dword ptr [rbx], 0
0x180009c7e  mov     rbx, [rsp+48h+arg_0]
0x180009c83  xor     eax, eax
0x180009c85  add     rsp, 40h
0x180009c89  pop     rdi
0x180009c8a  retn
```

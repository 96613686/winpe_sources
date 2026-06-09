# DfscRmReferralTargetSortFunc

- ea: `0x1400199a0`
- end: `0x1400199de`
- name: `DfscRmReferralTargetSortFunc`
- size: `62`
- prototype: `LONG __fastcall(const UNICODE_STRING **, __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140028da0`

## callees

- `0x1400199a0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400199cc`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400199cc`

## pseudocode

```c
LONG __fastcall DfscRmReferralTargetSortFunc(const UNICODE_STRING **a1, __int64 *a2)
{
  __int64 v2; // rdx
  unsigned int v3; // eax

  v2 = *a2;
  v3 = *(_DWORD *)(v2 + 4);
  if ( *(_DWORD *)(&(*a1)->MaximumLength + 1) < v3 )
    return -1;
  if ( *(_DWORD *)(&(*a1)->MaximumLength + 1) <= v3 )
    return RtlCompareUnicodeString(*a1 + 6, (PCUNICODE_STRING)(v2 + 96), 1u);
  return 1;
}

```

## disassembly

```asm
0x1400199a0  sub     rsp, 28h
0x1400199a4  mov     rdx, [rdx]
0x1400199a7  mov     r8, [rcx]
0x1400199aa  mov     eax, [rdx+4]
0x1400199ad  cmp     [r8+4], eax
0x1400199b1  jnb     short loc_1400199B8
0x1400199b3  or      eax, 0FFFFFFFFh
0x1400199b6  jmp     short loc_1400199D8
0x1400199b8  jbe     short loc_1400199C1
0x1400199ba  mov     eax, 1
0x1400199bf  jmp     short loc_1400199D8
0x1400199c1  lea     rcx, [r8+60h]; String1
0x1400199c5  add     rdx, 60h ; '`'; String2
0x1400199c9  mov     r8b, 1; CaseInSensitive
0x1400199cc  call    cs:__imp_RtlCompareUnicodeString
0x1400199d3  nop     dword ptr [rax+rax+00h]
0x1400199d8  add     rsp, 28h
0x1400199dc  retn
```

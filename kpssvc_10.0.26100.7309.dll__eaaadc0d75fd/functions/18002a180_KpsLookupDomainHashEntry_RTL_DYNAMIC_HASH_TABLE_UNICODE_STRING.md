# KpsLookupDomainHashEntry(_RTL_DYNAMIC_HASH_TABLE *,_UNICODE_STRING *)

- ea: `0x18002a180`
- end: `0x18002a2b1`
- name: `?KpsLookupDomainHashEntry@@YAPEAU_KPS_DOMAIN_HASH_ENTRY@@PEAU_RTL_DYNAMIC_HASH_TABLE@@PEAU_UNICODE_STRING@@@Z`
- size: `305`
- prototype: `const UNICODE_STRING *__fastcall(struct _RTL_DYNAMIC_HASH_TABLE *, struct _UNICODE_STRING *)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027de0`
- `0x1800280d8`
- `0x1800291e4`
- `0x180029c48`
- `0x18002b03c`

## callees

- `0x180026d9c`
- `0x18002a180`
- `0x18002c4dc`
- `0x18002c534`
- `0x180030060`

## import_xrefs

- `ntdll!RtlGetNextEntryHashTable` at `0x18002a223`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002a223`
- `ntdll!RtlLookupEntryHashTable` at `0x18002a1ee`
- `ntdll!RtlLookupEntryHashTable` at `0x18002a1ee`
- `ntdll!RtlEqualUnicodeString` at `0x18002a209`
- `ntdll!RtlEqualUnicodeString` at `0x18002a209`

## pseudocode

```c
const UNICODE_STRING *__fastcall KpsLookupDomainHashEntry(
        struct _RTL_DYNAMIC_HASH_TABLE *a1,
        struct _UNICODE_STRING *a2)
{
  const UNICODE_STRING *v4; // rdi
  unsigned __int64 v5; // rax
  const UNICODE_STRING *i; // rax
  __int64 v7; // r8
  const UNICODE_STRING *v8; // rbx
  int v9; // eax
  _QWORD *v10; // rcx
  __int128 v12; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+40h] [rbp-18h]

  v12 = 0;
  v13 = 0;
  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2);
  v5 = HashUnicodeString(a2);
  for ( i = (const UNICODE_STRING *)RtlLookupEntryHashTable(a1, v5, &v12);
        ;
        i = (const UNICODE_STRING *)RtlGetNextEntryHashTable(a1, &v12) )
  {
    v8 = i;
    if ( !i )
      goto LABEL_12;
    v4 = i;
    if ( RtlEqualUnicodeString(i + 2, a2, 1u) )
      break;
    v4 = 0;
  }
  v9 = LODWORD(v8[1].Buffer) + 1;
  LODWORD(v8[1].Buffer) = v9;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v4;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v7, v8, v9);
LABEL_12:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
    WPP_SF_q(v10[2], 35, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18002a180  mov     r11, rsp
0x18002a183  mov     [r11+8], rbx
0x18002a187  mov     [r11+10h], rbp
0x18002a18b  mov     [r11+18h], rsi
0x18002a18f  mov     [r11+20h], rdi
0x18002a193  push    r14
0x18002a195  sub     rsp, 50h
0x18002a199  xor     eax, eax
0x18002a19b  xorps   xmm0, xmm0
0x18002a19e  movups  [rsp+58h+var_28], xmm0
0x18002a1a3  mov     [r11-18h], rax
0x18002a1a7  mov     rbp, rdx
0x18002a1aa  mov     rsi, rcx
0x18002a1ad  xor     edi, edi
0x18002a1af  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1b6  lea     r14, WPP_GLOBAL_Control
0x18002a1bd  cmp     rcx, r14
0x18002a1c0  jz      short loc_18002A1DB
0x18002a1c2  test    byte ptr [rcx+1Ch], 20h
0x18002a1c6  jz      short loc_18002A1DB
0x18002a1c8  mov     rcx, [rcx+10h]; LoggerHandle
0x18002a1cc  lea     edx, [rax+22h]
0x18002a1cf  mov     r9, rsi
0x18002a1d2  mov     [r11-38h], rbp
0x18002a1d6  call    WPP_SF_qZ
0x18002a1db  mov     rcx, rbp; struct _UNICODE_STRING *
0x18002a1de  call    ?HashUnicodeString@@YA_KPEAU_UNICODE_STRING@@@Z; HashUnicodeString(_UNICODE_STRING *)
0x18002a1e3  lea     r8, [rsp+58h+var_28]
0x18002a1e8  mov     rdx, rax
0x18002a1eb  mov     rcx, rsi
0x18002a1ee  call    cs:__imp_RtlLookupEntryHashTable
0x18002a1f5  nop     dword ptr [rax+rax+00h]
0x18002a1fa  jmp     short loc_18002A22F
0x18002a1fc  lea     rcx, [rbx+20h]; String1
0x18002a200  mov     r8b, 1; CaseInsensitive
0x18002a203  mov     rdx, rbp; String2
0x18002a206  mov     rdi, rbx
0x18002a209  call    cs:__imp_RtlEqualUnicodeString
0x18002a210  nop     dword ptr [rax+rax+00h]
0x18002a215  test    al, al
0x18002a217  jnz     short loc_18002A239
0x18002a219  xor     edi, edi
0x18002a21b  lea     rdx, [rsp+58h+var_28]
0x18002a220  mov     rcx, rsi
0x18002a223  call    cs:__imp_RtlGetNextEntryHashTable
0x18002a22a  nop     dword ptr [rax+rax+00h]
0x18002a22f  mov     rbx, rax
0x18002a232  test    rax, rax
0x18002a235  jnz     short loc_18002A1FC
0x18002a237  jmp     short loc_18002A268
0x18002a239  mov     eax, [rbx+18h]
0x18002a23c  inc     eax
0x18002a23e  mov     [rbx+18h], eax
0x18002a241  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a248  cmp     rcx, r14
0x18002a24b  jz      short loc_18002A292
0x18002a24d  test    byte ptr [rcx+1Ch], 80h
0x18002a251  jz      short loc_18002A26F
0x18002a253  mov     rcx, [rcx+10h]
0x18002a257  mov     edx, 20h ; ' '
0x18002a25c  mov     r9, rbx
0x18002a25f  mov     [rsp+58h+var_38], eax
0x18002a263  call    WPP_SF_qL
0x18002a268  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a26f  cmp     rcx, r14
0x18002a272  jz      short loc_18002A292
0x18002a274  test    byte ptr [rcx+1Ch], 20h
0x18002a278  jz      short loc_18002A292
0x18002a27a  mov     rcx, [rcx+10h]
0x18002a27e  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002a285  mov     edx, 23h ; '#'
0x18002a28a  mov     r9, rdi
0x18002a28d  call    WPP_SF_q
0x18002a292  mov     rbx, [rsp+58h+arg_0]
0x18002a297  mov     rax, rdi
0x18002a29a  mov     rdi, [rsp+58h+arg_18]
0x18002a29f  mov     rbp, [rsp+58h+arg_8]
0x18002a2a4  mov     rsi, [rsp+58h+arg_10]
0x18002a2a9  add     rsp, 50h
0x18002a2ad  pop     r14
0x18002a2af  retn
```

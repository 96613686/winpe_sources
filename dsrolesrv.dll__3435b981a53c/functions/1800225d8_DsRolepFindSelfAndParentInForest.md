# DsRolepFindSelfAndParentInForest

- ea: `0x1800225d8`
- end: `0x180022680`
- name: `DsRolepFindSelfAndParentInForest`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800100c0`
- `0x1800225d8`

## callees

- `0x1800225d8`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180022633`
- `ntdll!RtlCompareUnicodeString` at `0x180022633`

## pseudocode

```c
void __fastcall DsRolepFindSelfAndParentInForest(
        __int64 a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  int v8; // r13d
  __int64 v9; // rbp
  __int64 i; // rsi
  __int64 v11; // rax

  v8 = a1;
  if ( !*a4 || !*a5 )
  {
    v9 = *(_QWORD *)(a1 + 72);
    if ( v9 )
      a2 = *(_QWORD *)(a1 + 72);
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a2 + 60) && !*a5; i = (unsigned int)(i + 1) )
    {
      if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)(a2 + 64) + 72 * i), a3, 1u) )
      {
        v11 = *(_QWORD *)(a2 + 64);
        *a4 = a2;
        *a5 = v11 + 72 * i;
        return;
      }
      if ( !v9 )
        DsRolepFindSelfAndParentInForest(v8, *(_QWORD *)(a2 + 64) + 72 * i, (_DWORD)a3, (_DWORD)a4, (__int64)a5);
    }
  }
}

```

## disassembly

```asm
0x1800225d8  push    rbx
0x1800225da  push    rbp
0x1800225db  push    rsi
0x1800225dc  push    rdi
0x1800225dd  push    r12
0x1800225df  push    r13
0x1800225e1  push    r14
0x1800225e3  push    r15
0x1800225e5  sub     rsp, 38h
0x1800225e9  cmp     qword ptr [r9], 0
0x1800225ed  mov     r14, r9
0x1800225f0  mov     rdi, [rsp+78h+arg_20]
0x1800225f8  mov     r12, r8
0x1800225fb  mov     rbx, rdx
0x1800225fe  mov     r13, rcx
0x180022601  jz      short loc_180022609
0x180022603  cmp     qword ptr [rdi], 0
0x180022607  jnz     short loc_18002266F
0x180022609  mov     rbp, [rcx+48h]
0x18002260d  test    rbp, rbp
0x180022610  cmovnz  rbx, rbp
0x180022614  xor     esi, esi
0x180022616  cmp     esi, [rbx+3Ch]
0x180022619  jnb     short loc_18002266F
0x18002261b  cmp     qword ptr [rdi], 0
0x18002261f  jnz     short loc_18002266F
0x180022621  mov     rax, [rbx+40h]
0x180022625  lea     r15, [rsi+rsi*8]
0x180022629  mov     r8b, 1; CaseInsensitive
0x18002262c  mov     rdx, r12; String2
0x18002262f  lea     rcx, [rax+r15*8]; String1
0x180022633  call    cs:__imp_RtlCompareUnicodeString
0x180022639  test    eax, eax
0x18002263b  jz      short loc_180022661
0x18002263d  test    rbp, rbp
0x180022640  jnz     short loc_18002265D
0x180022642  mov     rax, [rbx+40h]
0x180022646  mov     r9, r14
0x180022649  mov     r8, r12
0x18002264c  mov     [rsp+78h+var_58], rdi
0x180022651  mov     rcx, r13
0x180022654  lea     rdx, [rax+r15*8]
0x180022658  call    DsRolepFindSelfAndParentInForest
0x18002265d  inc     esi
0x18002265f  jmp     short loc_180022616
0x180022661  mov     rax, [rbx+40h]
0x180022665  mov     [r14], rbx
0x180022668  lea     rcx, [rax+r15*8]
0x18002266c  mov     [rdi], rcx
0x18002266f  add     rsp, 38h
0x180022673  pop     r15
0x180022675  pop     r14
0x180022677  pop     r13
0x180022679  pop     r12
0x18002267b  pop     rdi
0x18002267c  pop     rsi
0x18002267d  pop     rbp
0x18002267e  pop     rbx
0x18002267f  retn
```

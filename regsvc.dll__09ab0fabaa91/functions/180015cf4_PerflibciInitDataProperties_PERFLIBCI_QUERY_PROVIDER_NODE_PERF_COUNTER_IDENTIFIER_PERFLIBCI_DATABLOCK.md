# PerflibciInitDataProperties(PERFLIBCI_QUERY_PROVIDER_NODE *,_PERF_COUNTER_IDENTIFIER *,PERFLIBCI_DATABLOCK *)

- ea: `0x180015cf4`
- end: `0x180015e1a`
- name: `?PerflibciInitDataProperties@@YAXPEAUPERFLIBCI_QUERY_PROVIDER_NODE@@PEAU_PERF_COUNTER_IDENTIFIER@@PEAUPERFLIBCI_DATABLOCK@@@Z`
- size: `294`
- prototype: `void __fastcall(struct PERFLIBCI_QUERY_PROVIDER_NODE *, struct _PERF_COUNTER_IDENTIFIER *, struct PERFLIBCI_DATABLOCK *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004bb0`

## callees

- `0x180002dd0`
- `0x180004e40`
- `0x180015cf4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015d55`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015d55`

## pseudocode

```c
void __fastcall PerflibciInitDataProperties(
        struct PERFLIBCI_QUERY_PROVIDER_NODE *a1,
        struct _PERF_COUNTER_IDENTIFIER *a2,
        struct PERFLIBCI_DATABLOCK *a3)
{
  const WCHAR *v6; // rbx
  char v7; // bp
  unsigned __int8 v8; // r14
  __int64 CounterSet; // rdx
  int v10; // eax
  __int64 v11; // rdx
  BOOL v12; // eax
  int v13; // eax

  *((_QWORD *)a3 + 3) = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  if ( a2->Size > 0x28 )
  {
    v6 = (const WCHAR *)&a2[1];
    if ( LOWORD(a2[1].CounterSetGuid.Data1) != 42 || HIWORD(a2[1].CounterSetGuid.Data1) )
    {
      if ( CompareStringOrdinal(v6, -1, L"_Total", -1, 1) == 2 )
        v7 = 1;
    }
    else
    {
      v8 = 1;
    }
  }
  CounterSet = PerflibciCreateOrFindCounterSet(a2, 0, 0, 0);
  if ( CounterSet )
  {
    v10 = 0;
    if ( (!v6 || v8 || v7) && (*(_BYTE *)(CounterSet + 88) & 4) != 0 )
    {
      v10 = 2 * v8 + 4;
      if ( (*(_BYTE *)(CounterSet + 88) & 8) != 0 )
        v10 |= 8u;
    }
    *((_DWORD *)a3 + 6) = v10;
    if ( *(_DWORD *)(*((_QWORD *)a1 + 1) + 32LL) == 1 )
    {
      v12 = *(_DWORD *)(CounterSet + 88) && (!v6 || PerflibciWildcardInstance(v6) || v7 && *(_DWORD *)(v11 + 88) == 6);
      if ( a2->CounterId == -1 )
        v13 = 4 * v12 + 2;
      else
        v13 = v12 ? 4 : 1;
      *((_DWORD *)a3 + 7) = v13;
    }
  }
}

```

## disassembly

```asm
0x180015cf4  push    rbx
0x180015cf6  push    rbp
0x180015cf7  push    rsi
0x180015cf8  push    rdi
0x180015cf9  push    r12
0x180015cfb  push    r13
0x180015cfd  push    r14
0x180015cff  push    r15
0x180015d01  sub     rsp, 48h
0x180015d05  xor     r12d, r12d
0x180015d08  mov     rdi, r8
0x180015d0b  mov     [r8+18h], r12
0x180015d0f  mov     rsi, rdx
0x180015d12  cmp     dword ptr [rdx+14h], 28h ; '('
0x180015d16  mov     r15, rcx
0x180015d19  mov     ebx, r12d
0x180015d1c  movzx   ebp, r12b
0x180015d20  lea     r13d, [r12+1]
0x180015d25  mov     r14b, r12b
0x180015d28  jbe     short loc_180015D62
0x180015d2a  lea     rbx, [rdx+28h]
0x180015d2e  cmp     word ptr [rbx], 2Ah ; '*'
0x180015d32  jnz     short loc_180015D40
0x180015d34  cmp     [rbx+2], r12w
0x180015d39  jnz     short loc_180015D40
0x180015d3b  mov     r14b, r13b
0x180015d3e  jmp     short loc_180015D62
0x180015d40  or      edx, 0FFFFFFFFh; cchCount1
0x180015d43  mov     [rsp+88h+bIgnoreCase], r13d; bIgnoreCase
0x180015d48  mov     r9d, edx; cchCount2
0x180015d4b  lea     r8, Src; "_Total"
0x180015d52  mov     rcx, rbx; lpString1
0x180015d55  call    cs:__imp_CompareStringOrdinal
0x180015d5b  cmp     eax, 2
0x180015d5e  cmovz   ebp, r13d
0x180015d62  mov     [rsp+88h+var_58], r12d; int
0x180015d67  xor     r9d, r9d
0x180015d6a  mov     [rsp+88h+var_60], r12w; __int16
0x180015d70  xor     r8d, r8d
0x180015d73  xor     edx, edx
0x180015d75  mov     qword ptr [rsp+88h+bIgnoreCase], r12; void *
0x180015d7a  mov     rcx, rsi; Buf1
0x180015d7d  call    PerflibciCreateOrFindCounterSet
0x180015d82  mov     rdx, rax
0x180015d85  test    rax, rax
0x180015d88  jz      short loc_180015E09
0x180015d8a  mov     eax, r12d
0x180015d8d  test    rbx, rbx
0x180015d90  jz      short loc_180015D9C
0x180015d92  test    r14b, r14b
0x180015d95  jnz     short loc_180015D9C
0x180015d97  test    bpl, bpl
0x180015d9a  jz      short loc_180015DB6
0x180015d9c  test    byte ptr [rdx+58h], 4
0x180015da0  jz      short loc_180015DB6
0x180015da2  test    byte ptr [rdx+58h], 8
0x180015da6  movzx   eax, r14b
0x180015daa  lea     eax, ds:4[rax*2]
0x180015db1  jz      short loc_180015DB6
0x180015db3  or      eax, 8
0x180015db6  mov     [rdi+18h], eax
0x180015db9  mov     rax, [r15+8]
0x180015dbd  cmp     [rax+20h], r13d
0x180015dc1  jnz     short loc_180015E09
0x180015dc3  cmp     [rdx+58h], r12d
0x180015dc7  jz      short loc_180015DE5
0x180015dc9  test    rbx, rbx
0x180015dcc  jz      short loc_180015DEA
0x180015dce  mov     rcx, rbx; unsigned __int16 *
0x180015dd1  call    ?PerflibciWildcardInstance@@YAEPEBG@Z; PerflibciWildcardInstance(ushort const *)
0x180015dd6  test    al, al
0x180015dd8  jnz     short loc_180015DEA
0x180015dda  test    bpl, bpl
0x180015ddd  jz      short loc_180015DE5
0x180015ddf  cmp     dword ptr [rdx+58h], 6
0x180015de3  jz      short loc_180015DEA
0x180015de5  mov     eax, r12d
0x180015de8  jmp     short loc_180015DED
0x180015dea  mov     eax, r13d
0x180015ded  cmp     dword ptr [rsi+18h], 0FFFFFFFFh
0x180015df1  jnz     short loc_180015DFC
0x180015df3  lea     eax, ds:2[rax*4]
0x180015dfa  jmp     short loc_180015E06
0x180015dfc  neg     eax
0x180015dfe  sbb     eax, eax
0x180015e00  and     eax, 3
0x180015e03  add     eax, r13d
0x180015e06  mov     [rdi+1Ch], eax
0x180015e09  add     rsp, 48h
0x180015e0d  pop     r15
0x180015e0f  pop     r14
0x180015e11  pop     r13
0x180015e13  pop     r12
0x180015e15  pop     rdi
0x180015e16  pop     rsi
0x180015e17  pop     rbp
0x180015e18  pop     rbx
0x180015e19  retn
```

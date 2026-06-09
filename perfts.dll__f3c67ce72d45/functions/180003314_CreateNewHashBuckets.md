# CreateNewHashBuckets

- ea: `0x180003314`
- end: `0x180003447`
- name: `CreateNewHashBuckets`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002820`
- `0x180002990`

## callees

- `0x180003314`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000341e`
- `KERNEL32!HeapFree` at `0x18000341e`
- `KERNEL32!HeapAlloc` at `0x18000333b`
- `KERNEL32!HeapAlloc` at `0x18000333b`

## pseudocode

```c
void __fastcall CreateNewHashBuckets(unsigned int a1)
{
  char *v2; // rax
  __int64 v3; // rdx
  char *v4; // rdi
  unsigned int v5; // r8d
  __int64 v6; // rcx
  char *v7; // rcx
  __int128 *v8; // rdx
  unsigned int v9; // esi
  __int128 *v10; // r8
  char *v11; // rax
  __int64 v12; // rcx
  __int128 *i; // rdx
  __int128 *v14; // r8
  char *v15; // rax
  __int64 v16; // rcx

  if ( a1 == 4 )
  {
    v3 = 0;
    v4 = (char *)&DefaultWinStationHashBuckets;
    v5 = 0;
    do
    {
LABEL_6:
      ++v5;
      v6 = 16 * v3++;
      v7 = &v4[v6];
      *((_QWORD *)v7 + 1) = v7;
      *(_QWORD *)v7 = v7;
    }
    while ( v5 < a1 );
    goto LABEL_7;
  }
  v2 = (char *)HeapAlloc(hLibHeap, 0, 16LL * a1);
  v3 = 0;
  v4 = v2;
  if ( !v2 )
    return;
  v5 = 0;
  if ( a1 )
    goto LABEL_6;
LABEL_7:
  v8 = (__int128 *)UsedList;
  v9 = a1 - 1;
  while ( v8 != &UsedList )
  {
    v10 = v8 - 1;
    v11 = &v4[16 * ((_DWORD)v8[1] & v9)];
    v12 = *(_QWORD *)v11;
    if ( *(char **)(*(_QWORD *)v11 + 8LL) != v11 )
LABEL_19:
      __fastfail(3u);
    *(_QWORD *)v10 = v12;
    *((_QWORD *)v10 + 1) = v11;
    *(_QWORD *)(v12 + 8) = v10;
    *(_QWORD *)v11 = v10;
    v8 = *(__int128 **)v8;
  }
  for ( i = (__int128 *)UnusedList; i != &UnusedList; i = *(__int128 **)i )
  {
    v14 = i - 1;
    v15 = &v4[16 * ((_DWORD)i[1] & v9)];
    v16 = *(_QWORD *)v15;
    if ( *(char **)(*(_QWORD *)v15 + 8LL) != v15 )
      goto LABEL_19;
    *(_QWORD *)v14 = v16;
    *((_QWORD *)v14 + 1) = v15;
    *(_QWORD *)(v16 + 8) = v14;
    *(_QWORD *)v15 = v14;
  }
  if ( pWinStationHashBuckets != &DefaultWinStationHashBuckets )
    HeapFree(hLibHeap, 0, pWinStationHashBuckets);
  NumWinStationHashBuckets = a1;
  WinStationHashMask = a1 - 1;
  pWinStationHashBuckets = v4;
}

```

## disassembly

```asm
0x180003314  push    rbx
0x180003316  push    rbp
0x180003317  push    rsi
0x180003318  push    rdi
0x180003319  sub     rsp, 28h
0x18000331d  mov     ebx, ecx
0x18000331f  lea     rbp, DefaultWinStationHashBuckets
0x180003326  cmp     ecx, 4
0x180003329  jz      short loc_180003358
0x18000332b  mov     rcx, cs:hLibHeap; hHeap
0x180003332  mov     r8d, ebx
0x180003335  shl     r8, 4; dwBytes
0x180003339  xor     edx, edx; dwFlags
0x18000333b  call    cs:__imp_HeapAlloc
0x180003341  xor     edx, edx
0x180003343  mov     rdi, rax
0x180003346  test    rax, rax
0x180003349  jz      loc_180003437
0x18000334f  mov     r8d, edx
0x180003352  test    ebx, ebx
0x180003354  jz      short loc_18000337C
0x180003356  jmp     short loc_180003360
0x180003358  xor     edx, edx
0x18000335a  mov     rdi, rbp
0x18000335d  mov     r8d, edx
0x180003360  mov     rcx, rdx
0x180003363  inc     r8d
0x180003366  shl     rcx, 4
0x18000336a  inc     rdx
0x18000336d  add     rcx, rdi
0x180003370  mov     [rcx+8], rcx
0x180003374  mov     [rcx], rcx
0x180003377  cmp     r8d, ebx
0x18000337a  jb      short loc_180003360
0x18000337c  mov     rdx, qword ptr cs:UsedList
0x180003383  lea     esi, [rbx-1]
0x180003386  lea     r9, UsedList
0x18000338d  jmp     short loc_1800033C1
0x18000338f  lea     r8, [rdx-10h]
0x180003393  mov     eax, esi
0x180003395  mov     ecx, [r8+20h]
0x180003399  and     rax, rcx
0x18000339c  shl     rax, 4
0x1800033a0  add     rax, rdi
0x1800033a3  mov     rcx, [rax]
0x1800033a6  cmp     [rcx+8], rax
0x1800033aa  jnz     loc_180003440
0x1800033b0  mov     [r8], rcx
0x1800033b3  mov     [r8+8], rax
0x1800033b7  mov     [rcx+8], r8
0x1800033bb  mov     [rax], r8
0x1800033be  mov     rdx, [rdx]
0x1800033c1  cmp     rdx, r9
0x1800033c4  jnz     short loc_18000338F
0x1800033c6  mov     rdx, qword ptr cs:UnusedList
0x1800033cd  lea     r9, UnusedList
0x1800033d4  jmp     short loc_180003404
0x1800033d6  lea     r8, [rdx-10h]
0x1800033da  mov     eax, esi
0x1800033dc  mov     ecx, [r8+20h]
0x1800033e0  and     rax, rcx
0x1800033e3  shl     rax, 4
0x1800033e7  add     rax, rdi
0x1800033ea  mov     rcx, [rax]
0x1800033ed  cmp     [rcx+8], rax
0x1800033f1  jnz     short loc_180003440
0x1800033f3  mov     [r8], rcx
0x1800033f6  mov     [r8+8], rax
0x1800033fa  mov     [rcx+8], r8
0x1800033fe  mov     [rax], r8
0x180003401  mov     rdx, [rdx]
0x180003404  cmp     rdx, r9
0x180003407  jnz     short loc_1800033D6
0x180003409  mov     r8, cs:pWinStationHashBuckets; lpMem
0x180003410  cmp     r8, rbp
0x180003413  jz      short loc_180003424
0x180003415  mov     rcx, cs:hLibHeap; hHeap
0x18000341c  xor     edx, edx; dwFlags
0x18000341e  call    cs:__imp_HeapFree
0x180003424  mov     cs:NumWinStationHashBuckets, ebx
0x18000342a  mov     cs:WinStationHashMask, esi
0x180003430  mov     cs:pWinStationHashBuckets, rdi
0x180003437  add     rsp, 28h
0x18000343b  pop     rdi
0x18000343c  pop     rsi
0x18000343d  pop     rbp
0x18000343e  pop     rbx
0x18000343f  retn
0x180003440  mov     ecx, 3
0x180003445  int     29h; Win8: RtlFailFast(ecx)
```

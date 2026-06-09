# PerflibciInsertRedBlackNode(PERFLIBCI_RED_BLACK_NODE * *,PERFLIBCI_RED_BLACK_NODE *)

- ea: `0x1800071b0`
- end: `0x1800072ca`
- name: `?PerflibciInsertRedBlackNode@@YAXPEAPEAUPERFLIBCI_RED_BLACK_NODE@@PEAU1@@Z`
- size: `282`
- prototype: `void __fastcall(struct PERFLIBCI_RED_BLACK_NODE **, struct PERFLIBCI_RED_BLACK_NODE *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180002dd0`
- `0x18000d534`
- `0x1800158e8`
- `0x180015b1c`

## callees

- `0x1800071b0`
- `0x18000db9c`
- `0x18000dbf0`

## pseudocode

```c
void __fastcall PerflibciInsertRedBlackNode(struct PERFLIBCI_RED_BLACK_NODE **a1, struct PERFLIBCI_RED_BLACK_NODE *a2)
{
  struct PERFLIBCI_RED_BLACK_NODE *v2; // r9
  struct PERFLIBCI_RED_BLACK_NODE **v3; // r10
  int v4; // r11d
  __int64 v5; // rdx
  __int64 *v6; // rcx
  __int64 v7; // rax

  v2 = a2;
  v3 = a1;
  if ( a2 && a1 && *a1 && a2 != *a1 )
  {
    v4 = 0;
    do
    {
      v5 = *((_QWORD *)v2 + 2);
      if ( !v5 )
        return;
      if ( *(_DWORD *)(v5 + 40) == v4 )
        return;
      v6 = *(__int64 **)(v5 + 16);
      if ( !v6 )
        return;
      v7 = *v6;
      if ( v5 == *v6 )
      {
        v7 = v6[1];
        if ( !v7 || *(_DWORD *)(v7 + 40) != 1 )
        {
          if ( v2 == *(struct PERFLIBCI_RED_BLACK_NODE **)(v5 + 8) )
            PerflibciRotateLeft(v3, v5);
          *(_DWORD *)(*((_QWORD *)v2 + 2) + 40LL) = v4;
          *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v2 + 2) + 16LL) + 40LL) = 1;
          PerflibciRotateRight(v3);
          continue;
        }
      }
      else if ( !v7 || *(_DWORD *)(v7 + 40) != 1 )
      {
        if ( v2 == *(struct PERFLIBCI_RED_BLACK_NODE **)v5 )
          PerflibciRotateRight(v3);
        *(_DWORD *)(*((_QWORD *)v2 + 2) + 40LL) = v4;
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v2 + 2) + 16LL) + 40LL) = 1;
        PerflibciRotateLeft(v3, *(_QWORD *)(*((_QWORD *)v2 + 2) + 16LL));
        continue;
      }
      *(_DWORD *)(v5 + 40) = v4;
      *(_DWORD *)(v7 + 40) = v4;
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v2 + 2) + 16LL) + 40LL) = 1;
      v2 = *(struct PERFLIBCI_RED_BLACK_NODE **)(*((_QWORD *)v2 + 2) + 16LL);
    }
    while ( v2 != *v3 );
  }
}

```

## disassembly

```asm
0x1800071b0  sub     rsp, 28h
0x1800071b4  mov     r9, rdx
0x1800071b7  mov     r10, rcx
0x1800071ba  test    rdx, rdx
0x1800071bd  jz      loc_1800072C5
0x1800071c3  test    rcx, rcx
0x1800071c6  jz      loc_1800072C5
0x1800071cc  mov     rax, [rcx]
0x1800071cf  test    rax, rax
0x1800071d2  jz      loc_1800072C5
0x1800071d8  cmp     rdx, rax
0x1800071db  jz      loc_1800072C5
0x1800071e1  xor     r11d, r11d
0x1800071e4  mov     rdx, [r9+10h]
0x1800071e8  test    rdx, rdx
0x1800071eb  jz      loc_1800072C5
0x1800071f1  cmp     [rdx+28h], r11d
0x1800071f5  jz      loc_1800072C5
0x1800071fb  mov     rcx, [rdx+10h]
0x1800071ff  test    rcx, rcx
0x180007202  jz      loc_1800072C5
0x180007208  mov     rax, [rcx]
0x18000720b  cmp     rdx, rax
0x18000720e  jnz     short loc_180007259
0x180007210  mov     rax, [rcx+8]
0x180007214  test    rax, rax
0x180007217  jz      short loc_18000721F
0x180007219  cmp     dword ptr [rax+28h], 1
0x18000721d  jz      short loc_180007264
0x18000721f  cmp     r9, [rdx+8]
0x180007223  jnz     short loc_180007230
0x180007225  mov     rcx, r10
0x180007228  mov     r9, rdx
0x18000722b  call    PerflibciRotateLeft
0x180007230  mov     rax, [r9+10h]
0x180007234  mov     [rax+28h], r11d
0x180007238  mov     rax, [r9+10h]
0x18000723c  mov     rcx, [rax+10h]
0x180007240  mov     dword ptr [rcx+28h], 1
0x180007247  mov     rcx, r10
0x18000724a  mov     rdx, [r9+10h]
0x18000724e  mov     rdx, [rdx+10h]
0x180007252  call    PerflibciRotateRight
0x180007257  jmp     short loc_1800072BC
0x180007259  test    rax, rax
0x18000725c  jz      short loc_180007285
0x18000725e  cmp     dword ptr [rax+28h], 1
0x180007262  jnz     short loc_180007285
0x180007264  mov     [rdx+28h], r11d
0x180007268  mov     [rax+28h], r11d
0x18000726c  mov     rax, [r9+10h]
0x180007270  mov     rcx, [rax+10h]
0x180007274  mov     dword ptr [rcx+28h], 1
0x18000727b  mov     rax, [r9+10h]
0x18000727f  mov     r9, [rax+10h]
0x180007283  jmp     short loc_1800072BC
0x180007285  cmp     r9, [rdx]
0x180007288  jnz     short loc_180007295
0x18000728a  mov     rcx, r10
0x18000728d  mov     r9, rdx
0x180007290  call    PerflibciRotateRight
0x180007295  mov     rax, [r9+10h]
0x180007299  mov     [rax+28h], r11d
0x18000729d  mov     rax, [r9+10h]
0x1800072a1  mov     rcx, [rax+10h]
0x1800072a5  mov     dword ptr [rcx+28h], 1
0x1800072ac  mov     rcx, r10
0x1800072af  mov     rdx, [r9+10h]
0x1800072b3  mov     rdx, [rdx+10h]
0x1800072b7  call    PerflibciRotateLeft
0x1800072bc  cmp     r9, [r10]
0x1800072bf  jnz     loc_1800071E4
0x1800072c5  add     rsp, 28h
0x1800072c9  retn
```

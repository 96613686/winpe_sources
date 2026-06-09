# ListView_CommonArrangeEx

- ea: `0x180073014`
- end: `0x1800733da`
- name: `ListView_CommonArrangeEx`
- size: `966`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180072fb4`

## callees

- `0x1800115f0`
- `0x180051a90`
- `0x180055a14`
- `0x18005643c`
- `0x18005bde8`
- `0x180073014`
- `0x180074114`
- `0x1800767ec`
- `0x18007697c`
- `0x180076f50`
- `0x180077108`

## import_xrefs

- `USER32!SetRectEmpty` at `0x180073169`
- `USER32!SetRectEmpty` at `0x180073169`
- `USER32!RedrawWindow` at `0x180073101`
- `USER32!RedrawWindow` at `0x180073101`
- `USER32!UnionRect` at `0x1800732c6`
- `USER32!UnionRect` at `0x1800732c6`
- `USER32!IntersectRect` at `0x18007321f`
- `USER32!IntersectRect` at `0x18007321f`

## pseudocode

```c
__int64 __fastcall ListView_CommonArrangeEx(__int64 a1, int a2, __int64 a3, int a4)
{
  __int64 v5; // rsi
  int v6; // edi
  int v7; // r15d
  unsigned int SlotCount; // r12d
  unsigned int v9; // esi
  int v10; // ecx
  __int64 v11; // rax
  unsigned int v12; // r13d
  int v13; // r14d
  __int64 v14; // rsi
  __int16 v15; // ax
  int v16; // ecx
  int v17; // r8d
  int left; // eax
  int v19; // eax
  int v20; // r8d
  __int64 v21; // rdx
  __int64 v22; // rax
  int NextItem; // eax
  int v25; // [rsp+40h] [rbp-99h]
  unsigned int v26; // [rsp+44h] [rbp-95h]
  struct tagRECT rc; // [rsp+58h] [rbp-81h] BYREF
  RECT rcSrc1; // [rsp+68h] [rbp-71h] BYREF
  RECT rcSrc2; // [rsp+78h] [rbp-61h] BYREF
  struct tagRECT rcDst; // [rsp+88h] [rbp-51h] BYREF
  RECT v33; // [rsp+98h] [rbp-41h] BYREF
  _DWORD v34[16]; // [rsp+B0h] [rbp-29h]

  v25 = *(_DWORD *)(a1 + 16) & 3;
  v5 = a3;
  rc = 0;
  rcSrc1 = 0;
  rcDst = 0;
  if ( !a2 && (*(_DWORD *)(a1 + 16) & 0x100) != 0 )
  {
    if ( *(int *)(a1 + 296) < 0 )
      *(_DWORD *)(a1 + 296) = 0;
    if ( *(int *)(a1 + 300) < 0 )
      *(_DWORD *)(a1 + 300) = 0;
  }
  if ( *(_DWORD *)(a1 + 296) || (v6 = 0, *(_DWORD *)(a1 + 300)) )
    v6 = 1;
  if ( (*(_DWORD *)(a1 + 16) & 0x1000) != 0 )
    goto LABEL_13;
  if ( a2 == 5 )
  {
    v6 |= ListView_SnapToGrid(a1, a3);
    goto LABEL_13;
  }
  v7 = 0;
  if ( *(int *)(a1 + 172) <= 0 )
  {
    SlotCount = ListView_GetSlotCountEx(a1, 1, 0xFFFFFFFFLL);
    v26 = SlotCount;
  }
  else
  {
    SlotCount = 0;
    v26 = 0;
    v9 = 0;
    do
    {
      v10 = ListView_GetSlotCountEx(a1, 1, v9);
      v11 = (int)v9++;
      v34[v11] = v10;
    }
    while ( (signed int)v9 < *(_DWORD *)(a1 + 172) );
    v5 = a3;
  }
  SetRectEmpty(&rc);
  v12 = 0;
  v13 = 0;
  if ( *(int *)(a1 + 512) <= 0 )
    goto LABEL_13;
  do
  {
    v33 = 0;
    rcSrc2 = 0;
    if ( v5 && v13 >= 0 && v13 < *(_DWORD *)v5 )
      v14 = *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8LL * v13);
    else
      v14 = 0;
    if ( *(__int16 *)(v14 + 26) == a4 )
    {
      if ( *(int *)(a1 + 172) > 0 )
        SlotCount = v34[*(__int16 *)(v14 + 26)];
      if ( (v25 & 0xFFFFFFFD) == 0 )
      {
        CalcSlotRect(a1, v14, v12, SlotCount, 0, &rcSrc1);
        while ( IntersectRect(&rcDst, &rcSrc1, &rc) )
          CalcSlotRect(a1, v14, ++v12, SlotCount, 0, &rcSrc1);
      }
      v6 |= ListView_SetIconPos(a1, v14, v12++, SlotCount);
      ListView_GetRectsFromItem(a1, &rcSrc2, &rc, 0);
      if ( v25 || (*(_BYTE *)(a1 + 16) & 3) != 0 || *(char *)(a1 + 72) >= 0 || (*(_BYTE *)(v14 + 28) & 1) == 0 )
        goto LABEL_45;
      v15 = *(_WORD *)(v14 + 24);
      if ( v15 >= *(__int16 *)(v14 + 22) )
        v15 = *(_WORD *)(v14 + 22);
      v17 = v15;
      v16 = *(_DWORD *)(a1 + 128);
      if ( v15 >= g_cyEdge + 2 * v16 )
        v17 = g_cyEdge + 2 * v16;
      rcSrc2.bottom = rcSrc2.top + v17;
      UnionRect(&rc, &v33, &rcSrc2);
      if ( !*(_QWORD *)(a1 + 480) || *(_WORD *)(v14 + 28) < 0x1000u )
      {
LABEL_45:
        left = rc.left;
      }
      else
      {
        left = rc.left - *(_DWORD *)(a1 + 488);
        rc.left = left;
      }
      if ( left < v7 )
        v7 = left;
    }
    v19 = *(_DWORD *)(a1 + 512);
    ++v13;
    v5 = a3;
    SlotCount = v26;
  }
  while ( v13 < v19 );
  if ( v7 >= 0 )
  {
LABEL_13:
    if ( !v6 )
      return 1;
    goto LABEL_14;
  }
  v20 = 0;
  if ( v19 > 0 )
  {
    do
    {
      v21 = v20++;
      v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL) + 8 * v21);
      *(_DWORD *)(v22 + 8) -= v7;
    }
    while ( v20 < *(_DWORD *)(a1 + 512) );
  }
  *(_DWORD *)(a1 + 304) = 0x7FFFFFFF;
LABEL_14:
  if ( (*(_BYTE *)(a1 + 72) & 0x12) == 0x12 )
  {
    RedrawWindow(*(HWND *)a1, 0, 0, 5u);
  }
  else
  {
    ListView_DeleteHrgnInval(a1);
    *(_DWORD *)(a1 + 72) |= 4u;
    *(_QWORD *)(a1 + 200) = 1;
  }
  NextItem = *(_DWORD *)(a1 + 144);
  if ( NextItem >= 0 || (NextItem = ListView_OnGetNextItem(a1, 0xFFFFFFFFLL, 2), NextItem >= 0) )
    ListView_OnEnsureVisible(a1, NextItem);
  if ( (*(_BYTE *)(a1 + 72) & 0x12) == 0x12 )
    ListView_UpdateScrollBars(a1);
  return 1;
}

```

## disassembly

```asm
0x180073014  mov     [rsp-8+arg_8], rbx
0x180073019  push    rbp
0x18007301a  push    rsi
0x18007301b  push    rdi
0x18007301c  push    r12
0x18007301e  push    r13
0x180073020  push    r14
0x180073022  push    r15
0x180073024  lea     rbp, [rsp-27h]
0x180073029  sub     rsp, 100h
0x180073030  mov     rax, cs:__security_cookie
0x180073037  xor     rax, rsp
0x18007303a  mov     [rbp+57h+var_40], rax
0x18007303e  mov     eax, [rcx+10h]
0x180073041  mov     rbx, rcx
0x180073044  and     eax, 3
0x180073047  mov     [rsp+130h+var_E8], r9d
0x18007304c  xor     r9d, r9d
0x18007304f  mov     [rsp+130h+var_E0], r8
0x180073054  cmp     eax, 2
0x180073057  mov     [rsp+130h+var_F0], eax
0x18007305b  mov     ecx, r9d
0x18007305e  xorps   xmm0, xmm0
0x180073061  setz    cl
0x180073064  xorps   xmm1, xmm1
0x180073067  mov     [rsp+130h+var_E4], ecx
0x18007306b  mov     rsi, r8
0x18007306e  movups  xmmword ptr [rsp+130h+rc.left], xmm0
0x180073073  movups  xmmword ptr [rbp+57h+rcSrc1.left], xmm1
0x180073077  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x18007307b  test    edx, edx
0x18007307d  jnz     short loc_1800730A8
0x18007307f  test    dword ptr [rbx+10h], 100h
0x180073086  jz      short loc_1800730A8
0x180073088  cmp     [rbx+128h], r9d
0x18007308f  jge     short loc_180073098
0x180073091  mov     [rbx+128h], r9d
0x180073098  cmp     [rbx+12Ch], r9d
0x18007309f  jge     short loc_1800730A8
0x1800730a1  mov     [rbx+12Ch], r9d
0x1800730a8  cmp     [rbx+128h], r9d
0x1800730af  jnz     short loc_1800730BD
0x1800730b1  mov     edi, r9d
0x1800730b4  cmp     [rbx+12Ch], r9d
0x1800730bb  jz      short loc_1800730C2
0x1800730bd  mov     edi, 1
0x1800730c2  test    dword ptr [rbx+10h], 1000h
0x1800730c9  jnz     short loc_1800730DD
0x1800730cb  cmp     edx, 5
0x1800730ce  jnz     short loc_18007310C
0x1800730d0  mov     rdx, r8
0x1800730d3  mov     rcx, rbx
0x1800730d6  call    ListView_SnapToGrid
0x1800730db  or      edi, eax
0x1800730dd  test    edi, edi
0x1800730df  jz      loc_1800733AE
0x1800730e5  mov     eax, [rbx+48h]
0x1800730e8  and     eax, 12h
0x1800730eb  cmp     al, 12h
0x1800730ed  jnz     loc_180073358
0x1800730f3  mov     rcx, [rbx]; hWnd
0x1800730f6  mov     r9d, 5; flags
0x1800730fc  xor     r8d, r8d; hrgnUpdate
0x1800730ff  xor     edx, edx; lprcUpdate
0x180073101  call    cs:__imp_RedrawWindow
0x180073107  jmp     loc_18007336F
0x18007310c  mov     r15d, r9d
0x18007310f  cmp     [rbx+0ACh], r9d
0x180073116  jle     short loc_18007314D
0x180073118  mov     r12d, r9d
0x18007311b  mov     [rsp+130h+var_EC], r9d
0x180073120  mov     esi, r9d
0x180073123  mov     r8d, esi
0x180073126  mov     edx, 1
0x18007312b  mov     rcx, rbx
0x18007312e  call    ListView_GetSlotCountEx
0x180073133  mov     ecx, eax
0x180073135  movsxd  rax, esi
0x180073138  inc     esi
0x18007313a  mov     [rbp+rax*4+57h+var_80], ecx
0x18007313e  cmp     esi, [rbx+0ACh]
0x180073144  jl      short loc_180073123
0x180073146  mov     rsi, [rsp+130h+var_E0]
0x18007314b  jmp     short loc_180073164
0x18007314d  or      r8d, 0FFFFFFFFh
0x180073151  mov     rcx, rbx
0x180073154  lea     edx, [r8+2]
0x180073158  call    ListView_GetSlotCountEx
0x18007315d  mov     r12d, eax
0x180073160  mov     [rsp+130h+var_EC], eax
0x180073164  lea     rcx, [rsp+130h+rc]; lprc
0x180073169  call    cs:__imp_SetRectEmpty
0x18007316f  xor     r9d, r9d
0x180073172  mov     r13d, r9d
0x180073175  mov     r14d, r9d
0x180073178  cmp     [rbx+200h], r9d
0x18007317f  jle     loc_1800730DD
0x180073185  xorps   xmm0, xmm0
0x180073188  xorps   xmm1, xmm1
0x18007318b  movups  xmmword ptr [rbp+57h+var_98.left], xmm0
0x18007318f  movups  xmmword ptr [rbp+57h+rcSrc2.left], xmm1
0x180073193  test    rsi, rsi
0x180073196  jz      short loc_1800731AF
0x180073198  test    r14d, r14d
0x18007319b  js      short loc_1800731AF
0x18007319d  cmp     r14d, [rsi]
0x1800731a0  jge     short loc_1800731AF
0x1800731a2  mov     rax, [rsi+8]
0x1800731a6  movsxd  rcx, r14d
0x1800731a9  mov     rsi, [rax+rcx*8]
0x1800731ad  jmp     short loc_1800731B2
0x1800731af  mov     rsi, r9
0x1800731b2  movsx   eax, word ptr [rsi+1Ah]
0x1800731b6  cmp     eax, [rsp+130h+var_E8]
0x1800731ba  jnz     loc_1800732FE
0x1800731c0  cmp     [rbx+0ACh], r9d
0x1800731c7  jle     short loc_1800731D3
0x1800731c9  movsx   rax, word ptr [rsi+1Ah]
0x1800731ce  mov     r12d, [rbp+rax*4+57h+var_80]
0x1800731d3  test    [rsp+130h+var_F0], 0FFFFFFFDh
0x1800731db  jnz     short loc_180073229
0x1800731dd  lea     rax, [rbp+57h+rcSrc1]
0x1800731e1  mov     [rsp+130h+lprc], rax
0x1800731e6  mov     dword ptr [rsp+130h+lprcSrc2], r9d
0x1800731eb  jmp     short loc_180073201
0x1800731ed  lea     rax, [rbp+57h+rcSrc1]
0x1800731f1  inc     r13d
0x1800731f4  mov     [rsp+130h+lprc], rax; lprc
0x1800731f9  mov     dword ptr [rsp+130h+lprcSrc2], 0; int
0x180073201  mov     r9d, r12d; int
0x180073204  mov     r8d, r13d; int
0x180073207  mov     rdx, rsi; int
0x18007320a  mov     rcx, rbx; int
0x18007320d  call    _CalcSlotRect
0x180073212  lea     r8, [rsp+130h+rc]; lprcSrc2
0x180073217  lea     rdx, [rbp+57h+rcSrc1]; lprcSrc1
0x18007321b  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18007321f  call    cs:__imp_IntersectRect
0x180073225  test    eax, eax
0x180073227  jnz     short loc_1800731ED
0x180073229  mov     r9d, r12d
0x18007322c  mov     r8d, r13d
0x18007322f  mov     rdx, rsi
0x180073232  mov     rcx, rbx
0x180073235  call    ListView_SetIconPos
0x18007323a  mov     edx, [rsp+130h+var_E4]
0x18007323e  lea     r9, [rbp+57h+var_98]
0x180073242  or      edi, eax
0x180073244  mov     [rsp+130h+var_100], 0; LPRECT
0x18007324d  lea     rax, [rsp+130h+rc]
0x180073252  mov     r8, rsi
0x180073255  mov     [rsp+130h+lprc], rax; lprcDst
0x18007325a  mov     rcx, rbx; int
0x18007325d  lea     rax, [rbp+57h+rcSrc2]
0x180073261  inc     r13d
0x180073264  mov     [rsp+130h+lprcSrc2], rax; lprcSrc2
0x180073269  call    _ListView_GetRectsFromItem
0x18007326e  xor     r9d, r9d
0x180073271  cmp     [rsp+130h+var_F0], r9d
0x180073276  jnz     short loc_1800732F3
0x180073278  test    byte ptr [rbx+10h], 3
0x18007327c  jnz     short loc_1800732F3
0x18007327e  test    byte ptr [rbx+48h], 80h
0x180073282  jz      short loc_1800732F3
0x180073284  test    byte ptr [rsi+1Ch], 1
0x180073288  jz      short loc_1800732F3
0x18007328a  movzx   eax, word ptr [rsi+18h]
0x18007328e  cmp     ax, [rsi+16h]
0x180073292  mov     ecx, [rbx+80h]
0x180073298  cmovge  ax, [rsi+16h]
0x18007329d  movsx   r8d, ax
0x1800732a1  mov     eax, cs:g_cyEdge
0x1800732a7  lea     edx, [rax+rcx*2]
0x1800732aa  cmp     r8d, edx
0x1800732ad  lea     rcx, [rsp+130h+rc]; lprcDst
0x1800732b2  cmovge  r8d, edx
0x1800732b6  lea     rdx, [rbp+57h+var_98]; lprcSrc1
0x1800732ba  add     r8d, [rbp+57h+rcSrc2.top]
0x1800732be  mov     [rbp+57h+rcSrc2.bottom], r8d
0x1800732c2  lea     r8, [rbp+57h+rcSrc2]; lprcSrc2
0x1800732c6  call    cs:__imp_UnionRect
0x1800732cc  xor     r9d, r9d
0x1800732cf  cmp     [rbx+1E0h], r9
0x1800732d6  jz      short loc_1800732F3
0x1800732d8  mov     eax, 1000h
0x1800732dd  cmp     [rsi+1Ch], ax
0x1800732e1  jb      short loc_1800732F3
0x1800732e3  mov     eax, [rsp+130h+rc.left]
0x1800732e7  sub     eax, [rbx+1E8h]
0x1800732ed  mov     [rsp+130h+rc.left], eax
0x1800732f1  jmp     short loc_1800732F7
0x1800732f3  mov     eax, [rsp+130h+rc.left]
0x1800732f7  cmp     eax, r15d
0x1800732fa  cmovl   r15d, eax
0x1800732fe  mov     eax, [rbx+200h]
0x180073304  inc     r14d
0x180073307  mov     rsi, [rsp+130h+var_E0]
0x18007330c  mov     r12d, [rsp+130h+var_EC]
0x180073311  cmp     r14d, eax
0x180073314  jl      loc_180073185
0x18007331a  test    r15d, r15d
0x18007331d  jns     loc_1800730DD
0x180073323  mov     r8d, r9d
0x180073326  test    eax, eax
0x180073328  jle     short loc_180073349
0x18007332a  mov     rax, [rbx+40h]
0x18007332e  movsxd  rdx, r8d
0x180073331  inc     r8d
0x180073334  mov     rcx, [rax+8]
0x180073338  mov     rax, [rcx+rdx*8]
0x18007333c  sub     [rax+8], r15d
0x180073340  cmp     r8d, [rbx+200h]
0x180073347  jl      short loc_18007332A
0x180073349  mov     dword ptr [rbx+130h], 7FFFFFFFh
0x180073353  jmp     loc_1800730E5
0x180073358  mov     rcx, rbx
0x18007335b  call    ListView_DeleteHrgnInval
0x180073360  or      dword ptr [rbx+48h], 4
0x180073364  mov     qword ptr [rbx+0C8h], 1
0x18007336f  mov     eax, [rbx+90h]
0x180073375  test    eax, eax
0x180073377  jns     short loc_18007338E
0x180073379  mov     r8d, 2
0x18007337f  or      edx, 0FFFFFFFFh
0x180073382  mov     rcx, rbx
0x180073385  call    ListView_OnGetNextItem
0x18007338a  test    eax, eax
0x18007338c  js      short loc_18007339B
0x18007338e  xor     r8d, r8d
0x180073391  mov     edx, eax; int
0x180073393  mov     rcx, rbx; int
0x180073396  call    ListView_OnEnsureVisible
0x18007339b  mov     edx, [rbx+48h]
0x18007339e  and     edx, 12h
0x1800733a1  cmp     dl, 12h
0x1800733a4  jnz     short loc_1800733AE
0x1800733a6  mov     rcx, rbx
0x1800733a9  call    ListView_UpdateScrollBars
0x1800733ae  mov     eax, 1
0x1800733b3  mov     rcx, [rbp+57h+var_40]
0x1800733b7  xor     rcx, rsp; StackCookie
0x1800733ba  call    __security_check_cookie
0x1800733bf  mov     rbx, [rsp+130h+arg_8]
0x1800733c7  add     rsp, 100h
0x1800733ce  pop     r15
0x1800733d0  pop     r14
0x1800733d2  pop     r13
0x1800733d4  pop     r12
0x1800733d6  pop     rdi
0x1800733d7  pop     rsi
0x1800733d8  pop     rbp
0x1800733d9  retn
```

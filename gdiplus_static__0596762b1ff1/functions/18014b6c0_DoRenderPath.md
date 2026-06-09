# DoRenderPath

- ea: `0x18014b6c0`
- end: `0x18014bb37`
- name: `DoRenderPath`
- size: `1143`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: ``

## callers

- `0x1800c8310`
- `0x180147c40`
- `0x180148be0`
- `0x180148c00`
- `0x18014b3a4`

## callees

- `0x1800b4fa4`
- `0x1800c7f84`
- `0x1800c807c`
- `0x1800f80dc`
- `0x1801470b8`
- `0x18014b570`
- `0x18014b6c0`
- `0x18014bf40`
- `0x18014c074`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014b796`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014b817`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014b796`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014b817`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014bae6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014bafa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014bb0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014bae6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014bafa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014bb0f`
- `GDI32!GetPath` at `0x18014b75a`
- `GDI32!GetPath` at `0x18014b7ca`
- `GDI32!GetPath` at `0x18014b75a`
- `GDI32!GetPath` at `0x18014b7ca`
- `GDI32!AbortPath` at `0x18014bad2`
- `GDI32!AbortPath` at `0x18014bad2`
- `GDI32!FlattenPath` at `0x18014b73a`
- `GDI32!FlattenPath` at `0x18014b73a`
- `GDI32!SetROP2` at `0x18014b9a7`
- `GDI32!SetROP2` at `0x18014b9ff`
- `GDI32!SetROP2` at `0x18014b9a7`
- `GDI32!SetROP2` at `0x18014b9ff`

## pseudocode

```c
__int64 __fastcall DoRenderPath(__int64 a1, int a2, int a3)
{
  struct tagPOINT *v3; // r13
  unsigned int v4; // r15d
  _QWORD *v6; // r14
  __int64 v7; // rdi
  int Path; // eax
  struct tagPOINT *v9; // rax
  HDC v10; // rcx
  ULONGLONG v11; // rsi
  char *v12; // rax
  _QWORD *v13; // r9
  char *v14; // rdx
  char *v15; // rax
  unsigned int v16; // esi
  __int64 v17; // r8
  int v18; // r12d
  unsigned int v19; // r10d
  unsigned int v20; // r11d
  ULONGLONG v21; // r15
  char *v22; // r10
  __int64 v23; // rdx
  __int64 v24; // rcx
  char v25; // al
  unsigned int v26; // ecx
  ULONGLONG v27; // rax
  int v28; // edi
  int v29; // eax
  unsigned int v30; // edi
  __int64 v31; // r8
  __int64 v32; // r9
  int v34; // [rsp+30h] [rbp-30h]
  char *v35; // [rsp+38h] [rbp-28h]
  ULONGLONG uBytes; // [rsp+40h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-18h] BYREF
  _QWORD *v38; // [rsp+50h] [rbp-10h]
  char *v39; // [rsp+58h] [rbp-8h]
  ULONGLONG pullResult; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 0;
  v4 = 0;
  hMem = 0;
  LODWORD(pullResult) = 0;
  v6 = 0;
  if ( (unsigned int)GdipFlattenGdiPath(a1, &hMem, &pullResult) )
  {
    LODWORD(v7) = pullResult;
    if ( !(_DWORD)pullResult )
    {
LABEL_3:
      v4 = 1;
      goto LABEL_49;
    }
    v38 = hMem;
    v34 = 0;
    pullResult = (ULONGLONG)hMem + 8 * (int)pullResult;
  }
  else
  {
    if ( !FlattenPath(*(HDC *)(a1 + 40)) )
      goto LABEL_49;
    Path = GetPath(*(HDC *)(a1 + 40), 0, 0, 0);
    v7 = Path;
    if ( Path < 0 )
      goto LABEL_49;
    if ( !Path )
      goto LABEL_3;
    pullResult = 0;
    if ( ULongLongMult(9u, Path, &pullResult) < 0
      || (v9 = (struct tagPOINT *)LocalAlloc(0, pullResult), (v3 = v9) == 0)
      || (v10 = *(HDC *)(a1 + 40),
          pullResult = (ULONGLONG)&v9[v7],
          GetPath(v10, v9, (LPBYTE)pullResult, v7) != (_DWORD)v7) )
    {
LABEL_49:
      if ( !a3 )
        goto LABEL_50;
      goto LABEL_51;
    }
    v34 = 1;
    v38 = v3;
  }
  uBytes = 0;
  v11 = (int)v7 + (int)v7 / 2;
  if ( ULongLongMult(0xDu, v11, &uBytes) < 0 )
    goto LABEL_49;
  v12 = (char *)LocalAlloc(0, uBytes);
  v6 = v12;
  if ( !v12 )
    goto LABEL_49;
  v13 = v38;
  v14 = &v12[8 * v11];
  v15 = &v14[4 * v11];
  v35 = v14;
  v16 = 0;
  v39 = v15;
  v17 = 0;
  v18 = 0;
  while ( (int)v17 < (int)v7 )
  {
    v19 = v16;
    v20 = v16;
    uBytes = (int)v16;
    v39[v16] = *(_BYTE *)((int)v17 + pullResult);
    v4 = 0;
    v6[v16] = v13[(int)v17];
    LODWORD(v14) = (_DWORD)v35;
    v17 = (unsigned int)(v17 + 1);
    ++v16;
    if ( (int)v17 >= (int)v7 )
    {
      v16 = v19;
      break;
    }
    v21 = pullResult;
    v22 = v39;
    do
    {
      if ( (int)v17 >= (int)v7 )
        break;
      v23 = (int)v16;
      v22[v16] = *(_BYTE *)((int)v17 + v21);
      v6[v16] = v13[(int)v17];
      v17 = (unsigned int)(v17 + 1);
      ++v16;
    }
    while ( v22[v23] == 2 );
    v4 = 0;
    LODWORD(v14) = (_DWORD)v35;
    v24 = (int)v16;
    v25 = v22[v16 - 1];
    switch ( v25 )
    {
      case 6:
        --v16;
        v17 = (unsigned int)(v17 - 1);
        v26 = v16 - v20;
        if ( v16 - v20 != 1 )
          goto LABEL_26;
        v16 = v20;
        break;
      case 2:
        *(_DWORD *)&v35[4 * v18++] = v16 - v20;
        goto LABEL_29;
      case 3:
        v27 = uBytes;
        ++v16;
        *(_WORD *)&v22[v24 - 1] = 514;
        v6[v24] = v6[v27];
        v26 = v16 - v20;
LABEL_26:
        *(_DWORD *)&v35[4 * v18++] = v26;
        break;
    }
  }
LABEL_29:
  if ( !v16 )
  {
    v4 = 1;
    goto LABEL_49;
  }
  if ( a2 == 64 && !a3 )
  {
    v4 = DoPolyPolyline(a1, (_DWORD)v6, (_DWORD)v14, v18, v34);
    goto LABEL_50;
  }
  if ( *(_DWORD *)(a1 + 484) != 3 && !a3 )
  {
LABEL_41:
    v30 = 0;
    if ( a2 != 62 || (v30 = *(_DWORD *)(a1 + 436), (unsigned int)DoSelectObject(a1, 2147483656LL, v17, v13)) )
    {
      v4 = DoPolyPolygon(a1, v6, v35, v16, v18, v34);
      if ( a2 == 62 )
        DoSelectObject(a1, v30, v31, v32);
      v29 = a3;
      goto LABEL_46;
    }
    goto LABEL_49;
  }
  v28 = SetROP2(*(HDC *)(a1 + 40), 11);
  if ( !(unsigned int)bW16Emit1(a1, 260, 11) )
    goto LABEL_49;
  v4 = ConvertPolyPolygonToPolygons(a1, v6, v35, v16, v18, v34);
  if ( !v4 )
    goto LABEL_49;
  SetROP2(*(HDC *)(a1 + 40), v28);
  if ( !(unsigned int)bW16Emit1(a1, 260, (unsigned __int16)v28) )
    goto LABEL_49;
  LOWORD(pullResult) = 1;
  if ( !(unsigned int)bEmitWin16Escape(a1, 38, 2, &pullResult) )
    goto LABEL_49;
  v29 = a3;
  if ( !a3 )
    goto LABEL_41;
LABEL_46:
  if ( *(_DWORD *)(a1 + 484) == 3 || v29 )
  {
    LOWORD(pullResult) = 0;
    bEmitWin16Escape(a1, 38, 2, &pullResult);
    goto LABEL_49;
  }
LABEL_50:
  AbortPath(*(HDC *)(a1 + 40));
LABEL_51:
  if ( v6 )
    LocalFree(v6);
  if ( v3 )
    LocalFree(v3);
  if ( hMem )
    LocalFree(hMem);
  return v4;
}

```

## disassembly

```asm
0x18014b6c0  mov     [rsp-38h+arg_0], rbx
0x18014b6c5  mov     [rsp-38h+arg_10], r8d
0x18014b6ca  mov     [rsp-38h+arg_8], edx
0x18014b6ce  push    rbp
0x18014b6cf  push    rsi
0x18014b6d0  push    rdi
0x18014b6d1  push    r12
0x18014b6d3  push    r13
0x18014b6d5  push    r14
0x18014b6d7  push    r15
0x18014b6d9  mov     rbp, rsp
0x18014b6dc  sub     rsp, 60h
0x18014b6e0  xor     r13d, r13d
0x18014b6e3  lea     r8, [rbp+pullResult]
0x18014b6e7  xor     r15d, r15d
0x18014b6ea  mov     [rbp+hMem], r13
0x18014b6ee  lea     rdx, [rbp+hMem]
0x18014b6f2  mov     dword ptr [rbp+pullResult], r13d
0x18014b6f6  mov     [rbp+var_2C], r15d
0x18014b6fa  mov     rbx, rcx
0x18014b6fd  xor     r14d, r14d
0x18014b700  call    GdipFlattenGdiPath
0x18014b705  lea     esi, [r13+1]
0x18014b709  test    eax, eax
0x18014b70b  jz      short loc_18014B736
0x18014b70d  movsxd  rdi, dword ptr [rbp+pullResult]
0x18014b711  test    edi, edi
0x18014b713  jnz     short loc_18014B71D
0x18014b715  mov     r15d, esi
0x18014b718  jmp     loc_18014BAC8
0x18014b71d  mov     r9, [rbp+hMem]
0x18014b721  mov     [rbp+var_10], r9
0x18014b725  mov     [rbp+var_30], r13d
0x18014b729  lea     rax, [r9+rdi*8]
0x18014b72d  mov     [rbp+pullResult], rax
0x18014b731  jmp     loc_18014B7E5
0x18014b736  mov     rcx, [rbx+28h]; hdc
0x18014b73a  call    cs:__imp_FlattenPath
0x18014b741  nop     dword ptr [rax+rax+00h]
0x18014b746  test    eax, eax
0x18014b748  jz      loc_18014BAC8
0x18014b74e  mov     rcx, [rbx+28h]; hdc
0x18014b752  xor     r9d, r9d; cpt
0x18014b755  xor     r8d, r8d; aj
0x18014b758  xor     edx, edx; apt
0x18014b75a  call    cs:__imp_GetPath
0x18014b761  nop     dword ptr [rax+rax+00h]
0x18014b766  movsxd  rdi, eax
0x18014b769  test    eax, eax
0x18014b76b  js      loc_18014BAC8
0x18014b771  jz      short loc_18014B715
0x18014b773  lea     r8, [rbp+pullResult]; pullResult
0x18014b777  mov     [rbp+pullResult], r13
0x18014b77b  mov     rdx, rdi; ullMultiplier
0x18014b77e  mov     ecx, 9; ullMultiplicand
0x18014b783  call    ULongLongMult
0x18014b788  test    eax, eax
0x18014b78a  js      loc_18014BAC8
0x18014b790  mov     rdx, [rbp+pullResult]; uBytes
0x18014b794  xor     ecx, ecx; uFlags
0x18014b796  call    cs:__imp_LocalAlloc
0x18014b79d  nop     dword ptr [rax+rax+00h]
0x18014b7a2  mov     r13, rax
0x18014b7a5  test    rax, rax
0x18014b7a8  jz      loc_18014BAC8
0x18014b7ae  mov     rcx, [rbx+28h]; hdc
0x18014b7b2  lea     r12, ds:0[rdi*8]
0x18014b7ba  add     r12, rax
0x18014b7bd  mov     r9d, edi; cpt
0x18014b7c0  mov     r8, r12; aj
0x18014b7c3  mov     [rbp+pullResult], r12
0x18014b7c7  mov     rdx, rax; apt
0x18014b7ca  call    cs:__imp_GetPath
0x18014b7d1  nop     dword ptr [rax+rax+00h]
0x18014b7d6  cmp     eax, edi
0x18014b7d8  jnz     loc_18014BAC8
0x18014b7de  mov     [rbp+var_30], esi
0x18014b7e1  mov     [rbp+var_10], r13
0x18014b7e5  mov     eax, edi
0x18014b7e7  mov     [rbp+uBytes], r14
0x18014b7eb  cdq
0x18014b7ec  lea     r8, [rbp+uBytes]; pullResult
0x18014b7f0  mov     ecx, 2
0x18014b7f5  idiv    ecx
0x18014b7f7  mov     ecx, 0Dh; ullMultiplicand
0x18014b7fc  add     eax, edi
0x18014b7fe  movsxd  rsi, eax
0x18014b801  mov     rdx, rsi; ullMultiplier
0x18014b804  call    ULongLongMult
0x18014b809  test    eax, eax
0x18014b80b  js      loc_18014BAC8
0x18014b811  mov     rdx, [rbp+uBytes]; uBytes
0x18014b815  xor     ecx, ecx; uFlags
0x18014b817  call    cs:__imp_LocalAlloc
0x18014b81e  nop     dword ptr [rax+rax+00h]
0x18014b823  mov     r14, rax
0x18014b826  test    rax, rax
0x18014b829  jz      loc_18014BAC8
0x18014b82f  mov     r9, [rbp+var_10]
0x18014b833  lea     rdx, [rax+rsi*8]
0x18014b837  lea     rax, [rdx+rsi*4]
0x18014b83b  mov     [rbp+var_28], rdx
0x18014b83f  xor     esi, esi
0x18014b841  mov     [rbp+var_8], rax
0x18014b845  xor     r8d, r8d
0x18014b848  xor     r12d, r12d
0x18014b84b  mov     eax, 1
0x18014b850  cmp     r8d, edi
0x18014b853  jge     loc_18014B954
0x18014b859  mov     r15, [rbp+var_8]
0x18014b85d  mov     r10d, esi
0x18014b860  movsxd  rax, esi
0x18014b863  mov     r11d, esi
0x18014b866  mov     [rbp+uBytes], rax
0x18014b86a  mov     rdx, [rbp+uBytes]
0x18014b86e  mov     rax, [rbp+pullResult]
0x18014b872  movsxd  rcx, r8d
0x18014b875  mov     al, [rcx+rax]
0x18014b878  mov     [rdx+r15], al
0x18014b87c  mov     rax, [r9+rcx*8]
0x18014b880  mov     r15d, [rbp+var_2C]
0x18014b884  mov     [r14+rdx*8], rax
0x18014b888  mov     eax, 1
0x18014b88d  mov     rdx, [rbp+var_28]
0x18014b891  add     r8d, eax
0x18014b894  add     esi, eax
0x18014b896  cmp     r8d, edi
0x18014b899  jge     loc_18014B951
0x18014b89f  mov     r15, [rbp+pullResult]
0x18014b8a3  mov     r10, [rbp+var_8]
0x18014b8a7  cmp     r8d, edi
0x18014b8aa  jge     short loc_18014B8D3
0x18014b8ac  movsxd  rdx, esi
0x18014b8af  movsxd  rcx, r8d
0x18014b8b2  mov     al, [rcx+r15]
0x18014b8b6  mov     [rdx+r10], al
0x18014b8ba  mov     rax, [r9+rcx*8]
0x18014b8be  mov     [r14+rdx*8], rax
0x18014b8c2  mov     eax, 1
0x18014b8c7  add     r8d, eax
0x18014b8ca  add     esi, eax
0x18014b8cc  cmp     byte ptr [rdx+r10], 2
0x18014b8d1  jz      short loc_18014B8A7
0x18014b8d3  mov     r15d, [rbp+var_2C]
0x18014b8d7  mov     rdx, [rbp+var_28]
0x18014b8db  movsxd  rcx, esi
0x18014b8de  mov     al, [rcx+r10-1]
0x18014b8e3  cmp     al, 6
0x18014b8e5  jnz     short loc_18014B902
0x18014b8e7  dec     esi
0x18014b8e9  mov     eax, 1
0x18014b8ee  mov     ecx, esi
0x18014b8f0  sub     r8d, eax
0x18014b8f3  sub     ecx, r11d
0x18014b8f6  cmp     ecx, eax
0x18014b8f8  jnz     short loc_18014B929
0x18014b8fa  mov     esi, r11d
0x18014b8fd  jmp     loc_18014B850
0x18014b902  cmp     al, 2
0x18014b904  jz      short loc_18014B93C
0x18014b906  cmp     al, 3
0x18014b908  jnz     loc_18014B84B
0x18014b90e  mov     rax, [rbp+uBytes]
0x18014b912  inc     esi
0x18014b914  mov     word ptr [rcx+r10-1], 202h
0x18014b91c  mov     rax, [r14+rax*8]
0x18014b920  mov     [r14+rcx*8], rax
0x18014b924  mov     ecx, esi
0x18014b926  sub     ecx, r11d
0x18014b929  movsxd  rax, r12d
0x18014b92c  mov     [rdx+rax*4], ecx
0x18014b92f  mov     eax, 1
0x18014b934  add     r12d, eax
0x18014b937  jmp     loc_18014B850
0x18014b93c  movsxd  rax, r12d
0x18014b93f  mov     ecx, esi
0x18014b941  sub     ecx, r11d
0x18014b944  mov     [rdx+rax*4], ecx
0x18014b947  mov     eax, 1
0x18014b94c  add     r12d, eax
0x18014b94f  jmp     short loc_18014B954
0x18014b951  mov     esi, r10d
0x18014b954  test    esi, esi
0x18014b956  jnz     short loc_18014B960
0x18014b958  mov     r15d, eax
0x18014b95b  jmp     loc_18014BAC8
0x18014b960  cmp     [rbp+arg_8], 40h ; '@'
0x18014b964  mov     eax, [rbp+arg_10]
0x18014b967  jnz     short loc_18014B98D
0x18014b969  test    eax, eax
0x18014b96b  jnz     short loc_18014B98D
0x18014b96d  mov     eax, [rbp+var_30]
0x18014b970  mov     r8, rdx
0x18014b973  mov     rdx, r14
0x18014b976  mov     [rsp+60h+var_40], eax
0x18014b97a  mov     r9d, r12d
0x18014b97d  mov     rcx, rbx
0x18014b980  call    DoPolyPolyline
0x18014b985  mov     r15d, eax
0x18014b988  jmp     loc_18014BACE
0x18014b98d  cmp     dword ptr [rbx+1E4h], 3
0x18014b994  jz      short loc_18014B99E
0x18014b996  test    eax, eax
0x18014b998  jz      loc_18014BA4F
0x18014b99e  mov     rcx, [rbx+28h]; hdc
0x18014b9a2  mov     edx, 0Bh; rop2
0x18014b9a7  call    cs:__imp_SetROP2
0x18014b9ae  nop     dword ptr [rax+rax+00h]
0x18014b9b3  mov     edx, 104h
0x18014b9b8  mov     r8d, 0Bh
0x18014b9be  mov     rcx, rbx
0x18014b9c1  mov     edi, eax
0x18014b9c3  call    bW16Emit1
0x18014b9c8  test    eax, eax
0x18014b9ca  jz      loc_18014BAC8
0x18014b9d0  mov     eax, [rbp+var_30]
0x18014b9d3  mov     r9d, esi
0x18014b9d6  mov     r8, [rbp+var_28]
0x18014b9da  mov     rdx, r14
0x18014b9dd  mov     [rsp+60h+var_38], eax
0x18014b9e1  mov     rcx, rbx
0x18014b9e4  mov     [rsp+60h+var_40], r12d
0x18014b9e9  call    ConvertPolyPolygonToPolygons
0x18014b9ee  mov     r15d, eax
0x18014b9f1  test    eax, eax
0x18014b9f3  jz      loc_18014BAC8
0x18014b9f9  mov     rcx, [rbx+28h]; hdc
0x18014b9fd  mov     edx, edi; rop2
0x18014b9ff  call    cs:__imp_SetROP2
0x18014ba06  nop     dword ptr [rax+rax+00h]
0x18014ba0b  movzx   r8d, di
0x18014ba0f  mov     edx, 104h
0x18014ba14  mov     rcx, rbx
0x18014ba17  call    bW16Emit1
0x18014ba1c  test    eax, eax
0x18014ba1e  jz      loc_18014BAC8
0x18014ba24  mov     eax, 1
0x18014ba29  lea     r9, [rbp+pullResult]
0x18014ba2d  mov     rcx, rbx
0x18014ba30  mov     word ptr [rbp+pullResult], ax
0x18014ba34  lea     edx, [rax+25h]
0x18014ba37  lea     r8d, [rax+1]
0x18014ba3b  call    bEmitWin16Escape
0x18014ba40  test    eax, eax
0x18014ba42  jz      loc_18014BAC8
0x18014ba48  mov     eax, [rbp+arg_10]
0x18014ba4b  test    eax, eax
0x18014ba4d  jnz     short loc_18014BAA2
0x18014ba4f  xor     edi, edi
0x18014ba51  cmp     [rbp+arg_8], 3Eh ; '>'
0x18014ba55  jnz     short loc_18014BA6E
0x18014ba57  mov     edi, [rbx+1B4h]
0x18014ba5d  mov     edx, 80000008h
0x18014ba62  mov     rcx, rbx
0x18014ba65  call    DoSelectObject
0x18014ba6a  test    eax, eax
0x18014ba6c  jz      short loc_18014BAC8
0x18014ba6e  mov     eax, [rbp+var_30]
0x18014ba71  mov     r9d, esi
0x18014ba74  mov     r8, [rbp+var_28]
0x18014ba78  mov     rdx, r14
0x18014ba7b  mov     [rsp+60h+var_38], eax
0x18014ba7f  mov     rcx, rbx
0x18014ba82  mov     [rsp+60h+var_40], r12d
0x18014ba87  call    DoPolyPolygon
0x18014ba8c  cmp     [rbp+arg_8], 3Eh ; '>'
0x18014ba90  mov     r15d, eax
0x18014ba93  jnz     short loc_18014BA9F
0x18014ba95  mov     edx, edi
0x18014ba97  mov     rcx, rbx
0x18014ba9a  call    DoSelectObject
0x18014ba9f  mov     eax, [rbp+arg_10]
0x18014baa2  cmp     dword ptr [rbx+1E4h], 3
0x18014baa9  jz      short loc_18014BAAF
0x18014baab  test    eax, eax
0x18014baad  jz      short loc_18014BACE
0x18014baaf  xor     eax, eax
0x18014bab1  lea     r9, [rbp+pullResult]
0x18014bab5  mov     rcx, rbx
0x18014bab8  mov     word ptr [rbp+pullResult], ax
0x18014babc  lea     edx, [rax+26h]
0x18014babf  lea     r8d, [rax+2]
0x18014bac3  call    bEmitWin16Escape
0x18014bac8  cmp     [rbp+arg_10], 0
0x18014bacc  jnz     short loc_18014BADE
0x18014bace  mov     rcx, [rbx+28h]; hdc
0x18014bad2  call    cs:__imp_AbortPath
0x18014bad9  nop     dword ptr [rax+rax+00h]
0x18014bade  test    r14, r14
0x18014bae1  jz      short loc_18014BAF2
0x18014bae3  mov     rcx, r14; hMem
0x18014bae6  call    cs:__imp_LocalFree
0x18014baed  nop     dword ptr [rax+rax+00h]
0x18014baf2  test    r13, r13
0x18014baf5  jz      short loc_18014BB06
0x18014baf7  mov     rcx, r13; hMem
0x18014bafa  call    cs:__imp_LocalFree
0x18014bb01  nop     dword ptr [rax+rax+00h]
0x18014bb06  mov     rcx, [rbp+hMem]; hMem
0x18014bb0a  test    rcx, rcx
  ... truncated ...
```

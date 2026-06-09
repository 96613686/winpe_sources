# DoRenderPath

- ea: `0x1801456fc`
- end: `0x180145bef`
- name: `DoRenderPath`
- size: `1267`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: ``

## callers

- `0x1800b2424`
- `0x18013fbf0`
- `0x1801414b0`
- `0x1801414d0`
- `0x1801453c0`

## callees

- `0x18008ef00`
- `0x1800b2080`
- `0x1800b2190`
- `0x1800e7838`
- `0x18013ec88`
- `0x1801455a0`
- `0x1801456fc`
- `0x180145fec`
- `0x18014616c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801457e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014586e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801457e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014586e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180145a24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180145a38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180145a4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180145a24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180145a38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180145a4d`
- `GDI32!GetPath` at `0x1801457ad`
- `GDI32!GetPath` at `0x180145825`
- `GDI32!GetPath` at `0x1801457ad`
- `GDI32!GetPath` at `0x180145825`
- `GDI32!AbortPath` at `0x180145a10`
- `GDI32!AbortPath` at `0x180145a10`
- `GDI32!FlattenPath` at `0x18014578d`
- `GDI32!FlattenPath` at `0x18014578d`
- `GDI32!SetROP2` at `0x180145aba`
- `GDI32!SetROP2` at `0x180145b12`
- `GDI32!SetROP2` at `0x180145aba`
- `GDI32!SetROP2` at `0x180145b12`

## pseudocode

```c
__int64 __fastcall DoRenderPath(__int64 a1, int a2, int a3)
{
  __int64 v3; // rbx
  struct tagPOINT *v4; // r13
  _QWORD *v5; // r14
  unsigned int v6; // r15d
  __int64 v7; // rdi
  int v8; // r12d
  int Path; // eax
  struct tagPOINT *v10; // rax
  HDC v11; // rcx
  ULONGLONG v12; // rsi
  char *v13; // rax
  _QWORD *v14; // r11
  __int64 v15; // rdx
  unsigned int v16; // esi
  char *v17; // r10
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // r9d
  ULONGLONG v21; // rdi
  ULONGLONG v22; // r15
  _BYTE *v23; // r8
  __int64 v24; // rbx
  _QWORD *v25; // rdi
  char v26; // al
  ULONGLONG v27; // rax
  int v28; // edx
  int v30; // edi
  int v31; // edi
  int v32; // eax
  __int64 v33; // r8
  int v34; // [rsp+38h] [rbp-39h]
  ULONGLONG uBytes; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v36; // [rsp+48h] [rbp-29h]
  unsigned int v37; // [rsp+4Ch] [rbp-25h]
  char *v38; // [rsp+50h] [rbp-21h]
  _QWORD *v39; // [rsp+58h] [rbp-19h]
  __int64 v40; // [rsp+60h] [rbp-11h]
  HLOCAL hMem; // [rsp+68h] [rbp-9h] BYREF
  struct tagPOINT *v42; // [rsp+70h] [rbp-1h]
  _BYTE *v43; // [rsp+78h] [rbp+7h]
  __int64 v44; // [rsp+80h] [rbp+Fh]
  ULONGLONG pullResult; // [rsp+F0h] [rbp+7Fh] BYREF

  v42 = 0;
  v3 = a1;
  v37 = 0;
  v4 = 0;
  hMem = 0;
  LODWORD(pullResult) = 0;
  v34 = 1;
  v5 = 0;
  v6 = 0;
  v36 = 0;
  if ( (unsigned int)GdipFlattenGdiPath(a1, &hMem, &pullResult) )
  {
    LODWORD(v7) = pullResult;
    if ( !(_DWORD)pullResult )
    {
LABEL_3:
      v6 = 1;
      goto LABEL_32;
    }
    v39 = hMem;
    v8 = 0;
    v34 = 0;
    pullResult = (ULONGLONG)hMem + 8 * (int)pullResult;
  }
  else
  {
    if ( !FlattenPath(*(HDC *)(v3 + 40)) )
      goto LABEL_32;
    Path = GetPath(*(HDC *)(v3 + 40), 0, 0, 0);
    v7 = Path;
    if ( Path < 0 )
      goto LABEL_32;
    if ( !Path )
      goto LABEL_3;
    pullResult = 0;
    if ( ULongLongMult(9u, Path, &pullResult) < 0 )
      goto LABEL_32;
    v10 = (struct tagPOINT *)LocalAlloc(0, pullResult);
    v42 = v10;
    v4 = v10;
    if ( !v10 )
      goto LABEL_32;
    v11 = *(HDC *)(v3 + 40);
    v39 = v10;
    pullResult = (ULONGLONG)&v10[v7];
    v8 = 0;
    if ( GetPath(v11, v10, (LPBYTE)pullResult, v7) != (_DWORD)v7 )
      goto LABEL_32;
  }
  uBytes = 0;
  v12 = (int)v7 + (int)v7 / 2;
  if ( ULongLongMult(0xDu, v12, &uBytes) < 0 )
    goto LABEL_32;
  v13 = (char *)LocalAlloc(0, uBytes);
  v5 = v13;
  if ( !v13 )
    goto LABEL_32;
  v14 = v39;
  v38 = &v13[8 * v12];
  uBytes = (ULONGLONG)&v38[4 * v12];
  v15 = 0;
  v16 = 0;
  v40 = (int)v7;
  v17 = v38;
  v18 = 0;
  while ( 1 )
  {
    v19 = v16;
    if ( v15 >= v40 )
      break;
    v20 = v16;
    v21 = uBytes;
    v44 = v18;
    *(_BYTE *)(v18 + uBytes) = *(_BYTE *)(v15 + pullResult);
    v39 = &v5[v18];
    *v39 = v14[v15];
    v6 = v36;
    ++v15;
    ++v16;
    ++v18;
    if ( v15 >= v40 )
    {
      v16 = v19;
      break;
    }
    v22 = pullResult;
    v23 = (_BYTE *)(v18 + v21);
    v24 = v40;
    v25 = &v5[v18];
    do
    {
      v43 = v23;
      if ( v15 >= v24 )
        break;
      ++v16;
      *v23 = *(_BYTE *)(v15 + v22);
      ++v18;
      ++v23;
      *v25++ = v14[v15++];
    }
    while ( *v43 == 2 );
    v19 = v16 - 1;
    v3 = a1;
    v6 = v36;
    v4 = v42;
    v26 = *(_BYTE *)((int)v16 + uBytes - 1);
    switch ( v26 )
    {
      case 6:
        --v15;
        --v18;
        --v16;
        if ( (_DWORD)v19 - v20 == 1 )
        {
          v18 = v44;
          v16 = v20;
        }
        else
        {
          ++v8;
          *(_DWORD *)v17 = v19 - v20;
          v17 += 4;
        }
        break;
      case 2:
        v28 = (int)v38;
        *(_DWORD *)&v38[4 * v8++] = v16 - v20;
        goto LABEL_30;
      case 3:
        v27 = uBytes;
        *(_BYTE *)(v18 + uBytes) = 2;
        *(_BYTE *)((int)v16 + v27 - 1) = 2;
        v5[v18] = *v39;
        ++v16;
        ++v18;
        *(_DWORD *)v17 = v16 - v20;
        ++v8;
        v17 += 4;
        break;
    }
  }
  v28 = (int)v38;
LABEL_30:
  if ( !v16 )
  {
    v6 = 1;
    goto LABEL_32;
  }
  v30 = a2;
  if ( a2 != 64 || a3 )
  {
    if ( *(_DWORD *)(v3 + 484) == 3 || a3 )
    {
      v31 = SetROP2(*(HDC *)(v3 + 40), 11);
      if ( !(unsigned int)bW16Emit1(v3, 260, 11) )
        goto LABEL_32;
      v6 = ConvertPolyPolygonToPolygons(v3, v5, v38, v16, v8, v34);
      if ( !v6 )
        goto LABEL_32;
      SetROP2(*(HDC *)(v3 + 40), v31);
      if ( !(unsigned int)bW16Emit1(v3, 260, (unsigned __int16)v31) )
        goto LABEL_32;
      LOWORD(pullResult) = 1;
      if ( !(unsigned int)bEmitWin16Escape(v3, 38, 2, &pullResult) )
        goto LABEL_32;
      v32 = a3;
      if ( a3 )
        goto LABEL_57;
      v30 = a2;
    }
    if ( v30 == 62 )
    {
      v37 = *(_DWORD *)(v3 + 436);
      if ( !(unsigned int)DoSelectObject(v3, 2147483656LL, v19) )
        goto LABEL_32;
    }
    v6 = DoPolyPolygon(v3, v5, v38, v16, v8, v34);
    if ( v30 == 62 )
      DoSelectObject(v3, v37, v33);
    v32 = a3;
LABEL_57:
    if ( *(_DWORD *)(v3 + 484) != 3 && !v32 )
      goto LABEL_33;
    LOWORD(pullResult) = 0;
    bEmitWin16Escape(v3, 38, 2, &pullResult);
LABEL_32:
    if ( a3 )
      goto LABEL_34;
    goto LABEL_33;
  }
  v6 = DoPolyPolyline(v3, (_DWORD)v5, v28, v8, v34);
LABEL_33:
  AbortPath(*(HDC *)(v3 + 40));
LABEL_34:
  if ( v5 )
    LocalFree(v5);
  if ( v4 )
    LocalFree(v4);
  if ( hMem )
    LocalFree(hMem);
  return v6;
}

```

## disassembly

```asm
0x1801456fc  mov     rax, rsp
0x1801456ff  mov     [rax+18h], r8d
0x180145703  mov     [rax+10h], edx
0x180145706  mov     [rax+8], rcx
0x18014570a  push    rbp
0x18014570b  push    rbx
0x18014570c  push    rsi
0x18014570d  push    rdi
0x18014570e  push    r12
0x180145710  push    r13
0x180145712  push    r14
0x180145714  push    r15
0x180145716  lea     rbp, [rax-5Fh]
0x18014571a  sub     rsp, 88h
0x180145721  xor     r12d, r12d
0x180145724  lea     r8, [rbp+57h+pullResult]
0x180145728  lea     rdx, [rbp+57h+hMem]
0x18014572c  mov     [rbp+57h+var_58], r12
0x180145730  mov     rbx, rcx
0x180145733  mov     [rbp+57h+var_7C], r12d
0x180145737  mov     r13d, r12d
0x18014573a  mov     [rbp+57h+hMem], r12
0x18014573e  lea     esi, [r12+1]
0x180145743  mov     dword ptr [rbp+57h+pullResult], r12d
0x180145747  mov     [rbp+57h+var_90], esi
0x18014574a  mov     r14d, r12d
0x18014574d  mov     r15d, r12d
0x180145750  mov     [rbp+57h+var_80], r12d
0x180145754  call    GdipFlattenGdiPath
0x180145759  test    eax, eax
0x18014575b  jz      short loc_180145789
0x18014575d  movsxd  rdi, dword ptr [rbp+57h+pullResult]
0x180145761  test    edi, edi
0x180145763  jnz     short loc_18014576D
0x180145765  mov     r15d, esi
0x180145768  jmp     loc_180145A06
0x18014576d  mov     r12, [rbp+57h+hMem]
0x180145771  mov     [rbp+57h+var_70], r12
0x180145775  lea     rax, [r12+rdi*8]
0x180145779  xor     r12d, r12d
0x18014577c  mov     [rbp+57h+var_90], r12d
0x180145780  mov     [rbp+57h+pullResult], rax
0x180145784  jmp     loc_18014583C
0x180145789  mov     rcx, [rbx+28h]; hdc
0x18014578d  call    cs:__imp_FlattenPath
0x180145794  nop     dword ptr [rax+rax+00h]
0x180145799  test    eax, eax
0x18014579b  jz      loc_180145A06
0x1801457a1  mov     rcx, [rbx+28h]; hdc
0x1801457a5  xor     r9d, r9d; cpt
0x1801457a8  xor     r8d, r8d; aj
0x1801457ab  xor     edx, edx; apt
0x1801457ad  call    cs:__imp_GetPath
0x1801457b4  nop     dword ptr [rax+rax+00h]
0x1801457b9  movsxd  rdi, eax
0x1801457bc  test    eax, eax
0x1801457be  js      loc_180145A06
0x1801457c4  jz      short loc_180145765
0x1801457c6  lea     r8, [rbp+57h+pullResult]; pullResult
0x1801457ca  mov     [rbp+57h+pullResult], r12
0x1801457ce  mov     rdx, rdi; ullMultiplier
0x1801457d1  mov     ecx, 9; ullMultiplicand
0x1801457d6  call    ULongLongMult
0x1801457db  test    eax, eax
0x1801457dd  js      loc_180145A06
0x1801457e3  mov     rdx, [rbp+57h+pullResult]; uBytes
0x1801457e7  xor     ecx, ecx; uFlags
0x1801457e9  call    cs:__imp_LocalAlloc
0x1801457f0  nop     dword ptr [rax+rax+00h]
0x1801457f5  mov     [rbp+57h+var_58], rax
0x1801457f9  mov     r13, rax
0x1801457fc  test    rax, rax
0x1801457ff  jz      loc_180145A06
0x180145805  mov     rcx, [rbx+28h]; hdc
0x180145809  lea     r12, ds:0[rdi*8]
0x180145811  add     r12, rax
0x180145814  mov     [rbp+57h+var_70], rax
0x180145818  mov     r8, r12; aj
0x18014581b  mov     [rbp+57h+pullResult], r12
0x18014581f  mov     r9d, edi; cpt
0x180145822  mov     rdx, rax; apt
0x180145825  call    cs:__imp_GetPath
0x18014582c  nop     dword ptr [rax+rax+00h]
0x180145831  xor     r12d, r12d
0x180145834  cmp     eax, edi
0x180145836  jnz     loc_180145A06
0x18014583c  mov     eax, edi
0x18014583e  mov     [rbp+57h+uBytes], r12
0x180145842  cdq
0x180145843  lea     r8, [rbp+57h+uBytes]; pullResult
0x180145847  mov     ecx, 2
0x18014584c  idiv    ecx
0x18014584e  mov     ecx, 0Dh; ullMultiplicand
0x180145853  add     eax, edi
0x180145855  movsxd  rsi, eax
0x180145858  mov     rdx, rsi; ullMultiplier
0x18014585b  call    ULongLongMult
0x180145860  test    eax, eax
0x180145862  js      loc_180145A06
0x180145868  mov     rdx, [rbp+57h+uBytes]; uBytes
0x18014586c  xor     ecx, ecx; uFlags
0x18014586e  call    cs:__imp_LocalAlloc
0x180145875  nop     dword ptr [rax+rax+00h]
0x18014587a  mov     r14, rax
0x18014587d  test    rax, rax
0x180145880  jz      loc_180145A06
0x180145886  mov     r11, [rbp+57h+var_70]
0x18014588a  lea     rax, [rax+rsi*8]
0x18014588e  lea     rcx, [rax+rsi*4]
0x180145892  mov     [rbp+57h+var_78], rax
0x180145896  mov     [rbp+57h+uBytes], rcx
0x18014589a  xor     edx, edx
0x18014589c  movsxd  rcx, edi
0x18014589f  mov     esi, r12d
0x1801458a2  mov     [rbp+57h+var_68], rcx
0x1801458a6  mov     r10, rax
0x1801458a9  xor     ecx, ecx
0x1801458ab  mov     eax, 1
0x1801458b0  mov     r8d, esi
0x1801458b3  cmp     rdx, [rbp+57h+var_68]
0x1801458b7  jge     loc_1801459F8
0x1801458bd  mov     rax, [rbp+57h+pullResult]
0x1801458c1  mov     r9d, esi
0x1801458c4  mov     rdi, [rbp+57h+uBytes]
0x1801458c8  mov     [rbp+57h+var_48], rcx
0x1801458cc  mov     al, [rdx+rax]
0x1801458cf  mov     [rcx+rdi], al
0x1801458d2  lea     rax, [r14+rcx*8]
0x1801458d6  mov     [rbp+57h+var_70], rax
0x1801458da  mov     rax, [r11+rdx*8]
0x1801458de  mov     r15, [rbp+57h+var_70]
0x1801458e2  mov     [r15], rax
0x1801458e5  mov     eax, 1
0x1801458ea  mov     r15d, [rbp+57h+var_80]
0x1801458ee  add     rdx, rax
0x1801458f1  add     esi, eax
0x1801458f3  add     rcx, rax
0x1801458f6  cmp     rdx, [rbp+57h+var_68]
0x1801458fa  jge     loc_1801459F5
0x180145900  mov     r15, [rbp+57h+pullResult]
0x180145904  lea     r8, [rcx+rdi]
0x180145908  mov     rbx, [rbp+57h+var_68]
0x18014590c  lea     rdi, [r14+rcx*8]
0x180145910  mov     r13d, eax
0x180145913  mov     [rbp+57h+var_50], r8
0x180145917  cmp     rdx, rbx
0x18014591a  jge     short loc_180145943
0x18014591c  mov     al, [rdx+r15]
0x180145920  add     esi, r13d
0x180145923  mov     [r8], al
0x180145926  add     rcx, r13
0x180145929  mov     rax, [r11+rdx*8]
0x18014592d  add     r8, r13
0x180145930  mov     [rdi], rax
0x180145933  add     rdx, r13
0x180145936  mov     rax, [rbp+57h+var_50]
0x18014593a  add     rdi, 8
0x18014593e  cmp     byte ptr [rax], 2
0x180145941  jz      short loc_180145913
0x180145943  mov     rax, [rbp+57h+uBytes]
0x180145947  lea     r8d, [rsi-1]
0x18014594b  mov     rbx, [rbp+57h+arg_0]
0x18014594f  mov     r15d, [rbp+57h+var_80]
0x180145953  mov     r13, [rbp+57h+var_58]
0x180145957  movsxd  rdi, esi
0x18014595a  mov     al, [rdi+rax-1]
0x18014595e  cmp     al, 6
0x180145960  jnz     short loc_180145995
0x180145962  mov     edi, 1
0x180145967  mov     eax, r8d
0x18014596a  sub     rdx, rdi
0x18014596d  sub     rcx, rdi
0x180145970  sub     eax, r9d
0x180145973  mov     esi, r8d
0x180145976  cmp     eax, edi
0x180145978  jnz     short loc_180145983
0x18014597a  mov     rcx, [rbp+57h+var_48]
0x18014597e  mov     esi, r9d
0x180145981  jmp     short loc_18014598D
0x180145983  add     r12d, edi
0x180145986  mov     [r10], eax
0x180145989  add     r10, 4
0x18014598d  mov     rax, rdi
0x180145990  jmp     loc_1801458B0
0x180145995  cmp     al, 2
0x180145997  jz      short loc_1801459DC
0x180145999  cmp     al, 3
0x18014599b  jnz     loc_1801458AB
0x1801459a1  mov     rax, [rbp+57h+uBytes]
0x1801459a5  mov     byte ptr [rcx+rax], 2
0x1801459a9  mov     byte ptr [rdi+rax-1], 2
0x1801459ae  mov     rax, [rbp+57h+var_70]
0x1801459b2  mov     rax, [rax]
0x1801459b5  mov     [r14+rcx*8], rax
0x1801459b9  mov     eax, 1
0x1801459be  add     esi, eax
0x1801459c0  add     rcx, rax
0x1801459c3  mov     eax, esi
0x1801459c5  sub     eax, r9d
0x1801459c8  mov     [r10], eax
0x1801459cb  mov     eax, 1
0x1801459d0  add     r12d, eax
0x1801459d3  add     r10, 4
0x1801459d7  jmp     loc_1801458B0
0x1801459dc  mov     rdx, [rbp+57h+var_78]
0x1801459e0  mov     ecx, esi
0x1801459e2  movsxd  rax, r12d
0x1801459e5  sub     ecx, r9d
0x1801459e8  mov     [rdx+rax*4], ecx
0x1801459eb  mov     eax, 1
0x1801459f0  add     r12d, eax
0x1801459f3  jmp     short loc_1801459FC
0x1801459f5  mov     esi, r8d
0x1801459f8  mov     rdx, [rbp+57h+var_78]
0x1801459fc  test    esi, esi
0x1801459fe  jnz     short loc_180145A71
0x180145a00  mov     r15d, eax
0x180145a03  xor     r12d, r12d
0x180145a06  cmp     [rbp+57h+arg_10], r12d
0x180145a0a  jnz     short loc_180145A1C
0x180145a0c  mov     rcx, [rbx+28h]; hdc
0x180145a10  call    cs:__imp_AbortPath
0x180145a17  nop     dword ptr [rax+rax+00h]
0x180145a1c  test    r14, r14
0x180145a1f  jz      short loc_180145A30
0x180145a21  mov     rcx, r14; hMem
0x180145a24  call    cs:__imp_LocalFree
0x180145a2b  nop     dword ptr [rax+rax+00h]
0x180145a30  test    r13, r13
0x180145a33  jz      short loc_180145A44
0x180145a35  mov     rcx, r13; hMem
0x180145a38  call    cs:__imp_LocalFree
0x180145a3f  nop     dword ptr [rax+rax+00h]
0x180145a44  mov     rcx, [rbp+57h+hMem]; hMem
0x180145a48  test    rcx, rcx
0x180145a4b  jz      short loc_180145A59
0x180145a4d  call    cs:__imp_LocalFree
0x180145a54  nop     dword ptr [rax+rax+00h]
0x180145a59  mov     eax, r15d
0x180145a5c  add     rsp, 88h
0x180145a63  pop     r15
0x180145a65  pop     r14
0x180145a67  pop     r13
0x180145a69  pop     r12
0x180145a6b  pop     rdi
0x180145a6c  pop     rsi
0x180145a6d  pop     rbx
0x180145a6e  pop     rbp
0x180145a6f  retn
0x180145a71  mov     edi, [rbp+57h+arg_8]
0x180145a74  mov     eax, [rbp+57h+arg_10]
0x180145a77  cmp     edi, 40h ; '@'
0x180145a7a  jnz     short loc_180145AA0
0x180145a7c  test    eax, eax
0x180145a7e  jnz     short loc_180145AA0
0x180145a80  mov     eax, [rbp+57h+var_90]
0x180145a83  mov     r8, rdx
0x180145a86  mov     rdx, r14
0x180145a89  mov     [rsp+0C0h+var_A0], eax
0x180145a8d  mov     r9d, r12d
0x180145a90  mov     rcx, rbx
0x180145a93  call    DoPolyPolyline
0x180145a98  mov     r15d, eax
0x180145a9b  jmp     loc_180145A0C
0x180145aa0  cmp     dword ptr [rbx+1E4h], 3
0x180145aa7  jz      short loc_180145AB1
0x180145aa9  test    eax, eax
0x180145aab  jz      loc_180145B65
0x180145ab1  mov     rcx, [rbx+28h]; hdc
0x180145ab5  mov     edx, 0Bh; rop2
0x180145aba  call    cs:__imp_SetROP2
0x180145ac1  nop     dword ptr [rax+rax+00h]
0x180145ac6  mov     edx, 104h
0x180145acb  mov     r8d, 0Bh
0x180145ad1  mov     rcx, rbx
0x180145ad4  mov     edi, eax
0x180145ad6  call    bW16Emit1
0x180145adb  test    eax, eax
0x180145add  jz      loc_180145A03
0x180145ae3  mov     eax, [rbp+57h+var_90]
0x180145ae6  mov     r9d, esi
0x180145ae9  mov     r8, [rbp+57h+var_78]
0x180145aed  mov     rdx, r14
0x180145af0  mov     [rsp+28h], eax
0x180145af4  mov     rcx, rbx
0x180145af7  mov     [rsp+0C0h+var_A0], r12d
0x180145afc  call    ConvertPolyPolygonToPolygons
0x180145b01  mov     r15d, eax
0x180145b04  test    eax, eax
0x180145b06  jz      loc_180145A03
0x180145b0c  mov     rcx, [rbx+28h]; hdc
0x180145b10  mov     edx, edi; rop2
0x180145b12  call    cs:__imp_SetROP2
0x180145b19  nop     dword ptr [rax+rax+00h]
0x180145b1e  mov     edx, 104h
0x180145b23  movzx   r8d, di
0x180145b27  mov     rcx, rbx
0x180145b2a  call    bW16Emit1
0x180145b2f  test    eax, eax
0x180145b31  jz      loc_180145A03
  ... truncated ...
```

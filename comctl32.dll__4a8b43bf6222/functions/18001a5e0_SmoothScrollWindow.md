# SmoothScrollWindow

- ea: `0x18001a5e0`
- end: `0x18001aaef`
- name: `SmoothScrollWindow`
- size: `1295`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180054630`
- `0x1800616ac`
- `0x180066824`
- `0x180074e00`
- `0x180077370`
- `0x180079470`
- `0x18007a910`
- `0x18007da0c`
- `0x18007db50`
- `0x18007dc50`

## callees

- `0x1800115f0`
- `0x18001a5e0`
- `0x180090020`

## import_xrefs

- `GDI32!DeleteObject` at `0x18001aac3`
- `GDI32!DeleteObject` at `0x18001aac3`
- `GDI32!CreateRectRgn` at `0x18001a7c5`
- `GDI32!CreateRectRgn` at `0x18001a7c5`
- `KERNEL32!GetTickCount` at `0x18001a7d0`
- `KERNEL32!GetTickCount` at `0x18001a8f5`
- `KERNEL32!GetTickCount` at `0x18001a7d0`
- `KERNEL32!GetTickCount` at `0x18001a8f5`
- `USER32!SetRectEmpty` at `0x18001a67c`
- `USER32!SetRectEmpty` at `0x18001a67c`
- `USER32!GetDoubleClickTime` at `0x18001a6c6`
- `USER32!GetDoubleClickTime` at `0x18001a821`
- `USER32!GetDoubleClickTime` at `0x18001a6c6`
- `USER32!GetDoubleClickTime` at `0x18001a821`
- `USER32!ScrollWindowEx` at `0x18001a722`
- `USER32!RedrawWindow` at `0x18001a9f9`
- `USER32!RedrawWindow` at `0x18001aaab`
- `USER32!RedrawWindow` at `0x18001a9f9`
- `USER32!RedrawWindow` at `0x18001aaab`
- `USER32!UnionRect` at `0x18001aa12`
- `USER32!UnionRect` at `0x18001aa12`

## pseudocode

```c
__int64 __fastcall SmoothScrollWindow(__int64 a1)
{
  struct tagRECT *v1; // r12
  int v2; // r13d
  int v4; // ebx
  int v5; // esi
  __int128 *v6; // r14
  __int128 *v7; // rbp
  UINT v8; // r15d
  unsigned int v9; // eax
  int (__stdcall *v11)(HWND, int, int, const RECT *, const RECT *, HRGN, LPRECT, UINT); // rax
  __int128 v12; // xmm0
  __int128 v13; // xmm0
  HRGN RectRgn; // rax
  int v15; // eax
  int v16; // edx
  UINT v17; // ecx
  int v18; // r15d
  int v19; // r12d
  int v20; // esi
  HWND *v21; // r13
  int v22; // ecx
  int v23; // esi
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  int v27; // ebx
  unsigned int v28; // ebx
  DWORD v29; // eax
  int v30; // r9d
  int v31; // r8d
  int v32; // eax
  int v33; // eax
  int v34; // ecx
  int v35; // eax
  int v36; // ecx
  int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // ebx
  int v41; // [rsp+50h] [rbp-E8h]
  int v42; // [rsp+54h] [rbp-E4h]
  unsigned int v43; // [rsp+58h] [rbp-E0h]
  unsigned int v44; // [rsp+5Ch] [rbp-DCh]
  int v45; // [rsp+60h] [rbp-D8h]
  int v46; // [rsp+64h] [rbp-D4h]
  unsigned __int16 v47; // [rsp+68h] [rbp-D0h]
  int v48; // [rsp+6Ch] [rbp-CCh]
  int v49; // [rsp+70h] [rbp-C8h]
  HRGN hrgnUpdate; // [rsp+78h] [rbp-C0h]
  UINT v51; // [rsp+80h] [rbp-B8h]
  DWORD TickCount; // [rsp+84h] [rbp-B4h]
  HRGN v53; // [rsp+88h] [rbp-B0h]
  int (__stdcall *v54)(HWND, int, int, const RECT *, const RECT *, HRGN, LPRECT, UINT); // [rsp+90h] [rbp-A8h]
  LPRECT lprcDst; // [rsp+98h] [rbp-A0h]
  __int128 v56; // [rsp+A0h] [rbp-98h] BYREF
  __int128 v57; // [rsp+B0h] [rbp-88h] BYREF
  RECT rcSrc1; // [rsp+C0h] [rbp-78h] BYREF
  __int128 v59; // [rsp+D0h] [rbp-68h] BYREF

  v1 = (struct tagRECT *)&v59;
  v2 = *(_DWORD *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 48) )
    v1 = *(struct tagRECT **)(a1 + 48);
  v4 = *(_DWORD *)(a1 + 20);
  v5 = *(_DWORD *)(a1 + 56);
  v6 = *(__int128 **)(a1 + 24);
  v7 = *(__int128 **)(a1 + 32);
  v8 = *(_DWORD *)(a1 + 60);
  v53 = *(HRGN *)(a1 + 40);
  v43 = *(_DWORD *)(a1 + 64);
  v9 = *(_DWORD *)(a1 + 68);
  v41 = *(_DWORD *)(a1 + 16);
  v42 = v4;
  v47 = v5;
  v59 = 0;
  v44 = v9;
  v56 = 0;
  lprcDst = v1;
  v57 = 0;
  SetRectEmpty(v1);
  if ( *(_DWORD *)a1 != 80 )
    return 0;
  if ( ((*(_DWORD *)(a1 + 4) & 4) == 0 || v43 == -1) && (v43 = 8, (*(_DWORD *)(a1 + 4) & 4) == 0) || v44 == -1 )
    v44 = 8;
  if ( (*(_BYTE *)(a1 + 4) & 2) == 0 || v8 == -1 )
    v8 = (GetDoubleClickTime() >> 1) + 1;
  v46 = 100;
  if ( v8 < 0x64 )
    v8 = 100;
  v51 = v8;
  if ( (v5 & 0x40000) == 0 && !*(_DWORD *)&g_fSmoothScroll )
  {
    v5 |= 0x20000u;
    v47 = v5;
  }
  if ( (*(_BYTE *)(a1 + 4) & 1) == 0
    || (v11 = *(int (__stdcall **)(HWND, int, int, const RECT *, const RECT *, HRGN, LPRECT, UINT))(a1 + 72),
        (v54 = v11) == 0) )
  {
    v11 = ScrollWindowEx;
    v54 = ScrollWindowEx;
  }
  if ( (v5 & 0x20000) != 0 )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int128 *, __int128 *, HRGN, struct tagRECT *, _DWORD))v11)(
             *(_QWORD *)(a1 + 8),
             (unsigned int)v2,
             (unsigned int)v4,
             v6,
             v7,
             v53,
             v1,
             (unsigned __int16)v5);
  v45 = 0;
  v48 = 0;
  if ( v6 )
  {
    v12 = *v6;
    v6 = &v56;
    v56 = v12;
  }
  if ( v7 )
  {
    v13 = *v7;
    v7 = &v57;
    v57 = v13;
  }
  RectRgn = v53;
  if ( !v53 )
    RectRgn = CreateRectRgn(0, 0, 0, 0);
  hrgnUpdate = RectRgn;
  TickCount = GetTickCount();
  v15 = v5 & 0x10000;
  v49 = v5 & 0x10000;
  if ( (v5 & 0x10000) != 0 )
  {
    v16 = v2;
    v17 = 100;
    v18 = v43 * (((v2 >> 31) & 0xFFFFFFFE) + 1);
    v19 = v44 * (((v4 >> 31) & 0xFFFFFFFE) + 1);
  }
  else
  {
    v17 = 100 * (v8 / ((GetDoubleClickTime() >> 1) + 1));
    if ( !v17 )
      v17 = 100;
    v46 = v17;
    v18 = v2 / (int)v17;
    v16 = v2;
    v19 = v4 / (int)v17;
    v15 = 0;
  }
  if ( !v18 )
  {
    if ( v16 )
    {
      v18 = 1;
      if ( v16 < 0 )
        v18 = -1;
    }
  }
  if ( !v19 )
  {
    if ( v4 )
    {
      v19 = 1;
      if ( v4 < 0 )
        v19 = -1;
    }
  }
  v20 = 0;
  v21 = (HWND *)(a1 + 8);
  while ( v16 || v4 )
  {
    rcSrc1 = 0;
    if ( v15 )
    {
      v22 = -v18;
      v23 = v18;
      if ( v18 > 0 )
        v22 = v18;
      v24 = -v16;
      if ( v16 > 0 )
        v24 = v16;
      if ( v22 > v24 )
        v23 = v16;
      v25 = -v19;
      if ( v19 > 0 )
        v25 = v19;
      v26 = -v4;
      if ( v4 > 0 )
        v26 = v4;
      v27 = v19;
      if ( v25 > v26 )
        v27 = v42;
    }
    else
    {
      v28 = v51 / v17;
      if ( !(v51 / v17) )
        v28 = 1;
      v29 = GetTickCount();
      v30 = v20 + 1;
      v31 = 0;
      v32 = (v29 - TickCount) / v28 - v20;
      if ( v32 >= 0 )
        v31 = v32;
      while ( 1 )
      {
        v33 = v30 + v31++;
        v48 = v31;
        if ( v33 > v46 )
          break;
        v23 = v18 * v31;
        v34 = -(v18 * v31);
        if ( v18 * v31 > 0 )
          v34 = v18 * v31;
        v35 = -v41;
        if ( v41 > 0 )
          v35 = v41;
        if ( v34 > v35 )
          v23 = v41;
        v27 = v19 * v31;
        v36 = -(v19 * v31);
        if ( v19 * v31 > 0 )
          v36 = v19 * v31;
        v37 = -v42;
        if ( v42 > 0 )
          v37 = v42;
        if ( v36 > v37 )
          v27 = v42;
        if ( v23 != v41 || v27 != v42 )
        {
          v38 = -v23;
          if ( v23 > 0 )
            v38 = v23;
          if ( v38 < v43 && v23 )
            continue;
          v39 = -v27;
          if ( v27 > 0 )
            v39 = v27;
          if ( v39 < v44 && v27 )
            continue;
        }
        goto LABEL_88;
      }
      v23 = v41;
      v27 = v42;
    }
LABEL_88:
    v21 = (HWND *)(a1 + 8);
    if ( !((unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, __int128 *, __int128 *, HRGN, RECT *, _DWORD))v54)(
            *(_QWORD *)(a1 + 8),
            (unsigned int)v23,
            (unsigned int)v27,
            v6,
            v7,
            hrgnUpdate,
            &rcSrc1,
            v47) )
    {
      v40 = 0;
      goto LABEL_106;
    }
    RedrawWindow(*v21, 0, hrgnUpdate, 0x205u);
    UnionRect(lprcDst, &rcSrc1, lprcDst);
    if ( v6 )
    {
      if ( v23 <= 0 )
        *((_DWORD *)v6 + 2) += v23;
      else
        *(_DWORD *)v6 += v23;
      if ( v27 <= 0 )
        *((_DWORD *)v6 + 3) += v27;
      else
        *((_DWORD *)v6 + 1) += v27;
    }
    if ( v7 )
    {
      if ( v23 <= 0 )
        *((_DWORD *)v7 + 2) += v23;
      else
        *(_DWORD *)v7 += v23;
      if ( v27 <= 0 )
        *((_DWORD *)v7 + 3) += v27;
      else
        *((_DWORD *)v7 + 1) += v27;
    }
    v42 -= v27;
    v16 = v41 - v23;
    v20 = v48 + v45;
    v4 = v42;
    v17 = v46;
    v15 = v49;
    v45 += v48;
    v41 = v16;
  }
  v40 = 2;
LABEL_106:
  if ( (v47 & 1) != 0 )
    RedrawWindow(*v21, lprcDst, 0, 1u);
  if ( hrgnUpdate != v53 )
    DeleteObject(hrgnUpdate);
  return v40;
}

```

## disassembly

```asm
0x18001a5e0  mov     r11, rsp
0x18001a5e3  push    rbx
0x18001a5e4  push    rbp
0x18001a5e5  push    rsi
0x18001a5e6  push    rdi
0x18001a5e7  push    r12
0x18001a5e9  push    r13
0x18001a5eb  push    r14
0x18001a5ed  push    r15
0x18001a5ef  sub     rsp, 0F8h
0x18001a5f6  mov     rax, cs:__security_cookie
0x18001a5fd  xor     rax, rsp
0x18001a600  mov     [rsp+138h+var_58], rax
0x18001a608  mov     rax, [rcx+28h]
0x18001a60c  lea     r12, [r11-68h]
0x18001a610  cmp     qword ptr [rcx+30h], 0
0x18001a615  xorps   xmm0, xmm0
0x18001a618  mov     r13d, [rcx+10h]
0x18001a61c  mov     rdi, rcx
0x18001a61f  cmovnz  r12, [rcx+30h]
0x18001a624  xorps   xmm1, xmm1
0x18001a627  mov     ebx, [rcx+14h]
0x18001a62a  mov     esi, [rcx+38h]
0x18001a62d  mov     r14, [rcx+18h]
0x18001a631  mov     rbp, [rcx+20h]
0x18001a635  mov     r15d, [rcx+3Ch]
0x18001a639  mov     [rsp+138h+var_B0], rax
0x18001a641  mov     eax, [rcx+40h]
0x18001a644  mov     [rsp+138h+var_E0], eax
0x18001a648  mov     eax, [rcx+44h]
0x18001a64b  mov     rcx, r12; lprc
0x18001a64e  mov     [rsp+138h+var_E8], r13d
0x18001a653  mov     [rsp+138h+var_E4], ebx
0x18001a657  mov     [rsp+138h+var_D0], esi
0x18001a65b  movups  xmmword ptr [r11-68h], xmm0
0x18001a660  mov     [rsp+138h+var_DC], eax
0x18001a664  movups  [rsp+138h+var_98], xmm1
0x18001a66c  mov     [rsp+138h+lprcDst], r12
0x18001a674  movups  [rsp+138h+var_88], xmm0
0x18001a67c  call    cs:__imp_SetRectEmpty
0x18001a682  cmp     dword ptr [rdi], 50h ; 'P'
0x18001a685  jz      short loc_18001A68E
0x18001a687  xor     eax, eax
0x18001a689  jmp     loc_18001AACB
0x18001a68e  mov     eax, [rdi+4]
0x18001a691  or      edx, 0FFFFFFFFh
0x18001a694  mov     ecx, 8
0x18001a699  and     eax, 4
0x18001a69c  jz      short loc_18001A6A4
0x18001a69e  cmp     [rsp+138h+var_E0], edx
0x18001a6a2  jnz     short loc_18001A6AC
0x18001a6a4  mov     [rsp+138h+var_E0], ecx
0x18001a6a8  test    eax, eax
0x18001a6aa  jz      short loc_18001A6B2
0x18001a6ac  cmp     [rsp+138h+var_DC], edx
0x18001a6b0  jnz     short loc_18001A6B6
0x18001a6b2  mov     [rsp+138h+var_DC], ecx
0x18001a6b6  test    byte ptr [rdi+4], 2
0x18001a6ba  mov     ecx, 1
0x18001a6bf  jz      short loc_18001A6C6
0x18001a6c1  cmp     r15d, edx
0x18001a6c4  jnz     short loc_18001A6DA
0x18001a6c6  call    cs:__imp_GetDoubleClickTime
0x18001a6cc  mov     r15d, eax
0x18001a6cf  mov     ecx, 1
0x18001a6d4  shr     r15d, 1
0x18001a6d7  add     r15d, ecx
0x18001a6da  mov     eax, 64h ; 'd'
0x18001a6df  mov     edx, 20000h
0x18001a6e4  cmp     r15d, eax
0x18001a6e7  mov     [rsp+138h+var_D4], eax
0x18001a6eb  cmovb   r15d, eax
0x18001a6ef  mov     [rsp+138h+var_B8], r15d
0x18001a6f7  bt      esi, 12h
0x18001a6fb  jb      short loc_18001A70C
0x18001a6fd  cmp     cs:g_fSmoothScroll, 0
0x18001a704  jnz     short loc_18001A70C
0x18001a706  or      esi, edx
0x18001a708  mov     [rsp+138h+var_D0], esi
0x18001a70c  test    [rdi+4], cl
0x18001a70f  jz      short loc_18001A722
0x18001a711  mov     rax, [rdi+48h]
0x18001a715  mov     [rsp+138h+var_A8], rax
0x18001a71d  test    rax, rax
0x18001a720  jnz     short loc_18001A731
0x18001a722  mov     rax, cs:__imp_ScrollWindowEx
0x18001a729  mov     [rsp+138h+var_A8], rax
0x18001a731  test    edx, esi
0x18001a733  jz      short loc_18001A76A
0x18001a735  mov     rcx, [rsp+138h+var_B0]
0x18001a73d  mov     r9, r14
0x18001a740  movzx   edx, si
0x18001a743  mov     r8d, ebx
0x18001a746  mov     [rsp+138h+var_100], edx
0x18001a74a  mov     edx, r13d
0x18001a74d  mov     [rsp+138h+var_108], r12
0x18001a752  mov     [rsp+138h+var_110], rcx
0x18001a757  mov     rcx, [rdi+8]
0x18001a75b  mov     [rsp+138h+var_118], rbp
0x18001a760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a765  jmp     loc_18001AACB
0x18001a76a  mov     [rsp+138h+var_D8], 0
0x18001a772  mov     [rsp+138h+var_CC], 0
0x18001a77a  test    r14, r14
0x18001a77d  jz      short loc_18001A794
0x18001a77f  movups  xmm0, xmmword ptr [r14]
0x18001a783  lea     r14, [rsp+138h+var_98]
0x18001a78b  movdqu  [rsp+138h+var_98], xmm0
0x18001a794  test    rbp, rbp
0x18001a797  jz      short loc_18001A7AE
0x18001a799  movups  xmm0, xmmword ptr [rbp+0]
0x18001a79d  lea     rbp, [rsp+138h+var_88]
0x18001a7a5  movdqu  [rsp+138h+var_88], xmm0
0x18001a7ae  mov     rax, [rsp+138h+var_B0]
0x18001a7b6  test    rax, rax
0x18001a7b9  jnz     short loc_18001A7CB
0x18001a7bb  xor     r9d, r9d; y2
0x18001a7be  xor     r8d, r8d; x2
0x18001a7c1  xor     edx, edx; y1
0x18001a7c3  xor     ecx, ecx; x1
0x18001a7c5  call    cs:__imp_CreateRectRgn
0x18001a7cb  mov     [rsp+138h+hrgnUpdate], rax
0x18001a7d0  call    cs:__imp_GetTickCount
0x18001a7d6  mov     [rsp+138h+var_B4], eax
0x18001a7dd  mov     eax, esi
0x18001a7df  and     eax, 10000h
0x18001a7e4  mov     [rsp+138h+var_C8], eax
0x18001a7e8  jz      short loc_18001A821
0x18001a7ea  mov     r8d, 1
0x18001a7f0  mov     edx, r13d
0x18001a7f3  mov     r15d, edx
0x18001a7f6  mov     r12d, ebx
0x18001a7f9  sar     r15d, 1Fh
0x18001a7fd  and     r15d, 0FFFFFFFEh
0x18001a801  sar     r12d, 1Fh
0x18001a805  add     r15d, r8d
0x18001a808  lea     ecx, [r8+63h]
0x18001a80c  imul    r15d, [rsp+138h+var_E0]
0x18001a812  and     r12d, 0FFFFFFFEh
0x18001a816  add     r12d, r8d
0x18001a819  imul    r12d, [rsp+138h+var_DC]
0x18001a81f  jmp     short loc_18001A864
0x18001a821  call    cs:__imp_GetDoubleClickTime
0x18001a827  xor     edx, edx
0x18001a829  mov     r8d, 1
0x18001a82f  mov     ecx, eax
0x18001a831  mov     eax, r15d
0x18001a834  shr     ecx, 1
0x18001a836  add     ecx, r8d
0x18001a839  div     ecx
0x18001a83b  lea     r10d, [r8+63h]
0x18001a83f  imul    ecx, eax, 64h ; 'd'
0x18001a842  mov     eax, r13d
0x18001a845  cdq
0x18001a846  test    ecx, ecx
0x18001a848  cmovz   ecx, r10d
0x18001a84c  idiv    ecx
0x18001a84e  mov     [rsp+138h+var_D4], ecx
0x18001a852  mov     r15d, eax
0x18001a855  mov     eax, ebx
0x18001a857  cdq
0x18001a858  idiv    ecx
0x18001a85a  mov     edx, r13d
0x18001a85d  mov     r12d, eax
0x18001a860  mov     eax, [rsp+138h+var_C8]
0x18001a864  or      r9d, 0FFFFFFFFh
0x18001a868  test    r15d, r15d
0x18001a86b  jnz     short loc_18001A878
0x18001a86d  test    edx, edx
0x18001a86f  jz      short loc_18001A878
0x18001a871  mov     r15d, r8d
0x18001a874  cmovs   r15d, r9d
0x18001a878  test    r12d, r12d
0x18001a87b  jnz     short loc_18001A888
0x18001a87d  test    ebx, ebx
0x18001a87f  jz      short loc_18001A888
0x18001a881  mov     r12d, r8d
0x18001a884  cmovs   r12d, r9d
0x18001a888  mov     esi, [rsp+138h+var_D8]
0x18001a88c  lea     r13, [rdi+8]
0x18001a890  test    edx, edx
0x18001a892  jnz     short loc_18001A89C
0x18001a894  test    ebx, ebx
0x18001a896  jz      loc_18001AA8A
0x18001a89c  xorps   xmm0, xmm0
0x18001a89f  movups  xmmword ptr [rsp+138h+rcSrc1.left], xmm0
0x18001a8a7  test    eax, eax
0x18001a8a9  jz      short loc_18001A8E2
0x18001a8ab  mov     ecx, r15d
0x18001a8ae  mov     eax, edx
0x18001a8b0  neg     ecx
0x18001a8b2  mov     esi, r15d
0x18001a8b5  cmovs   ecx, r15d
0x18001a8b9  neg     eax
0x18001a8bb  cmovs   eax, edx
0x18001a8be  cmp     ecx, eax
0x18001a8c0  mov     eax, ebx
0x18001a8c2  mov     ecx, r12d
0x18001a8c5  cmovg   esi, edx
0x18001a8c8  neg     ecx
0x18001a8ca  cmovs   ecx, r12d
0x18001a8ce  neg     eax
0x18001a8d0  cmovs   eax, ebx
0x18001a8d3  mov     ebx, r12d
0x18001a8d6  cmp     ecx, eax
0x18001a8d8  cmovg   ebx, [rsp+138h+var_E4]
0x18001a8dd  jmp     loc_18001A99E
0x18001a8e2  mov     eax, [rsp+138h+var_B8]
0x18001a8e9  xor     edx, edx
0x18001a8eb  div     ecx
0x18001a8ed  test    eax, eax
0x18001a8ef  mov     ebx, eax
0x18001a8f1  cmovz   ebx, r8d
0x18001a8f5  call    cs:__imp_GetTickCount
0x18001a8fb  mov     r13d, [rsp+138h+var_E8]
0x18001a900  lea     r9d, [rsi+1]
0x18001a904  sub     eax, [rsp+138h+var_B4]
0x18001a90b  xor     edx, edx
0x18001a90d  mov     r10d, [rsp+138h+var_D4]
0x18001a912  mov     r8d, 0
0x18001a918  div     ebx
0x18001a91a  mov     edx, [rsp+138h+var_E4]
0x18001a91e  sub     eax, esi
0x18001a920  cmovns  r8d, eax
0x18001a924  lea     eax, [r9+r8]
0x18001a928  inc     r8d
0x18001a92b  mov     [rsp+138h+var_CC], r8d
0x18001a930  cmp     eax, r10d
0x18001a933  jg      short loc_18001A999
0x18001a935  mov     esi, r8d
0x18001a938  mov     eax, r13d
0x18001a93b  imul    esi, r15d
0x18001a93f  mov     ebx, r8d
0x18001a942  mov     ecx, esi
0x18001a944  neg     ecx
0x18001a946  cmovs   ecx, esi
0x18001a949  neg     eax
0x18001a94b  cmovs   eax, r13d
0x18001a94f  cmp     ecx, eax
0x18001a951  mov     eax, edx
0x18001a953  cmovg   esi, r13d
0x18001a957  imul    ebx, r12d
0x18001a95b  mov     ecx, ebx
0x18001a95d  neg     ecx
0x18001a95f  cmovs   ecx, ebx
0x18001a962  neg     eax
0x18001a964  cmovs   eax, edx
0x18001a967  cmp     ecx, eax
0x18001a969  cmovg   ebx, edx
0x18001a96c  cmp     esi, r13d
0x18001a96f  jnz     short loc_18001A975
0x18001a971  cmp     ebx, edx
0x18001a973  jz      short loc_18001A99E
0x18001a975  mov     eax, esi
0x18001a977  neg     eax
0x18001a979  cmovs   eax, esi
0x18001a97c  cmp     eax, [rsp+138h+var_E0]
0x18001a980  jnb     short loc_18001A986
0x18001a982  test    esi, esi
0x18001a984  jnz     short loc_18001A924
0x18001a986  mov     eax, ebx
0x18001a988  neg     eax
0x18001a98a  cmovs   eax, ebx
0x18001a98d  cmp     eax, [rsp+138h+var_DC]
0x18001a991  jnb     short loc_18001A99E
0x18001a993  test    ebx, ebx
0x18001a995  jnz     short loc_18001A924
0x18001a997  jmp     short loc_18001A99E
0x18001a999  mov     esi, r13d
0x18001a99c  mov     ebx, edx
0x18001a99e  movzx   eax, word ptr [rsp+138h+var_D0]
0x18001a9a3  lea     r13, [rdi+8]
0x18001a9a7  mov     rcx, [r13+0]
0x18001a9ab  mov     r9, r14
0x18001a9ae  mov     [rsp+138h+var_100], eax
0x18001a9b2  mov     r8d, ebx
0x18001a9b5  lea     rax, [rsp+138h+rcSrc1]
0x18001a9bd  mov     edx, esi
0x18001a9bf  mov     [rsp+138h+var_108], rax
0x18001a9c4  mov     rax, [rsp+138h+hrgnUpdate]
0x18001a9c9  mov     [rsp+138h+var_110], rax
0x18001a9ce  mov     rax, [rsp+138h+var_A8]
0x18001a9d6  mov     [rsp+138h+var_118], rbp
0x18001a9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9e0  test    eax, eax
0x18001a9e2  jz      loc_18001AA86
0x18001a9e8  mov     r8, [rsp+138h+hrgnUpdate]; hrgnUpdate
0x18001a9ed  mov     r9d, 205h; flags
0x18001a9f3  mov     rcx, [r13+0]; hWnd
0x18001a9f7  xor     edx, edx; lprcUpdate
0x18001a9f9  call    cs:__imp_RedrawWindow
0x18001a9ff  mov     r8, [rsp+138h+lprcDst]; lprcSrc2
0x18001aa07  lea     rdx, [rsp+138h+rcSrc1]; lprcSrc1
0x18001aa0f  mov     rcx, r8; lprcDst
0x18001aa12  call    cs:__imp_UnionRect
0x18001aa18  test    r14, r14
0x18001aa1b  jz      short loc_18001AA38
0x18001aa1d  test    esi, esi
0x18001aa1f  jle     short loc_18001AA26
0x18001aa21  add     [r14], esi
  ... truncated ...
```

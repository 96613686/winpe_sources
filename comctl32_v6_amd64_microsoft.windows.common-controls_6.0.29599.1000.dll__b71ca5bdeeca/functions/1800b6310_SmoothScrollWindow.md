# SmoothScrollWindow

- ea: `0x1800b6310`
- end: `0x1800b68c7`
- name: `SmoothScrollWindow`
- size: `1463`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18000c79c`
- `0x180025ad0`
- `0x18003e490`
- `0x1800901dc`
- `0x1800b604c`
- `0x1800b6140`
- `0x1800c8d74`
- `0x18011aae0`
- `0x1801c6f50`
- `0x1801c9630`

## callees

- `0x180073d0c`
- `0x1800b6310`
- `0x180114520`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b648e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b6539`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b648e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b6539`
- `GDI32!DeleteObject` at `0x1800b66d6`
- `GDI32!DeleteObject` at `0x1800b66d6`
- `GDI32!CreateRectRgn` at `0x1800b6764`
- `GDI32!CreateRectRgn` at `0x1800b6764`
- `USER32!ScrollWindowEx` at `0x1800b6420`
- `USER32!SetRectEmpty` at `0x1800b63aa`
- `USER32!SetRectEmpty` at `0x1800b63aa`
- `USER32!GetDoubleClickTime` at `0x1800b64ad`
- `USER32!GetDoubleClickTime` at `0x1800b678b`
- `USER32!GetDoubleClickTime` at `0x1800b64ad`
- `USER32!GetDoubleClickTime` at `0x1800b678b`
- `USER32!UnionRect` at `0x1800b6645`
- `USER32!UnionRect` at `0x1800b6645`
- `USER32!RedrawWindow` at `0x1800b665e`
- `USER32!RedrawWindow` at `0x1800b68bc`
- `USER32!RedrawWindow` at `0x1800b665e`
- `USER32!RedrawWindow` at `0x1800b68bc`

## pseudocode

```c
__int64 __fastcall SmoothScrollWindow(__int64 a1)
{
  struct tagRECT *v1; // r14
  int v2; // esi
  unsigned int v4; // r15d
  int v5; // r12d
  __int128 *v6; // rbp
  int v7; // r13d
  UINT v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rcx
  int (__stdcall *v11)(HWND, int, int, const RECT *, const RECT *, HRGN, LPRECT, UINT); // rax
  HRGN RectRgn; // rax
  int v13; // eax
  signed int v14; // ecx
  int v15; // r14d
  int v16; // r15d
  unsigned int v17; // ebx
  DWORD v18; // eax
  int v19; // ecx
  int v20; // eax
  int v21; // eax
  int v22; // ecx
  int v23; // esi
  int v24; // ebx
  int v25; // ecx
  int v26; // eax
  int v27; // ecx
  int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // ebx
  int v33; // ecx
  int v34; // eax
  int v35; // ecx
  int v36; // eax
  __int128 v37; // xmm0
  __int128 v38; // xmm0
  int v39; // [rsp+50h] [rbp-F8h]
  unsigned int v40; // [rsp+54h] [rbp-F4h]
  int v41; // [rsp+58h] [rbp-F0h]
  int v42; // [rsp+5Ch] [rbp-ECh]
  unsigned int v43; // [rsp+60h] [rbp-E8h]
  int v44; // [rsp+64h] [rbp-E4h]
  __int128 *v45; // [rsp+70h] [rbp-D8h]
  HRGN hrgnUpdate; // [rsp+78h] [rbp-D0h]
  DWORD TickCount; // [rsp+80h] [rbp-C8h]
  UINT v48; // [rsp+88h] [rbp-C0h]
  HWND *v49; // [rsp+90h] [rbp-B8h]
  HRGN v50; // [rsp+98h] [rbp-B0h]
  int (__stdcall *v51)(HWND, int, int, const RECT *, const RECT *, HRGN, LPRECT, UINT); // [rsp+A0h] [rbp-A8h]
  LPRECT lprcDst; // [rsp+A8h] [rbp-A0h]
  __int128 v53; // [rsp+B0h] [rbp-98h] BYREF
  __int128 v54; // [rsp+C0h] [rbp-88h] BYREF
  RECT rcSrc1; // [rsp+D0h] [rbp-78h] BYREF
  __int128 v56; // [rsp+E0h] [rbp-68h] BYREF

  v1 = (struct tagRECT *)&v56;
  v2 = *(_DWORD *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 48) )
    v1 = *(struct tagRECT **)(a1 + 48);
  v4 = *(_DWORD *)(a1 + 68);
  v5 = *(_DWORD *)(a1 + 20);
  v6 = *(__int128 **)(a1 + 24);
  v7 = *(_DWORD *)(a1 + 56);
  v8 = *(_DWORD *)(a1 + 60);
  v45 = *(__int128 **)(a1 + 32);
  v50 = *(HRGN *)(a1 + 40);
  v9 = *(_DWORD *)(a1 + 64);
  v39 = *(_DWORD *)(a1 + 16);
  v56 = 0;
  v40 = v9;
  v53 = 0;
  v43 = v4;
  v54 = 0;
  lprcDst = v1;
  SetRectEmpty(v1);
  if ( *(_DWORD *)a1 != 80 )
    return 0;
  v10 = 0xFFFFFFFFLL;
  if ( ((*(_DWORD *)(a1 + 4) & 4) == 0 || v40 == -1) && (v40 = 8, (*(_DWORD *)(a1 + 4) & 4) == 0) || v4 == -1 )
    v43 = 8;
  if ( (*(_BYTE *)(a1 + 4) & 2) == 0 || v8 == -1 )
    v8 = (GetDoubleClickTime() >> 1) + 1;
  v42 = 100;
  if ( v8 < 0x64 )
    v8 = 100;
  v48 = v8;
  if ( (v7 & 0x40000) == 0 )
  {
    CSystemMetrics::EnsureValidRegistry((CSystemMetrics *)v10);
    if ( !*(_DWORD *)&Data )
      v7 |= 0x20000u;
  }
  if ( (*(_BYTE *)(a1 + 4) & 1) == 0
    || (v11 = *(int (__stdcall **)(HWND, int, int, const RECT *, const RECT *, HRGN, LPRECT, UINT))(a1 + 72),
        (v51 = v11) == 0) )
  {
    v11 = ScrollWindowEx;
    v51 = ScrollWindowEx;
  }
  if ( (v7 & 0x20000) != 0 )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int128 *, __int128 *, HRGN, struct tagRECT *, _DWORD))v11)(
             *(_QWORD *)(a1 + 8),
             (unsigned int)v2,
             (unsigned int)v5,
             v6,
             v45,
             v50,
             v1,
             (unsigned __int16)v7);
  v44 = 0;
  v41 = 0;
  if ( v6 )
  {
    v37 = *v6;
    v6 = &v53;
    v53 = v37;
  }
  if ( v45 )
  {
    v38 = *v45;
    v45 = &v54;
    v54 = v38;
  }
  RectRgn = v50;
  if ( !v50 )
    RectRgn = CreateRectRgn(0, 0, 0, 0);
  hrgnUpdate = RectRgn;
  TickCount = GetTickCount();
  v13 = v7 & 0x10000;
  if ( (v7 & 0x10000) != 0 )
  {
    v15 = v40 * (((v2 >> 31) & 0xFFFFFFFE) + 1);
    v16 = v43 * (((v5 >> 31) & 0xFFFFFFFE) + 1);
  }
  else
  {
    v14 = 100 * (v8 / ((GetDoubleClickTime() >> 1) + 1));
    if ( !v14 )
      v14 = 100;
    v42 = v14;
    v15 = v2 / v14;
    v16 = v5 / v14;
    v13 = 0;
  }
  if ( !v15 )
  {
    if ( v2 )
    {
      v15 = 1;
      if ( v2 < 0 )
        v15 = -1;
    }
  }
  if ( !v16 )
  {
    if ( v5 )
    {
      v16 = 1;
      if ( v5 < 0 )
        v16 = -1;
    }
  }
  v49 = (HWND *)(a1 + 8);
  while ( 1 )
  {
    if ( !v2 && !v5 )
    {
      v31 = 2;
      goto LABEL_66;
    }
    rcSrc1 = 0;
    if ( !v13 )
    {
      v17 = v8 / v42;
      if ( !v17 )
        v17 = 1;
      v18 = GetTickCount();
      v19 = 0;
      v20 = (v18 - TickCount) / v17 - v44;
      if ( v20 >= 0 )
        v19 = v20;
      while ( 1 )
      {
        v21 = v44 + 1 + v19;
        v22 = v19 + 1;
        v41 = v22;
        if ( v21 > v42 )
          break;
        v23 = v15 * v22;
        v24 = v16 * v22;
        v25 = -(v15 * v22);
        if ( v25 < 0 )
          v25 = v23;
        v26 = -v39;
        if ( v39 > 0 )
          v26 = v39;
        if ( v25 > v26 )
          v23 = v39;
        v27 = -v24;
        if ( v24 > 0 )
          v27 = v24;
        v28 = -v5;
        if ( v5 > 0 )
          v28 = v5;
        if ( v27 > v28 )
          v24 = v5;
        if ( v24 == v5 && v23 == v39 )
          goto LABEL_57;
        v29 = -v23;
        if ( v23 > 0 )
          v29 = v23;
        if ( v29 < v40 )
        {
          v19 = v41;
          if ( v23 )
            continue;
        }
        v30 = -v24;
        if ( v24 > 0 )
          v30 = v24;
        if ( v30 >= v43 || !v24 )
          goto LABEL_57;
        v19 = v41;
      }
      v23 = v39;
LABEL_86:
      v24 = v5;
      goto LABEL_57;
    }
    v33 = -v15;
    v24 = v16;
    if ( v15 > 0 )
      v33 = v15;
    v34 = -v2;
    if ( v2 > 0 )
      v34 = v2;
    v23 = v15;
    if ( v33 > v34 )
      v23 = v39;
    v35 = -v16;
    if ( v16 > 0 )
      v35 = v16;
    v36 = -v5;
    if ( v5 > 0 )
      v36 = v5;
    if ( v35 > v36 )
      goto LABEL_86;
LABEL_57:
    v49 = (HWND *)(a1 + 8);
    if ( !((unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, __int128 *, __int128 *, HRGN, RECT *, _DWORD))v51)(
            *(_QWORD *)(a1 + 8),
            (unsigned int)v23,
            (unsigned int)v24,
            v6,
            v45,
            hrgnUpdate,
            &rcSrc1,
            (unsigned __int16)v7) )
      break;
    UnionRect(lprcDst, &rcSrc1, lprcDst);
    RedrawWindow(*(HWND *)(a1 + 8), 0, hrgnUpdate, (v7 & 0x80000 | 0x102800u) >> 11);
    if ( v6 )
    {
      if ( v23 > 0 )
        *(_DWORD *)v6 += v23;
      else
        *((_DWORD *)v6 + 2) += v23;
      if ( v24 <= 0 )
        *((_DWORD *)v6 + 3) += v24;
      else
        *((_DWORD *)v6 + 1) += v24;
    }
    v39 -= v23;
    v5 -= v24;
    v8 = v48;
    v2 = v39;
    v44 += v41;
    v13 = v7 & 0x10000;
  }
  v31 = 0;
LABEL_66:
  if ( (v7 & 1) != 0 )
    RedrawWindow(*v49, lprcDst, 0, 0x105u);
  if ( hrgnUpdate != v50 )
    DeleteObject(hrgnUpdate);
  return v31;
}

```

## disassembly

```asm
0x1800b6310  mov     r11, rsp
0x1800b6313  push    rbx
0x1800b6314  push    rbp
0x1800b6315  push    rsi
0x1800b6316  push    rdi
0x1800b6317  push    r12
0x1800b6319  push    r13
0x1800b631b  push    r14
0x1800b631d  push    r15
0x1800b631f  sub     rsp, 108h
0x1800b6326  mov     rax, cs:__security_cookie
0x1800b632d  xor     rax, rsp
0x1800b6330  mov     [rsp+148h+var_58], rax
0x1800b6338  mov     rax, [rcx+20h]
0x1800b633c  lea     r14, [r11-68h]
0x1800b6340  cmp     qword ptr [rcx+30h], 0
0x1800b6345  xorps   xmm0, xmm0
0x1800b6348  mov     esi, [rcx+10h]
0x1800b634b  mov     rdi, rcx
0x1800b634e  cmovnz  r14, [rcx+30h]
0x1800b6353  xorps   xmm1, xmm1
0x1800b6356  mov     r15d, [rcx+44h]
0x1800b635a  mov     r12d, [rcx+14h]
0x1800b635e  mov     rbp, [rcx+18h]
0x1800b6362  mov     r13d, [rcx+38h]
0x1800b6366  mov     ebx, [rcx+3Ch]
0x1800b6369  mov     [rsp+148h+var_D8], rax
0x1800b636e  mov     rax, [rcx+28h]
0x1800b6372  mov     [rsp+148h+var_B0], rax
0x1800b637a  mov     eax, [rcx+40h]
0x1800b637d  mov     rcx, r14; lprc
0x1800b6380  mov     [rsp+148h+var_F8], esi
0x1800b6384  movups  xmmword ptr [r11-68h], xmm0
0x1800b6389  mov     [rsp+148h+var_F4], eax
0x1800b638d  movups  [rsp+148h+var_98], xmm1
0x1800b6395  mov     [rsp+148h+var_E8], r15d
0x1800b639a  movups  [rsp+148h+var_88], xmm0
0x1800b63a2  mov     [rsp+148h+lprcDst], r14
0x1800b63aa  call    cs:__imp_SetRectEmpty
0x1800b63b0  cmp     dword ptr [rdi], 50h ; 'P'
0x1800b63b3  jnz     loc_1800B6756
0x1800b63b9  mov     eax, [rdi+4]
0x1800b63bc  or      ecx, 0FFFFFFFFh; this
0x1800b63bf  mov     edx, 8
0x1800b63c4  and     eax, 4
0x1800b63c7  jz      loc_1800B679C
0x1800b63cd  cmp     [rsp+148h+var_F4], ecx
0x1800b63d1  jz      loc_1800B679C
0x1800b63d7  cmp     r15d, ecx
0x1800b63da  jz      loc_1800B67A8
0x1800b63e0  test    byte ptr [rdi+4], 2
0x1800b63e4  jz      loc_1800B678B
0x1800b63ea  cmp     ebx, ecx
0x1800b63ec  jz      loc_1800B678B
0x1800b63f2  mov     r15d, 64h ; 'd'
0x1800b63f8  cmp     ebx, r15d
0x1800b63fb  mov     [rsp+148h+var_EC], r15d
0x1800b6400  cmovb   ebx, r15d
0x1800b6404  mov     [rsp+148h+var_C0], ebx
0x1800b640b  bt      r13d, 12h
0x1800b6410  jnb     loc_1800B676F
0x1800b6416  test    byte ptr [rdi+4], 1
0x1800b641a  jnz     loc_1800B67B1
0x1800b6420  mov     rax, cs:__imp_ScrollWindowEx
0x1800b6427  mov     [rsp+148h+var_A8], rax
0x1800b642f  bt      r13d, 11h
0x1800b6434  jb      loc_1800B67CB
0x1800b643a  mov     eax, r13d
0x1800b643d  mov     [rsp+148h+var_E4], 0
0x1800b6445  and     eax, 80000h
0x1800b644a  mov     [rsp+148h+var_F0], 0
0x1800b6452  or      eax, 102800h
0x1800b6457  shr     eax, 0Bh
0x1800b645a  mov     [rsp+148h+flags], eax
0x1800b6461  test    rbp, rbp
0x1800b6464  jnz     loc_1800B6805
0x1800b646a  mov     rcx, [rsp+148h+var_D8]
0x1800b646f  test    rcx, rcx
0x1800b6472  jnz     loc_1800B681F
0x1800b6478  mov     rax, [rsp+148h+var_B0]
0x1800b6480  test    rax, rax
0x1800b6483  jz      loc_1800B675A
0x1800b6489  mov     [rsp+148h+hrgnUpdate], rax
0x1800b648e  call    cs:__imp_GetTickCount
0x1800b6494  mov     [rsp+148h+var_C8], eax
0x1800b649b  mov     eax, r13d
0x1800b649e  and     eax, 10000h
0x1800b64a3  mov     [rsp+148h+var_E0], eax
0x1800b64a7  jnz     loc_1800B683D
0x1800b64ad  call    cs:__imp_GetDoubleClickTime
0x1800b64b3  xor     edx, edx
0x1800b64b5  mov     r8d, 1
0x1800b64bb  mov     ecx, eax
0x1800b64bd  mov     eax, ebx
0x1800b64bf  shr     ecx, 1
0x1800b64c1  add     ecx, r8d
0x1800b64c4  div     ecx
0x1800b64c6  imul    ecx, eax, 64h ; 'd'
0x1800b64c9  mov     eax, esi
0x1800b64cb  cdq
0x1800b64cc  test    ecx, ecx
0x1800b64ce  cmovz   ecx, r15d
0x1800b64d2  idiv    ecx
0x1800b64d4  mov     [rsp+148h+var_EC], ecx
0x1800b64d8  mov     r14d, eax
0x1800b64db  mov     eax, r12d
0x1800b64de  cdq
0x1800b64df  idiv    ecx
0x1800b64e1  mov     r15d, eax
0x1800b64e4  mov     eax, [rsp+148h+var_E0]
0x1800b64e8  or      ecx, 0FFFFFFFFh
0x1800b64eb  test    r14d, r14d
0x1800b64ee  jz      loc_1800B6870
0x1800b64f4  test    r15d, r15d
0x1800b64f7  jz      loc_1800B6884
0x1800b64fd  lea     rcx, [rdi+8]
0x1800b6501  mov     [rsp+148h+var_B8], rcx
0x1800b6509  test    esi, esi
0x1800b650b  jnz     short loc_1800B6516
0x1800b650d  test    r12d, r12d
0x1800b6510  jz      loc_1800B66AD
0x1800b6516  xorps   xmm0, xmm0
0x1800b6519  movups  xmmword ptr [rsp+148h+rcSrc1.left], xmm0
0x1800b6521  test    eax, eax
0x1800b6523  jnz     loc_1800B6713
0x1800b6529  mov     eax, ebx
0x1800b652b  xor     edx, edx
0x1800b652d  div     [rsp+148h+var_EC]
0x1800b6531  test    eax, eax
0x1800b6533  mov     ebx, eax
0x1800b6535  cmovz   ebx, r8d
0x1800b6539  call    cs:__imp_GetTickCount
0x1800b653f  mov     r9d, [rsp+148h+var_E4]
0x1800b6544  xor     edx, edx
0x1800b6546  sub     eax, [rsp+148h+var_C8]
0x1800b654d  mov     ecx, 0
0x1800b6552  mov     r8d, [rsp+148h+var_EC]
0x1800b6557  div     ebx
0x1800b6559  mov     edx, [rsp+148h+var_F8]
0x1800b655d  sub     eax, r9d
0x1800b6560  cmovns  ecx, eax
0x1800b6563  inc     r9d
0x1800b6566  lea     eax, [r9+rcx]
0x1800b656a  inc     ecx
0x1800b656c  mov     [rsp+148h+var_F0], ecx
0x1800b6570  cmp     eax, r8d
0x1800b6573  jg      loc_1800B674C
0x1800b6579  mov     esi, ecx
0x1800b657b  mov     ebx, ecx
0x1800b657d  imul    esi, r14d
0x1800b6581  mov     eax, edx
0x1800b6583  imul    ebx, r15d
0x1800b6587  mov     ecx, esi
0x1800b6589  neg     ecx
0x1800b658b  cmovs   ecx, esi
0x1800b658e  neg     eax
0x1800b6590  cmovs   eax, edx
0x1800b6593  cmp     ecx, eax
0x1800b6595  mov     ecx, ebx
0x1800b6597  mov     eax, r12d
0x1800b659a  cmovg   esi, edx
0x1800b659d  neg     ecx
0x1800b659f  cmovs   ecx, ebx
0x1800b65a2  neg     eax
0x1800b65a4  cmovs   eax, r12d
0x1800b65a8  cmp     ecx, eax
0x1800b65aa  cmovg   ebx, r12d
0x1800b65ae  cmp     ebx, r12d
0x1800b65b1  jnz     short loc_1800B65B7
0x1800b65b3  cmp     esi, edx
0x1800b65b5  jz      short loc_1800B65DD
0x1800b65b7  mov     eax, esi
0x1800b65b9  neg     eax
0x1800b65bb  cmovs   eax, esi
0x1800b65be  cmp     eax, [rsp+148h+var_F4]
0x1800b65c2  jnb     short loc_1800B65CC
0x1800b65c4  mov     ecx, [rsp+148h+var_F0]
0x1800b65c8  test    esi, esi
0x1800b65ca  jnz     short loc_1800B6566
0x1800b65cc  mov     eax, ebx
0x1800b65ce  neg     eax
0x1800b65d0  cmovs   eax, ebx
0x1800b65d3  cmp     eax, [rsp+148h+var_E8]
0x1800b65d7  jb      loc_1800B6702
0x1800b65dd  movzx   eax, r13w
0x1800b65e1  lea     rcx, [rdi+8]
0x1800b65e5  mov     [rsp+148h+var_110], eax
0x1800b65e9  mov     r9, rbp
0x1800b65ec  lea     rax, [rsp+148h+rcSrc1]
0x1800b65f4  mov     [rsp+148h+var_B8], rcx
0x1800b65fc  mov     rcx, [rcx]
0x1800b65ff  mov     r8d, ebx
0x1800b6602  mov     [rsp+148h+var_118], rax
0x1800b6607  mov     edx, esi
0x1800b6609  mov     rax, [rsp+148h+hrgnUpdate]
0x1800b660e  mov     [rsp+148h+var_120], rax
0x1800b6613  mov     rax, [rsp+148h+var_D8]
0x1800b6618  mov     [rsp+148h+var_128], rax
0x1800b661d  mov     rax, [rsp+148h+var_A8]
0x1800b6625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b662a  test    eax, eax
0x1800b662c  jz      loc_1800B68A1
0x1800b6632  mov     r8, [rsp+148h+lprcDst]; lprcSrc2
0x1800b663a  lea     rdx, [rsp+148h+rcSrc1]; lprcSrc1
0x1800b6642  mov     rcx, r8; lprcDst
0x1800b6645  call    cs:__imp_UnionRect
0x1800b664b  mov     r9d, [rsp+148h+flags]; flags
0x1800b6653  xor     edx, edx; lprcUpdate
0x1800b6655  mov     r8, [rsp+148h+hrgnUpdate]; hrgnUpdate
0x1800b665a  mov     rcx, [rdi+8]; hWnd
0x1800b665e  call    cs:__imp_RedrawWindow
0x1800b6664  test    rbp, rbp
0x1800b6667  jz      short loc_1800B667B
0x1800b6669  test    esi, esi
0x1800b666b  jg      loc_1800B6899
0x1800b6671  add     [rbp+8], esi
0x1800b6674  test    ebx, ebx
0x1800b6676  jle     short loc_1800B66A8
0x1800b6678  add     [rbp+4], ebx
0x1800b667b  sub     [rsp+148h+var_F8], esi
0x1800b667f  sub     r12d, ebx
0x1800b6682  mov     eax, [rsp+148h+var_E4]
0x1800b6686  mov     r8d, 1
0x1800b668c  add     eax, [rsp+148h+var_F0]
0x1800b6690  mov     ebx, [rsp+148h+var_C0]
0x1800b6697  mov     esi, [rsp+148h+var_F8]
0x1800b669b  mov     [rsp+148h+var_E4], eax
0x1800b669f  mov     eax, [rsp+148h+var_E0]
0x1800b66a3  jmp     loc_1800B6509
0x1800b66a8  add     [rbp+0Ch], ebx
0x1800b66ab  jmp     short loc_1800B667B
0x1800b66ad  mov     ebx, 2
0x1800b66b2  mov     rax, [rsp+148h+var_B8]
0x1800b66ba  test    r13b, 1
0x1800b66be  jnz     loc_1800B68A8
0x1800b66c4  mov     rax, [rsp+148h+hrgnUpdate]
0x1800b66c9  cmp     rax, [rsp+148h+var_B0]
0x1800b66d1  jz      short loc_1800B66DC
0x1800b66d3  mov     rcx, rax; ho
0x1800b66d6  call    cs:__imp_DeleteObject
0x1800b66dc  mov     eax, ebx
0x1800b66de  mov     rcx, [rsp+148h+var_58]
0x1800b66e6  xor     rcx, rsp; StackCookie
0x1800b66e9  call    __security_check_cookie
0x1800b66ee  add     rsp, 108h
0x1800b66f5  pop     r15
0x1800b66f7  pop     r14
0x1800b66f9  pop     r13
0x1800b66fb  pop     r12
0x1800b66fd  pop     rdi
0x1800b66fe  pop     rsi
0x1800b66ff  pop     rbp
0x1800b6700  pop     rbx
0x1800b6701  retn
0x1800b6702  test    ebx, ebx
0x1800b6704  jz      loc_1800B65DD
0x1800b670a  mov     ecx, [rsp+148h+var_F0]
0x1800b670e  jmp     loc_1800B6566
0x1800b6713  mov     eax, esi
0x1800b6715  mov     ecx, r14d
0x1800b6718  neg     ecx
0x1800b671a  mov     ebx, r15d
0x1800b671d  cmovs   ecx, r14d
0x1800b6721  neg     eax
0x1800b6723  cmovs   eax, esi
0x1800b6726  mov     esi, r14d
0x1800b6729  cmp     ecx, eax
0x1800b672b  mov     ecx, r15d
0x1800b672e  mov     eax, r12d
0x1800b6731  cmovg   esi, [rsp+148h+var_F8]
0x1800b6736  neg     ecx
0x1800b6738  cmovs   ecx, r15d
0x1800b673c  neg     eax
0x1800b673e  cmovs   eax, r12d
0x1800b6742  cmp     ecx, eax
0x1800b6744  jle     loc_1800B65DD
0x1800b674a  jmp     short loc_1800B674E
0x1800b674c  mov     esi, edx
0x1800b674e  mov     ebx, r12d
0x1800b6751  jmp     loc_1800B65DD
0x1800b6756  xor     eax, eax
0x1800b6758  jmp     short loc_1800B66DE
0x1800b675a  xor     r9d, r9d; y2
0x1800b675d  xor     r8d, r8d; x2
0x1800b6760  xor     edx, edx; y1
0x1800b6762  xor     ecx, ecx; x1
0x1800b6764  call    cs:__imp_CreateRectRgn
0x1800b676a  jmp     loc_1800B6489
0x1800b676f  call    ?EnsureValidRegistry@CSystemMetrics@@AEAAXXZ; CSystemMetrics::EnsureValidRegistry(void)
0x1800b6774  cmp     cs:Data, 0
0x1800b677b  jnz     loc_1800B6416
0x1800b6781  bts     r13d, 11h
0x1800b6786  jmp     loc_1800B6416
0x1800b678b  call    cs:__imp_GetDoubleClickTime
0x1800b6791  mov     ebx, eax
0x1800b6793  shr     ebx, 1
0x1800b6795  inc     ebx
0x1800b6797  jmp     loc_1800B63F2
0x1800b679c  mov     [rsp+148h+var_F4], edx
0x1800b67a0  test    eax, eax
  ... truncated ...
```

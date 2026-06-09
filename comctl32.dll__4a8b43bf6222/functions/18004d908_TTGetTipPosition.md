# TTGetTipPosition

- ea: `0x18004d908`
- end: `0x18004dddc`
- name: `TTGetTipPosition`
- size: `1236`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004ca94`

## callees

- `0x1800115f0`
- `0x18004d908`
- `0x18005029c`

## import_xrefs

- `USER32!GetWindowLongW` at `0x18004dc89`
- `USER32!GetWindowLongW` at `0x18004dc89`
- `USER32!MapWindowPoints` at `0x18004da21`
- `USER32!MapWindowPoints` at `0x18004da21`
- `USER32!PtInRect` at `0x18004dc08`
- `USER32!PtInRect` at `0x18004dc08`
- `USER32!GetMessagePos` at `0x18004dcd4`
- `USER32!GetMessagePos` at `0x18004dcd4`
- `USER32!CopyRect` at `0x18004dc9f`
- `USER32!CopyRect` at `0x18004dc9f`
- `USER32!GetMonitorInfoW` at `0x18004dbfa`
- `USER32!GetMonitorInfoW` at `0x18004dc7b`
- `USER32!GetMonitorInfoW` at `0x18004dbfa`
- `USER32!GetMonitorInfoW` at `0x18004dc7b`
- `USER32!MonitorFromPoint` at `0x18004dbc9`
- `USER32!MonitorFromPoint` at `0x18004dbe0`
- `USER32!MonitorFromPoint` at `0x18004dc67`
- `USER32!MonitorFromPoint` at `0x18004dbc9`
- `USER32!MonitorFromPoint` at `0x18004dbe0`
- `USER32!MonitorFromPoint` at `0x18004dc67`
- `USER32!GetWindowRect` at `0x18004da00`
- `USER32!GetWindowRect` at `0x18004da00`

## pseudocode

```c
__int64 __fastcall TTGetTipPosition(__int64 a1, int *a2, int a3, int a4, _DWORD *a5, __int64 a6)
{
  int v7; // ecx
  _DWORD *v8; // r12
  int v10; // ecx
  int v11; // r13d
  int v12; // esi
  int v13; // ecx
  int v14; // r14d
  int v15; // edx
  int v16; // r13d
  int v17; // eax
  int v18; // ecx
  __int64 v19; // rcx
  LONG *v20; // r15
  int v21; // ecx
  LONG v22; // r8d
  LONG v23; // ecx
  int v24; // edx
  LONG v25; // r9d
  int v26; // r12d
  LONG right; // ecx
  LONG left; // r8d
  LONG bottom; // r9d
  int v30; // eax
  LONG v31; // r12d
  HMONITOR v32; // rax
  HMONITOR v33; // rax
  HMONITOR v34; // rax
  char WindowLongW; // al
  RECT *p_rcMonitor; // rdx
  LONG v37; // ecx
  LONG top; // ecx
  unsigned int v39; // edx
  LONG v40; // eax
  LONG v41; // ecx
  LONG v42; // r8d
  int v43; // eax
  __int64 result; // rax
  int v45; // ecx
  _DWORD *v46; // rcx
  int v47; // [rsp+20h] [rbp-79h]
  unsigned int x; // [rsp+24h] [rbp-75h]
  POINT pt; // [rsp+28h] [rbp-71h] BYREF
  int v50; // [rsp+30h] [rbp-69h] BYREF
  POINT v51; // [rsp+38h] [rbp-61h]
  __int64 v52; // [rsp+40h] [rbp-59h]
  HMONITOR hMonitor; // [rsp+48h] [rbp-51h]
  __int64 v54; // [rsp+50h] [rbp-49h]
  struct tagRECT Rect; // [rsp+58h] [rbp-41h] BYREF
  struct tagRECT rcDst; // [rsp+68h] [rbp-31h] BYREF
  struct tagMONITORINFO mi; // [rsp+78h] [rbp-21h] BYREF

  v7 = *(_DWORD *)(a1 + 216);
  v8 = a5;
  v54 = a6;
  v10 = a3 + *(_DWORD *)(a1 + 208) + v7;
  v11 = *(_DWORD *)(a1 + 16);
  v52 = (__int64)a5;
  rcDst = 0;
  v12 = v10 + 4 * g_cxBorder;
  v13 = a4 + *(_DWORD *)(a1 + 212) + *(_DWORD *)(a1 + 220);
  Rect = 0;
  memset(&mi, 0, sizeof(mi));
  v14 = v13 + 2 * g_cyBorder;
  v15 = 0;
  v47 = 0;
  x = 0;
  pt.x = 0;
  v50 = 0;
  v16 = v11 & 0x40;
  if ( v16 || *(_DWORD *)(a1 + 160) )
  {
    v17 = v12 + 20;
    v18 = v14 + 16;
    v12 += 20;
    v14 += 16;
    if ( v16 )
    {
      if ( v17 < 30 || (*(_DWORD *)(a1 + 224) = 20, v15 = v18 / 3, v18 / 3 < 20) )
        *(_DWORD *)(a1 + 224) = v15;
    }
  }
  v19 = *(_QWORD *)(a1 + 80);
  if ( (*(_BYTE *)(v19 + 4) & 1) != 0 )
  {
    GetWindowRect(*(HWND *)(v19 + 16), &Rect);
  }
  else
  {
    Rect = *(struct tagRECT *)(v19 + 24);
    MapWindowPoints(*(HWND *)(v19 + 8), 0, (LPPOINT)&Rect, 2u);
  }
  v20 = a2 + 1;
  v21 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 4LL);
  if ( (v21 & 0x20) == 0 )
  {
    if ( (v21 & 2) != 0 )
    {
      right = Rect.right;
      left = Rect.left;
      bottom = Rect.bottom;
      v30 = Rect.left + Rect.right - v12;
      *v20 = Rect.bottom;
      *a2 = v30 / 2;
      if ( v16 )
      {
        x = bottom;
        v47 = (right + left) / 2;
LABEL_40:
        if ( (*(_BYTE *)(*(_QWORD *)(a1 + 80) + 4LL) & 2) == 0 && v12 > *(_DWORD *)(a1 + 224) + 16 )
          *a2 -= 16;
        v14 += *(_DWORD *)(a1 + 224);
      }
    }
    else
    {
      GetCursorLowerLeft(a2, a2 + 1, &v50, &pt);
      if ( v16 )
      {
        pt.y = *v20;
        x = pt.y - pt.x;
        v47 = *a2;
        v31 = pt.y - pt.x - *(_DWORD *)(a1 + 224) - v14;
        pt.x = *a2;
        v51.x = pt.y;
        v32 = MonitorFromPoint(pt, 2u);
        pt.y = v31;
        hMonitor = v32;
        v33 = MonitorFromPoint(pt, 2u);
        if ( hMonitor == v33 && (mi.cbSize = 40, GetMonitorInfoW(hMonitor, &mi), PtInRect(&mi.rcMonitor, pt)) )
        {
          *v20 = v31;
        }
        else
        {
          x = v51.x;
          v47 += v50 / 2;
        }
        goto LABEL_40;
      }
    }
    v26 = -1;
    goto LABEL_45;
  }
  v22 = *(_DWORD *)(a1 + 184);
  *a2 = v22;
  v23 = *(_DWORD *)(a1 + 188);
  *v20 = v23;
  if ( v16 )
  {
    v47 = *(_DWORD *)(a1 + 184);
    x = *(_DWORD *)(a1 + 188);
  }
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 80) + 4LL) & 2) != 0 )
  {
    v22 -= v12 / 2;
    *a2 = v22;
    if ( !v16 )
    {
      v23 -= v14 / 2;
      *v20 = v23;
    }
  }
  if ( *(char *)(*(_QWORD *)(a1 + 80) + 4LL) < 0 )
  {
    if ( v16 )
      v14 += *(_DWORD *)(a1 + 224);
    v24 = v47;
    goto LABEL_79;
  }
  if ( v16 )
    goto LABEL_40;
  v25 = *(_DWORD *)(a1 + 188);
  if ( v25 <= Rect.bottom )
  {
    if ( *(_DWORD *)(a1 + 184) >= Rect.left )
    {
      if ( v25 >= Rect.top )
      {
        v26 = 3;
        if ( v22 < Rect.right )
          *a2 = Rect.right;
      }
      else
      {
        v26 = 0;
        if ( v23 + v14 > Rect.top )
          *v20 = Rect.top - v14;
      }
    }
    else
    {
      v26 = 1;
      if ( v22 + v12 > Rect.left )
        *a2 = Rect.left - v12;
    }
  }
  else
  {
    v26 = 2;
    if ( v23 < Rect.bottom )
      *v20 = Rect.bottom;
  }
LABEL_45:
  v51.x = *a2;
  v51.y = *v20;
  v34 = MonitorFromPoint(v51, 2u);
  mi.cbSize = 40;
  GetMonitorInfoW(v34, &mi);
  WindowLongW = GetWindowLongW(*(HWND *)a1, -20);
  p_rcMonitor = &mi.rcMonitor;
  if ( (WindowLongW & 8) == 0 )
    p_rcMonitor = &mi.rcWork;
  CopyRect(&rcDst, p_rcMonitor);
  v37 = *v20;
  if ( *v20 + v14 >= rcDst.bottom )
  {
    if ( v26 == 2 )
    {
      top = Rect.top;
LABEL_52:
      v37 = top - v14;
      *v20 = v37;
      goto LABEL_55;
    }
    if ( (*(_BYTE *)(*(_QWORD *)(a1 + 80) + 4LL) & 0x20) != 0 )
    {
      top = *(_DWORD *)(a1 + 188);
      goto LABEL_52;
    }
    v39 = (__int16)(GetMessagePos() >> 16);
    v37 = v39 - v14;
    *v20 = v39 - v14;
    if ( v16 )
      x = v39;
  }
LABEL_55:
  v40 = rcDst.top;
  if ( v37 < rcDst.top )
  {
    if ( !v26 )
      v40 = Rect.bottom;
    *v20 = v40;
  }
  v41 = *a2;
  v42 = rcDst.right;
  if ( *a2 + v12 < rcDst.right )
  {
    v24 = v47;
    goto LABEL_72;
  }
  if ( v16 )
  {
    if ( v12 < 30 )
    {
      v24 = v47;
    }
    else
    {
      v24 = v47;
      v43 = (v12 - *(_DWORD *)(a1 + 224)) / 2;
      if ( v43 > 16 )
        v43 = 16;
      v41 = v43 - v12 + v47;
      *a2 = v41;
    }
    if ( v41 + v12 < v42 )
      goto LABEL_72;
  }
  else
  {
    v24 = v47;
    if ( v26 == 3 )
    {
      v41 = Rect.left - v12;
      goto LABEL_70;
    }
  }
  v41 = v42 - v12 - 1;
LABEL_70:
  *a2 = v41;
LABEL_72:
  v22 = rcDst.left;
  if ( v41 >= rcDst.left )
  {
    v22 = v41;
  }
  else
  {
    if ( v26 == 1 && !v16 )
      v22 = Rect.right;
    *a2 = v22;
  }
  v8 = (_DWORD *)v52;
LABEL_79:
  result = (unsigned int)(v22 + v12);
  v45 = v14 + *v20;
  a2[2] = result;
  a2[3] = v45;
  if ( v16 && v8 )
  {
    v46 = (_DWORD *)v54;
    if ( v54 )
    {
      result = x;
      *v8 = v24;
      *v46 = x;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004d908  mov     [rsp-8+arg_10], rbx
0x18004d90d  push    rbp
0x18004d90e  push    rsi
0x18004d90f  push    rdi
0x18004d910  push    r12
0x18004d912  push    r13
0x18004d914  push    r14
0x18004d916  push    r15
0x18004d918  lea     rbp, [rsp-17h]
0x18004d91d  sub     rsp, 0B0h
0x18004d924  mov     rax, cs:__security_cookie
0x18004d92b  xor     rax, rsp
0x18004d92e  mov     [rbp+47h+var_40], rax
0x18004d932  mov     rax, [rbp+47h+arg_28]
0x18004d936  mov     rbx, rcx
0x18004d939  mov     ecx, [rcx+0D8h]
0x18004d93f  xorps   xmm0, xmm0
0x18004d942  mov     r12, [rbp+47h+arg_20]
0x18004d946  xorps   xmm1, xmm1
0x18004d949  mov     [rbp+47h+var_90], rax
0x18004d94d  mov     rdi, rdx
0x18004d950  add     ecx, [rbx+0D0h]
0x18004d956  mov     eax, cs:g_cxBorder
0x18004d95c  add     ecx, r8d
0x18004d95f  mov     r13d, [rbx+10h]
0x18004d963  mov     [rbp+47h+var_A0], r12
0x18004d967  movups  xmmword ptr [rbp+47h+rcDst.left], xmm0
0x18004d96b  lea     esi, [rcx+rax*4]
0x18004d96e  mov     ecx, [rbx+0DCh]
0x18004d974  add     ecx, [rbx+0D4h]
0x18004d97a  mov     eax, cs:g_cyBorder
0x18004d980  add     ecx, r9d
0x18004d983  movups  xmmword ptr [rbp+47h+Rect.left], xmm0
0x18004d987  movups  xmmword ptr [rbp+47h+mi.cbSize], xmm1
0x18004d98b  lea     r14d, [rcx+rax*2]
0x18004d98f  xor     eax, eax
0x18004d991  mov     qword ptr [rbp+47h+mi.rcWork.bottom], rax
0x18004d995  mov     edx, eax
0x18004d997  mov     [rbp+47h+var_C0], edx
0x18004d99a  mov     [rbp+47h+var_BC], edx
0x18004d99d  mov     [rbp+47h+pt.x], edx
0x18004d9a0  mov     [rbp+47h+var_B0], edx
0x18004d9a3  movups  xmmword ptr [rbp+47h+mi.rcMonitor.bottom], xmm1
0x18004d9a7  and     r13d, 40h
0x18004d9ab  jnz     short loc_18004D9B5
0x18004d9ad  cmp     [rbx+0A0h], edx
0x18004d9b3  jz      short loc_18004D9EE
0x18004d9b5  lea     eax, [rsi+14h]
0x18004d9b8  lea     ecx, [r14+10h]
0x18004d9bc  mov     esi, eax
0x18004d9be  mov     r14d, ecx
0x18004d9c1  test    r13d, r13d
0x18004d9c4  jz      short loc_18004D9EE
0x18004d9c6  cmp     eax, 1Eh
0x18004d9c9  jl      short loc_18004D9E8
0x18004d9cb  mov     eax, 55555556h
0x18004d9d0  mov     dword ptr [rbx+0E0h], 14h
0x18004d9da  imul    ecx
0x18004d9dc  mov     eax, edx
0x18004d9de  shr     eax, 1Fh
0x18004d9e1  add     edx, eax
0x18004d9e3  cmp     edx, 14h
0x18004d9e6  jge     short loc_18004D9EE
0x18004d9e8  mov     [rbx+0E0h], edx
0x18004d9ee  mov     rcx, [rbx+50h]
0x18004d9f2  test    byte ptr [rcx+4], 1
0x18004d9f6  jz      short loc_18004DA08
0x18004d9f8  mov     rcx, [rcx+10h]; hWnd
0x18004d9fc  lea     rdx, [rbp+47h+Rect]; lpRect
0x18004da00  call    cs:__imp_GetWindowRect
0x18004da06  jmp     short loc_18004DA27
0x18004da08  movups  xmm0, xmmword ptr [rcx+18h]
0x18004da0c  mov     r9d, 2; cPoints
0x18004da12  lea     r8, [rbp+47h+Rect]; lpPoints
0x18004da16  xor     edx, edx; hWndTo
0x18004da18  movdqu  xmmword ptr [rbp+47h+Rect.left], xmm0
0x18004da1d  mov     rcx, [rcx+8]; hWndFrom
0x18004da21  call    cs:__imp_MapWindowPoints
0x18004da27  mov     rax, [rbx+50h]
0x18004da2b  lea     r15, [rdi+4]
0x18004da2f  mov     r9d, 10h
0x18004da35  mov     ecx, [rax+4]
0x18004da38  test    cl, 20h
0x18004da3b  jz      loc_18004DB3F
0x18004da41  mov     r8d, [rbx+0B8h]
0x18004da48  mov     [rdi], r8d
0x18004da4b  mov     ecx, [rbx+0BCh]
0x18004da51  mov     [r15], ecx
0x18004da54  test    r13d, r13d
0x18004da57  jz      short loc_18004DA6B
0x18004da59  mov     eax, [rbx+0B8h]
0x18004da5f  mov     [rbp+47h+var_C0], eax
0x18004da62  mov     eax, [rbx+0BCh]
0x18004da68  mov     [rbp+47h+var_BC], eax
0x18004da6b  mov     rax, [rbx+50h]
0x18004da6f  test    byte ptr [rax+4], 2
0x18004da73  jz      short loc_18004DA94
0x18004da75  mov     eax, esi
0x18004da77  cdq
0x18004da78  sub     eax, edx
0x18004da7a  sar     eax, 1
0x18004da7c  sub     r8d, eax
0x18004da7f  mov     [rdi], r8d
0x18004da82  test    r13d, r13d
0x18004da85  jnz     short loc_18004DA94
0x18004da87  mov     eax, r14d
0x18004da8a  cdq
0x18004da8b  sub     eax, edx
0x18004da8d  sar     eax, 1
0x18004da8f  sub     ecx, eax
0x18004da91  mov     [r15], ecx
0x18004da94  mov     rax, [rbx+50h]
0x18004da98  test    byte ptr [rax+4], 80h
0x18004da9c  jz      short loc_18004DAB2
0x18004da9e  test    r13d, r13d
0x18004daa1  jz      short loc_18004DAAA
0x18004daa3  add     r14d, [rbx+0E0h]
0x18004daaa  mov     edx, [rbp+47h+var_C0]
0x18004daad  jmp     loc_18004DD89
0x18004dab2  test    r13d, r13d
0x18004dab5  jnz     loc_18004DC2E
0x18004dabb  mov     r9d, [rbx+0BCh]
0x18004dac2  mov     eax, [rbp+47h+Rect.bottom]
0x18004dac5  cmp     r9d, eax
0x18004dac8  jle     short loc_18004DADE
0x18004daca  lea     r12d, [r13+2]
0x18004dace  cmp     ecx, eax
0x18004dad0  jge     loc_18004DC53
0x18004dad6  mov     [r15], eax
0x18004dad9  jmp     loc_18004DC53
0x18004dade  mov     edx, [rbp+47h+Rect.left]
0x18004dae1  cmp     [rbx+0B8h], edx
0x18004dae7  jge     short loc_18004DB04
0x18004dae9  lea     eax, [r8+rsi]
0x18004daed  mov     r12d, 1
0x18004daf3  cmp     eax, edx
0x18004daf5  jle     loc_18004DC53
0x18004dafb  sub     edx, esi
0x18004dafd  mov     [rdi], edx
0x18004daff  jmp     loc_18004DC53
0x18004db04  mov     edx, [rbp+47h+Rect.top]
0x18004db07  cmp     r9d, edx
0x18004db0a  jge     short loc_18004DB26
0x18004db0c  xor     r12d, r12d
0x18004db0f  lea     eax, [rcx+r14]
0x18004db13  cmp     eax, edx
0x18004db15  jle     loc_18004DC53
0x18004db1b  sub     edx, r14d
0x18004db1e  mov     [r15], edx
0x18004db21  jmp     loc_18004DC53
0x18004db26  mov     eax, [rbp+47h+Rect.right]
0x18004db29  mov     r12d, 3
0x18004db2f  cmp     r8d, eax
0x18004db32  jge     loc_18004DC53
0x18004db38  mov     [rdi], eax
0x18004db3a  jmp     loc_18004DC53
0x18004db3f  test    cl, 2
0x18004db42  jz      short loc_18004DB7E
0x18004db44  mov     ecx, [rbp+47h+Rect.right]
0x18004db47  mov     eax, ecx
0x18004db49  mov     r8d, [rbp+47h+Rect.left]
0x18004db4d  sub     eax, esi
0x18004db4f  mov     r9d, [rbp+47h+Rect.bottom]
0x18004db53  add     eax, r8d
0x18004db56  cdq
0x18004db57  mov     [r15], r9d
0x18004db5a  sub     eax, edx
0x18004db5c  sar     eax, 1
0x18004db5e  mov     [rdi], eax
0x18004db60  test    r13d, r13d
0x18004db63  jz      loc_18004DC4F
0x18004db69  lea     eax, [rcx+r8]
0x18004db6d  mov     [rbp+47h+var_BC], r9d
0x18004db71  cdq
0x18004db72  sub     eax, edx
0x18004db74  sar     eax, 1
0x18004db76  mov     [rbp+47h+var_C0], eax
0x18004db79  jmp     loc_18004DC28
0x18004db7e  lea     r9, [rbp+47h+pt]
0x18004db82  mov     rdx, r15
0x18004db85  lea     r8, [rbp+47h+var_B0]
0x18004db89  mov     rcx, rdi
0x18004db8c  call    _GetCursorLowerLeft
0x18004db91  test    r13d, r13d
0x18004db94  jz      loc_18004DC4F
0x18004db9a  mov     eax, [r15]
0x18004db9d  mov     edx, 2; dwFlags
0x18004dba2  mov     ecx, eax
0x18004dba4  mov     [rbp+47h+pt.y], eax
0x18004dba7  sub     ecx, [rbp+47h+pt.x]
0x18004dbaa  mov     r12d, ecx
0x18004dbad  mov     [rbp+47h+var_BC], ecx
0x18004dbb0  mov     ecx, [rdi]
0x18004dbb2  sub     r12d, [rbx+0E0h]
0x18004dbb9  mov     [rbp+47h+var_C0], ecx
0x18004dbbc  sub     r12d, r14d
0x18004dbbf  mov     [rbp+47h+pt.x], ecx
0x18004dbc2  mov     rcx, qword ptr [rbp+47h+pt.x]; pt
0x18004dbc6  mov     [rbp+47h+var_A8.x], eax
0x18004dbc9  call    cs:__imp_MonitorFromPoint
0x18004dbcf  mov     [rbp+47h+pt.y], r12d
0x18004dbd3  mov     edx, 2; dwFlags
0x18004dbd8  mov     rcx, qword ptr [rbp+47h+pt.x]; pt
0x18004dbdc  mov     [rbp+47h+hMonitor], rax
0x18004dbe0  call    cs:__imp_MonitorFromPoint
0x18004dbe6  mov     rcx, [rbp+47h+hMonitor]; hMonitor
0x18004dbea  cmp     rcx, rax
0x18004dbed  jnz     short loc_18004DC17
0x18004dbef  lea     rdx, [rbp+47h+mi]; lpmi
0x18004dbf3  mov     [rbp+47h+mi.cbSize], 28h ; '('
0x18004dbfa  call    cs:__imp_GetMonitorInfoW
0x18004dc00  mov     rdx, qword ptr [rbp+47h+pt.x]; pt
0x18004dc04  lea     rcx, [rbp+47h+mi.rcMonitor]; lprc
0x18004dc08  call    cs:__imp_PtInRect
0x18004dc0e  test    eax, eax
0x18004dc10  jz      short loc_18004DC17
0x18004dc12  mov     [r15], r12d
0x18004dc15  jmp     short loc_18004DC28
0x18004dc17  mov     eax, [rbp+47h+var_A8.x]
0x18004dc1a  mov     [rbp+47h+var_BC], eax
0x18004dc1d  mov     eax, [rbp+47h+var_B0]
0x18004dc20  cdq
0x18004dc21  sub     eax, edx
0x18004dc23  sar     eax, 1
0x18004dc25  add     [rbp+47h+var_C0], eax
0x18004dc28  mov     r9d, 10h
0x18004dc2e  mov     rax, [rbx+50h]
0x18004dc32  test    byte ptr [rax+4], 2
0x18004dc36  jnz     short loc_18004DC48
0x18004dc38  mov     eax, [rbx+0E0h]
0x18004dc3e  add     eax, r9d
0x18004dc41  cmp     esi, eax
0x18004dc43  jle     short loc_18004DC48
0x18004dc45  add     dword ptr [rdi], 0FFFFFFF0h
0x18004dc48  add     r14d, [rbx+0E0h]
0x18004dc4f  or      r12d, 0FFFFFFFFh
0x18004dc53  mov     eax, [rdi]
0x18004dc55  mov     edx, 2; dwFlags
0x18004dc5a  mov     [rbp+47h+var_A8.x], eax
0x18004dc5d  mov     eax, [r15]
0x18004dc60  mov     [rbp+47h+var_A8.y], eax
0x18004dc63  mov     rcx, qword ptr [rbp+47h+var_A8.x]; pt
0x18004dc67  call    cs:__imp_MonitorFromPoint
0x18004dc6d  lea     rdx, [rbp+47h+mi]; lpmi
0x18004dc71  mov     [rbp+47h+mi.cbSize], 28h ; '('
0x18004dc78  mov     rcx, rax; hMonitor
0x18004dc7b  call    cs:__imp_GetMonitorInfoW
0x18004dc81  mov     rcx, [rbx]; hWnd
0x18004dc84  mov     edx, 0FFFFFFECh; nIndex
0x18004dc89  call    cs:__imp_GetWindowLongW
0x18004dc8f  lea     rcx, [rbp+47h+rcDst]; lprcDst
0x18004dc93  lea     rdx, [rbp+47h+mi.rcMonitor]
0x18004dc97  test    al, 8
0x18004dc99  jnz     short loc_18004DC9F
0x18004dc9b  lea     rdx, [rbp+47h+mi.rcWork]; lprcSrc
0x18004dc9f  call    cs:__imp_CopyRect
0x18004dca5  mov     ecx, [r15]
0x18004dca8  lea     eax, [rcx+r14]
0x18004dcac  cmp     eax, [rbp+47h+rcDst.bottom]
0x18004dcaf  jl      short loc_18004DCF0
0x18004dcb1  cmp     r12d, 2
0x18004dcb5  jnz     short loc_18004DCBC
0x18004dcb7  mov     ecx, [rbp+47h+Rect.top]
0x18004dcba  jmp     short loc_18004DCCC
0x18004dcbc  mov     rax, [rbx+50h]
0x18004dcc0  test    byte ptr [rax+4], 20h
0x18004dcc4  jz      short loc_18004DCD4
0x18004dcc6  mov     ecx, [rbx+0BCh]
0x18004dccc  sub     ecx, r14d
0x18004dccf  mov     [r15], ecx
0x18004dcd2  jmp     short loc_18004DCF0
0x18004dcd4  call    cs:__imp_GetMessagePos
0x18004dcda  shr     eax, 10h
0x18004dcdd  movsx   edx, ax
0x18004dce0  mov     ecx, edx
0x18004dce2  sub     ecx, r14d
0x18004dce5  mov     [r15], ecx
0x18004dce8  test    r13d, r13d
0x18004dceb  jz      short loc_18004DCF0
0x18004dced  mov     [rbp+47h+var_BC], edx
0x18004dcf0  mov     eax, [rbp+47h+rcDst.top]
0x18004dcf3  cmp     ecx, eax
0x18004dcf5  jge     short loc_18004DD01
0x18004dcf7  test    r12d, r12d
0x18004dcfa  cmovz   eax, [rbp+47h+Rect.bottom]
0x18004dcfe  mov     [r15], eax
0x18004dd01  mov     ecx, [rdi]
0x18004dd03  mov     r8d, [rbp+47h+rcDst.right]
0x18004dd07  lea     eax, [rcx+rsi]
0x18004dd0a  cmp     eax, r8d
0x18004dd0d  jl      short loc_18004DD62
0x18004dd0f  test    r13d, r13d
0x18004dd12  jz      short loc_18004DD50
0x18004dd14  cmp     esi, 1Eh
0x18004dd17  jl      short loc_18004DD3C
0x18004dd19  mov     ecx, 10h
0x18004dd1e  mov     eax, esi
0x18004dd20  sub     eax, [rbx+0E0h]
0x18004dd26  cdq
0x18004dd27  sub     eax, edx
  ... truncated ...
```

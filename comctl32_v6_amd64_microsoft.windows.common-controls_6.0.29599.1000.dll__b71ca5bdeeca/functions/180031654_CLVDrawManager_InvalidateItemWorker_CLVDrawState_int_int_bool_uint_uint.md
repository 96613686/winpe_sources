# CLVDrawManager::_InvalidateItemWorker(CLVDrawState *,int,int,bool,uint,uint)

- ea: `0x180031654`
- end: `0x180031a2e`
- name: `?_InvalidateItemWorker@CLVDrawManager@@AEAAXPEAVCLVDrawState@@HH_NII@Z`
- size: `986`
- prototype: `void __fastcall(CLVDrawManager *__hidden this, struct CLVDrawState *, int, int, bool, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800311d0`

## callees

- `0x18002becc`
- `0x180031654`
- `0x180031a40`
- `0x1800347f4`
- `0x1800f4d34`
- `0x18010422c`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x180031902`
- `GDI32!DeleteObject` at `0x180031902`
- `GDI32!CombineRgn` at `0x1800318f9`
- `GDI32!CombineRgn` at `0x1800318f9`
- `GDI32!CreateRectRgnIndirect` at `0x1800318cc`
- `GDI32!CreateRectRgnIndirect` at `0x1800318cc`
- `USER32!InflateRect` at `0x18003180e`
- `USER32!InflateRect` at `0x1800319f7`
- `USER32!InflateRect` at `0x18003180e`
- `USER32!InflateRect` at `0x1800319f7`
- `USER32!GetSystemMetrics` at `0x1800319d5`
- `USER32!GetSystemMetrics` at `0x1800319e3`
- `USER32!GetSystemMetrics` at `0x1800319d5`
- `USER32!GetSystemMetrics` at `0x1800319e3`
- `USER32!RedrawWindow` at `0x18003183c`
- `USER32!RedrawWindow` at `0x18003183c`

## pseudocode

```c
void __fastcall CLVDrawManager::_InvalidateItemWorker(
        CLVDrawManager *this,
        struct CLVDrawState *a2,
        int a3,
        int a4,
        bool a5,
        UINT a6,
        unsigned int a7)
{
  __int64 v7; // rbx
  __int64 v11; // rcx
  __int64 v12; // r10
  int v13; // edx
  __int64 v14; // r14
  __int64 v15; // rax
  struct tagRECT *p_rc; // r8
  struct tagRECT *v17; // r11
  struct tagRECT *v18; // r9
  struct tagRECT *v19; // rdi
  bool v20; // cl
  __int16 v21; // ax
  _DWORD *v22; // rcx
  UINT v23; // edi
  __int64 v24; // rax
  int v25; // ecx
  __int64 v26; // rcx
  CListGroup *v27; // rcx
  HRGN v28; // rax
  HRGN v29; // rbx
  HRGN v30; // rcx
  int v31; // ebx
  int SystemMetrics; // eax
  struct tagRECT rc; // [rsp+50h] [rbp-20h] BYREF

  v7 = a3;
  rc = 0;
  if ( a3 == -1 )
    return;
  v11 = *((_QWORD *)this + 3);
  if ( (*(_DWORD *)(v11 + 112) & 0x1000) != 0 && (*(_DWORD *)(v11 + 160) & 2) != 0 && *(_WORD *)(v11 + 164) != 3 )
  {
    v27 = *(CListGroup **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 336) + 72LL) + 8LL) + 8LL * a4);
    if ( (*((_BYTE *)v27 + 96) & 1) != 0
      || !(unsigned int)CListGroup::IsInClientRect(v27)
      || !(unsigned int)CLVGroupManager::IsItemVisible(*(CLVGroupManager **)(*((_QWORD *)this + 3) + 336LL), v7, a4) )
    {
      return;
    }
  }
  v12 = *((_QWORD *)this + 3);
  v13 = *(_DWORD *)(v12 + 168);
  if ( (*(_BYTE *)(v12 + 168) & 0x12) != 0x12
    && (v13 & 0x10) == 0
    && *((_DWORD *)this + 5) != -1
    && (int)v7 >= *((_DWORD *)this + 5) )
  {
    return;
  }
  v14 = 0;
  v15 = *(_QWORD *)(*(_QWORD *)(v12 + 512) + 8LL);
  if ( v15 && (int)v7 >= 0 && (int)v7 < *(_DWORD *)v15 )
  {
    _mm_lfence();
    v14 = *(_QWORD *)(*(_QWORD *)(v15 + 8) + 8 * v7);
  }
  p_rc = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( (*(_DWORD *)(v12 + 112) & 0x1000) != 0 && (v13 & 0x2000) != 0 )
    v20 = CListView::IsFullRowSelect(*((CListView **)this + 3)) && a5;
  else
    v20 = a5;
  if ( (*(_DWORD *)(v12 + 112) & 0x400) == 0 && v20 )
  {
    if ( *(_WORD *)(v12 + 164) != 1
      || (*(_BYTE *)(v12 + 176) & 0x20) != 0
      || CListView::IsExtendedTileView((CListView *)v12) )
    {
LABEL_18:
      p_rc = &rc;
      goto LABEL_19;
    }
LABEL_50:
    v18 = &rc;
    goto LABEL_19;
  }
  if ( a7 == 1 )
    goto LABEL_50;
  if ( a7 == 2 )
  {
    v19 = &rc;
    goto LABEL_19;
  }
  v21 = *(_WORD *)(v12 + 164);
  if ( v21 == 1 && (*(_BYTE *)(v12 + 176) & 0x20) != 0
    || v21 == 4 && (*(_BYTE *)(*(_QWORD *)(v12 + 648) + 24LL) & 4) != 0 )
  {
    goto LABEL_18;
  }
  v17 = &rc;
LABEL_19:
  if ( (unsigned int)CLVView::GetRects(*(CLVView **)(v12 + 608), a2, v7, a4, 0, v19, v18, v17, p_rc) )
  {
    v22 = (_DWORD *)*((_QWORD *)this + 3);
    if ( v22[55] > rc.left && rc.right > 0 && v22[56] > rc.top && rc.bottom > 0 )
    {
      if ( (v22[44] & 0x8000) != 0 )
      {
        v31 = GetSystemMetrics(6) + 4;
        SystemMetrics = GetSystemMetrics(5);
        InflateRect(&rc, 8 * SystemMetrics + 4, v31);
        v23 = a6 | 4;
      }
      else
      {
        v23 = a6;
      }
      v24 = *((_QWORD *)this + 3);
      v25 = *(_DWORD *)(v24 + 176);
      if ( ((v25 & 0x10000) != 0 || *(_DWORD *)(v24 + 48)) && v14 && (*(_BYTE *)(v14 + 18) & 0x10) != 0
        || (v25 & 0x800000) != 0
        || (*(_BYTE *)(v24 + 832) & 1) != 0 )
      {
        InflateRect(&rc, 10, 10);
        v23 |= 4u;
      }
      v26 = *((_QWORD *)this + 3);
      if ( (*(_BYTE *)(v26 + 168) & 0x12) == 0x12 )
      {
        RedrawWindow(*(HWND *)(v26 + 96), &rc, 0, v23);
      }
      else if ( (*(_DWORD *)(v26 + 168) & 0x10) == 0 )
      {
        v28 = CreateRectRgnIndirect(&rc);
        v29 = v28;
        if ( v28 )
        {
          v30 = (HRGN)*((_QWORD *)this + 1);
          if ( v30 )
          {
            if ( v30 != (HRGN)1 )
              CombineRgn(v30, *((HRGN *)this + 1), v28, 2);
            DeleteObject(v29);
          }
          else
          {
            *((_QWORD *)this + 1) = v28;
          }
        }
        if ( (v23 & 4) != 0 )
          *(_DWORD *)(*((_QWORD *)this + 3) + 168LL) |= 4u;
      }
    }
  }
}

```

## disassembly

```asm
0x180031654  push    rbp
0x180031656  push    rbx
0x180031657  push    rsi
0x180031658  push    rdi
0x180031659  push    r12
0x18003165b  push    r14
0x18003165d  push    r15
0x18003165f  mov     rbp, rsp
0x180031662  sub     rsp, 70h
0x180031666  mov     rax, cs:__security_cookie
0x18003166d  xor     rax, rsp
0x180031670  mov     [rbp+var_10], rax
0x180031674  movsxd  rbx, r8d
0x180031677  xorps   xmm0, xmm0
0x18003167a  movsxd  r15, r9d
0x18003167d  mov     r12, rdx
0x180031680  mov     rsi, rcx
0x180031683  movups  xmmword ptr [rbp+rc.left], xmm0
0x180031687  cmp     ebx, 0FFFFFFFFh
0x18003168a  jz      loc_180031842
0x180031690  mov     rcx, [rcx+18h]
0x180031694  mov     edx, 1
0x180031699  test    dword ptr [rcx+70h], 1000h
0x1800316a0  jnz     loc_18003185D
0x1800316a6  mov     r10, [rsi+18h]
0x1800316aa  mov     edx, [r10+0A8h]
0x1800316b1  mov     eax, edx
0x1800316b3  and     eax, 12h
0x1800316b6  cmp     al, 12h
0x1800316b8  jz      short loc_1800316C9
0x1800316ba  test    dl, 10h
0x1800316bd  jnz     short loc_1800316C9
0x1800316bf  cmp     dword ptr [rsi+14h], 0FFFFFFFFh
0x1800316c3  jnz     loc_1800319AD
0x1800316c9  mov     rax, [r10+200h]
0x1800316d0  xor     r14d, r14d
0x1800316d3  mov     rax, [rax+8]
0x1800316d7  test    rax, rax
0x1800316da  jnz     loc_18003195C
0x1800316e0  xor     r8d, r8d
0x1800316e3  xor     r11d, r11d
0x1800316e6  xor     r9d, r9d
0x1800316e9  xor     edi, edi
0x1800316eb  test    dword ptr [r10+70h], 1000h
0x1800316f3  jz      short loc_1800316FF
0x1800316f5  bt      edx, 0Dh
0x1800316f9  jb      loc_180031A08
0x1800316ff  mov     cl, [rbp+arg_20]
0x180031702  test    dword ptr [r10+70h], 400h
0x18003170a  mov     edx, 4
0x18003170f  jnz     short loc_180031719
0x180031711  test    cl, cl
0x180031713  jnz     loc_180031922
0x180031719  mov     eax, [rbp+arg_30]
0x18003171c  sub     eax, 1
0x18003171f  jz      loc_180031953
0x180031725  cmp     eax, 1
0x180031728  jz      loc_180031A1C
0x18003172e  movzx   eax, word ptr [r10+0A4h]
0x180031736  mov     ecx, 1
0x18003173b  cmp     ax, cx
0x18003173e  jz      short loc_18003174F
0x180031740  cmp     ax, dx
0x180031743  jz      loc_1800319BB
0x180031749  lea     r11, [rbp+rc]
0x18003174d  jmp     short loc_18003175D
0x18003174f  test    byte ptr [r10+0B0h], 20h
0x180031757  jz      short loc_180031740
0x180031759  lea     r8, [rbp+rc]
0x18003175d  mov     rcx, [r10+260h]; this
0x180031764  mov     rdx, r12; struct CLVDrawState *
0x180031767  mov     [rsp+70h+var_30], r8; struct tagRECT *
0x18003176c  mov     r8d, ebx; int
0x18003176f  mov     [rsp+70h+var_38], r11; struct tagRECT *
0x180031774  mov     [rsp+70h+var_40], r9; struct tagRECT *
0x180031779  mov     r9d, r15d; int
0x18003177c  mov     [rsp+70h+var_48], rdi; LPRECT
0x180031781  mov     [rsp+70h+var_50], 0; unsigned int
0x180031789  call    ?GetRects@CLVView@@QEAAHPEAVCLVDrawState@@HHKPEAUtagRECT@@111@Z; CLVView::GetRects(CLVDrawState *,int,int,ulong,tagRECT *,tagRECT *,tagRECT *,tagRECT *)
0x18003178e  test    eax, eax
0x180031790  jz      loc_180031842
0x180031796  mov     rcx, [rsi+18h]
0x18003179a  mov     eax, [rbp+rc.left]
0x18003179d  cmp     [rcx+0DCh], eax
0x1800317a3  jle     loc_180031842
0x1800317a9  cmp     [rbp+rc.right], 0
0x1800317ad  jle     loc_180031842
0x1800317b3  mov     eax, [rbp+rc.top]
0x1800317b6  cmp     [rcx+0E0h], eax
0x1800317bc  jle     loc_180031842
0x1800317c2  cmp     [rbp+rc.bottom], 0
0x1800317c6  jle     short loc_180031842
0x1800317c8  test    dword ptr [rcx+0B0h], 8000h
0x1800317d2  jnz     loc_1800319D0
0x1800317d8  mov     edi, [rbp+arg_28]
0x1800317db  mov     rax, [rsi+18h]
0x1800317df  mov     ecx, [rax+0B0h]
0x1800317e5  bt      ecx, 10h
0x1800317e9  jnb     loc_18003198C
0x1800317ef  test    r14, r14
0x1800317f2  jnz     loc_18003197C
0x1800317f8  bt      ecx, 17h
0x1800317fc  jnb     loc_18003199B
0x180031802  mov     edx, 0Ah; dx
0x180031807  lea     rcx, [rbp+rc]; lprc
0x18003180b  mov     r8d, edx; dy
0x18003180e  call    cs:__imp_InflateRect
0x180031814  or      edi, 4
0x180031817  mov     rcx, [rsi+18h]
0x18003181b  mov     edx, [rcx+0A8h]
0x180031821  mov     eax, edx
0x180031823  and     eax, 12h
0x180031826  cmp     al, 12h
0x180031828  jnz     loc_1800318BF
0x18003182e  mov     rcx, [rcx+60h]; hWnd
0x180031832  lea     rdx, [rbp+rc]; lprcUpdate
0x180031836  mov     r9d, edi; flags
0x180031839  xor     r8d, r8d; hrgnUpdate
0x18003183c  call    cs:__imp_RedrawWindow
0x180031842  mov     rcx, [rbp+var_10]
0x180031846  xor     rcx, rsp; StackCookie
0x180031849  call    __security_check_cookie
0x18003184e  add     rsp, 70h
0x180031852  pop     r15
0x180031854  pop     r14
0x180031856  pop     r12
0x180031858  pop     rdi
0x180031859  pop     rsi
0x18003185a  pop     rbx
0x18003185b  pop     rbp
0x18003185c  retn
0x18003185d  mov     eax, [rcx+0A0h]
0x180031863  shr     eax, 1
0x180031865  test    dl, al
0x180031867  jz      loc_1800316A6
0x18003186d  mov     eax, 3
0x180031872  cmp     ax, [rcx+0A4h]
0x180031879  jz      loc_1800316A6
0x18003187f  mov     rax, [rcx+150h]
0x180031886  mov     rax, [rax+48h]
0x18003188a  mov     rax, [rax+8]
0x18003188e  mov     rcx, [rax+r15*8]; this
0x180031892  test    [rcx+60h], dl
0x180031895  jnz     short loc_180031842
0x180031897  call    ?IsInClientRect@CListGroup@@QEBAHXZ; CListGroup::IsInClientRect(void)
0x18003189c  test    eax, eax
0x18003189e  jz      short loc_180031842
0x1800318a0  mov     rcx, [rsi+18h]
0x1800318a4  mov     r8d, r15d; int
0x1800318a7  mov     edx, ebx; unsigned int
0x1800318a9  mov     rcx, [rcx+150h]; this
0x1800318b0  call    ?IsItemVisible@CLVGroupManager@@QEAAHHH@Z; CLVGroupManager::IsItemVisible(int,int)
0x1800318b5  test    eax, eax
0x1800318b7  jnz     loc_1800316A6
0x1800318bd  jmp     short loc_180031842
0x1800318bf  test    dl, 10h
0x1800318c2  jnz     loc_180031842
0x1800318c8  lea     rcx, [rbp+rc]; lprect
0x1800318cc  call    cs:__imp_CreateRectRgnIndirect
0x1800318d2  mov     rbx, rax
0x1800318d5  test    rax, rax
0x1800318d8  jz      short loc_180031908
0x1800318da  mov     rcx, [rsi+8]; hrgnDst
0x1800318de  test    rcx, rcx
0x1800318e1  jz      loc_180031A25
0x1800318e7  cmp     rcx, 1
0x1800318eb  jz      short loc_1800318FF
0x1800318ed  mov     r9d, 2; iMode
0x1800318f3  mov     r8, rax; hrgnSrc2
0x1800318f6  mov     rdx, rcx; hrgnSrc1
0x1800318f9  call    cs:__imp_CombineRgn
0x1800318ff  mov     rcx, rbx; ho
0x180031902  call    cs:__imp_DeleteObject
0x180031908  test    dil, 4
0x18003190c  jz      loc_180031842
0x180031912  mov     rax, [rsi+18h]
0x180031916  or      dword ptr [rax+0A8h], 4
0x18003191d  jmp     loc_180031842
0x180031922  mov     ecx, 1
0x180031927  cmp     [r10+0A4h], cx
0x18003192f  jnz     loc_180031759
0x180031935  test    byte ptr [r10+0B0h], 20h
0x18003193d  jnz     loc_180031759
0x180031943  mov     rcx, r10; this
0x180031946  call    ?IsExtendedTileView@CListView@@QEBA_NXZ; CListView::IsExtendedTileView(void)
0x18003194b  test    al, al
0x18003194d  jnz     loc_180031759
0x180031953  lea     r9, [rbp+rc]
0x180031957  jmp     loc_18003175D
0x18003195c  test    ebx, ebx
0x18003195e  js      loc_1800316E0
0x180031964  cmp     ebx, [rax]
0x180031966  jge     loc_1800316E0
0x18003196c  lfence
0x18003196f  mov     rax, [rax+8]
0x180031973  mov     r14, [rax+rbx*8]
0x180031977  jmp     loc_1800316E0
0x18003197c  test    byte ptr [r14+12h], 10h
0x180031981  jnz     loc_180031802
0x180031987  jmp     loc_1800317F8
0x18003198c  cmp     dword ptr [rax+30h], 0
0x180031990  jz      loc_1800317F8
0x180031996  jmp     loc_1800317EF
0x18003199b  test    byte ptr [rax+340h], 1
0x1800319a2  jnz     loc_180031802
0x1800319a8  jmp     loc_180031817
0x1800319ad  cmp     ebx, [rsi+14h]
0x1800319b0  jl      loc_1800316C9
0x1800319b6  jmp     loc_180031842
0x1800319bb  mov     rax, [r10+288h]
0x1800319c2  test    [rax+18h], dl
0x1800319c5  jz      loc_180031749
0x1800319cb  jmp     loc_180031759
0x1800319d0  mov     ecx, 6; nIndex
0x1800319d5  call    cs:__imp_GetSystemMetrics
0x1800319db  mov     ecx, 5; nIndex
0x1800319e0  lea     ebx, [rax+4]
0x1800319e3  call    cs:__imp_GetSystemMetrics
0x1800319e9  mov     r8d, ebx; dy
0x1800319ec  lea     rcx, [rbp+rc]; lprc
0x1800319f0  lea     edx, ds:4[rax*8]; dx
0x1800319f7  call    cs:__imp_InflateRect
0x1800319fd  mov     edi, [rbp+arg_28]
0x180031a00  or      edi, 4
0x180031a03  jmp     loc_1800317DB
0x180031a08  mov     rcx, r10; this
0x180031a0b  call    ?IsFullRowSelect@CListView@@QEBA_NXZ; CListView::IsFullRowSelect(void)
0x180031a10  neg     al
0x180031a12  sbb     cl, cl
0x180031a14  and     cl, [rbp+arg_20]
0x180031a17  jmp     loc_180031702
0x180031a1c  lea     rdi, [rbp+rc]
0x180031a20  jmp     loc_18003175D
0x180031a25  mov     [rsi+8], rbx
0x180031a29  jmp     loc_180031908
```

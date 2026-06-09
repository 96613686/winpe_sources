# DoShowBubble

- ea: `0x18004ca94`
- end: `0x18004ce59`
- name: `DoShowBubble`
- size: `965`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18004d644`
- `0x18004ed04`
- `0x18004f220`

## callees

- `0x18001a590`
- `0x180037080`
- `0x18004c7cc`
- `0x18004ca94`
- `0x18004d014`
- `0x18004d564`
- `0x18004d908`
- `0x18004dde4`
- `0x18004ea40`
- `0x18004ebf0`
- `0x18008dff8`

## import_xrefs

- `GDI32!DeleteObject` at `0x18004cd34`
- `GDI32!DeleteObject` at `0x18004cd34`
- `KERNEL32!GetTickCount` at `0x18004cd8d`
- `KERNEL32!GetTickCount` at `0x18004cdb6`
- `KERNEL32!GetTickCount` at `0x18004cd8d`
- `KERNEL32!GetTickCount` at `0x18004cdb6`
- `USER32!GetWindowLongW` at `0x18004cc97`
- `USER32!GetWindowLongW` at `0x18004cc97`
- `USER32!SetWindowPos` at `0x18004cbde`
- `USER32!SetWindowPos` at `0x18004cc69`
- `USER32!SetWindowPos` at `0x18004cd5d`
- `USER32!SetWindowPos` at `0x18004cbde`
- `USER32!SetWindowPos` at `0x18004cc69`
- `USER32!SetWindowPos` at `0x18004cd5d`
- `USER32!GetDoubleClickTime` at `0x18004cb20`
- `USER32!GetDoubleClickTime` at `0x18004cb20`
- `USER32!RedrawWindow` at `0x18004ce28`
- `USER32!RedrawWindow` at `0x18004ce28`
- `USER32!InvalidateRect` at `0x18004cde6`
- `USER32!InvalidateRect` at `0x18004cde6`
- `USER32!UpdateWindow` at `0x18004cdef`
- `USER32!UpdateWindow` at `0x18004cdef`
- `USER32!GetWindow` at `0x18004cc37`
- `USER32!GetWindow` at `0x18004cc37`
- `USER32!SetTimer` at `0x18004cb3f`
- `USER32!SetTimer` at `0x18004cb3f`
- `USER32!KillTimer` at `0x18004cb13`
- `USER32!KillTimer` at `0x18004cb13`
- `USER32!SetWindowRgn` at `0x18004cd27`
- `USER32!SetWindowRgn` at `0x18004cd27`

## pseudocode

```c
int __fastcall DoShowBubble(__int64 a1)
{
  __int64 v1; // rdx
  __int64 ToolText; // rax
  _WORD *v4; // rdi
  __int64 v5; // rax
  UINT_PTR v6; // rdx
  int v7; // edx
  int v8; // esi
  int v9; // r13d
  __int64 v10; // rcx
  __int64 v11; // r12
  HWND Window; // rax
  __int64 v13; // rcx
  BOOL v14; // edx
  int v15; // ecx
  int v16; // r10d
  signed int v17; // esi
  HRGN BalloonRgn; // rax
  HRGN v19; // rdi
  DWORD TickCount; // eax
  bool v21; // cc
  int v23; // [rsp+40h] [rbp-19h]
  int X[4]; // [rsp+48h] [rbp-11h] BYREF
  __int128 v25; // [rsp+58h] [rbp-1h] BYREF
  __int128 v26; // [rsp+68h] [rbp+Fh]
  int v27; // [rsp+C0h] [rbp+67h] BYREF
  int v28; // [rsp+C8h] [rbp+6Fh] BYREF
  int v29; // [rsp+D0h] [rbp+77h] BYREF
  int v30; // [rsp+D8h] [rbp+7Fh] BYREF

  v1 = *(_QWORD *)(a1 + 80);
  v29 = 0;
  v28 = 0;
  v27 = 0;
  ToolText = 0;
  v30 = 0;
  *(_OWORD *)X = 0;
  v25 = 0;
  v26 = 0;
  if ( v1 )
    ToolText = GetToolText();
  v4 = (_WORD *)(ToolText & -(__int64)(*(_QWORD *)(a1 + 80) != 0));
  if ( (*(_BYTE *)(a1 + 104) & 1) != 0 )
  {
    if ( !v4 || !*v4 )
    {
      LODWORD(v5) = PopBubble(a1);
      *(_DWORD *)(a1 + 104) &= ~1u;
      return v5;
    }
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 112);
    if ( v6 )
      KillTimer(*(HWND *)a1, v6);
    v7 = *(_DWORD *)(a1 + 64);
    if ( v7 < 0 )
      v7 = GetDoubleClickTime() / 5;
    SetTimer(*(HWND *)a1, 3u, v7, 0);
    if ( !v4 || !*v4 )
    {
      PopBubble(a1);
      v5 = TTToolAtMessagePos(a1);
      *(_DWORD *)(a1 + 104) |= 0x80u;
      *(_QWORD *)(a1 + 80) = v5;
      return v5;
    }
    TTSetTimer(a1, 4);
  }
  do
  {
    TTGetTipSize(a1, *(_QWORD *)(a1 + 80), v4, &v29, &v28);
    TTGetTipPosition(a1, (unsigned int)X, v29, v28, (__int64)&v27, (__int64)&v30);
    v8 = X[2];
    v9 = X[3] - X[1];
    v23 = X[2] - X[0];
    SetWindowPos(*(HWND *)a1, 0, X[0], X[1], X[2] - X[0], X[3] - X[1], 2 * (*(_DWORD *)(a1 + 16) & 0x40 | 0xA));
    v10 = *(_QWORD *)(a1 + 80);
    v11 = *(_QWORD *)(a1 + 96);
    *(_QWORD *)&v25 = *(_QWORD *)a1;
    *((_QWORD *)&v25 + 1) = *(_QWORD *)(v10 + 16);
    DWORD2(v26) = *(_DWORD *)(a1 + 16);
    LODWORD(v26) = -521;
    if ( !SendNotifyEx(*(_QWORD *)(v10 + 8), -1, 4294966775LL, &v25, (*(_DWORD *)(v10 + 4) >> 6) & 1) )
    {
      Window = GetWindow(*(HWND *)a1, 4u);
      SetWindowPos(*(HWND *)a1, 0, X[0], X[1], 0, 0, Window != 0 ? 21 : 17);
    }
  }
  while ( v11 != *(_QWORD *)(a1 + 96) );
  if ( (*(_BYTE *)(a1 + 16) & 0x40) != 0 )
  {
    v13 = *(_QWORD *)(a1 + 80);
    v14 = 0;
    if ( v13 )
      v14 = (GetWindowLongW(*(HWND *)(v13 + 8), -20) & 0x400000) != 0 && (*(_DWORD *)(a1 + 32) & 0x400000) == 0;
    v15 = 0;
    v16 = v30;
    if ( v30 >= X[3] - 1 )
      v15 = 4;
    *(_DWORD *)(a1 + 192) &= ~4u;
    *(_DWORD *)(a1 + 192) |= v15;
    if ( v14 )
      v17 = v8 - v27;
    else
      v17 = v27 - X[0];
    BalloonRgn = CreateBalloonRgn(
                   v17,
                   v16 - X[1],
                   v23,
                   v9,
                   *(_DWORD *)(a1 + 224),
                   -__CFSHR__(*(_DWORD *)(a1 + 192), 3),
                   v14);
    v19 = BalloonRgn;
    if ( BalloonRgn && !SetWindowRgn(*(HWND *)a1, BalloonRgn, 0) )
      DeleteObject(v19);
    SetWindowPos(*(HWND *)a1, 0, 0, 0, 0, 0, 0x53u);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 228) )
      GetTickCount();
    CoolTooltipBubble(*(HWND *)a1);
    TickCount = GetTickCount();
    v21 = *(_QWORD *)(a1 + 40) < 4LL;
    *(_DWORD *)(a1 + 228) = TickCount;
    if ( v21 && (*(_BYTE *)(a1 + 192) & 0x10) == 0 && (BYTE8(v26) & 0x30) == 0 )
    {
      InvalidateRect(*(HWND *)a1, 0, 1);
      UpdateWindow(*(HWND *)a1);
      if ( (*(_BYTE *)(a1 + 192) & 0x10) == 0 )
      {
        SetWindowBits(*(HWND *)a1, -16);
        *(_DWORD *)(a1 + 192) |= 0x10u;
      }
    }
  }
  *(_DWORD *)(a1 + 104) |= 0x40u;
  LODWORD(v5) = RedrawWindow(*(HWND *)a1, 0, 0, 0x105u);
  return v5;
}

```

## disassembly

```asm
0x18004ca94  push    rbp
0x18004ca96  push    rbx
0x18004ca97  push    rsi
0x18004ca98  push    rdi
0x18004ca99  push    r12
0x18004ca9b  push    r13
0x18004ca9d  lea     rbp, [rsp-2Fh]
0x18004caa2  sub     rsp, 88h
0x18004caa9  mov     rdx, [rcx+50h]
0x18004caad  xor     esi, esi
0x18004caaf  mov     [rbp+57h+arg_10], esi
0x18004cab2  xorps   xmm0, xmm0
0x18004cab5  mov     [rbp+57h+arg_8], esi
0x18004cab8  mov     rbx, rcx
0x18004cabb  mov     [rbp+57h+arg_0], esi
0x18004cabe  mov     eax, esi
0x18004cac0  mov     [rbp+57h+arg_18], esi
0x18004cac3  movups  xmmword ptr [rbp+57h+X], xmm0
0x18004cac7  movups  [rbp+57h+var_58], xmm0
0x18004cacb  movups  [rbp+57h+var_48], xmm0
0x18004cacf  test    rdx, rdx
0x18004cad2  jz      short loc_18004CAD9
0x18004cad4  call    GetToolText
0x18004cad9  mov     rcx, [rbx+50h]
0x18004cadd  neg     rcx
0x18004cae0  sbb     rdi, rdi
0x18004cae3  and     rdi, rax
0x18004cae6  test    byte ptr [rbx+68h], 1
0x18004caea  jz      short loc_18004CB07
0x18004caec  test    rdi, rdi
0x18004caef  jz      short loc_18004CAF6
0x18004caf1  cmp     [rdi], si
0x18004caf4  jnz     short loc_18004CB64
0x18004caf6  mov     rcx, rbx
0x18004caf9  call    PopBubble
0x18004cafe  and     dword ptr [rbx+68h], 0FFFFFFFEh
0x18004cb02  jmp     loc_18004CE49
0x18004cb07  mov     rdx, [rbx+70h]; uIDEvent
0x18004cb0b  test    rdx, rdx
0x18004cb0e  jz      short loc_18004CB19
0x18004cb10  mov     rcx, [rbx]; hWnd
0x18004cb13  call    cs:__imp_KillTimer
0x18004cb19  mov     edx, [rbx+40h]
0x18004cb1c  test    edx, edx
0x18004cb1e  jns     short loc_18004CB32
0x18004cb20  call    cs:__imp_GetDoubleClickTime
0x18004cb26  mov     ecx, eax
0x18004cb28  mov     eax, 0CCCCCCCDh
0x18004cb2d  mul     ecx
0x18004cb2f  shr     edx, 2
0x18004cb32  mov     rcx, [rbx]; hWnd
0x18004cb35  xor     r9d, r9d; lpTimerFunc
0x18004cb38  mov     r8d, edx; uElapse
0x18004cb3b  lea     edx, [r9+3]; nIDEvent
0x18004cb3f  call    cs:__imp_SetTimer
0x18004cb45  test    rdi, rdi
0x18004cb48  jz      loc_18004CE30
0x18004cb4e  cmp     [rdi], si
0x18004cb51  jz      loc_18004CE30
0x18004cb57  mov     edx, 4
0x18004cb5c  mov     rcx, rbx
0x18004cb5f  call    TTSetTimer
0x18004cb64  mov     rdx, [rbx+50h]
0x18004cb68  lea     rax, [rbp+57h+arg_8]
0x18004cb6c  lea     r9, [rbp+57h+arg_10]
0x18004cb70  mov     qword ptr [rsp+0B0h+var_90], rax
0x18004cb75  mov     r8, rdi
0x18004cb78  mov     rcx, rbx
0x18004cb7b  call    TTGetTipSize
0x18004cb80  mov     r9d, [rbp+57h+arg_8]
0x18004cb84  lea     rax, [rbp+57h+arg_18]
0x18004cb88  mov     r8d, [rbp+57h+arg_10]
0x18004cb8c  lea     rdx, [rbp+57h+X]
0x18004cb90  mov     qword ptr [rsp+0B0h+cy], rax
0x18004cb95  mov     rcx, rbx
0x18004cb98  lea     rax, [rbp+57h+arg_0]
0x18004cb9c  mov     qword ptr [rsp+0B0h+var_90], rax
0x18004cba1  call    TTGetTipPosition
0x18004cba6  mov     eax, [rbx+10h]
0x18004cba9  xor     edx, edx; hWndInsertAfter
0x18004cbab  mov     r13d, [rbp+57h+X+0Ch]
0x18004cbaf  and     eax, 40h
0x18004cbb2  mov     esi, [rbp+57h+X+8]
0x18004cbb5  or      eax, 0Ah
0x18004cbb8  sub     r13d, [rbp+57h+X+4]
0x18004cbbc  add     eax, eax
0x18004cbbe  mov     r9d, [rbp+57h+X+4]; Y
0x18004cbc2  mov     ecx, esi
0x18004cbc4  sub     ecx, [rbp+57h+X]
0x18004cbc7  mov     r8d, [rbp+57h+X]; X
0x18004cbcb  mov     [rsp+0B0h+uFlags], eax; uFlags
0x18004cbcf  mov     [rbp+57h+var_70], ecx
0x18004cbd2  mov     [rsp+0B0h+cy], r13d; cy
0x18004cbd7  mov     [rsp+0B0h+var_90], ecx; cx
0x18004cbdb  mov     rcx, [rbx]; hWnd
0x18004cbde  call    cs:__imp_SetWindowPos
0x18004cbe4  mov     rcx, [rbx+50h]
0x18004cbe8  lea     r9, [rbp+57h+var_58]
0x18004cbec  mov     rax, [rbx]
0x18004cbef  mov     r8d, 0FFFFFDF7h
0x18004cbf5  mov     r12, [rbx+60h]
0x18004cbf9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004cbfd  mov     qword ptr [rbp+57h+var_58], rax
0x18004cc01  mov     rax, [rcx+10h]
0x18004cc05  mov     qword ptr [rbp+57h+var_58+8], rax
0x18004cc09  mov     eax, [rbx+10h]
0x18004cc0c  mov     dword ptr [rbp+57h+var_48+8], eax
0x18004cc0f  mov     dword ptr [rbp+57h+var_48], 0FFFFFDF7h
0x18004cc16  mov     eax, [rcx+4]
0x18004cc19  mov     rcx, [rcx+8]
0x18004cc1d  shr     eax, 6
0x18004cc20  and     eax, 1
0x18004cc23  mov     [rsp+0B0h+var_90], eax
0x18004cc27  call    SendNotifyEx
0x18004cc2c  test    rax, rax
0x18004cc2f  jnz     short loc_18004CC6F
0x18004cc31  mov     rcx, [rbx]; hWnd
0x18004cc34  lea     edx, [rax+4]; uCmd
0x18004cc37  call    cs:__imp_GetWindow
0x18004cc3d  mov     r9d, [rbp+57h+X+4]; Y
0x18004cc41  neg     rax
0x18004cc44  mov     r8d, [rbp+57h+X]; X
0x18004cc48  sbb     ecx, ecx
0x18004cc4a  xor     edx, edx; hWndInsertAfter
0x18004cc4c  and     ecx, 4
0x18004cc4f  add     ecx, 11h
0x18004cc52  mov     [rsp+0B0h+uFlags], ecx; uFlags
0x18004cc56  mov     rcx, [rbx]; hWnd
0x18004cc59  mov     [rsp+0B0h+cy], 0; cy
0x18004cc61  mov     [rsp+0B0h+var_90], 0; cx
0x18004cc69  call    cs:__imp_SetWindowPos
0x18004cc6f  cmp     r12, [rbx+60h]
0x18004cc73  jnz     loc_18004CB64
0x18004cc79  test    byte ptr [rbx+10h], 40h
0x18004cc7d  jz      loc_18004CD68
0x18004cc83  mov     rcx, [rbx+50h]
0x18004cc87  xor     edx, edx
0x18004cc89  test    rcx, rcx
0x18004cc8c  jz      short loc_18004CCB4
0x18004cc8e  mov     rcx, [rcx+8]; hWnd
0x18004cc92  mov     edx, 0FFFFFFECh; nIndex
0x18004cc97  call    cs:__imp_GetWindowLongW
0x18004cc9d  mov     ecx, 400000h
0x18004cca2  test    ecx, eax
0x18004cca4  jz      short loc_18004CCB2
0x18004cca6  test    [rbx+20h], ecx
0x18004cca9  jnz     short loc_18004CCB2
0x18004ccab  mov     edx, 1
0x18004ccb0  jmp     short loc_18004CCB4
0x18004ccb2  xor     edx, edx
0x18004ccb4  mov     eax, [rbp+57h+X+0Ch]
0x18004ccb7  xor     ecx, ecx
0x18004ccb9  mov     r10d, [rbp+57h+arg_18]
0x18004ccbd  dec     eax
0x18004ccbf  cmp     r10d, eax
0x18004ccc2  lea     eax, [rcx+4]
0x18004ccc5  cmovge  ecx, eax
0x18004ccc8  and     dword ptr [rbx+0C0h], 0FFFFFFFBh
0x18004cccf  or      [rbx+0C0h], ecx
0x18004ccd5  mov     ecx, [rbx+0C0h]
0x18004ccdb  test    edx, edx
0x18004ccdd  jz      short loc_18004CCE4
0x18004ccdf  sub     esi, [rbp+57h+arg_0]
0x18004cce2  jmp     short loc_18004CCEA
0x18004cce4  mov     esi, [rbp+57h+arg_0]
0x18004cce7  sub     esi, [rbp+57h+X]
0x18004ccea  mov     eax, [rbx+0E0h]
0x18004ccf0  mov     r9d, r13d
0x18004ccf3  mov     r8d, [rbp+57h+var_70]
0x18004ccf7  mov     [rsp+0B0h+uFlags], edx
0x18004ccfb  shr     ecx, 3
0x18004ccfe  sbb     ecx, ecx
0x18004cd00  sub     r10d, [rbp+57h+X+4]
0x18004cd04  mov     [rsp+0B0h+cy], ecx
0x18004cd08  mov     edx, r10d
0x18004cd0b  mov     ecx, esi
0x18004cd0d  mov     [rsp+0B0h+var_90], eax
0x18004cd11  call    CreateBalloonRgn
0x18004cd16  mov     rdi, rax
0x18004cd19  test    rax, rax
0x18004cd1c  jz      short loc_18004CD3A
0x18004cd1e  mov     rcx, [rbx]; hWnd
0x18004cd21  xor     r8d, r8d; bRedraw
0x18004cd24  mov     rdx, rax; hRgn
0x18004cd27  call    cs:__imp_SetWindowRgn
0x18004cd2d  test    eax, eax
0x18004cd2f  jnz     short loc_18004CD3A
0x18004cd31  mov     rcx, rdi; ho
0x18004cd34  call    cs:__imp_DeleteObject
0x18004cd3a  mov     rcx, [rbx]; hWnd
0x18004cd3d  xor     r9d, r9d; Y
0x18004cd40  mov     [rsp+0B0h+uFlags], 53h ; 'S'; uFlags
0x18004cd48  xor     r8d, r8d; X
0x18004cd4b  mov     [rsp+0B0h+cy], 0; cy
0x18004cd53  xor     edx, edx; hWndInsertAfter
0x18004cd55  mov     [rsp+0B0h+var_90], 0; cx
0x18004cd5d  call    cs:__imp_SetWindowPos
0x18004cd63  jmp     loc_18004CE16
0x18004cd68  mov     edi, dword ptr [rbp+57h+var_48+8]
0x18004cd6b  mov     esi, edi
0x18004cd6d  shr     esi, 5
0x18004cd70  shr     edi, 4
0x18004cd73  not     esi
0x18004cd75  not     edi
0x18004cd77  and     esi, 1
0x18004cd7a  and     edi, 1
0x18004cd7d  cmp     dword ptr [rbx+0E4h], 0
0x18004cd84  jnz     short loc_18004CD8D
0x18004cd86  mov     eax, 7D0h
0x18004cd8b  jmp     short loc_18004CD93
0x18004cd8d  call    cs:__imp_GetTickCount
0x18004cd93  sub     eax, [rbx+0E4h]
0x18004cd99  cmp     eax, 7D0h
0x18004cd9e  jnb     short loc_18004CDA4
0x18004cda0  xor     edi, edi
0x18004cda2  xor     esi, esi
0x18004cda4  mov     rcx, [rbx]; hWnd
0x18004cda7  lea     rdx, [rbp+57h+X]
0x18004cdab  mov     r9d, edi
0x18004cdae  mov     r8d, esi
0x18004cdb1  call    CoolTooltipBubble
0x18004cdb6  call    cs:__imp_GetTickCount
0x18004cdbc  cmp     qword ptr [rbx+28h], 4
0x18004cdc1  mov     [rbx+0E4h], eax
0x18004cdc7  jge     short loc_18004CE16
0x18004cdc9  test    byte ptr [rbx+0C0h], 10h
0x18004cdd0  jnz     short loc_18004CE16
0x18004cdd2  mov     edi, 30h ; '0'
0x18004cdd7  test    byte ptr [rbp+57h+var_48+8], dil
0x18004cddb  jnz     short loc_18004CE16
0x18004cddd  mov     rcx, [rbx]; hWnd
0x18004cde0  lea     r8d, [rdi-2Fh]; bErase
0x18004cde4  xor     edx, edx; lpRect
0x18004cde6  call    cs:__imp_InvalidateRect
0x18004cdec  mov     rcx, [rbx]; hWnd
0x18004cdef  call    cs:__imp_UpdateWindow
0x18004cdf5  test    byte ptr [rbx+0C0h], 10h
0x18004cdfc  jnz     short loc_18004CE16
0x18004cdfe  mov     rcx, [rbx]; hWnd
0x18004ce01  lea     edx, [rdi-40h]; nIndex
0x18004ce04  mov     r9d, edi
0x18004ce07  mov     r8d, edi
0x18004ce0a  call    SetWindowBits
0x18004ce0f  or      dword ptr [rbx+0C0h], 10h
0x18004ce16  or      dword ptr [rbx+68h], 40h
0x18004ce1a  mov     r9d, 105h; flags
0x18004ce20  mov     rcx, [rbx]; hWnd
0x18004ce23  xor     r8d, r8d; hrgnUpdate
0x18004ce26  xor     edx, edx; lprcUpdate
0x18004ce28  call    cs:__imp_RedrawWindow
0x18004ce2e  jmp     short loc_18004CE49
0x18004ce30  mov     rcx, rbx
0x18004ce33  call    PopBubble
0x18004ce38  mov     rcx, rbx
0x18004ce3b  call    TTToolAtMessagePos
0x18004ce40  bts     dword ptr [rbx+68h], 7
0x18004ce45  mov     [rbx+50h], rax
0x18004ce49  add     rsp, 88h
0x18004ce50  pop     r13
0x18004ce52  pop     r12
0x18004ce54  pop     rdi
0x18004ce55  pop     rsi
0x18004ce56  pop     rbx
0x18004ce57  pop     rbp
0x18004ce58  retn
```

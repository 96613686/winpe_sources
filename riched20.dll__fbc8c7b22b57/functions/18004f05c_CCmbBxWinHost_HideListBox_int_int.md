# CCmbBxWinHost::HideListBox(int,int)

- ea: `0x18004f05c`
- end: `0x18004f227`
- name: `?HideListBox@CCmbBxWinHost@@QEAAHHH@Z`
- size: `459`
- prototype: `__int64 __fastcall(CCmbBxWinHost *__hidden this, int, int)`
- caller_count: `8`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18004f840`
- `0x18004fca0`
- `0x18004fec8`
- `0x18004ffa0`
- `0x1800507dc`
- `0x180050970`
- `0x180050a30`
- `0x180051788`

## callees

- `0x18004e420`
- `0x18004f05c`
- `0x18004f230`
- `0x180069ca0`
- `0x180095010`

## import_xrefs

- `USER32!UpdateWindow` at `0x18004f1c1`
- `USER32!UpdateWindow` at `0x18004f1c1`
- `USER32!SetWindowPos` at `0x18004f18b`
- `USER32!SetWindowPos` at `0x18004f18b`
- `USER32!ShowWindow` at `0x18004f0d2`
- `USER32!ShowWindow` at `0x18004f0d2`
- `USER32!InvalidateRect` at `0x18004f130`
- `USER32!InvalidateRect` at `0x18004f157`
- `USER32!InvalidateRect` at `0x18004f130`
- `USER32!InvalidateRect` at `0x18004f157`

## pseudocode

```c
__int64 __fastcall CCmbBxWinHost::HideListBox(CCmbBxWinHost *this, int a2, int a3)
{
  __int64 v5; // rdx
  HWND v6; // rcx
  int v7; // eax
  unsigned int v8; // edx
  int v9; // eax
  HWND v10; // rcx
  HWND v11; // rcx
  __int64 v12; // rdx

  if ( a2 )
  {
    if ( a3 )
    {
      v5 = 9;
LABEL_6:
      (*(void (__fastcall **)(CCmbBxWinHost *, __int64, _QWORD))(*(_QWORD *)this + 304LL))(this, v5, 0);
      goto LABEL_7;
    }
    if ( *((_DWORD *)this + 60) != 1 )
    {
      v5 = 10;
      goto LABEL_6;
    }
  }
LABEL_7:
  if ( (*((_BYTE *)this + 120) & 2) != 0 && *((_DWORD *)this + 60) != 1 )
  {
    CLstBxWinHost::OnCBTracking(*((CLstBxWinHost **)this + 31), 3u, 0);
    v6 = (HWND)*((_QWORD *)this + 16);
    *((_DWORD *)this + 30) &= ~2u;
    ShowWindow(v6, 0);
    v7 = *((_DWORD *)this + 30);
    if ( (v7 & 0x100) != 0 )
    {
      *((_DWORD *)this + 30) = v7 & 0xFFFFFEFF;
      (*(void (__fastcall **)(CCmbBxWinHost *, _QWORD))(*(_QWORD *)this + 136LL))(this, 0);
    }
    *((_DWORD *)this + 30) |= 0x200u;
    v8 = *((_DWORD *)this + 30);
    if ( *((_DWORD *)this + 60) == 3 )
    {
      if ( (v8 & 4) == 0 )
        CCmbBxWinHost::HiliteEdit(this, (v8 >> 3) & 1);
      InvalidateRect(*((HWND *)this + 2), 0, 1);
    }
    v9 = *((_DWORD *)this + 30);
    if ( (v9 & 0x10) != 0 )
    {
      v10 = (HWND)*((_QWORD *)this + 2);
      *((_DWORD *)this + 30) = v9 & 0xFFFFFFEF;
      InvalidateRect(v10, (const RECT *)this + 10, 0);
    }
    SetWindowPos(*((HWND *)this + 2), 0, 0, 0, *((_DWORD *)this + 55), *((_DWORD *)this + 54), 0x16u);
    *((_DWORD *)this + 30) &= ~0x200u;
    if ( *((_DWORD *)this + 60) == 2 )
      CCmbBxWinHost::AutoUpdateEdit(this, *((_DWORD *)this + 57));
    v11 = (HWND)*((_QWORD *)this + 2);
    *((_DWORD *)this + 57) = -2;
    UpdateWindow(v11);
    if ( a2 )
      (*(void (__fastcall **)(CCmbBxWinHost *, __int64))(*(_QWORD *)this + 304LL))(this, 8);
    v12 = *((_QWORD *)this + 17);
    if ( v12 )
    {
      (*(void (__fastcall **)(CCmbBxWinHost *, __int64, _QWORD))(*(_QWORD *)this + 376LL))(this, v12, 0);
      *((_QWORD *)this + 17) = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18004f05c  mov     [rsp+arg_0], rbx
0x18004f061  push    rdi
0x18004f062  sub     rsp, 40h
0x18004f066  mov     edi, edx
0x18004f068  mov     rbx, rcx
0x18004f06b  test    edx, edx
0x18004f06d  jz      short loc_18004F09B
0x18004f06f  test    r8d, r8d
0x18004f072  jz      short loc_18004F07B
0x18004f074  mov     edx, 9
0x18004f079  jmp     short loc_18004F089
0x18004f07b  cmp     dword ptr [rcx+0F0h], 1
0x18004f082  jz      short loc_18004F09B
0x18004f084  mov     edx, 0Ah
0x18004f089  mov     rax, [rcx]
0x18004f08c  xor     r8d, r8d
0x18004f08f  mov     rax, [rax+130h]
0x18004f096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f09b  test    byte ptr [rbx+78h], 2
0x18004f09f  jz      loc_18004F216
0x18004f0a5  cmp     dword ptr [rbx+0F0h], 1
0x18004f0ac  jz      loc_18004F216
0x18004f0b2  mov     rcx, [rbx+0F8h]; this
0x18004f0b9  xor     r8d, r8d; __int64
0x18004f0bc  lea     edx, [r8+3]; unsigned __int64
0x18004f0c0  call    ?OnCBTracking@CLstBxWinHost@@QEAAX_K_J@Z; CLstBxWinHost::OnCBTracking(unsigned __int64,__int64)
0x18004f0c5  mov     rcx, [rbx+80h]; hWnd
0x18004f0cc  xor     edx, edx; nCmdShow
0x18004f0ce  and     dword ptr [rbx+78h], 0FFFFFFFDh
0x18004f0d2  call    cs:__imp_ShowWindow
0x18004f0d9  nop     dword ptr [rax+rax+00h]
0x18004f0de  mov     eax, [rbx+78h]
0x18004f0e1  bt      eax, 8
0x18004f0e5  jnb     short loc_18004F102
0x18004f0e7  btr     eax, 8
0x18004f0eb  xor     edx, edx
0x18004f0ed  mov     [rbx+78h], eax
0x18004f0f0  mov     rcx, rbx
0x18004f0f3  mov     rax, [rbx]
0x18004f0f6  mov     rax, [rax+88h]
0x18004f0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f102  bts     dword ptr [rbx+78h], 9
0x18004f107  cmp     dword ptr [rbx+0F0h], 3
0x18004f10e  mov     edx, [rbx+78h]
0x18004f111  jnz     short loc_18004F13C
0x18004f113  test    dl, 4
0x18004f116  jnz     short loc_18004F126
0x18004f118  shr     edx, 3
0x18004f11b  mov     rcx, rbx; this
0x18004f11e  and     edx, 1; int
0x18004f121  call    ?HiliteEdit@CCmbBxWinHost@@IEAAXH@Z; CCmbBxWinHost::HiliteEdit(int)
0x18004f126  mov     rcx, [rbx+10h]; hWnd
0x18004f12a  xor     edx, edx; lpRect
0x18004f12c  lea     r8d, [rdx+1]; bErase
0x18004f130  call    cs:__imp_InvalidateRect
0x18004f137  nop     dword ptr [rax+rax+00h]
0x18004f13c  mov     eax, [rbx+78h]
0x18004f13f  test    al, 10h
0x18004f141  jz      short loc_18004F163
0x18004f143  mov     rcx, [rbx+10h]; hWnd
0x18004f147  lea     rdx, [rbx+0A0h]; lpRect
0x18004f14e  and     eax, 0FFFFFFEFh
0x18004f151  xor     r8d, r8d; bErase
0x18004f154  mov     [rbx+78h], eax
0x18004f157  call    cs:__imp_InvalidateRect
0x18004f15e  nop     dword ptr [rax+rax+00h]
0x18004f163  mov     eax, [rbx+0D8h]
0x18004f169  xor     r9d, r9d; Y
0x18004f16c  mov     rcx, [rbx+10h]; hWnd
0x18004f170  xor     r8d, r8d; X
0x18004f173  mov     [rsp+48h+uFlags], 16h; uFlags
0x18004f17b  xor     edx, edx; hWndInsertAfter
0x18004f17d  mov     [rsp+48h+cy], eax; cy
0x18004f181  mov     eax, [rbx+0DCh]
0x18004f187  mov     [rsp+48h+var_28], eax; cx
0x18004f18b  call    cs:__imp_SetWindowPos
0x18004f192  nop     dword ptr [rax+rax+00h]
0x18004f197  btr     dword ptr [rbx+78h], 9
0x18004f19c  cmp     dword ptr [rbx+0F0h], 2
0x18004f1a3  jnz     short loc_18004F1B3
0x18004f1a5  mov     edx, [rbx+0E4h]; int
0x18004f1ab  mov     rcx, rbx; this
0x18004f1ae  call    ?AutoUpdateEdit@CCmbBxWinHost@@IEAAXH@Z; CCmbBxWinHost::AutoUpdateEdit(int)
0x18004f1b3  mov     rcx, [rbx+10h]; hWnd
0x18004f1b7  mov     dword ptr [rbx+0E4h], 0FFFFFFFEh
0x18004f1c1  call    cs:__imp_UpdateWindow
0x18004f1c8  nop     dword ptr [rax+rax+00h]
0x18004f1cd  test    edi, edi
0x18004f1cf  jz      short loc_18004F1EA
0x18004f1d1  mov     rax, [rbx]
0x18004f1d4  xor     r8d, r8d
0x18004f1d7  mov     rcx, rbx
0x18004f1da  mov     rax, [rax+130h]
0x18004f1e1  lea     edx, [r8+8]
0x18004f1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1ea  mov     rdx, [rbx+88h]
0x18004f1f1  test    rdx, rdx
0x18004f1f4  jz      short loc_18004F216
0x18004f1f6  mov     rcx, [rbx]
0x18004f1f9  xor     r8d, r8d
0x18004f1fc  mov     rax, [rcx+178h]
0x18004f203  mov     rcx, rbx
0x18004f206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f20b  mov     qword ptr [rbx+88h], 0
0x18004f216  mov     rbx, [rsp+48h+arg_0]
0x18004f21b  mov     eax, 1
0x18004f220  add     rsp, 40h
0x18004f224  pop     rdi
0x18004f225  retn
```

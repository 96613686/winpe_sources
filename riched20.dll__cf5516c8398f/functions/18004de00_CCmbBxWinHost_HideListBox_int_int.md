# CCmbBxWinHost::HideListBox(int,int)

- ea: `0x18004de00`
- end: `0x18004dfac`
- name: `?HideListBox@CCmbBxWinHost@@QEAAHHH@Z`
- size: `428`
- prototype: `__int64 __fastcall(CCmbBxWinHost *__hidden this, int, int)`
- caller_count: `8`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18004e598`
- `0x18004e9e0`
- `0x18004ec08`
- `0x18004ece0`
- `0x18004f4a8`
- `0x18004f630`
- `0x18004f6e0`
- `0x1800503fc`

## callees

- `0x18004d230`
- `0x18004de00`
- `0x18004dfb4`
- `0x180068154`
- `0x180092010`

## import_xrefs

- `USER32!UpdateWindow` at `0x18004df4d`
- `USER32!UpdateWindow` at `0x18004df4d`
- `USER32!SetWindowPos` at `0x18004df1d`
- `USER32!SetWindowPos` at `0x18004df1d`
- `USER32!ShowWindow` at `0x18004de76`
- `USER32!ShowWindow` at `0x18004de76`
- `USER32!InvalidateRect` at `0x18004dece`
- `USER32!InvalidateRect` at `0x18004deef`
- `USER32!InvalidateRect` at `0x18004dece`
- `USER32!InvalidateRect` at `0x18004deef`

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
0x18004de00  mov     [rsp+arg_0], rbx
0x18004de05  push    rdi
0x18004de06  sub     rsp, 40h
0x18004de0a  mov     edi, edx
0x18004de0c  mov     rbx, rcx
0x18004de0f  test    edx, edx
0x18004de11  jz      short loc_18004DE3F
0x18004de13  test    r8d, r8d
0x18004de16  jz      short loc_18004DE1F
0x18004de18  mov     edx, 9
0x18004de1d  jmp     short loc_18004DE2D
0x18004de1f  cmp     dword ptr [rcx+0F0h], 1
0x18004de26  jz      short loc_18004DE3F
0x18004de28  mov     edx, 0Ah
0x18004de2d  mov     rax, [rcx]
0x18004de30  xor     r8d, r8d
0x18004de33  mov     rax, [rax+130h]
0x18004de3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de3f  test    byte ptr [rbx+78h], 2
0x18004de43  jz      loc_18004DF9C
0x18004de49  cmp     dword ptr [rbx+0F0h], 1
0x18004de50  jz      loc_18004DF9C
0x18004de56  mov     rcx, [rbx+0F8h]; this
0x18004de5d  xor     r8d, r8d; __int64
0x18004de60  lea     edx, [r8+3]; unsigned __int64
0x18004de64  call    ?OnCBTracking@CLstBxWinHost@@QEAAX_K_J@Z; CLstBxWinHost::OnCBTracking(unsigned __int64,__int64)
0x18004de69  mov     rcx, [rbx+80h]; hWnd
0x18004de70  xor     edx, edx; nCmdShow
0x18004de72  and     dword ptr [rbx+78h], 0FFFFFFFDh
0x18004de76  call    cs:__imp_ShowWindow
0x18004de7c  mov     eax, [rbx+78h]
0x18004de7f  bt      eax, 8
0x18004de83  jnb     short loc_18004DEA0
0x18004de85  btr     eax, 8
0x18004de89  xor     edx, edx
0x18004de8b  mov     [rbx+78h], eax
0x18004de8e  mov     rcx, rbx
0x18004de91  mov     rax, [rbx]
0x18004de94  mov     rax, [rax+88h]
0x18004de9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dea0  bts     dword ptr [rbx+78h], 9
0x18004dea5  cmp     dword ptr [rbx+0F0h], 3
0x18004deac  mov     edx, [rbx+78h]
0x18004deaf  jnz     short loc_18004DED4
0x18004deb1  test    dl, 4
0x18004deb4  jnz     short loc_18004DEC4
0x18004deb6  shr     edx, 3
0x18004deb9  mov     rcx, rbx; this
0x18004debc  and     edx, 1; int
0x18004debf  call    ?HiliteEdit@CCmbBxWinHost@@IEAAXH@Z; CCmbBxWinHost::HiliteEdit(int)
0x18004dec4  mov     rcx, [rbx+10h]; hWnd
0x18004dec8  xor     edx, edx; lpRect
0x18004deca  lea     r8d, [rdx+1]; bErase
0x18004dece  call    cs:__imp_InvalidateRect
0x18004ded4  mov     eax, [rbx+78h]
0x18004ded7  test    al, 10h
0x18004ded9  jz      short loc_18004DEF5
0x18004dedb  mov     rcx, [rbx+10h]; hWnd
0x18004dedf  lea     rdx, [rbx+0A0h]; lpRect
0x18004dee6  and     eax, 0FFFFFFEFh
0x18004dee9  xor     r8d, r8d; bErase
0x18004deec  mov     [rbx+78h], eax
0x18004deef  call    cs:__imp_InvalidateRect
0x18004def5  mov     eax, [rbx+0D8h]
0x18004defb  xor     r9d, r9d; Y
0x18004defe  mov     rcx, [rbx+10h]; hWnd
0x18004df02  xor     r8d, r8d; X
0x18004df05  mov     [rsp+48h+uFlags], 16h; uFlags
0x18004df0d  xor     edx, edx; hWndInsertAfter
0x18004df0f  mov     [rsp+48h+cy], eax; cy
0x18004df13  mov     eax, [rbx+0DCh]
0x18004df19  mov     [rsp+48h+var_28], eax; cx
0x18004df1d  call    cs:__imp_SetWindowPos
0x18004df23  btr     dword ptr [rbx+78h], 9
0x18004df28  cmp     dword ptr [rbx+0F0h], 2
0x18004df2f  jnz     short loc_18004DF3F
0x18004df31  mov     edx, [rbx+0E4h]; int
0x18004df37  mov     rcx, rbx; this
0x18004df3a  call    ?AutoUpdateEdit@CCmbBxWinHost@@IEAAXH@Z; CCmbBxWinHost::AutoUpdateEdit(int)
0x18004df3f  mov     rcx, [rbx+10h]; hWnd
0x18004df43  mov     dword ptr [rbx+0E4h], 0FFFFFFFEh
0x18004df4d  call    cs:__imp_UpdateWindow
0x18004df53  test    edi, edi
0x18004df55  jz      short loc_18004DF70
0x18004df57  mov     rax, [rbx]
0x18004df5a  xor     r8d, r8d
0x18004df5d  mov     rcx, rbx
0x18004df60  mov     rax, [rax+130h]
0x18004df67  lea     edx, [r8+8]
0x18004df6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df70  mov     rdx, [rbx+88h]
0x18004df77  test    rdx, rdx
0x18004df7a  jz      short loc_18004DF9C
0x18004df7c  mov     rcx, [rbx]
0x18004df7f  xor     r8d, r8d
0x18004df82  mov     rax, [rcx+178h]
0x18004df89  mov     rcx, rbx
0x18004df8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df91  mov     qword ptr [rbx+88h], 0
0x18004df9c  mov     rbx, [rsp+48h+arg_0]
0x18004dfa1  mov     eax, 1
0x18004dfa6  add     rsp, 40h
0x18004dfaa  pop     rdi
0x18004dfab  retn
```

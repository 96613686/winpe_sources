# CBody::InitToolbar(void)

- ea: `0x180022ae0`
- end: `0x180022d45`
- name: `?InitToolbar@CBody@@AEAAJXZ`
- size: `613`
- prototype: `__int64 __fastcall(CBody *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180022a98`

## callees

- `0x180022ae0`
- `0x180022d4c`
- `0x180022ee8`
- `0x180082728`
- `0x1800cb45c`
- `0x1800cbacc`
- `0x1800cca00`

## import_xrefs

- `MSOERT2!ReplaceCharsW` at `0x180022c79`
- `MSOERT2!ReplaceCharsW` at `0x180022c79`
- `USER32!LoadStringW` at `0x180022c63`
- `USER32!LoadStringW` at `0x180022c63`
- `USER32!SendMessageA` at `0x180022bc4`
- `USER32!SendMessageA` at `0x180022bf6`
- `USER32!SendMessageA` at `0x180022c0e`
- `USER32!SendMessageA` at `0x180022c27`
- `USER32!SendMessageA` at `0x180022c46`
- `USER32!SendMessageA` at `0x180022cb5`
- `USER32!SendMessageA` at `0x180022bc4`
- `USER32!SendMessageA` at `0x180022bf6`
- `USER32!SendMessageA` at `0x180022c0e`
- `USER32!SendMessageA` at `0x180022c27`
- `USER32!SendMessageA` at `0x180022c46`
- `USER32!SendMessageA` at `0x180022cb5`
- `USER32!SendMessageW` at `0x180022c93`
- `USER32!SendMessageW` at `0x180022c93`
- `USER32!DestroyWindow` at `0x180022b9e`
- `USER32!DestroyWindow` at `0x180022b9e`
- `USER32!SetWindowPos` at `0x180022ce1`
- `USER32!SetWindowPos` at `0x180022ce1`

## pseudocode

```c
__int64 __fastcall CBody::InitToolbar(CBody *this, __int64 a2, __int64 a3)
{
  HWND Window; // rax
  HINSTANCE v5; // rcx
  int v6; // r9d
  __int64 result; // rax
  HIMAGELIST ImageA; // rax
  HWND v9; // rcx
  HINSTANCE v10; // rcx
  int v11; // r9d
  HIMAGELIST v12; // rax
  HWND v13; // rcx
  unsigned int v14; // eax
  int v15; // r9d
  struct IMimeMessage *v16; // rdx
  struct IOleCommandTarget *v17; // r8
  COLORREF crMask; // [rsp+20h] [rbp-458h]
  COLORREF crMaska; // [rsp+20h] [rbp-458h]
  UINT uType; // [rsp+28h] [rbp-450h]
  UINT uTypea; // [rsp+28h] [rbp-450h]
  UINT uFlags; // [rsp+30h] [rbp-448h]
  UINT uFlagsa; // [rsp+30h] [rbp-448h]
  WCHAR Buffer[512]; // [rsp+60h] [rbp-418h] BYREF

  if ( !*((_QWORD *)this + 48) )
  {
    Window = SHFusionCreateWindowEx(
               0,
               "ToolbarWindow32",
               a3,
               0x4400894Cu,
               0,
               0,
               32,
               100,
               *((HWND *)this + 13),
               (HMENU)0x259,
               g_hInst,
               0);
    *((_QWORD *)this + 48) = Window;
    if ( !Window )
      return 2147500037LL;
    ImageA = ImageList_LoadImageA(v5, (LPCSTR)3, 32, v6, crMask, uType, uFlags);
    v9 = (HWND)*((_QWORD *)this + 48);
    *((_QWORD *)this + 71) = ImageA;
    if ( !ImageA
      || (SendMessageA(v9, 0x430u, 0, (LPARAM)ImageA),
          v12 = ImageList_LoadImageA(v10, (LPCSTR)4, 32, v11, crMaska, uTypea, uFlagsa),
          v9 = (HWND)*((_QWORD *)this + 48),
          (*((_QWORD *)this + 72) = v12) == 0) )
    {
      DestroyWindow(v9);
      result = 2147942414LL;
      *((_QWORD *)this + 48) = 0;
      return result;
    }
    SendMessageA(v9, 0x434u, 0, (LPARAM)v12);
    SendMessageA(*((HWND *)this + 48), 0x43Cu, 0, 0);
    SendMessageA(*((HWND *)this + 48), 0x41Eu, 0x20u, 0);
    SendMessageA(*((HWND *)this + 48), 0x414u, 6u, (LPARAM)&lParam);
    if ( LoadStringW(g_hLocRes, 0x4FDu, Buffer, 512) )
    {
      ReplaceCharsW(Buffer, 124);
      SendMessageW(*((HWND *)this + 48), 0x44Du, 0, (LPARAM)Buffer);
    }
    v13 = (HWND)*((_QWORD *)this + 48);
    *((_DWORD *)this + 83) = 0;
    v14 = SendMessageA(v13, 0x43Au, 0, 0);
    SetWindowPos(*((HWND *)this + 48), 0, 0, 0, 0, HIWORD(v14), 0x216u);
    v16 = (struct IMimeMessage *)*((_QWORD *)this + 35);
    if ( v16 )
    {
      v17 = (struct IOleCommandTarget *)*((_QWORD *)this + 43);
      if ( v17 )
      {
        if ( !*((_QWORD *)this + 80) )
          CCommunityRatings::Create(*((HWND *)this + 13), v16, v17, v15, (struct CCommunityRatings **)this + 80);
      }
    }
    CBody::RecalcPreviewHeight(this, (HDC)v16);
    CBody::Resize(this);
  }
  return 0;
}

```

## disassembly

```asm
0x180022ae0  push    rbx
0x180022ae2  sub     rsp, 470h
0x180022ae9  mov     rax, cs:__security_cookie
0x180022af0  xor     rax, rsp
0x180022af3  mov     [rsp+478h+var_18], rax
0x180022afb  cmp     qword ptr [rcx+180h], 0
0x180022b03  mov     rbx, rcx
0x180022b06  jnz     loc_180022D2A
0x180022b0c  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180022b13  lea     rdx, aToolbarwindow3; "ToolbarWindow32"
0x180022b1a  mov     [rsp+478h+var_420], 0; LPVOID
0x180022b23  mov     r9d, 4400894Ch
0x180022b29  mov     [rsp+478h+var_428], rax; HINSTANCE
0x180022b2e  mov     rax, [rcx+68h]
0x180022b32  xor     ecx, ecx; dwExStyle
0x180022b34  mov     [rsp+478h+var_430], 259h; HMENU
0x180022b3d  mov     [rsp+478h+var_438], rax; HWND
0x180022b42  mov     [rsp+478h+var_440], 64h ; 'd'; int
0x180022b4a  mov     [rsp+478h+uFlags], 20h ; ' '; int
0x180022b52  mov     [rsp+478h+uType], 0; int
0x180022b5a  mov     [rsp+478h+crMask], 0; int
0x180022b62  call    SHFusionCreateWindowEx
0x180022b67  mov     [rbx+180h], rax
0x180022b6e  test    rax, rax
0x180022b71  jnz     short loc_180022B7D
0x180022b73  mov     eax, 80004005h
0x180022b78  jmp     loc_180022D2C
0x180022b7d  mov     edx, 3; lpbmp
0x180022b82  lea     r8d, [rdx+1Dh]; cx
0x180022b86  call    ImageList_LoadImageA
0x180022b8b  mov     rcx, [rbx+180h]; hWnd
0x180022b92  mov     [rbx+238h], rax
0x180022b99  test    rax, rax
0x180022b9c  jnz     short loc_180022BB9
0x180022b9e  call    cs:__imp_DestroyWindow
0x180022ba4  mov     eax, 8007000Eh
0x180022ba9  mov     qword ptr [rbx+180h], 0
0x180022bb4  jmp     loc_180022D2C
0x180022bb9  mov     r9, rax; lParam
0x180022bbc  xor     r8d, r8d; wParam
0x180022bbf  mov     edx, 430h; Msg
0x180022bc4  call    cs:__imp_SendMessageA
0x180022bca  mov     edx, 4; lpbmp
0x180022bcf  lea     r8d, [rdx+1Ch]; cx
0x180022bd3  call    ImageList_LoadImageA
0x180022bd8  mov     rcx, [rbx+180h]; hWnd
0x180022bdf  mov     [rbx+240h], rax
0x180022be6  test    rax, rax
0x180022be9  jz      short loc_180022B9E
0x180022beb  mov     r9, rax; lParam
0x180022bee  xor     r8d, r8d; wParam
0x180022bf1  mov     edx, 434h; Msg
0x180022bf6  call    cs:__imp_SendMessageA
0x180022bfc  mov     rcx, [rbx+180h]; hWnd
0x180022c03  xor     r9d, r9d; lParam
0x180022c06  xor     r8d, r8d; wParam
0x180022c09  mov     edx, 43Ch; Msg
0x180022c0e  call    cs:__imp_SendMessageA
0x180022c14  mov     rcx, [rbx+180h]; hWnd
0x180022c1b  xor     r9d, r9d; lParam
0x180022c1e  mov     edx, 41Eh; Msg
0x180022c23  lea     r8d, [r9+20h]; wParam
0x180022c27  call    cs:__imp_SendMessageA
0x180022c2d  mov     rcx, [rbx+180h]; hWnd
0x180022c34  lea     r9, lParam; lParam
0x180022c3b  mov     edx, 414h; Msg
0x180022c40  mov     r8d, 6; wParam
0x180022c46  call    cs:__imp_SendMessageA
0x180022c4c  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x180022c53  lea     r8, [rsp+478h+Buffer]; lpBuffer
0x180022c58  mov     r9d, 200h; cchBufferMax
0x180022c5e  mov     edx, 4FDh; uID
0x180022c63  call    cs:__imp_LoadStringW
0x180022c69  test    eax, eax
0x180022c6b  jz      short loc_180022C99
0x180022c6d  xor     r8d, r8d
0x180022c70  lea     rcx, [rsp+478h+Buffer]
0x180022c75  lea     edx, [r8+7Ch]
0x180022c79  call    cs:__imp_ReplaceCharsW
0x180022c7f  mov     rcx, [rbx+180h]; hWnd
0x180022c86  lea     r9, [rsp+478h+Buffer]; lParam
0x180022c8b  xor     r8d, r8d; wParam
0x180022c8e  mov     edx, 44Dh; Msg
0x180022c93  call    cs:__imp_SendMessageW
0x180022c99  mov     rcx, [rbx+180h]; hWnd
0x180022ca0  xor     r9d, r9d; lParam
0x180022ca3  xor     r8d, r8d; wParam
0x180022ca6  mov     dword ptr [rbx+14Ch], 0
0x180022cb0  mov     edx, 43Ah; Msg
0x180022cb5  call    cs:__imp_SendMessageA
0x180022cbb  mov     rcx, [rbx+180h]; hWnd
0x180022cc2  xor     r9d, r9d; Y
0x180022cc5  shr     eax, 10h
0x180022cc8  xor     r8d, r8d; X
0x180022ccb  mov     [rsp+478h+uFlags], 216h; uFlags
0x180022cd3  xor     edx, edx; hWndInsertAfter
0x180022cd5  mov     [rsp+478h+uType], eax; cy
0x180022cd9  mov     [rsp+478h+crMask], 0; cx
0x180022ce1  call    cs:__imp_SetWindowPos
0x180022ce7  mov     rdx, [rbx+118h]; struct IMimeMessage *
0x180022cee  test    rdx, rdx
0x180022cf1  jz      short loc_180022D1A
0x180022cf3  mov     r8, [rbx+158h]; struct IOleCommandTarget *
0x180022cfa  test    r8, r8
0x180022cfd  jz      short loc_180022D1A
0x180022cff  lea     rax, [rbx+280h]
0x180022d06  cmp     qword ptr [rax], 0
0x180022d0a  jnz     short loc_180022D1A
0x180022d0c  mov     rcx, [rbx+68h]; HWND
0x180022d10  mov     qword ptr [rsp+478h+crMask], rax; struct CCommunityRatings **
0x180022d15  call    ?Create@CCommunityRatings@@SAJPEAUHWND__@@PEAUIMimeMessage@@PEAUIOleCommandTarget@@HPEAPEAV1@@Z; CCommunityRatings::Create(HWND__ *,IMimeMessage *,IOleCommandTarget *,int,CCommunityRatings * *)
0x180022d1a  mov     rcx, rbx; this
0x180022d1d  call    ?RecalcPreviewHeight@CBody@@AEAAJPEAUHDC__@@@Z; CBody::RecalcPreviewHeight(HDC__ *)
0x180022d22  mov     rcx, rbx; this
0x180022d25  call    ?Resize@CBody@@AEAAJXZ; CBody::Resize(void)
0x180022d2a  xor     eax, eax
0x180022d2c  mov     rcx, [rsp+478h+var_18]
0x180022d34  xor     rcx, rsp; StackCookie
0x180022d37  call    __security_check_cookie
0x180022d3c  add     rsp, 470h
0x180022d43  pop     rbx
0x180022d44  retn
```

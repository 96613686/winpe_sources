# CSimpleHeader::_InitToolbar(void)

- ea: `0x18006d5e4`
- end: `0x18006d87f`
- name: `?_InitToolbar@CSimpleHeader@@AEAAJXZ`
- size: `667`
- prototype: `__int64 __fastcall(CSimpleHeader *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006cc50`

## callees

- `0x180028a68`
- `0x18006d5e4`
- `0x180082728`
- `0x1800cb45c`
- `0x1800cbacc`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!ReplaceCharsW` at `0x18006d755`
- `MSOERT2!ReplaceCharsW` at `0x18006d755`
- `USER32!LoadStringW` at `0x18006d73c`
- `USER32!LoadStringW` at `0x18006d73c`
- `USER32!SendMessageA` at `0x18006d6a5`
- `USER32!SendMessageA` at `0x18006d6d5`
- `USER32!SendMessageA` at `0x18006d6ea`
- `USER32!SendMessageA` at `0x18006d700`
- `USER32!SendMessageA` at `0x18006d71c`
- `USER32!SendMessageA` at `0x18006d78b`
- `USER32!SendMessageA` at `0x18006d857`
- `USER32!SendMessageA` at `0x18006d6a5`
- `USER32!SendMessageA` at `0x18006d6d5`
- `USER32!SendMessageA` at `0x18006d6ea`
- `USER32!SendMessageA` at `0x18006d700`
- `USER32!SendMessageA` at `0x18006d71c`
- `USER32!SendMessageA` at `0x18006d78b`
- `USER32!SendMessageA` at `0x18006d857`
- `USER32!SendMessageW` at `0x18006d76f`
- `USER32!SendMessageW` at `0x18006d76f`
- `USER32!GetClientRect` at `0x18006d833`
- `USER32!GetClientRect` at `0x18006d833`
- `USER32!SetWindowPos` at `0x18006d7b4`
- `USER32!SetWindowPos` at `0x18006d7b4`

## pseudocode

```c
__int64 __fastcall CSimpleHeader::_InitToolbar(CSimpleHeader *this, __int64 a2, __int64 a3)
{
  HWND Window; // rax
  HINSTANCE v5; // rcx
  int v6; // r9d
  HIMAGELIST ImageA; // rax
  HINSTANCE v9; // rcx
  int v10; // r9d
  HIMAGELIST v11; // rax
  HWND v12; // rcx
  unsigned int v13; // eax
  int v14; // r9d
  __int64 v15; // rcx
  COLORREF crMask; // [rsp+20h] [rbp-478h]
  COLORREF crMaska; // [rsp+20h] [rbp-478h]
  UINT uType; // [rsp+28h] [rbp-470h]
  UINT uTypea; // [rsp+28h] [rbp-470h]
  UINT uFlags; // [rsp+30h] [rbp-468h]
  UINT uFlagsa; // [rsp+30h] [rbp-468h]
  HWND hWnd; // [rsp+60h] [rbp-438h] BYREF
  struct tagRECT Rect; // [rsp+68h] [rbp-430h] BYREF
  WCHAR Buffer[512]; // [rsp+80h] [rbp-418h] BYREF

  if ( *((_QWORD *)this + 5) )
    return 0;
  Window = SHFusionCreateWindowEx(
             0,
             "ToolbarWindow32",
             a3,
             0x4400894Cu,
             0,
             0,
             32,
             100,
             *((HWND *)this + 4),
             (HMENU)0x259,
             g_hInst,
             0);
  *((_QWORD *)this + 5) = Window;
  if ( !Window )
    return 2147500037LL;
  ImageA = ImageList_LoadImageA(v5, (LPCSTR)3, 32, v6, crMask, uType, uFlags);
  *((_QWORD *)this + 11) = ImageA;
  if ( ImageA )
  {
    SendMessageA(*((HWND *)this + 5), 0x430u, 0, (LPARAM)ImageA);
    v11 = ImageList_LoadImageA(v9, (LPCSTR)4, 32, v10, crMaska, uTypea, uFlagsa);
    *((_QWORD *)this + 12) = v11;
    if ( v11 )
    {
      SendMessageA(*((HWND *)this + 5), 0x434u, 0, (LPARAM)v11);
      SendMessageA(*((HWND *)this + 5), 0x43Cu, 0, 0);
      SendMessageA(*((HWND *)this + 5), 0x41Eu, 0x20u, 0);
      SendMessageA(*((HWND *)this + 5), 0x414u, 6u, (LPARAM)&qword_1800DCEF0);
      if ( LoadStringW(g_hLocRes, 0x4FDu, Buffer, 512) )
      {
        ReplaceCharsW(Buffer, 124);
        SendMessageW(*((HWND *)this + 5), 0x44Du, 0, (LPARAM)Buffer);
      }
      v12 = (HWND)*((_QWORD *)this + 5);
      *((_DWORD *)this + 18) = 0;
      v13 = SendMessageA(v12, 0x43Au, 0, 0);
      SetWindowPos(*((HWND *)this + 5), 0, 0, 0, 0, HIWORD(v13), 0x216u);
      CCommunityRatings::Create(
        *((HWND *)this + 4),
        *((struct IMimeMessage **)this + 18),
        *((struct IOleCommandTarget **)this + 7),
        v14,
        (struct CCommunityRatings **)this + 19);
      CSimpleHeader::_CalcHeight(this);
      (*(void (__fastcall **)(CSimpleHeader *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 56LL))(this, 0, 0, 0);
      v15 = *((_QWORD *)this + 6);
      if ( v15 )
      {
        hWnd = 0;
        Rect = 0;
        (*(void (__fastcall **)(__int64, HWND *))(*(_QWORD *)v15 + 24LL))(v15, &hWnd);
        if ( hWnd )
        {
          GetClientRect(hWnd, &Rect);
          SendMessageA(hWnd, 5u, 0, LOWORD(Rect.right) | (unsigned __int64)(LOWORD(Rect.bottom) << 16));
        }
      }
      return 0;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18006d5e4  push    rbx
0x18006d5e6  sub     rsp, 490h
0x18006d5ed  mov     rax, cs:__security_cookie
0x18006d5f4  xor     rax, rsp
0x18006d5f7  mov     [rsp+498h+var_18], rax
0x18006d5ff  cmp     qword ptr [rcx+28h], 0
0x18006d604  mov     rbx, rcx
0x18006d607  jnz     loc_18006D85D
0x18006d60d  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x18006d614  lea     rdx, aToolbarwindow3; "ToolbarWindow32"
0x18006d61b  mov     [rsp+498h+var_440], 0; LPVOID
0x18006d624  mov     r9d, 4400894Ch
0x18006d62a  mov     [rsp+498h+var_448], rax; HINSTANCE
0x18006d62f  mov     rax, [rcx+20h]
0x18006d633  xor     ecx, ecx; dwExStyle
0x18006d635  mov     [rsp+498h+var_450], 259h; HMENU
0x18006d63e  mov     [rsp+498h+var_458], rax; HWND
0x18006d643  mov     [rsp+498h+var_460], 64h ; 'd'; int
0x18006d64b  mov     [rsp+498h+uFlags], 20h ; ' '; int
0x18006d653  mov     [rsp+498h+uType], 0; int
0x18006d65b  mov     [rsp+498h+crMask], 0; int
0x18006d663  call    SHFusionCreateWindowEx
0x18006d668  mov     [rbx+28h], rax
0x18006d66c  test    rax, rax
0x18006d66f  jnz     short loc_18006D67B
0x18006d671  mov     eax, 80004005h
0x18006d676  jmp     loc_18006D85F
0x18006d67b  mov     edx, 3; lpbmp
0x18006d680  lea     r8d, [rdx+1Dh]; cx
0x18006d684  call    ImageList_LoadImageA
0x18006d689  mov     [rbx+58h], rax
0x18006d68d  test    rax, rax
0x18006d690  jz      loc_18006D878
0x18006d696  mov     rcx, [rbx+28h]; hWnd
0x18006d69a  mov     r9, rax; lParam
0x18006d69d  xor     r8d, r8d; wParam
0x18006d6a0  mov     edx, 430h; Msg
0x18006d6a5  call    cs:__imp_SendMessageA
0x18006d6ab  mov     edx, 4; lpbmp
0x18006d6b0  lea     r8d, [rdx+1Ch]; cx
0x18006d6b4  call    ImageList_LoadImageA
0x18006d6b9  mov     [rbx+60h], rax
0x18006d6bd  test    rax, rax
0x18006d6c0  jz      loc_18006D878
0x18006d6c6  mov     rcx, [rbx+28h]; hWnd
0x18006d6ca  mov     r9, rax; lParam
0x18006d6cd  xor     r8d, r8d; wParam
0x18006d6d0  mov     edx, 434h; Msg
0x18006d6d5  call    cs:__imp_SendMessageA
0x18006d6db  mov     rcx, [rbx+28h]; hWnd
0x18006d6df  xor     r9d, r9d; lParam
0x18006d6e2  xor     r8d, r8d; wParam
0x18006d6e5  mov     edx, 43Ch; Msg
0x18006d6ea  call    cs:__imp_SendMessageA
0x18006d6f0  mov     rcx, [rbx+28h]; hWnd
0x18006d6f4  xor     r9d, r9d; lParam
0x18006d6f7  mov     edx, 41Eh; Msg
0x18006d6fc  lea     r8d, [r9+20h]; wParam
0x18006d700  call    cs:__imp_SendMessageA
0x18006d706  mov     rcx, [rbx+28h]; hWnd
0x18006d70a  lea     r9, qword_1800DCEF0; lParam
0x18006d711  mov     edx, 414h; Msg
0x18006d716  mov     r8d, 6; wParam
0x18006d71c  call    cs:__imp_SendMessageA
0x18006d722  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18006d729  lea     r8, [rsp+498h+Buffer]; lpBuffer
0x18006d731  mov     r9d, 200h; cchBufferMax
0x18006d737  mov     edx, 4FDh; uID
0x18006d73c  call    cs:__imp_LoadStringW
0x18006d742  test    eax, eax
0x18006d744  jz      short loc_18006D775
0x18006d746  xor     r8d, r8d
0x18006d749  lea     rcx, [rsp+498h+Buffer]
0x18006d751  lea     edx, [r8+7Ch]
0x18006d755  call    cs:__imp_ReplaceCharsW
0x18006d75b  mov     rcx, [rbx+28h]; hWnd
0x18006d75f  lea     r9, [rsp+498h+Buffer]; lParam
0x18006d767  xor     r8d, r8d; wParam
0x18006d76a  mov     edx, 44Dh; Msg
0x18006d76f  call    cs:__imp_SendMessageW
0x18006d775  mov     rcx, [rbx+28h]; hWnd
0x18006d779  xor     r9d, r9d; lParam
0x18006d77c  xor     r8d, r8d; wParam
0x18006d77f  mov     dword ptr [rbx+48h], 0
0x18006d786  mov     edx, 43Ah; Msg
0x18006d78b  call    cs:__imp_SendMessageA
0x18006d791  mov     rcx, [rbx+28h]; hWnd
0x18006d795  xor     r9d, r9d; Y
0x18006d798  shr     eax, 10h
0x18006d79b  xor     r8d, r8d; X
0x18006d79e  mov     [rsp+498h+uFlags], 216h; uFlags
0x18006d7a6  xor     edx, edx; hWndInsertAfter
0x18006d7a8  mov     [rsp+498h+uType], eax; cy
0x18006d7ac  mov     [rsp+498h+crMask], 0; cx
0x18006d7b4  call    cs:__imp_SetWindowPos
0x18006d7ba  mov     r8, [rbx+38h]; struct IOleCommandTarget *
0x18006d7be  lea     rax, [rbx+98h]
0x18006d7c5  mov     rdx, [rbx+90h]; struct IMimeMessage *
0x18006d7cc  mov     rcx, [rbx+20h]; HWND
0x18006d7d0  mov     qword ptr [rsp+498h+crMask], rax; struct CCommunityRatings **
0x18006d7d5  call    ?Create@CCommunityRatings@@SAJPEAUHWND__@@PEAUIMimeMessage@@PEAUIOleCommandTarget@@HPEAPEAV1@@Z; CCommunityRatings::Create(HWND__ *,IMimeMessage *,IOleCommandTarget *,int,CCommunityRatings * *)
0x18006d7da  mov     rcx, rbx; this
0x18006d7dd  call    ?_CalcHeight@CSimpleHeader@@AEAAXXZ; CSimpleHeader::_CalcHeight(void)
0x18006d7e2  mov     rax, [rbx]
0x18006d7e5  xor     r9d, r9d
0x18006d7e8  xor     r8d, r8d
0x18006d7eb  xor     edx, edx
0x18006d7ed  mov     rcx, rbx
0x18006d7f0  mov     rax, [rax+38h]
0x18006d7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d7f9  mov     rcx, [rbx+30h]
0x18006d7fd  test    rcx, rcx
0x18006d800  jz      short loc_18006D85D
0x18006d802  xorps   xmm0, xmm0
0x18006d805  mov     [rsp+498h+hWnd], 0
0x18006d80e  movups  xmmword ptr [rsp+498h+Rect.left], xmm0
0x18006d813  mov     rax, [rcx]
0x18006d816  lea     rdx, [rsp+498h+hWnd]
0x18006d81b  mov     rax, [rax+18h]
0x18006d81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d824  mov     rcx, [rsp+498h+hWnd]; hWnd
0x18006d829  test    rcx, rcx
0x18006d82c  jz      short loc_18006D85D
0x18006d82e  lea     rdx, [rsp+498h+Rect]; lpRect
0x18006d833  call    cs:__imp_GetClientRect
0x18006d839  movzx   r9d, word ptr [rsp+498h+Rect.bottom]
0x18006d83f  xor     r8d, r8d; wParam
0x18006d842  movzx   eax, word ptr [rsp+498h+Rect.right]
0x18006d847  mov     rcx, [rsp+498h+hWnd]; hWnd
0x18006d84c  shl     r9d, 10h
0x18006d850  lea     edx, [r8+5]; Msg
0x18006d854  or      r9, rax; lParam
0x18006d857  call    cs:__imp_SendMessageA
0x18006d85d  xor     eax, eax
0x18006d85f  mov     rcx, [rsp+498h+var_18]
0x18006d867  xor     rcx, rsp; StackCookie
0x18006d86a  call    __security_check_cookie
0x18006d86f  add     rsp, 490h
0x18006d876  pop     rbx
0x18006d877  retn
0x18006d878  mov     eax, 8007000Eh
0x18006d87d  jmp     short loc_18006D85F
```

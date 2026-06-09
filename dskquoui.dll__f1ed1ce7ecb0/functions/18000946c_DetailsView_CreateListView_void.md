# DetailsView::CreateListView(void)

- ea: `0x18000946c`
- end: `0x1800098a5`
- name: `?CreateListView@DetailsView@@AEAAJXZ`
- size: `1081`
- prototype: `__int64 __fastcall(DetailsView *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000e918`

## callees

- `0x180001510`
- `0x1800022b4`
- `0x1800081ec`
- `0x18000946c`
- `0x18001c134`
- `0x18001ca18`
- `0x18001ca80`
- `0x18001caec`

## import_xrefs

- `USER32!EnableMenuItem` at `0x1800096c2`
- `USER32!EnableMenuItem` at `0x1800096c2`
- `USER32!GetClientRect` at `0x1800094aa`
- `USER32!GetClientRect` at `0x1800094aa`
- `USER32!CheckMenuItem` at `0x180009680`
- `USER32!CheckMenuItem` at `0x180009680`
- `USER32!GetMenu` at `0x18000966f`
- `USER32!GetMenu` at `0x180009691`
- `USER32!GetMenu` at `0x18000966f`
- `USER32!GetMenu` at `0x180009691`
- `USER32!GetSubMenu` at `0x18000969d`
- `USER32!GetSubMenu` at `0x1800096a9`
- `USER32!GetSubMenu` at `0x18000969d`
- `USER32!GetSubMenu` at `0x1800096a9`
- `USER32!SendMessageW` at `0x180009549`
- `USER32!SendMessageW` at `0x180009591`
- `USER32!SendMessageW` at `0x18000961d`
- `USER32!SendMessageW` at `0x18000963d`
- `USER32!SendMessageW` at `0x180009659`
- `USER32!SendMessageW` at `0x180009754`
- `USER32!SendMessageW` at `0x180009793`
- `USER32!SendMessageW` at `0x1800097c0`
- `USER32!SendMessageW` at `0x18000986e`
- `USER32!SendMessageW` at `0x180009549`
- `USER32!SendMessageW` at `0x180009591`
- `USER32!SendMessageW` at `0x18000961d`
- `USER32!SendMessageW` at `0x18000963d`
- `USER32!SendMessageW` at `0x180009659`
- `USER32!SendMessageW` at `0x180009754`
- `USER32!SendMessageW` at `0x180009793`
- `USER32!SendMessageW` at `0x1800097c0`
- `USER32!SendMessageW` at `0x18000986e`
- `USER32!LoadIconW` at `0x180009820`
- `USER32!LoadIconW` at `0x180009820`
- `USER32!GetWindowLongPtrW` at `0x180009561`
- `USER32!GetWindowLongPtrW` at `0x180009561`
- `USER32!SetWindowLongPtrW` at `0x180009534`
- `USER32!SetWindowLongPtrW` at `0x18000957b`
- `USER32!SetWindowLongPtrW` at `0x180009534`
- `USER32!SetWindowLongPtrW` at `0x18000957b`
- `USER32!DestroyIcon` at `0x18000983f`
- `USER32!DestroyIcon` at `0x18000983f`

## pseudocode

```c
__int64 __fastcall DetailsView::CreateListView(DetailsView *this)
{
  HWND v2; // rcx
  HWND Window; // rax
  LRESULT v4; // rax
  HWND v5; // rcx
  LONG_PTR WindowLongPtrW; // rax
  HWND v7; // rcx
  int v8; // ebx
  int i; // esi
  __int64 v10; // rbx
  int v11; // eax
  UINT v12; // ebx
  HMENU Menu; // rax
  unsigned int v14; // ebx
  HMENU v15; // rax
  HMENU SubMenu; // rax
  HMENU v17; // rax
  HWND v18; // rax
  HWND v19; // rbx
  HWND v20; // rcx
  int v21; // ebx
  struct _IMAGELIST *v22; // r15
  unsigned int v23; // esi
  HICON IconW; // rax
  HICON v25; // r14
  tagRECT Rect; // [rsp+60h] [rbp-39h] BYREF
  LPARAM lParam; // [rsp+70h] [rbp-29h] BYREF
  HINSTANCE hInstance; // [rsp+78h] [rbp-21h]
  __m128i si128; // [rsp+80h] [rbp-19h]
  __int64 v31; // [rsp+90h] [rbp-9h]
  HINSTANCE v32; // [rsp+98h] [rbp-1h]
  __int64 v33; // [rsp+A0h] [rbp+7h]

  v2 = (HWND)*((_QWORD *)this + 12);
  Rect = 0;
  GetClientRect(v2, &Rect);
  Window = SHFusionCreateWindowEx(
             0x200u,
             L"SysListView32",
             &WindowName,
             0x56011009u,
             0,
             0,
             Rect.right - Rect.left,
             Rect.bottom - Rect.top,
             *((HWND *)this + 12),
             0,
             g_hInstDll,
             0);
  *((_QWORD *)this + 13) = Window;
  if ( Window )
  {
    SetWindowLongPtrW(Window, -21, (LONG_PTR)this);
    v4 = SendMessageW(*((HWND *)this + 13), 0x101Fu, 0, 0);
    v5 = (HWND)*((_QWORD *)this + 13);
    *((_QWORD *)this + 18) = v4;
    WindowLongPtrW = GetWindowLongPtrW(v5, -4);
    v7 = (HWND)*((_QWORD *)this + 13);
    *((_QWORD *)this + 21) = WindowLongPtrW;
    SetWindowLongPtrW(v7, -4, (LONG_PTR)DetailsView::LVSubClassWndProc);
    SendMessageW(*((HWND *)this + 13), 0x1036u, 0, 50);
    v8 = 0;
    for ( i = 0; i < ((*((_BYTE *)this + 588) & 4) != 0) + 7; ++i )
    {
      DetailsView::AddColumn(this, i, (const struct DV_COLDATA *)&qword_180021F00[2 * v8++]);
      if ( (*((_BYTE *)this + 588) & 4) == 0 && v8 == 1 )
        v8 = 2;
    }
    if ( *((_WORD *)this + 284) == 88 )
    {
      v10 = 0;
      do
      {
        if ( *((_DWORD *)this + v10 + 148) )
          SendMessageW(*((HWND *)this + 13), 0x101Eu, (int)v10, *((unsigned __int16 *)this + 2 * v10 + 296));
        v10 = (unsigned int)(v10 + 1);
      }
      while ( (unsigned int)v10 < 8 );
    }
    v11 = SendMessageW(*((HWND *)this + 18), 0x1200u, 0, 0);
    SendMessageW(*((HWND *)this + 18), 0x1212u, v11, (LPARAM)this + 624);
    v12 = 2 * (*((_WORD *)this + 294) & 4);
    Menu = GetMenu(*((HWND *)this + 12));
    CheckMenuItem(Menu, 0x9C59u, v12);
    v14 = *((unsigned __int16 *)this + 294);
    v15 = GetMenu(*((HWND *)this + 12));
    SubMenu = GetSubMenu(v15, 2);
    v17 = GetSubMenu(SubMenu, 4);
    EnableMenuItem(v17, 0x9C63u, ((v14 >> 2) & 1) == 0);
    v18 = SHFusionCreateWindowEx(
            0,
            L"tooltips_class32",
            0,
            1u,
            0x80000000,
            0x80000000,
            0x80000000,
            0x80000000,
            *((HWND *)this + 13),
            0,
            g_hInstDll,
            0);
    *((_QWORD *)this + 17) = v18;
    v19 = v18;
    if ( v18 )
    {
      memset_0(&lParam, 0, 0x48u);
      SendMessageW(v19, 0x403u, 3u, 500);
      hInstance = (HINSTANCE)*((_QWORD *)this + 13);
      si128.m128i_i64[0] = (__int64)hInstance;
      v20 = (HWND)*((_QWORD *)this + 17);
      lParam = 0x100000048LL;
      v32 = g_hInstDll;
      v33 = -1;
      if ( SendMessageW(v20, 0x432u, 0, (LPARAM)&lParam) )
        SendMessageW(
          *((HWND *)this + 17),
          0x401u,
          ((unsigned __int64)(unsigned __int16)~*((_WORD *)this + 294) >> 2) & 1,
          0);
    }
    v21 = 0;
    v22 = ImageList_Create(16, 16, 1u, 3, 0);
    v23 = 0;
    hInstance = g_hInstDll;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v32 = g_hInstDll;
    lParam = 132;
    v31 = 134;
    do
    {
      if ( v21 < 0 )
        break;
      IconW = LoadIconW(*(&hInstance + 2 * v23), (LPCWSTR)*(&lParam + 2 * v23));
      v25 = IconW;
      if ( IconW )
      {
        ImageList_ReplaceIcon(v22, -1, IconW);
        DestroyIcon(v25);
      }
      else
      {
        v21 = -2147467259;
      }
      ++v23;
    }
    while ( v23 < 3 );
    ImageList_SetBkColor(v22, 0xFFFFFFFF);
    SendMessageW(*((HWND *)this + 13), 0x1003u, 1u, (LPARAM)v22);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18000946c  mov     [rsp-8+arg_8], rbx
0x180009471  mov     [rsp-8+arg_10], rsi
0x180009476  push    rbp
0x180009477  push    rdi
0x180009478  push    r13
0x18000947a  push    r14
0x18000947c  push    r15
0x18000947e  lea     rbp, [rsp-37h]
0x180009483  sub     rsp, 0D0h
0x18000948a  mov     rax, cs:__security_cookie
0x180009491  xor     rax, rsp
0x180009494  mov     [rbp+57h+var_30], rax
0x180009498  mov     rdi, rcx
0x18000949b  lea     rdx, [rbp+57h+Rect]; lpRect
0x18000949f  mov     rcx, [rcx+60h]; hWnd
0x1800094a3  xorps   xmm0, xmm0
0x1800094a6  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x1800094aa  call    cs:__imp_GetClientRect
0x1800094b0  mov     rax, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstDll
0x1800094b7  mov     r9d, 56011009h; dwStyle
0x1800094bd  mov     r8d, [rbp+57h+Rect.bottom]
0x1800094c1  mov     ecx, 200h; dwExStyle
0x1800094c6  mov     edx, [rbp+57h+Rect.right]
0x1800094c9  sub     r8d, [rbp+57h+Rect.top]
0x1800094cd  sub     edx, [rbp+57h+Rect.left]
0x1800094d0  mov     [rsp+0F0h+var_98], 0; LPVOID
0x1800094d9  mov     [rsp+0F0h+var_A0], rax; HINSTANCE
0x1800094de  mov     rax, [rdi+60h]
0x1800094e2  mov     [rsp+0F0h+var_A8], 0; HMENU
0x1800094eb  mov     [rsp+0F0h+var_B0], rax; HWND
0x1800094f0  mov     [rsp+0F0h+var_B8], r8d; int
0x1800094f5  lea     r8, WindowName; lpWindowName
0x1800094fc  mov     [rsp+0F0h+var_C0], edx; int
0x180009500  lea     rdx, aSyslistview32; "SysListView32"
0x180009507  mov     [rsp+0F0h+var_C8], 0; int
0x18000950f  mov     [rsp+0F0h+cGrow], 0; int
0x180009517  call    SHFusionCreateWindowEx
0x18000951c  mov     [rdi+68h], rax
0x180009520  test    rax, rax
0x180009523  jz      loc_180009876
0x180009529  mov     r8, rdi; dwNewLong
0x18000952c  mov     edx, 0FFFFFFEBh; nIndex
0x180009531  mov     rcx, rax; hWnd
0x180009534  call    cs:__imp_SetWindowLongPtrW
0x18000953a  mov     rcx, [rdi+68h]; hWnd
0x18000953e  xor     r9d, r9d; lParam
0x180009541  xor     r8d, r8d; wParam
0x180009544  mov     edx, 101Fh; Msg
0x180009549  call    cs:__imp_SendMessageW
0x18000954f  mov     rcx, [rdi+68h]; hWnd
0x180009553  mov     ebx, 0FFFFFFFCh
0x180009558  mov     edx, ebx; nIndex
0x18000955a  mov     [rdi+90h], rax
0x180009561  call    cs:__imp_GetWindowLongPtrW
0x180009567  mov     rcx, [rdi+68h]; hWnd
0x18000956b  lea     r8, ?LVSubClassWndProc@DetailsView@@CA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x180009572  mov     edx, ebx; nIndex
0x180009574  mov     [rdi+0A8h], rax
0x18000957b  call    cs:__imp_SetWindowLongPtrW
0x180009581  mov     rcx, [rdi+68h]; hWnd
0x180009585  lea     r9d, [rbx+36h]; lParam
0x180009589  xor     r8d, r8d; wParam
0x18000958c  mov     edx, 1036h; Msg
0x180009591  call    cs:__imp_SendMessageW
0x180009597  xor     ebx, ebx
0x180009599  xor     esi, esi
0x18000959b  lea     r14d, [rbx+4]
0x18000959f  lea     r13d, [rbx+1]
0x1800095a3  lea     r15d, [rbx+2]
0x1800095a7  mov     al, [rdi+24Ch]
0x1800095ad  and     al, r14b
0x1800095b0  neg     al
0x1800095b2  sbb     ecx, ecx
0x1800095b4  neg     ecx
0x1800095b6  add     ecx, 7
0x1800095b9  cmp     esi, ecx
0x1800095bb  jge     short loc_1800095F2
0x1800095bd  lea     rax, qword_180021F00
0x1800095c4  movsxd  r8, ebx
0x1800095c7  shl     r8, 4
0x1800095cb  mov     edx, esi; int
0x1800095cd  add     r8, rax; struct DV_COLDATA *
0x1800095d0  mov     rcx, rdi; this
0x1800095d3  call    ?AddColumn@DetailsView@@AEAAJHAEBUDV_COLDATA@@@Z; DetailsView::AddColumn(int,DV_COLDATA const &)
0x1800095d8  add     ebx, r13d
0x1800095db  mov     eax, ebx
0x1800095dd  test    [rdi+24Ch], r14b
0x1800095e4  jnz     short loc_1800095ED
0x1800095e6  cmp     eax, r13d
0x1800095e9  cmovz   ebx, r15d
0x1800095ed  add     esi, r13d
0x1800095f0  jmp     short loc_1800095A7
0x1800095f2  cmp     word ptr [rdi+238h], 58h ; 'X'
0x1800095fa  jnz     short loc_18000962B
0x1800095fc  xor     ebx, ebx
0x1800095fe  cmp     dword ptr [rdi+rbx*4+250h], 0
0x180009606  jz      short loc_180009623
0x180009608  movzx   r9d, word ptr [rdi+rbx*4+250h]; lParam
0x180009611  mov     edx, 101Eh; Msg
0x180009616  mov     rcx, [rdi+68h]; hWnd
0x18000961a  movsxd  r8, ebx; wParam
0x18000961d  call    cs:__imp_SendMessageW
0x180009623  add     ebx, r13d
0x180009626  cmp     ebx, 8
0x180009629  jb      short loc_1800095FE
0x18000962b  mov     rcx, [rdi+90h]; hWnd
0x180009632  xor     r9d, r9d; lParam
0x180009635  xor     r8d, r8d; wParam
0x180009638  mov     edx, 1200h; Msg
0x18000963d  call    cs:__imp_SendMessageW
0x180009643  mov     rcx, [rdi+90h]; hWnd
0x18000964a  lea     r9, [rdi+270h]; lParam
0x180009651  movsxd  r8, eax; wParam
0x180009654  mov     edx, 1212h; Msg
0x180009659  call    cs:__imp_SendMessageW
0x18000965f  movzx   ebx, word ptr [rdi+24Ch]
0x180009666  mov     rcx, [rdi+60h]; hWnd
0x18000966a  and     ebx, r14d
0x18000966d  add     ebx, ebx
0x18000966f  call    cs:__imp_GetMenu
0x180009675  mov     r8d, ebx; uCheck
0x180009678  mov     edx, 9C59h; uIDCheckItem
0x18000967d  mov     rcx, rax; hMenu
0x180009680  call    cs:__imp_CheckMenuItem
0x180009686  mov     rcx, [rdi+60h]; hWnd
0x18000968a  movzx   ebx, word ptr [rdi+24Ch]
0x180009691  call    cs:__imp_GetMenu
0x180009697  mov     rcx, rax; hMenu
0x18000969a  mov     edx, r15d; nPos
0x18000969d  call    cs:__imp_GetSubMenu
0x1800096a3  mov     rcx, rax; hMenu
0x1800096a6  mov     edx, r14d; nPos
0x1800096a9  call    cs:__imp_GetSubMenu
0x1800096af  shr     ebx, 2
0x1800096b2  mov     edx, 9C63h; uIDEnableItem
0x1800096b7  not     ebx
0x1800096b9  mov     rcx, rax; hMenu
0x1800096bc  and     ebx, r13d
0x1800096bf  mov     r8d, ebx; uEnable
0x1800096c2  call    cs:__imp_EnableMenuItem
0x1800096c8  mov     rax, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstDll
0x1800096cf  lea     rdx, aTooltipsClass3; "tooltips_class32"
0x1800096d6  mov     [rsp+0F0h+var_98], 0; LPVOID
0x1800096df  mov     r9d, r13d; dwStyle
0x1800096e2  mov     [rsp+0F0h+var_A0], rax; HINSTANCE
0x1800096e7  xor     r8d, r8d; lpWindowName
0x1800096ea  mov     rax, [rdi+68h]
0x1800096ee  xor     ecx, ecx; dwExStyle
0x1800096f0  mov     [rsp+0F0h+var_A8], 0; HMENU
0x1800096f9  mov     [rsp+0F0h+var_B0], rax; HWND
0x1800096fe  mov     eax, 80000000h
0x180009703  mov     [rsp+0F0h+var_B8], eax; int
0x180009707  mov     [rsp+0F0h+var_C0], eax; int
0x18000970b  mov     [rsp+0F0h+var_C8], eax; int
0x18000970f  mov     [rsp+0F0h+cGrow], eax; int
0x180009713  call    SHFusionCreateWindowEx
0x180009718  mov     [rdi+88h], rax
0x18000971f  mov     rbx, rax
0x180009722  mov     r14d, 3
0x180009728  test    rax, rax
0x18000972b  jz      loc_1800097C6
0x180009731  lea     esi, [r14+45h]
0x180009735  xor     edx, edx; Val
0x180009737  mov     r8d, esi; Size
0x18000973a  lea     rcx, [rbp+57h+lParam]; void *
0x18000973e  call    memset_0
0x180009743  mov     r9d, 1F4h; lParam
0x180009749  mov     r8d, r14d; wParam
0x18000974c  mov     edx, 403h; Msg
0x180009751  mov     rcx, rbx; hWnd
0x180009754  call    cs:__imp_SendMessageW
0x18000975a  mov     rcx, [rdi+68h]
0x18000975e  lea     r9, [rbp+57h+lParam]; lParam
0x180009762  mov     rax, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstDll
0x180009769  xor     r8d, r8d; wParam
0x18000976c  mov     [rbp+57h+hInstance], rcx
0x180009770  mov     edx, 432h; Msg
0x180009775  mov     qword ptr [rbp+57h+var_70], rcx
0x180009779  mov     rcx, [rdi+88h]; hWnd
0x180009780  mov     dword ptr [rbp+57h+lParam], esi
0x180009783  mov     dword ptr [rbp+57h+lParam+4], r13d
0x180009787  mov     [rbp+57h+var_58], rax
0x18000978b  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFFh
0x180009793  call    cs:__imp_SendMessageW
0x180009799  test    rax, rax
0x18000979c  jz      short loc_1800097C6
0x18000979e  movzx   r8d, word ptr [rdi+24Ch]
0x1800097a6  xor     r9d, r9d; lParam
0x1800097a9  mov     rcx, [rdi+88h]; hWnd
0x1800097b0  not     r8w
0x1800097b4  shr     r8, 2
0x1800097b8  mov     edx, 401h; Msg
0x1800097bd  and     r8, r13; wParam
0x1800097c0  call    cs:__imp_SendMessageW
0x1800097c6  xor     ebx, ebx
0x1800097c8  mov     r9d, r14d; cInitial
0x1800097cb  mov     r8d, r13d; flags
0x1800097ce  mov     [rsp+0F0h+cGrow], ebx; cGrow
0x1800097d2  lea     ecx, [rbx+10h]; cx
0x1800097d5  mov     edx, ecx; cy
0x1800097d7  call    ImageList_Create
0x1800097dc  mov     rcx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstDll
0x1800097e3  mov     r15, rax
0x1800097e6  movdqa  xmm0, cs:__xmm@00000000000000000000000000007f03
0x1800097ee  xor     esi, esi
0x1800097f0  mov     [rbp+57h+hInstance], rcx
0x1800097f4  movdqu  [rbp+57h+var_70], xmm0
0x1800097f9  mov     [rbp+57h+var_58], rcx
0x1800097fd  mov     [rbp+57h+lParam], 84h
0x180009805  mov     [rbp+57h+var_60], 86h
0x18000980d  test    ebx, ebx
0x18000980f  js      short loc_180009854
0x180009811  mov     ecx, esi
0x180009813  add     rcx, rcx
0x180009816  mov     rdx, [rbp+rcx*8+57h+lParam]; lpIconName
0x18000981b  mov     rcx, [rbp+rcx*8+57h+hInstance]; hInstance
0x180009820  call    cs:__imp_LoadIconW
0x180009826  mov     r14, rax
0x180009829  test    rax, rax
0x18000982c  jz      short loc_180009847
0x18000982e  mov     r8, rax; hicon
0x180009831  or      edx, 0FFFFFFFFh; i
0x180009834  mov     rcx, r15; himl
0x180009837  call    ImageList_ReplaceIcon
0x18000983c  mov     rcx, r14; hIcon
0x18000983f  call    cs:__imp_DestroyIcon
0x180009845  jmp     short loc_18000984C
0x180009847  mov     ebx, 80004005h
0x18000984c  add     esi, r13d
0x18000984f  cmp     esi, 3
0x180009852  jb      short loc_18000980D
0x180009854  or      edx, 0FFFFFFFFh; clrBk
0x180009857  mov     rcx, r15; himl
0x18000985a  call    ImageList_SetBkColor
0x18000985f  mov     rcx, [rdi+68h]; hWnd
0x180009863  mov     r9, r15; lParam
0x180009866  mov     r8, r13; wParam
0x180009869  mov     edx, 1003h; Msg
0x18000986e  call    cs:__imp_SendMessageW
0x180009874  jmp     short loc_18000987B
0x180009876  mov     ebx, 80004005h
0x18000987b  mov     eax, ebx
0x18000987d  mov     rcx, [rbp+57h+var_30]
0x180009881  xor     rcx, rsp; StackCookie
0x180009884  call    __security_check_cookie
0x180009889  lea     r11, [rsp+0F0h+var_20]
0x180009891  mov     rbx, [r11+38h]
0x180009895  mov     rsi, [r11+40h]
0x180009899  mov     rsp, r11
0x18000989c  pop     r15
0x18000989e  pop     r14
0x1800098a0  pop     r13
0x1800098a2  pop     rdi
0x1800098a3  pop     rbp
0x1800098a4  retn
```

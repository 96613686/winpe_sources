# CNovInterDlg::OnDialogResize(uint,unsigned __int64,__int64,int &)

- ea: `0x140021540`
- end: `0x140021a55`
- name: `?OnDialogResize@CNovInterDlg@@QEAA_JI_K_JAEAH@Z`
- size: `1301`
- prototype: `__int64(CNovInterDlg *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140023830`

## callees

- `0x140021540`
- `0x14004ad80`

## import_xrefs

- `USER32!SendMessageW` at `0x1400219cb`
- `USER32!SendMessageW` at `0x1400219cb`
- `USER32!GetDlgItem` at `0x140021638`
- `USER32!GetDlgItem` at `0x1400216dd`
- `USER32!GetDlgItem` at `0x140021783`
- `USER32!GetDlgItem` at `0x140021815`
- `USER32!GetDlgItem` at `0x1400218ab`
- `USER32!GetDlgItem` at `0x140021936`
- `USER32!GetDlgItem` at `0x140021638`
- `USER32!GetDlgItem` at `0x1400216dd`
- `USER32!GetDlgItem` at `0x140021783`
- `USER32!GetDlgItem` at `0x140021815`
- `USER32!GetDlgItem` at `0x1400218ab`
- `USER32!GetDlgItem` at `0x140021936`
- `USER32!InvalidateRect` at `0x1400216b9`
- `USER32!InvalidateRect` at `0x14002175f`
- `USER32!InvalidateRect` at `0x1400217ea`
- `USER32!InvalidateRect` at `0x140021887`
- `USER32!InvalidateRect` at `0x140021912`
- `USER32!InvalidateRect` at `0x14002199e`
- `USER32!InvalidateRect` at `0x1400219e3`
- `USER32!InvalidateRect` at `0x140021a12`
- `USER32!InvalidateRect` at `0x1400216b9`
- `USER32!InvalidateRect` at `0x14002175f`
- `USER32!InvalidateRect` at `0x1400217ea`
- `USER32!InvalidateRect` at `0x140021887`
- `USER32!InvalidateRect` at `0x140021912`
- `USER32!InvalidateRect` at `0x14002199e`
- `USER32!InvalidateRect` at `0x1400219e3`
- `USER32!InvalidateRect` at `0x140021a12`
- `USER32!MapDialogRect` at `0x14002161d`
- `USER32!MapDialogRect` at `0x14002165c`
- `USER32!MapDialogRect` at `0x14002171f`
- `USER32!MapDialogRect` at `0x1400217a7`
- `USER32!MapDialogRect` at `0x140021839`
- `USER32!MapDialogRect` at `0x1400218cf`
- `USER32!MapDialogRect` at `0x14002195a`
- `USER32!MapDialogRect` at `0x14002161d`
- `USER32!MapDialogRect` at `0x14002165c`
- `USER32!MapDialogRect` at `0x14002171f`
- `USER32!MapDialogRect` at `0x1400217a7`
- `USER32!MapDialogRect` at `0x140021839`
- `USER32!MapDialogRect` at `0x1400218cf`
- `USER32!MapDialogRect` at `0x14002195a`
- `USER32!UpdateWindow` at `0x1400216c8`
- `USER32!UpdateWindow` at `0x14002176e`
- `USER32!UpdateWindow` at `0x1400217f9`
- `USER32!UpdateWindow` at `0x140021896`
- `USER32!UpdateWindow` at `0x140021921`
- `USER32!UpdateWindow` at `0x1400219ad`
- `USER32!UpdateWindow` at `0x1400219f6`
- `USER32!UpdateWindow` at `0x140021a22`
- `USER32!UpdateWindow` at `0x1400216c8`
- `USER32!UpdateWindow` at `0x14002176e`
- `USER32!UpdateWindow` at `0x1400217f9`
- `USER32!UpdateWindow` at `0x140021896`
- `USER32!UpdateWindow` at `0x140021921`
- `USER32!UpdateWindow` at `0x1400219ad`
- `USER32!UpdateWindow` at `0x1400219f6`
- `USER32!UpdateWindow` at `0x140021a22`
- `USER32!MoveWindow` at `0x1400216a5`
- `USER32!MoveWindow` at `0x14002174b`
- `USER32!MoveWindow` at `0x1400217d6`
- `USER32!MoveWindow` at `0x140021873`
- `USER32!MoveWindow` at `0x1400218fe`
- `USER32!MoveWindow` at `0x14002198a`
- `USER32!MoveWindow` at `0x1400216a5`
- `USER32!MoveWindow` at `0x14002174b`
- `USER32!MoveWindow` at `0x1400217d6`
- `USER32!MoveWindow` at `0x140021873`
- `USER32!MoveWindow` at `0x1400218fe`
- `USER32!MoveWindow` at `0x14002198a`
- `USER32!GetClientRect` at `0x140021583`
- `USER32!GetClientRect` at `0x1400215b8`
- `USER32!GetClientRect` at `0x1400215d3`
- `USER32!GetClientRect` at `0x1400216f3`
- `USER32!GetClientRect` at `0x140021583`
- `USER32!GetClientRect` at `0x1400215b8`
- `USER32!GetClientRect` at `0x1400215d3`
- `USER32!GetClientRect` at `0x1400216f3`

## pseudocode

```c
__int64 __fastcall CNovInterDlg::OnDialogResize(CNovInterDlg *this, __int64 a2, WPARAM a3, LPARAM a4)
{
  int v6; // r12d
  int v7; // r14d
  LONG bottom; // r15d
  LONG v9; // edi
  int v10; // edi
  HWND v11; // rcx
  HWND DlgItem; // rax
  HWND v13; // rcx
  HWND v14; // rbx
  int v15; // r9d
  HWND v16; // rdi
  HWND v17; // rcx
  LONG right; // ebx
  HWND v19; // rax
  HWND v20; // rcx
  HWND v21; // rbx
  HWND v22; // rax
  HWND v23; // rcx
  HWND v24; // rbx
  HWND v25; // rax
  HWND v26; // rcx
  HWND v27; // rbx
  HWND v28; // rax
  HWND v29; // rcx
  HWND v30; // rbx
  LONG v32; // [rsp+30h] [rbp-30h]
  LONG v33; // [rsp+34h] [rbp-2Ch]
  struct tagRECT Rect; // [rsp+40h] [rbp-20h] BYREF

  Rect = 0;
  if ( a4 )
  {
    v7 = (unsigned __int16)a4;
    v6 = WORD1(a4);
  }
  else
  {
    GetClientRect(*((HWND *)this + 1), &Rect);
    v6 = Rect.bottom - Rect.top;
    v7 = Rect.right - Rect.left;
  }
  GetClientRect(*((HWND *)this + 9), &Rect);
  bottom = Rect.bottom;
  GetClientRect(*((HWND *)this + 22), &Rect);
  v9 = Rect.bottom;
  v33 = Rect.bottom;
  if ( !*((_DWORD *)this + 22) )
  {
    v10 = *(_DWORD *)(*((_QWORD *)_AtlModule + 104) + 136LL);
    if ( v10 != 3 )
    {
      v11 = (HWND)*((_QWORD *)this + 1);
      Rect.bottom = *((_DWORD *)this + 48);
      MapDialogRect(v11, &Rect);
      v32 = Rect.bottom;
      DlgItem = GetDlgItem(*((HWND *)this + 1), 1059);
      v13 = (HWND)*((_QWORD *)this + 1);
      v14 = DlgItem;
      Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
      MapDialogRect(v13, &Rect);
      v15 = v7 - Rect.right;
      if ( v10 == 8 )
        MoveWindow(v14, Rect.left, Rect.top + bottom, v15, v32 - 2 * Rect.top, 1);
      else
        MoveWindow(v14, Rect.left, bottom + Rect.top, v15, Rect.bottom, 1);
      InvalidateRect(v14, 0, 0);
      UpdateWindow(v14);
      v16 = GetDlgItem(*((HWND *)this + 1), 1042);
      GetClientRect(v16, &Rect);
      v17 = (HWND)*((_QWORD *)this + 1);
      right = Rect.right;
      Rect.left = 4;
      Rect.top = 20;
      Rect.bottom = 11;
      MapDialogRect(v17, &Rect);
      MoveWindow(v16, Rect.left, bottom + Rect.top, right + 2, Rect.bottom, 1);
      InvalidateRect(v16, 0, 0);
      UpdateWindow(v16);
      v19 = GetDlgItem(*((HWND *)this + 1), 1006);
      v20 = (HWND)*((_QWORD *)this + 1);
      v21 = v19;
      Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
      MapDialogRect(v20, &Rect);
      MoveWindow(v21, Rect.left, bottom + Rect.top, v7 - Rect.right, Rect.bottom, 1);
      InvalidateRect(v21, 0, 0);
      UpdateWindow(v21);
      bottom += v32;
    }
    v9 = v33;
  }
  v22 = GetDlgItem(*((HWND *)this + 1), 1035);
  v23 = (HWND)*((_QWORD *)this + 1);
  v24 = v22;
  Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
  MapDialogRect(v23, &Rect);
  MoveWindow(v24, Rect.left, bottom + Rect.top, v7 - Rect.right, v6 - Rect.bottom - v9 - bottom, 1);
  InvalidateRect(v24, 0, 1);
  UpdateWindow(v24);
  v25 = GetDlgItem(*((HWND *)this + 1), 1036);
  v26 = (HWND)*((_QWORD *)this + 1);
  v27 = v25;
  Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
  MapDialogRect(v26, &Rect);
  MoveWindow(v27, Rect.left, v6 - Rect.top - v9, v7 - Rect.right, Rect.bottom, 1);
  InvalidateRect(v27, 0, 1);
  UpdateWindow(v27);
  v28 = GetDlgItem(*((HWND *)this + 1), 1037);
  v29 = (HWND)*((_QWORD *)this + 1);
  v30 = v28;
  Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
  MapDialogRect(v29, &Rect);
  MoveWindow(v30, v7 - Rect.left, v6 - Rect.top - v9, Rect.right, Rect.bottom, 1);
  InvalidateRect(v30, 0, 1);
  UpdateWindow(v30);
  SendMessageW(*((HWND *)this + 22), 5u, a3, a4);
  InvalidateRect(*((HWND *)this + 22), 0, 1);
  UpdateWindow(*((HWND *)this + 22));
  InvalidateRect(*((HWND *)this + 1), 0, a4 != 0);
  UpdateWindow(*((HWND *)this + 1));
  return 0;
}

```

## disassembly

```asm
0x140021540  mov     [rsp-38h+arg_8], rbx
0x140021545  push    rbp
0x140021546  push    rsi
0x140021547  push    rdi
0x140021548  push    r12
0x14002154a  push    r13
0x14002154c  push    r14
0x14002154e  push    r15
0x140021550  mov     rbp, rsp
0x140021553  sub     rsp, 60h
0x140021557  mov     rax, cs:__security_cookie
0x14002155e  xor     rax, rsp
0x140021561  mov     [rbp+var_10], rax
0x140021565  mov     [rbp+wParam], r8
0x140021569  xorps   xmm0, xmm0
0x14002156c  mov     r13, r9
0x14002156f  mov     rsi, rcx
0x140021572  movups  xmmword ptr [rbp+Rect.left], xmm0
0x140021576  test    r9, r9
0x140021579  jnz     short loc_1400215A1
0x14002157b  mov     rcx, [rcx+8]; hWnd
0x14002157f  lea     rdx, [rbp+Rect]; lpRect
0x140021583  call    cs:__imp_GetClientRect
0x14002158a  nop     dword ptr [rax+rax+00h]
0x14002158f  mov     r12d, [rbp+Rect.bottom]
0x140021593  sub     r12d, [rbp+Rect.top]
0x140021597  mov     r14d, [rbp+Rect.right]
0x14002159b  sub     r14d, [rbp+Rect.left]
0x14002159f  jmp     short loc_1400215B0
0x1400215a1  mov     rax, r13
0x1400215a4  movzx   r14d, r13w
0x1400215a8  shr     rax, 10h
0x1400215ac  movzx   r12d, ax
0x1400215b0  mov     rcx, [rsi+48h]; hWnd
0x1400215b4  lea     rdx, [rbp+Rect]; lpRect
0x1400215b8  call    cs:__imp_GetClientRect
0x1400215bf  nop     dword ptr [rax+rax+00h]
0x1400215c4  mov     rcx, [rsi+0B0h]; hWnd
0x1400215cb  lea     rdx, [rbp+Rect]; lpRect
0x1400215cf  mov     r15d, [rbp+Rect.bottom]
0x1400215d3  call    cs:__imp_GetClientRect
0x1400215da  nop     dword ptr [rax+rax+00h]
0x1400215df  cmp     dword ptr [rsi+58h], 0
0x1400215e3  mov     edi, [rbp+Rect.bottom]
0x1400215e6  mov     [rbp+var_2C], edi
0x1400215e9  jnz     loc_14002180C
0x1400215ef  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400215f6  mov     rcx, [rax+340h]
0x1400215fd  mov     edi, [rcx+88h]
0x140021603  cmp     edi, 3
0x140021606  jz      loc_140021809
0x14002160c  mov     eax, [rsi+0C0h]
0x140021612  lea     rdx, [rbp+Rect]; lpRect
0x140021616  mov     rcx, [rsi+8]; hDlg
0x14002161a  mov     [rbp+Rect.bottom], eax
0x14002161d  call    cs:__imp_MapDialogRect
0x140021624  nop     dword ptr [rax+rax+00h]
0x140021629  mov     eax, [rbp+Rect.bottom]
0x14002162c  mov     edx, 423h; nIDDlgItem
0x140021631  mov     rcx, [rsi+8]; hDlg
0x140021635  mov     [rbp+var_30], eax
0x140021638  call    cs:__imp_GetDlgItem
0x14002163f  nop     dword ptr [rax+rax+00h]
0x140021644  movdqa  xmm0, cs:__xmm@0000000c000000080000000400000004
0x14002164c  lea     rdx, [rbp+Rect]; lpRect
0x140021650  mov     rcx, [rsi+8]; hDlg
0x140021654  mov     rbx, rax
0x140021657  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x14002165c  call    cs:__imp_MapDialogRect
0x140021663  nop     dword ptr [rax+rax+00h]
0x140021668  mov     r9d, r14d
0x14002166b  mov     [rsp+60h+bRepaint], 1; bRepaint
0x140021673  sub     r9d, [rbp+Rect.right]; nWidth
0x140021677  cmp     edi, 8
0x14002167a  jz      short loc_14002168C
0x14002167c  mov     r8d, [rbp+Rect.top]
0x140021680  mov     eax, [rbp+Rect.bottom]
0x140021683  add     r8d, r15d
0x140021686  mov     [rsp+60h+nHeight], eax
0x14002168a  jmp     short loc_14002169F
0x14002168c  mov     ecx, [rbp+Rect.top]
0x14002168f  mov     edx, [rbp+var_30]
0x140021692  lea     eax, [rcx+rcx]
0x140021695  sub     edx, eax
0x140021697  lea     r8d, [rcx+r15]; Y
0x14002169b  mov     [rsp+60h+nHeight], edx; nHeight
0x14002169f  mov     edx, [rbp+Rect.left]; X
0x1400216a2  mov     rcx, rbx; hWnd
0x1400216a5  call    cs:__imp_MoveWindow
0x1400216ac  nop     dword ptr [rax+rax+00h]
0x1400216b1  xor     r8d, r8d; bErase
0x1400216b4  xor     edx, edx; lpRect
0x1400216b6  mov     rcx, rbx; hWnd
0x1400216b9  call    cs:__imp_InvalidateRect
0x1400216c0  nop     dword ptr [rax+rax+00h]
0x1400216c5  mov     rcx, rbx; hWnd
0x1400216c8  call    cs:__imp_UpdateWindow
0x1400216cf  nop     dword ptr [rax+rax+00h]
0x1400216d4  mov     rcx, [rsi+8]; hDlg
0x1400216d8  mov     edx, 412h; nIDDlgItem
0x1400216dd  call    cs:__imp_GetDlgItem
0x1400216e4  nop     dword ptr [rax+rax+00h]
0x1400216e9  mov     rcx, rax; hWnd
0x1400216ec  lea     rdx, [rbp+Rect]; lpRect
0x1400216f0  mov     rdi, rax
0x1400216f3  call    cs:__imp_GetClientRect
0x1400216fa  nop     dword ptr [rax+rax+00h]
0x1400216ff  mov     rcx, [rsi+8]; hDlg
0x140021703  lea     rdx, [rbp+Rect]; lpRect
0x140021707  mov     ebx, [rbp+Rect.right]
0x14002170a  mov     [rbp+Rect.left], 4
0x140021711  mov     [rbp+Rect.top], 14h
0x140021718  mov     [rbp+Rect.bottom], 0Bh
0x14002171f  call    cs:__imp_MapDialogRect
0x140021726  nop     dword ptr [rax+rax+00h]
0x14002172b  mov     r8d, [rbp+Rect.top]
0x14002172f  lea     r9d, [rbx+2]; nWidth
0x140021733  mov     eax, [rbp+Rect.bottom]
0x140021736  add     r8d, r15d; Y
0x140021739  mov     edx, [rbp+Rect.left]; X
0x14002173c  mov     rcx, rdi; hWnd
0x14002173f  mov     [rsp+60h+bRepaint], 1; bRepaint
0x140021747  mov     [rsp+60h+nHeight], eax; nHeight
0x14002174b  call    cs:__imp_MoveWindow
0x140021752  nop     dword ptr [rax+rax+00h]
0x140021757  xor     r8d, r8d; bErase
0x14002175a  xor     edx, edx; lpRect
0x14002175c  mov     rcx, rdi; hWnd
0x14002175f  call    cs:__imp_InvalidateRect
0x140021766  nop     dword ptr [rax+rax+00h]
0x14002176b  mov     rcx, rdi; hWnd
0x14002176e  call    cs:__imp_UpdateWindow
0x140021775  nop     dword ptr [rax+rax+00h]
0x14002177a  mov     rcx, [rsi+8]; hDlg
0x14002177e  mov     edx, 3EEh; nIDDlgItem
0x140021783  call    cs:__imp_GetDlgItem
0x14002178a  nop     dword ptr [rax+rax+00h]
0x14002178f  movdqa  xmm0, cs:__xmm@00000010000000080000002300000004
0x140021797  lea     rdx, [rbp+Rect]; lpRect
0x14002179b  mov     rcx, [rsi+8]; hDlg
0x14002179f  mov     rbx, rax
0x1400217a2  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x1400217a7  call    cs:__imp_MapDialogRect
0x1400217ae  nop     dword ptr [rax+rax+00h]
0x1400217b3  mov     ecx, [rbp+Rect.bottom]
0x1400217b6  mov     r9d, r14d
0x1400217b9  mov     r8d, [rbp+Rect.top]
0x1400217bd  sub     r9d, [rbp+Rect.right]; nWidth
0x1400217c1  add     r8d, r15d; Y
0x1400217c4  mov     edx, [rbp+Rect.left]; X
0x1400217c7  mov     [rsp+60h+bRepaint], 1; bRepaint
0x1400217cf  mov     [rsp+60h+nHeight], ecx; nHeight
0x1400217d3  mov     rcx, rbx; hWnd
0x1400217d6  call    cs:__imp_MoveWindow
0x1400217dd  nop     dword ptr [rax+rax+00h]
0x1400217e2  xor     r8d, r8d; bErase
0x1400217e5  xor     edx, edx; lpRect
0x1400217e7  mov     rcx, rbx; hWnd
0x1400217ea  call    cs:__imp_InvalidateRect
0x1400217f1  nop     dword ptr [rax+rax+00h]
0x1400217f6  mov     rcx, rbx; hWnd
0x1400217f9  call    cs:__imp_UpdateWindow
0x140021800  nop     dword ptr [rax+rax+00h]
0x140021805  add     r15d, [rbp+var_30]
0x140021809  mov     edi, [rbp+var_2C]
0x14002180c  mov     rcx, [rsi+8]; hDlg
0x140021810  mov     edx, 40Bh; nIDDlgItem
0x140021815  call    cs:__imp_GetDlgItem
0x14002181c  nop     dword ptr [rax+rax+00h]
0x140021821  movdqa  xmm0, cs:__xmm@00000038000000080000000400000004
0x140021829  lea     rdx, [rbp+Rect]; lpRect
0x14002182d  mov     rcx, [rsi+8]; hDlg
0x140021831  mov     rbx, rax
0x140021834  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x140021839  call    cs:__imp_MapDialogRect
0x140021840  nop     dword ptr [rax+rax+00h]
0x140021845  mov     r8d, [rbp+Rect.top]
0x140021849  mov     ecx, r12d
0x14002184c  sub     ecx, [rbp+Rect.bottom]
0x14002184f  add     r8d, r15d; Y
0x140021852  mov     edx, [rbp+Rect.left]; X
0x140021855  sub     ecx, edi
0x140021857  sub     ecx, r15d
0x14002185a  mov     r9d, r14d
0x14002185d  sub     r9d, [rbp+Rect.right]; nWidth
0x140021861  mov     r15d, 1
0x140021867  mov     [rsp+60h+bRepaint], r15d; bRepaint
0x14002186c  mov     [rsp+60h+nHeight], ecx; nHeight
0x140021870  mov     rcx, rbx; hWnd
0x140021873  call    cs:__imp_MoveWindow
0x14002187a  nop     dword ptr [rax+rax+00h]
0x14002187f  mov     r8d, r15d; bErase
0x140021882  xor     edx, edx; lpRect
0x140021884  mov     rcx, rbx; hWnd
0x140021887  call    cs:__imp_InvalidateRect
0x14002188e  nop     dword ptr [rax+rax+00h]
0x140021893  mov     rcx, rbx; hWnd
0x140021896  call    cs:__imp_UpdateWindow
0x14002189d  nop     dword ptr [rax+rax+00h]
0x1400218a2  mov     rcx, [rsi+8]; hDlg
0x1400218a6  mov     edx, 40Ch; nIDDlgItem
0x1400218ab  call    cs:__imp_GetDlgItem
0x1400218b2  nop     dword ptr [rax+rax+00h]
0x1400218b7  movdqa  xmm0, cs:__xmm@0000001c000000080000003000000004
0x1400218bf  lea     rdx, [rbp+Rect]; lpRect
0x1400218c3  mov     rcx, [rsi+8]; hDlg
0x1400218c7  mov     rbx, rax
0x1400218ca  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x1400218cf  call    cs:__imp_MapDialogRect
0x1400218d6  nop     dword ptr [rax+rax+00h]
0x1400218db  mov     eax, [rbp+Rect.bottom]
0x1400218de  mov     r8d, r12d
0x1400218e1  sub     r8d, [rbp+Rect.top]
0x1400218e5  mov     r9d, r14d
0x1400218e8  sub     r9d, [rbp+Rect.right]; nWidth
0x1400218ec  sub     r8d, edi; Y
0x1400218ef  mov     edx, [rbp+Rect.left]; X
0x1400218f2  mov     rcx, rbx; hWnd
0x1400218f5  mov     [rsp+60h+bRepaint], r15d; bRepaint
0x1400218fa  mov     [rsp+60h+nHeight], eax; nHeight
0x1400218fe  call    cs:__imp_MoveWindow
0x140021905  nop     dword ptr [rax+rax+00h]
0x14002190a  mov     r8d, r15d; bErase
0x14002190d  xor     edx, edx; lpRect
0x14002190f  mov     rcx, rbx; hWnd
0x140021912  call    cs:__imp_InvalidateRect
0x140021919  nop     dword ptr [rax+rax+00h]
0x14002191e  mov     rcx, rbx; hWnd
0x140021921  call    cs:__imp_UpdateWindow
0x140021928  nop     dword ptr [rax+rax+00h]
0x14002192d  mov     rcx, [rsi+8]; hDlg
0x140021931  mov     edx, 40Dh; nIDDlgItem
0x140021936  call    cs:__imp_GetDlgItem
0x14002193d  nop     dword ptr [rax+rax+00h]
0x140021942  movdqa  xmm0, cs:__xmm@0000000c00000036000000100000003a
0x14002194a  lea     rdx, [rbp+Rect]; lpRect
0x14002194e  mov     rcx, [rsi+8]; hDlg
0x140021952  mov     rbx, rax
0x140021955  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x14002195a  call    cs:__imp_MapDialogRect
0x140021961  nop     dword ptr [rax+rax+00h]
0x140021966  sub     r12d, [rbp+Rect.top]
0x14002196a  mov     rcx, rbx; hWnd
0x14002196d  sub     r14d, [rbp+Rect.left]
0x140021971  sub     r12d, edi
0x140021974  mov     eax, [rbp+Rect.bottom]
0x140021977  mov     r8d, r12d; Y
0x14002197a  mov     r9d, [rbp+Rect.right]; nWidth
0x14002197e  mov     edx, r14d; X
0x140021981  mov     [rsp+60h+bRepaint], r15d; bRepaint
0x140021986  mov     [rsp+60h+nHeight], eax; nHeight
0x14002198a  call    cs:__imp_MoveWindow
0x140021991  nop     dword ptr [rax+rax+00h]
0x140021996  mov     r8d, r15d; bErase
0x140021999  xor     edx, edx; lpRect
0x14002199b  mov     rcx, rbx; hWnd
0x14002199e  call    cs:__imp_InvalidateRect
0x1400219a5  nop     dword ptr [rax+rax+00h]
0x1400219aa  mov     rcx, rbx; hWnd
0x1400219ad  call    cs:__imp_UpdateWindow
0x1400219b4  nop     dword ptr [rax+rax+00h]
0x1400219b9  mov     r8, [rbp+wParam]; wParam
0x1400219bd  lea     edx, [r15+4]; Msg
0x1400219c1  mov     rcx, [rsi+0B0h]; hWnd
0x1400219c8  mov     r9, r13; lParam
0x1400219cb  call    cs:__imp_SendMessageW
0x1400219d2  nop     dword ptr [rax+rax+00h]
0x1400219d7  mov     rcx, [rsi+0B0h]; hWnd
0x1400219de  mov     r8d, r15d; bErase
0x1400219e1  xor     edx, edx; lpRect
0x1400219e3  call    cs:__imp_InvalidateRect
0x1400219ea  nop     dword ptr [rax+rax+00h]
0x1400219ef  mov     rcx, [rsi+0B0h]; hWnd
0x1400219f6  call    cs:__imp_UpdateWindow
0x1400219fd  nop     dword ptr [rax+rax+00h]
0x140021a02  mov     rcx, [rsi+8]; hWnd
0x140021a06  xor     r8d, r8d
0x140021a09  test    r13, r13
0x140021a0c  setnz   r8b; bErase
0x140021a10  xor     edx, edx; lpRect
0x140021a12  call    cs:__imp_InvalidateRect
0x140021a19  nop     dword ptr [rax+rax+00h]
0x140021a1e  mov     rcx, [rsi+8]; hWnd
0x140021a22  call    cs:__imp_UpdateWindow
0x140021a29  nop     dword ptr [rax+rax+00h]
0x140021a2e  xor     eax, eax
0x140021a30  mov     rcx, [rbp+var_10]
0x140021a34  xor     rcx, rsp; StackCookie
0x140021a37  call    __security_check_cookie
0x140021a3c  mov     rbx, [rsp+60h+arg_8]
0x140021a44  add     rsp, 60h
0x140021a48  pop     r15
0x140021a4a  pop     r14
0x140021a4c  pop     r13
0x140021a4e  pop     r12
0x140021a50  pop     rdi
0x140021a51  pop     rsi
0x140021a52  pop     rbp
0x140021a53  retn
```

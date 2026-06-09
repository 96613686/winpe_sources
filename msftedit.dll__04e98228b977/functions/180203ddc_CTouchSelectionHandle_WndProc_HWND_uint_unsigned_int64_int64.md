# CTouchSelectionHandle::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180203ddc`
- end: `0x180204045`
- name: `?WndProc@CTouchSelectionHandle@@IEAA_JPEAUHWND__@@I_K_J@Z`
- size: `617`
- prototype: `__int64 __fastcall(CTouchSelectionHandle *__hidden this, HWND hWnd, unsigned int, unsigned __int64, LPARAM lParam)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1802010e0`

## callees

- `0x180008fdc`
- `0x18013ce80`
- `0x18013dce6`
- `0x1801feb38`
- `0x1801feb84`
- `0x1802005e4`
- `0x18020119c`
- `0x18020146c`
- `0x180202ba4`
- `0x180202ed0`
- `0x180203b78`
- `0x180203ddc`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x180203fd8`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x180203fd8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x180203ea6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x180203eba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x180203ea6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x180203eba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x180203e8b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x180203e8b`
- `ext-ms-win-ntuser-draw-l1-1-0!GetUpdateRect` at `0x180203eee`
- `ext-ms-win-ntuser-draw-l1-1-0!GetUpdateRect` at `0x180203eee`

## pseudocode

```c
LRESULT __fastcall CTouchSelectionHandle::WndProc(
        CTouchSelectionHandle *this,
        HWND hWnd,
        unsigned int a3,
        unsigned __int64 a4,
        LPARAM lParam)
{
  _BOOL8 v9; // rcx
  __int64 v10; // rax
  LONG WindowLongW; // ebx
  HDC v12; // rbx
  bool v13; // r8
  unsigned int v15; // [rsp+50h] [rbp-A8h] BYREF
  unsigned int v16; // [rsp+54h] [rbp-A4h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-A0h] BYREF
  _BYTE v18[80]; // [rsp+70h] [rbp-88h] BYREF

  v9 = CTouchTracker::HandleTouchWindowMessage(this, a3, a4, a4);
  v10 = *((_QWORD *)this + 15);
  if ( v10 && a3 == *(_DWORD *)(v10 + 64) )
  {
    CTouchSelectionHandle::Show(this, (struct tagPOINT *)this + 7, *((_BYTE *)this + 112), 1);
    return 0;
  }
  if ( a3 > 0x21 )
  {
    if ( a3 == 256 || a3 == 513 || a3 == 516 || a3 == 519 )
    {
      ShowGrippersCore(0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      return 0;
    }
    if ( a3 != 587 )
      goto LABEL_22;
    return 3;
  }
  switch ( a3 )
  {
    case 0x21u:
      return 3;
    case 1u:
      (*(void (__fastcall **)(CTouchSelectionHandle *))(*(_QWORD *)this + 8LL))(this);
      CTouchSelectionHandle::InitializeAnimation(this);
      return 0;
    case 2u:
      CTouchSelectionHandle::CleanUpAnimationController(this);
      return 0;
    case 0xFu:
      Rect = 0;
      if ( GetUpdateRect(hWnd, &Rect, 0) )
      {
        memset_0(v18, 0, 0x48u);
        v16 = 0;
        v15 = 0;
        v12 = (HDC)((__int64 (__fastcall *)(HWND, _BYTE *))g_pfnBeginPaint)(hWnd, v18);
        CTouchSelectionHandle::GetGripperColorsFromTextHost(this, &v16, &v15);
        CTouchSelectionHandle::RenderHandle(this, v12, v13, v16, v15);
        ((void (__fastcall *)(HWND, _BYTE *))g_pfnEndPaint)(hWnd, v18);
      }
      return 0;
    case 0x15u:
    case 0x1Au:
      CTouchSelectionHandle::CheckGripperBitmapColors(this);
      if ( *((_BYTE *)this + 100) )
      {
        WindowLongW = GetWindowLongW(hWnd, -20);
        SetWindowLongW(hWnd, -20, WindowLongW & 0xFFF7FFFF);
        SetWindowLongW(hWnd, -20, WindowLongW);
        CTouchSelectionHandle::UpdateLayeredWindow(this, 0, 0xFFu);
      }
      return 0;
  }
LABEL_22:
  if ( v9 )
    return !v9;
  else
    return DefWindowProcW(hWnd, a3, a4, lParam);
}

```

## disassembly

```asm
0x180203ddc  push    rbx
0x180203dde  push    rbp
0x180203ddf  push    rsi
0x180203de0  push    rdi
0x180203de1  sub     rsp, 0D8h
0x180203de8  mov     rax, cs:__security_cookie
0x180203def  xor     rax, rsp
0x180203df2  mov     [rsp+0F8h+var_38], rax
0x180203dfa  mov     ebx, r8d
0x180203dfd  mov     rsi, rdx
0x180203e00  mov     edx, ebx; unsigned int
0x180203e02  mov     r8, r9; unsigned __int64
0x180203e05  mov     rbp, r9
0x180203e08  mov     rdi, rcx
0x180203e0b  call    ?HandleTouchWindowMessage@CTouchTracker@@QEAA_NI_K_J@Z; CTouchTracker::HandleTouchWindowMessage(uint,unsigned __int64,__int64)
0x180203e10  movzx   ecx, al
0x180203e13  mov     rax, [rdi+78h]
0x180203e17  test    rax, rax
0x180203e1a  jz      short loc_180203E39
0x180203e1c  cmp     ebx, [rax+40h]
0x180203e1f  jnz     short loc_180203E39
0x180203e21  mov     r8b, [rdi+70h]; bool
0x180203e25  lea     rdx, [rdi+38h]; struct tagPOINT *
0x180203e29  mov     r9b, 1; bool
0x180203e2c  mov     rcx, rdi; this
0x180203e2f  call    ?Show@CTouchSelectionHandle@@IEAAXPEAUtagPOINT@@_N1@Z; CTouchSelectionHandle::Show(tagPOINT *,bool,bool)
0x180203e34  jmp     loc_180204026
0x180203e39  cmp     ebx, 21h ; '!'
0x180203e3c  ja      loc_180203FA5
0x180203e42  jz      loc_180203FEF
0x180203e48  mov     eax, ebx
0x180203e4a  sub     eax, 1
0x180203e4d  jz      loc_180203F89
0x180203e53  sub     eax, 1
0x180203e56  jz      loc_180203F7C
0x180203e5c  sub     eax, 0Dh
0x180203e5f  jz      short loc_180203EDB
0x180203e61  sub     eax, 6
0x180203e64  jz      short loc_180203E6F
0x180203e66  cmp     eax, 5
0x180203e69  jnz     loc_180203FC4
0x180203e6f  mov     rcx, rdi; this
0x180203e72  call    ?CheckGripperBitmapColors@CTouchSelectionHandle@@IEAAXXZ; CTouchSelectionHandle::CheckGripperBitmapColors(void)
0x180203e77  cmp     byte ptr [rdi+64h], 0
0x180203e7b  jz      loc_180204026
0x180203e81  mov     ebp, 0FFFFFFECh
0x180203e86  mov     rcx, rsi; hWnd
0x180203e89  mov     edx, ebp; nIndex
0x180203e8b  call    cs:__imp_GetWindowLongW
0x180203e92  nop     dword ptr [rax+rax+00h]
0x180203e97  mov     edx, ebp; nIndex
0x180203e99  mov     rcx, rsi; hWnd
0x180203e9c  mov     r8d, eax
0x180203e9f  mov     ebx, eax
0x180203ea1  btr     r8d, 13h; dwNewLong
0x180203ea6  call    cs:__imp_SetWindowLongW
0x180203ead  nop     dword ptr [rax+rax+00h]
0x180203eb2  mov     r8d, ebx; dwNewLong
0x180203eb5  mov     edx, ebp; nIndex
0x180203eb7  mov     rcx, rsi; hWnd
0x180203eba  call    cs:__imp_SetWindowLongW
0x180203ec1  nop     dword ptr [rax+rax+00h]
0x180203ec6  xor     edx, edx; pptDst
0x180203ec8  mov     r8d, 0FFh; int
0x180203ece  mov     rcx, rdi; this
0x180203ed1  call    ?UpdateLayeredWindow@CTouchSelectionHandle@@IEAAXPEAUtagPOINT@@H@Z; CTouchSelectionHandle::UpdateLayeredWindow(tagPOINT *,int)
0x180203ed6  jmp     loc_180204026
0x180203edb  xorps   xmm0, xmm0
0x180203ede  lea     rdx, [rsp+0F8h+Rect]; lpRect
0x180203ee3  xor     r8d, r8d; bErase
0x180203ee6  mov     rcx, rsi; hWnd
0x180203ee9  movups  xmmword ptr [rsp+0F8h+Rect.left], xmm0
0x180203eee  call    cs:__imp_GetUpdateRect
0x180203ef5  nop     dword ptr [rax+rax+00h]
0x180203efa  test    eax, eax
0x180203efc  jz      loc_180204026
0x180203f02  xor     edx, edx; Val
0x180203f04  lea     rcx, [rsp+0F8h+var_88]; void *
0x180203f09  lea     r8d, [rdx+48h]; Size
0x180203f0d  call    memset_0
0x180203f12  mov     rax, cs:?g_pfnBeginPaint@@3P6A_JXZEA; __int64 (*g_pfnBeginPaint)(void)
0x180203f19  lea     rdx, [rsp+0F8h+var_88]
0x180203f1e  mov     rcx, rsi
0x180203f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180203f26  lea     r8, [rsp+0F8h+var_A8]; unsigned int *
0x180203f2b  mov     [rsp+0F8h+var_A4], 0
0x180203f33  lea     rdx, [rsp+0F8h+var_A4]; unsigned int *
0x180203f38  mov     [rsp+0F8h+var_A8], 0
0x180203f40  mov     rcx, rdi; this
0x180203f43  mov     rbx, rax
0x180203f46  call    ?GetGripperColorsFromTextHost@CTouchSelectionHandle@@IEBAXAEAK0@Z; CTouchSelectionHandle::GetGripperColorsFromTextHost(ulong &,ulong &)
0x180203f4b  mov     ecx, [rsp+0F8h+var_A8]
0x180203f4f  mov     rdx, rbx; HDC
0x180203f52  mov     r9d, [rsp+0F8h+var_A4]; unsigned int
0x180203f57  mov     dword ptr [rsp+0F8h+var_D8], ecx; unsigned int
0x180203f5b  mov     rcx, rdi; this
0x180203f5e  call    ?RenderHandle@CTouchSelectionHandle@@IEBAXPEAUHDC__@@_NKK@Z; CTouchSelectionHandle::RenderHandle(HDC__ *,bool,ulong,ulong)
0x180203f63  mov     rax, cs:?g_pfnEndPaint@@3P6A_JXZEA; __int64 (*g_pfnEndPaint)(void)
0x180203f6a  lea     rdx, [rsp+0F8h+var_88]
0x180203f6f  mov     rcx, rsi
0x180203f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180203f77  jmp     loc_180204026
0x180203f7c  mov     rcx, rdi; this
0x180203f7f  call    ?CleanUpAnimationController@CTouchSelectionHandle@@IEAAXXZ; CTouchSelectionHandle::CleanUpAnimationController(void)
0x180203f84  jmp     loc_180204026
0x180203f89  mov     rax, [rdi]
0x180203f8c  mov     rcx, rdi
0x180203f8f  mov     rax, [rax+8]
0x180203f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180203f98  mov     rcx, rdi; this
0x180203f9b  call    ?InitializeAnimation@CTouchSelectionHandle@@IEAAJXZ; CTouchSelectionHandle::InitializeAnimation(void)
0x180203fa0  jmp     loc_180204026
0x180203fa5  mov     eax, ebx
0x180203fa7  sub     eax, 100h
0x180203fac  jz      short loc_180203FF6
0x180203fae  sub     eax, 101h
0x180203fb3  jz      short loc_180203FF6
0x180203fb5  sub     eax, 3
0x180203fb8  jz      short loc_180203FF6
0x180203fba  sub     eax, 3
0x180203fbd  jz      short loc_180203FF6
0x180203fbf  cmp     eax, 44h ; 'D'
0x180203fc2  jz      short loc_180203FEF
0x180203fc4  test    cl, cl
0x180203fc6  jnz     short loc_180203FE6
0x180203fc8  mov     r9, [rsp+0F8h+lParam]; lParam
0x180203fd0  mov     r8, rbp; wParam
0x180203fd3  mov     edx, ebx; Msg
0x180203fd5  mov     rcx, rsi; hWnd
0x180203fd8  call    cs:__imp_DefWindowProcW
0x180203fdf  nop     dword ptr [rax+rax+00h]
0x180203fe4  jmp     short loc_180204028
0x180203fe6  mov     rax, rcx
0x180203fe9  xor     rax, 1
0x180203fed  jmp     short loc_180204028
0x180203fef  mov     eax, 3
0x180203ff4  jmp     short loc_180204028
0x180203ff6  mov     [rsp+0F8h+var_B0], 0; unsigned int
0x180203ffe  xor     r9d, r9d; struct tagPOINT *
0x180204001  mov     [rsp+0F8h+var_B8], 0; bool
0x180204006  xor     r8d, r8d; struct tagPOINT *
0x180204009  mov     [rsp+0F8h+var_C0], 0; bool
0x18020400e  xor     edx, edx; HWND
0x180204010  mov     [rsp+0F8h+var_C8], 0; bool
0x180204015  xor     ecx, ecx; struct ITouchSelectionHandlesHost *
0x180204017  mov     [rsp+0F8h+var_D0], 0; bool
0x18020401c  mov     [rsp+0F8h+var_D8], 0; bool
0x180204021  call    ?ShowGrippersCore@@YAJPEAUITouchSelectionHandlesHost@@PEAUHWND__@@PEAUtagPOINT@@2_N3333I@Z; ShowGrippersCore(ITouchSelectionHandlesHost *,HWND__ *,tagPOINT *,tagPOINT *,bool,bool,bool,bool,bool,uint)
0x180204026  xor     eax, eax
0x180204028  mov     rcx, [rsp+0F8h+var_38]
0x180204030  xor     rcx, rsp; StackCookie
0x180204033  call    __security_check_cookie
0x180204038  add     rsp, 0D8h
0x18020403f  pop     rdi
0x180204040  pop     rsi
0x180204041  pop     rbp
0x180204042  pop     rbx
0x180204043  retn
```

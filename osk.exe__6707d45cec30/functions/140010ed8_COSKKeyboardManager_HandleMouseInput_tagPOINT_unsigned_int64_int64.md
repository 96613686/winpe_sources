# COSKKeyboardManager::HandleMouseInput(tagPOINT,unsigned __int64,__int64)

- ea: `0x140010ed8`
- end: `0x1400110c9`
- name: `?HandleMouseInput@COSKKeyboardManager@@AEAA_JUtagPOINT@@_K_J@Z`
- size: `497`
- prototype: `__int64(COSKKeyboardManager *__hidden this, struct tagPOINT, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400126e0`

## callees

- `0x140002de3`
- `0x140010968`
- `0x140010a40`
- `0x140010ed8`
- `0x1400135f0`
- `0x1400138fc`
- `0x140025d70`
- `0x140027010`

## import_xrefs

- `USER32!GetGUIThreadInfo` at `0x140010f97`
- `USER32!GetGUIThreadInfo` at `0x140011051`
- `USER32!GetGUIThreadInfo` at `0x140010f97`
- `USER32!GetGUIThreadInfo` at `0x140011051`
- `USER32!PostMessageW` at `0x140010fca`
- `USER32!PostMessageW` at `0x140010fca`
- `USER32!ShowWindow` at `0x14001102d`
- `USER32!ShowWindow` at `0x14001102d`
- `USER32!MapWindowPoints` at `0x140011092`
- `USER32!MapWindowPoints` at `0x140011092`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14001101f`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14001101f`

## pseudocode

```c
__int64 __fastcall COSKKeyboardManager::HandleMouseInput(
        COSKKeyboardManager *this,
        struct tagPOINT a2,
        __int64 a3,
        struct tagPOINT *a4)
{
  COSKKeyboardManager *v4; // rsi
  HWND OSKWndBeneathMousePoint; // rax
  HWND v9; // r12
  __int64 v10; // r14
  int v11; // eax
  HWND HWND; // rax
  bool v14; // [rsp+20h] [rbp-39h] BYREF
  struct tagPOINT Points; // [rsp+28h] [rbp-31h] BYREF
  struct tagGUITHREADINFO pgui; // [rsp+30h] [rbp-29h] BYREF

  v4 = COSKKeyboardManager::s_pCOSKKeyboardManager;
  Points = a2;
  v14 = 0;
  OSKWndBeneathMousePoint = COSKKeyboardManager::GetOSKWndBeneathMousePoint(this, a2, &v14);
  v9 = OSKWndBeneathMousePoint;
  if ( *((_BYTE *)v4 + 242) && OSKWndBeneathMousePoint && (a3 == 513 || a3 == 516) )
  {
    COSKKeyboardManager::SetFadeState(v4, 0);
    return 1;
  }
  v11 = *((_DWORD *)v4 + 41);
  v10 = 0;
  if ( v11 == 1 )
    return v10;
  if ( a3 == 513 )
  {
LABEL_11:
    if ( v14 )
    {
      v10 = 1;
      if ( a3 == 513 )
        PostMessageW(v9, 0x40Au, a2.x, Points.y);
    }
    return v10;
  }
  if ( a3 == 514 )
  {
    memset_0(&pgui, 0, sizeof(pgui));
    pgui.cbSize = 72;
    if ( !GetGUIThreadInfo(0, &pgui) || pgui.hwndCapture )
      return v10;
    goto LABEL_11;
  }
  if ( a3 == 512 && v11 == 2 )
  {
    if ( COSKKeyboardManager::ShouldRestoreMinimizedOSK(v4, a2) )
    {
      HWND = DirectUI::NativeHWNDHost::GetHWND(*((DirectUI::NativeHWNDHost **)v4 + 16));
      ShowWindow(HWND, 9);
    }
    else
    {
      memset_0(&pgui, 0, sizeof(pgui));
      pgui.cbSize = 72;
      if ( GetGUIThreadInfo(0, &pgui) )
      {
        if ( pgui.hwndCapture )
        {
          if ( v9 )
          {
            if ( a4 )
            {
              Points = *a4;
              MapWindowPoints(0, v9, &Points, 1u);
              if ( COSKKeyboardManager::GetSKBBeneathPoint(v4, &Points) )
                (*(void (__fastcall **)(_QWORD, struct tagPOINT *))(**((_QWORD **)v4 + 3) + 280LL))(
                  *((_QWORD *)v4 + 3),
                  &Points);
            }
          }
        }
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x140010ed8  mov     [rsp-8+arg_0], rbx
0x140010edd  mov     [rsp-8+arg_10], rsi
0x140010ee2  push    rbp
0x140010ee3  push    rdi
0x140010ee4  push    r12
0x140010ee6  push    r13
0x140010ee8  push    r14
0x140010eea  lea     rbp, [rsp-37h]
0x140010eef  sub     rsp, 90h
0x140010ef6  mov     rax, cs:__security_cookie
0x140010efd  xor     rax, rsp
0x140010f00  mov     [rbp+57h+var_30], rax
0x140010f04  mov     rsi, cs:?s_pCOSKKeyboardManager@COSKKeyboardManager@@0PEAV1@EA; COSKKeyboardManager * COSKKeyboardManager::s_pCOSKKeyboardManager
0x140010f0b  mov     rdi, r8
0x140010f0e  lea     r8, [rbp+57h+var_90]; bool *
0x140010f12  mov     qword ptr [rbp+57h+Points.x], rdx
0x140010f16  mov     r13, r9
0x140010f19  mov     [rbp+57h+var_90], 0
0x140010f1d  mov     rbx, rdx
0x140010f20  call    ?GetOSKWndBeneathMousePoint@COSKKeyboardManager@@AEAAPEAUHWND__@@UtagPOINT@@PEA_N@Z; COSKKeyboardManager::GetOSKWndBeneathMousePoint(tagPOINT,bool *)
0x140010f25  cmp     byte ptr [rsi+0F2h], 0
0x140010f2c  mov     r12, rax
0x140010f2f  mov     ecx, 201h
0x140010f34  jz      short loc_140010F5B
0x140010f36  test    rax, rax
0x140010f39  jz      short loc_140010F5B
0x140010f3b  cmp     rdi, rcx
0x140010f3e  jz      short loc_140010F49
0x140010f40  cmp     rdi, 204h
0x140010f47  jnz     short loc_140010F5B
0x140010f49  xor     edx, edx; bool
0x140010f4b  mov     rcx, rsi; this
0x140010f4e  call    ?SetFadeState@COSKKeyboardManager@@AEAAX_N@Z; COSKKeyboardManager::SetFadeState(bool)
0x140010f53  mov     r14d, 1
0x140010f59  jmp     short loc_140010FD0
0x140010f5b  mov     eax, [rsi+0A4h]
0x140010f61  xor     r14d, r14d
0x140010f64  cmp     eax, 1
0x140010f67  jz      short loc_140010FD0
0x140010f69  cmp     rdi, rcx
0x140010f6c  jz      short loc_140010FAA
0x140010f6e  cmp     rdi, 202h
0x140010f75  jnz     loc_140010FFB
0x140010f7b  xor     edx, edx; Val
0x140010f7d  lea     r8d, [r14+48h]; Size
0x140010f81  lea     rcx, [rbp+57h+pgui]; void *
0x140010f85  call    memset_0
0x140010f8a  lea     rdx, [rbp+57h+pgui]; pgui
0x140010f8e  mov     [rbp+57h+pgui.cbSize], 48h ; 'H'
0x140010f95  xor     ecx, ecx; idThread
0x140010f97  call    cs:__imp_GetGUIThreadInfo
0x140010f9d  test    eax, eax
0x140010f9f  jz      short loc_140010FD0
0x140010fa1  cmp     [rbp+57h+pgui.hwndCapture], r14
0x140010fa5  jnz     short loc_140010FD0
0x140010fa7  lea     ecx, [rdi-1]
0x140010faa  cmp     [rbp+57h+var_90], r14b
0x140010fae  jz      short loc_140010FD0
0x140010fb0  mov     r14d, 1
0x140010fb6  cmp     rdi, rcx
0x140010fb9  jnz     short loc_140010FD0
0x140010fbb  movsxd  r9, [rbp+57h+Points.y]; lParam
0x140010fbf  mov     edx, 40Ah; Msg
0x140010fc4  movsxd  r8, ebx; wParam
0x140010fc7  mov     rcx, r12; hWnd
0x140010fca  call    cs:__imp_PostMessageW
0x140010fd0  mov     rax, r14
0x140010fd3  mov     rcx, [rbp+57h+var_30]
0x140010fd7  xor     rcx, rsp; StackCookie
0x140010fda  call    __security_check_cookie
0x140010fdf  lea     r11, [rsp+0B0h+var_20]
0x140010fe7  mov     rbx, [r11+30h]
0x140010feb  mov     rsi, [r11+40h]
0x140010fef  mov     rsp, r11
0x140010ff2  pop     r14
0x140010ff4  pop     r13
0x140010ff6  pop     r12
0x140010ff8  pop     rdi
0x140010ff9  pop     rbp
0x140010ffa  retn
0x140010ffb  cmp     rdi, 200h
0x140011002  jnz     short loc_140010FD0
0x140011004  cmp     eax, 2
0x140011007  jnz     short loc_140010FD0
0x140011009  mov     rdx, rbx; struct tagPOINT
0x14001100c  mov     rcx, rsi; this
0x14001100f  call    ?ShouldRestoreMinimizedOSK@COSKKeyboardManager@@AEAA_NUtagPOINT@@@Z; COSKKeyboardManager::ShouldRestoreMinimizedOSK(tagPOINT)
0x140011014  test    al, al
0x140011016  jz      short loc_140011035
0x140011018  mov     rcx, [rsi+80h]
0x14001101f  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x140011025  mov     rcx, rax; hWnd
0x140011028  mov     edx, 9; nCmdShow
0x14001102d  call    cs:__imp_ShowWindow
0x140011033  jmp     short loc_140010FD0
0x140011035  xor     edx, edx; Val
0x140011037  lea     rcx, [rbp+57h+pgui]; void *
0x14001103b  lea     r8d, [rdx+48h]; Size
0x14001103f  call    memset_0
0x140011044  lea     rdx, [rbp+57h+pgui]; pgui
0x140011048  mov     [rbp+57h+pgui.cbSize], 48h ; 'H'
0x14001104f  xor     ecx, ecx; idThread
0x140011051  call    cs:__imp_GetGUIThreadInfo
0x140011057  test    eax, eax
0x140011059  jz      loc_140010FD0
0x14001105f  cmp     [rbp+57h+pgui.hwndCapture], r14
0x140011063  jz      loc_140010FD0
0x140011069  test    r12, r12
0x14001106c  jz      loc_140010FD0
0x140011072  test    r13, r13
0x140011075  jz      loc_140010FD0
0x14001107b  mov     rax, [r13+0]
0x14001107f  lea     r8, [rbp+57h+Points]; lpPoints
0x140011083  mov     r9d, 1; cPoints
0x140011089  mov     qword ptr [rbp+57h+Points.x], rax
0x14001108d  mov     rdx, r12; hWndTo
0x140011090  xor     ecx, ecx; hWndFrom
0x140011092  call    cs:__imp_MapWindowPoints
0x140011098  lea     rdx, [rbp+57h+Points]; struct tagPOINT *
0x14001109c  mov     rcx, rsi; this
0x14001109f  call    ?GetSKBBeneathPoint@COSKKeyboardManager@@AEAAPEAUIAccSoftKeyboardUI@@PEAUtagPOINT@@@Z; COSKKeyboardManager::GetSKBBeneathPoint(tagPOINT *)
0x1400110a4  test    rax, rax
0x1400110a7  jz      loc_140010FD0
0x1400110ad  mov     rcx, [rsi+18h]
0x1400110b1  lea     rdx, [rbp+57h+Points]
0x1400110b5  mov     rax, [rcx]
0x1400110b8  mov     rax, [rax+118h]
0x1400110bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400110c4  jmp     loc_140010FD0
```

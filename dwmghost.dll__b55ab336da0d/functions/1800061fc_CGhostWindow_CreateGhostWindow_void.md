# CGhostWindow::CreateGhostWindow(void)

- ea: `0x1800061fc`
- end: `0x18000648b`
- name: `?CreateGhostWindow@CGhostWindow@@QEAAHXZ`
- size: `655`
- prototype: `__int64 __fastcall(HWND *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800083e8`
- `0x1800086b8`

## callees

- `0x180001190`
- `0x1800061fc`
- `0x180006494`
- `0x1800067a8`
- `0x180006bac`
- `0x1800075d0`
- `0x18000c010`

## import_xrefs

- `USER32!CreateWindowInBand` at `0x18000637c`
- `USER32!CreateWindowInBand` at `0x18000637c`
- `USER32!SetWindowLongPtrW` at `0x1800063f1`
- `USER32!SetWindowLongPtrW` at `0x1800063f1`
- `USER32!GetWindowLongPtrW` at `0x1800062df`
- `USER32!GetWindowLongPtrW` at `0x1800063d5`
- `USER32!GetWindowLongPtrW` at `0x1800062df`
- `USER32!GetWindowLongPtrW` at `0x1800063d5`
- `USER32!GetWindowBand` at `0x180006303`
- `USER32!GetWindowBand` at `0x180006303`
- `USER32!InternalGetWindowText` at `0x18000628b`
- `USER32!InternalGetWindowText` at `0x18000628b`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x1800063b5`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x1800063b5`
- `ext-ms-win-ntuser-window-l1-1-4!GhostWindowFromHungWindow` at `0x1800062ed`
- `ext-ms-win-ntuser-window-l1-1-4!GhostWindowFromHungWindow` at `0x1800062ed`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowInfo` at `0x180006241`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowInfo` at `0x180006241`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180006398`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180006398`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18000641b`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18000641b`
- `ext-ms-win-ntuser-window-l1-1-3!GetTitleBarInfo` at `0x1800062ab`
- `ext-ms-win-ntuser-window-l1-1-3!GetTitleBarInfo` at `0x1800062ab`
- `ext-ms-win-ntuser-window-l1-1-3!IsHungAppWindow` at `0x18000630d`
- `ext-ms-win-ntuser-window-l1-1-3!IsHungAppWindow` at `0x18000630d`

## pseudocode

```c
__int64 __fastcall CGhostWindow::CreateGhostWindow(HWND *this)
{
  __int64 v2; // rcx
  HWND v3; // rcx
  int v4; // r12d
  int v5; // r15d
  int v6; // r14d
  HWND v7; // rcx
  int v8; // r13d
  unsigned int v9; // edi
  LONG_PTR WindowLongPtrW; // rax
  __int64 v11; // rsi
  HWND v12; // rax
  DWORD WindowThreadProcessId; // eax
  UINT v14; // edx
  int v15; // eax
  __int64 v16; // rcx
  int v18; // [rsp+70h] [rbp-90h] BYREF
  int v19; // [rsp+74h] [rbp-8Ch]
  int v20; // [rsp+78h] [rbp-88h]
  int v21; // [rsp+7Ch] [rbp-84h]
  tagTITLEBARINFO pti; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pString[256]; // [rsp+B0h] [rbp-50h] BYREF

  if ( (unsigned int)CGhostWindow::GetState(this) || !GetWindowInfo(*(HWND *)(v2 + 40), (PWINDOWINFO)(v2 + 72)) )
    goto LABEL_23;
  v3 = this[5];
  v4 = *((_DWORD *)this + 21);
  v5 = *((_DWORD *)this + 22);
  v18 = 0;
  v6 = 0;
  v20 = *((_DWORD *)this + 19);
  v19 = *((_DWORD *)this + 20);
  memset(&pti, 0, sizeof(pti));
  InternalGetWindowText(v3, pString, 256);
  v7 = this[5];
  v8 = *((_DWORD *)this + 27);
  v21 = *((_DWORD *)this + 28);
  pti.cbSize = 44;
  v9 = 1;
  if ( GetTitleBarInfo(v7, &pti) )
  {
    if ( (pti.rgstate[0] & 0x18000) != 0 )
    {
      v6 = 1;
    }
    else if ( (pti.rgstate[5] & 0x8001) == 0 )
    {
      *((_DWORD *)this + 50) = 1;
    }
  }
  WindowLongPtrW = GetWindowLongPtrW(this[5], -8);
  v11 = WindowLongPtrW ? GhostWindowFromHungWindow(WindowLongPtrW) : 0LL;
  GetWindowBand(this[5], &v18);
  v12 = IsHungAppWindow(this[5])
      ? (HWND)CreateWindowInBand(
                v21 & 0x87777FF,
                L"Ghost",
                pString,
                v8 & 0x86CF0000,
                v20,
                v19,
                v4 - v20,
                v5 - v19,
                v11,
                0,
                0,
                this,
                v18)
      : 0LL;
  this[6] = v12;
  if ( !v12 )
    goto LABEL_23;
  WindowThreadProcessId = GetWindowThreadProcessId(v12, 0);
  v14 = CGhostMgr::s_uHangRepMsg;
  *((_DWORD *)this + 14) = WindowThreadProcessId;
  if ( v14 )
    ChangeWindowMessageFilterEx(this[6], v14, 1u, 0);
  CGhostWindow::SetState(this, 1);
  if ( v6 )
  {
    v15 = GetWindowLongPtrW(this[6], -16);
    if ( (v15 & 0xC00000) != 0 )
    {
      SetWindowLongPtrW(this[6], -16, v15 & 0xFF3FFFFF);
      SetWindowPos(this[6], 0, 0, 0, 0, 0, 0x237u);
    }
  }
  CGhostWindow::GetHungWindowStuff((CGhostWindow *)this);
  if ( (*((unsigned int (__fastcall **)(HWND *, HWND, HWND))*this + 1))(this, this[6], this[5])
    && (unsigned int)CGhostWindow::GetState(this) == 1 )
  {
    CGhostWindow::SetState(v16, 2);
  }
  else
  {
LABEL_23:
    v9 = 0;
    CGhostWindow::DestroyGhostWindow((CGhostWindow *)this);
  }
  return v9;
}

```

## disassembly

```asm
0x1800061fc  push    rbp
0x1800061fe  push    rbx
0x1800061ff  push    rsi
0x180006200  push    rdi
0x180006201  push    r12
0x180006203  push    r13
0x180006205  push    r14
0x180006207  push    r15
0x180006209  lea     rbp, [rsp-1C8h]
0x180006211  sub     rsp, 2C8h
0x180006218  mov     rax, cs:__security_cookie
0x18000621f  xor     rax, rsp
0x180006222  mov     [rbp+200h+var_50], rax
0x180006229  mov     rbx, rcx
0x18000622c  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180006231  test    eax, eax
0x180006233  jnz     loc_18000645C
0x180006239  lea     rdx, [rcx+48h]; pwi
0x18000623d  mov     rcx, [rcx+28h]; hwnd
0x180006241  call    cs:__imp_GetWindowInfo
0x180006247  test    eax, eax
0x180006249  jz      loc_18000645C
0x18000624f  mov     rcx, [rbx+28h]; hWnd
0x180006253  lea     rdx, [rbp+200h+pString]; pString
0x180006257  mov     r12d, [rbx+54h]
0x18000625b  xor     eax, eax
0x18000625d  mov     r15d, [rbx+58h]
0x180006261  xorps   xmm0, xmm0
0x180006264  mov     [rsp+300h+var_290], eax
0x180006268  mov     r8d, 100h; cchMaxCount
0x18000626e  mov     eax, [rbx+4Ch]
0x180006271  xor     r14d, r14d
0x180006274  mov     [rsp+300h+var_288], eax
0x180006278  mov     eax, [rbx+50h]
0x18000627b  movups  xmmword ptr [rbp+200h+pti.rcTitleBar.bottom], xmm0
0x18000627f  mov     [rsp+300h+var_28C], eax
0x180006283  movups  xmmword ptr [rbp+200h+pti.cbSize], xmm0
0x180006287  movups  xmmword ptr [rbp+200h+pti.rgstate+8], xmm0
0x18000628b  call    cs:__imp_InternalGetWindowText
0x180006291  mov     eax, [rbx+70h]
0x180006294  lea     rdx, [rbp+200h+pti]; pti
0x180006298  mov     rcx, [rbx+28h]; hwnd
0x18000629c  mov     r13d, [rbx+6Ch]
0x1800062a0  mov     [rsp+300h+var_284], eax
0x1800062a4  mov     [rbp+200h+pti.cbSize], 2Ch ; ','
0x1800062ab  call    cs:__imp_GetTitleBarInfo
0x1800062b1  lea     edi, [r14+1]
0x1800062b5  test    eax, eax
0x1800062b7  jz      short loc_1800062D6
0x1800062b9  test    [rbp+200h+pti.rgstate], 18000h
0x1800062c0  jz      short loc_1800062C7
0x1800062c2  mov     r14d, edi
0x1800062c5  jmp     short loc_1800062D6
0x1800062c7  test    [rbp+200h+pti.rgstate+14h], 8001h
0x1800062ce  jnz     short loc_1800062D6
0x1800062d0  mov     [rbx+0C8h], edi
0x1800062d6  mov     rcx, [rbx+28h]; hWnd
0x1800062da  mov     edx, 0FFFFFFF8h; nIndex
0x1800062df  call    cs:__imp_GetWindowLongPtrW
0x1800062e5  test    rax, rax
0x1800062e8  jz      short loc_1800062F8
0x1800062ea  mov     rcx, rax
0x1800062ed  call    cs:__imp_GhostWindowFromHungWindow
0x1800062f3  mov     rsi, rax
0x1800062f6  jmp     short loc_1800062FA
0x1800062f8  xor     esi, esi
0x1800062fa  mov     rcx, [rbx+28h]
0x1800062fe  lea     rdx, [rsp+300h+var_290]
0x180006303  call    cs:__imp_GetWindowBand
0x180006309  mov     rcx, [rbx+28h]; hwnd
0x18000630d  call    cs:__imp_IsHungAppWindow
0x180006313  test    eax, eax
0x180006315  jz      short loc_180006384
0x180006317  mov     r8d, [rsp+300h+var_28C]
0x18000631c  and     r13d, 86CF0000h
0x180006323  mov     edx, [rsp+300h+var_288]
0x180006327  sub     r15d, r8d
0x18000632a  mov     eax, [rsp+300h+var_290]
0x18000632e  sub     r12d, edx
0x180006331  mov     ecx, [rsp+300h+var_284]
0x180006335  mov     r9d, r13d
0x180006338  mov     [rsp+300h+var_2A0], eax
0x18000633c  and     ecx, 87777FFh
0x180006342  mov     [rsp+300h+var_2A8], rbx
0x180006347  mov     [rsp+300h+var_2B0], 0
0x180006350  mov     [rsp+300h+var_2B8], 0
0x180006359  mov     [rsp+300h+var_2C0], rsi
0x18000635e  mov     [rsp+300h+var_2C8], r15d
0x180006363  mov     [rsp+300h+uFlags], r12d
0x180006368  mov     [rsp+300h+cy], r8d
0x18000636d  lea     r8, [rbp+200h+pString]
0x180006371  mov     [rsp+300h+var_2E0], edx
0x180006375  lea     rdx, ClassName; "Ghost"
0x18000637c  call    cs:__imp_CreateWindowInBand
0x180006382  jmp     short loc_180006386
0x180006384  xor     eax, eax
0x180006386  mov     [rbx+30h], rax
0x18000638a  test    rax, rax
0x18000638d  jz      loc_18000645C
0x180006393  xor     edx, edx; lpdwProcessId
0x180006395  mov     rcx, rax; hWnd
0x180006398  call    cs:__imp_GetWindowThreadProcessId
0x18000639e  mov     edx, cs:?s_uHangRepMsg@CGhostMgr@@2IA; message
0x1800063a4  mov     [rbx+38h], eax
0x1800063a7  test    edx, edx
0x1800063a9  jz      short loc_1800063BB
0x1800063ab  mov     rcx, [rbx+30h]; hwnd
0x1800063af  xor     r9d, r9d; pChangeFilterStruct
0x1800063b2  mov     r8d, edi; action
0x1800063b5  call    cs:__imp_ChangeWindowMessageFilterEx
0x1800063bb  mov     edx, edi
0x1800063bd  mov     rcx, rbx
0x1800063c0  call    ?SetState@CGhostWindow@@AEAA?AW4GHOSTSTATE@@W42@@Z; CGhostWindow::SetState(GHOSTSTATE)
0x1800063c5  test    r14d, r14d
0x1800063c8  jz      short loc_180006421
0x1800063ca  mov     rcx, [rbx+30h]; hWnd
0x1800063ce  mov     esi, 0FFFFFFF0h
0x1800063d3  mov     edx, esi; nIndex
0x1800063d5  call    cs:__imp_GetWindowLongPtrW
0x1800063db  test    eax, 0C00000h
0x1800063e0  jz      short loc_180006421
0x1800063e2  mov     rcx, [rbx+30h]; hWnd
0x1800063e6  mov     r8d, 0FF3FFFFFh
0x1800063ec  and     r8, rax; dwNewLong
0x1800063ef  mov     edx, esi; nIndex
0x1800063f1  call    cs:__imp_SetWindowLongPtrW
0x1800063f7  mov     rcx, [rbx+30h]; hWnd
0x1800063fb  xor     r9d, r9d; Y
0x1800063fe  mov     [rsp+300h+uFlags], 237h; uFlags
0x180006406  xor     r8d, r8d; X
0x180006409  mov     [rsp+300h+cy], 0; cy
0x180006411  xor     edx, edx; hWndInsertAfter
0x180006413  mov     [rsp+300h+var_2E0], 0; cx
0x18000641b  call    cs:__imp_SetWindowPos
0x180006421  mov     rcx, rbx; this
0x180006424  call    ?GetHungWindowStuff@CGhostWindow@@AEAAHXZ; CGhostWindow::GetHungWindowStuff(void)
0x180006429  mov     rax, [rbx]
0x18000642c  mov     rcx, rbx
0x18000642f  mov     r8, [rbx+28h]
0x180006433  mov     rdx, [rbx+30h]
0x180006437  mov     rax, [rax+8]
0x18000643b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006440  test    eax, eax
0x180006442  jz      short loc_18000645C
0x180006444  mov     rcx, rbx
0x180006447  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x18000644c  cmp     eax, edi
0x18000644e  jnz     short loc_18000645C
0x180006450  mov     edx, 2
0x180006455  call    ?SetState@CGhostWindow@@AEAA?AW4GHOSTSTATE@@W42@@Z; CGhostWindow::SetState(GHOSTSTATE)
0x18000645a  jmp     short loc_180006466
0x18000645c  xor     edi, edi
0x18000645e  mov     rcx, rbx; this
0x180006461  call    ?DestroyGhostWindow@CGhostWindow@@QEAAHXZ; CGhostWindow::DestroyGhostWindow(void)
0x180006466  mov     eax, edi
0x180006468  mov     rcx, [rbp+200h+var_50]
0x18000646f  xor     rcx, rsp; StackCookie
0x180006472  call    __security_check_cookie
0x180006477  add     rsp, 2C8h
0x18000647e  pop     r15
0x180006480  pop     r14
0x180006482  pop     r13
0x180006484  pop     r12
0x180006486  pop     rdi
0x180006487  pop     rsi
0x180006488  pop     rbx
0x180006489  pop     rbp
0x18000648a  retn
```

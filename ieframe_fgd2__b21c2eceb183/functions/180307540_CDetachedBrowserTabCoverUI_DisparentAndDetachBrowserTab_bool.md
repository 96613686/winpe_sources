# CDetachedBrowserTabCoverUI::DisparentAndDetachBrowserTab(bool)

- ea: `0x180307540`
- end: `0x1803078cd`
- name: `?DisparentAndDetachBrowserTab@CDetachedBrowserTabCoverUI@@QEAA_N_N@Z`
- size: `909`
- prototype: `bool __fastcall(CDetachedBrowserTabCoverUI *__hidden this, bool)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180257420`
- `0x180307404`
- `0x180307a08`

## callees

- `0x1800c2ed8`
- `0x180263b78`
- `0x180307540`
- `0x180307c90`
- `0x180308438`
- `0x180308c04`
- `0x180309528`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18030772d`
- `KERNEL32!CreateThread` at `0x18030772d`
- `KERNEL32!CloseHandle` at `0x18030774a`
- `KERNEL32!CloseHandle` at `0x18030774a`
- `KERNEL32!GetLastError` at `0x1803076a8`
- `KERNEL32!GetLastError` at `0x18030782f`
- `KERNEL32!GetLastError` at `0x1803076a8`
- `KERNEL32!GetLastError` at `0x18030782f`
- `KERNEL32!GetCurrentThreadId` at `0x1803075ae`
- `KERNEL32!GetCurrentThreadId` at `0x1803075ae`
- `KERNEL32!WaitForSingleObject` at `0x180307741`
- `KERNEL32!WaitForSingleObject` at `0x180307741`
- `USER32!GetFocus` at `0x1803075c9`
- `USER32!GetFocus` at `0x1803075c9`
- `USER32!SetFocus` at `0x180307693`
- `USER32!SetFocus` at `0x180307693`
- `USER32!SetWindowPos` at `0x1803077bf`
- `USER32!SetWindowPos` at `0x1803077bf`
- `USER32!InvalidateRect` at `0x1803077d9`
- `USER32!InvalidateRect` at `0x1803077d9`
- `USER32!SetForegroundWindow` at `0x18030787f`
- `USER32!SetForegroundWindow` at `0x18030787f`
- `USER32!AttachThreadInput` at `0x1803076e2`
- `USER32!AttachThreadInput` at `0x1803076e2`
- `USER32!GetForegroundWindow` at `0x1803075c0`
- `USER32!GetForegroundWindow` at `0x18030786a`
- `USER32!GetForegroundWindow` at `0x1803075c0`
- `USER32!GetForegroundWindow` at `0x18030786a`
- `USER32!PostThreadMessageW` at `0x180307610`
- `USER32!PostThreadMessageW` at `0x180307610`
- `USER32!SetActiveWindow` at `0x180307656`
- `USER32!SetActiveWindow` at `0x180307656`
- `USER32!UpdateWindow` at `0x1803077e9`
- `USER32!UpdateWindow` at `0x1803077f9`
- `USER32!UpdateWindow` at `0x1803077e9`
- `USER32!UpdateWindow` at `0x1803077f9`
- `USER32!GetParent` at `0x1803075e8`
- `USER32!GetParent` at `0x1803075e8`
- `USER32!SendMessageW` at `0x180307668`
- `USER32!SendMessageW` at `0x180307684`
- `USER32!SendMessageW` at `0x180307668`
- `USER32!SendMessageW` at `0x180307684`
- `USER32!SetParent` at `0x18030778b`
- `USER32!SetParent` at `0x18030778b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180307704`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180307704`

## pseudocode

```c
bool __fastcall CDetachedBrowserTabCoverUI::DisparentAndDetachBrowserTab(
        CDetachedBrowserTabCoverUI *this,
        unsigned __int8 a2)
{
  char *v3; // rsi
  int v5; // r12d
  int v6; // edi
  DWORD CurrentThreadId; // r14d
  HWND ForegroundWindow; // r15
  HWND Focus; // rax
  __int64 v10; // rcx
  char v11; // bp
  HWND v12; // rcx
  signed int LastError; // eax
  int i; // eax
  __int64 v15; // rcx
  HANDLE Thread; // rax
  void *v17; // rdi
  __int64 v18; // rax
  HWND v19; // rcx
  signed int v20; // eax

  v3 = (char *)this + 8;
  v5 = a2;
  if ( (Microsoft_IEFRAMEEnableBits & 0x800) != 0 )
    McTemplateU0qtq_EventWriteTransfer(
      (_DWORD)this,
      (unsigned int)BROWSEUI_HANGUI_DISPARENTANDDETACHBROWSERTAB_START,
      a2,
      *(_DWORD *)(*(_QWORD *)v3 + 240LL),
      0);
  if ( a2 )
  {
    if ( *((_BYTE *)this + 70) )
    {
      v6 = 1;
      goto LABEL_48;
    }
  }
  else
  {
    v6 = 1;
    if ( !*((_BYTE *)this + 70) )
      goto LABEL_48;
  }
  CurrentThreadId = GetCurrentThreadId();
  if ( a2 )
  {
    ForegroundWindow = GetForegroundWindow();
    Focus = GetFocus();
    *((_QWORD *)this + 3) = Focus;
    while ( 1 )
    {
      v10 = *((_QWORD *)this + 1);
      if ( !Focus )
        break;
      if ( Focus == *(HWND *)(v10 + 352) )
      {
        v11 = 1;
        goto LABEL_14;
      }
      Focus = GetParent(Focus);
    }
    v11 = 0;
LABEL_14:
    if ( *((_BYTE *)this + 77) )
      PostThreadMessageW(*(_DWORD *)(v10 + 248), 0x842Au, 1u, 0);
    v6 = CDetachedBrowserTabCoverUI::_AttachThreadInputHelper(
           this,
           *(_DWORD *)(*((_QWORD *)this + 1) + 248LL),
           CurrentThreadId,
           0);
    if ( v6 >= 0 )
    {
      if ( CDetachedBrowserTabCoverUI::_HideAndDisparentFrameTab(this, 0) )
      {
        v12 = *(HWND *)(*((_QWORD *)this + 1) + 344LL);
        if ( ForegroundWindow == v12 )
        {
          SetActiveWindow(v12);
        }
        else
        {
          SendMessageW(v12, 6u, 0, 0);
          SendMessageW(*(HWND *)(*((_QWORD *)this + 1) + 344LL), 0x86u, 0, 0);
        }
        if ( v11 )
          SetFocus(*((HWND *)this + 2));
        else
          *((_QWORD *)this + 3) = 0;
        *((_BYTE *)this + 70) = 1;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        for ( i = *((_DWORD *)this + 32); i; i = *((_DWORD *)this + 32) )
        {
          v15 = *((_QWORD *)this + 1);
          *((_DWORD *)this + 32) = i - 1;
          AttachThreadInput(*(_DWORD *)(v15 + 248), CurrentThreadId, 1);
        }
        *((_DWORD *)this + 32) = -1;
      }
    }
  }
  else
  {
    if ( IsDualEngineProcess() )
    {
      Thread = CreateThread(0, 0, s_FocusStomperThreadProc, (LPVOID)*(unsigned int *)(*(_QWORD *)v3 + 248LL), 0, 0);
      v17 = Thread;
      if ( Thread )
      {
        WaitForSingleObject(Thread, 0xFFFFFFFF);
        CloseHandle(v17);
      }
    }
    v18 = *(_QWORD *)v3;
    if ( *((_BYTE *)this + 77) )
    {
      v6 = CDetachedBrowserTabCoverUI::_AttachThreadInputHelper(this, *(_DWORD *)(v18 + 248), CurrentThreadId, 1u);
      if ( v6 >= 0 )
        *((_BYTE *)this + 70) = 0;
      if ( *((_BYTE *)this + 80) )
      {
        if ( !GetForegroundWindow() )
          SetForegroundWindow(*(HWND *)(*(_QWORD *)v3 + 344LL));
        *((_BYTE *)this + 80) = 0;
      }
    }
    else
    {
      SHSetWindowBits(*(HWND *)(v18 + 352), -16);
      if ( SetParent(*(HWND *)(*(_QWORD *)v3 + 352LL), *(HWND *)(*(_QWORD *)v3 + 344LL)) )
      {
        SetWindowPos(*(HWND *)(*(_QWORD *)v3 + 352LL), (HWND)1, 0, 0, 0, 0, 0x13u);
        v19 = *(HWND *)(*(_QWORD *)v3 + 376LL);
        if ( v19 )
        {
          InvalidateRect(v19, 0, 0);
          UpdateWindow(*(HWND *)(*(_QWORD *)v3 + 376LL));
        }
        UpdateWindow(*(HWND *)(*(_QWORD *)v3 + 368LL));
        v6 = CDetachedBrowserTabCoverUI::_AttachThreadInputHelper(
               this,
               *(_DWORD *)(*(_QWORD *)v3 + 248LL),
               CurrentThreadId,
               1u);
        if ( v6 >= 0 )
        {
          *((_BYTE *)this + 70) = 0;
          v6 = CDetachedBrowserTabCoverUI::ReparentDevTools(this, 1);
        }
      }
      else
      {
        v20 = GetLastError();
        v6 = v20;
        if ( v20 > 0 )
          v6 = (unsigned __int16)v20 | 0x80070000;
      }
    }
  }
  CDetachedBrowserTabCoverUI::_UpdateHangProtectionState(this);
LABEL_48:
  if ( (Microsoft_IEFRAMEEnableBits & 0x800) != 0 )
    McTemplateU0qtq_EventWriteTransfer(
      (_DWORD)this,
      (unsigned int)BROWSEUI_HANGUI_DISPARENTANDDETACHBROWSERTAB_STOP,
      v5,
      *(_DWORD *)(*(_QWORD *)v3 + 240LL),
      v6);
  return v6 == 0;
}

```

## disassembly

```asm
0x180307540  push    rbx
0x180307542  push    rbp
0x180307543  push    rsi
0x180307544  push    rdi
0x180307545  push    r12
0x180307547  push    r13
0x180307549  push    r14
0x18030754b  push    r15
0x18030754d  sub     rsp, 48h
0x180307551  xor     r13d, r13d
0x180307554  movzx   ebp, dl
0x180307557  test    byte ptr cs:Microsoft_IEFRAMEEnableBits+1, 8
0x18030755e  lea     rsi, [rcx+8]
0x180307562  mov     rbx, rcx
0x180307565  mov     r12d, ebp
0x180307568  jz      short loc_180307588
0x18030756a  mov     r9, [rsi]
0x18030756d  lea     rdx, BROWSEUI_HANGUI_DISPARENTANDDETACHBROWSERTAB_START
0x180307574  mov     r8d, ebp
0x180307577  mov     [rsp+88h+dwCreationFlags], r13d
0x18030757c  mov     r9d, [r9+0F0h]
0x180307583  call    McTemplateU0qtq_EventWriteTransfer
0x180307588  mov     r15d, 1
0x18030758e  test    bpl, bpl
0x180307591  jz      short loc_1803075A1
0x180307593  cmp     [rbx+46h], r13b
0x180307597  jz      short loc_1803075AE
0x180307599  mov     edi, r15d
0x18030759c  jmp     loc_180307891
0x1803075a1  mov     edi, r15d
0x1803075a4  cmp     [rbx+46h], r13b
0x1803075a8  jz      loc_180307891
0x1803075ae  call    cs:__imp_GetCurrentThreadId
0x1803075b4  mov     r14d, eax
0x1803075b7  test    bpl, bpl
0x1803075ba  jz      loc_180307704
0x1803075c0  call    cs:__imp_GetForegroundWindow
0x1803075c6  mov     r15, rax
0x1803075c9  call    cs:__imp_GetFocus
0x1803075cf  mov     [rbx+18h], rax
0x1803075d3  mov     rcx, [rbx+8]
0x1803075d7  test    rax, rax
0x1803075da  jz      short loc_1803075F5
0x1803075dc  cmp     rax, [rcx+160h]
0x1803075e3  jz      short loc_1803075F0
0x1803075e5  mov     rcx, rax; hWnd
0x1803075e8  call    cs:__imp_GetParent
0x1803075ee  jmp     short loc_1803075D3
0x1803075f0  mov     bpl, 1
0x1803075f3  jmp     short loc_1803075F8
0x1803075f5  mov     bpl, r13b
0x1803075f8  cmp     [rbx+4Dh], r13b
0x1803075fc  jz      short loc_180307616
0x1803075fe  mov     ecx, [rcx+0F8h]; idThread
0x180307604  xor     r9d, r9d; lParam
0x180307607  mov     edx, 842Ah; Msg
0x18030760c  lea     r8d, [r9+1]; wParam
0x180307610  call    cs:__imp_PostThreadMessageW
0x180307616  mov     rdx, [rbx+8]
0x18030761a  xor     r9d, r9d; bool
0x18030761d  mov     r8d, r14d; unsigned int
0x180307620  mov     rcx, rbx; this
0x180307623  mov     edx, [rdx+0F8h]; unsigned int
0x180307629  call    ?_AttachThreadInputHelper@CDetachedBrowserTabCoverUI@@IEAAJKK_N@Z; CDetachedBrowserTabCoverUI::_AttachThreadInputHelper(ulong,ulong,bool)
0x18030762e  mov     edi, eax
0x180307630  test    eax, eax
0x180307632  js      loc_180307889
0x180307638  xor     edx, edx; bool
0x18030763a  mov     rcx, rbx; this
0x18030763d  call    ?_HideAndDisparentFrameTab@CDetachedBrowserTabCoverUI@@IEAA_N_N@Z; CDetachedBrowserTabCoverUI::_HideAndDisparentFrameTab(bool)
0x180307642  test    al, al
0x180307644  jz      short loc_1803076A8
0x180307646  mov     rcx, [rbx+8]
0x18030764a  mov     rcx, [rcx+158h]; hWnd
0x180307651  cmp     r15, rcx
0x180307654  jnz     short loc_18030765E
0x180307656  call    cs:__imp_SetActiveWindow
0x18030765c  jmp     short loc_18030768A
0x18030765e  xor     r9d, r9d; lParam
0x180307661  xor     r8d, r8d; wParam
0x180307664  lea     edx, [r9+6]; Msg
0x180307668  call    cs:__imp_SendMessageW
0x18030766e  mov     rcx, [rbx+8]
0x180307672  xor     r9d, r9d; lParam
0x180307675  xor     r8d, r8d; wParam
0x180307678  mov     edx, 86h; Msg
0x18030767d  mov     rcx, [rcx+158h]; hWnd
0x180307684  call    cs:__imp_SendMessageW
0x18030768a  test    bpl, bpl
0x18030768d  jz      short loc_18030769B
0x18030768f  mov     rcx, [rbx+10h]; hWnd
0x180307693  call    cs:__imp_SetFocus
0x180307699  jmp     short loc_18030769F
0x18030769b  mov     [rbx+18h], r13
0x18030769f  mov     byte ptr [rbx+46h], 1
0x1803076a3  jmp     loc_180307889
0x1803076a8  call    cs:__imp_GetLastError
0x1803076ae  mov     edi, eax
0x1803076b0  test    eax, eax
0x1803076b2  jle     short loc_1803076BD
0x1803076b4  movzx   edi, ax
0x1803076b7  or      edi, 80070000h
0x1803076bd  mov     eax, [rbx+80h]
0x1803076c3  test    eax, eax
0x1803076c5  jz      short loc_1803076F4
0x1803076c7  mov     rcx, [rbx+8]
0x1803076cb  dec     eax
0x1803076cd  mov     [rbx+80h], eax
0x1803076d3  mov     r8d, 1; fAttach
0x1803076d9  mov     edx, r14d; idAttachTo
0x1803076dc  mov     ecx, [rcx+0F8h]; idAttach
0x1803076e2  call    cs:__imp_AttachThreadInput
0x1803076e8  mov     eax, [rbx+80h]
0x1803076ee  test    eax, eax
0x1803076f0  jnz     short loc_1803076C7
0x1803076f2  jmp     short loc_1803076F7
0x1803076f4  mov     eax, r13d
0x1803076f7  dec     eax
0x1803076f9  mov     [rbx+80h], eax
0x1803076ff  jmp     loc_180307889
0x180307704  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18030770a  test    al, al
0x18030770c  jz      short loc_180307750
0x18030770e  mov     rax, [rsi]
0x180307711  lea     r8, s_FocusStomperThreadProc; lpStartAddress
0x180307718  mov     [rsp+88h+lpThreadId], r13; lpThreadId
0x18030771d  xor     edx, edx; dwStackSize
0x18030771f  xor     ecx, ecx; lpThreadAttributes
0x180307721  mov     [rsp+88h+dwCreationFlags], r13d; dwCreationFlags
0x180307726  mov     r9d, [rax+0F8h]; lpParameter
0x18030772d  call    cs:__imp_CreateThread
0x180307733  mov     rdi, rax
0x180307736  test    rax, rax
0x180307739  jz      short loc_180307750
0x18030773b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18030773e  mov     rcx, rax; hHandle
0x180307741  call    cs:__imp_WaitForSingleObject
0x180307747  mov     rcx, rdi; hObject
0x18030774a  call    cs:__imp_CloseHandle
0x180307750  mov     rax, [rsi]
0x180307753  cmp     [rbx+4Dh], r13b
0x180307757  jnz     loc_180307846
0x18030775d  mov     rcx, [rax+160h]; hWnd
0x180307764  mov     edx, 0FFFFFFF0h; nIndex
0x180307769  mov     r9d, 40000000h
0x18030776f  mov     r8d, 0C0000000h
0x180307775  call    SHSetWindowBits
0x18030777a  mov     rcx, [rsi]
0x18030777d  mov     rdx, [rcx+158h]; hWndNewParent
0x180307784  mov     rcx, [rcx+160h]; hWndChild
0x18030778b  call    cs:__imp_SetParent
0x180307791  test    rax, rax
0x180307794  jz      loc_18030782F
0x18030779a  mov     rcx, [rsi]
0x18030779d  xor     r9d, r9d; Y
0x1803077a0  mov     [rsp+88h+uFlags], 13h; uFlags
0x1803077a8  xor     r8d, r8d; X
0x1803077ab  mov     dword ptr [rsp+88h+lpThreadId], r13d; cy
0x1803077b0  mov     rdx, r15; hWndInsertAfter
0x1803077b3  mov     [rsp+88h+dwCreationFlags], r13d; cx
0x1803077b8  mov     rcx, [rcx+160h]; hWnd
0x1803077bf  call    cs:__imp_SetWindowPos
0x1803077c5  mov     rax, [rsi]
0x1803077c8  mov     rcx, [rax+178h]; hWnd
0x1803077cf  test    rcx, rcx
0x1803077d2  jz      short loc_1803077EF
0x1803077d4  xor     r8d, r8d; bErase
0x1803077d7  xor     edx, edx; lpRect
0x1803077d9  call    cs:__imp_InvalidateRect
0x1803077df  mov     rcx, [rsi]
0x1803077e2  mov     rcx, [rcx+178h]; hWnd
0x1803077e9  call    cs:__imp_UpdateWindow
0x1803077ef  mov     rcx, [rsi]
0x1803077f2  mov     rcx, [rcx+170h]; hWnd
0x1803077f9  call    cs:__imp_UpdateWindow
0x1803077ff  mov     rdx, [rsi]
0x180307802  mov     r9b, r15b; bool
0x180307805  mov     r8d, r14d; unsigned int
0x180307808  mov     rcx, rbx; this
0x18030780b  mov     edx, [rdx+0F8h]; unsigned int
0x180307811  call    ?_AttachThreadInputHelper@CDetachedBrowserTabCoverUI@@IEAAJKK_N@Z; CDetachedBrowserTabCoverUI::_AttachThreadInputHelper(ulong,ulong,bool)
0x180307816  mov     edi, eax
0x180307818  test    eax, eax
0x18030781a  js      short loc_180307889
0x18030781c  mov     dl, r15b; bool
0x18030781f  mov     [rbx+46h], r13b
0x180307823  mov     rcx, rbx; this
0x180307826  call    ?ReparentDevTools@CDetachedBrowserTabCoverUI@@QEAAJ_N@Z; CDetachedBrowserTabCoverUI::ReparentDevTools(bool)
0x18030782b  mov     edi, eax
0x18030782d  jmp     short loc_180307889
0x18030782f  call    cs:__imp_GetLastError
0x180307835  mov     edi, eax
0x180307837  test    eax, eax
0x180307839  jle     short loc_180307889
0x18030783b  movzx   edi, ax
0x18030783e  or      edi, 80070000h
0x180307844  jmp     short loc_180307889
0x180307846  mov     edx, [rax+0F8h]; unsigned int
0x18030784c  mov     r9b, r15b; bool
0x18030784f  mov     r8d, r14d; unsigned int
0x180307852  mov     rcx, rbx; this
0x180307855  call    ?_AttachThreadInputHelper@CDetachedBrowserTabCoverUI@@IEAAJKK_N@Z; CDetachedBrowserTabCoverUI::_AttachThreadInputHelper(ulong,ulong,bool)
0x18030785a  mov     edi, eax
0x18030785c  test    eax, eax
0x18030785e  js      short loc_180307864
0x180307860  mov     [rbx+46h], r13b
0x180307864  cmp     [rbx+50h], r13b
0x180307868  jz      short loc_180307889
0x18030786a  call    cs:__imp_GetForegroundWindow
0x180307870  test    rax, rax
0x180307873  jnz     short loc_180307885
0x180307875  mov     rcx, [rsi]
0x180307878  mov     rcx, [rcx+158h]; hWnd
0x18030787f  call    cs:__imp_SetForegroundWindow
0x180307885  mov     [rbx+50h], r13b
0x180307889  mov     rcx, rbx; this
0x18030788c  call    ?_UpdateHangProtectionState@CDetachedBrowserTabCoverUI@@IEAAXXZ; CDetachedBrowserTabCoverUI::_UpdateHangProtectionState(void)
0x180307891  test    byte ptr cs:Microsoft_IEFRAMEEnableBits+1, 8
0x180307898  jz      short loc_1803078B7
0x18030789a  mov     r9, [rsi]
0x18030789d  lea     rdx, BROWSEUI_HANGUI_DISPARENTANDDETACHBROWSERTAB_STOP
0x1803078a4  mov     r8d, r12d
0x1803078a7  mov     [rsp+88h+dwCreationFlags], edi
0x1803078ab  mov     r9d, [r9+0F0h]
0x1803078b2  call    McTemplateU0qtq_EventWriteTransfer
0x1803078b7  test    edi, edi
0x1803078b9  setz    al
0x1803078bc  add     rsp, 48h
0x1803078c0  pop     r15
0x1803078c2  pop     r14
0x1803078c4  pop     r13
0x1803078c6  pop     r12
0x1803078c8  pop     rdi
0x1803078c9  pop     rsi
0x1803078ca  pop     rbp
0x1803078cb  pop     rbx
0x1803078cc  retn
```

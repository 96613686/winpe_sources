# _anonymous_namespace_::ShowMessageDialogAndGetUserSelection

- ea: `0x1800653f8`
- end: `0x1800655d1`
- name: `_anonymous_namespace_::ShowMessageDialogAndGetUserSelection`
- size: `473`
- prototype: `HRESULT __fastcall(HWND__ *ParentWindow, const wchar_t *Content, const wchar_t *AllowCommandText, const wchar_t *DenyCommandText, bool *UserSelection)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800652cc`

## callees

- `0x180002790`
- `0x180012748`
- `0x180012770`
- `0x1800128a4`
- `0x1800653f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065489`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065489`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006555d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006555d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006549d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006551a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006549d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006551a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006557a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006557a`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800654eb`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800654eb`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ShowMessageDialogAndGetUserSelection(
        HWND__ *ParentWindow,
        const wchar_t *Content,
        const wchar_t *AllowCommandText,
        const wchar_t *DenyCommandText,
        bool *UserSelection)
{
  int hrExit; // ebx
  signed int LastError; // eax
  signed int v11; // eax
  SHOWDIALOG_PARAMS params; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_SSS(
      WPP_GLOBAL_Control->Control.Logger,
      0x16u,
      WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids,
      Content,
      AllowCommandText,
      DenyCommandText);
  }
  params.ParentWindow = ParentWindow;
  params.Content = Content;
  params.AllowCommandText = AllowCommandText;
  params.DenyCommandText = DenyCommandText;
  hrExit = 0;
  *(_QWORD *)&params.UserSelection = 0;
  params.CompletionEvent = CreateEventW(0, 0, 0, 0);
  if ( params.CompletionEvent )
    goto LABEL_9;
  LastError = GetLastError();
  hrExit = LastError;
  if ( LastError > 0 )
    hrExit = (unsigned __int16)LastError | 0x80070000;
  if ( hrExit >= 0 )
  {
LABEL_9:
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x17u, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids);
    }
    if ( !TrySubmitThreadpoolCallback(anonymous_namespace_::ShowMessageDialogAndGetUserSelection_Thunk, &params, 0) )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x18u, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids);
      }
      v11 = GetLastError();
      hrExit = v11;
      if ( v11 > 0 )
        hrExit = (unsigned __int16)v11 | 0x80070000;
    }
    if ( hrExit >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids);
      }
      WaitForSingleObject(params.CompletionEvent, 0xFFFFFFFF);
      hrExit = params.hrExit;
      if ( params.hrExit >= 0 )
        *UserSelection = params.UserSelection;
    }
  }
  if ( params.CompletionEvent )
  {
    CloseHandle(params.CompletionEvent);
    params.CompletionEvent = 0;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Au, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids, hrExit);
  }
  return (unsigned int)hrExit;
}

```

## disassembly

```asm
0x1800653f8  push    rbp
0x1800653fa  push    rbx
0x1800653fb  push    rsi
0x1800653fc  push    rdi
0x1800653fd  push    r12
0x1800653ff  push    r13
0x180065401  push    r14
0x180065403  push    r15
0x180065405  mov     rbp, rsp
0x180065408  sub     rsp, 78h
0x18006540c  mov     rax, cs:__security_cookie
0x180065413  xor     rax, rsp
0x180065416  mov     [rbp+var_18], rax
0x18006541a  mov     r12, [rbp+arg_20]
0x18006541e  mov     r14, DenyCommandText
0x180065421  mov     rsi, AllowCommandText
0x180065424  mov     rdi, Content
0x180065427  mov     r15, ParentWindow
0x18006542a  mov     ParentWindow, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180065431  lea     r13, WPP_GLOBAL_Control
0x180065438  cmp     ParentWindow, r13
0x18006543b  jz      short loc_180065465
0x18006543d  test    byte ptr [ParentWindow+1Ch], 10h
0x180065441  jz      short loc_180065465
0x180065443  mov     ParentWindow, [ParentWindow+10h]; Logger
0x180065447  mov     edx, 16h; id
0x18006544c  mov     [rsp+78h+_a3], DenyCommandText; _a3
0x180065451  mov     DenyCommandText, rdi; _a1
0x180065454  mov     [rsp+78h+_a2], AllowCommandText; _a2
0x180065459  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x180065460  call    WPP_SF_SSS
0x180065465  xorps   xmm0, xmm0
0x180065468  mov     [rbp+params.ParentWindow], r15
0x18006546c  xor     r9d, r9d; lpName
0x18006546f  mov     [rbp+params.Content], rdi
0x180065473  xor     r8d, r8d; bInitialState
0x180065476  mov     [rbp+params.AllowCommandText], rsi
0x18006547a  xor     edx, edx; bManualReset
0x18006547c  mov     [rbp+params.DenyCommandText], r14
0x180065480  xor     ecx, ecx; lpEventAttributes
0x180065482  xor     ebx, ebx
0x180065484  movdqu  xmmword ptr [rbp+params.UserSelection], xmm0
0x180065489  call    cs:__imp_CreateEventW
0x18006548f  mov     [rbp+params.CompletionEvent], rax
0x180065493  mov     edi, 80070000h
0x180065498  test    rax, rax
0x18006549b  jnz     short loc_1800654B6
0x18006549d  call    cs:__imp_GetLastError
0x1800654a3  mov     ebx, eax
0x1800654a5  test    eax, eax
0x1800654a7  jle     short loc_1800654AE
0x1800654a9  movzx   ebx, ax
0x1800654ac  or      ebx, edi
0x1800654ae  test    ebx, ebx
0x1800654b0  js      loc_180065571
0x1800654b6  mov     ParentWindow, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800654bd  cmp     ParentWindow, r13
0x1800654c0  jz      short loc_1800654DD
0x1800654c2  test    byte ptr [ParentWindow+1Ch], 10h
0x1800654c6  jz      short loc_1800654DD
0x1800654c8  mov     ParentWindow, [ParentWindow+10h]; Logger
0x1800654cc  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x1800654d3  mov     edx, 17h; id
0x1800654d8  call    WPP_SF_
0x1800654dd  xor     r8d, r8d; pcbe
0x1800654e0  lea     Content, [rbp+params]; pv
0x1800654e4  lea     ParentWindow, _anonymous_namespace___ShowMessageDialogAndGetUserSelection_Thunk; pfns
0x1800654eb  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800654f1  test    eax, eax
0x1800654f3  jnz     short loc_18006552B
0x1800654f5  mov     ParentWindow, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800654fc  cmp     ParentWindow, r13
0x1800654ff  jz      short loc_18006551A
0x180065501  test    byte ptr [ParentWindow+1Ch], 2
0x180065505  jz      short loc_18006551A
0x180065507  mov     ParentWindow, [ParentWindow+10h]; Logger
0x18006550b  lea     edx, [rax+18h]; id
0x18006550e  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x180065515  call    WPP_SF_
0x18006551a  call    cs:__imp_GetLastError
0x180065520  mov     ebx, eax
0x180065522  test    eax, eax
0x180065524  jle     short loc_18006552B
0x180065526  movzx   ebx, ax
0x180065529  or      ebx, edi
0x18006552b  test    ebx, ebx
0x18006552d  js      short loc_180065571
0x18006552f  mov     ParentWindow, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180065536  cmp     ParentWindow, r13
0x180065539  jz      short loc_180065556
0x18006553b  test    byte ptr [ParentWindow+1Ch], 10h
0x18006553f  jz      short loc_180065556
0x180065541  mov     ParentWindow, [ParentWindow+10h]; Logger
0x180065545  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x18006554c  mov     edx, 19h; id
0x180065551  call    WPP_SF_
0x180065556  mov     ParentWindow, [rbp+params.CompletionEvent]; hHandle
0x18006555a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006555d  call    cs:__imp_WaitForSingleObject
0x180065563  mov     ebx, [rbp+params.hrExit]
0x180065566  test    ebx, ebx
0x180065568  js      short loc_180065571
0x18006556a  mov     al, [rbp+params.UserSelection]
0x18006556d  mov     [r12], al
0x180065571  mov     ParentWindow, [rbp+params.CompletionEvent]; hObject
0x180065575  test    ParentWindow, ParentWindow
0x180065578  jz      short loc_180065588
0x18006557a  call    cs:__imp_CloseHandle
0x180065580  mov     [rbp+params.CompletionEvent], 0
0x180065588  mov     ParentWindow, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18006558f  cmp     ParentWindow, r13
0x180065592  jz      short loc_1800655B2
0x180065594  test    byte ptr [ParentWindow+1Ch], 10h
0x180065598  jz      short loc_1800655B2
0x18006559a  mov     ParentWindow, [ParentWindow+10h]; Logger
0x18006559e  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x1800655a5  mov     edx, 1Ah; id
0x1800655aa  mov     r9d, ebx; _a1
0x1800655ad  call    WPP_SF_d
0x1800655b2  mov     eax, ebx
0x1800655b4  mov     ParentWindow, [rbp+var_18]
0x1800655b8  xor     ParentWindow, rsp; StackCookie
0x1800655bb  call    __security_check_cookie
0x1800655c0  add     rsp, 78h
0x1800655c4  pop     r15
0x1800655c6  pop     r14
0x1800655c8  pop     r13
0x1800655ca  pop     r12
0x1800655cc  pop     rdi
0x1800655cd  pop     rsi
0x1800655ce  pop     rbx
0x1800655cf  pop     rbp
0x1800655d0  retn
```

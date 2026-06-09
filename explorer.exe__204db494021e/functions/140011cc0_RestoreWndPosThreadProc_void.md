# RestoreWndPosThreadProc(void *)

- ea: `0x140011cc0`
- end: `0x14001204c`
- name: `?RestoreWndPosThreadProc@@YAKPEAX@Z`
- size: `908`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000bb20`
- `0x140011cc0`
- `0x1400131e8`
- `0x140021430`
- `0x1400b1cb8`
- `0x1400b454c`
- `0x1400b90e0`
- `0x14010e160`
- `0x14010e4c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140011fcc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140011fcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011fdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011fdc`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140011e7e`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140011e7e`
- `api-ms-win-ntuser-rectangle-l1-1-0!OffsetRect` at `0x140011e9d`
- `api-ms-win-ntuser-rectangle-l1-1-0!OffsetRect` at `0x140011e9d`
- `UxTheme!IsCompositionActive` at `0x140011d47`
- `UxTheme!IsCompositionActive` at `0x140011d47`
- `USER32!HungWindowFromGhostWindow` at `0x140011dda`
- `USER32!HungWindowFromGhostWindow` at `0x140011dda`
- `USER32!IsIconic` at `0x140011e02`
- `USER32!IsIconic` at `0x140011e35`
- `USER32!IsIconic` at `0x140011e02`
- `USER32!IsIconic` at `0x140011e35`
- `USER32!IsHungAppWindow` at `0x140011dc7`
- `USER32!IsHungAppWindow` at `0x140011dc7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x140011d33`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x140011d33`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x140011db0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x140011db0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x140011ee0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x140011ee0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x140011fb7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x140011fb7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x140011f8d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x140011f8d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EndDeferWindowPos` at `0x140011f6f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EndDeferWindowPos` at `0x140011f6f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!BeginDeferWindowPos` at `0x140011f22`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!BeginDeferWindowPos` at `0x140011f22`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!SetWindowPlacement` at `0x140011ebc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!SetWindowPlacement` at `0x140011ebc`

## pseudocode

```c
__int64 __fastcall RestoreWndPosThreadProc(__int64 *Parameter, __int64 a2, __int64 a3)
{
  int v4; // esi
  int v5; // r12d
  HWND ForegroundWindow; // rbp
  char v7; // r13
  _DWORD *v8; // rcx
  int i; // r14d
  HWND *ItemPtr; // rax
  HWND *v11; // rdi
  HDWP v12; // rdi
  __int64 v13; // rax
  int v14; // esi
  __int64 v15; // rcx
  HWND v16; // rcx
  void *v17; // rcx
  __int64 v18; // r8
  int v20; // [rsp+30h] [rbp-78h]
  __int128 pvParam; // [rsp+40h] [rbp-68h] BYREF

  if ( !Parameter || !*Parameter )
    return 1;
  v4 = *((_DWORD *)Parameter + 7);
  v5 = v4 & 2;
  if ( (v4 & 2) != 0 && (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Shell_Core_Provider_Context, Shake_RestoreWorker_Start, a3, 1);
  ForegroundWindow = GetForegroundWindow();
  if ( !IsCompositionActive() || (v4 & 4) != 0 )
  {
    v7 = 1;
    v20 = SetAnimation(0);
  }
  else
  {
    v7 = 0;
    v20 = 0;
  }
  v8 = *(_DWORD **)(*Parameter + 8);
  if ( v8 )
  {
    for ( i = *v8 - 1; i >= 0; --i )
    {
      ItemPtr = (HWND *)DSA_GetItemPtr(*(HDSA *)(*Parameter + 8), i);
      v11 = ItemPtr;
      if ( ItemPtr
        && IsWindow(*ItemPtr)
        && (!IsHungAppWindow(*v11) || HungWindowFromGhostWindow(*v11))
        && *((_DWORD *)v11 + 2) )
      {
        if ( (v4 & 4) != 0 && !IsIconic(*v11) )
          DSA_DeleteItem(*(HDSA *)(*Parameter + 8), i);
        if ( *((_DWORD *)v11 + 2) && ((v4 & 4) == 0 || IsIconic(*v11)) )
        {
          *((_DWORD *)v11 + 3) = 44;
          if ( (v4 & 4) == 0 )
            *((_DWORD *)v11 + 4) |= 4u;
          if ( *((_DWORD *)v11 + 5) == 1 )
          {
            *((_DWORD *)v11 + 5) = 4;
            if ( (v4 & 4) != 0 )
            {
              pvParam = 0;
              SystemParametersInfoW(0x30u, 0, &pvParam, 0);
              if ( *((_DWORD *)v11 + 12) > SDWORD2(pvParam) )
                OffsetRect((LPRECT)(v11 + 5), DWORD2(pvParam) - *((_DWORD *)v11 + 12), 0);
              if ( *((_DWORD *)v11 + 10) < (int)pvParam )
                *((_DWORD *)v11 + 10) = pvParam;
            }
          }
          if ( !SetWindowPlacement(*v11, (const WINDOWPLACEMENT *)((char *)v11 + 12)) )
            SendMessageW(*v11, 0x112u, 0xF120u, 0);
        }
      }
    }
  }
  if ( v7 )
    SetAnimation(v20);
  if ( (v4 & 3) != 0 )
  {
    v12 = BeginDeferWindowPos(**(_DWORD **)(*Parameter + 8));
    if ( (v4 & 2) != 0 )
    {
      v13 = Parameter[4];
      v14 = v4 & 4;
    }
    else
    {
      v14 = v4 & 4;
      v13 = v14 != 0;
    }
    v15 = *Parameter;
    *(_QWORD *)&pvParam = v12;
    *((_QWORD *)&pvParam + 1) = v13;
    DSA_EnumCallback(*(HDSA *)(v15 + 8), DeferCallback, &pvParam);
    EndDeferWindowPos(v12);
    if ( v5 )
    {
      v16 = (HWND)Parameter[5];
LABEL_44:
      SetForegroundWindow(v16);
      goto LABEL_45;
    }
    if ( v14 )
    {
      v16 = ForegroundWindow;
      goto LABEL_44;
    }
  }
LABEL_45:
  _DestroySavedWindowPositions((HLOCAL)*Parameter);
  if ( *((_DWORD *)Parameter + 6) )
    PostMessageW((HWND)Parameter[1], 0x453u, Parameter[2], 1);
  v17 = (void *)Parameter[6];
  if ( v17 )
  {
    SetEvent(v17);
    CloseHandle((HANDLE)Parameter[6]);
  }
  operator delete(Parameter, 0x38u);
  if ( v5 )
  {
    g_fWinHomeListening = 1;
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Shell_Core_Provider_Context,
        Shake_RestoreWorker_Stop,
        v18,
        1);
  }
  return 1;
}

```

## disassembly

```asm
0x140011cc0  push    rbx
0x140011cc2  push    rbp
0x140011cc3  push    rsi
0x140011cc4  push    rdi
0x140011cc5  push    r12
0x140011cc7  push    r13
0x140011cc9  push    r14
0x140011ccb  push    r15
0x140011ccd  sub     rsp, 68h
0x140011cd1  mov     rax, cs:__security_cookie
0x140011cd8  xor     rax, rsp
0x140011cdb  mov     [rsp+0A8h+var_58], rax
0x140011ce0  xor     r15d, r15d
0x140011ce3  mov     rbx, rcx
0x140011ce6  mov     r14d, 1
0x140011cec  test    rcx, rcx
0x140011cef  jz      loc_14001202A
0x140011cf5  cmp     [rcx], r15
0x140011cf8  jz      loc_14001202A
0x140011cfe  mov     esi, [rcx+1Ch]
0x140011d01  mov     r12d, esi
0x140011d04  and     r12d, 2
0x140011d08  jz      short loc_140011D33
0x140011d0a  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r14b
0x140011d11  jz      short loc_140011D33
0x140011d13  lea     rax, [rsp+0A8h+pvParam]
0x140011d18  mov     r9d, r14d
0x140011d1b  lea     rdx, Shake_RestoreWorker_Start
0x140011d22  mov     [rsp+0A8h+var_88], rax
0x140011d27  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x140011d2e  call    McGenEventWrite_EventWriteTransfer
0x140011d33  call    cs:__imp_GetForegroundWindow
0x140011d3a  nop     dword ptr [rax+rax+00h]
0x140011d3f  mov     rbp, rax
0x140011d42  mov     [rsp+0A8h+var_70], rax
0x140011d47  call    cs:__imp_IsCompositionActive
0x140011d4e  nop     dword ptr [rax+rax+00h]
0x140011d53  test    eax, eax
0x140011d55  jz      short loc_140011D67
0x140011d57  test    sil, 4
0x140011d5b  jnz     short loc_140011D67
0x140011d5d  mov     r13b, r15b
0x140011d60  mov     [rsp+0A8h+var_78], r15d
0x140011d65  jmp     short loc_140011D75
0x140011d67  xor     ecx, ecx; int
0x140011d69  mov     r13b, r14b
0x140011d6c  call    ?SetAnimation@@YAHH@Z; SetAnimation(int)
0x140011d71  mov     [rsp+0A8h+var_78], eax
0x140011d75  mov     rax, [rbx]
0x140011d78  mov     rcx, [rax+8]
0x140011d7c  test    rcx, rcx
0x140011d7f  jz      loc_140011F01
0x140011d85  mov     r14d, [rcx]
0x140011d88  sub     r14d, 1
0x140011d8c  js      loc_140011EFB
0x140011d92  mov     rcx, [rbx]
0x140011d95  mov     edx, r14d; i
0x140011d98  mov     rcx, [rcx+8]; hdsa
0x140011d9c  call    DSA_GetItemPtr
0x140011da1  mov     rdi, rax
0x140011da4  test    rax, rax
0x140011da7  jz      loc_140011EEC
0x140011dad  mov     rcx, [rax]; hWnd
0x140011db0  call    cs:__imp_IsWindow
0x140011db7  nop     dword ptr [rax+rax+00h]
0x140011dbc  test    eax, eax
0x140011dbe  jz      loc_140011EEC
0x140011dc4  mov     rcx, [rdi]; hwnd
0x140011dc7  call    cs:__imp_IsHungAppWindow
0x140011dce  nop     dword ptr [rax+rax+00h]
0x140011dd3  test    eax, eax
0x140011dd5  jz      short loc_140011DEF
0x140011dd7  mov     rcx, [rdi]
0x140011dda  call    cs:__imp_HungWindowFromGhostWindow
0x140011de1  nop     dword ptr [rax+rax+00h]
0x140011de6  test    rax, rax
0x140011de9  jz      loc_140011EEC
0x140011def  cmp     [rdi+8], r15d
0x140011df3  jz      loc_140011EEC
0x140011df9  test    sil, 4
0x140011dfd  jz      short loc_140011E21
0x140011dff  mov     rcx, [rdi]; hWnd
0x140011e02  call    cs:__imp_IsIconic
0x140011e09  nop     dword ptr [rax+rax+00h]
0x140011e0e  test    eax, eax
0x140011e10  jnz     short loc_140011E21
0x140011e12  mov     rcx, [rbx]
0x140011e15  mov     edx, r14d; i
0x140011e18  mov     rcx, [rcx+8]; hdsa
0x140011e1c  call    DSA_DeleteItem
0x140011e21  cmp     [rdi+8], r15d
0x140011e25  jz      loc_140011EEC
0x140011e2b  mov     ebp, esi
0x140011e2d  and     ebp, 4
0x140011e30  jz      short loc_140011E49
0x140011e32  mov     rcx, [rdi]; hWnd
0x140011e35  call    cs:__imp_IsIconic
0x140011e3c  nop     dword ptr [rax+rax+00h]
0x140011e41  test    eax, eax
0x140011e43  jz      loc_140011EEC
0x140011e49  mov     dword ptr [rdi+0Ch], 2Ch ; ','
0x140011e50  test    ebp, ebp
0x140011e52  jnz     short loc_140011E58
0x140011e54  or      dword ptr [rdi+10h], 4
0x140011e58  cmp     dword ptr [rdi+14h], 1
0x140011e5c  jnz     short loc_140011EB5
0x140011e5e  mov     dword ptr [rdi+14h], 4
0x140011e65  test    ebp, ebp
0x140011e67  jz      short loc_140011EB5
0x140011e69  xor     edx, edx; uiParam
0x140011e6b  lea     r8, [rsp+0A8h+pvParam]; pvParam
0x140011e70  xorps   xmm0, xmm0
0x140011e73  xor     r9d, r9d; fWinIni
0x140011e76  movups  [rsp+0A8h+pvParam], xmm0
0x140011e7b  lea     ecx, [rdx+30h]; uiAction
0x140011e7e  call    cs:__imp_SystemParametersInfoW
0x140011e85  nop     dword ptr [rax+rax+00h]
0x140011e8a  mov     edx, dword ptr [rsp+0A8h+pvParam+8]
0x140011e8e  cmp     [rdi+30h], edx
0x140011e91  jle     short loc_140011EA9
0x140011e93  sub     edx, [rdi+30h]; dx
0x140011e96  lea     rcx, [rdi+28h]; lprc
0x140011e9a  xor     r8d, r8d; dy
0x140011e9d  call    cs:__imp_OffsetRect
0x140011ea4  nop     dword ptr [rax+rax+00h]
0x140011ea9  mov     eax, dword ptr [rsp+0A8h+pvParam]
0x140011ead  cmp     [rdi+28h], eax
0x140011eb0  jge     short loc_140011EB5
0x140011eb2  mov     [rdi+28h], eax
0x140011eb5  mov     rcx, [rdi]; hWnd
0x140011eb8  lea     rdx, [rdi+0Ch]; lpwndpl
0x140011ebc  call    cs:__imp_SetWindowPlacement
0x140011ec3  nop     dword ptr [rax+rax+00h]
0x140011ec8  xor     r15d, r15d
0x140011ecb  test    eax, eax
0x140011ecd  jnz     short loc_140011EEC
0x140011ecf  mov     rcx, [rdi]; hWnd
0x140011ed2  xor     r9d, r9d; lParam
0x140011ed5  mov     edx, 112h; Msg
0x140011eda  mov     r8d, 0F120h; wParam
0x140011ee0  call    cs:__imp_SendMessageW
0x140011ee7  nop     dword ptr [rax+rax+00h]
0x140011eec  sub     r14d, 1
0x140011ef0  jns     loc_140011D92
0x140011ef6  mov     rbp, [rsp+0A8h+var_70]
0x140011efb  mov     r14d, 1
0x140011f01  test    r13b, r13b
0x140011f04  jz      short loc_140011F0F
0x140011f06  mov     ecx, [rsp+0A8h+var_78]; int
0x140011f0a  call    ?SetAnimation@@YAHH@Z; SetAnimation(int)
0x140011f0f  test    sil, 3
0x140011f13  jz      loc_140011F99
0x140011f19  mov     rax, [rbx]
0x140011f1c  mov     rcx, [rax+8]
0x140011f20  mov     ecx, [rcx]; nNumWindows
0x140011f22  call    cs:__imp_BeginDeferWindowPos
0x140011f29  nop     dword ptr [rax+rax+00h]
0x140011f2e  mov     rdi, rax
0x140011f31  test    r12d, r12d
0x140011f34  jz      short loc_140011F3F
0x140011f36  mov     rax, [rbx+20h]
0x140011f3a  and     esi, 4
0x140011f3d  jmp     short loc_140011F4A
0x140011f3f  mov     rax, r14
0x140011f42  and     esi, 4
0x140011f45  jnz     short loc_140011F4A
0x140011f47  mov     rax, r15
0x140011f4a  mov     rcx, [rbx]
0x140011f4d  lea     r8, [rsp+0A8h+pvParam]; pData
0x140011f52  mov     qword ptr [rsp+0A8h+pvParam], rdi
0x140011f57  lea     rdx, ?DeferCallback@@YAHPEAX0@Z; pfnCB
0x140011f5e  mov     qword ptr [rsp+0A8h+pvParam+8], rax
0x140011f63  mov     rcx, [rcx+8]; hdsa
0x140011f67  call    DSA_EnumCallback
0x140011f6c  mov     rcx, rdi; hWinPosInfo
0x140011f6f  call    cs:__imp_EndDeferWindowPos
0x140011f76  nop     dword ptr [rax+rax+00h]
0x140011f7b  test    r12d, r12d
0x140011f7e  jz      short loc_140011F86
0x140011f80  mov     rcx, [rbx+28h]
0x140011f84  jmp     short loc_140011F8D
0x140011f86  test    esi, esi
0x140011f88  jz      short loc_140011F99
0x140011f8a  mov     rcx, rbp; hWnd
0x140011f8d  call    cs:__imp_SetForegroundWindow
0x140011f94  nop     dword ptr [rax+rax+00h]
0x140011f99  mov     rcx, [rbx]; hMem
0x140011f9c  call    ?_DestroySavedWindowPositions@@YAXPEAUWINDOWPOSITIONS@@@Z; _DestroySavedWindowPositions(WINDOWPOSITIONS *)
0x140011fa1  cmp     [rbx+18h], r15d
0x140011fa5  jz      short loc_140011FC3
0x140011fa7  mov     r8, [rbx+10h]; wParam
0x140011fab  mov     r9, r14; lParam
0x140011fae  mov     rcx, [rbx+8]; hWnd
0x140011fb2  mov     edx, 453h; Msg
0x140011fb7  call    cs:__imp_PostMessageW
0x140011fbe  nop     dword ptr [rax+rax+00h]
0x140011fc3  mov     rcx, [rbx+30h]; hEvent
0x140011fc7  test    rcx, rcx
0x140011fca  jz      short loc_140011FE8
0x140011fcc  call    cs:__imp_SetEvent
0x140011fd3  nop     dword ptr [rax+rax+00h]
0x140011fd8  mov     rcx, [rbx+30h]; hObject
0x140011fdc  call    cs:__imp_CloseHandle
0x140011fe3  nop     dword ptr [rax+rax+00h]
0x140011fe8  mov     edx, 38h ; '8'; unsigned __int64
0x140011fed  mov     rcx, rbx; void *
0x140011ff0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011ff5  test    r12d, r12d
0x140011ff8  jz      short loc_14001202A
0x140011ffa  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r14b
0x140012001  mov     cs:?g_fWinHomeListening@@3JA, r14d; long g_fWinHomeListening
0x140012008  jz      short loc_14001202A
0x14001200a  lea     rdx, [rsp+0A8h+pvParam]
0x14001200f  mov     r9d, r14d
0x140012012  mov     [rsp+0A8h+var_88], rdx
0x140012017  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x14001201e  lea     rdx, Shake_RestoreWorker_Stop
0x140012025  call    McGenEventWrite_EventWriteTransfer
0x14001202a  mov     eax, r14d
0x14001202d  mov     rcx, [rsp+0A8h+var_58]
0x140012032  xor     rcx, rsp; StackCookie
0x140012035  call    __security_check_cookie
0x14001203a  add     rsp, 68h
0x14001203e  pop     r15
0x140012040  pop     r14
0x140012042  pop     r13
0x140012044  pop     r12
0x140012046  pop     rdi
0x140012047  pop     rsi
0x140012048  pop     rbp
0x140012049  pop     rbx
0x14001204a  retn
```

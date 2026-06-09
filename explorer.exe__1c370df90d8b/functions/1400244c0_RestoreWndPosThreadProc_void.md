# RestoreWndPosThreadProc(void *)

- ea: `0x1400244c0`
- end: `0x1400247e1`
- name: `?RestoreWndPosThreadProc@@YAKPEAX@Z`
- size: `801`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000d890`
- `0x140023fe0`
- `0x1400244c0`
- `0x140025b0c`
- `0x1400abbcc`
- `0x1400ae1d0`
- `0x1400b2fe8`
- `0x1401040e0`
- `0x140104444`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002476e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002476e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024778`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024778`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140024654`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140024654`
- `api-ms-win-ntuser-rectangle-l1-1-0!OffsetRect` at `0x14002466d`
- `api-ms-win-ntuser-rectangle-l1-1-0!OffsetRect` at `0x14002466d`
- `UxTheme!IsCompositionActive` at `0x140024541`
- `UxTheme!IsCompositionActive` at `0x140024541`
- `USER32!HungWindowFromGhostWindow` at `0x1400245c2`
- `USER32!HungWindowFromGhostWindow` at `0x1400245c2`
- `USER32!IsIconic` at `0x1400245e4`
- `USER32!IsIconic` at `0x140024611`
- `USER32!IsIconic` at `0x1400245e4`
- `USER32!IsIconic` at `0x140024611`
- `USER32!IsHungAppWindow` at `0x1400245b5`
- `USER32!IsHungAppWindow` at `0x1400245b5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x140024533`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x140024533`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1400245a4`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1400245a4`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1400246a4`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1400246a4`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x14002475f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x14002475f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x14002473b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x14002473b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EndDeferWindowPos` at `0x140024723`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EndDeferWindowPos` at `0x140024723`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!BeginDeferWindowPos` at `0x1400246dc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!BeginDeferWindowPos` at `0x1400246dc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!SetWindowPlacement` at `0x140024686`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!SetWindowPlacement` at `0x140024686`

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
0x1400244c0  push    rbx
0x1400244c2  push    rbp
0x1400244c3  push    rsi
0x1400244c4  push    rdi
0x1400244c5  push    r12
0x1400244c7  push    r13
0x1400244c9  push    r14
0x1400244cb  push    r15
0x1400244cd  sub     rsp, 68h
0x1400244d1  mov     rax, cs:__security_cookie
0x1400244d8  xor     rax, rsp
0x1400244db  mov     [rsp+0A8h+var_58], rax
0x1400244e0  xor     r15d, r15d
0x1400244e3  mov     rbx, rcx
0x1400244e6  mov     r14d, 1
0x1400244ec  test    rcx, rcx
0x1400244ef  jz      loc_1400247C0
0x1400244f5  cmp     [rcx], r15
0x1400244f8  jz      loc_1400247C0
0x1400244fe  mov     esi, [rcx+1Ch]
0x140024501  mov     r12d, esi
0x140024504  and     r12d, 2
0x140024508  jz      short loc_140024533
0x14002450a  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r14b
0x140024511  jz      short loc_140024533
0x140024513  lea     rax, [rsp+0A8h+pvParam]
0x140024518  mov     r9d, r14d
0x14002451b  lea     rdx, Shake_RestoreWorker_Start
0x140024522  mov     [rsp+0A8h+var_88], rax
0x140024527  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x14002452e  call    McGenEventWrite_EventWriteTransfer
0x140024533  call    cs:__imp_GetForegroundWindow
0x140024539  mov     rbp, rax
0x14002453c  mov     [rsp+0A8h+var_70], rax
0x140024541  call    cs:__imp_IsCompositionActive
0x140024547  test    eax, eax
0x140024549  jz      short loc_14002455B
0x14002454b  test    sil, 4
0x14002454f  jnz     short loc_14002455B
0x140024551  mov     r13b, r15b
0x140024554  mov     [rsp+0A8h+var_78], r15d
0x140024559  jmp     short loc_140024569
0x14002455b  xor     ecx, ecx; int
0x14002455d  mov     r13b, r14b
0x140024560  call    ?SetAnimation@@YAHH@Z; SetAnimation(int)
0x140024565  mov     [rsp+0A8h+var_78], eax
0x140024569  mov     rax, [rbx]
0x14002456c  mov     rcx, [rax+8]
0x140024570  test    rcx, rcx
0x140024573  jz      loc_1400246BF
0x140024579  mov     r14d, [rcx]
0x14002457c  sub     r14d, 1
0x140024580  js      loc_1400246B9
0x140024586  mov     rcx, [rbx]
0x140024589  mov     edx, r14d; i
0x14002458c  mov     rcx, [rcx+8]; hdsa
0x140024590  call    DSA_GetItemPtr
0x140024595  mov     rdi, rax
0x140024598  test    rax, rax
0x14002459b  jz      loc_1400246AA
0x1400245a1  mov     rcx, [rax]; hWnd
0x1400245a4  call    cs:__imp_IsWindow
0x1400245aa  test    eax, eax
0x1400245ac  jz      loc_1400246AA
0x1400245b2  mov     rcx, [rdi]; hwnd
0x1400245b5  call    cs:__imp_IsHungAppWindow
0x1400245bb  test    eax, eax
0x1400245bd  jz      short loc_1400245D1
0x1400245bf  mov     rcx, [rdi]
0x1400245c2  call    cs:__imp_HungWindowFromGhostWindow
0x1400245c8  test    rax, rax
0x1400245cb  jz      loc_1400246AA
0x1400245d1  cmp     [rdi+8], r15d
0x1400245d5  jz      loc_1400246AA
0x1400245db  test    sil, 4
0x1400245df  jz      short loc_1400245FD
0x1400245e1  mov     rcx, [rdi]; hWnd
0x1400245e4  call    cs:__imp_IsIconic
0x1400245ea  test    eax, eax
0x1400245ec  jnz     short loc_1400245FD
0x1400245ee  mov     rcx, [rbx]
0x1400245f1  mov     edx, r14d; i
0x1400245f4  mov     rcx, [rcx+8]; hdsa
0x1400245f8  call    DSA_DeleteItem
0x1400245fd  cmp     [rdi+8], r15d
0x140024601  jz      loc_1400246AA
0x140024607  mov     ebp, esi
0x140024609  and     ebp, 4
0x14002460c  jz      short loc_14002461F
0x14002460e  mov     rcx, [rdi]; hWnd
0x140024611  call    cs:__imp_IsIconic
0x140024617  test    eax, eax
0x140024619  jz      loc_1400246AA
0x14002461f  mov     dword ptr [rdi+0Ch], 2Ch ; ','
0x140024626  test    ebp, ebp
0x140024628  jnz     short loc_14002462E
0x14002462a  or      dword ptr [rdi+10h], 4
0x14002462e  cmp     dword ptr [rdi+14h], 1
0x140024632  jnz     short loc_14002467F
0x140024634  mov     dword ptr [rdi+14h], 4
0x14002463b  test    ebp, ebp
0x14002463d  jz      short loc_14002467F
0x14002463f  xor     edx, edx; uiParam
0x140024641  lea     r8, [rsp+0A8h+pvParam]; pvParam
0x140024646  xorps   xmm0, xmm0
0x140024649  xor     r9d, r9d; fWinIni
0x14002464c  movups  [rsp+0A8h+pvParam], xmm0
0x140024651  lea     ecx, [rdx+30h]; uiAction
0x140024654  call    cs:__imp_SystemParametersInfoW
0x14002465a  mov     edx, dword ptr [rsp+0A8h+pvParam+8]
0x14002465e  cmp     [rdi+30h], edx
0x140024661  jle     short loc_140024673
0x140024663  sub     edx, [rdi+30h]; dx
0x140024666  lea     rcx, [rdi+28h]; lprc
0x14002466a  xor     r8d, r8d; dy
0x14002466d  call    cs:__imp_OffsetRect
0x140024673  mov     eax, dword ptr [rsp+0A8h+pvParam]
0x140024677  cmp     [rdi+28h], eax
0x14002467a  jge     short loc_14002467F
0x14002467c  mov     [rdi+28h], eax
0x14002467f  mov     rcx, [rdi]; hWnd
0x140024682  lea     rdx, [rdi+0Ch]; lpwndpl
0x140024686  call    cs:__imp_SetWindowPlacement
0x14002468c  xor     r15d, r15d
0x14002468f  test    eax, eax
0x140024691  jnz     short loc_1400246AA
0x140024693  mov     rcx, [rdi]; hWnd
0x140024696  xor     r9d, r9d; lParam
0x140024699  mov     edx, 112h; Msg
0x14002469e  mov     r8d, 0F120h; wParam
0x1400246a4  call    cs:__imp_SendMessageW
0x1400246aa  sub     r14d, 1
0x1400246ae  jns     loc_140024586
0x1400246b4  mov     rbp, [rsp+0A8h+var_70]
0x1400246b9  mov     r14d, 1
0x1400246bf  test    r13b, r13b
0x1400246c2  jz      short loc_1400246CD
0x1400246c4  mov     ecx, [rsp+0A8h+var_78]; int
0x1400246c8  call    ?SetAnimation@@YAHH@Z; SetAnimation(int)
0x1400246cd  test    sil, 3
0x1400246d1  jz      short loc_140024741
0x1400246d3  mov     rax, [rbx]
0x1400246d6  mov     rcx, [rax+8]
0x1400246da  mov     ecx, [rcx]; nNumWindows
0x1400246dc  call    cs:__imp_BeginDeferWindowPos
0x1400246e2  mov     rdi, rax
0x1400246e5  test    r12d, r12d
0x1400246e8  jz      short loc_1400246F3
0x1400246ea  mov     rax, [rbx+20h]
0x1400246ee  and     esi, 4
0x1400246f1  jmp     short loc_1400246FE
0x1400246f3  mov     rax, r14
0x1400246f6  and     esi, 4
0x1400246f9  jnz     short loc_1400246FE
0x1400246fb  mov     rax, r15
0x1400246fe  mov     rcx, [rbx]
0x140024701  lea     r8, [rsp+0A8h+pvParam]; pData
0x140024706  mov     qword ptr [rsp+0A8h+pvParam], rdi
0x14002470b  lea     rdx, ?DeferCallback@@YAHPEAX0@Z; pfnCB
0x140024712  mov     qword ptr [rsp+0A8h+pvParam+8], rax
0x140024717  mov     rcx, [rcx+8]; hdsa
0x14002471b  call    DSA_EnumCallback
0x140024720  mov     rcx, rdi; hWinPosInfo
0x140024723  call    cs:__imp_EndDeferWindowPos
0x140024729  test    r12d, r12d
0x14002472c  jz      short loc_140024734
0x14002472e  mov     rcx, [rbx+28h]
0x140024732  jmp     short loc_14002473B
0x140024734  test    esi, esi
0x140024736  jz      short loc_140024741
0x140024738  mov     rcx, rbp; hWnd
0x14002473b  call    cs:__imp_SetForegroundWindow
0x140024741  mov     rcx, [rbx]; hMem
0x140024744  call    ?_DestroySavedWindowPositions@@YAXPEAUWINDOWPOSITIONS@@@Z; _DestroySavedWindowPositions(WINDOWPOSITIONS *)
0x140024749  cmp     [rbx+18h], r15d
0x14002474d  jz      short loc_140024765
0x14002474f  mov     r8, [rbx+10h]; wParam
0x140024753  mov     r9, r14; lParam
0x140024756  mov     rcx, [rbx+8]; hWnd
0x14002475a  mov     edx, 453h; Msg
0x14002475f  call    cs:__imp_PostMessageW
0x140024765  mov     rcx, [rbx+30h]; hEvent
0x140024769  test    rcx, rcx
0x14002476c  jz      short loc_14002477E
0x14002476e  call    cs:__imp_SetEvent
0x140024774  mov     rcx, [rbx+30h]; hObject
0x140024778  call    cs:__imp_CloseHandle
0x14002477e  mov     edx, 38h ; '8'; unsigned __int64
0x140024783  mov     rcx, rbx; void *
0x140024786  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002478b  test    r12d, r12d
0x14002478e  jz      short loc_1400247C0
0x140024790  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r14b
0x140024797  mov     cs:?g_fWinHomeListening@@3JA, r14d; long g_fWinHomeListening
0x14002479e  jz      short loc_1400247C0
0x1400247a0  lea     rdx, [rsp+0A8h+pvParam]
0x1400247a5  mov     r9d, r14d
0x1400247a8  mov     [rsp+0A8h+var_88], rdx
0x1400247ad  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1400247b4  lea     rdx, Shake_RestoreWorker_Stop
0x1400247bb  call    McGenEventWrite_EventWriteTransfer
0x1400247c0  mov     eax, r14d
0x1400247c3  mov     rcx, [rsp+0A8h+var_58]
0x1400247c8  xor     rcx, rsp; StackCookie
0x1400247cb  call    __security_check_cookie
0x1400247d0  add     rsp, 68h
0x1400247d4  pop     r15
0x1400247d6  pop     r14
0x1400247d8  pop     r13
0x1400247da  pop     r12
0x1400247dc  pop     rdi
0x1400247dd  pop     rsi
0x1400247de  pop     rbp
0x1400247df  pop     rbx
0x1400247e0  retn
```

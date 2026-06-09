# CFGControl::CGraphWindow::OnReceiveMessage(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180018f70`
- end: `0x18001969c`
- name: `?OnReceiveMessage@CGraphWindow@CFGControl@@UEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1836`
- prototype: `__int64(CFGControl::CGraphWindow *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, service_task`

## callees

- `0x180004530`
- `0x180016d60`
- `0x180018f70`
- `0x18001d3b0`
- `0x1800204dc`
- `0x1800228c0`
- `0x1800229e8`
- `0x180023a1c`
- `0x18002b218`
- `0x18006fb70`
- `0x18006fe6c`
- `0x18006ff74`
- `0x1800714dc`
- `0x180071554`
- `0x180071720`
- `0x1800718bc`
- `0x180071944`
- `0x180071a3c`
- `0x180071b40`
- `0x180076070`
- `0x180139f68`
- `0x18015e010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180019643`
- `KERNEL32!SetEvent` at `0x180019643`
- `USER32!PeekMessageW` at `0x180019249`
- `USER32!PeekMessageW` at `0x1800192a6`
- `USER32!PeekMessageW` at `0x180019249`
- `USER32!PeekMessageW` at `0x1800192a6`
- `USER32!IsWindowVisible` at `0x180018fd8`
- `USER32!IsWindowVisible` at `0x180019431`
- `USER32!IsWindowVisible` at `0x180019505`
- `USER32!IsWindowVisible` at `0x180018fd8`
- `USER32!IsWindowVisible` at `0x180019431`
- `USER32!IsWindowVisible` at `0x180019505`
- `USER32!InvalidateRect` at `0x18001953a`
- `USER32!InvalidateRect` at `0x18001953a`
- `USER32!SetWindowPos` at `0x18001900c`
- `USER32!SetWindowPos` at `0x18001947b`
- `USER32!SetWindowPos` at `0x18001900c`
- `USER32!SetWindowPos` at `0x18001947b`
- `USER32!SetForegroundWindow` at `0x180019021`
- `USER32!SetForegroundWindow` at `0x180019021`
- `USER32!DefWindowProcW` at `0x18001956e`
- `USER32!DefWindowProcW` at `0x18001956e`
- `USER32!ReplyMessage` at `0x1800195ea`
- `USER32!ReplyMessage` at `0x1800195ea`
- `USER32!PostMessageW` at `0x180019090`
- `USER32!PostMessageW` at `0x180019524`
- `USER32!PostMessageW` at `0x180019090`
- `USER32!PostMessageW` at `0x180019524`
- `USER32!KillTimer` at `0x180019194`
- `USER32!KillTimer` at `0x180019194`
- `USER32!InSendMessage` at `0x18001906b`
- `USER32!InSendMessage` at `0x18001906b`
- `ole32!CoTaskMemFree` at `0x18001931f`
- `ole32!CoTaskMemFree` at `0x18001931f`

## pseudocode

```c
__int64 __fastcall CFGControl::CGraphWindow::OnReceiveMessage(
        CFGControl::CGraphWindow *this,
        HWND a2,
        UINT a3,
        WPARAM a4,
        LPARAM lParam)
{
  BOOL v9; // eax
  UINT uFlags; // ecx
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // ebx
  CFGControl *v15; // rcx
  struct IPin v16; // rax
  struct IPinVtbl **v17; // rcx
  _QWORD *v18; // rdi
  struct IPinVtbl **v19; // rbx
  BOOL v20; // eax
  int v21; // edx
  unsigned int v22; // ebx
  __int64 v23; // rbx
  __int64 v24; // rcx
  int Filter; // eax
  struct IPin *v26; // [rsp+40h] [rbp-68h] BYREF
  struct tagMSG Msg; // [rsp+48h] [rbp-60h] BYREF

  if ( a3 == 129 )
  {
    CResourceManager::OnThreadInit((CResourceManager *)(*((_QWORD *)this + 24) + 448LL), a2);
    goto LABEL_3;
  }
  if ( a3 == 1034 )
  {
    if ( *(_DWORD *)(a4 + 16) == 2 )
    {
      v22 = (*(__int64 (__fastcall **)(_QWORD))(a4 + 8))(*(_QWORD *)a4);
      operator delete((void *)a4);
      return v22;
    }
    v23 = **((_QWORD **)this + 24);
    ReplyMessage(0);
    v24 = *(_QWORD *)a4;
    if ( *(_DWORD *)(a4 + 16) )
      Filter = CoCreateFilter(v24, lParam);
    else
      Filter = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *, LPARAM))(*(_QWORD *)v24 + 64LL))(
                 v24,
                 *(_QWORD *)(v23 + 632),
                 0,
                 &IID_IBaseFilter,
                 lParam);
    *(_DWORD *)(v23 + 496) = Filter;
    SetEvent(*(HANDLE *)(v23 + 504));
    return 0;
  }
  if ( a3 > 0x311 )
  {
    switch ( a3 )
    {
      case 0x400u:
        CResourceManager::OnThreadMessage((CResourceManager *)(*((_QWORD *)this + 24) + 448LL));
        goto LABEL_3;
      case 0x401u:
        v19 = (struct IPinVtbl **)lParam;
        CFGControl::WorkerRepaint(*((CFGControl **)this + 24), a4, (struct IPin *)lParam);
        if ( !lParam )
          return 0;
        goto LABEL_53;
      case 0x403u:
        v19 = (struct IPinVtbl **)lParam;
        CFGControl::WorkerActivate(*((CFGControl **)this + 24), (struct IBaseFilter *)lParam, a4);
        if ( !lParam )
          return 0;
LABEL_53:
        v16.lpVtbl = *v19;
        v17 = v19;
        goto LABEL_54;
      case 0x404u:
        CFGControl::WorkerRestart(*((CFGControl **)this + 24), a4);
        return 0;
      case 0x405u:
        CFGControl::WorkerRecue(*((CFGControl **)this + 24), a4);
        return 0;
      case 0x406u:
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, a2, 0x400u, 0x40Eu, 1u) )
        {
          if ( Msg.hwnd )
            (*(void (__fastcall **)(CFGControl::CGraphWindow *, HWND, _QWORD, WPARAM, LPARAM))(*(_QWORD *)this + 104LL))(
              this,
              Msg.hwnd,
              Msg.message,
              Msg.wParam,
              Msg.lParam);
        }
        return 0;
      case 0x407u:
        v14 = lParam;
        v15 = (CFGControl *)*((_QWORD *)this + 24);
        if ( (_DWORD)lParam )
        {
          v18 = (_QWORD *)a4;
          CFGControl::WorkerDisplayChanged(v15, (struct IPin **)a4, lParam);
          do
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 16LL))(*v18);
            ++v18;
            --v14;
          }
          while ( v14 );
          CoTaskMemFree((LPVOID)a4);
        }
        else
        {
          v26 = (struct IPin *)a4;
          CFGControl::WorkerDisplayChanged(v15, &v26, 1u);
          if ( a4 )
          {
            v16.lpVtbl = *(struct IPinVtbl **)a4;
            v17 = (struct IPinVtbl **)a4;
LABEL_54:
            ((void (__fastcall *)(struct IPinVtbl **))v16.lpVtbl->Release)(v17);
          }
        }
        break;
      case 0x409u:
        return ((unsigned int (__fastcall *)(LPARAM))a4)(lParam);
      case 0x40Bu:
        CFilterGraph::DeleteSpareList(**((_QWORD **)this + 24), a4);
        return 0;
      case 0x40Du:
        return CFGControl::WorkerFrameStepFinished(*((CFGControl **)this + 24), lParam);
      case 0x40Eu:
        return CFGControl::WorkerSkipFrames(*((CFGControl **)this + 24), a4, (struct IFrameSkipResultCallback *)lParam);
      default:
        goto LABEL_3;
    }
    return 0;
  }
  if ( a3 == 785 )
  {
LABEL_18:
    if ( InSendMessage() )
    {
      PostMessageW(*((HWND *)this + 2), a3, a4, lParam);
    }
    else
    {
      v13 = *((_QWORD *)this + 24);
      if ( !*(_DWORD *)(v13 + 216) )
        CFGControl::CImplVideoWindow::NotifyOwnerMessage(
          (CFGControl::CImplVideoWindow *)(v13 + 1152),
          *((_QWORD *)this + 2),
          a3,
          a4,
          lParam);
    }
    return 0;
  }
  if ( a3 > 0x7E )
  {
    if ( a3 == 275 )
    {
      if ( a4 == 1 )
      {
        CAutoMsgMutex::CAutoMsgMutex(
          (CAutoMsgMutex *)&v26,
          *(struct CMsgMutex **)(*((_QWORD *)this + 24) + 16LL),
          0xFFFFFFFF);
        KillTimer(a2, 1u);
        CFGControl::CheckCued(*((CFGControl **)this + 24));
        CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v26);
        return 0;
      }
    }
    else if ( a3 == 536 )
    {
      if ( a4 <= 0x12 )
      {
        v12 = 262596;
        if ( _bittest64(&v12, a4) )
        {
          CFGControl::HibernateResumeGraph(*((CFGControl **)this + 24));
          return 0;
        }
      }
      if ( a4 - 4 <= 1 )
      {
        CFGControl::HibernateSuspendGraph(*((CFGControl **)this + 24));
        return 0;
      }
    }
    else if ( a3 == 537 && ((a4 - 0x8000) & 0xFFFFFFFFFFFFFFFBuLL) == 0 && *(_DWORD *)(lParam + 4) == 5 )
    {
      CFGControl::DeviceChangeMsg(*((CFGControl **)this + 24), a4, (struct _DEV_BROADCAST_DEVICEINTERFACE_W *)lParam);
    }
  }
  else
  {
    switch ( a3 )
    {
      case 0x7Eu:
        goto LABEL_18;
      case 2u:
        if ( !*((_DWORD *)this + 50) )
        {
          *((_DWORD *)this + 50) = 1;
          CResourceManager::OnThreadExit((CResourceManager *)(*((_QWORD *)this + 24) + 448LL), a2);
        }
        break;
      case 0x15u:
      case 0x1Bu:
        goto LABEL_18;
    }
  }
LABEL_3:
  if ( (*(unsigned int (__fastcall **)(CFGControl::CGraphWindow *, _QWORD, WPARAM, LPARAM))(*(_QWORD *)this + 96LL))(
         this,
         a3,
         a4,
         lParam) )
  {
    return 0;
  }
  if ( a3 == *((_DWORD *)this + 17) )
  {
    v9 = IsWindowVisible(a2);
    uFlags = 83;
    if ( !v9 )
      uFlags = 67;
    SetWindowPos(a2, 0, 0, 0, 0, 0, uFlags);
    if ( a4 == 1 )
      SetForegroundWindow(a2);
    return 1;
  }
  if ( a3 != *((_DWORD *)this + 18) )
  {
    if ( a3 != *((_DWORD *)this + 19) )
    {
      if ( a3 <= 0x15 )
      {
        switch ( a3 )
        {
          case 0x15u:
            InvalidateRect(a2, 0, 0);
            return 1;
          case 3u:
            if ( IsWindowVisible(*((HWND *)this + 2)) )
              PostMessageW(*((HWND *)this + 2), 0xFu, 0, 0);
            break;
          case 5u:
            (*(void (__fastcall **)(CFGControl::CGraphWindow *, _QWORD, _QWORD))(*(_QWORD *)this + 40LL))(
              this,
              (unsigned __int16)lParam,
              WORD1(lParam));
            return 0;
          case 0x10u:
            (*(void (__fastcall **)(CFGControl::CGraphWindow *))(*(_QWORD *)this + 48LL))(this);
            return 0;
        }
        return DefWindowProcW(a2, a3, a4, lParam);
      }
      if ( a3 != 783 )
      {
        if ( a3 == 785 )
        {
          (**(void (__fastcall ***)(CFGControl::CGraphWindow *, WPARAM, __int64))this)(this, a4, 785);
          return 0;
        }
        return DefWindowProcW(a2, a3, a4, lParam);
      }
    }
    return (**(__int64 (__fastcall ***)(CFGControl::CGraphWindow *, _QWORD, __int64))this)(
             this,
             *((_QWORD *)this + 2),
             783);
  }
  v20 = IsWindowVisible(a2);
  v21 = 67;
  if ( a4 != 1 )
    v21 = 3;
  SetWindowPos(a2, (HWND)((a4 == 1) - 2LL), 0, 0, 0, 0, v21 | (v20 ? 0x10 : 0));
  return 1;
}

```

## disassembly

```asm
0x180018f70  push    rbx
0x180018f72  push    rbp
0x180018f73  push    rsi
0x180018f74  push    rdi
0x180018f75  sub     rsp, 88h
0x180018f7c  mov     rsi, r9
0x180018f7f  mov     ebx, r8d
0x180018f82  mov     rbp, rdx
0x180018f85  mov     rdi, rcx
0x180018f88  cmp     r8d, 81h
0x180018f8f  jnz     loc_180019037
0x180018f95  mov     rcx, [rcx+0C0h]
0x180018f9c  add     rcx, 1C0h; this
0x180018fa3  call    ?OnThreadInit@CResourceManager@@QEAAJPEAUHWND__@@@Z; CResourceManager::OnThreadInit(HWND__ *)
0x180018fa8  mov     rax, [rdi]; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x180018fab  mov     r8, rsi
0x180018fae  mov     r9, [rsp+0A8h+lParam]
0x180018fb6  mov     edx, ebx
0x180018fb8  mov     rcx, rdi
0x180018fbb  mov     rax, [rax+60h]
0x180018fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fc4  test    eax, eax
0x180018fc6  jnz     loc_18001964F
0x180018fcc  cmp     ebx, [rdi+44h]
0x180018fcf  jnz     loc_180019429
0x180018fd5  mov     rcx, rbp; hWnd
0x180018fd8  call    cs:__imp_IsWindowVisible
0x180018fdf  nop     dword ptr [rax+rax+00h]
0x180018fe4  mov     ecx, 53h ; 'S'
0x180018fe9  mov     edx, 43h ; 'C'
0x180018fee  test    eax, eax
0x180018ff0  cmovz   ecx, edx
0x180018ff3  xor     eax, eax
0x180018ff5  mov     [rsp+0A8h+uFlags], ecx; uFlags
0x180018ff9  xor     r9d, r9d; Y
0x180018ffc  mov     [rsp+0A8h+cy], eax; cy
0x180019000  mov     rcx, rbp; hWnd
0x180019003  xor     r8d, r8d; X
0x180019006  mov     [rsp+0A8h+wRemoveMsg], eax; cx
0x18001900a  xor     edx, edx; hWndInsertAfter
0x18001900c  call    cs:__imp_SetWindowPos
0x180019013  nop     dword ptr [rax+rax+00h]
0x180019018  cmp     rsi, 1
0x18001901c  jnz     short loc_18001902D
0x18001901e  mov     rcx, rbp; hWnd
0x180019021  call    cs:__imp_SetForegroundWindow
0x180019028  nop     dword ptr [rax+rax+00h]
0x18001902d  mov     eax, 1
0x180019032  jmp     loc_180019651
0x180019037  cmp     ebx, 40Ah
0x18001903d  jz      loc_1800195B8
0x180019043  cmp     ebx, 311h
0x180019049  ja      loc_1800191F7
0x18001904f  jz      short loc_18001906B
0x180019051  cmp     ebx, 7Eh ; '~'
0x180019054  ja      short loc_1800190D0
0x180019056  jz      short loc_18001906B
0x180019058  cmp     ebx, 2
0x18001905b  jz      short loc_1800190A1
0x18001905d  cmp     ebx, 15h
0x180019060  jz      short loc_18001906B
0x180019062  cmp     ebx, 1Bh
0x180019065  jnz     def_180019218; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x18001906b  call    cs:__imp_InSendMessage
0x180019072  nop     dword ptr [rax+rax+00h]
0x180019077  test    eax, eax
0x180019079  jz      loc_1800191BB
0x18001907f  mov     r9, [rsp+0A8h+lParam]; lParam
0x180019087  mov     r8, rsi; wParam
0x18001908a  mov     rcx, [rdi+10h]; hWnd
0x18001908e  mov     edx, ebx; Msg
0x180019090  call    cs:__imp_PostMessageW
0x180019097  nop     dword ptr [rax+rax+00h]
0x18001909c  jmp     loc_18001964F
0x1800190a1  cmp     dword ptr [rcx+0C8h], 0
0x1800190a8  jnz     def_180019218; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x1800190ae  mov     dword ptr [rcx+0C8h], 1
0x1800190b8  mov     rcx, [rcx+0C0h]
0x1800190bf  add     rcx, 1C0h; this
0x1800190c6  call    ?OnThreadExit@CResourceManager@@QEAAJPEAUHWND__@@@Z; CResourceManager::OnThreadExit(HWND__ *)
0x1800190cb  jmp     def_180019218; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x1800190d0  mov     eax, ebx
0x1800190d2  sub     eax, 113h
0x1800190d7  jz      loc_180019169
0x1800190dd  sub     eax, 105h
0x1800190e2  jz      short loc_180019128
0x1800190e4  cmp     eax, 1
0x1800190e7  jnz     def_180019218; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x1800190ed  lea     rax, [r9-8000h]
0x1800190f4  test    rax, 0FFFFFFFFFFFFFFFBh
0x1800190fa  jnz     def_180019218; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x180019100  mov     rcx, [rsp+0A8h+lParam]
0x180019108  cmp     dword ptr [rcx+4], 5
0x18001910c  jnz     def_180019218; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x180019112  mov     r8, rcx; struct _DEV_BROADCAST_DEVICEINTERFACE_W *
0x180019115  mov     edx, esi; unsigned int
0x180019117  mov     rcx, [rdi+0C0h]; this
0x18001911e  call    ?DeviceChangeMsg@CFGControl@@QEAAXKPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z; CFGControl::DeviceChangeMsg(ulong,_DEV_BROADCAST_DEVICEINTERFACE_W *)
0x180019123  jmp     def_180019218; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x180019128  cmp     rsi, 12h
0x18001912c  ja      short loc_18001914A
0x18001912e  mov     eax, 401C4h
0x180019133  bt      rax, rsi
0x180019137  jnb     short loc_18001914A
0x180019139  mov     rcx, [rcx+0C0h]; this
0x180019140  call    ?HibernateResumeGraph@CFGControl@@QEAAXXZ; CFGControl::HibernateResumeGraph(void)
0x180019145  jmp     loc_18001964F
0x18001914a  lea     rax, [r9-4]
0x18001914e  cmp     rax, 1
0x180019152  ja      def_180019218; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x180019158  mov     rcx, [rcx+0C0h]; this
0x18001915f  call    ?HibernateSuspendGraph@CFGControl@@QEAAXXZ; CFGControl::HibernateSuspendGraph(void)
0x180019164  jmp     loc_18001964F
0x180019169  cmp     rsi, 1
0x18001916d  jnz     def_180019218; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x180019173  mov     rdx, [rcx+0C0h]
0x18001917a  mov     r8d, 0FFFFFFFFh; unsigned int
0x180019180  lea     rcx, [rsp+0A8h+var_68]; this
0x180019185  mov     rdx, [rdx+10h]; struct CMsgMutex *
0x180019189  call    ??0CAutoMsgMutex@@QEAA@PEAVCMsgMutex@@K@Z; CAutoMsgMutex::CAutoMsgMutex(CMsgMutex *,ulong)
0x18001918e  mov     rdx, rsi; uIDEvent
0x180019191  mov     rcx, rbp; hWnd
0x180019194  call    cs:__imp_KillTimer
0x18001919b  nop     dword ptr [rax+rax+00h]
0x1800191a0  mov     rcx, [rdi+0C0h]; this
0x1800191a7  call    ?CheckCued@CFGControl@@QEAAJXZ; CFGControl::CheckCued(void)
0x1800191ac  lea     rcx, [rsp+0A8h+var_68]; this
0x1800191b1  call    ??1CAutoMsgMutex@@QEAA@XZ; CAutoMsgMutex::~CAutoMsgMutex(void)
0x1800191b6  jmp     loc_18001964F
0x1800191bb  mov     rcx, [rdi+0C0h]
0x1800191c2  cmp     dword ptr [rcx+0D8h], 0
0x1800191c9  jnz     loc_18001964F
0x1800191cf  mov     rax, [rsp+0A8h+lParam]
0x1800191d7  add     rcx, 480h; this
0x1800191de  mov     rdx, [rdi+10h]; __int64
0x1800191e2  mov     r9, rsi; __int64
0x1800191e5  mov     r8d, ebx; int
0x1800191e8  mov     qword ptr [rsp+0A8h+wRemoveMsg], rax; __int64
0x1800191ed  call    ?NotifyOwnerMessage@CImplVideoWindow@CFGControl@@UEAAJ_JJ00@Z; CFGControl::CImplVideoWindow::NotifyOwnerMessage(__int64,long,__int64,__int64)
0x1800191f2  jmp     loc_18001964F
0x1800191f7  lea     eax, [r8-400h]; switch 15 cases
0x1800191fe  cmp     eax, 0Eh
0x180019201  ja      def_180019218; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x180019207  lea     rcx, __ImageBase
0x18001920e  mov     eax, ds:(jpt_180019218 - 180000000h)[rcx+rax*4]
0x180019215  add     rax, rcx
0x180019218  jmp     rax; switch jump
0x18001921e  xorps   xmm0, xmm0; jumptable 0000000180019218 case 1030
0x180019221  mov     [rsp+0A8h+wRemoveMsg], 1; wRemoveMsg
0x180019229  mov     r9d, 40Eh; wMsgFilterMax
0x18001922f  lea     rcx, [rsp+0A8h+Msg]; lpMsg
0x180019234  mov     r8d, 400h; wMsgFilterMin
0x18001923a  movups  xmmword ptr [rsp+0A8h+Msg.hwnd], xmm0
0x18001923f  movups  xmmword ptr [rsp+0A8h+Msg.wParam], xmm0
0x180019244  movups  xmmword ptr [rsp+0A8h+Msg.time], xmm0
0x180019249  call    cs:__imp_PeekMessageW
0x180019250  nop     dword ptr [rax+rax+00h]
0x180019255  test    eax, eax
0x180019257  jz      loc_18001964F
0x18001925d  mov     rdx, [rsp+0A8h+Msg.hwnd]
0x180019262  test    rdx, rdx
0x180019265  jz      short loc_18001928A
0x180019267  mov     rcx, [rsp+0A8h+Msg.lParam]
0x18001926c  mov     rax, [rdi]
0x18001926f  mov     r9, [rsp+0A8h+Msg.wParam]
0x180019274  mov     r8d, [rsp+0A8h+Msg.message]
0x180019279  mov     qword ptr [rsp+0A8h+wRemoveMsg], rcx
0x18001927e  mov     rcx, rdi
0x180019281  mov     rax, [rax+68h]
0x180019285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001928a  mov     r9d, 40Eh; wMsgFilterMax
0x180019290  mov     [rsp+0A8h+wRemoveMsg], 1; wRemoveMsg
0x180019298  mov     r8d, 400h; wMsgFilterMin
0x18001929e  lea     rcx, [rsp+0A8h+Msg]; lpMsg
0x1800192a3  mov     rdx, rbp; hWnd
0x1800192a6  call    cs:__imp_PeekMessageW
0x1800192ad  nop     dword ptr [rax+rax+00h]
0x1800192b2  test    eax, eax
0x1800192b4  jnz     short loc_18001925D
0x1800192b6  jmp     loc_18001964F
0x1800192bb  mov     ebx, dword ptr [rsp+0A8h+lParam]; jumptable 0000000180019218 case 1031
0x1800192c2  mov     rcx, [rdi+0C0h]; this
0x1800192c9  test    ebx, ebx
0x1800192cb  jnz     short loc_1800192F6
0x1800192cd  mov     r8d, 1; unsigned int
0x1800192d3  mov     [rsp+0A8h+var_68], rsi
0x1800192d8  lea     rdx, [rsp+0A8h+var_68]; struct IPin **
0x1800192dd  call    ?WorkerDisplayChanged@CFGControl@@QEAA_JPEAPEAUIPin@@K@Z; CFGControl::WorkerDisplayChanged(IPin * *,ulong)
0x1800192e2  test    rsi, rsi
0x1800192e5  jz      loc_18001964F
0x1800192eb  mov     rax, [rsi]
0x1800192ee  mov     rcx, rsi
0x1800192f1  jmp     loc_18001938F
0x1800192f6  mov     r8d, ebx; unsigned int
0x1800192f9  mov     rdx, rsi; struct IPin **
0x1800192fc  mov     rdi, rsi
0x1800192ff  call    ?WorkerDisplayChanged@CFGControl@@QEAA_JPEAPEAUIPin@@K@Z; CFGControl::WorkerDisplayChanged(IPin * *,ulong)
0x180019304  mov     rcx, [rdi]
0x180019307  mov     rax, [rcx]
0x18001930a  mov     rax, [rax+10h]
0x18001930e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019313  lea     rdi, [rdi+8]
0x180019317  add     ebx, 0FFFFFFFFh
0x18001931a  jnz     short loc_180019304
0x18001931c  mov     rcx, rsi; pv
0x18001931f  call    cs:__imp_CoTaskMemFree
0x180019326  nop     dword ptr [rax+rax+00h]
0x18001932b  jmp     loc_18001964F
0x180019330  mov     rbx, [rsp+0A8h+lParam]; jumptable 0000000180019218 case 1025
0x180019338  mov     edx, esi; unsigned int
0x18001933a  mov     rcx, [rdi+0C0h]; this
0x180019341  mov     r8, rbx; struct IPin *
0x180019344  call    ?WorkerRepaint@CFGControl@@QEAA_JKPEAUIPin@@@Z; CFGControl::WorkerRepaint(ulong,IPin *)
0x180019349  test    rbx, rbx
0x18001934c  jnz     short loc_180019389
0x18001934e  jmp     loc_18001964F
0x180019353  mov     rcx, [rdi+0C0h]; jumptable 0000000180019218 case 1029
0x18001935a  mov     edx, esi; unsigned int
0x18001935c  call    ?WorkerRecue@CFGControl@@QEAA_JK@Z; CFGControl::WorkerRecue(ulong)
0x180019361  jmp     loc_18001964F
0x180019366  mov     rbx, [rsp+0A8h+lParam]; jumptable 0000000180019218 case 1027
0x18001936e  mov     r8d, esi; int
0x180019371  mov     rcx, [rdi+0C0h]; this
0x180019378  mov     rdx, rbx; struct IBaseFilter *
0x18001937b  call    ?WorkerActivate@CFGControl@@QEAA_JPEAUIBaseFilter@@H@Z; CFGControl::WorkerActivate(IBaseFilter *,int)
0x180019380  test    rbx, rbx
0x180019383  jz      loc_18001964F
0x180019389  mov     rax, [rbx]
0x18001938c  mov     rcx, rbx
0x18001938f  mov     rax, [rax+10h]
0x180019393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019398  jmp     loc_18001964F
0x18001939d  mov     rcx, [rdi+0C0h]; jumptable 0000000180019218 case 1028
0x1800193a4  mov     edx, esi; int
0x1800193a6  call    ?WorkerRestart@CFGControl@@QEAA_JH@Z; CFGControl::WorkerRestart(int)
0x1800193ab  jmp     loc_18001964F
0x1800193b0  mov     rcx, [rdi+0C0h]; jumptable 0000000180019218 case 1024
0x1800193b7  add     rcx, 1C0h; this
0x1800193be  call    ?OnThreadMessage@CResourceManager@@QEAAJXZ; CResourceManager::OnThreadMessage(void)
0x1800193c3  jmp     def_180019218; jumptable 0000000180019218 default case, cases 1026,1032,1034,1036
0x1800193c8  mov     rcx, [rsp+0A8h+lParam]; jumptable 0000000180019218 case 1033
0x1800193d0  mov     rax, rsi
0x1800193d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193d8  mov     eax, eax
0x1800193da  jmp     loc_180019651
0x1800193df  mov     rcx, [rdi+0C0h]; jumptable 0000000180019218 case 1035
0x1800193e6  mov     rdx, rsi
0x1800193e9  mov     rcx, [rcx]
0x1800193ec  call    ?DeleteSpareList@CFilterGraph@@AEAAJAEAV?$CGenericList@USpare@CFilterGraph@@@@@Z; CFilterGraph::DeleteSpareList(CGenericList<CFilterGraph::Spare> &)
0x1800193f1  jmp     loc_18001964F
0x1800193f6  mov     r8, [rsp+0A8h+lParam]; jumptable 0000000180019218 case 1038
0x1800193fe  mov     edx, esi; unsigned int
0x180019400  mov     rcx, [rdi+0C0h]; this
0x180019407  call    ?WorkerSkipFrames@CFGControl@@QEAA_JKPEAUIFrameSkipResultCallback@@@Z; CFGControl::WorkerSkipFrames(ulong,IFrameSkipResultCallback *)
0x18001940c  jmp     loc_180019651
0x180019411  mov     edx, dword ptr [rsp+0A8h+lParam]; jumptable 0000000180019218 case 1037
0x180019418  mov     rcx, [rdi+0C0h]; this
0x18001941f  call    ?WorkerFrameStepFinished@CFGControl@@QEAA_JK@Z; CFGControl::WorkerFrameStepFinished(ulong)
0x180019424  jmp     loc_180019651
0x180019429  cmp     ebx, [rdi+48h]
0x18001942c  jnz     short loc_180019491
0x18001942e  mov     rcx, rbp; hWnd
0x180019431  call    cs:__imp_IsWindowVisible
0x180019438  nop     dword ptr [rax+rax+00h]
0x18001943d  neg     eax
0x18001943f  mov     edx, 43h ; 'C'
0x180019444  mov     eax, 3
0x180019449  sbb     ecx, ecx
0x18001944b  and     ecx, 10h
0x18001944e  cmp     rsi, 1
0x180019452  cmovnz  edx, eax
0x180019455  xor     eax, eax
0x180019457  or      ecx, edx
0x180019459  mov     edx, eax
0x18001945b  mov     [rsp+0A8h+uFlags], ecx; uFlags
0x18001945f  cmp     rsi, 1
0x180019463  mov     [rsp+0A8h+cy], eax; cy
0x180019467  mov     rcx, rbp; hWnd
0x18001946a  setz    dl
0x18001946d  mov     [rsp+0A8h+wRemoveMsg], eax; cx
0x180019471  add     rdx, 0FFFFFFFFFFFFFFFEh; hWndInsertAfter
0x180019475  xor     r9d, r9d; Y
0x180019478  xor     r8d, r8d; X
0x18001947b  call    cs:__imp_SetWindowPos
0x180019482  nop     dword ptr [rax+rax+00h]
0x180019487  mov     eax, 1
0x18001948c  jmp     loc_180019651
0x180019491  cmp     ebx, [rdi+4Ch]
0x180019494  jnz     short loc_1800194A1
0x180019496  mov     r8d, 30Fh
0x18001949c  jmp     loc_18001959B
0x1800194a1  cmp     ebx, 15h
0x1800194a4  ja      loc_180019550
0x1800194aa  jz      loc_180019532
0x1800194b0  cmp     ebx, 3
0x1800194b3  jz      short loc_180019501
0x1800194b5  cmp     ebx, 5
0x1800194b8  jz      short loc_1800194D7
0x1800194ba  cmp     ebx, 10h
0x1800194bd  jnz     loc_18001955E
  ... truncated ...
```

# CThreadInputMgr::SetFocusEventHook(void)

- ea: `0x180029200`
- end: `0x180029505`
- name: `?SetFocusEventHook@CThreadInputMgr@@AEAAJXZ`
- size: `773`
- prototype: `__int64 __fastcall(CThreadInputMgr *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18000cb3c`

## callees

- `0x1800139a4`
- `0x180018714`
- `0x180019cfc`
- `0x180028ec8`
- `0x180029200`
- `0x180029630`
- `0x180029668`
- `0x1800297f0`
- `0x180029c68`
- `0x18003a930`
- `0x180040694`
- `0x1800879c4`
- `0x18008c138`
- `0x18009eaea`
- `0x1800a42a0`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800294cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800294cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029364`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800294c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029364`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800294c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029269`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029269`
- `USER32!GetWindowThreadProcessId` at `0x18002935c`
- `USER32!GetWindowThreadProcessId` at `0x18002935c`
- `USER32!GetGUIThreadInfo` at `0x180029346`
- `USER32!GetGUIThreadInfo` at `0x180029346`
- `USER32!MakeThreadTSFEventAware` at `0x1800294a9`
- `USER32!MakeThreadTSFEventAware` at `0x1800294a9`
- `USER32!SetWinEventHook` at `0x1800294f6`
- `USER32!SetWinEventHook` at `0x1800294f6`

## pseudocode

```c
__int64 __fastcall CThreadInputMgr::SetFocusEventHook(CThreadInputMgr *this)
{
  struct ICiceroEventSink *v2; // r13
  __int64 v3; // rbx
  unsigned __int64 v4; // rsi
  int v5; // edx
  _QWORD *v6; // r14
  void **v7; // rax
  DWORD WindowThreadProcessId; // ebx
  struct IDocumentInputManagerPrivate *PendingFocusDocInputMgr; // rax
  __int64 v11; // rcx
  DWORD v12; // ebp
  DWORD v13; // r15d
  int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rax
  DWORD v17; // r9d
  DWORD v18; // r8d
  DWORD v19; // eax
  DWORD v20; // eax
  _DWORD *v21; // rax
  _DWORD *v22; // r12
  __int64 v23; // r8
  int v24; // eax
  unsigned int v25; // r8d
  DWORD idThread; // ebx
  DWORD idProcess; // eax
  struct tagGUITHREADINFO pgui; // [rsp+40h] [rbp-A8h] BYREF

  if ( !*((_QWORD *)this + 370) )
  {
    *((_DWORD *)this + 917) &= ~0x200u;
    v2 = (CThreadInputMgr *)((char *)this + 80);
    v3 = *((_QWORD *)this + 26);
    *((_QWORD *)this + 370) = 0;
    v4 = ((unsigned __int64)this + 80) & -(__int64)(this != 0);
    v6 = LocalAlloc(0x40u, 0x18u);
    if ( v6 )
    {
      v7 = CVoidPtrArray::Append((CVoidPtrArray *)(v3 + 320), v5);
      if ( v7 )
      {
        *v7 = v6;
        v12 = -2147483646;
        *v6 = v4;
        v13 = -2147483643;
        *((_DWORD *)v6 + 2) = -2147483646;
        *((_DWORD *)v6 + 4) = 1;
        v14 = 0;
        *((_DWORD *)v6 + 3) = -2147483643;
        while ( v14 < *(_DWORD *)(v3 + 304) )
        {
          v15 = *(_DWORD *)(v3 + 308) * v14;
          v16 = *(_QWORD *)(v3 + 296);
          if ( *(_DWORD *)(v15 + v16 + 16) == 1 )
          {
            v17 = *(_DWORD *)(v15 + v16 + 12);
            if ( v12 <= v17 )
            {
              v18 = *(_DWORD *)(v15 + v16 + 8);
              if ( v13 >= v18 )
              {
                ++*(_DWORD *)(v15 + v16 + 20);
                v19 = v17 + 1;
                if ( v12 < v18 )
                  v19 = v12;
                v12 = v19;
                v20 = v18 - 1;
                if ( v13 > v17 )
                  v20 = v13;
                v13 = v20;
                if ( v12 >= v20 )
                {
                  v12 = v20 + 1;
                  break;
                }
              }
            }
          }
          ++v14;
        }
        if ( v12 <= v13 )
        {
          v21 = CVoidStructArray::Append((CVoidStructArray *)(v3 + 288), 1);
          v22 = v21;
          if ( !v21 )
          {
            tagSYSTHREAD::UnadviseCiceroEvents((tagSYSTHREAD *)v3, (unsigned __int64)v6);
            return *((_QWORD *)this + 370) == 0 ? 0x80004005 : 0;
          }
          v21[5] = 1;
          v21[2] = v12;
          v21[3] = v13;
          v21[4] = 1;
          if ( (*(_DWORD *)(v3 + 192) & 0x100) != 0 )
          {
            v23 = 0;
            while ( v12 <= v13 )
            {
              v24 = TSFRangeFromEvent(v12, 0, v23);
              if ( !v24 )
              {
                LODWORD(v23) = 0;
                break;
              }
              v23 = v24 | v25;
              ++v12;
            }
            *((_DWORD *)v6 + 5) = v23;
            MakeThreadTSFEventAware((unsigned int)v23);
            *(_QWORD *)v22 = 0;
            v22[6] = *((_DWORD *)v6 + 5);
          }
          else
          {
            idThread = GetCurrentThreadId();
            idProcess = GetCurrentProcessId();
            *(_QWORD *)v22 = SetWinEventHook(v12, v13, g_hInst, WinEventProc, idProcess, idThread, 4u);
          }
        }
        *((_QWORD *)this + 370) = v6;
        memset_0(&pgui, 0, sizeof(pgui));
        pgui.cbSize = 72;
        GetGUIThreadInfo(0, &pgui);
        if ( pgui.hwndFocus
          && (WindowThreadProcessId = GetWindowThreadProcessId(pgui.hwndFocus, 0),
              GetCurrentThreadId() == WindowThreadProcessId) )
        {
          CThreadInputMgr::UpdateFocusHwnd(this, pgui.hwndFocus);
          PendingFocusDocInputMgr = CThreadInputMgr::GetPendingFocusDocInputMgr(this);
          CThreadInputMgr::_SetFocus(this, PendingFocusDocInputMgr, 0);
          if ( CThreadInputMgr::HasDocumentFocus(this) )
            CThreadInputMgr::UpdateIMMStatus(v11, 2);
        }
        else
        {
          CThreadInputMgr::_SetFocus(this, 0, 0);
        }
        if ( CThreadInputMgr::IsUWPApp(this) )
          tagSYSTHREAD::AdviseCiceroEvents(
            *((tagSYSTHREAD **)this + 26),
            0x7FFFFF00u,
            0x7FFFFF01u,
            1,
            v2,
            (unsigned __int64 *)this + 377);
        else
          CThreadInputMgr::_StartAccFocusTracking(this);
        return *((_QWORD *)this + 370) == 0 ? 0x80004005 : 0;
      }
      cicMemFree(v6);
    }
    return *((_QWORD *)this + 370) == 0 ? 0x80004005 : 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180029200  push    rbx
0x180029202  push    rbp
0x180029203  push    rsi
0x180029204  push    rdi
0x180029205  push    r12
0x180029207  push    r13
0x180029209  push    r14
0x18002920b  push    r15
0x18002920d  sub     rsp, 0A8h
0x180029214  mov     rax, cs:__security_cookie
0x18002921b  xor     rax, rsp
0x18002921e  mov     [rsp+0E8h+var_58], rax
0x180029226  cmp     qword ptr [rcx+0B90h], 0
0x18002922e  mov     rdi, rcx
0x180029231  jnz     loc_1800292EE
0x180029237  btr     dword ptr [rcx+0E54h], 9
0x18002923f  lea     r13, [rcx+50h]
0x180029243  mov     rbx, [rcx+0D0h]
0x18002924a  mov     rax, rcx
0x18002924d  mov     edx, 18h; uBytes
0x180029252  mov     qword ptr [rcx+0B90h], 0
0x18002925d  neg     rax
0x180029260  sbb     rsi, rsi
0x180029263  lea     ecx, [rdx+28h]; uFlags
0x180029266  and     rsi, r13
0x180029269  call    cs:__imp_LocalAlloc
0x18002926f  mov     r14, rax
0x180029272  test    rax, rax
0x180029275  jz      short loc_1800292B7
0x180029277  lea     rcx, [rbx+140h]; this
0x18002927e  call    ?Append@CVoidPtrArray@@QEAAPEAPEAXH@Z; CVoidPtrArray::Append(int)
0x180029283  test    rax, rax
0x180029286  jnz     loc_1800293B6
0x18002928c  mov     rcx, r14
0x18002928f  call    cicMemFree
0x180029294  jmp     short loc_1800292B7
0x180029296  xor     r8d, r8d; int
0x180029299  xor     edx, edx; struct IDocumentInputManagerPrivate *
0x18002929b  mov     rcx, rdi; this
0x18002929e  call    ?_SetFocus@CThreadInputMgr@@QEAAJPEAUIDocumentInputManagerPrivate@@H@Z; CThreadInputMgr::_SetFocus(IDocumentInputManagerPrivate *,int)
0x1800292a3  mov     rcx, rdi; this
0x1800292a6  call    ?IsUWPApp@CThreadInputMgr@@QEBA_NXZ; CThreadInputMgr::IsUWPApp(void)
0x1800292ab  test    al, al
0x1800292ad  jnz     short loc_1800292F5
0x1800292af  mov     rcx, rdi; this
0x1800292b2  call    ?_StartAccFocusTracking@CThreadInputMgr@@AEAAXXZ; CThreadInputMgr::_StartAccFocusTracking(void)
0x1800292b7  mov     rax, [rdi+0B90h]
0x1800292be  neg     rax
0x1800292c1  sbb     eax, eax
0x1800292c3  not     eax
0x1800292c5  and     eax, 80004005h
0x1800292ca  mov     rcx, [rsp+0E8h+var_58]
0x1800292d2  xor     rcx, rsp; StackCookie
0x1800292d5  call    __security_check_cookie
0x1800292da  add     rsp, 0A8h
0x1800292e1  pop     r15
0x1800292e3  pop     r14
0x1800292e5  pop     r13
0x1800292e7  pop     r12
0x1800292e9  pop     rdi
0x1800292ea  pop     rsi
0x1800292eb  pop     rbp
0x1800292ec  pop     rbx
0x1800292ed  retn
0x1800292ee  mov     eax, 1
0x1800292f3  jmp     short loc_1800292CA
0x1800292f5  mov     rcx, [rdi+0D0h]; this
0x1800292fc  lea     rax, [rdi+0BC8h]
0x180029303  mov     edx, 7FFFFF00h; unsigned int
0x180029308  mov     qword ptr [rsp+0E8h+idThread], rax; unsigned __int64 *
0x18002930d  mov     r9d, esi; int
0x180029310  mov     qword ptr [rsp+0E8h+idProcess], r13; struct ICiceroEventSink *
0x180029315  lea     r8d, [rdx+1]; unsigned int
0x180029319  call    ?AdviseCiceroEvents@tagSYSTHREAD@@QEAAHIIHPEAUICiceroEventSink@@PEA_K@Z; tagSYSTHREAD::AdviseCiceroEvents(uint,uint,int,ICiceroEventSink *,unsigned __int64 *)
0x18002931e  jmp     short loc_1800292B7
0x180029320  mov     ebx, 48h ; 'H'
0x180029325  mov     [rdi+0B90h], r14
0x18002932c  mov     r8d, ebx; Size
0x18002932f  lea     rcx, [rsp+0E8h+pgui]; void *
0x180029334  xor     edx, edx; Val
0x180029336  call    memset_0
0x18002933b  lea     rdx, [rsp+0E8h+pgui]; pgui
0x180029340  mov     [rsp+0E8h+pgui.cbSize], ebx
0x180029344  xor     ecx, ecx; idThread
0x180029346  call    cs:__imp_GetGUIThreadInfo
0x18002934c  mov     rcx, [rsp+0E8h+pgui.hwndFocus]; hWnd
0x180029351  test    rcx, rcx
0x180029354  jz      loc_180029296
0x18002935a  xor     edx, edx; lpdwProcessId
0x18002935c  call    cs:__imp_GetWindowThreadProcessId
0x180029362  mov     ebx, eax
0x180029364  call    cs:__imp_GetCurrentThreadId
0x18002936a  cmp     eax, ebx
0x18002936c  jnz     loc_180029296
0x180029372  mov     rdx, [rsp+0E8h+pgui.hwndFocus]; hwnd
0x180029377  mov     rcx, rdi; this
0x18002937a  call    ?UpdateFocusHwnd@CThreadInputMgr@@QEAAXPEAUHWND__@@@Z; CThreadInputMgr::UpdateFocusHwnd(HWND__ *)
0x18002937f  mov     rcx, rdi; this
0x180029382  call    ?GetPendingFocusDocInputMgr@CThreadInputMgr@@AEAAPEAUIDocumentInputManagerPrivate@@XZ; CThreadInputMgr::GetPendingFocusDocInputMgr(void)
0x180029387  mov     rdx, rax; struct IDocumentInputManagerPrivate *
0x18002938a  xor     r8d, r8d; int
0x18002938d  mov     rcx, rdi; this
0x180029390  call    ?_SetFocus@CThreadInputMgr@@QEAAJPEAUIDocumentInputManagerPrivate@@H@Z; CThreadInputMgr::_SetFocus(IDocumentInputManagerPrivate *,int)
0x180029395  mov     rcx, rdi; this
0x180029398  call    ?HasDocumentFocus@CThreadInputMgr@@QEBA_NXZ; CThreadInputMgr::HasDocumentFocus(void)
0x18002939d  test    al, al
0x18002939f  jz      loc_1800292A3
0x1800293a5  xor     r8d, r8d
0x1800293a8  lea     edx, [r8+2]
0x1800293ac  call    ?UpdateIMMStatus@CThreadInputMgr@@QEAAXW4IMMStatusUpdateSource@@_N@Z; CThreadInputMgr::UpdateIMMStatus(IMMStatusUpdateSource,bool)
0x1800293b1  jmp     loc_1800292A3
0x1800293b6  mov     [rax], r14
0x1800293b9  mov     ebp, 80000002h
0x1800293be  mov     [r14], rsi
0x1800293c1  mov     r15d, 80000005h
0x1800293c7  mov     esi, 1
0x1800293cc  mov     [r14+8], ebp
0x1800293d0  mov     [r14+10h], esi
0x1800293d4  xor     ecx, ecx
0x1800293d6  mov     [r14+0Ch], r15d
0x1800293da  cmp     ecx, [rbx+130h]
0x1800293e0  jge     short loc_180029434
0x1800293e2  mov     eax, ecx
0x1800293e4  imul    eax, [rbx+134h]
0x1800293eb  movsxd  rdx, eax
0x1800293ee  mov     rax, [rbx+128h]
0x1800293f5  cmp     [rdx+rax+10h], esi
0x1800293f9  jnz     short loc_180029463
0x1800293fb  mov     r9d, [rdx+rax+0Ch]
0x180029400  cmp     ebp, r9d
0x180029403  ja      short loc_180029463
0x180029405  mov     r8d, [rdx+rax+8]
0x18002940a  cmp     r15d, r8d
0x18002940d  jb      short loc_180029463
0x18002940f  add     [rdx+rax+14h], esi
0x180029413  lea     eax, [r9+1]
0x180029417  cmp     ebp, r8d
0x18002941a  cmovb   eax, ebp
0x18002941d  cmp     r15d, r9d
0x180029420  mov     ebp, eax
0x180029422  lea     eax, [r8-1]
0x180029426  cmova   eax, r15d
0x18002942a  mov     r15d, eax
0x18002942d  cmp     ebp, eax
0x18002942f  jb      short loc_180029463
0x180029431  lea     ebp, [rax+1]
0x180029434  cmp     ebp, r15d
0x180029437  ja      loc_180029320
0x18002943d  lea     rcx, [rbx+120h]; this
0x180029444  mov     edx, esi; int
0x180029446  call    ?Append@CVoidStructArray@@QEAAPEAXH@Z; CVoidStructArray::Append(int)
0x18002944b  mov     r12, rax
0x18002944e  test    rax, rax
0x180029451  jnz     short loc_18002946A
0x180029453  mov     rdx, r14; unsigned __int64
0x180029456  mov     rcx, rbx; this
0x180029459  call    ?UnadviseCiceroEvents@tagSYSTHREAD@@QEAAX_K@Z; tagSYSTHREAD::UnadviseCiceroEvents(unsigned __int64)
0x18002945e  jmp     loc_1800292B7
0x180029463  add     ecx, esi
0x180029465  jmp     loc_1800293DA
0x18002946a  mov     [rax+14h], esi
0x18002946d  mov     [rax+8], ebp
0x180029470  mov     [rax+0Ch], r15d
0x180029474  mov     [rax+10h], esi
0x180029477  test    dword ptr [rbx+0C0h], 100h
0x180029481  jz      short loc_1800294C5
0x180029483  xor     r8d, r8d
0x180029486  cmp     ebp, r15d
0x180029489  ja      short loc_1800294A2
0x18002948b  xor     edx, edx
0x18002948d  mov     ecx, ebp
0x18002948f  call    ?TSFRangeFromEvent@@YAKKW4TSFLocality@@@Z; TSFRangeFromEvent(ulong,TSFLocality)
0x180029494  test    eax, eax
0x180029496  jz      short loc_18002949F
0x180029498  or      r8d, eax
0x18002949b  add     ebp, esi
0x18002949d  jmp     short loc_180029486
0x18002949f  xor     r8d, r8d
0x1800294a2  mov     ecx, r8d
0x1800294a5  mov     [r14+14h], r8d
0x1800294a9  call    cs:__imp_MakeThreadTSFEventAware
0x1800294af  mov     qword ptr [r12], 0
0x1800294b7  mov     eax, [r14+14h]
0x1800294bb  mov     [r12+18h], eax
0x1800294c0  jmp     loc_180029320
0x1800294c5  call    cs:__imp_GetCurrentThreadId
0x1800294cb  mov     ebx, eax
0x1800294cd  call    cs:__imp_GetCurrentProcessId
0x1800294d3  mov     r8, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hmodWinEventProc
0x1800294da  lea     r9, ?WinEventProc@@YAXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@Z; pfnWinEventProc
0x1800294e1  mov     [rsp+0E8h+dwFlags], 4; dwFlags
0x1800294e9  mov     edx, r15d; eventMax
0x1800294ec  mov     [rsp+0E8h+idThread], ebx; idThread
0x1800294f0  mov     ecx, ebp; eventMin
0x1800294f2  mov     [rsp+0E8h+idProcess], eax; idProcess
0x1800294f6  call    cs:__imp_SetWinEventHook
0x1800294fc  mov     [r12], rax
0x180029500  jmp     loc_180029320
```

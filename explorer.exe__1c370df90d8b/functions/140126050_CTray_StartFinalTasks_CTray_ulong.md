# CTray::_StartFinalTasks(CTray *,ulong)

- ea: `0x140126050`
- end: `0x1401261d0`
- name: `?_StartFinalTasks@CTray@@KA_NPEAV1@K@Z`
- size: `384`
- prototype: `bool __fastcall(struct CTray *this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x14001eba8`
- `0x140065a60`
- `0x140067bcc`
- `0x1401134c4`
- `0x140126050`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140126166`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140126166`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140126185`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140126185`
- `api-ms-win-shell-namespace-l1-1-0!ILRemoveLastID` at `0x1401260d1`
- `api-ms-win-shell-namespace-l1-1-0!ILRemoveLastID` at `0x1401260d1`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x140126128`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x140126128`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyRegister` at `0x140126110`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyRegister` at `0x140126110`
- `SHELL32!__imp_SHRestricted` at `0x14012606a`
- `SHELL32!__imp_SHRestricted` at `0x140126097`
- `SHELL32!__imp_SHRestricted` at `0x14012606a`
- `SHELL32!__imp_SHRestricted` at `0x140126097`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x14012608c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x14012608c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderLocation` at `0x1401260c3`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderLocation` at `0x1401260c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CTray::_StartFinalTasks(HWND *this)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  DWORD CurrentThreadId; // eax
  int v5; // edi
  SHChangeNotifyEntry pshcne; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  LPITEMIDLIST ppidl; // [rsp+60h] [rbp+20h] BYREF
  HWND v10; // [rsp+68h] [rbp+28h] BYREF

  if ( !SHRestricted(REST_NOLOWDISKSPACECHECKS) )
    SetCoalescableTimer(this[1], 0x15u, 0x927C0u, 0, 0xEA60u);
  if ( !SHRestricted(REST_NOCDBURNING) )
  {
    ppidl = 0;
    if ( SHGetFolderLocation(0, 32827, 0, 0, &ppidl) >= 0 )
    {
      if ( ILRemoveLastID(ppidl) )
      {
        pshcne.fRecursive = 1;
        pshcne.pidl = ppidl;
        *((_DWORD *)this + 115) = SHChangeNotifyRegister(this[1], 32771, 134230026, 0x551u, 1, &pshcne);
        CTray::_CheckStagingAreaOnTimer((CTray *)this);
        ILFree(ppidl);
      }
    }
  }
  v10 = v_hwndDesktop;
  v2 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_ce13106dbd77740075b30feac0d5b2b4_____lambda_ce13106dbd77740075b30feac0d5b2b4___(
                    &ppidl,
                    &v10);
  v3 = *v2;
  *v2 = 0;
  if ( ppidl )
  {
    ppidl = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v5 = SHTaskPoolQueueTask(1, 0, CurrentThreadId, 0);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x12B5,
      (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
      (const char *)(unsigned int)v5,
      v3);
  return 1;
}

```

## disassembly

```asm
0x140126050  mov     [rsp-8+arg_0], rbx
0x140126055  mov     [rsp-8+arg_8], rdi
0x14012605a  push    rbp
0x14012605b  mov     rbp, rsp
0x14012605e  sub     rsp, 40h
0x140126062  mov     rdi, rcx
0x140126065  mov     ecx, 40000071h; rest
0x14012606a  call    cs:__imp_SHRestricted
0x140126070  test    eax, eax
0x140126072  jnz     short loc_140126092
0x140126074  mov     [rsp+40h+uToleranceDelay], 0EA60h; uToleranceDelay
0x14012607c  xor     r9d, r9d; lpTimerFunc
0x14012607f  lea     edx, [rax+15h]; nIDEvent
0x140126082  mov     r8d, 927C0h; uElapse
0x140126088  mov     rcx, [rdi+8]; hWnd
0x14012608c  call    cs:__imp_SetCoalescableTimer
0x140126092  mov     ecx, 40000057h; rest
0x140126097  call    cs:__imp_SHRestricted
0x14012609d  test    eax, eax
0x14012609f  jnz     loc_14012612E
0x1401260a5  mov     [rbp+ppidl], 0
0x1401260ad  lea     rax, [rbp+ppidl]
0x1401260b1  mov     qword ptr [rsp+40h+uToleranceDelay], rax; ppidl
0x1401260b6  xor     r9d, r9d; dwFlags
0x1401260b9  xor     r8d, r8d; hToken
0x1401260bc  mov     edx, 803Bh; csidl
0x1401260c1  xor     ecx, ecx; hwnd
0x1401260c3  call    cs:__imp_SHGetFolderLocation
0x1401260c9  test    eax, eax
0x1401260cb  js      short loc_14012612E
0x1401260cd  mov     rcx, [rbp+ppidl]; pidl
0x1401260d1  call    cs:__imp_ILRemoveLastID
0x1401260d7  test    eax, eax
0x1401260d9  jz      short loc_14012612E
0x1401260db  mov     [rbp+var_10.fRecursive], 1
0x1401260e2  mov     rax, [rbp+ppidl]
0x1401260e6  mov     [rbp+var_10.pidl], rax
0x1401260ea  lea     rax, [rbp+var_10]
0x1401260ee  mov     [rsp+40h+pshcne], rax; pshcne
0x1401260f3  mov     [rsp+40h+uToleranceDelay], 1; cEntries
0x1401260fb  mov     edx, 8003h; fSources
0x140126100  mov     r9d, 551h; wMsg
0x140126106  mov     r8d, 800300Ah; fEvents
0x14012610c  mov     rcx, [rdi+8]; hwnd
0x140126110  call    cs:__imp_SHChangeNotifyRegister
0x140126116  mov     [rdi+1CCh], eax
0x14012611c  mov     rcx, rdi; this
0x14012611f  call    ?_CheckStagingAreaOnTimer@CTray@@IEAAXXZ; CTray::_CheckStagingAreaOnTimer(void)
0x140126124  mov     rcx, [rbp+ppidl]; pidl
0x140126128  call    cs:__imp_ILFree
0x14012612e  mov     rax, cs:?v_hwndDesktop@@3PEAUHWND__@@EA; HWND__ * v_hwndDesktop
0x140126135  mov     [rbp+arg_18], rax
0x140126139  lea     rdx, [rbp+arg_18]
0x14012613d  lea     rcx, [rbp+ppidl]
0x140126141  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_ce13106dbd77740075b30feac0d5b2b4_____lambda_ce13106dbd77740075b30feac0d5b2b4___
0x140126146  mov     rbx, [rax]
0x140126149  mov     qword ptr [rax], 0
0x140126150  mov     rcx, [rbp+ppidl]
0x140126154  test    rcx, rcx
0x140126157  jz      short loc_140126166
0x140126159  mov     [rbp+ppidl], 0
0x140126161  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x140126166  call    cs:__imp_GetCurrentThreadId
0x14012616c  mov     [rsp+40h+pshcne], 0
0x140126175  mov     qword ptr [rsp+40h+uToleranceDelay], rbx; int
0x14012617a  xor     r9d, r9d
0x14012617d  mov     r8d, eax
0x140126180  xor     edx, edx
0x140126182  lea     ecx, [rdx+1]
0x140126185  call    cs:__imp_SHTaskPoolQueueTask
0x14012618b  mov     edi, eax
0x14012618d  test    rbx, rbx
0x140126190  jz      short loc_1401261A2
0x140126192  mov     rdx, [rbx]
0x140126195  mov     rcx, rbx
0x140126198  mov     rax, [rdx+10h]
0x14012619c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401261a1  nop
0x1401261a2  test    edi, edi
0x1401261a4  jns     short loc_1401261BE
0x1401261a6  mov     rcx, [rbp+8]; this
0x1401261aa  mov     r9d, edi; char *
0x1401261ad  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x1401261b4  mov     edx, 12B5h; void *
0x1401261b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1401261be  mov     al, 1
0x1401261c0  mov     rbx, [rsp+40h+arg_0]
0x1401261c5  mov     rdi, [rsp+40h+arg_8]
0x1401261ca  add     rsp, 40h
0x1401261ce  pop     rbp
0x1401261cf  retn
```

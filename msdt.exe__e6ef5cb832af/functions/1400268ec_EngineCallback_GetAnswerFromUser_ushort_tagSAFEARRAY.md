# EngineCallback::GetAnswerFromUser(ushort *,tagSAFEARRAY * *)

- ea: `0x1400268ec`
- end: `0x140026a41`
- name: `?GetAnswerFromUser@EngineCallback@@AEAAJPEAGPEAPEAUtagSAFEARRAY@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(EngineCallback *this, unsigned __int16 *, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140026cb0`

## callees

- `0x14001ccc0`
- `0x140020420`
- `0x1400268ec`
- `0x14003ea28`
- `0x140048be0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400269cb`
- `KERNEL32!GetLastError` at `0x1400269cb`
- `KERNEL32!SetEvent` at `0x1400269bb`
- `KERNEL32!SetEvent` at `0x1400269bb`
- `KERNEL32!WaitForMultipleObjects` at `0x140026991`
- `KERNEL32!WaitForMultipleObjects` at `0x140026991`
- `USER32!PostMessageW` at `0x140026973`
- `USER32!PostMessageW` at `0x140026973`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140026959`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140026959`

## pseudocode

```c
__int64 __fastcall EngineCallback::GetAnswerFromUser(
        EngineCallback *this,
        unsigned __int16 *a2,
        struct tagSAFEARRAY **a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  HWND ParentHWND; // rax
  DWORD v10; // eax
  int v11; // r9d
  signed int LastError; // eax
  struct tagSAFEARRAY *v13; // rax
  struct PageManager *v15; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  v6 = WaitForProgressPage();
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( v6 == 1 )
      return (unsigned int)-2147467259;
    v8 = PageManager::Instance(&v15);
    v7 = v8;
    if ( v8 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EngineCallback::GetAnswerFromUser", 631, v8);
      return v7;
    }
    ParentHWND = DirectUI::TaskPage::GetParentHWND(*((DirectUI::TaskPage **)v15 + 1));
    PostMessageW(ParentHWND, 0x9DFu, 0, (LPARAM)a2);
    v10 = WaitForMultipleObjects(0x1Cu, &g_EventsToWorker, 0, 0xFFFFFFFF);
    if ( v10 == 4 )
    {
      v13 = (struct tagSAFEARRAY *)*((_QWORD *)this + 1);
      *a3 = v13;
      *((_QWORD *)this + 1) = 0;
      if ( v13 )
        return v7;
      v11 = 670;
    }
    else
    {
      if ( v10 == 27 )
      {
        Packages_Cancel();
        if ( SetEvent(qword_140080088) )
          return (unsigned int)-2147467260;
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( (v7 & 0x80000000) == 0 )
          return (unsigned int)-2147467260;
        v11 = 648;
LABEL_19:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EngineCallback::GetAnswerFromUser", v11, v7);
        return v7;
      }
      v11 = 659;
    }
    v7 = -2147467259;
    goto LABEL_19;
  }
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EngineCallback::GetAnswerFromUser", 624, v6);
  return v7;
}

```

## disassembly

```asm
0x1400268ec  push    rbx
0x1400268ee  push    rbp
0x1400268ef  push    rsi
0x1400268f0  push    r14
0x1400268f2  sub     rsp, 38h
0x1400268f6  mov     r14, r8
0x1400268f9  mov     [rsp+58h+arg_18], 0
0x140026902  mov     rbp, rdx
0x140026905  mov     rsi, rcx
0x140026908  call    ?WaitForProgressPage@@YAJXZ; WaitForProgressPage(void)
0x14002690d  mov     ebx, eax
0x14002690f  test    eax, eax
0x140026911  jns     short loc_140026922
0x140026913  mov     [rsp+58h+var_38], eax
0x140026917  mov     r9d, 270h
0x14002691d  jmp     loc_140026A1C
0x140026922  cmp     eax, 1
0x140026925  jnz     short loc_140026931
0x140026927  mov     ebx, 80004005h
0x14002692c  jmp     loc_140026A34
0x140026931  lea     rcx, [rsp+58h+arg_18]; struct PageManager **
0x140026936  call    ?Instance@PageManager@@SAJPEAPEAV1@@Z; PageManager::Instance(PageManager * *)
0x14002693b  mov     ebx, eax
0x14002693d  test    eax, eax
0x14002693f  jns     short loc_140026950
0x140026941  mov     [rsp+58h+var_38], eax
0x140026945  mov     r9d, 277h
0x14002694b  jmp     loc_140026A1C
0x140026950  mov     rcx, [rsp+58h+arg_18]
0x140026955  mov     rcx, [rcx+8]
0x140026959  call    cs:__imp_?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::TaskPage::GetParentHWND(void)
0x140026960  nop     dword ptr [rax+rax+00h]
0x140026965  mov     r9, rbp; lParam
0x140026968  xor     r8d, r8d; wParam
0x14002696b  mov     rcx, rax; hWnd
0x14002696e  mov     edx, 9DFh; Msg
0x140026973  call    cs:__imp_PostMessageW
0x14002697a  nop     dword ptr [rax+rax+00h]
0x14002697f  xor     r8d, r8d; bWaitAll
0x140026982  lea     rdx, ?g_EventsToWorker@@3PAPEAXA; lpHandles
0x140026989  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14002698d  lea     ecx, [r8+1Ch]; nCount
0x140026991  call    cs:__imp_WaitForMultipleObjects
0x140026998  nop     dword ptr [rax+rax+00h]
0x14002699d  cmp     eax, 4
0x1400269a0  jz      short loc_1400269F9
0x1400269a2  cmp     eax, 1Bh
0x1400269a5  jz      short loc_1400269AF
0x1400269a7  mov     r9d, 293h
0x1400269ad  jmp     short loc_140026A13
0x1400269af  call    ?Packages_Cancel@@YAXXZ; Packages_Cancel(void)
0x1400269b4  mov     rcx, cs:qword_140080088; hEvent
0x1400269bb  call    cs:__imp_SetEvent
0x1400269c2  nop     dword ptr [rax+rax+00h]
0x1400269c7  test    eax, eax
0x1400269c9  jnz     short loc_1400269F2
0x1400269cb  call    cs:__imp_GetLastError
0x1400269d2  nop     dword ptr [rax+rax+00h]
0x1400269d7  mov     ebx, eax
0x1400269d9  test    eax, eax
0x1400269db  jle     short loc_1400269E6
0x1400269dd  movzx   ebx, ax
0x1400269e0  or      ebx, 80070000h
0x1400269e6  test    ebx, ebx
0x1400269e8  jns     short loc_1400269F2
0x1400269ea  mov     r9d, 288h
0x1400269f0  jmp     short loc_140026A18
0x1400269f2  mov     ebx, 80004004h
0x1400269f7  jmp     short loc_140026A34
0x1400269f9  mov     rax, [rsi+8]
0x1400269fd  mov     [r14], rax
0x140026a00  mov     qword ptr [rsi+8], 0
0x140026a08  test    rax, rax
0x140026a0b  jnz     short loc_140026A34
0x140026a0d  mov     r9d, 29Eh
0x140026a13  mov     ebx, 80004005h
0x140026a18  mov     [rsp+58h+var_38], ebx
0x140026a1c  lea     r8, aEnginecallback_6; "EngineCallback::GetAnswerFromUser"
0x140026a23  mov     ecx, 1; Level
0x140026a28  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140026a2f  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140026a34  mov     eax, ebx
0x140026a36  add     rsp, 38h
0x140026a3a  pop     r14
0x140026a3c  pop     rsi
0x140026a3d  pop     rbp
0x140026a3e  pop     rbx
0x140026a3f  retn
```

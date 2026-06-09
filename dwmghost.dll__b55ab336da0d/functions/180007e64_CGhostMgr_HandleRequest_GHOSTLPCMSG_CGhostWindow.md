# CGhostMgr::HandleRequest(GHOSTLPCMSG *,CGhostWindow * *)

- ea: `0x180007e64`
- end: `0x180008138`
- name: `?HandleRequest@CGhostMgr@@QEAAHPEAUGHOSTLPCMSG@@PEAPEAVCGhostWindow@@@Z`
- size: `724`
- prototype: `__int64 __fastcall(CGhostMgr *__hidden this, struct GHOSTLPCMSG *, struct CGhostWindow **)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008eec`
- `0x18000a7f0`

## callees

- `0x180001190`
- `0x180004dc4`
- `0x1800057b8`
- `0x180005f24`
- `0x180006494`
- `0x180007c2c`
- `0x180007d0c`
- `0x180007e64`
- `0x18000825c`
- `0x1800083e8`
- `0x1800093f8`
- `0x1800095fc`
- `0x180009f80`
- `0x18000a2c4`
- `0x18000a5d0`
- `0x18000a8a0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800080ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800080ab`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1800080bc`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1800080bc`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180007f13`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180007f13`
- `ext-ms-win-ntuser-windowstation-l1-1-0!OpenThreadDesktop` at `0x180007f2d`
- `ext-ms-win-ntuser-windowstation-l1-1-0!OpenThreadDesktop` at `0x180007f2d`

## pseudocode

```c
__int64 __fastcall CGhostMgr::HandleRequest(CGhostMgr *this, struct GHOSTLPCMSG *a2, struct CGhostWindow **a3)
{
  char *v3; // rbp
  unsigned int v7; // r15d
  int v8; // esi
  CGhostProcess *GhostProcess; // rax
  CCountedObject *v10; // rdi
  int v11; // r13d
  HDESK ThreadDesktop; // rbp
  CCountedObject *GhostThread; // r12
  CGhostProcess *v14; // rax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  struct CGhostProcess *v18; // rsi
  CSiblingFrostWindow *v19; // rax
  __int64 v20; // rcx
  CGhostWindow *v21; // rax
  CCrashFrostWindow *v22; // rax
  __int64 v23; // rcx
  struct CGhostWindow *v24; // rdi
  CGhostWindow *v25; // rax
  __int64 v26; // rcx
  char v28; // [rsp+30h] [rbp-68h]
  int v29; // [rsp+34h] [rbp-64h]
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+40h] [rbp-58h] BYREF
  void *retaddr; // [rsp+98h] [rbp+0h]

  v3 = (char *)a2 + 8;
  v29 = 0;
  v28 = 0;
  v7 = 0;
  v8 = 0;
  if ( *(_QWORD *)a2 )
    v28 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a2 + 40LL))(*(_QWORD *)a2);
  if ( a3 )
    *a3 = 0;
  if ( !CGhostMgr::s_bInShutdown )
  {
    if ( *((_DWORD *)a2 + 13) == 4 )
    {
      GhostProcess = CGhostMgr::FindGhostProcess(this, *((_DWORD *)a2 + 16));
      v10 = GhostProcess;
      if ( GhostProcess )
      {
        v7 = CGhostProcess::SetErrorReportingHwnd(GhostProcess, *((HWND *)a2 + 9));
        CCountedObject::Release(v10);
      }
      goto LABEL_40;
    }
    v11 = 0;
    ThreadDesktop = GetThreadDesktop(*((_DWORD *)a2 + 17));
    if ( !ThreadDesktop )
    {
      ThreadDesktop = (HDESK)OpenThreadDesktop(*((unsigned int *)a2 + 17), 0, 0, 3);
      if ( !ThreadDesktop )
      {
LABEL_39:
        v3 = (char *)a2 + 8;
        goto LABEL_40;
      }
      v11 = 1;
    }
    if ( !(unsigned int)GetDesktopName(ThreadDesktop) )
    {
LABEL_37:
      if ( v11 )
        CloseDesktop(ThreadDesktop);
      goto LABEL_39;
    }
    GhostThread = CGhostMgr::FindGhostThread(this, 0);
    if ( !GhostThread )
    {
LABEL_36:
      HeapFree(g_hProcessHeap, 0, 0);
      goto LABEL_37;
    }
    v14 = CGhostMgr::FindGhostProcess(this, *((_DWORD *)a2 + 16));
    v18 = v14;
    if ( !v14 )
    {
LABEL_35:
      CCountedObject::Release(GhostThread);
      v8 = v29;
      goto LABEL_36;
    }
    switch ( *((_DWORD *)a2 + 13) )
    {
      case 1:
        if ( (Microsoft_Windows_Feedback_Service_TriggerProviderEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(v15, 0, v16, v17, &v30);
        v25 = (CGhostWindow *)DefaultHeap::AllocClear(0xE8u);
        if ( !v25 )
          ModuleFailFastForHRESULT(v26, retaddr);
        v21 = CGhostWindow::CGhostWindow(v25, *((HWND *)a2 + 7), v18);
        break;
      case 2:
        if ( !(unsigned int)CGhostProcess::MarkAsCrashedProcess(v14, *((HWND *)a2 + 9)) )
          goto LABEL_34;
        v22 = (CCrashFrostWindow *)DefaultHeap::AllocClear(0x148u);
        if ( !v22 )
          ModuleFailFastForHRESULT(v23, retaddr);
        v24 = CCrashFrostWindow::CCrashFrostWindow(
                v22,
                (struct GHOSTLPCMSG *)((char *)a2 + 8),
                v18,
                *(struct IPortMessage **)a2);
        if ( !v24 )
          goto LABEL_34;
        v29 = 1;
LABEL_29:
        v7 = CGhostThread::AssignGhostToThread(GhostThread, v24);
        if ( v7 )
        {
          if ( a3 )
          {
            *a3 = v24;
            goto LABEL_34;
          }
        }
        else
        {
          CGhostWindow::DestroyGhostWindow(v24);
        }
        CCountedObject::Release(v24);
        goto LABEL_34;
      case 3:
        v19 = (CSiblingFrostWindow *)DefaultHeap::AllocClear(0xE8u);
        if ( !v19 )
          ModuleFailFastForHRESULT(v20, retaddr);
        v21 = CSiblingFrostWindow::CSiblingFrostWindow(v19, *((HWND *)a2 + 7), v18);
        break;
      default:
LABEL_34:
        CCountedObject::Release(v18);
        goto LABEL_35;
    }
    v24 = v21;
    if ( v21 )
      goto LABEL_29;
    goto LABEL_34;
  }
LABEL_40:
  if ( v28 && !v8 )
  {
    *((_QWORD *)v3 + 9) = 0;
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)a2 + 24LL))(*(_QWORD *)a2, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x180007e64  mov     [rsp+arg_18], rbx
0x180007e69  push    rbp
0x180007e6a  push    rsi
0x180007e6b  push    rdi
0x180007e6c  push    r12
0x180007e6e  push    r13
0x180007e70  push    r14
0x180007e72  push    r15
0x180007e74  sub     rsp, 60h
0x180007e78  mov     rax, cs:__security_cookie
0x180007e7f  xor     rax, rsp
0x180007e82  mov     [rsp+98h+var_48], rax
0x180007e87  xor     r12d, r12d
0x180007e8a  lea     rbp, [rdx+8]
0x180007e8e  mov     rdi, rcx
0x180007e91  mov     [rsp+98h+var_64], r12d
0x180007e96  mov     rcx, [rdx]
0x180007e99  mov     r14, r8
0x180007e9c  mov     [rsp+98h+var_68], r12b
0x180007ea1  mov     rbx, rdx
0x180007ea4  mov     r15d, r12d
0x180007ea7  mov     esi, r12d
0x180007eaa  test    rcx, rcx
0x180007ead  jz      short loc_180007EBF
0x180007eaf  mov     rax, [rcx]
0x180007eb2  mov     rax, [rax+28h]
0x180007eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ebb  mov     [rsp+98h+var_68], al
0x180007ebf  test    r14, r14
0x180007ec2  jz      short loc_180007EC7
0x180007ec4  mov     [r14], r12
0x180007ec7  cmp     cs:?s_bInShutdown@CGhostMgr@@0HA, r12d; int CGhostMgr::s_bInShutdown
0x180007ece  jnz     loc_1800080C6
0x180007ed4  cmp     dword ptr [rbx+34h], 4
0x180007ed8  jnz     short loc_180007F0D
0x180007eda  mov     edx, [rbx+40h]; unsigned int
0x180007edd  mov     rcx, rdi; this
0x180007ee0  call    ?FindGhostProcess@CGhostMgr@@AEAAPEAVCGhostProcess@@K@Z; CGhostMgr::FindGhostProcess(ulong)
0x180007ee5  mov     rdi, rax
0x180007ee8  test    rax, rax
0x180007eeb  jz      loc_1800080C6
0x180007ef1  mov     rdx, [rbx+48h]; HWND
0x180007ef5  mov     rcx, rax; this
0x180007ef8  call    ?SetErrorReportingHwnd@CGhostProcess@@QEAAHPEAUHWND__@@@Z; CGhostProcess::SetErrorReportingHwnd(HWND__ *)
0x180007efd  mov     rcx, rdi; this
0x180007f00  mov     r15d, eax
0x180007f03  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180007f08  jmp     loc_1800080C6
0x180007f0d  mov     ecx, [rbx+44h]; dwThreadId
0x180007f10  mov     r13d, r12d
0x180007f13  call    cs:__imp_GetThreadDesktop
0x180007f19  mov     rbp, rax
0x180007f1c  test    rax, rax
0x180007f1f  jnz     short loc_180007F45
0x180007f21  mov     ecx, [rbx+44h]
0x180007f24  lea     r9d, [rax+3]
0x180007f28  xor     r8d, r8d
0x180007f2b  xor     edx, edx
0x180007f2d  call    cs:__imp_OpenThreadDesktop
0x180007f33  mov     rbp, rax
0x180007f36  test    rax, rax
0x180007f39  jz      loc_1800080C2
0x180007f3f  mov     r13d, 1
0x180007f45  lea     rdx, [rsp+98h+lpMem]
0x180007f4a  mov     [rsp+98h+lpMem], r12
0x180007f4f  mov     rcx, rbp; hObj
0x180007f52  call    GetDesktopName
0x180007f57  test    eax, eax
0x180007f59  jz      loc_1800080B4
0x180007f5f  mov     rdx, [rsp+98h+lpMem]; unsigned __int16 *
0x180007f64  mov     rcx, rdi; this
0x180007f67  call    ?FindGhostThread@CGhostMgr@@AEAAPEAVCGhostThread@@PEBG@Z; CGhostMgr::FindGhostThread(ushort const *)
0x180007f6c  mov     r12, rax
0x180007f6f  test    rax, rax
0x180007f72  jz      loc_18000809D
0x180007f78  mov     edx, [rbx+40h]; unsigned int
0x180007f7b  mov     rcx, rdi; this
0x180007f7e  call    ?FindGhostProcess@CGhostMgr@@AEAAPEAVCGhostProcess@@K@Z; CGhostMgr::FindGhostProcess(ulong)
0x180007f83  mov     rsi, rax
0x180007f86  test    rax, rax
0x180007f89  jz      loc_180008091
0x180007f8f  mov     edx, [rbx+34h]
0x180007f92  sub     edx, 1; int
0x180007f95  jz      loc_18000801B
0x180007f9b  sub     edx, 1
0x180007f9e  jz      short loc_180007FD0
0x180007fa0  cmp     edx, 1
0x180007fa3  jnz     loc_180008089
0x180007fa9  mov     ecx, 0E8h; unsigned __int64
0x180007fae  call    ?AllocClear@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::AllocClear(unsigned __int64)
0x180007fb3  test    rax, rax
0x180007fb6  jz      loc_18000811C
0x180007fbc  mov     rdx, [rbx+38h]; HWND
0x180007fc0  mov     r8, rsi; struct CGhostProcess *
0x180007fc3  mov     rcx, rax; this
0x180007fc6  call    ??0CSiblingFrostWindow@@QEAA@PEAUHWND__@@PEAVCGhostProcess@@@Z; CSiblingFrostWindow::CSiblingFrostWindow(HWND__ *,CGhostProcess *)
0x180007fcb  jmp     loc_180008055
0x180007fd0  mov     rdx, [rbx+48h]; HWND
0x180007fd4  mov     rcx, rsi; this
0x180007fd7  call    ?MarkAsCrashedProcess@CGhostProcess@@QEAAHPEAUHWND__@@@Z; CGhostProcess::MarkAsCrashedProcess(HWND__ *)
0x180007fdc  test    eax, eax
0x180007fde  jz      loc_180008089
0x180007fe4  mov     ecx, 148h; unsigned __int64
0x180007fe9  call    ?AllocClear@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::AllocClear(unsigned __int64)
0x180007fee  test    rax, rax
0x180007ff1  jz      loc_18000812A
0x180007ff7  mov     r9, [rbx]; struct IPortMessage *
0x180007ffa  lea     rdx, [rbx+8]; struct GHOSTMSG *
0x180007ffe  mov     r8, rsi; struct CGhostProcess *
0x180008001  mov     rcx, rax; this
0x180008004  call    ??0CCrashFrostWindow@@QEAA@PEBUGHOSTMSG@@PEAVCGhostProcess@@PEAUIPortMessage@@@Z; CCrashFrostWindow::CCrashFrostWindow(GHOSTMSG const *,CGhostProcess *,IPortMessage *)
0x180008009  mov     rdi, rax
0x18000800c  test    rax, rax
0x18000800f  jz      short loc_180008089
0x180008011  mov     [rsp+98h+var_64], 1
0x180008019  jmp     short loc_18000805D
0x18000801b  test    cs:Microsoft_Windows_Feedback_Service_TriggerProviderEnableBits, 1
0x180008022  jz      short loc_180008033
0x180008024  lea     rax, [rsp+98h+var_58]
0x180008029  mov     [rsp+98h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x18000802e  call    McGenEventWrite_EventWriteTransfer
0x180008033  mov     ecx, 0E8h; unsigned __int64
0x180008038  call    ?AllocClear@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::AllocClear(unsigned __int64)
0x18000803d  test    rax, rax
0x180008040  jz      loc_18000810E
0x180008046  mov     rdx, [rbx+38h]; HWND
0x18000804a  mov     r8, rsi; struct CGhostProcess *
0x18000804d  mov     rcx, rax; this
0x180008050  call    ??0CGhostWindow@@QEAA@PEAUHWND__@@PEAVCGhostProcess@@@Z; CGhostWindow::CGhostWindow(HWND__ *,CGhostProcess *)
0x180008055  mov     rdi, rax
0x180008058  test    rax, rax
0x18000805b  jz      short loc_180008089
0x18000805d  mov     rdx, rdi; struct CGhostWindow *
0x180008060  mov     rcx, r12; this
0x180008063  call    ?AssignGhostToThread@CGhostThread@@QEAAHPEAVCGhostWindow@@@Z; CGhostThread::AssignGhostToThread(CGhostWindow *)
0x180008068  mov     r15d, eax
0x18000806b  test    eax, eax
0x18000806d  jz      short loc_180008079
0x18000806f  test    r14, r14
0x180008072  jz      short loc_180008081
0x180008074  mov     [r14], rdi
0x180008077  jmp     short loc_180008089
0x180008079  mov     rcx, rdi; this
0x18000807c  call    ?DestroyGhostWindow@CGhostWindow@@QEAAHXZ; CGhostWindow::DestroyGhostWindow(void)
0x180008081  mov     rcx, rdi; this
0x180008084  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180008089  mov     rcx, rsi; this
0x18000808c  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180008091  mov     rcx, r12; this
0x180008094  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180008099  mov     esi, [rsp+98h+var_64]
0x18000809d  mov     r8, [rsp+98h+lpMem]; lpMem
0x1800080a2  xor     edx, edx; dwFlags
0x1800080a4  mov     rcx, cs:g_hProcessHeap; hHeap
0x1800080ab  call    cs:__imp_HeapFree
0x1800080b1  xor     r12d, r12d
0x1800080b4  test    r13d, r13d
0x1800080b7  jz      short loc_1800080C2
0x1800080b9  mov     rcx, rbp; hDesktop
0x1800080bc  call    cs:__imp_CloseDesktop
0x1800080c2  lea     rbp, [rbx+8]
0x1800080c6  cmp     [rsp+98h+var_68], r12b
0x1800080cb  jz      short loc_1800080E6
0x1800080cd  test    esi, esi
0x1800080cf  jnz     short loc_1800080E6
0x1800080d1  mov     [rbp+48h], r12
0x1800080d5  xor     edx, edx
0x1800080d7  mov     rcx, [rbx]
0x1800080da  mov     rax, [rcx]
0x1800080dd  mov     rax, [rax+18h]
0x1800080e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080e6  mov     eax, r15d
0x1800080e9  mov     rcx, [rsp+98h+var_48]
0x1800080ee  xor     rcx, rsp; StackCookie
0x1800080f1  call    __security_check_cookie
0x1800080f6  mov     rbx, [rsp+98h+arg_18]
0x1800080fe  add     rsp, 60h
0x180008102  pop     r15
0x180008104  pop     r14
0x180008106  pop     r13
0x180008108  pop     r12
0x18000810a  pop     rdi
0x18000810b  pop     rsi
0x18000810c  pop     rbp
0x18000810d  retn
0x18000810e  mov     rdx, [rsp+98h]
0x180008116  call    ModuleFailFastForHRESULT
0x18000811c  mov     rdx, [rsp+98h]
0x180008124  call    ModuleFailFastForHRESULT
0x18000812a  mov     rdx, [rsp+98h]
0x180008132  call    ModuleFailFastForHRESULT
```

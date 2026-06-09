# TryPauseResolution(IResolution *,int *)

- ea: `0x14004c834`
- end: `0x14004ca0e`
- name: `?TryPauseResolution@@YAJPEAVIResolution@@PEAH@Z`
- size: `474`
- prototype: `__int64 __fastcall(LPARAM lParam, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14004c2ac`

## callees

- `0x14001ccc0`
- `0x140020420`
- `0x14003ea28`
- `0x14004c834`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004c9c1`
- `KERNEL32!GetLastError` at `0x14004c9c1`
- `KERNEL32!SetEvent` at `0x14004c9b1`
- `KERNEL32!SetEvent` at `0x14004c9b1`
- `KERNEL32!WaitForMultipleObjects` at `0x14004c979`
- `KERNEL32!WaitForMultipleObjects` at `0x14004c979`
- `USER32!PostMessageW` at `0x14004c958`
- `USER32!PostMessageW` at `0x14004c958`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14004c93e`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14004c93e`

## pseudocode

```c
__int64 __fastcall TryPauseResolution(LPARAM lParam, int *a2)
{
  unsigned int v2; // ebx
  int v3; // esi
  int v6; // eax
  int v7; // eax
  int v8; // r9d
  HWND ParentHWND; // rax
  DWORD v10; // eax
  signed int LastError; // eax
  int v13; // [rsp+60h] [rbp+8h] BYREF
  struct PageManager *v14; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  v3 = 0;
  v14 = 0;
  v13 = 0;
  if ( lParam )
  {
    v6 = (*(__int64 (__fastcall **)(LPARAM, int *))(*(_QWORD *)lParam + 112LL))(lParam, &v13);
    if ( v6 < 0 )
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Resolution_GetScriptless", 595, v6);
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Resolution_GetScriptless", 592, -2147024809);
  }
  if ( !v13 )
    goto LABEL_25;
  v7 = WaitForProgressPage();
  v2 = v7;
  if ( v7 < 0 )
  {
    v8 = 1982;
LABEL_8:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "TryPauseResolution", v8, v7);
    return v2;
  }
  if ( v7 != 1 )
  {
    v7 = PageManager::Instance(&v14);
    v2 = v7;
    if ( v7 < 0 )
    {
      v8 = 1991;
      goto LABEL_8;
    }
    if ( lParam )
    {
      (*(void (__fastcall **)(LPARAM))(*(_QWORD *)lParam + 8LL))(lParam);
      ParentHWND = DirectUI::TaskPage::GetParentHWND(*((DirectUI::TaskPage **)v14 + 1));
      PostMessageW(ParentHWND, 0x9E1u, 0, lParam);
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "PageManager::Pause", 638, -2147024809);
    }
    v3 = 1;
    v10 = WaitForMultipleObjects(0x1Cu, &g_EventsToWorker, 0, 0xFFFFFFFF);
    if ( v10 != 20 )
    {
      if ( v10 == 27 )
      {
        g_Stop = 1;
        if ( SetEvent(qword_140080088) )
          return (unsigned int)-2147467260;
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( (v2 & 0x80000000) == 0 )
          return (unsigned int)-2147467260;
        else
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "TryPauseResolution", 2009, v2);
      }
      else
      {
        v2 = -2147467259;
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "TryPauseResolution", 2020, -2147467259);
      }
      return v2;
    }
LABEL_25:
    *a2 = v3;
  }
  return v2;
}

```

## disassembly

```asm
0x14004c834  mov     rax, rsp
0x14004c837  mov     [rax+10h], rbx
0x14004c83b  push    rsi
0x14004c83c  push    rdi
0x14004c83d  push    r12
0x14004c83f  push    r14
0x14004c841  push    r15
0x14004c843  sub     rsp, 30h
0x14004c847  xor     ebx, ebx
0x14004c849  lea     r12, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004c850  xor     esi, esi
0x14004c852  mov     [rax+18h], rbx
0x14004c856  mov     [rax+8], ebx
0x14004c859  mov     r14, rdx
0x14004c85c  mov     rdi, rcx
0x14004c85f  lea     r15d, [rbx+1]
0x14004c863  test    rcx, rcx
0x14004c866  jnz     short loc_14004C877
0x14004c868  mov     dword ptr [rax-38h], 80070057h
0x14004c86f  mov     r9d, 250h
0x14004c875  jmp     short loc_14004C896
0x14004c877  mov     rax, [rcx]
0x14004c87a  lea     rdx, [rsp+58h+arg_0]
0x14004c87f  mov     rax, [rax+70h]
0x14004c883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c888  test    eax, eax
0x14004c88a  jns     short loc_14004C8A8
0x14004c88c  mov     [rsp+58h+var_38], eax
0x14004c890  mov     r9d, 253h
0x14004c896  lea     r8, aResolutionGets; "Resolution_GetScriptless"
0x14004c89d  mov     rdx, r12; char *
0x14004c8a0  mov     ecx, r15d; Level
0x14004c8a3  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004c8a8  cmp     [rsp+58h+arg_0], ebx
0x14004c8ac  jz      loc_14004C9F6
0x14004c8b2  call    ?WaitForProgressPage@@YAJXZ; WaitForProgressPage(void)
0x14004c8b7  mov     ebx, eax
0x14004c8b9  test    eax, eax
0x14004c8bb  jns     short loc_14004C8DE
0x14004c8bd  mov     r9d, 7BEh
0x14004c8c3  mov     [rsp+58h+var_38], eax
0x14004c8c7  lea     r8, aTrypauseresolu; "TryPauseResolution"
0x14004c8ce  mov     rdx, r12; char *
0x14004c8d1  mov     ecx, r15d; Level
0x14004c8d4  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004c8d9  jmp     loc_14004C9F9
0x14004c8de  cmp     eax, r15d
0x14004c8e1  jz      loc_14004C9F9
0x14004c8e7  lea     rcx, [rsp+58h+arg_10]; struct PageManager **
0x14004c8ec  call    ?Instance@PageManager@@SAJPEAPEAV1@@Z; PageManager::Instance(PageManager * *)
0x14004c8f1  mov     ebx, eax
0x14004c8f3  test    eax, eax
0x14004c8f5  jns     short loc_14004C8FF
0x14004c8f7  mov     r9d, 7C7h
0x14004c8fd  jmp     short loc_14004C8C3
0x14004c8ff  test    rdi, rdi
0x14004c902  jnz     short loc_14004C926
0x14004c904  mov     r9d, 27Eh
0x14004c90a  mov     [rsp+58h+var_38], 80070057h
0x14004c912  lea     r8, aPagemanagerPau; "PageManager::Pause"
0x14004c919  mov     rdx, r12; char *
0x14004c91c  mov     ecx, r15d; Level
0x14004c91f  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004c924  jmp     short loc_14004C964
0x14004c926  mov     rax, [rdi]
0x14004c929  mov     rcx, rdi
0x14004c92c  mov     rax, [rax+8]
0x14004c930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c935  mov     rcx, [rsp+58h+arg_10]
0x14004c93a  mov     rcx, [rcx+8]
0x14004c93e  call    cs:__imp_?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::TaskPage::GetParentHWND(void)
0x14004c945  nop     dword ptr [rax+rax+00h]
0x14004c94a  mov     r9, rdi; lParam
0x14004c94d  xor     r8d, r8d; wParam
0x14004c950  mov     rcx, rax; hWnd
0x14004c953  mov     edx, 9E1h; Msg
0x14004c958  call    cs:__imp_PostMessageW
0x14004c95f  nop     dword ptr [rax+rax+00h]
0x14004c964  xor     r8d, r8d; bWaitAll
0x14004c967  lea     rdx, ?g_EventsToWorker@@3PAPEAXA; lpHandles
0x14004c96e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14004c972  mov     esi, r15d
0x14004c975  lea     ecx, [r8+1Ch]; nCount
0x14004c979  call    cs:__imp_WaitForMultipleObjects
0x14004c980  nop     dword ptr [rax+rax+00h]
0x14004c985  cmp     eax, 14h
0x14004c988  jz      short loc_14004C9F6
0x14004c98a  cmp     eax, 1Bh
0x14004c98d  jz      short loc_14004C9A3
0x14004c98f  mov     ebx, 80004005h
0x14004c994  mov     r9d, 7E4h
0x14004c99a  mov     [rsp+58h+var_38], ebx
0x14004c99e  jmp     loc_14004C8C7
0x14004c9a3  mov     rcx, cs:qword_140080088; hEvent
0x14004c9aa  mov     cs:?g_Stop@@3HA, r15d; int g_Stop
0x14004c9b1  call    cs:__imp_SetEvent
0x14004c9b8  nop     dword ptr [rax+rax+00h]
0x14004c9bd  test    eax, eax
0x14004c9bf  jnz     short loc_14004C9EF
0x14004c9c1  call    cs:__imp_GetLastError
0x14004c9c8  nop     dword ptr [rax+rax+00h]
0x14004c9cd  mov     ebx, eax
0x14004c9cf  test    eax, eax
0x14004c9d1  jle     short loc_14004C9DC
0x14004c9d3  movzx   ebx, ax
0x14004c9d6  or      ebx, 80070000h
0x14004c9dc  test    ebx, ebx
0x14004c9de  jns     short loc_14004C9EF
0x14004c9e0  mov     [rsp+58h+var_38], ebx
0x14004c9e4  mov     r9d, 7D9h
0x14004c9ea  jmp     loc_14004C8C7
0x14004c9ef  mov     ebx, 80004004h
0x14004c9f4  jmp     short loc_14004C9F9
0x14004c9f6  mov     [r14], esi
0x14004c9f9  mov     eax, ebx
0x14004c9fb  mov     rbx, [rsp+58h+arg_8]
0x14004ca00  add     rsp, 30h
0x14004ca04  pop     r15
0x14004ca06  pop     r14
0x14004ca08  pop     r12
0x14004ca0a  pop     rdi
0x14004ca0b  pop     rsi
0x14004ca0c  retn
```

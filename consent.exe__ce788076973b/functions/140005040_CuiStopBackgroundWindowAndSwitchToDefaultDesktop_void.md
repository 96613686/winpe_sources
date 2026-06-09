# CuiStopBackgroundWindowAndSwitchToDefaultDesktop(void)

- ea: `0x140005040`
- end: `0x140005259`
- name: `?CuiStopBackgroundWindowAndSwitchToDefaultDesktop@@YAXXZ`
- size: `537`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14001a080`

## callees

- `0x140005040`
- `0x140005260`
- `0x1400056a0`
- `0x14000fbec`
- `0x14000fdc4`
- `0x140013928`

## import_xrefs

- `USER32!PostMessageW` at `0x140005185`
- `USER32!PostMessageW` at `0x140005185`
- `USER32!GetThreadDesktop` at `0x1400050bd`
- `USER32!GetThreadDesktop` at `0x1400050bd`
- `USER32!CloseDesktop` at `0x1400050d9`
- `USER32!CloseDesktop` at `0x1400050d9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000513e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000513e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000519e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000519e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400050f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400050f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000521d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000521d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000508d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000508d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400050b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400050b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400051f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400051f0`
- `WMsgAPI!WmsgSendMessage` at `0x1400050af`
- `WMsgAPI!WmsgSendMessage` at `0x1400050af`
- `ntdll!EtwEventWrite` at `0x140005087`
- `ntdll!EtwEventWrite` at `0x14000515f`
- `ntdll!EtwEventWrite` at `0x140005087`
- `ntdll!EtwEventWrite` at `0x14000515f`

## pseudocode

```c
void CuiStopBackgroundWindowAndSwitchToDefaultDesktop(void)
{
  wchar_t *DesktopName; // rbx
  DWORD CurrentProcessId; // eax
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  HDESK v4; // rdi
  DWORD LastError; // eax
  int i; // edi
  DWORD v7; // eax
  int v8; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+48h] [rbp+10h] BYREF

  DesktopName = 0;
  v9 = 0;
  if ( dword_140029BE4 )
  {
    EtwEventWrite(g_ConsentPerfRegHandle, ConsentUI_ReturnUserDesktop_Start, 0, 0);
    CurrentProcessId = GetCurrentProcessId();
    WmsgSendMessage(NtCurrentPeb()->SessionId, 1281, CurrentProcessId, &v9);
    CurrentThreadId = GetCurrentThreadId();
    ThreadDesktop = GetThreadDesktop(CurrentThreadId);
    v4 = ThreadDesktop;
    if ( ThreadDesktop )
    {
      DesktopName = CuipGetDesktopName(ThreadDesktop);
      CloseDesktop(v4);
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, LastError);
    }
    for ( i = 1; i < 10; ++i )
    {
      v8 = 0;
      if ( CuipCheckActiveDesktop(DesktopName, (enum ActiveDesktopType *)&v8) )
        break;
      if ( v8 != 3 )
        break;
      Sleep(0x3E8u);
    }
    EtwEventWrite(g_ConsentPerfRegHandle, ConsentUI_ReturnUserDesktop_Stop, 0, 0);
  }
  if ( hWnd )
  {
    PostMessageW(hWnd, 2u, 0, 0);
    hWnd = 0;
    if ( WaitForSingleObject(hObject, 0x2710u) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v7 = GetLastError();
        WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 111, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v7);
      }
      dword_140029BC8 = 1;
    }
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( dword_140029BBC )
  {
    dword_140029BBC = 0;
    CuipReleaseSessionMutex();
  }
  if ( DesktopName )
    LocalFree(DesktopName);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 112, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
}

```

## disassembly

```asm
0x140005040  sub     rsp, 38h
0x140005044  mov     [rsp+38h+arg_10], rbx
0x140005049  mov     [rsp+38h+var_8], rbp
0x14000504e  lea     rbp, WPP_GLOBAL_Control
0x140005055  mov     [rsp+38h+var_10], rsi
0x14000505a  xor     esi, esi
0x14000505c  mov     ebx, esi
0x14000505e  mov     [rsp+38h+arg_8], esi
0x140005062  cmp     cs:dword_140029BE4, ebx
0x140005068  jz      loc_14000516A
0x14000506e  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x140005075  lea     rdx, ConsentUI_ReturnUserDesktop_Start
0x14000507c  xor     r9d, r9d
0x14000507f  mov     [rsp+38h+var_18], rdi
0x140005084  xor     r8d, r8d
0x140005087  call    cs:__imp_EtwEventWrite
0x14000508d  call    cs:__imp_GetCurrentProcessId
0x140005093  mov     rcx, gs:60h
0x14000509c  lea     r9, [rsp+38h+arg_8]
0x1400050a1  mov     r8d, eax
0x1400050a4  mov     edx, 501h
0x1400050a9  mov     ecx, [rcx+2C0h]
0x1400050af  call    cs:__imp_WmsgSendMessage
0x1400050b5  call    cs:__imp_GetCurrentThreadId
0x1400050bb  mov     ecx, eax; dwThreadId
0x1400050bd  call    cs:__imp_GetThreadDesktop
0x1400050c3  mov     rdi, rax
0x1400050c6  test    rax, rax
0x1400050c9  jz      short loc_1400050E1
0x1400050cb  mov     rcx, rax; hObj
0x1400050ce  call    ?CuipGetDesktopName@@YAPEAGPEAUHDESK__@@@Z; CuipGetDesktopName(HDESK__ *)
0x1400050d3  mov     rcx, rdi; hDesktop
0x1400050d6  mov     rbx, rax
0x1400050d9  call    cs:__imp_CloseDesktop
0x1400050df  jmp     short loc_140005118
0x1400050e1  mov     rax, cs:WPP_GLOBAL_Control
0x1400050e8  cmp     rax, rbp
0x1400050eb  jz      short loc_140005118
0x1400050ed  test    byte ptr [rax+1Ch], 4
0x1400050f1  jz      short loc_140005118
0x1400050f3  call    cs:__imp_GetLastError
0x1400050f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140005100  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140005107  mov     edx, 0Dh
0x14000510c  mov     r9d, eax
0x14000510f  mov     rcx, [rcx+10h]
0x140005113  call    WPP_SF_D
0x140005118  mov     edi, 1
0x14000511d  lea     rdx, [rsp+38h+arg_0]; enum ActiveDesktopType *
0x140005122  mov     [rsp+38h+arg_0], esi
0x140005126  mov     rcx, rbx; String2
0x140005129  call    ?CuipCheckActiveDesktop@@YAKPEBGPEAW4ActiveDesktopType@@@Z; CuipCheckActiveDesktop(ushort const *,ActiveDesktopType *)
0x14000512e  test    eax, eax
0x140005130  jnz     short loc_14000514B
0x140005132  cmp     [rsp+38h+arg_0], 3
0x140005137  jnz     short loc_14000514B
0x140005139  mov     ecx, 3E8h; dwMilliseconds
0x14000513e  call    cs:__imp_Sleep
0x140005144  inc     edi
0x140005146  cmp     edi, 0Ah
0x140005149  jl      short loc_14000511D
0x14000514b  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x140005152  lea     rdx, ConsentUI_ReturnUserDesktop_Stop
0x140005159  xor     r9d, r9d
0x14000515c  xor     r8d, r8d
0x14000515f  call    cs:__imp_EtwEventWrite
0x140005165  mov     rdi, [rsp+38h+var_18]
0x14000516a  mov     rcx, cs:hWnd; hWnd
0x140005171  test    rcx, rcx
0x140005174  jz      loc_1400051FD
0x14000517a  xor     r9d, r9d; lParam
0x14000517d  xor     r8d, r8d; wParam
0x140005180  mov     edx, 2; Msg
0x140005185  call    cs:__imp_PostMessageW
0x14000518b  mov     rcx, cs:hObject; hHandle
0x140005192  mov     edx, 2710h; dwMilliseconds
0x140005197  mov     cs:hWnd, rsi
0x14000519e  call    cs:__imp_WaitForSingleObject
0x1400051a4  test    eax, eax
0x1400051a6  jz      short loc_1400051E9
0x1400051a8  mov     rax, cs:WPP_GLOBAL_Control
0x1400051af  cmp     rax, rbp
0x1400051b2  jz      short loc_1400051DF
0x1400051b4  test    byte ptr [rax+1Ch], 4
0x1400051b8  jz      short loc_1400051DF
0x1400051ba  call    cs:__imp_GetLastError
0x1400051c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400051c7  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x1400051ce  mov     edx, 6Fh ; 'o'
0x1400051d3  mov     r9d, eax
0x1400051d6  mov     rcx, [rcx+10h]
0x1400051da  call    WPP_SF_D
0x1400051df  mov     cs:dword_140029BC8, 1
0x1400051e9  mov     rcx, cs:hObject; hObject
0x1400051f0  call    cs:__imp_CloseHandle
0x1400051f6  mov     cs:hObject, rsi
0x1400051fd  cmp     cs:dword_140029BBC, esi
0x140005203  jz      short loc_140005210
0x140005205  mov     cs:dword_140029BBC, esi
0x14000520b  call    ?CuipReleaseSessionMutex@@YAXXZ; CuipReleaseSessionMutex(void)
0x140005210  mov     rsi, [rsp+38h+var_10]
0x140005215  test    rbx, rbx
0x140005218  jz      short loc_140005223
0x14000521a  mov     rcx, rbx; hMem
0x14000521d  call    cs:__imp_LocalFree
0x140005223  mov     rcx, cs:WPP_GLOBAL_Control
0x14000522a  mov     rbx, [rsp+38h+arg_10]
0x14000522f  cmp     rcx, rbp
0x140005232  mov     rbp, [rsp+38h+var_8]
0x140005237  jz      short loc_140005254
0x140005239  test    byte ptr [rcx+1Ch], 4
0x14000523d  jz      short loc_140005254
0x14000523f  mov     rcx, [rcx+10h]
0x140005243  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000524a  mov     edx, 70h ; 'p'
0x14000524f  call    WPP_SF_
0x140005254  add     rsp, 38h
0x140005258  retn
```

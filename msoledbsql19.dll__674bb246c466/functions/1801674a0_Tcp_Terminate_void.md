# Tcp::Terminate(void)

- ea: `0x1801674a0`
- end: `0x180167671`
- name: `?Terminate@Tcp@@SAKXZ`
- size: `465`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x18015beb0`

## callees

- `0x180001f70`
- `0x1800030c0`
- `0x180003d80`
- `0x1801595c0`
- `0x1801674a0`
- `0x18017f7e0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1801675c9`
- `KERNEL32!FreeLibrary` at `0x1801675c9`
- `KERNEL32!GetLastError` at `0x1801675d3`
- `KERNEL32!GetLastError` at `0x1801675d3`
- `WS2_32!__imp_WSACleanup` at `0x1801675ac`
- `WS2_32!__imp_WSACleanup` at `0x1801675ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Tcp::Terminate(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  wchar_t *v4; // r8
  __int64 v5; // rdx
  char *v6; // rcx
  unsigned int v7; // eax
  DWORD LastError; // eax
  __int64 v10; // [rsp+40h] [rbp-18h] BYREF

  v10 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266A20[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      &v10,
      off_180266A20[0],
      0);
  if ( dword_180253978 )
  {
    if ( g_hCleanupSendNotificationTimer )
    {
      v7 = SNIStopTimerTask(g_hCleanupSendNotificationTimer, a2, a3, a4);
      g_hCleanupSendNotificationTimer = 0;
      if ( v7 != 997 && (bidGblFlags & 2) != 0 && off_180264798[0] )
        bidTraceW(off_180261450[0], 3351552, off_180264798[0], v7);
    }
    WSACleanup();
    dword_180253978 = 0;
    SNI::detail::Transport::StaticTerminate();
    if ( Tcp::s_hWS2_32 )
    {
      if ( !FreeLibrary(Tcp::s_hWS2_32) )
      {
        LastError = GetLastError();
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1802647A0[0] )
            bidTraceW(off_180261458[0], 3366912, off_1802647A0[0], LastError);
        }
      }
    }
    Tcp::s_hWS2_32 = 0;
    Tcp::s_pfnWSAPoll = 0;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802647A8[0] )
    {
      v4 = off_1802647A8[0];
      v5 = 3374080;
      v6 = off_180261460[0];
      goto LABEL_22;
    }
  }
  else if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264790[0] )
  {
    v4 = off_180264790[0];
    v5 = 3339264;
    v6 = off_180261448[0];
LABEL_22:
    bidTraceW(v6, v5, v4, 0);
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v10);
  return 0;
}

```

## disassembly

```asm
0x1801674a0  push    rbx
0x1801674a2  sub     rsp, 50h
0x1801674a6  mov     rax, cs:__security_cookie
0x1801674ad  xor     rax, rsp
0x1801674b0  mov     [rsp+58h+var_10], rax
0x1801674b5  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFFh
0x1801674be  mov     eax, cs:_bidGblFlags
0x1801674c4  and     eax, 20004h
0x1801674c9  xor     ebx, ebx
0x1801674cb  cmp     eax, 20004h
0x1801674d0  jnz     short loc_180167517
0x1801674d2  mov     rax, cs:off_180266A20; "<Tcp::Terminate|API|SNI> \n"
0x1801674d9  test    rax, rax
0x1801674dc  jz      short loc_180167517
0x1801674de  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1801674e6  jz      short loc_180167517
0x1801674e8  mov     rax, cs:off_180248060
0x1801674ef  mov     [rsp+58h+var_30], rbx
0x1801674f4  mov     rcx, cs:off_180266A20; "<Tcp::Terminate|API|SNI> \n"
0x1801674fb  mov     [rsp+58h+var_38], rcx
0x180167500  lea     r9, [rsp+58h+var_18]
0x180167505  xor     r8d, r8d
0x180167508  xor     edx, edx
0x18016750a  mov     rcx, cs:_bidID
0x180167511  call    cs:__guard_dispatch_icall_fptr
0x180167517  cmp     cs:dword_180253978, ebx
0x18016751d  jnz     short loc_18016755D
0x18016751f  mov     eax, cs:_bidGblFlags
0x180167525  and     eax, 20002h
0x18016752a  cmp     eax, 20002h
0x18016752f  jnz     loc_180167651
0x180167535  mov     rax, cs:off_180264790; "<Tcp::Terminate|RET|SNI> %d{WINERR}\n"
0x18016753c  test    rax, rax
0x18016753f  jz      loc_180167651
0x180167545  mov     r8, cs:off_180264790; "<Tcp::Terminate|RET|SNI> %d{WINERR}\n"
0x18016754c  mov     edx, 32F400h
0x180167551  mov     rcx, cs:off_180261448; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167558  jmp     loc_180167648
0x18016755d  mov     rcx, cs:?g_hCleanupSendNotificationTimer@@3PEAXEA; Timer
0x180167564  test    rcx, rcx
0x180167567  jz      short loc_1801675AC
0x180167569  call    SNIStopTimerTask
0x18016756e  mov     cs:?g_hCleanupSendNotificationTimer@@3PEAXEA, rbx; void * g_hCleanupSendNotificationTimer
0x180167575  cmp     eax, 3E5h
0x18016757a  jz      short loc_1801675AC
0x18016757c  test    byte ptr cs:_bidGblFlags, 2
0x180167583  jz      short loc_1801675AC
0x180167585  mov     rcx, cs:off_180264798; "<Tcp::Terminate|ERR|SNI> SNIStopTimerTa"...
0x18016758c  test    rcx, rcx
0x18016758f  jz      short loc_1801675AC
0x180167591  mov     r9d, eax
0x180167594  mov     r8, cs:off_180264798; "<Tcp::Terminate|ERR|SNI> SNIStopTimerTa"...
0x18016759b  mov     edx, 332400h
0x1801675a0  mov     rcx, cs:off_180261450; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801675a7  call    _bidTraceW
0x1801675ac  call    cs:__imp_WSACleanup
0x1801675b2  mov     cs:dword_180253978, ebx
0x1801675b8  call    ?StaticTerminate@Transport@detail@SNI@@SAXXZ; SNI::detail::Transport::StaticTerminate(void)
0x1801675bd  mov     rcx, cs:?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA; hLibModule
0x1801675c4  test    rcx, rcx
0x1801675c7  jz      short loc_180167609
0x1801675c9  call    cs:__imp_FreeLibrary
0x1801675cf  test    eax, eax
0x1801675d1  jnz     short loc_180167609
0x1801675d3  call    cs:__imp_GetLastError
0x1801675d9  test    byte ptr cs:_bidGblFlags, 2
0x1801675e0  jz      short loc_180167609
0x1801675e2  mov     rcx, cs:off_1802647A0; "<Tcp::Terminate|ERR|SNI> FreeLibrary fo"...
0x1801675e9  test    rcx, rcx
0x1801675ec  jz      short loc_180167609
0x1801675ee  mov     r9d, eax
0x1801675f1  mov     r8, cs:off_1802647A0; "<Tcp::Terminate|ERR|SNI> FreeLibrary fo"...
0x1801675f8  mov     edx, 336000h
0x1801675fd  mov     rcx, cs:off_180261458; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167604  call    _bidTraceW
0x180167609  mov     cs:?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * Tcp::s_hWS2_32
0x180167610  mov     cs:?s_pfnWSAPoll@Tcp@@1P6AHQEAUpollfd@@KH@ZEA, rbx; int (*Tcp::s_pfnWSAPoll)(pollfd * const,ulong,int)
0x180167617  mov     eax, cs:_bidGblFlags
0x18016761d  and     eax, 20002h
0x180167622  cmp     eax, 20002h
0x180167627  jnz     short loc_180167651
0x180167629  mov     rax, cs:off_1802647A8; "<Tcp::Terminate|RET|SNI> %d{WINERR}\n"
0x180167630  test    rax, rax
0x180167633  jz      short loc_180167651
0x180167635  mov     r8, cs:off_1802647A8; "<Tcp::Terminate|RET|SNI> %d{WINERR}\n"
0x18016763c  mov     edx, 337C00h
0x180167641  mov     rcx, cs:off_180261460; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167648  xor     r9d, r9d
0x18016764b  call    _bidTraceW
0x180167650  nop
0x180167651  lea     rcx, [rsp+58h+var_18]; this
0x180167656  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18016765b  nop
0x18016765c  xor     eax, eax
0x18016765e  mov     rcx, [rsp+58h+var_10]
0x180167663  xor     rcx, rsp; StackCookie
0x180167666  call    __security_check_cookie
0x18016766b  add     rsp, 50h
0x18016766f  pop     rbx
0x180167670  retn
```

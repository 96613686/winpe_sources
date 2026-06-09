# Tcp::Initialize(SNI_PROVIDER_INFO *)

- ea: `0x100434d74`
- end: `0x100435154`
- name: `?Initialize@Tcp@@SAKPEAUSNI_PROVIDER_INFO@@@Z`
- size: `992`
- prototype: `unsigned int __fastcall(struct SNI_PROVIDER_INFO *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task`

## callers

- `0x10041a108`

## callees

- `0x100416e54`
- `0x1004194b0`
- `0x100434218`
- `0x100434d74`
- `0x1004354b4`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043b49c`
- `0x10043b698`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x100434ec8`
- `KERNEL32!InitializeSListHead` at `0x100434ec8`
- `KERNEL32!GetLastError` at `0x10043505f`
- `KERNEL32!GetLastError` at `0x10043505f`
- `KERNEL32!FreeLibrary` at `0x100435055`
- `KERNEL32!FreeLibrary` at `0x100435055`
- `WS2_32!__imp_WSAGetLastError` at `0x100434fba`
- `WS2_32!__imp_WSAGetLastError` at `0x100434fba`
- `WS2_32!__imp_WSAStartup` at `0x100434ded`
- `WS2_32!__imp_WSAStartup` at `0x100434e0a`
- `WS2_32!__imp_WSAStartup` at `0x100434ded`
- `WS2_32!__imp_WSAStartup` at `0x100434e0a`
- `WS2_32!__imp_WSACleanup` at `0x100434faf`
- `WS2_32!__imp_WSACleanup` at `0x100434faf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Tcp::Initialize(struct SNI_PROVIDER_INFO *a1)
{
  char v2; // bp
  unsigned int WSAPoll; // ebx
  wchar_t *v4; // r8
  __int64 v5; // rdx
  unsigned int Error; // eax
  unsigned int v7; // eax
  DWORD LastError; // eax
  _QWORD v10[2]; // [rsp+30h] [rbp-1C8h] BYREF
  WSAData WSAData; // [rsp+40h] [rbp-1B8h] BYREF

  v10[1] = -2;
  v10[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7D28[0] )
    bidScopeEnterW(v10, off_1005E7D28[0], a1);
  v2 = 0;
  if ( WSAStartup(0x202u, &WSAData) )
  {
    WSAPoll = WSAStartup(0x101u, &WSAData);
    if ( WSAPoll )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E5888[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          2549760,
          off_1005E5888[0],
          0);
      if ( (bidGblFlags & 2) != 0 && off_1005E5890[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(0, 2550784, off_1005E5890[0], 7);
      }
      SNISetLastError(7, WSAPoll, 50100);
LABEL_33:
      if ( Tcp::s_fAutoTuning )
      {
        if ( g_hCleanupSendNotificationTimer )
        {
          v7 = SNIStopTimerTask((__int64)g_hCleanupSendNotificationTimer);
          g_hCleanupSendNotificationTimer = 0;
          if ( v7 != 997 && (bidGblFlags & 2) != 0 && off_1005E58C0[0] )
            bidTraceW(0, 2632704, off_1005E58C0[0], v7);
        }
      }
      if ( v2 )
        SNI::detail::Transport::StaticTerminate();
      if ( Tcp::s_hWS2_32 )
      {
        if ( !FreeLibrary(Tcp::s_hWS2_32) )
        {
          LastError = GetLastError();
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_1005E58C8[0] )
              bidTraceW(0, 2650112, off_1005E58C8[0], LastError);
          }
        }
        Tcp::s_hWS2_32 = 0;
      }
      Tcp::s_pfnWSAPoll = 0;
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E58D0[0] )
        bidTraceW(0, 2658304, off_1005E58D0[0], WSAPoll);
      goto LABEL_54;
    }
  }
  if ( Tcp::s_fAutoTuning )
  {
    InitializeSListHead(&Tcp::s_slhNotificationsToClose);
    WSAPoll = SNIEnqueueTimerTask(
                (__int64 *)&g_hCleanupSendNotificationTimer,
                (__int64)Tcp::CleanupSendNotifications,
                0,
                0x1388u);
    if ( WSAPoll )
    {
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5898[0] )
      {
        v4 = off_1005E5898[0];
        v5 = 2571264;
LABEL_28:
        bidTraceW(0, v5, v4, WSAPoll);
        goto LABEL_29;
      }
      goto LABEL_29;
    }
  }
  WSAPoll = SNI::detail::Transport::StaticInitialize();
  if ( WSAPoll )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E58A0[0] )
    {
      v4 = off_1005E58A0[0];
      v5 = 2580480;
      goto LABEL_28;
    }
LABEL_29:
    if ( WSACleanup() == -1 )
    {
      Error = WSAGetLastError();
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1005E58B8[0] )
          bidTraceW(0, 2618368, off_1005E58B8[0], Error);
      }
    }
    goto LABEL_33;
  }
  v2 = 1;
  if ( g_osviSNI.dwMajorVersion >= 6 )
  {
    WSAPoll = LoadWSAPoll(&Tcp::s_pfnWSAPoll, &Tcp::s_hWS2_32);
    if ( WSAPoll )
    {
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E58A8[0] )
      {
        v4 = off_1005E58A8[0];
        v5 = 2591744;
        goto LABEL_28;
      }
      goto LABEL_29;
    }
  }
  Tcp::s_fSupportsFlagNoHandleInherit = FOSSupportsFlagNoHandleInherit();
  *((_DWORD *)a1 + 3) = 1;
  *((_DWORD *)a1 + 1) = 0;
  *((_DWORD *)a1 + 2) = 0;
  *(_DWORD *)a1 = 7;
  *((_DWORD *)a1 + 4) = 1;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E58B0[0] )
    bidTraceW(0, 2608128, off_1005E58B0[0], 0);
  WSAPoll = 0;
LABEL_54:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v10);
  return WSAPoll;
}

```

## disassembly

```asm
0x100434d74  mov     rax, rsp
0x100434d77  push    rdi
0x100434d78  sub     rsp, 1F0h
0x100434d7f  mov     [rsp+1F8h+var_1C0], 0FFFFFFFFFFFFFFFEh
0x100434d88  mov     [rax+10h], rbx
0x100434d8c  mov     [rax+18h], rbp
0x100434d90  mov     [rax+20h], rsi
0x100434d94  mov     rax, cs:__security_cookie
0x100434d9b  xor     rax, rsp
0x100434d9e  mov     [rsp+1F8h+var_18], rax
0x100434da6  mov     rsi, rcx
0x100434da9  or      [rsp+1F8h+var_1C8], 0FFFFFFFFFFFFFFFFh
0x100434daf  mov     eax, cs:_bidGblFlags
0x100434db5  mov     ecx, 20004h
0x100434dba  and     eax, ecx
0x100434dbc  cmp     eax, ecx
0x100434dbe  jnz     short loc_100434DE0
0x100434dc0  mov     rax, cs:off_1005E7D28; "<Tcp::Initialize|API|SNI> pInfo: %p{PSN"...
0x100434dc7  test    rax, rax
0x100434dca  jz      short loc_100434DE0
0x100434dcc  mov     r8, rsi
0x100434dcf  mov     rdx, cs:off_1005E7D28; "<Tcp::Initialize|API|SNI> pInfo: %p{PSN"...
0x100434dd6  lea     rcx, [rsp+1F8h+var_1C8]
0x100434ddb  call    _bidScopeEnterW
0x100434de0  xor     bpl, bpl
0x100434de3  mov     ecx, 202h; wVersionRequested
0x100434de8  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x100434ded  call    cs:__imp_WSAStartup
0x100434df3  mov     edi, 20002h
0x100434df8  test    eax, eax
0x100434dfa  jz      loc_100434EB8
0x100434e00  mov     ecx, 101h; wVersionRequested
0x100434e05  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x100434e0a  call    cs:__imp_WSAStartup
0x100434e10  mov     ebx, eax
0x100434e12  test    eax, eax
0x100434e14  jz      loc_100434EB8
0x100434e1a  test    byte ptr cs:_bidGblFlags, 2
0x100434e21  jz      short loc_100434E62
0x100434e23  mov     rax, cs:off_1005E5888; "<Tcp::Initialize|ERR|SNI> Winsock libra"...
0x100434e2a  test    rax, rax
0x100434e2d  jz      short loc_100434E62
0x100434e2f  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100434e37  jz      short loc_100434E62
0x100434e39  mov     rax, cs:off_1005D39E0
0x100434e40  and     [rsp+1F8h+var_1D8], 0
0x100434e46  mov     r9, cs:off_1005E5888; "<Tcp::Initialize|ERR|SNI> Winsock libra"...
0x100434e4d  xor     edx, edx
0x100434e4f  mov     r8d, 26E800h
0x100434e55  mov     rcx, cs:_bidID
0x100434e5c  call    cs:__guard_dispatch_icall_fptr
0x100434e62  mov     esi, 0C3B4h
0x100434e67  test    byte ptr cs:_bidGblFlags, 2
0x100434e6e  jz      short loc_100434EA4
0x100434e70  mov     rax, cs:off_1005E5890; "<Tcp::Initialize|ERR|SNI> ProviderNum: "...
0x100434e77  test    rax, rax
0x100434e7a  jz      short loc_100434EA4
0x100434e7c  mov     ecx, esi; unsigned int
0x100434e7e  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100434e83  mov     [rsp+1F8h+var_1D0], ebx
0x100434e87  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x100434e8b  mov     r9d, 7
0x100434e91  mov     r8, cs:off_1005E5890; "<Tcp::Initialize|ERR|SNI> ProviderNum: "...
0x100434e98  mov     edx, 26EC00h
0x100434e9d  xor     ecx, ecx
0x100434e9f  call    _bidTraceW
0x100434ea4  mov     r8d, esi
0x100434ea7  mov     edx, ebx
0x100434ea9  mov     ecx, 7
0x100434eae  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100434eb3  jmp     loc_100434FEB
0x100434eb8  cmp     cs:?s_fAutoTuning@Tcp@@2HA, 0; int Tcp::s_fAutoTuning
0x100434ebf  jz      short loc_100434F21
0x100434ec1  lea     rcx, ?s_slhNotificationsToClose@Tcp@@1T_SLIST_HEADER@@A; ListHead
0x100434ec8  call    cs:__imp_InitializeSListHead
0x100434ece  mov     r9d, 1388h
0x100434ed4  xor     r8d, r8d
0x100434ed7  lea     rdx, ?CleanupSendNotifications@Tcp@@CA?AW4SOS_TIMERRESULT@@PEAXPEAK1@Z; Tcp::CleanupSendNotifications(void *,ulong *,ulong *)
0x100434ede  lea     rcx, ?g_hCleanupSendNotificationTimer@@3PEAXEA; void * g_hCleanupSendNotificationTimer
0x100434ee5  call    SNIEnqueueTimerTask
0x100434eea  mov     ebx, eax
0x100434eec  test    eax, eax
0x100434eee  jz      short loc_100434F21
0x100434ef0  mov     eax, cs:_bidGblFlags
0x100434ef6  and     eax, edi
0x100434ef8  cmp     eax, edi
0x100434efa  jnz     loc_100434FAF
0x100434f00  mov     rax, cs:off_1005E5898; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x100434f07  test    rax, rax
0x100434f0a  jz      loc_100434FAF
0x100434f10  mov     r8, cs:off_1005E5898; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x100434f17  mov     edx, 273C00h
0x100434f1c  jmp     loc_100434FA5
0x100434f21  call    ?StaticInitialize@Transport@detail@SNI@@SAKXZ; SNI::detail::Transport::StaticInitialize(void)
0x100434f26  mov     ebx, eax
0x100434f28  test    eax, eax
0x100434f2a  jz      short loc_100434F52
0x100434f2c  mov     eax, cs:_bidGblFlags
0x100434f32  and     eax, edi
0x100434f34  cmp     eax, edi
0x100434f36  jnz     short loc_100434FAF
0x100434f38  mov     rax, cs:off_1005E58A0; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x100434f3f  test    rax, rax
0x100434f42  jz      short loc_100434FAF
0x100434f44  mov     r8, cs:off_1005E58A0; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x100434f4b  mov     edx, 276000h
0x100434f50  jmp     short loc_100434FA5
0x100434f52  mov     ebp, 1
0x100434f57  cmp     cs:?g_osviSNI@@3U_OSVERSIONINFOEXW@@A.dwMajorVersion, 6; _OSVERSIONINFOEXW g_osviSNI ...
0x100434f5e  jb      loc_1004350D0
0x100434f64  lea     rdx, ?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA; HINSTANCE *
0x100434f6b  lea     rcx, ?s_pfnWSAPoll@Tcp@@1P6AHQEAUpollfd@@KH@ZEA; int (**)(struct pollfd *const, unsigned int, int)
0x100434f72  call    ?LoadWSAPoll@@YAKPEAP6AHQEAUpollfd@@KH@ZPEAPEAUHINSTANCE__@@@Z; LoadWSAPoll(int (**)(pollfd * const,ulong,int),HINSTANCE__ * *)
0x100434f77  mov     ebx, eax
0x100434f79  test    eax, eax
0x100434f7b  jz      loc_1004350D0
0x100434f81  mov     eax, cs:_bidGblFlags
0x100434f87  and     eax, edi
0x100434f89  cmp     eax, edi
0x100434f8b  jnz     short loc_100434FAF
0x100434f8d  mov     rax, cs:off_1005E58A8; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x100434f94  test    rax, rax
0x100434f97  jz      short loc_100434FAF
0x100434f99  mov     r8, cs:off_1005E58A8; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x100434fa0  mov     edx, 278C00h
0x100434fa5  mov     r9d, ebx
0x100434fa8  xor     ecx, ecx
0x100434faa  call    _bidTraceW
0x100434faf  call    cs:__imp_WSACleanup
0x100434fb5  cmp     eax, 0FFFFFFFFh
0x100434fb8  jnz     short loc_100434FEB
0x100434fba  call    cs:__imp_WSAGetLastError
0x100434fc0  test    byte ptr cs:_bidGblFlags, 2
0x100434fc7  jz      short loc_100434FEB
0x100434fc9  mov     rcx, cs:off_1005E58B8; "<Tcp::Initialize|ERR|SNI> WSACleanup fa"...
0x100434fd0  test    rcx, rcx
0x100434fd3  jz      short loc_100434FEB
0x100434fd5  mov     r9d, eax
0x100434fd8  mov     r8, cs:off_1005E58B8; "<Tcp::Initialize|ERR|SNI> WSACleanup fa"...
0x100434fdf  mov     edx, 27F400h
0x100434fe4  xor     ecx, ecx
0x100434fe6  call    _bidTraceW
0x100434feb  cmp     cs:?s_fAutoTuning@Tcp@@2HA, 0; int Tcp::s_fAutoTuning
0x100434ff2  jz      short loc_10043503F
0x100434ff4  mov     rcx, cs:?g_hCleanupSendNotificationTimer@@3PEAXEA; void * g_hCleanupSendNotificationTimer
0x100434ffb  test    rcx, rcx
0x100434ffe  jz      short loc_10043503F
0x100435000  call    SNIStopTimerTask
0x100435005  and     cs:?g_hCleanupSendNotificationTimer@@3PEAXEA, 0; void * g_hCleanupSendNotificationTimer
0x10043500d  cmp     eax, 3E5h
0x100435012  jz      short loc_10043503F
0x100435014  test    byte ptr cs:_bidGblFlags, 2
0x10043501b  jz      short loc_10043503F
0x10043501d  mov     rcx, cs:off_1005E58C0; "<Tcp::Initialize|ERR|SNI> SNIStopTimerT"...
0x100435024  test    rcx, rcx
0x100435027  jz      short loc_10043503F
0x100435029  mov     r9d, eax
0x10043502c  mov     r8, cs:off_1005E58C0; "<Tcp::Initialize|ERR|SNI> SNIStopTimerT"...
0x100435033  mov     edx, 282C00h
0x100435038  xor     ecx, ecx
0x10043503a  call    _bidTraceW
0x10043503f  test    bpl, bpl
0x100435042  jz      short loc_100435049
0x100435044  call    ?StaticTerminate@Transport@detail@SNI@@SAXXZ; SNI::detail::Transport::StaticTerminate(void)
0x100435049  mov     rcx, cs:?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA; hLibModule
0x100435050  test    rcx, rcx
0x100435053  jz      short loc_100435098
0x100435055  call    cs:__imp_FreeLibrary
0x10043505b  test    eax, eax
0x10043505d  jnz     short loc_100435090
0x10043505f  call    cs:__imp_GetLastError
0x100435065  test    byte ptr cs:_bidGblFlags, 2
0x10043506c  jz      short loc_100435090
0x10043506e  mov     rcx, cs:off_1005E58C8; "<Tcp::Initialize|ERR|SNI> FreeLibrary(W"...
0x100435075  test    rcx, rcx
0x100435078  jz      short loc_100435090
0x10043507a  mov     r9d, eax
0x10043507d  mov     r8, cs:off_1005E58C8; "<Tcp::Initialize|ERR|SNI> FreeLibrary(W"...
0x100435084  mov     edx, 287000h
0x100435089  xor     ecx, ecx
0x10043508b  call    _bidTraceW
0x100435090  and     cs:?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Tcp::s_hWS2_32
0x100435098  and     cs:?s_pfnWSAPoll@Tcp@@1P6AHQEAUpollfd@@KH@ZEA, 0; int (*Tcp::s_pfnWSAPoll)(pollfd * const,ulong,int)
0x1004350a0  mov     eax, cs:_bidGblFlags
0x1004350a6  and     eax, edi
0x1004350a8  cmp     eax, edi
0x1004350aa  jnz     short loc_10043511F
0x1004350ac  mov     rax, cs:off_1005E58D0; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x1004350b3  test    rax, rax
0x1004350b6  jz      short loc_10043511F
0x1004350b8  mov     r9d, ebx
0x1004350bb  mov     r8, cs:off_1005E58D0; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x1004350c2  mov     edx, 289000h
0x1004350c7  xor     ecx, ecx
0x1004350c9  call    _bidTraceW
0x1004350ce  jmp     short loc_10043511F
0x1004350d0  call    ?FOSSupportsFlagNoHandleInherit@@YA_NXZ; FOSSupportsFlagNoHandleInherit(void)
0x1004350d5  mov     cs:?s_fSupportsFlagNoHandleInherit@Tcp@@1_NA, al; bool Tcp::s_fSupportsFlagNoHandleInherit
0x1004350db  mov     [rsi+0Ch], ebp
0x1004350de  and     dword ptr [rsi+4], 0
0x1004350e2  and     dword ptr [rsi+8], 0
0x1004350e6  mov     dword ptr [rsi], 7
0x1004350ec  mov     [rsi+10h], ebp
0x1004350ef  mov     eax, cs:_bidGblFlags
0x1004350f5  and     eax, edi
0x1004350f7  cmp     eax, edi
0x1004350f9  jnz     short loc_10043511D
0x1004350fb  mov     rax, cs:off_1005E58B0; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x100435102  test    rax, rax
0x100435105  jz      short loc_10043511D
0x100435107  xor     r9d, r9d
0x10043510a  mov     r8, cs:off_1005E58B0; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x100435111  mov     edx, 27CC00h
0x100435116  xor     ecx, ecx
0x100435118  call    _bidTraceW
0x10043511d  xor     ebx, ebx
0x10043511f  lea     rcx, [rsp+1F8h+var_1C8]; this
0x100435124  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100435129  mov     eax, ebx
0x10043512b  mov     rcx, [rsp+1F8h+var_18]
0x100435133  xor     rcx, rsp; StackCookie
0x100435136  call    __security_check_cookie
0x10043513b  lea     r11, [rsp+1F8h+var_8]
0x100435143  mov     rbx, [r11+18h]
0x100435147  mov     rbp, [r11+20h]
0x10043514b  mov     rsi, [r11+28h]
0x10043514f  mov     rsp, r11
0x100435152  pop     rdi
0x100435153  retn
```

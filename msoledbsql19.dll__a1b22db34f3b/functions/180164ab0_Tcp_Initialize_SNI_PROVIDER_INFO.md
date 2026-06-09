# Tcp::Initialize(SNI_PROVIDER_INFO *)

- ea: `0x180164ab0`
- end: `0x180164ef8`
- name: `?Initialize@Tcp@@SAKPEAUSNI_PROVIDER_INFO@@@Z`
- size: `1096`
- prototype: `unsigned int __fastcall(struct SNI_PROVIDER_INFO *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task`

## callers

- `0x18015ba10`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180156c10`
- `0x1801595c0`
- `0x18015a6f0`
- `0x18015a880`
- `0x180163f60`
- `0x180164ab0`
- `0x1801652a0`
- `0x18017f4d0`
- `0x18017f7e0`
- `0x1801a65e1`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180164dd7`
- `KERNEL32!FreeLibrary` at `0x180164dd7`
- `KERNEL32!GetLastError` at `0x180164de1`
- `KERNEL32!GetLastError` at `0x180164de1`
- `KERNEL32!InitializeSListHead` at `0x180164c1b`
- `KERNEL32!InitializeSListHead` at `0x180164c1b`
- `WS2_32!__imp_WSAGetLastError` at `0x180164d34`
- `WS2_32!__imp_WSAGetLastError` at `0x180164d34`
- `WS2_32!__imp_WSAStartup` at `0x180164b36`
- `WS2_32!__imp_WSAStartup` at `0x180164b50`
- `WS2_32!__imp_WSAStartup` at `0x180164b36`
- `WS2_32!__imp_WSAStartup` at `0x180164b50`
- `WS2_32!__imp_WSACleanup` at `0x180164d29`
- `WS2_32!__imp_WSACleanup` at `0x180164d29`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Tcp::Initialize(struct SNI_PROVIDER_INFO *a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v5; // si
  unsigned int WSAPoll; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  wchar_t *v10; // r8
  __int64 v11; // rdx
  char *v12; // rcx
  unsigned int Error; // eax
  unsigned int v14; // eax
  DWORD LastError; // eax
  _QWORD v17[2]; // [rsp+30h] [rbp-1C8h] BYREF
  WSAData WSAData; // [rsp+40h] [rbp-1B8h] BYREF

  v17[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1802669F0[0] )
    bidScopeEnterW(v17, off_1802669F0[0], a1, a4);
  memset_0(&WSAData, 0, sizeof(WSAData));
  v5 = 0;
  if ( WSAStartup(0x202u, &WSAData) )
  {
    WSAPoll = WSAStartup(0x101u, &WSAData);
    if ( WSAPoll )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180264670[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
            bidID,
            off_180261328[0],
            2553856,
            off_180264670[0],
            0);
        if ( (bidGblFlags & 2) != 0 && off_180264678[0] )
        {
          SniErrorIdFromStringId(0xC3B4u);
          bidTraceW(off_180261330[0], 2554880, off_180264678[0], 6);
        }
      }
      SNISetLastError(6, WSAPoll, 50100);
LABEL_33:
      if ( Tcp::s_fAutoTuning )
      {
        if ( g_hCleanupSendNotificationTimer )
        {
          v14 = SNIStopTimerTask(g_hCleanupSendNotificationTimer, v7, v8, v9);
          g_hCleanupSendNotificationTimer = 0;
          if ( v14 != 997 && (bidGblFlags & 2) != 0 && off_1802646A8[0] )
            bidTraceW(off_180261360[0], 2636800, off_1802646A8[0], v14);
        }
      }
      if ( v5 )
        SNI::detail::Transport::StaticTerminate();
      if ( Tcp::s_hWS2_32 )
      {
        if ( !FreeLibrary(Tcp::s_hWS2_32) )
        {
          LastError = GetLastError();
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_1802646B0[0] )
              bidTraceW(off_180261368[0], 2654208, off_1802646B0[0], LastError);
          }
        }
        Tcp::s_hWS2_32 = 0;
      }
      Tcp::s_pfnWSAPoll = 0;
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802646B8[0] )
        bidTraceW(off_180261370[0], 2662400, off_1802646B8[0], WSAPoll);
      goto LABEL_54;
    }
  }
  if ( Tcp::s_fAutoTuning )
  {
    InitializeSListHead(&Tcp::s_slhNotificationsToClose);
    WSAPoll = SNIEnqueueTimerTask(&g_hCleanupSendNotificationTimer, (__int64)Tcp::CleanupSendNotifications, 0, 0x1388u);
    if ( WSAPoll )
    {
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264680[0] )
      {
        v10 = off_180264680[0];
        v11 = 2575360;
        v12 = off_180261338[0];
LABEL_28:
        bidTraceW(v12, v11, v10, WSAPoll);
        goto LABEL_29;
      }
      goto LABEL_29;
    }
  }
  WSAPoll = SNI::detail::Transport::StaticInitialize();
  if ( WSAPoll )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264688[0] )
    {
      v10 = off_180264688[0];
      v11 = 2584576;
      v12 = off_180261340[0];
      goto LABEL_28;
    }
LABEL_29:
    if ( WSACleanup() == -1 )
    {
      Error = WSAGetLastError();
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1802646A0[0] )
          bidTraceW(off_180261358[0], 2622464, off_1802646A0[0], Error);
      }
    }
    goto LABEL_33;
  }
  v5 = 1;
  if ( g_osviSNI.dwMajorVersion >= 6 )
  {
    WSAPoll = LoadWSAPoll(&Tcp::s_pfnWSAPoll, &Tcp::s_hWS2_32);
    if ( WSAPoll )
    {
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264690[0] )
      {
        v10 = off_180264690[0];
        v11 = 2595840;
        v12 = off_180261348[0];
        goto LABEL_28;
      }
      goto LABEL_29;
    }
  }
  Tcp::s_fSupportsFlagNoHandleInherit = FOSSupportsFlagNoHandleInherit();
  *((_DWORD *)a1 + 3) = 1;
  *(_QWORD *)((char *)a1 + 4) = 0;
  *(_DWORD *)a1 = 6;
  *((_DWORD *)a1 + 4) = 1;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264698[0] )
    bidTraceW(off_180261350[0], 2612224, off_180264698[0], 0);
  WSAPoll = 0;
LABEL_54:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v17);
  return WSAPoll;
}

```

## disassembly

```asm
0x180164ab0  mov     [rsp+arg_8], rbx
0x180164ab5  mov     [rsp+arg_10], rbp
0x180164aba  mov     [rsp+arg_18], rsi
0x180164abf  push    rdi
0x180164ac0  sub     rsp, 1F0h
0x180164ac7  mov     rax, cs:__security_cookie
0x180164ace  xor     rax, rsp
0x180164ad1  mov     [rsp+1F8h+var_18], rax
0x180164ad9  mov     rdi, rcx
0x180164adc  mov     [rsp+1F8h+var_1C8], 0FFFFFFFFFFFFFFFFh
0x180164ae5  mov     eax, cs:_bidGblFlags
0x180164aeb  and     eax, 20004h
0x180164af0  cmp     eax, 20004h
0x180164af5  jnz     short loc_180164B17
0x180164af7  mov     rax, cs:off_1802669F0; "<Tcp::Initialize|API|SNI> pInfo: %p{PSN"...
0x180164afe  test    rax, rax
0x180164b01  jz      short loc_180164B17
0x180164b03  mov     r8, rcx
0x180164b06  mov     rdx, cs:off_1802669F0; "<Tcp::Initialize|API|SNI> pInfo: %p{PSN"...
0x180164b0d  lea     rcx, [rsp+1F8h+var_1C8]
0x180164b12  call    _bidScopeEnterW
0x180164b17  xor     edx, edx; Val
0x180164b19  mov     r8d, 198h; Size
0x180164b1f  lea     rcx, [rsp+1F8h+WSAData]; void *
0x180164b24  call    memset_0
0x180164b29  xor     sil, sil
0x180164b2c  mov     ecx, 202h; wVersionRequested
0x180164b31  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x180164b36  call    cs:__imp_WSAStartup
0x180164b3c  xor     ebp, ebp
0x180164b3e  test    eax, eax
0x180164b40  jz      loc_180164C0C
0x180164b46  mov     ecx, 101h; wVersionRequested
0x180164b4b  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x180164b50  call    cs:__imp_WSAStartup
0x180164b56  mov     ebx, eax
0x180164b58  test    eax, eax
0x180164b5a  jz      loc_180164C0C
0x180164b60  test    byte ptr cs:_bidGblFlags, 2
0x180164b67  jz      loc_180164BF5
0x180164b6d  mov     rax, cs:off_180264670; "<Tcp::Initialize|ERR|SNI> Winsock libra"...
0x180164b74  test    rax, rax
0x180164b77  jz      short loc_180164BB0
0x180164b79  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180164b81  jz      short loc_180164BB0
0x180164b83  mov     rax, cs:off_180248050
0x180164b8a  mov     [rsp+1F8h+var_1D8], rbp
0x180164b8f  mov     r9, cs:off_180264670; "<Tcp::Initialize|ERR|SNI> Winsock libra"...
0x180164b96  mov     r8d, 26F800h
0x180164b9c  mov     rdx, cs:off_180261328; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164ba3  mov     rcx, cs:_bidID
0x180164baa  call    cs:__guard_dispatch_icall_fptr
0x180164bb0  test    byte ptr cs:_bidGblFlags, 2
0x180164bb7  jz      short loc_180164BF5
0x180164bb9  mov     rax, cs:off_180264678; "<Tcp::Initialize|ERR|SNI> ProviderNum: "...
0x180164bc0  test    rax, rax
0x180164bc3  jz      short loc_180164BF5
0x180164bc5  mov     ecx, 0C3B4h; unsigned int
0x180164bca  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180164bcf  mov     [rsp+1F8h+var_1D0], ebx
0x180164bd3  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x180164bd7  mov     r9d, 6
0x180164bdd  mov     r8, cs:off_180264678; "<Tcp::Initialize|ERR|SNI> ProviderNum: "...
0x180164be4  mov     edx, 26FC00h
0x180164be9  mov     rcx, cs:off_180261330; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164bf0  call    _bidTraceW
0x180164bf5  mov     r8d, 0C3B4h
0x180164bfb  mov     edx, ebx
0x180164bfd  mov     ecx, 6
0x180164c02  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x180164c07  jmp     loc_180164D6A
0x180164c0c  cmp     cs:?s_fAutoTuning@Tcp@@2HA, ebp; int Tcp::s_fAutoTuning
0x180164c12  jz      short loc_180164C81
0x180164c14  lea     rcx, ?s_slhNotificationsToClose@Tcp@@1T_SLIST_HEADER@@A; ListHead
0x180164c1b  call    cs:__imp_InitializeSListHead
0x180164c21  mov     r9d, 1388h
0x180164c27  xor     r8d, r8d
0x180164c2a  lea     rdx, ?CleanupSendNotifications@Tcp@@CA?AW4SOS_TIMERRESULT@@PEAXPEAK1@Z; Tcp::CleanupSendNotifications(void *,ulong *,ulong *)
0x180164c31  lea     rcx, ?g_hCleanupSendNotificationTimer@@3PEAXEA; void * g_hCleanupSendNotificationTimer
0x180164c38  call    SNIEnqueueTimerTask
0x180164c3d  mov     ebx, eax
0x180164c3f  test    eax, eax
0x180164c41  jz      short loc_180164C81
0x180164c43  mov     eax, cs:_bidGblFlags
0x180164c49  and     eax, 20002h
0x180164c4e  cmp     eax, 20002h
0x180164c53  jnz     loc_180164D29
0x180164c59  mov     rax, cs:off_180264680; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x180164c60  test    rax, rax
0x180164c63  jz      loc_180164D29
0x180164c69  mov     r8, cs:off_180264680; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x180164c70  mov     edx, 274C00h
0x180164c75  mov     rcx, cs:off_180261338; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164c7c  jmp     loc_180164D21
0x180164c81  call    ?StaticInitialize@Transport@detail@SNI@@SAKXZ; SNI::detail::Transport::StaticInitialize(void)
0x180164c86  mov     ebx, eax
0x180164c88  test    eax, eax
0x180164c8a  jz      short loc_180164CC3
0x180164c8c  mov     eax, cs:_bidGblFlags
0x180164c92  and     eax, 20002h
0x180164c97  cmp     eax, 20002h
0x180164c9c  jnz     loc_180164D29
0x180164ca2  mov     rax, cs:off_180264688; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x180164ca9  test    rax, rax
0x180164cac  jz      short loc_180164D29
0x180164cae  mov     r8, cs:off_180264688; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x180164cb5  mov     edx, 277000h
0x180164cba  mov     rcx, cs:off_180261340; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164cc1  jmp     short loc_180164D21
0x180164cc3  mov     sil, 1
0x180164cc6  cmp     cs:?g_osviSNI@@3U_OSVERSIONINFOEXW@@A.dwMajorVersion, 6; _OSVERSIONINFOEXW g_osviSNI ...
0x180164ccd  jb      loc_180164E64
0x180164cd3  lea     rdx, ?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA; HINSTANCE *
0x180164cda  lea     rcx, ?s_pfnWSAPoll@Tcp@@1P6AHQEAUpollfd@@KH@ZEA; int (**)(struct pollfd *const, unsigned int, int)
0x180164ce1  call    ?LoadWSAPoll@@YAKPEAP6AHQEAUpollfd@@KH@ZPEAPEAUHINSTANCE__@@@Z; LoadWSAPoll(int (**)(pollfd * const,ulong,int),HINSTANCE__ * *)
0x180164ce6  mov     ebx, eax
0x180164ce8  test    eax, eax
0x180164cea  jz      loc_180164E64
0x180164cf0  mov     eax, cs:_bidGblFlags
0x180164cf6  and     eax, 20002h
0x180164cfb  cmp     eax, 20002h
0x180164d00  jnz     short loc_180164D29
0x180164d02  mov     rax, cs:off_180264690; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x180164d09  test    rax, rax
0x180164d0c  jz      short loc_180164D29
0x180164d0e  mov     r8, cs:off_180264690; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x180164d15  mov     edx, 279C00h
0x180164d1a  mov     rcx, cs:off_180261348; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164d21  mov     r9d, ebx
0x180164d24  call    _bidTraceW
0x180164d29  call    cs:__imp_WSACleanup
0x180164d2f  cmp     eax, 0FFFFFFFFh
0x180164d32  jnz     short loc_180164D6A
0x180164d34  call    cs:__imp_WSAGetLastError
0x180164d3a  test    byte ptr cs:_bidGblFlags, 2
0x180164d41  jz      short loc_180164D6A
0x180164d43  mov     rcx, cs:off_1802646A0; "<Tcp::Initialize|ERR|SNI> WSACleanup fa"...
0x180164d4a  test    rcx, rcx
0x180164d4d  jz      short loc_180164D6A
0x180164d4f  mov     r9d, eax
0x180164d52  mov     r8, cs:off_1802646A0; "<Tcp::Initialize|ERR|SNI> WSACleanup fa"...
0x180164d59  mov     edx, 280400h
0x180164d5e  mov     rcx, cs:off_180261358; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164d65  call    _bidTraceW
0x180164d6a  cmp     cs:?s_fAutoTuning@Tcp@@2HA, ebp; int Tcp::s_fAutoTuning
0x180164d70  jz      short loc_180164DC1
0x180164d72  mov     rcx, cs:?g_hCleanupSendNotificationTimer@@3PEAXEA; Timer
0x180164d79  test    rcx, rcx
0x180164d7c  jz      short loc_180164DC1
0x180164d7e  call    SNIStopTimerTask
0x180164d83  mov     cs:?g_hCleanupSendNotificationTimer@@3PEAXEA, rbp; void * g_hCleanupSendNotificationTimer
0x180164d8a  cmp     eax, 3E5h
0x180164d8f  jz      short loc_180164DC1
0x180164d91  test    byte ptr cs:_bidGblFlags, 2
0x180164d98  jz      short loc_180164DC1
0x180164d9a  mov     rcx, cs:off_1802646A8; "<Tcp::Initialize|ERR|SNI> SNIStopTimerT"...
0x180164da1  test    rcx, rcx
0x180164da4  jz      short loc_180164DC1
0x180164da6  mov     r9d, eax
0x180164da9  mov     r8, cs:off_1802646A8; "<Tcp::Initialize|ERR|SNI> SNIStopTimerT"...
0x180164db0  mov     edx, 283C00h
0x180164db5  mov     rcx, cs:off_180261360; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164dbc  call    _bidTraceW
0x180164dc1  test    sil, sil
0x180164dc4  jz      short loc_180164DCB
0x180164dc6  call    ?StaticTerminate@Transport@detail@SNI@@SAXXZ; SNI::detail::Transport::StaticTerminate(void)
0x180164dcb  mov     rcx, cs:?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA; hLibModule
0x180164dd2  test    rcx, rcx
0x180164dd5  jz      short loc_180164E1E
0x180164dd7  call    cs:__imp_FreeLibrary
0x180164ddd  test    eax, eax
0x180164ddf  jnz     short loc_180164E17
0x180164de1  call    cs:__imp_GetLastError
0x180164de7  test    byte ptr cs:_bidGblFlags, 2
0x180164dee  jz      short loc_180164E17
0x180164df0  mov     rcx, cs:off_1802646B0; "<Tcp::Initialize|ERR|SNI> FreeLibrary(W"...
0x180164df7  test    rcx, rcx
0x180164dfa  jz      short loc_180164E17
0x180164dfc  mov     r9d, eax
0x180164dff  mov     r8, cs:off_1802646B0; "<Tcp::Initialize|ERR|SNI> FreeLibrary(W"...
0x180164e06  mov     edx, 288000h
0x180164e0b  mov     rcx, cs:off_180261368; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164e12  call    _bidTraceW
0x180164e17  mov     cs:?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA, rbp; HINSTANCE__ * Tcp::s_hWS2_32
0x180164e1e  mov     cs:?s_pfnWSAPoll@Tcp@@1P6AHQEAUpollfd@@KH@ZEA, rbp; int (*Tcp::s_pfnWSAPoll)(pollfd * const,ulong,int)
0x180164e25  mov     eax, cs:_bidGblFlags
0x180164e2b  and     eax, 20002h
0x180164e30  cmp     eax, 20002h
0x180164e35  jnz     loc_180164EC2
0x180164e3b  mov     rax, cs:off_1802646B8; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x180164e42  test    rax, rax
0x180164e45  jz      short loc_180164EC2
0x180164e47  mov     r9d, ebx
0x180164e4a  mov     r8, cs:off_1802646B8; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x180164e51  mov     edx, 28A000h
0x180164e56  mov     rcx, cs:off_180261370; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164e5d  call    _bidTraceW
0x180164e62  jmp     short loc_180164EC2
0x180164e64  call    ?FOSSupportsFlagNoHandleInherit@@YA_NXZ; FOSSupportsFlagNoHandleInherit(void)
0x180164e69  mov     cs:?s_fSupportsFlagNoHandleInherit@Tcp@@1_NA, al; bool Tcp::s_fSupportsFlagNoHandleInherit
0x180164e6f  mov     dword ptr [rdi+0Ch], 1
0x180164e76  mov     [rdi+4], rbp
0x180164e7a  mov     dword ptr [rdi], 6
0x180164e80  mov     dword ptr [rdi+10h], 1
0x180164e87  mov     eax, cs:_bidGblFlags
0x180164e8d  and     eax, 20002h
0x180164e92  cmp     eax, 20002h
0x180164e97  jnz     short loc_180164EC0
0x180164e99  mov     rax, cs:off_180264698; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x180164ea0  test    rax, rax
0x180164ea3  jz      short loc_180164EC0
0x180164ea5  xor     r9d, r9d
0x180164ea8  mov     r8, cs:off_180264698; "<Tcp::Initialize|RET|SNI> %d{WINERR}\n"
0x180164eaf  mov     edx, 27DC00h
0x180164eb4  mov     rcx, cs:off_180261350; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164ebb  call    _bidTraceW
0x180164ec0  mov     ebx, ebp
0x180164ec2  lea     rcx, [rsp+1F8h+var_1C8]; this
0x180164ec7  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180164ecc  nop
0x180164ecd  mov     eax, ebx
0x180164ecf  mov     rcx, [rsp+1F8h+var_18]
0x180164ed7  xor     rcx, rsp; StackCookie
0x180164eda  call    __security_check_cookie
0x180164edf  lea     r11, [rsp+1F8h+var_8]
0x180164ee7  mov     rbx, [r11+18h]
0x180164eeb  mov     rbp, [r11+20h]
0x180164eef  mov     rsi, [r11+28h]
0x180164ef3  mov     rsp, r11
0x180164ef6  pop     rdi
0x180164ef7  retn
```

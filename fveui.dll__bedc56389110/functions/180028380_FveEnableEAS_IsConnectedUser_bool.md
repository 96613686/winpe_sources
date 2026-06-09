# FveEnableEAS::IsConnectedUser(bool *)

- ea: `0x180028380`
- end: `0x180028641`
- name: `?IsConnectedUser@FveEnableEAS@@IEAAJPEA_N@Z`
- size: `705`
- prototype: `__int64 __fastcall(FveEnableEAS *this, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027800`

## callees

- `0x1800037a0`
- `0x18000e354`
- `0x180028380`
- `0x180028648`
- `0x18002969c`
- `0x18002b768`
- `0x18002bde0`
- `0x18002bfb4`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180028499`
- `KERNEL32!GetCurrentThread` at `0x180028499`
- `KERNEL32!GetCurrentProcess` at `0x1800284c3`
- `KERNEL32!GetCurrentProcess` at `0x1800284c3`
- `KERNEL32!GetLastError` at `0x1800284dc`
- `KERNEL32!GetLastError` at `0x1800284dc`
- `ADVAPI32!OpenProcessToken` at `0x1800284d2`
- `ADVAPI32!OpenProcessToken` at `0x1800284d2`
- `ADVAPI32!OpenThreadToken` at `0x1800284b0`
- `ADVAPI32!OpenThreadToken` at `0x1800284b0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800285f3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800285f3`

## string_xrefs

- `0x180028467`: `InitializeCOM`
- `0x18002851b`: `OpenProcessToken`
- `0x180028565`: `GetFullToken`

## pseudocode

```c
__int64 __fastcall FveEnableEAS::IsConnectedUser(FveEnableEAS *this, bool *a2)
{
  PVOID *v3; // rcx
  signed int v4; // ebx
  unsigned int v5; // eax
  const char *v6; // rax
  __int64 v7; // rdx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int FullToken; // eax
  unsigned int v12; // eax
  PVOID *v13; // rcx
  const char *v15; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  FveEnableEAS *v17; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF
  HANDLE v19; // [rsp+70h] [rbp+40h] BYREF

  v17 = this;
  TokenHandle = 0;
  v19 = 0;
  LOBYTE(v17) = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x40) != 0 )
      WPP_SF_d(v3[2], 98, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, 2147500035LL);
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x49D,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)0x80004003LL,
      (int)"IsMSAUsernullptr",
      v15);
    goto LABEL_40;
  }
  v5 = FveBackupMonitor::InitializeCOM((bool *)&v17);
  v4 = v5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v5);
  if ( v4 < 0 )
  {
    v6 = "InitializeCOM";
    v7 = 1184;
LABEL_14:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v7,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)(unsigned int)v4,
      (int)v6,
      v15);
LABEL_37:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_38;
  }
  SH<void *,SH_HANDLE>::Reset((CNgscbToken *)&TokenHandle);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Au, 0, &TokenHandle) )
  {
    SH<void *,SH_HANDLE>::Reset((CNgscbToken *)&TokenHandle);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x2000Au, &TokenHandle) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          100,
          &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
          (unsigned int)v4);
      if ( v4 < 0 )
      {
        v6 = "OpenProcessToken";
        v7 = 1195;
        goto LABEL_14;
      }
    }
  }
  FullToken = CNgscbToken::GetFullToken(&TokenHandle, (struct CNgscbToken *)&v19);
  v4 = FullToken;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, FullToken);
  if ( v4 < 0 )
  {
    v6 = "GetFullToken";
    v7 = 1199;
    goto LABEL_14;
  }
  v12 = FveBackupMonitor::CheckIsConnectedUser(&v19, a2);
  v4 = v12;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v12);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 < 0 )
  {
    v6 = "CheckIsConnectedUser";
    v7 = 1200;
    goto LABEL_14;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
  {
    WPP_SF_d(v13[2], 103, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, *a2);
    goto LABEL_37;
  }
LABEL_38:
  if ( (_BYTE)v17 )
  {
    CoUninitialize();
LABEL_40:
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x20) != 0 )
    WPP_SF_d(v13[2], 104, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, (unsigned int)v4);
  SH<void *,SH_HANDLE>::Reset((CNgscbToken *)&v19);
  SH<void *,SH_HANDLE>::Reset((CNgscbToken *)&TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180028380  mov     [rsp-28h+arg_0], rcx
0x180028385  push    rbp
0x180028386  push    rbx
0x180028387  push    rsi
0x180028388  push    r12
0x18002838a  push    r15
0x18002838c  mov     rbp, rsp
0x18002838f  sub     rsp, 30h
0x180028393  mov     rsi, rdx
0x180028396  mov     [rbp+TokenHandle], 0
0x18002839e  mov     [rbp+arg_10], 0
0x1800283a6  mov     byte ptr [rbp+arg_0], 0
0x1800283aa  lea     r15, WPP_GLOBAL_Control
0x1800283b1  lea     r12, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x1800283b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283bf  cmp     rcx, r15
0x1800283c2  jz      short loc_1800283E2
0x1800283c4  test    byte ptr [rcx+1Ch], 20h
0x1800283c8  jz      short loc_1800283E2
0x1800283ca  mov     edx, 61h ; 'a'
0x1800283cf  mov     r8, r12
0x1800283d2  mov     rcx, [rcx+10h]
0x1800283d6  call    WPP_SF_
0x1800283db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283e2  test    rsi, rsi
0x1800283e5  jnz     short loc_180028432
0x1800283e7  mov     ebx, 80004003h
0x1800283ec  cmp     rcx, r15
0x1800283ef  jz      short loc_180028409
0x1800283f1  test    byte ptr [rcx+1Ch], 40h
0x1800283f5  jz      short loc_180028409
0x1800283f7  lea     edx, [rsi+62h]
0x1800283fa  mov     r9d, ebx
0x1800283fd  mov     r8, r12
0x180028400  mov     rcx, [rcx+10h]
0x180028404  call    WPP_SF_d
0x180028409  mov     rcx, [rbp+28h]; this
0x18002840d  lea     rax, aIsmsausernullp; "IsMSAUsernullptr"
0x180028414  mov     qword ptr [rsp+30h+var_10], rax; int
0x180028419  mov     r9d, ebx; char *
0x18002841c  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180028423  mov     edx, 49Dh; void *
0x180028428  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002842d  jmp     loc_1800285F9
0x180028432  lea     rcx, [rbp+arg_0]; bool *
0x180028436  call    ?InitializeCOM@FveBackupMonitor@@SAJPEA_N@Z; FveBackupMonitor::InitializeCOM(bool *)
0x18002843b  mov     ebx, eax
0x18002843d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028444  cmp     rcx, r15
0x180028447  jz      short loc_180028463
0x180028449  test    byte ptr [rcx+1Ch], 40h
0x18002844d  jz      short loc_180028463
0x18002844f  mov     edx, 63h ; 'c'
0x180028454  mov     r9d, eax
0x180028457  mov     r8, r12
0x18002845a  mov     rcx, [rcx+10h]
0x18002845e  call    WPP_SF_d
0x180028463  test    ebx, ebx
0x180028465  jns     short loc_180028490
0x180028467  lea     rax, aInitializecom; "InitializeCOM"
0x18002846e  mov     edx, 4A0h; void *
0x180028473  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x18002847a  mov     r9d, ebx; char *
0x18002847d  mov     qword ptr [rsp+30h+var_10], rax; int
0x180028482  mov     rcx, [rbp+28h]; this
0x180028486  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002848b  jmp     loc_1800285E6
0x180028490  lea     rcx, [rbp+TokenHandle]
0x180028494  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180028499  call    cs:__imp_GetCurrentThread
0x18002849f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800284a3  xor     r8d, r8d; OpenAsSelf
0x1800284a6  mov     ebx, 2000Ah
0x1800284ab  mov     edx, ebx; DesiredAccess
0x1800284ad  mov     rcx, rax; ThreadHandle
0x1800284b0  call    cs:__imp_OpenThreadToken
0x1800284b6  test    eax, eax
0x1800284b8  jnz     short loc_18002852C
0x1800284ba  lea     rcx, [rbp+TokenHandle]
0x1800284be  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x1800284c3  call    cs:__imp_GetCurrentProcess
0x1800284c9  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800284cd  mov     edx, ebx; DesiredAccess
0x1800284cf  mov     rcx, rax; ProcessHandle
0x1800284d2  call    cs:__imp_OpenProcessToken
0x1800284d8  test    eax, eax
0x1800284da  jnz     short loc_18002852C
0x1800284dc  call    cs:__imp_GetLastError
0x1800284e2  mov     ebx, eax
0x1800284e4  test    eax, eax
0x1800284e6  jle     short loc_1800284F1
0x1800284e8  movzx   ebx, ax
0x1800284eb  or      ebx, 80070000h
0x1800284f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284f8  cmp     rcx, r15
0x1800284fb  jz      short loc_180028517
0x1800284fd  test    byte ptr [rcx+1Ch], 40h
0x180028501  jz      short loc_180028517
0x180028503  mov     edx, 64h ; 'd'
0x180028508  mov     r9d, ebx
0x18002850b  mov     r8, r12
0x18002850e  mov     rcx, [rcx+10h]
0x180028512  call    WPP_SF_d
0x180028517  test    ebx, ebx
0x180028519  jns     short loc_18002852C
0x18002851b  lea     rax, aOpenprocesstok; "OpenProcessToken"
0x180028522  mov     edx, 4ABh
0x180028527  jmp     loc_180028473
0x18002852c  lea     rdx, [rbp+arg_10]; struct CNgscbToken *
0x180028530  lea     rcx, [rbp+TokenHandle]; this
0x180028534  call    ?GetFullToken@CNgscbToken@@QEBAJAEAV1@@Z; CNgscbToken::GetFullToken(CNgscbToken &)
0x180028539  mov     ebx, eax
0x18002853b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028542  cmp     rcx, r15
0x180028545  jz      short loc_180028561
0x180028547  test    byte ptr [rcx+1Ch], 40h
0x18002854b  jz      short loc_180028561
0x18002854d  mov     edx, 65h ; 'e'
0x180028552  mov     r9d, eax
0x180028555  mov     r8, r12
0x180028558  mov     rcx, [rcx+10h]
0x18002855c  call    WPP_SF_d
0x180028561  test    ebx, ebx
0x180028563  jns     short loc_180028576
0x180028565  lea     rax, aGetfulltoken; "GetFullToken"
0x18002856c  mov     edx, 4AFh
0x180028571  jmp     loc_180028473
0x180028576  mov     rdx, rsi; bool *
0x180028579  lea     rcx, [rbp+arg_10]; struct CNgscbToken *
0x18002857d  call    ?CheckIsConnectedUser@FveBackupMonitor@@SAJPEBVCNgscbToken@@PEA_N@Z; FveBackupMonitor::CheckIsConnectedUser(CNgscbToken const *,bool *)
0x180028582  mov     ebx, eax
0x180028584  mov     rcx, cs:WPP_GLOBAL_Control
0x18002858b  cmp     rcx, r15
0x18002858e  jz      short loc_1800285B1
0x180028590  test    byte ptr [rcx+1Ch], 40h
0x180028594  jz      short loc_1800285B1
0x180028596  mov     edx, 66h ; 'f'
0x18002859b  mov     r9d, eax
0x18002859e  mov     r8, r12
0x1800285a1  mov     rcx, [rcx+10h]
0x1800285a5  call    WPP_SF_d
0x1800285aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285b1  test    ebx, ebx
0x1800285b3  jns     short loc_1800285C6
0x1800285b5  lea     rax, aCheckisconnect; "CheckIsConnectedUser"
0x1800285bc  mov     edx, 4B0h
0x1800285c1  jmp     loc_180028473
0x1800285c6  cmp     rcx, r15
0x1800285c9  jz      short loc_1800285ED
0x1800285cb  test    byte ptr [rcx+1Ch], 8
0x1800285cf  jz      short loc_1800285ED
0x1800285d1  movzx   r9d, byte ptr [rsi]
0x1800285d5  mov     edx, 67h ; 'g'
0x1800285da  mov     r8, r12
0x1800285dd  mov     rcx, [rcx+10h]
0x1800285e1  call    WPP_SF_d
0x1800285e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285ed  cmp     byte ptr [rbp+arg_0], 0
0x1800285f1  jz      short loc_180028600
0x1800285f3  call    cs:__imp_CoUninitialize
0x1800285f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180028600  cmp     rcx, r15
0x180028603  jz      short loc_180028620
0x180028605  test    byte ptr [rcx+1Ch], 20h
0x180028609  jz      short loc_180028620
0x18002860b  mov     edx, 68h ; 'h'
0x180028610  mov     r9d, ebx
0x180028613  mov     r8, r12
0x180028616  mov     rcx, [rcx+10h]
0x18002861a  call    WPP_SF_d
0x18002861f  nop
0x180028620  lea     rcx, [rbp+arg_10]
0x180028624  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180028629  nop
0x18002862a  lea     rcx, [rbp+TokenHandle]
0x18002862e  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180028633  mov     eax, ebx
0x180028635  add     rsp, 30h
0x180028639  pop     r15
0x18002863b  pop     r12
0x18002863d  pop     rsi
0x18002863e  pop     rbx
0x18002863f  pop     rbp
0x180028640  retn
```

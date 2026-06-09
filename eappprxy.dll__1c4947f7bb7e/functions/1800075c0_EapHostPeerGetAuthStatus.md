# EapHostPeerGetAuthStatus

- ea: `0x1800075c0`
- end: `0x180007a7a`
- name: `EapHostPeerGetAuthStatus`
- size: `1210`
- prototype: `DWORD __stdcall(EAP_SESSIONID sessionHandle, EapHostPeerAuthParams authParam, DWORD *pcbAuthData, BYTE **ppAuthData, EAP_ERROR **ppEapError)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x1800030f8`
- `0x180005450`
- `0x1800075c0`
- `0x18000ace0`
- `0x18000aeb8`
- `0x18000af14`
- `0x18000b824`
- `0x18000bef4`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000769f`
- `ntdll!EtwEventEnabled` at `0x180007900`
- `ntdll!EtwEventEnabled` at `0x18000769f`
- `ntdll!EtwEventEnabled` at `0x180007900`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800078e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800078e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000761d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000761d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000762f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000762f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
DWORD __stdcall EapHostPeerGetAuthStatus(
        EAP_SESSIONID sessionHandle,
        EapHostPeerAuthParams authParam,
        DWORD *pcbAuthData,
        BYTE **ppAuthData,
        EAP_ERROR **ppEapError)
{
  EAP_SESSIONID v6; // r14d
  unsigned __int64 v7; // rbx
  DWORD TickCount; // eax
  __int64 v9; // r8
  unsigned __int64 v10; // r13
  __int64 v11; // r8
  __int64 v12; // rsi
  __int64 v13; // rax
  void *v14; // rcx
  signed int SessionFreeBuffers; // ebx
  DWORD *v16; // rax
  BYTE **v17; // rcx
  void *v18; // rax
  __int64 v19; // rdx
  BYTE *v20; // rcx
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  __int64 v22; // r8
  LPWSTR lpBuffer; // [rsp+20h] [rbp-10D8h]
  DWORD nSize[2]; // [rsp+28h] [rbp-10D0h]
  DWORD v26; // [rsp+40h] [rbp-10B8h] BYREF
  void *v27; // [rsp+48h] [rbp-10B0h] BYREF
  EapHost::Peer::ConnectionSessionInfo *v28; // [rsp+50h] [rbp-10A8h] BYREF
  EAP_SESSIONID v29; // [rsp+58h] [rbp-10A0h]
  BYTE *v30; // [rsp+60h] [rbp-1098h] BYREF
  LPVOID v31; // [rsp+68h] [rbp-1090h] BYREF
  unsigned __int64 v32; // [rsp+70h] [rbp-1088h] BYREF
  BYTE **v33; // [rsp+78h] [rbp-1080h]
  DWORD *v34; // [rsp+80h] [rbp-1078h]
  _BYTE v35[16]; // [rsp+88h] [rbp-1070h] BYREF
  char *v36; // [rsp+98h] [rbp-1060h]
  __int64 v37; // [rsp+A0h] [rbp-1058h]
  char v38[2048]; // [rsp+B0h] [rbp-1048h] BYREF
  WCHAR Buffer[1024]; // [rsp+8B0h] [rbp-848h] BYREF

  v33 = ppAuthData;
  v34 = pcbAuthData;
  LODWORD(v27) = authParam;
  v6 = sessionHandle;
  v29 = sessionHandle;
  v30 = 0;
  v26 = 0;
  v31 = 0;
  v7 = (unsigned __int64)GetCurrentThreadId() << 32;
  TickCount = GetTickCount();
  v10 = v7 | TickCount;
  v32 = v10;
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v28 = (EapHost::Peer::ConnectionSessionInfo *)(v7 | TickCount);
    v36 = (char *)&v28;
    v37 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)GetAuthStatusStart, v9, 2, (__int64)v35);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v38, 0x800u, "EapHostPeerGetAuthStatus Entry:\n Session(%d), authParam(%d)", v6, authParam) >= 0 )
  {
    v12 = -1;
    if ( Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v38[v13] );
      v36 = v38;
      v37 = (unsigned int)(v13 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v11, 2, (__int64)v35);
    }
  }
  else
  {
    v12 = -1;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, v11, v6, (_DWORD)v27);
  v28 = 0;
  if ( !v6 )
    goto LABEL_29;
  SessionFreeBuffers = EapHost::Peer::PeerProxy::FindSessionFreeBuffers((__int64)v14, v6, &v28, &v31, 0);
  if ( SessionFreeBuffers )
    goto LABEL_30;
  v16 = v34;
  if ( !v34 || (v17 = v33) == 0 )
  {
LABEL_29:
    SessionFreeBuffers = 160;
    goto LABEL_30;
  }
  if ( ppEapError )
    *ppEapError = 0;
  *v16 = 0;
  *v17 = 0;
  SessionFreeBuffers = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, DWORD *, BYTE **, EAP_ERROR **))(*(_QWORD *)v31 + 88LL))(
                         v31,
                         v6,
                         (unsigned int)v27,
                         &v26,
                         &v30,
                         ppEapError);
  if ( SessionFreeBuffers >= 0 )
  {
    try
    {
      v18 = operator new(0x20u);
      if ( v18 )
      {
        v19 = v26;
        v20 = v30;
        *((_DWORD *)v18 + 2) = 0;
        *(_QWORD *)v18 = &EapHost::RawBuffer::`vftable';
        *((_QWORD *)v18 + 2) = v20;
        *((_QWORD *)v18 + 3) = v19;
        v27 = v18;
        _InterlockedIncrement((volatile signed __int32 *)v18 + 2);
      }
      else
      {
        v27 = 0;
      }
      EapHost::Peer::ConnectionSessionInfo::AddBuffer(v28, &v27);
      v21 = (void (__fastcall ***)(_QWORD, __int64))v27;
      if ( v27 && _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 2, 0xFFFFFFFF) == 1 && v21 )
        (**v21)(v21, 1);
      *v33 = v30;
      *v34 = v26;
    }
    catch ( std::bad_alloc )
    {
      LODWORD(v27) = 14;
      v12 = -1;
      SessionFreeBuffers = 14;
      v6 = v29;
      v10 = v32;
    }
  }
LABEL_30:
  FormatMessageW(0x1200u, 0, SessionFreeBuffers, 0, Buffer, 0x400u, 0);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    nSize[0] = v26;
    LODWORD(lpBuffer) = v6;
    if ( (int)StringCchPrintfA(
                v38,
                0x800u,
                "EapHostPeerGetAuthStatus Exit:\n %ws\nReturned session(%d), auth status data(%d) bytes.",
                Buffer,
                lpBuffer,
                *(_QWORD *)nSize) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v12;
      while ( v38[v12] );
      v36 = v38;
      v37 = (unsigned int)(v12 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v22, 2, (__int64)v35);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, v22, (unsigned int)SessionFreeBuffers, v6, v26);
  if ( v28 )
    _InterlockedCompareExchange((volatile signed __int32 *)v28 + 43, 0, *((_DWORD *)v28 + 43));
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v32 = v10;
    v36 = (char *)&v32;
    v37 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)GetAuthStatusEnd, v22, 2, (__int64)v35);
  }
  if ( v31 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
  return SessionFreeBuffers;
}

```

## disassembly

```asm
0x1800075c0  push    rbx
0x1800075c2  push    rsi
0x1800075c3  push    rdi
0x1800075c4  push    r12
0x1800075c6  push    r13
0x1800075c8  push    r14
0x1800075ca  push    r15
0x1800075cc  mov     eax, 10C0h
0x1800075d1  call    _alloca_probe
0x1800075d6  sub     rsp, rax
0x1800075d9  mov     rax, cs:__security_cookie
0x1800075e0  xor     rax, rsp
0x1800075e3  mov     [rsp+10F8h+var_48], rax
0x1800075eb  mov     [rsp+10F8h+var_1080], r9
0x1800075f0  mov     [rsp+10F8h+var_1078], r8
0x1800075f8  mov     esi, edx
0x1800075fa  mov     dword ptr [rsp+10F8h+var_10B0], edx
0x1800075fe  mov     r14d, ecx
0x180007601  mov     [rsp+10F8h+var_10A0], ecx
0x180007605  mov     r15, [rsp+10F8h+ppEapError]
0x18000760d  xor     edi, edi
0x18000760f  mov     [rsp+10F8h+var_1098], rdi
0x180007614  mov     [rsp+10F8h+var_10B8], edi
0x180007618  mov     [rsp+10F8h+var_1090], rdi
0x18000761d  call    cs:__imp_GetCurrentThreadId
0x180007624  nop     dword ptr [rax+rax+00h]
0x180007629  mov     ebx, eax
0x18000762b  shl     rbx, 20h
0x18000762f  call    cs:__imp_GetTickCount
0x180007636  nop     dword ptr [rax+rax+00h]
0x18000763b  mov     r13d, eax
0x18000763e  or      r13, rbx
0x180007641  mov     [rsp+10F8h+var_1088], r13
0x180007646  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x18000764d  jge     short loc_180007691
0x18000764f  mov     [rsp+10F8h+var_10A8], r13
0x180007654  lea     rax, [rsp+10F8h+var_10A8]
0x180007659  mov     [rsp+10F8h+var_1060], rax
0x180007661  mov     [rsp+10F8h+var_1058], 8
0x18000766d  lea     rax, [rsp+10F8h+var_1070]
0x180007675  mov     [rsp+10F8h+lpBuffer], rax
0x18000767a  lea     r9d, [rdi+2]
0x18000767e  lea     rdx, GetAuthStatusStart
0x180007685  lea     rcx, eaphost_Context
0x18000768c  call    McGenEventWrite_EtwEventWriteTransfer
0x180007691  lea     rdx, DebugInfoEvent
0x180007698  mov     rcx, cs:eaphost_Context
0x18000769f  call    cs:__imp_EtwEventEnabled
0x1800076a6  nop     dword ptr [rax+rax+00h]
0x1800076ab  test    al, al
0x1800076ad  jz      loc_180007740
0x1800076b3  mov     dword ptr [rsp+10F8h+lpBuffer], esi
0x1800076b7  mov     r9d, r14d
0x1800076ba  lea     r8, aEaphostpeerget_8; "EapHostPeerGetAuthStatus Entry:\n Sessi"...
0x1800076c1  mov     edx, 800h; unsigned __int64
0x1800076c6  lea     rcx, [rsp+10F8h+var_1048]; char *
0x1800076ce  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800076d3  test    eax, eax
0x1800076d5  js      short loc_180007740
0x1800076d7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800076db  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x1800076e2  jge     short loc_180007744
0x1800076e4  lea     rcx, [rsp+10F8h+var_1048]
0x1800076ec  mov     rax, rsi
0x1800076ef  inc     rax
0x1800076f2  cmp     [rcx+rax], dil
0x1800076f6  jnz     short loc_1800076EF
0x1800076f8  inc     eax
0x1800076fa  lea     rcx, [rsp+10F8h+var_1048]
0x180007702  mov     [rsp+10F8h+var_1060], rcx
0x18000770a  mov     dword ptr [rsp+10F8h+var_1058], eax
0x180007711  mov     dword ptr [rsp+10F8h+var_1058+4], edi
0x180007718  lea     rax, [rsp+10F8h+var_1070]
0x180007720  mov     [rsp+10F8h+lpBuffer], rax
0x180007725  mov     r9d, 2
0x18000772b  lea     rdx, DebugInfoEvent
0x180007732  lea     rcx, eaphost_Context
0x180007739  call    McGenEventWrite_EtwEventWriteTransfer
0x18000773e  jmp     short loc_180007744
0x180007740  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007744  lea     r12, WPP_GLOBAL_Control
0x18000774b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007752  cmp     rcx, r12
0x180007755  jz      short loc_180007776
0x180007757  test    byte ptr [rcx+1Ch], 4
0x18000775b  jz      short loc_180007776
0x18000775d  mov     edx, 2Ch ; ','
0x180007762  mov     eax, dword ptr [rsp+10F8h+var_10B0]
0x180007766  mov     dword ptr [rsp+10F8h+lpBuffer], eax
0x18000776a  mov     r9d, r14d
0x18000776d  mov     rcx, [rcx+10h]
0x180007771  call    WPP_SF_Dd
0x180007776  mov     [rsp+10F8h+var_10A8], rdi
0x18000777b  test    r14d, r14d
0x18000777e  jz      loc_1800078BA
0x180007784  mov     dword ptr [rsp+10F8h+lpBuffer], edi
0x180007788  lea     r9, [rsp+10F8h+var_1090]
0x18000778d  lea     r8, [rsp+10F8h+var_10A8]
0x180007792  mov     edx, r14d
0x180007795  call    ?FindSessionFreeBuffers@PeerProxy@Peer@EapHost@@QEAAKKAEAPEAVConnectionSessionInfo@23@AEAV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@H@Z; EapHost::Peer::PeerProxy::FindSessionFreeBuffers(ulong,EapHost::Peer::ConnectionSessionInfo * &,ATL::CComPtr<IEapHostPeerSessionApis> &,int)
0x18000779a  mov     ebx, eax
0x18000779c  test    eax, eax
0x18000779e  jnz     loc_1800078BF
0x1800077a4  mov     rax, [rsp+10F8h+var_1078]
0x1800077ac  test    rax, rax
0x1800077af  jz      loc_1800078BA
0x1800077b5  mov     rcx, [rsp+10F8h+var_1080]
0x1800077ba  test    rcx, rcx
0x1800077bd  jz      loc_1800078BA
0x1800077c3  test    r15, r15
0x1800077c6  jz      short loc_1800077CB
0x1800077c8  mov     [r15], rdi
0x1800077cb  mov     [rax], edi
0x1800077cd  mov     [rcx], rdi
0x1800077d0  mov     rcx, [rsp+10F8h+var_1090]
0x1800077d5  mov     rax, [rcx]
0x1800077d8  mov     qword ptr [rsp+10F8h+nSize], r15
0x1800077dd  lea     rdx, [rsp+10F8h+var_1098]
0x1800077e2  mov     [rsp+10F8h+lpBuffer], rdx
0x1800077e7  lea     r9, [rsp+10F8h+var_10B8]
0x1800077ec  mov     r8d, dword ptr [rsp+10F8h+var_10B0]
0x1800077f1  mov     edx, r14d
0x1800077f4  mov     rax, [rax+58h]
0x1800077f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077fd  mov     ebx, eax
0x1800077ff  test    eax, eax
0x180007801  js      loc_1800078BF
0x180007807  mov     ecx, 20h ; ' '; dwBytes
0x18000780c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007811  test    rax, rax
0x180007814  jz      short loc_18000783F
0x180007816  mov     edx, [rsp+10F8h+var_10B8]
0x18000781a  mov     rcx, [rsp+10F8h+var_1098]
0x18000781f  mov     [rax+8], edi
0x180007822  lea     r8, ??_7RawBuffer@EapHost@@6B@; const EapHost::RawBuffer::`vftable'
0x180007829  mov     [rax], r8
0x18000782c  mov     [rax+10h], rcx
0x180007830  mov     [rax+18h], rdx
0x180007834  mov     [rsp+10F8h+var_10B0], rax
0x180007839  lock inc dword ptr [rax+8]
0x18000783d  jmp     short loc_180007844
0x18000783f  mov     [rsp+10F8h+var_10B0], rdi
0x180007844  lea     rdx, [rsp+10F8h+var_10B0]
0x180007849  mov     rcx, [rsp+10F8h+var_10A8]
0x18000784e  call    ?AddBuffer@ConnectionSessionInfo@Peer@EapHost@@QEAAXAEBV?$SmartPointer@VReferenceCounted@@@@@Z; EapHost::Peer::ConnectionSessionInfo::AddBuffer(SmartPointer<ReferenceCounted> const &)
0x180007853  nop
0x180007854  mov     rcx, [rsp+10F8h+var_10B0]
0x180007859  test    rcx, rcx
0x18000785c  jz      short loc_18000787F
0x18000785e  mov     eax, esi
0x180007860  lock xadd [rcx+8], eax
0x180007865  add     eax, esi
0x180007867  jnz     short loc_18000787F
0x180007869  test    rcx, rcx
0x18000786c  jz      short loc_18000787F
0x18000786e  mov     rax, [rcx]
0x180007871  mov     edx, 1
0x180007876  mov     rax, [rax]
0x180007879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000787e  nop
0x18000787f  mov     rax, [rsp+10F8h+var_1098]
0x180007884  mov     rcx, [rsp+10F8h+var_1080]
0x180007889  mov     [rcx], rax
0x18000788c  mov     eax, [rsp+10F8h+var_10B8]
0x180007890  mov     r8, [rsp+10F8h+var_1078]
0x180007898  mov     [r8], eax
0x18000789b  jmp     short loc_1800078BF
0x18000789d  xor     edi, edi
0x18000789f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800078a3  lea     r12, WPP_GLOBAL_Control
0x1800078aa  mov     ebx, dword ptr [rsp+10F8h+var_10B0]
0x1800078ae  mov     r14d, [rsp+10F8h+var_10A0]
0x1800078b3  mov     r13, [rsp+10F8h+var_1088]
0x1800078b8  jmp     short loc_1800078BF
0x1800078ba  mov     ebx, 0A0h
0x1800078bf  mov     [rsp+10F8h+Arguments], rdi; Arguments
0x1800078c4  mov     [rsp+10F8h+nSize], 400h; nSize
0x1800078cc  lea     rax, [rsp+10F8h+Buffer]
0x1800078d4  mov     [rsp+10F8h+lpBuffer], rax; lpBuffer
0x1800078d9  xor     r9d, r9d; dwLanguageId
0x1800078dc  mov     r8d, ebx; dwMessageId
0x1800078df  xor     edx, edx; lpSource
0x1800078e1  mov     ecx, 1200h; dwFlags
0x1800078e6  call    cs:__imp_FormatMessageW
0x1800078ed  nop     dword ptr [rax+rax+00h]
0x1800078f2  lea     rdx, DebugInfoEvent
0x1800078f9  mov     rcx, cs:eaphost_Context
0x180007900  call    cs:__imp_EtwEventEnabled
0x180007907  nop     dword ptr [rax+rax+00h]
0x18000790c  test    al, al
0x18000790e  jz      loc_1800079A7
0x180007914  mov     eax, [rsp+10F8h+var_10B8]
0x180007918  mov     [rsp+10F8h+nSize], eax
0x18000791c  mov     dword ptr [rsp+10F8h+lpBuffer], r14d
0x180007921  lea     r9, [rsp+10F8h+Buffer]
0x180007929  lea     r8, aEaphostpeerget_9; "EapHostPeerGetAuthStatus Exit:\n %ws\nR"...
0x180007930  mov     edx, 800h; unsigned __int64
0x180007935  lea     rcx, [rsp+10F8h+var_1048]; char *
0x18000793d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007942  test    eax, eax
0x180007944  js      short loc_1800079A7
0x180007946  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x18000794d  jge     short loc_1800079A7
0x18000794f  lea     rax, [rsp+10F8h+var_1048]
0x180007957  inc     rsi
0x18000795a  cmp     [rax+rsi], dil
0x18000795e  jnz     short loc_180007957
0x180007960  lea     eax, [rsi+1]
0x180007963  lea     rcx, [rsp+10F8h+var_1048]
0x18000796b  mov     [rsp+10F8h+var_1060], rcx
0x180007973  mov     dword ptr [rsp+10F8h+var_1058], eax
0x18000797a  mov     dword ptr [rsp+10F8h+var_1058+4], edi
0x180007981  lea     rax, [rsp+10F8h+var_1070]
0x180007989  mov     [rsp+10F8h+lpBuffer], rax
0x18000798e  mov     r9d, 2
0x180007994  lea     rdx, DebugInfoEvent
0x18000799b  lea     rcx, eaphost_Context
0x1800079a2  call    McGenEventWrite_EtwEventWriteTransfer
0x1800079a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079ae  cmp     rcx, r12
0x1800079b1  jz      short loc_1800079D7
0x1800079b3  test    byte ptr [rcx+1Ch], 4
0x1800079b7  jz      short loc_1800079D7
0x1800079b9  mov     edx, 2Dh ; '-'
0x1800079be  mov     eax, [rsp+10F8h+var_10B8]
0x1800079c2  mov     [rsp+10F8h+nSize], eax
0x1800079c6  mov     dword ptr [rsp+10F8h+lpBuffer], r14d
0x1800079cb  mov     r9d, ebx
0x1800079ce  mov     rcx, [rcx+10h]
0x1800079d2  call    WPP_SF_Ddd
0x1800079d7  mov     rcx, [rsp+10F8h+var_10A8]
0x1800079dc  test    rcx, rcx
0x1800079df  jz      short loc_1800079EF
0x1800079e1  mov     eax, [rcx+0ACh]
0x1800079e7  lock cmpxchg [rcx+0ACh], edi
0x1800079ef  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x1800079f6  jge     short loc_180007A3D
0x1800079f8  mov     [rsp+10F8h+var_1088], r13
0x1800079fd  lea     rax, [rsp+10F8h+var_1088]
0x180007a02  mov     [rsp+10F8h+var_1060], rax
0x180007a0a  mov     [rsp+10F8h+var_1058], 8
0x180007a16  lea     rax, [rsp+10F8h+var_1070]
0x180007a1e  mov     [rsp+10F8h+lpBuffer], rax
0x180007a23  mov     r9d, 2
0x180007a29  lea     rdx, GetAuthStatusEnd
0x180007a30  lea     rcx, eaphost_Context
0x180007a37  call    McGenEventWrite_EtwEventWriteTransfer
0x180007a3c  nop
0x180007a3d  mov     rcx, [rsp+10F8h+var_1090]
0x180007a42  test    rcx, rcx
0x180007a45  jz      short loc_180007A54
0x180007a47  mov     rax, [rcx]
0x180007a4a  mov     rax, [rax+10h]
0x180007a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a53  nop
0x180007a54  mov     eax, ebx
0x180007a56  mov     rcx, [rsp+10F8h+var_48]
0x180007a5e  xor     rcx, rsp; StackCookie
0x180007a61  call    __security_check_cookie
0x180007a66  add     rsp, 10C0h
0x180007a6d  pop     r15
0x180007a6f  pop     r14
0x180007a71  pop     r13
0x180007a73  pop     r12
0x180007a75  pop     rdi
0x180007a76  pop     rsi
0x180007a77  pop     rbx
0x180007a78  retn
```

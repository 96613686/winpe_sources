# EapHostPeerGetSendPacket

- ea: `0x180009230`
- end: `0x1800096cf`
- name: `EapHostPeerGetSendPacket`
- size: `1183`
- prototype: `DWORD __stdcall(EAP_SESSIONID sessionHandle, DWORD *pcbSendPacket, BYTE **ppSendPacket, EAP_ERROR **ppEapError)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x1800030f8`
- `0x180005450`
- `0x180009230`
- `0x18000ace0`
- `0x18000ade4`
- `0x18000af14`
- `0x18000b824`
- `0x18000bef4`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180009304`
- `ntdll!EtwEventEnabled` at `0x180009555`
- `ntdll!EtwEventEnabled` at `0x180009304`
- `ntdll!EtwEventEnabled` at `0x180009555`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000953b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000953b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009282`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009294`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009294`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
DWORD __stdcall EapHostPeerGetSendPacket(
        EAP_SESSIONID sessionHandle,
        DWORD *pcbSendPacket,
        BYTE **ppSendPacket,
        EAP_ERROR **ppEapError)
{
  EAP_SESSIONID v5; // r14d
  unsigned __int64 v6; // rbx
  DWORD TickCount; // eax
  __int64 v8; // r8
  unsigned __int64 v9; // r12
  __int64 v10; // r8
  __int64 v11; // rsi
  __int64 v12; // rax
  void *v13; // rcx
  signed int SessionFreeBuffers; // ebx
  DWORD *v15; // rax
  BYTE **v16; // rcx
  void *v17; // rax
  __int64 v18; // rdx
  BYTE *v19; // rcx
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  __int64 v21; // r8
  LPWSTR lpBuffer; // [rsp+20h] [rbp-10D8h]
  __int64 nSize; // [rsp+28h] [rbp-10D0h]
  DWORD v25; // [rsp+40h] [rbp-10B8h] BYREF
  void *v26; // [rsp+48h] [rbp-10B0h] BYREF
  EapHost::Peer::ConnectionSessionInfo *v27; // [rsp+50h] [rbp-10A8h] BYREF
  EAP_SESSIONID v28; // [rsp+58h] [rbp-10A0h]
  BYTE *v29; // [rsp+60h] [rbp-1098h] BYREF
  LPVOID v30; // [rsp+68h] [rbp-1090h] BYREF
  unsigned __int64 v31; // [rsp+70h] [rbp-1088h] BYREF
  BYTE **v32; // [rsp+78h] [rbp-1080h]
  DWORD *v33; // [rsp+80h] [rbp-1078h]
  _BYTE v34[16]; // [rsp+88h] [rbp-1070h] BYREF
  char *v35; // [rsp+98h] [rbp-1060h]
  __int64 v36; // [rsp+A0h] [rbp-1058h]
  char v37[2048]; // [rsp+B0h] [rbp-1048h] BYREF
  WCHAR Buffer[1024]; // [rsp+8B0h] [rbp-848h] BYREF

  v32 = ppSendPacket;
  v33 = pcbSendPacket;
  v5 = sessionHandle;
  v28 = sessionHandle;
  v25 = 0;
  v29 = 0;
  v30 = 0;
  v6 = (unsigned __int64)GetCurrentThreadId() << 32;
  TickCount = GetTickCount();
  v9 = v6 | TickCount;
  v31 = v9;
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v27 = (EapHost::Peer::ConnectionSessionInfo *)(v6 | TickCount);
    v35 = (char *)&v27;
    v36 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)GetSendPacketStart, v8, 2, (__int64)v34);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v37, 0x800u, "EapHostPeerGetSendPacket Entry:\n Session(%d)", v5) >= 0 )
  {
    v11 = -1;
    if ( Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v37[v12] );
      v35 = v37;
      v36 = (unsigned int)(v12 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v10, 2, (__int64)v34);
    }
  }
  else
  {
    v11 = -1;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_e9255469090b376a053f3594056fdc10_Traceguids, v5);
  v27 = 0;
  if ( !v5 )
    goto LABEL_29;
  SessionFreeBuffers = EapHost::Peer::PeerProxy::FindSessionFreeBuffers((__int64)v13, v5, &v27, &v30, 0);
  if ( SessionFreeBuffers )
    goto LABEL_30;
  v15 = v33;
  if ( !v33 || (v16 = v32) == 0 )
  {
LABEL_29:
    SessionFreeBuffers = 160;
    goto LABEL_30;
  }
  if ( ppEapError )
    *ppEapError = 0;
  *v15 = 0;
  *v16 = 0;
  SessionFreeBuffers = (*(__int64 (__fastcall **)(LPVOID, _QWORD, DWORD *, BYTE **, EAP_ERROR **))(*(_QWORD *)v30 + 40LL))(
                         v30,
                         v5,
                         &v25,
                         &v29,
                         ppEapError);
  if ( SessionFreeBuffers >= 0 )
  {
    try
    {
      v17 = operator new(0x20u);
      if ( v17 )
      {
        v18 = v25;
        v19 = v29;
        *((_DWORD *)v17 + 2) = 0;
        *(_QWORD *)v17 = &EapHost::RawBuffer::`vftable';
        *((_QWORD *)v17 + 2) = v19;
        *((_QWORD *)v17 + 3) = v18;
        v26 = v17;
        _InterlockedIncrement((volatile signed __int32 *)v17 + 2);
      }
      else
      {
        v26 = 0;
      }
      EapHost::Peer::ConnectionSessionInfo::AddBuffer(v27, &v26);
      v20 = (void (__fastcall ***)(_QWORD, __int64))v26;
      if ( v26 && _InterlockedExchangeAdd((volatile signed __int32 *)v26 + 2, 0xFFFFFFFF) == 1 && v20 )
        (**v20)(v20, 1);
      *v32 = v29;
      *v33 = v25;
    }
    catch ( std::bad_alloc )
    {
      LODWORD(v26) = 14;
      v11 = -1;
      SessionFreeBuffers = 14;
      v5 = v28;
      v9 = v31;
    }
  }
LABEL_30:
  FormatMessageW(0x1200u, 0, SessionFreeBuffers, 0, Buffer, 0x400u, 0);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    LODWORD(nSize) = v25;
    LODWORD(lpBuffer) = v5;
    if ( (int)StringCchPrintfA(
                v37,
                0x800u,
                "EapHostPeerGetSendPacket Exit:\n %ws\n Returned session(%d), sending(%d) bytes data",
                Buffer,
                lpBuffer,
                nSize) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v11;
      while ( v37[v11] );
      v35 = v37;
      v36 = (unsigned int)(v11 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v21, 2, (__int64)v34);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v21, (unsigned int)SessionFreeBuffers, v5, v25);
  if ( v27 )
    _InterlockedCompareExchange((volatile signed __int32 *)v27 + 43, 0, *((_DWORD *)v27 + 43));
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v31 = v9;
    v35 = (char *)&v31;
    v36 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)GetSendPacketEnd, v21, 2, (__int64)v34);
  }
  if ( v30 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
  return SessionFreeBuffers;
}

```

## disassembly

```asm
0x180009230  push    rbx
0x180009232  push    rsi
0x180009233  push    rdi
0x180009234  push    r12
0x180009236  push    r13
0x180009238  push    r14
0x18000923a  push    r15
0x18000923c  mov     eax, 10C0h
0x180009241  call    _alloca_probe
0x180009246  sub     rsp, rax
0x180009249  mov     rax, cs:__security_cookie
0x180009250  xor     rax, rsp
0x180009253  mov     [rsp+10F8h+var_48], rax
0x18000925b  mov     r15, r9
0x18000925e  mov     [rsp+10F8h+var_1080], r8
0x180009263  mov     [rsp+10F8h+var_1078], rdx
0x18000926b  mov     r14d, ecx
0x18000926e  mov     [rsp+10F8h+var_10A0], ecx
0x180009272  xor     edi, edi
0x180009274  mov     [rsp+10F8h+var_10B8], edi
0x180009278  mov     [rsp+10F8h+var_1098], rdi
0x18000927d  mov     [rsp+10F8h+var_1090], rdi
0x180009282  call    cs:__imp_GetCurrentThreadId
0x180009289  nop     dword ptr [rax+rax+00h]
0x18000928e  mov     ebx, eax
0x180009290  shl     rbx, 20h
0x180009294  call    cs:__imp_GetTickCount
0x18000929b  nop     dword ptr [rax+rax+00h]
0x1800092a0  mov     r12d, eax
0x1800092a3  or      r12, rbx
0x1800092a6  mov     [rsp+10F8h+var_1088], r12
0x1800092ab  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x1800092b2  jge     short loc_1800092F6
0x1800092b4  mov     [rsp+10F8h+var_10A8], r12
0x1800092b9  lea     rax, [rsp+10F8h+var_10A8]
0x1800092be  mov     [rsp+10F8h+var_1060], rax
0x1800092c6  mov     [rsp+10F8h+var_1058], 8
0x1800092d2  lea     rax, [rsp+10F8h+var_1070]
0x1800092da  mov     [rsp+10F8h+lpBuffer], rax
0x1800092df  lea     r9d, [rdi+2]
0x1800092e3  lea     rdx, GetSendPacketStart
0x1800092ea  lea     rcx, eaphost_Context
0x1800092f1  call    McGenEventWrite_EtwEventWriteTransfer
0x1800092f6  lea     rdx, DebugInfoEvent
0x1800092fd  mov     rcx, cs:eaphost_Context
0x180009304  call    cs:__imp_EtwEventEnabled
0x18000930b  nop     dword ptr [rax+rax+00h]
0x180009310  test    al, al
0x180009312  jz      loc_1800093A1
0x180009318  mov     r9d, r14d
0x18000931b  lea     r8, aEaphostpeerget_21; "EapHostPeerGetSendPacket Entry:\n Sessi"...
0x180009322  mov     edx, 800h; unsigned __int64
0x180009327  lea     rcx, [rsp+10F8h+var_1048]; char *
0x18000932f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180009334  test    eax, eax
0x180009336  js      short loc_1800093A1
0x180009338  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000933c  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180009343  jge     short loc_1800093A5
0x180009345  lea     rcx, [rsp+10F8h+var_1048]
0x18000934d  mov     rax, rsi
0x180009350  inc     rax
0x180009353  cmp     [rcx+rax], dil
0x180009357  jnz     short loc_180009350
0x180009359  inc     eax
0x18000935b  lea     rcx, [rsp+10F8h+var_1048]
0x180009363  mov     [rsp+10F8h+var_1060], rcx
0x18000936b  mov     dword ptr [rsp+10F8h+var_1058], eax
0x180009372  mov     dword ptr [rsp+10F8h+var_1058+4], edi
0x180009379  lea     rax, [rsp+10F8h+var_1070]
0x180009381  mov     [rsp+10F8h+lpBuffer], rax
0x180009386  mov     r9d, 2
0x18000938c  lea     rdx, DebugInfoEvent
0x180009393  lea     rcx, eaphost_Context
0x18000939a  call    McGenEventWrite_EtwEventWriteTransfer
0x18000939f  jmp     short loc_1800093A5
0x1800093a1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800093a5  lea     r13, WPP_GLOBAL_Control
0x1800093ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093b3  cmp     rcx, r13
0x1800093b6  jz      short loc_1800093D6
0x1800093b8  test    byte ptr [rcx+1Ch], 4
0x1800093bc  jz      short loc_1800093D6
0x1800093be  mov     edx, 20h ; ' '
0x1800093c3  mov     r9d, r14d
0x1800093c6  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x1800093cd  mov     rcx, [rcx+10h]
0x1800093d1  call    WPP_SF_d
0x1800093d6  mov     [rsp+10F8h+var_10A8], rdi
0x1800093db  test    r14d, r14d
0x1800093de  jz      loc_18000950F
0x1800093e4  mov     dword ptr [rsp+10F8h+lpBuffer], edi
0x1800093e8  lea     r9, [rsp+10F8h+var_1090]
0x1800093ed  lea     r8, [rsp+10F8h+var_10A8]
0x1800093f2  mov     edx, r14d
0x1800093f5  call    ?FindSessionFreeBuffers@PeerProxy@Peer@EapHost@@QEAAKKAEAPEAVConnectionSessionInfo@23@AEAV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@H@Z; EapHost::Peer::PeerProxy::FindSessionFreeBuffers(ulong,EapHost::Peer::ConnectionSessionInfo * &,ATL::CComPtr<IEapHostPeerSessionApis> &,int)
0x1800093fa  mov     ebx, eax
0x1800093fc  test    eax, eax
0x1800093fe  jnz     loc_180009514
0x180009404  mov     rax, [rsp+10F8h+var_1078]
0x18000940c  test    rax, rax
0x18000940f  jz      loc_18000950F
0x180009415  mov     rcx, [rsp+10F8h+var_1080]
0x18000941a  test    rcx, rcx
0x18000941d  jz      loc_18000950F
0x180009423  test    r15, r15
0x180009426  jz      short loc_18000942B
0x180009428  mov     [r15], rdi
0x18000942b  mov     [rax], edi
0x18000942d  mov     [rcx], rdi
0x180009430  mov     rcx, [rsp+10F8h+var_1090]
0x180009435  mov     rax, [rcx]
0x180009438  mov     [rsp+10F8h+lpBuffer], r15
0x18000943d  lea     r9, [rsp+10F8h+var_1098]
0x180009442  lea     r8, [rsp+10F8h+var_10B8]
0x180009447  mov     edx, r14d
0x18000944a  mov     rax, [rax+28h]
0x18000944e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009453  mov     ebx, eax
0x180009455  test    eax, eax
0x180009457  js      loc_180009514
0x18000945d  mov     ecx, 20h ; ' '; dwBytes
0x180009462  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009467  test    rax, rax
0x18000946a  jz      short loc_180009495
0x18000946c  mov     edx, [rsp+10F8h+var_10B8]
0x180009470  mov     rcx, [rsp+10F8h+var_1098]
0x180009475  mov     [rax+8], edi
0x180009478  lea     r8, ??_7RawBuffer@EapHost@@6B@; const EapHost::RawBuffer::`vftable'
0x18000947f  mov     [rax], r8
0x180009482  mov     [rax+10h], rcx
0x180009486  mov     [rax+18h], rdx
0x18000948a  mov     [rsp+10F8h+var_10B0], rax
0x18000948f  lock inc dword ptr [rax+8]
0x180009493  jmp     short loc_18000949A
0x180009495  mov     [rsp+10F8h+var_10B0], rdi
0x18000949a  lea     rdx, [rsp+10F8h+var_10B0]
0x18000949f  mov     rcx, [rsp+10F8h+var_10A8]
0x1800094a4  call    ?AddBuffer@ConnectionSessionInfo@Peer@EapHost@@QEAAXAEBV?$SmartPointer@VReferenceCounted@@@@@Z; EapHost::Peer::ConnectionSessionInfo::AddBuffer(SmartPointer<ReferenceCounted> const &)
0x1800094a9  nop
0x1800094aa  mov     rcx, [rsp+10F8h+var_10B0]
0x1800094af  test    rcx, rcx
0x1800094b2  jz      short loc_1800094D5
0x1800094b4  mov     eax, esi
0x1800094b6  lock xadd [rcx+8], eax
0x1800094bb  add     eax, esi
0x1800094bd  jnz     short loc_1800094D5
0x1800094bf  test    rcx, rcx
0x1800094c2  jz      short loc_1800094D5
0x1800094c4  mov     rax, [rcx]
0x1800094c7  mov     edx, 1
0x1800094cc  mov     rax, [rax]
0x1800094cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d4  nop
0x1800094d5  mov     rax, [rsp+10F8h+var_1098]
0x1800094da  mov     rcx, [rsp+10F8h+var_1080]
0x1800094df  mov     [rcx], rax
0x1800094e2  mov     eax, [rsp+10F8h+var_10B8]
0x1800094e6  mov     rdx, [rsp+10F8h+var_1078]
0x1800094ee  mov     [rdx], eax
0x1800094f0  jmp     short loc_180009514
0x1800094f2  xor     edi, edi
0x1800094f4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800094f8  lea     r13, WPP_GLOBAL_Control
0x1800094ff  mov     ebx, dword ptr [rsp+10F8h+var_10B0]
0x180009503  mov     r14d, [rsp+10F8h+var_10A0]
0x180009508  mov     r12, [rsp+10F8h+var_1088]
0x18000950d  jmp     short loc_180009514
0x18000950f  mov     ebx, 0A0h
0x180009514  mov     [rsp+10F8h+Arguments], rdi; Arguments
0x180009519  mov     dword ptr [rsp+10F8h+nSize], 400h; nSize
0x180009521  lea     rax, [rsp+10F8h+Buffer]
0x180009529  mov     [rsp+10F8h+lpBuffer], rax; lpBuffer
0x18000952e  xor     r9d, r9d; dwLanguageId
0x180009531  mov     r8d, ebx; dwMessageId
0x180009534  xor     edx, edx; lpSource
0x180009536  mov     ecx, 1200h; dwFlags
0x18000953b  call    cs:__imp_FormatMessageW
0x180009542  nop     dword ptr [rax+rax+00h]
0x180009547  lea     rdx, DebugInfoEvent
0x18000954e  mov     rcx, cs:eaphost_Context
0x180009555  call    cs:__imp_EtwEventEnabled
0x18000955c  nop     dword ptr [rax+rax+00h]
0x180009561  test    al, al
0x180009563  jz      loc_1800095FC
0x180009569  mov     eax, [rsp+10F8h+var_10B8]
0x18000956d  mov     dword ptr [rsp+10F8h+nSize], eax
0x180009571  mov     dword ptr [rsp+10F8h+lpBuffer], r14d
0x180009576  lea     r9, [rsp+10F8h+Buffer]
0x18000957e  lea     r8, aEaphostpeerget_7; "EapHostPeerGetSendPacket Exit:\n %ws\n "...
0x180009585  mov     edx, 800h; unsigned __int64
0x18000958a  lea     rcx, [rsp+10F8h+var_1048]; char *
0x180009592  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180009597  test    eax, eax
0x180009599  js      short loc_1800095FC
0x18000959b  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x1800095a2  jge     short loc_1800095FC
0x1800095a4  lea     rax, [rsp+10F8h+var_1048]
0x1800095ac  inc     rsi
0x1800095af  cmp     [rax+rsi], dil
0x1800095b3  jnz     short loc_1800095AC
0x1800095b5  lea     eax, [rsi+1]
0x1800095b8  lea     rcx, [rsp+10F8h+var_1048]
0x1800095c0  mov     [rsp+10F8h+var_1060], rcx
0x1800095c8  mov     dword ptr [rsp+10F8h+var_1058], eax
0x1800095cf  mov     dword ptr [rsp+10F8h+var_1058+4], edi
0x1800095d6  lea     rax, [rsp+10F8h+var_1070]
0x1800095de  mov     [rsp+10F8h+lpBuffer], rax
0x1800095e3  mov     r9d, 2
0x1800095e9  lea     rdx, DebugInfoEvent
0x1800095f0  lea     rcx, eaphost_Context
0x1800095f7  call    McGenEventWrite_EtwEventWriteTransfer
0x1800095fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180009603  cmp     rcx, r13
0x180009606  jz      short loc_18000962C
0x180009608  test    byte ptr [rcx+1Ch], 4
0x18000960c  jz      short loc_18000962C
0x18000960e  mov     edx, 21h ; '!'
0x180009613  mov     eax, [rsp+10F8h+var_10B8]
0x180009617  mov     dword ptr [rsp+10F8h+nSize], eax
0x18000961b  mov     dword ptr [rsp+10F8h+lpBuffer], r14d
0x180009620  mov     r9d, ebx
0x180009623  mov     rcx, [rcx+10h]
0x180009627  call    WPP_SF_Ddd
0x18000962c  mov     rcx, [rsp+10F8h+var_10A8]
0x180009631  test    rcx, rcx
0x180009634  jz      short loc_180009644
0x180009636  mov     eax, [rcx+0ACh]
0x18000963c  lock cmpxchg [rcx+0ACh], edi
0x180009644  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x18000964b  jge     short loc_180009692
0x18000964d  mov     [rsp+10F8h+var_1088], r12
0x180009652  lea     rax, [rsp+10F8h+var_1088]
0x180009657  mov     [rsp+10F8h+var_1060], rax
0x18000965f  mov     [rsp+10F8h+var_1058], 8
0x18000966b  lea     rax, [rsp+10F8h+var_1070]
0x180009673  mov     [rsp+10F8h+lpBuffer], rax
0x180009678  mov     r9d, 2
0x18000967e  lea     rdx, GetSendPacketEnd
0x180009685  lea     rcx, eaphost_Context
0x18000968c  call    McGenEventWrite_EtwEventWriteTransfer
0x180009691  nop
0x180009692  mov     rcx, [rsp+10F8h+var_1090]
0x180009697  test    rcx, rcx
0x18000969a  jz      short loc_1800096A9
0x18000969c  mov     rax, [rcx]
0x18000969f  mov     rax, [rax+10h]
0x1800096a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a8  nop
0x1800096a9  mov     eax, ebx
0x1800096ab  mov     rcx, [rsp+10F8h+var_48]
0x1800096b3  xor     rcx, rsp; StackCookie
0x1800096b6  call    __security_check_cookie
0x1800096bb  add     rsp, 10C0h
0x1800096c2  pop     r15
0x1800096c4  pop     r14
0x1800096c6  pop     r13
0x1800096c8  pop     r12
0x1800096ca  pop     rdi
0x1800096cb  pop     rsi
0x1800096cc  pop     rbx
0x1800096cd  retn
```

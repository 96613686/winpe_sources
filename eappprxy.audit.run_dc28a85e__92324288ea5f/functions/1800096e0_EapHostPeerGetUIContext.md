# EapHostPeerGetUIContext

- ea: `0x1800096e0`
- end: `0x180009b7f`
- name: `EapHostPeerGetUIContext`
- size: `1183`
- prototype: `DWORD __stdcall(EAP_SESSIONID sessionHandle, DWORD *pdwSizeOfUIContextData, BYTE **ppUIContextData, EAP_ERROR **ppEapError)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x1800030f8`
- `0x180005450`
- `0x1800096e0`
- `0x18000ace0`
- `0x18000ade4`
- `0x18000af14`
- `0x18000b824`
- `0x18000bef4`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800097b4`
- `ntdll!EtwEventEnabled` at `0x180009a05`
- `ntdll!EtwEventEnabled` at `0x1800097b4`
- `ntdll!EtwEventEnabled` at `0x180009a05`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800099eb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800099eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009732`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009732`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009744`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009744`

## pseudocode

```c
DWORD __stdcall EapHostPeerGetUIContext(
        EAP_SESSIONID sessionHandle,
        DWORD *pdwSizeOfUIContextData,
        BYTE **ppUIContextData,
        EAP_ERROR **ppEapError)
{
  unsigned __int64 v6; // rbx
  DWORD TickCount; // eax
  __int64 v8; // r8
  unsigned __int64 v9; // r13
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

  v32 = ppUIContextData;
  v33 = pdwSizeOfUIContextData;
  v28 = sessionHandle;
  v29 = 0;
  v25 = 0;
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
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)GetUIContextStart, v8, 2, (__int64)v34);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v37, 0x800u, "EapHostPeerGetUIContext Entry:\n Session(%d)", sessionHandle) >= 0 )
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_e9255469090b376a053f3594056fdc10_Traceguids, sessionHandle);
  v27 = 0;
  if ( !sessionHandle )
    goto LABEL_28;
  SessionFreeBuffers = EapHost::Peer::PeerProxy::FindSessionFreeBuffers((__int64)v13, sessionHandle, &v27, &v30, 0);
  if ( SessionFreeBuffers )
    goto LABEL_29;
  v15 = v33;
  if ( !v33 || (v16 = v32) == 0 )
  {
LABEL_28:
    SessionFreeBuffers = 160;
    goto LABEL_29;
  }
  if ( ppEapError )
    *ppEapError = 0;
  *v15 = 0;
  *v16 = 0;
  SessionFreeBuffers = (*(__int64 (__fastcall **)(LPVOID, _QWORD, DWORD *, BYTE **, EAP_ERROR **))(*(_QWORD *)v30 + 56LL))(
                         v30,
                         sessionHandle,
                         &v25,
                         &v29,
                         ppEapError);
  if ( SessionFreeBuffers >= 0 )
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
LABEL_29:
  FormatMessageW(0x1200u, 0, SessionFreeBuffers, 0, Buffer, 0x400u, 0);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    LODWORD(nSize) = v25;
    LODWORD(lpBuffer) = sessionHandle;
    if ( (int)StringCchPrintfA(
                v37,
                0x800u,
                "EapHostPeerGetUIContext Exit:\n %ws\nReturned session(%d), UI context data(%d) bytes.",
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
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v21, (unsigned int)SessionFreeBuffers, sessionHandle, v25);
  if ( v27 )
    _InterlockedCompareExchange((volatile signed __int32 *)v27 + 43, 0, *((_DWORD *)v27 + 43));
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v31 = v9;
    v35 = (char *)&v31;
    v36 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)GetUIContextEnd, v21, 2, (__int64)v34);
  }
  if ( v30 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
  return SessionFreeBuffers;
}

```

## disassembly

```asm
0x1800096e0  push    rbx
0x1800096e2  push    rsi
0x1800096e3  push    rdi
0x1800096e4  push    r12
0x1800096e6  push    r13
0x1800096e8  push    r14
0x1800096ea  push    r15
0x1800096ec  mov     eax, 10C0h
0x1800096f1  call    _alloca_probe
0x1800096f6  sub     rsp, rax
0x1800096f9  mov     rax, cs:__security_cookie
0x180009700  xor     rax, rsp
0x180009703  mov     [rsp+10F8h+var_48], rax
0x18000970b  mov     r15, r9
0x18000970e  mov     [rsp+10F8h+var_1080], r8
0x180009713  mov     [rsp+10F8h+var_1078], rdx
0x18000971b  mov     r14d, ecx
0x18000971e  mov     [rsp+10F8h+var_10A0], ecx
0x180009722  xor     edi, edi
0x180009724  mov     [rsp+10F8h+var_1098], rdi
0x180009729  mov     [rsp+10F8h+var_10B8], edi
0x18000972d  mov     [rsp+10F8h+var_1090], rdi
0x180009732  call    cs:__imp_GetCurrentThreadId
0x180009739  nop     dword ptr [rax+rax+00h]
0x18000973e  mov     ebx, eax
0x180009740  shl     rbx, 20h
0x180009744  call    cs:__imp_GetTickCount
0x18000974b  nop     dword ptr [rax+rax+00h]
0x180009750  mov     r13d, eax
0x180009753  or      r13, rbx
0x180009756  mov     [rsp+10F8h+var_1088], r13
0x18000975b  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180009762  jge     short loc_1800097A6
0x180009764  mov     [rsp+10F8h+var_10A8], r13
0x180009769  lea     rax, [rsp+10F8h+var_10A8]
0x18000976e  mov     [rsp+10F8h+var_1060], rax
0x180009776  mov     [rsp+10F8h+var_1058], 8
0x180009782  lea     rax, [rsp+10F8h+var_1070]
0x18000978a  mov     [rsp+10F8h+lpBuffer], rax
0x18000978f  lea     r9d, [rdi+2]
0x180009793  lea     rdx, GetUIContextStart
0x18000979a  lea     rcx, eaphost_Context
0x1800097a1  call    McGenEventWrite_EtwEventWriteTransfer
0x1800097a6  lea     rdx, DebugInfoEvent
0x1800097ad  mov     rcx, cs:eaphost_Context
0x1800097b4  call    cs:__imp_EtwEventEnabled
0x1800097bb  nop     dword ptr [rax+rax+00h]
0x1800097c0  test    al, al
0x1800097c2  jz      loc_180009851
0x1800097c8  mov     r9d, r14d
0x1800097cb  lea     r8, aEaphostpeerget_16; "EapHostPeerGetUIContext Entry:\n Sessio"...
0x1800097d2  mov     edx, 800h; unsigned __int64
0x1800097d7  lea     rcx, [rsp+10F8h+var_1048]; char *
0x1800097df  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800097e4  test    eax, eax
0x1800097e6  js      short loc_180009851
0x1800097e8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800097ec  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x1800097f3  jge     short loc_180009855
0x1800097f5  lea     rcx, [rsp+10F8h+var_1048]
0x1800097fd  mov     rax, rsi
0x180009800  inc     rax
0x180009803  cmp     [rcx+rax], dil
0x180009807  jnz     short loc_180009800
0x180009809  inc     eax
0x18000980b  lea     rcx, [rsp+10F8h+var_1048]
0x180009813  mov     [rsp+10F8h+var_1060], rcx
0x18000981b  mov     dword ptr [rsp+10F8h+var_1058], eax
0x180009822  mov     dword ptr [rsp+10F8h+var_1058+4], edi
0x180009829  lea     rax, [rsp+10F8h+var_1070]
0x180009831  mov     [rsp+10F8h+lpBuffer], rax
0x180009836  mov     r9d, 2
0x18000983c  lea     rdx, DebugInfoEvent
0x180009843  lea     rcx, eaphost_Context
0x18000984a  call    McGenEventWrite_EtwEventWriteTransfer
0x18000984f  jmp     short loc_180009855
0x180009851  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009855  lea     r12, WPP_GLOBAL_Control
0x18000985c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009863  cmp     rcx, r12
0x180009866  jz      short loc_180009886
0x180009868  test    byte ptr [rcx+1Ch], 4
0x18000986c  jz      short loc_180009886
0x18000986e  mov     edx, 24h ; '$'
0x180009873  mov     r9d, r14d
0x180009876  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x18000987d  mov     rcx, [rcx+10h]
0x180009881  call    WPP_SF_d
0x180009886  mov     [rsp+10F8h+var_10A8], rdi
0x18000988b  test    r14d, r14d
0x18000988e  jz      loc_1800099BF
0x180009894  mov     dword ptr [rsp+10F8h+lpBuffer], edi
0x180009898  lea     r9, [rsp+10F8h+var_1090]
0x18000989d  lea     r8, [rsp+10F8h+var_10A8]
0x1800098a2  mov     edx, r14d
0x1800098a5  call    ?FindSessionFreeBuffers@PeerProxy@Peer@EapHost@@QEAAKKAEAPEAVConnectionSessionInfo@23@AEAV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@H@Z; EapHost::Peer::PeerProxy::FindSessionFreeBuffers(ulong,EapHost::Peer::ConnectionSessionInfo * &,ATL::CComPtr<IEapHostPeerSessionApis> &,int)
0x1800098aa  mov     ebx, eax
0x1800098ac  test    eax, eax
0x1800098ae  jnz     loc_1800099C4
0x1800098b4  mov     rax, [rsp+10F8h+var_1078]
0x1800098bc  test    rax, rax
0x1800098bf  jz      loc_1800099BF
0x1800098c5  mov     rcx, [rsp+10F8h+var_1080]
0x1800098ca  test    rcx, rcx
0x1800098cd  jz      loc_1800099BF
0x1800098d3  test    r15, r15
0x1800098d6  jz      short loc_1800098DB
0x1800098d8  mov     [r15], rdi
0x1800098db  mov     [rax], edi
0x1800098dd  mov     [rcx], rdi
0x1800098e0  mov     rcx, [rsp+10F8h+var_1090]
0x1800098e5  mov     rax, [rcx]
0x1800098e8  mov     [rsp+10F8h+lpBuffer], r15
0x1800098ed  lea     r9, [rsp+10F8h+var_1098]
0x1800098f2  lea     r8, [rsp+10F8h+var_10B8]
0x1800098f7  mov     edx, r14d
0x1800098fa  mov     rax, [rax+38h]
0x1800098fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009903  mov     ebx, eax
0x180009905  test    eax, eax
0x180009907  js      loc_1800099C4
0x18000990d  mov     ecx, 20h ; ' '; dwBytes
0x180009912  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009917  test    rax, rax
0x18000991a  jz      short loc_180009945
0x18000991c  mov     edx, [rsp+10F8h+var_10B8]
0x180009920  mov     rcx, [rsp+10F8h+var_1098]
0x180009925  mov     [rax+8], edi
0x180009928  lea     r8, ??_7RawBuffer@EapHost@@6B@; const EapHost::RawBuffer::`vftable'
0x18000992f  mov     [rax], r8
0x180009932  mov     [rax+10h], rcx
0x180009936  mov     [rax+18h], rdx
0x18000993a  mov     [rsp+10F8h+var_10B0], rax
0x18000993f  lock inc dword ptr [rax+8]
0x180009943  jmp     short loc_18000994A
0x180009945  mov     [rsp+10F8h+var_10B0], rdi
0x18000994a  lea     rdx, [rsp+10F8h+var_10B0]
0x18000994f  mov     rcx, [rsp+10F8h+var_10A8]
0x180009954  call    ?AddBuffer@ConnectionSessionInfo@Peer@EapHost@@QEAAXAEBV?$SmartPointer@VReferenceCounted@@@@@Z; EapHost::Peer::ConnectionSessionInfo::AddBuffer(SmartPointer<ReferenceCounted> const &)
0x180009959  nop
0x18000995a  mov     rcx, [rsp+10F8h+var_10B0]
0x18000995f  test    rcx, rcx
0x180009962  jz      short loc_180009985
0x180009964  mov     eax, esi
0x180009966  lock xadd [rcx+8], eax
0x18000996b  add     eax, esi
0x18000996d  jnz     short loc_180009985
0x18000996f  test    rcx, rcx
0x180009972  jz      short loc_180009985
0x180009974  mov     rax, [rcx]
0x180009977  mov     edx, 1
0x18000997c  mov     rax, [rax]
0x18000997f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009984  nop
0x180009985  mov     rax, [rsp+10F8h+var_1098]
0x18000998a  mov     rcx, [rsp+10F8h+var_1080]
0x18000998f  mov     [rcx], rax
0x180009992  mov     eax, [rsp+10F8h+var_10B8]
0x180009996  mov     rdx, [rsp+10F8h+var_1078]
0x18000999e  mov     [rdx], eax
0x1800099a0  jmp     short loc_1800099C4
0x1800099a2  xor     edi, edi
0x1800099a4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800099a8  lea     r12, WPP_GLOBAL_Control
0x1800099af  mov     ebx, dword ptr [rsp+10F8h+var_10B0]
0x1800099b3  mov     r14d, [rsp+10F8h+var_10A0]
0x1800099b8  mov     r13, [rsp+10F8h+var_1088]
0x1800099bd  jmp     short loc_1800099C4
0x1800099bf  mov     ebx, 0A0h
0x1800099c4  mov     [rsp+10F8h+Arguments], rdi; Arguments
0x1800099c9  mov     dword ptr [rsp+10F8h+nSize], 400h; nSize
0x1800099d1  lea     rax, [rsp+10F8h+Buffer]
0x1800099d9  mov     [rsp+10F8h+lpBuffer], rax; lpBuffer
0x1800099de  xor     r9d, r9d; dwLanguageId
0x1800099e1  mov     r8d, ebx; dwMessageId
0x1800099e4  xor     edx, edx; lpSource
0x1800099e6  mov     ecx, 1200h; dwFlags
0x1800099eb  call    cs:__imp_FormatMessageW
0x1800099f2  nop     dword ptr [rax+rax+00h]
0x1800099f7  lea     rdx, DebugInfoEvent
0x1800099fe  mov     rcx, cs:eaphost_Context
0x180009a05  call    cs:__imp_EtwEventEnabled
0x180009a0c  nop     dword ptr [rax+rax+00h]
0x180009a11  test    al, al
0x180009a13  jz      loc_180009AAC
0x180009a19  mov     eax, [rsp+10F8h+var_10B8]
0x180009a1d  mov     dword ptr [rsp+10F8h+nSize], eax
0x180009a21  mov     dword ptr [rsp+10F8h+lpBuffer], r14d
0x180009a26  lea     r9, [rsp+10F8h+Buffer]
0x180009a2e  lea     r8, aEaphostpeerget_11; "EapHostPeerGetUIContext Exit:\n %ws\nRe"...
0x180009a35  mov     edx, 800h; unsigned __int64
0x180009a3a  lea     rcx, [rsp+10F8h+var_1048]; char *
0x180009a42  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180009a47  test    eax, eax
0x180009a49  js      short loc_180009AAC
0x180009a4b  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180009a52  jge     short loc_180009AAC
0x180009a54  lea     rax, [rsp+10F8h+var_1048]
0x180009a5c  inc     rsi
0x180009a5f  cmp     [rax+rsi], dil
0x180009a63  jnz     short loc_180009A5C
0x180009a65  lea     eax, [rsi+1]
0x180009a68  lea     rcx, [rsp+10F8h+var_1048]
0x180009a70  mov     [rsp+10F8h+var_1060], rcx
0x180009a78  mov     dword ptr [rsp+10F8h+var_1058], eax
0x180009a7f  mov     dword ptr [rsp+10F8h+var_1058+4], edi
0x180009a86  lea     rax, [rsp+10F8h+var_1070]
0x180009a8e  mov     [rsp+10F8h+lpBuffer], rax
0x180009a93  mov     r9d, 2
0x180009a99  lea     rdx, DebugInfoEvent
0x180009aa0  lea     rcx, eaphost_Context
0x180009aa7  call    McGenEventWrite_EtwEventWriteTransfer
0x180009aac  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ab3  cmp     rcx, r12
0x180009ab6  jz      short loc_180009ADC
0x180009ab8  test    byte ptr [rcx+1Ch], 4
0x180009abc  jz      short loc_180009ADC
0x180009abe  mov     edx, 25h ; '%'
0x180009ac3  mov     eax, [rsp+10F8h+var_10B8]
0x180009ac7  mov     dword ptr [rsp+10F8h+nSize], eax
0x180009acb  mov     dword ptr [rsp+10F8h+lpBuffer], r14d
0x180009ad0  mov     r9d, ebx
0x180009ad3  mov     rcx, [rcx+10h]
0x180009ad7  call    WPP_SF_Ddd
0x180009adc  mov     rcx, [rsp+10F8h+var_10A8]
0x180009ae1  test    rcx, rcx
0x180009ae4  jz      short loc_180009AF4
0x180009ae6  mov     eax, [rcx+0ACh]
0x180009aec  lock cmpxchg [rcx+0ACh], edi
0x180009af4  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180009afb  jge     short loc_180009B42
0x180009afd  mov     [rsp+10F8h+var_1088], r13
0x180009b02  lea     rax, [rsp+10F8h+var_1088]
0x180009b07  mov     [rsp+10F8h+var_1060], rax
0x180009b0f  mov     [rsp+10F8h+var_1058], 8
0x180009b1b  lea     rax, [rsp+10F8h+var_1070]
0x180009b23  mov     [rsp+10F8h+lpBuffer], rax
0x180009b28  mov     r9d, 2
0x180009b2e  lea     rdx, GetUIContextEnd
0x180009b35  lea     rcx, eaphost_Context
0x180009b3c  call    McGenEventWrite_EtwEventWriteTransfer
0x180009b41  nop
0x180009b42  mov     rcx, [rsp+10F8h+var_1090]
0x180009b47  test    rcx, rcx
0x180009b4a  jz      short loc_180009B59
0x180009b4c  mov     rax, [rcx]
0x180009b4f  mov     rax, [rax+10h]
0x180009b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b58  nop
0x180009b59  mov     eax, ebx
0x180009b5b  mov     rcx, [rsp+10F8h+var_48]
0x180009b63  xor     rcx, rsp; StackCookie
0x180009b66  call    __security_check_cookie
0x180009b6b  add     rsp, 10C0h
0x180009b72  pop     r15
0x180009b74  pop     r14
0x180009b76  pop     r13
0x180009b78  pop     r12
0x180009b7a  pop     rdi
0x180009b7b  pop     rsi
0x180009b7c  pop     rbx
0x180009b7d  retn
```

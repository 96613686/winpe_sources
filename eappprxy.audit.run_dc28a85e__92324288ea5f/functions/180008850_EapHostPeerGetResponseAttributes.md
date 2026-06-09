# EapHostPeerGetResponseAttributes

- ea: `0x180008850`
- end: `0x180008cde`
- name: `EapHostPeerGetResponseAttributes`
- size: `1166`
- prototype: `DWORD __stdcall(EAP_SESSIONID sessionHandle, EapAttributes *pAttribs, EAP_ERROR **ppEapError)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x1800020d6`
- `0x1800030f8`
- `0x180005450`
- `0x180008850`
- `0x18000ace0`
- `0x18000ade4`
- `0x18000af14`
- `0x18000b824`
- `0x18000bef4`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008a95`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008a95`
- `ntdll!EtwEventEnabled` at `0x18000891b`
- `ntdll!EtwEventEnabled` at `0x180008b64`
- `ntdll!EtwEventEnabled` at `0x18000891b`
- `ntdll!EtwEventEnabled` at `0x180008b64`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008b4a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008b4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008899`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008899`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800088ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800088ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
DWORD __stdcall EapHostPeerGetResponseAttributes(
        EAP_SESSIONID sessionHandle,
        EapAttributes *pAttribs,
        EAP_ERROR **ppEapError)
{
  EAP_SESSIONID v4; // r15d
  unsigned __int64 v5; // rbx
  DWORD TickCount; // eax
  __int64 v7; // r8
  unsigned __int64 v8; // r12
  __int64 v9; // r8
  __int64 v10; // rsi
  __int64 v11; // rax
  void *v12; // rcx
  signed int SessionFreeBuffers; // ebx
  EapAttributes *v14; // rax
  EapAttributes *v15; // rax
  volatile signed __int32 *v16; // r14
  EapAttributes *v17; // rax
  volatile signed __int32 *v18; // rcx
  __int64 v19; // r8
  LPWSTR lpBuffer; // [rsp+20h] [rbp-10C8h]
  __int64 nSize; // [rsp+28h] [rbp-10C0h]
  volatile signed __int32 *v23; // [rsp+40h] [rbp-10A8h] BYREF
  EapHost::Peer::ConnectionSessionInfo *v24; // [rsp+48h] [rbp-10A0h] BYREF
  EAP_SESSIONID v25; // [rsp+50h] [rbp-1098h]
  LPVOID v26; // [rsp+58h] [rbp-1090h] BYREF
  unsigned __int64 v27; // [rsp+60h] [rbp-1088h] BYREF
  EapAttributes v28; // [rsp+68h] [rbp-1080h] BYREF
  EapAttributes *v29; // [rsp+78h] [rbp-1070h]
  _BYTE v30[16]; // [rsp+80h] [rbp-1068h] BYREF
  char *v31; // [rsp+90h] [rbp-1058h]
  __int64 v32; // [rsp+98h] [rbp-1050h]
  char v33[2048]; // [rsp+A0h] [rbp-1048h] BYREF
  WCHAR Buffer[1024]; // [rsp+8A0h] [rbp-848h] BYREF

  v29 = pAttribs;
  v4 = sessionHandle;
  v25 = sessionHandle;
  v28 = 0;
  v26 = 0;
  v5 = (unsigned __int64)GetCurrentThreadId() << 32;
  TickCount = GetTickCount();
  v8 = v5 | TickCount;
  v27 = v8;
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v24 = (EapHost::Peer::ConnectionSessionInfo *)(v5 | TickCount);
    v31 = (char *)&v24;
    v32 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)GetRespAttribStart, v7, 2, (__int64)v30);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v33, 0x800u, "EapHostPeerGetResponseAttributes Entry:\n Session(%d)", v4) >= 0 )
  {
    v10 = -1;
    if ( Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v33[v11] );
      v31 = v33;
      v32 = (unsigned int)(v11 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v9, 2, (__int64)v30);
    }
  }
  else
  {
    v10 = -1;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_e9255469090b376a053f3594056fdc10_Traceguids, v4);
  v24 = 0;
  if ( !v4 )
    goto LABEL_14;
  SessionFreeBuffers = EapHost::Peer::PeerProxy::FindSessionFreeBuffers((__int64)v12, v4, &v24, &v26, 0);
  if ( SessionFreeBuffers )
    goto LABEL_32;
  v14 = v29;
  if ( v29 )
  {
    if ( ppEapError )
      *ppEapError = 0;
    *v14 = v28;
    SessionFreeBuffers = (*(__int64 (__fastcall **)(LPVOID, _QWORD, EapAttributes *, EAP_ERROR **))(*(_QWORD *)v26 + 72LL))(
                           v26,
                           v4,
                           &v28,
                           ppEapError);
    if ( SessionFreeBuffers >= 0 )
    {
      try
      {
        v15 = (EapAttributes *)operator new(0x20u);
        v16 = (volatile signed __int32 *)v15;
        if ( v15 )
        {
          LODWORD(v15->pAttribs) = 0;
          *(_QWORD *)&v15->dwNumberOfAttributes = &EapHost::EapAttributesBuffer::`vftable';
          v17 = v15 + 1;
          if ( v16 == (volatile signed __int32 *)-16LL )
          {
            *(_DWORD *)_o__errno() = 22;
            invalid_parameter_noinfo();
          }
          else
          {
            *v17 = v28;
          }
          v23 = v16;
          _InterlockedIncrement(v16 + 2);
        }
        else
        {
          v23 = 0;
        }
        EapHost::Peer::ConnectionSessionInfo::AddBuffer(v24, &v23);
        v18 = v23;
        if ( v23 && _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 && v18 )
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v18)(v18, 1);
        *v29 = v28;
      }
      catch ( std::bad_alloc )
      {
        LODWORD(v23) = 14;
        v10 = -1;
        SessionFreeBuffers = 14;
        v4 = v25;
        v8 = v27;
      }
    }
  }
  else
  {
LABEL_14:
    SessionFreeBuffers = 160;
  }
LABEL_32:
  FormatMessageW(0x1200u, 0, SessionFreeBuffers, 0, Buffer, 0x400u, 0);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    LODWORD(nSize) = v28.dwNumberOfAttributes;
    LODWORD(lpBuffer) = v4;
    if ( (int)StringCchPrintfA(
                v33,
                0x800u,
                "EapHostPeerGetResponseAttributes Exit:\n %ws\nReturned session(%d), # of attributes(%d).",
                Buffer,
                lpBuffer,
                nSize) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v10;
      while ( v33[v10] );
      v31 = v33;
      v32 = (unsigned int)(v10 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v19, 2, (__int64)v30);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Ddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      v19,
      (unsigned int)SessionFreeBuffers,
      v4,
      v28.dwNumberOfAttributes);
  if ( v24 )
    _InterlockedCompareExchange((volatile signed __int32 *)v24 + 43, 0, *((_DWORD *)v24 + 43));
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v27 = v8;
    v31 = (char *)&v27;
    v32 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)GetRespAttribEnd, v19, 2, (__int64)v30);
  }
  if ( v26 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
  return SessionFreeBuffers;
}

```

## disassembly

```asm
0x180008850  push    rbx
0x180008852  push    rsi
0x180008853  push    rdi
0x180008854  push    r12
0x180008856  push    r13
0x180008858  push    r14
0x18000885a  push    r15
0x18000885c  mov     eax, 10B0h
0x180008861  call    _alloca_probe
0x180008866  sub     rsp, rax
0x180008869  mov     rax, cs:__security_cookie
0x180008870  xor     rax, rsp
0x180008873  mov     [rsp+10E8h+var_48], rax
0x18000887b  mov     r14, r8
0x18000887e  mov     [rsp+10E8h+var_1070], rdx
0x180008883  mov     r15d, ecx
0x180008886  mov     [rsp+10E8h+var_1098], ecx
0x18000888a  xorps   xmm0, xmm0
0x18000888d  movups  [rsp+10E8h+var_1080], xmm0
0x180008892  xor     edi, edi
0x180008894  mov     [rsp+10E8h+var_1090], rdi
0x180008899  call    cs:__imp_GetCurrentThreadId
0x1800088a0  nop     dword ptr [rax+rax+00h]
0x1800088a5  mov     ebx, eax
0x1800088a7  shl     rbx, 20h
0x1800088ab  call    cs:__imp_GetTickCount
0x1800088b2  nop     dword ptr [rax+rax+00h]
0x1800088b7  mov     r12d, eax
0x1800088ba  or      r12, rbx
0x1800088bd  mov     [rsp+10E8h+var_1088], r12
0x1800088c2  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x1800088c9  jge     short loc_18000890D
0x1800088cb  mov     [rsp+10E8h+var_10A0], r12
0x1800088d0  lea     rax, [rsp+10E8h+var_10A0]
0x1800088d5  mov     [rsp+10E8h+var_1058], rax
0x1800088dd  mov     [rsp+10E8h+var_1050], 8
0x1800088e9  lea     rax, [rsp+10E8h+var_1068]
0x1800088f1  mov     [rsp+10E8h+lpBuffer], rax
0x1800088f6  lea     r9d, [rdi+2]
0x1800088fa  lea     rdx, GetRespAttribStart
0x180008901  lea     rcx, eaphost_Context
0x180008908  call    McGenEventWrite_EtwEventWriteTransfer
0x18000890d  lea     rdx, DebugInfoEvent
0x180008914  mov     rcx, cs:eaphost_Context
0x18000891b  call    cs:__imp_EtwEventEnabled
0x180008922  nop     dword ptr [rax+rax+00h]
0x180008927  test    al, al
0x180008929  jz      loc_1800089B8
0x18000892f  mov     r9d, r15d
0x180008932  lea     r8, aEaphostpeerget_19; "EapHostPeerGetResponseAttributes Entry:"...
0x180008939  mov     edx, 800h; unsigned __int64
0x18000893e  lea     rcx, [rsp+10E8h+var_1048]; char *
0x180008946  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000894b  test    eax, eax
0x18000894d  js      short loc_1800089B8
0x18000894f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008953  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x18000895a  jge     short loc_1800089BC
0x18000895c  lea     rcx, [rsp+10E8h+var_1048]
0x180008964  mov     rax, rsi
0x180008967  inc     rax
0x18000896a  cmp     [rcx+rax], dil
0x18000896e  jnz     short loc_180008967
0x180008970  inc     eax
0x180008972  lea     rcx, [rsp+10E8h+var_1048]
0x18000897a  mov     [rsp+10E8h+var_1058], rcx
0x180008982  mov     dword ptr [rsp+10E8h+var_1050], eax
0x180008989  mov     dword ptr [rsp+10E8h+var_1050+4], edi
0x180008990  lea     rax, [rsp+10E8h+var_1068]
0x180008998  mov     [rsp+10E8h+lpBuffer], rax
0x18000899d  mov     r9d, 2
0x1800089a3  lea     rdx, DebugInfoEvent
0x1800089aa  lea     rcx, eaphost_Context
0x1800089b1  call    McGenEventWrite_EtwEventWriteTransfer
0x1800089b6  jmp     short loc_1800089BC
0x1800089b8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800089bc  lea     r13, WPP_GLOBAL_Control
0x1800089c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089ca  cmp     rcx, r13
0x1800089cd  jz      short loc_1800089ED
0x1800089cf  test    byte ptr [rcx+1Ch], 4
0x1800089d3  jz      short loc_1800089ED
0x1800089d5  mov     edx, 28h ; '('
0x1800089da  mov     r9d, r15d
0x1800089dd  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x1800089e4  mov     rcx, [rcx+10h]
0x1800089e8  call    WPP_SF_d
0x1800089ed  mov     [rsp+10E8h+var_10A0], rdi
0x1800089f2  test    r15d, r15d
0x1800089f5  jnz     short loc_180008A01
0x1800089f7  mov     ebx, 0A0h
0x1800089fc  jmp     loc_180008B23
0x180008a01  mov     dword ptr [rsp+10E8h+lpBuffer], edi
0x180008a05  lea     r9, [rsp+10E8h+var_1090]
0x180008a0a  lea     r8, [rsp+10E8h+var_10A0]
0x180008a0f  mov     edx, r15d
0x180008a12  call    ?FindSessionFreeBuffers@PeerProxy@Peer@EapHost@@QEAAKKAEAPEAVConnectionSessionInfo@23@AEAV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@H@Z; EapHost::Peer::PeerProxy::FindSessionFreeBuffers(ulong,EapHost::Peer::ConnectionSessionInfo * &,ATL::CComPtr<IEapHostPeerSessionApis> &,int)
0x180008a17  mov     ebx, eax
0x180008a19  test    eax, eax
0x180008a1b  jnz     loc_180008B23
0x180008a21  mov     rax, [rsp+10E8h+var_1070]
0x180008a26  test    rax, rax
0x180008a29  jz      short loc_1800089F7
0x180008a2b  test    r14, r14
0x180008a2e  jz      short loc_180008A33
0x180008a30  mov     [r14], rdi
0x180008a33  movups  xmm0, [rsp+10E8h+var_1080]
0x180008a38  movdqu  xmmword ptr [rax], xmm0
0x180008a3c  mov     rcx, [rsp+10E8h+var_1090]
0x180008a41  mov     rax, [rcx]
0x180008a44  mov     r9, r14
0x180008a47  lea     r8, [rsp+10E8h+var_1080]
0x180008a4c  mov     edx, r15d
0x180008a4f  mov     rax, [rax+48h]
0x180008a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a58  mov     ebx, eax
0x180008a5a  test    eax, eax
0x180008a5c  js      loc_180008B23
0x180008a62  mov     ecx, 20h ; ' '; dwBytes
0x180008a67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008a6c  mov     r14, rax
0x180008a6f  test    rax, rax
0x180008a72  jz      short loc_180008AB8
0x180008a74  mov     [rax+8], edi
0x180008a77  lea     rax, ??_7EapAttributesBuffer@EapHost@@6B@; const EapHost::EapAttributesBuffer::`vftable'
0x180008a7e  mov     [r14], rax
0x180008a81  lea     rax, [r14+10h]
0x180008a85  test    rax, rax
0x180008a88  jz      short loc_180008A95
0x180008a8a  movups  xmm0, [rsp+10E8h+var_1080]
0x180008a8f  movdqu  xmmword ptr [rax], xmm0
0x180008a93  jmp     short loc_180008AAC
0x180008a95  call    cs:__imp__o__errno
0x180008a9c  nop     dword ptr [rax+rax+00h]
0x180008aa1  mov     dword ptr [rax], 16h
0x180008aa7  call    _invalid_parameter_noinfo
0x180008aac  mov     [rsp+10E8h+var_10A8], r14
0x180008ab1  lock inc dword ptr [r14+8]
0x180008ab6  jmp     short loc_180008ABD
0x180008ab8  mov     [rsp+10E8h+var_10A8], rdi
0x180008abd  lea     rdx, [rsp+10E8h+var_10A8]
0x180008ac2  mov     rcx, [rsp+10E8h+var_10A0]
0x180008ac7  call    ?AddBuffer@ConnectionSessionInfo@Peer@EapHost@@QEAAXAEBV?$SmartPointer@VReferenceCounted@@@@@Z; EapHost::Peer::ConnectionSessionInfo::AddBuffer(SmartPointer<ReferenceCounted> const &)
0x180008acc  nop
0x180008acd  mov     rcx, [rsp+10E8h+var_10A8]
0x180008ad2  test    rcx, rcx
0x180008ad5  jz      short loc_180008AF8
0x180008ad7  mov     eax, esi
0x180008ad9  lock xadd [rcx+8], eax
0x180008ade  add     eax, esi
0x180008ae0  jnz     short loc_180008AF8
0x180008ae2  test    rcx, rcx
0x180008ae5  jz      short loc_180008AF8
0x180008ae7  mov     rax, [rcx]
0x180008aea  mov     edx, 1
0x180008aef  mov     rax, [rax]
0x180008af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008af7  nop
0x180008af8  movups  xmm0, [rsp+10E8h+var_1080]
0x180008afd  mov     rdx, [rsp+10E8h+var_1070]
0x180008b02  movdqu  xmmword ptr [rdx], xmm0
0x180008b06  jmp     short loc_180008B23
0x180008b08  xor     edi, edi
0x180008b0a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008b0e  lea     r13, WPP_GLOBAL_Control
0x180008b15  mov     ebx, dword ptr [rsp+10E8h+var_10A8]
0x180008b19  mov     r15d, [rsp+10E8h+var_1098]
0x180008b1e  mov     r12, [rsp+10E8h+var_1088]
0x180008b23  mov     [rsp+10E8h+Arguments], rdi; Arguments
0x180008b28  mov     dword ptr [rsp+10E8h+nSize], 400h; nSize
0x180008b30  lea     rax, [rsp+10E8h+Buffer]
0x180008b38  mov     [rsp+10E8h+lpBuffer], rax; lpBuffer
0x180008b3d  xor     r9d, r9d; dwLanguageId
0x180008b40  mov     r8d, ebx; dwMessageId
0x180008b43  xor     edx, edx; lpSource
0x180008b45  mov     ecx, 1200h; dwFlags
0x180008b4a  call    cs:__imp_FormatMessageW
0x180008b51  nop     dword ptr [rax+rax+00h]
0x180008b56  lea     rdx, DebugInfoEvent
0x180008b5d  mov     rcx, cs:eaphost_Context
0x180008b64  call    cs:__imp_EtwEventEnabled
0x180008b6b  nop     dword ptr [rax+rax+00h]
0x180008b70  test    al, al
0x180008b72  jz      loc_180008C0B
0x180008b78  mov     eax, dword ptr [rsp+10E8h+var_1080]
0x180008b7c  mov     dword ptr [rsp+10E8h+nSize], eax
0x180008b80  mov     dword ptr [rsp+10E8h+lpBuffer], r15d
0x180008b85  lea     r9, [rsp+10E8h+Buffer]
0x180008b8d  lea     r8, aEaphostpeerget_12; "EapHostPeerGetResponseAttributes Exit:"...
0x180008b94  mov     edx, 800h; unsigned __int64
0x180008b99  lea     rcx, [rsp+10E8h+var_1048]; char *
0x180008ba1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180008ba6  test    eax, eax
0x180008ba8  js      short loc_180008C0B
0x180008baa  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180008bb1  jge     short loc_180008C0B
0x180008bb3  lea     rax, [rsp+10E8h+var_1048]
0x180008bbb  inc     rsi
0x180008bbe  cmp     [rax+rsi], dil
0x180008bc2  jnz     short loc_180008BBB
0x180008bc4  lea     eax, [rsi+1]
0x180008bc7  lea     rcx, [rsp+10E8h+var_1048]
0x180008bcf  mov     [rsp+10E8h+var_1058], rcx
0x180008bd7  mov     dword ptr [rsp+10E8h+var_1050], eax
0x180008bde  mov     dword ptr [rsp+10E8h+var_1050+4], edi
0x180008be5  lea     rax, [rsp+10E8h+var_1068]
0x180008bed  mov     [rsp+10E8h+lpBuffer], rax
0x180008bf2  mov     r9d, 2
0x180008bf8  lea     rdx, DebugInfoEvent
0x180008bff  lea     rcx, eaphost_Context
0x180008c06  call    McGenEventWrite_EtwEventWriteTransfer
0x180008c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c12  cmp     rcx, r13
0x180008c15  jz      short loc_180008C3B
0x180008c17  test    byte ptr [rcx+1Ch], 4
0x180008c1b  jz      short loc_180008C3B
0x180008c1d  mov     edx, 29h ; ')'
0x180008c22  mov     eax, dword ptr [rsp+10E8h+var_1080]
0x180008c26  mov     dword ptr [rsp+10E8h+nSize], eax
0x180008c2a  mov     dword ptr [rsp+10E8h+lpBuffer], r15d
0x180008c2f  mov     r9d, ebx
0x180008c32  mov     rcx, [rcx+10h]
0x180008c36  call    WPP_SF_Ddd
0x180008c3b  mov     rcx, [rsp+10E8h+var_10A0]
0x180008c40  test    rcx, rcx
0x180008c43  jz      short loc_180008C53
0x180008c45  mov     eax, [rcx+0ACh]
0x180008c4b  lock cmpxchg [rcx+0ACh], edi
0x180008c53  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180008c5a  jge     short loc_180008CA1
0x180008c5c  mov     [rsp+10E8h+var_1088], r12
0x180008c61  lea     rax, [rsp+10E8h+var_1088]
0x180008c66  mov     [rsp+10E8h+var_1058], rax
0x180008c6e  mov     [rsp+10E8h+var_1050], 8
0x180008c7a  lea     rax, [rsp+10E8h+var_1068]
0x180008c82  mov     [rsp+10E8h+lpBuffer], rax
0x180008c87  mov     r9d, 2
0x180008c8d  lea     rdx, GetRespAttribEnd
0x180008c94  lea     rcx, eaphost_Context
0x180008c9b  call    McGenEventWrite_EtwEventWriteTransfer
0x180008ca0  nop
0x180008ca1  mov     rcx, [rsp+10E8h+var_1090]
0x180008ca6  test    rcx, rcx
0x180008ca9  jz      short loc_180008CB8
0x180008cab  mov     rax, [rcx]
0x180008cae  mov     rax, [rax+10h]
0x180008cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb7  nop
0x180008cb8  mov     eax, ebx
0x180008cba  mov     rcx, [rsp+10E8h+var_48]
0x180008cc2  xor     rcx, rsp; StackCookie
0x180008cc5  call    __security_check_cookie
0x180008cca  add     rsp, 10B0h
0x180008cd1  pop     r15
0x180008cd3  pop     r14
0x180008cd5  pop     r13
0x180008cd7  pop     r12
0x180008cd9  pop     rdi
0x180008cda  pop     rsi
0x180008cdb  pop     rbx
0x180008cdc  retn
```

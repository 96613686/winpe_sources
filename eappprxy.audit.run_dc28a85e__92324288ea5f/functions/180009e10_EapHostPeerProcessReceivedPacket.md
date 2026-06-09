# EapHostPeerProcessReceivedPacket

- ea: `0x180009e10`
- end: `0x18000a1a8`
- name: `EapHostPeerProcessReceivedPacket`
- size: `920`
- prototype: `DWORD __stdcall(EAP_SESSIONID sessionHandle, DWORD cbReceivePacket, const BYTE *const pReceivePacket, EapHostPeerResponseAction *pEapOutput, EAP_ERROR **ppEapError)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x180005450`
- `0x180009e10`
- `0x18000ace0`
- `0x18000aeb8`
- `0x18000af14`
- `0x18000bef4`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180009edd`
- `ntdll!EtwEventEnabled` at `0x18000a04b`
- `ntdll!EtwEventEnabled` at `0x180009edd`
- `ntdll!EtwEventEnabled` at `0x18000a04b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a031`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a031`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e68`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009e7a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009e7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __stdcall EapHostPeerProcessReceivedPacket(
        EAP_SESSIONID sessionHandle,
        DWORD cbReceivePacket,
        const BYTE *const pReceivePacket,
        EapHostPeerResponseAction *pEapOutput,
        EAP_ERROR **ppEapError)
{
  unsigned __int64 v8; // rbx
  __int64 v9; // r8
  EapHost::Peer::ConnectionSessionInfo *v10; // r13
  __int64 v11; // r8
  __int64 v12; // rdi
  __int64 v13; // rax
  void *v14; // rcx
  signed int SessionFreeBuffers; // ebx
  __int64 v16; // r8
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h]
  DWORD nSize[2]; // [rsp+28h] [rbp-D8h]
  EapHostPeerResponseAction v20; // [rsp+40h] [rbp-C0h] BYREF
  EapHost::Peer::ConnectionSessionInfo *v21; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v22; // [rsp+50h] [rbp-B0h] BYREF
  const BYTE *v23; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v24[16]; // [rsp+60h] [rbp-A0h] BYREF
  char *v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  char v27[2048]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[1024]; // [rsp+880h] [rbp+780h] BYREF

  v23 = pReceivePacket;
  v20 = EapHostPeerResponseNone;
  v22 = 0;
  v8 = (unsigned __int64)GetCurrentThreadId() << 32;
  v10 = (EapHost::Peer::ConnectionSessionInfo *)(v8 | GetTickCount());
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v21 = v10;
    v25 = (char *)&v21;
    v26 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)ProcessRPStart, v9, 2, (__int64)v24);
  }
  v12 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v27,
              0x800u,
              "EapHostPeerProcessReceivedPacket Entry:\n Session(%d), received(%d) bytes",
              sessionHandle,
              cbReceivePacket) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v27[v13] );
    v25 = v27;
    v26 = (unsigned int)(v13 + 1);
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v11, 2, (__int64)v24);
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v11, sessionHandle, cbReceivePacket);
  v21 = 0;
  SessionFreeBuffers = EapHost::Peer::PeerProxy::FindSessionFreeBuffers((__int64)v14, sessionHandle, &v21, &v22, 1);
  if ( !SessionFreeBuffers )
  {
    if ( pEapOutput )
    {
      if ( ppEapError )
        *ppEapError = 0;
      *pEapOutput = v20;
      SessionFreeBuffers = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, const BYTE *, EapHostPeerResponseAction *, EAP_ERROR **))(*(_QWORD *)v22 + 32LL))(
                             v22,
                             sessionHandle,
                             cbReceivePacket,
                             v23,
                             &v20,
                             ppEapError);
      if ( SessionFreeBuffers >= 0 )
        *pEapOutput = v20;
    }
    else
    {
      SessionFreeBuffers = 160;
    }
  }
  FormatMessageW(0x1200u, 0, SessionFreeBuffers, 0, Buffer, 0x400u, 0);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    nSize[0] = v20;
    LODWORD(lpBuffer) = sessionHandle;
    if ( (int)StringCchPrintfA(
                v27,
                0x800u,
                "EapHostPeerProcessReceivedPacket Exit:\n %ws\nReturned session(%d), action(%d).",
                Buffer,
                lpBuffer,
                *(_QWORD *)nSize) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v12;
      while ( v27[v12] );
      v25 = v27;
      v26 = (unsigned int)(v12 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v16, 2, (__int64)v24);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v16, (unsigned int)SessionFreeBuffers, sessionHandle, v20);
  if ( v21 )
    _InterlockedCompareExchange((volatile signed __int32 *)v21 + 43, 0, *((_DWORD *)v21 + 43));
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v23 = (const BYTE *)v10;
    v25 = (char *)&v23;
    v26 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)ProcessRPEnd, v16, 2, (__int64)v24);
  }
  if ( v22 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
  return SessionFreeBuffers;
}

```

## disassembly

```asm
0x180009e10  push    rbp
0x180009e12  push    rbx
0x180009e13  push    rsi
0x180009e14  push    rdi
0x180009e15  push    r12
0x180009e17  push    r13
0x180009e19  push    r14
0x180009e1b  push    r15
0x180009e1d  lea     rbp, [rsp-0F98h]
0x180009e25  mov     eax, 1098h
0x180009e2a  call    _alloca_probe
0x180009e2f  sub     rsp, rax
0x180009e32  mov     rax, cs:__security_cookie
0x180009e39  xor     rax, rsp
0x180009e3c  mov     [rbp+0FD0h+var_50], rax
0x180009e43  mov     r15, r9
0x180009e46  mov     [rsp+10D0h+var_1078], r8
0x180009e4b  mov     r12d, edx
0x180009e4e  mov     esi, ecx
0x180009e50  mov     r14, [rbp+0FD0h+ppEapError]
0x180009e57  mov     [rsp+10D0h+var_1090], 6
0x180009e5f  mov     [rsp+10D0h+var_1080], 0
0x180009e68  call    cs:__imp_GetCurrentThreadId
0x180009e6f  nop     dword ptr [rax+rax+00h]
0x180009e74  mov     ebx, eax
0x180009e76  shl     rbx, 20h
0x180009e7a  call    cs:__imp_GetTickCount
0x180009e81  nop     dword ptr [rax+rax+00h]
0x180009e86  mov     r13d, eax
0x180009e89  or      r13, rbx
0x180009e8c  xor     ebx, ebx
0x180009e8e  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x180009e94  jge     short loc_180009ECF
0x180009e96  mov     [rsp+10D0h+var_1088], r13
0x180009e9b  lea     rax, [rsp+10D0h+var_1088]
0x180009ea0  mov     [rsp+10D0h+var_1060], rax
0x180009ea5  mov     [rsp+10D0h+var_1058], 8
0x180009eae  lea     rax, [rsp+10D0h+var_1070]
0x180009eb3  mov     [rsp+10D0h+lpBuffer], rax
0x180009eb8  lea     r9d, [rbx+2]
0x180009ebc  lea     rdx, ProcessRPStart
0x180009ec3  lea     rcx, eaphost_Context
0x180009eca  call    McGenEventWrite_EtwEventWriteTransfer
0x180009ecf  lea     rdx, DebugInfoEvent
0x180009ed6  mov     rcx, cs:eaphost_Context
0x180009edd  call    cs:__imp_EtwEventEnabled
0x180009ee4  nop     dword ptr [rax+rax+00h]
0x180009ee9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180009eed  test    al, al
0x180009eef  jz      short loc_180009F5F
0x180009ef1  mov     dword ptr [rsp+10D0h+lpBuffer], r12d
0x180009ef6  mov     r9d, esi
0x180009ef9  lea     r8, aEaphostpeerpro_0; "EapHostPeerProcessReceivedPacket Entry:"...
0x180009f00  mov     edx, 800h; unsigned __int64
0x180009f05  lea     rcx, [rbp+0FD0h+var_1050]; char *
0x180009f09  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180009f0e  test    eax, eax
0x180009f10  js      short loc_180009F5F
0x180009f12  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x180009f18  jge     short loc_180009F5F
0x180009f1a  lea     rcx, [rbp+0FD0h+var_1050]
0x180009f1e  mov     rax, rdi
0x180009f21  inc     rax
0x180009f24  cmp     [rcx+rax], bl
0x180009f27  jnz     short loc_180009F21
0x180009f29  inc     eax
0x180009f2b  lea     rcx, [rbp+0FD0h+var_1050]
0x180009f2f  mov     [rsp+10D0h+var_1060], rcx
0x180009f34  mov     dword ptr [rsp+10D0h+var_1058], eax
0x180009f38  mov     dword ptr [rsp+10D0h+var_1058+4], ebx
0x180009f3c  lea     rax, [rsp+10D0h+var_1070]
0x180009f41  mov     [rsp+10D0h+lpBuffer], rax
0x180009f46  mov     r9d, 2
0x180009f4c  lea     rdx, DebugInfoEvent
0x180009f53  lea     rcx, eaphost_Context
0x180009f5a  call    McGenEventWrite_EtwEventWriteTransfer
0x180009f5f  lea     rax, WPP_GLOBAL_Control
0x180009f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f6d  cmp     rcx, rax
0x180009f70  jz      short loc_180009F8E
0x180009f72  test    byte ptr [rcx+1Ch], 4
0x180009f76  jz      short loc_180009F8E
0x180009f78  mov     edx, 1Eh
0x180009f7d  mov     dword ptr [rsp+10D0h+lpBuffer], r12d
0x180009f82  mov     r9d, esi
0x180009f85  mov     rcx, [rcx+10h]
0x180009f89  call    WPP_SF_Dd
0x180009f8e  mov     [rsp+10D0h+var_1088], rbx
0x180009f93  mov     dword ptr [rsp+10D0h+lpBuffer], 1
0x180009f9b  lea     r9, [rsp+10D0h+var_1080]
0x180009fa0  lea     r8, [rsp+10D0h+var_1088]
0x180009fa5  mov     edx, esi
0x180009fa7  call    ?FindSessionFreeBuffers@PeerProxy@Peer@EapHost@@QEAAKKAEAPEAVConnectionSessionInfo@23@AEAV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@H@Z; EapHost::Peer::PeerProxy::FindSessionFreeBuffers(ulong,EapHost::Peer::ConnectionSessionInfo * &,ATL::CComPtr<IEapHostPeerSessionApis> &,int)
0x180009fac  mov     ebx, eax
0x180009fae  test    eax, eax
0x180009fb0  jnz     short loc_18000A008
0x180009fb2  test    r15, r15
0x180009fb5  jnz     short loc_180009FBE
0x180009fb7  mov     ebx, 0A0h
0x180009fbc  jmp     short loc_18000A008
0x180009fbe  test    r14, r14
0x180009fc1  jz      short loc_180009FCA
0x180009fc3  mov     qword ptr [r14], 0
0x180009fca  mov     eax, [rsp+10D0h+var_1090]
0x180009fce  mov     [r15], eax
0x180009fd1  mov     rcx, [rsp+10D0h+var_1080]
0x180009fd6  mov     rax, [rcx]
0x180009fd9  mov     qword ptr [rsp+10D0h+nSize], r14
0x180009fde  lea     rdx, [rsp+10D0h+var_1090]
0x180009fe3  mov     [rsp+10D0h+lpBuffer], rdx
0x180009fe8  mov     r9, [rsp+10D0h+var_1078]
0x180009fed  mov     r8d, r12d
0x180009ff0  mov     edx, esi
0x180009ff2  mov     rax, [rax+20h]
0x180009ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ffb  mov     ebx, eax
0x180009ffd  test    eax, eax
0x180009fff  js      short loc_18000A008
0x18000a001  mov     eax, [rsp+10D0h+var_1090]
0x18000a005  mov     [r15], eax
0x18000a008  xor     r15d, r15d
0x18000a00b  mov     [rsp+10D0h+Arguments], r15; Arguments
0x18000a010  mov     [rsp+10D0h+nSize], 400h; nSize
0x18000a018  lea     rax, [rbp+0FD0h+Buffer]
0x18000a01f  mov     [rsp+10D0h+lpBuffer], rax; lpBuffer
0x18000a024  xor     r9d, r9d; dwLanguageId
0x18000a027  mov     r8d, ebx; dwMessageId
0x18000a02a  xor     edx, edx; lpSource
0x18000a02c  mov     ecx, 1200h; dwFlags
0x18000a031  call    cs:__imp_FormatMessageW
0x18000a038  nop     dword ptr [rax+rax+00h]
0x18000a03d  lea     rdx, DebugInfoEvent
0x18000a044  mov     rcx, cs:eaphost_Context
0x18000a04b  call    cs:__imp_EtwEventEnabled
0x18000a052  nop     dword ptr [rax+rax+00h]
0x18000a057  test    al, al
0x18000a059  jz      short loc_18000A0D5
0x18000a05b  mov     eax, [rsp+10D0h+var_1090]
0x18000a05f  mov     [rsp+10D0h+nSize], eax
0x18000a063  mov     dword ptr [rsp+10D0h+lpBuffer], esi
0x18000a067  lea     r9, [rbp+0FD0h+Buffer]
0x18000a06e  lea     r8, aEaphostpeerpro_1; "EapHostPeerProcessReceivedPacket Exit:"...
0x18000a075  mov     edx, 800h; unsigned __int64
0x18000a07a  lea     rcx, [rbp+0FD0h+var_1050]; char *
0x18000a07e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000a083  test    eax, eax
0x18000a085  js      short loc_18000A0D5
0x18000a087  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x18000a08e  jge     short loc_18000A0D5
0x18000a090  lea     rax, [rbp+0FD0h+var_1050]
0x18000a094  inc     rdi
0x18000a097  cmp     [rax+rdi], r15b
0x18000a09b  jnz     short loc_18000A094
0x18000a09d  lea     eax, [rdi+1]
0x18000a0a0  lea     rcx, [rbp+0FD0h+var_1050]
0x18000a0a4  mov     [rsp+10D0h+var_1060], rcx
0x18000a0a9  mov     dword ptr [rsp+10D0h+var_1058], eax
0x18000a0ad  mov     dword ptr [rsp+10D0h+var_1058+4], r15d
0x18000a0b2  lea     rax, [rsp+10D0h+var_1070]
0x18000a0b7  mov     [rsp+10D0h+lpBuffer], rax
0x18000a0bc  mov     r9d, 2
0x18000a0c2  lea     rdx, DebugInfoEvent
0x18000a0c9  lea     rcx, eaphost_Context
0x18000a0d0  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a0d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0dc  lea     rax, WPP_GLOBAL_Control
0x18000a0e3  cmp     rcx, rax
0x18000a0e6  jz      short loc_18000A10B
0x18000a0e8  test    byte ptr [rcx+1Ch], 4
0x18000a0ec  jz      short loc_18000A10B
0x18000a0ee  mov     edx, 1Fh
0x18000a0f3  mov     eax, [rsp+10D0h+var_1090]
0x18000a0f7  mov     [rsp+10D0h+nSize], eax
0x18000a0fb  mov     dword ptr [rsp+10D0h+lpBuffer], esi
0x18000a0ff  mov     r9d, ebx
0x18000a102  mov     rcx, [rcx+10h]
0x18000a106  call    WPP_SF_Ddd
0x18000a10b  mov     rdx, [rsp+10D0h+var_1088]
0x18000a110  test    rdx, rdx
0x18000a113  jz      short loc_18000A126
0x18000a115  mov     ecx, r15d
0x18000a118  mov     eax, [rdx+0ACh]
0x18000a11e  lock cmpxchg [rdx+0ACh], ecx
0x18000a126  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x18000a12d  jge     short loc_18000A16B
0x18000a12f  mov     [rsp+10D0h+var_1078], r13
0x18000a134  lea     rax, [rsp+10D0h+var_1078]
0x18000a139  mov     [rsp+10D0h+var_1060], rax
0x18000a13e  mov     [rsp+10D0h+var_1058], 8
0x18000a147  lea     rax, [rsp+10D0h+var_1070]
0x18000a14c  mov     [rsp+10D0h+lpBuffer], rax
0x18000a151  mov     r9d, 2
0x18000a157  lea     rdx, ProcessRPEnd
0x18000a15e  lea     rcx, eaphost_Context
0x18000a165  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a16a  nop
0x18000a16b  mov     rcx, [rsp+10D0h+var_1080]
0x18000a170  test    rcx, rcx
0x18000a173  jz      short loc_18000A182
0x18000a175  mov     rax, [rcx]
0x18000a178  mov     rax, [rax+10h]
0x18000a17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a181  nop
0x18000a182  mov     eax, ebx
0x18000a184  mov     rcx, [rbp+0FD0h+var_50]
0x18000a18b  xor     rcx, rsp; StackCookie
0x18000a18e  call    __security_check_cookie
0x18000a193  add     rsp, 1098h
0x18000a19a  pop     r15
0x18000a19c  pop     r14
0x18000a19e  pop     r13
0x18000a1a0  pop     r12
0x18000a1a2  pop     rdi
0x18000a1a3  pop     rsi
0x18000a1a4  pop     rbx
0x18000a1a5  pop     rbp
0x18000a1a6  retn
```

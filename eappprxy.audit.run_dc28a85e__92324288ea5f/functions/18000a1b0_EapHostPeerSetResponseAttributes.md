# EapHostPeerSetResponseAttributes

- ea: `0x18000a1b0`
- end: `0x18000a548`
- name: `EapHostPeerSetResponseAttributes`
- size: `920`
- prototype: `DWORD __stdcall(EAP_SESSIONID sessionHandle, const EapAttributes *const pAttribs, EapHostPeerResponseAction *pEapOutput, EAP_ERROR **ppEapError)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x180005450`
- `0x18000a1b0`
- `0x18000ace0`
- `0x18000aeb8`
- `0x18000af14`
- `0x18000bef4`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000a274`
- `ntdll!EtwEventEnabled` at `0x18000a3ea`
- `ntdll!EtwEventEnabled` at `0x18000a274`
- `ntdll!EtwEventEnabled` at `0x18000a3ea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a3d0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a3d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a1ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a1ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a211`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a211`

## pseudocode

```c
DWORD __stdcall EapHostPeerSetResponseAttributes(
        EAP_SESSIONID sessionHandle,
        const EapAttributes *const pAttribs,
        EapHostPeerResponseAction *pEapOutput,
        EAP_ERROR **ppEapError)
{
  unsigned __int64 v8; // rbx
  __int64 v9; // r8
  EapHost::Peer::ConnectionSessionInfo *v10; // r13
  __int64 v11; // r8
  __int64 v12; // r14
  DWORD dwNumberOfAttributes; // eax
  __int64 v14; // rax
  void *v15; // rcx
  DWORD v16; // eax
  signed int SessionFreeBuffers; // ebx
  __int64 v18; // r8
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h]
  __int64 nSize; // [rsp+28h] [rbp-D8h]
  EapHostPeerResponseAction v22; // [rsp+40h] [rbp-C0h] BYREF
  EapHost::Peer::ConnectionSessionInfo *v23; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v24; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[16]; // [rsp+58h] [rbp-A8h] BYREF
  char *v26; // [rsp+68h] [rbp-98h]
  __int64 v27; // [rsp+70h] [rbp-90h]
  char v28[2048]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[1024]; // [rsp+880h] [rbp+780h] BYREF

  v22 = EapHostPeerResponseNone;
  v24 = 0;
  v8 = (unsigned __int64)GetCurrentThreadId() << 32;
  v10 = (EapHost::Peer::ConnectionSessionInfo *)(v8 | GetTickCount());
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v23 = v10;
    v26 = (char *)&v23;
    v27 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)SetRespAttribStart, v9, 2, (__int64)v25);
  }
  v12 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    dwNumberOfAttributes = 0;
    if ( pAttribs )
      dwNumberOfAttributes = pAttribs->dwNumberOfAttributes;
    if ( (int)StringCchPrintfA(
                v28,
                0x800u,
                "EapHostPeerSetResponseAttributes Entry:\n Session(%d), # of attributes(%d)",
                sessionHandle,
                dwNumberOfAttributes) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v14 = -1;
      do
        ++v14;
      while ( v28[v14] );
      v26 = v28;
      v27 = (unsigned int)(v14 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v11, 2, (__int64)v25);
    }
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v16 = 0;
    if ( pAttribs )
      v16 = pAttribs->dwNumberOfAttributes;
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v11, sessionHandle, v16);
  }
  v23 = 0;
  if ( !sessionHandle )
    goto LABEL_17;
  SessionFreeBuffers = EapHost::Peer::PeerProxy::FindSessionFreeBuffers((__int64)v15, sessionHandle, &v23, &v24, 0);
  if ( SessionFreeBuffers )
    goto LABEL_24;
  if ( pEapOutput )
  {
    if ( ppEapError )
      *ppEapError = 0;
    *pEapOutput = v22;
    SessionFreeBuffers = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const EapAttributes *const, EapHostPeerResponseAction *, EAP_ERROR **))(*(_QWORD *)v24 + 80LL))(
                           v24,
                           sessionHandle,
                           pAttribs,
                           &v22,
                           ppEapError);
    if ( SessionFreeBuffers >= 0 )
      *pEapOutput = v22;
  }
  else
  {
LABEL_17:
    SessionFreeBuffers = 160;
  }
LABEL_24:
  FormatMessageW(0x1200u, 0, SessionFreeBuffers, 0, Buffer, 0x400u, 0);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    LODWORD(nSize) = v22;
    LODWORD(lpBuffer) = sessionHandle;
    if ( (int)StringCchPrintfA(
                v28,
                0x800u,
                "EapHostPeerSetResponseAttributes Exit:\n %ws\nReturned session(%d), action(%d).",
                Buffer,
                lpBuffer,
                nSize) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v12;
      while ( v28[v12] );
      v26 = v28;
      v27 = (unsigned int)(v12 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v18, 2, (__int64)v25);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v18, (unsigned int)SessionFreeBuffers, sessionHandle, v22);
  if ( v23 )
    _InterlockedCompareExchange((volatile signed __int32 *)v23 + 43, 0, *((_DWORD *)v23 + 43));
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v23 = v10;
    v26 = (char *)&v23;
    v27 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)GetRespAttribEnd, v18, 2, (__int64)v25);
  }
  if ( v24 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
  return SessionFreeBuffers;
}

```

## disassembly

```asm
0x18000a1b0  push    rbp
0x18000a1b2  push    rbx
0x18000a1b3  push    rsi
0x18000a1b4  push    rdi
0x18000a1b5  push    r12
0x18000a1b7  push    r13
0x18000a1b9  push    r14
0x18000a1bb  push    r15
0x18000a1bd  lea     rbp, [rsp-0F98h]
0x18000a1c5  mov     eax, 1098h
0x18000a1ca  call    _alloca_probe
0x18000a1cf  sub     rsp, rax
0x18000a1d2  mov     rax, cs:__security_cookie
0x18000a1d9  xor     rax, rsp
0x18000a1dc  mov     [rbp+0FD0h+var_50], rax
0x18000a1e3  mov     r15, r9
0x18000a1e6  mov     r12, r8
0x18000a1e9  mov     rdi, rdx
0x18000a1ec  mov     esi, ecx
0x18000a1ee  mov     [rsp+10D0h+var_1090], 6
0x18000a1f6  mov     [rsp+10D0h+var_1080], 0
0x18000a1ff  call    cs:__imp_GetCurrentThreadId
0x18000a206  nop     dword ptr [rax+rax+00h]
0x18000a20b  mov     ebx, eax
0x18000a20d  shl     rbx, 20h
0x18000a211  call    cs:__imp_GetTickCount
0x18000a218  nop     dword ptr [rax+rax+00h]
0x18000a21d  mov     r13d, eax
0x18000a220  or      r13, rbx
0x18000a223  xor     ebx, ebx
0x18000a225  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x18000a22b  jge     short loc_18000A266
0x18000a22d  mov     [rsp+10D0h+var_1088], r13
0x18000a232  lea     rax, [rsp+10D0h+var_1088]
0x18000a237  mov     [rsp+10D0h+var_1068], rax
0x18000a23c  mov     [rsp+10D0h+var_1060], 8
0x18000a245  lea     rax, [rsp+10D0h+var_1078]
0x18000a24a  mov     [rsp+10D0h+lpBuffer], rax
0x18000a24f  lea     r9d, [rbx+2]
0x18000a253  lea     rdx, SetRespAttribStart
0x18000a25a  lea     rcx, eaphost_Context
0x18000a261  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a266  lea     rdx, DebugInfoEvent
0x18000a26d  mov     rcx, cs:eaphost_Context
0x18000a274  call    cs:__imp_EtwEventEnabled
0x18000a27b  nop     dword ptr [rax+rax+00h]
0x18000a280  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000a284  test    al, al
0x18000a286  jz      short loc_18000A2FE
0x18000a288  test    rdi, rdi
0x18000a28b  mov     eax, ebx
0x18000a28d  jz      short loc_18000A291
0x18000a28f  mov     eax, [rdi]
0x18000a291  mov     dword ptr [rsp+10D0h+lpBuffer], eax
0x18000a295  mov     r9d, esi
0x18000a298  lea     r8, aEaphostpeerset_1; "EapHostPeerSetResponseAttributes Entry:"...
0x18000a29f  mov     edx, 800h; unsigned __int64
0x18000a2a4  lea     rcx, [rbp+0FD0h+var_1050]; char *
0x18000a2a8  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000a2ad  test    eax, eax
0x18000a2af  js      short loc_18000A2FE
0x18000a2b1  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x18000a2b7  jge     short loc_18000A2FE
0x18000a2b9  lea     rcx, [rbp+0FD0h+var_1050]
0x18000a2bd  mov     rax, r14
0x18000a2c0  inc     rax
0x18000a2c3  cmp     [rcx+rax], bl
0x18000a2c6  jnz     short loc_18000A2C0
0x18000a2c8  inc     eax
0x18000a2ca  lea     rcx, [rbp+0FD0h+var_1050]
0x18000a2ce  mov     [rsp+10D0h+var_1068], rcx
0x18000a2d3  mov     dword ptr [rsp+10D0h+var_1060], eax
0x18000a2d7  mov     dword ptr [rsp+10D0h+var_1060+4], ebx
0x18000a2db  lea     rax, [rsp+10D0h+var_1078]
0x18000a2e0  mov     [rsp+10D0h+lpBuffer], rax
0x18000a2e5  mov     r9d, 2
0x18000a2eb  lea     rdx, DebugInfoEvent
0x18000a2f2  lea     rcx, eaphost_Context
0x18000a2f9  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a2fe  lea     rax, WPP_GLOBAL_Control
0x18000a305  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a30c  cmp     rcx, rax
0x18000a30f  jz      short loc_18000A335
0x18000a311  test    byte ptr [rcx+1Ch], 4
0x18000a315  jz      short loc_18000A335
0x18000a317  test    rdi, rdi
0x18000a31a  mov     eax, ebx
0x18000a31c  jz      short loc_18000A320
0x18000a31e  mov     eax, [rdi]
0x18000a320  mov     edx, 2Ah ; '*'
0x18000a325  mov     dword ptr [rsp+10D0h+lpBuffer], eax
0x18000a329  mov     r9d, esi
0x18000a32c  mov     rcx, [rcx+10h]
0x18000a330  call    WPP_SF_Dd
0x18000a335  mov     [rsp+10D0h+var_1088], rbx
0x18000a33a  test    esi, esi
0x18000a33c  jnz     short loc_18000A345
0x18000a33e  mov     ebx, 0A0h
0x18000a343  jmp     short loc_18000A3A7
0x18000a345  mov     dword ptr [rsp+10D0h+lpBuffer], ebx
0x18000a349  lea     r9, [rsp+10D0h+var_1080]
0x18000a34e  lea     r8, [rsp+10D0h+var_1088]
0x18000a353  mov     edx, esi
0x18000a355  call    ?FindSessionFreeBuffers@PeerProxy@Peer@EapHost@@QEAAKKAEAPEAVConnectionSessionInfo@23@AEAV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@H@Z; EapHost::Peer::PeerProxy::FindSessionFreeBuffers(ulong,EapHost::Peer::ConnectionSessionInfo * &,ATL::CComPtr<IEapHostPeerSessionApis> &,int)
0x18000a35a  mov     ebx, eax
0x18000a35c  test    eax, eax
0x18000a35e  jnz     short loc_18000A3A7
0x18000a360  test    r12, r12
0x18000a363  jz      short loc_18000A33E
0x18000a365  test    r15, r15
0x18000a368  jz      short loc_18000A371
0x18000a36a  mov     qword ptr [r15], 0
0x18000a371  mov     eax, [rsp+10D0h+var_1090]
0x18000a375  mov     [r12], eax
0x18000a379  mov     rcx, [rsp+10D0h+var_1080]
0x18000a37e  mov     rax, [rcx]
0x18000a381  mov     [rsp+10D0h+lpBuffer], r15
0x18000a386  lea     r9, [rsp+10D0h+var_1090]
0x18000a38b  mov     r8, rdi
0x18000a38e  mov     edx, esi
0x18000a390  mov     rax, [rax+50h]
0x18000a394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a399  mov     ebx, eax
0x18000a39b  test    eax, eax
0x18000a39d  js      short loc_18000A3A7
0x18000a39f  mov     eax, [rsp+10D0h+var_1090]
0x18000a3a3  mov     [r12], eax
0x18000a3a7  xor     r12d, r12d
0x18000a3aa  mov     [rsp+10D0h+Arguments], r12; Arguments
0x18000a3af  mov     dword ptr [rsp+10D0h+nSize], 400h; nSize
0x18000a3b7  lea     rax, [rbp+0FD0h+Buffer]
0x18000a3be  mov     [rsp+10D0h+lpBuffer], rax; lpBuffer
0x18000a3c3  xor     r9d, r9d; dwLanguageId
0x18000a3c6  mov     r8d, ebx; dwMessageId
0x18000a3c9  xor     edx, edx; lpSource
0x18000a3cb  mov     ecx, 1200h; dwFlags
0x18000a3d0  call    cs:__imp_FormatMessageW
0x18000a3d7  nop     dword ptr [rax+rax+00h]
0x18000a3dc  lea     rdx, DebugInfoEvent
0x18000a3e3  mov     rcx, cs:eaphost_Context
0x18000a3ea  call    cs:__imp_EtwEventEnabled
0x18000a3f1  nop     dword ptr [rax+rax+00h]
0x18000a3f6  test    al, al
0x18000a3f8  jz      short loc_18000A475
0x18000a3fa  mov     eax, [rsp+10D0h+var_1090]
0x18000a3fe  mov     dword ptr [rsp+10D0h+nSize], eax
0x18000a402  mov     dword ptr [rsp+10D0h+lpBuffer], esi
0x18000a406  lea     r9, [rbp+0FD0h+Buffer]
0x18000a40d  lea     r8, aEaphostpeerset_4; "EapHostPeerSetResponseAttributes Exit:"...
0x18000a414  mov     edx, 800h; unsigned __int64
0x18000a419  lea     rcx, [rbp+0FD0h+var_1050]; char *
0x18000a41d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000a422  test    eax, eax
0x18000a424  js      short loc_18000A475
0x18000a426  cmp     cs:Microsoft_Windows_EapHostEnableBits, r12b
0x18000a42d  jge     short loc_18000A475
0x18000a42f  lea     rax, [rbp+0FD0h+var_1050]
0x18000a433  inc     r14
0x18000a436  cmp     [rax+r14], r12b
0x18000a43a  jnz     short loc_18000A433
0x18000a43c  lea     eax, [r14+1]
0x18000a440  lea     rcx, [rbp+0FD0h+var_1050]
0x18000a444  mov     [rsp+10D0h+var_1068], rcx
0x18000a449  mov     dword ptr [rsp+10D0h+var_1060], eax
0x18000a44d  mov     dword ptr [rsp+10D0h+var_1060+4], r12d
0x18000a452  lea     rax, [rsp+10D0h+var_1078]
0x18000a457  mov     [rsp+10D0h+lpBuffer], rax
0x18000a45c  mov     r9d, 2
0x18000a462  lea     rdx, DebugInfoEvent
0x18000a469  lea     rcx, eaphost_Context
0x18000a470  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a475  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a47c  lea     rax, WPP_GLOBAL_Control
0x18000a483  cmp     rcx, rax
0x18000a486  jz      short loc_18000A4AB
0x18000a488  test    byte ptr [rcx+1Ch], 4
0x18000a48c  jz      short loc_18000A4AB
0x18000a48e  mov     edx, 2Bh ; '+'
0x18000a493  mov     eax, [rsp+10D0h+var_1090]
0x18000a497  mov     dword ptr [rsp+10D0h+nSize], eax
0x18000a49b  mov     dword ptr [rsp+10D0h+lpBuffer], esi
0x18000a49f  mov     r9d, ebx
0x18000a4a2  mov     rcx, [rcx+10h]
0x18000a4a6  call    WPP_SF_Ddd
0x18000a4ab  mov     rdx, [rsp+10D0h+var_1088]
0x18000a4b0  test    rdx, rdx
0x18000a4b3  jz      short loc_18000A4C6
0x18000a4b5  mov     ecx, r12d
0x18000a4b8  mov     eax, [rdx+0ACh]
0x18000a4be  lock cmpxchg [rdx+0ACh], ecx
0x18000a4c6  cmp     cs:Microsoft_Windows_EapHostEnableBits, r12b
0x18000a4cd  jge     short loc_18000A50B
0x18000a4cf  mov     [rsp+10D0h+var_1088], r13
0x18000a4d4  lea     rax, [rsp+10D0h+var_1088]
0x18000a4d9  mov     [rsp+10D0h+var_1068], rax
0x18000a4de  mov     [rsp+10D0h+var_1060], 8
0x18000a4e7  lea     rax, [rsp+10D0h+var_1078]
0x18000a4ec  mov     [rsp+10D0h+lpBuffer], rax
0x18000a4f1  mov     r9d, 2
0x18000a4f7  lea     rdx, GetRespAttribEnd
0x18000a4fe  lea     rcx, eaphost_Context
0x18000a505  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a50a  nop
0x18000a50b  mov     rcx, [rsp+10D0h+var_1080]
0x18000a510  test    rcx, rcx
0x18000a513  jz      short loc_18000A522
0x18000a515  mov     rax, [rcx]
0x18000a518  mov     rax, [rax+10h]
0x18000a51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a521  nop
0x18000a522  mov     eax, ebx
0x18000a524  mov     rcx, [rbp+0FD0h+var_50]
0x18000a52b  xor     rcx, rsp; StackCookie
0x18000a52e  call    __security_check_cookie
0x18000a533  add     rsp, 1098h
0x18000a53a  pop     r15
0x18000a53c  pop     r14
0x18000a53e  pop     r13
0x18000a540  pop     r12
0x18000a542  pop     rdi
0x18000a543  pop     rsi
0x18000a544  pop     rbx
0x18000a545  pop     rbp
0x18000a546  retn
```

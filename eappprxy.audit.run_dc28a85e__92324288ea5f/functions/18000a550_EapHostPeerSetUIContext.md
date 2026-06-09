# EapHostPeerSetUIContext

- ea: `0x18000a550`
- end: `0x18000a8e8`
- name: `EapHostPeerSetUIContext`
- size: `920`
- prototype: `DWORD __stdcall(EAP_SESSIONID sessionHandle, DWORD dwSizeOfUIContextData, const BYTE *const pUIContextData, EapHostPeerResponseAction *pEapOutput, EAP_ERROR **ppEapError)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x180005450`
- `0x18000a550`
- `0x18000ace0`
- `0x18000aeb8`
- `0x18000af14`
- `0x18000bef4`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000a61d`
- `ntdll!EtwEventEnabled` at `0x18000a78b`
- `ntdll!EtwEventEnabled` at `0x18000a61d`
- `ntdll!EtwEventEnabled` at `0x18000a78b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a771`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a771`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a5ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a5ba`

## pseudocode

```c
DWORD __stdcall EapHostPeerSetUIContext(
        EAP_SESSIONID sessionHandle,
        DWORD dwSizeOfUIContextData,
        const BYTE *const pUIContextData,
        EapHostPeerResponseAction *pEapOutput,
        EAP_ERROR **ppEapError)
{
  unsigned __int64 v8; // rbx
  __int64 v9; // r8
  EapHost::Peer::ConnectionSessionInfo *v10; // r13
  __int64 v11; // r8
  __int64 v12; // rsi
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

  v23 = pUIContextData;
  v20 = EapHostPeerResponseNone;
  v22 = 0;
  v8 = (unsigned __int64)GetCurrentThreadId() << 32;
  v10 = (EapHost::Peer::ConnectionSessionInfo *)(v8 | GetTickCount());
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v21 = v10;
    v25 = (char *)&v21;
    v26 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)SetUIContextStart, v9, 2, (__int64)v24);
  }
  v12 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v27,
              0x800u,
              "EapHostPeerSetUIContext Entry:\n Session(%d), UI context data(%d) bytes",
              sessionHandle,
              dwSizeOfUIContextData) >= 0
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
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v11, sessionHandle, dwSizeOfUIContextData);
  v21 = 0;
  if ( !sessionHandle )
    goto LABEL_13;
  SessionFreeBuffers = EapHost::Peer::PeerProxy::FindSessionFreeBuffers((__int64)v14, sessionHandle, &v21, &v22, 0);
  if ( SessionFreeBuffers )
    goto LABEL_20;
  if ( pEapOutput )
  {
    if ( ppEapError )
      *ppEapError = 0;
    *pEapOutput = v20;
    SessionFreeBuffers = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, const BYTE *, EapHostPeerResponseAction *, EAP_ERROR **))(*(_QWORD *)v22 + 64LL))(
                           v22,
                           sessionHandle,
                           dwSizeOfUIContextData,
                           v23,
                           &v20,
                           ppEapError);
    if ( SessionFreeBuffers >= 0 )
      *pEapOutput = v20;
  }
  else
  {
LABEL_13:
    SessionFreeBuffers = 160;
  }
LABEL_20:
  FormatMessageW(0x1200u, 0, SessionFreeBuffers, 0, Buffer, 0x400u, 0);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    nSize[0] = v20;
    LODWORD(lpBuffer) = sessionHandle;
    if ( (int)StringCchPrintfA(
                v27,
                0x800u,
                "EapHostPeerSetUIContext Exit:\n %ws\n Returned session(%d), action(%d).",
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
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, v16, (unsigned int)SessionFreeBuffers, sessionHandle, v20);
  if ( v21 )
    _InterlockedCompareExchange((volatile signed __int32 *)v21 + 43, 0, *((_DWORD *)v21 + 43));
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v23 = (const BYTE *)v10;
    v25 = (char *)&v23;
    v26 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)SetUIContextEnd, v16, 2, (__int64)v24);
  }
  if ( v22 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
  return SessionFreeBuffers;
}

```

## disassembly

```asm
0x18000a550  push    rbp
0x18000a552  push    rbx
0x18000a553  push    rsi
0x18000a554  push    rdi
0x18000a555  push    r12
0x18000a557  push    r13
0x18000a559  push    r14
0x18000a55b  push    r15
0x18000a55d  lea     rbp, [rsp-0F98h]
0x18000a565  mov     eax, 1098h
0x18000a56a  call    _alloca_probe
0x18000a56f  sub     rsp, rax
0x18000a572  mov     rax, cs:__security_cookie
0x18000a579  xor     rax, rsp
0x18000a57c  mov     [rbp+0FD0h+var_50], rax
0x18000a583  mov     r15, r9
0x18000a586  mov     [rsp+10D0h+var_1078], r8
0x18000a58b  mov     r12d, edx
0x18000a58e  mov     edi, ecx
0x18000a590  mov     r14, [rbp+0FD0h+ppEapError]
0x18000a597  mov     [rsp+10D0h+var_1090], 6
0x18000a59f  mov     [rsp+10D0h+var_1080], 0
0x18000a5a8  call    cs:__imp_GetCurrentThreadId
0x18000a5af  nop     dword ptr [rax+rax+00h]
0x18000a5b4  mov     ebx, eax
0x18000a5b6  shl     rbx, 20h
0x18000a5ba  call    cs:__imp_GetTickCount
0x18000a5c1  nop     dword ptr [rax+rax+00h]
0x18000a5c6  mov     r13d, eax
0x18000a5c9  or      r13, rbx
0x18000a5cc  xor     ebx, ebx
0x18000a5ce  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x18000a5d4  jge     short loc_18000A60F
0x18000a5d6  mov     [rsp+10D0h+var_1088], r13
0x18000a5db  lea     rax, [rsp+10D0h+var_1088]
0x18000a5e0  mov     [rsp+10D0h+var_1060], rax
0x18000a5e5  mov     [rsp+10D0h+var_1058], 8
0x18000a5ee  lea     rax, [rsp+10D0h+var_1070]
0x18000a5f3  mov     [rsp+10D0h+lpBuffer], rax
0x18000a5f8  lea     r9d, [rbx+2]
0x18000a5fc  lea     rdx, SetUIContextStart
0x18000a603  lea     rcx, eaphost_Context
0x18000a60a  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a60f  lea     rdx, DebugInfoEvent
0x18000a616  mov     rcx, cs:eaphost_Context
0x18000a61d  call    cs:__imp_EtwEventEnabled
0x18000a624  nop     dword ptr [rax+rax+00h]
0x18000a629  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a62d  test    al, al
0x18000a62f  jz      short loc_18000A69F
0x18000a631  mov     dword ptr [rsp+10D0h+lpBuffer], r12d
0x18000a636  mov     r9d, edi
0x18000a639  lea     r8, aEaphostpeerset_3; "EapHostPeerSetUIContext Entry:\n Sessio"...
0x18000a640  mov     edx, 800h; unsigned __int64
0x18000a645  lea     rcx, [rbp+0FD0h+var_1050]; char *
0x18000a649  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000a64e  test    eax, eax
0x18000a650  js      short loc_18000A69F
0x18000a652  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x18000a658  jge     short loc_18000A69F
0x18000a65a  lea     rcx, [rbp+0FD0h+var_1050]
0x18000a65e  mov     rax, rsi
0x18000a661  inc     rax
0x18000a664  cmp     [rcx+rax], bl
0x18000a667  jnz     short loc_18000A661
0x18000a669  inc     eax
0x18000a66b  lea     rcx, [rbp+0FD0h+var_1050]
0x18000a66f  mov     [rsp+10D0h+var_1060], rcx
0x18000a674  mov     dword ptr [rsp+10D0h+var_1058], eax
0x18000a678  mov     dword ptr [rsp+10D0h+var_1058+4], ebx
0x18000a67c  lea     rax, [rsp+10D0h+var_1070]
0x18000a681  mov     [rsp+10D0h+lpBuffer], rax
0x18000a686  mov     r9d, 2
0x18000a68c  lea     rdx, DebugInfoEvent
0x18000a693  lea     rcx, eaphost_Context
0x18000a69a  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a69f  lea     rax, WPP_GLOBAL_Control
0x18000a6a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6ad  cmp     rcx, rax
0x18000a6b0  jz      short loc_18000A6CE
0x18000a6b2  test    byte ptr [rcx+1Ch], 4
0x18000a6b6  jz      short loc_18000A6CE
0x18000a6b8  mov     edx, 26h ; '&'
0x18000a6bd  mov     dword ptr [rsp+10D0h+lpBuffer], r12d
0x18000a6c2  mov     r9d, edi
0x18000a6c5  mov     rcx, [rcx+10h]
0x18000a6c9  call    WPP_SF_Dd
0x18000a6ce  mov     [rsp+10D0h+var_1088], rbx
0x18000a6d3  test    edi, edi
0x18000a6d5  jnz     short loc_18000A6DE
0x18000a6d7  mov     ebx, 0A0h
0x18000a6dc  jmp     short loc_18000A748
0x18000a6de  mov     dword ptr [rsp+10D0h+lpBuffer], ebx
0x18000a6e2  lea     r9, [rsp+10D0h+var_1080]
0x18000a6e7  lea     r8, [rsp+10D0h+var_1088]
0x18000a6ec  mov     edx, edi
0x18000a6ee  call    ?FindSessionFreeBuffers@PeerProxy@Peer@EapHost@@QEAAKKAEAPEAVConnectionSessionInfo@23@AEAV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@H@Z; EapHost::Peer::PeerProxy::FindSessionFreeBuffers(ulong,EapHost::Peer::ConnectionSessionInfo * &,ATL::CComPtr<IEapHostPeerSessionApis> &,int)
0x18000a6f3  mov     ebx, eax
0x18000a6f5  test    eax, eax
0x18000a6f7  jnz     short loc_18000A748
0x18000a6f9  test    r15, r15
0x18000a6fc  jz      short loc_18000A6D7
0x18000a6fe  test    r14, r14
0x18000a701  jz      short loc_18000A70A
0x18000a703  mov     qword ptr [r14], 0
0x18000a70a  mov     eax, [rsp+10D0h+var_1090]
0x18000a70e  mov     [r15], eax
0x18000a711  mov     rcx, [rsp+10D0h+var_1080]
0x18000a716  mov     rax, [rcx]
0x18000a719  mov     qword ptr [rsp+10D0h+nSize], r14
0x18000a71e  lea     rdx, [rsp+10D0h+var_1090]
0x18000a723  mov     [rsp+10D0h+lpBuffer], rdx
0x18000a728  mov     r9, [rsp+10D0h+var_1078]
0x18000a72d  mov     r8d, r12d
0x18000a730  mov     edx, edi
0x18000a732  mov     rax, [rax+40h]
0x18000a736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a73b  mov     ebx, eax
0x18000a73d  test    eax, eax
0x18000a73f  js      short loc_18000A748
0x18000a741  mov     eax, [rsp+10D0h+var_1090]
0x18000a745  mov     [r15], eax
0x18000a748  xor     r15d, r15d
0x18000a74b  mov     [rsp+10D0h+Arguments], r15; Arguments
0x18000a750  mov     [rsp+10D0h+nSize], 400h; nSize
0x18000a758  lea     rax, [rbp+0FD0h+Buffer]
0x18000a75f  mov     [rsp+10D0h+lpBuffer], rax; lpBuffer
0x18000a764  xor     r9d, r9d; dwLanguageId
0x18000a767  mov     r8d, ebx; dwMessageId
0x18000a76a  xor     edx, edx; lpSource
0x18000a76c  mov     ecx, 1200h; dwFlags
0x18000a771  call    cs:__imp_FormatMessageW
0x18000a778  nop     dword ptr [rax+rax+00h]
0x18000a77d  lea     rdx, DebugInfoEvent
0x18000a784  mov     rcx, cs:eaphost_Context
0x18000a78b  call    cs:__imp_EtwEventEnabled
0x18000a792  nop     dword ptr [rax+rax+00h]
0x18000a797  test    al, al
0x18000a799  jz      short loc_18000A815
0x18000a79b  mov     eax, [rsp+10D0h+var_1090]
0x18000a79f  mov     [rsp+10D0h+nSize], eax
0x18000a7a3  mov     dword ptr [rsp+10D0h+lpBuffer], edi
0x18000a7a7  lea     r9, [rbp+0FD0h+Buffer]
0x18000a7ae  lea     r8, aEaphostpeerset_2; "EapHostPeerSetUIContext Exit:\n %ws\n R"...
0x18000a7b5  mov     edx, 800h; unsigned __int64
0x18000a7ba  lea     rcx, [rbp+0FD0h+var_1050]; char *
0x18000a7be  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000a7c3  test    eax, eax
0x18000a7c5  js      short loc_18000A815
0x18000a7c7  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x18000a7ce  jge     short loc_18000A815
0x18000a7d0  lea     rax, [rbp+0FD0h+var_1050]
0x18000a7d4  inc     rsi
0x18000a7d7  cmp     [rax+rsi], r15b
0x18000a7db  jnz     short loc_18000A7D4
0x18000a7dd  lea     eax, [rsi+1]
0x18000a7e0  lea     rcx, [rbp+0FD0h+var_1050]
0x18000a7e4  mov     [rsp+10D0h+var_1060], rcx
0x18000a7e9  mov     dword ptr [rsp+10D0h+var_1058], eax
0x18000a7ed  mov     dword ptr [rsp+10D0h+var_1058+4], r15d
0x18000a7f2  lea     rax, [rsp+10D0h+var_1070]
0x18000a7f7  mov     [rsp+10D0h+lpBuffer], rax
0x18000a7fc  mov     r9d, 2
0x18000a802  lea     rdx, DebugInfoEvent
0x18000a809  lea     rcx, eaphost_Context
0x18000a810  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a815  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a81c  lea     rax, WPP_GLOBAL_Control
0x18000a823  cmp     rcx, rax
0x18000a826  jz      short loc_18000A84B
0x18000a828  test    byte ptr [rcx+1Ch], 4
0x18000a82c  jz      short loc_18000A84B
0x18000a82e  mov     edx, 27h ; '''
0x18000a833  mov     eax, [rsp+10D0h+var_1090]
0x18000a837  mov     [rsp+10D0h+nSize], eax
0x18000a83b  mov     dword ptr [rsp+10D0h+lpBuffer], edi
0x18000a83f  mov     r9d, ebx
0x18000a842  mov     rcx, [rcx+10h]
0x18000a846  call    WPP_SF_Ddd
0x18000a84b  mov     rdx, [rsp+10D0h+var_1088]
0x18000a850  test    rdx, rdx
0x18000a853  jz      short loc_18000A866
0x18000a855  mov     ecx, r15d
0x18000a858  mov     eax, [rdx+0ACh]
0x18000a85e  lock cmpxchg [rdx+0ACh], ecx
0x18000a866  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x18000a86d  jge     short loc_18000A8AB
0x18000a86f  mov     [rsp+10D0h+var_1078], r13
0x18000a874  lea     rax, [rsp+10D0h+var_1078]
0x18000a879  mov     [rsp+10D0h+var_1060], rax
0x18000a87e  mov     [rsp+10D0h+var_1058], 8
0x18000a887  lea     rax, [rsp+10D0h+var_1070]
0x18000a88c  mov     [rsp+10D0h+lpBuffer], rax
0x18000a891  mov     r9d, 2
0x18000a897  lea     rdx, SetUIContextEnd
0x18000a89e  lea     rcx, eaphost_Context
0x18000a8a5  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a8aa  nop
0x18000a8ab  mov     rcx, [rsp+10D0h+var_1080]
0x18000a8b0  test    rcx, rcx
0x18000a8b3  jz      short loc_18000A8C2
0x18000a8b5  mov     rax, [rcx]
0x18000a8b8  mov     rax, [rax+10h]
0x18000a8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8c1  nop
0x18000a8c2  mov     eax, ebx
0x18000a8c4  mov     rcx, [rbp+0FD0h+var_50]
0x18000a8cb  xor     rcx, rsp; StackCookie
0x18000a8ce  call    __security_check_cookie
0x18000a8d3  add     rsp, 1098h
0x18000a8da  pop     r15
0x18000a8dc  pop     r14
0x18000a8de  pop     r13
0x18000a8e0  pop     r12
0x18000a8e2  pop     rdi
0x18000a8e3  pop     rsi
0x18000a8e4  pop     rbx
0x18000a8e5  pop     rbp
0x18000a8e6  retn
```

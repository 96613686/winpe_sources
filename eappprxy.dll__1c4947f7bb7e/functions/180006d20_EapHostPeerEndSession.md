# EapHostPeerEndSession

- ea: `0x180006d20`
- end: `0x180007083`
- name: `EapHostPeerEndSession`
- size: `867`
- prototype: `DWORD __stdcall(EAP_SESSIONID sessionHandle, EAP_ERROR **ppEapError)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x180005450`
- `0x180006d20`
- `0x18000ace0`
- `0x18000ade4`
- `0x18000aeb8`
- `0x18000bef4`
- `0x18000c7d0`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180006ddb`
- `ntdll!EtwEventEnabled` at `0x180006f2b`
- `ntdll!EtwEventEnabled` at `0x180006ddb`
- `ntdll!EtwEventEnabled` at `0x180006f2b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006f11`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006f11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d65`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006d77`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006d77`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __stdcall EapHostPeerEndSession(EAP_SESSIONID sessionHandle, EAP_ERROR **ppEapError)
{
  int v4; // r13d
  unsigned __int64 v5; // rbx
  __int64 v6; // r8
  EapHost::Peer::ConnectionSessionInfo *v7; // r12
  __int64 v8; // r14
  __int64 v9; // r8
  __int64 v10; // rax
  void *v11; // rcx
  EapHost::Peer::ConnectionSessionInfo *v12; // rbx
  DWORD SessionFreeBuffers; // edi
  EapHost::Peer::PeerProxy *v14; // rcx
  __int64 v15; // r8
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h]
  EapHost::Peer::ConnectionSessionInfo *v18; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v19; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[16]; // [rsp+50h] [rbp-B0h] BYREF
  char *v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+68h] [rbp-98h]
  char v23[2048]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[1024]; // [rsp+870h] [rbp+770h] BYREF

  v4 = 0;
  v19 = 0;
  v5 = (unsigned __int64)GetCurrentThreadId() << 32;
  v7 = (EapHost::Peer::ConnectionSessionInfo *)(v5 | GetTickCount());
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v18 = v7;
    v21 = (char *)&v18;
    v22 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)EndSessionStart, v6, 2, (__int64)v20);
  }
  v8 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v23, 0x800u, "EapHostPeerEndSession Entry:\n Session(%d)", sessionHandle) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v23[v10] );
    v21 = v23;
    v22 = (unsigned int)(v10 + 1);
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v9, 2, (__int64)v20);
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_e9255469090b376a053f3594056fdc10_Traceguids, sessionHandle);
  v12 = 0;
  v18 = 0;
  if ( sessionHandle )
  {
    SessionFreeBuffers = EapHost::Peer::PeerProxy::FindSessionFreeBuffers((__int64)v11, sessionHandle, &v18, &v19, 0);
    if ( !SessionFreeBuffers )
    {
      if ( ppEapError )
        *ppEapError = 0;
      SessionFreeBuffers = (*(__int64 (__fastcall **)(LPVOID, _QWORD, EAP_ERROR **))(*(_QWORD *)v19 + 96LL))(
                             v19,
                             sessionHandle,
                             ppEapError);
      v4 = EapHost::Peer::PeerProxy::RemoveSessionIfNoConnId(v14, sessionHandle);
    }
    v12 = v18;
  }
  else
  {
    SessionFreeBuffers = 160;
  }
  FormatMessageW(0x1200u, 0, SessionFreeBuffers, 0, Buffer, 0x400u, 0);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    LODWORD(lpBuffer) = sessionHandle;
    if ( (int)StringCchPrintfA(
                v23,
                0x800u,
                "EapHostPeerEndSession Exit:\n %ws\nReturned session(%d).",
                Buffer,
                lpBuffer) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v8;
      while ( v23[v8] );
      v21 = v23;
      v22 = (unsigned int)(v8 + 1);
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v15, 2, (__int64)v20);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, v15, SessionFreeBuffers, sessionHandle);
  if ( v12 && !v4 )
    _InterlockedCompareExchange((volatile signed __int32 *)v12 + 43, 0, *((_DWORD *)v12 + 43));
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v18 = v7;
    v21 = (char *)&v18;
    v22 = 8;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)EndSessionEnd, v15, 2, (__int64)v20);
  }
  if ( v19 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
  return SessionFreeBuffers;
}

```

## disassembly

```asm
0x180006d20  mov     [rsp-8+arg_10], rbx
0x180006d25  push    rbp
0x180006d26  push    rsi
0x180006d27  push    rdi
0x180006d28  push    r12
0x180006d2a  push    r13
0x180006d2c  push    r14
0x180006d2e  push    r15
0x180006d30  lea     rbp, [rsp-0F80h]
0x180006d38  mov     eax, 1080h
0x180006d3d  call    _alloca_probe
0x180006d42  sub     rsp, rax
0x180006d45  mov     rax, cs:__security_cookie
0x180006d4c  xor     rax, rsp
0x180006d4f  mov     [rbp+0FB0h+var_40], rax
0x180006d56  mov     r15, rdx
0x180006d59  mov     esi, ecx
0x180006d5b  xor     edi, edi
0x180006d5d  mov     r13d, edi
0x180006d60  mov     [rsp+10B0h+var_1068], rdi
0x180006d65  call    cs:__imp_GetCurrentThreadId
0x180006d6c  nop     dword ptr [rax+rax+00h]
0x180006d71  mov     ebx, eax
0x180006d73  shl     rbx, 20h
0x180006d77  call    cs:__imp_GetTickCount
0x180006d7e  nop     dword ptr [rax+rax+00h]
0x180006d83  mov     r12d, eax
0x180006d86  or      r12, rbx
0x180006d89  lea     ebx, [rdi+2]
0x180006d8c  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180006d93  jge     short loc_180006DCD
0x180006d95  mov     [rsp+10B0h+var_1070], r12
0x180006d9a  lea     rax, [rsp+10B0h+var_1070]
0x180006d9f  mov     [rsp+10B0h+var_1050], rax
0x180006da4  mov     [rsp+10B0h+var_1048], 8
0x180006dad  lea     rax, [rsp+10B0h+var_1060]
0x180006db2  mov     [rsp+10B0h+lpBuffer], rax
0x180006db7  mov     r9d, ebx
0x180006dba  lea     rdx, EndSessionStart
0x180006dc1  lea     rcx, eaphost_Context
0x180006dc8  call    McGenEventWrite_EtwEventWriteTransfer
0x180006dcd  lea     rdx, DebugInfoEvent
0x180006dd4  mov     rcx, cs:eaphost_Context
0x180006ddb  call    cs:__imp_EtwEventEnabled
0x180006de2  nop     dword ptr [rax+rax+00h]
0x180006de7  or      r14, 0FFFFFFFFFFFFFFFFh
0x180006deb  test    al, al
0x180006ded  jz      short loc_180006E5A
0x180006def  mov     r9d, esi
0x180006df2  lea     r8, aEaphostpeerend_0; "EapHostPeerEndSession Entry:\n Session("...
0x180006df9  mov     edx, 800h; unsigned __int64
0x180006dfe  lea     rcx, [rsp+10B0h+var_1040]; char *
0x180006e03  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180006e08  test    eax, eax
0x180006e0a  js      short loc_180006E5A
0x180006e0c  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180006e13  jge     short loc_180006E5A
0x180006e15  lea     rcx, [rsp+10B0h+var_1040]
0x180006e1a  mov     rax, r14
0x180006e1d  inc     rax
0x180006e20  cmp     [rcx+rax], dil
0x180006e24  jnz     short loc_180006E1D
0x180006e26  inc     eax
0x180006e28  lea     rcx, [rsp+10B0h+var_1040]
0x180006e2d  mov     [rsp+10B0h+var_1050], rcx
0x180006e32  mov     dword ptr [rsp+10B0h+var_1048], eax
0x180006e36  mov     dword ptr [rsp+10B0h+var_1048+4], edi
0x180006e3a  lea     rax, [rsp+10B0h+var_1060]
0x180006e3f  mov     [rsp+10B0h+lpBuffer], rax
0x180006e44  mov     r9d, ebx
0x180006e47  lea     rdx, DebugInfoEvent
0x180006e4e  lea     rcx, eaphost_Context
0x180006e55  call    McGenEventWrite_EtwEventWriteTransfer
0x180006e5a  lea     rax, WPP_GLOBAL_Control
0x180006e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e68  cmp     rcx, rax
0x180006e6b  jz      short loc_180006E8B
0x180006e6d  test    byte ptr [rcx+1Ch], 4
0x180006e71  jz      short loc_180006E8B
0x180006e73  mov     edx, 2Eh ; '.'
0x180006e78  mov     r9d, esi
0x180006e7b  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x180006e82  mov     rcx, [rcx+10h]
0x180006e86  call    WPP_SF_d
0x180006e8b  mov     rbx, rdi
0x180006e8e  mov     [rsp+10B0h+var_1070], rbx
0x180006e93  test    esi, esi
0x180006e95  jnz     short loc_180006E9E
0x180006e97  mov     edi, 0A0h
0x180006e9c  jmp     short loc_180006EE8
0x180006e9e  mov     dword ptr [rsp+10B0h+lpBuffer], edi
0x180006ea2  lea     r9, [rsp+10B0h+var_1068]
0x180006ea7  lea     r8, [rsp+10B0h+var_1070]
0x180006eac  mov     edx, esi
0x180006eae  call    ?FindSessionFreeBuffers@PeerProxy@Peer@EapHost@@QEAAKKAEAPEAVConnectionSessionInfo@23@AEAV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@H@Z; EapHost::Peer::PeerProxy::FindSessionFreeBuffers(ulong,EapHost::Peer::ConnectionSessionInfo * &,ATL::CComPtr<IEapHostPeerSessionApis> &,int)
0x180006eb3  mov     edi, eax
0x180006eb5  test    eax, eax
0x180006eb7  jnz     short loc_180006EE3
0x180006eb9  test    r15, r15
0x180006ebc  jz      short loc_180006EC1
0x180006ebe  mov     [r15], rbx
0x180006ec1  mov     rcx, [rsp+10B0h+var_1068]
0x180006ec6  mov     rax, [rcx]
0x180006ec9  mov     r8, r15
0x180006ecc  mov     edx, esi
0x180006ece  mov     rax, [rax+60h]
0x180006ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed7  mov     edi, eax
0x180006ed9  mov     edx, esi; unsigned int
0x180006edb  call    ?RemoveSessionIfNoConnId@PeerProxy@Peer@EapHost@@QEAAHK@Z; EapHost::Peer::PeerProxy::RemoveSessionIfNoConnId(ulong)
0x180006ee0  mov     r13d, eax
0x180006ee3  mov     rbx, [rsp+10B0h+var_1070]
0x180006ee8  xor     r15d, r15d
0x180006eeb  mov     [rsp+10B0h+Arguments], r15; Arguments
0x180006ef0  mov     [rsp+10B0h+nSize], 400h; nSize
0x180006ef8  lea     rax, [rbp+0FB0h+Buffer]
0x180006eff  mov     [rsp+10B0h+lpBuffer], rax; lpBuffer
0x180006f04  xor     r9d, r9d; dwLanguageId
0x180006f07  mov     r8d, edi; dwMessageId
0x180006f0a  xor     edx, edx; lpSource
0x180006f0c  mov     ecx, 1200h; dwFlags
0x180006f11  call    cs:__imp_FormatMessageW
0x180006f18  nop     dword ptr [rax+rax+00h]
0x180006f1d  lea     rdx, DebugInfoEvent
0x180006f24  mov     rcx, cs:eaphost_Context
0x180006f2b  call    cs:__imp_EtwEventEnabled
0x180006f32  nop     dword ptr [rax+rax+00h]
0x180006f37  test    al, al
0x180006f39  jz      short loc_180006FB1
0x180006f3b  mov     dword ptr [rsp+10B0h+lpBuffer], esi
0x180006f3f  lea     r9, [rbp+0FB0h+Buffer]
0x180006f46  lea     r8, aEaphostpeerend_1; "EapHostPeerEndSession Exit:\n %ws\nRetu"...
0x180006f4d  mov     edx, 800h; unsigned __int64
0x180006f52  lea     rcx, [rsp+10B0h+var_1040]; char *
0x180006f57  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180006f5c  test    eax, eax
0x180006f5e  js      short loc_180006FB1
0x180006f60  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x180006f67  jge     short loc_180006FB1
0x180006f69  lea     rax, [rsp+10B0h+var_1040]
0x180006f6e  inc     r14
0x180006f71  cmp     [rax+r14], r15b
0x180006f75  jnz     short loc_180006F6E
0x180006f77  lea     eax, [r14+1]
0x180006f7b  lea     rcx, [rsp+10B0h+var_1040]
0x180006f80  mov     [rsp+10B0h+var_1050], rcx
0x180006f85  mov     dword ptr [rsp+10B0h+var_1048], eax
0x180006f89  mov     dword ptr [rsp+10B0h+var_1048+4], r15d
0x180006f8e  lea     rax, [rsp+10B0h+var_1060]
0x180006f93  mov     [rsp+10B0h+lpBuffer], rax
0x180006f98  mov     r9d, 2
0x180006f9e  lea     rdx, DebugInfoEvent
0x180006fa5  lea     rcx, eaphost_Context
0x180006fac  call    McGenEventWrite_EtwEventWriteTransfer
0x180006fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fb8  lea     rax, WPP_GLOBAL_Control
0x180006fbf  cmp     rcx, rax
0x180006fc2  jz      short loc_180006FDF
0x180006fc4  test    byte ptr [rcx+1Ch], 4
0x180006fc8  jz      short loc_180006FDF
0x180006fca  mov     edx, 2Fh ; '/'
0x180006fcf  mov     dword ptr [rsp+10B0h+lpBuffer], esi
0x180006fd3  mov     r9d, edi
0x180006fd6  mov     rcx, [rcx+10h]
0x180006fda  call    WPP_SF_Dd
0x180006fdf  test    rbx, rbx
0x180006fe2  jz      short loc_180006FFA
0x180006fe4  test    r13d, r13d
0x180006fe7  jnz     short loc_180006FFA
0x180006fe9  mov     ecx, r15d
0x180006fec  mov     eax, [rbx+0ACh]
0x180006ff2  lock cmpxchg [rbx+0ACh], ecx
0x180006ffa  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x180007001  jge     short loc_18000703F
0x180007003  mov     [rsp+10B0h+var_1070], r12
0x180007008  lea     rax, [rsp+10B0h+var_1070]
0x18000700d  mov     [rsp+10B0h+var_1050], rax
0x180007012  mov     [rsp+10B0h+var_1048], 8
0x18000701b  lea     rax, [rsp+10B0h+var_1060]
0x180007020  mov     [rsp+10B0h+lpBuffer], rax
0x180007025  mov     r9d, 2
0x18000702b  lea     rdx, EndSessionEnd
0x180007032  lea     rcx, eaphost_Context
0x180007039  call    McGenEventWrite_EtwEventWriteTransfer
0x18000703e  nop
0x18000703f  mov     rcx, [rsp+10B0h+var_1068]
0x180007044  test    rcx, rcx
0x180007047  jz      short loc_180007056
0x180007049  mov     rax, [rcx]
0x18000704c  mov     rax, [rax+10h]
0x180007050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007055  nop
0x180007056  mov     eax, edi
0x180007058  mov     rcx, [rbp+0FB0h+var_40]
0x18000705f  xor     rcx, rsp; StackCookie
0x180007062  call    __security_check_cookie
0x180007067  mov     rbx, [rsp+10B0h+arg_10]
0x18000706f  add     rsp, 1080h
0x180007076  pop     r15
0x180007078  pop     r14
0x18000707a  pop     r13
0x18000707c  pop     r12
0x18000707e  pop     rdi
0x18000707f  pop     rsi
0x180007080  pop     rbp
0x180007081  retn
```

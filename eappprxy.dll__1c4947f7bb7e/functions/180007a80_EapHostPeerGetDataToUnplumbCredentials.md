# EapHostPeerGetDataToUnplumbCredentials

- ea: `0x180007a80`
- end: `0x180007d3a`
- name: `EapHostPeerGetDataToUnplumbCredentials`
- size: `698`
- prototype: `DWORD __stdcall(GUID *pConnectionIdThatLastSavedCreds, __int64 *phCredentialImpersonationToken, EAP_SESSIONID sessionHandle, EAP_ERROR **ppEapError, BOOL *fSaveToCredMan)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x180005450`
- `0x180007a80`
- `0x18000ace0`
- `0x18000adb4`
- `0x18000bef4`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180007ae0`
- `ntdll!EtwEventEnabled` at `0x180007c36`
- `ntdll!EtwEventEnabled` at `0x180007ae0`
- `ntdll!EtwEventEnabled` at `0x180007c36`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007c1c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007c1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __stdcall EapHostPeerGetDataToUnplumbCredentials(
        GUID *pConnectionIdThatLastSavedCreds,
        __int64 *phCredentialImpersonationToken,
        EAP_SESSIONID sessionHandle,
        EAP_ERROR **ppEapError,
        BOOL *fSaveToCredMan)
{
  __int64 v9; // rsi
  __int64 v10; // r8
  __int64 v11; // rax
  void *v12; // rcx
  EapHost::Peer::ConnectionSessionInfo *v13; // rbx
  DWORD SessionFreeBuffers; // edi
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h]
  EapHost::Peer::ConnectionSessionInfo *v17; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v18; // [rsp+48h] [rbp-B8h] BYREF
  BOOL *v19; // [rsp+50h] [rbp-B0h]
  _BYTE v20[16]; // [rsp+58h] [rbp-A8h] BYREF
  char *v21; // [rsp+68h] [rbp-98h]
  int v22; // [rsp+70h] [rbp-90h]
  int v23; // [rsp+74h] [rbp-8Ch]
  char v24[2048]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[1024]; // [rsp+880h] [rbp+780h] BYREF

  v19 = fSaveToCredMan;
  v18 = 0;
  v9 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v24, 0x800u, "EapHostPeerGetDataToUnplumbCredentials Entry") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v24[v11] );
    v21 = v24;
    v22 = v11 + 1;
    v23 = 0;
    McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v10, 2, (__int64)v20);
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_e9255469090b376a053f3594056fdc10_Traceguids);
  v13 = 0;
  v17 = 0;
  if ( sessionHandle )
  {
    SessionFreeBuffers = EapHost::Peer::PeerProxy::FindSessionFreeBuffers((__int64)v12, sessionHandle, &v17, &v18, 0);
    if ( !SessionFreeBuffers )
    {
      if ( ppEapError )
        *ppEapError = 0;
      (*(void (__fastcall **)(LPVOID, GUID *, __int64 *, _QWORD, EAP_ERROR **, BOOL *))(*(_QWORD *)v18 + 104LL))(
        v18,
        pConnectionIdThatLastSavedCreds,
        phCredentialImpersonationToken,
        sessionHandle,
        ppEapError,
        v19);
    }
    v13 = v17;
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
                v24,
                0x800u,
                "EapHostPeerGetDataToUnplumbCredentials Exit:\n %ws\nReturned session(%d).",
                Buffer,
                lpBuffer) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v9;
      while ( v24[v9] );
      v21 = v24;
      v22 = v9 + 1;
      v23 = 0;
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, (__int64)v24, 2, (__int64)v20);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_e9255469090b376a053f3594056fdc10_Traceguids);
  if ( v13 )
    _InterlockedCompareExchange((volatile signed __int32 *)v13 + 43, 0, *((_DWORD *)v13 + 43));
  if ( v18 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
  return SessionFreeBuffers;
}

```

## disassembly

```asm
0x180007a80  push    rbp
0x180007a82  push    rbx
0x180007a83  push    rsi
0x180007a84  push    rdi
0x180007a85  push    r12
0x180007a87  push    r13
0x180007a89  push    r14
0x180007a8b  push    r15
0x180007a8d  lea     rbp, [rsp-0F98h]
0x180007a95  mov     eax, 1098h
0x180007a9a  call    _alloca_probe
0x180007a9f  sub     rsp, rax
0x180007aa2  mov     rax, cs:__security_cookie
0x180007aa9  xor     rax, rsp
0x180007aac  mov     [rbp+0FD0h+var_50], rax
0x180007ab3  mov     r15, r9
0x180007ab6  mov     r14d, r8d
0x180007ab9  mov     r13, rdx
0x180007abc  mov     r12, rcx
0x180007abf  mov     rax, [rbp+0FD0h+fSaveToCredMan]
0x180007ac6  mov     [rsp+10D0h+var_1080], rax
0x180007acb  xor     edi, edi
0x180007acd  mov     [rsp+10D0h+var_1088], rdi
0x180007ad2  lea     rdx, DebugInfoEvent
0x180007ad9  mov     rcx, cs:eaphost_Context
0x180007ae0  call    cs:__imp_EtwEventEnabled
0x180007ae7  nop     dword ptr [rax+rax+00h]
0x180007aec  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007af0  test    al, al
0x180007af2  jz      short loc_180007B5C
0x180007af4  lea     r8, aEaphostpeerget_18; "EapHostPeerGetDataToUnplumbCredentials "...
0x180007afb  mov     edx, 800h; unsigned __int64
0x180007b00  lea     rcx, [rbp+0FD0h+var_1050]; char *
0x180007b04  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007b09  test    eax, eax
0x180007b0b  js      short loc_180007B5C
0x180007b0d  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180007b14  jge     short loc_180007B5C
0x180007b16  lea     rcx, [rbp+0FD0h+var_1050]
0x180007b1a  mov     rax, rsi
0x180007b1d  inc     rax
0x180007b20  cmp     [rcx+rax], dil
0x180007b24  jnz     short loc_180007B1D
0x180007b26  inc     eax
0x180007b28  lea     rcx, [rbp+0FD0h+var_1050]
0x180007b2c  mov     [rsp+10D0h+var_1068], rcx
0x180007b31  mov     [rsp+10D0h+var_1060], eax
0x180007b35  mov     [rsp+10D0h+var_105C], edi
0x180007b39  lea     rax, [rsp+10D0h+var_1078]
0x180007b3e  mov     [rsp+10D0h+lpBuffer], rax
0x180007b43  mov     r9d, 2
0x180007b49  lea     rdx, DebugInfoEvent
0x180007b50  lea     rcx, eaphost_Context
0x180007b57  call    McGenEventWrite_EtwEventWriteTransfer
0x180007b5c  lea     rax, WPP_GLOBAL_Control
0x180007b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b6a  cmp     rcx, rax
0x180007b6d  jz      short loc_180007B8A
0x180007b6f  test    byte ptr [rcx+1Ch], 4
0x180007b73  jz      short loc_180007B8A
0x180007b75  mov     edx, 30h ; '0'
0x180007b7a  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x180007b81  mov     rcx, [rcx+10h]
0x180007b85  call    WPP_SF_
0x180007b8a  mov     rbx, rdi
0x180007b8d  mov     [rsp+10D0h+var_1090], rbx
0x180007b92  test    r14d, r14d
0x180007b95  jnz     short loc_180007B9E
0x180007b97  mov     edi, 0A0h
0x180007b9c  jmp     short loc_180007BF3
0x180007b9e  mov     dword ptr [rsp+10D0h+lpBuffer], edi
0x180007ba2  lea     r9, [rsp+10D0h+var_1088]
0x180007ba7  lea     r8, [rsp+10D0h+var_1090]
0x180007bac  mov     edx, r14d
0x180007baf  call    ?FindSessionFreeBuffers@PeerProxy@Peer@EapHost@@QEAAKKAEAPEAVConnectionSessionInfo@23@AEAV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@H@Z; EapHost::Peer::PeerProxy::FindSessionFreeBuffers(ulong,EapHost::Peer::ConnectionSessionInfo * &,ATL::CComPtr<IEapHostPeerSessionApis> &,int)
0x180007bb4  mov     edi, eax
0x180007bb6  test    eax, eax
0x180007bb8  jnz     short loc_180007BEE
0x180007bba  test    r15, r15
0x180007bbd  jz      short loc_180007BC2
0x180007bbf  mov     [r15], rbx
0x180007bc2  mov     r10, [rsp+10D0h+var_1088]
0x180007bc7  mov     rcx, [r10]
0x180007bca  mov     rax, [rcx+68h]
0x180007bce  mov     rcx, [rsp+10D0h+var_1080]
0x180007bd3  mov     qword ptr [rsp+10D0h+nSize], rcx
0x180007bd8  mov     [rsp+10D0h+lpBuffer], r15
0x180007bdd  mov     r9d, r14d
0x180007be0  mov     r8, r13
0x180007be3  mov     rdx, r12
0x180007be6  mov     rcx, r10
0x180007be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bee  mov     rbx, [rsp+10D0h+var_1090]
0x180007bf3  xor     r15d, r15d
0x180007bf6  mov     [rsp+10D0h+Arguments], r15; Arguments
0x180007bfb  mov     [rsp+10D0h+nSize], 400h; nSize
0x180007c03  lea     rax, [rbp+0FD0h+Buffer]
0x180007c0a  mov     [rsp+10D0h+lpBuffer], rax; lpBuffer
0x180007c0f  xor     r9d, r9d; dwLanguageId
0x180007c12  mov     r8d, edi; dwMessageId
0x180007c15  xor     edx, edx; lpSource
0x180007c17  mov     ecx, 1200h; dwFlags
0x180007c1c  call    cs:__imp_FormatMessageW
0x180007c23  nop     dword ptr [rax+rax+00h]
0x180007c28  lea     rdx, DebugInfoEvent
0x180007c2f  mov     rcx, cs:eaphost_Context
0x180007c36  call    cs:__imp_EtwEventEnabled
0x180007c3d  nop     dword ptr [rax+rax+00h]
0x180007c42  test    al, al
0x180007c44  jz      short loc_180007CB9
0x180007c46  mov     dword ptr [rsp+10D0h+lpBuffer], r14d
0x180007c4b  lea     r9, [rbp+0FD0h+Buffer]
0x180007c52  lea     r8, aEaphostpeerget_20; "EapHostPeerGetDataToUnplumbCredentials "...
0x180007c59  mov     edx, 800h; unsigned __int64
0x180007c5e  lea     rcx, [rbp+0FD0h+var_1050]; char *
0x180007c62  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007c67  test    eax, eax
0x180007c69  js      short loc_180007CB9
0x180007c6b  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x180007c72  jge     short loc_180007CB9
0x180007c74  lea     rax, [rbp+0FD0h+var_1050]
0x180007c78  inc     rsi
0x180007c7b  cmp     [rax+rsi], r15b
0x180007c7f  jnz     short loc_180007C78
0x180007c81  lea     eax, [rsi+1]
0x180007c84  lea     r8, [rbp+0FD0h+var_1050]
0x180007c88  mov     [rsp+10D0h+var_1068], r8
0x180007c8d  mov     [rsp+10D0h+var_1060], eax
0x180007c91  mov     [rsp+10D0h+var_105C], r15d
0x180007c96  lea     rax, [rsp+10D0h+var_1078]
0x180007c9b  mov     [rsp+10D0h+lpBuffer], rax
0x180007ca0  mov     r9d, 2
0x180007ca6  lea     rdx, DebugInfoEvent
0x180007cad  lea     rcx, eaphost_Context
0x180007cb4  call    McGenEventWrite_EtwEventWriteTransfer
0x180007cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cc0  lea     rax, WPP_GLOBAL_Control
0x180007cc7  cmp     rcx, rax
0x180007cca  jz      short loc_180007CE7
0x180007ccc  test    byte ptr [rcx+1Ch], 4
0x180007cd0  jz      short loc_180007CE7
0x180007cd2  mov     edx, 31h ; '1'
0x180007cd7  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x180007cde  mov     rcx, [rcx+10h]
0x180007ce2  call    WPP_SF_
0x180007ce7  test    rbx, rbx
0x180007cea  jz      short loc_180007CFD
0x180007cec  mov     ecx, r15d
0x180007cef  mov     eax, [rbx+0ACh]
0x180007cf5  lock cmpxchg [rbx+0ACh], ecx
0x180007cfd  mov     rcx, [rsp+10D0h+var_1088]
0x180007d02  test    rcx, rcx
0x180007d05  jz      short loc_180007D14
0x180007d07  mov     rax, [rcx]
0x180007d0a  mov     rax, [rax+10h]
0x180007d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d13  nop
0x180007d14  mov     eax, edi
0x180007d16  mov     rcx, [rbp+0FD0h+var_50]
0x180007d1d  xor     rcx, rsp; StackCookie
0x180007d20  call    __security_check_cookie
0x180007d25  add     rsp, 1098h
0x180007d2c  pop     r15
0x180007d2e  pop     r14
0x180007d30  pop     r13
0x180007d32  pop     r12
0x180007d34  pop     rdi
0x180007d35  pop     rsi
0x180007d36  pop     rbx
0x180007d37  pop     rbp
0x180007d38  retn
```

# EapHostPeerGetIdentity

- ea: `0x1800080c0`
- end: `0x18000883c`
- name: `EapHostPeerGetIdentity`
- size: `1916`
- prototype: `DWORD __stdcall(DWORD dwVersion, DWORD dwFlags, EAP_METHOD_TYPE *__struct_ptr eapMethodType, DWORD dwSizeofConnectionData, const BYTE *pConnectionData, DWORD dwSizeofUserData, const BYTE *pUserData, HANDLE hTokenImpersonateUser, BOOL *pfInvokeUI, DWORD *pdwSizeOfUserDataOut, BYTE **ppUserDataOut, LPWSTR *ppwszIdentity, EAP_ERROR **ppEapError, BYTE **ppvReserved)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x180005450`
- `0x1800080c0`
- `0x18000ace0`
- `0x18000adb4`
- `0x18000ade4`
- `0x18000afec`
- `0x18000b140`
- `0x18000bac0`
- `0x18000c204`
- `0x18000c6e0`
- `0x18000f010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000823e`
- `ntdll!EtwEventEnabled` at `0x18000860b`
- `ntdll!EtwEventEnabled` at `0x180008757`
- `ntdll!EtwEventEnabled` at `0x18000823e`
- `ntdll!EtwEventEnabled` at `0x18000860b`
- `ntdll!EtwEventEnabled` at `0x180008757`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008460`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008460`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800081bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800081bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
DWORD __stdcall EapHostPeerGetIdentity(
        DWORD dwVersion,
        DWORD dwFlags,
        EAP_METHOD_TYPE *eapMethodType,
        DWORD dwSizeofConnectionData,
        const BYTE *pConnectionData,
        DWORD dwSizeofUserData,
        const BYTE *pUserData,
        HANDLE hTokenImpersonateUser,
        BOOL *pfInvokeUI,
        DWORD *pdwSizeOfUserDataOut,
        BYTE **ppUserDataOut,
        LPWSTR *ppwszIdentity,
        EAP_ERROR **ppEapError,
        BYTE **ppvReserved)
{
  __int64 v17; // rbx
  unsigned __int64 v18; // rdi
  DWORD TickCount; // eax
  int v20; // r8d
  unsigned __int64 v21; // r13
  __int64 v22; // r8
  __int64 v23; // r15
  __int64 v24; // rax
  LPWSTR *v25; // rax
  DWORD *v26; // rdx
  BYTE **v27; // r8
  int v28; // eax
  DWORD v29; // esi
  EapHost::Peer::ConnectionSessionInfo *v30; // rdi
  _QWORD *HostApis; // rax
  __int64 v32; // rsi
  __int64 v33; // r13
  __int64 (__fastcall *v34)(__int64, _QWORD, _QWORD, __int128 *, DWORD, const BYTE *, DWORD, const BYTE *, DWORD, HANDLE, BOOL *, DWORD *, BYTE **, WCHAR **, EAP_ERROR **, __int64 *); // rsi
  DWORD CurrentProcessId; // eax
  int v36; // eax
  __int64 v37; // r8
  int v38; // r8d
  int v40; // r8d
  EapHost::Peer::ConnectionSessionInfo *v43; // [rsp+98h] [rbp-900h] BYREF
  WCHAR *v44; // [rsp+A0h] [rbp-8F8h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-8F0h]
  unsigned __int64 v46; // [rsp+B0h] [rbp-8E8h] BYREF
  unsigned __int64 v47; // [rsp+B8h] [rbp-8E0h] BYREF
  BYTE **v48; // [rsp+C0h] [rbp-8D8h]
  DWORD *v49; // [rsp+C8h] [rbp-8D0h]
  BOOL *v50; // [rsp+D0h] [rbp-8C8h]
  LPWSTR *v51; // [rsp+D8h] [rbp-8C0h]
  unsigned __int64 v52; // [rsp+E0h] [rbp-8B8h]
  __int128 v53; // [rsp+F0h] [rbp-8A8h] BYREF
  __int64 v54; // [rsp+100h] [rbp-898h] BYREF
  EAP_ERROR **v55; // [rsp+108h] [rbp-890h]
  HANDLE v56; // [rsp+110h] [rbp-888h]
  const BYTE *v57; // [rsp+118h] [rbp-880h]
  const BYTE *v58; // [rsp+120h] [rbp-878h]
  _BYTE v59[16]; // [rsp+128h] [rbp-870h] BYREF
  char *v60; // [rsp+138h] [rbp-860h]
  __int64 v61; // [rsp+140h] [rbp-858h]
  char v62[2048]; // [rsp+150h] [rbp-848h] BYREF

  *(_QWORD *)&v53 = eapMethodType;
  v58 = pConnectionData;
  v57 = pUserData;
  v56 = hTokenImpersonateUser;
  v50 = pfInvokeUI;
  v49 = pdwSizeOfUserDataOut;
  v48 = ppUserDataOut;
  v51 = ppwszIdentity;
  v55 = ppEapError;
  v43 = 0;
  v17 = 0;
  v45 = 0;
  v44 = 0;
  v54 = 0;
  v18 = (unsigned __int64)GetCurrentThreadId() << 32;
  TickCount = GetTickCount();
  v21 = v18 | TickCount;
  v52 = v21;
  v47 = v21;
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v46 = v18 | TickCount;
    v60 = (char *)&v46;
    v61 = 8;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)GetIdentityStart,
      v20,
      2,
      (__int64)v59);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v62,
              0x800u,
              " EapHostPeerGetIdentity Entry:\n"
              " flags(0x%x), eapType(authorId=%d, vendorId=%d, vendorType=%d, type=%d), conn data (%d) bytes, user data(%d) bytes",
              dwFlags,
              eapMethodType->dwAuthorId,
              eapMethodType->eapType.dwVendorId,
              eapMethodType->eapType.dwVendorType,
              eapMethodType->eapType.type,
              dwSizeofConnectionData,
              dwSizeofUserData) >= 0 )
  {
    v23 = -1;
    if ( Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v62[v24] );
      v60 = v62;
      v61 = (unsigned int)(v24 + 1);
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v22,
        2,
        (__int64)v59);
    }
  }
  else
  {
    v23 = -1;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Ddddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      dwSizeofConnectionData,
      v22,
      dwFlags,
      eapMethodType->dwAuthorId,
      eapMethodType->eapType.dwVendorId,
      eapMethodType->eapType.dwVendorType,
      eapMethodType->eapType.type,
      dwSizeofConnectionData,
      dwSizeofUserData);
  v25 = v51;
  if ( v51 && (v26 = v49) != 0 && (v27 = v48) != 0 && v50 )
  {
    *v50 = 0;
    *v26 = 0;
    *v27 = 0;
    *v25 = 0;
    v28 = EapHost::Peer::ConnectionSessionInfo::CreateInstance(&v43, HIDWORD(qword_180015528));
    v29 = v28;
    if ( v28 >= 0 )
    {
      v30 = v43;
      HostApis = (_QWORD *)EapHost::Peer::ConnectionSessionInfo::GetHostApis(v43, &v46);
      v32 = *HostApis;
      if ( *HostApis )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v32 + 8LL))(*HostApis);
        v17 = v32;
        v45 = v32;
      }
      if ( v46 )
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v46 + 16LL))(v46);
      v33 = v17;
      v34 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int128 *, DWORD, const BYTE *, DWORD, const BYTE *, DWORD, HANDLE, BOOL *, DWORD *, BYTE **, WCHAR **, EAP_ERROR **, __int64 *))(*(_QWORD *)v17 + 120LL);
      CurrentProcessId = GetCurrentProcessId();
      v53 = *(_OWORD *)v53;
      v36 = v34(
              v17,
              0,
              dwFlags,
              &v53,
              dwSizeofConnectionData,
              v58,
              dwSizeofUserData,
              v57,
              CurrentProcessId,
              v56,
              v50,
              v49,
              v48,
              &v44,
              v55,
              &v54);
      v29 = v36;
      if ( v36 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v37, v44);
        *v51 = v44;
        if ( v17 )
        {
          v17 = 0;
          v45 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        }
        v21 = v52;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_e9255469090b376a053f3594056fdc10_Traceguids,
            (unsigned int)v36);
        v21 = v52;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_e9255469090b376a053f3594056fdc10_Traceguids,
          (unsigned int)v28);
      v30 = v43;
    }
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v62, 0x800u, "EapHostPeerGetIdentity Exit:\n returned: 0x%x", v29) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v23;
      while ( v62[v23] );
      v60 = v62;
      v61 = (unsigned int)(v23 + 1);
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v38,
        2,
        (__int64)v59);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_e9255469090b376a053f3594056fdc10_Traceguids, v29);
    if ( Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v47 = v21;
      v60 = (char *)&v47;
      v61 = 8;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)GetIdentityEnd,
        v38,
        2,
        (__int64)v59);
    }
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v30 )
      EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(v30);
    return v29;
  }
  else
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v62, 0x800u, "Invalid argument passed for out parameters") >= 0
      && (byte_180015441 & 8) != 0 )
    {
      do
        ++v23;
      while ( v62[v23] );
      v60 = v62;
      v61 = (unsigned int)(v23 + 1);
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugErrorEvent,
        v40,
        2,
        (__int64)v59);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e9255469090b376a053f3594056fdc10_Traceguids);
    return 87;
  }
}

```

## disassembly

```asm
0x1800080c0  push    rbx
0x1800080c2  push    rsi
0x1800080c3  push    rdi
0x1800080c4  push    r12
0x1800080c6  push    r13
0x1800080c8  push    r14
0x1800080ca  push    r15
0x1800080cc  sub     rsp, 960h
0x1800080d3  mov     rax, cs:__security_cookie
0x1800080da  xor     rax, rsp
0x1800080dd  mov     [rsp+998h+var_48], rax
0x1800080e5  mov     r12d, r9d
0x1800080e8  mov     [rsp+998h+var_904], r9d
0x1800080f0  mov     rsi, r8
0x1800080f3  mov     qword ptr [rsp+998h+var_8A8], r8
0x1800080fb  mov     r15d, edx
0x1800080fe  mov     [rsp+998h+var_908], edx
0x180008105  mov     rax, [rsp+998h+pConnectionData]
0x18000810d  mov     [rsp+998h+var_878], rax
0x180008115  mov     rax, [rsp+998h+pUserData]
0x18000811d  mov     [rsp+998h+var_880], rax
0x180008125  mov     rax, [rsp+998h+hTokenImpersonateUser]
0x18000812d  mov     [rsp+998h+var_888], rax
0x180008135  mov     rax, [rsp+998h+pfInvokeUI]
0x18000813d  mov     [rsp+998h+var_8C8], rax
0x180008145  mov     rax, [rsp+998h+pdwSizeOfUserDataOut]
0x18000814d  mov     [rsp+998h+var_8D0], rax
0x180008155  mov     rax, [rsp+998h+ppUserDataOut]
0x18000815d  mov     [rsp+998h+var_8D8], rax
0x180008165  mov     rcx, [rsp+998h+ppwszIdentity]
0x18000816d  mov     [rsp+998h+var_8C0], rcx
0x180008175  mov     rax, [rsp+998h+ppEapError]
0x18000817d  mov     [rsp+998h+var_890], rax
0x180008185  xor     r14d, r14d
0x180008188  mov     [rsp+998h+var_900], r14
0x180008190  mov     ebx, r14d
0x180008193  mov     [rsp+998h+var_8F0], rbx
0x18000819b  mov     [rsp+998h+var_8F8], r14
0x1800081a3  mov     [rsp+998h+var_898], r14
0x1800081ab  call    cs:__imp_GetCurrentThreadId
0x1800081b2  nop     dword ptr [rax+rax+00h]
0x1800081b7  mov     edi, eax
0x1800081b9  shl     rdi, 20h
0x1800081bd  call    cs:__imp_GetTickCount
0x1800081c4  nop     dword ptr [rax+rax+00h]
0x1800081c9  mov     r13d, eax
0x1800081cc  or      r13, rdi
0x1800081cf  mov     [rsp+998h+var_8B8], r13
0x1800081d7  mov     [rsp+998h+var_8E0], r13
0x1800081df  cmp     cs:Microsoft_Windows_EapHostEnableBits, r14b
0x1800081e6  jge     short loc_180008230
0x1800081e8  mov     [rsp+998h+var_8E8], r13
0x1800081f0  lea     rax, [rsp+998h+var_8E8]
0x1800081f8  mov     [rsp+998h+var_860], rax
0x180008200  mov     [rsp+998h+var_858], 8
0x18000820c  lea     rax, [rsp+998h+var_870]
0x180008214  mov     [rsp+998h+var_978], rax
0x180008219  lea     r9d, [r14+2]
0x18000821d  lea     rdx, GetIdentityStart
0x180008224  lea     rcx, eaphost_Context
0x18000822b  call    McGenEventWrite_EtwEventWriteTransfer
0x180008230  lea     rdx, DebugInfoEvent
0x180008237  mov     rcx, cs:eaphost_Context
0x18000823e  call    cs:__imp_EtwEventEnabled
0x180008245  nop     dword ptr [rax+rax+00h]
0x18000824a  mov     edi, [rsp+998h+dwSizeofUserData]
0x180008251  test    al, al
0x180008253  jz      loc_180008308
0x180008259  movzx   eax, byte ptr [rsi]
0x18000825c  mov     dword ptr [rsp+998h+var_950], edi
0x180008260  mov     [rsp+998h+var_958], r12d
0x180008265  mov     dword ptr [rsp+998h+var_960], eax
0x180008269  mov     eax, [rsi+8]
0x18000826c  mov     [rsp+998h+var_968], eax
0x180008270  mov     eax, [rsi+4]
0x180008273  mov     dword ptr [rsp+998h+var_970], eax
0x180008277  mov     eax, [rsi+0Ch]
0x18000827a  mov     dword ptr [rsp+998h+var_978], eax
0x18000827e  mov     r9d, r15d
0x180008281  lea     r8, aEaphostpeerget_15; " EapHostPeerGetIdentity Entry:\n flags("...
0x180008288  mov     edx, 800h; unsigned __int64
0x18000828d  lea     rcx, [rsp+998h+var_848]; char *
0x180008295  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000829a  test    eax, eax
0x18000829c  js      short loc_180008308
0x18000829e  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800082a2  cmp     cs:Microsoft_Windows_EapHostEnableBits, r14b
0x1800082a9  jge     short loc_18000830C
0x1800082ab  lea     rcx, [rsp+998h+var_848]
0x1800082b3  mov     rax, r15
0x1800082b6  inc     rax
0x1800082b9  cmp     [rcx+rax], r14b
0x1800082bd  jnz     short loc_1800082B6
0x1800082bf  inc     eax
0x1800082c1  lea     rcx, [rsp+998h+var_848]
0x1800082c9  mov     [rsp+998h+var_860], rcx
0x1800082d1  mov     dword ptr [rsp+998h+var_858], eax
0x1800082d8  mov     dword ptr [rsp+998h+var_858+4], r14d
0x1800082e0  lea     rax, [rsp+998h+var_870]
0x1800082e8  mov     [rsp+998h+var_978], rax
0x1800082ed  mov     r9d, 2
0x1800082f3  lea     rdx, DebugInfoEvent
0x1800082fa  lea     rcx, eaphost_Context
0x180008301  call    McGenEventWrite_EtwEventWriteTransfer
0x180008306  jmp     short loc_18000830C
0x180008308  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000830c  lea     r12, WPP_GLOBAL_Control
0x180008313  mov     rcx, cs:WPP_GLOBAL_Control
0x18000831a  cmp     rcx, r12
0x18000831d  jz      short loc_180008361
0x18000831f  test    byte ptr [rcx+1Ch], 4
0x180008323  jz      short loc_180008361
0x180008325  movzx   eax, byte ptr [rsi]
0x180008328  mov     dword ptr [rsp+998h+var_950], edi
0x18000832c  mov     edx, [rsp+998h+var_904]
0x180008333  mov     [rsp+998h+var_958], edx
0x180008337  mov     dword ptr [rsp+998h+var_960], eax
0x18000833b  mov     eax, [rsi+8]
0x18000833e  mov     [rsp+998h+var_968], eax
0x180008342  mov     eax, [rsi+4]
0x180008345  mov     dword ptr [rsp+998h+var_970], eax
0x180008349  mov     eax, [rsi+0Ch]
0x18000834c  mov     dword ptr [rsp+998h+var_978], eax
0x180008350  mov     r9d, [rsp+998h+var_908]
0x180008358  mov     rcx, [rcx+10h]
0x18000835c  call    WPP_SF_Ddddddd
0x180008361  mov     rax, [rsp+998h+var_8C0]
0x180008369  test    rax, rax
0x18000836c  jz      loc_180008749
0x180008372  mov     rdx, [rsp+998h+var_8D0]
0x18000837a  test    rdx, rdx
0x18000837d  jz      loc_180008749
0x180008383  mov     r8, [rsp+998h+var_8D8]
0x18000838b  test    r8, r8
0x18000838e  jz      loc_180008749
0x180008394  mov     rcx, [rsp+998h+var_8C8]
0x18000839c  test    rcx, rcx
0x18000839f  jz      loc_180008749
0x1800083a5  mov     [rcx], r14d
0x1800083a8  mov     [rdx], r14d
0x1800083ab  mov     [r8], r14
0x1800083ae  mov     [rax], r14
0x1800083b1  mov     edx, dword ptr cs:qword_180015528+4; unsigned int
0x1800083b7  lea     rcx, [rsp+998h+var_900]; struct EapHost::Peer::ConnectionSessionInfoPtr *
0x1800083bf  call    ?CreateInstance@ConnectionSessionInfo@Peer@EapHost@@SAJAEAVConnectionSessionInfoPtr@23@K@Z; EapHost::Peer::ConnectionSessionInfo::CreateInstance(EapHost::Peer::ConnectionSessionInfoPtr &,ulong)
0x1800083c4  mov     esi, eax
0x1800083c6  test    eax, eax
0x1800083c8  jns     short loc_180008402
0x1800083ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083d1  cmp     rcx, r12
0x1800083d4  jz      short loc_1800083F5
0x1800083d6  test    byte ptr [rcx+1Ch], 4
0x1800083da  jz      short loc_1800083F5
0x1800083dc  mov     edx, 14h
0x1800083e1  mov     r9d, eax
0x1800083e4  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x1800083eb  mov     rcx, [rcx+10h]
0x1800083ef  call    WPP_SF_d
0x1800083f4  nop
0x1800083f5  mov     rdi, [rsp+998h+var_900]
0x1800083fd  jmp     loc_1800085FD
0x180008402  lea     rdx, [rsp+998h+var_8E8]
0x18000840a  mov     rdi, [rsp+998h+var_900]
0x180008412  mov     rcx, rdi
0x180008415  call    ?GetHostApis@ConnectionSessionInfo@Peer@EapHost@@QEAA?AV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@XZ; EapHost::Peer::ConnectionSessionInfo::GetHostApis(void)
0x18000841a  mov     rsi, [rax]
0x18000841d  test    rsi, rsi
0x180008420  jz      short loc_18000843C
0x180008422  mov     rax, [rsi]
0x180008425  mov     rcx, rsi
0x180008428  mov     rax, [rax+8]
0x18000842c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008431  mov     rbx, rsi
0x180008434  mov     [rsp+998h+var_8F0], rbx
0x18000843c  mov     rcx, [rsp+998h+var_8E8]
0x180008444  test    rcx, rcx
0x180008447  jz      short loc_180008456
0x180008449  mov     rax, [rcx]
0x18000844c  mov     rax, [rax+10h]
0x180008450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008455  nop
0x180008456  mov     r13, rbx
0x180008459  mov     rax, [rbx]
0x18000845c  mov     rsi, [rax+78h]
0x180008460  call    cs:__imp_GetCurrentProcessId
0x180008467  nop     dword ptr [rax+rax+00h]
0x18000846c  mov     rcx, qword ptr [rsp+998h+var_8A8]
0x180008474  movups  xmm0, xmmword ptr [rcx]
0x180008477  movdqu  [rsp+998h+var_8A8], xmm0
0x180008480  lea     rcx, [rsp+998h+var_898]
0x180008488  mov     [rsp+998h+var_920], rcx
0x18000848d  mov     rcx, [rsp+998h+var_890]
0x180008495  mov     [rsp+998h+var_928], rcx
0x18000849a  lea     rcx, [rsp+998h+var_8F8]
0x1800084a2  mov     [rsp+998h+var_930], rcx
0x1800084a7  mov     rcx, [rsp+998h+var_8D8]
0x1800084af  mov     [rsp+998h+var_938], rcx
0x1800084b4  mov     rcx, [rsp+998h+var_8D0]
0x1800084bc  mov     [rsp+998h+var_940], rcx
0x1800084c1  mov     rcx, [rsp+998h+var_8C8]
0x1800084c9  mov     [rsp+998h+var_948], rcx
0x1800084ce  mov     rcx, [rsp+998h+var_888]
0x1800084d6  mov     [rsp+998h+var_950], rcx
0x1800084db  mov     [rsp+998h+var_958], eax
0x1800084df  mov     rax, [rsp+998h+var_880]
0x1800084e7  mov     [rsp+998h+var_960], rax
0x1800084ec  mov     eax, [rsp+998h+dwSizeofUserData]
0x1800084f3  mov     [rsp+998h+var_968], eax
0x1800084f7  mov     rax, [rsp+998h+var_878]
0x1800084ff  mov     [rsp+998h+var_970], rax
0x180008504  mov     eax, [rsp+998h+var_904]
0x18000850b  mov     dword ptr [rsp+998h+var_978], eax
0x18000850f  lea     r9, [rsp+998h+var_8A8]
0x180008517  mov     r8d, [rsp+998h+var_908]
0x18000851f  xor     edx, edx
0x180008521  mov     rcx, rbx
0x180008524  mov     rax, rsi
0x180008527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000852c  mov     esi, eax
0x18000852e  test    eax, eax
0x180008530  jns     short loc_18000856A
0x180008532  mov     rcx, cs:WPP_GLOBAL_Control
0x180008539  cmp     rcx, r12
0x18000853c  jz      short loc_18000855D
0x18000853e  test    byte ptr [rcx+1Ch], 4
0x180008542  jz      short loc_18000855D
0x180008544  mov     edx, 15h
0x180008549  mov     r9d, eax
0x18000854c  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x180008553  mov     rcx, [rcx+10h]
0x180008557  call    WPP_SF_d
0x18000855c  nop
0x18000855d  mov     r13, [rsp+998h+var_8B8]
0x180008565  jmp     loc_1800085FD
0x18000856a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008571  cmp     rcx, r12
0x180008574  jz      short loc_180008592
0x180008576  test    byte ptr [rcx+1Ch], 4
0x18000857a  jz      short loc_180008592
0x18000857c  mov     edx, 16h
0x180008581  mov     r9, [rsp+998h+var_8F8]
0x180008589  mov     rcx, [rcx+10h]
0x18000858d  call    WPP_SF_S
0x180008592  mov     rax, [rsp+998h+var_8F8]
0x18000859a  mov     rcx, [rsp+998h+var_8C0]
0x1800085a2  mov     [rcx], rax
0x1800085a5  test    r13, r13
0x1800085a8  jz      short loc_1800085C6
0x1800085aa  mov     rbx, r14
0x1800085ad  mov     [rsp+998h+var_8F0], rbx
0x1800085b5  mov     rax, [r13+0]
0x1800085b9  mov     rcx, r13
0x1800085bc  mov     rax, [rax+10h]
0x1800085c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085c5  nop
0x1800085c6  mov     r13, [rsp+998h+var_8B8]
0x1800085ce  jmp     short loc_1800085FD
0x1800085d0  xor     r14d, r14d
0x1800085d3  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800085d7  lea     r12, WPP_GLOBAL_Control
0x1800085de  mov     rdi, [rsp+998h+var_900]
0x1800085e6  mov     rbx, [rsp+998h+var_8F0]
0x1800085ee  mov     esi, [rsp+998h+var_908]
0x1800085f5  mov     r13, [rsp+998h+var_8E0]
0x1800085fd  lea     rdx, DebugInfoEvent
0x180008604  mov     rcx, cs:eaphost_Context
0x18000860b  call    cs:__imp_EtwEventEnabled
0x180008612  nop     dword ptr [rax+rax+00h]
0x180008617  test    al, al
0x180008619  jz      loc_1800086A2
0x18000861f  mov     r9d, esi
0x180008622  lea     r8, aEaphostpeerget_14; "EapHostPeerGetIdentity Exit:\n returned"...
0x180008629  mov     edx, 800h; unsigned __int64
0x18000862e  lea     rcx, [rsp+998h+var_848]; char *
0x180008636  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000863b  test    eax, eax
0x18000863d  js      short loc_1800086A2
0x18000863f  cmp     cs:Microsoft_Windows_EapHostEnableBits, r14b
0x180008646  jge     short loc_1800086A2
0x180008648  lea     rax, [rsp+998h+var_848]
0x180008650  inc     r15
0x180008653  cmp     [rax+r15], r14b
0x180008657  jnz     short loc_180008650
0x180008659  lea     eax, [r15+1]
0x18000865d  lea     rcx, [rsp+998h+var_848]
0x180008665  mov     [rsp+998h+var_860], rcx
0x18000866d  mov     dword ptr [rsp+998h+var_858], eax
0x180008674  mov     dword ptr [rsp+998h+var_858+4], r14d
0x18000867c  lea     rax, [rsp+998h+var_870]
0x180008684  mov     [rsp+998h+var_978], rax
0x180008689  mov     r9d, 2
0x18000868f  lea     rdx, DebugInfoEvent
0x180008696  lea     rcx, eaphost_Context
0x18000869d  call    McGenEventWrite_EtwEventWriteTransfer
0x1800086a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086a9  cmp     rcx, r12
0x1800086ac  jz      short loc_1800086CC
0x1800086ae  test    byte ptr [rcx+1Ch], 4
0x1800086b2  jz      short loc_1800086CC
0x1800086b4  mov     edx, 18h
  ... truncated ...
```

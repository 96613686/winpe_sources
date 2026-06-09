# EapHostPeerBeginSession

- ea: `0x180006100`
- end: `0x1800069cd`
- name: `EapHostPeerBeginSession`
- size: `2253`
- prototype: `DWORD __stdcall(DWORD dwFlags, EAP_METHOD_TYPE *__struct_ptr eapType, const EapAttributes *const pAttributeArray, HANDLE hTokenImpersonateUser, DWORD dwSizeofConnectionData, const BYTE *const pConnectionData, DWORD dwSizeofUserData, const BYTE *const pUserData, DWORD dwMaxSendPacketSize, const GUID *const pConnectionId, NotificationHandler func, void *pContextData, EAP_SESSIONID *pSessionId, EAP_ERROR **ppEapError)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x180005450`
- `0x1800059c4`
- `0x180006100`
- `0x180007090`
- `0x18000ace0`
- `0x18000adb4`
- `0x18000aeb8`
- `0x18000b088`
- `0x18000b8bc`
- `0x18000bac0`
- `0x18000c204`
- `0x18000c6e0`
- `0x18000c720`
- `0x18000c7d0`
- `0x18000d1dc`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000627c`
- `ntdll!EtwEventEnabled` at `0x180006741`
- `ntdll!EtwEventEnabled` at `0x18000627c`
- `ntdll!EtwEventEnabled` at `0x180006741`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006727`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006727`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000650f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000650f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800061fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800061fc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006613`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006613`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
DWORD __stdcall EapHostPeerBeginSession(
        DWORD dwFlags,
        EAP_METHOD_TYPE *eapType,
        const EapAttributes *const pAttributeArray,
        HANDLE hTokenImpersonateUser,
        DWORD dwSizeofConnectionData,
        const BYTE *const pConnectionData,
        DWORD dwSizeofUserData,
        const BYTE *const pUserData,
        DWORD dwMaxSendPacketSize,
        const GUID *const pConnectionId,
        NotificationHandler func,
        void *pContextData,
        EAP_SESSIONID *pSessionId,
        EAP_ERROR **ppEapError)
{
  EapHost::Peer::ConnectionSessionInfo *v15; // r15
  __int64 v16; // rbx
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rax
  int v19; // r8d
  DWORD dwNumberOfAttributes; // ecx
  EAP_METHOD_TYPE *v21; // rdi
  int v22; // r8d
  __int64 v23; // r13
  __int64 v24; // rax
  _BYTE *v25; // rcx
  __int64 v26; // rdx
  signed int v27; // edi
  __int64 v28; // rdx
  _QWORD *HostApis; // rax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _QWORD, EAP_METHOD_TYPE *, const EapAttributes *, DWORD, HANDLE, DWORD, const BYTE *, DWORD, const BYTE *, DWORD, const GUID *const, unsigned int *, __int64 *, EAP_ERROR **); // rdi
  DWORD CurrentProcessId; // eax
  GUID *v33; // rcx
  GUID *v34; // rax
  struct EapHost::Peer::ConnectionSessionInfo *v35; // rdx
  char v36; // r14
  _BOOL8 v37; // r8
  EapHost::Peer::PeerProxy *v38; // rcx
  LPWSTR lpBuffer; // [rsp+20h] [rbp-1168h]
  char v41; // [rsp+80h] [rbp-1108h]
  char v42; // [rsp+81h] [rbp-1107h]
  char v43; // [rsp+82h] [rbp-1106h]
  unsigned int v44; // [rsp+84h] [rbp-1104h] BYREF
  EAP_ERROR *pEapError; // [rsp+88h] [rbp-1100h] BYREF
  EapHost::Peer::ConnectionSessionInfo *v46; // [rsp+90h] [rbp-10F8h] BYREF
  EAP_METHOD_TYPE *v47; // [rsp+98h] [rbp-10F0h]
  EapHost::Peer::ConnectionSessionInfo *v48; // [rsp+A0h] [rbp-10E8h]
  EAP_SESSIONID *v49; // [rsp+A8h] [rbp-10E0h]
  EAP_ERROR **v50; // [rsp+B0h] [rbp-10D8h]
  const EapAttributes *v51; // [rsp+B8h] [rbp-10D0h]
  __int64 v52; // [rsp+C0h] [rbp-10C8h]
  unsigned __int64 v53; // [rsp+C8h] [rbp-10C0h]
  EAP_METHOD_TYPE v54; // [rsp+D0h] [rbp-10B8h] BYREF
  GUID v55; // [rsp+E0h] [rbp-10A8h] BYREF
  void **v56; // [rsp+F0h] [rbp-1098h] BYREF
  __int64 v57; // [rsp+F8h] [rbp-1090h] BYREF
  const BYTE *v58; // [rsp+100h] [rbp-1088h]
  const BYTE *v59; // [rsp+108h] [rbp-1080h]
  HANDLE v60; // [rsp+110h] [rbp-1078h]
  const GUID *v61; // [rsp+118h] [rbp-1070h]
  _BYTE v62[16]; // [rsp+120h] [rbp-1068h] BYREF
  char *v63; // [rsp+130h] [rbp-1058h]
  __int64 v64; // [rsp+138h] [rbp-1050h]
  char v65[2048]; // [rsp+140h] [rbp-1048h] BYREF
  WCHAR Buffer[1024]; // [rsp+940h] [rbp-848h] BYREF

  v60 = hTokenImpersonateUser;
  v51 = pAttributeArray;
  v47 = eapType;
  LODWORD(pEapError) = dwFlags;
  v59 = pConnectionData;
  v58 = pUserData;
  v61 = pConnectionId;
  v49 = pSessionId;
  v50 = ppEapError;
  v44 = 0;
  v56 = &ObjectHandle::`vftable';
  v57 = 0;
  v42 = 0;
  v43 = 0;
  v15 = 0;
  v48 = 0;
  v16 = 0;
  v52 = 0;
  v46 = 0;
  v17 = (unsigned __int64)GetCurrentThreadId() << 32;
  v18 = v17 | GetTickCount();
  v53 = v18;
  *(_QWORD *)&v55.Data1 = v18;
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    *(_QWORD *)&v54.eapType.type = v18;
    v63 = (char *)&v54;
    v64 = 8;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)BeginSessionStart,
      v19,
      2,
      (__int64)v62);
  }
  if ( !(unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    v21 = v47;
LABEL_12:
    v23 = -1;
    goto LABEL_13;
  }
  dwNumberOfAttributes = 0;
  if ( pAttributeArray )
    dwNumberOfAttributes = pAttributeArray->dwNumberOfAttributes;
  v21 = v47;
  if ( (int)StringCchPrintfA(
              v65,
              0x800u,
              "EapHostPeerBeginSession Entry:\n"
              " flags(0x%x), eapType(authorId=%d, vendorId=%d, vendorType=%d, type=%d),# of attributes(%d), conn data (%d"
              ") bytes, user data(%d) bytes,max packet size (%d)",
              (_DWORD)pEapError,
              v47->dwAuthorId,
              v47->eapType.dwVendorId,
              v47->eapType.dwVendorType,
              v47->eapType.type,
              dwNumberOfAttributes,
              dwSizeofConnectionData,
              dwSizeofUserData,
              dwMaxSendPacketSize) < 0 )
    goto LABEL_12;
  v23 = -1;
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v24 = -1;
    do
      ++v24;
    while ( v65[v24] );
    v63 = v65;
    v64 = (unsigned int)(v24 + 1);
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v22,
      2,
      (__int64)v62);
  }
LABEL_13:
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v26 = 0;
    if ( v51 )
      v26 = v51->dwNumberOfAttributes;
    WPP_SF_Ddddddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v26,
      dwSizeofConnectionData,
      (unsigned int)pEapError,
      v21->dwAuthorId,
      v21->eapType.dwVendorId,
      v21->eapType.dwVendorType,
      v21->eapType.type,
      v26,
      dwSizeofConnectionData,
      dwSizeofUserData,
      dwMaxSendPacketSize);
    v25 = WPP_GLOBAL_Control;
  }
  if ( !pSessionId )
  {
    v27 = 160;
    v36 = 1;
    goto LABEL_50;
  }
  v41 = 0;
  if ( v50 )
  {
    *v50 = 0;
    v25 = WPP_GLOBAL_Control;
  }
  if ( func )
  {
    if ( v25 != (_BYTE *)&WPP_GLOBAL_Control && (v25[28] & 4) != 0 )
    {
      v28 = 16;
      goto LABEL_29;
    }
  }
  else if ( v25 != (_BYTE *)&WPP_GLOBAL_Control && (v25[28] & 4) != 0 )
  {
    v28 = 15;
LABEL_29:
    WPP_SF_(*((_QWORD *)v25 + 2), v28, WPP_e9255469090b376a053f3594056fdc10_Traceguids);
  }
  *pSessionId = 0;
  v27 = EapHost::Peer::ConnectionSessionInfo::CreateInstance(&v46, HIDWORD(qword_180015528));
  if ( v27 >= 0 )
  {
    v15 = v46;
    v48 = v46;
    HostApis = (_QWORD *)EapHost::Peer::ConnectionSessionInfo::GetHostApis(v46, &v54);
    v30 = *HostApis;
    if ( *HostApis )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v30 + 8LL))(*HostApis);
      v16 = v30;
      v52 = v30;
    }
    if ( *(_QWORD *)&v54.eapType.type )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v54.eapType.type + 16LL))(*(_QWORD *)&v54.eapType.type);
    v31 = *(__int64 (__fastcall **)(__int64, _QWORD, EAP_METHOD_TYPE *, const EapAttributes *, DWORD, HANDLE, DWORD, const BYTE *, DWORD, const BYTE *, DWORD, const GUID *const, unsigned int *, __int64 *, EAP_ERROR **))(*(_QWORD *)v16 + 24LL);
    ObjectHandle::Clear((ObjectHandle *)&v56);
    CurrentProcessId = GetCurrentProcessId();
    v54 = *v47;
    v27 = v31(
            v16,
            (unsigned int)pEapError,
            &v54,
            v51,
            CurrentProcessId,
            v60,
            dwSizeofConnectionData,
            v59,
            dwSizeofUserData,
            v58,
            dwMaxSendPacketSize,
            pConnectionId,
            &v44,
            &v57,
            v50);
    if ( v27 >= 0 )
    {
      v36 = 1;
      v42 = 1;
      *(_DWORD *)v15 = v44;
      v33 = (GUID *)((char *)v15 + 4);
      v34 = &GUID_NULL;
      if ( pConnectionId )
        v34 = (GUID *)pConnectionId;
      *v33 = *v34;
      StringFromGUID2(v33, (LPOLESTR)v15 + 10, 39);
      *((_QWORD *)v15 + 17) = func;
      *((_QWORD *)v15 + 18) = pContextData;
      if ( pConnectionId
        && (*(_QWORD *)&pConnectionId->Data1 != *(_QWORD *)&GUID_NULL.Data1
         || *(_QWORD *)pConnectionId->Data4 != *(_QWORD *)GUID_NULL.Data4)
        && func )
      {
        v41 = 1;
        _InterlockedAdd((volatile signed __int32 *)v15 + 42, 1u);
      }
      v27 = EapHost::Peer::PeerProxy::AddSession(
              (EapHost::Peer::PeerProxy *)func,
              (struct EapHost::Peer::ConnectionSessionInfoPtr *)&v46);
      if ( v27 )
      {
        EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(v15);
      }
      else
      {
        v43 = 1;
        if ( !v41 || (v27 = EapHost::Peer::WaitForNotification(v15, v35)) == 0 )
          *v49 = v44;
      }
    }
    else
    {
      v36 = 1;
    }
  }
  else
  {
    v36 = 1;
  }
LABEL_50:
  FormatMessageW(0x1200u, 0, v27, 0, Buffer, 0x400u, 0);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    LODWORD(lpBuffer) = v44;
    if ( (int)StringCchPrintfA(
                v65,
                0x800u,
                "EapHostPeerBeginSession Exit:\n %ws\nReturned session(%d).",
                Buffer,
                lpBuffer) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v23;
      while ( v65[v23] );
      v63 = v65;
      v64 = (unsigned int)(v23 + 1);
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v37,
        2,
        (__int64)v62);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v37, (unsigned int)v27, v44);
  if ( v15 )
    _InterlockedCompareExchange((volatile signed __int32 *)v15 + 43, 0, *((_DWORD *)v15 + 43));
  if ( v27 )
  {
    pEapError = 0;
    if ( !pConnectionId
      || *(_QWORD *)&pConnectionId->Data1 == *(_QWORD *)&GUID_NULL.Data1
      && *(_QWORD *)pConnectionId->Data4 == *(_QWORD *)GUID_NULL.Data4 )
    {
      v36 = 0;
    }
    v38 = (EapHost::Peer::PeerProxy *)v49;
    if ( v49 )
      *v49 = 0;
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, EAP_ERROR **))(*(_QWORD *)v16 + 96LL))(
        v16,
        *(unsigned int *)v38,
        &pEapError);
      EapHostPeerFreeEapError(pEapError);
      if ( v36 )
      {
        v55 = *pConnectionId;
        (*(void (__fastcall **)(__int64, GUID *, EAP_ERROR **))(*(_QWORD *)v16 + 112LL))(v16, &v55, &pEapError);
        EapHostPeerFreeEapError(pEapError);
      }
    }
    if ( v43 )
    {
      if ( v36 )
        EapHost::Peer::PeerProxy::RemoveSession(v38, pConnectionId, v37);
      else
        EapHost::Peer::PeerProxy::RemoveSessionIfNoConnId(v38, v44);
    }
  }
  if ( Microsoft_Windows_EapHostEnableBits < 0 )
  {
    *(_QWORD *)&v55.Data1 = v53;
    v63 = (char *)&v55;
    v64 = 8;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)BeginSessionEnd,
      v37,
      2,
      (__int64)v62);
  }
  if ( v46 )
    EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(v46);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  v56 = &ObjectHandle::`vftable';
  ObjectHandle::Clear((ObjectHandle *)&v56);
  return v27;
}

```

## disassembly

```asm
0x180006100  push    rbx
0x180006102  push    rsi
0x180006103  push    rdi
0x180006104  push    r12
0x180006106  push    r13
0x180006108  push    r14
0x18000610a  push    r15
0x18000610c  mov     eax, 1150h
0x180006111  call    _alloca_probe
0x180006116  sub     rsp, rax
0x180006119  mov     rax, cs:__security_cookie
0x180006120  xor     rax, rsp
0x180006123  mov     [rsp+1188h+var_48], rax
0x18000612b  mov     [rsp+1188h+var_1078], r9
0x180006133  mov     r13, r8
0x180006136  mov     [rsp+1188h+var_10D0], r8
0x18000613e  mov     [rsp+1188h+var_10F0], rdx
0x180006146  mov     dword ptr [rsp+1188h+pEapError], ecx
0x18000614d  mov     r12, [rsp+1188h+pConnectionId]
0x180006155  mov     rax, [rsp+1188h+pConnectionData]
0x18000615d  mov     [rsp+1188h+var_1080], rax
0x180006165  mov     rax, [rsp+1188h+pUserData]
0x18000616d  mov     [rsp+1188h+var_1088], rax
0x180006175  mov     [rsp+1188h+var_1070], r12
0x18000617d  mov     r14, [rsp+1188h+pSessionId]
0x180006185  mov     [rsp+1188h+var_10E0], r14
0x18000618d  mov     rax, [rsp+1188h+ppEapError]
0x180006195  mov     [rsp+1188h+var_10D8], rax
0x18000619d  xor     esi, esi
0x18000619f  mov     [rsp+1188h+var_1104], esi
0x1800061a6  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x1800061ad  mov     [rsp+1188h+var_1098], rax
0x1800061b5  mov     [rsp+1188h+var_1090], rsi
0x1800061bd  mov     [rsp+1188h+var_1107], sil
0x1800061c5  mov     [rsp+1188h+var_1106], sil
0x1800061cd  mov     r15d, esi
0x1800061d0  mov     [rsp+1188h+var_10E8], rsi
0x1800061d8  mov     ebx, esi
0x1800061da  mov     [rsp+1188h+var_10C8], rbx
0x1800061e2  mov     [rsp+1188h+var_10F8], rsi
0x1800061ea  call    cs:__imp_GetCurrentThreadId
0x1800061f1  nop     dword ptr [rax+rax+00h]
0x1800061f6  mov     edi, eax
0x1800061f8  shl     rdi, 20h
0x1800061fc  call    cs:__imp_GetTickCount
0x180006203  nop     dword ptr [rax+rax+00h]
0x180006208  mov     eax, eax
0x18000620a  or      rax, rdi
0x18000620d  mov     [rsp+1188h+var_10C0], rax
0x180006215  mov     qword ptr [rsp+1188h+var_10A8], rax
0x18000621d  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x180006224  jge     short loc_18000626E
0x180006226  mov     qword ptr [rsp+1188h+var_10B8], rax
0x18000622e  lea     rax, [rsp+1188h+var_10B8]
0x180006236  mov     [rsp+1188h+var_1058], rax
0x18000623e  mov     [rsp+1188h+var_1050], 8
0x18000624a  lea     rax, [rsp+1188h+var_1068]
0x180006252  mov     [rsp+1188h+lpBuffer], rax
0x180006257  lea     r9d, [rsi+2]
0x18000625b  lea     rdx, BeginSessionStart
0x180006262  lea     rcx, eaphost_Context
0x180006269  call    McGenEventWrite_EtwEventWriteTransfer
0x18000626e  lea     rdx, DebugInfoEvent
0x180006275  mov     rcx, cs:eaphost_Context
0x18000627c  call    cs:__imp_EtwEventEnabled
0x180006283  nop     dword ptr [rax+rax+00h]
0x180006288  test    al, al
0x18000628a  jz      loc_180006372
0x180006290  test    r13, r13
0x180006293  mov     ecx, esi
0x180006295  jz      short loc_18000629B
0x180006297  mov     ecx, [r13+0]
0x18000629b  mov     rdi, [rsp+1188h+var_10F0]
0x1800062a3  movzx   eax, byte ptr [rdi]
0x1800062a6  mov     edx, [rsp+1188h+dwMaxSendPacketSize]
0x1800062ad  mov     dword ptr [rsp+1188h+var_1130], edx
0x1800062b1  mov     edx, [rsp+1188h+dwSizeofUserData]
0x1800062b8  mov     [rsp+1188h+var_1138], edx
0x1800062bc  mov     edx, [rsp+1188h+dwSizeofConnectionData]
0x1800062c3  mov     dword ptr [rsp+1188h+var_1140], edx
0x1800062c7  mov     [rsp+1188h+var_1148], ecx
0x1800062cb  mov     dword ptr [rsp+1188h+var_1150], eax
0x1800062cf  mov     eax, [rdi+8]
0x1800062d2  mov     dword ptr [rsp+1188h+Arguments], eax
0x1800062d6  mov     eax, [rdi+4]
0x1800062d9  mov     [rsp+1188h+nSize], eax
0x1800062dd  mov     eax, [rdi+0Ch]
0x1800062e0  mov     dword ptr [rsp+1188h+lpBuffer], eax
0x1800062e4  mov     r9d, dword ptr [rsp+1188h+pEapError]
0x1800062ec  lea     r8, aEaphostpeerbeg_1; "EapHostPeerBeginSession Entry:\n flags("...
0x1800062f3  mov     edx, 800h; unsigned __int64
0x1800062f8  lea     rcx, [rsp+1188h+var_1048]; char *
0x180006300  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180006305  test    eax, eax
0x180006307  js      short loc_18000637A
0x180006309  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000630d  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x180006314  jge     short loc_18000637E
0x180006316  lea     rcx, [rsp+1188h+var_1048]
0x18000631e  mov     rax, r13
0x180006321  inc     rax
0x180006324  cmp     [rcx+rax], sil
0x180006328  jnz     short loc_180006321
0x18000632a  inc     eax
0x18000632c  lea     rcx, [rsp+1188h+var_1048]
0x180006334  mov     [rsp+1188h+var_1058], rcx
0x18000633c  mov     dword ptr [rsp+1188h+var_1050], eax
0x180006343  mov     dword ptr [rsp+1188h+var_1050+4], esi
0x18000634a  lea     rax, [rsp+1188h+var_1068]
0x180006352  mov     [rsp+1188h+lpBuffer], rax
0x180006357  mov     r9d, 2
0x18000635d  lea     rdx, DebugInfoEvent
0x180006364  lea     rcx, eaphost_Context
0x18000636b  call    McGenEventWrite_EtwEventWriteTransfer
0x180006370  jmp     short loc_18000637E
0x180006372  mov     rdi, [rsp+1188h+var_10F0]
0x18000637a  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000637e  lea     rax, WPP_GLOBAL_Control
0x180006385  mov     rcx, cs:WPP_GLOBAL_Control
0x18000638c  cmp     rcx, rax
0x18000638f  jz      short loc_18000640E
0x180006391  test    byte ptr [rcx+1Ch], 4
0x180006395  jz      short loc_18000640E
0x180006397  mov     rax, [rsp+1188h+var_10D0]
0x18000639f  test    rax, rax
0x1800063a2  mov     edx, esi
0x1800063a4  jz      short loc_1800063A8
0x1800063a6  mov     edx, [rax]
0x1800063a8  movzx   eax, byte ptr [rdi]
0x1800063ab  mov     r8d, [rsp+1188h+dwMaxSendPacketSize]
0x1800063b3  mov     dword ptr [rsp+1188h+var_1130], r8d
0x1800063b8  mov     r8d, [rsp+1188h+dwSizeofUserData]
0x1800063c0  mov     [rsp+1188h+var_1138], r8d
0x1800063c5  mov     r8d, [rsp+1188h+dwSizeofConnectionData]
0x1800063cd  mov     dword ptr [rsp+1188h+var_1140], r8d
0x1800063d2  mov     [rsp+1188h+var_1148], edx
0x1800063d6  mov     dword ptr [rsp+1188h+var_1150], eax
0x1800063da  mov     eax, [rdi+8]
0x1800063dd  mov     dword ptr [rsp+1188h+Arguments], eax
0x1800063e1  mov     eax, [rdi+4]
0x1800063e4  mov     [rsp+1188h+nSize], eax
0x1800063e8  mov     eax, [rdi+0Ch]
0x1800063eb  mov     dword ptr [rsp+1188h+lpBuffer], eax
0x1800063ef  mov     r9d, dword ptr [rsp+1188h+pEapError]
0x1800063f7  mov     rcx, [rcx+10h]
0x1800063fb  call    WPP_SF_Ddddddddd
0x180006400  mov     rcx, cs:WPP_GLOBAL_Control
0x180006407  lea     rax, WPP_GLOBAL_Control
0x18000640e  test    r14, r14
0x180006411  jnz     short loc_18000641D
0x180006413  mov     edi, 0A0h
0x180006418  jmp     loc_1800066FA
0x18000641d  mov     [rsp+1188h+var_1108], sil
0x180006425  mov     rdx, [rsp+1188h+var_10D8]
0x18000642d  test    rdx, rdx
0x180006430  jz      short loc_18000643C
0x180006432  mov     [rdx], rsi
0x180006435  mov     rcx, cs:WPP_GLOBAL_Control
0x18000643c  cmp     [rsp+1188h+func], rsi
0x180006444  jnz     short loc_180006458
0x180006446  cmp     rcx, rax
0x180006449  jz      short loc_180006478
0x18000644b  test    byte ptr [rcx+1Ch], 4
0x18000644f  jz      short loc_180006478
0x180006451  mov     edx, 0Fh
0x180006456  jmp     short loc_180006468
0x180006458  cmp     rcx, rax
0x18000645b  jz      short loc_180006478
0x18000645d  test    byte ptr [rcx+1Ch], 4
0x180006461  jz      short loc_180006478
0x180006463  mov     edx, 10h
0x180006468  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x18000646f  mov     rcx, [rcx+10h]
0x180006473  call    WPP_SF_
0x180006478  mov     [r14], esi
0x18000647b  mov     edx, dword ptr cs:qword_180015528+4; unsigned int
0x180006481  lea     rcx, [rsp+1188h+var_10F8]; struct EapHost::Peer::ConnectionSessionInfoPtr *
0x180006489  call    ?CreateInstance@ConnectionSessionInfo@Peer@EapHost@@SAJAEAVConnectionSessionInfoPtr@23@K@Z; EapHost::Peer::ConnectionSessionInfo::CreateInstance(EapHost::Peer::ConnectionSessionInfoPtr &,ulong)
0x18000648e  mov     edi, eax
0x180006490  test    eax, eax
0x180006492  jns     short loc_18000649F
0x180006494  mov     r14d, 1
0x18000649a  jmp     loc_180006700
0x18000649f  mov     r15, [rsp+1188h+var_10F8]
0x1800064a7  mov     [rsp+1188h+var_10E8], r15
0x1800064af  lea     rdx, [rsp+1188h+var_10B8]
0x1800064b7  mov     rcx, r15
0x1800064ba  call    ?GetHostApis@ConnectionSessionInfo@Peer@EapHost@@QEAA?AV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@XZ; EapHost::Peer::ConnectionSessionInfo::GetHostApis(void)
0x1800064bf  mov     rdi, [rax]
0x1800064c2  test    rdi, rdi
0x1800064c5  jz      short loc_1800064E1
0x1800064c7  mov     rax, [rdi]
0x1800064ca  mov     rcx, rdi
0x1800064cd  mov     rax, [rax+8]
0x1800064d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064d6  mov     rbx, rdi
0x1800064d9  mov     [rsp+1188h+var_10C8], rbx
0x1800064e1  mov     rcx, qword ptr [rsp+1188h+var_10B8]
0x1800064e9  test    rcx, rcx
0x1800064ec  jz      short loc_1800064FB
0x1800064ee  mov     rax, [rcx]
0x1800064f1  mov     rax, [rax+10h]
0x1800064f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064fa  nop
0x1800064fb  mov     rax, [rbx]
0x1800064fe  mov     rdi, [rax+18h]
0x180006502  lea     rcx, [rsp+1188h+var_1098]; this
0x18000650a  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000650f  call    cs:__imp_GetCurrentProcessId
0x180006516  nop     dword ptr [rax+rax+00h]
0x18000651b  mov     rdx, [rsp+1188h+var_10F0]
0x180006523  movups  xmm0, xmmword ptr [rdx]
0x180006526  movdqu  [rsp+1188h+var_10B8], xmm0
0x18000652f  mov     rcx, [rsp+1188h+var_10D8]
0x180006537  mov     [rsp+1188h+var_1118], rcx
0x18000653c  lea     rcx, [rsp+1188h+var_1090]
0x180006544  mov     [rsp+1188h+var_1120], rcx
0x180006549  lea     rcx, [rsp+1188h+var_1104]
0x180006551  mov     [rsp+1188h+var_1128], rcx
0x180006556  mov     [rsp+1188h+var_1130], r12
0x18000655b  mov     ecx, [rsp+1188h+dwMaxSendPacketSize]
0x180006562  mov     [rsp+1188h+var_1138], ecx
0x180006566  mov     rcx, [rsp+1188h+var_1088]
0x18000656e  mov     [rsp+1188h+var_1140], rcx
0x180006573  mov     ecx, [rsp+1188h+dwSizeofUserData]
0x18000657a  mov     [rsp+1188h+var_1148], ecx
0x18000657e  mov     rcx, [rsp+1188h+var_1080]
0x180006586  mov     [rsp+1188h+var_1150], rcx
0x18000658b  mov     ecx, [rsp+1188h+dwSizeofConnectionData]
0x180006592  mov     dword ptr [rsp+1188h+Arguments], ecx
0x180006596  mov     rcx, [rsp+1188h+var_1078]
0x18000659e  mov     qword ptr [rsp+1188h+nSize], rcx
0x1800065a3  mov     dword ptr [rsp+1188h+lpBuffer], eax
0x1800065a7  mov     r9, [rsp+1188h+var_10D0]
0x1800065af  lea     r8, [rsp+1188h+var_10B8]
0x1800065b7  mov     edx, dword ptr [rsp+1188h+pEapError]
0x1800065be  mov     rcx, rbx
0x1800065c1  mov     rax, rdi
0x1800065c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065c9  mov     edi, eax
0x1800065cb  test    eax, eax
0x1800065cd  jns     short loc_1800065DA
0x1800065cf  mov     r14d, 1
0x1800065d5  jmp     loc_180006700
0x1800065da  mov     r14d, 1
0x1800065e0  mov     [rsp+1188h+var_1107], r14b
0x1800065e8  mov     eax, [rsp+1188h+var_1104]
0x1800065ef  mov     [r15], eax
0x1800065f2  lea     rcx, [r15+4]; rguid
0x1800065f6  lea     rax, GUID_NULL
0x1800065fd  test    r12, r12
0x180006600  cmovnz  rax, r12
0x180006604  movups  xmm0, xmmword ptr [rax]
0x180006607  movdqu  xmmword ptr [rcx], xmm0
0x18000660b  lea     rdx, [r15+14h]; lpsz
0x18000660f  lea     r8d, [r14+26h]; cchMax
0x180006613  call    cs:__imp_StringFromGUID2
0x18000661a  nop     dword ptr [rax+rax+00h]
0x18000661f  mov     rcx, [rsp+1188h+func]; this
0x180006627  mov     [r15+88h], rcx
0x18000662e  mov     rax, [rsp+1188h+pContextData]
0x180006636  mov     [r15+90h], rax
0x18000663d  test    r12, r12
0x180006640  jz      short loc_180006672
0x180006642  mov     rax, [r12]
0x180006646  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18000664d  jnz     short loc_18000665D
0x18000664f  mov     rax, [r12+8]
0x180006654  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18000665b  jz      short loc_180006672
0x18000665d  test    rcx, rcx
0x180006660  jz      short loc_180006672
0x180006662  mov     [rsp+1188h+var_1108], r14b
0x18000666a  lock add [r15+0A8h], r14d
0x180006672  lea     rdx, [rsp+1188h+var_10F8]; struct EapHost::Peer::ConnectionSessionInfoPtr *
0x18000667a  call    ?AddSession@PeerProxy@Peer@EapHost@@QEAAKAEAVConnectionSessionInfoPtr@23@@Z; EapHost::Peer::PeerProxy::AddSession(EapHost::Peer::ConnectionSessionInfoPtr &)
0x18000667f  mov     edi, eax
0x180006681  test    eax, eax
0x180006683  jz      short loc_180006690
0x180006685  mov     rcx, r15; this
0x180006688  call    ?ReduceRefCount@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ; EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(void)
0x18000668d  nop
0x18000668e  jmp     short loc_180006700
0x180006690  mov     [rsp+1188h+var_1106], r14b
0x180006698  cmp     [rsp+1188h+var_1108], sil
0x1800066a0  jz      short loc_1800066B2
0x1800066a2  mov     rcx, r15; this
0x1800066a5  call    ?WaitForNotification@Peer@EapHost@@YAKPEAVConnectionSessionInfo@12@@Z; EapHost::Peer::WaitForNotification(EapHost::Peer::ConnectionSessionInfo *)
0x1800066aa  mov     edi, eax
0x1800066ac  test    eax, eax
0x1800066ae  jz      short loc_1800066B2
0x1800066b0  jmp     short loc_180006700
0x1800066b2  mov     eax, [rsp+1188h+var_1104]
0x1800066b9  mov     rcx, [rsp+1188h+var_10E0]
0x1800066c1  mov     [rcx], eax
0x1800066c3  jmp     short loc_180006700
0x1800066c5  xor     esi, esi
0x1800066c7  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800066cb  mov     edi, dword ptr [rsp+1188h+pEapError]
0x1800066d2  mov     r15, [rsp+1188h+var_10E8]
  ... truncated ...
```

# ConnectionManager::NetConnectionNotifySinkAdvise(IUnknown *,ulong *)

- ea: `0x18001bb00`
- end: `0x18001bffd`
- name: `?NetConnectionNotifySinkAdvise@ConnectionManager@@EEAAJPEAUIUnknown@@PEAK@Z`
- size: `1277`
- prototype: `__int64 __fastcall(ConnectionManager *__hidden this, struct IUnknown *, unsigned int *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001710`
- `0x180002320`
- `0x180004340`
- `0x180004580`
- `0x180004d80`
- `0x18000538c`
- `0x180019200`
- `0x180019c68`
- `0x180019e74`
- `0x18001a2b0`
- `0x18001b570`
- `0x18001b764`
- `0x18001bb00`
- `0x18001dda4`
- `0x18001de50`
- `0x18001f9c4`
- `0x18003060c`
- `0x180030a00`
- `0x180030a50`
- `0x180036010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001bebd`
- `KERNEL32!LeaveCriticalSection` at `0x18001bebd`
- `KERNEL32!EnterCriticalSection` at `0x18001be96`
- `KERNEL32!EnterCriticalSection` at `0x18001be96`
- `USER32!RegisterDeviceNotificationW` at `0x18001bf4e`
- `USER32!RegisterDeviceNotificationW` at `0x18001bf4e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001bbc3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001bc52`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001bbc3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001bc52`
- `SspiCli!GetUserNameExW` at `0x18001be1a`
- `SspiCli!GetUserNameExW` at `0x18001be1a`
- `SHELL32!SHGetFolderPathW` at `0x18001bd46`
- `SHELL32!SHGetFolderPathW` at `0x18001bd46`

## pseudocode

```c
__int64 __fastcall ConnectionManager::NetConnectionNotifySinkAdvise(
        ConnectionManager *this,
        struct IUnknown *a2,
        unsigned int *a3)
{
  __int64 result; // rax
  HRESULT v6; // edi
  unsigned int v7; // eax
  PVOID *v8; // rcx
  HRESULT v9; // eax
  HRESULT v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  _DWORD *v13; // rax
  _DWORD *v14; // rsi
  HRESULT v15; // eax
  __int64 v16; // rax
  PVOID *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // eax
  HDEVNOTIFY v22; // rax
  unsigned int Win32Error; // eax
  IUnknown *pProxy; // [rsp+40h] [rbp-C0h] BYREF
  ULONG nSize[2]; // [rsp+48h] [rbp-B8h] BYREF
  int NotificationFilter; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+5Ch] [rbp-A4h]
  GUID v28; // [rsp+64h] [rbp-9Ch]
  int v29; // [rsp+74h] [rbp-8Ch]
  WCHAR NameBuffer[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPath[264]; // [rsp+290h] [rbp+190h] BYREF

  pProxy = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
  result = HrEnsureEventHandlerInitialized();
  if ( (int)result >= 0 )
  {
    NotificationFilter = 0;
    LODWORD(v27) = 1;
    v28.Data1 = 0;
    v6 = CAutoImpersonate::Impersonate((CAutoImpersonate *)&NotificationFilter);
    if ( v6 < 0 )
    {
LABEL_44:
      CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&NotificationFilter);
      if ( !*((_DWORD *)this + 38) && !_InterlockedExchange((volatile __int32 *)this + 38, 1) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
        v27 = 5;
        v28 = GUID_NDIS_LAN_CLASS;
        v29 = 0;
        NotificationFilter = 32;
        v22 = RegisterDeviceNotificationW(hRecipient, &NotificationFilter, 1u);
        *((_QWORD *)this + 20) = v22;
        if ( !v22 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          Win32Error = HrFromLastWin32Error();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            110,
            &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
            Win32Error);
        }
        ConnectionManager::HrEnsureRegisteredOrDeregisteredWithWmi((ConnectionManager *)((char *)this - 8), 1);
        ConnectionManager::HrEnsureRegisteredOrDeregisteredWithNsi((ConnectionManager *)((char *)this - 8), 1);
      }
      if ( v6 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
          (unsigned int)v6);
      return (unsigned int)v6;
    }
    v7 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
    v6 = v7;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, v7);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 )
    {
      if ( v6 != -2147467262 )
        goto LABEL_20;
    }
    else
    {
      *(_QWORD *)nSize = 0;
      v6 = ((__int64 (__fastcall *)(IUnknown *, GUID *, ULONG *))pProxy->lpVtbl->QueryInterface)(
             pProxy,
             &GUID_faedcf5c_31fe_11d1_aad2_00805fc1270e,
             nSize);
      if ( v6 )
        goto LABEL_19;
      v9 = CoSetProxyBlanket(*(IUnknown **)nSize, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
      v6 = 0;
      if ( v9 != -2147467262 )
        v6 = v9;
      (*(void (**)(void))(**(_QWORD **)nSize + 16LL))();
      if ( v6 )
        goto LABEL_19;
    }
    v10 = ATL::IConnectionPointImpl<ConnectionManager,&_GUID const IID_INetConnectionNotifySink,ATL::CComDynamicUnkArray>::Advise(
            this,
            pProxy,
            a3);
    v6 = v10;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    {
LABEL_23:
      if ( v6 >= 0 )
      {
        v13 = MemAlloc(0x48u);
        v14 = v13;
        if ( v13 )
        {
          memset_0(v13, 0, 0x48u);
          std::wstring::wstring(v14);
          std::wstring::wstring(v14 + 8);
          v14[16] = 0;
          v14[16] = *a3;
          v15 = SHGetFolderPathW(0, 26, 0, 0, pszPath);
          if ( v15 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                105,
                &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
                (unsigned int)v15);
          }
          else
          {
            v16 = std::_WChar_traits<unsigned short>::length(pszPath);
            std::wstring::_Assign<unsigned short>(v14 + 8, pszPath, v16);
            v17 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)pszPath);
                v17 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 )
                WPP_SF_d(v17[2], 104, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, *((unsigned int *)this + 36));
            }
          }
          memset_0(NameBuffer, 0, 0x104u);
          nSize[0] = 260;
          if ( GetUserNameExW(NameSamCompatible, NameBuffer, nSize) && NameBuffer[0] )
          {
            v18 = std::_WChar_traits<unsigned short>::length(NameBuffer);
            std::wstring::_Assign<unsigned short>(v14, NameBuffer, v18);
          }
          else
          {
            v19 = std::_WChar_traits<unsigned short>::length(L"System");
            std::wstring::_Assign<unsigned short>(v14, v20, v19);
            v21 = HrFromLastWin32Error();
            if ( v21 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                106,
                &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
                (unsigned int)v21);
          }
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
          *(_QWORD *)(*(_QWORD *)std::map<IUnknown *,NotifySourceInfo *>::_Try_emplace<IUnknown * const &,>(
                                   (char *)this + 136,
                                   nSize,
                                   &pProxy)
                    + 40LL) = v14;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
        }
        else
        {
          v6 = -2147024882;
        }
      }
      goto LABEL_44;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_qdD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, pProxy, *a3, v10);
LABEL_19:
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_20:
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
      WPP_SF_d(v8[2], 102, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, (unsigned int)v6);
    goto LABEL_23;
  }
  return result;
}

```

## disassembly

```asm
0x18001bb00  push    rbp
0x18001bb02  push    rbx
0x18001bb03  push    rsi
0x18001bb04  push    rdi
0x18001bb05  push    r12
0x18001bb07  push    r14
0x18001bb09  push    r15
0x18001bb0b  lea     rbp, [rsp-3B0h]
0x18001bb13  sub     rsp, 4B0h
0x18001bb1a  mov     rax, cs:__security_cookie
0x18001bb21  xor     rax, rsp
0x18001bb24  mov     [rbp+3E0h+var_40], rax
0x18001bb2b  mov     rbx, r8
0x18001bb2e  mov     [rsp+4E0h+pProxy], rdx
0x18001bb33  mov     r14, rcx
0x18001bb36  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb3d  lea     r12, WPP_GLOBAL_Control
0x18001bb44  cmp     rcx, r12
0x18001bb47  jz      short loc_18001BB64
0x18001bb49  test    byte ptr [rcx+1Ch], 8
0x18001bb4d  jz      short loc_18001BB64
0x18001bb4f  mov     rcx, [rcx+10h]
0x18001bb53  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001bb5a  mov     edx, 63h ; 'c'
0x18001bb5f  call    WPP_SF_
0x18001bb64  call    ?HrEnsureEventHandlerInitialized@@YAJXZ; HrEnsureEventHandlerInitialized(void)
0x18001bb69  xor     r15d, r15d
0x18001bb6c  test    eax, eax
0x18001bb6e  js      loc_18001BFDC
0x18001bb74  lea     esi, [r15+1]
0x18001bb78  mov     [rsp+4E0h+NotificationFilter], r15d
0x18001bb7d  lea     rcx, [rsp+4E0h+NotificationFilter]; this
0x18001bb82  mov     dword ptr [rsp+4E0h+var_484], esi
0x18001bb86  mov     dword ptr [rsp+4E0h+var_47C], r15d
0x18001bb8b  call    ?Impersonate@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::Impersonate(void)
0x18001bb90  mov     edi, eax
0x18001bb92  test    eax, eax
0x18001bb94  js      loc_18001BECF
0x18001bb9a  mov     rcx, [rsp+4E0h+pProxy]; pProxy
0x18001bb9f  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001bba3  mov     [rsp+4E0h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001bbab  xor     r8d, r8d; dwAuthzSvc
0x18001bbae  mov     [rsp+4E0h+pAuthInfo], r15; pAuthInfo
0x18001bbb3  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001bbb6  mov     [rsp+4E0h+dwImpLevel], 3; dwImpLevel
0x18001bbbe  mov     [rsp+4E0h+dwAuthnLevel], r15d; dwAuthnLevel
0x18001bbc3  call    cs:__imp_CoSetProxyBlanket
0x18001bbc9  mov     edi, eax
0x18001bbcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbd2  cmp     rcx, r12
0x18001bbd5  jz      short loc_18001BBFA
0x18001bbd7  test    byte ptr [rcx+1Ch], 8
0x18001bbdb  jz      short loc_18001BBFA
0x18001bbdd  mov     rcx, [rcx+10h]
0x18001bbe1  lea     edx, [rsi+63h]
0x18001bbe4  mov     r9d, eax
0x18001bbe7  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001bbee  call    WPP_SF_d
0x18001bbf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbfa  test    edi, edi
0x18001bbfc  jnz     short loc_18001BC7A
0x18001bbfe  mov     rcx, [rsp+4E0h+pProxy]
0x18001bc03  lea     r8, [rsp+4E0h+nSize]
0x18001bc08  mov     qword ptr [rsp+4E0h+nSize], r15
0x18001bc0d  lea     rdx, _GUID_faedcf5c_31fe_11d1_aad2_00805fc1270e
0x18001bc14  mov     rax, [rcx]
0x18001bc17  mov     rax, [rax]
0x18001bc1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc1f  mov     edi, eax
0x18001bc21  test    eax, eax
0x18001bc23  jnz     loc_18001BCBE
0x18001bc29  mov     rcx, qword ptr [rsp+4E0h+nSize]; pProxy
0x18001bc2e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001bc32  mov     [rsp+4E0h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001bc3a  xor     r8d, r8d; dwAuthzSvc
0x18001bc3d  mov     [rsp+4E0h+pAuthInfo], r15; pAuthInfo
0x18001bc42  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001bc45  mov     [rsp+4E0h+dwImpLevel], 3; dwImpLevel
0x18001bc4d  mov     [rsp+4E0h+dwAuthnLevel], r15d; dwAuthnLevel
0x18001bc52  call    cs:__imp_CoSetProxyBlanket
0x18001bc58  mov     rcx, qword ptr [rsp+4E0h+nSize]
0x18001bc5d  mov     edi, r15d
0x18001bc60  cmp     eax, 80004002h
0x18001bc65  cmovnz  edi, eax
0x18001bc68  mov     rax, [rcx]
0x18001bc6b  mov     rax, [rax+10h]
0x18001bc6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc74  test    edi, edi
0x18001bc76  jz      short loc_18001BC82
0x18001bc78  jmp     short loc_18001BCBE
0x18001bc7a  cmp     edi, 80004002h
0x18001bc80  jnz     short loc_18001BCC5
0x18001bc82  mov     rdx, [rsp+4E0h+pProxy]
0x18001bc87  mov     r8, rbx
0x18001bc8a  mov     rcx, r14
0x18001bc8d  call    ?Advise@?$IConnectionPointImpl@VConnectionManager@@$1?IID_INetConnectionNotifySink@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAUIUnknown@@PEAK@Z; ATL::IConnectionPointImpl<ConnectionManager,&_GUID const IID_INetConnectionNotifySink,ATL::CComDynamicUnkArray>::Advise(IUnknown *,ulong *)
0x18001bc92  mov     edi, eax
0x18001bc94  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc9b  cmp     rcx, r12
0x18001bc9e  jz      short loc_18001BCE8
0x18001bca0  test    byte ptr [rcx+1Ch], 8
0x18001bca4  jz      short loc_18001BCC5
0x18001bca6  mov     r9, [rsp+4E0h+pProxy]
0x18001bcab  mov     rcx, [rcx+10h]
0x18001bcaf  mov     [rsp+4E0h+dwImpLevel], eax
0x18001bcb3  mov     eax, [rbx]
0x18001bcb5  mov     [rsp+4E0h+dwAuthnLevel], eax
0x18001bcb9  call    WPP_SF_qdD
0x18001bcbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcc5  cmp     rcx, r12
0x18001bcc8  jz      short loc_18001BCE8
0x18001bcca  test    byte ptr [rcx+1Ch], 8
0x18001bcce  jz      short loc_18001BCE8
0x18001bcd0  mov     rcx, [rcx+10h]
0x18001bcd4  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001bcdb  mov     edx, 66h ; 'f'
0x18001bce0  mov     r9d, edi
0x18001bce3  call    WPP_SF_d
0x18001bce8  test    edi, edi
0x18001bcea  js      loc_18001BECF
0x18001bcf0  mov     ecx, 48h ; 'H'; unsigned __int64
0x18001bcf5  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18001bcfa  mov     rsi, rax
0x18001bcfd  test    rax, rax
0x18001bd00  jz      loc_18001BEC5
0x18001bd06  xor     edx, edx; Val
0x18001bd08  mov     rcx, rax; void *
0x18001bd0b  lea     r8d, [rdx+48h]; Size
0x18001bd0f  call    memset_0
0x18001bd14  mov     rcx, rsi
0x18001bd17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001bd1c  lea     rcx, [rsi+20h]
0x18001bd20  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001bd25  mov     [rsi+40h], r15d
0x18001bd29  lea     rax, [rbp+3E0h+pszPath]
0x18001bd30  mov     ecx, [rbx]
0x18001bd32  xor     r9d, r9d; dwFlags
0x18001bd35  mov     [rsi+40h], ecx
0x18001bd38  xor     r8d, r8d; hToken
0x18001bd3b  xor     ecx, ecx; hwnd
0x18001bd3d  mov     qword ptr [rsp+4E0h+dwAuthnLevel], rax; pszPath
0x18001bd42  lea     edx, [r9+1Ah]; csidl
0x18001bd46  call    cs:__imp_SHGetFolderPathW
0x18001bd4c  test    eax, eax
0x18001bd4e  js      short loc_18001BDCB
0x18001bd50  lea     rcx, [rbp+3E0h+pszPath]
0x18001bd57  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001bd5c  mov     r8, rax
0x18001bd5f  lea     rcx, [rsi+20h]
0x18001bd63  lea     rdx, [rbp+3E0h+pszPath]
0x18001bd6a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001bd6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd76  cmp     rcx, r12
0x18001bd79  jz      short loc_18001BDF5
0x18001bd7b  test    byte ptr [rcx+1Ch], 8
0x18001bd7f  jz      short loc_18001BDA2
0x18001bd81  mov     r9, [rsp+4E0h+pProxy]
0x18001bd86  lea     rax, [rbp+3E0h+pszPath]
0x18001bd8d  mov     rcx, [rcx+10h]; LoggerHandle
0x18001bd91  mov     qword ptr [rsp+4E0h+dwAuthnLevel], rax; __int64
0x18001bd96  call    WPP_SF_qS
0x18001bd9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bda2  cmp     rcx, r12
0x18001bda5  jz      short loc_18001BDF5
0x18001bda7  test    byte ptr [rcx+1Ch], 8
0x18001bdab  jz      short loc_18001BDF5
0x18001bdad  mov     r9d, [r14+90h]
0x18001bdb4  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001bdbb  mov     rcx, [rcx+10h]
0x18001bdbf  mov     edx, 68h ; 'h'
0x18001bdc4  call    WPP_SF_d
0x18001bdc9  jmp     short loc_18001BDF5
0x18001bdcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdd2  cmp     rcx, r12
0x18001bdd5  jz      short loc_18001BDF5
0x18001bdd7  test    byte ptr [rcx+1Ch], 1
0x18001bddb  jz      short loc_18001BDF5
0x18001bddd  mov     rcx, [rcx+10h]
0x18001bde1  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001bde8  mov     edx, 69h ; 'i'
0x18001bded  mov     r9d, eax
0x18001bdf0  call    WPP_SF_d
0x18001bdf5  mov     ebx, 104h
0x18001bdfa  lea     rcx, [rbp+3E0h+NameBuffer]; void *
0x18001bdfe  mov     r8d, ebx; Size
0x18001be01  xor     edx, edx; Val
0x18001be03  call    memset_0
0x18001be08  lea     r8, [rsp+4E0h+nSize]; nSize
0x18001be0d  mov     [rsp+4E0h+nSize], ebx
0x18001be11  lea     rdx, [rbp+3E0h+NameBuffer]; lpNameBuffer
0x18001be15  mov     ecx, 2; NameFormat
0x18001be1a  call    cs:__imp_GetUserNameExW
0x18001be20  test    al, al
0x18001be22  jz      short loc_18001BE45
0x18001be24  cmp     [rbp+3E0h+NameBuffer], r15w
0x18001be29  jz      short loc_18001BE45
0x18001be2b  lea     rcx, [rbp+3E0h+NameBuffer]
0x18001be2f  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001be34  mov     r8, rax
0x18001be37  lea     rdx, [rbp+3E0h+NameBuffer]
0x18001be3b  mov     rcx, rsi
0x18001be3e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001be43  jmp     short loc_18001BE92
0x18001be45  lea     rcx, aSystem_0; "System"
0x18001be4c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001be51  mov     rdx, rcx
0x18001be54  mov     r8, rax
0x18001be57  mov     rcx, rsi
0x18001be5a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001be5f  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001be64  test    eax, eax
0x18001be66  jns     short loc_18001BE92
0x18001be68  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be6f  cmp     rcx, r12
0x18001be72  jz      short loc_18001BE92
0x18001be74  test    byte ptr [rcx+1Ch], 1
0x18001be78  jz      short loc_18001BE92
0x18001be7a  mov     rcx, [rcx+10h]
0x18001be7e  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001be85  mov     edx, 6Ah ; 'j'
0x18001be8a  mov     r9d, eax
0x18001be8d  call    WPP_SF_d
0x18001be92  lea     rcx, [r14+48h]; lpCriticalSection
0x18001be96  call    cs:__imp_EnterCriticalSection
0x18001be9c  lea     rcx, [r14+88h]
0x18001bea3  lea     r8, [rsp+4E0h+pProxy]
0x18001bea8  lea     rdx, [rsp+4E0h+nSize]
0x18001bead  call    ??$_Try_emplace@AEBQEAUIUnknown@@$$V@?$map@PEAUIUnknown@@PEAVNotifySourceInfo@@U?$less@PEAUIUnknown@@@std@@V?$allocator@U?$pair@QEAUIUnknown@@PEAVNotifySourceInfo@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAUIUnknown@@PEAVNotifySourceInfo@@@std@@PEAX@std@@_N@1@AEBQEAUIUnknown@@@Z; std::map<IUnknown *,NotifySourceInfo *>::_Try_emplace<IUnknown * const &,>(IUnknown * const &)
0x18001beb2  lea     rcx, [r14+48h]; lpCriticalSection
0x18001beb6  mov     rdx, [rax]
0x18001beb9  mov     [rdx+28h], rsi
0x18001bebd  call    cs:__imp_LeaveCriticalSection
0x18001bec3  jmp     short loc_18001BECA
0x18001bec5  mov     edi, 8007000Eh
0x18001beca  mov     esi, 1
0x18001becf  lea     rcx, [rsp+4E0h+NotificationFilter]; this
0x18001bed4  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18001bed9  cmp     [r14+98h], r15d
0x18001bee0  jnz     loc_18001BFAC
0x18001bee6  mov     eax, esi
0x18001bee8  xchg    eax, [r14+98h]
0x18001beef  test    eax, eax
0x18001bef1  jnz     loc_18001BFAC
0x18001bef7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001befe  cmp     rcx, r12
0x18001bf01  jz      short loc_18001BF1C
0x18001bf03  test    byte ptr [rcx+1Ch], 8
0x18001bf07  jz      short loc_18001BF1C
0x18001bf09  mov     rcx, [rcx+10h]
0x18001bf0d  lea     edx, [rax+6Dh]
0x18001bf10  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001bf17  call    WPP_SF_
0x18001bf1c  movups  xmm0, xmmword ptr cs:GUID_NDIS_LAN_CLASS.Data1
0x18001bf23  mov     rcx, cs:hRecipient; hRecipient
0x18001bf2a  lea     rdx, [rsp+4E0h+NotificationFilter]; NotificationFilter
0x18001bf2f  mov     r8d, esi; Flags
0x18001bf32  mov     [rsp+4E0h+var_484], 5
0x18001bf3b  movdqu  [rsp+4E0h+var_47C], xmm0
0x18001bf41  mov     [rsp+4E0h+var_46C], r15d
0x18001bf46  mov     [rsp+4E0h+NotificationFilter], 20h ; ' '
0x18001bf4e  call    cs:__imp_RegisterDeviceNotificationW
0x18001bf54  mov     [r14+0A0h], rax
0x18001bf5b  test    rax, rax
0x18001bf5e  jnz     short loc_18001BF96
0x18001bf60  mov     rax, cs:WPP_GLOBAL_Control
0x18001bf67  cmp     rax, r12
0x18001bf6a  jz      short loc_18001BF96
0x18001bf6c  test    byte ptr [rax+1Ch], 8
0x18001bf70  jz      short loc_18001BF96
0x18001bf72  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001bf77  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf7e  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001bf85  mov     edx, 6Eh ; 'n'
0x18001bf8a  mov     r9d, eax
0x18001bf8d  mov     rcx, [rcx+10h]
0x18001bf91  call    WPP_SF_d
0x18001bf96  mov     edx, esi; int
0x18001bf98  lea     rcx, [r14-8]; this
0x18001bf9c  call    ?HrEnsureRegisteredOrDeregisteredWithWmi@ConnectionManager@@AEAAJH@Z; ConnectionManager::HrEnsureRegisteredOrDeregisteredWithWmi(int)
0x18001bfa1  mov     edx, esi; int
0x18001bfa3  lea     rcx, [r14-8]; this
0x18001bfa7  call    ?HrEnsureRegisteredOrDeregisteredWithNsi@ConnectionManager@@AEAAJH@Z; ConnectionManager::HrEnsureRegisteredOrDeregisteredWithNsi(int)
0x18001bfac  test    edi, edi
0x18001bfae  jns     short loc_18001BFDA
0x18001bfb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfb7  cmp     rcx, r12
0x18001bfba  jz      short loc_18001BFDA
0x18001bfbc  test    [rcx+1Ch], sil
0x18001bfc0  jz      short loc_18001BFDA
0x18001bfc2  mov     rcx, [rcx+10h]
0x18001bfc6  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001bfcd  mov     edx, 6Fh ; 'o'
0x18001bfd2  mov     r9d, edi
0x18001bfd5  call    WPP_SF_d
0x18001bfda  mov     eax, edi
0x18001bfdc  mov     rcx, [rbp+3E0h+var_40]
0x18001bfe3  xor     rcx, rsp; StackCookie
0x18001bfe6  call    __security_check_cookie
0x18001bfeb  add     rsp, 4B0h
0x18001bff2  pop     r15
  ... truncated ...
```

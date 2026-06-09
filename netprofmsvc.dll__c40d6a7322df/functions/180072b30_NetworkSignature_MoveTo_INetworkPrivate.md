# NetworkSignature::MoveTo(INetworkPrivate *)

- ea: `0x180072b30`
- end: `0x1800732e3`
- name: `?MoveTo@NetworkSignature@@UEAAJPEAUINetworkPrivate@@@Z`
- size: `1971`
- prototype: `__int64 __fastcall(NetworkSignature *__hidden this, struct INetworkPrivate *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x1800120a0`
- `0x1800127d0`
- `0x180015650`
- `0x180015710`
- `0x180019274`
- `0x1800386bc`
- `0x18003b250`
- `0x18004068c`
- `0x180042bf8`
- `0x180047ff4`
- `0x180072b30`
- `0x180073420`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800ca1d0`
- `0x1800cfdc0`
- `0x1800d72b8`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072e2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072e92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072f38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072fde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072e2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072e92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072f38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072fde`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180072eb2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180072fa8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180072eb2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180072fa8`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180072f8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180072f8f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072ee3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072ee3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NetworkSignature::MoveTo(NetworkSignature *this, struct INetworkPrivate *a2)
{
  struct tagNLA_SIGNATURE *v5; // r14
  unsigned int v6; // eax
  unsigned int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // esi
  unsigned int v10; // eax
  unsigned int v11; // esi
  unsigned int NlaSignatureProfile; // eax
  unsigned int v13; // esi
  LSTATUS v14; // eax
  unsigned int v15; // esi
  bool v16; // r12
  __int64 v17; // rsi
  __int64 v18; // r15
  __int64 v19; // rsi
  __int64 v20; // r14
  PVOID *v21; // rcx
  bool v22; // [rsp+30h] [rbp-1B8h] BYREF
  bool v23; // [rsp+31h] [rbp-1B7h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-1B0h] BYREF
  int v25; // [rsp+40h] [rbp-1A8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-1A0h] BYREF
  GUID rguid; // [rsp+50h] [rbp-198h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-188h] BYREF
  struct _GUID v29; // [rsp+78h] [rbp-170h] BYREF
  __int64 v30; // [rsp+90h] [rbp-158h] BYREF
  int v31; // [rsp+98h] [rbp-150h]
  int v32; // [rsp+9Ch] [rbp-14Ch]
  GUID v33; // [rsp+A0h] [rbp-148h] BYREF
  GUID v34; // [rsp+B0h] [rbp-138h]
  __int128 v35; // [rsp+C0h] [rbp-128h]
  __int128 v36; // [rsp+D0h] [rbp-118h]
  __int128 v37; // [rsp+E0h] [rbp-108h]
  int v38; // [rsp+F0h] [rbp-F8h]
  OLECHAR v39[40]; // [rsp+110h] [rbp-D8h] BYREF
  OLECHAR sz[40]; // [rsp+160h] [rbp-88h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids);
  StandbyMonitor::ProcessClientActivity(89);
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, 2147500035LL);
    return 2147500035LL;
  }
  if ( !*((_DWORD *)this + 4) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, 2147549183LL);
    return 2147549183LL;
  }
  v5 = (NetworkSignature *)((char *)this + 24);
  if ( !*((_DWORD *)this + 18) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, 2147942450LL);
    return 2147942450LL;
  }
  if ( (*((_BYTE *)this + 76) & 3) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, 2147942450LL);
    return 2147942450LL;
  }
  if ( !(unsigned int)ClientHasAccess(3) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, 2147942405LL);
    return 2147942405LL;
  }
  v25 = 0;
  v6 = (*(__int64 (__fastcall **)(struct INetworkPrivate *, int *))(*(_QWORD *)a2 + 80LL))(a2, &v25);
  v7 = v6;
  if ( !v6 )
  {
    if ( v25 == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, 2147942450LL);
      return 2147942450LL;
    }
    if ( (unsigned int)SignatureSetByPolicy(v5) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, 2147942405LL);
      return 2147942405LL;
    }
    v23 = 0;
    v22 = 0;
    v29 = 0;
    rguid = 0;
    v8 = (*(__int64 (__fastcall **)(struct INetworkPrivate *, GUID *))(*(_QWORD *)a2 + 48LL))(a2, &rguid);
    v9 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, v8);
      return v9;
    }
    lpCriticalSection = 0;
    NetworkPropertyMaps::LockProfileStore(&lpCriticalSection);
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v10 = HrOpenSignatureKey(v5, 0x2001Fu, &hKey);
    v11 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, v10);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      return v11;
    }
    NlaSignatureProfile = HrGetNlaSignatureProfile(hKey, 0, &v29, 0);
    v13 = NlaSignatureProfile;
    if ( NlaSignatureProfile )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids,
          NlaSignatureProfile);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      return v13;
    }
    StringFromGUID2(&rguid, sz, 39);
    v14 = RegSetValueExW(hKey, L"ProfileGuid", 0, 1u, (const BYTE *)sz, 0x4Eu);
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, v15);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      return v15;
    }
    NetworkPropertyMaps::MoveNlaSignature(v5, &v29, &rguid, &v23, &v22);
    v16 = v22;
    if ( v22 )
    {
      memset_0(v39, 0, 0x4Eu);
      SystemTime = 0;
      GetLocalTime(&SystemTime);
      if ( StringFromGUID2(&rguid, v39, 39) == 39 )
        HrUpdateProfileInfo(v39, 0x40u, &SystemTime);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    v31 = -1;
    v32 = 0;
    memset_0(&v33, 0, 0x68u);
    v30 = 1063;
    v33 = v29;
    v34 = rguid;
    v35 = *(_OWORD *)v5;
    v36 = *((_OWORD *)v5 + 1);
    v37 = *((_OWORD *)v5 + 2);
    v38 = *((_DWORD *)v5 + 12);
    NetworkListManager::PostEventToEventMgr((struct NP_EVENT_INFO *)&v30, 1);
    if ( v23 )
    {
      LODWORD(v30) = 1045;
      v33 = v29;
      NetworkPropertyMaps::FindConnectedNetworksBySignature(&SystemTime, v5, &rguid, 0, 0);
      v17 = *(_QWORD *)&SystemTime.wYear;
      v18 = *(_QWORD *)&SystemTime.wHour;
      while ( v17 != v18 )
      {
        HIDWORD(v30) = *(_DWORD *)(v17 + 128);
        NetworkListManager::PostEventToEventMgr((struct NP_EVENT_INFO *)&v30, 1);
        v17 += 696;
      }
      std::vector<ACTIVE_NETWORK>::_Tidy(&SystemTime);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids);
    }
    if ( v16 )
    {
      LODWORD(v30) = 1044;
      v33 = rguid;
      NetworkPropertyMaps::FindConnectedNetworksBySignature(&SystemTime, v5, &rguid, 0, 0);
      v19 = *(_QWORD *)&SystemTime.wYear;
      v20 = *(_QWORD *)&SystemTime.wHour;
      while ( v19 != v20 )
      {
        HIDWORD(v30) = *(_DWORD *)(v19 + 128);
        NetworkListManager::PostEventToEventMgr((struct NP_EVENT_INFO *)&v30, 1);
        v19 += 696;
      }
      std::vector<ACTIVE_NETWORK>::_Tidy(&SystemTime);
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_90:
        if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
          WPP_SF_d(v21[2], 46, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, 0);
        return 0;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids);
    }
    else if ( NetworkPropertyMaps::IsNetworkConnected(&rguid) )
    {
      v30 = 1046;
      v33 = rguid;
      v34.Data1 = 1;
      NetworkListManager::PostEventToEventMgr((struct NP_EVENT_INFO *)&v30, 1);
    }
    v21 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_90;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, v6);
  return v7;
}

```

## disassembly

```asm
0x180072b30  mov     [rsp+arg_10], rbx
0x180072b35  push    rsi
0x180072b36  push    r12
0x180072b38  push    r13
0x180072b3a  push    r14
0x180072b3c  push    r15
0x180072b3e  sub     rsp, 1C0h
0x180072b45  mov     rax, cs:__security_cookie
0x180072b4c  xor     rax, rsp
0x180072b4f  mov     [rsp+1E8h+var_38], rax
0x180072b57  mov     r15, rdx
0x180072b5a  mov     rsi, rcx
0x180072b5d  lea     r12, WPP_GLOBAL_Control
0x180072b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180072b6b  lea     rbx, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids
0x180072b72  cmp     rcx, r12
0x180072b75  jz      short loc_180072B8E
0x180072b77  test    byte ptr [rcx+1Ch], 8
0x180072b7b  jz      short loc_180072B8E
0x180072b7d  mov     edx, 1Fh
0x180072b82  mov     r8, rbx
0x180072b85  mov     rcx, [rcx+10h]
0x180072b89  call    WPP_SF_
0x180072b8e  mov     ecx, 59h ; 'Y'
0x180072b93  call    ?ProcessClientActivity@StandbyMonitor@@YAXW4ClientActivity@1@@Z; StandbyMonitor::ProcessClientActivity(StandbyMonitor::ClientActivity)
0x180072b98  xor     r13d, r13d
0x180072b9b  test    r15, r15
0x180072b9e  jnz     short loc_180072BD2
0x180072ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x180072ba7  cmp     rcx, r12
0x180072baa  jz      short loc_180072BC8
0x180072bac  test    byte ptr [rcx+1Ch], 8
0x180072bb0  jz      short loc_180072BC8
0x180072bb2  lea     edx, [r13+20h]
0x180072bb6  mov     r9d, 80004003h
0x180072bbc  mov     r8, rbx
0x180072bbf  mov     rcx, [rcx+10h]
0x180072bc3  call    WPP_SF_d
0x180072bc8  mov     eax, 80004003h
0x180072bcd  jmp     loc_1800732B9
0x180072bd2  cmp     [rsi+10h], r13d
0x180072bd6  jnz     short loc_180072C0B
0x180072bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180072bdf  cmp     rcx, r12
0x180072be2  jz      short loc_180072C01
0x180072be4  test    byte ptr [rcx+1Ch], 8
0x180072be8  jz      short loc_180072C01
0x180072bea  mov     edx, 21h ; '!'
0x180072bef  mov     r9d, 8000FFFFh
0x180072bf5  mov     r8, rbx
0x180072bf8  mov     rcx, [rcx+10h]
0x180072bfc  call    WPP_SF_d
0x180072c01  mov     eax, 8000FFFFh
0x180072c06  jmp     loc_1800732B9
0x180072c0b  lea     r14, [rsi+18h]
0x180072c0f  cmp     [r14+30h], r13d
0x180072c13  jnz     short loc_180072C48
0x180072c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180072c1c  cmp     rcx, r12
0x180072c1f  jz      short loc_180072C3E
0x180072c21  test    byte ptr [rcx+1Ch], 8
0x180072c25  jz      short loc_180072C3E
0x180072c27  mov     edx, 22h ; '"'
0x180072c2c  mov     r9d, 80070032h
0x180072c32  mov     r8, rbx
0x180072c35  mov     rcx, [rcx+10h]
0x180072c39  call    WPP_SF_d
0x180072c3e  mov     eax, 80070032h
0x180072c43  jmp     loc_1800732B9
0x180072c48  mov     ecx, 3; unsigned int
0x180072c4d  test    [rsi+4Ch], cl
0x180072c50  jz      short loc_180072C85
0x180072c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180072c59  cmp     rcx, r12
0x180072c5c  jz      short loc_180072C7B
0x180072c5e  test    byte ptr [rcx+1Ch], 8
0x180072c62  jz      short loc_180072C7B
0x180072c64  mov     edx, 23h ; '#'
0x180072c69  mov     r9d, 80070032h
0x180072c6f  mov     r8, rbx
0x180072c72  mov     rcx, [rcx+10h]
0x180072c76  call    WPP_SF_d
0x180072c7b  mov     eax, 80070032h
0x180072c80  jmp     loc_1800732B9
0x180072c85  call    ?ClientHasAccess@@YAHK@Z; ClientHasAccess(ulong)
0x180072c8a  test    eax, eax
0x180072c8c  jnz     short loc_180072CBF
0x180072c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180072c95  cmp     rcx, r12
0x180072c98  jz      short loc_180072CB5
0x180072c9a  test    byte ptr [rcx+1Ch], 8
0x180072c9e  jz      short loc_180072CB5
0x180072ca0  lea     edx, [rax+24h]
0x180072ca3  mov     r9d, 80070005h
0x180072ca9  mov     r8, rbx
0x180072cac  mov     rcx, [rcx+10h]
0x180072cb0  call    WPP_SF_d
0x180072cb5  mov     eax, 80070005h
0x180072cba  jmp     loc_1800732B9
0x180072cbf  mov     [rsp+1E8h+var_1A8], r13d
0x180072cc4  mov     rax, [r15]
0x180072cc7  lea     rdx, [rsp+1E8h+var_1A8]
0x180072ccc  mov     rcx, r15
0x180072ccf  mov     rax, [rax+50h]
0x180072cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072cd8  mov     esi, eax
0x180072cda  test    eax, eax
0x180072cdc  jnz     loc_18007328B
0x180072ce2  cmp     [rsp+1E8h+var_1A8], 1
0x180072ce7  jnz     short loc_180072D1A
0x180072ce9  mov     rcx, cs:WPP_GLOBAL_Control
0x180072cf0  cmp     rcx, r12
0x180072cf3  jz      short loc_180072D10
0x180072cf5  test    byte ptr [rcx+1Ch], 8
0x180072cf9  jz      short loc_180072D10
0x180072cfb  lea     edx, [rax+25h]
0x180072cfe  mov     r9d, 80070032h
0x180072d04  mov     r8, rbx
0x180072d07  mov     rcx, [rcx+10h]
0x180072d0b  call    WPP_SF_d
0x180072d10  mov     eax, 80070032h
0x180072d15  jmp     loc_1800732B9
0x180072d1a  mov     rcx, r14; Buf1
0x180072d1d  call    ?SignatureSetByPolicy@@YAHPEAUtagNLA_SIGNATURE@@@Z; SignatureSetByPolicy(tagNLA_SIGNATURE *)
0x180072d22  test    eax, eax
0x180072d24  jz      short loc_180072D59
0x180072d26  mov     rcx, cs:WPP_GLOBAL_Control
0x180072d2d  cmp     rcx, r12
0x180072d30  jz      short loc_180072D4F
0x180072d32  test    byte ptr [rcx+1Ch], 8
0x180072d36  jz      short loc_180072D4F
0x180072d38  mov     edx, 27h ; '''
0x180072d3d  mov     r9d, 80070005h
0x180072d43  mov     r8, rbx
0x180072d46  mov     rcx, [rcx+10h]
0x180072d4a  call    WPP_SF_d
0x180072d4f  mov     eax, 80070005h
0x180072d54  jmp     loc_1800732B9
0x180072d59  mov     [rsp+1E8h+var_1B7], r13b
0x180072d5e  mov     [rsp+1E8h+var_1B8], r13b
0x180072d63  xorps   xmm0, xmm0
0x180072d66  movups  xmmword ptr [rsp+1E8h+var_170.Data1], xmm0
0x180072d6b  xorps   xmm1, xmm1
0x180072d6e  movups  xmmword ptr [rsp+1E8h+rguid.Data1], xmm1
0x180072d73  mov     rax, [r15]
0x180072d76  lea     rdx, [rsp+1E8h+rguid]
0x180072d7b  mov     rcx, r15
0x180072d7e  mov     rax, [rax+30h]
0x180072d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072d87  mov     esi, eax
0x180072d89  test    eax, eax
0x180072d8b  jz      short loc_180072DBA
0x180072d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072d94  cmp     rcx, r12
0x180072d97  jz      short loc_180072DB3
0x180072d99  test    byte ptr [rcx+1Ch], 8
0x180072d9d  jz      short loc_180072DB3
0x180072d9f  mov     edx, 28h ; '('
0x180072da4  mov     r9d, eax
0x180072da7  mov     r8, rbx
0x180072daa  mov     rcx, [rcx+10h]
0x180072dae  call    WPP_SF_d
0x180072db3  mov     eax, esi
0x180072db5  jmp     loc_1800732B9
0x180072dba  mov     [rsp+1E8h+lpCriticalSection], r13
0x180072dbf  lea     rcx, [rsp+1E8h+lpCriticalSection]
0x180072dc4  call    ?LockProfileStore@NetworkPropertyMaps@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; NetworkPropertyMaps::LockProfileStore(void)
0x180072dc9  nop
0x180072dca  mov     [rsp+1E8h+hKey], r13
0x180072dcf  xor     edx, edx
0x180072dd1  lea     rcx, [rsp+1E8h+hKey]
0x180072dd6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180072ddb  lea     r8, [rsp+1E8h+hKey]; HKEY *
0x180072de0  mov     edx, 2001Fh; unsigned int
0x180072de5  mov     rcx, r14; struct tagNLA_SIGNATURE *
0x180072de8  call    ?HrOpenSignatureKey@@YAJPEAUtagNLA_SIGNATURE@@KPEAPEAUHKEY__@@@Z; HrOpenSignatureKey(tagNLA_SIGNATURE *,ulong,HKEY__ * *)
0x180072ded  mov     esi, eax
0x180072def  test    eax, eax
0x180072df1  jz      short loc_180072E3C
0x180072df3  mov     rcx, cs:WPP_GLOBAL_Control
0x180072dfa  cmp     rcx, r12
0x180072dfd  jz      short loc_180072E1A
0x180072dff  test    byte ptr [rcx+1Ch], 8
0x180072e03  jz      short loc_180072E1A
0x180072e05  mov     edx, 29h ; ')'
0x180072e0a  mov     r9d, eax
0x180072e0d  mov     r8, rbx
0x180072e10  mov     rcx, [rcx+10h]
0x180072e14  call    WPP_SF_d
0x180072e19  nop
0x180072e1a  lea     rcx, [rsp+1E8h+hKey]
0x180072e1f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180072e24  nop
0x180072e25  mov     rcx, [rsp+1E8h+lpCriticalSection]; lpCriticalSection
0x180072e2a  test    rcx, rcx
0x180072e2d  jz      short loc_180072E35
0x180072e2f  call    cs:__imp_LeaveCriticalSection
0x180072e35  mov     eax, esi
0x180072e37  jmp     loc_1800732B9
0x180072e3c  xor     r9d, r9d; unsigned int *
0x180072e3f  lea     r8, [rsp+1E8h+var_170]; struct _GUID *
0x180072e44  xor     edx, edx; struct tagNLA_SIGNATURE *
0x180072e46  mov     rcx, [rsp+1E8h+hKey]; HKEY
0x180072e4b  call    ?HrGetNlaSignatureProfile@@YAJPEAUHKEY__@@PEAUtagNLA_SIGNATURE@@PEAU_GUID@@PEAK@Z; HrGetNlaSignatureProfile(HKEY__ *,tagNLA_SIGNATURE *,_GUID *,ulong *)
0x180072e50  mov     esi, eax
0x180072e52  test    eax, eax
0x180072e54  jz      short loc_180072E9F
0x180072e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180072e5d  cmp     rcx, r12
0x180072e60  jz      short loc_180072E7D
0x180072e62  test    byte ptr [rcx+1Ch], 8
0x180072e66  jz      short loc_180072E7D
0x180072e68  mov     edx, 2Ah ; '*'
0x180072e6d  mov     r9d, eax
0x180072e70  mov     r8, rbx
0x180072e73  mov     rcx, [rcx+10h]
0x180072e77  call    WPP_SF_d
0x180072e7c  nop
0x180072e7d  lea     rcx, [rsp+1E8h+hKey]
0x180072e82  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180072e87  nop
0x180072e88  mov     rcx, [rsp+1E8h+lpCriticalSection]; lpCriticalSection
0x180072e8d  test    rcx, rcx
0x180072e90  jz      short loc_180072E98
0x180072e92  call    cs:__imp_LeaveCriticalSection
0x180072e98  mov     eax, esi
0x180072e9a  jmp     loc_1800732B9
0x180072e9f  mov     r8d, 27h ; '''; cchMax
0x180072ea5  lea     rdx, [rsp+1E8h+sz]; lpsz
0x180072ead  lea     rcx, [rsp+1E8h+rguid]; rguid
0x180072eb2  call    cs:__imp_StringFromGUID2
0x180072eb8  mov     r15d, 4Eh ; 'N'
0x180072ebe  mov     [rsp+1E8h+cbData], r15d; cbData
0x180072ec3  lea     rax, [rsp+1E8h+sz]
0x180072ecb  mov     [rsp+1E8h+lpData], rax; lpData
0x180072ed0  lea     r9d, [r15-4Dh]; dwType
0x180072ed4  xor     r8d, r8d; Reserved
0x180072ed7  lea     rdx, aProfileguid; "ProfileGuid"
0x180072ede  mov     rcx, [rsp+1E8h+hKey]; hKey
0x180072ee3  call    cs:__imp_RegSetValueExW
0x180072ee9  mov     esi, eax
0x180072eeb  test    eax, eax
0x180072eed  jle     short loc_180072EF8
0x180072eef  movzx   esi, ax
0x180072ef2  or      esi, 80070000h
0x180072ef8  test    esi, esi
0x180072efa  jz      short loc_180072F45
0x180072efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f03  cmp     rcx, r12
0x180072f06  jz      short loc_180072F23
0x180072f08  test    byte ptr [rcx+1Ch], 2
0x180072f0c  jz      short loc_180072F23
0x180072f0e  mov     edx, 2Bh ; '+'
0x180072f13  mov     r9d, esi
0x180072f16  mov     r8, rbx
0x180072f19  mov     rcx, [rcx+10h]
0x180072f1d  call    WPP_SF_d
0x180072f22  nop
0x180072f23  lea     rcx, [rsp+1E8h+hKey]
0x180072f28  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180072f2d  nop
0x180072f2e  mov     rcx, [rsp+1E8h+lpCriticalSection]; lpCriticalSection
0x180072f33  test    rcx, rcx
0x180072f36  jz      short loc_180072F3E
0x180072f38  call    cs:__imp_LeaveCriticalSection
0x180072f3e  mov     eax, esi
0x180072f40  jmp     loc_1800732B9
0x180072f45  lea     rax, [rsp+1E8h+var_1B8]
0x180072f4a  mov     [rsp+1E8h+lpData], rax; bool *
0x180072f4f  lea     r9, [rsp+1E8h+var_1B7]; bool *
0x180072f54  lea     r8, [rsp+1E8h+rguid]; struct _GUID *
0x180072f59  lea     rdx, [rsp+1E8h+var_170]; struct _GUID *
0x180072f5e  mov     rcx, r14; struct tagNLA_SIGNATURE *
0x180072f61  call    ?MoveNlaSignature@NetworkPropertyMaps@@SAXPEBUtagNLA_SIGNATURE@@AEBU_GUID@@1PEA_N2@Z; NetworkPropertyMaps::MoveNlaSignature(tagNLA_SIGNATURE const *,_GUID const &,_GUID const &,bool *,bool *)
0x180072f66  mov     r12b, [rsp+1E8h+var_1B8]
0x180072f6b  test    r12b, r12b
0x180072f6e  jz      short loc_180072FC9
0x180072f70  mov     r8, r15; Size
0x180072f73  xor     edx, edx; Val
0x180072f75  lea     rcx, [rsp+1E8h+var_D8]; void *
0x180072f7d  call    memset_0
0x180072f82  xorps   xmm0, xmm0
0x180072f85  movups  xmmword ptr [rsp+1E8h+SystemTime.wYear], xmm0
0x180072f8a  lea     rcx, [rsp+1E8h+SystemTime]; lpSystemTime
0x180072f8f  call    cs:__imp_GetLocalTime
0x180072f95  mov     r8d, 27h ; '''; cchMax
0x180072f9b  lea     rdx, [rsp+1E8h+var_D8]; lpsz
0x180072fa3  lea     rcx, [rsp+1E8h+rguid]; rguid
0x180072fa8  call    cs:__imp_StringFromGUID2
0x180072fae  cmp     eax, 27h ; '''
0x180072fb1  jnz     short loc_180072FC9
0x180072fb3  lea     r8, [rsp+1E8h+SystemTime]
0x180072fb8  lea     edx, [rax+19h]; unsigned int
0x180072fbb  lea     rcx, [rsp+1E8h+var_D8]; wchar_t *
0x180072fc3  call    ?HrUpdateProfileInfo@@YAJPEB_WKZZ; HrUpdateProfileInfo(wchar_t const *,ulong,...)
0x180072fc8  nop
0x180072fc9  lea     rcx, [rsp+1E8h+hKey]
0x180072fce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180072fd3  nop
0x180072fd4  mov     rcx, [rsp+1E8h+lpCriticalSection]; lpCriticalSection
  ... truncated ...
```

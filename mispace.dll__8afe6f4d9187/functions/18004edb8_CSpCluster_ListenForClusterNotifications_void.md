# CSpCluster::_ListenForClusterNotifications(void)

- ea: `0x18004edb8`
- end: `0x18004f457`
- name: `?_ListenForClusterNotifications@CSpCluster@@AEAAXXZ`
- size: `1695`
- prototype: `void __fastcall(CSpCluster *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004d340`

## callees

- `0x1800011b0`
- `0x180001490`
- `0x1800014ec`
- `0x1800015b8`
- `0x180002364`
- `0x180002438`
- `0x180006290`
- `0x18000d49c`
- `0x18000e43c`
- `0x18000f050`
- `0x18003902c`
- `0x18004bcf0`
- `0x18004dfc0`
- `0x18004e01c`
- `0x18004e1e0`
- `0x18004edb8`
- `0x180050380`
- `0x18005064c`
- `0x1800506a0`
- `0x180066ab4`
- `0x1801ad3f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004f004`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004f004`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f038`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f046`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f054`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f3d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f3de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f3ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f038`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f046`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f054`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f3d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f3de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f3ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f067`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f080`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f099`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f067`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f080`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f099`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x18004ee8f`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x18004eec7`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x18004eefb`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x18004ef33`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x18004ee8f`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x18004eec7`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x18004eefb`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x18004ef33`
- `ext-ms-win-cluster-clusapi-l1-1-1!CloseClusterNotifyPort` at `0x18004f3b7`
- `ext-ms-win-cluster-clusapi-l1-1-1!CloseClusterNotifyPort` at `0x18004f3b7`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNotifyV2` at `0x18004f10c`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNotifyV2` at `0x18004f10c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSpCluster::_ListenForClusterNotifications(CSpCluster *this, __int64 a2, __int64 a3, __int64 a4)
{
  char *v5; // r14
  HLOCAL v6; // rsi
  void *v7; // r15
  __int64 v8; // rdx
  __int64 v9; // rax
  struct _HCHANGE *v10; // rbx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  HLOCAL v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  signed int ClusterNotifyV2; // eax
  CSpCluster *v19; // rcx
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  int *v30; // [rsp+28h] [rbp-A1h]
  __int64 v31; // [rsp+28h] [rbp-A1h]
  __int64 v32; // [rsp+28h] [rbp-A1h]
  __int64 v33; // [rsp+28h] [rbp-A1h]
  int v34; // [rsp+70h] [rbp-59h] BYREF
  const char *v35; // [rsp+78h] [rbp-51h] BYREF
  unsigned int v36; // [rsp+80h] [rbp-49h] BYREF
  int v37; // [rsp+84h] [rbp-45h] BYREF
  int v38; // [rsp+88h] [rbp-41h] BYREF
  __int64 v39; // [rsp+90h] [rbp-39h] BYREF
  char v40; // [rsp+98h] [rbp-31h]
  __int64 v41; // [rsp+A0h] [rbp-29h] BYREF
  const char *v42; // [rsp+A8h] [rbp-21h] BYREF
  __int128 v43; // [rsp+B0h] [rbp-19h] BYREF
  _QWORD v44[2]; // [rsp+C0h] [rbp-9h] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v34 = 3274;
    v42 = "CSpCluster::_ListenForClusterNotifications";
    v30 = &v34;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"CSpCluster::_ListenForClusterNotifications",
      (__int64)word_1803022E2,
      a3,
      a4,
      &v42);
  }
  v5 = 0;
  v36 = 0;
  v43 = 0;
  v34 = 0;
  v41 = 0;
  v6 = 0;
  v38 = 39;
  v7 = 0;
  v37 = 0;
  v39 = 0;
  v40 = 0;
  wil::EnterCriticalSection(&v42, (char *)this + 8);
  v8 = *((_QWORD *)this + 9);
  if ( v8 )
  {
    LODWORD(v43) = 1;
    *((_QWORD *)&v43 + 1) = 1024;
    v9 = CreateClusterNotifyPortV2(-1, v8, &v43, 1, v41, v30);
    v10 = (struct _HCHANGE *)v9;
    if ( v9 )
    {
      LODWORD(v43) = 7;
      *((_QWORD *)&v43 + 1) = 146;
      v10 = (struct _HCHANGE *)CreateClusterNotifyPortV2(v9, *((_QWORD *)this + 9), &v43, 1, v41, v31);
      if ( v10 )
      {
        LODWORD(v43) = 11;
        *((_QWORD *)&v43 + 1) = 1;
        v10 = (struct _HCHANGE *)CreateClusterNotifyPortV2(v10, *((_QWORD *)this + 9), &v43, 1, v41, v32);
        if ( v10 )
        {
          LODWORD(v43) = 8;
          *((_QWORD *)&v43 + 1) = 12;
          v10 = (struct _HCHANGE *)CreateClusterNotifyPortV2(v10, *((_QWORD *)this + 9), &v43, 1, v41, v33);
          if ( v10 )
          {
            wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
              &v42,
              0);
            if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 4) != 0 )
              McGenEventWrite_EventWriteTransfer(LOG_PROVIDER_GUID_Context, ClusterConnected, v11, 1, v44);
            if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
            {
              v35 = "Connected";
              v44[0] = v13;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v12,
                (__int64)word_180303BBA,
                v13,
                v14,
                v44,
                &v35);
            }
            while ( 2 )
            {
              if ( (unsigned int)SmIsClusteredNode(0, &v34) && v34 && (unsigned int)CSpCluster::IsClusterUp(this) )
              {
                if ( WaitForSingleObject(*((HANDLE *)this + 8), 0) )
                {
                  v36 = 256;
                  v37 = 256;
                  v38 = 39;
                  LODWORD(v39) = -2147024662;
                  while ( _status_t::ToWin32((_status_t *)&v39) == 234 )
                  {
                    if ( v5 )
                      LocalFree(v5);
                    if ( v6 )
                      LocalFree(v6);
                    if ( v7 )
                      LocalFree(v7);
                    v5 = (char *)LocalAlloc(0, ++v36);
                    v6 = LocalAlloc(0, 2LL * (unsigned int)++v38);
                    v15 = LocalAlloc(0, 2LL * (unsigned int)++v37);
                    v7 = v15;
                    if ( !v5 || !v6 || !v15 )
                    {
                      LODWORD(v39) = -2147024882;
                      if ( (unsigned int)dword_180397B68 > 2 )
                      {
                        LODWORD(v35) = -2147024882;
                        v34 = 3417;
                        v44[0] = "CSpCluster::_ListenForClusterNotifications";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                          2147942414LL,
                          (__int64)byte_180304431,
                          v16,
                          v17,
                          v44);
                      }
                      goto LABEL_48;
                    }
                    ClusterNotifyV2 = GetClusterNotifyV2(
                                        v10,
                                        &v41,
                                        &v43,
                                        v5,
                                        &v36,
                                        v6,
                                        &v38,
                                        0,
                                        0,
                                        v15,
                                        &v37,
                                        0,
                                        0,
                                        2500);
                    if ( ClusterNotifyV2 > 0 )
                      ClusterNotifyV2 = (unsigned __int16)ClusterNotifyV2 | 0x80070000;
                    LODWORD(v39) = ClusterNotifyV2;
                  }
                  if ( _status_t::ToWin32((_status_t *)&v39) == 6 )
                  {
                    if ( (unsigned int)dword_180397B68 > 3 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 3072) )
                    {
                      LODWORD(v35) = SmIsClusteredNode(0, 0);
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                        (__int64)&dword_180397B68,
                        (__int64)byte_180301B73);
                    }
                    break;
                  }
                  if ( _status_t::ToWin32((_status_t *)&v39) )
                    continue;
                  if ( (unsigned int)dword_180397B68 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 3072) )
                  {
                    v44[0] = *((_QWORD *)&v43 + 1);
                    LODWORD(v35) = v43;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      (__int64)v19,
                      (__int64)byte_180303EE1);
                  }
                  if ( (_DWORD)v43 != 1 )
                  {
                    switch ( (_DWORD)v43 )
                    {
                      case 7:
                        CSpCluster::_HandleNodeNotification(
                          this,
                          (struct _NOTIFY_FILTER_AND_TYPE *)&v43,
                          (const unsigned __int16 *)v6,
                          (unsigned __int8 *)v5,
                          v36);
                        break;
                      case 8:
                        CSpCluster::_HandleRegistryNotification(
                          this,
                          (struct _NOTIFY_FILTER_AND_TYPE *)&v43,
                          (const unsigned __int16 *)v6);
                        break;
                      case 0xB:
                        SpProcessNotification((struct _SP_NOTIFICATION_INFO *)(v5 + 52));
                        break;
                      default:
                        if ( (unsigned int)dword_180397B68 > 4 )
                        {
                          if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 3072) )
                          {
                            v44[0] = *((_QWORD *)&v43 + 1);
                            LODWORD(v35) = v43;
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                              v20,
                              (__int64)&word_18030434E);
                          }
                        }
                        break;
                    }
                    continue;
                  }
                  if ( !(unsigned int)CSpCluster::_HandleClusterNotification(
                                        v19,
                                        (struct _NOTIFY_FILTER_AND_TYPE *)&v43) )
                    continue;
                }
                LODWORD(v39) = 0;
              }
              break;
            }
LABEL_48:
            if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 2) != 0 )
            {
              v21 = _status_t::ToWin32((_status_t *)&v39);
              McTemplateU0d_EventWriteTransfer(v23, v22, v21);
            }
            if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
            {
              v44[0] = "Disconnected";
              v35 = "Node";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v24,
                (__int64)byte_1803028E3,
                v25,
                v26,
                &v35,
                v44);
            }
          }
        }
      }
    }
  }
  else
  {
    v10 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
    &v42,
    0);
  if ( v10 )
    CloseClusterNotifyPort(v10);
  CSpCluster::_UninitializeClusterState(this, 1);
  if ( v7 )
    LocalFree(v7);
  if ( v6 )
    LocalFree(v6);
  if ( v5 )
    LocalFree(v5);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v35) = 3531;
    v44[0] = "CSpCluster::_ListenForClusterNotifications";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)&byte_1803059D7,
      v28,
      v29,
      v44);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v42);
}

```

## disassembly

```asm
0x18004edb8  push    rbp
0x18004edba  push    rbx
0x18004edbb  push    rsi
0x18004edbc  push    rdi
0x18004edbd  push    r12
0x18004edbf  push    r13
0x18004edc1  push    r14
0x18004edc3  push    r15
0x18004edc5  lea     rbp, [rsp-1Fh]
0x18004edca  sub     rsp, 0E8h
0x18004edd1  mov     rax, cs:__security_cookie
0x18004edd8  xor     rax, rsp
0x18004eddb  mov     [rbp+57h+var_50], rax
0x18004eddf  mov     rdi, rcx
0x18004ede2  mov     eax, cs:dword_180397B68
0x18004ede8  lea     rcx, aCspclusterList; "CSpCluster::_ListenForClusterNotificati"...
0x18004edef  cmp     eax, 5
0x18004edf2  jbe     short loc_18004EE1D
0x18004edf4  mov     [rbp+57h+var_B0], 0CCAh
0x18004edfb  mov     [rbp+57h+var_78], rcx
0x18004edff  lea     rax, [rbp+57h+var_B0]
0x18004ee03  mov     [rsp+120h+var_F8], rax
0x18004ee08  lea     rax, [rbp+57h+var_78]
0x18004ee0c  mov     qword ptr [rsp+120h+var_100], rax
0x18004ee11  lea     rdx, word_1803022E2
0x18004ee18  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004ee1d  xor     r12d, r12d
0x18004ee20  mov     r14d, r12d
0x18004ee23  mov     [rbp+57h+var_A0], r12d
0x18004ee27  xorps   xmm0, xmm0
0x18004ee2a  movups  [rbp+57h+var_70], xmm0
0x18004ee2e  mov     [rbp+57h+var_B0], r12d
0x18004ee32  mov     [rbp+57h+var_80], r12
0x18004ee36  mov     esi, r12d
0x18004ee39  mov     [rbp+57h+var_98], 27h ; '''
0x18004ee40  mov     r15d, r12d
0x18004ee43  mov     [rbp+57h+var_9C], r12d
0x18004ee47  mov     [rbp+57h+var_90], r12
0x18004ee4b  mov     [rbp+57h+var_88], r12b
0x18004ee4f  lea     rdx, [rdi+8]
0x18004ee53  lea     rcx, [rbp+57h+var_78]
0x18004ee57  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004ee5c  nop
0x18004ee5d  mov     rdx, [rdi+48h]
0x18004ee61  lea     r13d, [r12+1]
0x18004ee66  test    rdx, rdx
0x18004ee69  jz      loc_18004F3A1
0x18004ee6f  mov     dword ptr [rbp+57h+var_70], r13d
0x18004ee73  mov     qword ptr [rbp+57h+var_70+8], 400h
0x18004ee7b  mov     rax, [rbp+57h+var_80]
0x18004ee7f  mov     qword ptr [rsp+120h+var_100], rax
0x18004ee84  mov     r9d, r13d
0x18004ee87  lea     r8, [rbp+57h+var_70]
0x18004ee8b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004ee8f  call    cs:__imp_CreateClusterNotifyPortV2
0x18004ee95  mov     rbx, rax
0x18004ee98  test    rax, rax
0x18004ee9b  jz      loc_18004F3A4
0x18004eea1  mov     dword ptr [rbp+57h+var_70], 7
0x18004eea8  mov     qword ptr [rbp+57h+var_70+8], 92h
0x18004eeb0  mov     rcx, [rbp+57h+var_80]
0x18004eeb4  mov     qword ptr [rsp+120h+var_100], rcx
0x18004eeb9  mov     r9d, r13d
0x18004eebc  lea     r8, [rbp+57h+var_70]
0x18004eec0  mov     rdx, [rdi+48h]
0x18004eec4  mov     rcx, rax
0x18004eec7  call    cs:__imp_CreateClusterNotifyPortV2
0x18004eecd  mov     rbx, rax
0x18004eed0  test    rax, rax
0x18004eed3  jz      loc_18004F3A4
0x18004eed9  mov     dword ptr [rbp+57h+var_70], 0Bh
0x18004eee0  mov     qword ptr [rbp+57h+var_70+8], r13
0x18004eee4  mov     rax, [rbp+57h+var_80]
0x18004eee8  mov     qword ptr [rsp+120h+var_100], rax
0x18004eeed  mov     r9d, r13d
0x18004eef0  lea     r8, [rbp+57h+var_70]
0x18004eef4  mov     rdx, [rdi+48h]
0x18004eef8  mov     rcx, rbx
0x18004eefb  call    cs:__imp_CreateClusterNotifyPortV2
0x18004ef01  mov     rbx, rax
0x18004ef04  test    rax, rax
0x18004ef07  jz      loc_18004F3A4
0x18004ef0d  mov     dword ptr [rbp+57h+var_70], 8
0x18004ef14  mov     qword ptr [rbp+57h+var_70+8], 0Ch
0x18004ef1c  mov     rax, [rbp+57h+var_80]
0x18004ef20  mov     qword ptr [rsp+120h+var_100], rax
0x18004ef25  mov     r9d, r13d
0x18004ef28  lea     r8, [rbp+57h+var_70]
0x18004ef2c  mov     rdx, [rdi+48h]
0x18004ef30  mov     rcx, rbx
0x18004ef33  call    cs:__imp_CreateClusterNotifyPortV2
0x18004ef39  mov     rbx, rax
0x18004ef3c  test    rax, rax
0x18004ef3f  jz      loc_18004F3A4
0x18004ef45  xor     edx, edx
0x18004ef47  lea     rcx, [rbp+57h+var_78]
0x18004ef4b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18004ef50  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 4
0x18004ef57  jz      short loc_18004EF78
0x18004ef59  lea     rax, [rbp+57h+var_60]
0x18004ef5d  mov     qword ptr [rsp+120h+var_100], rax
0x18004ef62  mov     r9d, r13d
0x18004ef65  lea     rdx, ClusterConnected
0x18004ef6c  lea     rcx, LOG_PROVIDER_GUID_Context
0x18004ef73  call    McGenEventWrite_EventWriteTransfer
0x18004ef78  mov     eax, cs:dword_180397B68
0x18004ef7e  lea     r8, aNode; "Node"
0x18004ef85  cmp     eax, 5
0x18004ef88  jbe     short loc_18004EFD1
0x18004ef8a  mov     rdx, 400000000000h
0x18004ef94  lea     rcx, dword_180397B68
0x18004ef9b  call    _tlgKeywordOn
0x18004efa0  test    al, al
0x18004efa2  jz      short loc_18004EFD1
0x18004efa4  lea     rax, aConnected; "Connected"
0x18004efab  mov     [rbp+57h+var_A8], rax
0x18004efaf  mov     [rbp+57h+var_60], r8
0x18004efb3  lea     rax, [rbp+57h+var_A8]
0x18004efb7  mov     [rsp+120h+var_F8], rax
0x18004efbc  lea     rax, [rbp+57h+var_60]
0x18004efc0  mov     qword ptr [rsp+120h+var_100], rax
0x18004efc5  lea     rdx, word_180303BBA
0x18004efcc  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18004efd1  lea     rdx, [rbp+57h+var_B0]; int *
0x18004efd5  xor     ecx, ecx; unsigned __int16 *
0x18004efd7  call    ?SmIsClusteredNode@@YAHPEBGPEAH@Z; SmIsClusteredNode(ushort const *,int *)
0x18004efdc  test    eax, eax
0x18004efde  jz      loc_18004F271
0x18004efe4  cmp     [rbp+57h+var_B0], r12d
0x18004efe8  jz      loc_18004F271
0x18004efee  mov     rcx, rdi; this
0x18004eff1  call    ?IsClusterUp@CSpCluster@@QEAAHXZ; CSpCluster::IsClusterUp(void)
0x18004eff6  test    eax, eax
0x18004eff8  jz      loc_18004F271
0x18004effe  xor     edx, edx; dwMilliseconds
0x18004f000  mov     rcx, [rdi+40h]; hHandle
0x18004f004  call    cs:__imp_WaitForSingleObject
0x18004f00a  test    eax, eax
0x18004f00c  jz      loc_18004F26D
0x18004f012  mov     eax, 100h
0x18004f017  mov     [rbp+57h+var_A0], eax
0x18004f01a  mov     [rbp+57h+var_9C], eax
0x18004f01d  mov     [rbp+57h+var_98], 27h ; '''
0x18004f024  mov     dword ptr [rbp+57h+var_90], 800700EAh
0x18004f02b  jmp     loc_18004F121
0x18004f030  test    r14, r14
0x18004f033  jz      short loc_18004F03E
0x18004f035  mov     rcx, r14; hMem
0x18004f038  call    cs:__imp_LocalFree
0x18004f03e  test    rsi, rsi
0x18004f041  jz      short loc_18004F04C
0x18004f043  mov     rcx, rsi; hMem
0x18004f046  call    cs:__imp_LocalFree
0x18004f04c  test    r15, r15
0x18004f04f  jz      short loc_18004F05A
0x18004f051  mov     rcx, r15; hMem
0x18004f054  call    cs:__imp_LocalFree
0x18004f05a  mov     eax, [rbp+57h+var_A0]
0x18004f05d  add     eax, r13d
0x18004f060  mov     [rbp+57h+var_A0], eax
0x18004f063  mov     edx, eax; uBytes
0x18004f065  xor     ecx, ecx; uFlags
0x18004f067  call    cs:__imp_LocalAlloc
0x18004f06d  mov     r14, rax
0x18004f070  mov     eax, [rbp+57h+var_98]
0x18004f073  add     eax, r13d
0x18004f076  mov     [rbp+57h+var_98], eax
0x18004f079  mov     edx, eax
0x18004f07b  add     rdx, rdx; uBytes
0x18004f07e  xor     ecx, ecx; uFlags
0x18004f080  call    cs:__imp_LocalAlloc
0x18004f086  mov     rsi, rax
0x18004f089  mov     eax, [rbp+57h+var_9C]
0x18004f08c  add     eax, r13d
0x18004f08f  mov     [rbp+57h+var_9C], eax
0x18004f092  mov     edx, eax
0x18004f094  add     rdx, rdx; uBytes
0x18004f097  xor     ecx, ecx; uFlags
0x18004f099  call    cs:__imp_LocalAlloc
0x18004f09f  mov     r15, rax
0x18004f0a2  test    r14, r14
0x18004f0a5  jz      loc_18004F2F1
0x18004f0ab  test    rsi, rsi
0x18004f0ae  jz      loc_18004F2F1
0x18004f0b4  test    rax, rax
0x18004f0b7  jz      loc_18004F2F1
0x18004f0bd  mov     [rsp+120h+var_B8], 9C4h
0x18004f0c5  mov     [rsp+120h+var_C0], r12
0x18004f0ca  mov     [rsp+120h+var_C8], r12
0x18004f0cf  lea     rax, [rbp+57h+var_9C]
0x18004f0d3  mov     [rsp+120h+var_D0], rax
0x18004f0d8  mov     [rsp+120h+var_D8], r15
0x18004f0dd  mov     [rsp+120h+var_E0], r12
0x18004f0e2  mov     [rsp+120h+var_E8], r12
0x18004f0e7  lea     rax, [rbp+57h+var_98]
0x18004f0eb  mov     [rsp+120h+var_F0], rax
0x18004f0f0  mov     [rsp+120h+var_F8], rsi
0x18004f0f5  lea     rax, [rbp+57h+var_A0]
0x18004f0f9  mov     qword ptr [rsp+120h+var_100], rax
0x18004f0fe  mov     r9, r14
0x18004f101  lea     r8, [rbp+57h+var_70]
0x18004f105  lea     rdx, [rbp+57h+var_80]
0x18004f109  mov     rcx, rbx
0x18004f10c  call    cs:__imp_GetClusterNotifyV2
0x18004f112  test    eax, eax
0x18004f114  jle     short loc_18004F11E
0x18004f116  movzx   eax, ax
0x18004f119  or      eax, 80070000h
0x18004f11e  mov     dword ptr [rbp+57h+var_90], eax
0x18004f121  lea     rcx, [rbp+57h+var_90]; this
0x18004f125  call    ?ToWin32@_status_t@@QEAAKXZ; _status_t::ToWin32(void)
0x18004f12a  cmp     eax, 0EAh
0x18004f12f  jz      loc_18004F030
0x18004f135  lea     rcx, [rbp+57h+var_90]; this
0x18004f139  call    ?ToWin32@_status_t@@QEAAKXZ; _status_t::ToWin32(void)
0x18004f13e  cmp     eax, 6
0x18004f141  jz      loc_18004F349
0x18004f147  lea     rcx, [rbp+57h+var_90]; this
0x18004f14b  call    ?ToWin32@_status_t@@QEAAKXZ; _status_t::ToWin32(void)
0x18004f150  test    eax, eax
0x18004f152  jnz     loc_18004EFD1
0x18004f158  mov     eax, cs:dword_180397B68
0x18004f15e  cmp     eax, 4
0x18004f161  jbe     short loc_18004F1A4
0x18004f163  mov     edx, 0C00h
0x18004f168  lea     rcx, dword_180397B68
0x18004f16f  call    _tlgKeywordOn
0x18004f174  test    al, al
0x18004f176  jz      short loc_18004F1A4
0x18004f178  mov     rax, qword ptr [rbp+57h+var_70+8]
0x18004f17c  mov     [rbp+57h+var_60], rax
0x18004f180  mov     eax, dword ptr [rbp+57h+var_70]
0x18004f183  mov     dword ptr [rbp+57h+var_A8], eax
0x18004f186  lea     rax, [rbp+57h+var_60]
0x18004f18a  mov     [rsp+120h+var_F8], rax
0x18004f18f  lea     rax, [rbp+57h+var_A8]
0x18004f193  mov     qword ptr [rsp+120h+var_100], rax
0x18004f198  lea     rdx, byte_180303EE1
0x18004f19f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18004f1a4  mov     eax, dword ptr [rbp+57h+var_70]
0x18004f1a7  sub     eax, r13d
0x18004f1aa  jz      loc_18004F25C
0x18004f1b0  sub     eax, 6
0x18004f1b3  jz      loc_18004F23E
0x18004f1b9  sub     eax, r13d
0x18004f1bc  jz      short loc_18004F22A
0x18004f1be  cmp     eax, 3
0x18004f1c1  jz      short loc_18004F21C
0x18004f1c3  mov     eax, cs:dword_180397B68
0x18004f1c9  cmp     eax, 4
0x18004f1cc  jbe     loc_18004EFD1
0x18004f1d2  mov     edx, 0C00h
0x18004f1d7  lea     rcx, dword_180397B68
0x18004f1de  call    _tlgKeywordOn
0x18004f1e3  test    al, al
0x18004f1e5  jz      loc_18004EFD1
0x18004f1eb  mov     rax, qword ptr [rbp+57h+var_70+8]
0x18004f1ef  mov     [rbp+57h+var_60], rax
0x18004f1f3  mov     eax, dword ptr [rbp+57h+var_70]
0x18004f1f6  mov     dword ptr [rbp+57h+var_A8], eax
0x18004f1f9  lea     rax, [rbp+57h+var_60]
0x18004f1fd  mov     [rsp+120h+var_F8], rax
0x18004f202  lea     rax, [rbp+57h+var_A8]
0x18004f206  mov     qword ptr [rsp+120h+var_100], rax
0x18004f20b  lea     rdx, word_18030434E
0x18004f212  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18004f217  jmp     loc_18004EFD1
0x18004f21c  lea     rcx, [r14+34h]; struct _SP_NOTIFICATION_INFO *
0x18004f220  call    ?SpProcessNotification@@YA?AW4_MI_Result@@PEAU_SP_NOTIFICATION_INFO@@@Z; SpProcessNotification(_SP_NOTIFICATION_INFO *)
0x18004f225  jmp     loc_18004EFD1
0x18004f22a  mov     r8, rsi; unsigned __int16 *
0x18004f22d  lea     rdx, [rbp+57h+var_70]; struct _NOTIFY_FILTER_AND_TYPE *
0x18004f231  mov     rcx, rdi; this
0x18004f234  call    ?_HandleRegistryNotification@CSpCluster@@AEAAXAEAU_NOTIFY_FILTER_AND_TYPE@@PEBG@Z; CSpCluster::_HandleRegistryNotification(_NOTIFY_FILTER_AND_TYPE &,ushort const *)
0x18004f239  jmp     loc_18004EFD1
0x18004f23e  mov     eax, [rbp+57h+var_A0]
0x18004f241  mov     [rsp+120h+var_100], eax; unsigned int
0x18004f245  mov     r9, r14; unsigned __int8 *
0x18004f248  mov     r8, rsi; unsigned __int16 *
0x18004f24b  lea     rdx, [rbp+57h+var_70]; struct _NOTIFY_FILTER_AND_TYPE *
0x18004f24f  mov     rcx, rdi; this
0x18004f252  call    ?_HandleNodeNotification@CSpCluster@@AEAAXAEAU_NOTIFY_FILTER_AND_TYPE@@PEBGPEAEK@Z; CSpCluster::_HandleNodeNotification(_NOTIFY_FILTER_AND_TYPE &,ushort const *,uchar *,ulong)
0x18004f257  jmp     loc_18004EFD1
0x18004f25c  lea     rdx, [rbp+57h+var_70]; struct _NOTIFY_FILTER_AND_TYPE *
0x18004f260  call    ?_HandleClusterNotification@CSpCluster@@AEAAHAEAU_NOTIFY_FILTER_AND_TYPE@@@Z; CSpCluster::_HandleClusterNotification(_NOTIFY_FILTER_AND_TYPE &)
0x18004f265  test    eax, eax
0x18004f267  jz      loc_18004EFD1
0x18004f26d  mov     dword ptr [rbp+57h+var_90], r12d
0x18004f271  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 2
0x18004f278  jz      short loc_18004F28B
0x18004f27a  lea     rcx, [rbp+57h+var_90]; this
0x18004f27e  call    ?ToWin32@_status_t@@QEAAKXZ; _status_t::ToWin32(void)
0x18004f283  mov     r8d, eax
0x18004f286  call    McTemplateU0d_EventWriteTransfer
0x18004f28b  mov     eax, cs:dword_180397B68
0x18004f291  cmp     eax, 5
0x18004f294  jbe     loc_18004F3A4
0x18004f29a  mov     rdx, 400000000000h
0x18004f2a4  lea     rcx, dword_180397B68
0x18004f2ab  call    _tlgKeywordOn
  ... truncated ...
```

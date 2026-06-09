# CSpCluster::_ListenForClusterNotifications(void)

- ea: `0x1800506b4`
- end: `0x180050db4`
- name: `?_ListenForClusterNotifications@CSpCluster@@AEAAXXZ`
- size: `1792`
- prototype: `void __fastcall(CSpCluster *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004eb20`

## callees

- `0x1800011c4`
- `0x1800014a8`
- `0x180001504`
- `0x1800015d8`
- `0x180002390`
- `0x180002464`
- `0x180006350`
- `0x18000d47c`
- `0x18000e3ac`
- `0x18000f100`
- `0x18003a1c8`
- `0x18004d450`
- `0x18004f854`
- `0x18004f8b4`
- `0x18004fa88`
- `0x1800506b4`
- `0x180051d7c`
- `0x180052074`
- `0x1800520d0`
- `0x180068be8`
- `0x1801b2fb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180050918`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180050918`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050952`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050966`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005097a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050d1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050d2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050d42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050952`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050966`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005097a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050d1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050d2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050d42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180050993`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800509b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800509d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180050993`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800509b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800509d1`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x18005078b`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x1800507c9`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x180050803`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x180050841`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x18005078b`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x1800507c9`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x180050803`
- `ext-ms-win-cluster-clusapi-l1-1-1!CreateClusterNotifyPortV2` at `0x180050841`
- `ext-ms-win-cluster-clusapi-l1-1-1!CloseClusterNotifyPort` at `0x180050cfb`
- `ext-ms-win-cluster-clusapi-l1-1-1!CloseClusterNotifyPort` at `0x180050cfb`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNotifyV2` at `0x180050a4a`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNotifyV2` at `0x180050a4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSpCluster::_ListenForClusterNotifications(CSpCluster *this, __int64 a2, int a3, int a4)
{
  char *v5; // r14
  HLOCAL v6; // rsi
  void *v7; // r15
  __int64 v8; // rdx
  __int64 v9; // rax
  struct _HCHANGE *v10; // rbx
  __int64 v11; // r8
  int v12; // ecx
  __int64 v13; // r8
  int v14; // r9d
  HLOCAL v15; // rax
  int v16; // r8d
  int v17; // r9d
  signed int ClusterNotifyV2; // eax
  CSpCluster *v19; // rcx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v31; // r9d
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int v35; // [rsp+70h] [rbp-59h] BYREF
  const char *v36; // [rsp+78h] [rbp-51h] BYREF
  unsigned int v37; // [rsp+80h] [rbp-49h] BYREF
  int v38; // [rsp+84h] [rbp-45h] BYREF
  int v39; // [rsp+88h] [rbp-41h] BYREF
  __int64 v40; // [rsp+90h] [rbp-39h] BYREF
  char v41; // [rsp+98h] [rbp-31h]
  __int64 v42; // [rsp+A0h] [rbp-29h] BYREF
  const char *v43; // [rsp+A8h] [rbp-21h] BYREF
  __int128 v44; // [rsp+B0h] [rbp-19h] BYREF
  _QWORD v45[2]; // [rsp+C0h] [rbp-9h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v35 = 3274;
    v43 = "CSpCluster::_ListenForClusterNotifications";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"CSpCluster::_ListenForClusterNotifications",
      (unsigned int)word_18030926A,
      a3,
      a4,
      (__int64)&v43,
      (__int64)&v35);
  }
  v5 = 0;
  v37 = 0;
  v44 = 0;
  v35 = 0;
  v42 = 0;
  v6 = 0;
  v39 = 39;
  v7 = 0;
  v38 = 0;
  v40 = 0;
  v41 = 0;
  wil::EnterCriticalSection(&v43, (char *)this + 8);
  v8 = *((_QWORD *)this + 9);
  if ( v8 )
  {
    LODWORD(v44) = 1;
    *((_QWORD *)&v44 + 1) = 1024;
    v9 = CreateClusterNotifyPortV2(-1, v8, &v44, 1, v42);
    v10 = (struct _HCHANGE *)v9;
    if ( v9 )
    {
      LODWORD(v44) = 7;
      *((_QWORD *)&v44 + 1) = 146;
      v10 = (struct _HCHANGE *)CreateClusterNotifyPortV2(v9, *((_QWORD *)this + 9), &v44, 1, v42);
      if ( v10 )
      {
        LODWORD(v44) = 11;
        *((_QWORD *)&v44 + 1) = 1;
        v10 = (struct _HCHANGE *)CreateClusterNotifyPortV2(v10, *((_QWORD *)this + 9), &v44, 1, v42);
        if ( v10 )
        {
          LODWORD(v44) = 8;
          *((_QWORD *)&v44 + 1) = 12;
          v10 = (struct _HCHANGE *)CreateClusterNotifyPortV2(v10, *((_QWORD *)this + 9), &v44, 1, v42);
          if ( v10 )
          {
            wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
              &v43,
              0);
            if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 4) != 0 )
              McGenEventWrite_EventWriteTransfer(LOG_PROVIDER_GUID_Context, ClusterConnected, v11, 1, v45);
            if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
            {
              v36 = "Connected";
              v45[0] = v13;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v12,
                (unsigned int)word_18030AB42,
                v13,
                v14,
                (__int64)v45,
                (__int64)&v36);
            }
            while ( 2 )
            {
              if ( (unsigned int)SmIsClusteredNode(0, &v35) && v35 && (unsigned int)CSpCluster::IsClusterUp(this) )
              {
                if ( WaitForSingleObject(*((HANDLE *)this + 8), 0) )
                {
                  v37 = 256;
                  v38 = 256;
                  v39 = 39;
                  LODWORD(v40) = -2147024662;
                  while ( _status_t::ToWin32((_status_t *)&v40) == 234 )
                  {
                    if ( v5 )
                      LocalFree(v5);
                    if ( v6 )
                      LocalFree(v6);
                    if ( v7 )
                      LocalFree(v7);
                    v5 = (char *)LocalAlloc(0, ++v37);
                    v6 = LocalAlloc(0, 2LL * (unsigned int)++v39);
                    v15 = LocalAlloc(0, 2LL * (unsigned int)++v38);
                    v7 = v15;
                    if ( !v5 || !v6 || !v15 )
                    {
                      LODWORD(v40) = -2147024882;
                      if ( (unsigned int)dword_18039EB68 > 2 )
                      {
                        LODWORD(v36) = -2147024882;
                        v35 = 3417;
                        v45[0] = "CSpCluster::_ListenForClusterNotifications";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                          -2147024882,
                          (unsigned int)byte_18030B3B9,
                          v16,
                          v17,
                          (__int64)v45,
                          (__int64)&v35,
                          (__int64)&v36);
                      }
                      goto LABEL_48;
                    }
                    ClusterNotifyV2 = GetClusterNotifyV2(
                                        v10,
                                        &v42,
                                        &v44,
                                        v5,
                                        &v37,
                                        v6,
                                        &v39,
                                        0,
                                        0,
                                        v15,
                                        &v38,
                                        0,
                                        0,
                                        2500);
                    if ( ClusterNotifyV2 > 0 )
                      ClusterNotifyV2 = (unsigned __int16)ClusterNotifyV2 | 0x80070000;
                    LODWORD(v40) = ClusterNotifyV2;
                  }
                  if ( _status_t::ToWin32((_status_t *)&v40) == 6 )
                  {
                    if ( (unsigned int)dword_18039EB68 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 3072) )
                    {
                      LODWORD(v36) = SmIsClusteredNode(0, 0);
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                        (unsigned int)&dword_18039EB68,
                        (unsigned int)byte_180308AFB,
                        0,
                        v31,
                        (__int64)&v36);
                    }
                    break;
                  }
                  if ( _status_t::ToWin32((_status_t *)&v40) )
                    continue;
                  if ( (unsigned int)dword_18039EB68 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 3072) )
                  {
                    v45[0] = *((_QWORD *)&v44 + 1);
                    LODWORD(v36) = v44;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      (_DWORD)v19,
                      (unsigned int)byte_18030AE69,
                      v20,
                      v21,
                      (__int64)&v36,
                      (__int64)v45);
                  }
                  if ( (_DWORD)v44 != 1 )
                  {
                    switch ( (_DWORD)v44 )
                    {
                      case 7:
                        CSpCluster::_HandleNodeNotification(
                          this,
                          (struct _NOTIFY_FILTER_AND_TYPE *)&v44,
                          (const unsigned __int16 *)v6,
                          (unsigned __int8 *)v5,
                          v37);
                        break;
                      case 8:
                        CSpCluster::_HandleRegistryNotification(
                          this,
                          (struct _NOTIFY_FILTER_AND_TYPE *)&v44,
                          (const unsigned __int16 *)v6);
                        break;
                      case 0xB:
                        SpProcessNotification((struct _SP_NOTIFICATION_INFO *)(v5 + 52));
                        break;
                      default:
                        if ( (unsigned int)dword_18039EB68 > 4 )
                        {
                          if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 3072) )
                          {
                            v45[0] = *((_QWORD *)&v44 + 1);
                            LODWORD(v36) = v44;
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                              v22,
                              (unsigned int)&word_18030B2D6,
                              v23,
                              v24,
                              (__int64)&v36,
                              (__int64)v45);
                          }
                        }
                        break;
                    }
                    continue;
                  }
                  if ( !(unsigned int)CSpCluster::_HandleClusterNotification(
                                        v19,
                                        (struct _NOTIFY_FILTER_AND_TYPE *)&v44) )
                    continue;
                }
                LODWORD(v40) = 0;
              }
              break;
            }
LABEL_48:
            if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 2) != 0 )
            {
              v25 = _status_t::ToWin32((_status_t *)&v40);
              McTemplateU0d_EventWriteTransfer(v27, v26, v25);
            }
            if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
            {
              v45[0] = "Disconnected";
              v36 = "Node";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v28,
                (unsigned int)byte_18030986B,
                v29,
                v30,
                (__int64)&v36,
                (__int64)v45);
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
    &v43,
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
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v36) = 3531;
    v45[0] = "CSpCluster::_ListenForClusterNotifications";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v32,
      (unsigned int)&byte_18030C95F,
      v33,
      v34,
      (__int64)v45,
      (__int64)&v36);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v43);
}

```

## disassembly

```asm
0x1800506b4  push    rbp
0x1800506b6  push    rbx
0x1800506b7  push    rsi
0x1800506b8  push    rdi
0x1800506b9  push    r12
0x1800506bb  push    r13
0x1800506bd  push    r14
0x1800506bf  push    r15
0x1800506c1  lea     rbp, [rsp-1Fh]
0x1800506c6  sub     rsp, 0E8h
0x1800506cd  mov     rax, cs:__security_cookie
0x1800506d4  xor     rax, rsp
0x1800506d7  mov     [rbp+57h+var_50], rax
0x1800506db  mov     rdi, rcx
0x1800506de  mov     eax, cs:dword_18039EB68
0x1800506e4  lea     rcx, aCspclusterList; "CSpCluster::_ListenForClusterNotificati"...
0x1800506eb  cmp     eax, 5
0x1800506ee  jbe     short loc_180050719
0x1800506f0  mov     [rbp+57h+var_B0], 0CCAh
0x1800506f7  mov     [rbp+57h+var_78], rcx
0x1800506fb  lea     rax, [rbp+57h+var_B0]
0x1800506ff  mov     [rsp+120h+var_F8], rax
0x180050704  lea     rax, [rbp+57h+var_78]
0x180050708  mov     qword ptr [rsp+120h+var_100], rax
0x18005070d  lea     rdx, word_18030926A
0x180050714  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180050719  xor     r12d, r12d
0x18005071c  mov     r14d, r12d
0x18005071f  mov     [rbp+57h+var_A0], r12d
0x180050723  xorps   xmm0, xmm0
0x180050726  movups  [rbp+57h+var_70], xmm0
0x18005072a  mov     [rbp+57h+var_B0], r12d
0x18005072e  mov     [rbp+57h+var_80], r12
0x180050732  mov     esi, r12d
0x180050735  mov     [rbp+57h+var_98], 27h ; '''
0x18005073c  mov     r15d, r12d
0x18005073f  mov     [rbp+57h+var_9C], r12d
0x180050743  mov     [rbp+57h+var_90], r12
0x180050747  mov     [rbp+57h+var_88], r12b
0x18005074b  lea     rdx, [rdi+8]
0x18005074f  lea     rcx, [rbp+57h+var_78]
0x180050753  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180050758  nop
0x180050759  mov     rdx, [rdi+48h]
0x18005075d  lea     r13d, [r12+1]
0x180050762  test    rdx, rdx
0x180050765  jz      loc_180050CE5
0x18005076b  mov     dword ptr [rbp+57h+var_70], r13d
0x18005076f  mov     qword ptr [rbp+57h+var_70+8], 400h
0x180050777  mov     rax, [rbp+57h+var_80]
0x18005077b  mov     qword ptr [rsp+120h+var_100], rax
0x180050780  mov     r9d, r13d
0x180050783  lea     r8, [rbp+57h+var_70]
0x180050787  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005078b  call    cs:__imp_CreateClusterNotifyPortV2
0x180050792  nop     dword ptr [rax+rax+00h]
0x180050797  mov     rbx, rax
0x18005079a  test    rax, rax
0x18005079d  jz      loc_180050CE8
0x1800507a3  mov     dword ptr [rbp+57h+var_70], 7
0x1800507aa  mov     qword ptr [rbp+57h+var_70+8], 92h
0x1800507b2  mov     rcx, [rbp+57h+var_80]
0x1800507b6  mov     qword ptr [rsp+120h+var_100], rcx
0x1800507bb  mov     r9d, r13d
0x1800507be  lea     r8, [rbp+57h+var_70]
0x1800507c2  mov     rdx, [rdi+48h]
0x1800507c6  mov     rcx, rax
0x1800507c9  call    cs:__imp_CreateClusterNotifyPortV2
0x1800507d0  nop     dword ptr [rax+rax+00h]
0x1800507d5  mov     rbx, rax
0x1800507d8  test    rax, rax
0x1800507db  jz      loc_180050CE8
0x1800507e1  mov     dword ptr [rbp+57h+var_70], 0Bh
0x1800507e8  mov     qword ptr [rbp+57h+var_70+8], r13
0x1800507ec  mov     rax, [rbp+57h+var_80]
0x1800507f0  mov     qword ptr [rsp+120h+var_100], rax
0x1800507f5  mov     r9d, r13d
0x1800507f8  lea     r8, [rbp+57h+var_70]
0x1800507fc  mov     rdx, [rdi+48h]
0x180050800  mov     rcx, rbx
0x180050803  call    cs:__imp_CreateClusterNotifyPortV2
0x18005080a  nop     dword ptr [rax+rax+00h]
0x18005080f  mov     rbx, rax
0x180050812  test    rax, rax
0x180050815  jz      loc_180050CE8
0x18005081b  mov     dword ptr [rbp+57h+var_70], 8
0x180050822  mov     qword ptr [rbp+57h+var_70+8], 0Ch
0x18005082a  mov     rax, [rbp+57h+var_80]
0x18005082e  mov     qword ptr [rsp+120h+var_100], rax
0x180050833  mov     r9d, r13d
0x180050836  lea     r8, [rbp+57h+var_70]
0x18005083a  mov     rdx, [rdi+48h]
0x18005083e  mov     rcx, rbx
0x180050841  call    cs:__imp_CreateClusterNotifyPortV2
0x180050848  nop     dword ptr [rax+rax+00h]
0x18005084d  mov     rbx, rax
0x180050850  test    rax, rax
0x180050853  jz      loc_180050CE8
0x180050859  xor     edx, edx
0x18005085b  lea     rcx, [rbp+57h+var_78]
0x18005085f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x180050864  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 4
0x18005086b  jz      short loc_18005088C
0x18005086d  lea     rax, [rbp+57h+var_60]
0x180050871  mov     qword ptr [rsp+120h+var_100], rax
0x180050876  mov     r9d, r13d
0x180050879  lea     rdx, ClusterConnected
0x180050880  lea     rcx, LOG_PROVIDER_GUID_Context
0x180050887  call    McGenEventWrite_EventWriteTransfer
0x18005088c  mov     eax, cs:dword_18039EB68
0x180050892  lea     r8, aNode; "Node"
0x180050899  cmp     eax, 5
0x18005089c  jbe     short loc_1800508E5
0x18005089e  mov     rdx, 400000000000h
0x1800508a8  lea     rcx, dword_18039EB68
0x1800508af  call    _tlgKeywordOn
0x1800508b4  test    al, al
0x1800508b6  jz      short loc_1800508E5
0x1800508b8  lea     rax, aConnected; "Connected"
0x1800508bf  mov     [rbp+57h+var_A8], rax
0x1800508c3  mov     [rbp+57h+var_60], r8
0x1800508c7  lea     rax, [rbp+57h+var_A8]
0x1800508cb  mov     [rsp+120h+var_F8], rax
0x1800508d0  lea     rax, [rbp+57h+var_60]
0x1800508d4  mov     qword ptr [rsp+120h+var_100], rax
0x1800508d9  lea     rdx, word_18030AB42
0x1800508e0  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800508e5  lea     rdx, [rbp+57h+var_B0]; int *
0x1800508e9  xor     ecx, ecx; unsigned __int16 *
0x1800508eb  call    ?SmIsClusteredNode@@YAHPEBGPEAH@Z; SmIsClusteredNode(ushort const *,int *)
0x1800508f0  test    eax, eax
0x1800508f2  jz      loc_180050BB5
0x1800508f8  cmp     [rbp+57h+var_B0], r12d
0x1800508fc  jz      loc_180050BB5
0x180050902  mov     rcx, rdi; this
0x180050905  call    ?IsClusterUp@CSpCluster@@QEAAHXZ; CSpCluster::IsClusterUp(void)
0x18005090a  test    eax, eax
0x18005090c  jz      loc_180050BB5
0x180050912  xor     edx, edx; dwMilliseconds
0x180050914  mov     rcx, [rdi+40h]; hHandle
0x180050918  call    cs:__imp_WaitForSingleObject
0x18005091f  nop     dword ptr [rax+rax+00h]
0x180050924  test    eax, eax
0x180050926  jz      loc_180050BB1
0x18005092c  mov     eax, 100h
0x180050931  mov     [rbp+57h+var_A0], eax
0x180050934  mov     [rbp+57h+var_9C], eax
0x180050937  mov     [rbp+57h+var_98], 27h ; '''
0x18005093e  mov     dword ptr [rbp+57h+var_90], 800700EAh
0x180050945  jmp     loc_180050A65
0x18005094a  test    r14, r14
0x18005094d  jz      short loc_18005095E
0x18005094f  mov     rcx, r14; hMem
0x180050952  call    cs:__imp_LocalFree
0x180050959  nop     dword ptr [rax+rax+00h]
0x18005095e  test    rsi, rsi
0x180050961  jz      short loc_180050972
0x180050963  mov     rcx, rsi; hMem
0x180050966  call    cs:__imp_LocalFree
0x18005096d  nop     dword ptr [rax+rax+00h]
0x180050972  test    r15, r15
0x180050975  jz      short loc_180050986
0x180050977  mov     rcx, r15; hMem
0x18005097a  call    cs:__imp_LocalFree
0x180050981  nop     dword ptr [rax+rax+00h]
0x180050986  mov     eax, [rbp+57h+var_A0]
0x180050989  add     eax, r13d
0x18005098c  mov     [rbp+57h+var_A0], eax
0x18005098f  mov     edx, eax; uBytes
0x180050991  xor     ecx, ecx; uFlags
0x180050993  call    cs:__imp_LocalAlloc
0x18005099a  nop     dword ptr [rax+rax+00h]
0x18005099f  mov     r14, rax
0x1800509a2  mov     eax, [rbp+57h+var_98]
0x1800509a5  add     eax, r13d
0x1800509a8  mov     [rbp+57h+var_98], eax
0x1800509ab  mov     edx, eax
0x1800509ad  add     rdx, rdx; uBytes
0x1800509b0  xor     ecx, ecx; uFlags
0x1800509b2  call    cs:__imp_LocalAlloc
0x1800509b9  nop     dword ptr [rax+rax+00h]
0x1800509be  mov     rsi, rax
0x1800509c1  mov     eax, [rbp+57h+var_9C]
0x1800509c4  add     eax, r13d
0x1800509c7  mov     [rbp+57h+var_9C], eax
0x1800509ca  mov     edx, eax
0x1800509cc  add     rdx, rdx; uBytes
0x1800509cf  xor     ecx, ecx; uFlags
0x1800509d1  call    cs:__imp_LocalAlloc
0x1800509d8  nop     dword ptr [rax+rax+00h]
0x1800509dd  mov     r15, rax
0x1800509e0  test    r14, r14
0x1800509e3  jz      loc_180050C35
0x1800509e9  test    rsi, rsi
0x1800509ec  jz      loc_180050C35
0x1800509f2  test    rax, rax
0x1800509f5  jz      loc_180050C35
0x1800509fb  mov     [rsp+120h+var_B8], 9C4h
0x180050a03  mov     [rsp+120h+var_C0], r12
0x180050a08  mov     [rsp+120h+var_C8], r12
0x180050a0d  lea     rax, [rbp+57h+var_9C]
0x180050a11  mov     [rsp+120h+var_D0], rax
0x180050a16  mov     [rsp+120h+var_D8], r15
0x180050a1b  mov     [rsp+120h+var_E0], r12
0x180050a20  mov     [rsp+120h+var_E8], r12
0x180050a25  lea     rax, [rbp+57h+var_98]
0x180050a29  mov     [rsp+120h+var_F0], rax
0x180050a2e  mov     [rsp+120h+var_F8], rsi
0x180050a33  lea     rax, [rbp+57h+var_A0]
0x180050a37  mov     qword ptr [rsp+120h+var_100], rax
0x180050a3c  mov     r9, r14
0x180050a3f  lea     r8, [rbp+57h+var_70]
0x180050a43  lea     rdx, [rbp+57h+var_80]
0x180050a47  mov     rcx, rbx
0x180050a4a  call    cs:__imp_GetClusterNotifyV2
0x180050a51  nop     dword ptr [rax+rax+00h]
0x180050a56  test    eax, eax
0x180050a58  jle     short loc_180050A62
0x180050a5a  movzx   eax, ax
0x180050a5d  or      eax, 80070000h
0x180050a62  mov     dword ptr [rbp+57h+var_90], eax
0x180050a65  lea     rcx, [rbp+57h+var_90]; this
0x180050a69  call    ?ToWin32@_status_t@@QEAAKXZ; _status_t::ToWin32(void)
0x180050a6e  cmp     eax, 0EAh
0x180050a73  jz      loc_18005094A
0x180050a79  lea     rcx, [rbp+57h+var_90]; this
0x180050a7d  call    ?ToWin32@_status_t@@QEAAKXZ; _status_t::ToWin32(void)
0x180050a82  cmp     eax, 6
0x180050a85  jz      loc_180050C8D
0x180050a8b  lea     rcx, [rbp+57h+var_90]; this
0x180050a8f  call    ?ToWin32@_status_t@@QEAAKXZ; _status_t::ToWin32(void)
0x180050a94  test    eax, eax
0x180050a96  jnz     loc_1800508E5
0x180050a9c  mov     eax, cs:dword_18039EB68
0x180050aa2  cmp     eax, 4
0x180050aa5  jbe     short loc_180050AE8
0x180050aa7  mov     edx, 0C00h
0x180050aac  lea     rcx, dword_18039EB68
0x180050ab3  call    _tlgKeywordOn
0x180050ab8  test    al, al
0x180050aba  jz      short loc_180050AE8
0x180050abc  mov     rax, qword ptr [rbp+57h+var_70+8]
0x180050ac0  mov     [rbp+57h+var_60], rax
0x180050ac4  mov     eax, dword ptr [rbp+57h+var_70]
0x180050ac7  mov     dword ptr [rbp+57h+var_A8], eax
0x180050aca  lea     rax, [rbp+57h+var_60]
0x180050ace  mov     [rsp+120h+var_F8], rax
0x180050ad3  lea     rax, [rbp+57h+var_A8]
0x180050ad7  mov     qword ptr [rsp+120h+var_100], rax
0x180050adc  lea     rdx, byte_18030AE69
0x180050ae3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180050ae8  mov     eax, dword ptr [rbp+57h+var_70]
0x180050aeb  sub     eax, r13d
0x180050aee  jz      loc_180050BA0
0x180050af4  sub     eax, 6
0x180050af7  jz      loc_180050B82
0x180050afd  sub     eax, r13d
0x180050b00  jz      short loc_180050B6E
0x180050b02  cmp     eax, 3
0x180050b05  jz      short loc_180050B60
0x180050b07  mov     eax, cs:dword_18039EB68
0x180050b0d  cmp     eax, 4
0x180050b10  jbe     loc_1800508E5
0x180050b16  mov     edx, 0C00h
0x180050b1b  lea     rcx, dword_18039EB68
0x180050b22  call    _tlgKeywordOn
0x180050b27  test    al, al
0x180050b29  jz      loc_1800508E5
0x180050b2f  mov     rax, qword ptr [rbp+57h+var_70+8]
0x180050b33  mov     [rbp+57h+var_60], rax
0x180050b37  mov     eax, dword ptr [rbp+57h+var_70]
0x180050b3a  mov     dword ptr [rbp+57h+var_A8], eax
0x180050b3d  lea     rax, [rbp+57h+var_60]
0x180050b41  mov     [rsp+120h+var_F8], rax
0x180050b46  lea     rax, [rbp+57h+var_A8]
0x180050b4a  mov     qword ptr [rsp+120h+var_100], rax
0x180050b4f  lea     rdx, word_18030B2D6
0x180050b56  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180050b5b  jmp     loc_1800508E5
0x180050b60  lea     rcx, [r14+34h]; struct _SP_NOTIFICATION_INFO *
0x180050b64  call    ?SpProcessNotification@@YA?AW4_MI_Result@@PEAU_SP_NOTIFICATION_INFO@@@Z; SpProcessNotification(_SP_NOTIFICATION_INFO *)
0x180050b69  jmp     loc_1800508E5
0x180050b6e  mov     r8, rsi; unsigned __int16 *
0x180050b71  lea     rdx, [rbp+57h+var_70]; struct _NOTIFY_FILTER_AND_TYPE *
0x180050b75  mov     rcx, rdi; this
0x180050b78  call    ?_HandleRegistryNotification@CSpCluster@@AEAAXAEAU_NOTIFY_FILTER_AND_TYPE@@PEBG@Z; CSpCluster::_HandleRegistryNotification(_NOTIFY_FILTER_AND_TYPE &,ushort const *)
0x180050b7d  jmp     loc_1800508E5
0x180050b82  mov     eax, [rbp+57h+var_A0]
0x180050b85  mov     [rsp+120h+var_100], eax; unsigned int
0x180050b89  mov     r9, r14; unsigned __int8 *
0x180050b8c  mov     r8, rsi; unsigned __int16 *
0x180050b8f  lea     rdx, [rbp+57h+var_70]; struct _NOTIFY_FILTER_AND_TYPE *
0x180050b93  mov     rcx, rdi; this
0x180050b96  call    ?_HandleNodeNotification@CSpCluster@@AEAAXAEAU_NOTIFY_FILTER_AND_TYPE@@PEBGPEAEK@Z; CSpCluster::_HandleNodeNotification(_NOTIFY_FILTER_AND_TYPE &,ushort const *,uchar *,ulong)
0x180050b9b  jmp     loc_1800508E5
0x180050ba0  lea     rdx, [rbp+57h+var_70]; struct _NOTIFY_FILTER_AND_TYPE *
0x180050ba4  call    ?_HandleClusterNotification@CSpCluster@@AEAAHAEAU_NOTIFY_FILTER_AND_TYPE@@@Z; CSpCluster::_HandleClusterNotification(_NOTIFY_FILTER_AND_TYPE &)
0x180050ba9  test    eax, eax
0x180050bab  jz      loc_1800508E5
0x180050bb1  mov     dword ptr [rbp+57h+var_90], r12d
  ... truncated ...
```

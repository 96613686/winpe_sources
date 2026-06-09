# cdp::ActivityManager::GetDatabaseInstanceId(void)

- ea: `0x1800d6310`
- end: `0x1800d6604`
- name: `?GetDatabaseInstanceId@ActivityManager@cdp@@UEAAGXZ`
- size: `756`
- prototype: `unsigned __int16 __fastcall(cdp::ActivityManager *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update`

## callees

- `0x180013da0`
- `0x180030190`
- `0x180067954`
- `0x18006b7cc`
- `0x18006cb90`
- `0x18007120c`
- `0x18008056c`
- `0x18008e820`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800a77d4`
- `0x1800d6310`
- `0x1800d6e2c`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x1800d639e`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x1800d639e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d63df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d6543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d63df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d6543`

## string_xrefs

- `0x1800d64ec`: `DatabaseInstanceIdUpdateTime`
- `0x1800d640a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800d656e`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall cdp::ActivityManager::GetDatabaseInstanceId(cdp::ActivityManager *this)
{
  __int64 result; // rax
  std::_Ref_count_base *v3; // rcx
  __int64 v4; // r9
  _QWORD *v5; // rcx
  int v6; // ecx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  unsigned int v11; // ecx
  const char *v12; // r8
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  unsigned __int16 v20; // bx
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 CurrentThreadId; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v24; // [rsp+48h] [rbp-B8h]
  const char *v25; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v26[6]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v28; // [rsp+78h] [rbp-88h]
  _BYTE v29[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h]
  volatile signed __int32 *v31; // [rsp+90h] [rbp-70h]
  _BYTE pExceptionObject[56]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v33[20]; // [rsp+E8h] [rbp-18h] BYREF
  char *v34[4]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v35[4]; // [rsp+130h] [rbp+30h] BYREF

  result = *((unsigned __int16 *)this + 754);
  if ( !(_WORD)result )
  {
    cdp::ActivityManager::GetDatabaseConnectionLease(this, v29);
    v3 = (std::_Ref_count_base *)v31;
    if ( v31 )
    {
      _InterlockedIncrement(v31 + 2);
      v3 = (std::_Ref_count_base *)v31;
    }
    v23 = v30;
    v24 = v3;
    ActivityFeedClient::MetadataManager::GetMetadata(&v23, v35, "DatabaseInstanceId");
    if ( v35[2] )
    {
      v5 = v35;
      if ( v35[3] > 0xFu )
        v5 = (_QWORD *)v35[0];
      *((_WORD *)this + 754) = _o_strtoul(v5, 0, 0);
    }
    else
    {
      if ( !*((_QWORD *)this + 30) )
      {
        v25 = "..\\activitymanager.cpp";
        v26[0] = 2463;
        v21 = -2147418113;
        CurrentThreadId = GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v6,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v21,
          (unsigned int)&v25,
          (__int64)v26,
          (__int64)&CurrentThreadId);
        v7 = cdp::ExceptionStackFromSourceLocationInfo(v34, &v25);
        v10 = cdp::ErrorCodeToString(2147549183LL, v8, v9, v7);
        ConnectedDevices::Exception::Exception(pExceptionObject, 2147549183LL, v10);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
      LOBYTE(v4) = 1;
      (*(void (__fastcall **)(_QWORD, __int64 *, char *, __int64))(**((_QWORD **)this + 66) + 24LL))(
        *((_QWORD *)this + 66),
        &v27,
        (char *)this + 224,
        v4);
      (*(void (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v27 + 144LL))(v27, v33);
      v11 = v33[0];
      *((_WORD *)this + 754) = v33[0];
      if ( (_WORD)v11 )
      {
        std::_Integral_to_string<char,int>(v34, v11);
        v12 = (const char *)v34;
        if ( v34[3] > (char *)0xF )
          v12 = v34[0];
        ActivityFeedClient::MetadataManager::AddUpdateMetadata(
          (ActivityFeedClient::MetadataManager *)&v23,
          "DatabaseInstanceId",
          v12);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v34);
        v13 = CDP_DATE_TIME::UtcNow(&v25);
        v14 = CDP_DATE_TIME::ToString(v13, v34);
        if ( *(_QWORD *)(v14 + 24) > 0xFu )
          v14 = *(_QWORD *)v14;
        ActivityFeedClient::MetadataManager::AddUpdateMetadata(
          (ActivityFeedClient::MetadataManager *)&v23,
          "DatabaseInstanceIdUpdateTime",
          (const char *)v14);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v34);
      }
      if ( v28 )
        std::_Ref_count_base::_Decref(v28);
    }
    if ( !*((_WORD *)this + 754) )
    {
      v25 = "..\\activitymanager.cpp";
      v26[0] = 2476;
      v21 = -2147418113;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v15,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v21,
        (unsigned int)&v25,
        (__int64)v26,
        (__int64)&CurrentThreadId);
      v16 = cdp::ExceptionStackFromSourceLocationInfo(v34, &v25);
      v19 = cdp::ErrorCodeToString(2147549183LL, v17, v18, v16);
      ConnectedDevices::Exception::Exception(pExceptionObject, 2147549183LL, v19);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    ActivityFeedClient::ConnectionLease::RestoreConnectionToPool((ActivityFeedClient::ConnectionLease *)v29);
    v20 = *((_WORD *)this + 754);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v35);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    ActivityFeedClient::ConnectionLease::~ConnectionLease((ActivityFeedClient::ConnectionLease *)v29);
    return v20;
  }
  return result;
}

```

## disassembly

```asm
0x1800d6310  mov     [rsp-8+arg_8], rbx
0x1800d6315  push    rbp
0x1800d6316  lea     rbp, [rsp-60h]
0x1800d631b  sub     rsp, 160h
0x1800d6322  mov     rax, cs:__security_cookie
0x1800d6329  xor     rax, rsp
0x1800d632c  mov     [rbp+60h+var_10], rax
0x1800d6330  mov     rbx, rcx
0x1800d6333  movzx   eax, word ptr [rcx+5E4h]
0x1800d633a  xor     edx, edx
0x1800d633c  cmp     dx, ax
0x1800d633f  jnz     loc_1800D65E7
0x1800d6345  lea     rdx, [rbp+60h+var_E0]
0x1800d6349  call    ?GetDatabaseConnectionLease@ActivityManager@cdp@@AEAA?AVConnectionLease@ActivityFeedClient@@XZ; cdp::ActivityManager::GetDatabaseConnectionLease(void)
0x1800d634e  nop
0x1800d634f  mov     rcx, [rbp+60h+var_D0]
0x1800d6353  test    rcx, rcx
0x1800d6356  jz      short loc_1800D6360
0x1800d6358  lock inc dword ptr [rcx+8]
0x1800d635c  mov     rcx, [rbp+60h+var_D0]
0x1800d6360  mov     rax, [rbp+60h+var_D8]
0x1800d6364  mov     [rsp+160h+var_120], rax
0x1800d6369  mov     [rsp+160h+var_118], rcx
0x1800d636e  lea     r8, aDatabaseinstan_0; "DatabaseInstanceId"
0x1800d6375  lea     rdx, [rbp+60h+var_30]
0x1800d6379  lea     rcx, [rsp+160h+var_120]
0x1800d637e  call    ?GetMetadata@MetadataManager@ActivityFeedClient@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; ActivityFeedClient::MetadataManager::GetMetadata(char const *)
0x1800d6383  nop
0x1800d6384  cmp     [rbp+60h+var_20], 0
0x1800d6389  jz      short loc_1800D63B0
0x1800d638b  lea     rcx, [rbp+60h+var_30]
0x1800d638f  cmp     [rbp+60h+var_18], 0Fh
0x1800d6394  cmova   rcx, [rbp+60h+var_30]
0x1800d6399  xor     r8d, r8d
0x1800d639c  xor     edx, edx
0x1800d639e  call    cs:__imp__o_strtoul
0x1800d63a4  mov     [rbx+5E4h], ax
0x1800d63ab  jmp     loc_1800D6517
0x1800d63b0  lea     r8, [rbx+0E0h]
0x1800d63b7  cmp     qword ptr [r8+10h], 0
0x1800d63bc  jnz     loc_1800D644D
0x1800d63c2  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1800d63c9  mov     [rsp+160h+var_110], rax
0x1800d63ce  mov     [rsp+160h+var_108], 99Fh
0x1800d63d6  mov     ebx, 8000FFFFh
0x1800d63db  mov     [rsp+160h+var_130], ebx
0x1800d63df  call    cs:__imp_GetCurrentThreadId
0x1800d63e5  mov     eax, eax
0x1800d63e7  mov     [rsp+160h+var_128], rax
0x1800d63ec  lea     rax, [rsp+160h+var_128]
0x1800d63f1  mov     [rsp+160h+var_138], rax
0x1800d63f6  lea     rax, [rsp+160h+var_108]
0x1800d63fb  mov     [rsp+160h+var_140], rax
0x1800d6400  lea     r9, [rsp+160h+var_110]
0x1800d6405  lea     r8, [rsp+160h+var_130]
0x1800d640a  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800d6411  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800d6416  lea     rdx, [rsp+160h+var_110]
0x1800d641b  lea     rcx, [rbp+60h+var_50]
0x1800d641f  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800d6424  mov     r9, rax
0x1800d6427  mov     ecx, ebx
0x1800d6429  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800d642e  mov     r8, rax
0x1800d6431  mov     edx, ebx
0x1800d6433  lea     rcx, [rbp+60h+pExceptionObject]
0x1800d6437  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800d643c  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800d6443  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x1800d6447  call    _CxxThrowException_0
0x1800d644d  mov     rcx, [rbx+210h]
0x1800d6454  mov     rax, [rcx]
0x1800d6457  mov     r9b, 1
0x1800d645a  lea     rdx, [rsp+160h+var_F0]
0x1800d645f  mov     rax, [rax+18h]
0x1800d6463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6468  nop
0x1800d6469  mov     rcx, [rsp+160h+var_F0]
0x1800d646e  mov     rax, [rcx]
0x1800d6471  lea     rdx, [rbp+60h+var_78]
0x1800d6475  mov     rax, [rax+90h]
0x1800d647c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6481  movzx   ecx, [rbp+60h+var_78]
0x1800d6485  mov     [rbx+5E4h], cx
0x1800d648c  xor     eax, eax
0x1800d648e  cmp     ax, cx
0x1800d6491  jz      short loc_1800D6508
0x1800d6493  mov     edx, ecx
0x1800d6495  lea     rcx, [rbp+60h+var_50]
0x1800d6499  call    ??$_Integral_to_string@DH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@H@Z; std::_Integral_to_string<char,int>(int)
0x1800d649e  nop
0x1800d649f  lea     r8, [rbp+60h+var_50]
0x1800d64a3  cmp     [rbp+60h+var_38], 0Fh
0x1800d64a8  cmova   r8, [rbp+60h+var_50]; char *
0x1800d64ad  lea     rdx, aDatabaseinstan_0; "DatabaseInstanceId"
0x1800d64b4  lea     rcx, [rsp+160h+var_120]; this
0x1800d64b9  call    ?AddUpdateMetadata@MetadataManager@ActivityFeedClient@@QEAAXPEBD0@Z; ActivityFeedClient::MetadataManager::AddUpdateMetadata(char const *,char const *)
0x1800d64be  nop
0x1800d64bf  lea     rcx, [rbp+60h+var_50]; void *
0x1800d64c3  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800d64c8  lea     rcx, [rsp+160h+var_110]
0x1800d64cd  call    ?UtcNow@CDP_DATE_TIME@@SA?AU1@XZ; CDP_DATE_TIME::UtcNow(void)
0x1800d64d2  lea     rdx, [rbp+60h+var_50]
0x1800d64d6  mov     rcx, rax
0x1800d64d9  call    ?ToString@CDP_DATE_TIME@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; CDP_DATE_TIME::ToString(void)
0x1800d64de  nop
0x1800d64df  cmp     qword ptr [rax+18h], 0Fh
0x1800d64e4  jbe     short loc_1800D64E9
0x1800d64e6  mov     rax, [rax]
0x1800d64e9  mov     r8, rax; char *
0x1800d64ec  lea     rdx, aDatabaseinstan_1; "DatabaseInstanceIdUpdateTime"
0x1800d64f3  lea     rcx, [rsp+160h+var_120]; this
0x1800d64f8  call    ?AddUpdateMetadata@MetadataManager@ActivityFeedClient@@QEAAXPEBD0@Z; ActivityFeedClient::MetadataManager::AddUpdateMetadata(char const *,char const *)
0x1800d64fd  nop
0x1800d64fe  lea     rcx, [rbp+60h+var_50]; void *
0x1800d6502  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800d6507  nop
0x1800d6508  mov     rcx, [rsp+160h+var_E8]; this
0x1800d650d  test    rcx, rcx
0x1800d6510  jz      short loc_1800D6517
0x1800d6512  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d6517  xor     eax, eax
0x1800d6519  cmp     ax, [rbx+5E4h]
0x1800d6520  jnz     loc_1800D65B1
0x1800d6526  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1800d652d  mov     [rsp+160h+var_110], rax
0x1800d6532  mov     [rsp+160h+var_108], 9ACh
0x1800d653a  mov     ebx, 8000FFFFh
0x1800d653f  mov     [rsp+160h+var_130], ebx
0x1800d6543  call    cs:__imp_GetCurrentThreadId
0x1800d6549  mov     eax, eax
0x1800d654b  mov     [rsp+160h+var_128], rax
0x1800d6550  lea     rax, [rsp+160h+var_128]
0x1800d6555  mov     [rsp+160h+var_138], rax
0x1800d655a  lea     rax, [rsp+160h+var_108]
0x1800d655f  mov     [rsp+160h+var_140], rax
0x1800d6564  lea     r9, [rsp+160h+var_110]
0x1800d6569  lea     r8, [rsp+160h+var_130]
0x1800d656e  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800d6575  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800d657a  lea     rdx, [rsp+160h+var_110]
0x1800d657f  lea     rcx, [rbp+60h+var_50]
0x1800d6583  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800d6588  mov     r9, rax
0x1800d658b  mov     ecx, ebx
0x1800d658d  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800d6592  mov     r8, rax
0x1800d6595  mov     edx, ebx
0x1800d6597  lea     rcx, [rbp+60h+pExceptionObject]
0x1800d659b  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800d65a0  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800d65a7  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x1800d65ab  call    _CxxThrowException_0
0x1800d65b1  lea     rcx, [rbp+60h+var_E0]; this
0x1800d65b5  call    ?RestoreConnectionToPool@ConnectionLease@ActivityFeedClient@@QEAAXXZ; ActivityFeedClient::ConnectionLease::RestoreConnectionToPool(void)
0x1800d65ba  movzx   ebx, word ptr [rbx+5E4h]
0x1800d65c1  lea     rcx, [rbp+60h+var_30]; void *
0x1800d65c5  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800d65ca  nop
0x1800d65cb  mov     rcx, [rsp+160h+var_118]; this
0x1800d65d0  test    rcx, rcx
0x1800d65d3  jz      short loc_1800D65DB
0x1800d65d5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d65da  nop
0x1800d65db  lea     rcx, [rbp+60h+var_E0]; this
0x1800d65df  call    ??1ConnectionLease@ActivityFeedClient@@QEAA@XZ; ActivityFeedClient::ConnectionLease::~ConnectionLease(void)
0x1800d65e4  movzx   eax, bx
0x1800d65e7  mov     rcx, [rbp+60h+var_10]
0x1800d65eb  xor     rcx, rsp; StackCookie
0x1800d65ee  call    __security_check_cookie
0x1800d65f3  mov     rbx, [rsp+160h+arg_8]
0x1800d65fb  add     rsp, 160h
0x1800d6602  pop     rbp
0x1800d6603  retn
```

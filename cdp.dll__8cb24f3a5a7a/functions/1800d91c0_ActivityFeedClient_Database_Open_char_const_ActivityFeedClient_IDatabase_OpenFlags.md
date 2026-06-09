# ActivityFeedClient::Database::Open(char const *,ActivityFeedClient::IDatabase::OpenFlags)

- ea: `0x1800d91c0`
- end: `0x1800d9455`
- name: `?Open@Database@ActivityFeedClient@@UEAAXPEBDW4OpenFlags@IDatabase@2@@Z`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180013da0`
- `0x1800376a8`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800d91c0`
- `0x1800d945c`
- `0x180143248`
- `0x1801fcb36`
- `0x1803077f0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d92dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d9377`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d92dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d9377`
- `winsqlite3!sqlite3_file_control` at `0x1800d9294`
- `winsqlite3!sqlite3_file_control` at `0x1800d9294`
- `winsqlite3!sqlite3_extended_errcode` at `0x1800d925f`
- `winsqlite3!sqlite3_extended_errcode` at `0x1800d925f`
- `winsqlite3!sqlite3_extended_result_codes` at `0x1800d9349`
- `winsqlite3!sqlite3_extended_result_codes` at `0x1800d9349`
- `winsqlite3!sqlite3_open_v2` at `0x1800d9242`
- `winsqlite3!sqlite3_open_v2` at `0x1800d9242`
- `winsqlite3!sqlite3_errmsg` at `0x1800d92a0`
- `winsqlite3!sqlite3_errmsg` at `0x1800d92a0`

## string_xrefs

- `0x1800d9302`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800d939d`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ActivityFeedClient::Database::Open(_QWORD *a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // r8
  int v7; // eax
  _QWORD *v8; // rdi
  int v9; // eax
  bool v10; // sf
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // edx
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // ecx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rax
  const char **v28; // rax
  const char *v29; // rdx
  volatile signed __int32 *v30; // rcx
  const char *v31; // [rsp+30h] [rbp-29h] BYREF
  std::_Ref_count_base *v32; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v33[8]; // [rsp+40h] [rbp-19h] BYREF
  std::_Ref_count_base *v34; // [rsp+48h] [rbp-11h]
  _BYTE pExceptionObject[88]; // [rsp+58h] [rbp-1h] BYREF
  __int64 v36; // [rsp+C0h] [rbp+67h] BYREF
  int v37; // [rsp+D0h] [rbp+77h] BYREF
  __int64 CurrentThreadId; // [rsp+D8h] [rbp+7Fh] BYREF

  (*(void (__fastcall **)(_QWORD *))(*a1 + 16LL))(a1);
  if ( (a3 & 3) != 0 )
  {
    if ( (a3 & 3) == 2 )
      v6 = 6;
    else
      v6 = 1;
  }
  else
  {
    v6 = 2;
  }
  v7 = a3 & 0xC;
  if ( (a3 & 0xC) != 0 )
  {
    if ( v7 == 4 )
    {
      LODWORD(v6) = v6 | 0x20000;
    }
    else if ( v7 == 8 )
    {
      LODWORD(v6) = v6 | 0x40000;
    }
    else
    {
      v6 = (unsigned int)v6 | 1;
    }
  }
  v8 = a1 + 3;
  v9 = sqlite3_open_v2(a2, a1 + 3, v6, 0);
  v10 = v9 < 0;
  if ( v9 > 0 )
    v10 = 1;
  v11 = *v8;
  if ( v10 )
  {
    v12 = sqlite3_extended_errcode(v11);
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x87AF0000;
    LODWORD(v36) = -2147024882;
    v37 = 7;
    if ( *v8 )
      v37 = sqlite3_file_control(*v8, 0, 4, &v36);
    CurrentThreadId = sqlite3_errmsg(*v8);
    Log<int &,int &,char const *>(v15, v14, (unsigned int)&v36, (unsigned int)&v37, (__int64)&CurrentThreadId);
    *v8 = 0;
    v31 = ".\\database.cpp";
    LODWORD(v32) = 134;
    v37 = v13;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v16,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v37,
      (unsigned int)&v31,
      (__int64)&v32,
      (__int64)&CurrentThreadId);
    v17 = cdp::ExceptionStackFromSourceLocationInfo(v33, &v31);
    v20 = cdp::ErrorCodeToString(v13, v18, v19, v17);
    ConnectedDevices::Exception::Exception(pExceptionObject, v13, v20);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v21 = sqlite3_extended_result_codes(v11, 1);
  v22 = v21;
  if ( v21 > 0 )
    v22 = (unsigned __int16)v21 | 0x87AF0000;
  if ( (v22 & 0x80000000) != 0 )
  {
    v31 = ".\\database.cpp";
    LODWORD(v32) = 139;
    v37 = v22;
    v36 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v23,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v37,
      (unsigned int)&v31,
      (__int64)&v32,
      (__int64)&v36);
    v24 = cdp::ExceptionStackFromSourceLocationInfo(v33, &v31);
    v27 = cdp::ErrorCodeToString(v22, v25, v26, v24);
    ConnectedDevices::Exception::Exception(pExceptionObject, v22, v27);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v28 = (const char **)std::enable_shared_from_this<cdp::DiscovererBase>::shared_from_this(a1 + 1, v33);
  v29 = *v28;
  v30 = (volatile signed __int32 *)v28[1];
  *v28 = 0;
  v28[1] = 0;
  if ( v30 )
    _InterlockedIncrement(v30 + 2);
  v31 = v29;
  v32 = (std::_Ref_count_base *)v30;
  if ( v30 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v30);
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
  ActivityFeedClient::DatabaseConfigurationHelper::Configure(&v31, a3);
  if ( v32 )
    std::_Ref_count_base::_Decref(v32);
}

```

## disassembly

```asm
0x1800d91c0  push    rbp
0x1800d91c2  push    rbx
0x1800d91c3  push    rsi
0x1800d91c4  push    rdi
0x1800d91c5  push    r14
0x1800d91c7  lea     rbp, [rsp-37h]
0x1800d91cc  sub     rsp, 90h
0x1800d91d3  mov     r14d, r8d
0x1800d91d6  mov     rbx, rdx
0x1800d91d9  mov     rsi, rcx
0x1800d91dc  mov     rax, [rcx]
0x1800d91df  mov     rax, [rax+10h]
0x1800d91e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d91e8  mov     r9d, r14d
0x1800d91eb  and     r9d, 3
0x1800d91ef  jz      short loc_1800D920B
0x1800d91f1  sub     r9d, 1
0x1800d91f5  jz      short loc_1800D9203
0x1800d91f7  cmp     r9d, 1
0x1800d91fb  jnz     short loc_1800D9203
0x1800d91fd  lea     r8d, [r9+5]
0x1800d9201  jmp     short loc_1800D9211
0x1800d9203  mov     r8d, 1
0x1800d9209  jmp     short loc_1800D9211
0x1800d920b  mov     r8d, 2
0x1800d9211  mov     eax, r14d
0x1800d9214  and     eax, 0Ch
0x1800d9217  jz      short loc_1800D9235
0x1800d9219  cmp     eax, 4
0x1800d921c  jz      short loc_1800D9230
0x1800d921e  cmp     eax, 8
0x1800d9221  jz      short loc_1800D9229
0x1800d9223  or      r8d, 1
0x1800d9227  jmp     short loc_1800D9235
0x1800d9229  bts     r8d, 12h
0x1800d922e  jmp     short loc_1800D9235
0x1800d9230  bts     r8d, 11h
0x1800d9235  lea     rdi, [rsi+18h]
0x1800d9239  xor     r9d, r9d
0x1800d923c  mov     rdx, rdi
0x1800d923f  mov     rcx, rbx
0x1800d9242  call    cs:__imp_sqlite3_open_v2
0x1800d9248  test    eax, eax
0x1800d924a  jle     short loc_1800D9256
0x1800d924c  movzx   eax, ax
0x1800d924f  or      eax, 87AF0000h
0x1800d9254  test    eax, eax
0x1800d9256  mov     rcx, [rdi]
0x1800d9259  jns     loc_1800D9344
0x1800d925f  call    cs:__imp_sqlite3_extended_errcode
0x1800d9265  mov     ebx, eax
0x1800d9267  test    eax, eax
0x1800d9269  jle     short loc_1800D9274
0x1800d926b  movzx   ebx, ax
0x1800d926e  or      ebx, 87AF0000h
0x1800d9274  mov     dword ptr [rbp+57h+arg_0], 8007000Eh
0x1800d927b  mov     [rbp+57h+arg_10], 7
0x1800d9282  mov     rcx, [rdi]
0x1800d9285  test    rcx, rcx
0x1800d9288  jz      short loc_1800D929D
0x1800d928a  lea     r9, [rbp+57h+arg_0]
0x1800d928e  xor     edx, edx
0x1800d9290  lea     r8d, [rdx+4]
0x1800d9294  call    cs:__imp_sqlite3_file_control
0x1800d929a  mov     [rbp+57h+arg_10], eax
0x1800d929d  mov     rcx, [rdi]
0x1800d92a0  call    cs:__imp_sqlite3_errmsg
0x1800d92a6  mov     [rbp+57h+arg_18], rax
0x1800d92aa  lea     rax, [rbp+57h+arg_18]
0x1800d92ae  mov     [rsp+0B0h+var_90], rax
0x1800d92b3  lea     r9, [rbp+57h+arg_10]
0x1800d92b7  lea     r8, [rbp+57h+arg_0]
0x1800d92bb  call    ??$Log@AEAHAEAHPEBD@@YAXW4CDPLogLevel@@PEBDAEAH2$$QEAPEBD@Z; Log<int &,int &,char const *>(CDPLogLevel,char const *,int &,int &,char const * &&)
0x1800d92c0  mov     qword ptr [rdi], 0
0x1800d92c7  lea     rax, aDatabaseCpp; ".\\database.cpp"
0x1800d92ce  mov     [rbp+57h+var_80], rax
0x1800d92d2  mov     dword ptr [rbp+57h+var_78], 86h
0x1800d92d9  mov     [rbp+57h+arg_10], ebx
0x1800d92dc  call    cs:__imp_GetCurrentThreadId
0x1800d92e2  mov     eax, eax
0x1800d92e4  mov     [rbp+57h+arg_18], rax
0x1800d92e8  lea     rax, [rbp+57h+arg_18]
0x1800d92ec  mov     [rsp+0B0h+var_88], rax
0x1800d92f1  lea     rax, [rbp+57h+var_78]
0x1800d92f5  mov     [rsp+0B0h+var_90], rax
0x1800d92fa  lea     r9, [rbp+57h+var_80]
0x1800d92fe  lea     r8, [rbp+57h+arg_10]
0x1800d9302  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800d9309  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800d930e  lea     rdx, [rbp+57h+var_80]
0x1800d9312  lea     rcx, [rbp+57h+var_70]
0x1800d9316  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800d931b  mov     r9, rax
0x1800d931e  mov     ecx, ebx
0x1800d9320  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800d9325  mov     r8, rax
0x1800d9328  mov     edx, ebx
0x1800d932a  lea     rcx, [rbp+57h+pExceptionObject]
0x1800d932e  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800d9333  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800d933a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800d933e  call    _CxxThrowException_0
0x1800d9344  mov     edx, 1
0x1800d9349  call    cs:__imp_sqlite3_extended_result_codes
0x1800d934f  mov     ebx, eax
0x1800d9351  test    eax, eax
0x1800d9353  jle     short loc_1800D935E
0x1800d9355  movzx   ebx, ax
0x1800d9358  or      ebx, 87AF0000h
0x1800d935e  test    ebx, ebx
0x1800d9360  jns     short loc_1800D93DF
0x1800d9362  lea     rax, aDatabaseCpp; ".\\database.cpp"
0x1800d9369  mov     [rbp+57h+var_80], rax
0x1800d936d  mov     dword ptr [rbp+57h+var_78], 8Bh
0x1800d9374  mov     [rbp+57h+arg_10], ebx
0x1800d9377  call    cs:__imp_GetCurrentThreadId
0x1800d937d  mov     eax, eax
0x1800d937f  mov     [rbp+57h+arg_0], rax
0x1800d9383  lea     rax, [rbp+57h+arg_0]
0x1800d9387  mov     [rsp+0B0h+var_88], rax
0x1800d938c  lea     rax, [rbp+57h+var_78]
0x1800d9390  mov     [rsp+0B0h+var_90], rax
0x1800d9395  lea     r9, [rbp+57h+var_80]
0x1800d9399  lea     r8, [rbp+57h+arg_10]
0x1800d939d  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800d93a4  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800d93a9  lea     rdx, [rbp+57h+var_80]
0x1800d93ad  lea     rcx, [rbp+57h+var_70]
0x1800d93b1  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800d93b6  mov     r9, rax
0x1800d93b9  mov     ecx, ebx
0x1800d93bb  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800d93c0  mov     r8, rax
0x1800d93c3  mov     edx, ebx
0x1800d93c5  lea     rcx, [rbp+57h+pExceptionObject]
0x1800d93c9  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800d93ce  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800d93d5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800d93d9  call    _CxxThrowException_0
0x1800d93df  lea     rcx, [rsi+8]
0x1800d93e3  lea     rdx, [rbp+57h+var_70]
0x1800d93e7  call    ?shared_from_this@?$enable_shared_from_this@VDiscovererBase@cdp@@@std@@QEAA?AV?$shared_ptr@VDiscovererBase@cdp@@@2@XZ; std::enable_shared_from_this<cdp::DiscovererBase>::shared_from_this(void)
0x1800d93ec  mov     rdx, [rax]
0x1800d93ef  mov     rcx, [rax+8]; this
0x1800d93f3  mov     qword ptr [rax], 0
0x1800d93fa  mov     qword ptr [rax+8], 0
0x1800d9402  test    rcx, rcx
0x1800d9405  jz      short loc_1800D940B
0x1800d9407  lock inc dword ptr [rcx+8]
0x1800d940b  mov     [rbp+57h+var_80], rdx
0x1800d940f  mov     [rbp+57h+var_78], rcx
0x1800d9413  test    rcx, rcx
0x1800d9416  jz      short loc_1800D941E
0x1800d9418  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d941d  nop
0x1800d941e  mov     rcx, [rbp+57h+var_68]; this
0x1800d9422  test    rcx, rcx
0x1800d9425  jz      short loc_1800D942C
0x1800d9427  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d942c  mov     edx, r14d
0x1800d942f  lea     rcx, [rbp+57h+var_80]
0x1800d9433  call    ?Configure@DatabaseConfigurationHelper@ActivityFeedClient@@QEAAXW4OpenFlags@IDatabase@2@@Z; ActivityFeedClient::DatabaseConfigurationHelper::Configure(ActivityFeedClient::IDatabase::OpenFlags)
0x1800d9438  nop
0x1800d9439  mov     rcx, [rbp+57h+var_78]; this
0x1800d943d  test    rcx, rcx
0x1800d9440  jz      short loc_1800D9447
0x1800d9442  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d9447  add     rsp, 90h
0x1800d944e  pop     r14
0x1800d9450  pop     rdi
0x1800d9451  pop     rsi
0x1800d9452  pop     rbx
0x1800d9453  pop     rbp
0x1800d9454  retn
```

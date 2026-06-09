# ActivityFeedClient::Statement::BindString(int,char const *)

- ea: `0x1800d0590`
- end: `0x1800d0703`
- name: `?BindString@Statement@ActivityFeedClient@@UEAAXHPEBD@Z`
- size: `371`
- prototype: `void __fastcall(ActivityFeedClient::Statement *__hidden this, int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800d0590`
- `0x180143248`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d061e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d069b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d061e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d069b`
- `winsqlite3!sqlite3_bind_text` at `0x1800d05d2`
- `winsqlite3!sqlite3_bind_text` at `0x1800d05d2`

## string_xrefs

- `0x1800d0644`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800d06c1`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ActivityFeedClient::Statement::BindString(
        ActivityFeedClient::Statement *this,
        unsigned int a2,
        const char *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // ecx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  const char *v18; // [rsp+30h] [rbp-19h] BYREF
  int v19; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v20[24]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+58h] [rbp+Fh] BYREF
  int v22; // [rsp+B0h] [rbp+67h] BYREF
  __int64 CurrentThreadId; // [rsp+C8h] [rbp+7Fh] BYREF

  if ( !(*(unsigned __int8 (__fastcall **)(ActivityFeedClient::Statement *))(*(_QWORD *)this + 8LL))(this) )
  {
    v18 = ".\\statement.cpp";
    v19 = 141;
    v22 = -2147019873;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v8,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v22,
      (unsigned int)&v18,
      (__int64)&v19,
      (__int64)&CurrentThreadId);
    v9 = cdp::ExceptionStackFromSourceLocationInfo(v20, &v18);
    v12 = cdp::ErrorCodeToString(2147947423LL, v10, v11, v9);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147947423LL, v12);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v6 = sqlite3_bind_text(*((_QWORD *)this + 1), a2, a3, 0xFFFFFFFFLL, 0);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x87AF0000;
  if ( (v7 & 0x80000000) != 0 )
  {
    v18 = ".\\statement.cpp";
    v19 = 142;
    v22 = v7;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v13,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v22,
      (unsigned int)&v18,
      (__int64)&v19,
      (__int64)&CurrentThreadId);
    v14 = cdp::ExceptionStackFromSourceLocationInfo(v20, &v18);
    v17 = cdp::ErrorCodeToString(v7, v15, v16, v14);
    ConnectedDevices::Exception::Exception(pExceptionObject, v7, v17);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800d0590  mov     [rsp-8+arg_8], rbx
0x1800d0595  push    rbp
0x1800d0596  push    rsi
0x1800d0597  push    rdi
0x1800d0598  lea     rbp, [rsp-47h]
0x1800d059d  sub     rsp, 90h
0x1800d05a4  mov     rdi, r8
0x1800d05a7  mov     esi, edx
0x1800d05a9  mov     rbx, rcx
0x1800d05ac  mov     rax, [rcx]
0x1800d05af  mov     rax, [rax+8]
0x1800d05b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d05b8  test    al, al
0x1800d05ba  jz      short loc_1800D0604
0x1800d05bc  mov     [rsp+0A0h+var_80], 0
0x1800d05c5  or      r9d, 0FFFFFFFFh
0x1800d05c9  mov     r8, rdi
0x1800d05cc  mov     edx, esi
0x1800d05ce  mov     rcx, [rbx+8]
0x1800d05d2  call    cs:__imp_sqlite3_bind_text
0x1800d05d8  mov     ebx, eax
0x1800d05da  test    eax, eax
0x1800d05dc  jg      short loc_1800D05F9
0x1800d05de  test    ebx, ebx
0x1800d05e0  js      loc_1800D0686
0x1800d05e6  mov     rbx, [rsp+0A0h+arg_8]
0x1800d05ee  add     rsp, 90h
0x1800d05f5  pop     rdi
0x1800d05f6  pop     rsi
0x1800d05f7  pop     rbp
0x1800d05f8  retn
0x1800d05f9  movzx   ebx, ax
0x1800d05fc  or      ebx, 87AF0000h
0x1800d0602  jmp     short loc_1800D05DE
0x1800d0604  lea     rax, aStatementCpp; ".\\statement.cpp"
0x1800d060b  mov     [rbp+57h+var_70], rax
0x1800d060f  mov     [rbp+57h+var_68], 8Dh
0x1800d0616  mov     ebx, 8007139Fh
0x1800d061b  mov     [rbp+57h+arg_0], ebx
0x1800d061e  call    cs:__imp_GetCurrentThreadId
0x1800d0624  mov     eax, eax
0x1800d0626  mov     [rbp+57h+arg_18], rax
0x1800d062a  lea     rax, [rbp+57h+arg_18]
0x1800d062e  mov     [rsp+0A0h+var_78], rax
0x1800d0633  lea     rax, [rbp+57h+var_68]
0x1800d0637  mov     [rsp+0A0h+var_80], rax
0x1800d063c  lea     r9, [rbp+57h+var_70]
0x1800d0640  lea     r8, [rbp+57h+arg_0]
0x1800d0644  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800d064b  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800d0650  lea     rdx, [rbp+57h+var_70]
0x1800d0654  lea     rcx, [rbp+57h+var_60]
0x1800d0658  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800d065d  mov     r9, rax
0x1800d0660  mov     ecx, ebx
0x1800d0662  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800d0667  mov     r8, rax
0x1800d066a  mov     edx, ebx
0x1800d066c  lea     rcx, [rbp+57h+pExceptionObject]
0x1800d0670  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800d0675  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800d067c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800d0680  call    _CxxThrowException_0
0x1800d0686  lea     rax, aStatementCpp; ".\\statement.cpp"
0x1800d068d  mov     [rbp+57h+var_70], rax
0x1800d0691  mov     [rbp+57h+var_68], 8Eh
0x1800d0698  mov     [rbp+57h+arg_0], ebx
0x1800d069b  call    cs:__imp_GetCurrentThreadId
0x1800d06a1  mov     eax, eax
0x1800d06a3  mov     [rbp+57h+arg_18], rax
0x1800d06a7  lea     rax, [rbp+57h+arg_18]
0x1800d06ab  mov     [rsp+0A0h+var_78], rax
0x1800d06b0  lea     rax, [rbp+57h+var_68]
0x1800d06b4  mov     [rsp+0A0h+var_80], rax
0x1800d06b9  lea     r9, [rbp+57h+var_70]
0x1800d06bd  lea     r8, [rbp+57h+arg_0]
0x1800d06c1  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800d06c8  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800d06cd  lea     rdx, [rbp+57h+var_70]
0x1800d06d1  lea     rcx, [rbp+57h+var_60]
0x1800d06d5  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800d06da  mov     r9, rax
0x1800d06dd  mov     ecx, ebx
0x1800d06df  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800d06e4  mov     r8, rax
0x1800d06e7  mov     edx, ebx
0x1800d06e9  lea     rcx, [rbp+57h+pExceptionObject]
0x1800d06ed  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800d06f2  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800d06f9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800d06fd  call    _CxxThrowException_0
```

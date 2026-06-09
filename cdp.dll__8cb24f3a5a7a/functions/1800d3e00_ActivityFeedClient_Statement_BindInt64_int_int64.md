# ActivityFeedClient::Statement::BindInt64(int,__int64)

- ea: `0x1800d3e00`
- end: `0x1800d3f66`
- name: `?BindInt64@Statement@ActivityFeedClient@@UEAAXH_J@Z`
- size: `358`
- prototype: `void __fastcall(ActivityFeedClient::Statement *__hidden this, int, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800d3e00`
- `0x180143248`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3e81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3efe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3e81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3efe`
- `winsqlite3!sqlite3_bind_int64` at `0x1800d3e35`
- `winsqlite3!sqlite3_bind_int64` at `0x1800d3e35`

## string_xrefs

- `0x1800d3ea7`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800d3f24`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ActivityFeedClient::Statement::BindInt64(
        ActivityFeedClient::Statement *this,
        unsigned int a2,
        __int64 a3)
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
    v18 = "onecoreuap\\windows\\cdp\\afc\\database\\Statement.h";
    v19 = 56;
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
  v6 = sqlite3_bind_int64(*((_QWORD *)this + 1), a2, a3);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x87AF0000;
  if ( (v7 & 0x80000000) != 0 )
  {
    v18 = "onecoreuap\\windows\\cdp\\afc\\database\\Statement.h";
    v19 = 57;
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
0x1800d3e00  mov     [rsp-8+arg_8], rbx
0x1800d3e05  push    rbp
0x1800d3e06  push    rsi
0x1800d3e07  push    rdi
0x1800d3e08  lea     rbp, [rsp-47h]
0x1800d3e0d  sub     rsp, 90h
0x1800d3e14  mov     rdi, r8
0x1800d3e17  mov     esi, edx
0x1800d3e19  mov     rbx, rcx
0x1800d3e1c  mov     rax, [rcx]
0x1800d3e1f  mov     rax, [rax+8]
0x1800d3e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3e28  test    al, al
0x1800d3e2a  jz      short loc_1800D3E67
0x1800d3e2c  mov     r8, rdi
0x1800d3e2f  mov     edx, esi
0x1800d3e31  mov     rcx, [rbx+8]
0x1800d3e35  call    cs:__imp_sqlite3_bind_int64
0x1800d3e3b  mov     ebx, eax
0x1800d3e3d  test    eax, eax
0x1800d3e3f  jg      short loc_1800D3E5C
0x1800d3e41  test    ebx, ebx
0x1800d3e43  js      loc_1800D3EE9
0x1800d3e49  mov     rbx, [rsp+0A0h+arg_8]
0x1800d3e51  add     rsp, 90h
0x1800d3e58  pop     rdi
0x1800d3e59  pop     rsi
0x1800d3e5a  pop     rbp
0x1800d3e5b  retn
0x1800d3e5c  movzx   ebx, ax
0x1800d3e5f  or      ebx, 87AF0000h
0x1800d3e65  jmp     short loc_1800D3E41
0x1800d3e67  lea     rax, aOnecoreuapWind_46; "onecoreuap\\windows\\cdp\\afc\\database"...
0x1800d3e6e  mov     [rbp+57h+var_70], rax
0x1800d3e72  mov     [rbp+57h+var_68], 38h ; '8'
0x1800d3e79  mov     ebx, 8007139Fh
0x1800d3e7e  mov     [rbp+57h+arg_0], ebx
0x1800d3e81  call    cs:__imp_GetCurrentThreadId
0x1800d3e87  mov     eax, eax
0x1800d3e89  mov     [rbp+57h+arg_18], rax
0x1800d3e8d  lea     rax, [rbp+57h+arg_18]
0x1800d3e91  mov     [rsp+0A0h+var_78], rax
0x1800d3e96  lea     rax, [rbp+57h+var_68]
0x1800d3e9a  mov     [rsp+0A0h+var_80], rax
0x1800d3e9f  lea     r9, [rbp+57h+var_70]
0x1800d3ea3  lea     r8, [rbp+57h+arg_0]
0x1800d3ea7  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800d3eae  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800d3eb3  lea     rdx, [rbp+57h+var_70]
0x1800d3eb7  lea     rcx, [rbp+57h+var_60]
0x1800d3ebb  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800d3ec0  mov     r9, rax
0x1800d3ec3  mov     ecx, ebx
0x1800d3ec5  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800d3eca  mov     r8, rax
0x1800d3ecd  mov     edx, ebx
0x1800d3ecf  lea     rcx, [rbp+57h+pExceptionObject]
0x1800d3ed3  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800d3ed8  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800d3edf  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800d3ee3  call    _CxxThrowException_0
0x1800d3ee9  lea     rax, aOnecoreuapWind_46; "onecoreuap\\windows\\cdp\\afc\\database"...
0x1800d3ef0  mov     [rbp+57h+var_70], rax
0x1800d3ef4  mov     [rbp+57h+var_68], 39h ; '9'
0x1800d3efb  mov     [rbp+57h+arg_0], ebx
0x1800d3efe  call    cs:__imp_GetCurrentThreadId
0x1800d3f04  mov     eax, eax
0x1800d3f06  mov     [rbp+57h+arg_18], rax
0x1800d3f0a  lea     rax, [rbp+57h+arg_18]
0x1800d3f0e  mov     [rsp+0A0h+var_78], rax
0x1800d3f13  lea     rax, [rbp+57h+var_68]
0x1800d3f17  mov     [rsp+0A0h+var_80], rax
0x1800d3f1c  lea     r9, [rbp+57h+var_70]
0x1800d3f20  lea     r8, [rbp+57h+arg_0]
0x1800d3f24  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800d3f2b  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800d3f30  lea     rdx, [rbp+57h+var_70]
0x1800d3f34  lea     rcx, [rbp+57h+var_60]
0x1800d3f38  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800d3f3d  mov     r9, rax
0x1800d3f40  mov     ecx, ebx
0x1800d3f42  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800d3f47  mov     r8, rax
0x1800d3f4a  mov     edx, ebx
0x1800d3f4c  lea     rcx, [rbp+57h+pExceptionObject]
0x1800d3f50  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800d3f55  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800d3f5c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800d3f60  call    _CxxThrowException_0
```

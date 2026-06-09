# ActivityFeedClient::Database::SetWalFilesPersistence(char const *,bool)

- ea: `0x1800f3af0`
- end: `0x1800f3c61`
- name: `?SetWalFilesPersistence@Database@ActivityFeedClient@@UEAAXPEBD_N@Z`
- size: `369`
- prototype: `void __fastcall(ActivityFeedClient::Database *__hidden this, const char *, bool)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800f3af0`
- `0x180143248`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f3b3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f3be6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f3b3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f3be6`
- `winsqlite3!sqlite3_file_control` at `0x1800f3bb8`
- `winsqlite3!sqlite3_file_control` at `0x1800f3bb8`

## string_xrefs

- `0x1800f3b62`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800f3c0c`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ActivityFeedClient::Database::SetWalFilesPersistence(
        ActivityFeedClient::Database *this,
        const char *a2,
        unsigned __int8 a3)
{
  int v3; // edi
  int v6; // ecx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 CurrentThreadId; // [rsp+30h] [rbp-29h] BYREF
  const char *v19; // [rsp+38h] [rbp-21h] BYREF
  int v20; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v21[24]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+60h] [rbp+7h] BYREF
  int v23; // [rsp+C0h] [rbp+67h] BYREF
  int v24; // [rsp+D8h] [rbp+7Fh] BYREF

  v3 = a3;
  if ( !(*(unsigned __int8 (__fastcall **)(ActivityFeedClient::Database *))(*(_QWORD *)this + 8LL))(this) )
  {
    v19 = ".\\database.cpp";
    v20 = 521;
    v23 = -2147019873;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v6,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v23,
      (unsigned int)&v19,
      (__int64)&v20,
      (__int64)&CurrentThreadId);
    v7 = cdp::ExceptionStackFromSourceLocationInfo(v21, &v19);
    v10 = cdp::ErrorCodeToString(2147947423LL, v8, v9, v7);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147947423LL, v10);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v24 = v3;
  v11 = sqlite3_file_control(*((_QWORD *)this + 3), a2, 10, &v24);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x87AF0000;
  if ( (v12 & 0x80000000) != 0 )
  {
    v19 = ".\\database.cpp";
    v20 = 524;
    v23 = v12;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v13,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v23,
      (unsigned int)&v19,
      (__int64)&v20,
      (__int64)&CurrentThreadId);
    v14 = cdp::ExceptionStackFromSourceLocationInfo(v21, &v19);
    v17 = cdp::ErrorCodeToString(v12, v15, v16, v14);
    ConnectedDevices::Exception::Exception(pExceptionObject, v12, v17);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800f3af0  mov     [rsp-8+arg_8], rbx
0x1800f3af5  push    rbp
0x1800f3af6  push    rsi
0x1800f3af7  push    rdi
0x1800f3af8  lea     rbp, [rsp-47h]
0x1800f3afd  sub     rsp, 0A0h
0x1800f3b04  movzx   edi, r8b
0x1800f3b08  mov     rsi, rdx
0x1800f3b0b  mov     rbx, rcx
0x1800f3b0e  mov     rax, [rcx]
0x1800f3b11  mov     rax, [rax+8]
0x1800f3b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3b1a  test    al, al
0x1800f3b1c  jnz     loc_1800F3BA4
0x1800f3b22  lea     rax, aDatabaseCpp; ".\\database.cpp"
0x1800f3b29  mov     [rbp+57h+var_78], rax
0x1800f3b2d  mov     [rbp+57h+var_70], 209h
0x1800f3b34  mov     ebx, 8007139Fh
0x1800f3b39  mov     [rbp+57h+arg_0], ebx
0x1800f3b3c  call    cs:__imp_GetCurrentThreadId
0x1800f3b42  mov     eax, eax
0x1800f3b44  mov     [rbp+57h+var_80], rax
0x1800f3b48  lea     rax, [rbp+57h+var_80]
0x1800f3b4c  mov     [rsp+0B0h+var_88], rax
0x1800f3b51  lea     rax, [rbp+57h+var_70]
0x1800f3b55  mov     [rsp+0B0h+var_90], rax
0x1800f3b5a  lea     r9, [rbp+57h+var_78]
0x1800f3b5e  lea     r8, [rbp+57h+arg_0]
0x1800f3b62  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800f3b69  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800f3b6e  lea     rdx, [rbp+57h+var_78]
0x1800f3b72  lea     rcx, [rbp+57h+var_68]
0x1800f3b76  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800f3b7b  mov     r9, rax
0x1800f3b7e  mov     ecx, ebx
0x1800f3b80  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800f3b85  mov     r8, rax
0x1800f3b88  mov     edx, ebx
0x1800f3b8a  lea     rcx, [rbp+57h+pExceptionObject]
0x1800f3b8e  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800f3b93  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800f3b9a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f3b9e  call    _CxxThrowException_0
0x1800f3ba4  mov     [rbp+57h+arg_18], edi
0x1800f3ba7  lea     r9, [rbp+57h+arg_18]
0x1800f3bab  mov     r8d, 0Ah
0x1800f3bb1  mov     rdx, rsi
0x1800f3bb4  mov     rcx, [rbx+18h]
0x1800f3bb8  call    cs:__imp_sqlite3_file_control
0x1800f3bbe  mov     ebx, eax
0x1800f3bc0  test    eax, eax
0x1800f3bc2  jle     short loc_1800F3BCD
0x1800f3bc4  movzx   ebx, ax
0x1800f3bc7  or      ebx, 87AF0000h
0x1800f3bcd  test    ebx, ebx
0x1800f3bcf  jns     short loc_1800F3C4E
0x1800f3bd1  lea     rax, aDatabaseCpp; ".\\database.cpp"
0x1800f3bd8  mov     [rbp+57h+var_78], rax
0x1800f3bdc  mov     [rbp+57h+var_70], 20Ch
0x1800f3be3  mov     [rbp+57h+arg_0], ebx
0x1800f3be6  call    cs:__imp_GetCurrentThreadId
0x1800f3bec  mov     eax, eax
0x1800f3bee  mov     [rbp+57h+var_80], rax
0x1800f3bf2  lea     rax, [rbp+57h+var_80]
0x1800f3bf6  mov     [rsp+0B0h+var_88], rax
0x1800f3bfb  lea     rax, [rbp+57h+var_70]
0x1800f3bff  mov     [rsp+0B0h+var_90], rax
0x1800f3c04  lea     r9, [rbp+57h+var_78]
0x1800f3c08  lea     r8, [rbp+57h+arg_0]
0x1800f3c0c  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800f3c13  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800f3c18  lea     rdx, [rbp+57h+var_78]
0x1800f3c1c  lea     rcx, [rbp+57h+var_68]
0x1800f3c20  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800f3c25  mov     r9, rax
0x1800f3c28  mov     ecx, ebx
0x1800f3c2a  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800f3c2f  mov     r8, rax
0x1800f3c32  mov     edx, ebx
0x1800f3c34  lea     rcx, [rbp+57h+pExceptionObject]
0x1800f3c38  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800f3c3d  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800f3c44  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f3c48  call    _CxxThrowException_0
0x1800f3c4e  mov     rbx, [rsp+0B0h+arg_8]
0x1800f3c56  add     rsp, 0A0h
0x1800f3c5d  pop     rdi
0x1800f3c5e  pop     rsi
0x1800f3c5f  pop     rbp
0x1800f3c60  retn
```

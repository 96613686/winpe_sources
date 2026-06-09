# ActivityFeedClient::Statement::BindBlob(int,int,void const *)

- ea: `0x1800ddf00`
- end: `0x1800de082`
- name: `?BindBlob@Statement@ActivityFeedClient@@UEAAXHHPEBX@Z`
- size: `386`
- prototype: `void __fastcall(ActivityFeedClient::Statement *__hidden this, int, int, const void *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800ddf00`
- `0x180143248`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ddf9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800de01a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ddf9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800de01a`
- `winsqlite3!sqlite3_bind_blob` at `0x1800ddf4c`
- `winsqlite3!sqlite3_bind_blob` at `0x1800ddf4c`

## string_xrefs

- `0x1800ddfc3`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800de040`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ActivityFeedClient::Statement::BindBlob(
        ActivityFeedClient::Statement *this,
        unsigned int a2,
        unsigned int a3,
        const void *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 CurrentThreadId; // [rsp+30h] [rbp-29h] BYREF
  const char *v21; // [rsp+38h] [rbp-21h] BYREF
  int v22; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v23[24]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp+7h] BYREF
  int v25; // [rsp+C0h] [rbp+67h] BYREF

  if ( !(*(unsigned __int8 (__fastcall **)(ActivityFeedClient::Statement *))(*(_QWORD *)this + 8LL))(this) )
  {
    v21 = ".\\statement.cpp";
    v22 = 149;
    v25 = -2147019873;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v10,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v25,
      (unsigned int)&v21,
      (__int64)&v22,
      (__int64)&CurrentThreadId);
    v11 = cdp::ExceptionStackFromSourceLocationInfo(v23, &v21);
    v14 = cdp::ErrorCodeToString(2147947423LL, v12, v13, v11);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147947423LL, v14);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v8 = sqlite3_bind_blob(*((_QWORD *)this + 1), a2, a4, a3, 0);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x87AF0000;
  if ( (v9 & 0x80000000) != 0 )
  {
    v21 = ".\\statement.cpp";
    v22 = 150;
    v25 = v9;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v15,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v25,
      (unsigned int)&v21,
      (__int64)&v22,
      (__int64)&CurrentThreadId);
    v16 = cdp::ExceptionStackFromSourceLocationInfo(v23, &v21);
    v19 = cdp::ErrorCodeToString(v9, v17, v18, v16);
    ConnectedDevices::Exception::Exception(pExceptionObject, v9, v19);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800ddf00  mov     [rsp-8+arg_8], rbx
0x1800ddf05  mov     [rsp-8+arg_10], rsi
0x1800ddf0a  push    rbp
0x1800ddf0b  push    rdi
0x1800ddf0c  push    r14
0x1800ddf0e  lea     rbp, [rsp-47h]
0x1800ddf13  sub     rsp, 0A0h
0x1800ddf1a  mov     rdi, r9
0x1800ddf1d  mov     esi, r8d
0x1800ddf20  mov     r14d, edx
0x1800ddf23  mov     rbx, rcx
0x1800ddf26  mov     rax, [rcx]
0x1800ddf29  mov     rax, [rax+8]
0x1800ddf2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddf32  test    al, al
0x1800ddf34  jz      short loc_1800DDF83
0x1800ddf36  mov     [rsp+0B0h+var_90], 0
0x1800ddf3f  mov     r9d, esi
0x1800ddf42  mov     r8, rdi
0x1800ddf45  mov     edx, r14d
0x1800ddf48  mov     rcx, [rbx+8]
0x1800ddf4c  call    cs:__imp_sqlite3_bind_blob
0x1800ddf52  mov     ebx, eax
0x1800ddf54  test    eax, eax
0x1800ddf56  jg      short loc_1800DDF78
0x1800ddf58  test    ebx, ebx
0x1800ddf5a  js      loc_1800DE005
0x1800ddf60  lea     r11, [rsp+0B0h+var_10]
0x1800ddf68  mov     rbx, [r11+28h]
0x1800ddf6c  mov     rsi, [r11+30h]
0x1800ddf70  mov     rsp, r11
0x1800ddf73  pop     r14
0x1800ddf75  pop     rdi
0x1800ddf76  pop     rbp
0x1800ddf77  retn
0x1800ddf78  movzx   ebx, ax
0x1800ddf7b  or      ebx, 87AF0000h
0x1800ddf81  jmp     short loc_1800DDF58
0x1800ddf83  lea     rax, aStatementCpp; ".\\statement.cpp"
0x1800ddf8a  mov     [rbp+57h+var_78], rax
0x1800ddf8e  mov     [rbp+57h+var_70], 95h
0x1800ddf95  mov     ebx, 8007139Fh
0x1800ddf9a  mov     [rbp+57h+arg_0], ebx
0x1800ddf9d  call    cs:__imp_GetCurrentThreadId
0x1800ddfa3  mov     eax, eax
0x1800ddfa5  mov     [rbp+57h+var_80], rax
0x1800ddfa9  lea     rax, [rbp+57h+var_80]
0x1800ddfad  mov     [rsp+0B0h+var_88], rax
0x1800ddfb2  lea     rax, [rbp+57h+var_70]
0x1800ddfb6  mov     [rsp+0B0h+var_90], rax
0x1800ddfbb  lea     r9, [rbp+57h+var_78]
0x1800ddfbf  lea     r8, [rbp+57h+arg_0]
0x1800ddfc3  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800ddfca  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800ddfcf  lea     rdx, [rbp+57h+var_78]
0x1800ddfd3  lea     rcx, [rbp+57h+var_68]
0x1800ddfd7  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800ddfdc  mov     r9, rax
0x1800ddfdf  mov     ecx, ebx
0x1800ddfe1  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800ddfe6  mov     r8, rax
0x1800ddfe9  mov     edx, ebx
0x1800ddfeb  lea     rcx, [rbp+57h+pExceptionObject]
0x1800ddfef  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800ddff4  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800ddffb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800ddfff  call    _CxxThrowException_0
0x1800de005  lea     rax, aStatementCpp; ".\\statement.cpp"
0x1800de00c  mov     [rbp+57h+var_78], rax
0x1800de010  mov     [rbp+57h+var_70], 96h
0x1800de017  mov     [rbp+57h+arg_0], ebx
0x1800de01a  call    cs:__imp_GetCurrentThreadId
0x1800de020  mov     eax, eax
0x1800de022  mov     [rbp+57h+var_80], rax
0x1800de026  lea     rax, [rbp+57h+var_80]
0x1800de02a  mov     [rsp+0B0h+var_88], rax
0x1800de02f  lea     rax, [rbp+57h+var_70]
0x1800de033  mov     [rsp+0B0h+var_90], rax
0x1800de038  lea     r9, [rbp+57h+var_78]
0x1800de03c  lea     r8, [rbp+57h+arg_0]
0x1800de040  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800de047  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800de04c  lea     rdx, [rbp+57h+var_78]
0x1800de050  lea     rcx, [rbp+57h+var_68]
0x1800de054  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800de059  mov     r9, rax
0x1800de05c  mov     ecx, ebx
0x1800de05e  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800de063  mov     r8, rax
0x1800de066  mov     edx, ebx
0x1800de068  lea     rcx, [rbp+57h+pExceptionObject]
0x1800de06c  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800de071  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800de078  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800de07c  call    _CxxThrowException_0
```

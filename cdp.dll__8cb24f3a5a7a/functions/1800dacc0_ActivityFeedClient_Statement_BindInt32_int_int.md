# ActivityFeedClient::Statement::BindInt32(int,int)

- ea: `0x1800dacc0`
- end: `0x1800dae26`
- name: `?BindInt32@Statement@ActivityFeedClient@@UEAAXHH@Z`
- size: `358`
- prototype: `void __fastcall(ActivityFeedClient::Statement *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800dacc0`
- `0x180143248`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dad41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dadbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dad41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dadbe`
- `winsqlite3!sqlite3_bind_int` at `0x1800dacf5`
- `winsqlite3!sqlite3_bind_int` at `0x1800dacf5`

## string_xrefs

- `0x1800dad67`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800dade4`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
void __fastcall ActivityFeedClient::Statement::BindInt32(
        ActivityFeedClient::Statement *this,
        unsigned int a2,
        unsigned int a3)
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
    v19 = 64;
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
  v6 = sqlite3_bind_int(*((_QWORD *)this + 1), a2, a3);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x87AF0000;
  if ( (v7 & 0x80000000) != 0 )
  {
    v18 = "onecoreuap\\windows\\cdp\\afc\\database\\Statement.h";
    v19 = 65;
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
0x1800dacc0  mov     [rsp-8+arg_8], rbx
0x1800dacc5  push    rbp
0x1800dacc6  push    rsi
0x1800dacc7  push    rdi
0x1800dacc8  lea     rbp, [rsp-47h]
0x1800daccd  sub     rsp, 90h
0x1800dacd4  mov     edi, r8d
0x1800dacd7  mov     esi, edx
0x1800dacd9  mov     rbx, rcx
0x1800dacdc  mov     rax, [rcx]
0x1800dacdf  mov     rax, [rax+8]
0x1800dace3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dace8  test    al, al
0x1800dacea  jz      short loc_1800DAD27
0x1800dacec  mov     r8d, edi
0x1800dacef  mov     edx, esi
0x1800dacf1  mov     rcx, [rbx+8]
0x1800dacf5  call    cs:__imp_sqlite3_bind_int
0x1800dacfb  mov     ebx, eax
0x1800dacfd  test    eax, eax
0x1800dacff  jg      short loc_1800DAD1C
0x1800dad01  test    ebx, ebx
0x1800dad03  js      loc_1800DADA9
0x1800dad09  mov     rbx, [rsp+0A0h+arg_8]
0x1800dad11  add     rsp, 90h
0x1800dad18  pop     rdi
0x1800dad19  pop     rsi
0x1800dad1a  pop     rbp
0x1800dad1b  retn
0x1800dad1c  movzx   ebx, ax
0x1800dad1f  or      ebx, 87AF0000h
0x1800dad25  jmp     short loc_1800DAD01
0x1800dad27  lea     rax, aOnecoreuapWind_46; "onecoreuap\\windows\\cdp\\afc\\database"...
0x1800dad2e  mov     [rbp+57h+var_70], rax
0x1800dad32  mov     [rbp+57h+var_68], 40h ; '@'
0x1800dad39  mov     ebx, 8007139Fh
0x1800dad3e  mov     [rbp+57h+arg_0], ebx
0x1800dad41  call    cs:__imp_GetCurrentThreadId
0x1800dad47  mov     eax, eax
0x1800dad49  mov     [rbp+57h+arg_18], rax
0x1800dad4d  lea     rax, [rbp+57h+arg_18]
0x1800dad51  mov     [rsp+0A0h+var_78], rax
0x1800dad56  lea     rax, [rbp+57h+var_68]
0x1800dad5a  mov     [rsp+0A0h+var_80], rax
0x1800dad5f  lea     r9, [rbp+57h+var_70]
0x1800dad63  lea     r8, [rbp+57h+arg_0]
0x1800dad67  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800dad6e  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800dad73  lea     rdx, [rbp+57h+var_70]
0x1800dad77  lea     rcx, [rbp+57h+var_60]
0x1800dad7b  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800dad80  mov     r9, rax
0x1800dad83  mov     ecx, ebx
0x1800dad85  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800dad8a  mov     r8, rax
0x1800dad8d  mov     edx, ebx
0x1800dad8f  lea     rcx, [rbp+57h+pExceptionObject]
0x1800dad93  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800dad98  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800dad9f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800dada3  call    _CxxThrowException_0
0x1800dada9  lea     rax, aOnecoreuapWind_46; "onecoreuap\\windows\\cdp\\afc\\database"...
0x1800dadb0  mov     [rbp+57h+var_70], rax
0x1800dadb4  mov     [rbp+57h+var_68], 41h ; 'A'
0x1800dadbb  mov     [rbp+57h+arg_0], ebx
0x1800dadbe  call    cs:__imp_GetCurrentThreadId
0x1800dadc4  mov     eax, eax
0x1800dadc6  mov     [rbp+57h+arg_18], rax
0x1800dadca  lea     rax, [rbp+57h+arg_18]
0x1800dadce  mov     [rsp+0A0h+var_78], rax
0x1800dadd3  lea     rax, [rbp+57h+var_68]
0x1800dadd7  mov     [rsp+0A0h+var_80], rax
0x1800daddc  lea     r9, [rbp+57h+var_70]
0x1800dade0  lea     r8, [rbp+57h+arg_0]
0x1800dade4  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800dadeb  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800dadf0  lea     rdx, [rbp+57h+var_70]
0x1800dadf4  lea     rcx, [rbp+57h+var_60]
0x1800dadf8  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800dadfd  mov     r9, rax
0x1800dae00  mov     ecx, ebx
0x1800dae02  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800dae07  mov     r8, rax
0x1800dae0a  mov     edx, ebx
0x1800dae0c  lea     rcx, [rbp+57h+pExceptionObject]
0x1800dae10  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800dae15  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800dae1c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800dae20  call    _CxxThrowException_0
```

# ActivityFeedClient::Statement::BindFloat(int,float)

- ea: `0x180308cc0`
- end: `0x180308e36`
- name: `?BindFloat@Statement@ActivityFeedClient@@UEAAXHM@Z`
- size: `374`
- prototype: `void __fastcall(ActivityFeedClient::Statement *__hidden this, int, float)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x1801fcb36`
- `0x180308cc0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180308d11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180308db4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180308d11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180308db4`
- `winsqlite3!sqlite3_bind_double` at `0x180308d86`
- `winsqlite3!sqlite3_bind_double` at `0x180308d86`

## string_xrefs

- `0x180308d37`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180308dda`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ActivityFeedClient::Statement::BindFloat(
        ActivityFeedClient::Statement *this,
        unsigned int a2,
        float a3)
{
  int v5; // ecx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  const char *v17; // [rsp+38h] [rbp-19h] BYREF
  int v18; // [rsp+40h] [rbp-11h] BYREF
  _BYTE v19[24]; // [rsp+48h] [rbp-9h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+60h] [rbp+Fh] BYREF
  int v21; // [rsp+B8h] [rbp+67h] BYREF
  __int64 CurrentThreadId; // [rsp+D0h] [rbp+7Fh] BYREF

  if ( !(*(unsigned __int8 (__fastcall **)(ActivityFeedClient::Statement *))(*(_QWORD *)this + 8LL))(this) )
  {
    v17 = "onecoreuap\\windows\\cdp\\afc\\database\\Statement.h";
    v18 = 79;
    v21 = -2147019873;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v5,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v21,
      (unsigned int)&v17,
      (__int64)&v18,
      (__int64)&CurrentThreadId);
    v6 = cdp::ExceptionStackFromSourceLocationInfo(v19, &v17);
    v9 = cdp::ErrorCodeToString(2147947423LL, v7, v8, v6);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147947423LL, v9);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v10 = sqlite3_bind_double(*((_QWORD *)this + 1), a2);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x87AF0000;
  if ( (v11 & 0x80000000) != 0 )
  {
    v17 = "onecoreuap\\windows\\cdp\\afc\\database\\Statement.h";
    v18 = 80;
    v21 = v11;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v12,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v21,
      (unsigned int)&v17,
      (__int64)&v18,
      (__int64)&CurrentThreadId);
    v13 = cdp::ExceptionStackFromSourceLocationInfo(v19, &v17);
    v16 = cdp::ErrorCodeToString(v11, v14, v15, v13);
    ConnectedDevices::Exception::Exception(pExceptionObject, v11, v16);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180308cc0  mov     rax, rsp
0x180308cc3  mov     [rax+10h], rbx
0x180308cc7  mov     [rax+18h], rdi
0x180308ccb  push    rbp
0x180308ccc  lea     rbp, [rax-5Fh]
0x180308cd0  sub     rsp, 0A0h
0x180308cd7  movaps  xmmword ptr [rax-18h], xmm6
0x180308cdb  movaps  xmm6, xmm2
0x180308cde  mov     edi, edx
0x180308ce0  mov     rbx, rcx
0x180308ce3  mov     rax, [rcx]
0x180308ce6  mov     rax, [rax+8]
0x180308cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180308cef  test    al, al
0x180308cf1  jnz     loc_180308D79
0x180308cf7  lea     rax, aOnecoreuapWind_46; "onecoreuap\\windows\\cdp\\afc\\database"...
0x180308cfe  mov     [rbp+57h+var_70], rax
0x180308d02  mov     [rbp+57h+var_68], 4Fh ; 'O'
0x180308d09  mov     ebx, 8007139Fh
0x180308d0e  mov     [rbp+57h+arg_0], ebx
0x180308d11  call    cs:__imp_GetCurrentThreadId
0x180308d17  mov     eax, eax
0x180308d19  mov     [rbp+57h+arg_18], rax
0x180308d1d  lea     rax, [rbp+57h+arg_18]
0x180308d21  mov     [rsp+0A0h+var_78], rax
0x180308d26  lea     rax, [rbp+57h+var_68]
0x180308d2a  mov     [rsp+0A0h+var_80], rax
0x180308d2f  lea     r9, [rbp+57h+var_70]
0x180308d33  lea     r8, [rbp+57h+arg_0]
0x180308d37  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180308d3e  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180308d43  lea     rdx, [rbp+57h+var_70]
0x180308d47  lea     rcx, [rbp+57h+var_60]
0x180308d4b  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180308d50  mov     r9, rax
0x180308d53  mov     ecx, ebx
0x180308d55  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180308d5a  mov     r8, rax
0x180308d5d  mov     edx, ebx
0x180308d5f  lea     rcx, [rbp+57h+pExceptionObject]
0x180308d63  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180308d68  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180308d6f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180308d73  call    _CxxThrowException_0
0x180308d79  xorps   xmm2, xmm2
0x180308d7c  cvtss2sd xmm2, xmm6
0x180308d80  mov     edx, edi
0x180308d82  mov     rcx, [rbx+8]
0x180308d86  call    cs:__imp_sqlite3_bind_double
0x180308d8c  mov     ebx, eax
0x180308d8e  test    eax, eax
0x180308d90  jle     short loc_180308D9B
0x180308d92  movzx   ebx, ax
0x180308d95  or      ebx, 87AF0000h
0x180308d9b  test    ebx, ebx
0x180308d9d  jns     short loc_180308E1C
0x180308d9f  lea     rax, aOnecoreuapWind_46; "onecoreuap\\windows\\cdp\\afc\\database"...
0x180308da6  mov     [rbp+57h+var_70], rax
0x180308daa  mov     [rbp+57h+var_68], 50h ; 'P'
0x180308db1  mov     [rbp+57h+arg_0], ebx
0x180308db4  call    cs:__imp_GetCurrentThreadId
0x180308dba  mov     eax, eax
0x180308dbc  mov     [rbp+57h+arg_18], rax
0x180308dc0  lea     rax, [rbp+57h+arg_18]
0x180308dc4  mov     [rsp+0A0h+var_78], rax
0x180308dc9  lea     rax, [rbp+57h+var_68]
0x180308dcd  mov     [rsp+0A0h+var_80], rax
0x180308dd2  lea     r9, [rbp+57h+var_70]
0x180308dd6  lea     r8, [rbp+57h+arg_0]
0x180308dda  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180308de1  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180308de6  lea     rdx, [rbp+57h+var_70]
0x180308dea  lea     rcx, [rbp+57h+var_60]
0x180308dee  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180308df3  mov     r9, rax
0x180308df6  mov     ecx, ebx
0x180308df8  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180308dfd  mov     r8, rax
0x180308e00  mov     edx, ebx
0x180308e02  lea     rcx, [rbp+57h+pExceptionObject]
0x180308e06  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180308e0b  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180308e12  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180308e16  call    _CxxThrowException_0
0x180308e1c  lea     r11, [rsp+0A0h+var_s0]
0x180308e24  mov     rbx, [r11+18h]
0x180308e28  mov     rdi, [r11+20h]
0x180308e2c  movaps  xmm6, xmmword ptr [r11-10h]
0x180308e31  mov     rsp, r11
0x180308e34  pop     rbp
0x180308e35  retn
```

# ActivityFeedClient::Statement::BindFloat(int,double)

- ea: `0x180308e40`
- end: `0x180308fb2`
- name: `?BindFloat@Statement@ActivityFeedClient@@UEAAXHN@Z`
- size: `370`
- prototype: `void __fastcall(ActivityFeedClient::Statement *__hidden this, int, double)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x1801fcb36`
- `0x180308e40`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180308e91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180308f30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180308e91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180308f30`
- `winsqlite3!sqlite3_bind_double` at `0x180308f02`
- `winsqlite3!sqlite3_bind_double` at `0x180308f02`

## string_xrefs

- `0x180308eb7`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180308f56`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ActivityFeedClient::Statement::BindFloat(
        ActivityFeedClient::Statement *this,
        unsigned int a2,
        double a3)
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
    v18 = 72;
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
    v18 = 73;
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
0x180308e40  mov     rax, rsp
0x180308e43  mov     [rax+10h], rbx
0x180308e47  mov     [rax+18h], rdi
0x180308e4b  push    rbp
0x180308e4c  lea     rbp, [rax-5Fh]
0x180308e50  sub     rsp, 0A0h
0x180308e57  movaps  xmmword ptr [rax-18h], xmm6
0x180308e5b  movaps  xmm6, xmm2
0x180308e5e  mov     edi, edx
0x180308e60  mov     rbx, rcx
0x180308e63  mov     rax, [rcx]
0x180308e66  mov     rax, [rax+8]
0x180308e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180308e6f  test    al, al
0x180308e71  jnz     loc_180308EF9
0x180308e77  lea     rax, aOnecoreuapWind_46; "onecoreuap\\windows\\cdp\\afc\\database"...
0x180308e7e  mov     [rbp+57h+var_70], rax
0x180308e82  mov     [rbp+57h+var_68], 48h ; 'H'
0x180308e89  mov     ebx, 8007139Fh
0x180308e8e  mov     [rbp+57h+arg_0], ebx
0x180308e91  call    cs:__imp_GetCurrentThreadId
0x180308e97  mov     eax, eax
0x180308e99  mov     [rbp+57h+arg_18], rax
0x180308e9d  lea     rax, [rbp+57h+arg_18]
0x180308ea1  mov     [rsp+0A0h+var_78], rax
0x180308ea6  lea     rax, [rbp+57h+var_68]
0x180308eaa  mov     [rsp+0A0h+var_80], rax
0x180308eaf  lea     r9, [rbp+57h+var_70]
0x180308eb3  lea     r8, [rbp+57h+arg_0]
0x180308eb7  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180308ebe  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180308ec3  lea     rdx, [rbp+57h+var_70]
0x180308ec7  lea     rcx, [rbp+57h+var_60]
0x180308ecb  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180308ed0  mov     r9, rax
0x180308ed3  mov     ecx, ebx
0x180308ed5  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180308eda  mov     r8, rax
0x180308edd  mov     edx, ebx
0x180308edf  lea     rcx, [rbp+57h+pExceptionObject]
0x180308ee3  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180308ee8  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180308eef  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180308ef3  call    _CxxThrowException_0
0x180308ef9  movaps  xmm2, xmm6
0x180308efc  mov     edx, edi
0x180308efe  mov     rcx, [rbx+8]
0x180308f02  call    cs:__imp_sqlite3_bind_double
0x180308f08  mov     ebx, eax
0x180308f0a  test    eax, eax
0x180308f0c  jle     short loc_180308F17
0x180308f0e  movzx   ebx, ax
0x180308f11  or      ebx, 87AF0000h
0x180308f17  test    ebx, ebx
0x180308f19  jns     short loc_180308F98
0x180308f1b  lea     rax, aOnecoreuapWind_46; "onecoreuap\\windows\\cdp\\afc\\database"...
0x180308f22  mov     [rbp+57h+var_70], rax
0x180308f26  mov     [rbp+57h+var_68], 49h ; 'I'
0x180308f2d  mov     [rbp+57h+arg_0], ebx
0x180308f30  call    cs:__imp_GetCurrentThreadId
0x180308f36  mov     eax, eax
0x180308f38  mov     [rbp+57h+arg_18], rax
0x180308f3c  lea     rax, [rbp+57h+arg_18]
0x180308f40  mov     [rsp+0A0h+var_78], rax
0x180308f45  lea     rax, [rbp+57h+var_68]
0x180308f49  mov     [rsp+0A0h+var_80], rax
0x180308f4e  lea     r9, [rbp+57h+var_70]
0x180308f52  lea     r8, [rbp+57h+arg_0]
0x180308f56  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180308f5d  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180308f62  lea     rdx, [rbp+57h+var_70]
0x180308f66  lea     rcx, [rbp+57h+var_60]
0x180308f6a  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180308f6f  mov     r9, rax
0x180308f72  mov     ecx, ebx
0x180308f74  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180308f79  mov     r8, rax
0x180308f7c  mov     edx, ebx
0x180308f7e  lea     rcx, [rbp+57h+pExceptionObject]
0x180308f82  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180308f87  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180308f8e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180308f92  call    _CxxThrowException_0
0x180308f98  lea     r11, [rsp+0A0h+var_s0]
0x180308fa0  mov     rbx, [r11+18h]
0x180308fa4  mov     rdi, [r11+20h]
0x180308fa8  movaps  xmm6, xmmword ptr [r11-10h]
0x180308fad  mov     rsp, r11
0x180308fb0  pop     rbp
0x180308fb1  retn
```

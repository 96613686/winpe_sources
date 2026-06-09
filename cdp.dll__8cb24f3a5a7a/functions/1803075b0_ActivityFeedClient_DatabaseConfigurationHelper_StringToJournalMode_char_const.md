# ActivityFeedClient::DatabaseConfigurationHelper::StringToJournalMode(char const *)

- ea: `0x1803075b0`
- end: `0x180307700`
- name: `?StringToJournalMode@DatabaseConfigurationHelper@ActivityFeedClient@@AEAA?AW4JournalMode@12@PEBD@Z`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180307358`

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x1801fcb36`
- `0x1803075b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1803075d4`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1803075fe`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180307619`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180307634`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18030764f`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18030766a`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1803075d4`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1803075fe`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180307619`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180307634`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18030764f`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18030766a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180307698`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180307698`

## string_xrefs

- `0x1803076be`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1803075ca`: `DELETE`
- `0x18030767e`: `.\databaseconfigurationhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ActivityFeedClient::DatabaseConfigurationHelper::StringToJournalMode(__int64 a1, __int64 a2)
{
  int v4; // ecx
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rax
  const char *v9; // [rsp+30h] [rbp-9h] BYREF
  int v10; // [rsp+38h] [rbp-1h] BYREF
  _BYTE v11[24]; // [rsp+40h] [rbp+7h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+58h] [rbp+1Fh] BYREF
  __int64 v13; // [rsp+A0h] [rbp+67h] BYREF
  __int64 CurrentThreadId; // [rsp+B0h] [rbp+77h] BYREF

  v13 = a1;
  if ( !(unsigned int)_o__stricmp(a2, "DELETE") )
    return 1;
  if ( !(unsigned int)_o__stricmp(a2, "TRUNCATE") )
    return 2;
  if ( !(unsigned int)_o__stricmp(a2, "PERSIST") )
    return 3;
  if ( !(unsigned int)_o__stricmp(a2, "MEMORY") )
    return 4;
  if ( !(unsigned int)_o__stricmp(a2, "WAL") )
    return 5;
  if ( (unsigned int)_o__stricmp(a2, "OFF") )
  {
    v9 = ".\\databaseconfigurationhelper.cpp";
    v10 = 577;
    LODWORD(v13) = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v4,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v13,
      (unsigned int)&v9,
      (__int64)&v10,
      (__int64)&CurrentThreadId);
    v5 = cdp::ExceptionStackFromSourceLocationInfo(v11, &v9);
    v8 = cdp::ErrorCodeToString(2147942487LL, v6, v7, v5);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147942487LL, v8);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  return 6;
}

```

## disassembly

```asm
0x1803075b0  mov     [rsp-8+arg_8], rbx
0x1803075b5  mov     [rsp-8+arg_0], rcx
0x1803075ba  push    rbp
0x1803075bb  lea     rbp, [rsp-57h]
0x1803075c0  sub     rsp, 90h
0x1803075c7  mov     rbx, rdx
0x1803075ca  lea     rdx, aDelete_0; "DELETE"
0x1803075d1  mov     rcx, rbx
0x1803075d4  call    cs:__imp__o__stricmp
0x1803075da  test    eax, eax
0x1803075dc  jnz     short loc_1803075F4
0x1803075de  mov     eax, 1
0x1803075e3  mov     rbx, [rsp+90h+arg_8]
0x1803075eb  add     rsp, 90h
0x1803075f2  pop     rbp
0x1803075f3  retn
0x1803075f4  lea     rdx, aTruncate; "TRUNCATE"
0x1803075fb  mov     rcx, rbx
0x1803075fe  call    cs:__imp__o__stricmp
0x180307604  test    eax, eax
0x180307606  jnz     short loc_18030760F
0x180307608  mov     eax, 2
0x18030760d  jmp     short loc_1803075E3
0x18030760f  lea     rdx, aPersist; "PERSIST"
0x180307616  mov     rcx, rbx
0x180307619  call    cs:__imp__o__stricmp
0x18030761f  test    eax, eax
0x180307621  jnz     short loc_18030762A
0x180307623  mov     eax, 3
0x180307628  jmp     short loc_1803075E3
0x18030762a  lea     rdx, aMemory; "MEMORY"
0x180307631  mov     rcx, rbx
0x180307634  call    cs:__imp__o__stricmp
0x18030763a  test    eax, eax
0x18030763c  jnz     short loc_180307645
0x18030763e  mov     eax, 4
0x180307643  jmp     short loc_1803075E3
0x180307645  lea     rdx, aWal; "WAL"
0x18030764c  mov     rcx, rbx
0x18030764f  call    cs:__imp__o__stricmp
0x180307655  test    eax, eax
0x180307657  jnz     short loc_180307660
0x180307659  mov     eax, 5
0x18030765e  jmp     short loc_1803075E3
0x180307660  lea     rdx, aOff; "OFF"
0x180307667  mov     rcx, rbx
0x18030766a  call    cs:__imp__o__stricmp
0x180307670  test    eax, eax
0x180307672  jnz     short loc_18030767E
0x180307674  mov     eax, 6
0x180307679  jmp     loc_1803075E3
0x18030767e  lea     rax, aDatabaseconfig; ".\\databaseconfigurationhelper.cpp"
0x180307685  mov     [rbp+57h+var_60], rax
0x180307689  mov     [rbp+57h+var_58], 241h
0x180307690  mov     ebx, 80070057h
0x180307695  mov     dword ptr [rbp+57h+arg_0], ebx
0x180307698  call    cs:__imp_GetCurrentThreadId
0x18030769e  mov     eax, eax
0x1803076a0  mov     [rbp+57h+arg_10], rax
0x1803076a4  lea     rax, [rbp+57h+arg_10]
0x1803076a8  mov     [rsp+90h+var_68], rax
0x1803076ad  lea     rax, [rbp+57h+var_58]
0x1803076b1  mov     [rsp+90h+var_70], rax
0x1803076b6  lea     r9, [rbp+57h+var_60]
0x1803076ba  lea     r8, [rbp+57h+arg_0]
0x1803076be  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1803076c5  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1803076ca  lea     rdx, [rbp+57h+var_60]
0x1803076ce  lea     rcx, [rbp+57h+var_50]
0x1803076d2  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1803076d7  mov     r9, rax
0x1803076da  mov     ecx, ebx
0x1803076dc  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1803076e1  mov     r8, rax
0x1803076e4  mov     edx, ebx
0x1803076e6  lea     rcx, [rbp+57h+pExceptionObject]
0x1803076ea  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1803076ef  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1803076f6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1803076fa  call    _CxxThrowException_0
```

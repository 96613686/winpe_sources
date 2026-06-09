# shared::FileTraceLogHandler::FileQueueItemHandler::TruncateIfNeeded(void)

- ea: `0x1801ca940`
- end: `0x1801caa52`
- name: `?TruncateIfNeeded@FileQueueItemHandler@FileTraceLogHandler@shared@@AEAAXXZ`
- size: `274`
- prototype: `void __fastcall(shared::FileTraceLogHandler::FileQueueItemHandler *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180238fd0`
- `0x18023908c`

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x1801ca940`
- `0x1801fcb36`
- `0x1802394e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801ca9ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801ca9ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ca981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ca981`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801ca973`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801ca973`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801caa29`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801caa29`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1801caa3b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1801caa3b`

## string_xrefs

- `0x1801ca9d1`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall shared::FileTraceLogHandler::FileQueueItemHandler::TruncateIfNeeded(
        shared::FileTraceLogHandler::FileQueueItemHandler *this)
{
  char *v2; // rcx
  signed int LastError; // eax
  unsigned int v4; // ebx
  int v5; // ecx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  const char *v10; // [rsp+30h] [rbp-9h] BYREF
  int v11; // [rsp+38h] [rbp-1h] BYREF
  _BYTE v12[24]; // [rsp+40h] [rbp+7h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+58h] [rbp+1Fh] BYREF
  unsigned int v14; // [rsp+A0h] [rbp+67h] BYREF
  _LARGE_INTEGER FileSize; // [rsp+A8h] [rbp+6Fh] BYREF
  __int64 CurrentThreadId; // [rsp+B0h] [rbp+77h] BYREF

  v2 = (char *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(v2, &FileSize) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v10 = ".\\filetraceloghandler.cpp";
      v11 = 121;
      v14 = v4;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v5,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v14,
        (unsigned int)&v10,
        (__int64)&v11,
        (__int64)&CurrentThreadId);
      v6 = cdp::ExceptionStackFromSourceLocationInfo(v12, &v10);
      v9 = cdp::ErrorCodeToString(v4, v7, v8, v6);
      ConnectedDevices::Exception::Exception(pExceptionObject, v4, v9);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    if ( FileSize.QuadPart > 0x400000 )
    {
      SetFilePointer(*((HANDLE *)this + 1), 0, 0, 0);
      shared::FileTraceLogHandler::FileQueueItemHandler::WriteByteOrderMarker(this);
      SetEndOfFile(*((HANDLE *)this + 1));
    }
  }
}

```

## disassembly

```asm
0x1801ca940  mov     [rsp-8+arg_18], rbx
0x1801ca945  push    rbp
0x1801ca946  lea     rbp, [rsp-57h]
0x1801ca94b  sub     rsp, 90h
0x1801ca952  mov     rbx, rcx
0x1801ca955  mov     rcx, [rcx+8]; hFile
0x1801ca959  lea     rax, [rcx-1]
0x1801ca95d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801ca961  ja      loc_1801CAA41
0x1801ca967  mov     qword ptr [rbp+57h+FileSize], 0
0x1801ca96f  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x1801ca973  call    cs:__imp_GetFileSizeEx
0x1801ca979  test    eax, eax
0x1801ca97b  jnz     loc_1801CAA13
0x1801ca981  call    cs:__imp_GetLastError
0x1801ca987  mov     ebx, eax
0x1801ca989  test    eax, eax
0x1801ca98b  jle     short loc_1801CA996
0x1801ca98d  movzx   ebx, ax
0x1801ca990  or      ebx, 80070000h
0x1801ca996  lea     rax, aFiletracelogha; ".\\filetraceloghandler.cpp"
0x1801ca99d  mov     [rbp+57h+var_60], rax
0x1801ca9a1  mov     [rbp+57h+var_58], 79h ; 'y'
0x1801ca9a8  mov     [rbp+57h+arg_0], ebx
0x1801ca9ab  call    cs:__imp_GetCurrentThreadId
0x1801ca9b1  mov     eax, eax
0x1801ca9b3  mov     [rbp+57h+arg_10], rax
0x1801ca9b7  lea     rax, [rbp+57h+arg_10]
0x1801ca9bb  mov     [rsp+90h+var_68], rax
0x1801ca9c0  lea     rax, [rbp+57h+var_58]
0x1801ca9c4  mov     [rsp+90h+var_70], rax
0x1801ca9c9  lea     r9, [rbp+57h+var_60]
0x1801ca9cd  lea     r8, [rbp+57h+arg_0]
0x1801ca9d1  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801ca9d8  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801ca9dd  lea     rdx, [rbp+57h+var_60]
0x1801ca9e1  lea     rcx, [rbp+57h+var_50]
0x1801ca9e5  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801ca9ea  mov     r9, rax
0x1801ca9ed  mov     ecx, ebx
0x1801ca9ef  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801ca9f4  mov     r8, rax
0x1801ca9f7  mov     edx, ebx
0x1801ca9f9  lea     rcx, [rbp+57h+pExceptionObject]
0x1801ca9fd  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801caa02  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801caa09  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801caa0d  call    _CxxThrowException_0
0x1801caa13  cmp     qword ptr [rbp+57h+FileSize], 400000h
0x1801caa1b  jle     short loc_1801CAA41
0x1801caa1d  xor     r9d, r9d; dwMoveMethod
0x1801caa20  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801caa23  xor     edx, edx; lDistanceToMove
0x1801caa25  mov     rcx, [rbx+8]; hFile
0x1801caa29  call    cs:__imp_SetFilePointer
0x1801caa2f  mov     rcx, rbx; this
0x1801caa32  call    ?WriteByteOrderMarker@FileQueueItemHandler@FileTraceLogHandler@shared@@AEAAXXZ; shared::FileTraceLogHandler::FileQueueItemHandler::WriteByteOrderMarker(void)
0x1801caa37  mov     rcx, [rbx+8]; hFile
0x1801caa3b  call    cs:__imp_SetEndOfFile
0x1801caa41  mov     rbx, [rsp+90h+arg_18]
0x1801caa49  add     rsp, 90h
0x1801caa50  pop     rbp
0x1801caa51  retn
```

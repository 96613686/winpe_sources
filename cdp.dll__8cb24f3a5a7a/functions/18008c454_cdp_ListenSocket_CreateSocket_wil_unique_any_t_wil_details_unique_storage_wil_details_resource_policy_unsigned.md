# cdp::ListenSocket::CreateSocket(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> &,shared::EndpointType)

- ea: `0x18008c454`
- end: `0x18008c626`
- name: `?CreateSocket@ListenSocket@cdp@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@W4EndpointType@shared@@@Z`
- size: `466`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180089dc4`
- `0x18008bd64`

## callees

- `0x18008c454`
- `0x18008dbc0`
- `0x180135158`
- `0x1801fcb36`
- `0x1802a3cec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c5c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c5c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008c5d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008c5d7`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18008c522`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18008c522`
- `WS2_32!WSASocketW` at `0x18008c4ab`
- `WS2_32!WSASocketW` at `0x18008c4ab`
- `WS2_32!__imp_closesocket` at `0x18008c5cf`
- `WS2_32!__imp_closesocket` at `0x18008c5cf`
- `WS2_32!__imp_setsockopt` at `0x18008c4f2`
- `WS2_32!__imp_setsockopt` at `0x18008c4f2`
- `WS2_32!__imp_WSAGetLastError` at `0x18008c549`
- `WS2_32!__imp_WSAGetLastError` at `0x18008c5e2`
- `WS2_32!__imp_WSAGetLastError` at `0x18008c549`
- `WS2_32!__imp_WSAGetLastError` at `0x18008c5e2`

## string_xrefs

- `0x18008c501`: `{"text":"ListenSocket enabled ERTM (RfComm)"}`
- `0x18008c59b`: `Failed to register the socket with the IO completion port`
- `0x18008c5f6`: `Failed to set ERTM mode (Rfcomm listen socket), WSA error %d`

## pseudocode

```c
HANDLE __fastcall cdp::ListenSocket::CreateSocket(__int64 a1, HANDLE *a2, __int16 a3)
{
  bool v5; // zf
  int v7; // r8d
  int v8; // ecx
  SOCKET v9; // rax
  HANDLE v10; // r15
  SOCKET v11; // rdi
  HANDLE *v12; // rbx
  HANDLE result; // rax
  DWORD LastError; // ebx
  const char *v15; // [rsp+30h] [rbp-50h] BYREF
  int v16; // [rsp+38h] [rbp-48h]
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-40h] BYREF
  int Error; // [rsp+B8h] [rbp+38h] BYREF
  int optval; // [rsp+C0h] [rbp+40h] BYREF

  v5 = a3 == 5;
  v7 = 3;
  v8 = 32;
  if ( !v5 )
  {
    v7 = 6;
    v8 = 2;
  }
  v9 = WSASocketW(v8, 1, v7, 0, 0, 1u);
  v10 = *a2;
  v11 = v9;
  if ( *a2 != (HANDLE)-1LL )
  {
    LastError = GetLastError();
    closesocket((SOCKET)v10);
    SetLastError(LastError);
  }
  *a2 = (HANDLE)v11;
  if ( v11 == -1 )
  {
    v16 = 160;
    optval = WSAGetLastError();
    v15 = ".\\listensocket.cpp";
    cdp::MakeException<cdp::PlatformException<-2147220991>,int>(
      pExceptionObject,
      &v15,
      "Failed listen socket init %d",
      (unsigned int)&optval);
    throw (cdp::PlatformException<-2147220991> *)pExceptionObject;
  }
  if ( a3 == 5 )
  {
    optval = 1;
    if ( setsockopt(v11, 3, -2147483632, (const char *)&optval, 4) == -1 )
    {
      v16 = 172;
      Error = WSAGetLastError();
      v15 = ".\\listensocket.cpp";
      cdp::MakeException<cdp::PlatformException<-2147220991>,int>(
        pExceptionObject,
        &v15,
        "Failed to set ERTM mode (Rfcomm listen socket), WSA error %d",
        (unsigned int)&Error);
      throw (cdp::PlatformException<-2147220991> *)pExceptionObject;
    }
    Log<>(3, "{\"text\":\"ListenSocket enabled ERTM (RfComm)\"}");
  }
  v12 = *(HANDLE **)(a1 + 24);
  result = CreateIoCompletionPort(*a2, *v12, 0, 0);
  if ( *v12 != result )
  {
    v16 = 236;
    v15 = ".\\socket.cpp";
    cdp::MakeException<cdp::HResultException<-2147467259>,>(
      pExceptionObject,
      &v15,
      "Failed to register the socket with the IO completion port");
    throw (cdp::HResultException<-2147467259> *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18008c454  mov     [rsp-28h+arg_0], rbx
0x18008c459  mov     [rsp-28h+arg_18], rsi
0x18008c45e  push    rbp
0x18008c45f  push    rdi
0x18008c460  push    r13
0x18008c462  push    r14
0x18008c464  push    r15
0x18008c466  mov     rbp, rsp
0x18008c469  sub     rsp, 80h
0x18008c470  mov     eax, 6
0x18008c475  mov     [rsp+80h+dwFlags], 1; dwFlags
0x18008c47d  movzx   r14d, r8w
0x18008c481  mov     [rsp+80h+g], 0; g
0x18008c489  mov     r13, rcx
0x18008c48c  cmp     r14w, 5
0x18008c491  mov     rsi, rdx
0x18008c494  lea     r8d, [rax-3]
0x18008c498  lea     ecx, [rax+1Ah]
0x18008c49b  cmovnz  r8d, eax; protocol
0x18008c49f  lea     eax, [rcx-1Eh]
0x18008c4a2  cmovnz  ecx, eax; af
0x18008c4a5  lea     edx, [rax-1]; type
0x18008c4a8  xor     r9d, r9d; lpProtocolInfo
0x18008c4ab  call    cs:__imp_WSASocketW
0x18008c4b1  mov     r15, [rsi]
0x18008c4b4  mov     rdi, rax
0x18008c4b7  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18008c4bb  jnz     loc_18008C5C4
0x18008c4c1  mov     [rsi], rdi
0x18008c4c4  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18008c4c8  jz      short loc_18008C549
0x18008c4ca  cmp     r14w, 5
0x18008c4cf  jnz     short loc_18008C512
0x18008c4d1  lea     r9, [rbp+optval]; optval
0x18008c4d5  mov     [rbp+optval], 1
0x18008c4dc  mov     edx, 3; level
0x18008c4e1  mov     [rsp+80h+g], 4; optlen
0x18008c4e9  mov     r8d, 80000010h; optname
0x18008c4ef  mov     rcx, rdi; s
0x18008c4f2  call    cs:__imp_setsockopt
0x18008c4f8  cmp     eax, 0FFFFFFFFh
0x18008c4fb  jz      loc_18008C5E2
0x18008c501  lea     rdx, aTextListensock_0; "{\"text\":\"ListenSocket enabled ERTM ("...
0x18008c508  mov     ecx, 3
0x18008c50d  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18008c512  mov     rbx, [r13+18h]
0x18008c516  xor     r9d, r9d; NumberOfConcurrentThreads
0x18008c519  mov     rcx, [rsi]; FileHandle
0x18008c51c  xor     r8d, r8d; CompletionKey
0x18008c51f  mov     rdx, [rbx]; ExistingCompletionPort
0x18008c522  call    cs:__imp_CreateIoCompletionPort
0x18008c528  cmp     [rbx], rax
0x18008c52b  jnz     short loc_18008C58D
0x18008c52d  lea     r11, [rsp+80h+var_s0]
0x18008c535  mov     rbx, [r11+30h]
0x18008c539  mov     rsi, [r11+48h]
0x18008c53d  mov     rsp, r11
0x18008c540  pop     r15
0x18008c542  pop     r14
0x18008c544  pop     r13
0x18008c546  pop     rdi
0x18008c547  pop     rbp
0x18008c548  retn
0x18008c549  call    cs:__imp_WSAGetLastError
0x18008c54f  lea     r9, [rbp+optval]
0x18008c553  mov     [rbp+var_48], 0A0h
0x18008c55a  mov     [rbp+optval], eax
0x18008c55d  lea     r8, aFailedListenSo; "Failed listen socket init %d"
0x18008c564  lea     rax, aListensocketCp; ".\\listensocket.cpp"
0x18008c56b  lea     rdx, [rbp+var_50]
0x18008c56f  mov     [rbp+var_50], rax
0x18008c573  lea     rcx, [rbp+pExceptionObject]
0x18008c577  call    ??$MakeException@V?$PlatformException@$0?HPPLPNPP@@cdp@@H@cdp@@YA?AV?$PlatformException@$0?HPPLPNPP@@0@AEBUCDPSourceLocationInfo@0@PEBD$$QEAH@Z; cdp::MakeException<cdp::PlatformException<-2147220991>,int>(cdp::CDPSourceLocationInfo const &,char const *,int &&)
0x18008c57c  lea     rdx, _TI6?AV?$PlatformException@$0?HPPLPNPP@@cdp@@; pThrowInfo
0x18008c583  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18008c587  call    _CxxThrowException_0
0x18008c58d  lea     rax, aSocketCpp; ".\\socket.cpp"
0x18008c594  mov     [rbp+var_48], 0ECh
0x18008c59b  lea     r8, aFailedToRegist_0; "Failed to register the socket with the "...
0x18008c5a2  mov     [rbp+var_50], rax
0x18008c5a6  lea     rdx, [rbp+var_50]
0x18008c5aa  lea     rcx, [rbp+pExceptionObject]
0x18008c5ae  call    ??$MakeException@V?$HResultException@$0?HPPPLPPL@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPLPPL@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147467259>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x18008c5b3  lea     rdx, _TI5?AV?$HResultException@$0?HPPPLPPL@@cdp@@; pThrowInfo
0x18008c5ba  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18008c5be  call    _CxxThrowException_0
0x18008c5c4  call    cs:__imp_GetLastError
0x18008c5ca  mov     rcx, r15; s
0x18008c5cd  mov     ebx, eax
0x18008c5cf  call    cs:__imp_closesocket
0x18008c5d5  mov     ecx, ebx; dwErrCode
0x18008c5d7  call    cs:__imp_SetLastError
0x18008c5dd  jmp     loc_18008C4C1
0x18008c5e2  call    cs:__imp_WSAGetLastError
0x18008c5e8  lea     r9, [rbp+arg_8]
0x18008c5ec  mov     [rbp+var_48], 0ACh
0x18008c5f3  mov     [rbp+arg_8], eax
0x18008c5f6  lea     r8, aFailedToSetErt; "Failed to set ERTM mode (Rfcomm listen "...
0x18008c5fd  lea     rax, aListensocketCp; ".\\listensocket.cpp"
0x18008c604  lea     rdx, [rbp+var_50]
0x18008c608  mov     [rbp+var_50], rax
0x18008c60c  lea     rcx, [rbp+pExceptionObject]
0x18008c610  call    ??$MakeException@V?$PlatformException@$0?HPPLPNPP@@cdp@@H@cdp@@YA?AV?$PlatformException@$0?HPPLPNPP@@0@AEBUCDPSourceLocationInfo@0@PEBD$$QEAH@Z; cdp::MakeException<cdp::PlatformException<-2147220991>,int>(cdp::CDPSourceLocationInfo const &,char const *,int &&)
0x18008c615  lea     rdx, _TI6?AV?$PlatformException@$0?HPPLPNPP@@cdp@@; pThrowInfo
0x18008c61c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18008c620  call    _CxxThrowException_0
```

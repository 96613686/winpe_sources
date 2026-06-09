# I_RpcAsyncSetHandle

- ea: `0x18005faa0`
- end: `0x18005fc9f`
- name: `I_RpcAsyncSetHandle`
- size: `511`
- prototype: `RPC_STATUS __stdcall(PRPC_MESSAGE Message, PRPC_ASYNC_STATE pAsync)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c90`
- `0x180002100`
- `0x18005ef40`
- `0x1800cc850`
- `0x1800ccdc0`

## callees

- `0x180022870`
- `0x18002499c`
- `0x18005ca40`
- `0x18005faa0`
- `0x180061948`
- `0x18006ab00`
- `0x1800a3fd4`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18005fc16`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18005fc16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005fc0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005fc0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005fb1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005fb1c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005fb0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005fb0e`

## pseudocode

```c
RPC_STATUS __stdcall I_RpcAsyncSetHandle(PRPC_MESSAGE Message, PRPC_ASYNC_STATE pAsync)
{
  _DWORD *Handle; // rdi
  RPC_STATUS v5; // ebp
  RPC_STATUS result; // eax
  GENERIC_OBJECT *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rax
  RPC_STATUS v10; // ebx
  int v11; // eax
  RPC_WSTR v12; // rsi
  char *v13; // rbx
  DWORD CurrentProcessId; // edi
  unsigned int CommandLineW; // eax
  int v16; // ecx
  RPC_WSTR StringBinding; // [rsp+50h] [rbp+8h] BYREF
  RPC_WSTR Protseq; // [rsp+60h] [rbp+18h] BYREF

  Handle = Message->Handle;
  StringBinding = 0;
  Protseq = 0;
  if ( !Handle || Handle[2] != -1985229329 || (Handle[3] & 0x20306C) == 0 )
    return 1702;
  if ( pAsync->NotificationType != RpcNotificationTypeHwnd || (Handle[3] & 0x1024) == 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)Handle + 80LL))(Handle);
    if ( !v5 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)pAsync->Reserved);
      pAsync->RuntimeInfo = Handle;
      ReleaseSRWLockExclusive((PSRWLOCK)pAsync->Reserved);
    }
    return v5;
  }
  v7 = (GENERIC_OBJECT *)(*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)Handle + 272LL))(Handle);
  if ( !RpcHasBeenInitialized )
  {
    result = PerformRpcInitialization();
    if ( result )
      return result;
  }
  if ( GENERIC_OBJECT::InvalidHandle(v7, 3350616) )
    return 1702;
  v9 = *(_QWORD *)v7;
  if ( (*((_DWORD *)v7 + 3) & 0x130010) != 0 )
    result = (*(__int64 (__fastcall **)(__int64, RPC_WSTR *))(v9 + 176))(v8, &StringBinding);
  else
    result = (*(__int64 (__fastcall **)(__int64, RPC_WSTR *))(v9 + 368))(v8, &StringBinding);
  if ( !result )
  {
    v10 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    if ( RpcHasBeenInitialized || !(unsigned int)PerformRpcInitialization() )
    {
      FreeWrapper(StringBinding);
      StringBinding = 0;
    }
    if ( v10 )
    {
      return v10;
    }
    else
    {
      v11 = ShouldSkipLogging(3u);
      v12 = Protseq;
      if ( !v11 && (Microsoft_Windows_RPC_EventsEnableBits & 1) != 0 )
      {
        v13 = (char *)Message->RpcInterfaceInformation + 4;
        CurrentProcessId = GetCurrentProcessId();
        CommandLineW = (unsigned int)GetCommandLineW();
        McTemplateU0zdzj_EtwEventWriteTransfer(
          v16,
          (unsigned int)RPC_EVENTLOG_ASYNC_HWND_USE_ERR,
          CommandLineW,
          CurrentProcessId,
          (__int64)v12,
          (__int64)v13);
      }
      if ( RpcHasBeenInitialized || !(unsigned int)PerformRpcInitialization() )
        FreeWrapper(v12);
      return 1764;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005faa0  mov     rax, rsp
0x18005faa3  mov     [rax+10h], rbx
0x18005faa7  mov     [rax+20h], rbp
0x18005faab  push    rsi
0x18005faac  push    rdi
0x18005faad  push    r14
0x18005faaf  sub     rsp, 30h
0x18005fab3  mov     rdi, [rcx]
0x18005fab6  mov     rsi, rdx
0x18005fab9  mov     qword ptr [rax+8], 0
0x18005fac1  mov     r14, rcx
0x18005fac4  mov     qword ptr [rax+18h], 0
0x18005facc  test    rdi, rdi
0x18005facf  jz      loc_18005FC53
0x18005fad5  cmp     dword ptr [rdi+8], 89ABCDEFh
0x18005fadc  jnz     loc_18005FC53
0x18005fae2  test    dword ptr [rdi+0Ch], 20306Ch
0x18005fae9  jz      loc_18005FC53
0x18005faef  cmp     dword ptr [rdx+2Ch], 4
0x18005faf3  jz      short loc_18005FB37
0x18005faf5  mov     rax, [rdi]
0x18005faf8  mov     rcx, rdi
0x18005fafb  mov     rax, [rax+50h]
0x18005faff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb04  mov     ebp, eax
0x18005fb06  test    eax, eax
0x18005fb08  jnz     short loc_18005FB22
0x18005fb0a  lea     rcx, [rsi+50h]; SRWLock
0x18005fb0e  call    cs:__imp_AcquireSRWLockExclusive
0x18005fb14  lea     rcx, [rsi+50h]; SRWLock
0x18005fb18  mov     [rsi+20h], rdi
0x18005fb1c  call    cs:__imp_ReleaseSRWLockExclusive
0x18005fb22  mov     eax, ebp
0x18005fb24  mov     rbx, [rsp+48h+arg_8]
0x18005fb29  mov     rbp, [rsp+48h+arg_18]
0x18005fb2e  add     rsp, 30h
0x18005fb32  pop     r14
0x18005fb34  pop     rdi
0x18005fb35  pop     rsi
0x18005fb36  retn
0x18005fb37  test    dword ptr [rdi+0Ch], 1024h
0x18005fb3e  jz      short loc_18005FAF5
0x18005fb40  mov     rax, [rdi]
0x18005fb43  mov     rcx, rdi
0x18005fb46  mov     rax, [rax+110h]
0x18005fb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb52  cmp     cs:?RpcHasBeenInitialized@@3HA, 0; int RpcHasBeenInitialized
0x18005fb59  mov     rbx, rax
0x18005fb5c  jz      loc_18005FC7A
0x18005fb62  mov     edx, 332058h; int
0x18005fb67  mov     rcx, rbx; this
0x18005fb6a  call    ?InvalidHandle@GENERIC_OBJECT@@QEAAIH@Z; GENERIC_OBJECT::InvalidHandle(int)
0x18005fb6f  test    eax, eax
0x18005fb71  jnz     loc_18005FC53
0x18005fb77  test    dword ptr [rbx+0Ch], 130010h
0x18005fb7e  lea     rdx, [rsp+48h+StringBinding]
0x18005fb83  mov     rax, [rbx]
0x18005fb86  jnz     loc_18005FC8C
0x18005fb8c  mov     rax, [rax+170h]
0x18005fb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb98  test    eax, eax
0x18005fb9a  jnz     short loc_18005FB24
0x18005fb9c  mov     rcx, [rsp+48h+StringBinding]; StringBinding
0x18005fba1  lea     r8, [rsp+48h+Protseq]; Protseq
0x18005fba6  mov     [rsp+48h+NetworkOptions], 0; NetworkOptions
0x18005fbaf  xor     r9d, r9d; NetworkAddr
0x18005fbb2  xor     edx, edx; ObjUuid
0x18005fbb4  mov     [rsp+48h+Endpoint], 0; Endpoint
0x18005fbbd  call    RpcStringBindingParseW
0x18005fbc2  cmp     cs:?RpcHasBeenInitialized@@3HA, 0; int RpcHasBeenInitialized
0x18005fbc9  mov     ebx, eax
0x18005fbcb  jz      loc_18005FC5D
0x18005fbd1  mov     rcx, [rsp+48h+StringBinding]; lpMem
0x18005fbd6  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005fbdb  mov     [rsp+48h+StringBinding], 0
0x18005fbe4  test    ebx, ebx
0x18005fbe6  jnz     loc_18005FC98
0x18005fbec  lea     ecx, [rbx+3]; unsigned int
0x18005fbef  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x18005fbf4  mov     rsi, [rsp+48h+Protseq]
0x18005fbf9  test    eax, eax
0x18005fbfb  jnz     short loc_18005FC38
0x18005fbfd  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x18005fc04  jz      short loc_18005FC38
0x18005fc06  mov     rbx, [r14+28h]
0x18005fc0a  add     rbx, 4
0x18005fc0e  call    cs:__imp_GetCurrentProcessId
0x18005fc14  mov     edi, eax
0x18005fc16  call    cs:__imp_GetCommandLineW
0x18005fc1c  mov     [rsp+48h+NetworkOptions], rbx
0x18005fc21  lea     rdx, RPC_EVENTLOG_ASYNC_HWND_USE_ERR
0x18005fc28  mov     r8, rax
0x18005fc2b  mov     [rsp+48h+Endpoint], rsi
0x18005fc30  mov     r9d, edi
0x18005fc33  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x18005fc38  cmp     cs:?RpcHasBeenInitialized@@3HA, 0; int RpcHasBeenInitialized
0x18005fc3f  jz      short loc_18005FC6F
0x18005fc41  mov     rcx, rsi; lpMem
0x18005fc44  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005fc49  mov     eax, 6E4h
0x18005fc4e  jmp     loc_18005FB24
0x18005fc53  mov     eax, 6A6h
0x18005fc58  jmp     loc_18005FB24
0x18005fc5d  call    ?PerformRpcInitialization@@YAJXZ; PerformRpcInitialization(void)
0x18005fc62  test    eax, eax
0x18005fc64  jnz     loc_18005FBE4
0x18005fc6a  jmp     loc_18005FBD1
0x18005fc6f  call    ?PerformRpcInitialization@@YAJXZ; PerformRpcInitialization(void)
0x18005fc74  test    eax, eax
0x18005fc76  jnz     short loc_18005FC49
0x18005fc78  jmp     short loc_18005FC41
0x18005fc7a  call    ?PerformRpcInitialization@@YAJXZ; PerformRpcInitialization(void)
0x18005fc7f  test    eax, eax
0x18005fc81  jnz     loc_18005FB24
0x18005fc87  jmp     loc_18005FB62
0x18005fc8c  mov     rax, [rax+0B0h]
0x18005fc93  jmp     loc_18005FB93
0x18005fc98  mov     eax, ebx
0x18005fc9a  jmp     loc_18005FB24
```

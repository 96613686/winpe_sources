# LOG_PIPE_SERVER::PipeConnected(void)

- ea: `0x180005360`
- end: `0x180005408`
- name: `?PipeConnected@LOG_PIPE_SERVER@@UEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(LOG_PIPE_SERVER *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005360`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000537b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000537b`
- `iisutil!?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@KPEAX@Z` at `0x1800053a9`
- `iisutil!?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@KPEAX@Z` at `0x1800053a9`
- `iisutil!PuDbgPrint` at `0x1800053e9`
- `iisutil!PuDbgPrint` at `0x1800053e9`

## string_xrefs

- `0x1800053d7`: `LOG_PIPE_SERVER::PipeConnected WriteMessage handshake failed hr=0x%08X\n`
- `0x1800053d0`: `servercommon\inetsrv\iis\iisrearc\iis70\httplog\logpipeserver.cxx`

## pseudocode

```c
__int64 __fastcall LOG_PIPE_SERVER::PipeConnected(LOG_PIPE_SERVER *this)
{
  DWORD CurrentProcessId; // eax
  __int64 v3; // rcx
  int v4; // eax
  unsigned int v5; // esi
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v7 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v3 = *((_QWORD *)this + 2);
  v7 = CurrentProcessId | 0x100000000LL;
  v4 = IPM2_MESSAGE_PIPE::WriteMessage(v3, 1, 8, &v7);
  v5 = v4;
  if ( v4 >= 0 )
  {
    _InterlockedExchange((volatile __int32 *)this + 20, 1);
    return 0;
  }
  else
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\httplog\\logpipeserver.cxx",
        361,
        "LOG_PIPE_SERVER::PipeConnected",
        "LOG_PIPE_SERVER::PipeConnected WriteMessage handshake failed hr=0x%08X\n",
        v4);
    return v5;
  }
}

```

## disassembly

```asm
0x180005360  mov     [rsp+arg_8], rbx
0x180005365  mov     [rsp+arg_10], rsi
0x18000536a  push    rdi
0x18000536b  sub     rsp, 30h
0x18000536f  mov     rbx, rcx
0x180005372  mov     [rsp+38h+arg_0], 0
0x18000537b  call    cs:__imp_GetCurrentProcessId
0x180005381  mov     edi, 1
0x180005386  mov     eax, eax
0x180005388  mov     rcx, 100000000h
0x180005392  lea     r9, [rsp+38h+arg_0]
0x180005397  or      rax, rcx
0x18000539a  mov     edx, edi
0x18000539c  mov     rcx, [rbx+10h]
0x1800053a0  lea     r8d, [rdi+7]
0x1800053a4  mov     [rsp+38h+arg_0], rax
0x1800053a9  call    cs:__imp_?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@KPEAX@Z; IPM2_MESSAGE_PIPE::WriteMessage(IPM2_OPCODE,ulong,void *)
0x1800053af  mov     esi, eax
0x1800053b1  test    eax, eax
0x1800053b3  jns     short loc_1800053F3
0x1800053b5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800053bc  jz      short loc_1800053EF
0x1800053be  mov     rcx, cs:g_pDebug
0x1800053c5  lea     r9, aLogPipeServerP_0; "LOG_PIPE_SERVER::PipeConnected"
0x1800053cc  mov     [rsp+38h+var_10], eax
0x1800053d0  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800053d7  lea     rax, aLogPipeServerP; "LOG_PIPE_SERVER::PipeConnected WriteMes"...
0x1800053de  mov     r8d, 169h
0x1800053e4  mov     [rsp+38h+var_18], rax
0x1800053e9  call    cs:__imp_PuDbgPrint
0x1800053ef  mov     eax, esi
0x1800053f1  jmp     short loc_1800053F8
0x1800053f3  xchg    edi, [rbx+50h]
0x1800053f6  xor     eax, eax
0x1800053f8  mov     rbx, [rsp+38h+arg_8]
0x1800053fd  mov     rsi, [rsp+38h+arg_10]
0x180005402  add     rsp, 30h
0x180005406  pop     rdi
0x180005407  retn
```

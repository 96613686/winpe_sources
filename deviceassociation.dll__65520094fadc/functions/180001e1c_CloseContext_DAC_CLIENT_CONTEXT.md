# CloseContext(_DAC_CLIENT_CONTEXT *)

- ea: `0x180001e1c`
- end: `0x180002161`
- name: `?CloseContext@@YAJPEAU_DAC_CLIENT_CONTEXT@@@Z`
- size: `837`
- prototype: `__int64 __fastcall(struct _DAC_CLIENT_CONTEXT *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800087f0`
- `0x180008b40`
- `0x1800099a0`
- `0x18000a3d0`
- `0x18000ada0`

## callees

- `0x180001e1c`
- `0x180002ca4`
- `0x180002e58`
- `0x180002f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001ec3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001ec3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e82`
- `RPCRT4!RpcAsyncCancelCall` at `0x180001ed7`
- `RPCRT4!RpcAsyncCancelCall` at `0x180001ed7`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000bfe4`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000c000`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000bfe4`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000c000`
- `RPCRT4!NdrClientCall3` at `0x180001f90`
- `RPCRT4!NdrClientCall3` at `0x180001fbb`
- `RPCRT4!NdrClientCall3` at `0x180001fe3`
- `RPCRT4!NdrClientCall3` at `0x18000200b`
- `RPCRT4!NdrClientCall3` at `0x180001f90`
- `RPCRT4!NdrClientCall3` at `0x180001fbb`
- `RPCRT4!NdrClientCall3` at `0x180001fe3`
- `RPCRT4!NdrClientCall3` at `0x18000200b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180002068`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800020a9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180002068`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800020a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180002056`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180002097`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180002056`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180002097`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180002075`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800020b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180002075`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800020b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001ea1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001ea1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002112`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002112`

## pseudocode

```c
__int64 __fastcall CloseContext(struct _DAC_CLIENT_CONTEXT *a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  unsigned int Pointer; // eax
  struct _TP_WAIT *v5; // rcx
  struct _TP_WAIT *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
  if ( !a1 || *((_WORD *)a1 + 4) != 3503 )
    return (unsigned int)-2147024809;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
  *((_DWORD *)a1 + 20) = 0;
  if ( *((_DWORD *)a1 + 16) )
  {
    *((_QWORD *)a1 + 11) = 0;
    if ( !GetModuleHandleExW(4u, (LPCWSTR)DafCloseImportExportContext, (HMODULE *)a1 + 11) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
      return v3;
    }
    RpcAsyncCancelCall(*((PRPC_ASYNC_STATE *)a1 + 9), 1);
    *((_DWORD *)a1 + 16) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
  if ( *((_DWORD *)a1 + 24) == 1 || *((_DWORD *)a1 + 24) == 2 || *((_DWORD *)a1 + 24) == 3 )
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo,
                              0xAu,
                              0,
                              (char *)a1 + 56).Pointer;
  }
  else if ( *((_DWORD *)a1 + 24) == 4 )
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&DevicePresenceChallenge_ProxyInfo,
                              2u,
                              0,
                              (char *)a1 + 56).Pointer;
  }
  else
  {
    if ( *((_DWORD *)a1 + 24) != 5 )
    {
      if ( *((_DWORD *)a1 + 24) == 6 )
      {
        v3 = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&Inbound_ProxyInfo, 3u, 0, (char *)a1 + 56).Pointer;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35);
        v3 = -2147467259;
      }
      goto LABEL_27;
    }
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo,
                              0xFu,
                              0,
                              (char *)a1 + 56).Pointer;
  }
  v3 = Pointer;
LABEL_27:
  if ( (v3 & 0x80000000) == 0 )
  {
    v5 = (struct _TP_WAIT *)*((_QWORD *)a1 + 20);
    if ( v5 )
    {
      SetThreadpoolWait(v5, 0, 0);
      WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)a1 + 20), 1);
      CloseThreadpoolWait(*((PTP_WAIT *)a1 + 20));
      *((_QWORD *)a1 + 20) = 0;
    }
    v6 = (struct _TP_WAIT *)*((_QWORD *)a1 + 18);
    if ( v6 )
    {
      SetThreadpoolWait(v6, 0, 0);
      WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)a1 + 18), 1);
      CloseThreadpoolWait(*((PTP_WAIT *)a1 + 18));
      *((_QWORD *)a1 + 18) = 0;
    }
    v7 = (void *)*((_QWORD *)a1 + 19);
    if ( v7 )
    {
      if ( !CloseHandle(v7)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36);
      }
      *((_QWORD *)a1 + 19) = 0;
    }
    v8 = (void *)*((_QWORD *)a1 + 17);
    if ( v8 )
    {
      if ( !CloseHandle(v8)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37);
      }
      *((_QWORD *)a1 + 17) = 0;
    }
    ReleaseClientContext(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x180001e1c  mov     [rsp+arg_0], rcx
0x180001e21  push    rbx
0x180001e22  push    rdi
0x180001e23  push    r14
0x180001e25  push    r15
0x180001e27  sub     rsp, 38h
0x180001e2b  mov     rdi, rcx
0x180001e2e  lea     r15, WPP_GLOBAL_Control
0x180001e35  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e3c  cmp     rcx, r15
0x180001e3f  jz      short loc_180001E5C
0x180001e41  cmp     byte ptr [rcx+19h], 4
0x180001e45  jb      short loc_180001E5C
0x180001e47  mov     edx, 22h ; '"'
0x180001e4c  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180001e53  mov     rcx, [rcx+10h]
0x180001e57  call    WPP_SF_s
0x180001e5c  test    rdi, rdi
0x180001e5f  jz      loc_18000214F
0x180001e65  mov     eax, 0DAFh
0x180001e6a  cmp     [rdi+8], ax
0x180001e6e  jnz     loc_18000214F
0x180001e74  xor     ebx, ebx
0x180001e76  lea     r14, [rdi+10h]
0x180001e7a  mov     [rsp+58h+arg_8], r14
0x180001e7f  mov     rcx, r14; lpCriticalSection
0x180001e82  call    cs:__imp_EnterCriticalSection
0x180001e88  mov     [rdi+50h], ebx
0x180001e8b  cmp     [rdi+40h], ebx
0x180001e8e  jz      short loc_180001F07
0x180001e90  lea     r8, [rdi+58h]; phModule
0x180001e94  mov     [r8], rbx
0x180001e97  lea     rdx, DafCloseImportExportContext; lpModuleName
0x180001e9e  lea     ecx, [rbx+4]; dwFlags
0x180001ea1  call    cs:__imp_GetModuleHandleExW
0x180001ea7  test    eax, eax
0x180001ea9  jnz     short loc_180001ECE
0x180001eab  call    cs:__imp_GetLastError
0x180001eb1  mov     ebx, eax
0x180001eb3  test    eax, eax
0x180001eb5  jle     short loc_180001EC0
0x180001eb7  movzx   ebx, ax
0x180001eba  or      ebx, 80070000h
0x180001ec0  mov     rcx, r14; lpCriticalSection
0x180001ec3  call    cs:__imp_LeaveCriticalSection
0x180001ec9  jmp     loc_180002154
0x180001ece  mov     edx, 1; fAbort
0x180001ed3  mov     rcx, [rdi+48h]; pAsync
0x180001ed7  call    cs:__imp_RpcAsyncCancelCall
0x180001edd  mov     dword ptr [rdi+40h], 0
0x180001ee4  jmp     short loc_180001F07
0x180001ee6  mov     ebx, eax
0x180001ee8  cmp     eax, 1
0x180001eeb  jl      short loc_180001EF6
0x180001eed  movzx   ebx, ax
0x180001ef0  or      ebx, 80010000h
0x180001ef6  lea     r15, WPP_GLOBAL_Control
0x180001efd  mov     rdi, [rsp+58h+arg_0]
0x180001f02  mov     r14, [rsp+58h+arg_8]
0x180001f07  mov     rcx, r14; lpCriticalSection
0x180001f0a  call    cs:__imp_LeaveCriticalSection
0x180001f10  test    ebx, ebx
0x180001f12  jnz     loc_180002154
0x180001f18  mov     ecx, [rdi+60h]
0x180001f1b  sub     ecx, 1
0x180001f1e  jz      loc_180001FF0
0x180001f24  sub     ecx, 1
0x180001f27  jz      loc_180001FF0
0x180001f2d  sub     ecx, 1
0x180001f30  jz      loc_180001FF0
0x180001f36  sub     ecx, 1
0x180001f39  jz      loc_180001FC8
0x180001f3f  sub     ecx, 1
0x180001f42  jz      short loc_180001FA0
0x180001f44  cmp     ecx, 1
0x180001f47  jz      short loc_180001F75
0x180001f49  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f50  cmp     rcx, r15
0x180001f53  jz      short loc_180001F67
0x180001f55  cmp     byte ptr [rcx+19h], 2
0x180001f59  jb      short loc_180001F67
0x180001f5b  lea     edx, [rbx+23h]
0x180001f5e  mov     rcx, [rcx+10h]
0x180001f62  call    WPP_SF_
0x180001f67  mov     ebx, 80004005h
0x180001f6c  mov     [rsp+58h+var_38], ebx
0x180001f70  jmp     loc_18000201C
0x180001f75  mov     [rsp+58h+arg_8], 0
0x180001f7e  lea     r9, [rdi+38h]
0x180001f82  xor     r8d, r8d; pReturnValue
0x180001f85  lea     edx, [r8+3]; nProcNum
0x180001f89  lea     rcx, ?Inbound_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180001f90  call    cs:__imp_NdrClientCall3
0x180001f96  mov     rbx, rax
0x180001f99  mov     [rsp+58h+arg_8], rax
0x180001f9e  jmp     short loc_180002018
0x180001fa0  mov     [rsp+58h+arg_10], 0
0x180001fa9  lea     r9, [rdi+38h]
0x180001fad  xor     r8d, r8d; pReturnValue
0x180001fb0  lea     edx, [r8+0Fh]; nProcNum
0x180001fb4  lea     rcx, ?DeviceAssociation_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180001fbb  call    cs:__imp_NdrClientCall3
0x180001fc1  mov     [rsp+58h+arg_10], rax
0x180001fc6  jmp     short loc_180002016
0x180001fc8  mov     [rsp+58h+arg_18], 0
0x180001fd1  lea     r9, [rdi+38h]
0x180001fd5  xor     r8d, r8d; pReturnValue
0x180001fd8  lea     edx, [r8+2]; nProcNum
0x180001fdc  lea     rcx, ?DevicePresenceChallenge_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180001fe3  call    cs:__imp_NdrClientCall3
0x180001fe9  mov     [rsp+58h+arg_18], rax
0x180001fee  jmp     short loc_180002016
0x180001ff0  mov     [rsp+58h+var_30], 0
0x180001ff9  lea     r9, [rdi+38h]
0x180001ffd  xor     r8d, r8d; pReturnValue
0x180002000  lea     edx, [r8+0Ah]; nProcNum
0x180002004  lea     rcx, ?DeviceAssociation_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000200b  call    cs:__imp_NdrClientCall3
0x180002011  mov     [rsp+58h+var_30], rax
0x180002016  mov     ebx, eax
0x180002018  mov     [rsp+58h+var_38], eax
0x18000201c  jmp     short loc_18000203D
0x18000201e  cmp     eax, 1
0x180002021  jl      short loc_18000202B
0x180002023  movzx   eax, ax
0x180002026  or      eax, 80010000h
0x18000202b  mov     ebx, eax
0x18000202d  mov     [rsp+58h+var_38], eax
0x180002031  lea     r15, WPP_GLOBAL_Control
0x180002038  mov     rdi, [rsp+58h+arg_0]
0x18000203d  test    ebx, ebx
0x18000203f  js      loc_180002154
0x180002045  mov     rcx, [rdi+0A0h]; pwa
0x18000204c  test    rcx, rcx
0x18000204f  jz      short loc_180002086
0x180002051  xor     r8d, r8d; pftTimeout
0x180002054  xor     edx, edx; h
0x180002056  call    cs:__imp_SetThreadpoolWait
0x18000205c  mov     edx, 1; fCancelPendingCallbacks
0x180002061  mov     rcx, [rdi+0A0h]; pwa
0x180002068  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000206e  mov     rcx, [rdi+0A0h]; pwa
0x180002075  call    cs:__imp_CloseThreadpoolWait
0x18000207b  mov     qword ptr [rdi+0A0h], 0
0x180002086  mov     rcx, [rdi+90h]; pwa
0x18000208d  test    rcx, rcx
0x180002090  jz      short loc_1800020C7
0x180002092  xor     r8d, r8d; pftTimeout
0x180002095  xor     edx, edx; h
0x180002097  call    cs:__imp_SetThreadpoolWait
0x18000209d  mov     edx, 1; fCancelPendingCallbacks
0x1800020a2  mov     rcx, [rdi+90h]; pwa
0x1800020a9  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800020af  mov     rcx, [rdi+90h]; pwa
0x1800020b6  call    cs:__imp_CloseThreadpoolWait
0x1800020bc  mov     qword ptr [rdi+90h], 0
0x1800020c7  mov     rcx, [rdi+98h]; hObject
0x1800020ce  test    rcx, rcx
0x1800020d1  jz      short loc_180002106
0x1800020d3  call    cs:__imp_CloseHandle
0x1800020d9  test    eax, eax
0x1800020db  jnz     short loc_1800020FB
0x1800020dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020e4  cmp     rcx, r15
0x1800020e7  jz      short loc_1800020FB
0x1800020e9  cmp     byte ptr [rcx+19h], 2
0x1800020ed  jb      short loc_1800020FB
0x1800020ef  lea     edx, [rax+24h]
0x1800020f2  mov     rcx, [rcx+10h]
0x1800020f6  call    WPP_SF_
0x1800020fb  mov     qword ptr [rdi+98h], 0
0x180002106  mov     rcx, [rdi+88h]; hObject
0x18000210d  test    rcx, rcx
0x180002110  jz      short loc_180002145
0x180002112  call    cs:__imp_CloseHandle
0x180002118  test    eax, eax
0x18000211a  jnz     short loc_18000213A
0x18000211c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002123  cmp     rcx, r15
0x180002126  jz      short loc_18000213A
0x180002128  cmp     byte ptr [rcx+19h], 2
0x18000212c  jb      short loc_18000213A
0x18000212e  lea     edx, [rax+25h]
0x180002131  mov     rcx, [rcx+10h]
0x180002135  call    WPP_SF_
0x18000213a  mov     qword ptr [rdi+88h], 0
0x180002145  mov     rcx, rdi; struct _DAC_CLIENT_CONTEXT *
0x180002148  call    ?ReleaseClientContext@@YAKPEAU_DAC_CLIENT_CONTEXT@@@Z; ReleaseClientContext(_DAC_CLIENT_CONTEXT *)
0x18000214d  jmp     short loc_180002154
0x18000214f  mov     ebx, 80070057h
0x180002154  mov     eax, ebx
0x180002156  add     rsp, 38h
0x18000215a  pop     r15
0x18000215c  pop     r14
0x18000215e  pop     rdi
0x18000215f  pop     rbx
0x180002160  retn
0x18000bfd6  push    rbp
0x18000bfd8  sub     rsp, 20h
0x18000bfdc  mov     rbp, rdx
0x18000bfdf  mov     rcx, [rcx]
0x18000bfe2  mov     ecx, [rcx]; ExceptionCode
0x18000bfe4  call    cs:__imp_I_RpcExceptionFilter
0x18000bfea  nop
0x18000bfeb  add     rsp, 20h
0x18000bfef  pop     rbp
0x18000bff0  retn
0x18000bff2  push    rbp
0x18000bff4  sub     rsp, 20h
0x18000bff8  mov     rbp, rdx
0x18000bffb  mov     rcx, [rcx]
0x18000bffe  mov     ecx, [rcx]; ExceptionCode
0x18000c000  call    cs:__imp_I_RpcExceptionFilter
0x18000c006  nop
0x18000c007  add     rsp, 20h
0x18000c00b  pop     rbp
0x18000c00c  retn
```

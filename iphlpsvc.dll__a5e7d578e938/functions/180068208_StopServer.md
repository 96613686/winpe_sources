# StopServer

- ea: `0x180068208`
- end: `0x1800683d1`
- name: `StopServer`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180042af8`

## callees

- `0x180004c64`
- `0x18000a704`
- `0x18004901c`
- `0x18004b5f0`
- `0x180068208`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180068268`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180068268`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800682f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800682f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068334`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068278`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068278`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180068241`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180068241`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800683a7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800683a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006834f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006836a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006834f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006836a`
- `HTTPAPI!HttpCloseRequestQueue` at `0x180068251`
- `HTTPAPI!HttpCloseRequestQueue` at `0x180068251`
- `HTTPAPI!HttpCloseUrlGroup` at `0x180068288`
- `HTTPAPI!HttpCloseUrlGroup` at `0x180068288`
- `HTTPAPI!HttpCloseServerSession` at `0x180068298`
- `HTTPAPI!HttpCloseServerSession` at `0x180068298`
- `HTTPAPI!HttpTerminate` at `0x1800682a9`
- `HTTPAPI!HttpTerminate` at `0x1800682a9`

## pseudocode

```c
void __fastcall StopServer(__int64 a1)
{
  bool v2; // bl
  _QWORD *v3; // rbx
  _QWORD *v4; // rcx
  __int64 v5; // r8
  _BYTE v6[16]; // [rsp+30h] [rbp-28h] BYREF

  v2 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 80)) == 1;
  CancelIoEx(*(HANDLE *)(a1 + 72), 0);
  HttpCloseRequestQueue(*(HANDLE *)(a1 + 72));
  if ( !v2 )
    WaitForSingleObject(*(HANDLE *)(a1 + 88), 0xFFFFFFFF);
  CloseHandle(*(HANDLE *)(a1 + 88));
  HttpCloseUrlGroup(*(_QWORD *)(a1 + 64));
  HttpCloseServerSession(*(_QWORD *)(a1 + 56));
  HttpTerminate(1u, 0);
  *(_DWORD *)(*(_QWORD *)(a1 + 288) + 1192LL) = 0;
  *(_DWORD *)(*(_QWORD *)(a1 + 288) + 1196LL) = 0;
  IpTlsStoreInterfacePersistentValues(*(const BYTE **)(a1 + 288), *(_DWORD *)(*(_QWORD *)(a1 + 288) + 1024LL), 12);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 240));
  v3 = *(_QWORD **)(a1 + 776);
  *(_DWORD *)(a1 + 368) |= 0x20u;
  *(_QWORD *)(a1 + 776) = 0;
  while ( v3 )
  {
    v4 = v3;
    v3 = (_QWORD *)*v3;
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 784));
    FREE(v4);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 240));
  SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 304), 0, 0, 0);
  SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 352), 0, 0, 0);
  if ( (Microsoft_Windows_IphlpsvcEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      MS_IPHLPSVC_EVENTS_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_IPHTTPS_SERVER_STOPPED,
      v5,
      1,
      v6);
  SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 360));
}

```

## disassembly

```asm
0x180068208  mov     [rsp+arg_8], rbx
0x18006820d  mov     [rsp+arg_10], rsi
0x180068212  push    rdi
0x180068213  sub     rsp, 50h
0x180068217  mov     rax, cs:__security_cookie
0x18006821e  xor     rax, rsp
0x180068221  mov     [rsp+58h+var_18], rax
0x180068226  xor     esi, esi
0x180068228  mov     rdi, rcx
0x18006822b  or      eax, 0FFFFFFFFh
0x18006822e  lock xadd [rcx+50h], eax
0x180068233  mov     rcx, [rcx+48h]; hFile
0x180068237  dec     eax
0x180068239  cmp     eax, 1
0x18006823c  setz    bl
0x18006823f  xor     edx, edx; lpOverlapped
0x180068241  call    cs:__imp_CancelIoEx
0x180068248  nop     dword ptr [rax+rax+00h]
0x18006824d  mov     rcx, [rdi+48h]; RequestQueueHandle
0x180068251  call    cs:__imp_HttpCloseRequestQueue
0x180068258  nop     dword ptr [rax+rax+00h]
0x18006825d  test    bl, bl
0x18006825f  jnz     short loc_180068274
0x180068261  mov     rcx, [rdi+58h]; hHandle
0x180068265  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180068268  call    cs:__imp_WaitForSingleObject
0x18006826f  nop     dword ptr [rax+rax+00h]
0x180068274  mov     rcx, [rdi+58h]; hObject
0x180068278  call    cs:__imp_CloseHandle
0x18006827f  nop     dword ptr [rax+rax+00h]
0x180068284  mov     rcx, [rdi+40h]; UrlGroupId
0x180068288  call    cs:__imp_HttpCloseUrlGroup
0x18006828f  nop     dword ptr [rax+rax+00h]
0x180068294  mov     rcx, [rdi+38h]; ServerSessionId
0x180068298  call    cs:__imp_HttpCloseServerSession
0x18006829f  nop     dword ptr [rax+rax+00h]
0x1800682a4  xor     edx, edx; pReserved
0x1800682a6  lea     ecx, [rdx+1]; Flags
0x1800682a9  call    cs:__imp_HttpTerminate
0x1800682b0  nop     dword ptr [rax+rax+00h]
0x1800682b5  mov     rax, [rdi+120h]
0x1800682bc  mov     [rax+4A8h], esi
0x1800682c2  mov     rax, [rdi+120h]
0x1800682c9  mov     [rax+4ACh], esi
0x1800682cf  or      si, 0Ch
0x1800682d3  mov     rcx, [rdi+120h]
0x1800682da  movzx   r8d, si
0x1800682de  mov     edx, [rcx+400h]
0x1800682e4  call    IpTlsStoreInterfacePersistentValues
0x1800682e9  lea     rsi, [rdi+0F0h]
0x1800682f0  mov     rcx, rsi; lpCriticalSection
0x1800682f3  call    cs:__imp_EnterCriticalSection
0x1800682fa  nop     dword ptr [rax+rax+00h]
0x1800682ff  mov     rbx, [rdi+308h]
0x180068306  or      dword ptr [rdi+170h], 20h
0x18006830d  mov     qword ptr [rdi+308h], 0
0x180068318  jmp     short loc_18006832C
0x18006831a  mov     rcx, rbx
0x18006831d  mov     rbx, [rbx]
0x180068320  lock dec dword ptr [rdi+310h]
0x180068327  call    FREE
0x18006832c  test    rbx, rbx
0x18006832f  jnz     short loc_18006831A
0x180068331  mov     rcx, rsi; lpCriticalSection
0x180068334  call    cs:__imp_LeaveCriticalSection
0x18006833b  nop     dword ptr [rax+rax+00h]
0x180068340  mov     rcx, [rdi+130h]; pti
0x180068347  xor     r9d, r9d; msWindowLength
0x18006834a  xor     r8d, r8d; msPeriod
0x18006834d  xor     edx, edx; pftDueTime
0x18006834f  call    cs:__imp_SetThreadpoolTimer
0x180068356  nop     dword ptr [rax+rax+00h]
0x18006835b  mov     rcx, [rdi+160h]; pti
0x180068362  xor     r9d, r9d; msWindowLength
0x180068365  xor     r8d, r8d; msPeriod
0x180068368  xor     edx, edx; pftDueTime
0x18006836a  call    cs:__imp_SetThreadpoolTimer
0x180068371  nop     dword ptr [rax+rax+00h]
0x180068376  test    cs:Microsoft_Windows_IphlpsvcEnableBits, 1
0x18006837d  jz      short loc_1800683A0
0x18006837f  lea     rax, [rsp+58h+var_28]
0x180068384  lea     r9d, [rbx+1]
0x180068388  mov     [rsp+58h+var_38], rax
0x18006838d  lea     rdx, EVENT_IPHLPSVC_IPHTTPS_SERVER_STOPPED
0x180068394  lea     rcx, MS_IPHLPSVC_EVENTS_PROVIDER_ID_Context
0x18006839b  call    McGenEventWrite_EventWriteTransfer
0x1800683a0  mov     rcx, [rdi+168h]; pwk
0x1800683a7  call    cs:__imp_SubmitThreadpoolWork
0x1800683ae  nop     dword ptr [rax+rax+00h]
0x1800683b3  mov     rcx, [rsp+58h+var_18]
0x1800683b8  xor     rcx, rsp; StackCookie
0x1800683bb  call    __security_check_cookie
0x1800683c0  mov     rbx, [rsp+58h+arg_8]
0x1800683c5  mov     rsi, [rsp+58h+arg_10]
0x1800683ca  add     rsp, 50h
0x1800683ce  pop     rdi
0x1800683cf  retn
```

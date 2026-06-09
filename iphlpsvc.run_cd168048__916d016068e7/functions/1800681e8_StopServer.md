# StopServer

- ea: `0x1800681e8`
- end: `0x1800683b1`
- name: `StopServer`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180042b38`

## callees

- `0x180004c54`
- `0x18000a6f4`
- `0x18004905c`
- `0x18004b630`
- `0x1800681e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180068248`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180068248`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800682d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800682d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068314`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068314`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068258`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068258`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180068221`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180068221`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180068387`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180068387`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006832f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006834a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006832f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006834a`
- `HTTPAPI!HttpCloseRequestQueue` at `0x180068231`
- `HTTPAPI!HttpCloseRequestQueue` at `0x180068231`
- `HTTPAPI!HttpCloseUrlGroup` at `0x180068268`
- `HTTPAPI!HttpCloseUrlGroup` at `0x180068268`
- `HTTPAPI!HttpCloseServerSession` at `0x180068278`
- `HTTPAPI!HttpCloseServerSession` at `0x180068278`
- `HTTPAPI!HttpTerminate` at `0x180068289`
- `HTTPAPI!HttpTerminate` at `0x180068289`

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
0x1800681e8  mov     [rsp+arg_8], rbx
0x1800681ed  mov     [rsp+arg_10], rsi
0x1800681f2  push    rdi
0x1800681f3  sub     rsp, 50h
0x1800681f7  mov     rax, cs:__security_cookie
0x1800681fe  xor     rax, rsp
0x180068201  mov     [rsp+58h+var_18], rax
0x180068206  xor     esi, esi
0x180068208  mov     rdi, rcx
0x18006820b  or      eax, 0FFFFFFFFh
0x18006820e  lock xadd [rcx+50h], eax
0x180068213  mov     rcx, [rcx+48h]; hFile
0x180068217  dec     eax
0x180068219  cmp     eax, 1
0x18006821c  setz    bl
0x18006821f  xor     edx, edx; lpOverlapped
0x180068221  call    cs:__imp_CancelIoEx
0x180068228  nop     dword ptr [rax+rax+00h]
0x18006822d  mov     rcx, [rdi+48h]; RequestQueueHandle
0x180068231  call    cs:__imp_HttpCloseRequestQueue
0x180068238  nop     dword ptr [rax+rax+00h]
0x18006823d  test    bl, bl
0x18006823f  jnz     short loc_180068254
0x180068241  mov     rcx, [rdi+58h]; hHandle
0x180068245  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180068248  call    cs:__imp_WaitForSingleObject
0x18006824f  nop     dword ptr [rax+rax+00h]
0x180068254  mov     rcx, [rdi+58h]; hObject
0x180068258  call    cs:__imp_CloseHandle
0x18006825f  nop     dword ptr [rax+rax+00h]
0x180068264  mov     rcx, [rdi+40h]; UrlGroupId
0x180068268  call    cs:__imp_HttpCloseUrlGroup
0x18006826f  nop     dword ptr [rax+rax+00h]
0x180068274  mov     rcx, [rdi+38h]; ServerSessionId
0x180068278  call    cs:__imp_HttpCloseServerSession
0x18006827f  nop     dword ptr [rax+rax+00h]
0x180068284  xor     edx, edx; pReserved
0x180068286  lea     ecx, [rdx+1]; Flags
0x180068289  call    cs:__imp_HttpTerminate
0x180068290  nop     dword ptr [rax+rax+00h]
0x180068295  mov     rax, [rdi+120h]
0x18006829c  mov     [rax+4A8h], esi
0x1800682a2  mov     rax, [rdi+120h]
0x1800682a9  mov     [rax+4ACh], esi
0x1800682af  or      si, 0Ch
0x1800682b3  mov     rcx, [rdi+120h]
0x1800682ba  movzx   r8d, si
0x1800682be  mov     edx, [rcx+400h]
0x1800682c4  call    IpTlsStoreInterfacePersistentValues
0x1800682c9  lea     rsi, [rdi+0F0h]
0x1800682d0  mov     rcx, rsi; lpCriticalSection
0x1800682d3  call    cs:__imp_EnterCriticalSection
0x1800682da  nop     dword ptr [rax+rax+00h]
0x1800682df  mov     rbx, [rdi+308h]
0x1800682e6  or      dword ptr [rdi+170h], 20h
0x1800682ed  mov     qword ptr [rdi+308h], 0
0x1800682f8  jmp     short loc_18006830C
0x1800682fa  mov     rcx, rbx
0x1800682fd  mov     rbx, [rbx]
0x180068300  lock dec dword ptr [rdi+310h]
0x180068307  call    FREE
0x18006830c  test    rbx, rbx
0x18006830f  jnz     short loc_1800682FA
0x180068311  mov     rcx, rsi; lpCriticalSection
0x180068314  call    cs:__imp_LeaveCriticalSection
0x18006831b  nop     dword ptr [rax+rax+00h]
0x180068320  mov     rcx, [rdi+130h]; pti
0x180068327  xor     r9d, r9d; msWindowLength
0x18006832a  xor     r8d, r8d; msPeriod
0x18006832d  xor     edx, edx; pftDueTime
0x18006832f  call    cs:__imp_SetThreadpoolTimer
0x180068336  nop     dword ptr [rax+rax+00h]
0x18006833b  mov     rcx, [rdi+160h]; pti
0x180068342  xor     r9d, r9d; msWindowLength
0x180068345  xor     r8d, r8d; msPeriod
0x180068348  xor     edx, edx; pftDueTime
0x18006834a  call    cs:__imp_SetThreadpoolTimer
0x180068351  nop     dword ptr [rax+rax+00h]
0x180068356  test    cs:Microsoft_Windows_IphlpsvcEnableBits, 1
0x18006835d  jz      short loc_180068380
0x18006835f  lea     rax, [rsp+58h+var_28]
0x180068364  lea     r9d, [rbx+1]
0x180068368  mov     [rsp+58h+var_38], rax
0x18006836d  lea     rdx, EVENT_IPHLPSVC_IPHTTPS_SERVER_STOPPED
0x180068374  lea     rcx, MS_IPHLPSVC_EVENTS_PROVIDER_ID_Context
0x18006837b  call    McGenEventWrite_EventWriteTransfer
0x180068380  mov     rcx, [rdi+168h]; pwk
0x180068387  call    cs:__imp_SubmitThreadpoolWork
0x18006838e  nop     dword ptr [rax+rax+00h]
0x180068393  mov     rcx, [rsp+58h+var_18]
0x180068398  xor     rcx, rsp; StackCookie
0x18006839b  call    __security_check_cookie
0x1800683a0  mov     rbx, [rsp+58h+arg_8]
0x1800683a5  mov     rsi, [rsp+58h+arg_10]
0x1800683aa  add     rsp, 50h
0x1800683ae  pop     rdi
0x1800683af  retn
```

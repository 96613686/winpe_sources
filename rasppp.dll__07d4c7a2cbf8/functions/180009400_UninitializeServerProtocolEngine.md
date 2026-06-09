# UninitializeServerProtocolEngine

- ea: `0x180009400`
- end: `0x18000954e`
- name: `UninitializeServerProtocolEngine`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180009400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000943f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009455`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000946b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000943f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009455`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000946b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094f2`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800094cb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800094cb`

## pseudocode

```c
void *UninitializeServerProtocolEngine()
{
  void *result; // rax
  HANDLE Handles[2]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v2; // [rsp+38h] [rbp-20h]

  if ( DDMInitialized )
  {
    *(_OWORD *)Handles = 0;
    v2 = 0;
    if ( !_InterlockedDecrement((_DWORD *)&g_AuthProv + 1) )
      SetEvent(*((HANDLE *)&g_AuthProv + 1));
    if ( !_InterlockedDecrement((_DWORD *)&g_AcctProv + 1) )
      SetEvent(*((HANDLE *)&g_AcctProv + 1));
    if ( !_InterlockedDecrement((volatile signed __int32 *)&g_DdmMsgHandler) )
      SetEvent(*((HANDLE *)&g_DdmMsgHandler + 1));
    Handles[0] = *((HANDLE *)&g_AuthProv + 1);
    Handles[1] = *((HANDLE *)&g_AcctProv + 1);
    v2 = *((_QWORD *)&g_DdmMsgHandler + 1);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
        L"PppDdmDeInit: waiting for auth-acct providers");
    WaitForMultipleObjects(3u, Handles, 1, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)&g_AuthProv + 1));
    CloseHandle(*((HANDLE *)&g_AcctProv + 1));
    CloseHandle(*((HANDLE *)&g_DdmMsgHandler + 1));
    g_AuthProv = 0;
    g_AcctProv = 0;
    g_DdmMsgHandler = 0;
    result = memset_0(&g_IpAddrMgmtFunctions, 0, 0xB0u);
    qword_18004CA60 = 0;
    DDMInitialized = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009400  sub     rsp, 58h
0x180009404  mov     rax, cs:__security_cookie
0x18000940b  xor     rax, rsp
0x18000940e  mov     [rsp+58h+var_18], rax
0x180009413  cmp     cs:DDMInitialized, 0
0x18000941a  jz      loc_18000953C
0x180009420  xor     eax, eax
0x180009422  xorps   xmm0, xmm0
0x180009425  movups  xmmword ptr [rsp+58h+Handles], xmm0
0x18000942a  mov     [rsp+58h+var_20], rax
0x18000942f  lock dec dword ptr cs:g_AuthProv+4
0x180009436  jnz     short loc_180009445
0x180009438  mov     rcx, qword ptr cs:g_AuthProv+8; hEvent
0x18000943f  call    cs:__imp_SetEvent
0x180009445  lock dec dword ptr cs:g_AcctProv+4
0x18000944c  jnz     short loc_18000945B
0x18000944e  mov     rcx, qword ptr cs:g_AcctProv+8; hEvent
0x180009455  call    cs:__imp_SetEvent
0x18000945b  lock dec dword ptr cs:g_DdmMsgHandler
0x180009462  jnz     short loc_180009471
0x180009464  mov     rcx, qword ptr cs:g_DdmMsgHandler+8; hEvent
0x18000946b  call    cs:__imp_SetEvent
0x180009471  test    cs:byte_18004CF34, 1
0x180009478  mov     rax, qword ptr cs:g_AuthProv+8
0x18000947f  mov     [rsp+58h+Handles], rax
0x180009484  mov     rax, qword ptr cs:g_AcctProv+8
0x18000948b  mov     [rsp+58h+Handles+8], rax
0x180009490  mov     rax, qword ptr cs:g_DdmMsgHandler+8
0x180009497  mov     [rsp+58h+var_20], rax
0x18000949c  jz      short loc_1800094B8
0x18000949e  lea     r8, aPppddmdeinitWa; "PppDdmDeInit: waiting for auth-acct pro"...
0x1800094a5  lea     rdx, RasPppTraceInfo
0x1800094ac  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800094b3  call    McTemplateU0z_EventWriteTransfer
0x1800094b8  mov     r8d, 1; bWaitAll
0x1800094be  lea     rdx, [rsp+58h+Handles]; lpHandles
0x1800094c3  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800094c7  lea     ecx, [r8+2]; nCount
0x1800094cb  call    cs:__imp_WaitForMultipleObjects
0x1800094d1  mov     rcx, qword ptr cs:g_AuthProv+8; hObject
0x1800094d8  call    cs:__imp_CloseHandle
0x1800094de  mov     rcx, qword ptr cs:g_AcctProv+8; hObject
0x1800094e5  call    cs:__imp_CloseHandle
0x1800094eb  mov     rcx, qword ptr cs:g_DdmMsgHandler+8; hObject
0x1800094f2  call    cs:__imp_CloseHandle
0x1800094f8  xorps   xmm0, xmm0
0x1800094fb  lea     rcx, g_IpAddrMgmtFunctions; void *
0x180009502  xorps   xmm1, xmm1
0x180009505  xor     edx, edx; Val
0x180009507  mov     r8d, 0B0h; Size
0x18000950d  movups  cs:g_AuthProv, xmm0
0x180009514  movups  cs:g_AcctProv, xmm1
0x18000951b  movups  cs:g_DdmMsgHandler, xmm0
0x180009522  call    memset_0
0x180009527  mov     cs:qword_18004CA60, 0
0x180009532  mov     cs:DDMInitialized, 0
0x18000953c  mov     rcx, [rsp+58h+var_18]
0x180009541  xor     rcx, rsp; StackCookie
0x180009544  call    __security_check_cookie
0x180009549  add     rsp, 58h
0x18000954d  retn
```

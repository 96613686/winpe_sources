# UninitializeServerProtocolEngine

- ea: `0x1800097a0`
- end: `0x180009919`
- name: `UninitializeServerProtocolEngine`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x1800097a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800097df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800097fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009817`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800097df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800097fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009817`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009890`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009890`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098b6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000987d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000987d`

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
    if ( (byte_18004DF34 & 1) != 0 )
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
    qword_18004DA60 = 0;
    DDMInitialized = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800097a0  sub     rsp, 58h
0x1800097a4  mov     rax, cs:__security_cookie
0x1800097ab  xor     rax, rsp
0x1800097ae  mov     [rsp+58h+var_18], rax
0x1800097b3  cmp     cs:DDMInitialized, 0
0x1800097ba  jz      loc_180009906
0x1800097c0  xor     eax, eax
0x1800097c2  xorps   xmm0, xmm0
0x1800097c5  movups  xmmword ptr [rsp+58h+Handles], xmm0
0x1800097ca  mov     [rsp+58h+var_20], rax
0x1800097cf  lock dec dword ptr cs:g_AuthProv+4
0x1800097d6  jnz     short loc_1800097EB
0x1800097d8  mov     rcx, qword ptr cs:g_AuthProv+8; hEvent
0x1800097df  call    cs:__imp_SetEvent
0x1800097e6  nop     dword ptr [rax+rax+00h]
0x1800097eb  lock dec dword ptr cs:g_AcctProv+4
0x1800097f2  jnz     short loc_180009807
0x1800097f4  mov     rcx, qword ptr cs:g_AcctProv+8; hEvent
0x1800097fb  call    cs:__imp_SetEvent
0x180009802  nop     dword ptr [rax+rax+00h]
0x180009807  lock dec dword ptr cs:g_DdmMsgHandler
0x18000980e  jnz     short loc_180009823
0x180009810  mov     rcx, qword ptr cs:g_DdmMsgHandler+8; hEvent
0x180009817  call    cs:__imp_SetEvent
0x18000981e  nop     dword ptr [rax+rax+00h]
0x180009823  test    cs:byte_18004DF34, 1
0x18000982a  mov     rax, qword ptr cs:g_AuthProv+8
0x180009831  mov     [rsp+58h+Handles], rax
0x180009836  mov     rax, qword ptr cs:g_AcctProv+8
0x18000983d  mov     [rsp+58h+Handles+8], rax
0x180009842  mov     rax, qword ptr cs:g_DdmMsgHandler+8
0x180009849  mov     [rsp+58h+var_20], rax
0x18000984e  jz      short loc_18000986A
0x180009850  lea     r8, aPppddmdeinitWa; "PppDdmDeInit: waiting for auth-acct pro"...
0x180009857  lea     rdx, RasPppTraceInfo
0x18000985e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009865  call    McTemplateU0z_EventWriteTransfer
0x18000986a  mov     r8d, 1; bWaitAll
0x180009870  lea     rdx, [rsp+58h+Handles]; lpHandles
0x180009875  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180009879  lea     ecx, [r8+2]; nCount
0x18000987d  call    cs:__imp_WaitForMultipleObjects
0x180009884  nop     dword ptr [rax+rax+00h]
0x180009889  mov     rcx, qword ptr cs:g_AuthProv+8; hObject
0x180009890  call    cs:__imp_CloseHandle
0x180009897  nop     dword ptr [rax+rax+00h]
0x18000989c  mov     rcx, qword ptr cs:g_AcctProv+8; hObject
0x1800098a3  call    cs:__imp_CloseHandle
0x1800098aa  nop     dword ptr [rax+rax+00h]
0x1800098af  mov     rcx, qword ptr cs:g_DdmMsgHandler+8; hObject
0x1800098b6  call    cs:__imp_CloseHandle
0x1800098bd  nop     dword ptr [rax+rax+00h]
0x1800098c2  xorps   xmm0, xmm0
0x1800098c5  lea     rcx, g_IpAddrMgmtFunctions; void *
0x1800098cc  xorps   xmm1, xmm1
0x1800098cf  xor     edx, edx; Val
0x1800098d1  mov     r8d, 0B0h; Size
0x1800098d7  movups  cs:g_AuthProv, xmm0
0x1800098de  movups  cs:g_AcctProv, xmm1
0x1800098e5  movups  cs:g_DdmMsgHandler, xmm0
0x1800098ec  call    memset_0
0x1800098f1  mov     cs:qword_18004DA60, 0
0x1800098fc  mov     cs:DDMInitialized, 0
0x180009906  mov     rcx, [rsp+58h+var_18]
0x18000990b  xor     rcx, rsp; StackCookie
0x18000990e  call    __security_check_cookie
0x180009913  add     rsp, 58h
0x180009917  retn
```

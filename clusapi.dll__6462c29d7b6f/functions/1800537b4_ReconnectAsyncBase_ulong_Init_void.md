# ReconnectAsyncBase<ulong>::Init(void)

- ea: `0x1800537b4`
- end: `0x180053863`
- name: `?Init@?$ReconnectAsyncBase@K@@QEAAKXZ`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180052d30`
- `0x180053274`

## callees

- `0x1800537b4`
- `0x18006f910`

## import_xrefs

- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800537cf`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800537cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800537fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800537fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005380b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005380b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053845`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053845`

## pseudocode

```c
__int64 __fastcall ReconnectAsyncBase<unsigned long>::Init(__int64 a1)
{
  RPC_STATUS v2; // eax
  DWORD LastError; // ebx
  HANDLE EventW; // rax

  v2 = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(a1 + 8), 0x70u);
  *(_QWORD *)(a1 + 32) = 0;
  LastError = v2;
  *(_DWORD *)(a1 + 52) = 1;
  *(_QWORD *)(a1 + 56) = -1;
  if ( v2 )
    goto LABEL_4;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 120) = EventW;
  if ( EventW )
  {
    *(_QWORD *)(a1 + 56) = EventW;
    return LastError;
  }
  LastError = GetLastError();
  TraceMsg(
    4u,
    7u,
    (__int64)L"ReconnectAsyncBase<unsigned long>::Init",
    183,
    L"Could not construct event when calling async rpc function posting %d",
    LastError);
  if ( LastError )
LABEL_4:
    CloseHandle(*(HANDLE *)(a1 + 120));
  return LastError;
}

```

## disassembly

```asm
0x1800537b4  mov     [rsp+arg_0], rbx
0x1800537b9  mov     [rsp+arg_8], rsi
0x1800537be  push    rdi
0x1800537bf  sub     rsp, 30h
0x1800537c3  mov     rsi, rcx
0x1800537c6  mov     edx, 70h ; 'p'; Size
0x1800537cb  add     rcx, 8; pAsync
0x1800537cf  call    cs:__imp_RpcAsyncInitializeHandle
0x1800537d5  mov     qword ptr [rsi+20h], 0
0x1800537dd  mov     ebx, eax
0x1800537df  mov     dword ptr [rsi+34h], 1
0x1800537e6  mov     qword ptr [rsi+38h], 0FFFFFFFFFFFFFFFFh
0x1800537ee  test    eax, eax
0x1800537f0  jnz     short loc_180053841
0x1800537f2  xor     r9d, r9d; lpName
0x1800537f5  xor     r8d, r8d; bInitialState
0x1800537f8  xor     edx, edx; bManualReset
0x1800537fa  xor     ecx, ecx; lpEventAttributes
0x1800537fc  call    cs:__imp_CreateEventW
0x180053802  mov     [rsi+78h], rax
0x180053806  test    rax, rax
0x180053809  jnz     short loc_18005385D
0x18005380b  call    cs:__imp_GetLastError
0x180053811  mov     [rsp+38h+var_10], eax
0x180053815  mov     edx, 7
0x18005381a  mov     ebx, eax
0x18005381c  lea     r8, aReconnectasync_0; "ReconnectAsyncBase<unsigned long>::Init"
0x180053823  lea     rax, aCouldNotConstr_1; "Could not construct event when calling "...
0x18005382a  mov     r9d, 0B7h
0x180053830  mov     [rsp+38h+var_18], rax
0x180053835  lea     ecx, [rdx-3]
0x180053838  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005383d  test    ebx, ebx
0x18005383f  jz      short loc_18005384B
0x180053841  mov     rcx, [rsi+78h]; hObject
0x180053845  call    cs:__imp_CloseHandle
0x18005384b  mov     rsi, [rsp+38h+arg_8]
0x180053850  mov     eax, ebx
0x180053852  mov     rbx, [rsp+38h+arg_0]
0x180053857  add     rsp, 30h
0x18005385b  pop     rdi
0x18005385c  retn
0x18005385d  mov     [rsi+38h], rax
0x180053861  jmp     short loc_18005384B
```

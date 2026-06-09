# BackgroundThreadStartup(void)

- ea: `0x1800c6d8c`
- end: `0x1800c6e51`
- name: `?BackgroundThreadStartup@@YAHXZ`
- size: `197`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800e2458`
- `0x1801029b0`

## callees

- `0x1800c6d8c`
- `0x1800c6e58`
- `0x1800e58c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c6ddd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c6ddd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6dfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6dfe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c6da2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c6dc2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c6da2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c6dc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6e43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6e43`

## pseudocode

```c
__int64 BackgroundThreadStartup(void)
{
  HANDLE EventW; // rbx
  HANDLE v1; // rdi
  unsigned __int64 v2; // rdx
  struct _SECURITY_ATTRIBUTES *v3; // rcx
  unsigned int (*v4)(void *); // r8
  void *v5; // r9
  unsigned int v7; // [rsp+20h] [rbp-18h]
  unsigned int *v8; // [rsp+28h] [rbp-10h]

  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
    goto LABEL_4;
  v1 = CreateEventW(0, 1, 0, 0);
  if ( !v1 )
  {
    CloseHandle(EventW);
    goto LABEL_4;
  }
  EnterCriticalSection(&BackgroundThreadCriticalSection::critSec);
  Globals::ThreadQuitEvent = EventW;
  Globals::ThreadNotify = v1;
  LeaveCriticalSection(&BackgroundThreadCriticalSection::critSec);
  Globals::BackgroundThreadHandle = CreateThreadAndAddRefDll(v3, v2, v4, v5, v7, v8);
  if ( !Globals::BackgroundThreadHandle )
  {
LABEL_4:
    BackgroundThreadShutdown();
    return 0;
  }
  Globals::HiddenWindowOwnerToken = 1;
  return 1;
}

```

## disassembly

```asm
0x1800c6d8c  mov     [rsp+arg_0], rbx
0x1800c6d91  push    rdi
0x1800c6d92  sub     rsp, 30h
0x1800c6d96  xor     r9d, r9d; lpName
0x1800c6d99  xor     r8d, r8d; bInitialState
0x1800c6d9c  xor     ecx, ecx; lpEventAttributes
0x1800c6d9e  lea     edx, [r9+1]; bManualReset
0x1800c6da2  call    cs:__imp_CreateEventW
0x1800c6da9  nop     dword ptr [rax+rax+00h]
0x1800c6dae  mov     rbx, rax
0x1800c6db1  test    rax, rax
0x1800c6db4  jz      short loc_1800C6E1B
0x1800c6db6  xor     r9d, r9d; lpName
0x1800c6db9  xor     r8d, r8d; bInitialState
0x1800c6dbc  xor     ecx, ecx; lpEventAttributes
0x1800c6dbe  lea     edx, [r9+1]; bManualReset
0x1800c6dc2  call    cs:__imp_CreateEventW
0x1800c6dc9  nop     dword ptr [rax+rax+00h]
0x1800c6dce  mov     rdi, rax
0x1800c6dd1  test    rax, rax
0x1800c6dd4  jz      short loc_1800C6E40
0x1800c6dd6  lea     rcx, ?critSec@BackgroundThreadCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800c6ddd  call    cs:__imp_EnterCriticalSection
0x1800c6de4  nop     dword ptr [rax+rax+00h]
0x1800c6de9  lea     rcx, ?critSec@BackgroundThreadCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800c6df0  mov     cs:?ThreadQuitEvent@Globals@@3PEAXEA, rbx; void * Globals::ThreadQuitEvent
0x1800c6df7  mov     cs:?ThreadNotify@Globals@@3PEAXEA, rdi; void * Globals::ThreadNotify
0x1800c6dfe  call    cs:__imp_LeaveCriticalSection
0x1800c6e05  nop     dword ptr [rax+rax+00h]
0x1800c6e0a  call    ?CreateThreadAndAddRefDll@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@_KP6AKPEAX@Z2KPEAK@Z; CreateThreadAndAddRefDll(_SECURITY_ATTRIBUTES *,unsigned __int64,ulong (*)(void *),void *,ulong,ulong *)
0x1800c6e0f  mov     cs:?BackgroundThreadHandle@Globals@@3PEAXEA, rax; void * Globals::BackgroundThreadHandle
0x1800c6e16  test    rax, rax
0x1800c6e19  jnz     short loc_1800C6E2E
0x1800c6e1b  call    ?BackgroundThreadShutdown@@YAPEAXXZ; BackgroundThreadShutdown(void)
0x1800c6e20  xor     eax, eax
0x1800c6e22  mov     rbx, [rsp+38h+arg_0]
0x1800c6e27  add     rsp, 30h
0x1800c6e2b  pop     rdi
0x1800c6e2c  retn
0x1800c6e2e  mov     cs:?HiddenWindowOwnerToken@Globals@@3_KA, 1; unsigned __int64 Globals::HiddenWindowOwnerToken
0x1800c6e39  mov     eax, 1
0x1800c6e3e  jmp     short loc_1800C6E22
0x1800c6e40  mov     rcx, rbx; hObject
0x1800c6e43  call    cs:__imp_CloseHandle
0x1800c6e4a  nop     dword ptr [rax+rax+00h]
0x1800c6e4f  jmp     short loc_1800C6E1B
```

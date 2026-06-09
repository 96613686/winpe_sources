# BackgroundThreadStartup(void)

- ea: `0x1800cdc48`
- end: `0x1800cdd0d`
- name: `?BackgroundThreadStartup@@YAHXZ`
- size: `197`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800cc950`
- `0x18011c1a0`

## callees

- `0x1800cdc48`
- `0x1800cdd14`
- `0x1800cde74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cdc99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cdc99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cdcba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cdcba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cdc5e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cdc7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cdc5e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cdc7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cdcff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cdcff`

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
0x1800cdc48  mov     [rsp+arg_0], rbx
0x1800cdc4d  push    rdi
0x1800cdc4e  sub     rsp, 30h
0x1800cdc52  xor     r9d, r9d; lpName
0x1800cdc55  xor     r8d, r8d; bInitialState
0x1800cdc58  xor     ecx, ecx; lpEventAttributes
0x1800cdc5a  lea     edx, [r9+1]; bManualReset
0x1800cdc5e  call    cs:__imp_CreateEventW
0x1800cdc65  nop     dword ptr [rax+rax+00h]
0x1800cdc6a  mov     rbx, rax
0x1800cdc6d  test    rax, rax
0x1800cdc70  jz      short loc_1800CDCD7
0x1800cdc72  xor     r9d, r9d; lpName
0x1800cdc75  xor     r8d, r8d; bInitialState
0x1800cdc78  xor     ecx, ecx; lpEventAttributes
0x1800cdc7a  lea     edx, [r9+1]; bManualReset
0x1800cdc7e  call    cs:__imp_CreateEventW
0x1800cdc85  nop     dword ptr [rax+rax+00h]
0x1800cdc8a  mov     rdi, rax
0x1800cdc8d  test    rax, rax
0x1800cdc90  jz      short loc_1800CDCFC
0x1800cdc92  lea     rcx, ?critSec@BackgroundThreadCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cdc99  call    cs:__imp_EnterCriticalSection
0x1800cdca0  nop     dword ptr [rax+rax+00h]
0x1800cdca5  lea     rcx, ?critSec@BackgroundThreadCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cdcac  mov     cs:?ThreadQuitEvent@Globals@@3PEAXEA, rbx; void * Globals::ThreadQuitEvent
0x1800cdcb3  mov     cs:?ThreadNotify@Globals@@3PEAXEA, rdi; void * Globals::ThreadNotify
0x1800cdcba  call    cs:__imp_LeaveCriticalSection
0x1800cdcc1  nop     dword ptr [rax+rax+00h]
0x1800cdcc6  call    ?CreateThreadAndAddRefDll@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@_KP6AKPEAX@Z2KPEAK@Z; CreateThreadAndAddRefDll(_SECURITY_ATTRIBUTES *,unsigned __int64,ulong (*)(void *),void *,ulong,ulong *)
0x1800cdccb  mov     cs:?BackgroundThreadHandle@Globals@@3PEAXEA, rax; void * Globals::BackgroundThreadHandle
0x1800cdcd2  test    rax, rax
0x1800cdcd5  jnz     short loc_1800CDCEA
0x1800cdcd7  call    ?BackgroundThreadShutdown@@YAPEAXXZ; BackgroundThreadShutdown(void)
0x1800cdcdc  xor     eax, eax
0x1800cdcde  mov     rbx, [rsp+38h+arg_0]
0x1800cdce3  add     rsp, 30h
0x1800cdce7  pop     rdi
0x1800cdce8  retn
0x1800cdcea  mov     cs:?HiddenWindowOwnerToken@Globals@@3_KA, 1; unsigned __int64 Globals::HiddenWindowOwnerToken
0x1800cdcf5  mov     eax, 1
0x1800cdcfa  jmp     short loc_1800CDCDE
0x1800cdcfc  mov     rcx, rbx; hObject
0x1800cdcff  call    cs:__imp_CloseHandle
0x1800cdd06  nop     dword ptr [rax+rax+00h]
0x1800cdd0b  jmp     short loc_1800CDCD7
```

# TmDeinit(void)

- ea: `0x18001ed50`
- end: `0x18001ee27`
- name: `?TmDeinit@@YAKXZ`
- size: `215`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b9fc`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18001ed50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edb2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18001eda8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18001eda8`

## pseudocode

```c
__int64 TmDeinit(void)
{
  DWORD v0; // ebx
  struct _LIST_ENTRY *v1; // rcx
  DWORD LastError; // eax

  v0 = 0;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 13, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids);
    v1 = WPP_GLOBAL_Control;
  }
  if ( !g_hTimerQueue )
    goto LABEL_12;
  if ( DeleteTimerQueueEx(g_hTimerQueue, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    goto LABEL_11;
  LastError = GetLastError();
  v0 = LastError;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v0;
  if ( BYTE1(WPP_GLOBAL_Control[1].Blink) && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 14, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids, LastError);
LABEL_11:
    v1 = WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v1 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v1[1].Blink) >= 4u && (BYTE4(v1[1].Blink) & 1) != 0 )
    WPP_SF_d(v1[1].Flink, 15, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x18001ed50  mov     [rsp+arg_0], rbx
0x18001ed55  push    rsi
0x18001ed56  sub     rsp, 20h
0x18001ed5a  xor     ebx, ebx
0x18001ed5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed63  lea     rsi, WPP_GLOBAL_Control
0x18001ed6a  cmp     rcx, rsi
0x18001ed6d  jz      short loc_18001ED95
0x18001ed6f  cmp     byte ptr [rcx+19h], 4
0x18001ed73  jb      short loc_18001ED95
0x18001ed75  test    byte ptr [rcx+1Ch], 1
0x18001ed79  jz      short loc_18001ED95
0x18001ed7b  mov     rcx, [rcx+10h]
0x18001ed7f  lea     edx, [rbx+0Dh]
0x18001ed82  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001ed89  call    WPP_SF_
0x18001ed8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed95  mov     rax, cs:?g_hTimerQueue@@3PEAXEA; void * g_hTimerQueue
0x18001ed9c  test    rax, rax
0x18001ed9f  jz      short loc_18001EDF1
0x18001eda1  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001eda5  mov     rcx, rax; TimerQueue
0x18001eda8  call    cs:__imp_DeleteTimerQueueEx
0x18001edae  test    eax, eax
0x18001edb0  jnz     short loc_18001EDEA
0x18001edb2  call    cs:__imp_GetLastError
0x18001edb8  mov     ebx, eax
0x18001edba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edc1  cmp     rcx, rsi
0x18001edc4  jz      short loc_18001EE1A
0x18001edc6  cmp     byte ptr [rcx+19h], 1
0x18001edca  jb      short loc_18001EDF1
0x18001edcc  test    byte ptr [rcx+1Ch], 1
0x18001edd0  jz      short loc_18001EDF1
0x18001edd2  mov     rcx, [rcx+10h]
0x18001edd6  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001eddd  mov     edx, 0Eh
0x18001ede2  mov     r9d, eax
0x18001ede5  call    WPP_SF_d
0x18001edea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edf1  cmp     rcx, rsi
0x18001edf4  jz      short loc_18001EE1A
0x18001edf6  cmp     byte ptr [rcx+19h], 4
0x18001edfa  jb      short loc_18001EE1A
0x18001edfc  test    byte ptr [rcx+1Ch], 1
0x18001ee00  jz      short loc_18001EE1A
0x18001ee02  mov     rcx, [rcx+10h]
0x18001ee06  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001ee0d  mov     edx, 0Fh
0x18001ee12  mov     r9d, ebx
0x18001ee15  call    WPP_SF_d
0x18001ee1a  mov     eax, ebx
0x18001ee1c  mov     rbx, [rsp+28h+arg_0]
0x18001ee21  add     rsp, 20h
0x18001ee25  pop     rsi
0x18001ee26  retn
```

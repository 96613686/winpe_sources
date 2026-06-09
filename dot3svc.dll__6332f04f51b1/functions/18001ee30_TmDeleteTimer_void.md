# TmDeleteTimer(void *)

- ea: `0x18001ee30`
- end: `0x18001ef08`
- name: `?TmDeleteTimer@@YAKPEAX@Z`
- size: `216`
- prototype: `__int64 __fastcall(HANDLE Timer)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180014040`
- `0x180014100`
- `0x180017a00`
- `0x1800224ac`
- `0x1800226b8`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18001ee30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee8e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001ee84`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001ee84`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TmDeleteTimer(HANDLE Timer)
{
  DWORD v2; // ebx
  DWORD LastError; // eax
  struct _LIST_ENTRY *v4; // rcx

  v2 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 22, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids);
  }
  if ( DeleteTimerQueueTimer(g_hTimerQueue, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    goto LABEL_10;
  LastError = GetLastError();
  v2 = LastError;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v2;
  if ( BYTE1(WPP_GLOBAL_Control[1].Blink) && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 23, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids, LastError);
LABEL_10:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v4[1].Blink) >= 4u && (BYTE4(v4[1].Blink) & 1) != 0 )
    WPP_SF_d(v4[1].Flink, 24, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18001ee30  mov     [rsp+arg_0], rbx
0x18001ee35  mov     [rsp+arg_8], rbp
0x18001ee3a  push    rdi
0x18001ee3b  sub     rsp, 20h
0x18001ee3f  mov     rdi, rcx
0x18001ee42  xor     ebx, ebx
0x18001ee44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee4b  lea     rbp, WPP_GLOBAL_Control
0x18001ee52  cmp     rcx, rbp
0x18001ee55  jz      short loc_18001EE76
0x18001ee57  cmp     byte ptr [rcx+19h], 4
0x18001ee5b  jb      short loc_18001EE76
0x18001ee5d  test    byte ptr [rcx+1Ch], 1
0x18001ee61  jz      short loc_18001EE76
0x18001ee63  mov     rcx, [rcx+10h]
0x18001ee67  lea     edx, [rbx+16h]
0x18001ee6a  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001ee71  call    WPP_SF_
0x18001ee76  mov     rcx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x18001ee7d  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001ee81  mov     rdx, rdi; Timer
0x18001ee84  call    cs:__imp_DeleteTimerQueueTimer
0x18001ee8a  test    eax, eax
0x18001ee8c  jnz     short loc_18001EEC6
0x18001ee8e  call    cs:__imp_GetLastError
0x18001ee94  mov     ebx, eax
0x18001ee96  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee9d  cmp     rcx, rbp
0x18001eea0  jz      short loc_18001EEF6
0x18001eea2  cmp     byte ptr [rcx+19h], 1
0x18001eea6  jb      short loc_18001EECD
0x18001eea8  test    byte ptr [rcx+1Ch], 1
0x18001eeac  jz      short loc_18001EECD
0x18001eeae  mov     rcx, [rcx+10h]
0x18001eeb2  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001eeb9  mov     edx, 17h
0x18001eebe  mov     r9d, eax
0x18001eec1  call    WPP_SF_d
0x18001eec6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eecd  cmp     rcx, rbp
0x18001eed0  jz      short loc_18001EEF6
0x18001eed2  cmp     byte ptr [rcx+19h], 4
0x18001eed6  jb      short loc_18001EEF6
0x18001eed8  test    byte ptr [rcx+1Ch], 1
0x18001eedc  jz      short loc_18001EEF6
0x18001eede  mov     rcx, [rcx+10h]
0x18001eee2  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001eee9  mov     edx, 18h
0x18001eeee  mov     r9d, ebx
0x18001eef1  call    WPP_SF_d
0x18001eef6  mov     rbp, [rsp+28h+arg_8]
0x18001eefb  mov     eax, ebx
0x18001eefd  mov     rbx, [rsp+28h+arg_0]
0x18001ef02  add     rsp, 20h
0x18001ef06  pop     rdi
0x18001ef07  retn
```

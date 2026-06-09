# TmCreateTimer(_LAN_TIMER_CONTEXT *,ulong,ulong,void * *)

- ea: `0x18001ec18`
- end: `0x18001ed47`
- name: `?TmCreateTimer@@YAKPEAU_LAN_TIMER_CONTEXT@@KKPEAPEAX@Z`
- size: `303`
- prototype: `__int64 __fastcall(PVOID Parameter, DWORD DueTime, DWORD Period, PHANDLE phNewTimer)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180014100`
- `0x180019474`
- `0x1800226b8`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18001ec18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecd0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001ecc6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001ecc6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TmCreateTimer(PVOID Parameter, DWORD DueTime, DWORD Period, PHANDLE phNewTimer)
{
  struct _LIST_ENTRY *v8; // rcx
  unsigned int v9; // ebx
  DWORD LastError; // eax

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 18, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !Parameter )
  {
    if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v8[1].Blink) && (BYTE4(v8[1].Blink) & 1) != 0 )
    {
      WPP_SF_(v8[1].Flink, 19, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    v9 = 87;
    goto LABEL_17;
  }
  v9 = 0;
  if ( CreateTimerQueueTimer(phNewTimer, g_hTimerQueue, TmTimeoutCallback, Parameter, DueTime, Period, 0) )
    goto LABEL_16;
  LastError = GetLastError();
  v9 = LastError;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v9;
  if ( BYTE1(WPP_GLOBAL_Control[1].Blink) && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 20, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids, LastError);
LABEL_16:
    v8 = WPP_GLOBAL_Control;
  }
LABEL_17:
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v8[1].Blink) >= 4u && (BYTE4(v8[1].Blink) & 1) != 0 )
    WPP_SF_d(v8[1].Flink, 21, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18001ec18  push    rbx
0x18001ec1a  push    rbp
0x18001ec1b  push    rsi
0x18001ec1c  push    rdi
0x18001ec1d  push    r12
0x18001ec1f  push    r14
0x18001ec21  sub     rsp, 48h
0x18001ec25  mov     rsi, r9
0x18001ec28  mov     ebp, r8d
0x18001ec2b  mov     r14d, edx
0x18001ec2e  mov     rdi, rcx
0x18001ec31  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec38  lea     r12, WPP_GLOBAL_Control
0x18001ec3f  cmp     rcx, r12
0x18001ec42  jz      short loc_18001EC6C
0x18001ec44  cmp     byte ptr [rcx+19h], 4
0x18001ec48  jb      short loc_18001EC6C
0x18001ec4a  test    byte ptr [rcx+1Ch], 1
0x18001ec4e  jz      short loc_18001EC6C
0x18001ec50  mov     rcx, [rcx+10h]
0x18001ec54  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001ec5b  mov     edx, 12h
0x18001ec60  call    WPP_SF_
0x18001ec65  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec6c  test    rdi, rdi
0x18001ec6f  jnz     short loc_18001ECA3
0x18001ec71  cmp     rcx, r12
0x18001ec74  jz      short loc_18001EC9C
0x18001ec76  cmp     byte ptr [rcx+19h], 1
0x18001ec7a  jb      short loc_18001EC9C
0x18001ec7c  test    byte ptr [rcx+1Ch], 1
0x18001ec80  jz      short loc_18001EC9C
0x18001ec82  mov     rcx, [rcx+10h]
0x18001ec86  lea     edx, [rdi+13h]
0x18001ec89  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001ec90  call    WPP_SF_
0x18001ec95  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec9c  mov     ebx, 57h ; 'W'
0x18001eca1  jmp     short loc_18001ED0F
0x18001eca3  mov     rdx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x18001ecaa  lea     r8, ?TmTimeoutCallback@@YAXPEAXE@Z; Callback
0x18001ecb1  xor     ebx, ebx
0x18001ecb3  mov     r9, rdi; Parameter
0x18001ecb6  mov     [rsp+78h+Flags], ebx; Flags
0x18001ecba  mov     rcx, rsi; phNewTimer
0x18001ecbd  mov     [rsp+78h+Period], ebp; Period
0x18001ecc1  mov     [rsp+78h+DueTime], r14d; DueTime
0x18001ecc6  call    cs:__imp_CreateTimerQueueTimer
0x18001eccc  test    eax, eax
0x18001ecce  jnz     short loc_18001ED08
0x18001ecd0  call    cs:__imp_GetLastError
0x18001ecd6  mov     ebx, eax
0x18001ecd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecdf  cmp     rcx, r12
0x18001ece2  jz      short loc_18001ED38
0x18001ece4  cmp     byte ptr [rcx+19h], 1
0x18001ece8  jb      short loc_18001ED0F
0x18001ecea  test    byte ptr [rcx+1Ch], 1
0x18001ecee  jz      short loc_18001ED0F
0x18001ecf0  mov     rcx, [rcx+10h]
0x18001ecf4  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001ecfb  mov     edx, 14h
0x18001ed00  mov     r9d, eax
0x18001ed03  call    WPP_SF_d
0x18001ed08  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed0f  cmp     rcx, r12
0x18001ed12  jz      short loc_18001ED38
0x18001ed14  cmp     byte ptr [rcx+19h], 4
0x18001ed18  jb      short loc_18001ED38
0x18001ed1a  test    byte ptr [rcx+1Ch], 1
0x18001ed1e  jz      short loc_18001ED38
0x18001ed20  mov     rcx, [rcx+10h]
0x18001ed24  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001ed2b  mov     edx, 15h
0x18001ed30  mov     r9d, ebx
0x18001ed33  call    WPP_SF_d
0x18001ed38  mov     eax, ebx
0x18001ed3a  add     rsp, 48h
0x18001ed3e  pop     r14
0x18001ed40  pop     r12
0x18001ed42  pop     rdi
0x18001ed43  pop     rsi
0x18001ed44  pop     rbp
0x18001ed45  pop     rbx
0x18001ed46  retn
```

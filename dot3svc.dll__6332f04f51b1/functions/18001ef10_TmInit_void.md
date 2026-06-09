# TmInit(void)

- ea: `0x18001ef10`
- end: `0x18001efe5`
- name: `?TmInit@@YAKXZ`
- size: `213`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aac0`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18001ef10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef70`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18001ef5e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18001ef5e`

## pseudocode

```c
__int64 TmInit(void)
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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids);
    v1 = WPP_GLOBAL_Control;
  }
  if ( g_hTimerQueue )
    goto LABEL_12;
  g_hTimerQueue = CreateTimerQueue();
  if ( g_hTimerQueue )
    goto LABEL_11;
  LastError = GetLastError();
  v0 = LastError;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v0;
  if ( BYTE1(WPP_GLOBAL_Control[1].Blink) && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 11, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids, LastError);
LABEL_11:
    v1 = WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v1 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v1[1].Blink) >= 4u && (BYTE4(v1[1].Blink) & 1) != 0 )
    WPP_SF_d(v1[1].Flink, 12, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x18001ef10  mov     [rsp+arg_0], rbx
0x18001ef15  push    rsi
0x18001ef16  sub     rsp, 20h
0x18001ef1a  xor     ebx, ebx
0x18001ef1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef23  lea     rsi, WPP_GLOBAL_Control
0x18001ef2a  cmp     rcx, rsi
0x18001ef2d  jz      short loc_18001EF55
0x18001ef2f  cmp     byte ptr [rcx+19h], 4
0x18001ef33  jb      short loc_18001EF55
0x18001ef35  test    byte ptr [rcx+1Ch], 1
0x18001ef39  jz      short loc_18001EF55
0x18001ef3b  mov     rcx, [rcx+10h]
0x18001ef3f  lea     edx, [rbx+0Ah]
0x18001ef42  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001ef49  call    WPP_SF_
0x18001ef4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef55  cmp     cs:?g_hTimerQueue@@3PEAXEA, rbx; void * g_hTimerQueue
0x18001ef5c  jnz     short loc_18001EFAF
0x18001ef5e  call    cs:__imp_CreateTimerQueue
0x18001ef64  mov     cs:?g_hTimerQueue@@3PEAXEA, rax; void * g_hTimerQueue
0x18001ef6b  test    rax, rax
0x18001ef6e  jnz     short loc_18001EFA8
0x18001ef70  call    cs:__imp_GetLastError
0x18001ef76  mov     ebx, eax
0x18001ef78  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef7f  cmp     rcx, rsi
0x18001ef82  jz      short loc_18001EFD8
0x18001ef84  cmp     byte ptr [rcx+19h], 1
0x18001ef88  jb      short loc_18001EFAF
0x18001ef8a  test    byte ptr [rcx+1Ch], 1
0x18001ef8e  jz      short loc_18001EFAF
0x18001ef90  mov     rcx, [rcx+10h]
0x18001ef94  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001ef9b  mov     edx, 0Bh
0x18001efa0  mov     r9d, eax
0x18001efa3  call    WPP_SF_d
0x18001efa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efaf  cmp     rcx, rsi
0x18001efb2  jz      short loc_18001EFD8
0x18001efb4  cmp     byte ptr [rcx+19h], 4
0x18001efb8  jb      short loc_18001EFD8
0x18001efba  test    byte ptr [rcx+1Ch], 1
0x18001efbe  jz      short loc_18001EFD8
0x18001efc0  mov     rcx, [rcx+10h]
0x18001efc4  lea     r8, WPP_d37e7eac81603c74ada5f5cc384b309f_Traceguids
0x18001efcb  mov     edx, 0Ch
0x18001efd0  mov     r9d, ebx
0x18001efd3  call    WPP_SF_d
0x18001efd8  mov     eax, ebx
0x18001efda  mov     rbx, [rsp+28h+arg_0]
0x18001efdf  add     rsp, 20h
0x18001efe3  pop     rsi
0x18001efe4  retn
```

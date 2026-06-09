# EventQueue_QueueWorkItem(EVENT_THREAD_CONTROL_BLOCK *)

- ea: `0x18000d760`
- end: `0x18000d856`
- name: `?EventQueue_QueueWorkItem@@YAJPEAUEVENT_THREAD_CONTROL_BLOCK@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(struct EVENT_THREAD_CONTROL_BLOCK *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e030`
- `0x18000ea28`

## callees

- `0x18000c1d0`
- `0x18000c3f0`
- `0x18000d760`
- `0x18002f10c`
- `0x180036394`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d7ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d7ed`
- `KERNEL32!TrySubmitThreadpoolCallback` at `0x18000d7cd`
- `KERNEL32!TrySubmitThreadpoolCallback` at `0x18000d7cd`
- `KERNEL32!LocalAlloc` at `0x18000d786`
- `KERNEL32!LocalAlloc` at `0x18000d786`
- `KERNEL32!LocalFree` at `0x18000d7f6`
- `KERNEL32!LocalFree` at `0x18000d7f6`

## pseudocode

```c
__int64 __fastcall EventQueue_QueueWorkItem(struct EVENT_THREAD_CONTROL_BLOCK *a1)
{
  _QWORD *v2; // rbx
  unsigned int Error; // edi
  DWORD LastError; // esi
  void *v5; // rcx

  CInvSemaphore::Increment((CInvSemaphore *)&g_invsemThreadControlBlocks);
  v2 = LocalAlloc(0x40u, 0x28u);
  if ( !v2 && GetLastError() )
    goto LABEL_9;
  v2[4] = a1;
  v2[2] = EventQueue_PacketProcessingProc;
  Error = 0;
  v2[3] = EventQueue_PacketWorkItemCancelled;
  *(_DWORD *)v2 = 0;
  if ( !TrySubmitThreadpoolCallback((PTP_SIMPLE_CALLBACK)CscTppSimpleWorkItemCallback, v2, &pcbe) )
  {
    LastError = GetLastError();
    if ( v2 )
    {
      v5 = (void *)v2[1];
      if ( v5 )
        CloseHandle(v5);
      LocalFree(v2);
    }
    if ( LastError )
    {
LABEL_9:
      CInvSemaphore::Decrement((CInvSemaphore *)&g_invsemThreadControlBlocks);
      Error = ResultFromLastError();
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids, Error);
    }
  }
  return Error;
}

```

## disassembly

```asm
0x18000d760  mov     [rsp+arg_0], rbx
0x18000d765  mov     [rsp+arg_8], rsi
0x18000d76a  push    rdi
0x18000d76b  sub     rsp, 20h
0x18000d76f  mov     rsi, rcx
0x18000d772  lea     rcx, ?g_invsemThreadControlBlocks@@3VCInvSemaphore@@A; this
0x18000d779  call    ?Increment@CInvSemaphore@@QEAAXXZ; CInvSemaphore::Increment(void)
0x18000d77e  mov     edx, 28h ; '('; uBytes
0x18000d783  lea     ecx, [rdx+18h]; uFlags
0x18000d786  call    cs:__imp_LocalAlloc
0x18000d78c  mov     rbx, rax
0x18000d78f  test    rax, rax
0x18000d792  jnz     short loc_18000D79E
0x18000d794  call    cs:__imp_GetLastError
0x18000d79a  test    eax, eax
0x18000d79c  jnz     short loc_18000D800
0x18000d79e  lea     rax, ?EventQueue_PacketProcessingProc@@YAKPEAX@Z; EventQueue_PacketProcessingProc(void *)
0x18000d7a5  mov     [rbx+20h], rsi
0x18000d7a9  mov     [rbx+10h], rax
0x18000d7ad  lea     r8, pcbe; pcbe
0x18000d7b4  lea     rax, ?EventQueue_PacketWorkItemCancelled@@YAKPEAX@Z; EventQueue_PacketWorkItemCancelled(void *)
0x18000d7bb  xor     edi, edi
0x18000d7bd  mov     rdx, rbx; pv
0x18000d7c0  mov     [rbx+18h], rax
0x18000d7c4  lea     rcx, ?CscTppSimpleWorkItemCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18000d7cb  mov     [rbx], edi
0x18000d7cd  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000d7d3  test    eax, eax
0x18000d7d5  jnz     short loc_18000D844
0x18000d7d7  call    cs:__imp_GetLastError
0x18000d7dd  mov     esi, eax
0x18000d7df  test    rbx, rbx
0x18000d7e2  jz      short loc_18000D7FC
0x18000d7e4  mov     rcx, [rbx+8]; hObject
0x18000d7e8  test    rcx, rcx
0x18000d7eb  jz      short loc_18000D7F3
0x18000d7ed  call    cs:__imp_CloseHandle
0x18000d7f3  mov     rcx, rbx; hMem
0x18000d7f6  call    cs:__imp_LocalFree
0x18000d7fc  test    esi, esi
0x18000d7fe  jz      short loc_18000D844
0x18000d800  lea     rcx, ?g_invsemThreadControlBlocks@@3VCInvSemaphore@@A; this
0x18000d807  call    ?Decrement@CInvSemaphore@@QEAAXXZ; CInvSemaphore::Decrement(void)
0x18000d80c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000d811  mov     edi, eax
0x18000d813  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d81a  lea     rax, WPP_GLOBAL_Control
0x18000d821  cmp     rcx, rax
0x18000d824  jz      short loc_18000D844
0x18000d826  test    byte ptr [rcx+1Ch], 2
0x18000d82a  jz      short loc_18000D844
0x18000d82c  mov     rcx, [rcx+10h]
0x18000d830  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x18000d837  mov     edx, 0Fh
0x18000d83c  mov     r9d, edi
0x18000d83f  call    WPP_SF_d
0x18000d844  mov     rbx, [rsp+28h+arg_0]
0x18000d849  mov     eax, edi
0x18000d84b  mov     rsi, [rsp+28h+arg_8]
0x18000d850  add     rsp, 20h
0x18000d854  pop     rdi
0x18000d855  retn
```

# azure::storage::core::windows_timer::stop(bool)

- ea: `0x180077600`
- end: `0x180077652`
- name: `?stop@windows_timer@core@storage@azure@@QEAAX_N@Z`
- size: `82`
- prototype: `void __fastcall(azure::storage::core::windows_timer *__hidden this, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18007f370`

## callees

- `0x180077600`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077627`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18007761d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18007763d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18007761d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18007763d`

## pseudocode

```c
void __fastcall azure::storage::core::windows_timer::stop(HANDLE *this, unsigned __int8 a2)
{
  __int64 v3; // rdi

  v3 = a2 ^ 1LL;
  if ( !DeleteTimerQueueTimer(0, *this, (HANDLE)(v3 - 1)) )
  {
    while ( GetLastError() != 997 && !DeleteTimerQueueTimer(0, *this, (HANDLE)(v3 - 1)) )
      ;
  }
}

```

## disassembly

```asm
0x180077600  mov     [rsp+arg_0], rbx
0x180077605  push    rdi
0x180077606  sub     rsp, 20h
0x18007760a  movzx   edi, dl
0x18007760d  mov     rbx, rcx
0x180077610  mov     rdx, [rcx]; Timer
0x180077613  xor     rdi, 1
0x180077617  xor     ecx, ecx; TimerQueue
0x180077619  lea     r8, [rdi-1]; CompletionEvent
0x18007761d  call    cs:__imp_DeleteTimerQueueTimer
0x180077623  test    eax, eax
0x180077625  jnz     short loc_180077647
0x180077627  call    cs:__imp_GetLastError
0x18007762d  cmp     eax, 3E5h
0x180077632  jz      short loc_180077647
0x180077634  mov     rdx, [rbx]; Timer
0x180077637  lea     r8, [rdi-1]; CompletionEvent
0x18007763b  xor     ecx, ecx; TimerQueue
0x18007763d  call    cs:__imp_DeleteTimerQueueTimer
0x180077643  test    eax, eax
0x180077645  jz      short loc_180077627
0x180077647  mov     rbx, [rsp+28h+arg_0]
0x18007764c  add     rsp, 20h
0x180077650  pop     rdi
0x180077651  retn
```

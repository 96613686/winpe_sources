# _Init_thread_header

- ea: `0x180004c64`
- end: `0x180004cc9`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180020ef8`
- `0x180021688`
- `0x180021ec4`

## callees

- `0x180004c64`
- `0x180004d18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004c74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004c74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004cc2`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_180032A78);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    Init_thread_wait_v2();
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  LeaveCriticalSection(&stru_180032A78);
}

```

## disassembly

```asm
0x180004c64  push    rbx
0x180004c66  sub     rsp, 20h
0x180004c6a  mov     rbx, rcx
0x180004c6d  lea     rcx, stru_180032A78; lpCriticalSection
0x180004c74  call    cs:__imp_EnterCriticalSection
0x180004c7a  cmp     dword ptr [rbx], 0
0x180004c7d  jnz     short loc_180004C8E
0x180004c7f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180004c85  jmp     short loc_180004CB6
0x180004c87  call    _Init_thread_wait_v2
0x180004c8c  jmp     short loc_180004C7A
0x180004c8e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180004c91  jz      short loc_180004C87
0x180004c93  mov     rax, gs:58h
0x180004c9c  mov     ecx, cs:_tls_index
0x180004ca2  mov     r8d, 4
0x180004ca8  mov     rdx, [rax+rcx*8]
0x180004cac  mov     eax, cs:_Init_global_epoch
0x180004cb2  mov     [r8+rdx], eax
0x180004cb6  lea     rcx, stru_180032A78
0x180004cbd  add     rsp, 20h
0x180004cc1  pop     rbx
0x180004cc2  jmp     cs:__imp_LeaveCriticalSection
```

# _Init_thread_header

- ea: `0x180002ca4`
- end: `0x180002d09`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800136a4`

## callees

- `0x180002ca4`
- `0x180002d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cb4`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&CriticalSection);
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
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180002ca4  push    rbx
0x180002ca6  sub     rsp, 20h
0x180002caa  mov     rbx, rcx
0x180002cad  lea     rcx, CriticalSection; lpCriticalSection
0x180002cb4  call    cs:__imp_EnterCriticalSection
0x180002cba  cmp     dword ptr [rbx], 0
0x180002cbd  jnz     short loc_180002CCE
0x180002cbf  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002cc5  jmp     short loc_180002CF6
0x180002cc7  call    _Init_thread_wait_v2
0x180002ccc  jmp     short loc_180002CBA
0x180002cce  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002cd1  jz      short loc_180002CC7
0x180002cd3  mov     rax, gs:58h
0x180002cdc  mov     ecx, cs:_tls_index
0x180002ce2  mov     r8d, 4
0x180002ce8  mov     rdx, [rax+rcx*8]
0x180002cec  mov     eax, cs:_Init_global_epoch
0x180002cf2  mov     [r8+rdx], eax
0x180002cf6  lea     rcx, CriticalSection
0x180002cfd  add     rsp, 20h
0x180002d01  pop     rbx
0x180002d02  jmp     cs:__imp_LeaveCriticalSection
```

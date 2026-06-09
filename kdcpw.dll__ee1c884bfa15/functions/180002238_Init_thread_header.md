# _Init_thread_header

- ea: `0x180002238`
- end: `0x18000229d`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bf24`
- `0x18000c598`

## callees

- `0x180002238`
- `0x1800022ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002248`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002248`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002296`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_180012470);
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
  LeaveCriticalSection(&stru_180012470);
}

```

## disassembly

```asm
0x180002238  push    rbx
0x18000223a  sub     rsp, 20h
0x18000223e  mov     rbx, rcx
0x180002241  lea     rcx, stru_180012470; lpCriticalSection
0x180002248  call    cs:__imp_EnterCriticalSection
0x18000224e  cmp     dword ptr [rbx], 0
0x180002251  jnz     short loc_180002262
0x180002253  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002259  jmp     short loc_18000228A
0x18000225b  call    _Init_thread_wait_v2
0x180002260  jmp     short loc_18000224E
0x180002262  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002265  jz      short loc_18000225B
0x180002267  mov     rax, gs:58h
0x180002270  mov     ecx, cs:_tls_index
0x180002276  mov     r8d, 4
0x18000227c  mov     rdx, [rax+rcx*8]
0x180002280  mov     eax, cs:_Init_global_epoch
0x180002286  mov     [r8+rdx], eax
0x18000228a  lea     rcx, stru_180012470
0x180002291  add     rsp, 20h
0x180002295  pop     rbx
0x180002296  jmp     cs:__imp_LeaveCriticalSection
```

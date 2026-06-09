# _Init_thread_header

- ea: `0x180001c34`
- end: `0x180001c99`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012b10`
- `0x180014220`

## callees

- `0x180001c34`
- `0x180001ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c44`

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
0x180001c34  push    rbx
0x180001c36  sub     rsp, 20h
0x180001c3a  mov     rbx, rcx
0x180001c3d  lea     rcx, CriticalSection; lpCriticalSection
0x180001c44  call    cs:__imp_EnterCriticalSection
0x180001c4a  cmp     dword ptr [rbx], 0
0x180001c4d  jnz     short loc_180001C5E
0x180001c4f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180001c55  jmp     short loc_180001C86
0x180001c57  call    _Init_thread_wait_v2
0x180001c5c  jmp     short loc_180001C4A
0x180001c5e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180001c61  jz      short loc_180001C57
0x180001c63  mov     rax, gs:58h
0x180001c6c  mov     ecx, cs:_tls_index
0x180001c72  mov     r8d, 4
0x180001c78  mov     rdx, [rax+rcx*8]
0x180001c7c  mov     eax, cs:_Init_global_epoch
0x180001c82  mov     [r8+rdx], eax
0x180001c86  lea     rcx, CriticalSection
0x180001c8d  add     rsp, 20h
0x180001c91  pop     rbx
0x180001c92  jmp     cs:__imp_LeaveCriticalSection
```

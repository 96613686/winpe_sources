# _Init_thread_header

- ea: `0x140001d44`
- end: `0x140001da9`
- name: `_Init_thread_header`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002a94`
- `0x140019e24`
- `0x14001a28c`
- `0x140022bd8`

## callees

- `0x140001d44`
- `0x140001df8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140001da2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001d54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001d54`

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
0x140001d44  push    rbx
0x140001d46  sub     rsp, 20h
0x140001d4a  mov     rbx, rcx
0x140001d4d  lea     rcx, CriticalSection; lpCriticalSection
0x140001d54  call    cs:__imp_EnterCriticalSection
0x140001d5a  cmp     dword ptr [rbx], 0
0x140001d5d  jnz     short loc_140001D6E
0x140001d5f  mov     dword ptr [rbx], 0FFFFFFFFh
0x140001d65  jmp     short loc_140001D96
0x140001d67  call    _Init_thread_wait_v2
0x140001d6c  jmp     short loc_140001D5A
0x140001d6e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140001d71  jz      short loc_140001D67
0x140001d73  mov     rax, gs:58h
0x140001d7c  mov     ecx, cs:_tls_index
0x140001d82  mov     r8d, 4
0x140001d88  mov     rdx, [rax+rcx*8]
0x140001d8c  mov     eax, cs:_Init_global_epoch
0x140001d92  mov     [r8+rdx], eax
0x140001d96  lea     rcx, CriticalSection
0x140001d9d  add     rsp, 20h
0x140001da1  pop     rbx
0x140001da2  jmp     cs:__imp_LeaveCriticalSection
```

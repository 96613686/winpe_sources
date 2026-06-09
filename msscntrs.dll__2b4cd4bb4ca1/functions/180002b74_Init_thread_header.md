# _Init_thread_header

- ea: `0x180002b74`
- end: `0x180002bd9`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d9bc`
- `0x18000df84`

## callees

- `0x180002b74`
- `0x180002c28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002bd2`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_180021DA8);
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
  LeaveCriticalSection(&stru_180021DA8);
}

```

## disassembly

```asm
0x180002b74  push    rbx
0x180002b76  sub     rsp, 20h
0x180002b7a  mov     rbx, rcx
0x180002b7d  lea     rcx, stru_180021DA8; lpCriticalSection
0x180002b84  call    cs:__imp_EnterCriticalSection
0x180002b8a  cmp     dword ptr [rbx], 0
0x180002b8d  jnz     short loc_180002B9E
0x180002b8f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002b95  jmp     short loc_180002BC6
0x180002b97  call    _Init_thread_wait_v2
0x180002b9c  jmp     short loc_180002B8A
0x180002b9e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002ba1  jz      short loc_180002B97
0x180002ba3  mov     rax, gs:58h
0x180002bac  mov     ecx, cs:_tls_index
0x180002bb2  mov     r8d, 4
0x180002bb8  mov     rdx, [rax+rcx*8]
0x180002bbc  mov     eax, cs:_Init_global_epoch
0x180002bc2  mov     [r8+rdx], eax
0x180002bc6  lea     rcx, stru_180021DA8
0x180002bcd  add     rsp, 20h
0x180002bd1  pop     rbx
0x180002bd2  jmp     cs:__imp_LeaveCriticalSection
```

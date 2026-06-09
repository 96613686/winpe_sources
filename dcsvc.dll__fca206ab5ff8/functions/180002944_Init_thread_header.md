# _Init_thread_header

- ea: `0x180002944`
- end: `0x1800029a9`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e83c`

## callees

- `0x180002944`
- `0x1800029f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002954`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002954`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029a2`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_18001B688);
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
  LeaveCriticalSection(&stru_18001B688);
}

```

## disassembly

```asm
0x180002944  push    rbx
0x180002946  sub     rsp, 20h
0x18000294a  mov     rbx, rcx
0x18000294d  lea     rcx, stru_18001B688; lpCriticalSection
0x180002954  call    cs:__imp_EnterCriticalSection
0x18000295a  cmp     dword ptr [rbx], 0
0x18000295d  jnz     short loc_18000296E
0x18000295f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002965  jmp     short loc_180002996
0x180002967  call    _Init_thread_wait_v2
0x18000296c  jmp     short loc_18000295A
0x18000296e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002971  jz      short loc_180002967
0x180002973  mov     rax, gs:58h
0x18000297c  mov     ecx, cs:_tls_index
0x180002982  mov     r8d, 4
0x180002988  mov     rdx, [rax+rcx*8]
0x18000298c  mov     eax, cs:_Init_global_epoch
0x180002992  mov     [r8+rdx], eax
0x180002996  lea     rcx, stru_18001B688
0x18000299d  add     rsp, 20h
0x1800029a1  pop     rbx
0x1800029a2  jmp     cs:__imp_LeaveCriticalSection
```

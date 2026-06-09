# _Init_thread_header

- ea: `0x1800021b4`
- end: `0x180002219`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180009d10`
- `0x18000ad80`
- `0x18000ae80`

## callees

- `0x1800021b4`
- `0x180002268`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002212`

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
0x1800021b4  push    rbx
0x1800021b6  sub     rsp, 20h
0x1800021ba  mov     rbx, rcx
0x1800021bd  lea     rcx, CriticalSection; lpCriticalSection
0x1800021c4  call    cs:__imp_EnterCriticalSection
0x1800021ca  cmp     dword ptr [rbx], 0
0x1800021cd  jnz     short loc_1800021DE
0x1800021cf  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800021d5  jmp     short loc_180002206
0x1800021d7  call    _Init_thread_wait_v2
0x1800021dc  jmp     short loc_1800021CA
0x1800021de  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800021e1  jz      short loc_1800021D7
0x1800021e3  mov     rax, gs:58h
0x1800021ec  mov     ecx, cs:_tls_index
0x1800021f2  mov     r8d, 4
0x1800021f8  mov     rdx, [rax+rcx*8]
0x1800021fc  mov     eax, cs:_Init_global_epoch
0x180002202  mov     [r8+rdx], eax
0x180002206  lea     rcx, CriticalSection
0x18000220d  add     rsp, 20h
0x180002211  pop     rbx
0x180002212  jmp     cs:__imp_LeaveCriticalSection
```

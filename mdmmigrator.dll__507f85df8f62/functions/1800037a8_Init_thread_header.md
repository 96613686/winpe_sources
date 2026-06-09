# _Init_thread_header

- ea: `0x1800037a8`
- end: `0x18000380d`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001dce8`

## callees

- `0x1800037a8`
- `0x18000385c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003806`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800037b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800037b8`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_18002B5C8);
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
  LeaveCriticalSection(&stru_18002B5C8);
}

```

## disassembly

```asm
0x1800037a8  push    rbx
0x1800037aa  sub     rsp, 20h
0x1800037ae  mov     rbx, rcx
0x1800037b1  lea     rcx, stru_18002B5C8; lpCriticalSection
0x1800037b8  call    cs:__imp_EnterCriticalSection
0x1800037be  cmp     dword ptr [rbx], 0
0x1800037c1  jnz     short loc_1800037D2
0x1800037c3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800037c9  jmp     short loc_1800037FA
0x1800037cb  call    _Init_thread_wait_v2
0x1800037d0  jmp     short loc_1800037BE
0x1800037d2  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800037d5  jz      short loc_1800037CB
0x1800037d7  mov     rax, gs:58h
0x1800037e0  mov     ecx, cs:_tls_index
0x1800037e6  mov     r8d, 4
0x1800037ec  mov     rdx, [rax+rcx*8]
0x1800037f0  mov     eax, cs:_Init_global_epoch
0x1800037f6  mov     [r8+rdx], eax
0x1800037fa  lea     rcx, stru_18002B5C8
0x180003801  add     rsp, 20h
0x180003805  pop     rbx
0x180003806  jmp     cs:__imp_LeaveCriticalSection
```

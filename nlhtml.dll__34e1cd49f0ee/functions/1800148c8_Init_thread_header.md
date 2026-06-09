# _Init_thread_header

- ea: `0x1800148c8`
- end: `0x18001492d`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d0c`

## callees

- `0x1800148c8`
- `0x18001497c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014926`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800148d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800148d8`

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
0x1800148c8  push    rbx
0x1800148ca  sub     rsp, 20h
0x1800148ce  mov     rbx, rcx
0x1800148d1  lea     rcx, CriticalSection; lpCriticalSection
0x1800148d8  call    cs:__imp_EnterCriticalSection
0x1800148de  cmp     dword ptr [rbx], 0
0x1800148e1  jnz     short loc_1800148F2
0x1800148e3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800148e9  jmp     short loc_18001491A
0x1800148eb  call    _Init_thread_wait_v2
0x1800148f0  jmp     short loc_1800148DE
0x1800148f2  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800148f5  jz      short loc_1800148EB
0x1800148f7  mov     rax, gs:58h
0x180014900  mov     ecx, cs:_tls_index
0x180014906  mov     r8d, 4
0x18001490c  mov     rdx, [rax+rcx*8]
0x180014910  mov     eax, cs:_Init_global_epoch
0x180014916  mov     [r8+rdx], eax
0x18001491a  lea     rcx, CriticalSection
0x180014921  add     rsp, 20h
0x180014925  pop     rbx
0x180014926  jmp     cs:__imp_LeaveCriticalSection
```

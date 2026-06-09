# _Init_thread_header

- ea: `0x1400023b8`
- end: `0x14000241d`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140006390`
- `0x140006570`

## callees

- `0x1400023b8`
- `0x14000246c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400023c8`
- `KERNEL32!EnterCriticalSection` at `0x1400023c8`
- `KERNEL32!LeaveCriticalSection` at `0x140002416`

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
0x1400023b8  push    rbx
0x1400023ba  sub     rsp, 20h
0x1400023be  mov     rbx, rcx
0x1400023c1  lea     rcx, CriticalSection; lpCriticalSection
0x1400023c8  call    cs:__imp_EnterCriticalSection
0x1400023ce  cmp     dword ptr [rbx], 0
0x1400023d1  jnz     short loc_1400023E2
0x1400023d3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1400023d9  jmp     short loc_14000240A
0x1400023db  call    _Init_thread_wait_v2
0x1400023e0  jmp     short loc_1400023CE
0x1400023e2  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1400023e5  jz      short loc_1400023DB
0x1400023e7  mov     rax, gs:58h
0x1400023f0  mov     ecx, cs:_tls_index
0x1400023f6  mov     r8d, 4
0x1400023fc  mov     rdx, [rax+rcx*8]
0x140002400  mov     eax, cs:_Init_global_epoch
0x140002406  mov     [r8+rdx], eax
0x14000240a  lea     rcx, CriticalSection
0x140002411  add     rsp, 20h
0x140002415  pop     rbx
0x140002416  jmp     cs:__imp_LeaveCriticalSection
```

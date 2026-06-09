# _Init_thread_header

- ea: `0x1800023b8`
- end: `0x18000241d`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180013040`
- `0x180013774`

## callees

- `0x1800023b8`
- `0x18000246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002416`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023c8`

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
0x1800023b8  push    rbx
0x1800023ba  sub     rsp, 20h
0x1800023be  mov     rbx, rcx
0x1800023c1  lea     rcx, CriticalSection; lpCriticalSection
0x1800023c8  call    cs:__imp_EnterCriticalSection
0x1800023ce  cmp     dword ptr [rbx], 0
0x1800023d1  jnz     short loc_1800023E2
0x1800023d3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800023d9  jmp     short loc_18000240A
0x1800023db  call    _Init_thread_wait_v2
0x1800023e0  jmp     short loc_1800023CE
0x1800023e2  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800023e5  jz      short loc_1800023DB
0x1800023e7  mov     rax, gs:58h
0x1800023f0  mov     ecx, cs:_tls_index
0x1800023f6  mov     r8d, 4
0x1800023fc  mov     rdx, [rax+rcx*8]
0x180002400  mov     eax, cs:_Init_global_epoch
0x180002406  mov     [r8+rdx], eax
0x18000240a  lea     rcx, CriticalSection
0x180002411  add     rsp, 20h
0x180002415  pop     rbx
0x180002416  jmp     cs:__imp_LeaveCriticalSection
```

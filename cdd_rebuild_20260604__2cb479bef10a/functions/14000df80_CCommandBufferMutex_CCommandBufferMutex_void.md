# CCommandBufferMutex::~CCommandBufferMutex(void)

- ea: `0x14000df80`
- end: `0x14000dfc8`
- name: `??1CCommandBufferMutex@@QEAA@XZ`
- size: `72`
- prototype: `void __fastcall(CCommandBufferMutex *__hidden this)`
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400015e0`
- `0x140003840`
- `0x140005cc0`
- `0x140007b00`
- `0x14000cf80`
- `0x14000ddd0`
- `0x14001c630`
- `0x14001f5d0`
- `0x14001f860`
- `0x140020ca0`
- `0x1400212b0`
- `0x14002ee20`
- `0x14002f640`
- `0x140031110`
- `0x140033800`
- `0x1400339f0`

## callees

- `0x14000df80`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000df99`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000dfb5`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000df99`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000dfb5`

## pseudocode

```c
void __fastcall CCommandBufferMutex::~CCommandBufferMutex(CCommandBufferMutex *this)
{
  if ( *((_BYTE *)this + 9) )
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*(_QWORD *)(*(_QWORD *)this + 2896LL));
  if ( *((_BYTE *)this + 8) )
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*(_QWORD *)(*(_QWORD *)this + 2888LL));
}

```

## disassembly

```asm
0x14000df80  push    rbx
0x14000df82  sub     rsp, 20h
0x14000df86  cmp     byte ptr [rcx+9], 0
0x14000df8a  mov     rbx, rcx
0x14000df8d  jz      short loc_14000DFA5
0x14000df8f  mov     rcx, [rcx]
0x14000df92  mov     rcx, [rcx+0B50h]
0x14000df99  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000dfa0  nop     dword ptr [rax+rax+00h]
0x14000dfa5  cmp     byte ptr [rbx+8], 0
0x14000dfa9  jz      short loc_14000DFC1
0x14000dfab  mov     rcx, [rbx]
0x14000dfae  mov     rcx, [rcx+0B48h]
0x14000dfb5  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000dfbc  nop     dword ptr [rax+rax+00h]
0x14000dfc1  add     rsp, 20h
0x14000dfc5  pop     rbx
0x14000dfc6  retn
```

# AutoThreadpool::AutoThreadpool(void)

- ea: `0x140015054`
- end: `0x1400150b1`
- name: `??0AutoThreadpool@@QEAA@XZ`
- size: `93`
- prototype: `AutoThreadpool *__fastcall(AutoThreadpool *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400107ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140015070`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14001509b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140015070`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14001509b`

## pseudocode

```c
AutoThreadpool *__fastcall AutoThreadpool::AutoThreadpool(AutoThreadpool *this)
{
  *(_QWORD *)this = &AutoThreadpool::`vftable';
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 8), 0, 0);
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 16) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 136), 0, 0);
  return this;
}

```

## disassembly

```asm
0x140015054  push    rbx
0x140015056  sub     rsp, 20h
0x14001505a  lea     rax, ??_7AutoThreadpool@@6B@; const AutoThreadpool::`vftable'
0x140015061  mov     rbx, rcx
0x140015064  mov     [rcx], rax
0x140015067  xor     r8d, r8d; Flags
0x14001506a  add     rcx, 8; lpCriticalSection
0x14001506e  xor     edx, edx; dwSpinCount
0x140015070  call    cs:__imp_InitializeCriticalSectionEx
0x140015077  nop     dword ptr [rax+rax+00h]
0x14001507c  lea     rcx, [rbx+88h]; lpCriticalSection
0x140015083  mov     qword ptr [rbx+30h], 0
0x14001508b  xor     r8d, r8d; Flags
0x14001508e  mov     qword ptr [rbx+80h], 0
0x140015099  xor     edx, edx; dwSpinCount
0x14001509b  call    cs:__imp_InitializeCriticalSectionEx
0x1400150a2  nop     dword ptr [rax+rax+00h]
0x1400150a7  mov     rax, rbx
0x1400150aa  add     rsp, 20h
0x1400150ae  pop     rbx
0x1400150af  retn
```

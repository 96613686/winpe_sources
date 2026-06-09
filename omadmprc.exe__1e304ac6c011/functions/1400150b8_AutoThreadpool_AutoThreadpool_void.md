# AutoThreadpool::~AutoThreadpool(void)

- ea: `0x1400150b8`
- end: `0x1400150f8`
- name: `??1AutoThreadpool@@UEAA@XZ`
- size: `64`
- prototype: `void __fastcall(AutoThreadpool *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140015100`

## callees

- `0x140015438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400150d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400150d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400150ec`

## pseudocode

```c
void __fastcall AutoThreadpool::~AutoThreadpool(AutoThreadpool *this)
{
  *(_QWORD *)this = &AutoThreadpool::`vftable';
  AutoThreadpool::UninitializeAndWaitForPendingWorkItems(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1400150b8  push    rbx
0x1400150ba  sub     rsp, 20h
0x1400150be  lea     rax, ??_7AutoThreadpool@@6B@; const AutoThreadpool::`vftable'
0x1400150c5  mov     rbx, rcx
0x1400150c8  mov     [rcx], rax
0x1400150cb  call    ?UninitializeAndWaitForPendingWorkItems@AutoThreadpool@@QEAAXXZ; AutoThreadpool::UninitializeAndWaitForPendingWorkItems(void)
0x1400150d0  lea     rcx, [rbx+88h]; lpCriticalSection
0x1400150d7  call    cs:__imp_DeleteCriticalSection
0x1400150de  nop     dword ptr [rax+rax+00h]
0x1400150e3  lea     rcx, [rbx+8]
0x1400150e7  add     rsp, 20h
0x1400150eb  pop     rbx
0x1400150ec  jmp     cs:__imp_DeleteCriticalSection
```

# SmFx::Worker::~Worker(void)

- ea: `0x18003489c`
- end: `0x1800348ce`
- name: `??1Worker@SmFx@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(SmFx::Worker *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180032ed8`

## callees

- `0x18003489c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800348ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800348ad`

## pseudocode

```c
void __fastcall SmFx::Worker::~Worker(struct _TP_WORK **this)
{
  struct _TP_WORK *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    CloseThreadpoolWork(v2);
    *this = 0;
    this[1] = 0;
    this[2] = 0;
  }
}

```

## disassembly

```asm
0x18003489c  push    rbx
0x18003489e  sub     rsp, 20h
0x1800348a2  mov     rbx, rcx
0x1800348a5  mov     rcx, [rcx]; pwk
0x1800348a8  test    rcx, rcx
0x1800348ab  jz      short loc_1800348C7
0x1800348ad  call    cs:__imp_CloseThreadpoolWork
0x1800348b4  nop     dword ptr [rax+rax+00h]
0x1800348b9  and     qword ptr [rbx], 0
0x1800348bd  and     qword ptr [rbx+8], 0
0x1800348c2  and     qword ptr [rbx+10h], 0
0x1800348c7  add     rsp, 20h
0x1800348cb  pop     rbx
0x1800348cc  retn
```

# SmFx::Worker::~Worker(void)

- ea: `0x1800329c0`
- end: `0x1800329f4`
- name: `??1Worker@SmFx@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(struct _TP_WORK **this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003111c`

## callees

- `0x1800329c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800329d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800329d1`

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
0x1800329c0  push    rbx
0x1800329c2  sub     rsp, 20h
0x1800329c6  mov     rbx, rcx
0x1800329c9  mov     rcx, [rcx]; pwk
0x1800329cc  test    rcx, rcx
0x1800329cf  jz      short loc_1800329EE
0x1800329d1  call    cs:__imp_CloseThreadpoolWork
0x1800329d7  mov     qword ptr [rbx], 0
0x1800329de  mov     qword ptr [rbx+8], 0
0x1800329e6  mov     qword ptr [rbx+10h], 0
0x1800329ee  add     rsp, 20h
0x1800329f2  pop     rbx
0x1800329f3  retn
```

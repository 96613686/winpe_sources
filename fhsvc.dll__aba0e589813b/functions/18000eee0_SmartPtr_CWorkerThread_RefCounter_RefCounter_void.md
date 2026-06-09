# SmartPtr<CWorkerThread>::RefCounter::~RefCounter(void)

- ea: `0x18000eee0`
- end: `0x18000eef6`
- name: `??1RefCounter@?$SmartPtr@VCWorkerThread@@@@QEAA@XZ`
- size: `22`
- prototype: `void *__fastcall(CWorkerThread **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f11c`

## callees

- `0x18000eee0`
- `0x18000ef8c`

## pseudocode

```c
void *__fastcall SmartPtr<CWorkerThread>::RefCounter::~RefCounter(CWorkerThread **a1, unsigned int a2)
{
  CWorkerThread *v2; // rcx
  void *result; // rax

  v2 = *a1;
  if ( v2 )
    return CWorkerThread::`scalar deleting destructor'(v2, a2);
  return result;
}

```

## disassembly

```asm
0x18000eee0  sub     rsp, 28h
0x18000eee4  mov     rcx, [rcx]; this
0x18000eee7  test    rcx, rcx
0x18000eeea  jz      short loc_18000EEF1
0x18000eeec  call    ??_GCWorkerThread@@QEAAPEAXI@Z; CWorkerThread::`scalar deleting destructor'(uint)
0x18000eef1  add     rsp, 28h
0x18000eef5  retn
```

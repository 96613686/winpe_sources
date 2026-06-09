# CThread::ThreadProc(void *)

- ea: `0x140007d20`
- end: `0x140007d30`
- name: `?ThreadProc@CThread@@CAIPEAX@Z`
- size: `16`
- prototype: `__int64 __fastcall(CThread *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140007af8`

## pseudocode

```c
__int64 __fastcall CThread::ThreadProc(CThread *a1)
{
  CThread::Execute(a1);
  return 0;
}

```

## disassembly

```asm
0x140007d20  sub     rsp, 28h
0x140007d24  call    ?Execute@CThread@@AEAAXXZ; CThread::Execute(void)
0x140007d29  xor     eax, eax
0x140007d2b  add     rsp, 28h
0x140007d2f  retn
```

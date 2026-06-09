# RetrieveTracingHandle(void)

- ea: `0x180003f10`
- end: `0x180003f18`
- name: `?RetrieveTracingHandle@@YAPEAVCEtwTracer@@XZ`
- size: `8`
- prototype: `struct CEtwTracer *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
struct CEtwTracer *RetrieveTracingHandle(void)
{
  return (struct CEtwTracer *)g_pEtwGlobalTracer;
}

```

## disassembly

```asm
0x180003f10  mov     rax, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x180003f17  retn
```

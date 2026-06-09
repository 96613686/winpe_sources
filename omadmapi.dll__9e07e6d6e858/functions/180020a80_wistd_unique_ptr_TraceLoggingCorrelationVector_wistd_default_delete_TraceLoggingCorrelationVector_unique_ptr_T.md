# wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::~unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>(void)

- ea: `0x180020a80`
- end: `0x180020aa6`
- name: `??1?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@wistd@@@wistd@@QEAA@XZ`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002342c`

## callees

- `0x1800031d4`
- `0x180020a80`

## pseudocode

```c
void __fastcall wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::~unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180020a80  sub     rsp, 28h
0x180020a84  mov     rax, [rcx]
0x180020a87  mov     qword ptr [rcx], 0
0x180020a8e  test    rax, rax
0x180020a91  jz      short loc_180020AA0
0x180020a93  mov     edx, 90h; unsigned __int64
0x180020a98  mov     rcx, rax; void *
0x180020a9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020aa0  add     rsp, 28h
0x180020aa4  retn
```

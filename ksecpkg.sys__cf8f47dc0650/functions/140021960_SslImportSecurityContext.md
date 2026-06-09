# SslImportSecurityContext

- ea: `0x140021960`
- end: `0x1400219a5`
- name: `SslImportSecurityContext`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003e30`
- `0x140021960`
- `0x1400230a0`

## pseudocode

```c
__int64 __fastcall SslImportSecurityContext(__int64 a1, __int64 a2, __int64 a3)
{
  signed __int32 v5; // eax

  GetExternalSchannelAlgorithmsDeferred();
  do
    v5 = _InterlockedIncrement((volatile signed __int32 *)&ExportedContext);
  while ( (v5 & 7) == 0 );
  return SslInitKernelContext(v5, a1, a3);
}

```

## disassembly

```asm
0x140021960  mov     [rsp+arg_0], rbx
0x140021965  push    rdi
0x140021966  sub     rsp, 20h
0x14002196a  mov     rbx, r8
0x14002196d  mov     rdi, rcx
0x140021970  call    GetExternalSchannelAlgorithmsDeferred
0x140021975  mov     edx, 1
0x14002197a  mov     eax, edx
0x14002197c  lock xadd cs:?ExportedContext@@3_KA, eax; unsigned __int64 ExportedContext
0x140021984  add     eax, edx
0x140021986  movsxd  rcx, eax
0x140021989  test    cl, 7
0x14002198c  jz      short loc_14002197A
0x14002198e  mov     r8, rbx
0x140021991  mov     rdx, rdi
0x140021994  call    SslInitKernelContext
0x140021999  mov     rbx, [rsp+28h+arg_0]
0x14002199e  add     rsp, 20h
0x1400219a2  pop     rdi
0x1400219a3  retn
```

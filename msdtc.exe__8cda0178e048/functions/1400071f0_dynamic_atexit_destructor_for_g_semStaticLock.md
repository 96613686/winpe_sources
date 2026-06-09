# _dynamic_atexit_destructor_for__g_semStaticLock__

- ea: `0x1400071f0`
- end: `0x140007215`
- name: `_dynamic_atexit_destructor_for__g_semStaticLock__`
- size: `37`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140007209`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140007209`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_semStaticLock__()
{
  qword_140010690 = &CSemExclusive::`vftable';
  DeleteCriticalSection(&stru_140010698);
}

```

## disassembly

```asm
0x1400071f0  sub     rsp, 28h
0x1400071f4  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1400071fb  mov     cs:qword_140010690, rax
0x140007202  lea     rcx, stru_140010698; lpCriticalSection
0x140007209  call    cs:__imp_DeleteCriticalSection
0x14000720f  nop
0x140007210  add     rsp, 28h
0x140007214  retn
```

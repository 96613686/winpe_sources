# Tracer::~Tracer(void)

- ea: `0x18004ad88`
- end: `0x18004ada5`
- name: `??1Tracer@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(Tracer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18004ac3c`
- `0x1800936b3`

## callees

- `0x180028510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ad91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ad91`

## pseudocode

```c
void __fastcall Tracer::~Tracer(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
  std::vector<Troubleshooter *>::_Tidy(&this[2].LockCount);
}

```

## disassembly

```asm
0x18004ad88  push    rbx
0x18004ad8a  sub     rsp, 20h
0x18004ad8e  mov     rbx, rcx
0x18004ad91  call    cs:__imp_DeleteCriticalSection
0x18004ad97  lea     rcx, [rbx+58h]
0x18004ad9b  add     rsp, 20h
0x18004ad9f  pop     rbx
0x18004ada0  jmp     ?_Tidy@?$vector@PEAVTroubleshooter@@V?$allocator@PEAVTroubleshooter@@@std@@@std@@AEAAXXZ; std::vector<Troubleshooter *>::_Tidy(void)
```

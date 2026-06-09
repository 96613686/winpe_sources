# RTSecurityContextBase::~RTSecurityContextBase(void)

- ea: `0x18000a67c`
- end: `0x18000a685`
- name: `??1RTSecurityContextBase@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(RTSecurityContextBase *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180024d56`

## callees

- `0x18000a524`

## pseudocode

```c
void __fastcall RTSecurityContextBase::~RTSecurityContextBase(void **this)
{
  CACSecurityContext::~CACSecurityContext(this + 1);
}

```

## disassembly

```asm
0x18000a67c  add     rcx, 8; this
0x18000a680  jmp     ??1CACSecurityContext@@QEAA@XZ; CACSecurityContext::~CACSecurityContext(void)
```

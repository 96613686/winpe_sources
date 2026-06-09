# CAutoImpersonate::~CAutoImpersonate(void)

- ea: `0x1800115b8`
- end: `0x1800115bd`
- name: `??1CAutoImpersonate@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18001e816`
- `0x18001e8ca`
- `0x18001ed73`
- `0x18001edbb`
- `0x18001ee41`

## callees

- `0x18000927c`

## pseudocode

```c
// attributes: thunk
void __fastcall CAutoImpersonate::~CAutoImpersonate(HANDLE *this)
{
  CAutoImpersonate::ResetImpersonation(this);
}

```

## disassembly

```asm
0x1800115b8  jmp     ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
```

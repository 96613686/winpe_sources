# CPrivateAddRef::~CPrivateAddRef(void)

- ea: `0x180005a38`
- end: `0x180005a3e`
- name: `??1CPrivateAddRef@@QEAA@XZ`
- size: `6`
- prototype: `void __fastcall(CPrivateAddRef *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800134fc`
- `0x18001350e`
- `0x1800135fc`
- `0x18001360e`

## pseudocode

```c
void __fastcall CPrivateAddRef::~CPrivateAddRef(CPrivateAddRef *this)
{
  --**(_DWORD **)this;
}

```

## disassembly

```asm
0x180005a38  mov     rax, [rcx]
0x180005a3b  dec     dword ptr [rax]
0x180005a3d  retn
```

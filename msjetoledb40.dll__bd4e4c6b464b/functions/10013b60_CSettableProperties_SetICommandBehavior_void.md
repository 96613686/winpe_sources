# CSettableProperties::SetICommandBehavior(void)

- ea: `0x10013b60`
- end: `0x10013b80`
- name: `?SetICommandBehavior@CSettableProperties@@QAEXXZ`
- size: `32`
- prototype: `void __thiscall(CSettableProperties *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10016040`

## callees

- `0x10013b60`

## pseudocode

```c
void __thiscall CSettableProperties::SetICommandBehavior(CSettableProperties *this)
{
  int v1; // eax
  int v2; // eax

  v1 = *((_DWORD *)this + 2);
  *((_DWORD *)this + 1) = 1;
  *(_DWORD *)(v1 + 36) = 1;
  v2 = *((_DWORD *)this + 3);
  if ( v2 )
    *(_DWORD *)(v2 + 36) = 1;
}

```

## disassembly

```asm
0x10013b60  mov     eax, [ecx+8]
0x10013b63  mov     dword ptr [ecx+4], 1
0x10013b6a  mov     dword ptr [eax+24h], 1
0x10013b71  mov     eax, [ecx+0Ch]
0x10013b74  test    eax, eax
0x10013b76  jz      short locret_10013B7F
0x10013b78  mov     dword ptr [eax+24h], 1
0x10013b7f  retn
```

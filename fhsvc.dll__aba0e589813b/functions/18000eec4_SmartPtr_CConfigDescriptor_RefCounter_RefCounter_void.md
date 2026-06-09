# SmartPtr<CConfigDescriptor>::RefCounter::~RefCounter(void)

- ea: `0x18000eec4`
- end: `0x18000eeda`
- name: `??1RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ`
- size: `22`
- prototype: `void *__fastcall(CConfigDescriptor **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004e50`

## callees

- `0x18000eec4`
- `0x18000ef64`

## pseudocode

```c
void *__fastcall SmartPtr<CConfigDescriptor>::RefCounter::~RefCounter(CConfigDescriptor **a1, unsigned int a2)
{
  CConfigDescriptor *v2; // rcx
  void *result; // rax

  v2 = *a1;
  if ( v2 )
    return CConfigDescriptor::`scalar deleting destructor'(v2, a2);
  return result;
}

```

## disassembly

```asm
0x18000eec4  sub     rsp, 28h
0x18000eec8  mov     rcx, [rcx]; this
0x18000eecb  test    rcx, rcx
0x18000eece  jz      short loc_18000EED5
0x18000eed0  call    ??_GCConfigDescriptor@@QEAAPEAXI@Z; CConfigDescriptor::`scalar deleting destructor'(uint)
0x18000eed5  add     rsp, 28h
0x18000eed9  retn
```

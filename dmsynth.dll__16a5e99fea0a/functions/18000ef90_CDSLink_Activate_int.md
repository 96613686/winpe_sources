# CDSLink::Activate(int)

- ea: `0x18000ef90`
- end: `0x18000ef9d`
- name: `?Activate@CDSLink@@UEAAJH@Z`
- size: `13`
- prototype: `__int64 __fastcall(CDSLink *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f010`
- `0x18000f650`

## pseudocode

```c
__int64 __fastcall CDSLink::Activate(CDSLink *this, int a2)
{
  if ( a2 )
    return CDSLink::Connect(this);
  else
    return CDSLink::Disconnect(this);
}

```

## disassembly

```asm
0x18000ef90  test    edx, edx
0x18000ef92  jnz     ?Connect@CDSLink@@AEAAJXZ; CDSLink::Connect(void)
0x18000ef98  jmp     ?Disconnect@CDSLink@@AEAAJXZ; CDSLink::Disconnect(void)
```

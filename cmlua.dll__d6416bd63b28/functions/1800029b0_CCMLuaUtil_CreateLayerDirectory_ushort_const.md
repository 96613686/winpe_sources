# CCMLuaUtil::CreateLayerDirectory(ushort const *)

- ea: `0x1800029b0`
- end: `0x1800029cb`
- name: `?CreateLayerDirectory@CCMLuaUtil@@UEAAJPEBG@Z`
- size: `27`
- prototype: `_BOOL8 __fastcall(CCMLuaUtil *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004630`

## pseudocode

```c
_BOOL8 __fastcall CCMLuaUtil::CreateLayerDirectory(CCMLuaUtil *this, unsigned __int16 *a2)
{
  return (unsigned int)CreateLayerDirectory(a2) == 0;
}

```

## disassembly

```asm
0x1800029b0  sub     rsp, 28h
0x1800029b4  mov     rcx, rdx; unsigned __int16 *
0x1800029b7  call    _CreateLayerDirectory
0x1800029bc  nop
0x1800029bd  xor     ecx, ecx
0x1800029bf  test    eax, eax
0x1800029c1  setz    cl
0x1800029c4  mov     eax, ecx
0x1800029c6  add     rsp, 28h
0x1800029ca  retn
```

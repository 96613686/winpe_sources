# CGhostWindow::GetState(void)

- ea: `0x180006bac`
- end: `0x180006bb0`
- name: `?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ`
- size: `4`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800061fc`
- `0x180006494`
- `0x180006784`
- `0x180006bb8`
- `0x1800073c0`
- `0x1800075e0`
- `0x1800083e8`
- `0x1800084c8`
- `0x1800086b8`

## pseudocode

```c
__int64 __fastcall CGhostWindow::GetState(__int64 a1)
{
  return *(unsigned int *)(a1 + 28);
}

```

## disassembly

```asm
0x180006bac  mov     eax, [rcx+1Ch]
0x180006baf  retn
```

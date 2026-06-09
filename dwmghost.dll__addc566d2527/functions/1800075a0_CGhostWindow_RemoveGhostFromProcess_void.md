# CGhostWindow::RemoveGhostFromProcess(void)

- ea: `0x1800075a0`
- end: `0x1800075c7`
- name: `?RemoveGhostFromProcess@CGhostWindow@@AEAAHXZ`
- size: `39`
- prototype: `__int64 __fastcall(CGhostWindow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005fe8`
- `0x1800061a4`

## callees

- `0x180009518`

## pseudocode

```c
_BOOL8 __fastcall CGhostWindow::RemoveGhostFromProcess(CGhostWindow *this, struct CGhostWindow *a2)
{
  *((_DWORD *)this + 8) = 0;
  CGhostProcess::RemoveGhostWindow(*((CGhostProcess **)this + 2), a2);
  return *((_DWORD *)this + 8) == 0;
}

```

## disassembly

```asm
0x1800075a0  push    rbx
0x1800075a2  sub     rsp, 20h
0x1800075a6  mov     rbx, rcx
0x1800075a9  mov     dword ptr [rcx+20h], 0
0x1800075b0  mov     rcx, [rcx+10h]; this
0x1800075b4  call    ?RemoveGhostWindow@CGhostProcess@@QEAAJPEAVCGhostWindow@@@Z; CGhostProcess::RemoveGhostWindow(CGhostWindow *)
0x1800075b9  xor     eax, eax
0x1800075bb  cmp     [rbx+20h], eax
0x1800075be  setz    al
0x1800075c1  add     rsp, 20h
0x1800075c5  pop     rbx
0x1800075c6  retn
```

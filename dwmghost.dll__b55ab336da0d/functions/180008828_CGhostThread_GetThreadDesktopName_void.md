# CGhostThread::GetThreadDesktopName(void)

- ea: `0x180008828`
- end: `0x18000882d`
- name: `?GetThreadDesktopName@CGhostThread@@QEAAPEBGXZ`
- size: `5`
- prototype: `const unsigned __int16 *__fastcall(CGhostThread *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180007d0c`

## pseudocode

```c
const unsigned __int16 *__fastcall CGhostThread::GetThreadDesktopName(CGhostThread *this)
{
  return (const unsigned __int16 *)*((_QWORD *)this + 9);
}

```

## disassembly

```asm
0x180008828  mov     rax, [rcx+48h]
0x18000882c  retn
```

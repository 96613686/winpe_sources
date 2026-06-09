# CGhostThread::s_ThreadProc(void *)

- ea: `0x180008cb0`
- end: `0x180008cd9`
- name: `?s_ThreadProc@CGhostThread@@CAKPEAX@Z`
- size: `41`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004dc4`
- `0x180008c10`

## pseudocode

```c
__int64 __fastcall CGhostThread::s_ThreadProc(CGhostThread *Parameter)
{
  unsigned int v2; // ebx

  v2 = CGhostThread::WorkerThreadProc(Parameter);
  CCountedObject::Release(Parameter);
  return v2;
}

```

## disassembly

```asm
0x180008cb0  mov     [rsp+arg_0], rbx
0x180008cb5  push    rdi
0x180008cb6  sub     rsp, 20h
0x180008cba  mov     rdi, rcx
0x180008cbd  call    ?WorkerThreadProc@CGhostThread@@AEAAKXZ; CGhostThread::WorkerThreadProc(void)
0x180008cc2  mov     rcx, rdi; this
0x180008cc5  mov     ebx, eax
0x180008cc7  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180008ccc  mov     eax, ebx
0x180008cce  mov     rbx, [rsp+28h+arg_0]
0x180008cd3  add     rsp, 20h
0x180008cd7  pop     rdi
0x180008cd8  retn
```

# CGhostThread::SetState(tagGHOSTTHREADSTATE)

- ea: `0x180008b00`
- end: `0x180008b31`
- name: `?SetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@W42@@Z`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008558`
- `0x180008834`
- `0x180008b38`
- `0x180008c10`

## callees

- `0x180009f60`
- `0x180009f70`

## pseudocode

```c
__int64 __fastcall CGhostThread::SetState(__int64 a1, int a2)
{
  unsigned int v4; // ebx

  CLock::Acquire((LPCRITICAL_SECTION)(a1 + 16));
  v4 = *(_DWORD *)(a1 + 56);
  *(_DWORD *)(a1 + 56) = a2;
  CLock::Release((LPCRITICAL_SECTION)(a1 + 16));
  return v4;
}

```

## disassembly

```asm
0x180008b00  push    rbx
0x180008b02  push    rbp
0x180008b03  push    rsi
0x180008b04  push    rdi
0x180008b05  sub     rsp, 28h
0x180008b09  mov     rsi, rcx
0x180008b0c  mov     ebp, edx
0x180008b0e  add     rcx, 10h; lpCriticalSection
0x180008b12  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180008b17  mov     ebx, [rsi+38h]
0x180008b1a  lea     rcx, [rsi+10h]; lpCriticalSection
0x180008b1e  mov     [rsi+38h], ebp
0x180008b21  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180008b26  mov     eax, ebx
0x180008b28  add     rsp, 28h
0x180008b2c  pop     rdi
0x180008b2d  pop     rsi
0x180008b2e  pop     rbp
0x180008b2f  pop     rbx
0x180008b30  retn
```

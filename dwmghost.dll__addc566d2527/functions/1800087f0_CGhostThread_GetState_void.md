# CGhostThread::GetState(void)

- ea: `0x1800087f0`
- end: `0x180008821`
- name: `?GetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@XZ`
- size: `49`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800083e8`
- `0x180008944`
- `0x180008970`
- `0x180008b38`
- `0x180008c10`

## callees

- `0x180009f60`
- `0x180009f70`

## pseudocode

```c
__int64 __fastcall CGhostThread::GetState(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v2; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  v2 = a1;
  CLock::Acquire((LPCRITICAL_SECTION)(a1 + 16));
  LODWORD(v2) = *(_DWORD *)(v2 + 56);
  CLock::Release(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800087f0  mov     [rsp+arg_0], rbx
0x1800087f5  push    rdi
0x1800087f6  sub     rsp, 20h
0x1800087fa  lea     rdi, [rcx+10h]
0x1800087fe  mov     rbx, rcx
0x180008801  mov     rcx, rdi; lpCriticalSection
0x180008804  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180008809  mov     ebx, [rbx+38h]
0x18000880c  mov     rcx, rdi; lpCriticalSection
0x18000880f  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180008814  mov     eax, ebx
0x180008816  mov     rbx, [rsp+28h+arg_0]
0x18000881b  add     rsp, 20h
0x18000881f  pop     rdi
0x180008820  retn
```

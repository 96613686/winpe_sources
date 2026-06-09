# CGhostProcess::HasErrorReportingStarted(void)

- ea: `0x1800092a8`
- end: `0x1800092d9`
- name: `?HasErrorReportingStarted@CGhostProcess@@QEAAHXZ`
- size: `49`
- prototype: `__int64 __fastcall(CGhostProcess *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006bb8`
- `0x1800073c0`
- `0x1800075e0`
- `0x18000a020`

## callees

- `0x180009f60`
- `0x180009f70`

## pseudocode

```c
__int64 __fastcall CGhostProcess::HasErrorReportingStarted(CGhostProcess *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  CGhostProcess *v2; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v2 = this;
  CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
  LODWORD(v2) = *((_DWORD *)v2 + 30);
  CLock::Release(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800092a8  mov     [rsp+arg_0], rbx
0x1800092ad  push    rdi
0x1800092ae  sub     rsp, 20h
0x1800092b2  lea     rdi, [rcx+10h]
0x1800092b6  mov     rbx, rcx
0x1800092b9  mov     rcx, rdi; lpCriticalSection
0x1800092bc  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x1800092c1  mov     ebx, [rbx+78h]
0x1800092c4  mov     rcx, rdi; lpCriticalSection
0x1800092c7  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x1800092cc  mov     eax, ebx
0x1800092ce  mov     rbx, [rsp+28h+arg_0]
0x1800092d3  add     rsp, 20h
0x1800092d7  pop     rdi
0x1800092d8  retn
```

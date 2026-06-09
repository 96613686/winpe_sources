# wil::details::shared_buffer::reset(void)

- ea: `0x180006134`
- end: `0x180006186`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003924`
- `0x1800056c8`
- `0x180006044`
- `0x180006190`

## callees

- `0x180006134`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006166`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006158`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006158`

## pseudocode

```c
void __fastcall wil::details::shared_buffer::reset(volatile signed __int32 **this)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rbx
  HANDLE ProcessHeap; // rax

  v2 = *this;
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = *this;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v3);
    }
    *this = 0;
    this[1] = 0;
  }
}

```

## disassembly

```asm
0x180006134  mov     [rsp+arg_0], rbx
0x180006139  push    rdi
0x18000613a  sub     rsp, 20h
0x18000613e  mov     rdi, rcx
0x180006141  mov     rcx, [rcx]
0x180006144  test    rcx, rcx
0x180006147  jz      short loc_18000617B
0x180006149  or      eax, 0FFFFFFFFh
0x18000614c  lock xadd [rcx], eax
0x180006150  cmp     eax, 1
0x180006153  jnz     short loc_18000616C
0x180006155  mov     rbx, [rdi]
0x180006158  call    cs:__imp_GetProcessHeap
0x18000615e  mov     r8, rbx; lpMem
0x180006161  xor     edx, edx; dwFlags
0x180006163  mov     rcx, rax; hHeap
0x180006166  call    cs:__imp_HeapFree
0x18000616c  mov     qword ptr [rdi], 0
0x180006173  mov     qword ptr [rdi+8], 0
0x18000617b  mov     rbx, [rsp+28h+arg_0]
0x180006180  add     rsp, 20h
0x180006184  pop     rdi
0x180006185  retn
```

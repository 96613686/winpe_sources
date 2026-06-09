# wil::details::shared_buffer::reset(void)

- ea: `0x1800085ac`
- end: `0x1800085fe`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000673c`
- `0x180007b88`
- `0x1800084bc`
- `0x180008610`

## callees

- `0x1800085ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800085de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800085de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085d0`

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
0x1800085ac  mov     [rsp+arg_0], rbx
0x1800085b1  push    rdi
0x1800085b2  sub     rsp, 20h
0x1800085b6  mov     rdi, rcx
0x1800085b9  mov     rcx, [rcx]
0x1800085bc  test    rcx, rcx
0x1800085bf  jz      short loc_1800085F3
0x1800085c1  or      eax, 0FFFFFFFFh
0x1800085c4  lock xadd [rcx], eax
0x1800085c8  cmp     eax, 1
0x1800085cb  jnz     short loc_1800085E4
0x1800085cd  mov     rbx, [rdi]
0x1800085d0  call    cs:__imp_GetProcessHeap
0x1800085d6  mov     r8, rbx; lpMem
0x1800085d9  xor     edx, edx; dwFlags
0x1800085db  mov     rcx, rax; hHeap
0x1800085de  call    cs:__imp_HeapFree
0x1800085e4  mov     qword ptr [rdi], 0
0x1800085eb  mov     qword ptr [rdi+8], 0
0x1800085f3  mov     rbx, [rsp+28h+arg_0]
0x1800085f8  add     rsp, 20h
0x1800085fc  pop     rdi
0x1800085fd  retn
```

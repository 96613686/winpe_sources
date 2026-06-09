# wil::details::shared_buffer::reset(void)

- ea: `0x18000a144`
- end: `0x18000a196`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006050`
- `0x180008ec8`
- `0x180009f58`
- `0x18000a1a0`

## callees

- `0x18000a144`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a168`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a168`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a176`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a176`

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
0x18000a144  mov     [rsp+arg_0], rbx
0x18000a149  push    rdi
0x18000a14a  sub     rsp, 20h
0x18000a14e  mov     rdi, rcx
0x18000a151  mov     rcx, [rcx]
0x18000a154  test    rcx, rcx
0x18000a157  jz      short loc_18000A18B
0x18000a159  or      eax, 0FFFFFFFFh
0x18000a15c  lock xadd [rcx], eax
0x18000a160  cmp     eax, 1
0x18000a163  jnz     short loc_18000A17C
0x18000a165  mov     rbx, [rdi]
0x18000a168  call    cs:__imp_GetProcessHeap
0x18000a16e  mov     r8, rbx; lpMem
0x18000a171  xor     edx, edx; dwFlags
0x18000a173  mov     rcx, rax; hHeap
0x18000a176  call    cs:__imp_HeapFree
0x18000a17c  mov     qword ptr [rdi], 0
0x18000a183  mov     qword ptr [rdi+8], 0
0x18000a18b  mov     rbx, [rsp+28h+arg_0]
0x18000a190  add     rsp, 20h
0x18000a194  pop     rdi
0x18000a195  retn
```

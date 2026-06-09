# wil::details::shared_buffer::reset(void)

- ea: `0x14000673c`
- end: `0x14000678e`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140004124`
- `0x140005bf0`
- `0x1400065e4`
- `0x1400067a0`
- `0x14000f5ac`

## callees

- `0x14000673c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006760`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006760`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000676e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000676e`

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
0x14000673c  mov     [rsp+arg_0], rbx
0x140006741  push    rdi
0x140006742  sub     rsp, 20h
0x140006746  mov     rdi, rcx
0x140006749  mov     rcx, [rcx]
0x14000674c  test    rcx, rcx
0x14000674f  jz      short loc_140006783
0x140006751  or      eax, 0FFFFFFFFh
0x140006754  lock xadd [rcx], eax
0x140006758  cmp     eax, 1
0x14000675b  jnz     short loc_140006774
0x14000675d  mov     rbx, [rdi]
0x140006760  call    cs:__imp_GetProcessHeap
0x140006766  mov     r8, rbx; lpMem
0x140006769  xor     edx, edx; dwFlags
0x14000676b  mov     rcx, rax; hHeap
0x14000676e  call    cs:__imp_HeapFree
0x140006774  mov     qword ptr [rdi], 0
0x14000677b  mov     qword ptr [rdi+8], 0
0x140006783  mov     rbx, [rsp+28h+arg_0]
0x140006788  add     rsp, 20h
0x14000678c  pop     rdi
0x14000678d  retn
```

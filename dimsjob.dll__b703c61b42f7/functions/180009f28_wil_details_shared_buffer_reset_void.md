# wil::details::shared_buffer::reset(void)

- ea: `0x180009f28`
- end: `0x180009f7a`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b0c`
- `0x180008ac8`
- `0x180009a28`
- `0x180009f80`

## callees

- `0x180009f28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f5a`

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
0x180009f28  mov     [rsp+arg_0], rbx
0x180009f2d  push    rdi
0x180009f2e  sub     rsp, 20h
0x180009f32  mov     rdi, rcx
0x180009f35  mov     rcx, [rcx]
0x180009f38  test    rcx, rcx
0x180009f3b  jz      short loc_180009F6F
0x180009f3d  or      eax, 0FFFFFFFFh
0x180009f40  lock xadd [rcx], eax
0x180009f44  cmp     eax, 1
0x180009f47  jnz     short loc_180009F60
0x180009f49  mov     rbx, [rdi]
0x180009f4c  call    cs:__imp_GetProcessHeap
0x180009f52  mov     r8, rbx; lpMem
0x180009f55  xor     edx, edx; dwFlags
0x180009f57  mov     rcx, rax; hHeap
0x180009f5a  call    cs:__imp_HeapFree
0x180009f60  mov     qword ptr [rdi], 0
0x180009f67  mov     qword ptr [rdi+8], 0
0x180009f6f  mov     rbx, [rsp+28h+arg_0]
0x180009f74  add     rsp, 20h
0x180009f78  pop     rdi
0x180009f79  retn
```

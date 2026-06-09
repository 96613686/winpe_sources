# wil::details::shared_buffer::reset(void)

- ea: `0x180005e44`
- end: `0x180005e96`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e34`
- `0x1800057c0`
- `0x180005e00`
- `0x180005ea0`

## callees

- `0x180005e44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e68`

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
0x180005e44  mov     [rsp+arg_0], rbx
0x180005e49  push    rdi
0x180005e4a  sub     rsp, 20h
0x180005e4e  mov     rdi, rcx
0x180005e51  mov     rcx, [rcx]
0x180005e54  test    rcx, rcx
0x180005e57  jz      short loc_180005E8B
0x180005e59  or      eax, 0FFFFFFFFh
0x180005e5c  lock xadd [rcx], eax
0x180005e60  cmp     eax, 1
0x180005e63  jnz     short loc_180005E7C
0x180005e65  mov     rbx, [rdi]
0x180005e68  call    cs:__imp_GetProcessHeap
0x180005e6e  mov     r8, rbx; lpMem
0x180005e71  xor     edx, edx; dwFlags
0x180005e73  mov     rcx, rax; hHeap
0x180005e76  call    cs:__imp_HeapFree
0x180005e7c  mov     qword ptr [rdi], 0
0x180005e83  mov     qword ptr [rdi+8], 0
0x180005e8b  mov     rbx, [rsp+28h+arg_0]
0x180005e90  add     rsp, 20h
0x180005e94  pop     rdi
0x180005e95  retn
```

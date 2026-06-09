# DhcpFree

- ea: `0x180001e30`
- end: `0x180001e63`
- name: `DhcpFree`
- size: `51`
- prototype: `BOOL __fastcall(LPVOID *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800016f0`
- `0x180001d30`
- `0x180004e10`
- `0x180005270`
- `0x180005b30`
- `0x180005ec0`
- `0x1800062f0`

## callees

- `0x180001e30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001e50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001e50`

## pseudocode

```c
BOOL __fastcall DhcpFree(LPVOID *a1)
{
  BOOL result; // eax

  if ( *a1 )
  {
    result = HeapFree(NtCurrentPeb()->ProcessHeap, 0, *a1);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001e30  push    rbx
0x180001e32  sub     rsp, 20h
0x180001e36  mov     r8, [rcx]; lpMem
0x180001e39  mov     rbx, rcx
0x180001e3c  test    r8, r8
0x180001e3f  jz      short loc_180001E5D
0x180001e41  mov     rcx, gs:60h
0x180001e4a  xor     edx, edx; dwFlags
0x180001e4c  mov     rcx, [rcx+30h]; hHeap
0x180001e50  call    cs:__imp_HeapFree
0x180001e56  mov     qword ptr [rbx], 0
0x180001e5d  add     rsp, 20h
0x180001e61  pop     rbx
0x180001e62  retn
```

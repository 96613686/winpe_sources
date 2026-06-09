# I_FreeReaderStates

- ea: `0x18000fe14`
- end: `0x18000fe73`
- name: `I_FreeReaderStates`
- size: `95`
- prototype: `BOOL __fastcall(_QWORD *lpMem, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003510`
- `0x180005830`

## callees

- `0x18000fe14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe62`

## pseudocode

```c
BOOL __fastcall I_FreeReaderStates(_QWORD *lpMem, int a2)
{
  int v2; // ebx
  void *v4; // r8
  BOOL result; // eax

  if ( lpMem )
  {
    v2 = a2;
    while ( v2 )
    {
      while ( 1 )
      {
        v4 = (void *)lpMem[8 * (unsigned __int64)(unsigned int)--v2];
        if ( !v4 )
          break;
        if ( !v2 )
          return HeapFree(hHeap, 0, lpMem);
        HeapFree(hHeap, 0, v4);
      }
    }
    return HeapFree(hHeap, 0, lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x18000fe14  test    rcx, rcx
0x18000fe17  jz      short locret_18000FE72
0x18000fe19  mov     [rsp+arg_0], rbx
0x18000fe1e  push    rdi
0x18000fe1f  sub     rsp, 20h
0x18000fe23  mov     ebx, edx
0x18000fe25  mov     rdi, rcx
0x18000fe28  test    edx, edx
0x18000fe2a  jz      short loc_18000FE56
0x18000fe2c  dec     ebx
0x18000fe2e  mov     eax, ebx
0x18000fe30  shl     rax, 6
0x18000fe34  mov     r8, [rax+rdi]; lpMem
0x18000fe38  test    r8, r8
0x18000fe3b  jz      short loc_18000FE52
0x18000fe3d  test    ebx, ebx
0x18000fe3f  jz      short loc_18000FE56
0x18000fe41  mov     rcx, cs:hHeap; hHeap
0x18000fe48  xor     edx, edx; dwFlags
0x18000fe4a  call    cs:__imp_HeapFree
0x18000fe50  jmp     short loc_18000FE2C
0x18000fe52  test    ebx, ebx
0x18000fe54  jnz     short loc_18000FE2C
0x18000fe56  mov     rcx, cs:hHeap; hHeap
0x18000fe5d  mov     r8, rdi; lpMem
0x18000fe60  xor     edx, edx; dwFlags
0x18000fe62  call    cs:__imp_HeapFree
0x18000fe68  mov     rbx, [rsp+28h+arg_0]
0x18000fe6d  add     rsp, 20h
0x18000fe71  pop     rdi
0x18000fe72  retn
```

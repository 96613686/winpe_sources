# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)

- ea: `0x180005b90`
- end: `0x180005bdd`
- name: `?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `77`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `29`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800015a0`
- `0x1800017e4`
- `0x180001d3c`
- `0x180002650`
- `0x180003840`
- `0x180003914`
- `0x180004000`
- `0x180004230`
- `0x180004990`
- `0x180004c10`
- `0x180005160`
- `0x180005df0`
- `0x180006de0`
- `0x1800087f0`
- `0x180008910`
- `0x180009120`
- `0x180009488`
- `0x180009d10`
- `0x18000c0f0`
- `0x18000d23c`
- `0x18000dd18`
- `0x180015d60`
- `0x180016250`
- `0x180016400`
- `0x1800165d0`
- `0x180017150`
- `0x180017186`
- `0x1800171aa`
- `0x1800171bc`

## callees

- `0x180005b90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ba5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ba5`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(
        __int64 a1)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  __int64 result; // rax

  v1 = *(void **)a1;
  if ( *(_QWORD *)a1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    result = 0;
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
  else
  {
    result = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005b90  mov     [rsp+arg_0], rbx
0x180005b95  push    rdi
0x180005b96  sub     rsp, 20h
0x180005b9a  mov     rdi, [rcx]
0x180005b9d  mov     rbx, rcx
0x180005ba0  test    rdi, rdi
0x180005ba3  jz      short loc_180005BD1
0x180005ba5  call    cs:__imp_GetProcessHeap
0x180005bab  mov     r8, rdi; lpMem
0x180005bae  xor     edx, edx; dwFlags
0x180005bb0  mov     rcx, rax; hHeap
0x180005bb3  call    cs:__imp_HeapFree
0x180005bb9  xor     eax, eax
0x180005bbb  mov     [rbx], rax
0x180005bbe  mov     [rbx+8], rax
0x180005bc2  mov     [rbx+10h], rax
0x180005bc6  mov     rbx, [rsp+28h+arg_0]
0x180005bcb  add     rsp, 20h
0x180005bcf  pop     rdi
0x180005bd0  retn
0x180005bd1  xor     eax, eax
0x180005bd3  mov     [rcx+8], rax
0x180005bd7  mov     [rcx+10h], rax
0x180005bdb  jmp     short loc_180005BC6
```

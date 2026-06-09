# CMFBaseStringT<char>::_FreeBuffer(void)

- ea: `0x1800a52a4`
- end: `0x1800a5307`
- name: `?_FreeBuffer@?$CMFBaseStringT@D@@IEAAXXZ`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a4464`
- `0x1800a51f0`

## callees

- `0x1800a52a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a52d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a52d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a52c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a52c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a52e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a52e3`

## pseudocode

```c
void __fastcall CMFBaseStringT<char>::_FreeBuffer(__int64 a1)
{
  void *v2; // rdi
  int v3; // eax
  HANDLE ProcessHeap; // rax

  if ( (*(_DWORD *)a1 & 1) == 0 )
  {
    v2 = *(void **)(a1 + 16);
    if ( v2 )
    {
      v3 = *(_DWORD *)a1 & 6;
      if ( v3 )
      {
        if ( v3 == 2 )
          CoTaskMemFree(*(LPVOID *)(a1 + 16));
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v2);
      }
    }
    *(_DWORD *)a1 &= 0xFFFFFFF9;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800a52a4  mov     [rsp+arg_0], rbx
0x1800a52a9  push    rdi
0x1800a52aa  sub     rsp, 20h
0x1800a52ae  mov     eax, [rcx]
0x1800a52b0  mov     rbx, rcx
0x1800a52b3  test    al, 1
0x1800a52b5  jnz     short loc_1800A52FC
0x1800a52b7  mov     rdi, [rcx+10h]
0x1800a52bb  test    rdi, rdi
0x1800a52be  jz      short loc_1800A52E9
0x1800a52c0  and     eax, 6
0x1800a52c3  jnz     short loc_1800A52DB
0x1800a52c5  call    cs:__imp_GetProcessHeap
0x1800a52cb  mov     r8, rdi; lpMem
0x1800a52ce  xor     edx, edx; dwFlags
0x1800a52d0  mov     rcx, rax; hHeap
0x1800a52d3  call    cs:__imp_HeapFree
0x1800a52d9  jmp     short loc_1800A52E9
0x1800a52db  cmp     eax, 2
0x1800a52de  jnz     short loc_1800A52E9
0x1800a52e0  mov     rcx, rdi; pv
0x1800a52e3  call    cs:__imp_CoTaskMemFree
0x1800a52e9  and     dword ptr [rbx], 0FFFFFFF9h
0x1800a52ec  mov     qword ptr [rbx+10h], 0
0x1800a52f4  mov     qword ptr [rbx+8], 0
0x1800a52fc  mov     rbx, [rsp+28h+arg_0]
0x1800a5301  add     rsp, 20h
0x1800a5305  pop     rdi
0x1800a5306  retn
```

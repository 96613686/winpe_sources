# CMFBaseStringT<ushort>::_FreeBuffer(void)

- ea: `0x180050d3c`
- end: `0x180050db2`
- name: `?_FreeBuffer@?$CMFBaseStringT@G@@IEAAXXZ`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004ed70`
- `0x180053f20`

## callees

- `0x180050d3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050d71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050d71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050d5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050d5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050d87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050d87`

## pseudocode

```c
void __fastcall CMFBaseStringT<unsigned short>::_FreeBuffer(__int64 a1)
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
0x180050d3c  mov     [rsp+arg_0], rbx
0x180050d41  push    rdi
0x180050d42  sub     rsp, 20h
0x180050d46  mov     eax, [rcx]
0x180050d48  mov     rbx, rcx
0x180050d4b  test    al, 1
0x180050d4d  jnz     short loc_180050DA6
0x180050d4f  mov     rdi, [rcx+10h]
0x180050d53  test    rdi, rdi
0x180050d56  jz      short loc_180050D93
0x180050d58  and     eax, 6
0x180050d5b  jnz     short loc_180050D7F
0x180050d5d  call    cs:__imp_GetProcessHeap
0x180050d64  nop     dword ptr [rax+rax+00h]
0x180050d69  mov     r8, rdi; lpMem
0x180050d6c  xor     edx, edx; dwFlags
0x180050d6e  mov     rcx, rax; hHeap
0x180050d71  call    cs:__imp_HeapFree
0x180050d78  nop     dword ptr [rax+rax+00h]
0x180050d7d  jmp     short loc_180050D93
0x180050d7f  cmp     eax, 2
0x180050d82  jnz     short loc_180050D93
0x180050d84  mov     rcx, rdi; pv
0x180050d87  call    cs:__imp_CoTaskMemFree
0x180050d8e  nop     dword ptr [rax+rax+00h]
0x180050d93  and     dword ptr [rbx], 0FFFFFFF9h
0x180050d96  mov     qword ptr [rbx+10h], 0
0x180050d9e  mov     qword ptr [rbx+8], 0
0x180050da6  mov     rbx, [rsp+28h+arg_0]
0x180050dab  add     rsp, 20h
0x180050daf  pop     rdi
0x180050db0  retn
```

# CMFBaseStringT<ushort>::_FreeBuffer(void)

- ea: `0x18001d7d4`
- end: `0x18001d837`
- name: `?_FreeBuffer@?$CMFBaseStringT@G@@IEAAXXZ`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d9bc`
- `0x18001d41c`

## callees

- `0x18001d7d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d813`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d7f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d7f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d803`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d803`

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
0x18001d7d4  mov     [rsp+arg_0], rbx
0x18001d7d9  push    rdi
0x18001d7da  sub     rsp, 20h
0x18001d7de  mov     eax, [rcx]
0x18001d7e0  mov     rbx, rcx
0x18001d7e3  test    al, 1
0x18001d7e5  jnz     short loc_18001D82C
0x18001d7e7  mov     rdi, [rcx+10h]
0x18001d7eb  test    rdi, rdi
0x18001d7ee  jz      short loc_18001D819
0x18001d7f0  and     eax, 6
0x18001d7f3  jnz     short loc_18001D80B
0x18001d7f5  call    cs:__imp_GetProcessHeap
0x18001d7fb  mov     r8, rdi; lpMem
0x18001d7fe  xor     edx, edx; dwFlags
0x18001d800  mov     rcx, rax; hHeap
0x18001d803  call    cs:__imp_HeapFree
0x18001d809  jmp     short loc_18001D819
0x18001d80b  cmp     eax, 2
0x18001d80e  jnz     short loc_18001D819
0x18001d810  mov     rcx, rdi; pv
0x18001d813  call    cs:__imp_CoTaskMemFree
0x18001d819  and     dword ptr [rbx], 0FFFFFFF9h
0x18001d81c  mov     qword ptr [rbx+10h], 0
0x18001d824  mov     qword ptr [rbx+8], 0
0x18001d82c  mov     rbx, [rsp+28h+arg_0]
0x18001d831  add     rsp, 20h
0x18001d835  pop     rdi
0x18001d836  retn
```

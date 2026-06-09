# CMFBaseStringT<ushort>::_FreeBuffer(void)

- ea: `0x18004eb70`
- end: `0x18004ebd3`
- name: `?_FreeBuffer@?$CMFBaseStringT@G@@IEAAXXZ`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004cd9c`
- `0x180051bcc`

## callees

- `0x18004eb70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004eb9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004eb9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004eb91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004eb91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ebaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ebaf`

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
0x18004eb70  mov     [rsp+arg_0], rbx
0x18004eb75  push    rdi
0x18004eb76  sub     rsp, 20h
0x18004eb7a  mov     eax, [rcx]
0x18004eb7c  mov     rbx, rcx
0x18004eb7f  test    al, 1
0x18004eb81  jnz     short loc_18004EBC8
0x18004eb83  mov     rdi, [rcx+10h]
0x18004eb87  test    rdi, rdi
0x18004eb8a  jz      short loc_18004EBB5
0x18004eb8c  and     eax, 6
0x18004eb8f  jnz     short loc_18004EBA7
0x18004eb91  call    cs:__imp_GetProcessHeap
0x18004eb97  mov     r8, rdi; lpMem
0x18004eb9a  xor     edx, edx; dwFlags
0x18004eb9c  mov     rcx, rax; hHeap
0x18004eb9f  call    cs:__imp_HeapFree
0x18004eba5  jmp     short loc_18004EBB5
0x18004eba7  cmp     eax, 2
0x18004ebaa  jnz     short loc_18004EBB5
0x18004ebac  mov     rcx, rdi; pv
0x18004ebaf  call    cs:__imp_CoTaskMemFree
0x18004ebb5  and     dword ptr [rbx], 0FFFFFFF9h
0x18004ebb8  mov     qword ptr [rbx+10h], 0
0x18004ebc0  mov     qword ptr [rbx+8], 0
0x18004ebc8  mov     rbx, [rsp+28h+arg_0]
0x18004ebcd  add     rsp, 20h
0x18004ebd1  pop     rdi
0x18004ebd2  retn
```

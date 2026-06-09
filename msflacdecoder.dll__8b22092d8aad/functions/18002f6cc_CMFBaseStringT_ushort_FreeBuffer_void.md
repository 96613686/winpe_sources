# CMFBaseStringT<ushort>::_FreeBuffer(void)

- ea: `0x18002f6cc`
- end: `0x18002f72f`
- name: `?_FreeBuffer@?$CMFBaseStringT@G@@IEAAXXZ`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a16c`
- `0x18003f230`

## callees

- `0x18002f6cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f70b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f70b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f6ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f6ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f6fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f6fb`

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
0x18002f6cc  mov     [rsp+arg_0], rbx
0x18002f6d1  push    rdi
0x18002f6d2  sub     rsp, 20h
0x18002f6d6  mov     eax, [rcx]
0x18002f6d8  mov     rbx, rcx
0x18002f6db  test    al, 1
0x18002f6dd  jnz     short loc_18002F724
0x18002f6df  mov     rdi, [rcx+10h]
0x18002f6e3  test    rdi, rdi
0x18002f6e6  jz      short loc_18002F711
0x18002f6e8  and     eax, 6
0x18002f6eb  jnz     short loc_18002F703
0x18002f6ed  call    cs:__imp_GetProcessHeap
0x18002f6f3  mov     r8, rdi; lpMem
0x18002f6f6  xor     edx, edx; dwFlags
0x18002f6f8  mov     rcx, rax; hHeap
0x18002f6fb  call    cs:__imp_HeapFree
0x18002f701  jmp     short loc_18002F711
0x18002f703  cmp     eax, 2
0x18002f706  jnz     short loc_18002F711
0x18002f708  mov     rcx, rdi; pv
0x18002f70b  call    cs:__imp_CoTaskMemFree
0x18002f711  and     dword ptr [rbx], 0FFFFFFF9h
0x18002f714  mov     qword ptr [rbx+10h], 0
0x18002f71c  mov     qword ptr [rbx+8], 0
0x18002f724  mov     rbx, [rsp+28h+arg_0]
0x18002f729  add     rsp, 20h
0x18002f72d  pop     rdi
0x18002f72e  retn
```

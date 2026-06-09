# CMFBaseStringT<char>::_FreeBuffer(void)

- ea: `0x1800487f4`
- end: `0x18004886a`
- name: `?_FreeBuffer@?$CMFBaseStringT@D@@IEAAXXZ`
- size: `118`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023f20`
- `0x18003e190`
- `0x18007662c`

## callees

- `0x1800487f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004883f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004883f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048829`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048815`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048815`

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
0x1800487f4  mov     [rsp+arg_0], rbx
0x1800487f9  push    rdi
0x1800487fa  sub     rsp, 20h
0x1800487fe  mov     eax, [rcx]
0x180048800  mov     rbx, rcx
0x180048803  test    al, 1
0x180048805  jnz     short loc_18004885E
0x180048807  mov     rdi, [rcx+10h]
0x18004880b  test    rdi, rdi
0x18004880e  jz      short loc_18004884B
0x180048810  and     eax, 6
0x180048813  jnz     short loc_180048837
0x180048815  call    cs:__imp_GetProcessHeap
0x18004881c  nop     dword ptr [rax+rax+00h]
0x180048821  mov     r8, rdi; lpMem
0x180048824  xor     edx, edx; dwFlags
0x180048826  mov     rcx, rax; hHeap
0x180048829  call    cs:__imp_HeapFree
0x180048830  nop     dword ptr [rax+rax+00h]
0x180048835  jmp     short loc_18004884B
0x180048837  cmp     eax, 2
0x18004883a  jnz     short loc_18004884B
0x18004883c  mov     rcx, rdi; pv
0x18004883f  call    cs:__imp_CoTaskMemFree
0x180048846  nop     dword ptr [rax+rax+00h]
0x18004884b  and     dword ptr [rbx], 0FFFFFFF9h
0x18004884e  mov     qword ptr [rbx+10h], 0
0x180048856  mov     qword ptr [rbx+8], 0
0x18004885e  mov     rbx, [rsp+28h+arg_0]
0x180048863  add     rsp, 20h
0x180048867  pop     rdi
0x180048868  retn
```

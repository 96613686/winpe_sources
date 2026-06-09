# CreateCompression

- ea: `0x1800068d0`
- end: `0x18000692c`
- name: `CreateCompression`
- size: `92`
- prototype: `HRESULT __stdcall(PVOID *context, ULONG reserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800059b8`
- `0x1800068d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800068ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800068ee`

## pseudocode

```c
HRESULT __stdcall CreateCompression(PVOID *context, ULONG reserved)
{
  char v2; // di
  LPVOID v4; // rax

  v2 = reserved;
  v4 = HeapAlloc(g_hHeap, 0, 0x88u);
  *context = v4;
  if ( !v4 )
    return -2147024882;
  *((_QWORD *)v4 + 10) = 0;
  *((_QWORD *)v4 + 11) = 0;
  *((_QWORD *)v4 + 12) = 0;
  *((_DWORD *)v4 + 29) = v2 & 1;
  InternalResetCompression(v4);
  return 0;
}

```

## disassembly

```asm
0x1800068d0  mov     [rsp+arg_0], rbx
0x1800068d5  push    rdi
0x1800068d6  sub     rsp, 20h
0x1800068da  mov     edi, edx
0x1800068dc  mov     rbx, rcx
0x1800068df  mov     rcx, cs:g_hHeap; hHeap
0x1800068e6  xor     edx, edx; dwFlags
0x1800068e8  mov     r8d, 88h; dwBytes
0x1800068ee  call    cs:__imp_HeapAlloc
0x1800068f4  xor     ecx, ecx
0x1800068f6  mov     [rbx], rax
0x1800068f9  test    rax, rax
0x1800068fc  jnz     short loc_180006905
0x1800068fe  mov     eax, 8007000Eh
0x180006903  jmp     short loc_180006921
0x180006905  mov     [rax+50h], rcx
0x180006909  and     edi, 1
0x18000690c  mov     [rax+58h], rcx
0x180006910  mov     [rax+60h], rcx
0x180006914  mov     rcx, rax
0x180006917  mov     [rax+74h], edi
0x18000691a  call    InternalResetCompression
0x18000691f  xor     eax, eax
0x180006921  mov     rbx, [rsp+28h+arg_0]
0x180006926  add     rsp, 20h
0x18000692a  pop     rdi
0x18000692b  retn
```

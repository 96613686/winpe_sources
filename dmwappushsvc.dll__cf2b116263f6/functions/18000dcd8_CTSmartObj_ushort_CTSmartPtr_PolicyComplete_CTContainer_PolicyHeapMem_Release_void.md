# CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)

- ea: `0x18000dcd8`
- end: `0x18000dd07`
- name: `?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ`
- size: `47`
- prototype: `void __fastcall(void **)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eff0`
- `0x18000f0ec`
- `0x180010220`
- `0x1800109f8`
- `0x180010ce4`
- `0x180010ed4`
- `0x180010fd8`

## callees

- `0x18000dcd8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dcfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dcfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dced`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dced`

## pseudocode

```c
void __fastcall CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void **a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x18000dcd8  push    rbx
0x18000dcda  sub     rsp, 20h
0x18000dcde  mov     rbx, [rcx]
0x18000dce1  mov     qword ptr [rcx], 0
0x18000dce8  test    rbx, rbx
0x18000dceb  jz      short loc_18000DD01
0x18000dced  call    cs:__imp_GetProcessHeap
0x18000dcf3  mov     r8, rbx; lpMem
0x18000dcf6  xor     edx, edx; dwFlags
0x18000dcf8  mov     rcx, rax; hHeap
0x18000dcfb  call    cs:__imp_HeapFree
0x18000dd01  add     rsp, 20h
0x18000dd05  pop     rbx
0x18000dd06  retn
```

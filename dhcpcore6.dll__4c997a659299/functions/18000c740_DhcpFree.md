# DhcpFree

- ea: `0x18000c740`
- end: `0x18000c77a`
- name: `DhcpFree`
- size: `58`
- prototype: `BOOL __fastcall(LPVOID *)`
- caller_count: `75`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034c8`
- `0x180003cc0`
- `0x180005014`
- `0x180005200`
- `0x180005e8c`
- `0x1800062e8`
- `0x180006468`
- `0x18000678c`
- `0x180007344`
- `0x18000812c`
- `0x180008f80`
- `0x180009520`
- `0x18000bb2c`
- `0x18000bdd4`
- `0x18000c508`
- `0x18000c558`
- `0x18000cabc`
- `0x180010088`
- `0x180010fd4`
- `0x1800128dc`
- `0x180014070`
- `0x180014590`
- `0x180014e18`
- `0x1800152b8`
- `0x18001564c`
- `0x1800157f4`
- `0x180016350`
- `0x180016658`
- `0x180016adc`
- `0x180016db0`
- `0x180016ea0`
- `0x180016ed0`
- `0x180016f14`
- `0x180016f48`
- `0x180016f8c`
- `0x180017bc4`
- `0x180018740`
- `0x180018864`
- `0x180018d74`
- `0x180019250`
- `0x1800192e4`
- `0x18001b314`
- `0x18001dabc`
- `0x18001dc84`
- `0x18001de50`
- `0x18001dfb4`
- `0x18001e060`
- `0x180020c1c`
- `0x180020d50`
- `0x180021150`

## callees

- `0x18000c740`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c760`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c760`

## pseudocode

```c
BOOL __fastcall DhcpFree(LPVOID *a1)
{
  BOOL result; // eax

  if ( *a1 )
  {
    result = HeapFree(NtCurrentPeb()->ProcessHeap, 0, *a1);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c740  push    rbx
0x18000c742  sub     rsp, 20h
0x18000c746  mov     r8, [rcx]; lpMem
0x18000c749  mov     rbx, rcx
0x18000c74c  test    r8, r8
0x18000c74f  jz      short loc_18000C773
0x18000c751  mov     rcx, gs:60h
0x18000c75a  xor     edx, edx; dwFlags
0x18000c75c  mov     rcx, [rcx+30h]; hHeap
0x18000c760  call    cs:__imp_HeapFree
0x18000c767  nop     dword ptr [rax+rax+00h]
0x18000c76c  mov     qword ptr [rbx], 0
0x18000c773  add     rsp, 20h
0x18000c777  pop     rbx
0x18000c778  retn
```

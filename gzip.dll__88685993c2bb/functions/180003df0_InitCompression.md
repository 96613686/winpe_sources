# InitCompression

- ea: `0x180003df0`
- end: `0x180003e28`
- name: `InitCompression`
- size: `56`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003df0`
- `0x180003e30`
- `0x180003f30`
- `0x180003ff0`
- `0x180004ee0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e19`

## pseudocode

```c
HRESULT __stdcall InitCompression()
{
  if ( !g_hHeap )
    g_hHeap = GetProcessHeap();
  GenerateSlotTables();
  InitStaticBlock();
  GenerateStaticEncodingTables();
  FastEncoderGenerateDynamicTreeEncoding();
  return 0;
}

```

## disassembly

```asm
0x180003df0  sub     rsp, 28h
0x180003df4  cmp     cs:g_hHeap, 0
0x180003dfc  jz      short loc_180003E19
0x180003dfe  call    GenerateSlotTables
0x180003e03  call    InitStaticBlock
0x180003e08  call    GenerateStaticEncodingTables
0x180003e0d  call    FastEncoderGenerateDynamicTreeEncoding
0x180003e12  xor     eax, eax
0x180003e14  add     rsp, 28h
0x180003e18  retn
0x180003e19  call    cs:__imp_GetProcessHeap
0x180003e1f  mov     cs:g_hHeap, rax
0x180003e26  jmp     short loc_180003DFE
```

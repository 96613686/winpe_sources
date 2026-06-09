# com_ptr<uchar>::Clear(void)

- ea: `0x180006c0c`
- end: `0x180006c30`
- name: `?Clear@?$com_ptr@E@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(void **)`
- caller_count: `20`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005ec8`
- `0x1800067cc`
- `0x180007fe0`
- `0x18000d430`
- `0x18000d6e0`
- `0x18000d9c0`
- `0x18000dd50`
- `0x18000df60`
- `0x18000e250`
- `0x18001eb30`
- `0x18001ede0`
- `0x18001efa0`
- `0x18001f7e0`
- `0x18001f990`
- `0x18001fb30`
- `0x180021770`
- `0x1800287c0`
- `0x180028b60`
- `0x180028ec0`
- `0x180031e31`

## callees

- `0x180006c0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c1d`

## pseudocode

```c
void __fastcall com_ptr<unsigned char>::Clear(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180006c0c  push    rbx
0x180006c0e  sub     rsp, 20h
0x180006c12  mov     rbx, rcx
0x180006c15  mov     rcx, [rcx]; pv
0x180006c18  test    rcx, rcx
0x180006c1b  jz      short loc_180006C2A
0x180006c1d  call    cs:__imp_CoTaskMemFree
0x180006c23  mov     qword ptr [rbx], 0
0x180006c2a  add     rsp, 20h
0x180006c2e  pop     rbx
0x180006c2f  retn
```

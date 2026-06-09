# TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)

- ea: `0x1800040b4`
- end: `0x1800040cb`
- name: `??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `10`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000458c`
- `0x180004694`
- `0x1800070d4`
- `0x1800071ec`
- `0x180009f54`
- `0x1800121d0`
- `0x180027020`
- `0x18002d637`
- `0x18002d649`
- `0x18002d65b`

## callees

- `0x1800040b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040c0`

## pseudocode

```c
void __fastcall TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x1800040b4  sub     rsp, 28h
0x1800040b8  mov     rcx, [rcx]; pv
0x1800040bb  test    rcx, rcx
0x1800040be  jz      short loc_1800040C6
0x1800040c0  call    cs:__imp_CoTaskMemFree
0x1800040c6  add     rsp, 28h
0x1800040ca  retn
```

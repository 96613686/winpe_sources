# TSimpleDeallocator<uchar *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<uchar *,void,void *,&CoTaskMemFree(void *)>(void)

- ea: `0x18000563c`
- end: `0x18000565a`
- name: `??1?$TSimpleDeallocator@PEAEXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013dbf`
- `0x1800141a0`
- `0x1800141d6`
- `0x1800141e8`
- `0x18001420c`

## callees

- `0x18000563c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005648`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005648`

## pseudocode

```c
void __fastcall TSimpleDeallocator<unsigned char *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned char *,void,void *,&void CoTaskMemFree(void *)>(
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
0x18000563c  sub     rsp, 28h
0x180005640  mov     rcx, [rcx]; pv
0x180005643  test    rcx, rcx
0x180005646  jz      short loc_180005654
0x180005648  call    cs:__imp_CoTaskMemFree
0x18000564f  nop     dword ptr [rax+rax+00h]
0x180005654  add     rsp, 28h
0x180005658  retn
```

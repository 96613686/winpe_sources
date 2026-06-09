# com_ptr<uchar>::Clear(void)

- ea: `0x180005370`
- end: `0x180005394`
- name: `?Clear@?$com_ptr@E@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(void **)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004de8`
- `0x1800052f4`
- `0x180005d30`
- `0x180018020`
- `0x1800183d0`
- `0x180018740`

## callees

- `0x180005370`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005381`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005381`

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
0x180005370  push    rbx
0x180005372  sub     rsp, 20h
0x180005376  mov     rbx, rcx
0x180005379  mov     rcx, [rcx]; pv
0x18000537c  test    rcx, rcx
0x18000537f  jz      short loc_18000538E
0x180005381  call    cs:__imp_CoTaskMemFree
0x180005387  mov     qword ptr [rbx], 0
0x18000538e  add     rsp, 20h
0x180005392  pop     rbx
0x180005393  retn
```

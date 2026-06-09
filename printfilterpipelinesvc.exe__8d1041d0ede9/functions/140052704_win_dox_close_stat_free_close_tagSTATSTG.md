# win_dox::close_stat_free::close(tagSTATSTG * *)

- ea: `0x140052704`
- end: `0x140052730`
- name: `?close@close_stat_free@win_dox@@SAXPEAPEAUtagSTATSTG@@@Z`
- size: `44`
- prototype: `void __fastcall(struct tagSTATSTG **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140052020`
- `0x140052120`

## callees

- `0x140046340`
- `0x140052704`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052718`

## pseudocode

```c
void __fastcall win_dox::close_stat_free::close(struct tagSTATSTG **a1)
{
  void *v2; // rcx

  v2 = *(void **)*a1;
  if ( v2 )
    CoTaskMemFree(v2);
  operator delete(*a1);
}

```

## disassembly

```asm
0x140052704  push    rbx
0x140052706  sub     rsp, 20h
0x14005270a  mov     rax, [rcx]
0x14005270d  mov     rbx, rcx
0x140052710  mov     rcx, [rax]; pv
0x140052713  test    rcx, rcx
0x140052716  jz      short loc_14005271E
0x140052718  call    cs:__imp_CoTaskMemFree
0x14005271e  mov     rcx, [rbx]; Block
0x140052721  mov     edx, 50h ; 'P'
0x140052726  add     rsp, 20h
0x14005272a  pop     rbx
0x14005272b  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```

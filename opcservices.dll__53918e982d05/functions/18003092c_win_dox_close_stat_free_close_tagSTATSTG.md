# win_dox::close_stat_free::close(tagSTATSTG * *)

- ea: `0x18003092c`
- end: `0x180030955`
- name: `?close@close_stat_free@win_dox@@SAXPEAPEAUtagSTATSTG@@@Z`
- size: `41`
- prototype: `void __fastcall(struct tagSTATSTG **)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002fc20`
- `0x18002fe30`
- `0x1800301c0`
- `0x180030900`

## callees

- `0x18003092c`
- `0x1800cd1c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003094d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003094d`

## pseudocode

```c
void __fastcall win_dox::close_stat_free::close(struct tagSTATSTG **a1)
{
  LPOLESTR pwcsName; // rcx

  pwcsName = (*a1)->pwcsName;
  if ( pwcsName )
    CoTaskMemFree(pwcsName);
  operator delete(*a1);
}

```

## disassembly

```asm
0x18003092c  push    rbx
0x18003092e  sub     rsp, 20h
0x180030932  mov     rax, [rcx]
0x180030935  mov     rbx, rcx
0x180030938  mov     rcx, [rax]; pv
0x18003093b  test    rcx, rcx
0x18003093e  jnz     short loc_18003094D
0x180030940  mov     rcx, [rbx]; Block
0x180030943  add     rsp, 20h
0x180030947  pop     rbx
0x180030948  jmp     ??3@YAXPEAX@Z; operator delete(void *)
0x18003094d  call    cs:__imp_CoTaskMemFree
0x180030953  jmp     short loc_180030940
```

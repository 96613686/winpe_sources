# P<List<CNsUriNode,0>>::~P<List<CNsUriNode,0>>(void)

- ea: `0x180020220`
- end: `0x180020238`
- name: `??1?$P@V?$List@VCNsUriNode@@$0A@@@@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020488`
- `0x180025433`

## callees

- `0x180020220`

## import_xrefs

- `msvcrt!free` at `0x18002022c`
- `msvcrt!free` at `0x18002022c`

## pseudocode

```c
void __fastcall P<List<CNsUriNode,0>>::~P<List<CNsUriNode,0>>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    free(v1);
}

```

## disassembly

```asm
0x180020220  sub     rsp, 28h
0x180020224  mov     rcx, [rcx]; Block
0x180020227  test    rcx, rcx
0x18002022a  jz      short loc_180020233
0x18002022c  call    cs:__imp_free
0x180020232  nop
0x180020233  add     rsp, 28h
0x180020237  retn
```

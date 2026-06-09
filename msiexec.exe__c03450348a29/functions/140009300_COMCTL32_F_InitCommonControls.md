# COMCTL32::F_InitCommonControls

- ea: `0x140009300`
- end: `0x14000932d`
- name: `COMCTL32::F_InitCommonControls`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140008d60`
- `0x140009300`
- `0x14000a010`

## string_xrefs

- `0x14000930b`: `InitCommonControls`

## pseudocode

```c
__int64 (*COMCTL32::F_InitCommonControls())(void)
{
  __int64 (*result)(void); // rax

  result = Bind_COMCTL32("InitCommonControls", &COMCTL32::InitCommonControls);
  if ( result )
    return (__int64 (*)(void))COMCTL32::InitCommonControls();
  return result;
}

```

## disassembly

```asm
0x140009300  sub     rsp, 28h
0x140009304  lea     rdx, ?InitCommonControls@COMCTL32@@3P6AXXZEA; __int64 (**)(void)
0x14000930b  lea     rcx, aInitcommoncont; "InitCommonControls"
0x140009312  call    ?Bind_COMCTL32@@YAP6A_JXZPEBDPEAP6A_JXZ@Z; Bind_COMCTL32(char const *,__int64 (**)(void))
0x140009317  test    rax, rax
0x14000931a  jz      short loc_140009328
0x14000931c  mov     rax, cs:?InitCommonControls@COMCTL32@@3P6AXXZEA; void (*COMCTL32::InitCommonControls)(void)
0x140009323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009328  add     rsp, 28h
0x14000932c  retn
```

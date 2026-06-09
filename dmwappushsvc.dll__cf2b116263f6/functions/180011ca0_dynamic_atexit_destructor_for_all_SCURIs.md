# _dynamic_atexit_destructor_for__all_SCURIs__

- ea: `0x180011ca0`
- end: `0x180011cf1`
- name: `_dynamic_atexit_destructor_for__all_SCURIs__`
- size: `81`
- prototype: `void()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002a9c`
- `0x180006f2c`
- `0x180011ca0`

## pseudocode

```c
void dynamic_atexit_destructor_for__all_SCURIs__()
{
  if ( all_SCURIs )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<SCURI>>>(all_SCURIs, xmmword_18001C760);
    std::_Deallocate<16>(
      (_QWORD *)all_SCURIs,
      (*((_QWORD *)&xmmword_18001C760 + 1) - all_SCURIs) & 0xFFFFFFFFFFFFFFF0uLL);
    all_SCURIs = 0;
    xmmword_18001C760 = 0;
  }
}

```

## disassembly

```asm
0x180011ca0  sub     rsp, 28h
0x180011ca4  mov     rcx, cs:?all_SCURIs@@3V?$vector@V?$shared_ptr@VSCURI@@@std@@V?$allocator@V?$shared_ptr@VSCURI@@@std@@@2@@std@@A; std::vector<std::shared_ptr<SCURI>> all_SCURIs
0x180011cab  test    rcx, rcx
0x180011cae  jz      short loc_180011CEC
0x180011cb0  mov     rdx, qword ptr cs:xmmword_18001C760
0x180011cb7  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VSCURI@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VSCURI@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VSCURI@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<SCURI>>>(std::shared_ptr<SCURI> *,std::shared_ptr<SCURI> * const,std::allocator<std::shared_ptr<SCURI>> &)
0x180011cbc  mov     rcx, cs:?all_SCURIs@@3V?$vector@V?$shared_ptr@VSCURI@@@std@@V?$allocator@V?$shared_ptr@VSCURI@@@std@@@2@@std@@A; std::vector<std::shared_ptr<SCURI>> all_SCURIs
0x180011cc3  mov     rdx, qword ptr cs:xmmword_18001C760+8
0x180011cca  sub     rdx, rcx
0x180011ccd  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180011cd1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011cd6  xorps   xmm0, xmm0
0x180011cd9  mov     cs:?all_SCURIs@@3V?$vector@V?$shared_ptr@VSCURI@@@std@@V?$allocator@V?$shared_ptr@VSCURI@@@std@@@2@@std@@A, 0; std::vector<std::shared_ptr<SCURI>> all_SCURIs
0x180011ce4  movdqu  cs:xmmword_18001C760, xmm0
0x180011cec  add     rsp, 28h
0x180011cf0  retn
```

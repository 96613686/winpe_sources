# std::unique_ptr<ProviderIndexAndPairingID,std::default_delete<ProviderIndexAndPairingID>>::~unique_ptr<ProviderIndexAndPairingID,std::default_delete<ProviderIndexAndPairingID>>(void)

- ea: `0x18000871c`
- end: `0x180008732`
- name: `??1?$unique_ptr@UProviderIndexAndPairingID@@U?$default_delete@UProviderIndexAndPairingID@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001cfb8`
- `0x18001d7cf`

## callees

- `0x1800014d0`
- `0x18000871c`

## pseudocode

```c
void __fastcall std::unique_ptr<ProviderIndexAndPairingID>::~unique_ptr<ProviderIndexAndPairingID>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000871c  sub     rsp, 28h
0x180008720  mov     rcx, [rcx]; Block
0x180008723  test    rcx, rcx
0x180008726  jz      short loc_18000872D
0x180008728  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000872d  add     rsp, 28h
0x180008731  retn
```

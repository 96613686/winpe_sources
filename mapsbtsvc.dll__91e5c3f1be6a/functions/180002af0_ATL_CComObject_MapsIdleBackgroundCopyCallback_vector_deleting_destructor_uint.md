# ATL::CComObject<MapsIdleBackgroundCopyCallback>::`vector deleting destructor'(uint)

- ea: `0x180002af0`
- end: `0x180002b1f`
- name: `??_E?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001e54`
- `0x180002a60`
- `0x180002af0`

## pseudocode

```c
void *__fastcall ATL::CComObject<MapsIdleBackgroundCopyCallback>::`vector deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<MapsIdleBackgroundCopyCallback>::~CComObject<MapsIdleBackgroundCopyCallback>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002af0  mov     [rsp+arg_0], rbx
0x180002af5  push    rdi
0x180002af6  sub     rsp, 20h
0x180002afa  mov     ebx, edx
0x180002afc  mov     rdi, rcx
0x180002aff  call    ??1?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@UEAA@XZ; ATL::CComObject<MapsIdleBackgroundCopyCallback>::~CComObject<MapsIdleBackgroundCopyCallback>(void)
0x180002b04  test    bl, 1
0x180002b07  jz      short loc_180002B11
0x180002b09  mov     rcx, rdi; Block
0x180002b0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002b11  mov     rbx, [rsp+28h+arg_0]
0x180002b16  mov     rax, rdi
0x180002b19  add     rsp, 20h
0x180002b1d  pop     rdi
0x180002b1e  retn
```

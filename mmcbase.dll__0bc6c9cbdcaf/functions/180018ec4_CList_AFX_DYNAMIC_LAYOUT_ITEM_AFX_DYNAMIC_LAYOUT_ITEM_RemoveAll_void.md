# CList<AFX_DYNAMIC_LAYOUT_ITEM *,AFX_DYNAMIC_LAYOUT_ITEM *>::RemoveAll(void)

- ea: `0x180018ec4`
- end: `0x180018f03`
- name: `?RemoveAll@?$CList@PEAUAFX_DYNAMIC_LAYOUT_ITEM@@PEAU1@@@QEAAXXZ`
- size: `63`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018238`
- `0x1800182d0`
- `0x180018ae4`
- `0x180018da0`

## import_xrefs

- `MFC42u!__imp_?FreeDataChain@CPlex@@QEAAXXZ` at `0x180018eef`
- `MFC42u!__imp_?FreeDataChain@CPlex@@QEAAXXZ` at `0x180018eef`

## pseudocode

```c
void __fastcall CList<AFX_DYNAMIC_LAYOUT_ITEM *,AFX_DYNAMIC_LAYOUT_ITEM *>::RemoveAll(__int64 a1)
{
  *(_DWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = 0;
  CPlex::FreeDataChain(*(CPlex **)(a1 + 32));
  *(_QWORD *)(a1 + 32) = 0;
}

```

## disassembly

```asm
0x180018ec4  push    rbx
0x180018ec6  sub     rsp, 20h
0x180018eca  mov     rbx, rcx
0x180018ecd  mov     dword ptr [rcx+10h], 0
0x180018ed4  mov     qword ptr [rcx+18h], 0
0x180018edc  mov     qword ptr [rcx+8], 0
0x180018ee4  mov     qword ptr [rcx], 0
0x180018eeb  mov     rcx, [rcx+20h]
0x180018eef  call    cs:__imp_?FreeDataChain@CPlex@@QEAAXXZ; CPlex::FreeDataChain(void)
0x180018ef5  mov     qword ptr [rbx+20h], 0
0x180018efd  add     rsp, 20h
0x180018f01  pop     rbx
0x180018f02  retn
```

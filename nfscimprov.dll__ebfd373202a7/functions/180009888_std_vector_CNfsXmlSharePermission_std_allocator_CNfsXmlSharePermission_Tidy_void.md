# std::vector<CNfsXmlSharePermission *,std::allocator<CNfsXmlSharePermission *>>::_Tidy(void)

- ea: `0x180009888`
- end: `0x1800098bc`
- name: `?_Tidy@?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@std@@IEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x18001cee8`
- `0x18001cf14`
- `0x18001cf20`
- `0x180027a2c`
- `0x180028338`
- `0x180036164`
- `0x180036952`
- `0x180036a18`

## callees

- `0x180009888`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009899`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009899`

## pseudocode

```c
void __fastcall std::vector<CNfsXmlSharePermission *>::_Tidy(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180009888  push    rbx
0x18000988a  sub     rsp, 20h
0x18000988e  mov     rbx, rcx
0x180009891  mov     rcx, [rcx]
0x180009894  test    rcx, rcx
0x180009897  jz      short loc_1800098B6
0x180009899  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000989f  mov     qword ptr [rbx], 0
0x1800098a6  mov     qword ptr [rbx+8], 0
0x1800098ae  mov     qword ptr [rbx+10h], 0
0x1800098b6  add     rsp, 20h
0x1800098ba  pop     rbx
0x1800098bb  retn
```

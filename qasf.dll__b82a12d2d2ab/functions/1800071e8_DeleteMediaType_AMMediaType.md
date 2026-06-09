# DeleteMediaType(_AMMediaType *)

- ea: `0x1800071e8`
- end: `0x180007209`
- name: `?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z`
- size: `33`
- prototype: `void __fastcall(struct _AMMediaType *pv)`
- caller_count: `14`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003768`
- `0x180003984`
- `0x180006510`
- `0x180006630`
- `0x1800083d0`
- `0x1800126e0`
- `0x180013a50`
- `0x180015c64`
- `0x180016020`
- `0x18001657c`
- `0x180018750`
- `0x180018f10`
- `0x180019250`
- `0x18001a600`

## callees

- `0x1800071e8`
- `0x180007210`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800071fd`
- `ole32!CoTaskMemFree` at `0x1800071fd`

## pseudocode

```c
void __fastcall DeleteMediaType(struct _AMMediaType *pv)
{
  if ( pv )
  {
    FreeMediaType(pv);
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x1800071e8  test    rcx, rcx
0x1800071eb  jz      short locret_180007208
0x1800071ed  push    rbx
0x1800071ee  sub     rsp, 20h
0x1800071f2  mov     rbx, rcx
0x1800071f5  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800071fa  mov     rcx, rbx; pv
0x1800071fd  call    cs:__imp_CoTaskMemFree
0x180007203  add     rsp, 20h
0x180007207  pop     rbx
0x180007208  retn
```

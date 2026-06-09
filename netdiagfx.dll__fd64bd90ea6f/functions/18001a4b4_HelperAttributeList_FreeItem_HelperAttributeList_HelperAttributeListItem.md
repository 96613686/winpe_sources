# HelperAttributeList::FreeItem(HelperAttributeList::HelperAttributeListItem *)

- ea: `0x18001a4b4`
- end: `0x18001a4dc`
- name: `?FreeItem@HelperAttributeList@@AEAAXPEAUHelperAttributeListItem@1@@Z`
- size: `40`
- prototype: `void __fastcall(HelperAttributeList *this, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017f94`
- `0x18001ba6c`

## callees

- `0x18000bda4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a4d5`

## pseudocode

```c
void __fastcall HelperAttributeList::FreeItem(HelperAttributeList *this, struct tagHELPER_ATTRIBUTE **a2)
{
  FreeHelperAttributes(*a2, 1u, 1);
  CoTaskMemFree(a2);
}

```

## disassembly

```asm
0x18001a4b4  push    rbx
0x18001a4b6  sub     rsp, 20h
0x18001a4ba  mov     rbx, rdx
0x18001a4bd  mov     edx, 1; unsigned int
0x18001a4c2  mov     r8d, edx; int
0x18001a4c5  mov     rcx, [rbx]; pv
0x18001a4c8  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x18001a4cd  mov     rcx, rbx
0x18001a4d0  add     rsp, 20h
0x18001a4d4  pop     rbx
0x18001a4d5  jmp     cs:__imp_CoTaskMemFree
```

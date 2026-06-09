# DeleteMediaType(_AMMediaType *)

- ea: `0x18003e22c`
- end: `0x18003e254`
- name: `?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z`
- size: `40`
- prototype: `void __fastcall(struct _AMMediaType *pv)`
- caller_count: `19`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003e50`
- `0x1800043d0`
- `0x180009250`
- `0x180016de4`
- `0x180016f60`
- `0x18001d7c0`
- `0x180025d60`
- `0x18002998c`
- `0x18002c620`
- `0x18002da70`
- `0x18002dd70`
- `0x18002fa50`
- `0x180031360`
- `0x1800315e0`
- `0x18003bae4`
- `0x18003cfe0`
- `0x18003e844`
- `0x18003f6d0`
- `0x18003f8a0`

## callees

- `0x180009c4c`
- `0x18003e22c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18003e241`
- `ole32!CoTaskMemFree` at `0x18003e241`

## pseudocode

```c
void __fastcall DeleteMediaType(struct _AMMediaType *pv)
{
  if ( pv )
  {
    FreeMediaType(pv);
    CoTaskMemFree((LPVOID)pv);
  }
}

```

## disassembly

```asm
0x18003e22c  test    rcx, rcx
0x18003e22f  jz      short locret_18003E252
0x18003e231  push    rbx
0x18003e232  sub     rsp, 20h
0x18003e236  mov     rbx, rcx
0x18003e239  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18003e23e  mov     rcx, rbx; pv
0x18003e241  call    cs:__imp_CoTaskMemFree
0x18003e248  nop     dword ptr [rax+rax+00h]
0x18003e24d  add     rsp, 20h
0x18003e251  pop     rbx
0x18003e252  retn
```

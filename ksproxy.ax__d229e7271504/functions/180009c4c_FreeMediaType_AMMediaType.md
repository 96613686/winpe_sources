# FreeMediaType(_AMMediaType &)

- ea: `0x180009c4c`
- end: `0x180009c89`
- name: `?FreeMediaType@@YAXAEAU_AMMediaType@@@Z`
- size: `61`
- prototype: `void __fastcall(struct _AMMediaType *)`
- caller_count: `15`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180008690`
- `0x180009704`
- `0x18000d88c`
- `0x180011840`
- `0x1800191e0`
- `0x180024140`
- `0x180024d10`
- `0x180025480`
- `0x180026de0`
- `0x180029ad0`
- `0x18002f814`
- `0x18003c198`
- `0x18003e22c`
- `0x18003e32c`
- `0x18003fedc`

## callees

- `0x180009c4c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180009c5f`
- `ole32!CoTaskMemFree` at `0x180009c5f`

## pseudocode

```c
void __fastcall FreeMediaType(struct _AMMediaType *a1)
{
  if ( a1->cbFormat )
  {
    CoTaskMemFree(a1->pbFormat);
    a1->cbFormat = 0;
    a1->pbFormat = 0;
  }
  a1->pUnk = 0;
}

```

## disassembly

```asm
0x180009c4c  push    rbx
0x180009c4e  sub     rsp, 20h
0x180009c52  cmp     dword ptr [rcx+48h], 0
0x180009c56  mov     rbx, rcx
0x180009c59  jz      short loc_180009C7A
0x180009c5b  mov     rcx, [rcx+50h]; pv
0x180009c5f  call    cs:__imp_CoTaskMemFree
0x180009c66  nop     dword ptr [rax+rax+00h]
0x180009c6b  mov     dword ptr [rbx+48h], 0
0x180009c72  mov     qword ptr [rbx+50h], 0
0x180009c7a  mov     qword ptr [rbx+40h], 0
0x180009c82  add     rsp, 20h
0x180009c86  pop     rbx
0x180009c87  retn
```

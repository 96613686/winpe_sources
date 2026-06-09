# FreeMediaType(_AMMediaType &)

- ea: `0x180006494`
- end: `0x1800064ca`
- name: `?FreeMediaType@@YAXAEAU_AMMediaType@@@Z`
- size: `54`
- prototype: `void __fastcall(struct _AMMediaType *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180002448`
- `0x18000310c`

## callees

- `0x180006494`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800064a7`
- `ole32!CoTaskMemFree` at `0x1800064a7`

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
0x180006494  push    rbx
0x180006496  sub     rsp, 20h
0x18000649a  cmp     dword ptr [rcx+48h], 0
0x18000649e  mov     rbx, rcx
0x1800064a1  jz      short loc_1800064BC
0x1800064a3  mov     rcx, [rcx+50h]; pv
0x1800064a7  call    cs:__imp_CoTaskMemFree
0x1800064ad  mov     dword ptr [rbx+48h], 0
0x1800064b4  mov     qword ptr [rbx+50h], 0
0x1800064bc  mov     qword ptr [rbx+40h], 0
0x1800064c4  add     rsp, 20h
0x1800064c8  pop     rbx
0x1800064c9  retn
```

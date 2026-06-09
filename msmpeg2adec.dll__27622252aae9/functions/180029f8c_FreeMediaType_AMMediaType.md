# FreeMediaType(_AMMediaType &)

- ea: `0x180029f8c`
- end: `0x180029fc9`
- name: `?FreeMediaType@@YAXAEAU_AMMediaType@@@Z`
- size: `61`
- prototype: `void __fastcall(struct _AMMediaType *)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026238`
- `0x1800273c0`
- `0x1800285c0`
- `0x1800286f0`
- `0x180029e40`
- `0x180029f5c`

## callees

- `0x180029f8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029f9f`

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
0x180029f8c  push    rbx
0x180029f8e  sub     rsp, 20h
0x180029f92  cmp     dword ptr [rcx+48h], 0
0x180029f96  mov     rbx, rcx
0x180029f99  jz      short loc_180029FBA
0x180029f9b  mov     rcx, [rcx+50h]; pv
0x180029f9f  call    cs:__imp_CoTaskMemFree
0x180029fa6  nop     dword ptr [rax+rax+00h]
0x180029fab  mov     dword ptr [rbx+48h], 0
0x180029fb2  mov     qword ptr [rbx+50h], 0
0x180029fba  mov     qword ptr [rbx+40h], 0
0x180029fc2  add     rsp, 20h
0x180029fc6  pop     rbx
0x180029fc7  retn
```

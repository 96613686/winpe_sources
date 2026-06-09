# FreeMediaType(_AMMediaType &)

- ea: `0x180007210`
- end: `0x180007246`
- name: `?FreeMediaType@@YAXAEAU_AMMediaType@@@Z`
- size: `54`
- prototype: `void __fastcall(struct _AMMediaType *)`
- caller_count: `16`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800036fc`
- `0x1800050d0`
- `0x1800069f0`
- `0x1800071e8`
- `0x18000724c`
- `0x1800083d0`
- `0x180008980`
- `0x180009d70`
- `0x18000f594`
- `0x180014f78`
- `0x18001588c`
- `0x180015a10`
- `0x180015c64`
- `0x1800177cc`
- `0x18001a600`
- `0x18001a88c`

## callees

- `0x180007210`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180007223`
- `ole32!CoTaskMemFree` at `0x180007223`

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
0x180007210  push    rbx
0x180007212  sub     rsp, 20h
0x180007216  cmp     dword ptr [rcx+48h], 0
0x18000721a  mov     rbx, rcx
0x18000721d  jz      short loc_180007238
0x18000721f  mov     rcx, [rcx+50h]; pv
0x180007223  call    cs:__imp_CoTaskMemFree
0x180007229  mov     dword ptr [rbx+48h], 0
0x180007230  mov     qword ptr [rbx+50h], 0
0x180007238  mov     qword ptr [rbx+40h], 0
0x180007240  add     rsp, 20h
0x180007244  pop     rbx
0x180007245  retn
```

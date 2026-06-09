# TSmartPointerArray<wstring>::~TSmartPointerArray<wstring>(void)

- ea: `0x1800058a4`
- end: `0x1800058ec`
- name: `??1?$TSmartPointerArray@Vwstring@@@@QEAA@XZ`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180005b18`

## callees

- `0x180001f2c`
- `0x1800058a4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800058d4`
- `ole32!CoTaskMemFree` at `0x1800058d4`

## pseudocode

```c
void __fastcall TSmartPointerArray<wstring>::~TSmartPointerArray<wstring>(void **a1)
{
  char *v2; // rcx
  char *v3; // rbx

  v2 = (char *)*a1;
  if ( v2 )
  {
    v3 = v2 - 8;
    `vector destructor iterator'(v2, 8u, *((_QWORD *)v2 - 1), (void (*)(void *))wstring::~wstring);
    CoTaskMemFree(v3);
  }
  *a1 = 0;
}

```

## disassembly

```asm
0x1800058a4  mov     [rsp+arg_0], rbx
0x1800058a9  push    rdi
0x1800058aa  sub     rsp, 20h
0x1800058ae  mov     rdi, rcx
0x1800058b1  mov     rcx, [rcx]; void *
0x1800058b4  test    rcx, rcx
0x1800058b7  jz      short loc_1800058DA
0x1800058b9  lea     rbx, [rcx-8]
0x1800058bd  lea     r9, ??1wstring@@QEAA@XZ; void (*)(void *)
0x1800058c4  mov     r8, [rbx]; unsigned __int64
0x1800058c7  mov     edx, 8; unsigned __int64
0x1800058cc  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800058d1  mov     rcx, rbx; pv
0x1800058d4  call    cs:__imp_CoTaskMemFree
0x1800058da  mov     qword ptr [rdi], 0
0x1800058e1  mov     rbx, [rsp+28h+arg_0]
0x1800058e6  add     rsp, 20h
0x1800058ea  pop     rdi
0x1800058eb  retn
```

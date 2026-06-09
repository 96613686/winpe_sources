# _dynamic_atexit_destructor_for__g_pSimpleTableDispenser__

- ea: `0x18002ef80`
- end: `0x18002efb4`
- name: `_dynamic_atexit_destructor_for__g_pSimpleTableDispenser__`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002bf0`
- `0x18002ef80`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002ef9d`
- `ole32!CoTaskMemFree` at `0x18002ef9d`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_pSimpleTableDispenser__()
{
  CSimpleTableDispenser *v0; // rbx

  v0 = g_pSimpleTableDispenser;
  if ( g_pSimpleTableDispenser )
  {
    CSimpleTableDispenser::~CSimpleTableDispenser(g_pSimpleTableDispenser);
    CoTaskMemFree(v0);
  }
  g_pSimpleTableDispenser = 0;
}

```

## disassembly

```asm
0x18002ef80  push    rbx
0x18002ef82  sub     rsp, 20h
0x18002ef86  mov     rbx, cs:?g_pSimpleTableDispenser@@3V?$TSmartPointer@VCSimpleTableDispenser@@@@A; TSmartPointer<CSimpleTableDispenser> g_pSimpleTableDispenser
0x18002ef8d  test    rbx, rbx
0x18002ef90  jz      short loc_18002EFA3
0x18002ef92  mov     rcx, rbx; this
0x18002ef95  call    ??1CSimpleTableDispenser@@QEAA@XZ; CSimpleTableDispenser::~CSimpleTableDispenser(void)
0x18002ef9a  mov     rcx, rbx; pv
0x18002ef9d  call    cs:__imp_CoTaskMemFree
0x18002efa3  mov     cs:?g_pSimpleTableDispenser@@3V?$TSmartPointer@VCSimpleTableDispenser@@@@A, 0; TSmartPointer<CSimpleTableDispenser> g_pSimpleTableDispenser
0x18002efae  add     rsp, 20h
0x18002efb2  pop     rbx
0x18002efb3  retn
```

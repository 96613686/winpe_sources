# CCfgArray<TMetabase_XMLtable::TProperty>::~CCfgArray<TMetabase_XMLtable::TProperty>(void)

- ea: `0x180005824`
- end: `0x180005843`
- name: `??1?$CCfgArray@VTProperty@TMetabase_XMLtable@@@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task`

## callers

- `0x18002e8f1`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005830`
- `ole32!CoTaskMemFree` at `0x180005830`

## pseudocode

```c
void __fastcall CCfgArray<TMetabase_XMLtable::TProperty>::~CCfgArray<TMetabase_XMLtable::TProperty>(LPVOID *a1)
{
  CoTaskMemFree(*a1);
  *a1 = 0;
}

```

## disassembly

```asm
0x180005824  push    rbx
0x180005826  sub     rsp, 20h
0x18000582a  mov     rbx, rcx
0x18000582d  mov     rcx, [rcx]; pv
0x180005830  call    cs:__imp_CoTaskMemFree
0x180005836  mov     qword ptr [rbx], 0
0x18000583d  add     rsp, 20h
0x180005841  pop     rbx
0x180005842  retn
```

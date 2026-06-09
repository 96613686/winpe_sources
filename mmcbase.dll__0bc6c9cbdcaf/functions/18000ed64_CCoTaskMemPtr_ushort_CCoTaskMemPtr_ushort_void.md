# CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)

- ea: `0x18000ed64`
- end: `0x18000ed88`
- name: `??1?$CCoTaskMemPtr@G@@QEAA@XZ`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f43c`
- `0x180015ca0`
- `0x18001bd87`
- `0x18001c07b`
- `0x18001c09f`

## callees

- `0x18000ed64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ed75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ed75`

## pseudocode

```c
void __fastcall CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18000ed64  push    rbx
0x18000ed66  sub     rsp, 20h
0x18000ed6a  mov     rbx, rcx
0x18000ed6d  mov     rcx, [rcx]; pv
0x18000ed70  test    rcx, rcx
0x18000ed73  jz      short loc_18000ED82
0x18000ed75  call    cs:__imp_CoTaskMemFree
0x18000ed7b  mov     qword ptr [rbx], 0
0x18000ed82  add     rsp, 20h
0x18000ed86  pop     rbx
0x18000ed87  retn
```

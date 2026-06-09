# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::~NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>(void)

- ea: `0x180016738`
- end: `0x18001676c`
- name: `??1?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800596d9`

## callees

- `0x180016738`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016749`

## pseudocode

```c
void __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::~NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180016738  push    rbx
0x18001673a  sub     rsp, 20h
0x18001673e  mov     rbx, rcx
0x180016741  mov     rcx, [rcx]; pv
0x180016744  test    rcx, rcx
0x180016747  jz      short loc_180016756
0x180016749  call    cs:__imp_CoTaskMemFree
0x18001674f  mov     qword ptr [rbx], 0
0x180016756  mov     qword ptr [rbx+8], 0
0x18001675e  mov     qword ptr [rbx+10h], 0
0x180016766  add     rsp, 20h
0x18001676a  pop     rbx
0x18001676b  retn
```

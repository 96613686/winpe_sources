# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::~NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>(void)

- ea: `0x1800027a8`
- end: `0x1800027dc`
- name: `??1?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000979e`

## callees

- `0x1800027a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800027b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800027b9`

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
0x1800027a8  push    rbx
0x1800027aa  sub     rsp, 20h
0x1800027ae  mov     rbx, rcx
0x1800027b1  mov     rcx, [rcx]; pv
0x1800027b4  test    rcx, rcx
0x1800027b7  jz      short loc_1800027C6
0x1800027b9  call    cs:__imp_CoTaskMemFree
0x1800027bf  mov     qword ptr [rbx], 0
0x1800027c6  mov     qword ptr [rbx+8], 0
0x1800027ce  mov     qword ptr [rbx+10h], 0
0x1800027d6  add     rsp, 20h
0x1800027da  pop     rbx
0x1800027db  retn
```

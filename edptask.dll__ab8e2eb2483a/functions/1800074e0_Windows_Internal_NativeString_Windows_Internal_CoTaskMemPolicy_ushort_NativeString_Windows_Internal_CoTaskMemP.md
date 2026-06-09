# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::~NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>(void)

- ea: `0x1800074e0`
- end: `0x180007514`
- name: `??1?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ac1c`
- `0x1800138dd`
- `0x18001392f`
- `0x180013941`
- `0x180013953`
- `0x180013965`
- `0x180013977`
- `0x180013bdb`
- `0x180013bed`
- `0x180013bff`

## callees

- `0x1800074e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074f1`

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
0x1800074e0  push    rbx
0x1800074e2  sub     rsp, 20h
0x1800074e6  mov     rbx, rcx
0x1800074e9  mov     rcx, [rcx]; pv
0x1800074ec  test    rcx, rcx
0x1800074ef  jz      short loc_1800074FE
0x1800074f1  call    cs:__imp_CoTaskMemFree
0x1800074f7  mov     qword ptr [rbx], 0
0x1800074fe  mov     qword ptr [rbx+8], 0
0x180007506  mov     qword ptr [rbx+10h], 0
0x18000750e  add     rsp, 20h
0x180007512  pop     rbx
0x180007513  retn
```

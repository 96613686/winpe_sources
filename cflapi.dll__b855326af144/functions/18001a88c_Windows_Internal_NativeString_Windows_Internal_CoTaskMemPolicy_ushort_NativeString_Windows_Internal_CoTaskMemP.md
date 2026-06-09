# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::~NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>(void)

- ea: `0x18001a88c`
- end: `0x18001a8c0`
- name: `??1?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f49f`

## callees

- `0x18001a88c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a89d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a89d`

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
0x18001a88c  push    rbx
0x18001a88e  sub     rsp, 20h
0x18001a892  mov     rbx, rcx
0x18001a895  mov     rcx, [rcx]; pv
0x18001a898  test    rcx, rcx
0x18001a89b  jz      short loc_18001A8AA
0x18001a89d  call    cs:__imp_CoTaskMemFree
0x18001a8a3  mov     qword ptr [rbx], 0
0x18001a8aa  mov     qword ptr [rbx+8], 0
0x18001a8b2  mov     qword ptr [rbx+10h], 0
0x18001a8ba  add     rsp, 20h
0x18001a8be  pop     rbx
0x18001a8bf  retn
```

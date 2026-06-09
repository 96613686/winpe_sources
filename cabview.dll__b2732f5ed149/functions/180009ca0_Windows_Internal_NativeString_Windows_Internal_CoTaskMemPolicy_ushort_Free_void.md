# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180009ca0`
- end: `0x180009cd4`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800046d0`
- `0x1800066dc`

## callees

- `0x180009ca0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009cb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009cb1`

## pseudocode

```c
void __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(__int64 a1)
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
0x180009ca0  push    rbx
0x180009ca2  sub     rsp, 20h
0x180009ca6  mov     rbx, rcx
0x180009ca9  mov     rcx, [rcx]; pv
0x180009cac  test    rcx, rcx
0x180009caf  jz      short loc_180009CBE
0x180009cb1  call    cs:__imp_CoTaskMemFree
0x180009cb7  mov     qword ptr [rbx], 0
0x180009cbe  mov     qword ptr [rbx+8], 0
0x180009cc6  mov     qword ptr [rbx+10h], 0
0x180009cce  add     rsp, 20h
0x180009cd2  pop     rbx
0x180009cd3  retn
```

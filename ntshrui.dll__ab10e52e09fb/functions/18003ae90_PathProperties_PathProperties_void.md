# PathProperties::~PathProperties(void)

- ea: `0x18003ae90`
- end: `0x18003aed5`
- name: `??1PathProperties@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(PathProperties *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003af44`

## callees

- `0x180024e44`
- `0x18003ae90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aeab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aeba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aec9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aeab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aeba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aec9`

## pseudocode

```c
void __fastcall PathProperties::~PathProperties(PathProperties *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 40);
  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
    CoTaskMemFree(v4);
}

```

## disassembly

```asm
0x18003ae90  push    rbx
0x18003ae92  sub     rsp, 20h
0x18003ae96  mov     rbx, rcx
0x18003ae99  add     rcx, 28h ; '('
0x18003ae9d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003aea2  mov     rcx, [rbx+20h]; pv
0x18003aea6  test    rcx, rcx
0x18003aea9  jz      short loc_18003AEB1
0x18003aeab  call    cs:__imp_CoTaskMemFree
0x18003aeb1  mov     rcx, [rbx+18h]; pv
0x18003aeb5  test    rcx, rcx
0x18003aeb8  jz      short loc_18003AEC0
0x18003aeba  call    cs:__imp_CoTaskMemFree
0x18003aec0  mov     rcx, [rbx+10h]; pv
0x18003aec4  test    rcx, rcx
0x18003aec7  jz      short loc_18003AECF
0x18003aec9  call    cs:__imp_CoTaskMemFree
0x18003aecf  add     rsp, 20h
0x18003aed3  pop     rbx
0x18003aed4  retn
```

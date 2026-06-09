# _hypothesis_builder::FreeAll(void)

- ea: `0x180010f58`
- end: `0x180010fb7`
- name: `?FreeAll@_hypothesis_builder@@QEAAXXZ`
- size: `95`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f560`
- `0x18000f5bc`
- `0x18000f7c8`
- `0x18000fc14`
- `0x180010184`
- `0x1800104f0`

## callees

- `0x18000d48c`
- `0x180010f58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010fa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010fa3`

## pseudocode

```c
void __fastcall _hypothesis_builder::FreeAll(LPVOID *this)
{
  void *v2; // rcx
  LPVOID *v3; // rcx

  CoTaskMemFree(*this);
  v2 = this[1];
  *this = 0;
  CoTaskMemFree(v2);
  this[1] = 0;
  _attributes_array_t::FreeElements((_attributes_array_t *)(this + 2));
  v3 = (LPVOID *)this[4];
  if ( v3 )
    CoTaskMemFree(v3[3]);
  CoTaskMemFree(this[4]);
  this[4] = 0;
}

```

## disassembly

```asm
0x180010f58  push    rbx
0x180010f5a  sub     rsp, 20h
0x180010f5e  mov     rbx, rcx
0x180010f61  mov     rcx, [rcx]; pv
0x180010f64  call    cs:__imp_CoTaskMemFree
0x180010f6a  mov     rcx, [rbx+8]; pv
0x180010f6e  mov     qword ptr [rbx], 0
0x180010f75  call    cs:__imp_CoTaskMemFree
0x180010f7b  lea     rcx, [rbx+10h]; this
0x180010f7f  mov     qword ptr [rbx+8], 0
0x180010f87  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180010f8c  mov     rcx, [rbx+20h]
0x180010f90  test    rcx, rcx
0x180010f93  jz      short loc_180010F9F
0x180010f95  mov     rcx, [rcx+18h]; pv
0x180010f99  call    cs:__imp_CoTaskMemFree
0x180010f9f  mov     rcx, [rbx+20h]; pv
0x180010fa3  call    cs:__imp_CoTaskMemFree
0x180010fa9  mov     qword ptr [rbx+20h], 0
0x180010fb1  add     rsp, 20h
0x180010fb5  pop     rbx
0x180010fb6  retn
```

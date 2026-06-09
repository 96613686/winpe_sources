# _hypothesis_builder::~_hypothesis_builder(void)

- ea: `0x180005f00`
- end: `0x180005f8b`
- name: `??1_hypothesis_builder@@QEAA@XZ`
- size: `139`
- prototype: `void __fastcall(_hypothesis_builder *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005f00`
- `0x180006628`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f6c`

## pseudocode

```c
void __fastcall _hypothesis_builder::~_hypothesis_builder(LPVOID *this)
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
  _attributes_array_t::FreeElements((_attributes_array_t *)(this + 2));
  CoTaskMemFree(this[3]);
  this[3] = 0;
  *((_DWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x180005f00  mov     [rsp+arg_0], rbx
0x180005f05  push    rdi
0x180005f06  sub     rsp, 20h
0x180005f0a  mov     rbx, rcx
0x180005f0d  mov     rcx, [rcx]; pv
0x180005f10  call    cs:__imp_CoTaskMemFree
0x180005f16  mov     rcx, [rbx+8]; pv
0x180005f1a  mov     qword ptr [rbx], 0
0x180005f21  call    cs:__imp_CoTaskMemFree
0x180005f27  lea     rdi, [rbx+10h]
0x180005f2b  mov     qword ptr [rbx+8], 0
0x180005f33  mov     rcx, rdi; this
0x180005f36  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180005f3b  mov     rcx, [rbx+20h]
0x180005f3f  test    rcx, rcx
0x180005f42  jz      short loc_180005F4E
0x180005f44  mov     rcx, [rcx+18h]; pv
0x180005f48  call    cs:__imp_CoTaskMemFree
0x180005f4e  mov     rcx, [rbx+20h]; pv
0x180005f52  call    cs:__imp_CoTaskMemFree
0x180005f58  mov     rcx, rdi; this
0x180005f5b  mov     qword ptr [rbx+20h], 0
0x180005f63  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180005f68  mov     rcx, [rdi+8]; pv
0x180005f6c  call    cs:__imp_CoTaskMemFree
0x180005f72  mov     rbx, [rsp+28h+arg_0]
0x180005f77  mov     qword ptr [rdi+8], 0
0x180005f7f  mov     dword ptr [rdi], 0
0x180005f85  add     rsp, 20h
0x180005f89  pop     rdi
0x180005f8a  retn
```

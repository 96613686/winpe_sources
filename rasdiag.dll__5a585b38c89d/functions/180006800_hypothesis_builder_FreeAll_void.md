# _hypothesis_builder::FreeAll(void)

- ea: `0x180006800`
- end: `0x18000689e`
- name: `?FreeAll@_hypothesis_builder@@QEAAXXZ`
- size: `158`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006100`
- `0x180006ac0`
- `0x1800086b0`
- `0x180009e60`
- `0x18000ad60`

## callees

- `0x18000678c`
- `0x180006800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006810`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006827`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000686e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000687e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006810`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006827`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000686e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000687e`

## pseudocode

```c
void __fastcall _hypothesis_builder::FreeAll(LPVOID *this)
{
  void *v2; // rcx
  __int64 i; // rdi
  LPVOID *v4; // rcx

  CoTaskMemFree(*this);
  v2 = this[1];
  *this = 0;
  CoTaskMemFree(v2);
  this[1] = 0;
  if ( this[3] )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
      _attribute_t::FreeAll((LPVOID *)this[3] + 18 * i);
  }
  v4 = (LPVOID *)this[4];
  if ( v4 )
    CoTaskMemFree(v4[3]);
  CoTaskMemFree(this[4]);
  this[4] = 0;
}

```

## disassembly

```asm
0x180006800  mov     [rsp+arg_0], rbx
0x180006805  push    rdi
0x180006806  sub     rsp, 20h
0x18000680a  mov     rbx, rcx
0x18000680d  mov     rcx, [rcx]; pv
0x180006810  call    cs:__imp_CoTaskMemFree
0x180006817  nop     dword ptr [rax+rax+00h]
0x18000681c  mov     rcx, [rbx+8]; pv
0x180006820  mov     qword ptr [rbx], 0
0x180006827  call    cs:__imp_CoTaskMemFree
0x18000682e  nop     dword ptr [rax+rax+00h]
0x180006833  mov     qword ptr [rbx+8], 0
0x18000683b  cmp     qword ptr [rbx+18h], 0
0x180006840  jz      short loc_180006861
0x180006842  xor     edi, edi
0x180006844  cmp     [rbx+10h], edi
0x180006847  jbe     short loc_180006861
0x180006849  lea     rcx, [rdi+rdi*8]
0x18000684d  shl     rcx, 4
0x180006851  add     rcx, [rbx+18h]; this
0x180006855  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000685a  inc     edi
0x18000685c  cmp     edi, [rbx+10h]
0x18000685f  jb      short loc_180006849
0x180006861  mov     rcx, [rbx+20h]
0x180006865  test    rcx, rcx
0x180006868  jz      short loc_18000687A
0x18000686a  mov     rcx, [rcx+18h]; pv
0x18000686e  call    cs:__imp_CoTaskMemFree
0x180006875  nop     dword ptr [rax+rax+00h]
0x18000687a  mov     rcx, [rbx+20h]; pv
0x18000687e  call    cs:__imp_CoTaskMemFree
0x180006885  nop     dword ptr [rax+rax+00h]
0x18000688a  mov     qword ptr [rbx+20h], 0
0x180006892  mov     rbx, [rsp+28h+arg_0]
0x180006897  add     rsp, 20h
0x18000689b  pop     rdi
0x18000689c  retn
```

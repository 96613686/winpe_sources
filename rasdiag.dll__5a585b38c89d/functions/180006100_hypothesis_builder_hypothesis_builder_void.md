# _hypothesis_builder::~_hypothesis_builder(void)

- ea: `0x180006100`
- end: `0x180006163`
- name: `??1_hypothesis_builder@@QEAA@XZ`
- size: `99`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006ac0`
- `0x180009e60`
- `0x18000ad60`
- `0x18000e538`
- `0x18000e57e`

## callees

- `0x180006100`
- `0x18000678c`
- `0x180006800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000613c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000613c`

## pseudocode

```c
void __fastcall _hypothesis_builder::~_hypothesis_builder(LPVOID *this)
{
  __int64 i; // rdi

  _hypothesis_builder::FreeAll((_hypothesis_builder *)this);
  if ( this[3] )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
      _attribute_t::FreeAll((_attribute_t *)((char *)this[3] + 144 * i));
  }
  CoTaskMemFree(this[3]);
  this[3] = 0;
  *((_DWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x180006100  mov     [rsp+arg_0], rbx
0x180006105  push    rdi
0x180006106  sub     rsp, 20h
0x18000610a  mov     rbx, rcx
0x18000610d  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x180006112  cmp     qword ptr [rbx+18h], 0
0x180006117  jz      short loc_180006138
0x180006119  xor     edi, edi
0x18000611b  cmp     [rbx+10h], edi
0x18000611e  jbe     short loc_180006138
0x180006120  lea     rcx, [rdi+rdi*8]
0x180006124  shl     rcx, 4
0x180006128  add     rcx, [rbx+18h]; this
0x18000612c  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180006131  inc     edi
0x180006133  cmp     edi, [rbx+10h]
0x180006136  jb      short loc_180006120
0x180006138  mov     rcx, [rbx+18h]; pv
0x18000613c  call    cs:__imp_CoTaskMemFree
0x180006143  nop     dword ptr [rax+rax+00h]
0x180006148  mov     qword ptr [rbx+18h], 0
0x180006150  mov     dword ptr [rbx+10h], 0
0x180006157  mov     rbx, [rsp+28h+arg_0]
0x18000615c  add     rsp, 20h
0x180006160  pop     rdi
0x180006161  retn
```

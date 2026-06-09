# CValueChunk::Reset(void)

- ea: `0x18000f90c`
- end: `0x18000f950`
- name: `?Reset@CValueChunk@@QEAAXXZ`
- size: `68`
- prototype: `void __fastcall(CValueChunk *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005654`
- `0x18000e1fc`
- `0x18000e318`

## callees

- `0x180005a70`
- `0x18000f90c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f941`

## pseudocode

```c
void __fastcall CValueChunk::Reset(CValueChunk *this)
{
  __int64 i; // rdi

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 9); i = (unsigned int)(i + 1) )
    CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 5) + 8 * i));
  *((_DWORD *)this + 9) = 0;
  CFullPropSpec::~CFullPropSpec(this);
}

```

## disassembly

```asm
0x18000f90c  mov     [rsp+arg_0], rbx
0x18000f911  push    rdi
0x18000f912  sub     rsp, 20h
0x18000f916  xor     edi, edi
0x18000f918  mov     rbx, rcx
0x18000f91b  cmp     [rcx+24h], edi
0x18000f91e  ja      short loc_18000F939
0x18000f920  mov     rcx, rbx; this
0x18000f923  mov     dword ptr [rbx+24h], 0
0x18000f92a  mov     rbx, [rsp+28h+arg_0]
0x18000f92f  add     rsp, 20h
0x18000f933  pop     rdi
0x18000f934  jmp     ??1CFullPropSpec@@QEAA@XZ; CFullPropSpec::~CFullPropSpec(void)
0x18000f939  mov     rcx, [rbx+28h]
0x18000f93d  mov     rcx, [rcx+rdi*8]; pv
0x18000f941  call    cs:__imp_CoTaskMemFree
0x18000f947  inc     edi
0x18000f949  cmp     edi, [rbx+24h]
0x18000f94c  jb      short loc_18000F939
0x18000f94e  jmp     short loc_18000F920
```

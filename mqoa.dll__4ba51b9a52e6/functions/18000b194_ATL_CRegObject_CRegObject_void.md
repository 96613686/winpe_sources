# ATL::CRegObject::~CRegObject(void)

- ea: `0x18000b194`
- end: `0x18000b1fa`
- name: `??1CRegObject@ATL@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180012854`
- `0x180027c9f`

## callees

- `0x18000178c`
- `0x18000b194`

## import_xrefs

- `msvcrt!free` at `0x18000b1e3`
- `msvcrt!free` at `0x18000b1e3`
- `ole32!CoTaskMemFree` at `0x18000b1bb`
- `ole32!CoTaskMemFree` at `0x18000b1c4`
- `ole32!CoTaskMemFree` at `0x18000b1bb`
- `ole32!CoTaskMemFree` at `0x18000b1c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  int i; // esi
  LPVOID *v3; // rbx

  for ( i = 0; i < *((_DWORD *)this + 2); ++i )
  {
    v3 = *(LPVOID **)(*(_QWORD *)this + 8LL * i);
    CoTaskMemFree(v3[1]);
    CoTaskMemFree(*v3);
    operator delete(v3);
  }
  *((_DWORD *)this + 2) = 0;
  free(*(void **)this);
}

```

## disassembly

```asm
0x18000b194  mov     [rsp+arg_0], rbx
0x18000b199  mov     [rsp+arg_8], rsi
0x18000b19e  push    rdi
0x18000b19f  sub     rsp, 20h
0x18000b1a3  mov     rdi, rcx
0x18000b1a6  xor     esi, esi
0x18000b1a8  cmp     [rcx+8], esi
0x18000b1ab  jle     short loc_18000B1D9
0x18000b1ad  movsxd  rdx, esi
0x18000b1b0  mov     rax, [rdi]
0x18000b1b3  mov     rbx, [rax+rdx*8]
0x18000b1b7  mov     rcx, [rbx+8]; pv
0x18000b1bb  call    cs:__imp_CoTaskMemFree
0x18000b1c1  mov     rcx, [rbx]; pv
0x18000b1c4  call    cs:__imp_CoTaskMemFree
0x18000b1ca  mov     rcx, rbx; Block
0x18000b1cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b1d2  inc     esi
0x18000b1d4  cmp     esi, [rdi+8]
0x18000b1d7  jl      short loc_18000B1AD
0x18000b1d9  mov     dword ptr [rdi+8], 0
0x18000b1e0  mov     rcx, [rdi]; Block
0x18000b1e3  call    cs:__imp_free
0x18000b1e9  nop
0x18000b1ea  mov     rbx, [rsp+28h+arg_0]
0x18000b1ef  mov     rsi, [rsp+28h+arg_8]
0x18000b1f4  add     rsp, 20h
0x18000b1f8  pop     rdi
0x18000b1f9  retn
```

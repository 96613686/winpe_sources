# ATL::CRegObject::~CRegObject(void)

- ea: `0x18000e18c`
- end: `0x18000e1f2`
- name: `??1CRegObject@ATL@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180012314`
- `0x180013a77`

## callees

- `0x18000e18c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000e1c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e1c5`
- `msvcrt!free` at `0x18000e1eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1bc`

## pseudocode

```c
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
0x18000e18c  mov     [rsp+arg_0], rbx
0x18000e191  mov     [rsp+arg_8], rsi
0x18000e196  push    rdi
0x18000e197  sub     rsp, 20h
0x18000e19b  xor     esi, esi
0x18000e19d  mov     rdi, rcx
0x18000e1a0  cmp     [rcx+8], esi
0x18000e1a3  jle     short loc_18000E1D2
0x18000e1a5  mov     rax, [rdi]
0x18000e1a8  movsxd  rdx, esi
0x18000e1ab  mov     rbx, [rax+rdx*8]
0x18000e1af  mov     rcx, [rbx+8]; pv
0x18000e1b3  call    cs:__imp_CoTaskMemFree
0x18000e1b9  mov     rcx, [rbx]; pv
0x18000e1bc  call    cs:__imp_CoTaskMemFree
0x18000e1c2  mov     rcx, rbx
0x18000e1c5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e1cb  inc     esi
0x18000e1cd  cmp     esi, [rdi+8]
0x18000e1d0  jl      short loc_18000E1A5
0x18000e1d2  mov     dword ptr [rdi+8], 0
0x18000e1d9  mov     rcx, [rdi]
0x18000e1dc  mov     rbx, [rsp+28h+arg_0]
0x18000e1e1  mov     rsi, [rsp+28h+arg_8]
0x18000e1e6  add     rsp, 20h
0x18000e1ea  pop     rdi
0x18000e1eb  jmp     cs:__imp_free
```

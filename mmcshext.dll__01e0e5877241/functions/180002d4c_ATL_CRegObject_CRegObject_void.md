# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002d4c`
- end: `0x180002db2`
- name: `??1CRegObject@ATL@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x180006374`
- `0x18000ab76`

## callees

- `0x180002d4c`

## import_xrefs

- `msvcrt!free` at `0x180002dab`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002d85`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002d85`
- `ole32!CoTaskMemFree` at `0x180002d73`
- `ole32!CoTaskMemFree` at `0x180002d7c`
- `ole32!CoTaskMemFree` at `0x180002d73`
- `ole32!CoTaskMemFree` at `0x180002d7c`

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
0x180002d4c  mov     [rsp+arg_0], rbx
0x180002d51  mov     [rsp+arg_8], rsi
0x180002d56  push    rdi
0x180002d57  sub     rsp, 20h
0x180002d5b  xor     esi, esi
0x180002d5d  mov     rdi, rcx
0x180002d60  cmp     [rcx+8], esi
0x180002d63  jle     short loc_180002D92
0x180002d65  mov     rax, [rdi]
0x180002d68  movsxd  rdx, esi
0x180002d6b  mov     rbx, [rax+rdx*8]
0x180002d6f  mov     rcx, [rbx+8]; pv
0x180002d73  call    cs:__imp_CoTaskMemFree
0x180002d79  mov     rcx, [rbx]; pv
0x180002d7c  call    cs:__imp_CoTaskMemFree
0x180002d82  mov     rcx, rbx
0x180002d85  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002d8b  inc     esi
0x180002d8d  cmp     esi, [rdi+8]
0x180002d90  jl      short loc_180002D65
0x180002d92  mov     dword ptr [rdi+8], 0
0x180002d99  mov     rcx, [rdi]
0x180002d9c  mov     rbx, [rsp+28h+arg_0]
0x180002da1  mov     rsi, [rsp+28h+arg_8]
0x180002da6  add     rsp, 20h
0x180002daa  pop     rdi
0x180002dab  jmp     cs:__imp_free
```

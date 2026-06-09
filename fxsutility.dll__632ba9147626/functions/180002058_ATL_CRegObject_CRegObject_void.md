# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002058`
- end: `0x1800020bd`
- name: `??1CRegObject@ATL@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180004680`
- `0x180016205`

## callees

- `0x1800012d0`
- `0x180002058`

## import_xrefs

- `msvcrt!free` at `0x1800020b6`
- `ole32!CoTaskMemFree` at `0x18000207f`
- `ole32!CoTaskMemFree` at `0x180002088`
- `ole32!CoTaskMemFree` at `0x18000207f`
- `ole32!CoTaskMemFree` at `0x180002088`

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
0x180002058  mov     [rsp+arg_0], rbx
0x18000205d  mov     [rsp+arg_8], rsi
0x180002062  push    rdi
0x180002063  sub     rsp, 20h
0x180002067  xor     esi, esi
0x180002069  mov     rdi, rcx
0x18000206c  cmp     [rcx+8], esi
0x18000206f  jle     short loc_18000209D
0x180002071  mov     rax, [rdi]
0x180002074  movsxd  rdx, esi
0x180002077  mov     rbx, [rax+rdx*8]
0x18000207b  mov     rcx, [rbx+8]; pv
0x18000207f  call    cs:__imp_CoTaskMemFree
0x180002085  mov     rcx, [rbx]; pv
0x180002088  call    cs:__imp_CoTaskMemFree
0x18000208e  mov     rcx, rbx; Block
0x180002091  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002096  inc     esi
0x180002098  cmp     esi, [rdi+8]
0x18000209b  jl      short loc_180002071
0x18000209d  mov     dword ptr [rdi+8], 0
0x1800020a4  mov     rcx, [rdi]
0x1800020a7  mov     rbx, [rsp+28h+arg_0]
0x1800020ac  mov     rsi, [rsp+28h+arg_8]
0x1800020b1  add     rsp, 20h
0x1800020b5  pop     rdi
0x1800020b6  jmp     cs:__imp_free
```

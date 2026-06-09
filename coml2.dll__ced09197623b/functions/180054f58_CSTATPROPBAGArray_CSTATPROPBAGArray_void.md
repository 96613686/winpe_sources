# CSTATPROPBAGArray::~CSTATPROPBAGArray(void)

- ea: `0x180054f58`
- end: `0x180054fae`
- name: `??1CSTATPROPBAGArray@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(CSTATPROPBAGArray *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054efc`

## callees

- `0x180054f58`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054f82`

## pseudocode

```c
void __fastcall CSTATPROPBAGArray::~CSTATPROPBAGArray(CSTATPROPBAGArray *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx

  v2 = *((_QWORD *)this + 1);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 1) = 0;
  CoTaskMemFree(v3);
  v4 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 3) = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x180054f58  push    rbx
0x180054f5a  sub     rsp, 20h
0x180054f5e  mov     rbx, rcx
0x180054f61  mov     rcx, [rcx+8]
0x180054f65  test    rcx, rcx
0x180054f68  jz      short loc_180054F76
0x180054f6a  mov     rax, [rcx]
0x180054f6d  mov     rax, [rax+10h]
0x180054f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f76  mov     rcx, [rbx+18h]; pv
0x180054f7a  mov     qword ptr [rbx+8], 0
0x180054f82  call    cs:__imp_CoTaskMemFree
0x180054f88  mov     rcx, [rbx+10h]
0x180054f8c  mov     qword ptr [rbx+18h], 0
0x180054f94  mov     rax, [rcx]
0x180054f97  mov     rax, [rax+10h]
0x180054f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fa0  mov     qword ptr [rbx+10h], 0
0x180054fa8  add     rsp, 20h
0x180054fac  pop     rbx
0x180054fad  retn
```

# CRasDiagHelper::~CRasDiagHelper(void)

- ea: `0x1800060b0`
- end: `0x1800060f8`
- name: `??1CRasDiagHelper@@QEAA@XZ`
- size: `72`
- prototype: `void __fastcall(CRasDiagHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006170`

## callees

- `0x180006030`
- `0x1800060b0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060c5`

## pseudocode

```c
void __fastcall CRasDiagHelper::~CRasDiagHelper(CRasDiagHelper *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  v2 = (void *)*((_QWORD *)this + 148);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = *((_QWORD *)this + 151);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  CNetDiagHelper::~CNetDiagHelper(this);
}

```

## disassembly

```asm
0x1800060b0  push    rbx
0x1800060b2  sub     rsp, 20h
0x1800060b6  mov     rbx, rcx
0x1800060b9  mov     rcx, [rcx+4A0h]; pv
0x1800060c0  test    rcx, rcx
0x1800060c3  jz      short loc_1800060D2
0x1800060c5  call    cs:__imp_CoTaskMemFree
0x1800060cc  nop     dword ptr [rax+rax+00h]
0x1800060d1  nop
0x1800060d2  mov     rcx, [rbx+4B8h]
0x1800060d9  test    rcx, rcx
0x1800060dc  jz      short loc_1800060EB
0x1800060de  mov     rax, [rcx]
0x1800060e1  mov     rax, [rax+10h]
0x1800060e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ea  nop
0x1800060eb  mov     rcx, rbx; this
0x1800060ee  add     rsp, 20h
0x1800060f2  pop     rbx
0x1800060f3  jmp     ??1CNetDiagHelper@@QEAA@XZ; CNetDiagHelper::~CNetDiagHelper(void)
```

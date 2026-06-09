# CVPNDiagHelper::~CVPNDiagHelper(void)

- ea: `0x180008280`
- end: `0x1800082d2`
- name: `??1CVPNDiagHelper@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(CVPNDiagHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800082e0`

## callees

- `0x180006030`
- `0x180008280`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008295`

## pseudocode

```c
void __fastcall CVPNDiagHelper::~CVPNDiagHelper(CVPNDiagHelper *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  v2 = (void *)*((_QWORD *)this + 178);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 178) = 0;
  }
  v3 = *((_QWORD *)this + 177);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  CNetDiagHelper::~CNetDiagHelper(this);
}

```

## disassembly

```asm
0x180008280  push    rbx
0x180008282  sub     rsp, 20h
0x180008286  mov     rbx, rcx
0x180008289  mov     rcx, [rcx+590h]; pv
0x180008290  test    rcx, rcx
0x180008293  jz      short loc_1800082AC
0x180008295  call    cs:__imp_CoTaskMemFree
0x18000829c  nop     dword ptr [rax+rax+00h]
0x1800082a1  mov     qword ptr [rbx+590h], 0
0x1800082ac  mov     rcx, [rbx+588h]
0x1800082b3  test    rcx, rcx
0x1800082b6  jz      short loc_1800082C5
0x1800082b8  mov     rax, [rcx]
0x1800082bb  mov     rax, [rax+10h]
0x1800082bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082c4  nop
0x1800082c5  mov     rcx, rbx; this
0x1800082c8  add     rsp, 20h
0x1800082cc  pop     rbx
0x1800082cd  jmp     ??1CNetDiagHelper@@QEAA@XZ; CNetDiagHelper::~CNetDiagHelper(void)
```

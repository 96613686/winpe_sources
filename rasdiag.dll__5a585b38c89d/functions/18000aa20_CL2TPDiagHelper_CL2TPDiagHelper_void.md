# CL2TPDiagHelper::~CL2TPDiagHelper(void)

- ea: `0x18000aa20`
- end: `0x18000aa59`
- name: `??1CL2TPDiagHelper@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(CL2TPDiagHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000aa60`

## callees

- `0x180006030`
- `0x18000aa20`
- `0x18000f010`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x18000aa29`
- `WS2_32!__imp_WSACleanup` at `0x18000aa29`

## pseudocode

```c
void __fastcall CL2TPDiagHelper::~CL2TPDiagHelper(CL2TPDiagHelper *this)
{
  __int64 v2; // rcx

  WSACleanup();
  v2 = *((_QWORD *)this + 14);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  CNetDiagHelper::~CNetDiagHelper(this);
}

```

## disassembly

```asm
0x18000aa20  push    rbx
0x18000aa22  sub     rsp, 20h
0x18000aa26  mov     rbx, rcx
0x18000aa29  call    cs:__imp_WSACleanup
0x18000aa30  nop     dword ptr [rax+rax+00h]
0x18000aa35  nop
0x18000aa36  mov     rcx, [rbx+70h]
0x18000aa3a  test    rcx, rcx
0x18000aa3d  jz      short loc_18000AA4C
0x18000aa3f  mov     rax, [rcx]
0x18000aa42  mov     rax, [rax+10h]
0x18000aa46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa4b  nop
0x18000aa4c  mov     rcx, rbx; this
0x18000aa4f  add     rsp, 20h
0x18000aa53  pop     rbx
0x18000aa54  jmp     ??1CNetDiagHelper@@QEAA@XZ; CNetDiagHelper::~CNetDiagHelper(void)
```

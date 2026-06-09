# CMQTransaction::CMQTransaction(void)

- ea: `0x1800182e0`
- end: `0x180018321`
- name: `??0CMQTransaction@@QEAA@XZ`
- size: `65`
- prototype: `CMQTransaction *__fastcall(CMQTransaction *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180018800`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180018312`
- `RPCRT4!UuidCreate` at `0x180018312`

## pseudocode

```c
CMQTransaction *__fastcall CMQTransaction::CMQTransaction(CMQTransaction *this)
{
  *((_QWORD *)this + 2) = 1;
  *(_QWORD *)this = &CMQTransaction::`vftable'{for `ITransaction'};
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 1) = &CMQTransaction::`vftable'{for `IMSMQTransaction'};
  UuidCreate((UUID *)((char *)this + 24));
  return this;
}

```

## disassembly

```asm
0x1800182e0  push    rbx
0x1800182e2  sub     rsp, 20h
0x1800182e6  lea     rax, ??_7CMQTransaction@@6BITransaction@@@; const CMQTransaction::`vftable'{for `ITransaction'}
0x1800182ed  mov     qword ptr [rcx+10h], 1
0x1800182f5  mov     [rcx], rax
0x1800182f8  mov     rbx, rcx
0x1800182fb  lea     rax, ??_7CMQTransaction@@6BIMSMQTransaction@@@; const CMQTransaction::`vftable'{for `IMSMQTransaction'}
0x180018302  mov     qword ptr [rcx+28h], 0
0x18001830a  mov     [rcx+8], rax
0x18001830e  add     rcx, 18h; Uuid
0x180018312  call    cs:__imp_UuidCreate
0x180018318  mov     rax, rbx
0x18001831b  add     rsp, 20h
0x18001831f  pop     rbx
0x180018320  retn
```

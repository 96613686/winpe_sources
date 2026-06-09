# ATL::CRegObject::ClearReplacements(void)

- ea: `0x14000cd40`
- end: `0x14000cd7b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000cc84`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000cd54`
- `KERNEL32!EnterCriticalSection` at `0x14000cd54`
- `KERNEL32!LeaveCriticalSection` at `0x14000cd68`
- `KERNEL32!LeaveCriticalSection` at `0x14000cd68`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  ATL::CRegObject *v2; // rbx
  unsigned int v3; // edx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v2 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  LODWORD(v2) = ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)v2 + 8), v3);
  LeaveCriticalSection(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000cd40  mov     [rsp+arg_0], rbx
0x14000cd45  push    rdi
0x14000cd46  sub     rsp, 20h
0x14000cd4a  lea     rdi, [rcx+20h]
0x14000cd4e  mov     rbx, rcx
0x14000cd51  mov     rcx, rdi; lpCriticalSection
0x14000cd54  call    cs:__imp_EnterCriticalSection
0x14000cd5a  lea     rcx, [rbx+8]; this
0x14000cd5e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x14000cd63  mov     rcx, rdi; lpCriticalSection
0x14000cd66  mov     ebx, eax
0x14000cd68  call    cs:__imp_LeaveCriticalSection
0x14000cd6e  mov     eax, ebx
0x14000cd70  mov     rbx, [rsp+28h+arg_0]
0x14000cd75  add     rsp, 20h
0x14000cd79  pop     rdi
0x14000cd7a  retn
```

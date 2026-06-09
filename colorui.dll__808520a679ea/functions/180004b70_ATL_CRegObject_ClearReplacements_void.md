# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180004b70`
- end: `0x180004bab`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004ab8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004b84`
- `KERNEL32!EnterCriticalSection` at `0x180004b84`
- `KERNEL32!LeaveCriticalSection` at `0x180004b98`
- `KERNEL32!LeaveCriticalSection` at `0x180004b98`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  ATL::CRegObject *v2; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v2 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  LODWORD(v2) = ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)v2 + 8));
  LeaveCriticalSection(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180004b70  mov     [rsp+arg_0], rbx
0x180004b75  push    rdi
0x180004b76  sub     rsp, 20h
0x180004b7a  lea     rdi, [rcx+20h]
0x180004b7e  mov     rbx, rcx
0x180004b81  mov     rcx, rdi; lpCriticalSection
0x180004b84  call    cs:__imp_EnterCriticalSection
0x180004b8a  lea     rcx, [rbx+8]; this
0x180004b8e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180004b93  mov     rcx, rdi; lpCriticalSection
0x180004b96  mov     ebx, eax
0x180004b98  call    cs:__imp_LeaveCriticalSection
0x180004b9e  mov     eax, ebx
0x180004ba0  mov     rbx, [rsp+28h+arg_0]
0x180004ba5  add     rsp, 20h
0x180004ba9  pop     rdi
0x180004baa  retn
```

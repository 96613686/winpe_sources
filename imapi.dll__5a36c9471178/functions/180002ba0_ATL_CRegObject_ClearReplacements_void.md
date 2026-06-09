# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180002ba0`
- end: `0x180002bdb`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002aec`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002bc8`
- `KERNEL32!LeaveCriticalSection` at `0x180002bc8`
- `KERNEL32!EnterCriticalSection` at `0x180002bb4`
- `KERNEL32!EnterCriticalSection` at `0x180002bb4`

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
0x180002ba0  mov     [rsp+arg_0], rbx
0x180002ba5  push    rdi
0x180002ba6  sub     rsp, 20h
0x180002baa  lea     rdi, [rcx+20h]
0x180002bae  mov     rbx, rcx
0x180002bb1  mov     rcx, rdi; lpCriticalSection
0x180002bb4  call    cs:__imp_EnterCriticalSection
0x180002bba  lea     rcx, [rbx+8]; this
0x180002bbe  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002bc3  mov     rcx, rdi; lpCriticalSection
0x180002bc6  mov     ebx, eax
0x180002bc8  call    cs:__imp_LeaveCriticalSection
0x180002bce  mov     eax, ebx
0x180002bd0  mov     rbx, [rsp+28h+arg_0]
0x180002bd5  add     rsp, 20h
0x180002bd9  pop     rdi
0x180002bda  retn
```

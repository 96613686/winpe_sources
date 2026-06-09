# ATL::CRegObject::ClearReplacements(void)

- ea: `0x18000a020`
- end: `0x18000a05b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008a2c`

## callees

- `0x180009fa4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000a034`
- `KERNEL32!EnterCriticalSection` at `0x18000a034`
- `KERNEL32!LeaveCriticalSection` at `0x18000a048`
- `KERNEL32!LeaveCriticalSection` at `0x18000a048`

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
0x18000a020  mov     [rsp+arg_0], rbx
0x18000a025  push    rdi
0x18000a026  sub     rsp, 20h
0x18000a02a  lea     rdi, [rcx+20h]
0x18000a02e  mov     rbx, rcx
0x18000a031  mov     rcx, rdi; lpCriticalSection
0x18000a034  call    cs:__imp_EnterCriticalSection
0x18000a03a  lea     rcx, [rbx+8]; this
0x18000a03e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000a043  mov     rcx, rdi; lpCriticalSection
0x18000a046  mov     ebx, eax
0x18000a048  call    cs:__imp_LeaveCriticalSection
0x18000a04e  mov     eax, ebx
0x18000a050  mov     rbx, [rsp+28h+arg_0]
0x18000a055  add     rsp, 20h
0x18000a059  pop     rdi
0x18000a05a  retn
```

# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180003830`
- end: `0x18000386b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003774`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003844`
- `KERNEL32!EnterCriticalSection` at `0x180003844`
- `KERNEL32!LeaveCriticalSection` at `0x180003858`
- `KERNEL32!LeaveCriticalSection` at `0x180003858`

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
0x180003830  mov     [rsp+arg_0], rbx
0x180003835  push    rdi
0x180003836  sub     rsp, 20h
0x18000383a  lea     rdi, [rcx+20h]
0x18000383e  mov     rbx, rcx
0x180003841  mov     rcx, rdi; lpCriticalSection
0x180003844  call    cs:__imp_EnterCriticalSection
0x18000384a  lea     rcx, [rbx+8]; this
0x18000384e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003853  mov     rcx, rdi; lpCriticalSection
0x180003856  mov     ebx, eax
0x180003858  call    cs:__imp_LeaveCriticalSection
0x18000385e  mov     eax, ebx
0x180003860  mov     rbx, [rsp+28h+arg_0]
0x180003865  add     rsp, 20h
0x180003869  pop     rdi
0x18000386a  retn
```

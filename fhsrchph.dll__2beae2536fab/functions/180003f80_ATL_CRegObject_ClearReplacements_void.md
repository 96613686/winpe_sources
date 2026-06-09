# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180003f80`
- end: `0x180003fbb`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003ed0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003f94`
- `KERNEL32!EnterCriticalSection` at `0x180003f94`
- `KERNEL32!LeaveCriticalSection` at `0x180003fa8`
- `KERNEL32!LeaveCriticalSection` at `0x180003fa8`

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
0x180003f80  mov     [rsp+arg_0], rbx
0x180003f85  push    rdi
0x180003f86  sub     rsp, 20h
0x180003f8a  lea     rdi, [rcx+20h]
0x180003f8e  mov     rbx, rcx
0x180003f91  mov     rcx, rdi; lpCriticalSection
0x180003f94  call    cs:__imp_EnterCriticalSection
0x180003f9a  lea     rcx, [rbx+8]; this
0x180003f9e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003fa3  mov     rcx, rdi; lpCriticalSection
0x180003fa6  mov     ebx, eax
0x180003fa8  call    cs:__imp_LeaveCriticalSection
0x180003fae  mov     eax, ebx
0x180003fb0  mov     rbx, [rsp+28h+arg_0]
0x180003fb5  add     rsp, 20h
0x180003fb9  pop     rdi
0x180003fba  retn
```

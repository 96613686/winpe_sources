# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180009a50`
- end: `0x180009a8b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008d34`

## callees

- `0x1800099d4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180009a64`
- `KERNEL32!EnterCriticalSection` at `0x180009a64`
- `KERNEL32!LeaveCriticalSection` at `0x180009a78`
- `KERNEL32!LeaveCriticalSection` at `0x180009a78`

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
0x180009a50  mov     [rsp+arg_0], rbx
0x180009a55  push    rdi
0x180009a56  sub     rsp, 20h
0x180009a5a  lea     rdi, [rcx+20h]
0x180009a5e  mov     rbx, rcx
0x180009a61  mov     rcx, rdi; lpCriticalSection
0x180009a64  call    cs:__imp_EnterCriticalSection
0x180009a6a  lea     rcx, [rbx+8]; this
0x180009a6e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180009a73  mov     rcx, rdi; lpCriticalSection
0x180009a76  mov     ebx, eax
0x180009a78  call    cs:__imp_LeaveCriticalSection
0x180009a7e  mov     eax, ebx
0x180009a80  mov     rbx, [rsp+28h+arg_0]
0x180009a85  add     rsp, 20h
0x180009a89  pop     rdi
0x180009a8a  retn
```

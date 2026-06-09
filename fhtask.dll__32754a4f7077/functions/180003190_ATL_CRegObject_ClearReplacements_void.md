# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180003190`
- end: `0x1800031cb`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800030dc`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800031a4`
- `KERNEL32!EnterCriticalSection` at `0x1800031a4`
- `KERNEL32!LeaveCriticalSection` at `0x1800031b8`
- `KERNEL32!LeaveCriticalSection` at `0x1800031b8`

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
0x180003190  mov     [rsp+arg_0], rbx
0x180003195  push    rdi
0x180003196  sub     rsp, 20h
0x18000319a  lea     rdi, [rcx+20h]
0x18000319e  mov     rbx, rcx
0x1800031a1  mov     rcx, rdi; lpCriticalSection
0x1800031a4  call    cs:__imp_EnterCriticalSection
0x1800031aa  lea     rcx, [rbx+8]; this
0x1800031ae  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800031b3  mov     rcx, rdi; lpCriticalSection
0x1800031b6  mov     ebx, eax
0x1800031b8  call    cs:__imp_LeaveCriticalSection
0x1800031be  mov     eax, ebx
0x1800031c0  mov     rbx, [rsp+28h+arg_0]
0x1800031c5  add     rsp, 20h
0x1800031c9  pop     rdi
0x1800031ca  retn
```

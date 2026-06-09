# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180004290`
- end: `0x1800042d8`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `72`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800041b4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800042be`
- `KERNEL32!LeaveCriticalSection` at `0x1800042be`
- `KERNEL32!EnterCriticalSection` at `0x1800042a4`
- `KERNEL32!EnterCriticalSection` at `0x1800042a4`

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
0x180004290  mov     [rsp+arg_0], rbx
0x180004295  push    rdi
0x180004296  sub     rsp, 20h
0x18000429a  lea     rdi, [rcx+20h]
0x18000429e  mov     rbx, rcx
0x1800042a1  mov     rcx, rdi; lpCriticalSection
0x1800042a4  call    cs:__imp_EnterCriticalSection
0x1800042ab  nop     dword ptr [rax+rax+00h]
0x1800042b0  lea     rcx, [rbx+8]; this
0x1800042b4  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800042b9  mov     rcx, rdi; lpCriticalSection
0x1800042bc  mov     ebx, eax
0x1800042be  call    cs:__imp_LeaveCriticalSection
0x1800042c5  nop     dword ptr [rax+rax+00h]
0x1800042ca  mov     eax, ebx
0x1800042cc  mov     rbx, [rsp+28h+arg_0]
0x1800042d1  add     rsp, 20h
0x1800042d5  pop     rdi
0x1800042d6  retn
```

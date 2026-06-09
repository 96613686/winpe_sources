# ATL::CRegObject::ClearReplacements(void)

- ea: `0x1800069f0`
- end: `0x180006a38`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `72`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006914`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006a04`
- `KERNEL32!EnterCriticalSection` at `0x180006a04`
- `KERNEL32!LeaveCriticalSection` at `0x180006a1e`
- `KERNEL32!LeaveCriticalSection` at `0x180006a1e`

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
0x1800069f0  mov     [rsp+arg_0], rbx
0x1800069f5  push    rdi
0x1800069f6  sub     rsp, 20h
0x1800069fa  lea     rdi, [rcx+20h]
0x1800069fe  mov     rbx, rcx
0x180006a01  mov     rcx, rdi; lpCriticalSection
0x180006a04  call    cs:__imp_EnterCriticalSection
0x180006a0b  nop     dword ptr [rax+rax+00h]
0x180006a10  lea     rcx, [rbx+8]; this
0x180006a14  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180006a19  mov     rcx, rdi; lpCriticalSection
0x180006a1c  mov     ebx, eax
0x180006a1e  call    cs:__imp_LeaveCriticalSection
0x180006a25  nop     dword ptr [rax+rax+00h]
0x180006a2a  mov     eax, ebx
0x180006a2c  mov     rbx, [rsp+28h+arg_0]
0x180006a31  add     rsp, 20h
0x180006a35  pop     rdi
0x180006a36  retn
```

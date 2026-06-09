# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180006840`
- end: `0x18000687b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000678c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180006868`
- `KERNEL32!LeaveCriticalSection` at `0x180006868`
- `KERNEL32!EnterCriticalSection` at `0x180006854`
- `KERNEL32!EnterCriticalSection` at `0x180006854`

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
0x180006840  mov     [rsp+arg_0], rbx
0x180006845  push    rdi
0x180006846  sub     rsp, 20h
0x18000684a  lea     rdi, [rcx+20h]
0x18000684e  mov     rbx, rcx
0x180006851  mov     rcx, rdi; lpCriticalSection
0x180006854  call    cs:__imp_EnterCriticalSection
0x18000685a  lea     rcx, [rbx+8]; this
0x18000685e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180006863  mov     rcx, rdi; lpCriticalSection
0x180006866  mov     ebx, eax
0x180006868  call    cs:__imp_LeaveCriticalSection
0x18000686e  mov     eax, ebx
0x180006870  mov     rbx, [rsp+28h+arg_0]
0x180006875  add     rsp, 20h
0x180006879  pop     rdi
0x18000687a  retn
```

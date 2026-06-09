# ATL::CRegObject::ClearReplacements(void)

- ea: `0x18000f360`
- end: `0x18000f39b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f2a4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f374`
- `KERNEL32!EnterCriticalSection` at `0x18000f374`
- `KERNEL32!LeaveCriticalSection` at `0x18000f388`
- `KERNEL32!LeaveCriticalSection` at `0x18000f388`

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
0x18000f360  mov     [rsp+arg_0], rbx
0x18000f365  push    rdi
0x18000f366  sub     rsp, 20h
0x18000f36a  lea     rdi, [rcx+20h]
0x18000f36e  mov     rbx, rcx
0x18000f371  mov     rcx, rdi; lpCriticalSection
0x18000f374  call    cs:__imp_EnterCriticalSection
0x18000f37a  lea     rcx, [rbx+8]; this
0x18000f37e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000f383  mov     rcx, rdi; lpCriticalSection
0x18000f386  mov     ebx, eax
0x18000f388  call    cs:__imp_LeaveCriticalSection
0x18000f38e  mov     eax, ebx
0x18000f390  mov     rbx, [rsp+28h+arg_0]
0x18000f395  add     rsp, 20h
0x18000f399  pop     rdi
0x18000f39a  retn
```

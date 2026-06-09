# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180003a90`
- end: `0x180003acb`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800039a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ab8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ab8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003aa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003aa4`

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
0x180003a90  mov     [rsp+arg_0], rbx
0x180003a95  push    rdi
0x180003a96  sub     rsp, 20h
0x180003a9a  lea     rdi, [rcx+20h]
0x180003a9e  mov     rbx, rcx
0x180003aa1  mov     rcx, rdi; lpCriticalSection
0x180003aa4  call    cs:__imp_EnterCriticalSection
0x180003aaa  lea     rcx, [rbx+8]; this
0x180003aae  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003ab3  mov     rcx, rdi; lpCriticalSection
0x180003ab6  mov     ebx, eax
0x180003ab8  call    cs:__imp_LeaveCriticalSection
0x180003abe  mov     eax, ebx
0x180003ac0  mov     rbx, [rsp+28h+arg_0]
0x180003ac5  add     rsp, 20h
0x180003ac9  pop     rdi
0x180003aca  retn
```

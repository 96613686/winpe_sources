# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180004120`
- end: `0x18000415b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004148`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004148`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004134`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004134`

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
0x180004120  mov     [rsp+arg_0], rbx
0x180004125  push    rdi
0x180004126  sub     rsp, 20h
0x18000412a  lea     rdi, [rcx+20h]
0x18000412e  mov     rbx, rcx
0x180004131  mov     rcx, rdi; lpCriticalSection
0x180004134  call    cs:__imp_EnterCriticalSection
0x18000413a  lea     rcx, [rbx+8]; this
0x18000413e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180004143  mov     rcx, rdi; lpCriticalSection
0x180004146  mov     ebx, eax
0x180004148  call    cs:__imp_LeaveCriticalSection
0x18000414e  mov     eax, ebx
0x180004150  mov     rbx, [rsp+28h+arg_0]
0x180004155  add     rsp, 20h
0x180004159  pop     rdi
0x18000415a  retn
```

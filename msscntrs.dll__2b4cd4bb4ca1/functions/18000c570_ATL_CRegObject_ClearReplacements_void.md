# ATL::CRegObject::ClearReplacements(void)

- ea: `0x18000c570`
- end: `0x18000c5ab`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c4b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c584`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c584`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c598`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c598`

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
0x18000c570  mov     [rsp+arg_0], rbx
0x18000c575  push    rdi
0x18000c576  sub     rsp, 20h
0x18000c57a  lea     rdi, [rcx+20h]
0x18000c57e  mov     rbx, rcx
0x18000c581  mov     rcx, rdi; lpCriticalSection
0x18000c584  call    cs:__imp_EnterCriticalSection
0x18000c58a  lea     rcx, [rbx+8]; this
0x18000c58e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000c593  mov     rcx, rdi; lpCriticalSection
0x18000c596  mov     ebx, eax
0x18000c598  call    cs:__imp_LeaveCriticalSection
0x18000c59e  mov     eax, ebx
0x18000c5a0  mov     rbx, [rsp+28h+arg_0]
0x18000c5a5  add     rsp, 20h
0x18000c5a9  pop     rdi
0x18000c5aa  retn
```

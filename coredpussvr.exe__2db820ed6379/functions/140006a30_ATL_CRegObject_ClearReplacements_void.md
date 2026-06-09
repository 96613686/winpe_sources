# ATL::CRegObject::ClearReplacements(void)

- ea: `0x140006a30`
- end: `0x140006a78`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `72`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140006968`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006a44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006a44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006a5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006a5e`

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
0x140006a30  mov     [rsp+arg_0], rbx
0x140006a35  push    rdi
0x140006a36  sub     rsp, 20h
0x140006a3a  lea     rdi, [rcx+20h]
0x140006a3e  mov     rbx, rcx
0x140006a41  mov     rcx, rdi; lpCriticalSection
0x140006a44  call    cs:__imp_EnterCriticalSection
0x140006a4b  nop     dword ptr [rax+rax+00h]
0x140006a50  lea     rcx, [rbx+8]; this
0x140006a54  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x140006a59  mov     rcx, rdi; lpCriticalSection
0x140006a5c  mov     ebx, eax
0x140006a5e  call    cs:__imp_LeaveCriticalSection
0x140006a65  nop     dword ptr [rax+rax+00h]
0x140006a6a  mov     eax, ebx
0x140006a6c  mov     rbx, [rsp+28h+arg_0]
0x140006a71  add     rsp, 20h
0x140006a75  pop     rdi
0x140006a76  retn
```

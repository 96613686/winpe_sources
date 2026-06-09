# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180003f90`
- end: `0x180003fcb`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003ed8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003fb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003fb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003fa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003fa4`

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
0x180003f90  mov     [rsp+arg_0], rbx
0x180003f95  push    rdi
0x180003f96  sub     rsp, 20h
0x180003f9a  lea     rdi, [rcx+20h]
0x180003f9e  mov     rbx, rcx
0x180003fa1  mov     rcx, rdi; lpCriticalSection
0x180003fa4  call    cs:__imp_EnterCriticalSection
0x180003faa  lea     rcx, [rbx+8]; this
0x180003fae  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003fb3  mov     rcx, rdi; lpCriticalSection
0x180003fb6  mov     ebx, eax
0x180003fb8  call    cs:__imp_LeaveCriticalSection
0x180003fbe  mov     eax, ebx
0x180003fc0  mov     rbx, [rsp+28h+arg_0]
0x180003fc5  add     rsp, 20h
0x180003fc9  pop     rdi
0x180003fca  retn
```

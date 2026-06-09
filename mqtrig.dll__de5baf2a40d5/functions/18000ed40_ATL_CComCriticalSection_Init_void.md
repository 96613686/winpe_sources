# ATL::CComCriticalSection::Init(void)

- ea: `0x18000ed40`
- end: `0x18000ed6a`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ed1c`

## callees

- `0x18000ed40`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000ed48`
- `KERNEL32!InitializeCriticalSection` at `0x18000ed48`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  InitializeCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x18000ed40  push    rbx
0x18000ed42  sub     rsp, 20h
0x18000ed46  xor     ebx, ebx
0x18000ed48  call    cs:__imp_InitializeCriticalSection
0x18000ed4e  jmp     short loc_18000ED62
0x18000ed50  mov     ebx, 80004005h
0x18000ed55  mov     ecx, 8007000Eh
0x18000ed5a  cmp     eax, 0C0000017h
0x18000ed5f  cmovz   ebx, ecx
0x18000ed62  mov     eax, ebx
0x18000ed64  add     rsp, 20h
0x18000ed68  pop     rbx
0x18000ed69  retn
```

# ATL::CComCriticalSection::Init(void)

- ea: `0x14000232c`
- end: `0x140002356`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001aa4`
- `0x140001b98`
- `0x140001cb0`

## callees

- `0x14000232c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140002334`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140002334`

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
0x14000232c  push    rbx
0x14000232e  sub     rsp, 20h
0x140002332  xor     ebx, ebx
0x140002334  call    cs:__imp_InitializeCriticalSection
0x14000233a  jmp     short loc_14000234E
0x14000233c  mov     ebx, 80004005h
0x140002341  mov     ecx, 8007000Eh
0x140002346  cmp     eax, 0C0000017h
0x14000234b  cmovz   ebx, ecx
0x14000234e  mov     eax, ebx
0x140002350  add     rsp, 20h
0x140002354  pop     rbx
0x140002355  retn
```

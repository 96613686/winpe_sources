# ATL::CComCriticalSection::Init(void)

- ea: `0x1800040dc`
- end: `0x180004106`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003e50`

## callees

- `0x1800040dc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800040e4`
- `KERNEL32!InitializeCriticalSection` at `0x1800040e4`

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
0x1800040dc  push    rbx
0x1800040de  sub     rsp, 20h
0x1800040e2  xor     ebx, ebx
0x1800040e4  call    cs:__imp_InitializeCriticalSection
0x1800040ea  jmp     short loc_1800040FE
0x1800040ec  mov     ebx, 80004005h
0x1800040f1  mov     ecx, 8007000Eh
0x1800040f6  cmp     eax, 0C0000017h
0x1800040fb  cmovz   ebx, ecx
0x1800040fe  mov     eax, ebx
0x180004100  add     rsp, 20h
0x180004104  pop     rbx
0x180004105  retn
```

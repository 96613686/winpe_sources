# ATL::CComCriticalSection::Init(void)

- ea: `0x180002edc`
- end: `0x180002f06`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002c50`

## callees

- `0x180002edc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180002ee4`
- `KERNEL32!InitializeCriticalSection` at `0x180002ee4`

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
0x180002edc  push    rbx
0x180002ede  sub     rsp, 20h
0x180002ee2  xor     ebx, ebx
0x180002ee4  call    cs:__imp_InitializeCriticalSection
0x180002eea  jmp     short loc_180002EFE
0x180002eec  mov     ebx, 80004005h
0x180002ef1  mov     ecx, 8007000Eh
0x180002ef6  cmp     eax, 0C0000017h
0x180002efb  cmovz   ebx, ecx
0x180002efe  mov     eax, ebx
0x180002f00  add     rsp, 20h
0x180002f04  pop     rbx
0x180002f05  retn
```

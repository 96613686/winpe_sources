# ATL::CComCriticalSection::Init(void)

- ea: `0x18001017c`
- end: `0x1800101a6`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fd50`
- `0x18000fef0`

## callees

- `0x18001017c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180010184`
- `KERNEL32!InitializeCriticalSection` at `0x180010184`

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
0x18001017c  push    rbx
0x18001017e  sub     rsp, 20h
0x180010182  xor     ebx, ebx
0x180010184  call    cs:__imp_InitializeCriticalSection
0x18001018a  jmp     short loc_18001019E
0x18001018c  mov     ebx, 80004005h
0x180010191  mov     ecx, 8007000Eh
0x180010196  cmp     eax, 0C0000017h
0x18001019b  cmovz   ebx, ecx
0x18001019e  mov     eax, ebx
0x1800101a0  add     rsp, 20h
0x1800101a4  pop     rbx
0x1800101a5  retn
```

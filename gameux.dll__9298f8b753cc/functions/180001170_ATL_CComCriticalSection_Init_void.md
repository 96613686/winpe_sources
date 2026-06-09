# ATL::CComCriticalSection::Init(void)

- ea: `0x180001170`
- end: `0x180001190`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010b0`
- `0x180001f44`
- `0x18000203c`
- `0x180002110`

## callees

- `0x180001170`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180001174`
- `KERNEL32!InitializeCriticalSection` at `0x180001174`

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
0x180001170  sub     rsp, 38h
0x180001174  call    cs:__imp_InitializeCriticalSection
0x18000117a  xor     eax, eax
0x18000117c  mov     [rsp+38h+var_18], eax
0x180001180  jmp     short loc_18000118B
0x180001182  mov     eax, 8007000Eh
0x180001187  mov     [rsp+38h+var_18], eax
0x18000118b  add     rsp, 38h
0x18000118f  retn
0x1800030f0  push    rbp
0x1800030f2  sub     rsp, 20h
0x1800030f6  mov     rbp, rdx
0x1800030f9  mov     rax, [rcx]
0x1800030fc  xor     ecx, ecx
0x1800030fe  cmp     dword ptr [rax], 0C0000017h
0x180003104  setz    cl
0x180003107  mov     eax, ecx
0x180003109  add     rsp, 20h
0x18000310d  pop     rbp
0x18000310e  retn
```

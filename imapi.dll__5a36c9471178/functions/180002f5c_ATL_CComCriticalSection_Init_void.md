# ATL::CComCriticalSection::Init(void)

- ea: `0x180002f5c`
- end: `0x180002f7c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001050`
- `0x1800010a0`
- `0x1800010d0`
- `0x180001110`
- `0x180002c18`
- `0x180002d30`
- `0x1800043dc`
- `0x180006224`
- `0x180006320`
- `0x180008784`
- `0x1800088b8`
- `0x1800093cc`
- `0x18000aaa4`
- `0x18000b10c`
- `0x18000b8f0`
- `0x18000bb64`
- `0x1800165b4`

## callees

- `0x180002f5c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180002f60`
- `KERNEL32!InitializeCriticalSection` at `0x180002f60`

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
0x180002f5c  sub     rsp, 38h
0x180002f60  call    cs:__imp_InitializeCriticalSection
0x180002f66  xor     eax, eax
0x180002f68  mov     [rsp+38h+var_18], eax
0x180002f6c  jmp     short loc_180002F77
0x180002f6e  mov     eax, 8007000Eh
0x180002f73  mov     [rsp+38h+var_18], eax
0x180002f77  add     rsp, 38h
0x180002f7b  retn
0x1800188f6  push    rbp
0x1800188f8  sub     rsp, 20h
0x1800188fc  mov     rbp, rdx
0x1800188ff  mov     rax, [rcx]
0x180018902  xor     ecx, ecx
0x180018904  cmp     dword ptr [rax], 0C0000017h
0x18001890a  setz    cl
0x18001890d  mov     eax, ecx
0x18001890f  add     rsp, 20h
0x180018913  pop     rbp
0x180018914  retn
```

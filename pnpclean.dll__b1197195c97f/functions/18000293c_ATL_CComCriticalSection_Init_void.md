# ATL::CComCriticalSection::Init(void)

- ea: `0x18000293c`
- end: `0x18000295c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010a0`
- `0x1800010e0`
- `0x180001120`
- `0x180002e60`

## callees

- `0x18000293c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180002940`
- `KERNEL32!InitializeCriticalSection` at `0x180002940`

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
0x18000293c  sub     rsp, 38h
0x180002940  call    cs:__imp_InitializeCriticalSection
0x180002946  xor     eax, eax
0x180002948  mov     [rsp+38h+var_18], eax
0x18000294c  jmp     short loc_180002957
0x18000294e  mov     eax, 8007000Eh
0x180002953  mov     [rsp+38h+var_18], eax
0x180002957  add     rsp, 38h
0x18000295b  retn
0x1800091b6  push    rbp
0x1800091b8  sub     rsp, 20h
0x1800091bc  mov     rbp, rdx
0x1800091bf  mov     rax, [rcx]
0x1800091c2  xor     ecx, ecx
0x1800091c4  cmp     dword ptr [rax], 0C0000017h
0x1800091ca  setz    cl
0x1800091cd  mov     eax, ecx
0x1800091cf  add     rsp, 20h
0x1800091d3  pop     rbp
0x1800091d4  retn
```

# ATL::CComCriticalSection::Init(void)

- ea: `0x180006f6c`
- end: `0x180006f8c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800017d0`
- `0x180001820`
- `0x180001850`
- `0x180001890`
- `0x180006890`
- `0x180006990`
- `0x180006a8c`
- `0x180006b90`
- `0x180006ca0`
- `0x1800088fc`
- `0x180008c1c`
- `0x18000bfcc`

## callees

- `0x180006f6c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006f70`
- `KERNEL32!InitializeCriticalSection` at `0x180006f70`

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
0x180006f6c  sub     rsp, 38h
0x180006f70  call    cs:__imp_InitializeCriticalSection
0x180006f76  xor     eax, eax
0x180006f78  mov     [rsp+38h+var_18], eax
0x180006f7c  jmp     short loc_180006F87
0x180006f7e  mov     eax, 8007000Eh
0x180006f83  mov     [rsp+38h+var_18], eax
0x180006f87  add     rsp, 38h
0x180006f8b  retn
0x1800131e6  push    rbp
0x1800131e8  sub     rsp, 20h
0x1800131ec  mov     rbp, rdx
0x1800131ef  mov     rax, [rcx]
0x1800131f2  xor     ecx, ecx
0x1800131f4  cmp     dword ptr [rax], 0C0000017h
0x1800131fa  setz    cl
0x1800131fd  mov     eax, ecx
0x1800131ff  add     rsp, 20h
0x180013203  pop     rbp
0x180013204  retn
```

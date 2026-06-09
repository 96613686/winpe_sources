# ATL::CComCriticalSection::Init(void)

- ea: `0x1800021fc`
- end: `0x18000221c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010a0`
- `0x180001e48`
- `0x180001f90`

## callees

- `0x1800021fc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180002200`
- `KERNEL32!InitializeCriticalSection` at `0x180002200`

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
0x1800021fc  sub     rsp, 38h
0x180002200  call    cs:__imp_InitializeCriticalSection
0x180002206  xor     eax, eax
0x180002208  mov     [rsp+38h+var_18], eax
0x18000220c  jmp     short loc_180002217
0x18000220e  mov     eax, 8007000Eh
0x180002213  mov     [rsp+38h+var_18], eax
0x180002217  add     rsp, 38h
0x18000221b  retn
0x180004ca6  push    rbp
0x180004ca8  sub     rsp, 20h
0x180004cac  mov     rbp, rdx
0x180004caf  mov     rax, [rcx]
0x180004cb2  xor     ecx, ecx
0x180004cb4  cmp     dword ptr [rax], 0C0000017h
0x180004cba  setz    cl
0x180004cbd  mov     eax, ecx
0x180004cbf  add     rsp, 20h
0x180004cc3  pop     rbp
0x180004cc4  retn
```

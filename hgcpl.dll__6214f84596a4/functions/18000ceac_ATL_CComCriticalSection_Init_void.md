# ATL::CComCriticalSection::Init(void)

- ea: `0x18000ceac`
- end: `0x18000cecc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800021f0`
- `0x180002260`
- `0x1800022a0`
- `0x18000dfcc`
- `0x18000e224`
- `0x18000f868`

## callees

- `0x18000ceac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ceb0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ceb0`

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
0x18000ceac  sub     rsp, 38h
0x18000ceb0  call    cs:__imp_InitializeCriticalSection
0x18000ceb6  xor     eax, eax
0x18000ceb8  mov     [rsp+38h+var_18], eax
0x18000cebc  jmp     short loc_18000CEC7
0x18000cebe  mov     eax, 8007000Eh
0x18000cec3  mov     [rsp+38h+var_18], eax
0x18000cec7  add     rsp, 38h
0x18000cecb  retn
0x180018eb9  push    rbp
0x180018ebb  sub     rsp, 20h
0x180018ebf  mov     rbp, rdx
0x180018ec2  mov     rax, [rcx]
0x180018ec5  xor     ecx, ecx
0x180018ec7  cmp     dword ptr [rax], 0C0000017h
0x180018ecd  setz    cl
0x180018ed0  mov     eax, ecx
0x180018ed2  add     rsp, 20h
0x180018ed6  pop     rbp
0x180018ed7  retn
```

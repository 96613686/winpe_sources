# ATL::CComCriticalSection::Init(void)

- ea: `0x18000b344`
- end: `0x18000b364`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001090`
- `0x1800010d0`
- `0x18000b1f0`
- `0x18000b2ec`
- `0x1800138c0`

## callees

- `0x18000b344`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000b348`
- `KERNEL32!InitializeCriticalSection` at `0x18000b348`

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
0x18000b344  sub     rsp, 38h
0x18000b348  call    cs:__imp_InitializeCriticalSection
0x18000b34e  xor     eax, eax
0x18000b350  mov     [rsp+38h+var_18], eax
0x18000b354  jmp     short loc_18000B35F
0x18000b356  mov     eax, 8007000Eh
0x18000b35b  mov     [rsp+38h+var_18], eax
0x18000b35f  add     rsp, 38h
0x18000b363  retn
0x18002263c  push    rbp
0x18002263e  sub     rsp, 20h
0x180022642  mov     rbp, rdx
0x180022645  mov     rax, [rcx]
0x180022648  xor     ecx, ecx
0x18002264a  cmp     dword ptr [rax], 0C0000017h
0x180022650  setz    cl
0x180022653  mov     eax, ecx
0x180022655  add     rsp, 20h
0x180022659  pop     rbp
0x18002265a  retn
```

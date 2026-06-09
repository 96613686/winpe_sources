# ATL::CComCriticalSection::Init(void)

- ea: `0x18000b88c`
- end: `0x18000b8ac`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001110`
- `0x180009870`

## callees

- `0x18000b88c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000b890`
- `KERNEL32!InitializeCriticalSection` at `0x18000b890`

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
0x18000b88c  sub     rsp, 38h
0x18000b890  call    cs:__imp_InitializeCriticalSection
0x18000b896  xor     eax, eax
0x18000b898  mov     [rsp+38h+var_18], eax
0x18000b89c  jmp     short loc_18000B8A7
0x18000b89e  mov     eax, 8007000Eh
0x18000b8a3  mov     [rsp+38h+var_18], eax
0x18000b8a7  add     rsp, 38h
0x18000b8ab  retn
0x180012017  push    rbp
0x180012019  sub     rsp, 20h
0x18001201d  mov     rbp, rdx
0x180012020  mov     rax, [rcx]
0x180012023  xor     ecx, ecx
0x180012025  cmp     dword ptr [rax], 0C0000017h
0x18001202b  setz    cl
0x18001202e  mov     eax, ecx
0x180012030  add     rsp, 20h
0x180012034  pop     rbp
0x180012035  retn
```

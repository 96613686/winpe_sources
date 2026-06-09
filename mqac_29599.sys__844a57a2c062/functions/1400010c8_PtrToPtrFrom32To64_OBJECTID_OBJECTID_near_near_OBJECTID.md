# PtrToPtrFrom32To64<_OBJECTID>(_OBJECTID near * near *,_OBJECTID * *)

- ea: `0x1400010c8`
- end: `0x14000110a`
- name: `??$PtrToPtrFrom32To64@U_OBJECTID@@@@YAPEAPEAU_OBJECTID@@PAPAU0@PEAPEAU0@@Z`
- size: `66`
- prototype: `_QWORD *__fastcall(volatile void *Address, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001364`
- `0x1400017cc`
- `0x140001a04`

## callees

- `0x1400010c8`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400010ea`
- `ntoskrnl!ProbeForRead` at `0x1400010ea`

## pseudocode

```c
_QWORD *__fastcall PtrToPtrFrom32To64<_OBJECTID>(volatile void *Address, _QWORD *a2)
{
  unsigned __int64 v4; // rbx

  if ( !(_DWORD)Address )
    return 0;
  v4 = (unsigned int)Address;
  ProbeForRead((volatile void *)(unsigned int)Address, 4u, 1u);
  *a2 = *(unsigned int *)v4;
  return a2;
}

```

## disassembly

```asm
0x1400010c8  mov     [rsp+arg_0], rbx
0x1400010cd  push    rdi
0x1400010ce  sub     rsp, 20h
0x1400010d2  mov     rdi, rdx
0x1400010d5  test    ecx, ecx
0x1400010d7  jnz     short loc_1400010DD
0x1400010d9  xor     eax, eax
0x1400010db  jmp     short loc_1400010FE
0x1400010dd  mov     edx, 4; Length
0x1400010e2  mov     ebx, ecx
0x1400010e4  mov     ecx, ecx; Address
0x1400010e6  lea     r8d, [rdx-3]; Alignment
0x1400010ea  call    cs:__imp_ProbeForRead
0x1400010f1  nop     dword ptr [rax+rax+00h]
0x1400010f6  mov     eax, [rbx]
0x1400010f8  mov     [rdi], rax
0x1400010fb  mov     rax, rdi
0x1400010fe  mov     rbx, [rsp+28h+arg_0]
0x140001103  add     rsp, 20h
0x140001107  pop     rdi
0x140001108  retn
```

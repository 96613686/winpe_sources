# CWMReadSample::GetMaxLength(ulong *)

- ea: `0x180009d30`
- end: `0x180009d5f`
- name: `?GetMaxLength@CWMReadSample@@UEAAJPEAK@Z`
- size: `47`
- prototype: `__int64 __fastcall(CWMReadSample *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009d30`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMReadSample::GetMaxLength(CWMReadSample *this, unsigned int *a2)
{
  if ( !a2 )
    return 2147942487LL;
  *a2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 32LL))(*((_QWORD *)this + 9));
  return 0;
}

```

## disassembly

```asm
0x180009d30  push    rbx
0x180009d32  sub     rsp, 20h
0x180009d36  mov     rbx, rdx
0x180009d39  test    rdx, rdx
0x180009d3c  jnz     short loc_180009D45
0x180009d3e  mov     eax, 80070057h
0x180009d43  jmp     short loc_180009D59
0x180009d45  mov     rcx, [rcx+48h]
0x180009d49  mov     rax, [rcx]
0x180009d4c  mov     rax, [rax+20h]
0x180009d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d55  mov     [rbx], eax
0x180009d57  xor     eax, eax
0x180009d59  add     rsp, 20h
0x180009d5d  pop     rbx
0x180009d5e  retn
```

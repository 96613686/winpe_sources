# NtLmDeleteKernelContext

- ea: `0x140023500`
- end: `0x14002356d`
- name: `NtLmDeleteKernelContext`
- size: `109`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140010240`
- `0x140023500`
- `0x14002fe40`

## pseudocode

```c
__int64 __fastcall NtLmDeleteKernelContext(_QWORD *P, _QWORD *a2, __int64 a3)
{
  int v5; // esi
  unsigned int v6; // ebx

  LOBYTE(a3) = 1;
  v5 = (*((__int64 (__fastcall **)(_QWORD *, __int64, __int64))LsaKernelFunctions + 4))(P, 1296847950, a3);
  if ( v5 < 0 )
  {
    v6 = 0;
    *a2 = P;
  }
  else
  {
    *a2 = P[5];
    v6 = (P[6] & 0x1000000) != 0 ? 0x90323 : 0;
    NtlmDerefContext(P);
  }
  if ( v6 != 590627 )
    return (unsigned int)v5;
  return v6;
}

```

## disassembly

```asm
0x140023500  push    rbx
0x140023502  push    rsi
0x140023503  push    rdi
0x140023504  push    r14
0x140023506  sub     rsp, 28h
0x14002350a  mov     rax, cs:?LsaKernelFunctions@@3PEAU_SECPKG_KERNEL_FUNCTIONS@@EA; _SECPKG_KERNEL_FUNCTIONS * LsaKernelFunctions
0x140023511  mov     r14, rdx
0x140023514  mov     r8b, 1
0x140023517  mov     edx, 4D4C544Eh
0x14002351c  mov     rdi, rcx
0x14002351f  mov     rax, [rax+20h]
0x140023523  call    _guard_dispatch_icall
0x140023528  mov     esi, eax
0x14002352a  test    eax, eax
0x14002352c  js      short loc_140023566
0x14002352e  mov     rcx, [rdi+28h]
0x140023532  mov     [r14], rcx
0x140023535  mov     ecx, [rdi+30h]
0x140023538  and     ecx, 1000000h
0x14002353e  neg     ecx
0x140023540  sbb     ebx, ebx
0x140023542  and     ebx, 90323h
0x140023548  mov     rcx, rdi; P
0x14002354b  call    NtlmDerefContext
0x140023550  cmp     ebx, 90323h
0x140023556  cmovnz  ebx, esi
0x140023559  mov     eax, ebx
0x14002355b  add     rsp, 28h
0x14002355f  pop     r14
0x140023561  pop     rdi
0x140023562  pop     rsi
0x140023563  pop     rbx
0x140023564  retn
0x140023566  xor     ebx, ebx
0x140023568  mov     [r14], rdi
0x14002356b  jmp     short loc_140023550
```

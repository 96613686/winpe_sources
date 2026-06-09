# ConvertPenToGdi::~ConvertPenToGdi(void)

- ea: `0x1800299b4`
- end: `0x180029a8c`
- name: `??1ConvertPenToGdi@@QEAA@XZ`
- size: `216`
- prototype: `void __fastcall(ConvertPenToGdi *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180029070`
- `0x1800e6300`
- `0x180138be8`

## callees

- `0x1800299b4`

## import_xrefs

- `GDI32!SetMiterLimit` at `0x180029a02`
- `GDI32!SetMiterLimit` at `0x180029a02`
- `GDI32!ExtEscape` at `0x180029a54`
- `GDI32!ExtEscape` at `0x180029a7e`
- `GDI32!ExtEscape` at `0x180029a54`
- `GDI32!ExtEscape` at `0x180029a7e`
- `GDI32!DeleteObject` at `0x1800299e4`
- `GDI32!DeleteObject` at `0x1800299e4`

## pseudocode

```c
void __fastcall ConvertPenToGdi::~ConvertPenToGdi(ConvertPenToGdi *this)
{
  int v2; // ebx

  v2 = _mm_getcsr();
  _mm_setcsr(v2 & 0xFFFFFFC0);
  if ( *(_DWORD *)this == 1198932785 )
    DeleteObject(*((HGDIOBJ *)this + 1));
  if ( *((_DWORD *)this + 4) )
    SetMiterLimit(*((HDC *)this + 4), *((FLOAT *)this + 5), 0);
  if ( *((_DWORD *)this + 6) != -2 )
    ExtEscape(*((HDC *)this + 4), 21, 4, (LPCSTR)this + 24, 0, 0);
  if ( *((_DWORD *)this + 7) != -2 )
    ExtEscape(*((HDC *)this + 4), 22, 4, (LPCSTR)this + 28, 0, 0);
  *(_DWORD *)this = 1279869254;
  _mm_setcsr(v2 & 0xFFFFFFC0);
}

```

## disassembly

```asm
0x1800299b4  mov     [rsp+arg_8], rbx
0x1800299b9  push    rdi
0x1800299ba  sub     rsp, 30h
0x1800299be  mov     rdi, rcx
0x1800299c1  stmxcsr [rsp+38h+arg_0]
0x1800299c6  mov     ebx, [rsp+38h+arg_0]
0x1800299ca  mov     eax, ebx
0x1800299cc  and     eax, 0FFFFFFC0h
0x1800299cf  cmp     dword ptr [rcx], 47764331h
0x1800299d5  mov     [rsp+38h+arg_0], eax
0x1800299d9  ldmxcsr [rsp+38h+arg_0]
0x1800299de  jnz     short loc_1800299F0
0x1800299e0  mov     rcx, [rcx+8]; ho
0x1800299e4  call    cs:__imp_DeleteObject
0x1800299eb  nop     dword ptr [rax+rax+00h]
0x1800299f0  cmp     dword ptr [rdi+10h], 0
0x1800299f4  jz      short loc_180029A0E
0x1800299f6  movss   xmm1, dword ptr [rdi+14h]; limit
0x1800299fb  xor     r8d, r8d; old
0x1800299fe  mov     rcx, [rdi+20h]; hdc
0x180029a02  call    cs:__imp_SetMiterLimit
0x180029a09  nop     dword ptr [rax+rax+00h]
0x180029a0e  cmp     dword ptr [rdi+18h], 0FFFFFFFEh
0x180029a12  jnz     short loc_180029A38
0x180029a14  cmp     dword ptr [rdi+1Ch], 0FFFFFFFEh
0x180029a18  jnz     short loc_180029A62
0x180029a1a  and     ebx, 0FFFFFFC0h
0x180029a1d  mov     dword ptr [rdi], 4C494146h
0x180029a23  mov     [rsp+38h+arg_0], ebx
0x180029a27  ldmxcsr [rsp+38h+arg_0]
0x180029a2c  mov     rbx, [rsp+38h+arg_8]
0x180029a31  add     rsp, 30h
0x180029a35  pop     rdi
0x180029a36  retn
0x180029a38  and     [rsp+38h+var_10], 0
0x180029a3e  lea     r9, [rdi+18h]; lpInData
0x180029a42  and     [rsp+38h+var_18], 0
0x180029a47  mov     edx, 15h; iEscape
0x180029a4c  mov     rcx, [rdi+20h]; hdc
0x180029a50  lea     r8d, [rdx-11h]; cjInput
0x180029a54  call    cs:__imp_ExtEscape
0x180029a5b  nop     dword ptr [rax+rax+00h]
0x180029a60  jmp     short loc_180029A14
0x180029a62  and     [rsp+38h+var_10], 0
0x180029a68  lea     r9, [rdi+1Ch]; lpInData
0x180029a6c  and     [rsp+38h+var_18], 0
0x180029a71  mov     edx, 16h; iEscape
0x180029a76  mov     rcx, [rdi+20h]; hdc
0x180029a7a  lea     r8d, [rdx-12h]; cjInput
0x180029a7e  call    cs:__imp_ExtEscape
0x180029a85  nop     dword ptr [rax+rax+00h]
0x180029a8a  jmp     short loc_180029A1A
```

# ConvertPenToGdi::~ConvertPenToGdi(void)

- ea: `0x18003e5e0`
- end: `0x18003e6c4`
- name: `??1ConvertPenToGdi@@QEAA@XZ`
- size: `228`
- prototype: `void __fastcall(ConvertPenToGdi *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18003cc70`
- `0x18003d400`
- `0x1801431e8`

## callees

- `0x18003e5e0`

## import_xrefs

- `GDI32!SetMiterLimit` at `0x18003e62e`
- `GDI32!SetMiterLimit` at `0x18003e62e`
- `GDI32!ExtEscape` at `0x18003e686`
- `GDI32!ExtEscape` at `0x18003e6b6`
- `GDI32!ExtEscape` at `0x18003e686`
- `GDI32!ExtEscape` at `0x18003e6b6`
- `GDI32!DeleteObject` at `0x18003e610`
- `GDI32!DeleteObject` at `0x18003e610`

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
0x18003e5e0  mov     [rsp+arg_8], rbx
0x18003e5e5  push    rdi
0x18003e5e6  sub     rsp, 30h
0x18003e5ea  mov     rdi, rcx
0x18003e5ed  stmxcsr [rsp+38h+arg_0]
0x18003e5f2  mov     ebx, [rsp+38h+arg_0]
0x18003e5f6  mov     eax, ebx
0x18003e5f8  and     eax, 0FFFFFFC0h
0x18003e5fb  cmp     dword ptr [rcx], 47764331h
0x18003e601  mov     [rsp+38h+arg_0], eax
0x18003e605  ldmxcsr [rsp+38h+arg_0]
0x18003e60a  jnz     short loc_18003E61C
0x18003e60c  mov     rcx, [rcx+8]; ho
0x18003e610  call    cs:__imp_DeleteObject
0x18003e617  nop     dword ptr [rax+rax+00h]
0x18003e61c  cmp     dword ptr [rdi+10h], 0
0x18003e620  jz      short loc_18003E63A
0x18003e622  movss   xmm1, dword ptr [rdi+14h]; limit
0x18003e627  xor     r8d, r8d; old
0x18003e62a  mov     rcx, [rdi+20h]; hdc
0x18003e62e  call    cs:__imp_SetMiterLimit
0x18003e635  nop     dword ptr [rax+rax+00h]
0x18003e63a  cmp     dword ptr [rdi+18h], 0FFFFFFFEh
0x18003e63e  jnz     short loc_18003E664
0x18003e640  cmp     dword ptr [rdi+1Ch], 0FFFFFFFEh
0x18003e644  jnz     short loc_18003E694
0x18003e646  and     ebx, 0FFFFFFC0h
0x18003e649  mov     dword ptr [rdi], 4C494146h
0x18003e64f  mov     [rsp+38h+arg_0], ebx
0x18003e653  ldmxcsr [rsp+38h+arg_0]
0x18003e658  mov     rbx, [rsp+38h+arg_8]
0x18003e65d  add     rsp, 30h
0x18003e661  pop     rdi
0x18003e662  retn
0x18003e664  mov     rcx, [rdi+20h]; hdc
0x18003e668  lea     r9, [rdi+18h]; lpInData
0x18003e66c  mov     edx, 15h; iEscape
0x18003e671  mov     [rsp+38h+lpOutData], 0; lpOutData
0x18003e67a  mov     [rsp+38h+cjOutput], 0; cjOutput
0x18003e682  lea     r8d, [rdx-11h]; cjInput
0x18003e686  call    cs:__imp_ExtEscape
0x18003e68d  nop     dword ptr [rax+rax+00h]
0x18003e692  jmp     short loc_18003E640
0x18003e694  mov     rcx, [rdi+20h]; hdc
0x18003e698  lea     r9, [rdi+1Ch]; lpInData
0x18003e69c  mov     edx, 16h; iEscape
0x18003e6a1  mov     [rsp+38h+lpOutData], 0; lpOutData
0x18003e6aa  mov     [rsp+38h+cjOutput], 0; cjOutput
0x18003e6b2  lea     r8d, [rdx-12h]; cjInput
0x18003e6b6  call    cs:__imp_ExtEscape
0x18003e6bd  nop     dword ptr [rax+rax+00h]
0x18003e6c2  jmp     short loc_18003E646
```

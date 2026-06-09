# ConvertPenToGdi::~ConvertPenToGdi(void)

- ea: `0x18004c284`
- end: `0x18004c34f`
- name: `??1ConvertPenToGdi@@QEAA@XZ`
- size: `203`
- prototype: `void __fastcall(ConvertPenToGdi *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18004a970`
- `0x18004b0f0`
- `0x18013ac6c`

## callees

- `0x18004c284`

## import_xrefs

- `GDI32!SetMiterLimit` at `0x18004c2cc`
- `GDI32!SetMiterLimit` at `0x18004c2cc`
- `GDI32!ExtEscape` at `0x18004c31d`
- `GDI32!ExtEscape` at `0x18004c347`
- `GDI32!ExtEscape` at `0x18004c31d`
- `GDI32!ExtEscape` at `0x18004c347`
- `GDI32!DeleteObject` at `0x18004c2b4`
- `GDI32!DeleteObject` at `0x18004c2b4`

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
0x18004c284  mov     [rsp+arg_8], rbx
0x18004c289  push    rdi
0x18004c28a  sub     rsp, 30h
0x18004c28e  mov     rdi, rcx
0x18004c291  stmxcsr [rsp+38h+arg_0]
0x18004c296  mov     ebx, [rsp+38h+arg_0]
0x18004c29a  mov     eax, ebx
0x18004c29c  and     eax, 0FFFFFFC0h
0x18004c29f  cmp     dword ptr [rcx], 47764331h
0x18004c2a5  mov     [rsp+38h+arg_0], eax
0x18004c2a9  ldmxcsr [rsp+38h+arg_0]
0x18004c2ae  jnz     short loc_18004C2BA
0x18004c2b0  mov     rcx, [rcx+8]; ho
0x18004c2b4  call    cs:__imp_DeleteObject
0x18004c2ba  cmp     dword ptr [rdi+10h], 0
0x18004c2be  jz      short loc_18004C2D2
0x18004c2c0  movss   xmm1, dword ptr [rdi+14h]; limit
0x18004c2c5  xor     r8d, r8d; old
0x18004c2c8  mov     rcx, [rdi+20h]; hdc
0x18004c2cc  call    cs:__imp_SetMiterLimit
0x18004c2d2  cmp     dword ptr [rdi+18h], 0FFFFFFFEh
0x18004c2d6  jnz     short loc_18004C2FB
0x18004c2d8  cmp     dword ptr [rdi+1Ch], 0FFFFFFFEh
0x18004c2dc  jnz     short loc_18004C325
0x18004c2de  and     ebx, 0FFFFFFC0h
0x18004c2e1  mov     dword ptr [rdi], 4C494146h
0x18004c2e7  mov     [rsp+38h+arg_0], ebx
0x18004c2eb  ldmxcsr [rsp+38h+arg_0]
0x18004c2f0  mov     rbx, [rsp+38h+arg_8]
0x18004c2f5  add     rsp, 30h
0x18004c2f9  pop     rdi
0x18004c2fa  retn
0x18004c2fb  mov     rcx, [rdi+20h]; hdc
0x18004c2ff  lea     r9, [rdi+18h]; lpInData
0x18004c303  mov     edx, 15h; iEscape
0x18004c308  mov     [rsp+38h+lpOutData], 0; lpOutData
0x18004c311  mov     [rsp+38h+cjOutput], 0; cjOutput
0x18004c319  lea     r8d, [rdx-11h]; cjInput
0x18004c31d  call    cs:__imp_ExtEscape
0x18004c323  jmp     short loc_18004C2D8
0x18004c325  mov     rcx, [rdi+20h]; hdc
0x18004c329  lea     r9, [rdi+1Ch]; lpInData
0x18004c32d  mov     edx, 16h; iEscape
0x18004c332  mov     [rsp+38h+lpOutData], 0; lpOutData
0x18004c33b  mov     [rsp+38h+cjOutput], 0; cjOutput
0x18004c343  lea     r8d, [rdx-12h]; cjInput
0x18004c347  call    cs:__imp_ExtEscape
0x18004c34d  jmp     short loc_18004C2DE
```

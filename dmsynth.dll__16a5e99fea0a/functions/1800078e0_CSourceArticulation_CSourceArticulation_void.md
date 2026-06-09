# CSourceArticulation::CSourceArticulation(void)

- ea: `0x1800078e0`
- end: `0x1800079f9`
- name: `??0CSourceArticulation@@QEAA@XZ`
- size: `281`
- prototype: `CSourceArticulation *__fastcall(CSourceArticulation *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b30`
- `0x180008cb0`

## callees

- `0x180001d52`

## pseudocode

```c
CSourceArticulation *__fastcall CSourceArticulation::CSourceArticulation(CSourceArticulation *this)
{
  double v2; // xmm6_8
  double v3; // xmm0_8
  CSourceArticulation *result; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_WORD *)this + 25) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_WORD *)this + 40) = 0;
  *((_WORD *)this + 43) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_WORD *)this + 53) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_WORD *)this + 72) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_WORD *)this + 96) = 0;
  *(_DWORD *)((char *)this + 26) = 65536000;
  *(_DWORD *)((char *)this + 82) = 65536000;
  *((_DWORD *)this + 28) = 3804;
  *((_DWORD *)this + 40) = 3804;
  v2 = o_log_0(50.11363636363637);
  v3 = o_log_0(2.0);
  *(_DWORD *)((char *)this + 202) = 0x7FFF;
  *((_WORD *)this + 103) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_WORD *)this + 100) = (int)(v2 / v3 * 1200.0 + 6900.0);
  result = this;
  *((_QWORD *)this + 19) = 22050;
  *((_WORD *)this + 15) = 0;
  return result;
}

```

## disassembly

```asm
0x1800078e0  mov     [rsp+arg_0], rbx
0x1800078e5  push    rdi
0x1800078e6  sub     rsp, 30h
0x1800078ea  movsd   xmm0, cs:__real@40490e8ba2e8ba2f; X
0x1800078f2  xor     edi, edi
0x1800078f4  mov     [rcx], rdi
0x1800078f7  mov     rbx, rcx
0x1800078fa  mov     [rcx+8], rdi
0x1800078fe  mov     [rcx+10h], rdi
0x180007902  mov     [rcx+18h], di
0x180007906  mov     [rcx+20h], rdi
0x18000790a  mov     [rcx+28h], rdi
0x18000790e  mov     [rcx+32h], di
0x180007912  mov     [rcx+38h], rdi
0x180007916  mov     [rcx+40h], rdi
0x18000791a  mov     [rcx+48h], rdi
0x18000791e  mov     [rcx+50h], di
0x180007922  mov     [rcx+56h], di
0x180007926  mov     [rcx+58h], rdi
0x18000792a  mov     [rcx+60h], rdi
0x18000792e  mov     [rcx+6Ah], di
0x180007932  mov     [rcx+78h], rdi
0x180007936  mov     [rcx+80h], rdi
0x18000793d  mov     [rcx+88h], rdi
0x180007944  mov     [rcx+90h], di
0x18000794b  movaps  [rsp+38h+var_18], xmm6
0x180007950  mov     [rcx+0A8h], rdi
0x180007957  mov     [rcx+0B0h], rdi
0x18000795e  mov     [rcx+0B8h], rdi
0x180007965  mov     [rcx+0C0h], di
0x18000796c  mov     dword ptr [rcx+1Ah], 3E80000h
0x180007973  mov     dword ptr [rcx+52h], 3E80000h
0x18000797a  mov     dword ptr [rcx+70h], 0EDCh
0x180007981  mov     dword ptr [rcx+0A0h], 0EDCh
0x18000798b  call    _o_log_0
0x180007990  movaps  xmm6, xmm0
0x180007993  movsd   xmm0, cs:__real@4000000000000000; X
0x18000799b  call    _o_log_0
0x1800079a0  divsd   xmm6, xmm0
0x1800079a4  mov     dword ptr [rbx+0CAh], 7FFFh
0x1800079ae  mov     [rbx+0CEh], di
0x1800079b5  mov     [rbx+0D0h], rdi
0x1800079bc  mulsd   xmm6, cs:__real@4092c00000000000
0x1800079c4  addsd   xmm6, cs:__real@40baf40000000000
0x1800079cc  cvttsd2si eax, xmm6
0x1800079d0  movaps  xmm6, [rsp+38h+var_18]
0x1800079d5  mov     [rbx+0C8h], ax
0x1800079dc  mov     rax, rbx
0x1800079df  mov     qword ptr [rbx+98h], 5622h
0x1800079ea  mov     [rbx+1Eh], di
0x1800079ee  mov     rbx, [rsp+38h+arg_0]
0x1800079f3  add     rsp, 30h
0x1800079f7  pop     rdi
0x1800079f8  retn
```

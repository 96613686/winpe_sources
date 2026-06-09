# CSourceArticulation::Init(ulong)

- ea: `0x180009760`
- end: `0x18000987f`
- name: `?Init@CSourceArticulation@@QEAAXK@Z`
- size: `287`
- prototype: `void __fastcall(CSourceArticulation *__hidden this, unsigned int)`
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
void __fastcall CSourceArticulation::Init(CSourceArticulation *this, unsigned int a2)
{
  double v3; // xmm6_8
  double v4; // xmm0_8

  *((_DWORD *)this + 38) = a2;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 28) = 0x5000000 / a2;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_WORD *)this + 72) = 0;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *(_DWORD *)((char *)this + 26) = 65536000;
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = 0;
  *((_WORD *)this + 15) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_WORD *)this + 25) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *(_DWORD *)((char *)this + 82) = 65536000;
  *((_QWORD *)this + 9) = 0;
  *((_WORD *)this + 40) = 0;
  *((_WORD *)this + 43) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_WORD *)this + 53) = 0;
  *((_DWORD *)this + 40) = 0x5000000 / a2;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_WORD *)this + 96) = 0;
  v3 = o_log_0((double)(int)a2 / 440.0);
  v4 = o_log_0(2.0);
  *(_DWORD *)((char *)this + 202) = 0x7FFF;
  *((_WORD *)this + 103) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_WORD *)this + 100) = (int)(v3 / v4 * 1200.0 + 6900.0);
}

```

## disassembly

```asm
0x180009760  mov     [rsp+arg_0], rbx
0x180009765  push    rdi
0x180009766  sub     rsp, 30h
0x18000976a  xor     edi, edi
0x18000976c  mov     r10d, edx
0x18000976f  xorps   xmm0, xmm0
0x180009772  movaps  [rsp+38h+var_18], xmm6
0x180009777  xor     edx, edx
0x180009779  mov     [rcx+98h], r10d
0x180009780  mov     eax, 5000000h
0x180009785  mov     [rcx+78h], rdi
0x180009789  div     r10d
0x18000978c  cvtsi2sd xmm0, r10
0x180009791  mov     rbx, rcx
0x180009794  mov     [rcx+70h], eax
0x180009797  mov     [rcx+80h], rdi
0x18000979e  mov     [rcx+88h], rdi
0x1800097a5  mov     [rcx+90h], di
0x1800097ac  mov     [rcx], rdi
0x1800097af  divsd   xmm0, cs:__real@407b800000000000; X
0x1800097b7  mov     [rcx+8], rdi
0x1800097bb  mov     dword ptr [rcx+1Ah], 3E80000h
0x1800097c2  mov     [rcx+10h], rdi
0x1800097c6  mov     [rcx+18h], di
0x1800097ca  mov     [rcx+1Eh], di
0x1800097ce  mov     [rcx+20h], rdi
0x1800097d2  mov     [rcx+28h], rdi
0x1800097d6  mov     [rcx+32h], di
0x1800097da  mov     [rcx+38h], rdi
0x1800097de  mov     [rcx+40h], rdi
0x1800097e2  mov     dword ptr [rcx+52h], 3E80000h
0x1800097e9  mov     [rcx+48h], rdi
0x1800097ed  mov     [rcx+50h], di
0x1800097f1  mov     [rcx+56h], di
0x1800097f5  mov     [rcx+58h], rdi
0x1800097f9  mov     [rcx+60h], rdi
0x1800097fd  mov     [rcx+6Ah], di
0x180009801  mov     [rcx+0A0h], eax
0x180009807  mov     [rcx+0A8h], rdi
0x18000980e  mov     [rcx+0B0h], rdi
0x180009815  mov     [rcx+0B8h], rdi
0x18000981c  mov     [rcx+0C0h], di
0x180009823  call    _o_log_0
0x180009828  movaps  xmm6, xmm0
0x18000982b  movsd   xmm0, cs:__real@4000000000000000; X
0x180009833  call    _o_log_0
0x180009838  divsd   xmm6, xmm0
0x18000983c  mov     dword ptr [rbx+0CAh], 7FFFh
0x180009846  mov     [rbx+0CEh], di
0x18000984d  mov     [rbx+0D0h], rdi
0x180009854  mulsd   xmm6, cs:__real@4092c00000000000
0x18000985c  addsd   xmm6, cs:__real@40baf40000000000
0x180009864  cvttsd2si eax, xmm6
0x180009868  movaps  xmm6, [rsp+38h+var_18]
0x18000986d  mov     [rbx+0C8h], ax
0x180009874  mov     rbx, [rsp+38h+arg_0]
0x180009879  add     rsp, 30h
0x18000987d  pop     rdi
0x18000987e  retn
```

# UpdateCurve

- ea: `0x140085880`
- end: `0x140085953`
- name: `UpdateCurve`
- size: `211`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14003e980`
- `0x14005c378`
- `0x14007f4c0`

## callees

- `0x140050f10`
- `0x140066724`
- `0x140085880`

## pseudocode

```c
__int64 __fastcall UpdateCurve(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6)
{
  __int64 v7; // rdi
  __int64 result; // rax
  __int128 v9; // [rsp+30h] [rbp-88h] BYREF
  __int128 v10; // [rsp+40h] [rbp-78h]
  __int128 v11; // [rsp+50h] [rbp-68h]
  __int128 v12; // [rsp+60h] [rbp-58h] BYREF
  __int128 v13; // [rsp+70h] [rbp-48h]
  __int128 v14; // [rsp+80h] [rbp-38h]
  __int64 v15; // [rsp+90h] [rbp-28h]
  __int64 v16; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v17; // [rsp+C8h] [rbp+10h] BYREF
  __int64 v18; // [rsp+D0h] [rbp+18h] BYREF
  __int64 v19; // [rsp+D8h] [rbp+20h] BYREF

  v19 = a4;
  v18 = a3;
  v17 = a2;
  v16 = a1;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v7 = a5;
  if ( (unsigned __int8)PointWithinABC(a2, a5) != 1 || (result = PointWithinABC(a3, v7), (_BYTE)result != 1) )
  {
    DWORD2(v13) = a6;
    *(_QWORD *)&v10 = ABCLineTo;
    *(_QWORD *)&v14 = &v9;
    *(_QWORD *)&v12 = v7;
    return FixedFltn((unsigned int)&v16, (unsigned int)&v17, (unsigned int)&v18, (unsigned int)&v19, (__int64)&v12);
  }
  return result;
}

```

## disassembly

```asm
0x140085880  mov     r11, rsp
0x140085883  mov     [r11+20h], r9
0x140085887  mov     [r11+18h], r8
0x14008588b  mov     [rsp+arg_8], rdx
0x140085890  mov     [r11+8], rcx
0x140085894  push    rbx
0x140085895  push    rdi
0x140085896  sub     rsp, 0A8h
0x14008589d  mov     rbx, r8
0x1400858a0  mov     rax, rdx
0x1400858a3  xorps   xmm0, xmm0
0x1400858a6  xor     ecx, ecx
0x1400858a8  movups  [rsp+0B8h+var_58], xmm0
0x1400858ad  movups  [rsp+0B8h+var_48], xmm0
0x1400858b2  movups  xmmword ptr [r11-38h], xmm0
0x1400858b7  mov     [r11-28h], rcx
0x1400858bb  movups  [rsp+0B8h+var_88], xmm0
0x1400858c0  movups  [rsp+0B8h+var_78], xmm0
0x1400858c5  movups  [rsp+0B8h+var_68], xmm0
0x1400858ca  mov     rdi, [rsp+0B8h+arg_20]
0x1400858d2  mov     rdx, rdi
0x1400858d5  mov     rcx, rax
0x1400858d8  call    PointWithinABC
0x1400858dd  cmp     al, 1
0x1400858df  jnz     short loc_1400858F0
0x1400858e1  mov     rdx, rdi
0x1400858e4  mov     rcx, rbx
0x1400858e7  call    PointWithinABC
0x1400858ec  cmp     al, 1
0x1400858ee  jz      short loc_140085949
0x1400858f0  mov     eax, [rsp+0B8h+arg_28]
0x1400858f7  mov     dword ptr [rsp+0B8h+var_48+8], eax
0x1400858fb  lea     rax, ABCLineTo
0x140085902  mov     qword ptr [rsp+0B8h+var_78], rax
0x140085907  lea     rax, [rsp+0B8h+var_88]
0x14008590c  mov     qword ptr [rsp+0B8h+var_38], rax
0x140085914  mov     qword ptr [rsp+0B8h+var_58], rdi
0x140085919  lea     rax, [rsp+0B8h+var_58]
0x14008591e  mov     [rsp+0B8h+var_98], rax
0x140085923  lea     r9, [rsp+0B8h+arg_18]
0x14008592b  lea     r8, [rsp+0B8h+arg_10]
0x140085933  lea     rdx, [rsp+0B8h+arg_8]
0x14008593b  lea     rcx, [rsp+0B8h+arg_0]
0x140085943  call    FixedFltn
0x140085948  nop
0x140085949  add     rsp, 0A8h
0x140085950  pop     rdi
0x140085951  pop     rbx
0x140085952  retn
0x14009780f  push    rbp
0x140097811  sub     rsp, 30h
0x140097815  mov     rbp, rdx
0x140097818  add     rsp, 30h
0x14009781c  pop     rbp
0x14009781d  retn
```

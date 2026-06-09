# filecopy

- ea: `0x18000239c`
- end: `0x180002543`
- name: `filecopy`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001bd8`

## callees

- `0x18000239c`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall filecopy(
        __int64 a1,
        __int64 a2,
        unsigned int (__fastcall *a3)(__int64, __int64, _QWORD, __int64),
        _DWORD *a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        _DWORD *a8)
{
  __int64 v10; // rsi
  unsigned int (__fastcall *v11)(__int64, _QWORD, _QWORD, _DWORD *, __int64); // rax
  unsigned int v12; // eax
  unsigned int v13; // r14d
  __int64 v14; // rdx
  _DWORD *v15; // rax
  _DWORD *v17; // rcx
  _DWORD v18[4]; // [rsp+30h] [rbp-10h] BYREF

  v18[0] = 0;
  v10 = (*(__int64 (__fastcall **)(__int64))(a7 + 24))(0x8000);
  if ( v10 )
  {
    v11 = *(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, _DWORD *, __int64))(a7 + 72);
    v18[0] = 0;
    if ( v11(a2, 0, 0, v18, a6) == -1 )
    {
      (*(void (__fastcall **)(__int64))(a7 + 32))(v10);
      v17 = a8;
      *a8 = 4;
    }
    else
    {
      v18[0] = 0;
      while ( 1 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _DWORD *, __int64))(a7 + 48))(
                a2,
                v10,
                0x8000,
                v18,
                a6);
        v13 = v12;
        if ( !v12 )
        {
          (*(void (__fastcall **)(__int64))(a7 + 32))(v10);
          return 1;
        }
        if ( v12 > 0x8000 )
          break;
        v18[0] = 0;
        if ( v12 != (*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, _DWORD *, __int64))(a7 + 56))(
                      a1,
                      v10,
                      v12,
                      v18,
                      a6) )
          break;
        *a4 += v13;
        v14 = (unsigned int)*a4;
        v18[0] = 0;
        if ( a3(1, v14, a5, a6) == -1 )
        {
          (*(void (__fastcall **)(__int64))(a7 + 32))(v10);
          v15 = a8;
          *(_QWORD *)a8 = 7;
          goto LABEL_9;
        }
      }
      (*(void (__fastcall **)(__int64))(a7 + 32))(v10);
      v17 = a8;
      *a8 = 6;
    }
    v17[1] = v18[0];
    v17[2] = 1;
  }
  else
  {
    v15 = a8;
    *(_QWORD *)a8 = 3;
LABEL_9:
    v15[2] = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000239c  mov     rax, rsp
0x18000239f  mov     [rax+10h], rsi
0x1800023a3  mov     [rax+20h], rdi
0x1800023a7  mov     [rax+18h], r8
0x1800023ab  mov     [rax+8], rcx
0x1800023af  push    rbp
0x1800023b0  push    r12
0x1800023b2  push    r13
0x1800023b4  push    r14
0x1800023b6  push    r15
0x1800023b8  mov     rbp, rsp
0x1800023bb  sub     rsp, 40h
0x1800023bf  mov     rdi, [rbp+arg_30]
0x1800023c3  mov     ecx, 8000h
0x1800023c8  mov     r13, r9
0x1800023cb  mov     [rbp+var_10], 0
0x1800023d2  mov     r12, rdx
0x1800023d5  mov     rax, [rdi+18h]
0x1800023d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023de  mov     rsi, rax
0x1800023e1  test    rax, rax
0x1800023e4  jz      loc_1800024F7
0x1800023ea  mov     r15, [rbp+arg_28]
0x1800023ee  lea     r9, [rbp+var_10]
0x1800023f2  mov     rax, [rdi+48h]
0x1800023f6  xor     r8d, r8d
0x1800023f9  xor     edx, edx
0x1800023fb  mov     [rsp+40h+var_20], r15
0x180002400  mov     rcx, r12
0x180002403  mov     [rbp+var_10], 0
0x18000240a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240f  cmp     eax, 0FFFFFFFFh
0x180002412  jz      loc_180002504
0x180002418  mov     [rbp+var_10], 0
0x18000241f  mov     rax, [rdi+30h]
0x180002423  lea     r9, [rbp+var_10]
0x180002427  mov     r8d, 8000h
0x18000242d  mov     [rsp+40h+var_20], r15
0x180002432  mov     rdx, rsi
0x180002435  mov     rcx, r12
0x180002438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000243d  mov     r14d, eax
0x180002440  test    eax, eax
0x180002442  jz      loc_1800024CC
0x180002448  cmp     eax, 8000h
0x18000244d  ja      loc_18000252B
0x180002453  mov     rcx, [rbp+arg_0]
0x180002457  lea     r9, [rbp+var_10]
0x18000245b  mov     r8d, eax
0x18000245e  mov     [rbp+var_10], 0
0x180002465  mov     rax, [rdi+38h]
0x180002469  mov     rdx, rsi
0x18000246c  mov     [rsp+40h+var_20], r15
0x180002471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002476  cmp     r14d, eax
0x180002479  jnz     loc_18000252B
0x18000247f  add     [r13+0], r14d
0x180002483  mov     r9, r15
0x180002486  mov     edx, [r13+0]
0x18000248a  mov     ecx, 1
0x18000248f  mov     r8d, [rbp+arg_20]
0x180002493  mov     rax, [rbp+arg_10]
0x180002497  mov     [rbp+var_10], 0
0x18000249e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024a3  cmp     eax, 0FFFFFFFFh
0x1800024a6  jnz     loc_18000241F
0x1800024ac  mov     rax, [rdi+20h]
0x1800024b0  mov     rcx, rsi
0x1800024b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024b8  mov     rax, [rbp+arg_38]
0x1800024bc  mov     qword ptr [rax], 7
0x1800024c3  mov     dword ptr [rax+8], 1
0x1800024ca  jmp     short loc_180002527
0x1800024cc  mov     rax, [rdi+20h]
0x1800024d0  mov     rcx, rsi
0x1800024d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024d8  mov     eax, 1
0x1800024dd  lea     r11, [rsp+40h+var_s0]
0x1800024e2  mov     rsi, [r11+38h]
0x1800024e6  mov     rdi, [r11+48h]
0x1800024ea  mov     rsp, r11
0x1800024ed  pop     r15
0x1800024ef  pop     r14
0x1800024f1  pop     r13
0x1800024f3  pop     r12
0x1800024f5  pop     rbp
0x1800024f6  retn
0x1800024f7  mov     rax, [rbp+arg_38]
0x1800024fb  mov     qword ptr [rax], 3
0x180002502  jmp     short loc_1800024C3
0x180002504  mov     rax, [rdi+20h]
0x180002508  mov     rcx, rsi
0x18000250b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002510  mov     rcx, [rbp+arg_38]
0x180002514  mov     dword ptr [rcx], 4
0x18000251a  mov     eax, [rbp+var_10]
0x18000251d  mov     [rcx+4], eax
0x180002520  mov     dword ptr [rcx+8], 1
0x180002527  xor     eax, eax
0x180002529  jmp     short loc_1800024DD
0x18000252b  mov     rax, [rdi+20h]
0x18000252f  mov     rcx, rsi
0x180002532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002537  mov     rcx, [rbp+arg_38]
0x18000253b  mov     dword ptr [rcx], 6
0x180002541  jmp     short loc_18000251A
```

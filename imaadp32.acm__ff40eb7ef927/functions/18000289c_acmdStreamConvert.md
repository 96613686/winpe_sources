# acmdStreamConvert

- ea: `0x18000289c`
- end: `0x180002980`
- name: `acmdStreamConvert`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800020b0`
- `0x18000494c`

## callees

- `0x18000289c`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall acmdStreamConvert(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // r10d
  _WORD *v4; // rax
  __int64 v5; // rdi
  __int64 v7; // rsi
  unsigned int v8; // r8d
  unsigned int v9; // r11d
  unsigned int v10; // eax

  v3 = *(_DWORD *)(a3 + 64);
  v4 = *(_WORD **)(a2 + 4);
  v5 = *(_QWORD *)(a2 + 52);
  if ( *v4 == 1 )
  {
    v7 = *(_QWORD *)(a2 + 12);
    v8 = (unsigned __int16)v4[7] >> 3 << ((unsigned __int16)v4[1] >> 1);
    v9 = v8 * (*(_DWORD *)(a3 + 24) / v8 - *(_DWORD *)(a3 + 24) / v8 % *(unsigned __int16 *)(v7 + 18));
    if ( (v3 & 0x10) != 0 )
      *(_QWORD *)(v5 + 12) = 0;
  }
  else
  {
    v7 = *(_QWORD *)(a2 + 4);
    v9 = *(_DWORD *)(a3 + 24) - *(_DWORD *)(a3 + 24) % (unsigned int)(unsigned __int16)v4[6];
  }
  v10 = v9;
  if ( (v3 & 4) == 0 )
    v10 = *(_DWORD *)(a3 + 24);
  *(_DWORD *)(a3 + 28) = v10;
  *(_DWORD *)(a3 + 52) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, __int64, __int64))v5)(
                           *(_QWORD *)(a3 + 16),
                           v9,
                           *(_QWORD *)(a3 + 40),
                           *(unsigned int *)(a3 + 48),
                           *(unsigned __int16 *)(v7 + 12),
                           *(unsigned __int16 *)(v7 + 18),
                           v5 + 12,
                           v5 + 16);
  return 0;
}

```

## disassembly

```asm
0x18000289c  mov     [rsp+arg_0], rbx
0x1800028a1  mov     [rsp+arg_8], rsi
0x1800028a6  push    rdi
0x1800028a7  sub     rsp, 50h
0x1800028ab  mov     r10d, [r8+40h]
0x1800028af  mov     ecx, 1
0x1800028b4  mov     rax, [rdx+4]
0x1800028b8  mov     r9d, r10d
0x1800028bb  mov     rdi, [rdx+34h]
0x1800028bf  and     r9d, 4
0x1800028c3  mov     rbx, r8
0x1800028c6  cmp     cx, [rax]
0x1800028c9  jnz     short loc_18000290B
0x1800028cb  mov     rsi, [rdx+0Ch]
0x1800028cf  xor     edx, edx
0x1800028d1  movzx   r8d, word ptr [rax+0Eh]
0x1800028d6  movzx   ecx, word ptr [rax+2]
0x1800028da  mov     eax, [rbx+18h]
0x1800028dd  shr     ecx, 1
0x1800028df  shr     r8d, 3
0x1800028e3  shl     r8d, cl
0x1800028e6  movzx   ecx, word ptr [rsi+12h]
0x1800028ea  div     r8d
0x1800028ed  xor     edx, edx
0x1800028ef  mov     r11d, eax
0x1800028f2  div     ecx
0x1800028f4  sub     r11d, edx
0x1800028f7  imul    r11d, r8d
0x1800028fb  test    r10b, 10h
0x1800028ff  jz      short loc_180002920
0x180002901  mov     qword ptr [rdi+0Ch], 0
0x180002909  jmp     short loc_180002920
0x18000290b  mov     r11d, [r8+18h]
0x18000290f  mov     rsi, rax
0x180002912  movzx   ecx, word ptr [rax+0Ch]
0x180002916  xor     edx, edx
0x180002918  mov     eax, r11d
0x18000291b  div     ecx
0x18000291d  sub     r11d, edx
0x180002920  mov     eax, r11d
0x180002923  test    r9d, r9d
0x180002926  jnz     short loc_18000292B
0x180002928  mov     eax, [rbx+18h]
0x18000292b  mov     [rbx+1Ch], eax
0x18000292e  lea     rcx, [rdi+10h]
0x180002932  movzx   r9d, word ptr [rsi+12h]
0x180002937  lea     r8, [rdi+0Ch]
0x18000293b  movzx   r10d, word ptr [rsi+0Ch]
0x180002940  mov     edx, r11d
0x180002943  mov     rax, [rdi]
0x180002946  mov     [rsp+58h+var_20], rcx
0x18000294b  mov     rcx, [rbx+10h]
0x18000294f  mov     [rsp+58h+var_28], r8
0x180002954  mov     r8, [rbx+28h]
0x180002958  mov     [rsp+58h+var_30], r9d
0x18000295d  mov     r9d, [rbx+30h]
0x180002961  mov     [rsp+58h+var_38], r10d
0x180002966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000296b  mov     rsi, [rsp+58h+arg_8]
0x180002970  mov     [rbx+34h], eax
0x180002973  xor     eax, eax
0x180002975  mov     rbx, [rsp+58h+arg_0]
0x18000297a  add     rsp, 50h
0x18000297e  pop     rdi
0x18000297f  retn
```

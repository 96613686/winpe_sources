# MRxDAVExtractNetRootName

- ea: `0x1400193d0`
- end: `0x1400194e9`
- name: `MRxDAVExtractNetRootName`
- size: `281`
- prototype: `__int16 __fastcall(unsigned __int16 *, __int64, __int64, __int128 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002ac4`
- `0x1400031b4`
- `0x1400193d0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140019470`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400194b5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019470`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400194b5`

## pseudocode

```c
__int16 __fastcall MRxDAVExtractNetRootName(unsigned __int16 *a1, __int64 a2, __int64 a3, __int128 *a4)
{
  __int64 v4; // r11
  unsigned __int16 *v6; // rax
  unsigned __int64 v7; // rbx
  _WORD *v10; // r8
  _WORD *v11; // rcx
  __int128 *v12; // rsi
  __int16 result; // ax
  __int16 v14; // bx
  __int64 v15; // rbx
  unsigned int CurrentThreadId; // eax
  __int64 v17; // rbx
  __int64 v18; // rdi
  unsigned int v19; // eax
  int v20; // edx
  int v21; // r8d
  __int128 v22; // [rsp+40h] [rbp-48h] BYREF

  v4 = *((_QWORD *)a1 + 1);
  v6 = *(unsigned __int16 **)(a2 + 64);
  v7 = v4 + *a1;
  v22 = 0;
  v10 = (_WORD *)(v4 + 2 * ((unsigned __int64)*v6 >> 1));
  v11 = v10;
  *(_QWORD *)(a3 + 8) = v10;
  while ( (unsigned __int64)v10 < v7 && (*v10 != 92 || v10 == v11) )
    ++v10;
  v12 = &v22;
  result = (_WORD)v10 - (_WORD)v11;
  *(_WORD *)(a3 + 2) = (_WORD)v10 - (_WORD)v11;
  *(_WORD *)a3 = (_WORD)v10 - (_WORD)v11;
  if ( a4 )
    v12 = a4;
  v14 = v7 - (_WORD)v10;
  *((_QWORD *)v12 + 1) = v10;
  *((_WORD *)v12 + 1) = v14;
  *(_WORD *)v12 = v14;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
      result = WPP_SF_qZ(
                 v15,
                 66,
                 (unsigned int)WPP_295ecfbeda123026d67516205ca0d119_Traceguids,
                 CurrentThreadId,
                 (__int64)a1);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v17 = *(_QWORD *)(a2 + 64);
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v19 = (unsigned int)PsGetCurrentThreadId();
      return WPP_SF_qZZZ(v18, v20, v21, v19, v17, a3, (__int64)v12);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400193d0  push    rbx
0x1400193d2  push    rbp
0x1400193d3  push    rsi
0x1400193d4  push    rdi
0x1400193d5  push    r12
0x1400193d7  push    r14
0x1400193d9  sub     rsp, 58h
0x1400193dd  mov     r11, [rcx+8]
0x1400193e1  mov     r14, r8
0x1400193e4  movzx   ebx, word ptr [rcx]
0x1400193e7  xorps   xmm0, xmm0
0x1400193ea  mov     rax, [rdx+40h]
0x1400193ee  add     rbx, r11
0x1400193f1  movups  [rsp+88h+var_48], xmm0
0x1400193f6  mov     rdi, rcx
0x1400193f9  mov     rbp, rdx
0x1400193fc  movzx   r10d, word ptr [rax]
0x140019400  shr     r10, 1
0x140019403  lea     r8, [r11+r10*2]
0x140019407  mov     rcx, r8
0x14001940a  mov     [r14+8], r8
0x14001940e  jmp     short loc_140019420
0x140019410  cmp     word ptr [r8], 5Ch ; '\'
0x140019415  jnz     short loc_14001941C
0x140019417  cmp     r8, rcx
0x14001941a  jnz     short loc_140019425
0x14001941c  add     r8, 2
0x140019420  cmp     r8, rbx
0x140019423  jb      short loc_140019410
0x140019425  movzx   eax, r8w
0x140019429  lea     rsi, [rsp+88h+var_48]
0x14001942e  sub     ax, cx
0x140019431  mov     [r14+2], ax
0x140019436  test    r9, r9
0x140019439  mov     [r14], ax
0x14001943d  cmovnz  rsi, r9
0x140019441  sub     bx, r8w
0x140019445  mov     [rsi+8], r8
0x140019449  mov     [rsi+2], bx
0x14001944d  mov     [rsi], bx
0x140019450  mov     rbx, cs:WPP_GLOBAL_Control
0x140019457  lea     r12, WPP_GLOBAL_Control
0x14001945e  cmp     rbx, r12
0x140019461  jz      short loc_1400194DB
0x140019463  test    dword ptr [rbx+2Ch], 4000h
0x14001946a  jz      short loc_140019498
0x14001946c  mov     rbx, [rbx+18h]
0x140019470  call    cs:__imp_PsGetCurrentThreadId
0x140019477  nop     dword ptr [rax+rax+00h]
0x14001947c  mov     edx, 42h ; 'B'
0x140019481  mov     [rsp+88h+var_68], rdi
0x140019486  mov     r9, rax
0x140019489  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140019490  mov     rcx, rbx
0x140019493  call    WPP_SF_qZ
0x140019498  mov     rdi, cs:WPP_GLOBAL_Control
0x14001949f  cmp     rdi, r12
0x1400194a2  jz      short loc_1400194DB
0x1400194a4  test    dword ptr [rdi+2Ch], 4000h
0x1400194ab  jz      short loc_1400194DB
0x1400194ad  mov     rbx, [rbp+40h]
0x1400194b1  mov     rdi, [rdi+18h]
0x1400194b5  call    cs:__imp_PsGetCurrentThreadId
0x1400194bc  nop     dword ptr [rax+rax+00h]
0x1400194c1  mov     [rsp+88h+var_58], rsi
0x1400194c6  mov     rcx, rdi
0x1400194c9  mov     r9, rax
0x1400194cc  mov     [rsp+88h+var_60], r14
0x1400194d1  mov     [rsp+88h+var_68], rbx
0x1400194d6  call    WPP_SF_qZZZ
0x1400194db  add     rsp, 58h
0x1400194df  pop     r14
0x1400194e1  pop     r12
0x1400194e3  pop     rdi
0x1400194e4  pop     rsi
0x1400194e5  pop     rbp
0x1400194e6  pop     rbx
0x1400194e7  retn
```

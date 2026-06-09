# CDisplay::GetViewRect(tagRECT &,tagRECT const *)

- ea: `0x18000c260`
- end: `0x18000c6e9`
- name: `?GetViewRect@CDisplay@@QEAAXAEAUtagRECT@@PEBU2@@Z`
- size: `1161`
- prototype: `void __fastcall(CDisplay *__hidden this, struct tagRECT *, const struct tagRECT *)`
- caller_count: `26`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ec10`
- `0x18001f580`
- `0x1800200d0`
- `0x180039460`
- `0x18003f580`
- `0x180040e04`
- `0x180045260`
- `0x1800566f0`
- `0x180057cec`
- `0x180057f58`
- `0x180058104`
- `0x180058554`
- `0x180058fa0`
- `0x180059d70`
- `0x180059f10`
- `0x18005a420`
- `0x18005a880`
- `0x18005d310`
- `0x18005dce8`
- `0x1800703b0`
- `0x180081f34`
- `0x180082298`
- `0x180082c68`
- `0x180084df0`
- `0x18008ab20`
- `0x18008bae0`

## callees

- `0x18000c260`
- `0x18000c6f0`
- `0x18000da20`
- `0x18000e67c`
- `0x180039990`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18000c378`
- `KERNEL32!MulDiv` at `0x18000c58d`
- `KERNEL32!MulDiv` at `0x18000c5a6`
- `KERNEL32!MulDiv` at `0x18000c5c1`
- `KERNEL32!MulDiv` at `0x18000c5d7`
- `KERNEL32!MulDiv` at `0x18000c5f4`
- `KERNEL32!MulDiv` at `0x18000c65f`
- `KERNEL32!MulDiv` at `0x18000c68b`
- `KERNEL32!MulDiv` at `0x18000c378`
- `KERNEL32!MulDiv` at `0x18000c58d`
- `KERNEL32!MulDiv` at `0x18000c5a6`
- `KERNEL32!MulDiv` at `0x18000c5c1`
- `KERNEL32!MulDiv` at `0x18000c5d7`
- `KERNEL32!MulDiv` at `0x18000c5f4`
- `KERNEL32!MulDiv` at `0x18000c65f`
- `KERNEL32!MulDiv` at `0x18000c68b`

## pseudocode

```c
void __fastcall CDisplay::GetViewRect(CDisplay *this, struct tagRECT *a2, const struct tagRECT *a3)
{
  __int64 v5; // rax
  int v6; // r13d
  int v7; // ebp
  int v8; // r15d
  __int64 v9; // rax
  int v10; // ebp
  int v11; // edx
  int v12; // edx
  int v13; // r12d
  int ZoomDenominator; // eax
  __int64 v15; // rcx
  int v16; // edx
  int v17; // edx
  __int16 *v18; // r8
  __int64 v19; // rax
  int v20; // ebp
  int v21; // r15d
  int v22; // edx
  int v23; // edx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // edx
  int v28; // eax
  int v29; // edx
  int v30; // eax
  int v31; // [rsp+20h] [rbp-68h] BYREF
  int v32; // [rsp+24h] [rbp-64h] BYREF
  int v33[2]; // [rsp+28h] [rbp-60h] BYREF
  int nNumber[4]; // [rsp+30h] [rbp-58h] BYREF

  if ( a3 )
    *a2 = *a3;
  else
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 48LL) + 192LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 48LL));
  *((_DWORD *)this + 17) = a2->bottom - a2->top;
  v5 = *((_QWORD *)this + 2);
  *(_OWORD *)nNumber = 0;
  if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v5 + 48) + 200LL))(*(_QWORD *)(v5 + 48), nNumber) < 0 )
  {
    v20 = 0;
    v13 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
    v6 = _mm_cvtsi128_si32((__m128i)0LL);
    goto LABEL_47;
  }
  v6 = nNumber[0];
  v7 = nNumber[2];
  v8 = nNumber[1];
  v31 = nNumber[2];
  v32 = nNumber[3];
  if ( !nNumber[0] )
  {
    v6 = 0;
    goto LABEL_20;
  }
  v9 = *((_QWORD *)this + 2);
  if ( !*(_WORD *)(v9 + 204) )
  {
    v10 = *((_DWORD *)this + 19);
    if ( v10 )
    {
      v27 = *((__int16 *)this + 19);
      if ( v27 == 2540 )
      {
LABEL_9:
        if ( v10 <= 0 )
          v10 = 1;
        goto LABEL_11;
      }
      v28 = MulDiv(v10, v27, 2540);
    }
    else
    {
      v10 = *((_DWORD *)this + 17);
      *(_QWORD *)v33 = 0;
      if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v9 + 48) + 272LL))(*(_QWORD *)(v9 + 48), v33) < 0 )
      {
LABEL_8:
        v9 = *((_QWORD *)this + 2);
        goto LABEL_9;
      }
      v28 = CW32System::MulDiv(v33[1], *((__int16 *)this + 19), 2540);
    }
    v10 = v28;
    goto LABEL_8;
  }
  v10 = *(unsigned __int16 *)(v9 + 204);
LABEL_11:
  v11 = *(unsigned __int16 *)(v9 + 202);
  if ( !*(_WORD *)(v9 + 202) )
  {
    v11 = 1;
    if ( *((int *)this + 17) > 0 )
      v11 = *((_DWORD *)this + 17);
  }
  if ( v11 != v10 )
    v6 = MulDiv(v6, v11, v10);
  v12 = *((__int16 *)this + 18);
  if ( v12 != 2540 && v6 )
    v6 = MulDiv(v6, v12, 2540);
  v7 = v31;
LABEL_20:
  if ( v8 )
  {
    v13 = nNumber[1];
    ZoomDenominator = CDisplay::GetZoomDenominator(this);
    v15 = *((_QWORD *)this + 2);
    v16 = *(unsigned __int16 *)(v15 + 202);
    if ( !*(_WORD *)(v15 + 202) )
    {
      v16 = 1;
      if ( *((int *)this + 17) > 0 )
        v16 = *((_DWORD *)this + 17);
    }
    if ( v16 != ZoomDenominator && (!ZoomDenominator || v13) )
      v13 = MulDiv(v13, v16, ZoomDenominator);
    v17 = *((__int16 *)this + 19);
    v18 = (__int16 *)((char *)this + 38);
    if ( v17 != 2540 && v13 )
    {
      v13 = MulDiv(v13, v17, 2540);
      v18 = (__int16 *)((char *)this + 38);
    }
  }
  else
  {
    v13 = 0;
    v18 = (__int16 *)((char *)this + 38);
  }
  if ( !v7 )
  {
    v20 = 0;
    goto LABEL_46;
  }
  v19 = *((_QWORD *)this + 2);
  v20 = nNumber[2];
  if ( !*(_WORD *)(v19 + 204) )
  {
    v21 = *((_DWORD *)this + 19);
    if ( v21 )
    {
      v29 = *v18;
      if ( v29 == 2540 )
      {
LABEL_35:
        if ( v21 <= 0 )
          v21 = 1;
        goto LABEL_37;
      }
      v30 = MulDiv(v21, v29, 2540);
    }
    else
    {
      v21 = *((_DWORD *)this + 17);
      *(_QWORD *)v33 = 0;
      if ( (*(int (__fastcall **)(_QWORD, int *, __int16 *))(**(_QWORD **)(v19 + 48) + 272LL))(
             *(_QWORD *)(v19 + 48),
             v33,
             v18) < 0 )
      {
LABEL_34:
        v19 = *((_QWORD *)this + 2);
        goto LABEL_35;
      }
      v30 = CW32System::MulDiv(v33[1], *((__int16 *)this + 19), 2540);
    }
    v21 = v30;
    goto LABEL_34;
  }
  v21 = *(unsigned __int16 *)(v19 + 204);
LABEL_37:
  v22 = *(unsigned __int16 *)(v19 + 202);
  if ( !*(_WORD *)(v19 + 202) )
  {
    v22 = 1;
    if ( *((int *)this + 17) > 0 )
      v22 = *((_DWORD *)this + 17);
  }
  if ( v22 != v21 && v20 )
    v20 = MulDiv(v20, v22, v21);
  v23 = *((__int16 *)this + 18);
  if ( v23 != 2540 && v20 )
    v20 = MulDiv(v20, v23, 2540);
LABEL_46:
  if ( v32 )
  {
    v24 = CDisplay::HimetricYtoDY(this, nNumber[3]);
    goto LABEL_48;
  }
LABEL_47:
  v24 = 0;
LABEL_48:
  a2->left += v6;
  a2->top += v13;
  a2->right -= v20;
  a2->bottom -= v24;
  v25 = *((_QWORD *)this + 2);
  if ( (*(_DWORD *)(v25 + 180) & 0x2000000) != 0
    && (v26 = *(_QWORD *)(v25 + 48),
        v32 = 0,
        v31 = 0,
        (*(void (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v26 + 400LL))(v26, &v32, &v31),
        (v31 & 0x4000) != 0) )
  {
    a2->right -= CDisplay::GetSelBarInPixels(this);
  }
  else
  {
    a2->left += CDisplay::GetSelBarInPixels(this);
  }
}

```

## disassembly

```asm
0x18000c260  mov     r11, rsp
0x18000c263  push    rbx
0x18000c264  push    rdi
0x18000c265  sub     rsp, 78h
0x18000c269  mov     rax, cs:__security_cookie
0x18000c270  xor     rax, rsp
0x18000c273  mov     [rsp+88h+var_48], rax
0x18000c278  mov     [r11+18h], rbp
0x18000c27c  mov     rbx, rdx
0x18000c27f  mov     [r11-20h], r12
0x18000c283  mov     rdi, rcx
0x18000c286  mov     [r11-28h], r13
0x18000c28a  mov     [r11-30h], r14
0x18000c28e  test    r8, r8
0x18000c291  jz      loc_18000C61B
0x18000c297  movups  xmm0, xmmword ptr [r8]
0x18000c29b  movups  xmmword ptr [rdx], xmm0
0x18000c29e  mov     eax, [rbx+0Ch]
0x18000c2a1  lea     rdx, [rsp+88h+nNumber]
0x18000c2a6  sub     eax, [rbx+4]
0x18000c2a9  xorps   xmm0, xmm0
0x18000c2ac  mov     [rdi+44h], eax
0x18000c2af  mov     rax, [rdi+10h]
0x18000c2b3  movups  xmmword ptr [rsp+88h+nNumber], xmm0
0x18000c2b8  mov     [rsp+88h+var_18], rsi
0x18000c2bd  mov     rcx, [rax+30h]
0x18000c2c1  mov     rax, [rcx]
0x18000c2c4  mov     rax, [rax+0C8h]
0x18000c2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2d0  xor     esi, esi
0x18000c2d2  test    eax, eax
0x18000c2d4  js      loc_18000C55C
0x18000c2da  mov     r13d, [rsp+88h+nNumber]
0x18000c2df  mov     ebp, [rsp+88h+nNumber+8]
0x18000c2e3  mov     eax, [rsp+88h+nNumber+0Ch]
0x18000c2e7  mov     [rsp+88h+var_38], r15
0x18000c2ec  mov     r15d, [rsp+88h+nNumber+4]
0x18000c2f1  mov     [rsp+88h+var_68], ebp
0x18000c2f5  mov     [rsp+88h+var_64], eax
0x18000c2f9  test    r13d, r13d
0x18000c2fc  jz      loc_18000C6C5
0x18000c302  mov     rax, [rdi+10h]
0x18000c306  movzx   ecx, word ptr [rax+0CCh]
0x18000c30d  test    cx, cx
0x18000c310  jnz     loc_18000C60C
0x18000c316  mov     ebp, [rdi+4Ch]
0x18000c319  test    ebp, ebp
0x18000c31b  jnz     loc_18000C647
0x18000c321  mov     ebp, [rdi+44h]
0x18000c324  lea     rdx, [rsp+88h+var_60]
0x18000c329  mov     qword ptr [rsp+88h+var_60], rsi
0x18000c32e  mov     rcx, [rax+30h]
0x18000c332  mov     rax, [rcx]
0x18000c335  mov     rax, [rax+110h]
0x18000c33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c341  test    eax, eax
0x18000c343  jns     loc_18000C6B0
0x18000c349  mov     rax, [rdi+10h]
0x18000c34d  test    ebp, ebp
0x18000c34f  jg      short loc_18000C356
0x18000c351  mov     ebp, 1
0x18000c356  movzx   edx, word ptr [rax+0CAh]
0x18000c35d  test    edx, edx
0x18000c35f  jnz     short loc_18000C36E
0x18000c361  mov     eax, [rdi+44h]
0x18000c364  mov     edx, 1
0x18000c369  test    eax, eax
0x18000c36b  cmovg   edx, eax; nNumerator
0x18000c36e  cmp     edx, ebp
0x18000c370  jz      short loc_18000C387
0x18000c372  mov     r8d, ebp; nDenominator
0x18000c375  mov     ecx, r13d; nNumber
0x18000c378  call    cs:__imp_MulDiv
0x18000c37f  nop     dword ptr [rax+rax+00h]
0x18000c384  mov     r13d, eax
0x18000c387  movsx   edx, word ptr [rdi+24h]; nNumerator
0x18000c38b  cmp     edx, 9ECh
0x18000c391  jz      short loc_18000C39C
0x18000c393  test    r13d, r13d
0x18000c396  jnz     loc_18000C584
0x18000c39c  mov     ebp, [rsp+88h+var_68]
0x18000c3a0  test    r15d, r15d
0x18000c3a3  jz      loc_18000C578
0x18000c3a9  mov     r12d, [rsp+88h+nNumber+4]
0x18000c3ae  mov     rcx, rdi; this
0x18000c3b1  call    ?GetZoomDenominator@CDisplay@@QEBAJXZ; CDisplay::GetZoomDenominator(void)
0x18000c3b6  mov     rcx, [rdi+10h]
0x18000c3ba  mov     r8d, eax; nDenominator
0x18000c3bd  movzx   edx, word ptr [rcx+0CAh]
0x18000c3c4  test    edx, edx
0x18000c3c6  jnz     short loc_18000C3D5
0x18000c3c8  mov     eax, [rdi+44h]
0x18000c3cb  mov     edx, 1
0x18000c3d0  test    eax, eax
0x18000c3d2  cmovg   edx, eax; nNumerator
0x18000c3d5  cmp     edx, r8d
0x18000c3d8  jz      short loc_18000C3EC
0x18000c3da  test    r8d, r8d
0x18000c3dd  jz      loc_18000C5D4
0x18000c3e3  test    r12d, r12d
0x18000c3e6  jnz     loc_18000C5D4
0x18000c3ec  movsx   edx, word ptr [rdi+26h]; nNumerator
0x18000c3f0  lea     r8, [rdi+26h]
0x18000c3f4  test    sil, sil
0x18000c3f7  jnz     short loc_18000C40A
0x18000c3f9  cmp     edx, 9ECh
0x18000c3ff  jz      short loc_18000C40A
0x18000c401  test    r12d, r12d
0x18000c404  jnz     loc_18000C5EB
0x18000c40a  test    ebp, ebp
0x18000c40c  jz      loc_18000C6E2
0x18000c412  mov     rax, [rdi+10h]
0x18000c416  mov     ebp, [rsp+88h+nNumber+8]
0x18000c41a  movzx   ecx, word ptr [rax+0CCh]
0x18000c421  test    cx, cx
0x18000c424  jnz     loc_18000C613
0x18000c42a  mov     r15d, [rdi+4Ch]
0x18000c42e  test    r15d, r15d
0x18000c431  jnz     loc_18000C672
0x18000c437  mov     r15d, [rdi+44h]
0x18000c43b  lea     rdx, [rsp+88h+var_60]
0x18000c440  mov     qword ptr [rsp+88h+var_60], rsi
0x18000c445  mov     rcx, [rax+30h]
0x18000c449  mov     rax, [rcx]
0x18000c44c  mov     rax, [rax+110h]
0x18000c453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c458  test    eax, eax
0x18000c45a  jns     loc_18000C6CD
0x18000c460  mov     rax, [rdi+10h]
0x18000c464  test    r15d, r15d
0x18000c467  jle     loc_18000C551
0x18000c46d  movzx   edx, word ptr [rax+0CAh]
0x18000c474  test    edx, edx
0x18000c476  jnz     short loc_18000C485
0x18000c478  mov     eax, [rdi+44h]
0x18000c47b  mov     edx, 1
0x18000c480  test    eax, eax
0x18000c482  cmovg   edx, eax; nNumerator
0x18000c485  cmp     edx, r15d
0x18000c488  jz      short loc_18000C49B
0x18000c48a  test    r15d, r15d
0x18000c48d  jz      loc_18000C5A1
0x18000c493  test    ebp, ebp
0x18000c495  jnz     loc_18000C5A1
0x18000c49b  movsx   edx, word ptr [rdi+24h]; nNumerator
0x18000c49f  test    sil, sil
0x18000c4a2  jnz     short loc_18000C4B4
0x18000c4a4  cmp     edx, 9ECh
0x18000c4aa  jz      short loc_18000C4B4
0x18000c4ac  test    ebp, ebp
0x18000c4ae  jnz     loc_18000C5B9
0x18000c4b4  cmp     [rsp+88h+var_64], 0
0x18000c4b9  mov     r15, [rsp+88h+var_38]
0x18000c4be  jnz     loc_18000C69F
0x18000c4c4  mov     eax, esi
0x18000c4c6  add     [rbx], r13d
0x18000c4c9  add     [rbx+4], r12d
0x18000c4cd  sub     [rbx+8], ebp
0x18000c4d0  sub     [rbx+0Ch], eax
0x18000c4d3  mov     rcx, [rdi+10h]
0x18000c4d7  mov     r14, [rsp+88h+var_30]
0x18000c4dc  mov     r13, [rsp+88h+var_28]
0x18000c4e1  mov     r12, [rsp+88h+var_20]
0x18000c4e6  test    dword ptr [rcx+0B4h], 2000000h
0x18000c4f0  mov     rbp, [rsp+88h+arg_10]
0x18000c4f8  jz      short loc_18000C52D
0x18000c4fa  mov     rcx, [rcx+30h]
0x18000c4fe  lea     r8, [rsp+88h+var_68]
0x18000c503  mov     [rsp+88h+var_64], esi
0x18000c507  lea     rdx, [rsp+88h+var_64]
0x18000c50c  mov     [rsp+88h+var_68], esi
0x18000c510  mov     rax, [rcx]
0x18000c513  mov     rax, [rax+190h]
0x18000c51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c51f  test    [rsp+88h+var_68], 4000h
0x18000c527  jnz     loc_18000C637
0x18000c52d  mov     rcx, rdi; this
0x18000c530  call    ?GetSelBarInPixels@CDisplay@@IEAAJXZ; CDisplay::GetSelBarInPixels(void)
0x18000c535  add     [rbx], eax
0x18000c537  mov     rsi, [rsp+88h+var_18]
0x18000c53c  mov     rcx, [rsp+88h+var_48]
0x18000c541  xor     rcx, rsp; StackCookie
0x18000c544  call    __security_check_cookie
0x18000c549  add     rsp, 78h
0x18000c54d  pop     rdi
0x18000c54e  pop     rbx
0x18000c54f  retn
0x18000c551  mov     r15d, 1
0x18000c557  jmp     loc_18000C46D
0x18000c55c  xorps   xmm0, xmm0
0x18000c55f  xorps   xmm1, xmm1
0x18000c562  psrldq  xmm0, 4
0x18000c567  mov     ebp, esi
0x18000c569  movd    r12d, xmm0
0x18000c56e  movd    r13d, xmm1
0x18000c573  jmp     loc_18000C4C4
0x18000c578  mov     r12d, esi
0x18000c57b  lea     r8, [rdi+26h]
0x18000c57f  jmp     loc_18000C40A
0x18000c584  mov     r8d, 9ECh; nDenominator
0x18000c58a  mov     ecx, r13d; nNumber
0x18000c58d  call    cs:__imp_MulDiv
0x18000c594  nop     dword ptr [rax+rax+00h]
0x18000c599  mov     r13d, eax
0x18000c59c  jmp     loc_18000C39C
0x18000c5a1  mov     r8d, r15d; nDenominator
0x18000c5a4  mov     ecx, ebp; nNumber
0x18000c5a6  call    cs:__imp_MulDiv
0x18000c5ad  nop     dword ptr [rax+rax+00h]
0x18000c5b2  mov     ebp, eax
0x18000c5b4  jmp     loc_18000C49B
0x18000c5b9  mov     r8d, 9ECh; nDenominator
0x18000c5bf  mov     ecx, ebp; nNumber
0x18000c5c1  call    cs:__imp_MulDiv
0x18000c5c8  nop     dword ptr [rax+rax+00h]
0x18000c5cd  mov     ebp, eax
0x18000c5cf  jmp     loc_18000C4B4
0x18000c5d4  mov     ecx, r12d; nNumber
0x18000c5d7  call    cs:__imp_MulDiv
0x18000c5de  nop     dword ptr [rax+rax+00h]
0x18000c5e3  mov     r12d, eax
0x18000c5e6  jmp     loc_18000C3EC
0x18000c5eb  mov     r8d, 9ECh; nDenominator
0x18000c5f1  mov     ecx, r12d; nNumber
0x18000c5f4  call    cs:__imp_MulDiv
0x18000c5fb  nop     dword ptr [rax+rax+00h]
0x18000c600  mov     r12d, eax
0x18000c603  lea     r8, [rdi+26h]
0x18000c607  jmp     loc_18000C40A
0x18000c60c  mov     ebp, ecx
0x18000c60e  jmp     loc_18000C356
0x18000c613  mov     r15d, ecx
0x18000c616  jmp     loc_18000C46D
0x18000c61b  mov     rax, [rcx+10h]
0x18000c61f  mov     rcx, [rax+30h]
0x18000c623  mov     rax, [rcx]
0x18000c626  mov     rax, [rax+0C0h]
0x18000c62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c632  jmp     loc_18000C29E
0x18000c637  mov     rcx, rdi; this
0x18000c63a  call    ?GetSelBarInPixels@CDisplay@@IEAAJXZ; CDisplay::GetSelBarInPixels(void)
0x18000c63f  sub     [rbx+8], eax
0x18000c642  jmp     loc_18000C537
0x18000c647  movsx   edx, word ptr [rdi+26h]; nNumerator
0x18000c64b  cmp     edx, 9ECh
0x18000c651  jz      loc_18000C34D
0x18000c657  mov     r8d, 9ECh; nDenominator
0x18000c65d  mov     ecx, ebp; nNumber
0x18000c65f  call    cs:__imp_MulDiv
0x18000c666  nop     dword ptr [rax+rax+00h]
0x18000c66b  mov     ebp, eax
0x18000c66d  jmp     loc_18000C349
0x18000c672  movsx   edx, word ptr [r8]; nNumerator
0x18000c676  cmp     edx, 9ECh
0x18000c67c  jz      loc_18000C464
0x18000c682  mov     r8d, 9ECh; nDenominator
0x18000c688  mov     ecx, r15d; nNumber
0x18000c68b  call    cs:__imp_MulDiv
0x18000c692  nop     dword ptr [rax+rax+00h]
0x18000c697  mov     r15d, eax
0x18000c69a  jmp     loc_18000C460
0x18000c69f  mov     edx, [rsp+88h+nNumber+0Ch]; int
0x18000c6a3  mov     rcx, rdi; this
0x18000c6a6  call    ?HimetricYtoDY@CDisplay@@QEBAJJ@Z; CDisplay::HimetricYtoDY(long)
0x18000c6ab  jmp     loc_18000C4C6
0x18000c6b0  movsx   edx, word ptr [rdi+26h]; int
0x18000c6b4  mov     r8d, 9ECh; int
0x18000c6ba  mov     ecx, [rsp+88h+var_60+4]; int
0x18000c6be  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18000c6c3  jmp     short loc_18000C66B
0x18000c6c5  mov     r13d, esi
0x18000c6c8  jmp     loc_18000C3A0
0x18000c6cd  movsx   edx, word ptr [rdi+26h]; int
0x18000c6d1  mov     r8d, 9ECh; int
0x18000c6d7  mov     ecx, [rsp+88h+var_60+4]; int
0x18000c6db  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18000c6e0  jmp     short loc_18000C697
0x18000c6e2  mov     ebp, esi
0x18000c6e4  jmp     loc_18000C4B4
```

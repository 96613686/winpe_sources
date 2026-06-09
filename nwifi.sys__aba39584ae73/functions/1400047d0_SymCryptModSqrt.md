# SymCryptModSqrt

- ea: `0x1400047d0`
- end: `0x140004b14`
- name: `SymCryptModSqrt`
- size: `836`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140003598`
- `0x14001d634`
- `0x14003a9b8`

## callees

- `0x1400047d0`
- `0x140004b1c`
- `0x140004b50`
- `0x140005010`
- `0x1400058e0`
- `0x14001d0c0`
- `0x14002c550`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004a9f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004adb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004a9f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004adb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004aef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b03`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004aef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b03`

## pseudocode

```c
__int64 __fastcall SymCryptModSqrt(_DWORD *a1, __int64 a2, _DWORD *a3, char *a4, __int64 a5, __int64 a6)
{
  unsigned int v6; // eax
  char *v7; // r13
  unsigned int v9; // ebx
  _DWORD *v10; // rbp
  unsigned int v11; // eax
  unsigned int v12; // edi
  char *v13; // rsi
  __int64 v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // r14
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int v20; // ecx
  __int64 v21; // r8
  unsigned int v22; // edx
  __int64 i; // r9
  __int64 v24; // rcx
  unsigned __int64 v25; // r8
  unsigned int v26; // r9d
  __int64 v27; // rcx
  unsigned int v28; // ebx
  _DWORD *v30; // rax
  PNPAGED_LOOKASIDE_LIST *v31; // rsi
  __int64 v32; // r14

  v6 = a1[19];
  v7 = a4;
  if ( v6 )
  {
    if ( v6 <= 0x100000 )
      v9 = (a1[19] >> 9) + (((a1[19] & 0x1FFu) + 511) >> 9);
    else
      v9 = 0;
  }
  else
  {
    v9 = 1;
  }
  v10 = 0;
  v11 = SymCryptFdefSizeofIntFromDigits(v9);
  v12 = v11;
  if ( v11 )
  {
    v30 = (_DWORD *)SymCryptCallbackAlloc(v11);
    if ( v30 )
    {
      *v30 = 1732837376;
      v30[1] = v9;
      v30[2] = v12;
      v10 = v30;
    }
  }
  v13 = 0;
  v14 = SymCryptCallbackAlloc((unsigned int)a1[4]);
  if ( v14 )
  {
    v13 = (char *)v14;
    v15 = (a1[1] << 6) - 64;
    *(_QWORD *)(v15 + v14) = 0;
    *(_QWORD *)(v15 + v14 + 8) = 0;
    *(_QWORD *)(v15 + v14 + 16) = 0;
    *(_QWORD *)(v15 + v14 + 24) = 0;
    *(_QWORD *)(v15 + v14 + 32) = 0;
    *(_QWORD *)(v15 + v14 + 40) = 0;
    *(_QWORD *)(v15 + v14 + 48) = 0;
    *(_QWORD *)(v15 + v14 + 56) = 0;
  }
  v16 = 0;
  v17 = SymCryptCallbackAlloc((unsigned int)a1[4]);
  if ( v17 )
  {
    v16 = v17;
    v20 = (a1[1] << 6) - 64;
    *(_QWORD *)(v20 + v17) = 0;
    *(_QWORD *)(v20 + v17 + 8) = 0;
    *(_QWORD *)(v20 + v17 + 16) = 0;
    *(_QWORD *)(v20 + v17 + 24) = 0;
    *(_QWORD *)(v20 + v17 + 32) = 0;
    *(_QWORD *)(v20 + v17 + 40) = 0;
    *(_QWORD *)(v20 + v17 + 48) = 0;
    *(_QWORD *)(v20 + v17 + 56) = 0;
  }
  if ( v10 && v13 && v16 )
  {
    if ( a1 + 24 != v10 )
      memmove(v10 + 8, a1 + 32, (unsigned int)(v10[1] << 6));
    v21 = 1;
    v22 = 16 * v10[1];
    for ( i = 0; (unsigned int)i < v22; v21 = HIDWORD(v25) )
    {
      v24 = (unsigned int)i;
      i = (unsigned int)(i + 1);
      v25 = (unsigned int)v10[v24 + 8] + v21;
      v10[v24 + 8] = v25;
    }
    SymCryptFdefIntDivPow2(v10, 2, v10, i);
    SymCryptModExpWindowed((_DWORD)a1, a2, (_DWORD)v10, a1[19] - 2, (__int64)v13, a5, a6);
    (*(void (__fastcall **)(_DWORD *, char *, __int64, __int64, __int64))((char *)&off_14009E020 + (*a1 & 0x380)))(
      a1,
      v13,
      v16,
      a5,
      a6);
    v26 = 16 * a1[1];
    v19 = 0;
    v18 = 0;
    if ( v26 )
    {
      do
      {
        v27 = (unsigned int)v18;
        v18 = (unsigned int)(v18 + 1);
        v19 = *(_DWORD *)(a2 + 4 * v27) ^ *(_DWORD *)(v16 + 4 * v27) | (unsigned int)v19;
      }
      while ( (unsigned int)v18 < v26 );
      v7 = a4;
    }
    *a3 = ~((unsigned __int64)-(__int64)(unsigned int)v19 >> 32);
    if ( v7 && v13 != v7 )
      memmove(v7, v13, (unsigned int)a1[4]);
    v28 = 0;
  }
  else
  {
    v28 = 32783;
    if ( !v10 )
      goto LABEL_24;
  }
  SymCryptIntFree(v10, v18, v19);
LABEL_24:
  if ( v13 )
  {
    SymCryptWipeAsm(v13, (unsigned int)a1[4]);
    v31 = (PNPAGED_LOOKASIDE_LIST *)&v13[-*((unsigned int *)v13 - 1)];
    if ( v31 )
    {
      if ( *(v31 - 2) )
        ExFreeToNPagedLookasideList(*(v31 - 2), v31 - 2);
      else
        ExFreePoolWithTag(v31 - 2, *((_DWORD *)v31 - 2));
    }
  }
  if ( v16 )
  {
    SymCryptWipeAsm(v16, (unsigned int)a1[4]);
    v32 = v16 - *(unsigned int *)(v16 - 4);
    if ( v32 )
    {
      if ( *(_QWORD *)(v32 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v32 - 16), (PVOID)(v32 - 16));
      else
        ExFreePoolWithTag((PVOID)(v32 - 16), *(_DWORD *)(v32 - 16 + 8));
    }
  }
  return v28;
}

```

## disassembly

```asm
0x1400047d0  mov     [rsp+arg_18], r9
0x1400047d5  mov     [rsp+arg_10], r8
0x1400047da  mov     [rsp+arg_8], rdx
0x1400047df  push    rbx
0x1400047e0  push    rbp
0x1400047e1  push    rsi
0x1400047e2  push    rdi
0x1400047e3  push    r12
0x1400047e5  push    r13
0x1400047e7  push    r14
0x1400047e9  push    r15
0x1400047eb  sub     rsp, 48h
0x1400047ef  mov     eax, [rcx+4Ch]
0x1400047f2  mov     r13, r9
0x1400047f5  mov     r15, rcx
0x1400047f8  test    eax, eax
0x1400047fa  jz      loc_140004A22
0x140004800  cmp     eax, 100000h
0x140004805  jbe     loc_140004A2C
0x14000480b  xor     ebx, ebx
0x14000480d  mov     ecx, ebx
0x14000480f  xor     ebp, ebp
0x140004811  call    SymCryptFdefSizeofIntFromDigits
0x140004816  mov     edi, eax
0x140004818  test    eax, eax
0x14000481a  jnz     loc_140004A50
0x140004820  mov     ecx, [r15+10h]
0x140004824  xor     edi, edi
0x140004826  mov     esi, edi
0x140004828  call    SymCryptCallbackAlloc
0x14000482d  lea     r12d, [rdi+4]
0x140004831  mov     rbx, r15
0x140004834  test    rax, rax
0x140004837  jz      short loc_14000486D
0x140004839  mov     ecx, [r15+4]
0x14000483d  mov     rsi, rax
0x140004840  shl     ecx, 6
0x140004843  sub     ecx, 40h ; '@'
0x140004846  mov     [rcx+rax], rdi
0x14000484a  mov     [rcx+rax+8], rdi
0x14000484f  mov     [rcx+rax+10h], rdi
0x140004854  mov     [rcx+rax+18h], rdi
0x140004859  mov     [rcx+rax+20h], rdi
0x14000485e  mov     [rcx+rax+28h], rdi
0x140004863  mov     [rcx+rax+30h], rdi
0x140004868  mov     [rcx+rax+38h], rdi
0x14000486d  mov     ecx, [r15+10h]
0x140004871  mov     r14, rdi
0x140004874  call    SymCryptCallbackAlloc
0x140004879  test    rax, rax
0x14000487c  jz      short loc_1400048B2
0x14000487e  mov     ecx, [r12+rbx]
0x140004882  mov     r14, rax
0x140004885  shl     ecx, 6
0x140004888  sub     ecx, 40h ; '@'
0x14000488b  mov     [rcx+rax], rdi
0x14000488f  mov     [rcx+rax+8], rdi
0x140004894  mov     [rcx+rax+10h], rdi
0x140004899  mov     [rcx+rax+18h], rdi
0x14000489e  mov     [rcx+rax+20h], rdi
0x1400048a3  mov     [rcx+rax+28h], rdi
0x1400048a8  mov     [rcx+rax+30h], rdi
0x1400048ad  mov     [rcx+rax+38h], rdi
0x1400048b2  test    rbp, rbp
0x1400048b5  jz      loc_140004A44
0x1400048bb  test    rsi, rsi
0x1400048be  jz      loc_140004A44
0x1400048c4  test    r14, r14
0x1400048c7  jz      loc_140004A44
0x1400048cd  lea     rdx, [r15+60h]
0x1400048d1  cmp     rdx, rbp
0x1400048d4  jz      short loc_1400048EB
0x1400048d6  mov     r8d, [rbp+4]
0x1400048da  lea     rcx, [rbp+20h]; void *
0x1400048de  shl     r8d, 6; Size
0x1400048e2  add     rdx, 20h ; ' '; Src
0x1400048e6  call    memmove
0x1400048eb  mov     edx, [rbp+4]
0x1400048ee  mov     r8d, 1
0x1400048f4  shl     edx, 4
0x1400048f7  mov     r9d, edi
0x1400048fa  test    edx, edx
0x1400048fc  jz      short loc_140004919
0x1400048fe  mov     ecx, r9d
0x140004901  inc     r9d
0x140004904  mov     eax, [rbp+rcx*4+20h]
0x140004908  add     r8, rax
0x14000490b  mov     [rbp+rcx*4+20h], r8d
0x140004910  shr     r8, 20h
0x140004914  cmp     r9d, edx
0x140004917  jb      short loc_1400048FE
0x140004919  mov     r8, rbp
0x14000491c  mov     edx, 2
0x140004921  mov     rcx, rbp
0x140004924  call    SymCryptFdefIntDivPow2
0x140004929  mov     r9d, [r15+4Ch]
0x14000492d  mov     r8, rbp
0x140004930  mov     rdi, [rsp+88h+arg_28]
0x140004938  sub     r9d, 2
0x14000493c  mov     rbx, [rsp+88h+arg_20]
0x140004944  mov     rcx, r15
0x140004947  mov     rdx, [rsp+88h+arg_8]
0x14000494f  mov     [rsp+88h+var_58], rdi
0x140004954  mov     [rsp+88h+var_60], rbx
0x140004959  mov     [rsp+88h+var_68], rsi
0x14000495e  call    SymCryptModExpWindowed
0x140004963  mov     eax, [r15]
0x140004966  lea     rcx, off_14009E020
0x14000496d  and     eax, 380h
0x140004972  mov     [rsp+88h+var_68], rdi
0x140004977  mov     r9, rbx
0x14000497a  mov     r8, r14
0x14000497d  mov     rdx, rsi
0x140004980  mov     rax, [rax+rcx]
0x140004984  mov     rcx, r15
0x140004987  call    rax
0x140004989  nop     dword ptr [rax]
0x14000498c  mov     r9d, [r12+r15]
0x140004990  xor     edi, edi
0x140004992  shl     r9d, 4
0x140004996  mov     r8d, edi
0x140004999  mov     edx, edi
0x14000499b  test    r9d, r9d
0x14000499e  jz      short loc_1400049C7
0x1400049a0  mov     r13, [rsp+88h+arg_8]
0x1400049a8  mov     ecx, edx
0x1400049aa  inc     edx
0x1400049ac  mov     eax, [r13+rcx*4+0]
0x1400049b1  mov     ecx, [r14+rcx*4]
0x1400049b5  xor     ecx, eax
0x1400049b7  or      r8d, ecx
0x1400049ba  cmp     edx, r9d
0x1400049bd  jb      short loc_1400049A8
0x1400049bf  mov     r13, [rsp+88h+arg_18]
0x1400049c7  mov     rcx, [rsp+88h+arg_10]
0x1400049cf  mov     eax, r8d
0x1400049d2  neg     rax
0x1400049d5  shr     rax, 20h
0x1400049d9  not     eax
0x1400049db  mov     [rcx], eax
0x1400049dd  test    r13, r13
0x1400049e0  jz      short loc_1400049F6
0x1400049e2  cmp     rsi, r13
0x1400049e5  jz      short loc_1400049F6
0x1400049e7  mov     r8d, [r15+10h]; Size
0x1400049eb  mov     rdx, rsi; Src
0x1400049ee  mov     rcx, r13; void *
0x1400049f1  call    memmove
0x1400049f6  mov     ebx, edi
0x1400049f8  mov     rcx, rbp
0x1400049fb  call    SymCryptIntFree
0x140004a00  test    rsi, rsi
0x140004a03  jnz     short loc_140004A75
0x140004a05  test    r14, r14
0x140004a08  jnz     loc_140004AB0
0x140004a0e  mov     eax, ebx
0x140004a10  add     rsp, 48h
0x140004a14  pop     r15
0x140004a16  pop     r14
0x140004a18  pop     r13
0x140004a1a  pop     r12
0x140004a1c  pop     rdi
0x140004a1d  pop     rsi
0x140004a1e  pop     rbp
0x140004a1f  pop     rbx
0x140004a20  retn
0x140004a22  mov     ebx, 1
0x140004a27  jmp     loc_14000480D
0x140004a2c  mov     ebx, eax
0x140004a2e  mov     ecx, 1FFh
0x140004a33  and     ebx, ecx
0x140004a35  shr     eax, 9
0x140004a38  add     ebx, ecx
0x140004a3a  shr     ebx, 9
0x140004a3d  add     ebx, eax
0x140004a3f  jmp     loc_14000480D
0x140004a44  mov     ebx, 800Fh
0x140004a49  test    rbp, rbp
0x140004a4c  jnz     short loc_1400049F8
0x140004a4e  jmp     short loc_140004A00
0x140004a50  mov     rcx, rdi
0x140004a53  call    SymCryptCallbackAlloc
0x140004a58  test    rax, rax
0x140004a5b  jz      loc_140004820
0x140004a61  mov     dword ptr [rax], 67490000h
0x140004a67  mov     [rax+4], ebx
0x140004a6a  mov     [rax+8], edi
0x140004a6d  mov     rbp, rax
0x140004a70  jmp     loc_140004820
0x140004a75  mov     edx, [r15+10h]
0x140004a79  mov     rcx, rsi
0x140004a7c  call    SymCryptWipeAsm
0x140004a81  mov     eax, [rsi-4]
0x140004a84  sub     rsi, rax
0x140004a87  jz      loc_140004A05
0x140004a8d  lea     rcx, [rsi-10h]; P
0x140004a91  mov     rax, [rcx]
0x140004a94  test    rax, rax
0x140004a97  jz      short loc_140004AEC
0x140004a99  mov     rdx, rcx; Entry
0x140004a9c  mov     rcx, rax; Lookaside
0x140004a9f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140004aa6  nop     dword ptr [rax+rax+00h]
0x140004aab  jmp     loc_140004A05
0x140004ab0  mov     edx, [r15+10h]
0x140004ab4  mov     rcx, r14
0x140004ab7  call    SymCryptWipeAsm
0x140004abc  mov     eax, [r14-4]
0x140004ac0  sub     r14, rax
0x140004ac3  jz      loc_140004A0E
0x140004ac9  lea     rcx, [r14-10h]; P
0x140004acd  mov     rax, [rcx]
0x140004ad0  test    rax, rax
0x140004ad3  jz      short loc_140004B00
0x140004ad5  mov     rdx, rcx; Entry
0x140004ad8  mov     rcx, rax; Lookaside
0x140004adb  call    cs:__imp_ExFreeToNPagedLookasideList
0x140004ae2  nop     dword ptr [rax+rax+00h]
0x140004ae7  jmp     loc_140004A0E
0x140004aec  mov     edx, [rcx+8]; Tag
0x140004aef  call    cs:__imp_ExFreePoolWithTag
0x140004af6  nop     dword ptr [rax+rax+00h]
0x140004afb  jmp     loc_140004A05
0x140004b00  mov     edx, [rcx+8]; Tag
0x140004b03  call    cs:__imp_ExFreePoolWithTag
0x140004b0a  nop     dword ptr [rax+rax+00h]
0x140004b0f  jmp     loc_140004A0E
```

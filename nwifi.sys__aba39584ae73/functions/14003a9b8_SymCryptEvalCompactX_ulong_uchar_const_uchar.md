# SymCryptEvalCompactX(ulong,uchar const *,uchar *)

- ea: `0x14003a9b8`
- end: `0x14003af49`
- name: `?SymCryptEvalCompactX@@YA?AW4SYMCRYPT_ERROR@@KPEBEPEAE@Z`
- size: `1425`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140039864`

## callees

- `0x140003454`
- `0x1400047d0`
- `0x140004b1c`
- `0x140004b50`
- `0x140004ba8`
- `0x140004f50`
- `0x140007c6c`
- `0x140007cf0`
- `0x140007d24`
- `0x14000b090`
- `0x14000d21c`
- `0x14001d0c0`
- `0x14001d1a4`
- `0x14002071c`
- `0x140020dc0`
- `0x14002c550`
- `0x14003a9b8`
- `0x14003b164`
- `0x14009bbf0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ae2c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ae7b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003aec9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003af10`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ae2c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ae7b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003aec9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003af10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ae3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ae8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003aeda`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003af21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ae3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ae8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003aeda`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003af21`

## pseudocode

```c
__int64 __fastcall SymCryptEvalCompactX(unsigned int a1, int a2, __int64 a3)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  __int64 *v6; // rcx
  __int64 v7; // rax
  _QWORD *v8; // rdi
  unsigned int v9; // ecx
  unsigned int v10; // r12d
  unsigned int v11; // edx
  unsigned int v12; // eax
  _DWORD *v13; // r13
  unsigned int v14; // eax
  unsigned int v15; // esi
  _DWORD *v16; // rax
  __int64 v17; // rbx
  char *v18; // r15
  __int64 v19; // rax
  unsigned int v20; // ecx
  __int64 v21; // rbx
  __int64 v22; // r14
  __int64 v23; // rax
  unsigned int v24; // ecx
  __int64 v25; // rbx
  __int64 v26; // rbp
  __int64 v27; // rax
  unsigned int v28; // ecx
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  char *v33; // rsi
  unsigned int v34; // eax
  __int64 v35; // r9
  PDEVICE_OBJECT v36; // rcx
  __int64 v37; // rdx
  struct NETMON_VELAN *v38; // rbx
  unsigned int v39; // eax
  PNPAGED_LOOKASIDE_LIST *v40; // r15
  __int64 v41; // r14
  __int64 v42; // rbp
  PNPAGED_LOOKASIDE_LIST *v43; // rsi
  int v47; // [rsp+A8h] [rbp+20h] BYREF

  if ( a1 == 66 )
  {
    v3 = 521;
LABEL_3:
    v4 = (v3 >> 9) + (((v3 & 0x1FF) + 511) >> 9);
    goto LABEL_4;
  }
  v3 = 8 * a1;
  if ( 8 * a1 )
  {
    if ( v3 <= 0x100000 )
      goto LABEL_3;
    v4 = 0;
  }
  else
  {
    v4 = 1;
  }
LABEL_4:
  v47 = 0;
  if ( a1 == 32 )
  {
    v6 = qword_1400A1A00;
  }
  else
  {
    if ( a1 != 48 )
      return 32779;
    v6 = qword_1400A3700;
  }
  v7 = SymCryptEcurveAllocate(v6);
  v8 = (_QWORD *)v7;
  if ( v7 )
  {
    v9 = *(_DWORD *)(v7 + 56);
    v10 = (v4 << 8) + 64;
    v11 = 4480 * v4 + 64;
    v12 = v11;
    if ( v11 <= v9 )
      v12 = v9;
    if ( v10 <= v12 )
    {
      v10 = v9;
      if ( v11 > v9 )
        v10 = 4480 * v4 + 64;
    }
    v13 = 0;
    v14 = SymCryptFdefSizeofIntFromDigits(v4);
    v15 = v14;
    if ( v14 )
    {
      v16 = (_DWORD *)SymCryptCallbackAlloc(v14);
      if ( v16 )
      {
        *v16 = 1732837376;
        v16[1] = v4;
        v16[2] = v15;
        v13 = v16;
      }
    }
    v17 = v8[77];
    v18 = 0;
    v19 = SymCryptCallbackAlloc(*(unsigned int *)(v17 + 16));
    if ( v19 )
    {
      v18 = (char *)v19;
      v20 = (*(_DWORD *)(v17 + 4) << 6) - 64;
      *(_QWORD *)(v20 + v19) = 0;
      *(_QWORD *)(v20 + v19 + 8) = 0;
      *(_QWORD *)(v20 + v19 + 16) = 0;
      *(_QWORD *)(v20 + v19 + 24) = 0;
      *(_QWORD *)(v20 + v19 + 32) = 0;
      *(_QWORD *)(v20 + v19 + 40) = 0;
      *(_QWORD *)(v20 + v19 + 48) = 0;
      *(_QWORD *)(v20 + v19 + 56) = 0;
    }
    v21 = v8[77];
    v22 = 0;
    v23 = SymCryptCallbackAlloc(*(unsigned int *)(v21 + 16));
    if ( v23 )
    {
      v22 = v23;
      v24 = (*(_DWORD *)(v21 + 4) << 6) - 64;
      *(_QWORD *)(v24 + v23) = 0;
      *(_QWORD *)(v24 + v23 + 8) = 0;
      *(_QWORD *)(v24 + v23 + 16) = 0;
      *(_QWORD *)(v24 + v23 + 24) = 0;
      *(_QWORD *)(v24 + v23 + 32) = 0;
      *(_QWORD *)(v24 + v23 + 40) = 0;
      *(_QWORD *)(v24 + v23 + 48) = 0;
      *(_QWORD *)(v24 + v23 + 56) = 0;
    }
    v25 = v8[77];
    v26 = 0;
    v27 = SymCryptCallbackAlloc(*(unsigned int *)(v25 + 16));
    if ( v27 )
    {
      v26 = v27;
      v28 = (*(_DWORD *)(v25 + 4) << 6) - 64;
      *(_QWORD *)(v28 + v27) = 0;
      *(_QWORD *)(v28 + v27 + 8) = 0;
      *(_QWORD *)(v28 + v27 + 16) = 0;
      *(_QWORD *)(v28 + v27 + 24) = 0;
      *(_QWORD *)(v28 + v27 + 32) = 0;
      *(_QWORD *)(v28 + v27 + 40) = 0;
      *(_QWORD *)(v28 + v27 + 48) = 0;
      *(_QWORD *)(v28 + v27 + 56) = 0;
    }
    v29 = v10;
    v30 = SymCryptCallbackAlloc(v10);
    v33 = (char *)v30;
    if ( !v13 || !v18 || !v22 || !v26 || !v30 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_qqqqq(WPP_GLOBAL_Control->AttachedDevice, v31, v32, v13, v18, v22, v26, v30);
      if ( !v13 )
        goto LABEL_48;
      goto LABEL_47;
    }
    v34 = SymCryptFdefRawSetValue(a2, a1, v32, (int)v13 + 32, v13[1]);
    v35 = v34;
    if ( v34 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v37 = 12;
LABEL_38:
        WPP_SF_d(v36->AttachedDevice, v37, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids, v35);
      }
    }
    else
    {
      v38 = (struct NETMON_VELAN *)v8[77];
      SymCryptFdefRawDivMod(v13 + 8, v18, (__int64)v33);
      (*(void (__fastcall **)(struct NETMON_VELAN *, int, void *, unsigned int))((char *)&off_14009E030
                                                                               + (*(_DWORD *)v38 & 0x380)))(
        v38,
        (int)v18,
        v33,
        v10);
      v29 = v10;
      SymCryptModSquare(v8[77], (_DWORD)v18, v26, (_DWORD)v33, v10);
      SymCryptModAdd(v8[77], v26, v8[79], v26, (__int64)v33, v10);
      SymCryptModMul(v8[77], v26, (_DWORD)v18, v26, (__int64)v33, v10);
      SymCryptModAdd(v8[77], v26, v8[80], v26, (__int64)v33, v10);
      v39 = SymCryptModSqrt(v8[77], v26, &v47, v22, v33, v10);
      v35 = v39;
      if ( !v39 )
      {
        SymCryptModElementToInt(v8[77], v22, (_DWORD)v13, (_DWORD)v33, v10);
        SymCryptFdefRawGetValue(v13 + 8, (unsigned int)v13[1], a3, a1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids, v10);
        goto LABEL_47;
      }
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v37 = 13;
        goto LABEL_38;
      }
    }
LABEL_47:
    SymCryptIntFree(v13, v31, v32);
LABEL_48:
    if ( v18 )
    {
      SymCryptWipeAsm(v18, *(unsigned int *)(v8[77] + 16LL));
      v40 = (PNPAGED_LOOKASIDE_LIST *)&v18[-*((unsigned int *)v18 - 1)];
      if ( v40 )
      {
        if ( *(v40 - 2) )
          ExFreeToNPagedLookasideList(*(v40 - 2), v40 - 2);
        else
          ExFreePoolWithTag(v40 - 2, *((_DWORD *)v40 - 2));
      }
    }
    if ( v22 )
    {
      SymCryptWipeAsm(v22, *(unsigned int *)(v8[77] + 16LL));
      v41 = v22 - *(unsigned int *)(v22 - 4);
      if ( v41 )
      {
        if ( *(_QWORD *)(v41 - 16) )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v41 - 16), (PVOID)(v41 - 16));
        else
          ExFreePoolWithTag((PVOID)(v41 - 16), *(_DWORD *)(v41 - 16 + 8));
      }
    }
    if ( v26 )
    {
      SymCryptWipeAsm(v26, *(unsigned int *)(v8[77] + 16LL));
      v42 = v26 - *(unsigned int *)(v26 - 4);
      if ( v42 )
      {
        if ( *(_QWORD *)(v42 - 16) )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v42 - 16), (PVOID)(v42 - 16));
        else
          ExFreePoolWithTag((PVOID)(v42 - 16), *(_DWORD *)(v42 - 16 + 8));
      }
    }
    if ( v33 )
    {
      SymCryptWipeAsm(v33, v29);
      v43 = (PNPAGED_LOOKASIDE_LIST *)&v33[-*((unsigned int *)v33 - 1)];
      if ( v43 )
      {
        if ( *(v43 - 2) )
          ExFreeToNPagedLookasideList(*(v43 - 2), v43 - 2);
        else
          ExFreePoolWithTag(v43 - 2, *((_DWORD *)v43 - 2));
      }
    }
    SymCryptEcurveFree(v8);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14003a9b8  mov     [rsp+arg_10], r8
0x14003a9bd  mov     [rsp+arg_8], rdx
0x14003a9c2  mov     [rsp+arg_0], ecx
0x14003a9c6  push    rbx
0x14003a9c7  push    rbp
0x14003a9c8  push    rsi
0x14003a9c9  push    rdi
0x14003a9ca  push    r12
0x14003a9cc  push    r13
0x14003a9ce  push    r14
0x14003a9d0  push    r15
0x14003a9d2  sub     rsp, 48h
0x14003a9d6  cmp     ecx, 42h ; 'B'
0x14003a9d9  jnz     short loc_14003AA12
0x14003a9db  mov     eax, 209h
0x14003a9e0  mov     ebx, eax
0x14003a9e2  mov     edx, 1FFh
0x14003a9e7  and     ebx, edx
0x14003a9e9  shr     eax, 9
0x14003a9ec  add     ebx, edx
0x14003a9ee  shr     ebx, 9
0x14003a9f1  add     ebx, eax
0x14003a9f3  mov     [rsp+88h+arg_18], 0
0x14003a9fe  cmp     ecx, 20h ; ' '
0x14003aa01  jz      short loc_14003AA36
0x14003aa03  cmp     ecx, 30h ; '0'
0x14003aa06  jz      short loc_14003AA2D
0x14003aa08  mov     eax, 800Bh
0x14003aa0d  jmp     loc_14003AF37
0x14003aa12  lea     eax, ds:0[rcx*8]
0x14003aa19  test    eax, eax
0x14003aa1b  jnz     short loc_14003AA22
0x14003aa1d  lea     ebx, [rax+1]
0x14003aa20  jmp     short loc_14003A9F3
0x14003aa22  cmp     eax, 100000h
0x14003aa27  jbe     short loc_14003A9E0
0x14003aa29  xor     ebx, ebx
0x14003aa2b  jmp     short loc_14003A9F3
0x14003aa2d  lea     rcx, qword_1400A3700
0x14003aa34  jmp     short loc_14003AA3D
0x14003aa36  lea     rcx, qword_1400A1A00
0x14003aa3d  call    SymCryptEcurveAllocate
0x14003aa42  mov     rdi, rax
0x14003aa45  test    rax, rax
0x14003aa48  jnz     short loc_14003AA79
0x14003aa4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aa51  lea     rax, WPP_GLOBAL_Control
0x14003aa58  cmp     rcx, rax
0x14003aa5b  jz      loc_14003AF35
0x14003aa61  mov     rcx, [rcx+18h]
0x14003aa65  lea     edx, [rdi+0Ah]
0x14003aa68  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x14003aa6f  call    WPP_SF_
0x14003aa74  jmp     loc_14003AF35
0x14003aa79  mov     ecx, [rdi+38h]
0x14003aa7c  mov     r12d, ebx
0x14003aa7f  imul    edx, ebx, 1180h
0x14003aa85  shl     r12d, 8
0x14003aa89  add     r12d, 40h ; '@'
0x14003aa8d  add     edx, 40h ; '@'
0x14003aa90  cmp     edx, ecx
0x14003aa92  mov     eax, edx
0x14003aa94  cmovbe  eax, ecx
0x14003aa97  cmp     r12d, eax
0x14003aa9a  ja      short loc_14003AAA5
0x14003aa9c  cmp     edx, ecx
0x14003aa9e  mov     r12d, ecx
0x14003aaa1  cmova   r12d, edx
0x14003aaa5  mov     ecx, ebx
0x14003aaa7  xor     r13d, r13d
0x14003aaaa  call    SymCryptFdefSizeofIntFromDigits
0x14003aaaf  mov     esi, eax
0x14003aab1  test    eax, eax
0x14003aab3  jz      short loc_14003AAD0
0x14003aab5  mov     ecx, esi
0x14003aab7  call    SymCryptCallbackAlloc
0x14003aabc  test    rax, rax
0x14003aabf  jz      short loc_14003AAD0
0x14003aac1  mov     dword ptr [rax], 67490000h
0x14003aac7  mov     [rax+4], ebx
0x14003aaca  mov     [rax+8], esi
0x14003aacd  mov     r13, rax
0x14003aad0  mov     rbx, [rdi+268h]
0x14003aad7  xor     esi, esi
0x14003aad9  mov     r15d, esi
0x14003aadc  mov     ecx, [rbx+10h]
0x14003aadf  call    SymCryptCallbackAlloc
0x14003aae4  test    rax, rax
0x14003aae7  jz      short loc_14003AB1C
0x14003aae9  mov     ecx, [rbx+4]
0x14003aaec  mov     r15, rax
0x14003aaef  shl     ecx, 6
0x14003aaf2  sub     ecx, 40h ; '@'
0x14003aaf5  mov     [rcx+rax], rsi
0x14003aaf9  mov     [rcx+rax+8], rsi
0x14003aafe  mov     [rcx+rax+10h], rsi
0x14003ab03  mov     [rcx+rax+18h], rsi
0x14003ab08  mov     [rcx+rax+20h], rsi
0x14003ab0d  mov     [rcx+rax+28h], rsi
0x14003ab12  mov     [rcx+rax+30h], rsi
0x14003ab17  mov     [rcx+rax+38h], rsi
0x14003ab1c  mov     rbx, [rdi+268h]
0x14003ab23  mov     r14, rsi
0x14003ab26  mov     ecx, [rbx+10h]
0x14003ab29  call    SymCryptCallbackAlloc
0x14003ab2e  test    rax, rax
0x14003ab31  jz      short loc_14003AB66
0x14003ab33  mov     ecx, [rbx+4]
0x14003ab36  mov     r14, rax
0x14003ab39  shl     ecx, 6
0x14003ab3c  sub     ecx, 40h ; '@'
0x14003ab3f  mov     [rcx+rax], rsi
0x14003ab43  mov     [rcx+rax+8], rsi
0x14003ab48  mov     [rcx+rax+10h], rsi
0x14003ab4d  mov     [rcx+rax+18h], rsi
0x14003ab52  mov     [rcx+rax+20h], rsi
0x14003ab57  mov     [rcx+rax+28h], rsi
0x14003ab5c  mov     [rcx+rax+30h], rsi
0x14003ab61  mov     [rcx+rax+38h], rsi
0x14003ab66  mov     rbx, [rdi+268h]
0x14003ab6d  mov     rbp, rsi
0x14003ab70  mov     ecx, [rbx+10h]
0x14003ab73  call    SymCryptCallbackAlloc
0x14003ab78  test    rax, rax
0x14003ab7b  jz      short loc_14003ABB0
0x14003ab7d  mov     ecx, [rbx+4]
0x14003ab80  mov     rbp, rax
0x14003ab83  shl     ecx, 6
0x14003ab86  sub     ecx, 40h ; '@'
0x14003ab89  mov     [rcx+rax], rsi
0x14003ab8d  mov     [rcx+rax+8], rsi
0x14003ab92  mov     [rcx+rax+10h], rsi
0x14003ab97  mov     [rcx+rax+18h], rsi
0x14003ab9c  mov     [rcx+rax+20h], rsi
0x14003aba1  mov     [rcx+rax+28h], rsi
0x14003aba6  mov     [rcx+rax+30h], rsi
0x14003abab  mov     [rcx+rax+38h], rsi
0x14003abb0  mov     ecx, r12d
0x14003abb3  mov     ebx, r12d
0x14003abb6  call    SymCryptCallbackAlloc
0x14003abbb  mov     rsi, rax
0x14003abbe  test    r13, r13
0x14003abc1  jz      loc_14003ADBA
0x14003abc7  test    r15, r15
0x14003abca  jz      loc_14003ADBA
0x14003abd0  test    r14, r14
0x14003abd3  jz      loc_14003ADBA
0x14003abd9  test    rbp, rbp
0x14003abdc  jz      loc_14003ADBA
0x14003abe2  test    rax, rax
0x14003abe5  jz      loc_14003ADBA
0x14003abeb  mov     eax, [r13+4]
0x14003abef  lea     r9, [r13+20h]
0x14003abf3  mov     edx, [rsp+88h+arg_0]
0x14003abfa  mov     rcx, [rsp+88h+arg_8]
0x14003ac02  mov     dword ptr [rsp+88h+var_68], eax
0x14003ac06  call    SymCryptFdefRawSetValue
0x14003ac0b  mov     r9d, eax
0x14003ac0e  test    eax, eax
0x14003ac10  jz      short loc_14003AC43
0x14003ac12  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac19  lea     rax, WPP_GLOBAL_Control
0x14003ac20  cmp     rcx, rax
0x14003ac23  jz      loc_14003ADF2
0x14003ac29  mov     edx, 0Ch
0x14003ac2e  mov     rcx, [rcx+18h]
0x14003ac32  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x14003ac39  call    WPP_SF_d
0x14003ac3e  jmp     loc_14003ADF2
0x14003ac43  mov     rbx, [rdi+268h]
0x14003ac4a  lea     rcx, [r13+20h]; Src
0x14003ac4e  mov     edx, [r13+4]
0x14003ac52  mov     [rsp+88h+var_60], rsi; __int64
0x14003ac57  mov     [rsp+88h+var_68], r15; void *
0x14003ac5c  lea     r8, [rbx+40h]
0x14003ac60  call    SymCryptFdefRawDivMod
0x14003ac65  mov     eax, [rbx]
0x14003ac67  lea     rcx, off_14009E030
0x14003ac6e  and     eax, 380h
0x14003ac73  mov     r9d, r12d
0x14003ac76  mov     r8, rsi
0x14003ac79  mov     rdx, r15
0x14003ac7c  mov     rax, [rax+rcx]
0x14003ac80  mov     rcx, rbx
0x14003ac83  call    _guard_dispatch_icall
0x14003ac88  mov     rcx, [rdi+268h]
0x14003ac8f  mov     r9, rsi
0x14003ac92  mov     ebx, r12d
0x14003ac95  mov     r8, rbp
0x14003ac98  mov     rdx, r15
0x14003ac9b  mov     [rsp+88h+var_68], rbx
0x14003aca0  call    SymCryptModSquare
0x14003aca5  mov     r8, [rdi+278h]
0x14003acac  mov     r9, rbp
0x14003acaf  mov     rcx, [rdi+268h]
0x14003acb6  mov     rdx, rbp
0x14003acb9  mov     [rsp+88h+var_60], rbx
0x14003acbe  mov     [rsp+88h+var_68], rsi
0x14003acc3  call    SymCryptModAdd
0x14003acc8  mov     rcx, [rdi+268h]
0x14003accf  mov     r9, rbp
0x14003acd2  mov     r8, r15
0x14003acd5  mov     [rsp+88h+var_60], rbx
0x14003acda  mov     rdx, rbp
0x14003acdd  mov     [rsp+88h+var_68], rsi
0x14003ace2  call    SymCryptModMul
0x14003ace7  mov     r8, [rdi+280h]
0x14003acee  mov     r9, rbp
0x14003acf1  mov     rcx, [rdi+268h]
0x14003acf8  mov     rdx, rbp
0x14003acfb  mov     [rsp+88h+var_60], rbx
0x14003ad00  mov     [rsp+88h+var_68], rsi
0x14003ad05  call    SymCryptModAdd
0x14003ad0a  mov     rcx, [rdi+268h]
0x14003ad11  lea     r8, [rsp+88h+arg_18]
0x14003ad19  mov     r9, r14
0x14003ad1c  mov     [rsp+88h+var_60], rbx
0x14003ad21  mov     rdx, rbp
0x14003ad24  mov     [rsp+88h+var_68], rsi
0x14003ad29  call    SymCryptModSqrt
0x14003ad2e  mov     r9d, eax
0x14003ad31  test    eax, eax
0x14003ad33  jz      short loc_14003AD56
0x14003ad35  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ad3c  lea     rax, WPP_GLOBAL_Control
0x14003ad43  cmp     rcx, rax
0x14003ad46  jz      loc_14003ADF2
0x14003ad4c  mov     edx, 0Dh
0x14003ad51  jmp     loc_14003AC2E
0x14003ad56  mov     rcx, [rdi+268h]
0x14003ad5d  mov     r9, rsi
0x14003ad60  mov     r8, r13
0x14003ad63  mov     [rsp+88h+var_68], rbx
0x14003ad68  mov     rdx, r14
0x14003ad6b  call    SymCryptModElementToInt
0x14003ad70  mov     r9d, [rsp+88h+arg_0]
0x14003ad78  lea     rcx, [r13+20h]
0x14003ad7c  mov     r8, [rsp+88h+arg_10]
0x14003ad84  mov     edx, [r13+4]
0x14003ad88  call    SymCryptFdefRawGetValue
0x14003ad8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ad94  lea     rax, WPP_GLOBAL_Control
0x14003ad9b  cmp     rcx, rax
0x14003ad9e  jz      short loc_14003ADF2
0x14003ada0  mov     rcx, [rcx+18h]
0x14003ada4  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x14003adab  mov     edx, 0Eh
0x14003adb0  mov     r9d, r12d
0x14003adb3  call    WPP_SF_d
0x14003adb8  jmp     short loc_14003ADF2
0x14003adba  mov     rcx, cs:WPP_GLOBAL_Control
0x14003adc1  lea     rax, WPP_GLOBAL_Control
0x14003adc8  cmp     rcx, rax
0x14003adcb  jz      short loc_14003ADED
0x14003adcd  mov     rcx, [rcx+18h]
0x14003add1  mov     r9, r13
0x14003add4  mov     [rsp+88h+var_50], rsi
0x14003add9  mov     [rsp+88h+var_58], rbp
0x14003adde  mov     [rsp+88h+var_60], r14
0x14003ade3  mov     [rsp+88h+var_68], r15
0x14003ade8  call    WPP_SF_qqqqq
0x14003aded  test    r13, r13
0x14003adf0  jz      short loc_14003ADFA
0x14003adf2  mov     rcx, r13
0x14003adf5  call    SymCryptIntFree
0x14003adfa  test    r15, r15
0x14003adfd  jz      short loc_14003AE49
0x14003adff  mov     rax, [rdi+268h]
0x14003ae06  mov     rcx, r15
0x14003ae09  mov     edx, [rax+10h]
0x14003ae0c  call    SymCryptWipeAsm
0x14003ae11  mov     eax, [r15-4]
0x14003ae15  sub     r15, rax
0x14003ae18  jz      short loc_14003AE49
0x14003ae1a  lea     rcx, [r15-10h]; P
0x14003ae1e  mov     rax, [rcx]
0x14003ae21  test    rax, rax
0x14003ae24  jz      short loc_14003AE3A
0x14003ae26  mov     rdx, rcx; Entry
0x14003ae29  mov     rcx, rax; Lookaside
0x14003ae2c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003ae33  nop     dword ptr [rax+rax+00h]
0x14003ae38  jmp     short loc_14003AE49
0x14003ae3a  mov     edx, [rcx+8]; Tag
0x14003ae3d  call    cs:__imp_ExFreePoolWithTag
0x14003ae44  nop     dword ptr [rax+rax+00h]
0x14003ae49  test    r14, r14
0x14003ae4c  jz      short loc_14003AE98
0x14003ae4e  mov     rax, [rdi+268h]
0x14003ae55  mov     rcx, r14
0x14003ae58  mov     edx, [rax+10h]
0x14003ae5b  call    SymCryptWipeAsm
0x14003ae60  mov     eax, [r14-4]
0x14003ae64  sub     r14, rax
0x14003ae67  jz      short loc_14003AE98
0x14003ae69  lea     rcx, [r14-10h]; P
0x14003ae6d  mov     rax, [rcx]
0x14003ae70  test    rax, rax
0x14003ae73  jz      short loc_14003AE89
0x14003ae75  mov     rdx, rcx; Entry
  ... truncated ...
```

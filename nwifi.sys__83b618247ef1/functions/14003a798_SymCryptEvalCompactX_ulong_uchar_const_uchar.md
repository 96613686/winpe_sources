# SymCryptEvalCompactX(ulong,uchar const *,uchar *)

- ea: `0x14003a798`
- end: `0x14003ad29`
- name: `?SymCryptEvalCompactX@@YA?AW4SYMCRYPT_ERROR@@KPEBEPEAE@Z`
- size: `1425`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140039644`

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
- `0x14000b0a0`
- `0x14000d22c`
- `0x14001d0c0`
- `0x14001d1a4`
- `0x14002071c`
- `0x140020dc0`
- `0x14002c2c0`
- `0x14003a798`
- `0x14003af44`
- `0x14009a410`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ac0c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ac5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003aca9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003acf0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ac0c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ac5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003aca9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003acf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003acba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ad01`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003acba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ad01`

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
    v6 = qword_14009F900;
  }
  else
  {
    if ( a1 != 48 )
      return 32779;
    v6 = qword_1400A15C0;
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
      (*(void (__fastcall **)(struct NETMON_VELAN *, int, void *, unsigned int))((char *)&off_14009C030
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
0x14003a798  mov     [rsp+arg_10], r8
0x14003a79d  mov     [rsp+arg_8], rdx
0x14003a7a2  mov     [rsp+arg_0], ecx
0x14003a7a6  push    rbx
0x14003a7a7  push    rbp
0x14003a7a8  push    rsi
0x14003a7a9  push    rdi
0x14003a7aa  push    r12
0x14003a7ac  push    r13
0x14003a7ae  push    r14
0x14003a7b0  push    r15
0x14003a7b2  sub     rsp, 48h
0x14003a7b6  cmp     ecx, 42h ; 'B'
0x14003a7b9  jnz     short loc_14003A7F2
0x14003a7bb  mov     eax, 209h
0x14003a7c0  mov     ebx, eax
0x14003a7c2  mov     edx, 1FFh
0x14003a7c7  and     ebx, edx
0x14003a7c9  shr     eax, 9
0x14003a7cc  add     ebx, edx
0x14003a7ce  shr     ebx, 9
0x14003a7d1  add     ebx, eax
0x14003a7d3  mov     [rsp+88h+arg_18], 0
0x14003a7de  cmp     ecx, 20h ; ' '
0x14003a7e1  jz      short loc_14003A816
0x14003a7e3  cmp     ecx, 30h ; '0'
0x14003a7e6  jz      short loc_14003A80D
0x14003a7e8  mov     eax, 800Bh
0x14003a7ed  jmp     loc_14003AD17
0x14003a7f2  lea     eax, ds:0[rcx*8]
0x14003a7f9  test    eax, eax
0x14003a7fb  jnz     short loc_14003A802
0x14003a7fd  lea     ebx, [rax+1]
0x14003a800  jmp     short loc_14003A7D3
0x14003a802  cmp     eax, 100000h
0x14003a807  jbe     short loc_14003A7C0
0x14003a809  xor     ebx, ebx
0x14003a80b  jmp     short loc_14003A7D3
0x14003a80d  lea     rcx, qword_1400A15C0
0x14003a814  jmp     short loc_14003A81D
0x14003a816  lea     rcx, qword_14009F900
0x14003a81d  call    SymCryptEcurveAllocate
0x14003a822  mov     rdi, rax
0x14003a825  test    rax, rax
0x14003a828  jnz     short loc_14003A859
0x14003a82a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a831  lea     rax, WPP_GLOBAL_Control
0x14003a838  cmp     rcx, rax
0x14003a83b  jz      loc_14003AD15
0x14003a841  mov     rcx, [rcx+18h]
0x14003a845  lea     edx, [rdi+0Ah]
0x14003a848  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x14003a84f  call    WPP_SF_
0x14003a854  jmp     loc_14003AD15
0x14003a859  mov     ecx, [rdi+38h]
0x14003a85c  mov     r12d, ebx
0x14003a85f  imul    edx, ebx, 1180h
0x14003a865  shl     r12d, 8
0x14003a869  add     r12d, 40h ; '@'
0x14003a86d  add     edx, 40h ; '@'
0x14003a870  cmp     edx, ecx
0x14003a872  mov     eax, edx
0x14003a874  cmovbe  eax, ecx
0x14003a877  cmp     r12d, eax
0x14003a87a  ja      short loc_14003A885
0x14003a87c  cmp     edx, ecx
0x14003a87e  mov     r12d, ecx
0x14003a881  cmova   r12d, edx
0x14003a885  mov     ecx, ebx
0x14003a887  xor     r13d, r13d
0x14003a88a  call    SymCryptFdefSizeofIntFromDigits
0x14003a88f  mov     esi, eax
0x14003a891  test    eax, eax
0x14003a893  jz      short loc_14003A8B0
0x14003a895  mov     ecx, esi
0x14003a897  call    SymCryptCallbackAlloc
0x14003a89c  test    rax, rax
0x14003a89f  jz      short loc_14003A8B0
0x14003a8a1  mov     dword ptr [rax], 67490000h
0x14003a8a7  mov     [rax+4], ebx
0x14003a8aa  mov     [rax+8], esi
0x14003a8ad  mov     r13, rax
0x14003a8b0  mov     rbx, [rdi+268h]
0x14003a8b7  xor     esi, esi
0x14003a8b9  mov     r15d, esi
0x14003a8bc  mov     ecx, [rbx+10h]
0x14003a8bf  call    SymCryptCallbackAlloc
0x14003a8c4  test    rax, rax
0x14003a8c7  jz      short loc_14003A8FC
0x14003a8c9  mov     ecx, [rbx+4]
0x14003a8cc  mov     r15, rax
0x14003a8cf  shl     ecx, 6
0x14003a8d2  sub     ecx, 40h ; '@'
0x14003a8d5  mov     [rcx+rax], rsi
0x14003a8d9  mov     [rcx+rax+8], rsi
0x14003a8de  mov     [rcx+rax+10h], rsi
0x14003a8e3  mov     [rcx+rax+18h], rsi
0x14003a8e8  mov     [rcx+rax+20h], rsi
0x14003a8ed  mov     [rcx+rax+28h], rsi
0x14003a8f2  mov     [rcx+rax+30h], rsi
0x14003a8f7  mov     [rcx+rax+38h], rsi
0x14003a8fc  mov     rbx, [rdi+268h]
0x14003a903  mov     r14, rsi
0x14003a906  mov     ecx, [rbx+10h]
0x14003a909  call    SymCryptCallbackAlloc
0x14003a90e  test    rax, rax
0x14003a911  jz      short loc_14003A946
0x14003a913  mov     ecx, [rbx+4]
0x14003a916  mov     r14, rax
0x14003a919  shl     ecx, 6
0x14003a91c  sub     ecx, 40h ; '@'
0x14003a91f  mov     [rcx+rax], rsi
0x14003a923  mov     [rcx+rax+8], rsi
0x14003a928  mov     [rcx+rax+10h], rsi
0x14003a92d  mov     [rcx+rax+18h], rsi
0x14003a932  mov     [rcx+rax+20h], rsi
0x14003a937  mov     [rcx+rax+28h], rsi
0x14003a93c  mov     [rcx+rax+30h], rsi
0x14003a941  mov     [rcx+rax+38h], rsi
0x14003a946  mov     rbx, [rdi+268h]
0x14003a94d  mov     rbp, rsi
0x14003a950  mov     ecx, [rbx+10h]
0x14003a953  call    SymCryptCallbackAlloc
0x14003a958  test    rax, rax
0x14003a95b  jz      short loc_14003A990
0x14003a95d  mov     ecx, [rbx+4]
0x14003a960  mov     rbp, rax
0x14003a963  shl     ecx, 6
0x14003a966  sub     ecx, 40h ; '@'
0x14003a969  mov     [rcx+rax], rsi
0x14003a96d  mov     [rcx+rax+8], rsi
0x14003a972  mov     [rcx+rax+10h], rsi
0x14003a977  mov     [rcx+rax+18h], rsi
0x14003a97c  mov     [rcx+rax+20h], rsi
0x14003a981  mov     [rcx+rax+28h], rsi
0x14003a986  mov     [rcx+rax+30h], rsi
0x14003a98b  mov     [rcx+rax+38h], rsi
0x14003a990  mov     ecx, r12d
0x14003a993  mov     ebx, r12d
0x14003a996  call    SymCryptCallbackAlloc
0x14003a99b  mov     rsi, rax
0x14003a99e  test    r13, r13
0x14003a9a1  jz      loc_14003AB9A
0x14003a9a7  test    r15, r15
0x14003a9aa  jz      loc_14003AB9A
0x14003a9b0  test    r14, r14
0x14003a9b3  jz      loc_14003AB9A
0x14003a9b9  test    rbp, rbp
0x14003a9bc  jz      loc_14003AB9A
0x14003a9c2  test    rax, rax
0x14003a9c5  jz      loc_14003AB9A
0x14003a9cb  mov     eax, [r13+4]
0x14003a9cf  lea     r9, [r13+20h]
0x14003a9d3  mov     edx, [rsp+88h+arg_0]
0x14003a9da  mov     rcx, [rsp+88h+arg_8]
0x14003a9e2  mov     dword ptr [rsp+88h+var_68], eax
0x14003a9e6  call    SymCryptFdefRawSetValue
0x14003a9eb  mov     r9d, eax
0x14003a9ee  test    eax, eax
0x14003a9f0  jz      short loc_14003AA23
0x14003a9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a9f9  lea     rax, WPP_GLOBAL_Control
0x14003aa00  cmp     rcx, rax
0x14003aa03  jz      loc_14003ABD2
0x14003aa09  mov     edx, 0Ch
0x14003aa0e  mov     rcx, [rcx+18h]
0x14003aa12  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x14003aa19  call    WPP_SF_d
0x14003aa1e  jmp     loc_14003ABD2
0x14003aa23  mov     rbx, [rdi+268h]
0x14003aa2a  lea     rcx, [r13+20h]; Src
0x14003aa2e  mov     edx, [r13+4]
0x14003aa32  mov     [rsp+88h+var_60], rsi; __int64
0x14003aa37  mov     [rsp+88h+var_68], r15; void *
0x14003aa3c  lea     r8, [rbx+40h]
0x14003aa40  call    SymCryptFdefRawDivMod
0x14003aa45  mov     eax, [rbx]
0x14003aa47  lea     rcx, off_14009C030
0x14003aa4e  and     eax, 380h
0x14003aa53  mov     r9d, r12d
0x14003aa56  mov     r8, rsi
0x14003aa59  mov     rdx, r15
0x14003aa5c  mov     rax, [rax+rcx]
0x14003aa60  mov     rcx, rbx
0x14003aa63  call    _guard_dispatch_icall
0x14003aa68  mov     rcx, [rdi+268h]
0x14003aa6f  mov     r9, rsi
0x14003aa72  mov     ebx, r12d
0x14003aa75  mov     r8, rbp
0x14003aa78  mov     rdx, r15
0x14003aa7b  mov     [rsp+88h+var_68], rbx
0x14003aa80  call    SymCryptModSquare
0x14003aa85  mov     r8, [rdi+278h]
0x14003aa8c  mov     r9, rbp
0x14003aa8f  mov     rcx, [rdi+268h]
0x14003aa96  mov     rdx, rbp
0x14003aa99  mov     [rsp+88h+var_60], rbx
0x14003aa9e  mov     [rsp+88h+var_68], rsi
0x14003aaa3  call    SymCryptModAdd
0x14003aaa8  mov     rcx, [rdi+268h]
0x14003aaaf  mov     r9, rbp
0x14003aab2  mov     r8, r15
0x14003aab5  mov     [rsp+88h+var_60], rbx
0x14003aaba  mov     rdx, rbp
0x14003aabd  mov     [rsp+88h+var_68], rsi
0x14003aac2  call    SymCryptModMul
0x14003aac7  mov     r8, [rdi+280h]
0x14003aace  mov     r9, rbp
0x14003aad1  mov     rcx, [rdi+268h]
0x14003aad8  mov     rdx, rbp
0x14003aadb  mov     [rsp+88h+var_60], rbx
0x14003aae0  mov     [rsp+88h+var_68], rsi
0x14003aae5  call    SymCryptModAdd
0x14003aaea  mov     rcx, [rdi+268h]
0x14003aaf1  lea     r8, [rsp+88h+arg_18]
0x14003aaf9  mov     r9, r14
0x14003aafc  mov     [rsp+88h+var_60], rbx
0x14003ab01  mov     rdx, rbp
0x14003ab04  mov     [rsp+88h+var_68], rsi
0x14003ab09  call    SymCryptModSqrt
0x14003ab0e  mov     r9d, eax
0x14003ab11  test    eax, eax
0x14003ab13  jz      short loc_14003AB36
0x14003ab15  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab1c  lea     rax, WPP_GLOBAL_Control
0x14003ab23  cmp     rcx, rax
0x14003ab26  jz      loc_14003ABD2
0x14003ab2c  mov     edx, 0Dh
0x14003ab31  jmp     loc_14003AA0E
0x14003ab36  mov     rcx, [rdi+268h]
0x14003ab3d  mov     r9, rsi
0x14003ab40  mov     r8, r13
0x14003ab43  mov     [rsp+88h+var_68], rbx
0x14003ab48  mov     rdx, r14
0x14003ab4b  call    SymCryptModElementToInt
0x14003ab50  mov     r9d, [rsp+88h+arg_0]
0x14003ab58  lea     rcx, [r13+20h]
0x14003ab5c  mov     r8, [rsp+88h+arg_10]
0x14003ab64  mov     edx, [r13+4]
0x14003ab68  call    SymCryptFdefRawGetValue
0x14003ab6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab74  lea     rax, WPP_GLOBAL_Control
0x14003ab7b  cmp     rcx, rax
0x14003ab7e  jz      short loc_14003ABD2
0x14003ab80  mov     rcx, [rcx+18h]
0x14003ab84  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x14003ab8b  mov     edx, 0Eh
0x14003ab90  mov     r9d, r12d
0x14003ab93  call    WPP_SF_d
0x14003ab98  jmp     short loc_14003ABD2
0x14003ab9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aba1  lea     rax, WPP_GLOBAL_Control
0x14003aba8  cmp     rcx, rax
0x14003abab  jz      short loc_14003ABCD
0x14003abad  mov     rcx, [rcx+18h]
0x14003abb1  mov     r9, r13
0x14003abb4  mov     [rsp+88h+var_50], rsi
0x14003abb9  mov     [rsp+88h+var_58], rbp
0x14003abbe  mov     [rsp+88h+var_60], r14
0x14003abc3  mov     [rsp+88h+var_68], r15
0x14003abc8  call    WPP_SF_qqqqq
0x14003abcd  test    r13, r13
0x14003abd0  jz      short loc_14003ABDA
0x14003abd2  mov     rcx, r13
0x14003abd5  call    SymCryptIntFree
0x14003abda  test    r15, r15
0x14003abdd  jz      short loc_14003AC29
0x14003abdf  mov     rax, [rdi+268h]
0x14003abe6  mov     rcx, r15
0x14003abe9  mov     edx, [rax+10h]
0x14003abec  call    SymCryptWipeAsm
0x14003abf1  mov     eax, [r15-4]
0x14003abf5  sub     r15, rax
0x14003abf8  jz      short loc_14003AC29
0x14003abfa  lea     rcx, [r15-10h]; P
0x14003abfe  mov     rax, [rcx]
0x14003ac01  test    rax, rax
0x14003ac04  jz      short loc_14003AC1A
0x14003ac06  mov     rdx, rcx; Entry
0x14003ac09  mov     rcx, rax; Lookaside
0x14003ac0c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003ac13  nop     dword ptr [rax+rax+00h]
0x14003ac18  jmp     short loc_14003AC29
0x14003ac1a  mov     edx, [rcx+8]; Tag
0x14003ac1d  call    cs:__imp_ExFreePoolWithTag
0x14003ac24  nop     dword ptr [rax+rax+00h]
0x14003ac29  test    r14, r14
0x14003ac2c  jz      short loc_14003AC78
0x14003ac2e  mov     rax, [rdi+268h]
0x14003ac35  mov     rcx, r14
0x14003ac38  mov     edx, [rax+10h]
0x14003ac3b  call    SymCryptWipeAsm
0x14003ac40  mov     eax, [r14-4]
0x14003ac44  sub     r14, rax
0x14003ac47  jz      short loc_14003AC78
0x14003ac49  lea     rcx, [r14-10h]; P
0x14003ac4d  mov     rax, [rcx]
0x14003ac50  test    rax, rax
0x14003ac53  jz      short loc_14003AC69
0x14003ac55  mov     rdx, rcx; Entry
  ... truncated ...
```

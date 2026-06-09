# SymCrypt802_11SaeCustomCreatePTGeneric

- ea: `0x14001c418`
- end: `0x14001cbc3`
- name: `SymCrypt802_11SaeCustomCreatePTGeneric`
- size: `1963`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, size_t, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation`

## callers

- `0x1400920ec`

## callees

- `0x140003454`
- `0x140004b1c`
- `0x140004b50`
- `0x140004ba8`
- `0x140004f50`
- `0x14001b3d8`
- `0x14001c418`
- `0x14001d0c0`
- `0x14001d0dc`
- `0x14001d1a4`
- `0x14001d634`
- `0x140020e74`
- `0x14002c2c0`
- `0x1400584a0`
- `0x1400586e4`
- `0x1400588dc`
- `0x14005954c`
- `0x14009a3d0`
- `0x14009a410`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ca5e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cabe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cb27`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cb70`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ca5e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cabe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cb27`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cb70`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ca80`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cacf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cb38`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cb81`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ca80`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cacf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cb38`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cb81`

## pseudocode

```c
__int64 __fastcall SymCrypt802_11SaeCustomCreatePTGeneric(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        const void *a4,
        size_t a5,
        const void *a6,
        size_t a7,
        __int64 a8,
        __int64 a9)
{
  __int64 GroupData; // rax
  __int64 v11; // rbx
  unsigned int Value; // ebx
  _DWORD *v13; // rax
  __int64 v14; // rdi
  unsigned int v15; // ecx
  unsigned int v16; // edx
  unsigned int v17; // r10d
  int v18; // r8d
  unsigned int v19; // r9d
  unsigned int v20; // eax
  unsigned int v21; // r8d
  size_t v22; // rax
  __int64 v23; // rax
  unsigned int v24; // eax
  char *v25; // rsi
  unsigned int v26; // ebx
  unsigned int v27; // r14d
  __int64 v28; // r15
  unsigned int v29; // ebx
  unsigned int v30; // ebp
  unsigned int v31; // eax
  unsigned int v32; // r12d
  _DWORD *v33; // rax
  _DWORD *v34; // r13
  unsigned int v35; // eax
  unsigned int v36; // ebp
  _DWORD *v37; // rax
  __int64 v38; // rbx
  char *v39; // r14
  __int64 v40; // rax
  unsigned int v41; // ecx
  __int64 v42; // rbx
  char *v43; // rbp
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  unsigned int v47; // ecx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // r12
  int v55; // r8d
  void *v56; // r9
  _DWORD *v57; // rbx
  int v58; // r8d
  void *v59; // r9
  _DWORD *v60; // rbx
  int v61; // r8d
  __int64 v62; // rdx
  PNPAGED_LOOKASIDE_LIST *v63; // rbp
  PNPAGED_LOOKASIDE_LIST *v64; // r14
  __int64 v65; // r15
  PNPAGED_LOOKASIDE_LIST *v66; // rsi
  int v68; // [rsp+30h] [rbp-308h]
  __int64 v69; // [rsp+50h] [rbp-2E8h]
  __int64 v70; // [rsp+58h] [rbp-2E0h]
  _DWORD *v71; // [rsp+60h] [rbp-2D8h]
  __int64 v72; // [rsp+68h] [rbp-2D0h]
  __int64 v73; // [rsp+70h] [rbp-2C8h]
  __int64 v74; // [rsp+78h] [rbp-2C0h]
  __int64 v78; // [rsp+A8h] [rbp-290h]
  _BYTE v79[560]; // [rsp+C0h] [rbp-278h] BYREF

  memset(v79, 0, sizeof(v79));
  GroupData = SymCryptSaeFindGroupData(a1);
  v74 = GroupData;
  v11 = GroupData;
  if ( !GroupData )
    return 32782;
  v13 = (_DWORD *)SymCryptEcurveAllocate(**(_QWORD **)(GroupData + 8));
  v14 = (__int64)v13;
  if ( !v13 )
    return 32783;
  v15 = v13[11];
  v16 = v13[14];
  v17 = v16;
  v18 = v13[4];
  if ( v16 <= v15 )
    v17 = v13[11];
  v78 = **(_QWORD **)(v11 + 16);
  v19 = 4480 * v18 + 64;
  if ( v19 <= v17 )
  {
    v20 = v13[11];
    if ( v16 > v15 )
      v20 = v16;
  }
  else
  {
    v20 = 4480 * v18 + 64;
  }
  v21 = (v18 << 8) + 64;
  if ( v21 <= v20 )
  {
    if ( v19 <= v17 )
    {
      v22 = v15;
      if ( v16 > v15 )
        v22 = v16;
    }
    else
    {
      v22 = v19;
    }
  }
  else
  {
    v22 = v21;
  }
  if ( a5 + a7 <= v22 )
  {
    if ( v19 <= v17 )
    {
      v24 = v15;
      if ( v16 > v15 )
        v24 = v16;
    }
    else
    {
      v24 = v19;
    }
    if ( v21 <= v24 )
    {
      if ( v19 <= v17 )
      {
        v21 = v15;
        if ( v16 > v15 )
          v21 = v16;
      }
      else
      {
        v21 = v19;
      }
    }
    v23 = v21;
  }
  else
  {
    v23 = a5 + a7;
  }
  v70 = v23;
  v25 = (char *)SymCryptCallbackAlloc(v23);
  v26 = ((unsigned int)(*(_DWORD *)(v14 + 12) + 7) >> 3) + ((unsigned int)(*(_DWORD *)(v14 + 12) + 7) >> 4);
  v72 = v26;
  v27 = 8 * v26;
  v28 = SymCryptCallbackAlloc(v26);
  v29 = 1;
  if ( v27 )
  {
    if ( v27 <= 0x100000 )
      v30 = (v27 >> 9) + (((v27 & 0x1FF) + 511) >> 9);
    else
      v30 = 0;
  }
  else
  {
    v30 = 1;
  }
  v71 = 0;
  v31 = SymCryptFdefSizeofIntFromDigits(v30);
  v32 = v31;
  if ( v31 )
  {
    v33 = (_DWORD *)SymCryptCallbackAlloc(v31);
    if ( v33 )
    {
      *v33 = 1732837376;
      v33[1] = v30;
      v33[2] = v32;
      v71 = v33;
    }
  }
  if ( v27 )
  {
    if ( v27 <= 0x100000 )
      v29 = (v27 >> 9) + (((v27 & 0x1FF) + 511) >> 9);
    else
      v29 = 0;
  }
  v34 = 0;
  v35 = SymCryptFdefSizeofIntFromDigits(v29);
  v36 = v35;
  if ( v35 )
  {
    v37 = (_DWORD *)SymCryptCallbackAlloc(v35);
    if ( v37 )
    {
      *v37 = 1732837376;
      v37[1] = v29;
      v37[2] = v36;
      v34 = v37;
    }
  }
  v38 = *(_QWORD *)(v14 + 616);
  v39 = 0;
  v40 = SymCryptCallbackAlloc(*(unsigned int *)(v38 + 16));
  if ( v40 )
  {
    v39 = (char *)v40;
    v41 = (*(_DWORD *)(v38 + 4) << 6) - 64;
    *(_QWORD *)(v41 + v40) = 0;
    *(_QWORD *)(v41 + v40 + 8) = 0;
    *(_QWORD *)(v41 + v40 + 16) = 0;
    *(_QWORD *)(v41 + v40 + 24) = 0;
    *(_QWORD *)(v41 + v40 + 32) = 0;
    *(_QWORD *)(v41 + v40 + 40) = 0;
    *(_QWORD *)(v41 + v40 + 48) = 0;
    *(_QWORD *)(v41 + v40 + 56) = 0;
  }
  v42 = *(_QWORD *)(v14 + 616);
  v43 = 0;
  v44 = SymCryptCallbackAlloc(*(unsigned int *)(v42 + 16));
  if ( v44 )
  {
    v43 = (char *)v44;
    v47 = (*(_DWORD *)(v42 + 4) << 6) - 64;
    *(_QWORD *)(v47 + v44) = 0;
    *(_QWORD *)(v47 + v44 + 8) = 0;
    *(_QWORD *)(v47 + v44 + 16) = 0;
    *(_QWORD *)(v47 + v44 + 24) = 0;
    *(_QWORD *)(v47 + v44 + 32) = 0;
    *(_QWORD *)(v47 + v44 + 40) = 0;
    *(_QWORD *)(v47 + v44 + 48) = 0;
    *(_QWORD *)(v47 + v44 + 56) = 0;
  }
  v73 = SymCryptEcpointAllocate(v14, v45, v46);
  v69 = SymCryptEcpointAllocate(v14, v48, v49);
  v52 = SymCryptEcpointAllocate(v14, v50, v51);
  v54 = v52;
  if ( v25 && v28 && v71 && v34 && v39 && v43 && v73 && v69 && v52 )
  {
    memmove(v25, a4, a5);
    if ( a6 )
      memmove(&v25[a5], a6, a7);
    Value = SymCryptHkdfExpandKey((unsigned int)v79, v78, (_DWORD)v25, (int)a5 + (int)a7, a2, a3);
    if ( !Value )
    {
      Value = SymCryptHkdfDerive(v79, "SAE Hash to Element u1 P1", 25, v28, v72);
      if ( !Value )
      {
        Value = SymCryptFdefRawSetValue(v28, v72, v55, (int)v71 + 32, v71[1]);
        if ( !Value )
        {
          v57 = *(_DWORD **)(v14 + 616);
          SymCryptFdefRawDivMod(v56, v39, (__int64)v25);
          (*(void (__fastcall **)(_DWORD *, char *, char *, __int64))((char *)&g_SymCryptModFns[6] + (*v57 & 0x380)))(
            v57,
            v39,
            v25,
            v70);
          SymCryptSswu(v14, *(_DWORD *)(v74 + 24), (__int64)v39, v73, v25, v70);
          Value = SymCryptHkdfDerive(v79, "SAE Hash to Element u2 P2", 25, v28, v72);
          if ( !Value )
          {
            Value = SymCryptFdefRawSetValue(v28, v72, v58, (int)v34 + 32, v34[1]);
            if ( !Value )
            {
              v60 = *(_DWORD **)(v14 + 616);
              SymCryptFdefRawDivMod(v59, v43, (__int64)v25);
              (*(void (__fastcall **)(_DWORD *, char *, char *, __int64))((char *)&g_SymCryptModFns[6] + (*v60 & 0x380)))(
                v60,
                v43,
                v25,
                v70);
              Value = SymCryptSswu(v14, *(_DWORD *)(v74 + 24), (__int64)v43, v69, v25, v70);
              if ( !Value )
              {
                SymCryptEcpointAdd(v14, v73, v69, v54, 0, (__int64)v25, v70);
                Value = SymCryptEcpointGetValue(v14, v54, v61, 2, a8, a9, v68, (__int64)v25, v70);
              }
            }
          }
        }
      }
    }
    v62 = v69;
  }
  else
  {
    v62 = v69;
    Value = 32783;
    if ( !v69 )
      goto LABEL_68;
  }
  SymCryptEcpointFree(v14, v62);
LABEL_68:
  if ( v73 )
    SymCryptEcpointFree(v14, v73);
  if ( v54 )
    SymCryptEcpointFree(v14, v54);
  if ( v43 )
  {
    SymCryptWipeAsm(v43, *(unsigned int *)(*(_QWORD *)(v14 + 616) + 16LL));
    v63 = (PNPAGED_LOOKASIDE_LIST *)&v43[-*((unsigned int *)v43 - 1)];
    if ( v63 )
    {
      if ( *(v63 - 2) )
        ExFreeToNPagedLookasideList(*(v63 - 2), v63 - 2);
      else
        ExFreePoolWithTag(v63 - 2, *((_DWORD *)v63 - 2));
    }
  }
  if ( v39 )
  {
    SymCryptWipeAsm(v39, *(unsigned int *)(*(_QWORD *)(v14 + 616) + 16LL));
    v64 = (PNPAGED_LOOKASIDE_LIST *)&v39[-*((unsigned int *)v39 - 1)];
    if ( v64 )
    {
      if ( *(v64 - 2) )
        ExFreeToNPagedLookasideList(*(v64 - 2), v64 - 2);
      else
        ExFreePoolWithTag(v64 - 2, *((_DWORD *)v64 - 2));
    }
  }
  if ( v34 )
    SymCryptIntFree(v34, v62, v53);
  if ( v71 )
    SymCryptIntFree(v71, v62, v53);
  if ( v28 )
  {
    SymCryptWipeAsm(v28, v72);
    v65 = v28 - *(unsigned int *)(v28 - 4);
    if ( v65 )
    {
      if ( *(_QWORD *)(v65 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v65 - 16), (PVOID)(v65 - 16));
      else
        ExFreePoolWithTag((PVOID)(v65 - 16), *(_DWORD *)(v65 - 16 + 8));
    }
  }
  if ( v25 )
  {
    SymCryptWipeAsm(v25, v70);
    v66 = (PNPAGED_LOOKASIDE_LIST *)&v25[-*((unsigned int *)v25 - 1)];
    if ( v66 )
    {
      if ( *(v66 - 2) )
        ExFreeToNPagedLookasideList(*(v66 - 2), v66 - 2);
      else
        ExFreePoolWithTag(v66 - 2, *((_DWORD *)v66 - 2));
    }
  }
  SymCryptEcurveFree(v14);
  return Value;
}

```

## disassembly

```asm
0x14001c418  mov     [rsp+arg_10], rbx
0x14001c41d  push    rbp
0x14001c41e  push    rsi
0x14001c41f  push    rdi
0x14001c420  push    r12
0x14001c422  push    r13
0x14001c424  push    r14
0x14001c426  push    r15
0x14001c428  sub     rsp, 300h
0x14001c42f  mov     rax, cs:__security_cookie
0x14001c436  xor     rax, rsp
0x14001c439  mov     [rsp+338h+var_48], rax
0x14001c441  mov     rax, [rsp+338h+arg_28]
0x14001c449  mov     ebx, ecx
0x14001c44b  mov     rsi, [rsp+338h+arg_20]
0x14001c453  lea     rcx, [rsp+338h+var_278]; void *
0x14001c45b  mov     [rsp+338h+var_2A8], rax
0x14001c463  mov     rax, [rsp+338h+arg_38]
0x14001c46b  mov     [rsp+338h+var_2A0], r8
0x14001c473  mov     r8d, 230h; Size
0x14001c479  mov     [rsp+338h+var_298], rdx
0x14001c481  xor     edx, edx; Val
0x14001c483  mov     [rsp+338h+var_288], rax
0x14001c48b  mov     [rsp+338h+Src], r9
0x14001c493  mov     [rsp+338h+Size], rsi
0x14001c49b  call    memset
0x14001c4a0  mov     ecx, ebx
0x14001c4a2  call    SymCryptSaeFindGroupData
0x14001c4a7  mov     [rsp+338h+var_2C0], rax
0x14001c4ac  mov     rbx, rax
0x14001c4af  test    rax, rax
0x14001c4b2  jnz     short loc_14001C4BE
0x14001c4b4  mov     ebx, 800Eh
0x14001c4b9  jmp     loc_14001CB95
0x14001c4be  mov     rcx, [rax+8]
0x14001c4c2  mov     rcx, [rcx]
0x14001c4c5  call    SymCryptEcurveAllocate
0x14001c4ca  mov     rdi, rax
0x14001c4cd  test    rax, rax
0x14001c4d0  jnz     short loc_14001C4DC
0x14001c4d2  mov     ebx, 800Fh
0x14001c4d7  jmp     loc_14001CB95
0x14001c4dc  mov     ecx, [rdi+2Ch]
0x14001c4df  mov     edx, [rdi+38h]
0x14001c4e2  mov     r10d, edx
0x14001c4e5  mov     r11, [rsp+338h+arg_30]
0x14001c4ed  mov     r8d, [rdi+10h]
0x14001c4f1  add     r11, rsi
0x14001c4f4  mov     rax, [rbx+10h]
0x14001c4f8  cmp     edx, ecx
0x14001c4fa  cmovbe  r10d, ecx
0x14001c4fe  imul    r9d, r8d, 1180h
0x14001c505  mov     rax, [rax]
0x14001c508  mov     [rsp+338h+var_290], rax
0x14001c510  add     r9d, 40h ; '@'
0x14001c514  cmp     r9d, r10d
0x14001c517  jbe     short loc_14001C51E
0x14001c519  mov     eax, r9d
0x14001c51c  jmp     short loc_14001C525
0x14001c51e  cmp     edx, ecx
0x14001c520  mov     eax, ecx
0x14001c522  cmova   eax, edx
0x14001c525  shl     r8d, 8
0x14001c529  add     r8d, 40h ; '@'
0x14001c52d  cmp     r8d, eax
0x14001c530  jbe     short loc_14001C537
0x14001c532  mov     eax, r8d
0x14001c535  jmp     short loc_14001C548
0x14001c537  cmp     r9d, r10d
0x14001c53a  jbe     short loc_14001C541
0x14001c53c  mov     eax, r9d
0x14001c53f  jmp     short loc_14001C548
0x14001c541  cmp     edx, ecx
0x14001c543  mov     eax, ecx
0x14001c545  cmova   eax, edx
0x14001c548  cmp     r11, rax
0x14001c54b  jbe     short loc_14001C552
0x14001c54d  mov     rax, r11
0x14001c550  jmp     short loc_14001C57E
0x14001c552  cmp     r9d, r10d
0x14001c555  jbe     short loc_14001C55C
0x14001c557  mov     eax, r9d
0x14001c55a  jmp     short loc_14001C563
0x14001c55c  cmp     edx, ecx
0x14001c55e  mov     eax, ecx
0x14001c560  cmova   eax, edx
0x14001c563  cmp     r8d, eax
0x14001c566  ja      short loc_14001C57B
0x14001c568  cmp     r9d, r10d
0x14001c56b  jbe     short loc_14001C572
0x14001c56d  mov     r8d, r9d
0x14001c570  jmp     short loc_14001C57B
0x14001c572  cmp     edx, ecx
0x14001c574  mov     r8d, ecx
0x14001c577  cmova   r8d, edx
0x14001c57b  mov     eax, r8d
0x14001c57e  mov     rcx, rax
0x14001c581  mov     [rsp+338h+var_2E0], rax
0x14001c586  call    SymCryptCallbackAlloc
0x14001c58b  mov     edx, [rdi+0Ch]
0x14001c58e  mov     rsi, rax
0x14001c591  add     edx, 7
0x14001c594  mov     ebx, edx
0x14001c596  shr     edx, 3
0x14001c599  shr     ebx, 4
0x14001c59c  add     ebx, edx
0x14001c59e  mov     eax, ebx
0x14001c5a0  mov     ecx, ebx
0x14001c5a2  mov     [rsp+338h+var_2D0], rax
0x14001c5a7  call    SymCryptCallbackAlloc
0x14001c5ac  lea     r14d, ds:0[rbx*8]
0x14001c5b4  mov     r15, rax
0x14001c5b7  mov     ebx, 1
0x14001c5bc  mov     r13d, 1FFh
0x14001c5c2  test    r14d, r14d
0x14001c5c5  jnz     short loc_14001C5CB
0x14001c5c7  mov     ebp, ebx
0x14001c5c9  jmp     short loc_14001C5EC
0x14001c5cb  cmp     r14d, 100000h
0x14001c5d2  jbe     short loc_14001C5D8
0x14001c5d4  xor     ebp, ebp
0x14001c5d6  jmp     short loc_14001C5EC
0x14001c5d8  mov     ebp, r14d
0x14001c5db  mov     eax, r14d
0x14001c5de  and     ebp, r13d
0x14001c5e1  shr     eax, 9
0x14001c5e4  add     ebp, r13d
0x14001c5e7  shr     ebp, 9
0x14001c5ea  add     ebp, eax
0x14001c5ec  mov     ecx, ebp
0x14001c5ee  mov     [rsp+338h+var_2D8], 0
0x14001c5f7  call    SymCryptFdefSizeofIntFromDigits
0x14001c5fc  mov     r12d, eax
0x14001c5ff  test    eax, eax
0x14001c601  jz      short loc_14001C622
0x14001c603  mov     ecx, r12d
0x14001c606  call    SymCryptCallbackAlloc
0x14001c60b  test    rax, rax
0x14001c60e  jz      short loc_14001C622
0x14001c610  mov     dword ptr [rax], 67490000h
0x14001c616  mov     [rax+4], ebp
0x14001c619  mov     [rax+8], r12d
0x14001c61d  mov     [rsp+338h+var_2D8], rax
0x14001c622  xor     r12d, r12d
0x14001c625  test    r14d, r14d
0x14001c628  jz      short loc_14001C64B
0x14001c62a  cmp     r14d, 100000h
0x14001c631  jbe     short loc_14001C638
0x14001c633  mov     ebx, r12d
0x14001c636  jmp     short loc_14001C64B
0x14001c638  mov     ebx, r14d
0x14001c63b  shr     r14d, 9
0x14001c63f  and     ebx, r13d
0x14001c642  add     ebx, r13d
0x14001c645  shr     ebx, 9
0x14001c648  add     ebx, r14d
0x14001c64b  mov     ecx, ebx
0x14001c64d  mov     r13, r12
0x14001c650  call    SymCryptFdefSizeofIntFromDigits
0x14001c655  mov     ebp, eax
0x14001c657  test    eax, eax
0x14001c659  jz      short loc_14001C676
0x14001c65b  mov     ecx, ebp
0x14001c65d  call    SymCryptCallbackAlloc
0x14001c662  test    rax, rax
0x14001c665  jz      short loc_14001C676
0x14001c667  mov     dword ptr [rax], 67490000h
0x14001c66d  mov     [rax+4], ebx
0x14001c670  mov     [rax+8], ebp
0x14001c673  mov     r13, rax
0x14001c676  mov     rbx, [rdi+268h]
0x14001c67d  mov     r14, r12
0x14001c680  mov     ecx, [rbx+10h]
0x14001c683  call    SymCryptCallbackAlloc
0x14001c688  test    rax, rax
0x14001c68b  jz      short loc_14001C6C0
0x14001c68d  mov     ecx, [rbx+4]
0x14001c690  mov     r14, rax
0x14001c693  shl     ecx, 6
0x14001c696  sub     ecx, 40h ; '@'
0x14001c699  mov     [rcx+rax], r12
0x14001c69d  mov     [rcx+rax+8], r12
0x14001c6a2  mov     [rcx+rax+10h], r12
0x14001c6a7  mov     [rcx+rax+18h], r12
0x14001c6ac  mov     [rcx+rax+20h], r12
0x14001c6b1  mov     [rcx+rax+28h], r12
0x14001c6b6  mov     [rcx+rax+30h], r12
0x14001c6bb  mov     [rcx+rax+38h], r12
0x14001c6c0  mov     rbx, [rdi+268h]
0x14001c6c7  mov     rbp, r12
0x14001c6ca  mov     ecx, [rbx+10h]
0x14001c6cd  call    SymCryptCallbackAlloc
0x14001c6d2  test    rax, rax
0x14001c6d5  jz      short loc_14001C70A
0x14001c6d7  mov     ecx, [rbx+4]
0x14001c6da  mov     rbp, rax
0x14001c6dd  shl     ecx, 6
0x14001c6e0  sub     ecx, 40h ; '@'
0x14001c6e3  mov     [rcx+rax], r12
0x14001c6e7  mov     [rcx+rax+8], r12
0x14001c6ec  mov     [rcx+rax+10h], r12
0x14001c6f1  mov     [rcx+rax+18h], r12
0x14001c6f6  mov     [rcx+rax+20h], r12
0x14001c6fb  mov     [rcx+rax+28h], r12
0x14001c700  mov     [rcx+rax+30h], r12
0x14001c705  mov     [rcx+rax+38h], r12
0x14001c70a  mov     rcx, rdi
0x14001c70d  call    SymCryptEcpointAllocate
0x14001c712  mov     rcx, rdi
0x14001c715  mov     [rsp+338h+var_2C8], rax
0x14001c71a  call    SymCryptEcpointAllocate
0x14001c71f  mov     rcx, rdi
0x14001c722  mov     [rsp+338h+var_2E8], rax
0x14001c727  mov     rbx, rax
0x14001c72a  call    SymCryptEcpointAllocate
0x14001c72f  mov     r12, rax
0x14001c732  test    rsi, rsi
0x14001c735  jz      loc_14001CA6C
0x14001c73b  test    r15, r15
0x14001c73e  jz      loc_14001CA6C
0x14001c744  cmp     [rsp+338h+var_2D8], 0
0x14001c74a  jz      loc_14001CA6C
0x14001c750  test    r13, r13
0x14001c753  jz      loc_14001CA6C
0x14001c759  test    r14, r14
0x14001c75c  jz      loc_14001CA6C
0x14001c762  test    rbp, rbp
0x14001c765  jz      loc_14001CA6C
0x14001c76b  cmp     [rsp+338h+var_2C8], 0
0x14001c771  jz      loc_14001CA6C
0x14001c777  test    rbx, rbx
0x14001c77a  jz      loc_14001CA6C
0x14001c780  test    rax, rax
0x14001c783  jz      loc_14001CA6C
0x14001c789  mov     rbx, [rsp+338h+Size]
0x14001c791  mov     rcx, rsi; void *
0x14001c794  mov     rdx, [rsp+338h+Src]; Src
0x14001c79c  mov     r8, rbx; Size
0x14001c79f  call    memmove
0x14001c7a4  mov     rax, [rsp+338h+var_2A8]
0x14001c7ac  test    rax, rax
0x14001c7af  jz      short loc_14001C7C5
0x14001c7b1  mov     r8, [rsp+338h+arg_30]; Size
0x14001c7b9  lea     rcx, [rbx+rsi]; void *
0x14001c7bd  mov     rdx, rax; Src
0x14001c7c0  call    memmove
0x14001c7c5  mov     rax, [rsp+338h+var_2A0]
0x14001c7cd  lea     rcx, [rsp+338h+var_278]
0x14001c7d5  mov     r9, [rsp+338h+arg_30]
0x14001c7dd  mov     r8, rsi
0x14001c7e0  mov     rdx, [rsp+338h+var_290]
0x14001c7e8  add     r9, rbx
0x14001c7eb  mov     [rsp+338h+var_310], rax
0x14001c7f0  mov     rax, [rsp+338h+var_298]
0x14001c7f8  mov     [rsp+338h+var_318], rax
0x14001c7fd  call    SymCryptHkdfExpandKey
0x14001c802  mov     ebx, eax
0x14001c804  test    eax, eax
0x14001c806  jnz     loc_14001C9FB
0x14001c80c  mov     rax, [rsp+338h+var_2D0]
0x14001c811  lea     r8d, [rbx+19h]
0x14001c815  mov     r9, r15
0x14001c818  mov     [rsp+338h+var_318], rax
0x14001c81d  lea     rdx, aSaeHashToEleme_1; "SAE Hash to Element u1 P1"
0x14001c824  lea     rcx, [rsp+338h+var_278]
0x14001c82c  call    SymCryptHkdfDerive
0x14001c831  mov     ebx, eax
0x14001c833  test    eax, eax
0x14001c835  jnz     loc_14001C9FB
0x14001c83b  mov     rax, [rsp+338h+var_2D8]
0x14001c840  mov     rcx, r15
0x14001c843  mov     rdx, [rsp+338h+var_2D0]
0x14001c848  lea     r9, [rax+20h]
0x14001c84c  mov     eax, [rax+4]
0x14001c84f  mov     dword ptr [rsp+338h+var_318], eax
0x14001c853  call    SymCryptFdefRawSetValue
0x14001c858  mov     ebx, eax
0x14001c85a  test    eax, eax
0x14001c85c  jnz     loc_14001C9FB
0x14001c862  mov     rbx, [rdi+268h]
0x14001c869  mov     rcx, r9; Src
0x14001c86c  mov     rdx, [rsp+338h+var_2D8]
0x14001c871  mov     [rsp+338h+var_310], rsi; __int64
0x14001c876  mov     [rsp+338h+var_318], r14; void *
0x14001c87b  lea     r8, [rbx+40h]
0x14001c87f  mov     edx, [rdx+4]
0x14001c882  call    SymCryptFdefRawDivMod
0x14001c887  mov     eax, [rbx]
0x14001c889  lea     rcx, g_SymCryptModFns
0x14001c890  mov     r9, [rsp+338h+var_2E0]
0x14001c895  and     eax, 380h
0x14001c89a  mov     r8, rsi
0x14001c89d  mov     rdx, r14
0x14001c8a0  mov     rax, [rax+rcx+30h]
0x14001c8a5  mov     rcx, rbx
0x14001c8a8  call    _guard_dispatch_icall
0x14001c8ad  mov     rdx, [rsp+338h+var_2C0]
0x14001c8b2  mov     r8, r14
0x14001c8b5  mov     rax, [rsp+338h+var_2E0]
0x14001c8ba  mov     rcx, rdi
  ... truncated ...
```

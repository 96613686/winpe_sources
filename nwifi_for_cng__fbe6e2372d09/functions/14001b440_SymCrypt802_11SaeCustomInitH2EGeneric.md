# SymCrypt802_11SaeCustomInitH2EGeneric

- ea: `0x14001b440`
- end: `0x14001bbe9`
- name: `SymCrypt802_11SaeCustomInitH2EGeneric`
- size: `1961`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, __int64, __int64, int *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation`

## callers

- `0x1400920b4`

## callees

- `0x140003454`
- `0x140004b1c`
- `0x140004b50`
- `0x140004dcc`
- `0x140006018`
- `0x140007d24`
- `0x140008904`
- `0x1400089f8`
- `0x14000bbcc`
- `0x14000cf24`
- `0x14001b3d8`
- `0x14001b440`
- `0x14001d0c0`
- `0x14001d0dc`
- `0x14001d144`
- `0x14001e320`
- `0x14002071c`
- `0x140020934`
- `0x14002c550`
- `0x1400599bc`
- `0x140059adc`
- `0x140059cc0`
- `0x14005aea8`
- `0x14009bbb0`
- `0x14009bbf0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ba7c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bac4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bb11`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bb87`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ba7c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bac4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bb11`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bb87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ba8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bb22`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bb44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bb98`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ba8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bb22`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bb44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bb98`

## pseudocode

```c
__int64 __fastcall SymCrypt802_11SaeCustomInitH2EGeneric(
        __int64 *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 GroupData; // rax
  __int64 v12; // rbx
  unsigned int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // r13
  __int64 *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  unsigned int v19; // ecx
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // ecx
  __int64 v25; // rax
  unsigned int v26; // eax
  unsigned int v27; // ebx
  _DWORD *v28; // r15
  unsigned int v29; // eax
  unsigned int v30; // edi
  _DWORD *v31; // rax
  __int64 v32; // rdi
  unsigned int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned int v36; // esi
  __int64 v37; // rax
  __int64 v38; // rax
  unsigned int v39; // edx
  unsigned int v40; // ecx
  unsigned int v41; // r8d
  unsigned int v42; // r9d
  unsigned int v43; // ecx
  unsigned int v44; // ebx
  unsigned int v45; // eax
  __int64 v46; // r14
  __int64 v47; // rax
  __int64 v48; // rsi
  int v49; // ecx
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // rax
  unsigned __int64 v52; // rcx
  int v53; // edx
  unsigned int *v54; // r14
  char *Src; // r15
  __int64 v56; // rax
  unsigned int v57; // ecx
  __int64 v58; // rax
  int v59; // r8d
  __int64 v60; // rdx
  unsigned int v61; // ecx
  int v62; // r9d
  __int64 v63; // rax
  __int64 v64; // rcx
  PNPAGED_LOOKASIDE_LIST *v65; // r15
  __int64 v66; // rdx
  __int64 v67; // rdi
  __int64 v68; // rsi
  __int64 v70; // [rsp+50h] [rbp-B0h]
  __int64 v71; // [rsp+58h] [rbp-A8h]
  __int64 v72; // [rsp+60h] [rbp-A0h]
  __int64 v73; // [rsp+60h] [rbp-A0h]
  _DWORD *v74; // [rsp+68h] [rbp-98h]
  int v75[2]; // [rsp+70h] [rbp-90h]
  _BYTE v78[272]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v79[544]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v80; // [rsp+3D0h] [rbp+2D0h] BYREF
  int v81[4]; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int128 v82; // [rsp+3F0h] [rbp+2F0h]
  __int128 v83; // [rsp+400h] [rbp+300h]
  _OWORD v84[3]; // [rsp+410h] [rbp+310h] BYREF

  memset(v84, 0, sizeof(v84));
  *(_OWORD *)v81 = 0;
  v82 = 0;
  v83 = 0;
  v80 = 0;
  memset(v79, 0, sizeof(v79));
  memset(v78, 0, sizeof(v78));
  a1[4] = 0;
  a1[5] = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  a1[3] = 0;
  GroupData = SymCryptSaeFindGroupData(a2);
  v12 = GroupData;
  if ( !GroupData )
  {
    v13 = 32782;
LABEL_81:
    SymCrypt802_11SaeCustomDestroy(a1);
    return v13;
  }
  v14 = SymCryptEcurveAllocate(**(_QWORD **)(GroupData + 8));
  v15 = v14;
  if ( !v14 )
    goto LABEL_80;
  *a1 = v14;
  v16 = *(__int64 **)(v12 + 16);
  v17 = *(_QWORD *)(v15 + 624);
  v72 = *v16;
  *(_QWORD *)v75 = *(_QWORD *)(*v16 + 48);
  v18 = SymCryptCallbackAlloc(*(unsigned int *)(v17 + 16));
  if ( !v18 )
  {
    a1[2] = 0;
    goto LABEL_80;
  }
  v19 = (*(_DWORD *)(v17 + 4) << 6) - 64;
  *(_QWORD *)(v19 + v18) = 0;
  *(_QWORD *)(v19 + v18 + 8) = 0;
  *(_QWORD *)(v19 + v18 + 16) = 0;
  *(_QWORD *)(v19 + v18 + 24) = 0;
  *(_QWORD *)(v19 + v18 + 32) = 0;
  *(_QWORD *)(v19 + v18 + 40) = 0;
  *(_QWORD *)(v19 + v18 + 48) = 0;
  *(_QWORD *)(v19 + v18 + 56) = 0;
  a1[2] = v18;
  v20 = *(_QWORD *)(v15 + 624);
  v21 = SymCryptCallbackAlloc(*(unsigned int *)(v20 + 16));
  if ( !v21 )
  {
    a1[3] = 0;
    goto LABEL_80;
  }
  v24 = (*(_DWORD *)(v20 + 4) << 6) - 64;
  *(_QWORD *)(v24 + v21) = 0;
  *(_QWORD *)(v24 + v21 + 8) = 0;
  *(_QWORD *)(v24 + v21 + 16) = 0;
  *(_QWORD *)(v24 + v21 + 24) = 0;
  *(_QWORD *)(v24 + v21 + 32) = 0;
  *(_QWORD *)(v24 + v21 + 40) = 0;
  *(_QWORD *)(v24 + v21 + 48) = 0;
  *(_QWORD *)(v24 + v21 + 56) = 0;
  a1[3] = v21;
  v25 = SymCryptEcpointAllocate(v15, v22, v23);
  a1[4] = v25;
  if ( !v25 )
  {
LABEL_80:
    v13 = 32783;
    goto LABEL_81;
  }
  v26 = *(_DWORD *)(v15 + 24);
  if ( v26 )
  {
    if ( v26 <= 0x100000 )
      v27 = (*(_DWORD *)(v15 + 24) >> 9) + (((*(_DWORD *)(v15 + 24) & 0x1FFu) + 511) >> 9);
    else
      v27 = 0;
  }
  else
  {
    v27 = 1;
  }
  v74 = 0;
  v28 = 0;
  v29 = SymCryptFdefSizeofIntFromDigits(v27);
  v30 = v29;
  if ( v29 )
  {
    v31 = (_DWORD *)SymCryptCallbackAlloc(v29);
    if ( v31 )
    {
      *v31 = 1732837376;
      v31[1] = v27;
      v31[2] = v30;
      v28 = v31;
      v74 = v31;
    }
  }
  v32 = 0;
  v33 = SymCryptFdefSizeofModulusFromDigits(v27);
  if ( v33 )
  {
    v36 = v33;
    v37 = SymCryptCallbackAlloc(v33);
    if ( v37 )
      v32 = SymCryptFdefModulusCreate(v37, v36, v27);
  }
  v38 = SymCryptEcpointAllocate(v15, v34, v35);
  v39 = *(_DWORD *)(v15 + 44);
  v40 = v39;
  v41 = *(_DWORD *)(v15 + 48) + *(_DWORD *)(v15 + 52);
  v42 = *(_DWORD *)(v15 + 56);
  v71 = v38;
  if ( v39 <= v41 )
    v40 = *(_DWORD *)(v15 + 48) + *(_DWORD *)(v15 + 52);
  if ( v42 <= v40 )
  {
    v43 = *(_DWORD *)(v15 + 48) + *(_DWORD *)(v15 + 52);
    if ( v39 > v41 )
      v43 = *(_DWORD *)(v15 + 44);
  }
  else
  {
    v43 = *(_DWORD *)(v15 + 56);
  }
  v44 = (v27 << 8) + 64;
  if ( v44 <= v43 )
  {
    v45 = *(_DWORD *)(v15 + 48) + *(_DWORD *)(v15 + 52);
    if ( v39 > v41 )
      v45 = *(_DWORD *)(v15 + 44);
    if ( v42 <= v45 )
    {
      v44 = *(_DWORD *)(v15 + 48) + *(_DWORD *)(v15 + 52);
      if ( v39 > v41 )
        v44 = *(_DWORD *)(v15 + 44);
    }
    else
    {
      v44 = *(_DWORD *)(v15 + 56);
    }
  }
  v46 = v44;
  v70 = v44;
  v47 = SymCryptCallbackAlloc(v44);
  v48 = v47;
  if ( !v28 || !v32 || !v71 || !v47 )
  {
    v66 = v71;
    v13 = 32783;
    if ( !v71 )
      goto LABEL_61;
    goto LABEL_60;
  }
  v49 = *a5;
  WORD2(v80) = *((_WORD *)a5 + 2);
  LODWORD(v80) = v49;
  v50 = _byteswap_uint64(v80);
  LODWORD(v80) = *(_DWORD *)a6;
  WORD2(v80) = *(_WORD *)(a6 + 4);
  v51 = _byteswap_uint64(v80);
  if ( v50 <= v51 )
  {
    v52 = v51;
  }
  else
  {
    v52 = v50;
    v50 = v51;
  }
  *(_QWORD *)&v80 = _byteswap_uint64(v52);
  *(_QWORD *)((char *)&v80 + 6) = _byteswap_uint64(v50);
  (*(void (__fastcall **)(_BYTE *, _OWORD *, int *))v72)(v79, v84, *(int **)v75);
  (*(void (__fastcall **)(_BYTE *, _BYTE *))(v72 + 8))(v78, v79);
  (*(void (__fastcall **)(_BYTE *, __int128 *, __int64))(v72 + 16))(v78, &v80, 12);
  (*(void (__fastcall **)(_BYTE *, int *))(v72 + 24))(v78, v81);
  SymCryptFdefRawSubUint32(*(_QWORD *)(v15 + 624) + 128LL, 1, v28 + 8, (unsigned int)v28[1]);
  *(_DWORD *)(v32 + 12) = v53;
  SymCryptFdefIntToDivisor(v28, v32 + 64);
  *(_DWORD *)v32 = SymCryptFdefDecideModulusType(v28, *(unsigned int *)(v32 + 4), 1, 1);
  *(_QWORD *)(v32 + 24) = -SymCryptInverseMod2e64(*((_QWORD *)v28 + 4));
  (*(void (__fastcall **)(__int64, __int64, _QWORD))((char *)&off_14009E048 + (*(_DWORD *)v32 & 0x380)))(v32, v48, v44);
  v54 = (unsigned int *)(v32 + 16);
  Src = 0;
  v56 = SymCryptCallbackAlloc(*(unsigned int *)(v32 + 16));
  if ( v56 )
  {
    Src = (char *)v56;
    v57 = (*(_DWORD *)(v32 + 4) << 6) - 64;
    *(_QWORD *)(v57 + v56) = 0;
    *(_QWORD *)(v57 + v56 + 8) = 0;
    *(_QWORD *)(v57 + v56 + 16) = 0;
    *(_QWORD *)(v57 + v56 + 24) = 0;
    *(_QWORD *)(v57 + v56 + 32) = 0;
    *(_QWORD *)(v57 + v56 + 40) = 0;
    *(_QWORD *)(v57 + v56 + 48) = 0;
    *(_QWORD *)(v57 + v56 + 56) = 0;
  }
  v73 = 0;
  v58 = SymCryptCallbackAlloc(*v54);
  if ( v58 )
  {
    v60 = v58;
    v61 = (*(_DWORD *)(v32 + 4) << 6) - 64;
    v73 = v58;
    *(_QWORD *)(v61 + v58) = 0;
    *(_QWORD *)(v61 + v58 + 8) = 0;
    *(_QWORD *)(v61 + v58 + 16) = 0;
    *(_QWORD *)(v61 + v58 + 24) = 0;
    *(_QWORD *)(v61 + v58 + 32) = 0;
    *(_QWORD *)(v61 + v58 + 40) = 0;
    *(_QWORD *)(v61 + v58 + 48) = 0;
    *(_QWORD *)(v61 + v58 + 56) = 0;
  }
  else
  {
    v60 = 0;
  }
  if ( Src && v60 )
  {
    v13 = SymCryptModElementSetValue((int)v81, v75[0], v59, v32, Src, v48, v44);
    if ( !v13 )
    {
      SymCryptModElementSetValueUint32(1, v32, v73, v48, v70);
      SymCryptModAdd(v32, (_DWORD)Src, v73, (_DWORD)Src, v48, v70);
      SymCryptModElementToInt(v32, (_DWORD)Src, (_DWORD)v74, v48, v70);
      v13 = SymCryptEcpointSetValue(v15, a3, a4);
      if ( !v13 )
      {
        v13 = SymCryptEcpointScalarMul(v15, (_DWORD)v74, v71, v62, a1[4], v48, v70);
        if ( !v13 )
          v13 = SymCrypt802_11SaeCustomSetRandMask(a1, a7, 48, a9, 48, v48, v70);
      }
    }
    goto LABEL_51;
  }
  v13 = 32783;
  if ( v60 )
  {
    v73 = v60;
LABEL_51:
    SymCryptWipeAsm(v73, *v54);
    v63 = *(unsigned int *)(v73 - 4);
    if ( v73 != v63 )
    {
      v64 = v73 - v63 - 16;
      if ( *(_QWORD *)v64 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v64, (PVOID)v64);
      else
        ExFreePoolWithTag((PVOID)v64, *(_DWORD *)(v64 + 8));
    }
  }
  if ( Src )
  {
    SymCryptWipeAsm(Src, *v54);
    v65 = (PNPAGED_LOOKASIDE_LIST *)&Src[-*((unsigned int *)Src - 1)];
    if ( v65 )
    {
      if ( *(v65 - 2) )
        ExFreeToNPagedLookasideList(*(v65 - 2), v65 - 2);
      else
        ExFreePoolWithTag(v65 - 2, *((_DWORD *)v65 - 2));
    }
  }
  v66 = v71;
  v28 = v74;
  v46 = v70;
LABEL_60:
  SymCryptEcpointFree(v15, v66);
LABEL_61:
  if ( v32 )
  {
    SymCryptWipeAsm(v32, *(unsigned int *)(v32 + 8));
    v67 = v32 - *(unsigned int *)(v32 - 4);
    if ( v67 )
    {
      if ( *(_QWORD *)(v67 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v67 - 16), (PVOID)(v67 - 16));
      else
        ExFreePoolWithTag((PVOID)(v67 - 16), *(_DWORD *)(v67 - 16 + 8));
    }
  }
  if ( v28 )
    SymCryptIntFree(v28);
  if ( v48 )
  {
    SymCryptWipeAsm(v48, v46);
    v68 = v48 - *(unsigned int *)(v48 - 4);
    if ( v68 )
    {
      if ( *(_QWORD *)(v68 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v68 - 16), (PVOID)(v68 - 16));
      else
        ExFreePoolWithTag((PVOID)(v68 - 16), *(_DWORD *)(v68 - 16 + 8));
    }
  }
  if ( v13 )
    goto LABEL_81;
  return v13;
}

```

## disassembly

```asm
0x14001b440  push    rbp
0x14001b442  push    rbx
0x14001b443  push    rsi
0x14001b444  push    rdi
0x14001b445  push    r12
0x14001b447  push    r13
0x14001b449  push    r14
0x14001b44b  push    r15
0x14001b44d  lea     rbp, [rsp-358h]
0x14001b455  sub     rsp, 458h
0x14001b45c  mov     rax, cs:__security_cookie
0x14001b463  xor     rax, rsp
0x14001b466  mov     [rbp+390h+var_50], rax
0x14001b46d  mov     rax, [rbp+390h+arg_30]
0x14001b474  xorps   xmm0, xmm0
0x14001b477  xorps   xmm1, xmm1
0x14001b47a  mov     [rbp+390h+var_400], rax
0x14001b47e  mov     rax, [rbp+390h+arg_40]
0x14001b485  mov     ebx, edx
0x14001b487  mov     [rbp+390h+var_410], r8
0x14001b48b  mov     r12, rcx
0x14001b48e  xor     edx, edx; Val
0x14001b490  mov     [rbp+390h+var_408], rax
0x14001b494  mov     r8d, 220h; Size
0x14001b49a  mov     [rsp+490h+var_418], r9
0x14001b49f  lea     rcx, [rbp+390h+var_2E0]; void *
0x14001b4a6  movups  [rbp+390h+var_80], xmm0
0x14001b4ad  movups  [rbp+390h+var_70], xmm0
0x14001b4b4  movups  [rbp+390h+var_60], xmm0
0x14001b4bb  movups  xmmword ptr [rbp+390h+var_B0], xmm1
0x14001b4c2  movups  [rbp+390h+var_A0], xmm1
0x14001b4c9  movups  [rbp+390h+var_90], xmm1
0x14001b4d0  movups  [rbp+390h+var_C0], xmm0
0x14001b4d7  call    memset
0x14001b4dc  xor     edx, edx; Val
0x14001b4de  lea     rcx, [rbp+390h+var_3F0]; void *
0x14001b4e2  mov     r8d, 110h; Size
0x14001b4e8  call    memset
0x14001b4ed  xor     r14d, r14d
0x14001b4f0  mov     ecx, ebx
0x14001b4f2  mov     [r12+20h], r14
0x14001b4f7  mov     [r12+28h], r14
0x14001b4fc  mov     [r12], r14
0x14001b500  mov     [r12+8], r14
0x14001b505  mov     [r12+10h], r14
0x14001b50a  mov     [r12+18h], r14
0x14001b50f  call    SymCryptSaeFindGroupData
0x14001b514  mov     rbx, rax
0x14001b517  test    rax, rax
0x14001b51a  jnz     short loc_14001B526
0x14001b51c  mov     ebx, 800Eh
0x14001b521  jmp     loc_14001BBBB
0x14001b526  mov     rcx, [rax+8]
0x14001b52a  mov     rcx, [rcx]
0x14001b52d  call    SymCryptEcurveAllocate
0x14001b532  mov     r13, rax
0x14001b535  test    rax, rax
0x14001b538  jz      loc_14001BBB6
0x14001b53e  mov     [r12], rax
0x14001b542  mov     rax, [rbx+10h]
0x14001b546  mov     rbx, [r13+270h]
0x14001b54d  mov     rcx, [rax]
0x14001b550  mov     [rsp+490h+var_430], rcx
0x14001b555  mov     rax, [rcx+30h]
0x14001b559  mov     ecx, [rbx+10h]
0x14001b55c  mov     qword ptr [rsp+490h+var_420], rax
0x14001b561  call    SymCryptCallbackAlloc
0x14001b566  test    rax, rax
0x14001b569  jz      loc_14001BBB1
0x14001b56f  mov     ecx, [rbx+4]
0x14001b572  shl     ecx, 6
0x14001b575  sub     ecx, 40h ; '@'
0x14001b578  mov     [rcx+rax], r14
0x14001b57c  mov     [rcx+rax+8], r14
0x14001b581  mov     [rcx+rax+10h], r14
0x14001b586  mov     [rcx+rax+18h], r14
0x14001b58b  mov     [rcx+rax+20h], r14
0x14001b590  mov     [rcx+rax+28h], r14
0x14001b595  mov     [rcx+rax+30h], r14
0x14001b59a  mov     [rcx+rax+38h], r14
0x14001b59f  mov     [r12+10h], rax
0x14001b5a4  mov     rbx, [r13+270h]
0x14001b5ab  mov     ecx, [rbx+10h]
0x14001b5ae  call    SymCryptCallbackAlloc
0x14001b5b3  test    rax, rax
0x14001b5b6  jz      loc_14001BBAA
0x14001b5bc  mov     ecx, [rbx+4]
0x14001b5bf  shl     ecx, 6
0x14001b5c2  sub     ecx, 40h ; '@'
0x14001b5c5  mov     [rcx+rax], r14
0x14001b5c9  mov     [rcx+rax+8], r14
0x14001b5ce  mov     [rcx+rax+10h], r14
0x14001b5d3  mov     [rcx+rax+18h], r14
0x14001b5d8  mov     [rcx+rax+20h], r14
0x14001b5dd  mov     [rcx+rax+28h], r14
0x14001b5e2  mov     [rcx+rax+30h], r14
0x14001b5e7  mov     [rcx+rax+38h], r14
0x14001b5ec  mov     rcx, r13
0x14001b5ef  mov     [r12+18h], rax
0x14001b5f4  call    SymCryptEcpointAllocate
0x14001b5f9  mov     [r12+20h], rax
0x14001b5fe  test    rax, rax
0x14001b601  jz      loc_14001BBB6
0x14001b607  mov     eax, [r13+18h]
0x14001b60b  test    eax, eax
0x14001b60d  jnz     short loc_14001B614
0x14001b60f  lea     ebx, [rax+1]
0x14001b612  jmp     short loc_14001B633
0x14001b614  cmp     eax, 100000h
0x14001b619  jbe     short loc_14001B620
0x14001b61b  mov     ebx, r14d
0x14001b61e  jmp     short loc_14001B633
0x14001b620  mov     ebx, eax
0x14001b622  mov     ecx, 1FFh
0x14001b627  and     ebx, ecx
0x14001b629  shr     eax, 9
0x14001b62c  add     ebx, ecx
0x14001b62e  shr     ebx, 9
0x14001b631  add     ebx, eax
0x14001b633  mov     ecx, ebx
0x14001b635  mov     [rsp+490h+var_428], r14
0x14001b63a  mov     r15, r14
0x14001b63d  call    SymCryptFdefSizeofIntFromDigits
0x14001b642  mov     edi, eax
0x14001b644  test    eax, eax
0x14001b646  jz      short loc_14001B668
0x14001b648  mov     ecx, edi
0x14001b64a  call    SymCryptCallbackAlloc
0x14001b64f  test    rax, rax
0x14001b652  jz      short loc_14001B668
0x14001b654  mov     dword ptr [rax], 67490000h
0x14001b65a  mov     [rax+4], ebx
0x14001b65d  mov     [rax+8], edi
0x14001b660  mov     r15, rax
0x14001b663  mov     [rsp+490h+var_428], rax
0x14001b668  mov     ecx, ebx
0x14001b66a  mov     rdi, r14
0x14001b66d  call    SymCryptFdefSizeofModulusFromDigits
0x14001b672  test    eax, eax
0x14001b674  jz      short loc_14001B694
0x14001b676  mov     ecx, eax
0x14001b678  mov     esi, eax
0x14001b67a  call    SymCryptCallbackAlloc
0x14001b67f  test    rax, rax
0x14001b682  jz      short loc_14001B694
0x14001b684  mov     r8d, ebx
0x14001b687  mov     edx, esi
0x14001b689  mov     rcx, rax
0x14001b68c  call    SymCryptFdefModulusCreate
0x14001b691  mov     rdi, rax
0x14001b694  mov     rcx, r13
0x14001b697  call    SymCryptEcpointAllocate
0x14001b69c  mov     edx, [r13+2Ch]
0x14001b6a0  mov     ecx, edx
0x14001b6a2  mov     r8d, [r13+34h]
0x14001b6a6  add     r8d, [r13+30h]
0x14001b6aa  mov     r9d, [r13+38h]
0x14001b6ae  cmp     edx, r8d
0x14001b6b1  mov     [rsp+490h+var_438], rax
0x14001b6b6  cmovbe  ecx, r8d
0x14001b6ba  cmp     r9d, ecx
0x14001b6bd  jbe     short loc_14001B6C4
0x14001b6bf  mov     ecx, r9d
0x14001b6c2  jmp     short loc_14001B6CD
0x14001b6c4  cmp     edx, r8d
0x14001b6c7  mov     ecx, r8d
0x14001b6ca  cmova   ecx, edx
0x14001b6cd  shl     ebx, 8
0x14001b6d0  add     ebx, 40h ; '@'
0x14001b6d3  cmp     ebx, ecx
0x14001b6d5  ja      short loc_14001B6F3
0x14001b6d7  cmp     edx, r8d
0x14001b6da  mov     eax, r8d
0x14001b6dd  cmova   eax, edx
0x14001b6e0  cmp     r9d, eax
0x14001b6e3  jbe     short loc_14001B6EA
0x14001b6e5  mov     ebx, r9d
0x14001b6e8  jmp     short loc_14001B6F3
0x14001b6ea  cmp     edx, r8d
0x14001b6ed  mov     ebx, r8d
0x14001b6f0  cmova   ebx, edx
0x14001b6f3  mov     r14d, ebx
0x14001b6f6  mov     ecx, ebx
0x14001b6f8  mov     [rsp+490h+var_440], r14
0x14001b6fd  call    SymCryptCallbackAlloc
0x14001b702  mov     rsi, rax
0x14001b705  test    r15, r15
0x14001b708  jz      loc_14001BB30
0x14001b70e  test    rdi, rdi
0x14001b711  jz      loc_14001BB30
0x14001b717  cmp     [rsp+490h+var_438], 0
0x14001b71d  jz      loc_14001BB30
0x14001b723  test    rax, rax
0x14001b726  jz      loc_14001BB30
0x14001b72c  mov     rax, [rbp+390h+arg_20]
0x14001b733  mov     ecx, [rax]
0x14001b735  movzx   eax, word ptr [rax+4]
0x14001b739  mov     word ptr [rbp+390h+var_C0+4], ax
0x14001b740  mov     dword ptr [rbp+390h+var_C0], ecx
0x14001b746  mov     rdx, qword ptr [rbp+390h+var_C0]
0x14001b74d  mov     rcx, [rbp+390h+arg_28]
0x14001b754  bswap   rdx
0x14001b757  mov     eax, [rcx]
0x14001b759  mov     dword ptr [rbp+390h+var_C0], eax
0x14001b75f  movzx   eax, word ptr [rcx+4]
0x14001b763  mov     word ptr [rbp+390h+var_C0+4], ax
0x14001b76a  mov     rax, qword ptr [rbp+390h+var_C0]
0x14001b771  bswap   rax
0x14001b774  cmp     rdx, rax
0x14001b777  jbe     short loc_14001B781
0x14001b779  mov     rcx, rdx
0x14001b77c  mov     rdx, rax
0x14001b77f  jmp     short loc_14001B784
0x14001b781  mov     rcx, rax
0x14001b784  mov     rbx, [rsp+490h+var_430]
0x14001b789  mov     r8, qword ptr [rsp+490h+var_420]
0x14001b78e  bswap   rcx
0x14001b791  mov     qword ptr [rbp+390h+var_C0], rcx
0x14001b798  lea     rcx, [rbp+390h+var_2E0]
0x14001b79f  bswap   rdx
0x14001b7a2  mov     qword ptr [rbp+390h+var_C0+6], rdx
0x14001b7a9  lea     rdx, [rbp+390h+var_80]
0x14001b7b0  mov     rax, [rbx]
0x14001b7b3  call    _guard_dispatch_icall
0x14001b7b8  mov     rax, [rbx+8]
0x14001b7bc  lea     rdx, [rbp+390h+var_2E0]
0x14001b7c3  lea     rcx, [rbp+390h+var_3F0]
0x14001b7c7  call    _guard_dispatch_icall
0x14001b7cc  mov     rax, [rbx+10h]
0x14001b7d0  lea     rdx, [rbp+390h+var_C0]
0x14001b7d7  mov     r8d, 0Ch
0x14001b7dd  lea     rcx, [rbp+390h+var_3F0]
0x14001b7e1  call    _guard_dispatch_icall
0x14001b7e6  mov     rax, [rbx+18h]
0x14001b7ea  lea     rdx, [rbp+390h+var_B0]
0x14001b7f1  lea     rcx, [rbp+390h+var_3F0]
0x14001b7f5  call    _guard_dispatch_icall
0x14001b7fa  mov     rcx, [r13+270h]
0x14001b801  lea     r8, [r15+20h]
0x14001b805  mov     r9d, [r15+4]
0x14001b809  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14001b80d  mov     edx, 1
0x14001b812  call    SymCryptFdefRawSubUint32
0x14001b817  mov     [rdi+0Ch], edx
0x14001b81a  mov     rcx, r15
0x14001b81d  lea     rdx, [rdi+40h]
0x14001b821  call    SymCryptFdefIntToDivisor
0x14001b826  mov     edx, [rdi+4]
0x14001b829  mov     eax, 1
0x14001b82e  mov     r9d, eax
0x14001b831  mov     r8d, eax
0x14001b834  mov     rcx, r15
0x14001b837  call    SymCryptFdefDecideModulusType
0x14001b83c  mov     [rdi], eax
0x14001b83e  mov     eax, [r15+20h]
0x14001b842  mov     ecx, [r15+24h]
0x14001b846  shl     rcx, 20h
0x14001b84a  or      rcx, rax
0x14001b84d  call    SymCryptInverseMod2e64
0x14001b852  neg     rax
0x14001b855  lea     rcx, off_14009E048
0x14001b85c  mov     [rdi+18h], rax
0x14001b860  mov     r8, r14
0x14001b863  mov     eax, [rdi]
0x14001b865  mov     rdx, rsi
0x14001b868  and     eax, 380h
0x14001b86d  mov     rax, [rax+rcx]
0x14001b871  mov     rcx, rdi
0x14001b874  call    _guard_dispatch_icall
0x14001b879  lea     r14, [rdi+10h]
0x14001b87d  xor     ebx, ebx
0x14001b87f  mov     ecx, [r14]
0x14001b882  mov     r15d, ebx
0x14001b885  call    SymCryptCallbackAlloc
0x14001b88a  test    rax, rax
0x14001b88d  jz      short loc_14001B8C2
0x14001b88f  mov     ecx, [rdi+4]
0x14001b892  mov     r15, rax
0x14001b895  shl     ecx, 6
0x14001b898  sub     ecx, 40h ; '@'
0x14001b89b  mov     [rcx+rax], rbx
0x14001b89f  mov     [rcx+rax+8], rbx
0x14001b8a4  mov     [rcx+rax+10h], rbx
0x14001b8a9  mov     [rcx+rax+18h], rbx
0x14001b8ae  mov     [rcx+rax+20h], rbx
0x14001b8b3  mov     [rcx+rax+28h], rbx
0x14001b8b8  mov     [rcx+rax+30h], rbx
0x14001b8bd  mov     [rcx+rax+38h], rbx
0x14001b8c2  mov     ecx, [r14]
0x14001b8c5  mov     [rsp+490h+var_430], rbx
0x14001b8ca  call    SymCryptCallbackAlloc
0x14001b8cf  test    rax, rax
0x14001b8d2  jz      short loc_14001B90E
0x14001b8d4  mov     ecx, [rdi+4]
0x14001b8d7  mov     rdx, rax
0x14001b8da  shl     ecx, 6
0x14001b8dd  sub     ecx, 40h ; '@'
0x14001b8e0  mov     [rsp+490h+var_430], rax
0x14001b8e5  mov     [rcx+rax], rbx
0x14001b8e9  mov     [rcx+rax+8], rbx
  ... truncated ...
```

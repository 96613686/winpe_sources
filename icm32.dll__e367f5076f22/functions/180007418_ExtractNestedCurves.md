# ExtractNestedCurves

- ea: `0x180007418`
- end: `0x18000798b`
- name: `ExtractNestedCurves`
- size: `1395`
- prototype: `__int64 __fastcall(void *, TAGTYPE, unsigned int, unsigned __int8, unsigned __int64 dwOffset, char, unsigned __int8, __int64 *)`
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x18001a358`
- `0x18001a490`
- `0x180020984`
- `0x180020c14`
- `0x180021348`

## callees

- `0x1800042e0`
- `0x180006008`
- `0x18000604c`
- `0x1800060f0`
- `0x180007418`
- `0x1800079d4`
- `0x180007ddc`
- `0x180018b68`
- `0x18001d15d`
- `0x18003d040`

## import_xrefs

- `mscms!GetColorProfileElement` at `0x180007522`
- `mscms!GetColorProfileElement` at `0x1800075f6`
- `mscms!GetColorProfileElement` at `0x180007677`
- `mscms!GetColorProfileElement` at `0x180007739`
- `mscms!GetColorProfileElement` at `0x180007522`
- `mscms!GetColorProfileElement` at `0x1800075f6`
- `mscms!GetColorProfileElement` at `0x180007677`
- `mscms!GetColorProfileElement` at `0x180007739`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800074f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800075c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007651`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007710`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800074f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800075c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007651`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007710`

## pseudocode

```c
__int64 __fastcall ExtractNestedCurves(
        void *a1,
        TAGTYPE a2,
        unsigned int a3,
        unsigned __int8 a4,
        unsigned __int64 dwOffset,
        char a6,
        char a7,
        __int64 *a8)
{
  __int64 v8; // r13
  void *v9; // r12
  unsigned __int16 v10; // cx
  unsigned int v11; // ebx
  int v13; // edi
  unsigned __int8 i; // r14
  unsigned __int64 v15; // r15
  unsigned __int64 v16; // rbx
  int v17; // ecx
  HPROFILE v18; // r15
  TAGTYPE v19; // ebx
  unsigned __int16 v20; // cx
  unsigned __int64 v21; // r14
  int v22; // edx
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned int v25; // edx
  unsigned __int16 v26; // cx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned __int64 v29; // r14
  __int64 v30; // rax
  char *v31; // r8
  unsigned __int64 v32; // rcx
  DWORD pcbElement; // [rsp+30h] [rbp-99h] BYREF
  unsigned __int8 v35; // [rsp+34h] [rbp-95h]
  unsigned __int8 v36; // [rsp+35h] [rbp-94h]
  unsigned __int16 v37[2]; // [rsp+38h] [rbp-91h] BYREF
  WINBOOL pbReference; // [rsp+3Ch] [rbp-8Dh] BYREF
  TAGTYPE tag; // [rsp+40h] [rbp-89h]
  char *v40; // [rsp+48h] [rbp-81h]
  HPROFILE hProfile; // [rsp+50h] [rbp-79h]
  unsigned int v42; // [rsp+58h] [rbp-71h]
  char *v43; // [rsp+60h] [rbp-69h]
  __int64 *v44; // [rsp+68h] [rbp-61h]
  __int64 v45; // [rsp+70h] [rbp-59h]
  unsigned __int64 v46; // [rsp+78h] [rbp-51h]
  _OWORD v47[2]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-29h]
  __int64 pElement; // [rsp+A8h] [rbp-21h] BYREF
  __int128 v50; // [rsp+B0h] [rbp-19h] BYREF

  v8 = 0;
  hProfile = a1;
  v9 = 0;
  v36 = a4;
  v42 = a3;
  v45 = 2LL * (unsigned int)(1 << a6);
  tag = a2;
  v44 = a8;
  v46 = v45 * a4 + 2;
  v40 = (char *)malloc_0(2 * (1 << a6) * a4 + 2);
  v10 = v40 == 0 ? 8 : 0;
  v11 = v10;
  v37[0] = v10;
  if ( v10 )
    goto LABEL_52;
  v13 = 0;
  for ( i = 0; ; i = v35 + 1 )
  {
    v35 = i;
    if ( i >= v36 )
      break;
    v15 = v42;
    pElement = 0;
    pcbElement = 0;
    if ( dwOffset >= v42 )
      goto LABEL_42;
    pcbElement = 8;
    v16 = v42 - dwOffset;
    if ( v16 < 8 )
      goto LABEL_42;
    pbReference = 0;
    SetLastError(0);
    if ( !GetColorProfileElement(hProfile, tag, dwOffset, &pcbElement, &pElement, &pbReference) )
      goto LABEL_41;
    if ( pcbElement != 8 )
      goto LABEL_42;
    v43 = &v40[v45 * i];
    v17 = BYTE3(pElement) | ((BYTE2(pElement) | ((BYTE1(pElement) | ((unsigned __int8)pElement << 8)) << 8)) << 8);
    LOBYTE(pElement) = BYTE3(pElement);
    BYTE1(pElement) = BYTE1(v17);
    BYTE2(pElement) = BYTE2(v17);
    BYTE3(pElement) = HIBYTE(v17);
    if ( v17 != 1668641398 )
    {
      if ( v17 != 1885434465 )
        goto LABEL_42;
      pcbElement = 10;
      v48 = 0;
      memset(v47, 0, sizeof(v47));
      if ( v16 < 0xA )
        goto LABEL_42;
      pbReference = 0;
      SetLastError(0);
      v18 = hProfile;
      v19 = tag;
      if ( !GetColorProfileElement(hProfile, tag, dwOffset, &pcbElement, v47, &pbReference) )
        goto LABEL_41;
      if ( pcbElement != 10 )
        goto LABEL_42;
      v20 = _byteswap_ushort(WORD4(v47[0]));
      WORD4(v47[0]) = v20;
      if ( v20 > 4u )
        goto LABEL_42;
      pbReference = 0;
      LODWORD(v21) = 4 * *((_DWORD *)&unk_18003F008 + 8 * v20) + 12;
      pcbElement = v21;
      SetLastError(0);
      if ( !GetColorProfileElement(v18, v19, dwOffset, &pcbElement, v47, &pbReference) )
        goto LABEL_41;
      if ( pcbElement != (_DWORD)v21 )
        goto LABEL_42;
      WORD4(v47[0]) = _byteswap_ushort(WORD4(v47[0]));
      SwapLongOffset(v47, 12, (unsigned int)v21);
      if ( a7 == 8 )
      {
        v13 = v22 - 11;
        goto LABEL_19;
      }
      if ( v13 )
LABEL_19:
        v24 = 16;
      else
        v24 = (unsigned __int8)a7;
      LOBYTE(v23) = a6;
      v11 = Fill_ushort_ELUT_from_ParametricCurveTag(v47, v43, v23, v24);
      if ( v11 )
        goto LABEL_52;
      goto LABEL_40;
    }
    pcbElement = 12;
    v50 = 0;
    if ( v16 < 0xC )
      goto LABEL_42;
    pbReference = 0;
    SetLastError(0);
    if ( !GetColorProfileElement(hProfile, tag, dwOffset, &pcbElement, &v50, &pbReference) )
    {
LABEL_41:
      v11 = 2012;
      goto LABEL_52;
    }
    if ( pcbElement != 12 )
      goto LABEL_42;
    v25 = BYTE11(v50) | ((BYTE10(v50) | ((BYTE9(v50) | (BYTE8(v50) << 8)) << 8)) << 8);
    BYTE8(v50) = BYTE11(v50);
    BYTE9(v50) = BYTE1(v25);
    BYTE10(v50) = BYTE2(v25);
    BYTE11(v50) = HIBYTE(v25);
    if ( v25 >= 0x7FFFFFFF )
      goto LABEL_42;
    if ( 0xFFFFFFFF - 2 * (unsigned __int64)v25 <= 0xC )
      goto LABEL_42;
    v21 = 2 * v25 + 12;
    if ( v21 >= 0xFFFFFFFF - dwOffset || v21 + dwOffset > v15 )
      goto LABEL_42;
    v8 = (__int64)malloc_0((int)v21);
    v26 = v8 == 0 ? 8 : 0;
    v11 = v26;
    v37[0] = v26;
    if ( v26 )
      goto LABEL_52;
    pcbElement = v21;
    v11 = CMGetPartialProfileElement(hProfile, tag, dwOffset, &pcbElement, (PVOID)v8);
    if ( v11 )
      goto LABEL_52;
    if ( pcbElement != (_DWORD)v21 )
    {
LABEL_42:
      v11 = 2011;
      goto LABEL_52;
    }
    *(_DWORD *)(v8 + 8) = *(unsigned __int8 *)(v8 + 11)
                        | ((*(unsigned __int8 *)(v8 + 10)
                          | ((*(unsigned __int8 *)(v8 + 9) | (*(unsigned __int8 *)(v8 + 8) << 8)) << 8)) << 8);
    SwapShortOffset(v8, 12, (unsigned int)v21);
    if ( a7 == 8 )
    {
      v13 = 1;
    }
    else if ( !v13 )
    {
      v28 = (unsigned __int8)a7;
      goto LABEL_38;
    }
    v28 = 16;
LABEL_38:
    LOBYTE(v27) = a6;
    v11 = Fill_ushort_ELUT_from_CurveTag(v8, v43, v27, v28);
    if ( v11 )
      goto LABEL_52;
    v8 = DisposeIfPtr((void *)v8);
LABEL_40:
    dwOffset = ((unsigned int)v21 + dwOffset + 3) & 0xFFFFFFFFFFFFFFFCuLL;
  }
  if ( !v13 )
  {
    v31 = v40;
    goto LABEL_49;
  }
  v29 = v46 >> 1;
  v30 = SmartNewPtr((unsigned int)(v46 >> 1), v37);
  v11 = (__int16)v37[0];
  v9 = (void *)v30;
  if ( !v37[0] )
  {
    v31 = v40;
    v32 = 0;
    if ( v29 != 1 )
    {
      do
      {
        *(_BYTE *)(v30 + v32) = v31[2 * v32 + 1];
        ++v32;
      }
      while ( v32 < v29 - 1 );
    }
LABEL_49:
    if ( (unsigned __int8)a7 <= 8u )
    {
      *v44 = (__int64)v9;
      v9 = 0;
    }
    else
    {
      *v44 = (__int64)v31;
      v40 = 0;
    }
  }
LABEL_52:
  DisposeIfPtr((void *)v8);
  DisposeIfPtr(v40);
  DisposeIfPtr(v9);
  return v11;
}

```

## disassembly

```asm
0x180007418  mov     [rsp-8+arg_10], rbx
0x18000741d  push    rbp
0x18000741e  push    rsi
0x18000741f  push    rdi
0x180007420  push    r12
0x180007422  push    r13
0x180007424  push    r14
0x180007426  push    r15
0x180007428  lea     rbp, [rsp-7]
0x18000742d  sub     rsp, 0D0h
0x180007434  mov     rax, cs:__security_cookie
0x18000743b  xor     rax, rsp
0x18000743e  mov     [rbp+37h+var_40], rax
0x180007442  mov     r15, [rbp+37h+arg_38]
0x180007446  xor     r13d, r13d
0x180007449  mov     [rbp+37h+hProfile], rcx
0x18000744d  xor     r12d, r12d
0x180007450  mov     cl, [rbp+37h+arg_28]
0x180007453  mov     [rsp+100h+var_CB], r9b
0x180007458  lea     eax, [r13+1]
0x18000745c  mov     [rbp+37h+var_A8], r8d
0x180007460  shl     eax, cl
0x180007462  mov     ecx, eax
0x180007464  add     rcx, rcx
0x180007467  movzx   eax, r9b
0x18000746b  imul    rax, rcx
0x18000746f  mov     [rbp+37h+var_90], rcx
0x180007473  add     rax, 2
0x180007477  mov     [rsp+100h+tag], edx
0x18000747b  movsxd  rcx, eax; Size
0x18000747e  mov     [rbp+37h+var_98], r15
0x180007482  mov     [rbp+37h+var_88], rax
0x180007486  call    malloc_0
0x18000748b  mov     [rsp+100h+var_B8], rax
0x180007490  lea     r8d, [r13+8]
0x180007494  neg     rax
0x180007497  sbb     cx, cx
0x18000749a  not     cx
0x18000749d  and     cx, r8w
0x1800074a1  movzx   ebx, cx
0x1800074a4  mov     [rsp+100h+var_C8], bx
0x1800074a9  jnz     loc_180007948
0x1800074af  mov     rsi, [rbp+37h+dwOffset]
0x1800074b3  xor     edi, edi
0x1800074b5  xor     r14b, r14b
0x1800074b8  mov     [rsp+100h+var_CC], r14b
0x1800074bd  cmp     r14b, [rsp+100h+var_CB]
0x1800074c2  jnb     loc_1800078DF
0x1800074c8  mov     r15d, [rbp+37h+var_A8]
0x1800074cc  mov     [rbp+37h+var_58], r12
0x1800074d0  mov     [rsp+100h+pcbElement], r12d
0x1800074d5  cmp     rsi, r15
0x1800074d8  jnb     loc_1800078D8
0x1800074de  mov     ebx, r15d
0x1800074e1  mov     [rsp+100h+pcbElement], r8d
0x1800074e6  sub     rbx, rsi
0x1800074e9  cmp     rbx, r8
0x1800074ec  jb      loc_1800078D8
0x1800074f2  xor     ecx, ecx; dwErrCode
0x1800074f4  mov     [rsp+100h+var_C4], r12d
0x1800074f9  call    cs:__imp_SetLastError
0x1800074ff  mov     edx, [rsp+100h+tag]; tag
0x180007503  lea     rax, [rsp+100h+var_C4]
0x180007508  mov     rcx, [rbp+37h+hProfile]; hProfile
0x18000750c  lea     r9, [rsp+100h+pcbElement]; pcbElement
0x180007511  mov     [rsp+100h+pbReference], rax; pbReference
0x180007516  mov     r8d, esi; dwOffset
0x180007519  lea     rax, [rbp+37h+var_58]
0x18000751d  mov     [rsp+100h+pElement], rax; pElement
0x180007522  call    cs:__imp_GetColorProfileElement
0x180007528  test    eax, eax
0x18000752a  jz      loc_1800078D1
0x180007530  cmp     [rsp+100h+pcbElement], 8
0x180007535  jnz     loc_1800078D8
0x18000753b  movzx   ecx, byte ptr [rbp+37h+var_58]
0x18000753f  shl     ecx, 8
0x180007542  movzx   eax, r14b
0x180007546  imul    rax, [rbp+37h+var_90]
0x18000754b  add     rax, [rsp+100h+var_B8]
0x180007550  mov     [rbp+37h+var_A0], rax
0x180007554  movzx   eax, byte ptr [rbp+37h+var_58+1]
0x180007558  or      ecx, eax
0x18000755a  movzx   eax, byte ptr [rbp+37h+var_58+2]
0x18000755e  shl     ecx, 8
0x180007561  or      ecx, eax
0x180007563  movzx   eax, byte ptr [rbp+37h+var_58+3]
0x180007567  shl     ecx, 8
0x18000756a  or      ecx, eax
0x18000756c  mov     eax, ecx
0x18000756e  mov     byte ptr [rbp+37h+var_58], cl
0x180007571  shr     eax, 8
0x180007574  mov     byte ptr [rbp+37h+var_58+1], al
0x180007577  mov     eax, ecx
0x180007579  shr     eax, 10h
0x18000757c  mov     byte ptr [rbp+37h+var_58+2], al
0x18000757f  mov     eax, ecx
0x180007581  shr     eax, 18h
0x180007584  mov     byte ptr [rbp+37h+var_58+3], al
0x180007587  cmp     ecx, 63757276h
0x18000758d  jz      loc_1800076F0
0x180007593  cmp     ecx, 70617261h
0x180007599  jnz     loc_1800078D8
0x18000759f  xor     eax, eax
0x1800075a1  mov     [rsp+100h+pcbElement], 0Ah
0x1800075a9  mov     [rbp+37h+var_60], rax
0x1800075ad  xorps   xmm0, xmm0
0x1800075b0  movups  [rbp+37h+var_80], xmm0
0x1800075b4  movups  [rbp+37h+var_70], xmm0
0x1800075b8  cmp     rbx, 0Ah
0x1800075bc  jb      loc_1800078D8
0x1800075c2  xor     ecx, ecx; dwErrCode
0x1800075c4  mov     [rsp+100h+var_C4], eax
0x1800075c8  call    cs:__imp_SetLastError
0x1800075ce  mov     r15, [rbp+37h+hProfile]
0x1800075d2  lea     rax, [rsp+100h+var_C4]
0x1800075d7  mov     ebx, [rsp+100h+tag]
0x1800075db  lea     r9, [rsp+100h+pcbElement]; pcbElement
0x1800075e0  mov     [rsp+100h+pbReference], rax; pbReference
0x1800075e5  mov     r8d, esi; dwOffset
0x1800075e8  lea     rax, [rbp+37h+var_80]
0x1800075ec  mov     edx, ebx; tag
0x1800075ee  mov     rcx, r15; hProfile
0x1800075f1  mov     [rsp+100h+pElement], rax; pElement
0x1800075f6  call    cs:__imp_GetColorProfileElement
0x1800075fc  test    eax, eax
0x1800075fe  jz      loc_1800078D1
0x180007604  cmp     [rsp+100h+pcbElement], 0Ah
0x180007609  jnz     loc_1800078D8
0x18000760f  movzx   ecx, byte ptr [rbp+37h+var_80+8]
0x180007613  movzx   eax, byte ptr [rbp+37h+var_80+9]
0x180007617  shl     cx, 8
0x18000761b  or      cx, ax
0x18000761e  mov     word ptr [rbp+37h+var_80+8], cx
0x180007622  cmp     cx, 4
0x180007626  ja      loc_1800078D8
0x18000762c  movzx   eax, cx
0x18000762f  lea     rcx, unk_18003F008
0x180007636  shl     rax, 5
0x18000763a  mov     [rsp+100h+var_C4], r12d
0x18000763f  mov     eax, [rax+rcx]
0x180007642  xor     ecx, ecx; dwErrCode
0x180007644  lea     r14d, ds:0Ch[rax*4]
0x18000764c  mov     [rsp+100h+pcbElement], r14d
0x180007651  call    cs:__imp_SetLastError
0x180007657  lea     rax, [rsp+100h+var_C4]
0x18000765c  mov     r8d, esi; dwOffset
0x18000765f  mov     [rsp+100h+pbReference], rax; pbReference
0x180007664  lea     r9, [rsp+100h+pcbElement]; pcbElement
0x180007669  lea     rax, [rbp+37h+var_80]
0x18000766d  mov     edx, ebx; tag
0x18000766f  mov     rcx, r15; hProfile
0x180007672  mov     [rsp+100h+pElement], rax; pElement
0x180007677  call    cs:__imp_GetColorProfileElement
0x18000767d  test    eax, eax
0x18000767f  jz      loc_1800078D1
0x180007685  cmp     [rsp+100h+pcbElement], r14d
0x18000768a  jnz     loc_1800078D8
0x180007690  movzx   ecx, byte ptr [rbp+37h+var_80+8]
0x180007694  mov     r8d, r14d
0x180007697  movzx   eax, byte ptr [rbp+37h+var_80+9]
0x18000769b  mov     edx, 0Ch
0x1800076a0  shl     cx, 8
0x1800076a4  or      cx, ax
0x1800076a7  mov     word ptr [rbp+37h+var_80+8], cx
0x1800076ab  lea     rcx, [rbp+37h+var_80]
0x1800076af  call    SwapLongOffset
0x1800076b4  cmp     [rbp+37h+arg_30], 8
0x1800076b8  jnz     short loc_1800076BF
0x1800076ba  lea     edi, [rdx-0Bh]
0x1800076bd  jmp     short loc_1800076C3
0x1800076bf  test    edi, edi
0x1800076c1  jz      short loc_1800076CB
0x1800076c3  mov     r9d, 10h
0x1800076c9  jmp     short loc_1800076D0
0x1800076cb  movzx   r9d, [rbp+37h+arg_30]
0x1800076d0  mov     r8b, [rbp+37h+arg_28]
0x1800076d4  lea     rcx, [rbp+37h+var_80]
0x1800076d8  mov     rdx, [rbp+37h+var_A0]
0x1800076dc  call    Fill_ushort_ELUT_from_ParametricCurveTag
0x1800076e1  mov     ebx, eax
0x1800076e3  test    eax, eax
0x1800076e5  jz      loc_1800078B0
0x1800076eb  jmp     loc_180007948
0x1800076f0  mov     [rsp+100h+pcbElement], 0Ch
0x1800076f8  xorps   xmm0, xmm0
0x1800076fb  movups  [rbp+37h+var_50], xmm0
0x1800076ff  cmp     rbx, 0Ch
0x180007703  jb      loc_1800078D8
0x180007709  xor     ecx, ecx; dwErrCode
0x18000770b  mov     [rsp+100h+var_C4], r12d
0x180007710  call    cs:__imp_SetLastError
0x180007716  mov     edx, [rsp+100h+tag]; tag
0x18000771a  lea     rax, [rsp+100h+var_C4]
0x18000771f  mov     rcx, [rbp+37h+hProfile]; hProfile
0x180007723  lea     r9, [rsp+100h+pcbElement]; pcbElement
0x180007728  mov     [rsp+100h+pbReference], rax; pbReference
0x18000772d  mov     r8d, esi; dwOffset
0x180007730  lea     rax, [rbp+37h+var_50]
0x180007734  mov     [rsp+100h+pElement], rax; pElement
0x180007739  call    cs:__imp_GetColorProfileElement
0x18000773f  test    eax, eax
0x180007741  jz      loc_1800078D1
0x180007747  cmp     [rsp+100h+pcbElement], 0Ch
0x18000774c  jnz     loc_1800078D8
0x180007752  movzx   eax, byte ptr [rbp+37h+var_50+9]
0x180007756  movzx   edx, byte ptr [rbp+37h+var_50+8]
0x18000775a  shl     edx, 8
0x18000775d  or      edx, eax
0x18000775f  movzx   eax, byte ptr [rbp+37h+var_50+0Ah]
0x180007763  shl     edx, 8
0x180007766  or      edx, eax
0x180007768  movzx   eax, byte ptr [rbp+37h+var_50+0Bh]
0x18000776c  shl     edx, 8
0x18000776f  or      edx, eax
0x180007771  mov     eax, edx
0x180007773  mov     byte ptr [rbp+37h+var_50+8], dl
0x180007776  shr     eax, 8
0x180007779  mov     byte ptr [rbp+37h+var_50+9], al
0x18000777c  mov     eax, edx
0x18000777e  shr     eax, 10h
0x180007781  mov     byte ptr [rbp+37h+var_50+0Ah], al
0x180007784  mov     eax, edx
0x180007786  shr     eax, 18h
0x180007789  mov     byte ptr [rbp+37h+var_50+0Bh], al
0x18000778c  cmp     edx, 7FFFFFFFh
0x180007792  jnb     loc_1800078D8
0x180007798  mov     ecx, edx
0x18000779a  mov     r8d, 0FFFFFFFFh
0x1800077a0  add     rcx, rcx
0x1800077a3  mov     eax, r8d
0x1800077a6  sub     rax, rcx
0x1800077a9  cmp     rax, 0Ch
0x1800077ad  jbe     loc_1800078D8
0x1800077b3  lea     r14d, ds:0Ch[rdx*2]
0x1800077bb  mov     eax, r8d
0x1800077be  mov     ecx, r14d
0x1800077c1  sub     rax, rsi
0x1800077c4  cmp     rcx, rax
0x1800077c7  jnb     loc_1800078D8
0x1800077cd  lea     rax, [r14+rsi]
0x1800077d1  cmp     rax, r15
0x1800077d4  ja      loc_1800078D8
0x1800077da  movsxd  rcx, r14d; Size
0x1800077dd  call    malloc_0
0x1800077e2  mov     r13, rax
0x1800077e5  mov     r15d, 8
0x1800077eb  neg     rax
0x1800077ee  sbb     cx, cx
0x1800077f1  not     cx
0x1800077f4  and     cx, r15w
0x1800077f8  movzx   ebx, cx
0x1800077fb  mov     [rsp+100h+var_C8], bx
0x180007800  jnz     loc_180007948
0x180007806  mov     edx, [rsp+100h+tag]; tag
0x18000780a  lea     r9, [rsp+100h+pcbElement]; pcbElement
0x18000780f  mov     rcx, [rbp+37h+hProfile]; hProfile
0x180007813  mov     r8d, esi; dwOffset
0x180007816  mov     [rsp+100h+pcbElement], r14d
0x18000781b  mov     [rsp+100h+pElement], r13; PVOID
0x180007820  call    CMGetPartialProfileElement
0x180007825  mov     ebx, eax
0x180007827  test    eax, eax
0x180007829  jnz     loc_180007948
0x18000782f  cmp     [rsp+100h+pcbElement], r14d
0x180007834  jnz     loc_1800078D8
0x18000783a  movzx   ecx, byte ptr [r13+8]
0x18000783f  lea     edx, [rbx+0Ch]
0x180007842  movzx   eax, byte ptr [r13+9]
0x180007847  mov     r8d, r14d
0x18000784a  shl     ecx, 8
0x18000784d  or      ecx, eax
0x18000784f  movzx   eax, byte ptr [r13+0Ah]
0x180007854  shl     ecx, 8
0x180007857  or      ecx, eax
0x180007859  movzx   eax, byte ptr [r13+0Bh]
0x18000785e  shl     ecx, 8
0x180007861  or      ecx, eax
0x180007863  mov     [r13+8], ecx
0x180007867  mov     rcx, r13
0x18000786a  call    SwapShortOffset
0x18000786f  cmp     [rbp+37h+arg_30], r15b
0x180007873  jnz     short loc_18000787A
0x180007875  lea     edi, [rbx+1]
0x180007878  jmp     short loc_18000787E
0x18000787a  test    edi, edi
0x18000787c  jz      short loc_180007886
0x18000787e  mov     r9d, 10h
0x180007884  jmp     short loc_18000788B
0x180007886  movzx   r9d, [rbp+37h+arg_30]
0x18000788b  mov     r8b, [rbp+37h+arg_28]
0x18000788f  mov     rcx, r13
0x180007892  mov     rdx, [rbp+37h+var_A0]
0x180007896  call    Fill_ushort_ELUT_from_CurveTag
0x18000789b  mov     ebx, eax
0x18000789d  test    eax, eax
0x18000789f  jnz     loc_180007948
0x1800078a5  mov     rcx, r13
0x1800078a8  call    DisposeIfPtr
0x1800078ad  mov     r13, rax
0x1800078b0  mov     ecx, r14d
  ... truncated ...
```

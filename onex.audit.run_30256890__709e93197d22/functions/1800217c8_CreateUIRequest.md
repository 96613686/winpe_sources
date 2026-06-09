# CreateUIRequest

- ea: `0x1800217c8`
- end: `0x180021b64`
- name: `CreateUIRequest`
- size: `924`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180022c30`
- `0x180025bc4`
- `0x180027494`

## callees

- `0x180005440`
- `0x180007f60`
- `0x1800106c8`
- `0x18001b864`
- `0x1800214f0`
- `0x1800217c8`
- `0x18002f705`

## import_xrefs

- `MobileNetworking!GetSystemTimeAsUlongLong` at `0x1800219a2`
- `MobileNetworking!GetSystemTimeAsUlongLong` at `0x1800219a2`
- `MobileNetworking!AllocateMemory` at `0x180021915`
- `MobileNetworking!AllocateMemory` at `0x180021915`
- `MobileNetworking!FreeMemory` at `0x180021b1e`
- `MobileNetworking!FreeMemory` at `0x180021b1e`

## string_xrefs

- `0x180021902`: `CreateUIRequest`
- `0x180021b13`: `CreateUIRequest`

## pseudocode

```c
__int64 __fastcall CreateUIRequest(__int64 a1, unsigned int a2, unsigned int **a3)
{
  __int64 v3; // r8
  unsigned int v5; // ecx
  unsigned int v6; // r13d
  void *v7; // rdx
  __int64 v8; // r14
  __int64 v9; // rax
  void *v10; // rdx
  __int64 v11; // rax
  unsigned int v12; // r12d
  unsigned int v13; // esi
  unsigned int v14; // edx
  unsigned int v15; // ebx
  unsigned int v16; // ecx
  unsigned int v17; // r15d
  unsigned int v18; // edi
  unsigned int v19; // eax
  _DWORD *v20; // rdx
  unsigned int *v21; // rbx
  unsigned int *v22; // r8
  void *v23; // rdx
  void *v24; // rdx
  void *v25; // rdx
  unsigned int v27; // [rsp+30h] [rbp-38h]
  unsigned int *v28; // [rsp+38h] [rbp-30h] BYREF
  _DWORD *v29; // [rsp+40h] [rbp-28h]
  void *Src; // [rsp+48h] [rbp-20h]
  void *v31; // [rsp+50h] [rbp-18h]
  void *v32; // [rsp+58h] [rbp-10h]
  unsigned int Size; // [rsp+B0h] [rbp+48h]
  __int64 v36; // [rsp+C8h] [rbp+60h] BYREF

  v3 = a1 + 2496;
  LODWORD(v36) = *(_DWORD *)(a1 + 20);
  v28 = 0;
  v5 = 0;
  v29 = (_DWORD *)v3;
  Size = 0;
  v6 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 45, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids);
    v5 = 0;
    v3 = a1 + 2496;
  }
  v7 = *(void **)(a1 + 2856);
  v8 = -1;
  Src = v7;
  if ( v7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v7 + v9) );
    v6 = 2 * v9 + 2;
  }
  v10 = *(void **)(a1 + 2864);
  v31 = v10;
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v5 = 2 * v11 + 2;
    Size = v5;
  }
  v12 = v6 + 7;
  if ( v6 + 7 < v6 || (v13 = 56, v14 = (v12 & 0xFFFFFFF8) + 56, v14 < 0x38) )
  {
    v15 = 534;
    goto LABEL_46;
  }
  if ( v5 + 7 < v5 || (v16 = ((v5 + 7) & 0xFFFFFFF8) + v14, v16 < v14) )
  {
    v15 = 534;
    goto LABEL_46;
  }
  v27 = *(_DWORD *)(v3 + 64);
  v17 = v27 + 7;
  if ( v27 + 7 < v27 || (v18 = v16 + (v17 & 0xFFFFFFF8), v18 < v16) )
  {
    v15 = 534;
    goto LABEL_46;
  }
  v32 = *(void **)(v3 + 72);
  v19 = AllocateMemory(v18, &v28, "CreateUIRequest", 818);
  v15 = v19;
  if ( v19 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        46,
        WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids,
        (unsigned int)v36,
        v19);
    goto LABEL_46;
  }
  v20 = v29;
  *v28 = v18;
  v28[1] = a2;
  v28[2] = *(_DWORD *)(*(_QWORD *)v20 + 2828LL);
  v28[3] ^= (v28[3] ^ (8 * v20[43])) & 8;
  v21 = v28;
  *((_QWORD *)v21 + 3) = GetSystemTimeAsUlongLong();
  v22 = v28;
  if ( !v28 )
  {
    v15 = 87;
    goto LABEL_46;
  }
  if ( v28 + 14 >= v28 )
    v8 = (__int64)(v28 + 14);
  v15 = v28 + 14 < v28 ? 0x216 : 0;
  v36 = v8;
  if ( v28 + 14 >= v28 )
  {
    v23 = Src;
    if ( Src && v6 )
    {
      v28[3] |= 1u;
      v28[8] = v6;
      v28[9] = 56;
      memcpy_0((void *)v8, v23, v6);
      v15 = AddAlignedSizeToPointer(v6, v8, &v36);
      if ( v15 )
        goto LABEL_46;
      v22 = v28;
      v8 = v36;
      v13 = (v12 & 0xFFFFFFF8) + 56;
    }
    v24 = v31;
    if ( v31 && Size )
    {
      v22[3] |= 2u;
      v28[10] = Size;
      v28[11] = v13;
      memcpy_0((void *)v8, v24, Size);
      v15 = AddAlignedSizeToPointer(Size, v8, &v36);
      if ( v15 )
        goto LABEL_46;
      if ( v13 + ((Size + 7) & 0xFFFFFFF8) < v13 )
        goto LABEL_44;
      v22 = v28;
      v13 += (Size + 7) & 0xFFFFFFF8;
      v8 = v36;
    }
    v25 = v32;
    if ( !v32 || !v27 )
      goto LABEL_43;
    v22[3] |= 4u;
    v28[12] = v27;
    v28[13] = v13;
    memcpy_0((void *)v8, v25, v27);
    v15 = AddAlignedSizeToPointer(v27, v8, &v36);
    if ( v15 )
      goto LABEL_46;
    if ( v13 + (v17 & 0xFFFFFFF8) >= v13 )
    {
      v22 = v28;
LABEL_43:
      *a3 = v22;
      goto LABEL_46;
    }
LABEL_44:
    v15 = 534;
  }
LABEL_46:
  EapSetUIContextData(v29, 0, 0);
  if ( v15 )
    FreeMemory(&v28, "CreateUIRequest", 891);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 47, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x1800217c8  mov     [rsp-40h+arg_10], r8
0x1800217cd  mov     [rsp-40h+arg_8], edx
0x1800217d1  push    rbp
0x1800217d2  push    rbx
0x1800217d3  push    rsi
0x1800217d4  push    rdi
0x1800217d5  push    r12
0x1800217d7  push    r13
0x1800217d9  push    r14
0x1800217db  push    r15
0x1800217dd  mov     rbp, rsp
0x1800217e0  sub     rsp, 68h
0x1800217e4  mov     eax, [rcx+14h]
0x1800217e7  lea     r8, [rcx+9C0h]
0x1800217ee  xor     edi, edi
0x1800217f0  mov     dword ptr [rbp+arg_18], eax
0x1800217f3  mov     rbx, rcx
0x1800217f6  mov     [rbp+var_30], rdi
0x1800217fa  mov     ecx, edi
0x1800217fc  mov     [rbp+var_28], r8
0x180021800  mov     dword ptr [rbp+Size], ecx
0x180021803  mov     r13d, edi
0x180021806  mov     rax, cs:WPP_GLOBAL_Control
0x18002180d  lea     r15, WPP_GLOBAL_Control
0x180021814  cmp     rax, r15
0x180021817  jz      short loc_18002183E
0x180021819  test    dword ptr [rax+44h], 800h
0x180021820  jz      short loc_18002183E
0x180021822  mov     rcx, [rax+38h]
0x180021826  lea     edx, [rdi+2Dh]
0x180021829  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x180021830  call    WPP_SF_
0x180021835  mov     ecx, edi
0x180021837  lea     r8, [rbx+9C0h]
0x18002183e  mov     rdx, [rbx+0B28h]
0x180021845  or      r14, 0FFFFFFFFFFFFFFFFh
0x180021849  mov     [rbp+Src], rdx
0x18002184d  test    rdx, rdx
0x180021850  jz      short loc_180021866
0x180021852  mov     rax, r14
0x180021855  inc     rax
0x180021858  cmp     [rdx+rax*2], di
0x18002185c  jnz     short loc_180021855
0x18002185e  lea     r13d, ds:2[rax*2]
0x180021866  mov     rdx, [rbx+0B30h]
0x18002186d  mov     [rbp+var_18], rdx
0x180021871  test    rdx, rdx
0x180021874  jz      short loc_18002188C
0x180021876  mov     rax, r14
0x180021879  inc     rax
0x18002187c  cmp     [rdx+rax*2], di
0x180021880  jnz     short loc_180021879
0x180021882  lea     ecx, ds:2[rax*2]
0x180021889  mov     dword ptr [rbp+Size], ecx
0x18002188c  lea     r12d, [r13+7]
0x180021890  cmp     r12d, r13d
0x180021893  jb      short loc_1800218AD
0x180021895  mov     edx, r12d
0x180021898  mov     r9d, 0FFFFFFF8h
0x18002189e  and     edx, r9d
0x1800218a1  mov     esi, 38h ; '8'
0x1800218a6  add     edx, 38h ; '8'
0x1800218a9  cmp     edx, esi
0x1800218ab  jnb     short loc_1800218B9
0x1800218ad  mov     edi, 216h
0x1800218b2  mov     ebx, edi
0x1800218b4  jmp     loc_180021AFB
0x1800218b9  lea     eax, [rcx+7]
0x1800218bc  cmp     eax, ecx
0x1800218be  jb      short loc_1800218CA
0x1800218c0  and     eax, r9d
0x1800218c3  lea     ecx, [rax+rdx]
0x1800218c6  cmp     ecx, edx
0x1800218c8  jnb     short loc_1800218D4
0x1800218ca  mov     ebx, 216h
0x1800218cf  jmp     loc_180021AFB
0x1800218d4  mov     eax, [r8+40h]
0x1800218d8  mov     dword ptr [rbp+var_38], eax
0x1800218db  lea     r15d, [rax+7]
0x1800218df  cmp     r15d, eax
0x1800218e2  jb      short loc_1800218F0
0x1800218e4  mov     edi, r15d
0x1800218e7  and     edi, r9d
0x1800218ea  add     edi, ecx
0x1800218ec  cmp     edi, ecx
0x1800218ee  jnb     short loc_1800218FA
0x1800218f0  mov     ebx, 216h
0x1800218f5  jmp     loc_180021AF4
0x1800218fa  mov     rax, [r8+48h]
0x1800218fe  lea     rdx, [rbp+var_30]
0x180021902  lea     r8, aCreateuireques; "CreateUIRequest"
0x180021909  mov     [rbp+var_10], rax
0x18002190d  mov     r9d, 332h
0x180021913  mov     ecx, edi
0x180021915  call    cs:__imp_AllocateMemory
0x18002191b  mov     ebx, eax
0x18002191d  test    eax, eax
0x18002191f  jz      short loc_180021964
0x180021921  mov     rcx, cs:WPP_GLOBAL_Control
0x180021928  lea     r15, WPP_GLOBAL_Control
0x18002192f  cmp     rcx, r15
0x180021932  jz      loc_180021AFB
0x180021938  test    byte ptr [rcx+44h], 1
0x18002193c  jz      loc_180021AFB
0x180021942  mov     r9d, dword ptr [rbp+arg_18]
0x180021946  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x18002194d  mov     rcx, [rcx+38h]
0x180021951  mov     edx, 2Eh ; '.'
0x180021956  mov     [rsp+68h+var_48], eax
0x18002195a  call    WPP_SF_dd
0x18002195f  jmp     loc_180021AFB
0x180021964  mov     rax, [rbp+var_30]
0x180021968  mov     rdx, [rbp+var_28]
0x18002196c  mov     ecx, [rbp+arg_8]
0x18002196f  mov     [rax], edi
0x180021971  mov     rax, [rbp+var_30]
0x180021975  mov     [rax+4], ecx
0x180021978  mov     rax, [rdx]
0x18002197b  mov     ecx, [rax+0B0Ch]
0x180021981  mov     rax, [rbp+var_30]
0x180021985  mov     [rax+8], ecx
0x180021988  mov     rcx, [rbp+var_30]
0x18002198c  mov     eax, [rdx+0ACh]
0x180021992  shl     eax, 3
0x180021995  xor     eax, [rcx+0Ch]
0x180021998  and     eax, 8
0x18002199b  xor     [rcx+0Ch], eax
0x18002199e  mov     rbx, [rbp+var_30]
0x1800219a2  call    cs:__imp_GetSystemTimeAsUlongLong
0x1800219a8  mov     [rbx+18h], rax
0x1800219ac  mov     r8, [rbp+var_30]
0x1800219b0  test    r8, r8
0x1800219b3  jz      loc_180021AEF
0x1800219b9  lea     rax, [r8+38h]
0x1800219bd  mov     edi, 216h
0x1800219c2  cmp     rax, r8
0x1800219c5  cmovnb  r14, rax
0x1800219c9  sbb     ebx, ebx
0x1800219cb  and     ebx, edi
0x1800219cd  mov     [rbp+arg_18], r14
0x1800219d1  cmp     rax, r8
0x1800219d4  jb      loc_180021AF4
0x1800219da  mov     rdx, [rbp+Src]; Src
0x1800219de  test    rdx, rdx
0x1800219e1  jz      short loc_180021A2F
0x1800219e3  test    r13d, r13d
0x1800219e6  jz      short loc_180021A2F
0x1800219e8  or      dword ptr [r8+0Ch], 1
0x1800219ed  mov     rcx, r14; void *
0x1800219f0  mov     rax, [rbp+var_30]
0x1800219f4  mov     r8d, r13d; Size
0x1800219f7  mov     [rax+20h], r13d
0x1800219fb  mov     rax, [rbp+var_30]
0x1800219ff  mov     [rax+24h], esi
0x180021a02  call    memcpy_0
0x180021a07  lea     r8, [rbp+arg_18]
0x180021a0b  mov     rdx, r14
0x180021a0e  mov     ecx, r13d
0x180021a11  call    AddAlignedSizeToPointer
0x180021a16  mov     ebx, eax
0x180021a18  test    eax, eax
0x180021a1a  jnz     loc_180021AF4
0x180021a20  mov     r8, [rbp+var_30]
0x180021a24  and     r12d, 0FFFFFFF8h
0x180021a28  mov     r14, [rbp+arg_18]
0x180021a2c  add     esi, r12d
0x180021a2f  mov     rdx, [rbp+var_18]; Src
0x180021a33  test    rdx, rdx
0x180021a36  jz      short loc_180021A8C
0x180021a38  mov     r13d, dword ptr [rbp+Size]
0x180021a3c  test    r13d, r13d
0x180021a3f  jz      short loc_180021A8C
0x180021a41  or      dword ptr [r8+0Ch], 2
0x180021a46  mov     rcx, r14; void *
0x180021a49  mov     rax, [rbp+var_30]
0x180021a4d  mov     r8d, r13d; Size
0x180021a50  mov     [rax+28h], r13d
0x180021a54  mov     rax, [rbp+var_30]
0x180021a58  mov     [rax+2Ch], esi
0x180021a5b  call    memcpy_0
0x180021a60  lea     r8, [rbp+arg_18]
0x180021a64  mov     rdx, r14
0x180021a67  mov     ecx, r13d
0x180021a6a  call    AddAlignedSizeToPointer
0x180021a6f  mov     ebx, eax
0x180021a71  test    eax, eax
0x180021a73  jnz     short loc_180021AF4
0x180021a75  lea     ecx, [r13+7]
0x180021a79  and     ecx, 0FFFFFFF8h
0x180021a7c  add     ecx, esi
0x180021a7e  cmp     ecx, esi
0x180021a80  jb      short loc_180021AEB
0x180021a82  mov     r8, [rbp+var_30]
0x180021a86  mov     esi, ecx
0x180021a88  mov     r14, [rbp+arg_18]
0x180021a8c  mov     rdx, [rbp+var_10]; Src
0x180021a90  test    rdx, rdx
0x180021a93  jz      short loc_180021AE2
0x180021a95  mov     r13d, dword ptr [rbp+var_38]
0x180021a99  test    r13d, r13d
0x180021a9c  jz      short loc_180021AE2
0x180021a9e  or      dword ptr [r8+0Ch], 4
0x180021aa3  mov     rcx, r14; void *
0x180021aa6  mov     rax, [rbp+var_30]
0x180021aaa  mov     r8d, r13d; Size
0x180021aad  mov     [rax+30h], r13d
0x180021ab1  mov     rax, [rbp+var_30]
0x180021ab5  mov     [rax+34h], esi
0x180021ab8  call    memcpy_0
0x180021abd  lea     r8, [rbp+arg_18]
0x180021ac1  mov     rdx, r14
0x180021ac4  mov     ecx, r13d
0x180021ac7  call    AddAlignedSizeToPointer
0x180021acc  mov     ebx, eax
0x180021ace  test    eax, eax
0x180021ad0  jnz     short loc_180021AF4
0x180021ad2  and     r15d, 0FFFFFFF8h
0x180021ad6  add     r15d, esi
0x180021ad9  cmp     r15d, esi
0x180021adc  jb      short loc_180021AEB
0x180021ade  mov     r8, [rbp+var_30]
0x180021ae2  mov     rax, [rbp+arg_10]
0x180021ae6  mov     [rax], r8
0x180021ae9  jmp     short loc_180021AF4
0x180021aeb  mov     ebx, edi
0x180021aed  jmp     short loc_180021AF4
0x180021aef  mov     ebx, 57h ; 'W'
0x180021af4  lea     r15, WPP_GLOBAL_Control
0x180021afb  mov     rcx, [rbp+var_28]
0x180021aff  xor     r8d, r8d
0x180021b02  xor     edx, edx
0x180021b04  call    EapSetUIContextData
0x180021b09  test    ebx, ebx
0x180021b0b  jz      short loc_180021B24
0x180021b0d  mov     r8d, 37Bh
0x180021b13  lea     rdx, aCreateuireques; "CreateUIRequest"
0x180021b1a  lea     rcx, [rbp+var_30]
0x180021b1e  call    cs:__imp_FreeMemory
0x180021b24  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b2b  cmp     rcx, r15
0x180021b2e  jz      short loc_180021B51
0x180021b30  test    dword ptr [rcx+44h], 800h
0x180021b37  jz      short loc_180021B51
0x180021b39  mov     rcx, [rcx+38h]
0x180021b3d  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x180021b44  mov     edx, 2Fh ; '/'
0x180021b49  mov     r9d, ebx
0x180021b4c  call    WPP_SF_D
0x180021b51  mov     eax, ebx
0x180021b53  add     rsp, 68h
0x180021b57  pop     r15
0x180021b59  pop     r14
0x180021b5b  pop     r13
0x180021b5d  pop     r12
0x180021b5f  pop     rdi
0x180021b60  pop     rsi
0x180021b61  pop     rbx
0x180021b62  pop     rbp
0x180021b63  retn
```

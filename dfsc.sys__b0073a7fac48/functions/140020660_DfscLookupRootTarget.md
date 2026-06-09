# DfscLookupRootTarget

- ea: `0x140020660`
- end: `0x140020cfe`
- name: `DfscLookupRootTarget`
- size: `1694`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140020e10`

## callees

- `0x140002340`
- `0x1400025f4`
- `0x1400026a4`
- `0x140002fcc`
- `0x140006380`
- `0x14001d110`
- `0x14001f040`
- `0x140020660`
- `0x140020d10`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140020a79`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140020b16`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140020a79`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140020b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400208f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400209bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400208f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400209bf`

## pseudocode

```c
__int64 __fastcall DfscLookupRootTarget(__int64 a1)
{
  UNICODE_STRING *v2; // r9
  unsigned __int16 v3; // cx
  unsigned __int16 v4; // dx
  WCHAR v5; // r8
  __int16 v6; // r8
  PVOID *v7; // rax
  PVOID *v8; // rdi
  __int128 *v9; // rcx
  __int64 v10; // r14
  __int64 v11; // rdx
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  PVOID *v20; // r15
  int CacheReferral; // r8d
  void *v22; // r12
  unsigned __int16 v23; // dx
  unsigned __int16 v24; // cx
  __int16 v25; // r8
  __int16 v26; // r8
  unsigned int v27; // esi
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  void *v31; // rcx
  PVOID *v32; // rcx
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  PDEVICE_OBJECT v41; // rcx
  int v42; // edx
  __int64 v43; // rax
  PDEVICE_OBJECT v44; // rcx
  __int64 v45; // rdx
  UNICODE_STRING String2; // [rsp+30h] [rbp-D0h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-C0h] BYREF
  PVOID v48[34]; // [rsp+50h] [rbp-B0h] BYREF
  int v49; // [rsp+190h] [rbp+90h] BYREF

  v49 = 0;
  memset(v48, 0, 0x108u);
  if ( !*(_WORD *)(a1 + 208) )
  {
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0 )
    {
      return 6;
    }
    v42 = 39;
    v43 = *(_QWORD *)(a1 + 280) + 96LL;
    goto LABEL_46;
  }
  v2 = *(UNICODE_STRING **)(a1 + 280);
  v3 = *(_WORD *)(a1 + 176) >> 1;
  String1 = 0;
  v4 = v2[5].Length >> 1;
  for ( String2 = 0; v4; --v4 )
  {
    v5 = v2[5].Buffer[v4 - 1];
    if ( v5 != 92 && v5 )
      break;
  }
  if ( v3 )
  {
    while ( 1 )
    {
      v6 = *(_WORD *)(*(_QWORD *)(a1 + 184) + 2LL * v3 - 2);
      if ( v6 != 92 )
      {
        if ( v6 )
          break;
      }
      if ( !--v3 )
        goto LABEL_55;
    }
    if ( v3 == v4 )
    {
      if ( v4 )
      {
        String1 = v2[5];
        String1.Length = 2 * v4;
        String2 = *(UNICODE_STRING *)(a1 + 176);
        String2.Length = 2 * v3;
        if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
          goto LABEL_43;
      }
    }
LABEL_9:
    v7 = v48;
    v8 = (PVOID *)(a1 + 8);
    v9 = (__int128 *)(a1 + 8);
    v10 = 2;
    v11 = 2;
    do
    {
      v7 += 16;
      v12 = *v9;
      v13 = v9[1];
      v9 += 8;
      *((_OWORD *)v7 - 8) = v12;
      v14 = *(v9 - 6);
      *((_OWORD *)v7 - 7) = v13;
      v15 = *(v9 - 5);
      *((_OWORD *)v7 - 6) = v14;
      v16 = *(v9 - 4);
      *((_OWORD *)v7 - 5) = v15;
      v17 = *(v9 - 3);
      *((_OWORD *)v7 - 4) = v16;
      v18 = *(v9 - 2);
      *((_OWORD *)v7 - 3) = v17;
      v19 = *(v9 - 1);
      *((_OWORD *)v7 - 2) = v18;
      *((_OWORD *)v7 - 1) = v19;
      --v11;
    }
    while ( v11 );
    *v7 = *(PVOID *)v9;
    memset((void *)(a1 + 16), 0, 0x60u);
    memset((void *)(a1 + 112), 0, 0x60u);
    *(_OWORD *)(a1 + 208) = 0;
    *(_WORD *)(a1 + 226) = 0;
    v20 = (PVOID *)(a1 + 272);
    CacheReferral = DfscRewritePath(
                      a1,
                      (unsigned __int16 *)(*(_QWORD *)(a1 + 280) + 96LL),
                      (const UNICODE_STRING *)&v48[25],
                      1);
    v22 = *(void **)(a1 + 272);
    *(_QWORD *)(a1 + 272) = 0;
    if ( CacheReferral < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0 )
      {
        goto LABEL_34;
      }
      v30 = 47;
    }
    else
    {
      CacheReferral = DfscGetCacheReferral(a1 + 8, a1 + 272, &v49);
      if ( CacheReferral )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0 )
        {
          goto LABEL_34;
        }
        v30 = 46;
      }
      else
      {
        CacheReferral = v49;
        switch ( v49 )
        {
          case 2:
            v23 = LOWORD(v48[25]) >> 1;
            v24 = *(_WORD *)(a1 + 208) >> 1;
            String2 = 0;
            for ( String1 = 0; v24; --v24 )
            {
              v25 = *(_WORD *)(*(_QWORD *)(a1 + 216) + 2LL * v24 - 2);
              if ( v25 != 92 && v25 )
                break;
            }
            if ( v23 )
            {
              while ( 1 )
              {
                v26 = *((_WORD *)v48[26] + v23 - 1);
                if ( v26 != 92 )
                {
                  if ( v26 )
                    break;
                }
                if ( !--v23 )
                  goto LABEL_59;
              }
              if ( v23 == v24 )
              {
                if ( v24 )
                {
                  String2 = *(UNICODE_STRING *)(a1 + 208);
                  String2.Length = 2 * v24;
                  String1 = *(UNICODE_STRING *)&v48[25];
                  String1.Length = 2 * v23;
                  if ( !RtlCompareUnicodeString(&String2, &String1, 1u) )
                    goto LABEL_50;
                }
              }
            }
            else
            {
LABEL_59:
              if ( !v24 )
              {
LABEL_50:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
                {
                  WPP_SF_qZ(
                    WPP_GLOBAL_Control->AttachedDevice,
                    41,
                    (unsigned int)WPP_05cba1b763293f8d98259e004f8588c9_Traceguids,
                    a1,
                    a1 + 96);
                }
                goto LABEL_34;
              }
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                42,
                WPP_05cba1b763293f8d98259e004f8588c9_Traceguids,
                a1,
                *v20);
            }
            v27 = 1;
            if ( v48[12] )
              ExFreePoolWithTag(v48[12], 0);
            memset(&v48[1], 0, 208);
            WORD1(v48[27]) = 0;
            if ( v22 )
              DfscReferralRelease(v22);
            ++*(_WORD *)(a1 + 290);
            return v27;
          case 0:
            v44 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0 )
            {
              goto LABEL_34;
            }
            v45 = 44;
LABEL_76:
            WPP_SF_q(v44->AttachedDevice, v45, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1);
LABEL_34:
            v31 = *(void **)(a1 + 104);
            v27 = 6;
            if ( v31 )
              ExFreePoolWithTag(v31, 0);
            v32 = v48;
            do
            {
              v8 += 16;
              v33 = *(_OWORD *)v32;
              v34 = *((_OWORD *)v32 + 1);
              v32 += 16;
              *((_OWORD *)v8 - 8) = v33;
              v35 = *((_OWORD *)v32 - 6);
              *((_OWORD *)v8 - 7) = v34;
              v36 = *((_OWORD *)v32 - 5);
              *((_OWORD *)v8 - 6) = v35;
              v37 = *((_OWORD *)v32 - 4);
              *((_OWORD *)v8 - 5) = v36;
              v38 = *((_OWORD *)v32 - 3);
              *((_OWORD *)v8 - 4) = v37;
              v39 = *((_OWORD *)v32 - 2);
              *((_OWORD *)v8 - 3) = v38;
              v40 = *((_OWORD *)v32 - 1);
              *((_OWORD *)v8 - 2) = v39;
              *((_OWORD *)v8 - 1) = v40;
              --v10;
            }
            while ( v10 );
            *v8 = *v32;
            if ( *v20 )
              DfscReferralRelease(*v20);
            *v20 = v22;
            return v27;
          case 1:
            v44 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0 )
            {
              goto LABEL_34;
            }
            v45 = 43;
            goto LABEL_76;
        }
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0 )
        {
          goto LABEL_34;
        }
        v30 = 45;
      }
    }
    WPP_SF_qD(v29->AttachedDevice, v30, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1, CacheReferral);
    goto LABEL_34;
  }
LABEL_55:
  if ( v4 )
    goto LABEL_9;
LABEL_43:
  v41 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0 )
    return 6;
  v42 = 40;
  v43 = *(_QWORD *)(a1 + 280) + 80LL;
LABEL_46:
  WPP_SF_qZ(v41->AttachedDevice, v42, (unsigned int)WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1, v43);
  return 6;
}

```

## disassembly

```asm
0x140020660  push    rbp
0x140020662  push    rbx
0x140020663  push    rsi
0x140020664  push    r13
0x140020666  lea     rbp, [rsp-68h]
0x14002066b  sub     rsp, 168h
0x140020672  mov     rbx, rcx
0x140020675  xor     r13d, r13d
0x140020678  lea     rcx, [rsp+180h+var_130]; void *
0x14002067d  mov     [rbp+80h+arg_0], r13d
0x140020684  xor     edx, edx; Val
0x140020686  mov     r8d, 108h; Size
0x14002068c  call    memset
0x140020691  cmp     [rbx+0D0h], r13w
0x140020699  jz      loc_140020BF9
0x14002069f  mov     r9, [rbx+118h]
0x1400206a6  xorps   xmm0, xmm0
0x1400206a9  movzx   ecx, word ptr [rbx+0B0h]
0x1400206b0  xorps   xmm1, xmm1
0x1400206b3  shr     cx, 1
0x1400206b6  mov     esi, 0FFFFh
0x1400206bb  movups  xmmword ptr [rsp+180h+String1.Length], xmm0
0x1400206c0  movzx   edx, word ptr [r9+50h]
0x1400206c5  shr     dx, 1
0x1400206c8  movups  xmmword ptr [rsp+180h+String2.Length], xmm1
0x1400206cd  jz      short loc_1400206F1
0x1400206cf  mov     r10, [r9+58h]
0x1400206d3  movzx   eax, dx
0x1400206d6  movzx   r8d, word ptr [r10+rax*2-2]
0x1400206dc  cmp     r8w, 5Ch ; '\'
0x1400206e1  jz      loc_140020B74
0x1400206e7  test    r8w, r8w
0x1400206eb  jz      loc_140020B74
0x1400206f1  test    cx, cx
0x1400206f4  jz      loc_140020B82
0x1400206fa  mov     r10, [rbx+0B8h]
0x140020701  movzx   eax, cx
0x140020704  movzx   r8d, word ptr [r10+rax*2-2]
0x14002070a  cmp     r8w, 5Ch ; '\'
0x14002070f  jz      loc_140020BE3
0x140020715  test    r8w, r8w
0x140020719  jz      loc_140020BE3
0x14002071f  cmp     cx, dx
0x140020722  jz      loc_140020A3D
0x140020728  mov     [rsp+180h+arg_8], rdi
0x140020730  lea     rax, [rsp+180h+var_130]
0x140020735  mov     [rsp+180h+arg_10], r12
0x14002073d  lea     rdi, [rbx+8]
0x140020741  mov     [rsp+180h+arg_18], r14
0x140020749  mov     rcx, rdi
0x14002074c  mov     r14d, 2
0x140020752  mov     [rsp+180h+var_20], r15
0x14002075a  mov     edx, r14d
0x14002075d  lea     rax, [rax+80h]
0x140020764  movups  xmm0, xmmword ptr [rcx]
0x140020767  movups  xmm1, xmmword ptr [rcx+10h]
0x14002076b  lea     rcx, [rcx+80h]
0x140020772  movups  xmmword ptr [rax-80h], xmm0
0x140020776  movups  xmm0, xmmword ptr [rcx-60h]
0x14002077a  movups  xmmword ptr [rax-70h], xmm1
0x14002077e  movups  xmm1, xmmword ptr [rcx-50h]
0x140020782  movups  xmmword ptr [rax-60h], xmm0
0x140020786  movups  xmm0, xmmword ptr [rcx-40h]
0x14002078a  movups  xmmword ptr [rax-50h], xmm1
0x14002078e  movups  xmm1, xmmword ptr [rcx-30h]
0x140020792  movups  xmmword ptr [rax-40h], xmm0
0x140020796  movups  xmm0, xmmword ptr [rcx-20h]
0x14002079a  movups  xmmword ptr [rax-30h], xmm1
0x14002079e  movups  xmm1, xmmword ptr [rcx-10h]
0x1400207a2  movups  xmmword ptr [rax-20h], xmm0
0x1400207a6  movups  xmmword ptr [rax-10h], xmm1
0x1400207aa  sub     rdx, 1; Val
0x1400207ae  jnz     short loc_14002075D
0x1400207b0  mov     rcx, [rcx]
0x1400207b3  mov     r8d, 60h ; '`'; Size
0x1400207b9  mov     [rax], rcx
0x1400207bc  lea     rcx, [rbx+10h]; void *
0x1400207c0  call    memset
0x1400207c5  lea     rcx, [rbx+70h]; void *
0x1400207c9  xor     edx, edx; Val
0x1400207cb  mov     r8d, 60h ; '`'; Size
0x1400207d1  call    memset
0x1400207d6  xorps   xmm0, xmm0
0x1400207d9  lea     r8, [rbp+80h+var_68]
0x1400207dd  movups  xmmword ptr [rbx+0D0h], xmm0
0x1400207e4  mov     [rbx+0E2h], r13w
0x1400207ec  mov     r9b, 1
0x1400207ef  mov     rdx, [rbx+118h]
0x1400207f6  mov     rcx, rbx
0x1400207f9  add     rdx, 60h ; '`'
0x1400207fd  call    DfscRewritePath
0x140020802  lea     r15, [rbx+110h]
0x140020809  mov     r8d, eax
0x14002080c  mov     r12, [r15]
0x14002080f  mov     [r15], r13
0x140020812  test    eax, eax
0x140020814  js      loc_140020998
0x14002081a  lea     r8, [rbp+80h+arg_0]
0x140020821  mov     rdx, r15
0x140020824  mov     rcx, rdi
0x140020827  call    DfscGetCacheReferral
0x14002082c  mov     r8d, eax
0x14002082f  test    eax, eax
0x140020831  jnz     loc_140020972
0x140020837  mov     r8d, [rbp+80h+arg_0]
0x14002083e  cmp     r8d, r14d
0x140020841  jnz     loc_140020BA9
0x140020847  movzx   edx, word ptr [rbp+80h+var_68]
0x14002084b  xorps   xmm0, xmm0
0x14002084e  movzx   ecx, word ptr [rbx+0D0h]
0x140020855  xorps   xmm1, xmm1
0x140020858  shr     dx, 1
0x14002085b  shr     cx, 1
0x14002085e  movups  xmmword ptr [rsp+180h+String2.Length], xmm0
0x140020863  movups  xmmword ptr [rsp+180h+String1.Length], xmm1
0x140020868  jz      short loc_14002088F
0x14002086a  mov     r9, [rbx+0D8h]
0x140020871  movzx   eax, cx
0x140020874  movzx   r8d, word ptr [r9+rax*2-2]
0x14002087a  cmp     r8w, 5Ch ; '\'
0x14002087f  jz      loc_140020B90
0x140020885  test    r8w, r8w
0x140020889  jz      loc_140020B90
0x14002088f  test    dx, dx
0x140020892  jz      loc_140020B9E
0x140020898  mov     r9, qword ptr [rbp+80h+var_68+8]
0x14002089c  movzx   eax, dx
0x14002089f  movzx   r8d, word ptr [r9+rax*2-2]
0x1400208a5  cmp     r8w, 5Ch ; '\'
0x1400208aa  jz      loc_140020BEE
0x1400208b0  test    r8w, r8w
0x1400208b4  jz      loc_140020BEE
0x1400208ba  cmp     dx, cx
0x1400208bd  jz      loc_140020ADB
0x1400208c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400208ca  lea     rax, WPP_GLOBAL_Control
0x1400208d1  cmp     rcx, rax
0x1400208d4  jz      short loc_1400208E3
0x1400208d6  test    dword ptr [rcx+2Ch], 400000h
0x1400208dd  jnz     loc_140020CA0
0x1400208e3  mov     rcx, [rbp+80h+P]; P
0x1400208e7  mov     esi, 1
0x1400208ec  test    rcx, rcx
0x1400208ef  jz      short loc_1400208FF
0x1400208f1  xor     edx, edx; Tag
0x1400208f3  call    cs:__imp_ExFreePoolWithTag
0x1400208fa  nop     dword ptr [rax+rax+00h]
0x1400208ff  xor     edx, edx; Val
0x140020901  lea     rcx, [rsp+180h+var_128]; void *
0x140020906  mov     r8d, 60h ; '`'; Size
0x14002090c  call    memset
0x140020911  xor     edx, edx; Val
0x140020913  lea     rcx, [rbp+80h+var_C8]; void *
0x140020917  mov     r8d, 60h ; '`'; Size
0x14002091d  call    memset
0x140020922  mov     [rbp+80h+var_56], r13w
0x140020927  xorps   xmm0, xmm0
0x14002092a  movups  [rbp+80h+var_68], xmm0
0x14002092e  test    r12, r12
0x140020931  jz      short loc_14002093B
0x140020933  mov     rcx, r12; P
0x140020936  call    DfscReferralRelease
0x14002093b  inc     word ptr [rbx+122h]
0x140020942  mov     r15, [rsp+180h+var_20]
0x14002094a  mov     eax, esi
0x14002094c  mov     r14, [rsp+180h+arg_18]
0x140020954  mov     r12, [rsp+180h+arg_10]
0x14002095c  mov     rdi, [rsp+180h+arg_8]
0x140020964  add     rsp, 168h
0x14002096b  pop     r13
0x14002096d  pop     rsi
0x14002096e  pop     rbx
0x14002096f  pop     rbp
0x140020970  retn
0x140020972  mov     rcx, cs:WPP_GLOBAL_Control
0x140020979  lea     rax, WPP_GLOBAL_Control
0x140020980  cmp     rcx, rax
0x140020983  jz      short loc_1400209AF
0x140020985  test    dword ptr [rcx+2Ch], 400000h
0x14002098c  jz      short loc_1400209AF
0x14002098e  mov     edx, 2Eh ; '.'
0x140020993  jmp     loc_140020CD7
0x140020998  mov     rcx, cs:WPP_GLOBAL_Control
0x14002099f  lea     rax, WPP_GLOBAL_Control
0x1400209a6  cmp     rcx, rax
0x1400209a9  jnz     loc_140020CC5
0x1400209af  mov     rcx, [rbx+68h]; P
0x1400209b3  mov     esi, 6
0x1400209b8  test    rcx, rcx
0x1400209bb  jz      short loc_1400209CB
0x1400209bd  xor     edx, edx; Tag
0x1400209bf  call    cs:__imp_ExFreePoolWithTag
0x1400209c6  nop     dword ptr [rax+rax+00h]
0x1400209cb  lea     rcx, [rsp+180h+var_130]
0x1400209d0  lea     rdi, [rdi+80h]
0x1400209d7  movups  xmm0, xmmword ptr [rcx]
0x1400209da  movups  xmm1, xmmword ptr [rcx+10h]
0x1400209de  lea     rcx, [rcx+80h]
0x1400209e5  movups  xmmword ptr [rdi-80h], xmm0
0x1400209e9  movups  xmm0, xmmword ptr [rcx-60h]
0x1400209ed  movups  xmmword ptr [rdi-70h], xmm1
0x1400209f1  movups  xmm1, xmmword ptr [rcx-50h]
0x1400209f5  movups  xmmword ptr [rdi-60h], xmm0
0x1400209f9  movups  xmm0, xmmword ptr [rcx-40h]
0x1400209fd  movups  xmmword ptr [rdi-50h], xmm1
0x140020a01  movups  xmm1, xmmword ptr [rcx-30h]
0x140020a05  movups  xmmword ptr [rdi-40h], xmm0
0x140020a09  movups  xmm0, xmmword ptr [rcx-20h]
0x140020a0d  movups  xmmword ptr [rdi-30h], xmm1
0x140020a11  movups  xmm1, xmmword ptr [rcx-10h]
0x140020a15  movups  xmmword ptr [rdi-20h], xmm0
0x140020a19  movups  xmmword ptr [rdi-10h], xmm1
0x140020a1d  sub     r14, 1
0x140020a21  jnz     short loc_1400209D0
0x140020a23  mov     rcx, [rcx]
0x140020a26  mov     [rdi], rcx
0x140020a29  mov     rcx, [r15]; P
0x140020a2c  test    rcx, rcx
0x140020a2f  jnz     loc_140020CF4
0x140020a35  mov     [r15], r12
0x140020a38  jmp     loc_140020942
0x140020a3d  test    dx, dx
0x140020a40  jz      loc_140020728
0x140020a46  movups  xmm0, xmmword ptr [r9+50h]
0x140020a4b  add     dx, dx
0x140020a4e  add     cx, cx
0x140020a51  mov     r8b, 1; CaseInSensitive
0x140020a54  movups  xmmword ptr [rsp+180h+String1.Length], xmm0
0x140020a59  mov     [rsp+180h+String1.Length], dx
0x140020a5e  lea     rdx, [rsp+180h+String2]; String2
0x140020a63  movups  xmm0, xmmword ptr [rbx+0B0h]
0x140020a6a  movups  xmmword ptr [rsp+180h+String2.Length], xmm0
0x140020a6f  mov     [rsp+180h+String2.Length], cx
0x140020a74  lea     rcx, [rsp+180h+String1]; String1
0x140020a79  call    cs:__imp_RtlCompareUnicodeString
0x140020a80  nop     dword ptr [rax+rax+00h]
0x140020a85  test    eax, eax
0x140020a87  jnz     loc_140020728
0x140020a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140020a94  lea     rax, WPP_GLOBAL_Control
0x140020a9b  cmp     rcx, rax
0x140020a9e  jz      short loc_140020AD1
0x140020aa0  test    dword ptr [rcx+2Ch], 400000h
0x140020aa7  jz      short loc_140020AD1
0x140020aa9  mov     rax, [rbx+118h]
0x140020ab0  mov     edx, 28h ; '('
0x140020ab5  add     rax, 50h ; 'P'
0x140020ab9  mov     rcx, [rcx+18h]
0x140020abd  lea     r8, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids
0x140020ac4  mov     r9, rbx
0x140020ac7  mov     [rsp+180h+var_160], rax
0x140020acc  call    WPP_SF_qZ
0x140020ad1  mov     eax, 6
0x140020ad6  jmp     loc_140020964
0x140020adb  test    cx, cx
0x140020ade  jz      loc_1400208C3
0x140020ae4  movups  xmm0, xmmword ptr [rbx+0D0h]
0x140020aeb  add     cx, cx
0x140020aee  add     dx, dx
0x140020af1  mov     r8b, 1; CaseInSensitive
0x140020af4  movups  xmmword ptr [rsp+180h+String2.Length], xmm0
0x140020af9  mov     [rsp+180h+String2.Length], cx
0x140020afe  lea     rcx, [rsp+180h+String2]; String1
0x140020b03  movups  xmm0, [rbp+80h+var_68]
0x140020b07  movups  xmmword ptr [rsp+180h+String1.Length], xmm0
0x140020b0c  mov     [rsp+180h+String1.Length], dx
0x140020b11  lea     rdx, [rsp+180h+String1]; String2
0x140020b16  call    cs:__imp_RtlCompareUnicodeString
0x140020b1d  nop     dword ptr [rax+rax+00h]
0x140020b22  test    eax, eax
0x140020b24  jnz     loc_1400208C3
0x140020b2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140020b31  lea     rax, WPP_GLOBAL_Control
0x140020b38  cmp     rcx, rax
0x140020b3b  jz      loc_1400209AF
0x140020b41  test    dword ptr [rcx+2Ch], 400000h
0x140020b48  jz      loc_1400209AF
0x140020b4e  mov     rcx, [rcx+18h]
0x140020b52  lea     rax, [rbx+60h]
0x140020b56  mov     edx, 29h ; ')'
0x140020b5b  mov     [rsp+180h+var_160], rax
0x140020b60  mov     r9, rbx
0x140020b63  lea     r8, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids
0x140020b6a  call    WPP_SF_qZ
0x140020b6f  jmp     loc_1400209AF
0x140020b74  add     dx, si
0x140020b77  jnz     loc_1400206D3
0x140020b7d  jmp     loc_1400206F1
0x140020b82  test    dx, dx
0x140020b85  jnz     loc_140020728
0x140020b8b  jmp     loc_140020A8D
0x140020b90  add     cx, si
0x140020b93  jnz     loc_140020871
0x140020b99  jmp     loc_14002088F
0x140020b9e  test    cx, cx
0x140020ba1  jnz     loc_1400208C3
0x140020ba7  jmp     short loc_140020B2A
0x140020ba9  test    r8d, r8d
0x140020bac  jz      loc_140020C7A
0x140020bb2  cmp     r8d, 1
  ... truncated ...
```

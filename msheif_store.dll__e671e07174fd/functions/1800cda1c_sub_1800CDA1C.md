# sub_1800CDA1C

- ea: `0x1800cda1c`
- end: `0x1800ce075`
- name: `sub_1800CDA1C`
- size: `1625`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800d1c50`

## callees

- `0x180002d00`
- `0x180059ab4`
- `0x180059eac`
- `0x18005ae04`
- `0x18005b17c`
- `0x18005e330`
- `0x18005ef34`
- `0x180070474`
- `0x180079880`
- `0x1800cda1c`
- `0x180207168`
- `0x1802b9010`

## import_xrefs

- `MFPlat!MFCreateCollection` at `0x1800cdb10`
- `MFPlat!MFCreateCollection` at `0x1800cdcc0`
- `MFPlat!MFCreateCollection` at `0x1800cdb10`
- `MFPlat!MFCreateCollection` at `0x1800cdcc0`

## string_xrefs

- `0x1800cda5d`: `CWICHeifDecoderFrame::CreateCombinedCollection`
- `0x1800cdad9`: `CWICHeifDecoderFrame::CreateCombinedCollection`
- `0x1800cdb9f`: `CWICHeifDecoderFrame::CreateCombinedCollection`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall sub_1800CDA1C(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdi
  int v11; // ebx
  int v12; // ebx
  unsigned int *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 *v22; // rcx
  unsigned int v23; // esi
  __int64 (__fastcall *v24)(__int64, _QWORD, _QWORD *); // rbx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  __int64 *v30; // rcx
  __int64 *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rcx
  unsigned int v35; // esi
  __int64 (__fastcall *v36)(__int64, _QWORD, _QWORD *); // rbx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 *v46; // rcx
  __int64 *v47; // rcx
  __int64 v48; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v49[4]; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v50; // [rsp+3Ch] [rbp-2Dh] BYREF
  __int64 v51; // [rsp+40h] [rbp-29h]
  _BYTE v52[32]; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v53[2]; // [rsp+68h] [rbp-1h] BYREF

  v51 = -2;
  sub_180059AB4(v49, "CWICHeifDecoderFrame::CreateCombinedCollection", 937);
  if ( *(_BYTE *)(qword_180685260 + 8) && *(_QWORD *)(a1 + 112) )
  {
    v10 = sub_18005AE04(qword_180685260, v8, v9);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 112) + 296LL))(*(_QWORD *)(a1 + 112));
    *(_OWORD *)(v10 + 2000) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(a1 + 112) + 280LL))(
                                           *(_QWORD *)(a1 + 112),
                                           v53);
    *(_DWORD *)(v10 + 2016) = v11;
  }
  v12 = 0;
  v13 = (unsigned int *)(a1 + 48);
  sub_18005E330(v52, (a1 + 48) & -(__int64)(a1 != 0), "CWICHeifDecoderFrame::CreateCombinedCollection");
  v48 = 0;
  v53[0] = 0;
  v50 = 0;
  *a4 = 0;
  if ( !a2 )
    goto LABEL_30;
  sub_180070474(&v48, v14, v15, v16);
  v12 = MFCreateCollection(&v48);
  if ( v12 < 0 )
  {
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 120, qword_1805D65D8, *v13, v12);
    }
    v19 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v19 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v20 = sub_18005AE04(v19, v17, v18);
      if ( *(_DWORD *)(v20 + 1996) != v12 )
      {
        v21 = 946;
LABEL_15:
        sub_180207168(v20, "CWICHeifDecoderFrame::CreateCombinedCollection", v21);
        goto LABEL_75;
      }
    }
    goto LABEL_75;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 24LL))(a2, &v50);
  if ( v12 >= 0 )
  {
    v23 = 0;
    if ( v50 )
    {
      while ( 1 )
      {
        v24 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)a2 + 32LL);
        sub_18005B17C(v53);
        v12 = v24(a2, v23, v53);
        if ( v12 < 0 )
          break;
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v48 + 40LL))(v48, v53[0]);
        if ( v12 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 123, qword_1805D65D8, *v13, v12);
          }
          v30 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v30 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( *((_BYTE *)v30 + 8) )
          {
            v20 = sub_18005AE04(v30, v14, v15);
            if ( *(_DWORD *)(v20 + 1996) != v12 )
            {
              v21 = 953;
              goto LABEL_15;
            }
          }
          goto LABEL_75;
        }
        if ( ++v23 >= v50 )
          goto LABEL_30;
      }
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 122, qword_1805D65D8, *v13, v12);
      }
      v31 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v31 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v20 = sub_18005AE04(v31, v25, v26);
        if ( *(_DWORD *)(v20 + 1996) != v12 )
        {
          v21 = 952;
          goto LABEL_15;
        }
      }
      goto LABEL_75;
    }
LABEL_30:
    if ( a3 )
    {
      if ( !v48 )
      {
        sub_180070474(&v48, v14, v15, v16);
        v12 = MFCreateCollection(&v48);
        if ( v12 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 124, qword_1805D65D8, *v13, v12);
          }
          v29 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v29 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( *((_BYTE *)v29 + 8) )
          {
            v20 = sub_18005AE04(v29, v27, v28);
            if ( *(_DWORD *)(v20 + 1996) != v12 )
            {
              v21 = 961;
              goto LABEL_15;
            }
          }
          goto LABEL_75;
        }
      }
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a3 + 24LL))(a3, &v50);
      if ( v12 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 125, qword_1805D65D8, *v13, v12);
        }
        v34 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v34 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v20 = sub_18005AE04(v34, v32, v33);
          if ( *(_DWORD *)(v20 + 1996) != v12 )
          {
            v21 = 964;
            goto LABEL_15;
          }
        }
        goto LABEL_75;
      }
      v35 = 0;
      if ( v50 )
      {
        while ( 1 )
        {
          v36 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)a3 + 32LL);
          sub_18005B17C(v53);
          v12 = v36(a3, v35, v53);
          if ( v12 < 0 )
            break;
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v48 + 40LL))(v48, v53[0]);
          if ( v12 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 127, qword_1805D65D8, *v13, v12);
            }
            v46 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v46 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( *((_BYTE *)v46 + 8) )
            {
              v20 = sub_18005AE04(v46, v39, v40);
              if ( *(_DWORD *)(v20 + 1996) != v12 )
              {
                v21 = 969;
                goto LABEL_15;
              }
            }
            goto LABEL_75;
          }
          if ( ++v35 >= v50 )
            goto LABEL_74;
        }
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 126, qword_1805D65D8, *v13, v12);
        }
        v47 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v47 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v47 + 8) )
        {
          v20 = sub_18005AE04(v47, v37, v38);
          if ( *(_DWORD *)(v20 + 1996) != v12 )
          {
            v21 = 968;
            goto LABEL_15;
          }
        }
        goto LABEL_75;
      }
    }
LABEL_74:
    v41 = v48;
    v48 = 0;
    *a4 = v41;
    goto LABEL_75;
  }
  if ( RequestContext != &RequestContext
    && (*((_BYTE *)RequestContext + 28) & 1) != 0
    && *((_BYTE *)RequestContext + 25) >= 4u )
  {
    sub_180079880(*((_QWORD *)RequestContext + 2), 121, qword_1805D65D8, *v13, v12);
  }
  v22 = (__int64 *)qword_180685260;
  if ( !qword_180685260 )
  {
    v22 = &qword_180684620;
    qword_180685260 = (__int64)&qword_180684620;
  }
  if ( *((_BYTE *)v22 + 8) )
  {
    v20 = sub_18005AE04(v22, v14, v15);
    if ( *(_DWORD *)(v20 + 1996) != v12 )
    {
      v21 = 948;
      goto LABEL_15;
    }
  }
LABEL_75:
  sub_18005B17C(v53);
  sub_180070474(&v48, v42, v43, v44);
  sub_18005EF34(v52);
  sub_180059EAC(v49);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800cda1c  push    rbp
0x1800cda1e  push    rbx
0x1800cda1f  push    rsi
0x1800cda20  push    rdi
0x1800cda21  push    r12
0x1800cda23  push    r13
0x1800cda25  push    r14
0x1800cda27  push    r15
0x1800cda29  lea     rbp, [rsp-1Fh]
0x1800cda2e  sub     rsp, 88h
0x1800cda35  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x1800cda3d  mov     rax, cs:__security_cookie
0x1800cda44  xor     rax, rsp
0x1800cda47  mov     [rbp+57h+var_48], rax
0x1800cda4b  mov     r12, r9
0x1800cda4e  mov     r15, r8
0x1800cda51  mov     r14, rdx
0x1800cda54  mov     rsi, rcx
0x1800cda57  mov     r8d, 3A9h
0x1800cda5d  lea     rdx, aCwicheifdecode_11; "CWICHeifDecoderFrame::CreateCombinedCol"...
0x1800cda64  lea     rcx, [rbp+57h+var_88]
0x1800cda68  call    sub_180059AB4
0x1800cda6d  nop
0x1800cda6e  xor     r13d, r13d
0x1800cda71  mov     rcx, cs:qword_180685260
0x1800cda78  cmp     [rcx+8], r13b
0x1800cda7c  jz      short loc_1800CDAC9
0x1800cda7e  cmp     [rsi+70h], r13
0x1800cda82  jz      short loc_1800CDAC9
0x1800cda84  call    sub_18005AE04
0x1800cda89  mov     rdi, rax
0x1800cda8c  mov     rcx, [rsi+70h]
0x1800cda90  mov     rdx, [rcx]
0x1800cda93  mov     rax, [rdx+128h]
0x1800cda9a  call    j__guard_dispatch_icall
0x1800cda9f  mov     ebx, eax
0x1800cdaa1  mov     rcx, [rsi+70h]
0x1800cdaa5  mov     rdx, [rcx]
0x1800cdaa8  mov     rax, [rdx+118h]
0x1800cdaaf  lea     rdx, [rbp+57h+var_58]
0x1800cdab3  call    j__guard_dispatch_icall
0x1800cdab8  movups  xmm0, xmmword ptr [rax]
0x1800cdabb  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800cdac3  mov     [rdi+7E0h], ebx
0x1800cdac9  mov     ebx, r13d
0x1800cdacc  lea     rdi, [rsi+30h]
0x1800cdad0  neg     rsi
0x1800cdad3  sbb     rdx, rdx
0x1800cdad6  and     rdx, rdi
0x1800cdad9  lea     r8, aCwicheifdecode_11; "CWICHeifDecoderFrame::CreateCombinedCol"...
0x1800cdae0  lea     rcx, [rbp+57h+var_78]
0x1800cdae4  call    sub_18005E330
0x1800cdae9  nop
0x1800cdaea  mov     [rbp+57h+var_90], r13
0x1800cdaee  mov     [rbp+57h+var_58], r13
0x1800cdaf2  mov     [rbp+57h+var_84], r13d
0x1800cdaf6  mov     [r12], r13
0x1800cdafa  test    r14, r14
0x1800cdafd  jz      loc_1800CDCA0
0x1800cdb03  lea     rcx, [rbp+57h+var_90]
0x1800cdb07  call    sub_180070474
0x1800cdb0c  lea     rcx, [rbp+57h+var_90]
0x1800cdb10  call    cs:MFCreateCollection
0x1800cdb17  nop     dword ptr [rax+rax+00h]
0x1800cdb1c  mov     ebx, eax
0x1800cdb1e  test    eax, eax
0x1800cdb20  jns     loc_1800CDBB3
0x1800cdb26  lea     rax, RequestContext
0x1800cdb2d  mov     rcx, cs:RequestContext
0x1800cdb34  cmp     rcx, rax
0x1800cdb37  jz      short loc_1800CDB61
0x1800cdb39  test    byte ptr [rcx+1Ch], 1
0x1800cdb3d  jz      short loc_1800CDB61
0x1800cdb3f  cmp     byte ptr [rcx+19h], 4
0x1800cdb43  jb      short loc_1800CDB61
0x1800cdb45  mov     edx, 78h ; 'x'
0x1800cdb4a  mov     [rsp+0C0h+var_A0], ebx
0x1800cdb4e  mov     r9d, [rdi]
0x1800cdb51  lea     r8, qword_1805D65D8
0x1800cdb58  mov     rcx, [rcx+10h]
0x1800cdb5c  call    sub_180079880
0x1800cdb61  mov     rcx, cs:qword_180685260
0x1800cdb68  test    rcx, rcx
0x1800cdb6b  jnz     short loc_1800CDB7B
0x1800cdb6d  lea     rcx, qword_180684620
0x1800cdb74  mov     cs:qword_180685260, rcx
0x1800cdb7b  cmp     [rcx+8], r13b
0x1800cdb7f  jz      loc_1800CDF34
0x1800cdb85  call    sub_18005AE04
0x1800cdb8a  cmp     [rax+7CCh], ebx
0x1800cdb90  jz      loc_1800CDF34
0x1800cdb96  mov     r8d, 3B2h
0x1800cdb9c  mov     r9d, ebx
0x1800cdb9f  lea     rdx, aCwicheifdecode_11; "CWICHeifDecoderFrame::CreateCombinedCol"...
0x1800cdba6  mov     rcx, rax
0x1800cdba9  call    sub_180207168
0x1800cdbae  jmp     loc_1800CDF34
0x1800cdbb3  mov     rax, [r14]
0x1800cdbb6  lea     rdx, [rbp+57h+var_84]
0x1800cdbba  mov     rcx, r14
0x1800cdbbd  mov     rax, [rax+18h]
0x1800cdbc1  call    j__guard_dispatch_icall
0x1800cdbc6  mov     ebx, eax
0x1800cdbc8  test    eax, eax
0x1800cdbca  jns     short loc_1800CDC47
0x1800cdbcc  lea     rax, RequestContext
0x1800cdbd3  mov     rcx, cs:RequestContext
0x1800cdbda  cmp     rcx, rax
0x1800cdbdd  jz      short loc_1800CDC07
0x1800cdbdf  test    byte ptr [rcx+1Ch], 1
0x1800cdbe3  jz      short loc_1800CDC07
0x1800cdbe5  cmp     byte ptr [rcx+19h], 4
0x1800cdbe9  jb      short loc_1800CDC07
0x1800cdbeb  mov     edx, 79h ; 'y'
0x1800cdbf0  mov     [rsp+0C0h+var_A0], ebx
0x1800cdbf4  mov     r9d, [rdi]
0x1800cdbf7  lea     r8, qword_1805D65D8
0x1800cdbfe  mov     rcx, [rcx+10h]
0x1800cdc02  call    sub_180079880
0x1800cdc07  mov     rcx, cs:qword_180685260
0x1800cdc0e  test    rcx, rcx
0x1800cdc11  jnz     short loc_1800CDC21
0x1800cdc13  lea     rcx, qword_180684620
0x1800cdc1a  mov     cs:qword_180685260, rcx
0x1800cdc21  cmp     [rcx+8], r13b
0x1800cdc25  jz      loc_1800CDF34
0x1800cdc2b  call    sub_18005AE04
0x1800cdc30  cmp     [rax+7CCh], ebx
0x1800cdc36  jz      loc_1800CDF34
0x1800cdc3c  mov     r8d, 3B4h
0x1800cdc42  jmp     loc_1800CDB9C
0x1800cdc47  mov     esi, r13d
0x1800cdc4a  cmp     [rbp+57h+var_84], r13d
0x1800cdc4e  jbe     short loc_1800CDCA0
0x1800cdc50  mov     rax, [r14]
0x1800cdc53  mov     rbx, [rax+20h]
0x1800cdc57  lea     rcx, [rbp+57h+var_58]
0x1800cdc5b  call    sub_18005B17C
0x1800cdc60  lea     r8, [rbp+57h+var_58]
0x1800cdc64  mov     edx, esi
0x1800cdc66  mov     rcx, r14
0x1800cdc69  mov     rax, rbx
0x1800cdc6c  call    j__guard_dispatch_icall
0x1800cdc71  mov     ebx, eax
0x1800cdc73  test    eax, eax
0x1800cdc75  js      loc_1800CDDCC
0x1800cdc7b  mov     rcx, [rbp+57h+var_90]
0x1800cdc7f  mov     rax, [rcx]
0x1800cdc82  mov     rdx, [rbp+57h+var_58]
0x1800cdc86  mov     rax, [rax+28h]
0x1800cdc8a  call    j__guard_dispatch_icall
0x1800cdc8f  mov     ebx, eax
0x1800cdc91  test    eax, eax
0x1800cdc93  js      loc_1800CDD51
0x1800cdc99  inc     esi
0x1800cdc9b  cmp     esi, [rbp+57h+var_84]
0x1800cdc9e  jb      short loc_1800CDC50
0x1800cdca0  test    r15, r15
0x1800cdca3  jz      loc_1800CDF28
0x1800cdca9  cmp     [rbp+57h+var_90], r13
0x1800cdcad  jnz     loc_1800CDE47
0x1800cdcb3  lea     rcx, [rbp+57h+var_90]
0x1800cdcb7  call    sub_180070474
0x1800cdcbc  lea     rcx, [rbp+57h+var_90]
0x1800cdcc0  call    cs:MFCreateCollection
0x1800cdcc7  nop     dword ptr [rax+rax+00h]
0x1800cdccc  mov     ebx, eax
0x1800cdcce  test    eax, eax
0x1800cdcd0  jns     loc_1800CDE47
0x1800cdcd6  lea     rax, RequestContext
0x1800cdcdd  mov     rcx, cs:RequestContext
0x1800cdce4  cmp     rcx, rax
0x1800cdce7  jz      short loc_1800CDD11
0x1800cdce9  test    byte ptr [rcx+1Ch], 1
0x1800cdced  jz      short loc_1800CDD11
0x1800cdcef  cmp     byte ptr [rcx+19h], 4
0x1800cdcf3  jb      short loc_1800CDD11
0x1800cdcf5  mov     edx, 7Ch ; '|'
0x1800cdcfa  mov     [rsp+0C0h+var_A0], ebx
0x1800cdcfe  mov     r9d, [rdi]
0x1800cdd01  lea     r8, qword_1805D65D8
0x1800cdd08  mov     rcx, [rcx+10h]
0x1800cdd0c  call    sub_180079880
0x1800cdd11  mov     rcx, cs:qword_180685260
0x1800cdd18  test    rcx, rcx
0x1800cdd1b  jnz     short loc_1800CDD2B
0x1800cdd1d  lea     rcx, qword_180684620
0x1800cdd24  mov     cs:qword_180685260, rcx
0x1800cdd2b  cmp     [rcx+8], r13b
0x1800cdd2f  jz      loc_1800CDF34
0x1800cdd35  call    sub_18005AE04
0x1800cdd3a  cmp     [rax+7CCh], ebx
0x1800cdd40  jz      loc_1800CDF34
0x1800cdd46  mov     r8d, 3C1h
0x1800cdd4c  jmp     loc_1800CDB9C
0x1800cdd51  lea     rax, RequestContext
0x1800cdd58  mov     rcx, cs:RequestContext
0x1800cdd5f  cmp     rcx, rax
0x1800cdd62  jz      short loc_1800CDD8C
0x1800cdd64  test    byte ptr [rcx+1Ch], 1
0x1800cdd68  jz      short loc_1800CDD8C
0x1800cdd6a  cmp     byte ptr [rcx+19h], 4
0x1800cdd6e  jb      short loc_1800CDD8C
0x1800cdd70  mov     edx, 7Bh ; '{'
0x1800cdd75  mov     [rsp+0C0h+var_A0], ebx
0x1800cdd79  mov     r9d, [rdi]
0x1800cdd7c  lea     r8, qword_1805D65D8
0x1800cdd83  mov     rcx, [rcx+10h]
0x1800cdd87  call    sub_180079880
0x1800cdd8c  mov     rcx, cs:qword_180685260
0x1800cdd93  test    rcx, rcx
0x1800cdd96  jnz     short loc_1800CDDA6
0x1800cdd98  lea     rcx, qword_180684620
0x1800cdd9f  mov     cs:qword_180685260, rcx
0x1800cdda6  cmp     [rcx+8], r13b
0x1800cddaa  jz      loc_1800CDF34
0x1800cddb0  call    sub_18005AE04
0x1800cddb5  cmp     [rax+7CCh], ebx
0x1800cddbb  jz      loc_1800CDF34
0x1800cddc1  mov     r8d, 3B9h
0x1800cddc7  jmp     loc_1800CDB9C
0x1800cddcc  lea     rax, RequestContext
0x1800cddd3  mov     rcx, cs:RequestContext
0x1800cddda  cmp     rcx, rax
0x1800cdddd  jz      short loc_1800CDE07
0x1800cdddf  test    byte ptr [rcx+1Ch], 1
0x1800cdde3  jz      short loc_1800CDE07
0x1800cdde5  cmp     byte ptr [rcx+19h], 4
0x1800cdde9  jb      short loc_1800CDE07
0x1800cddeb  mov     edx, 7Ah ; 'z'
0x1800cddf0  mov     [rsp+0C0h+var_A0], ebx
0x1800cddf4  mov     r9d, [rdi]
0x1800cddf7  lea     r8, qword_1805D65D8
0x1800cddfe  mov     rcx, [rcx+10h]
0x1800cde02  call    sub_180079880
0x1800cde07  mov     rcx, cs:qword_180685260
0x1800cde0e  test    rcx, rcx
0x1800cde11  jnz     short loc_1800CDE21
0x1800cde13  lea     rcx, qword_180684620
0x1800cde1a  mov     cs:qword_180685260, rcx
0x1800cde21  cmp     [rcx+8], r13b
0x1800cde25  jz      loc_1800CDF34
0x1800cde2b  call    sub_18005AE04
0x1800cde30  cmp     [rax+7CCh], ebx
0x1800cde36  jz      loc_1800CDF34
0x1800cde3c  mov     r8d, 3B8h
0x1800cde42  jmp     loc_1800CDB9C
0x1800cde47  mov     rax, [r15]
0x1800cde4a  lea     rdx, [rbp+57h+var_84]
0x1800cde4e  mov     rcx, r15
0x1800cde51  mov     rax, [rax+18h]
0x1800cde55  call    j__guard_dispatch_icall
0x1800cde5a  mov     ebx, eax
0x1800cde5c  test    eax, eax
0x1800cde5e  jns     short loc_1800CDED3
0x1800cde60  lea     rax, RequestContext
0x1800cde67  mov     rcx, cs:RequestContext
0x1800cde6e  cmp     rcx, rax
0x1800cde71  jz      short loc_1800CDE9B
0x1800cde73  test    byte ptr [rcx+1Ch], 1
0x1800cde77  jz      short loc_1800CDE9B
0x1800cde79  cmp     byte ptr [rcx+19h], 4
0x1800cde7d  jb      short loc_1800CDE9B
0x1800cde7f  mov     edx, 7Dh ; '}'
0x1800cde84  mov     [rsp+0C0h+var_A0], ebx
0x1800cde88  mov     r9d, [rdi]
0x1800cde8b  lea     r8, qword_1805D65D8
0x1800cde92  mov     rcx, [rcx+10h]
0x1800cde96  call    sub_180079880
0x1800cde9b  mov     rcx, cs:qword_180685260
0x1800cdea2  test    rcx, rcx
0x1800cdea5  jnz     short loc_1800CDEB5
0x1800cdea7  lea     rcx, qword_180684620
0x1800cdeae  mov     cs:qword_180685260, rcx
0x1800cdeb5  cmp     [rcx+8], r13b
0x1800cdeb9  jz      short loc_1800CDF34
0x1800cdebb  call    sub_18005AE04
0x1800cdec0  cmp     [rax+7CCh], ebx
0x1800cdec6  jz      short loc_1800CDF34
0x1800cdec8  mov     r8d, 3C4h
0x1800cdece  jmp     loc_1800CDB9C
0x1800cded3  mov     esi, r13d
0x1800cded6  cmp     [rbp+57h+var_84], r13d
0x1800cdeda  jbe     short loc_1800CDF28
0x1800cdedc  mov     rax, [r15]
0x1800cdedf  mov     rbx, [rax+20h]
0x1800cdee3  lea     rcx, [rbp+57h+var_58]
0x1800cdee7  call    sub_18005B17C
0x1800cdeec  lea     r8, [rbp+57h+var_58]
0x1800cdef0  mov     edx, esi
0x1800cdef2  mov     rcx, r15
0x1800cdef5  mov     rax, rbx
0x1800cdef8  call    j__guard_dispatch_icall
0x1800cdefd  mov     ebx, eax
0x1800cdeff  test    eax, eax
0x1800cdf01  js      loc_1800CDFF9
0x1800cdf07  mov     rcx, [rbp+57h+var_90]
0x1800cdf0b  mov     rax, [rcx]
0x1800cdf0e  mov     rdx, [rbp+57h+var_58]
0x1800cdf12  mov     rax, [rax+28h]
  ... truncated ...
```

# SspiMarshalAuthIdentity

- ea: `0x180006420`
- end: `0x1800066eb`
- name: `SspiMarshalAuthIdentity`
- size: `715`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity, unsigned int *AuthIdentityLength, char **AuthIdentityByteArray)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180027738`

## callees

- `0x180006420`
- `0x180006700`
- `0x180006830`
- `0x180010980`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180006484`
- `ntoskrnl!ExAllocatePool2` at `0x18000658c`
- `ntoskrnl!ExAllocatePool2` at `0x180006484`
- `ntoskrnl!ExAllocatePool2` at `0x18000658c`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiMarshalAuthIdentity(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity,
        unsigned int *AuthIdentityLength,
        char **AuthIdentityByteArray)
{
  unsigned int v6; // eax
  int v7; // r9d
  char *Pool2; // rax
  unsigned int v9; // ecx
  size_t v10; // r8
  char *v11; // rbx
  int v12; // ecx
  int v13; // r14d
  unsigned int v14; // edx
  unsigned int v16; // eax
  int v17; // ecx
  unsigned int v18; // r8d
  unsigned int v19; // eax
  unsigned int v20; // edx
  unsigned int v21; // eax
  unsigned int v22; // esi
  char *v23; // rax
  char *v24; // rsi
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  char *v27; // rbp
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx

  *AuthIdentityByteArray = 0;
  *AuthIdentityLength = 0;
  v6 = SspiValidateAuthIdentity(AuthIdentity);
  if ( (v6 & 0x80000000) == 0 )
  {
    v7 = *(_DWORD *)AuthIdentity;
    if ( *(_DWORD *)AuthIdentity == 513 )
    {
      if ( (*((_DWORD *)AuthIdentity + 9) & 0x10) != 0 )
      {
LABEL_4:
        v6 = -1073741811;
        return SspNtStatusToSecStatus(v6);
      }
      Pool2 = (char *)ExAllocatePool2(256, (unsigned int)(*((_DWORD *)AuthIdentity + 2) + 8) + 2LL, 1230267731);
      *AuthIdentityByteArray = Pool2;
      if ( !Pool2 )
      {
LABEL_6:
        v6 = -1073741801;
        return SspNtStatusToSecStatus(v6);
      }
      v9 = *((_DWORD *)AuthIdentity + 2);
      v10 = v9 + 8;
      if ( !_bittest((const signed __int32 *)AuthIdentity + 9, 0x10u) )
        v10 = v9;
      memmove(Pool2, AuthIdentity, v10);
      *AuthIdentityLength = *((_DWORD *)AuthIdentity + 2) + 8;
LABEL_50:
      v6 = 0;
      return SspNtStatusToSecStatus(v6);
    }
    v11 = (char *)AuthIdentity + 8;
    if ( v7 != 512 )
      v11 = (char *)AuthIdentity;
    v12 = *((_DWORD *)v11 + 11);
    if ( (v12 & 0x10) != 0 )
      goto LABEL_4;
    v13 = ((v12 & 1) == 0) + 1;
    if ( v7 == 512 )
    {
      v14 = *((_DWORD *)AuthIdentity + 16) * v13 + 48;
      if ( (unsigned int)(*((_DWORD *)AuthIdentity + 16) * v13) >= 0xFFFFFFD0 )
        goto LABEL_15;
    }
    else
    {
      v14 = 48;
    }
    v16 = *((_DWORD *)v11 + 2) * v13;
    v17 = v12 & 0x10000;
    if ( v17 )
      v16 = (v16 + 7) & 0xFFFFFFF8;
    v18 = v16 + v14;
    if ( v16 + v14 >= v14 )
    {
      v19 = *((_DWORD *)v11 + 6) * v13;
      if ( v17 )
        v19 = (v19 + 7) & 0xFFFFFFF8;
      v20 = v18 + v19;
      if ( v18 + v19 >= v18 )
      {
        v21 = *((_DWORD *)v11 + 10) * v13;
        if ( v17 )
          v21 = (v21 + 7) & 0xFFFFFFF8;
        v22 = v20 + v21;
        if ( v20 + v21 >= v20 )
        {
          v23 = (char *)ExAllocatePool2(256, v22 + 2LL, 1230267731);
          *AuthIdentityByteArray = v23;
          if ( !v23 )
            goto LABEL_6;
          *AuthIdentityLength = v22;
          v24 = *AuthIdentityByteArray;
          *(_DWORD *)v24 = 512;
          *((_DWORD *)v24 + 1) = 44;
          *((_DWORD *)v24 + 3) = *((_DWORD *)v11 + 2);
          if ( *(_QWORD *)v11 )
          {
            *((_DWORD *)v24 + 2) = 44;
            v25 = *((_DWORD *)v11 + 2) * v13;
            if ( (*((_DWORD *)v11 + 11) & 0x10000) != 0 )
              v25 = (v25 + 7) & 0xFFFFFFF8;
            memmove(v24 + 44, *(const void **)v11, v25);
            v26 = *((_DWORD *)v11 + 2) * v13;
            if ( (*((_DWORD *)v11 + 11) & 0x10000) != 0 )
              v26 = (v26 + 7) & 0xFFFFFFF8;
            v27 = &v24[v26 + 44];
          }
          else
          {
            v27 = v24 + 44;
          }
          *((_DWORD *)v24 + 5) = *((_DWORD *)v11 + 6);
          if ( *((_QWORD *)v11 + 2) )
          {
            *((_DWORD *)v24 + 4) = (_DWORD)v27 - (_DWORD)v24;
            v28 = *((_DWORD *)v11 + 6) * v13;
            if ( (*((_DWORD *)v11 + 11) & 0x10000) != 0 )
              v28 = (v28 + 7) & 0xFFFFFFF8;
            memmove(v27, *((const void **)v11 + 2), v28);
            v29 = *((_DWORD *)v11 + 6) * v13;
            if ( (*((_DWORD *)v11 + 11) & 0x10000) != 0 )
              v29 = (v29 + 7) & 0xFFFFFFF8;
            v27 += v29;
          }
          *((_DWORD *)v24 + 7) = *((_DWORD *)v11 + 10);
          if ( *((_QWORD *)v11 + 4) )
          {
            *((_DWORD *)v24 + 6) = (_DWORD)v27 - (_DWORD)v24;
            v30 = *((_DWORD *)v11 + 10) * v13;
            if ( (*((_DWORD *)v11 + 11) & 0x10000) != 0 )
              v30 = (v30 + 7) & 0xFFFFFFF8;
            memmove(v27, *((const void **)v11 + 4), v30);
            v31 = *((_DWORD *)v11 + 10) * v13;
            if ( (*((_DWORD *)v11 + 11) & 0x10000) != 0 )
              v31 = (v31 + 7) & 0xFFFFFFF8;
            v27 += v31;
          }
          *((_DWORD *)v24 + 8) = *((_DWORD *)v11 + 11);
          if ( *(_DWORD *)AuthIdentity == 512 )
          {
            *((_DWORD *)v24 + 10) = *((_DWORD *)AuthIdentity + 16);
            if ( *((_QWORD *)AuthIdentity + 7) )
            {
              *((_DWORD *)v24 + 9) = (_DWORD)v27 - (_DWORD)v24;
              memmove(v27, *((const void **)AuthIdentity + 7), (unsigned int)(*((_DWORD *)AuthIdentity + 16) * v13));
            }
          }
          goto LABEL_50;
        }
      }
    }
LABEL_15:
    v6 = -1073741675;
  }
  return SspNtStatusToSecStatus(v6);
}

```

## disassembly

```asm
0x180006420  push    rbx
0x180006422  push    rbp
0x180006423  push    rsi
0x180006424  push    rdi
0x180006425  push    r12
0x180006427  push    r14
0x180006429  push    r15
0x18000642b  sub     rsp, 20h
0x18000642f  mov     qword ptr [r8], 0
0x180006436  mov     r15, r8
0x180006439  mov     dword ptr [rdx], 0
0x18000643f  mov     rbp, rdx
0x180006442  mov     rdi, rcx
0x180006445  call    SspiValidateAuthIdentity
0x18000644a  test    eax, eax
0x18000644c  js      loc_180006506
0x180006452  mov     r9d, [rdi]
0x180006455  cmp     r9d, 201h
0x18000645c  jnz     short loc_1800064C8
0x18000645e  mov     eax, [rdi+24h]
0x180006461  test    al, 10h
0x180006463  jz      short loc_18000646F
0x180006465  mov     eax, 0C000000Dh
0x18000646a  jmp     loc_180006506
0x18000646f  mov     edx, [rdi+8]
0x180006472  mov     ecx, 100h
0x180006477  add     edx, 8
0x18000647a  mov     r8d, 49546553h
0x180006480  add     rdx, 2
0x180006484  call    cs:__imp_ExAllocatePool2
0x18000648b  nop     dword ptr [rax+rax+00h]
0x180006490  mov     [r15], rax
0x180006493  test    rax, rax
0x180006496  jnz     short loc_18000649F
0x180006498  mov     eax, 0C0000017h
0x18000649d  jmp     short loc_180006506
0x18000649f  mov     ecx, [rdi+8]
0x1800064a2  bt      dword ptr [rdi+24h], 10h
0x1800064a7  mov     rdx, rdi; Src
0x1800064aa  lea     r8d, [rcx+8]
0x1800064ae  cmovnb  r8d, ecx; Size
0x1800064b2  mov     rcx, rax; void *
0x1800064b5  call    memmove
0x1800064ba  mov     eax, [rdi+8]
0x1800064bd  add     eax, 8
0x1800064c0  mov     [rbp+0], eax
0x1800064c3  jmp     loc_1800066E4
0x1800064c8  mov     edx, 200h
0x1800064cd  lea     rbx, [rdi+8]
0x1800064d1  cmp     r9d, edx
0x1800064d4  cmovnz  rbx, rdi
0x1800064d8  mov     ecx, [rbx+2Ch]
0x1800064db  test    cl, 10h
0x1800064de  jnz     short loc_180006465
0x1800064e0  mov     r14d, ecx
0x1800064e3  not     r14d
0x1800064e6  and     r14d, 1
0x1800064ea  inc     r14d
0x1800064ed  cmp     r9d, edx
0x1800064f0  jnz     short loc_18000651D
0x1800064f2  mov     edx, r14d
0x1800064f5  imul    edx, [rdi+40h]
0x1800064f9  add     edx, 30h ; '0'
0x1800064fc  cmp     edx, 30h ; '0'
0x1800064ff  jnb     short loc_180006522
0x180006501  mov     eax, 0C0000095h
0x180006506  mov     ecx, eax
0x180006508  call    SspNtStatusToSecStatus
0x18000650d  add     rsp, 20h
0x180006511  pop     r15
0x180006513  pop     r14
0x180006515  pop     r12
0x180006517  pop     rdi
0x180006518  pop     rsi
0x180006519  pop     rbp
0x18000651a  pop     rbx
0x18000651b  retn
0x18000651d  mov     edx, 30h ; '0'
0x180006522  mov     eax, r14d
0x180006525  mov     r12d, 10000h
0x18000652b  imul    eax, [rbx+8]
0x18000652f  mov     r9d, 0FFFFFFF8h
0x180006535  and     ecx, r12d
0x180006538  jz      short loc_180006540
0x18000653a  add     eax, 7
0x18000653d  and     eax, r9d
0x180006540  lea     r8d, [rax+rdx]
0x180006544  cmp     r8d, edx
0x180006547  jb      short loc_180006501
0x180006549  mov     eax, r14d
0x18000654c  imul    eax, [rbx+18h]
0x180006550  test    ecx, ecx
0x180006552  jz      short loc_18000655A
0x180006554  add     eax, 7
0x180006557  and     eax, r9d
0x18000655a  lea     edx, [r8+rax]
0x18000655e  cmp     edx, r8d
0x180006561  jb      short loc_180006501
0x180006563  mov     eax, r14d
0x180006566  imul    eax, [rbx+28h]
0x18000656a  test    ecx, ecx
0x18000656c  jz      short loc_180006574
0x18000656e  add     eax, 7
0x180006571  and     eax, r9d
0x180006574  lea     esi, [rdx+rax]
0x180006577  cmp     esi, edx
0x180006579  jb      short loc_180006501
0x18000657b  mov     edx, esi
0x18000657d  mov     ecx, 100h
0x180006582  add     rdx, 2
0x180006586  mov     r8d, 49546553h
0x18000658c  call    cs:__imp_ExAllocatePool2
0x180006593  nop     dword ptr [rax+rax+00h]
0x180006598  mov     [r15], rax
0x18000659b  test    rax, rax
0x18000659e  jz      loc_180006498
0x1800065a4  mov     [rbp+0], esi
0x1800065a7  mov     rsi, [r15]
0x1800065aa  mov     dword ptr [rsi], 200h
0x1800065b0  lea     r15, [rsi+2Ch]
0x1800065b4  mov     dword ptr [rsi+4], 2Ch ; ','
0x1800065bb  mov     eax, [rbx+8]
0x1800065be  mov     [rsi+0Ch], eax
0x1800065c1  cmp     qword ptr [rbx], 0
0x1800065c5  jz      short loc_18000660A
0x1800065c7  mov     eax, r15d
0x1800065ca  mov     ecx, r14d
0x1800065cd  sub     eax, esi
0x1800065cf  mov     [rsi+8], eax
0x1800065d2  imul    ecx, [rbx+8]
0x1800065d6  test    [rbx+2Ch], r12d
0x1800065da  jz      short loc_1800065E2
0x1800065dc  add     ecx, 7
0x1800065df  and     ecx, 0FFFFFFF8h
0x1800065e2  mov     rdx, [rbx]; Src
0x1800065e5  mov     r8d, ecx; Size
0x1800065e8  mov     rcx, r15; void *
0x1800065eb  call    memmove
0x1800065f0  mov     ecx, r14d
0x1800065f3  imul    ecx, [rbx+8]
0x1800065f7  test    [rbx+2Ch], r12d
0x1800065fb  jz      short loc_180006603
0x1800065fd  add     ecx, 7
0x180006600  and     ecx, 0FFFFFFF8h
0x180006603  mov     ebp, ecx
0x180006605  add     rbp, r15
0x180006608  jmp     short loc_18000660D
0x18000660a  mov     rbp, r15
0x18000660d  mov     eax, [rbx+18h]
0x180006610  mov     r15d, esi
0x180006613  mov     [rsi+14h], eax
0x180006616  cmp     qword ptr [rbx+10h], 0
0x18000661b  jz      short loc_18000665E
0x18000661d  mov     eax, ebp
0x18000661f  mov     ecx, r14d
0x180006622  sub     eax, esi
0x180006624  mov     [rsi+10h], eax
0x180006627  imul    ecx, [rbx+18h]
0x18000662b  test    [rbx+2Ch], r12d
0x18000662f  jz      short loc_180006637
0x180006631  add     ecx, 7
0x180006634  and     ecx, 0FFFFFFF8h
0x180006637  mov     rdx, [rbx+10h]; Src
0x18000663b  mov     r8d, ecx; Size
0x18000663e  mov     rcx, rbp; void *
0x180006641  call    memmove
0x180006646  mov     ecx, r14d
0x180006649  imul    ecx, [rbx+18h]
0x18000664d  test    [rbx+2Ch], r12d
0x180006651  jz      short loc_180006659
0x180006653  add     ecx, 7
0x180006656  and     ecx, 0FFFFFFF8h
0x180006659  mov     eax, ecx
0x18000665b  add     rbp, rax
0x18000665e  mov     eax, [rbx+28h]
0x180006661  mov     [rsi+1Ch], eax
0x180006664  cmp     qword ptr [rbx+20h], 0
0x180006669  jz      short loc_1800066AD
0x18000666b  mov     eax, ebp
0x18000666d  mov     ecx, r14d
0x180006670  sub     eax, r15d
0x180006673  mov     [rsi+18h], eax
0x180006676  imul    ecx, [rbx+28h]
0x18000667a  test    [rbx+2Ch], r12d
0x18000667e  jz      short loc_180006686
0x180006680  add     ecx, 7
0x180006683  and     ecx, 0FFFFFFF8h
0x180006686  mov     rdx, [rbx+20h]; Src
0x18000668a  mov     r8d, ecx; Size
0x18000668d  mov     rcx, rbp; void *
0x180006690  call    memmove
0x180006695  mov     ecx, r14d
0x180006698  imul    ecx, [rbx+28h]
0x18000669c  test    [rbx+2Ch], r12d
0x1800066a0  jz      short loc_1800066A8
0x1800066a2  add     ecx, 7
0x1800066a5  and     ecx, 0FFFFFFF8h
0x1800066a8  mov     eax, ecx
0x1800066aa  add     rbp, rax
0x1800066ad  mov     eax, [rbx+2Ch]
0x1800066b0  mov     [rsi+20h], eax
0x1800066b3  cmp     dword ptr [rdi], 200h
0x1800066b9  jnz     short loc_1800066E4
0x1800066bb  mov     eax, [rdi+40h]
0x1800066be  mov     [rsi+28h], eax
0x1800066c1  cmp     qword ptr [rdi+38h], 0
0x1800066c6  jz      short loc_1800066E4
0x1800066c8  mov     eax, ebp
0x1800066ca  mov     rcx, rbp; void *
0x1800066cd  sub     eax, r15d
0x1800066d0  mov     [rsi+24h], eax
0x1800066d3  imul    r14d, [rdi+40h]
0x1800066d8  mov     rdx, [rdi+38h]; Src
0x1800066dc  mov     r8d, r14d; Size
0x1800066df  call    memmove
0x1800066e4  xor     eax, eax
0x1800066e6  jmp     loc_180006506
```

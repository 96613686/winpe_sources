# Pku2uMarshallApReply(KERB_AP_REPLY *,KERB_ENCRYPTED_AP_REPLY *,KERB_ENCRYPTION_KEY *,uchar * *,ulong *)

- ea: `0x180005a80`
- end: `0x180006246`
- name: `?Pku2uMarshallApReply@@YAJPEAUKERB_AP_REPLY@@PEAUKERB_ENCRYPTED_AP_REPLY@@PEAUKERB_ENCRYPTION_KEY@@PEAPEAEPEAK@Z`
- size: `1990`
- prototype: `__int64 __fastcall(struct KERB_AP_REPLY *, struct KERB_ENCRYPTED_AP_REPLY *, struct KERB_ENCRYPTION_KEY *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005840`
- `0x18001cc90`

## callees

- `0x1800057f0`
- `0x180005a80`
- `0x180007dc8`
- `0x180018870`
- `0x18001a448`
- `0x180021a54`
- `0x180023ce0`
- `0x180023d9c`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `MSASN1!ASN1_CreateEncoder` at `0x180005b3d`
- `MSASN1!ASN1_CreateEncoder` at `0x180005f24`
- `MSASN1!ASN1_CreateEncoder` at `0x180005b3d`
- `MSASN1!ASN1_CreateEncoder` at `0x180005f24`
- `MSASN1!ASN1_CloseEncoder` at `0x180005c9b`
- `MSASN1!ASN1_CloseEncoder` at `0x18000607b`
- `MSASN1!ASN1_CloseEncoder` at `0x180005c9b`
- `MSASN1!ASN1_CloseEncoder` at `0x18000607b`
- `MSASN1!ASN1_Encode` at `0x180005ba6`
- `MSASN1!ASN1_Encode` at `0x180005f8a`
- `MSASN1!ASN1_Encode` at `0x180005ba6`
- `MSASN1!ASN1_Encode` at `0x180005f8a`
- `MSASN1!ASN1_FreeEncoded` at `0x180005c85`
- `MSASN1!ASN1_FreeEncoded` at `0x18000605e`
- `MSASN1!ASN1_FreeEncoded` at `0x180005c85`
- `MSASN1!ASN1_FreeEncoded` at `0x18000605e`
- `MSASN1!ASN1_CreateModule` at `0x180005b15`
- `MSASN1!ASN1_CreateModule` at `0x180005efc`
- `MSASN1!ASN1_CreateModule` at `0x180005b15`
- `MSASN1!ASN1_CreateModule` at `0x180005efc`
- `cryptdll!CDLocateCSystem` at `0x180005d0b`
- `cryptdll!CDLocateCSystem` at `0x180005dba`
- `cryptdll!CDLocateCSystem` at `0x180005d0b`
- `cryptdll!CDLocateCSystem` at `0x180005dba`

## string_xrefs

- `0x180005cc4`: `onecore\ds\security\protocols\pku2u\tick.cxx`
- `0x180005d6b`: `onecore\ds\security\protocols\pku2u\tick.cxx`
- `0x180005e5e`: `onecore\ds\security\protocols\pku2u\tick.cxx`
- `0x18000609c`: `onecore\ds\security\protocols\pku2u\tick.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uMarshallApReply(
        struct KERB_AP_REPLY *a1,
        struct KERB_ENCRYPTED_AP_REPLY *a2,
        struct KERB_ENCRYPTION_KEY *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int v8; // r12d
  void *v9; // r13
  __int64 Module; // rax
  unsigned int v11; // eax
  PVOID *v12; // r10
  int v13; // edi
  int v14; // r14d
  int v15; // eax
  size_t v16; // r14
  void *v17; // rbx
  __int64 v18; // rcx
  void *v19; // rax
  unsigned int v20; // ebx
  __int64 v21; // rcx
  unsigned int v22; // r14d
  void *v23; // rax
  __int64 v24; // rcx
  void *v25; // rsi
  __int64 v26; // r10
  int v27; // eax
  int v28; // ebx
  unsigned int v29; // esi
  __int64 v30; // rax
  unsigned int v31; // eax
  PVOID *v32; // r10
  int v33; // eax
  size_t v34; // rsi
  void *v35; // rbx
  __int64 v36; // rcx
  void *v37; // rax
  unsigned int v38; // eax
  int v39; // edx
  int v40; // eax
  unsigned int v41; // ecx
  unsigned int v42; // edi
  struct gss_OID_desc_struct *v43; // rcx
  unsigned __int8 *v44; // rbx
  unsigned __int8 *v45; // rax
  void *v46; // rcx
  __int64 v48; // [rsp+50h] [rbp-20h] BYREF
  __int64 v49; // [rsp+58h] [rbp-18h] BYREF
  __int64 v50; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 *v51; // [rsp+68h] [rbp-8h] BYREF
  void *v52; // [rsp+B0h] [rbp+40h]

  v52 = 0;
  v48 = 0;
  v8 = 0;
  v9 = 0;
  if ( fKRB5ModuleStarted )
  {
    Module = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               49,
               off_180047350,
               off_1800471C0,
               off_180047030,
               qword_180049F80,
               846556016);
    PKU2UMSG_Module = Module;
  }
  v11 = ASN1_CreateEncoder(Module, &v48, 0, 0, 0);
  if ( !v11 )
  {
    v15 = ASN1_Encode(v48, a2, 37, 16, 0, 0);
    if ( v15 < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
          &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
          (unsigned int)v15);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_12;
    }
    v13 = 60;
    v16 = *(unsigned int *)(v48 + 28);
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
    {
      v17 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))((unsigned int)v16);
    }
    else
    {
      v19 = (void *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))((unsigned int)v16);
      v17 = v19;
      if ( v19 )
      {
        memset_0(v19, 0, v16);
        v52 = v17;
        goto LABEL_19;
      }
    }
    v52 = v17;
    if ( !v17 )
    {
      v18 = v48;
      v14 = 60;
LABEL_20:
      ASN1_FreeEncoded(v18, *(_QWORD *)(v18 + 16));
      goto LABEL_21;
    }
LABEL_19:
    v14 = 0;
    memcpy_0(v17, *(const void **)(v48 + 16), *(unsigned int *)(v48 + 28));
    v18 = v48;
    v8 = *(_DWORD *)(v48 + 28);
    goto LABEL_20;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
LABEL_12:
    v13 = 60;
    v14 = 60;
    goto LABEL_22;
  }
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v11);
  v13 = 60;
  v14 = 60;
LABEL_21:
  v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_22:
  if ( v48 )
  {
    ASN1_CloseEncoder();
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v14 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_dsd(
        (unsigned int)v12[2],
        32,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        v14,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        41);
    v20 = KerbMapKerbError(v14);
    goto LABEL_94;
  }
  v21 = *(unsigned int *)a3;
  v51 = 0;
  if ( (int)CDLocateCSystem(v21, &v51) < 0 )
  {
    v13 = 14;
LABEL_32:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        v13,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        58);
LABEL_35:
    v20 = KerbMapKerbError(v13);
LABEL_94:
    v25 = v52;
    goto LABEL_95;
  }
  v22 = -*((_DWORD *)v51 + 1) & (v8 + *((_DWORD *)v51 + 1) + *((_DWORD *)v51 + 4) - 1);
  v23 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v22);
  *((_QWORD *)a1 + 4) = v23;
  if ( !v23 )
    goto LABEL_32;
  *((_DWORD *)a1 + 6) = v22;
  v24 = *(unsigned int *)a3;
  v50 = 0;
  v51 = 0;
  if ( (int)CDLocateCSystem(v24, &v50) < 0 )
  {
    v25 = v52;
    v13 = 14;
    goto LABEL_42;
  }
  v26 = v50;
  if ( *(_DWORD *)(v50 + 12) <= *((_DWORD *)a3 + 2) )
  {
    *((_DWORD *)a1 + 3) = *(_DWORD *)a3;
    v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int8 **))(v26 + 40))(
            *((_QWORD *)a3 + 2),
            *((unsigned int *)a3 + 2),
            12,
            &v51);
    v25 = v52;
    if ( v27 < 0 )
      goto LABEL_42;
    v28 = (*(__int64 (__fastcall **)(unsigned __int8 *, void *, _QWORD, _QWORD, char *))(v50 + 48))(
            v51,
            v52,
            v8,
            *((_QWORD *)a1 + 4),
            (char *)a1 + 24);
    (*(void (__fastcall **)(unsigned __int8 **))(v50 + 64))(&v51);
    if ( v28 < 0 )
      goto LABEL_42;
    v29 = 0;
    v49 = 0;
    if ( fKRB5ModuleStarted )
    {
      v30 = PKU2UMSG_Module;
    }
    else
    {
      fKRB5ModuleStarted = 1;
      v30 = ASN1_CreateModule(
              0x10000,
              1024,
              4096,
              49,
              off_180047350,
              off_1800471C0,
              off_180047030,
              qword_180049F80,
              846556016);
      PKU2UMSG_Module = v30;
    }
    v31 = ASN1_CreateEncoder(v30, &v49, 0, 0, 0);
    if ( v31 )
    {
      v32 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v31);
LABEL_65:
        v32 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_66;
      }
      goto LABEL_66;
    }
    v33 = ASN1_Encode(v49, a1, 36, 16, 0, 0);
    if ( v33 < 0 )
    {
      v32 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
          &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
          (unsigned int)v33);
        goto LABEL_65;
      }
LABEL_66:
      if ( v49 )
      {
        ASN1_CloseEncoder();
        v32 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v13 )
      {
        if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 1) != 0 )
          WPP_SF_dsd(
            (unsigned int)v32[2],
            35,
            (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
            v13,
            (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
            89);
        goto LABEL_35;
      }
      v38 = (_DWORD)pku2u_global_oids + 4;
      *a5 = 0;
      if ( v38 < 4 )
      {
        *a5 = -1;
        v20 = -1073741675;
        goto LABEL_94;
      }
      v39 = v38 + v29;
      if ( v38 + v29 < v38 )
      {
        *a5 = -1;
        v20 = -1073741675;
        goto LABEL_94;
      }
      if ( v39 >= 128 )
      {
        if ( v39 >= 256 )
        {
          if ( v39 >= 0x10000 )
            v40 = (v39 >= 0x1000000) + 5;
          else
            v40 = 4;
        }
        else
        {
          v40 = 3;
        }
      }
      else
      {
        v40 = 2;
      }
      v41 = v39 + v40;
      v42 = -1;
      if ( v39 + v40 >= (unsigned int)v39 )
        v42 = v39 + v40;
      v20 = v41 < v39 ? 0xC0000095 : 0;
      *a5 = v42;
      if ( v41 < v39 )
        goto LABEL_94;
      if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      {
        v44 = (unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(v42);
      }
      else
      {
        v45 = (unsigned __int8 *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))(v42);
        v44 = v45;
        if ( v45 )
        {
          memset_0(v45, 0, v42);
          *a4 = v44;
          goto LABEL_93;
        }
      }
      *a4 = v44;
      if ( !v44 )
      {
        v20 = -1073741801;
        goto LABEL_94;
      }
LABEL_93:
      v51 = v44;
      g_make_token_header(v43, v29, &v51, 512);
      memcpy_0(v51, v9, v29);
      v20 = 0;
      goto LABEL_94;
    }
    v34 = *(unsigned int *)(v49 + 28);
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
    {
      v35 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))((unsigned int)v34);
    }
    else
    {
      v37 = (void *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))((unsigned int)v34);
      v35 = v37;
      if ( v37 )
      {
        memset_0(v37, 0, v34);
        v9 = v35;
        goto LABEL_63;
      }
    }
    v9 = v35;
    if ( !v35 )
    {
      v36 = v49;
      v29 = 0;
LABEL_64:
      ASN1_FreeEncoded(v36, *(_QWORD *)(v36 + 16));
      goto LABEL_65;
    }
LABEL_63:
    v13 = 0;
    memcpy_0(v35, *(const void **)(v49 + 16), *(unsigned int *)(v49 + 28));
    v36 = v49;
    v29 = *(_DWORD *)(v49 + 28);
    goto LABEL_64;
  }
  v25 = v52;
LABEL_42:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
      v13,
      (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
      73);
  v20 = KerbMapKerbError(v13);
LABEL_95:
  v46 = (void *)*((_QWORD *)a1 + 4);
  if ( v46 )
  {
    Pku2uFree(v46);
    *((_QWORD *)a1 + 4) = 0;
  }
  if ( v25 )
    Pku2uFree(v25);
  if ( v9 )
    Pku2uFree(v9);
  return v20;
}

```

## disassembly

```asm
0x180005a80  mov     [rsp-38h+arg_8], rbx
0x180005a85  mov     [rsp-38h+arg_18], r9
0x180005a8a  push    rbp
0x180005a8b  push    rsi
0x180005a8c  push    rdi
0x180005a8d  push    r12
0x180005a8f  push    r13
0x180005a91  push    r14
0x180005a93  push    r15
0x180005a95  mov     rbp, rsp
0x180005a98  sub     rsp, 70h
0x180005a9c  xor     edi, edi
0x180005a9e  lea     rax, qword_180049F80
0x180005aa5  cmp     cs:?fKRB5ModuleStarted@@3HA, edi; int fKRB5ModuleStarted
0x180005aab  mov     rsi, r8
0x180005aae  mov     rbx, rdx
0x180005ab1  mov     [rbp+arg_0], rdi
0x180005ab5  mov     r15, rcx
0x180005ab8  mov     [rbp+var_20], rdi
0x180005abc  mov     r12d, edi
0x180005abf  lea     rcx, off_180047030
0x180005ac6  mov     r13d, edi
0x180005ac9  lea     rdx, off_1800471C0
0x180005ad0  lea     r8, off_180047350
0x180005ad7  jnz     short loc_180005B24
0x180005ad9  mov     [rsp+70h+var_30], 32756B70h
0x180005ae1  mov     r9d, 31h ; '1'
0x180005ae7  mov     [rsp+70h+var_38], rax
0x180005aec  mov     [rsp+70h+var_40], rcx
0x180005af1  mov     ecx, 10000h
0x180005af6  mov     [rsp+70h+var_48], rdx
0x180005afb  mov     edx, 400h
0x180005b00  mov     [rsp+70h+var_50], r8
0x180005b05  mov     r8d, 1000h
0x180005b0b  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x180005b15  call    cs:__imp_ASN1_CreateModule
0x180005b1b  mov     cs:PKU2UMSG_Module, rax
0x180005b22  jmp     short loc_180005B2B
0x180005b24  mov     rax, cs:PKU2UMSG_Module
0x180005b2b  xor     r9d, r9d
0x180005b2e  mov     [rsp+70h+var_50], rdi
0x180005b33  xor     r8d, r8d
0x180005b36  lea     rdx, [rbp+var_20]
0x180005b3a  mov     rcx, rax
0x180005b3d  call    cs:__imp_ASN1_CreateEncoder
0x180005b43  lea     r14, WPP_GLOBAL_Control
0x180005b4a  test    eax, eax
0x180005b4c  jz      short loc_180005B8A
0x180005b4e  mov     r10, cs:WPP_GLOBAL_Control
0x180005b55  cmp     r10, r14
0x180005b58  jz      loc_180005BE2
0x180005b5e  test    byte ptr [r10+1Ch], 1
0x180005b63  jz      short loc_180005BE2
0x180005b65  mov     rcx, [r10+10h]
0x180005b69  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180005b70  mov     edx, 4Dh ; 'M'
0x180005b75  mov     r9d, eax
0x180005b78  call    WPP_SF_d
0x180005b7d  mov     edi, 3Ch ; '<'
0x180005b82  mov     r14d, edi
0x180005b85  jmp     loc_180005C8B
0x180005b8a  mov     rcx, [rbp+var_20]
0x180005b8e  mov     r9d, 10h
0x180005b94  mov     dword ptr [rsp+70h+var_48], edi
0x180005b98  mov     r8d, 25h ; '%'
0x180005b9e  mov     rdx, rbx
0x180005ba1  mov     [rsp+70h+var_50], rdi
0x180005ba6  call    cs:__imp_ASN1_Encode
0x180005bac  test    eax, eax
0x180005bae  jns     short loc_180005BEF
0x180005bb0  mov     r10, cs:WPP_GLOBAL_Control
0x180005bb7  cmp     r10, r14
0x180005bba  jz      short loc_180005BE2
0x180005bbc  test    byte ptr [r10+1Ch], 1
0x180005bc1  jz      short loc_180005BE2
0x180005bc3  mov     rcx, [r10+10h]
0x180005bc7  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180005bce  mov     edx, 4Eh ; 'N'
0x180005bd3  mov     r9d, eax
0x180005bd6  call    WPP_SF_d
0x180005bdb  mov     r10, cs:WPP_GLOBAL_Control
0x180005be2  mov     edi, 3Ch ; '<'
0x180005be7  mov     r14d, edi
0x180005bea  jmp     loc_180005C92
0x180005bef  mov     rax, [rbp+var_20]
0x180005bf3  mov     edi, 3Ch ; '<'
0x180005bf8  mov     r14d, [rax+1Ch]
0x180005bfc  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180005c03  cmp     dword ptr [rax+0D0h], 1
0x180005c0a  jnz     short loc_180005C37
0x180005c0c  mov     rax, [rax+0F0h]
0x180005c13  mov     ecx, r14d
0x180005c16  mov     rax, [rax+180h]
0x180005c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c22  mov     rbx, rax
0x180005c25  mov     [rbp+arg_0], rbx
0x180005c29  test    rbx, rbx
0x180005c2c  jnz     short loc_180005C62
0x180005c2e  mov     rcx, [rbp+var_20]
0x180005c32  mov     r14d, edi
0x180005c35  jmp     short loc_180005C81
0x180005c37  mov     rax, [rax+0F8h]
0x180005c3e  mov     ecx, r14d
0x180005c41  mov     rax, [rax]
0x180005c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c49  mov     rbx, rax
0x180005c4c  test    rax, rax
0x180005c4f  jz      short loc_180005C25
0x180005c51  mov     r8, r14; Size
0x180005c54  xor     edx, edx; Val
0x180005c56  mov     rcx, rax; void *
0x180005c59  call    memset_0
0x180005c5e  mov     [rbp+arg_0], rbx
0x180005c62  mov     rdx, [rbp+var_20]
0x180005c66  xor     r14d, r14d
0x180005c69  mov     rcx, rbx; void *
0x180005c6c  mov     r8d, [rdx+1Ch]; Size
0x180005c70  mov     rdx, [rdx+10h]; Src
0x180005c74  call    memcpy_0
0x180005c79  mov     rcx, [rbp+var_20]
0x180005c7d  mov     r12d, [rcx+1Ch]
0x180005c81  mov     rdx, [rcx+10h]
0x180005c85  call    cs:__imp_ASN1_FreeEncoded
0x180005c8b  mov     r10, cs:WPP_GLOBAL_Control
0x180005c92  mov     rcx, [rbp+var_20]
0x180005c96  test    rcx, rcx
0x180005c99  jz      short loc_180005CA8
0x180005c9b  call    cs:__imp_ASN1_CloseEncoder
0x180005ca1  mov     r10, cs:WPP_GLOBAL_Control
0x180005ca8  test    r14d, r14d
0x180005cab  jz      short loc_180005CFE
0x180005cad  lea     rbx, WPP_GLOBAL_Control
0x180005cb4  cmp     r10, rbx
0x180005cb7  jz      short loc_180005CEC
0x180005cb9  test    byte ptr [r10+1Ch], 1
0x180005cbe  jz      short loc_180005CEC
0x180005cc0  mov     rcx, [r10+10h]
0x180005cc4  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\protocols\\pku2u"...
0x180005ccb  mov     edx, 20h ; ' '
0x180005cd0  mov     dword ptr [rsp+70h+var_48], 729h
0x180005cd8  mov     r9d, r14d
0x180005cdb  mov     [rsp+70h+var_50], rax
0x180005ce0  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180005ce7  call    WPP_SF_dsd
0x180005cec  mov     ecx, r14d; int
0x180005cef  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x180005cf4  mov     ebx, eax
0x180005cf6  xor     r14d, r14d
0x180005cf9  jmp     loc_1800061FC
0x180005cfe  mov     ecx, [rsi]
0x180005d00  lea     rdx, [rbp+var_8]
0x180005d04  xor     r14d, r14d
0x180005d07  mov     [rbp+var_8], r14
0x180005d0b  call    cs:__imp_CDLocateCSystem
0x180005d11  test    eax, eax
0x180005d13  jns     short loc_180005D1C
0x180005d15  mov     edi, 0Eh
0x180005d1a  jmp     short loc_180005D4E
0x180005d1c  mov     rax, [rbp+var_8]
0x180005d20  mov     edx, [rax+4]
0x180005d23  mov     ecx, [rax+10h]
0x180005d26  dec     ecx
0x180005d28  add     ecx, edx
0x180005d2a  neg     edx
0x180005d2c  add     ecx, r12d
0x180005d2f  and     ecx, edx
0x180005d31  mov     r14d, ecx
0x180005d34  mov     edx, ecx; unsigned __int64
0x180005d36  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180005d3d  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180005d42  mov     [r15+20h], rax
0x180005d46  test    rax, rax
0x180005d49  jnz     short loc_180005DA1
0x180005d4b  xor     r14d, r14d
0x180005d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d55  lea     rbx, WPP_GLOBAL_Control
0x180005d5c  cmp     rcx, rbx
0x180005d5f  jz      short loc_180005D93
0x180005d61  test    byte ptr [rcx+1Ch], 1
0x180005d65  jz      short loc_180005D93
0x180005d67  mov     rcx, [rcx+10h]
0x180005d6b  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\protocols\\pku2u"...
0x180005d72  mov     edx, 21h ; '!'
0x180005d77  mov     dword ptr [rsp+70h+var_48], 73Ah
0x180005d7f  mov     r9d, edi
0x180005d82  mov     [rsp+70h+var_50], rax
0x180005d87  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180005d8e  call    WPP_SF_dsd
0x180005d93  mov     ecx, edi; int
0x180005d95  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x180005d9a  mov     ebx, eax
0x180005d9c  jmp     loc_1800061FC
0x180005da1  mov     [r15+18h], r14d
0x180005da5  lea     rbx, [r15+18h]
0x180005da9  mov     ecx, [rsi]
0x180005dab  lea     rdx, [rbp+var_10]
0x180005daf  xor     r14d, r14d
0x180005db2  mov     [rbp+var_10], r14
0x180005db6  mov     [rbp+var_8], r14
0x180005dba  call    cs:__imp_CDLocateCSystem
0x180005dc0  test    eax, eax
0x180005dc2  jns     short loc_180005DCF
0x180005dc4  mov     rsi, [rbp+arg_0]
0x180005dc8  mov     edi, 0Eh
0x180005dcd  jmp     short loc_180005E41
0x180005dcf  mov     r10, [rbp+var_10]
0x180005dd3  mov     eax, [rsi+8]
0x180005dd6  cmp     [r10+0Ch], eax
0x180005dda  jbe     short loc_180005DE2
0x180005ddc  mov     rsi, [rbp+arg_0]
0x180005de0  jmp     short loc_180005E41
0x180005de2  mov     eax, [rsi]
0x180005de4  lea     r9, [rbp+var_8]
0x180005de8  mov     [r15+0Ch], eax
0x180005dec  mov     r8d, 0Ch
0x180005df2  mov     edx, [rsi+8]
0x180005df5  mov     rcx, [rsi+10h]
0x180005df9  mov     rax, [r10+28h]
0x180005dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e02  mov     rsi, [rbp+arg_0]
0x180005e06  test    eax, eax
0x180005e08  js      short loc_180005E41
0x180005e0a  mov     rax, [rbp+var_10]
0x180005e0e  mov     r8d, r12d
0x180005e11  mov     r9, [r15+20h]
0x180005e15  mov     rdx, rsi
0x180005e18  mov     rcx, [rbp+var_8]
0x180005e1c  mov     [rsp+70h+var_50], rbx
0x180005e21  mov     rax, [rax+30h]
0x180005e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e2a  mov     rcx, [rbp+var_10]
0x180005e2e  mov     ebx, eax
0x180005e30  mov     rax, [rcx+40h]
0x180005e34  lea     rcx, [rbp+var_8]
0x180005e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e3d  test    ebx, ebx
0x180005e3f  jns     short loc_180005E94
0x180005e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e48  lea     rbx, WPP_GLOBAL_Control
0x180005e4f  cmp     rcx, rbx
0x180005e52  jz      short loc_180005E86
0x180005e54  test    byte ptr [rcx+1Ch], 1
0x180005e58  jz      short loc_180005E86
0x180005e5a  mov     rcx, [rcx+10h]
0x180005e5e  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\protocols\\pku2u"...
0x180005e65  mov     edx, 22h ; '"'
0x180005e6a  mov     dword ptr [rsp+70h+var_48], 749h
0x180005e72  mov     r9d, edi
0x180005e75  mov     [rsp+70h+var_50], rax
0x180005e7a  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180005e81  call    WPP_SF_dsd
0x180005e86  mov     ecx, edi; int
0x180005e88  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x180005e8d  mov     ebx, eax
0x180005e8f  jmp     loc_180006200
0x180005e94  cmp     cs:?fKRB5ModuleStarted@@3HA, r14d; int fKRB5ModuleStarted
0x180005e9b  mov     esi, r14d
0x180005e9e  mov     [rbp+var_18], r14
0x180005ea2  jnz     short loc_180005F0B
0x180005ea4  mov     [rsp+70h+var_30], 32756B70h
0x180005eac  lea     rax, qword_180049F80
0x180005eb3  mov     [rsp+70h+var_38], rax
0x180005eb8  mov     edx, 400h
0x180005ebd  lea     rax, off_180047030
0x180005ec4  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x180005ece  mov     [rsp+70h+var_40], rax
0x180005ed3  mov     ecx, 10000h
0x180005ed8  lea     rax, off_1800471C0
0x180005edf  mov     r9d, 31h ; '1'
0x180005ee5  mov     [rsp+70h+var_48], rax
0x180005eea  mov     r8d, 1000h
0x180005ef0  lea     rax, off_180047350
0x180005ef7  mov     [rsp+70h+var_50], rax
0x180005efc  call    cs:__imp_ASN1_CreateModule
0x180005f02  mov     cs:PKU2UMSG_Module, rax
0x180005f09  jmp     short loc_180005F12
0x180005f0b  mov     rax, cs:PKU2UMSG_Module
0x180005f12  xor     r9d, r9d
0x180005f15  mov     [rsp+70h+var_50], r14
0x180005f1a  xor     r8d, r8d
0x180005f1d  lea     rdx, [rbp+var_18]
0x180005f21  mov     rcx, rax
0x180005f24  call    cs:__imp_ASN1_CreateEncoder
0x180005f2a  test    eax, eax
0x180005f2c  jz      short loc_180005F6D
0x180005f2e  mov     r10, cs:WPP_GLOBAL_Control
0x180005f35  lea     rbx, WPP_GLOBAL_Control
0x180005f3c  cmp     r10, rbx
0x180005f3f  jz      loc_180006072
0x180005f45  test    byte ptr [r10+1Ch], 1
0x180005f4a  jz      loc_180006072
0x180005f50  mov     rcx, [r10+10h]
0x180005f54  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180005f5b  mov     edx, 4Dh ; 'M'
0x180005f60  mov     r9d, eax
0x180005f63  call    WPP_SF_d
0x180005f68  jmp     loc_18000606B
0x180005f6d  mov     rcx, [rbp+var_18]
0x180005f71  mov     r9d, 10h
0x180005f77  mov     dword ptr [rsp+70h+var_48], r14d
  ... truncated ...
```

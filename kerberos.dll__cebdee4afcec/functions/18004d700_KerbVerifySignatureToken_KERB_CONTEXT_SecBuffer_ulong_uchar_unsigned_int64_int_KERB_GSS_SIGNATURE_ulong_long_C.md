# KerbVerifySignatureToken(_KERB_CONTEXT *,_SecBuffer *,ulong,uchar,unsigned __int64,int *,_KERB_GSS_SIGNATURE * *,ulong *,long *,_CRYPTO_SYSTEM * *,unsigned __int64 *)

- ea: `0x18004d700`
- end: `0x18004e374`
- name: `?KerbVerifySignatureToken@@YAJPEAU_KERB_CONTEXT@@PEAU_SecBuffer@@KE_KPEAHPEAPEAU_KERB_GSS_SIGNATURE@@PEAKPEAJPEAPEAU_CRYPTO_SYSTEM@@PEA_K@Z`
- size: `3188`
- prototype: `__int64 __fastcall(struct _KERB_CONTEXT *, struct _SecBuffer *, unsigned int, unsigned __int8, char, int *, struct _KERB_GSS_SIGNATURE **, unsigned int *, int *, struct _CRYPTO_SYSTEM **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18004bd90`
- `0x18004d200`

## callees

- `0x180011520`
- `0x18004d700`
- `0x1800744c3`
- `0x1800744cf`
- `0x180077804`
- `0x18008b70c`
- `0x180090aac`
- `0x180090b50`
- `0x1800f5010`

## import_xrefs

- `cryptdll!CDLocateCSystem` at `0x18004db5d`
- `cryptdll!CDLocateCSystem` at `0x18004df37`
- `cryptdll!CDLocateCSystem` at `0x18004db5d`
- `cryptdll!CDLocateCSystem` at `0x18004df37`

## string_xrefs

- `0x18004d791`: `KerbVerifySignatureToken ContextAttributes %#x\n`
- `0x18004d7a7`: `KerbVerifySignatureToken`
- `0x18004d84c`: `KerbVerifySignatureToken`
- `0x18004d8f0`: `KerbVerifySignatureToken`
- `0x18004d996`: `KerbVerifySignatureToken`
- `0x18004d9c0`: `KerbVerifySignatureToken`
- `0x18004db7e`: `KerbVerifySignatureToken`
- `0x18004dcda`: `KerbVerifySignatureToken`
- `0x18004dd19`: `KerbVerifySignatureToken`
- `0x18004de91`: `KerbVerifySignatureToken`
- `0x18004ded0`: `KerbVerifySignatureToken`
- `0x18004e11f`: `KerbVerifySignatureToken`
- `0x18004e26c`: `KerbVerifySignatureToken`
- `0x18004d83f`: `KerbVerifySignatureToken MechUsed = gss_mech_krb5_u2u\n`
- `0x18004d8e3`: `KerbVerifySignatureToken Signature gss_mech_krb5\n`
- `0x18004d989`: `KerbVerifySignatureToken Signature gss_mech_krb5\n`
- `0x18004d948`: `KerbVerifySignatureToken Signature MechUsed\n`
- `0x18004ddc9`: `bad token header`
- `0x18004e25f`: `bad token id in the header`
- `0x18004de21`: `token header too small`
- `0x18004de38`: `bad EC in token header`
- `0x18004de84`: `KerbVerifySignatureToken acceptor subkey requested but disallowed`

## pseudocode

```c
__int64 __fastcall KerbVerifySignatureToken(
        struct _KERB_CONTEXT *a1,
        struct _SecBuffer *a2,
        int a3,
        unsigned __int8 a4,
        char a5,
        int *a6,
        struct _KERB_GSS_SIGNATURE **a7,
        unsigned int *a8,
        int *a9,
        struct _CRYPTO_SYSTEM **a10,
        unsigned __int64 *a11)
{
  int v11; // ebx
  int *v12; // rdi
  unsigned int *v14; // r12
  unsigned __int8 *pvBuffer; // rdx
  char *v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // edi
  size_t *v21; // r12
  int v22; // ecx
  int v23; // eax
  unsigned int v24; // ebx
  unsigned __int8 v25; // r8
  unsigned __int8 *v26; // rdi
  unsigned int cbBuffer; // r15d
  unsigned int v28; // eax
  bool v29; // cf
  int *v30; // r12
  char *v31; // rax
  unsigned int v32; // r15d
  unsigned __int8 *v33; // rdi
  unsigned int *v34; // rcx
  int *v35; // rdx
  int *v36; // rdx
  int *v37; // rdx
  int *v38; // rdx
  unsigned __int8 v39; // al
  int v40; // eax
  __int64 v41; // r8
  __int64 v42; // rdx
  char *v43; // rcx
  int v44; // eax
  int v45; // eax
  const char *v46; // r9
  __int64 v47; // r8
  __int64 v48; // rdx
  int v49; // edx
  int *v50; // rcx
  int v51; // r8d
  char *v52; // rcx
  int v53; // eax
  int v54; // edx
  __int64 v55; // r8
  int v56; // eax
  char *v57; // r15
  int v58; // ecx
  char *v59; // rax
  char *v60; // rax
  int *v61; // rax
  int *v62; // rax
  char *v63; // rax
  char *v64; // rax
  char *v65; // rax
  size_t v66; // r12
  char *v67; // rax
  char *v68; // rax
  size_t v69; // r8
  char *v70; // rax
  char *v71; // rax
  int v72; // ecx
  char *v73; // rax
  char *v74; // rax
  char *v75; // rax
  int v77[2]; // [rsp+20h] [rbp-79h]
  int v78[2]; // [rsp+20h] [rbp-79h]
  unsigned __int64 Buf1; // [rsp+38h] [rbp-61h] BYREF
  int v81; // [rsp+40h] [rbp-59h] BYREF
  int *v82; // [rsp+48h] [rbp-51h]
  unsigned __int8 *v83; // [rsp+50h] [rbp-49h] BYREF
  int v84; // [rsp+58h] [rbp-41h]
  int v85; // [rsp+5Ch] [rbp-3Dh]
  __int64 v86; // [rsp+60h] [rbp-39h] BYREF
  int v87; // [rsp+68h] [rbp-31h] BYREF
  int *v88; // [rsp+70h] [rbp-29h]
  __int64 v89; // [rsp+78h] [rbp-21h] BYREF
  unsigned int *v90; // [rsp+80h] [rbp-19h]
  unsigned __int64 *v91; // [rsp+88h] [rbp-11h]
  struct _CRYPTO_SYSTEM **v92; // [rsp+90h] [rbp-9h]
  struct _KERB_GSS_SIGNATURE **v93; // [rsp+98h] [rbp-1h]

  v11 = a3;
  v12 = a6;
  v14 = a8;
  v93 = a7;
  v88 = a9;
  v92 = a10;
  v91 = a11;
  v85 = a3;
  v82 = a6;
  v90 = a8;
  v81 = 0;
  v89 = 0;
  v87 = 0;
  v86 = 0;
  if ( !a4 || (*((_DWORD *)a1 + 48) & 0x600) != 0 )
  {
    v11 = 0;
    v85 = 0;
  }
  KerbTracerT::Log(
    3,
    "KerbVerifySignatureToken",
    663,
    "KerbVerifySignatureToken ContextAttributes %#x\n",
    *((_DWORD *)a1 + 49));
  pvBuffer = (unsigned __int8 *)a2->pvBuffer;
  v83 = pvBuffer;
  if ( *pvBuffer == 96
    && (unsigned int)(*((_DWORD *)a1 + 37) - 17) <= 1
    && (*((_DWORD *)a1 + 49) & 0x400) != 0
    && (unsigned int)(*((_DWORD *)a1 + 97) - 17) > 1 )
  {
    *v12 = 1;
  }
  v17 = (char *)a1 + 136;
  v18 = 388;
  v19 = 388;
  if ( !*v12 )
    v19 = 148;
  if ( *(_DWORD *)((char *)a1 + v19) != 17 )
  {
    if ( !*v12 )
      v18 = 148;
    if ( *(_DWORD *)((char *)a1 + v18) != 18 )
    {
      v20 = 0;
      if ( (*((_BYTE *)a1 + 196) & 0x10) != 0 )
      {
        KerbTracerT::Log(25, "KerbVerifySignatureToken", 683, "KerbVerifySignatureToken MechUsed = gss_mech_krb5_u2u\n");
        v21 = &dword_1801400D0;
      }
      else
      {
        v21 = &dword_1801400A0;
      }
      v22 = v11 + a2->cbBuffer;
      v23 = 513;
      LODWORD(Buf1) = v22;
      if ( !a4 )
        v23 = 257;
      v84 = v23;
      v24 = -2146893048;
      if ( !(unsigned int)g_verify_token_header((struct gss_OID_desc_struct *)v21, &v81, &v83, v23, v22) )
      {
        v20 = -2146893048;
        if ( (*((_DWORD *)a1 + 48) & 0x200) != 0 )
        {
          v83 = (unsigned __int8 *)a2->pvBuffer;
          if ( (unsigned int)g_verify_token_header((struct gss_OID_desc_struct *)&oids, &v81, &v83, v84, Buf1) )
          {
            KerbTracerT::Log(3, "KerbVerifySignatureToken", 722, "KerbVerifySignatureToken Signature gss_mech_krb5\n");
            v20 = 0;
          }
        }
      }
      v25 = a4;
      if ( a4 && v20 < 0 )
      {
        v26 = (unsigned __int8 *)a2->pvBuffer;
        cbBuffer = a2->cbBuffer;
        v83 = v26;
        v85 = 0;
        if ( (unsigned int)g_verify_token_header((struct gss_OID_desc_struct *)v21, &v81, &v83, v84, cbBuffer) )
        {
          KerbTracerT::Log(3, "KerbVerifySignatureToken", 748, "KerbVerifySignatureToken Signature MechUsed\n");
        }
        else if ( (*((_DWORD *)a1 + 48) & 0x200) != 0 )
        {
          v83 = v26;
          if ( (unsigned int)g_verify_token_header((struct gss_OID_desc_struct *)&oids, &v81, &v83, v84, cbBuffer) )
            KerbTracerT::Log(3, "KerbVerifySignatureToken", 772, "KerbVerifySignatureToken Signature gss_mech_krb5\n");
        }
        v25 = a4;
      }
      if ( !v81 )
      {
        KerbTracerT::Log(1, "KerbVerifySignatureToken", 784, "Bad Signature");
LABEL_34:
        v24 = -2146893041;
        goto LABEL_216;
      }
      v28 = v81 - v85;
      if ( v25 )
        v29 = v28 < 0x1E;
      else
        v29 = v28 < 0x16;
      if ( v29 )
        goto LABEL_216;
      v30 = v82;
      v31 = (char *)a1 + 136;
      if ( *v82 )
        v31 = (char *)a1 + 376;
      switch ( *((_DWORD *)v31 + 3) )
      {
        case 0xFFFFFF79:
          v32 = -136;
          goto LABEL_47;
        case 0xFFFFFF7B:
          v32 = -134;
          goto LABEL_47;
        case 1:
        case 3:
          v32 = -132;
          goto LABEL_47;
        case 0x17:
          v32 = -140;
          goto LABEL_47;
        case 0x18:
          v32 = -141;
LABEL_47:
          v33 = v83;
          if ( v83[1] )
          {
            KerbTracerT::Log(1, "KerbVerifySignatureToken", 844, "Not KERB_GSS_SIG_SECOND");
            goto LABEL_34;
          }
          if ( *v83 )
          {
            switch ( *v83 )
            {
              case 1u:
                v34 = v90;
                v37 = v88;
                *v90 = 1;
                *v37 = -135;
                break;
              case 2u:
                v34 = v90;
                v36 = v88;
                *v90 = 3;
                *v36 = -133;
                break;
              case 0x11u:
                v34 = v90;
                v35 = v88;
                *v90 = 0;
                *v35 = -138;
                break;
              default:
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    16,
                    WPP_a1119ca399823668ae16bae9ee423caf_Traceguids,
                    *v83);
                  v24 = -2146893041;
                  goto LABEL_216;
                }
                goto LABEL_34;
            }
          }
          else
          {
            v34 = v90;
            v38 = v88;
            *v90 = 2;
            *v38 = -134;
          }
          if ( !v25 )
          {
            if ( *(_DWORD *)(v33 + 2) == -1 )
              goto LABEL_65;
            goto LABEL_83;
          }
          v39 = v33[3];
          if ( v39 == 0xFF )
          {
            if ( v33[2] == 0xFF )
            {
              *v34 = -2147483647;
              goto LABEL_64;
            }
          }
          else if ( !v39 )
          {
            if ( v32 + 141 <= 1 )
            {
              if ( v33[2] != 16 )
              {
                KerbTracerT::Log(1, "KerbVerifySignatureToken", 918, "Trying to mix encryption types");
                goto LABEL_34;
              }
            }
            else if ( ((v32 + 136) & 0xFFFFFFFD) != 0 )
            {
              if ( v32 != -132 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    17,
                    WPP_a1119ca399823668ae16bae9ee423caf_Traceguids,
                    v33[2],
                    v32);
                  v24 = -2146893041;
                  goto LABEL_216;
                }
                goto LABEL_34;
              }
              if ( v33[2] )
              {
                KerbTracerT::Log(1, "KerbVerifySignatureToken", 900, "Trying to mix encryption types");
                goto LABEL_34;
              }
            }
            else if ( v33[2] != 17 )
            {
              KerbTracerT::Log(1, "KerbVerifySignatureToken", 909, "Trying to mix encryption types");
              goto LABEL_34;
            }
LABEL_64:
            if ( *((_WORD *)v33 + 2) == 0xFFFF )
            {
LABEL_65:
              v40 = CDLocateCSystem(v32, &v86);
              v24 = v40;
              if ( v40 < 0 )
              {
                v41 = 948;
                goto LABEL_67;
              }
              if ( *v30 )
              {
                v42 = *((unsigned int *)a1 + 98);
                v43 = (char *)a1 + 376;
              }
              else
              {
                v42 = *((unsigned int *)a1 + 38);
                v43 = (char *)a1 + 136;
              }
              v44 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64 *))(v86 + 40))(
                      *((_QWORD *)v43 + 3),
                      v42,
                      0,
                      &v89);
              v24 = v44;
              if ( v44 < 0 )
              {
                KerbTracerT::Log(1, "KerbVerifySignatureToken", 965, "failed to initialize %#x\n", v44);
                goto LABEL_216;
              }
              v45 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64))(v86 + 88))(
                      1,
                      v89,
                      v33 + 14,
                      8);
              v24 = v45;
              if ( v45 < 0 )
              {
                v46 = "failed to control %#x\n";
                v47 = 982;
LABEL_91:
                v78[0] = v45;
                KerbTracerT::Log(1, "KerbVerifySignatureToken", v47, v46, *(_QWORD *)v78);
                goto LABEL_216;
              }
              v87 = 8;
              v45 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, __int64, unsigned __int8 *, int *))(v86 + 56))(
                      v89,
                      v33 + 6,
                      8,
                      v33 + 6,
                      &v87);
              v24 = v45;
              if ( v45 < 0 )
              {
                v46 = "failed to decrypt %#x\n";
                v47 = 1003;
                goto LABEL_91;
              }
              v55 = a4;
              goto LABEL_136;
            }
LABEL_83:
            KerbTracerT::Log(1, "KerbVerifySignatureToken", 939, "Bad filler");
            goto LABEL_34;
          }
          KerbTracerT::Log(1, "KerbVerifySignatureToken", 885, "Not KERB_GSS_SIG_SECOND");
          goto LABEL_34;
        default:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            if ( *v82 )
              v17 = (char *)a1 + 376;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              WPP_a1119ca399823668ae16bae9ee423caf_Traceguids,
              *((unsigned int *)v17 + 3));
          }
          v24 = -1073741595;
          goto LABEL_216;
      }
    }
  }
  v33 = pvBuffer + 2;
  if ( a2->cbBuffer < 0x1C )
  {
    KerbTracerT::Log(1, "KerbVerifySignatureToken", 1019, "bad token header");
LABEL_215:
    v24 = -2146893048;
    goto LABEL_216;
  }
  if ( *pvBuffer != (a4 != 0) + 4 || pvBuffer[1] != 4 )
  {
    KerbTracerT::Log(1, "KerbVerifySignatureToken", 1026, "bad token id in the header");
    goto LABEL_215;
  }
  if ( a4 )
  {
    v49 = pvBuffer[5] + (pvBuffer[4] << 8);
    if ( (*v33 & 2) != 0 )
    {
      if ( a2->cbBuffer < v49 + 60 )
      {
        KerbTracerT::Log(1, "KerbVerifySignatureToken", 1038, "token header too small");
        goto LABEL_215;
      }
    }
    else if ( v49 != 12 )
    {
      KerbTracerT::Log(1, "KerbVerifySignatureToken", 1047, "bad EC in token header");
      goto LABEL_34;
    }
  }
  if ( v33[1] != 0xFF || !a4 && *(_DWORD *)(v33 + 2) != -1 )
  {
    KerbTracerT::Log(1, "KerbVerifySignatureToken", 1061, "bad filler");
    goto LABEL_34;
  }
  if ( (*((_DWORD *)a1 + 49) & 0x400) != 0 && (*v33 & 4) == 0 )
  {
    if ( (unsigned int)(*((_DWORD *)a1 + 97) - 17) <= 1 )
    {
      v50 = v82;
      *v82 = 1;
      goto LABEL_118;
    }
    KerbTracerT::Log(
      2,
      "KerbVerifySignatureToken",
      1077,
      "KerbVerifySignatureToken acceptor subkey requested but disallowed");
  }
  v50 = v82;
LABEL_118:
  v51 = *v50;
  v52 = (char *)a1 + 136;
  if ( v51 )
    v52 = (char *)a1 + 376;
  if ( *((_DWORD *)v52 + 3) == 17 )
  {
    v32 = -148;
    v53 = -150;
    v54 = 15;
  }
  else
  {
    if ( *((_DWORD *)v52 + 3) != 18 )
    {
      if ( v51 )
        v17 = (char *)a1 + 376;
      v77[0] = *((_DWORD *)v17 + 3);
      KerbTracerT::Log(1, "KerbVerifySignatureToken", 1093, "unexpected etype %d\n", *(_QWORD *)v77);
      v24 = -2146893054;
      goto LABEL_216;
    }
    v32 = -149;
    v53 = -151;
    v54 = 16;
  }
  if ( (*v33 & 2) == 0 )
    v53 = v54;
  *v88 = v53;
  v40 = CDLocateCSystem(v32, &v86);
  v24 = v40;
  if ( v40 < 0 )
  {
    v41 = 1101;
LABEL_67:
    KerbTracerT::Log(1, "KerbVerifySignatureToken", v41, "Failed to load %d crypt system: 0x%x", v32, v40);
    goto LABEL_216;
  }
  v55 = a4;
  if ( a4 && (*v33 & 2) == 0 )
    *v14 = -2147483647;
  v30 = v82;
LABEL_136:
  v56 = *((_DWORD *)a1 + 48);
  if ( (v56 & 0x400) != 0 || (v57 = (char *)a1 + 184, (v56 & 0x1000C) == 0x10000) )
    v57 = &a5;
  v58 = *v30;
  v59 = (char *)a1 + 136;
  if ( *v30 )
    v59 = (char *)a1 + 376;
  if ( *((_DWORD *)v59 + 3) == 17 )
    goto LABEL_156;
  v60 = (char *)a1 + 136;
  if ( v58 )
    v60 = (char *)a1 + 376;
  if ( *((_DWORD *)v60 + 3) == 18 )
    goto LABEL_156;
  v61 = (int *)((char *)a1 + 136);
  if ( v58 )
    v61 = (int *)((char *)a1 + 376);
  if ( v61[3] >= 1 )
  {
    v62 = (int *)((char *)a1 + 136);
    if ( v58 )
      v62 = (int *)((char *)a1 + 376);
    if ( v62[3] <= 3 )
      goto LABEL_154;
  }
  v63 = (char *)a1 + 136;
  if ( v58 )
    v63 = (char *)a1 + 376;
  if ( *((_DWORD *)v63 + 3) != -132 )
  {
LABEL_156:
    v64 = (char *)a1 + 136;
    if ( v58 )
      v64 = (char *)a1 + 376;
    if ( *((_DWORD *)v64 + 3) == 17 )
      goto LABEL_163;
    v65 = (char *)a1 + 136;
    if ( v58 )
      v65 = (char *)a1 + 376;
    if ( *((_DWORD *)v65 + 3) == 18 )
    {
LABEL_163:
      v48 = *(_QWORD *)v57;
      HIBYTE(Buf1) = *(_QWORD *)v57;
      BYTE3(Buf1) = BYTE4(v48);
      LOBYTE(Buf1) = HIBYTE(v48);
      BYTE1(Buf1) = BYTE6(v48);
      BYTE2(Buf1) = BYTE5(v48);
      BYTE4(Buf1) = BYTE3(v48);
      BYTE5(Buf1) = BYTE2(v48);
      BYTE6(Buf1) = BYTE1(v48);
    }
    else
    {
      LOBYTE(Buf1) = v57[3];
      BYTE1(Buf1) = v57[2];
      BYTE2(Buf1) = v57[1];
      BYTE3(Buf1) = *v57;
    }
  }
  else
  {
LABEL_154:
    LODWORD(Buf1) = *(_DWORD *)v57;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dii(*((_QWORD *)WPP_GLOBAL_Control + 2), v48, v55, (unsigned __int8)v55, Buf1, *(_QWORD *)(v33 + 6));
  v66 = 4;
  if ( (*((_BYTE *)a1 + 192) & 0xC) != 0 )
  {
    v67 = (char *)a1 + 136;
    if ( *v82 )
      v67 = (char *)a1 + 376;
    if ( *((_DWORD *)v67 + 3) == 17 )
      goto LABEL_174;
    v68 = (char *)a1 + 136;
    v69 = 4;
    if ( *v82 )
      v68 = (char *)a1 + 376;
    if ( *((_DWORD *)v68 + 3) == 18 )
LABEL_174:
      v69 = 8;
    if ( memcmp_0(&Buf1, v33 + 6, v69) )
    {
      KerbTracerT::Log(1, "KerbVerifySignatureToken", 1170, "sequence number mismatched\n");
      v24 = -2146893040;
      goto LABEL_216;
    }
  }
  v70 = (char *)a1 + 136;
  if ( *v82 )
    v70 = (char *)a1 + 376;
  if ( *((_DWORD *)v70 + 3) == 17 )
    goto LABEL_183;
  v71 = (char *)a1 + 136;
  if ( *v82 )
    v71 = (char *)a1 + 376;
  if ( *((_DWORD *)v71 + 3) == 18 )
LABEL_183:
    v66 = 8;
  memcpy_0(&Buf1, v33 + 6, v66);
  *v91 = Buf1;
  v72 = *v82;
  v73 = (char *)a1 + 136;
  if ( *v82 )
    v73 = (char *)a1 + 376;
  if ( *((_DWORD *)v73 + 3) == 17 )
    goto LABEL_208;
  v74 = (char *)a1 + 136;
  if ( v72 )
    v74 = (char *)a1 + 376;
  if ( *((_DWORD *)v74 + 3) == 18 )
  {
LABEL_208:
    if ( (*((_BYTE *)a1 + 196) & 2) != 0 && (*v33 & 1) == 0 )
    {
      KerbTracerT::Log(1, "KerbVerifySignatureToken", 1220, "message not sent by acceptor\n");
      goto LABEL_34;
    }
  }
  else
  {
    v75 = (char *)a1 + 136;
    if ( (*((_BYTE *)a1 + 196) & 2) != 0 )
    {
      if ( v72 )
        v75 = (char *)a1 + 376;
      if ( *((_DWORD *)v75 + 3) != 17 )
      {
        if ( v72 )
          v17 = (char *)a1 + 376;
        if ( *((_DWORD *)v17 + 3) != 18 && *(_DWORD *)(v33 + 10) != -1 )
        {
          KerbTracerT::Log(1, "KerbVerifySignatureToken", 1192, "Bad outbound sequence number");
          goto LABEL_34;
        }
      }
    }
    else
    {
      if ( v72 )
        v75 = (char *)a1 + 376;
      if ( *((_DWORD *)v75 + 3) != 17 )
      {
        if ( v72 )
          v17 = (char *)a1 + 376;
        if ( *((_DWORD *)v17 + 3) != 18 && *(_DWORD *)(v33 + 10) )
        {
          KerbTracerT::Log(1, "KerbVerifySignatureToken", 1205, "Bad inbound sequence number");
          goto LABEL_34;
        }
      }
    }
  }
  ++*(_QWORD *)v57;
  if ( v92 )
    *v92 = (struct _CRYPTO_SYSTEM *)v86;
  *v93 = (struct _KERB_GSS_SIGNATURE *)v33;
LABEL_216:
  if ( v89 && v86 )
    (*(void (__fastcall **)(__int64 *))(v86 + 64))(&v89);
  return v24;
}

```

## disassembly

```asm
0x18004d700  mov     [rsp-8+arg_10], rbx
0x18004d705  push    rbp
0x18004d706  push    rsi
0x18004d707  push    rdi
0x18004d708  push    r12
0x18004d70a  push    r13
0x18004d70c  push    r14
0x18004d70e  push    r15
0x18004d710  lea     rbp, [rsp-7]
0x18004d715  sub     rsp, 0A0h
0x18004d71c  mov     rax, [rbp+37h+arg_30]
0x18004d720  mov     ebx, r8d
0x18004d723  mov     rdi, [rbp+37h+arg_28]
0x18004d727  mov     r15, rdx
0x18004d72a  mov     r12, [rbp+37h+arg_38]
0x18004d72e  mov     r13, rcx
0x18004d731  mov     [rbp+37h+var_38], rax
0x18004d735  mov     rax, [rbp+37h+arg_40]
0x18004d73c  mov     [rbp+37h+var_60], rax
0x18004d740  mov     rax, [rbp+37h+arg_48]
0x18004d747  mov     [rbp+37h+var_40], rax
0x18004d74b  mov     rax, [rbp+37h+arg_50]
0x18004d752  mov     [rbp+37h+var_48], rax
0x18004d756  xor     eax, eax
0x18004d758  mov     [rbp+37h+var_A0], r9b
0x18004d75c  mov     [rbp+37h+var_74], ebx
0x18004d75f  mov     [rbp+37h+var_88], rdi
0x18004d763  mov     [rbp+37h+var_50], r12
0x18004d767  mov     [rbp+37h+var_90], eax
0x18004d76a  mov     [rbp+37h+var_58], rax
0x18004d76e  mov     [rbp+37h+var_68], eax
0x18004d771  mov     [rbp+37h+var_70], rax
0x18004d775  test    r9b, r9b
0x18004d778  jz      short loc_18004D786
0x18004d77a  test    dword ptr [rcx+0C0h], 600h
0x18004d784  jz      short loc_18004D78B
0x18004d786  mov     ebx, eax
0x18004d788  mov     [rbp+37h+var_74], eax
0x18004d78b  mov     eax, [rcx+0C4h]
0x18004d791  lea     r9, aKerbverifysign_2; "KerbVerifySignatureToken ContextAttribu"...
0x18004d798  mov     ecx, 3
0x18004d79d  mov     [rsp+0D0h+var_B0], eax
0x18004d7a1  mov     r8d, 297h
0x18004d7a7  lea     rdx, aKerbverifysign_1; "KerbVerifySignatureToken"
0x18004d7ae  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004d7b3  mov     rdx, [r15+8]
0x18004d7b7  mov     [rbp+37h+var_80], rdx
0x18004d7bb  cmp     byte ptr [rdx], 60h ; '`'
0x18004d7be  jnz     short loc_18004D7F1
0x18004d7c0  mov     eax, [r13+94h]
0x18004d7c7  sub     eax, 11h
0x18004d7ca  cmp     eax, 1
0x18004d7cd  ja      short loc_18004D7F1
0x18004d7cf  test    dword ptr [r13+0C4h], 400h
0x18004d7da  jz      short loc_18004D7F1
0x18004d7dc  mov     eax, [r13+184h]
0x18004d7e3  sub     eax, 11h
0x18004d7e6  cmp     eax, 1
0x18004d7e9  jbe     short loc_18004D7F1
0x18004d7eb  mov     dword ptr [rdi], 1
0x18004d7f1  mov     r8d, [rdi]
0x18004d7f4  lea     rsi, [r13+88h]
0x18004d7fb  test    r8d, r8d
0x18004d7fe  lea     r14, [r13+178h]
0x18004d805  mov     ecx, 184h
0x18004d80a  mov     r9d, 94h
0x18004d810  mov     eax, ecx
0x18004d812  cmovz   eax, r9d
0x18004d816  cmp     dword ptr [rax+r13], 11h
0x18004d81b  jz      loc_18004DDBC
0x18004d821  test    r8d, r8d
0x18004d824  cmovz   ecx, r9d
0x18004d828  cmp     dword ptr [rcx+r13], 12h
0x18004d82d  jz      loc_18004DDBC
0x18004d833  xor     edi, edi
0x18004d835  test    byte ptr [r13+0C4h], 10h
0x18004d83d  jz      short loc_18004D866
0x18004d83f  lea     r9, aKerbverifysign_0; "KerbVerifySignatureToken MechUsed = gss"...
0x18004d846  mov     r8d, 2ABh
0x18004d84c  lea     rdx, aKerbverifysign_1; "KerbVerifySignatureToken"
0x18004d853  mov     ecx, 19h
0x18004d858  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004d85d  lea     r12, dword_1801400D0
0x18004d864  jmp     short loc_18004D86D
0x18004d866  lea     r12, dword_1801400A0
0x18004d86d  mov     ecx, [r15]
0x18004d870  lea     r8, [rbp+37h+var_80]; unsigned __int8 **
0x18004d874  add     ecx, ebx
0x18004d876  mov     eax, 201h
0x18004d87b  cmp     [rbp+37h+var_A0], dil
0x18004d87f  mov     edx, 101h
0x18004d884  mov     dword ptr [rbp+37h+Buf1], ecx
0x18004d887  cmovz   eax, edx
0x18004d88a  mov     [rsp+0D0h+var_B0], ecx; int
0x18004d88e  mov     r9d, eax; int
0x18004d891  mov     [rbp+37h+var_78], eax
0x18004d894  lea     rdx, [rbp+37h+var_90]; int *
0x18004d898  mov     rcx, r12; struct gss_OID_desc_struct *
0x18004d89b  call    ?g_verify_token_header@@YAHPEAUgss_OID_desc_struct@@PEAHPEAPEAEHH@Z; g_verify_token_header(gss_OID_desc_struct *,int *,uchar * *,int,int)
0x18004d8a0  mov     ebx, 80090308h
0x18004d8a5  test    eax, eax
0x18004d8a7  jnz     short loc_18004D903
0x18004d8a9  test    dword ptr [r13+0C0h], 200h
0x18004d8b4  mov     edi, ebx
0x18004d8b6  jz      short loc_18004D903
0x18004d8b8  mov     rax, [r15+8]
0x18004d8bc  lea     r8, [rbp+37h+var_80]; unsigned __int8 **
0x18004d8c0  mov     r9d, [rbp+37h+var_78]; int
0x18004d8c4  lea     rdx, [rbp+37h+var_90]; int *
0x18004d8c8  mov     [rbp+37h+var_80], rax
0x18004d8cc  lea     rcx, ?oids@@3PAUgss_OID_desc_struct@@A; struct gss_OID_desc_struct *
0x18004d8d3  mov     eax, dword ptr [rbp+37h+Buf1]
0x18004d8d6  mov     [rsp+0D0h+var_B0], eax; int
0x18004d8da  call    ?g_verify_token_header@@YAHPEAUgss_OID_desc_struct@@PEAHPEAPEAEHH@Z; g_verify_token_header(gss_OID_desc_struct *,int *,uchar * *,int,int)
0x18004d8df  test    eax, eax
0x18004d8e1  jz      short loc_18004D903
0x18004d8e3  lea     r9, aKerbverifysign_5; "KerbVerifySignatureToken Signature gss_"...
0x18004d8ea  mov     r8d, 2D2h
0x18004d8f0  lea     rdx, aKerbverifysign_1; "KerbVerifySignatureToken"
0x18004d8f7  mov     ecx, 3
0x18004d8fc  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004d901  xor     edi, edi
0x18004d903  movzx   r8d, [rbp+37h+var_A0]
0x18004d908  test    r8b, r8b
0x18004d90b  jz      loc_18004D9AC
0x18004d911  test    edi, edi
0x18004d913  jns     loc_18004D9AC
0x18004d919  mov     rdi, [r15+8]
0x18004d91d  lea     r8, [rbp+37h+var_80]; unsigned __int8 **
0x18004d921  mov     r15d, [r15]
0x18004d924  lea     rdx, [rbp+37h+var_90]; int *
0x18004d928  mov     r9d, [rbp+37h+var_78]; int
0x18004d92c  mov     rcx, r12; struct gss_OID_desc_struct *
0x18004d92f  mov     [rbp+37h+var_80], rdi
0x18004d933  mov     [rsp+0D0h+var_B0], r15d; int
0x18004d938  mov     [rbp+37h+var_74], 0
0x18004d93f  call    ?g_verify_token_header@@YAHPEAUgss_OID_desc_struct@@PEAHPEAPEAEHH@Z; g_verify_token_header(gss_OID_desc_struct *,int *,uchar * *,int,int)
0x18004d944  test    eax, eax
0x18004d946  jz      short loc_18004D957
0x18004d948  lea     r9, aKerbverifysign_3; "KerbVerifySignatureToken Signature Mech"...
0x18004d94f  mov     r8d, 2ECh
0x18004d955  jmp     short loc_18004D996
0x18004d957  test    dword ptr [r13+0C0h], 200h
0x18004d962  jz      short loc_18004D9A7
0x18004d964  mov     r9d, [rbp+37h+var_78]; int
0x18004d968  lea     r8, [rbp+37h+var_80]; unsigned __int8 **
0x18004d96c  lea     rdx, [rbp+37h+var_90]; int *
0x18004d970  mov     [rbp+37h+var_80], rdi
0x18004d974  lea     rcx, ?oids@@3PAUgss_OID_desc_struct@@A; struct gss_OID_desc_struct *
0x18004d97b  mov     [rsp+0D0h+var_B0], r15d; int
0x18004d980  call    ?g_verify_token_header@@YAHPEAUgss_OID_desc_struct@@PEAHPEAPEAEHH@Z; g_verify_token_header(gss_OID_desc_struct *,int *,uchar * *,int,int)
0x18004d985  test    eax, eax
0x18004d987  jz      short loc_18004D9A7
0x18004d989  lea     r9, aKerbverifysign_5; "KerbVerifySignatureToken Signature gss_"...
0x18004d990  mov     r8d, 304h
0x18004d996  lea     rdx, aKerbverifysign_1; "KerbVerifySignatureToken"
0x18004d99d  mov     ecx, 3
0x18004d9a2  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004d9a7  movzx   r8d, [rbp+37h+var_A0]
0x18004d9ac  mov     eax, [rbp+37h+var_90]
0x18004d9af  test    eax, eax
0x18004d9b1  jnz     short loc_18004D9DB
0x18004d9b3  lea     r9, aBadSignature; "Bad Signature"
0x18004d9ba  mov     r8d, 310h
0x18004d9c0  lea     rdx, aKerbverifysign_1; "KerbVerifySignatureToken"
0x18004d9c7  mov     ecx, 1
0x18004d9cc  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004d9d1  mov     ebx, 8009030Fh
0x18004d9d6  jmp     loc_18004E282
0x18004d9db  sub     eax, [rbp+37h+var_74]
0x18004d9de  test    r8b, r8b
0x18004d9e1  jz      short loc_18004D9E8
0x18004d9e3  cmp     eax, 1Eh
0x18004d9e6  jmp     short loc_18004D9EB
0x18004d9e8  cmp     eax, 16h
0x18004d9eb  jb      loc_18004E282
0x18004d9f1  mov     r12, [rbp+37h+var_88]
0x18004d9f5  mov     rax, rsi
0x18004d9f8  mov     edx, [r12]
0x18004d9fc  test    edx, edx
0x18004d9fe  cmovnz  rax, r14
0x18004da02  mov     eax, [rax+0Ch]
0x18004da05  add     eax, 87h; switch 160 cases
0x18004da0a  cmp     eax, 9Fh
0x18004da0f  ja      def_18004DA32; jumptable 000000018004DA32 default case, cases -134,-132-0,2,4-22
0x18004da15  lea     r9, __ImageBase
0x18004da1c  cdqe
0x18004da1e  movzx   eax, ds:(byte_18004E2D4 - 180000000h)[r9+rax]
0x18004da27  mov     ecx, ds:(jpt_18004DA32 - 180000000h)[r9+rax*4]
0x18004da2f  add     rcx, r9
0x18004da32  jmp     rcx; switch jump
0x18004da34  mov     r15d, 0FFFFFF7Ch; jumptable 000000018004DA32 cases 1,3
0x18004da3a  jmp     short loc_18004DA5A
0x18004da3c  mov     r15d, 0FFFFFF78h; jumptable 000000018004DA32 case -135
0x18004da42  jmp     short loc_18004DA5A
0x18004da44  mov     r15d, 0FFFFFF7Ah; jumptable 000000018004DA32 case -133
0x18004da4a  jmp     short loc_18004DA5A
0x18004da4c  mov     r15d, 0FFFFFF73h; jumptable 000000018004DA32 case 24
0x18004da52  jmp     short loc_18004DA5A
0x18004da54  mov     r15d, 0FFFFFF74h; jumptable 000000018004DA32 case 23
0x18004da5a  mov     rdi, [rbp+37h+var_80]
0x18004da5e  cmp     byte ptr [rdi+1], 0
0x18004da62  jz      short loc_18004DA76
0x18004da64  lea     r9, aNotKerbGssSigS; "Not KERB_GSS_SIG_SECOND"
0x18004da6b  mov     r8d, 34Ch
0x18004da71  jmp     loc_18004D9C0
0x18004da76  movzx   r9d, byte ptr [rdi]
0x18004da7a  mov     ecx, r9d
0x18004da7d  test    r9d, r9d
0x18004da80  jz      loc_18004DB17
0x18004da86  sub     ecx, 1
0x18004da89  jz      short loc_18004DB01
0x18004da8b  sub     ecx, 1
0x18004da8e  jz      short loc_18004DAEB
0x18004da90  cmp     ecx, 0Fh
0x18004da93  jz      short loc_18004DAD5
0x18004da95  mov     rcx, cs:WPP_GLOBAL_Control
0x18004da9c  lea     rax, WPP_GLOBAL_Control
0x18004daa3  cmp     rcx, rax
0x18004daa6  jz      loc_18004D9D1
0x18004daac  test    byte ptr [rcx+1Ch], 1
0x18004dab0  jz      loc_18004D9D1
0x18004dab6  mov     rcx, [rcx+10h]
0x18004daba  lea     r8, WPP_a1119ca399823668ae16bae9ee423caf_Traceguids
0x18004dac1  mov     edx, 10h
0x18004dac6  call    WPP_SF_d
0x18004dacb  mov     ebx, 8009030Fh
0x18004dad0  jmp     loc_18004E282
0x18004dad5  mov     rcx, [rbp+37h+var_50]
0x18004dad9  mov     rdx, [rbp+37h+var_60]
0x18004dadd  mov     dword ptr [rcx], 0
0x18004dae3  mov     dword ptr [rdx], 0FFFFFF76h
0x18004dae9  jmp     short loc_18004DB2B
0x18004daeb  mov     rcx, [rbp+37h+var_50]
0x18004daef  mov     rdx, [rbp+37h+var_60]
0x18004daf3  mov     dword ptr [rcx], 3
0x18004daf9  mov     dword ptr [rdx], 0FFFFFF7Bh
0x18004daff  jmp     short loc_18004DB2B
0x18004db01  mov     rcx, [rbp+37h+var_50]
0x18004db05  mov     rdx, [rbp+37h+var_60]
0x18004db09  mov     dword ptr [rcx], 1
0x18004db0f  mov     dword ptr [rdx], 0FFFFFF79h
0x18004db15  jmp     short loc_18004DB2B
0x18004db17  mov     rcx, [rbp+37h+var_50]
0x18004db1b  mov     rdx, [rbp+37h+var_60]
0x18004db1f  mov     dword ptr [rcx], 2
0x18004db25  mov     dword ptr [rdx], 0FFFFFF7Ah
0x18004db2b  test    r8b, r8b
0x18004db2e  jz      loc_18004DC74
0x18004db34  movzx   eax, byte ptr [rdi+3]
0x18004db38  cmp     al, 0FFh
0x18004db3a  jnz     short loc_18004DB99
0x18004db3c  cmp     [rdi+2], al
0x18004db3f  jnz     short loc_18004DB9D
0x18004db41  mov     dword ptr [rcx], 80000001h
0x18004db47  mov     eax, 0FFFFh
0x18004db4c  cmp     [rdi+4], ax
0x18004db50  jnz     loc_18004DC7E
0x18004db56  lea     rdx, [rbp+37h+var_70]
0x18004db5a  mov     ecx, r15d
0x18004db5d  call    cs:__imp_CDLocateCSystem
0x18004db63  mov     ebx, eax
0x18004db65  test    eax, eax
0x18004db67  jns     loc_18004DC90
0x18004db6d  mov     r8d, 3B4h
0x18004db73  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18004db77  lea     r9, aFailedToLoadDC_0; "Failed to load %d crypt system: 0x%x"
0x18004db7e  lea     rdx, aKerbverifysign_1; "KerbVerifySignatureToken"
0x18004db85  mov     [rsp+0D0h+var_B0], r15d
0x18004db8a  mov     ecx, 1
0x18004db8f  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004db94  jmp     loc_18004E282
0x18004db99  test    al, al
0x18004db9b  jz      short loc_18004DBAF
0x18004db9d  lea     r9, aNotKerbGssSigS; "Not KERB_GSS_SIG_SECOND"
0x18004dba4  mov     r8d, 375h
0x18004dbaa  jmp     loc_18004D9C0
0x18004dbaf  lea     eax, [r15+8Dh]
0x18004dbb6  cmp     eax, 1
0x18004dbb9  jbe     loc_18004DC58
0x18004dbbf  lea     eax, [r15+88h]
0x18004dbc6  test    eax, 0FFFFFFFDh
0x18004dbcb  jz      short loc_18004DC3C
0x18004dbcd  cmp     r15d, 0FFFFFF7Ch
0x18004dbd4  jz      short loc_18004DC20
0x18004dbd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dbdd  lea     rax, WPP_GLOBAL_Control
0x18004dbe4  cmp     rcx, rax
0x18004dbe7  jz      loc_18004D9D1
0x18004dbed  test    byte ptr [rcx+1Ch], 1
0x18004dbf1  jz      loc_18004D9D1
0x18004dbf7  movzx   r9d, byte ptr [rdi+2]
0x18004dbfc  lea     r8, WPP_a1119ca399823668ae16bae9ee423caf_Traceguids
0x18004dc03  mov     rcx, [rcx+10h]
0x18004dc07  mov     edx, 11h
0x18004dc0c  mov     [rsp+0D0h+var_B0], r15d
0x18004dc11  call    WPP_SF_dd
0x18004dc16  mov     ebx, 8009030Fh
0x18004dc1b  jmp     loc_18004E282
0x18004dc20  cmp     byte ptr [rdi+2], 0
  ... truncated ...
```

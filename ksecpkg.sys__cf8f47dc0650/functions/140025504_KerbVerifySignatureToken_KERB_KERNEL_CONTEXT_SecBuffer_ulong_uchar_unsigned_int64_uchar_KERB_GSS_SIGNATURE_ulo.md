# KerbVerifySignatureToken(_KERB_KERNEL_CONTEXT *,_SecBuffer *,ulong,uchar,unsigned __int64,uchar *,_KERB_GSS_SIGNATURE * *,ulong *,long *,_CRYPTO_SYSTEM * *,unsigned __int64 *)

- ea: `0x140025504`
- end: `0x140025ce5`
- name: `?KerbVerifySignatureToken@@YAJPEAU_KERB_KERNEL_CONTEXT@@PEAU_SecBuffer@@KE_KPEAEPEAPEAU_KERB_GSS_SIGNATURE@@PEAKPEAJPEAPEAU_CRYPTO_SYSTEM@@PEA_K@Z`
- size: `2017`
- prototype: `__int64 __fastcall(struct _KERB_KERNEL_CONTEXT *, struct _SecBuffer *, unsigned int, unsigned __int8, char, unsigned __int8 *, struct _KERB_GSS_SIGNATURE **, unsigned int *, int *, struct _CRYPTO_SYSTEM **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140024008`
- `0x14002510c`

## callees

- `0x1400085dc`
- `0x140010240`
- `0x1400102c0`
- `0x140010ae0`
- `0x140025504`
- `0x14002c874`

## pseudocode

```c
__int64 __fastcall KerbVerifySignatureToken(
        struct _KERB_KERNEL_CONTEXT *a1,
        struct _SecBuffer *a2,
        int a3,
        char a4,
        char a5,
        unsigned __int8 *a6,
        struct _KERB_GSS_SIGNATURE **a7,
        unsigned int *a8,
        int *a9,
        struct _CRYPTO_SYSTEM **a10,
        unsigned __int64 *a11)
{
  signed int v11; // edi
  int *v13; // rbx
  __int64 v15; // r13
  unsigned __int8 *v16; // rcx
  unsigned __int8 *pvBuffer; // rdx
  _DWORD *v18; // rsi
  _DWORD *v19; // r12
  struct gss_OID_desc_struct *v20; // r11
  int v21; // r13d
  int v22; // ebx
  char v23; // dl
  unsigned __int8 *v24; // r15
  int v25; // edi
  unsigned int v26; // eax
  bool v27; // cf
  char *v28; // rax
  int v29; // ecx
  unsigned int v30; // r8d
  unsigned __int8 *v31; // rdi
  unsigned int *v32; // rcx
  int *v33; // rax
  int *v34; // rax
  int *v35; // rax
  int *v36; // rax
  unsigned __int8 v37; // al
  bool v38; // zf
  bool v39; // zf
  unsigned __int8 *v40; // r15
  char *v41; // rcx
  __int64 v42; // rdx
  char *v43; // rcx
  int v44; // edx
  char *v45; // rcx
  unsigned int v46; // r8d
  int v47; // ecx
  char v48; // r10
  _DWORD *v49; // r11
  int v50; // edx
  char *v51; // r14
  unsigned __int8 v52; // r15
  _DWORD *v53; // rax
  _DWORD *v54; // rax
  int *v55; // rax
  int *v56; // rax
  _DWORD *v57; // rax
  _DWORD *v58; // rax
  _DWORD *v59; // rax
  __int64 v60; // rcx
  char v61; // ah
  _DWORD *v62; // rax
  _DWORD *v63; // rax
  size_t v64; // r8
  _DWORD *v65; // rax
  _DWORD *v66; // rax
  size_t v67; // rax
  unsigned __int8 v68; // cl
  _DWORD *v69; // rax
  _DWORD *v70; // rax
  _DWORD *v71; // rax
  bool v72; // zf
  unsigned __int64 Buf1; // [rsp+38h] [rbp-71h] BYREF
  unsigned __int8 v76; // [rsp+40h] [rbp-69h]
  int v77; // [rsp+44h] [rbp-65h] BYREF
  unsigned __int8 *v78; // [rsp+48h] [rbp-61h] BYREF
  int v79; // [rsp+50h] [rbp-59h]
  unsigned __int8 *v80; // [rsp+58h] [rbp-51h]
  __int64 v81; // [rsp+60h] [rbp-49h] BYREF
  int cbBuffer; // [rsp+68h] [rbp-41h]
  int v83; // [rsp+6Ch] [rbp-3Dh] BYREF
  __int64 v84; // [rsp+70h] [rbp-39h] BYREF
  unsigned int *v85; // [rsp+78h] [rbp-31h]
  int *v86; // [rsp+80h] [rbp-29h]
  struct _KERB_KERNEL_CONTEXT *v87; // [rsp+88h] [rbp-21h]
  struct gss_OID_desc_struct *v88; // [rsp+90h] [rbp-19h]
  unsigned __int64 *v89; // [rsp+98h] [rbp-11h]
  struct _CRYPTO_SYSTEM **v90; // [rsp+A0h] [rbp-9h]
  struct _KERB_GSS_SIGNATURE **v91; // [rsp+A8h] [rbp-1h]

  v11 = 0;
  v13 = a9;
  v91 = a7;
  v15 = 0;
  v90 = a10;
  v87 = a1;
  v16 = a6;
  v89 = a11;
  v79 = a3;
  v80 = a6;
  v85 = a8;
  v86 = a9;
  v77 = 0;
  v84 = 0;
  v83 = 0;
  v81 = 0;
  if ( !a4 || (*((_DWORD *)a1 + 38) & 0x600) != 0 )
  {
    a3 = 0;
    v79 = 0;
  }
  pvBuffer = (unsigned __int8 *)a2->pvBuffer;
  v78 = pvBuffer;
  if ( *pvBuffer == 96
    && (unsigned int)(*((_DWORD *)a1 + 28) - 17) <= 1
    && (*((_DWORD *)a1 + 39) & 0x400) != 0
    && (unsigned int)(*((_DWORD *)a1 + 46) - 17) > 1 )
  {
    *a6 = 1;
  }
  v18 = (_DWORD *)((char *)a1 + 112);
  v76 = *v16;
  v19 = (_DWORD *)((char *)a1 + 184);
  if ( *(_DWORD *)((char *)a1 + (v76 != 0 ? 0x48 : 0) + 112) == 17
    || *(_DWORD *)((char *)a1 + (v76 != 0 ? 0x48 : 0) + 112) == 18 )
  {
    v31 = pvBuffer + 2;
    if ( a2->cbBuffer < 0x1C )
      return (unsigned int)-2146893048;
    if ( *pvBuffer != (a4 != 0) + 4 || pvBuffer[1] != 4 )
    {
      v22 = -2146893048;
      goto LABEL_179;
    }
    if ( a4 )
    {
      v44 = pvBuffer[5] + (pvBuffer[4] << 8);
      if ( (*v31 & 2) != 0 )
      {
        if ( a2->cbBuffer < v44 + 60 )
          return (unsigned int)-2146893048;
      }
      else if ( v44 != 12 )
      {
        return (unsigned int)-2146893041;
      }
    }
    if ( v31[1] == 0xFF && (a4 || *(_DWORD *)(v31 + 2) == -1) )
    {
      v40 = v80;
      if ( (*((_DWORD *)a1 + 39) & 0x400) != 0 && (*v31 & 4) == 0 && (unsigned int)(*v19 - 17) <= 1 )
        *v80 = 1;
      v45 = (char *)a1 + 112;
      if ( *v40 )
        v45 = (char *)a1 + 184;
      if ( *(_DWORD *)v45 == 17 )
      {
        v46 = -148;
        v47 = (*v31 & 2) != 0 ? -150 : 15;
      }
      else
      {
        if ( *(_DWORD *)v45 != 18 )
          return (unsigned int)-2146893054;
        v46 = -149;
        v47 = (*v31 & 2) != 0 ? -151 : 16;
      }
      *v13 = v47;
      v22 = CDLocateCSystem(v46, &v81);
      if ( v22 < 0 )
      {
        v15 = v81;
        goto LABEL_179;
      }
      if ( v48 && (*v31 & 2) == 0 )
        *v49 = -2147483647;
      v15 = v81;
LABEL_104:
      v50 = *((_DWORD *)a1 + 38);
      if ( (v50 & 0x400) != 0 || (v50 & 0x1000C) == 0x10000 )
        v51 = &a5;
      else
        v51 = (char *)a1 + 144;
      v52 = *v40;
      v53 = v18;
      if ( v52 )
        v53 = v19;
      if ( *v53 == 17 )
        goto LABEL_124;
      v54 = v18;
      if ( v52 )
        v54 = v19;
      if ( *v54 == 18 )
        goto LABEL_124;
      v55 = v18;
      if ( v52 )
        v55 = v19;
      if ( *v55 >= 1 )
      {
        v56 = v18;
        if ( v52 )
          v56 = v19;
        if ( *v56 <= 3 )
          goto LABEL_123;
      }
      v57 = v18;
      if ( v52 )
        v57 = v19;
      if ( *v57 != -132 )
      {
LABEL_124:
        v58 = v18;
        if ( v52 )
          v58 = v19;
        if ( *v58 == 17 )
          goto LABEL_131;
        v59 = v18;
        if ( v52 )
          v59 = v19;
        if ( *v59 == 18 )
        {
LABEL_131:
          v60 = HIDWORD(*(_QWORD *)v51);
          BYTE3(Buf1) = BYTE4(*(_QWORD *)v51);
          LOBYTE(Buf1) = BYTE3(v60);
          BYTE1(Buf1) = BYTE2(v60);
          v61 = BYTE1(v60);
          LODWORD(v60) = *(_DWORD *)v51;
          BYTE2(Buf1) = v61;
          BYTE4(Buf1) = BYTE3(v60);
          BYTE5(Buf1) = BYTE2(v60);
          BYTE6(Buf1) = BYTE1(v60);
          HIBYTE(Buf1) = v60;
        }
        else
        {
          LOBYTE(Buf1) = v51[3];
          BYTE1(Buf1) = v51[2];
          BYTE2(Buf1) = v51[1];
          BYTE3(Buf1) = *v51;
        }
      }
      else
      {
LABEL_123:
        LODWORD(Buf1) = *(_DWORD *)v51;
      }
      if ( (v50 & 0xC) != 0 )
      {
        v62 = v18;
        if ( v52 )
          v62 = v19;
        if ( *v62 == 17 )
          goto LABEL_139;
        v63 = v18;
        v64 = 4;
        if ( v52 )
          v63 = v19;
        if ( *v63 == 18 )
LABEL_139:
          v64 = 8;
        if ( memcmp(&Buf1, v31 + 6, v64) )
        {
          v22 = -2146893040;
LABEL_179:
          if ( v84 && v15 )
            (*(void (__fastcall **)(__int64 *))(v15 + 64))(&v84);
          return (unsigned int)v22;
        }
      }
      v65 = v18;
      if ( v52 )
        v65 = v19;
      if ( *v65 == 17 )
        goto LABEL_148;
      v66 = v18;
      if ( v52 )
        v66 = v19;
      v38 = *v66 == 18;
      v67 = 4;
      if ( v38 )
LABEL_148:
        v67 = 8;
      memmove(&Buf1, v31 + 6, v67);
      *v89 = Buf1;
      v68 = *v80;
      v69 = v18;
      if ( *v80 )
        v69 = v19;
      if ( *v69 == 17 )
        goto LABEL_173;
      v70 = v18;
      if ( v68 )
        v70 = v19;
      if ( *v70 == 18 )
      {
LABEL_173:
        if ( (*((_DWORD *)v87 + 39) & 2) != 0 && (*v31 & 1) == 0 )
          goto LABEL_164;
      }
      else
      {
        v71 = v18;
        if ( (*((_DWORD *)v87 + 39) & 2) != 0 )
        {
          if ( v68 )
            v71 = v19;
          if ( *v71 == 17 )
            goto LABEL_174;
          if ( v68 )
            v18 = v19;
          if ( *v18 == 18 )
            goto LABEL_174;
          v72 = *(_DWORD *)(v31 + 10) == -1;
        }
        else
        {
          if ( v68 )
            v71 = v19;
          if ( *v71 == 17 )
            goto LABEL_174;
          if ( v68 )
            v18 = v19;
          if ( *v18 == 18 )
            goto LABEL_174;
          v72 = *(_DWORD *)(v31 + 10) == 0;
        }
        if ( !v72 )
        {
LABEL_164:
          v22 = -2146893041;
          goto LABEL_179;
        }
      }
LABEL_174:
      ++*(_QWORD *)v51;
      if ( v90 )
        *v90 = (struct _CRYPTO_SYSTEM *)v15;
      *v91 = (struct _KERB_GSS_SIGNATURE *)v31;
      goto LABEL_179;
    }
    return (unsigned int)-2146893041;
  }
  v20 = (struct gss_OID_desc_struct *)&unk_140018A40;
  if ( (*((_DWORD *)a1 + 39) & 0x10) == 0 )
    v20 = (struct gss_OID_desc_struct *)&unk_140018A10;
  cbBuffer = a2->cbBuffer;
  v88 = v20;
  LODWORD(Buf1) = cbBuffer + a3;
  v21 = a4 != 0 ? 513 : 257;
  v22 = -2146893048;
  if ( !g_verify_token_header(v20, &v77, &v78, v21, cbBuffer + a3) )
  {
    v11 = -2146893048;
    if ( (*((_DWORD *)a1 + 38) & 0x200) != 0 )
    {
      v78 = (unsigned __int8 *)a2->pvBuffer;
      v11 = g_verify_token_header((struct gss_OID_desc_struct *)&oids, &v77, &v78, v21, Buf1) == 0 ? 0x80090308 : 0;
    }
  }
  v23 = a4;
  if ( a4 && v11 < 0 )
  {
    v24 = (unsigned __int8 *)a2->pvBuffer;
    v78 = v24;
    v25 = 0;
    if ( !g_verify_token_header(v88, &v77, &v78, v21, cbBuffer) && (*((_DWORD *)a1 + 38) & 0x200) != 0 )
    {
      v78 = v24;
      g_verify_token_header((struct gss_OID_desc_struct *)&oids, &v77, &v78, v21, cbBuffer);
    }
    v23 = a4;
  }
  else
  {
    v25 = v79;
  }
  if ( !v77 )
    return (unsigned int)-2146893041;
  v26 = v77 - v25;
  if ( v23 )
    v27 = v26 < 0x1E;
  else
    v27 = v26 < 0x16;
  if ( !v27 )
  {
    v28 = (char *)a1 + 112;
    if ( v76 )
      v28 = (char *)a1 + 184;
    v29 = *(_DWORD *)v28;
    if ( *(_DWORD *)v28 == -135 )
    {
      v30 = -136;
    }
    else if ( v29 == -133 )
    {
      v30 = -134;
    }
    else if ( ((v29 - 1) & 0xFFFFFFFD) != 0 )
    {
      if ( v29 == 23 )
      {
        v30 = -140;
      }
      else
      {
        if ( v29 != 24 )
          return (unsigned int)-1073741595;
        v30 = -141;
      }
    }
    else
    {
      v30 = -132;
    }
    v31 = v78;
    if ( v78[1] )
      return (unsigned int)-2146893041;
    if ( *v78 )
    {
      switch ( *v78 )
      {
        case 1u:
          v32 = v85;
          v35 = v86;
          *v85 = 1;
          *v35 = -135;
          break;
        case 2u:
          v32 = v85;
          v34 = v86;
          *v85 = 3;
          *v34 = -133;
          break;
        case 0x11u:
          v32 = v85;
          v33 = v86;
          *v85 = 0;
          *v33 = -138;
          break;
        default:
          return (unsigned int)-2146893041;
      }
    }
    else
    {
      v32 = v85;
      v36 = v86;
      *v85 = 2;
      *v36 = -134;
    }
    if ( v23 )
    {
      v37 = v31[3];
      if ( v37 == 0xFF )
      {
        if ( v31[2] != 0xFF )
          return (unsigned int)-2146893041;
        *v32 = -2147483647;
      }
      else
      {
        if ( v37 )
          return (unsigned int)-2146893041;
        if ( v30 + 141 <= 1 )
        {
          v39 = v31[2] == 16;
        }
        else if ( ((v30 + 136) & 0xFFFFFFFD) != 0 )
        {
          if ( v30 != -132 )
            return (unsigned int)-2146893041;
          v39 = v31[2] == 0;
        }
        else
        {
          v39 = v31[2] == 17;
        }
        if ( !v39 )
          return (unsigned int)-2146893041;
      }
      v38 = *((_WORD *)v31 + 2) == 0xFFFF;
    }
    else
    {
      v38 = *(_DWORD *)(v31 + 2) == -1;
    }
    if ( v38 )
    {
      v22 = CDLocateCSystem(v30, &v81);
      if ( v22 < 0 )
        return (unsigned int)v22;
      v40 = v80;
      v15 = v81;
      v41 = (char *)a1 + 112;
      if ( *v80 )
        v41 = (char *)a1 + 184;
      v42 = *((unsigned int *)v41 + 2);
      v43 = (char *)a1 + 112;
      if ( *v80 )
        v43 = (char *)a1 + 184;
      v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64 *))(v81 + 40))(
              *((_QWORD *)v43 + 2),
              v42,
              0,
              &v84);
      if ( v22 < 0 )
        goto LABEL_179;
      v22 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int8 *))(v15 + 88))(1, v84, v31 + 14);
      if ( v22 < 0 )
        goto LABEL_179;
      v83 = 8;
      v22 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, __int64, unsigned __int8 *, int *))(v15 + 56))(
              v84,
              v31 + 6,
              8,
              v31 + 6,
              &v83);
      if ( v22 < 0 )
        goto LABEL_179;
      goto LABEL_104;
    }
    return (unsigned int)-2146893041;
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x140025504  mov     [rsp-8+arg_10], rbx
0x140025509  push    rbp
0x14002550a  push    rsi
0x14002550b  push    rdi
0x14002550c  push    r12
0x14002550e  push    r13
0x140025510  push    r14
0x140025512  push    r15
0x140025514  lea     rbp, [rsp-7]
0x140025519  sub     rsp, 0B0h
0x140025520  mov     rax, [rbp+37h+arg_30]
0x140025524  xor     edi, edi
0x140025526  mov     r11, [rbp+37h+arg_38]
0x14002552a  mov     r14, rcx
0x14002552d  mov     rbx, [rbp+37h+arg_40]
0x140025534  mov     r10b, r9b
0x140025537  mov     [rbp+37h+var_38], rax
0x14002553b  mov     r15, rdx
0x14002553e  mov     rax, [rbp+37h+arg_48]
0x140025545  mov     r13d, edi
0x140025548  mov     [rbp+37h+var_40], rax
0x14002554c  mov     rax, [rbp+37h+arg_50]
0x140025553  mov     [rbp+37h+var_58], rcx
0x140025557  mov     rcx, [rbp+37h+arg_28]
0x14002555b  mov     [rbp+37h+var_48], rax
0x14002555f  mov     [rbp+37h+var_B0], r9b
0x140025563  mov     [rbp+37h+var_90], r8d
0x140025567  mov     [rbp+37h+var_88], rcx
0x14002556b  mov     [rbp+37h+var_68], r11
0x14002556f  mov     [rbp+37h+var_60], rbx
0x140025573  mov     [rbp+37h+var_9C], edi
0x140025576  mov     [rbp+37h+var_70], rdi
0x14002557a  mov     [rbp+37h+var_74], edi
0x14002557d  mov     [rbp+37h+var_80], rdi
0x140025581  test    r9b, r9b
0x140025584  jz      short loc_140025593
0x140025586  test    dword ptr [r14+98h], 600h
0x140025591  jz      short loc_140025599
0x140025593  mov     r8d, edi
0x140025596  mov     [rbp+37h+var_90], edi
0x140025599  mov     rdx, [rdx+8]
0x14002559d  mov     [rbp+37h+var_98], rdx
0x1400255a1  cmp     byte ptr [rdx], 60h ; '`'
0x1400255a4  jnz     short loc_1400255D1
0x1400255a6  mov     eax, [r14+70h]
0x1400255aa  sub     eax, 11h
0x1400255ad  cmp     eax, 1
0x1400255b0  ja      short loc_1400255D1
0x1400255b2  test    dword ptr [r14+9Ch], 400h
0x1400255bd  jz      short loc_1400255D1
0x1400255bf  mov     eax, [r14+0B8h]
0x1400255c6  sub     eax, 11h
0x1400255c9  cmp     eax, 1
0x1400255cc  jbe     short loc_1400255D1
0x1400255ce  mov     byte ptr [rcx], 1
0x1400255d1  mov     r9b, [rcx]
0x1400255d4  lea     rsi, [r14+70h]
0x1400255d8  mov     al, r9b
0x1400255db  mov     [rbp+37h+var_A0], r9b
0x1400255df  neg     al
0x1400255e1  lea     r12, [r14+0B8h]
0x1400255e8  sbb     rcx, rcx
0x1400255eb  and     ecx, 48h
0x1400255ee  cmp     dword ptr [rcx+r14+70h], 11h
0x1400255f4  jz      loc_140025940
0x1400255fa  mov     al, r9b
0x1400255fd  neg     al
0x1400255ff  sbb     rcx, rcx
0x140025602  and     ecx, 48h
0x140025605  cmp     dword ptr [rcx+r14+70h], 12h
0x14002560b  jz      loc_140025940
0x140025611  mov     eax, [r14+9Ch]
0x140025618  lea     r11, unk_140018A40
0x14002561f  test    al, 10h
0x140025621  lea     rdx, [rbp+37h+var_9C]; int *
0x140025625  lea     rax, unk_140018A10
0x14002562c  cmovz   r11, rax
0x140025630  mov     eax, [r15]
0x140025633  mov     [rbp+37h+var_78], eax
0x140025636  mov     [rbp+37h+var_50], r11
0x14002563a  lea     ecx, [rax+r8]
0x14002563e  mov     al, r10b
0x140025641  neg     al
0x140025643  mov     dword ptr [rbp+37h+Buf1], ecx
0x140025646  mov     [rsp+0E0h+var_C0], ecx; int
0x14002564a  lea     r8, [rbp+37h+var_98]; unsigned __int8 **
0x14002564e  sbb     r13d, r13d
0x140025651  mov     rcx, r11; struct gss_OID_desc_struct *
0x140025654  and     r13d, 100h
0x14002565b  add     r13d, 101h
0x140025662  mov     r9d, r13d; int
0x140025665  call    ?g_verify_token_header@@YAHPEAUgss_OID_desc_struct@@PEAHPEAPEAEHH@Z; g_verify_token_header(gss_OID_desc_struct *,int *,uchar * *,int,int)
0x14002566a  mov     ebx, 80090308h
0x14002566f  test    eax, eax
0x140025671  jnz     short loc_1400256B0
0x140025673  test    dword ptr [r14+98h], 200h
0x14002567e  mov     edi, ebx
0x140025680  jz      short loc_1400256B0
0x140025682  mov     rax, [r15+8]
0x140025686  lea     r8, [rbp+37h+var_98]; unsigned __int8 **
0x14002568a  mov     [rbp+37h+var_98], rax
0x14002568e  lea     rdx, [rbp+37h+var_9C]; int *
0x140025692  mov     eax, dword ptr [rbp+37h+Buf1]
0x140025695  lea     rcx, ?oids@@3PAUgss_OID_desc_struct@@A; struct gss_OID_desc_struct *
0x14002569c  mov     r9d, r13d; int
0x14002569f  mov     [rsp+0E0h+var_C0], eax; int
0x1400256a3  call    ?g_verify_token_header@@YAHPEAUgss_OID_desc_struct@@PEAHPEAPEAEHH@Z; g_verify_token_header(gss_OID_desc_struct *,int *,uchar * *,int,int)
0x1400256a8  neg     eax
0x1400256aa  sbb     edi, edi
0x1400256ac  not     edi
0x1400256ae  and     edi, ebx
0x1400256b0  mov     dl, [rbp+37h+var_B0]
0x1400256b3  test    dl, dl
0x1400256b5  jz      short loc_140025727
0x1400256b7  test    edi, edi
0x1400256b9  jns     short loc_140025727
0x1400256bb  mov     eax, [rbp+37h+var_78]
0x1400256be  lea     r8, [rbp+37h+var_98]; unsigned __int8 **
0x1400256c2  mov     r15, [r15+8]
0x1400256c6  lea     rdx, [rbp+37h+var_9C]; int *
0x1400256ca  mov     rcx, [rbp+37h+var_50]; struct gss_OID_desc_struct *
0x1400256ce  mov     r9d, r13d; int
0x1400256d1  mov     [rbp+37h+var_98], r15
0x1400256d5  xor     edi, edi
0x1400256d7  mov     [rsp+0E0h+var_C0], eax; int
0x1400256db  call    ?g_verify_token_header@@YAHPEAUgss_OID_desc_struct@@PEAHPEAPEAEHH@Z; g_verify_token_header(gss_OID_desc_struct *,int *,uchar * *,int,int)
0x1400256e0  test    eax, eax
0x1400256e2  jnz     short loc_140025713
0x1400256e4  test    dword ptr [r14+98h], 200h
0x1400256ef  jz      short loc_140025713
0x1400256f1  mov     eax, [rbp+37h+var_78]
0x1400256f4  lea     r8, [rbp+37h+var_98]; unsigned __int8 **
0x1400256f8  mov     r9d, r13d; int
0x1400256fb  mov     [rsp+0E0h+var_C0], eax; int
0x1400256ff  lea     rdx, [rbp+37h+var_9C]; int *
0x140025703  mov     [rbp+37h+var_98], r15
0x140025707  lea     rcx, ?oids@@3PAUgss_OID_desc_struct@@A; struct gss_OID_desc_struct *
0x14002570e  call    ?g_verify_token_header@@YAHPEAUgss_OID_desc_struct@@PEAHPEAPEAEHH@Z; g_verify_token_header(gss_OID_desc_struct *,int *,uchar * *,int,int)
0x140025713  mov     dl, [rbp+37h+var_B0]
0x140025716  mov     eax, [rbp+37h+var_9C]
0x140025719  test    eax, eax
0x14002571b  jnz     short loc_14002572C
0x14002571d  mov     ebx, 8009030Fh
0x140025722  jmp     loc_140025CC7
0x140025727  mov     edi, [rbp+37h+var_90]
0x14002572a  jmp     short loc_140025716
0x14002572c  sub     eax, edi
0x14002572e  test    dl, dl
0x140025730  jz      short loc_140025737
0x140025732  cmp     eax, 1Eh
0x140025735  jmp     short loc_14002573A
0x140025737  cmp     eax, 16h
0x14002573a  jb      loc_140025CC7
0x140025740  cmp     [rbp+37h+var_A0], 0
0x140025744  mov     r9d, 0FFFFFF7Ah
0x14002574a  mov     rax, rsi
0x14002574d  mov     ebx, 0FFFFFFFDh
0x140025752  cmovnz  rax, r12
0x140025756  lea     r11d, [r9-1]
0x14002575a  lea     r10d, [r9+1]
0x14002575e  mov     ecx, [rax]
0x140025760  cmp     ecx, r11d
0x140025763  jz      short loc_1400257A2
0x140025765  cmp     ecx, r10d
0x140025768  jz      short loc_14002579D
0x14002576a  lea     eax, [rcx-1]
0x14002576d  test    ebx, eax
0x14002576f  jz      short loc_140025795
0x140025771  cmp     ecx, 17h
0x140025774  jz      short loc_14002578D
0x140025776  cmp     ecx, 18h
0x140025779  jz      short loc_140025785
0x14002577b  mov     ebx, 0C00000E5h
0x140025780  jmp     loc_140025CC7
0x140025785  mov     r8d, 0FFFFFF73h
0x14002578b  jmp     short loc_1400257A8
0x14002578d  mov     r8d, 0FFFFFF74h
0x140025793  jmp     short loc_1400257A8
0x140025795  mov     r8d, 0FFFFFF7Ch
0x14002579b  jmp     short loc_1400257A8
0x14002579d  mov     r8d, r9d
0x1400257a0  jmp     short loc_1400257A8
0x1400257a2  mov     r8d, 0FFFFFF78h
0x1400257a8  mov     rdi, [rbp+37h+var_98]
0x1400257ac  cmp     byte ptr [rdi+1], 0
0x1400257b0  jnz     loc_14002571D
0x1400257b6  movzx   ecx, byte ptr [rdi]
0x1400257b9  test    ecx, ecx
0x1400257bb  jz      short loc_14002580C
0x1400257bd  sub     ecx, 1
0x1400257c0  jz      short loc_1400257F9
0x1400257c2  sub     ecx, 1
0x1400257c5  jz      short loc_1400257E6
0x1400257c7  cmp     ecx, 0Fh
0x1400257ca  jnz     loc_14002571D
0x1400257d0  mov     rcx, [rbp+37h+var_68]
0x1400257d4  mov     rax, [rbp+37h+var_60]
0x1400257d8  mov     dword ptr [rcx], 0
0x1400257de  mov     dword ptr [rax], 0FFFFFF76h
0x1400257e4  jmp     short loc_14002581D
0x1400257e6  mov     rcx, [rbp+37h+var_68]
0x1400257ea  mov     rax, [rbp+37h+var_60]
0x1400257ee  mov     dword ptr [rcx], 3
0x1400257f4  mov     [rax], r10d
0x1400257f7  jmp     short loc_14002581D
0x1400257f9  mov     rcx, [rbp+37h+var_68]
0x1400257fd  mov     rax, [rbp+37h+var_60]
0x140025801  mov     dword ptr [rcx], 1
0x140025807  mov     [rax], r11d
0x14002580a  jmp     short loc_14002581D
0x14002580c  mov     rcx, [rbp+37h+var_68]
0x140025810  mov     rax, [rbp+37h+var_60]
0x140025814  mov     dword ptr [rcx], 2
0x14002581a  mov     [rax], r9d
0x14002581d  test    dl, dl
0x14002581f  jz      short loc_140025885
0x140025821  mov     al, [rdi+3]
0x140025824  cmp     al, 0FFh
0x140025826  jnz     short loc_140025842
0x140025828  cmp     [rdi+2], al
0x14002582b  jnz     loc_14002571D
0x140025831  mov     dword ptr [rcx], 80000001h
0x140025837  mov     eax, 0FFFFh
0x14002583c  cmp     [rdi+4], ax
0x140025840  jmp     short loc_140025889
0x140025842  test    al, al
0x140025844  jnz     loc_14002571D
0x14002584a  lea     eax, [r8+8Dh]
0x140025851  cmp     eax, 1
0x140025854  jbe     short loc_14002587F
0x140025856  lea     eax, [r8+88h]
0x14002585d  test    ebx, eax
0x14002585f  jz      short loc_140025879
0x140025861  cmp     r8d, 0FFFFFF7Ch
0x140025868  jnz     loc_14002571D
0x14002586e  cmp     byte ptr [rdi+2], 0
0x140025872  jz      short loc_140025837
0x140025874  jmp     loc_14002571D
0x140025879  cmp     byte ptr [rdi+2], 11h
0x14002587d  jmp     short loc_140025872
0x14002587f  cmp     byte ptr [rdi+2], 10h
0x140025883  jmp     short loc_140025872
0x140025885  cmp     dword ptr [rdi+2], 0FFFFFFFFh
0x140025889  jnz     loc_14002571D
0x14002588f  lea     rdx, [rbp+37h+var_80]
0x140025893  mov     ecx, r8d
0x140025896  call    CDLocateCSystem
0x14002589b  mov     ebx, eax
0x14002589d  test    eax, eax
0x14002589f  js      loc_140025CC7
0x1400258a5  mov     r15, [rbp+37h+var_88]
0x1400258a9  lea     r9, [rbp+37h+var_70]
0x1400258ad  mov     r13, [rbp+37h+var_80]
0x1400258b1  mov     rcx, rsi
0x1400258b4  mov     r8b, [r15]
0x1400258b7  mov     rax, [r13+28h]
0x1400258bb  test    r8b, r8b
0x1400258be  cmovnz  rcx, r12
0x1400258c2  mov     edx, [rcx+8]
0x1400258c5  mov     rcx, rsi
0x1400258c8  cmovnz  rcx, r12
0x1400258cc  xor     r8d, r8d
0x1400258cf  mov     rcx, [rcx+10h]
0x1400258d3  call    _guard_dispatch_icall
0x1400258d8  mov     ebx, eax
0x1400258da  test    eax, eax
0x1400258dc  js      loc_140025CAE
0x1400258e2  mov     rax, [r13+58h]
0x1400258e6  lea     r8, [rdi+0Eh]
0x1400258ea  mov     rdx, [rbp+37h+var_70]
0x1400258ee  mov     r9d, 8
0x1400258f4  lea     ecx, [r9-7]
0x1400258f8  call    _guard_dispatch_icall
0x1400258fd  mov     ebx, eax
0x1400258ff  test    eax, eax
0x140025901  js      loc_140025CAE
0x140025907  lea     rcx, [rbp+37h+var_74]
0x14002590b  mov     [rbp+37h+var_74], 8
0x140025912  mov     rax, [r13+38h]
0x140025916  lea     rdx, [rdi+6]
0x14002591a  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x14002591f  mov     r9, rdx
0x140025922  mov     rcx, [rbp+37h+var_70]
0x140025926  mov     r8d, 8
0x14002592c  call    _guard_dispatch_icall
0x140025931  mov     ebx, eax
0x140025933  test    eax, eax
0x140025935  jns     loc_140025A68
0x14002593b  jmp     loc_140025CAE
0x140025940  mov     r8d, [r15]
0x140025943  lea     rdi, [rdx+2]
0x140025947  cmp     r8d, 1Ch
0x14002594b  jnb     short loc_140025957
0x14002594d  mov     ebx, 80090308h
0x140025952  jmp     loc_140025CC7
0x140025957  mov     al, r10b
0x14002595a  mov     r9d, 4
0x140025960  neg     al
0x140025962  movzx   eax, byte ptr [rdx]
0x140025965  sbb     cx, cx
  ... truncated ...
```

# CRPCRequest::AddParam(ushort const *,ushort,uchar,unsigned __int64,unsigned __int64,void const *,RPCPARAMEXINFO const *,_TDSCRYPTOMETADATA * const,unsigned __int64,unsigned __int64)

- ea: `0x100459968`
- end: `0x10045a866`
- name: `?AddParam@CRPCRequest@@QEAAJPEBGGE_K1PEBXPEBVRPCPARAMEXINFO@@QEAU_TDSCRYPTOMETADATA@@_K5@Z`
- size: `3838`
- prototype: `__int64 __usercall@<rax>(CRPCRequest *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int16@<r8w>, unsigned __int8@<r9b>, rsize_t DestinationSize, unsigned __int64, const void *, const struct RPCPARAMEXINFO *, struct _TDSCRYPTOMETADATA *const, unsigned __int64, unsigned __int64)`
- caller_count: `33`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10045b624`
- `0x10045b6cc`
- `0x1004b8c88`
- `0x1004b9060`
- `0x1004b98bc`
- `0x1004b9df0`
- `0x1004ba544`
- `0x1004bf948`
- `0x1004c0a88`
- `0x1004c1304`
- `0x1004c1a34`
- `0x1004c401c`
- `0x1004c4314`
- `0x1004c4868`
- `0x1004c4c24`
- `0x1004c5054`
- `0x1004c5d00`
- `0x1004ef334`
- `0x1004ef72c`
- `0x1004efe64`
- `0x1004f095c`
- `0x1004f38c4`
- `0x1004f3e5c`
- `0x1004f4ea8`
- `0x1004f52d4`
- `0x1004f6098`
- `0x1004f6dd0`
- `0x1004f7310`
- `0x1004fcca0`
- `0x1004fecd0`
- `0x1005018c0`
- `0x1005024a8`
- `0x100522dcc`

## callees

- `0x100459968`
- `0x10045a86c`
- `0x10045ae90`
- `0x10045af04`
- `0x10045be64`
- `0x10045c214`
- `0x10045c3f0`
- `0x10045e330`
- `0x100463e78`
- `0x1004824c8`
- `0x1004bbb40`
- `0x1004bbe8c`
- `0x100546a24`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100459e38`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100459fe9`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a145`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a236`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a39e`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a436`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a486`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a653`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a721`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a775`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100459e38`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100459fe9`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a145`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a236`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a39e`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a436`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a486`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a653`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a721`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045a775`

## pseudocode

```c
__int64 __fastcall CRPCRequest::AddParam(
        CRPCRequest *this,
        const unsigned __int16 *a2,
        __int16 a3,
        unsigned __int8 a4,
        rsize_t DestinationSize,
        unsigned __int64 a6,
        void *a7,
        const struct RPCPARAMEXINFO *a8,
        struct _TDSCRYPTOMETADATA *const a9,
        unsigned __int64 a10,
        unsigned __int64 a11)
{
  void *v11; // rbx
  struct _TDSCRYPTOMETADATA *v13; // rcx
  unsigned int v15; // r14d
  const struct RPCPARAMEXINFO *v17; // r8
  unsigned __int8 **v18; // r9
  __int64 v19; // rdx
  unsigned __int64 v20; // r12
  unsigned __int64 v21; // rdi
  const void *v22; // rdx
  int PaddingSize; // ebx
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  void *v28; // rdx
  int Param; // eax
  int v30; // eax
  unsigned __int8 *v31; // r8
  __int64 v32; // rbx
  unsigned __int64 v33; // r15
  unsigned __int8 v34; // dl
  __int64 v35; // r8
  struct _TDSCRYPTOMETADATA *v36; // r12
  __int64 v37; // rax
  char *v38; // rcx
  char *v39; // rdx
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  char *v47; // rcx
  __int64 v48; // rax
  char *v49; // rdx
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  __int128 v56; // xmm1
  unsigned int *v57; // rdi
  unsigned __int64 v58; // rcx
  unsigned __int8 v59; // r15
  rsize_t v60; // rax
  void *v61; // rdx
  char v62; // al
  char v63; // al
  __int16 v64; // ax
  __int64 v65; // rdx
  rsize_t v66; // rdi
  char v67; // al
  unsigned __int64 v68; // rcx
  __int16 v69; // ax
  __int16 v70; // ax
  __int16 v71; // bx
  __int64 v72; // rax
  __int64 v73; // rcx
  __int16 v74; // bx
  int v75; // ecx
  CRPCPolicy *v76; // r15
  int v77; // eax
  __int64 v78; // r9
  __int64 v79; // rdx
  __int64 v80; // rdx
  bool v81; // cf
  rsize_t v82; // rbx
  rsize_t v83; // rbx
  rsize_t v84; // rcx
  unsigned __int64 v85; // rcx
  unsigned __int8 v87; // [rsp+50h] [rbp-B0h]
  struct _TDSCRYPTOMETADATA *v88; // [rsp+58h] [rbp-A8h]
  rsize_t SourceSize; // [rsp+60h] [rbp-A0h]
  struct RPCPARAMEXINFO *v90; // [rsp+68h] [rbp-98h]
  unsigned int v91; // [rsp+70h] [rbp-90h] BYREF
  void *v92; // [rsp+78h] [rbp-88h]
  void *Source; // [rsp+80h] [rbp-80h]
  __int64 v94; // [rsp+88h] [rbp-78h]
  char v95; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v96; // [rsp+91h] [rbp-6Fh] BYREF
  char v97; // [rsp+92h] [rbp-6Eh]
  _BYTE Destination[390]; // [rsp+93h] [rbp-6Dh] BYREF
  char v99; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int8 v100[398]; // [rsp+222h] [rbp+122h] BYREF
  char v101[8]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int8 v102[24]; // [rsp+3B8h] [rbp+2B8h] BYREF

  v11 = a7;
  v13 = a9;
  v15 = a4;
  v17 = a8;
  v18 = (unsigned __int8 **)((char *)this + 16);
  v87 = v15;
  v19 = *((_QWORD *)this + 2);
  v92 = a7;
  v90 = a8;
  v88 = a9;
  SourceSize = 1;
  if ( v19 )
  {
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
    v13 = v88;
    v18 = (unsigned __int8 **)((char *)this + 16);
    v17 = v90;
  }
  v20 = a6;
  v21 = DestinationSize;
  *v18 = 0;
  v91 = 0;
  if ( v13 )
  {
    if ( (a3 & 0x200) != 0 )
    {
      if ( v20 != 0xFFFF )
      {
LABEL_18:
        *((_BYTE *)v13 + 8) = v15;
        *((_BYTE *)v13 + 9) = *((_BYTE *)v90 + 8);
        goto LABEL_19;
      }
      EncryptStream(*((void **)this + 4), 0, 0, 0, 0, (struct _TDSCRYPTOMETADATA *)((char *)v13 + 3184));
    }
    else
    {
      v22 = v11;
      if ( (a3 & 0x100) != 0 )
        v22 = 0;
      PaddingSize = EncryptParam(
                      *((void **)this + 4),
                      v22,
                      v21,
                      a10,
                      v15,
                      *((_BYTE *)v17 + 8),
                      (struct _TDSCRYPTOMETADATA *)((char *)v13 + 3184),
                      v18,
                      &v91);
      if ( PaddingSize < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
        {
LABEL_12:
          v27 = *(_QWORD *)this;
          *((_WORD *)this + 49) = 0;
          *((_BYTE *)this + 100) = 0;
          *((_QWORD *)this + 13) = 0;
          *((_QWORD *)this + 1) = 0;
          *((_QWORD *)this + 14) = 0;
          *((_QWORD *)this + 15) = 0;
          if ( v27 )
            ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
          v28 = (void *)*((_QWORD *)this + 4);
          *(_QWORD *)this = 0;
          *((_DWORD *)this + 20) = 0;
          CRPCRequest::RemoveAllCommands(this, v28);
          return (unsigned int)PaddingSize;
        }
        v25 = 1387529;
        goto LABEL_10;
      }
    }
    v13 = v88;
    goto LABEL_18;
  }
LABEL_19:
  Param = CRPCRequest::FinishSendingLastParam(this);
  v24 = 0;
  PaddingSize = Param;
  if ( Param < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_12;
    v26 = (unsigned int)Param;
    v25 = 1412105;
    goto LABEL_11;
  }
  if ( v15 > 0x3B )
  {
    if ( v15 != 60 )
    {
      if ( v15 == 61 )
        goto LABEL_28;
      if ( v15 == 62 )
      {
LABEL_36:
        v87 = 109;
        goto LABEL_38;
      }
      if ( v15 != 122 )
      {
        if ( v15 != 127 )
          goto LABEL_38;
        goto LABEL_35;
      }
    }
    v87 = 110;
    goto LABEL_38;
  }
  switch ( v15 )
  {
    case ';':
      goto LABEL_36;
    case '0':
      goto LABEL_35;
    case '2':
      v87 = 104;
      goto LABEL_38;
  }
  if ( ((v15 - 52) & 0xFFFFFFFB) == 0 )
  {
LABEL_35:
    v87 = 38;
    goto LABEL_38;
  }
  if ( v15 == 58 )
LABEL_28:
    v87 = 111;
LABEL_38:
  if ( !*((_DWORD *)this + 135) && a2 && *a2 )
  {
    _mm_lfence();
    v30 = CRPCRequest::AddParamName(this, (struct RPCParamHead *)&v95, a2);
    v24 = 0;
    PaddingSize = v30;
    if ( v30 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_12;
      v26 = (unsigned int)v30;
      v25 = 1423369;
      goto LABEL_11;
    }
    v21 = DestinationSize;
    v31 = &v96;
    v32 = 6;
    v94 = 12;
    v33 = 2;
  }
  else
  {
    v95 = 0;
    v31 = (unsigned __int8 *)&v95;
    v33 = 3;
    v94 = 13;
    v32 = 7;
  }
  v34 = v87;
  Source = v31;
  v96 = a3;
  v97 = v87;
  if ( v87 <= 0x62u )
  {
    if ( v87 == 98 )
    {
      if ( (a3 & 0x100) != 0 )
        v21 = 0;
      DestinationSize = v21;
    }
    else
    {
      if ( v87 > 0x28u )
      {
        if ( v87 == 41 || v87 == 42 || v87 == 43 )
        {
          if ( (a3 & 0x100) != 0 )
            v21 = 0;
          v62 = *((_BYTE *)v90 + 8);
          DestinationSize = v21;
          Destination[1] = v21;
          Destination[0] = v62;
          goto LABEL_91;
        }
        if ( v87 != 45 && v87 != 47 )
          goto LABEL_56;
LABEL_87:
        if ( (a3 & 0x100) == 0 )
        {
          Destination[1] = v21;
LABEL_90:
          Destination[0] = v20;
LABEL_91:
          v33 += 2LL;
          SourceSize = 2;
          v35 = 2;
          goto LABEL_78;
        }
LABEL_89:
        Destination[1] = 0;
        DestinationSize = 0;
        goto LABEL_90;
      }
      if ( v87 == 40 )
      {
        if ( (a3 & 0x100) != 0 )
          v21 = 0;
        ++v33;
        DestinationSize = v21;
        Destination[0] = v21;
        goto LABEL_77;
      }
      if ( v87 != 34 )
      {
        if ( v87 != 35 )
        {
          if ( v87 != 36 )
          {
            if ( v87 == 37 )
              goto LABEL_87;
            if ( v87 != 38 )
            {
              if ( v87 != 39 )
              {
LABEL_56:
                v35 = 1;
                v36 = v88;
                goto LABEL_57;
              }
              goto LABEL_87;
            }
          }
LABEL_134:
          if ( (a3 & 0x100) == 0 )
          {
            Destination[0] = v21;
            Destination[1] = v21;
            goto LABEL_91;
          }
          goto LABEL_89;
        }
        goto LABEL_136;
      }
      if ( (a3 & 0x100) != 0 )
      {
        *(_QWORD *)Destination = 0xFFFFFFFF00000000uLL;
        DestinationSize = 0;
        goto LABEL_76;
      }
    }
    *(_DWORD *)&Destination[4] = v21;
    *(_DWORD *)Destination = v21;
LABEL_76:
    v33 += 8LL;
LABEL_77:
    v35 = 1;
LABEL_78:
    v36 = v88;
    goto LABEL_57;
  }
  if ( v87 > 0xA7u )
  {
    if ( v87 == 173 || v87 == 175 || v87 == 231 || v87 == 239 )
      goto LABEL_108;
    if ( v87 == 240 || v87 == 241 )
    {
      _mm_lfence();
      v57 = (unsigned int *)((char *)this + 48);
      v68 = *((unsigned int *)this + 16) - *(_QWORD *)(*((_QWORD *)this + 7) + 8LL);
      _mm_lfence();
      if ( v33 >= v68 )
      {
        PaddingSize = BATCHCTX::QueuePacket(
                        *(BATCHCTX **)v57,
                        *(void **)(*(_QWORD *)v57 + 112LL),
                        v33,
                        v31,
                        3,
                        *((_DWORD *)this + 17),
                        0);
        if ( PaddingSize < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_12;
          v25 = 1588233;
          goto LABEL_10;
        }
      }
      else
      {
        memcpy_s((void *const)(**((_QWORD **)this + 7) + *(_QWORD *)(*((_QWORD *)this + 7) + 8LL)), v33, v31, v33);
        *(_QWORD *)(*((_QWORD *)this + 7) + 8LL) += v33;
      }
      _mm_lfence();
      v59 = v87;
      PaddingSize = CRPCPolicy::WriteUDTXmlHeader((CRPCRequest *)((char *)this + 48), v87, a3, &DestinationSize, v90);
      if ( PaddingSize >= 0 )
      {
        v36 = v88;
        goto LABEL_70;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_12;
      v25 = 1598473;
LABEL_10:
      v26 = (unsigned int)PaddingSize;
LABEL_11:
      _mm_lfence();
      bidTraceHR(0, v25, v26, v24);
      goto LABEL_12;
    }
    if ( v87 != 245 )
      goto LABEL_77;
    v33 += 5LL;
    v35 = 1;
    Destination[2] = *((_BYTE *)v90 + 9);
    if ( (a3 & 0x100) != 0 )
    {
      *(_WORD *)Destination = v20;
      v36 = v88;
      *(_WORD *)&Destination[3] = -1;
      DestinationSize = 0;
      goto LABEL_57;
    }
    *(_WORD *)Destination = v21;
    *(_WORD *)&Destination[3] = v21;
    goto LABEL_133;
  }
  switch ( v87 )
  {
    case 0xA7u:
      goto LABEL_108;
    case 0x63u:
LABEL_136:
      memcpy_s(&Destination[4], 5u, (char *)v90 + 8, 5u);
      if ( (a3 & 0x100) != 0 )
      {
        *(_DWORD *)&Destination[9] = -1;
        *(_DWORD *)Destination = 0;
        DestinationSize = 0;
      }
      else
      {
        *(_DWORD *)&Destination[9] = v21;
        *(_DWORD *)Destination = v21;
      }
      v33 += 13LL;
      goto LABEL_77;
    case 0x68u:
      goto LABEL_134;
    case 0x6Au:
    case 0x6Cu:
      if ( (a3 & 0x200) != 0 )
      {
        v35 = 1;
      }
      else
      {
        if ( (a3 & 0x100) != 0 )
        {
          if ( v92 )
          {
            if ( v21 - 2 > 0x11 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                v65 = 1536009;
                goto LABEL_120;
              }
              goto LABEL_121;
            }
            *(_WORD *)&Destination[1] = *(_WORD *)v92;
          }
          else
          {
            strcpy(&Destination[1], "&");
          }
          v91 = 0;
          LOBYTE(v66) = 0;
          DestinationSize = 0;
        }
        else
        {
          if ( v21 - 2 > 0x11 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v65 = 1510409;
              goto LABEL_120;
            }
LABEL_121:
            PaddingSize = -2147024809;
            goto LABEL_12;
          }
          if ( !v92 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v65 = 1516553;
LABEL_120:
              PaddingSize = bidTraceHR(0, v65, 2147942487LL, 0);
              goto LABEL_12;
            }
            goto LABEL_121;
          }
          v66 = v21 - 2;
          Destination[1] = *(_BYTE *)v92;
          v67 = *((_BYTE *)v92 + 1);
          v92 = (char *)v92 + 2;
          Destination[2] = v67;
          DestinationSize = v66;
        }
        Destination[0] = 17;
        v33 += 4LL;
        SourceSize = 4;
        v35 = 4;
        Destination[3] = v66;
      }
LABEL_133:
      v36 = v88;
      goto LABEL_57;
    case 0x6Du:
    case 0x6Eu:
    case 0x6Fu:
      goto LABEL_134;
  }
  if ( v87 != 165 )
    goto LABEL_56;
LABEL_108:
  v63 = v87 & 0xB2;
  if ( (a3 & 0x100) != 0 )
  {
    DestinationSize = 0;
    if ( v20 == 0xFFFF )
    {
      if ( v63 == -94 )
      {
        memcpy_s(&Destination[2], 5u, (char *)v90 + 8, 5u);
        *(_QWORD *)&Destination[7] = -1;
        v35 = 8;
        v73 = 15;
      }
      else
      {
        v35 = 3;
        *(_QWORD *)&Destination[2] = -1;
        v73 = 10;
      }
      *(_WORD *)Destination = -1;
      v33 += v73;
    }
    else
    {
      v74 = 2;
      if ( v20 )
        v74 = v20;
      if ( v63 != -94 )
      {
        *(_WORD *)Destination = v74;
        v33 += 4LL;
        *(_WORD *)&Destination[2] = -1;
        v35 = 3;
        SourceSize = 3;
        goto LABEL_195;
      }
      memcpy_s(&Destination[2], 5u, (char *)v90 + 8, 5u);
      v33 += 9LL;
      *(_WORD *)Destination = v74;
      v35 = 8;
      *(_WORD *)&Destination[7] = -1;
    }
    SourceSize = v35;
LABEL_195:
    v36 = v88;
    goto LABEL_57;
  }
  if ( v20 == 0xFFFF )
  {
    if ( v63 == -94 )
    {
      memcpy_s(&Destination[2], 5u, (char *)v90 + 8, 5u);
      *(_WORD *)Destination = -1;
      if ( v21 == -1 )
      {
        v64 = a3 & 0x200;
      }
      else
      {
        v64 = a3 & 0x200;
        if ( (a3 & 0x200) == 0 )
        {
          *(_QWORD *)&Destination[7] = v21;
          goto LABEL_161;
        }
      }
      *(_QWORD *)&Destination[7] = -2;
LABEL_161:
      v36 = v88;
      v33 += 15LL;
      v35 = 8;
      SourceSize = 8;
      if ( !v88 )
        goto LABEL_175;
      if ( !v64 )
        goto LABEL_175;
      v69 = a11;
      if ( !a11 )
        goto LABEL_175;
      *(_WORD *)&Destination[7] = a11;
LABEL_174:
      v33 = v32;
      *(_WORD *)Destination = v69;
LABEL_175:
      *((_DWORD *)this + 20) = 1;
      goto LABEL_57;
    }
    *(_WORD *)Destination = -1;
    if ( v21 == -1 )
    {
      v70 = a3 & 0x200;
    }
    else
    {
      v70 = a3 & 0x200;
      if ( (a3 & 0x200) == 0 )
      {
        *(_QWORD *)&Destination[2] = v21;
        goto LABEL_170;
      }
    }
    *(_QWORD *)&Destination[2] = -2;
LABEL_170:
    v36 = v88;
    v33 += 10LL;
    SourceSize = 3;
    v35 = 3;
    if ( !v88 )
      goto LABEL_175;
    if ( !v70 )
      goto LABEL_175;
    v69 = a11;
    if ( !a11 )
      goto LABEL_175;
    *(_WORD *)&Destination[2] = a11;
    goto LABEL_174;
  }
  v71 = 2;
  if ( v20 )
    v71 = v20;
  if ( v63 == -94 )
  {
    memcpy_s(&Destination[2], 5u, (char *)v90 + 8, 5u);
    v34 = v87;
    v35 = 8;
    *(_WORD *)&Destination[7] = v21;
    v72 = 9;
  }
  else
  {
    *(_WORD *)&Destination[2] = v21;
    v35 = 3;
    v72 = 4;
  }
  v36 = v88;
  v33 += v72;
  SourceSize = v35;
  *(_WORD *)Destination = v71;
  if ( !v88 )
  {
    _mm_lfence();
    PaddingSize = CRPCRequest::FindPaddingSize(this, v34, (struct RPCParamHead *)&v95);
    if ( PaddingSize < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_12;
      v25 = 1770505;
      goto LABEL_10;
    }
    v35 = SourceSize;
  }
LABEL_57:
  _mm_lfence();
  PaddingSize = 0;
  if ( v36 )
  {
    v37 = 3;
    v38 = &v99;
    v39 = &v95;
    do
    {
      v40 = *((_OWORD *)v39 + 1);
      *(_OWORD *)v38 = *(_OWORD *)v39;
      v41 = *((_OWORD *)v39 + 2);
      *((_OWORD *)v38 + 1) = v40;
      v42 = *((_OWORD *)v39 + 3);
      *((_OWORD *)v38 + 2) = v41;
      v43 = *((_OWORD *)v39 + 4);
      *((_OWORD *)v38 + 3) = v42;
      v44 = *((_OWORD *)v39 + 5);
      *((_OWORD *)v38 + 4) = v43;
      v45 = *((_OWORD *)v39 + 6);
      *((_OWORD *)v38 + 5) = v44;
      v46 = *((_OWORD *)v39 + 7);
      v39 += 128;
      *((_OWORD *)v38 + 6) = v45;
      v38 += 128;
      *((_OWORD *)v38 - 1) = v46;
      --v37;
    }
    while ( v37 );
    *(_QWORD *)v38 = *(_QWORD *)v39;
    *((_DWORD *)v38 + 2) = *((_DWORD *)v39 + 2);
    *((_WORD *)v38 + 6) = *((_WORD *)v39 + 6);
    if ( (a3 & 0x200) != 0 )
    {
      v47 = (char *)this + 128;
      v48 = 3;
      v49 = &v95;
      do
      {
        v50 = *((_OWORD *)v49 + 1);
        *(_OWORD *)v47 = *(_OWORD *)v49;
        v51 = *((_OWORD *)v49 + 2);
        *((_OWORD *)v47 + 1) = v50;
        v52 = *((_OWORD *)v49 + 3);
        *((_OWORD *)v47 + 2) = v51;
        v53 = *((_OWORD *)v49 + 4);
        *((_OWORD *)v47 + 3) = v52;
        v54 = *((_OWORD *)v49 + 5);
        *((_OWORD *)v47 + 4) = v53;
        v55 = *((_OWORD *)v49 + 6);
        *((_OWORD *)v47 + 5) = v54;
        v56 = *((_OWORD *)v49 + 7);
        v49 += 128;
        *((_OWORD *)v47 + 6) = v55;
        v47 += 128;
        *((_OWORD *)v47 - 1) = v56;
        --v48;
      }
      while ( v48 );
      *(_QWORD *)v47 = *(_QWORD *)v49;
      *((_DWORD *)v47 + 2) = *((_DWORD *)v49 + 2);
      *((_WORD *)v47 + 6) = *((_WORD *)v49 + 6);
      *((_QWORD *)this + 66) = v35;
    }
    v96 |= 8u;
    v97 = -91;
    *(_WORD *)Destination = -1;
    *(_QWORD *)&Destination[2] = -1;
    if ( (a3 & 0x100) == 0 )
    {
      *((_DWORD *)this + 20) = 1;
      *(_QWORD *)&Destination[2] = -2;
    }
    v33 = v94;
  }
  v57 = (unsigned int *)((char *)this + 48);
  v58 = *((unsigned int *)this + 16) - *(_QWORD *)(*((_QWORD *)this + 7) + 8LL);
  _mm_lfence();
  if ( v33 >= v58 )
  {
    PaddingSize = BATCHCTX::QueuePacket(
                    *(BATCHCTX **)v57,
                    *(void **)(*(_QWORD *)v57 + 112LL),
                    v33,
                    (const unsigned __int8 *)Source,
                    3,
                    *((_DWORD *)this + 17),
                    0);
    if ( PaddingSize >= 0 )
      goto LABEL_69;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_12;
    v25 = 1921033;
    goto LABEL_10;
  }
  memcpy_s((void *const)(**((_QWORD **)this + 7) + *(_QWORD *)(*((_QWORD *)this + 7) + 8LL)), v33, Source, v33);
  *(_QWORD *)(*((_QWORD *)this + 7) + 8LL) += v33;
LABEL_69:
  v59 = v87;
LABEL_70:
  if ( !v36 || (a3 & 0x100) != 0 )
  {
    v60 = DestinationSize;
    v61 = v92;
  }
  else
  {
    _mm_lfence();
    v60 = v91;
    v61 = (void *)*((_QWORD *)this + 2);
    DestinationSize = v91;
  }
  v75 = *((_DWORD *)this + 20);
  if ( (a3 & 0x200) != 0 )
  {
    *((_WORD *)this + 49) = a3;
    *((_BYTE *)this + 100) = v59;
    if ( v75 )
      v60 = -1;
    *((_QWORD *)this + 15) = v36;
    *((_QWORD *)this + 13) = v60;
  }
  else
  {
    if ( v75 )
    {
      v76 = (CRPCPolicy *)v57;
      if ( v61 )
      {
        if ( v60 )
        {
          _mm_lfence();
          v76 = (CRPCRequest *)((char *)this + 48);
          v77 = CRPCPolicy::WriteChunk((CRPCRequest *)((char *)this + 48), v61, DestinationSize);
          PaddingSize = v77;
          if ( v77 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_12;
            v79 = 1942537;
LABEL_210:
            _mm_lfence();
            bidTraceHR(0, v79, (unsigned int)v77, v78);
            goto LABEL_12;
          }
        }
      }
      if ( *((_DWORD *)v76 + 8) )
      {
        _mm_lfence();
        v77 = CRPCPolicy::WriteChunk(v76, 0, 0);
        PaddingSize = v77;
        if ( v77 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_12;
          v79 = 1946633;
          goto LABEL_210;
        }
      }
      else
      {
        PaddingSize = 0;
      }
      _mm_lfence();
      v80 = *(_QWORD *)this;
      *((_WORD *)this + 49) = 0;
      *((_BYTE *)this + 100) = 0;
      *((_QWORD *)this + 13) = 0;
      *((_QWORD *)this + 1) = 0;
      *((_QWORD *)this + 14) = 0;
      *((_QWORD *)this + 15) = 0;
      if ( v80 )
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
      *(_QWORD *)this = 0;
      *((_DWORD *)this + 20) = 0;
    }
    else
    {
      if ( v61 && v60 )
      {
        _mm_lfence();
        v81 = DestinationSize < (unsigned __int64)v57[4] - *(_QWORD *)(*((_QWORD *)v57 + 1) + 8LL);
        _mm_lfence();
        if ( v81 )
        {
          v82 = DestinationSize;
          memcpy_s(
            (void *const)(**((_QWORD **)v57 + 1) + *(_QWORD *)(*((_QWORD *)v57 + 1) + 8LL)),
            DestinationSize,
            v61,
            DestinationSize);
          *(_QWORD *)(*((_QWORD *)v57 + 1) + 8LL) += v82;
          PaddingSize = 0;
        }
        else
        {
          v77 = BATCHCTX::QueuePacket(
                  *(BATCHCTX **)v57,
                  *(void **)(*(_QWORD *)v57 + 112LL),
                  DestinationSize,
                  (const unsigned __int8 *)v61,
                  3,
                  v57[5],
                  0);
          PaddingSize = v77;
          if ( v77 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_12;
            v79 = 1956873;
            goto LABEL_210;
          }
        }
      }
      if ( *((_QWORD *)this + 14) )
      {
        _mm_lfence();
        v77 = CRPCPolicy::WritePadding((CRPCPolicy *)v57, v59, *((_QWORD *)this + 14));
        PaddingSize = v77;
        if ( v77 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_12;
          v79 = 1965065;
          goto LABEL_210;
        }
        *((_QWORD *)this + 14) = 0;
      }
    }
    if ( v36 )
    {
      _mm_lfence();
      v83 = SourceSize;
      v84 = v57[4] - *(_QWORD *)(*((_QWORD *)v57 + 1) + 8LL);
      _mm_lfence();
      if ( v83 >= v84 )
      {
        v77 = BATCHCTX::QueuePacket(
                *(BATCHCTX **)v57,
                *(void **)(*(_QWORD *)v57 + 112LL),
                SourceSize,
                v100,
                3,
                v57[5],
                0);
        PaddingSize = v77;
        if ( v77 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_12;
          v79 = 1973257;
          goto LABEL_210;
        }
      }
      else
      {
        memcpy_s(
          (void *const)(**((_QWORD **)v57 + 1) + *(_QWORD *)(*((_QWORD *)v57 + 1) + 8LL)),
          SourceSize,
          v100,
          SourceSize);
        *(_QWORD *)(*((_QWORD *)v57 + 1) + 8LL) += SourceSize;
      }
      _mm_lfence();
      sqlencrypt::ColumnEncryptionInputParameterInfo::ColumnEncryptionInputParameterInfo(
        (sqlencrypt::ColumnEncryptionInputParameterInfo *)v101,
        (struct _TDSCRYPTOMETADATA *)((char *)v36 + 3184));
      v85 = v57[4] - *(_QWORD *)(*((_QWORD *)v57 + 1) + 8LL);
      _mm_lfence();
      if ( v85 <= 0x17 )
      {
        PaddingSize = BATCHCTX::QueuePacket(
                        *(BATCHCTX **)v57,
                        *(void **)(*(_QWORD *)v57 + 112LL),
                        0x17u,
                        v102,
                        3,
                        v57[5],
                        0);
      }
      else
      {
        memcpy_s((void *const)(**((_QWORD **)v57 + 1) + *(_QWORD *)(*((_QWORD *)v57 + 1) + 8LL)), 0x17u, v102, 0x17u);
        *(_QWORD *)(*((_QWORD *)v57 + 1) + 8LL) += 23LL;
        PaddingSize = 0;
      }
    }
  }
  _mm_lfence();
  if ( v90 && *(_QWORD *)v90 )
    **(_WORD **)v90 = *((_WORD *)this + 48);
  ++*((_WORD *)this + 48);
  return (unsigned int)PaddingSize;
}

```

## disassembly

```asm
0x100459968  push    rbp
0x10045996a  push    rbx
0x10045996b  push    rsi
0x10045996c  push    rdi
0x10045996d  push    r12
0x10045996f  push    r13
0x100459971  push    r14
0x100459973  push    r15
0x100459975  lea     rbp, [rsp-2E8h]
0x10045997d  sub     rsp, 3E8h
0x100459984  mov     rax, cs:__security_cookie
0x10045998b  xor     rax, rsp
0x10045998e  mov     [rbp+320h+var_50], rax
0x100459995  mov     rbx, [rbp+320h+arg_30]
0x10045999c  mov     rsi, rcx
0x10045999f  mov     rcx, [rbp+320h+arg_40]
0x1004599a6  mov     r15, rdx
0x1004599a9  movzx   r14d, r9b
0x1004599ad  movzx   r13d, r8w
0x1004599b1  mov     r8, [rbp+320h+arg_38]
0x1004599b8  xor     r10d, r10d
0x1004599bb  lea     r9, [rsi+10h]
0x1004599bf  mov     [rsp+420h+var_3D0], r14b
0x1004599c4  mov     rdx, [r9]
0x1004599c7  mov     [rsp+420h+var_3A8], rbx
0x1004599cc  mov     [rsp+420h+var_3B8], r8
0x1004599d1  mov     [rsp+420h+var_3C8], rcx
0x1004599d6  mov     [rsp+420h+SourceSize], 1
0x1004599df  test    rdx, rdx
0x1004599e2  jz      short loc_100459A0C
0x1004599e4  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004599eb  mov     rax, [rcx]
0x1004599ee  mov     rax, [rax+80h]
0x1004599f5  call    cs:__guard_dispatch_icall_fptr
0x1004599fb  mov     rcx, [rsp+420h+var_3C8]
0x100459a00  lea     r9, [rsi+10h]
0x100459a04  mov     r8, [rsp+420h+var_3B8]
0x100459a09  xor     r10d, r10d
0x100459a0c  mov     r12, [rbp+320h+arg_28]
0x100459a13  mov     eax, 0FFFFh
0x100459a18  mov     rdi, [rbp+320h+DestinationSize]
0x100459a1f  mov     [r9], r10
0x100459a22  mov     [rsp+420h+var_3B0], r10d
0x100459a27  test    rcx, rcx
0x100459a2a  jz      loc_100459B3D
0x100459a30  bt      r13w, 9
0x100459a36  jb      loc_100459B02
0x100459a3c  lea     rax, [rcx+0C70h]
0x100459a43  mov     rdx, rbx
0x100459a46  lea     rcx, [rsp+420h+var_3B0]
0x100459a4b  mov     [rsp+420h+var_3E0], rcx; unsigned int *
0x100459a50  bt      r13w, 8
0x100459a56  mov     rcx, [rsi+20h]; void *
0x100459a5a  mov     [rsp+420h+var_3E8], r9; unsigned __int8 **
0x100459a5f  cmovb   rdx, r10; void *
0x100459a63  mov     r9, [rbp+320h+arg_48]; unsigned __int64
0x100459a6a  mov     [rsp+420h+var_3F0], rax; struct sqlencrypt::CipherMetadata *
0x100459a6f  mov     al, [r8+8]
0x100459a73  mov     r8, rdi; unsigned __int64
0x100459a76  mov     byte ptr [rsp+420h+var_3F8], al; char
0x100459a7a  mov     byte ptr [rsp+420h+var_400], r14b; char
0x100459a7f  call    ?EncryptParam@@YAJPEAXPEBX_K2EEAEAVCipherMetadata@sqlencrypt@@AEAPEAEAEAK@Z; EncryptParam(void *,void const *,unsigned __int64,unsigned __int64,uchar,uchar,sqlencrypt::CipherMetadata &,uchar * &,ulong &)
0x100459a84  mov     ebx, eax
0x100459a86  test    eax, eax
0x100459a88  jns     loc_100459B29
0x100459a8e  mov     r14d, 2
0x100459a94  test    byte ptr cs:_bidGblFlags, r14b
0x100459a9b  jz      short loc_100459AAF
0x100459a9d  mov     edx, 152C09h
0x100459aa2  mov     r8d, ebx
0x100459aa5  lfence
0x100459aa8  xor     ecx, ecx
0x100459aaa  call    _bidTraceHR
0x100459aaf  xor     r13d, r13d
0x100459ab2  mov     rdx, [rsi]
0x100459ab5  mov     [rsi+62h], r13w
0x100459aba  mov     [rsi+64h], r13b
0x100459abe  mov     [rsi+68h], r13
0x100459ac2  mov     [rsi+8], r13
0x100459ac6  mov     [rsi+70h], r13
0x100459aca  mov     [rsi+78h], r13
0x100459ace  test    rdx, rdx
0x100459ad1  jz      short loc_100459AEA
0x100459ad3  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100459ada  mov     rax, [rcx]
0x100459add  mov     rax, [rax+80h]
0x100459ae4  call    cs:__guard_dispatch_icall_fptr
0x100459aea  mov     rdx, [rsi+20h]; void *
0x100459aee  mov     rcx, rsi; this
0x100459af1  mov     [rsi], r13
0x100459af4  mov     [rsi+50h], r13d
0x100459af8  call    ?RemoveAllCommands@CRPCRequest@@QEAAJPEAX@Z; CRPCRequest::RemoveAllCommands(void *)
0x100459afd  jmp     loc_10045A841
0x100459b02  cmp     r12, rax
0x100459b05  jnz     short loc_100459B2E
0x100459b07  lea     rax, [rcx+0C70h]
0x100459b0e  xor     r9d, r9d; unsigned __int8 **
0x100459b11  mov     rcx, [rsi+20h]; void *
0x100459b15  xor     r8d, r8d; unsigned __int64
0x100459b18  mov     [rsp+420h+var_3F8], rax; struct sqlencrypt::CipherMetadata *
0x100459b1d  xor     edx, edx; unsigned __int8 *
0x100459b1f  mov     [rsp+420h+var_400], r10; unsigned int *
0x100459b24  call    ?EncryptStream@@YAJPEAXPEAE_KPEAPEAEPEAKAEAVCipherMetadata@sqlencrypt@@@Z; EncryptStream(void *,uchar *,unsigned __int64,uchar * *,ulong *,sqlencrypt::CipherMetadata &)
0x100459b29  mov     rcx, [rsp+420h+var_3C8]
0x100459b2e  mov     rax, [rsp+420h+var_3B8]
0x100459b33  mov     [rcx+8], r14b
0x100459b37  mov     al, [rax+8]
0x100459b3a  mov     [rcx+9], al
0x100459b3d  mov     rcx, rsi; this
0x100459b40  call    ?FinishSendingLastParam@CRPCRequest@@AEAAJXZ; CRPCRequest::FinishSendingLastParam(void)
0x100459b45  xor     r9d, r9d
0x100459b48  mov     ebx, eax
0x100459b4a  test    eax, eax
0x100459b4c  jns     short loc_100459B6C
0x100459b4e  lea     r14d, [r9+2]
0x100459b52  test    byte ptr cs:_bidGblFlags, r14b
0x100459b59  jz      loc_100459AAF
0x100459b5f  mov     r8d, eax
0x100459b62  mov     edx, 158C09h
0x100459b67  jmp     loc_100459AA5
0x100459b6c  mov     ecx, r14d
0x100459b6f  mov     r10d, 5
0x100459b75  cmp     r14d, 3Bh ; ';'
0x100459b79  ja      short loc_100459BA5
0x100459b7b  jz      short loc_100459BC5
0x100459b7d  cmp     ecx, 30h ; '0'
0x100459b80  jz      short loc_100459BBE
0x100459b82  cmp     ecx, 32h ; '2'
0x100459b85  jz      short loc_100459B9E
0x100459b87  lea     eax, [r14-34h]
0x100459b8b  test    eax, 0FFFFFFFBh
0x100459b90  jz      short loc_100459BBE
0x100459b92  cmp     ecx, 3Ah ; ':'
0x100459b95  jnz     short loc_100459BD1
0x100459b97  mov     [rsp+420h+var_3D0], 6Fh ; 'o'
0x100459b9c  jmp     short loc_100459BD1
0x100459b9e  mov     [rsp+420h+var_3D0], 68h ; 'h'
0x100459ba3  jmp     short loc_100459BD1
0x100459ba5  sub     ecx, 3Ch ; '<'
0x100459ba8  jz      short loc_100459BCC
0x100459baa  sub     ecx, 1
0x100459bad  jz      short loc_100459B97
0x100459baf  sub     ecx, 1
0x100459bb2  jz      short loc_100459BC5
0x100459bb4  sub     ecx, 3Ch ; '<'
0x100459bb7  jz      short loc_100459BCC
0x100459bb9  cmp     ecx, r10d
0x100459bbc  jnz     short loc_100459BD1
0x100459bbe  mov     [rsp+420h+var_3D0], 26h ; '&'
0x100459bc3  jmp     short loc_100459BD1
0x100459bc5  mov     [rsp+420h+var_3D0], 6Dh ; 'm'
0x100459bca  jmp     short loc_100459BD1
0x100459bcc  mov     [rsp+420h+var_3D0], 6Eh ; 'n'
0x100459bd1  mov     r11d, 3
0x100459bd7  lea     r14d, [r11-1]
0x100459bdb  cmp     [rsi+21Ch], r9d
0x100459be2  jnz     short loc_100459C49
0x100459be4  test    r15, r15
0x100459be7  jz      short loc_100459C49
0x100459be9  cmp     [r15], r9w
0x100459bed  jz      short loc_100459C49
0x100459bef  lfence
0x100459bf2  mov     r8, r15; unsigned __int16 *
0x100459bf5  lea     rdx, [rbp+320h+var_390]; struct RPCParamHead *
0x100459bf9  mov     rcx, rsi; this
0x100459bfc  call    ?AddParamName@CRPCRequest@@AEAAJPEAURPCParamHead@@PEBG@Z; CRPCRequest::AddParamName(RPCParamHead *,ushort const *)
0x100459c01  xor     r9d, r9d
0x100459c04  mov     ebx, eax
0x100459c06  test    eax, eax
0x100459c08  jns     short loc_100459C24
0x100459c0a  test    byte ptr cs:_bidGblFlags, r14b
0x100459c11  jz      loc_100459AAF
0x100459c17  mov     r8d, eax
0x100459c1a  mov     edx, 15B809h
0x100459c1f  jmp     loc_100459AA5
0x100459c24  mov     rdi, [rbp+320h+DestinationSize]
0x100459c2b  lea     r8, [rbp+320h+var_38F]
0x100459c2f  mov     ebx, 6
0x100459c34  mov     [rbp+320h+var_398], 0Ch
0x100459c3c  mov     r15, r14
0x100459c3f  lea     r10d, [rbx-1]
0x100459c43  lea     r11d, [rbx-3]
0x100459c47  jmp     short loc_100459C61
0x100459c49  mov     [rbp+320h+var_390], r9b
0x100459c4d  lea     r8, [rbp+320h+var_390]; Source
0x100459c51  mov     r15, r11
0x100459c54  mov     [rbp+320h+var_398], 0Dh
0x100459c5c  mov     ebx, 7
0x100459c61  movzx   edx, [rsp+420h+var_3D0]; unsigned __int8
0x100459c66  mov     [rbp+320h+Source], r8
0x100459c6a  mov     ecx, edx
0x100459c6c  mov     [rbp+320h+var_38F], r13b
0x100459c70  mov     [rbp+320h+var_38E], dl
0x100459c73  cmp     edx, 62h ; 'b'
0x100459c76  ja      loc_100459F59
0x100459c7c  jz      loc_100459F3F
0x100459c82  cmp     edx, 28h ; '('
0x100459c85  ja      loc_100459ECE
0x100459c8b  jz      loc_100459EB0
0x100459c91  sub     ecx, 22h ; '"'
0x100459c94  jz      loc_100459E77
0x100459c9a  sub     ecx, 1
0x100459c9d  jz      loc_10045A132
0x100459ca3  sub     ecx, 1
0x100459ca6  jz      loc_10045A115
0x100459cac  sub     ecx, 1
0x100459caf  jz      loc_100459EEB
0x100459cb5  sub     ecx, 1
0x100459cb8  jz      loc_10045A115
0x100459cbe  cmp     ecx, 1
0x100459cc1  jz      loc_100459EEB
0x100459cc7  mov     r8, [rsp+420h+SourceSize]
0x100459ccc  mov     r12, [rsp+420h+var_3C8]
0x100459cd1  mov     r10d, 100h
0x100459cd7  mov     r11d, 200h
0x100459cdd  mov     edi, 0FFFFh
0x100459ce2  lfence
0x100459ce5  xor     ebx, ebx
0x100459ce7  test    r12, r12
0x100459cea  jz      loc_100459E08
0x100459cf0  lea     eax, [rbx+3]
0x100459cf3  lea     r9d, [rax+7Dh]
0x100459cf7  lea     rcx, [rbp+320h+var_200]
0x100459cfe  lea     rdx, [rbp+320h+var_390]
0x100459d02  movups  xmm0, xmmword ptr [rdx]
0x100459d05  movups  xmm1, xmmword ptr [rdx+10h]
0x100459d09  movups  xmmword ptr [rcx], xmm0
0x100459d0c  movups  xmm0, xmmword ptr [rdx+20h]
0x100459d10  movups  xmmword ptr [rcx+10h], xmm1
0x100459d14  movups  xmm1, xmmword ptr [rdx+30h]
0x100459d18  movups  xmmword ptr [rcx+20h], xmm0
0x100459d1c  movups  xmm0, xmmword ptr [rdx+40h]
0x100459d20  movups  xmmword ptr [rcx+30h], xmm1
0x100459d24  movups  xmm1, xmmword ptr [rdx+50h]
0x100459d28  movups  xmmword ptr [rcx+40h], xmm0
0x100459d2c  movups  xmm0, xmmword ptr [rdx+60h]
0x100459d30  movups  xmmword ptr [rcx+50h], xmm1
0x100459d34  movups  xmm1, xmmword ptr [rdx+70h]
0x100459d38  add     rdx, r9
0x100459d3b  movups  xmmword ptr [rcx+60h], xmm0
0x100459d3f  add     rcx, r9
0x100459d42  movups  xmmword ptr [rcx-10h], xmm1
0x100459d46  sub     rax, 1
0x100459d4a  jnz     short loc_100459D02
0x100459d4c  mov     rax, [rdx]
0x100459d4f  mov     [rcx], rax
0x100459d52  mov     eax, [rdx+8]
0x100459d55  mov     [rcx+8], eax
0x100459d58  movzx   eax, word ptr [rdx+0Ch]
0x100459d5c  mov     [rcx+0Ch], ax
0x100459d60  test    r11w, r13w
0x100459d64  jz      short loc_100459DDB
0x100459d66  lea     rcx, [rsi+80h]
0x100459d6d  mov     eax, 3
0x100459d72  lea     rdx, [rbp+320h+var_390]
0x100459d76  movups  xmm0, xmmword ptr [rdx]
0x100459d79  movups  xmm1, xmmword ptr [rdx+10h]
0x100459d7d  movups  xmmword ptr [rcx], xmm0
0x100459d80  movups  xmm0, xmmword ptr [rdx+20h]
0x100459d84  movups  xmmword ptr [rcx+10h], xmm1
0x100459d88  movups  xmm1, xmmword ptr [rdx+30h]
0x100459d8c  movups  xmmword ptr [rcx+20h], xmm0
0x100459d90  movups  xmm0, xmmword ptr [rdx+40h]
0x100459d94  movups  xmmword ptr [rcx+30h], xmm1
0x100459d98  movups  xmm1, xmmword ptr [rdx+50h]
0x100459d9c  movups  xmmword ptr [rcx+40h], xmm0
0x100459da0  movups  xmm0, xmmword ptr [rdx+60h]
0x100459da4  movups  xmmword ptr [rcx+50h], xmm1
0x100459da8  movups  xmm1, xmmword ptr [rdx+70h]
0x100459dac  add     rdx, r9
0x100459daf  movups  xmmword ptr [rcx+60h], xmm0
0x100459db3  add     rcx, r9
0x100459db6  movups  xmmword ptr [rcx-10h], xmm1
0x100459dba  sub     rax, 1
0x100459dbe  jnz     short loc_100459D76
0x100459dc0  mov     rax, [rdx]
0x100459dc3  mov     [rcx], rax
0x100459dc6  mov     eax, [rdx+8]
0x100459dc9  mov     [rcx+8], eax
0x100459dcc  movzx   eax, word ptr [rdx+0Ch]
0x100459dd0  mov     [rcx+0Ch], ax
0x100459dd4  mov     [rsi+210h], r8
0x100459ddb  or      [rbp+320h+var_38F], 8
0x100459ddf  or      rax, 0FFFFFFFFFFFFFFFFh
0x100459de3  mov     [rbp+320h+var_38E], 0A5h
0x100459de7  mov     word ptr [rbp+320h+Destination], di
0x100459deb  mov     [rbp+320h+Destination+2], rax
0x100459def  test    r10w, r13w
0x100459df3  jnz     short loc_100459E04
0x100459df5  mov     dword ptr [rsi+50h], 1
0x100459dfc  mov     [rbp+320h+Destination+2], 0FFFFFFFFFFFFFFFEh
0x100459e04  mov     r15, [rbp+320h+var_398]
0x100459e08  lea     rdi, [rsi+30h]
0x100459e0c  mov     rax, [rdi+8]
0x100459e10  mov     ecx, [rdi+10h]
0x100459e13  sub     rcx, [rax+8]
0x100459e17  lfence
0x100459e1a  cmp     r15, rcx
0x100459e1d  jnb     loc_10045A4E3
0x100459e23  mov     rax, [rdi+8]
  ... truncated ...
```

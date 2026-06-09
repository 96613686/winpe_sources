# CDataFileWriter::WriteBLOBColumn(CBCPField *,CBCPColumn *,ushort,COLINFO *,CRecordFetcher *,CDataSource *,unsigned __int64)

- ea: `0x180119970`
- end: `0x18011a919`
- name: `?WriteBLOBColumn@CDataFileWriter@@QEAAJPEAVCBCPField@@PEAVCBCPColumn@@GPEAUCOLINFO@@PEAVCRecordFetcher@@PEAVCDataSource@@_K@Z`
- size: `4009`
- prototype: `__int64 __usercall@<rax>(CDataFileWriter *__hidden this@<rcx>, struct CBCPField *@<rdx>, struct CBCPColumn *@<r8>, unsigned __int16@<r9w>, struct COLINFO *, struct CRecordFetcher *, struct CDataSource *, unsigned __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting`

## callers

- `0x18011b110`

## callees

- `0x180003030`
- `0x180003d80`
- `0x1800138c0`
- `0x1800465a0`
- `0x18006c9e0`
- `0x18006cce0`
- `0x18006cf20`
- `0x180072f10`
- `0x1800730f0`
- `0x180106be0`
- `0x180106c90`
- `0x180106d40`
- `0x180119970`
- `0x18011afb0`
- `0x180126b40`
- `0x180129020`
- `0x1801291d0`
- `0x1801336f4`
- `0x180133bcc`
- `0x180134658`
- `0x1801a65fc`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!IsDBCSLeadByteEx` at `0x180119fea`
- `KERNEL32!IsDBCSLeadByteEx` at `0x180119fea`
- `KERNEL32!GetCPInfo` at `0x180119a54`
- `KERNEL32!GetCPInfo` at `0x180119a71`
- `KERNEL32!GetCPInfo` at `0x180119f71`
- `KERNEL32!GetCPInfo` at `0x180119a54`
- `KERNEL32!GetCPInfo` at `0x180119a71`
- `KERNEL32!GetCPInfo` at `0x180119f71`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDataFileWriter::WriteBLOBColumn(
        CDataFileWriter *this,
        struct CBCPField *a2,
        struct CBCPColumn *a3,
        unsigned __int16 a4,
        struct COLINFO *a5,
        struct CRecordFetcher *a6,
        struct CDataSource *a7,
        unsigned __int64 a8)
{
  struct CBCPField *v9; // r14
  unsigned __int16 v11; // r15
  int v12; // edi
  unsigned __int64 v13; // r13
  BOOL v14; // ebx
  BOOL v15; // eax
  UINT v16; // edx
  UINT MaxCharSize; // r8d
  unsigned __int64 v18; // r8
  int v19; // ebx
  __int64 v20; // rax
  __int64 v21; // r8
  struct COLINFO *v22; // r15
  __int64 v23; // rax
  unsigned __int64 v24; // rcx
  __int64 v25; // r9
  int v26; // eax
  unsigned __int64 v27; // r8
  int v28; // eax
  __int16 v29; // ax
  int v30; // eax
  int v31; // eax
  bool v32; // zf
  BOOL v33; // edx
  CBCPBLOBStream *v34; // rax
  CBCPBLOBStream *v35; // r15
  unsigned __int8 *v36; // rax
  char *v37; // r15
  size_t v38; // rsi
  __int64 v39; // rcx
  size_t v40; // rdi
  char *v41; // rdx
  int v42; // eax
  __int64 v43; // rsi
  unsigned __int16 v44; // di
  unsigned __int16 v45; // di
  __int64 v46; // rdi
  UINT v47; // r14d
  unsigned int v48; // esi
  BOOL v49; // eax
  UINT v50; // edx
  char v51; // cl
  int v52; // eax
  int v53; // eax
  unsigned __int8 *v54; // rsi
  int v55; // eax
  int v56; // eax
  struct tagDBTIMESTAMP *v57; // rcx
  unsigned __int64 v58; // rdx
  _DWORD *v59; // rcx
  unsigned __int64 v60; // rdx
  int v61; // edi
  int v62; // eax
  int v63; // eax
  int v64; // eax
  int v65; // eax
  int v66; // eax
  int v67; // eax
  int v68; // eax
  int v70; // [rsp+80h] [rbp-80h]
  unsigned __int16 v71; // [rsp+84h] [rbp-7Ch]
  unsigned __int16 v72; // [rsp+86h] [rbp-7Ah]
  unsigned __int64 v73; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v74; // [rsp+90h] [rbp-70h]
  int v75; // [rsp+98h] [rbp-68h]
  __int64 v76; // [rsp+A0h] [rbp-60h]
  int v77; // [rsp+A8h] [rbp-58h]
  CBCPBLOBStream *v78; // [rsp+B0h] [rbp-50h]
  struct CBCPColumn *v79; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v80; // [rsp+C0h] [rbp-40h]
  struct CBCPField *v81; // [rsp+C8h] [rbp-38h]
  struct CRecordFetcher *v82; // [rsp+D0h] [rbp-30h]
  struct COLINFO *v83; // [rsp+D8h] [rbp-28h]
  CDataSource *v84; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v85; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v86; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v87; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v88; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 v89[8]; // [rsp+108h] [rbp+8h] BYREF
  __int16 v90; // [rsp+110h] [rbp+10h]
  int v91; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v92; // [rsp+11Ch] [rbp+1Ch] BYREF
  struct _cpinfo v93; // [rsp+120h] [rbp+20h] BYREF
  size_t Size[2]; // [rsp+138h] [rbp+38h] BYREF
  __int128 v95; // [rsp+148h] [rbp+48h]
  void *Src[2]; // [rsp+158h] [rbp+58h]
  __int64 v97; // [rsp+168h] [rbp+68h] BYREF
  __int64 v98; // [rsp+170h] [rbp+70h] BYREF
  struct _cpinfo CPInfo; // [rsp+178h] [rbp+78h] BYREF

  v79 = a3;
  v9 = a2;
  v81 = a2;
  v83 = a5;
  v82 = a6;
  v84 = a7;
  v88 = a8;
  v97 = 0;
  v98 = 0;
  v73 = *((int *)a2 + 5);
  v71 = *((_WORD *)a2 + 12);
  v11 = *((_WORD *)a3 + 1);
  v72 = v11;
  v12 = *((_DWORD *)a3 + 143);
  v92 = 0;
  v13 = 0;
  v86 = 0;
  v75 = 0;
  *(_QWORD *)v89 = 0;
  v90 = 0;
  v78 = 0;
  Size[0] = 0;
  Size[1] = 0;
  v95 = 0u;
  *(_OWORD *)Src = 0;
  memset(&CPInfo, 0, sizeof(CPInfo));
  v14 = GetCPInfo(0xFDE9u, &CPInfo);
  memset(&v93, 0, sizeof(v93));
  v15 = GetCPInfo(0xFDE9u, &v93);
  v16 = 0;
  MaxCharSize = 0;
  if ( v14 )
    MaxCharSize = CPInfo.MaxCharSize;
  v18 = MaxCharSize - 1;
  if ( v15 )
    v16 = v93.MaxCharSize;
  if ( !(unsigned int)CExtByteBuffer::FInit((CExtByteBuffer *)Size, v16 - 1, v18) )
  {
    v19 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], 7578633, 2147942414LL);
    }
    goto LABEL_220;
  }
  v20 = *((_QWORD *)this + 10);
  v21 = 0;
  v76 = 0;
  v80 = 0x7FFFFFFF;
  if ( *(_BYTE *)(v20 + 2648) > 0x5Au )
  {
    v76 = 0;
    if ( v11 == 128 )
    {
      v76 = 0;
      if ( v12 )
      {
        v76 = 0;
        if ( !*((_DWORD *)v9 + 4) )
        {
          if ( *(_DWORD *)(v20 + 2680) || (v76 = 0, *(_DWORD *)(v20 + 2684)) )
          {
            if ( v73 == 2147483632 || (v76 = 0, v73 == 0x7FFFFFFF) )
              v76 = 1;
          }
        }
      }
    }
  }
  v22 = v83;
  if ( *((_DWORD *)v83 + 28) == 29 && *((_WORD *)v9 + 12) == 128 )
  {
    v23 = 2;
    if ( v88 == -1 )
      v23 = 0;
    v24 = v23 + v88;
    v88 += v23;
    v75 = 1;
  }
  else
  {
    v24 = v88;
  }
  v25 = 130;
  if ( !*((_DWORD *)v9 + 4) )
  {
    v19 = 0;
    if ( v24 )
      goto LABEL_59;
    v29 = *((_WORD *)v9 + 12);
    if ( v29 == 129 )
    {
      LOBYTE(v87) = 0;
      v30 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64, __int16 *, __int64))(*(_QWORD *)this + 16LL))(
              this,
              1,
              &v87,
              130);
      v19 = v30;
      if ( v30 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B8[0], 7644169, (unsigned int)v30);
        }
LABEL_220:
        _mm_lfence();
        v19 = CBCPErrorHandler::PostBCPErrors(0, v19);
        goto LABEL_221;
      }
    }
    else
    {
      if ( v29 != 130 )
      {
LABEL_58:
        v73 = 0;
        goto LABEL_59;
      }
      v87 = 0;
      v31 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64, __int16 *, __int64))(*(_QWORD *)this + 16LL))(
              this,
              2,
              &v87,
              130);
      v19 = v31;
      if ( v31 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B8[0], 7650313, (unsigned int)v31);
        }
        goto LABEL_220;
      }
    }
    v21 = 0;
    goto LABEL_58;
  }
  v26 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64 *, _QWORD, __int64))(*(_QWORD *)this + 32LL))(
          this,
          &v97,
          0,
          130);
  v19 = v26;
  if ( v26 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], 7607305, (unsigned int)v26);
    }
    goto LABEL_220;
  }
  if ( v12 && v88 && (_mm_lfence(), *(_BYTE *)(*((_QWORD *)this + 10) + 2648LL) >= 0x5Au) && v73 == 2147483632 )
  {
    _mm_lfence();
    v27 = -1;
  }
  else
  {
    _mm_lfence();
    switch ( *(_BYTE *)v9 )
    {
      case '(':
        v27 = 3;
        break;
      case ')':
        v27 = 5;
        break;
      case '*':
        v27 = 8;
        break;
      case '+':
        v27 = 10;
        break;
      case 'z':
        v27 = 4;
        break;
      default:
        v27 = v88;
        break;
    }
    v88 = v27;
  }
  v28 = CDataFileWriter::WriteNonNullPrefix(this, *((_DWORD *)v9 + 4), v27, *((_DWORD *)v9 + 5), &v73);
  v19 = v28;
  if ( v28 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], 7630857, (unsigned int)v28);
    }
    goto LABEL_220;
  }
  v21 = 0;
LABEL_59:
  if ( !v12
    || *(_BYTE *)(*((_QWORD *)this + 10) + 2648LL) < 0x5Au
    || v73 != 2147483632
    || (v32 = *((_DWORD *)v9 + 4) == 0, v77 = 1, v32) )
  {
    v77 = 0;
  }
  v33 = v73 == 0;
  v70 = v33;
  if ( v73 )
  {
    v34 = (CBCPBLOBStream *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64, _QWORD))(*(_QWORD *)g_pMO
                                                                                                 + 88LL))(
                              g_pMO,
                              48,
                              0);
    v78 = v34;
    if ( v34 )
    {
      v35 = CBCPBLOBStream::CBCPBLOBStream(v34, v82, a4, v22);
      v21 = 0;
    }
    else
    {
      v21 = 0;
      v35 = 0;
    }
    v78 = v35;
    if ( !v35 )
    {
LABEL_219:
      if ( v19 < 0 )
        goto LABEL_220;
      goto LABEL_221;
    }
    v33 = v70;
  }
  if ( *((_DWORD *)v9 + 91) )
    v36 = (unsigned __int8 *)*((_QWORD *)this + 13);
  else
    v36 = (unsigned __int8 *)*((_QWORD *)v9 + 39);
  v74 = v36;
  v37 = (char *)*((_QWORD *)v9 + 39);
  v38 = *((_QWORD *)v9 + 40);
  if ( v75 )
  {
    *(_WORD *)v37 = -257;
    v37 += 2;
    v38 -= 2LL;
  }
  if ( *((_WORD *)v79 + 1) == 128 )
  {
    if ( *((_WORD *)v9 + 12) == 129 )
    {
      v39 = 2147483646;
    }
    else
    {
      if ( *((_WORD *)v9 + 12) != 130 )
        goto LABEL_81;
      v39 = 2147483644;
    }
    v80 = v39;
  }
LABEL_81:
  if ( !v33 )
  {
    v40 = Size[1];
    while ( 1 )
    {
      LODWORD(v85) = 0;
      v41 = v37;
      if ( v38 < v40 )
      {
        v19 = -2147418113;
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B8[0], 7717897, 2147549183LL);
        }
        goto LABEL_220;
      }
      if ( v40 )
      {
        memmove_0(v37, Src[0], v40);
        v41 = &v37[v40];
        LODWORD(v40) = Size[1];
      }
      v42 = (*(__int64 (__fastcall **)(CBCPBLOBStream *, char *, _QWORD, unsigned __int64 *))(*(_QWORD *)v78 + 24LL))(
              v78,
              v41,
              (unsigned int)(v38 - v40),
              &v85);
      v19 = v42;
      if ( v42 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B8[0], 7727113, (unsigned int)v42);
        }
        goto LABEL_220;
      }
      if ( (unsigned int)v85 != v38 - Size[1] || v42 == 1 )
        v70 = 1;
      v43 = (unsigned int)(LODWORD(Size[1]) + v85);
      LODWORD(v85) = LODWORD(Size[1]) + v85;
      v21 = 0;
      v40 = 0;
      Size[1] = 0;
      if ( v75 )
      {
        v43 = (unsigned int)(v43 + 2);
        LODWORD(v85) = v43;
        v37 -= 2;
        v75 = 0;
      }
      if ( (_DWORD)v43 )
        break;
LABEL_177:
      v37 = (char *)*((_QWORD *)v9 + 39);
      v38 = *((_QWORD *)v9 + 40);
      if ( v70 )
        goto LABEL_178;
    }
    if ( *((_DWORD *)v9 + 91) )
    {
      v45 = v72;
      if ( v72 == 129 )
      {
        v46 = (unsigned int)v43;
        v47 = *((_DWORD *)v79 + 139);
        if ( v47 == 65001 )
        {
          if ( v37[v43 - 1] < 0 )
          {
            memset(&v93, 0, sizeof(v93));
            v49 = GetCPInfo(0xFDE9u, &v93);
            v50 = 0;
            if ( v49 )
              v50 = v93.MaxCharSize;
            v48 = 1;
            while ( v48 < v50 )
            {
              v51 = v37[v46 - 1];
              if ( (v51 & 0xC0) == 0xC0 )
              {
                if ( (v51 & 0xE0) == 0xC0 )
                {
                  if ( v48 >= 2 )
                    v48 = 0;
                }
                else if ( v48 >= (unsigned int)((v51 & 0xF0) != 0xE0) + 3 )
                {
                  v48 = 0;
                }
                goto LABEL_116;
              }
              ++v48;
              if ( !--v46 )
              {
                v48 = 0;
                goto LABEL_116;
              }
            }
          }
          v48 = 0;
        }
        else
        {
          do
          {
            if ( !IsDBCSLeadByteEx(v47, v37[v46 - 1]) )
              break;
            --v46;
          }
          while ( v46 );
          v48 = ((_BYTE)v43 - (_BYTE)v46) & 1;
        }
LABEL_116:
        if ( v48 )
        {
          v52 = CExtByteBuffer::WriteIntoExtBuffer(
                  (CExtByteBuffer *)Size,
                  &v37[(unsigned int)v85 - (unsigned __int64)v48],
                  v48);
          v19 = v52;
          if ( v52 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              _mm_lfence();
              bidTraceHR(off_1802605B8[0], 7767049, (unsigned int)v52);
            }
            goto LABEL_220;
          }
          LODWORD(v85) = v85 - v48;
        }
        v45 = 129;
        v9 = v81;
      }
      v32 = (*((_BYTE *)v9 + 364) & 1) == 0;
      _mm_lfence();
      if ( v32 )
      {
        v19 = CDataSource::DataConvert(
                v84,
                v45,
                v71,
                (unsigned int)v85,
                &v88,
                v37,
                *((_WORD **)this + 13),
                0x4002u,
                0,
                (unsigned __int8 *)&v92,
                *((_BYTE *)v83 + 120),
                *((_BYTE *)v83 + 121),
                0,
                *((_DWORD *)v79 + 139),
                *((_DWORD *)v84 + 287),
                0x1C0u);
        if ( v19 < 0 )
          goto LABEL_135;
        v44 = v71;
        switch ( v71 )
        {
          case 6u:
            if ( *((_DWORD *)v9 + 5) != 8 )
              goto LABEL_124;
            v88 = 8;
            v59 = (_DWORD *)*((_QWORD *)this + 13);
            *(_DWORD *)v89 = v59[1];
            *(_DWORD *)&v89[4] = *v59;
            v54 = v89;
            v74 = v89;
            v21 = 0;
            break;
          case 7u:
          case 8u:
          case 9u:
          case 0xAu:
          case 0xCu:
          case 0xDu:
          case 0xEu:
          case 0xFu:
          case 0x10u:
          case 0x11u:
          case 0x12u:
          case 0x13u:
          case 0x14u:
          case 0x15u:
          case 0x16u:
          case 0x17u:
          case 0x18u:
          case 0x19u:
          case 0x1Au:
          case 0x1Bu:
          case 0x1Cu:
          case 0x1Du:
          case 0x1Eu:
          case 0x1Fu:
          case 0x20u:
          case 0x21u:
          case 0x22u:
          case 0x23u:
          case 0x24u:
          case 0x25u:
          case 0x26u:
          case 0x27u:
          case 0x28u:
          case 0x29u:
          case 0x2Au:
          case 0x2Bu:
          case 0x2Cu:
          case 0x2Du:
          case 0x2Eu:
          case 0x2Fu:
          case 0x30u:
          case 0x31u:
          case 0x32u:
          case 0x33u:
          case 0x34u:
          case 0x35u:
          case 0x36u:
          case 0x37u:
          case 0x38u:
          case 0x39u:
          case 0x3Au:
          case 0x3Bu:
          case 0x3Cu:
          case 0x3Du:
          case 0x3Eu:
          case 0x3Fu:
          case 0x40u:
          case 0x41u:
          case 0x42u:
          case 0x43u:
          case 0x44u:
          case 0x45u:
          case 0x46u:
          case 0x47u:
          case 0x48u:
          case 0x49u:
          case 0x4Au:
          case 0x4Bu:
          case 0x4Cu:
          case 0x4Du:
          case 0x4Eu:
          case 0x4Fu:
          case 0x50u:
          case 0x51u:
          case 0x52u:
          case 0x53u:
          case 0x54u:
          case 0x55u:
          case 0x56u:
          case 0x57u:
          case 0x58u:
          case 0x59u:
          case 0x5Au:
          case 0x5Bu:
          case 0x5Cu:
          case 0x5Du:
          case 0x5Eu:
          case 0x5Fu:
          case 0x60u:
          case 0x61u:
          case 0x62u:
          case 0x63u:
          case 0x64u:
          case 0x65u:
          case 0x66u:
          case 0x67u:
          case 0x68u:
          case 0x69u:
          case 0x6Au:
          case 0x6Bu:
          case 0x6Cu:
          case 0x6Du:
          case 0x6Eu:
          case 0x6Fu:
          case 0x70u:
          case 0x71u:
          case 0x72u:
          case 0x73u:
          case 0x74u:
          case 0x75u:
          case 0x76u:
          case 0x77u:
          case 0x78u:
          case 0x79u:
          case 0x7Au:
          case 0x7Bu:
          case 0x7Cu:
          case 0x7Du:
          case 0x7Eu:
          case 0x7Fu:
          case 0x80u:
          case 0x81u:
          case 0x82u:
          case 0x83u:
          case 0x84u:
          case 0x86u:
          case 0x88u:
          case 0x89u:
          case 0x8Au:
          case 0x8Bu:
          case 0x8Cu:
          case 0x8Du:
          case 0x8Eu:
          case 0x8Fu:
          case 0x90u:
            v54 = v74;
            v21 = 0;
            break;
          case 0xBu:
            v88 = 1;
            v89[0] = **((_WORD **)this + 13) == 0xFFFF;
            v54 = v89;
            v74 = v89;
            v21 = 0;
            break;
          case 0x85u:
            v88 = 3;
            if ( SqlDateFromOledbDate(*((struct tagDBDATE **)this + 13), v89, 3u) )
              goto LABEL_135;
            v54 = v89;
            v74 = v89;
            v21 = 0;
            break;
          case 0x87u:
            v57 = (struct tagDBTIMESTAMP *)*((_QWORD *)this + 13);
            if ( *(_BYTE *)v9 == 42 )
            {
              v88 = 8;
              if ( (unsigned __int16)DateTime2FromTimestamp(v57, 7u, v89, 8u) )
                goto LABEL_135;
              v54 = v89;
              v74 = v89;
              v21 = 0;
            }
            else
            {
              v58 = *((int *)v9 + 5);
              v88 = v58;
              if ( DateTimeFromTimestamp(v57, v58, v89, 1) == 0x9CBE )
              {
LABEL_135:
                v19 = -2147221260;
                goto LABEL_220;
              }
              v54 = v89;
              v74 = v89;
              v21 = 0;
            }
            break;
          case 0x91u:
            v88 = 8;
            if ( SqlTimeFromOledbTime2(*((struct tagDBTIME2 **)this + 13), 7u, v89, 5u) )
              goto LABEL_135;
            v54 = v89;
            v74 = v89;
            v21 = 0;
            break;
          case 0x92u:
            v88 = 10;
            if ( DateTimeOffsetFromTimestampOffset(*((struct tagDBTIMESTAMP **)this + 13), 7u, v89, 0xAu) )
              goto LABEL_135;
            v54 = v89;
            v74 = v89;
            v21 = 0;
            break;
          default:
            goto LABEL_124;
        }
LABEL_126:
        if ( v77 )
        {
          if ( *(_BYTE *)(*((_QWORD *)this + 10) + 2648LL) < 0x5Au )
          {
            v13 += v88;
            if ( v13 >= v80 )
            {
              v88 += v80 - v13;
              v70 = 1;
            }
          }
          v55 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64, unsigned __int64 *))(*(_QWORD *)this + 16LL))(
                  this,
                  4,
                  &v88);
          v19 = v55;
          if ( v55 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              _mm_lfence();
              bidTraceHR(off_1802605B8[0], 7938057, (unsigned int)v55);
            }
            goto LABEL_220;
          }
          _mm_lfence();
          v56 = (*(__int64 (__fastcall **)(CDataFileWriter *, _QWORD, unsigned __int8 *))(*(_QWORD *)this + 16LL))(
                  this,
                  (unsigned int)v88,
                  v54);
          v19 = v56;
          if ( v56 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              _mm_lfence();
              bidTraceHR(off_1802605B8[0], 7942153, (unsigned int)v56);
            }
            goto LABEL_220;
          }
LABEL_176:
          v40 = Size[1];
          v21 = 0;
          goto LABEL_177;
        }
        if ( v76 || v88 <= v73 - v13 )
        {
          v60 = v88;
          v86 = v88;
          if ( v72 != 130
            || v44 != 130
            || v88 != v73 - v13
            || (unsigned __int16)(*(_WORD *)&v37[v88 - 2] + 10240) > 0x3FFu )
          {
            goto LABEL_169;
          }
          _mm_lfence();
          v87 = 0;
          v91 = 0;
          if ( (*(int (__fastcall **)(CBCPBLOBStream *, __int16 *, __int64, int *))(*(_QWORD *)v78 + 24LL))(
                 v78,
                 &v87,
                 2,
                 &v91) >= 0
            && v91 == 2
            && (unsigned __int16)(v87 + 9216) <= 0x3FFu )
          {
            v60 = v86 - 2;
            v70 = 1;
            v61 = 1;
            v86 -= 2LL;
            goto LABEL_170;
          }
        }
        else
        {
          v86 = v73 - v13;
          CBCPErrorHandler::PostBCPWarning(-2147221204);
          if ( v72 == 130 && v44 == 130 )
          {
            v60 = v86;
            if ( (unsigned __int16)(*(_WORD *)&v37[v86 - 2] + 10240) <= 0x3FFu
              && (unsigned __int16)(*(_WORD *)&v37[v86] + 9216) <= 0x3FFu )
            {
              v60 = v86 - 2;
              v70 = 1;
              v61 = 1;
              v86 -= 2LL;
LABEL_170:
              if ( !v60 )
                goto LABEL_192;
              v62 = (*(__int64 (__fastcall **)(CDataFileWriter *, unsigned __int64, unsigned __int8 *))(*(_QWORD *)this + 16LL))(
                      this,
                      v60,
                      v54);
              v19 = v62;
              if ( v62 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802605B8[0], 7999497, (unsigned int)v62);
                }
                goto LABEL_220;
              }
              v13 += v86;
              if ( !v76 )
              {
                if ( v13 == v73 )
                  v61 = 1;
                v70 = v61;
              }
              goto LABEL_176;
            }
LABEL_169:
            v61 = v70;
            goto LABEL_170;
          }
        }
        v60 = v86;
        goto LABEL_169;
      }
      v53 = CDBConnection::XlateCharFromServer(
              *((CDBConnection **)v82 + 1),
              v37,
              (unsigned int)v85,
              *((char **)this + 13),
              0x4002u,
              (__int64 *)&v88,
              0,
              (struct CErrorData *)(*(_QWORD *)v82 + 136LL),
              *((_DWORD *)v79 + 139));
      if ( v53 == 1 )
      {
        v19 = 265937;
      }
      else if ( v53 == -1 )
      {
        goto LABEL_135;
      }
      v44 = v71;
LABEL_124:
      v21 = 0;
    }
    else
    {
      v88 = (unsigned int)v43;
      v44 = v71;
    }
    v54 = v74;
    goto LABEL_126;
  }
LABEL_178:
  if ( v77 )
  {
    v86 = 0;
    v63 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64, unsigned __int64 *))(*(_QWORD *)this + 16LL))(
            this,
            4,
            &v86);
    v19 = v63;
    if ( v63 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_1802605B8[0], 8024073, (unsigned int)v63);
      }
      goto LABEL_220;
    }
  }
  else
  {
LABEL_192:
    if ( !*((_DWORD *)v9 + 4) )
      goto LABEL_207;
    if ( v13 < v73 )
    {
      v64 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64 *))(*(_QWORD *)this + 32LL))(this, &v98);
      v19 = v64;
      if ( v64 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B8[0], 8035337, (unsigned int)v64);
        }
        goto LABEL_220;
      }
      _mm_lfence();
      v65 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64, _QWORD))(*(_QWORD *)this + 24LL))(this, v97, 0);
      v19 = v65;
      if ( v65 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B8[0], 8037385, (unsigned int)v65);
        }
        goto LABEL_220;
      }
      _mm_lfence();
      v66 = CDataFileWriter::WriteNonNullPrefix(this, *((_DWORD *)v9 + 4), v13, *((_DWORD *)v9 + 5), &v73);
      v19 = v66;
      if ( v66 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B8[0], 8045577, (unsigned int)v66);
        }
        goto LABEL_220;
      }
      _mm_lfence();
      v67 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64, _QWORD))(*(_QWORD *)this + 24LL))(this, v98, 0);
      v19 = v67;
      if ( v67 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B8[0], 8049673, (unsigned int)v67);
        }
        goto LABEL_220;
      }
    }
  }
  if ( *((_DWORD *)v9 + 4) )
    goto LABEL_219;
LABEL_207:
  if ( *((_DWORD *)v9 + 1) || v13 >= v73 )
    goto LABEL_219;
  switch ( *((_WORD *)v9 + 12) )
  {
    case 0x80:
      _mm_lfence();
      v68 = CDataFileWriter::WritePadding<unsigned char,0>(this, v73 - v13, v21, v25);
      break;
    case 0x81:
      _mm_lfence();
      v68 = CDataFileWriter::WritePadding<char,32>(this, v73 - v13, v21, v25);
      break;
    case 0x82:
      _mm_lfence();
      v68 = CDataFileWriter::WritePadding<wchar_t,32>(this, v73 - v13, v21, v25);
      break;
    default:
      goto LABEL_216;
  }
  v19 = v68;
LABEL_216:
  if ( v19 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], 8068105, (unsigned int)v19);
    }
    goto LABEL_220;
  }
LABEL_221:
  if ( v78 )
    (*(void (__fastcall **)(CBCPBLOBStream *))(*(_QWORD *)v78 + 16LL))(v78);
  CExtBaseBuffer::~CExtBaseBuffer((CExtBaseBuffer *)Size);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180119970  push    rbp
0x180119972  push    rbx
0x180119973  push    rsi
0x180119974  push    rdi
0x180119975  push    r12
0x180119977  push    r13
0x180119979  push    r14
0x18011997b  push    r15
0x18011997d  lea     rbp, [rsp-0A8h]
0x180119985  sub     rsp, 1A8h
0x18011998c  mov     rax, cs:__security_cookie
0x180119993  xor     rax, rsp
0x180119996  mov     [rbp+0E0h+var_50], rax
0x18011999d  movzx   esi, r9w
0x1801199a1  mov     [rbp+0E0h+var_128], r8
0x1801199a5  mov     r14, rdx
0x1801199a8  mov     [rbp+0E0h+var_118], rdx
0x1801199ac  mov     r12, rcx
0x1801199af  mov     rax, [rbp+0E0h+arg_20]
0x1801199b6  mov     [rbp+0E0h+var_108], rax
0x1801199ba  mov     rax, [rbp+0E0h+arg_28]
0x1801199c1  mov     [rbp+0E0h+var_110], rax
0x1801199c5  mov     rcx, [rbp+0E0h+arg_30]
0x1801199cc  mov     [rbp+0E0h+var_100], rcx
0x1801199d0  mov     rax, [rbp+0E0h+arg_38]
0x1801199d7  mov     [rbp+0E0h+var_E0], rax
0x1801199db  xor     ecx, ecx
0x1801199dd  mov     [rbp+0E0h+var_78], rcx
0x1801199e1  mov     [rbp+0E0h+var_70], rcx
0x1801199e5  movsxd  rax, dword ptr [rdx+14h]
0x1801199e9  mov     [rbp+0E0h+var_158], rax
0x1801199ed  movzx   eax, word ptr [rdx+18h]
0x1801199f1  mov     [rbp+0E0h+var_15C], ax
0x1801199f5  movzx   r15d, word ptr [r8+2]
0x1801199fa  mov     [rbp+0E0h+var_15A], r15w
0x1801199ff  mov     edi, [r8+23Ch]
0x180119a06  mov     [rbp+0E0h+var_C4], ecx
0x180119a09  mov     r13d, ecx
0x180119a0c  mov     [rbp+0E0h+var_F0], rcx
0x180119a10  mov     [rbp+0E0h+var_148], ecx
0x180119a13  xor     eax, eax
0x180119a15  mov     qword ptr [rbp+0E0h+var_D8], rax
0x180119a19  mov     [rbp+0E0h+var_D0], ax
0x180119a1d  mov     [rbp+0E0h+var_130], rcx
0x180119a21  xorps   xmm0, xmm0
0x180119a24  movups  xmmword ptr [rbp+0E0h+Size], xmm0
0x180119a28  movups  [rbp+0E0h+var_98], xmm0
0x180119a2c  mov     [rbp+0E0h+Size], rcx
0x180119a30  mov     [rbp+0E0h+Size+8], rcx
0x180119a34  mov     qword ptr [rbp+0E0h+var_98], rcx
0x180119a38  mov     qword ptr [rbp+0E0h+var_98+8], rcx
0x180119a3c  movdqu  xmmword ptr [rbp+0E0h+Src], xmm0
0x180119a41  movups  xmmword ptr [rbp+0E0h+CPInfo.MaxCharSize], xmm0
0x180119a45  mov     dword ptr [rbp+0E0h+CPInfo.LeadByte+0Ah], eax
0x180119a4b  lea     rdx, [rbp+0E0h+CPInfo]; lpCPInfo
0x180119a4f  mov     ecx, 0FDE9h; CodePage
0x180119a54  call    cs:__imp_GetCPInfo
0x180119a5a  mov     ebx, eax
0x180119a5c  xorps   xmm0, xmm0
0x180119a5f  xor     eax, eax
0x180119a61  movups  xmmword ptr [rbp+0E0h+var_C0.MaxCharSize], xmm0
0x180119a65  mov     dword ptr [rbp+0E0h+var_C0.LeadByte+0Ah], eax
0x180119a68  lea     rdx, [rbp+0E0h+var_C0]; lpCPInfo
0x180119a6c  mov     ecx, 0FDE9h; CodePage
0x180119a71  call    cs:__imp_GetCPInfo
0x180119a77  xor     edx, edx
0x180119a79  mov     r8d, edx
0x180119a7c  test    ebx, ebx
0x180119a7e  cmovnz  r8d, [rbp+0E0h+CPInfo.MaxCharSize]
0x180119a83  dec     r8d; unsigned __int64
0x180119a86  test    eax, eax
0x180119a88  cmovnz  edx, [rbp+0E0h+var_C0.MaxCharSize]
0x180119a8c  dec     edx; unsigned __int64
0x180119a8e  lea     rcx, [rbp+0E0h+Size]; this
0x180119a92  call    ?FInit@CExtByteBuffer@@QEAAH_K0@Z; CExtByteBuffer::FInit(unsigned __int64,unsigned __int64)
0x180119a97  test    eax, eax
0x180119a99  jnz     short loc_180119AC9
0x180119a9b  mov     ebx, 8007000Eh
0x180119aa0  test    byte ptr cs:_bidGblFlags, 2
0x180119aa7  jz      loc_18011A81D
0x180119aad  lfence
0x180119ab0  mov     r8d, ebx
0x180119ab3  mov     edx, 73A409h
0x180119ab8  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180119abf  call    _bidTraceHR
0x180119ac4  jmp     loc_18011A81D
0x180119ac9  mov     rax, [r12+50h]
0x180119ace  xor     r8d, r8d
0x180119ad1  mov     [rbp+0E0h+var_140], r8
0x180119ad5  mov     ecx, 7FFFFFFFh
0x180119ada  mov     r9d, 80h
0x180119ae0  mov     [rbp+0E0h+var_120], rcx
0x180119ae4  mov     edx, 1
0x180119ae9  cmp     byte ptr [rax+0A58h], 5Ah ; 'Z'
0x180119af0  jbe     short loc_180119B3D
0x180119af2  mov     [rbp+0E0h+var_140], r8
0x180119af6  cmp     r15w, r9w
0x180119afa  jnz     short loc_180119B3D
0x180119afc  mov     [rbp+0E0h+var_140], r8
0x180119b00  test    edi, edi
0x180119b02  jz      short loc_180119B3D
0x180119b04  mov     [rbp+0E0h+var_140], r8
0x180119b08  cmp     [r14+10h], r8d
0x180119b0c  jnz     short loc_180119B3D
0x180119b0e  cmp     [rax+0A78h], r8d
0x180119b15  jnz     short loc_180119B24
0x180119b17  mov     [rbp+0E0h+var_140], r8
0x180119b1b  cmp     [rax+0A7Ch], r8d
0x180119b22  jz      short loc_180119B3D
0x180119b24  mov     rax, [rbp+0E0h+var_158]
0x180119b28  cmp     rax, 7FFFFFF0h
0x180119b2e  jz      short loc_180119B39
0x180119b30  mov     [rbp+0E0h+var_140], r8
0x180119b34  cmp     rax, rcx
0x180119b37  jnz     short loc_180119B3D
0x180119b39  mov     [rbp+0E0h+var_140], rdx
0x180119b3d  mov     r15, [rbp+0E0h+var_108]
0x180119b41  cmp     dword ptr [r15+70h], 1Dh
0x180119b46  jnz     short loc_180119B6C
0x180119b48  cmp     [r14+18h], r9w
0x180119b4d  jnz     short loc_180119B6C
0x180119b4f  mov     eax, 2
0x180119b54  mov     rcx, [rbp+0E0h+var_E0]
0x180119b58  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180119b5c  cmovz   rax, r8
0x180119b60  add     rcx, rax
0x180119b63  mov     [rbp+0E0h+var_E0], rcx
0x180119b67  mov     [rbp+0E0h+var_148], edx
0x180119b6a  jmp     short loc_180119B70
0x180119b6c  mov     rcx, [rbp+0E0h+var_E0]
0x180119b70  mov     r10d, 81h
0x180119b76  mov     r9d, 82h
0x180119b7c  cmp     [r14+10h], r8d
0x180119b80  jz      loc_180119C9F
0x180119b86  mov     rax, [r12]
0x180119b8a  lea     rdx, [rbp+0E0h+var_78]
0x180119b8e  mov     rcx, r12
0x180119b91  mov     rax, [rax+20h]
0x180119b95  call    cs:__guard_dispatch_icall_fptr
0x180119b9b  mov     ebx, eax
0x180119b9d  test    eax, eax
0x180119b9f  jns     short loc_180119BCA
0x180119ba1  test    byte ptr cs:_bidGblFlags, 2
0x180119ba8  jz      loc_18011A81D
0x180119bae  lfence
0x180119bb1  mov     r8d, eax
0x180119bb4  mov     edx, 741409h
0x180119bb9  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180119bc0  call    _bidTraceHR
0x180119bc5  jmp     loc_18011A81D
0x180119bca  test    edi, edi
0x180119bcc  jz      short loc_180119BFC
0x180119bce  cmp     [rbp+0E0h+var_E0], 0
0x180119bd3  jz      short loc_180119BFC
0x180119bd5  lfence
0x180119bd8  mov     rax, [r12+50h]
0x180119bdd  cmp     byte ptr [rax+0A58h], 5Ah ; 'Z'
0x180119be4  jb      short loc_180119BFC
0x180119be6  cmp     [rbp+0E0h+var_158], 7FFFFFF0h
0x180119bee  jnz     short loc_180119BFC
0x180119bf0  lfence
0x180119bf3  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180119bfa  jmp     short loc_180119C4C
0x180119bfc  lfence
0x180119bff  movzx   ecx, byte ptr [r14]
0x180119c03  sub     ecx, 28h ; '('
0x180119c06  jz      short loc_180119C42
0x180119c08  sub     ecx, 1
0x180119c0b  jz      short loc_180119C3A
0x180119c0d  sub     ecx, 1
0x180119c10  jz      short loc_180119C32
0x180119c12  sub     ecx, 1
0x180119c15  jz      short loc_180119C2A
0x180119c17  cmp     ecx, 4Fh ; 'O'
0x180119c1a  jz      short loc_180119C22
0x180119c1c  mov     r8, [rbp+0E0h+var_E0]
0x180119c20  jmp     short loc_180119C48
0x180119c22  mov     r8d, 4
0x180119c28  jmp     short loc_180119C48
0x180119c2a  mov     r8d, 0Ah
0x180119c30  jmp     short loc_180119C48
0x180119c32  mov     r8d, 8
0x180119c38  jmp     short loc_180119C48
0x180119c3a  mov     r8d, 5
0x180119c40  jmp     short loc_180119C48
0x180119c42  mov     r8d, 3; unsigned __int64
0x180119c48  mov     [rbp+0E0h+var_E0], r8
0x180119c4c  lea     r9, [r14+14h]
0x180119c50  lea     rax, [rbp+0E0h+var_158]
0x180119c54  mov     rcx, r12; this
0x180119c57  mov     edx, [r14+10h]; unsigned int
0x180119c5b  mov     [rsp+1E0h+var_1C0], rax; unsigned __int64 *
0x180119c60  mov     r9d, [r9]; int
0x180119c63  call    ?WriteNonNullPrefix@CDataFileWriter@@QEAAJK_KHPEA_K@Z; CDataFileWriter::WriteNonNullPrefix(ulong,unsigned __int64,int,unsigned __int64 *)
0x180119c68  mov     ebx, eax
0x180119c6a  test    eax, eax
0x180119c6c  jns     short loc_180119C97
0x180119c6e  test    byte ptr cs:_bidGblFlags, 2
0x180119c75  jz      loc_18011A81D
0x180119c7b  lfence
0x180119c7e  mov     r8d, eax
0x180119c81  mov     edx, 747009h
0x180119c86  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180119c8d  call    _bidTraceHR
0x180119c92  jmp     loc_18011A81D
0x180119c97  xor     r8d, r8d
0x180119c9a  jmp     loc_180119D58
0x180119c9f  mov     ebx, r8d
0x180119ca2  test    rcx, rcx
0x180119ca5  jnz     loc_180119D58
0x180119cab  movzx   eax, word ptr [r14+18h]
0x180119cb0  cmp     ax, r10w
0x180119cb4  jnz     short loc_180119CFD
0x180119cb6  mov     byte ptr [rbp+0E0h+var_E8], bl
0x180119cb9  mov     rax, [r12]
0x180119cbd  lea     r8, [rbp+0E0h+var_E8]
0x180119cc1  mov     rcx, r12
0x180119cc4  mov     rax, [rax+10h]
0x180119cc8  call    cs:__guard_dispatch_icall_fptr
0x180119cce  mov     ebx, eax
0x180119cd0  test    eax, eax
0x180119cd2  jns     short loc_180119D51
0x180119cd4  test    byte ptr cs:_bidGblFlags, 2
0x180119cdb  jz      loc_18011A81D
0x180119ce1  lfence
0x180119ce4  mov     r8d, eax
0x180119ce7  mov     edx, 74A409h
0x180119cec  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180119cf3  call    _bidTraceHR
0x180119cf8  jmp     loc_18011A81D
0x180119cfd  cmp     ax, r9w
0x180119d01  jnz     short loc_180119D54
0x180119d03  mov     [rbp+0E0h+var_E8], r8w
0x180119d08  mov     rax, [r12]
0x180119d0c  lea     r8, [rbp+0E0h+var_E8]
0x180119d10  mov     edx, 2
0x180119d15  mov     rcx, r12
0x180119d18  mov     rax, [rax+10h]
0x180119d1c  call    cs:__guard_dispatch_icall_fptr
0x180119d22  mov     ebx, eax
0x180119d24  test    eax, eax
0x180119d26  jns     short loc_180119D51
0x180119d28  test    byte ptr cs:_bidGblFlags, 2
0x180119d2f  jz      loc_18011A81D
0x180119d35  lfence
0x180119d38  mov     r8d, eax
0x180119d3b  mov     edx, 74BC09h
0x180119d40  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180119d47  call    _bidTraceHR
0x180119d4c  jmp     loc_18011A81D
0x180119d51  xor     r8d, r8d
0x180119d54  mov     [rbp+0E0h+var_158], r8
0x180119d58  test    edi, edi
0x180119d5a  jz      short loc_180119D82
0x180119d5c  mov     rax, [r12+50h]
0x180119d61  cmp     byte ptr [rax+0A58h], 5Ah ; 'Z'
0x180119d68  jb      short loc_180119D82
0x180119d6a  cmp     [rbp+0E0h+var_158], 7FFFFFF0h
0x180119d72  jnz     short loc_180119D82
0x180119d74  cmp     dword ptr [r14+10h], 0
0x180119d79  mov     [rbp+0E0h+var_138], 1
0x180119d80  jnz     short loc_180119D86
0x180119d82  mov     [rbp+0E0h+var_138], r8d
0x180119d86  mov     edx, r8d
0x180119d89  mov     rax, [rbp+0E0h+var_158]
0x180119d8d  test    rax, rax
0x180119d90  setz    dl
0x180119d93  mov     [rbp+0E0h+var_160], edx
0x180119d96  test    rax, rax
0x180119d99  jz      short loc_180119DEF
0x180119d9b  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180119da2  mov     rax, [rcx]
0x180119da5  mov     edx, 30h ; '0'
0x180119daa  mov     rax, [rax+58h]
0x180119dae  call    cs:__guard_dispatch_icall_fptr
0x180119db4  nop
0x180119db5  mov     [rbp+0E0h+var_130], rax
0x180119db9  test    rax, rax
0x180119dbc  jz      short loc_180119DD9
0x180119dbe  mov     r9, r15; struct COLINFO *
0x180119dc1  movzx   r8d, si; unsigned __int16
0x180119dc5  mov     rdx, [rbp+0E0h+var_110]; struct CRecordFetcher *
0x180119dc9  mov     rcx, rax; this
0x180119dcc  call    ??0CBCPBLOBStream@@QEAA@PEAVCRecordFetcher@@GPEAUCOLINFO@@@Z; CBCPBLOBStream::CBCPBLOBStream(CRecordFetcher *,ushort,COLINFO *)
0x180119dd1  mov     r15, rax
0x180119dd4  xor     r8d, r8d
0x180119dd7  jmp     short loc_180119DDF
0x180119dd9  xor     r8d, r8d
0x180119ddc  mov     r15d, r8d
0x180119ddf  mov     [rbp+0E0h+var_130], r15
0x180119de3  test    r15, r15
0x180119de6  jz      loc_18011A819
0x180119dec  mov     edx, [rbp+0E0h+var_160]
0x180119def  cmp     dword ptr [r14+16Ch], 0
0x180119df7  jnz     short loc_180119E02
0x180119df9  mov     rax, [r14+138h]
0x180119e00  jmp     short loc_180119E07
0x180119e02  mov     rax, [r12+68h]
0x180119e07  mov     [rbp+0E0h+var_150], rax
0x180119e0b  mov     r15, [r14+138h]
  ... truncated ...
```

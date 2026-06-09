# CIVIAudioCodec::DecodeAAC(uchar *,long)

- ea: `0x180019d60`
- end: `0x18001a6a3`
- name: `?DecodeAAC@CIVIAudioCodec@@IEAAJPEAEJ@Z`
- size: `2371`
- prototype: `__int64 __fastcall(CIVIAudioCodec *__hidden this, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001ab80`

## callees

- `0x1800017b0`
- `0x180019d60`
- `0x18001a6b0`
- `0x180033bf0`
- `0x1800363f0`
- `0x180037490`
- `0x1800739e0`
- `0x1800886fc`
- `0x180088708`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019f34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a29c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019f34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a29c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019efe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a266`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019efe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a266`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180019f24`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a28c`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180019f24`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a28c`

## pseudocode

```c
__int64 __fastcall CIVIAudioCodec::DecodeAAC(CIVIAudioCodec *this, unsigned __int8 *a2, int a3)
{
  unsigned __int8 *v3; // rsi
  char *v5; // rdx
  int v6; // eax
  unsigned __int64 v7; // rcx
  __int64 v8; // rbx
  int v9; // r15d
  _BYTE *v10; // rax
  _BYTE *v11; // rdx
  unsigned __int64 v12; // r9
  char v13; // r10
  int *v14; // rbx
  _BYTE *v15; // r8
  int v16; // eax
  __int64 v17; // rdi
  unsigned int v18; // esi
  int v19; // r8d
  int v20; // edx
  unsigned int v21; // edx
  __int64 v22; // rcx
  int v23; // ecx
  unsigned __int16 v24; // r14
  unsigned int v25; // ebx
  unsigned __int16 *v26; // rcx
  char *v27; // rdx
  int v28; // eax
  unsigned __int64 v29; // rcx
  int v30; // r8d
  int v31; // r15d
  size_t v32; // rbx
  int v33; // eax
  void *v34; // rcx
  void *v35; // rcx
  _BYTE *v36; // rdx
  _BYTE *v37; // rcx
  unsigned __int64 v38; // r9
  char v39; // r10
  int *v40; // rbx
  _BYTE *v41; // r8
  int v42; // eax
  __int64 v43; // rdi
  __int64 v44; // rcx
  int v45; // r9d
  char *v46; // r14
  unsigned int v47; // r9d
  unsigned int v48; // r8d
  bool v49; // zf
  unsigned int v50; // eax
  unsigned int v51; // r12d
  unsigned int v52; // edi
  unsigned __int64 v53; // rsi
  int v54; // ebx
  int v55; // eax
  unsigned int v56; // ebx
  unsigned int v57; // edi
  int v58; // edx
  char *v59; // r8
  int *v60; // rcx
  __int64 v61; // rax
  int v62; // eax
  int v64; // [rsp+30h] [rbp-59h] BYREF
  int v65; // [rsp+34h] [rbp-55h]
  int v66; // [rsp+38h] [rbp-51h] BYREF
  int v67; // [rsp+3Ch] [rbp-4Dh] BYREF
  __int128 v68; // [rsp+40h] [rbp-49h] BYREF
  __int128 v69; // [rsp+50h] [rbp-39h]
  __int128 v70; // [rsp+60h] [rbp-29h]
  unsigned __int8 *v71; // [rsp+70h] [rbp-19h]
  int v72; // [rsp+78h] [rbp-11h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v74; // [rsp+90h] [rbp+7h] BYREF

  *((_DWORD *)this + 1580) = 0;
  v3 = a2;
  v65 = a3;
  v71 = a2;
  v66 = 0;
  if ( *(_OWORD *)((char *)this + 136) != __PAIR128__(0x719B3800AA000080LL, MEDIASUBTYPE_MPEG_ADTS_AAC) )
  {
    if ( MEDIASUBTYPE_MPEG_LOAS != *((_QWORD *)this + 17) || *((_QWORD *)this + 18) != 0x719B3800AA000080LL )
    {
      if ( *(_QWORD *)((char *)this + 164) != *(_QWORD *)&FORMAT_WaveFormatEx.Data1
        || *(_QWORD *)((char *)this + 172) != *(_QWORD *)FORMAT_WaveFormatEx.Data4
        || (v61 = *((_QWORD *)this + 25)) == 0
        || (v62 = *(_DWORD *)(v61 + 4)) == 0 )
      {
        v62 = 48000;
      }
      if ( *((_DWORD *)this + 1711) != v62 )
      {
        *((_DWORD *)this + 1711) = v62;
        if ( *((_QWORD *)this + 801) )
        {
          AACAudioDecoderClose();
          a3 = v65;
        }
        *((_DWORD *)this + 2) = 1;
      }
      *((_QWORD *)this + 803) = 0;
      *((_QWORD *)this + 804) = 0;
      CIVIAudioCodec::DecodeAACFrame(this, v3, a3, 0, 0);
      return 0;
    }
    v68 = 0;
    v69 = 0;
    v70 = 0;
LABEL_49:
    v27 = (char *)*((_QWORD *)this + 12);
    v28 = 0;
    if ( a3 >= 0 )
      v28 = a3;
    v29 = *((_QWORD *)this + 13) - (_QWORD)v27;
    v65 = v28;
    v30 = v28;
    if ( v29 > 0x7FFFFFFF )
    {
      v27 = (char *)this + 6864;
      LODWORD(v29) = 0;
      *((_QWORD *)this + 13) = (char *)this + 6864;
      *((_QWORD *)this + 12) = (char *)this + 6864;
      *((_QWORD *)this + 11) = (char *)this + 6864;
    }
    v31 = v28;
    v32 = (int)v29;
    v33 = 8256 - v29;
    v34 = (void *)*((_QWORD *)this + 11);
    if ( v33 < v30 )
      v31 = v33;
    v72 = v31;
    memmove_0(v34, v27, v32);
    v35 = (void *)(v32 + *((_QWORD *)this + 11));
    UserData.Ptr = v31;
    memcpy_0(v35, v3, v31);
    v36 = (_BYTE *)*((_QWORD *)this + 11);
    *((_QWORD *)this + 13) = &v36[v31 + v32];
LABEL_56:
    *((_QWORD *)this + 12) = v36;
    while ( 1 )
    {
      while ( 1 )
      {
        v37 = v36;
        if ( *((_DWORD *)this + 1586) )
          return 0;
        v38 = *((_QWORD *)this + 13);
        v39 = 0;
        v40 = (int *)((char *)this + 6460);
        if ( (unsigned __int64)(v36 + 3) > v38 )
        {
          v41 = v36;
        }
        else
        {
          do
          {
            if ( *v37 == 86 )
            {
              v41 = v37;
              if ( (v37[1] & 0xE0) == 0xE0 )
                break;
            }
            ++v36;
            v40 = (int *)((char *)this + 6460);
            ++*((_DWORD *)this + 1615);
            v39 = 1;
            *((_QWORD *)this + 12) = v36;
            v37 = v36;
            v41 = v36;
          }
          while ( (unsigned __int64)(v36 + 3) <= v38 );
        }
        if ( (unsigned __int64)(v41 + 3) > v38 )
          goto LABEL_112;
        if ( v39 )
        {
          v42 = *v40;
          ++*((_DWORD *)this + 1614);
          v67 = v42;
          v74.Ptr = (ULONGLONG)&v67;
          *(_QWORD *)&v74.Size = 4;
          if ( this != (CIVIAudioCodec *)-24LL )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
            if ( !*((_DWORD *)this + 6) )
              EventWrite(*((_QWORD *)this + 4), &MSMPEG2ADEC_AUD_RESYNC, 1u, &v74);
            LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
          }
        }
        v43 = *((_QWORD *)this + 12);
        v44 = (unsigned int)(*((_DWORD *)this + 26) - v43);
        v70 = (unsigned __int64)(v43 + v44);
        *((_QWORD *)&v68 + 1) = v43 + v44;
        *((_QWORD *)&v69 + 1) = v43;
        *(_QWORD *)&v69 = v43;
        LODWORD(v68) = 0;
        FillBitCache(&v68, 11);
        LODWORD(v68) = v68 - 11;
        v45 = v68;
        if ( ((DWORD1(v68) >> v68) & 0x7FF) != 0x2B7 )
        {
          v36 = (_BYTE *)(v43 + 1);
          goto LABEL_56;
        }
        if ( (unsigned int)v68 < 0xD )
        {
          FillBitCache(&v68, 13);
          v45 = v68;
        }
        v46 = (char *)this + 6476;
        v47 = v45 - 13;
        v36 = (_BYTE *)(v43 + 1);
        LODWORD(v68) = v47;
        *((_DWORD *)this + 1619) = (DWORD1(v68) >> v47) & 0x1FFF;
        v48 = ((*(_BYTE *)(v43 + 1) & 0x1F) << 8) + *(unsigned __int8 *)(v43 + 2) + 3;
        *((_DWORD *)this + 1616) = v48;
        *((_DWORD *)this + 94) = v48;
        if ( v48 <= 3 )
          goto LABEL_56;
        *v40 = 0;
        if ( v43 + (unsigned __int64)v48 > *((_QWORD *)this + 13) )
        {
LABEL_112:
          a3 = v65 - v72;
          if ( v65 == v72 )
            return 0;
          v3 = &v71[UserData.Ptr];
          v71 += UserData.Ptr;
          goto LABEL_49;
        }
        if ( *((_DWORD *)this + 1620) )
        {
          if ( !v47 )
          {
            FillBitCache(&v68, 1);
            v47 = v68;
          }
          LODWORD(v68) = --v47;
          v49 = ((DWORD1(v68) >> v47) & 1) == 0;
          *((_DWORD *)this + 1622) = (DWORD1(v68) >> v47) & 1;
          if ( v49 )
          {
            if ( (unsigned int)ReadStreamMuxConfig(&v68, (char *)this + 6476) )
              goto LABEL_100;
            v47 = v68;
          }
        }
        if ( !*((_DWORD *)this + 1624) )
          break;
LABEL_100:
        v36 = (_BYTE *)++*((_QWORD *)this + 12);
      }
      v50 = 0;
      v64 = 0;
      if ( *((_DWORD *)this + 1626) )
      {
        while ( *((_DWORD *)this + 1625) == 1 )
        {
          v51 = 0;
          if ( *((_DWORD *)this + 1627) )
          {
            while ( 1 )
            {
              v52 = 0;
              if ( *((_DWORD *)this + 1628) )
                break;
LABEL_92:
              if ( ++v51 >= *((_DWORD *)this + 1627) )
              {
                v50 = v64;
                goto LABEL_94;
              }
            }
            while ( 1 )
            {
              v53 = 300 * (v51 + (unsigned __int64)v52);
              if ( *(_DWORD *)&v46[v53 + 64] )
                goto LABEL_100;
              v54 = 0;
              do
              {
                if ( v47 < 8 )
                {
                  FillBitCache(&v68, 8);
                  v47 = v68;
                }
                v47 -= 8;
                LODWORD(v68) = v47;
                v54 += (unsigned __int8)(DWORD1(v68) >> v47);
              }
              while ( (unsigned __int8)(DWORD1(v68) >> v47) == 0xFF );
              ++v52;
              *(_DWORD *)&v46[v53 + 76] = 8 * v54;
              if ( v52 >= *((_DWORD *)this + 1628) )
                goto LABEL_92;
            }
          }
LABEL_94:
          v64 = ++v50;
          if ( v50 >= *((_DWORD *)this + 1626) )
            goto LABEL_95;
        }
        goto LABEL_100;
      }
LABEL_95:
      *((_DWORD *)this + 1621) = 1;
      *((_QWORD *)this + 803) = 0;
      *((_QWORD *)this + 804) = 0;
      if ( !*((_DWORD *)this + 1710) && (*((_DWORD *)this + 1622) || *((_DWORD *)this + 1629)) )
      {
        *((_QWORD *)this + 12) += *((unsigned int *)this + 1616);
        v36 = (_BYTE *)*((_QWORD *)this + 12);
      }
      else
      {
        *((_DWORD *)this + 1710) = 1;
        if ( *((_DWORD *)this + 1640) > 0xBu )
          goto LABEL_100;
        v55 = *((_DWORD *)this + 1641);
        v56 = (8 * ((_DWORD)v69 - DWORD2(v69)) - v47) >> 3;
        v57 = (8 * ((_BYTE)v69 - BYTE8(v69)) - (_BYTE)v47) & 7;
        if ( *((_DWORD *)this + 1711) != v55 )
        {
          *((_DWORD *)this + 1711) = v55;
          if ( *((_QWORD *)this + 801) )
            AACAudioDecoderClose();
          *((_DWORD *)this + 2) = 1;
        }
        v58 = *((_DWORD *)this + 1647);
        v66 = v58;
        if ( v58 )
          v59 = 0;
        else
          v59 = (char *)this + 6652;
        v60 = &v66;
        if ( !v58 )
          v60 = 0;
        *((_QWORD *)this + 803) = v60;
        *((_QWORD *)this + 804) = v59;
        CIVIAudioCodec::DecodeAACFrame(
          this,
          (unsigned __int8 *)(*((_QWORD *)this + 12) + v56),
          *((_DWORD *)this + 1616),
          v57,
          0);
        *((_QWORD *)this + 12) += *((unsigned int *)this + 1616);
        v36 = (_BYTE *)*((_QWORD *)this + 12);
      }
    }
  }
  v64 = 0;
LABEL_3:
  v5 = (char *)*((_QWORD *)this + 12);
  v6 = 0;
  if ( a3 >= 0 )
    v6 = a3;
  v7 = *((_QWORD *)this + 13) - (_QWORD)v5;
  v65 = v6;
  if ( v7 > 0x7FFFFFFF )
  {
    v5 = (char *)this + 6864;
    LODWORD(v7) = 0;
    *((_QWORD *)this + 13) = (char *)this + 6864;
    *((_QWORD *)this + 12) = (char *)this + 6864;
    *((_QWORD *)this + 11) = (char *)this + 6864;
  }
  v8 = (int)v7;
  v9 = v6;
  if ( 8256 - (int)v7 < v6 )
    v9 = 8256 - v7;
  memmove_0(*((void **)this + 11), v5, (int)v7);
  memcpy_0((void *)(v8 + *((_QWORD *)this + 11)), v3, v9);
  v10 = (_BYTE *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 13) = &v10[v9 + v8];
LABEL_10:
  for ( *((_QWORD *)this + 12) = v10; ; v10 = (_BYTE *)*((_QWORD *)this + 12) )
  {
    v11 = v10;
    if ( *((_DWORD *)this + 1586) )
      break;
    v12 = *((_QWORD *)this + 13);
    v13 = 0;
    v14 = (int *)((char *)this + 6460);
    if ( (unsigned __int64)(v10 + 2) > v12 )
    {
      v15 = v10;
    }
    else
    {
      do
      {
        if ( *v11 == 0xFF )
        {
          v15 = v11;
          if ( (v11[1] & 0xF6) == 0xF0 )
            break;
        }
        ++v10;
        v14 = (int *)((char *)this + 6460);
        ++*((_DWORD *)this + 1615);
        v13 = 1;
        *((_QWORD *)this + 12) = v10;
        v11 = v10;
        v15 = v10;
      }
      while ( (unsigned __int64)(v10 + 2) <= v12 );
    }
    if ( (unsigned __int64)(v15 + 9) > v12 )
      goto LABEL_44;
    if ( v13 )
    {
      v16 = *v14;
      ++*((_DWORD *)this + 1614);
      v67 = v16;
      UserData.Ptr = (ULONGLONG)&v67;
      *(_QWORD *)&UserData.Size = 4;
      if ( this != (CIVIAudioCodec *)-24LL )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
        if ( !*((_DWORD *)this + 6) )
          EventWrite(*((_QWORD *)this + 4), &MSMPEG2ADEC_AUD_RESYNC, 1u, &UserData);
        LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
      }
    }
    v17 = *((_QWORD *)this + 12);
    v18 = (*(unsigned __int8 *)(v17 + 5) >> 5)
        | (8 * (*(unsigned __int8 *)(v17 + 4) | ((*(_BYTE *)(v17 + 3) & 3) << 8)));
    v10 = (_BYTE *)(v17 + 1);
    *((_DWORD *)this + 1616) = v18;
    *((_DWORD *)this + 94) = v18;
    v19 = (*(_BYTE *)(v17 + 1) & 1) == 0;
    *((_DWORD *)this + 1617) = v19;
    v20 = (*(unsigned __int8 *)(v17 + 3) >> 6) | (4 * (*(_BYTE *)(v17 + 2) & 1));
    *((_QWORD *)this + 804) = 0;
    v66 = v20;
    *((_QWORD *)this + 803) = &v66;
    if ( !v18 )
      goto LABEL_10;
    v21 = *(unsigned __int8 *)(v17 + 2);
    if ( (v21 & 0xC0) != 0x40 )
      goto LABEL_10;
    if ( (*(_BYTE *)(v17 + 6) & 3) != 0 )
      goto LABEL_10;
    v22 = (v21 >> 2) & 0xF;
    if ( (unsigned int)v22 > 0xB )
      goto LABEL_10;
    v23 = *((_DWORD *)qword_18008DD50 + v22);
    if ( *((_DWORD *)this + 1711) != v23 )
    {
      *((_DWORD *)this + 1711) = v23;
      if ( *((_QWORD *)this + 801) )
      {
        AACAudioDecoderClose();
        v19 = *((_DWORD *)this + 1617);
        v18 = *((_DWORD *)this + 1616);
      }
      v17 = *((_QWORD *)this + 12);
      *((_DWORD *)this + 2) = 1;
    }
    v24 = v19 ? _byteswap_ushort(*(_WORD *)(v17 + 7)) : 0;
    *((_WORD *)this + 3236) = v24;
    *v14 = 0;
    if ( v17 + (unsigned __int64)v18 > *((_QWORD *)this + 13) )
    {
LABEL_44:
      a3 = v65 - v9;
      if ( v65 == v9 )
        return 0;
      v3 = &v71[v9];
      v71 = v3;
      goto LABEL_3;
    }
    if ( v19 )
    {
      v25 = 9;
      LOWORD(v64) = -1;
      if ( v17 )
        CAacDecoderGenerateCRC(v17, 0, 56, 56, (__int64)&v64);
      HIWORD(v64) = v24;
      v26 = (unsigned __int16 *)&v64;
      if ( *((_DWORD *)this + 1571) )
        v26 = 0;
    }
    else
    {
      v25 = 7;
      v26 = 0;
    }
    CIVIAudioCodec::DecodeAACFrame(this, (unsigned __int8 *)(v17 + v25), v18 - v25, 0, v26);
    *((_QWORD *)this + 12) += *((unsigned int *)this + 1616);
  }
  return 0;
}

```

## disassembly

```asm
0x180019d60  mov     [rsp-8+arg_18], rbx
0x180019d65  push    rbp
0x180019d66  push    rsi
0x180019d67  push    rdi
0x180019d68  push    r12
0x180019d6a  push    r13
0x180019d6c  push    r14
0x180019d6e  push    r15
0x180019d70  lea     rbp, [rsp-27h]
0x180019d75  sub     rsp, 0B0h
0x180019d7c  mov     rax, cs:__security_cookie
0x180019d83  xor     rax, rsp
0x180019d86  mov     [rbp+57h+var_40], rax
0x180019d8a  mov     dword ptr [rcx+18B0h], 0
0x180019d94  mov     rsi, rdx
0x180019d97  mov     rax, cs:MEDIASUBTYPE_MPEG_ADTS_AAC
0x180019d9e  mov     r13, rcx
0x180019da1  mov     [rbp+57h+var_AC], r8d
0x180019da5  mov     [rbp+57h+var_70], rdx
0x180019da9  mov     [rbp+57h+var_A8], 0
0x180019db0  cmp     rax, [rcx+88h]
0x180019db7  jnz     loc_18001A10B
0x180019dbd  mov     rax, cs:qword_18008CF48
0x180019dc4  cmp     rax, [rcx+90h]
0x180019dcb  jnz     loc_18001A10B
0x180019dd1  mov     [rbp+57h+var_B0], 0
0x180019dd8  lea     r14, qword_18008DD50
0x180019ddf  nop
0x180019de0  mov     rdx, [r13+60h]
0x180019de4  xor     eax, eax
0x180019de6  mov     rcx, [r13+68h]
0x180019dea  test    r8d, r8d
0x180019ded  cmovns  eax, r8d
0x180019df1  sub     rcx, rdx
0x180019df4  mov     [rbp+57h+var_AC], eax
0x180019df7  mov     r8d, eax
0x180019dfa  cmp     rcx, 7FFFFFFFh
0x180019e01  jbe     short loc_180019E18
0x180019e03  lea     rdx, [r13+1AD0h]; Src
0x180019e0a  xor     ecx, ecx
0x180019e0c  mov     [r13+68h], rdx
0x180019e10  mov     [r13+60h], rdx
0x180019e14  mov     [r13+58h], rdx
0x180019e18  movsxd  rbx, ecx
0x180019e1b  mov     r15d, r8d
0x180019e1e  mov     eax, 2040h
0x180019e23  sub     eax, ecx
0x180019e25  mov     rcx, [r13+58h]; void *
0x180019e29  cmp     eax, r8d
0x180019e2c  mov     r8, rbx; Size
0x180019e2f  cmovl   r15d, eax
0x180019e33  call    memmove_0
0x180019e38  mov     rcx, [r13+58h]
0x180019e3c  mov     rdx, rsi; Src
0x180019e3f  movsxd  r12, r15d
0x180019e42  add     rcx, rbx; void *
0x180019e45  mov     r8, r12; Size
0x180019e48  call    memcpy_0
0x180019e4d  mov     rax, [r13+58h]
0x180019e51  lea     rcx, [r12+rax]
0x180019e55  add     rcx, rbx
0x180019e58  mov     [r13+68h], rcx
0x180019e5c  mov     [r13+60h], rax
0x180019e60  cmp     dword ptr [r13+18C8h], 0
0x180019e68  mov     rdx, rax
0x180019e6b  jnz     loc_18001A679
0x180019e71  mov     r9, [r13+68h]
0x180019e75  lea     rcx, [rax+2]
0x180019e79  xor     r10b, r10b
0x180019e7c  lea     rbx, [r13+193Ch]
0x180019e83  cmp     rcx, r9
0x180019e86  ja      short loc_180019EC0
0x180019e88  cmp     byte ptr [rdx], 0FFh
0x180019e8b  jnz     short loc_180019E9C
0x180019e8d  movzx   ecx, byte ptr [rdx+1]
0x180019e91  mov     r8, rdx
0x180019e94  and     cl, 0F6h
0x180019e97  cmp     cl, 0F0h
0x180019e9a  jz      short loc_180019EC3
0x180019e9c  inc     rax
0x180019e9f  lea     rbx, [r13+193Ch]
0x180019ea6  inc     dword ptr [rbx]
0x180019ea8  mov     r10b, 1
0x180019eab  mov     [r13+60h], rax
0x180019eaf  mov     rdx, rax
0x180019eb2  mov     r8, rax
0x180019eb5  lea     rcx, [rax+2]
0x180019eb9  cmp     rcx, r9
0x180019ebc  jbe     short loc_180019E88
0x180019ebe  jmp     short loc_180019EC3
0x180019ec0  mov     r8, rdx
0x180019ec3  lea     rax, [r8+9]
0x180019ec7  cmp     rax, r9
0x180019eca  ja      loc_18001A0EE
0x180019ed0  test    r10b, r10b
0x180019ed3  jz      short loc_180019F40
0x180019ed5  mov     eax, [rbx]
0x180019ed7  lea     rdi, [r13+18h]
0x180019edb  inc     dword ptr [r13+1938h]
0x180019ee2  mov     [rbp+57h+var_A4], eax
0x180019ee5  lea     rax, [rbp+57h+var_A4]
0x180019ee9  mov     [rbp+57h+UserData.Ptr], rax
0x180019eed  mov     qword ptr [rbp+57h+UserData.Size], 4
0x180019ef5  test    rdi, rdi
0x180019ef8  jz      short loc_180019F40
0x180019efa  lea     rcx, [rdi+10h]; lpCriticalSection
0x180019efe  call    cs:__imp_EnterCriticalSection
0x180019f05  nop     dword ptr [rax+rax+00h]
0x180019f0a  cmp     dword ptr [rdi], 0
0x180019f0d  jnz     short loc_180019F30
0x180019f0f  mov     rcx, [rdi+8]; RegHandle
0x180019f13  lea     r9, [rbp+57h+UserData]; UserData
0x180019f17  mov     r8d, 1; UserDataCount
0x180019f1d  lea     rdx, MSMPEG2ADEC_AUD_RESYNC; EventDescriptor
0x180019f24  call    cs:__imp_EventWrite
0x180019f2b  nop     dword ptr [rax+rax+00h]
0x180019f30  lea     rcx, [rdi+10h]; lpCriticalSection
0x180019f34  call    cs:__imp_LeaveCriticalSection
0x180019f3b  nop     dword ptr [rax+rax+00h]
0x180019f40  mov     rdi, [r13+60h]
0x180019f44  movzx   eax, byte ptr [rdi+4]
0x180019f48  movzx   esi, byte ptr [rdi+3]
0x180019f4c  and     esi, 3
0x180019f4f  shl     esi, 8
0x180019f52  or      esi, eax
0x180019f54  movzx   eax, byte ptr [rdi+5]
0x180019f58  shr     eax, 5
0x180019f5b  shl     esi, 3
0x180019f5e  or      esi, eax
0x180019f60  lea     rax, [rdi+1]
0x180019f64  mov     [r13+1940h], esi
0x180019f6b  mov     [r13+178h], esi
0x180019f72  movzx   r8d, byte ptr [rax]
0x180019f76  not     r8b
0x180019f79  and     r8d, 1
0x180019f7d  mov     [r13+1944h], r8d
0x180019f84  movzx   ecx, byte ptr [rdi+3]
0x180019f88  movzx   edx, byte ptr [rdi+2]
0x180019f8c  and     edx, 1
0x180019f8f  shr     ecx, 6
0x180019f92  shl     edx, 2
0x180019f95  or      edx, ecx
0x180019f97  mov     qword ptr [r13+1920h], 0
0x180019fa2  mov     [rbp+57h+var_A8], edx
0x180019fa5  lea     rcx, [rbp+57h+var_A8]
0x180019fa9  mov     [r13+1918h], rcx
0x180019fb0  test    esi, esi
0x180019fb2  jz      loc_180019E5C
0x180019fb8  movzx   edx, byte ptr [rdi+2]
0x180019fbc  movzx   ecx, dl
0x180019fbf  and     cl, 0C0h
0x180019fc2  cmp     cl, 40h ; '@'
0x180019fc5  jnz     loc_180019E5C
0x180019fcb  test    byte ptr [rdi+6], 3
0x180019fcf  jnz     loc_180019E5C
0x180019fd5  mov     ecx, edx
0x180019fd7  shr     ecx, 2
0x180019fda  and     ecx, 0Fh
0x180019fdd  cmp     ecx, 0Bh
0x180019fe0  ja      loc_180019E5C
0x180019fe6  mov     ecx, [r14+rcx*4]
0x180019fea  cmp     [r13+1ABCh], ecx
0x180019ff1  jz      short loc_18001A026
0x180019ff3  mov     [r13+1ABCh], ecx
0x180019ffa  lea     rcx, [r13+1908h]
0x18001a001  cmp     qword ptr [rcx], 0
0x18001a005  jz      short loc_18001A01A
0x18001a007  call    AACAudioDecoderClose
0x18001a00c  mov     r8d, [r13+1944h]
0x18001a013  mov     esi, [r13+1940h]
0x18001a01a  mov     rdi, [r13+60h]
0x18001a01e  mov     dword ptr [r13+8], 1
0x18001a026  test    r8d, r8d
0x18001a029  jz      short loc_18001A03F
0x18001a02b  movzx   r14d, byte ptr [rdi+7]
0x18001a030  movzx   eax, byte ptr [rdi+8]
0x18001a034  shl     r14w, 8
0x18001a039  or      r14w, ax
0x18001a03d  jmp     short loc_18001A042
0x18001a03f  xor     r14d, r14d
0x18001a042  mov     [r13+1948h], r14w
0x18001a04a  mov     eax, esi
0x18001a04c  add     rax, rdi
0x18001a04f  mov     dword ptr [rbx], 0
0x18001a055  cmp     rax, [r13+68h]
0x18001a059  ja      loc_18001A0E7
0x18001a05f  test    r8d, r8d
0x18001a062  jz      short loc_18001A0AB
0x18001a064  mov     eax, 0FFFFh
0x18001a069  mov     ebx, 9
0x18001a06e  mov     word ptr [rbp+57h+var_B0], ax
0x18001a072  test    rdi, rdi
0x18001a075  jz      short loc_18001A093
0x18001a077  mov     r9d, 38h ; '8'
0x18001a07d  lea     rax, [rbp+57h+var_B0]
0x18001a081  mov     r8d, r9d
0x18001a084  mov     [rsp+0E0h+var_C0], rax
0x18001a089  xor     edx, edx
0x18001a08b  mov     rcx, rdi
0x18001a08e  call    CAacDecoderGenerateCRC
0x18001a093  xor     eax, eax
0x18001a095  mov     word ptr [rbp+57h+var_B0+2], r14w
0x18001a09a  cmp     [r13+188Ch], eax
0x18001a0a1  lea     rcx, [rbp+57h+var_B0]
0x18001a0a5  cmovnz  rcx, rax
0x18001a0a9  jmp     short loc_18001A0B2
0x18001a0ab  mov     ebx, 7
0x18001a0b0  xor     ecx, ecx
0x18001a0b2  mov     [rsp+0E0h+var_C0], rcx; unsigned __int16 *
0x18001a0b7  sub     esi, ebx
0x18001a0b9  mov     edx, ebx
0x18001a0bb  mov     r8d, esi; int
0x18001a0be  add     rdx, rdi; unsigned __int8 *
0x18001a0c1  xor     r9d, r9d; unsigned int
0x18001a0c4  mov     rcx, r13; this
0x18001a0c7  call    ?DecodeAACFrame@CIVIAudioCodec@@IEAAJPEAEJKPEAG@Z; CIVIAudioCodec::DecodeAACFrame(uchar *,long,ulong,ushort *)
0x18001a0cc  mov     eax, [r13+1940h]
0x18001a0d3  lea     r14, qword_18008DD50
0x18001a0da  add     [r13+60h], rax
0x18001a0de  mov     rax, [r13+60h]
0x18001a0e2  jmp     loc_180019E60
0x18001a0e7  lea     r14, qword_18008DD50
0x18001a0ee  mov     r8d, [rbp+57h+var_AC]
0x18001a0f2  sub     r8d, r15d
0x18001a0f5  jz      loc_18001A679
0x18001a0fb  mov     rsi, [rbp+57h+var_70]
0x18001a0ff  add     rsi, r12
0x18001a102  mov     [rbp+57h+var_70], rsi
0x18001a106  jmp     loc_180019DE0
0x18001a10b  mov     rax, cs:MEDIASUBTYPE_MPEG_LOAS
0x18001a112  cmp     rax, [rcx+88h]
0x18001a119  jnz     loc_18001A5E8
0x18001a11f  mov     rax, cs:qword_18008CF58
0x18001a126  cmp     rax, [rcx+90h]
0x18001a12d  jnz     loc_18001A5E8
0x18001a133  xorps   xmm0, xmm0
0x18001a136  movups  [rbp+57h+var_A0], xmm0
0x18001a13a  movups  [rbp+57h+var_90], xmm0
0x18001a13e  movups  [rbp+57h+var_80], xmm0
0x18001a142  mov     rdx, [r13+60h]
0x18001a146  xor     eax, eax
0x18001a148  mov     rcx, [r13+68h]
0x18001a14c  test    r8d, r8d
0x18001a14f  cmovns  eax, r8d
0x18001a153  sub     rcx, rdx
0x18001a156  mov     [rbp+57h+var_AC], eax
0x18001a159  mov     r8d, eax
0x18001a15c  cmp     rcx, 7FFFFFFFh
0x18001a163  jbe     short loc_18001A17A
0x18001a165  lea     rdx, [r13+1AD0h]; Src
0x18001a16c  xor     ecx, ecx
0x18001a16e  mov     [r13+68h], rdx
0x18001a172  mov     [r13+60h], rdx
0x18001a176  mov     [r13+58h], rdx
0x18001a17a  mov     r15d, r8d
0x18001a17d  movsxd  rbx, ecx
0x18001a180  mov     eax, 2040h
0x18001a185  sub     eax, ecx
0x18001a187  mov     rcx, [r13+58h]; void *
0x18001a18b  cmp     eax, r8d
0x18001a18e  mov     r8, rbx; Size
0x18001a191  cmovl   r15d, eax
0x18001a195  mov     [rbp+57h+var_68], r15d
0x18001a199  call    memmove_0
0x18001a19e  mov     rcx, [r13+58h]
0x18001a1a2  mov     rdx, rsi; Src
0x18001a1a5  movsxd  rdi, r15d
0x18001a1a8  add     rcx, rbx; void *
0x18001a1ab  mov     r8, rdi; Size
0x18001a1ae  mov     [rbp+57h+UserData.Ptr], rdi
0x18001a1b2  call    memcpy_0
0x18001a1b7  mov     rdx, [r13+58h]
0x18001a1bb  lea     rax, [rdi+rdx]
0x18001a1bf  add     rax, rbx
0x18001a1c2  mov     [r13+68h], rax
0x18001a1c6  mov     [r13+60h], rdx
0x18001a1ca  cmp     dword ptr [r13+18C8h], 0
0x18001a1d2  mov     rcx, rdx
0x18001a1d5  jnz     loc_18001A679
0x18001a1db  mov     r9, [r13+68h]
0x18001a1df  lea     rax, [rdx+3]
0x18001a1e3  xor     r10b, r10b
0x18001a1e6  lea     rbx, [r13+193Ch]
0x18001a1ed  cmp     rax, r9
0x18001a1f0  ja      short loc_18001A228
0x18001a1f2  cmp     byte ptr [rcx], 56h ; 'V'
0x18001a1f5  jnz     short loc_18001A204
0x18001a1f7  movzx   eax, byte ptr [rcx+1]
0x18001a1fb  mov     r8, rcx
0x18001a1fe  and     al, 0E0h
0x18001a200  cmp     al, 0E0h
0x18001a202  jz      short loc_18001A22B
0x18001a204  inc     rdx
0x18001a207  lea     rbx, [r13+193Ch]
0x18001a20e  inc     dword ptr [rbx]
0x18001a210  mov     r10b, 1
0x18001a213  mov     [r13+60h], rdx
0x18001a217  mov     rcx, rdx
0x18001a21a  mov     r8, rdx
0x18001a21d  lea     rax, [rdx+3]
  ... truncated ...
```

# CRDPVideoBitmapPresentation::SendPresentationStartToClient(ulong,_RDPGFX_PROVIDER_VIDEO_HINT_UPDATE *,IMFMediaType *,__int64)

- ea: `0x18009fe80`
- end: `0x1800a054b`
- name: `?SendPresentationStartToClient@CRDPVideoBitmapPresentation@@EEAAJKPEAU_RDPGFX_PROVIDER_VIDEO_HINT_UPDATE@@PEAUIMFMediaType@@_J@Z`
- size: `1739`
- prototype: `__int64 __fastcall(CRDPVideoBitmapPresentation *__hidden this, unsigned int, struct _RDPGFX_PROVIDER_VIDEO_HINT_UPDATE *, struct IMFMediaType *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18009f480`

## callees

- `0x1800091a8`
- `0x18002e600`
- `0x180033da0`
- `0x180034970`
- `0x1800598d0`
- `0x180081ba8`
- `0x18009c3e0`
- `0x18009fe80`
- `0x1800a0b44`
- `0x1800a0cf0`
- `0x18014c328`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a051f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a051f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a00bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a0311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a00bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a0311`

## string_xrefs

- `0x1800a00ea`: `"CoTaskMemAlloc( BYTE* )"`
- `0x1800a02fa`: `TSMM_MakeCompactFramerate() failed`

## pseudocode

```c
__int64 __fastcall CRDPVideoBitmapPresentation::SendPresentationStartToClient(
        CRDPVideoBitmapPresentationManager **this,
        int a2,
        struct _RDPGFX_PROVIDER_VIDEO_HINT_UPDATE *a3,
        struct IMFMediaType *a4,
        __int64 a5)
{
  PVOID *v8; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  int v13; // ebx
  unsigned int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  void *v17; // r14
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // edx
  const char *v21; // rcx
  int v22; // r15d
  PVOID *v23; // rax
  unsigned int v24; // eax
  unsigned int v25; // edi
  SIZE_T v26; // r12
  char *v27; // rax
  char *v28; // rbx
  unsigned int v29; // eax
  CRDPVideoBitmapPresentationManager *v30; // rcx
  unsigned int v31; // eax
  __int64 v32; // r8
  __int64 v34; // [rsp+28h] [rbp-48h]
  SIZE_T cb; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v36; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v37; // [rsp+3Ch] [rbp-34h] BYREF
  int v38; // [rsp+40h] [rbp-30h] BYREF
  int v39; // [rsp+44h] [rbp-2Ch] BYREF
  int v40; // [rsp+48h] [rbp-28h]
  GUID v41; // [rsp+50h] [rbp-20h] BYREF

  v40 = a2;
  cb = 0;
  v41 = GUID_00000000_0000_0000_0000_000000000000;
  v38 = 0;
  v39 = 0;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      78,
      &WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
      CurrentThreadActivityIdPrefix,
      this);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
      return (unsigned int)-2147467261;
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 79;
    v12 = "pVideoHint";
LABEL_10:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
      v10,
      (__int64)v12);
    return (unsigned int)-2147467261;
  }
  if ( !a4 )
  {
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
      return (unsigned int)-2147467261;
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 80;
    v12 = "pMediaType";
    goto LABEL_10;
  }
  v13 = MFGetAttribute2UINT32asUINT64(a4, &MF_MT_FRAME_SIZE, &v38, &v39);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 81;
      v16 = "MFGetAttributeSize( MF_MT_FRAME_SIZE ) failed";
LABEL_22:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
        v14,
        (__int64)v16,
        v13);
      return (unsigned int)v13;
    }
    return (unsigned int)v13;
  }
  v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))a4->lpVtbl->GetGUID)(
          a4,
          &MF_MT_SUBTYPE,
          &v41);
  if ( v13 >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, SIZE_T *))a4->lpVtbl->GetBlobSize)(
            a4,
            &MF_MT_MPEG_SEQUENCE_HEADER,
            &cb);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 83;
        v16 = "pMediaType->GetBlobSize( MF_MT_MPEG_SEQUENCE_HEADER ) failed";
        goto LABEL_22;
      }
      return (unsigned int)v13;
    }
    v17 = CoTaskMemAlloc((unsigned int)cb);
    if ( !v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          84,
          (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
          v18,
          (__int64)"\"CoTaskMemAlloc( BYTE* )\"");
      }
      return (unsigned int)-2147024882;
    }
    v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, void *, _QWORD, _QWORD))a4->lpVtbl->GetBlob)(
            a4,
            &MF_MT_MPEG_SEQUENCE_HEADER,
            v17,
            (unsigned int)cb,
            0);
    if ( v13 >= 0 )
    {
      v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, char *))a4->lpVtbl->GetUINT32)(
              a4,
              &MF_MT_AVG_BITRATE,
              (char *)&cb + 4);
      if ( v13 >= 0 )
      {
        v36 = 0;
        v37 = 0;
        v13 = MFGetAttribute2UINT32asUINT64(a4, &MF_MT_FRAME_RATE, &v36, &v37);
        if ( v13 >= 0 )
        {
          v22 = v36 / v37;
          if ( ((v36 / v37 - 1) & 0xFFFFFFC0) != 0 )
          {
            v13 = -2147467259;
            v23 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              goto LABEL_85;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v24 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                42,
                (unsigned int)WPP_2b9efb4e65de3739c4887646ec83aab4_Traceguids,
                v24,
                (__int64)"dwNumerator is too big.  Result will get truncated.",
                -2147467259);
              v23 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v23 == &WPP_GLOBAL_Control || (*((_BYTE *)v23 + 28) & 8) == 0 || *((_BYTE *)v23 + 25) < 2u )
              goto LABEL_85;
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            v20 = 88;
            v21 = "TSMM_MakeCompactFramerate() failed";
          }
          else
          {
            v25 = cb + 69;
            v26 = (unsigned int)(cb + 69);
            v27 = (char *)CoTaskMemAlloc(v26);
            v28 = v27;
            if ( !v27 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v29 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Ds(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  89,
                  (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
                  v29,
                  (__int64)"\"TSMM_PRESENTATION_REQUEST*\"");
              }
              v13 = -2147024882;
              goto LABEL_85;
            }
            memset_0(v27, 0, v26);
            v28[8] = v40;
            *(_DWORD *)v28 = v25;
            *((_DWORD *)v28 + 1) = 1;
            v28[11] = (v22 - 1) & 0x3F;
            *(_WORD *)(v28 + 9) = 257;
            *((_WORD *)v28 + 6) = HIDWORD(cb) / 0x3E8;
            *((_DWORD *)v28 + 4) = *((_DWORD *)a3 + 278) - *((_DWORD *)a3 + 276);
            *((_DWORD *)v28 + 5) = *((_DWORD *)a3 + 279) - *((_DWORD *)a3 + 277);
            *((_DWORD *)v28 + 6) = v38;
            *((_DWORD *)v28 + 7) = v39;
            *((_QWORD *)v28 + 4) = a5;
            *((_QWORD *)v28 + 5) = *((_QWORD *)a3 + 135);
            *((GUID *)v28 + 3) = v41;
            *((_DWORD *)v28 + 16) = cb;
            memcpy_0(v28 + 68, v17, (unsigned int)cb);
            v30 = this[10];
            if ( !v30 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) )
              {
                v31 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Ds(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  90,
                  (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
                  v31,
                  (__int64)"m_spPresentationManager");
              }
              CoTaskMemFree(v28);
              v13 = -2147418113;
              goto LABEL_85;
            }
            v13 = CRDPVideoBitmapPresentationManager::SendPacketToClient(v30, (unsigned __int8 *)v28, v25, 1);
            if ( v13 >= 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_ddd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  HIDWORD(cb) / 0x3E8,
                  v32,
                  (unsigned int)(*((_DWORD *)a3 + 278) - *((_DWORD *)a3 + 276)),
                  *((_DWORD *)a3 + 279) - *((_DWORD *)a3 + 277),
                  HIDWORD(cb) / 0x3E8);
              }
              goto LABEL_85;
            }
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
LABEL_85:
              CoTaskMemFree(v17);
              return (unsigned int)v13;
            }
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            v20 = 91;
            v21 = "m_spPresentationManager->SendPacketToClient() failed";
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_85;
          }
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 87;
          v21 = "MFGetAttributeRatio( MF_MT_FRAME_RATE ) failed";
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_85;
        }
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 86;
        v21 = "pMediaType->GetUINT32( MF_MT_AVG_BITRATE ) failed";
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 85;
      v21 = "pMediaType->GetBlob( MF_MT_MPEG_SEQUENCE_HEADER ) failed";
    }
    LODWORD(v34) = v13;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v20,
      (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
      v19,
      (__int64)v21,
      v34);
    goto LABEL_85;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 82;
    v16 = "pMediaType->GetGUID( MF_MT_SUBTYPE ) failed";
    goto LABEL_22;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18009fe80  mov     [rsp-38h+arg_8], rbx
0x18009fe85  push    rbp
0x18009fe86  push    rsi
0x18009fe87  push    rdi
0x18009fe88  push    r12
0x18009fe8a  push    r13
0x18009fe8c  push    r14
0x18009fe8e  push    r15
0x18009fe90  mov     rbp, rsp
0x18009fe93  sub     rsp, 70h
0x18009fe97  mov     rax, cs:__security_cookie
0x18009fe9e  xor     rax, rsp
0x18009fea1  mov     [rbp+var_10], rax
0x18009fea5  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18009feac  xor     r15d, r15d
0x18009feaf  mov     [rbp+var_28], edx
0x18009feb2  mov     rdi, r9
0x18009feb5  mov     dword ptr [rbp+cb], r15d
0x18009feb9  movdqu  [rbp+var_20], xmm0
0x18009febe  mov     rsi, r8
0x18009fec1  mov     [rbp+var_30], r15d
0x18009fec5  mov     r13, rcx
0x18009fec8  mov     [rbp+var_2C], r15d
0x18009fecc  mov     dword ptr [rbp+cb+4], r15d
0x18009fed0  mov     rax, cs:WPP_GLOBAL_Control
0x18009fed7  lea     r12, WPP_GLOBAL_Control
0x18009fede  lea     r14, WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids
0x18009fee5  cmp     rax, r12
0x18009fee8  jz      short loc_18009FF24
0x18009feea  test    dword ptr [rax+1Ch], 200h
0x18009fef1  jz      short loc_18009FF24
0x18009fef3  cmp     byte ptr [rax+19h], 4
0x18009fef7  jb      short loc_18009FF24
0x18009fef9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009fefe  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ff05  lea     edx, [r15+4Eh]
0x18009ff09  mov     r9d, eax
0x18009ff0c  mov     [rsp+70h+var_50], r13
0x18009ff11  mov     r8, r14
0x18009ff14  mov     rcx, [rcx+10h]
0x18009ff18  call    WPP_SF_Dq
0x18009ff1d  mov     rax, cs:WPP_GLOBAL_Control
0x18009ff24  test    rsi, rsi
0x18009ff27  jnz     short loc_18009FF6E
0x18009ff29  cmp     rax, r12
0x18009ff2c  jz      short loc_18009FF64
0x18009ff2e  test    byte ptr [rax+1Ch], 8
0x18009ff32  jz      short loc_18009FF64
0x18009ff34  cmp     byte ptr [rax+19h], 2
0x18009ff38  jb      short loc_18009FF64
0x18009ff3a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009ff3f  lea     edx, [rsi+4Fh]
0x18009ff42  lea     rcx, aPvideohint; "pVideoHint"
0x18009ff49  mov     [rsp+70h+var_50], rcx
0x18009ff4e  mov     r9d, eax
0x18009ff51  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ff58  mov     r8, r14
0x18009ff5b  mov     rcx, [rcx+10h]
0x18009ff5f  call    WPP_SF_Ds
0x18009ff64  mov     ebx, 80004003h
0x18009ff69  jmp     loc_1800A0525
0x18009ff6e  test    rdi, rdi
0x18009ff71  jnz     short loc_18009FF95
0x18009ff73  cmp     rax, r12
0x18009ff76  jz      short loc_18009FF64
0x18009ff78  test    byte ptr [rax+1Ch], 8
0x18009ff7c  jz      short loc_18009FF64
0x18009ff7e  cmp     byte ptr [rax+19h], 2
0x18009ff82  jb      short loc_18009FF64
0x18009ff84  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009ff89  lea     edx, [rdi+50h]
0x18009ff8c  lea     rcx, aPmediatype; "pMediaType"
0x18009ff93  jmp     short loc_18009FF49
0x18009ff95  lea     r9, [rbp+var_2C]
0x18009ff99  mov     rcx, rdi
0x18009ff9c  lea     r8, [rbp+var_30]
0x18009ffa0  lea     rdx, MF_MT_FRAME_SIZE
0x18009ffa7  call    MFGetAttribute2UINT32asUINT64
0x18009ffac  mov     ebx, eax
0x18009ffae  test    eax, eax
0x18009ffb0  jns     short loc_1800A000B
0x18009ffb2  mov     rax, cs:WPP_GLOBAL_Control
0x18009ffb9  cmp     rax, r12
0x18009ffbc  jz      loc_1800A0525
0x18009ffc2  test    byte ptr [rax+1Ch], 8
0x18009ffc6  jz      loc_1800A0525
0x18009ffcc  cmp     byte ptr [rax+19h], 2
0x18009ffd0  jb      loc_1800A0525
0x18009ffd6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009ffdb  mov     edx, 51h ; 'Q'
0x18009ffe0  lea     rcx, aMfgetattribute; "MFGetAttributeSize( MF_MT_FRAME_SIZE ) "...
0x18009ffe7  mov     dword ptr [rsp+70h+var_48], ebx
0x18009ffeb  mov     r9d, eax
0x18009ffee  mov     [rsp+70h+var_50], rcx
0x18009fff3  mov     r8, r14
0x18009fff6  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fffd  mov     rcx, [rcx+10h]
0x1800a0001  call    WPP_SF_DsD
0x1800a0006  jmp     loc_1800A0525
0x1800a000b  mov     rax, [rdi]
0x1800a000e  lea     r8, [rbp+var_20]
0x1800a0012  lea     rdx, MF_MT_SUBTYPE
0x1800a0019  mov     rcx, rdi
0x1800a001c  mov     rax, [rax+50h]
0x1800a0020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0025  mov     ebx, eax
0x1800a0027  test    eax, eax
0x1800a0029  jns     short loc_1800A0062
0x1800a002b  mov     rax, cs:WPP_GLOBAL_Control
0x1800a0032  cmp     rax, r12
0x1800a0035  jz      loc_1800A0525
0x1800a003b  test    byte ptr [rax+1Ch], 8
0x1800a003f  jz      loc_1800A0525
0x1800a0045  cmp     byte ptr [rax+19h], 2
0x1800a0049  jb      loc_1800A0525
0x1800a004f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a0054  mov     edx, 52h ; 'R'
0x1800a0059  lea     rcx, aPmediatypeGetg; "pMediaType->GetGUID( MF_MT_SUBTYPE ) fa"...
0x1800a0060  jmp     short loc_18009FFE7
0x1800a0062  mov     rax, [rdi]
0x1800a0065  lea     r8, [rbp+cb]
0x1800a0069  lea     rdx, MF_MT_MPEG_SEQUENCE_HEADER
0x1800a0070  mov     rcx, rdi
0x1800a0073  mov     rax, [rax+70h]
0x1800a0077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a007c  mov     ebx, eax
0x1800a007e  test    eax, eax
0x1800a0080  jns     short loc_1800A00BC
0x1800a0082  mov     rax, cs:WPP_GLOBAL_Control
0x1800a0089  cmp     rax, r12
0x1800a008c  jz      loc_1800A0525
0x1800a0092  test    byte ptr [rax+1Ch], 8
0x1800a0096  jz      loc_1800A0525
0x1800a009c  cmp     byte ptr [rax+19h], 2
0x1800a00a0  jb      loc_1800A0525
0x1800a00a6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a00ab  mov     edx, 53h ; 'S'
0x1800a00b0  lea     rcx, aPmediatypeGetb_0; "pMediaType->GetBlobSize( MF_MT_MPEG_SEQ"...
0x1800a00b7  jmp     loc_18009FFE7
0x1800a00bc  mov     ecx, dword ptr [rbp+cb]; cb
0x1800a00bf  call    cs:__imp_CoTaskMemAlloc
0x1800a00c5  mov     r14, rax
0x1800a00c8  test    rax, rax
0x1800a00cb  jnz     short loc_1800A011E
0x1800a00cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800a00d4  cmp     rax, r12
0x1800a00d7  jz      short loc_1800A0114
0x1800a00d9  test    byte ptr [rax+1Ch], 8
0x1800a00dd  jz      short loc_1800A0114
0x1800a00df  cmp     byte ptr [rax+19h], 2
0x1800a00e3  jb      short loc_1800A0114
0x1800a00e5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a00ea  lea     rcx, aCotaskmemalloc; "\"CoTaskMemAlloc( BYTE* )\""
0x1800a00f1  mov     r9d, eax
0x1800a00f4  mov     [rsp+70h+var_50], rcx
0x1800a00f9  lea     edx, [r14+54h]
0x1800a00fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0104  lea     r8, WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids
0x1800a010b  mov     rcx, [rcx+10h]
0x1800a010f  call    WPP_SF_Ds
0x1800a0114  mov     ebx, 8007000Eh
0x1800a0119  jmp     loc_1800A0525
0x1800a011e  mov     rax, [rdi]
0x1800a0121  lea     rdx, MF_MT_MPEG_SEQUENCE_HEADER
0x1800a0128  mov     r9d, dword ptr [rbp+cb]
0x1800a012c  mov     r8, r14
0x1800a012f  mov     rcx, rdi
0x1800a0132  mov     [rsp+70h+var_50], r15
0x1800a0137  mov     rax, [rax+78h]
0x1800a013b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0140  mov     ebx, eax
0x1800a0142  test    eax, eax
0x1800a0144  jns     short loc_1800A01A3
0x1800a0146  mov     rax, cs:WPP_GLOBAL_Control
0x1800a014d  cmp     rax, r12
0x1800a0150  jz      loc_1800A051C
0x1800a0156  test    byte ptr [rax+1Ch], 8
0x1800a015a  jz      loc_1800A051C
0x1800a0160  cmp     byte ptr [rax+19h], 2
0x1800a0164  jb      loc_1800A051C
0x1800a016a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a016f  mov     edx, 55h ; 'U'
0x1800a0174  lea     rcx, aPmediatypeGetb; "pMediaType->GetBlob( MF_MT_MPEG_SEQUENC"...
0x1800a017b  mov     dword ptr [rsp+70h+var_48], ebx
0x1800a017f  lea     r8, WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids
0x1800a0186  mov     [rsp+70h+var_50], rcx
0x1800a018b  mov     r9d, eax
0x1800a018e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0195  mov     rcx, [rcx+10h]
0x1800a0199  call    WPP_SF_DsD
0x1800a019e  jmp     loc_1800A051C
0x1800a01a3  mov     rax, [rdi]
0x1800a01a6  lea     r8, [rbp+cb+4]
0x1800a01aa  lea     rdx, MF_MT_AVG_BITRATE
0x1800a01b1  mov     rcx, rdi
0x1800a01b4  mov     rax, [rax+38h]
0x1800a01b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a01bd  mov     ebx, eax
0x1800a01bf  test    eax, eax
0x1800a01c1  jns     short loc_1800A01FA
0x1800a01c3  mov     rax, cs:WPP_GLOBAL_Control
0x1800a01ca  cmp     rax, r12
0x1800a01cd  jz      loc_1800A051C
0x1800a01d3  test    byte ptr [rax+1Ch], 8
0x1800a01d7  jz      loc_1800A051C
0x1800a01dd  cmp     byte ptr [rax+19h], 2
0x1800a01e1  jb      loc_1800A051C
0x1800a01e7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a01ec  mov     edx, 56h ; 'V'
0x1800a01f1  lea     rcx, aPmediatypeGetu; "pMediaType->GetUINT32( MF_MT_AVG_BITRAT"...
0x1800a01f8  jmp     short loc_1800A017B
0x1800a01fa  lea     r9, [rbp+var_34]
0x1800a01fe  mov     [rbp+var_38], r15d
0x1800a0202  lea     r8, [rbp+var_38]
0x1800a0206  mov     [rbp+var_34], r15d
0x1800a020a  lea     rdx, MF_MT_FRAME_RATE
0x1800a0211  mov     rcx, rdi
0x1800a0214  call    MFGetAttribute2UINT32asUINT64
0x1800a0219  mov     ebx, eax
0x1800a021b  test    eax, eax
0x1800a021d  jns     short loc_1800A0259
0x1800a021f  mov     rax, cs:WPP_GLOBAL_Control
0x1800a0226  cmp     rax, r12
0x1800a0229  jz      loc_1800A051C
0x1800a022f  test    byte ptr [rax+1Ch], 8
0x1800a0233  jz      loc_1800A051C
0x1800a0239  cmp     byte ptr [rax+19h], 2
0x1800a023d  jb      loc_1800A051C
0x1800a0243  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a0248  mov     edx, 57h ; 'W'
0x1800a024d  lea     rcx, aMfgetattribute_1; "MFGetAttributeRatio( MF_MT_FRAME_RATE )"...
0x1800a0254  jmp     loc_1800A017B
0x1800a0259  mov     eax, [rbp+var_38]
0x1800a025c  xor     edx, edx
0x1800a025e  div     [rbp+var_34]
0x1800a0261  mov     r15d, eax
0x1800a0264  lea     ecx, [rax-1]
0x1800a0267  test    ecx, 0FFFFFFC0h
0x1800a026d  jz      loc_1800A0306
0x1800a0273  mov     ebx, 80004005h
0x1800a0278  mov     rax, cs:WPP_GLOBAL_Control
0x1800a027f  cmp     rax, r12
0x1800a0282  jz      loc_1800A051C
0x1800a0288  test    byte ptr [rax+1Ch], 8
0x1800a028c  jz      short loc_1800A02D3
0x1800a028e  cmp     byte ptr [rax+19h], 2
0x1800a0292  jb      short loc_1800A02D3
0x1800a0294  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a0299  lea     rcx, aDwnumeratorIsT; "dwNumerator is too big.  Result will ge"...
0x1800a02a0  mov     dword ptr [rsp+70h+var_48], 80004005h
0x1800a02a8  mov     [rsp+70h+var_50], rcx
0x1800a02ad  lea     r8, WPP_2b9efb4e65de3739c4887646ec83aab4_Traceguids
0x1800a02b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a02bb  mov     edx, 2Ah ; '*'
0x1800a02c0  mov     r9d, eax
0x1800a02c3  mov     rcx, [rcx+10h]
0x1800a02c7  call    WPP_SF_DsD
0x1800a02cc  mov     rax, cs:WPP_GLOBAL_Control
0x1800a02d3  cmp     rax, r12
0x1800a02d6  jz      loc_1800A051C
0x1800a02dc  test    byte ptr [rax+1Ch], 8
0x1800a02e0  jz      loc_1800A051C
0x1800a02e6  cmp     byte ptr [rax+19h], 2
0x1800a02ea  jb      loc_1800A051C
0x1800a02f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a02f5  mov     edx, 58h ; 'X'
0x1800a02fa  lea     rcx, aTsmmMakecompac; "TSMM_MakeCompactFramerate() failed"
0x1800a0301  jmp     loc_1800A017B
0x1800a0306  mov     edi, dword ptr [rbp+cb]
0x1800a0309  add     edi, 45h ; 'E'
0x1800a030c  mov     ecx, edi; cb
0x1800a030e  mov     r12d, edi
0x1800a0311  call    cs:__imp_CoTaskMemAlloc
0x1800a0317  mov     rbx, rax
0x1800a031a  test    rax, rax
0x1800a031d  jnz     short loc_1800A0376
0x1800a031f  mov     rax, cs:WPP_GLOBAL_Control
0x1800a0326  lea     rdx, WPP_GLOBAL_Control
0x1800a032d  cmp     rax, rdx
0x1800a0330  jz      short loc_1800A036C
0x1800a0332  test    byte ptr [rax+1Ch], 8
0x1800a0336  jz      short loc_1800A036C
0x1800a0338  cmp     byte ptr [rax+19h], 2
0x1800a033c  jb      short loc_1800A036C
0x1800a033e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a0343  lea     rcx, aTsmmPresentati; "\"TSMM_PRESENTATION_REQUEST*\""
0x1800a034a  mov     r9d, eax
0x1800a034d  mov     [rsp+70h+var_50], rcx
0x1800a0352  lea     edx, [rbx+59h]
0x1800a0355  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a035c  lea     r8, WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids
0x1800a0363  mov     rcx, [rcx+10h]
0x1800a0367  call    WPP_SF_Ds
0x1800a036c  mov     ebx, 8007000Eh
0x1800a0371  jmp     loc_1800A051C
0x1800a0376  mov     r8, r12; Size
0x1800a0379  xor     edx, edx; Val
0x1800a037b  mov     rcx, rbx; void *
0x1800a037e  call    memset_0
0x1800a0383  mov     eax, [rbp+var_28]
  ... truncated ...
```

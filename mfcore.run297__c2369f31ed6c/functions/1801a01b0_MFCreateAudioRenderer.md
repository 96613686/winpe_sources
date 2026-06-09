# MFCreateAudioRenderer

- ea: `0x1801a01b0`
- end: `0x1801a0d04`
- name: `MFCreateAudioRenderer`
- size: `2900`
- prototype: `HRESULT __stdcall(IMFAttributes *pAudioAttributes, IMFMediaSink **ppSink)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802126c0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x18007cae0`
- `0x180091eb0`
- `0x180092630`
- `0x18009302c`
- `0x18009efc4`
- `0x1800cac5c`
- `0x1800ec0e0`
- `0x18013577c`
- `0x1801a01b0`
- `0x18025839c`
- `0x1802583a8`
- `0x1802583e8`
- `0x180258480`
- `0x1802592a0`
- `0x18031794c`
- `0x180317bd0`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0c9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0c9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0314`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a04ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a06c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0959`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0a22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0b5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0bfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0314`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a04ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a06c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0959`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0a22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0b5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0bfa`

## string_xrefs

- `0x1801a0287`: `MFCreateAudioRenderer`
- `0x1801a0372`: `MFCreateAudioRenderer`
- `0x1801a0548`: `MFCreateAudioRenderer`
- `0x1801a0724`: `MFCreateAudioRenderer`
- `0x1801a09b7`: `MFCreateAudioRenderer`
- `0x1801a0a80`: `MFCreateAudioRenderer`
- `0x1801a0bbb`: `MFCreateAudioRenderer`
- `0x1801a0c58`: `MFCreateAudioRenderer`
- `0x1801a0b17`: `CCreateAudioDevice::CreateAudioRenderer`

## pseudocode

```c
HRESULT __stdcall MFCreateAudioRenderer(IMFAttributes *pAudioAttributes, IMFMediaSink **ppSink)
{
  __int64 v4; // r14
  __int64 v5; // r12
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 *v9; // rcx
  HRESULT v10; // edi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  int v14; // eax
  int v15; // ecx
  bool v16; // sf
  struct IMFAttributesVtbl *lpVtbl; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 *v20; // rcx
  int v21; // ebx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // eax
  int v41; // ecx
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 *v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  _BYTE v55[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v56; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v57; // [rsp+38h] [rbp-C8h] BYREF
  int v58; // [rsp+3Ch] [rbp-C4h] BYREF
  int v59; // [rsp+40h] [rbp-C0h] BYREF
  int v60; // [rsp+44h] [rbp-BCh] BYREF
  int v61; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v62; // [rsp+4Ch] [rbp-B4h] BYREF
  int v63; // [rsp+50h] [rbp-B0h] BYREF
  int v64; // [rsp+54h] [rbp-ACh] BYREF
  int v65; // [rsp+58h] [rbp-A8h] BYREF
  int v66; // [rsp+5Ch] [rbp-A4h] BYREF
  int v67; // [rsp+60h] [rbp-A0h] BYREF
  int v68; // [rsp+64h] [rbp-9Ch] BYREF
  int v69; // [rsp+68h] [rbp-98h] BYREF
  int v70; // [rsp+6Ch] [rbp-94h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  int v72; // [rsp+78h] [rbp-88h] BYREF
  __int64 v73; // [rsp+80h] [rbp-80h] BYREF
  __int64 v74; // [rsp+88h] [rbp-78h] BYREF
  double v75; // [rsp+90h] [rbp-70h] BYREF
  double v76; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v77[192]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD Buf1[8]; // [rsp+160h] [rbp+60h] BYREF
  GUID v79; // [rsp+1E0h] [rbp+E0h] BYREF

  v58 = 0;
  v79 = guidExtendedType;
  v76 = 2.0;
  v75 = 0.0;
  v4 = 0;
  v73 = 0;
  pv = 0;
  v5 = 0;
  v72 = 0;
  v57 = 0;
  v62 = 0;
  v61 = 0;
  v74 = 0;
  v59 = 0;
  v60 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v56 = 0;
  memset(Buf1, 0, sizeof(Buf1));
  sub_18002FEE0(v55, "MFCreateAudioRenderer", 145);
  if ( pAudioAttributes && (unsigned __int8)byte_1803CECE9 >= 0x10u )
  {
    sub_180092630(v77, pAudioAttributes);
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    {
      v6 = sub_180091EB0(v77, 0);
      sub_1800CAC5C(*((_QWORD *)RequestContext + 7), 13, qword_18038DC50, v6);
    }
    sub_18009302C(v77);
  }
  memset(Buf1, 0, sizeof(Buf1));
  if ( !ppSink )
  {
    v9 = (__int64 *)qword_1803CEF18;
    v10 = -2147467261;
    if ( !qword_1803CEF18 )
    {
      v11 = MFGetCallStackTracingWeakReference(0, v7, v8);
      qword_1803CEF18 = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v9 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v9 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v12 = sub_1800402C0(v9);
      if ( *(_DWORD *)(v12 + 1996) != -2147467261 )
        sub_1800EC0E0(v12, "MFCreateAudioRenderer", 155, 2147500035LL);
    }
    if ( byte_1803CECE8 )
    {
      v13 = 14;
LABEL_17:
      sub_180050D6C(*((_QWORD *)RequestContext + 2), v13, qword_18038DC50, 0, v10);
      goto LABEL_137;
    }
    goto LABEL_137;
  }
  if ( (unsigned __int8)sub_180317BD0(qword_1803CF3C0) )
  {
    LODWORD(Buf1[6]) = 1;
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      sub_18009EFC4(*((_QWORD *)RequestContext + 7), 15, qword_18038DC50);
  }
  if ( !pAudioAttributes )
    goto LABEL_113;
  v14 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
          pAudioAttributes,
          qword_18037ADB0,
          &v58);
  v15 = Buf1[1];
  v16 = v14 < 0;
  lpVtbl = pAudioAttributes->lpVtbl;
  if ( !v16 )
    v15 = v58;
  LODWORD(Buf1[1]) = v15;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, GUID *))lpVtbl->GetGUID)(
         pAudioAttributes,
         qword_18037C8C8,
         &v79) >= 0 )
    Buf1[0] = v79;
  if ( !memcmp(Buf1, &guidExtendedType, 0x10u) && (Buf1[1] & 1) != 0 )
    LODWORD(Buf1[1]) ^= 1u;
  ((void (__fastcall *)(IMFAttributes *, __int64 *, __int64 *, __int64 *))pAudioAttributes->lpVtbl->GetUnknown)(
    pAudioAttributes,
    qword_18036BF60,
    qword_18036BF60,
    &v73);
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, LPVOID *, int *))pAudioAttributes->lpVtbl->GetAllocatedString)(
         pAudioAttributes,
         qword_18037C520,
         &pv,
         &v72) >= 0
    && ((int (__fastcall *)(IMFAttributes *, __int64 *, unsigned int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_18037B628,
         &v57) >= 0 )
  {
    v20 = (__int64 *)qword_1803CEF18;
    v21 = -2147024809;
    v10 = -2147024809;
    if ( !qword_1803CEF18 )
    {
      v22 = MFGetCallStackTracingWeakReference(0, v18, v19);
      qword_1803CEF18 = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v20 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v20 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v23 = sub_1800402C0(v20);
      if ( *(_DWORD *)(v23 + 1996) != -2147024809 )
        sub_1800EC0E0(v23, "MFCreateAudioRenderer", 193, 2147942487LL);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_137;
    v24 = 16;
    goto LABEL_136;
  }
  if ( pv )
  {
    *((_QWORD *)&Buf1[1] + 1) = pv;
  }
  else if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, unsigned int *))pAudioAttributes->lpVtbl->GetUINT32)(
              pAudioAttributes,
              qword_18037B628,
              &v57) >= 0 )
  {
    *(_QWORD *)&Buf1[2] = v57 | 0x100000000LL;
  }
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_18037B590,
         &v59) >= 0 )
    LODWORD(Buf1[4]) = v59 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_18037B160,
         &v60) >= 0 )
    DWORD1(Buf1[4]) = v60 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_1803787D0,
         &v61) >= 0 )
  {
    if ( v61 )
    {
      HIDWORD(Buf1[2]) = 1;
      DWORD1(Buf1[4]) = 1;
    }
    else
    {
      HIDWORD(Buf1[2]) = 0;
    }
  }
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, __int64 *))pAudioAttributes->lpVtbl->GetUINT64)(
         pAudioAttributes,
         qword_18037B030,
         &v74) >= 0 )
  {
    *((_QWORD *)&Buf1[3] + 1) = v74;
    LODWORD(Buf1[3]) = 1;
  }
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, unsigned int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_18037B3C8,
         &v62) >= 0 )
  {
    if ( v62 >= 0xF )
    {
      v27 = (__int64 *)qword_1803CEF18;
      v21 = -2147024809;
      v10 = -2147024809;
      if ( !qword_1803CEF18 )
      {
        v28 = MFGetCallStackTracingWeakReference(0, v25, v26);
        qword_1803CEF18 = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v27 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = sub_1800402C0(v27);
        if ( *(_DWORD *)(v29 + 1996) != -2147024809 )
          sub_1800EC0E0(v29, "MFCreateAudioRenderer", 245, 2147942487LL);
      }
      if ( !byte_1803CECE8 )
        goto LABEL_137;
      v24 = 17;
      goto LABEL_136;
    }
    DWORD2(Buf1[2]) = v62;
  }
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_18037B7D0,
         &v63) >= 0 )
    DWORD2(Buf1[4]) = v63 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_180377B30,
         &v64) >= 0 )
    HIDWORD(Buf1[4]) = v64 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_180377B40,
         &v65) >= 0 )
    LODWORD(Buf1[5]) = v65 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_180377B50,
         &v66) >= 0 )
    DWORD1(Buf1[5]) = v66 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_180377B70,
         &v67) >= 0 )
    LODWORD(Buf1[6]) = v67 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_18038DC60,
         &v68) >= 0 )
    DWORD2(Buf1[5]) = v68 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         qword_18037AB60,
         &v69) >= 0 )
    HIDWORD(Buf1[5]) = v69 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, double *))pAudioAttributes->lpVtbl->GetDouble)(
         pAudioAttributes,
         qword_18037C5D0,
         &v75) >= 0 )
    *((float *)&Buf1[6] + 2) = v75;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, double *))pAudioAttributes->lpVtbl->GetDouble)(
         pAudioAttributes,
         qword_180377B60,
         &v76) >= 0 )
    *((float *)&Buf1[6] + 3) = v76;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, unsigned int *))pAudioAttributes->lpVtbl->GetBlobSize)(
         pAudioAttributes,
         qword_180378790,
         &v56) < 0 )
  {
LABEL_110:
    v40 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
            pAudioAttributes,
            qword_180377B80,
            &v70);
    v41 = DWORD1(Buf1[6]);
    if ( v40 >= 0 )
      v41 = v70;
    DWORD1(Buf1[6]) = v41;
LABEL_113:
    v42 = sub_1802583A8(16);
    if ( v42 )
    {
      v4 = sub_18031794C(v42);
      if ( v4 )
      {
        v45 = v73;
        sub_18002FEE0(v55, "CCreateAudioDevice::CreateAudioRenderer", 80);
        v10 = sub_18013577C(Buf1, v45, ppSink);
        sub_18003ECB0(v55);
        if ( v10 < 0 )
        {
          v48 = (__int64 *)qword_1803CEF18;
          if ( !qword_1803CEF18 )
          {
            v49 = MFGetCallStackTracingWeakReference(0, v46, v47);
            qword_1803CEF18 = v49;
            if ( v49 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
            {
              v48 = (__int64 *)qword_1803CEF18;
            }
            else
            {
              v48 = &qword_1803CE250;
              qword_1803CEF18 = (__int64)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v48 + 8) )
          {
            v50 = sub_1800402C0(v48);
            if ( *(_DWORD *)(v50 + 1996) != v10 )
              sub_1800EC0E0(v50, "MFCreateAudioRenderer", 330, (unsigned int)v10);
          }
          if ( byte_1803CECE8 )
          {
            v13 = 21;
            goto LABEL_17;
          }
        }
        goto LABEL_137;
      }
    }
    v51 = (__int64 *)qword_1803CEF18;
    v21 = -2147024882;
    v10 = -2147024882;
    if ( !qword_1803CEF18 )
    {
      v52 = MFGetCallStackTracingWeakReference(0, v43, v44);
      qword_1803CEF18 = v52;
      if ( v52 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
      {
        v51 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v51 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v51 + 8) )
    {
      v53 = sub_1800402C0(v51);
      if ( *(_DWORD *)(v53 + 1996) != -2147024882 )
        sub_1800EC0E0(v53, "MFCreateAudioRenderer", 328, 2147942414LL);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_137;
    v24 = 20;
LABEL_136:
    sub_180050D6C(*((_QWORD *)RequestContext + 2), v24, qword_18038DC50, 0, v21);
    goto LABEL_137;
  }
  v5 = sub_1802583E8(v56);
  if ( !v5 )
  {
    v32 = (__int64 *)qword_1803CEF18;
    v21 = -2147024882;
    v10 = -2147024882;
    if ( !qword_1803CEF18 )
    {
      v33 = MFGetCallStackTracingWeakReference(0, v30, v31);
      qword_1803CEF18 = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
      {
        v32 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v32 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v34 = sub_1800402C0(v32);
      if ( *(_DWORD *)(v34 + 1996) != -2147024882 )
        sub_1800EC0E0(v34, "MFCreateAudioRenderer", 311, 2147942414LL);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_137;
    v24 = 18;
    goto LABEL_136;
  }
  v10 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64, _QWORD, unsigned int *))pAudioAttributes->lpVtbl->GetBlob)(
          pAudioAttributes,
          qword_180378790,
          v5,
          v56,
          &v56);
  if ( v10 >= 0 )
  {
    LODWORD(Buf1[7]) = v56;
    *((_QWORD *)&Buf1[7] + 1) = v5;
    goto LABEL_110;
  }
  v37 = (__int64 *)qword_1803CEF18;
  if ( !qword_1803CEF18 )
  {
    v38 = MFGetCallStackTracingWeakReference(0, v35, v36);
    qword_1803CEF18 = v38;
    if ( v38 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
    {
      v37 = (__int64 *)qword_1803CEF18;
    }
    else
    {
      v37 = &qword_1803CE250;
      qword_1803CEF18 = (__int64)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v37 + 8) )
  {
    v39 = sub_1800402C0(v37);
    if ( *(_DWORD *)(v39 + 1996) != v10 )
      sub_1800EC0E0(v39, "MFCreateAudioRenderer", 314, (unsigned int)v10);
  }
  if ( byte_1803CECE8 )
  {
    v13 = 19;
    goto LABEL_17;
  }
LABEL_137:
  CoTaskMemFree(pv);
  pv = 0;
  if ( v4 )
    sub_18007CAE0(v4);
  j_j__o_free(v5);
  sub_18003ECB0(v55);
  sub_180063F00(&v73);
  return v10;
}

```

## disassembly

```asm
0x1801a01b0  mov     [rsp-8+arg_10], rbx
0x1801a01b5  push    rbp
0x1801a01b6  push    rsi
0x1801a01b7  push    rdi
0x1801a01b8  push    r12
0x1801a01ba  push    r13
0x1801a01bc  push    r14
0x1801a01be  push    r15
0x1801a01c0  lea     rbp, [rsp-100h]
0x1801a01c8  sub     rsp, 200h
0x1801a01cf  mov     rax, cs:__security_cookie
0x1801a01d6  xor     rax, rsp
0x1801a01d9  mov     [rbp+130h+var_40], rax
0x1801a01e0  movups  xmm0, xmmword ptr cs:guidExtendedType.Data1
0x1801a01e7  xor     r13d, r13d
0x1801a01ea  mov     r15, rdx
0x1801a01ed  mov     rbx, rcx
0x1801a01f0  mov     [rsp+230h+var_1F4], r13d
0x1801a01f5  movdqu  [rbp+130h+var_50], xmm0
0x1801a01fd  lea     rcx, [rbp+130h+Buf1]; void *
0x1801a0201  mov     edi, 80h
0x1801a0206  movsd   xmm0, cs:qword_18036B938
0x1801a020e  xorps   xmm1, xmm1
0x1801a0211  mov     r8d, edi; Size
0x1801a0214  movsd   [rbp+130h+var_198], xmm0
0x1801a0219  xor     edx, edx; Val
0x1801a021b  movsd   [rbp+130h+var_1A0], xmm1
0x1801a0220  mov     r14d, r13d
0x1801a0223  mov     [rbp+130h+var_1B0], r13
0x1801a0227  mov     [rsp+230h+pv], r13
0x1801a022c  mov     r12d, r13d
0x1801a022f  mov     [rsp+230h+var_1B8], r13d
0x1801a0234  mov     [rsp+230h+var_1F8], r13d
0x1801a0239  mov     [rsp+230h+var_1E4], r13d
0x1801a023e  mov     [rsp+230h+var_1E8], r13d
0x1801a0243  mov     [rbp+130h+var_1A8], r13
0x1801a0247  mov     [rsp+230h+var_1F0], r13d
0x1801a024c  mov     [rsp+230h+var_1EC], r13d
0x1801a0251  mov     [rsp+230h+var_1E0], r13d
0x1801a0256  mov     [rsp+230h+var_1DC], r13d
0x1801a025b  mov     [rsp+230h+var_1D8], r13d
0x1801a0260  mov     [rsp+230h+var_1D4], r13d
0x1801a0265  mov     [rsp+230h+var_1D0], r13d
0x1801a026a  mov     [rsp+230h+var_1CC], r13d
0x1801a026f  mov     [rsp+230h+var_1C8], r13d
0x1801a0274  mov     [rsp+230h+var_1C4], r13d
0x1801a0279  mov     [rsp+230h+var_1FC], r13d
0x1801a027e  call    memset
0x1801a0283  lea     r8d, [rdi+11h]
0x1801a0287  lea     rdx, aMfcreateaudior_1; "MFCreateAudioRenderer"
0x1801a028e  lea     rcx, [rsp+230h+var_200]
0x1801a0293  call    sub_18002FEE0
0x1801a0298  test    rbx, rbx
0x1801a029b  jz      short loc_1801A02EC
0x1801a029d  cmp     cs:byte_1803CECE9, 10h
0x1801a02a4  jb      short loc_1801A02EC
0x1801a02a6  mov     rdx, rbx
0x1801a02a9  lea     rcx, [rbp+130h+var_190]
0x1801a02ad  call    sub_180092630
0x1801a02b2  cmp     cs:byte_1803CECE9, 10h
0x1801a02b9  jb      short loc_1801A02E3
0x1801a02bb  xor     edx, edx
0x1801a02bd  lea     rcx, [rbp+130h+var_190]
0x1801a02c1  call    sub_180091EB0
0x1801a02c6  mov     rcx, cs:RequestContext
0x1801a02cd  lea     edx, [rdi-73h]
0x1801a02d0  mov     r9, rax
0x1801a02d3  lea     r8, qword_18038DC50
0x1801a02da  mov     rcx, [rcx+38h]
0x1801a02de  call    sub_1800CAC5C
0x1801a02e3  lea     rcx, [rbp+130h+var_190]
0x1801a02e7  call    sub_18009302C
0x1801a02ec  mov     r8, rdi; Size
0x1801a02ef  lea     rcx, [rbp+130h+Buf1]; void *
0x1801a02f3  xor     edx, edx; Val
0x1801a02f5  call    memset
0x1801a02fa  test    r15, r15
0x1801a02fd  jnz     loc_1801A03A5
0x1801a0303  mov     rcx, cs:qword_1803CEF18
0x1801a030a  mov     edi, 80004003h
0x1801a030f  test    rcx, rcx
0x1801a0312  jnz     short loc_1801A035C
0x1801a0314  call    cs:MFGetCallStackTracingWeakReference
0x1801a031b  nop     dword ptr [rax+rax+00h]
0x1801a0320  mov     cs:qword_1803CEF18, rax
0x1801a0327  mov     rcx, rax
0x1801a032a  test    rax, rax
0x1801a032d  jz      short loc_1801A034E
0x1801a032f  mov     rax, [rax]
0x1801a0332  mov     edx, 7F0h
0x1801a0337  mov     rax, [rax+8]
0x1801a033b  call    cs:__guard_dispatch_icall_fptr
0x1801a0341  test    eax, eax
0x1801a0343  jz      short loc_1801A034E
0x1801a0345  mov     rcx, cs:qword_1803CEF18
0x1801a034c  jmp     short loc_1801A035C
0x1801a034e  lea     rcx, qword_1803CE250
0x1801a0355  mov     cs:qword_1803CEF18, rcx
0x1801a035c  cmp     [rcx+8], r13b
0x1801a0360  jz      short loc_1801A0387
0x1801a0362  call    sub_1800402C0
0x1801a0367  cmp     [rax+7CCh], edi
0x1801a036d  jz      short loc_1801A0387
0x1801a036f  mov     r9d, edi
0x1801a0372  lea     rdx, aMfcreateaudior_1; "MFCreateAudioRenderer"
0x1801a0379  mov     r8d, 9Bh
0x1801a037f  mov     rcx, rax
0x1801a0382  call    sub_1800EC0E0
0x1801a0387  mov     esi, 1
0x1801a038c  cmp     cs:byte_1803CECE8, sil
0x1801a0393  jb      loc_1801A0C99
0x1801a0399  lea     edx, [rsi+0Dh]
0x1801a039c  mov     dword ptr [rsp+230h+var_210], edi
0x1801a03a0  jmp     loc_1801A0C7F
0x1801a03a5  lea     rcx, qword_1803CF3C0
0x1801a03ac  call    sub_180317BD0
0x1801a03b1  mov     esi, 1
0x1801a03b6  test    al, al
0x1801a03b8  jz      short loc_1801A03E3
0x1801a03ba  mov     [rbp+130h+var_70], esi
0x1801a03c0  cmp     cs:byte_1803CECE9, 10h
0x1801a03c7  jb      short loc_1801A03E3
0x1801a03c9  mov     rcx, cs:RequestContext
0x1801a03d0  lea     edx, [rsi+0Eh]
0x1801a03d3  lea     r8, qword_18038DC50
0x1801a03da  mov     rcx, [rcx+38h]
0x1801a03de  call    sub_18009EFC4
0x1801a03e3  test    rbx, rbx
0x1801a03e6  jz      loc_1801A0AEC
0x1801a03ec  mov     rax, [rbx]
0x1801a03ef  lea     r8, [rsp+230h+var_1F4]
0x1801a03f4  lea     rdx, qword_18037ADB0
0x1801a03fb  mov     rcx, rbx
0x1801a03fe  mov     rax, [rax+38h]
0x1801a0402  call    cs:__guard_dispatch_icall_fptr
0x1801a0408  mov     ecx, [rbp+130h+var_C0]
0x1801a040b  lea     r8, [rbp+130h+var_50]
0x1801a0412  test    eax, eax
0x1801a0414  lea     rdx, qword_18037C8C8
0x1801a041b  mov     rax, [rbx]
0x1801a041e  cmovns  ecx, [rsp+230h+var_1F4]
0x1801a0423  mov     [rbp+130h+var_C0], ecx
0x1801a0426  mov     rcx, rbx
0x1801a0429  mov     rax, [rax+50h]
0x1801a042d  call    cs:__guard_dispatch_icall_fptr
0x1801a0433  test    eax, eax
0x1801a0435  js      short loc_1801A0442
0x1801a0437  movups  xmm0, [rbp+130h+var_50]
0x1801a043e  movups  [rbp+130h+Buf1], xmm0
0x1801a0442  mov     r8d, 10h; Size
0x1801a0448  lea     rdx, guidExtendedType; Buf2
0x1801a044f  lea     rcx, [rbp+130h+Buf1]; Buf1
0x1801a0453  call    memcmp
0x1801a0458  test    eax, eax
0x1801a045a  jnz     short loc_1801A0469
0x1801a045c  mov     eax, [rbp+130h+var_C0]
0x1801a045f  test    sil, al
0x1801a0462  jz      short loc_1801A0469
0x1801a0464  xor     eax, esi
0x1801a0466  mov     [rbp+130h+var_C0], eax
0x1801a0469  mov     rax, [rbx]
0x1801a046c  lea     rdx, qword_18036BF60
0x1801a0473  lea     r9, [rbp+130h+var_1B0]
0x1801a0477  mov     r8, rdx
0x1801a047a  mov     rcx, rbx
0x1801a047d  mov     rax, [rax+88h]
0x1801a0484  call    cs:__guard_dispatch_icall_fptr
0x1801a048a  mov     rax, [rbx]
0x1801a048d  lea     r9, [rsp+230h+var_1B8]
0x1801a0492  lea     r8, [rsp+230h+pv]
0x1801a0497  mov     rcx, rbx
0x1801a049a  lea     rdx, qword_18037C520
0x1801a04a1  mov     rax, [rax+68h]
0x1801a04a5  call    cs:__guard_dispatch_icall_fptr
0x1801a04ab  test    eax, eax
0x1801a04ad  js      loc_1801A0574
0x1801a04b3  mov     rax, [rbx]
0x1801a04b6  lea     r8, [rsp+230h+var_1F8]
0x1801a04bb  lea     rdx, qword_18037B628
0x1801a04c2  mov     rcx, rbx
0x1801a04c5  mov     rax, [rax+38h]
0x1801a04c9  call    cs:__guard_dispatch_icall_fptr
0x1801a04cf  test    eax, eax
0x1801a04d1  js      loc_1801A0574
0x1801a04d7  mov     rcx, cs:qword_1803CEF18
0x1801a04de  mov     ebx, 80070057h
0x1801a04e3  mov     edi, ebx
0x1801a04e5  test    rcx, rcx
0x1801a04e8  jnz     short loc_1801A0532
0x1801a04ea  call    cs:MFGetCallStackTracingWeakReference
0x1801a04f1  nop     dword ptr [rax+rax+00h]
0x1801a04f6  mov     cs:qword_1803CEF18, rax
0x1801a04fd  mov     rcx, rax
0x1801a0500  test    rax, rax
0x1801a0503  jz      short loc_1801A0524
0x1801a0505  mov     rax, [rax]
0x1801a0508  mov     edx, 7F0h
0x1801a050d  mov     rax, [rax+8]
0x1801a0511  call    cs:__guard_dispatch_icall_fptr
0x1801a0517  test    eax, eax
0x1801a0519  jz      short loc_1801A0524
0x1801a051b  mov     rcx, cs:qword_1803CEF18
0x1801a0522  jmp     short loc_1801A0532
0x1801a0524  lea     rcx, qword_1803CE250
0x1801a052b  mov     cs:qword_1803CEF18, rcx
0x1801a0532  cmp     [rcx+8], r13b
0x1801a0536  jz      short loc_1801A055D
0x1801a0538  call    sub_1800402C0
0x1801a053d  cmp     [rax+7CCh], ebx
0x1801a0543  jz      short loc_1801A055D
0x1801a0545  mov     r9d, ebx
0x1801a0548  lea     rdx, aMfcreateaudior_1; "MFCreateAudioRenderer"
0x1801a054f  mov     r8d, 0C1h
0x1801a0555  mov     rcx, rax
0x1801a0558  call    sub_1800EC0E0
0x1801a055d  cmp     cs:byte_1803CECE8, sil
0x1801a0564  jb      loc_1801A0C99
0x1801a056a  mov     edx, 10h
0x1801a056f  jmp     loc_1801A0C7B
0x1801a0574  mov     rax, [rsp+230h+pv]
0x1801a0579  test    rax, rax
0x1801a057c  jz      short loc_1801A0584
0x1801a057e  mov     [rbp+130h+var_B8], rax
0x1801a0582  jmp     short loc_1801A05B4
0x1801a0584  mov     rax, [rbx]
0x1801a0587  lea     r8, [rsp+230h+var_1F8]
0x1801a058c  lea     rdx, qword_18037B628
0x1801a0593  mov     rcx, rbx
0x1801a0596  mov     rax, [rax+38h]
0x1801a059a  call    cs:__guard_dispatch_icall_fptr
0x1801a05a0  test    eax, eax
0x1801a05a2  js      short loc_1801A05B4
0x1801a05a4  mov     eax, [rsp+230h+var_1F8]
0x1801a05a8  mov     [rbp+130h+var_B0], eax
0x1801a05ae  mov     [rbp+130h+var_AC], esi
0x1801a05b4  mov     rax, [rbx]
0x1801a05b7  lea     r8, [rsp+230h+var_1F0]
0x1801a05bc  lea     rdx, qword_18037B590
0x1801a05c3  mov     rcx, rbx
0x1801a05c6  mov     rax, [rax+38h]
0x1801a05ca  call    cs:__guard_dispatch_icall_fptr
0x1801a05d0  test    eax, eax
0x1801a05d2  js      short loc_1801A05E5
0x1801a05d4  cmp     [rsp+230h+var_1F0], r13d
0x1801a05d9  mov     eax, r13d
0x1801a05dc  setnz   al
0x1801a05df  mov     [rbp+130h+var_90], eax
0x1801a05e5  mov     rax, [rbx]
0x1801a05e8  lea     r8, [rsp+230h+var_1EC]
0x1801a05ed  lea     rdx, qword_18037B160
0x1801a05f4  mov     rcx, rbx
0x1801a05f7  mov     rax, [rax+38h]
0x1801a05fb  call    cs:__guard_dispatch_icall_fptr
0x1801a0601  test    eax, eax
0x1801a0603  js      short loc_1801A0616
0x1801a0605  cmp     [rsp+230h+var_1EC], r13d
0x1801a060a  mov     eax, r13d
0x1801a060d  setnz   al
0x1801a0610  mov     [rbp+130h+var_8C], eax
0x1801a0616  mov     rax, [rbx]
0x1801a0619  lea     r8, [rsp+230h+var_1E8]
0x1801a061e  lea     rdx, qword_1803787D0
0x1801a0625  mov     rcx, rbx
0x1801a0628  mov     rax, [rax+38h]
0x1801a062c  call    cs:__guard_dispatch_icall_fptr
0x1801a0632  test    eax, eax
0x1801a0634  js      short loc_1801A0652
0x1801a0636  cmp     [rsp+230h+var_1E8], r13d
0x1801a063b  jz      short loc_1801A064B
0x1801a063d  mov     [rbp+130h+var_A4], esi
0x1801a0643  mov     [rbp+130h+var_8C], esi
0x1801a0649  jmp     short loc_1801A0652
0x1801a064b  mov     [rbp+130h+var_A4], r13d
0x1801a0652  mov     rax, [rbx]
0x1801a0655  lea     r8, [rbp+130h+var_1A8]
0x1801a0659  lea     rdx, qword_18037B030
0x1801a0660  mov     rcx, rbx
0x1801a0663  mov     rax, [rax+40h]
0x1801a0667  call    cs:__guard_dispatch_icall_fptr
0x1801a066d  test    eax, eax
0x1801a066f  js      short loc_1801A0682
0x1801a0671  mov     rax, [rbp+130h+var_1A8]
0x1801a0675  mov     [rbp+130h+var_98], rax
0x1801a067c  mov     [rbp+130h+var_A0], esi
0x1801a0682  mov     rax, [rbx]
0x1801a0685  lea     r8, [rsp+230h+var_1E4]
0x1801a068a  lea     rdx, qword_18037B3C8
0x1801a0691  mov     rcx, rbx
0x1801a0694  mov     rax, [rax+38h]
0x1801a0698  call    cs:__guard_dispatch_icall_fptr
0x1801a069e  test    eax, eax
0x1801a06a0  js      loc_1801A0756
0x1801a06a6  mov     eax, [rsp+230h+var_1E4]
0x1801a06aa  cmp     eax, 0Fh
0x1801a06ad  jb      loc_1801A0750
0x1801a06b3  mov     rcx, cs:qword_1803CEF18
0x1801a06ba  mov     ebx, 80070057h
0x1801a06bf  mov     edi, ebx
0x1801a06c1  test    rcx, rcx
0x1801a06c4  jnz     short loc_1801A070E
  ... truncated ...
```

# SPPkcs11ExportKey

- ea: `0x180047efc`
- end: `0x1800489c0`
- name: `SPPkcs11ExportKey`
- size: `2756`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180029600`

## callees

- `0x1800010ec`
- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x18001a564`
- `0x18001f0a4`
- `0x180021120`
- `0x1800245d0`
- `0x180028a70`
- `0x180035c9c`
- `0x1800398b0`
- `0x180040cc8`
- `0x180047aa0`
- `0x180047efc`
- `0x18004dc24`
- `0x18004dd10`
- `0x18004ea80`
- `0x180062310`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180048367`
- `bcrypt!BCryptGenRandom` at `0x180048367`
- `bcrypt!BCryptDestroyKey` at `0x18004893c`
- `bcrypt!BCryptDestroyKey` at `0x18004893c`
- `bcrypt!BCryptExportKey` at `0x180048258`
- `bcrypt!BCryptExportKey` at `0x1800482bd`
- `bcrypt!BCryptExportKey` at `0x180048258`
- `bcrypt!BCryptExportKey` at `0x1800482bd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004897a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004897a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800482f2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800482f2`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800483a3`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800483a3`

## string_xrefs

- `0x180048310`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004846d`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004855e`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004860f`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`

## pseudocode

```c
__int64 __fastcall SPPkcs11ExportKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int *a6,
        int a7)
{
  __int64 v8; // rax
  __int64 v11; // rsi
  __int64 v12; // r12
  PUCHAR v13; // r15
  ULONG v14; // r14d
  __int64 v15; // r9
  int started; // eax
  _DWORD *v17; // rbx
  __int64 v18; // rax
  unsigned int v19; // edi
  __int64 v20; // rcx
  int v21; // eax
  ULONG v22; // r15d
  __int64 v23; // r14
  NTSTATUS v24; // edi
  UCHAR *v25; // rax
  NTSTATUS v26; // edi
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // r8
  ULONG v30; // ebx
  UCHAR *v31; // rax
  unsigned int v32; // edx
  __int64 v33; // rax
  unsigned int v34; // r8d
  unsigned int v35; // ebx
  unsigned int v36; // esi
  __int64 v37; // r9
  __int64 v38; // rcx
  _DWORD *v39; // r9
  unsigned int *v40; // rdx
  unsigned int v41; // ecx
  PUCHAR v42; // r8
  int v43; // eax
  _DWORD *v44; // r13
  unsigned int v45; // ebx
  int v46; // eax
  unsigned int v47; // ebx
  int v48; // r14d
  __int64 v49; // r9
  __int64 v50; // rax
  ULONG v51; // ecx
  int v52; // r13d
  const wchar_t *v53; // rdx
  int v54; // eax
  __int64 v55; // r9
  __int64 v56; // rax
  int v57; // ecx
  const wchar_t *v58; // rdx
  __int64 v59; // rcx
  PUCHAR v60; // rax
  ULONG cbBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v63; // [rsp+58h] [rbp-A8h] BYREF
  bool v64; // [rsp+60h] [rbp-A0h] BYREF
  PUCHAR pbSecret; // [rsp+68h] [rbp-98h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp-90h] BYREF
  size_t Size; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v68; // [rsp+7Ch] [rbp-84h] BYREF
  int v69; // [rsp+80h] [rbp-80h] BYREF
  __int64 v70; // [rsp+88h] [rbp-78h] BYREF
  __int64 v71; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v72; // [rsp+98h] [rbp-68h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-60h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+A8h] [rbp-58h] BYREF
  void *Src[2]; // [rsp+B0h] [rbp-50h] BYREF
  size_t v76; // [rsp+C0h] [rbp-40h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v78; // [rsp+D0h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v79; // [rsp+E0h] [rbp-20h] BYREF
  __int64 *v80; // [rsp+100h] [rbp+0h]
  __int64 v81; // [rsp+108h] [rbp+8h]
  __int64 *v82; // [rsp+110h] [rbp+10h]
  __int64 v83; // [rsp+118h] [rbp+18h]
  unsigned int **v84; // [rsp+120h] [rbp+20h]
  __int64 v85; // [rsp+128h] [rbp+28h]
  ULONG *p_cbBuffer; // [rsp+130h] [rbp+30h]
  __int64 v87; // [rsp+138h] [rbp+38h]
  PUCHAR *v88; // [rsp+140h] [rbp+40h]
  __int64 v89; // [rsp+148h] [rbp+48h]
  PUCHAR *p_pbSecret; // [rsp+150h] [rbp+50h]
  __int64 v91; // [rsp+158h] [rbp+58h]
  _QWORD v92[2]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v93[6]; // [rsp+170h] [rbp+70h] BYREF

  v63 = a5;
  v8 = (__int64)a6;
  v73 = a1;
  v72 = a6;
  v76 = 0;
  v11 = a3;
  v71 = a3;
  v68 = 0;
  v12 = 0;
  v13 = 0;
  Size = 0;
  v14 = 0;
  pcbResult = 0;
  pbSecret = 0;
  v70 = 0;
  phAlgorithm = 0;
  phKey = 0;
  cbBuffer = 0;
  *(_OWORD *)Src = 0;
  v69 = -1073741823;
  v78 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_fe1ed9a4da15309a55f4307617006ced_Traceguids,
      "SPPkcs11ExportKey");
    v8 = (__int64)v72;
  }
  if ( !a1 || !v11 || !v8 )
  {
    v15 = 5222;
    goto LABEL_94;
  }
  if ( !a2 )
  {
    v15 = 5229;
LABEL_94:
    v19 = -2146893785;
    v20 = 2148073511LL;
    goto LABEL_95;
  }
  if ( !a4 )
  {
    v15 = 5236;
    goto LABEL_94;
  }
  started = StartPerfMeasure(&v78);
  v69 = started;
  if ( started < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)WPP_fe1ed9a4da15309a55f4307617006ced_Traceguids,
      (unsigned int)"SPPkcs11ExportKey",
      started);
  if ( (int)KspGetPointerFromParameters(a4, (unsigned int)&v70, (unsigned int)&cbBuffer, 4, 96) < 0
    || (v17 = (_DWORD *)v70) == 0 )
  {
    v15 = 5259;
    goto LABEL_94;
  }
  if ( cbBuffer != 4 )
  {
    v15 = 5266;
    goto LABEL_94;
  }
  if ( ((*(_DWORD *)v70 - 128) & 0xFFFFFF3F) != 0 || *(_DWORD *)v70 == 320 )
  {
    v19 = -1073741811;
    v15 = 5273;
    v20 = 3221225485LL;
    goto LABEL_95;
  }
  if ( (int)KspGetStringBufferFromParameters(a4, Src, 97) < 0 || !Src[0] )
  {
    v15 = 5284;
    goto LABEL_94;
  }
  if ( (int)KspGetPointerFromParameters(a4, (unsigned int)&Src[1], (unsigned int)&v76, 0, 98) < 0 )
  {
    v15 = 5297;
    goto LABEL_94;
  }
  if ( *(_DWORD *)(*(_QWORD *)(a2 + 64) + 32LL) != 196609 )
  {
    v15 = 5305;
    goto LABEL_94;
  }
  if ( *(_DWORD *)(a2 + 28) <= *v17 )
  {
    v15 = 5312;
    goto LABEL_94;
  }
  v18 = *(_QWORD *)(v11 + 64);
  v14 = (unsigned int)(*v17 + 7) >> 3;
  cbBuffer = v14;
  if ( (*(_DWORD *)(v18 + 32) & 0xFFFF0000) != 0x30000 )
  {
    v24 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(v11 + 112), 0, L"KeyDataBlob", 0, 0, &pcbResult, 0);
    if ( v24 >= 0 )
    {
      v25 = (UCHAR *)SafeAllocaAllocateFromHeap(pcbResult);
      v12 = (__int64)v25;
      if ( !v25 )
      {
        v15 = 5397;
        goto LABEL_44;
      }
      v24 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(v11 + 112), 0, L"KeyDataBlob", v25, pcbResult, &pcbResult, 0);
      if ( v24 >= 0 )
      {
        v22 = *(_DWORD *)(v12 + 8);
        v23 = v12 + 12;
        goto LABEL_56;
      }
      v15 = 5411;
    }
    else
    {
      v15 = 5390;
    }
    v19 = v24 | 0x10000000;
    v20 = v19;
    goto LABEL_95;
  }
  if ( *(_DWORD *)(v18 + 32) != 196609
    && *(_DWORD *)(v18 + 32) != 196612
    && *(_DWORD *)(v18 + 32) != 196613
    && *(_DWORD *)(v18 + 32) != 196614
    && *(_DWORD *)(v18 + 32) != 196615
    && *(_DWORD *)(v18 + 32) != 196616
    && *(_DWORD *)(v18 + 32) != 196617
    && (unsigned int)(*(_DWORD *)(v18 + 32) - 196618) >= 2 )
  {
    v19 = -2146893821;
    v15 = 5371;
    v20 = 2148073475LL;
LABEL_95:
    DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v15);
    goto LABEL_96;
  }
  v21 = SPPkcs8ExportKey(v11, 0, 0, 0, &pcbResult, 0);
  v19 = v21;
  if ( v21 < 0 )
  {
    v15 = 5343;
LABEL_41:
    v20 = (unsigned int)v21;
    goto LABEL_95;
  }
  v12 = SafeAllocaAllocateFromHeap(pcbResult);
  if ( !v12 )
  {
    v15 = 5350;
LABEL_44:
    v19 = -2146893810;
    v20 = 2148073486LL;
    goto LABEL_95;
  }
  v21 = SPPkcs8ExportKey(v11, 0, (BYTE *)v12, pcbResult, &pcbResult, 0);
  v19 = v21;
  if ( v21 < 0 )
  {
    v15 = 5362;
    goto LABEL_41;
  }
  v22 = pcbResult;
  v23 = v12;
LABEL_56:
  v26 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  if ( v26 < 0 )
  {
    v27 = 5427;
LABEL_58:
    v19 = v26 | 0x10000000;
    v28 = v19;
LABEL_59:
    DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v27);
LABEL_60:
    v14 = cbBuffer;
    v13 = pbSecret;
LABEL_96:
    v39 = (_DWORD *)v63;
    goto LABEL_97;
  }
  v30 = cbBuffer;
  v31 = (UCHAR *)SafeAllocaAllocateFromHeap(cbBuffer);
  pbSecret = v31;
  if ( !v31 )
  {
    v19 = -2146893810;
    v27 = 5434;
    v28 = 2148073486LL;
    goto LABEL_59;
  }
  v26 = BCryptGenRandom(0, v31, v30, 2u);
  if ( v26 < 0 )
  {
    v27 = 5445;
    goto LABEL_58;
  }
  v26 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, v30, 0);
  if ( v26 < 0 )
  {
    v27 = 5459;
    goto LABEL_58;
  }
  v32 = (unsigned int)(*(_DWORD *)(a2 + 28) + 7) >> 3;
  v68 = v32;
  v33 = -1;
  do
    ++v33;
  while ( *((_WORD *)Src[0] + v33) );
  LODWORD(Size) = 2 * v33 + 2;
  v34 = 2 * v33 + 18 + v76;
  if ( v34 < 2 * (int)v33 + 18 )
  {
    v27 = 5475;
LABEL_71:
    v19 = -805306219;
    v28 = 3489661077LL;
    goto LABEL_59;
  }
  v35 = v34 + v32;
  if ( v34 + v32 < v34 )
  {
    v27 = 5485;
    goto LABEL_71;
  }
  v26 = SPPkcs11AesKeyWrapPad(phKey, v23, v22, 0, (char *)&Size + 4);
  if ( v26 < 0 )
  {
    v27 = 5499;
    goto LABEL_58;
  }
  v36 = v35 + HIDWORD(Size);
  if ( v35 + HIDWORD(Size) < v35 )
  {
    v19 = -805306219;
    v37 = 5510;
    v38 = 3489661077LL;
LABEL_78:
    DebugTraceError(v38, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v37);
    v11 = v71;
    goto LABEL_60;
  }
  v39 = (_DWORD *)v63;
  v40 = v72;
  if ( !v63 || !*v72 )
  {
    v14 = cbBuffer;
    v19 = 0;
    v13 = pbSecret;
    *v72 = v36;
    v11 = v71;
    goto LABEL_97;
  }
  if ( *v72 < v36 )
  {
    v19 = -2146893784;
    v37 = 5524;
    v38 = 2148073512LL;
    goto LABEL_78;
  }
  v41 = v68 + HIDWORD(Size);
  v42 = pbSecret;
  *(_DWORD *)(v63 + 8) = Size;
  v39[3] = v76;
  v39[1] = v41;
  *v39 = 1464877394;
  v43 = SPCryptEncrypt(v73, a2, v42, cbBuffer, Src, v39 + 4, *v40 - 16, &v68, 4);
  v19 = v43;
  if ( v43 < 0 )
  {
    v37 = 5548;
    v38 = (unsigned int)v43;
    goto LABEL_78;
  }
  v44 = (_DWORD *)v63;
  v45 = v68 + 16;
  v46 = SPPkcs11AesKeyWrapPad(phKey, v23, v22, v63 + v68 + 16, (char *)&Size + 4);
  if ( v46 >= 0 )
  {
    v47 = HIDWORD(Size) + v45;
    v48 = Size;
    memcpy_0((char *)v44 + v47, Src[0], (unsigned int)Size);
    memcpy_0((char *)v44 + v47 + v48, Src[1], (unsigned int)v76);
    *v72 = v36;
  }
  else
  {
    v19 = v46 | 0x10000000;
    DebugTraceError(v46 | 0x10000000u, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 5563);
  }
  v11 = v71;
  v39 = v44;
  v14 = cbBuffer;
  v13 = pbSecret;
LABEL_97:
  if ( (unsigned int)dword_180079068 <= 5 )
  {
    v52 = Size;
  }
  else if ( (unsigned __int8)tlgKeywordOn(&dword_180079068, 0x800000000000LL, v29, v39) )
  {
    v81 = 8;
    v80 = &v73;
    v82 = &v70;
    v84 = (unsigned int **)((char *)&Size + 4);
    v73 = 1;
    v70 = 0x1000000;
    v83 = 8;
    HIDWORD(Size) = v19;
    v85 = 4;
    if ( v11 && (v50 = *(_QWORD *)(v11 + 64)) != 0 )
      v51 = *(_DWORD *)(v50 + 32);
    else
      v51 = 0;
    v52 = Size;
    p_cbBuffer = &cbBuffer;
    cbBuffer = v51;
    v88 = (PUCHAR *)&v64;
    v64 = v49 != 0;
    v87 = 4;
    p_pbSecret = &pbSecret;
    v89 = 1;
    LODWORD(pbSecret) = v14;
    v91 = 4;
    if ( !(_DWORD)Size || (v53 = (const wchar_t *)Src[0]) == 0 )
      v53 = L"NULL";
    tlgCreate1Sz_wchar_t(v92, v53);
    LODWORD(Size) = a7;
    v93[0] = &Size;
    v93[1] = 4;
    tlgWriteAgg((int)&dword_180079068, (int)&word_18007018E, 0, 10, &v79);
  }
  else
  {
    v52 = Size;
  }
  if ( v69 >= 0 && (v19 & 0x80000000) == 0 )
  {
    v70 = 0;
    v54 = EndPerfMeasure(v78, &v70);
    if ( v54 >= 0 )
    {
      if ( dword_180079068 && (unsigned __int8)tlgKeywordOn(&dword_180079068, 0x400000000000LL, 0, v55) )
      {
        v81 = 8;
        v80 = &v73;
        v72 = (unsigned int *)v70;
        v71 = v70;
        v82 = &v70;
        p_cbBuffer = (ULONG *)&v71;
        v73 = 1;
        v83 = 8;
        v84 = &v72;
        v85 = 8;
        v87 = 8;
        if ( v11 && (v56 = *(_QWORD *)(v11 + 64)) != 0 )
          v57 = *(_DWORD *)(v56 + 32);
        else
          v57 = 0;
        v88 = &pbSecret;
        p_pbSecret = (PUCHAR *)&v64;
        v64 = v63 != 0;
        LODWORD(pbSecret) = v57;
        v92[0] = &v69;
        v89 = 4;
        v91 = 1;
        v69 = v14;
        v92[1] = 4;
        if ( !v52 || (v58 = (const wchar_t *)Src[0]) == 0 )
          v58 = L"NULL";
        tlgCreate1Sz_wchar_t(v93, v58);
        HIDWORD(Size) = a7;
        v93[2] = (char *)&Size + 4;
        v93[3] = 4;
        v93[4] = &v63;
        v63 = 50331648;
        v93[5] = 8;
        tlgWriteAgg((int)&dword_180079068, (int)&byte_180070289, 0, 12, &v79);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_fe1ed9a4da15309a55f4307617006ced_Traceguids,
        (unsigned int)"SPPkcs11ExportKey",
        v54);
    }
  }
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( v13 )
  {
    v59 = v14;
    v60 = v13;
    if ( v14 )
    {
      do
      {
        *v60++ = 0;
        --v59;
      }
      while ( v59 );
    }
    MSCryptFree(v13);
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v12 )
    MSCryptFree(v12);
  return v19;
}

```

## disassembly

```asm
0x180047efc  mov     [rsp-8+arg_0], rbx
0x180047f01  push    rbp
0x180047f02  push    rsi
0x180047f03  push    rdi
0x180047f04  push    r12
0x180047f06  push    r13
0x180047f08  push    r14
0x180047f0a  push    r15
0x180047f0c  lea     rbp, [rsp-0B0h]
0x180047f14  sub     rsp, 1B0h
0x180047f1b  mov     rax, cs:__security_cookie
0x180047f22  xor     rax, rsp
0x180047f25  mov     [rbp+0E0h+var_40], rax
0x180047f2c  mov     rax, [rbp+0E0h+arg_20]
0x180047f33  mov     r13, rdx
0x180047f36  xor     edx, edx
0x180047f38  mov     [rsp+1E0h+var_188], rax
0x180047f3d  mov     rax, [rbp+0E0h+arg_28]
0x180047f44  mov     rbx, rcx
0x180047f47  mov     [rbp+0E0h+var_140], rcx
0x180047f4b  xorps   xmm0, xmm0
0x180047f4e  xor     ecx, ecx
0x180047f50  mov     [rbp+0E0h+var_148], rax
0x180047f54  mov     [rbp+0E0h+var_120], rcx
0x180047f58  mov     rdi, r9
0x180047f5b  mov     rsi, r8
0x180047f5e  mov     [rbp+0E0h+var_150], r8
0x180047f62  mov     [rsp+1E0h+var_164], edx
0x180047f66  mov     r12d, edx
0x180047f69  mov     dword ptr [rsp+1E0h+Size+4], edx
0x180047f6d  mov     r15d, edx
0x180047f70  mov     dword ptr [rsp+1E0h+Size], edx
0x180047f74  mov     r14d, edx
0x180047f77  mov     [rsp+1E0h+var_170], edx
0x180047f7b  mov     [rsp+1E0h+pbSecret], rdx
0x180047f80  mov     [rbp+0E0h+var_158], rdx
0x180047f84  mov     [rbp+0E0h+phAlgorithm], rdx
0x180047f88  mov     [rbp+0E0h+phKey], rdx
0x180047f8c  mov     [rsp+1E0h+cbBuffer], edx
0x180047f90  movups  xmmword ptr [rbp+0E0h+Src], xmm0
0x180047f94  mov     [rbp+0E0h+var_160], 0C0000001h
0x180047f9b  mov     [rbp+0E0h+var_110], rdx
0x180047f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fa6  lea     r8, WPP_GLOBAL_Control
0x180047fad  cmp     rcx, r8
0x180047fb0  jz      short loc_180047FD7
0x180047fb2  test    byte ptr [rcx+1Ch], 8
0x180047fb6  jz      short loc_180047FD7
0x180047fb8  mov     rcx, [rcx+10h]
0x180047fbc  lea     edx, [r15+0Ch]
0x180047fc0  lea     r9, aSppkcs11export; "SPPkcs11ExportKey"
0x180047fc7  lea     r8, WPP_fe1ed9a4da15309a55f4307617006ced_Traceguids
0x180047fce  call    WPP_SF_s
0x180047fd3  mov     rax, [rbp+0E0h+var_148]
0x180047fd7  test    rbx, rbx
0x180047fda  jz      loc_1800485FF
0x180047fe0  test    rsi, rsi
0x180047fe3  jz      loc_1800485FF
0x180047fe9  test    rax, rax
0x180047fec  jz      loc_1800485FF
0x180047ff2  test    r13, r13
0x180047ff5  jnz     short loc_180048002
0x180047ff7  mov     r9d, 146Dh
0x180047ffd  jmp     loc_180048605
0x180048002  test    rdi, rdi
0x180048005  jnz     short loc_180048012
0x180048007  mov     r9d, 1474h
0x18004800d  jmp     loc_180048605
0x180048012  lea     rcx, [rbp+0E0h+var_110]
0x180048016  call    StartPerfMeasure
0x18004801b  mov     [rbp+0E0h+var_160], eax
0x18004801e  test    eax, eax
0x180048020  jns     short loc_18004805B
0x180048022  mov     rcx, cs:WPP_GLOBAL_Control
0x180048029  lea     rdx, WPP_GLOBAL_Control
0x180048030  cmp     rcx, rdx
0x180048033  jz      short loc_18004805B
0x180048035  test    byte ptr [rcx+1Ch], 1
0x180048039  jz      short loc_18004805B
0x18004803b  mov     rcx, [rcx+10h]
0x18004803f  lea     r9, aSppkcs11export; "SPPkcs11ExportKey"
0x180048046  mov     edx, 0Dh
0x18004804b  mov     [rsp+1E0h+cbOutput], eax
0x18004804f  lea     r8, WPP_fe1ed9a4da15309a55f4307617006ced_Traceguids
0x180048056  call    WPP_SF_sD
0x18004805b  mov     r9d, 4
0x180048061  mov     [rsp+1E0h+cbOutput], 60h ; '`'
0x180048069  lea     r8, [rsp+1E0h+cbBuffer]
0x18004806e  mov     rcx, rdi
0x180048071  lea     rdx, [rbp+0E0h+var_158]
0x180048075  call    KspGetPointerFromParameters
0x18004807a  test    eax, eax
0x18004807c  js      loc_1800485F7
0x180048082  mov     rbx, [rbp+0E0h+var_158]
0x180048086  test    rbx, rbx
0x180048089  jz      loc_1800485F7
0x18004808f  cmp     [rsp+1E0h+cbBuffer], 4
0x180048094  jz      short loc_1800480A1
0x180048096  mov     r9d, 1492h
0x18004809c  jmp     loc_180048605
0x1800480a1  mov     ecx, [rbx]
0x1800480a3  lea     eax, [rcx-80h]
0x1800480a6  test    eax, 0FFFFFF3Fh
0x1800480ab  jnz     loc_1800485E5
0x1800480b1  cmp     ecx, 140h
0x1800480b7  jz      loc_1800485E5
0x1800480bd  mov     r8d, 61h ; 'a'
0x1800480c3  lea     rdx, [rbp+0E0h+Src]
0x1800480c7  mov     rcx, rdi
0x1800480ca  call    KspGetStringBufferFromParameters
0x1800480cf  xor     ecx, ecx
0x1800480d1  test    eax, eax
0x1800480d3  js      loc_1800485DD
0x1800480d9  cmp     [rbp+0E0h+Src], rcx
0x1800480dd  jz      loc_1800485DD
0x1800480e3  xor     r9d, r9d
0x1800480e6  mov     [rsp+1E0h+cbOutput], 62h ; 'b'
0x1800480ee  lea     r8, [rbp+0E0h+var_120]
0x1800480f2  mov     rcx, rdi
0x1800480f5  lea     rdx, [rbp+0E0h+Src+8]
0x1800480f9  call    KspGetPointerFromParameters
0x1800480fe  test    eax, eax
0x180048100  jns     short loc_18004810D
0x180048102  mov     r9d, 14B1h
0x180048108  jmp     loc_180048605
0x18004810d  mov     rax, [r13+40h]
0x180048111  mov     edx, 30001h
0x180048116  cmp     [rax+20h], edx
0x180048119  jz      short loc_180048126
0x18004811b  mov     r9d, 14B9h
0x180048121  jmp     loc_180048605
0x180048126  mov     eax, [rbx]
0x180048128  cmp     [r13+1Ch], eax
0x18004812c  ja      short loc_180048139
0x18004812e  mov     r9d, 14C0h
0x180048134  jmp     loc_180048605
0x180048139  lea     r14d, [rax+7]
0x18004813d  mov     rax, [rsi+40h]
0x180048141  shr     r14d, 3
0x180048145  mov     [rsp+1E0h+cbBuffer], r14d
0x18004814a  mov     ecx, [rax+20h]
0x18004814d  mov     eax, ecx
0x18004814f  and     eax, 0FFFF0000h
0x180048154  cmp     eax, 30000h
0x180048159  jnz     loc_180048234
0x18004815f  sub     ecx, edx
0x180048161  jz      short loc_1800481A0
0x180048163  sub     ecx, 3
0x180048166  jz      short loc_1800481A0
0x180048168  sub     ecx, 1
0x18004816b  jz      short loc_1800481A0
0x18004816d  sub     ecx, 1
0x180048170  jz      short loc_1800481A0
0x180048172  sub     ecx, 1
0x180048175  jz      short loc_1800481A0
0x180048177  sub     ecx, 1
0x18004817a  jz      short loc_1800481A0
0x18004817c  sub     ecx, 1
0x18004817f  jz      short loc_1800481A0
0x180048181  sub     ecx, 1
0x180048184  jz      short loc_1800481A0
0x180048186  cmp     ecx, 1
0x180048189  jz      short loc_1800481A0
0x18004818b  mov     edi, 80090003h
0x180048190  mov     r9d, 14FBh
0x180048196  mov     ecx, 80090003h
0x18004819b  jmp     loc_18004860F
0x1800481a0  lea     rax, [rsp+1E0h+var_170]
0x1800481a5  xor     ebx, ebx
0x1800481a7  mov     dword ptr [rsp+1E0h+pcbResult], ebx
0x1800481ab  xor     r9d, r9d
0x1800481ae  xor     r8d, r8d
0x1800481b1  mov     qword ptr [rsp+1E0h+cbOutput], rax
0x1800481b6  xor     edx, edx
0x1800481b8  mov     rcx, rsi
0x1800481bb  call    SPPkcs8ExportKey
0x1800481c0  mov     edi, eax
0x1800481c2  test    eax, eax
0x1800481c4  jns     short loc_1800481D3
0x1800481c6  mov     r9d, 14DFh
0x1800481cc  mov     ecx, eax
0x1800481ce  jmp     loc_18004860F
0x1800481d3  mov     ecx, [rsp+1E0h+var_170]
0x1800481d7  call    SafeAllocaAllocateFromHeap
0x1800481dc  mov     r12, rax
0x1800481df  test    rax, rax
0x1800481e2  jnz     short loc_1800481F9
0x1800481e4  mov     r9d, 14E6h
0x1800481ea  mov     edi, 8009000Eh
0x1800481ef  mov     ecx, 8009000Eh
0x1800481f4  jmp     loc_18004860F
0x1800481f9  mov     r9d, [rsp+1E0h+var_170]
0x1800481fe  lea     rax, [rsp+1E0h+var_170]
0x180048203  mov     dword ptr [rsp+1E0h+pcbResult], ebx
0x180048207  mov     r8, r12
0x18004820a  xor     edx, edx
0x18004820c  mov     qword ptr [rsp+1E0h+cbOutput], rax
0x180048211  mov     rcx, rsi
0x180048214  call    SPPkcs8ExportKey
0x180048219  mov     edi, eax
0x18004821b  test    eax, eax
0x18004821d  jns     short loc_180048227
0x18004821f  mov     r9d, 14F2h
0x180048225  jmp     short loc_1800481CC
0x180048227  mov     r15d, [rsp+1E0h+var_170]
0x18004822c  mov     r14, r12
0x18004822f  jmp     loc_1800482E1
0x180048234  mov     rcx, [rsi+70h]; hKey
0x180048238  lea     rax, [rsp+1E0h+var_170]
0x18004823d  xor     ebx, ebx
0x18004823f  lea     r8, aKeydatablob; "KeyDataBlob"
0x180048246  mov     [rsp+1E0h+dwFlags], ebx; dwFlags
0x18004824a  xor     r9d, r9d; pbOutput
0x18004824d  mov     [rsp+1E0h+pcbResult], rax; pcbResult
0x180048252  xor     edx, edx; hExportKey
0x180048254  mov     [rsp+1E0h+cbOutput], ebx; cbOutput
0x180048258  call    cs:__imp_BCryptExportKey
0x18004825f  nop     dword ptr [rax+rax+00h]
0x180048264  mov     edi, eax
0x180048266  test    eax, eax
0x180048268  jns     short loc_18004827B
0x18004826a  mov     r9d, 150Eh
0x180048270  bts     edi, 1Ch
0x180048274  mov     ecx, edi
0x180048276  jmp     loc_18004860F
0x18004827b  mov     ecx, [rsp+1E0h+var_170]
0x18004827f  call    SafeAllocaAllocateFromHeap
0x180048284  mov     r12, rax
0x180048287  test    rax, rax
0x18004828a  jnz     short loc_180048297
0x18004828c  mov     r9d, 1515h
0x180048292  jmp     loc_1800481EA
0x180048297  mov     rcx, [rsi+70h]; hKey
0x18004829b  lea     rax, [rsp+1E0h+var_170]
0x1800482a0  mov     [rsp+1E0h+dwFlags], ebx; dwFlags
0x1800482a4  lea     r8, aKeydatablob; "KeyDataBlob"
0x1800482ab  mov     [rsp+1E0h+pcbResult], rax; pcbResult
0x1800482b0  mov     r9, r12; pbOutput
0x1800482b3  mov     eax, [rsp+1E0h+var_170]
0x1800482b7  xor     edx, edx; hExportKey
0x1800482b9  mov     [rsp+1E0h+cbOutput], eax; cbOutput
0x1800482bd  call    cs:__imp_BCryptExportKey
0x1800482c4  nop     dword ptr [rax+rax+00h]
0x1800482c9  mov     edi, eax
0x1800482cb  test    eax, eax
0x1800482cd  jns     short loc_1800482D7
0x1800482cf  mov     r9d, 1523h
0x1800482d5  jmp     short loc_180048270
0x1800482d7  mov     r15d, [r12+8]
0x1800482dc  lea     r14, [r12+0Ch]
0x1800482e1  xor     r9d, r9d; dwFlags
0x1800482e4  lea     rdx, aAes; "AES"
0x1800482eb  xor     r8d, r8d; pszImplementation
0x1800482ee  lea     rcx, [rbp+0E0h+phAlgorithm]; phAlgorithm
0x1800482f2  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800482f9  nop     dword ptr [rax+rax+00h]
0x1800482fe  mov     edi, eax
0x180048300  test    eax, eax
0x180048302  jns     short loc_180048332
0x180048304  mov     r9d, 1533h
0x18004830a  bts     edi, 1Ch
0x18004830e  mov     ecx, edi
0x180048310  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180048317  lea     rdx, aStatus; "Status"
0x18004831e  call    DebugTraceError
0x180048323  mov     r14d, [rsp+1E0h+cbBuffer]
0x180048328  mov     r15, [rsp+1E0h+pbSecret]
0x18004832d  jmp     loc_180048622
0x180048332  mov     ebx, [rsp+1E0h+cbBuffer]
0x180048336  mov     ecx, ebx
0x180048338  call    SafeAllocaAllocateFromHeap
0x18004833d  mov     [rsp+1E0h+pbSecret], rax
0x180048342  test    rax, rax
0x180048345  jnz     short loc_180048359
0x180048347  mov     edi, 8009000Eh
0x18004834c  mov     r9d, 153Ah
0x180048352  mov     ecx, 8009000Eh
0x180048357  jmp     short loc_180048310
0x180048359  mov     r9d, 2; dwFlags
0x18004835f  mov     r8d, ebx; cbBuffer
0x180048362  mov     rdx, rax; pbBuffer
0x180048365  xor     ecx, ecx; hAlgorithm
0x180048367  call    cs:__imp_BCryptGenRandom
0x18004836e  nop     dword ptr [rax+rax+00h]
0x180048373  mov     edi, eax
0x180048375  xor     eax, eax
0x180048377  test    edi, edi
0x180048379  jns     short loc_180048383
0x18004837b  mov     r9d, 1545h
0x180048381  jmp     short loc_18004830A
0x180048383  mov     rcx, [rbp+0E0h+phAlgorithm]; hAlgorithm
0x180048387  lea     rdx, [rbp+0E0h+phKey]; phKey
0x18004838b  mov     [rsp+1E0h+dwFlags], eax; dwFlags
0x18004838f  xor     r9d, r9d; cbKeyObject
0x180048392  mov     rax, [rsp+1E0h+pbSecret]
0x180048397  xor     r8d, r8d; pbKeyObject
0x18004839a  mov     dword ptr [rsp+1E0h+pcbResult], ebx; cbSecret
0x18004839e  mov     qword ptr [rsp+1E0h+cbOutput], rax; pbSecret
0x1800483a3  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800483aa  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

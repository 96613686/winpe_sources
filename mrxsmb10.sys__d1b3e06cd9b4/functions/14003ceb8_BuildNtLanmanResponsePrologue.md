# BuildNtLanmanResponsePrologue

- ea: `0x14003ceb8`
- end: `0x14003dad7`
- name: `BuildNtLanmanResponsePrologue`
- size: `3103`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140035df8`
- `0x140050ae0`

## callees

- `0x140009e20`
- `0x14000b120`
- `0x14000dc44`
- `0x14000dfd8`
- `0x14000e46c`
- `0x14000e694`
- `0x14000ebd8`
- `0x140011028`
- `0x140016560`
- `0x1400166c0`
- `0x1400169c0`
- `0x14003ce2c`
- `0x14003ceb8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003d110`
- `ntoskrnl!ExAllocatePool2` at `0x14003d14a`
- `ntoskrnl!ExAllocatePool2` at `0x14003d110`
- `ntoskrnl!ExAllocatePool2` at `0x14003d14a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d2df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003da71`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003da8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054559`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054574`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d2df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003da71`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003da8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054559`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054574`
- `ksecdd!InitializeSecurityContextW` at `0x14003d841`
- `ksecdd!InitializeSecurityContextW` at `0x14003d841`
- `ksecdd!AcquireCredentialsHandleW` at `0x14003d29e`
- `ksecdd!AcquireCredentialsHandleW` at `0x14003d29e`
- `ksecdd!MapSecurityError` at `0x14003d884`
- `ksecdd!MapSecurityError` at `0x14003d884`
- `ksecdd!SecMakeSPNEx2` at `0x14003d52c`
- `ksecdd!SecMakeSPNEx2` at `0x14003d5fa`
- `ksecdd!SecMakeSPNEx2` at `0x14003d52c`
- `ksecdd!SecMakeSPNEx2` at `0x14003d5fa`
- `mrxsmb!MRxSmbUseKernelModeSecurity` at `0x14003d253`
- `mrxsmb!MRxSmbUseKernelModeSecurity` at `0x14003d7d5`
- `mrxsmb!MRxSmbUseKernelModeSecurity` at `0x14003d876`

## pseudocode

```c
__int64 __fastcall BuildNtLanmanResponsePrologue(__int64 a1, _OWORD *a2, _OWORD *a3, _WORD *a4, _WORD *a5, char **a6)
{
  __int64 v6; // r12
  char *v7; // r13
  __int64 v8; // rbx
  int v9; // edx
  unsigned int v10; // r9d
  __int64 v11; // r10
  __int64 ExchangeSession; // r15
  _QWORD *v13; // r14
  _QWORD *v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rax
  void *v17; // r8
  USHORT v18; // cx
  int v19; // ecx
  unsigned int v20; // edi
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // rax
  __int64 Pool2; // rsi
  int v25; // ebx
  char *v26; // rax
  char **v27; // rdi
  _WORD *v28; // rax
  char *v29; // rdx
  _WORD *v30; // rax
  _WORD *v31; // rax
  size_t v32; // rbx
  WCHAR *v33; // rcx
  struct _UNICODE_STRING *v34; // rbx
  NTSTATUS SPNEx2; // eax
  int v36; // eax
  NTSTATUS v37; // eax
  unsigned int v38; // r8d
  unsigned int v39; // r9d
  char **v40; // rcx
  unsigned int *v41; // rdx
  int *v42; // r10
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rax
  struct _SecBufferDesc *v46; // rcx
  char *v47; // rdx
  __int64 ExchangeSessionEntry; // rax
  __int64 v49; // r10
  __int64 v50; // rdi
  _WORD *v51; // rcx
  _WORD *v52; // rcx
  _OWORD *v53; // rax
  __int16 v54; // ax
  _OWORD *v55; // rcx
  _OWORD *v56; // rax
  _OWORD *v57; // rcx
  __int64 v58; // rax
  SEC_GET_KEY_FN pGetKeyFn; // [rsp+28h] [rbp-200h]
  int fContextReq; // [rsp+64h] [rbp-1C4h]
  char *v63; // [rsp+80h] [rbp-1A8h]
  int v64; // [rsp+8Ch] [rbp-19Ch]
  ULONG TotalSize; // [rsp+90h] [rbp-198h] BYREF
  unsigned int v66; // [rsp+94h] [rbp-194h]
  int v67; // [rsp+98h] [rbp-190h]
  unsigned int pfContextAttr; // [rsp+9Ch] [rbp-18Ch] BYREF
  char *v69; // [rsp+A0h] [rbp-188h]
  size_t v70; // [rsp+A8h] [rbp-180h]
  struct _UNICODE_STRING v71; // [rsp+B0h] [rbp-178h] BYREF
  struct _SecBufferDesc pInput; // [rsp+C0h] [rbp-168h] BYREF
  PVOID P; // [rsp+D0h] [rbp-158h]
  char *v74; // [rsp+D8h] [rbp-150h]
  _OWORD *v75; // [rsp+E0h] [rbp-148h]
  _OWORD *v76; // [rsp+E8h] [rbp-140h]
  __int64 v77; // [rsp+F0h] [rbp-138h]
  void *Src; // [rsp+F8h] [rbp-130h]
  void *v79; // [rsp+100h] [rbp-128h]
  struct _UNICODE_STRING Spn; // [rsp+108h] [rbp-120h] BYREF
  size_t v81; // [rsp+118h] [rbp-110h]
  __int64 v82; // [rsp+120h] [rbp-108h]
  UNICODE_STRING pPackage; // [rsp+128h] [rbp-100h] BYREF
  struct _UNICODE_STRING ServiceName; // [rsp+140h] [rbp-E8h] BYREF
  SECURITY_INTEGER v85; // [rsp+150h] [rbp-D8h] BYREF
  _WORD *v86; // [rsp+158h] [rbp-D0h]
  _WORD *v87; // [rsp+160h] [rbp-C8h]
  char **v88; // [rsp+168h] [rbp-C0h]
  __int64 v89; // [rsp+170h] [rbp-B8h]
  __int64 v90; // [rsp+178h] [rbp-B0h]
  SECURITY_INTEGER ptsExpiry; // [rsp+180h] [rbp-A8h] BYREF
  __int64 v92; // [rsp+188h] [rbp-A0h]
  size_t Size; // [rsp+190h] [rbp-98h]
  unsigned int v94; // [rsp+1A0h] [rbp-88h] BYREF
  int v95; // [rsp+1A4h] [rbp-84h]
  __int64 v96; // [rsp+1A8h] [rbp-80h]
  unsigned int v97; // [rsp+1B0h] [rbp-78h] BYREF
  int v98; // [rsp+1B4h] [rbp-74h] BYREF
  char *v99; // [rsp+1B8h] [rbp-70h] BYREF
  char v100; // [rsp+1C0h] [rbp-68h] BYREF
  char v101; // [rsp+1C4h] [rbp-64h] BYREF
  char v102; // [rsp+1C8h] [rbp-60h] BYREF

  v86 = a4;
  v75 = a3;
  v76 = a2;
  v6 = a1;
  v87 = a5;
  v89 = a1;
  v88 = a6;
  pfContextAttr = -1073741811;
  v71 = 0;
  ServiceName = 0;
  Spn = 0;
  TotalSize = 0;
  v64 = 0;
  v79 = 0;
  pInput = 0;
  fContextReq = 256;
  v85.QuadPart = 0;
  v77 = 0;
  v63 = 0;
  v7 = 0;
  v70 = 0;
  v92 = *(_QWORD *)(a1 + 80);
  v8 = v92;
  ExchangeSession = SmbCeGetExchangeSession(a1, 256, a6, 0);
  v90 = ExchangeSession;
  v13 = *(_QWORD **)(ExchangeSession + 48);
  *v14 = v11;
  v16 = *(_QWORD *)(v15 + 80);
  v17 = (void *)(*(_QWORD *)(v16 + 88) + 2LL);
  Src = v17;
  v71.Buffer = (PWSTR)v17;
  v18 = *(_WORD *)(v16 + 80) - (v11 + 2);
  v71.Length = v18;
  v71.MaximumLength = *(_WORD *)(v16 + 82) - (v11 + 2);
  if ( *(_WORD *)(v8 + 96) != (_WORD)v11 && *(_QWORD *)(v8 + 104) != v11 )
  {
    ServiceName = v71;
    v10 = v18;
    v64 = v18;
    v71 = *(struct _UNICODE_STRING *)(v8 + 96);
    v79 = v17;
    Src = (void *)_mm_srli_si128((__m128i)v71, 8).m128i_u64[0];
    v18 = _mm_cvtsi128_si32((__m128i)v71);
  }
  Size = v18;
  v81 = v10;
  v19 = v18 + v10 + 56;
  v66 = v19;
  v20 = 24;
  if ( v13 )
  {
    v21 = (unsigned __int16 *)v13[3];
    if ( v21 )
    {
      v20 = *v21 + 24;
      v9 = 384;
      fContextReq = 384;
    }
    v22 = (unsigned __int16 *)v13[2];
    if ( v22 )
    {
      v20 += *v22;
      v9 |= 0x80u;
      fContextReq = v9;
    }
    v23 = (unsigned __int16 *)v13[4];
    if ( v23 )
    {
      v20 += *v23;
      fContextReq = v9 | 0x80;
    }
  }
  v70 = v20 + ((v19 + 3) & 0xFFFFFFFC);
  Pool2 = ExAllocatePool2(258, (unsigned int)v70, 1934454099);
  v77 = Pool2;
  if ( Pool2 && (v26 = (char *)ExAllocatePool2(258, 48, 1934454099), (P = v26) != 0) )
  {
    v74 = v26 + 16;
    *a6 = v26;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids, Pool2);
    v67 = fContextReq & 0x80;
    if ( (fContextReq & 0x80) != 0 )
    {
      v63 = (char *)((Pool2 + v66 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL);
      memset(v63, 0, v20);
      v7 = v63 + 24;
      v69 = v63 + 24;
    }
    if ( *(_QWORD *)(ExchangeSession + 232) == -1 || *(_QWORD *)(ExchangeSession + 240) == -1 )
    {
      *(_DWORD *)(&pPackage.MaximumLength + 1) = 0;
      ptsExpiry.QuadPart = 0;
      pPackage.Buffer = (PWSTR)Pool2;
      *(_DWORD *)&pPackage.Length = 524296;
      *(_QWORD *)Pool2 = 0x4D004C0054004ELL;
      if ( (*(_DWORD *)(ExchangeSession + 8) & 8) != 0 || MRxSmbUseKernelModeSecurity )
        v25 = -1073741822;
      else
        v25 = AcquireCredentialsHandleW(
                0,
                &pPackage,
                2u,
                (void *)(ExchangeSession + 16),
                0,
                0,
                (void *)1,
                (PCredHandle)(ExchangeSession + 232),
                &ptsExpiry);
      if ( v25 < 0 )
      {
        *(_QWORD *)(ExchangeSession + 240) = -1;
        *(_QWORD *)(ExchangeSession + 232) = -1;
        ExFreePoolWithTag(P, 0);
        v27 = a6;
        *a6 = 0;
        v6 = a1;
        goto LABEL_98;
      }
      v8 = v92;
    }
    if ( v13 )
    {
      v28 = (_WORD *)v13[3];
      v29 = v63;
      if ( v28 )
      {
        *(_WORD *)v63 = *v28;
        *((_WORD *)v63 + 1) = *(_WORD *)v13[3];
        memmove(v7, *(const void **)(v13[3] + 8LL), *(unsigned __int16 *)v13[3]);
        v29 = v63;
        *((_DWORD *)v63 + 1) = (_DWORD)v7 - (_DWORD)v63;
        v7 += *(unsigned __int16 *)v13[3];
        v69 = v7;
      }
      v30 = (_WORD *)v13[2];
      if ( v30 )
      {
        *((_WORD *)v29 + 4) = *v30;
        *((_WORD *)v29 + 5) = *(_WORD *)v13[2];
        memmove(v7, *(const void **)(v13[2] + 8LL), *(unsigned __int16 *)v13[2]);
        v29 = v63;
        *((_DWORD *)v63 + 3) = (_DWORD)v7 - (_DWORD)v63;
        v7 += *(unsigned __int16 *)v13[2];
        v69 = v7;
      }
      v31 = (_WORD *)v13[4];
      if ( v31 )
      {
        *((_WORD *)v29 + 8) = *v31;
        *((_WORD *)v29 + 9) = *(_WORD *)v13[4];
        memmove(v7, *(const void **)(v13[4] + 8LL), *(unsigned __int16 *)v13[4]);
        *((_DWORD *)v63 + 5) = (_DWORD)v7 - (_DWORD)v63;
        v69 = &v7[*(unsigned __int16 *)v13[4]];
      }
    }
    *(_QWORD *)Pool2 = 0x5053534D4C544ELL;
    *(_DWORD *)(Pool2 + 8) = 2;
    *(_DWORD *)(Pool2 + 20) = 1048579;
    if ( !*(_DWORD *)(v8 + 432) )
      *(_DWORD *)(Pool2 + 20) = 17825795;
    *(_QWORD *)(Pool2 + 24) = *(_QWORD *)(v8 + 514);
    v32 = Size;
    *(_WORD *)(Pool2 + 14) = Size;
    *(_WORD *)(Pool2 + 12) = v32;
    *(_DWORD *)(Pool2 + 16) = 56;
    memmove((void *)(Pool2 + 56), Src, v32);
    v33 = (WCHAR *)(Pool2 + v32 + 56);
    ServiceName.Buffer = v33;
    if ( v13 )
      v34 = (struct _UNICODE_STRING *)v13[5];
    else
      v34 = 0;
    if ( v64 )
    {
      memmove(v33, v79, v81);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_ZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          (unsigned int)WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids,
          (unsigned int)&ServiceName,
          (__int64)v34);
      }
      SPNEx2 = SecMakeSPNEx2(&CifsServiceName, &ServiceName, 0, 0, 0, v34, &Spn, &TotalSize, 1u, 0);
      if ( SPNEx2 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids,
          (unsigned int)SPNEx2);
      }
      v36 = *(_DWORD *)(Pool2 + 20) | 0x10000;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_ZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          (unsigned int)WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids,
          (unsigned int)&v71,
          (__int64)v34);
      }
      v37 = SecMakeSPNEx2(&CifsServiceName, &v71, 0, 0, 0, v34, &Spn, &TotalSize, 1u, 0);
      if ( v37 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids,
          (unsigned int)v37);
      }
      v36 = *(_DWORD *)(Pool2 + 20) | 0x20000;
    }
    *(_DWORD *)(Pool2 + 20) = v36;
    pInput.pBuffers = (PSecBuffer)&v94;
    pInput.cBuffers = 1;
    pInput.ulVersion = 0;
    v96 = Pool2;
    v94 = v66;
    v95 = 2;
    if ( v67 )
    {
      pInput.cBuffers = 2;
      v99 = v63;
      v97 = v20;
      v98 = 2;
      v38 = 2;
      v39 = 2;
      v40 = (char **)&v102;
      v41 = (unsigned int *)&v100;
      v42 = (int *)&v101;
    }
    else
    {
      v38 = 1;
      v39 = 1;
      v40 = &v99;
      v41 = &v97;
      v42 = &v98;
    }
    v43 = *(_QWORD *)(a1 + 96);
    if ( v43 )
    {
      *v40 = (char *)(v43 + 428);
      *v41 = 28;
      *v42 = 129;
      pInput.cBuffers = ++v38;
      v39 = v38;
    }
    v44 = *(_QWORD *)(a1 + 80);
    v82 = *(_QWORD *)(v44 + 88) + 2LL;
    LOWORD(v81) = *(_WORD *)(v44 + 80) - 2;
    LODWORD(v44) = (unsigned __int16)(*(_WORD *)(v44 + 82) - 2);
    WORD1(v81) = v44;
    *(&v96 + 2 * v38) = v82;
    v45 = 2LL * v39;
    *(&v94 + 2 * v45) = v44;
    *(&v95 + 2 * v45) = 130;
    pInput.cBuffers = v38 + 1;
    v46 = (struct _SecBufferDesc *)P;
    v47 = (char *)P + 16;
    *((_QWORD *)P + 1) = (char *)P + 16;
    v46->cBuffers = 2;
    v46->ulVersion = 0;
    *((_QWORD *)v47 + 1) = 0;
    *(_DWORD *)v47 = 0;
    *((_DWORD *)v47 + 1) = 2;
    *((_QWORD *)v47 + 3) = 0;
    *((_DWORD *)v47 + 4) = 0;
    *((_DWORD *)v47 + 5) = 2;
    if ( (*(_DWORD *)(ExchangeSession + 8) & 8) != 0 || MRxSmbUseKernelModeSecurity )
    {
      v25 = -1073741822;
    }
    else
    {
      v25 = InitializeSecurityContextW(
              (PCredHandle)(ExchangeSession + 232),
              0,
              &Spn,
              fContextReq,
              0,
              0x10u,
              &pInput,
              0,
              (PCtxtHandle)(ExchangeSession + 216),
              v46,
              &pfContextAttr,
              &v85);
      v47 = v74;
    }
    if ( v25 >= 0 )
    {
      v50 = *((_QWORD *)v47 + 1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids, v50);
        v47 = v74;
      }
      if ( v50 )
      {
        v51 = v86;
        if ( v86 )
        {
          *v86 = *(_WORD *)(v50 + 20);
          v51[1] = *(_WORD *)(v50 + 22);
          *((_QWORD *)v51 + 1) = v50 + *(unsigned int *)(v50 + 24);
        }
        v52 = v87;
        if ( v87 )
        {
          *v87 = *(_WORD *)(v50 + 12);
          v52[1] = *(_WORD *)(v50 + 14);
          *((_QWORD *)v52 + 1) = v50 + *(unsigned int *)(v50 + 16);
        }
        if ( v13 && (v53 = (_OWORD *)v13[4]) != 0 )
        {
          *v75 = *v53;
        }
        else
        {
          v54 = *(_WORD *)(v50 + 28);
          v55 = v75;
          *(_WORD *)v75 = v54;
          *((_WORD *)v55 + 1) = v54;
          *((_QWORD *)v55 + 1) = v50 + *(unsigned int *)(v50 + 32);
        }
        if ( v13 && (v56 = (_OWORD *)v13[2]) != 0 )
        {
          *v76 = *v56;
        }
        else
        {
          v57 = v76;
          *(_WORD *)v76 = *(_WORD *)(v50 + 36);
          *((_WORD *)v57 + 1) = *(_WORD *)(v50 + 38);
          *((_QWORD *)v57 + 1) = v50 + *(unsigned int *)(v50 + 40);
        }
        v58 = *((_QWORD *)v47 + 3);
        if ( v58 )
        {
          *(_OWORD *)(ExchangeSession + 60) = *(_OWORD *)v58;
          *(_QWORD *)(ExchangeSession + 204) = *(_QWORD *)(v58 + 16);
        }
      }
      else
      {
        v25 = -1073741823;
      }
      v6 = a1;
    }
    else
    {
      if ( (*(_DWORD *)(ExchangeSession + 8) & 8) != 0 || MRxSmbUseKernelModeSecurity )
        v25 = -1073741822;
      else
        v25 = MapSecurityError(v25);
      if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
      {
        LODWORD(pGetKeyFn) = 13;
        McTemplateK0qqq_EtwWriteTransfer((_DWORD)v46, (unsigned int)SessionSetupError, a1 + 340, v25, 232, pGetKeyFn);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        ExchangeSessionEntry = SmbCeGetExchangeSessionEntry(a1);
        WPP_SF_qD(*(_QWORD *)(v49 + 24), 15, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids, ExchangeSessionEntry, v25);
      }
      v6 = a1;
    }
  }
  else
  {
    v25 = -1073741670;
  }
  v27 = a6;
LABEL_98:
  if ( Pool2 )
  {
    memset((void *)Pool2, 0, v70);
    ExFreePoolWithTag((PVOID)Pool2, 0);
  }
  if ( Spn.Buffer )
    ExFreePoolWithTag(Spn.Buffer, 0);
  if ( v25 >= 0 )
    DeleteSecurityContextForSession(ExchangeSession);
  else
    BuildNtLanmanResponseEpilogue(v6, v27);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x14003ceb8  mov     r11, rsp
0x14003cebb  push    rbx
0x14003cebc  push    rsi
0x14003cebd  push    rdi
0x14003cebe  push    r12
0x14003cec0  push    r13
0x14003cec2  push    r14
0x14003cec4  push    r15
0x14003cec6  sub     rsp, 1F0h
0x14003cecd  mov     rax, cs:__security_cookie
0x14003ced4  xor     rax, rsp
0x14003ced7  mov     [rsp+228h+var_48], rax
0x14003cedf  mov     [rsp+228h+var_D0], r9
0x14003cee7  mov     [rsp+228h+var_148], r8
0x14003ceef  mov     [rsp+228h+var_140], rdx
0x14003cef7  mov     r12, rcx
0x14003cefa  mov     [rsp+228h+var_1B8], rcx
0x14003ceff  mov     rax, [rsp+228h+arg_20]
0x14003cf07  mov     [rsp+228h+var_C8], rax
0x14003cf0f  mov     r8, [rsp+228h+arg_28]
0x14003cf17  mov     [rsp+228h+var_1C0], r8
0x14003cf1c  mov     [rsp+228h+var_B8], rcx
0x14003cf24  mov     [rsp+228h+var_C0], r8
0x14003cf2c  mov     eax, 0C000000Dh
0x14003cf31  mov     [rsp+228h+var_1C8], eax
0x14003cf35  mov     [rsp+228h+var_18C], eax
0x14003cf3c  xorps   xmm0, xmm0
0x14003cf3f  movups  xmmword ptr [rsp+228h+var_178.Length], xmm0
0x14003cf47  xorps   xmm1, xmm1
0x14003cf4a  movups  xmmword ptr [rsp+228h+ServiceName.Length], xmm1
0x14003cf52  movups  xmmword ptr [rsp+228h+Spn.Length], xmm0
0x14003cf5a  xor     r10d, r10d
0x14003cf5d  mov     [r11-198h], r10d
0x14003cf64  mov     r9d, r10d
0x14003cf67  mov     [r11-19Ch], r10d
0x14003cf6e  mov     [r11-128h], r10
0x14003cf75  movups  xmmword ptr [rsp+228h+pInput.ulVersion], xmm0
0x14003cf7d  mov     edx, 100h
0x14003cf82  mov     [rsp+228h+fContextReq], edx
0x14003cf86  mov     [r11-0D8h], r10
0x14003cf8d  mov     [r11-138h], r10
0x14003cf94  mov     [r11-1A8h], r10
0x14003cf9b  mov     r13d, r10d
0x14003cf9e  mov     [r11-180h], r10
0x14003cfa5  mov     rbx, [rcx+50h]
0x14003cfa9  mov     [rsp+228h+var_A0], rbx
0x14003cfb1  call    SmbCeGetExchangeSession
0x14003cfb6  mov     r15, rax
0x14003cfb9  mov     [rsp+228h+var_B0], rax
0x14003cfc1  mov     r14, [rax+30h]
0x14003cfc5  mov     [r8], r10
0x14003cfc8  mov     rax, [rcx+50h]
0x14003cfcc  mov     r8, [rax+58h]
0x14003cfd0  add     r8, 2
0x14003cfd4  mov     [rsp+228h+Src], r8
0x14003cfdc  mov     [rsp+228h+var_178.Buffer], r8
0x14003cfe4  movzx   ecx, word ptr [rax+50h]
0x14003cfe8  lea     r11d, [r10+2]
0x14003cfec  sub     cx, r11w
0x14003cff0  mov     [rsp+228h+var_178.Length], cx
0x14003cff8  movzx   eax, word ptr [rax+52h]
0x14003cffc  sub     ax, r11w
0x14003d000  mov     [rsp+228h+var_178.MaximumLength], ax
0x14003d008  cmp     [rbx+60h], r10w
0x14003d00d  jz      short loc_14003D05C
0x14003d00f  cmp     [rbx+68h], r10
0x14003d013  jz      short loc_14003D05C
0x14003d015  movaps  xmm0, xmmword ptr [rsp+228h+var_178.Length]
0x14003d01d  movdqa  xmmword ptr [rsp+228h+ServiceName.Length], xmm0
0x14003d026  movzx   r9d, cx
0x14003d02a  mov     [rsp+228h+var_19C], r9d
0x14003d032  movups  xmm1, xmmword ptr [rbx+60h]
0x14003d036  movaps  xmmword ptr [rsp+228h+var_178.Length], xmm1
0x14003d03e  mov     [rsp+228h+var_128], r8
0x14003d046  movdqa  xmm0, xmm1
0x14003d04a  psrldq  xmm0, 8
0x14003d04f  movq    [rsp+228h+Src], xmm0
0x14003d058  movd    ecx, xmm1
0x14003d05c  movzx   eax, cx
0x14003d05f  mov     [rsp+228h+Size], rax
0x14003d067  mov     ecx, r9d
0x14003d06a  mov     [rsp+228h+var_110], rcx
0x14003d072  lea     ecx, [r9+38h]
0x14003d076  add     ecx, eax
0x14003d078  mov     [rsp+228h+var_194], ecx
0x14003d07f  mov     edi, 18h
0x14003d084  mov     [rsp+228h+var_1B0], edi
0x14003d088  test    r14, r14
0x14003d08b  jz      short loc_14003D0F3
0x14003d08d  mov     rax, [r14+18h]
0x14003d091  test    rax, rax
0x14003d094  jz      short loc_14003D0B1
0x14003d096  movzx   eax, word ptr [rax]
0x14003d099  add     eax, edi
0x14003d09b  mov     edi, eax
0x14003d09d  mov     [rsp+228h+var_1B0], eax
0x14003d0a1  mov     edx, 180h
0x14003d0a6  mov     [rsp+228h+fContextReq], edx
0x14003d0aa  mov     [rsp+228h+var_1A0], edx
0x14003d0b1  mov     rax, [r14+10h]
0x14003d0b5  test    rax, rax
0x14003d0b8  jz      short loc_14003D0D2
0x14003d0ba  movzx   eax, word ptr [rax]
0x14003d0bd  add     edi, eax
0x14003d0bf  mov     [rsp+228h+var_1B0], edi
0x14003d0c3  bts     edx, 7
0x14003d0c7  mov     [rsp+228h+fContextReq], edx
0x14003d0cb  mov     [rsp+228h+var_1A0], edx
0x14003d0d2  mov     rax, [r14+20h]
0x14003d0d6  test    rax, rax
0x14003d0d9  jz      short loc_14003D0F3
0x14003d0db  movzx   eax, word ptr [rax]
0x14003d0de  add     edi, eax
0x14003d0e0  mov     [rsp+228h+var_1B0], edi
0x14003d0e4  bts     edx, 7
0x14003d0e8  mov     [rsp+228h+fContextReq], edx
0x14003d0ec  mov     [rsp+228h+var_1A0], edx
0x14003d0f3  lea     eax, [rcx+3]
0x14003d0f6  and     eax, 0FFFFFFFCh
0x14003d0f9  add     eax, edi
0x14003d0fb  mov     [rsp+228h+var_180], rax
0x14003d103  mov     r8d, 734D6D53h
0x14003d109  mov     edx, eax
0x14003d10b  mov     ecx, 102h
0x14003d110  call    cs:__imp_ExAllocatePool2
0x14003d117  nop     dword ptr [rax+rax+00h]
0x14003d11c  mov     rsi, rax
0x14003d11f  mov     [rsp+228h+var_138], rax
0x14003d127  test    rax, rax
0x14003d12a  jnz     short loc_14003D13A
0x14003d12c  mov     ebx, 0C000009Ah
0x14003d131  mov     [rsp+228h+var_1C8], ebx
0x14003d135  jmp     loc_14003DA50
0x14003d13a  mov     edx, 30h ; '0'
0x14003d13f  mov     ecx, 102h
0x14003d144  mov     r8d, 734D6D53h
0x14003d14a  call    cs:__imp_ExAllocatePool2
0x14003d151  nop     dword ptr [rax+rax+00h]
0x14003d156  mov     [rsp+228h+P], rax
0x14003d15e  test    rax, rax
0x14003d161  jz      short loc_14003D12C
0x14003d163  lea     rcx, [rax+10h]
0x14003d167  mov     [rsp+228h+var_150], rcx
0x14003d16f  mov     rdx, [rsp+228h+var_1C0]
0x14003d174  mov     [rdx], rax
0x14003d177  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14003d17e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d185  lea     r12, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x14003d18c  cmp     rcx, rax
0x14003d18f  jz      short loc_14003D1AE
0x14003d191  test    dword ptr [rcx+2Ch], 400h
0x14003d198  jz      short loc_14003D1AE
0x14003d19a  mov     edx, 0Ah
0x14003d19f  mov     r9, rsi
0x14003d1a2  mov     r8, r12
0x14003d1a5  mov     rcx, [rcx+18h]
0x14003d1a9  call    WPP_SF_q
0x14003d1ae  mov     eax, [rsp+228h+fContextReq]
0x14003d1b2  and     eax, 80h
0x14003d1b7  mov     [rsp+228h+var_190], eax
0x14003d1be  jz      short loc_14003D1F4
0x14003d1c0  mov     r13d, [rsp+228h+var_194]
0x14003d1c8  add     r13, 3
0x14003d1cc  add     r13, rsi
0x14003d1cf  and     r13, 0FFFFFFFFFFFFFFFCh
0x14003d1d3  mov     [rsp+228h+var_1A8], r13
0x14003d1db  mov     r8d, edi; Size
0x14003d1de  xor     edx, edx; Val
0x14003d1e0  mov     rcx, r13; void *
0x14003d1e3  call    memset
0x14003d1e8  add     r13, 18h
0x14003d1ec  mov     [rsp+228h+var_188], r13
0x14003d1f4  lea     rdx, [r15+0E8h]
0x14003d1fb  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x14003d1ff  jz      short loc_14003D20F
0x14003d201  cmp     qword ptr [r15+0F0h], 0FFFFFFFFFFFFFFFFh
0x14003d209  jnz     loc_14003D308
0x14003d20f  xorps   xmm0, xmm0
0x14003d212  movups  xmmword ptr [rsp+228h+pPackage.Length], xmm0
0x14003d21a  mov     qword ptr [rsp+228h+var_A8], 0
0x14003d226  mov     [rsp+228h+pPackage.Buffer], rsi
0x14003d22e  mov     ecx, 8
0x14003d233  mov     dword ptr [rsp+228h+pPackage.Length], 80008h
0x14003d23e  mov     rax, 4D004C0054004Eh
0x14003d248  mov     [rsi], rax
0x14003d24b  mov     eax, [r15+8]
0x14003d24f  test    cl, al
0x14003d251  jnz     short loc_14003D2B2
0x14003d253  mov     rax, cs:__imp_MRxSmbUseKernelModeSecurity
0x14003d25a  cmp     byte ptr [rax], 0
0x14003d25d  jnz     short loc_14003D2B2
0x14003d25f  lea     r9, [r15+10h]; pvLogonId
0x14003d263  lea     rax, [rsp+228h+var_A8]
0x14003d26b  mov     [rsp+228h+ptsExpiry], rax; ptsExpiry
0x14003d270  mov     [rsp+228h+phCredential], rdx; phCredential
0x14003d275  mov     [rsp+228h+pvGetKeyArgument], 1; pvGetKeyArgument
0x14003d27e  mov     [rsp+228h+pGetKeyFn], 0; pGetKeyFn
0x14003d287  mov     [rsp+228h+pAuthData], 0; pAuthData
0x14003d290  lea     r8d, [rcx-6]; fCredentialUse
0x14003d294  lea     rdx, [rsp+228h+pPackage]; pPackage
0x14003d29c  xor     ecx, ecx; pPrincipal
0x14003d29e  call    cs:__imp_AcquireCredentialsHandleW
0x14003d2a5  nop     dword ptr [rax+rax+00h]
0x14003d2aa  mov     ebx, eax
0x14003d2ac  mov     [rsp+228h+var_1C8], eax
0x14003d2b0  jmp     short loc_14003D2BB
0x14003d2b2  mov     ebx, 0C0000002h
0x14003d2b7  mov     [rsp+228h+var_1C8], ebx
0x14003d2bb  test    ebx, ebx
0x14003d2bd  jns     short loc_14003D300
0x14003d2bf  mov     qword ptr [r15+0F0h], 0FFFFFFFFFFFFFFFFh
0x14003d2ca  mov     qword ptr [r15+0E8h], 0FFFFFFFFFFFFFFFFh
0x14003d2d5  xor     edx, edx; Tag
0x14003d2d7  mov     rcx, [rsp+228h+P]; P
0x14003d2df  call    cs:__imp_ExFreePoolWithTag
0x14003d2e6  nop     dword ptr [rax+rax+00h]
0x14003d2eb  mov     rdi, [rsp+228h+var_1C0]
0x14003d2f0  xor     r13d, r13d
0x14003d2f3  mov     [rdi], r13
0x14003d2f6  mov     r12, [rsp+228h+var_1B8]
0x14003d2fb  jmp     loc_14003DA55
0x14003d300  mov     rbx, [rsp+228h+var_A0]
0x14003d308  test    r14, r14
0x14003d30b  jz      loc_14003D40B
0x14003d311  mov     rax, [r14+18h]
0x14003d315  mov     rdx, [rsp+228h+var_1A8]
0x14003d31d  test    rax, rax
0x14003d320  jz      short loc_14003D369
0x14003d322  movzx   eax, word ptr [rax]
0x14003d325  mov     [rdx], ax
0x14003d328  mov     rax, [r14+18h]
0x14003d32c  movzx   ecx, word ptr [rax]
0x14003d32f  mov     [rdx+2], cx
0x14003d333  mov     rdx, [r14+18h]
0x14003d337  movzx   r8d, word ptr [rdx]; Size
0x14003d33b  mov     rdx, [rdx+8]; Src
0x14003d33f  mov     rcx, r13; void *
0x14003d342  call    memmove
0x14003d347  mov     eax, r13d
0x14003d34a  mov     rdx, [rsp+228h+var_1A8]
0x14003d352  sub     eax, edx
0x14003d354  mov     [rdx+4], eax
0x14003d357  mov     rax, [r14+18h]
0x14003d35b  movzx   ecx, word ptr [rax]
0x14003d35e  add     r13, rcx
0x14003d361  mov     [rsp+228h+var_188], r13
0x14003d369  mov     rax, [r14+10h]
0x14003d36d  test    rax, rax
0x14003d370  jz      short loc_14003D3BA
0x14003d372  movzx   eax, word ptr [rax]
0x14003d375  mov     [rdx+8], ax
0x14003d379  mov     rax, [r14+10h]
0x14003d37d  movzx   ecx, word ptr [rax]
0x14003d380  mov     [rdx+0Ah], cx
0x14003d384  mov     rdx, [r14+10h]
0x14003d388  movzx   r8d, word ptr [rdx]; Size
0x14003d38c  mov     rdx, [rdx+8]; Src
0x14003d390  mov     rcx, r13; void *
0x14003d393  call    memmove
0x14003d398  mov     eax, r13d
0x14003d39b  mov     rdx, [rsp+228h+var_1A8]
0x14003d3a3  sub     eax, edx
0x14003d3a5  mov     [rdx+0Ch], eax
0x14003d3a8  mov     rax, [r14+10h]
0x14003d3ac  movzx   ecx, word ptr [rax]
0x14003d3af  add     r13, rcx
0x14003d3b2  mov     [rsp+228h+var_188], r13
0x14003d3ba  mov     rax, [r14+20h]
0x14003d3be  test    rax, rax
0x14003d3c1  jz      short loc_14003D40B
0x14003d3c3  movzx   eax, word ptr [rax]
0x14003d3c6  mov     [rdx+10h], ax
0x14003d3ca  mov     rax, [r14+20h]
0x14003d3ce  movzx   ecx, word ptr [rax]
0x14003d3d1  mov     [rdx+12h], cx
0x14003d3d5  mov     rdx, [r14+20h]
0x14003d3d9  movzx   r8d, word ptr [rdx]; Size
0x14003d3dd  mov     rdx, [rdx+8]; Src
0x14003d3e1  mov     rcx, r13; void *
0x14003d3e4  call    memmove
0x14003d3e9  mov     eax, r13d
0x14003d3ec  mov     rcx, [rsp+228h+var_1A8]
0x14003d3f4  sub     eax, ecx
0x14003d3f6  mov     [rcx+14h], eax
0x14003d3f9  mov     rax, [r14+20h]
0x14003d3fd  movzx   ecx, word ptr [rax]
0x14003d400  add     r13, rcx
0x14003d403  mov     [rsp+228h+var_188], r13
0x14003d40b  mov     rax, 5053534D4C544Eh
0x14003d415  mov     [rsi], rax
0x14003d418  mov     dword ptr [rsi+8], 2
0x14003d41f  mov     dword ptr [rsi+14h], 100003h
0x14003d426  xor     r13d, r13d
0x14003d429  cmp     [rbx+1B0h], r13d
0x14003d430  jnz     short loc_14003D439
0x14003d432  mov     dword ptr [rsi+14h], 1100003h
0x14003d439  mov     rax, [rbx+202h]
0x14003d440  mov     [rsi+18h], rax
0x14003d444  mov     rbx, [rsp+228h+Size]
0x14003d44c  mov     [rsi+0Eh], bx
  ... truncated ...
```

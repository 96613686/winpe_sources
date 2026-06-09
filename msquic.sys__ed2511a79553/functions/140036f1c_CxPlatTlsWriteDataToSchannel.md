# CxPlatTlsWriteDataToSchannel

- ea: `0x140036f1c`
- end: `0x1400385b9`
- name: `CxPlatTlsWriteDataToSchannel`
- size: `5789`
- prototype: `__int64 __fastcall(char *, __int64, _DWORD *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140035f3c`

## callees

- `0x140008af8`
- `0x14002bbbc`
- `0x1400337e4`
- `0x14003597c`
- `0x140036db8`
- `0x140036f1c`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003ec10`
- `0x14003ed00`
- `0x14003fdf8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400375ef`
- `ntoskrnl!_snprintf_s` at `0x140037b2f`
- `ntoskrnl!_snprintf_s` at `0x140037bfb`
- `ntoskrnl!_snprintf_s` at `0x140037d29`
- `ntoskrnl!_snprintf_s` at `0x140037e16`
- `ntoskrnl!_snprintf_s` at `0x140037fee`
- `ntoskrnl!_snprintf_s` at `0x14003810a`
- `ntoskrnl!_snprintf_s` at `0x1400382ac`
- `ntoskrnl!_snprintf_s` at `0x140038445`
- `ntoskrnl!_snprintf_s` at `0x14003854f`
- `ntoskrnl!_snprintf_s` at `0x1400375ef`
- `ntoskrnl!_snprintf_s` at `0x140037b2f`
- `ntoskrnl!_snprintf_s` at `0x140037bfb`
- `ntoskrnl!_snprintf_s` at `0x140037d29`
- `ntoskrnl!_snprintf_s` at `0x140037e16`
- `ntoskrnl!_snprintf_s` at `0x140037fee`
- `ntoskrnl!_snprintf_s` at `0x14003810a`
- `ntoskrnl!_snprintf_s` at `0x1400382ac`
- `ntoskrnl!_snprintf_s` at `0x140038445`
- `ntoskrnl!_snprintf_s` at `0x14003854f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003775e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400377aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400382e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038501`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038580`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003775e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400377aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400382e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038501`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038580`
- `ntoskrnl!PsRevertToSelf` at `0x140037474`
- `ntoskrnl!PsRevertToSelf` at `0x140037474`
- `ntoskrnl!PsImpersonateClient` at `0x14003736a`
- `ntoskrnl!PsImpersonateClient` at `0x14003736a`
- `ntoskrnl!ExAllocatePool2` at `0x140038308`
- `ntoskrnl!ExAllocatePool2` at `0x1400384b3`
- `ntoskrnl!ExAllocatePool2` at `0x140038308`
- `ntoskrnl!ExAllocatePool2` at `0x1400384b3`
- `ksecdd!QueryContextAttributesW` at `0x1400377ec`
- `ksecdd!QueryContextAttributesW` at `0x1400378b9`
- `ksecdd!QueryContextAttributesW` at `0x140037939`
- `ksecdd!QueryContextAttributesW` at `0x140037962`
- `ksecdd!QueryContextAttributesW` at `0x140037a63`
- `ksecdd!QueryContextAttributesW` at `0x1400377ec`
- `ksecdd!QueryContextAttributesW` at `0x1400378b9`
- `ksecdd!QueryContextAttributesW` at `0x140037939`
- `ksecdd!QueryContextAttributesW` at `0x140037962`
- `ksecdd!QueryContextAttributesW` at `0x140037a63`
- `ksecdd!InitializeSecurityContextW` at `0x140037457`
- `ksecdd!InitializeSecurityContextW` at `0x140037457`
- `ksecdd!AcceptSecurityContext` at `0x1400373f2`
- `ksecdd!AcceptSecurityContext` at `0x1400373f2`
- `ksecdd!FreeContextBuffer` at `0x1400379d3`
- `ksecdd!FreeContextBuffer` at `0x1400379d3`

## string_xrefs

- `0x14003738a`: `PsImpersonateClient failed`
- `0x1400375c6`: `Key Ready Type, %u [%hu to %hu]`
- `0x140037b11`: `Handshake complete (resume=%hu)`
- `0x140037d14`: `Reading Handshake data starts now`
- `0x140037e01`: `Reading 1-RTT data starts now`
- `0x1400381e6`: `OutputTokenBuffer->cbBuffer <= 0xFFFF`
- `0x14003832f`: `Temporary Peer Transport Params`
- `0x140038403`: `Accept/InitializeSecurityContext`

## pseudocode

```c
__int64 __fastcall CxPlatTlsWriteDataToSchannel(char *a1, __int64 a2, _DWORD *a3, unsigned __int8 *a4)
{
  unsigned __int8 *v4; // r15
  _DWORD *v5; // r13
  char *v6; // rdi
  __int64 cBuffers; // rax
  const CHAR *v10; // rcx
  int v11; // eax
  __int64 v13; // rax
  __int64 v14; // rcx
  char v15; // al
  unsigned int v16; // ecx
  __int64 v17; // rax
  unsigned int v18; // ecx
  char v19; // dl
  char *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // edi
  void *v24; // rdx
  struct _KTHREAD *CurrentThread; // rcx
  NTSTATUS v26; // eax
  int v27; // ecx
  __int64 v28; // rdx
  struct _SecHandle *v29; // rdx
  SECURITY_STATUS v30; // eax
  struct _SecHandle *v31; // rdx
  unsigned int v32; // edi
  PSecBuffer v33; // r9
  _DWORD *p_cbBuffer; // r8
  PSecBuffer pBuffers; // rax
  __int64 v36; // rdx
  unsigned int v37; // r10d
  __int64 v38; // rcx
  PSecBuffer v39; // rdx
  struct _SecBuffer *v40; // rax
  struct _SecBuffer *v41; // r9
  unsigned int v42; // r11d
  unsigned __int8 v43; // r13
  UNICODE_STRING *v44; // r15
  unsigned __int8 v45; // r12
  struct _SecBuffer *v46; // r8
  PSECURITY_STRING pvBuffer; // rcx
  int Buffer; // r8d
  __int64 v49; // rcx
  int v50; // r8d
  __int64 v51; // rax
  __int64 v52; // rax
  const char *v53; // r9
  void *v54; // rcx
  void *v55; // rcx
  SECURITY_STATUS ContextAttributesW; // eax
  int v57; // ecx
  const char *v58; // rcx
  unsigned __int8 *v59; // rax
  struct _SecHandle *v60; // rcx
  __int64 v61; // rax
  SECURITY_STATUS v62; // edx
  int v63; // ecx
  int v64; // ecx
  SECURITY_STATUS v65; // edx
  int v66; // ecx
  int v67; // ecx
  __int64 v68; // rcx
  SECURITY_STATUS v69; // r9d
  const char *v70; // rax
  _DWORD *v71; // rcx
  __int64 v72; // rcx
  unsigned __int8 v73; // al
  __int64 v74; // r13
  _BYTE *v75; // rcx
  int v76; // eax
  __int64 v77; // rcx
  _BYTE *v78; // rcx
  const void *v79; // rdx
  __int64 v80; // rcx
  size_t v81; // r8
  __int64 v82; // rcx
  _BYTE *v83; // rcx
  const void *v84; // rdx
  __int64 v85; // rcx
  size_t v86; // r8
  unsigned __int8 v87; // al
  char *v88; // r13
  _BYTE *v89; // rcx
  int v90; // eax
  int v91; // ecx
  int v92; // edx
  int v93; // eax
  __int64 v94; // rcx
  _BYTE *v95; // rcx
  const void *v96; // rdx
  __int64 v97; // rcx
  size_t v98; // r8
  __int64 v99; // rcx
  _BYTE *v100; // rcx
  const void *v101; // rdx
  __int64 v102; // rcx
  size_t v103; // r8
  PSECURITY_STRING v104; // r14
  __int64 v105; // rcx
  unsigned int v106; // r13d
  _DWORD *v107; // rax
  __int64 v108; // rcx
  void *v109; // rcx
  __int64 v110; // rax
  __int64 v111; // rdx
  int v112; // ecx
  __int64 v113; // rcx
  unsigned __int16 v114; // ax
  unsigned __int16 v115; // di
  __int64 v116; // rdx
  __int64 v117; // rcx
  void *Pool2; // rbx
  SECURITY_IMPERSONATION_LEVEL ImpersonationLevel[2]; // [rsp+20h] [rbp-E0h]
  char v120; // [rsp+60h] [rbp-A0h]
  unsigned __int8 i; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v122; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v123; // [rsp+61h] [rbp-9Fh]
  unsigned __int8 v124; // [rsp+62h] [rbp-9Eh]
  SECURITY_STATUS v125; // [rsp+64h] [rbp-9Ch]
  struct _SecBufferDesc pInput; // [rsp+68h] [rbp-98h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+78h] [rbp-88h] BYREF
  struct _SecBuffer *v128; // [rsp+88h] [rbp-78h]
  unsigned __int8 *v129; // [rsp+90h] [rbp-70h] BYREF
  PSECURITY_STRING pTargetName; // [rsp+98h] [rbp-68h]
  _DWORD *v131; // [rsp+A0h] [rbp-60h]
  unsigned int pfContextAttr; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v133; // [rsp+ACh] [rbp-54h]
  char v134; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v135; // [rsp+B4h] [rbp-4Ch]
  __int128 v136; // [rsp+B8h] [rbp-48h] BYREF
  PVOID pvContextBuffer; // [rsp+C8h] [rbp-38h]
  struct _SecBuffer *v138; // [rsp+D0h] [rbp-30h]
  _DWORD *v139; // [rsp+D8h] [rbp-28h]
  _DWORD *v140; // [rsp+E0h] [rbp-20h]
  __int128 v141; // [rsp+E8h] [rbp-18h]
  __int128 v142; // [rsp+F8h] [rbp-8h]
  PVOID P[2]; // [rsp+108h] [rbp+8h] BYREF
  _DWORD pBuffer[68]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v145; // [rsp+230h] [rbp+130h] BYREF
  int v146; // [rsp+238h] [rbp+138h]
  _OWORD v147[2]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v148; // [rsp+260h] [rbp+160h]
  char DstBuf[128]; // [rsp+270h] [rbp+170h] BYREF

  v4 = a4;
  v129 = a4;
  v131 = a3;
  v5 = a1 + 1944;
  v6 = a1 + 2056;
  cBuffers = 0;
  pTargetName = 0;
  pInput.ulVersion = 0;
  *(_OWORD *)P = 0;
  pInput.pBuffers = (PSecBuffer)(a1 + 1944);
  pInput.cBuffers = 0;
  *(_QWORD *)&pOutput.ulVersion = 0;
  pOutput.pBuffers = (PSecBuffer)(a1 + 2056);
  if ( *a3 )
  {
    *((_DWORD *)a1 + 487) = 2;
    *v5 = *a3;
    *((_QWORD *)a1 + 244) = a2;
    pInput.cBuffers = 1;
    v13 = 1;
  }
  else
  {
    v10 = (const CHAR *)*((_QWORD *)a1 + 1);
    if ( v10 )
    {
      pTargetName = (PSECURITY_STRING)P;
      v11 = CxPlatTlsUtf8ToUnicodeString(v10);
      if ( v11 < 0 )
      {
        if ( byte_14005C48D < 0 )
          McTemplateU0pqs_EtwWriteTransfer(
            (unsigned int)"Convert SNI to unicode",
            (unsigned int)QuicTlsErrorStatus,
            *((_QWORD *)a1 + 9),
            v11,
            (__int64)"Convert SNI to unicode");
        return 0x8000;
      }
      cBuffers = pInput.cBuffers;
      a3 = v131;
    }
    v5[4 * cBuffers + 1] = 18;
    v5[4 * pInput.cBuffers] = *((_DWORD *)a1 + 14);
    *(_QWORD *)&v5[4 * pInput.cBuffers + 2] = *((_QWORD *)a1 + 6);
    v13 = ++pInput.cBuffers;
  }
  v14 = 2;
  do
  {
    v5[4 * v13 + 1] = 0;
    v5[4 * pInput.cBuffers] = 0;
    *(_QWORD *)&v5[4 * pInput.cBuffers + 2] = 0;
    v13 = ++pInput.cBuffers;
    --v14;
  }
  while ( v14 );
  *((_QWORD *)a1 + 10) = 0x100000000LL;
  v5[4 * v13 + 1] = 27;
  v5[4 * pInput.cBuffers] = 8;
  *(_QWORD *)&v5[4 * pInput.cBuffers + 2] = a1 + 80;
  v15 = *a1;
  v16 = ++pInput.cBuffers;
  if ( (v15 & 1) != 0 && (v15 & 2) == 0 )
  {
    v5[4 * v16 + 1] = 18;
    v5[4 * pInput.cBuffers] = *((_DWORD *)a1 + 14);
    *(_QWORD *)&v5[4 * pInput.cBuffers++ + 2] = *((_QWORD *)a1 + 6);
  }
  *(_DWORD *)&v6[16 * pOutput.cBuffers + 4] = 2;
  *(_DWORD *)&v6[16 * pOutput.cBuffers] = *((unsigned __int16 *)v4 + 10) - *((unsigned __int16 *)v4 + 9);
  *(_QWORD *)&v6[16 * pOutput.cBuffers++ + 8] = *((_QWORD *)v4 + 5) + *((unsigned __int16 *)v4 + 9);
  *(_DWORD *)&v6[16 * pOutput.cBuffers + 4] = 17;
  *(_DWORD *)&v6[16 * pOutput.cBuffers] = 2;
  *(_QWORD *)&v6[16 * pOutput.cBuffers + 8] = &v134;
  v17 = ++pOutput.cBuffers;
  if ( *((_QWORD *)a1 + 8) )
  {
    v5[4 * pInput.cBuffers + 1] = 25;
    v5[4 * pInput.cBuffers] = *(unsigned __int16 *)(*((_QWORD *)a1 + 8) + 8LL) + 10;
    *(_QWORD *)&v5[4 * pInput.cBuffers + 2] = *((_QWORD *)a1 + 8);
    v17 = pOutput.cBuffers;
    v18 = ++pInput.cBuffers;
  }
  else
  {
    v18 = pInput.cBuffers;
  }
  v145 = 0;
  v146 = 0;
  if ( *a3 )
  {
    v19 = *a1;
    if ( (*a1 & 5) == 0 )
    {
      LOWORD(v146) = *((_WORD *)a1 + 1);
      HIDWORD(v145) = 1;
      HIWORD(v146) = (v19 & 1) != 0 ? 1 : 8;
      v5[4 * v18 + 1] = 26;
      v5[4 * pInput.cBuffers] = 12;
      *(_QWORD *)&v5[4 * pInput.cBuffers++ + 2] = &v145;
      *(_DWORD *)&v6[16 * pOutput.cBuffers + 4] = 26;
      if ( *((_QWORD *)a1 + 272) )
      {
        *(_DWORD *)&v6[16 * pOutput.cBuffers] = *((_DWORD *)a1 + 542);
        *(_QWORD *)&v6[16 * pOutput.cBuffers + 8] = *((_QWORD *)a1 + 272);
      }
      else
      {
        *(_DWORD *)&v6[16 * pOutput.cBuffers] = *a3;
        *(_QWORD *)&v6[16 * pOutput.cBuffers + 8] = a2;
      }
      v17 = ++pOutput.cBuffers;
    }
  }
  v20 = a1 + 88;
  v21 = 4;
  do
  {
    *(_DWORD *)&v6[16 * v17 + 4] = 28;
    *(_DWORD *)&v6[16 * pOutput.cBuffers] = 464;
    *(_QWORD *)&v6[16 * pOutput.cBuffers + 8] = v20;
    v20 += 464;
    v17 = ++pOutput.cBuffers;
    --v21;
  }
  while ( v21 );
  v22 = *((_QWORD *)a1 + 4);
  if ( (*a1 & 1) != 0 )
  {
    v23 = (*(_DWORD *)(v22 + 16) & 0x40 | 0x300B00u) >> 5;
  }
  else
  {
    v23 = 49176;
    if ( (*(_DWORD *)(v22 + 16) & 0x8000) != 0 )
      v23 = 49304;
  }
  pfContextAttr = 0;
  v24 = *(void **)(v22 + 48);
  if ( v24 )
  {
    CurrentThread = KeGetCurrentThread();
    v26 = *(_BYTE *)(v22 + 56)
        ? PsImpersonateClient(CurrentThread, v24, 0, 0, SecurityImpersonation)
        : PsImpersonateClient(
            CurrentThread,
            v24,
            *(_BYTE *)(v22 + 57),
            *(_BYTE *)(v22 + 58),
            *(SECURITY_IMPERSONATION_LEVEL *)(v22 + 60));
    if ( v26 < 0 && byte_14005C48D < 0 )
      McTemplateU0pqs_EtwWriteTransfer(
        v27,
        (unsigned int)QuicTlsErrorStatus,
        *((_QWORD *)a1 + 9),
        v26,
        (__int64)"PsImpersonateClient failed");
  }
  v28 = *((_QWORD *)a1 + 2);
  if ( (*a1 & 1) != 0 )
  {
    if ( v28 == -1 || (v29 = (struct _SecHandle *)(a1 + 16), *((_QWORD *)a1 + 3) == -1) )
      v29 = 0;
    v30 = AcceptSecurityContext(
            *((PCredHandle *)a1 + 4),
            v29,
            &pInput,
            v23,
            0,
            (PCtxtHandle)a1 + 1,
            &pOutput,
            &pfContextAttr,
            0);
  }
  else
  {
    if ( v28 == -1 || (v31 = (struct _SecHandle *)(a1 + 16), *((_QWORD *)a1 + 3) == -1) )
      v31 = 0;
    v30 = InitializeSecurityContextW(
            *((PCredHandle *)a1 + 4),
            v31,
            pTargetName,
            v23,
            0,
            0x10u,
            &pInput,
            0,
            (PCtxtHandle)a1 + 1,
            &pOutput,
            &pfContextAttr,
            0);
  }
  v125 = v30;
  if ( *(_QWORD *)(*((_QWORD *)a1 + 4) + 48LL) )
    PsRevertToSelf();
  v32 = 0;
  v135 = 0;
  v33 = 0;
  v140 = 0;
  p_cbBuffer = 0;
  v139 = 0;
  if ( pInput.cBuffers )
  {
    pBuffers = pInput.pBuffers;
    v36 = pInput.cBuffers;
    do
    {
      if ( v33 || pBuffers->BufferType != 5 )
      {
        if ( !p_cbBuffer && pBuffers->BufferType == 4 )
          p_cbBuffer = &pBuffers->cbBuffer;
      }
      else
      {
        v33 = pBuffers;
      }
      ++pBuffers;
      --v36;
    }
    while ( v36 );
    v140 = &v33->cbBuffer;
    v139 = p_cbBuffer;
  }
  v37 = pOutput.cBuffers;
  v38 = 0;
  v39 = pOutput.pBuffers;
  pTargetName = 0;
  v128 = 0;
  v40 = 0;
  v138 = 0;
  v41 = 0;
  v123 = 0;
  v42 = 0;
  v124 = 0;
  v133 = 0;
  v141 = 0;
  v142 = 0;
  if ( pOutput.cBuffers )
  {
    v43 = 0;
    v44 = 0;
    v45 = 0;
    while ( 1 )
    {
      if ( v44 || (v40 = v128, v39[v42].BufferType != 2) )
      {
        if ( v40 || (v46 = &v39[v42], v46->BufferType != 17) || !v46->cbBuffer )
        {
          if ( !v41 && v39[v42].BufferType == 26 )
          {
            v41 = &v39[v42];
            v138 = v41;
LABEL_79:
            v40 = v128;
            goto LABEL_80;
          }
          if ( v39[v42].BufferType != 28 )
            goto LABEL_79;
          pvBuffer = (PSECURITY_STRING)v39[v42].pvBuffer;
          pTargetName = pvBuffer;
          Buffer = (int)pvBuffer[24].Buffer;
          if ( !Buffer )
            goto LABEL_79;
          if ( (byte_14005C48C & 1) != 0 )
          {
            _snprintf_s(
              DstBuf,
              0x80u,
              0xFFFFFFFFFFFFFFFFuLL,
              "Key Ready Type, %u [%hu to %hu]",
              Buffer,
              *(&pvBuffer[24].MaximumLength + 1),
              *(&pvBuffer[24].MaximumLength + 2));
            McTemplateU0ps_EtwWriteTransfer(v49, QuicConnLogVerbose, *((_QWORD *)a1 + 9), DstBuf);
            v39 = pOutput.pBuffers;
            v37 = pOutput.cBuffers;
            pvBuffer = pTargetName;
            v41 = v138;
            v42 = v133;
          }
          v50 = (int)pvBuffer[24].Buffer;
          if ( (*a1 & 1) != 0 )
          {
            if ( v50 != 2 )
            {
LABEL_76:
              v51 = v43++;
              *((_QWORD *)&v141 + v51) = pvBuffer;
              goto LABEL_79;
            }
          }
          else if ( v50 == 2 )
          {
            goto LABEL_76;
          }
          v52 = v45++;
          P[v52 - 2] = pvBuffer;
          goto LABEL_79;
        }
        v40 = &v39[v42];
        v128 = v40;
      }
      else
      {
        v44 = (UNICODE_STRING *)&v39[v42];
      }
LABEL_80:
      v133 = ++v42;
      if ( v42 >= v37 )
      {
        v32 = v135;
        v38 = 0;
        p_cbBuffer = v139;
        v124 = v45;
        pTargetName = v44;
        v4 = v129;
        v123 = v43;
        v5 = a1 + 1944;
        break;
      }
    }
  }
  if ( v125 != -2146893032 )
  {
    if ( v125 == -2146893023 )
    {
      if ( byte_14005C48B < 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Increasing TLS output buffer size");
        McTemplateU0ps_EtwWriteTransfer(v113, QuicConnLogInfo, *((_QWORD *)a1 + 9), DstBuf);
      }
      v114 = *((_WORD *)v4 + 10);
      v115 = 2 * v114;
      if ( (unsigned __int16)(2 * v114) >= v114 )
      {
        Pool2 = (void *)ExAllocatePool2(66, v115, 959669073);
        if ( Pool2 )
        {
          if ( *((_WORD *)v4 + 9) )
            memmove(Pool2, *((const void **)v4 + 5), *((unsigned __int16 *)v4 + 9));
          ExFreePoolWithTag(*((PVOID *)v4 + 5), 0x39336351u);
          *((_WORD *)v4 + 10) = v115;
          v32 = 1;
          *((_QWORD *)v4 + 5) = Pool2;
          goto LABEL_280;
        }
        if ( (Microsoft_QuicEnableBits & 2) != 0 )
          McTemplateU0sx_EtwWriteTransfer(v117, v116, "New TLS RX Buffer", v115);
      }
      else if ( byte_14005C48D < 0 )
      {
        v53 = "TLS buffer too large";
        goto LABEL_267;
      }
      goto LABEL_268;
    }
    if ( v125 == -2146892950 )
    {
      if ( *v131 && (*a1 & 5) == 0 )
      {
        v106 = 0;
        if ( v37 )
        {
          while ( v39[v106].BufferType != 26 )
          {
            if ( ++v106 >= v37 )
              goto LABEL_246;
          }
          if ( byte_14005C48B < 0 )
          {
            v107 = a1 + 2168;
            if ( !*((_QWORD *)a1 + 272) )
              v107 = v131;
            _snprintf_s(
              DstBuf,
              0x80u,
              0xFFFFFFFFFFFFFFFFuLL,
              "Peer TP too large for available buffer (%u vs. %u)",
              v39[v106].cbBuffer,
              *v107);
            McTemplateU0ps_EtwWriteTransfer(v108, QuicConnLogInfo, *((_QWORD *)a1 + 9), DstBuf);
            v39 = pOutput.pBuffers;
          }
          v109 = (void *)*((_QWORD *)a1 + 272);
          if ( v109 )
          {
            ExFreePoolWithTag(v109, 0x34346351u);
            v39 = pOutput.pBuffers;
          }
          v110 = ExAllocatePool2(66, v39[v106].cbBuffer, 875848529);
          LODWORD(v38) = 0;
          *((_QWORD *)a1 + 272) = v110;
          if ( v110 )
          {
            v32 = 1;
            *((_DWORD *)a1 + 542) = pOutput.pBuffers[v106].cbBuffer;
LABEL_246:
            LODWORD(v38) = 0;
          }
          else
          {
            if ( (Microsoft_QuicEnableBits & 2) != 0 )
            {
              McTemplateU0sx_EtwWriteTransfer(
                2LL * v106,
                v111,
                "Temporary Peer Transport Params",
                pOutput.pBuffers[v106].cbBuffer);
              LODWORD(v38) = 0;
            }
            v32 = 0x8000;
          }
        }
        if ( *((_QWORD *)a1 + 272) )
          goto LABEL_280;
      }
LABEL_248:
      if ( !v128 )
        goto LABEL_255;
      if ( v128->cbBuffer >= 2 )
      {
        v112 = *((unsigned __int8 *)v128->pvBuffer + 1);
        *((_WORD *)v4 + 8) = v112;
        if ( byte_14005C48D < 0 )
          McTemplateU0pqs_EtwWriteTransfer(
            v112,
            (unsigned int)QuicTlsErrorStatus,
            *((_QWORD *)a1 + 9),
            v112,
            (__int64)"TLS alert message received");
      }
      else
      {
        if ( (byte_14005C48D & 0x80) == 0 )
          goto LABEL_255;
        McTemplateU0ps_EtwWriteTransfer(0, QuicTlsError, *((_QWORD *)a1 + 9), "TLS alert message received (invalid)");
      }
      LODWORD(v38) = 0;
LABEL_255:
      v69 = v125;
      if ( v125 == 590624 && !*((_WORD *)v4 + 8) )
        *((_WORD *)v4 + 8) = 116;
      *v131 = 0;
      if ( (byte_14005C48D & 0x80) == 0 )
        goto LABEL_261;
      v70 = "Accept/InitializeSecurityContext";
      goto LABEL_260;
    }
    if ( v125 )
    {
      if ( v125 == 590610 )
        goto LABEL_156;
      if ( v125 != 590614 )
      {
        if ( v125 != 590694 )
          goto LABEL_248;
LABEL_156:
        if ( !v128 )
        {
          if ( v140 )
          {
            v71 = v131;
            if ( *v140 )
              *v131 -= v5[4];
          }
          else
          {
            v71 = v131;
          }
          if ( byte_14005C48B < 0 )
          {
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Consumed %u bytes", *v71);
            McTemplateU0ps_EtwWriteTransfer(v72, QuicConnLogInfo, *((_QWORD *)a1 + 9), DstBuf);
          }
          v73 = 0;
          for ( i = 0; v73 < v123; i = v73 )
          {
            v32 |= 4u;
            v74 = *((_QWORD *)&v141 + v73);
            if ( *(_DWORD *)(v74 + 392) == 3 )
            {
              CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\platform\\tls_schannel.c", 2460, "0");
              __int2c();
              if ( (*a1 & 1) == 0 )
              {
                CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\platform\\tls_schannel.c", 2461, "TlsContext->IsServer");
                __int2c();
              }
              v75 = (_BYTE *)*((_QWORD *)a1 + 273);
              if ( v75 )
              {
                *v75 = *(_BYTE *)(v74 + 396);
                memmove(
                  (void *)(*((_QWORD *)a1 + 273) + 34LL),
                  (const void *)(v74 + 398),
                  *(unsigned __int16 *)(v74 + 396));
                *(_BYTE *)(*((_QWORD *)a1 + 273) + 1LL) |= 2u;
              }
            }
            else
            {
              v76 = *((_DWORD *)v4 + 2);
              if ( v76 )
              {
                if ( v76 == 2 )
                {
                  if ( !(unsigned __int8)QuicPacketKeyCreate((_DWORD)a1, 3, (_DWORD)p_cbBuffer, v74, (__int64)(v4 + 96)) )
                  {
LABEL_192:
                    v32 |= 0x8000u;
                    break;
                  }
                  *((_DWORD *)v4 + 2) = 3;
                  if ( byte_14005C48B < 0 )
                  {
                    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Reading 1-RTT data starts now");
                    McTemplateU0ps_EtwWriteTransfer(v82, QuicConnLogInfo, *((_QWORD *)a1 + 9), DstBuf);
                  }
                  v83 = (_BYTE *)*((_QWORD *)a1 + 273);
                  if ( v83 )
                  {
                    v84 = (const void *)(v74 + 398);
                    *v83 = *(_BYTE *)(v74 + 396);
                    v85 = *((_QWORD *)a1 + 273);
                    v86 = *(unsigned __int16 *)(v74 + 396);
                    if ( (*a1 & 1) != 0 )
                    {
                      memmove((void *)(v85 + 226), v84, v86);
                      *(_BYTE *)(*((_QWORD *)a1 + 273) + 1LL) |= 0x10u;
                    }
                    else
                    {
                      memmove((void *)(v85 + 290), v84, v86);
                      *(_BYTE *)(*((_QWORD *)a1 + 273) + 1LL) |= 0x20u;
                    }
                  }
                }
              }
              else
              {
                if ( !(unsigned __int8)QuicPacketKeyCreate((_DWORD)a1, 2, (_DWORD)p_cbBuffer, v74, (__int64)(v4 + 88)) )
                  goto LABEL_192;
                *((_DWORD *)v4 + 2) = 2;
                if ( byte_14005C48B < 0 )
                {
                  _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Reading Handshake data starts now");
                  McTemplateU0ps_EtwWriteTransfer(v77, QuicConnLogInfo, *((_QWORD *)a1 + 9), DstBuf);
                }
                v78 = (_BYTE *)*((_QWORD *)a1 + 273);
                if ( v78 )
                {
                  v79 = (const void *)(v74 + 398);
                  *v78 = *(_BYTE *)(v74 + 396);
                  v80 = *((_QWORD *)a1 + 273);
                  v81 = *(unsigned __int16 *)(v74 + 396);
                  if ( (*a1 & 1) != 0 )
                  {
                    memmove((void *)(v80 + 98), v79, v81);
                    *(_BYTE *)(*((_QWORD *)a1 + 273) + 1LL) |= 4u;
                  }
                  else
                  {
                    memmove((void *)(v80 + 162), v79, v81);
                    *(_BYTE *)(*((_QWORD *)a1 + 273) + 1LL) |= 8u;
                  }
                }
              }
            }
            v73 = i + 1;
          }
          v87 = 0;
          v122 = 0;
          if ( !v124 )
            goto LABEL_221;
          while ( 1 )
          {
            v32 |= 8u;
            v88 = (char *)P[v87 - 2];
            if ( *((_DWORD *)v88 + 98) == 3 )
            {
              CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\platform\\tls_schannel.c", 2543, "0");
              __int2c();
              if ( (*a1 & 1) != 0 )
              {
                CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\platform\\tls_schannel.c", 2544, "!TlsContext->IsServer");
                __int2c();
              }
              v89 = (_BYTE *)*((_QWORD *)a1 + 273);
              if ( v89 )
              {
                *v89 = v88[396];
                memmove((void *)(*((_QWORD *)a1 + 273) + 34LL), v88 + 398, *((unsigned __int16 *)v88 + 198));
                *(_BYTE *)(*((_QWORD *)a1 + 273) + 1LL) |= 2u;
              }
            }
            else
            {
              v90 = *((_DWORD *)v4 + 3);
              if ( v90 )
              {
                if ( v90 == 2 )
                {
                  if ( (*a1 & 1) != 0 || *((_DWORD *)v4 + 7) != *((_DWORD *)v4 + 8) )
                  {
                    if ( !(unsigned __int8)QuicPacketKeyCreate(
                                             (_DWORD)a1,
                                             3,
                                             (_DWORD)p_cbBuffer,
                                             (_DWORD)v88,
                                             (__int64)(v4 + 144)) )
                    {
LABEL_220:
                      v32 |= 0x8000u;
LABEL_221:
                      if ( !v125 )
                        *((_QWORD *)a1 + 273) = 0;
                      v104 = pTargetName;
                      if ( pTargetName && *(_DWORD *)&pTargetName->Length )
                      {
                        *a1 |= 2u;
                        v32 |= 2u;
                        if ( *(_DWORD *)&v104->Length > 0xFFFFu )
                        {
                          CxPlatLogAssert(
                            "C:\\__w\\1\\s\\msquic\\src\\platform\\tls_schannel.c",
                            2647,
                            "OutputTokenBuffer->cbBuffer <= 0xFFFF");
                          __int2c();
                        }
                        *((_WORD *)v4 + 9) += v104->Length;
                        *((_DWORD *)v4 + 6) += *(_DWORD *)&v104->Length;
                        if ( byte_14005C48B < 0 )
                        {
                          ImpersonationLevel[0] = *(SECURITY_IMPERSONATION_LEVEL *)&v104->Length;
                          _snprintf_s(
                            DstBuf,
                            0x80u,
                            0xFFFFFFFFFFFFFFFFuLL,
                            "Produced %u bytes",
                            *(_QWORD *)ImpersonationLevel);
                          goto LABEL_279;
                        }
                      }
                      goto LABEL_280;
                    }
                    *((_DWORD *)v4 + 3) = 3;
                    if ( byte_14005C48B < 0 )
                    {
                      _snprintf_s(
                        DstBuf,
                        0x80u,
                        0xFFFFFFFFFFFFFFFFuLL,
                        "Writing 1-RTT data starts at %u",
                        *((_DWORD *)v4 + 8));
                      McTemplateU0ps_EtwWriteTransfer(v99, QuicConnLogInfo, *((_QWORD *)a1 + 9), DstBuf);
                    }
                    v100 = (_BYTE *)*((_QWORD *)a1 + 273);
                    if ( v100 )
                    {
                      v101 = v88 + 398;
                      *v100 = v88[396];
                      v102 = *((_QWORD *)a1 + 273);
                      v103 = *((unsigned __int16 *)v88 + 198);
                      if ( (*a1 & 1) != 0 )
                      {
                        memmove((void *)(v102 + 290), v101, v103);
                        *(_BYTE *)(*((_QWORD *)a1 + 273) + 1LL) |= 0x20u;
                      }
                      else
                      {
                        memmove((void *)(v102 + 226), v101, v103);
                        *(_BYTE *)(*((_QWORD *)a1 + 273) + 1LL) |= 0x10u;
                      }
                    }
                  }
                  else
                  {
                    *((_DWORD *)v4 + 8) = *((_DWORD *)v4 + 6) + *((unsigned __int16 *)v88 + 195);
                  }
                }
              }
              else
              {
                if ( !(unsigned __int8)QuicPacketKeyCreate(
                                         (_DWORD)a1,
                                         2,
                                         (_DWORD)p_cbBuffer,
                                         (_DWORD)v88,
                                         (__int64)(v4 + 136)) )
                  goto LABEL_220;
                v91 = *((_DWORD *)v4 + 6);
                v92 = v91 + *((unsigned __int16 *)v88 + 194);
                *((_DWORD *)v4 + 7) = v92;
                v93 = v91 + *((unsigned __int16 *)v88 + 195);
                *((_DWORD *)v4 + 3) = 2;
                *((_DWORD *)v4 + 8) = v93;
                if ( byte_14005C48B < 0 )
                {
                  _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Writing Handshake data starts at %u", v92);
                  McTemplateU0ps_EtwWriteTransfer(v94, QuicConnLogInfo, *((_QWORD *)a1 + 9), DstBuf);
                }
                v95 = (_BYTE *)*((_QWORD *)a1 + 273);
                if ( v95 )
                {
                  v96 = v88 + 398;
                  *v95 = v88[396];
                  v97 = *((_QWORD *)a1 + 273);
                  v98 = *((unsigned __int16 *)v88 + 198);
                  if ( (*a1 & 1) != 0 )
                  {
                    memmove((void *)(v97 + 162), v96, v98);
                    *(_BYTE *)(*((_QWORD *)a1 + 273) + 1LL) |= 8u;
                  }
                  else
                  {
                    memmove((void *)(v97 + 98), v96, v98);
                    *(_BYTE *)(*((_QWORD *)a1 + 273) + 1LL) |= 4u;
                  }
                }
              }
            }
            v87 = v122 + 1;
            v122 = v87;
            if ( v87 >= v124 )
              goto LABEL_221;
          }
        }
        if ( v128->cbBuffer < 2 )
        {
          if ( byte_14005C48D < 0 )
            McTemplateU0ps_EtwWriteTransfer(
              0,
              QuicTlsError,
              *((_QWORD *)a1 + 9),
              "TLS alert message received (invalid)");
          goto LABEL_261;
        }
        LODWORD(v38) = *((unsigned __int8 *)v128->pvBuffer + 1);
        *((_WORD *)v4 + 8) = v38;
        if ( (byte_14005C48D & 0x80) == 0 )
        {
LABEL_261:
          v32 |= 0x8000u;
          goto LABEL_280;
        }
        v69 = v38;
        v70 = "TLS alert message received";
LABEL_260:
        McTemplateU0pqs_EtwWriteTransfer(v38, (unsigned int)QuicTlsErrorStatus, *((_QWORD *)a1 + 9), v69, (__int64)v70);
        goto LABEL_261;
      }
      if ( v41 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, __int64))(*((_QWORD *)a1 + 4) + 24LL))(
               *((_QWORD *)a1 + 9),
               (unsigned __int16)(LOWORD(v41->cbBuffer) - 4),
               (__int64)v41->pvBuffer + 4) )
        {
          *a1 |= 4u;
          v32 = 1;
          v54 = (void *)*((_QWORD *)a1 + 272);
          if ( v54 )
          {
            ExFreePoolWithTag(v54, 0x34346351u);
            *((_QWORD *)a1 + 272) = 0;
            *((_DWORD *)a1 + 542) = 0;
          }
          goto LABEL_280;
        }
        if ( byte_14005C48D < 0 )
        {
          v53 = "Process QUIC TP";
          goto LABEL_267;
        }
      }
      else if ( byte_14005C48D < 0 )
      {
        v53 = "QUIC TP wasn't present";
LABEL_267:
        McTemplateU0ps_EtwWriteTransfer(v38, QuicTlsError, *((_QWORD *)a1 + 9), v53);
      }
LABEL_268:
      v32 = 0x8000;
      goto LABEL_280;
    }
    if ( (*a1 & 5) == 0 )
    {
      if ( byte_14005C48D < 0 )
      {
        v53 = "No QUIC TP received";
        goto LABEL_267;
      }
      goto LABEL_268;
    }
    v55 = (void *)*((_QWORD *)a1 + 8);
    if ( v55 )
    {
      ExFreePoolWithTag(v55, 0x46316351u);
      *((_QWORD *)a1 + 8) = 0;
    }
    if ( (*v4 & 1) != 0 )
      goto LABEL_156;
    if ( (*a1 & 1) == 0 )
    {
      memset(pBuffer, 0, 0x108u);
      ContextAttributesW = QueryContextAttributesW((PCtxtHandle)a1 + 1, 0x23u, pBuffer);
      if ( ContextAttributesW )
      {
        if ( (byte_14005C48D & 0x80) == 0 )
          goto LABEL_268;
        v58 = "query negotiated ALPN";
LABEL_108:
        McTemplateU0pqs_EtwWriteTransfer(
          (_DWORD)v58,
          (unsigned int)QuicTlsErrorStatus,
          *((_QWORD *)a1 + 9),
          ContextAttributesW,
          (__int64)v58);
        goto LABEL_268;
      }
      if ( pBuffer[0] != 1 )
      {
        if ( byte_14005C48D < 0 )
          McTemplateU0pqs_EtwWriteTransfer(
            v57,
            (unsigned int)QuicTlsErrorStatus,
            *((_QWORD *)a1 + 9),
            pBuffer[0],
            (__int64)"ALPN negotiation status");
        goto LABEL_268;
      }
      v59 = CxPlatTlsAlpnFindInList(
              *(_WORD *)(*((_QWORD *)a1 + 6) + 8LL),
              (unsigned __int8 *)(*((_QWORD *)a1 + 6) + 10LL),
              pBuffer[2],
              (char *)&pBuffer[2] + 1);
      *((_QWORD *)v4 + 8) = v59;
      if ( !v59 )
      {
        if ( byte_14005C48D < 0 )
        {
          v53 = "ALPN Mismatch";
          goto LABEL_267;
        }
        goto LABEL_268;
      }
    }
    v129 = 0;
    v148 = 0;
    memset(v147, 0, sizeof(v147));
    ContextAttributesW = QueryContextAttributesW((PCtxtHandle)a1 + 1, 0x5Du, v147);
    if ( ContextAttributesW )
    {
      if ( (byte_14005C48D & 0x80) == 0 )
        goto LABEL_268;
      v58 = "query session info";
      goto LABEL_108;
    }
    if ( (v147[0] & 1) != 0 )
      *v4 |= 2u;
    if ( (*a1 & 1) == 0 || (v120 = 0, (*(_DWORD *)(*((_QWORD *)a1 + 4) + 16LL) & 0x40) != 0) )
      v120 = 1;
    v60 = (struct _SecHandle *)(a1 + 16);
    pvContextBuffer = 0;
    v61 = *((_QWORD *)a1 + 4);
    v136 = 0;
    if ( (*(_DWORD *)(v61 + 16) & 0x80000) != 0 )
    {
      LODWORD(v136) = 3;
      v62 = QueryContextAttributesW(v60, 0x74u, (char *)&v136 + 8);
      v125 = v62;
      if ( !v62 )
        goto LABEL_127;
      v60 = (struct _SecHandle *)(a1 + 16);
    }
    LODWORD(v136) = 1;
    v62 = QueryContextAttributesW(v60, 0x5Fu, (char *)&v136 + 8);
    v125 = v62;
LABEL_127:
    LODWORD(p_cbBuffer) = -2146893042;
    if ( v62 == -2146893042 )
    {
      if ( (*(_DWORD *)(*((_QWORD *)a1 + 4) + 16LL) & 0x20) != 0 )
      {
        LODWORD(v136) = 0;
        HIDWORD(v129) = -2146893042;
        goto LABEL_130;
      }
    }
    else if ( !v62 )
    {
      v64 = *(_DWORD *)(*((_QWORD *)a1 + 4) + 16LL);
      if ( (v64 & 4) == 0 && (v64 & 0x60) != 0 )
      {
        v65 = QueryContextAttributesW((PCtxtHandle)a1 + 1, 0x72u, &v129);
        v125 = v65;
        if ( v65 == -2146893042 )
        {
          HIDWORD(v129) = -2146893042;
        }
        else if ( v65 )
        {
          if ( byte_14005C48D < 0 )
            McTemplateU0pqs_EtwWriteTransfer(
              v66,
              (unsigned int)QuicTlsErrorStatus,
              *((_QWORD *)a1 + 9),
              v65,
              (__int64)"query cert validation result");
          goto LABEL_268;
        }
      }
LABEL_130:
      if ( (*(_DWORD *)(*((_QWORD *)a1 + 4) + 16LL) & 0x10) != 0 )
        v32 = CxPlatTlsIndicateCertificateReceived(a1, v4, &v129, &v136);
      if ( pvContextBuffer )
        FreeContextBuffer(pvContextBuffer);
      if ( (v32 & 0x8000) != 0 )
        goto LABEL_280;
      v63 = *(_DWORD *)(*((_QWORD *)a1 + 4) + 16LL);
      if ( (v63 & 0x20) == 0 && HIDWORD(v129) )
      {
        if ( byte_14005C48D < 0 )
          McTemplateU0pqs_EtwWriteTransfer(
            v63,
            (unsigned int)QuicTlsErrorStatus,
            *((_QWORD *)a1 + 9),
            HIDWORD(v129),
            (__int64)"Certificate validation failed");
        v32 |= 0x8000u;
        *((_WORD *)v4 + 8) = 42;
        goto LABEL_280;
      }
      if ( byte_14005C48B < 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Handshake complete (resume=%hu)", (*v4 >> 1) & 1);
        McTemplateU0ps_EtwWriteTransfer(v68, QuicConnLogInfo, *((_QWORD *)a1 + 9), DstBuf);
      }
      *v4 |= 1u;
      v32 |= 0x40u;
      goto LABEL_156;
    }
    if ( v120 )
    {
      v67 = *(_DWORD *)(*((_QWORD *)a1 + 4) + 16LL);
      if ( (v67 & 4) == 0 )
      {
        if ( byte_14005C48D < 0 )
          McTemplateU0pqs_EtwWriteTransfer(
            v67,
            (unsigned int)QuicTlsErrorStatus,
            *((_QWORD *)a1 + 9),
            v62,
            (__int64)"Query peer cert");
        v32 = 0x8000;
        *((_WORD *)v4 + 8) = 80;
        goto LABEL_280;
      }
    }
    goto LABEL_130;
  }
  *v131 = 0;
  if ( p_cbBuffer && *p_cbBuffer && byte_14005C48B < 0 )
  {
    ImpersonationLevel[0] = *(SECURITY_IMPERSONATION_LEVEL *)p_cbBuffer;
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "TLS message missing %u bytes of data",
      *(_QWORD *)ImpersonationLevel);
LABEL_279:
    McTemplateU0ps_EtwWriteTransfer(v105, QuicConnLogInfo, *((_QWORD *)a1 + 9), DstBuf);
  }
LABEL_280:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x43316351u);
  return v32;
}

```

## disassembly

```asm
0x140036f1c  mov     [rsp-8+arg_8], rbx
0x140036f21  push    rbp
0x140036f22  push    rsi
0x140036f23  push    rdi
0x140036f24  push    r12
0x140036f26  push    r13
0x140036f28  push    r14
0x140036f2a  push    r15
0x140036f2c  lea     rbp, [rsp-200h]
0x140036f34  sub     rsp, 300h
0x140036f3b  mov     rax, cs:__security_cookie
0x140036f42  xor     rax, rsp
0x140036f45  mov     [rbp+230h+var_40], rax
0x140036f4c  mov     r15, r9
0x140036f4f  mov     [rbp+230h+var_2A0], r9
0x140036f53  xor     r9d, r9d
0x140036f56  mov     [rbp+230h+var_290], r8
0x140036f5a  lea     r13, [rcx+798h]
0x140036f61  xorps   xmm0, xmm0
0x140036f64  lea     rdi, [rcx+808h]
0x140036f6b  mov     eax, r9d
0x140036f6e  mov     rsi, rdx
0x140036f71  mov     rbx, rcx
0x140036f74  lea     r10d, [r9+2]
0x140036f78  mov     [rbp+230h+pTargetName], r9
0x140036f7c  lea     r12d, [r9+12h]
0x140036f80  mov     [rsp+330h+pInput.ulVersion], r9d
0x140036f85  movups  xmmword ptr [rbp+230h+P], xmm0
0x140036f89  mov     [rsp+330h+pInput.pBuffers], r13
0x140036f8e  mov     [rsp+330h+pInput.cBuffers], eax
0x140036f92  mov     qword ptr [rsp+330h+var_2B8.ulVersion], r9
0x140036f97  mov     [rbp+230h+var_2B8.pBuffers], rdi
0x140036f9b  cmp     [r8], r9d
0x140036f9e  jnz     loc_14003704A
0x140036fa4  mov     rcx, [rcx+8]; UTF8StringSource
0x140036fa8  test    rcx, rcx
0x140036fab  jz      short loc_140037010
0x140036fad  lea     rax, [rbp+230h+P]
0x140036fb1  mov     r8d, 43316351h
0x140036fb7  lea     rdx, [rbp+230h+P]
0x140036fbb  mov     [rbp+230h+pTargetName], rax
0x140036fbf  call    CxPlatTlsUtf8ToUnicodeString
0x140036fc4  xor     r9d, r9d
0x140036fc7  test    eax, eax
0x140036fc9  jns     short loc_140037002
0x140036fcb  lea     esi, [r12+6Eh]
0x140036fd0  test    cs:byte_14005C48D, sil
0x140036fd7  jz      short loc_140036FF8
0x140036fd9  mov     r8, [rbx+48h]
0x140036fdd  lea     rcx, aConvertSniToUn; "Convert SNI to unicode"
0x140036fe4  mov     r9d, eax
0x140036fe7  mov     qword ptr [rsp+330h+ImpersonationLevel], rcx
0x140036fec  lea     rdx, QuicTlsErrorStatus
0x140036ff3  call    McTemplateU0pqs_EtwWriteTransfer
0x140036ff8  mov     eax, 8000h
0x140036ffd  jmp     loc_14003858E
0x140037002  mov     eax, [rsp+330h+pInput.cBuffers]
0x140037006  mov     r10d, 2
0x14003700c  mov     r8, [rbp+230h+var_290]
0x140037010  add     rax, rax
0x140037013  mov     r14d, 1
0x140037019  mov     [r13+rax*8+4], r12d
0x14003701e  mov     ecx, [rsp+330h+pInput.cBuffers]
0x140037022  mov     eax, [rbx+38h]
0x140037025  add     rcx, rcx
0x140037028  mov     [r13+rcx*8+0], eax
0x14003702d  mov     ecx, [rsp+330h+pInput.cBuffers]
0x140037031  mov     rax, [rbx+30h]
0x140037035  add     rcx, rcx
0x140037038  mov     [r13+rcx*8+8], rax
0x14003703d  mov     eax, [rsp+330h+pInput.cBuffers]
0x140037041  add     eax, r14d
0x140037044  mov     [rsp+330h+pInput.cBuffers], eax
0x140037048  jmp     short loc_140037067
0x14003704a  mov     [r13+4], r10d
0x14003704e  mov     r14d, 1
0x140037054  mov     eax, [r8]
0x140037057  mov     [r13+0], eax
0x14003705b  mov     [r13+8], rsi
0x14003705f  mov     [rsp+330h+pInput.cBuffers], r14d
0x140037064  mov     eax, r14d
0x140037067  mov     rcx, r10
0x14003706a  add     rax, rax
0x14003706d  mov     [r13+rax*8+4], r9d
0x140037072  mov     eax, [rsp+330h+pInput.cBuffers]
0x140037076  add     rax, rax
0x140037079  mov     [r13+rax*8+0], r9d
0x14003707e  mov     eax, [rsp+330h+pInput.cBuffers]
0x140037082  add     rax, rax
0x140037085  mov     [r13+rax*8+8], r9
0x14003708a  mov     eax, [rsp+330h+pInput.cBuffers]
0x14003708e  inc     eax
0x140037090  mov     [rsp+330h+pInput.cBuffers], eax
0x140037094  sub     rcx, r14
0x140037097  jnz     short loc_14003706A
0x140037099  add     rax, rax
0x14003709c  lea     rcx, [rbx+50h]
0x1400370a0  mov     rdx, 100000000h
0x1400370aa  mov     [rcx], rdx
0x1400370ad  mov     dword ptr [r13+rax*8+4], 1Bh
0x1400370b6  mov     eax, [rsp+330h+pInput.cBuffers]
0x1400370ba  add     rax, rax
0x1400370bd  mov     dword ptr [r13+rax*8+0], 8
0x1400370c6  mov     eax, [rsp+330h+pInput.cBuffers]
0x1400370ca  add     rax, rax
0x1400370cd  mov     [r13+rax*8+8], rcx
0x1400370d2  mov     ecx, [rsp+330h+pInput.cBuffers]
0x1400370d6  mov     al, [rbx]
0x1400370d8  inc     ecx
0x1400370da  mov     [rsp+330h+pInput.cBuffers], ecx
0x1400370de  test    r14b, al
0x1400370e1  jz      short loc_140037116
0x1400370e3  test    r10b, al
0x1400370e6  jnz     short loc_140037116
0x1400370e8  mov     eax, ecx
0x1400370ea  add     rax, rax
0x1400370ed  mov     [r13+rax*8+4], r12d
0x1400370f2  mov     ecx, [rsp+330h+pInput.cBuffers]
0x1400370f6  mov     eax, [rbx+38h]
0x1400370f9  add     rcx, rcx
0x1400370fc  mov     [r13+rcx*8+0], eax
0x140037101  mov     ecx, [rsp+330h+pInput.cBuffers]
0x140037105  mov     rax, [rbx+30h]
0x140037109  add     rcx, rcx
0x14003710c  mov     [r13+rcx*8+8], rax
0x140037111  add     [rsp+330h+pInput.cBuffers], r14d
0x140037116  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x14003711a  add     rax, rax
0x14003711d  mov     [rdi+rax*8+4], r10d
0x140037122  movzx   ecx, word ptr [r15+14h]
0x140037127  movzx   eax, word ptr [r15+12h]
0x14003712c  sub     ecx, eax
0x14003712e  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x140037132  add     rax, rax
0x140037135  mov     [rdi+rax*8], ecx
0x140037138  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x14003713c  movzx   ecx, word ptr [r15+12h]
0x140037141  add     rax, rax
0x140037144  add     rcx, [r15+28h]
0x140037148  mov     [rdi+rax*8+8], rcx
0x14003714d  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x140037151  add     eax, r14d
0x140037154  mov     [rsp+330h+var_2B8.cBuffers], eax
0x140037158  mov     ecx, eax
0x14003715a  add     rcx, rcx
0x14003715d  mov     dword ptr [rdi+rcx*8+4], 11h
0x140037165  lea     rcx, [rbp+230h+var_280]
0x140037169  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x14003716d  add     rax, rax
0x140037170  mov     [rdi+rax*8], r10d
0x140037174  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x140037178  add     rax, rax
0x14003717b  mov     [rdi+rax*8+8], rcx
0x140037180  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x140037184  add     eax, r14d
0x140037187  mov     [rsp+330h+var_2B8.cBuffers], eax
0x14003718b  cmp     [rbx+40h], r9
0x14003718f  jz      short loc_1400371D9
0x140037191  mov     eax, [rsp+330h+pInput.cBuffers]
0x140037195  add     rax, rax
0x140037198  mov     dword ptr [r13+rax*8+4], 19h
0x1400371a1  mov     rax, [rbx+40h]
0x1400371a5  movzx   ecx, word ptr [rax+8]
0x1400371a9  mov     eax, [rsp+330h+pInput.cBuffers]
0x1400371ad  add     ecx, 0Ah
0x1400371b0  add     rax, rax
0x1400371b3  mov     [r13+rax*8+0], ecx
0x1400371b8  mov     ecx, [rsp+330h+pInput.cBuffers]
0x1400371bc  mov     rax, [rbx+40h]
0x1400371c0  add     rcx, rcx
0x1400371c3  mov     [r13+rcx*8+8], rax
0x1400371c8  mov     ecx, [rsp+330h+pInput.cBuffers]
0x1400371cc  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x1400371d0  add     ecx, r14d
0x1400371d3  mov     [rsp+330h+pInput.cBuffers], ecx
0x1400371d7  jmp     short loc_1400371DD
0x1400371d9  mov     ecx, [rsp+330h+pInput.cBuffers]
0x1400371dd  xor     edx, edx
0x1400371df  mov     [rbp+230h+var_100], rdx
0x1400371e6  mov     [rbp+230h+var_F8], edx
0x1400371ec  lea     r11d, [rdx+1Ah]
0x1400371f0  cmp     [r8], r9d
0x1400371f3  jz      loc_1400372B6
0x1400371f9  mov     dl, [rbx]
0x1400371fb  test    dl, 5
0x1400371fe  jnz     loc_1400372B6
0x140037204  movzx   eax, word ptr [rbx+2]
0x140037208  and     dl, r14b
0x14003720b  mov     word ptr [rbp+230h+var_F8], ax
0x140037212  neg     dl
0x140037214  mov     dword ptr [rbp+230h+var_100+4], r14d
0x14003721b  sbb     ax, ax
0x14003721e  and     ax, 0FFF9h
0x140037222  add     ax, 8
0x140037226  mov     word ptr [rbp+230h+var_F8+2], ax
0x14003722d  mov     eax, ecx
0x14003722f  lea     rcx, [rbp+230h+var_100]
0x140037236  add     rax, rax
0x140037239  mov     [r13+rax*8+4], r11d
0x14003723e  mov     eax, [rsp+330h+pInput.cBuffers]
0x140037242  add     rax, rax
0x140037245  mov     dword ptr [r13+rax*8+0], 0Ch
0x14003724e  mov     eax, [rsp+330h+pInput.cBuffers]
0x140037252  add     rax, rax
0x140037255  mov     [r13+rax*8+8], rcx
0x14003725a  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x14003725e  add     [rsp+330h+pInput.cBuffers], r14d
0x140037263  add     rax, rax
0x140037266  mov     [rdi+rax*8+4], r11d
0x14003726b  mov     ecx, [rsp+330h+var_2B8.cBuffers]
0x14003726f  add     rcx, rcx
0x140037272  cmp     [rbx+880h], r9
0x140037279  jz      short loc_140037299
0x14003727b  mov     eax, [rbx+878h]
0x140037281  mov     [rdi+rcx*8], eax
0x140037284  mov     ecx, [rsp+330h+var_2B8.cBuffers]
0x140037288  mov     rax, [rbx+880h]
0x14003728f  add     rcx, rcx
0x140037292  mov     [rdi+rcx*8+8], rax
0x140037297  jmp     short loc_1400372AB
0x140037299  mov     eax, [r8]
0x14003729c  mov     [rdi+rcx*8], eax
0x14003729f  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x1400372a3  add     rax, rax
0x1400372a6  mov     [rdi+rax*8+8], rsi
0x1400372ab  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x1400372af  add     eax, r14d
0x1400372b2  mov     [rsp+330h+var_2B8.cBuffers], eax
0x1400372b6  lea     rcx, [rbx+58h]
0x1400372ba  mov     edx, 4
0x1400372bf  mov     r8d, 1D0h
0x1400372c5  add     rax, rax
0x1400372c8  mov     dword ptr [rdi+rax*8+4], 1Ch
0x1400372d0  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x1400372d4  add     rax, rax
0x1400372d7  mov     [rdi+rax*8], r8d
0x1400372db  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x1400372df  add     rax, rax
0x1400372e2  mov     [rdi+rax*8+8], rcx
0x1400372e7  add     rcx, r8
0x1400372ea  mov     eax, [rsp+330h+var_2B8.cBuffers]
0x1400372ee  add     eax, r14d
0x1400372f1  mov     [rsp+330h+var_2B8.cBuffers], eax
0x1400372f5  sub     rdx, r14
0x1400372f8  jnz     short loc_1400372C5
0x1400372fa  mov     r12d, 8000h
0x140037300  mov     r8, [rbx+20h]
0x140037304  mov     ecx, [r8+10h]
0x140037308  test    [rbx], r14b
0x14003730b  jz      short loc_14003731D
0x14003730d  and     ecx, 40h
0x140037310  or      ecx, 300B00h
0x140037316  shr     ecx, 5
0x140037319  mov     edi, ecx
0x14003731b  jmp     short loc_14003732C
0x14003731d  mov     edi, 0C018h
0x140037322  test    r12d, ecx
0x140037325  jz      short loc_14003732C
0x140037327  mov     edi, 0C098h
0x14003732c  mov     [rbp+230h+var_288], r9d
0x140037330  mov     esi, 80h
0x140037335  mov     rdx, [r8+30h]; Token
0x140037339  test    rdx, rdx
0x14003733c  jz      short loc_1400373A5
0x14003733e  mov     rcx, gs:188h; Thread
0x140037347  cmp     [r8+38h], r9b
0x14003734b  jz      short loc_14003735A
0x14003734d  xor     r9d, r9d
0x140037350  mov     [rsp+330h+ImpersonationLevel], r10d
0x140037355  xor     r8d, r8d
0x140037358  jmp     short loc_14003736A
0x14003735a  mov     eax, [r8+3Ch]
0x14003735e  mov     r9b, [r8+3Ah]; EffectiveOnly
0x140037362  mov     r8b, [r8+39h]; CopyOnOpen
0x140037366  mov     [rsp+330h+ImpersonationLevel], eax; ImpersonationLevel
0x14003736a  call    cs:__imp_PsImpersonateClient
0x140037371  nop     dword ptr [rax+rax+00h]
0x140037376  mov     r9d, eax
0x140037379  test    eax, eax
0x14003737b  jns     short loc_1400373A2
0x14003737d  test    cs:byte_14005C48D, sil
0x140037384  jz      short loc_1400373A2
0x140037386  mov     r8, [rbx+48h]
0x14003738a  lea     rax, aPsimpersonatec; "PsImpersonateClient failed"
0x140037391  lea     rdx, QuicTlsErrorStatus
0x140037398  mov     qword ptr [rsp+330h+ImpersonationLevel], rax
0x14003739d  call    McTemplateU0pqs_EtwWriteTransfer
0x1400373a2  xor     r9d, r9d
0x1400373a5  lea     rcx, [rbx+10h]
0x1400373a9  mov     rdx, [rcx]
0x1400373ac  test    [rbx], r14b
0x1400373af  jz      short loc_140037400
0x1400373b1  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400373b5  jz      short loc_1400373C1
0x1400373b7  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x1400373bc  mov     rdx, rcx
0x1400373bf  jnz     short loc_1400373C4
0x1400373c1  mov     rdx, r9; phContext
0x1400373c4  mov     [rsp+330h+ptsExpiry], r9; ptsExpiry
0x1400373c9  lea     rax, [rbp+230h+var_288]
  ... truncated ...
```

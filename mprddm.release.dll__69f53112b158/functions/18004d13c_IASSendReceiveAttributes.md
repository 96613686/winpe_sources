# IASSendReceiveAttributes

- ea: `0x18004d13c`
- end: `0x18004defc`
- name: `IASSendReceiveAttributes`
- size: `3520`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: ``

## callers

- `0x18004df80`
- `0x18004e020`
- `0x18004e090`
- `0x18004e0f0`
- `0x18004e160`
- `0x18004e220`

## callees

- `0x180002be6`
- `0x180046fd4`
- `0x18004d13c`
- `0x1800755b8`
- `0x180075b28`
- `0x180075ba0`
- `0x180075d34`
- `0x180075fe0`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18004daff`
- `KERNEL32!MultiByteToWideChar` at `0x18004db28`
- `KERNEL32!MultiByteToWideChar` at `0x18004dc25`
- `KERNEL32!MultiByteToWideChar` at `0x18004daff`
- `KERNEL32!MultiByteToWideChar` at `0x18004db28`
- `KERNEL32!MultiByteToWideChar` at `0x18004dc25`
- `KERNEL32!GetLastError` at `0x18004dd6c`
- `KERNEL32!GetLastError` at `0x18004dd6c`
- `ole32!CoUninitialize` at `0x18004d34f`
- `ole32!CoUninitialize` at `0x18004d34f`
- `ole32!CoInitializeEx` at `0x18004d242`
- `ole32!CoInitializeEx` at `0x18004d242`
- `rtutils!RouterLogEventStringW` at `0x18004dc89`
- `rtutils!RouterLogEventStringW` at `0x18004dc89`
- `iashlpr!FreeAttributes` at `0x18004d2f2`
- `iashlpr!FreeAttributes` at `0x18004d31d`
- `iashlpr!FreeAttributes` at `0x18004d2f2`
- `iashlpr!FreeAttributes` at `0x18004d31d`
- `iashlpr!MemFreeIas` at `0x18004d302`
- `iashlpr!MemFreeIas` at `0x18004d32d`
- `iashlpr!MemFreeIas` at `0x18004d302`
- `iashlpr!MemFreeIas` at `0x18004d32d`
- `iashlpr!DoRequest` at `0x18004d9a2`
- `iashlpr!DoRequest` at `0x18004d9a2`
- `iashlpr!AllocateAttributes` at `0x18004d2cc`
- `iashlpr!AllocateAttributes` at `0x18004d2cc`
- `iashlpr!MemAllocIas` at `0x18004d293`
- `iashlpr!MemAllocIas` at `0x18004d41c`
- `iashlpr!MemAllocIas` at `0x18004d685`
- `iashlpr!MemAllocIas` at `0x18004d765`
- `iashlpr!MemAllocIas` at `0x18004d833`
- `iashlpr!MemAllocIas` at `0x18004d8e6`
- `iashlpr!MemAllocIas` at `0x18004d293`
- `iashlpr!MemAllocIas` at `0x18004d41c`
- `iashlpr!MemAllocIas` at `0x18004d685`
- `iashlpr!MemAllocIas` at `0x18004d765`
- `iashlpr!MemAllocIas` at `0x18004d833`
- `iashlpr!MemAllocIas` at `0x18004d8e6`
- `WS2_32!__imp_htonl` at `0x18004d448`
- `WS2_32!__imp_htonl` at `0x18004d448`
- `WS2_32!__imp_ntohl` at `0x18004de4a`
- `WS2_32!__imp_ntohl` at `0x18004de4a`

## string_xrefs

- `0x18004dd33`: `IASResponse = ACCESS_ACCEPT`
- `0x18004da9b`: `IASResponse = ACCESS_CHALLENGE`
- `0x18004dd00`: `IASResponse = ACCESS_REJECT. Failurereason=0x%x`

## pseudocode

```c
__int64 __fastcall IASSendReceiveAttributes(unsigned int a1, _DWORD *a2, __int64 *a3, int *a4)
{
  int v4; // edi
  unsigned int v7; // r12d
  _OWORD *v9; // rbx
  DWORD LastError; // esi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 result; // rax
  int v14; // r14d
  unsigned int v15; // ecx
  unsigned int v16; // r13d
  unsigned int v17; // r13d
  _QWORD *v18; // rax
  __int64 v19; // r8
  _QWORD *v20; // rdi
  HLOCAL *v21; // r12
  int Attributes; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rcx
  u_long *v26; // r12
  int v27; // ecx
  _DWORD *v28; // rax
  _DWORD *v29; // rdi
  u_long v30; // eax
  unsigned int v31; // r12d
  unsigned int v32; // r12d
  unsigned int v33; // r12d
  int v34; // eax
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  bool v38; // zf
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  int v43; // ecx
  bool v44; // zf
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  _QWORD *v50; // rax
  __int64 v51; // rax
  size_t v52; // rdi
  void *v53; // rcx
  __int64 v54; // rdx
  unsigned int v55; // r12d
  _OWORD *v56; // rax
  __int64 v57; // rcx
  unsigned int v58; // ebx
  void *v59; // r9
  const void **v60; // rdx
  int v61; // eax
  DWORD *v62; // rbx
  const CHAR *v63; // r8
  __int64 v64; // rax
  __int64 v65; // rdx
  unsigned __int64 v66; // rcx
  unsigned int v67; // edi
  int v68; // r15d
  __int64 v69; // rcx
  __m128i v70; // xmm1
  int v71; // ecx
  int v72; // ecx
  int v73; // ecx
  int v74; // ecx
  __int64 v75; // rbx
  unsigned __int64 v76; // xmm1_8
  _WORD *v77; // xmm1_8
  u_long *v78; // rcx
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-E0h]
  int v80; // [rsp+50h] [rbp-B0h]
  unsigned int v81; // [rsp+54h] [rbp-ACh]
  unsigned int v83; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v84; // [rsp+64h] [rbp-9Ch] BYREF
  int v85; // [rsp+68h] [rbp-98h]
  unsigned int v86; // [rsp+6Ch] [rbp-94h]
  unsigned int v87; // [rsp+70h] [rbp-90h] BYREF
  __int64 v88; // [rsp+78h] [rbp-88h]
  __int64 v89; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v90; // [rsp+88h] [rbp-78h]
  unsigned int v91; // [rsp+8Ch] [rbp-74h]
  _DWORD *v92; // [rsp+90h] [rbp-70h]
  const void **v93; // [rsp+98h] [rbp-68h]
  int *v94; // [rsp+A0h] [rbp-60h]
  LPCCH lpMultiByteStr; // [rsp+A8h] [rbp-58h]
  _DWORD *v96; // [rsp+B0h] [rbp-50h]
  _QWORD *v97; // [rsp+B8h] [rbp-48h]
  LPWSTR plpszSubStringArray[2]; // [rsp+C0h] [rbp-40h] BYREF
  LPCWCH v99; // [rsp+D0h] [rbp-30h]
  __int128 v100; // [rsp+D8h] [rbp-28h]
  _BYTE MultiByteStr[40]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 v102[32]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR v103[40]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR v104[104]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v105; // [rsp+270h] [rbp+170h] BYREF
  char v106[2044]; // [rsp+274h] [rbp+174h] BYREF
  WCHAR WideCharStr[264]; // [rsp+A70h] [rbp+970h] BYREF

  v4 = 0;
  v92 = a2;
  lpMultiByteStr = &g_aszUnauthenticatedUser;
  strcpy(MultiByteStr, "{NA}");
  v7 = a1;
  v90 = a1;
  v94 = a4;
  v87 = 0;
  v9 = 0;
  v84 = 0;
  LastError = 0;
  v89 = 0;
  v93 = 0;
  v96 = 0;
  v85 = 0;
  memset(&MultiByteStr[5], 0, 35);
  v83 = 0;
  v105 = 0;
  memset_0(v106, 0, sizeof(v106));
  RasAuthAttributesPrint(v12, v11, a2);
  if ( v7 <= 4 )
  {
    v4 = 1;
  }
  else if ( v7 != 5 )
  {
    return 87;
  }
  v80 = v4;
  *a3 = 0;
  v14 = 691;
  *a4 = 691;
  LODWORD(result) = CoInitializeEx(0, 0);
  if ( (int)result < 0 )
    return (unsigned __int16)result;
  v15 = 0;
  v86 = 0;
  if ( *a2 )
  {
    do
      ++v15;
    while ( a2[4 * v15] );
    v86 = v15;
  }
  v16 = v15 + 1;
  if ( v4 != 1 )
    v16 = v15;
  v17 = v16 + 2;
  v91 = v17;
  v18 = (_QWORD *)MemAllocIas(8 * v17, 0);
  v97 = v18;
  v20 = v18;
  if ( !v18 )
  {
    v21 = (HLOCAL *)a3;
    LastError = 8;
    goto LABEL_18;
  }
  memset_0(v18, 0, 8LL * v17);
  Attributes = AllocateAttributes(v17, v20);
  v24 = 0;
  if ( Attributes < 0 )
  {
    LastError = (unsigned __int16)Attributes;
    goto LABEL_16;
  }
  v25 = 0;
  v81 = 0;
  if ( !v86 )
    goto LABEL_51;
  v26 = v92 + 2;
  v88 = (__int64)v20;
  do
  {
    v27 = *(v26 - 2);
    if ( v27 <= 55 )
    {
      if ( v27 == 55 )
        goto LABEL_46;
      if ( v27 > 26 )
      {
        if ( v27 > 43 )
        {
          v45 = v27 - 45;
          if ( !v45 )
            goto LABEL_46;
          v46 = v45 - 1;
          if ( !v46 )
            goto LABEL_46;
          v47 = v46 - 1;
          if ( !v47 )
            goto LABEL_46;
          v48 = v47 - 1;
          if ( !v48 )
            goto LABEL_46;
          v49 = v48 - 1;
          if ( !v49 )
            goto LABEL_46;
          v44 = v49 == 2;
        }
        else
        {
          if ( v27 == 43 )
            goto LABEL_46;
          v40 = v27 - 27;
          if ( !v40 )
            goto LABEL_46;
          v41 = v40 - 1;
          if ( !v41 )
            goto LABEL_46;
          v42 = v41 - 1;
          if ( !v42 )
            goto LABEL_46;
          v39 = v42 - 11;
          v38 = v39 == 0;
LABEL_69:
          if ( v38 )
            goto LABEL_46;
          v43 = v39 - 1;
          if ( !v43 )
            goto LABEL_46;
          v44 = v43 == 1;
        }
        if ( v44 )
          goto LABEL_46;
        goto LABEL_101;
      }
      if ( v27 == 26 )
      {
        if ( *(v26 - 1) >= 8 )
        {
          v23 = *(_QWORD *)v26;
          if ( *(unsigned __int8 *)(*(_QWORD *)v26 + 3LL)
             + (**(unsigned __int8 **)v26 << 24)
             + (*(unsigned __int8 *)(*(_QWORD *)v26 + 2LL) << 8)
             + (*(unsigned __int8 *)(*(_QWORD *)v26 + 1LL) << 16) == 311
            && (*(_BYTE *)(v23 + 4) == 1 || (unsigned int)*(unsigned __int8 *)(v23 + 4) - 3 <= 1) )
          {
            v80 = 0;
          }
        }
        v51 = *(_QWORD *)v26;
        if ( *(_BYTE *)(*(_QWORD *)v26 + 4LL) == 56 )
        {
          *(_OWORD *)MultiByteStr = *(_OWORD *)(v51 + 6);
          *(_OWORD *)&MultiByteStr[16] = *(_OWORD *)(v51 + 22);
          *(_QWORD *)&MultiByteStr[32] = *(_QWORD *)(v51 + 38);
        }
        goto LABEL_101;
      }
      if ( v27 > 9 )
      {
        v35 = v27 - 10;
        if ( !v35 )
          goto LABEL_46;
        v36 = v35 - 2;
        if ( !v36 )
          goto LABEL_46;
        v37 = v36 - 1;
        if ( !v37 )
          goto LABEL_46;
        v39 = v37 - 1;
        v38 = v39 == 0;
        goto LABEL_69;
      }
      if ( v27 == 9 )
        goto LABEL_46;
      v23 = (unsigned int)(v27 - 2);
      if ( v27 != 2 )
      {
        v23 = (unsigned int)(v27 - 3);
        if ( v27 != 3 )
        {
          v23 = (unsigned int)(v27 - 4);
          if ( v27 == 4 )
            goto LABEL_39;
          v23 = (unsigned int)(v27 - 5);
          if ( v27 == 5 || (v23 = (unsigned int)(v27 - 6), v27 == 6) || (v23 = (unsigned int)(v27 - 7), v27 == 7) )
          {
            if ( v27 == 7 && *(_QWORD *)v26 == 3 )
              v80 = 0;
LABEL_46:
            *(_DWORD *)(*v20 + 16LL) = 2;
            *(_DWORD *)(*v20 + 24LL) = *v26;
            goto LABEL_47;
          }
          if ( v27 == 8 )
          {
LABEL_39:
            v28 = (_DWORD *)MemAllocIas(128, v23);
            v29 = v28;
            if ( !v28 )
              goto LABEL_107;
            memset_0(v28, 0, 0x80u);
            v30 = htonl(*v26);
            v23 = v88;
            v29[1] = v30;
            *v29 = 2;
            *((_QWORD *)v29 + 1) = 0;
            *(_DWORD *)(*(_QWORD *)v23 + 16LL) = 4;
            *(_QWORD *)(*(_QWORD *)v23 + 24LL) = v29;
            if ( *(v26 - 2) == 4 )
              v9 = v29;
            v20 = (_QWORD *)v23;
            goto LABEL_47;
          }
          goto LABEL_99;
        }
      }
      v34 = 1;
LABEL_91:
      v85 = v34;
      v80 = 0;
LABEL_99:
      if ( v27 == 1 )
        lpMultiByteStr = *(LPCCH *)v26;
      goto LABEL_101;
    }
    v23 = (unsigned int)(v27 - 61);
    if ( v27 == 61 )
      goto LABEL_46;
    v23 = (unsigned int)(v27 - 62);
    if ( v27 == 62 )
      goto LABEL_46;
    v23 = (unsigned int)(v27 - 64);
    if ( v27 == 64 )
      goto LABEL_46;
    v23 = (unsigned int)(v27 - 65);
    if ( v27 == 65 )
      goto LABEL_46;
    v23 = (unsigned int)(v27 - 75);
    if ( v27 == 75 )
      goto LABEL_46;
    v23 = (unsigned int)(v27 - 76);
    if ( v27 == 76 )
      goto LABEL_46;
    v23 = (unsigned int)(v27 - 79);
    if ( v27 == 79 )
    {
      v34 = v85;
      goto LABEL_91;
    }
    v23 = (unsigned int)(v27 - 96);
    if ( (unsigned int)v23 <= 1 )
    {
      v50 = (_QWORD *)MemAllocIas(8, v23);
      v24 = 0;
      v23 = (__int64)v50;
      if ( !v50 )
        goto LABEL_107;
      *v50 = **(_QWORD **)v26;
      *(_DWORD *)(*v20 + 16LL) = 6;
      *(_QWORD *)(*v20 + 32LL) = v50;
      *(_DWORD *)(*v20 + 24LL) = 8;
      goto LABEL_47;
    }
LABEL_101:
    v52 = *(v26 - 1);
    v53 = (void *)MemAllocIas(v52, v23);
    if ( !v53 )
      goto LABEL_107;
    if ( *(v26 - 2) == 32 )
    {
      v93 = (const void **)&v92[4 * v81];
    }
    else if ( *(v26 - 2) == 31 )
    {
      v96 = &v92[4 * v81];
    }
    v54 = v88;
    *(_DWORD *)(*(_QWORD *)v88 + 16LL) = 6;
    *(_DWORD *)(*(_QWORD *)v54 + 24LL) = v52;
    *(_QWORD *)(*(_QWORD *)v54 + 32LL) = v53;
    memcpy_0(v53, *(const void **)v26, v52);
    v20 = (_QWORD *)v88;
LABEL_47:
    v38 = (_QWORD)xmmword_1800D1100 == 0;
    *(_DWORD *)(*v20 + 8LL) = *(v26 - 2);
    if ( !v38 )
    {
      LOWORD(v105) = 0;
      FormatRRASErrorString(&v105, L"Inserting attribute type %d", *(v26 - 2));
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasAuthTemplateFunc)(gRasAuthEtwContext, xmmword_1800D1100, &v105);
    }
    ++v20;
    v25 = v81 + 1;
    v88 = (__int64)v20;
    v26 += 4;
    v81 = v25;
  }
  while ( (unsigned int)v25 < v86 );
  v20 = v97;
  v7 = v90;
LABEL_51:
  if ( v80 == 1 )
  {
    v23 = 2;
    *(_DWORD *)(v20[v25] + 8LL) = 40;
    *(_DWORD *)(v20[v25] + 16LL) = 2;
    if ( v7 )
    {
      v31 = v7 - 1;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( v32 )
        {
          v33 = v32 - 1;
          if ( v33 )
          {
            if ( v33 == 1 )
              *(_DWORD *)(v20[v25] + 24LL) = 8;
          }
          else
          {
            *(_DWORD *)(v20[v25] + 24LL) = 7;
          }
        }
        else
        {
          *(_DWORD *)(v20[v25] + 24LL) = 3;
        }
      }
      else
      {
        *(_DWORD *)(v20[v25] + 24LL) = 2;
      }
    }
    else
    {
      *(_DWORD *)(v20[v25] + 24LL) = 1;
    }
    v55 = v81 + 1;
  }
  else
  {
    v55 = v81;
  }
  if ( !v9 )
  {
    --v17;
    goto LABEL_119;
  }
  v56 = (_OWORD *)MemAllocIas(128, v23);
  if ( !v56 )
    goto LABEL_107;
  v57 = v55++;
  *v56 = *v9;
  v56[1] = v9[1];
  v56[2] = v9[2];
  v56[3] = v9[3];
  v56[4] = v9[4];
  v56[5] = v9[5];
  v56[6] = v9[6];
  v56[7] = v9[7];
  *(_DWORD *)(v20[v57] + 16LL) = 4;
  *(_QWORD *)(v20[v57] + 24LL) = v56;
  v23 = *((_QWORD *)&xmmword_1800D1100 + 1);
  *(_DWORD *)(v20[v57] + 8LL) = 4108;
  if ( v23 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasAuthTemplateFunc)(
      gRasAuthEtwContext,
      v23,
      L"Inserting attribute type 4108");
LABEL_119:
  if ( !v93 )
  {
    --v17;
    goto LABEL_124;
  }
  v58 = *((_DWORD *)v93 + 1);
  v59 = (void *)MemAllocIas(v58, v23);
  if ( !v59 )
  {
LABEL_107:
    LastError = 8;
    goto LABEL_16;
  }
  v60 = v93;
  *(_DWORD *)(v20[v55] + 8LL) = 4128;
  *(_DWORD *)(v20[v55] + 16LL) = 6;
  *(_DWORD *)(v20[v55] + 24LL) = v58;
  *(_QWORD *)(v20[v55] + 32LL) = v59;
  memcpy_0(v59, v60[1], v58);
  if ( *((_QWORD *)&xmmword_1800D1100 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasAuthTemplateFunc)(
      gRasAuthEtwContext,
      *((_QWORD *)&xmmword_1800D1100 + 1),
      L"Inserting attribute type 4128");
LABEL_124:
  v61 = DoRequest(v17, v20, &v84, &v89, v80, &v87, 5, &v83, 1);
  if ( v61 < 0 )
  {
    LastError = (unsigned __int16)v61;
    if ( (_QWORD)xmmword_1800D1100 )
    {
      LOWORD(v105) = 0;
      FormatRRASErrorString(&v105, L"IAS->DoRequest failed with %d", (unsigned __int16)v61);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasAuthTemplateFunc)(gRasAuthEtwContext, xmmword_1800D1100, &v105);
    }
    goto LABEL_16;
  }
  v24 = v87;
  if ( v87 == 1 )
  {
    if ( *((_QWORD *)&xmmword_1800D1100 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasAuthTemplateFunc)(
        gRasAuthEtwContext,
        *((_QWORD *)&xmmword_1800D1100 + 1),
        L"IASResponse = ACCESS_ACCEPT");
    *v94 = 0;
    goto LABEL_174;
  }
  if ( v87 != 2 )
  {
    if ( v87 == 3 )
    {
      if ( *((_QWORD *)&xmmword_1800D1100 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasAuthTemplateFunc)(
          gRasAuthEtwContext,
          *((_QWORD *)&xmmword_1800D1100 + 1),
          L"IASResponse = ACCESS_CHALLENGE");
      if ( v85 != 1 )
        v14 = 0;
      *v94 = v14;
      goto LABEL_174;
    }
    if ( v87 != 5 )
    {
      if ( (_QWORD)xmmword_1800D1100 )
      {
        LOWORD(v105) = 0;
        FormatRRASErrorString(&v105, L"IASResponse = %d, FailureReason = 0x%x", v87, v83);
        goto LABEL_133;
      }
      goto LABEL_174;
    }
  }
  v100 = 0;
  memset_0(v102, 0, sizeof(v102));
  MultiByteToWideChar(0, 0, lpMultiByteStr, -1, WideCharStr, 257);
  MultiByteToWideChar(0, 0, MultiByteStr, -1, v103, 40);
  if ( (int)v83 > 65 )
  {
    switch ( v83 )
    {
      case 'B':
        v14 = 942;
        break;
      case 'D':
LABEL_146:
        v14 = 940;
        break;
      case 'F':
        v14 = 941;
        break;
      case '`':
        v14 = 930;
        break;
      default:
        goto LABEL_155;
    }
  }
  else if ( v83 == 65 )
  {
    v14 = 649;
  }
  else if ( v83 != 16 )
  {
    switch ( v83 )
    {
      case 0x11u:
        v14 = 709;
        break;
      case 0x22u:
        v14 = 647;
        break;
      case 0x23u:
        v14 = 708;
        break;
      case 0x25u:
        goto LABEL_146;
      default:
LABEL_155:
        v14 = 812;
        break;
    }
  }
  v62 = (DWORD *)v94;
  *v94 = v14;
  StringCchPrintfW(v102, 0x20u, L"0x%x");
  plpszSubStringArray[0] = v103;
  plpszSubStringArray[1] = WideCharStr;
  if ( v96 )
  {
    v63 = (const CHAR *)*((_QWORD *)v96 + 1);
    v99 = v104;
    *(_QWORD *)&v100 = v102;
    MultiByteToWideChar(0, 0, v63, -1, v104, 100);
    if ( (unsigned int)g_LoggingLevel > 1 )
      RouterLogEventStringW(g_hEventLog, 2u, 0x4F2Fu, 4u, plpszSubStringArray, *v62, 3u);
  }
  else
  {
    v99 = v102;
    if ( (unsigned int)g_LoggingLevel > 1 )
      RouterLogEventStringW(g_hEventLog, 2u, 0x4F2Du, 3u, plpszSubStringArray, *v62, 2u);
  }
  if ( v87 != 5 )
  {
    if ( (_QWORD)xmmword_1800D1100 )
    {
      LOWORD(v105) = 0;
      FormatRRASErrorString(&v105, L"IASResponse = ACCESS_REJECT. Failurereason=0x%x", v83);
LABEL_133:
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasAuthTemplateFunc)(gRasAuthEtwContext, xmmword_1800D1100, &v105);
    }
LABEL_174:
    if ( !v84 )
      goto LABEL_16;
    v64 = RasAuthAttributeCreate();
    v21 = (HLOCAL *)a3;
    *a3 = v64;
    if ( !v64 )
    {
      LastError = GetLastError();
      goto LABEL_17;
    }
    v67 = 0;
    if ( !v84 )
    {
LABEL_201:
      RasAuthAttributesPrint(v66, v65, *a3);
      goto LABEL_17;
    }
    while ( 1 )
    {
      v68 = 0;
      v69 = *(_QWORD *)(v89 + 8LL * v67);
      v70 = *(__m128i *)(v69 + 16);
      v99 = *(LPCWCH *)(v69 + 32);
      v71 = _mm_cvtsi128_si32(v70) - 1;
      if ( !v71 )
        break;
      v72 = v71 - 1;
      if ( !v72 )
        break;
      v73 = v72 - 1;
      if ( !v73 )
        break;
      v74 = v73 - 1;
      if ( !v74 )
      {
        v77 = (_WORD *)_mm_srli_si128(v70, 8).m128i_u64[0];
        LODWORD(v75) = 4;
        v78 = (u_long *)(v77 + 4);
        if ( *v77 != 23 )
          v78 = (u_long *)(v77 + 2);
        v66 = ntohl(*v78);
        goto LABEL_197;
      }
      v66 = (unsigned int)(v74 - 1);
      if ( (_DWORD)v66 )
      {
        if ( (_DWORD)v66 == 1 )
        {
          v66 = (unsigned __int64)v99;
          LODWORD(v75) = _mm_cvtsi128_si32(_mm_srli_si128(v70, 8));
LABEL_197:
          LODWORD(lpWideCharStr) = v75;
          LastError = RasAuthAttributeInsert(
                        v67,
                        *a3,
                        *(_DWORD *)(*(_QWORD *)(v89 + 8LL * v67) + 8LL),
                        v68,
                        (size_t)lpWideCharStr,
                        (LPCWCH)v66);
          if ( LastError )
            goto LABEL_201;
          if ( (_QWORD)xmmword_1800D1100 )
          {
            LOWORD(v105) = 0;
            FormatRRASErrorString(
              &v105,
              L"Received attribute %d",
              *(unsigned int *)(*(_QWORD *)(v89 + 8LL * v67) + 8LL));
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasAuthTemplateFunc)(
              gRasAuthEtwContext,
              xmmword_1800D1100,
              &v105);
          }
        }
      }
      else
      {
        v76 = _mm_srli_si128(v70, 8).m128i_u64[0];
        v66 = v76;
        if ( v76 )
        {
          v75 = -1;
          do
            ++v75;
          while ( *(_BYTE *)(v76 + v75) );
          goto LABEL_197;
        }
        v66 = (unsigned __int64)v99;
        if ( v99 )
        {
          v68 = 1;
          v75 = -1;
          do
            ++v75;
          while ( v99[v75] );
          goto LABEL_197;
        }
      }
      if ( ++v67 >= v84 )
        goto LABEL_201;
    }
    LODWORD(v75) = 4;
    v66 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v70, 8));
    goto LABEL_197;
  }
  LastError = *v62;
  if ( (_QWORD)xmmword_1800D1100 )
  {
    LOWORD(v105) = 0;
    FormatRRASErrorString(&v105, L"IASResponse = DISCARD_PACKET. Failurereason=0x%x", v83);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasAuthTemplateFunc)(gRasAuthEtwContext, xmmword_1800D1100, &v105);
  }
  if ( !LastError )
    goto LABEL_174;
LABEL_16:
  v21 = (HLOCAL *)a3;
LABEL_17:
  FreeAttributes(v91, v97, v24);
  MemFreeIas(v97);
LABEL_18:
  if ( v89 )
  {
    FreeAttributes(v84, v89, v19);
    MemFreeIas(v89);
  }
  if ( LastError )
  {
    if ( *v21 )
    {
      RasAuthAttributeDestroy(*v21);
      *v21 = 0;
    }
  }
  CoUninitialize();
  return LastError;
}

```

## disassembly

```asm
0x18004d13c  mov     [rsp-8+arg_0], rbx
0x18004d141  push    rbp
0x18004d142  push    rsi
0x18004d143  push    rdi
0x18004d144  push    r12
0x18004d146  push    r13
0x18004d148  push    r14
0x18004d14a  push    r15
0x18004d14c  lea     rbp, [rsp-0B90h]
0x18004d154  sub     rsp, 0C90h
0x18004d15b  mov     rax, cs:__security_cookie
0x18004d162  xor     rax, rsp
0x18004d165  mov     [rbp+0BC0h+var_40], rax
0x18004d16c  xor     edi, edi
0x18004d16e  mov     [rsp+0CC0h+var_C68], r8
0x18004d173  lea     rax, g_aszUnauthenticatedUser
0x18004d17a  mov     [rbp+0BC0h+var_C30], rdx
0x18004d17e  mov     [rbp+0BC0h+lpMultiByteStr], rax
0x18004d182  xorps   xmm0, xmm0
0x18004d185  mov     eax, dword ptr cs:aNa; "{NA}"
0x18004d18b  mov     r14, r8
0x18004d18e  mov     dword ptr [rbp+0BC0h+MultiByteStr], eax
0x18004d191  mov     r15, rdx
0x18004d194  mov     al, byte ptr cs:aNa+4; ""
0x18004d19a  mov     r12d, ecx
0x18004d19d  mov     [rbp+0BC0h+MultiByteStr+4], al
0x18004d1a0  xor     edx, edx; Val
0x18004d1a2  xor     eax, eax
0x18004d1a4  mov     [rbp+0BC0h+var_C38], ecx
0x18004d1a7  mov     r8d, 7FCh; Size
0x18004d1ad  mov     [rbp+0BC0h+var_BB3], ax
0x18004d1b1  lea     rcx, [rbp+0BC0h+var_A4C]; void *
0x18004d1b8  mov     [rbp+0BC0h+var_BB1], al
0x18004d1bb  mov     r13, r9
0x18004d1be  mov     [rbp+0BC0h+var_C20], r9
0x18004d1c2  mov     [rsp+0CC0h+var_C50], edi
0x18004d1c6  mov     ebx, edi
0x18004d1c8  mov     [rsp+0CC0h+var_C5C], edi
0x18004d1cc  mov     esi, edi
0x18004d1ce  mov     [rbp+0BC0h+var_C40], rdi
0x18004d1d2  mov     [rbp+0BC0h+var_C28], rdi
0x18004d1d6  mov     [rbp+0BC0h+var_C10], rdi
0x18004d1da  mov     [rsp+0CC0h+var_C58], edi
0x18004d1de  movups  xmmword ptr [rbp+0BC0h+MultiByteStr+5], xmm0
0x18004d1e2  mov     [rsp+0CC0h+var_C60], edi
0x18004d1e6  movups  [rbp+0BC0h+var_BC3], xmm0
0x18004d1ea  mov     [rbp+0BC0h+var_A50], edi
0x18004d1f0  call    memset_0
0x18004d1f5  mov     r8, r15
0x18004d1f8  call    RasAuthAttributesPrint
0x18004d1fd  mov     ecx, r12d
0x18004d200  test    r12d, r12d
0x18004d203  jz      short loc_18004D226
0x18004d205  sub     ecx, 1
0x18004d208  jz      short loc_18004D226
0x18004d20a  sub     ecx, 1
0x18004d20d  jz      short loc_18004D226
0x18004d20f  sub     ecx, 1
0x18004d212  jz      short loc_18004D226
0x18004d214  sub     ecx, 1
0x18004d217  jz      short loc_18004D226
0x18004d219  cmp     ecx, 1
0x18004d21c  jz      short loc_18004D22B
0x18004d21e  lea     eax, [rdi+57h]
0x18004d221  jmp     loc_18004D35D
0x18004d226  mov     edi, 1
0x18004d22b  xor     eax, eax
0x18004d22d  mov     [rsp+0CC0h+var_C70], edi
0x18004d231  mov     [r14], rax
0x18004d234  xor     edx, edx; dwCoInit
0x18004d236  mov     r14d, 2B3h
0x18004d23c  xor     ecx, ecx; pvReserved
0x18004d23e  mov     [r13+0], r14d
0x18004d242  call    cs:__imp_CoInitializeEx
0x18004d249  nop     dword ptr [rax+rax+00h]
0x18004d24e  xor     edx, edx
0x18004d250  test    eax, eax
0x18004d252  jns     short loc_18004D25C
0x18004d254  movzx   eax, ax
0x18004d257  jmp     loc_18004D35D
0x18004d25c  mov     ecx, edx
0x18004d25e  mov     [rsp+0CC0h+var_C54], edx
0x18004d262  cmp     [r15], edx
0x18004d265  jz      short loc_18004D278
0x18004d267  inc     ecx
0x18004d269  mov     eax, ecx
0x18004d26b  add     rax, rax
0x18004d26e  cmp     [r15+rax*8], edx
0x18004d272  jnz     short loc_18004D267
0x18004d274  mov     [rsp+0CC0h+var_C54], ecx
0x18004d278  lea     r13d, [rcx+1]
0x18004d27c  cmp     edi, 1
0x18004d27f  cmovnz  r13d, ecx
0x18004d283  add     r13d, 2
0x18004d287  mov     [rbp+0BC0h+var_C34], r13d
0x18004d28b  lea     ecx, ds:0[r13*8]
0x18004d293  call    cs:__imp_MemAllocIas
0x18004d29a  nop     dword ptr [rax+rax+00h]
0x18004d29f  mov     [rbp+0BC0h+var_C08], rax
0x18004d2a3  mov     rdi, rax
0x18004d2a6  test    rax, rax
0x18004d2a9  jnz     short loc_18004D2B5
0x18004d2ab  mov     r12, [rsp+0CC0h+var_C68]
0x18004d2b0  lea     esi, [rax+8]
0x18004d2b3  jmp     short loc_18004D30E
0x18004d2b5  mov     r8d, r13d
0x18004d2b8  xor     edx, edx; Val
0x18004d2ba  shl     r8, 3; Size
0x18004d2be  mov     rcx, rdi; void *
0x18004d2c1  call    memset_0
0x18004d2c6  mov     rdx, rdi
0x18004d2c9  mov     ecx, r13d
0x18004d2cc  call    cs:__imp_AllocateAttributes
0x18004d2d3  nop     dword ptr [rax+rax+00h]
0x18004d2d8  xor     r8d, r8d
0x18004d2db  test    eax, eax
0x18004d2dd  jns     loc_18004D388
0x18004d2e3  movzx   esi, ax
0x18004d2e6  mov     r12, [rsp+0CC0h+var_C68]
0x18004d2eb  mov     rdx, [rbp+0BC0h+var_C08]
0x18004d2ef  mov     ecx, [rbp+0BC0h+var_C34]
0x18004d2f2  call    cs:__imp_FreeAttributes
0x18004d2f9  nop     dword ptr [rax+rax+00h]
0x18004d2fe  mov     rcx, [rbp+0BC0h+var_C08]
0x18004d302  call    cs:__imp_MemFreeIas
0x18004d309  nop     dword ptr [rax+rax+00h]
0x18004d30e  mov     rdx, [rbp+0BC0h+var_C40]
0x18004d312  xor     ebx, ebx
0x18004d314  test    rdx, rdx
0x18004d317  jz      short loc_18004D339
0x18004d319  mov     ecx, [rsp+0CC0h+var_C5C]
0x18004d31d  call    cs:__imp_FreeAttributes
0x18004d324  nop     dword ptr [rax+rax+00h]
0x18004d329  mov     rcx, [rbp+0BC0h+var_C40]
0x18004d32d  call    cs:__imp_MemFreeIas
0x18004d334  nop     dword ptr [rax+rax+00h]
0x18004d339  test    esi, esi
0x18004d33b  jz      short loc_18004D34F
0x18004d33d  mov     rcx, [r12]; hMem
0x18004d341  test    rcx, rcx
0x18004d344  jz      short loc_18004D34F
0x18004d346  call    RasAuthAttributeDestroy
0x18004d34b  mov     [r12], rbx
0x18004d34f  call    cs:__imp_CoUninitialize
0x18004d356  nop     dword ptr [rax+rax+00h]
0x18004d35b  mov     eax, esi
0x18004d35d  mov     rcx, [rbp+0BC0h+var_40]
0x18004d364  xor     rcx, rsp; StackCookie
0x18004d367  call    __security_check_cookie
0x18004d36c  mov     rbx, [rsp+0CC0h+arg_0]
0x18004d374  add     rsp, 0C90h
0x18004d37b  pop     r15
0x18004d37d  pop     r14
0x18004d37f  pop     r13
0x18004d381  pop     r12
0x18004d383  pop     rdi
0x18004d384  pop     rsi
0x18004d385  pop     rbp
0x18004d386  retn
0x18004d388  mov     r15d, 8
0x18004d38e  mov     ecx, r8d
0x18004d391  mov     [rsp+0CC0h+var_C6C], ecx
0x18004d395  cmp     [rsp+0CC0h+var_C54], r8d
0x18004d39a  jbe     loc_18004D531
0x18004d3a0  mov     r12, [rbp+0BC0h+var_C30]
0x18004d3a4  add     r12, r15
0x18004d3a7  mov     [rsp+0CC0h+var_C48], rdi
0x18004d3ac  mov     ecx, [r12-8]
0x18004d3b1  cmp     ecx, 37h ; '7'
0x18004d3b4  jg      loc_18004D637
0x18004d3ba  jz      loc_18004D49D
0x18004d3c0  cmp     ecx, 1Ah
0x18004d3c3  jg      loc_18004D5BB
0x18004d3c9  jz      loc_18004D6D9
0x18004d3cf  cmp     ecx, 9
0x18004d3d2  jg      loc_18004D59B
0x18004d3d8  jz      loc_18004D49D
0x18004d3de  mov     edx, ecx
0x18004d3e0  sub     edx, 2
0x18004d3e3  jz      loc_18004D591
0x18004d3e9  sub     edx, 1
0x18004d3ec  jz      loc_18004D591
0x18004d3f2  sub     edx, 1
0x18004d3f5  jz      short loc_18004D417
0x18004d3f7  sub     edx, 1
0x18004d3fa  jz      loc_18004D48C
0x18004d400  sub     edx, 1
0x18004d403  jz      loc_18004D48C
0x18004d409  sub     edx, 1
0x18004d40c  jz      short loc_18004D48C
0x18004d40e  cmp     edx, 1
0x18004d411  jnz     loc_18004D751
0x18004d417  mov     ecx, 80h
0x18004d41c  call    cs:__imp_MemAllocIas
0x18004d423  nop     dword ptr [rax+rax+00h]
0x18004d428  mov     rdi, rax
0x18004d42b  test    rax, rax
0x18004d42e  jz      loc_18004D7E0
0x18004d434  xor     edx, edx; Val
0x18004d436  mov     r8d, 80h; Size
0x18004d43c  mov     rcx, rax; void *
0x18004d43f  call    memset_0
0x18004d444  mov     ecx, [r12]; hostlong
0x18004d448  call    cs:__imp_htonl
0x18004d44f  nop     dword ptr [rax+rax+00h]
0x18004d454  mov     rdx, [rsp+0CC0h+var_C48]
0x18004d459  xor     r8d, r8d
0x18004d45c  mov     [rdi+4], eax
0x18004d45f  xor     eax, eax
0x18004d461  mov     dword ptr [rdi], 2
0x18004d467  mov     [rdi+8], rax
0x18004d46b  mov     rax, [rdx]
0x18004d46e  mov     dword ptr [rax+10h], 4
0x18004d475  mov     rax, [rdx]
0x18004d478  mov     [rax+18h], rdi
0x18004d47c  cmp     dword ptr [r12-8], 4
0x18004d482  jnz     short loc_18004D487
0x18004d484  mov     rbx, rdi
0x18004d487  mov     rdi, rdx
0x18004d48a  jmp     short loc_18004D4B1
0x18004d48c  cmp     ecx, 7
0x18004d48f  jnz     short loc_18004D49D
0x18004d491  cmp     qword ptr [r12], 3
0x18004d496  jnz     short loc_18004D49D
0x18004d498  mov     [rsp+0CC0h+var_C70], r8d
0x18004d49d  mov     rax, [rdi]
0x18004d4a0  mov     dword ptr [rax+10h], 2
0x18004d4a7  mov     rcx, [rdi]
0x18004d4aa  mov     eax, [r12]
0x18004d4ae  mov     [rcx+18h], eax
0x18004d4b1  cmp     qword ptr cs:xmmword_1800D1100, r8
0x18004d4b8  mov     rcx, [rdi]
0x18004d4bb  mov     eax, [r12-8]
0x18004d4c0  mov     [rcx+8], eax
0x18004d4c3  jz      short loc_18004D509
0x18004d4c5  mov     word ptr [rbp+0BC0h+var_A50], r8w
0x18004d4cd  lea     rdx, aInsertingAttri; "Inserting attribute type %d"
0x18004d4d4  mov     r8d, [r12-8]
0x18004d4d9  lea     rcx, [rbp+0BC0h+var_A50]
0x18004d4e0  call    FormatRRASErrorString
0x18004d4e5  mov     rdx, qword ptr cs:xmmword_1800D1100
0x18004d4ec  lea     r8, [rbp+0BC0h+var_A50]
0x18004d4f3  mov     rcx, cs:gRasAuthEtwContext
0x18004d4fa  mov     rax, cs:gRasAuthTemplateFunc
0x18004d501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d506  xor     r8d, r8d
0x18004d509  mov     ecx, [rsp+0CC0h+var_C6C]
0x18004d50d  add     rdi, r15
0x18004d510  inc     ecx
0x18004d512  mov     [rsp+0CC0h+var_C48], rdi
0x18004d517  add     r12, 10h
0x18004d51b  mov     [rsp+0CC0h+var_C6C], ecx
0x18004d51f  cmp     ecx, [rsp+0CC0h+var_C54]
0x18004d523  jb      loc_18004D3AC
0x18004d529  mov     rdi, [rbp+0BC0h+var_C08]
0x18004d52d  mov     r12d, [rbp+0BC0h+var_C38]
0x18004d531  cmp     [rsp+0CC0h+var_C70], 1
0x18004d536  jnz     loc_18004D820
0x18004d53c  mov     rax, [rdi+rcx*8]
0x18004d540  mov     edx, 2
0x18004d545  mov     dword ptr [rax+8], 28h ; '('
0x18004d54c  mov     rax, [rdi+rcx*8]
0x18004d550  mov     [rax+10h], edx
0x18004d553  test    r12d, r12d
0x18004d556  jz      loc_18004D80B
0x18004d55c  sub     r12d, 1
0x18004d560  jz      loc_18004D802
0x18004d566  sub     r12d, 1
0x18004d56a  jz      loc_18004D7F5
0x18004d570  sub     r12d, 1
0x18004d574  jz      loc_18004D7E8
0x18004d57a  cmp     r12d, 1
0x18004d57e  jnz     loc_18004D816
0x18004d584  mov     rax, [rdi+rcx*8]
0x18004d588  mov     [rax+18h], r15d
0x18004d58c  jmp     loc_18004D816
0x18004d591  mov     eax, 1
0x18004d596  jmp     loc_18004D6CB
0x18004d59b  sub     ecx, 0Ah
0x18004d59e  jz      loc_18004D49D
0x18004d5a4  sub     ecx, 2
0x18004d5a7  jz      loc_18004D49D
0x18004d5ad  sub     ecx, 1
0x18004d5b0  jz      loc_18004D49D
0x18004d5b6  sub     ecx, 1
0x18004d5b9  jmp     short loc_18004D5E4
0x18004d5bb  cmp     ecx, 2Bh ; '+'
0x18004d5be  jg      short loc_18004D5F8
0x18004d5c0  jz      loc_18004D49D
0x18004d5c6  sub     ecx, 1Bh
0x18004d5c9  jz      loc_18004D49D
0x18004d5cf  sub     ecx, 1
0x18004d5d2  jz      loc_18004D49D
0x18004d5d8  sub     ecx, 1
0x18004d5db  jz      loc_18004D49D
0x18004d5e1  sub     ecx, 0Bh
0x18004d5e4  jz      loc_18004D49D
0x18004d5ea  sub     ecx, 1
0x18004d5ed  jz      loc_18004D49D
0x18004d5f3  cmp     ecx, 1
  ... truncated ...
```

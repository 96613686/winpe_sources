# IASSendReceiveAttributes

- ea: `0x18004bbc8`
- end: `0x18004c8a7`
- name: `IASSendReceiveAttributes`
- size: `3295`
- prototype: `__int64 __fastcall(unsigned int, _DWORD *, HLOCAL *, int *)`
- caller_count: `6`
- callee_count: `11`
- tags: ``

## callers

- `0x18004c920`
- `0x18004ca50`
- `0x18004cac0`
- `0x18004cb30`
- `0x18004cba0`
- `0x18004cc60`

## callees

- `0x180002ba6`
- `0x180045f14`
- `0x18004bbc8`
- `0x180071cec`
- `0x180072138`
- `0x1800721bc`
- `0x180072348`
- `0x1800725b0`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18004c4fb`
- `KERNEL32!MultiByteToWideChar` at `0x18004c51e`
- `KERNEL32!MultiByteToWideChar` at `0x18004c615`
- `KERNEL32!MultiByteToWideChar` at `0x18004c4fb`
- `KERNEL32!MultiByteToWideChar` at `0x18004c51e`
- `KERNEL32!MultiByteToWideChar` at `0x18004c615`
- `KERNEL32!GetLastError` at `0x18004c750`
- `KERNEL32!GetLastError` at `0x18004c750`
- `ole32!CoUninitialize` at `0x18004c18e`
- `ole32!CoUninitialize` at `0x18004c18e`
- `ole32!CoInitializeEx` at `0x18004bcb6`
- `ole32!CoInitializeEx` at `0x18004bcb6`
- `rtutils!RouterLogEventStringW` at `0x18004c673`
- `rtutils!RouterLogEventStringW` at `0x18004c673`
- `iashlpr!FreeAttributes` at `0x18004c148`
- `iashlpr!FreeAttributes` at `0x18004c167`
- `iashlpr!FreeAttributes` at `0x18004c148`
- `iashlpr!FreeAttributes` at `0x18004c167`
- `iashlpr!MemFreeIas` at `0x18004c151`
- `iashlpr!MemFreeIas` at `0x18004c172`
- `iashlpr!MemFreeIas` at `0x18004c151`
- `iashlpr!MemFreeIas` at `0x18004c172`
- `iashlpr!DoRequest` at `0x18004c39b`
- `iashlpr!DoRequest` at `0x18004c39b`
- `iashlpr!AllocateAttributes` at `0x18004bd2c`
- `iashlpr!AllocateAttributes` at `0x18004bd2c`
- `iashlpr!MemAllocIas` at `0x18004bcfc`
- `iashlpr!MemAllocIas` at `0x18004bde7`
- `iashlpr!MemAllocIas` at `0x18004c087`
- `iashlpr!MemAllocIas` at `0x18004c0d4`
- `iashlpr!MemAllocIas` at `0x18004c241`
- `iashlpr!MemAllocIas` at `0x18004c2eb`
- `iashlpr!MemAllocIas` at `0x18004bcfc`
- `iashlpr!MemAllocIas` at `0x18004bde7`
- `iashlpr!MemAllocIas` at `0x18004c087`
- `iashlpr!MemAllocIas` at `0x18004c0d4`
- `iashlpr!MemAllocIas` at `0x18004c241`
- `iashlpr!MemAllocIas` at `0x18004c2eb`
- `WS2_32!__imp_htonl` at `0x18004be0e`
- `WS2_32!__imp_htonl` at `0x18004be0e`
- `WS2_32!__imp_ntohl` at `0x18004c7fc`
- `WS2_32!__imp_ntohl` at `0x18004c7fc`

## string_xrefs

- `0x18004c717`: `IASResponse = ACCESS_ACCEPT`
- `0x18004c48e`: `IASResponse = ACCESS_CHALLENGE`
- `0x18004c6e4`: `IASResponse = ACCESS_REJECT. Failurereason=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IASSendReceiveAttributes(unsigned int a1, _DWORD *a2, HLOCAL *a3, int *a4)
{
  HLOCAL *v4; // r12
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 result; // rax
  int v11; // esi
  int v12; // r14d
  unsigned int v13; // edi
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  _QWORD *v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  _QWORD *v19; // r15
  DWORD LastError; // ebx
  int Attributes; // eax
  __int64 v22; // r8
  void *v23; // r9
  __int64 v24; // r12
  _OWORD *v25; // rbx
  int v26; // r8d
  __int64 v27; // rdi
  unsigned int *v28; // r12
  int v29; // ecx
  _DWORD *v30; // rax
  _DWORD *v31; // rsi
  u_long v32; // eax
  char *v33; // rdi
  __int64 v34; // r8
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  bool v38; // zf
  int v39; // ecx
  unsigned __int8 *v40; // rdx
  __int64 v41; // rax
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  int v45; // ecx
  bool v46; // zf
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  int v56; // ecx
  int v57; // ecx
  int v58; // ecx
  _QWORD *v59; // rax
  size_t v60; // rsi
  void *v61; // rcx
  unsigned int v62; // edi
  unsigned int v63; // r13d
  unsigned int v64; // r13d
  unsigned int v65; // r13d
  _OWORD *v66; // rax
  __int64 v67; // rax
  __int64 v68; // rdx
  const void **v69; // r13
  unsigned int v70; // ebx
  void *v71; // rax
  int v72; // eax
  DWORD *v73; // rdi
  const CHAR *v74; // r8
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rcx
  unsigned int v78; // edi
  int v79; // r14d
  _WORD *v80; // r8
  unsigned __int64 v81; // r9
  __int64 v82; // rbx
  __int64 v83; // rcx
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-E0h]
  int v85; // [rsp+50h] [rbp-B0h]
  int v86; // [rsp+54h] [rbp-ACh]
  unsigned int v87; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v88; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 *v89; // [rsp+60h] [rbp-A0h]
  unsigned int v90; // [rsp+68h] [rbp-98h] BYREF
  __int64 v91; // [rsp+70h] [rbp-90h] BYREF
  int v92; // [rsp+78h] [rbp-88h]
  unsigned int v93; // [rsp+7Ch] [rbp-84h]
  unsigned int v94; // [rsp+80h] [rbp-80h]
  const void **v95; // [rsp+88h] [rbp-78h]
  int *v96; // [rsp+90h] [rbp-70h]
  LPCCH lpMultiByteStr; // [rsp+98h] [rbp-68h]
  unsigned int *v98; // [rsp+A0h] [rbp-60h]
  _DWORD *v99; // [rsp+A8h] [rbp-58h]
  _QWORD *v100; // [rsp+B0h] [rbp-50h]
  LPWSTR plpszSubStringArray[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v102; // [rsp+C8h] [rbp-38h]
  __int64 v103; // [rsp+D8h] [rbp-28h]
  _OWORD MultiByteStr[3]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v105[32]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR v106[40]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR v107[104]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v108; // [rsp+270h] [rbp+170h] BYREF
  char v109[2044]; // [rsp+274h] [rbp+174h] BYREF
  WCHAR WideCharStr[264]; // [rsp+A70h] [rbp+970h] BYREF

  strcpy((char *)MultiByteStr, "{NA}");
  v4 = a3;
  v89 = (__int64 *)a3;
  v99 = a2;
  v96 = a4;
  v90 = 0;
  v88 = 0;
  v91 = 0;
  memset((char *)MultiByteStr + 5, 0, 35);
  v87 = 0;
  v108 = 0;
  memset_0(v109, 0, sizeof(v109));
  RasAuthAttributesPrint(v9, v8, a2);
  if ( a1 <= 4 )
  {
    v11 = 1;
  }
  else
  {
    if ( a1 != 5 )
      return 87;
    v11 = 0;
  }
  *v4 = 0;
  v12 = 691;
  *a4 = 691;
  v85 = v11;
  LODWORD(result) = CoInitializeEx(0, 0);
  if ( (int)result < 0 )
    return (unsigned __int16)result;
  v13 = 0;
  v93 = 0;
  if ( *a2 )
  {
    do
      ++v13;
    while ( a2[4 * v13] );
    v93 = v13;
  }
  v14 = v13 + 1;
  if ( v11 != 1 )
    v14 = v13;
  v15 = v14 + 2;
  v94 = v15;
  v16 = (_QWORD *)MemAllocIas(8 * v15);
  v100 = v16;
  v19 = v16;
  if ( !v16 )
  {
    LastError = 8;
    goto LABEL_94;
  }
  memset_0(v16, 0, 8LL * v15);
  Attributes = AllocateAttributes(v15, v19);
  v23 = 0;
  if ( Attributes < 0 )
  {
    LastError = (unsigned __int16)Attributes;
    goto LABEL_93;
  }
  v24 = 0;
  lpMultiByteStr = &g_aszUnauthenticatedUser;
  v25 = 0;
  v92 = 0;
  v26 = 0;
  v95 = 0;
  v98 = 0;
  v86 = 0;
  if ( v13 )
  {
    while ( 1 )
    {
      v27 = (unsigned int)v24;
      v28 = &v99[4 * v24];
      v29 = *v28;
      if ( (int)*v28 > 55 )
      {
        v52 = v29 - 61;
        if ( !v52 )
          goto LABEL_37;
        v53 = v52 - 1;
        if ( !v53 )
          goto LABEL_37;
        v54 = v53 - 2;
        if ( !v54 )
          goto LABEL_37;
        v55 = v54 - 1;
        if ( !v55 )
          goto LABEL_37;
        v56 = v55 - 10;
        if ( !v56 )
          goto LABEL_37;
        v57 = v56 - 1;
        if ( !v57 )
          goto LABEL_37;
        v58 = v57 - 3;
        if ( v58 )
        {
          if ( (unsigned int)(v58 - 17) <= 1 )
          {
            v59 = (_QWORD *)MemAllocIas(8);
            v23 = 0;
            if ( !v59 )
              goto LABEL_91;
            v33 = (char *)&v19[v27];
            *v59 = **((_QWORD **)v28 + 1);
            *(_DWORD *)(*(_QWORD *)v33 + 16LL) = 6;
            *(_QWORD *)(*(_QWORD *)v33 + 32LL) = v59;
            *(_DWORD *)(*(_QWORD *)v33 + 24LL) = 8;
            goto LABEL_38;
          }
        }
        else
        {
          v85 = 0;
        }
      }
      else
      {
        if ( v29 == 55 )
          goto LABEL_37;
        if ( v29 > 26 )
        {
          if ( v29 <= 43 )
          {
            if ( v29 == 43 )
              goto LABEL_37;
            v42 = v29 - 27;
            if ( !v42 )
              goto LABEL_37;
            v43 = v42 - 1;
            if ( !v43 )
              goto LABEL_37;
            v44 = v43 - 1;
            if ( !v44 )
              goto LABEL_37;
            v39 = v44 - 11;
            v38 = v39 == 0;
            goto LABEL_63;
          }
          v47 = v29 - 45;
          if ( !v47 )
            goto LABEL_37;
          v48 = v47 - 1;
          if ( !v48 )
            goto LABEL_37;
          v49 = v48 - 1;
          if ( !v49 )
            goto LABEL_37;
          v50 = v49 - 1;
          if ( !v50 )
            goto LABEL_37;
          v51 = v50 - 1;
          if ( !v51 )
            goto LABEL_37;
          v46 = v51 == 2;
LABEL_72:
          if ( v46 )
            goto LABEL_37;
          goto LABEL_85;
        }
        if ( v29 != 26 )
        {
          if ( v29 <= 9 )
          {
            switch ( v29 )
            {
              case 9:
                goto LABEL_37;
              case 2:
              case 3:
                v86 = 1;
                v85 = 0;
                break;
              case 4:
                goto LABEL_31;
              case 5:
              case 6:
              case 7:
                if ( v29 == 7 && *((_QWORD *)v28 + 1) == 3 )
                  v85 = 0;
LABEL_37:
                v33 = (char *)&v19[v27];
                *(_DWORD *)(*(_QWORD *)v33 + 16LL) = 2;
                *(_DWORD *)(*(_QWORD *)v33 + 24LL) = v28[2];
                goto LABEL_38;
              case 8:
LABEL_31:
                v30 = (_DWORD *)MemAllocIas(128);
                v31 = v30;
                if ( !v30 )
                  goto LABEL_91;
                memset_0(v30, 0, 0x80u);
                v32 = htonl(v28[2]);
                *v31 = 2;
                v33 = (char *)&v19[v27];
                v31[1] = v32;
                *((_QWORD *)v31 + 1) = 0;
                *(_DWORD *)(*(_QWORD *)v33 + 16LL) = 4;
                *(_QWORD *)(*(_QWORD *)v33 + 24LL) = v31;
                if ( *v28 == 4 )
                  v25 = v31;
                goto LABEL_38;
              case 1:
                lpMultiByteStr = (LPCCH)*((_QWORD *)v28 + 1);
                break;
            }
            goto LABEL_85;
          }
          v35 = v29 - 10;
          if ( !v35 )
            goto LABEL_37;
          v36 = v35 - 2;
          if ( !v36 )
            goto LABEL_37;
          v37 = v36 - 1;
          if ( !v37 )
            goto LABEL_37;
          v39 = v37 - 1;
          v38 = v39 == 0;
LABEL_63:
          if ( v38 )
            goto LABEL_37;
          v45 = v39 - 1;
          if ( !v45 )
            goto LABEL_37;
          v46 = v45 == 1;
          goto LABEL_72;
        }
        v86 = v26;
        v85 = v11;
        if ( v28[1] >= 8
          && (v40 = (unsigned __int8 *)*((_QWORD *)v28 + 1),
              v40[3] + (*v40 << 24) + (v40[2] << 8) + (v40[1] << 16) == 311) )
        {
          if ( v40[4] == 1 || (unsigned int)v40[4] - 3 <= 1 )
            v85 = 0;
        }
        else
        {
          v85 = v11;
        }
        v41 = *((_QWORD *)v28 + 1);
        if ( *(_BYTE *)(v41 + 4) == 56 )
        {
          v86 = v26;
          MultiByteStr[0] = *(_OWORD *)(v41 + 6);
          MultiByteStr[1] = *(_OWORD *)(v41 + 22);
          *(_QWORD *)&MultiByteStr[2] = *(_QWORD *)(v41 + 38);
        }
      }
LABEL_85:
      v60 = v28[1];
      v61 = (void *)MemAllocIas(v60);
      if ( !v61 )
        goto LABEL_91;
      if ( *v28 == 32 )
      {
        v95 = (const void **)v28;
      }
      else if ( *v28 == 31 )
      {
        v98 = v28;
      }
      v33 = (char *)&v19[v27];
      *(_DWORD *)(*(_QWORD *)v33 + 16LL) = 6;
      *(_DWORD *)(*(_QWORD *)v33 + 24LL) = v60;
      *(_QWORD *)(*(_QWORD *)v33 + 32LL) = v61;
      memcpy_0(v61, *((const void **)v28 + 1), v60);
LABEL_38:
      v38 = (_QWORD)xmmword_1800CA100 == 0;
      *(_DWORD *)(*(_QWORD *)v33 + 8LL) = *v28;
      if ( !v38 )
      {
        v34 = *v28;
        LOWORD(v108) = 0;
        FormatRRASErrorString(&v108, L"Inserting attribute type %d", v34);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasAuthTemplateFunc)(
          gRasAuthEtwContext,
          xmmword_1800CA100,
          &v108);
      }
      v11 = v85;
      v24 = (unsigned int)(v92 + 1);
      v92 = v24;
      if ( (unsigned int)v24 >= v93 )
        break;
      v26 = v86;
    }
  }
  v62 = v94;
  if ( v11 == 1 )
  {
    *(_DWORD *)(v19[v24] + 8LL) = 40;
    *(_DWORD *)(v19[v24] + 16LL) = 2;
    if ( a1 )
    {
      v63 = a1 - 1;
      if ( v63 )
      {
        v64 = v63 - 1;
        if ( v64 )
        {
          v65 = v64 - 1;
          if ( v65 )
          {
            if ( v65 == 1 )
              *(_DWORD *)(v19[v24] + 24LL) = 8;
          }
          else
          {
            *(_DWORD *)(v19[v24] + 24LL) = 7;
          }
        }
        else
        {
          *(_DWORD *)(v19[v24] + 24LL) = 3;
        }
      }
      else
      {
        *(_DWORD *)(v19[v24] + 24LL) = 2;
      }
    }
    else
    {
      *(_DWORD *)(v19[v24] + 24LL) = 1;
    }
    v24 = (unsigned int)(v24 + 1);
  }
  if ( v25 )
  {
    v66 = (_OWORD *)MemAllocIas(128);
    if ( !v66 )
      goto LABEL_91;
    *v66 = *v25;
    v66[1] = v25[1];
    v66[2] = v25[2];
    v66[3] = v25[3];
    v66[4] = v25[4];
    v66[5] = v25[5];
    v66[6] = v25[6];
    v66[7] = v25[7];
    *(_DWORD *)(v19[v24] + 16LL) = 4;
    *(_QWORD *)(v19[v24] + 24LL) = v66;
    v67 = v19[v24];
    v24 = (unsigned int)(v24 + 1);
    v68 = *((_QWORD *)&xmmword_1800CA100 + 1);
    *(_DWORD *)(v67 + 8) = 4108;
    if ( v68 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasAuthTemplateFunc)(
        gRasAuthEtwContext,
        v68,
        L"Inserting attribute type 4108");
  }
  else
  {
    --v62;
  }
  v69 = v95;
  if ( !v95 )
  {
    --v62;
    goto LABEL_122;
  }
  v70 = *((_DWORD *)v95 + 1);
  v71 = (void *)MemAllocIas(v70);
  v23 = v71;
  if ( !v71 )
  {
LABEL_91:
    LastError = 8;
LABEL_92:
    v4 = (HLOCAL *)v89;
    goto LABEL_93;
  }
  *(_DWORD *)(v19[v24] + 8LL) = 4128;
  *(_DWORD *)(v19[v24] + 16LL) = 6;
  *(_DWORD *)(v19[v24] + 24LL) = v70;
  *(_QWORD *)(v19[v24] + 32LL) = v71;
  memcpy_0(v71, v69[1], v70);
  if ( *((_QWORD *)&xmmword_1800CA100 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasAuthTemplateFunc)(
      gRasAuthEtwContext,
      *((_QWORD *)&xmmword_1800CA100 + 1),
      L"Inserting attribute type 4128");
LABEL_122:
  v72 = DoRequest(v62, v19, &v88, &v91, v11, &v90, 5, &v87, 1);
  if ( v72 < 0 )
  {
    LastError = (unsigned __int16)v72;
    if ( (_QWORD)xmmword_1800CA100 )
    {
      LOWORD(v108) = 0;
      FormatRRASErrorString(&v108, L"IAS->DoRequest failed with %d", (unsigned __int16)v72);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasAuthTemplateFunc)(gRasAuthEtwContext, xmmword_1800CA100, &v108);
    }
    goto LABEL_92;
  }
  v22 = v90;
  LastError = 0;
  if ( v90 == 1 )
  {
    if ( *((_QWORD *)&xmmword_1800CA100 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasAuthTemplateFunc)(
        gRasAuthEtwContext,
        *((_QWORD *)&xmmword_1800CA100 + 1),
        L"IASResponse = ACCESS_ACCEPT");
    *v96 = 0;
    goto LABEL_172;
  }
  if ( v90 != 2 )
  {
    if ( v90 == 3 )
    {
      if ( *((_QWORD *)&xmmword_1800CA100 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasAuthTemplateFunc)(
          gRasAuthEtwContext,
          *((_QWORD *)&xmmword_1800CA100 + 1),
          L"IASResponse = ACCESS_CHALLENGE");
      if ( v86 != 1 )
        v12 = 0;
      *v96 = v12;
      goto LABEL_172;
    }
    if ( v90 != 5 )
    {
      if ( !(_QWORD)xmmword_1800CA100 )
        goto LABEL_172;
      LOWORD(v108) = 0;
      FormatRRASErrorString(&v108, L"IASResponse = %d, FailureReason = 0x%x", v90, v87);
      goto LABEL_131;
    }
  }
  v103 = 0;
  *(_OWORD *)plpszSubStringArray = 0;
  v102 = 0;
  memset_0(v105, 0, sizeof(v105));
  MultiByteToWideChar(0, 0, lpMultiByteStr, -1, WideCharStr, 257);
  MultiByteToWideChar(0, 0, (LPCCH)MultiByteStr, -1, v106, 40);
  if ( (int)v87 <= 65 )
  {
    switch ( v87 )
    {
      case 0x41u:
        v12 = 649;
        goto LABEL_157;
      case 0x10u:
        goto LABEL_157;
      case 0x11u:
        v12 = 709;
        goto LABEL_157;
      case 0x22u:
        v12 = 647;
        goto LABEL_157;
      case 0x23u:
        v12 = 708;
        goto LABEL_157;
      case 0x25u:
LABEL_144:
        v12 = 940;
        goto LABEL_157;
    }
    goto LABEL_153;
  }
  switch ( v87 )
  {
    case 'B':
      v12 = 942;
      break;
    case 'D':
      goto LABEL_144;
    case 'F':
      v12 = 941;
      break;
    case '`':
      v12 = 930;
      break;
    default:
LABEL_153:
      v12 = 812;
      break;
  }
LABEL_157:
  v73 = (DWORD *)v96;
  *v96 = v12;
  StringCchPrintfW(v105, 0x20u, L"0x%x");
  plpszSubStringArray[0] = v106;
  plpszSubStringArray[1] = WideCharStr;
  if ( v98 )
  {
    v74 = (const CHAR *)*((_QWORD *)v98 + 1);
    *(_QWORD *)&v102 = v107;
    *((_QWORD *)&v102 + 1) = v105;
    MultiByteToWideChar(0, 0, v74, -1, v107, 100);
    if ( (unsigned int)g_LoggingLevel > 1 )
      RouterLogEventStringW(g_hEventLog, 2u, 0x4F2Fu, 4u, plpszSubStringArray, *v73, 3u);
  }
  else
  {
    *(_QWORD *)&v102 = v105;
    if ( (unsigned int)g_LoggingLevel > 1 )
      RouterLogEventStringW(g_hEventLog, 2u, 0x4F2Du, 3u, plpszSubStringArray, *v73, 2u);
  }
  if ( v90 == 5 )
  {
    LastError = *v73;
    if ( (_QWORD)xmmword_1800CA100 )
    {
      LOWORD(v108) = 0;
      FormatRRASErrorString(&v108, L"IASResponse = DISCARD_PACKET. Failurereason=0x%x", v87);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasAuthTemplateFunc)(gRasAuthEtwContext, xmmword_1800CA100, &v108);
    }
    if ( LastError )
      goto LABEL_92;
  }
  else if ( (_QWORD)xmmword_1800CA100 )
  {
    LOWORD(v108) = 0;
    FormatRRASErrorString(&v108, L"IASResponse = ACCESS_REJECT. Failurereason=0x%x", v87);
LABEL_131:
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasAuthTemplateFunc)(gRasAuthEtwContext, xmmword_1800CA100, &v108);
  }
LABEL_172:
  if ( !v88 )
    goto LABEL_92;
  v75 = RasAuthAttributeCreate();
  v4 = (HLOCAL *)v89;
  *v89 = v75;
  if ( !v75 )
  {
    LastError = GetLastError();
    goto LABEL_93;
  }
  v78 = 0;
  if ( !v88 )
    goto LABEL_200;
  do
  {
    v79 = 0;
    v77 = *(_QWORD *)(v91 + 8LL * v78);
    v80 = *(_WORD **)(v77 + 24);
    v81 = *(_QWORD *)(v77 + 32);
    if ( *(_DWORD *)(v77 + 16) == 1 || *(_DWORD *)(v77 + 16) == 2 || *(_DWORD *)(v77 + 16) == 3 )
    {
      LODWORD(v82) = 4;
      v81 = (unsigned int)v80;
    }
    else if ( *(_DWORD *)(v77 + 16) == 4 )
    {
      v83 = 4;
      LODWORD(v82) = 4;
      if ( *v80 != 23 )
        v83 = 2;
      v81 = ntohl(*(_DWORD *)&v80[v83]);
    }
    else
    {
      v76 = (unsigned int)(*(_DWORD *)(v77 + 16) - 5);
      if ( *(_DWORD *)(v77 + 16) == 5 )
      {
        if ( v80 )
        {
          v82 = -1;
          do
            ++v82;
          while ( *((_BYTE *)v80 + v82) );
          v81 = *(_QWORD *)(v77 + 24);
        }
        else
        {
          if ( !v81 )
            goto LABEL_198;
          v82 = -1;
          do
            ++v82;
          while ( *(_WORD *)(v81 + 2 * v82) );
          v79 = 1;
        }
      }
      else
      {
        if ( *(_DWORD *)(v77 + 16) != 6 )
          goto LABEL_198;
        LODWORD(v82) = *(_QWORD *)(v77 + 24);
      }
    }
    LODWORD(lpWideCharStr) = v82;
    LastError = RasAuthAttributeInsert(
                  v78,
                  (int)*v4,
                  *(_DWORD *)(*(_QWORD *)(v91 + 8LL * v78) + 8LL),
                  v79,
                  (size_t)lpWideCharStr,
                  (LPCWCH)v81);
    if ( LastError )
      break;
    if ( (_QWORD)xmmword_1800CA100 )
    {
      LOWORD(v108) = 0;
      FormatRRASErrorString(&v108, L"Received attribute %d", *(unsigned int *)(*(_QWORD *)(v91 + 8LL * v78) + 8LL));
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasAuthTemplateFunc)(gRasAuthEtwContext, xmmword_1800CA100, &v108);
    }
LABEL_198:
    ++v78;
  }
  while ( v78 < v88 );
  v19 = v100;
LABEL_200:
  RasAuthAttributesPrint(v77, v76, *v4);
LABEL_93:
  FreeAttributes(v94, v19, v22, v23);
  MemFreeIas(v19);
LABEL_94:
  if ( v91 )
  {
    FreeAttributes(v88, v91, v17, v18);
    MemFreeIas(v91);
  }
  if ( LastError )
  {
    if ( *v4 )
    {
      RasAuthAttributeDestroy(*v4);
      *v4 = 0;
    }
  }
  CoUninitialize();
  return LastError;
}

```

## disassembly

```asm
0x18004bbc8  mov     [rsp-8+arg_0], rbx
0x18004bbcd  push    rbp
0x18004bbce  push    rsi
0x18004bbcf  push    rdi
0x18004bbd0  push    r12
0x18004bbd2  push    r13
0x18004bbd4  push    r14
0x18004bbd6  push    r15
0x18004bbd8  lea     rbp, [rsp-0B90h]
0x18004bbe0  sub     rsp, 0C90h
0x18004bbe7  mov     rax, cs:__security_cookie
0x18004bbee  xor     rax, rsp
0x18004bbf1  mov     [rbp+0BC0h+var_40], rax
0x18004bbf8  mov     eax, dword ptr cs:aNa; "{NA}"
0x18004bbfe  xor     r15d, r15d
0x18004bc01  mov     dword ptr [rbp+0BC0h+MultiByteStr], eax
0x18004bc04  xorps   xmm0, xmm0
0x18004bc07  mov     al, byte ptr cs:aNa+4; ""
0x18004bc0d  mov     r12, r8
0x18004bc10  mov     [rbp+0BC0h+MultiByteStr+4], al
0x18004bc13  mov     rbx, rdx
0x18004bc16  xor     eax, eax
0x18004bc18  mov     [rsp+0CC0h+var_C60], r8
0x18004bc1d  mov     [rbp+0BC0h+var_C18], rdx
0x18004bc21  mov     r13d, ecx
0x18004bc24  movups  [rbp+0BC0h+var_BCB], xmm0
0x18004bc28  xor     edx, edx; Val
0x18004bc2a  mov     dword ptr [rbp+0BC0h+var_BCB+0Fh], eax
0x18004bc2d  mov     r8d, 7FCh; Size
0x18004bc33  mov     [rbp+0BC0h+var_C30], r9
0x18004bc37  lea     rcx, [rbp+0BC0h+var_A4C]; void *
0x18004bc3e  mov     [rsp+0CC0h+var_C58], r15d
0x18004bc43  mov     rdi, r9
0x18004bc46  mov     [rsp+0CC0h+var_C64], r15d
0x18004bc4b  mov     [rsp+0CC0h+var_C50], r15
0x18004bc50  movups  xmmword ptr [rbp+0BC0h+MultiByteStr+5], xmm0
0x18004bc54  mov     [rsp+0CC0h+var_C68], r15d
0x18004bc59  mov     [rbp+0BC0h+var_A50], r15d
0x18004bc60  call    memset_0
0x18004bc65  mov     r8, rbx
0x18004bc68  call    RasAuthAttributesPrint
0x18004bc6d  mov     ecx, r13d
0x18004bc70  test    r13d, r13d
0x18004bc73  jz      short loc_18004BC9C
0x18004bc75  sub     ecx, 1
0x18004bc78  jz      short loc_18004BC9C
0x18004bc7a  sub     ecx, 1
0x18004bc7d  jz      short loc_18004BC9C
0x18004bc7f  sub     ecx, 1
0x18004bc82  jz      short loc_18004BC9C
0x18004bc84  sub     ecx, 1
0x18004bc87  jz      short loc_18004BC9C
0x18004bc89  cmp     ecx, 1
0x18004bc8c  jz      short loc_18004BC97
0x18004bc8e  lea     eax, [r15+57h]
0x18004bc92  jmp     loc_18004C196
0x18004bc97  mov     esi, r15d
0x18004bc9a  jmp     short loc_18004BCA1
0x18004bc9c  mov     esi, 1
0x18004bca1  mov     [r12], r15
0x18004bca5  mov     r14d, 2B3h
0x18004bcab  xor     edx, edx; dwCoInit
0x18004bcad  mov     [rdi], r14d
0x18004bcb0  xor     ecx, ecx; pvReserved
0x18004bcb2  mov     [rsp+0CC0h+var_C70], esi
0x18004bcb6  call    cs:__imp_CoInitializeEx
0x18004bcbc  test    eax, eax
0x18004bcbe  jns     short loc_18004BCC8
0x18004bcc0  movzx   eax, ax
0x18004bcc3  jmp     loc_18004C196
0x18004bcc8  mov     edi, r15d
0x18004bccb  mov     [rsp+0CC0h+var_C44], r15d
0x18004bcd0  cmp     [rbx], r15d
0x18004bcd3  jz      short loc_18004BCE6
0x18004bcd5  inc     edi
0x18004bcd7  mov     eax, edi
0x18004bcd9  add     rax, rax
0x18004bcdc  cmp     [rbx+rax*8], r15d
0x18004bce0  jnz     short loc_18004BCD5
0x18004bce2  mov     [rsp+0CC0h+var_C44], edi
0x18004bce6  cmp     esi, 1
0x18004bce9  lea     ebx, [rdi+1]
0x18004bcec  cmovnz  ebx, edi
0x18004bcef  add     ebx, 2
0x18004bcf2  mov     [rbp+0BC0h+var_C40], ebx
0x18004bcf5  lea     ecx, ds:0[rbx*8]
0x18004bcfc  call    cs:__imp_MemAllocIas
0x18004bd02  mov     [rbp+0BC0h+var_C10], rax
0x18004bd06  mov     r15, rax
0x18004bd09  test    rax, rax
0x18004bd0c  jnz     short loc_18004BD16
0x18004bd0e  lea     ebx, [rax+8]
0x18004bd11  jmp     loc_18004C157
0x18004bd16  mov     r8d, ebx
0x18004bd19  xor     edx, edx; Val
0x18004bd1b  shl     r8, 3; Size
0x18004bd1f  mov     rcx, r15; void *
0x18004bd22  call    memset_0
0x18004bd27  mov     rdx, r15
0x18004bd2a  mov     ecx, ebx
0x18004bd2c  call    cs:__imp_AllocateAttributes
0x18004bd32  xor     r9d, r9d
0x18004bd35  test    eax, eax
0x18004bd37  jns     short loc_18004BD41
0x18004bd39  movzx   ebx, ax
0x18004bd3c  jmp     loc_18004C142
0x18004bd41  mov     r12d, r9d
0x18004bd44  lea     rax, g_aszUnauthenticatedUser
0x18004bd4b  mov     [rbp+0BC0h+lpMultiByteStr], rax
0x18004bd4f  mov     rbx, r9
0x18004bd52  mov     [rsp+0CC0h+var_C48], r12d
0x18004bd57  mov     r8d, r9d
0x18004bd5a  mov     [rbp+0BC0h+var_C38], r9
0x18004bd5e  mov     r10d, 2
0x18004bd64  mov     [rbp+0BC0h+var_C20], r9
0x18004bd68  mov     [rsp+0CC0h+var_C6C], r9d
0x18004bd6d  test    edi, edi
0x18004bd6f  jz      loc_18004C1C0
0x18004bd75  mov     edi, r12d
0x18004bd78  shl     r12, 4
0x18004bd7c  add     r12, [rbp+0BC0h+var_C18]
0x18004bd80  mov     ecx, [r12]
0x18004bd84  cmp     ecx, 37h ; '7'
0x18004bd87  jg      loc_18004C03D
0x18004bd8d  jz      loc_18004BE59
0x18004bd93  cmp     ecx, 1Ah
0x18004bd96  jg      loc_18004BFC5
0x18004bd9c  jz      loc_18004BF38
0x18004bda2  cmp     ecx, 9
0x18004bda5  jg      loc_18004BF15
0x18004bdab  jz      loc_18004BE59
0x18004bdb1  mov     edx, ecx
0x18004bdb3  sub     edx, r10d
0x18004bdb6  jz      loc_18004BEF1
0x18004bdbc  sub     edx, 1
0x18004bdbf  jz      loc_18004BEF1
0x18004bdc5  sub     edx, 1
0x18004bdc8  jz      short loc_18004BDE2
0x18004bdca  sub     edx, 1
0x18004bdcd  jz      short loc_18004BE47
0x18004bdcf  sub     edx, 1
0x18004bdd2  jz      short loc_18004BE47
0x18004bdd4  sub     edx, 1
0x18004bdd7  jz      short loc_18004BE47
0x18004bdd9  cmp     edx, 1
0x18004bddc  jnz     loc_18004BEFE
0x18004bde2  mov     ecx, 80h
0x18004bde7  call    cs:__imp_MemAllocIas
0x18004bded  mov     rsi, rax
0x18004bdf0  test    rax, rax
0x18004bdf3  jz      loc_18004C138
0x18004bdf9  xor     edx, edx; Val
0x18004bdfb  mov     r8d, 80h; Size
0x18004be01  mov     rcx, rax; void *
0x18004be04  call    memset_0
0x18004be09  mov     ecx, [r12+8]; hostlong
0x18004be0e  call    cs:__imp_htonl
0x18004be14  mov     dword ptr [rsi], 2
0x18004be1a  lea     rdi, [r15+rdi*8]
0x18004be1e  mov     [rsi+4], eax
0x18004be21  xor     r9d, r9d
0x18004be24  xor     eax, eax
0x18004be26  mov     [rsi+8], rax
0x18004be2a  mov     rax, [rdi]
0x18004be2d  lea     r11d, [r9+4]
0x18004be31  mov     [rax+10h], r11d
0x18004be35  mov     rax, [rdi]
0x18004be38  mov     [rax+18h], rsi
0x18004be3c  cmp     [r12], r11d
0x18004be40  jnz     short loc_18004BE6F
0x18004be42  mov     rbx, rsi
0x18004be45  jmp     short loc_18004BE6F
0x18004be47  cmp     ecx, 7
0x18004be4a  jnz     short loc_18004BE59
0x18004be4c  cmp     qword ptr [r12+8], 3
0x18004be52  jnz     short loc_18004BE59
0x18004be54  mov     [rsp+0CC0h+var_C70], r9d
0x18004be59  lea     rdi, [r15+rdi*8]
0x18004be5d  mov     rax, [rdi]
0x18004be60  mov     [rax+10h], r10d
0x18004be64  mov     rcx, [rdi]
0x18004be67  mov     eax, [r12+8]
0x18004be6c  mov     [rcx+18h], eax
0x18004be6f  cmp     qword ptr cs:xmmword_1800CA100, r9
0x18004be76  mov     rcx, [rdi]
0x18004be79  mov     eax, [r12]
0x18004be7d  mov     [rcx+8], eax
0x18004be80  jz      short loc_18004BEC5
0x18004be82  mov     r8d, [r12]
0x18004be86  lea     rdx, aInsertingAttri; "Inserting attribute type %d"
0x18004be8d  lea     rcx, [rbp+0BC0h+var_A50]
0x18004be94  mov     word ptr [rbp+0BC0h+var_A50], r9w
0x18004be9c  call    FormatRRASErrorString
0x18004bea1  mov     rdx, qword ptr cs:xmmword_1800CA100
0x18004bea8  lea     r8, [rbp+0BC0h+var_A50]
0x18004beaf  mov     rcx, cs:gRasAuthEtwContext
0x18004beb6  mov     rax, cs:gRasAuthTemplateFunc
0x18004bebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bec2  xor     r9d, r9d
0x18004bec5  mov     r12d, [rsp+0CC0h+var_C48]
0x18004beca  mov     r10d, 2
0x18004bed0  mov     esi, [rsp+0CC0h+var_C70]
0x18004bed4  inc     r12d
0x18004bed7  mov     [rsp+0CC0h+var_C48], r12d
0x18004bedc  cmp     r12d, [rsp+0CC0h+var_C44]
0x18004bee1  jnb     loc_18004C1C0
0x18004bee7  mov     r8d, [rsp+0CC0h+var_C6C]
0x18004beec  jmp     loc_18004BD75
0x18004bef1  mov     [rsp+0CC0h+var_C6C], 1
0x18004bef9  mov     [rsp+0CC0h+var_C70], r9d
0x18004befe  cmp     ecx, 1
0x18004bf01  jnz     loc_18004C0CD
0x18004bf07  mov     rax, [r12+8]
0x18004bf0c  mov     [rbp+0BC0h+lpMultiByteStr], rax
0x18004bf10  jmp     loc_18004C0CD
0x18004bf15  sub     ecx, 0Ah
0x18004bf18  jz      loc_18004BE59
0x18004bf1e  sub     ecx, r10d
0x18004bf21  jz      loc_18004BE59
0x18004bf27  sub     ecx, 1
0x18004bf2a  jz      loc_18004BE59
0x18004bf30  sub     ecx, 1
0x18004bf33  jmp     loc_18004BFEE
0x18004bf38  cmp     dword ptr [r12+4], 8
0x18004bf3e  mov     [rsp+0CC0h+var_C6C], r8d
0x18004bf43  mov     [rsp+0CC0h+var_C70], esi
0x18004bf47  jb      short loc_18004BF8E
0x18004bf49  mov     rdx, [r12+8]
0x18004bf4e  movzx   ecx, byte ptr [rdx+1]
0x18004bf52  movzx   eax, byte ptr [rdx+2]
0x18004bf56  shl     eax, 8
0x18004bf59  shl     ecx, 10h
0x18004bf5c  add     ecx, eax
0x18004bf5e  movzx   eax, byte ptr [rdx]
0x18004bf61  shl     eax, 18h
0x18004bf64  add     ecx, eax
0x18004bf66  movzx   eax, byte ptr [rdx+3]
0x18004bf6a  add     ecx, eax
0x18004bf6c  cmp     ecx, 137h
0x18004bf72  jnz     short loc_18004BF8E
0x18004bf74  movzx   ecx, byte ptr [rdx+4]
0x18004bf78  sub     ecx, 1
0x18004bf7b  jz      short loc_18004BF87
0x18004bf7d  sub     ecx, r10d
0x18004bf80  jz      short loc_18004BF87
0x18004bf82  cmp     ecx, 1
0x18004bf85  jnz     short loc_18004BF92
0x18004bf87  mov     [rsp+0CC0h+var_C70], r9d
0x18004bf8c  jmp     short loc_18004BF92
0x18004bf8e  mov     [rsp+0CC0h+var_C70], esi
0x18004bf92  mov     rax, [r12+8]
0x18004bf97  cmp     byte ptr [rax+4], 38h ; '8'
0x18004bf9b  jnz     loc_18004C0CD
0x18004bfa1  movups  xmm0, xmmword ptr [rax+6]
0x18004bfa5  mov     [rsp+0CC0h+var_C6C], r8d
0x18004bfaa  movups  xmmword ptr [rbp+0BC0h+MultiByteStr], xmm0
0x18004bfae  movups  xmm1, xmmword ptr [rax+16h]
0x18004bfb2  movups  xmmword ptr [rbp-10h], xmm1
0x18004bfb6  movsd   xmm0, qword ptr [rax+26h]
0x18004bfbb  movsd   qword ptr [rbp+0BC0h+var_BCB+0Bh], xmm0
0x18004bfc0  jmp     loc_18004C0CD
0x18004bfc5  cmp     ecx, 2Bh ; '+'
0x18004bfc8  jg      short loc_18004C002
0x18004bfca  jz      loc_18004BE59
0x18004bfd0  sub     ecx, 1Bh
0x18004bfd3  jz      loc_18004BE59
0x18004bfd9  sub     ecx, 1
0x18004bfdc  jz      loc_18004BE59
0x18004bfe2  sub     ecx, 1
0x18004bfe5  jz      loc_18004BE59
0x18004bfeb  sub     ecx, 0Bh
0x18004bfee  jz      loc_18004BE59
0x18004bff4  sub     ecx, 1
0x18004bff7  jz      loc_18004BE59
0x18004bffd  cmp     ecx, 1
0x18004c000  jmp     short loc_18004C032
0x18004c002  sub     ecx, 2Dh ; '-'
0x18004c005  jz      loc_18004BE59
0x18004c00b  sub     ecx, 1
0x18004c00e  jz      loc_18004BE59
0x18004c014  sub     ecx, 1
0x18004c017  jz      loc_18004BE59
0x18004c01d  sub     ecx, 1
0x18004c020  jz      loc_18004BE59
0x18004c026  sub     ecx, 1
0x18004c029  jz      loc_18004BE59
0x18004c02f  cmp     ecx, r10d
0x18004c032  jz      loc_18004BE59
0x18004c038  jmp     loc_18004C0CD
0x18004c03d  sub     ecx, 3Dh ; '='
0x18004c040  jz      loc_18004BE59
0x18004c046  sub     ecx, 1
0x18004c049  jz      loc_18004BE59
0x18004c04f  sub     ecx, r10d
0x18004c052  jz      loc_18004BE59
0x18004c058  sub     ecx, 1
0x18004c05b  jz      loc_18004BE59
0x18004c061  sub     ecx, 0Ah
0x18004c064  jz      loc_18004BE59
0x18004c06a  sub     ecx, 1
  ... truncated ...
```

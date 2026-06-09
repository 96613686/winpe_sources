# DhcpInform

- ea: `0x180031120`
- end: `0x180031cc7`
- name: `DhcpInform`
- size: `2983`
- prototype: `void __stdcall(PVOID)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x180031120`
- `0x18003230c`
- `0x180033a20`
- `0x180033a80`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031468`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003176b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003183d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031468`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003176b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003183d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031281`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003147d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003161f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003177f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031860`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031281`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003147d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003161f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003177f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800312b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800312b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a9f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031517`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031517`
- `dhcpcsvc!DhcpRequestParams` at `0x18003144c`
- `dhcpcsvc!DhcpRequestParams` at `0x18003144c`

## string_xrefs

- `0x180031b94`: `DhcpInform: Send reponse to Protocol engine`
- `0x180031ba9`: `DhcpInform: Send reponse to Protocol engine`
- `0x180031be5`: `DhcpInform: SendMessageToProtocolEngine=%d`
- `0x180031c1d`: `DhcpInform: SendMessageToProtocolEngine=%d`
- `0x18003131f`: `DhcpInform: No need to send response to Protocol engine`
- `0x180031c2b`: `DhcpInform: No need to send response to Protocol engine`

## pseudocode

```c
void __fastcall DhcpInform(_DWORD *a1)
{
  unsigned int *v2; // r14
  void *v3; // r12
  unsigned int v4; // esi
  ULONG v5; // ebx
  BYTE *Buffer; // r13
  DWORD LastError; // eax
  const CHAR *v8; // rcx
  __int64 v9; // r8
  int v10; // edi
  WCHAR *v11; // r8
  DWORD v12; // eax
  DWORD v13; // ebx
  unsigned int v14; // edx
  int v15; // r13d
  int v16; // edi
  ULONG v17; // eax
  __int64 v18; // rbx
  unsigned int v19; // edx
  char *v20; // rax
  _DWORD *v21; // rdi
  unsigned int v22; // edx
  int i; // r14d
  __int64 v24; // r8
  unsigned int *v25; // rax
  unsigned int v26; // edx
  bool v27; // zf
  int v28; // esi
  HLOCAL v29; // rax
  unsigned int v30; // edx
  __int64 v31; // r8
  unsigned int v32; // edx
  unsigned __int8 *v33; // rcx
  DWORD v34; // eax
  HLOCAL v35; // rbx
  unsigned int v36; // eax
  unsigned int v37; // [rsp+50h] [rbp-B0h]
  ULONG v38; // [rsp+58h] [rbp-A8h]
  DWORD pSize; // [rsp+5Ch] [rbp-A4h] BYREF
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h]
  __int64 v43; // [rsp+70h] [rbp-90h]
  unsigned int *v44; // [rsp+78h] [rbp-88h]
  HLOCAL v45; // [rsp+80h] [rbp-80h]
  DHCPCAPI_PARAMS_ARRAY RecdParams; // [rsp+90h] [rbp-70h] BYREF
  DHCPCAPI_PARAMS_ARRAY SendParams; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v48[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h]
  __int64 v50; // [rsp+C0h] [rbp-40h]
  __int64 v51; // [rsp+C8h] [rbp-38h]
  int v52; // [rsp+D0h] [rbp-30h]
  unsigned int *v53; // [rsp+D8h] [rbp-28h]
  int v54; // [rsp+E0h] [rbp-20h]
  int v55; // [rsp+E4h] [rbp-1Ch]
  unsigned int v56; // [rsp+E8h] [rbp-18h]
  void *v57; // [rsp+F0h] [rbp-10h]
  HLOCAL v58; // [rsp+F8h] [rbp-8h]
  int v59; // [rsp+1C90h] [rbp+1B90h] BYREF
  __int64 v60; // [rsp+1C94h] [rbp+1B94h]
  void *Src; // [rsp+1CA0h] [rbp+1BA0h]
  size_t Size; // [rsp+1CA8h] [rbp+1BA8h]
  int v63; // [rsp+1CB0h] [rbp+1BB0h]
  __int64 v64; // [rsp+1CB4h] [rbp+1BB4h]
  __int64 v65; // [rsp+1CC0h] [rbp+1BC0h]
  int v66; // [rsp+1CC8h] [rbp+1BC8h]
  int v67; // [rsp+1CD0h] [rbp+1BD0h]
  __int64 v68; // [rsp+1CD4h] [rbp+1BD4h]
  __int64 v69; // [rsp+1CE0h] [rbp+1BE0h]
  int v70; // [rsp+1CE8h] [rbp+1BE8h]
  int v71; // [rsp+1CF0h] [rbp+1BF0h]
  __int64 v72; // [rsp+1CF4h] [rbp+1BF4h]
  __int64 v73; // [rsp+1D00h] [rbp+1C00h]
  int v74; // [rsp+1D08h] [rbp+1C08h]
  int v75; // [rsp+1D10h] [rbp+1C10h]
  __int64 v76; // [rsp+1D14h] [rbp+1C14h]
  __int64 v77; // [rsp+1D20h] [rbp+1C20h]
  int v78; // [rsp+1D28h] [rbp+1C28h]
  int v79; // [rsp+1D30h] [rbp+1C30h]
  __int64 v80; // [rsp+1D34h] [rbp+1C34h]
  __int64 v81; // [rsp+1D40h] [rbp+1C40h]
  int v82; // [rsp+1D48h] [rbp+1C48h]
  int v83; // [rsp+1D50h] [rbp+1C50h] BYREF
  char v84[2044]; // [rsp+1D54h] [rbp+1C54h] BYREF

  v48[1] = 0;
  memset_0(v48, 0, 0x1BDCu);
  v64 = 44;
  v44 = 0;
  v40 = 0;
  v2 = 0;
  v41 = 0;
  hMem = 0;
  v3 = 0;
  v59 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  v4 = 0;
  v63 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v60 = 6;
  v68 = 43;
  v72 = 1;
  v76 = 249;
  v80 = 15;
  v43 = 0;
  pSize = 2048;
  memset_0(v84, 0, sizeof(v84));
  v5 = 5;
  if ( a1[6] )
    v5 = 6;
  v38 = v5;
  v45 = LocalAlloc(0x40u, 0x800u);
  Buffer = (BYTE *)v45;
  if ( !v45 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004D640 )
      {
        LOWORD(v83) = 0;
        LastError = GetLastError();
        FormatRRASErrorString(&v83, L"DhcpInform:LocalAlloc=%d", LastError);
LABEL_8:
        ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D640, &v83);
      }
    }
    else
    {
      GetLastError();
      v8 = "DhcpInform:LocalAlloc=%d";
LABEL_13:
      TraceHlp(v8);
    }
    goto LABEL_9;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004D648 )
    {
      v9 = *(_QWORD *)a1;
      LOWORD(v83) = 0;
      FormatRRASErrorString(&v83, L"DhcpRequestParams(%ws)...", v9);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D648, &v83);
    }
  }
  else
  {
    TraceHlp("DhcpRequestParams(%ws)...");
  }
  v10 = 4;
  while ( 1 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004D648 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
          gIphlpEtwContext,
          qword_18004D648,
          L"DhcpRequestParams Start");
    }
    else
    {
      TraceHlp("DhcpRequestParams Start");
    }
    v11 = *(WCHAR **)a1;
    *(&RecdParams.nParams + 1) = v43;
    RecdParams.Params = (LPDHCPCAPI_PARAMS)&v59;
    *(&SendParams.nParams + 1) = 0;
    RecdParams.nParams = v5;
    SendParams.nParams = 0;
    SendParams.Params = 0;
    v12 = DhcpRequestParams(2u, 0, v11, 0, &SendParams, &RecdParams, Buffer, &pSize, 0);
    v13 = v12;
    if ( v12 == 234 )
    {
      LocalFree(Buffer);
      v45 = LocalAlloc(0x40u, pSize);
      Buffer = (BYTE *)v45;
      if ( v45 )
        goto LABEL_33;
      v13 = GetLastError();
      if ( v13 == 234 )
        goto LABEL_33;
      goto LABEL_26;
    }
    if ( v12 == 2 )
      break;
LABEL_26:
    if ( v13 != 2 )
      goto LABEL_27;
LABEL_33:
    v5 = v38;
  }
  if ( --v10 )
  {
    Sleep(0x3E8u);
    goto LABEL_33;
  }
LABEL_27:
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004D648 )
    {
      LOWORD(v83) = 0;
      FormatRRASErrorString(&v83, L"DhcpRequestParams done(%d)", v13);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D648, &v83);
    }
  }
  else
  {
    TraceHlp("DhcpRequestParams done(%d)");
  }
  if ( v13 )
  {
LABEL_9:
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004D648 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
          gIphlpEtwContext,
          qword_18004D648,
          L"DhcpInform: No need to send response to Protocol engine");
    }
    else
    {
      TraceHlp("DhcpInform: No need to send response to Protocol engine");
    }
    v35 = hMem;
LABEL_128:
    LocalFree(*(HLOCAL *)a1);
    LocalFree(v35);
    LocalFree(v2);
    if ( v3 )
      LocalFree(v3);
    goto LABEL_130;
  }
  v14 = 0;
  v15 = 0;
  v37 = 0;
  v16 = 0;
  v17 = 0;
  while ( 2 )
  {
    LODWORD(v43) = v17;
    if ( v17 < v38 )
    {
      v18 = 32LL * v17;
      if ( *(_DWORD *)((char *)&v60 + v18) != 1 )
      {
        if ( *((_DWORD *)&v60 + 8 * v17) != 6 )
        {
          switch ( *((_DWORD *)&v60 + 8 * v17) )
          {
            case 0xF:
              v28 = *((_DWORD *)&Size + 8 * v17);
              if ( !v28 )
                goto LABEL_116;
              if ( v3 )
                LocalFree(v3);
              v29 = LocalAlloc(0x40u, (unsigned int)(v28 + 1));
              v4 = 0;
              v3 = v29;
              if ( !v29 )
              {
LABEL_95:
                if ( !gIsIphlpEtwTracingAvailable )
                {
                  GetLastError();
                  v8 = "DhcpInform: LocalAlloc=%d";
                  goto LABEL_13;
                }
                if ( !qword_18004D640 )
                  goto LABEL_9;
                LOWORD(v83) = 0;
                v34 = GetLastError();
                FormatRRASErrorString(&v83, L"DhcpInform: LocalAlloc=%d", v34);
                goto LABEL_8;
              }
              memcpy_0(v29, *(void **)((char *)&Src + v18), *(unsigned int *)((char *)&Size + v18));
              if ( gIsIphlpEtwTracingAvailable )
              {
                if ( qword_18004D648 )
                {
                  LOWORD(v83) = 0;
                  FormatRRASErrorString(&v83, L"DhcpInform: DOMAIN_NAME %hs", v3);
                  ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(
                    gIphlpEtwContext,
                    qword_18004D648,
                    &v83);
                }
              }
              else
              {
                TraceHlp("DhcpInform: DOMAIN_NAME %hs");
              }
LABEL_51:
              v16 = 1;
              break;
            case 0x2C:
              v22 = *((_DWORD *)&Size + 8 * v17);
              if ( !v22 )
                goto LABEL_115;
              if ( (v22 & 3) != 0 )
              {
                if ( !gIsIphlpEtwTracingAvailable )
                {
                  v8 = "Invalid NETBIOS_NAME_SERVER size %d";
                  goto LABEL_13;
                }
                if ( !qword_18004D640 )
                  goto LABEL_9;
                LOWORD(v83) = 0;
                FormatRRASErrorString(&v83, L"Invalid NETBIOS_NAME_SERVER size %d", v22);
                goto LABEL_8;
              }
              for ( i = 0; i < 2; ++i )
              {
                v24 = *(__int64 *)((char *)&Src + v18);
                v25 = (unsigned int *)&v41;
                v26 = *(unsigned __int8 *)(v4 + v24)
                    + (*(unsigned __int8 *)(v4 + 1 + v24) << 8)
                    + (*(unsigned __int8 *)(v4 + 2 + v24) << 16)
                    + (*(unsigned __int8 *)(v4 + 3 + v24) << 24);
                if ( !i )
                  v25 = (unsigned int *)&v40;
                v27 = gIsIphlpEtwTracingAvailable == 0;
                *v25 = v26;
                if ( v27 )
                {
                  TraceHlp("DhcpInform: NETBIOS_NAME_SERVER 0x%x");
                }
                else if ( qword_18004D648 )
                {
                  LOWORD(v83) = 0;
                  FormatRRASErrorString(&v83, L"DhcpInform: NETBIOS_NAME_SERVER 0x%x", v26);
                  ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(
                    gIphlpEtwContext,
                    qword_18004D648,
                    &v83);
                }
                v4 += 4;
                v16 = 1;
                if ( v4 == *(_DWORD *)((char *)&Size + v18) )
                  break;
              }
              v2 = v44;
LABEL_92:
              v4 = 0;
              break;
            case 0xF9:
              v19 = *((_DWORD *)&Size + 8 * v17);
              if ( !v19 )
                goto LABEL_115;
              if ( v19 < 5 )
              {
                if ( !gIsIphlpEtwTracingAvailable )
                {
                  v8 = "Invalid OPTION_VENDOR_ROUTE_PLUMB size %d";
                  goto LABEL_13;
                }
                if ( !qword_18004D640 )
                  goto LABEL_9;
                LOWORD(v83) = 0;
                FormatRRASErrorString(&v83, L"Invalid OPTION_VENDOR_ROUTE_PLUMB size %d", v19);
                goto LABEL_8;
              }
              if ( gIsIphlpEtwTracingAvailable )
              {
                if ( qword_18004D648 )
                {
                  LOWORD(v83) = 0;
                  FormatRRASErrorString(&v83, L"DhcpInform: OPTION_VENDOR_ROUTE_PLUMB Code Len 0x%x", v19);
                  ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(
                    gIphlpEtwContext,
                    qword_18004D648,
                    &v83);
                }
              }
              else
              {
                TraceHlp("DhcpInform: OPTION_VENDOR_ROUTE_PLUMB Code Len 0x%x");
              }
              v20 = (char *)LocalAlloc(0x40u, *(unsigned int *)((char *)&Size + v18) + 4LL);
              hMem = v20;
              v21 = v20;
              if ( !v20 )
                goto LABEL_95;
              memcpy_0(v20 + 4, *(void **)((char *)&Src + v18), *(unsigned int *)((char *)&Size + v18));
              *v21 = *(_DWORD *)((char *)&Size + v18);
              goto LABEL_51;
            default:
LABEL_94:
              v17 = v43 + 1;
              continue;
          }
          v14 = v37;
          goto LABEL_94;
        }
        v30 = *((_DWORD *)&Size + 8 * v17);
        if ( !v30 )
          goto LABEL_115;
        if ( (v30 & 3) != 0 )
        {
          if ( !gIsIphlpEtwTracingAvailable )
          {
            v8 = "Invalid DOMAIN_NAME_SERVERS size %d";
            goto LABEL_13;
          }
          if ( !qword_18004D640 )
            goto LABEL_9;
          LOWORD(v83) = 0;
          FormatRRASErrorString(&v83, L"Invalid DOMAIN_NAME_SERVERS size %d", v30);
          goto LABEL_8;
        }
        if ( v2 )
        {
          LocalFree(v2);
          v15 = 0;
        }
        v44 = (unsigned int *)LocalAlloc(0x40u, *(_DWORD *)((_BYTE *)&Size + v18) & 0xFFFFFFFC);
        v2 = v44;
        if ( !v44 )
          goto LABEL_95;
        while ( v4 < *(_DWORD *)((char *)&Size + v18) )
        {
          v31 = *(__int64 *)((char *)&Src + v18);
          v27 = gIsIphlpEtwTracingAvailable == 0;
          v2[v15] = *(unsigned __int8 *)(v4 + v31)
                  + (*(unsigned __int8 *)(v4 + 1 + v31) << 8)
                  + (*(unsigned __int8 *)(v4 + 2 + v31) << 16)
                  + (*(unsigned __int8 *)(v4 + 3 + v31) << 24);
          if ( v27 )
          {
            TraceHlp("DhcpInform: DOMAIN_NAME_SERVER 0x%x");
          }
          else if ( qword_18004D648 )
          {
            LOWORD(v83) = 0;
            FormatRRASErrorString(&v83, L"DhcpInform: DOMAIN_NAME_SERVER 0x%x", v2[v15]);
            ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D648, &v83);
          }
          v4 += 4;
          v16 = 1;
          ++v15;
        }
        goto LABEL_92;
      }
      v32 = *((_DWORD *)&Size + 8 * v17);
      if ( !v32 )
      {
LABEL_115:
        v14 = v37;
        break;
      }
      if ( (v32 & 3) != 0 )
      {
        if ( !gIsIphlpEtwTracingAvailable )
        {
          v8 = "Invalid OPTION_SUBNET_MASK size %d";
          goto LABEL_13;
        }
        if ( !qword_18004D640 )
          goto LABEL_9;
        LOWORD(v83) = 0;
        FormatRRASErrorString(&v83, L"Invalid OPTION_SUBNET_MASK size %d", v32);
        goto LABEL_8;
      }
      v33 = (unsigned __int8 *)*(&Src + 4 * v17);
      v14 = *v33 + (v33[1] << 8) + (v33[2] << 16) + (v33[3] << 24);
      v37 = v14;
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( qword_18004D648 )
        {
          LOWORD(v83) = 0;
          FormatRRASErrorString(&v83, L"DhcpInform: OPTION_SUBNET_MASK 0x%x", v14);
          ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D648, &v83);
          goto LABEL_89;
        }
      }
      else
      {
        TraceHlp("DhcpInform: OPTION_SUBNET_MASK 0x%x");
LABEL_89:
        v14 = v37;
      }
      v16 = 1;
      goto LABEL_94;
    }
    break;
  }
LABEL_116:
  if ( !v16 )
    goto LABEL_9;
  v35 = hMem;
  v50 = *((_QWORD *)a1 + 1);
  v49 = *((_QWORD *)a1 + 2);
  v51 = *(_QWORD *)a1;
  v54 = v40;
  v55 = v41;
  v48[0] = 11;
  v52 = v15;
  v53 = v2;
  v56 = v14;
  v57 = v3;
  v58 = hMem;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004D648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004D648,
        L"DhcpInform: Send reponse to Protocol engine");
  }
  else
  {
    TraceHlp("DhcpInform: Send reponse to Protocol engine");
  }
  v36 = (*((__int64 (__fastcall **)(_DWORD *))a1 + 4))(v48);
  if ( v36 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004D640 )
      {
        LOWORD(v83) = 0;
        FormatRRASErrorString(&v83, L"DhcpInform: SendMessageToProtocolEngine=%d", v36);
        ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D640, &v83);
      }
    }
    else
    {
      TraceHlp("DhcpInform: SendMessageToProtocolEngine=%d");
    }
    goto LABEL_128;
  }
LABEL_130:
  if ( v45 )
    LocalFree(v45);
  LocalFree(a1);
}

```

## disassembly

```asm
0x180031120  push    rbp
0x180031122  push    rbx
0x180031123  push    rsi
0x180031124  push    rdi
0x180031125  push    r12
0x180031127  push    r13
0x180031129  push    r14
0x18003112b  push    r15
0x18003112d  lea     rbp, [rsp-2468h]
0x180031135  mov     eax, 2568h
0x18003113a  call    _alloca_probe
0x18003113f  sub     rsp, rax
0x180031142  mov     rax, cs:__security_cookie
0x180031149  xor     rax, rsp
0x18003114c  mov     [rbp+24A0h+var_50], rax
0x180031153  mov     r15, rcx
0x180031156  xor     eax, eax
0x180031158  lea     rcx, [rbp+24A0h+var_24F0]; void *
0x18003115c  mov     [rbp+24A0h+var_24EC], eax
0x18003115f  xor     edx, edx; Val
0x180031161  mov     r8d, 1BDCh; Size
0x180031167  call    memset_0
0x18003116c  xor     ecx, ecx
0x18003116e  mov     [rbp+24A0h+var_8EC], 2Ch ; ','
0x180031179  xor     eax, eax
0x18003117b  mov     [rsp+25A0h+var_2528], rcx
0x180031180  mov     edi, 800h
0x180031185  mov     [rsp+25A0h+var_2540], ecx
0x180031189  mov     r14d, ecx
0x18003118c  mov     [rsp+25A0h+var_253C], ecx
0x180031190  lea     r13d, [rcx+6]
0x180031194  mov     [rsp+25A0h+hMem], rcx
0x180031199  mov     r12d, ecx
0x18003119c  mov     [rbp+24A0h+var_910], ecx
0x1800311a2  mov     [rbp+24A0h+Src], rcx
0x1800311a9  lea     r8d, [rdi-4]; Size
0x1800311ad  mov     dword ptr [rbp+24A0h+Size], ecx
0x1800311b3  mov     esi, ecx
0x1800311b5  mov     [rbp+24A0h+var_8F0], ecx
0x1800311bb  xor     edx, edx; Val
0x1800311bd  mov     [rbp+24A0h+var_8E0], rcx
0x1800311c4  mov     [rbp+24A0h+var_8D8], ecx
0x1800311ca  mov     [rbp+24A0h+var_8D0], ecx
0x1800311d0  mov     [rbp+24A0h+var_8C0], rcx
0x1800311d7  mov     [rbp+24A0h+var_8B8], ecx
0x1800311dd  mov     [rbp+24A0h+var_8B0], ecx
0x1800311e3  mov     [rbp+24A0h+var_8A0], rcx
0x1800311ea  mov     [rbp+24A0h+var_898], ecx
0x1800311f0  mov     [rbp+24A0h+var_890], ecx
0x1800311f6  mov     [rbp+24A0h+var_880], rcx
0x1800311fd  mov     [rbp+24A0h+var_878], ecx
0x180031203  mov     [rbp+24A0h+var_870], ecx
0x180031209  mov     [rbp+24A0h+var_860], rcx
0x180031210  mov     [rbp+24A0h+var_858], ecx
0x180031216  mov     [rbp+24A0h+var_850], ecx
0x18003121c  lea     rcx, [rbp+24A0h+var_84C]; void *
0x180031223  mov     [rbp+24A0h+var_90C], r13
0x18003122a  mov     [rbp+24A0h+var_8CC], 2Bh ; '+'
0x180031235  mov     [rbp+24A0h+var_8AC], 1
0x180031240  mov     [rbp+24A0h+var_88C], 0F9h
0x18003124b  mov     [rbp+24A0h+var_86C], 0Fh
0x180031256  mov     [rsp+25A0h+var_2530], rax
0x18003125b  mov     [rsp+25A0h+var_2550], rax
0x180031260  mov     [rsp+25A0h+var_2544], edi
0x180031264  call    memset_0
0x180031269  cmp     [r15+18h], esi
0x18003126d  lea     ebx, [r12+5]
0x180031272  mov     edx, edi; uBytes
0x180031274  lea     ecx, [r12+40h]; uFlags
0x180031279  cmovnz  ebx, r13d
0x18003127d  mov     [rsp+25A0h+var_2548], ebx
0x180031281  call    cs:__imp_LocalAlloc
0x180031288  nop     dword ptr [rax+rax+00h]
0x18003128d  mov     [rbp+24A0h+var_2520], rax
0x180031291  mov     r13, rax
0x180031294  test    rax, rax
0x180031297  jnz     loc_180031353
0x18003129d  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x1800312a3  jz      loc_180031337
0x1800312a9  cmp     cs:qword_18004D640, rsi
0x1800312b0  jz      short loc_1800312FC
0x1800312b2  mov     word ptr [rbp+24A0h+var_850], si
0x1800312b9  call    cs:__imp_GetLastError
0x1800312c0  nop     dword ptr [rax+rax+00h]
0x1800312c5  lea     rdx, aDhcpinformLoca; "DhcpInform:LocalAlloc=%d"
0x1800312cc  mov     r8d, eax
0x1800312cf  lea     rcx, [rbp+24A0h+var_850]
0x1800312d6  call    FormatRRASErrorString
0x1800312db  mov     rdx, cs:qword_18004D640
0x1800312e2  lea     r8, [rbp+24A0h+var_850]
0x1800312e9  mov     rcx, cs:gIphlpEtwContext
0x1800312f0  mov     rax, cs:gIphlpTemplateFunc
0x1800312f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312fc  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x180031302  jz      loc_180031C2B
0x180031308  mov     rdx, cs:qword_18004D648
0x18003130f  test    rdx, rdx
0x180031312  jz      loc_180031C37
0x180031318  mov     rcx, cs:gIphlpEtwContext
0x18003131f  lea     r8, aDhcpinformNoNe; "DhcpInform: No need to send response to"...
0x180031326  mov     rax, cs:gIphlpTemplateFunc
0x18003132d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031332  jmp     loc_180031C37
0x180031337  call    cs:__imp_GetLastError
0x18003133e  nop     dword ptr [rax+rax+00h]
0x180031343  lea     rcx, aDhcpinformLoca_0; "DhcpInform:LocalAlloc=%d"
0x18003134a  mov     edx, eax
0x18003134c  call    TraceHlp
0x180031351  jmp     short loc_1800312FC
0x180031353  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x180031359  jz      short loc_1800313A6
0x18003135b  cmp     cs:qword_18004D648, rsi
0x180031362  jz      short loc_1800313B5
0x180031364  mov     r8, [r15]
0x180031367  lea     rdx, aDhcprequestpar; "DhcpRequestParams(%ws)..."
0x18003136e  xor     eax, eax
0x180031370  lea     rcx, [rbp+24A0h+var_850]
0x180031377  mov     word ptr [rbp+24A0h+var_850], ax
0x18003137e  call    FormatRRASErrorString
0x180031383  mov     rdx, cs:qword_18004D648
0x18003138a  lea     r8, [rbp+24A0h+var_850]
0x180031391  mov     rcx, cs:gIphlpEtwContext
0x180031398  mov     rax, cs:gIphlpTemplateFunc
0x18003139f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313a4  jmp     short loc_1800313B5
0x1800313a6  mov     rdx, [r15]
0x1800313a9  lea     rcx, aDhcprequestpar_0; "DhcpRequestParams(%ws)..."
0x1800313b0  call    TraceHlp
0x1800313b5  mov     edi, 4
0x1800313ba  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x1800313c0  jz      short loc_1800313EA
0x1800313c2  mov     rdx, cs:qword_18004D648
0x1800313c9  test    rdx, rdx
0x1800313cc  jz      short loc_1800313F6
0x1800313ce  mov     rcx, cs:gIphlpEtwContext
0x1800313d5  lea     r8, aDhcprequestpar_3; "DhcpRequestParams Start"
0x1800313dc  mov     rax, cs:gIphlpTemplateFunc
0x1800313e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313e8  jmp     short loc_1800313F6
0x1800313ea  lea     rcx, aDhcprequestpar_2; "DhcpRequestParams Start"
0x1800313f1  call    TraceHlp
0x1800313f6  mov     rax, [rsp+25A0h+var_2530]
0x1800313fb  xor     edx, edx; Reserved
0x1800313fd  mov     r8, [r15]; AdapterName
0x180031400  xor     r9d, r9d; ClassId
0x180031403  mov     dword ptr [rbp+24A0h+var_2510+4], eax
0x180031406  lea     rax, [rbp+24A0h+var_910]
0x18003140d  mov     [rbp+24A0h+var_2510.Params], rax
0x180031411  mov     rax, [rsp+25A0h+var_2550]
0x180031416  lea     ecx, [rdx+2]; Flags
0x180031419  mov     dword ptr [rbp+24A0h+var_2500+4], eax
0x18003141c  lea     rax, [rsp+25A0h+var_2544]
0x180031421  mov     [rsp+25A0h+RequestIdStr], rsi; RequestIdStr
0x180031426  mov     [rsp+25A0h+pSize], rax; pSize
0x18003142b  lea     rax, [rbp+24A0h+var_2510]
0x18003142f  mov     [rsp+25A0h+Buffer], r13; Buffer
0x180031434  mov     [rsp+25A0h+RecdParams], rax; RecdParams
0x180031439  lea     rax, [rbp+24A0h+var_2500]
0x18003143d  mov     [rsp+25A0h+SendParams], rax; SendParams
0x180031442  mov     [rbp+24A0h+var_2510.nParams], ebx
0x180031445  mov     [rbp+24A0h+var_2500.nParams], esi
0x180031448  mov     [rbp+24A0h+var_2500.Params], rsi
0x18003144c  call    cs:__imp_DhcpRequestParams
0x180031453  nop     dword ptr [rax+rax+00h]
0x180031458  mov     ebx, eax
0x18003145a  cmp     eax, 0EAh
0x18003145f  jnz     loc_180031508
0x180031465  mov     rcx, r13; hMem
0x180031468  call    cs:__imp_LocalFree
0x18003146f  nop     dword ptr [rax+rax+00h]
0x180031474  mov     edx, [rsp+25A0h+var_2544]; uBytes
0x180031478  mov     ecx, 40h ; '@'; uFlags
0x18003147d  call    cs:__imp_LocalAlloc
0x180031484  nop     dword ptr [rax+rax+00h]
0x180031489  mov     [rbp+24A0h+var_2520], rax
0x18003148d  mov     r13, rax
0x180031490  test    rax, rax
0x180031493  jnz     loc_180031523
0x180031499  call    cs:__imp_GetLastError
0x1800314a0  nop     dword ptr [rax+rax+00h]
0x1800314a5  mov     ebx, eax
0x1800314a7  cmp     eax, 0EAh
0x1800314ac  jz      short loc_180031523
0x1800314ae  cmp     ebx, 2
0x1800314b1  jnz     short loc_1800314B7
0x1800314b3  test    edi, edi
0x1800314b5  jnz     short loc_180031523
0x1800314b7  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x1800314bd  jz      short loc_18003152C
0x1800314bf  cmp     cs:qword_18004D648, rsi
0x1800314c6  jz      short loc_18003153A
0x1800314c8  mov     r8d, ebx
0x1800314cb  mov     word ptr [rbp+24A0h+var_850], si
0x1800314d2  lea     rdx, aDhcprequestpar_1; "DhcpRequestParams done(%d)"
0x1800314d9  lea     rcx, [rbp+24A0h+var_850]
0x1800314e0  call    FormatRRASErrorString
0x1800314e5  mov     rdx, cs:qword_18004D648
0x1800314ec  lea     r8, [rbp+24A0h+var_850]
0x1800314f3  mov     rcx, cs:gIphlpEtwContext
0x1800314fa  mov     rax, cs:gIphlpTemplateFunc
0x180031501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031506  jmp     short loc_18003153A
0x180031508  cmp     eax, 2
0x18003150b  jnz     short loc_1800314AE
0x18003150d  sub     edi, 1
0x180031510  jz      short loc_1800314B7
0x180031512  mov     ecx, 3E8h; dwMilliseconds
0x180031517  call    cs:__imp_Sleep
0x18003151e  nop     dword ptr [rax+rax+00h]
0x180031523  mov     ebx, [rsp+25A0h+var_2548]
0x180031527  jmp     loc_1800313BA
0x18003152c  mov     edx, ebx
0x18003152e  lea     rcx, aDhcprequestpar_4; "DhcpRequestParams done(%d)"
0x180031535  call    TraceHlp
0x18003153a  test    ebx, ebx
0x18003153c  jnz     loc_1800312FC
0x180031542  mov     edx, esi
0x180031544  mov     r13d, esi
0x180031547  mov     dword ptr [rsp+25A0h+var_2550], edx
0x18003154b  mov     edi, esi
0x18003154d  mov     eax, esi
0x18003154f  mov     dword ptr [rsp+25A0h+var_2530], eax
0x180031553  cmp     eax, [rsp+25A0h+var_2548]
0x180031557  jnb     loc_180031B2D
0x18003155d  mov     ebx, eax
0x18003155f  shl     rbx, 5
0x180031563  mov     ecx, dword ptr [rbp+rbx+24A0h+var_90C]
0x18003156a  sub     ecx, 1
0x18003156d  jz      loc_180031939
0x180031573  sub     ecx, 5
0x180031576  jz      loc_18003181D
0x18003157c  sub     ecx, 9
0x18003157f  jz      loc_180031754
0x180031585  sub     ecx, 1Dh
0x180031588  jz      loc_180031668
0x18003158e  cmp     ecx, 0CDh
0x180031594  jnz     loc_1800319EE
0x18003159a  mov     edx, dword ptr [rbp+rbx+24A0h+Size]
0x1800315a1  test    edx, edx
0x1800315a3  jz      loc_180031B25
0x1800315a9  cmp     edx, 5
0x1800315ac  jb      loc_180031A31
0x1800315b2  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x1800315b8  jz      short loc_180031603
0x1800315ba  cmp     cs:qword_18004D648, rsi
0x1800315c1  jz      short loc_18003160F
0x1800315c3  mov     r8d, edx
0x1800315c6  mov     word ptr [rbp+24A0h+var_850], si
0x1800315cd  lea     rdx, aDhcpinformOpti_0; "DhcpInform: OPTION_VENDOR_ROUTE_PLUMB C"...
0x1800315d4  lea     rcx, [rbp+24A0h+var_850]
0x1800315db  call    FormatRRASErrorString
0x1800315e0  mov     rdx, cs:qword_18004D648
0x1800315e7  lea     r8, [rbp+24A0h+var_850]
0x1800315ee  mov     rcx, cs:gIphlpEtwContext
0x1800315f5  mov     rax, cs:gIphlpTemplateFunc
0x1800315fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031601  jmp     short loc_18003160F
0x180031603  lea     rcx, aDhcpinformOpti_2; "DhcpInform: OPTION_VENDOR_ROUTE_PLUMB C"...
0x18003160a  call    TraceHlp
0x18003160f  mov     edx, dword ptr [rbp+rbx+24A0h+Size]
0x180031616  mov     ecx, 40h ; '@'; uFlags
0x18003161b  add     rdx, 4; uBytes
0x18003161f  call    cs:__imp_LocalAlloc
0x180031626  nop     dword ptr [rax+rax+00h]
0x18003162b  mov     [rsp+25A0h+hMem], rax
0x180031630  mov     rdi, rax
0x180031633  test    rax, rax
0x180031636  jz      loc_1800319F9
0x18003163c  mov     r8d, dword ptr [rbp+rbx+24A0h+Size]; Size
0x180031644  lea     rcx, [rax+4]; void *
0x180031648  mov     rdx, [rbp+rbx+24A0h+Src]; Src
0x180031650  call    memcpy_0
0x180031655  mov     ecx, dword ptr [rbp+rbx+24A0h+Size]
0x18003165c  mov     [rdi], ecx
0x18003165e  mov     edi, 1
0x180031663  jmp     loc_1800319EA
0x180031668  mov     edx, dword ptr [rbp+rbx+24A0h+Size]
0x18003166f  test    edx, edx
0x180031671  jz      loc_180031B25
0x180031677  test    dl, 3
0x18003167a  jnz     loc_180031A68
0x180031680  xor     r14d, r14d
0x180031683  cmp     r14d, 2
0x180031687  jge     loc_1800319E3
0x18003168d  mov     r8, [rbp+rbx+24A0h+Src]
0x180031695  lea     eax, [rsi+3]
0x180031698  movzx   edx, byte ptr [rax+r8]
0x18003169d  lea     eax, [rsi+2]
0x1800316a0  movzx   eax, byte ptr [rax+r8]
0x1800316a5  shl     eax, 10h
0x1800316a8  shl     edx, 18h
0x1800316ab  add     edx, eax
0x1800316ad  lea     eax, [rsi+1]
0x1800316b0  movzx   eax, byte ptr [rax+r8]
0x1800316b5  shl     eax, 8
0x1800316b8  add     edx, eax
0x1800316ba  mov     eax, esi
0x1800316bc  movzx   ecx, byte ptr [rax+r8]
0x1800316c1  lea     rax, [rsp+25A0h+var_253C]
0x1800316c6  add     edx, ecx
  ... truncated ...
```

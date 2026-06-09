# DhcpInform

- ea: `0x18002fc60`
- end: `0x180030784`
- name: `DhcpInform`
- size: `2852`
- prototype: `void __stdcall(PVOID)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x18002fc60`
- `0x180030da4`
- `0x180032400`
- `0x180032460`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030271`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030337`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030721`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003072a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030733`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030741`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030750`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030759`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030271`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030337`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030721`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003072a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030733`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030741`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030750`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030759`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fdc1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ff9f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003012b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003027f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030354`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fdc1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ff9f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003012b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003027f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fdf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fdf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030587`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030029`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030029`
- `dhcpcsvc!DhcpRequestParams` at `0x18002ff7a`
- `dhcpcsvc!DhcpRequestParams` at `0x18002ff7a`

## string_xrefs

- `0x180030676`: `DhcpInform: Send reponse to Protocol engine`
- `0x18003068b`: `DhcpInform: Send reponse to Protocol engine`
- `0x1800306c7`: `DhcpInform: SendMessageToProtocolEngine=%d`
- `0x1800306ff`: `DhcpInform: SendMessageToProtocolEngine=%d`
- `0x18002fe53`: `DhcpInform: No need to send response to Protocol engine`
- `0x18003070d`: `DhcpInform: No need to send response to Protocol engine`

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
      if ( qword_18004C640 )
      {
        LOWORD(v83) = 0;
        LastError = GetLastError();
        FormatRRASErrorString(&v83, L"DhcpInform:LocalAlloc=%d", LastError);
LABEL_8:
        ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C640, &v83);
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
    if ( qword_18004C648 )
    {
      v9 = *(_QWORD *)a1;
      LOWORD(v83) = 0;
      FormatRRASErrorString(&v83, L"DhcpRequestParams(%ws)...", v9);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C648, &v83);
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
      if ( qword_18004C648 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
          gIphlpEtwContext,
          qword_18004C648,
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
    if ( qword_18004C648 )
    {
      LOWORD(v83) = 0;
      FormatRRASErrorString(&v83, L"DhcpRequestParams done(%d)", v13);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C648, &v83);
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
      if ( qword_18004C648 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
          gIphlpEtwContext,
          qword_18004C648,
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
                if ( !qword_18004C640 )
                  goto LABEL_9;
                LOWORD(v83) = 0;
                v34 = GetLastError();
                FormatRRASErrorString(&v83, L"DhcpInform: LocalAlloc=%d", v34);
                goto LABEL_8;
              }
              memcpy_0(v29, *(void **)((char *)&Src + v18), *(unsigned int *)((char *)&Size + v18));
              if ( gIsIphlpEtwTracingAvailable )
              {
                if ( qword_18004C648 )
                {
                  LOWORD(v83) = 0;
                  FormatRRASErrorString(&v83, L"DhcpInform: DOMAIN_NAME %hs", v3);
                  ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(
                    gIphlpEtwContext,
                    qword_18004C648,
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
                if ( !qword_18004C640 )
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
                else if ( qword_18004C648 )
                {
                  LOWORD(v83) = 0;
                  FormatRRASErrorString(&v83, L"DhcpInform: NETBIOS_NAME_SERVER 0x%x", v26);
                  ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(
                    gIphlpEtwContext,
                    qword_18004C648,
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
                if ( !qword_18004C640 )
                  goto LABEL_9;
                LOWORD(v83) = 0;
                FormatRRASErrorString(&v83, L"Invalid OPTION_VENDOR_ROUTE_PLUMB size %d", v19);
                goto LABEL_8;
              }
              if ( gIsIphlpEtwTracingAvailable )
              {
                if ( qword_18004C648 )
                {
                  LOWORD(v83) = 0;
                  FormatRRASErrorString(&v83, L"DhcpInform: OPTION_VENDOR_ROUTE_PLUMB Code Len 0x%x", v19);
                  ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(
                    gIphlpEtwContext,
                    qword_18004C648,
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
          if ( !qword_18004C640 )
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
          else if ( qword_18004C648 )
          {
            LOWORD(v83) = 0;
            FormatRRASErrorString(&v83, L"DhcpInform: DOMAIN_NAME_SERVER 0x%x", v2[v15]);
            ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C648, &v83);
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
        if ( !qword_18004C640 )
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
        if ( qword_18004C648 )
        {
          LOWORD(v83) = 0;
          FormatRRASErrorString(&v83, L"DhcpInform: OPTION_SUBNET_MASK 0x%x", v14);
          ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C648, &v83);
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
    if ( qword_18004C648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C648,
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
      if ( qword_18004C640 )
      {
        LOWORD(v83) = 0;
        FormatRRASErrorString(&v83, L"DhcpInform: SendMessageToProtocolEngine=%d", v36);
        ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C640, &v83);
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
0x18002fc60  push    rbp
0x18002fc62  push    rbx
0x18002fc63  push    rsi
0x18002fc64  push    rdi
0x18002fc65  push    r12
0x18002fc67  push    r13
0x18002fc69  push    r14
0x18002fc6b  push    r15
0x18002fc6d  lea     rbp, [rsp-2468h]
0x18002fc75  mov     eax, 2568h
0x18002fc7a  call    _alloca_probe
0x18002fc7f  sub     rsp, rax
0x18002fc82  mov     rax, cs:__security_cookie
0x18002fc89  xor     rax, rsp
0x18002fc8c  mov     [rbp+24A0h+var_50], rax
0x18002fc93  mov     r15, rcx
0x18002fc96  xor     eax, eax
0x18002fc98  lea     rcx, [rbp+24A0h+var_24F0]; void *
0x18002fc9c  mov     [rbp+24A0h+var_24EC], eax
0x18002fc9f  xor     edx, edx; Val
0x18002fca1  mov     r8d, 1BDCh; Size
0x18002fca7  call    memset_0
0x18002fcac  xor     ecx, ecx
0x18002fcae  mov     [rbp+24A0h+var_8EC], 2Ch ; ','
0x18002fcb9  xor     eax, eax
0x18002fcbb  mov     [rsp+25A0h+var_2528], rcx
0x18002fcc0  mov     edi, 800h
0x18002fcc5  mov     [rsp+25A0h+var_2540], ecx
0x18002fcc9  mov     r14d, ecx
0x18002fccc  mov     [rsp+25A0h+var_253C], ecx
0x18002fcd0  lea     r13d, [rcx+6]
0x18002fcd4  mov     [rsp+25A0h+hMem], rcx
0x18002fcd9  mov     r12d, ecx
0x18002fcdc  mov     [rbp+24A0h+var_910], ecx
0x18002fce2  mov     [rbp+24A0h+Src], rcx
0x18002fce9  lea     r8d, [rdi-4]; Size
0x18002fced  mov     dword ptr [rbp+24A0h+Size], ecx
0x18002fcf3  mov     esi, ecx
0x18002fcf5  mov     [rbp+24A0h+var_8F0], ecx
0x18002fcfb  xor     edx, edx; Val
0x18002fcfd  mov     [rbp+24A0h+var_8E0], rcx
0x18002fd04  mov     [rbp+24A0h+var_8D8], ecx
0x18002fd0a  mov     [rbp+24A0h+var_8D0], ecx
0x18002fd10  mov     [rbp+24A0h+var_8C0], rcx
0x18002fd17  mov     [rbp+24A0h+var_8B8], ecx
0x18002fd1d  mov     [rbp+24A0h+var_8B0], ecx
0x18002fd23  mov     [rbp+24A0h+var_8A0], rcx
0x18002fd2a  mov     [rbp+24A0h+var_898], ecx
0x18002fd30  mov     [rbp+24A0h+var_890], ecx
0x18002fd36  mov     [rbp+24A0h+var_880], rcx
0x18002fd3d  mov     [rbp+24A0h+var_878], ecx
0x18002fd43  mov     [rbp+24A0h+var_870], ecx
0x18002fd49  mov     [rbp+24A0h+var_860], rcx
0x18002fd50  mov     [rbp+24A0h+var_858], ecx
0x18002fd56  mov     [rbp+24A0h+var_850], ecx
0x18002fd5c  lea     rcx, [rbp+24A0h+var_84C]; void *
0x18002fd63  mov     [rbp+24A0h+var_90C], r13
0x18002fd6a  mov     [rbp+24A0h+var_8CC], 2Bh ; '+'
0x18002fd75  mov     [rbp+24A0h+var_8AC], 1
0x18002fd80  mov     [rbp+24A0h+var_88C], 0F9h
0x18002fd8b  mov     [rbp+24A0h+var_86C], 0Fh
0x18002fd96  mov     [rsp+25A0h+var_2530], rax
0x18002fd9b  mov     [rsp+25A0h+var_2550], rax
0x18002fda0  mov     [rsp+25A0h+var_2544], edi
0x18002fda4  call    memset_0
0x18002fda9  cmp     [r15+18h], esi
0x18002fdad  lea     ebx, [r12+5]
0x18002fdb2  mov     edx, edi; uBytes
0x18002fdb4  lea     ecx, [r12+40h]; uFlags
0x18002fdb9  cmovnz  ebx, r13d
0x18002fdbd  mov     [rsp+25A0h+var_2548], ebx
0x18002fdc1  call    cs:__imp_LocalAlloc
0x18002fdc7  mov     [rbp+24A0h+var_2520], rax
0x18002fdcb  mov     r13, rax
0x18002fdce  test    rax, rax
0x18002fdd1  jnz     loc_18002FE81
0x18002fdd7  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18002fddd  jz      loc_18002FE6B
0x18002fde3  cmp     cs:qword_18004C640, rsi
0x18002fdea  jz      short loc_18002FE30
0x18002fdec  mov     word ptr [rbp+24A0h+var_850], si
0x18002fdf3  call    cs:__imp_GetLastError
0x18002fdf9  lea     rdx, aDhcpinformLoca; "DhcpInform:LocalAlloc=%d"
0x18002fe00  mov     r8d, eax
0x18002fe03  lea     rcx, [rbp+24A0h+var_850]
0x18002fe0a  call    FormatRRASErrorString
0x18002fe0f  mov     rdx, cs:qword_18004C640
0x18002fe16  lea     r8, [rbp+24A0h+var_850]
0x18002fe1d  mov     rcx, cs:gIphlpEtwContext
0x18002fe24  mov     rax, cs:gIphlpTemplateFunc
0x18002fe2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe30  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18002fe36  jz      loc_18003070D
0x18002fe3c  mov     rdx, cs:qword_18004C648
0x18002fe43  test    rdx, rdx
0x18002fe46  jz      loc_180030719
0x18002fe4c  mov     rcx, cs:gIphlpEtwContext
0x18002fe53  lea     r8, aDhcpinformNoNe; "DhcpInform: No need to send response to"...
0x18002fe5a  mov     rax, cs:gIphlpTemplateFunc
0x18002fe61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe66  jmp     loc_180030719
0x18002fe6b  call    cs:__imp_GetLastError
0x18002fe71  lea     rcx, aDhcpinformLoca_0; "DhcpInform:LocalAlloc=%d"
0x18002fe78  mov     edx, eax
0x18002fe7a  call    TraceHlp
0x18002fe7f  jmp     short loc_18002FE30
0x18002fe81  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18002fe87  jz      short loc_18002FED4
0x18002fe89  cmp     cs:qword_18004C648, rsi
0x18002fe90  jz      short loc_18002FEE3
0x18002fe92  mov     r8, [r15]
0x18002fe95  lea     rdx, aDhcprequestpar; "DhcpRequestParams(%ws)..."
0x18002fe9c  xor     eax, eax
0x18002fe9e  lea     rcx, [rbp+24A0h+var_850]
0x18002fea5  mov     word ptr [rbp+24A0h+var_850], ax
0x18002feac  call    FormatRRASErrorString
0x18002feb1  mov     rdx, cs:qword_18004C648
0x18002feb8  lea     r8, [rbp+24A0h+var_850]
0x18002febf  mov     rcx, cs:gIphlpEtwContext
0x18002fec6  mov     rax, cs:gIphlpTemplateFunc
0x18002fecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fed2  jmp     short loc_18002FEE3
0x18002fed4  mov     rdx, [r15]
0x18002fed7  lea     rcx, aDhcprequestpar_0; "DhcpRequestParams(%ws)..."
0x18002fede  call    TraceHlp
0x18002fee3  mov     edi, 4
0x18002fee8  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18002feee  jz      short loc_18002FF18
0x18002fef0  mov     rdx, cs:qword_18004C648
0x18002fef7  test    rdx, rdx
0x18002fefa  jz      short loc_18002FF24
0x18002fefc  mov     rcx, cs:gIphlpEtwContext
0x18002ff03  lea     r8, aDhcprequestpar_3; "DhcpRequestParams Start"
0x18002ff0a  mov     rax, cs:gIphlpTemplateFunc
0x18002ff11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff16  jmp     short loc_18002FF24
0x18002ff18  lea     rcx, aDhcprequestpar_2; "DhcpRequestParams Start"
0x18002ff1f  call    TraceHlp
0x18002ff24  mov     rax, [rsp+25A0h+var_2530]
0x18002ff29  xor     edx, edx; Reserved
0x18002ff2b  mov     r8, [r15]; AdapterName
0x18002ff2e  xor     r9d, r9d; ClassId
0x18002ff31  mov     dword ptr [rbp+24A0h+var_2510+4], eax
0x18002ff34  lea     rax, [rbp+24A0h+var_910]
0x18002ff3b  mov     [rbp+24A0h+var_2510.Params], rax
0x18002ff3f  mov     rax, [rsp+25A0h+var_2550]
0x18002ff44  lea     ecx, [rdx+2]; Flags
0x18002ff47  mov     dword ptr [rbp+24A0h+var_2500+4], eax
0x18002ff4a  lea     rax, [rsp+25A0h+var_2544]
0x18002ff4f  mov     [rsp+25A0h+RequestIdStr], rsi; RequestIdStr
0x18002ff54  mov     [rsp+25A0h+pSize], rax; pSize
0x18002ff59  lea     rax, [rbp+24A0h+var_2510]
0x18002ff5d  mov     [rsp+25A0h+Buffer], r13; Buffer
0x18002ff62  mov     [rsp+25A0h+RecdParams], rax; RecdParams
0x18002ff67  lea     rax, [rbp+24A0h+var_2500]
0x18002ff6b  mov     [rsp+25A0h+SendParams], rax; SendParams
0x18002ff70  mov     [rbp+24A0h+var_2510.nParams], ebx
0x18002ff73  mov     [rbp+24A0h+var_2500.nParams], esi
0x18002ff76  mov     [rbp+24A0h+var_2500.Params], rsi
0x18002ff7a  call    cs:__imp_DhcpRequestParams
0x18002ff80  mov     ebx, eax
0x18002ff82  cmp     eax, 0EAh
0x18002ff87  jnz     loc_18003001A
0x18002ff8d  mov     rcx, r13; hMem
0x18002ff90  call    cs:__imp_LocalFree
0x18002ff96  mov     edx, [rsp+25A0h+var_2544]; uBytes
0x18002ff9a  mov     ecx, 40h ; '@'; uFlags
0x18002ff9f  call    cs:__imp_LocalAlloc
0x18002ffa5  mov     [rbp+24A0h+var_2520], rax
0x18002ffa9  mov     r13, rax
0x18002ffac  test    rax, rax
0x18002ffaf  jnz     short loc_18003002F
0x18002ffb1  call    cs:__imp_GetLastError
0x18002ffb7  mov     ebx, eax
0x18002ffb9  cmp     eax, 0EAh
0x18002ffbe  jz      short loc_18003002F
0x18002ffc0  cmp     ebx, 2
0x18002ffc3  jnz     short loc_18002FFC9
0x18002ffc5  test    edi, edi
0x18002ffc7  jnz     short loc_18003002F
0x18002ffc9  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18002ffcf  jz      short loc_180030038
0x18002ffd1  cmp     cs:qword_18004C648, rsi
0x18002ffd8  jz      short loc_180030046
0x18002ffda  mov     r8d, ebx
0x18002ffdd  mov     word ptr [rbp+24A0h+var_850], si
0x18002ffe4  lea     rdx, aDhcprequestpar_1; "DhcpRequestParams done(%d)"
0x18002ffeb  lea     rcx, [rbp+24A0h+var_850]
0x18002fff2  call    FormatRRASErrorString
0x18002fff7  mov     rdx, cs:qword_18004C648
0x18002fffe  lea     r8, [rbp+24A0h+var_850]
0x180030005  mov     rcx, cs:gIphlpEtwContext
0x18003000c  mov     rax, cs:gIphlpTemplateFunc
0x180030013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030018  jmp     short loc_180030046
0x18003001a  cmp     eax, 2
0x18003001d  jnz     short loc_18002FFC0
0x18003001f  sub     edi, 1
0x180030022  jz      short loc_18002FFC9
0x180030024  mov     ecx, 3E8h; dwMilliseconds
0x180030029  call    cs:__imp_Sleep
0x18003002f  mov     ebx, [rsp+25A0h+var_2548]
0x180030033  jmp     loc_18002FEE8
0x180030038  mov     edx, ebx
0x18003003a  lea     rcx, aDhcprequestpar_4; "DhcpRequestParams done(%d)"
0x180030041  call    TraceHlp
0x180030046  test    ebx, ebx
0x180030048  jnz     loc_18002FE30
0x18003004e  mov     edx, esi
0x180030050  mov     r13d, esi
0x180030053  mov     dword ptr [rsp+25A0h+var_2550], edx
0x180030057  mov     edi, esi
0x180030059  mov     eax, esi
0x18003005b  mov     dword ptr [rsp+25A0h+var_2530], eax
0x18003005f  cmp     eax, [rsp+25A0h+var_2548]
0x180030063  jnb     loc_18003060F
0x180030069  mov     ebx, eax
0x18003006b  shl     rbx, 5
0x18003006f  mov     ecx, dword ptr [rbp+rbx+24A0h+var_90C]
0x180030076  sub     ecx, 1
0x180030079  jz      loc_180030427
0x18003007f  sub     ecx, 5
0x180030082  jz      loc_180030317
0x180030088  sub     ecx, 9
0x18003008b  jz      loc_18003025A
0x180030091  sub     ecx, 1Dh
0x180030094  jz      loc_18003016E
0x18003009a  cmp     ecx, 0CDh
0x1800300a0  jnz     loc_1800304DC
0x1800300a6  mov     edx, dword ptr [rbp+rbx+24A0h+Size]
0x1800300ad  test    edx, edx
0x1800300af  jz      loc_180030607
0x1800300b5  cmp     edx, 5
0x1800300b8  jb      loc_180030519
0x1800300be  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x1800300c4  jz      short loc_18003010F
0x1800300c6  cmp     cs:qword_18004C648, rsi
0x1800300cd  jz      short loc_18003011B
0x1800300cf  mov     r8d, edx
0x1800300d2  mov     word ptr [rbp+24A0h+var_850], si
0x1800300d9  lea     rdx, aDhcpinformOpti_0; "DhcpInform: OPTION_VENDOR_ROUTE_PLUMB C"...
0x1800300e0  lea     rcx, [rbp+24A0h+var_850]
0x1800300e7  call    FormatRRASErrorString
0x1800300ec  mov     rdx, cs:qword_18004C648
0x1800300f3  lea     r8, [rbp+24A0h+var_850]
0x1800300fa  mov     rcx, cs:gIphlpEtwContext
0x180030101  mov     rax, cs:gIphlpTemplateFunc
0x180030108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003010d  jmp     short loc_18003011B
0x18003010f  lea     rcx, aDhcpinformOpti_2; "DhcpInform: OPTION_VENDOR_ROUTE_PLUMB C"...
0x180030116  call    TraceHlp
0x18003011b  mov     edx, dword ptr [rbp+rbx+24A0h+Size]
0x180030122  mov     ecx, 40h ; '@'; uFlags
0x180030127  add     rdx, 4; uBytes
0x18003012b  call    cs:__imp_LocalAlloc
0x180030131  mov     [rsp+25A0h+hMem], rax
0x180030136  mov     rdi, rax
0x180030139  test    rax, rax
0x18003013c  jz      loc_1800304E7
0x180030142  mov     r8d, dword ptr [rbp+rbx+24A0h+Size]; Size
0x18003014a  lea     rcx, [rax+4]; void *
0x18003014e  mov     rdx, [rbp+rbx+24A0h+Src]; Src
0x180030156  call    memcpy_0
0x18003015b  mov     ecx, dword ptr [rbp+rbx+24A0h+Size]
0x180030162  mov     [rdi], ecx
0x180030164  mov     edi, 1
0x180030169  jmp     loc_1800304D8
0x18003016e  mov     edx, dword ptr [rbp+rbx+24A0h+Size]
0x180030175  test    edx, edx
0x180030177  jz      loc_180030607
0x18003017d  test    dl, 3
0x180030180  jnz     loc_180030550
0x180030186  xor     r14d, r14d
0x180030189  cmp     r14d, 2
0x18003018d  jge     loc_1800304D1
0x180030193  mov     r8, [rbp+rbx+24A0h+Src]
0x18003019b  lea     eax, [rsi+3]
0x18003019e  movzx   edx, byte ptr [rax+r8]
0x1800301a3  lea     eax, [rsi+2]
0x1800301a6  movzx   eax, byte ptr [rax+r8]
0x1800301ab  shl     eax, 10h
0x1800301ae  shl     edx, 18h
0x1800301b1  add     edx, eax
0x1800301b3  lea     eax, [rsi+1]
0x1800301b6  movzx   eax, byte ptr [rax+r8]
0x1800301bb  shl     eax, 8
0x1800301be  add     edx, eax
0x1800301c0  mov     eax, esi
0x1800301c2  movzx   ecx, byte ptr [rax+r8]
0x1800301c7  lea     rax, [rsp+25A0h+var_253C]
0x1800301cc  add     edx, ecx
0x1800301ce  lea     rcx, [rsp+25A0h+var_2540]
0x1800301d3  test    r14d, r14d
0x1800301d6  cmovz   rax, rcx
0x1800301da  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x1800301e1  mov     [rax], edx
0x1800301e3  jz      short loc_180030231
0x1800301e5  cmp     cs:qword_18004C648, 0
0x1800301ed  jz      short loc_18003023D
0x1800301ef  xor     eax, eax
  ... truncated ...
```

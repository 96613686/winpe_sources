# TraceW8ReturnCode(ushort *,uint)

- ea: `0x180024f08`
- end: `0x180027520`
- name: `?TraceW8ReturnCode@@YAJPEAGI@Z`
- size: `9752`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f650`

## callees

- `0x180023cdc`
- `0x180024f08`
- `0x180027528`
- `0x180059010`

## string_xrefs

- `0x180026392`: `TPM_RC_PARAMSIZE`
- `0x180026340`: `TPM_RC_COMMAND_CODE`

## pseudocode

```c
__int64 __fastcall TraceW8ReturnCode(unsigned __int16 *a1, unsigned int a2)
{
  int v4; // ebx
  int v5; // eax
  int v6; // ecx
  int v7; // eax
  int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  int v35; // eax
  int v36; // eax
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  int v61; // eax
  unsigned __int16 *v62; // rdi
  __int64 v64; // [rsp+30h] [rbp-30h]
  __int64 v65; // [rsp+30h] [rbp-30h]
  __int64 v66; // [rsp+30h] [rbp-30h]
  __int64 v67; // [rsp+38h] [rbp-28h]
  __int64 v68; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v69; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int64 v70; // [rsp+58h] [rbp-8h] BYREF
  unsigned __int64 v71; // [rsp+A0h] [rbp+40h] BYREF
  wchar_t *Buffer; // [rsp+A8h] [rbp+48h] BYREF

  v69 = 0;
  Buffer = 0;
  v70 = 0;
  v71 = 0;
  if ( !a2 )
  {
    while ( 1 )
    {
      v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      if ( v4 < 0 )
        break;
      if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"%sReturnCode = TPM_RC_SUCCESS\r\n", a1) != -2147024774 )
        goto LABEL_483;
    }
LABEL_486:
    v62 = v69;
    goto LABEL_487;
  }
  if ( a2 == 30 )
  {
    while ( 1 )
    {
      v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      if ( v4 < 0 )
        goto LABEL_486;
      LODWORD(v67) = 30;
      if ( (unsigned int)StringCchPrintfExW(
                           Buffer,
                           v71,
                           &Buffer,
                           &v71,
                           0,
                           L"%sReturnCode = TPM_RC_BAD_TAG (0x%08x)\r\n",
                           a1,
                           v67) != -2147024774 )
        goto LABEL_483;
    }
  }
  if ( (a2 & 0x80u) != 0 )
  {
    if ( (a2 & 0x40) != 0 )
    {
      while ( 1 )
      {
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        if ( v4 < 0 )
          goto LABEL_486;
        LODWORD(v67) = (a2 >> 8) & 0xF;
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"%sReturnCode = PARAMETER-%d: ", a1, v67) != -2147024774 )
          goto LABEL_324;
      }
    }
    if ( (a2 & 0x800) != 0 )
    {
      while ( 1 )
      {
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        if ( v4 < 0 )
          goto LABEL_486;
        LODWORD(v67) = (a2 >> 8) & 7;
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"%sReturnCode = SESSION-%d: ", a1, v67) != -2147024774 )
          goto LABEL_324;
      }
    }
    do
    {
      v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      if ( v4 < 0 )
        goto LABEL_486;
      LODWORD(v67) = (a2 >> 8) & 7;
      v36 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"%sReturnCode = HANDLE-%d: ", a1, v67);
    }
    while ( v36 == -2147024774 );
LABEL_324:
    v37 = a2 & 0xBF;
    if ( v37 > 0x92 )
    {
      if ( v37 > 0x9D )
      {
        v56 = v37 - 159;
        if ( !v56 )
        {
          while ( 1 )
          {
            v61 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_INTEGRITY");
            if ( v61 != -2147024774 )
              break;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
            if ( v4 < 0 )
              goto LABEL_486;
          }
LABEL_482:
          while ( 1 )
          {
            LODWORD(v66) = a2;
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L" (0x%08x)\r\n", v66) != -2147024774 )
              goto LABEL_483;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
            if ( v4 < 0 )
              goto LABEL_486;
          }
        }
        v57 = v56 - 1;
        if ( !v57 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_TICKET") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v58 = v57 - 1;
        if ( !v58 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_RESERVED_BITS") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v59 = v58 - 1;
        if ( !v59 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_BAD_AUTH") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v60 = v59 - 1;
        if ( !v60 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_EXPIRED") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        if ( v60 == 1 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_POLICY_CC") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
      }
      else
      {
        if ( v37 == 157 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_POLICY_FAIL") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v50 = v37 - 149;
        if ( !v50 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_SIZE") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v51 = v50 - 1;
        if ( !v51 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_SYMMETRIC") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v52 = v51 - 1;
        if ( !v52 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_TAG") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v53 = v52 - 1;
        if ( !v53 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_SELECTOR") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v54 = v53 - 2;
        if ( !v54 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_INSUFFICIENT") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v55 = v54 - 1;
        if ( !v55 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_SIGNATURE") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        if ( v55 == 1 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_KEY") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
      }
    }
    else
    {
      if ( v37 == 146 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_SCHEME") != -2147024774 )
            goto LABEL_482;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      if ( v37 > 0x89 )
      {
        v44 = v37 - 138;
        if ( !v44 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_TYPE") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v45 = v44 - 1;
        if ( !v45 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_HANDLE") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v46 = v45 - 1;
        if ( !v46 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_KDF") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v47 = v46 - 1;
        if ( !v47 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_RANGE") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v48 = v47 - 1;
        if ( !v48 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_AUTH_FAIL") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v49 = v48 - 1;
        if ( !v49 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_NONCE") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        if ( v49 == 1 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_PP") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
      }
      else
      {
        if ( v37 == 137 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_MODE") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v38 = v37 - 129;
        if ( !v38 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_ASYMMETRIC") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v39 = v38 - 1;
        if ( !v39 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_ATTRIBUTES") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v40 = v39 - 1;
        if ( !v40 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_HASH") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v41 = v40 - 1;
        if ( !v41 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_VALUE") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v42 = v41 - 1;
        if ( !v42 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_HIERARCHY") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        v43 = v42 - 2;
        if ( !v43 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_KEY_SIZE") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
        if ( v43 == 1 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_MGF") != -2147024774 )
              goto LABEL_482;
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
          }
          while ( v4 >= 0 );
          goto LABEL_486;
        }
      }
    }
    do
    {
      LODWORD(v66) = a2 & 0x3F;
      if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"UNKNOWN_FMT1(0x%03x)", v66) != -2147024774 )
        goto LABEL_482;
      v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
    }
    while ( v4 >= 0 );
    goto LABEL_486;
  }
  if ( (a2 & 0x400) != 0 )
  {
    while ( 1 )
    {
      v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      if ( v4 < 0 )
        goto LABEL_486;
      LODWORD(v68) = a2;
      LODWORD(v67) = a2 & 0x7F;
      if ( (unsigned int)StringCchPrintfExW(
                           Buffer,
                           v71,
                           &Buffer,
                           &v71,
                           0,
                           L"%sReturnCode = VENDORSPECIFIC(0x%03x) (0x%08x)\r\n",
                           a1,
                           v67,
                           v68) != -2147024774 )
        goto LABEL_483;
    }
  }
  if ( (a2 & 0x800) != 0 )
  {
    while ( 1 )
    {
      v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      if ( v4 < 0 )
        goto LABEL_486;
      v5 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"%sReturnCode = WARNING: ", a1);
      v6 = v5;
      if ( v5 != -2147024774 )
      {
        if ( v5 )
          v6 = -2147023537;
        switch ( a2 & 0xFFF )
        {
          case 0x901u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_CONTEXT_GAP");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x902u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_OBJECT_MEMORY");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x903u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_SESSION_MEMORY");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x904u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_MEMORY");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x905u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_SESSION_HANDLES");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x906u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_OBJECT_HANDLES");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x907u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_LOCALITY");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x908u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_YIELDED");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x909u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_CANCELLED");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x90Au:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_TESTING");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x910u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_H0");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x911u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_H1");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x912u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_H2");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x913u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_H3");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x914u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_H4");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x915u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_H5");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x916u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_H6");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x918u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_S0");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x919u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_S1");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Au:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_S2");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Bu:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_S3");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Cu:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_S4");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Du:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_S5");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Eu:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_S6");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Fu:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REFERENCE_S7");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x920u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_NV_RATE");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x921u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              v7 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_LOCKOUT");
              v6 = v7;
              if ( v7 != -2147024774 )
              {
LABEL_23:
                if ( v7 )
                  v6 = -2147023537;
                goto LABEL_134;
              }
            }
          default:
            break;
        }
        while ( 1 )
        {
          if ( v6 == -2147024774 )
          {
            v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
            if ( v4 < 0 )
              goto LABEL_486;
          }
          LODWORD(v64) = a2 & 0x7F;
          v8 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"UNKNOWN(0x%03x)", v64);
          v6 = v8;
          if ( v8 != -2147024774 )
          {
            if ( v8 )
              v6 = -2147023537;
LABEL_134:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
                if ( v4 < 0 )
                  goto LABEL_486;
              }
              LODWORD(v64) = a2;
              v6 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L" (0x%08x)\r\n", v64);
              if ( v6 != -2147024774 )
                goto LABEL_483;
            }
          }
        }
      }
    }
  }
  if ( (a2 & 0x100) == 0 )
  {
    while ( 1 )
    {
      v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      if ( v4 < 0 )
        goto LABEL_486;
      LODWORD(v68) = a2;
      LODWORD(v67) = a2 & 0x7F;
      if ( (unsigned int)StringCchPrintfExW(
                           Buffer,
                           v71,
                           &Buffer,
                           &v71,
                           0,
                           L"%sReturnCode = LEGACY(0x%03x) (0x%08x)\r\n",
                           a1,
                           v67,
                           v68) != -2147024774 )
        goto LABEL_483;
    }
  }
  do
  {
    v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
    if ( v4 < 0 )
      goto LABEL_486;
  }
  while ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"%sReturnCode = ERROR: ", a1) == -2147024774 );
  v9 = a2 & 0x1FF;
  if ( v9 <= 0x12F )
  {
    if ( v9 == 303 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_AUTH_UNAVAILABLE") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    if ( v9 > 0x124 )
    {
      v17 = v9 - 293;
      if ( !v17 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_AUTH_MISSING") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_POLICY") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v19 = v18 - 1;
      if ( !v19 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_PCR") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_PCR_CHANGED") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v21 = v20 - 4;
      if ( !v21 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_ECC_POINT") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_UPGRADE") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      if ( v22 == 1 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_TOO_MANY_CONTEXTS") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
    }
    else
    {
      if ( v9 == 292 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_AUTH_TYPE") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v10 = v9 - 256;
      if ( !v10 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_INITIALIZE") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v11 = v10 - 1;
      if ( !v11 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_FAILURE") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v12 = v11 - 2;
      if ( !v12 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_SEQUENCE") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v13 = v12 - 8;
      if ( !v13 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_PRIVATE") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v14 = v13 - 14;
      if ( !v14 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_HMAC") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v15 = v14 - 7;
      if ( !v15 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_DISABLED") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_EXCLUSIVE") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
      if ( v16 == 2 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_ECC_CURVE") != -2147024774 )
            goto LABEL_312;
          v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
        }
        while ( v4 >= 0 );
        goto LABEL_486;
      }
    }
    goto LABEL_281;
  }
  if ( v9 <= 0x149 )
  {
    if ( v9 == 329 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_NV_AUTHORIZATION") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    v23 = v9 - 304;
    if ( !v23 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_REBOOT") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    v24 = v23 - 18;
    if ( !v24 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_PARAMSIZE") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    v25 = v24 - 1;
    if ( !v25 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_COMMAND_CODE") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    v26 = v25 - 1;
    if ( !v26 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_AUTHSIZE") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    v27 = v26 - 2;
    if ( !v27 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_NV_RANGE") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    v28 = v27 - 1;
    if ( !v28 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_NV_SIZE") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    if ( v28 == 1 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_NV_LOCKED") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    goto LABEL_281;
  }
  v29 = v9 - 330;
  if ( v29 )
  {
    v30 = v29 - 1;
    if ( !v30 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_NV_SPACE") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    v31 = v30 - 1;
    if ( !v31 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_NV_DEFINED") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    v32 = v31 - 4;
    if ( !v32 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_BAD_CONTEXT") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    v33 = v32 - 1;
    if ( !v33 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_CPHASH") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    v34 = v33 - 1;
    if ( !v34 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_PARENT") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    if ( v34 == 1 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_NEEDS_TEST") != -2147024774 )
          goto LABEL_312;
        v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
      }
      while ( v4 >= 0 );
      goto LABEL_486;
    }
    do
    {
LABEL_281:
      LODWORD(v65) = a2 & 0x7F;
      if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"UNKNOWN(0x%03x)", v65) != -2147024774 )
        goto LABEL_312;
      v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
    }
    while ( v4 >= 0 );
    goto LABEL_486;
  }
  while ( 1 )
  {
    v35 = StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L"TPM_RC_NV_UNINITIALIZED");
    if ( v35 != -2147024774 )
      break;
    v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
    if ( v4 < 0 )
      goto LABEL_486;
  }
LABEL_312:
  while ( 1 )
  {
    LODWORD(v65) = a2;
    if ( (unsigned int)StringCchPrintfExW(Buffer, v71, &Buffer, &v71, 0, L" (0x%08x)\r\n", v65) != -2147024774 )
      break;
    v4 = TracepGetBuffer(&v69, &Buffer, &v70, &v71);
    if ( v4 < 0 )
      goto LABEL_486;
  }
LABEL_483:
  v62 = v69;
  if ( g_fpFlushTrace )
    v4 = g_fpFlushTrace(v69, v70 - v71);
  else
    v4 = -2147467263;
LABEL_487:
  if ( g_fpFreeMemory )
    g_fpFreeMemory(v62);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180024f08  mov     [rsp-28h+arg_0], rbx
0x180024f0d  mov     [rsp-28h+arg_8], rsi
0x180024f12  push    rbp
0x180024f13  push    rdi
0x180024f14  push    r12
0x180024f16  push    r14
0x180024f18  push    r15
0x180024f1a  mov     rbp, rsp
0x180024f1d  sub     rsp, 60h
0x180024f21  xor     r12d, r12d
0x180024f24  mov     r15d, edx
0x180024f27  mov     [rbp+var_10], r12
0x180024f2b  mov     r14, rcx
0x180024f2e  mov     [rbp+Buffer], r12
0x180024f32  mov     edi, 8007007Ah
0x180024f37  mov     [rbp+var_8], r12
0x180024f3b  mov     [rbp+arg_10], r12
0x180024f3f  test    edx, edx
0x180024f41  jnz     short loc_180024F96
0x180024f43  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180024f47  lea     r8, [rbp+var_8]; unsigned __int64 *
0x180024f4b  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x180024f4f  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x180024f53  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x180024f58  mov     ebx, eax
0x180024f5a  test    eax, eax
0x180024f5c  js      loc_180027468
0x180024f62  mov     rdx, [rbp+arg_10]; unsigned __int64
0x180024f66  lea     rax, aSreturncodeTpm; "%sReturnCode = TPM_RC_SUCCESS\r\n"
0x180024f6d  mov     rcx, [rbp+Buffer]; Buffer
0x180024f71  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180024f75  mov     [rsp+60h+var_30], r14
0x180024f7a  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x180024f7e  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180024f83  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x180024f88  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180024f8d  cmp     eax, edi
0x180024f8f  jz      short loc_180024F43
0x180024f91  jmp     loc_18002743D
0x180024f96  cmp     r15d, 1Eh
0x180024f9a  jnz     short loc_180024FF7
0x180024f9c  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180024fa0  lea     r8, [rbp+var_8]; unsigned __int64 *
0x180024fa4  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x180024fa8  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x180024fac  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x180024fb1  mov     ebx, eax
0x180024fb3  test    eax, eax
0x180024fb5  js      loc_180027468
0x180024fbb  mov     rdx, [rbp+arg_10]; unsigned __int64
0x180024fbf  lea     rax, aSreturncodeTpm_0; "%sReturnCode = TPM_RC_BAD_TAG (0x%08x)"...
0x180024fc6  mov     rcx, [rbp+Buffer]; Buffer
0x180024fca  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180024fce  mov     dword ptr [rsp+60h+var_28], 1Eh
0x180024fd6  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x180024fda  mov     [rsp+60h+var_30], r14
0x180024fdf  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180024fe4  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x180024fe9  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180024fee  cmp     eax, edi
0x180024ff0  jz      short loc_180024F9C
0x180024ff2  jmp     loc_18002743D
0x180024ff7  test    r15b, r15b
0x180024ffa  js      loc_180026790
0x180025000  bt      r15d, 0Ah
0x180025005  jnb     short loc_180025069
0x180025007  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x18002500b  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18002500f  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x180025013  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x180025017  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x18002501c  mov     ebx, eax
0x18002501e  test    eax, eax
0x180025020  js      loc_180027468
0x180025026  mov     rdx, [rbp+arg_10]; unsigned __int64
0x18002502a  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x18002502e  mov     rcx, [rbp+Buffer]; Buffer
0x180025032  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x180025036  mov     [rsp+60h+var_20], r15d
0x18002503b  mov     eax, r15d
0x18002503e  and     eax, 7Fh
0x180025041  mov     dword ptr [rsp+60h+var_28], eax
0x180025045  lea     rax, aSreturncodeVen; "%sReturnCode = VENDORSPECIFIC(0x%03x) ("...
0x18002504c  mov     [rsp+60h+var_30], r14
0x180025051  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180025056  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x18002505b  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180025060  cmp     eax, edi
0x180025062  jz      short loc_180025007
0x180025064  jmp     loc_18002743D
0x180025069  bt      r15d, 0Bh
0x18002506e  jnb     loc_180025A95
0x180025074  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180025078  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18002507c  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x180025080  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x180025084  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x180025089  mov     ebx, eax
0x18002508b  test    eax, eax
0x18002508d  js      loc_180027468
0x180025093  mov     rdx, [rbp+arg_10]; unsigned __int64
0x180025097  lea     rax, aSreturncodeWar; "%sReturnCode = WARNING: "
0x18002509e  mov     rcx, [rbp+Buffer]; Buffer
0x1800250a2  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800250a6  mov     [rsp+60h+var_30], r14
0x1800250ab  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x1800250af  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800250b4  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800250b9  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800250be  mov     ecx, eax
0x1800250c0  cmp     eax, edi
0x1800250c2  jz      short loc_180025074
0x1800250c4  test    eax, eax
0x1800250c6  mov     esi, 8007054Fh
0x1800250cb  mov     eax, r15d
0x1800250ce  cmovnz  ecx, esi
0x1800250d1  and     eax, 0FFFh
0x1800250d6  add     eax, 0FFFFF6FFh; switch 33 cases
0x1800250db  cmp     eax, 20h
0x1800250de  ja      def_1800250F5; jumptable 00000001800250F5 default case, cases 2315-2319,2327
0x1800250e4  lea     rdx, __ImageBase
0x1800250eb  mov     eax, ds:(jpt_1800250F5 - 180000000h)[rdx+rax*4]
0x1800250f2  add     rax, rdx
0x1800250f5  jmp     rax; switch jump
0x1800250fb  cmp     ecx, edi; jumptable 00000001800250F5 case 2305
0x1800250fd  jnz     short loc_18002511E
0x1800250ff  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180025103  lea     r8, [rbp+var_8]; unsigned __int64 *
0x180025107  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x18002510b  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x18002510f  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x180025114  mov     ebx, eax
0x180025116  test    eax, eax
0x180025118  js      loc_180027468
0x18002511e  mov     rdx, [rbp+arg_10]; unsigned __int64
0x180025122  lea     rax, aTpmRcContextGa; "TPM_RC_CONTEXT_GAP"
0x180025129  mov     rcx, [rbp+Buffer]; Buffer
0x18002512d  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180025131  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180025136  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x18002513a  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x18002513f  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180025144  mov     ecx, eax
0x180025146  cmp     eax, edi
0x180025148  jz      short loc_1800250FB; jumptable 00000001800250F5 case 2305
0x18002514a  test    eax, eax
0x18002514c  jz      loc_180025A3C
0x180025152  mov     ecx, esi
0x180025154  jmp     loc_180025A3C
0x180025159  cmp     ecx, edi; jumptable 00000001800250F5 case 2306
0x18002515b  jnz     short loc_18002517C
0x18002515d  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180025161  lea     r8, [rbp+var_8]; unsigned __int64 *
0x180025165  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x180025169  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x18002516d  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x180025172  mov     ebx, eax
0x180025174  test    eax, eax
0x180025176  js      loc_180027468
0x18002517c  mov     rdx, [rbp+arg_10]; unsigned __int64
0x180025180  lea     rax, aTpmRcObjectMem; "TPM_RC_OBJECT_MEMORY"
0x180025187  mov     rcx, [rbp+Buffer]; Buffer
0x18002518b  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x18002518f  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180025194  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x180025198  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x18002519d  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800251a2  mov     ecx, eax
0x1800251a4  cmp     eax, edi
0x1800251a6  jz      short loc_180025159; jumptable 00000001800250F5 case 2306
0x1800251a8  jmp     short loc_18002514A
0x1800251aa  cmp     ecx, edi; jumptable 00000001800250F5 case 2307
0x1800251ac  jnz     short loc_1800251CD
0x1800251ae  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800251b2  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800251b6  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x1800251ba  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800251be  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800251c3  mov     ebx, eax
0x1800251c5  test    eax, eax
0x1800251c7  js      loc_180027468
0x1800251cd  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800251d1  lea     rax, aTpmRcSessionMe; "TPM_RC_SESSION_MEMORY"
0x1800251d8  mov     rcx, [rbp+Buffer]; Buffer
0x1800251dc  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800251e0  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800251e5  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x1800251e9  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800251ee  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800251f3  mov     ecx, eax
0x1800251f5  cmp     eax, edi
0x1800251f7  jz      short loc_1800251AA; jumptable 00000001800250F5 case 2307
0x1800251f9  jmp     loc_18002514A
0x1800251fe  cmp     ecx, edi; jumptable 00000001800250F5 case 2308
0x180025200  jnz     short loc_180025221
0x180025202  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180025206  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18002520a  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x18002520e  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x180025212  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x180025217  mov     ebx, eax
0x180025219  test    eax, eax
0x18002521b  js      loc_180027468
0x180025221  mov     rdx, [rbp+arg_10]; unsigned __int64
0x180025225  lea     rax, aTpmRcMemory; "TPM_RC_MEMORY"
0x18002522c  mov     rcx, [rbp+Buffer]; Buffer
0x180025230  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180025234  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180025239  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x18002523d  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x180025242  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180025247  mov     ecx, eax
0x180025249  cmp     eax, edi
0x18002524b  jz      short loc_1800251FE; jumptable 00000001800250F5 case 2308
0x18002524d  jmp     loc_18002514A
0x180025252  cmp     ecx, edi; jumptable 00000001800250F5 case 2309
0x180025254  jnz     short loc_180025275
0x180025256  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x18002525a  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18002525e  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x180025262  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x180025266  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x18002526b  mov     ebx, eax
0x18002526d  test    eax, eax
0x18002526f  js      loc_180027468
0x180025275  mov     rdx, [rbp+arg_10]; unsigned __int64
0x180025279  lea     rax, aTpmRcSessionHa; "TPM_RC_SESSION_HANDLES"
0x180025280  mov     rcx, [rbp+Buffer]; Buffer
0x180025284  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180025288  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x18002528d  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x180025291  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x180025296  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18002529b  mov     ecx, eax
0x18002529d  cmp     eax, edi
0x18002529f  jz      short loc_180025252; jumptable 00000001800250F5 case 2309
0x1800252a1  jmp     loc_18002514A
0x1800252a6  cmp     ecx, edi; jumptable 00000001800250F5 case 2310
0x1800252a8  jnz     short loc_1800252C9
0x1800252aa  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800252ae  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800252b2  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x1800252b6  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800252ba  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800252bf  mov     ebx, eax
0x1800252c1  test    eax, eax
0x1800252c3  js      loc_180027468
0x1800252c9  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800252cd  lea     rax, aTpmRcObjectHan; "TPM_RC_OBJECT_HANDLES"
0x1800252d4  mov     rcx, [rbp+Buffer]; Buffer
0x1800252d8  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800252dc  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800252e1  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x1800252e5  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800252ea  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800252ef  mov     ecx, eax
0x1800252f1  cmp     eax, edi
0x1800252f3  jz      short loc_1800252A6; jumptable 00000001800250F5 case 2310
0x1800252f5  jmp     loc_18002514A
0x1800252fa  cmp     ecx, edi; jumptable 00000001800250F5 case 2311
0x1800252fc  jnz     short loc_18002531D
0x1800252fe  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180025302  lea     r8, [rbp+var_8]; unsigned __int64 *
0x180025306  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x18002530a  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x18002530e  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x180025313  mov     ebx, eax
0x180025315  test    eax, eax
0x180025317  js      loc_180027468
0x18002531d  mov     rdx, [rbp+arg_10]; unsigned __int64
0x180025321  lea     rax, aTpmRcLocality; "TPM_RC_LOCALITY"
0x180025328  mov     rcx, [rbp+Buffer]; Buffer
0x18002532c  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180025330  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180025335  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x180025339  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x18002533e  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180025343  mov     ecx, eax
0x180025345  cmp     eax, edi
0x180025347  jz      short loc_1800252FA; jumptable 00000001800250F5 case 2311
0x180025349  jmp     loc_18002514A
0x18002534e  cmp     ecx, edi; jumptable 00000001800250F5 case 2312
0x180025350  jnz     short loc_180025371
0x180025352  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180025356  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18002535a  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x18002535e  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x180025362  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x180025367  mov     ebx, eax
0x180025369  test    eax, eax
0x18002536b  js      loc_180027468
0x180025371  mov     rdx, [rbp+arg_10]; unsigned __int64
0x180025375  lea     rax, aTpmRcYielded; "TPM_RC_YIELDED"
0x18002537c  mov     rcx, [rbp+Buffer]; Buffer
0x180025380  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180025384  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180025389  lea     r8, [rbp+Buffer]; unsigned __int16 **
0x18002538d  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x180025392  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180025397  mov     ecx, eax
  ... truncated ...
```

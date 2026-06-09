# CL2TPDiagHelper::GetLowerHypotheses(ulong *,tagHYPOTHESIS * *)

- ea: `0x18000ad60`
- end: `0x18000b600`
- name: `?GetLowerHypotheses@CL2TPDiagHelper@@UEAAJPEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `2208`
- prototype: `__int64 __fastcall(CL2TPDiagHelper *__hidden this, unsigned int *, struct tagHYPOTHESIS **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002676`
- `0x180006100`
- `0x180006274`
- `0x18000678c`
- `0x180006800`
- `0x180008084`
- `0x18000ad60`
- `0x18000b864`
- `0x18000bd1c`
- `0x18000beb8`
- `0x18000c310`
- `0x18000ca8c`
- `0x18000dab4`
- `0x18000dc5c`
- `0x18000df10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000af94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b0c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b1fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b2fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b38d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b44a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000af94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b0c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b1fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b2fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b38d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b44a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b072`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b1a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b3fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b5ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b072`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b1a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b3fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b5ae`

## string_xrefs

- `0x18000aebc`: `%systemroot%\system32\svchost.exe`
- `0x18000b1c2`: `protocol`
- `0x18000aea0`: `CL2TPDiagHelper::GetLowerHypotheses - Failed to get the process SID: 0x%x.`

## pseudocode

```c
__int64 __fastcall CL2TPDiagHelper::GetLowerHypotheses(
        CL2TPDiagHelper *this,
        unsigned int *a2,
        struct tagHYPOTHESIS **a3)
{
  char *v4; // r14
  char *v5; // r15
  char *v6; // rbx
  int RasEntryProperties; // eax
  signed int inited; // esi
  union tagHELPER_ATTRIBUTE::$E73CE4DD3AF9771F1CA4F78E7E603792 *v9; // r14
  union tagHELPER_ATTRIBUTE::$E73CE4DD3AF9771F1CA4F78E7E603792 *v10; // r13
  int ProcessSID; // eax
  WCHAR *v12; // r8
  __int64 v13; // rdx
  const wchar_t *v14; // r15
  const wchar_t *v15; // rax
  __int64 v16; // rdi
  WCHAR *v17; // rax
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  wchar_t v20; // r9
  WCHAR *v21; // rcx
  struct tagHELPER_ATTRIBUTE *v22; // r15
  WCHAR *v23; // r8
  __int64 v24; // rdx
  const wchar_t *v25; // r14
  const wchar_t *v26; // rax
  __int64 v27; // rdi
  WCHAR *v28; // rax
  unsigned __int64 v29; // rdx
  __int64 v30; // rcx
  wchar_t v31; // r9
  WCHAR *v32; // rcx
  WCHAR *v33; // r8
  __int64 v34; // rdx
  const wchar_t *v35; // r14
  const wchar_t *v36; // rax
  __int64 v37; // rdi
  WCHAR *v38; // rax
  unsigned __int64 v39; // rdx
  __int64 v40; // r13
  __int64 v41; // rcx
  wchar_t v42; // r9
  WCHAR *v43; // rcx
  WCHAR *v44; // rdi
  __int64 v45; // rdx
  const wchar_t *v46; // r15
  const wchar_t *v47; // rax
  __int64 v48; // r14
  WCHAR *v49; // rax
  unsigned __int64 v50; // rdx
  __int64 v51; // rcx
  wchar_t v52; // r8
  WCHAR *v53; // rcx
  unsigned int v54; // r14d
  void *v55; // rax
  int v56; // eax
  struct tagHELPER_ATTRIBUTE *v57; // r15
  __int64 v58; // rcx
  const wchar_t *v59; // r14
  const wchar_t *v60; // rax
  __int64 v61; // rdi
  WCHAR *v62; // rax
  unsigned __int64 v63; // rdx
  __int64 v64; // rcx
  wchar_t v65; // r8
  WCHAR *v66; // rcx
  int v67; // eax
  ATTRIBUTE_TYPE v68; // ecx
  unsigned int *v69; // r9
  _QWORD *v70; // r14
  _WORD *v71; // rax
  void *v72; // rdi
  __int16 *v73; // rcx
  __int64 v74; // rdx
  __int16 v75; // r8
  _WORD *v76; // rcx
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v79; // [rsp+50h] [rbp-B0h]
  _attribute_t *v80[2]; // [rsp+58h] [rbp-A8h]
  struct tagHELPER_ATTRIBUTE v81; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v82; // [rsp+F8h] [rbp-8h]
  struct tagHYPOTHESIS **v83; // [rsp+100h] [rbp+0h]
  unsigned int *v84; // [rsp+108h] [rbp+8h]
  SIZE_T cb[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v86[8]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v87; // [rsp+130h] [rbp+30h]
  __int128 v88; // [rsp+140h] [rbp+40h]
  __int128 v89; // [rsp+150h] [rbp+50h]
  int v90; // [rsp+160h] [rbp+60h]

  v83 = a3;
  v84 = a2;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v4 = (char *)this + 120;
    v5 = (char *)this + 634;
    v6 = (char *)this + 1424;
    v82 = (_QWORD *)((char *)this + 1424);
    RasEntryProperties = GetRasEntryProperties(
                           (LPCWSTR)this + 317,
                           (LPCWSTR)this + 60,
                           (struct tagRASENTRYW **)this + 178);
    inited = RasEntryProperties;
    if ( RasEntryProperties >= 0 )
    {
      v9 = (union tagHELPER_ATTRIBUTE::$E73CE4DD3AF9771F1CA4F78E7E603792 *)((char *)this + 1296);
      v10 = (union tagHELPER_ATTRIBUTE::$E73CE4DD3AF9771F1CA4F78E7E603792 *)((char *)this + 1168);
      inited = InitSockAddresses(
                 (PCWSTR)(*(_QWORD *)v6 + 38LL),
                 1701,
                 (struct sockaddr_storage *)((char *)this + 1168),
                 (struct sockaddr_storage *)((char *)this + 1296),
                 1);
      if ( inited >= 0 )
      {
        *(_OWORD *)pv = 0;
        v79 = 0;
        *(_OWORD *)v80 = 0;
        *(_OWORD *)cb = 0;
        ProcessSID = GetProcessSID((struct tagOCTET_STRING *)cb);
        inited = ProcessSID;
        if ( ProcessSID >= 0 )
        {
          *(_OWORD *)v86 = *(_OWORD *)L"%systemroot%\\system32\\svchost.exe";
          v87 = *(_OWORD *)L"oot%\\system32\\svchost.exe";
          v88 = *(_OWORD *)L"tem32\\svchost.exe";
          v89 = *(_OWORD *)L"chost.exe";
          v90 = *(_DWORD *)L"e";
          _hypothesis_builder::FreeAll(pv);
          CoTaskMemFree(pv[0]);
          pv[0] = 0;
          if ( (int)StringCchCopyWithAlloc((unsigned __int16 **)pv, 0xFFFFu, L"TransportConnection") >= 0 )
            _hypothesis_builder::SetCount((_hypothesis_builder *)pv, 5u);
          CoTaskMemFree(0);
          v12 = 0;
          v81.pwszName = 0;
          v13 = 65534;
          v14 = L"remoteaddr";
          v15 = L"remoteaddr";
          do
          {
            if ( !*v15 )
              break;
            ++v15;
            --v13;
          }
          while ( v13 );
          v16 = (65534 - v13) & -(__int64)(v13 != 0);
          if ( v13 )
          {
            v17 = (WCHAR *)CoTaskMemAlloc(2 * v16 + 2);
            v12 = v17;
            v81.pwszName = v17;
            if ( v17 )
            {
              v18 = v16 + 1;
              if ( v16 != -1 )
              {
                if ( v18 <= 0x7FFFFFFF )
                {
                  v19 = 2147483646;
                  do
                  {
                    if ( !v19 )
                      break;
                    v20 = *v14;
                    if ( !*v14 )
                      break;
                    ++v14;
                    *v17++ = v20;
                    --v19;
                    --v18;
                  }
                  while ( v18 );
                  v21 = v17 - 1;
                  if ( v18 )
                    v21 = v17;
                  *v21 = 0;
                }
                else
                {
                  *v17 = 0;
                }
              }
            }
          }
          v81.type = AT_SOCKADDR;
          v81.16 = *v9;
          v22 = (struct tagHELPER_ATTRIBUTE *)v80[0];
          if ( v12 )
            _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)v80[0], &v81);
          _attribute_t::FreeAll((LPVOID *)&v81.pwszName);
          CoTaskMemFree(0);
          v23 = 0;
          v81.pwszName = 0;
          v24 = 65534;
          v25 = L"localaddr";
          v26 = L"localaddr";
          do
          {
            if ( !*v26 )
              break;
            ++v26;
            --v24;
          }
          while ( v24 );
          v27 = (65534 - v24) & -(__int64)(v24 != 0);
          if ( v24 )
          {
            v28 = (WCHAR *)CoTaskMemAlloc(2 * v27 + 2);
            v23 = v28;
            v81.pwszName = v28;
            if ( v28 )
            {
              v29 = v27 + 1;
              if ( v27 != -1 )
              {
                if ( v29 <= 0x7FFFFFFF )
                {
                  v30 = 2147483646;
                  do
                  {
                    if ( !v30 )
                      break;
                    v31 = *v25;
                    if ( !*v25 )
                      break;
                    ++v25;
                    *v28++ = v31;
                    --v30;
                    --v29;
                  }
                  while ( v29 );
                  v32 = v28 - 1;
                  if ( v29 )
                    v32 = v28;
                  *v32 = 0;
                }
                else
                {
                  *v28 = 0;
                }
              }
            }
          }
          v81.type = AT_SOCKADDR;
          v81.16 = *v10;
          if ( v79 && v23 )
            _attribute_t::Copy(v22 + 1, &v81);
          _attribute_t::FreeAll((LPVOID *)&v81.pwszName);
          CoTaskMemFree(0);
          v33 = 0;
          v81.pwszName = 0;
          v34 = 65534;
          v35 = L"protocol";
          v36 = L"protocol";
          do
          {
            if ( !*v36 )
              break;
            ++v36;
            --v34;
          }
          while ( v34 );
          v37 = (65534 - v34) & -(__int64)(v34 != 0);
          if ( v34
            && (v38 = (WCHAR *)CoTaskMemAlloc(2 * v37 + 2), v33 = v38, (v81.pwszName = v38) != 0)
            && (v39 = v37 + 1, v37 != -1) )
          {
            v40 = 2147483646;
            if ( v39 <= 0x7FFFFFFF )
            {
              v41 = 2147483646;
              do
              {
                if ( !v41 )
                  break;
                v42 = *v35;
                if ( !*v35 )
                  break;
                ++v35;
                *v38++ = v42;
                --v41;
                --v39;
              }
              while ( v39 );
              v43 = v38 - 1;
              if ( v39 )
                v43 = v38;
              *v43 = 0;
            }
            else
            {
              *v38 = 0;
            }
          }
          else
          {
            v40 = 2147483646;
          }
          v81.type = AT_UINT32;
          v81.Boolean = 17;
          if ( v79 >= 2 && v33 )
            _attribute_t::Copy(v22 + 2, &v81);
          _attribute_t::FreeAll((LPVOID *)&v81.pwszName);
          CoTaskMemFree(0);
          v44 = 0;
          v81.pwszName = 0;
          v45 = 65534;
          v46 = L"userid";
          v47 = L"userid";
          do
          {
            if ( !*v47 )
              break;
            ++v47;
            --v45;
          }
          while ( v45 );
          v48 = (65534 - v45) & -(__int64)(v45 != 0);
          if ( v45 )
          {
            v49 = (WCHAR *)CoTaskMemAlloc(2 * v48 + 2);
            v44 = v49;
            v81.pwszName = v49;
            if ( v49 )
            {
              v50 = v48 + 1;
              if ( v48 != -1 )
              {
                if ( v50 <= 0x7FFFFFFF )
                {
                  v51 = 2147483646;
                  do
                  {
                    if ( !v51 )
                      break;
                    v52 = *v46;
                    if ( !*v46 )
                      break;
                    ++v46;
                    *v49++ = v52;
                    --v51;
                    --v50;
                  }
                  while ( v50 );
                  v53 = v49 - 1;
                  if ( v50 )
                    v53 = v49;
                  *v53 = 0;
                }
                else
                {
                  *v49 = 0;
                }
              }
            }
          }
          CoTaskMemFree(0);
          v81.OctetString.lpValue = 0;
          v81.Boolean = 0;
          v54 = cb[0];
          if ( LODWORD(cb[0]) < 0xFFFF
            && (v55 = CoTaskMemAlloc(LODWORD(cb[0])), (v81.OctetString.lpValue = (BYTE *)v55) != 0) )
          {
            memcpy_0(v55, (const void *)cb[1], v54);
            v81.Boolean = v54;
            v56 = 14;
            v81.type = AT_OCTET_STRING;
          }
          else
          {
            v81.type = AT_INVALID;
            v56 = 0;
          }
          v57 = (struct tagHELPER_ATTRIBUTE *)v80[0];
          if ( v79 >= 3 && v56 && v44 )
            _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)v80[0] + 3, &v81);
          _attribute_t::FreeAll((LPVOID *)&v81.pwszName);
          CoTaskMemFree(0);
          v81.pwszName = 0;
          v58 = 65534;
          v59 = L"appid";
          v60 = L"appid";
          do
          {
            if ( !*v60 )
              break;
            ++v60;
            --v58;
          }
          while ( v58 );
          v61 = (65534 - v58) & -(__int64)(v58 != 0);
          if ( v58 )
          {
            v62 = (WCHAR *)CoTaskMemAlloc(2 * v61 + 2);
            v81.pwszName = v62;
            if ( v62 )
            {
              v63 = v61 + 1;
              if ( v61 != -1 )
              {
                if ( v63 <= 0x7FFFFFFF )
                {
                  v64 = 2147483646;
                  do
                  {
                    if ( !v64 )
                      break;
                    v65 = *v59;
                    if ( !*v59 )
                      break;
                    ++v59;
                    *v62++ = v65;
                    --v64;
                    --v63;
                  }
                  while ( v63 );
                  v66 = v62 - 1;
                  if ( v63 )
                    v66 = v62;
                  *v66 = 0;
                }
                else
                {
                  *v62 = 0;
                }
              }
            }
          }
          v81.type = AT_STRING;
          CoTaskMemFree(0);
          v81.Int64 = 0;
          v67 = StringCchCopyWithAlloc(&v81.PWStr, 0xFFFFu, v86);
          v68 = AT_INVALID;
          if ( v67 >= 0 )
            v68 = AT_STRING;
          v81.type = v68;
          if ( v79 >= 4 && ((v67 >> 31) & 0xFFFFFFF6) != 0xFFFFFFF6 && v81.pwszName )
            _attribute_t::Copy(v57 + 4, &v81);
          _attribute_t::FreeAll((LPVOID *)&v81.pwszName);
          v70 = v82;
          if ( *v82 != -38 )
          {
            v71 = CoTaskMemAlloc(0x102u);
            v72 = v71;
            v73 = (__int16 *)(*v70 + 38LL);
            v74 = 129;
            do
            {
              if ( !v40 )
                break;
              v75 = *v73;
              if ( !*v73 )
                break;
              ++v73;
              *v71++ = v75;
              --v40;
              --v74;
            }
            while ( v74 );
            v76 = v71 - 1;
            if ( v74 )
              v76 = v71;
            *v76 = 0;
            inited = v74 == 0 ? 0x8007007A : 0;
            if ( v74 )
            {
              CoTaskMemFree(pv[1]);
              pv[1] = v72;
            }
            else
            {
              CoTaskMemFree(v72);
            }
          }
          _hypothesis_builder::Detach((_hypothesis_builder *)pv, v84, v83, v69);
        }
        else
        {
          RasDiagTrace("CL2TPDiagHelper::GetLowerHypotheses - Failed to get the process SID: 0x%x.", ProcessSID);
        }
        _hypothesis_builder::~_hypothesis_builder(pv);
      }
      else
      {
        CRasLogger::Log((char *)this + 112, 2, 1, L"CL2TPDiagHelper", L"Socket address initialization failed.");
      }
    }
    else
    {
      CRasLogger::Log(
        (char *)this + 112,
        2,
        1,
        L"CL2TPDiagHelper",
        L"RasGetEntryProperties(%s,%s) failed with error: 0x%x.",
        v5,
        v4,
        RasEntryProperties);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000ad60  mov     [rsp-8+arg_18], rbx
0x18000ad65  push    rbp
0x18000ad66  push    rsi
0x18000ad67  push    rdi
0x18000ad68  push    r12
0x18000ad6a  push    r13
0x18000ad6c  push    r14
0x18000ad6e  push    r15
0x18000ad70  lea     rbp, [rsp-80h]
0x18000ad75  sub     rsp, 180h
0x18000ad7c  mov     rax, cs:__security_cookie
0x18000ad83  xor     rax, rsp
0x18000ad86  mov     [rbp+0B0h+var_40], rax
0x18000ad8a  mov     rax, r8
0x18000ad8d  mov     [rbp+0B0h+var_B0], rax
0x18000ad91  mov     [rbp+0B0h+var_A8], rdx
0x18000ad95  mov     rdi, rcx
0x18000ad98  xor     r12d, r12d
0x18000ad9b  test    rdx, rdx
0x18000ad9e  jz      loc_18000B5D1
0x18000ada4  test    rax, rax
0x18000ada7  jz      loc_18000B5D1
0x18000adad  mov     [rdx], r12d
0x18000adb0  mov     [r8], r12
0x18000adb3  lea     r14, [rcx+78h]
0x18000adb7  lea     r15, [rcx+27Ah]
0x18000adbe  lea     rbx, [rcx+590h]
0x18000adc5  mov     [rbp+0B0h+var_B8], rbx
0x18000adc9  mov     r8, rbx; struct tagRASENTRYW **
0x18000adcc  mov     rdx, r14; LPCWSTR
0x18000adcf  mov     rcx, r15; LPCWSTR
0x18000add2  call    ?GetRasEntryProperties@@YAJPEBG0PEAPEAUtagRASENTRYW@@@Z; GetRasEntryProperties(ushort const *,ushort const *,tagRASENTRYW * *)
0x18000add7  mov     esi, eax
0x18000add9  test    eax, eax
0x18000addb  jns     short loc_18000AE18
0x18000addd  lea     ebx, [r12+1]
0x18000ade2  lea     rcx, [rdi+70h]
0x18000ade6  mov     [rsp+1B0h+var_178], eax
0x18000adea  mov     [rsp+1B0h+var_180], r14
0x18000adef  mov     [rsp+1B0h+var_188], r15
0x18000adf4  lea     rax, aRasgetentrypro_0; "RasGetEntryProperties(%s,%s) failed wit"...
0x18000adfb  mov     qword ptr [rsp+1B0h+var_190], rax
0x18000ae00  lea     r9, aCl2tpdiaghelpe; "CL2TPDiagHelper"
0x18000ae07  movsx   r8d, bx
0x18000ae0b  lea     edx, [rbx+1]
0x18000ae0e  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x18000ae13  jmp     loc_18000B5D6
0x18000ae18  lea     r14, [rdi+510h]
0x18000ae1f  lea     r13, [rdi+490h]
0x18000ae26  mov     edx, 6A5h; __int16
0x18000ae2b  mov     rcx, [rbx]
0x18000ae2e  add     rcx, 26h ; '&'; pNodeName
0x18000ae32  mov     ebx, 1
0x18000ae37  mov     [rsp+1B0h+var_190], ebx; int
0x18000ae3b  mov     r9, r14; struct sockaddr_storage *
0x18000ae3e  mov     r8, r13; struct sockaddr_storage *
0x18000ae41  call    ?InitSockAddresses@@YAJPEBGFPEAUsockaddr_storage@@1H@Z; InitSockAddresses(ushort const *,short,sockaddr_storage *,sockaddr_storage *,int)
0x18000ae46  mov     esi, eax
0x18000ae48  test    eax, eax
0x18000ae4a  jns     short loc_18000AE74
0x18000ae4c  lea     rcx, [rdi+70h]
0x18000ae50  lea     rax, aSocketAddressI; "Socket address initialization failed."
0x18000ae57  mov     qword ptr [rsp+1B0h+var_190], rax
0x18000ae5c  lea     r9, aCl2tpdiaghelpe; "CL2TPDiagHelper"
0x18000ae63  movsx   r8d, bx
0x18000ae67  lea     edx, [rbx+1]
0x18000ae6a  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x18000ae6f  jmp     loc_18000B5D6
0x18000ae74  xorps   xmm0, xmm0
0x18000ae77  movdqu  xmmword ptr [rsp+1B0h+pv], xmm0
0x18000ae7d  mov     [rsp+1B0h+var_160], r12d
0x18000ae82  xorps   xmm1, xmm1
0x18000ae85  movdqu  xmmword ptr [rsp+1B0h+var_158], xmm1
0x18000ae8b  movups  xmmword ptr [rbp+0B0h+cb], xmm0
0x18000ae8f  lea     rcx, [rbp+0B0h+cb]; struct tagOCTET_STRING *
0x18000ae93  call    ?GetProcessSID@@YAJPEAUtagOCTET_STRING@@@Z; GetProcessSID(tagOCTET_STRING *)
0x18000ae98  mov     esi, eax
0x18000ae9a  test    eax, eax
0x18000ae9c  jns     short loc_18000AEBC
0x18000ae9e  mov     edx, eax
0x18000aea0  lea     rcx, aCl2tpdiaghelpe_0; "CL2TPDiagHelper::GetLowerHypotheses - F"...
0x18000aea7  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000aeac  nop
0x18000aead  lea     rcx, [rsp+1B0h+pv]; this
0x18000aeb2  call    ??1_hypothesis_builder@@QEAA@XZ; _hypothesis_builder::~_hypothesis_builder(void)
0x18000aeb7  jmp     loc_18000B5D6
0x18000aebc  movaps  xmm0, xmmword ptr cs:aSystemrootSyst; "%systemroot%\\system32\\svchost.exe"
0x18000aec3  movaps  xmmword ptr [rbp+0B0h+var_90], xmm0
0x18000aec7  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+10h; "oot%\\system32\\svchost.exe"
0x18000aece  movaps  [rbp+0B0h+var_80], xmm1
0x18000aed2  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+20h; "tem32\\svchost.exe"
0x18000aed9  movaps  [rbp+0B0h+var_70], xmm0
0x18000aedd  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+30h; "chost.exe"
0x18000aee4  movaps  [rbp+0B0h+var_60], xmm1
0x18000aee8  mov     eax, dword ptr cs:aSystemrootSyst+40h; "e"
0x18000aeee  mov     [rbp+0B0h+var_50], eax
0x18000aef1  lea     rcx, [rsp+1B0h+pv]; this
0x18000aef6  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x18000aefb  mov     rcx, [rsp+1B0h+pv]; pv
0x18000af00  call    cs:__imp_CoTaskMemFree
0x18000af07  nop     dword ptr [rax+rax+00h]
0x18000af0c  mov     [rsp+1B0h+pv], r12
0x18000af11  lea     r8, aTransportconne; "TransportConnection"
0x18000af18  mov     edx, 0FFFFh; unsigned __int64
0x18000af1d  lea     rcx, [rsp+1B0h+pv]; unsigned __int16 **
0x18000af22  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000af27  test    eax, eax
0x18000af29  js      short loc_18000AF3A
0x18000af2b  mov     edx, 5; unsigned int
0x18000af30  lea     rcx, [rsp+1B0h+pv]; this
0x18000af35  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x18000af3a  xor     ecx, ecx; pv
0x18000af3c  call    cs:__imp_CoTaskMemFree
0x18000af43  nop     dword ptr [rax+rax+00h]
0x18000af48  mov     r8, r12
0x18000af4b  mov     [rsp+1B0h+var_148.pwszName], r12
0x18000af50  mov     r12d, 0FFFEh
0x18000af56  mov     edx, r12d
0x18000af59  lea     r15, aRemoteaddr; "remoteaddr"
0x18000af60  mov     rax, r15
0x18000af63  xor     r10d, r10d
0x18000af66  cmp     [rax], r10w
0x18000af6a  jz      short loc_18000AF75
0x18000af6c  add     rax, 2
0x18000af70  sub     rdx, rbx
0x18000af73  jnz     short loc_18000AF66
0x18000af75  mov     rax, rdx
0x18000af78  mov     rcx, r12
0x18000af7b  sub     rcx, rdx
0x18000af7e  neg     rax
0x18000af81  sbb     rdi, rdi
0x18000af84  and     rdi, rcx
0x18000af87  test    rdx, rdx
0x18000af8a  jz      short loc_18000AFFF
0x18000af8c  lea     rcx, ds:2[rdi*2]; cb
0x18000af94  call    cs:__imp_CoTaskMemAlloc
0x18000af9b  nop     dword ptr [rax+rax+00h]
0x18000afa0  mov     r8, rax
0x18000afa3  mov     [rsp+1B0h+var_148.pwszName], rax
0x18000afa8  xor     r10d, r10d
0x18000afab  test    rax, rax
0x18000afae  jz      short loc_18000AFFF
0x18000afb0  lea     rdx, [rdi+1]
0x18000afb4  test    rdx, rdx
0x18000afb7  jz      short loc_18000AFFF
0x18000afb9  cmp     rdx, 7FFFFFFFh
0x18000afc0  jbe     short loc_18000AFC8
0x18000afc2  mov     [rax], r10w
0x18000afc6  jmp     short loc_18000AFFF
0x18000afc8  mov     ecx, 7FFFFFFEh
0x18000afcd  test    rcx, rcx
0x18000afd0  jz      short loc_18000AFF0
0x18000afd2  movzx   r9d, word ptr [r15]
0x18000afd6  test    r9w, r9w
0x18000afda  jz      short loc_18000AFF0
0x18000afdc  add     r15, 2
0x18000afe0  mov     [rax], r9w
0x18000afe4  add     rax, 2
0x18000afe8  sub     rcx, rbx
0x18000afeb  sub     rdx, rbx
0x18000afee  jnz     short loc_18000AFCD
0x18000aff0  lea     rcx, [rax-2]
0x18000aff4  test    rdx, rdx
0x18000aff7  cmovnz  rcx, rax
0x18000affb  mov     [rcx], r10w
0x18000afff  mov     [rsp+1B0h+var_148.type], 0Dh
0x18000b007  movups  xmm0, xmmword ptr [r14]
0x18000b00b  movups  xmmword ptr [rsp+1B0h+var_148.10h], xmm0
0x18000b010  movups  xmm1, xmmword ptr [r14+10h]
0x18000b015  movups  xmmword ptr [rbp+0B0h+var_148.10h+10h], xmm1
0x18000b019  movups  xmm0, xmmword ptr [r14+20h]
0x18000b01e  movups  xmmword ptr [rbp+0B0h+var_148.10h+20h], xmm0
0x18000b022  movups  xmm1, xmmword ptr [r14+30h]
0x18000b027  movups  xmmword ptr [rbp+0B0h+var_148.10h+30h], xmm1
0x18000b02b  movups  xmm0, xmmword ptr [r14+40h]
0x18000b030  movups  xmmword ptr [rbp+0B0h+var_148.10h+40h], xmm0
0x18000b034  movups  xmm1, xmmword ptr [r14+50h]
0x18000b039  movups  xmmword ptr [rbp+0B0h+var_148.10h+50h], xmm1
0x18000b03d  movups  xmm0, xmmword ptr [r14+60h]
0x18000b042  movups  xmmword ptr [rbp+0B0h+var_148.10h+60h], xmm0
0x18000b046  movups  xmm1, xmmword ptr [r14+70h]
0x18000b04b  movups  xmmword ptr [rbp+0B0h+var_148.10h+70h], xmm1
0x18000b04f  mov     r15, [rsp+1B0h+var_158]
0x18000b054  test    r8, r8
0x18000b057  jz      short loc_18000B066
0x18000b059  lea     rdx, [rsp+1B0h+var_148]; struct tagHELPER_ATTRIBUTE *
0x18000b05e  mov     rcx, r15; this
0x18000b061  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000b066  lea     rcx, [rsp+1B0h+var_148]; this
0x18000b06b  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000b070  xor     ecx, ecx; pv
0x18000b072  call    cs:__imp_CoTaskMemFree
0x18000b079  nop     dword ptr [rax+rax+00h]
0x18000b07e  xor     r10d, r10d
0x18000b081  mov     r8d, r10d
0x18000b084  mov     [rsp+1B0h+var_148.pwszName], r10
0x18000b089  mov     rdx, r12
0x18000b08c  lea     r14, aLocaladdr; "localaddr"
0x18000b093  mov     rax, r14
0x18000b096  cmp     [rax], r10w
0x18000b09a  jz      short loc_18000B0A5
0x18000b09c  add     rax, 2
0x18000b0a0  sub     rdx, rbx
0x18000b0a3  jnz     short loc_18000B096
0x18000b0a5  mov     rax, rdx
0x18000b0a8  mov     rcx, r12
0x18000b0ab  sub     rcx, rdx
0x18000b0ae  neg     rax
0x18000b0b1  sbb     rdi, rdi
0x18000b0b4  and     rdi, rcx
0x18000b0b7  test    rdx, rdx
0x18000b0ba  jz      short loc_18000B12F
0x18000b0bc  lea     rcx, ds:2[rdi*2]; cb
0x18000b0c4  call    cs:__imp_CoTaskMemAlloc
0x18000b0cb  nop     dword ptr [rax+rax+00h]
0x18000b0d0  mov     r8, rax
0x18000b0d3  mov     [rsp+1B0h+var_148.pwszName], rax
0x18000b0d8  xor     r10d, r10d
0x18000b0db  test    rax, rax
0x18000b0de  jz      short loc_18000B12F
0x18000b0e0  lea     rdx, [rdi+1]
0x18000b0e4  test    rdx, rdx
0x18000b0e7  jz      short loc_18000B12F
0x18000b0e9  cmp     rdx, 7FFFFFFFh
0x18000b0f0  jbe     short loc_18000B0F8
0x18000b0f2  mov     [rax], r10w
0x18000b0f6  jmp     short loc_18000B12F
0x18000b0f8  mov     ecx, 7FFFFFFEh
0x18000b0fd  test    rcx, rcx
0x18000b100  jz      short loc_18000B120
0x18000b102  movzx   r9d, word ptr [r14]
0x18000b106  test    r9w, r9w
0x18000b10a  jz      short loc_18000B120
0x18000b10c  add     r14, 2
0x18000b110  mov     [rax], r9w
0x18000b114  add     rax, 2
0x18000b118  sub     rcx, rbx
0x18000b11b  sub     rdx, rbx
0x18000b11e  jnz     short loc_18000B0FD
0x18000b120  lea     rcx, [rax-2]
0x18000b124  test    rdx, rdx
0x18000b127  cmovnz  rcx, rax
0x18000b12b  mov     [rcx], r10w
0x18000b12f  mov     [rsp+1B0h+var_148.type], 0Dh
0x18000b137  movups  xmm0, xmmword ptr [r13+0]
0x18000b13c  movups  xmmword ptr [rsp+1B0h+var_148.10h], xmm0
0x18000b141  movups  xmm1, xmmword ptr [r13+10h]
0x18000b146  movups  xmmword ptr [rbp+0B0h+var_148.10h+10h], xmm1
0x18000b14a  movups  xmm0, xmmword ptr [r13+20h]
0x18000b14f  movups  xmmword ptr [rbp+0B0h+var_148.10h+20h], xmm0
0x18000b153  movups  xmm1, xmmword ptr [r13+30h]
0x18000b158  movups  xmmword ptr [rbp+0B0h+var_148.10h+30h], xmm1
0x18000b15c  movups  xmm0, xmmword ptr [r13+40h]
0x18000b161  movups  xmmword ptr [rbp+0B0h+var_148.10h+40h], xmm0
0x18000b165  movups  xmm1, xmmword ptr [r13+50h]
0x18000b16a  movups  xmmword ptr [rbp+0B0h+var_148.10h+50h], xmm1
0x18000b16e  movups  xmm0, xmmword ptr [r13+60h]
0x18000b173  movups  xmmword ptr [rbp+0B0h+var_148.10h+60h], xmm0
0x18000b177  movups  xmm1, xmmword ptr [r13+70h]
0x18000b17c  movups  xmmword ptr [rbp+0B0h+var_148.10h+70h], xmm1
0x18000b180  cmp     [rsp+1B0h+var_160], ebx
0x18000b184  jb      short loc_18000B19C
0x18000b186  test    r8, r8
0x18000b189  jz      short loc_18000B19C
0x18000b18b  lea     rcx, [r15+90h]; this
0x18000b192  lea     rdx, [rsp+1B0h+var_148]; struct tagHELPER_ATTRIBUTE *
0x18000b197  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000b19c  lea     rcx, [rsp+1B0h+var_148]; this
0x18000b1a1  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000b1a6  xor     ecx, ecx; pv
0x18000b1a8  call    cs:__imp_CoTaskMemFree
0x18000b1af  nop     dword ptr [rax+rax+00h]
0x18000b1b4  xor     r10d, r10d
0x18000b1b7  mov     r8d, r10d
0x18000b1ba  mov     [rsp+1B0h+var_148.pwszName], r10
0x18000b1bf  mov     rdx, r12
0x18000b1c2  lea     r14, aProtocol; "protocol"
0x18000b1c9  mov     rax, r14
0x18000b1cc  cmp     [rax], r10w
0x18000b1d0  jz      short loc_18000B1DB
0x18000b1d2  add     rax, 2
0x18000b1d6  sub     rdx, rbx
0x18000b1d9  jnz     short loc_18000B1CC
0x18000b1db  mov     rax, rdx
0x18000b1de  mov     rcx, r12
0x18000b1e1  sub     rcx, rdx
0x18000b1e4  neg     rax
0x18000b1e7  sbb     rdi, rdi
0x18000b1ea  and     rdi, rcx
0x18000b1ed  test    rdx, rdx
0x18000b1f0  jz      short loc_18000B26B
0x18000b1f2  lea     rcx, ds:2[rdi*2]; cb
0x18000b1fa  call    cs:__imp_CoTaskMemAlloc
0x18000b201  nop     dword ptr [rax+rax+00h]
0x18000b206  mov     r8, rax
0x18000b209  mov     [rsp+1B0h+var_148.pwszName], rax
0x18000b20e  xor     r10d, r10d
0x18000b211  test    rax, rax
0x18000b214  jz      short loc_18000B26B
0x18000b216  lea     rdx, [rdi+1]
  ... truncated ...
```

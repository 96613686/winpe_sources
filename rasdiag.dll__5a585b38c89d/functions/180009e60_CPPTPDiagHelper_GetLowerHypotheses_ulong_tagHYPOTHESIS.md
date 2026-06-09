# CPPTPDiagHelper::GetLowerHypotheses(ulong *,tagHYPOTHESIS * *)

- ea: `0x180009e60`
- end: `0x18000a706`
- name: `?GetLowerHypotheses@CPPTPDiagHelper@@UEAAJPEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `2214`
- prototype: `__int64 __fastcall(CPPTPDiagHelper *__hidden this, unsigned int *, struct tagHYPOTHESIS **)`
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
- `0x180009e60`
- `0x18000b864`
- `0x18000bd1c`
- `0x18000beb8`
- `0x18000c310`
- `0x18000ca8c`
- `0x18000dab4`
- `0x18000dc5c`
- `0x18000df10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a09a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a1ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a402`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a493`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a550`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a637`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a09a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a1ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a402`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a493`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a550`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a637`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a03d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a2ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a46d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a69e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a03d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a2ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a46d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a69e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6b4`

## string_xrefs

- `0x180009fa1`: `CPPTPDiagHelper::GetLowerHypotheses - Failed to get process SID: 0x%x.`
- `0x180009fbd`: `%systemroot%\system32\svchost.exe`
- `0x18000a2c8`: `protocol`

## pseudocode

```c
__int64 __fastcall CPPTPDiagHelper::GetLowerHypotheses(
        CPPTPDiagHelper *this,
        unsigned int *a2,
        struct tagHYPOTHESIS **a3)
{
  char *v4; // r14
  char *v5; // r15
  char *v6; // rdi
  int RasEntryProperties; // eax
  signed int inited; // esi
  union tagHELPER_ATTRIBUTE::$E73CE4DD3AF9771F1CA4F78E7E603792 *v9; // r14
  union tagHELPER_ATTRIBUTE::$E73CE4DD3AF9771F1CA4F78E7E603792 *v10; // r13
  int ProcessSID; // eax
  WCHAR *v12; // r8
  __int64 v13; // rdx
  const wchar_t *v14; // r15
  const wchar_t *v15; // rax
  __int64 v16; // rbx
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
  __int64 v27; // rbx
  WCHAR *v28; // rax
  unsigned __int64 v29; // rdx
  __int64 v30; // rcx
  wchar_t v31; // r9
  WCHAR *v32; // rcx
  WCHAR *v33; // r8
  __int64 v34; // rdx
  const wchar_t *v35; // r14
  const wchar_t *v36; // rax
  __int64 v37; // rbx
  WCHAR *v38; // rax
  unsigned __int64 v39; // rdx
  __int64 v40; // r13
  __int64 v41; // rcx
  wchar_t v42; // r9
  WCHAR *v43; // rcx
  WCHAR *v44; // rbx
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
  __int64 v61; // rbx
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
  void *v72; // rbx
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
                 1723,
                 (struct sockaddr_storage *)((char *)this + 1168),
                 (struct sockaddr_storage *)((char *)this + 1296),
                 0);
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
          v81.Boolean = 6;
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
          RasDiagTrace("CPPTPDiagHelper::GetLowerHypotheses - Failed to get process SID: 0x%x.", ProcessSID);
        }
        _hypothesis_builder::~_hypothesis_builder(pv);
      }
      else
      {
        CRasLogger::Log((char *)this + 112, 2, 1, L"CPPTPDiagHelper", L"Socket address initialization failed.");
      }
    }
    else
    {
      CRasLogger::Log(
        (char *)this + 112,
        2,
        1,
        L"CPPTPDiagHelper",
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
0x180009e60  mov     [rsp-8+arg_18], rbx
0x180009e65  push    rbp
0x180009e66  push    rsi
0x180009e67  push    rdi
0x180009e68  push    r12
0x180009e6a  push    r13
0x180009e6c  push    r14
0x180009e6e  push    r15
0x180009e70  lea     rbp, [rsp-80h]
0x180009e75  sub     rsp, 180h
0x180009e7c  mov     rax, cs:__security_cookie
0x180009e83  xor     rax, rsp
0x180009e86  mov     [rbp+0B0h+var_40], rax
0x180009e8a  mov     rax, r8
0x180009e8d  mov     [rbp+0B0h+var_B0], rax
0x180009e91  mov     [rbp+0B0h+var_A8], rdx
0x180009e95  mov     rbx, rcx
0x180009e98  xor     r12d, r12d
0x180009e9b  test    rdx, rdx
0x180009e9e  jz      loc_18000A6D7
0x180009ea4  test    rax, rax
0x180009ea7  jz      loc_18000A6D7
0x180009ead  mov     [rdx], r12d
0x180009eb0  mov     [r8], r12
0x180009eb3  lea     r14, [rcx+78h]
0x180009eb7  lea     r15, [rcx+27Ah]
0x180009ebe  lea     rdi, [rcx+590h]
0x180009ec5  mov     [rbp+0B0h+var_B8], rdi
0x180009ec9  mov     r8, rdi; struct tagRASENTRYW **
0x180009ecc  mov     rdx, r14; LPCWSTR
0x180009ecf  mov     rcx, r15; LPCWSTR
0x180009ed2  call    ?GetRasEntryProperties@@YAJPEBG0PEAPEAUtagRASENTRYW@@@Z; GetRasEntryProperties(ushort const *,ushort const *,tagRASENTRYW * *)
0x180009ed7  mov     esi, eax
0x180009ed9  test    eax, eax
0x180009edb  jns     short loc_180009F18
0x180009edd  lea     edi, [r12+1]
0x180009ee2  lea     rcx, [rbx+70h]
0x180009ee6  mov     [rsp+1B0h+var_178], eax
0x180009eea  mov     [rsp+1B0h+var_180], r14
0x180009eef  mov     [rsp+1B0h+var_188], r15
0x180009ef4  lea     rax, aRasgetentrypro_0; "RasGetEntryProperties(%s,%s) failed wit"...
0x180009efb  mov     qword ptr [rsp+1B0h+var_190], rax
0x180009f00  lea     r9, aCpptpdiaghelpe; "CPPTPDiagHelper"
0x180009f07  movsx   r8d, di
0x180009f0b  lea     edx, [rdi+1]
0x180009f0e  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x180009f13  jmp     loc_18000A6DC
0x180009f18  lea     r14, [rbx+510h]
0x180009f1f  lea     r13, [rbx+490h]
0x180009f26  mov     edx, 6BBh; __int16
0x180009f2b  mov     rcx, [rdi]
0x180009f2e  add     rcx, 26h ; '&'; pNodeName
0x180009f32  mov     [rsp+1B0h+var_190], r12d; int
0x180009f37  mov     r9, r14; struct sockaddr_storage *
0x180009f3a  mov     r8, r13; struct sockaddr_storage *
0x180009f3d  call    ?InitSockAddresses@@YAJPEBGFPEAUsockaddr_storage@@1H@Z; InitSockAddresses(ushort const *,short,sockaddr_storage *,sockaddr_storage *,int)
0x180009f42  mov     esi, eax
0x180009f44  test    eax, eax
0x180009f46  jns     short loc_180009F75
0x180009f48  mov     edi, 1
0x180009f4d  lea     rcx, [rbx+70h]
0x180009f51  lea     rax, aSocketAddressI; "Socket address initialization failed."
0x180009f58  mov     qword ptr [rsp+1B0h+var_190], rax
0x180009f5d  lea     r9, aCpptpdiaghelpe; "CPPTPDiagHelper"
0x180009f64  movsx   r8d, di
0x180009f68  lea     edx, [rdi+1]
0x180009f6b  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x180009f70  jmp     loc_18000A6DC
0x180009f75  xorps   xmm0, xmm0
0x180009f78  movdqu  xmmword ptr [rsp+1B0h+pv], xmm0
0x180009f7e  mov     [rsp+1B0h+var_160], r12d
0x180009f83  xorps   xmm1, xmm1
0x180009f86  movdqu  xmmword ptr [rsp+1B0h+var_158], xmm1
0x180009f8c  movups  xmmword ptr [rbp+0B0h+cb], xmm0
0x180009f90  lea     rcx, [rbp+0B0h+cb]; struct tagOCTET_STRING *
0x180009f94  call    ?GetProcessSID@@YAJPEAUtagOCTET_STRING@@@Z; GetProcessSID(tagOCTET_STRING *)
0x180009f99  mov     esi, eax
0x180009f9b  test    eax, eax
0x180009f9d  jns     short loc_180009FBD
0x180009f9f  mov     edx, eax
0x180009fa1  lea     rcx, Format; "CPPTPDiagHelper::GetLowerHypotheses - F"...
0x180009fa8  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x180009fad  nop
0x180009fae  lea     rcx, [rsp+1B0h+pv]; this
0x180009fb3  call    ??1_hypothesis_builder@@QEAA@XZ; _hypothesis_builder::~_hypothesis_builder(void)
0x180009fb8  jmp     loc_18000A6DC
0x180009fbd  movaps  xmm0, xmmword ptr cs:aSystemrootSyst; "%systemroot%\\system32\\svchost.exe"
0x180009fc4  movaps  xmmword ptr [rbp+0B0h+var_90], xmm0
0x180009fc8  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+10h; "oot%\\system32\\svchost.exe"
0x180009fcf  movaps  [rbp+0B0h+var_80], xmm1
0x180009fd3  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+20h; "tem32\\svchost.exe"
0x180009fda  movaps  [rbp+0B0h+var_70], xmm0
0x180009fde  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+30h; "chost.exe"
0x180009fe5  movaps  [rbp+0B0h+var_60], xmm1
0x180009fe9  mov     eax, dword ptr cs:aSystemrootSyst+40h; "e"
0x180009fef  mov     [rbp+0B0h+var_50], eax
0x180009ff2  lea     rcx, [rsp+1B0h+pv]; this
0x180009ff7  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x180009ffc  mov     rcx, [rsp+1B0h+pv]; pv
0x18000a001  call    cs:__imp_CoTaskMemFree
0x18000a008  nop     dword ptr [rax+rax+00h]
0x18000a00d  mov     [rsp+1B0h+pv], r12
0x18000a012  lea     r8, aTransportconne; "TransportConnection"
0x18000a019  mov     edx, 0FFFFh; unsigned __int64
0x18000a01e  lea     rcx, [rsp+1B0h+pv]; unsigned __int16 **
0x18000a023  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000a028  test    eax, eax
0x18000a02a  js      short loc_18000A03B
0x18000a02c  mov     edx, 5; unsigned int
0x18000a031  lea     rcx, [rsp+1B0h+pv]; this
0x18000a036  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x18000a03b  xor     ecx, ecx; pv
0x18000a03d  call    cs:__imp_CoTaskMemFree
0x18000a044  nop     dword ptr [rax+rax+00h]
0x18000a049  mov     r8, r12
0x18000a04c  mov     [rsp+1B0h+var_148.pwszName], r12
0x18000a051  mov     r12d, 0FFFEh
0x18000a057  mov     edx, r12d
0x18000a05a  lea     r15, aRemoteaddr; "remoteaddr"
0x18000a061  mov     rax, r15
0x18000a064  mov     edi, 1
0x18000a069  xor     r10d, r10d
0x18000a06c  cmp     [rax], r10w
0x18000a070  jz      short loc_18000A07B
0x18000a072  add     rax, 2
0x18000a076  sub     rdx, rdi
0x18000a079  jnz     short loc_18000A06C
0x18000a07b  mov     rax, rdx
0x18000a07e  mov     rcx, r12
0x18000a081  sub     rcx, rdx
0x18000a084  neg     rax
0x18000a087  sbb     rbx, rbx
0x18000a08a  and     rbx, rcx
0x18000a08d  test    rdx, rdx
0x18000a090  jz      short loc_18000A105
0x18000a092  lea     rcx, ds:2[rbx*2]; cb
0x18000a09a  call    cs:__imp_CoTaskMemAlloc
0x18000a0a1  nop     dword ptr [rax+rax+00h]
0x18000a0a6  mov     r8, rax
0x18000a0a9  mov     [rsp+1B0h+var_148.pwszName], rax
0x18000a0ae  xor     r10d, r10d
0x18000a0b1  test    rax, rax
0x18000a0b4  jz      short loc_18000A105
0x18000a0b6  lea     rdx, [rbx+1]
0x18000a0ba  test    rdx, rdx
0x18000a0bd  jz      short loc_18000A105
0x18000a0bf  cmp     rdx, 7FFFFFFFh
0x18000a0c6  jbe     short loc_18000A0CE
0x18000a0c8  mov     [rax], r10w
0x18000a0cc  jmp     short loc_18000A105
0x18000a0ce  mov     ecx, 7FFFFFFEh
0x18000a0d3  test    rcx, rcx
0x18000a0d6  jz      short loc_18000A0F6
0x18000a0d8  movzx   r9d, word ptr [r15]
0x18000a0dc  test    r9w, r9w
0x18000a0e0  jz      short loc_18000A0F6
0x18000a0e2  add     r15, 2
0x18000a0e6  mov     [rax], r9w
0x18000a0ea  add     rax, 2
0x18000a0ee  sub     rcx, rdi
0x18000a0f1  sub     rdx, rdi
0x18000a0f4  jnz     short loc_18000A0D3
0x18000a0f6  lea     rcx, [rax-2]
0x18000a0fa  test    rdx, rdx
0x18000a0fd  cmovnz  rcx, rax
0x18000a101  mov     [rcx], r10w
0x18000a105  mov     [rsp+1B0h+var_148.type], 0Dh
0x18000a10d  movups  xmm0, xmmword ptr [r14]
0x18000a111  movups  xmmword ptr [rsp+1B0h+var_148.10h], xmm0
0x18000a116  movups  xmm1, xmmword ptr [r14+10h]
0x18000a11b  movups  xmmword ptr [rbp+0B0h+var_148.10h+10h], xmm1
0x18000a11f  movups  xmm0, xmmword ptr [r14+20h]
0x18000a124  movups  xmmword ptr [rbp+0B0h+var_148.10h+20h], xmm0
0x18000a128  movups  xmm1, xmmword ptr [r14+30h]
0x18000a12d  movups  xmmword ptr [rbp+0B0h+var_148.10h+30h], xmm1
0x18000a131  movups  xmm0, xmmword ptr [r14+40h]
0x18000a136  movups  xmmword ptr [rbp+0B0h+var_148.10h+40h], xmm0
0x18000a13a  movups  xmm1, xmmword ptr [r14+50h]
0x18000a13f  movups  xmmword ptr [rbp+0B0h+var_148.10h+50h], xmm1
0x18000a143  movups  xmm0, xmmword ptr [r14+60h]
0x18000a148  movups  xmmword ptr [rbp+0B0h+var_148.10h+60h], xmm0
0x18000a14c  movups  xmm1, xmmword ptr [r14+70h]
0x18000a151  movups  xmmword ptr [rbp+0B0h+var_148.10h+70h], xmm1
0x18000a155  mov     r15, [rsp+1B0h+var_158]
0x18000a15a  test    r8, r8
0x18000a15d  jz      short loc_18000A16C
0x18000a15f  lea     rdx, [rsp+1B0h+var_148]; struct tagHELPER_ATTRIBUTE *
0x18000a164  mov     rcx, r15; this
0x18000a167  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000a16c  lea     rcx, [rsp+1B0h+var_148]; this
0x18000a171  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000a176  xor     ecx, ecx; pv
0x18000a178  call    cs:__imp_CoTaskMemFree
0x18000a17f  nop     dword ptr [rax+rax+00h]
0x18000a184  xor     r10d, r10d
0x18000a187  mov     r8d, r10d
0x18000a18a  mov     [rsp+1B0h+var_148.pwszName], r10
0x18000a18f  mov     rdx, r12
0x18000a192  lea     r14, aLocaladdr; "localaddr"
0x18000a199  mov     rax, r14
0x18000a19c  cmp     [rax], r10w
0x18000a1a0  jz      short loc_18000A1AB
0x18000a1a2  add     rax, 2
0x18000a1a6  sub     rdx, rdi
0x18000a1a9  jnz     short loc_18000A19C
0x18000a1ab  mov     rax, rdx
0x18000a1ae  mov     rcx, r12
0x18000a1b1  sub     rcx, rdx
0x18000a1b4  neg     rax
0x18000a1b7  sbb     rbx, rbx
0x18000a1ba  and     rbx, rcx
0x18000a1bd  test    rdx, rdx
0x18000a1c0  jz      short loc_18000A235
0x18000a1c2  lea     rcx, ds:2[rbx*2]; cb
0x18000a1ca  call    cs:__imp_CoTaskMemAlloc
0x18000a1d1  nop     dword ptr [rax+rax+00h]
0x18000a1d6  mov     r8, rax
0x18000a1d9  mov     [rsp+1B0h+var_148.pwszName], rax
0x18000a1de  xor     r10d, r10d
0x18000a1e1  test    rax, rax
0x18000a1e4  jz      short loc_18000A235
0x18000a1e6  lea     rdx, [rbx+1]
0x18000a1ea  test    rdx, rdx
0x18000a1ed  jz      short loc_18000A235
0x18000a1ef  cmp     rdx, 7FFFFFFFh
0x18000a1f6  jbe     short loc_18000A1FE
0x18000a1f8  mov     [rax], r10w
0x18000a1fc  jmp     short loc_18000A235
0x18000a1fe  mov     ecx, 7FFFFFFEh
0x18000a203  test    rcx, rcx
0x18000a206  jz      short loc_18000A226
0x18000a208  movzx   r9d, word ptr [r14]
0x18000a20c  test    r9w, r9w
0x18000a210  jz      short loc_18000A226
0x18000a212  add     r14, 2
0x18000a216  mov     [rax], r9w
0x18000a21a  add     rax, 2
0x18000a21e  sub     rcx, rdi
0x18000a221  sub     rdx, rdi
0x18000a224  jnz     short loc_18000A203
0x18000a226  lea     rcx, [rax-2]
0x18000a22a  test    rdx, rdx
0x18000a22d  cmovnz  rcx, rax
0x18000a231  mov     [rcx], r10w
0x18000a235  mov     [rsp+1B0h+var_148.type], 0Dh
0x18000a23d  movups  xmm0, xmmword ptr [r13+0]
0x18000a242  movups  xmmword ptr [rsp+1B0h+var_148.10h], xmm0
0x18000a247  movups  xmm1, xmmword ptr [r13+10h]
0x18000a24c  movups  xmmword ptr [rbp+0B0h+var_148.10h+10h], xmm1
0x18000a250  movups  xmm0, xmmword ptr [r13+20h]
0x18000a255  movups  xmmword ptr [rbp+0B0h+var_148.10h+20h], xmm0
0x18000a259  movups  xmm1, xmmword ptr [r13+30h]
0x18000a25e  movups  xmmword ptr [rbp+0B0h+var_148.10h+30h], xmm1
0x18000a262  movups  xmm0, xmmword ptr [r13+40h]
0x18000a267  movups  xmmword ptr [rbp+0B0h+var_148.10h+40h], xmm0
0x18000a26b  movups  xmm1, xmmword ptr [r13+50h]
0x18000a270  movups  xmmword ptr [rbp+0B0h+var_148.10h+50h], xmm1
0x18000a274  movups  xmm0, xmmword ptr [r13+60h]
0x18000a279  movups  xmmword ptr [rbp+0B0h+var_148.10h+60h], xmm0
0x18000a27d  movups  xmm1, xmmword ptr [r13+70h]
0x18000a282  movups  xmmword ptr [rbp+0B0h+var_148.10h+70h], xmm1
0x18000a286  cmp     [rsp+1B0h+var_160], edi
0x18000a28a  jb      short loc_18000A2A2
0x18000a28c  test    r8, r8
0x18000a28f  jz      short loc_18000A2A2
0x18000a291  lea     rcx, [r15+90h]; this
0x18000a298  lea     rdx, [rsp+1B0h+var_148]; struct tagHELPER_ATTRIBUTE *
0x18000a29d  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000a2a2  lea     rcx, [rsp+1B0h+var_148]; this
0x18000a2a7  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000a2ac  xor     ecx, ecx; pv
0x18000a2ae  call    cs:__imp_CoTaskMemFree
0x18000a2b5  nop     dword ptr [rax+rax+00h]
0x18000a2ba  xor     r10d, r10d
0x18000a2bd  mov     r8d, r10d
0x18000a2c0  mov     [rsp+1B0h+var_148.pwszName], r10
0x18000a2c5  mov     rdx, r12
0x18000a2c8  lea     r14, aProtocol; "protocol"
0x18000a2cf  mov     rax, r14
0x18000a2d2  cmp     [rax], r10w
0x18000a2d6  jz      short loc_18000A2E1
0x18000a2d8  add     rax, 2
0x18000a2dc  sub     rdx, rdi
0x18000a2df  jnz     short loc_18000A2D2
0x18000a2e1  mov     rax, rdx
0x18000a2e4  mov     rcx, r12
0x18000a2e7  sub     rcx, rdx
0x18000a2ea  neg     rax
0x18000a2ed  sbb     rbx, rbx
0x18000a2f0  and     rbx, rcx
0x18000a2f3  test    rdx, rdx
0x18000a2f6  jz      short loc_18000A371
0x18000a2f8  lea     rcx, ds:2[rbx*2]; cb
0x18000a300  call    cs:__imp_CoTaskMemAlloc
0x18000a307  nop     dword ptr [rax+rax+00h]
0x18000a30c  mov     r8, rax
0x18000a30f  mov     [rsp+1B0h+var_148.pwszName], rax
0x18000a314  xor     r10d, r10d
0x18000a317  test    rax, rax
0x18000a31a  jz      short loc_18000A371
  ... truncated ...
```

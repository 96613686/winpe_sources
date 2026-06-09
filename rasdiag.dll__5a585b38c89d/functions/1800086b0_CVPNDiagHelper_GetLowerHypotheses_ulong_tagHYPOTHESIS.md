# CVPNDiagHelper::GetLowerHypotheses(ulong *,tagHYPOTHESIS * *)

- ea: `0x1800086b0`
- end: `0x18000923b`
- name: `?GetLowerHypotheses@CVPNDiagHelper@@UEAAJPEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `2955`
- prototype: `__int64 __fastcall(CVPNDiagHelper *__hidden this, unsigned int *, struct tagHYPOTHESIS **)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002028`
- `0x18000258c`
- `0x180006274`
- `0x18000678c`
- `0x180006800`
- `0x180007dc0`
- `0x180008084`
- `0x1800086b0`
- `0x18000dab4`
- `0x18000db44`
- `0x18000dc5c`
- `0x18000df10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008829`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000896d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008a71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008d79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008e7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009083`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008829`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000896d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008a71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008d79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008e7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009083`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800088e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008921`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008cf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009171`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800088e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008921`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008cf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009171`

## pseudocode

```c
__int64 __fastcall CVPNDiagHelper::GetLowerHypotheses(
        CVPNDiagHelper *this,
        unsigned int *a2,
        struct tagHYPOTHESIS **a3)
{
  unsigned int v5; // eax
  int v6; // r15d
  BOOL v7; // r12d
  __int64 v8; // r14
  __int64 v9; // rdx
  const wchar_t *v10; // rsi
  const wchar_t *v11; // rax
  __int64 v12; // rbx
  WCHAR *v13; // rax
  unsigned __int64 v14; // rdx
  __int64 v15; // r8
  wchar_t v16; // cx
  WCHAR *v17; // rcx
  unsigned int *v18; // r9
  __int64 v19; // rdx
  const wchar_t *v20; // rbx
  const wchar_t *v21; // rax
  __int64 v22; // rsi
  WCHAR *v23; // rax
  unsigned __int64 v24; // rdx
  __int64 v25; // r12
  __int64 v26; // rcx
  wchar_t v27; // r8
  WCHAR *v28; // rcx
  __int64 v29; // r15
  __int64 v30; // rdx
  const wchar_t *v31; // rsi
  const wchar_t *v32; // rax
  __int64 v33; // rbx
  WCHAR *v34; // rax
  unsigned __int64 v35; // rdx
  __int64 v36; // rcx
  wchar_t v37; // r8
  WCHAR *v38; // rcx
  int v39; // r14d
  WCHAR *v40; // r8
  __int64 v41; // rdx
  const wchar_t *v42; // rsi
  const wchar_t *v43; // rax
  __int64 v44; // rbx
  WCHAR *v45; // rax
  unsigned __int64 v46; // rdx
  __int64 v47; // rcx
  wchar_t v48; // r9
  WCHAR *v49; // rcx
  int v50; // r14d
  WCHAR *v51; // r8
  __int64 v52; // rcx
  const wchar_t *v53; // rbx
  const wchar_t *v54; // rax
  __int64 v55; // rsi
  WCHAR *v56; // rax
  unsigned __int64 v57; // rdx
  wchar_t v58; // cx
  __int64 v59; // rdx
  const wchar_t *v60; // rbx
  const wchar_t *v61; // rax
  __int64 v62; // rsi
  WCHAR *v63; // rax
  unsigned __int64 v64; // rdx
  __int64 v65; // r12
  __int64 v66; // rcx
  wchar_t v67; // r8
  WCHAR *v68; // rcx
  __int64 v69; // r15
  __int64 v70; // rdx
  const wchar_t *v71; // rsi
  const wchar_t *v72; // rax
  __int64 v73; // rbx
  WCHAR *v74; // rax
  unsigned __int64 v75; // rdx
  __int64 v76; // rcx
  wchar_t v77; // r8
  WCHAR *v78; // rcx
  int v79; // r14d
  WCHAR *v80; // r8
  __int64 v81; // rdx
  const wchar_t *v82; // rsi
  const wchar_t *v83; // rax
  __int64 v84; // rbx
  WCHAR *v85; // rax
  unsigned __int64 v86; // rdx
  __int64 v87; // rcx
  wchar_t v88; // r9
  WCHAR *v89; // rcx
  __int64 v90; // rcx
  const wchar_t *v91; // rbx
  const wchar_t *v92; // rax
  __int64 v93; // rsi
  wchar_t v94; // cx
  WCHAR *v95; // rcx
  __int64 v96; // rdi
  struct tagHYPOTHESIS *v97; // rax
  struct tagHYPOTHESIS *v98; // rbx
  unsigned int v99; // r14d
  struct tagHYPOTHESIS *v100; // rdi
  unsigned int v101; // esi
  unsigned int v102; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v103[2]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v104; // [rsp+40h] [rbp-C0h]
  struct tagHELPER_ATTRIBUTE v105; // [rsp+48h] [rbp-B8h] BYREF
  struct tagHYPOTHESIS **v106; // [rsp+D8h] [rbp-28h]
  unsigned int *v107; // [rsp+E0h] [rbp-20h]
  LPVOID pv[5]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v109[2]; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v110; // [rsp+128h] [rbp+28h]
  _attribute_t *v111; // [rsp+130h] [rbp+30h]

  v106 = a3;
  v107 = a2;
  *(_QWORD *)v103 = this;
  if ( *(_OWORD *)((char *)this + 1436) == RCG_RAS_MINIPORT_MISSING )
    return 0;
  if ( a2 && a3 )
  {
    v104 = 0;
    *a2 = 0;
    *a3 = 0;
    `eh vector constructor iterator'(
      pv,
      0x28u,
      6u,
      (void (*)(void *))_hypothesis_builder::_hypothesis_builder,
      (void (*)(void *))_hypothesis_builder::~_hypothesis_builder);
    v5 = *(_DWORD *)(*((_QWORD *)this + 178) + 4044LL);
    if ( v5 <= 2 || (v6 = 0, v5 == 12) )
      v6 = 1;
    v7 = v5 - 3 <= 1;
    _hypothesis_builder::FreeAll(pv);
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
    if ( (int)StringCchCopyWithAlloc((unsigned __int16 **)pv, 0xFFFFu, L"DnsHelperClass") >= 0 )
      _hypothesis_builder::SetCount((_hypothesis_builder *)pv, 1u);
    v8 = *((_QWORD *)this + 178);
    CoTaskMemFree(0);
    v105.pwszName = 0;
    v9 = 65534;
    v10 = L"QueryName";
    v11 = L"QueryName";
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v9;
    }
    while ( v9 );
    v12 = (65534 - v9) & -(__int64)(v9 != 0);
    if ( v9 )
    {
      v13 = (WCHAR *)CoTaskMemAlloc(2 * v12 + 2);
      v105.pwszName = v13;
      if ( v13 )
      {
        v14 = v12 + 1;
        if ( v12 != -1 )
        {
          if ( v14 <= 0x7FFFFFFF )
          {
            v15 = 2147483646;
            do
            {
              if ( !v15 )
                break;
              v16 = *v10;
              if ( !*v10 )
                break;
              ++v10;
              *v13++ = v16;
              --v15;
              --v14;
            }
            while ( v14 );
            v17 = v13 - 1;
            if ( v14 )
              v17 = v13;
            *v17 = 0;
          }
          else
          {
            *v13 = 0;
          }
        }
      }
    }
    v105.type = AT_STRING;
    v105.Int64 = 0;
    _attribute_t::SetValue((_attribute_t *)&v105, (const unsigned __int16 *)(v8 + 38));
    if ( v105.type && v105.pwszName )
      _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)pv[3], &v105);
    _attribute_t::FreeAll((LPVOID *)&v105.pwszName);
    if ( v6 )
    {
      _hypothesis_builder::FreeAll((LPVOID *)v109);
      CoTaskMemFree(v109[0]);
      v109[0] = 0;
      if ( (int)StringCchCopyWithAlloc(v109, 0xFFFFu, L"CPPTPDiagHelper") >= 0 )
        _hypothesis_builder::SetCount((_hypothesis_builder *)v109, 4u);
      CoTaskMemFree(0);
      v105.pwszName = 0;
      v19 = 65534;
      v20 = L"entryname";
      v21 = L"entryname";
      do
      {
        if ( !*v21 )
          break;
        ++v21;
        --v19;
      }
      while ( v19 );
      v22 = (65534 - v19) & -(__int64)(v19 != 0);
      if ( v19 && (v23 = (WCHAR *)CoTaskMemAlloc(2 * v22 + 2), (v105.pwszName = v23) != 0) && (v24 = v22 + 1, v22 != -1) )
      {
        v25 = 2147483646;
        if ( v24 <= 0x7FFFFFFF )
        {
          v26 = 2147483646;
          do
          {
            if ( !v26 )
              break;
            v27 = *v20;
            if ( !*v20 )
              break;
            ++v20;
            *v23++ = v27;
            --v26;
            --v24;
          }
          while ( v24 );
          v28 = v23 - 1;
          if ( v24 )
            v28 = v23;
          *v28 = 0;
        }
        else
        {
          *v23 = 0;
        }
      }
      else
      {
        v25 = 2147483646;
      }
      v105.type = AT_STRING;
      v105.Int64 = 0;
      v29 = *(_QWORD *)v103;
      _attribute_t::SetValue((_attribute_t *)&v105, (const unsigned __int16 *)(*(_QWORD *)v103 + 112LL));
      if ( v105.type && v105.pwszName )
        _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)v111, &v105);
      _attribute_t::FreeAll((LPVOID *)&v105.pwszName);
      CoTaskMemFree(0);
      v105.pwszName = 0;
      v30 = 65534;
      v31 = L"phonebook";
      v32 = L"phonebook";
      do
      {
        if ( !*v32 )
          break;
        ++v32;
        --v30;
      }
      while ( v30 );
      v33 = (65534 - v30) & -(__int64)(v30 != 0);
      if ( v30 )
      {
        v34 = (WCHAR *)CoTaskMemAlloc(2 * v33 + 2);
        v105.pwszName = v34;
        if ( v34 )
        {
          v35 = v33 + 1;
          if ( v33 != -1 )
          {
            if ( v35 <= 0x7FFFFFFF )
            {
              v36 = 2147483646;
              do
              {
                if ( !v36 )
                  break;
                v37 = *v31;
                if ( !*v31 )
                  break;
                ++v31;
                *v34++ = v37;
                --v36;
                --v35;
              }
              while ( v35 );
              v38 = v34 - 1;
              if ( v35 )
                v38 = v34;
              *v38 = 0;
            }
            else
            {
              *v34 = 0;
            }
          }
        }
      }
      v105.type = AT_STRING;
      v105.Int64 = 0;
      _attribute_t::SetValue((_attribute_t *)&v105, (const unsigned __int16 *)(v29 + 626));
      if ( v110 && v105.type && v105.pwszName )
        _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)v111 + 1, &v105);
      _attribute_t::FreeAll((LPVOID *)&v105.pwszName);
      v39 = *(_DWORD *)(v29 + 1148);
      CoTaskMemFree(0);
      v40 = 0;
      v105.pwszName = 0;
      v41 = 65534;
      v42 = L"ErrorCode";
      v43 = L"ErrorCode";
      do
      {
        if ( !*v43 )
          break;
        ++v43;
        --v41;
      }
      while ( v41 );
      v44 = (65534 - v41) & -(__int64)(v41 != 0);
      if ( v41 )
      {
        v45 = (WCHAR *)CoTaskMemAlloc(2 * v44 + 2);
        v40 = v45;
        v105.pwszName = v45;
        if ( v45 )
        {
          v46 = v44 + 1;
          if ( v44 != -1 )
          {
            if ( v46 <= 0x7FFFFFFF )
            {
              v47 = 2147483646;
              do
              {
                if ( !v47 )
                  break;
                v48 = *v42;
                if ( !*v42 )
                  break;
                ++v42;
                *v45++ = v48;
                --v47;
                --v46;
              }
              while ( v46 );
              v49 = v45 - 1;
              if ( v46 )
                v49 = v45;
              *v49 = 0;
            }
            else
            {
              *v45 = 0;
            }
          }
        }
      }
      v105.type = AT_UINT32;
      v105.Boolean = v39;
      if ( v110 >= 2 && v40 )
        _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)v111 + 2, &v105);
      _attribute_t::FreeAll((LPVOID *)&v105.pwszName);
      v50 = *(unsigned __int8 *)(v29 + 1152);
      CoTaskMemFree(0);
      v51 = 0;
      v105.pwszName = 0;
      v52 = 65534;
      v53 = L"IsCMConnection";
      v54 = L"IsCMConnection";
      do
      {
        if ( !*v54 )
          break;
        ++v54;
        --v52;
      }
      while ( v52 );
      v55 = (65534 - v52) & -(__int64)(v52 != 0);
      if ( !v52 )
        goto LABEL_171;
      v56 = (WCHAR *)CoTaskMemAlloc(2 * v55 + 2);
      v51 = v56;
      v105.pwszName = v56;
      if ( !v56 )
        goto LABEL_171;
      v57 = v55 + 1;
      if ( v55 == -1 )
        goto LABEL_171;
      if ( v57 <= 0x7FFFFFFF )
      {
        do
        {
          if ( !v25 )
            break;
          v58 = *v53;
          if ( !*v53 )
            break;
          ++v53;
          *v56++ = v58;
          --v25;
          --v57;
        }
        while ( v57 );
LABEL_168:
        v95 = v56 - 1;
        if ( v57 )
          v95 = v56;
        *v95 = 0;
        goto LABEL_171;
      }
    }
    else
    {
      if ( !v7 )
      {
        _hypothesis_builder::Detach((_hypothesis_builder *)pv, v107, v106, v18);
LABEL_183:
        `eh vector destructor iterator'(pv, 0x28u, 6u, (void (*)(void *))_hypothesis_builder::~_hypothesis_builder);
        return v104;
      }
      _hypothesis_builder::FreeAll((LPVOID *)v109);
      CoTaskMemFree(v109[0]);
      v109[0] = 0;
      if ( (int)StringCchCopyWithAlloc(v109, 0xFFFFu, L"CL2TPDiagHelper") >= 0 )
        _hypothesis_builder::SetCount((_hypothesis_builder *)v109, 4u);
      CoTaskMemFree(0);
      v105.pwszName = 0;
      v59 = 65534;
      v60 = L"entryname";
      v61 = L"entryname";
      do
      {
        if ( !*v61 )
          break;
        ++v61;
        --v59;
      }
      while ( v59 );
      v62 = (65534 - v59) & -(__int64)(v59 != 0);
      if ( v59 && (v63 = (WCHAR *)CoTaskMemAlloc(2 * v62 + 2), (v105.pwszName = v63) != 0) && (v64 = v62 + 1, v62 != -1) )
      {
        v65 = 2147483646;
        if ( v64 <= 0x7FFFFFFF )
        {
          v66 = 2147483646;
          do
          {
            if ( !v66 )
              break;
            v67 = *v60;
            if ( !*v60 )
              break;
            ++v60;
            *v63++ = v67;
            --v66;
            --v64;
          }
          while ( v64 );
          v68 = v63 - 1;
          if ( v64 )
            v68 = v63;
          *v68 = 0;
        }
        else
        {
          *v63 = 0;
        }
      }
      else
      {
        v65 = 2147483646;
      }
      v105.type = AT_STRING;
      v105.Int64 = 0;
      v69 = *(_QWORD *)v103;
      _attribute_t::SetValue((_attribute_t *)&v105, (const unsigned __int16 *)(*(_QWORD *)v103 + 112LL));
      if ( v105.type && v105.pwszName )
        _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)v111, &v105);
      _attribute_t::FreeAll((LPVOID *)&v105.pwszName);
      CoTaskMemFree(0);
      v105.pwszName = 0;
      v70 = 65534;
      v71 = L"phonebook";
      v72 = L"phonebook";
      do
      {
        if ( !*v72 )
          break;
        ++v72;
        --v70;
      }
      while ( v70 );
      v73 = (65534 - v70) & -(__int64)(v70 != 0);
      if ( v70 )
      {
        v74 = (WCHAR *)CoTaskMemAlloc(2 * v73 + 2);
        v105.pwszName = v74;
        if ( v74 )
        {
          v75 = v73 + 1;
          if ( v73 != -1 )
          {
            if ( v75 <= 0x7FFFFFFF )
            {
              v76 = 2147483646;
              do
              {
                if ( !v76 )
                  break;
                v77 = *v71;
                if ( !*v71 )
                  break;
                ++v71;
                *v74++ = v77;
                --v76;
                --v75;
              }
              while ( v75 );
              v78 = v74 - 1;
              if ( v75 )
                v78 = v74;
              *v78 = 0;
            }
            else
            {
              *v74 = 0;
            }
          }
        }
      }
      v105.type = AT_STRING;
      v105.Int64 = 0;
      _attribute_t::SetValue((_attribute_t *)&v105, (const unsigned __int16 *)(v69 + 626));
      if ( v110 && v105.type && v105.pwszName )
        _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)v111 + 1, &v105);
      _attribute_t::FreeAll((LPVOID *)&v105.pwszName);
      v79 = *(_DWORD *)(v69 + 1148);
      CoTaskMemFree(0);
      v80 = 0;
      v105.pwszName = 0;
      v81 = 65534;
      v82 = L"ErrorCode";
      v83 = L"ErrorCode";
      do
      {
        if ( !*v83 )
          break;
        ++v83;
        --v81;
      }
      while ( v81 );
      v84 = (65534 - v81) & -(__int64)(v81 != 0);
      if ( v81 )
      {
        v85 = (WCHAR *)CoTaskMemAlloc(2 * v84 + 2);
        v80 = v85;
        v105.pwszName = v85;
        if ( v85 )
        {
          v86 = v84 + 1;
          if ( v84 != -1 )
          {
            if ( v86 <= 0x7FFFFFFF )
            {
              v87 = 2147483646;
              do
              {
                if ( !v87 )
                  break;
                v88 = *v82;
                if ( !*v82 )
                  break;
                ++v82;
                *v85++ = v88;
                --v87;
                --v86;
              }
              while ( v86 );
              v89 = v85 - 1;
              if ( v86 )
                v89 = v85;
              *v89 = 0;
            }
            else
            {
              *v85 = 0;
            }
          }
        }
      }
      v105.type = AT_UINT32;
      v105.Boolean = v79;
      if ( v110 >= 2 && v80 )
        _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)v111 + 2, &v105);
      _attribute_t::FreeAll((LPVOID *)&v105.pwszName);
      v50 = *(unsigned __int8 *)(v69 + 1152);
      CoTaskMemFree(0);
      v51 = 0;
      v105.pwszName = 0;
      v90 = 65534;
      v91 = L"IsCMConnection";
      v92 = L"IsCMConnection";
      do
      {
        if ( !*v92 )
          break;
        ++v92;
        --v90;
      }
      while ( v90 );
      v93 = (65534 - v90) & -(__int64)(v90 != 0);
      if ( !v90
        || (v56 = (WCHAR *)CoTaskMemAlloc(2 * v93 + 2), v51 = v56, (v105.pwszName = v56) == 0)
        || (v57 = v93 + 1, v93 == -1) )
      {
LABEL_171:
        v105.Boolean = v50;
        v105.type = AT_BOOLEAN;
        if ( v110 >= 3 && v51 )
          _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)v111 + 3, &v105);
        _attribute_t::FreeAll((LPVOID *)&v105.pwszName);
        v96 = 64;
        v97 = (struct tagHYPOTHESIS *)CoTaskMemAlloc(0x40u);
        v98 = v97;
        if ( v97 )
        {
          do
          {
            LOBYTE(v97->pwszClassName) = 0;
            v97 = (struct tagHYPOTHESIS *)((char *)v97 + 1);
            --v96;
          }
          while ( v96 );
          v103[0] = 0;
          v102 = 0;
          if ( (int)_hypothesis_builder::DetachInPlace((WCHAR **)pv, v98, &v102, v103) >= 0 )
          {
            v99 = v102;
            v100 = (struct tagHYPOTHESIS *)((char *)v98 + v103[0]);
            v101 = 0;
            do
            {
              if ( (int)_hypothesis_builder::DetachInPlace(&v109[5 * v101], v100, &v102, v103) < 0 )
                break;
              v99 += v102;
              v100 = (struct tagHYPOTHESIS *)((char *)v100 + v103[0]);
              ++v101;
            }
            while ( !v101 );
            *v106 = v98;
            *v107 = v99;
          }
          else
          {
            CoTaskMemFree(v98);
          }
        }
        goto LABEL_183;
      }
      if ( v57 <= 0x7FFFFFFF )
      {
        do
        {
          if ( !v65 )
            break;
          v94 = *v91;
          if ( !*v91 )
            break;
          ++v91;
          *v56++ = v94;
          --v65;
          --v57;
        }
        while ( v57 );
        goto LABEL_168;
      }
    }
    *v56 = 0;
    goto LABEL_171;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800086b0  mov     [rsp-8+arg_18], rbx
0x1800086b5  push    rbp
0x1800086b6  push    rsi
0x1800086b7  push    rdi
0x1800086b8  push    r12
0x1800086ba  push    r13
0x1800086bc  push    r14
0x1800086be  push    r15
0x1800086c0  lea     rbp, [rsp-0F0h]
0x1800086c8  sub     rsp, 1F0h
0x1800086cf  mov     rax, cs:__security_cookie
0x1800086d6  xor     rax, rsp
0x1800086d9  mov     [rbp+120h+var_40], rax
0x1800086e0  mov     [rbp+120h+var_148], r8
0x1800086e4  mov     [rbp+120h+var_140], rdx
0x1800086e8  mov     rbx, rcx
0x1800086eb  mov     qword ptr [rsp+220h+var_1E8], rcx
0x1800086f0  mov     rax, [rcx+59Ch]
0x1800086f7  cmp     rax, qword ptr cs:RCG_RAS_MINIPORT_MISSING
0x1800086fe  jnz     short loc_180008717
0x180008700  mov     rax, [rcx+5A4h]
0x180008707  cmp     rax, qword ptr cs:RCG_RAS_MINIPORT_MISSING+8
0x18000870e  jnz     short loc_180008717
0x180008710  xor     eax, eax
0x180008712  jmp     loc_180009210
0x180008717  xor     esi, esi
0x180008719  test    rdx, rdx
0x18000871c  jz      loc_18000920B
0x180008722  test    r8, r8
0x180008725  jz      loc_18000920B
0x18000872b  mov     [rsp+220h+var_1E0], esi
0x18000872f  mov     [rdx], esi
0x180008731  mov     [r8], rsi
0x180008734  lea     rax, ??1_hypothesis_builder@@QEAA@XZ; _hypothesis_builder::~_hypothesis_builder(void)
0x18000873b  mov     [rsp+220h+var_200], rax; void (*)(void *)
0x180008740  lea     r9, ??0_hypothesis_builder@@QEAA@XZ; void (*)(void *)
0x180008747  lea     edx, [rsi+28h]; unsigned __int64
0x18000874a  lea     r8d, [rsi+6]; unsigned __int64
0x18000874e  lea     rcx, [rbp+120h+pv]; void *
0x180008752  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180008757  nop
0x180008758  mov     rax, [rbx+590h]
0x18000875f  mov     eax, [rax+0FCCh]
0x180008765  lea     edi, [rsi+2]
0x180008768  cmp     eax, edi
0x18000876a  jbe     short loc_180008774
0x18000876c  cmp     eax, 0Ch
0x18000876f  mov     r15d, esi
0x180008772  jnz     short loc_18000877A
0x180008774  mov     r15d, 1
0x18000877a  add     eax, 0FFFFFFFDh
0x18000877d  mov     r12d, esi
0x180008780  cmp     eax, 1
0x180008783  setbe   r12b
0x180008787  lea     rcx, [rbp+120h+pv]; this
0x18000878b  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x180008790  mov     rcx, [rbp+120h+pv]; pv
0x180008794  call    cs:__imp_CoTaskMemFree
0x18000879b  nop     dword ptr [rax+rax+00h]
0x1800087a0  mov     [rbp+120h+pv], rsi
0x1800087a4  lea     r8, aDnshelperclass; "DnsHelperClass"
0x1800087ab  mov     edx, 0FFFFh; unsigned __int64
0x1800087b0  lea     rcx, [rbp+120h+pv]; unsigned __int16 **
0x1800087b4  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x1800087b9  test    eax, eax
0x1800087bb  js      short loc_1800087CB
0x1800087bd  mov     edx, 1; unsigned int
0x1800087c2  lea     rcx, [rbp+120h+pv]; this
0x1800087c6  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x1800087cb  mov     r14, [rbx+590h]
0x1800087d2  xor     ecx, ecx; pv
0x1800087d4  call    cs:__imp_CoTaskMemFree
0x1800087db  nop     dword ptr [rax+rax+00h]
0x1800087e0  mov     [rsp+220h+var_1D8.pwszName], rsi
0x1800087e5  mov     r13d, 0FFFEh
0x1800087eb  mov     edx, r13d
0x1800087ee  lea     rsi, aQueryname; "QueryName"
0x1800087f5  mov     rax, rsi
0x1800087f8  xor     r9d, r9d
0x1800087fb  cmp     [rax], r9w
0x1800087ff  jz      short loc_18000880A
0x180008801  add     rax, rdi
0x180008804  sub     rdx, 1
0x180008808  jnz     short loc_1800087FB
0x18000880a  mov     rax, rdx
0x18000880d  mov     rcx, r13
0x180008810  sub     rcx, rdx
0x180008813  neg     rax
0x180008816  sbb     rbx, rbx
0x180008819  and     rbx, rcx
0x18000881c  test    rdx, rdx
0x18000881f  jz      short loc_18000888E
0x180008821  lea     rcx, ds:2[rbx*2]; cb
0x180008829  call    cs:__imp_CoTaskMemAlloc
0x180008830  nop     dword ptr [rax+rax+00h]
0x180008835  mov     [rsp+220h+var_1D8.pwszName], rax
0x18000883a  xor     r9d, r9d
0x18000883d  test    rax, rax
0x180008840  jz      short loc_18000888E
0x180008842  lea     rdx, [rbx+1]
0x180008846  test    rdx, rdx
0x180008849  jz      short loc_18000888E
0x18000884b  cmp     rdx, 7FFFFFFFh
0x180008852  jbe     short loc_18000885A
0x180008854  mov     [rax], r9w
0x180008858  jmp     short loc_18000888E
0x18000885a  mov     r8d, 7FFFFFFEh
0x180008860  test    r8, r8
0x180008863  jz      short loc_18000887F
0x180008865  movzx   ecx, word ptr [rsi]
0x180008868  test    cx, cx
0x18000886b  jz      short loc_18000887F
0x18000886d  add     rsi, rdi
0x180008870  mov     [rax], cx
0x180008873  add     rax, rdi
0x180008876  dec     r8
0x180008879  sub     rdx, 1
0x18000887d  jnz     short loc_180008860
0x18000887f  lea     rcx, [rax-2]
0x180008883  test    rdx, rdx
0x180008886  cmovnz  rcx, rax
0x18000888a  mov     [rcx], r9w
0x18000888e  mov     [rsp+220h+var_1D8.type], 0Ah
0x180008896  mov     qword ptr [rsp+220h+var_1D8.10h], r9
0x18000889b  lea     rdx, [r14+26h]; unsigned __int16 *
0x18000889f  lea     rcx, [rsp+220h+var_1D8]; this
0x1800088a4  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x1800088a9  xor     r14d, r14d
0x1800088ac  cmp     [rsp+220h+var_1D8.type], r14d
0x1800088b1  jz      short loc_1800088C8
0x1800088b3  cmp     [rsp+220h+var_1D8.pwszName], r14
0x1800088b8  jz      short loc_1800088C8
0x1800088ba  lea     rdx, [rsp+220h+var_1D8]; struct tagHELPER_ATTRIBUTE *
0x1800088bf  mov     rcx, [rbp+120h+var_118]; this
0x1800088c3  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x1800088c8  lea     rcx, [rsp+220h+var_1D8]; this
0x1800088cd  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x1800088d2  test    r15d, r15d
0x1800088d5  jz      loc_180008CDE
0x1800088db  lea     rcx, [rbp+120h+var_108]; this
0x1800088df  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x1800088e4  mov     rcx, [rbp+120h+var_108]; pv
0x1800088e8  call    cs:__imp_CoTaskMemFree
0x1800088ef  nop     dword ptr [rax+rax+00h]
0x1800088f4  mov     [rbp+120h+var_108], r14
0x1800088f8  lea     r8, aCpptpdiaghelpe; "CPPTPDiagHelper"
0x1800088ff  mov     edx, 0FFFFh; unsigned __int64
0x180008904  lea     rcx, [rbp+120h+var_108]; unsigned __int16 **
0x180008908  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000890d  test    eax, eax
0x18000890f  js      short loc_18000891F
0x180008911  mov     edx, 4; unsigned int
0x180008916  lea     rcx, [rbp+120h+var_108]; this
0x18000891a  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x18000891f  xor     ecx, ecx; pv
0x180008921  call    cs:__imp_CoTaskMemFree
0x180008928  nop     dword ptr [rax+rax+00h]
0x18000892d  mov     [rsp+220h+var_1D8.pwszName], r14
0x180008932  mov     rdx, r13
0x180008935  lea     rbx, aEntryname; "entryname"
0x18000893c  mov     rax, rbx
0x18000893f  cmp     [rax], r14w
0x180008943  jz      short loc_18000894E
0x180008945  add     rax, rdi
0x180008948  sub     rdx, 1
0x18000894c  jnz     short loc_18000893F
0x18000894e  mov     rax, rdx
0x180008951  mov     rcx, r13
0x180008954  sub     rcx, rdx
0x180008957  neg     rax
0x18000895a  sbb     rsi, rsi
0x18000895d  and     rsi, rcx
0x180008960  test    rdx, rdx
0x180008963  jz      short loc_1800089D7
0x180008965  lea     rcx, ds:2[rsi*2]; cb
0x18000896d  call    cs:__imp_CoTaskMemAlloc
0x180008974  nop     dword ptr [rax+rax+00h]
0x180008979  mov     [rsp+220h+var_1D8.pwszName], rax
0x18000897e  test    rax, rax
0x180008981  jz      short loc_1800089D7
0x180008983  lea     rdx, [rsi+1]
0x180008987  test    rdx, rdx
0x18000898a  jz      short loc_1800089D7
0x18000898c  mov     r12d, 7FFFFFFEh
0x180008992  cmp     rdx, 7FFFFFFFh
0x180008999  jbe     short loc_1800089A1
0x18000899b  mov     [rax], r14w
0x18000899f  jmp     short loc_1800089DD
0x1800089a1  mov     rcx, r12
0x1800089a4  test    rcx, rcx
0x1800089a7  jz      short loc_1800089C6
0x1800089a9  movzx   r8d, word ptr [rbx]
0x1800089ad  test    r8w, r8w
0x1800089b1  jz      short loc_1800089C6
0x1800089b3  add     rbx, rdi
0x1800089b6  mov     [rax], r8w
0x1800089ba  add     rax, rdi
0x1800089bd  dec     rcx
0x1800089c0  sub     rdx, 1
0x1800089c4  jnz     short loc_1800089A4
0x1800089c6  lea     rcx, [rax-2]
0x1800089ca  test    rdx, rdx
0x1800089cd  cmovnz  rcx, rax
0x1800089d1  mov     [rcx], r14w
0x1800089d5  jmp     short loc_1800089DD
0x1800089d7  mov     r12d, 7FFFFFFEh
0x1800089dd  mov     [rsp+220h+var_1D8.type], 0Ah
0x1800089e5  mov     qword ptr [rsp+220h+var_1D8.10h], r14
0x1800089ea  mov     r15, qword ptr [rsp+220h+var_1E8]
0x1800089ef  lea     rdx, [r15+70h]; unsigned __int16 *
0x1800089f3  lea     rcx, [rsp+220h+var_1D8]; this
0x1800089f8  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x1800089fd  cmp     [rsp+220h+var_1D8.type], r14d
0x180008a02  jz      short loc_180008A19
0x180008a04  cmp     [rsp+220h+var_1D8.pwszName], r14
0x180008a09  jz      short loc_180008A19
0x180008a0b  lea     rdx, [rsp+220h+var_1D8]; struct tagHELPER_ATTRIBUTE *
0x180008a10  mov     rcx, [rbp+120h+var_F0]; this
0x180008a14  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180008a19  lea     rcx, [rsp+220h+var_1D8]; this
0x180008a1e  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180008a23  xor     ecx, ecx; pv
0x180008a25  call    cs:__imp_CoTaskMemFree
0x180008a2c  nop     dword ptr [rax+rax+00h]
0x180008a31  mov     [rsp+220h+var_1D8.pwszName], r14
0x180008a36  mov     rdx, r13
0x180008a39  lea     rsi, aPhonebook; "phonebook"
0x180008a40  mov     rax, rsi
0x180008a43  cmp     [rax], r14w
0x180008a47  jz      short loc_180008A52
0x180008a49  add     rax, rdi
0x180008a4c  sub     rdx, 1
0x180008a50  jnz     short loc_180008A43
0x180008a52  mov     rax, rdx
0x180008a55  mov     rcx, r13
0x180008a58  sub     rcx, rdx
0x180008a5b  neg     rax
0x180008a5e  sbb     rbx, rbx
0x180008a61  and     rbx, rcx
0x180008a64  test    rdx, rdx
0x180008a67  jz      short loc_180008AD3
0x180008a69  lea     rcx, ds:2[rbx*2]; cb
0x180008a71  call    cs:__imp_CoTaskMemAlloc
0x180008a78  nop     dword ptr [rax+rax+00h]
0x180008a7d  mov     [rsp+220h+var_1D8.pwszName], rax
0x180008a82  test    rax, rax
0x180008a85  jz      short loc_180008AD3
0x180008a87  lea     rdx, [rbx+1]
0x180008a8b  test    rdx, rdx
0x180008a8e  jz      short loc_180008AD3
0x180008a90  cmp     rdx, 7FFFFFFFh
0x180008a97  jbe     short loc_180008A9F
0x180008a99  mov     [rax], r14w
0x180008a9d  jmp     short loc_180008AD3
0x180008a9f  mov     rcx, r12
0x180008aa2  test    rcx, rcx
0x180008aa5  jz      short loc_180008AC4
0x180008aa7  movzx   r8d, word ptr [rsi]
0x180008aab  test    r8w, r8w
0x180008aaf  jz      short loc_180008AC4
0x180008ab1  add     rsi, rdi
0x180008ab4  mov     [rax], r8w
0x180008ab8  add     rax, rdi
0x180008abb  dec     rcx
0x180008abe  sub     rdx, 1
0x180008ac2  jnz     short loc_180008AA2
0x180008ac4  lea     rcx, [rax-2]
0x180008ac8  test    rdx, rdx
0x180008acb  cmovnz  rcx, rax
0x180008acf  mov     [rcx], r14w
0x180008ad3  mov     [rsp+220h+var_1D8.type], 0Ah
0x180008adb  mov     qword ptr [rsp+220h+var_1D8.10h], r14
0x180008ae0  lea     rdx, [r15+272h]; unsigned __int16 *
0x180008ae7  lea     rcx, [rsp+220h+var_1D8]; this
0x180008aec  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x180008af1  cmp     [rbp+120h+var_F8], 1
0x180008af5  jb      short loc_180008B1A
0x180008af7  cmp     [rsp+220h+var_1D8.type], r14d
0x180008afc  jz      short loc_180008B1A
0x180008afe  cmp     [rsp+220h+var_1D8.pwszName], r14
0x180008b03  jz      short loc_180008B1A
0x180008b05  mov     rcx, [rbp+120h+var_F0]
0x180008b09  add     rcx, 90h; this
0x180008b10  lea     rdx, [rsp+220h+var_1D8]; struct tagHELPER_ATTRIBUTE *
0x180008b15  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180008b1a  lea     rcx, [rsp+220h+var_1D8]; this
0x180008b1f  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180008b24  mov     r14d, [r15+47Ch]
0x180008b2b  xor     ecx, ecx; pv
0x180008b2d  call    cs:__imp_CoTaskMemFree
0x180008b34  nop     dword ptr [rax+rax+00h]
0x180008b39  xor     r10d, r10d
0x180008b3c  mov     r8d, r10d
0x180008b3f  mov     [rsp+220h+var_1D8.pwszName], r10
0x180008b44  mov     rdx, r13
0x180008b47  lea     rsi, aErrorcode; "ErrorCode"
0x180008b4e  mov     rax, rsi
0x180008b51  cmp     [rax], r10w
0x180008b55  jz      short loc_180008B60
0x180008b57  add     rax, rdi
  ... truncated ...
```

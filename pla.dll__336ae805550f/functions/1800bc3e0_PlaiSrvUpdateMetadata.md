# PlaiSrvUpdateMetadata

- ea: `0x1800bc3e0`
- end: `0x1800bce84`
- name: `PlaiSrvUpdateMetadata`
- size: `2724`
- prototype: `__int64 __fastcall(void *, SAFEARRAY *psa)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x18003f304`
- `0x18004de9c`
- `0x1800bc3e0`
- `0x180113c60`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!rand` at `0x1800bc634`
- `msvcrt!rand` at `0x1800bc634`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bcdcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bcdcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bc43f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bc43f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bc655`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bc655`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bc63c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bc63c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800bca6c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800bca6c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800bcdea`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800bcdea`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x1800bc626`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x1800bc689`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x1800bc626`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x1800bc689`

## string_xrefs

- `0x1800bc599`: `PlaiSrvUpdateMetadata`
- `0x1800bcd84`: `PlaiSrvUpdateMetadata`

## pseudocode

```c
__int64 __fastcall PlaiSrvUpdateMetadata(void *a1, SAFEARRAY *psa, int a3)
{
  _WORD *v4; // r15
  _DWORD *v5; // r12
  WCHAR *v6; // r13
  SAFEARRAY *v8; // rdi
  int v9; // eax
  HRESULT v10; // ebx
  __int64 v11; // rdx
  SIZE_T *v12; // r9
  SIZE_T *p_dwBytes; // rcx
  int v14; // eax
  __int64 v15; // rdx
  int v16; // ebx
  DWORD CurrentThreadId; // eax
  HRESULT v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  unsigned __int64 cElements; // rax
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rdx
  unsigned __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rdx
  _WORD *v29; // rax
  __int64 v30; // rdx
  SAFEARRAY *v31; // r14
  SAFEARRAY *v32; // rcx
  __int64 v33; // rdx
  unsigned __int64 v34; // rdx
  unsigned int v35; // r10d
  __int64 v36; // r9
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rdi
  __int64 v43; // rdx
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rdx
  int pStgOptions; // [rsp+20h] [rbp-E0h]
  int pStgOptionsa; // [rsp+20h] [rbp-E0h]
  void **ppObjectOpen; // [rsp+38h] [rbp-C8h]
  __int64 v52; // [rsp+40h] [rbp-C0h]
  int v53; // [rsp+70h] [rbp-90h] BYREF
  SIZE_T dwBytes; // [rsp+78h] [rbp-88h] BYREF
  SAFEARRAY *psaa; // [rsp+80h] [rbp-80h]
  void *v56; // [rsp+88h] [rbp-78h] BYREF
  WCHAR *pwcsName; // [rsp+90h] [rbp-70h] BYREF
  void *ppvData; // [rsp+98h] [rbp-68h] BYREF
  __int64 v59; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v60[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v61[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v62[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v63[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v64[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v65[64]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v66[64]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v67[64]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int16 v68[64]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v69[64]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v70[64]; // [rsp+5B0h] [rbp+4B0h] BYREF
  unsigned __int16 v71[64]; // [rsp+630h] [rbp+530h] BYREF
  unsigned __int16 v72[64]; // [rsp+6B0h] [rbp+5B0h] BYREF

  psaa = psa;
  ppvData = 0;
  v59 = 0;
  v4 = 0;
  v56 = 0;
  v5 = 0;
  pwcsName = 0;
  v6 = 0;
  v8 = psa;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)&xmmword_180169D00 + 8));
  v9 = PlaiCheckContext(a1);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( !g_isTaskSchedulerUseXMLStoreEnabled )
      goto LABEL_32;
    v14 = PlaiCreateCollectorSetPath(*((const unsigned __int16 **)a1 + 12), *((_DWORD *)a1 + 22), &pwcsName);
    v10 = v14;
    if ( v14 < 0 )
    {
      v53 = v14;
      LODWORD(dwBytes) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        v6 = pwcsName;
        goto LABEL_102;
      }
      PlaiWhoAmI(v62, 0x4000000000000800uLL);
      v15 = -1;
      do
        ++v15;
      while ( v62[v15] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v53, 4, byte_180147320, 1, &dwBytes, 4);
      v6 = pwcsName;
      goto LABEL_101;
    }
    v6 = pwcsName;
    if ( StgOpenStorageEx(pwcsName, 0x12u, 3u, 0, 0, 0, &IID_IPropertySetStorage, &v56) < 0 )
    {
      v16 = rand();
      CurrentThreadId = GetCurrentThreadId();
      Sleep((CurrentThreadId ^ v16) % 0x64);
      v18 = StgOpenStorageEx(v6, 0x12u, 3u, 0, 0, 0, &IID_IPropertySetStorage, &v56);
      v10 = v18;
      if ( v18 < 0 )
      {
        v53 = v18;
        LODWORD(dwBytes) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_102;
        }
        PlaiWhoAmI(v63, 0x4000000000000800uLL);
        v19 = -1;
        do
          ++v19;
        while ( v63[v19] );
        goto LABEL_24;
      }
    }
    pStgOptions = 4114;
    v20 = (*(__int64 (__fastcall **)(void *, GUID *, _QWORD, _QWORD))(*(_QWORD *)v56 + 24LL))(
            v56,
            &FMTID_PlaDcsInfo,
            0,
            0);
    v10 = v20;
    if ( v20 < 0 )
    {
      v53 = v20;
      LODWORD(dwBytes) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_102;
      }
      PlaiWhoAmI(v64, 0x4000000000000800uLL);
      v21 = -1;
      do
        ++v21;
      while ( v64[v21] );
    }
    else
    {
LABEL_32:
      cElements = v8->rgsabound[0].cElements;
      if ( cElements + 1 < cElements )
      {
        v10 = -2147024362;
        LODWORD(dwBytes) = 0;
        v53 = -2147024362;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v72, 0x4000000000000800uLL);
          v47 = -1;
          do
            ++v47;
          while ( v72[v47] );
          v12 = (SIZE_T *)&v53;
          p_dwBytes = &dwBytes;
          goto LABEL_100;
        }
        goto LABEL_102;
      }
      dwBytes = cElements + 1;
      v23 = ULongLongMult(cElements + 1, 0x10u, &dwBytes);
      v10 = v23;
      if ( v23 >= 0 )
      {
        v5 = PlaiAlloc(dwBytes, 1, 0, byte_180147320, pStgOptions);
        if ( v5 )
        {
          v26 = psaa->rgsabound[0].cElements;
          if ( v26 + 1 < v26 )
          {
            v10 = -2147024362;
            LODWORD(dwBytes) = 0;
            v53 = -2147024362;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_101;
            }
            PlaiWhoAmI(v71, 0x4000000000000800uLL);
            v46 = -1;
            do
              ++v46;
            while ( v71[v46] );
          }
          else
          {
            dwBytes = v26 + 1;
            v27 = ULongLongMult(v26 + 1, 0x18u, &dwBytes);
            v10 = v27;
            if ( v27 >= 0 )
            {
              v29 = PlaiAlloc(dwBytes, 1, 0, byte_180147320, pStgOptionsa);
              v4 = v29;
              if ( v29 )
              {
                *v5 = 1;
                v5[2] = 2;
                *((_DWORD *)v29 + 2) = a3;
                v31 = psaa;
                v32 = psaa;
                *v29 = 19;
                v10 = SafeArrayAccessData(v32, &ppvData);
                if ( v10 >= 0 )
                {
                  v34 = v31->rgsabound[0].cElements;
                  v35 = 0;
                  if ( (_DWORD)v34 )
                  {
                    do
                    {
                      v36 = v35 + 1;
                      v37 = 2 * v36;
                      v38 = 3 * v36;
                      v5[2 * v37] = 1;
                      v5[2 * v37 + 2] = v35 + 3;
                      v4[4 * v38] = 8;
                      v39 = v35++;
                      *(_QWORD *)&v4[4 * v38 + 4] = *((_QWORD *)ppvData + v39);
                      v34 = v31->rgsabound[0].cElements;
                    }
                    while ( (unsigned int)v36 < (unsigned int)v34 );
                  }
                  if ( !g_isTaskSchedulerUseXMLStoreEnabled
                    || (v40 = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, _WORD *, _DWORD))(*(_QWORD *)v59 + 32LL))(
                                v59,
                                (unsigned int)(v34 + 1),
                                v5,
                                v4,
                                0),
                        v10 = v40,
                        v40 >= 0) )
                  {
                    v42 = *((_QWORD *)a1 + 2);
                    if ( (int)PlaiWhoAmI(v60, v34) < 0 )
                      v60[0] = 0;
                    v43 = -1;
                    v44 = -1;
                    do
                      ++v44;
                    while ( v60[v44] );
                    if ( v42 )
                    {
                      do
                        ++v43;
                      while ( *(_WORD *)(v42 + 2 * v43) );
                      v45 = (unsigned int)(2 * v43) + 2LL;
                    }
                    else
                    {
                      v45 = 0;
                    }
                    EventingWriteEvent(
                      &g_Eventing,
                      &PLA_EVENTLOG_DCS_EDIT,
                      2,
                      v42,
                      v45,
                      v60,
                      (unsigned int)(2 * v44) + 2LL,
                      ppObjectOpen,
                      v52);
                    goto LABEL_101;
                  }
                  LODWORD(dwBytes) = 0;
                  v53 = v40;
                  if ( !(_DWORD)xmmword_180169738
                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
LABEL_101:
                    v8 = psaa;
                    goto LABEL_102;
                  }
                  PlaiWhoAmI(v70, 0x4000000000000800uLL);
                  v41 = -1;
                  do
                    ++v41;
                  while ( v70[v41] );
                }
                else
                {
                  v53 = v10;
                  LODWORD(dwBytes) = 0;
                  if ( !(_DWORD)xmmword_180169738
                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
                    goto LABEL_101;
                  }
                  PlaiWhoAmI(v69, 0x4000000000000800uLL);
                  v33 = -1;
                  do
                    ++v33;
                  while ( v69[v33] );
                }
              }
              else
              {
                v10 = -2147024882;
                LODWORD(dwBytes) = 0;
                v53 = -2147024882;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_101;
                }
                PlaiWhoAmI(v68, 0x4000000000000800uLL);
                v30 = -1;
                do
                  ++v30;
                while ( v68[v30] );
              }
            }
            else
            {
              v53 = v27;
              LODWORD(dwBytes) = 0;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_101;
              }
              PlaiWhoAmI(v67, 0x4000000000000800uLL);
              v28 = -1;
              do
                ++v28;
              while ( v67[v28] );
            }
          }
        }
        else
        {
          v10 = -2147024882;
          LODWORD(dwBytes) = 0;
          v53 = -2147024882;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_101;
          }
          PlaiWhoAmI(v66, 0x4000000000000800uLL);
          v25 = -1;
          do
            ++v25;
          while ( v66[v25] );
        }
      }
      else
      {
        v53 = v23;
        LODWORD(dwBytes) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_102;
        }
        PlaiWhoAmI(v65, 0x4000000000000800uLL);
        v24 = -1;
        do
          ++v24;
        while ( v65[v24] );
      }
    }
LABEL_24:
    v12 = (SIZE_T *)&v53;
    p_dwBytes = &dwBytes;
LABEL_100:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v12, 4, byte_180147320, 1, p_dwBytes, 4);
    goto LABEL_101;
  }
  LODWORD(dwBytes) = v9;
  v53 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v61, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v61[v11] );
    v12 = &dwBytes;
    p_dwBytes = (SIZE_T *)&v53;
    goto LABEL_100;
  }
LABEL_102:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)&xmmword_180169D00 + 8));
  if ( v10 == -2147287007 )
    v10 = -2147024863;
  if ( ppvData )
  {
    SafeArrayUnaccessData(v8);
    ppvData = 0;
  }
  if ( v6 )
    PlaiFree(v6, 1);
  if ( v5 )
    PlaiFree(v5, 1);
  if ( v4 )
    PlaiFree(v4, 1);
  if ( v56 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
  if ( v59 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800bc3e0  mov     [rsp-8+arg_10], rbx
0x1800bc3e5  push    rbp
0x1800bc3e6  push    rsi
0x1800bc3e7  push    rdi
0x1800bc3e8  push    r12
0x1800bc3ea  push    r13
0x1800bc3ec  push    r14
0x1800bc3ee  push    r15
0x1800bc3f0  lea     rbp, [rsp-640h]
0x1800bc3f8  sub     rsp, 740h
0x1800bc3ff  mov     rax, cs:__security_cookie
0x1800bc406  xor     rax, rsp
0x1800bc409  mov     [rbp+670h+var_40], rax
0x1800bc410  xor     eax, eax
0x1800bc412  mov     [rbp+670h+psa], rdx
0x1800bc416  mov     rsi, rcx
0x1800bc419  mov     [rbp+670h+ppvData], rax
0x1800bc41d  lea     rcx, xmmword_180169D00+8; lpCriticalSection
0x1800bc424  mov     [rbp+670h+var_6D0], rax
0x1800bc428  mov     r15d, eax
0x1800bc42b  mov     [rbp+670h+var_6E8], rax
0x1800bc42f  mov     r12d, eax
0x1800bc432  mov     [rbp+670h+pwcsName], rax
0x1800bc436  mov     r13d, eax
0x1800bc439  mov     r14d, r8d
0x1800bc43c  mov     rdi, rdx
0x1800bc43f  call    cs:__imp_EnterCriticalSection
0x1800bc445  mov     rcx, rsi; void *
0x1800bc448  call    ?PlaiCheckContext@@YAJPEAX@Z; PlaiCheckContext(void *)
0x1800bc44d  xor     r9d, r9d
0x1800bc450  mov     ebx, eax
0x1800bc452  test    eax, eax
0x1800bc454  jns     loc_1800BC4DB
0x1800bc45a  xor     r14d, r14d
0x1800bc45d  mov     dword ptr [rsp+770h+dwBytes], eax
0x1800bc461  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800bc468  mov     [rsp+770h+var_700], r14d
0x1800bc46d  jz      loc_1800BCDC6
0x1800bc473  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bc47d  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bc484  jz      loc_1800BCDC6
0x1800bc48a  mov     rax, cs:qword_180169748
0x1800bc491  and     rax, rdx
0x1800bc494  cmp     cs:qword_180169748, rax
0x1800bc49b  jnz     loc_1800BCDC6
0x1800bc4a1  lea     rcx, [rbp+670h+var_640]; unsigned __int16 *
0x1800bc4a5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bc4aa  lea     rax, [rbp+670h+var_640]
0x1800bc4ae  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bc4b2  inc     rdx
0x1800bc4b5  cmp     [rax+rdx*2], r14w
0x1800bc4ba  jnz     short loc_1800BC4B2
0x1800bc4bc  lea     ecx, [rdx+rdx]
0x1800bc4bf  add     rcx, 2
0x1800bc4c3  lea     rax, [rbp+670h+var_640]
0x1800bc4c7  mov     [rsp+770h+var_710], rcx
0x1800bc4cc  lea     r9, [rsp+770h+dwBytes]
0x1800bc4d1  lea     rcx, [rsp+770h+var_700]
0x1800bc4d6  jmp     loc_1800BCD68
0x1800bc4db  cmp     cs:?g_isTaskSchedulerUseXMLStoreEnabled@@3_NA, r9b; bool g_isTaskSchedulerUseXMLStoreEnabled
0x1800bc4e2  jz      loc_1800BC7D2
0x1800bc4e8  mov     edx, [rsi+58h]; int
0x1800bc4eb  lea     r8, [rbp+670h+pwcsName]; unsigned __int16 **
0x1800bc4ef  mov     rcx, [rsi+60h]; unsigned __int16 *
0x1800bc4f3  call    ?PlaiCreateCollectorSetPath@@YAJPEBGHPEAPEAG@Z; PlaiCreateCollectorSetPath(ushort const *,int,ushort * *)
0x1800bc4f8  xor     ecx, ecx
0x1800bc4fa  mov     ebx, eax
0x1800bc4fc  test    eax, eax
0x1800bc4fe  jns     loc_1800BC5F5
0x1800bc504  xor     r14d, r14d
0x1800bc507  mov     [rsp+770h+var_700], eax
0x1800bc50b  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800bc512  mov     dword ptr [rsp+770h+dwBytes], r14d
0x1800bc517  jz      loc_1800BC5EC
0x1800bc51d  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bc527  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bc52e  jz      loc_1800BC5EC
0x1800bc534  mov     rax, cs:qword_180169748
0x1800bc53b  and     rax, rdx
0x1800bc53e  cmp     cs:qword_180169748, rax
0x1800bc545  jnz     loc_1800BC5EC
0x1800bc54b  lea     rcx, [rbp+670h+var_5C0]; unsigned __int16 *
0x1800bc552  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bc557  lea     rax, [rbp+670h+var_5C0]
0x1800bc55e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bc562  inc     rdx
0x1800bc565  cmp     [rax+rdx*2], r14w
0x1800bc56a  jnz     short loc_1800BC562
0x1800bc56c  lea     ecx, [rdx+rdx]
0x1800bc56f  add     rcx, 2
0x1800bc573  lea     rax, [rbp+670h+var_5C0]
0x1800bc57a  mov     [rsp+770h+var_710], rcx
0x1800bc57f  lea     rdi, byte_180147320
0x1800bc586  mov     [rsp+770h+var_718], rax
0x1800bc58b  lea     rcx, [rsp+770h+dwBytes]
0x1800bc590  mov     [rsp+770h+var_720], 16h
0x1800bc599  lea     rax, aPlaisrvupdatem; "PlaiSrvUpdateMetadata"
0x1800bc5a0  mov     [rsp+770h+var_728], rax
0x1800bc5a5  lea     r9, [rsp+770h+var_700]
0x1800bc5aa  mov     eax, 4
0x1800bc5af  lea     rdx, PLA_EVENT_ERROR
0x1800bc5b6  mov     [rsp+770h+var_730], rax
0x1800bc5bb  mov     [rsp+770h+ppObjectOpen], rcx
0x1800bc5c0  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800bc5c7  mov     [rsp+770h+riid], 1
0x1800bc5d0  mov     [rsp+770h+pSecurityDescriptor], rdi
0x1800bc5d5  lea     r8d, [rax+1]
0x1800bc5d9  mov     [rsp+770h+pStgOptions], rax
0x1800bc5de  call    EventingWriteEvent
0x1800bc5e3  mov     r13, [rbp+670h+pwcsName]
0x1800bc5e7  jmp     loc_1800BCDC2
0x1800bc5ec  mov     r13, [rbp+670h+pwcsName]
0x1800bc5f0  jmp     loc_1800BCDC6
0x1800bc5f5  mov     r13, [rbp+670h+pwcsName]
0x1800bc5f9  lea     rax, [rbp+670h+var_6E8]
0x1800bc5fd  mov     [rsp+770h+ppObjectOpen], rax; ppObjectOpen
0x1800bc602  xor     r9d, r9d; grfAttrs
0x1800bc605  lea     rax, IID_IPropertySetStorage
0x1800bc60c  mov     [rsp+770h+riid], rax; riid
0x1800bc611  mov     [rsp+770h+pSecurityDescriptor], rcx; pSecurityDescriptor
0x1800bc616  mov     [rsp+770h+pStgOptions], rcx; pStgOptions
0x1800bc61b  lea     edx, [r9+12h]; grfMode
0x1800bc61f  mov     rcx, r13; pwcsName
0x1800bc622  lea     r8d, [r9+3]; stgfmt
0x1800bc626  call    cs:__imp_StgOpenStorageEx
0x1800bc62c  test    eax, eax
0x1800bc62e  jns     loc_1800BC72A
0x1800bc634  call    cs:__imp_rand
0x1800bc63a  mov     ebx, eax
0x1800bc63c  call    cs:__imp_GetCurrentThreadId
0x1800bc642  xor     ebx, eax
0x1800bc644  mov     eax, 51EB851Fh
0x1800bc649  mul     ebx
0x1800bc64b  shr     edx, 5
0x1800bc64e  imul    eax, edx, 64h ; 'd'
0x1800bc651  sub     ebx, eax
0x1800bc653  mov     ecx, ebx; dwMilliseconds
0x1800bc655  call    cs:__imp_Sleep
0x1800bc65b  lea     rax, [rbp+670h+var_6E8]
0x1800bc65f  xor     r9d, r9d; grfAttrs
0x1800bc662  mov     [rsp+770h+ppObjectOpen], rax; ppObjectOpen
0x1800bc667  mov     rcx, r13; pwcsName
0x1800bc66a  lea     rax, IID_IPropertySetStorage
0x1800bc671  mov     [rsp+770h+riid], rax; riid
0x1800bc676  xor     eax, eax
0x1800bc678  mov     [rsp+770h+pSecurityDescriptor], rax; pSecurityDescriptor
0x1800bc67d  mov     [rsp+770h+pStgOptions], rax; pStgOptions
0x1800bc682  lea     edx, [rax+12h]; grfMode
0x1800bc685  lea     r8d, [rax+3]; stgfmt
0x1800bc689  call    cs:__imp_StgOpenStorageEx
0x1800bc68f  mov     ebx, eax
0x1800bc691  test    eax, eax
0x1800bc693  jns     loc_1800BC72A
0x1800bc699  xor     r14d, r14d
0x1800bc69c  mov     [rsp+770h+var_700], eax
0x1800bc6a0  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800bc6a7  mov     dword ptr [rsp+770h+dwBytes], r14d
0x1800bc6ac  jz      loc_1800BCDC6
0x1800bc6b2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bc6bc  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bc6c3  jz      loc_1800BCDC6
0x1800bc6c9  mov     rax, cs:qword_180169748
0x1800bc6d0  and     rax, rdx
0x1800bc6d3  cmp     cs:qword_180169748, rax
0x1800bc6da  jnz     loc_1800BCDC6
0x1800bc6e0  lea     rcx, [rbp+670h+var_540]; unsigned __int16 *
0x1800bc6e7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bc6ec  lea     rax, [rbp+670h+var_540]
0x1800bc6f3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bc6f7  inc     rdx
0x1800bc6fa  cmp     [rax+rdx*2], r14w
0x1800bc6ff  jnz     short loc_1800BC6F7
0x1800bc701  lea     rax, [rbp+670h+var_540]
0x1800bc708  lea     rdi, byte_180147320
0x1800bc70f  lea     ecx, [rdx+rdx]
0x1800bc712  add     rcx, 2
0x1800bc716  lea     r9, [rsp+770h+var_700]
0x1800bc71b  mov     [rsp+770h+var_710], rcx
0x1800bc720  lea     rcx, [rsp+770h+dwBytes]
0x1800bc725  jmp     loc_1800BCD6F
0x1800bc72a  mov     rcx, [rbp+670h+var_6E8]
0x1800bc72e  lea     rdx, [rbp+670h+var_6D0]
0x1800bc732  mov     [rsp+770h+pSecurityDescriptor], rdx
0x1800bc737  xor     r9d, r9d
0x1800bc73a  xor     r8d, r8d
0x1800bc73d  mov     dword ptr [rsp+770h+pStgOptions], 1012h
0x1800bc745  lea     rdx, ?FMTID_PlaDcsInfo@@3U_GUID@@A; _GUID FMTID_PlaDcsInfo
0x1800bc74c  mov     rax, [rcx]
0x1800bc74f  mov     rax, [rax+18h]
0x1800bc753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc758  mov     ebx, eax
0x1800bc75a  test    eax, eax
0x1800bc75c  jns     short loc_1800BC7D2
0x1800bc75e  xor     r14d, r14d
0x1800bc761  mov     [rsp+770h+var_700], eax
0x1800bc765  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800bc76c  mov     dword ptr [rsp+770h+dwBytes], r14d
0x1800bc771  jz      loc_1800BCDC6
0x1800bc777  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bc781  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bc788  jz      loc_1800BCDC6
0x1800bc78e  mov     rax, cs:qword_180169748
0x1800bc795  and     rax, rdx
0x1800bc798  cmp     cs:qword_180169748, rax
0x1800bc79f  jnz     loc_1800BCDC6
0x1800bc7a5  lea     rcx, [rbp+670h+var_4C0]; unsigned __int16 *
0x1800bc7ac  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bc7b1  lea     rax, [rbp+670h+var_4C0]
0x1800bc7b8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bc7bc  inc     rdx
0x1800bc7bf  cmp     [rax+rdx*2], r14w
0x1800bc7c4  jnz     short loc_1800BC7BC
0x1800bc7c6  lea     rax, [rbp+670h+var_4C0]
0x1800bc7cd  jmp     loc_1800BC708
0x1800bc7d2  mov     eax, [rdi+18h]
0x1800bc7d5  lea     rcx, [rax+1]; unsigned __int64
0x1800bc7d9  cmp     rcx, rax
0x1800bc7dc  jb      loc_1800BCCDC
0x1800bc7e2  lea     r8, [rsp+770h+dwBytes]; unsigned __int64 *
0x1800bc7e7  mov     [rsp+770h+dwBytes], rcx
0x1800bc7ec  mov     edx, 10h; unsigned __int64
0x1800bc7f1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800bc7f6  mov     ebx, eax
0x1800bc7f8  test    eax, eax
0x1800bc7fa  jns     short loc_1800BC870
0x1800bc7fc  xor     r14d, r14d
0x1800bc7ff  mov     [rsp+770h+var_700], eax
0x1800bc803  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800bc80a  mov     dword ptr [rsp+770h+dwBytes], r14d
0x1800bc80f  jz      loc_1800BCDC6
0x1800bc815  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bc81f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bc826  jz      loc_1800BCDC6
0x1800bc82c  mov     rax, cs:qword_180169748
0x1800bc833  and     rax, rdx
0x1800bc836  cmp     cs:qword_180169748, rax
0x1800bc83d  jnz     loc_1800BCDC6
0x1800bc843  lea     rcx, [rbp+670h+var_440]; unsigned __int16 *
0x1800bc84a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bc84f  lea     rax, [rbp+670h+var_440]
0x1800bc856  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bc85a  inc     rdx
0x1800bc85d  cmp     [rax+rdx*2], r14w
0x1800bc862  jnz     short loc_1800BC85A
0x1800bc864  lea     rax, [rbp+670h+var_440]
0x1800bc86b  jmp     loc_1800BC708
0x1800bc870  mov     rcx, [rsp+770h+dwBytes]; dwBytes
0x1800bc875  lea     rdi, byte_180147320
0x1800bc87c  xor     r8d, r8d; int
0x1800bc87f  mov     r9, rdi; char *
0x1800bc882  lea     edx, [r8+1]; int
0x1800bc886  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800bc88b  mov     r12, rax
0x1800bc88e  test    rax, rax
0x1800bc891  jnz     short loc_1800BC90E
0x1800bc893  xor     r14d, r14d
0x1800bc896  mov     eax, 8007000Eh
0x1800bc89b  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800bc8a2  mov     ebx, eax
0x1800bc8a4  mov     dword ptr [rsp+770h+dwBytes], r14d
0x1800bc8a9  mov     [rsp+770h+var_700], eax
0x1800bc8ad  jz      loc_1800BCDC2
0x1800bc8b3  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bc8bd  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bc8c4  jz      loc_1800BCDC2
0x1800bc8ca  mov     rax, cs:qword_180169748
0x1800bc8d1  and     rax, rdx
0x1800bc8d4  cmp     cs:qword_180169748, rax
0x1800bc8db  jnz     loc_1800BCDC2
0x1800bc8e1  lea     rcx, [rbp+670h+var_3C0]; unsigned __int16 *
0x1800bc8e8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800bc8ed  lea     rax, [rbp+670h+var_3C0]
0x1800bc8f4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bc8f8  inc     rdx
0x1800bc8fb  cmp     [rax+rdx*2], r14w
0x1800bc900  jnz     short loc_1800BC8F8
0x1800bc902  lea     rax, [rbp+670h+var_3C0]
0x1800bc909  jmp     loc_1800BC70F
0x1800bc90e  mov     rax, [rbp+670h+psa]
0x1800bc912  mov     eax, [rax+18h]
0x1800bc915  lea     rcx, [rax+1]; unsigned __int64
0x1800bc919  cmp     rcx, rax
0x1800bc91c  jb      loc_1800BCC61
0x1800bc922  lea     r8, [rsp+770h+dwBytes]; unsigned __int64 *
0x1800bc927  mov     [rsp+770h+dwBytes], rcx
0x1800bc92c  mov     edx, 18h; unsigned __int64
0x1800bc931  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800bc936  mov     ebx, eax
0x1800bc938  test    eax, eax
0x1800bc93a  jns     short loc_1800BC9B0
0x1800bc93c  xor     r14d, r14d
0x1800bc93f  mov     [rsp+770h+var_700], eax
0x1800bc943  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800bc94a  mov     dword ptr [rsp+770h+dwBytes], r14d
0x1800bc94f  jz      loc_1800BCDC2
0x1800bc955  mov     rdx, 4000000000000800h; unsigned __int64
0x1800bc95f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800bc966  jz      loc_1800BCDC2
0x1800bc96c  mov     rax, cs:qword_180169748
0x1800bc973  and     rax, rdx
  ... truncated ...
```

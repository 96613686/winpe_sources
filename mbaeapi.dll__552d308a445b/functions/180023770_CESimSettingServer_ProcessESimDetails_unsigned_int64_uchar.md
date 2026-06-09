# CESimSettingServer::ProcessESimDetails(unsigned __int64,uchar *)

- ea: `0x180023770`
- end: `0x1800242eb`
- name: `?ProcessESimDetails@CESimSettingServer@@AEAAX_KPEAE@Z`
- size: `2939`
- prototype: `void __fastcall(CESimSettingServer *__hidden this, unsigned __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18001fc54`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x1800028b0`
- `0x1800028ec`
- `0x180002efc`
- `0x1800040cd`
- `0x180009ffc`
- `0x18001105c`
- `0x1800171b8`
- `0x1800172bc`
- `0x18001c950`
- `0x18001dd10`
- `0x18001e0d0`
- `0x180020994`
- `0x180020b40`
- `0x180023770`
- `0x180025eb0`
- `0x180026e74`
- `0x18005c010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002416a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002416a`

## string_xrefs

- `0x180023a70`: `The LPA_ESIM_INFO in eSIM information update is missing fields, dwParam = 0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CESimSettingServer::ProcessESimDetails(
        CESimSettingServer *this,
        unsigned __int64 a2,
        unsigned __int8 *a3)
{
  CESimSettingServer *v5; // r15
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rbx
  __int64 v10; // r14
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  const struct _tlgProvider_t *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned __int8 *v20; // rdx
  unsigned __int64 v21; // r8
  __int64 AdapterSlotPair; // r13
  __int128 *v23; // r9
  const struct _tlgProvider_t *v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 AdapterSlotData; // r12
  const unsigned __int16 *v28; // rbx
  const struct _tlgProvider_t *v29; // rax
  __int64 v30; // r8
  __int64 v31; // r9
  int v32; // r9d
  int v33; // edx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // eax
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  int v43; // edx
  int v44; // ecx
  int v45; // ecx
  int v46; // ecx
  unsigned int v47; // ebx
  __int16 *v48; // rax
  __int64 v49; // rdx
  _WORD *v50; // rcx
  unsigned int v51; // r12d
  __int16 v52; // r8
  _WORD *v53; // rcx
  unsigned __int16 *v54; // rax
  int v55; // edx
  int v56; // r8d
  __int64 v57; // rdx
  unsigned __int8 *v58; // r8
  __int64 v59; // rax
  __int16 v60; // r10
  unsigned __int8 *v61; // rbx
  const unsigned __int16 *v62; // r14
  _QWORD *v63; // r10
  _QWORD *i; // rax
  unsigned __int8 *v65; // rcx
  signed __int64 v66; // r9
  int v67; // edx
  int v68; // r8d
  unsigned __int16 *v69; // r14
  __int64 v70; // rax
  __int64 v71; // rdx
  unsigned __int8 *v72; // r8
  __int64 v73; // rax
  unsigned __int16 *v74; // rcx
  unsigned __int16 v75; // r9
  const unsigned __int16 *v76; // r15
  __int64 v77; // rbx
  _QWORD *v78; // rax
  _QWORD *v79; // rcx
  int v80; // r14d
  __int64 *v81; // rsi
  __int64 *v82; // rbx
  __int64 *v83; // rdi
  int v84; // eax
  int v85; // eax
  void *v86; // rax
  const struct _tlgProvider_t *v87; // rax
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 v90; // [rsp+20h] [rbp-B9h]
  __int64 v91; // [rsp+20h] [rbp-B9h]
  __int64 v92; // [rsp+20h] [rbp-B9h]
  unsigned __int16 *v93[2]; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v94; // [rsp+48h] [rbp-91h]
  unsigned __int16 *v95; // [rsp+50h] [rbp-89h] BYREF
  const unsigned __int16 *v96; // [rsp+58h] [rbp-81h] BYREF
  unsigned __int16 *v97; // [rsp+60h] [rbp-79h] BYREF
  __int128 Buf2; // [rsp+68h] [rbp-71h] BYREF
  __int64 v99; // [rsp+78h] [rbp-61h]
  __int128 v100; // [rsp+80h] [rbp-59h] BYREF
  __int64 v101; // [rsp+90h] [rbp-49h]
  unsigned __int64 v102; // [rsp+98h] [rbp-41h]
  _BYTE v103[80]; // [rsp+A0h] [rbp-39h] BYREF

  v5 = this;
  v95 = (unsigned __int16 *)this;
  *(_OWORD *)v93 = 0;
  v94 = 0;
  Buf2 = 0;
  v99 = 0;
  std::vector<unsigned short>::resize(v93);
  std::vector<unsigned short>::resize(&Buf2);
  StringCchPrintfW(v93[0], v93[1] - v93[0], L"Enter");
  StringCchPrintfW(
    (unsigned __int16 *)Buf2,
    (__int64)(*((_QWORD *)&Buf2 + 1) - Buf2) >> 1,
    L"%S(%d):%s",
    "CESimSettingServer::ProcessESimDetails",
    611,
    v93[0]);
  v6 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v96 = (const unsigned __int16 *)Buf2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)byte_18007595B,
      v7,
      v8,
      &v96);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)&Buf2);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
  if ( a3 )
  {
    v9 = 720;
    if ( a2 >= 0x2D0 )
    {
      v10 = 33;
      if ( (a3[4] & 0x21) == 0x21 )
        v9 = 120 * (*((unsigned int *)a3 + 26) + 6LL);
      if ( v9 != a2 )
      {
        Buf2 = 0;
        v99 = 0;
        *(_OWORD *)v93 = 0;
        v94 = 0;
        std::vector<unsigned short>::resize(&Buf2);
        std::vector<unsigned short>::resize(v93);
        LODWORD(v90) = a2;
        StringCchPrintfW(
          (unsigned __int16 *)Buf2,
          (__int64)(*((_QWORD *)&Buf2 + 1) - Buf2) >> 1,
          L"Failed the size check, expected: %ld, actual: %ld",
          (unsigned int)v9,
          v90);
        LODWORD(v91) = 633;
        StringCchPrintfW(
          v93[0],
          v93[1] - v93[0],
          L"%S(%d):%s",
          "CESimSettingServer::ProcessESimDetails",
          v91,
          (_QWORD)Buf2);
        v11 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v11 > 2u )
        {
          v95 = v93[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v11,
            (__int64)word_18007593A,
            v12,
            v13,
            (const unsigned __int16 **)&v95);
        }
LABEL_10:
        std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
        std::vector<unsigned short>::~vector<unsigned short>((char **)&Buf2);
        return;
      }
      if ( (a3[4] & 1) == 0 )
      {
        Buf2 = 0;
        v99 = 0;
        *(_OWORD *)v93 = 0;
        v94 = 0;
        std::vector<unsigned short>::resize(&Buf2);
        std::vector<unsigned short>::resize(v93);
        StringCchPrintfW(
          (unsigned __int16 *)Buf2,
          (__int64)(*((_QWORD *)&Buf2 + 1) - Buf2) >> 1,
          L"eSim detail notification does not have eSim info. Ignore the notification.");
        LODWORD(v90) = 639;
        StringCchPrintfW(
          v93[0],
          v93[1] - v93[0],
          L"%S(%d):%s",
          "CESimSettingServer::ProcessESimDetails",
          v90,
          (_QWORD)Buf2);
        v14 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v14 > 4u )
        {
          v95 = v93[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v14,
            (__int64)word_18007591A,
            v15,
            v16,
            (const unsigned __int16 **)&v95);
        }
        goto LABEL_10;
      }
      if ( (a3[8] & 0xB) != 0xB )
      {
        Buf2 = 0;
        v99 = 0;
        *(_OWORD *)v93 = 0;
        v94 = 0;
        std::vector<unsigned short>::resize(&Buf2);
        std::vector<unsigned short>::resize(v93);
        StringCchPrintfW(
          (unsigned __int16 *)Buf2,
          (__int64)(*((_QWORD *)&Buf2 + 1) - Buf2) >> 1,
          L"The LPA_ESIM_INFO in eSIM information update is missing fields, dwParam = 0x%08x.",
          *((unsigned int *)a3 + 2));
        LODWORD(v90) = 646;
        StringCchPrintfW(
          v93[0],
          v93[1] - v93[0],
          L"%S(%d):%s",
          "CESimSettingServer::ProcessESimDetails",
          v90,
          (_QWORD)Buf2);
        v17 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v17 > 2u )
        {
          v95 = v93[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v17,
            (__int64)byte_1800758F9,
            v18,
            v19,
            (const unsigned __int16 **)&v95);
        }
        goto LABEL_10;
      }
      v20 = a3 + 12;
      v100 = 0;
      v101 = 0;
      v102 = 0;
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)&v20[2 * v21] );
      std::wstring::_Construct<1,unsigned short const *>((char **)&v100, v20, v21);
      AdapterSlotPair = CESimSettingServer::GetAdapterSlotPair(v5, &v100);
      if ( !AdapterSlotPair )
      {
        Buf2 = 0;
        v99 = 0;
        *(_OWORD *)v93 = 0;
        v94 = 0;
        std::vector<unsigned short>::resize(&Buf2);
        std::vector<unsigned short>::resize(v93);
        v23 = &v100;
        if ( v102 > 7 )
          v23 = (__int128 *)v100;
        StringCchPrintfW(
          (unsigned __int16 *)Buf2,
          (__int64)(*((_QWORD *)&Buf2 + 1) - Buf2) >> 1,
          L"No record found for eSIM - {%ls}",
          v23);
        LODWORD(v90) = 655;
        StringCchPrintfW(
          v93[0],
          v93[1] - v93[0],
          L"%S(%d):%s",
          "CESimSettingServer::ProcessESimDetails",
          v90,
          (_QWORD)Buf2);
        v24 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v24 > 3u )
        {
          v95 = v93[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v24,
            (__int64)&word_1800758D6,
            v25,
            v26,
            (const unsigned __int16 **)&v95);
        }
LABEL_136:
        std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
        std::vector<unsigned short>::~vector<unsigned short>((char **)&Buf2);
        std::wstring::~wstring((char **)&v100);
        return;
      }
      AdapterSlotData = CESimSettingServer::GetAdapterSlotData(v5, &v100);
      v28 = *(const unsigned __int16 **)(AdapterSlotData + 16);
      v96 = v28;
      if ( (a3[4] & 2) == 0 )
      {
LABEL_56:
        if ( *((_DWORD *)a3 + 25) == 3 )
        {
          CESimSettingServer::RemoveESimData((__int64)v5, &v100);
        }
        else
        {
          if ( (a3[8] & 4) != 0 )
          {
            v39 = *((_DWORD *)a3 + 24);
            if ( *((_DWORD *)v28 + 140) != v39 )
            {
              *((_DWORD *)v28 + 140) = v39;
              (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*((_QWORD *)v5 + 1) + 48LL))(
                (__int64)v5 + 8,
                AdapterSlotPair,
                *(unsigned int *)(AdapterSlotPair + 16),
                *((unsigned int *)a3 + 24));
            }
          }
          if ( (a3[8] & 8) == 0
            || ((v40 = *((_DWORD *)a3 + 25)) == 0 || (v41 = v40 - 1) == 0 || (v42 = v41 - 1) == 0
              ? (v43 = 2)
              : (v43 = v42 == 1),
                *(_DWORD *)AdapterSlotData == v43) )
          {
            v51 = 0;
          }
          else
          {
            v44 = *((_DWORD *)a3 + 25);
            if ( v44 && (v45 = v44 - 1) != 0 && (v46 = v45 - 1) != 0 )
              v47 = v46 == 1;
            else
              v47 = 2;
            *(_DWORD *)AdapterSlotData = v47;
            memset_0(v103, 0, 0x42u);
            v48 = (__int16 *)&v100;
            if ( v102 > 7 )
              v48 = (__int16 *)v100;
            v49 = 2147483646;
            v50 = v103;
            v51 = 0;
            while ( v49 )
            {
              v52 = *v48;
              if ( *v48 )
              {
                ++v48;
                *v50++ = v52;
                --v49;
                if ( --v10 )
                  continue;
              }
              if ( !v10 )
                --v50;
              break;
            }
            *v50 = 0;
            (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _BYTE *))(*((_QWORD *)v5 + 1) + 56LL))(
              (__int64)v5 + 8,
              AdapterSlotPair,
              *(unsigned int *)(AdapterSlotPair + 16),
              v47,
              v103);
            v28 = v96;
          }
          if ( (a3[4] & 0x40) != 0 && a3 != (unsigned __int8 *)-158LL )
          {
            v53 = v28 + 20;
            v54 = (unsigned __int16 *)(v28 + 20);
            do
            {
              v55 = *(unsigned __int16 *)((char *)v54 + a3 + 158 - (unsigned __int8 *)(v28 + 20));
              v56 = *v54 - v55;
              if ( v56 )
                break;
              ++v54;
            }
            while ( v55 );
            if ( v56 )
            {
              v57 = 2147483646;
              v58 = a3 + 158;
              v59 = 260;
              while ( v57 )
              {
                v60 = *(_WORD *)v58;
                if ( *(_WORD *)v58 )
                {
                  v58 += 2;
                  *v53++ = v60;
                  --v57;
                  if ( --v59 )
                    continue;
                }
                if ( !v59 )
                  --v53;
                break;
              }
              *v53 = 0;
              (*(void (__fastcall **)(__int64, __int64, _QWORD))(*((_QWORD *)v5 + 1) + 40LL))(
                (__int64)v5 + 8,
                AdapterSlotPair,
                *(unsigned int *)(AdapterSlotPair + 16));
            }
          }
          if ( (a3[4] & 0x20) != 0 )
          {
            v61 = a3 + 720;
            if ( *((_DWORD *)a3 + 26) )
            {
              v62 = v96;
              do
              {
                v63 = (_QWORD *)*((_QWORD *)v62 + 71);
                for ( i = (_QWORD *)*v63; i != v63; i = (_QWORD *)*i )
                {
                  v65 = (unsigned __int8 *)i[2];
                  v66 = &v61[120 * v51 + 4] - v65;
                  do
                  {
                    v67 = *(unsigned __int16 *)&v65[v66];
                    v68 = *(unsigned __int16 *)v65 - v67;
                    if ( v68 )
                      break;
                    v65 += 2;
                  }
                  while ( v67 );
                  if ( !v68 )
                  {
                    CESimSettingServer::UpdateESimProfileCache(
                      (__int64)v5,
                      (unsigned int *)&v61[120 * v51],
                      (const unsigned __int16 *)&v100,
                      0);
                    goto LABEL_117;
                  }
                }
                v69 = (unsigned __int16 *)operator new(0x3A0u);
                v97 = v69;
                memset_0(v69, 0, 0x3A0u);
                v70 = *((_QWORD *)v69 + 113);
                if ( v70 != *((_QWORD *)v69 + 114) )
                  *((_QWORD *)v69 + 114) = v70;
                v71 = 2147483646;
                v72 = &v61[120 * v51 + 4];
                v73 = 21;
                v74 = v69;
                while ( v71 )
                {
                  v75 = *(_WORD *)v72;
                  if ( *(_WORD *)v72 )
                  {
                    v72 += 2;
                    *v74++ = v75;
                    --v71;
                    if ( --v73 )
                      continue;
                  }
                  if ( !v73 )
                    --v74;
                  break;
                }
                *v74 = 0;
                v76 = v96 + 284;
                if ( *((_QWORD *)v96 + 72) == 0xAAAAAAAAAAAAAAALL )
                  std::_Xlength_error("list too long");
                v77 = *(_QWORD *)v76;
                Buf2 = (unsigned __int64)(v96 + 284);
                v78 = operator new(0x18u);
                v78[2] = v69;
                ++*((_QWORD *)v76 + 1);
                v79 = *(_QWORD **)(v77 + 8);
                *v78 = v77;
                v78[1] = v79;
                *((_QWORD *)&Buf2 + 1) = 0;
                *(_QWORD *)(v77 + 8) = v78;
                *v79 = v78;
                v61 = a3 + 720;
                v5 = (CESimSettingServer *)v95;
                v62 = v96;
                CESimSettingServer::UpdateESimProfileCache(
                  (__int64)v95,
                  (unsigned int *)&a3[120 * v51 + 720],
                  (const unsigned __int16 *)&v100,
                  1);
LABEL_117:
                ++v51;
              }
              while ( v51 < *((_DWORD *)a3 + 26) );
            }
          }
          Buf2 = *(_OWORD *)AdapterSlotPair;
          v80 = *(_DWORD *)(AdapterSlotPair + 16);
          LODWORD(v99) = v80;
          v81 = (__int64 *)*((_QWORD *)v5 + 17);
          v82 = (__int64 *)v81[1];
          HIDWORD(v93[1]) = 0;
          v83 = v81;
          while ( !*((_BYTE *)v82 + 25) )
          {
            v84 = memcmp_0((char *)v82 + 28, &Buf2, 0x10u);
            if ( v84 >= 0 && (v84 || *((_DWORD *)v82 + 11) >= v80) )
            {
              v83 = v82;
              v82 = (__int64 *)*v82;
            }
            else
            {
              v82 = (__int64 *)v82[2];
            }
          }
          if ( *((_BYTE *)v83 + 25)
            || (v85 = memcmp_0(&Buf2, (char *)v83 + 28, 0x10u), v85 < 0)
            || !v85 && v80 < *((_DWORD *)v83 + 11) )
          {
            v83 = v81;
          }
          if ( v83 != v81 )
          {
            v86 = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<_GUID,enum SimSlot> const,bool>>>::_Extract(
                            (char *)v5 + 136,
                            v83);
            operator delete(v86);
            if ( !*((_QWORD *)v95 + 18) )
            {
              Buf2 = 0;
              (*(void (__fastcall **)(unsigned __int16 *, __int128 *, _QWORD, const unsigned __int16 *))(*((_QWORD *)v95 + 1) + 72LL))(
                v95 + 4,
                &Buf2,
                *(unsigned int *)(AdapterSlotPair + 16),
                &dword_1800684AC);
            }
          }
        }
        Buf2 = 0;
        v99 = 0;
        *(_OWORD *)v93 = 0;
        v94 = 0;
        std::vector<unsigned short>::resize(&Buf2);
        std::vector<unsigned short>::resize(v93);
        StringCchPrintfW((unsigned __int16 *)Buf2, (__int64)(*((_QWORD *)&Buf2 + 1) - Buf2) >> 1, L"Exit");
        LODWORD(v90) = 816;
        StringCchPrintfW(
          v93[0],
          v93[1] - v93[0],
          L"%S(%d):%s",
          "CESimSettingServer::ProcessESimDetails",
          v90,
          (_QWORD)Buf2);
        v87 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v87 > 5u )
        {
          v97 = v93[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v87,
            (__int64)byte_180075893,
            v88,
            v89,
            (const unsigned __int16 **)&v97);
        }
        goto LABEL_136;
      }
      Buf2 = 0;
      v99 = 0;
      *(_OWORD *)v93 = 0;
      v94 = 0;
      std::vector<unsigned short>::resize(&Buf2);
      std::vector<unsigned short>::resize(v93);
      LODWORD(v90) = *((_DWORD *)a3 + 172);
      StringCchPrintfW(
        (unsigned __int16 *)Buf2,
        (__int64)(*((_QWORD *)&Buf2 + 1) - Buf2) >> 1,
        L"Got ESimDetail operation: %d, subOperation: %d",
        *((unsigned int *)a3 + 170),
        v90);
      LODWORD(v92) = 666;
      StringCchPrintfW(
        v93[0],
        v93[1] - v93[0],
        L"%S(%d):%s",
        "CESimSettingServer::ProcessESimDetails",
        v92,
        (_QWORD)Buf2);
      v29 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v29 > 4u )
      {
        v97 = v93[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v29,
          (__int64)&word_1800758B6,
          v30,
          v31,
          (const unsigned __int16 **)&v97);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
      std::vector<unsigned short>::~vector<unsigned short>((char **)&Buf2);
      v32 = 0;
      v33 = 0;
      v34 = *((_DWORD *)a3 + 170);
      if ( !v34 )
      {
        v32 = 1;
        goto LABEL_53;
      }
      v35 = v34 - 1;
      if ( !v35 )
      {
        v32 = 2;
        v33 = 1;
        goto LABEL_53;
      }
      v36 = v35 - 1;
      if ( !v36 )
      {
        v32 = 2;
        v33 = 2;
        goto LABEL_53;
      }
      v37 = v36 - 1;
      if ( !v37 )
      {
        v32 = 2;
        v33 = 3;
        goto LABEL_53;
      }
      v38 = v37 - 2;
      if ( !v38 )
      {
        v32 = 2;
        v33 = 7;
        goto LABEL_53;
      }
      if ( (unsigned int)(v38 - 1) <= 1 )
      {
        v32 = 2;
        if ( (a3[4] & 8) != 0 )
        {
          if ( *((_DWORD *)a3 + 172) == 1 )
          {
LABEL_47:
            v33 = 8;
            goto LABEL_53;
          }
          if ( *((_DWORD *)a3 + 172) == 2 )
          {
            v33 = 9;
          }
          else if ( *((_DWORD *)a3 + 172) == 3 )
          {
            v33 = 4;
          }
          else
          {
            if ( *((_DWORD *)a3 + 172) != 4 )
            {
              if ( *((_DWORD *)a3 + 172) != 5 )
              {
                if ( *((_DWORD *)a3 + 172) == 6 )
                  v33 = 10;
                goto LABEL_53;
              }
              goto LABEL_47;
            }
            v33 = 5;
          }
        }
      }
LABEL_53:
      if ( *((_DWORD *)v28 + 8) != v32 || *((_DWORD *)v28 + 9) != v33 )
      {
        *((_DWORD *)v28 + 8) = v32;
        *((_DWORD *)v28 + 9) = v33;
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*((_QWORD *)v5 + 1) + 32LL))(
          (__int64)v5 + 8,
          AdapterSlotPair,
          *(unsigned int *)(AdapterSlotPair + 16));
      }
      goto LABEL_56;
    }
  }
}

```

## disassembly

```asm
0x180023770  mov     [rsp-8+arg_18], rbx
0x180023775  push    rbp
0x180023776  push    rsi
0x180023777  push    rdi
0x180023778  push    r12
0x18002377a  push    r13
0x18002377c  push    r14
0x18002377e  push    r15
0x180023780  lea     rbp, [rsp-27h]
0x180023785  sub     rsp, 100h
0x18002378c  mov     rax, cs:__security_cookie
0x180023793  xor     rax, rsp
0x180023796  mov     [rbp+57h+var_40], rax
0x18002379a  mov     rdi, r8
0x18002379d  mov     rsi, rdx
0x1800237a0  mov     r15, rcx
0x1800237a3  mov     [rsp+130h+var_E0], rcx
0x1800237a8  xorps   xmm0, xmm0
0x1800237ab  movdqu  xmmword ptr [rsp+130h+var_F8], xmm0
0x1800237b1  xor     r12d, r12d
0x1800237b4  mov     [rsp+130h+var_E8], r12
0x1800237b9  movdqu  [rbp+57h+Buf2], xmm0
0x1800237be  mov     [rbp+57h+var_B8], r12
0x1800237c2  lea     rcx, [rsp+130h+var_F8]
0x1800237c7  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800237cc  lea     rcx, [rbp+57h+Buf2]
0x1800237d0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800237d5  mov     rdx, [rsp+130h+var_F8+8]
0x1800237da  mov     rcx, [rsp+130h+var_F8]; unsigned __int16 *
0x1800237df  sub     rdx, rcx
0x1800237e2  sar     rdx, 1; unsigned __int64
0x1800237e5  lea     r8, aEnter; "Enter"
0x1800237ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800237f1  mov     rdx, qword ptr [rbp+57h+Buf2+8]
0x1800237f5  mov     rcx, qword ptr [rbp+57h+Buf2]; unsigned __int16 *
0x1800237f9  sub     rdx, rcx
0x1800237fc  sar     rdx, 1; unsigned __int64
0x1800237ff  mov     rax, [rsp+130h+var_F8]
0x180023804  mov     [rsp+130h+var_108], rax
0x180023809  mov     dword ptr [rsp+130h+var_110], 263h
0x180023811  lea     r13, aCesimsettingse_20; "CESimSettingServer::ProcessESimDetails"
0x180023818  mov     r9, r13
0x18002381b  lea     r8, aSDS; "%S(%d):%s"
0x180023822  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023827  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18002382c  mov     ecx, [rax]
0x18002382e  cmp     ecx, 5
0x180023831  jbe     short loc_180023856
0x180023833  mov     rcx, qword ptr [rbp+57h+Buf2]
0x180023837  mov     [rsp+130h+var_D8], rcx
0x18002383c  lea     rcx, [rsp+130h+var_D8]
0x180023841  mov     [rsp+130h+var_110], rcx
0x180023846  lea     rdx, byte_18007595B
0x18002384d  mov     rcx, rax
0x180023850  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180023855  nop
0x180023856  lea     rcx, [rbp+57h+Buf2]
0x18002385a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002385f  nop
0x180023860  lea     rcx, [rsp+130h+var_F8]
0x180023865  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002386a  test    rdi, rdi
0x18002386d  jz      loc_1800242C4
0x180023873  mov     ebx, 2D0h
0x180023878  cmp     rsi, rbx
0x18002387b  jb      loc_1800242C4
0x180023881  mov     eax, [rdi+4]
0x180023884  mov     r14d, 21h ; '!'
0x18002388a  and     eax, r14d
0x18002388d  cmp     al, r14b
0x180023890  jnz     short loc_18002389D
0x180023892  mov     eax, [rdi+68h]
0x180023895  add     rax, 6
0x180023899  imul    rbx, rax, 78h ; 'x'
0x18002389d  xorps   xmm0, xmm0
0x1800238a0  cmp     rbx, rsi
0x1800238a3  jz      loc_18002396E
0x1800238a9  movdqu  [rbp+57h+Buf2], xmm0
0x1800238ae  mov     [rbp+57h+var_B8], r12
0x1800238b2  movdqu  xmmword ptr [rsp+130h+var_F8], xmm0
0x1800238b8  mov     [rsp+130h+var_E8], r12
0x1800238bd  lea     rcx, [rbp+57h+Buf2]
0x1800238c1  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800238c6  lea     rcx, [rsp+130h+var_F8]
0x1800238cb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800238d0  mov     r9d, ebx
0x1800238d3  mov     rdx, qword ptr [rbp+57h+Buf2+8]
0x1800238d7  mov     rcx, qword ptr [rbp+57h+Buf2]; unsigned __int16 *
0x1800238db  sub     rdx, rcx
0x1800238de  sar     rdx, 1; unsigned __int64
0x1800238e1  mov     dword ptr [rsp+130h+var_110], esi
0x1800238e5  lea     r8, aFailedTheSizeC_0; "Failed the size check, expected: %ld, a"...
0x1800238ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800238f1  mov     rdx, [rsp+130h+var_F8+8]
0x1800238f6  mov     rcx, [rsp+130h+var_F8]; unsigned __int16 *
0x1800238fb  sub     rdx, rcx
0x1800238fe  sar     rdx, 1; unsigned __int64
0x180023901  mov     rax, qword ptr [rbp+57h+Buf2]
0x180023905  mov     [rsp+130h+var_108], rax
0x18002390a  mov     dword ptr [rsp+130h+var_110], 279h
0x180023912  mov     r9, r13
0x180023915  lea     r8, aSDS; "%S(%d):%s"
0x18002391c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023921  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180023926  mov     ecx, [rax]
0x180023928  mov     esi, 2
0x18002392d  cmp     ecx, esi
0x18002392f  jbe     short loc_180023955
0x180023931  mov     rcx, [rsp+130h+var_F8]
0x180023936  mov     [rsp+130h+var_E0], rcx
0x18002393b  lea     rcx, [rsp+130h+var_E0]
0x180023940  mov     [rsp+130h+var_110], rcx
0x180023945  lea     rdx, word_18007593A
0x18002394c  mov     rcx, rax
0x18002394f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180023954  nop
0x180023955  lea     rcx, [rsp+130h+var_F8]
0x18002395a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002395f  nop
0x180023960  lea     rcx, [rbp+57h+Buf2]
0x180023964  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180023969  jmp     loc_1800242C4
0x18002396e  test    byte ptr [rdi+4], 1
0x180023972  jnz     loc_180023A29
0x180023978  movdqu  [rbp+57h+Buf2], xmm0
0x18002397d  mov     [rbp+57h+var_B8], r12
0x180023981  movdqu  xmmword ptr [rsp+130h+var_F8], xmm0
0x180023987  mov     [rsp+130h+var_E8], r12
0x18002398c  lea     rcx, [rbp+57h+Buf2]
0x180023990  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180023995  lea     rcx, [rsp+130h+var_F8]
0x18002399a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002399f  mov     rdx, qword ptr [rbp+57h+Buf2+8]
0x1800239a3  mov     rcx, qword ptr [rbp+57h+Buf2]; unsigned __int16 *
0x1800239a7  sub     rdx, rcx
0x1800239aa  sar     rdx, 1; unsigned __int64
0x1800239ad  lea     r8, aEsimDetailNoti; "eSim detail notification does not have "...
0x1800239b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800239b9  mov     rdx, [rsp+130h+var_F8+8]
0x1800239be  mov     rcx, [rsp+130h+var_F8]; unsigned __int16 *
0x1800239c3  sub     rdx, rcx
0x1800239c6  sar     rdx, 1; unsigned __int64
0x1800239c9  mov     rax, qword ptr [rbp+57h+Buf2]
0x1800239cd  mov     [rsp+130h+var_108], rax
0x1800239d2  mov     dword ptr [rsp+130h+var_110], 27Fh
0x1800239da  mov     r9, r13
0x1800239dd  lea     r8, aSDS; "%S(%d):%s"
0x1800239e4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800239e9  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800239ee  mov     ecx, [rax]
0x1800239f0  cmp     ecx, 4
0x1800239f3  jbe     short loc_180023A19
0x1800239f5  mov     rcx, [rsp+130h+var_F8]
0x1800239fa  mov     [rsp+130h+var_E0], rcx
0x1800239ff  lea     rcx, [rsp+130h+var_E0]
0x180023a04  mov     [rsp+130h+var_110], rcx
0x180023a09  lea     rdx, word_18007591A
0x180023a10  mov     rcx, rax
0x180023a13  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180023a18  nop
0x180023a19  lea     rcx, [rsp+130h+var_F8]
0x180023a1e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180023a23  nop
0x180023a24  jmp     loc_180023960
0x180023a29  mov     eax, [rdi+8]
0x180023a2c  and     eax, 0Bh
0x180023a2f  cmp     al, 0Bh
0x180023a31  jz      loc_180023AF0
0x180023a37  movdqu  [rbp+57h+Buf2], xmm0
0x180023a3c  mov     [rbp+57h+var_B8], r12
0x180023a40  movdqu  xmmword ptr [rsp+130h+var_F8], xmm0
0x180023a46  mov     [rsp+130h+var_E8], r12
0x180023a4b  lea     rcx, [rbp+57h+Buf2]
0x180023a4f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180023a54  lea     rcx, [rsp+130h+var_F8]
0x180023a59  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180023a5e  mov     rdx, qword ptr [rbp+57h+Buf2+8]
0x180023a62  mov     rcx, qword ptr [rbp+57h+Buf2]; unsigned __int16 *
0x180023a66  sub     rdx, rcx
0x180023a69  sar     rdx, 1; unsigned __int64
0x180023a6c  mov     r9d, [rdi+8]
0x180023a70  lea     r8, aTheLpaEsimInfo; "The LPA_ESIM_INFO in eSIM information u"...
0x180023a77  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023a7c  mov     rdx, [rsp+130h+var_F8+8]
0x180023a81  mov     rcx, [rsp+130h+var_F8]; unsigned __int16 *
0x180023a86  sub     rdx, rcx
0x180023a89  sar     rdx, 1; unsigned __int64
0x180023a8c  mov     rax, qword ptr [rbp+57h+Buf2]
0x180023a90  mov     [rsp+130h+var_108], rax
0x180023a95  mov     dword ptr [rsp+130h+var_110], 286h
0x180023a9d  mov     r9, r13
0x180023aa0  lea     r8, aSDS; "%S(%d):%s"
0x180023aa7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023aac  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180023ab1  mov     ecx, [rax]
0x180023ab3  mov     esi, 2
0x180023ab8  cmp     ecx, esi
0x180023aba  jbe     short loc_180023AE0
0x180023abc  mov     rcx, [rsp+130h+var_F8]
0x180023ac1  mov     [rsp+130h+var_E0], rcx
0x180023ac6  lea     rcx, [rsp+130h+var_E0]
0x180023acb  mov     [rsp+130h+var_110], rcx
0x180023ad0  lea     rdx, byte_1800758F9
0x180023ad7  mov     rcx, rax
0x180023ada  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180023adf  nop
0x180023ae0  lea     rcx, [rsp+130h+var_F8]
0x180023ae5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180023aea  nop
0x180023aeb  jmp     loc_180023960
0x180023af0  lea     rdx, [rdi+0Ch]
0x180023af4  movups  [rbp+57h+var_B0], xmm0
0x180023af8  mov     [rbp+57h+var_A0], r12
0x180023afc  mov     [rbp+57h+var_98], r12
0x180023b00  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023b04  inc     r8
0x180023b07  cmp     [rdx+r8*2], r12w
0x180023b0c  jnz     short loc_180023B04
0x180023b0e  lea     rcx, [rbp+57h+var_B0]
0x180023b12  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180023b17  nop
0x180023b18  lea     rdx, [rbp+57h+var_B0]
0x180023b1c  mov     rcx, r15
0x180023b1f  call    ?GetAdapterSlotPair@CESimSettingServer@@AEAAPEBU?$pair@U_GUID@@W4SimSlot@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; CESimSettingServer::GetAdapterSlotPair(std::wstring const &)
0x180023b24  mov     r13, rax
0x180023b27  test    rax, rax
0x180023b2a  jnz     loc_180023BF6
0x180023b30  xorps   xmm0, xmm0
0x180023b33  movdqu  [rbp+57h+Buf2], xmm0
0x180023b38  mov     [rbp+57h+var_B8], r12
0x180023b3c  movdqu  xmmword ptr [rsp+130h+var_F8], xmm0
0x180023b42  mov     [rsp+130h+var_E8], r12
0x180023b47  lea     rcx, [rbp+57h+Buf2]
0x180023b4b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180023b50  lea     rcx, [rsp+130h+var_F8]
0x180023b55  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180023b5a  lea     r9, [rbp+57h+var_B0]
0x180023b5e  cmp     [rbp+57h+var_98], 7
0x180023b63  cmova   r9, qword ptr [rbp+57h+var_B0]
0x180023b68  mov     rdx, qword ptr [rbp+57h+Buf2+8]
0x180023b6c  mov     rcx, qword ptr [rbp+57h+Buf2]; unsigned __int16 *
0x180023b70  sub     rdx, rcx
0x180023b73  sar     rdx, 1; unsigned __int64
0x180023b76  lea     r8, aNoRecordFoundF; "No record found for eSIM - {%ls}"
0x180023b7d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023b82  mov     rdx, [rsp+130h+var_F8+8]
0x180023b87  mov     rcx, [rsp+130h+var_F8]; unsigned __int16 *
0x180023b8c  sub     rdx, rcx
0x180023b8f  sar     rdx, 1; unsigned __int64
0x180023b92  mov     rax, qword ptr [rbp+57h+Buf2]
0x180023b96  mov     [rsp+130h+var_108], rax
0x180023b9b  mov     dword ptr [rsp+130h+var_110], 28Fh
0x180023ba3  lea     r9, aCesimsettingse_20; "CESimSettingServer::ProcessESimDetails"
0x180023baa  lea     r8, aSDS; "%S(%d):%s"
0x180023bb1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023bb6  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180023bbb  mov     ecx, [rax]
0x180023bbd  cmp     ecx, 3
0x180023bc0  jbe     short loc_180023BE6
0x180023bc2  mov     rcx, [rsp+130h+var_F8]
0x180023bc7  mov     [rsp+130h+var_E0], rcx
0x180023bcc  lea     rcx, [rsp+130h+var_E0]
0x180023bd1  mov     [rsp+130h+var_110], rcx
0x180023bd6  lea     rdx, word_1800758D6
0x180023bdd  mov     rcx, rax
0x180023be0  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180023be5  nop
0x180023be6  lea     rcx, [rsp+130h+var_F8]
0x180023beb  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180023bf0  nop
0x180023bf1  jmp     loc_1800242B1
0x180023bf6  lea     rdx, [rbp+57h+var_B0]
0x180023bfa  mov     rcx, r15
0x180023bfd  call    ?GetAdapterSlotData@CESimSettingServer@@AEAAPEAUAdapterSlotData@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CESimSettingServer::GetAdapterSlotData(std::wstring const &)
0x180023c02  mov     r12, rax
0x180023c05  mov     rbx, [rax+10h]
0x180023c09  mov     [rsp+130h+var_D8], rbx
0x180023c0e  mov     esi, 2
0x180023c13  test    [rdi+4], sil
0x180023c17  jz      loc_180023DC8
0x180023c1d  xorps   xmm0, xmm0
0x180023c20  movdqu  [rbp+57h+Buf2], xmm0
0x180023c25  xor     eax, eax
0x180023c27  mov     [rbp+57h+var_B8], rax
0x180023c2b  movdqu  xmmword ptr [rsp+130h+var_F8], xmm0
0x180023c31  mov     [rsp+130h+var_E8], rax
0x180023c36  lea     rcx, [rbp+57h+Buf2]
0x180023c3a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180023c3f  lea     rcx, [rsp+130h+var_F8]
0x180023c44  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180023c49  mov     rdx, qword ptr [rbp+57h+Buf2+8]
0x180023c4d  mov     rcx, qword ptr [rbp+57h+Buf2]; unsigned __int16 *
0x180023c51  sub     rdx, rcx
0x180023c54  sar     rdx, 1; unsigned __int64
0x180023c57  mov     eax, [rdi+2B0h]
0x180023c5d  mov     dword ptr [rsp+130h+var_110], eax
0x180023c61  mov     r9d, [rdi+2A8h]
0x180023c68  lea     r8, aGotEsimdetailO; "Got ESimDetail operation: %d, subOperat"...
0x180023c6f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023c74  mov     rdx, [rsp+130h+var_F8+8]
  ... truncated ...
```

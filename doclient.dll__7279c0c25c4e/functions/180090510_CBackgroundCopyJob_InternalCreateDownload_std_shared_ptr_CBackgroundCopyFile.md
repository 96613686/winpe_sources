# CBackgroundCopyJob::_InternalCreateDownload(std::shared_ptr<CBackgroundCopyFile> &)

- ea: `0x180090510`
- end: `0x180091ef0`
- name: `?_InternalCreateDownload@CBackgroundCopyJob@@AEAAJAEAV?$shared_ptr@VCBackgroundCopyFile@@@std@@@Z`
- size: `6624`
- prototype: `__int64 __fastcall(CBackgroundCopyJob *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180088958`

## callees

- `0x18000933c`
- `0x1800095a0`
- `0x18000a4fc`
- `0x18000e9a8`
- `0x180014ac4`
- `0x180019b18`
- `0x18001d534`
- `0x18001dfc4`
- `0x18001fe68`
- `0x180084164`
- `0x18008624c`
- `0x18008eb44`
- `0x180090510`
- `0x1800a1ea4`
- `0x1800a9af0`
- `0x1800aa3b0`
- `0x1800ab528`
- `0x1800e8988`
- `0x1800f823c`
- `0x1800f82f0`
- `0x1801087ec`
- `0x180108e50`
- `0x180109290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180090f29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180090f29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180090f61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009105f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180090f61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009105f`

## string_xrefs

- `0x1800905ab`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180090691`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x1800907b1`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18009097a`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180090aa2`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180090bd1`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180090d19`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180090f4d`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x1800910f8`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x1800912c1`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x1800914b3`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x1800916a0`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18009188d`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180091a65`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180091cd5`: `CBackgroundCopyJob::_InternalCreateDownload`
- `0x180091cc8`: `New download: jobId = %s, contentId = %s, Uri = %s, LocalFile = %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CBackgroundCopyJob::_InternalCreateDownload(CBackgroundCopyJob *this, __int64 a2)
{
  char *v3; // rbx
  unsigned int v4; // r14d
  int v5; // eax
  const char *v6; // r9
  volatile signed __int32 *v7; // rbx
  volatile signed __int32 *v8; // rbx
  __int64 result; // rax
  __int64 v10; // r15
  int v11; // eax
  unsigned int v12; // esi
  volatile signed __int32 *v13; // rbx
  volatile signed __int32 *v14; // rbx
  char **v15; // rcx
  int v16; // eax
  unsigned int v17; // esi
  volatile signed __int32 *v18; // rbx
  volatile signed __int32 *v19; // rbx
  __int64 v20; // rax
  volatile signed __int32 *v21; // rbx
  int v22; // eax
  unsigned int v23; // esi
  volatile signed __int32 *v24; // rbx
  volatile signed __int32 *v25; // rbx
  volatile signed __int32 *v26; // rbx
  __int128 *p_Src; // rcx
  volatile signed __int32 *v28; // rbx
  volatile signed __int32 *v29; // rbx
  volatile signed __int32 *v30; // rbx
  int v31; // eax
  unsigned int v32; // esi
  volatile signed __int32 *v33; // rbx
  volatile signed __int32 *v34; // rbx
  volatile signed __int32 *v35; // rbx
  const char *v36; // r8
  errno_t v37; // eax
  unsigned int v38; // esi
  volatile signed __int32 *v39; // rbx
  volatile signed __int32 *v40; // rbx
  volatile signed __int32 *v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rbx
  char *v44; // rax
  size_t v45; // rsi
  __int64 v46; // rcx
  __int128 *v47; // rbx
  char *v48; // rbx
  volatile signed __int32 *v49; // rbx
  volatile signed __int32 *v50; // rbx
  volatile signed __int32 *v51; // rbx
  volatile signed __int32 *v52; // rbx
  __int64 v53; // rax
  __int64 v54; // rsi
  int v55; // eax
  unsigned int v56; // r14d
  volatile signed __int32 *v57; // rsi
  volatile signed __int32 *v58; // rsi
  volatile signed __int32 *v59; // rbx
  volatile signed __int32 *v60; // rbx
  __int64 *v61; // r15
  int v62; // eax
  unsigned int v63; // r14d
  volatile signed __int32 *v64; // rsi
  volatile signed __int32 *v65; // rsi
  volatile signed __int32 *v66; // rsi
  volatile signed __int32 *v67; // rbx
  volatile signed __int32 *v68; // rbx
  int v69; // eax
  CBackgroundCopyFile *v70; // rsi
  int v71; // eax
  unsigned int v72; // r14d
  volatile signed __int32 *v73; // rsi
  volatile signed __int32 *v74; // rsi
  volatile signed __int32 *v75; // rsi
  volatile signed __int32 *v76; // rbx
  volatile signed __int32 *v77; // rbx
  int v78; // eax
  unsigned int v79; // r14d
  volatile signed __int32 *v80; // rsi
  volatile signed __int32 *v81; // rsi
  volatile signed __int32 *v82; // rsi
  volatile signed __int32 *v83; // rbx
  volatile signed __int32 *v84; // rbx
  int v85; // eax
  unsigned int v86; // r14d
  volatile signed __int32 *v87; // rsi
  volatile signed __int32 *v88; // rsi
  volatile signed __int32 *v89; // rsi
  volatile signed __int32 *v90; // rbx
  volatile signed __int32 *v91; // rbx
  int v92; // eax
  unsigned int v93; // esi
  volatile signed __int32 *v94; // rbx
  volatile signed __int32 *v95; // rbx
  volatile signed __int32 *v96; // rbx
  volatile signed __int32 *v97; // rbx
  volatile signed __int32 *v98; // rbx
  volatile signed __int32 *v99; // rbx
  __int64 v100; // rax
  const char *v101; // rsi
  const char *v102; // r14
  const char *v103; // rax
  volatile signed __int32 *v104; // rsi
  volatile signed __int32 *v105; // rsi
  volatile signed __int32 *v106; // rsi
  volatile signed __int32 *v107; // rbx
  volatile signed __int32 *v108; // rbx
  int v109; // [rsp+20h] [rbp-288h]
  int v110; // [rsp+20h] [rbp-288h]
  char v111; // [rsp+40h] [rbp-268h]
  __int128 v112; // [rsp+48h] [rbp-260h] BYREF
  __int128 v113; // [rsp+58h] [rbp-250h] BYREF
  __int128 v114; // [rsp+68h] [rbp-240h] BYREF
  __int128 v115; // [rsp+78h] [rbp-230h] BYREF
  __int64 v116; // [rsp+88h] [rbp-220h]
  _QWORD v117[4]; // [rsp+90h] [rbp-218h] BYREF
  _BYTE v118[40]; // [rsp+B0h] [rbp-1F8h] BYREF
  char *Source[2]; // [rsp+D8h] [rbp-1D0h] BYREF
  unsigned __int64 v120[2]; // [rsp+E8h] [rbp-1C0h]
  __int128 Src; // [rsp+F8h] [rbp-1B0h] BYREF
  __int64 v122; // [rsp+108h] [rbp-1A0h]
  unsigned __int64 v123; // [rsp+110h] [rbp-198h]
  _OWORD v124[2]; // [rsp+118h] [rbp-190h] BYREF
  __int128 v125; // [rsp+138h] [rbp-170h] BYREF
  __int64 v126; // [rsp+148h] [rbp-160h]
  unsigned __int64 v127; // [rsp+150h] [rbp-158h]
  char Size_1[272]; // [rsp+160h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v116 = a2;
  v111 = 0;
  v113 = 0;
  v3 = (char *)this + 16;
  v4 = (unsigned int)CConfigStore::Find((char *)this + 16, 1, &v113) >> 31;
  v112 = 0;
  v5 = CConfigStore::Find(v3, 2, &v112);
  try
  {
    if ( v5 >= 0 )
    {
      v10 = v113;
    }
    else
    {
      if ( (_BYTE)v4 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x795,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)0x80D02200LL,
          v109);
        v7 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
        if ( *((_QWORD *)&v112 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
            if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
          }
        }
        v8 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
        if ( *((_QWORD *)&v113 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
            if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
          }
        }
        return 2161123840LL;
      }
      *(_OWORD *)Source = 0;
      *(__m128i *)v120 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(Source[0]) = 0;
      v10 = v113;
      v11 = CConvert::FromVariantNoThrow<std::string,std::monostate,bool,int,unsigned int,__int64,unsigned __int64,double,std::string>(
              v113,
              Source);
      v12 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x799,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v11,
          v109);
        std::string::~string(Source);
        v13 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
        if ( *((_QWORD *)&v112 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
            if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
          }
        }
        v14 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
        if ( *((_QWORD *)&v113 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
            if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
          }
        }
        return v12;
      }
      StripUrlQueryParams(Source);
      v124[0] = 0;
      v124[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v124[0]) = 0;
      v15 = Source;
      if ( v120[1] > 0xF )
        v15 = (char **)Source[0];
      v16 = Sha1HashAndEncode(v15, v120[0]);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x79C,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v16,
          v109);
        std::string::~string(v124);
        std::string::~string(Source);
        v18 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
        if ( *((_QWORD *)&v112 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
            if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
          }
        }
        v19 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
        if ( *((_QWORD *)&v113 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
            if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
          }
        }
        return v17;
      }
      v20 = std::make_shared<CConfigValue,std::string const &>((__int64)&v115, (__int64)v124);
      std::shared_ptr<_EXCEPTION_RECORD const>::operator=(&v112, v20);
      v21 = (volatile signed __int32 *)*((_QWORD *)&v115 + 1);
      if ( *((_QWORD *)&v115 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
          if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        }
      }
      std::string::~string(v124);
      std::string::~string(Source);
      v3 = (char *)this + 16;
    }
    *((_DWORD *)this + 93) = 0;
    v115 = 0;
    Src = 0;
    v122 = 0;
    v123 = 15;
    LOBYTE(Src) = 0;
    v124[0] = 0;
    if ( (int)CConfigStore::Find(v3, 4, v124) < 0 )
    {
      AcquireSRWLockShared((PSRWLOCK)this + 27);
      if ( !*((_QWORD *)this + 14) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7BC,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)0x80D02018LL,
          v109);
        ReleaseSRWLockShared((PSRWLOCK)this + 27);
        v50 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
        if ( *((_QWORD *)&v124[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
            if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
          }
        }
        std::string::~string(&Src);
        v51 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
        if ( *((_QWORD *)&v112 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
            if ( _InterlockedExchangeAdd(v51 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
          }
        }
        v52 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
        if ( *((_QWORD *)&v113 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
            if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
          }
        }
        return 2161123352LL;
      }
      v53 = *((_QWORD *)this + 15);
      if ( v53 )
        _InterlockedIncrement((volatile signed __int32 *)(v53 + 8));
      *(_QWORD *)&v115 = *((_QWORD *)this + 14);
      v49 = (volatile signed __int32 *)*((_QWORD *)this + 15);
      *((_QWORD *)&v115 + 1) = v49;
      ReleaseSRWLockShared((PSRWLOCK)this + 27);
    }
    else
    {
      v22 = CConvert::FromVariantNoThrow<std::string,std::monostate,bool,int,unsigned int,__int64,unsigned __int64,double,std::string>(
              *(_QWORD *)&v124[0],
              &Src);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7AA,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v22,
          v109);
        v24 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
        if ( *((_QWORD *)&v124[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
            if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
          }
        }
        std::string::~string(&Src);
        v25 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
        if ( *((_QWORD *)&v112 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        v26 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
        if ( *((_QWORD *)&v113 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
            if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
          }
        }
        return v23;
      }
      p_Src = &Src;
      if ( v123 > 0xF )
        p_Src = (__int128 *)Src;
      if ( *((_BYTE *)p_Src + v122 - 1) == 92 )
      {
        if ( (_BYTE)v4 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7AD,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
            (const char *)0x80D02200LL,
            v109);
          v28 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
          if ( *((_QWORD *)&v124[0] + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
              if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
            }
          }
          std::string::~string(&Src);
          v29 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
          if ( *((_QWORD *)&v112 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
              if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
            }
          }
          v30 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
          if ( *((_QWORD *)&v113 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
              if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
            }
          }
          return 2161123840LL;
        }
        *(_OWORD *)Source = 0;
        *(__m128i *)v120 = _mm_load_si128((const __m128i *)&_xmm);
        LOBYTE(Source[0]) = 0;
        v31 = CConvert::FromVariantNoThrow<std::string,std::monostate,bool,int,unsigned int,__int64,unsigned __int64,double,std::string>(
                v10,
                Source);
        v32 = v31;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7AF,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
            (const char *)(unsigned int)v31,
            v109);
          std::string::~string(Source);
          v33 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
          if ( *((_QWORD *)&v124[0] + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
              if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
            }
          }
          std::string::~string(&Src);
          v34 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
          if ( *((_QWORD *)&v112 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
              if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
            }
          }
          v35 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
          if ( *((_QWORD *)&v113 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
              if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
            }
          }
          return v32;
        }
        StripUrlQueryParams(Source);
        v36 = (const char *)Source;
        if ( v120[1] > 0xF )
          v36 = Source[0];
        v37 = strcpy_s(Size_1, 0x104u, v36);
        v38 = v37 != 0 ? 0x8007007A : 0;
        if ( v37 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7B3,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
            (const char *)v38,
            v109);
          std::string::~string(Source);
          v39 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
          if ( *((_QWORD *)&v124[0] + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
              if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
            }
          }
          std::string::~string(&Src);
          v40 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
          if ( *((_QWORD *)&v112 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
              if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
            }
          }
          v41 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
          if ( *((_QWORD *)&v113 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
              if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
            }
          }
          return v38;
        }
        v42 = -1;
        do
          ++v42;
        while ( Size_1[v42] );
        v43 = v42 + 1;
        v44 = strrchr(Size_1, 92);
        if ( v44 || (v44 = strrchr(Size_1, 47)) != 0 )
          memmove(Size_1, v44 + 1, (size_t)&Size_1[v43 - (_QWORD)v44 - 1]);
        v45 = -1;
        do
          ++v45;
        while ( Size_1[v45] );
        v46 = v122;
        if ( v45 > v123 - v122 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
            &Src,
            v45);
        }
        else
        {
          v122 += v45;
          v47 = &Src;
          if ( v123 > 0xF )
            v47 = (__int128 *)Src;
          v48 = (char *)v47 + v46;
          memmove(v48, Size_1, v45);
          v48[v45] = 0;
        }
        std::string::~string(Source);
        v49 = (volatile signed __int32 *)*((_QWORD *)&v115 + 1);
      }
      else
      {
        v49 = (volatile signed __int32 *)*((_QWORD *)&v115 + 1);
      }
    }
    LODWORD(v54) = 0;
    v114 = 0;
    if ( (int)CConfigStore::Find((char *)this + 16, 21, &v114) >= 0 )
    {
      if ( *(_BYTE *)(v114 + 32) != 5 )
        std::_Throw_bad_variant_access();
      v54 = *(_QWORD *)v114;
    }
    *(_OWORD *)Source = 0;
    v125 = 0;
    v126 = 0;
    v127 = 15;
    LOBYTE(v125) = 0;
    if ( v10 )
    {
      v55 = CConvert::FromVariantNoThrow<std::string,std::monostate,bool,int,unsigned int,__int64,unsigned __int64,double,std::string>(
              v10,
              &v125);
      v56 = v55;
      if ( v55 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7CC,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v55,
          v109);
        std::string::~string(&v125);
        v57 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
        if ( *((_QWORD *)&v114 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
            if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
          }
        }
        v58 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
        if ( *((_QWORD *)&v124[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
            if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
          }
        }
        std::string::~string(&Src);
        if ( v49 )
        {
          if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
            if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
          }
        }
        v59 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
        if ( *((_QWORD *)&v112 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
            if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
          }
        }
        v60 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
        if ( *((_QWORD *)&v113 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
            if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
          }
        }
        return v56;
      }
    }
    v61 = (__int64 *)v112;
    if ( *(_BYTE *)(v112 + 32) != 7 )
      std::_Throw_bad_variant_access();
    v62 = CBackgroundCopyJob::_AddFileInternal(
            this,
            (_QWORD *)v112,
            (__int64)&v125,
            (const char *)&Src,
            0,
            0,
            v54,
            (__int64)Source);
    v63 = v62;
    if ( v62 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7CE,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)(unsigned int)v62,
        v110);
      std::string::~string(&v125);
      v64 = (volatile signed __int32 *)Source[1];
      if ( Source[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Source[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v64)(v64);
          if ( _InterlockedExchangeAdd(v64 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 8LL))(v64);
        }
      }
      v65 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
      if ( *((_QWORD *)&v114 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
          if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
        }
      }
      v66 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
      if ( *((_QWORD *)&v124[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
          if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
        }
      }
      std::string::~string(&Src);
      if ( v49 )
      {
        if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
          if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
        }
      }
      v67 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
      if ( *((_QWORD *)&v112 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
          if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
        }
      }
      v68 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
      if ( *((_QWORD *)&v113 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
          if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
        }
      }
      return v63;
    }
    v69 = CConfigStore::Find((char *)this + 16, 18, &v114);
    v70 = (CBackgroundCopyFile *)Source[0];
    if ( v69 >= 0 )
    {
      v71 = CBackgroundCopyFile::SetProperty((CBackgroundCopyFile *)Source[0], 0, (const char **)&v114);
      v72 = v71;
      if ( v71 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7D3,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v71,
          v110);
        std::string::~string(&v125);
        v73 = (volatile signed __int32 *)Source[1];
        if ( Source[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Source[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v73)(v73);
            if ( _InterlockedExchangeAdd(v73 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v73 + 8LL))(v73);
          }
        }
        v74 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
        if ( *((_QWORD *)&v114 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
            if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
          }
        }
        v75 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
        if ( *((_QWORD *)&v124[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
            if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
          }
        }
        std::string::~string(&Src);
        if ( v49 )
        {
          if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
            if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
          }
        }
        v76 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
        if ( *((_QWORD *)&v112 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
            if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
          }
        }
        v77 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
        if ( *((_QWORD *)&v113 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v77)(v77);
            if ( _InterlockedExchangeAdd(v77 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v77 + 8LL))(v77);
          }
        }
        return v72;
      }
    }
    if ( (int)CConfigStore::Find((char *)this + 16, 19, &v114) >= 0 )
    {
      v78 = CBackgroundCopyFile::SetProperty(v70, 1u, (const char **)&v114);
      v79 = v78;
      if ( v78 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7D7,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v78,
          v110);
        std::string::~string(&v125);
        v80 = (volatile signed __int32 *)Source[1];
        if ( Source[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Source[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v80)(v80);
            if ( _InterlockedExchangeAdd(v80 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v80 + 8LL))(v80);
          }
        }
        v81 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
        if ( *((_QWORD *)&v114 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v81)(v81);
            if ( _InterlockedExchangeAdd(v81 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v81 + 8LL))(v81);
          }
        }
        v82 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
        if ( *((_QWORD *)&v124[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
            if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
          }
        }
        std::string::~string(&Src);
        if ( v49 )
        {
          if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
            if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
          }
        }
        v83 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
        if ( *((_QWORD *)&v112 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v83)(v83);
            if ( _InterlockedExchangeAdd(v83 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 8LL))(v83);
          }
        }
        v84 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
        if ( *((_QWORD *)&v113 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v84)(v84);
            if ( _InterlockedExchangeAdd(v84 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v84 + 8LL))(v84);
          }
        }
        return v79;
      }
    }
    if ( (int)CConfigStore::Find((char *)this + 16, 20, &v114) >= 0 )
    {
      v85 = CBackgroundCopyFile::SetProperty(v70, 2u, (const char **)&v114);
      v86 = v85;
      if ( v85 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7DB,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v85,
          v110);
        std::string::~string(&v125);
        v87 = (volatile signed __int32 *)Source[1];
        if ( Source[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Source[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v87)(v87);
            if ( _InterlockedExchangeAdd(v87 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v87 + 8LL))(v87);
          }
        }
        v88 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
        if ( *((_QWORD *)&v114 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v88)(v88);
            if ( _InterlockedExchangeAdd(v88 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v88 + 8LL))(v88);
          }
        }
        v89 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
        if ( *((_QWORD *)&v124[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v89)(v89);
            if ( _InterlockedExchangeAdd(v89 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v89 + 8LL))(v89);
          }
        }
        std::string::~string(&Src);
        if ( v49 )
        {
          if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
            if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
          }
        }
        v90 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
        if ( *((_QWORD *)&v112 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v90)(v90);
            if ( _InterlockedExchangeAdd(v90 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v90 + 8LL))(v90);
          }
        }
        v91 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
        if ( *((_QWORD *)&v113 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v91)(v91);
            if ( _InterlockedExchangeAdd(v91 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v91 + 8LL))(v91);
          }
        }
        return v86;
      }
    }
    if ( (_QWORD)v115 )
    {
      v92 = CBackgroundCopyFile::SetDownloadSinkStreamInterface(v70, &v115);
      v93 = v92;
      if ( v92 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7DF,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v92,
          v110);
        std::string::~string(&v125);
        v94 = (volatile signed __int32 *)Source[1];
        if ( Source[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Source[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v94)(v94);
            if ( _InterlockedExchangeAdd(v94 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v94 + 8LL))(v94);
          }
        }
        v95 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
        if ( *((_QWORD *)&v114 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v95)(v95);
            if ( _InterlockedExchangeAdd(v95 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v95 + 8LL))(v95);
          }
        }
        v96 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
        if ( *((_QWORD *)&v124[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v96)(v96);
            if ( _InterlockedExchangeAdd(v96 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v96 + 8LL))(v96);
          }
        }
        std::string::~string(&Src);
        v97 = (volatile signed __int32 *)*((_QWORD *)&v115 + 1);
        if ( *((_QWORD *)&v115 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v97)(v97);
            if ( _InterlockedExchangeAdd(v97 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v97 + 8LL))(v97);
          }
        }
        v98 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
        if ( *((_QWORD *)&v112 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v98)(v98);
            if ( _InterlockedExchangeAdd(v98 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v98 + 8LL))(v98);
          }
        }
        v99 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
        if ( *((_QWORD *)&v113 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v99)(v99);
            if ( _InterlockedExchangeAdd(v99 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v99 + 8LL))(v99);
          }
        }
        return v93;
      }
      v49 = (volatile signed __int32 *)*((_QWORD *)&v115 + 1);
    }
    if ( v122 )
    {
      v100 = RemovePIIFromFilePath(v117, &Src);
      v101 = (const char *)v100;
      v111 = 1;
      if ( *(_QWORD *)(v100 + 24) > 0xFu )
        v101 = *(const char **)v100;
    }
    else
    {
      v101 = "[none]";
    }
    if ( v126 )
    {
      v102 = (const char *)&v125;
      if ( v127 > 0xF )
        v102 = (const char *)v125;
    }
    else
    {
      v102 = "[none]";
    }
    if ( *((_BYTE *)v61 + 32) != 7 )
      std::_Throw_bad_variant_access();
    if ( (unsigned __int64)v61[3] > 0xF )
      v61 = (__int64 *)*v61;
    v103 = (const char *)CGuidToString::CGuidToString(
                           (CGuidToString *)v118,
                           (const struct _GUID *)(*((_QWORD *)this + 31) + 16LL));
    LogMessage(
      4u,
      "CBackgroundCopyJob::_InternalCreateDownload",
      0x7E7u,
      "New download: jobId = %s, contentId = %s, Uri = %s, LocalFile = %s",
      v103,
      (const char *)v61,
      v102,
      v101);
    if ( (v111 & 1) != 0 )
      std::string::~string(v117);
    std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::operator=(v116, Source);
    std::string::~string(&v125);
    v104 = (volatile signed __int32 *)Source[1];
    if ( Source[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Source[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v104)(v104);
        if ( _InterlockedExchangeAdd(v104 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v104 + 8LL))(v104);
      }
    }
    v105 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
    if ( *((_QWORD *)&v114 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v105)(v105);
        if ( _InterlockedExchangeAdd(v105 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v105 + 8LL))(v105);
      }
    }
    v106 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
    if ( *((_QWORD *)&v124[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v106)(v106);
        if ( _InterlockedExchangeAdd(v106 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v106 + 8LL))(v106);
      }
    }
    std::string::~string(&Src);
    if ( v49 )
    {
      if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
        if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
      }
    }
    v107 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
    if ( *((_QWORD *)&v112 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v107)(v107);
        if ( _InterlockedExchangeAdd(v107 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v107 + 8LL))(v107);
      }
    }
    v108 = (volatile signed __int32 *)*((_QWORD *)&v113 + 1);
    if ( *((_QWORD *)&v113 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v108)(v108);
        if ( _InterlockedExchangeAdd(v108 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v108 + 8LL))(v108);
      }
    }
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7EB,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x180090510  mov     [rsp+arg_10], rbx
0x180090515  mov     [rsp+arg_18], rsi
0x18009051a  push    rdi
0x18009051b  push    r12
0x18009051d  push    r13
0x18009051f  push    r14
0x180090521  push    r15
0x180090523  sub     rsp, 280h
0x18009052a  mov     rax, cs:__security_cookie
0x180090531  xor     rax, rsp
0x180090534  mov     [rsp+2A8h+var_38], rax
0x18009053c  mov     [rsp+2A8h+var_220], rdx
0x180090544  mov     r13, rcx
0x180090547  xor     edi, edi
0x180090549  mov     dword ptr [rsp+2A8h+var_268], edi
0x18009054d  xorps   xmm1, xmm1
0x180090550  movdqu  [rsp+2A8h+var_250], xmm1
0x180090556  lea     rbx, [rcx+10h]
0x18009055a  lea     r8, [rsp+2A8h+var_250]
0x18009055f  lea     edx, [rdi+1]
0x180090562  mov     rcx, rbx
0x180090565  call    ?Find@CConfigStore@@QEBAJHAEAV?$shared_ptr@VCConfigValue@@@std@@@Z; CConfigStore::Find(int,std::shared_ptr<CConfigValue> &)
0x18009056a  mov     r14d, eax
0x18009056d  shr     r14d, 1Fh
0x180090571  xorps   xmm1, xmm1
0x180090574  movdqu  [rsp+2A8h+var_260], xmm1
0x18009057a  lea     r8, [rsp+2A8h+var_260]
0x18009057f  lea     edx, [rdi+2]
0x180090582  mov     rcx, rbx
0x180090585  call    ?Find@CConfigStore@@QEBAJHAEAV?$shared_ptr@VCConfigValue@@@std@@@Z; CConfigStore::Find(int,std::shared_ptr<CConfigValue> &)
0x18009058a  test    eax, eax
0x18009058c  jns     loc_1800908EA
0x180090592  test    r14b, r14b
0x180090595  jz      loc_180090643
0x18009059b  mov     rcx, [rsp+2A8h]; this
0x1800905a3  mov     esi, 80D02200h
0x1800905a8  mov     r9d, esi; char *
0x1800905ab  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800905b2  mov     edx, 795h; void *
0x1800905b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800905bc  nop
0x1800905bd  mov     rbx, qword ptr [rsp+2A8h+var_260+8]
0x1800905c2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800905c6  test    rbx, rbx
0x1800905c9  jz      short loc_1800905FF
0x1800905cb  mov     eax, edi
0x1800905cd  lock xadd [rbx+8], eax
0x1800905d2  add     eax, edi
0x1800905d4  jnz     short loc_1800905FF
0x1800905d6  mov     rax, [rbx]
0x1800905d9  mov     rcx, rbx
0x1800905dc  mov     rax, [rax]
0x1800905df  call    _guard_dispatch_icall
0x1800905e4  mov     eax, edi
0x1800905e6  lock xadd [rbx+0Ch], eax
0x1800905eb  add     eax, edi
0x1800905ed  jnz     short loc_1800905FF
0x1800905ef  mov     rax, [rbx]
0x1800905f2  mov     rcx, rbx
0x1800905f5  mov     rax, [rax+8]
0x1800905f9  call    _guard_dispatch_icall
0x1800905fe  nop
0x1800905ff  mov     rbx, qword ptr [rsp+2A8h+var_250+8]
0x180090604  test    rbx, rbx
0x180090607  jz      short loc_18009063C
0x180090609  mov     eax, edi
0x18009060b  lock xadd [rbx+8], eax
0x180090610  add     eax, edi
0x180090612  jnz     short loc_18009063C
0x180090614  mov     rax, [rbx]
0x180090617  mov     rcx, rbx
0x18009061a  mov     rax, [rax]
0x18009061d  call    _guard_dispatch_icall
0x180090622  mov     edx, edi
0x180090624  lock xadd [rbx+0Ch], edx
0x180090629  add     edx, edi
0x18009062b  jnz     short loc_18009063C
0x18009062d  mov     rdx, [rbx]
0x180090630  mov     rcx, rbx
0x180090633  mov     rax, [rdx+8]
0x180090637  call    _guard_dispatch_icall
0x18009063c  mov     eax, esi
0x18009063e  jmp     loc_180091EB0
0x180090643  xorps   xmm0, xmm0
0x180090646  movups  xmmword ptr [rsp+2A8h+Source], xmm0
0x18009064e  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180090656  movdqu  xmmword ptr [rsp+2A8h+var_1C0], xmm1
0x18009065f  mov     byte ptr [rsp+2A8h+Source], dil
0x180090667  lea     rdx, [rsp+2A8h+Source]
0x18009066f  mov     r15, qword ptr [rsp+2A8h+var_250]
0x180090674  mov     rcx, r15
0x180090677  call    ??$FromVariantNoThrow@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Umonostate@2@_NHI_J_KNV12@@CConvert@@SAJAEBV?$variant@Umonostate@std@@_NHI_J_KNV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; CConvert::FromVariantNoThrow<std::string,std::monostate,bool,int,uint,__int64,unsigned __int64,double,std::string>(std::variant<std::monostate,bool,int,uint,__int64,unsigned __int64,double,std::string> const &,std::string &)
0x18009067c  mov     esi, eax
0x18009067e  test    eax, eax
0x180090680  jns     loc_180090737
0x180090686  mov     rcx, [rsp+2A8h]; this
0x18009068e  mov     r9d, eax; char *
0x180090691  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180090698  mov     edx, 799h; void *
0x18009069d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800906a2  nop
0x1800906a3  lea     rcx, [rsp+2A8h+Source]; void *
0x1800906ab  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800906b0  nop
0x1800906b1  mov     rbx, qword ptr [rsp+2A8h+var_260+8]
0x1800906b6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800906ba  test    rbx, rbx
0x1800906bd  jz      short loc_1800906F3
0x1800906bf  mov     eax, edi
0x1800906c1  lock xadd [rbx+8], eax
0x1800906c6  add     eax, edi
0x1800906c8  jnz     short loc_1800906F3
0x1800906ca  mov     rax, [rbx]
0x1800906cd  mov     rcx, rbx
0x1800906d0  mov     rax, [rax]
0x1800906d3  call    _guard_dispatch_icall
0x1800906d8  mov     eax, edi
0x1800906da  lock xadd [rbx+0Ch], eax
0x1800906df  add     eax, edi
0x1800906e1  jnz     short loc_1800906F3
0x1800906e3  mov     rax, [rbx]
0x1800906e6  mov     rcx, rbx
0x1800906e9  mov     rax, [rax+8]
0x1800906ed  call    _guard_dispatch_icall
0x1800906f2  nop
0x1800906f3  mov     rbx, qword ptr [rsp+2A8h+var_250+8]
0x1800906f8  test    rbx, rbx
0x1800906fb  jz      short loc_180090730
0x1800906fd  mov     eax, edi
0x1800906ff  lock xadd [rbx+8], eax
0x180090704  add     eax, edi
0x180090706  jnz     short loc_180090730
0x180090708  mov     rax, [rbx]
0x18009070b  mov     rcx, rbx
0x18009070e  mov     rax, [rax]
0x180090711  call    _guard_dispatch_icall
0x180090716  mov     eax, edi
0x180090718  lock xadd [rbx+0Ch], eax
0x18009071d  add     eax, edi
0x18009071f  jnz     short loc_180090730
0x180090721  mov     rax, [rbx]
0x180090724  mov     rcx, rbx
0x180090727  mov     rax, [rax+8]
0x18009072b  call    _guard_dispatch_icall
0x180090730  mov     eax, esi
0x180090732  jmp     loc_180091EB0
0x180090737  lea     rcx, [rsp+2A8h+Source]
0x18009073f  call    ?StripUrlQueryParams@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; StripUrlQueryParams(std::string &)
0x180090744  xorps   xmm0, xmm0
0x180090747  movups  [rsp+2A8h+var_190], xmm0
0x18009074f  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180090757  movdqu  [rsp+2A8h+var_180], xmm1
0x180090760  mov     byte ptr [rsp+2A8h+var_190], dil
0x180090768  lea     rcx, [rsp+2A8h+Source]
0x180090770  mov     r12d, 0Fh
0x180090776  cmp     [rsp+2A8h+var_1C0+8], r12
0x18009077e  cmova   rcx, [rsp+2A8h+Source]; void *
0x180090787  lea     r8, [rsp+2A8h+var_190]
0x18009078f  mov     rdx, [rsp+2A8h+var_1C0]; unsigned __int64
0x180090797  call    ?Sha1HashAndEncode@@YAJPEBX_KAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Sha1HashAndEncode(void const *,unsigned __int64,std::string &)
0x18009079c  mov     esi, eax
0x18009079e  test    eax, eax
0x1800907a0  jns     loc_180090865
0x1800907a6  mov     rcx, [rsp+2A8h]; this
0x1800907ae  mov     r9d, eax; char *
0x1800907b1  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800907b8  mov     edx, 79Ch; void *
0x1800907bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800907c2  nop
0x1800907c3  lea     rcx, [rsp+2A8h+var_190]; void *
0x1800907cb  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800907d0  nop
0x1800907d1  lea     rcx, [rsp+2A8h+Source]; void *
0x1800907d9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800907de  nop
0x1800907df  mov     rbx, qword ptr [rsp+2A8h+var_260+8]
0x1800907e4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800907e8  test    rbx, rbx
0x1800907eb  jz      short loc_180090821
0x1800907ed  mov     eax, edi
0x1800907ef  lock xadd [rbx+8], eax
0x1800907f4  add     eax, edi
0x1800907f6  jnz     short loc_180090821
0x1800907f8  mov     rax, [rbx]
0x1800907fb  mov     rcx, rbx
0x1800907fe  mov     rax, [rax]
0x180090801  call    _guard_dispatch_icall
0x180090806  mov     eax, edi
0x180090808  lock xadd [rbx+0Ch], eax
0x18009080d  add     eax, edi
0x18009080f  jnz     short loc_180090821
0x180090811  mov     rax, [rbx]
0x180090814  mov     rcx, rbx
0x180090817  mov     rax, [rax+8]
0x18009081b  call    _guard_dispatch_icall
0x180090820  nop
0x180090821  mov     rbx, qword ptr [rsp+2A8h+var_250+8]
0x180090826  test    rbx, rbx
0x180090829  jz      short loc_18009085E
0x18009082b  mov     eax, edi
0x18009082d  lock xadd [rbx+8], eax
0x180090832  add     eax, edi
0x180090834  jnz     short loc_18009085E
0x180090836  mov     rax, [rbx]
0x180090839  mov     rcx, rbx
0x18009083c  mov     rax, [rax]
0x18009083f  call    _guard_dispatch_icall
0x180090844  mov     eax, edi
0x180090846  lock xadd [rbx+0Ch], eax
0x18009084b  add     eax, edi
0x18009084d  jnz     short loc_18009085E
0x18009084f  mov     rax, [rbx]
0x180090852  mov     rcx, rbx
0x180090855  mov     rax, [rax+8]
0x180090859  call    _guard_dispatch_icall
0x18009085e  mov     eax, esi
0x180090860  jmp     loc_180091EB0
0x180090865  lea     rdx, [rsp+2A8h+var_190]
0x18009086d  lea     rcx, [rsp+2A8h+var_230]
0x180090872  call    ??$make_shared@VCConfigValue@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@YA?AV?$shared_ptr@VCConfigValue@@@0@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::make_shared<CConfigValue,std::string const &>(std::string const &)
0x180090877  mov     rdx, rax
0x18009087a  lea     rcx, [rsp+2A8h+var_260]
0x18009087f  call    ??4?$shared_ptr@$$CBU_EXCEPTION_RECORD@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_EXCEPTION_RECORD const>::operator=(std::shared_ptr<_EXCEPTION_RECORD const> &&)
0x180090884  mov     rbx, qword ptr [rsp+2A8h+var_230+8]
0x18009088c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180090890  test    rbx, rbx
0x180090893  jz      short loc_1800908C9
0x180090895  mov     eax, edi
0x180090897  lock xadd [rbx+8], eax
0x18009089c  add     eax, edi
0x18009089e  jnz     short loc_1800908C9
0x1800908a0  mov     rax, [rbx]
0x1800908a3  mov     rcx, rbx
0x1800908a6  mov     rax, [rax]
0x1800908a9  call    _guard_dispatch_icall
0x1800908ae  mov     eax, edi
0x1800908b0  lock xadd [rbx+0Ch], eax
0x1800908b5  add     eax, edi
0x1800908b7  jnz     short loc_1800908C9
0x1800908b9  mov     rax, [rbx]
0x1800908bc  mov     rcx, rbx
0x1800908bf  mov     rax, [rax+8]
0x1800908c3  call    _guard_dispatch_icall
0x1800908c8  nop
0x1800908c9  lea     rcx, [rsp+2A8h+var_190]; void *
0x1800908d1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800908d6  nop
0x1800908d7  lea     rcx, [rsp+2A8h+Source]; void *
0x1800908df  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800908e4  lea     rbx, [r13+10h]
0x1800908e8  jmp     short loc_1800908F7
0x1800908ea  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800908ee  lea     r12d, [rdi+10h]
0x1800908f2  mov     r15, qword ptr [rsp+2A8h+var_250]
0x1800908f7  xor     esi, esi
0x1800908f9  mov     [r13+174h], esi
0x180090900  xorps   xmm0, xmm0
0x180090903  xorps   xmm1, xmm1
0x180090906  movdqu  [rsp+2A8h+var_230], xmm1
0x18009090c  movups  [rsp+2A8h+Src], xmm0
0x180090914  mov     [rsp+2A8h+var_1A0], rsi
0x18009091c  mov     [rsp+2A8h+var_198], r12
0x180090924  mov     byte ptr [rsp+2A8h+Src], sil
0x18009092c  movdqu  [rsp+2A8h+var_190], xmm1
0x180090935  lea     r8, [rsp+2A8h+var_190]
0x18009093d  lea     edx, [rsi+4]
0x180090940  mov     rcx, rbx
0x180090943  call    ?Find@CConfigStore@@QEBAJHAEAV?$shared_ptr@VCConfigValue@@@std@@@Z; CConfigStore::Find(int,std::shared_ptr<CConfigValue> &)
0x180090948  test    eax, eax
0x18009094a  js      loc_180090F1F
0x180090950  lea     rdx, [rsp+2A8h+Src]
0x180090958  mov     rcx, qword ptr [rsp+2A8h+var_190]
0x180090960  call    ??$FromVariantNoThrow@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Umonostate@2@_NHI_J_KNV12@@CConvert@@SAJAEBV?$variant@Umonostate@std@@_NHI_J_KNV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; CConvert::FromVariantNoThrow<std::string,std::monostate,bool,int,uint,__int64,unsigned __int64,double,std::string>(std::variant<std::monostate,bool,int,uint,__int64,unsigned __int64,double,std::string> const &,std::string &)
0x180090965  mov     esi, eax
0x180090967  test    eax, eax
0x180090969  jns     loc_180090A5D
0x18009096f  mov     rcx, [rsp+2A8h]; this
0x180090977  mov     r9d, eax; char *
0x18009097a  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180090981  mov     edx, 7AAh; void *
0x180090986  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009098b  nop
0x18009098c  mov     rbx, qword ptr [rsp+2A8h+var_190+8]
0x180090994  test    rbx, rbx
0x180090997  jz      short loc_1800909CD
0x180090999  mov     eax, edi
0x18009099b  lock xadd [rbx+8], eax
0x1800909a0  add     eax, edi
0x1800909a2  jnz     short loc_1800909CD
0x1800909a4  mov     rax, [rbx]
0x1800909a7  mov     rcx, rbx
0x1800909aa  mov     rax, [rax]
0x1800909ad  call    _guard_dispatch_icall
0x1800909b2  mov     eax, edi
0x1800909b4  lock xadd [rbx+0Ch], eax
0x1800909b9  add     eax, edi
0x1800909bb  jnz     short loc_1800909CD
0x1800909bd  mov     rax, [rbx]
0x1800909c0  mov     rcx, rbx
0x1800909c3  mov     rax, [rax+8]
  ... truncated ...
```

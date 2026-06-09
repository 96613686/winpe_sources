# Microsoft::Basix::Dct::SmilesV3::Summary::Report(void)

- ea: `0x18027a08c`
- end: `0x18027b38f`
- name: `?Report@Summary@SmilesV3@Dct@Basix@Microsoft@@QEAAXXZ`
- size: `4867`
- prototype: `void __fastcall(Microsoft::Basix::Dct::SmilesV3::Summary *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18025f410`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x18001ae64`
- `0x18001db78`
- `0x180024760`
- `0x18003c308`
- `0x1800c3524`
- `0x1800c3bc8`
- `0x1800f30dc`
- `0x1801171b8`
- `0x18024fe80`
- `0x180250028`
- `0x18025245c`
- `0x18027a08c`
- `0x18027f6f8`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x18027a738`: `numActiveLinkAtClose`
- `0x18027a804`: `maxNumLinks`
- `0x18027a888`: `LinkInfo`
- `0x18027a9e1`: `ReportSummary:LinkInfo: maxNumLinks=%d, numActiveLinkAtClose=%d`
- `0x18027ab05`: `Summary:final UpdateDoR: currentDoR=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=124
void __fastcall Microsoft::Basix::Dct::SmilesV3::Summary::Report(
        Microsoft::Basix::Dct::SmilesV3::Summary *this,
        __int64 a2,
        double a3,
        double a4)
{
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  volatile signed __int32 *v20; // rbx
  __int128 v21; // xmm6
  int v22; // r9d
  volatile signed __int32 *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  volatile signed __int32 *v32; // rbx
  int v33; // r9d
  int v34; // ebx
  int v35; // edi
  volatile signed __int32 *v36; // rbx
  __int64 v37; // rdi
  __int64 v38; // rbx
  __int64 v39; // rax
  unsigned int v40; // ebx
  volatile signed __int32 *v41; // rbx
  __int64 v42; // rcx
  unsigned int v43; // r14d
  int v44; // r15d
  int v45; // r9d
  volatile signed __int32 *v46; // rbx
  double v47; // xmm6_8
  __int64 v48; // rbx
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // rbx
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rdx
  __int64 v65; // rdx
  volatile signed __int32 *v66; // rbx
  int v67; // r9d
  int v68; // ebx
  int v69; // r9d
  volatile signed __int32 *v70; // rbx
  double Str; // [rsp+20h] [rbp-E0h]
  double Str_8; // [rsp+28h] [rbp-D8h]
  char v73; // [rsp+50h] [rbp-B0h]
  __int128 v74; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v75; // [rsp+68h] [rbp-98h]
  __int64 *v76; // [rsp+78h] [rbp-88h] BYREF
  __int64 v77[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v78; // [rsp+90h] [rbp-70h]
  __int128 v79; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v80; // [rsp+B0h] [rbp-50h]
  __int128 v81; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v82; // [rsp+D0h] [rbp-30h]
  __int128 v83; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v84; // [rsp+F0h] [rbp-10h]
  __int128 v85; // [rsp+100h] [rbp+0h] BYREF
  __int128 v86; // [rsp+110h] [rbp+10h]
  __int128 v87; // [rsp+120h] [rbp+20h] BYREF
  __int128 v88; // [rsp+130h] [rbp+30h]
  __int64 *v89; // [rsp+140h] [rbp+40h]
  __int64 *v90; // [rsp+148h] [rbp+48h]
  __int64 v91[2]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v92; // [rsp+160h] [rbp+60h]
  __int64 v93[2]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v94; // [rsp+180h] [rbp+80h]
  __int128 v95; // [rsp+190h] [rbp+90h] BYREF
  __int128 v96; // [rsp+1A0h] [rbp+A0h]
  __int128 v97; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v98; // [rsp+1C0h] [rbp+C0h]
  __int64 v99[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v100[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v101[4]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v102[32]; // [rsp+230h] [rbp+130h] BYREF
  __int64 v103[4]; // [rsp+250h] [rbp+150h] BYREF
  _OWORD v104[2]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v105[32]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v106[32]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v107[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v108[32]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v109[32]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v110[32]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v111[32]; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v112[32]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v113[32]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v114[32]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v115[32]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v116[32]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _BYTE v117[32]; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v118[32]; // [rsp+430h] [rbp+330h] BYREF
  int v119[4]; // [rsp+450h] [rbp+350h] BYREF
  int v120[4]; // [rsp+470h] [rbp+370h] BYREF
  __int128 v121; // [rsp+480h] [rbp+380h]

  if ( *((_QWORD *)this + 3) )
  {
    *(_OWORD *)v119 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v119);
    if ( *(_QWORD *)v119 && *(_BYTE *)(*(_QWORD *)v119 + 128LL) )
    {
      _mm_lfence();
      v89 = v77;
      v5 = std::to_string(v107);
      v74 = 0;
      v75 = 0;
      std::string::_Construct<1,char const *>(&v74, ":", 1);
      v87 = 0;
      v88 = 0;
      std::string::_Construct<1,char const *>(&v87, "\"", 1);
      v85 = 0;
      v86 = 0;
      std::string::_Construct<1,char const *>(&v85, "\"", 1);
      v6 = std::operator+<char>(v108, &v85, "MaxDelay");
      LOBYTE(v7) = v73;
      std::string::string(v101, v7, v6, &v87);
      LOBYTE(v8) = v73;
      std::string::string(v100, v8, v101, &v74);
      LOBYTE(v9) = v73;
      std::string::string(v77, v9, v100, v5);
      v90 = v93;
      v10 = std::to_string(v109);
      v83 = 0;
      v84 = 0;
      std::string::_Construct<1,char const *>(&v83, ":", 1);
      v81 = 0;
      v82 = 0;
      std::string::_Construct<1,char const *>(&v81, "\"", 1);
      v79 = 0;
      v80 = 0;
      std::string::_Construct<1,char const *>(&v79, "\"", 1);
      v11 = std::operator+<char>(v110, &v79, "MinDelay");
      LOBYTE(v12) = v73;
      std::string::string(v99, v12, v11, &v81);
      LOBYTE(v13) = v73;
      std::string::string(v103, v13, v99, &v83);
      LOBYTE(v14) = v73;
      std::string::string(v93, v14, v103, v10);
      v15 = std::to_string(v105);
      v97 = 0;
      v98 = 0;
      std::string::_Construct<1,char const *>(&v97, ":", 1);
      v95 = 0;
      v96 = 0;
      std::string::_Construct<1,char const *>(&v95, "\"", 1);
      *(_OWORD *)v120 = 0;
      v121 = 0;
      std::string::_Construct<1,char const *>(v120, "\"", 1);
      v16 = std::operator+<char>(v106, v120, "AveDelay");
      LOBYTE(v17) = v73;
      std::string::string(v102, v17, v16, &v95);
      LOBYTE(v18) = v73;
      std::string::string(v104, v18, v102, &v97);
      LOBYTE(v19) = v73;
      std::string::string(v91, v19, v104, v15);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(
        (int)v119,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "ReportSummary",
        "DelayInfo",
        (__int64)v91,
        (__int64)v93,
        (__int64)v77);
      std::string::_Tidy_deallocate(v104);
      std::string::_Tidy_deallocate(v102);
      std::string::_Tidy_deallocate(v106);
      std::string::_Tidy_deallocate(v120);
      std::string::_Tidy_deallocate(&v95);
      std::string::_Tidy_deallocate(&v97);
      std::string::_Tidy_deallocate(v105);
      std::string::_Tidy_deallocate(v103);
      std::string::_Tidy_deallocate(v99);
      std::string::_Tidy_deallocate(v110);
      std::string::_Tidy_deallocate(&v79);
      std::string::_Tidy_deallocate(&v81);
      std::string::_Tidy_deallocate(&v83);
      std::string::_Tidy_deallocate(v109);
      std::string::_Tidy_deallocate(v100);
      std::string::_Tidy_deallocate(v101);
      std::string::_Tidy_deallocate(v108);
      std::string::_Tidy_deallocate(&v85);
      std::string::_Tidy_deallocate(&v87);
      std::string::_Tidy_deallocate(&v74);
      std::string::_Tidy_deallocate(v107);
    }
    v20 = *(volatile signed __int32 **)&v119[2];
    if ( *(_QWORD *)&v119[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v119[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    *(_OWORD *)v119 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v119);
    if ( *(_QWORD *)v119 && *(_BYTE *)(*(_QWORD *)v119 + 128LL) )
    {
      _mm_lfence();
      v21 = *(_OWORD *)((char *)this + 8);
      v74 = 0;
      v75 = 0;
      std::string::_Construct<1,char const *>(
        &v74,
        "ReportSummary:DelayInfo: AveDelay=%f, minDelay=%f, maxDelay=%f",
        a3,
        a4,
        Str);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,double,double,double>(
        (unsigned int)v119,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v74,
        v22,
        v21,
        SBYTE8(v21));
      std::string::_Tidy_deallocate(&v74);
    }
    v23 = *(volatile signed __int32 **)&v119[2];
    if ( *(_QWORD *)&v119[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v119[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
  }
  *(_OWORD *)v119 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v119);
  if ( *(_QWORD *)v119 && *(_BYTE *)(*(_QWORD *)v119 + 128LL) )
  {
    v76 = v101;
    std::_Integral_to_string<char,unsigned int>(v91, *((unsigned int *)this + 10));
    v79 = 0;
    v80 = 0;
    std::string::_Construct<1,char const *>(&v79, ":", 1);
    v81 = 0;
    v82 = 0;
    std::string::_Construct<1,char const *>(&v81, "\"", 1);
    v83 = 0;
    v84 = 0;
    std::string::_Construct<1,char const *>(&v83, "\"", 1);
    v24 = std::operator+<char>(v105, &v83, "numActiveLinkAtClose");
    LOBYTE(v25) = v73;
    std::string::string(v93, v25, v24, &v81);
    LOBYTE(v26) = v73;
    std::string::string(v77, v26, v93, &v79);
    LOBYTE(v27) = v73;
    std::string::string(v101, v27, v77, v91);
    std::_Integral_to_string<char,unsigned int>(v102, *((unsigned int *)this + 8));
    v85 = 0;
    v86 = 0;
    std::string::_Construct<1,char const *>(&v85, ":", 1);
    v87 = 0;
    v88 = 0;
    std::string::_Construct<1,char const *>(&v87, "\"", 1);
    v74 = 0;
    v75 = 0;
    std::string::_Construct<1,char const *>(&v74, "\"", 1);
    v28 = std::operator+<char>(v106, &v74, "maxNumLinks");
    LOBYTE(v29) = v73;
    std::string::string(v103, v29, v28, &v87);
    LOBYTE(v30) = v73;
    std::string::string(v99, v30, v103, &v85);
    LOBYTE(v31) = v73;
    std::string::string(v100, v31, v99, v102);
    Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string>(
      (int)v119,
      (int)"RD_CHECKPOINT",
      0,
      (int)"Smiles",
      "ReportSummary",
      "LinkInfo",
      (__int64)v100,
      (__int64)v101);
    std::string::_Tidy_deallocate(v99);
    std::string::_Tidy_deallocate(v103);
    std::string::_Tidy_deallocate(v106);
    std::string::_Tidy_deallocate(&v74);
    std::string::_Tidy_deallocate(&v87);
    std::string::_Tidy_deallocate(&v85);
    std::string::_Tidy_deallocate(v102);
    std::string::_Tidy_deallocate(v77);
    std::string::_Tidy_deallocate(v93);
    std::string::_Tidy_deallocate(v105);
    std::string::_Tidy_deallocate(&v83);
    std::string::_Tidy_deallocate(&v81);
    std::string::_Tidy_deallocate(&v79);
    std::string::_Tidy_deallocate(v91);
  }
  v32 = *(volatile signed __int32 **)&v119[2];
  if ( *(_QWORD *)&v119[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v119[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
      if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
    }
  }
  *(_OWORD *)v119 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v119);
  if ( *(_QWORD *)v119 && *(_BYTE *)(*(_QWORD *)v119 + 128LL) )
  {
    v34 = *((_DWORD *)this + 10);
    v35 = *((_DWORD *)this + 8);
    v74 = 0;
    v75 = 0;
    std::string::_Construct<1,char const *>(
      &v74,
      "ReportSummary:LinkInfo: maxNumLinks=%d, numActiveLinkAtClose=%d",
      63,
      v33);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int>(
      (unsigned int)v119,
      (unsigned int)"BASIX_DCT",
      (unsigned int)&v74,
      v35,
      v34);
    std::string::_Tidy_deallocate(&v74);
  }
  v36 = *(volatile signed __int32 **)&v119[2];
  if ( *(_QWORD *)&v119[2] )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v119[2] + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
      if ( !_InterlockedDecrement(v36 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
    }
  }
  if ( *((_DWORD *)this + 30) )
  {
    v37 = *(_QWORD *)std::chrono::steady_clock::now(&v76) / 1000000LL;
    v38 = v37 - *((_QWORD *)this + 13);
    v39 = std::map<unsigned int,unsigned int>::_Try_emplace<unsigned int const &,>(
            (char *)this + 128,
            v120,
            (char *)this + 96);
    *(_DWORD *)(*(_QWORD *)v39 + 32LL) += v38;
    *(_OWORD *)v119 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v119);
    if ( *(_QWORD *)v119 && *(_BYTE *)(*(_QWORD *)v119 + 128LL) )
    {
      v40 = *((_DWORD *)this + 24);
      v74 = 0;
      v75 = 0;
      std::string::_Construct<1,char const *>(&v74, "Summary:final UpdateDoR: currentDoR=%d", 38);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int>(
        v119,
        "BASIX_DCT",
        &v74,
        v40);
      std::string::_Tidy_deallocate(&v74);
    }
    v41 = *(volatile signed __int32 **)&v119[2];
    if ( *(_QWORD *)&v119[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v119[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
        if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
      }
    }
    v42 = **((_QWORD **)this + 16);
    v43 = *(_DWORD *)(v42 + 28);
    v44 = *(_DWORD *)(v42 + 32);
    *(_OWORD *)v119 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v119);
    if ( *(_QWORD *)v119 && *(_BYTE *)(*(_QWORD *)v119 + 128LL) )
    {
      v74 = 0;
      v75 = 0;
      std::string::_Construct<1,char const *>(&v74, "ReportSummary:minDoR=%d, duration=%d", 36, v45);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int>(
        (unsigned int)v119,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v74,
        v43,
        v44);
      std::string::_Tidy_deallocate(&v74);
    }
    v46 = *(volatile signed __int32 **)&v119[2];
    if ( *(_QWORD *)&v119[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v119[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
        if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
      }
    }
    v47 = (double)v44 / (double)((int)v37 - *((_DWORD *)this + 28)) * 100.0;
    *(_OWORD *)v120 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v120);
    if ( *(_QWORD *)v120 && *(_BYTE *)(*(_QWORD *)v120 + 128LL) )
    {
      v76 = v101;
      v48 = std::to_string(v118);
      *(_OWORD *)v77 = 0;
      v78 = 0;
      std::string::_Construct<1,char const *>(v77, ":", 1);
      *(_OWORD *)v93 = 0;
      v94 = 0;
      std::string::_Construct<1,char const *>(v93, "\"", 1);
      *(_OWORD *)v91 = 0;
      v92 = 0;
      std::string::_Construct<1,char const *>(v91, "\"", 1);
      v49 = std::operator+<char>(v117, v91, "minDoRPercentage");
      LOBYTE(v50) = v73;
      std::string::string(v106, v50, v49, v93);
      LOBYTE(v51) = v73;
      std::string::string(v105, v51, v106, v77);
      LOBYTE(v52) = v73;
      std::string::string(v101, v52, v105, v48);
      v90 = v100;
      std::_Integral_to_string<char,unsigned int>(v110, v43);
      memset(v104, 0, sizeof(v104));
      std::string::_Construct<1,char const *>(v104, ":", 1);
      v95 = 0;
      v96 = 0;
      std::string::_Construct<1,char const *>(&v95, "\"", 1);
      v97 = 0;
      v98 = 0;
      std::string::_Construct<1,char const *>(&v97, "\"", 1);
      v53 = std::operator+<char>(v116, &v97, "minDoR");
      LOBYTE(v54) = v73;
      std::string::string(v109, v54, v53, &v95);
      LOBYTE(v55) = v73;
      std::string::string(v108, v55, v109, v104);
      LOBYTE(v56) = v73;
      std::string::string(v100, v56, v108, v110);
      v89 = v99;
      std::_Integral_to_string<char,unsigned int>(v107, *((unsigned int *)this + 36));
      v79 = 0;
      v80 = 0;
      std::string::_Construct<1,char const *>(&v79, ":", 1);
      v81 = 0;
      v82 = 0;
      std::string::_Construct<1,char const *>(&v81, "\"", 1);
      v83 = 0;
      v84 = 0;
      std::string::_Construct<1,char const *>(&v83, "\"", 1);
      v57 = std::operator+<char>(v115, &v83, "DoRAtClose");
      LOBYTE(v58) = v73;
      std::string::string(v112, v58, v57, &v81);
      LOBYTE(v59) = v73;
      std::string::string(v111, v59, v112, &v79);
      LOBYTE(v60) = v73;
      std::string::string(v99, v60, v111, v107);
      v61 = std::to_string(v114);
      v85 = 0;
      v86 = 0;
      std::string::_Construct<1,char const *>(&v85, ":", 1);
      v87 = 0;
      v88 = 0;
      std::string::_Construct<1,char const *>(&v87, "\"", 1);
      v74 = 0;
      v75 = 0;
      std::string::_Construct<1,char const *>(&v74, "\"", 1);
      v62 = std::operator+<char>(v113, &v74, "aveDoR");
      LOBYTE(v63) = v73;
      std::string::string(v119, v63, v62, &v87);
      LOBYTE(v64) = v73;
      std::string::string(v102, v64, v119, &v85);
      LOBYTE(v65) = v73;
      std::string::string(v103, v65, v102, v61);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string>(
        (int)v120,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "ReportSummary",
        "DoRInfo",
        (__int64)v103,
        (__int64)v99,
        (__int64)v100,
        (__int64)v101);
      std::string::_Tidy_deallocate(v102);
      std::string::_Tidy_deallocate(v119);
      std::string::_Tidy_deallocate(v113);
      std::string::_Tidy_deallocate(&v74);
      std::string::_Tidy_deallocate(&v87);
      std::string::_Tidy_deallocate(&v85);
      std::string::_Tidy_deallocate(v114);
      std::string::_Tidy_deallocate(v111);
      std::string::_Tidy_deallocate(v112);
      std::string::_Tidy_deallocate(v115);
      std::string::_Tidy_deallocate(&v83);
      std::string::_Tidy_deallocate(&v81);
      std::string::_Tidy_deallocate(&v79);
      std::string::_Tidy_deallocate(v107);
      std::string::_Tidy_deallocate(v108);
      std::string::_Tidy_deallocate(v109);
      std::string::_Tidy_deallocate(v116);
      std::string::_Tidy_deallocate(&v97);
      std::string::_Tidy_deallocate(&v95);
      std::string::_Tidy_deallocate(v104);
      std::string::_Tidy_deallocate(v110);
      std::string::_Tidy_deallocate(v105);
      std::string::_Tidy_deallocate(v106);
      std::string::_Tidy_deallocate(v117);
      std::string::_Tidy_deallocate(v91);
      std::string::_Tidy_deallocate(v93);
      std::string::_Tidy_deallocate(v77);
      std::string::_Tidy_deallocate(v118);
    }
    v66 = *(volatile signed __int32 **)&v120[2];
    if ( *(_QWORD *)&v120[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v120[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
        if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
      }
    }
    *(_OWORD *)v120 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v120);
    if ( *(_QWORD *)v120 && *(_BYTE *)(*(_QWORD *)v120 + 128LL) )
    {
      v68 = *((_DWORD *)this + 36);
      *(_OWORD *)v77 = 0;
      v78 = 0;
      std::string::_Construct<1,char const *>(
        v77,
        "ReportSummary:DoRInfo: aveDoR=%f, DoRAtClose=%d, minDoR=%d, minDoRPercentage=%f",
        a3,
        v67,
        LODWORD(Str),
        Str_8);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,double,unsigned int,unsigned int,double>(
        (unsigned int)v120,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v77,
        v69,
        v68,
        v43,
        SLOBYTE(v47));
      std::string::_Tidy_deallocate(v77);
    }
    v70 = *(volatile signed __int32 **)&v120[2];
    if ( *(_QWORD *)&v120[2] && !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v120[2] + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v70)(v70);
      if ( !_InterlockedDecrement(v70 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v70 + 8LL))(v70);
    }
  }
}

```

## disassembly

```asm
0x18027a08c  mov     [rsp-8+arg_8], rbx
0x18027a091  mov     [rsp-8+arg_10], rsi
0x18027a096  push    rbp
0x18027a097  push    rdi
0x18027a098  push    r12
0x18027a09a  push    r14
0x18027a09c  push    r15
0x18027a09e  lea     rbp, [rsp-3D0h]
0x18027a0a6  mov     eax, 4D0h
0x18027a0ab  call    _alloca_probe
0x18027a0b0  sub     rsp, rax
0x18027a0b3  movaps  [rsp+4F0h+var_30], xmm6
0x18027a0bb  movaps  [rsp+4F0h+var_40], xmm7
0x18027a0c3  movaps  [rsp+4F0h+var_50], xmm8
0x18027a0cc  mov     rax, cs:__security_cookie
0x18027a0d3  xor     rax, rsp
0x18027a0d6  mov     [rbp+3F0h+var_60], rax
0x18027a0dd  mov     rsi, rcx
0x18027a0e0  mov     rcx, [rcx+18h]
0x18027a0e4  mov     edi, 1
0x18027a0e9  lea     r15, asc_1803D71C4; ":"
0x18027a0f0  lea     r14, asc_1803D71C8; "\""
0x18027a0f7  lea     rbx, aReportsummary; "ReportSummary"
0x18027a0fe  or      r12d, 0FFFFFFFFh
0x18027a102  test    rcx, rcx
0x18027a105  jz      loc_18027A68E
0x18027a10b  xorps   xmm0, xmm0
0x18027a10e  js      short loc_18027A117
0x18027a110  cvtsi2sd xmm0, rcx
0x18027a115  jmp     short loc_18027A12C
0x18027a117  mov     rax, rcx
0x18027a11a  shr     rax, 1
0x18027a11d  and     rcx, rdi
0x18027a120  or      rax, rcx
0x18027a123  cvtsi2sd xmm0, rax
0x18027a128  addsd   xmm0, xmm0
0x18027a12c  movsd   xmm8, qword ptr [rsi]
0x18027a131  divsd   xmm8, xmm0
0x18027a136  xorps   xmm0, xmm0
0x18027a139  movups  xmmword ptr [rbp+3F0h+var_A0], xmm0
0x18027a140  lea     rcx, [rbp+3F0h+var_A0]
0x18027a147  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x18027a14c  nop
0x18027a14d  mov     rax, qword ptr [rbp+3F0h+var_A0]
0x18027a154  test    rax, rax
0x18027a157  jz      loc_18027A574
0x18027a15d  cmp     byte ptr [rax+80h], 0
0x18027a164  jz      loc_18027A574
0x18027a16a  lfence
0x18027a16d  lea     rax, [rbp+3F0h+var_470]
0x18027a171  mov     [rbp+3F0h+var_3B0], rax
0x18027a175  movsd   xmm1, qword ptr [rsi+10h]
0x18027a17a  lea     rcx, [rbp+3F0h+var_220]
0x18027a181  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@N@Z; std::to_string(double)
0x18027a186  mov     rbx, rax
0x18027a189  xorps   xmm0, xmm0
0x18027a18c  movups  [rsp+4F0h+var_498], xmm0
0x18027a191  xorps   xmm1, xmm1
0x18027a194  movdqu  [rsp+4F0h+var_488], xmm1
0x18027a19a  mov     r8, rdi
0x18027a19d  mov     rdx, r15
0x18027a1a0  lea     rcx, [rsp+4F0h+var_498]
0x18027a1a5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027a1aa  nop
0x18027a1ab  xorps   xmm0, xmm0
0x18027a1ae  movups  [rbp+3F0h+var_3D0], xmm0
0x18027a1b2  xorps   xmm1, xmm1
0x18027a1b5  movdqu  [rbp+3F0h+var_3C0], xmm1
0x18027a1ba  mov     r8, rdi
0x18027a1bd  mov     rdx, r14
0x18027a1c0  lea     rcx, [rbp+3F0h+var_3D0]
0x18027a1c4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027a1c9  nop
0x18027a1ca  xorps   xmm0, xmm0
0x18027a1cd  movups  [rbp+3F0h+var_3F0], xmm0
0x18027a1d1  xorps   xmm1, xmm1
0x18027a1d4  movdqu  [rbp+3F0h+var_3E0], xmm1
0x18027a1d9  mov     r8, rdi
0x18027a1dc  mov     rdx, r14
0x18027a1df  lea     rcx, [rbp+3F0h+var_3F0]
0x18027a1e3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027a1e8  nop
0x18027a1e9  lea     r8, aMaxdelay; "MaxDelay"
0x18027a1f0  lea     rdx, [rbp+3F0h+var_3F0]
0x18027a1f4  lea     rcx, [rbp+3F0h+var_200]
0x18027a1fb  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18027a200  nop
0x18027a201  lea     r9, [rbp+3F0h+var_3D0]
0x18027a205  mov     r8, rax
0x18027a208  mov     dl, [rsp+4F0h+var_4A0]
0x18027a20c  lea     rcx, [rbp+3F0h+var_2E0]
0x18027a213  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18027a218  nop
0x18027a219  lea     r9, [rsp+4F0h+var_498]
0x18027a21e  lea     r8, [rbp+3F0h+var_2E0]
0x18027a225  mov     dl, [rsp+4F0h+var_4A0]
0x18027a229  lea     rcx, [rbp+3F0h+var_300]
0x18027a230  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18027a235  nop
0x18027a236  mov     r9, rbx
0x18027a239  lea     r8, [rbp+3F0h+var_300]
0x18027a240  mov     dl, [rsp+4F0h+var_4A0]
0x18027a244  lea     rcx, [rbp+3F0h+var_470]
0x18027a248  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18027a24d  nop
0x18027a24e  lea     rax, [rbp+3F0h+var_380]
0x18027a252  mov     [rbp+3F0h+var_3A8], rax
0x18027a256  movsd   xmm1, qword ptr [rsi+8]
0x18027a25b  lea     rcx, [rbp+3F0h+var_1E0]
0x18027a262  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@N@Z; std::to_string(double)
0x18027a267  mov     rbx, rax
0x18027a26a  xorps   xmm0, xmm0
0x18027a26d  movups  [rbp+3F0h+var_410], xmm0
0x18027a271  xorps   xmm1, xmm1
0x18027a274  movdqu  [rbp+3F0h+var_400], xmm1
0x18027a279  mov     r8, rdi
0x18027a27c  mov     rdx, r15
0x18027a27f  lea     rcx, [rbp+3F0h+var_410]
0x18027a283  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027a288  nop
0x18027a289  xorps   xmm0, xmm0
0x18027a28c  movups  [rbp+3F0h+var_430], xmm0
0x18027a290  xorps   xmm1, xmm1
0x18027a293  movdqu  [rbp+3F0h+var_420], xmm1
0x18027a298  mov     r8, rdi
0x18027a29b  mov     rdx, r14
0x18027a29e  lea     rcx, [rbp+3F0h+var_430]
0x18027a2a2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027a2a7  nop
0x18027a2a8  xorps   xmm0, xmm0
0x18027a2ab  movups  [rbp+3F0h+var_450], xmm0
0x18027a2af  xorps   xmm1, xmm1
0x18027a2b2  movdqu  [rbp+3F0h+var_440], xmm1
0x18027a2b7  mov     r8, rdi
0x18027a2ba  mov     rdx, r14
0x18027a2bd  lea     rcx, [rbp+3F0h+var_450]
0x18027a2c1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027a2c6  nop
0x18027a2c7  lea     r8, aMindelay; "MinDelay"
0x18027a2ce  lea     rdx, [rbp+3F0h+var_450]
0x18027a2d2  lea     rcx, [rbp+3F0h+var_1C0]
0x18027a2d9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18027a2de  nop
0x18027a2df  lea     r9, [rbp+3F0h+var_430]
0x18027a2e3  mov     r8, rax
0x18027a2e6  mov     dl, [rsp+4F0h+var_4A0]
0x18027a2ea  lea     rcx, [rbp+3F0h+var_320]
0x18027a2f1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18027a2f6  nop
0x18027a2f7  lea     r9, [rbp+3F0h+var_410]
0x18027a2fb  lea     r8, [rbp+3F0h+var_320]
0x18027a302  mov     dl, [rsp+4F0h+var_4A0]
0x18027a306  lea     rcx, [rbp+3F0h+var_2A0]
0x18027a30d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18027a312  nop
0x18027a313  mov     r9, rbx
0x18027a316  lea     r8, [rbp+3F0h+var_2A0]
0x18027a31d  mov     dl, [rsp+4F0h+var_4A0]
0x18027a321  lea     rcx, [rbp+3F0h+var_380]
0x18027a325  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18027a32a  nop
0x18027a32b  movaps  xmm1, xmm8
0x18027a32f  lea     rcx, [rbp+3F0h+var_260]
0x18027a336  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@N@Z; std::to_string(double)
0x18027a33b  mov     rbx, rax
0x18027a33e  xorps   xmm0, xmm0
0x18027a341  movups  [rbp+3F0h+var_340], xmm0
0x18027a348  xorps   xmm1, xmm1
0x18027a34b  movdqu  [rbp+3F0h+var_330], xmm1
0x18027a353  mov     r8, rdi
0x18027a356  mov     rdx, r15
0x18027a359  lea     rcx, [rbp+3F0h+var_340]
0x18027a360  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027a365  nop
0x18027a366  xorps   xmm0, xmm0
0x18027a369  movups  [rbp+3F0h+var_360], xmm0
0x18027a370  xorps   xmm1, xmm1
0x18027a373  movdqu  [rbp+3F0h+var_350], xmm1
0x18027a37b  mov     r8, rdi
0x18027a37e  mov     rdx, r14
0x18027a381  lea     rcx, [rbp+3F0h+var_360]
0x18027a388  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027a38d  nop
0x18027a38e  xorps   xmm0, xmm0
0x18027a391  movups  xmmword ptr [rbp+3F0h+var_80], xmm0
0x18027a398  xorps   xmm1, xmm1
0x18027a39b  movdqu  [rbp+3F0h+var_70], xmm1
0x18027a3a3  mov     r8, rdi
0x18027a3a6  mov     rdx, r14
0x18027a3a9  lea     rcx, [rbp+3F0h+var_80]
0x18027a3b0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027a3b5  nop
0x18027a3b6  lea     r8, aAvedelay; "AveDelay"
0x18027a3bd  lea     rdx, [rbp+3F0h+var_80]
0x18027a3c4  lea     rcx, [rbp+3F0h+var_240]
0x18027a3cb  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18027a3d0  nop
0x18027a3d1  lea     r9, [rbp+3F0h+var_360]
0x18027a3d8  mov     r8, rax
0x18027a3db  mov     dl, [rsp+4F0h+var_4A0]
0x18027a3df  lea     rcx, [rbp+3F0h+var_2C0]
0x18027a3e6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18027a3eb  nop
0x18027a3ec  lea     r9, [rbp+3F0h+var_340]
0x18027a3f3  lea     r8, [rbp+3F0h+var_2C0]
0x18027a3fa  mov     dl, [rsp+4F0h+var_4A0]
0x18027a3fe  lea     rcx, [rbp+3F0h+var_280]
0x18027a405  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18027a40a  nop
0x18027a40b  mov     r9, rbx
0x18027a40e  lea     r8, [rbp+3F0h+var_280]
0x18027a415  mov     dl, [rsp+4F0h+var_4A0]
0x18027a419  lea     rcx, [rbp+3F0h+var_3A0]
0x18027a41d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18027a422  nop
0x18027a423  lea     rax, [rbp+3F0h+var_470]
0x18027a427  mov     [rsp+4F0h+var_4B0], rax; __int64
0x18027a42c  lea     rax, [rbp+3F0h+var_380]
0x18027a430  mov     [rsp+4F0h+var_4B8], rax; __int64
0x18027a435  lea     rax, [rbp+3F0h+var_3A0]
0x18027a439  mov     [rsp+4F0h+var_4C0], rax; __int64
0x18027a43e  lea     rax, aDelayinfo; "DelayInfo"
0x18027a445  mov     [rsp+4F0h+Str+8], rax; Str
0x18027a44a  lea     rax, aReportsummary; "ReportSummary"
0x18027a451  mov     [rsp+4F0h+Str], rax; char *
0x18027a456  lea     r9, aSmiles; "Smiles"
0x18027a45d  xor     r8d, r8d; int
0x18027a460  lea     rdx, aRdCheckpoint; "RD_CHECKPOINT"
0x18027a467  lea     rcx, [rbp+3F0h+var_A0]; int
0x18027a46e  call    ??$TraceCheckpointMessage@VTraceCheckpoint@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V45@V45@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDI111V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@22@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,char const *,uint,char const *,char const *,char const *,std::string,std::string,std::string)
0x18027a473  nop
0x18027a474  lea     rcx, [rbp+3F0h+var_280]
0x18027a47b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a480  nop
0x18027a481  lea     rcx, [rbp+3F0h+var_2C0]
0x18027a488  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a48d  nop
0x18027a48e  lea     rcx, [rbp+3F0h+var_240]
0x18027a495  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a49a  nop
0x18027a49b  lea     rcx, [rbp+3F0h+var_80]
0x18027a4a2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a4a7  nop
0x18027a4a8  lea     rcx, [rbp+3F0h+var_360]
0x18027a4af  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a4b4  nop
0x18027a4b5  lea     rcx, [rbp+3F0h+var_340]
0x18027a4bc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a4c1  nop
0x18027a4c2  lea     rcx, [rbp+3F0h+var_260]
0x18027a4c9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a4ce  nop
0x18027a4cf  lea     rcx, [rbp+3F0h+var_2A0]
0x18027a4d6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a4db  nop
0x18027a4dc  lea     rcx, [rbp+3F0h+var_320]
0x18027a4e3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a4e8  nop
0x18027a4e9  lea     rcx, [rbp+3F0h+var_1C0]
0x18027a4f0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a4f5  nop
0x18027a4f6  lea     rcx, [rbp+3F0h+var_450]
0x18027a4fa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a4ff  nop
0x18027a500  lea     rcx, [rbp+3F0h+var_430]
0x18027a504  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a509  nop
0x18027a50a  lea     rcx, [rbp+3F0h+var_410]
0x18027a50e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a513  nop
0x18027a514  lea     rcx, [rbp+3F0h+var_1E0]
0x18027a51b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a520  nop
0x18027a521  lea     rcx, [rbp+3F0h+var_300]
0x18027a528  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a52d  nop
0x18027a52e  lea     rcx, [rbp+3F0h+var_2E0]
0x18027a535  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a53a  nop
0x18027a53b  lea     rcx, [rbp+3F0h+var_200]
0x18027a542  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a547  nop
0x18027a548  lea     rcx, [rbp+3F0h+var_3F0]
0x18027a54c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a551  nop
0x18027a552  lea     rcx, [rbp+3F0h+var_3D0]
0x18027a556  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a55b  nop
0x18027a55c  lea     rcx, [rsp+4F0h+var_498]
0x18027a561  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a566  nop
0x18027a567  lea     rcx, [rbp+3F0h+var_220]
0x18027a56e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027a573  nop
0x18027a574  mov     rbx, qword ptr [rbp+3F0h+var_A0+8]
0x18027a57b  test    rbx, rbx
0x18027a57e  jz      short loc_18027A5B9
0x18027a580  mov     eax, r12d
0x18027a583  lock xadd [rbx+8], eax
0x18027a588  add     eax, r12d
  ... truncated ...
```

# Microsoft::Basix::Dct::ICECore::ComputeDegreeOfRedundency(void)

- ea: `0x18021fe58`
- end: `0x180220c01`
- name: `?ComputeDegreeOfRedundency@ICECore@Dct@Basix@Microsoft@@QEAA?AV?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@XZ`
- size: `3497`
- prototype: ``
- caller_count: `5`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18021a548`
- `0x18022f760`
- `0x180230058`
- `0x180230ad8`
- `0x180243c50`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180018d1c`
- `0x18001902c`
- `0x18003c308`
- `0x1800c3bc8`
- `0x1801dab7c`
- `0x180202298`
- `0x180202480`
- `0x18021b170`
- `0x18021b1e8`
- `0x18021fe58`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x180220260`: `ComputeDegreeOfRedundency: localRelayLinkCnt =%d, localNonRelayLinkCnt=%d, lc=%s`
- `0x18022043c`: `ComputeDegreeOfRedundency: remoteRelayLinkCnt =%d, remoteNonRelayLinkCnt=%d, rc=%s`
- `0x1802205ac`: `ComputeDegreeOfRedundency: dor%d, lc=%s`
- `0x1802206fe`: `ComputeDegreeOfRedundency: dor%d, rc=%s`
- `0x18022093d`: `ComputeDegreeOfRedundency: last dor=%d, new dor=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
_QWORD *__fastcall Microsoft::Basix::Dct::ICECore::ComputeDegreeOfRedundency(__int64 a1, _QWORD *a2)
{
  __int64 v2; // r15
  unsigned int v3; // r12d
  _Mtx_t v4; // rdi
  _QWORD *v5; // r14
  _QWORD *i; // rbx
  __int64 v7; // rdx
  signed __int32 v8; // eax
  signed __int32 v9; // ett
  __int64 v10; // rax
  volatile signed __int32 *v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rdx
  _QWORD *v14; // rbx
  volatile signed __int32 *v15; // r15
  volatile signed __int32 *v16; // rsi
  unsigned int v17; // edi
  __int64 v18; // rdx
  signed __int32 v19; // eax
  signed __int32 v20; // ett
  __int128 v21; // kr00_16
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // r13
  volatile signed __int32 *v25; // rsi
  unsigned int v26; // eax
  volatile signed __int32 *v27; // rsi
  __int64 v28; // rax
  __int64 v29; // rsi
  int v30; // r9d
  volatile signed __int32 *v31; // rsi
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // r15
  volatile signed __int32 *v35; // r14
  unsigned int v36; // eax
  __int64 v37; // rsi
  int v38; // r9d
  volatile signed __int32 *v39; // rsi
  __int64 v40; // rsi
  const char *v41; // r9
  volatile signed __int32 *v42; // rsi
  __int64 v43; // rsi
  const char *v44; // r9
  volatile signed __int32 *v45; // rsi
  volatile signed __int32 *v46; // rsi
  volatile signed __int32 *v47; // rsi
  volatile signed __int32 *v48; // r13
  volatile signed __int32 *v49; // r14
  unsigned int v50; // eax
  __int64 v51; // rdx
  int v52; // r9d
  int v53; // ebx
  volatile signed __int32 *v54; // rbx
  __int64 v55; // rdx
  signed __int32 v56; // eax
  signed __int32 v57; // ett
  __int128 v58; // rcx
  _QWORD *v59; // rdi
  const char *v61; // [rsp+20h] [rbp-E0h]
  unsigned int v62; // [rsp+30h] [rbp-D0h]
  unsigned int v63; // [rsp+30h] [rbp-D0h]
  unsigned int v64; // [rsp+34h] [rbp-CCh]
  unsigned __int64 v65; // [rsp+38h] [rbp-C8h]
  volatile signed __int32 *v66; // [rsp+40h] [rbp-C0h]
  unsigned int v67; // [rsp+48h] [rbp-B8h]
  unsigned int v68; // [rsp+4Ch] [rbp-B4h]
  volatile signed __int32 *v69; // [rsp+60h] [rbp-A0h]
  __int128 v70; // [rsp+68h] [rbp-98h] BYREF
  __int128 v71; // [rsp+78h] [rbp-88h]
  _BYTE *v72; // [rsp+88h] [rbp-78h] BYREF
  volatile signed __int32 *v73; // [rsp+90h] [rbp-70h]
  volatile signed __int32 *v74; // [rsp+98h] [rbp-68h]
  __int128 v75; // [rsp+A0h] [rbp-60h]
  __int128 v76; // [rsp+B0h] [rbp-50h]
  __int128 v77; // [rsp+C0h] [rbp-40h]
  _QWORD *v78; // [rsp+D0h] [rbp-30h]
  _Mtx_t v79; // [rsp+D8h] [rbp-28h]
  __int128 v80; // [rsp+E0h] [rbp-20h]
  __int128 v81; // [rsp+F0h] [rbp-10h]
  _QWORD *v82; // [rsp+108h] [rbp+8h]
  __int64 v83; // [rsp+110h] [rbp+10h]
  _BYTE v84[32]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v85; // [rsp+138h] [rbp+38h]
  __int128 v86; // [rsp+140h] [rbp+40h] BYREF

  v78 = a2;
  v2 = a1;
  v83 = a1;
  v3 = 0;
  v77 = 0;
  v67 = 0;
  v68 = 0;
  v4 = (_Mtx_t)(a1 + 456);
  v79 = (_Mtx_t)(a1 + 456);
  v85 = a1 + 456;
  if ( Mtx_lock((_Mtx_t)(a1 + 456)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v4 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v75 = 0;
  v76 = 0;
  v5 = *(_QWORD **)(v2 + 544);
  for ( i = (_QWORD *)*v5; i != v5; i = (_QWORD *)*i )
  {
    v7 = i[10];
    if ( v7 )
    {
      v8 = *(_DWORD *)(v7 + 8);
      while ( v8 )
      {
        v9 = v8;
        v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 8), v8 + 1, v8);
        if ( v9 == v8 )
        {
          v10 = i[9];
          v11 = (volatile signed __int32 *)i[10];
          if ( v10 )
          {
            v12 = *(_QWORD *)(v10 + 1392);
            if ( v12 )
              *(_BYTE *)(v12 + 226) = 0;
            v13 = *(_QWORD *)(v10 + 1408);
            if ( v13 )
              *(_BYTE *)(v13 + 226) = 0;
          }
          if ( v11 )
          {
            if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
              if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
            }
          }
          break;
        }
      }
    }
  }
  v82 = *(_QWORD **)(v2 + 544);
  v14 = (_QWORD *)*v82;
  if ( (_QWORD *)*v82 != v82 )
  {
    v15 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
    v69 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
    v74 = (volatile signed __int32 *)*((_QWORD *)&v75 + 1);
    v16 = (volatile signed __int32 *)*((_QWORD *)&v76 + 1);
    v66 = (volatile signed __int32 *)*((_QWORD *)&v76 + 1);
    v17 = 0;
    while ( 1 )
    {
      v80 = 0;
      v81 = 0;
      v65 = 0;
      v64 = 0;
      v62 = 0;
      v18 = v14[10];
      if ( v18 )
      {
        v19 = *(_DWORD *)(v18 + 8);
        while ( v19 )
        {
          v20 = v19;
          v19 = _InterlockedCompareExchange((volatile signed __int32 *)(v18 + 8), v19 + 1, v19);
          if ( v20 == v19 )
          {
            v21 = *(_OWORD *)(v14 + 9);
            goto LABEL_27;
          }
        }
      }
      v21 = 0;
LABEL_27:
      if ( !*(_DWORD *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v21 + 1508) )
        break;
      if ( *((_QWORD *)&v21 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (***((void (__fastcall ****)(_QWORD))&v21 + 1))(*((_QWORD *)&v21 + 1));
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 12LL)) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v21 + 1) + 8LL))(*((_QWORD *)&v21 + 1));
        }
      }
LABEL_147:
      v14 = (_QWORD *)*v14;
      if ( v14 == v82 )
      {
        v63 = v17;
        v4 = v79;
        v2 = v83;
        v47 = v69;
        v3 = v63;
        v48 = v74;
        v49 = v66;
        goto LABEL_150;
      }
    }
    if ( (_QWORD)v21 && (v22 = *(_QWORD *)(v21 + 1392)) != 0 && !*(_BYTE *)(v22 + 225) )
    {
      v23 = *(_QWORD *)(v21 + 1400);
      if ( v23 )
        _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
      v24 = *(_QWORD *)(v21 + 1392);
      v25 = *(volatile signed __int32 **)(v21 + 1400);
      v73 = v25;
      *(_QWORD *)&v80 = v24;
      *((_QWORD *)&v80 + 1) = v25;
      LODWORD(v65) = Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(
                       (Microsoft::Basix::Dct::ICE::Candidate *)v24,
                       0);
      v26 = Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink((Microsoft::Basix::Dct::ICE::Candidate *)v24, 0);
      HIDWORD(v65) = v26;
      if ( v24 && *(_DWORD *)(v24 + 228) == 3 && (!(_QWORD)v75 || v26 + (unsigned int)v65 < v67) )
      {
        if ( v25 )
          _InterlockedIncrement(v25 + 2);
        *(_QWORD *)&v75 = v24;
        v27 = v74;
        v74 = v73;
        *((_QWORD *)&v75 + 1) = v73;
        if ( v27 )
        {
          if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
            if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
          }
        }
        v67 = v65 + HIDWORD(v65);
        v28 = *(_QWORD *)(v21 + 1384);
        if ( v28 )
          _InterlockedIncrement((volatile signed __int32 *)(v28 + 8));
        *(_QWORD *)&v77 = *(_QWORD *)(v21 + 1376);
        v69 = *(volatile signed __int32 **)(v21 + 1384);
        *((_QWORD *)&v77 + 1) = v69;
        if ( v15 )
        {
          if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
            if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
          }
        }
      }
      v86 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v86);
      if ( (_QWORD)v86 && *(_BYTE *)(v86 + 128) )
      {
        v72 = v84;
        v29 = Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v84, v24, 0, 6);
        v70 = 0;
        v71 = 0;
        std::string::_Construct<1,char const *>(
          &v70,
          "ComputeDegreeOfRedundency: localRelayLinkCnt =%d, localNonRelayLinkCnt=%d, lc=%s",
          80,
          v30,
          v61);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned int,std::string>(
          (unsigned int)&v86,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v70,
          v65,
          SBYTE4(v65),
          v29);
        std::string::_Tidy_deallocate(&v70);
      }
      v31 = (volatile signed __int32 *)*((_QWORD *)&v86 + 1);
      if ( *((_QWORD *)&v86 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
          if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
        }
      }
      v16 = v66;
    }
    else
    {
      v73 = (volatile signed __int32 *)*((_QWORD *)&v80 + 1);
      v24 = v80;
    }
    if ( (_QWORD)v21 && (v32 = *(_QWORD *)(v21 + 1408)) != 0 && !*(_BYTE *)(v32 + 225) )
    {
      v33 = *(_QWORD *)(v21 + 1416);
      if ( v33 )
        _InterlockedIncrement((volatile signed __int32 *)(v33 + 8));
      v34 = *(_QWORD *)(v21 + 1408);
      v35 = *(volatile signed __int32 **)(v21 + 1416);
      *(_QWORD *)&v81 = v34;
      *((_QWORD *)&v81 + 1) = v35;
      v64 = Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink((Microsoft::Basix::Dct::ICE::Candidate *)v34, 0);
      v36 = Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink((Microsoft::Basix::Dct::ICE::Candidate *)v34, 0);
      v62 = v36;
      if ( v34 && *(_DWORD *)(v34 + 228) == 3 && (!(_QWORD)v76 || v36 + v64 < v68) )
      {
        if ( v35 )
          _InterlockedIncrement(v35 + 2);
        *(_QWORD *)&v76 = v34;
        v66 = v35;
        *((_QWORD *)&v76 + 1) = v35;
        if ( v16 )
        {
          if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
            if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
          }
        }
        v68 = v64 + v62;
      }
      v86 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v86);
      if ( (_QWORD)v86 && *(_BYTE *)(v86 + 128) )
      {
        v72 = v84;
        v37 = Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v84, v34, 0, 6);
        v70 = 0;
        v71 = 0;
        std::string::_Construct<1,char const *>(
          &v70,
          "ComputeDegreeOfRedundency: remoteRelayLinkCnt =%d, remoteNonRelayLinkCnt=%d, rc=%s",
          82,
          v38,
          v61);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned int,std::string>(
          (unsigned int)&v86,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v70,
          v64,
          v62,
          v37);
        std::string::_Tidy_deallocate(&v70);
      }
      v39 = (volatile signed __int32 *)*((_QWORD *)&v86 + 1);
      if ( *((_QWORD *)&v86 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
          if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
        }
      }
    }
    else
    {
      v35 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
      v34 = v81;
    }
    if ( !v24 || *(_BYTE *)(v24 + 226) )
    {
LABEL_111:
      if ( !v34 || *(_BYTE *)(v34 + 226) )
      {
LABEL_134:
        if ( *((_QWORD *)&v21 + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL)) )
          {
            (***((void (__fastcall ****)(_QWORD))&v21 + 1))(*((_QWORD *)&v21 + 1));
            if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 12LL)) )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v21 + 1) + 8LL))(*((_QWORD *)&v21 + 1));
          }
        }
        if ( v35 )
        {
          if ( !_InterlockedDecrement(v35 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
            if ( !_InterlockedDecrement(v35 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
          }
        }
        v46 = v73;
        if ( v73 )
        {
          if ( !_InterlockedDecrement(v73 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
            if ( !_InterlockedDecrement(v46 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
          }
        }
        v16 = v66;
        v15 = v69;
        goto LABEL_147;
      }
      if ( *(_DWORD *)(v34 + 228) == 3 )
      {
        if ( v62 || v64 > 1 )
          goto LABEL_125;
        if ( v65 != 1 || !v24 || *(_BYTE *)(v24 + 226) )
          goto LABEL_126;
      }
      else if ( !v24 || *(_DWORD *)(v24 + 228) == 3 || *(_BYTE *)(v24 + 226) || !HIDWORD(v65) )
      {
        goto LABEL_126;
      }
      *(_BYTE *)(v24 + 226) = 1;
LABEL_125:
      ++v17;
LABEL_126:
      v86 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v86);
      if ( (_QWORD)v86 && *(_BYTE *)(v86 + 128) )
      {
        v72 = v84;
        v43 = Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v84, v34, 0, 6);
        v70 = 0;
        v71 = 0;
        std::string::_Construct<1,char const *>(&v70, "ComputeDegreeOfRedundency: dor%d, rc=%s", 39, v44);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,std::string>(
          (unsigned int)&v86,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v70,
          v17,
          v43);
        std::string::_Tidy_deallocate(&v70);
      }
      v45 = (volatile signed __int32 *)*((_QWORD *)&v86 + 1);
      if ( *((_QWORD *)&v86 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
          if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
        }
      }
      *(_BYTE *)(v34 + 226) = 1;
      goto LABEL_134;
    }
    if ( *(_DWORD *)(v24 + 228) == 3 )
    {
      if ( v65 > 1 )
      {
LABEL_102:
        ++v17;
LABEL_103:
        v86 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v86);
        if ( (_QWORD)v86 && *(_BYTE *)(v86 + 128) )
        {
          v72 = v84;
          v40 = Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v84, v24, 0, 6);
          v70 = 0;
          v71 = 0;
          std::string::_Construct<1,char const *>(&v70, "ComputeDegreeOfRedundency: dor%d, lc=%s", 39, v41);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,std::string>(
            (unsigned int)&v86,
            (unsigned int)"BASIX_DCT",
            (unsigned int)&v70,
            v17,
            v40);
          std::string::_Tidy_deallocate(&v70);
        }
        v42 = (volatile signed __int32 *)*((_QWORD *)&v86 + 1);
        if ( *((_QWORD *)&v86 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
            if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
          }
        }
        *(_BYTE *)(v24 + 226) = 1;
        goto LABEL_111;
      }
      if ( v62 || v64 != 1 || !v34 || *(_BYTE *)(v34 + 226) )
        goto LABEL_103;
    }
    else if ( !v34 || *(_DWORD *)(v34 + 228) == 3 || *(_BYTE *)(v34 + 226) || !v62 )
    {
      goto LABEL_103;
    }
    *(_BYTE *)(v34 + 226) = 1;
    goto LABEL_102;
  }
  v47 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
  v48 = (volatile signed __int32 *)*((_QWORD *)&v75 + 1);
  v49 = (volatile signed __int32 *)*((_QWORD *)&v76 + 1);
LABEL_150:
  v50 = *(_DWORD *)(v2 + 9064);
  if ( *(_DWORD *)(v2 + 9060) > v50 )
  {
    if ( v50 < v3 )
      goto LABEL_157;
LABEL_156:
    *(_BYTE *)(v2 + 264) = 0;
    goto LABEL_157;
  }
  if ( v50 >= v3 )
    goto LABEL_156;
  v51 = *(_QWORD *)std::chrono::steady_clock::now(&v72) / 1000000LL;
  if ( !*(_BYTE *)(v2 + 264) )
    *(_BYTE *)(v2 + 264) = 1;
  *(_QWORD *)(v2 + 256) = v51;
LABEL_157:
  v86 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v86);
  if ( (_QWORD)v86 && *(_BYTE *)(v86 + 128) )
  {
    v53 = *(_DWORD *)(v2 + 9060);
    v70 = 0;
    v71 = 0;
    std::string::_Construct<1,char const *>(&v70, "ComputeDegreeOfRedundency: last dor=%d, new dor=%d", 50, v52);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int>(
      (unsigned int)&v86,
      (unsigned int)"BASIX_DCT",
      (unsigned int)&v70,
      v53,
      v3);
    std::string::_Tidy_deallocate(&v70);
  }
  v54 = (volatile signed __int32 *)*((_QWORD *)&v86 + 1);
  if ( *((_QWORD *)&v86 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
      if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
    }
  }
  *(_DWORD *)(v2 + 9060) = v3;
  if ( v49 )
  {
    if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
      if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
    }
  }
  if ( v48 )
  {
    if ( _InterlockedExchangeAdd(v48 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
      if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
    }
  }
  Mtx_unlock(v4);
  v55 = *(_QWORD *)(v2 + 160);
  if ( v55 )
  {
    v56 = *(_DWORD *)(v55 + 8);
    while ( v56 )
    {
      v57 = v56;
      v56 = _InterlockedCompareExchange((volatile signed __int32 *)(v55 + 8), v56 + 1, v56);
      if ( v57 == v56 )
      {
        v58 = *(_OWORD *)(v2 + 152);
        goto LABEL_177;
      }
    }
  }
  v58 = 0;
LABEL_177:
  if ( (_QWORD)v58 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v58 + 72LL))(v58, v3);
  if ( *(_DWORD *)(v2 + 9064) < *(_DWORD *)(v2 + 9060) && v67 && v67 <= v68 )
  {
    v59 = v78;
    *v78 = v77;
    v59[1] = v47;
    if ( *((_QWORD *)&v58 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v58 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (***((void (__fastcall ****)(_QWORD))&v58 + 1))(*((_QWORD *)&v58 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v58 + 1) + 12LL), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v58 + 1) + 8LL))(*((_QWORD *)&v58 + 1));
      }
    }
  }
  else
  {
    v59 = v78;
    *v78 = 0;
    v59[1] = 0;
    if ( *((_QWORD *)&v58 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v58 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (***((void (__fastcall ****)(_QWORD))&v58 + 1))(*((_QWORD *)&v58 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v58 + 1) + 12LL), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v58 + 1) + 8LL))(*((_QWORD *)&v58 + 1));
      }
    }
    if ( v47 )
    {
      if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
        if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
      }
    }
  }
  return v59;
}

```

## disassembly

```asm
0x18021fe58  mov     [rsp-8+arg_10], rbx
0x18021fe5d  push    rbp
0x18021fe5e  push    rsi
0x18021fe5f  push    rdi
0x18021fe60  push    r12
0x18021fe62  push    r13
0x18021fe64  push    r14
0x18021fe66  push    r15
0x18021fe68  lea     rbp, [rsp-60h]
0x18021fe6d  mov     eax, 160h
0x18021fe72  call    _alloca_probe
0x18021fe77  sub     rsp, rax
0x18021fe7a  mov     rax, cs:__security_cookie
0x18021fe81  xor     rax, rsp
0x18021fe84  mov     [rbp+90h+var_40], rax
0x18021fe88  mov     [rbp+90h+var_C0], rdx
0x18021fe8c  mov     r15, rcx
0x18021fe8f  mov     [rbp+90h+var_80], rcx
0x18021fe93  mov     [rbp+90h+var_B8], rdx
0x18021fe97  xor     r13d, r13d
0x18021fe9a  mov     r12d, r13d
0x18021fe9d  mov     [rsp+190h+var_160], r13d
0x18021fea2  xorps   xmm1, xmm1
0x18021fea5  movdqu  [rbp+90h+var_D0], xmm1
0x18021feaa  mov     [rsp+190h+var_148], r13d
0x18021feaf  mov     [rsp+190h+var_144], r13d
0x18021feb4  lea     rdi, [rcx+1C8h]
0x18021febb  mov     [rbp+90h+var_B8], rdi
0x18021febf  mov     [rbp+90h+var_58], rdi
0x18021fec3  mov     rcx, rdi; _Mtx_t
0x18021fec6  call    _Mtx_lock
0x18021fecb  test    eax, eax
0x18021fecd  jnz     loc_180220BF6
0x18021fed3  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x18021feda  jz      loc_180220BE4
0x18021fee0  xorps   xmm1, xmm1
0x18021fee3  movdqu  [rbp+90h+var_F0], xmm1
0x18021fee8  movdqu  [rbp+90h+var_E0], xmm1
0x18021feed  mov     r14, [r15+220h]
0x18021fef4  mov     rbx, [r14]
0x18021fef7  jmp     loc_18021FF95
0x18021fefc  mov     rdx, [rbx+50h]
0x18021ff00  test    rdx, rdx
0x18021ff03  jz      loc_18021FF92
0x18021ff09  mov     eax, [rdx+8]
0x18021ff0c  jmp     short loc_18021FF18
0x18021ff0e  lea     ecx, [rax+1]
0x18021ff11  lock cmpxchg [rdx+8], ecx
0x18021ff16  jz      short loc_18021FF1E
0x18021ff18  test    eax, eax
0x18021ff1a  jnz     short loc_18021FF0E
0x18021ff1c  jmp     short loc_18021FF92
0x18021ff1e  mov     rax, [rbx+48h]
0x18021ff22  mov     rcx, [rbx+50h]
0x18021ff26  mov     rsi, rcx
0x18021ff29  test    rax, rax
0x18021ff2c  jz      short loc_18021FF54
0x18021ff2e  mov     rdx, [rax+570h]
0x18021ff35  test    rdx, rdx
0x18021ff38  jz      short loc_18021FF41
0x18021ff3a  mov     [rdx+0E2h], r13b
0x18021ff41  mov     rdx, [rax+580h]
0x18021ff48  test    rdx, rdx
0x18021ff4b  jz      short loc_18021FF54
0x18021ff4d  mov     [rdx+0E2h], r13b
0x18021ff54  test    rsi, rsi
0x18021ff57  jz      short loc_18021FF92
0x18021ff59  or      eax, 0FFFFFFFFh
0x18021ff5c  lock xadd [rsi+8], eax
0x18021ff61  cmp     eax, 1
0x18021ff64  jnz     short loc_18021FF92
0x18021ff66  mov     rax, [rsi]
0x18021ff69  mov     rcx, rsi
0x18021ff6c  mov     rax, [rax]
0x18021ff6f  call    cs:__guard_dispatch_icall_fptr
0x18021ff75  or      eax, 0FFFFFFFFh
0x18021ff78  lock xadd [rsi+0Ch], eax
0x18021ff7d  cmp     eax, 1
0x18021ff80  jnz     short loc_18021FF92
0x18021ff82  mov     rax, [rsi]
0x18021ff85  mov     rcx, rsi
0x18021ff88  mov     rax, [rax+8]
0x18021ff8c  call    cs:__guard_dispatch_icall_fptr
0x18021ff92  mov     rbx, [rbx]
0x18021ff95  cmp     rbx, r14
0x18021ff98  jnz     loc_18021FEFC
0x18021ff9e  mov     rax, [r15+220h]
0x18021ffa5  mov     [rbp+90h+var_88], rax
0x18021ffa9  mov     rbx, [rax]
0x18021ffac  cmp     rbx, rax
0x18021ffaf  jz      loc_18022088C
0x18021ffb5  mov     r15, qword ptr [rbp+90h+var_D0+8]
0x18021ffb9  mov     [rsp+190h+var_130], r15
0x18021ffbe  mov     rax, qword ptr [rbp+90h+var_F0+8]
0x18021ffc2  mov     [rbp+90h+var_F8], rax
0x18021ffc6  mov     rsi, qword ptr [rbp+90h+var_E0+8]
0x18021ffca  mov     [rsp+190h+var_150], rsi
0x18021ffcf  mov     edi, [rsp+190h+var_160]
0x18021ffd3  xorps   xmm1, xmm1
0x18021ffd6  movdqu  [rbp+90h+var_B0], xmm1
0x18021ffdb  movdqu  [rbp+90h+var_A0], xmm1
0x18021ffe0  mov     [rsp+190h+var_158], r13d
0x18021ffe5  mov     [rsp+190h+var_154], r13d
0x18021ffea  mov     [rsp+190h+var_15C], r13d
0x18021ffef  mov     [rsp+190h+var_160], r13d
0x18021fff4  movdqu  [rsp+190h+var_140], xmm1
0x18021fffa  mov     rdx, [rbx+50h]
0x18021fffe  test    rdx, rdx
0x180220001  jz      short loc_180220016
0x180220003  mov     eax, [rdx+8]
0x180220006  jmp     short loc_180220012
0x180220008  lea     ecx, [rax+1]
0x18022000b  lock cmpxchg [rdx+8], ecx
0x180220010  jz      short loc_180220081
0x180220012  test    eax, eax
0x180220014  jnz     short loc_180220008
0x180220016  mov     r14, qword ptr [rsp+190h+var_140]
0x18022001b  mov     r12, qword ptr [rsp+190h+var_140+8]
0x180220020  lea     rcx, [r14+5E4h]
0x180220027  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18022002c  mov     ecx, [rax]
0x18022002e  nop
0x18022002f  test    ecx, ecx
0x180220031  jz      short loc_180220095
0x180220033  test    r12, r12
0x180220036  jz      short loc_18022007C
0x180220038  or      r14d, 0FFFFFFFFh
0x18022003c  mov     eax, r14d
0x18022003f  lock xadd [r12+8], eax
0x180220046  add     eax, r14d
0x180220049  jnz     short loc_18022007C
0x18022004b  mov     rax, [r12]
0x18022004f  mov     rcx, r12
0x180220052  mov     rax, [rax]
0x180220055  call    cs:__guard_dispatch_icall_fptr
0x18022005b  mov     eax, r14d
0x18022005e  lock xadd [r12+0Ch], eax
0x180220065  add     eax, r14d
0x180220068  jnz     short loc_18022007C
0x18022006a  mov     rax, [r12]
0x18022006e  mov     rcx, r12
0x180220071  mov     rax, [rax+8]
0x180220075  call    cs:__guard_dispatch_icall_fptr
0x18022007b  nop
0x18022007c  jmp     loc_18022085E
0x180220081  mov     r14, [rbx+48h]
0x180220085  mov     qword ptr [rsp+190h+var_140], r14
0x18022008a  mov     r12, [rbx+50h]
0x18022008e  mov     qword ptr [rsp+190h+var_140+8], r12
0x180220093  jmp     short loc_180220020
0x180220095  test    r14, r14
0x180220098  jz      loc_1802204C5
0x18022009e  mov     rax, [r14+570h]
0x1802200a5  test    rax, rax
0x1802200a8  jz      loc_1802204C5
0x1802200ae  cmp     [rax+0E1h], r13b
0x1802200b5  jnz     loc_1802204C5
0x1802200bb  mov     rax, [r14+578h]
0x1802200c2  test    rax, rax
0x1802200c5  jz      short loc_1802200CB
0x1802200c7  lock inc dword ptr [rax+8]
0x1802200cb  mov     r13, [r14+570h]
0x1802200d2  mov     rsi, [r14+578h]
0x1802200d9  mov     [rbp+90h+var_100], rsi
0x1802200dd  mov     qword ptr [rbp+90h+var_B0], r13
0x1802200e1  mov     qword ptr [rbp+90h+var_B0+8], rsi
0x1802200e5  xor     edx, edx; int
0x1802200e7  mov     rcx, r13; this
0x1802200ea  call    ?AdjustRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(int)
0x1802200ef  mov     [rsp+190h+var_158], eax
0x1802200f3  xor     edx, edx; int
0x1802200f5  mov     rcx, r13; this
0x1802200f8  call    ?AdjustNonRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(int)
0x1802200fd  mov     [rsp+190h+var_154], eax
0x180220101  test    r13, r13
0x180220104  jz      loc_180220202
0x18022010a  cmp     dword ptr [r13+0E4h], 3
0x180220112  jnz     loc_180220202
0x180220118  cmp     qword ptr [rbp+90h+var_F0], 0
0x18022011d  jz      short loc_18022012F
0x18022011f  mov     ecx, [rsp+190h+var_158]
0x180220123  add     ecx, eax
0x180220125  cmp     ecx, [rsp+190h+var_148]
0x180220129  jnb     loc_180220202
0x18022012f  test    rsi, rsi
0x180220132  jz      short loc_180220138
0x180220134  lock inc dword ptr [rsi+8]
0x180220138  mov     qword ptr [rbp+90h+var_F0], r13
0x18022013c  mov     rsi, [rbp+90h+var_F8]
0x180220140  mov     rax, [rbp+90h+var_100]
0x180220144  mov     [rbp+90h+var_F8], rax
0x180220148  mov     qword ptr [rbp+90h+var_F0+8], rax
0x18022014c  test    rsi, rsi
0x18022014f  jz      short loc_18022018A
0x180220151  or      eax, 0FFFFFFFFh
0x180220154  lock xadd [rsi+8], eax
0x180220159  cmp     eax, 1
0x18022015c  jnz     short loc_18022018A
0x18022015e  mov     rax, [rsi]
0x180220161  mov     rcx, rsi
0x180220164  mov     rax, [rax]
0x180220167  call    cs:__guard_dispatch_icall_fptr
0x18022016d  or      eax, 0FFFFFFFFh
0x180220170  lock xadd [rsi+0Ch], eax
0x180220175  cmp     eax, 1
0x180220178  jnz     short loc_18022018A
0x18022017a  mov     rax, [rsi]
0x18022017d  mov     rcx, rsi
0x180220180  mov     rax, [rax+8]
0x180220184  call    cs:__guard_dispatch_icall_fptr
0x18022018a  mov     eax, [rsp+190h+var_154]
0x18022018e  add     eax, [rsp+190h+var_158]
0x180220192  mov     [rsp+190h+var_148], eax
0x180220196  mov     rax, [r14+568h]
0x18022019d  test    rax, rax
0x1802201a0  jz      short loc_1802201A6
0x1802201a2  lock inc dword ptr [rax+8]
0x1802201a6  mov     rax, [r14+560h]
0x1802201ad  mov     qword ptr [rbp+90h+var_D0], rax
0x1802201b1  mov     rsi, r15
0x1802201b4  mov     r15, [r14+568h]
0x1802201bb  mov     [rsp+190h+var_130], r15
0x1802201c0  mov     qword ptr [rbp+90h+var_D0+8], r15
0x1802201c4  test    rsi, rsi
0x1802201c7  jz      short loc_180220202
0x1802201c9  or      eax, 0FFFFFFFFh
0x1802201cc  lock xadd [rsi+8], eax
0x1802201d1  cmp     eax, 1
0x1802201d4  jnz     short loc_180220202
0x1802201d6  mov     rax, [rsi]
0x1802201d9  mov     rcx, rsi
0x1802201dc  mov     rax, [rax]
0x1802201df  call    cs:__guard_dispatch_icall_fptr
0x1802201e5  or      eax, 0FFFFFFFFh
0x1802201e8  lock xadd [rsi+0Ch], eax
0x1802201ed  cmp     eax, 1
0x1802201f0  jnz     short loc_180220202
0x1802201f2  mov     rax, [rsi]
0x1802201f5  mov     rcx, rsi
0x1802201f8  mov     rax, [rax+8]
0x1802201fc  call    cs:__guard_dispatch_icall_fptr
0x180220202  xorps   xmm0, xmm0
0x180220205  movups  [rbp+90h+var_50], xmm0
0x180220209  lea     rcx, [rbp+90h+var_50]
0x18022020d  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x180220212  nop
0x180220213  mov     rax, qword ptr [rbp+90h+var_50]
0x180220217  test    rax, rax
0x18022021a  jz      loc_1802202A5
0x180220220  cmp     byte ptr [rax+80h], 0
0x180220227  jz      short loc_1802202A5
0x180220229  lea     rax, [rbp+90h+var_78]
0x18022022d  mov     [rbp+90h+var_108], rax
0x180220231  mov     r9d, 6
0x180220237  xor     r8d, r8d
0x18022023a  mov     rdx, r13
0x18022023d  lea     rcx, [rbp+90h+var_78]
0x180220241  call    ??$ToString@VCandidate@ICE@Dct@Basix@Microsoft@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVCandidate@ICE@Dct@01@HH@Z; Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(Microsoft::Basix::Dct::ICE::Candidate const &,int,int)
0x180220246  mov     rsi, rax
0x180220249  xorps   xmm0, xmm0
0x18022024c  movups  [rsp+190h+var_128], xmm0
0x180220251  xorps   xmm1, xmm1
0x180220254  movdqu  [rsp+190h+var_118], xmm1
0x18022025a  mov     r8d, 50h ; 'P'
0x180220260  lea     rdx, aComputedegreeo; "ComputeDegreeOfRedundency: localRelayLi"...
0x180220267  lea     rcx, [rsp+190h+var_128]
0x18022026c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180220271  nop
0x180220272  mov     [rsp+190h+var_168], rsi
0x180220277  mov     eax, [rsp+190h+var_154]
0x18022027b  mov     dword ptr [rsp+190h+var_170], eax
0x18022027f  mov     r9d, [rsp+190h+var_158]
0x180220284  lea     r8, [rsp+190h+var_128]
0x180220289  lea     rdx, aBasixDct; "BASIX_DCT"
0x180220290  lea     rcx, [rbp+90h+var_50]
0x180220294  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@IIV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@IIV65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,uint,uint,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,uint,uint,std::string)
0x180220299  nop
0x18022029a  lea     rcx, [rsp+190h+var_128]
0x18022029f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1802202a4  nop
0x1802202a5  mov     rsi, qword ptr [rbp+90h+var_50+8]
0x1802202a9  test    rsi, rsi
0x1802202ac  jz      short loc_1802202E7
0x1802202ae  or      eax, 0FFFFFFFFh
0x1802202b1  lock xadd [rsi+8], eax
0x1802202b6  cmp     eax, 1
0x1802202b9  jnz     short loc_1802202E7
0x1802202bb  mov     rax, [rsi]
0x1802202be  mov     rcx, rsi
0x1802202c1  mov     rax, [rax]
0x1802202c4  call    cs:__guard_dispatch_icall_fptr
0x1802202ca  or      eax, 0FFFFFFFFh
0x1802202cd  lock xadd [rsi+0Ch], eax
0x1802202d2  cmp     eax, 1
0x1802202d5  jnz     short loc_1802202E7
0x1802202d7  mov     rax, [rsi]
0x1802202da  mov     rcx, rsi
0x1802202dd  mov     rax, [rax+8]
0x1802202e1  call    cs:__guard_dispatch_icall_fptr
0x1802202e7  mov     rsi, [rsp+190h+var_150]
  ... truncated ...
```

# ProfileTelemetry::CUserProfile_Unload::StopActivity(void)

- ea: `0x180029980`
- end: `0x18002a1e4`
- name: `?StopActivity@CUserProfile_Unload@ProfileTelemetry@@MEAAXXZ`
- size: `2148`
- prototype: `void __fastcall(ProfileTelemetry::CUserProfile_Unload *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180029980`
- `0x180035fe0`
- `0x18003a730`
- `0x18003aae0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800299f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029f47`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800299f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029f47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029a09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029a24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029a3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029f5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029f7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029f94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029a09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029a24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029a3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029f5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029f7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029f94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a0d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a0d4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180029a6e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180029fc4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180029a6e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180029fc4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180029b64`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002a0ba`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180029b64`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002a0ba`
- `ntdll!EtwEventWriteTransfer` at `0x18002a1a7`
- `ntdll!EtwEventWriteTransfer` at `0x18002a1a7`
- `ntdll!EtwEventSetInformation` at `0x180029b35`
- `ntdll!EtwEventSetInformation` at `0x18002a08b`
- `ntdll!EtwEventSetInformation` at `0x180029b35`
- `ntdll!EtwEventSetInformation` at `0x18002a08b`
- `ntdll!EtwEventRegister` at `0x180029b1a`
- `ntdll!EtwEventRegister` at `0x18002a070`
- `ntdll!EtwEventRegister` at `0x180029b1a`
- `ntdll!EtwEventRegister` at `0x18002a070`

## pseudocode

```c
void __fastcall ProfileTelemetry::CUserProfile_Unload::StopActivity(ProfileTelemetry::CUserProfile_Unload *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rbx
  RTL_SRWLOCK *v6; // rbx
  _QWORD *v7; // rbx
  _QWORD *Ptr; // r13
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // r9
  const unsigned __int16 *v12; // r10
  const unsigned __int16 *v13; // r11
  const unsigned __int16 *v14; // rbx
  const unsigned __int16 *v15; // rsi
  const unsigned __int16 *v16; // r15
  const unsigned __int16 *v17; // r12
  __int64 v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  int v35; // eax
  int v36; // ecx
  RTL_SRWLOCK *v37; // rbx
  _QWORD *v38; // rbx
  _QWORD *v39; // rbx
  __int64 v40; // r8
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK v44; // [rsp+48h] [rbp-B8h] BYREF
  PSRWLOCK v45; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+58h] [rbp-A8h] BYREF
  int v47; // [rsp+5Ch] [rbp-A4h] BYREF
  int v48; // [rsp+60h] [rbp-A0h] BYREF
  int v49; // [rsp+64h] [rbp-9Ch] BYREF
  int v50; // [rsp+68h] [rbp-98h] BYREF
  PSRWLOCK v51; // [rsp+70h] [rbp-90h] BYREF
  __int128 v52; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v53; // [rsp+90h] [rbp-70h] BYREF
  int v54; // [rsp+98h] [rbp-68h]
  int v55; // [rsp+9Ch] [rbp-64h]
  __int16 *v56; // [rsp+A0h] [rbp-60h]
  __int64 v57; // [rsp+A8h] [rbp-58h]
  PSRWLOCK *v58; // [rsp+B0h] [rbp-50h]
  __int64 v59; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *v60; // [rsp+C0h] [rbp-40h]
  __int64 v61; // [rsp+C8h] [rbp-38h]
  PSRWLOCK *p_SRWLock; // [rsp+D0h] [rbp-30h]
  __int64 v63; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v64; // [rsp+E0h] [rbp-20h] BYREF
  int v65; // [rsp+E8h] [rbp-18h]
  int v66; // [rsp+ECh] [rbp-14h]
  __int16 *v67; // [rsp+F0h] [rbp-10h]
  __int64 v68; // [rsp+F8h] [rbp-8h]
  PSRWLOCK *v69; // [rsp+100h] [rbp+0h]
  __int64 v70; // [rsp+108h] [rbp+8h]
  PSRWLOCK *v71; // [rsp+110h] [rbp+10h]
  __int64 v72; // [rsp+118h] [rbp+18h]
  PSRWLOCK *v73; // [rsp+120h] [rbp+20h]
  __int64 v74; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v75; // [rsp+130h] [rbp+30h]
  int v76; // [rsp+138h] [rbp+38h]
  int v77; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v78; // [rsp+140h] [rbp+40h]
  __int64 v79; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v80; // [rsp+150h] [rbp+50h]
  int v81; // [rsp+158h] [rbp+58h]
  int v82; // [rsp+15Ch] [rbp+5Ch]
  int *v83; // [rsp+160h] [rbp+60h]
  __int64 v84; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v85; // [rsp+170h] [rbp+70h]
  int v86; // [rsp+178h] [rbp+78h]
  int v87; // [rsp+17Ch] [rbp+7Ch]
  int *v88; // [rsp+180h] [rbp+80h]
  __int64 v89; // [rsp+188h] [rbp+88h]
  const unsigned __int16 *v90; // [rsp+190h] [rbp+90h]
  int v91; // [rsp+198h] [rbp+98h]
  int v92; // [rsp+19Ch] [rbp+9Ch]
  int *v93; // [rsp+1A0h] [rbp+A0h]
  __int64 v94; // [rsp+1A8h] [rbp+A8h]
  const unsigned __int16 *v95; // [rsp+1B0h] [rbp+B0h]
  int v96; // [rsp+1B8h] [rbp+B8h]
  int v97; // [rsp+1BCh] [rbp+BCh]
  const unsigned __int16 *v98; // [rsp+1C0h] [rbp+C0h]
  int v99; // [rsp+1C8h] [rbp+C8h]
  int v100; // [rsp+1CCh] [rbp+CCh]
  int *v101; // [rsp+1D0h] [rbp+D0h]
  __int64 v102; // [rsp+1D8h] [rbp+D8h]
  const unsigned __int16 *v103; // [rsp+1E0h] [rbp+E0h]
  int v104; // [rsp+1E8h] [rbp+E8h]
  int v105; // [rsp+1ECh] [rbp+ECh]
  const unsigned __int16 *v106; // [rsp+1F0h] [rbp+F0h]
  int v107; // [rsp+1F8h] [rbp+F8h]
  int v108; // [rsp+1FCh] [rbp+FCh]
  int *v109; // [rsp+200h] [rbp+100h]
  __int64 v110; // [rsp+208h] [rbp+108h]
  WINBOOL *p_fPending; // [rsp+210h] [rbp+110h]
  __int64 v112; // [rsp+218h] [rbp+118h]
  const unsigned __int16 *v113; // [rsp+220h] [rbp+120h]
  int v114; // [rsp+228h] [rbp+128h]
  int v115; // [rsp+22Ch] [rbp+12Ch]

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) )
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
    if ( v4 )
    {
      if ( v5 )
      {
        v6 = v5 + 33;
        AcquireSRWLockExclusive(v6);
        SRWLock = 0;
        **((_DWORD **)this + 34) = 2;
        if ( v6 )
          ReleaseSRWLockExclusive(v6);
      }
      else
      {
        v44 = 0;
        **((_DWORD **)this + 34) = 2;
      }
      SRWLock = 0;
      fPending = 0;
      if ( InitOnceBeginInitialize(&`ProfileLogging::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
        && fPending )
      {
        SRWLock = (PSRWLOCK)&qword_18007F888;
        qword_18007F890 = 0;
        byte_18007F898 = 0;
        dword_18007F89C = 0;
        qword_18007F888 = (__int64)&ProfileLogging::`vftable';
        qword_18007F8A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
        v7 = (_QWORD *)qword_18007F8A0;
        qword_18007F890 = qword_18007F8A0;
        byte_18007F898 = 1;
        v52 = *(_OWORD *)(*(_QWORD *)(qword_18007F8A0 + 8) - 16LL);
        if ( *(_QWORD *)(qword_18007F8A0 + 32) )
          __fastfail(5u);
        *(_QWORD *)(qword_18007F8A0 + 40) = 0;
        v7[6] = 0;
        if ( !(unsigned int)EtwEventRegister(&v52, tlgEnableCallback, v7, v7 + 4) )
          EtwEventSetInformation(v7[4], 2, v7[1], *(unsigned __int16 *)v7[1]);
        dword_18007F89C = 1;
        (*(void (__fastcall **)(__int64 *))(qword_18007F888 + 8))(&qword_18007F888);
        InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_18007F888);
      }
      Ptr = SRWLock[1].Ptr;
      if ( *(_DWORD *)Ptr > 4u )
      {
        v9 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
        fPending = v4[17];
        v46 = v4[4];
        v10 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
        v11 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v47 = v4[26];
        v12 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
        v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v48 = v4[20];
        v14 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v49 = v4[8];
        v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
        v50 = *v4;
        v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        LODWORD(v43) = v4[16];
        v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(v44) = v4[2];
        v51 = (PSRWLOCK)0x1000000;
        v45 = (PSRWLOCK)0x1000000;
        v18 = *((_QWORD *)this + 34);
        v19 = -1;
        if ( v9 )
        {
          v20 = -1;
          do
            ++v20;
          while ( *((_BYTE *)v9 + v20) );
          v21 = v20 + 1;
        }
        else
        {
          v9 = &word_180061D6E;
          v21 = 1;
        }
        v113 = v9;
        v114 = v21;
        v115 = 0;
        p_fPending = &fPending;
        v112 = 4;
        v109 = &v46;
        v110 = 4;
        if ( v10 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v10[v22] );
          v23 = 2 * v22 + 2;
        }
        else
        {
          v10 = &qword_180061CC0;
          v23 = 2;
        }
        v106 = v10;
        v107 = v23;
        v108 = 0;
        if ( v11 )
        {
          v24 = -1;
          do
            ++v24;
          while ( *((_BYTE *)v11 + v24) );
          v25 = v24 + 1;
        }
        else
        {
          v11 = &word_180061D6E;
          v25 = 1;
        }
        v103 = v11;
        v104 = v25;
        v105 = 0;
        v101 = &v47;
        v102 = 4;
        if ( v12 )
        {
          v26 = -1;
          do
            ++v26;
          while ( v12[v26] );
          v27 = 2 * v26 + 2;
        }
        else
        {
          v12 = &qword_180061CC0;
          v27 = 2;
        }
        v98 = v12;
        v99 = v27;
        v100 = 0;
        if ( v13 )
        {
          v28 = -1;
          do
            ++v28;
          while ( *((_BYTE *)v13 + v28) );
          v29 = v28 + 1;
        }
        else
        {
          v13 = &word_180061D6E;
          v29 = 1;
        }
        v95 = v13;
        v96 = v29;
        v97 = 0;
        v93 = &v48;
        v94 = 4;
        if ( v14 )
        {
          v30 = -1;
          do
            ++v30;
          while ( *((_BYTE *)v14 + v30) );
          v31 = v30 + 1;
        }
        else
        {
          v14 = &word_180061D6E;
          v31 = 1;
        }
        v90 = v14;
        v91 = v31;
        v92 = 0;
        v88 = &v49;
        v89 = 4;
        if ( v15 )
        {
          v32 = -1;
          do
            ++v32;
          while ( v15[v32] );
          v33 = 2 * v32 + 2;
        }
        else
        {
          v15 = &qword_180061CC0;
          v33 = 2;
        }
        v85 = v15;
        v86 = v33;
        v87 = 0;
        v83 = &v50;
        v84 = 4;
        if ( v16 )
        {
          v34 = -1;
          do
            ++v34;
          while ( *((_BYTE *)v16 + v34) );
          v35 = v34 + 1;
        }
        else
        {
          v16 = &word_180061D6E;
          v35 = 1;
        }
        v80 = v16;
        v81 = v35;
        v82 = 0;
        v78 = &v43;
        v79 = 4;
        if ( v17 )
        {
          do
            ++v19;
          while ( *((_BYTE *)v17 + v19) );
          v36 = v19 + 1;
        }
        else
        {
          v17 = &word_180061D6E;
          v36 = 1;
        }
        v75 = v17;
        v76 = v36;
        v77 = 0;
        v73 = &v44;
        v74 = 4;
        v71 = &v51;
        v72 = 8;
        v69 = &v45;
        v70 = 8;
        v52 = 0x2040B000000uLL;
        v64 = (unsigned __int16 *)Ptr[1];
        v65 = *v64;
        v66 = 2;
        v67 = &word_18006FB4E;
        v68 = 0x100000142LL;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(Ptr[4], &v52, v18 + 8, 0, 21, &v64, fPending, SRWLock, v43);
      }
      goto LABEL_75;
    }
  }
  else
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  }
  if ( v5 )
  {
    v37 = v5 + 33;
    AcquireSRWLockExclusive(v37);
    v45 = 0;
    **((_DWORD **)this + 34) = 2;
    if ( v37 )
      ReleaseSRWLockExclusive(v37);
  }
  else
  {
    v51 = 0;
    **((_DWORD **)this + 34) = 2;
  }
  SRWLock = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`ProfileLogging::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock) && fPending )
  {
    SRWLock = (PSRWLOCK)&qword_18007F888;
    qword_18007F890 = 0;
    byte_18007F898 = 0;
    dword_18007F89C = 0;
    qword_18007F888 = (__int64)&ProfileLogging::`vftable';
    qword_18007F8A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
    v38 = (_QWORD *)qword_18007F8A0;
    qword_18007F890 = qword_18007F8A0;
    byte_18007F898 = 1;
    v52 = *(_OWORD *)(*(_QWORD *)(qword_18007F8A0 + 8) - 16LL);
    if ( *(_QWORD *)(qword_18007F8A0 + 32) )
      __fastfail(5u);
    *(_QWORD *)(qword_18007F8A0 + 40) = 0;
    v38[6] = 0;
    if ( !(unsigned int)EtwEventRegister(&v52, tlgEnableCallback, v38, v38 + 4) )
      EtwEventSetInformation(v38[4], 2, v38[1], *(unsigned __int16 *)v38[1]);
    dword_18007F89C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18007F888 + 8))(&qword_18007F888);
    InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_18007F888);
  }
  v39 = SRWLock[1].Ptr;
  if ( *(_DWORD *)v39 > 4u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v40 = *((_QWORD *)this + 34);
    LODWORD(v44) = *(_DWORD *)(v40 + 72);
    v45 = (PSRWLOCK)0x1000000;
    p_SRWLock = &SRWLock;
    v63 = 4;
    v60 = &v44;
    v61 = 4;
    v58 = &v45;
    v59 = 8;
    v52 = 0x2040B000000uLL;
    v53 = (unsigned __int16 *)v39[1];
    v54 = *v53;
    v55 = 2;
    v56 = word_18006FAFA;
    v57 = 0x100000048LL;
    LODWORD(v43) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(v39[4], &v52, v40 + 8, 0, 5, &v53, fPending, SRWLock, v43);
  }
LABEL_75:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ProfileTelemetry::CUserProfile_Unload *)((char *)this + 288));
}

```

## disassembly

```asm
0x180029980  push    rbp
0x180029982  push    rbx
0x180029983  push    rsi
0x180029984  push    rdi
0x180029985  push    r12
0x180029987  push    r13
0x180029989  push    r14
0x18002998b  push    r15
0x18002998d  lea     rbp, [rsp-148h]
0x180029995  sub     rsp, 248h
0x18002999c  mov     rax, cs:__security_cookie
0x1800299a3  xor     rax, rsp
0x1800299a6  mov     [rbp+180h+var_50], rax
0x1800299ad  mov     r14, rcx
0x1800299b0  xor     r12d, r12d
0x1800299b3  mov     rdi, [rcx+110h]
0x1800299ba  mov     eax, [rdi+48h]
0x1800299bd  test    eax, eax
0x1800299bf  jns     loc_180029F31
0x1800299c5  add     rdi, 50h ; 'P'
0x1800299c9  cmp     eax, [rdi+8]
0x1800299cc  jnz     loc_180029F31
0x1800299d2  mov     rbx, [rcx+118h]
0x1800299d9  test    rdi, rdi
0x1800299dc  jz      loc_180029F38
0x1800299e2  test    rbx, rbx
0x1800299e5  jz      short loc_180029A2C
0x1800299e7  add     rbx, 108h
0x1800299ee  mov     rcx, rbx; SRWLock
0x1800299f1  call    cs:__imp_AcquireSRWLockExclusive
0x1800299f7  lea     rax, [rsp+280h+SRWLock]
0x1800299fc  mov     [rax], r12
0x1800299ff  mov     rcx, [rsp+280h+SRWLock]; SRWLock
0x180029a04  test    rcx, rcx
0x180029a07  jz      short loc_180029A0F
0x180029a09  call    cs:__imp_ReleaseSRWLockExclusive
0x180029a0f  mov     rax, [r14+110h]
0x180029a16  mov     dword ptr [rax], 2
0x180029a1c  test    rbx, rbx
0x180029a1f  jz      short loc_180029A51
0x180029a21  mov     rcx, rbx; SRWLock
0x180029a24  call    cs:__imp_ReleaseSRWLockExclusive
0x180029a2a  jmp     short loc_180029A51
0x180029a2c  lea     rax, [rsp+280h+var_238]
0x180029a31  mov     [rax], r12
0x180029a34  mov     rcx, [rsp+280h+var_238]; SRWLock
0x180029a39  test    rcx, rcx
0x180029a3c  jz      short loc_180029A44
0x180029a3e  call    cs:__imp_ReleaseSRWLockExclusive
0x180029a44  mov     rax, [r14+110h]
0x180029a4b  mov     dword ptr [rax], 2
0x180029a51  mov     [rsp+280h+SRWLock], r12
0x180029a56  mov     [rsp+280h+fPending], r12d
0x180029a5b  lea     r9, [rsp+280h+SRWLock]; lpContext
0x180029a60  lea     r8, [rsp+280h+fPending]; fPending
0x180029a65  xor     edx, edx; dwFlags
0x180029a67  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x180029a6e  call    cs:__imp_InitOnceBeginInitialize
0x180029a74  test    eax, eax
0x180029a76  jz      loc_180029B6A
0x180029a7c  cmp     [rsp+280h+fPending], r12d
0x180029a81  jz      loc_180029B6A
0x180029a87  lea     rsi, qword_18007F888
0x180029a8e  mov     [rsp+280h+SRWLock], rsi
0x180029a93  mov     cs:qword_18007F890, r12
0x180029a9a  mov     cs:byte_18007F898, r12b
0x180029aa1  mov     cs:dword_18007F89C, r12d
0x180029aa8  lea     rax, ??_7ProfileLogging@@6B@
0x180029aaf  mov     cs:qword_18007F888, rax
0x180029ab6  lea     rax, ?__hInner@?1???0StaticHandle@ProfileLogging@@QEAA@XZ@4U_tlgProvider_t@@A
0x180029abd  mov     cs:qword_18007F8A0, rax
0x180029ac4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cff094b7b3eb7b3291eb3a07719b48ba_@@CA@XZ; void (__cdecl *)()
0x180029acb  call    atexit
0x180029ad0  mov     rbx, cs:qword_18007F8A0
0x180029ad7  mov     cs:qword_18007F890, rbx
0x180029ade  mov     cs:byte_18007F898, 1
0x180029ae5  mov     rax, [rbx+8]
0x180029ae9  movups  xmm0, xmmword ptr [rax-10h]
0x180029aed  movups  [rsp+280h+var_208], xmm0
0x180029af2  cmp     [rbx+20h], r12
0x180029af6  jz      short loc_180029AFF
0x180029af8  mov     ecx, 5
0x180029afd  int     29h; Win8: RtlFailFast(ecx)
0x180029aff  mov     [rbx+28h], r12
0x180029b03  mov     [rbx+30h], r12
0x180029b07  lea     r9, [rbx+20h]
0x180029b0b  mov     r8, rbx
0x180029b0e  lea     rdx, _tlgEnableCallback
0x180029b15  lea     rcx, [rsp+280h+var_208]
0x180029b1a  call    cs:__imp_EtwEventRegister
0x180029b20  test    eax, eax
0x180029b22  jnz     short loc_180029B3B
0x180029b24  mov     r8, [rbx+8]
0x180029b28  movzx   r9d, word ptr [r8]
0x180029b2c  mov     edx, 2
0x180029b31  mov     rcx, [rbx+20h]
0x180029b35  call    cs:__imp_EtwEventSetInformation
0x180029b3b  mov     cs:dword_18007F89C, 1
0x180029b45  mov     rax, cs:qword_18007F888
0x180029b4c  mov     rcx, rsi
0x180029b4f  mov     rax, [rax+8]
0x180029b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b58  mov     r8, rsi; lpContext
0x180029b5b  xor     edx, edx; dwFlags
0x180029b5d  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x180029b64  call    cs:__imp_InitOnceComplete
0x180029b6a  mov     rax, [rsp+280h+SRWLock]
0x180029b6f  mov     r13, [rax+8]
0x180029b73  mov     eax, [r13+0]
0x180029b77  cmp     eax, 4
0x180029b7a  jbe     loc_18002A1AE
0x180029b80  mov     rdx, [rdi+30h]
0x180029b84  mov     eax, [rdi+44h]
0x180029b87  mov     [rsp+280h+fPending], eax
0x180029b8b  mov     eax, [rdi+10h]
0x180029b8e  mov     [rsp+280h+var_228], eax
0x180029b92  mov     r8, [rdi+78h]
0x180029b96  mov     r9, [rdi+70h]
0x180029b9a  mov     eax, [rdi+68h]
0x180029b9d  mov     [rsp+280h+var_224], eax
0x180029ba1  mov     r10, [rdi+60h]
0x180029ba5  mov     r11, [rdi+58h]
0x180029ba9  mov     eax, [rdi+50h]
0x180029bac  mov     [rsp+280h+var_220], eax
0x180029bb0  mov     rbx, [rdi+48h]
0x180029bb4  mov     eax, [rdi+20h]
0x180029bb7  mov     [rsp+280h+var_21C], eax
0x180029bbb  mov     rsi, [rdi+18h]
0x180029bbf  mov     eax, [rdi]
0x180029bc1  mov     [rsp+280h+var_218], eax
0x180029bc5  mov     r15, [rdi+80h]
0x180029bcc  mov     eax, [rdi+40h]
0x180029bcf  mov     dword ptr [rsp+280h+var_240], eax
0x180029bd3  mov     r12, [rdi+38h]
0x180029bd7  mov     eax, [rdi+8]
0x180029bda  mov     dword ptr [rsp+280h+var_238], eax
0x180029bde  mov     [rsp+280h+var_210], 1000000h
0x180029be7  mov     [rsp+280h+var_230], 1000000h
0x180029bf0  mov     rdi, [r14+110h]
0x180029bf7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180029bfe  test    rdx, rdx
0x180029c01  jz      short loc_180029C13
0x180029c03  mov     rax, rcx
0x180029c06  inc     rax
0x180029c09  cmp     byte ptr [rdx+rax], 0
0x180029c0d  jnz     short loc_180029C06
0x180029c0f  inc     eax
0x180029c11  jmp     short loc_180029C1F
0x180029c13  lea     rdx, word_180061D6E
0x180029c1a  mov     eax, 1
0x180029c1f  mov     [rbp+180h+var_60], rdx
0x180029c26  mov     [rbp+180h+var_58], eax
0x180029c2c  xor     edx, edx
0x180029c2e  mov     [rbp+180h+var_54], edx
0x180029c34  lea     rax, [rsp+280h+fPending]
0x180029c39  mov     [rbp+180h+var_70], rax
0x180029c40  mov     [rbp+180h+var_68], 4
0x180029c4b  lea     rax, [rsp+280h+var_228]
0x180029c50  mov     [rbp+180h+var_80], rax
0x180029c57  mov     [rbp+180h+var_78], 4
0x180029c62  test    r8, r8
0x180029c65  jz      short loc_180029C84
0x180029c67  mov     rax, rcx
0x180029c6a  nop     word ptr [rax+rax+00h]
0x180029c70  lea     rax, [rax+1]
0x180029c74  cmp     [r8+rax*2], dx
0x180029c79  jnz     short loc_180029C70
0x180029c7b  lea     eax, ds:2[rax*2]
0x180029c82  jmp     short loc_180029C90
0x180029c84  lea     r8, qword_180061CC0
0x180029c8b  mov     eax, 2
0x180029c90  mov     [rbp+180h+var_90], r8
0x180029c97  mov     [rbp+180h+var_88], eax
0x180029c9d  mov     [rbp+180h+var_84], edx
0x180029ca3  test    r9, r9
0x180029ca6  jz      short loc_180029CBD
0x180029ca8  mov     rax, rcx
0x180029cab  nop     dword ptr [rax+rax+00h]
0x180029cb0  inc     rax
0x180029cb3  cmp     [r9+rax], dl
0x180029cb7  jnz     short loc_180029CB0
0x180029cb9  inc     eax
0x180029cbb  jmp     short loc_180029CC9
0x180029cbd  lea     r9, word_180061D6E
0x180029cc4  mov     eax, 1
0x180029cc9  mov     [rbp+180h+var_A0], r9
0x180029cd0  mov     [rbp+180h+var_98], eax
0x180029cd6  mov     [rbp+180h+var_94], edx
0x180029cdc  lea     rax, [rsp+280h+var_224]
0x180029ce1  mov     [rbp+180h+var_B0], rax
0x180029ce8  mov     [rbp+180h+var_A8], 4
0x180029cf3  test    r10, r10
0x180029cf6  jz      short loc_180029D14
0x180029cf8  mov     rax, rcx
0x180029cfb  nop     dword ptr [rax+rax+00h]
0x180029d00  lea     rax, [rax+1]
0x180029d04  cmp     [r10+rax*2], dx
0x180029d09  jnz     short loc_180029D00
0x180029d0b  lea     eax, ds:2[rax*2]
0x180029d12  jmp     short loc_180029D20
0x180029d14  lea     r10, qword_180061CC0
0x180029d1b  mov     eax, 2
0x180029d20  mov     [rbp+180h+var_C0], r10
0x180029d27  mov     [rbp+180h+var_B8], eax
0x180029d2d  mov     [rbp+180h+var_B4], edx
0x180029d33  test    r11, r11
0x180029d36  jz      short loc_180029D4D
0x180029d38  mov     rax, rcx
0x180029d3b  nop     dword ptr [rax+rax+00h]
0x180029d40  inc     rax
0x180029d43  cmp     [r11+rax], dl
0x180029d47  jnz     short loc_180029D40
0x180029d49  inc     eax
0x180029d4b  jmp     short loc_180029D59
0x180029d4d  lea     r11, word_180061D6E
0x180029d54  mov     eax, 1
0x180029d59  mov     [rbp+180h+var_D0], r11
0x180029d60  mov     [rbp+180h+var_C8], eax
0x180029d66  mov     [rbp+180h+var_C4], edx
0x180029d6c  lea     rax, [rsp+280h+var_220]
0x180029d71  mov     [rbp+180h+var_E0], rax
0x180029d78  mov     [rbp+180h+var_D8], 4
0x180029d83  test    rbx, rbx
0x180029d86  jz      short loc_180029D9C
0x180029d88  mov     rax, rcx
0x180029d8b  nop     dword ptr [rax+rax+00h]
0x180029d90  inc     rax
0x180029d93  cmp     [rbx+rax], dl
0x180029d96  jnz     short loc_180029D90
0x180029d98  inc     eax
0x180029d9a  jmp     short loc_180029DA8
0x180029d9c  lea     rbx, word_180061D6E
0x180029da3  mov     eax, 1
0x180029da8  mov     [rbp+180h+var_F0], rbx
0x180029daf  mov     [rbp+180h+var_E8], eax
0x180029db5  mov     [rbp+180h+var_E4], edx
0x180029dbb  lea     rax, [rsp+280h+var_21C]
0x180029dc0  mov     [rbp+180h+var_100], rax
0x180029dc7  mov     [rbp+180h+var_F8], 4
0x180029dd2  test    rsi, rsi
0x180029dd5  jz      short loc_180029DF3
0x180029dd7  mov     rax, rcx
0x180029dda  nop     word ptr [rax+rax+00h]
0x180029de0  lea     rax, [rax+1]
0x180029de4  cmp     [rsi+rax*2], dx
0x180029de8  jnz     short loc_180029DE0
0x180029dea  lea     eax, ds:2[rax*2]
0x180029df1  jmp     short loc_180029DFF
0x180029df3  lea     rsi, qword_180061CC0
0x180029dfa  mov     eax, 2
0x180029dff  mov     [rbp+180h+var_110], rsi
0x180029e03  mov     [rbp+180h+var_108], eax
0x180029e06  mov     [rbp+180h+var_104], edx
0x180029e09  lea     rax, [rsp+280h+var_218]
0x180029e0e  mov     [rbp+180h+var_120], rax
0x180029e12  mov     [rbp+180h+var_118], 4
0x180029e1a  test    r15, r15
0x180029e1d  jz      short loc_180029E2F
0x180029e1f  mov     rax, rcx
0x180029e22  inc     rax
0x180029e25  cmp     [r15+rax], dl
0x180029e29  jnz     short loc_180029E22
0x180029e2b  inc     eax
0x180029e2d  jmp     short loc_180029E3B
0x180029e2f  lea     r15, word_180061D6E
0x180029e36  mov     eax, 1
0x180029e3b  mov     [rbp+180h+var_130], r15
0x180029e3f  mov     [rbp+180h+var_128], eax
0x180029e42  mov     [rbp+180h+var_124], edx
0x180029e45  lea     rax, [rsp+280h+var_240]
0x180029e4a  mov     [rbp+180h+var_140], rax
0x180029e4e  mov     [rbp+180h+var_138], 4
0x180029e56  test    r12, r12
0x180029e59  jz      short loc_180029E6D
0x180029e5b  nop     dword ptr [rax+rax+00h]
0x180029e60  inc     rcx
0x180029e63  cmp     [r12+rcx], dl
0x180029e67  jnz     short loc_180029E60
0x180029e69  inc     ecx
0x180029e6b  jmp     short loc_180029E79
0x180029e6d  lea     r12, word_180061D6E
0x180029e74  mov     ecx, 1
0x180029e79  mov     [rbp+180h+var_150], r12
0x180029e7d  mov     [rbp+180h+var_148], ecx
0x180029e80  mov     [rbp+180h+var_144], edx
0x180029e83  lea     rax, [rsp+280h+var_238]
0x180029e88  mov     [rbp+180h+var_160], rax
0x180029e8c  mov     [rbp+180h+var_158], 4
0x180029e94  lea     rax, [rsp+280h+var_210]
0x180029e99  mov     [rbp+180h+var_170], rax
0x180029e9d  mov     [rbp+180h+var_168], 8
0x180029ea5  lea     rax, [rsp+280h+var_230]
0x180029eaa  mov     [rbp+180h+var_180], rax
0x180029eae  mov     [rbp+180h+var_178], 8
0x180029eb6  mov     dword ptr [rsp+280h+var_208], 0B000000h
0x180029ebe  movzx   eax, cs:word_18006FB44
0x180029ec5  mov     dword ptr [rsp+280h+var_208+4], eax
0x180029ec9  mov     qword ptr [rbp+180h+var_208+8], rdx
0x180029ecd  mov     rax, [r13+8]
0x180029ed1  mov     [rbp+180h+var_1A0], rax
  ... truncated ...
```

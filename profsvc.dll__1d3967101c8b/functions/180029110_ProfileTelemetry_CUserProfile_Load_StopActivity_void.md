# ProfileTelemetry::CUserProfile_Load::StopActivity(void)

- ea: `0x180029110`
- end: `0x180029974`
- name: `?StopActivity@CUserProfile_Load@ProfileTelemetry@@MEAAXXZ`
- size: `2148`
- prototype: `void __fastcall(ProfileTelemetry::CUserProfile_Load *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180029110`
- `0x180035fe0`
- `0x18003a730`
- `0x18003aae0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029181`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800296d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029181`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800296d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029199`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800291b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800291ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800296ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002970a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029724`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029199`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800291b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800291ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800296ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002970a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029724`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029864`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029864`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800291fe`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180029754`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800291fe`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180029754`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800292f4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002984a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800292f4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002984a`
- `ntdll!EtwEventWriteTransfer` at `0x180029937`
- `ntdll!EtwEventWriteTransfer` at `0x180029937`
- `ntdll!EtwEventSetInformation` at `0x1800292c5`
- `ntdll!EtwEventSetInformation` at `0x18002981b`
- `ntdll!EtwEventSetInformation` at `0x1800292c5`
- `ntdll!EtwEventSetInformation` at `0x18002981b`
- `ntdll!EtwEventRegister` at `0x1800292aa`
- `ntdll!EtwEventRegister` at `0x180029800`
- `ntdll!EtwEventRegister` at `0x1800292aa`
- `ntdll!EtwEventRegister` at `0x180029800`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ProfileTelemetry::CUserProfile_Load::StopActivity(ProfileTelemetry::CUserProfile_Load *this)
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
  void *v67; // [rsp+F0h] [rbp-10h]
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
        v67 = &unk_18006FF60;
        v68 = 0x100000140LL;
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
    v56 = &word_18006FF0E;
    v57 = 0x100000046LL;
    LODWORD(v43) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(v39[4], &v52, v40 + 8, 0, 5, &v53, fPending, SRWLock, v43);
  }
LABEL_75:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ProfileTelemetry::CUserProfile_Load *)((char *)this + 288));
}

```

## disassembly

```asm
0x180029110  push    rbp
0x180029112  push    rbx
0x180029113  push    rsi
0x180029114  push    rdi
0x180029115  push    r12
0x180029117  push    r13
0x180029119  push    r14
0x18002911b  push    r15
0x18002911d  lea     rbp, [rsp-148h]
0x180029125  sub     rsp, 248h
0x18002912c  mov     rax, cs:__security_cookie
0x180029133  xor     rax, rsp
0x180029136  mov     [rbp+180h+var_50], rax
0x18002913d  mov     r14, rcx
0x180029140  xor     r12d, r12d
0x180029143  mov     rdi, [rcx+110h]
0x18002914a  mov     eax, [rdi+48h]
0x18002914d  test    eax, eax
0x18002914f  jns     loc_1800296C1
0x180029155  add     rdi, 50h ; 'P'
0x180029159  cmp     eax, [rdi+8]
0x18002915c  jnz     loc_1800296C1
0x180029162  mov     rbx, [rcx+118h]
0x180029169  test    rdi, rdi
0x18002916c  jz      loc_1800296C8
0x180029172  test    rbx, rbx
0x180029175  jz      short loc_1800291BC
0x180029177  add     rbx, 108h
0x18002917e  mov     rcx, rbx; SRWLock
0x180029181  call    cs:__imp_AcquireSRWLockExclusive
0x180029187  lea     rax, [rsp+280h+SRWLock]
0x18002918c  mov     [rax], r12
0x18002918f  mov     rcx, [rsp+280h+SRWLock]; SRWLock
0x180029194  test    rcx, rcx
0x180029197  jz      short loc_18002919F
0x180029199  call    cs:__imp_ReleaseSRWLockExclusive
0x18002919f  mov     rax, [r14+110h]
0x1800291a6  mov     dword ptr [rax], 2
0x1800291ac  test    rbx, rbx
0x1800291af  jz      short loc_1800291E1
0x1800291b1  mov     rcx, rbx; SRWLock
0x1800291b4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800291ba  jmp     short loc_1800291E1
0x1800291bc  lea     rax, [rsp+280h+var_238]
0x1800291c1  mov     [rax], r12
0x1800291c4  mov     rcx, [rsp+280h+var_238]; SRWLock
0x1800291c9  test    rcx, rcx
0x1800291cc  jz      short loc_1800291D4
0x1800291ce  call    cs:__imp_ReleaseSRWLockExclusive
0x1800291d4  mov     rax, [r14+110h]
0x1800291db  mov     dword ptr [rax], 2
0x1800291e1  mov     [rsp+280h+SRWLock], r12
0x1800291e6  mov     [rsp+280h+fPending], r12d
0x1800291eb  lea     r9, [rsp+280h+SRWLock]; lpContext
0x1800291f0  lea     r8, [rsp+280h+fPending]; fPending
0x1800291f5  xor     edx, edx; dwFlags
0x1800291f7  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x1800291fe  call    cs:__imp_InitOnceBeginInitialize
0x180029204  test    eax, eax
0x180029206  jz      loc_1800292FA
0x18002920c  cmp     [rsp+280h+fPending], r12d
0x180029211  jz      loc_1800292FA
0x180029217  lea     rsi, qword_18007F888
0x18002921e  mov     [rsp+280h+SRWLock], rsi
0x180029223  mov     cs:qword_18007F890, r12
0x18002922a  mov     cs:byte_18007F898, r12b
0x180029231  mov     cs:dword_18007F89C, r12d
0x180029238  lea     rax, ??_7ProfileLogging@@6B@
0x18002923f  mov     cs:qword_18007F888, rax
0x180029246  lea     rax, ?__hInner@?1???0StaticHandle@ProfileLogging@@QEAA@XZ@4U_tlgProvider_t@@A
0x18002924d  mov     cs:qword_18007F8A0, rax
0x180029254  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cff094b7b3eb7b3291eb3a07719b48ba_@@CA@XZ; void (__cdecl *)()
0x18002925b  call    atexit
0x180029260  mov     rbx, cs:qword_18007F8A0
0x180029267  mov     cs:qword_18007F890, rbx
0x18002926e  mov     cs:byte_18007F898, 1
0x180029275  mov     rax, [rbx+8]
0x180029279  movups  xmm0, xmmword ptr [rax-10h]
0x18002927d  movups  [rsp+280h+var_208], xmm0
0x180029282  cmp     [rbx+20h], r12
0x180029286  jz      short loc_18002928F
0x180029288  mov     ecx, 5
0x18002928d  int     29h; Win8: RtlFailFast(ecx)
0x18002928f  mov     [rbx+28h], r12
0x180029293  mov     [rbx+30h], r12
0x180029297  lea     r9, [rbx+20h]
0x18002929b  mov     r8, rbx
0x18002929e  lea     rdx, _tlgEnableCallback
0x1800292a5  lea     rcx, [rsp+280h+var_208]
0x1800292aa  call    cs:__imp_EtwEventRegister
0x1800292b0  test    eax, eax
0x1800292b2  jnz     short loc_1800292CB
0x1800292b4  mov     r8, [rbx+8]
0x1800292b8  movzx   r9d, word ptr [r8]
0x1800292bc  mov     edx, 2
0x1800292c1  mov     rcx, [rbx+20h]
0x1800292c5  call    cs:__imp_EtwEventSetInformation
0x1800292cb  mov     cs:dword_18007F89C, 1
0x1800292d5  mov     rax, cs:qword_18007F888
0x1800292dc  mov     rcx, rsi
0x1800292df  mov     rax, [rax+8]
0x1800292e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292e8  mov     r8, rsi; lpContext
0x1800292eb  xor     edx, edx; dwFlags
0x1800292ed  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x1800292f4  call    cs:__imp_InitOnceComplete
0x1800292fa  mov     rax, [rsp+280h+SRWLock]
0x1800292ff  mov     r13, [rax+8]
0x180029303  mov     eax, [r13+0]
0x180029307  cmp     eax, 4
0x18002930a  jbe     loc_18002993E
0x180029310  mov     rdx, [rdi+30h]
0x180029314  mov     eax, [rdi+44h]
0x180029317  mov     [rsp+280h+fPending], eax
0x18002931b  mov     eax, [rdi+10h]
0x18002931e  mov     [rsp+280h+var_228], eax
0x180029322  mov     r8, [rdi+78h]
0x180029326  mov     r9, [rdi+70h]
0x18002932a  mov     eax, [rdi+68h]
0x18002932d  mov     [rsp+280h+var_224], eax
0x180029331  mov     r10, [rdi+60h]
0x180029335  mov     r11, [rdi+58h]
0x180029339  mov     eax, [rdi+50h]
0x18002933c  mov     [rsp+280h+var_220], eax
0x180029340  mov     rbx, [rdi+48h]
0x180029344  mov     eax, [rdi+20h]
0x180029347  mov     [rsp+280h+var_21C], eax
0x18002934b  mov     rsi, [rdi+18h]
0x18002934f  mov     eax, [rdi]
0x180029351  mov     [rsp+280h+var_218], eax
0x180029355  mov     r15, [rdi+80h]
0x18002935c  mov     eax, [rdi+40h]
0x18002935f  mov     dword ptr [rsp+280h+var_240], eax
0x180029363  mov     r12, [rdi+38h]
0x180029367  mov     eax, [rdi+8]
0x18002936a  mov     dword ptr [rsp+280h+var_238], eax
0x18002936e  mov     [rsp+280h+var_210], 1000000h
0x180029377  mov     [rsp+280h+var_230], 1000000h
0x180029380  mov     rdi, [r14+110h]
0x180029387  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002938e  test    rdx, rdx
0x180029391  jz      short loc_1800293A3
0x180029393  mov     rax, rcx
0x180029396  inc     rax
0x180029399  cmp     byte ptr [rdx+rax], 0
0x18002939d  jnz     short loc_180029396
0x18002939f  inc     eax
0x1800293a1  jmp     short loc_1800293AF
0x1800293a3  lea     rdx, word_180061D6E
0x1800293aa  mov     eax, 1
0x1800293af  mov     [rbp+180h+var_60], rdx
0x1800293b6  mov     [rbp+180h+var_58], eax
0x1800293bc  xor     edx, edx
0x1800293be  mov     [rbp+180h+var_54], edx
0x1800293c4  lea     rax, [rsp+280h+fPending]
0x1800293c9  mov     [rbp+180h+var_70], rax
0x1800293d0  mov     [rbp+180h+var_68], 4
0x1800293db  lea     rax, [rsp+280h+var_228]
0x1800293e0  mov     [rbp+180h+var_80], rax
0x1800293e7  mov     [rbp+180h+var_78], 4
0x1800293f2  test    r8, r8
0x1800293f5  jz      short loc_180029414
0x1800293f7  mov     rax, rcx
0x1800293fa  nop     word ptr [rax+rax+00h]
0x180029400  lea     rax, [rax+1]
0x180029404  cmp     [r8+rax*2], dx
0x180029409  jnz     short loc_180029400
0x18002940b  lea     eax, ds:2[rax*2]
0x180029412  jmp     short loc_180029420
0x180029414  lea     r8, qword_180061CC0
0x18002941b  mov     eax, 2
0x180029420  mov     [rbp+180h+var_90], r8
0x180029427  mov     [rbp+180h+var_88], eax
0x18002942d  mov     [rbp+180h+var_84], edx
0x180029433  test    r9, r9
0x180029436  jz      short loc_18002944D
0x180029438  mov     rax, rcx
0x18002943b  nop     dword ptr [rax+rax+00h]
0x180029440  inc     rax
0x180029443  cmp     [r9+rax], dl
0x180029447  jnz     short loc_180029440
0x180029449  inc     eax
0x18002944b  jmp     short loc_180029459
0x18002944d  lea     r9, word_180061D6E
0x180029454  mov     eax, 1
0x180029459  mov     [rbp+180h+var_A0], r9
0x180029460  mov     [rbp+180h+var_98], eax
0x180029466  mov     [rbp+180h+var_94], edx
0x18002946c  lea     rax, [rsp+280h+var_224]
0x180029471  mov     [rbp+180h+var_B0], rax
0x180029478  mov     [rbp+180h+var_A8], 4
0x180029483  test    r10, r10
0x180029486  jz      short loc_1800294A4
0x180029488  mov     rax, rcx
0x18002948b  nop     dword ptr [rax+rax+00h]
0x180029490  lea     rax, [rax+1]
0x180029494  cmp     [r10+rax*2], dx
0x180029499  jnz     short loc_180029490
0x18002949b  lea     eax, ds:2[rax*2]
0x1800294a2  jmp     short loc_1800294B0
0x1800294a4  lea     r10, qword_180061CC0
0x1800294ab  mov     eax, 2
0x1800294b0  mov     [rbp+180h+var_C0], r10
0x1800294b7  mov     [rbp+180h+var_B8], eax
0x1800294bd  mov     [rbp+180h+var_B4], edx
0x1800294c3  test    r11, r11
0x1800294c6  jz      short loc_1800294DD
0x1800294c8  mov     rax, rcx
0x1800294cb  nop     dword ptr [rax+rax+00h]
0x1800294d0  inc     rax
0x1800294d3  cmp     [r11+rax], dl
0x1800294d7  jnz     short loc_1800294D0
0x1800294d9  inc     eax
0x1800294db  jmp     short loc_1800294E9
0x1800294dd  lea     r11, word_180061D6E
0x1800294e4  mov     eax, 1
0x1800294e9  mov     [rbp+180h+var_D0], r11
0x1800294f0  mov     [rbp+180h+var_C8], eax
0x1800294f6  mov     [rbp+180h+var_C4], edx
0x1800294fc  lea     rax, [rsp+280h+var_220]
0x180029501  mov     [rbp+180h+var_E0], rax
0x180029508  mov     [rbp+180h+var_D8], 4
0x180029513  test    rbx, rbx
0x180029516  jz      short loc_18002952C
0x180029518  mov     rax, rcx
0x18002951b  nop     dword ptr [rax+rax+00h]
0x180029520  inc     rax
0x180029523  cmp     [rbx+rax], dl
0x180029526  jnz     short loc_180029520
0x180029528  inc     eax
0x18002952a  jmp     short loc_180029538
0x18002952c  lea     rbx, word_180061D6E
0x180029533  mov     eax, 1
0x180029538  mov     [rbp+180h+var_F0], rbx
0x18002953f  mov     [rbp+180h+var_E8], eax
0x180029545  mov     [rbp+180h+var_E4], edx
0x18002954b  lea     rax, [rsp+280h+var_21C]
0x180029550  mov     [rbp+180h+var_100], rax
0x180029557  mov     [rbp+180h+var_F8], 4
0x180029562  test    rsi, rsi
0x180029565  jz      short loc_180029583
0x180029567  mov     rax, rcx
0x18002956a  nop     word ptr [rax+rax+00h]
0x180029570  lea     rax, [rax+1]
0x180029574  cmp     [rsi+rax*2], dx
0x180029578  jnz     short loc_180029570
0x18002957a  lea     eax, ds:2[rax*2]
0x180029581  jmp     short loc_18002958F
0x180029583  lea     rsi, qword_180061CC0
0x18002958a  mov     eax, 2
0x18002958f  mov     [rbp+180h+var_110], rsi
0x180029593  mov     [rbp+180h+var_108], eax
0x180029596  mov     [rbp+180h+var_104], edx
0x180029599  lea     rax, [rsp+280h+var_218]
0x18002959e  mov     [rbp+180h+var_120], rax
0x1800295a2  mov     [rbp+180h+var_118], 4
0x1800295aa  test    r15, r15
0x1800295ad  jz      short loc_1800295BF
0x1800295af  mov     rax, rcx
0x1800295b2  inc     rax
0x1800295b5  cmp     [r15+rax], dl
0x1800295b9  jnz     short loc_1800295B2
0x1800295bb  inc     eax
0x1800295bd  jmp     short loc_1800295CB
0x1800295bf  lea     r15, word_180061D6E
0x1800295c6  mov     eax, 1
0x1800295cb  mov     [rbp+180h+var_130], r15
0x1800295cf  mov     [rbp+180h+var_128], eax
0x1800295d2  mov     [rbp+180h+var_124], edx
0x1800295d5  lea     rax, [rsp+280h+var_240]
0x1800295da  mov     [rbp+180h+var_140], rax
0x1800295de  mov     [rbp+180h+var_138], 4
0x1800295e6  test    r12, r12
0x1800295e9  jz      short loc_1800295FD
0x1800295eb  nop     dword ptr [rax+rax+00h]
0x1800295f0  inc     rcx
0x1800295f3  cmp     [r12+rcx], dl
0x1800295f7  jnz     short loc_1800295F0
0x1800295f9  inc     ecx
0x1800295fb  jmp     short loc_180029609
0x1800295fd  lea     r12, word_180061D6E
0x180029604  mov     ecx, 1
0x180029609  mov     [rbp+180h+var_150], r12
0x18002960d  mov     [rbp+180h+var_148], ecx
0x180029610  mov     [rbp+180h+var_144], edx
0x180029613  lea     rax, [rsp+280h+var_238]
0x180029618  mov     [rbp+180h+var_160], rax
0x18002961c  mov     [rbp+180h+var_158], 4
0x180029624  lea     rax, [rsp+280h+var_210]
0x180029629  mov     [rbp+180h+var_170], rax
0x18002962d  mov     [rbp+180h+var_168], 8
0x180029635  lea     rax, [rsp+280h+var_230]
0x18002963a  mov     [rbp+180h+var_180], rax
0x18002963e  mov     [rbp+180h+var_178], 8
0x180029646  mov     dword ptr [rsp+280h+var_208], 0B000000h
0x18002964e  movzx   eax, cs:word_18006FF56
0x180029655  mov     dword ptr [rsp+280h+var_208+4], eax
0x180029659  mov     qword ptr [rbp+180h+var_208+8], rdx
0x18002965d  mov     rax, [r13+8]
0x180029661  mov     [rbp+180h+var_1A0], rax
  ... truncated ...
```

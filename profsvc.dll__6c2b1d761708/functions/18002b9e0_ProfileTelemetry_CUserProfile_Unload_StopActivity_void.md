# ProfileTelemetry::CUserProfile_Unload::StopActivity(void)

- ea: `0x18002b9e0`
- end: `0x18002c2b1`
- name: `?StopActivity@CUserProfile_Unload@ProfileTelemetry@@MEAAXXZ`
- size: `2257`
- prototype: `void __fastcall(ProfileTelemetry::CUserProfile_Unload *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002b9e0`
- `0x18003657c`
- `0x18003bc70`
- `0x18003c020`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ba51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bfd7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ba51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bfd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ba6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ba90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bab0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bff5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c016`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c036`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ba6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ba90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bab0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bff5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c016`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c036`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c194`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c194`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002bae6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002c06c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002bae6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002c06c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002bbee`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002c174`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002bbee`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002c174`
- `ntdll!EtwEventWriteTransfer` at `0x18002c26d`
- `ntdll!EtwEventWriteTransfer` at `0x18002c26d`
- `ntdll!EtwEventSetInformation` at `0x18002bbb9`
- `ntdll!EtwEventSetInformation` at `0x18002c13f`
- `ntdll!EtwEventSetInformation` at `0x18002bbb9`
- `ntdll!EtwEventSetInformation` at `0x18002c13f`
- `ntdll!EtwEventRegister` at `0x18002bb98`
- `ntdll!EtwEventRegister` at `0x18002c11e`
- `ntdll!EtwEventRegister` at `0x18002bb98`
- `ntdll!EtwEventRegister` at `0x18002c11e`

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
  unsigned int v43; // [rsp+40h] [rbp-C0h] BYREF
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
  int v57; // [rsp+A8h] [rbp-58h]
  int v58; // [rsp+ACh] [rbp-54h]
  PSRWLOCK *v59; // [rsp+B0h] [rbp-50h]
  __int64 v60; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *v61; // [rsp+C0h] [rbp-40h]
  __int64 v62; // [rsp+C8h] [rbp-38h]
  PSRWLOCK *p_SRWLock; // [rsp+D0h] [rbp-30h]
  __int64 v64; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v65; // [rsp+E0h] [rbp-20h] BYREF
  int v66; // [rsp+E8h] [rbp-18h]
  int v67; // [rsp+ECh] [rbp-14h]
  __int16 *v68; // [rsp+F0h] [rbp-10h]
  int v69; // [rsp+F8h] [rbp-8h]
  int v70; // [rsp+FCh] [rbp-4h]
  PSRWLOCK *v71; // [rsp+100h] [rbp+0h]
  __int64 v72; // [rsp+108h] [rbp+8h]
  PSRWLOCK *v73; // [rsp+110h] [rbp+10h]
  __int64 v74; // [rsp+118h] [rbp+18h]
  PSRWLOCK *v75; // [rsp+120h] [rbp+20h]
  __int64 v76; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v77; // [rsp+130h] [rbp+30h]
  int v78; // [rsp+138h] [rbp+38h]
  int v79; // [rsp+13Ch] [rbp+3Ch]
  unsigned int *v80; // [rsp+140h] [rbp+40h]
  __int64 v81; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v82; // [rsp+150h] [rbp+50h]
  int v83; // [rsp+158h] [rbp+58h]
  int v84; // [rsp+15Ch] [rbp+5Ch]
  int *v85; // [rsp+160h] [rbp+60h]
  __int64 v86; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v87; // [rsp+170h] [rbp+70h]
  int v88; // [rsp+178h] [rbp+78h]
  int v89; // [rsp+17Ch] [rbp+7Ch]
  int *v90; // [rsp+180h] [rbp+80h]
  __int64 v91; // [rsp+188h] [rbp+88h]
  const unsigned __int16 *v92; // [rsp+190h] [rbp+90h]
  int v93; // [rsp+198h] [rbp+98h]
  int v94; // [rsp+19Ch] [rbp+9Ch]
  int *v95; // [rsp+1A0h] [rbp+A0h]
  __int64 v96; // [rsp+1A8h] [rbp+A8h]
  const unsigned __int16 *v97; // [rsp+1B0h] [rbp+B0h]
  int v98; // [rsp+1B8h] [rbp+B8h]
  int v99; // [rsp+1BCh] [rbp+BCh]
  const unsigned __int16 *v100; // [rsp+1C0h] [rbp+C0h]
  int v101; // [rsp+1C8h] [rbp+C8h]
  int v102; // [rsp+1CCh] [rbp+CCh]
  int *v103; // [rsp+1D0h] [rbp+D0h]
  __int64 v104; // [rsp+1D8h] [rbp+D8h]
  const unsigned __int16 *v105; // [rsp+1E0h] [rbp+E0h]
  int v106; // [rsp+1E8h] [rbp+E8h]
  int v107; // [rsp+1ECh] [rbp+ECh]
  const unsigned __int16 *v108; // [rsp+1F0h] [rbp+F0h]
  int v109; // [rsp+1F8h] [rbp+F8h]
  int v110; // [rsp+1FCh] [rbp+FCh]
  int *v111; // [rsp+200h] [rbp+100h]
  __int64 v112; // [rsp+208h] [rbp+108h]
  WINBOOL *p_fPending; // [rsp+210h] [rbp+110h]
  __int64 v114; // [rsp+218h] [rbp+118h]
  const unsigned __int16 *v115; // [rsp+220h] [rbp+120h]
  int v116; // [rsp+228h] [rbp+128h]
  int v117; // [rsp+22Ch] [rbp+12Ch]

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
        SRWLock = (PSRWLOCK)&qword_180082988;
        qword_180082990 = 0;
        byte_180082998 = 0;
        dword_18008299C = 0;
        qword_180082988 = (__int64)&ProfileLogging::`vftable';
        qword_1800829A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
        v7 = (_QWORD *)qword_1800829A0;
        qword_180082990 = qword_1800829A0;
        byte_180082998 = 1;
        v52 = *(_OWORD *)(*(_QWORD *)(qword_1800829A0 + 8) - 16LL);
        if ( *(_QWORD *)(qword_1800829A0 + 32) )
          __fastfail(5u);
        *(_QWORD *)(qword_1800829A0 + 40) = 0;
        v7[6] = 0;
        if ( !(unsigned int)EtwEventRegister(&v52, tlgEnableCallback, v7, v7 + 4) )
          EtwEventSetInformation(v7[4], 2, v7[1], *(unsigned __int16 *)v7[1]);
        dword_18008299C = 1;
        (*(void (__fastcall **)(__int64 *))(qword_180082988 + 8))(&qword_180082988);
        InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_180082988);
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
        v43 = v4[16];
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
          v9 = &qword_180064A78;
          v21 = 1;
        }
        v115 = v9;
        v116 = v21;
        v117 = 0;
        p_fPending = &fPending;
        v114 = 4;
        v111 = &v46;
        v112 = 4;
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
          v10 = &qword_1800649D8;
          v23 = 2;
        }
        v108 = v10;
        v109 = v23;
        v110 = 0;
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
          v11 = &qword_180064A78;
          v25 = 1;
        }
        v105 = v11;
        v106 = v25;
        v107 = 0;
        v103 = &v47;
        v104 = 4;
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
          v12 = &qword_1800649D8;
          v27 = 2;
        }
        v100 = v12;
        v101 = v27;
        v102 = 0;
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
          v13 = &qword_180064A78;
          v29 = 1;
        }
        v97 = v13;
        v98 = v29;
        v99 = 0;
        v95 = &v48;
        v96 = 4;
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
          v14 = &qword_180064A78;
          v31 = 1;
        }
        v92 = v14;
        v93 = v31;
        v94 = 0;
        v90 = &v49;
        v91 = 4;
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
          v15 = &qword_1800649D8;
          v33 = 2;
        }
        v87 = v15;
        v88 = v33;
        v89 = 0;
        v85 = &v50;
        v86 = 4;
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
          v16 = &qword_180064A78;
          v35 = 1;
        }
        v82 = v16;
        v83 = v35;
        v84 = 0;
        v80 = &v43;
        v81 = 4;
        if ( v17 )
        {
          do
            ++v19;
          while ( *((_BYTE *)v17 + v19) );
          v36 = v19 + 1;
        }
        else
        {
          v17 = &qword_180064A78;
          v36 = 1;
        }
        v77 = v17;
        v78 = v36;
        v79 = 0;
        v75 = &v44;
        v76 = 4;
        v73 = &v51;
        v74 = 8;
        v71 = &v45;
        v72 = 8;
        v52 = 0x2040B000000uLL;
        v65 = (unsigned __int16 *)Ptr[1];
        v66 = *v65;
        v67 = 2;
        v68 = &word_180072C06;
        v69 = 322;
        v70 = 1;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(Ptr[4], &v52, v18 + 8, 0, 21, &v65);
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
    SRWLock = (PSRWLOCK)&qword_180082988;
    qword_180082990 = 0;
    byte_180082998 = 0;
    dword_18008299C = 0;
    qword_180082988 = (__int64)&ProfileLogging::`vftable';
    qword_1800829A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
    v38 = (_QWORD *)qword_1800829A0;
    qword_180082990 = qword_1800829A0;
    byte_180082998 = 1;
    v52 = *(_OWORD *)(*(_QWORD *)(qword_1800829A0 + 8) - 16LL);
    if ( *(_QWORD *)(qword_1800829A0 + 32) )
      __fastfail(5u);
    *(_QWORD *)(qword_1800829A0 + 40) = 0;
    v38[6] = 0;
    if ( !(unsigned int)EtwEventRegister(&v52, tlgEnableCallback, v38, v38 + 4) )
      EtwEventSetInformation(v38[4], 2, v38[1], *(unsigned __int16 *)v38[1]);
    dword_18008299C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180082988 + 8))(&qword_180082988);
    InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_180082988);
  }
  v39 = SRWLock[1].Ptr;
  if ( *(_DWORD *)v39 > 4u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v40 = *((_QWORD *)this + 34);
    LODWORD(v44) = *(_DWORD *)(v40 + 72);
    v45 = (PSRWLOCK)0x1000000;
    p_SRWLock = &SRWLock;
    v64 = 4;
    v61 = &v44;
    v62 = 4;
    v59 = &v45;
    v60 = 8;
    v52 = 0x2040B000000uLL;
    v53 = (unsigned __int16 *)v39[1];
    v54 = *v53;
    v55 = 2;
    v56 = word_180072BB2;
    v57 = 72;
    v58 = 1;
    v43 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(v39[4], &v52, v40 + 8, 0, 5, &v53);
  }
LABEL_75:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ProfileTelemetry::CUserProfile_Unload *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002b9e0  push    rbp
0x18002b9e2  push    rbx
0x18002b9e3  push    rsi
0x18002b9e4  push    rdi
0x18002b9e5  push    r12
0x18002b9e7  push    r13
0x18002b9e9  push    r14
0x18002b9eb  push    r15
0x18002b9ed  lea     rbp, [rsp-148h]
0x18002b9f5  sub     rsp, 248h
0x18002b9fc  mov     rax, cs:__security_cookie
0x18002ba03  xor     rax, rsp
0x18002ba06  mov     [rbp+180h+var_50], rax
0x18002ba0d  mov     r14, rcx
0x18002ba10  xor     r12d, r12d
0x18002ba13  mov     rdi, [rcx+110h]
0x18002ba1a  mov     eax, [rdi+48h]
0x18002ba1d  test    eax, eax
0x18002ba1f  jns     loc_18002BFC1
0x18002ba25  add     rdi, 50h ; 'P'
0x18002ba29  cmp     eax, [rdi+8]
0x18002ba2c  jnz     loc_18002BFC1
0x18002ba32  mov     rbx, [rcx+118h]
0x18002ba39  test    rdi, rdi
0x18002ba3c  jz      loc_18002BFC8
0x18002ba42  test    rbx, rbx
0x18002ba45  jz      short loc_18002BA9E
0x18002ba47  add     rbx, 108h
0x18002ba4e  mov     rcx, rbx; SRWLock
0x18002ba51  call    cs:__imp_AcquireSRWLockExclusive
0x18002ba58  nop     dword ptr [rax+rax+00h]
0x18002ba5d  lea     rax, [rsp+280h+SRWLock]
0x18002ba62  mov     [rax], r12
0x18002ba65  mov     rcx, [rsp+280h+SRWLock]; SRWLock
0x18002ba6a  test    rcx, rcx
0x18002ba6d  jz      short loc_18002BA7B
0x18002ba6f  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ba76  nop     dword ptr [rax+rax+00h]
0x18002ba7b  mov     rax, [r14+110h]
0x18002ba82  mov     dword ptr [rax], 2
0x18002ba88  test    rbx, rbx
0x18002ba8b  jz      short loc_18002BAC9
0x18002ba8d  mov     rcx, rbx; SRWLock
0x18002ba90  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ba97  nop     dword ptr [rax+rax+00h]
0x18002ba9c  jmp     short loc_18002BAC9
0x18002ba9e  lea     rax, [rsp+280h+var_238]
0x18002baa3  mov     [rax], r12
0x18002baa6  mov     rcx, [rsp+280h+var_238]; SRWLock
0x18002baab  test    rcx, rcx
0x18002baae  jz      short loc_18002BABC
0x18002bab0  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bab7  nop     dword ptr [rax+rax+00h]
0x18002babc  mov     rax, [r14+110h]
0x18002bac3  mov     dword ptr [rax], 2
0x18002bac9  mov     [rsp+280h+SRWLock], r12
0x18002bace  mov     [rsp+280h+fPending], r12d
0x18002bad3  lea     r9, [rsp+280h+SRWLock]; lpContext
0x18002bad8  lea     r8, [rsp+280h+fPending]; fPending
0x18002badd  xor     edx, edx; dwFlags
0x18002badf  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x18002bae6  call    cs:__imp_InitOnceBeginInitialize
0x18002baed  nop     dword ptr [rax+rax+00h]
0x18002baf2  test    eax, eax
0x18002baf4  jz      loc_18002BBFA
0x18002bafa  cmp     [rsp+280h+fPending], r12d
0x18002baff  jz      loc_18002BBFA
0x18002bb05  lea     rsi, qword_180082988
0x18002bb0c  mov     [rsp+280h+SRWLock], rsi
0x18002bb11  mov     cs:qword_180082990, r12
0x18002bb18  mov     cs:byte_180082998, r12b
0x18002bb1f  mov     cs:dword_18008299C, r12d
0x18002bb26  lea     rax, ??_7ProfileLogging@@6B@
0x18002bb2d  mov     cs:qword_180082988, rax
0x18002bb34  lea     rax, ?__hInner@?1???0StaticHandle@ProfileLogging@@QEAA@XZ@4U_tlgProvider_t@@A
0x18002bb3b  mov     cs:qword_1800829A0, rax
0x18002bb42  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cff094b7b3eb7b3291eb3a07719b48ba_@@CA@XZ; void (__cdecl *)()
0x18002bb49  call    atexit
0x18002bb4e  mov     rbx, cs:qword_1800829A0
0x18002bb55  mov     cs:qword_180082990, rbx
0x18002bb5c  mov     cs:byte_180082998, 1
0x18002bb63  mov     rax, [rbx+8]
0x18002bb67  movups  xmm0, xmmword ptr [rax-10h]
0x18002bb6b  movups  [rsp+280h+var_208], xmm0
0x18002bb70  cmp     [rbx+20h], r12
0x18002bb74  jz      short loc_18002BB7D
0x18002bb76  mov     ecx, 5
0x18002bb7b  int     29h; Win8: RtlFailFast(ecx)
0x18002bb7d  mov     [rbx+28h], r12
0x18002bb81  mov     [rbx+30h], r12
0x18002bb85  lea     r9, [rbx+20h]
0x18002bb89  mov     r8, rbx
0x18002bb8c  lea     rdx, _tlgEnableCallback
0x18002bb93  lea     rcx, [rsp+280h+var_208]
0x18002bb98  call    cs:__imp_EtwEventRegister
0x18002bb9f  nop     dword ptr [rax+rax+00h]
0x18002bba4  test    eax, eax
0x18002bba6  jnz     short loc_18002BBC5
0x18002bba8  mov     r8, [rbx+8]
0x18002bbac  movzx   r9d, word ptr [r8]
0x18002bbb0  mov     edx, 2
0x18002bbb5  mov     rcx, [rbx+20h]
0x18002bbb9  call    cs:__imp_EtwEventSetInformation
0x18002bbc0  nop     dword ptr [rax+rax+00h]
0x18002bbc5  mov     cs:dword_18008299C, 1
0x18002bbcf  mov     rax, cs:qword_180082988
0x18002bbd6  mov     rcx, rsi
0x18002bbd9  mov     rax, [rax+8]
0x18002bbdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbe2  mov     r8, rsi; lpContext
0x18002bbe5  xor     edx, edx; dwFlags
0x18002bbe7  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x18002bbee  call    cs:__imp_InitOnceComplete
0x18002bbf5  nop     dword ptr [rax+rax+00h]
0x18002bbfa  mov     rax, [rsp+280h+SRWLock]
0x18002bbff  mov     r13, [rax+8]
0x18002bc03  mov     eax, [r13+0]
0x18002bc07  cmp     eax, 4
0x18002bc0a  jbe     loc_18002C27A
0x18002bc10  mov     rdx, [rdi+30h]
0x18002bc14  mov     eax, [rdi+44h]
0x18002bc17  mov     [rsp+280h+fPending], eax
0x18002bc1b  mov     eax, [rdi+10h]
0x18002bc1e  mov     [rsp+280h+var_228], eax
0x18002bc22  mov     r8, [rdi+78h]
0x18002bc26  mov     r9, [rdi+70h]
0x18002bc2a  mov     eax, [rdi+68h]
0x18002bc2d  mov     [rsp+280h+var_224], eax
0x18002bc31  mov     r10, [rdi+60h]
0x18002bc35  mov     r11, [rdi+58h]
0x18002bc39  mov     eax, [rdi+50h]
0x18002bc3c  mov     [rsp+280h+var_220], eax
0x18002bc40  mov     rbx, [rdi+48h]
0x18002bc44  mov     eax, [rdi+20h]
0x18002bc47  mov     [rsp+280h+var_21C], eax
0x18002bc4b  mov     rsi, [rdi+18h]
0x18002bc4f  mov     eax, [rdi]
0x18002bc51  mov     [rsp+280h+var_218], eax
0x18002bc55  mov     r15, [rdi+80h]
0x18002bc5c  mov     eax, [rdi+40h]
0x18002bc5f  mov     [rsp+280h+var_240], eax
0x18002bc63  mov     r12, [rdi+38h]
0x18002bc67  mov     eax, [rdi+8]
0x18002bc6a  mov     dword ptr [rsp+280h+var_238], eax
0x18002bc6e  mov     [rsp+280h+var_210], 1000000h
0x18002bc77  mov     [rsp+280h+var_230], 1000000h
0x18002bc80  mov     rdi, [r14+110h]
0x18002bc87  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002bc8e  test    rdx, rdx
0x18002bc91  jz      short loc_18002BCA3
0x18002bc93  mov     rax, rcx
0x18002bc96  inc     rax
0x18002bc99  cmp     byte ptr [rdx+rax], 0
0x18002bc9d  jnz     short loc_18002BC96
0x18002bc9f  inc     eax
0x18002bca1  jmp     short loc_18002BCAF
0x18002bca3  lea     rdx, qword_180064A78
0x18002bcaa  mov     eax, 1
0x18002bcaf  mov     [rbp+180h+var_60], rdx
0x18002bcb6  mov     [rbp+180h+var_58], eax
0x18002bcbc  xor     edx, edx
0x18002bcbe  mov     [rbp+180h+var_54], edx
0x18002bcc4  lea     rax, [rsp+280h+fPending]
0x18002bcc9  mov     [rbp+180h+var_70], rax
0x18002bcd0  mov     [rbp+180h+var_68], 4
0x18002bcdb  lea     rax, [rsp+280h+var_228]
0x18002bce0  mov     [rbp+180h+var_80], rax
0x18002bce7  mov     [rbp+180h+var_78], 4
0x18002bcf2  test    r8, r8
0x18002bcf5  jz      short loc_18002BD14
0x18002bcf7  mov     rax, rcx
0x18002bcfa  nop     word ptr [rax+rax+00h]
0x18002bd00  lea     rax, [rax+1]
0x18002bd04  cmp     [r8+rax*2], dx
0x18002bd09  jnz     short loc_18002BD00
0x18002bd0b  lea     eax, ds:2[rax*2]
0x18002bd12  jmp     short loc_18002BD20
0x18002bd14  lea     r8, qword_1800649D8
0x18002bd1b  mov     eax, 2
0x18002bd20  mov     [rbp+180h+var_90], r8
0x18002bd27  mov     [rbp+180h+var_88], eax
0x18002bd2d  mov     [rbp+180h+var_84], edx
0x18002bd33  test    r9, r9
0x18002bd36  jz      short loc_18002BD4D
0x18002bd38  mov     rax, rcx
0x18002bd3b  nop     dword ptr [rax+rax+00h]
0x18002bd40  inc     rax
0x18002bd43  cmp     [r9+rax], dl
0x18002bd47  jnz     short loc_18002BD40
0x18002bd49  inc     eax
0x18002bd4b  jmp     short loc_18002BD59
0x18002bd4d  lea     r9, qword_180064A78
0x18002bd54  mov     eax, 1
0x18002bd59  mov     [rbp+180h+var_A0], r9
0x18002bd60  mov     [rbp+180h+var_98], eax
0x18002bd66  mov     [rbp+180h+var_94], edx
0x18002bd6c  lea     rax, [rsp+280h+var_224]
0x18002bd71  mov     [rbp+180h+var_B0], rax
0x18002bd78  mov     [rbp+180h+var_A8], 4
0x18002bd83  test    r10, r10
0x18002bd86  jz      short loc_18002BDA4
0x18002bd88  mov     rax, rcx
0x18002bd8b  nop     dword ptr [rax+rax+00h]
0x18002bd90  lea     rax, [rax+1]
0x18002bd94  cmp     [r10+rax*2], dx
0x18002bd99  jnz     short loc_18002BD90
0x18002bd9b  lea     eax, ds:2[rax*2]
0x18002bda2  jmp     short loc_18002BDB0
0x18002bda4  lea     r10, qword_1800649D8
0x18002bdab  mov     eax, 2
0x18002bdb0  mov     [rbp+180h+var_C0], r10
0x18002bdb7  mov     [rbp+180h+var_B8], eax
0x18002bdbd  mov     [rbp+180h+var_B4], edx
0x18002bdc3  test    r11, r11
0x18002bdc6  jz      short loc_18002BDDD
0x18002bdc8  mov     rax, rcx
0x18002bdcb  nop     dword ptr [rax+rax+00h]
0x18002bdd0  inc     rax
0x18002bdd3  cmp     [r11+rax], dl
0x18002bdd7  jnz     short loc_18002BDD0
0x18002bdd9  inc     eax
0x18002bddb  jmp     short loc_18002BDE9
0x18002bddd  lea     r11, qword_180064A78
0x18002bde4  mov     eax, 1
0x18002bde9  mov     [rbp+180h+var_D0], r11
0x18002bdf0  mov     [rbp+180h+var_C8], eax
0x18002bdf6  mov     [rbp+180h+var_C4], edx
0x18002bdfc  lea     rax, [rsp+280h+var_220]
0x18002be01  mov     [rbp+180h+var_E0], rax
0x18002be08  mov     [rbp+180h+var_D8], 4
0x18002be13  test    rbx, rbx
0x18002be16  jz      short loc_18002BE2C
0x18002be18  mov     rax, rcx
0x18002be1b  nop     dword ptr [rax+rax+00h]
0x18002be20  inc     rax
0x18002be23  cmp     [rbx+rax], dl
0x18002be26  jnz     short loc_18002BE20
0x18002be28  inc     eax
0x18002be2a  jmp     short loc_18002BE38
0x18002be2c  lea     rbx, qword_180064A78
0x18002be33  mov     eax, 1
0x18002be38  mov     [rbp+180h+var_F0], rbx
0x18002be3f  mov     [rbp+180h+var_E8], eax
0x18002be45  mov     [rbp+180h+var_E4], edx
0x18002be4b  lea     rax, [rsp+280h+var_21C]
0x18002be50  mov     [rbp+180h+var_100], rax
0x18002be57  mov     [rbp+180h+var_F8], 4
0x18002be62  test    rsi, rsi
0x18002be65  jz      short loc_18002BE83
0x18002be67  mov     rax, rcx
0x18002be6a  nop     word ptr [rax+rax+00h]
0x18002be70  lea     rax, [rax+1]
0x18002be74  cmp     [rsi+rax*2], dx
0x18002be78  jnz     short loc_18002BE70
0x18002be7a  lea     eax, ds:2[rax*2]
0x18002be81  jmp     short loc_18002BE8F
0x18002be83  lea     rsi, qword_1800649D8
0x18002be8a  mov     eax, 2
0x18002be8f  mov     [rbp+180h+var_110], rsi
0x18002be93  mov     [rbp+180h+var_108], eax
0x18002be96  mov     [rbp+180h+var_104], edx
0x18002be99  lea     rax, [rsp+280h+var_218]
0x18002be9e  mov     [rbp+180h+var_120], rax
0x18002bea2  mov     [rbp+180h+var_118], 4
0x18002beaa  test    r15, r15
0x18002bead  jz      short loc_18002BEBF
0x18002beaf  mov     rax, rcx
0x18002beb2  inc     rax
0x18002beb5  cmp     [r15+rax], dl
0x18002beb9  jnz     short loc_18002BEB2
0x18002bebb  inc     eax
0x18002bebd  jmp     short loc_18002BECB
0x18002bebf  lea     r15, qword_180064A78
0x18002bec6  mov     eax, 1
0x18002becb  mov     [rbp+180h+var_130], r15
0x18002becf  mov     [rbp+180h+var_128], eax
0x18002bed2  mov     [rbp+180h+var_124], edx
0x18002bed5  lea     rax, [rsp+280h+var_240]
0x18002beda  mov     [rbp+180h+var_140], rax
0x18002bede  mov     [rbp+180h+var_138], 4
0x18002bee6  test    r12, r12
0x18002bee9  jz      short loc_18002BEFD
0x18002beeb  nop     dword ptr [rax+rax+00h]
0x18002bef0  inc     rcx
0x18002bef3  cmp     [r12+rcx], dl
0x18002bef7  jnz     short loc_18002BEF0
0x18002bef9  inc     ecx
0x18002befb  jmp     short loc_18002BF09
0x18002befd  lea     r12, qword_180064A78
0x18002bf04  mov     ecx, 1
0x18002bf09  mov     [rbp+180h+var_150], r12
0x18002bf0d  mov     [rbp+180h+var_148], ecx
0x18002bf10  mov     [rbp+180h+var_144], edx
0x18002bf13  lea     rax, [rsp+280h+var_238]
0x18002bf18  mov     [rbp+180h+var_160], rax
0x18002bf1c  mov     [rbp+180h+var_158], 4
0x18002bf24  lea     rax, [rsp+280h+var_210]
0x18002bf29  mov     [rbp+180h+var_170], rax
0x18002bf2d  mov     [rbp+180h+var_168], 8
0x18002bf35  lea     rax, [rsp+280h+var_230]
  ... truncated ...
```

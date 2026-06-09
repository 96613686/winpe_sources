# ProfileTelemetry::CUserProfile_Load::StopActivity(void)

- ea: `0x18002b100`
- end: `0x18002b9d1`
- name: `?StopActivity@CUserProfile_Load@ProfileTelemetry@@MEAAXXZ`
- size: `2257`
- prototype: `void __fastcall(ProfileTelemetry::CUserProfile_Load *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002b100`
- `0x18003657c`
- `0x18003bc70`
- `0x18003c020`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b171`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b6f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b171`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b6f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b18f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b1b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b1d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b715`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b736`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b756`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b18f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b1b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b1d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b715`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b736`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b756`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b8b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b8b4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002b206`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002b78c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002b206`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002b78c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002b30e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002b894`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002b30e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002b894`
- `ntdll!EtwEventWriteTransfer` at `0x18002b98d`
- `ntdll!EtwEventWriteTransfer` at `0x18002b98d`
- `ntdll!EtwEventSetInformation` at `0x18002b2d9`
- `ntdll!EtwEventSetInformation` at `0x18002b85f`
- `ntdll!EtwEventSetInformation` at `0x18002b2d9`
- `ntdll!EtwEventSetInformation` at `0x18002b85f`
- `ntdll!EtwEventRegister` at `0x18002b2b8`
- `ntdll!EtwEventRegister` at `0x18002b83e`
- `ntdll!EtwEventRegister` at `0x18002b2b8`
- `ntdll!EtwEventRegister` at `0x18002b83e`

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
  void *v68; // [rsp+F0h] [rbp-10h]
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
        v68 = &unk_180073018;
        v69 = 320;
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
    v56 = &word_180072FC6;
    v57 = 70;
    v58 = 1;
    v43 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(v39[4], &v52, v40 + 8, 0, 5, &v53);
  }
LABEL_75:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ProfileTelemetry::CUserProfile_Load *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002b100  push    rbp
0x18002b102  push    rbx
0x18002b103  push    rsi
0x18002b104  push    rdi
0x18002b105  push    r12
0x18002b107  push    r13
0x18002b109  push    r14
0x18002b10b  push    r15
0x18002b10d  lea     rbp, [rsp-148h]
0x18002b115  sub     rsp, 248h
0x18002b11c  mov     rax, cs:__security_cookie
0x18002b123  xor     rax, rsp
0x18002b126  mov     [rbp+180h+var_50], rax
0x18002b12d  mov     r14, rcx
0x18002b130  xor     r12d, r12d
0x18002b133  mov     rdi, [rcx+110h]
0x18002b13a  mov     eax, [rdi+48h]
0x18002b13d  test    eax, eax
0x18002b13f  jns     loc_18002B6E1
0x18002b145  add     rdi, 50h ; 'P'
0x18002b149  cmp     eax, [rdi+8]
0x18002b14c  jnz     loc_18002B6E1
0x18002b152  mov     rbx, [rcx+118h]
0x18002b159  test    rdi, rdi
0x18002b15c  jz      loc_18002B6E8
0x18002b162  test    rbx, rbx
0x18002b165  jz      short loc_18002B1BE
0x18002b167  add     rbx, 108h
0x18002b16e  mov     rcx, rbx; SRWLock
0x18002b171  call    cs:__imp_AcquireSRWLockExclusive
0x18002b178  nop     dword ptr [rax+rax+00h]
0x18002b17d  lea     rax, [rsp+280h+SRWLock]
0x18002b182  mov     [rax], r12
0x18002b185  mov     rcx, [rsp+280h+SRWLock]; SRWLock
0x18002b18a  test    rcx, rcx
0x18002b18d  jz      short loc_18002B19B
0x18002b18f  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b196  nop     dword ptr [rax+rax+00h]
0x18002b19b  mov     rax, [r14+110h]
0x18002b1a2  mov     dword ptr [rax], 2
0x18002b1a8  test    rbx, rbx
0x18002b1ab  jz      short loc_18002B1E9
0x18002b1ad  mov     rcx, rbx; SRWLock
0x18002b1b0  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b1b7  nop     dword ptr [rax+rax+00h]
0x18002b1bc  jmp     short loc_18002B1E9
0x18002b1be  lea     rax, [rsp+280h+var_238]
0x18002b1c3  mov     [rax], r12
0x18002b1c6  mov     rcx, [rsp+280h+var_238]; SRWLock
0x18002b1cb  test    rcx, rcx
0x18002b1ce  jz      short loc_18002B1DC
0x18002b1d0  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b1d7  nop     dword ptr [rax+rax+00h]
0x18002b1dc  mov     rax, [r14+110h]
0x18002b1e3  mov     dword ptr [rax], 2
0x18002b1e9  mov     [rsp+280h+SRWLock], r12
0x18002b1ee  mov     [rsp+280h+fPending], r12d
0x18002b1f3  lea     r9, [rsp+280h+SRWLock]; lpContext
0x18002b1f8  lea     r8, [rsp+280h+fPending]; fPending
0x18002b1fd  xor     edx, edx; dwFlags
0x18002b1ff  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x18002b206  call    cs:__imp_InitOnceBeginInitialize
0x18002b20d  nop     dword ptr [rax+rax+00h]
0x18002b212  test    eax, eax
0x18002b214  jz      loc_18002B31A
0x18002b21a  cmp     [rsp+280h+fPending], r12d
0x18002b21f  jz      loc_18002B31A
0x18002b225  lea     rsi, qword_180082988
0x18002b22c  mov     [rsp+280h+SRWLock], rsi
0x18002b231  mov     cs:qword_180082990, r12
0x18002b238  mov     cs:byte_180082998, r12b
0x18002b23f  mov     cs:dword_18008299C, r12d
0x18002b246  lea     rax, ??_7ProfileLogging@@6B@
0x18002b24d  mov     cs:qword_180082988, rax
0x18002b254  lea     rax, ?__hInner@?1???0StaticHandle@ProfileLogging@@QEAA@XZ@4U_tlgProvider_t@@A
0x18002b25b  mov     cs:qword_1800829A0, rax
0x18002b262  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cff094b7b3eb7b3291eb3a07719b48ba_@@CA@XZ; void (__cdecl *)()
0x18002b269  call    atexit
0x18002b26e  mov     rbx, cs:qword_1800829A0
0x18002b275  mov     cs:qword_180082990, rbx
0x18002b27c  mov     cs:byte_180082998, 1
0x18002b283  mov     rax, [rbx+8]
0x18002b287  movups  xmm0, xmmword ptr [rax-10h]
0x18002b28b  movups  [rsp+280h+var_208], xmm0
0x18002b290  cmp     [rbx+20h], r12
0x18002b294  jz      short loc_18002B29D
0x18002b296  mov     ecx, 5
0x18002b29b  int     29h; Win8: RtlFailFast(ecx)
0x18002b29d  mov     [rbx+28h], r12
0x18002b2a1  mov     [rbx+30h], r12
0x18002b2a5  lea     r9, [rbx+20h]
0x18002b2a9  mov     r8, rbx
0x18002b2ac  lea     rdx, _tlgEnableCallback
0x18002b2b3  lea     rcx, [rsp+280h+var_208]
0x18002b2b8  call    cs:__imp_EtwEventRegister
0x18002b2bf  nop     dword ptr [rax+rax+00h]
0x18002b2c4  test    eax, eax
0x18002b2c6  jnz     short loc_18002B2E5
0x18002b2c8  mov     r8, [rbx+8]
0x18002b2cc  movzx   r9d, word ptr [r8]
0x18002b2d0  mov     edx, 2
0x18002b2d5  mov     rcx, [rbx+20h]
0x18002b2d9  call    cs:__imp_EtwEventSetInformation
0x18002b2e0  nop     dword ptr [rax+rax+00h]
0x18002b2e5  mov     cs:dword_18008299C, 1
0x18002b2ef  mov     rax, cs:qword_180082988
0x18002b2f6  mov     rcx, rsi
0x18002b2f9  mov     rax, [rax+8]
0x18002b2fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b302  mov     r8, rsi; lpContext
0x18002b305  xor     edx, edx; dwFlags
0x18002b307  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x18002b30e  call    cs:__imp_InitOnceComplete
0x18002b315  nop     dword ptr [rax+rax+00h]
0x18002b31a  mov     rax, [rsp+280h+SRWLock]
0x18002b31f  mov     r13, [rax+8]
0x18002b323  mov     eax, [r13+0]
0x18002b327  cmp     eax, 4
0x18002b32a  jbe     loc_18002B99A
0x18002b330  mov     rdx, [rdi+30h]
0x18002b334  mov     eax, [rdi+44h]
0x18002b337  mov     [rsp+280h+fPending], eax
0x18002b33b  mov     eax, [rdi+10h]
0x18002b33e  mov     [rsp+280h+var_228], eax
0x18002b342  mov     r8, [rdi+78h]
0x18002b346  mov     r9, [rdi+70h]
0x18002b34a  mov     eax, [rdi+68h]
0x18002b34d  mov     [rsp+280h+var_224], eax
0x18002b351  mov     r10, [rdi+60h]
0x18002b355  mov     r11, [rdi+58h]
0x18002b359  mov     eax, [rdi+50h]
0x18002b35c  mov     [rsp+280h+var_220], eax
0x18002b360  mov     rbx, [rdi+48h]
0x18002b364  mov     eax, [rdi+20h]
0x18002b367  mov     [rsp+280h+var_21C], eax
0x18002b36b  mov     rsi, [rdi+18h]
0x18002b36f  mov     eax, [rdi]
0x18002b371  mov     [rsp+280h+var_218], eax
0x18002b375  mov     r15, [rdi+80h]
0x18002b37c  mov     eax, [rdi+40h]
0x18002b37f  mov     [rsp+280h+var_240], eax
0x18002b383  mov     r12, [rdi+38h]
0x18002b387  mov     eax, [rdi+8]
0x18002b38a  mov     dword ptr [rsp+280h+var_238], eax
0x18002b38e  mov     [rsp+280h+var_210], 1000000h
0x18002b397  mov     [rsp+280h+var_230], 1000000h
0x18002b3a0  mov     rdi, [r14+110h]
0x18002b3a7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b3ae  test    rdx, rdx
0x18002b3b1  jz      short loc_18002B3C3
0x18002b3b3  mov     rax, rcx
0x18002b3b6  inc     rax
0x18002b3b9  cmp     byte ptr [rdx+rax], 0
0x18002b3bd  jnz     short loc_18002B3B6
0x18002b3bf  inc     eax
0x18002b3c1  jmp     short loc_18002B3CF
0x18002b3c3  lea     rdx, qword_180064A78
0x18002b3ca  mov     eax, 1
0x18002b3cf  mov     [rbp+180h+var_60], rdx
0x18002b3d6  mov     [rbp+180h+var_58], eax
0x18002b3dc  xor     edx, edx
0x18002b3de  mov     [rbp+180h+var_54], edx
0x18002b3e4  lea     rax, [rsp+280h+fPending]
0x18002b3e9  mov     [rbp+180h+var_70], rax
0x18002b3f0  mov     [rbp+180h+var_68], 4
0x18002b3fb  lea     rax, [rsp+280h+var_228]
0x18002b400  mov     [rbp+180h+var_80], rax
0x18002b407  mov     [rbp+180h+var_78], 4
0x18002b412  test    r8, r8
0x18002b415  jz      short loc_18002B434
0x18002b417  mov     rax, rcx
0x18002b41a  nop     word ptr [rax+rax+00h]
0x18002b420  lea     rax, [rax+1]
0x18002b424  cmp     [r8+rax*2], dx
0x18002b429  jnz     short loc_18002B420
0x18002b42b  lea     eax, ds:2[rax*2]
0x18002b432  jmp     short loc_18002B440
0x18002b434  lea     r8, qword_1800649D8
0x18002b43b  mov     eax, 2
0x18002b440  mov     [rbp+180h+var_90], r8
0x18002b447  mov     [rbp+180h+var_88], eax
0x18002b44d  mov     [rbp+180h+var_84], edx
0x18002b453  test    r9, r9
0x18002b456  jz      short loc_18002B46D
0x18002b458  mov     rax, rcx
0x18002b45b  nop     dword ptr [rax+rax+00h]
0x18002b460  inc     rax
0x18002b463  cmp     [r9+rax], dl
0x18002b467  jnz     short loc_18002B460
0x18002b469  inc     eax
0x18002b46b  jmp     short loc_18002B479
0x18002b46d  lea     r9, qword_180064A78
0x18002b474  mov     eax, 1
0x18002b479  mov     [rbp+180h+var_A0], r9
0x18002b480  mov     [rbp+180h+var_98], eax
0x18002b486  mov     [rbp+180h+var_94], edx
0x18002b48c  lea     rax, [rsp+280h+var_224]
0x18002b491  mov     [rbp+180h+var_B0], rax
0x18002b498  mov     [rbp+180h+var_A8], 4
0x18002b4a3  test    r10, r10
0x18002b4a6  jz      short loc_18002B4C4
0x18002b4a8  mov     rax, rcx
0x18002b4ab  nop     dword ptr [rax+rax+00h]
0x18002b4b0  lea     rax, [rax+1]
0x18002b4b4  cmp     [r10+rax*2], dx
0x18002b4b9  jnz     short loc_18002B4B0
0x18002b4bb  lea     eax, ds:2[rax*2]
0x18002b4c2  jmp     short loc_18002B4D0
0x18002b4c4  lea     r10, qword_1800649D8
0x18002b4cb  mov     eax, 2
0x18002b4d0  mov     [rbp+180h+var_C0], r10
0x18002b4d7  mov     [rbp+180h+var_B8], eax
0x18002b4dd  mov     [rbp+180h+var_B4], edx
0x18002b4e3  test    r11, r11
0x18002b4e6  jz      short loc_18002B4FD
0x18002b4e8  mov     rax, rcx
0x18002b4eb  nop     dword ptr [rax+rax+00h]
0x18002b4f0  inc     rax
0x18002b4f3  cmp     [r11+rax], dl
0x18002b4f7  jnz     short loc_18002B4F0
0x18002b4f9  inc     eax
0x18002b4fb  jmp     short loc_18002B509
0x18002b4fd  lea     r11, qword_180064A78
0x18002b504  mov     eax, 1
0x18002b509  mov     [rbp+180h+var_D0], r11
0x18002b510  mov     [rbp+180h+var_C8], eax
0x18002b516  mov     [rbp+180h+var_C4], edx
0x18002b51c  lea     rax, [rsp+280h+var_220]
0x18002b521  mov     [rbp+180h+var_E0], rax
0x18002b528  mov     [rbp+180h+var_D8], 4
0x18002b533  test    rbx, rbx
0x18002b536  jz      short loc_18002B54C
0x18002b538  mov     rax, rcx
0x18002b53b  nop     dword ptr [rax+rax+00h]
0x18002b540  inc     rax
0x18002b543  cmp     [rbx+rax], dl
0x18002b546  jnz     short loc_18002B540
0x18002b548  inc     eax
0x18002b54a  jmp     short loc_18002B558
0x18002b54c  lea     rbx, qword_180064A78
0x18002b553  mov     eax, 1
0x18002b558  mov     [rbp+180h+var_F0], rbx
0x18002b55f  mov     [rbp+180h+var_E8], eax
0x18002b565  mov     [rbp+180h+var_E4], edx
0x18002b56b  lea     rax, [rsp+280h+var_21C]
0x18002b570  mov     [rbp+180h+var_100], rax
0x18002b577  mov     [rbp+180h+var_F8], 4
0x18002b582  test    rsi, rsi
0x18002b585  jz      short loc_18002B5A3
0x18002b587  mov     rax, rcx
0x18002b58a  nop     word ptr [rax+rax+00h]
0x18002b590  lea     rax, [rax+1]
0x18002b594  cmp     [rsi+rax*2], dx
0x18002b598  jnz     short loc_18002B590
0x18002b59a  lea     eax, ds:2[rax*2]
0x18002b5a1  jmp     short loc_18002B5AF
0x18002b5a3  lea     rsi, qword_1800649D8
0x18002b5aa  mov     eax, 2
0x18002b5af  mov     [rbp+180h+var_110], rsi
0x18002b5b3  mov     [rbp+180h+var_108], eax
0x18002b5b6  mov     [rbp+180h+var_104], edx
0x18002b5b9  lea     rax, [rsp+280h+var_218]
0x18002b5be  mov     [rbp+180h+var_120], rax
0x18002b5c2  mov     [rbp+180h+var_118], 4
0x18002b5ca  test    r15, r15
0x18002b5cd  jz      short loc_18002B5DF
0x18002b5cf  mov     rax, rcx
0x18002b5d2  inc     rax
0x18002b5d5  cmp     [r15+rax], dl
0x18002b5d9  jnz     short loc_18002B5D2
0x18002b5db  inc     eax
0x18002b5dd  jmp     short loc_18002B5EB
0x18002b5df  lea     r15, qword_180064A78
0x18002b5e6  mov     eax, 1
0x18002b5eb  mov     [rbp+180h+var_130], r15
0x18002b5ef  mov     [rbp+180h+var_128], eax
0x18002b5f2  mov     [rbp+180h+var_124], edx
0x18002b5f5  lea     rax, [rsp+280h+var_240]
0x18002b5fa  mov     [rbp+180h+var_140], rax
0x18002b5fe  mov     [rbp+180h+var_138], 4
0x18002b606  test    r12, r12
0x18002b609  jz      short loc_18002B61D
0x18002b60b  nop     dword ptr [rax+rax+00h]
0x18002b610  inc     rcx
0x18002b613  cmp     [r12+rcx], dl
0x18002b617  jnz     short loc_18002B610
0x18002b619  inc     ecx
0x18002b61b  jmp     short loc_18002B629
0x18002b61d  lea     r12, qword_180064A78
0x18002b624  mov     ecx, 1
0x18002b629  mov     [rbp+180h+var_150], r12
0x18002b62d  mov     [rbp+180h+var_148], ecx
0x18002b630  mov     [rbp+180h+var_144], edx
0x18002b633  lea     rax, [rsp+280h+var_238]
0x18002b638  mov     [rbp+180h+var_160], rax
0x18002b63c  mov     [rbp+180h+var_158], 4
0x18002b644  lea     rax, [rsp+280h+var_210]
0x18002b649  mov     [rbp+180h+var_170], rax
0x18002b64d  mov     [rbp+180h+var_168], 8
0x18002b655  lea     rax, [rsp+280h+var_230]
  ... truncated ...
```

# wil::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x18002a380`
- end: `0x18002abc1`
- name: `?ReportStopActivity@?$ActivityBase@VProfileLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `2113`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180045b8c`
- `0x1800477d4`

## callees

- `0x18002a380`
- `0x18003bc70`
- `0x18003c020`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aa1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aa1f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002a414`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002a8bf`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002a414`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002a8bf`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002a519`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002a9c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002a519`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002a9c4`
- `ntdll!EtwEventWriteTransfer` at `0x18002a88b`
- `ntdll!EtwEventWriteTransfer` at `0x18002ab60`
- `ntdll!EtwEventWriteTransfer` at `0x18002a88b`
- `ntdll!EtwEventWriteTransfer` at `0x18002ab60`
- `ntdll!EtwEventSetInformation` at `0x18002a4e4`
- `ntdll!EtwEventSetInformation` at `0x18002a98f`
- `ntdll!EtwEventSetInformation` at `0x18002a4e4`
- `ntdll!EtwEventSetInformation` at `0x18002a98f`
- `ntdll!EtwEventRegister` at `0x18002a4c3`
- `ntdll!EtwEventRegister` at `0x18002a96e`
- `ntdll!EtwEventRegister` at `0x18002a4c3`
- `ntdll!EtwEventRegister` at `0x18002a96e`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  _QWORD *v3; // r12
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  _QWORD *v7; // rsi
  __int64 v8; // r9
  _QWORD *v9; // rdx
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r9
  const unsigned __int16 *v13; // r10
  const unsigned __int16 *v14; // r11
  const unsigned __int16 *v15; // r14
  const unsigned __int16 *v16; // r15
  const unsigned __int16 *v17; // r12
  __int64 v18; // rax
  __int64 v19; // rcx
  bool v20; // zf
  int v21; // ecx
  __int64 v22; // rcx
  int v23; // ecx
  __int64 v24; // rcx
  int v25; // ecx
  __int64 v26; // rcx
  int v27; // ecx
  __int64 v28; // rcx
  int v29; // ecx
  __int64 v30; // rcx
  int v31; // ecx
  __int64 v32; // rcx
  int v33; // ecx
  int v34; // eax
  _QWORD *v35; // rcx
  _QWORD *v36; // rdi
  __int64 v37; // r9
  __int64 v38; // r14
  __int64 v39; // rax
  const unsigned __int16 *v40; // rsi
  const unsigned __int16 *v41; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v43; // r8
  __int64 v44; // rax
  __int64 v45; // rcx
  int v46; // ecx
  int v47; // eax
  WINBOOL fPending[2]; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID Context; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v51; // [rsp+48h] [rbp-C0h] BYREF
  int v52; // [rsp+4Ch] [rbp-BCh] BYREF
  int v53; // [rsp+50h] [rbp-B8h] BYREF
  int v54; // [rsp+54h] [rbp-B4h] BYREF
  __int64 v55; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD *v57; // [rsp+68h] [rbp-A0h]
  _QWORD v58[3]; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int16 *v59; // [rsp+88h] [rbp-80h] BYREF
  int v60; // [rsp+90h] [rbp-78h]
  int v61; // [rsp+94h] [rbp-74h]
  char *v62; // [rsp+98h] [rbp-70h]
  int v63; // [rsp+A0h] [rbp-68h]
  int v64; // [rsp+A4h] [rbp-64h]
  __int64 *v65; // [rsp+A8h] [rbp-60h]
  __int64 v66; // [rsp+B0h] [rbp-58h]
  int *v67; // [rsp+B8h] [rbp-50h]
  __int64 v68; // [rsp+C0h] [rbp-48h]
  LPVOID *p_Context; // [rsp+C8h] [rbp-40h]
  __int64 v70; // [rsp+D0h] [rbp-38h]
  const unsigned __int16 *v71; // [rsp+D8h] [rbp-30h]
  int v72; // [rsp+E0h] [rbp-28h]
  int v73; // [rsp+E4h] [rbp-24h]
  const unsigned __int16 *v74; // [rsp+E8h] [rbp-20h]
  int v75; // [rsp+F0h] [rbp-18h]
  int v76; // [rsp+F4h] [rbp-14h]
  unsigned __int16 *v77; // [rsp+F8h] [rbp-10h] BYREF
  int v78; // [rsp+100h] [rbp-8h]
  int v79; // [rsp+104h] [rbp-4h]
  __int16 *v80; // [rsp+108h] [rbp+0h]
  int v81; // [rsp+110h] [rbp+8h]
  int v82; // [rsp+114h] [rbp+Ch]
  _QWORD *v83; // [rsp+118h] [rbp+10h]
  __int64 v84; // [rsp+120h] [rbp+18h]
  int *v85; // [rsp+128h] [rbp+20h]
  __int64 v86; // [rsp+130h] [rbp+28h]
  const unsigned __int16 *v87; // [rsp+138h] [rbp+30h]
  int v88; // [rsp+140h] [rbp+38h]
  int v89; // [rsp+144h] [rbp+3Ch]
  unsigned int *v90; // [rsp+148h] [rbp+40h]
  __int64 v91; // [rsp+150h] [rbp+48h]
  const unsigned __int16 *v92; // [rsp+158h] [rbp+50h]
  int v93; // [rsp+160h] [rbp+58h]
  int v94; // [rsp+164h] [rbp+5Ch]
  __int64 *v95; // [rsp+168h] [rbp+60h]
  __int64 v96; // [rsp+170h] [rbp+68h]
  const unsigned __int16 *v97; // [rsp+178h] [rbp+70h]
  int v98; // [rsp+180h] [rbp+78h]
  int v99; // [rsp+184h] [rbp+7Ch]
  int *v100; // [rsp+188h] [rbp+80h]
  __int64 v101; // [rsp+190h] [rbp+88h]
  const unsigned __int16 *v102; // [rsp+198h] [rbp+90h]
  int v103; // [rsp+1A0h] [rbp+98h]
  int v104; // [rsp+1A4h] [rbp+9Ch]
  int *v105; // [rsp+1A8h] [rbp+A0h]
  __int64 v106; // [rsp+1B0h] [rbp+A8h]
  const unsigned __int16 *v107; // [rsp+1B8h] [rbp+B0h]
  int v108; // [rsp+1C0h] [rbp+B8h]
  int v109; // [rsp+1C4h] [rbp+BCh]
  const unsigned __int16 *v110; // [rsp+1C8h] [rbp+C0h]
  int v111; // [rsp+1D0h] [rbp+C8h]
  int v112; // [rsp+1D4h] [rbp+CCh]
  WINBOOL *v113; // [rsp+1D8h] [rbp+D0h]
  __int64 v114; // [rsp+1E0h] [rbp+D8h]
  const unsigned __int16 *v115; // [rsp+1E8h] [rbp+E0h]
  int v116; // [rsp+1F0h] [rbp+E8h]
  int v117; // [rsp+1F4h] [rbp+ECh]
  const unsigned __int16 *v118; // [rsp+1F8h] [rbp+F0h]
  int v119; // [rsp+200h] [rbp+F8h]
  int v120; // [rsp+204h] [rbp+FCh]

  v57 = a1;
  v3 = a1;
  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      Context = 0;
      fPending[0] = 0;
      if ( InitOnceBeginInitialize(&`ProfileLogging::Instance'::`2'::wrapper, 0, fPending, &Context) && fPending[0] )
      {
        qword_180082990 = 0;
        Context = &qword_180082988;
        qword_180082988 = (__int64)&ProfileLogging::`vftable';
        byte_180082998 = 0;
        dword_18008299C = 0;
        qword_1800829A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
        v7 = (_QWORD *)qword_1800829A0;
        qword_180082990 = qword_1800829A0;
        byte_180082998 = 1;
        *(_OWORD *)&v58[1] = *(_OWORD *)(*(_QWORD *)(qword_1800829A0 + 8) - 16LL);
        if ( *(_QWORD *)(qword_1800829A0 + 32) )
          __fastfail(5u);
        v8 = qword_1800829A0 + 32;
        *(_QWORD *)(qword_1800829A0 + 40) = 0;
        v7[6] = 0;
        if ( !(unsigned int)EtwEventRegister(&v58[1], tlgEnableCallback, v7, v8) )
          EtwEventSetInformation(v7[4], 2, v7[1], *(unsigned __int16 *)v7[1]);
        dword_18008299C = 1;
        (*(void (__fastcall **)(__int64 *))(qword_180082988 + 8))(&qword_180082988);
        InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_180082988);
      }
      v9 = (_QWORD *)*((_QWORD *)Context + 1);
      Context = v9;
      if ( *(_DWORD *)v9 > 2u && (v9[2] & 0x200000000000LL) != 0 && (v9[3] & 0x200000000000LL) == v9[3] )
      {
        v10 = *(const unsigned __int16 **)(v6 + 120);
        v11 = *(const unsigned __int16 **)(v6 + 112);
        v12 = *(const unsigned __int16 **)(v6 + 96);
        v13 = *(const unsigned __int16 **)(v6 + 88);
        v14 = *(const unsigned __int16 **)(v6 + 72);
        v15 = *(const unsigned __int16 **)(v6 + 24);
        v16 = *(const unsigned __int16 **)(v6 + 128);
        v17 = *(const unsigned __int16 **)(v6 + 56);
        fPending[0] = *(_DWORD *)(v6 + 104);
        v53 = *(_DWORD *)(v6 + 80);
        v54 = *(_DWORD *)(v6 + 32);
        LODWORD(v55) = *(_DWORD *)v6;
        v51 = *(_DWORD *)(v6 + 64);
        v52 = *(_DWORD *)(v6 + 8);
        v58[0] = 0x1000000;
        v56 = v57[34] + 8LL;
        v18 = -1;
        if ( v10 )
        {
          v19 = -1;
          do
            v20 = v10[++v19] == 0;
          while ( !v20 );
          v21 = 2 * v19 + 2;
        }
        else
        {
          v10 = &qword_1800649D8;
          v21 = 2;
        }
        v118 = v10;
        v119 = v21;
        v120 = 0;
        if ( v11 )
        {
          v22 = -1;
          do
            ++v22;
          while ( *((_BYTE *)v11 + v22) );
          v23 = v22 + 1;
        }
        else
        {
          v11 = &qword_180064A78;
          v23 = 1;
        }
        v116 = v23;
        v113 = fPending;
        v115 = v11;
        v117 = 0;
        v114 = 4;
        if ( v12 )
        {
          v24 = -1;
          do
            v20 = v12[++v24] == 0;
          while ( !v20 );
          v25 = 2 * v24 + 2;
        }
        else
        {
          v12 = &qword_1800649D8;
          v25 = 2;
        }
        v110 = v12;
        v111 = v25;
        v112 = 0;
        if ( v13 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *((_BYTE *)v13 + v26) );
          v27 = v26 + 1;
        }
        else
        {
          v13 = &qword_180064A78;
          v27 = 1;
        }
        v108 = v27;
        v105 = &v53;
        v107 = v13;
        v109 = 0;
        v106 = 4;
        if ( v14 )
        {
          v28 = -1;
          do
            ++v28;
          while ( *((_BYTE *)v14 + v28) );
          v29 = v28 + 1;
        }
        else
        {
          v14 = &qword_180064A78;
          v29 = 1;
        }
        v103 = v29;
        v100 = &v54;
        v102 = v14;
        v104 = 0;
        v101 = 4;
        if ( v15 )
        {
          v30 = -1;
          do
            v20 = v15[++v30] == 0;
          while ( !v20 );
          v31 = 2 * v30 + 2;
        }
        else
        {
          v15 = &qword_1800649D8;
          v31 = 2;
        }
        v98 = v31;
        v95 = &v55;
        v97 = v15;
        v99 = 0;
        v96 = 4;
        if ( v16 )
        {
          v32 = -1;
          do
            ++v32;
          while ( *((_BYTE *)v16 + v32) );
          v33 = v32 + 1;
        }
        else
        {
          v16 = &qword_180064A78;
          v33 = 1;
        }
        v93 = v33;
        v90 = &v51;
        v92 = v16;
        v94 = 0;
        v91 = 4;
        if ( v17 )
        {
          do
            ++v18;
          while ( *((_BYTE *)v17 + v18) );
          v34 = v18 + 1;
        }
        else
        {
          v17 = &qword_180064A78;
          v34 = 1;
        }
        v35 = Context;
        v88 = v34;
        v87 = v17;
        v85 = &v52;
        v83 = v58;
        v77 = (unsigned __int16 *)*((_QWORD *)Context + 1);
        v89 = 0;
        v86 = 4;
        v84 = 8;
        v58[1] = 0x20B000000LL;
        v58[2] = 0x200000000000LL;
        v78 = *v77;
        v80 = &word_1800713F6;
        v79 = 2;
        v81 = 267;
        v82 = 1;
        LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(v35[4], &v58[1], v56, 0, 17, &v77);
        v3 = v57;
      }
    }
    else
    {
      Context = 0;
      fPending[0] = 0;
      if ( InitOnceBeginInitialize(&`ProfileLogging::Instance'::`2'::wrapper, 0, fPending, &Context) && fPending[0] )
      {
        qword_180082990 = 0;
        Context = &qword_180082988;
        qword_180082988 = (__int64)&ProfileLogging::`vftable';
        byte_180082998 = 0;
        dword_18008299C = 0;
        qword_1800829A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
        v36 = (_QWORD *)qword_1800829A0;
        qword_180082990 = qword_1800829A0;
        byte_180082998 = 1;
        *(_OWORD *)&v58[1] = *(_OWORD *)(*(_QWORD *)(qword_1800829A0 + 8) - 16LL);
        if ( *(_QWORD *)(qword_1800829A0 + 32) )
          __fastfail(5u);
        v37 = qword_1800829A0 + 32;
        *(_QWORD *)(qword_1800829A0 + 40) = 0;
        v36[6] = 0;
        if ( !(unsigned int)EtwEventRegister(&v58[1], tlgEnableCallback, v36, v37) )
          EtwEventSetInformation(v36[4], 2, v36[1], *(unsigned __int16 *)v36[1]);
        dword_18008299C = 1;
        (*(void (__fastcall **)(__int64 *))(qword_180082988 + 8))(&qword_180082988);
        InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_180082988);
      }
      v38 = *((_QWORD *)Context + 1);
      if ( *(_DWORD *)v38 > 2u
        && (*(_QWORD *)(v38 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(v38 + 24) & 0x200000000000LL) == *(_QWORD *)(v38 + 24) )
      {
        v39 = v3[34];
        v40 = *(const unsigned __int16 **)(v39 + 56);
        v41 = *(const unsigned __int16 **)(v39 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v43 = v3[34] + 8LL;
        LODWORD(Context) = CurrentThreadId;
        v52 = a2;
        v44 = -1;
        v56 = 0x1000000;
        if ( v40 )
        {
          v45 = -1;
          do
            v20 = v40[++v45] == 0;
          while ( !v20 );
          v46 = 2 * v45 + 2;
        }
        else
        {
          v40 = &qword_1800649D8;
          v46 = 2;
        }
        v74 = v40;
        v75 = v46;
        v76 = 0;
        if ( v41 )
        {
          do
            ++v44;
          while ( *((_BYTE *)v41 + v44) );
          v47 = v44 + 1;
        }
        else
        {
          v41 = &qword_180064A78;
          v47 = 1;
        }
        v72 = v47;
        v71 = v41;
        p_Context = &Context;
        v73 = 0;
        v67 = &v52;
        v65 = &v56;
        v59 = *(unsigned __int16 **)(v38 + 8);
        v70 = 4;
        v68 = 4;
        v66 = 8;
        v58[1] = 0x20B000000LL;
        v58[2] = 0x200000000000LL;
        v60 = *v59;
        v62 = byte_18007137B;
        v61 = 2;
        v63 = 111;
        v64 = 1;
        v51 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(*(_QWORD *)(v38 + 32), &v58[1], v43, 0, 7, &v59);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
}

```

## disassembly

```asm
0x18002a380  mov     r11, rsp
0x18002a383  push    rbp
0x18002a384  push    r12
0x18002a386  push    r15
0x18002a388  lea     rbp, [r11-138h]
0x18002a38f  sub     rsp, 220h
0x18002a396  mov     rax, cs:__security_cookie
0x18002a39d  xor     rax, rsp
0x18002a3a0  mov     [rbp+130h+var_30], rax
0x18002a3a7  mov     [rsp+230h+var_1D0], rcx
0x18002a3ac  mov     r15d, edx
0x18002a3af  mov     r12, rcx
0x18002a3b2  test    edx, edx
0x18002a3b4  jns     loc_18002AB94
0x18002a3ba  mov     [r11+20h], rdi
0x18002a3be  mov     rdi, [rcx+110h]
0x18002a3c5  mov     [r11+10h], rbx
0x18002a3c9  mov     [r11+18h], rsi
0x18002a3cd  mov     [r11-20h], r13
0x18002a3d1  mov     eax, [rdi+48h]
0x18002a3d4  mov     [r11-28h], r14
0x18002a3d8  test    eax, eax
0x18002a3da  jns     loc_18002A8A1
0x18002a3e0  add     rdi, 50h ; 'P'
0x18002a3e4  cmp     eax, [rdi+8]
0x18002a3e7  jnz     loc_18002A8A1
0x18002a3ed  test    rdi, rdi
0x18002a3f0  jz      loc_18002A8A1
0x18002a3f6  xor     ebx, ebx
0x18002a3f8  lea     r9, [rsp+230h+Context]; lpContext
0x18002a3fd  lea     r8, [rsp+230h+fPending]; fPending
0x18002a402  mov     [rsp+230h+Context], rbx
0x18002a407  xor     edx, edx; dwFlags
0x18002a409  mov     [rsp+230h+fPending], ebx
0x18002a40d  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x18002a414  call    cs:__imp_InitOnceBeginInitialize
0x18002a41b  nop     dword ptr [rax+rax+00h]
0x18002a420  test    eax, eax
0x18002a422  jz      loc_18002A525
0x18002a428  cmp     [rsp+230h+fPending], ebx
0x18002a42c  jz      loc_18002A525
0x18002a432  lea     r14, qword_180082988
0x18002a439  mov     cs:qword_180082990, rbx
0x18002a440  lea     rax, ??_7ProfileLogging@@6B@; const ProfileLogging::`vftable'
0x18002a447  mov     [rsp+230h+Context], r14
0x18002a44c  mov     cs:qword_180082988, rax
0x18002a453  mov     cs:byte_180082998, bl
0x18002a459  mov     cs:dword_18008299C, ebx
0x18002a45f  lea     rax, ?__hInner@?1???0StaticHandle@ProfileLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ProfileLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002a466  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cff094b7b3eb7b3291eb3a07719b48ba_@@CA@XZ; void (__cdecl *)()
0x18002a46d  mov     cs:qword_1800829A0, rax
0x18002a474  call    atexit
0x18002a479  mov     rsi, cs:qword_1800829A0
0x18002a480  mov     cs:qword_180082990, rsi
0x18002a487  mov     cs:byte_180082998, 1
0x18002a48e  mov     rax, [rsi+8]
0x18002a492  movups  xmm0, xmmword ptr [rax-10h]
0x18002a496  movups  xmmword ptr [rsp+230h+var_1C8+8], xmm0
0x18002a49b  cmp     [rsi+20h], rbx
0x18002a49f  jz      short loc_18002A4A8
0x18002a4a1  mov     ecx, 5
0x18002a4a6  int     29h; Win8: RtlFailFast(ecx)
0x18002a4a8  lea     r9, [rsi+20h]
0x18002a4ac  mov     [rsi+28h], rbx
0x18002a4b0  mov     r8, rsi
0x18002a4b3  mov     [rsi+30h], rbx
0x18002a4b7  lea     rdx, _tlgEnableCallback
0x18002a4be  lea     rcx, [rsp+230h+var_1C8+8]
0x18002a4c3  call    cs:__imp_EtwEventRegister
0x18002a4ca  nop     dword ptr [rax+rax+00h]
0x18002a4cf  test    eax, eax
0x18002a4d1  jnz     short loc_18002A4F0
0x18002a4d3  mov     r8, [rsi+8]
0x18002a4d7  mov     edx, 2
0x18002a4dc  mov     rcx, [rsi+20h]
0x18002a4e0  movzx   r9d, word ptr [r8]
0x18002a4e4  call    cs:__imp_EtwEventSetInformation
0x18002a4eb  nop     dword ptr [rax+rax+00h]
0x18002a4f0  mov     rax, cs:qword_180082988
0x18002a4f7  mov     rcx, r14
0x18002a4fa  mov     cs:dword_18008299C, 1
0x18002a504  mov     rax, [rax+8]
0x18002a508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a50d  mov     r8, r14; lpContext
0x18002a510  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x18002a517  xor     edx, edx; dwFlags
0x18002a519  call    cs:__imp_InitOnceComplete
0x18002a520  nop     dword ptr [rax+rax+00h]
0x18002a525  mov     rax, [rsp+230h+Context]
0x18002a52a  mov     rdx, [rax+8]
0x18002a52e  mov     [rsp+230h+Context], rdx
0x18002a533  mov     eax, [rdx]
0x18002a535  cmp     eax, 2
0x18002a538  jbe     loc_18002AB6C
0x18002a53e  mov     rcx, [rdx+18h]
0x18002a542  mov     r13, 200000000000h
0x18002a54c  mov     rax, [rdx+10h]
0x18002a550  test    r13, rax
0x18002a553  jz      loc_18002AB6C
0x18002a559  mov     rax, rcx
0x18002a55c  and     rax, r13
0x18002a55f  cmp     rax, rcx
0x18002a562  jnz     loc_18002AB6C
0x18002a568  mov     eax, [rdi+68h]
0x18002a56b  lea     rsi, qword_1800649D8
0x18002a572  mov     rdx, [rdi+78h]
0x18002a576  mov     r8, [rdi+70h]
0x18002a57a  mov     r9, [rdi+60h]
0x18002a57e  mov     r10, [rdi+58h]
0x18002a582  mov     r11, [rdi+48h]
0x18002a586  mov     r14, [rdi+18h]
0x18002a58a  mov     r15, [rdi+80h]
0x18002a591  mov     r12, [rdi+38h]
0x18002a595  mov     [rsp+230h+fPending], eax
0x18002a599  mov     eax, [rdi+50h]
0x18002a59c  mov     [rsp+230h+var_1E8], eax
0x18002a5a0  mov     eax, [rdi+20h]
0x18002a5a3  mov     [rsp+230h+var_1E4], eax
0x18002a5a7  mov     eax, [rdi]
0x18002a5a9  mov     dword ptr [rsp+230h+var_1E0], eax
0x18002a5ad  mov     eax, [rdi+40h]
0x18002a5b0  mov     [rsp+230h+var_1F0], eax
0x18002a5b4  mov     eax, [rdi+8]
0x18002a5b7  mov     [rsp+230h+var_1EC], eax
0x18002a5bb  mov     rax, [rsp+230h+var_1D0]
0x18002a5c0  mov     qword ptr [rsp+230h+var_1C8], 1000000h
0x18002a5c9  mov     rax, [rax+110h]
0x18002a5d0  add     rax, 8
0x18002a5d4  mov     [rsp+230h+var_1D8], rax
0x18002a5d9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002a5e0  test    rdx, rdx
0x18002a5e3  jz      short loc_18002A604
0x18002a5e5  mov     rcx, rax
0x18002a5e8  nop     dword ptr [rax+rax+00000000h]
0x18002a5f0  cmp     [rdx+rcx*2+2], bx
0x18002a5f5  lea     rcx, [rcx+1]
0x18002a5f9  jnz     short loc_18002A5F0
0x18002a5fb  lea     ecx, ds:2[rcx*2]
0x18002a602  jmp     short loc_18002A60C
0x18002a604  mov     rdx, rsi
0x18002a607  mov     ecx, 2
0x18002a60c  mov     [rbp+130h+var_40], rdx
0x18002a613  lea     rdi, qword_180064A78
0x18002a61a  mov     [rbp+130h+var_38], ecx
0x18002a620  mov     [rbp+130h+var_34], ebx
0x18002a626  test    r8, r8
0x18002a629  jz      short loc_18002A63D
0x18002a62b  mov     rcx, rax
0x18002a62e  xchg    ax, ax
0x18002a630  inc     rcx
0x18002a633  cmp     [r8+rcx], bl
0x18002a637  jnz     short loc_18002A630
0x18002a639  inc     ecx
0x18002a63b  jmp     short loc_18002A645
0x18002a63d  mov     r8, rdi
0x18002a640  mov     ecx, 1
0x18002a645  mov     [rbp+130h+var_48], ecx
0x18002a64b  lea     rcx, [rsp+230h+fPending]
0x18002a650  mov     [rbp+130h+var_60], rcx
0x18002a657  mov     [rbp+130h+var_50], r8
0x18002a65e  mov     [rbp+130h+var_44], ebx
0x18002a664  mov     [rbp+130h+var_58], 4
0x18002a66f  test    r9, r9
0x18002a672  jz      short loc_18002A695
0x18002a674  mov     rcx, rax
0x18002a677  nop     word ptr [rax+rax+00000000h]
0x18002a680  cmp     [r9+rcx*2+2], bx
0x18002a686  lea     rcx, [rcx+1]
0x18002a68a  jnz     short loc_18002A680
0x18002a68c  lea     ecx, ds:2[rcx*2]
0x18002a693  jmp     short loc_18002A69D
0x18002a695  mov     r9, rsi
0x18002a698  mov     ecx, 2
0x18002a69d  mov     [rbp+130h+var_70], r9
0x18002a6a4  mov     [rbp+130h+var_68], ecx
0x18002a6aa  mov     [rbp+130h+var_64], ebx
0x18002a6b0  test    r10, r10
0x18002a6b3  jz      short loc_18002A6CD
0x18002a6b5  mov     rcx, rax
0x18002a6b8  nop     dword ptr [rax+rax+00000000h]
0x18002a6c0  inc     rcx
0x18002a6c3  cmp     [r10+rcx], bl
0x18002a6c7  jnz     short loc_18002A6C0
0x18002a6c9  inc     ecx
0x18002a6cb  jmp     short loc_18002A6D5
0x18002a6cd  mov     r10, rdi
0x18002a6d0  mov     ecx, 1
0x18002a6d5  mov     [rbp+130h+var_78], ecx
0x18002a6db  lea     rcx, [rsp+230h+var_1E8]
0x18002a6e0  mov     [rbp+130h+var_90], rcx
0x18002a6e7  mov     [rbp+130h+var_80], r10
0x18002a6ee  mov     [rbp+130h+var_74], ebx
0x18002a6f4  mov     [rbp+130h+var_88], 4
0x18002a6ff  test    r11, r11
0x18002a702  jz      short loc_18002A714
0x18002a704  mov     rcx, rax
0x18002a707  inc     rcx
0x18002a70a  cmp     [r11+rcx], bl
0x18002a70e  jnz     short loc_18002A707
0x18002a710  inc     ecx
0x18002a712  jmp     short loc_18002A71C
0x18002a714  mov     r11, rdi
0x18002a717  mov     ecx, 1
0x18002a71c  mov     [rbp+130h+var_98], ecx
0x18002a722  lea     rcx, [rsp+230h+var_1E4]
0x18002a727  mov     [rbp+130h+var_B0], rcx
0x18002a72e  mov     [rbp+130h+var_A0], r11
0x18002a735  mov     [rbp+130h+var_94], ebx
0x18002a73b  mov     [rbp+130h+var_A8], 4
0x18002a746  test    r14, r14
0x18002a749  jz      short loc_18002A765
0x18002a74b  mov     rcx, rax
0x18002a74e  xchg    ax, ax
0x18002a750  cmp     [r14+rcx*2+2], bx
0x18002a756  lea     rcx, [rcx+1]
0x18002a75a  jnz     short loc_18002A750
0x18002a75c  lea     ecx, ds:2[rcx*2]
0x18002a763  jmp     short loc_18002A76D
0x18002a765  mov     r14, rsi
0x18002a768  mov     ecx, 2
0x18002a76d  mov     [rbp+130h+var_B8], ecx
0x18002a770  lea     rcx, [rsp+230h+var_1E0]
0x18002a775  mov     [rbp+130h+var_D0], rcx
0x18002a779  mov     [rbp+130h+var_C0], r14
0x18002a77d  mov     [rbp+130h+var_B4], ebx
0x18002a780  mov     [rbp+130h+var_C8], 4
0x18002a788  test    r15, r15
0x18002a78b  jz      short loc_18002A79D
0x18002a78d  mov     rcx, rax
0x18002a790  inc     rcx
0x18002a793  cmp     [r15+rcx], bl
0x18002a797  jnz     short loc_18002A790
0x18002a799  inc     ecx
0x18002a79b  jmp     short loc_18002A7A5
0x18002a79d  mov     r15, rdi
0x18002a7a0  mov     ecx, 1
0x18002a7a5  mov     [rbp+130h+var_D8], ecx
0x18002a7a8  lea     rcx, [rsp+230h+var_1F0]
0x18002a7ad  mov     [rbp+130h+var_F0], rcx
0x18002a7b1  mov     [rbp+130h+var_E0], r15
0x18002a7b5  mov     [rbp+130h+var_D4], ebx
0x18002a7b8  mov     [rbp+130h+var_E8], 4
0x18002a7c0  test    r12, r12
0x18002a7c3  jz      short loc_18002A7D2
0x18002a7c5  inc     rax
0x18002a7c8  cmp     [r12+rax], bl
0x18002a7cc  jnz     short loc_18002A7C5
0x18002a7ce  inc     eax
0x18002a7d0  jmp     short loc_18002A7DA
0x18002a7d2  mov     r12, rdi
0x18002a7d5  mov     eax, 1
0x18002a7da  mov     rcx, [rsp+230h+Context]
0x18002a7df  lea     rdx, _TraceLoggingMetadata
0x18002a7e6  mov     [rbp+130h+var_F8], eax
0x18002a7e9  xor     r9d, r9d
0x18002a7ec  mov     [rbp+130h+var_100], r12
0x18002a7f0  lea     rax, [rsp+230h+var_1EC]
0x18002a7f5  mov     [rbp+130h+var_110], rax
0x18002a7f9  lea     rax, [rsp+230h+var_1C8]
0x18002a7fe  mov     [rbp+130h+var_120], rax
0x18002a802  movzx   eax, cs:word_1800713EC
0x18002a809  mov     dword ptr [rsp+230h+var_1C8+0Ch], eax
0x18002a80d  mov     rax, [rcx+8]
0x18002a811  mov     [rbp+130h+var_140], rax
0x18002a815  mov     [rbp+130h+var_F4], ebx
0x18002a818  mov     [rbp+130h+var_108], 4
0x18002a820  mov     [rbp+130h+var_118], 8
0x18002a828  mov     dword ptr [rsp+230h+var_1C8+8], 0B000000h
0x18002a830  mov     qword ptr [rsp+230h+var_1C8+10h], r13
0x18002a835  movzx   eax, word ptr [rax]
0x18002a838  mov     [rbp+130h+var_138], eax
0x18002a83b  lea     rax, word_1800713F6
0x18002a842  mov     [rbp+130h+var_130], rax
0x18002a846  lea     rax, _TraceLoggingMetadataEnd
0x18002a84d  sub     eax, edx
0x18002a84f  mov     [rbp+130h+var_134], 2
0x18002a856  mov     [rbp+130h+var_128], 10Bh
0x18002a85d  lea     rdx, [rsp+230h+var_1C8+8]
0x18002a862  mov     [rbp+130h+var_124], 1
0x18002a869  mov     dword ptr [rsp+230h+Context], eax
0x18002a86d  mov     eax, dword ptr [rsp+230h+Context]
0x18002a871  mov     r8, [rsp+230h+var_1D8]
0x18002a876  lea     rax, [rbp+130h+var_140]
0x18002a87a  mov     rcx, [rcx+20h]
0x18002a87e  mov     qword ptr [rsp+230h+var_208], rax
0x18002a883  mov     dword ptr [rsp+230h+var_210], 11h
0x18002a88b  call    cs:__imp_EtwEventWriteTransfer
0x18002a892  nop     dword ptr [rax+rax+00h]
0x18002a897  mov     r12, [rsp+230h+var_1D0]
0x18002a89c  jmp     loc_18002AB6C
0x18002a8a1  xor     ebx, ebx
0x18002a8a3  lea     r9, [rsp+230h+Context]; lpContext
0x18002a8a8  lea     r8, [rsp+230h+fPending]; fPending
0x18002a8ad  mov     [rsp+230h+Context], rbx
0x18002a8b2  xor     edx, edx; dwFlags
0x18002a8b4  mov     [rsp+230h+fPending], ebx
0x18002a8b8  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x18002a8bf  call    cs:__imp_InitOnceBeginInitialize
0x18002a8c6  nop     dword ptr [rax+rax+00h]
0x18002a8cb  test    eax, eax
  ... truncated ...
```

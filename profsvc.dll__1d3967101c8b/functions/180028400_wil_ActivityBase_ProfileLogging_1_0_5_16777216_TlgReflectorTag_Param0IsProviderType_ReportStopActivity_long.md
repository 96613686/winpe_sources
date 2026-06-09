# wil::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x180028400`
- end: `0x180028bed`
- name: `?ReportStopActivity@?$ActivityBase@VProfileLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `2029`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004408c`
- `0x180045800`

## callees

- `0x180028400`
- `0x18003a730`
- `0x18003aae0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028a61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028a61`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028494`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028919`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028494`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028919`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028587`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028a0c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028587`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028a0c`
- `ntdll!EtwEventWriteTransfer` at `0x1800288eb`
- `ntdll!EtwEventWriteTransfer` at `0x180028b93`
- `ntdll!EtwEventWriteTransfer` at `0x1800288eb`
- `ntdll!EtwEventWriteTransfer` at `0x180028b93`
- `ntdll!EtwEventSetInformation` at `0x180028558`
- `ntdll!EtwEventSetInformation` at `0x1800289dd`
- `ntdll!EtwEventSetInformation` at `0x180028558`
- `ntdll!EtwEventSetInformation` at `0x1800289dd`
- `ntdll!EtwEventRegister` at `0x18002853d`
- `ntdll!EtwEventRegister` at `0x1800289c2`
- `ntdll!EtwEventRegister` at `0x18002853d`
- `ntdll!EtwEventRegister` at `0x1800289c2`

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
  __int64 v51; // [rsp+48h] [rbp-C0h] BYREF
  int v52; // [rsp+50h] [rbp-B8h] BYREF
  int v53; // [rsp+54h] [rbp-B4h] BYREF
  __int64 v54; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD *v56; // [rsp+68h] [rbp-A0h]
  _QWORD v57[3]; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int16 *v58; // [rsp+88h] [rbp-80h] BYREF
  int v59; // [rsp+90h] [rbp-78h]
  int v60; // [rsp+94h] [rbp-74h]
  char *v61; // [rsp+98h] [rbp-70h]
  __int64 v62; // [rsp+A0h] [rbp-68h]
  __int64 *v63; // [rsp+A8h] [rbp-60h]
  __int64 v64; // [rsp+B0h] [rbp-58h]
  char *v65; // [rsp+B8h] [rbp-50h]
  __int64 v66; // [rsp+C0h] [rbp-48h]
  LPVOID *p_Context; // [rsp+C8h] [rbp-40h]
  __int64 v68; // [rsp+D0h] [rbp-38h]
  const unsigned __int16 *v69; // [rsp+D8h] [rbp-30h]
  int v70; // [rsp+E0h] [rbp-28h]
  int v71; // [rsp+E4h] [rbp-24h]
  const unsigned __int16 *v72; // [rsp+E8h] [rbp-20h]
  int v73; // [rsp+F0h] [rbp-18h]
  int v74; // [rsp+F4h] [rbp-14h]
  unsigned __int16 *v75; // [rsp+F8h] [rbp-10h] BYREF
  int v76; // [rsp+100h] [rbp-8h]
  int v77; // [rsp+104h] [rbp-4h]
  __int16 *v78; // [rsp+108h] [rbp+0h]
  __int64 v79; // [rsp+110h] [rbp+8h]
  _QWORD *v80; // [rsp+118h] [rbp+10h]
  __int64 v81; // [rsp+120h] [rbp+18h]
  char *v82; // [rsp+128h] [rbp+20h]
  __int64 v83; // [rsp+130h] [rbp+28h]
  const unsigned __int16 *v84; // [rsp+138h] [rbp+30h]
  int v85; // [rsp+140h] [rbp+38h]
  int v86; // [rsp+144h] [rbp+3Ch]
  __int64 *v87; // [rsp+148h] [rbp+40h]
  __int64 v88; // [rsp+150h] [rbp+48h]
  const unsigned __int16 *v89; // [rsp+158h] [rbp+50h]
  int v90; // [rsp+160h] [rbp+58h]
  int v91; // [rsp+164h] [rbp+5Ch]
  __int64 *v92; // [rsp+168h] [rbp+60h]
  __int64 v93; // [rsp+170h] [rbp+68h]
  const unsigned __int16 *v94; // [rsp+178h] [rbp+70h]
  int v95; // [rsp+180h] [rbp+78h]
  int v96; // [rsp+184h] [rbp+7Ch]
  int *v97; // [rsp+188h] [rbp+80h]
  __int64 v98; // [rsp+190h] [rbp+88h]
  const unsigned __int16 *v99; // [rsp+198h] [rbp+90h]
  int v100; // [rsp+1A0h] [rbp+98h]
  int v101; // [rsp+1A4h] [rbp+9Ch]
  int *v102; // [rsp+1A8h] [rbp+A0h]
  __int64 v103; // [rsp+1B0h] [rbp+A8h]
  const unsigned __int16 *v104; // [rsp+1B8h] [rbp+B0h]
  int v105; // [rsp+1C0h] [rbp+B8h]
  int v106; // [rsp+1C4h] [rbp+BCh]
  const unsigned __int16 *v107; // [rsp+1C8h] [rbp+C0h]
  int v108; // [rsp+1D0h] [rbp+C8h]
  int v109; // [rsp+1D4h] [rbp+CCh]
  WINBOOL *v110; // [rsp+1D8h] [rbp+D0h]
  __int64 v111; // [rsp+1E0h] [rbp+D8h]
  const unsigned __int16 *v112; // [rsp+1E8h] [rbp+E0h]
  int v113; // [rsp+1F0h] [rbp+E8h]
  int v114; // [rsp+1F4h] [rbp+ECh]
  const unsigned __int16 *v115; // [rsp+1F8h] [rbp+F0h]
  int v116; // [rsp+200h] [rbp+F8h]
  int v117; // [rsp+204h] [rbp+FCh]

  v56 = a1;
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
        qword_18007F890 = 0;
        Context = &qword_18007F888;
        qword_18007F888 = (__int64)&ProfileLogging::`vftable';
        byte_18007F898 = 0;
        dword_18007F89C = 0;
        qword_18007F8A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
        v7 = (_QWORD *)qword_18007F8A0;
        qword_18007F890 = qword_18007F8A0;
        byte_18007F898 = 1;
        *(_OWORD *)&v57[1] = *(_OWORD *)(*(_QWORD *)(qword_18007F8A0 + 8) - 16LL);
        if ( *(_QWORD *)(qword_18007F8A0 + 32) )
          __fastfail(5u);
        v8 = qword_18007F8A0 + 32;
        *(_QWORD *)(qword_18007F8A0 + 40) = 0;
        v7[6] = 0;
        if ( !(unsigned int)EtwEventRegister(&v57[1], tlgEnableCallback, v7, v8) )
          EtwEventSetInformation(v7[4], 2, v7[1], *(unsigned __int16 *)v7[1]);
        dword_18007F89C = 1;
        (*(void (__fastcall **)(__int64 *))(qword_18007F888 + 8))(&qword_18007F888);
        InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_18007F888);
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
        v52 = *(_DWORD *)(v6 + 80);
        v53 = *(_DWORD *)(v6 + 32);
        LODWORD(v54) = *(_DWORD *)v6;
        LODWORD(v51) = *(_DWORD *)(v6 + 64);
        HIDWORD(v51) = *(_DWORD *)(v6 + 8);
        v57[0] = 0x1000000;
        v55 = v56[34] + 8LL;
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
          v10 = &qword_180061CC0;
          v21 = 2;
        }
        v115 = v10;
        v116 = v21;
        v117 = 0;
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
          v11 = &word_180061D6E;
          v23 = 1;
        }
        v113 = v23;
        v110 = fPending;
        v112 = v11;
        v114 = 0;
        v111 = 4;
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
          v12 = &qword_180061CC0;
          v25 = 2;
        }
        v107 = v12;
        v108 = v25;
        v109 = 0;
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
          v13 = &word_180061D6E;
          v27 = 1;
        }
        v105 = v27;
        v102 = &v52;
        v104 = v13;
        v106 = 0;
        v103 = 4;
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
          v14 = &word_180061D6E;
          v29 = 1;
        }
        v100 = v29;
        v97 = &v53;
        v99 = v14;
        v101 = 0;
        v98 = 4;
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
          v15 = &qword_180061CC0;
          v31 = 2;
        }
        v95 = v31;
        v92 = &v54;
        v94 = v15;
        v96 = 0;
        v93 = 4;
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
          v16 = &word_180061D6E;
          v33 = 1;
        }
        v90 = v33;
        v87 = &v51;
        v89 = v16;
        v91 = 0;
        v88 = 4;
        if ( v17 )
        {
          do
            ++v18;
          while ( *((_BYTE *)v17 + v18) );
          v34 = v18 + 1;
        }
        else
        {
          v17 = &word_180061D6E;
          v34 = 1;
        }
        v35 = Context;
        v85 = v34;
        v84 = v17;
        v82 = (char *)&v51 + 4;
        v80 = v57;
        v75 = (unsigned __int16 *)*((_QWORD *)Context + 1);
        v86 = 0;
        v83 = 4;
        v81 = 8;
        v57[1] = 0x20B000000LL;
        v57[2] = 0x200000000000LL;
        v76 = *v75;
        v78 = &word_18006E33E;
        v77 = 2;
        v79 = 0x10000010BLL;
        LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(v35[4], &v57[1], v55, 0, 17, &v75, fPending[0], Context, v51);
        v3 = v56;
      }
    }
    else
    {
      Context = 0;
      fPending[0] = 0;
      if ( InitOnceBeginInitialize(&`ProfileLogging::Instance'::`2'::wrapper, 0, fPending, &Context) && fPending[0] )
      {
        qword_18007F890 = 0;
        Context = &qword_18007F888;
        qword_18007F888 = (__int64)&ProfileLogging::`vftable';
        byte_18007F898 = 0;
        dword_18007F89C = 0;
        qword_18007F8A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
        v36 = (_QWORD *)qword_18007F8A0;
        qword_18007F890 = qword_18007F8A0;
        byte_18007F898 = 1;
        *(_OWORD *)&v57[1] = *(_OWORD *)(*(_QWORD *)(qword_18007F8A0 + 8) - 16LL);
        if ( *(_QWORD *)(qword_18007F8A0 + 32) )
          __fastfail(5u);
        v37 = qword_18007F8A0 + 32;
        *(_QWORD *)(qword_18007F8A0 + 40) = 0;
        v36[6] = 0;
        if ( !(unsigned int)EtwEventRegister(&v57[1], tlgEnableCallback, v36, v37) )
          EtwEventSetInformation(v36[4], 2, v36[1], *(unsigned __int16 *)v36[1]);
        dword_18007F89C = 1;
        (*(void (__fastcall **)(__int64 *))(qword_18007F888 + 8))(&qword_18007F888);
        InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_18007F888);
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
        HIDWORD(v51) = a2;
        v44 = -1;
        v55 = 0x1000000;
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
          v40 = &qword_180061CC0;
          v46 = 2;
        }
        v72 = v40;
        v73 = v46;
        v74 = 0;
        if ( v41 )
        {
          do
            ++v44;
          while ( *((_BYTE *)v41 + v44) );
          v47 = v44 + 1;
        }
        else
        {
          v41 = &word_180061D6E;
          v47 = 1;
        }
        v70 = v47;
        v69 = v41;
        p_Context = &Context;
        v71 = 0;
        v65 = (char *)&v51 + 4;
        v63 = &v55;
        v58 = *(unsigned __int16 **)(v38 + 8);
        v68 = 4;
        v66 = 4;
        v64 = 8;
        v57[1] = 0x20B000000LL;
        v57[2] = 0x200000000000LL;
        v59 = *v58;
        v61 = byte_18006E2C3;
        v60 = 2;
        v62 = 0x10000006FLL;
        LODWORD(v51) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(*(_QWORD *)(v38 + 32), &v57[1], v43, 0, 7, &v58, fPending[0], Context, v51);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
}

```

## disassembly

```asm
0x180028400  mov     r11, rsp
0x180028403  push    rbp
0x180028404  push    r12
0x180028406  push    r15
0x180028408  lea     rbp, [r11-138h]
0x18002840f  sub     rsp, 220h
0x180028416  mov     rax, cs:__security_cookie
0x18002841d  xor     rax, rsp
0x180028420  mov     [rbp+130h+var_30], rax
0x180028427  mov     [rsp+230h+var_1D0], rcx
0x18002842c  mov     r15d, edx
0x18002842f  mov     r12, rcx
0x180028432  test    edx, edx
0x180028434  jns     loc_180028BC1
0x18002843a  mov     [r11+20h], rdi
0x18002843e  mov     rdi, [rcx+110h]
0x180028445  mov     [r11+10h], rbx
0x180028449  mov     [r11+18h], rsi
0x18002844d  mov     [r11-20h], r13
0x180028451  mov     eax, [rdi+48h]
0x180028454  mov     [r11-28h], r14
0x180028458  test    eax, eax
0x18002845a  jns     loc_1800288FB
0x180028460  add     rdi, 50h ; 'P'
0x180028464  cmp     eax, [rdi+8]
0x180028467  jnz     loc_1800288FB
0x18002846d  test    rdi, rdi
0x180028470  jz      loc_1800288FB
0x180028476  xor     ebx, ebx
0x180028478  lea     r9, [rsp+230h+Context]; lpContext
0x18002847d  lea     r8, [rsp+230h+fPending]; fPending
0x180028482  mov     [rsp+230h+Context], rbx
0x180028487  xor     edx, edx; dwFlags
0x180028489  mov     [rsp+230h+fPending], ebx
0x18002848d  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x180028494  call    cs:__imp_InitOnceBeginInitialize
0x18002849a  test    eax, eax
0x18002849c  jz      loc_18002858D
0x1800284a2  cmp     [rsp+230h+fPending], ebx
0x1800284a6  jz      loc_18002858D
0x1800284ac  lea     r14, qword_18007F888
0x1800284b3  mov     cs:qword_18007F890, rbx
0x1800284ba  lea     rax, ??_7ProfileLogging@@6B@; const ProfileLogging::`vftable'
0x1800284c1  mov     [rsp+230h+Context], r14
0x1800284c6  mov     cs:qword_18007F888, rax
0x1800284cd  mov     cs:byte_18007F898, bl
0x1800284d3  mov     cs:dword_18007F89C, ebx
0x1800284d9  lea     rax, ?__hInner@?1???0StaticHandle@ProfileLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ProfileLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800284e0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cff094b7b3eb7b3291eb3a07719b48ba_@@CA@XZ; void (__cdecl *)()
0x1800284e7  mov     cs:qword_18007F8A0, rax
0x1800284ee  call    atexit
0x1800284f3  mov     rsi, cs:qword_18007F8A0
0x1800284fa  mov     cs:qword_18007F890, rsi
0x180028501  mov     cs:byte_18007F898, 1
0x180028508  mov     rax, [rsi+8]
0x18002850c  movups  xmm0, xmmword ptr [rax-10h]
0x180028510  movups  xmmword ptr [rsp+230h+var_1C8+8], xmm0
0x180028515  cmp     [rsi+20h], rbx
0x180028519  jz      short loc_180028522
0x18002851b  mov     ecx, 5
0x180028520  int     29h; Win8: RtlFailFast(ecx)
0x180028522  lea     r9, [rsi+20h]
0x180028526  mov     [rsi+28h], rbx
0x18002852a  mov     r8, rsi
0x18002852d  mov     [rsi+30h], rbx
0x180028531  lea     rdx, _tlgEnableCallback
0x180028538  lea     rcx, [rsp+230h+var_1C8+8]
0x18002853d  call    cs:__imp_EtwEventRegister
0x180028543  test    eax, eax
0x180028545  jnz     short loc_18002855E
0x180028547  mov     r8, [rsi+8]
0x18002854b  mov     edx, 2
0x180028550  mov     rcx, [rsi+20h]
0x180028554  movzx   r9d, word ptr [r8]
0x180028558  call    cs:__imp_EtwEventSetInformation
0x18002855e  mov     rax, cs:qword_18007F888
0x180028565  mov     rcx, r14
0x180028568  mov     cs:dword_18007F89C, 1
0x180028572  mov     rax, [rax+8]
0x180028576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002857b  mov     r8, r14; lpContext
0x18002857e  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x180028585  xor     edx, edx; dwFlags
0x180028587  call    cs:__imp_InitOnceComplete
0x18002858d  mov     rax, [rsp+230h+Context]
0x180028592  mov     rdx, [rax+8]
0x180028596  mov     [rsp+230h+Context], rdx
0x18002859b  mov     eax, [rdx]
0x18002859d  cmp     eax, 2
0x1800285a0  jbe     loc_180028B99
0x1800285a6  mov     rcx, [rdx+18h]
0x1800285aa  mov     r13, 200000000000h
0x1800285b4  mov     rax, [rdx+10h]
0x1800285b8  test    r13, rax
0x1800285bb  jz      loc_180028B99
0x1800285c1  mov     rax, rcx
0x1800285c4  and     rax, r13
0x1800285c7  cmp     rax, rcx
0x1800285ca  jnz     loc_180028B99
0x1800285d0  mov     eax, [rdi+68h]
0x1800285d3  lea     rsi, qword_180061CC0
0x1800285da  mov     rdx, [rdi+78h]
0x1800285de  mov     r8, [rdi+70h]
0x1800285e2  mov     r9, [rdi+60h]
0x1800285e6  mov     r10, [rdi+58h]
0x1800285ea  mov     r11, [rdi+48h]
0x1800285ee  mov     r14, [rdi+18h]
0x1800285f2  mov     r15, [rdi+80h]
0x1800285f9  mov     r12, [rdi+38h]
0x1800285fd  mov     [rsp+230h+fPending], eax
0x180028601  mov     eax, [rdi+50h]
0x180028604  mov     [rsp+230h+var_1E8], eax
0x180028608  mov     eax, [rdi+20h]
0x18002860b  mov     [rsp+230h+var_1E4], eax
0x18002860f  mov     eax, [rdi]
0x180028611  mov     dword ptr [rsp+230h+var_1E0], eax
0x180028615  mov     eax, [rdi+40h]
0x180028618  mov     [rsp+230h+var_1F0], eax
0x18002861c  mov     eax, [rdi+8]
0x18002861f  mov     [rsp+230h+var_1EC], eax
0x180028623  mov     rax, [rsp+230h+var_1D0]
0x180028628  mov     qword ptr [rsp+230h+var_1C8], 1000000h
0x180028631  mov     rax, [rax+110h]
0x180028638  add     rax, 8
0x18002863c  mov     [rsp+230h+var_1D8], rax
0x180028641  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180028648  test    rdx, rdx
0x18002864b  jz      short loc_180028664
0x18002864d  mov     rcx, rax
0x180028650  cmp     [rdx+rcx*2+2], bx
0x180028655  lea     rcx, [rcx+1]
0x180028659  jnz     short loc_180028650
0x18002865b  lea     ecx, ds:2[rcx*2]
0x180028662  jmp     short loc_18002866C
0x180028664  mov     rdx, rsi
0x180028667  mov     ecx, 2
0x18002866c  mov     [rbp+130h+var_40], rdx
0x180028673  lea     rdi, word_180061D6E
0x18002867a  mov     [rbp+130h+var_38], ecx
0x180028680  mov     [rbp+130h+var_34], ebx
0x180028686  test    r8, r8
0x180028689  jz      short loc_18002869D
0x18002868b  mov     rcx, rax
0x18002868e  xchg    ax, ax
0x180028690  inc     rcx
0x180028693  cmp     [r8+rcx], bl
0x180028697  jnz     short loc_180028690
0x180028699  inc     ecx
0x18002869b  jmp     short loc_1800286A5
0x18002869d  mov     r8, rdi
0x1800286a0  mov     ecx, 1
0x1800286a5  mov     [rbp+130h+var_48], ecx
0x1800286ab  lea     rcx, [rsp+230h+fPending]
0x1800286b0  mov     [rbp+130h+var_60], rcx
0x1800286b7  mov     [rbp+130h+var_50], r8
0x1800286be  mov     [rbp+130h+var_44], ebx
0x1800286c4  mov     [rbp+130h+var_58], 4
0x1800286cf  test    r9, r9
0x1800286d2  jz      short loc_1800286F5
0x1800286d4  mov     rcx, rax
0x1800286d7  nop     word ptr [rax+rax+00000000h]
0x1800286e0  cmp     [r9+rcx*2+2], bx
0x1800286e6  lea     rcx, [rcx+1]
0x1800286ea  jnz     short loc_1800286E0
0x1800286ec  lea     ecx, ds:2[rcx*2]
0x1800286f3  jmp     short loc_1800286FD
0x1800286f5  mov     r9, rsi
0x1800286f8  mov     ecx, 2
0x1800286fd  mov     [rbp+130h+var_70], r9
0x180028704  mov     [rbp+130h+var_68], ecx
0x18002870a  mov     [rbp+130h+var_64], ebx
0x180028710  test    r10, r10
0x180028713  jz      short loc_18002872D
0x180028715  mov     rcx, rax
0x180028718  nop     dword ptr [rax+rax+00000000h]
0x180028720  inc     rcx
0x180028723  cmp     [r10+rcx], bl
0x180028727  jnz     short loc_180028720
0x180028729  inc     ecx
0x18002872b  jmp     short loc_180028735
0x18002872d  mov     r10, rdi
0x180028730  mov     ecx, 1
0x180028735  mov     [rbp+130h+var_78], ecx
0x18002873b  lea     rcx, [rsp+230h+var_1E8]
0x180028740  mov     [rbp+130h+var_90], rcx
0x180028747  mov     [rbp+130h+var_80], r10
0x18002874e  mov     [rbp+130h+var_74], ebx
0x180028754  mov     [rbp+130h+var_88], 4
0x18002875f  test    r11, r11
0x180028762  jz      short loc_180028774
0x180028764  mov     rcx, rax
0x180028767  inc     rcx
0x18002876a  cmp     [r11+rcx], bl
0x18002876e  jnz     short loc_180028767
0x180028770  inc     ecx
0x180028772  jmp     short loc_18002877C
0x180028774  mov     r11, rdi
0x180028777  mov     ecx, 1
0x18002877c  mov     [rbp+130h+var_98], ecx
0x180028782  lea     rcx, [rsp+230h+var_1E4]
0x180028787  mov     [rbp+130h+var_B0], rcx
0x18002878e  mov     [rbp+130h+var_A0], r11
0x180028795  mov     [rbp+130h+var_94], ebx
0x18002879b  mov     [rbp+130h+var_A8], 4
0x1800287a6  test    r14, r14
0x1800287a9  jz      short loc_1800287C5
0x1800287ab  mov     rcx, rax
0x1800287ae  xchg    ax, ax
0x1800287b0  cmp     [r14+rcx*2+2], bx
0x1800287b6  lea     rcx, [rcx+1]
0x1800287ba  jnz     short loc_1800287B0
0x1800287bc  lea     ecx, ds:2[rcx*2]
0x1800287c3  jmp     short loc_1800287CD
0x1800287c5  mov     r14, rsi
0x1800287c8  mov     ecx, 2
0x1800287cd  mov     [rbp+130h+var_B8], ecx
0x1800287d0  lea     rcx, [rsp+230h+var_1E0]
0x1800287d5  mov     [rbp+130h+var_D0], rcx
0x1800287d9  mov     [rbp+130h+var_C0], r14
0x1800287dd  mov     [rbp+130h+var_B4], ebx
0x1800287e0  mov     [rbp+130h+var_C8], 4
0x1800287e8  test    r15, r15
0x1800287eb  jz      short loc_1800287FD
0x1800287ed  mov     rcx, rax
0x1800287f0  inc     rcx
0x1800287f3  cmp     [r15+rcx], bl
0x1800287f7  jnz     short loc_1800287F0
0x1800287f9  inc     ecx
0x1800287fb  jmp     short loc_180028805
0x1800287fd  mov     r15, rdi
0x180028800  mov     ecx, 1
0x180028805  mov     [rbp+130h+var_D8], ecx
0x180028808  lea     rcx, [rsp+230h+var_1F0]
0x18002880d  mov     [rbp+130h+var_F0], rcx
0x180028811  mov     [rbp+130h+var_E0], r15
0x180028815  mov     [rbp+130h+var_D4], ebx
0x180028818  mov     [rbp+130h+var_E8], 4
0x180028820  test    r12, r12
0x180028823  jz      short loc_180028832
0x180028825  inc     rax
0x180028828  cmp     [r12+rax], bl
0x18002882c  jnz     short loc_180028825
0x18002882e  inc     eax
0x180028830  jmp     short loc_18002883A
0x180028832  mov     r12, rdi
0x180028835  mov     eax, 1
0x18002883a  mov     rcx, [rsp+230h+Context]
0x18002883f  lea     rdx, _TraceLoggingMetadata
0x180028846  mov     [rbp+130h+var_F8], eax
0x180028849  xor     r9d, r9d
0x18002884c  mov     [rbp+130h+var_100], r12
0x180028850  lea     rax, [rsp+230h+var_1EC]
0x180028855  mov     [rbp+130h+var_110], rax
0x180028859  lea     rax, [rsp+230h+var_1C8]
0x18002885e  mov     [rbp+130h+var_120], rax
0x180028862  movzx   eax, cs:word_18006E334
0x180028869  mov     dword ptr [rsp+230h+var_1C8+0Ch], eax
0x18002886d  mov     rax, [rcx+8]
0x180028871  mov     [rbp+130h+var_140], rax
0x180028875  mov     [rbp+130h+var_F4], ebx
0x180028878  mov     [rbp+130h+var_108], 4
0x180028880  mov     [rbp+130h+var_118], 8
0x180028888  mov     dword ptr [rsp+230h+var_1C8+8], 0B000000h
0x180028890  mov     qword ptr [rsp+230h+var_1C8+10h], r13
0x180028895  movzx   eax, word ptr [rax]
0x180028898  mov     [rbp+130h+var_138], eax
0x18002889b  lea     rax, word_18006E33E
0x1800288a2  mov     [rbp+130h+var_130], rax
0x1800288a6  lea     rax, _TraceLoggingMetadataEnd
0x1800288ad  sub     eax, edx
0x1800288af  mov     [rbp+130h+var_134], 2
0x1800288b6  mov     dword ptr [rbp+130h+var_128], 10Bh
0x1800288bd  lea     rdx, [rsp+230h+var_1C8+8]
0x1800288c2  mov     dword ptr [rbp+130h+var_128+4], 1
0x1800288c9  mov     dword ptr [rsp+230h+Context], eax
0x1800288cd  mov     eax, dword ptr [rsp+230h+Context]
0x1800288d1  mov     r8, [rsp+230h+var_1D8]
0x1800288d6  lea     rax, [rbp+130h+var_140]
0x1800288da  mov     rcx, [rcx+20h]
0x1800288de  mov     qword ptr [rsp+230h+var_208], rax
0x1800288e3  mov     dword ptr [rsp+230h+var_210], 11h
0x1800288eb  call    cs:__imp_EtwEventWriteTransfer
0x1800288f1  mov     r12, [rsp+230h+var_1D0]
0x1800288f6  jmp     loc_180028B99
0x1800288fb  xor     ebx, ebx
0x1800288fd  lea     r9, [rsp+230h+Context]; lpContext
0x180028902  lea     r8, [rsp+230h+fPending]; fPending
0x180028907  mov     [rsp+230h+Context], rbx
0x18002890c  xor     edx, edx; dwFlags
0x18002890e  mov     [rsp+230h+fPending], ebx
0x180028912  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x180028919  call    cs:__imp_InitOnceBeginInitialize
0x18002891f  test    eax, eax
0x180028921  jz      loc_180028A12
0x180028927  cmp     [rsp+230h+fPending], ebx
0x18002892b  jz      loc_180028A12
0x180028931  lea     r14, qword_18007F888
0x180028938  mov     cs:qword_18007F890, rbx
0x18002893f  lea     rax, ??_7ProfileLogging@@6B@; const ProfileLogging::`vftable'
0x180028946  mov     [rsp+230h+Context], r14
  ... truncated ...
```

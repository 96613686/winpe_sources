# FindParentDeviceInstanceId(_INIPRINTER *,ushort * *,unsigned __int64 *)

- ea: `0x1800c35c8`
- end: `0x1800c39e0`
- name: `?FindParentDeviceInstanceId@@YAJPEAU_INIPRINTER@@PEAPEAGPEA_K@Z`
- size: `1048`
- prototype: `int(struct _INIPRINTER *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18004fe9c`
- `0x1800c30d0`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x180012610`
- `0x180014d9c`
- `0x180014dd4`
- `0x18003e984`
- `0x180040804`
- `0x180046650`
- `0x1800c35c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c36cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c36cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c38de`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c38de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c36e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c393d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c36e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c393d`
- `SPOOLSS!DllFreeSplStr` at `0x1800c396c`
- `SPOOLSS!DllFreeSplStr` at `0x1800c398c`
- `SPOOLSS!DllFreeSplStr` at `0x1800c396c`
- `SPOOLSS!DllFreeSplStr` at `0x1800c398c`
- `SPOOLSS!AllocSplStr` at `0x1800c363b`
- `SPOOLSS!AllocSplStr` at `0x1800c363b`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x1800c38be`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x1800c38be`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800c3983`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800c3983`

## pseudocode

```c
__int64 __fastcall FindParentDeviceInstanceId(struct _INIPRINTER *a1, unsigned __int16 **a2, unsigned __int64 *a3)
{
  __int64 v6; // rax
  const unsigned __int16 *v7; // r14
  signed int v8; // ebx
  unsigned int *v9; // r15
  __int64 v10; // rcx
  int v11; // eax
  void *v12; // rdx
  int v13; // r12d
  HANDLE EventW; // rax
  void *v15; // rdi
  signed int LastError; // eax
  void *v17; // rcx
  DWORD v18; // eax
  const unsigned __int16 *v19; // rcx
  signed int v20; // eax
  char v22; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v25[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v26; // [rsp+78h] [rbp-88h]
  _DWORD v27[3]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v28; // [rsp+9Ch] [rbp-64h]
  _BYTE v29[28]; // [rsp+ACh] [rbp-54h] BYREF
  int v30; // [rsp+C8h] [rbp-38h]
  __int128 v31; // [rsp+D0h] [rbp-30h]
  int v32; // [rsp+E0h] [rbp-20h]
  int v33; // [rsp+E4h] [rbp-1Ch]
  __int64 v34; // [rsp+E8h] [rbp-18h]
  int v35; // [rsp+F0h] [rbp-10h]
  int v36; // [rsp+F4h] [rbp-Ch]
  const unsigned __int16 *v37; // [rsp+F8h] [rbp-8h]
  int v38; // [rsp+100h] [rbp+0h]
  int v39; // [rsp+108h] [rbp+8h]
  __int128 v40; // [rsp+10Ch] [rbp+Ch]
  _BYTE v41[28]; // [rsp+11Ch] [rbp+1Ch] BYREF
  int v42; // [rsp+138h] [rbp+38h]
  DEVPROPKEY v43; // [rsp+140h] [rbp+40h]
  int v44; // [rsp+154h] [rbp+54h]
  __int64 v45; // [rsp+158h] [rbp+58h]
  int v46; // [rsp+160h] [rbp+60h]
  int v47; // [rsp+164h] [rbp+64h]
  GUID *v48; // [rsp+168h] [rbp+68h]
  int v49; // [rsp+170h] [rbp+70h]
  __int128 v50; // [rsp+178h] [rbp+78h]
  int v51; // [rsp+188h] [rbp+88h]
  int v52; // [rsp+18Ch] [rbp+8Ch]
  __int64 v53; // [rsp+190h] [rbp+90h]
  int v54; // [rsp+198h] [rbp+98h]
  int v55; // [rsp+19Ch] [rbp+9Ch]
  char *v56; // [rsp+1A0h] [rbp+A0h]
  int v57; // [rsp+1A8h] [rbp+A8h]
  int v58; // [rsp+1B0h] [rbp+B0h]
  __int128 v59; // [rsp+1B4h] [rbp+B4h]
  _BYTE v60[28]; // [rsp+1C4h] [rbp+C4h] BYREF
  int v61; // [rsp+1E0h] [rbp+E0h]
  int v62; // [rsp+1E8h] [rbp+E8h]
  __int128 v63; // [rsp+1ECh] [rbp+ECh]
  _BYTE v64[28]; // [rsp+1FCh] [rbp+FCh] BYREF

  *a2 = 0;
  *a3 = 0;
  LocalSpoolerTelemetry::WriteDbgTraceInfo("FindParentDeviceInstanceId", L"pName: %ws", *((_QWORD *)a1 + 3));
  if ( *((_DWORD *)a1 + 77) != 1 )
    return 0;
  v6 = AllocSplStr(*(_QWORD *)(**((_QWORD **)a1 + 39) + 24LL));
  v7 = (const unsigned __int16 *)v6;
  if ( !v6 )
    return (unsigned int)-2147024882;
  LocalSpoolerTelemetry::WriteDbgTraceInfo("FindParentDeviceInstanceId", L"PortName: %ws", v6);
  v9 = (unsigned int *)((char *)a1 + 16);
  if ( SafeIncrementReference((unsigned int *)a1 + 4) > *((_DWORD *)a1 + 62) )
    *((_DWORD *)a1 + 62) = *v9;
  LeaveSplSem(v10);
  v23 = 0;
  v11 = StringCbLengthW(v7, 0x7FFFFFFEu, &v23);
  v13 = v23;
  v8 = v11;
  if ( v11 >= 0 )
    v13 = v23 + 2;
  NCoreLibrary::TAutoHandleNT::TAutoHandleNT((NCoreLibrary::TAutoHandleNT *)&v23, v12);
  if ( v8 < 0 )
  {
    v15 = (void *)v23;
  }
  else
  {
    EventW = CreateEventW(0, 1, 0, 0);
    NCoreLibrary::TAutoHandleNT::operator=(&v23, EventW);
    v15 = (void *)v23;
    if ( v23 == -1 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  v24 = 0;
  *(_OWORD *)v25 = 0;
  v26 = 0;
  if ( v8 < 0 )
    goto LABEL_31;
  v36 = v13;
  DWORD2(v26) = 0;
  v27[2] = 0;
  v17 = v15;
  if ( v15 == (void *)-1LL )
    v17 = 0;
  v22 = -1;
  v32 = 2;
  memset(v29, 0, sizeof(v29));
  *(_QWORD *)&v26 = v17;
  v48 = &GUID_DEVCLASS_PRINTER;
  v51 = 4;
  v56 = &v22;
  v28 = 0;
  v43 = DEVPKEY_Device_ClassGuid;
  v27[0] = 0x100000;
  v31 = xmmword_18011FB00;
  memset(v41, 0, sizeof(v41));
  v40 = 0;
  v30 = 131074;
  v33 = 0;
  v34 = 0;
  v50 = xmmword_18011FB48;
  v35 = 18;
  v37 = v7;
  memset(v60, 0, sizeof(v60));
  v38 = 3145728;
  memset(v64, 0, sizeof(v64));
  v39 = 0;
  v42 = 2;
  v44 = 0;
  v45 = 0;
  v46 = 13;
  v47 = 16;
  v49 = 2;
  v52 = 0;
  v53 = 0;
  v54 = 17;
  v55 = 1;
  v57 = 0x400000;
  v58 = 0;
  v59 = 0;
  v61 = 0x200000;
  v62 = 0;
  v63 = 0;
  v8 = DevCreateObjectQuery(3, 0, 0, 0, 7, v27, ParentDeviceQueryCallback, v25, &v24);
  if ( v8 < 0 )
    goto LABEL_31;
  if ( v15 == (void *)-1LL )
    v15 = 0;
  v18 = WaitForSingleObject(v15, 0xFFFFFFFF);
  if ( v18 )
  {
    if ( v18 == -1 )
    {
      v20 = GetLastError();
      v8 = v20;
      if ( v20 > 0 )
        v8 = (unsigned __int16)v20 | 0x80070000;
      if ( v8 >= 0 )
        goto LABEL_33;
    }
    else
    {
      v8 = -2147418113;
    }
    goto LABEL_31;
  }
  v8 = DWORD2(v26);
  if ( SDWORD2(v26) < 0
    || v25[1]
    && (LocalSpoolerTelemetry::WriteDbgTraceInfo("FindParentDeviceInstanceId", L"Parent Device Instance Id: %ws"),
        v19 = v25[1],
        *a2 = v25[1],
        v8 = StringCbLengthW(v19, 0x190u, a3),
        v8 < 0) )
  {
LABEL_31:
    if ( v25[1] )
    {
      DllFreeSplStr(v25[1]);
      *a2 = 0;
      *a3 = 0;
    }
    goto LABEL_33;
  }
  if ( *a3 )
    *a3 += 2LL;
LABEL_33:
  if ( v24 )
    DevCloseObjectQuery();
  DllFreeSplStr(v7);
  EnterSplSem(0);
  if ( *v9 )
    SafeDecrementReference(v9);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v23);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c35c8  mov     [rsp-8+arg_18], rbx
0x1800c35cd  push    rbp
0x1800c35ce  push    rsi
0x1800c35cf  push    rdi
0x1800c35d0  push    r12
0x1800c35d2  push    r13
0x1800c35d4  push    r14
0x1800c35d6  push    r15
0x1800c35d8  lea     rbp, [rsp-130h]
0x1800c35e0  sub     rsp, 230h
0x1800c35e7  mov     rax, cs:__security_cookie
0x1800c35ee  xor     rax, rsp
0x1800c35f1  mov     [rbp+160h+var_40], rax
0x1800c35f8  xor     edi, edi
0x1800c35fa  mov     rsi, r8
0x1800c35fd  mov     [rdx], rdi
0x1800c3600  mov     r13, rdx
0x1800c3603  mov     [r8], rdi
0x1800c3606  lea     rdx, aPnameWs; "pName: %ws"
0x1800c360d  mov     r8, [rcx+18h]
0x1800c3611  mov     rbx, rcx
0x1800c3614  lea     rcx, aFindparentdevi; "FindParentDeviceInstanceId"
0x1800c361b  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c3620  cmp     dword ptr [rbx+134h], 1
0x1800c3627  jnz     loc_1800C39B2
0x1800c362d  mov     rax, [rbx+138h]
0x1800c3634  mov     rcx, [rax]
0x1800c3637  mov     rcx, [rcx+18h]
0x1800c363b  call    cs:__imp_AllocSplStr
0x1800c3641  mov     r14, rax
0x1800c3644  test    rax, rax
0x1800c3647  jnz     short loc_1800C3653
0x1800c3649  mov     ebx, 8007000Eh
0x1800c364e  jmp     loc_1800C39B4
0x1800c3653  mov     r8, r14
0x1800c3656  lea     rdx, aPortnameWs; "PortName: %ws"
0x1800c365d  lea     rcx, aFindparentdevi; "FindParentDeviceInstanceId"
0x1800c3664  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c3669  lea     r15, [rbx+10h]
0x1800c366d  mov     rcx, r15; unsigned int *
0x1800c3670  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x1800c3675  cmp     eax, [rbx+0F8h]
0x1800c367b  jbe     short loc_1800C3686
0x1800c367d  mov     eax, [r15]
0x1800c3680  mov     [rbx+0F8h], eax
0x1800c3686  call    LeaveSplSem
0x1800c368b  lea     r8, [rsp+260h+var_208]; unsigned __int64 *
0x1800c3690  mov     [rsp+260h+var_208], rdi
0x1800c3695  mov     edx, 7FFFFFFEh; unsigned __int64
0x1800c369a  mov     rcx, r14; unsigned __int16 *
0x1800c369d  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800c36a2  mov     r12, [rsp+260h+var_208]
0x1800c36a7  mov     ebx, eax
0x1800c36a9  test    eax, eax
0x1800c36ab  js      short loc_1800C36B1
0x1800c36ad  add     r12, 2
0x1800c36b1  lea     rcx, [rsp+260h+var_208]; this
0x1800c36b6  call    ??0TAutoHandleNT@NCoreLibrary@@QEAA@PEAX@Z; NCoreLibrary::TAutoHandleNT::TAutoHandleNT(void *)
0x1800c36bb  test    ebx, ebx
0x1800c36bd  js      short loc_1800C3700
0x1800c36bf  xor     r9d, r9d; lpName
0x1800c36c2  xor     r8d, r8d; bInitialState
0x1800c36c5  xor     ecx, ecx; lpEventAttributes
0x1800c36c7  lea     edx, [r9+1]; bManualReset
0x1800c36cb  call    cs:__imp_CreateEventW
0x1800c36d1  mov     rdx, rax
0x1800c36d4  lea     rcx, [rsp+260h+var_208]
0x1800c36d9  call    ??4TAutoHandleNT@NCoreLibrary@@QEAAPEAXPEAX@Z; NCoreLibrary::TAutoHandleNT::operator=(void *)
0x1800c36de  mov     rdi, [rsp+260h+var_208]
0x1800c36e3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800c36e7  jnz     short loc_1800C3705
0x1800c36e9  call    cs:__imp_GetLastError
0x1800c36ef  mov     ebx, eax
0x1800c36f1  test    eax, eax
0x1800c36f3  jle     short loc_1800C3705
0x1800c36f5  movzx   ebx, ax
0x1800c36f8  or      ebx, 80070000h
0x1800c36fe  jmp     short loc_1800C3705
0x1800c3700  mov     rdi, [rsp+260h+var_208]
0x1800c3705  mov     [rsp+260h+var_200], 0
0x1800c370e  xorps   xmm0, xmm0
0x1800c3711  movups  xmmword ptr [rsp+260h+var_1F8], xmm0
0x1800c3716  movups  [rsp+260h+var_1E8], xmm0
0x1800c371b  test    ebx, ebx
0x1800c371d  js      loc_1800C395F
0x1800c3723  movups  xmm1, xmmword ptr cs:DEVPKEY_Device_ClassGuid.fmtid.Data1
0x1800c372a  xor     eax, eax
0x1800c372c  mov     [rbp+160h+var_16C], r12d
0x1800c3730  mov     dword ptr [rbp+160h+var_1E8+8], eax
0x1800c3733  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800c3737  mov     [rbp+160h+var_1C8], eax
0x1800c373a  mov     rcx, rdi
0x1800c373d  cmovz   rcx, rax
0x1800c3741  mov     [rsp+260h+var_210], 0FFh
0x1800c3746  mov     eax, cs:dword_18011FB10
0x1800c374c  xor     r12d, r12d
0x1800c374f  mov     [rbp+160h+var_180], eax
0x1800c3752  xor     edx, edx
0x1800c3754  movups  xmmword ptr [rbp+160h+var_1B4], xmm0
0x1800c3758  lea     rax, GUID_DEVCLASS_PRINTER
0x1800c375f  mov     qword ptr [rsp+260h+var_1E8], rcx
0x1800c3764  mov     ecx, cs:DEVPKEY_Device_ClassGuid.pid
0x1800c376a  xor     r9d, r9d
0x1800c376d  mov     [rbp+160h+var_F8], rax
0x1800c3771  xor     r8d, r8d
0x1800c3774  mov     eax, cs:dword_18011FB58
0x1800c377a  mov     [rbp+160h+var_D8], eax
0x1800c3780  lea     rax, [rsp+260h+var_210]
0x1800c3785  mov     [rbp+160h+var_C0], rax
0x1800c378c  xor     eax, eax
0x1800c378e  movups  [rbp+160h+var_1C4], xmm0
0x1800c3792  lea     rax, [rsp+260h+var_200]
0x1800c3797  mov     [rbp+160h+var_110], ecx
0x1800c379a  mov     [rsp+260h+var_220], rax
0x1800c379f  lea     ecx, [rdx+3]
0x1800c37a2  movups  xmmword ptr [rbp+160h+var_1B4+0Ch], xmm0
0x1800c37a6  lea     rax, [rsp+260h+var_1F8]
0x1800c37ab  mov     [rbp+160h+var_1D0], 100000h
0x1800c37b2  movups  xmm0, cs:xmmword_18011FB00
0x1800c37b9  mov     [rsp+260h+var_228], rax
0x1800c37be  lea     rax, ?ParentDeviceQueryCallback@@YAXPEAX0PEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; ParentDeviceQueryCallback(void *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x1800c37c5  mov     [rsp+260h+var_230], rax
0x1800c37ca  lea     rax, [rbp+160h+var_1D0]
0x1800c37ce  movaps  [rbp+160h+var_190], xmm0
0x1800c37d2  xorps   xmm0, xmm0
0x1800c37d5  movups  xmmword ptr [rbp+160h+var_144], xmm0
0x1800c37d9  mov     [rsp+260h+var_238], rax
0x1800c37de  movups  [rbp+160h+var_154], xmm0
0x1800c37e2  mov     [rsp+260h+var_240], 7
0x1800c37ea  movups  xmmword ptr [rbp+160h+var_144+0Ch], xmm0
0x1800c37ee  mov     [rbp+160h+var_198], 20002h
0x1800c37f5  movups  xmm0, cs:xmmword_18011FB48
0x1800c37fc  mov     [rbp+160h+var_17C], 0
0x1800c3803  mov     [rbp+160h+var_178], 0
0x1800c380b  movups  [rbp+160h+var_E8], xmm0
0x1800c380f  mov     [rbp+160h+var_170], 12h
0x1800c3816  xorps   xmm0, xmm0
0x1800c3819  mov     [rbp+160h+var_168], r14
0x1800c381d  movups  xmmword ptr [rbp+160h+var_9C], xmm0
0x1800c3824  mov     [rbp+160h+var_160], 300000h
0x1800c382b  movups  xmmword ptr [rbp+160h+var_64], xmm0
0x1800c3832  mov     [rbp+160h+var_158], r12d
0x1800c3836  mov     [rbp+160h+var_128], 2
0x1800c383d  movaps  [rbp+160h+var_120], xmm1
0x1800c3841  mov     [rbp+160h+var_10C], r12d
0x1800c3845  mov     [rbp+160h+var_108], r12
0x1800c3849  mov     [rbp+160h+var_100], 0Dh
0x1800c3850  mov     [rbp+160h+var_FC], 10h
0x1800c3857  mov     [rbp+160h+var_F0], 2
0x1800c385e  mov     [rbp+160h+var_D4], r12d
0x1800c3865  mov     [rbp+160h+var_D0], r12
0x1800c386c  mov     [rbp+160h+var_C8], 11h
0x1800c3876  mov     [rbp+160h+var_C4], 1
0x1800c3880  mov     [rbp+160h+var_B8], 400000h
0x1800c388a  mov     [rbp+160h+var_B0], r12d
0x1800c3891  movups  [rbp+160h+var_AC], xmm0
0x1800c3898  mov     [rbp+160h+var_80], 200000h
0x1800c38a2  movups  xmmword ptr [rbp+160h+var_9C+0Ch], xmm0
0x1800c38a9  mov     [rbp+160h+var_78], r12d
0x1800c38b0  movups  [rbp+160h+var_74], xmm0
0x1800c38b7  movups  xmmword ptr [rbp+160h+var_64+0Ch], xmm0
0x1800c38be  call    cs:__imp_DevCreateObjectQuery
0x1800c38c4  mov     ebx, eax
0x1800c38c6  test    eax, eax
0x1800c38c8  js      loc_1800C3962
0x1800c38ce  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800c38d2  cmovz   rdi, r12
0x1800c38d6  or      ebx, 0FFFFFFFFh
0x1800c38d9  mov     edx, ebx; dwMilliseconds
0x1800c38db  mov     rcx, rdi; hHandle
0x1800c38de  call    cs:__imp_WaitForSingleObject
0x1800c38e4  test    eax, eax
0x1800c38e6  jnz     short loc_1800C3939
0x1800c38e8  mov     ebx, dword ptr [rbp+160h+var_1E8+8]
0x1800c38eb  test    ebx, ebx
0x1800c38ed  js      short loc_1800C3962
0x1800c38ef  mov     r8, [rsp+260h+var_1F8+8]
0x1800c38f4  test    r8, r8
0x1800c38f7  jz      short loc_1800C3928
0x1800c38f9  lea     rdx, aParentDeviceIn; "Parent Device Instance Id: %ws"
0x1800c3900  lea     rcx, aFindparentdevi; "FindParentDeviceInstanceId"
0x1800c3907  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c390c  mov     rcx, [rsp+260h+var_1F8+8]; unsigned __int16 *
0x1800c3911  mov     r8, rsi; unsigned __int64 *
0x1800c3914  mov     edx, 190h; unsigned __int64
0x1800c3919  mov     [r13+0], rcx
0x1800c391d  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800c3922  mov     ebx, eax
0x1800c3924  test    eax, eax
0x1800c3926  js      short loc_1800C3962
0x1800c3928  mov     rax, [rsi]
0x1800c392b  test    rax, rax
0x1800c392e  jz      short loc_1800C3979
0x1800c3930  add     rax, 2
0x1800c3934  mov     [rsi], rax
0x1800c3937  jmp     short loc_1800C3979
0x1800c3939  cmp     eax, ebx
0x1800c393b  jnz     short loc_1800C3958
0x1800c393d  call    cs:__imp_GetLastError
0x1800c3943  mov     ebx, eax
0x1800c3945  test    eax, eax
0x1800c3947  jle     short loc_1800C3952
0x1800c3949  movzx   ebx, ax
0x1800c394c  or      ebx, 80070000h
0x1800c3952  test    ebx, ebx
0x1800c3954  js      short loc_1800C3962
0x1800c3956  jmp     short loc_1800C3979
0x1800c3958  mov     ebx, 8000FFFFh
0x1800c395d  jmp     short loc_1800C3962
0x1800c395f  xor     r12d, r12d
0x1800c3962  mov     rcx, [rsp+260h+var_1F8+8]
0x1800c3967  test    rcx, rcx
0x1800c396a  jz      short loc_1800C3979
0x1800c396c  call    cs:__imp_DllFreeSplStr
0x1800c3972  mov     [r13+0], r12
0x1800c3976  mov     [rsi], r12
0x1800c3979  mov     rcx, [rsp+260h+var_200]
0x1800c397e  test    rcx, rcx
0x1800c3981  jz      short loc_1800C3989
0x1800c3983  call    cs:__imp_DevCloseObjectQuery
0x1800c3989  mov     rcx, r14
0x1800c398c  call    cs:__imp_DllFreeSplStr
0x1800c3992  xor     ecx, ecx
0x1800c3994  call    EnterSplSem
0x1800c3999  cmp     [r15], r12d
0x1800c399c  jz      short loc_1800C39A6
0x1800c399e  mov     rcx, r15; unsigned int *
0x1800c39a1  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x1800c39a6  lea     rcx, [rsp+260h+var_208]
0x1800c39ab  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x1800c39b0  jmp     short loc_1800C39B4
0x1800c39b2  mov     ebx, edi
0x1800c39b4  mov     eax, ebx
0x1800c39b6  mov     rcx, [rbp+160h+var_40]
0x1800c39bd  xor     rcx, rsp; StackCookie
0x1800c39c0  call    __security_check_cookie
0x1800c39c5  mov     rbx, [rsp+260h+arg_18]
0x1800c39cd  add     rsp, 230h
0x1800c39d4  pop     r15
0x1800c39d6  pop     r14
0x1800c39d8  pop     r13
0x1800c39da  pop     r12
0x1800c39dc  pop     rdi
0x1800c39dd  pop     rsi
0x1800c39de  pop     rbp
0x1800c39df  retn
```

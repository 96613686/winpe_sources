# SERVER_InitializeFileDataTransfer

- ea: `0x1401a0420`
- end: `0x1401a0b23`
- name: `SERVER_InitializeFileDataTransfer`
- size: `1795`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, installer_update`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000e34c`
- `0x14002a15c`
- `0x14002c2f4`
- `0x1400888ac`
- `0x140088c6c`
- `0x1401989a4`
- `0x140199414`
- `0x140199c84`
- `0x14019b164`
- `0x14019ba34`
- `0x14019bb34`
- `0x1401a0420`
- `0x1401a0f50`
- `0x1401b0928`
- `0x1401b12fc`
- `0x1401b30b0`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401a04db`
- `KERNEL32!GetCurrentThreadId` at `0x1401a0545`
- `KERNEL32!GetCurrentThreadId` at `0x1401a05ae`
- `KERNEL32!GetCurrentThreadId` at `0x1401a061f`
- `KERNEL32!GetCurrentThreadId` at `0x1401a068d`
- `KERNEL32!GetCurrentThreadId` at `0x1401a070b`
- `KERNEL32!GetCurrentThreadId` at `0x1401a04db`
- `KERNEL32!GetCurrentThreadId` at `0x1401a0545`
- `KERNEL32!GetCurrentThreadId` at `0x1401a05ae`
- `KERNEL32!GetCurrentThreadId` at `0x1401a061f`
- `KERNEL32!GetCurrentThreadId` at `0x1401a068d`
- `KERNEL32!GetCurrentThreadId` at `0x1401a070b`

## pseudocode

```c
__int64 __fastcall SERVER_InitializeFileDataTransfer(
        void *a1,
        struct _GUID *a2,
        const struct _FRS_UPDATE *a3,
        struct FRS_SERVER_CONTEXT **a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        unsigned int a8,
        _DWORD *a9,
        _DWORD *a10)
{
  _DWORD *v12; // r14
  _DWORD *v13; // r12
  struct UpstreamTransport *v15; // rbx
  struct FrsStatus *v16; // rsi
  struct FRS_SERVER_CONTEXT *v17; // rdi
  DWORD v18; // eax
  __int64 v19; // rcx
  int v20; // edx
  NetworkGlobals *v21; // rcx
  DWORD v22; // eax
  __int64 v23; // rcx
  DWORD v24; // eax
  __int64 v25; // rcx
  DWORD v26; // eax
  __int64 v27; // rcx
  UpstreamTransport *UpstreamTransport; // rax
  unsigned __int64 v29; // r8
  DWORD CurrentThreadId; // eax
  __int64 v31; // rcx
  DWORD v32; // eax
  __int64 v33; // rcx
  unsigned __int64 v34; // r8
  __int64 v35; // rcx
  struct FrsStatus *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rdx
  unsigned __int64 v39; // r8
  LPCRITICAL_SECTION v40; // rax
  __int64 v41; // rax
  unsigned int v42; // esi
  __int64 v43; // rax
  struct FrsStatus *v44; // [rsp+58h] [rbp-A8h] BYREF
  void *v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v47; // [rsp+70h] [rbp-90h] BYREF
  int v48; // [rsp+78h] [rbp-88h]
  int v49; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v50; // [rsp+80h] [rbp-80h]
  struct _GUID *v51; // [rsp+88h] [rbp-78h]
  int v52; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v53; // [rsp+94h] [rbp-6Ch]
  UpstreamTransport *v54; // [rsp+98h] [rbp-68h] BYREF
  __int128 v55; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-50h]
  __int128 v57; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v58; // [rsp+C8h] [rbp-38h]
  __int128 v59; // [rsp+E8h] [rbp-18h]
  int v60; // [rsp+11Ch] [rbp+1Ch]
  int v61; // [rsp+120h] [rbp+20h]
  char v62; // [rsp+138h] [rbp+38h]
  _BYTE v63[532]; // [rsp+13Ch] [rbp+3Ch] BYREF

  v12 = a9;
  v13 = a10;
  v46 = a7;
  v53 = a8;
  v51 = a2;
  v45 = a1;
  if ( !Settings::GhostingEnabled )
    return 50;
  v15 = 0;
  v16 = 0;
  v54 = 0;
  v44 = 0;
  v17 = 0;
  memset_0(&v55, 0, 0x2A8u);
  v61 = 0;
  v60 = 3;
  if ( a3 && a4 && v46 && v12 && v13
    || (v18 = GetCurrentThreadId(),
        v44 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v19,
                                    87,
                                    0,
                                    1,
                                    "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                    "SERVER_InitializeFileDataTransfer",
                                    1372,
                                    v18,
                                    0),
        (v16 = v44) == 0) )
  {
    *a4 = 0;
    *v12 = 0;
    *v13 = 0;
    if ( Settings::GhostingEnabled
      || (v22 = GetCurrentThreadId(),
          v44 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                      v23,
                                      9305,
                                      0,
                                      3,
                                      "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                      "SERVER_InitializeFileDataTransfer",
                                      1383,
                                      v22,
                                      0),
          (v16 = v44) == 0) )
    {
      if ( !isInBackupRestore
        || !*isInBackupRestore
        || (v24 = GetCurrentThreadId(),
            v44 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                        v25,
                                        9036,
                                        0,
                                        3,
                                        "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                        "SERVER_InitializeFileDataTransfer",
                                        1387,
                                        v24,
                                        0),
            (v16 = v44) == 0) )
      {
        ID_UPDATE::Set((ID_UPDATE *)&v55, a3);
        if ( (v62 & 8) != 0
          || (v62 & 4) != 0
          || (v26 = GetCurrentThreadId(),
              v44 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                          v27,
                                          87,
                                          0,
                                          1,
                                          "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                          "SERVER_InitializeFileDataTransfer",
                                          1400,
                                          v26,
                                          0),
              (v16 = v44) == 0) )
        {
          UpstreamTransport = NetworkGlobals::FindUpstreamTransport(v21, v45, v51);
          v54 = UpstreamTransport;
          v15 = UpstreamTransport;
          if ( UpstreamTransport )
          {
            UpstreamTransport::CountBytes(UpstreamTransport, 0x2CCu, v29);
          }
          else
          {
            CurrentThreadId = GetCurrentThreadId();
            v16 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                        v31,
                                        9026,
                                        0,
                                        3,
                                        "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                        "SERVER_InitializeFileDataTransfer",
                                        1410,
                                        CurrentThreadId,
                                        0);
            v44 = v16;
          }
        }
      }
    }
  }
  if ( v16 )
    goto LABEL_55;
  v17 = NetworkGlobals::ReserveFileTransfer(v21, v51, v15, (struct ID_UPDATE *)&v55);
  if ( !v17 )
  {
    v32 = GetCurrentThreadId();
    v44 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v33,
                                9078,
                                0,
                                3,
                                "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                "SERVER_InitializeFileDataTransfer",
                                1425,
                                v32,
                                0);
    v16 = v44;
    if ( v44 )
      goto LABEL_55;
  }
  v52 = 0;
  v45 = v17;
  *((_OWORD *)v17 + 6) = v57;
  *((_QWORD *)v17 + 14) = v58;
  *(_OWORD *)((char *)v17 + 72) = v55;
  *((_QWORD *)v17 + 11) = v56;
  *((_OWORD *)v17 + 2) = v59;
  *a4 = v17;
  RefCountObject::AddRef(v17);
  v44 = (struct FrsStatus *)UpstreamTransport::OpenFile(
                              (_DWORD)v15,
                              0,
                              (unsigned int)&v55,
                              (unsigned int)&v52,
                              0,
                              (__int64)&v45,
                              a5,
                              a6);
  v16 = v44;
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v45);
  ID_UPDATE::Get((ID_UPDATE *)&v55, a3);
  if ( v44 )
  {
LABEL_55:
    v40 = g_DebugLog;
    goto LABEL_56;
  }
  v35 = *((_QWORD *)v17 + 40);
  if ( v35 )
  {
    if ( (v62 & 1) != 0 )
    {
      v36 = (struct FrsStatus *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _DWORD *))(*(_QWORD *)v35 + 8LL))(
                                  v35,
                                  v46,
                                  v53,
                                  v12);
      v37 = *((_QWORD *)v17 + 40);
      v16 = v36;
      v44 = v36;
      *v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 24LL))(v37);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v48 = 1477;
        v47 = L"SERVER_InitializeFileDataTransfer";
        v49 = 5;
        v50 = L"SRTR";
        dbgobj::DbgPrint<unsigned short,unsigned short [261],unsigned long>(&v47, v38, v63, v12);
      }
      UpstreamTransport::CountBytes(v15, (unsigned int)*v12, v39);
      v40 = g_DebugLog;
    }
    else
    {
      v40 = g_DebugLog;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v48 = 1489;
        v47 = L"SERVER_InitializeFileDataTransfer";
        v49 = 5;
        v50 = L"SRTR";
        dbgobj::DbgPrint<unsigned short,GVSN>(&v47, L"Tombstone %?", &v55);
        v40 = g_DebugLog;
      }
      *v13 = 1;
      *v12 = 0;
    }
    if ( *v13 )
    {
      SERVER_RdcClose(a4);
      v40 = g_DebugLog;
      v17 = 0;
    }
    if ( !v16 )
      goto LABEL_41;
LABEL_56:
    if ( *a4 )
    {
      SERVER_RdcClose(a4);
      v40 = g_DebugLog;
      v17 = 0;
    }
    if ( v40 && LODWORD(v40[1].LockSemaphore) && SLODWORD(v40[1].OwningThread) >= 3 )
    {
      v48 = 1507;
      v47 = L"SERVER_InitializeFileDataTransfer";
      v50 = L"SRTR";
      v49 = 3;
      if ( v17 )
        v43 = *((_QWORD *)v17 + 40);
      else
        v43 = 0;
      v46 = v43;
      v45 = v17;
      dbgobj::DbgPrint<unsigned short,_GUID,unsigned __int64,unsigned __int64,UID,GVSN,unsigned __int64,unsigned __int64,FrsStatus>(
        (unsigned int)&v47,
        v20,
        (_DWORD)v51,
        (unsigned int)&v45,
        (__int64)&v46,
        (__int64)&v55,
        (__int64)&v57,
        (__int64)&a5,
        (__int64)&a6,
        (__int64)v16);
    }
    v42 = *((_DWORD *)v16 + 1);
    CLEAR_ERROR(&v44);
    goto LABEL_49;
  }
  v40 = g_DebugLog;
LABEL_41:
  if ( v40 && LODWORD(v40[1].LockSemaphore) && SLODWORD(v40[1].OwningThread) >= 4 )
  {
    v48 = 1522;
    v47 = L"SERVER_InitializeFileDataTransfer";
    v50 = L"SRTR";
    v49 = 4;
    if ( v17 )
      v41 = *((_QWORD *)v17 + 40);
    else
      v41 = 0;
    v46 = v41;
    v45 = v17;
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned __int64,unsigned __int64,UID,GVSN,unsigned __int64,unsigned __int64>(
      (unsigned int)&v47,
      v20,
      (_DWORD)v51,
      (unsigned int)&v45,
      (__int64)&v46,
      (__int64)&v55,
      (__int64)&v57,
      (__int64)&a5,
      (__int64)&a6);
  }
  v42 = 0;
LABEL_49:
  if ( v15 && v12 )
    UpstreamTransport::CountBytes(v15, (unsigned int)*v12, v34);
  if ( v17 )
    FRS_SERVER_CONTEXT::SetIdle(v17);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v54);
  return v42;
}

```

## disassembly

```asm
0x1401a0420  push    rbp
0x1401a0422  push    rbx
0x1401a0423  push    rsi
0x1401a0424  push    rdi
0x1401a0425  push    r12
0x1401a0427  push    r13
0x1401a0429  push    r14
0x1401a042b  push    r15
0x1401a042d  lea     rbp, [rsp-268h]
0x1401a0435  sub     rsp, 368h
0x1401a043c  mov     rax, cs:__security_cookie
0x1401a0443  xor     rax, rsp
0x1401a0446  mov     [rbp+2A0h+var_50], rax
0x1401a044d  cmp     cs:?GhostingEnabled@Settings@@3VGenericBoolSetting@1@A, 0; Settings::GenericBoolSetting Settings::GhostingEnabled
0x1401a0454  mov     r15, r9
0x1401a0457  mov     rax, [rbp+2A0h+arg_30]
0x1401a045e  mov     r13, r8
0x1401a0461  mov     r14, [rbp+2A0h+arg_40]
0x1401a0468  mov     r12, [rbp+2A0h+arg_48]
0x1401a046f  mov     [rsp+3A0h+var_338], rax
0x1401a0474  mov     eax, [rbp+2A0h+arg_38]
0x1401a047a  mov     [rbp+2A0h+var_30C], eax
0x1401a047d  mov     [rbp+2A0h+var_318], rdx
0x1401a0481  mov     [rsp+3A0h+var_340], rcx
0x1401a0486  jnz     short loc_1401A0492
0x1401a0488  mov     eax, 32h ; '2'
0x1401a048d  jmp     loc_1401A0A21
0x1401a0492  xor     ebx, ebx
0x1401a0494  lea     rcx, [rbp+2A0h+var_300]; void *
0x1401a0498  and     [rsp+3A0h+var_350], ebx
0x1401a049c  xor     esi, esi
0x1401a049e  xor     edx, edx; Val
0x1401a04a0  mov     [rbp+2A0h+var_308], rbx
0x1401a04a4  mov     r8d, 2A8h; Size
0x1401a04aa  mov     [rsp+3A0h+var_348], rsi
0x1401a04af  xor     edi, edi
0x1401a04b1  call    memset_0
0x1401a04b6  and     [rbp+2A0h+var_280], ebx
0x1401a04b9  mov     [rbp+2A0h+var_284], 3
0x1401a04c0  test    r13, r13
0x1401a04c3  jz      short loc_1401A04DB
0x1401a04c5  test    r15, r15
0x1401a04c8  jz      short loc_1401A04DB
0x1401a04ca  cmp     [rsp+3A0h+var_338], rbx
0x1401a04cf  jz      short loc_1401A04DB
0x1401a04d1  test    r14, r14
0x1401a04d4  jz      short loc_1401A04DB
0x1401a04d6  test    r12, r12
0x1401a04d9  jnz     short loc_1401A0533
0x1401a04db  call    cs:__imp_GetCurrentThreadId
0x1401a04e2  nop     dword ptr [rax+rax+00h]
0x1401a04e7  and     [rsp+3A0h+var_360], rbx
0x1401a04ec  mov     r9d, 1
0x1401a04f2  mov     dword ptr [rsp+3A0h+var_368], eax
0x1401a04f6  xor     r8d, r8d
0x1401a04f9  lea     rax, aServerInitiali; "SERVER_InitializeFileDataTransfer"
0x1401a0500  mov     dword ptr [rsp+3A0h+var_370], 55Ch
0x1401a0508  mov     [rsp+3A0h+var_378], rax
0x1401a050d  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a0514  lea     edx, [r9+56h]
0x1401a0518  mov     [rsp+3A0h+var_380], rax
0x1401a051d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a0522  mov     [rsp+3A0h+var_348], rax
0x1401a0527  mov     rsi, rax
0x1401a052a  test    rax, rax
0x1401a052d  jnz     loc_1401A06EA
0x1401a0533  and     [r15], rbx
0x1401a0536  and     [r14], ebx
0x1401a0539  and     [r12], ebx
0x1401a053d  cmp     cs:?GhostingEnabled@Settings@@3VGenericBoolSetting@1@A, ebx; Settings::GenericBoolSetting Settings::GhostingEnabled
0x1401a0543  jnz     short loc_1401A059E
0x1401a0545  call    cs:__imp_GetCurrentThreadId
0x1401a054c  nop     dword ptr [rax+rax+00h]
0x1401a0551  and     [rsp+3A0h+var_360], rbx
0x1401a0556  mov     r9d, 3
0x1401a055c  mov     dword ptr [rsp+3A0h+var_368], eax
0x1401a0560  xor     r8d, r8d
0x1401a0563  lea     rax, aServerInitiali; "SERVER_InitializeFileDataTransfer"
0x1401a056a  mov     dword ptr [rsp+3A0h+var_370], 567h
0x1401a0572  mov     [rsp+3A0h+var_378], rax
0x1401a0577  mov     edx, 2459h
0x1401a057c  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a0583  mov     [rsp+3A0h+var_380], rax
0x1401a0588  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a058d  mov     [rsp+3A0h+var_348], rax
0x1401a0592  mov     rsi, rax
0x1401a0595  test    rax, rax
0x1401a0598  jnz     loc_1401A06EA
0x1401a059e  mov     rax, cs:?isInBackupRestore@@3PEAHEA; int * isInBackupRestore
0x1401a05a5  test    rax, rax
0x1401a05a8  jz      short loc_1401A0607
0x1401a05aa  cmp     [rax], ebx
0x1401a05ac  jz      short loc_1401A0607
0x1401a05ae  call    cs:__imp_GetCurrentThreadId
0x1401a05b5  nop     dword ptr [rax+rax+00h]
0x1401a05ba  and     [rsp+3A0h+var_360], rbx
0x1401a05bf  mov     r9d, 3
0x1401a05c5  mov     dword ptr [rsp+3A0h+var_368], eax
0x1401a05c9  xor     r8d, r8d
0x1401a05cc  lea     rax, aServerInitiali; "SERVER_InitializeFileDataTransfer"
0x1401a05d3  mov     dword ptr [rsp+3A0h+var_370], 56Bh
0x1401a05db  mov     [rsp+3A0h+var_378], rax
0x1401a05e0  mov     edx, 234Ch
0x1401a05e5  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a05ec  mov     [rsp+3A0h+var_380], rax
0x1401a05f1  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a05f6  mov     [rsp+3A0h+var_348], rax
0x1401a05fb  mov     rsi, rax
0x1401a05fe  test    rax, rax
0x1401a0601  jnz     loc_1401A06EA
0x1401a0607  mov     rdx, r13; struct _FRS_UPDATE *
0x1401a060a  lea     rcx, [rbp+2A0h+var_300]; this
0x1401a060e  call    ?Set@ID_UPDATE@@QEAAXAEBU_FRS_UPDATE@@@Z; ID_UPDATE::Set(_FRS_UPDATE const &)
0x1401a0613  test    [rbp+2A0h+var_268], 8
0x1401a0617  jnz     short loc_1401A0673
0x1401a0619  test    [rbp+2A0h+var_268], 4
0x1401a061d  jnz     short loc_1401A0673
0x1401a061f  call    cs:__imp_GetCurrentThreadId
0x1401a0626  nop     dword ptr [rax+rax+00h]
0x1401a062b  and     [rsp+3A0h+var_360], rbx
0x1401a0630  mov     r9d, 1
0x1401a0636  mov     dword ptr [rsp+3A0h+var_368], eax
0x1401a063a  xor     r8d, r8d
0x1401a063d  lea     rax, aServerInitiali; "SERVER_InitializeFileDataTransfer"
0x1401a0644  mov     dword ptr [rsp+3A0h+var_370], 578h
0x1401a064c  mov     [rsp+3A0h+var_378], rax
0x1401a0651  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a0658  lea     edx, [r9+56h]
0x1401a065c  mov     [rsp+3A0h+var_380], rax
0x1401a0661  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a0666  mov     [rsp+3A0h+var_348], rax
0x1401a066b  mov     rsi, rax
0x1401a066e  test    rax, rax
0x1401a0671  jnz     short loc_1401A06EA
0x1401a0673  mov     r8, [rbp+2A0h+var_318]; struct _GUID *
0x1401a0677  mov     rdx, [rsp+3A0h+var_340]; void *
0x1401a067c  call    ?FindUpstreamTransport@NetworkGlobals@@QEAAPEAVUpstreamTransport@@PEAXAEBU_GUID@@@Z; NetworkGlobals::FindUpstreamTransport(void *,_GUID const &)
0x1401a0681  mov     [rbp+2A0h+var_308], rax
0x1401a0685  mov     rbx, rax
0x1401a0688  test    rax, rax
0x1401a068b  jnz     short loc_1401A06DD
0x1401a068d  call    cs:__imp_GetCurrentThreadId
0x1401a0694  nop     dword ptr [rax+rax+00h]
0x1401a0699  and     [rsp+3A0h+var_360], rdi
0x1401a069e  lea     r9d, [rbx+3]
0x1401a06a2  mov     dword ptr [rsp+3A0h+var_368], eax
0x1401a06a6  xor     r8d, r8d
0x1401a06a9  lea     rax, aServerInitiali; "SERVER_InitializeFileDataTransfer"
0x1401a06b0  mov     dword ptr [rsp+3A0h+var_370], 582h
0x1401a06b8  mov     [rsp+3A0h+var_378], rax
0x1401a06bd  mov     edx, 2342h
0x1401a06c2  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a06c9  mov     [rsp+3A0h+var_380], rax
0x1401a06ce  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a06d3  mov     rsi, rax
0x1401a06d6  mov     [rsp+3A0h+var_348], rax
0x1401a06db  jmp     short loc_1401A06EA
0x1401a06dd  mov     edx, 2CCh; unsigned __int64
0x1401a06e2  mov     rcx, rax; this
0x1401a06e5  call    ?CountBytes@UpstreamTransport@@QEAAX_K0@Z; UpstreamTransport::CountBytes(unsigned __int64,unsigned __int64)
0x1401a06ea  test    rsi, rsi
0x1401a06ed  jnz     loc_1401A0A45
0x1401a06f3  mov     rdx, [rbp+2A0h+var_318]; struct _GUID *
0x1401a06f7  lea     r9, [rbp+2A0h+var_300]; struct ID_UPDATE *
0x1401a06fb  mov     r8, rbx; struct UpstreamTransport *
0x1401a06fe  call    ?ReserveFileTransfer@NetworkGlobals@@QEAAPEAVFRS_SERVER_CONTEXT@@AEBU_GUID@@PEAVUpstreamTransport@@AEAVID_UPDATE@@@Z; NetworkGlobals::ReserveFileTransfer(_GUID const &,UpstreamTransport *,ID_UPDATE &)
0x1401a0703  mov     rdi, rax
0x1401a0706  test    rax, rax
0x1401a0709  jnz     short loc_1401A0762
0x1401a070b  call    cs:__imp_GetCurrentThreadId
0x1401a0712  nop     dword ptr [rax+rax+00h]
0x1401a0717  and     [rsp+3A0h+var_360], rdi
0x1401a071c  lea     r9d, [rsi+3]
0x1401a0720  mov     dword ptr [rsp+3A0h+var_368], eax
0x1401a0724  xor     r8d, r8d
0x1401a0727  lea     rax, aServerInitiali; "SERVER_InitializeFileDataTransfer"
0x1401a072e  mov     dword ptr [rsp+3A0h+var_370], 591h
0x1401a0736  mov     [rsp+3A0h+var_378], rax
0x1401a073b  mov     edx, 2376h
0x1401a0740  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a0747  mov     [rsp+3A0h+var_380], rax
0x1401a074c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a0751  mov     [rsp+3A0h+var_348], rax
0x1401a0756  mov     rsi, rax
0x1401a0759  test    rax, rax
0x1401a075c  jnz     loc_1401A0A45
0x1401a0762  movups  xmm0, [rbp+2A0h+var_2E8]
0x1401a0766  and     [rbp+2A0h+var_310], 0
0x1401a076a  mov     rcx, rdi; this
0x1401a076d  mov     [rsp+3A0h+var_340], rdi
0x1401a0772  movdqu  xmmword ptr [rdi+60h], xmm0
0x1401a0777  mov     rax, [rbp+2A0h+var_2D8]
0x1401a077b  mov     [rdi+70h], rax
0x1401a077f  movaps  xmm0, [rbp+2A0h+var_300]
0x1401a0783  movdqu  xmmword ptr [rdi+48h], xmm0
0x1401a0788  mov     rax, [rbp+2A0h+var_2F0]
0x1401a078c  mov     [rdi+58h], rax
0x1401a0790  movups  xmm0, [rbp+2A0h+var_2B8]
0x1401a0794  movdqu  xmmword ptr [rdi+20h], xmm0
0x1401a0799  mov     [r15], rdi
0x1401a079c  call    ?AddRef@RefCountObject@@QEAAJXZ; RefCountObject::AddRef(void)
0x1401a07a1  mov     rax, [rbp+2A0h+arg_28]
0x1401a07a8  lea     r9, [rbp+2A0h+var_310]
0x1401a07ac  mov     [rsp+3A0h+var_368], rax
0x1401a07b1  lea     r8, [rbp+2A0h+var_300]
0x1401a07b5  mov     rax, [rbp+2A0h+arg_20]
0x1401a07bc  xor     edx, edx
0x1401a07be  mov     [rsp+3A0h+var_370], rax
0x1401a07c3  mov     rcx, rbx
0x1401a07c6  lea     rax, [rsp+3A0h+var_340]
0x1401a07cb  mov     [rsp+3A0h+var_378], rax
0x1401a07d0  and     [rsp+3A0h+var_380], 0
0x1401a07d6  call    ?OpenFile@UpstreamTransport@@QEAAPEAVFrsStatus@@HAEAVID_UPDATE@@PEAW4__MIDL___MIDL_itf_frstransport_0000_0000_0009@@PEAUMyFRS_RDC_FILEINFO@Rdc@@AEAV?$ScopedRef@VFRS_SERVER_CONTEXT@@@@_K4@Z; UpstreamTransport::OpenFile(int,ID_UPDATE &,__MIDL___MIDL_itf_frstransport_0000_0000_0009 *,Rdc::MyFRS_RDC_FILEINFO *,ScopedRef<FRS_SERVER_CONTEXT> &,unsigned __int64,unsigned __int64)
0x1401a07db  lea     rcx, [rsp+3A0h+var_340]
0x1401a07e0  mov     [rsp+3A0h+var_348], rax
0x1401a07e5  mov     rsi, rax
0x1401a07e8  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1401a07ed  mov     rdx, r13; struct _FRS_UPDATE *
0x1401a07f0  lea     rcx, [rbp+2A0h+var_300]; this
0x1401a07f4  call    ?Get@ID_UPDATE@@QEBAXAEAU_FRS_UPDATE@@@Z; ID_UPDATE::Get(_FRS_UPDATE &)
0x1401a07f9  xor     r13d, r13d
0x1401a07fc  test    rsi, rsi
0x1401a07ff  jnz     loc_1401A0A48
0x1401a0805  mov     rcx, [rdi+140h]
0x1401a080c  test    rcx, rcx
0x1401a080f  jz      loc_1401A0943
0x1401a0815  test    [rbp+2A0h+var_268], 1
0x1401a0819  jz      loc_1401A08BA
0x1401a081f  mov     rax, [rcx]
0x1401a0822  mov     r9, r14
0x1401a0825  mov     r8d, [rbp+2A0h+var_30C]
0x1401a0829  mov     rdx, [rsp+3A0h+var_338]
0x1401a082e  mov     rax, [rax+8]
0x1401a0832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a0837  mov     rcx, [rdi+140h]
0x1401a083e  mov     rsi, rax
0x1401a0841  mov     [rsp+3A0h+var_348], rax
0x1401a0846  mov     rax, [rcx]
0x1401a0849  mov     rax, [rax+18h]
0x1401a084d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a0852  mov     [r12], eax
0x1401a0856  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a085d  test    rax, rax
0x1401a0860  jz      short loc_1401A08A6
0x1401a0862  cmp     [rax+40h], r13d
0x1401a0866  jz      short loc_1401A08A6
0x1401a0868  cmp     dword ptr [rax+38h], 5
0x1401a086c  jl      short loc_1401A08A6
0x1401a086e  lea     rax, aServerInitiali_0; "SERVER_InitializeFileDataTransfer"
0x1401a0875  mov     [rsp+3A0h+var_328], 5C5h
0x1401a087d  mov     [rsp+3A0h+var_330], rax
0x1401a0882  lea     r8, [rbp+2A0h+var_264]
0x1401a0886  lea     rax, aSrtr; "SRTR"
0x1401a088d  mov     [rsp+3A0h+var_324], 5
0x1401a0895  mov     r9, r14
0x1401a0898  mov     [rbp+2A0h+var_320], rax
0x1401a089c  lea     rcx, [rsp+3A0h+var_330]
0x1401a08a1  call    ??$DbgPrint@G$$BY0BAF@GK@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBK@Z; dbgobj::DbgPrint<ushort,ushort [261],ulong>(ushort const *,ushort const (&)[261],ulong const &)
0x1401a08a6  mov     edx, [r14]; unsigned __int64
0x1401a08a9  mov     rcx, rbx; this
0x1401a08ac  call    ?CountBytes@UpstreamTransport@@QEAAX_K0@Z; UpstreamTransport::CountBytes(unsigned __int64,unsigned __int64)
0x1401a08b1  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a08b8  jmp     short loc_1401A0920
0x1401a08ba  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a08c1  test    rax, rax
0x1401a08c4  jz      short loc_1401A0915
0x1401a08c6  cmp     [rax+40h], r13d
0x1401a08ca  jz      short loc_1401A0915
0x1401a08cc  cmp     dword ptr [rax+38h], 5
0x1401a08d0  jl      short loc_1401A0915
0x1401a08d2  lea     rax, aServerInitiali_0; "SERVER_InitializeFileDataTransfer"
0x1401a08d9  mov     [rsp+3A0h+var_328], 5D1h
0x1401a08e1  mov     [rsp+3A0h+var_330], rax
0x1401a08e6  lea     r8, [rbp+2A0h+var_300]
0x1401a08ea  lea     rax, aSrtr; "SRTR"
0x1401a08f1  mov     [rsp+3A0h+var_324], 5
0x1401a08f9  lea     rdx, aTombstone; "Tombstone %?"
0x1401a0900  mov     [rbp+2A0h+var_320], rax
0x1401a0904  lea     rcx, [rsp+3A0h+var_330]
0x1401a0909  call    ??$DbgPrint@GVGVSN@@@dbgobj@@QEAA_KPEBGAEBVGVSN@@@Z; dbgobj::DbgPrint<ushort,GVSN>(ushort const *,GVSN const &)
0x1401a090e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a0915  mov     dword ptr [r12], 1
0x1401a091d  mov     [r14], r13d
0x1401a0920  cmp     [r12], r13d
0x1401a0924  jz      short loc_1401A0938
0x1401a0926  mov     rcx, r15
0x1401a0929  call    SERVER_RdcClose
0x1401a092e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a0935  mov     rdi, r13
0x1401a0938  test    rsi, rsi
0x1401a093b  jnz     loc_1401A0A4F
0x1401a0941  jmp     short loc_1401A094A
0x1401a0943  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a094a  test    rax, rax
0x1401a094d  jz      loc_1401A09F0
0x1401a0953  cmp     [rax+40h], r13d
0x1401a0957  jz      loc_1401A09F0
0x1401a095d  cmp     dword ptr [rax+38h], 4
0x1401a0961  jl      loc_1401A09F0
0x1401a0967  mov     [rsp+3A0h+var_328], 5F2h
  ... truncated ...
```

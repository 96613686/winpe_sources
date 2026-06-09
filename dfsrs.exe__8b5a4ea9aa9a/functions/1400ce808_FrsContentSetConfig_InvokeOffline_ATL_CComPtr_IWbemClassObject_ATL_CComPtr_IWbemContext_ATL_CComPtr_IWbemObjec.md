# FrsContentSetConfig::InvokeOffline(ATL::CComPtr<IWbemClassObject> &,ATL::CComPtr<IWbemContext> &,ATL::CComPtr<IWbemObjectSink> &)

- ea: `0x1400ce808`
- end: `0x1400cef79`
- name: `?InvokeOffline@FrsContentSetConfig@@IEAAJAEAV?$CComPtr@UIWbemClassObject@@@ATL@@AEAV?$CComPtr@UIWbemContext@@@3@AEAV?$CComPtr@UIWbemObjectSink@@@3@@Z`
- size: `1905`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400ccd50`

## callees

- `0x1400036a0`
- `0x14000be44`
- `0x14000c910`
- `0x14000e34c`
- `0x14000ee94`
- `0x140010680`
- `0x14001c548`
- `0x14005c110`
- `0x1400cb0e4`
- `0x1400cba30`
- `0x1400ce808`
- `0x1400d2304`
- `0x1401b3d14`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400cebd9`
- `KERNEL32!GetCurrentThreadId` at `0x1400cec3d`
- `KERNEL32!GetCurrentThreadId` at `0x1400ceca3`
- `KERNEL32!GetCurrentThreadId` at `0x1400cebd9`
- `KERNEL32!GetCurrentThreadId` at `0x1400cec3d`
- `KERNEL32!GetCurrentThreadId` at `0x1400ceca3`
- `OLEAUT32!__imp_VariantInit` at `0x1400ceda8`
- `OLEAUT32!__imp_VariantInit` at `0x1400ceda8`
- `OLEAUT32!__imp_VariantClear` at `0x1400ce953`
- `OLEAUT32!__imp_VariantClear` at `0x1400ce9f8`
- `OLEAUT32!__imp_VariantClear` at `0x1400cea9d`
- `OLEAUT32!__imp_VariantClear` at `0x1400ceb44`
- `OLEAUT32!__imp_VariantClear` at `0x1400cee2f`
- `OLEAUT32!__imp_VariantClear` at `0x1400ce953`
- `OLEAUT32!__imp_VariantClear` at `0x1400ce9f8`
- `OLEAUT32!__imp_VariantClear` at `0x1400cea9d`
- `OLEAUT32!__imp_VariantClear` at `0x1400ceb44`
- `OLEAUT32!__imp_VariantClear` at `0x1400cee2f`
- `OLEAUT32!__imp_VariantChangeType` at `0x1400cedd2`
- `OLEAUT32!__imp_VariantChangeType` at `0x1400cedd2`

## string_xrefs

- `0x1400ced8b`: `DfsrReplicatedFolderConfig`
- `0x1400ce8ea`: `FrsContentSetConfig::InvokeOffline`
- `0x1400ceeee`: `FrsContentSetConfig::InvokeOffline`
- `0x1400cebf6`: `FrsContentSetConfig::InvokeOffline`
- `0x1400cec5a`: `FrsContentSetConfig::InvokeOffline`
- `0x1400cecc0`: `FrsContentSetConfig::InvokeOffline`
- `0x1400cebb3`: `[CLUSTER] Processing WMI call to DfsrReplicatedFolderConfig::Offline(). resName:%? csId:%? rgId:%? volId:%?`
- `0x1400ced5e`: `[CLUSTER] Failed to offline content set. resName:%? csId:%? Error:%?`
- `0x1400cec02`: `base\fs\remotefs\frs\src\prov\wmiconfig.cpp`
- `0x1400cec66`: `base\fs\remotefs\frs\src\prov\wmiconfig.cpp`
- `0x1400ceccc`: `base\fs\remotefs\frs\src\prov\wmiconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall FrsContentSetConfig::InvokeOffline(__int64 a1, _QWORD *a2, OLECHAR *a3, _QWORD *a4)
{
  char v6; // al
  unsigned int v7; // r12d
  HRESULT OutParamInstance; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  struct FrsStatus *v11; // rax
  struct FrsStatus *v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rcx
  DWORD v15; // eax
  __int64 v16; // rcx
  const wchar_t *v17; // rdx
  const wchar_t *v19; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+58h] [rbp-A8h]
  int v21; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v22; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v23; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-90h] BYREF
  struct FrsStatus *v25; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v26; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v27; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v28; // [rsp+A0h] [rbp-60h] BYREF
  int v29[2]; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v30; // [rsp+B0h] [rbp-50h] BYREF
  int v31; // [rsp+B8h] [rbp-48h]
  int v32; // [rsp+BCh] [rbp-44h]
  const wchar_t *v33; // [rsp+C0h] [rbp-40h]
  BSTR bstrString; // [rsp+C8h] [rbp-38h]
  _QWORD *v35; // [rsp+D0h] [rbp-30h]
  VARIANTARG pvargDest; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v37; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v38; // [rsp+100h] [rbp+0h] BYREF

  v35 = a4;
  bstrString = a3;
  *(_QWORD *)v29 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v23 = &FrsStringImpl<unsigned short,char>::s_Empty;
  v6 = byte_140315A80;
  if ( !byte_140315A80 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v6 = 0;
  }
  v28 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v6 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v6 = byte_140315A80;
  }
  v27 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v6 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v6 = byte_140315A80;
  }
  v26 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v6 )
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
  v7 = 0;
  OutParamInstance = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)*a2 + 32LL))(
                       *a2,
                       L"ResourceName",
                       0,
                       &pvarg);
  if ( OutParamInstance < 0 )
  {
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 2 )
      goto LABEL_83;
    v20 = 2238;
    v17 = L"[CLUSTER] Missing ResourceName argument";
    goto LABEL_82;
  }
  if ( pvarg.vt == 8 )
  {
    FrsStringImpl<unsigned short,char>::Set(&v23, pvarg.llVal);
  }
  else
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      *(_QWORD *)&pvargDest.vt = L"FrsContentSetConfig::InvokeOffline";
      pvargDest.llVal = 0x2000008B5LL;
      pvargDest.pRecInfo = (IRecordInfo *)L"WMIC";
      dbgobj::DbgPrint<unsigned short>(&pvargDest, L"[CLUSTER] Incorrect ResourceName argument type");
    }
    OutParamInstance = -2147217361;
  }
  VariantClear(&pvarg);
  if ( OutParamInstance >= 0 )
  {
    OutParamInstance = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)*a2 + 32LL))(
                         *a2,
                         L"ReplicatedFolderGuid",
                         0,
                         &pvarg);
    if ( OutParamInstance < 0 )
    {
      if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 2 )
        goto LABEL_83;
      v20 = 2275;
      v17 = L"[CLUSTER] Missing ReplicatedFolderGuid argument";
      goto LABEL_82;
    }
    if ( pvarg.vt == 8 )
    {
      FrsStringImpl<unsigned short,char>::Set(&v28, pvarg.llVal);
    }
    else
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        *(_QWORD *)&pvargDest.vt = L"FrsContentSetConfig::InvokeOffline";
        pvargDest.llVal = 0x2000008DALL;
        pvargDest.pRecInfo = (IRecordInfo *)L"WMIC";
        dbgobj::DbgPrint<unsigned short>(&pvargDest, L"[CLUSTER] Incorrect ReplicatedFolderGuid argument type");
      }
      OutParamInstance = -2147217361;
    }
    VariantClear(&pvarg);
    if ( OutParamInstance >= 0 )
    {
      OutParamInstance = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)*a2 + 32LL))(
                           *a2,
                           L"ReplicationGroupGuid",
                           0,
                           &pvarg,
                           0,
                           0);
      if ( OutParamInstance < 0 )
      {
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 2 )
          goto LABEL_83;
        v20 = 2312;
        v17 = L"[CLUSTER] Missing ReplicationGroupGuid argument";
        goto LABEL_82;
      }
      if ( pvarg.vt == 8 )
      {
        FrsStringImpl<unsigned short,char>::Set(&v27, pvarg.llVal);
      }
      else
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          *(_QWORD *)&pvargDest.vt = L"FrsContentSetConfig::InvokeOffline";
          pvargDest.llVal = 0x2000008FFLL;
          pvargDest.pRecInfo = (IRecordInfo *)L"WMIC";
          dbgobj::DbgPrint<unsigned short>(&pvargDest, L"[CLUSTER] Incorrect ReplicationGroupGuid argument type");
        }
        OutParamInstance = -2147217361;
      }
      VariantClear(&pvarg);
      if ( OutParamInstance >= 0 )
      {
        OutParamInstance = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)*a2 + 32LL))(
                             *a2,
                             L"VolumeGuid",
                             0,
                             &pvarg,
                             0,
                             0);
        if ( OutParamInstance >= 0 )
        {
          if ( pvarg.vt == 8 )
          {
            FrsStringImpl<unsigned short,char>::Set(&v26, pvarg.llVal);
          }
          else
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
            {
              *(_QWORD *)&pvargDest.vt = L"FrsContentSetConfig::InvokeOffline";
              pvargDest.llVal = 0x200000923LL;
              pvargDest.pRecInfo = (IRecordInfo *)L"WMIC";
              dbgobj::DbgPrint<unsigned short>(&pvargDest, L"[CLUSTER] Incorrect VolumeGuid argument type");
            }
            OutParamInstance = -2147217361;
          }
          VariantClear(&pvarg);
          if ( OutParamInstance >= 0 )
          {
            v37 = 0;
            *(_OWORD *)&pvargDest.vt = 0;
            v38 = 0;
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v30 = L"FrsContentSetConfig::InvokeOffline";
              v31 = 2364;
              v32 = 4;
              v33 = L"WMIC";
              dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
                (unsigned int)&v30,
                (unsigned int)L"[CLUSTER] Processing WMI call to DfsrReplicatedFolderConfig::Offline(). resName:%? csId:%?"
                               " rgId:%? volId:%?",
                (unsigned int)&v23,
                (unsigned int)&v28,
                (__int64)&v27,
                (__int64)&v26);
            }
            if ( !(unsigned int)Guid::StringToGuid(&v28, &v37) )
            {
              CurrentThreadId = GetCurrentThreadId();
              v11 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                          v10,
                                          87,
                                          0,
                                          1,
                                          "base\\fs\\remotefs\\frs\\src\\prov\\wmiconfig.cpp",
                                          "FrsContentSetConfig::InvokeOffline",
                                          2376,
                                          CurrentThreadId,
                                          0);
              v25 = v11;
              v12 = v11;
              if ( v11 )
                goto LABEL_56;
            }
            if ( !(unsigned int)Guid::StringToGuid(&v27, &pvargDest) )
            {
              v13 = GetCurrentThreadId();
              v11 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                          v14,
                                          87,
                                          0,
                                          1,
                                          "base\\fs\\remotefs\\frs\\src\\prov\\wmiconfig.cpp",
                                          "FrsContentSetConfig::InvokeOffline",
                                          2385,
                                          v13,
                                          0);
              v25 = v11;
              v12 = v11;
              if ( v11 )
                goto LABEL_56;
            }
            if ( !(unsigned int)Guid::StringToGuid(&v26, &v38)
              && (v15 = GetCurrentThreadId(),
                  v11 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                              v16,
                                              87,
                                              0,
                                              1,
                                              "base\\fs\\remotefs\\frs\\src\\prov\\wmiconfig.cpp",
                                              "FrsContentSetConfig::InvokeOffline",
                                              2394,
                                              v15,
                                              0),
                  v25 = v11,
                  (v12 = v11) != 0)
              || (v11 = (struct FrsStatus *)ConfigurationHelper::SetReplicatedFolderOffline(
                                              (unsigned int)&v23,
                                              (unsigned int)&v37,
                                              (unsigned int)&pvargDest,
                                              (unsigned int)&v38,
                                              *(_QWORD *)(*(_QWORD *)(a1 + 24) + 80LL)),
                  v25 = v11,
                  (v12 = v11) != 0) )
            {
LABEL_56:
              v7 = *((_DWORD *)v12 + 1);
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
              {
                v30 = L"FrsContentSetConfig::InvokeOffline";
                v31 = 2416;
                v32 = 2;
                v33 = L"WMIC";
                dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,FrsStatus>(
                  (unsigned int)&v30,
                  (unsigned int)L"[CLUSTER] Failed to offline content set. resName:%? csId:%? Error:%?",
                  (unsigned int)&v23,
                  (unsigned int)&v37,
                  (__int64)v11);
              }
              CLEAR_ERROR(&v25);
            }
            OutParamInstance = WmiInstance::CreateOutParamInstance(
                                 a1,
                                 (int)L"DfsrReplicatedFolderConfig",
                                 (int)L"Offline",
                                 (int)v29,
                                 bstrString);
            if ( OutParamInstance >= 0 )
            {
              VariantInit(&pvargDest);
              ATL::CComVariant::operator=(&pvargDest, v7);
              OutParamInstance = VariantChangeType(&pvargDest, &pvargDest, 0, 3u);
              if ( OutParamInstance >= 0 )
              {
                OutParamInstance = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(**(_QWORD **)v29 + 40LL))(
                                     *(_QWORD *)v29,
                                     L"ReturnValue",
                                     0,
                                     &pvargDest,
                                     0);
                if ( OutParamInstance >= 0 )
                  OutParamInstance = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(*(_QWORD *)*v35 + 24LL))(
                                       *v35,
                                       1,
                                       v29);
              }
              VariantClear(&pvargDest);
            }
          }
          goto LABEL_83;
        }
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 2 )
          goto LABEL_83;
        v20 = 2348;
        v17 = L"[CLUSTER] Missing VolumeGuid argument";
LABEL_82:
        v19 = L"FrsContentSetConfig::InvokeOffline";
        v21 = 2;
        v22 = L"WMIC";
        dbgobj::DbgPrint<unsigned short>(&v19, v17);
      }
    }
  }
LABEL_83:
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v26);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v27);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v28);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v29);
  return (unsigned int)OutParamInstance;
}

```

## disassembly

```asm
0x1400ce808  push    rbp
0x1400ce80a  push    rbx
0x1400ce80b  push    rsi
0x1400ce80c  push    rdi
0x1400ce80d  push    r12
0x1400ce80f  push    r13
0x1400ce811  push    r14
0x1400ce813  push    r15
0x1400ce815  lea     rbp, [rsp-28h]
0x1400ce81a  sub     rsp, 128h
0x1400ce821  mov     rax, cs:__security_cookie
0x1400ce828  xor     rax, rsp
0x1400ce82b  mov     [rbp+60h+var_50], rax
0x1400ce82f  mov     [rbp+60h+var_90], r9
0x1400ce833  mov     [rbp+60h+var_98], r8
0x1400ce837  mov     r15, rdx
0x1400ce83a  mov     r13, rcx
0x1400ce83d  xor     edi, edi
0x1400ce83f  mov     qword ptr [rbp+60h+var_B8], rdi
0x1400ce843  xorps   xmm0, xmm0
0x1400ce846  xor     eax, eax
0x1400ce848  movups  xmmword ptr [rsp+160h+pvarg], xmm0
0x1400ce84d  mov     qword ptr [rbp+60h+pvarg+10h], rax
0x1400ce851  lea     rcx, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400ce858  mov     [rsp+160h+var_F8], rcx
0x1400ce85d  mov     al, cs:byte_140315A80
0x1400ce863  test    al, al
0x1400ce865  jnz     short loc_1400CE874
0x1400ce867  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400ce86e  mov     al, cs:byte_140315A80
0x1400ce874  mov     [rbp+60h+var_C0], rcx
0x1400ce878  test    al, al
0x1400ce87a  jnz     short loc_1400CE889
0x1400ce87c  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400ce883  mov     al, cs:byte_140315A80
0x1400ce889  mov     [rbp+60h+var_C8], rcx
0x1400ce88d  test    al, al
0x1400ce88f  jnz     short loc_1400CE89E
0x1400ce891  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400ce898  mov     al, cs:byte_140315A80
0x1400ce89e  mov     [rbp+60h+var_D0], rcx
0x1400ce8a2  test    al, al
0x1400ce8a4  jnz     short loc_1400CE8AD
0x1400ce8a6  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400ce8ad  mov     r12d, edi
0x1400ce8b0  mov     rcx, [rdx]
0x1400ce8b3  mov     rax, [rcx]
0x1400ce8b6  mov     [rsp+160h+var_138], rdi
0x1400ce8bb  mov     [rsp+160h+bstrString], rdi
0x1400ce8c0  lea     r9, [rsp+160h+pvarg]
0x1400ce8c5  xor     r8d, r8d
0x1400ce8c8  lea     rdx, aResourcename; "ResourceName"
0x1400ce8cf  mov     rax, [rax+20h]
0x1400ce8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ce8d8  mov     ebx, eax
0x1400ce8da  test    eax, eax
0x1400ce8dc  js      loc_1400CEED3
0x1400ce8e2  mov     eax, 8
0x1400ce8e7  lea     edi, [rax-6]
0x1400ce8ea  lea     rsi, aFrscontentsetc_3; "FrsContentSetConfig::InvokeOffline"
0x1400ce8f1  lea     r14, aWmic; "WMIC"
0x1400ce8f8  cmp     ax, word ptr [rsp+160h+pvarg]
0x1400ce8fd  jnz     short loc_1400CE910
0x1400ce8ff  mov     rdx, qword ptr [rsp+160h+pvarg+8]
0x1400ce904  lea     rcx, [rsp+160h+var_F8]
0x1400ce909  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400ce90e  jmp     short loc_1400CE94E
0x1400ce910  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ce917  test    rax, rax
0x1400ce91a  jz      short loc_1400CE949
0x1400ce91c  cmp     [rax+40h], r12d
0x1400ce920  jz      short loc_1400CE949
0x1400ce922  cmp     [rax+38h], edi
0x1400ce925  jl      short loc_1400CE949
0x1400ce927  mov     qword ptr [rbp+60h+pvargDest], rsi
0x1400ce92b  mov     dword ptr [rbp+60h+pvargDest+8], 8B5h
0x1400ce932  mov     dword ptr [rbp+60h+pvargDest+0Ch], edi
0x1400ce935  mov     qword ptr [rbp+60h+pvargDest+10h], r14
0x1400ce939  lea     rdx, aClusterIncorre_2; "[CLUSTER] Incorrect ResourceName argume"...
0x1400ce940  lea     rcx, [rbp+60h+pvargDest]
0x1400ce944  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400ce949  mov     ebx, 8004102Fh
0x1400ce94e  lea     rcx, [rsp+160h+pvarg]; pvarg
0x1400ce953  call    cs:__imp_VariantClear
0x1400ce95a  nop     dword ptr [rax+rax+00h]
0x1400ce95f  test    ebx, ebx
0x1400ce961  js      loc_1400CEF24
0x1400ce967  mov     rcx, [r15]
0x1400ce96a  mov     rax, [rcx]
0x1400ce96d  and     [rsp+160h+var_138], r12
0x1400ce972  and     [rsp+160h+bstrString], r12
0x1400ce977  lea     r9, [rsp+160h+pvarg]
0x1400ce97c  xor     r8d, r8d
0x1400ce97f  lea     rdx, aReplicatedfold_2; "ReplicatedFolderGuid"
0x1400ce986  mov     rax, [rax+20h]
0x1400ce98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ce98f  mov     ebx, eax
0x1400ce991  test    eax, eax
0x1400ce993  js      loc_1400CEEAB
0x1400ce999  mov     eax, 8
0x1400ce99e  cmp     ax, word ptr [rsp+160h+pvarg]
0x1400ce9a3  jnz     short loc_1400CE9B5
0x1400ce9a5  mov     rdx, qword ptr [rsp+160h+pvarg+8]
0x1400ce9aa  lea     rcx, [rbp+60h+var_C0]
0x1400ce9ae  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400ce9b3  jmp     short loc_1400CE9F3
0x1400ce9b5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ce9bc  test    rax, rax
0x1400ce9bf  jz      short loc_1400CE9EE
0x1400ce9c1  cmp     [rax+40h], r12d
0x1400ce9c5  jz      short loc_1400CE9EE
0x1400ce9c7  cmp     [rax+38h], edi
0x1400ce9ca  jl      short loc_1400CE9EE
0x1400ce9cc  mov     qword ptr [rbp+60h+pvargDest], rsi
0x1400ce9d0  mov     dword ptr [rbp+60h+pvargDest+8], 8DAh
0x1400ce9d7  mov     dword ptr [rbp+60h+pvargDest+0Ch], edi
0x1400ce9da  mov     qword ptr [rbp+60h+pvargDest+10h], r14
0x1400ce9de  lea     rdx, aClusterIncorre_0; "[CLUSTER] Incorrect ReplicatedFolderGui"...
0x1400ce9e5  lea     rcx, [rbp+60h+pvargDest]
0x1400ce9e9  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400ce9ee  mov     ebx, 8004102Fh
0x1400ce9f3  lea     rcx, [rsp+160h+pvarg]; pvarg
0x1400ce9f8  call    cs:__imp_VariantClear
0x1400ce9ff  nop     dword ptr [rax+rax+00h]
0x1400cea04  test    ebx, ebx
0x1400cea06  js      loc_1400CEF24
0x1400cea0c  mov     rcx, [r15]
0x1400cea0f  mov     rax, [rcx]
0x1400cea12  and     [rsp+160h+var_138], r12
0x1400cea17  and     [rsp+160h+bstrString], r12
0x1400cea1c  lea     r9, [rsp+160h+pvarg]
0x1400cea21  xor     r8d, r8d
0x1400cea24  lea     rdx, aReplicationgro_1; "ReplicationGroupGuid"
0x1400cea2b  mov     rax, [rax+20h]
0x1400cea2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cea34  mov     ebx, eax
0x1400cea36  test    eax, eax
0x1400cea38  js      loc_1400CEE77
0x1400cea3e  mov     eax, 8
0x1400cea43  cmp     ax, word ptr [rsp+160h+pvarg]
0x1400cea48  jnz     short loc_1400CEA5A
0x1400cea4a  mov     rdx, qword ptr [rsp+160h+pvarg+8]
0x1400cea4f  lea     rcx, [rbp+60h+var_C8]
0x1400cea53  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400cea58  jmp     short loc_1400CEA98
0x1400cea5a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400cea61  test    rax, rax
0x1400cea64  jz      short loc_1400CEA93
0x1400cea66  cmp     [rax+40h], r12d
0x1400cea6a  jz      short loc_1400CEA93
0x1400cea6c  cmp     [rax+38h], edi
0x1400cea6f  jl      short loc_1400CEA93
0x1400cea71  mov     qword ptr [rbp+60h+pvargDest], rsi
0x1400cea75  mov     dword ptr [rbp+60h+pvargDest+8], 8FFh
0x1400cea7c  mov     dword ptr [rbp+60h+pvargDest+0Ch], edi
0x1400cea7f  mov     qword ptr [rbp+60h+pvargDest+10h], r14
0x1400cea83  lea     rdx, aClusterIncorre_1; "[CLUSTER] Incorrect ReplicationGroupGui"...
0x1400cea8a  lea     rcx, [rbp+60h+pvargDest]
0x1400cea8e  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400cea93  mov     ebx, 8004102Fh
0x1400cea98  lea     rcx, [rsp+160h+pvarg]; pvarg
0x1400cea9d  call    cs:__imp_VariantClear
0x1400ceaa4  nop     dword ptr [rax+rax+00h]
0x1400ceaa9  test    ebx, ebx
0x1400ceaab  js      loc_1400CEF24
0x1400ceab1  mov     rcx, [r15]
0x1400ceab4  mov     rax, [rcx]
0x1400ceab7  xor     r15d, r15d
0x1400ceaba  mov     [rsp+160h+var_138], r15
0x1400ceabf  mov     [rsp+160h+bstrString], r15
0x1400ceac4  lea     r9, [rsp+160h+pvarg]
0x1400ceac9  xor     r8d, r8d
0x1400ceacc  lea     rdx, aVolumeguid; "VolumeGuid"
0x1400cead3  mov     rax, [rax+20h]
0x1400cead7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ceadc  mov     ebx, eax
0x1400ceade  test    eax, eax
0x1400ceae0  js      loc_1400CEE40
0x1400ceae6  lea     eax, [r15+8]
0x1400ceaea  cmp     ax, word ptr [rsp+160h+pvarg]
0x1400ceaef  jnz     short loc_1400CEB01
0x1400ceaf1  mov     rdx, qword ptr [rsp+160h+pvarg+8]
0x1400ceaf6  lea     rcx, [rbp+60h+var_D0]
0x1400ceafa  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400ceaff  jmp     short loc_1400CEB3F
0x1400ceb01  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ceb08  test    rax, rax
0x1400ceb0b  jz      short loc_1400CEB3A
0x1400ceb0d  cmp     [rax+40h], r15d
0x1400ceb11  jz      short loc_1400CEB3A
0x1400ceb13  cmp     [rax+38h], edi
0x1400ceb16  jl      short loc_1400CEB3A
0x1400ceb18  mov     qword ptr [rbp+60h+pvargDest], rsi
0x1400ceb1c  mov     dword ptr [rbp+60h+pvargDest+8], 923h
0x1400ceb23  mov     dword ptr [rbp+60h+pvargDest+0Ch], edi
0x1400ceb26  mov     qword ptr [rbp+60h+pvargDest+10h], r14
0x1400ceb2a  lea     rdx, aClusterIncorre; "[CLUSTER] Incorrect VolumeGuid argument"...
0x1400ceb31  lea     rcx, [rbp+60h+pvargDest]
0x1400ceb35  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400ceb3a  mov     ebx, 8004102Fh
0x1400ceb3f  lea     rcx, [rsp+160h+pvarg]; pvarg
0x1400ceb44  call    cs:__imp_VariantClear
0x1400ceb4b  nop     dword ptr [rax+rax+00h]
0x1400ceb50  test    ebx, ebx
0x1400ceb52  js      loc_1400CEF24
0x1400ceb58  xorps   xmm0, xmm0
0x1400ceb5b  movups  [rbp+60h+var_70], xmm0
0x1400ceb5f  xorps   xmm1, xmm1
0x1400ceb62  movups  xmmword ptr [rbp+60h+pvargDest], xmm1
0x1400ceb66  movups  [rbp+60h+var_60], xmm0
0x1400ceb6a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ceb71  test    rax, rax
0x1400ceb74  jz      short loc_1400CEBC3
0x1400ceb76  cmp     [rax+40h], r15d
0x1400ceb7a  jz      short loc_1400CEBC3
0x1400ceb7c  cmp     dword ptr [rax+38h], 4
0x1400ceb80  jl      short loc_1400CEBC3
0x1400ceb82  mov     [rbp+60h+var_B0], rsi
0x1400ceb86  mov     [rbp+60h+var_A8], 93Ch
0x1400ceb8d  mov     [rbp+60h+var_A4], 4
0x1400ceb94  mov     [rbp+60h+var_A0], r14
0x1400ceb98  lea     rax, [rbp+60h+var_D0]
0x1400ceb9c  mov     [rsp+160h+var_138], rax
0x1400ceba1  lea     rax, [rbp+60h+var_C8]
0x1400ceba5  mov     [rsp+160h+bstrString], rax
0x1400cebaa  lea     r9, [rbp+60h+var_C0]
0x1400cebae  lea     r8, [rsp+160h+var_F8]
0x1400cebb3  lea     rdx, aClusterProcess_4; "[CLUSTER] Processing WMI call to DfsrRe"...
0x1400cebba  lea     rcx, [rbp+60h+var_B0]
0x1400cebbe  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@V1@V1@V1@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@111@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)
0x1400cebc3  lea     rdx, [rbp+60h+var_70]
0x1400cebc7  lea     rcx, [rbp+60h+var_C0]
0x1400cebcb  call    ?StringToGuid@Guid@@SAHAEBV?$FrsStringImpl@GD@@AEAU_GUID@@@Z; Guid::StringToGuid(FrsStringImpl<ushort,char> const &,_GUID &)
0x1400cebd0  mov     ebx, 57h ; 'W'
0x1400cebd5  test    eax, eax
0x1400cebd7  jnz     short loc_1400CEC2C
0x1400cebd9  call    cs:__imp_GetCurrentThreadId
0x1400cebe0  nop     dword ptr [rax+rax+00h]
0x1400cebe5  mov     [rsp+160h+var_120], r15
0x1400cebea  mov     [rsp+160h+var_128], eax
0x1400cebee  mov     [rsp+160h+var_130], 948h
0x1400cebf6  lea     rax, aFrscontentsetc; "FrsContentSetConfig::InvokeOffline"
0x1400cebfd  mov     [rsp+160h+var_138], rax
0x1400cec02  lea     rax, aBaseFsRemotefs_102; "base\\fs\\remotefs\\frs\\src\\prov\\wmi"...
0x1400cec09  mov     [rsp+160h+bstrString], rax
0x1400cec0e  lea     r9d, [rbx-56h]
0x1400cec12  xor     r8d, r8d
0x1400cec15  mov     edx, ebx
0x1400cec17  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400cec1c  mov     [rbp+60h+var_D8], rax
0x1400cec20  mov     rcx, rax
0x1400cec23  test    rax, rax
0x1400cec26  jnz     loc_1400CED23
0x1400cec2c  lea     rdx, [rbp+60h+pvargDest]
0x1400cec30  lea     rcx, [rbp+60h+var_C8]
0x1400cec34  call    ?StringToGuid@Guid@@SAHAEBV?$FrsStringImpl@GD@@AEAU_GUID@@@Z; Guid::StringToGuid(FrsStringImpl<ushort,char> const &,_GUID &)
0x1400cec39  test    eax, eax
0x1400cec3b  jnz     short loc_1400CEC92
0x1400cec3d  call    cs:__imp_GetCurrentThreadId
0x1400cec44  nop     dword ptr [rax+rax+00h]
0x1400cec49  mov     [rsp+160h+var_120], r15
0x1400cec4e  mov     [rsp+160h+var_128], eax
0x1400cec52  mov     [rsp+160h+var_130], 951h
0x1400cec5a  lea     rax, aFrscontentsetc; "FrsContentSetConfig::InvokeOffline"
0x1400cec61  mov     [rsp+160h+var_138], rax
0x1400cec66  lea     rax, aBaseFsRemotefs_102; "base\\fs\\remotefs\\frs\\src\\prov\\wmi"...
0x1400cec6d  mov     [rsp+160h+bstrString], rax
0x1400cec72  mov     r9d, 1
0x1400cec78  xor     r8d, r8d
0x1400cec7b  mov     edx, ebx
0x1400cec7d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400cec82  mov     [rbp+60h+var_D8], rax
0x1400cec86  mov     rcx, rax
0x1400cec89  test    rax, rax
0x1400cec8c  jnz     loc_1400CED23
0x1400cec92  lea     rdx, [rbp+60h+var_60]
0x1400cec96  lea     rcx, [rbp+60h+var_D0]
0x1400cec9a  call    ?StringToGuid@Guid@@SAHAEBV?$FrsStringImpl@GD@@AEAU_GUID@@@Z; Guid::StringToGuid(FrsStringImpl<ushort,char> const &,_GUID &)
0x1400cec9f  test    eax, eax
0x1400ceca1  jnz     short loc_1400CECF4
0x1400ceca3  call    cs:__imp_GetCurrentThreadId
0x1400cecaa  nop     dword ptr [rax+rax+00h]
0x1400cecaf  mov     [rsp+160h+var_120], r15
0x1400cecb4  mov     [rsp+160h+var_128], eax
0x1400cecb8  mov     [rsp+160h+var_130], 95Ah
0x1400cecc0  lea     rax, aFrscontentsetc; "FrsContentSetConfig::InvokeOffline"
0x1400cecc7  mov     [rsp+160h+var_138], rax
0x1400ceccc  lea     rax, aBaseFsRemotefs_102; "base\\fs\\remotefs\\frs\\src\\prov\\wmi"...
0x1400cecd3  mov     [rsp+160h+bstrString], rax
0x1400cecd8  mov     r9d, 1
0x1400cecde  xor     r8d, r8d
0x1400cece1  mov     edx, ebx
0x1400cece3  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400cece8  mov     [rbp+60h+var_D8], rax
0x1400cecec  mov     rcx, rax
0x1400cecef  test    rax, rax
0x1400cecf2  jnz     short loc_1400CED23
0x1400cecf4  mov     rax, [r13+18h]
0x1400cecf8  mov     rcx, [rax+50h]
0x1400cecfc  mov     [rsp+160h+bstrString], rcx
  ... truncated ...
```

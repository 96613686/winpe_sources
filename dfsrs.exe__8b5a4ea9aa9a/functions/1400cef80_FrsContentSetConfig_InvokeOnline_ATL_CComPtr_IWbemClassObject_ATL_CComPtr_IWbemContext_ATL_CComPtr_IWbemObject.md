# FrsContentSetConfig::InvokeOnline(ATL::CComPtr<IWbemClassObject> &,ATL::CComPtr<IWbemContext> &,ATL::CComPtr<IWbemObjectSink> &)

- ea: `0x1400cef80`
- end: `0x1400cf6f1`
- name: `?InvokeOnline@FrsContentSetConfig@@IEAAJAEAV?$CComPtr@UIWbemClassObject@@@ATL@@AEAV?$CComPtr@UIWbemContext@@@3@AEAV?$CComPtr@UIWbemObjectSink@@@3@@Z`
- size: `1905`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

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
- `0x1400cb3b0`
- `0x1400cba30`
- `0x1400cef80`
- `0x1400d2304`
- `0x1401b3d14`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400cf351`
- `KERNEL32!GetCurrentThreadId` at `0x1400cf3b5`
- `KERNEL32!GetCurrentThreadId` at `0x1400cf41b`
- `KERNEL32!GetCurrentThreadId` at `0x1400cf351`
- `KERNEL32!GetCurrentThreadId` at `0x1400cf3b5`
- `KERNEL32!GetCurrentThreadId` at `0x1400cf41b`
- `OLEAUT32!__imp_VariantInit` at `0x1400cf520`
- `OLEAUT32!__imp_VariantInit` at `0x1400cf520`
- `OLEAUT32!__imp_VariantClear` at `0x1400cf0cb`
- `OLEAUT32!__imp_VariantClear` at `0x1400cf170`
- `OLEAUT32!__imp_VariantClear` at `0x1400cf215`
- `OLEAUT32!__imp_VariantClear` at `0x1400cf2bc`
- `OLEAUT32!__imp_VariantClear` at `0x1400cf5a7`
- `OLEAUT32!__imp_VariantClear` at `0x1400cf0cb`
- `OLEAUT32!__imp_VariantClear` at `0x1400cf170`
- `OLEAUT32!__imp_VariantClear` at `0x1400cf215`
- `OLEAUT32!__imp_VariantClear` at `0x1400cf2bc`
- `OLEAUT32!__imp_VariantClear` at `0x1400cf5a7`
- `OLEAUT32!__imp_VariantChangeType` at `0x1400cf54a`
- `OLEAUT32!__imp_VariantChangeType` at `0x1400cf54a`

## string_xrefs

- `0x1400cf503`: `DfsrReplicatedFolderConfig`
- `0x1400cf37a`: `base\fs\remotefs\frs\src\prov\wmiconfig.cpp`
- `0x1400cf3de`: `base\fs\remotefs\frs\src\prov\wmiconfig.cpp`
- `0x1400cf444`: `base\fs\remotefs\frs\src\prov\wmiconfig.cpp`
- `0x1400cf32b`: `[CLUSTER] Processing WMI call to DfsrReplicatedFolderConfig::Online(). resName:%? csId:%? rgId:%? volId:%?`
- `0x1400cf062`: `FrsContentSetConfig::InvokeOnline`
- `0x1400cf666`: `FrsContentSetConfig::InvokeOnline`
- `0x1400cf4d6`: `[CLUSTER] Failed to online content set. resName:%? csId:%? Error:%?`
- `0x1400cf36e`: `FrsContentSetConfig::InvokeOnline`
- `0x1400cf3d2`: `FrsContentSetConfig::InvokeOnline`
- `0x1400cf438`: `FrsContentSetConfig::InvokeOnline`

## pseudocode

```c
__int64 __fastcall FrsContentSetConfig::InvokeOnline(__int64 a1, _QWORD *a2, OLECHAR *a3, _QWORD *a4)
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
    v20 = 2540;
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
      *(_QWORD *)&pvargDest.vt = L"FrsContentSetConfig::InvokeOnline";
      pvargDest.llVal = 0x2000009E3LL;
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
      v20 = 2577;
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
        *(_QWORD *)&pvargDest.vt = L"FrsContentSetConfig::InvokeOnline";
        pvargDest.llVal = 0x200000A08LL;
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
        v20 = 2614;
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
          *(_QWORD *)&pvargDest.vt = L"FrsContentSetConfig::InvokeOnline";
          pvargDest.llVal = 0x200000A2DLL;
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
              *(_QWORD *)&pvargDest.vt = L"FrsContentSetConfig::InvokeOnline";
              pvargDest.llVal = 0x200000A51LL;
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
              v30 = L"FrsContentSetConfig::InvokeOnline";
              v31 = 2666;
              v32 = 4;
              v33 = L"WMIC";
              dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
                (unsigned int)&v30,
                (unsigned int)L"[CLUSTER] Processing WMI call to DfsrReplicatedFolderConfig::Online(). resName:%? csId:%? "
                               "rgId:%? volId:%?",
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
                                          "FrsContentSetConfig::InvokeOnline",
                                          2678,
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
                                          "FrsContentSetConfig::InvokeOnline",
                                          2687,
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
                                              "FrsContentSetConfig::InvokeOnline",
                                              2696,
                                              v15,
                                              0),
                  v25 = v11,
                  (v12 = v11) != 0)
              || (v11 = (struct FrsStatus *)ConfigurationHelper::SetReplicatedFolderOnline(
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
                v30 = L"FrsContentSetConfig::InvokeOnline";
                v31 = 2717;
                v32 = 2;
                v33 = L"WMIC";
                dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,FrsStatus>(
                  (unsigned int)&v30,
                  (unsigned int)L"[CLUSTER] Failed to online content set. resName:%? csId:%? Error:%?",
                  (unsigned int)&v23,
                  (unsigned int)&v37,
                  (__int64)v11);
              }
              CLEAR_ERROR(&v25);
            }
            OutParamInstance = WmiInstance::CreateOutParamInstance(
                                 a1,
                                 (int)L"DfsrReplicatedFolderConfig",
                                 (int)L"Online",
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
        v20 = 2650;
        v17 = L"[CLUSTER] Missing VolumeGuid argument";
LABEL_82:
        v19 = L"FrsContentSetConfig::InvokeOnline";
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
0x1400cef80  push    rbp
0x1400cef82  push    rbx
0x1400cef83  push    rsi
0x1400cef84  push    rdi
0x1400cef85  push    r12
0x1400cef87  push    r13
0x1400cef89  push    r14
0x1400cef8b  push    r15
0x1400cef8d  lea     rbp, [rsp-28h]
0x1400cef92  sub     rsp, 128h
0x1400cef99  mov     rax, cs:__security_cookie
0x1400cefa0  xor     rax, rsp
0x1400cefa3  mov     [rbp+60h+var_50], rax
0x1400cefa7  mov     [rbp+60h+var_90], r9
0x1400cefab  mov     [rbp+60h+var_98], r8
0x1400cefaf  mov     r15, rdx
0x1400cefb2  mov     r13, rcx
0x1400cefb5  xor     edi, edi
0x1400cefb7  mov     qword ptr [rbp+60h+var_B8], rdi
0x1400cefbb  xorps   xmm0, xmm0
0x1400cefbe  xor     eax, eax
0x1400cefc0  movups  xmmword ptr [rsp+160h+pvarg], xmm0
0x1400cefc5  mov     qword ptr [rbp+60h+pvarg+10h], rax
0x1400cefc9  lea     rcx, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400cefd0  mov     [rsp+160h+var_F8], rcx
0x1400cefd5  mov     al, cs:byte_140315A80
0x1400cefdb  test    al, al
0x1400cefdd  jnz     short loc_1400CEFEC
0x1400cefdf  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400cefe6  mov     al, cs:byte_140315A80
0x1400cefec  mov     [rbp+60h+var_C0], rcx
0x1400ceff0  test    al, al
0x1400ceff2  jnz     short loc_1400CF001
0x1400ceff4  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400ceffb  mov     al, cs:byte_140315A80
0x1400cf001  mov     [rbp+60h+var_C8], rcx
0x1400cf005  test    al, al
0x1400cf007  jnz     short loc_1400CF016
0x1400cf009  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400cf010  mov     al, cs:byte_140315A80
0x1400cf016  mov     [rbp+60h+var_D0], rcx
0x1400cf01a  test    al, al
0x1400cf01c  jnz     short loc_1400CF025
0x1400cf01e  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400cf025  mov     r12d, edi
0x1400cf028  mov     rcx, [rdx]
0x1400cf02b  mov     rax, [rcx]
0x1400cf02e  mov     [rsp+160h+var_138], rdi
0x1400cf033  mov     [rsp+160h+bstrString], rdi
0x1400cf038  lea     r9, [rsp+160h+pvarg]
0x1400cf03d  xor     r8d, r8d
0x1400cf040  lea     rdx, aResourcename; "ResourceName"
0x1400cf047  mov     rax, [rax+20h]
0x1400cf04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cf050  mov     ebx, eax
0x1400cf052  test    eax, eax
0x1400cf054  js      loc_1400CF64B
0x1400cf05a  mov     eax, 8
0x1400cf05f  lea     edi, [rax-6]
0x1400cf062  lea     rsi, aFrscontentsetc_10; "FrsContentSetConfig::InvokeOnline"
0x1400cf069  lea     r14, aWmic; "WMIC"
0x1400cf070  cmp     ax, word ptr [rsp+160h+pvarg]
0x1400cf075  jnz     short loc_1400CF088
0x1400cf077  mov     rdx, qword ptr [rsp+160h+pvarg+8]
0x1400cf07c  lea     rcx, [rsp+160h+var_F8]
0x1400cf081  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400cf086  jmp     short loc_1400CF0C6
0x1400cf088  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400cf08f  test    rax, rax
0x1400cf092  jz      short loc_1400CF0C1
0x1400cf094  cmp     [rax+40h], r12d
0x1400cf098  jz      short loc_1400CF0C1
0x1400cf09a  cmp     [rax+38h], edi
0x1400cf09d  jl      short loc_1400CF0C1
0x1400cf09f  mov     qword ptr [rbp+60h+pvargDest], rsi
0x1400cf0a3  mov     dword ptr [rbp+60h+pvargDest+8], 9E3h
0x1400cf0aa  mov     dword ptr [rbp+60h+pvargDest+0Ch], edi
0x1400cf0ad  mov     qword ptr [rbp+60h+pvargDest+10h], r14
0x1400cf0b1  lea     rdx, aClusterIncorre_2; "[CLUSTER] Incorrect ResourceName argume"...
0x1400cf0b8  lea     rcx, [rbp+60h+pvargDest]
0x1400cf0bc  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400cf0c1  mov     ebx, 8004102Fh
0x1400cf0c6  lea     rcx, [rsp+160h+pvarg]; pvarg
0x1400cf0cb  call    cs:__imp_VariantClear
0x1400cf0d2  nop     dword ptr [rax+rax+00h]
0x1400cf0d7  test    ebx, ebx
0x1400cf0d9  js      loc_1400CF69C
0x1400cf0df  mov     rcx, [r15]
0x1400cf0e2  mov     rax, [rcx]
0x1400cf0e5  and     [rsp+160h+var_138], r12
0x1400cf0ea  and     [rsp+160h+bstrString], r12
0x1400cf0ef  lea     r9, [rsp+160h+pvarg]
0x1400cf0f4  xor     r8d, r8d
0x1400cf0f7  lea     rdx, aReplicatedfold_2; "ReplicatedFolderGuid"
0x1400cf0fe  mov     rax, [rax+20h]
0x1400cf102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cf107  mov     ebx, eax
0x1400cf109  test    eax, eax
0x1400cf10b  js      loc_1400CF623
0x1400cf111  mov     eax, 8
0x1400cf116  cmp     ax, word ptr [rsp+160h+pvarg]
0x1400cf11b  jnz     short loc_1400CF12D
0x1400cf11d  mov     rdx, qword ptr [rsp+160h+pvarg+8]
0x1400cf122  lea     rcx, [rbp+60h+var_C0]
0x1400cf126  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400cf12b  jmp     short loc_1400CF16B
0x1400cf12d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400cf134  test    rax, rax
0x1400cf137  jz      short loc_1400CF166
0x1400cf139  cmp     [rax+40h], r12d
0x1400cf13d  jz      short loc_1400CF166
0x1400cf13f  cmp     [rax+38h], edi
0x1400cf142  jl      short loc_1400CF166
0x1400cf144  mov     qword ptr [rbp+60h+pvargDest], rsi
0x1400cf148  mov     dword ptr [rbp+60h+pvargDest+8], 0A08h
0x1400cf14f  mov     dword ptr [rbp+60h+pvargDest+0Ch], edi
0x1400cf152  mov     qword ptr [rbp+60h+pvargDest+10h], r14
0x1400cf156  lea     rdx, aClusterIncorre_0; "[CLUSTER] Incorrect ReplicatedFolderGui"...
0x1400cf15d  lea     rcx, [rbp+60h+pvargDest]
0x1400cf161  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400cf166  mov     ebx, 8004102Fh
0x1400cf16b  lea     rcx, [rsp+160h+pvarg]; pvarg
0x1400cf170  call    cs:__imp_VariantClear
0x1400cf177  nop     dword ptr [rax+rax+00h]
0x1400cf17c  test    ebx, ebx
0x1400cf17e  js      loc_1400CF69C
0x1400cf184  mov     rcx, [r15]
0x1400cf187  mov     rax, [rcx]
0x1400cf18a  and     [rsp+160h+var_138], r12
0x1400cf18f  and     [rsp+160h+bstrString], r12
0x1400cf194  lea     r9, [rsp+160h+pvarg]
0x1400cf199  xor     r8d, r8d
0x1400cf19c  lea     rdx, aReplicationgro_1; "ReplicationGroupGuid"
0x1400cf1a3  mov     rax, [rax+20h]
0x1400cf1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cf1ac  mov     ebx, eax
0x1400cf1ae  test    eax, eax
0x1400cf1b0  js      loc_1400CF5EF
0x1400cf1b6  mov     eax, 8
0x1400cf1bb  cmp     ax, word ptr [rsp+160h+pvarg]
0x1400cf1c0  jnz     short loc_1400CF1D2
0x1400cf1c2  mov     rdx, qword ptr [rsp+160h+pvarg+8]
0x1400cf1c7  lea     rcx, [rbp+60h+var_C8]
0x1400cf1cb  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400cf1d0  jmp     short loc_1400CF210
0x1400cf1d2  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400cf1d9  test    rax, rax
0x1400cf1dc  jz      short loc_1400CF20B
0x1400cf1de  cmp     [rax+40h], r12d
0x1400cf1e2  jz      short loc_1400CF20B
0x1400cf1e4  cmp     [rax+38h], edi
0x1400cf1e7  jl      short loc_1400CF20B
0x1400cf1e9  mov     qword ptr [rbp+60h+pvargDest], rsi
0x1400cf1ed  mov     dword ptr [rbp+60h+pvargDest+8], 0A2Dh
0x1400cf1f4  mov     dword ptr [rbp+60h+pvargDest+0Ch], edi
0x1400cf1f7  mov     qword ptr [rbp+60h+pvargDest+10h], r14
0x1400cf1fb  lea     rdx, aClusterIncorre_1; "[CLUSTER] Incorrect ReplicationGroupGui"...
0x1400cf202  lea     rcx, [rbp+60h+pvargDest]
0x1400cf206  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400cf20b  mov     ebx, 8004102Fh
0x1400cf210  lea     rcx, [rsp+160h+pvarg]; pvarg
0x1400cf215  call    cs:__imp_VariantClear
0x1400cf21c  nop     dword ptr [rax+rax+00h]
0x1400cf221  test    ebx, ebx
0x1400cf223  js      loc_1400CF69C
0x1400cf229  mov     rcx, [r15]
0x1400cf22c  mov     rax, [rcx]
0x1400cf22f  xor     r15d, r15d
0x1400cf232  mov     [rsp+160h+var_138], r15
0x1400cf237  mov     [rsp+160h+bstrString], r15
0x1400cf23c  lea     r9, [rsp+160h+pvarg]
0x1400cf241  xor     r8d, r8d
0x1400cf244  lea     rdx, aVolumeguid; "VolumeGuid"
0x1400cf24b  mov     rax, [rax+20h]
0x1400cf24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cf254  mov     ebx, eax
0x1400cf256  test    eax, eax
0x1400cf258  js      loc_1400CF5B8
0x1400cf25e  lea     eax, [r15+8]
0x1400cf262  cmp     ax, word ptr [rsp+160h+pvarg]
0x1400cf267  jnz     short loc_1400CF279
0x1400cf269  mov     rdx, qword ptr [rsp+160h+pvarg+8]
0x1400cf26e  lea     rcx, [rbp+60h+var_D0]
0x1400cf272  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400cf277  jmp     short loc_1400CF2B7
0x1400cf279  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400cf280  test    rax, rax
0x1400cf283  jz      short loc_1400CF2B2
0x1400cf285  cmp     [rax+40h], r15d
0x1400cf289  jz      short loc_1400CF2B2
0x1400cf28b  cmp     [rax+38h], edi
0x1400cf28e  jl      short loc_1400CF2B2
0x1400cf290  mov     qword ptr [rbp+60h+pvargDest], rsi
0x1400cf294  mov     dword ptr [rbp+60h+pvargDest+8], 0A51h
0x1400cf29b  mov     dword ptr [rbp+60h+pvargDest+0Ch], edi
0x1400cf29e  mov     qword ptr [rbp+60h+pvargDest+10h], r14
0x1400cf2a2  lea     rdx, aClusterIncorre; "[CLUSTER] Incorrect VolumeGuid argument"...
0x1400cf2a9  lea     rcx, [rbp+60h+pvargDest]
0x1400cf2ad  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400cf2b2  mov     ebx, 8004102Fh
0x1400cf2b7  lea     rcx, [rsp+160h+pvarg]; pvarg
0x1400cf2bc  call    cs:__imp_VariantClear
0x1400cf2c3  nop     dword ptr [rax+rax+00h]
0x1400cf2c8  test    ebx, ebx
0x1400cf2ca  js      loc_1400CF69C
0x1400cf2d0  xorps   xmm0, xmm0
0x1400cf2d3  movups  [rbp+60h+var_70], xmm0
0x1400cf2d7  xorps   xmm1, xmm1
0x1400cf2da  movups  xmmword ptr [rbp+60h+pvargDest], xmm1
0x1400cf2de  movups  [rbp+60h+var_60], xmm0
0x1400cf2e2  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400cf2e9  test    rax, rax
0x1400cf2ec  jz      short loc_1400CF33B
0x1400cf2ee  cmp     [rax+40h], r15d
0x1400cf2f2  jz      short loc_1400CF33B
0x1400cf2f4  cmp     dword ptr [rax+38h], 4
0x1400cf2f8  jl      short loc_1400CF33B
0x1400cf2fa  mov     [rbp+60h+var_B0], rsi
0x1400cf2fe  mov     [rbp+60h+var_A8], 0A6Ah
0x1400cf305  mov     [rbp+60h+var_A4], 4
0x1400cf30c  mov     [rbp+60h+var_A0], r14
0x1400cf310  lea     rax, [rbp+60h+var_D0]
0x1400cf314  mov     [rsp+160h+var_138], rax
0x1400cf319  lea     rax, [rbp+60h+var_C8]
0x1400cf31d  mov     [rsp+160h+bstrString], rax
0x1400cf322  lea     r9, [rbp+60h+var_C0]
0x1400cf326  lea     r8, [rsp+160h+var_F8]
0x1400cf32b  lea     rdx, aClusterProcess_0; "[CLUSTER] Processing WMI call to DfsrRe"...
0x1400cf332  lea     rcx, [rbp+60h+var_B0]
0x1400cf336  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@V1@V1@V1@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@111@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)
0x1400cf33b  lea     rdx, [rbp+60h+var_70]
0x1400cf33f  lea     rcx, [rbp+60h+var_C0]
0x1400cf343  call    ?StringToGuid@Guid@@SAHAEBV?$FrsStringImpl@GD@@AEAU_GUID@@@Z; Guid::StringToGuid(FrsStringImpl<ushort,char> const &,_GUID &)
0x1400cf348  mov     ebx, 57h ; 'W'
0x1400cf34d  test    eax, eax
0x1400cf34f  jnz     short loc_1400CF3A4
0x1400cf351  call    cs:__imp_GetCurrentThreadId
0x1400cf358  nop     dword ptr [rax+rax+00h]
0x1400cf35d  mov     [rsp+160h+var_120], r15
0x1400cf362  mov     [rsp+160h+var_128], eax
0x1400cf366  mov     [rsp+160h+var_130], 0A76h
0x1400cf36e  lea     rax, aFrscontentsetc_1; "FrsContentSetConfig::InvokeOnline"
0x1400cf375  mov     [rsp+160h+var_138], rax
0x1400cf37a  lea     rax, aBaseFsRemotefs_102; "base\\fs\\remotefs\\frs\\src\\prov\\wmi"...
0x1400cf381  mov     [rsp+160h+bstrString], rax
0x1400cf386  lea     r9d, [rbx-56h]
0x1400cf38a  xor     r8d, r8d
0x1400cf38d  mov     edx, ebx
0x1400cf38f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400cf394  mov     [rbp+60h+var_D8], rax
0x1400cf398  mov     rcx, rax
0x1400cf39b  test    rax, rax
0x1400cf39e  jnz     loc_1400CF49B
0x1400cf3a4  lea     rdx, [rbp+60h+pvargDest]
0x1400cf3a8  lea     rcx, [rbp+60h+var_C8]
0x1400cf3ac  call    ?StringToGuid@Guid@@SAHAEBV?$FrsStringImpl@GD@@AEAU_GUID@@@Z; Guid::StringToGuid(FrsStringImpl<ushort,char> const &,_GUID &)
0x1400cf3b1  test    eax, eax
0x1400cf3b3  jnz     short loc_1400CF40A
0x1400cf3b5  call    cs:__imp_GetCurrentThreadId
0x1400cf3bc  nop     dword ptr [rax+rax+00h]
0x1400cf3c1  mov     [rsp+160h+var_120], r15
0x1400cf3c6  mov     [rsp+160h+var_128], eax
0x1400cf3ca  mov     [rsp+160h+var_130], 0A7Fh
0x1400cf3d2  lea     rax, aFrscontentsetc_1; "FrsContentSetConfig::InvokeOnline"
0x1400cf3d9  mov     [rsp+160h+var_138], rax
0x1400cf3de  lea     rax, aBaseFsRemotefs_102; "base\\fs\\remotefs\\frs\\src\\prov\\wmi"...
0x1400cf3e5  mov     [rsp+160h+bstrString], rax
0x1400cf3ea  mov     r9d, 1
0x1400cf3f0  xor     r8d, r8d
0x1400cf3f3  mov     edx, ebx
0x1400cf3f5  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400cf3fa  mov     [rbp+60h+var_D8], rax
0x1400cf3fe  mov     rcx, rax
0x1400cf401  test    rax, rax
0x1400cf404  jnz     loc_1400CF49B
0x1400cf40a  lea     rdx, [rbp+60h+var_60]
0x1400cf40e  lea     rcx, [rbp+60h+var_D0]
0x1400cf412  call    ?StringToGuid@Guid@@SAHAEBV?$FrsStringImpl@GD@@AEAU_GUID@@@Z; Guid::StringToGuid(FrsStringImpl<ushort,char> const &,_GUID &)
0x1400cf417  test    eax, eax
0x1400cf419  jnz     short loc_1400CF46C
0x1400cf41b  call    cs:__imp_GetCurrentThreadId
0x1400cf422  nop     dword ptr [rax+rax+00h]
0x1400cf427  mov     [rsp+160h+var_120], r15
0x1400cf42c  mov     [rsp+160h+var_128], eax
0x1400cf430  mov     [rsp+160h+var_130], 0A88h
0x1400cf438  lea     rax, aFrscontentsetc_1; "FrsContentSetConfig::InvokeOnline"
0x1400cf43f  mov     [rsp+160h+var_138], rax
0x1400cf444  lea     rax, aBaseFsRemotefs_102; "base\\fs\\remotefs\\frs\\src\\prov\\wmi"...
0x1400cf44b  mov     [rsp+160h+bstrString], rax
0x1400cf450  mov     r9d, 1
0x1400cf456  xor     r8d, r8d
0x1400cf459  mov     edx, ebx
0x1400cf45b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400cf460  mov     [rbp+60h+var_D8], rax
0x1400cf464  mov     rcx, rax
0x1400cf467  test    rax, rax
0x1400cf46a  jnz     short loc_1400CF49B
0x1400cf46c  mov     rax, [r13+18h]
0x1400cf470  mov     rcx, [rax+50h]
0x1400cf474  mov     [rsp+160h+bstrString], rcx
  ... truncated ...
```

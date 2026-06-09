# CPinProgressDialog::_DoThreadWork(void)

- ea: `0x180042148`
- end: `0x18004278d`
- name: `?_DoThreadWork@CPinProgressDialog@@AEAAJXZ`
- size: `1605`
- prototype: `__int64 __fastcall(CPinProgressDialog *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180043420`

## callees

- `0x180003c20`
- `0x180006430`
- `0x180008848`
- `0x180010ff4`
- `0x18001101c`
- `0x1800322a8`
- `0x180040320`
- `0x1800414f4`
- `0x180041988`
- `0x180041d4c`
- `0x180041fbc`
- `0x180042148`
- `0x1800430c4`
- `0x18004328c`
- `0x180047e08`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042261`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042261`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004272c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004272c`
- `USER32!SendMessageW` at `0x1800425ea`
- `USER32!SendMessageW` at `0x180042627`
- `USER32!SendMessageW` at `0x1800426e6`
- `USER32!SendMessageW` at `0x180042708`
- `USER32!SendMessageW` at `0x18004271f`
- `USER32!SendMessageW` at `0x1800425ea`
- `USER32!SendMessageW` at `0x180042627`
- `USER32!SendMessageW` at `0x1800426e6`
- `USER32!SendMessageW` at `0x180042708`
- `USER32!SendMessageW` at `0x18004271f`

## string_xrefs

- `0x1800423ef`: `LinkTargetCaching`

## pseudocode

```c
__int64 __fastcall CPinProgressDialog::_DoThreadWork(CPinProgressDialog *this)
{
  CPinProgress **v1; // r15
  int Instance; // eax
  int StringPtrArray; // edi
  UstCommon::CImpersonator *v5; // rcx
  CPinProgress *v6; // rcx
  CStringSet *v7; // rcx
  HRESULT v8; // eax
  void *v9; // rdx
  unsigned __int16 **v10; // r14
  unsigned int v11; // ecx
  int v12; // eax
  int v13; // r8d
  const unsigned __int16 *v14; // rdx
  IID *v15; // rcx
  int v16; // eax
  unsigned int v17; // ecx
  CPinProgressDialog *v18; // rcx
  int v19; // ecx
  int v20; // edi
  unsigned int v21; // eax
  UstCommon::CImpersonator *v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // edx
  unsigned int v25; // r8d
  int v26; // r9d
  int v27; // r14d
  unsigned int v28; // eax
  HWND v29; // rcx
  int v30; // eax
  UstCommon::CImpersonator *v31; // rcx
  __int64 v32; // r9
  int ppv; // [rsp+20h] [rbp-50h]
  struct CInvSemaphore *ppva; // [rsp+20h] [rbp-50h]
  int (*v36)(struct tagMSG *); // [rsp+28h] [rbp-48h]
  int *v37; // [rsp+30h] [rbp-40h]
  void *v38; // [rsp+50h] [rbp-20h] BYREF
  struct IOfflineFilesSyncProgress *v39; // [rsp+58h] [rbp-18h] BYREF
  struct ISyncMgrSyncCallback *v40; // [rsp+60h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 **v42; // [rsp+B8h] [rbp+48h] BYREF
  int v43; // [rsp+C0h] [rbp+50h] BYREF
  struct IOfflineFilesCache *v44; // [rsp+C8h] [rbp+58h] BYREF

  v1 = (CPinProgress **)((char *)this + 296);
  Instance = CPinProgress::CreateInstance(
               *((HWND *)this + 3),
               *((_DWORD *)this + 8),
               *((void **)this + 32),
               (struct CPinProgress **)this + 37);
  StringPtrArray = Instance;
  if ( Instance >= 0 )
  {
    v6 = *v1;
    pHandles = 0;
    StringPtrArray = (**(__int64 (__fastcall ***)(CPinProgress *, GUID *, HANDLE *))v6)(
                       v6,
                       &GUID_6931f49a_6fc7_4c1b_b265_56793fc451b7,
                       &pHandles);
    if ( StringPtrArray < 0 )
      goto LABEL_76;
    StringPtrArray = MarshalToGIT(
                       (struct IUnknown *)pHandles,
                       &GUID_6931f49a_6fc7_4c1b_b265_56793fc451b7,
                       (unsigned int *)this + 76);
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)pHandles + 16LL))(pHandles);
    if ( StringPtrArray < 0 )
      goto LABEL_76;
    v7 = (CStringSet *)*((_QWORD *)this + 34);
    v42 = 0;
    LODWORD(pHandles) = 0;
    StringPtrArray = CStringSet::CreateStringPtrArray(v7, (const unsigned __int16 ***)&v42, (unsigned int *)&pHandles);
    if ( StringPtrArray < 0 )
    {
LABEL_55:
      if ( *((_DWORD *)this + 12) )
        goto LABEL_75;
      v29 = (HWND)*((_QWORD *)this + 3);
      if ( !v29 )
        goto LABEL_75;
      SendMessageW(v29, 0x46Cu, 3u, 4459LL - (*((_DWORD *)this + 8) != 0));
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids);
      }
      SendMessageW(*((HWND *)this + 3), 0x46Fu, 2u, 0);
      v30 = *((_DWORD *)*v1 + 10);
      if ( v30 >= 0 )
      {
        v32 = *((unsigned int *)*v1 + 3);
        if ( (int)v32 <= 0 )
        {
          SendMessageW(*((HWND *)this + 3), 0x46Bu, 0, 0xFFFFFFFFLL);
          SendMessageW(*((HWND *)this + 3), 0x46Cu, 0, (LPARAM)&lParam);
          *((_DWORD *)this + 13) = 1;
          *((_DWORD *)this + 15) = GetTickCount();
          goto LABEL_75;
        }
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids, v32);
        }
      }
      else
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids,
            (unsigned int)v30);
          v31 = WPP_GLOBAL_Control;
        }
        if ( *((_DWORD *)*v1 + 3) == 1 )
        {
          CPinProgressDialog::_ReportEndResultError(this, *((_DWORD *)*v1 + 10));
          v31 = WPP_GLOBAL_Control;
        }
        if ( v31 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 0x40) != 0 )
          WPP_SF_(*((_QWORD *)v31 + 2), 45, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids);
      }
      SendMessageW(*((HWND *)this + 3), 0x468u, 2u, 0);
      CPinProgressDialog::_AnnouncePresenceOfErrors(this);
LABEL_75:
      CPinProgress::SetProgressOut(*v1, 0);
      (*(void (__fastcall **)(CPinProgress *))(*(_QWORD *)*v1 + 16LL))(*v1);
      *v1 = 0;
      goto LABEL_76;
    }
    v44 = 0;
    v8 = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 3u, &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5, (LPVOID *)&v44);
    v10 = v42;
    StringPtrArray = v8;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids,
          (unsigned int)v8);
      }
LABEL_40:
      CscUtil_HeapFree(v10, v9);
      if ( StringPtrArray >= 0 )
      {
        v27 = 0;
        pHandles = (HANDLE)*((_QWORD *)this + 32);
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids);
        }
        while ( !v27 )
        {
          v28 = CscUtil_WaitAndProcessThreadMessages(&pHandles, v24, v25, v26, ppv, v36, v37);
          if ( v28 == -1 )
          {
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids);
            }
            StringPtrArray = -2147467259;
            goto LABEL_55;
          }
          if ( !v28 )
          {
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids);
            }
            v27 = 1;
          }
        }
      }
      goto LABEL_55;
    }
    v11 = *((_DWORD *)this + 70);
    v40 = 0;
    v12 = UnMarshalFromGIT(v11, &GUID_884ccd87_b139_4937_a4ba_4f8e19513fbe, (void **)&v40);
    StringPtrArray = v12;
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids,
          (unsigned int)v12);
      }
      goto LABEL_39;
    }
    v13 = *((_DWORD *)this + 10);
    v14 = (const unsigned __int16 *)*((_QWORD *)this + 8);
    v15 = (IID *)*((_QWORD *)this + 9);
    ppva = (struct CInvSemaphore *)*((_QWORD *)this + 36);
    v39 = 0;
    v16 = CSyncItemProgress::CreateInstance(v15, v14, v13, v40, ppva, (const struct _GUID *)v36, (void **)&v39, 0);
    StringPtrArray = v16;
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids,
          (unsigned int)v16);
      }
      goto LABEL_38;
    }
    StringPtrArray = CPinProgress::SetProgressOut(*v1, v39);
    if ( StringPtrArray < 0
      || (v17 = *((_DWORD *)this + 76),
          v38 = 0,
          StringPtrArray = UnMarshalFromGIT(v17, &GUID_6931f49a_6fc7_4c1b_b265_56793fc451b7, &v38),
          StringPtrArray < 0) )
    {
LABEL_37:
      ((void (__fastcall *)(struct IOfflineFilesSyncProgress *))v39->lpVtbl->Release)(v39);
LABEL_38:
      ((void (__fastcall *)(struct ISyncMgrSyncCallback *))v40->lpVtbl->Release)(v40);
LABEL_39:
      ((void (__fastcall *)(struct IOfflineFilesCache *))v44->lpVtbl->Release)(v44);
      goto LABEL_40;
    }
    if ( *((_DWORD *)this + 8) )
    {
      CPinProgressDialog::_UpdateItemLastSyncTime(
        v18,
        *((const unsigned __int16 **)this + 8),
        (const struct _FILETIME *)((char *)this + 308));
      v19 = *((_DWORD *)this + 8);
    }
    else
    {
      v19 = 0;
    }
    v20 = *((_DWORD *)this + 11) != 0 ? 2080 : 32;
    if ( v19 )
    {
      LODWORD(v42) = 0;
      v43 = 0;
      if ( (int)CscConfig_QueryNumericSetting(v44, L"LinkTargetCaching", (unsigned int *)&v42, &v43) >= 0 && (_DWORD)v42 )
        v20 |= 0x10u;
      LODWORD(v37) = v20 | 1;
      LODWORD(v36) = 1;
      ppv = *((_DWORD *)this + 9);
      v21 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, _QWORD, unsigned __int16 **, _QWORD))v44->lpVtbl->Pin)(
              v44,
              *((_QWORD *)this + 3),
              v10,
              (unsigned int)pHandles);
      StringPtrArray = v21;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      {
        goto LABEL_36;
      }
      v23 = 38;
    }
    else
    {
      LODWORD(v37) = *((_DWORD *)this + 11) != 0 ? 2080 : 32;
      LODWORD(v36) = 1;
      ppv = *((_DWORD *)this + 9);
      v21 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, _QWORD, unsigned __int16 **, _QWORD))v44->lpVtbl->Unpin)(
              v44,
              *((_QWORD *)this + 3),
              v10,
              (unsigned int)pHandles);
      StringPtrArray = v21;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      {
        goto LABEL_36;
      }
      v23 = 39;
    }
    WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids, v21);
LABEL_36:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
    goto LABEL_37;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
    return (unsigned int)StringPtrArray;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids,
      (unsigned int)Instance);
LABEL_76:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 47, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids, (unsigned int)StringPtrArray);
  return (unsigned int)StringPtrArray;
}

```

## disassembly

```asm
0x180042148  push    rbp
0x18004214a  push    rbx
0x18004214b  push    rdi
0x18004214c  push    r12
0x18004214e  push    r13
0x180042150  push    r14
0x180042152  push    r15
0x180042154  mov     rbp, rsp
0x180042157  sub     rsp, 70h
0x18004215b  mov     r8, [rcx+100h]; void *
0x180042162  lea     r15, [rcx+128h]
0x180042169  mov     edx, [rcx+20h]; int
0x18004216c  mov     rbx, rcx
0x18004216f  mov     rcx, [rcx+18h]; HWND
0x180042173  mov     r9, r15; struct CPinProgress **
0x180042176  call    ?CreateInstance@CPinProgress@@SAJPEAUHWND__@@HPEAXPEAPEAV1@@Z; CPinProgress::CreateInstance(HWND__ *,int,void *,CPinProgress * *)
0x18004217b  xor     r12d, r12d
0x18004217e  lea     r13, WPP_GLOBAL_Control
0x180042185  mov     edi, eax
0x180042187  test    eax, eax
0x180042189  jns     short loc_1800421C2
0x18004218b  mov     rcx, cs:WPP_GLOBAL_Control
0x180042192  cmp     rcx, r13
0x180042195  jz      loc_18004277B
0x18004219b  test    byte ptr [rcx+1Ch], 2
0x18004219f  jz      loc_180042758
0x1800421a5  mov     rcx, [rcx+10h]
0x1800421a9  lea     edx, [r12+22h]
0x1800421ae  mov     r9d, eax
0x1800421b1  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x1800421b8  call    WPP_SF_d
0x1800421bd  jmp     loc_180042751
0x1800421c2  mov     rcx, [r15]
0x1800421c5  lea     r8, [rbp+pHandles]
0x1800421c9  mov     [rbp+pHandles], r12
0x1800421cd  lea     rdx, _GUID_6931f49a_6fc7_4c1b_b265_56793fc451b7
0x1800421d4  mov     rax, [rcx]
0x1800421d7  mov     rax, [rax]
0x1800421da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421df  mov     edi, eax
0x1800421e1  test    eax, eax
0x1800421e3  js      loc_180042751
0x1800421e9  mov     rcx, [rbp+pHandles]; struct IUnknown *
0x1800421ed  lea     r8, [rbx+130h]; unsigned int *
0x1800421f4  lea     rdx, _GUID_6931f49a_6fc7_4c1b_b265_56793fc451b7; struct _GUID *
0x1800421fb  call    ?MarshalToGIT@@YAJPEAUIUnknown@@AEBU_GUID@@PEAK@Z; MarshalToGIT(IUnknown *,_GUID const &,ulong *)
0x180042200  mov     rcx, [rbp+pHandles]
0x180042204  mov     edi, eax
0x180042206  mov     rax, [rcx]
0x180042209  mov     rax, [rax+10h]
0x18004220d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042212  test    edi, edi
0x180042214  js      loc_180042751
0x18004221a  mov     rcx, [rbx+110h]; this
0x180042221  lea     r8, [rbp+pHandles]; unsigned int *
0x180042225  lea     rdx, [rbp+arg_8]; unsigned __int16 ***
0x180042229  mov     [rbp+arg_8], r12
0x18004222d  mov     dword ptr [rbp+pHandles], r12d
0x180042231  call    ?CreateStringPtrArray@CStringSet@@QEAAJPEAPEAPEBGPEAK@Z; CStringSet::CreateStringPtrArray(ushort const * * *,ulong *)
0x180042236  mov     edi, eax
0x180042238  test    eax, eax
0x18004223a  js      loc_1800425B5
0x180042240  xor     edx, edx; pUnkOuter
0x180042242  mov     [rbp+arg_18], r12
0x180042246  lea     rax, [rbp+arg_18]
0x18004224a  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x180042251  mov     [rsp+70h+ppv], rax; ppv
0x180042256  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x18004225d  lea     r8d, [rdx+3]; dwClsContext
0x180042261  call    cs:__imp_CoCreateInstance
0x180042267  mov     r14, [rbp+arg_8]
0x18004226b  mov     edi, eax
0x18004226d  test    eax, eax
0x18004226f  jns     short loc_1800422A8
0x180042271  mov     rcx, cs:WPP_GLOBAL_Control
0x180042278  cmp     rcx, r13
0x18004227b  jz      loc_1800424FC
0x180042281  test    byte ptr [rcx+1Ch], 2
0x180042285  jz      loc_1800424FC
0x18004228b  mov     rcx, [rcx+10h]
0x18004228f  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x180042296  mov     edx, 23h ; '#'
0x18004229b  mov     r9d, eax
0x18004229e  call    WPP_SF_d
0x1800422a3  jmp     loc_1800424FC
0x1800422a8  mov     ecx, [rbx+118h]; unsigned int
0x1800422ae  lea     r8, [rbp+var_10]; void **
0x1800422b2  lea     rdx, _GUID_884ccd87_b139_4937_a4ba_4f8e19513fbe; struct _GUID *
0x1800422b9  mov     [rbp+var_10], r12
0x1800422bd  call    ?UnMarshalFromGIT@@YAJKAEBU_GUID@@PEAPEAX@Z; UnMarshalFromGIT(ulong,_GUID const &,void * *)
0x1800422c2  mov     edi, eax
0x1800422c4  test    eax, eax
0x1800422c6  jns     short loc_1800422FF
0x1800422c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800422cf  cmp     rcx, r13
0x1800422d2  jz      loc_1800424EC
0x1800422d8  test    byte ptr [rcx+1Ch], 2
0x1800422dc  jz      loc_1800424EC
0x1800422e2  mov     rcx, [rcx+10h]
0x1800422e6  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x1800422ed  mov     edx, 24h ; '$'
0x1800422f2  mov     r9d, eax
0x1800422f5  call    WPP_SF_d
0x1800422fa  jmp     loc_1800424EC
0x1800422ff  mov     r9, [rbp+var_10]; struct ISyncMgrSyncCallback *
0x180042303  lea     rax, [rbp+var_18]
0x180042307  mov     r8d, [rbx+28h]; int
0x18004230b  mov     rdx, [rbx+40h]; unsigned __int16 *
0x18004230f  mov     rcx, [rbx+48h]; rclsid
0x180042313  mov     [rsp+70h+var_38], r12d; int
0x180042318  mov     [rsp+70h+var_40], rax; void **
0x18004231d  mov     rax, [rbx+120h]
0x180042324  mov     [rsp+70h+ppv], rax; struct CInvSemaphore *
0x180042329  mov     [rbp+var_18], r12
0x18004232d  call    ?CreateInstance@CSyncItemProgress@@SAJAEBU_GUID@@PEBGHPEAUISyncMgrSyncCallback@@AEAVCInvSemaphore@@0PEAPEAXH@Z; CSyncItemProgress::CreateInstance(_GUID const &,ushort const *,int,ISyncMgrSyncCallback *,CInvSemaphore &,_GUID const &,void * *,int)
0x180042332  mov     edi, eax
0x180042334  test    eax, eax
0x180042336  jns     short loc_18004236F
0x180042338  mov     rcx, cs:WPP_GLOBAL_Control
0x18004233f  cmp     rcx, r13
0x180042342  jz      loc_1800424DC
0x180042348  test    byte ptr [rcx+1Ch], 2
0x18004234c  jz      loc_1800424DC
0x180042352  mov     rcx, [rcx+10h]
0x180042356  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x18004235d  mov     edx, 25h ; '%'
0x180042362  mov     r9d, eax
0x180042365  call    WPP_SF_d
0x18004236a  jmp     loc_1800424DC
0x18004236f  mov     rdx, [rbp+var_18]; struct IOfflineFilesSyncProgress *
0x180042373  mov     rcx, [r15]; this
0x180042376  call    ?SetProgressOut@CPinProgress@@QEAAJPEAUIOfflineFilesSyncProgress@@@Z; CPinProgress::SetProgressOut(IOfflineFilesSyncProgress *)
0x18004237b  mov     edi, eax
0x18004237d  test    eax, eax
0x18004237f  js      loc_1800424CC
0x180042385  mov     ecx, [rbx+130h]; unsigned int
0x18004238b  lea     r8, [rbp+var_20]; void **
0x18004238f  lea     rdx, _GUID_6931f49a_6fc7_4c1b_b265_56793fc451b7; struct _GUID *
0x180042396  mov     [rbp+var_20], r12
0x18004239a  call    ?UnMarshalFromGIT@@YAJKAEBU_GUID@@PEAPEAX@Z; UnMarshalFromGIT(ulong,_GUID const &,void * *)
0x18004239f  mov     edi, eax
0x1800423a1  test    eax, eax
0x1800423a3  js      loc_1800424CC
0x1800423a9  cmp     [rbx+20h], r12d
0x1800423ad  jz      short loc_1800423C4
0x1800423af  mov     rdx, [rbx+40h]; unsigned __int16 *
0x1800423b3  lea     r8, [rbx+134h]; struct _FILETIME *
0x1800423ba  call    ?_UpdateItemLastSyncTime@CPinProgressDialog@@AEAAJPEBGAEBU_FILETIME@@@Z; CPinProgressDialog::_UpdateItemLastSyncTime(ushort const *,_FILETIME const &)
0x1800423bf  mov     ecx, [rbx+20h]
0x1800423c2  jmp     short loc_1800423C7
0x1800423c4  mov     ecx, r12d
0x1800423c7  mov     eax, [rbx+2Ch]
0x1800423ca  neg     eax
0x1800423cc  sbb     edi, edi
0x1800423ce  and     edi, 800h
0x1800423d4  add     edi, 20h ; ' '
0x1800423d7  test    ecx, ecx
0x1800423d9  mov     rcx, [rbp+arg_18]; struct IOfflineFilesCache *
0x1800423dd  jz      short loc_18004245D
0x1800423df  lea     r9, [rbp+arg_10]; int *
0x1800423e3  mov     dword ptr [rbp+arg_8], r12d
0x1800423e7  lea     r8, [rbp+arg_8]; unsigned int *
0x1800423eb  mov     [rbp+arg_10], r12d
0x1800423ef  lea     rdx, aLinktargetcach; "LinkTargetCaching"
0x1800423f6  call    ?CscConfig_QueryNumericSetting@@YAJPEAUIOfflineFilesCache@@PEBGPEAKPEAH@Z; CscConfig_QueryNumericSetting(IOfflineFilesCache *,ushort const *,ulong *,int *)
0x1800423fb  test    eax, eax
0x1800423fd  js      short loc_180042408
0x1800423ff  cmp     dword ptr [rbp+arg_8], r12d
0x180042403  jz      short loc_180042408
0x180042405  or      edi, 10h
0x180042408  mov     rdx, [rbp+var_20]
0x18004240c  or      edi, 1
0x18004240f  mov     rcx, [rbp+arg_18]
0x180042413  mov     r8, r14
0x180042416  mov     r9d, dword ptr [rbp+pHandles]
0x18004241a  mov     qword ptr [rsp+70h+var_38], rdx
0x18004241f  mov     edx, [rbx+24h]
0x180042422  mov     rax, [rcx]
0x180042425  mov     dword ptr [rsp+70h+var_40], edi
0x180042429  mov     dword ptr [rsp+70h+var_48], 1
0x180042431  mov     dword ptr [rsp+70h+ppv], edx
0x180042435  mov     rax, [rax+30h]
0x180042439  mov     rdx, [rbx+18h]
0x18004243d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042442  mov     edi, eax
0x180042444  mov     rcx, cs:WPP_GLOBAL_Control
0x18004244b  cmp     rcx, r13
0x18004244e  jz      short loc_1800424BC
0x180042450  test    byte ptr [rcx+1Ch], 40h
0x180042454  jz      short loc_1800424BC
0x180042456  mov     edx, 26h ; '&'
0x18004245b  jmp     short loc_1800424A9
0x18004245d  mov     rdx, [rbp+var_20]
0x180042461  mov     r8, r14
0x180042464  mov     rax, [rcx]
0x180042467  mov     r9d, dword ptr [rbp+pHandles]
0x18004246b  mov     qword ptr [rsp+70h+var_38], rdx
0x180042470  mov     edx, [rbx+24h]
0x180042473  mov     rax, [rax+38h]
0x180042477  mov     dword ptr [rsp+70h+var_40], edi; int *
0x18004247b  mov     dword ptr [rsp+70h+var_48], 1; int (*)(struct tagMSG *)
0x180042483  mov     dword ptr [rsp+70h+ppv], edx; int
0x180042487  mov     rdx, [rbx+18h]
0x18004248b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042490  mov     edi, eax
0x180042492  mov     rcx, cs:WPP_GLOBAL_Control
0x180042499  cmp     rcx, r13
0x18004249c  jz      short loc_1800424BC
0x18004249e  test    byte ptr [rcx+1Ch], 40h
0x1800424a2  jz      short loc_1800424BC
0x1800424a4  mov     edx, 27h ; '''
0x1800424a9  mov     rcx, [rcx+10h]
0x1800424ad  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x1800424b4  mov     r9d, eax
0x1800424b7  call    WPP_SF_d
0x1800424bc  mov     rcx, [rbp+var_20]
0x1800424c0  mov     rax, [rcx]
0x1800424c3  mov     rax, [rax+10h]
0x1800424c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424cc  mov     rcx, [rbp+var_18]
0x1800424d0  mov     rax, [rcx]
0x1800424d3  mov     rax, [rax+10h]
0x1800424d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424dc  mov     rcx, [rbp+var_10]
0x1800424e0  mov     rax, [rcx]
0x1800424e3  mov     rax, [rax+10h]
0x1800424e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424ec  mov     rcx, [rbp+arg_18]
0x1800424f0  mov     rax, [rcx]
0x1800424f3  mov     rax, [rax+10h]
0x1800424f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424fc  mov     rcx, r14; lpMem
0x1800424ff  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180042504  test    edi, edi
0x180042506  js      loc_1800425B5
0x18004250c  mov     rax, [rbx+100h]
0x180042513  mov     r14d, r12d
0x180042516  mov     [rbp+pHandles], rax
0x18004251a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042521  cmp     rcx, r13
0x180042524  jz      short loc_180042541
0x180042526  test    byte ptr [rcx+1Ch], 40h
0x18004252a  jz      short loc_180042541
0x18004252c  mov     rcx, [rcx+10h]
0x180042530  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x180042537  mov     edx, 28h ; '('
0x18004253c  call    WPP_SF_
0x180042541  test    r14d, r14d
0x180042544  jnz     short loc_1800425B5
0x180042546  lea     rcx, [rbp+pHandles]; pHandles
0x18004254a  call    ?CscUtil_WaitAndProcessThreadMessages@@YAKPEAPEAXKKHHP6AHPEAUtagMSG@@@ZPEAH@Z; CscUtil_WaitAndProcessThreadMessages(void * *,ulong,ulong,int,int,int (*)(tagMSG *),int *)
0x18004254f  mov     ecx, 0FFFFFFFFh
0x180042554  cmp     eax, ecx
0x180042556  jz      short loc_180042589
0x180042558  test    eax, eax
0x18004255a  jnz     short loc_180042541
0x18004255c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042563  cmp     rcx, r13
0x180042566  jz      short loc_180042581
0x180042568  test    byte ptr [rcx+1Ch], 40h
0x18004256c  jz      short loc_180042581
0x18004256e  mov     rcx, [rcx+10h]
0x180042572  lea     edx, [rax+2Ah]
0x180042575  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x18004257c  call    WPP_SF_
0x180042581  mov     r14d, 1
0x180042587  jmp     short loc_180042541
0x180042589  mov     rcx, cs:WPP_GLOBAL_Control
0x180042590  cmp     rcx, r13
0x180042593  jz      short loc_1800425B0
0x180042595  test    byte ptr [rcx+1Ch], 2
0x180042599  jz      short loc_1800425B0
0x18004259b  mov     rcx, [rcx+10h]
0x18004259f  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x1800425a6  mov     edx, 29h ; ')'
0x1800425ab  call    WPP_SF_
0x1800425b0  mov     edi, 80004005h
0x1800425b5  cmp     [rbx+30h], r12d
0x1800425b9  jnz     loc_180042735
0x1800425bf  mov     rcx, [rbx+18h]; hWnd
0x1800425c3  test    rcx, rcx
0x1800425c6  jz      loc_180042735
0x1800425cc  mov     eax, [rbx+20h]
0x1800425cf  mov     r14d, 46Ch
0x1800425d5  neg     eax
0x1800425d7  mov     r8d, 3; wParam
0x1800425dd  mov     edx, r14d; Msg
0x1800425e0  sbb     r9, r9
0x1800425e3  add     r9, 116Bh; lParam
0x1800425ea  call    cs:__imp_SendMessageW
0x1800425f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800425f7  cmp     rcx, r13
0x1800425fa  jz      short loc_180042617
0x1800425fc  test    byte ptr [rcx+1Ch], 40h
0x180042600  jz      short loc_180042617
0x180042602  mov     rcx, [rcx+10h]
0x180042606  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x18004260d  mov     edx, 2Bh ; '+'
0x180042612  call    WPP_SF_
0x180042617  mov     rcx, [rbx+18h]; hWnd
  ... truncated ...
```

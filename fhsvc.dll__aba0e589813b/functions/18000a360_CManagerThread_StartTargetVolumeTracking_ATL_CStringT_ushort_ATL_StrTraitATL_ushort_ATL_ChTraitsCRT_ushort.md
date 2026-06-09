# CManagerThread::StartTargetVolumeTracking(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x18000a360`
- end: `0x18000aa02`
- name: `?StartTargetVolumeTracking@CManagerThread@@QEAAHV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1698`
- prototype: `__int64 __fastcall(__int64, wint_t **)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, service_task`

## callers

- `0x180004e80`

## callees

- `0x180006d38`
- `0x1800076a0`
- `0x180007720`
- `0x180007800`
- `0x180008640`
- `0x1800092b0`
- `0x1800092f0`
- `0x18000a360`
- `0x18000ac14`
- `0x18000b1cc`
- `0x18000b1e8`
- `0x18000b250`
- `0x18000b348`
- `0x18000b448`
- `0x18000b48c`
- `0x18000b4ac`
- `0x18000b5b4`
- `0x18000be90`
- `0x18000d0a8`
- `0x18000d970`
- `0x18000daf0`
- `0x18000ec74`
- `0x18000f5e8`
- `0x18000fcd4`
- `0x18000fe58`
- `0x18001044c`
- `0x180011980`
- `0x180013010`

## import_xrefs

- `msvcrt!iswalpha` at `0x18000a3f8`
- `msvcrt!iswalpha` at `0x18000a3f8`
- `KERNEL32!GetLastError` at `0x18000a719`
- `KERNEL32!GetLastError` at `0x18000a7db`
- `KERNEL32!GetLastError` at `0x18000a719`
- `KERNEL32!GetLastError` at `0x18000a7db`
- `KERNEL32!CloseHandle` at `0x18000a991`
- `KERNEL32!CloseHandle` at `0x18000a991`
- `KERNEL32!EnterCriticalSection` at `0x18000a5ec`
- `KERNEL32!EnterCriticalSection` at `0x18000a5ec`
- `KERNEL32!LeaveCriticalSection` at `0x18000a77c`
- `KERNEL32!LeaveCriticalSection` at `0x18000a841`
- `KERNEL32!LeaveCriticalSection` at `0x18000a923`
- `KERNEL32!LeaveCriticalSection` at `0x18000a96b`
- `KERNEL32!LeaveCriticalSection` at `0x18000a77c`
- `KERNEL32!LeaveCriticalSection` at `0x18000a841`
- `KERNEL32!LeaveCriticalSection` at `0x18000a923`
- `KERNEL32!LeaveCriticalSection` at `0x18000a96b`
- `KERNEL32!CreateFileW` at `0x18000a705`
- `KERNEL32!CreateFileW` at `0x18000a705`
- `USER32!RegisterDeviceNotificationW` at `0x18000a7bb`
- `USER32!RegisterDeviceNotificationW` at `0x18000a7bb`

## pseudocode

```c
__int64 __fastcall CManagerThread::StartTargetVolumeTracking(__int64 a1, wint_t **a2)
{
  __int64 v3; // rbx
  const WCHAR *v4; // rdi
  __int64 v5; // r12
  __int64 v6; // rcx
  __int64 v7; // rsi
  __int64 Manager; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  int *v11; // r14
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  int *v18; // r14
  __int64 v19; // rdi
  _QWORD *v20; // rax
  _QWORD *v21; // rsi
  _QWORD *v22; // rcx
  _QWORD *v23; // r14
  _QWORD *v24; // rcx
  int *v25; // rsi
  __int64 v26; // r13
  HANDLE FileW; // rax
  signed int LastError; // eax
  char v29; // cl
  HDEVNOTIFY v30; // rax
  _QWORD *v31; // rsi
  signed int v32; // eax
  char v33; // cl
  __int64 v34; // rax
  int v35; // edx
  int v36; // r8d
  __int64 v37; // rcx
  bool v38; // zf
  _QWORD *v40; // [rsp+40h] [rbp-B8h] BYREF
  unsigned int v41; // [rsp+48h] [rbp-B0h]
  char *v42; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A0h] BYREF
  const WCHAR *v44; // [rsp+60h] [rbp-98h] BYREF
  __int64 v45; // [rsp+68h] [rbp-90h]
  wint_t **v46; // [rsp+70h] [rbp-88h]
  struct _RTL_CRITICAL_SECTION *v47; // [rsp+78h] [rbp-80h] BYREF
  __int128 NotificationFilter; // [rsp+88h] [rbp-70h] BYREF
  __int128 v49; // [rsp+98h] [rbp-60h]
  __int128 v50; // [rsp+A8h] [rbp-50h]
  __int64 v51; // [rsp+B8h] [rbp-40h]

  v46 = a2;
  v3 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v43 = v3;
  v4 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v44 = v4;
  v5 = -1;
  v45 = -1;
  v41 = 1;
  if ( *((int *)*a2 - 4) >= 2 && iswalpha(**a2) )
  {
    v6 = (__int64)(*a2 - 12);
    if ( *(int *)(v6 + 8) < 1 )
      ATL::AtlThrowImpl(-2147024809);
    if ( (*a2)[1] == 58 )
    {
      if ( *(int *)(v6 + 8) > 2 )
      {
        Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(a2);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v40,
          *a2,
          2,
          Manager);
        v7 = (__int64)v40;
      }
      else
      {
        v7 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v6) + 24;
        v40 = (_QWORD *)v7;
      }
      v9 = *(_QWORD *)ATL::operator+(&v42, &v40);
      v10 = (_QWORD *)(v9 - 24);
      v11 = (int *)(v3 - 24);
      if ( v9 - 24 != v3 - 24 )
      {
        if ( v11[4] >= 0 && *v10 == *(_QWORD *)v11 )
        {
          v12 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v10);
          ATL::CStringData::Release((ATL::CStringData *)v11);
          v3 = v12 + 24;
          v43 = v3;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v43, v9, *(unsigned int *)(v9 - 16));
          v3 = v43;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
      v13 = (__int64)(*a2 - 12);
      if ( *(int *)(v13 + 8) > 2 )
      {
        v15 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(a2);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v42,
          *a2,
          2,
          v15);
        v14 = (__int64)v42;
      }
      else
      {
        v14 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v13) + 24;
        v42 = (char *)v14;
      }
      v40 = (_QWORD *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( (unsigned __int64)L"\\\\.\\" >= 0x10000 )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v40);
      else
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
          &v40,
          (unsigned __int16)L"\\\\.\\");
      v16 = *(_QWORD *)ATL::operator+(&v47, &v40, &v42);
      v17 = (_QWORD *)(v16 - 24);
      v18 = (int *)(v4 - 12);
      if ( (const WCHAR *)(v16 - 24) != v4 - 12 )
      {
        if ( v18[4] >= 0 && *v17 == *(_QWORD *)v18 )
        {
          v19 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v17);
          ATL::CStringData::Release((ATL::CStringData *)v18);
          v4 = (const WCHAR *)(v19 + 24);
          v44 = v4;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v44, v16, *(unsigned int *)(v16 - 16));
          v4 = v44;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)&v47[-1].OwningThread);
      ATL::CStringData::Release((ATL::CStringData *)(v40 - 3));
      ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
      v47 = &stru_1800199F0;
      EnterCriticalSection(&stru_1800199F0);
      SmartPtr<CWorkerThread>::SmartPtr<CWorkerThread>(&v40);
      if ( !(unsigned __int8)ATL::CRBMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Lookup(
                               &qword_180019A18,
                               v3,
                               &v40) )
      {
        NotificationFilter = 0;
        v49 = 0;
        v50 = 0;
        v51 = 0;
        v20 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        v21 = v20;
        v42 = (char *)v20;
        if ( v20 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v20);
          v21[1] = 0;
          v21[2] = 0;
          *((_DWORD *)v21 + 6) = 0;
        }
        else
        {
          v21 = 0;
        }
        SmartPtr<CVolumeTrackingDescriptor>::operator=(&v40, v21);
        v22 = v40;
        if ( !v40 || !*v40 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              150,
              &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
              "volumeDesc");
            v22 = v40;
          }
          if ( !v22 )
            goto LABEL_43;
LABEL_42:
          SmartPtr<CVolumeTrackingDescriptor>::RefCounter::Dec_nRefs();
LABEL_43:
          LeaveCriticalSection(&stru_1800199F0);
          goto LABEL_69;
        }
        v23 = (_QWORD *)*v40;
        v24 = (_QWORD *)(v3 - 24);
        v25 = (int *)(*(_QWORD *)*v40 - 24LL);
        if ( (int *)(v3 - 24) != v25 )
        {
          if ( v25[4] >= 0 && *v24 == *(_QWORD *)v25 )
          {
            v26 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v24);
            ATL::CStringData::Release((ATL::CStringData *)v25);
            *v23 = v26 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(*v40, v3, *(unsigned int *)(v3 - 16));
          }
        }
        FileW = CreateFileW(v4, 0, 7u, 0, 3u, 0x200080u, 0);
        v5 = (__int64)FileW;
        v45 = (__int64)FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          v29 = LastError;
          if ( LastError > 0 )
            v29 = LastError;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              151,
              (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
              (_DWORD)v4,
              v29);
          if ( !v40 )
            goto LABEL_43;
          goto LABEL_42;
        }
        *(_QWORD *)&NotificationFilter = 0x600000038LL;
        *(_QWORD *)&v49 = FileW;
        v30 = RegisterDeviceNotificationW(g_Service, &NotificationFilter, 1u);
        *(_QWORD *)(*v40 + 8LL) = v30;
        v31 = (_QWORD *)*v40;
        if ( !*(_QWORD *)(*v40 + 8LL) )
        {
          v32 = GetLastError();
          v33 = v32;
          if ( v32 > 0 )
            v33 = v32;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              152,
              (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
              *(_QWORD *)*v40,
              v33);
          SmartPtr<CVolumeTrackingDescriptor>::~SmartPtr<CVolumeTrackingDescriptor>(&v40);
          LeaveCriticalSection(&stru_1800199F0);
LABEL_67:
          CloseHandle((HANDLE)v5);
          goto LABEL_69;
        }
        v34 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(
                &qword_180019A18,
                *v31);
        if ( v34 )
          SmartPtr<CVolumeTrackingDescriptor>::operator=(v34 + 8, &v40);
        else
          ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBInsert(
            &qword_180019A18,
            *v31,
            &v40);
        ATL::CRBMap<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetAt(
          (char *)&xmmword_180019A40 + 8,
          *(_QWORD *)(*v40 + 8LL),
          &v40);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, v36, *(_QWORD *)*v40, *(_QWORD *)(*v40 + 8LL));
      }
      v37 = *v40;
      if ( *(_DWORD *)(*v40 + 16LL) || *(_DWORD *)(v37 + 20) || (v38 = *(_DWORD *)(v37 + 24) == 0, v41 = 1, !v38) )
        v41 = 0;
      SmartPtr<CVolumeTrackingDescriptor>::~SmartPtr<CVolumeTrackingDescriptor>(&v40);
      LeaveCriticalSection(&stru_1800199F0);
      if ( v5 != -1 )
        goto LABEL_67;
    }
  }
LABEL_69:
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v3 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2);
  return v41;
}

```

## disassembly

```asm
0x18000a360  mov     [rsp+arg_0], rbx
0x18000a365  mov     [rsp+arg_10], rsi
0x18000a36a  push    rdi
0x18000a36b  push    r12
0x18000a36d  push    r13
0x18000a36f  push    r14
0x18000a371  push    r15
0x18000a373  sub     rsp, 0D0h
0x18000a37a  mov     rax, cs:__security_cookie
0x18000a381  xor     rax, rsp
0x18000a384  mov     [rsp+0F8h+var_38], rax
0x18000a38c  mov     r15, rdx
0x18000a38f  mov     [rsp+0F8h+var_88], rdx
0x18000a394  xor     r13d, r13d
0x18000a397  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a39e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a3a5  mov     rax, [rax+18h]
0x18000a3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3ae  lea     rbx, [rax+18h]
0x18000a3b2  mov     [rsp+0F8h+var_A0], rbx
0x18000a3b7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a3be  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a3c5  mov     rax, [rax+18h]
0x18000a3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3ce  lea     rdi, [rax+18h]
0x18000a3d2  mov     [rsp+0F8h+var_98], rdi
0x18000a3d7  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000a3db  mov     [rsp+0F8h+var_90], r12
0x18000a3e0  mov     [rsp+0F8h+var_B0], 1
0x18000a3e8  mov     rcx, [r15]
0x18000a3eb  cmp     dword ptr [rcx-10h], 2
0x18000a3ef  jl      loc_18000A9A4
0x18000a3f5  movzx   ecx, word ptr [rcx]; C
0x18000a3f8  call    cs:__imp_iswalpha
0x18000a3fe  test    eax, eax
0x18000a400  jz      loc_18000A9A4
0x18000a406  mov     rax, [r15]
0x18000a409  lea     rcx, [rax-18h]
0x18000a40d  cmp     dword ptr [rcx+8], 1
0x18000a411  jl      loc_18000A999
0x18000a417  cmp     word ptr [rax+2], 3Ah ; ':'
0x18000a41c  jnz     loc_18000A9A4
0x18000a422  cmp     dword ptr [rcx+8], 2
0x18000a426  jg      short loc_18000A438
0x18000a428  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000a42d  lea     rsi, [rax+18h]
0x18000a431  mov     [rsp+0F8h+var_B8], rsi
0x18000a436  jmp     short loc_18000A45B
0x18000a438  mov     rcx, r15
0x18000a43b  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x18000a440  mov     r9, rax
0x18000a443  mov     r8d, 2
0x18000a449  mov     rdx, [r15]
0x18000a44c  lea     rcx, [rsp+0F8h+var_B8]
0x18000a451  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int,ATL::IAtlStringMgr *)
0x18000a456  mov     rsi, [rsp+0F8h+var_B8]
0x18000a45b  lea     rdx, [rsp+0F8h+var_B8]
0x18000a460  lea     rcx, [rsp+0F8h+var_A8]
0x18000a465  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x18000a46a  nop
0x18000a46b  mov     rdx, [rax]
0x18000a46e  lea     rcx, [rdx-18h]
0x18000a472  lea     r14, [rbx-18h]
0x18000a476  cmp     rcx, r14
0x18000a479  jz      short loc_18000A4B7
0x18000a47b  cmp     [r14+10h], r13d
0x18000a47f  jl      short loc_18000A4A4
0x18000a481  mov     rax, [r14]
0x18000a484  cmp     [rcx], rax
0x18000a487  jnz     short loc_18000A4A4
0x18000a489  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000a48e  mov     rbx, rax
0x18000a491  mov     rcx, r14; this
0x18000a494  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a499  add     rbx, 18h
0x18000a49d  mov     [rsp+0F8h+var_A0], rbx
0x18000a4a2  jmp     short loc_18000A4B7
0x18000a4a4  mov     r8d, [rdx-10h]
0x18000a4a8  lea     rcx, [rsp+0F8h+var_A0]
0x18000a4ad  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000a4b2  mov     rbx, [rsp+0F8h+var_A0]
0x18000a4b7  mov     rcx, [rsp+0F8h+var_A8]
0x18000a4bc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000a4c0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a4c5  nop
0x18000a4c6  lea     rcx, [rsi-18h]; this
0x18000a4ca  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a4cf  mov     rcx, [r15]
0x18000a4d2  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18000a4d6  cmp     dword ptr [rcx+8], 2
0x18000a4da  jg      short loc_18000A4EC
0x18000a4dc  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000a4e1  lea     rsi, [rax+18h]
0x18000a4e5  mov     [rsp+0F8h+var_A8], rsi
0x18000a4ea  jmp     short loc_18000A50F
0x18000a4ec  mov     rcx, r15
0x18000a4ef  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x18000a4f4  mov     r9, rax
0x18000a4f7  mov     r8d, 2
0x18000a4fd  mov     rdx, [r15]
0x18000a500  lea     rcx, [rsp+0F8h+var_A8]
0x18000a505  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int,ATL::IAtlStringMgr *)
0x18000a50a  mov     rsi, [rsp+0F8h+var_A8]
0x18000a50f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a516  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a51d  mov     rax, [rax+18h]
0x18000a521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a526  add     rax, 18h
0x18000a52a  mov     [rsp+0F8h+var_B8], rax
0x18000a52f  lea     rdx, asc_180015890; "\\\\.\\"
0x18000a536  lea     rcx, [rsp+0F8h+var_B8]
0x18000a53b  cmp     rdx, 10000h
0x18000a542  jnb     short loc_18000A54E
0x18000a544  movzx   edx, dx
0x18000a547  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18000a54c  jmp     short loc_18000A554
0x18000a54e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18000a553  nop
0x18000a554  lea     r8, [rsp+0F8h+var_A8]
0x18000a559  lea     rdx, [rsp+0F8h+var_B8]
0x18000a55e  lea     rcx, [rsp+0F8h+var_80]
0x18000a563  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000a568  nop
0x18000a569  mov     rdx, [rax]
0x18000a56c  lea     rcx, [rdx-18h]
0x18000a570  lea     r14, [rdi-18h]
0x18000a574  cmp     rcx, r14
0x18000a577  jz      short loc_18000A5B5
0x18000a579  cmp     [r14+10h], r13d
0x18000a57d  jl      short loc_18000A5A2
0x18000a57f  mov     rax, [r14]
0x18000a582  cmp     [rcx], rax
0x18000a585  jnz     short loc_18000A5A2
0x18000a587  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000a58c  mov     rdi, rax
0x18000a58f  mov     rcx, r14; this
0x18000a592  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a597  add     rdi, 18h
0x18000a59b  mov     [rsp+0F8h+var_98], rdi
0x18000a5a0  jmp     short loc_18000A5B5
0x18000a5a2  mov     r8d, [rdx-10h]
0x18000a5a6  lea     rcx, [rsp+0F8h+var_98]
0x18000a5ab  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000a5b0  mov     rdi, [rsp+0F8h+var_98]
0x18000a5b5  mov     rcx, [rsp+0F8h+var_80]
0x18000a5ba  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000a5be  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a5c3  nop
0x18000a5c4  mov     rcx, [rsp+0F8h+var_B8]
0x18000a5c9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000a5cd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a5d2  nop
0x18000a5d3  lea     rcx, [rsi-18h]; this
0x18000a5d7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a5dc  nop
0x18000a5dd  lea     r14, stru_1800199F0
0x18000a5e4  mov     [rsp+0F8h+var_80], r14
0x18000a5e9  mov     rcx, r14; lpCriticalSection
0x18000a5ec  call    cs:__imp_EnterCriticalSection
0x18000a5f2  nop
0x18000a5f3  lea     rcx, [rsp+0F8h+var_B8]
0x18000a5f8  call    ??0?$SmartPtr@VCWorkerThread@@@@QEAA@PEAVCWorkerThread@@@Z; SmartPtr<CWorkerThread>::SmartPtr<CWorkerThread>(CWorkerThread *)
0x18000a5fd  nop
0x18000a5fe  lea     r8, [rsp+0F8h+var_B8]
0x18000a603  mov     rdx, rbx
0x18000a606  lea     rcx, qword_180019A18
0x18000a60d  call    ?Lookup@?$CRBMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@QEBA_NPEBGAEAV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z; ATL::CRBMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Lookup(ushort const *,SmartPtr<CVolumeTrackingDescriptor> &)
0x18000a612  test    al, al
0x18000a614  jnz     loc_18000A936
0x18000a61a  xorps   xmm0, xmm0
0x18000a61d  xor     eax, eax
0x18000a61f  movups  [rsp+0F8h+NotificationFilter], xmm0
0x18000a627  movups  [rsp+0F8h+var_60], xmm0
0x18000a62f  movups  [rsp+0F8h+var_50], xmm0
0x18000a637  mov     [rsp+0F8h+var_40], rax
0x18000a63f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a646  lea     ecx, [rax+20h]; unsigned __int64
0x18000a649  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a64e  mov     rsi, rax
0x18000a651  mov     [rsp+0F8h+var_A8], rax
0x18000a656  test    rax, rax
0x18000a659  jz      short loc_18000A671
0x18000a65b  mov     rcx, rax
0x18000a65e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000a663  mov     [rsi+8], r13
0x18000a667  mov     [rsi+10h], r13
0x18000a66b  mov     [rsi+18h], r13d
0x18000a66f  jmp     short loc_18000A674
0x18000a671  mov     rsi, r13
0x18000a674  mov     rdx, rsi
0x18000a677  lea     rcx, [rsp+0F8h+var_B8]
0x18000a67c  call    ??4?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAAEAV0@PEAVCVolumeTrackingDescriptor@@@Z; SmartPtr<CVolumeTrackingDescriptor>::operator=(CVolumeTrackingDescriptor *)
0x18000a681  mov     rcx, [rsp+0F8h+var_B8]
0x18000a686  test    rcx, rcx
0x18000a689  jz      loc_18000A8DA
0x18000a68f  cmp     [rcx], r13
0x18000a692  jz      loc_18000A8DA
0x18000a698  mov     r14, [rcx]
0x18000a69b  lea     rcx, [rbx-18h]
0x18000a69f  mov     rsi, [r14]
0x18000a6a2  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18000a6a6  cmp     rcx, rsi
0x18000a6a9  jz      short loc_18000A6E4
0x18000a6ab  cmp     [rsi+10h], r13d
0x18000a6af  jl      short loc_18000A6D5
0x18000a6b1  mov     rax, [rsi]
0x18000a6b4  cmp     [rcx], rax
0x18000a6b7  jnz     short loc_18000A6D5
0x18000a6b9  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000a6be  mov     r13, rax
0x18000a6c1  mov     rcx, rsi; this
0x18000a6c4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a6c9  lea     rax, [r13+18h]
0x18000a6cd  mov     [r14], rax
0x18000a6d0  xor     r13d, r13d
0x18000a6d3  jmp     short loc_18000A6E4
0x18000a6d5  mov     r8d, [rbx-10h]
0x18000a6d9  mov     rdx, rbx
0x18000a6dc  mov     rcx, r14
0x18000a6df  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000a6e4  mov     [rsp+0F8h+hTemplateFile], r13; hTemplateFile
0x18000a6e9  mov     [rsp+0F8h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x18000a6f1  mov     [rsp+0F8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a6f9  xor     r9d, r9d; lpSecurityAttributes
0x18000a6fc  xor     edx, edx; dwDesiredAccess
0x18000a6fe  lea     r8d, [r9+7]; dwShareMode
0x18000a702  mov     rcx, rdi; lpFileName
0x18000a705  call    cs:__imp_CreateFileW
0x18000a70b  mov     r12, rax
0x18000a70e  mov     [rsp+0F8h+var_90], rax
0x18000a713  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a717  jnz     short loc_18000A788
0x18000a719  call    cs:__imp_GetLastError
0x18000a71f  mov     ecx, eax
0x18000a721  test    eax, eax
0x18000a723  jle     short loc_18000A72E
0x18000a725  movzx   ecx, ax
0x18000a728  or      ecx, 80070000h
0x18000a72e  lea     rax, WPP_GLOBAL_Control
0x18000a735  mov     r10, cs:WPP_GLOBAL_Control
0x18000a73c  cmp     r10, rax
0x18000a73f  jz      short loc_18000A765
0x18000a741  test    byte ptr [r10+1Ch], 1
0x18000a746  jz      short loc_18000A765
0x18000a748  mov     edx, 97h
0x18000a74d  mov     [rsp+0F8h+dwCreationDisposition], ecx
0x18000a751  mov     r9, rdi
0x18000a754  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000a75b  mov     rcx, [r10+10h]
0x18000a75f  call    WPP_SF_Sd
0x18000a764  nop
0x18000a765  mov     rcx, [rsp+0F8h+var_B8]
0x18000a76a  test    rcx, rcx
0x18000a76d  jz      short loc_18000A775
0x18000a76f  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAHXZ; SmartPtr<CVolumeTrackingDescriptor>::RefCounter::Dec_nRefs(void)
0x18000a774  nop
0x18000a775  lea     rcx, stru_1800199F0; lpCriticalSection
0x18000a77c  call    cs:__imp_LeaveCriticalSection
0x18000a782  nop
0x18000a783  jmp     loc_18000A9B5
0x18000a788  mov     dword ptr [rsp+0F8h+NotificationFilter], 38h ; '8'
0x18000a793  mov     dword ptr [rsp+0F8h+NotificationFilter+4], 6
0x18000a79e  mov     qword ptr [rsp+0F8h+var_60], rax
0x18000a7a6  mov     r8d, 1; Flags
0x18000a7ac  lea     rdx, [rsp+0F8h+NotificationFilter]; NotificationFilter
0x18000a7b4  mov     rcx, cs:?g_Service@@3VCFhService@@A; hRecipient
0x18000a7bb  call    cs:__imp_RegisterDeviceNotificationW
0x18000a7c1  mov     rcx, [rsp+0F8h+var_B8]
0x18000a7c6  mov     rdx, [rcx]
0x18000a7c9  mov     [rdx+8], rax
0x18000a7cd  mov     rax, [rsp+0F8h+var_B8]
0x18000a7d2  mov     rsi, [rax]
0x18000a7d5  cmp     [rsi+8], r13
0x18000a7d9  jnz     short loc_18000A84D
0x18000a7db  call    cs:__imp_GetLastError
0x18000a7e1  mov     ecx, eax
0x18000a7e3  test    eax, eax
0x18000a7e5  jle     short loc_18000A7F0
0x18000a7e7  movzx   ecx, ax
0x18000a7ea  or      ecx, 80070000h
0x18000a7f0  lea     rax, WPP_GLOBAL_Control
0x18000a7f7  mov     r10, cs:WPP_GLOBAL_Control
0x18000a7fe  cmp     r10, rax
0x18000a801  jz      short loc_18000A82F
0x18000a803  test    byte ptr [r10+1Ch], 1
0x18000a808  jz      short loc_18000A82F
0x18000a80a  mov     rax, [rsp+0F8h+var_B8]
0x18000a80f  mov     r9, [rax]
0x18000a812  mov     edx, 98h
0x18000a817  mov     [rsp+0F8h+dwCreationDisposition], ecx
0x18000a81b  mov     r9, [r9]
0x18000a81e  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000a825  mov     rcx, [r10+10h]
0x18000a829  call    WPP_SF_Sd
0x18000a82e  nop
0x18000a82f  lea     rcx, [rsp+0F8h+var_B8]
0x18000a834  call    ??1?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAA@XZ; SmartPtr<CVolumeTrackingDescriptor>::~SmartPtr<CVolumeTrackingDescriptor>(void)
0x18000a839  nop
0x18000a83a  lea     rcx, stru_1800199F0; lpCriticalSection
0x18000a841  call    cs:__imp_LeaveCriticalSection
  ... truncated ...
```

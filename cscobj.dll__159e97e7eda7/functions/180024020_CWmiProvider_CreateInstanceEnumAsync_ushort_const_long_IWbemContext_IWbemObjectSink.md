# CWmiProvider::CreateInstanceEnumAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x180024020`
- end: `0x1800244b6`
- name: `?CreateInstanceEnumAsync@CWmiProvider@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `1174`
- prototype: `int(CWmiProvider *__hidden this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006c00`
- `0x180009d50`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x18000f658`
- `0x180014068`
- `0x1800176e0`
- `0x180017784`
- `0x180017930`
- `0x180023b18`
- `0x180023bac`
- `0x180024020`
- `0x180025d30`
- `0x180026470`
- `0x18002a198`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180024495`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180024495`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180024103`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180024172`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002420d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002430b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180024103`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180024172`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002420d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002430b`

## string_xrefs

- `0x180024301`: `Win32_OfflineFilesCache`
- `0x180024168`: `Win32_OfflineFilesMachineConfiguration`
- `0x1800240ea`: `Win32_OfflineFilesUserConfiguration`

## pseudocode

```c
__int64 __fastcall CWmiProvider::CreateInstanceEnumAsync(
        struct CWmiAsyncCancelMonitor **this,
        unsigned __int16 *const a2,
        int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  int v9; // eax
  int *v10; // rdx
  struct IWbemObjectSink *v11; // r14
  int v12; // ebx
  int Instance; // eax
  CWmiProvider *v14; // rcx
  CWmiProvider *v15; // rcx
  int v16; // eax
  struct IWbemServices *v18; // [rsp+40h] [rbp-20h] BYREF
  struct IOfflineFilesCache *v19; // [rsp+48h] [rbp-18h] BYREF
  struct IEnumWbemClassObject *v20[2]; // [rsp+50h] [rbp-10h] BYREF
  int v21; // [rsp+90h] [rbp+30h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 48, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids, a2);
  }
  v21 = 0;
  v9 = CWmiProvider::_NeedsImpersonation((CWmiProvider *)(this - 1), a2);
  v11 = a5;
  if ( v9 )
  {
    v12 = CComImpersonator::Impersonate((CComImpersonator *)&v21, v10);
    if ( v12 < 0 )
      goto LABEL_49;
  }
  v18 = 0;
  v12 = CInterfaceInGITBase::_Unmarshal(
          (CInterfaceInGITBase *)(this + 9),
          &GUID_9556dc99_828c_11cf_a37e_00aa003240c7,
          (void **)&v18);
  if ( v12 < 0 )
    goto LABEL_48;
  v19 = 0;
  if ( !a2 || !v11 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_qq(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 49, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids, a2, v11);
    }
    v12 = -2147217400;
    goto LABEL_46;
  }
  if ( CompareStringW(0x7Fu, 1u, L"Win32_OfflineFilesUserConfiguration", -1, a2, -1) == 2 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 50, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids);
    }
    v20[0] = 0;
    Instance = CCscWmiSingletonEnum<COfflineFilesUserConfiguration>::CreateInstance(v18, a4, v20);
  }
  else
  {
    if ( CompareStringW(0x7Fu, 1u, L"Win32_OfflineFilesMachineConfiguration", -1, a2, -1) != 2 )
    {
      if ( CompareStringW(0x7Fu, 1u, L"Win32_OfflineFilesItem", -1, a2, -1) == 2 )
      {
        v14 = (CWmiProvider *)WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 52, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids);
        }
        v12 = CWmiProvider::_CreateCscCacheObject(v14, &v19);
        if ( (((unsigned __int16)v12 - 1058) & 0xFFFFFFFB) != 0 )
        {
          if ( v12 >= 0 )
          {
            v20[0] = 0;
            v12 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, GUID *, struct IEnumWbemClassObject **))v19->lpVtbl->QueryInterface)(
                    v19,
                    &GUID_3836f049_9413_45dd_bf46_b5aaa82dc310,
                    v20);
            if ( v12 >= 0 )
            {
              v12 = CCscWmiItemEnum::RunEnumOnThread(
                      v18,
                      a4,
                      v11,
                      this[22],
                      (struct IOfflineFilesItemContainer *)v20[0],
                      0,
                      0xFFFFFFFF,
                      a3);
              ((void (__fastcall *)(struct IEnumWbemClassObject *))v20[0]->lpVtbl->Release)(v20[0]);
            }
          }
        }
        else
        {
          v12 = -2147217372;
        }
      }
      else if ( CompareStringW(0x7Fu, 1u, L"Win32_OfflineFilesCache", -1, a2, -1) == 2 )
      {
        v15 = (CWmiProvider *)WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 53, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids);
        }
        v16 = CWmiProvider::_CreateCscCacheObject(v15, &v19);
        v12 = v16;
        if ( v16 >= 0 || (((unsigned __int16)v16 - 1058) & 0xFFFFFFFB) == 0 )
          v12 = CCscWmiCacheEnum::RunEnumOnThread(v18, a4, v11, this[22], v19, 0xFFFFFFFF, a3);
      }
      else
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 54, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids);
        }
        v12 = -2147217406;
      }
      goto LABEL_46;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 51, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids);
    }
    v20[0] = 0;
    Instance = CCscWmiSingletonEnum<COfflineFilesMachineConfiguration>::CreateInstance(v18, a4, v20);
  }
  v12 = Instance;
  if ( Instance >= 0 )
    v12 = WmiEnumerateAsyn((a3 & 0x80) != 0, v20[0], v11);
  ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(v20);
LABEL_46:
  if ( v19 )
    ((void (__fastcall *)(struct IOfflineFilesCache *))v19->lpVtbl->Release)(v19);
LABEL_48:
  ((void (__fastcall *)(struct IWbemServices *))v18->lpVtbl->Release)(v18);
  if ( v12 < 0 )
LABEL_49:
    ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))v11->lpVtbl->SetStatus)(
      v11,
      0,
      (unsigned int)v12,
      0,
      0);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      55,
      WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids,
      (unsigned int)v12);
  }
  if ( v21 )
    CoRevertToSelf();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180024020  mov     [rsp-28h+arg_8], rbx
0x180024025  mov     [rsp-28h+arg_10], rsi
0x18002402a  push    rbp
0x18002402b  push    rdi
0x18002402c  push    r12
0x18002402e  push    r14
0x180024030  push    r15
0x180024032  mov     rbp, rsp
0x180024035  sub     rsp, 60h
0x180024039  mov     r12, r9
0x18002403c  mov     esi, r8d
0x18002403f  mov     rdi, rdx
0x180024042  mov     r15, rcx
0x180024045  mov     rcx, cs:WPP_GLOBAL_Control
0x18002404c  lea     rax, WPP_GLOBAL_Control
0x180024053  cmp     rcx, rax
0x180024056  jz      short loc_180024079
0x180024058  test    dword ptr [rcx+1Ch], 4000000h
0x18002405f  jz      short loc_180024079
0x180024061  mov     rcx, [rcx+10h]
0x180024065  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x18002406c  mov     edx, 30h ; '0'
0x180024071  mov     r9, rdi
0x180024074  call    WPP_SF_S
0x180024079  lea     rcx, [r15-8]; this
0x18002407d  mov     [rbp+arg_0], 0
0x180024084  mov     rdx, rdi; unsigned __int16 *
0x180024087  call    ?_NeedsImpersonation@CWmiProvider@@AEAAHQEAG@Z; CWmiProvider::_NeedsImpersonation(ushort * const)
0x18002408c  mov     r14, [rbp+arg_20]
0x180024090  test    eax, eax
0x180024092  jz      short loc_1800240A7
0x180024094  lea     rcx, [rbp+arg_0]; this
0x180024098  call    ?Impersonate@CComImpersonator@@QEAAJPEAH@Z; CComImpersonator::Impersonate(int *)
0x18002409d  mov     ebx, eax
0x18002409f  test    eax, eax
0x1800240a1  js      loc_18002443B
0x1800240a7  lea     rcx, [r15+48h]; this
0x1800240ab  mov     [rbp+var_20], 0
0x1800240b3  lea     r8, [rbp+var_20]; void **
0x1800240b7  lea     rdx, _GUID_9556dc99_828c_11cf_a37e_00aa003240c7; struct _GUID *
0x1800240be  call    ?_Unmarshal@CInterfaceInGITBase@@IEAAJAEBU_GUID@@PEAPEAX@Z; CInterfaceInGITBase::_Unmarshal(_GUID const &,void * *)
0x1800240c3  mov     ebx, eax
0x1800240c5  test    eax, eax
0x1800240c7  js      loc_180024427
0x1800240cd  mov     [rbp+var_18], 0
0x1800240d5  test    rdi, rdi
0x1800240d8  jz      loc_1800243D4
0x1800240de  test    r14, r14
0x1800240e1  jz      loc_1800243D4
0x1800240e7  or      ebx, 0FFFFFFFFh
0x1800240ea  lea     r8, CSCWMI_STR_OFFLINEFILESUSERCONFIGURATION; "Win32_OfflineFilesUserConfiguration"
0x1800240f1  mov     [rsp+60h+cchCount2], ebx; cchCount2
0x1800240f5  mov     r9d, ebx; cchCount1
0x1800240f8  mov     [rsp+60h+lpString2], rdi; lpString2
0x1800240fd  lea     edx, [rbx+2]; dwCmpFlags
0x180024100  lea     ecx, [rdx+7Eh]; Locale
0x180024103  call    cs:__imp_CompareStringW
0x180024109  cmp     eax, 2
0x18002410c  jnz     short loc_180024157
0x18002410e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024115  lea     rax, WPP_GLOBAL_Control
0x18002411c  cmp     rcx, rax
0x18002411f  jz      short loc_18002413D
0x180024121  test    dword ptr [rcx+1Ch], 4000000h
0x180024128  jz      short loc_18002413D
0x18002412a  mov     rcx, [rcx+10h]
0x18002412e  lea     edx, [rbx+33h]
0x180024131  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180024138  call    WPP_SF_
0x18002413d  mov     rcx, [rbp+var_20]
0x180024141  lea     r8, [rbp+var_10]
0x180024145  mov     rdx, r12
0x180024148  mov     [rbp+var_10], 0
0x180024150  call    ?CreateInstance@?$CCscWmiSingletonEnum@VCOfflineFilesUserConfiguration@@@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z; CCscWmiSingletonEnum<COfflineFilesUserConfiguration>::CreateInstance(IWbemServices *,IWbemContext *,IEnumWbemClassObject * *)
0x180024155  jmp     short loc_1800241C6
0x180024157  mov     edx, 1; dwCmpFlags
0x18002415c  mov     [rsp+60h+cchCount2], ebx; cchCount2
0x180024160  mov     r9d, ebx; cchCount1
0x180024163  mov     [rsp+60h+lpString2], rdi; lpString2
0x180024168  lea     r8, CSCWMI_STR__OFFLINEFILESMACHINECONFIGURATION; "Win32_OfflineFilesMachineConfiguration"
0x18002416f  lea     ecx, [rdx+7Eh]; Locale
0x180024172  call    cs:__imp_CompareStringW
0x180024178  cmp     eax, 2
0x18002417b  jnz     short loc_1800241F2
0x18002417d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024184  lea     rax, WPP_GLOBAL_Control
0x18002418b  cmp     rcx, rax
0x18002418e  jz      short loc_1800241AE
0x180024190  test    dword ptr [rcx+1Ch], 4000000h
0x180024197  jz      short loc_1800241AE
0x180024199  mov     rcx, [rcx+10h]
0x18002419d  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x1800241a4  mov     edx, 33h ; '3'
0x1800241a9  call    WPP_SF_
0x1800241ae  mov     rcx, [rbp+var_20]
0x1800241b2  lea     r8, [rbp+var_10]
0x1800241b6  mov     rdx, r12
0x1800241b9  mov     [rbp+var_10], 0
0x1800241c1  call    ?CreateInstance@?$CCscWmiSingletonEnum@VCOfflineFilesMachineConfiguration@@@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z; CCscWmiSingletonEnum<COfflineFilesMachineConfiguration>::CreateInstance(IWbemServices *,IWbemContext *,IEnumWbemClassObject * *)
0x1800241c6  mov     ebx, eax
0x1800241c8  test    eax, eax
0x1800241ca  js      short loc_1800241E4
0x1800241cc  mov     rdx, [rbp+var_10]; struct IEnumWbemClassObject *
0x1800241d0  mov     r8, r14; struct IWbemObjectSink *
0x1800241d3  shr     esi, 7
0x1800241d6  and     sil, 1
0x1800241da  mov     cl, sil; bool
0x1800241dd  call    ?WmiEnumerateAsyn@@YAJ_NPEAUIEnumWbemClassObject@@PEAUIWbemObjectSink@@@Z; WmiEnumerateAsyn(bool,IEnumWbemClassObject *,IWbemObjectSink *)
0x1800241e2  mov     ebx, eax
0x1800241e4  lea     rcx, [rbp+var_10]
0x1800241e8  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x1800241ed  jmp     loc_180024412
0x1800241f2  mov     edx, 1; dwCmpFlags
0x1800241f7  mov     [rsp+60h+cchCount2], ebx; cchCount2
0x1800241fb  mov     r9d, ebx; cchCount1
0x1800241fe  mov     [rsp+60h+lpString2], rdi; lpString2
0x180024203  lea     r8, CSCWMI_STR_OFFLINEFILESITEM; "Win32_OfflineFilesItem"
0x18002420a  lea     ecx, [rdx+7Eh]; Locale
0x18002420d  call    cs:__imp_CompareStringW
0x180024213  cmp     eax, 2
0x180024216  jnz     loc_1800242F0
0x18002421c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024223  lea     rax, WPP_GLOBAL_Control
0x18002422a  cmp     rcx, rax
0x18002422d  jz      short loc_18002424D
0x18002422f  test    dword ptr [rcx+1Ch], 4000000h
0x180024236  jz      short loc_18002424D
0x180024238  mov     rcx, [rcx+10h]
0x18002423c  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180024243  mov     edx, 34h ; '4'
0x180024248  call    WPP_SF_
0x18002424d  lea     rdx, [rbp+var_18]; struct IOfflineFilesCache **
0x180024251  call    ?_CreateCscCacheObject@CWmiProvider@@AEAAJPEAPEAUIOfflineFilesCache@@@Z; CWmiProvider::_CreateCscCacheObject(IOfflineFilesCache * *)
0x180024256  mov     ebx, eax
0x180024258  movzx   eax, ax
0x18002425b  sub     eax, 422h
0x180024260  test    eax, 0FFFFFFFBh
0x180024265  jnz     short loc_180024271
0x180024267  mov     ebx, 80041024h
0x18002426c  jmp     loc_180024412
0x180024271  test    ebx, ebx
0x180024273  js      loc_180024412
0x180024279  mov     rcx, [rbp+var_18]
0x18002427d  lea     r8, [rbp+var_10]
0x180024281  mov     [rbp+var_10], 0
0x180024289  lea     rdx, _GUID_3836f049_9413_45dd_bf46_b5aaa82dc310
0x180024290  mov     rax, [rcx]
0x180024293  mov     rax, [rax]
0x180024296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002429b  mov     ebx, eax
0x18002429d  test    eax, eax
0x18002429f  js      loc_180024412
0x1800242a5  mov     rax, [rbp+var_10]
0x1800242a9  mov     r8, r14; struct IWbemObjectSink *
0x1800242ac  mov     r9, [r15+0B0h]; struct CWmiAsyncCancelMonitor *
0x1800242b3  mov     rdx, r12; struct IWbemContext *
0x1800242b6  mov     rcx, [rbp+var_20]; struct IWbemServices *
0x1800242ba  mov     [rsp+60h+var_28], esi; int
0x1800242be  mov     [rsp+60h+var_30], 0FFFFFFFFh; unsigned int
0x1800242c6  mov     qword ptr [rsp+60h+cchCount2], 0; struct IOfflineFilesItem *
0x1800242cf  mov     [rsp+60h+lpString2], rax; struct IOfflineFilesItemContainer *
0x1800242d4  call    ?RunEnumOnThread@CCscWmiItemEnum@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAVCWmiAsyncCancelMonitor@@PEAUIOfflineFilesItemContainer@@PEAUIOfflineFilesItem@@KJ@Z; CCscWmiItemEnum::RunEnumOnThread(IWbemServices *,IWbemContext *,IWbemObjectSink *,CWmiAsyncCancelMonitor *,IOfflineFilesItemContainer *,IOfflineFilesItem *,ulong,long)
0x1800242d9  mov     rcx, [rbp+var_10]
0x1800242dd  mov     ebx, eax
0x1800242df  mov     rax, [rcx]
0x1800242e2  mov     rax, [rax+10h]
0x1800242e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242eb  jmp     loc_180024412
0x1800242f0  mov     edx, 1; dwCmpFlags
0x1800242f5  mov     [rsp+60h+cchCount2], ebx; cchCount2
0x1800242f9  mov     r9d, ebx; cchCount1
0x1800242fc  mov     [rsp+60h+lpString2], rdi; lpString2
0x180024301  lea     r8, CSCWMI_STR_OFFLINEFILESCACHE; "Win32_OfflineFilesCache"
0x180024308  lea     ecx, [rdx+7Eh]; Locale
0x18002430b  call    cs:__imp_CompareStringW
0x180024311  cmp     eax, 2
0x180024314  jnz     loc_18002439C
0x18002431a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024321  lea     rax, WPP_GLOBAL_Control
0x180024328  cmp     rcx, rax
0x18002432b  jz      short loc_18002434B
0x18002432d  test    dword ptr [rcx+1Ch], 4000000h
0x180024334  jz      short loc_18002434B
0x180024336  mov     rcx, [rcx+10h]
0x18002433a  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180024341  mov     edx, 35h ; '5'
0x180024346  call    WPP_SF_
0x18002434b  lea     rdx, [rbp+var_18]; struct IOfflineFilesCache **
0x18002434f  call    ?_CreateCscCacheObject@CWmiProvider@@AEAAJPEAPEAUIOfflineFilesCache@@@Z; CWmiProvider::_CreateCscCacheObject(IOfflineFilesCache * *)
0x180024354  mov     ebx, eax
0x180024356  test    eax, eax
0x180024358  jns     short loc_18002436D
0x18002435a  movzx   eax, ax
0x18002435d  sub     eax, 422h
0x180024362  test    eax, 0FFFFFFFBh
0x180024367  jnz     loc_180024412
0x18002436d  mov     rax, [rbp+var_18]
0x180024371  mov     r8, r14; struct IWbemObjectSink *
0x180024374  mov     r9, [r15+0B0h]; struct CWmiAsyncCancelMonitor *
0x18002437b  mov     rdx, r12; struct IWbemContext *
0x18002437e  mov     rcx, [rbp+var_20]; struct IWbemServices *
0x180024382  mov     [rsp+60h+var_30], esi; int
0x180024386  mov     [rsp+60h+cchCount2], 0FFFFFFFFh; unsigned int
0x18002438e  mov     [rsp+60h+lpString2], rax; struct IOfflineFilesCache *
0x180024393  call    ?RunEnumOnThread@CCscWmiCacheEnum@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAVCWmiAsyncCancelMonitor@@PEAUIOfflineFilesCache@@KJ@Z; CCscWmiCacheEnum::RunEnumOnThread(IWbemServices *,IWbemContext *,IWbemObjectSink *,CWmiAsyncCancelMonitor *,IOfflineFilesCache *,ulong,long)
0x180024398  mov     ebx, eax
0x18002439a  jmp     short loc_180024412
0x18002439c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243a3  lea     rax, WPP_GLOBAL_Control
0x1800243aa  cmp     rcx, rax
0x1800243ad  jz      short loc_1800243CD
0x1800243af  test    dword ptr [rcx+1Ch], 4000000h
0x1800243b6  jz      short loc_1800243CD
0x1800243b8  mov     rcx, [rcx+10h]
0x1800243bc  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x1800243c3  mov     edx, 36h ; '6'
0x1800243c8  call    WPP_SF_
0x1800243cd  mov     ebx, 80041002h
0x1800243d2  jmp     short loc_180024412
0x1800243d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243db  lea     rax, WPP_GLOBAL_Control
0x1800243e2  cmp     rcx, rax
0x1800243e5  jz      short loc_18002440D
0x1800243e7  test    dword ptr [rcx+1Ch], 4000000h
0x1800243ee  jz      short loc_18002440D
0x1800243f0  mov     rcx, [rcx+10h]
0x1800243f4  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x1800243fb  mov     edx, 31h ; '1'
0x180024400  mov     [rsp+60h+lpString2], r14
0x180024405  mov     r9, rdi
0x180024408  call    WPP_SF_qq
0x18002440d  mov     ebx, 80041008h
0x180024412  mov     rcx, [rbp+var_18]
0x180024416  test    rcx, rcx
0x180024419  jz      short loc_180024427
0x18002441b  mov     rax, [rcx]
0x18002441e  mov     rax, [rax+10h]
0x180024422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024427  mov     rcx, [rbp+var_20]
0x18002442b  mov     rax, [rcx]
0x18002442e  mov     rax, [rax+10h]
0x180024432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024437  test    ebx, ebx
0x180024439  jns     short loc_18002445B
0x18002443b  mov     rax, [r14]
0x18002443e  xor     r9d, r9d
0x180024441  mov     r8d, ebx
0x180024444  mov     [rsp+60h+lpString2], 0
0x18002444d  xor     edx, edx
0x18002444f  mov     rcx, r14
0x180024452  mov     rax, [rax+20h]
0x180024456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002445b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024462  lea     rax, WPP_GLOBAL_Control
0x180024469  cmp     rcx, rax
0x18002446c  jz      short loc_18002448F
0x18002446e  test    dword ptr [rcx+1Ch], 4000000h
0x180024475  jz      short loc_18002448F
0x180024477  mov     rcx, [rcx+10h]
0x18002447b  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180024482  mov     edx, 37h ; '7'
0x180024487  mov     r9d, ebx
0x18002448a  call    WPP_SF_d
0x18002448f  cmp     [rbp+arg_0], 0
0x180024493  jz      short loc_18002449B
0x180024495  call    cs:__imp_CoRevertToSelf
0x18002449b  lea     r11, [rsp+60h+var_s0]
0x1800244a0  mov     eax, ebx
0x1800244a2  mov     rbx, [r11+38h]
0x1800244a6  mov     rsi, [r11+40h]
0x1800244aa  mov     rsp, r11
0x1800244ad  pop     r15
0x1800244af  pop     r14
0x1800244b1  pop     r12
0x1800244b3  pop     rdi
0x1800244b4  pop     rbp
0x1800244b5  retn
```

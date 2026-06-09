# CWmiProvider::CreateInstanceEnum(ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x180023c40`
- end: `0x180024014`
- name: `?CreateInstanceEnum@CWmiProvider@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `980`
- prototype: `int(CWmiProvider *__hidden this, unsigned __int16 *const, int, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006c00`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x180014068`
- `0x180016edc`
- `0x18001702c`
- `0x180023b18`
- `0x180023bac`
- `0x180023c40`
- `0x180025d30`
- `0x180026470`
- `0x18002a198`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180023ff3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180023ff3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023d4d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023d85`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023dc9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023ecf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023d4d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023d85`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023dc9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023ecf`

## string_xrefs

- `0x180023ec5`: `Win32_OfflineFilesCache`
- `0x180023d7b`: `Win32_OfflineFilesMachineConfiguration`
- `0x180023d34`: `Win32_OfflineFilesUserConfiguration`

## pseudocode

```c
__int64 __fastcall CWmiProvider::CreateInstanceEnum(
        struct CWmiAsyncCancelMonitor **this,
        unsigned __int16 *const a2,
        int a3,
        struct IWbemContext *a4,
        struct IEnumWbemClassObject **a5)
{
  int *v9; // rdx
  int CscCacheObject; // ebx
  int Instance; // eax
  CWmiProvider *v12; // rcx
  CWmiProvider *v13; // rcx
  int v14; // eax
  struct IWbemServices *v16; // [rsp+50h] [rbp-20h] BYREF
  struct IOfflineFilesCache *v17; // [rsp+58h] [rbp-18h] BYREF
  struct IOfflineFilesItemContainer *v18; // [rsp+60h] [rbp-10h] BYREF
  int v19; // [rsp+A0h] [rbp+30h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 42, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids, a2);
  }
  v19 = 0;
  if ( !(unsigned int)CWmiProvider::_NeedsImpersonation((CWmiProvider *)(this - 1), a2)
    || (CscCacheObject = CComImpersonator::Impersonate((CComImpersonator *)&v19, v9), CscCacheObject >= 0) )
  {
    v16 = 0;
    CscCacheObject = CInterfaceInGITBase::_Unmarshal(
                       (CInterfaceInGITBase *)(this + 9),
                       &GUID_9556dc99_828c_11cf_a37e_00aa003240c7,
                       (void **)&v16);
    if ( CscCacheObject < 0 )
    {
LABEL_39:
      ((void (__fastcall *)(struct IWbemServices *))v16->lpVtbl->Release)(v16);
      goto LABEL_40;
    }
    v17 = 0;
    if ( a2 )
    {
      if ( CompareStringW(0x7Fu, 1u, L"Win32_OfflineFilesUserConfiguration", -1, a2, -1) == 2 )
      {
        Instance = CCscWmiSingletonEnum<COfflineFilesUserConfiguration>::CreateInstance(v16, a4, a5);
      }
      else
      {
        if ( CompareStringW(0x7Fu, 1u, L"Win32_OfflineFilesMachineConfiguration", -1, a2, -1) != 2 )
        {
          if ( CompareStringW(0x7Fu, 1u, L"Win32_OfflineFilesItem", -1, a2, -1) == 2 )
          {
            v12 = (CWmiProvider *)WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
            {
              WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 44, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids);
            }
            CscCacheObject = CWmiProvider::_CreateCscCacheObject(v12, (LPVOID *)&v17);
            if ( (((unsigned __int16)CscCacheObject - 1058) & 0xFFFFFFFB) != 0 )
            {
              if ( CscCacheObject >= 0 )
              {
                v18 = 0;
                CscCacheObject = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, GUID *, struct IOfflineFilesItemContainer **))v17->lpVtbl->QueryInterface)(
                                   v17,
                                   &GUID_3836f049_9413_45dd_bf46_b5aaa82dc310,
                                   &v18);
                if ( CscCacheObject >= 0 )
                {
                  CscCacheObject = CCscWmiItemEnum::CreateInstance(
                                     v16,
                                     a4,
                                     v18,
                                     0,
                                     this[22],
                                     a3,
                                     1,
                                     &GUID_027947e1_d731_11ce_a357_000000000001,
                                     (void **)a5);
                  ((void (__fastcall *)(struct IOfflineFilesItemContainer *))v18->lpVtbl->Release)(v18);
                }
              }
            }
            else
            {
              CscCacheObject = -2147217372;
            }
          }
          else if ( CompareStringW(0x7Fu, 1u, L"Win32_OfflineFilesCache", -1, a2, -1) == 2 )
          {
            v13 = (CWmiProvider *)WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
            {
              WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 45, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids);
            }
            v14 = CWmiProvider::_CreateCscCacheObject(v13, (LPVOID *)&v17);
            CscCacheObject = v14;
            if ( v14 >= 0 || (((unsigned __int16)v14 - 1058) & 0xFFFFFFFB) == 0 )
              CscCacheObject = CCscWmiCacheEnum::CreateInstance(
                                 v16,
                                 a4,
                                 this[22],
                                 v17,
                                 a3,
                                 &GUID_027947e1_d731_11ce_a357_000000000001,
                                 (void **)a5);
          }
          else
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
            {
              WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 46, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids);
            }
            CscCacheObject = -2147217406;
          }
          goto LABEL_37;
        }
        Instance = CCscWmiSingletonEnum<COfflineFilesMachineConfiguration>::CreateInstance(v16, a4, a5);
      }
      CscCacheObject = Instance;
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 43, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids);
      }
      CscCacheObject = -2147217400;
    }
LABEL_37:
    if ( v17 )
      ((void (__fastcall *)(struct IOfflineFilesCache *))v17->lpVtbl->Release)(v17);
    goto LABEL_39;
  }
LABEL_40:
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      47,
      WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids,
      (unsigned int)CscCacheObject);
  }
  if ( v19 )
    CoRevertToSelf();
  return (unsigned int)CscCacheObject;
}

```

## disassembly

```asm
0x180023c40  mov     [rsp-28h+arg_8], rbx
0x180023c45  mov     [rsp-28h+arg_10], rsi
0x180023c4a  push    rbp
0x180023c4b  push    rdi
0x180023c4c  push    r13
0x180023c4e  push    r14
0x180023c50  push    r15
0x180023c52  mov     rbp, rsp
0x180023c55  sub     rsp, 70h
0x180023c59  mov     rsi, r9
0x180023c5c  mov     r15d, r8d
0x180023c5f  mov     rdi, rdx
0x180023c62  mov     r14, rcx
0x180023c65  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c6c  lea     rax, WPP_GLOBAL_Control
0x180023c73  mov     r13d, 4000000h
0x180023c79  cmp     rcx, rax
0x180023c7c  jz      short loc_180023C9C
0x180023c7e  test    [rcx+1Ch], r13d
0x180023c82  jz      short loc_180023C9C
0x180023c84  mov     rcx, [rcx+10h]
0x180023c88  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180023c8f  mov     edx, 2Ah ; '*'
0x180023c94  mov     r9, rdi
0x180023c97  call    WPP_SF_S
0x180023c9c  lea     rcx, [r14-8]; this
0x180023ca0  mov     [rbp+arg_0], 0
0x180023ca7  mov     rdx, rdi; unsigned __int16 *
0x180023caa  call    ?_NeedsImpersonation@CWmiProvider@@AEAAHQEAG@Z; CWmiProvider::_NeedsImpersonation(ushort * const)
0x180023caf  test    eax, eax
0x180023cb1  jz      short loc_180023CC6
0x180023cb3  lea     rcx, [rbp+arg_0]; this
0x180023cb7  call    ?Impersonate@CComImpersonator@@QEAAJPEAH@Z; CComImpersonator::Impersonate(int *)
0x180023cbc  mov     ebx, eax
0x180023cbe  test    eax, eax
0x180023cc0  js      loc_180023FBC
0x180023cc6  lea     rcx, [r14+48h]; this
0x180023cca  mov     [rbp+var_20], 0
0x180023cd2  lea     r8, [rbp+var_20]; void **
0x180023cd6  lea     rdx, _GUID_9556dc99_828c_11cf_a37e_00aa003240c7; struct _GUID *
0x180023cdd  call    ?_Unmarshal@CInterfaceInGITBase@@IEAAJAEBU_GUID@@PEAPEAX@Z; CInterfaceInGITBase::_Unmarshal(_GUID const &,void * *)
0x180023ce2  mov     ebx, eax
0x180023ce4  test    eax, eax
0x180023ce6  js      loc_180023FA3
0x180023cec  mov     [rbp+var_18], 0
0x180023cf4  test    rdi, rdi
0x180023cf7  jnz     short loc_180023D31
0x180023cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d00  lea     rdi, WPP_GLOBAL_Control
0x180023d07  cmp     rcx, rdi
0x180023d0a  jz      short loc_180023D27
0x180023d0c  test    [rcx+1Ch], r13d
0x180023d10  jz      short loc_180023D27
0x180023d12  mov     rcx, [rcx+10h]
0x180023d16  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180023d1d  mov     edx, 2Bh ; '+'
0x180023d22  call    WPP_SF_
0x180023d27  mov     ebx, 80041008h
0x180023d2c  jmp     loc_180023F8C
0x180023d31  or      ebx, 0FFFFFFFFh
0x180023d34  lea     r8, CSCWMI_STR_OFFLINEFILESUSERCONFIGURATION; "Win32_OfflineFilesUserConfiguration"
0x180023d3b  mov     [rsp+70h+cchCount2], ebx; cchCount2
0x180023d3f  mov     r9d, ebx; cchCount1
0x180023d42  mov     [rsp+70h+lpString2], rdi; lpString2
0x180023d47  lea     edx, [rbx+2]; dwCmpFlags
0x180023d4a  lea     ecx, [rdx+7Eh]; Locale
0x180023d4d  call    cs:__imp_CompareStringW
0x180023d53  cmp     eax, 2
0x180023d56  jnz     short loc_180023D6A
0x180023d58  mov     r8, [rbp+arg_20]
0x180023d5c  mov     rdx, rsi
0x180023d5f  mov     rcx, [rbp+var_20]
0x180023d63  call    ?CreateInstance@?$CCscWmiSingletonEnum@VCOfflineFilesUserConfiguration@@@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z; CCscWmiSingletonEnum<COfflineFilesUserConfiguration>::CreateInstance(IWbemServices *,IWbemContext *,IEnumWbemClassObject * *)
0x180023d68  jmp     short loc_180023DA0
0x180023d6a  mov     edx, 1; dwCmpFlags
0x180023d6f  mov     [rsp+70h+cchCount2], ebx; cchCount2
0x180023d73  mov     r9d, ebx; cchCount1
0x180023d76  mov     [rsp+70h+lpString2], rdi; lpString2
0x180023d7b  lea     r8, CSCWMI_STR__OFFLINEFILESMACHINECONFIGURATION; "Win32_OfflineFilesMachineConfiguration"
0x180023d82  lea     ecx, [rdx+7Eh]; Locale
0x180023d85  call    cs:__imp_CompareStringW
0x180023d8b  cmp     eax, 2
0x180023d8e  jnz     short loc_180023DAE
0x180023d90  mov     r8, [rbp+arg_20]
0x180023d94  mov     rdx, rsi
0x180023d97  mov     rcx, [rbp+var_20]
0x180023d9b  call    ?CreateInstance@?$CCscWmiSingletonEnum@VCOfflineFilesMachineConfiguration@@@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z; CCscWmiSingletonEnum<COfflineFilesMachineConfiguration>::CreateInstance(IWbemServices *,IWbemContext *,IEnumWbemClassObject * *)
0x180023da0  mov     ebx, eax
0x180023da2  lea     rdi, WPP_GLOBAL_Control
0x180023da9  jmp     loc_180023F8C
0x180023dae  mov     edx, 1; dwCmpFlags
0x180023db3  mov     [rsp+70h+cchCount2], ebx; cchCount2
0x180023db7  mov     r9d, ebx; cchCount1
0x180023dba  mov     [rsp+70h+lpString2], rdi; lpString2
0x180023dbf  lea     r8, CSCWMI_STR_OFFLINEFILESITEM; "Win32_OfflineFilesItem"
0x180023dc6  lea     ecx, [rdx+7Eh]; Locale
0x180023dc9  call    cs:__imp_CompareStringW
0x180023dcf  cmp     eax, 2
0x180023dd2  jnz     loc_180023EB4
0x180023dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ddf  lea     rdi, WPP_GLOBAL_Control
0x180023de6  cmp     rcx, rdi
0x180023de9  jz      short loc_180023E04
0x180023deb  test    [rcx+1Ch], r13d
0x180023def  jz      short loc_180023E04
0x180023df1  mov     rcx, [rcx+10h]
0x180023df5  lea     edx, [rax+2Ah]
0x180023df8  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180023dff  call    WPP_SF_
0x180023e04  lea     rdx, [rbp+var_18]; struct IOfflineFilesCache **
0x180023e08  call    ?_CreateCscCacheObject@CWmiProvider@@AEAAJPEAPEAUIOfflineFilesCache@@@Z; CWmiProvider::_CreateCscCacheObject(IOfflineFilesCache * *)
0x180023e0d  mov     ebx, eax
0x180023e0f  movzx   eax, ax
0x180023e12  sub     eax, 422h
0x180023e17  test    eax, 0FFFFFFFBh
0x180023e1c  jnz     short loc_180023E28
0x180023e1e  mov     ebx, 80041024h
0x180023e23  jmp     loc_180023F8C
0x180023e28  test    ebx, ebx
0x180023e2a  js      loc_180023F8C
0x180023e30  mov     rcx, [rbp+var_18]
0x180023e34  lea     r8, [rbp+var_10]
0x180023e38  mov     [rbp+var_10], 0
0x180023e40  lea     rdx, _GUID_3836f049_9413_45dd_bf46_b5aaa82dc310
0x180023e47  mov     rax, [rcx]
0x180023e4a  mov     rax, [rax]
0x180023e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e52  mov     ebx, eax
0x180023e54  test    eax, eax
0x180023e56  js      loc_180023F8C
0x180023e5c  mov     rax, [rbp+arg_20]
0x180023e60  xor     r9d, r9d; struct IOfflineFilesItem *
0x180023e63  mov     r8, [rbp+var_10]; struct IOfflineFilesItemContainer *
0x180023e67  mov     rdx, rsi; struct IWbemContext *
0x180023e6a  mov     rcx, [rbp+var_20]; struct IWbemServices *
0x180023e6e  mov     [rsp+70h+var_30], rax; void **
0x180023e73  lea     rax, _GUID_027947e1_d731_11ce_a357_000000000001
0x180023e7a  mov     [rsp+70h+var_38], rax; struct _GUID *
0x180023e7f  mov     rax, [r14+0B0h]
0x180023e86  mov     dword ptr [rsp+70h+var_40], 1; int
0x180023e8e  mov     [rsp+70h+cchCount2], r15d; int
0x180023e93  mov     [rsp+70h+lpString2], rax; struct CWmiAsyncCancelMonitor *
0x180023e98  call    ?CreateInstance@CCscWmiItemEnum@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIOfflineFilesItemContainer@@PEAUIOfflineFilesItem@@PEAVCWmiAsyncCancelMonitor@@JHAEBU_GUID@@PEAPEAX@Z; CCscWmiItemEnum::CreateInstance(IWbemServices *,IWbemContext *,IOfflineFilesItemContainer *,IOfflineFilesItem *,CWmiAsyncCancelMonitor *,long,int,_GUID const &,void * *)
0x180023e9d  mov     rcx, [rbp+var_10]
0x180023ea1  mov     ebx, eax
0x180023ea3  mov     rax, [rcx]
0x180023ea6  mov     rax, [rax+10h]
0x180023eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eaf  jmp     loc_180023F8C
0x180023eb4  mov     edx, 1; dwCmpFlags
0x180023eb9  mov     [rsp+70h+cchCount2], ebx; cchCount2
0x180023ebd  mov     r9d, ebx; cchCount1
0x180023ec0  mov     [rsp+70h+lpString2], rdi; lpString2
0x180023ec5  lea     r8, CSCWMI_STR_OFFLINEFILESCACHE; "Win32_OfflineFilesCache"
0x180023ecc  lea     ecx, [rdx+7Eh]; Locale
0x180023ecf  call    cs:__imp_CompareStringW
0x180023ed5  cmp     eax, 2
0x180023ed8  jnz     short loc_180023F59
0x180023eda  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ee1  lea     rdi, WPP_GLOBAL_Control
0x180023ee8  cmp     rcx, rdi
0x180023eeb  jz      short loc_180023F06
0x180023eed  test    [rcx+1Ch], r13d
0x180023ef1  jz      short loc_180023F06
0x180023ef3  mov     rcx, [rcx+10h]
0x180023ef7  lea     edx, [rax+2Bh]
0x180023efa  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180023f01  call    WPP_SF_
0x180023f06  lea     rdx, [rbp+var_18]; struct IOfflineFilesCache **
0x180023f0a  call    ?_CreateCscCacheObject@CWmiProvider@@AEAAJPEAPEAUIOfflineFilesCache@@@Z; CWmiProvider::_CreateCscCacheObject(IOfflineFilesCache * *)
0x180023f0f  mov     ebx, eax
0x180023f11  test    eax, eax
0x180023f13  jns     short loc_180023F24
0x180023f15  movzx   eax, ax
0x180023f18  sub     eax, 422h
0x180023f1d  test    eax, 0FFFFFFFBh
0x180023f22  jnz     short loc_180023F8C
0x180023f24  mov     rax, [rbp+arg_20]
0x180023f28  mov     rdx, rsi; struct IWbemContext *
0x180023f2b  mov     r9, [rbp+var_18]; struct IOfflineFilesCache *
0x180023f2f  mov     r8, [r14+0B0h]; struct CWmiAsyncCancelMonitor *
0x180023f36  mov     rcx, [rbp+var_20]; struct IWbemServices *
0x180023f3a  mov     [rsp+70h+var_40], rax; void **
0x180023f3f  lea     rax, _GUID_027947e1_d731_11ce_a357_000000000001
0x180023f46  mov     qword ptr [rsp+70h+cchCount2], rax; struct _GUID *
0x180023f4b  mov     dword ptr [rsp+70h+lpString2], r15d; int
0x180023f50  call    ?CreateInstance@CCscWmiCacheEnum@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAVCWmiAsyncCancelMonitor@@PEAUIOfflineFilesCache@@JAEBU_GUID@@PEAPEAX@Z; CCscWmiCacheEnum::CreateInstance(IWbemServices *,IWbemContext *,CWmiAsyncCancelMonitor *,IOfflineFilesCache *,long,_GUID const &,void * *)
0x180023f55  mov     ebx, eax
0x180023f57  jmp     short loc_180023F8C
0x180023f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f60  lea     rdi, WPP_GLOBAL_Control
0x180023f67  cmp     rcx, rdi
0x180023f6a  jz      short loc_180023F87
0x180023f6c  test    [rcx+1Ch], r13d
0x180023f70  jz      short loc_180023F87
0x180023f72  mov     rcx, [rcx+10h]
0x180023f76  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180023f7d  mov     edx, 2Eh ; '.'
0x180023f82  call    WPP_SF_
0x180023f87  mov     ebx, 80041002h
0x180023f8c  mov     rcx, [rbp+var_18]
0x180023f90  test    rcx, rcx
0x180023f93  jz      short loc_180023FAA
0x180023f95  mov     rax, [rcx]
0x180023f98  mov     rax, [rax+10h]
0x180023f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fa1  jmp     short loc_180023FAA
0x180023fa3  lea     rdi, WPP_GLOBAL_Control
0x180023faa  mov     rcx, [rbp+var_20]
0x180023fae  mov     rax, [rcx]
0x180023fb1  mov     rax, [rax+10h]
0x180023fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fba  jmp     short loc_180023FC3
0x180023fbc  lea     rdi, WPP_GLOBAL_Control
0x180023fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fca  cmp     rcx, rdi
0x180023fcd  jz      short loc_180023FED
0x180023fcf  test    [rcx+1Ch], r13d
0x180023fd3  jz      short loc_180023FED
0x180023fd5  mov     rcx, [rcx+10h]
0x180023fd9  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180023fe0  mov     edx, 2Fh ; '/'
0x180023fe5  mov     r9d, ebx
0x180023fe8  call    WPP_SF_d
0x180023fed  cmp     [rbp+arg_0], 0
0x180023ff1  jz      short loc_180023FF9
0x180023ff3  call    cs:__imp_CoRevertToSelf
0x180023ff9  lea     r11, [rsp+70h+var_s0]
0x180023ffe  mov     eax, ebx
0x180024000  mov     rbx, [r11+38h]
0x180024004  mov     rsi, [r11+40h]
0x180024008  mov     rsp, r11
0x18002400b  pop     r15
0x18002400d  pop     r14
0x18002400f  pop     r13
0x180024011  pop     rdi
0x180024012  pop     rbp
0x180024013  retn
```

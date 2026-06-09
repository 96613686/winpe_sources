# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1000cd70`
- end: `0x1000d075`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YGXIIIPBD@Z`
- size: `773`
- prototype: `void(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task`

## callees

- `0x1000a900`
- `0x1000c730`
- `0x1000ca40`
- `0x1000cad0`
- `0x1000cd70`
- `0x1000e3a0`
- `0x1000e520`
- `0x1000e710`
- `0x1000e740`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f10c`
- `0x1005f180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1000ce68`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1000ce98`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1000ce68`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1000ce98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000ce29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000cfb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d03c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000ce29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000cfb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d03c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d003`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d05b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d003`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d05b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000cf1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000cf1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000cf0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000cf0e`

## string_xrefs

- `0x1000cf09`: `ntdll.dll`

## pseudocode

```c
void __userpurge wil::details::WilApiImpl_RecordFeatureUsage(
        wil::details *this,
        signed int a2,
        unsigned int a3,
        unsigned int a4,
        const char *a5)
{
  unsigned int v5; // esi
  _DWORD *v6; // edx
  FARPROC RtlNotifyFeatureUsage; // esi
  HMODULE ModuleHandleW; // eax
  PSRWLOCK v9; // edi
  int v10; // ecx
  char Ptr; // bl
  __int64 v12; // [esp+10h] [ebp-20h]
  wil::details *v13; // [esp+1Ch] [ebp-14h] BYREF
  int v14; // [esp+20h] [ebp-10h]
  int v15; // [esp+2Ch] [ebp-4h]

  v5 = a2 & 0x7FFFFFFF;
  if ( !this && !a3 && !v5 )
  {
    wil::details::FeatureStateManager::FlushUsage((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager);
    return;
  }
  if ( (a2 & 0x40000000) == 0 )
  {
    if ( !a3 && v5 != 254 )
    {
      v13 = this;
      v14 = (unsigned __int16)a2;
      if ( a2 < 0 )
        HIWORD(v14) |= 1u;
      RtlNotifyFeatureUsage = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
      if ( g_wil_details_pfnRtlNotifyFeatureUsage )
        goto LABEL_27;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      RtlNotifyFeatureUsage = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (int)RtlNotifyFeatureUsage;
      if ( RtlNotifyFeatureUsage )
LABEL_27:
        ((void (__thiscall *)(FARPROC, wil::details **))RtlNotifyFeatureUsage)(RtlNotifyFeatureUsage, &v13);
      return;
    }
    v15 = 1;
    if ( !wil::details::g_featureStateManager
      || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
    {
      return;
    }
    v9 = SRWLock;
    if ( v5 == 254 )
    {
      wil::details_abi::FeatureStateData::RecordUsage(SRWLock);
    }
    else
    {
      if ( v5 >= 0xC8 && (v5 < 0x100 || v5 >= 0x200) )
        return;
      AcquireSRWLockExclusive(SRWLock);
      if ( v5 == 2 || v5 == 3 || v5 == 6 || v5 == 7 || v5 >= 0x100 && v5 < 0x180 )
      {
        wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
          a2,
          (char)this,
          v10);
        Ptr = (char)v9[9].Ptr;
      }
      else
      {
        Ptr = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
                a2,
                (char)this,
                a3);
      }
      if ( v9 )
        ReleaseSRWLockExclusive(v9);
      if ( !Ptr )
        return;
    }
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress
       || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(wil::details::g_pfnDllShutdownInProgress)) )
    {
      AcquireSRWLockExclusive(&stru_10066160);
      wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(
        (struct _TP_TIMER **)&dword_10066168,
        byte_10066171,
        &wil::details::g_featureStateManager);
      ReleaseSRWLockExclusive(&stru_10066160);
    }
    return;
  }
  v15 = 0;
  if ( wil::details::g_featureStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress
     || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(wil::details::g_pfnDllShutdownInProgress)) )
  {
    AcquireSRWLockExclusive(&stru_10066164);
    LODWORD(v12) = this;
    HIDWORD(v12) = (unsigned __int16)a2;
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)((char *)&xmmword_100661C0 + 12), 0xCu) )
    {
LABEL_18:
      wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(
        (struct _TP_TIMER **)&dword_1006616C,
        &byte_10066170,
        &wil::details::g_featureStateManager);
      ReleaseSRWLockExclusive(&stru_10066164);
      return;
    }
    v6 = dword_100661D0;
    if ( dword_100661D0 )
    {
      if ( ((dword_100661D4 - (_DWORD)dword_100661D0) & (unsigned int)-((unsigned int)dword_100661D0 < dword_100661D4)) >= 0xC )
      {
        *(_QWORD *)dword_100661D0 = v12;
        v6[2] = a3;
LABEL_17:
        dword_100661D0 = (char *)dword_100661D0 + 12;
        goto LABEL_18;
      }
      memset(
        dword_100661D0,
        0,
        (unsigned int)dword_100661D0 < dword_100661D4 ? dword_100661D4 - (_DWORD)dword_100661D0 : 0);
      *__errno() = 34;
    }
    else
    {
      *__errno() = 22;
    }
    _invalid_parameter_noinfo();
    goto LABEL_17;
  }
}

```

## disassembly

```asm
0x1000cd70  mov     edi, edi
0x1000cd72  push    ebp
0x1000cd73  mov     ebp, esp
0x1000cd75  push    0FFFFFFFFh
0x1000cd77  push    offset ?WilApiImpl_RecordFeatureUsage@details@wil@@YGXIIIPBD@Z_SEH
0x1000cd7c  mov     eax, large fs:0
0x1000cd82  push    eax
0x1000cd83  sub     esp, 14h
0x1000cd86  push    ebx
0x1000cd87  push    esi
0x1000cd88  push    edi; unsigned int
0x1000cd89  mov     eax, ___security_cookie
0x1000cd8e  xor     eax, ebp
0x1000cd90  push    eax; void *
0x1000cd91  lea     eax, [ebp+var_C]
0x1000cd94  mov     large fs:0, eax
0x1000cd9a  mov     ecx, [ebp+arg_4]
0x1000cd9d  mov     esi, ecx
0x1000cd9f  mov     ebx, [ebp+this]
0x1000cda2  and     esi, 7FFFFFFFh
0x1000cda8  mov     eax, [ebp+arg_8]
0x1000cdab  test    ebx, ebx
0x1000cdad  jnz     short loc_1000CDD5
0x1000cdaf  test    eax, eax
0x1000cdb1  jnz     short loc_1000CDD5
0x1000cdb3  test    esi, esi
0x1000cdb5  jnz     short loc_1000CDD5
0x1000cdb7  mov     ecx, offset ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1000cdbc  call    ?FlushUsage@FeatureStateManager@details@wil@@QAEXXZ; wil::details::FeatureStateManager::FlushUsage(void)
0x1000cdc1  mov     ecx, [ebp+var_C]
0x1000cdc4  mov     large fs:0, ecx
0x1000cdcb  pop     ecx
0x1000cdcc  pop     edi
0x1000cdcd  pop     esi
0x1000cdce  pop     ebx
0x1000cdcf  mov     esp, ebp
0x1000cdd1  pop     ebp
0x1000cdd2  retn    10h
0x1000cdd5  test    esi, 40000000h
0x1000cddb  jz      loc_1000CECE
0x1000cde1  and     esi, 0BFFFFFFFh
0x1000cde7  mov     [ebp+var_4], 0
0x1000cdee  cmp     ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1000cdf5  jz      loc_1000D061
0x1000cdfb  cmp     ?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1000ce02  jnz     loc_1000D061
0x1000ce08  mov     edi, ?g_pfnDllShutdownInProgress@details@wil@@3P6GEX_EA
0x1000ce0e  test    edi, edi
0x1000ce10  jz      short loc_1000CE24
0x1000ce12  mov     ecx, edi
0x1000ce14  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000ce1a  call    edi ; ?g_pfnDllShutdownInProgress@details@wil@@3P6GEX_EA
0x1000ce1c  test    al, al
0x1000ce1e  jnz     loc_1000D061
0x1000ce24  push    offset stru_10066164; SRWLock
0x1000ce29  call    ds:__imp__AcquireSRWLockExclusive@4; AcquireSRWLockExclusive(x)
0x1000ce2f  xor     eax, eax
0x1000ce31  mov     dword ptr [ebp+var_20], ebx
0x1000ce34  push    0Ch; unsigned int
0x1000ce36  mov     ecx, (offset xmmword_100661C0+0Ch); this
0x1000ce3b  mov     word ptr [ebp+var_20+6], ax
0x1000ce3f  mov     word ptr [ebp+var_20+4], si
0x1000ce43  call    ?ensure@heap_buffer@details_abi@wil@@QAE_NI@Z; wil::details_abi::heap_buffer::ensure(uint)
0x1000ce48  test    al, al
0x1000ce4a  jz      short loc_1000CEB0
0x1000ce4c  mov     edx, dword_100661D0
0x1000ce52  mov     ecx, dword_100661D4
0x1000ce58  sub     ecx, edx
0x1000ce5a  cmp     edx, dword_100661D4
0x1000ce60  sbb     eax, eax
0x1000ce62  and     eax, ecx
0x1000ce64  test    edx, edx
0x1000ce66  jnz     short loc_1000CE76
0x1000ce68  call    ds:__imp___errno
0x1000ce6e  mov     dword ptr [eax], 16h
0x1000ce74  jmp     short loc_1000CEA4
0x1000ce76  cmp     eax, 0Ch
0x1000ce79  jb      short loc_1000CE8C
0x1000ce7b  movq    xmm0, [ebp+var_20]
0x1000ce80  mov     eax, [ebp+arg_8]
0x1000ce83  movq    qword ptr [edx], xmm0
0x1000ce87  mov     [edx+8], eax
0x1000ce8a  jmp     short loc_1000CEA9
0x1000ce8c  push    eax; Size
0x1000ce8d  push    0; Val
0x1000ce8f  push    edx; void *
0x1000ce90  call    _memset
0x1000ce95  add     esp, 0Ch
0x1000ce98  call    ds:__imp___errno
0x1000ce9e  mov     dword ptr [eax], 22h ; '"'
0x1000cea4  call    __invalid_parameter_noinfo
0x1000cea9  add     dword_100661D0, 0Ch
0x1000ceb0  push    offset ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1000ceb5  mov     edx, offset byte_10066170
0x1000ceba  mov     ecx, offset dword_1006616C
0x1000cebf  call    ??$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YGXAAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAU_TP_TIMER@@P6GXPAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SGX0@ZU?$integral_constant@I$0A@@wistd@@PAU1@PAU1@$0A@$$T@details@wil@@@details@wil@@@1@AA_NPAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<uint,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x1000cec4  push    offset stru_10066164
0x1000cec9  jmp     loc_1000D05B
0x1000cece  test    eax, eax
0x1000ced0  jnz     loc_1000CF57
0x1000ced6  cmp     esi, 0FEh
0x1000cedc  jz      short loc_1000CF57
0x1000cede  xorps   xmm0, xmm0
0x1000cee1  movlpd  [ebp+var_14], xmm0
0x1000cee6  mov     dword ptr [ebp+var_14], ebx
0x1000cee9  mov     word ptr [ebp+var_14+4], si
0x1000ceed  test    ecx, ecx
0x1000ceef  jns     short loc_1000CEF6
0x1000cef1  or      word ptr [ebp+var_14+6], 1
0x1000cef6  mov     esi, _g_wil_details_pfnRtlNotifyFeatureUsage
0x1000cefc  test    esi, esi
0x1000cefe  jnz     short loc_1000CF35
0x1000cf00  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000cf05  test    eax, eax
0x1000cf07  jnz     short loc_1000CF19
0x1000cf09  push    offset ModuleName; "ntdll.dll"
0x1000cf0e  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x1000cf14  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000cf19  push    offset aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1000cf1e  push    eax; hModule
0x1000cf1f  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1000cf25  mov     esi, eax
0x1000cf27  mov     _g_wil_details_pfnRtlNotifyFeatureUsage, esi
0x1000cf2d  test    esi, esi
0x1000cf2f  jz      loc_1000D061
0x1000cf35  lea     eax, [ebp+var_14]
0x1000cf38  mov     ecx, esi
0x1000cf3a  push    eax; void *
0x1000cf3b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000cf41  call    esi ; _g_wil_details_pfnRtlNotifyFeatureUsage
0x1000cf43  mov     ecx, [ebp+var_C]
0x1000cf46  mov     large fs:0, ecx
0x1000cf4d  pop     ecx
0x1000cf4e  pop     edi
0x1000cf4f  pop     esi
0x1000cf50  pop     ebx
0x1000cf51  mov     esp, ebp
0x1000cf53  pop     ebp
0x1000cf54  retn    10h
0x1000cf57  mov     [ebp+var_4], 1
0x1000cf5e  cmp     ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1000cf65  jz      loc_1000D061
0x1000cf6b  mov     ecx, offset ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1000cf70  call    ?EnsureStateData@FeatureStateManager@details@wil@@AAE_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1000cf75  test    al, al
0x1000cf77  jz      loc_1000D061
0x1000cf7d  mov     edi, SRWLock
0x1000cf83  cmp     esi, 0FEh
0x1000cf89  jz      loc_1000D00F
0x1000cf8f  cmp     esi, 0C8h
0x1000cf95  jb      short loc_1000CFAF
0x1000cf97  cmp     esi, 100h
0x1000cf9d  jb      loc_1000D061
0x1000cfa3  cmp     esi, 200h
0x1000cfa9  jnb     loc_1000D061
0x1000cfaf  push    edi; SRWLock
0x1000cfb0  call    ds:__imp__AcquireSRWLockExclusive@4; AcquireSRWLockExclusive(x)
0x1000cfb6  cmp     esi, 2
0x1000cfb9  jz      short loc_1000CFEE
0x1000cfbb  cmp     esi, 3
0x1000cfbe  jz      short loc_1000CFEE
0x1000cfc0  cmp     esi, 6
0x1000cfc3  jz      short loc_1000CFEE
0x1000cfc5  cmp     esi, 7
0x1000cfc8  jz      short loc_1000CFEE
0x1000cfca  cmp     esi, 100h
0x1000cfd0  jb      short loc_1000CFDA
0x1000cfd2  cmp     esi, 180h
0x1000cfd8  jb      short loc_1000CFEE
0x1000cfda  mov     eax, [ebp+arg_8]
0x1000cfdd  lea     ecx, [edi+28h]
0x1000cfe0  push    eax
0x1000cfe1  push    [ebp+this]
0x1000cfe4  push    esi
0x1000cfe5  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QAE_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1000cfea  mov     bl, al
0x1000cfec  jmp     short loc_1000CFFE
0x1000cfee  push    ecx
0x1000cfef  push    [ebp+this]
0x1000cff2  lea     ecx, [edi+4]
0x1000cff5  push    esi
0x1000cff6  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QAE_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1000cffb  mov     bl, [edi+24h]
0x1000cffe  test    edi, edi
0x1000d000  jz      short loc_1000D009
0x1000d002  push    edi; SRWLock
0x1000d003  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d009  test    bl, bl
0x1000d00b  jz      short loc_1000D061
0x1000d00d  jmp     short loc_1000D016
0x1000d00f  mov     ecx, edi; SRWLock
0x1000d011  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QAEXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1000d016  cmp     ?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1000d01d  jnz     short loc_1000D061
0x1000d01f  mov     esi, ?g_pfnDllShutdownInProgress@details@wil@@3P6GEX_EA
0x1000d025  test    esi, esi
0x1000d027  jz      short loc_1000D037
0x1000d029  mov     ecx, esi
0x1000d02b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000d031  call    esi ; ?g_pfnDllShutdownInProgress@details@wil@@3P6GEX_EA
0x1000d033  test    al, al
0x1000d035  jnz     short loc_1000D061
0x1000d037  push    offset stru_10066160; SRWLock
0x1000d03c  call    ds:__imp__AcquireSRWLockExclusive@4; AcquireSRWLockExclusive(x)
0x1000d042  push    offset ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1000d047  mov     edx, offset byte_10066171
0x1000d04c  mov     ecx, offset dword_10066168
0x1000d051  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YGXAAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAU_TP_TIMER@@P6GXPAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SGX0@ZU?$integral_constant@I$0A@@wistd@@PAU1@PAU1@$0A@$$T@details@wil@@@details@wil@@@1@AA_NPAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<uint,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x1000d056  push    offset stru_10066160; SRWLock
0x1000d05b  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d061  mov     ecx, [ebp+var_C]
0x1000d064  mov     large fs:0, ecx
0x1000d06b  pop     ecx
0x1000d06c  pop     edi
0x1000d06d  pop     esi
0x1000d06e  pop     ebx
0x1000d06f  mov     esp, ebp
0x1000d071  pop     ebp
0x1000d072  retn    10h
0x1005f070  jmp     ds:__imp____std_terminate
0x1005f830  nop
0x1005f831  nop
0x1005f832  mov     edx, [esp-4+arg_4]
0x1005f836  lea     eax, [edx+0Ch]
0x1005f839  mov     ecx, [edx-24h]
0x1005f83c  xor     ecx, eax; StackCookie
0x1005f83e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f843  mov     eax, offset stru_10062BE4
0x1005f848  jmp     ___CxxFrameHandler3
```

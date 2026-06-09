# RaiseDialogThread(CNetStatisticsEngine *,PROPERTY_DIALOG)

- ea: `0x18005ac00`
- end: `0x18005ade9`
- name: `?RaiseDialogThread@@YAKPEAVCNetStatisticsEngine@@W4PROPERTY_DIALOG@@@Z`
- size: `489`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005abf0`
- `0x18005adf0`
- `0x18005b2c0`

## callees

- `0x1800157f0`
- `0x18001644c`
- `0x180017b90`
- `0x180018d74`
- `0x180040790`
- `0x180046100`
- `0x18004eb5c`
- `0x18005985c`
- `0x18005ac00`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18005add2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18005add2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005adc2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005adc2`
- `ole32!CoUninitialize` at `0x18005adac`
- `ole32!CoUninitialize` at `0x18005adac`
- `ole32!CoInitializeEx` at `0x18005ac26`
- `ole32!CoInitializeEx` at `0x18005ac26`

## string_xrefs

- `0x18005adbb`: `netshell.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RaiseDialogThread(__int64 a1, int a2)
{
  HRESULT v5; // eax
  HRESULT v6; // r14d
  signed int ConnectionFromPersistData; // ebx
  int v8; // esi
  struct IUnknownVtbl *lpVtbl; // rcx
  HMODULE ModuleHandleW; // rax
  struct IUnknown v11; // [rsp+60h] [rbp+30h] BYREF
  struct tagNETCON_PROPERTIES_EX *pv; // [rsp+70h] [rbp+40h] BYREF
  __int64 v13; // [rsp+78h] [rbp+48h] BYREF

  if ( !a1 )
    return 0;
  v5 = CoInitializeEx(0, 6u);
  v6 = v5;
  ConnectionFromPersistData = 0;
  if ( v5 != -2147417850 )
    ConnectionFromPersistData = v5;
  if ( ConnectionFromPersistData >= 0 )
  {
    if ( a2 )
    {
      v8 = a2 - 1;
      if ( v8 )
      {
        if ( v8 == 1 )
          ConnectionFromPersistData = HrRaiseWlanProperties((struct CNetStatisticsEngine *)a1);
      }
      else
      {
        v11.lpVtbl = 0;
        ConnectionFromPersistData = HrGetConnectionFromPersistData(
                                      (const struct _GUID *)(a1 + 180),
                                      *(const unsigned __int8 **)(a1 + 168),
                                      *(_DWORD *)(a1 + 176),
                                      &IID_INetConnection,
                                      &v11,
                                      0);
        if ( ConnectionFromPersistData >= 0 )
        {
          pv = 0;
          v13 = 0;
          lpVtbl = v11.lpVtbl;
          if ( v11.lpVtbl )
          {
            if ( (*(int (__fastcall **)(struct IUnknownVtbl *, GUID *, __int64 *))v11.lpVtbl->QueryInterface)(
                   v11.lpVtbl,
                   &IID_INetConnection2,
                   &v13) >= 0
              && (*(int (__fastcall **)(__int64, struct tagNETCON_PROPERTIES_EX **))(*(_QWORD *)v13 + 24LL))(v13, &pv) >= 0 )
            {
              SqmUpload(1, *((unsigned int *)pv + 11), *((unsigned int *)pv + 12), *((unsigned int *)pv + 10));
              HrFreeNetConProperties2(pv);
            }
            lpVtbl = v11.lpVtbl;
          }
          ConnectionFromPersistData = HrRaiseDialogFromINetConnection(*(_QWORD *)(a1 + 208), lpVtbl, HrOnCommandFix);
          ReleaseObj((struct IUnknown *)v11.lpVtbl);
          ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v13);
        }
      }
    }
    else
    {
      v11.lpVtbl = 0;
      ConnectionFromPersistData = HrGetConnectionFromPersistData(
                                    (const struct _GUID *)(a1 + 180),
                                    *(const unsigned __int8 **)(a1 + 168),
                                    *(_DWORD *)(a1 + 176),
                                    &IID_INetConnection,
                                    &v11,
                                    1);
      if ( ConnectionFromPersistData >= 0 )
      {
        ConnectionFromPersistData = HrRaiseConnectionPropertiesLua(
                                      *(HWND *)(a1 + 208),
                                      (struct INetConnection *)v11.lpVtbl);
        ReleaseObj((struct IUnknown *)v11.lpVtbl);
      }
    }
    if ( v6 != -2147417850 )
      CoUninitialize();
  }
  ReleaseObj((struct IUnknown *)(a1 + 32));
  ModuleHandleW = GetModuleHandleW(L"netshell.dll");
  if ( ModuleHandleW )
    FreeLibraryAndExitThread(ModuleHandleW, ConnectionFromPersistData);
  return 1;
}

```

## disassembly

```asm
0x18005ac00  push    rbp
0x18005ac02  push    rbx
0x18005ac03  push    rsi
0x18005ac04  push    rdi
0x18005ac05  push    r14
0x18005ac07  mov     rbp, rsp
0x18005ac0a  sub     rsp, 30h
0x18005ac0e  mov     esi, edx
0x18005ac10  mov     rdi, rcx
0x18005ac13  test    rcx, rcx
0x18005ac16  jnz     short loc_18005AC1F
0x18005ac18  xor     eax, eax
0x18005ac1a  jmp     loc_18005ADDE
0x18005ac1f  mov     edx, 6; dwCoInit
0x18005ac24  xor     ecx, ecx; pvReserved
0x18005ac26  call    cs:__imp_CoInitializeEx
0x18005ac2c  mov     r14d, eax
0x18005ac2f  xor     ebx, ebx
0x18005ac31  cmp     eax, 80010106h
0x18005ac36  cmovnz  ebx, eax
0x18005ac39  test    ebx, ebx
0x18005ac3b  js      loc_18005ADB2
0x18005ac41  test    esi, esi
0x18005ac43  jz      loc_18005AD48
0x18005ac49  sub     esi, 1
0x18005ac4c  jz      short loc_18005AC66
0x18005ac4e  cmp     esi, 1
0x18005ac51  jnz     loc_18005ADA3
0x18005ac57  mov     rcx, rdi; this
0x18005ac5a  call    ?HrRaiseWlanProperties@@YAJPEAVCNetStatisticsEngine@@@Z; HrRaiseWlanProperties(CNetStatisticsEngine *)
0x18005ac5f  mov     ebx, eax
0x18005ac61  jmp     loc_18005ADA3
0x18005ac66  mov     [rbp+arg_0.lpVtbl], 0
0x18005ac6e  lea     rcx, [rdi+0B4h]; struct _GUID *
0x18005ac75  mov     [rsp+30h+var_8], 0; int
0x18005ac7d  lea     rax, [rbp+arg_0]
0x18005ac81  mov     [rsp+30h+var_10], rax; struct IUnknown *
0x18005ac86  lea     r9, IID_INetConnection; struct _GUID *
0x18005ac8d  mov     r8d, [rdi+0B0h]; unsigned int
0x18005ac94  mov     rdx, [rdi+0A8h]; unsigned __int8 *
0x18005ac9b  call    ?HrGetConnectionFromPersistData@@YAJAEBU_GUID@@PEBEK0PEAPEAXH@Z; HrGetConnectionFromPersistData(_GUID const &,uchar const *,ulong,_GUID const &,void * *,int)
0x18005aca0  mov     ebx, eax
0x18005aca2  test    eax, eax
0x18005aca4  js      loc_18005ADA3
0x18005acaa  mov     [rbp+pv], 0
0x18005acb2  mov     [rbp+arg_18], 0
0x18005acba  mov     rcx, [rbp+arg_0.lpVtbl]
0x18005acbe  test    rcx, rcx
0x18005acc1  jz      short loc_18005AD1B
0x18005acc3  mov     rax, [rcx]
0x18005acc6  lea     r8, [rbp+arg_18]
0x18005acca  lea     rdx, IID_INetConnection2
0x18005acd1  mov     rax, [rax]
0x18005acd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005acd9  test    eax, eax
0x18005acdb  js      short loc_18005AD17
0x18005acdd  mov     rcx, [rbp+arg_18]
0x18005ace1  mov     rax, [rcx]
0x18005ace4  lea     rdx, [rbp+pv]
0x18005ace8  mov     rax, [rax+18h]
0x18005acec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005acf1  test    eax, eax
0x18005acf3  js      short loc_18005AD17
0x18005acf5  mov     rdx, [rbp+pv]
0x18005acf9  mov     r9d, [rdx+28h]
0x18005acfd  mov     r8d, [rdx+30h]
0x18005ad01  mov     edx, [rdx+2Ch]
0x18005ad04  mov     ecx, 1
0x18005ad09  call    ?SqmUpload@@YAJW4tagSqmRepairEntryPoint@@W4tagNETCON_MEDIATYPE@@W4tagNETCON_SUBMEDIATYPE@@W4tagNETCON_STATUS@@@Z; SqmUpload(tagSqmRepairEntryPoint,tagNETCON_MEDIATYPE,tagNETCON_SUBMEDIATYPE,tagNETCON_STATUS)
0x18005ad0e  mov     rcx, [rbp+pv]; pv
0x18005ad12  call    ?HrFreeNetConProperties2@@YAJPEAUtagNETCON_PROPERTIES_EX@@@Z; HrFreeNetConProperties2(tagNETCON_PROPERTIES_EX *)
0x18005ad17  mov     rcx, [rbp+arg_0.lpVtbl]
0x18005ad1b  lea     r8, ?HrOnCommandFix@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUHWND__@@PEAUIShellFolder@@@Z; HrOnCommandFix(std::vector<CPConFoldPidl<ConFoldPidl_v3>> const &,HWND__ *,IShellFolder *)
0x18005ad22  mov     rdx, rcx
0x18005ad25  mov     rcx, [rdi+0D0h]
0x18005ad2c  call    ?HrRaiseDialogFromINetConnection@@YAJPEAUHWND__@@PEAUINetConnection@@P6AJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@0PEAUIShellFolder@@@Z@Z; HrRaiseDialogFromINetConnection(HWND__ *,INetConnection *,long (*)(std::vector<CPConFoldPidl<ConFoldPidl_v3>> const &,HWND__ *,IShellFolder *))
0x18005ad31  mov     ebx, eax
0x18005ad33  mov     rcx, [rbp+arg_0.lpVtbl]; struct IUnknown *
0x18005ad37  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18005ad3c  nop
0x18005ad3d  lea     rcx, [rbp+arg_18]
0x18005ad41  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18005ad46  jmp     short loc_18005ADA3
0x18005ad48  mov     [rbp+arg_0.lpVtbl], 0
0x18005ad50  lea     rcx, [rdi+0B4h]; struct _GUID *
0x18005ad57  mov     [rsp+30h+var_8], 1; int
0x18005ad5f  lea     rax, [rbp+arg_0]
0x18005ad63  mov     [rsp+30h+var_10], rax; struct IUnknown *
0x18005ad68  lea     r9, IID_INetConnection; struct _GUID *
0x18005ad6f  mov     r8d, [rdi+0B0h]; unsigned int
0x18005ad76  mov     rdx, [rdi+0A8h]; unsigned __int8 *
0x18005ad7d  call    ?HrGetConnectionFromPersistData@@YAJAEBU_GUID@@PEBEK0PEAPEAXH@Z; HrGetConnectionFromPersistData(_GUID const &,uchar const *,ulong,_GUID const &,void * *,int)
0x18005ad82  mov     ebx, eax
0x18005ad84  test    eax, eax
0x18005ad86  js      short loc_18005ADA3
0x18005ad88  mov     rdx, [rbp+arg_0.lpVtbl]; struct INetConnection *
0x18005ad8c  mov     rcx, [rdi+0D0h]; HWND
0x18005ad93  call    ?HrRaiseConnectionPropertiesLua@@YAJPEAUHWND__@@PEAUINetConnection@@@Z; HrRaiseConnectionPropertiesLua(HWND__ *,INetConnection *)
0x18005ad98  mov     ebx, eax
0x18005ad9a  mov     rcx, [rbp+arg_0.lpVtbl]; struct IUnknown *
0x18005ad9e  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18005ada3  cmp     r14d, 80010106h
0x18005adaa  jz      short loc_18005ADB2
0x18005adac  call    cs:__imp_CoUninitialize
0x18005adb2  lea     rcx, [rdi+20h]; struct IUnknown *
0x18005adb6  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18005adbb  lea     rcx, ?c_szNetShellDll@@3QBGB; "netshell.dll"
0x18005adc2  call    cs:__imp_GetModuleHandleW
0x18005adc8  test    rax, rax
0x18005adcb  jz      short loc_18005ADD9
0x18005adcd  mov     edx, ebx; dwExitCode
0x18005adcf  mov     rcx, rax; hLibModule
0x18005add2  call    cs:__imp_FreeLibraryAndExitThread
0x18005add8  int     3; Trap to Debugger
0x18005add9  mov     eax, 1
0x18005adde  add     rsp, 30h
0x18005ade2  pop     r14
0x18005ade4  pop     rdi
0x18005ade5  pop     rsi
0x18005ade6  pop     rbx
0x18005ade7  pop     rbp
0x18005ade8  retn
```

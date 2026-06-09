# CDXGIFactory::FinalRelease(void)

- ea: `0x18002fe28`
- end: `0x1800300ff`
- name: `?FinalRelease@CDXGIFactory@@QEAAXXZ`
- size: `727`
- prototype: `void __fastcall(CDXGIFactory *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002fbdc`

## callees

- `0x180006770`
- `0x18000cb1c`
- `0x1800174f4`
- `0x180017e1c`
- `0x180019518`
- `0x18001d480`
- `0x18001d9b0`
- `0x18001ddec`
- `0x18002dbe8`
- `0x18002fe28`
- `0x180030108`
- `0x180030384`
- `0x18004ef4c`
- `0x180056428`
- `0x180058ef4`
- `0x180066b54`
- `0x1800cb010`

## import_xrefs

- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x180030038`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x180030038`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fee5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fee5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fec9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fec9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ff31`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ff31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800300b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800300b5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800300a5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800300a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030086`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030086`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003006d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003006d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300d6`

## string_xrefs

- `0x18002fec2`: `gdi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDXGIFactory::FinalRelease(CDXGIFactory *this)
{
  CModule *v2; // rcx
  __int64 v3; // rcx
  HMODULE Library; // rax
  HMODULE v5; // rbx
  int (*ProcAddress)(const struct _D3DKMT_CLOSEADAPTER *); // rax
  __int64 v7; // rcx
  CLazyModule *v8; // rcx
  __int64 v9; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-28h] BYREF
  char v11; // [rsp+58h] [rbp-20h]
  ULONG_PTR Arguments[3]; // [rsp+60h] [rbp-18h] BYREF
  HMODULE v13; // [rsp+A0h] [rbp+28h] BYREF

  if ( *((_QWORD *)this + 49) )
  {
    CheckDxgiDebugDll();
    if ( g_pDebugPrivate )
    {
      (*(void (__fastcall **)(struct IDXGIDebugPrivate *, _QWORD))(*(_QWORD *)g_pDebugPrivate + 40LL))(
        g_pDebugPrivate,
        *((_QWORD *)this + 49));
      *((_QWORD *)this + 49) = 0;
    }
  }
  CDestructionNotifier::Destroy((CDXGIFactory *)((char *)this + 8));
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(
    &lpCriticalSection,
    &CriticalSection);
  if ( *((_BYTE *)this + 760) )
  {
    if ( (int)EnumAdapterByGpuPreferenceInfo::PrepareInfoForTelemetry((CDXGIFactory *)((char *)this + 832)) >= 0 )
      CDXGITelemetryHelper::LogGpuPreferenceInfo(
        v3,
        (char *)this + 832,
        *((unsigned int *)this + 104),
        *((unsigned int *)this + 106));
    Library = LoadLibraryExW(L"gdi32.dll", 0, 0);
    v5 = Library;
    v13 = Library;
    if ( Library )
    {
      ProcAddress = (int (*)(const struct _D3DKMT_CLOSEADAPTER *))GetProcAddress(Library, "D3DKMTCloseAdapter");
      CDXGIFactory::ClearAdapters(this, ProcAddress);
    }
    if ( (Microsoft_Windows_DXGIEnableBits & 1) != 0 )
      McTemplateU0pqqZRZRx_EtwEventWriteTransfer(
        (_DWORD)v2,
        (unsigned int)EventDestroyFactory,
        (_DWORD)this,
        *((_BYTE *)this + 744) != 0);
    if ( v5 )
      FreeLibrary(v5);
  }
  if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v2, "(", 1);
  if ( !(_DWORD)qword_180109A08 && !(unsigned int)IsMultiSession0() )
    CDXGIFactory::MakeWindowAssociation(this, 0, 1u);
  LOBYTE(v13) = 0;
  CModule::RemoveFactory(v2, this, (bool *)&v13);
  *((_QWORD *)this + 98) = 0;
  *((_QWORD *)this + 99) = 0;
  std::_List_node<NotificationRegistry::NotificationRecord,void *>::_Free_non_head<std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>>>(
    v7,
    *((_QWORD *)this + 96));
  **((_QWORD **)this + 96) = *((_QWORD *)this + 96);
  *(_QWORD *)(*((_QWORD *)this + 96) + 8LL) = *((_QWORD *)this + 96);
  *((_QWORD *)this + 97) = 0;
  v8 = xmmword_180109A10;
  if ( xmmword_180109A10 )
    *((_DWORD *)xmmword_180109A10 + 53) -= *((_DWORD *)this + 202);
  std::_List_node<NotificationRegistry::NotificationRecord,void *>::_Free_non_head<std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>>>(
    v8,
    *((_QWORD *)this + 100));
  **((_QWORD **)this + 100) = *((_QWORD *)this + 100);
  *(_QWORD *)(*((_QWORD *)this + 100) + 8LL) = *((_QWORD *)this + 100);
  *((_QWORD *)this + 101) = 0;
  std::_List_node<NotificationRegistry::NotificationRecord,void *>::_Free_non_head<std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>>>(
    v9,
    *((_QWORD *)this + 102));
  **((_QWORD **)this + 102) = *((_QWORD *)this + 102);
  *(_QWORD *)(*((_QWORD *)this + 102) + 8LL) = *((_QWORD *)this + 102);
  *((_QWORD *)this + 103) = 0;
  if ( !xmmword_180109A10 && RtlIsCriticalSectionLockedByThread(NtCurrentPeb()->LoaderLock) )
  {
    DXGI_SDK_MSG(this, DXGI_MSG_IDXGIFactory_Release_CalledFromDllMain);
    Arguments[0] = -2005270527;
    Arguments[1] = 83;
    RaiseException(0x87Au, 1u, 2u, Arguments);
  }
  if ( (_BYTE)v13 )
  {
    CLockedDLLWatchdogThread::CLockedDLLWatchdogThread((CLockedDLLWatchdogThread *)Arguments);
    LeaveCriticalSection(lpCriticalSection);
    v11 = 0;
    if ( hHandle && hObject )
    {
      SetEvent(hObject);
      WaitForSingleObject(hHandle, 0xFFFFFFFF);
      CloseHandle(hObject);
      hObject = 0;
      CloseHandle(hHandle);
      hHandle = 0;
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(Arguments);
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&lpCriticalSection);
}

```

## disassembly

```asm
0x18002fe28  push    rbp
0x18002fe2a  push    rbx
0x18002fe2b  push    rsi
0x18002fe2c  push    rdi
0x18002fe2d  mov     rbp, rsp
0x18002fe30  sub     rsp, 78h
0x18002fe34  mov     rdi, rcx
0x18002fe37  xor     esi, esi
0x18002fe39  cmp     [rcx+188h], rsi
0x18002fe40  jz      short loc_18002FE6D
0x18002fe42  call    ?CheckDxgiDebugDll@@YAXXZ; CheckDxgiDebugDll(void)
0x18002fe47  mov     rcx, cs:?g_pDebugPrivate@@3PEAUIDXGIDebugPrivate@@EA; IDXGIDebugPrivate * g_pDebugPrivate
0x18002fe4e  test    rcx, rcx
0x18002fe51  jz      short loc_18002FE6D
0x18002fe53  mov     rax, [rcx]
0x18002fe56  mov     rdx, [rdi+188h]
0x18002fe5d  mov     rax, [rax+28h]
0x18002fe61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe66  mov     [rdi+188h], rsi
0x18002fe6d  lea     rcx, [rdi+8]; this
0x18002fe71  call    ?Destroy@CDestructionNotifier@@QEAAXXZ; CDestructionNotifier::Destroy(void)
0x18002fe76  lea     rdx, CriticalSection
0x18002fe7d  lea     rcx, [rbp+lpCriticalSection]
0x18002fe81  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x18002fe86  nop
0x18002fe87  cmp     [rdi+2F8h], sil
0x18002fe8e  jz      loc_18002FF37
0x18002fe94  lea     rbx, [rdi+340h]
0x18002fe9b  mov     rcx, rbx; this
0x18002fe9e  call    ?PrepareInfoForTelemetry@EnumAdapterByGpuPreferenceInfo@@QEAAJXZ; EnumAdapterByGpuPreferenceInfo::PrepareInfoForTelemetry(void)
0x18002fea3  test    eax, eax
0x18002fea5  js      short loc_18002FEBD
0x18002fea7  mov     r9d, [rdi+1A8h]
0x18002feae  mov     r8d, [rdi+1A0h]
0x18002feb5  mov     rdx, rbx
0x18002feb8  call    ?LogGpuPreferenceInfo@CDXGITelemetryHelper@@QEAAXAEBUEnumAdapterByGpuPreferenceInfo@@W4ADAPTER_ENUM_ORDER@@W4GPU_PREFERENCE_DECIDING_FACTOR@@@Z; CDXGITelemetryHelper::LogGpuPreferenceInfo(EnumAdapterByGpuPreferenceInfo const &,ADAPTER_ENUM_ORDER,GPU_PREFERENCE_DECIDING_FACTOR)
0x18002febd  xor     r8d, r8d; dwFlags
0x18002fec0  xor     edx, edx; hFile
0x18002fec2  lea     rcx, LibFileName; "gdi32.dll"
0x18002fec9  call    cs:__imp_LoadLibraryExW
0x18002fecf  mov     rbx, rax
0x18002fed2  mov     [rbp+arg_0], rax
0x18002fed6  test    rax, rax
0x18002fed9  jz      short loc_18002FEF6
0x18002fedb  lea     rdx, aD3dkmtcloseada; "D3DKMTCloseAdapter"
0x18002fee2  mov     rcx, rax; hModule
0x18002fee5  call    cs:__imp_GetProcAddress
0x18002feeb  mov     rdx, rax; int (*)(const struct _D3DKMT_CLOSEADAPTER *)
0x18002feee  mov     rcx, rdi; this
0x18002fef1  call    ?ClearAdapters@CDXGIFactory@@AEAAXP6AJPEBU_D3DKMT_CLOSEADAPTER@@@Z@Z; CDXGIFactory::ClearAdapters(long (*)(_D3DKMT_CLOSEADAPTER const *))
0x18002fef6  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 1
0x18002fefd  jz      short loc_18002FF29
0x18002feff  mov     r9d, esi
0x18002ff02  cmp     [rdi+2E8h], sil
0x18002ff09  setnz   r9b
0x18002ff0d  mov     rax, cs:qword_180109C48
0x18002ff14  mov     [rsp+78h+var_30], rax
0x18002ff19  mov     r8, rdi
0x18002ff1c  lea     rdx, EventDestroyFactory
0x18002ff23  call    McTemplateU0pqqZRZRx_EtwEventWriteTransfer
0x18002ff28  nop
0x18002ff29  test    rbx, rbx
0x18002ff2c  jz      short loc_18002FF37
0x18002ff2e  mov     rcx, rbx; hLibModule
0x18002ff31  call    cs:__imp_FreeLibrary
0x18002ff37  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 2
0x18002ff3e  jz      short loc_18002FF52
0x18002ff40  mov     r8d, 1
0x18002ff46  lea     rdx, EventProfileStart; "("
0x18002ff4d  call    McTemplateU0q_EtwEventWriteTransfer
0x18002ff52  cmp     dword ptr cs:qword_180109A08, esi
0x18002ff58  jnz     short loc_18002FF71
0x18002ff5a  call    ?IsMultiSession0@@YAHXZ; IsMultiSession0(void)
0x18002ff5f  test    eax, eax
0x18002ff61  jnz     short loc_18002FF71
0x18002ff63  xor     edx, edx; HWND
0x18002ff65  lea     r8d, [rax+1]; unsigned int
0x18002ff69  mov     rcx, rdi; this
0x18002ff6c  call    ?MakeWindowAssociation@CDXGIFactory@@UEAAJPEAUHWND__@@I@Z; CDXGIFactory::MakeWindowAssociation(HWND__ *,uint)
0x18002ff71  mov     byte ptr [rbp+arg_0], sil
0x18002ff75  lea     r8, [rbp+arg_0]; bool *
0x18002ff79  mov     rdx, rdi; struct CDXGIFactory *
0x18002ff7c  call    ?RemoveFactory@CModule@@QEAAXPEAVCDXGIFactory@@AEA_N@Z; CModule::RemoveFactory(CDXGIFactory *,bool &)
0x18002ff81  mov     [rdi+310h], rsi
0x18002ff88  mov     [rdi+318h], rsi
0x18002ff8f  mov     rdx, [rdi+300h]
0x18002ff96  call    ??$_Free_non_head@V?$allocator@U?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@@std@@@?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<NotificationRegistry::NotificationRecord,void *>::_Free_non_head<std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>>>(std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>> &,std::_List_node<NotificationRegistry::NotificationRecord,void *> *)
0x18002ff9b  mov     rax, [rdi+300h]
0x18002ffa2  mov     [rax], rax
0x18002ffa5  mov     rax, [rdi+300h]
0x18002ffac  mov     [rax+8], rax
0x18002ffb0  mov     [rdi+308h], rsi
0x18002ffb7  mov     rcx, qword ptr cs:xmmword_180109A10
0x18002ffbe  test    rcx, rcx
0x18002ffc1  jz      short loc_18002FFCF
0x18002ffc3  mov     eax, [rdi+328h]
0x18002ffc9  sub     [rcx+0D4h], eax
0x18002ffcf  mov     rdx, [rdi+320h]
0x18002ffd6  call    ??$_Free_non_head@V?$allocator@U?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@@std@@@?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<NotificationRegistry::NotificationRecord,void *>::_Free_non_head<std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>>>(std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>> &,std::_List_node<NotificationRegistry::NotificationRecord,void *> *)
0x18002ffdb  mov     rax, [rdi+320h]
0x18002ffe2  mov     [rax], rax
0x18002ffe5  mov     rax, [rdi+320h]
0x18002ffec  mov     [rax+8], rax
0x18002fff0  mov     [rdi+328h], rsi
0x18002fff7  mov     rdx, [rdi+330h]
0x18002fffe  call    ??$_Free_non_head@V?$allocator@U?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@@std@@@?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<NotificationRegistry::NotificationRecord,void *>::_Free_non_head<std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>>>(std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>> &,std::_List_node<NotificationRegistry::NotificationRecord,void *> *)
0x180030003  mov     rax, [rdi+330h]
0x18003000a  mov     [rax], rax
0x18003000d  mov     rax, [rdi+330h]
0x180030014  mov     [rax+8], rax
0x180030018  mov     [rdi+338h], rsi
0x18003001f  cmp     qword ptr cs:xmmword_180109A10, rsi
0x180030026  jnz     short loc_180030073
0x180030028  mov     rcx, gs:60h
0x180030031  mov     rcx, [rcx+110h]; CriticalSection
0x180030038  call    cs:__imp_RtlIsCriticalSectionLockedByThread
0x18003003e  test    eax, eax
0x180030040  jz      short loc_180030073
0x180030042  mov     ebx, 53h ; 'S'
0x180030047  mov     edx, ebx; enum DXGI_Message_Id
0x180030049  mov     rcx, rdi; struct CDXGIFactory *
0x18003004c  call    ?DXGI_SDK_MSG@@YAXPEAVCDXGIFactory@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG(CDXGIFactory *,DXGI_Message_Id,...)
0x180030051  mov     [rbp+Arguments], 0FFFFFFFF887A0001h
0x180030059  mov     [rbp+var_10], rbx
0x18003005d  lea     r9, [rbp+Arguments]; lpArguments
0x180030061  lea     edx, [rbx-52h]; dwExceptionFlags
0x180030064  mov     ecx, 87Ah; dwExceptionCode
0x180030069  lea     r8d, [rbx-51h]; nNumberOfArguments
0x18003006d  call    cs:__imp_RaiseException
0x180030073  cmp     byte ptr [rbp+arg_0], sil
0x180030077  jz      short loc_1800300ED
0x180030079  lea     rcx, [rbp+Arguments]; this
0x18003007d  call    ??0CLockedDLLWatchdogThread@@QEAA@XZ; CLockedDLLWatchdogThread::CLockedDLLWatchdogThread(void)
0x180030082  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180030086  call    cs:__imp_LeaveCriticalSection
0x18003008c  mov     [rbp+var_20], sil
0x180030090  cmp     cs:hHandle, rsi
0x180030097  jz      short loc_1800300E3
0x180030099  mov     rcx, cs:hObject; hEvent
0x1800300a0  test    rcx, rcx
0x1800300a3  jz      short loc_1800300E3
0x1800300a5  call    cs:__imp_SetEvent
0x1800300ab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800300ae  mov     rcx, cs:hHandle; hHandle
0x1800300b5  call    cs:__imp_WaitForSingleObject
0x1800300bb  mov     rcx, cs:hObject; hObject
0x1800300c2  call    cs:__imp_CloseHandle
0x1800300c8  mov     cs:hObject, rsi
0x1800300cf  mov     rcx, cs:hHandle; hObject
0x1800300d6  call    cs:__imp_CloseHandle
0x1800300dc  mov     cs:hHandle, rsi
0x1800300e3  lea     rcx, [rbp+Arguments]
0x1800300e7  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800300ec  nop
0x1800300ed  lea     rcx, [rbp+lpCriticalSection]
0x1800300f1  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800300f6  add     rsp, 78h
0x1800300fa  pop     rdi
0x1800300fb  pop     rsi
0x1800300fc  pop     rbx
0x1800300fd  pop     rbp
0x1800300fe  retn
```

# MotionTurboJpeg::CMJPGMFT::~CMJPGMFT(void)

- ea: `0x18003f308`
- end: `0x18003f400`
- name: `??1CMJPGMFT@MotionTurboJpeg@@UEAA@XZ`
- size: `248`
- prototype: `void __fastcall(MotionTurboJpeg::CMJPGMFT *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003fcc0`

## callees

- `0x180014940`
- `0x18003af40`
- `0x18003f308`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f3ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f3ed`
- `MFPlat!MFUnlockWorkQueue` at `0x18003f384`
- `MFPlat!MFUnlockWorkQueue` at `0x18003f384`

## pseudocode

```c
void __fastcall MotionTurboJpeg::CMJPGMFT::~CMJPGMFT(MotionTurboJpeg::CMJPGMFT *this)
{
  DWORD v2; // ecx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &MotionTurboJpeg::CMJPGMFT::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &MotionTurboJpeg::CMJPGMFT::`vftable'{for `CMFTBase'};
  *((_QWORD *)this + 11) = &MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFQualityAdvise2'};
  *((_QWORD *)this + 12) = &MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFQualityAdviseLimits'};
  *((_QWORD *)this + 13) = &MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFRateControl'};
  *((_QWORD *)this + 14) = &MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFRateSupport'};
  *((_QWORD *)this + 15) = &MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFGetService'};
  *((_QWORD *)this + 16) = &MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFTelemetryComponent'};
  *((_QWORD *)this + 17) = &MotionTurboJpeg::CMJPGMFT::`vftable'{for `Microsoft::WRL::CloakedIid<IMFRealTimeClientEx>'};
  v2 = *((_DWORD *)this + 72);
  if ( v2 != 5 )
  {
    MFUnlockWorkQueue(v2);
    *((_DWORD *)this + 72) = 5;
  }
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
  if ( v3 )
    (**v3)(v3, 1);
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 5);
  if ( v4 )
    (**v4)(v4, 1);
  if ( (unsigned int)dword_18009C028 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v4,
      qword_180093D58);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 280);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x18003f308  push    rbx
0x18003f30a  sub     rsp, 20h
0x18003f30e  lea     rax, ??_7CMJPGMFT@MotionTurboJpeg@@6BCUnknown@@@; const MotionTurboJpeg::CMJPGMFT::`vftable'{for `CUnknown'}
0x18003f315  mov     rbx, rcx
0x18003f318  mov     [rcx], rax
0x18003f31b  lea     rax, ??_7CMJPGMFT@MotionTurboJpeg@@6BCMFTBase@@@; const MotionTurboJpeg::CMJPGMFT::`vftable'{for `CMFTBase'}
0x18003f322  mov     [rcx+18h], rax
0x18003f326  lea     rax, ??_7CMJPGMFT@MotionTurboJpeg@@6BIMFQualityAdvise2@@@; const MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFQualityAdvise2'}
0x18003f32d  mov     [rcx+58h], rax
0x18003f331  lea     rax, ??_7CMJPGMFT@MotionTurboJpeg@@6BIMFQualityAdviseLimits@@@; const MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFQualityAdviseLimits'}
0x18003f338  mov     [rcx+60h], rax
0x18003f33c  lea     rax, ??_7CMJPGMFT@MotionTurboJpeg@@6BIMFRateControl@@@; const MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFRateControl'}
0x18003f343  mov     [rcx+68h], rax
0x18003f347  lea     rax, ??_7CMJPGMFT@MotionTurboJpeg@@6BIMFRateSupport@@@; const MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFRateSupport'}
0x18003f34e  mov     [rcx+70h], rax
0x18003f352  lea     rax, ??_7CMJPGMFT@MotionTurboJpeg@@6BIMFGetService@@@; const MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFGetService'}
0x18003f359  mov     [rcx+78h], rax
0x18003f35d  lea     rax, ??_7CMJPGMFT@MotionTurboJpeg@@6BIMFTelemetryComponent@@@; const MotionTurboJpeg::CMJPGMFT::`vftable'{for `IMFTelemetryComponent'}
0x18003f364  mov     [rcx+80h], rax
0x18003f36b  lea     rax, ??_7CMJPGMFT@MotionTurboJpeg@@6B?$CloakedIid@UIMFRealTimeClientEx@@@WRL@Microsoft@@@; const MotionTurboJpeg::CMJPGMFT::`vftable'{for `Microsoft::WRL::CloakedIid<IMFRealTimeClientEx>'}
0x18003f372  mov     [rcx+88h], rax
0x18003f379  mov     ecx, [rcx+120h]; dwWorkQueue
0x18003f37f  cmp     ecx, 5
0x18003f382  jz      short loc_18003F394
0x18003f384  call    cs:__imp_MFUnlockWorkQueue
0x18003f38a  mov     dword ptr [rbx+120h], 5
0x18003f394  mov     rcx, [rbx+20h]
0x18003f398  test    rcx, rcx
0x18003f39b  jz      short loc_18003F3AD
0x18003f39d  mov     rax, [rcx]
0x18003f3a0  mov     edx, 1
0x18003f3a5  mov     rax, [rax]
0x18003f3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3ad  mov     rcx, [rbx+28h]
0x18003f3b1  test    rcx, rcx
0x18003f3b4  jz      short loc_18003F3C6
0x18003f3b6  mov     rax, [rcx]
0x18003f3b9  mov     edx, 1
0x18003f3be  mov     rax, [rax]
0x18003f3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3c6  mov     eax, cs:dword_18009C028
0x18003f3cc  cmp     eax, 5
0x18003f3cf  jbe     short loc_18003F3DD
0x18003f3d1  lea     rdx, qword_180093D58
0x18003f3d8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003f3dd  lea     rcx, [rbx+118h]
0x18003f3e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003f3e9  lea     rcx, [rbx+30h]; lpCriticalSection
0x18003f3ed  call    cs:__imp_DeleteCriticalSection
0x18003f3f3  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18003f3fa  add     rsp, 20h
0x18003f3fe  pop     rbx
0x18003f3ff  retn
```

# AudioStateMonitorHelper::RuntimeClassInitialize(ThreadProcHelper *)

- ea: `0x10039550`
- end: `0x1003978e`
- name: `?RuntimeClassInitialize@AudioStateMonitorHelper@@QAGJPAVThreadProcHelper@@@Z`
- size: `574`
- prototype: `int(AudioStateMonitorHelper *__hidden this, struct ThreadProcHelper *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10038410`

## callees

- `0x100075ad`
- `0x1000f598`
- `0x1002d510`
- `0x10037e42`
- `0x10037e8d`
- `0x10038369`
- `0x100387bc`
- `0x10039550`
- `0x1003990a`
- `0x100399ce`
- `0x10039bef`
- `0x1003aba0`
- `0x1003abb4`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x100395f6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x100395f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100395da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100395da`

## pseudocode

```c
int __fastcall AudioStateMonitorHelper::RuntimeClassInitialize(_DWORD *a1, int a2)
{
  int ActivationFactory; // esi
  _DWORD *v4; // ecx
  _DWORD *v5; // ebx
  int v6; // ecx
  int v7; // eax
  int (__thiscall *v8)(_DWORD, _DWORD *, _DWORD *); // esi
  int v9; // esi
  Microsoft::WRL::Details *v11; // [esp+14h] [ebp-48h]
  const char *v12; // [esp+18h] [ebp-44h]
  unsigned int v13; // [esp+1Ch] [ebp-40h]
  _DWORD *v14; // [esp+24h] [ebp-38h] BYREF
  _DWORD *v15; // [esp+28h] [ebp-34h] BYREF
  int v16; // [esp+2Ch] [ebp-30h] BYREF
  int v17; // [esp+30h] [ebp-2Ch] BYREF
  _DWORD v18[2]; // [esp+34h] [ebp-28h] BYREF
  _DWORD *v19; // [esp+3Ch] [ebp-20h]
  HSTRING_HEADER hstringHeader; // [esp+40h] [ebp-1Ch] BYREF
  HSTRING string; // [esp+54h] [ebp-8h] BYREF

  if ( a2 )
  {
    v14 = 0;
    v17 = 0;
    v19 = a1 + 18;
    a1[18] = 0;
    a1[19] = 0;
    wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=(a2);
    v4 = v14;
    v14 = 0;
    if ( v4 )
      (*(void (__thiscall **)(_DWORD, _DWORD *))(*v4 + 8))(*(_DWORD *)(*v4 + 8), v4);
    string = 0;
    if ( WindowsCreateStringReference(L"Windows.Media.Audio.AudioStateMonitor", 0x25u, &hstringHeader, &string) < 0 )
    {
      Microsoft::WRL::Details::RaiseException(v11, (int)v12, v13);
      JUMPOUT(0x1003978E);
    }
    ActivationFactory = RoGetActivationFactory(string, &_GUID_6374ea4c_1b3b_4001_94d9_dd225330fa40, &v14);
    if ( ActivationFactory < 0 )
      goto LABEL_13;
    v5 = a1 + 16;
    v6 = a1[16];
    v15 = v14;
    v7 = *v14;
    a1[16] = 0;
    v8 = *(int (__thiscall **)(_DWORD, _DWORD *, _DWORD *))(v7 + 40);
    v18[0] = v8;
    if ( v6 )
    {
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v6 + 8))(*(_DWORD *)(*(_DWORD *)v6 + 8), v6);
      v8 = (int (__thiscall *)(_DWORD, _DWORD *, _DWORD *))v18[0];
    }
    ActivationFactory = v8(v8, v15, a1 + 16);
    if ( ActivationFactory < 0 )
      goto LABEL_13;
    ActivationFactory = (*(int (__thiscall **)(_DWORD, _DWORD, _DWORD *))(*(_DWORD *)*v5 + 32))(
                          *(_DWORD *)(*(_DWORD *)*v5 + 32),
                          *v5,
                          a1 + 20);
    if ( ActivationFactory < 0 )
      goto LABEL_13;
    if ( !a1[20] )
    {
      ActivationFactory = -1072873822;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\audiostatemonitorhelper.cpp",
        (void *)ActivationFactory,
        (unsigned int)v11,
        v12,
        v13);
LABEL_24:
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v17);
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v14);
      return ActivationFactory;
    }
    ThreadProcHelper::UpdateSoundState(a1[15], a1[20]);
    v16 = 0;
    v15 = a1;
    ActivationFactory = wil::com_weak_query_nothrow<AudioStateMonitorHelper *>(&v15, &v16);
    if ( ActivationFactory >= 0 )
    {
      wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::com_ptr_t<IWeakReference,wil::err_returncode_policy>(&v16);
      v18[1] = a1;
      if ( operator new(0x2Cu, &std::nothrow) )
        v9 = Microsoft::WRL::Details::DelegateArgTraits_long____stdcall_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Media::Audio::AudioStateMonitor___Windows::Media::Audio::IAudioStateMonitor____IInspectable___::___Windows::Media::Audio::IAudioStateMonitor___IInspectable____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::Media::Audio::AudioStateMonitor___IInspectable____Microsoft::WRL::FtmBase___lambda_030c9ede94e1e468de0333a7c0f8c54b___1_Windows::Media::Audio::IAudioStateMonitor___IInspectable___::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::Media::Audio::AudioStateMonitor___IInspectable____Microsoft::WRL::FtmBase___lambda_030c9ede94e1e468de0333a7c0f8c54b___1_Windows::Media::Audio::IAudioStateMonitor___IInspectable___(v18);
      else
        v9 = 0;
      v15 = 0;
      v17 = v9;
      Microsoft::WRL::ComPtr<Windows::Internal::IComPoolTask>::~ComPtr<Windows::Internal::IComPoolTask>(&v15);
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(v18);
      if ( v9 )
      {
        ActivationFactory = (*(int (__thiscall **)(_DWORD, _DWORD, int, _DWORD *))(*(_DWORD *)*v5 + 24))(
                              *(_DWORD *)(*(_DWORD *)*v5 + 24),
                              *v5,
                              v9,
                              v19);
        if ( ActivationFactory >= 0 )
        {
          ActivationFactory = 0;
          goto LABEL_23;
        }
      }
      else
      {
        ActivationFactory = -2147024882;
      }
    }
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\audiostatemonitorhelper.cpp",
      (void *)ActivationFactory,
      (unsigned int)v11,
      v12,
      v13);
LABEL_23:
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v16);
    goto LABEL_24;
  }
  ActivationFactory = -2147024809;
  wil::details::in1diag3::Return_Hr(
    (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\audiostatemonitorhelper.cpp",
    (void *)0x80070057,
    (unsigned int)v11,
    v12,
    v13);
  return ActivationFactory;
}

```

## disassembly

```asm
0x10039550  mov     edi, edi
0x10039552  push    ebp
0x10039553  mov     ebp, esp
0x10039555  and     esp, 0FFFFFFF8h
0x10039558  sub     esp, 3Ch
0x1003955b  mov     eax, ___security_cookie
0x10039560  xor     eax, esp
0x10039562  mov     [esp+3Ch+var_4], eax
0x10039566  push    ebx; unsigned int
0x10039567  push    esi; int
0x10039568  push    edi; this
0x10039569  mov     edi, ecx
0x1003956b  test    edx, edx
0x1003956d  jnz     short loc_1003958A
0x1003956f  mov     ecx, [ebp+4]
0x10039572  mov     esi, 80070057h
0x10039577  push    esi; void *
0x10039578  push    offset aMultimediaDsho_0; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1003957d  push    13h
0x1003957f  pop     edx
0x10039580  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10039585  jmp     loc_10039773
0x1003958a  xor     ebx, ebx
0x1003958c  lea     eax, [edi+48h]
0x1003958f  lea     ecx, [edi+3Ch]
0x10039592  mov     [esp+48h+var_38], ebx
0x10039596  push    edx
0x10039597  mov     [esp+4Ch+var_2C], ebx
0x1003959b  mov     [esp+4Ch+var_20], eax
0x1003959f  mov     [eax], ebx
0x100395a1  mov     [eax+4], ebx
0x100395a4  call    ??4?$com_ptr_t@VThreadProcHelper@@Uerr_returncode_policy@wil@@@wil@@QAEAAV01@PAVThreadProcHelper@@@Z; wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=(ThreadProcHelper *)
0x100395a9  mov     ecx, [esp+48h+var_38]
0x100395ad  mov     [esp+48h+var_38], ebx
0x100395b1  test    ecx, ecx
0x100395b3  jz      short loc_100395C5
0x100395b5  mov     eax, [ecx]
0x100395b7  push    ecx
0x100395b8  mov     esi, [eax+8]
0x100395bb  mov     ecx, esi; this
0x100395bd  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100395c3  call    esi
0x100395c5  lea     eax, [esp+48h+string]
0x100395c9  mov     [esp+48h+string], ebx
0x100395cd  push    eax; string
0x100395ce  lea     eax, [esp+4Ch+hstringHeader]
0x100395d2  push    eax; hstringHeader
0x100395d3  push    25h ; '%'; length
0x100395d5  push    offset ?RuntimeClass_Windows_Media_Audio_AudioStateMonitor@@3QBGB; "Windows.Media.Audio.AudioStateMonitor"
0x100395da  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100395e0  test    eax, eax
0x100395e2  js      loc_10039787
0x100395e8  lea     eax, [esp+48h+var_38]
0x100395ec  push    eax
0x100395ed  push    offset __GUID_6374ea4c_1b3b_4001_94d9_dd225330fa40
0x100395f2  push    [esp+50h+string]
0x100395f6  call    ds:__imp__RoGetActivationFactory@12; RoGetActivationFactory(x,x,x)
0x100395fc  mov     esi, eax
0x100395fe  test    esi, esi
0x10039600  jns     short loc_10039606
0x10039602  push    1Ch
0x10039604  jmp     short loc_10039680
0x10039606  mov     eax, [esp+48h+var_38]
0x1003960a  lea     ebx, [edi+40h]
0x1003960d  mov     ecx, [ebx]
0x1003960f  mov     [esp+48h+var_34], eax
0x10039613  mov     eax, [eax]
0x10039615  mov     dword ptr [ebx], 0
0x1003961b  mov     esi, [eax+28h]
0x1003961e  mov     [esp+48h+var_28], esi
0x10039622  test    ecx, ecx
0x10039624  jz      short loc_1003963A
0x10039626  mov     eax, [ecx]
0x10039628  push    ecx
0x10039629  mov     esi, [eax+8]
0x1003962c  mov     ecx, esi; this
0x1003962e  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10039634  call    esi
0x10039636  mov     esi, [esp+48h+var_28]
0x1003963a  push    ebx
0x1003963b  push    [esp+4Ch+var_34]
0x1003963f  mov     ecx, esi; this
0x10039641  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10039647  call    esi
0x10039649  mov     esi, eax
0x1003964b  test    esi, esi
0x1003964d  jns     short loc_10039653
0x1003964f  push    1Eh
0x10039651  jmp     short loc_10039680
0x10039653  mov     ecx, [ebx]
0x10039655  mov     eax, [ecx]
0x10039657  mov     esi, [eax+20h]
0x1003965a  lea     eax, [edi+50h]
0x1003965d  push    eax
0x1003965e  push    ecx
0x1003965f  mov     ecx, esi; this
0x10039661  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10039667  call    esi
0x10039669  mov     esi, eax
0x1003966b  test    esi, esi
0x1003966d  jns     short loc_10039673
0x1003966f  push    21h ; '!'
0x10039671  jmp     short loc_10039680
0x10039673  cmp     dword ptr [edi+50h], 0
0x10039677  jnz     short loc_10039694
0x10039679  mov     esi, 0C00D3EA2h
0x1003967e  push    22h ; '"'
0x10039680  mov     ecx, [ebp+4]
0x10039683  pop     edx
0x10039684  push    esi; void *
0x10039685  push    offset aMultimediaDsho_0; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1003968a  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1003968f  jmp     loc_10039761
0x10039694  push    dword ptr [edi+50h]
0x10039697  mov     ecx, [edi+3Ch]
0x1003969a  call    ?UpdateSoundState@ThreadProcHelper@@QAEXW4SoundLevel@Media@Windows@@@Z; ThreadProcHelper::UpdateSoundState(Windows::Media::SoundLevel)
0x1003969f  lea     edx, [esp+48h+var_30]
0x100396a3  mov     [esp+48h+var_30], 0
0x100396ab  lea     ecx, [esp+48h+var_34]
0x100396af  mov     [esp+48h+var_34], edi
0x100396b3  call    ??$com_weak_query_nothrow@PAVAudioStateMonitorHelper@@@wil@@YGJ$$QAPAVAudioStateMonitorHelper@@PAPAUIWeakReference@@@Z; wil::com_weak_query_nothrow<AudioStateMonitorHelper *>(AudioStateMonitorHelper * &&,IWeakReference * *)
0x100396b8  mov     esi, eax
0x100396ba  test    esi, esi
0x100396bc  jns     short loc_100396C5
0x100396be  push    2Bh ; '+'
0x100396c0  jmp     loc_10039745
0x100396c5  lea     eax, [esp+48h+var_30]
0x100396c9  push    eax
0x100396ca  lea     ecx, [esp+4Ch+var_28]
0x100396ce  call    ??0?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QAE@ABV01@@Z; wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::com_ptr_t<IWeakReference,wil::err_returncode_policy>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> const &)
0x100396d3  push    offset ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x100396d8  push    2Ch ; ','; Size
0x100396da  mov     [esp+50h+var_24], edi
0x100396de  call    ??2@YAPAXIABUnothrow_t@std@@@Z; operator new(uint,std::nothrow_t const &)
0x100396e3  pop     ecx
0x100396e4  pop     ecx
0x100396e5  test    eax, eax
0x100396e7  jz      short loc_100396F9
0x100396e9  lea     ecx, [esp+48h+var_28]
0x100396ed  push    ecx
0x100396ee  mov     ecx, eax
0x100396f0  call    Microsoft__WRL__Details__DelegateArgTraits_long____stdcall_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Media__Audio__AudioStateMonitor___Windows__Media__Audio__IAudioStateMonitor____IInspectable________Windows__Media__Audio__IAudioStateMonitor___IInspectable______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__ITypedEventHandler_Windows__Media__Audio__AudioStateMonitor___IInspectable____Microsoft__WRL__FtmBase___lambda_030c9ede94e1e468de0333a7c0f8c54b___1_Windows__Media__Audio__IAudioStateMonitor___IInspectable_____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__ITypedEventHandler_Windows__Media__Audio__AudioStateMonitor___IInspectable____Microsoft__WRL__FtmBase___lambda_030c9ede94e1e468de0333a7c0f8c54b___1_Windows__Media__Audio__IAudioStateMonitor___IInspectable___
0x100396f5  mov     esi, eax
0x100396f7  jmp     short loc_100396FB
0x100396f9  xor     esi, esi
0x100396fb  lea     ecx, [esp+48h+var_34]
0x100396ff  mov     [esp+48h+var_34], 0
0x10039707  mov     [esp+48h+var_2C], esi
0x1003970b  call    ??1?$ComPtr@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::ComPtr<Windows::Internal::IComPoolTask>::~ComPtr<Windows::Internal::IComPoolTask>(void)
0x10039710  lea     ecx, [esp+48h+var_28]
0x10039714  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10039719  test    esi, esi
0x1003971b  jnz     short loc_10039726
0x1003971d  mov     esi, 8007000Eh
0x10039722  push    43h ; 'C'
0x10039724  jmp     short loc_10039745
0x10039726  mov     ecx, [ebx]
0x10039728  push    [esp+48h+var_20]
0x1003972c  push    esi
0x1003972d  mov     eax, [ecx]
0x1003972f  push    ecx
0x10039730  mov     edi, [eax+18h]
0x10039733  mov     ecx, edi; this
0x10039735  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003973b  call    edi
0x1003973d  mov     esi, eax
0x1003973f  test    esi, esi
0x10039741  jns     short loc_10039756
0x10039743  push    45h ; 'E'
0x10039745  mov     ecx, [ebp+4]
0x10039748  pop     edx
0x10039749  push    esi; void *
0x1003974a  push    offset aMultimediaDsho_0; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1003974f  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10039754  jmp     short loc_10039758
0x10039756  xor     esi, esi
0x10039758  lea     ecx, [esp+48h+var_30]
0x1003975c  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10039761  lea     ecx, [esp+48h+var_2C]
0x10039765  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x1003976a  lea     ecx, [esp+48h+var_38]
0x1003976e  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10039773  mov     ecx, [esp+48h+var_4]
0x10039777  mov     eax, esi
0x10039779  pop     edi
0x1003977a  pop     esi
0x1003977b  pop     ebx
0x1003977c  xor     ecx, esp; StackCookie
0x1003977e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10039783  mov     esp, ebp
0x10039785  pop     ebp
0x10039786  retn
0x10039787  mov     ecx, eax
0x10039789  call    ?RaiseException@Details@WRL@Microsoft@@YGXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

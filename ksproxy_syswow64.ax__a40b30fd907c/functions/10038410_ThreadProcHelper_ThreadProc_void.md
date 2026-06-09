# ThreadProcHelper::ThreadProc(void *)

- ea: `0x10038410`
- end: `0x1003860d`
- name: `?ThreadProc@ThreadProcHelper@@CGKPAX@Z`
- size: `509`
- prototype: `int __stdcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x100075ad`
- `0x1000f598`
- `0x1002d510`
- `0x10038410`
- `0x10038614`
- `0x100386a2`
- `0x1003872f`
- `0x10038893`
- `0x10039040`
- `0x100390ca`
- `0x10039210`
- `0x10039359`
- `0x1003937f`
- `0x10039550`
- `0x10039e3c`
- `0x1003abb4`

## import_xrefs

- `ole32!CoUninitialize` at `0x100385eb`
- `ole32!CoUninitialize` at `0x100385eb`
- `ole32!CoInitializeEx` at `0x1003841f`
- `ole32!CoInitializeEx` at `0x1003841f`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x100385b4`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x100385b4`

## string_xrefs

- `0x1003859b`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
int __stdcall ThreadProcHelper::ThreadProc(_DWORD *Parameter)
{
  void *v1; // eax
  wil::details::in1diag3 *v2; // ecx
  AudioStateMonitorHelper *v3; // eax
  int v4; // esi
  AudioStateMonitorHelper *v5; // edi
  int v6; // ebx
  int v7; // ecx
  CapabilityAccessHelper *v8; // eax
  void *v10; // [esp+0h] [ebp-30h]
  char *v11; // [esp+4h] [ebp-2Ch]
  const char *v12; // [esp+8h] [ebp-28h]
  _DWORD v13[4]; // [esp+Ch] [ebp-24h] BYREF
  char v14; // [esp+1Ch] [ebp-14h]
  int v15; // [esp+20h] [ebp-10h] BYREF
  int v16; // [esp+24h] [ebp-Ch] BYREF
  int v17; // [esp+28h] [ebp-8h] BYREF
  _DWORD *v18; // [esp+2Ch] [ebp-4h] BYREF
  int retaddr; // [esp+34h] [ebp+4h]

  v1 = (void *)CoInitializeEx(0, 0);
  if ( (int)v1 < 0 )
    wil::details::in1diag3::_FailFast_Hr(v2, v1, (unsigned int)v10, v11, (int)v12);
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = Parameter;
  if ( !Parameter )
    wil::details::in1diag3::_FailFast_Unexpected(0, v10, (unsigned int)v11, v12);
  (*(void (__thiscall **)(_DWORD, _DWORD *))(*Parameter + 4))(*(_DWORD *)(*Parameter + 4), Parameter);
  v13[0] = &v15;
  v13[1] = &v18;
  v13[2] = &v17;
  v13[3] = &v16;
  v16 = 0;
  v3 = (AudioStateMonitorHelper *)operator new(0x58u, &std::nothrow);
  if ( v3 )
  {
    v5 = AudioStateMonitorHelper::AudioStateMonitorHelper(v3);
    v4 = AudioStateMonitorHelper::RuntimeClassInitialize((AudioStateMonitorHelper *)v10, (struct ThreadProcHelper *)v11);
    if ( v4 < 0 )
    {
      if ( !v5 )
        goto LABEL_23;
      goto LABEL_19;
    }
    v4 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>>(
           v5,
           &_GUID_91699f56_52b5_4f6c_8e19_4ec35f8818c3,
           &v16);
    if ( v5 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::Release(v5);
    if ( v4 < 0 )
      goto LABEL_23;
    v6 = (int)v18;
    if ( v18[14] == 1 )
    {
      v7 = v17;
      v17 = 0;
      if ( v7 )
        (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v7 + 8))(*(_DWORD *)(*(_DWORD *)v7 + 8), v7);
      v17 = 0;
      v8 = (CapabilityAccessHelper *)operator new(0x58u, &std::nothrow);
      if ( !v8 )
      {
        v4 = -2147024882;
        goto LABEL_23;
      }
      v5 = CapabilityAccessHelper::CapabilityAccessHelper(v8);
      v4 = CapabilityAccessHelper::RuntimeClassInitialize((CapabilityAccessHelper *)v10, (struct ThreadProcHelper *)v11);
      if ( v4 < 0 )
      {
        if ( !v5 )
          goto LABEL_23;
LABEL_19:
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::Release(v5);
        goto LABEL_23;
      }
      v4 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>>(
             v5,
             &_GUID_9afc28bc_2422_4a0c_8b57_87ec171ec5e5,
             &v17);
      if ( v5 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::Release(v5);
      if ( v4 < 0 )
        goto LABEL_23;
      v6 = (int)v18;
    }
    *(_DWORD *)(v6 + 8) = 1;
    WakeByAddressAll((PVOID)(v6 + 8));
    wil::slim_event_t<0>::wait((unsigned int)(v18 + 3));
    v4 = 0;
    goto LABEL_26;
  }
  v4 = -2147024882;
LABEL_23:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
    (void *)v4,
    (unsigned int)v10,
    v11,
    (int)v12);
LABEL_26:
  v14 = 0;
  lambda_fda4b39d4802b530115b2c69e4681f8e_::operator()(v13);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>((int *)&v18);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v17);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v16);
  CoUninitialize();
  return v4;
}

```

## disassembly

```asm
0x10038410  mov     edi, edi
0x10038412  push    ebp
0x10038413  mov     ebp, esp
0x10038415  sub     esp, 24h
0x10038418  push    ebx; int
0x10038419  push    esi; char *
0x1003841a  push    edi; unsigned int
0x1003841b  xor     ebx, ebx
0x1003841d  push    ebx; dwCoInit
0x1003841e  push    ebx; pvReserved
0x1003841f  call    ds:__imp__CoInitializeEx@8; CoInitializeEx(x,x)
0x10038425  test    eax, eax
0x10038427  js      loc_10038603
0x1003842d  mov     ecx, [ebp+Parameter]
0x10038430  mov     [ebp+var_10], ebx
0x10038433  mov     [ebp+var_C], ebx
0x10038436  mov     [ebp+var_8], ebx
0x10038439  mov     [ebp+var_4], ecx
0x1003843c  test    ecx, ecx
0x1003843e  jz      loc_100385FA
0x10038444  mov     eax, [ecx]
0x10038446  push    ecx
0x10038447  mov     esi, [eax+4]
0x1003844a  mov     ecx, esi; this
0x1003844c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10038452  call    esi
0x10038454  mov     ebx, [ebp+var_4]
0x10038457  test    ebx, ebx
0x10038459  jz      loc_100385FA
0x1003845f  mov     ecx, [ebp+var_C]
0x10038462  lea     eax, [ebp+var_10]
0x10038465  mov     [ebp+var_24], eax
0x10038468  lea     eax, [ebp+var_4]
0x1003846b  mov     [ebp+var_20], eax
0x1003846e  lea     eax, [ebp+var_8]
0x10038471  mov     [ebp+var_1C], eax
0x10038474  lea     eax, [ebp+var_C]
0x10038477  mov     [ebp+var_18], eax
0x1003847a  mov     [ebp+var_C], 0
0x10038481  test    ecx, ecx
0x10038483  jz      short loc_10038495
0x10038485  mov     eax, [ecx]
0x10038487  push    ecx
0x10038488  mov     esi, [eax+8]
0x1003848b  mov     ecx, esi; this
0x1003848d  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10038493  call    esi
0x10038495  push    offset ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1003849a  push    58h ; 'X'; Size
0x1003849c  mov     [ebp+var_C], 0
0x100384a3  call    ??2@YAPAXIABUnothrow_t@std@@@Z; operator new(uint,std::nothrow_t const &)
0x100384a8  pop     ecx
0x100384a9  pop     ecx
0x100384aa  test    eax, eax
0x100384ac  jnz     short loc_100384B5
0x100384ae  mov     esi, 8007000Eh
0x100384b3  jmp     short loc_100384F9
0x100384b5  mov     ecx, eax; this
0x100384b7  call    ??0AudioStateMonitorHelper@@QAE@XZ; AudioStateMonitorHelper::AudioStateMonitorHelper(void)
0x100384bc  mov     edi, eax
0x100384be  mov     edx, ebx
0x100384c0  mov     ecx, edi
0x100384c2  call    ?RuntimeClassInitialize@AudioStateMonitorHelper@@QAGJPAVThreadProcHelper@@@Z; AudioStateMonitorHelper::RuntimeClassInitialize(ThreadProcHelper *)
0x100384c7  mov     esi, eax
0x100384c9  test    esi, esi
0x100384cb  jns     short loc_100384D9
0x100384cd  test    edi, edi
0x100384cf  jz      short loc_100384F9
0x100384d1  push    edi
0x100384d2  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UAGKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::Release(void)
0x100384d7  jmp     short loc_100384F9
0x100384d9  lea     eax, [ebp+var_C]
0x100384dc  mov     edx, offset __GUID_91699f56_52b5_4f6c_8e19_4ec35f8818c3
0x100384e1  push    eax
0x100384e2  mov     ecx, edi
0x100384e4  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAudioStateMonitorHelper@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAudioStateMonitorHelper@@VFtmBase@23@@123@ABU_GUID@@PAPAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x100384e9  mov     esi, eax
0x100384eb  test    edi, edi
0x100384ed  jz      short loc_100384F5
0x100384ef  push    edi
0x100384f0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UAGKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::Release(void)
0x100384f5  test    esi, esi
0x100384f7  jns     short loc_10038503
0x100384f9  mov     edx, 110h
0x100384fe  jmp     loc_10038597
0x10038503  mov     ebx, [ebp+var_4]
0x10038506  cmp     dword ptr [ebx+38h], 1
0x1003850a  jnz     loc_100385AA
0x10038510  mov     ecx, [ebp+var_8]
0x10038513  mov     [ebp+var_8], 0
0x1003851a  test    ecx, ecx
0x1003851c  jz      short loc_1003852E
0x1003851e  mov     eax, [ecx]
0x10038520  push    ecx
0x10038521  mov     esi, [eax+8]
0x10038524  mov     ecx, esi; this
0x10038526  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003852c  call    esi
0x1003852e  push    offset ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x10038533  push    58h ; 'X'; Size
0x10038535  mov     [ebp+var_8], 0
0x1003853c  call    ??2@YAPAXIABUnothrow_t@std@@@Z; operator new(uint,std::nothrow_t const &)
0x10038541  pop     ecx
0x10038542  pop     ecx
0x10038543  test    eax, eax
0x10038545  jnz     short loc_1003854E
0x10038547  mov     esi, 8007000Eh
0x1003854c  jmp     short loc_10038592
0x1003854e  mov     ecx, eax; this
0x10038550  call    ??0CapabilityAccessHelper@@QAE@XZ; CapabilityAccessHelper::CapabilityAccessHelper(void)
0x10038555  mov     edi, eax
0x10038557  mov     edx, ebx
0x10038559  mov     ecx, edi
0x1003855b  call    ?RuntimeClassInitialize@CapabilityAccessHelper@@QAGJPAVThreadProcHelper@@@Z; CapabilityAccessHelper::RuntimeClassInitialize(ThreadProcHelper *)
0x10038560  mov     esi, eax
0x10038562  test    esi, esi
0x10038564  jns     short loc_10038572
0x10038566  test    edi, edi
0x10038568  jz      short loc_10038592
0x1003856a  push    edi
0x1003856b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UAGKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::Release(void)
0x10038570  jmp     short loc_10038592
0x10038572  lea     eax, [ebp+var_8]
0x10038575  mov     edx, offset __GUID_9afc28bc_2422_4a0c_8b57_87ec171ec5e5
0x1003857a  push    eax
0x1003857b  mov     ecx, edi
0x1003857d  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@123@ABU_GUID@@PAPAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x10038582  mov     esi, eax
0x10038584  test    edi, edi
0x10038586  jz      short loc_1003858E
0x10038588  push    edi
0x10038589  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UAGKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::Release(void)
0x1003858e  test    esi, esi
0x10038590  jns     short loc_100385A7
0x10038592  mov     edx, 115h
0x10038597  mov     ecx, [ebp+4]
0x1003859a  push    esi; void *
0x1003859b  push    offset aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x100385a0  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x100385a5  jmp     short loc_100385C7
0x100385a7  mov     ebx, [ebp+var_4]
0x100385aa  lea     eax, [ebx+8]
0x100385ad  push    eax; Address
0x100385ae  mov     dword ptr [eax], 1
0x100385b4  call    ds:__imp__WakeByAddressAll@4; WakeByAddressAll(x)
0x100385ba  mov     ecx, [ebp+var_4]
0x100385bd  lea     ecx, [ecx+0Ch]; unsigned int
0x100385c0  call    ?wait@?$slim_event_t@$0A@@wil@@QAE_NXZ; wil::slim_event_t<0>::wait(void)
0x100385c5  xor     esi, esi
0x100385c7  lea     ecx, [ebp+var_24]
0x100385ca  mov     [ebp+var_14], 0
0x100385ce  call    _lambda_fda4b39d4802b530115b2c69e4681f8e___operator__
0x100385d3  lea     ecx, [ebp+var_4]
0x100385d6  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x100385db  lea     ecx, [ebp+var_8]
0x100385de  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x100385e3  lea     ecx, [ebp+var_C]
0x100385e6  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x100385eb  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x100385f1  pop     edi
0x100385f2  mov     eax, esi
0x100385f4  pop     esi
0x100385f5  pop     ebx
0x100385f6  leave
0x100385f7  retn    4
0x100385fa  push    ecx; this
0x100385fb  mov     ecx, [ebp+4]
0x100385fe  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x10038603  push    eax; void *
0x10038604  push    ecx; this
0x10038605  mov     ecx, [ebp+4]
0x10038608  call    ?_FailFast_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```

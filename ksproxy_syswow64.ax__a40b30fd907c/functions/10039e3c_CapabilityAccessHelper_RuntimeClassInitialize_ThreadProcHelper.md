# CapabilityAccessHelper::RuntimeClassInitialize(ThreadProcHelper *)

- ea: `0x10039e3c`
- end: `0x1003a0b6`
- name: `?RuntimeClassInitialize@CapabilityAccessHelper@@QAGJPAVThreadProcHelper@@@Z`
- size: `634`
- prototype: `int __fastcall(int *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10038410`

## callees

- `0x100075ad`
- `0x1000f598`
- `0x1002d510`
- `0x10037e42`
- `0x10037e8d`
- `0x100383b7`
- `0x100387bc`
- `0x100399ce`
- `0x10039e3c`
- `0x1003a20a`
- `0x1003a3ad`
- `0x1003aba0`
- `0x1003abb4`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x10039ee6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x10039ee6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x10039eca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x10039f49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x10039eca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x10039f49`

## string_xrefs

- `0x10039ec5`: `Windows.Security.Authorization.AppCapabilityAccess.AppCapability`
- `0x10039e66`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\capabilityaccesshelper.cpp`
- `0x10039fab`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\capabilityaccesshelper.cpp`
- `0x1003a072`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\capabilityaccesshelper.cpp`

## pseudocode

```c
int __fastcall CapabilityAccessHelper::RuntimeClassInitialize(int *a1, int a2)
{
  int ActivationFactory; // esi
  int v5; // ecx
  void *v6; // eax
  int *v7; // esi
  int v8; // ecx
  int v9; // eax
  int (__thiscall *v10)(_DWORD, int, int *); // ecx
  int v11; // esi
  unsigned int v13; // [esp+1Ch] [ebp-48h]
  const char *v14; // [esp+20h] [ebp-44h]
  int v15; // [esp+24h] [ebp-40h]
  int *v16; // [esp+28h] [ebp-3Ch] BYREF
  CD3DSurfaceAllocator *v17; // [esp+2Ch] [ebp-38h] BYREF
  int v18; // [esp+30h] [ebp-34h] BYREF
  int v19; // [esp+34h] [ebp-30h] BYREF
  int v20[2]; // [esp+38h] [ebp-2Ch] BYREF
  _DWORD *v21; // [esp+40h] [ebp-24h]
  int *v22; // [esp+44h] [ebp-20h]
  HSTRING_HEADER hstringHeader; // [esp+48h] [ebp-1Ch] BYREF
  HSTRING string; // [esp+5Ch] [ebp-8h] BYREF
  int retaddr; // [esp+68h] [ebp+4h]

  if ( a2 )
  {
    v16 = 0;
    v19 = 0;
    v22 = a1 + 18;
    a1[18] = 0;
    a1[19] = 0;
    wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=(a1 + 15, a2);
    v5 = (int)v16;
    v16 = 0;
    if ( v5 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v5 + 8))(*(_DWORD *)(*(_DWORD *)v5 + 8), v5);
    string = 0;
    v6 = (void *)WindowsCreateStringReference(
                   L"Windows.Security.Authorization.AppCapabilityAccess.AppCapability",
                   0x40u,
                   &hstringHeader,
                   &string);
    if ( (int)v6 < 0 )
      goto LABEL_27;
    ActivationFactory = RoGetActivationFactory(string, &_GUID_7c353e2a_46ee_44e5_af3d_6ad3fc49bd22, &v16);
    if ( ActivationFactory < 0 )
    {
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityaccesshelper.cpp",
        (void *)ActivationFactory,
        v13,
        v14,
        v15);
LABEL_25:
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v19);
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>((int *)&v16);
      return ActivationFactory;
    }
    v7 = a1 + 16;
    v8 = a1[16];
    v20[0] = (int)v16;
    v21 = a1 + 16;
    v9 = *v16;
    a1[16] = 0;
    v17 = *(CD3DSurfaceAllocator **)(v9 + 32);
    if ( v8 )
    {
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v8 + 8))(*(_DWORD *)(*(_DWORD *)v8 + 8), v8);
      v7 = a1 + 16;
    }
    string = 0;
    v6 = (void *)WindowsCreateStringReference(L"webcam", 6u, &hstringHeader, &string);
    if ( (int)v6 < 0 )
    {
LABEL_27:
      Microsoft::WRL::Details::RaiseException(v6);
      JUMPOUT(0x1003A0B6);
    }
    ActivationFactory = ((int (__thiscall *)(CD3DSurfaceAllocator *, int, HSTRING, int *))v17)(v17, v20[0], string, v7);
    if ( ActivationFactory < 0 )
      goto LABEL_14;
    v10 = *(int (__thiscall **)(_DWORD, int, int *))(*(_DWORD *)a1[16] + 36);
    ActivationFactory = v10(v10, a1[16], a1 + 20);
    if ( ActivationFactory < 0 )
      goto LABEL_14;
    if ( a1[20] != 4 )
    {
      ActivationFactory = -2147024891;
      goto LABEL_14;
    }
    ThreadProcHelper::UpdateCapabilityState(a2, 4);
    v18 = 0;
    v17 = (CD3DSurfaceAllocator *)a1;
    ActivationFactory = wil::com_weak_query_nothrow<CapabilityAccessHelper *>(&v17, &v18);
    if ( ActivationFactory >= 0 )
    {
      wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::com_ptr_t<IWeakReference,wil::err_returncode_policy>(
        v20,
        &v18);
      v20[1] = (int)a1;
      if ( operator new(0x2Cu, &std::nothrow) )
        v11 = Microsoft::WRL::Details::DelegateArgTraits_long____stdcall_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Security::Authorization::AppCapabilityAccess::AppCapability___Windows::Security::Authorization::AppCapabilityAccess::IAppCapability____Windows::Foundation::Internal::AggregateType_Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs___Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityAccessChangedEventArgs_____::___Windows::Security::Authorization::AppCapabilityAccess::IAppCapability___Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityAccessChangedEventArgs____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::Security::Authorization::AppCapabilityAccess::AppCapability___Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs____Microsoft::WRL::FtmBase___lambda_b0cc0fcdbf1cd0d9c171f1d8c9b18ade___1_Windows::Security::Authorization::AppCapabilityAccess::IAppCapability___Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityAccessChangedEventArgs___::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::Security::Authorization::AppCapabilityAccess::AppCapability___Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs____Microsoft::WRL::FtmBase___lambda_b0cc0fcdbf1cd0d9c171f1d8c9b18ade___1_Windows::Security::Authorization::AppCapabilityAccess::IAppCapability___Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityAccessChangedEventArgs___(v20);
      else
        v11 = 0;
      v17 = 0;
      v19 = v11;
      Microsoft::WRL::ComPtr<Windows::Internal::IComPoolTask>::~ComPtr<Windows::Internal::IComPoolTask>((int *)&v17);
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(v20);
      if ( v11 )
      {
        ActivationFactory = (*(int (__thiscall **)(_DWORD, _DWORD, int, int *))(*(_DWORD *)*v21 + 40))(
                              *(_DWORD *)(*(_DWORD *)*v21 + 40),
                              *v21,
                              v11,
                              v22);
        if ( ActivationFactory >= 0 )
        {
          ActivationFactory = 0;
          goto LABEL_24;
        }
      }
      else
      {
        ActivationFactory = -2147024882;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityaccesshelper.cpp",
      (void *)ActivationFactory,
      v13,
      v14,
      v15);
LABEL_24:
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v18);
    goto LABEL_25;
  }
  ActivationFactory = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityaccesshelper.cpp",
    (void *)0x80070057,
    v13,
    v14,
    v15);
  return ActivationFactory;
}

```

## disassembly

```asm
0x10039e3c  mov     edi, edi
0x10039e3e  push    ebp
0x10039e3f  mov     ebp, esp
0x10039e41  and     esp, 0FFFFFFF8h
0x10039e44  sub     esp, 3Ch
0x10039e47  mov     eax, ___security_cookie
0x10039e4c  xor     eax, esp
0x10039e4e  mov     [esp+3Ch+var_4], eax
0x10039e52  push    ebx; unsigned int
0x10039e53  push    esi; int
0x10039e54  mov     ebx, edx
0x10039e56  push    edi; this
0x10039e57  mov     edi, ecx
0x10039e59  test    ebx, ebx
0x10039e5b  jnz     short loc_10039E78
0x10039e5d  mov     ecx, [ebp+4]
0x10039e60  mov     esi, 80070057h
0x10039e65  push    esi; void *
0x10039e66  push    offset aMultimediaDsho_4; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10039e6b  push    15h
0x10039e6d  pop     edx
0x10039e6e  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10039e73  jmp     loc_1003A09B
0x10039e78  xor     esi, esi
0x10039e7a  lea     eax, [edi+48h]
0x10039e7d  push    ebx
0x10039e7e  lea     ecx, [edi+3Ch]
0x10039e81  mov     [esp+4Ch+var_3C], esi
0x10039e85  mov     [esp+4Ch+var_30], esi
0x10039e89  mov     [esp+4Ch+var_20], eax
0x10039e8d  mov     [eax], esi
0x10039e8f  mov     [eax+4], esi
0x10039e92  call    ??4?$com_ptr_t@VThreadProcHelper@@Uerr_returncode_policy@wil@@@wil@@QAEAAV01@PAVThreadProcHelper@@@Z; wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=(ThreadProcHelper *)
0x10039e97  mov     ecx, [esp+48h+var_3C]
0x10039e9b  mov     [esp+48h+var_3C], esi
0x10039e9f  test    ecx, ecx
0x10039ea1  jz      short loc_10039EB5
0x10039ea3  mov     eax, [ecx]
0x10039ea5  push    ecx
0x10039ea6  mov     esi, [eax+8]
0x10039ea9  mov     ecx, esi; this
0x10039eab  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10039eb1  call    esi
0x10039eb3  xor     esi, esi
0x10039eb5  lea     eax, [esp+48h+string]
0x10039eb9  mov     [esp+48h+string], esi
0x10039ebd  push    eax; string
0x10039ebe  lea     eax, [esp+4Ch+hstringHeader]
0x10039ec2  push    eax; hstringHeader
0x10039ec3  push    40h ; '@'; length
0x10039ec5  push    offset ?RuntimeClass_Windows_Security_Authorization_AppCapabilityAccess_AppCapability@@3QBGB; "Windows.Security.Authorization.AppCapab"...
0x10039eca  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x10039ed0  test    eax, eax
0x10039ed2  js      loc_1003A0AF
0x10039ed8  lea     eax, [esp+48h+var_3C]
0x10039edc  push    eax
0x10039edd  push    offset __GUID_7c353e2a_46ee_44e5_af3d_6ad3fc49bd22
0x10039ee2  push    [esp+50h+string]
0x10039ee6  call    ds:__imp__RoGetActivationFactory@12; RoGetActivationFactory(x,x,x)
0x10039eec  mov     esi, eax
0x10039eee  test    esi, esi
0x10039ef0  jns     short loc_10039EF9
0x10039ef2  push    1Eh
0x10039ef4  jmp     loc_10039FA6
0x10039ef9  mov     eax, [esp+48h+var_3C]
0x10039efd  lea     esi, [edi+40h]
0x10039f00  mov     ecx, [esi]
0x10039f02  mov     [esp+48h+var_2C], eax
0x10039f06  mov     [esp+48h+var_24], esi
0x10039f0a  mov     eax, [eax]
0x10039f0c  mov     dword ptr [esi], 0
0x10039f12  mov     eax, [eax+20h]
0x10039f15  mov     [esp+48h+var_38], eax
0x10039f19  test    ecx, ecx
0x10039f1b  jz      short loc_10039F30
0x10039f1d  mov     eax, [ecx]
0x10039f1f  push    ecx
0x10039f20  mov     esi, [eax+8]
0x10039f23  mov     ecx, esi; this
0x10039f25  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10039f2b  call    esi
0x10039f2d  lea     esi, [edi+40h]
0x10039f30  lea     eax, [esp+48h+string]
0x10039f34  mov     [esp+48h+string], 0
0x10039f3c  push    eax; string
0x10039f3d  lea     eax, [esp+4Ch+hstringHeader]
0x10039f41  push    eax; hstringHeader
0x10039f42  push    6; length
0x10039f44  push    offset sourceString; "webcam"
0x10039f49  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x10039f4f  test    eax, eax
0x10039f51  js      loc_1003A0AF
0x10039f57  push    esi
0x10039f58  push    [esp+4Ch+string]
0x10039f5c  mov     esi, [esp+50h+var_38]
0x10039f60  mov     ecx, esi; this
0x10039f62  push    [esp+50h+var_2C]
0x10039f66  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10039f6c  call    esi
0x10039f6e  mov     esi, eax
0x10039f70  test    esi, esi
0x10039f72  jns     short loc_10039F78
0x10039f74  push    20h ; ' '
0x10039f76  jmp     short loc_10039FA6
0x10039f78  mov     ecx, [edi+40h]
0x10039f7b  mov     eax, [ecx]
0x10039f7d  mov     esi, [eax+24h]
0x10039f80  lea     eax, [edi+50h]
0x10039f83  push    eax
0x10039f84  push    ecx
0x10039f85  mov     ecx, esi; this
0x10039f87  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10039f8d  call    esi
0x10039f8f  mov     esi, eax
0x10039f91  test    esi, esi
0x10039f93  jns     short loc_10039F99
0x10039f95  push    23h ; '#'
0x10039f97  jmp     short loc_10039FA6
0x10039f99  cmp     dword ptr [edi+50h], 4
0x10039f9d  jz      short loc_10039FBA
0x10039f9f  mov     esi, 80070005h
0x10039fa4  push    24h ; '$'
0x10039fa6  mov     ecx, [ebp+4]
0x10039fa9  pop     edx
0x10039faa  push    esi; void *
0x10039fab  push    offset aMultimediaDsho_4; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10039fb0  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10039fb5  jmp     loc_1003A089
0x10039fba  push    4
0x10039fbc  mov     ecx, ebx
0x10039fbe  call    ?UpdateCapabilityState@ThreadProcHelper@@QAEXW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Z; ThreadProcHelper::UpdateCapabilityState(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus)
0x10039fc3  lea     edx, [esp+48h+var_34]
0x10039fc7  mov     [esp+48h+var_34], 0
0x10039fcf  lea     ecx, [esp+48h+var_38]
0x10039fd3  mov     [esp+48h+var_38], edi
0x10039fd7  call    ??$com_weak_query_nothrow@PAVCapabilityAccessHelper@@@wil@@YGJ$$QAPAVCapabilityAccessHelper@@PAPAUIWeakReference@@@Z; wil::com_weak_query_nothrow<CapabilityAccessHelper *>(CapabilityAccessHelper * &&,IWeakReference * *)
0x10039fdc  mov     esi, eax
0x10039fde  test    esi, esi
0x10039fe0  jns     short loc_10039FE9
0x10039fe2  push    2Dh ; '-'
0x10039fe4  jmp     loc_1003A06D
0x10039fe9  lea     eax, [esp+48h+var_34]
0x10039fed  push    eax
0x10039fee  lea     ecx, [esp+4Ch+var_2C]
0x10039ff2  call    ??0?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QAE@ABV01@@Z; wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::com_ptr_t<IWeakReference,wil::err_returncode_policy>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> const &)
0x10039ff7  push    offset ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x10039ffc  push    2Ch ; ','; Size
0x10039ffe  mov     [esp+50h+var_28], edi
0x1003a002  call    ??2@YAPAXIABUnothrow_t@std@@@Z; operator new(uint,std::nothrow_t const &)
0x1003a007  pop     ecx
0x1003a008  pop     ecx
0x1003a009  test    eax, eax
0x1003a00b  jz      short loc_1003A01D
0x1003a00d  lea     ecx, [esp+48h+var_2C]
0x1003a011  push    ecx
0x1003a012  mov     ecx, eax
0x1003a014  call    Microsoft__WRL__Details__DelegateArgTraits_long____stdcall_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Security__Authorization__AppCapabilityAccess__AppCapability___Windows__Security__Authorization__AppCapabilityAccess__IAppCapability____Windows__Foundation__Internal__AggregateType_Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessChangedEventArgs___Windows__Security__Authorization__AppCapabilityAccess__IAppCapabilityAccessChangedEventArgs__________Windows__Security__Authorization__AppCapabilityAccess__IAppCapability___Windows__Security__Authorization__AppCapabilityAccess__IAppCapabilityAccessChangedEventArgs______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__ITypedEventHandler_Windows__Security__Authorization__AppCapabilityAccess__AppCapability___Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessChangedEventArgs____Microsoft__WRL__FtmBase___lambda_b0cc0fcdbf1cd0d9c171f1d8c9b18ade___1_Windows__Security__Authorization__AppCapabilityAccess__IAppCapability___Windows__Security__Authorization__AppCapabilityAccess__IAppCapabilityAccessChangedEventArgs_____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__ITypedEventHandler_Windows__Security__Authorization__AppCapabilityAccess__AppCapability___Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessChangedEventArgs____Microsoft__WRL__FtmBase___lambda_b0cc0fcdbf1cd0d9c171f1d8c9b18ade___1_Windows__Security__Authorization__AppCapabilityAccess__IAppCapability___Windows__Security__Authorization__AppCapabilityAccess__IAppCapabilityAccessChangedEventArgs___
0x1003a019  mov     esi, eax
0x1003a01b  jmp     short loc_1003A01F
0x1003a01d  xor     esi, esi
0x1003a01f  lea     ecx, [esp+48h+var_38]
0x1003a023  mov     [esp+48h+var_38], 0
0x1003a02b  mov     [esp+48h+var_30], esi
0x1003a02f  call    ??1?$ComPtr@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::ComPtr<Windows::Internal::IComPoolTask>::~ComPtr<Windows::Internal::IComPoolTask>(void)
0x1003a034  lea     ecx, [esp+48h+var_2C]
0x1003a038  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x1003a03d  test    esi, esi
0x1003a03f  jnz     short loc_1003A04A
0x1003a041  mov     esi, 8007000Eh
0x1003a046  push    48h ; 'H'
0x1003a048  jmp     short loc_1003A06D
0x1003a04a  mov     eax, [esp+48h+var_24]
0x1003a04e  push    [esp+48h+var_20]
0x1003a052  push    esi
0x1003a053  mov     ecx, [eax]
0x1003a055  push    ecx
0x1003a056  mov     eax, [ecx]
0x1003a058  mov     edi, [eax+28h]
0x1003a05b  mov     ecx, edi; this
0x1003a05d  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003a063  call    edi
0x1003a065  mov     esi, eax
0x1003a067  test    esi, esi
0x1003a069  jns     short loc_1003A07E
0x1003a06b  push    4Ah ; 'J'
0x1003a06d  mov     ecx, [ebp+4]
0x1003a070  pop     edx
0x1003a071  push    esi; void *
0x1003a072  push    offset aMultimediaDsho_4; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1003a077  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1003a07c  jmp     short loc_1003A080
0x1003a07e  xor     esi, esi
0x1003a080  lea     ecx, [esp+48h+var_34]
0x1003a084  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x1003a089  lea     ecx, [esp+48h+var_30]
0x1003a08d  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x1003a092  lea     ecx, [esp+48h+var_3C]
0x1003a096  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x1003a09b  mov     ecx, [esp+48h+var_4]
0x1003a09f  mov     eax, esi
0x1003a0a1  pop     edi
0x1003a0a2  pop     esi
0x1003a0a3  pop     ebx
0x1003a0a4  xor     ecx, esp; StackCookie
0x1003a0a6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003a0ab  mov     esp, ebp
0x1003a0ad  pop     ebp
0x1003a0ae  retn
0x1003a0af  mov     ecx, eax
0x1003a0b1  call    ?RaiseException@Details@WRL@Microsoft@@YGXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

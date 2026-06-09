# CapabilityUsageHelper::StartInternal(void *)

- ea: `0x10037be0`
- end: `0x10037e0a`
- name: `?StartInternal@CapabilityUsageHelper@@CGKPAX@Z`
- size: `554`
- prototype: `int __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x100075ad`
- `0x1000f598`
- `0x1002d510`
- `0x10037be0`
- `0x10037e42`
- `0x10037e56`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x10037d57`
- `KERNEL32!GetCurrentProcessId` at `0x10037d57`
- `KERNEL32!WaitForSingleObject` at `0x10037da1`
- `KERNEL32!WaitForSingleObject` at `0x10037da1`
- `ole32!CoUninitialize` at `0x10037df1`
- `ole32!CoUninitialize` at `0x10037df1`
- `ole32!CoInitializeEx` at `0x10037c04`
- `ole32!CoInitializeEx` at `0x10037c04`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x10037c86`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x10037c86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x10037c6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x10037c6a`

## string_xrefs

- `0x10037c65`: `Windows.Internal.CapabilityAccess.Management.CapabilityUsage`

## pseudocode

```c
int __stdcall CapabilityUsageHelper::StartInternal(PVOID Parameter)
{
  void *v1; // eax
  int v2; // esi
  void *ActivationFactory; // eax
  _DWORD *v5; // edi
  int v6; // eax
  PCWSTR v7; // ecx
  __int16 v8; // ax
  UINT32 v9; // ecx
  _DWORD *v10; // edi
  int v11; // eax
  CD3DSurfaceAllocator *v12; // esi
  DWORD CurrentProcessId; // eax
  Microsoft::WRL::Details *v14; // [esp+1Ch] [ebp-40h]
  const char *v15; // [esp+20h] [ebp-3Ch]
  unsigned int v16; // [esp+24h] [ebp-38h]
  int v17; // [esp+2Ch] [ebp-30h] BYREF
  _DWORD *v18; // [esp+30h] [ebp-2Ch] BYREF
  _DWORD *v19; // [esp+34h] [ebp-28h] BYREF
  CD3DSurfaceAllocator *v20; // [esp+38h] [ebp-24h]
  int v21; // [esp+3Ch] [ebp-20h]
  Microsoft::WRL::Wrappers::HStringReference hstringHeader; // [esp+40h] [ebp-1Ch] BYREF
  int retaddr; // [esp+60h] [ebp+4h]

  v21 = 0;
  v1 = (void *)CoInitializeEx(0, 0);
  v2 = (int)v1;
  if ( (int)v1 >= 0 )
  {
    v19 = 0;
    v18 = 0;
    v17 = 0;
    if ( Parameter )
    {
      hstringHeader.hstr_ = 0;
      if ( WindowsCreateStringReference(
             L"Windows.Internal.CapabilityAccess.Management.CapabilityUsage",
             0x3Cu,
             &hstringHeader.header_,
             &hstringHeader.hstr_) < 0 )
        goto LABEL_19;
      ActivationFactory = (void *)RoGetActivationFactory(
                                    hstringHeader.hstr_,
                                    &_GUID_42947746_4ea0_48c2_9274_062ed61f8daa,
                                    &v19);
      v2 = (int)ActivationFactory;
      if ( (int)ActivationFactory < 0 )
        goto LABEL_16;
      v5 = v19;
      v6 = *v19;
      v18 = 0;
      v20 = *(CD3DSurfaceAllocator **)(v6 + 24);
      v7 = c_szCapabilityWebcam;
      hstringHeader.hstr_ = 0;
      do
        v8 = *v7++;
      while ( v8 != (_WORD)v21 );
      v9 = v7 - (c_szCapabilityWebcam + 1);
      if ( v9 + 1 < v9 )
      {
LABEL_19:
        Microsoft::WRL::Details::RaiseException(v14, (int)v15, v16);
        JUMPOUT(0x10037E0A);
      }
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, c_szCapabilityWebcam, v9 + 1, v9);
      v2 = ((int (__thiscall *)(CD3DSurfaceAllocator *, _DWORD *, HSTRING__ *, _DWORD **))v20)(
             v20,
             v5,
             hstringHeader.hstr_,
             &v18);
      if ( v2 >= 0 )
      {
        v10 = v18;
        v11 = *v18;
        v17 = 0;
        v20 = *(CD3DSurfaceAllocator **)(v11 + 24);
        v12 = v20;
        CurrentProcessId = GetCurrentProcessId();
        v2 = ((int (__thiscall *)(CD3DSurfaceAllocator *, _DWORD *, DWORD, _DWORD, int *))v12)(
               v12,
               v10,
               CurrentProcessId,
               0,
               &v17);
        if ( v2 >= 0 )
        {
          v2 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v17 + 24))(*(_DWORD *)(*(_DWORD *)v17 + 24), v17);
          if ( v2 >= 0 )
          {
            WaitForSingleObject(Parameter, 0xFFFFFFFF);
            ActivationFactory = (void *)(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v17 + 28))(
                                          *(_DWORD *)(*(_DWORD *)v17 + 28),
                                          v17);
            v2 = (int)ActivationFactory;
            if ( (int)ActivationFactory >= 0 )
            {
              v2 = 0;
              goto LABEL_18;
            }
LABEL_16:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityusagehelper.cpp",
              ActivationFactory,
              (unsigned int)v14,
              v15,
              v16);
LABEL_18:
            wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v17);
            wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>((int *)&v18);
            wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>((int *)&v19);
            CoUninitialize();
            return v2;
          }
        }
      }
    }
    else
    {
      v2 = -2147024809;
    }
    ActivationFactory = (void *)v2;
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityusagehelper.cpp",
    v1,
    (unsigned int)v14,
    v15,
    v16);
  return v2;
}

```

## disassembly

```asm
0x10037be0  mov     edi, edi
0x10037be2  push    ebp
0x10037be3  mov     ebp, esp
0x10037be5  and     esp, 0FFFFFFF8h
0x10037be8  sub     esp, 34h
0x10037beb  mov     eax, ___security_cookie
0x10037bf0  xor     eax, esp
0x10037bf2  mov     [esp+34h+var_4], eax
0x10037bf6  push    ebx; unsigned int
0x10037bf7  mov     ebx, [ebp+Parameter]
0x10037bfa  push    esi; int
0x10037bfb  push    edi; this
0x10037bfc  xor     edi, edi
0x10037bfe  push    edi; dwCoInit
0x10037bff  push    edi; pvReserved
0x10037c00  mov     [esp+48h+var_20], edi
0x10037c04  call    ds:__imp__CoInitializeEx@8; CoInitializeEx(x,x)
0x10037c0a  mov     esi, eax
0x10037c0c  test    esi, esi
0x10037c0e  jns     short loc_10037C37
0x10037c10  mov     ecx, [ebp+4]
0x10037c13  push    esi; void *
0x10037c14  push    offset aMultimediaDsho; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10037c19  push    59h ; 'Y'
0x10037c1b  pop     edx
0x10037c1c  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10037c21  mov     ecx, [esp+40h+var_4]
0x10037c25  mov     eax, esi
0x10037c27  pop     edi
0x10037c28  pop     esi
0x10037c29  pop     ebx
0x10037c2a  xor     ecx, esp; StackCookie
0x10037c2c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037c31  mov     esp, ebp
0x10037c33  pop     ebp
0x10037c34  retn    4
0x10037c37  mov     [esp+40h+var_28], edi
0x10037c3b  mov     [esp+40h+var_2C], edi
0x10037c3f  mov     [esp+40h+var_30], edi
0x10037c43  test    ebx, ebx
0x10037c45  jnz     short loc_10037C55
0x10037c47  mov     esi, 80070057h
0x10037c4c  push    64h ; 'd'
0x10037c4e  mov     eax, esi
0x10037c50  jmp     loc_10037DC3
0x10037c55  lea     eax, [esp+40h+string]
0x10037c59  mov     [esp+40h+string], edi
0x10037c5d  push    eax; string
0x10037c5e  lea     eax, [esp+44h+hstringHeader]
0x10037c62  push    eax; hstringHeader
0x10037c63  push    3Ch ; '<'; length
0x10037c65  push    offset ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityUsage@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x10037c6a  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x10037c70  test    eax, eax
0x10037c72  js      loc_10037E03
0x10037c78  lea     eax, [esp+40h+var_28]
0x10037c7c  push    eax
0x10037c7d  push    offset __GUID_42947746_4ea0_48c2_9274_062ed61f8daa
0x10037c82  push    [esp+48h+string]
0x10037c86  call    ds:__imp__RoGetActivationFactory@12; RoGetActivationFactory(x,x,x)
0x10037c8c  mov     esi, eax
0x10037c8e  test    esi, esi
0x10037c90  jns     short loc_10037C99
0x10037c92  push    6Bh ; 'k'
0x10037c94  jmp     loc_10037DC3
0x10037c99  mov     edi, [esp+40h+var_28]
0x10037c9d  mov     ecx, [esp+40h+var_2C]
0x10037ca1  mov     eax, [edi]
0x10037ca3  mov     [esp+40h+var_2C], 0
0x10037cab  mov     eax, [eax+18h]
0x10037cae  mov     [esp+40h+var_24], eax
0x10037cb2  test    ecx, ecx
0x10037cb4  jz      short loc_10037CC6
0x10037cb6  mov     eax, [ecx]
0x10037cb8  push    ecx
0x10037cb9  mov     esi, [eax+8]
0x10037cbc  mov     ecx, esi; this
0x10037cbe  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037cc4  call    esi
0x10037cc6  mov     edx, ds:?c_szCapabilityWebcam@@3QBGB; ushort const * const c_szCapabilityWebcam
0x10037ccc  mov     ecx, edx
0x10037cce  mov     [esp+40h+string], 0
0x10037cd6  lea     esi, [ecx+2]
0x10037cd9  mov     ax, [ecx]
0x10037cdc  add     ecx, 2
0x10037cdf  cmp     ax, word ptr [esp+40h+var_20]
0x10037ce4  jnz     short loc_10037CD9
0x10037ce6  sub     ecx, esi
0x10037ce8  sar     ecx, 1
0x10037cea  lea     eax, [ecx+1]
0x10037ced  cmp     eax, ecx
0x10037cef  jb      loc_10037DFC
0x10037cf5  push    ecx; length
0x10037cf6  push    eax; unsigned int
0x10037cf7  push    edx; sourceString
0x10037cf8  lea     ecx, [esp+4Ch+hstringHeader]; this
0x10037cfc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AAEXPBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x10037d01  mov     esi, [esp+40h+var_24]
0x10037d05  lea     eax, [esp+40h+var_2C]
0x10037d09  push    eax
0x10037d0a  push    [esp+44h+string]
0x10037d0e  mov     ecx, esi; this
0x10037d10  push    edi
0x10037d11  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037d17  call    esi
0x10037d19  mov     esi, eax
0x10037d1b  test    esi, esi
0x10037d1d  jns     short loc_10037D26
0x10037d1f  push    6Dh ; 'm'
0x10037d21  jmp     loc_10037C4E
0x10037d26  mov     edi, [esp+40h+var_2C]
0x10037d2a  mov     ecx, [esp+40h+var_30]
0x10037d2e  mov     eax, [edi]
0x10037d30  mov     [esp+40h+var_30], 0
0x10037d38  mov     esi, [eax+18h]
0x10037d3b  mov     [esp+40h+var_24], esi
0x10037d3f  test    ecx, ecx
0x10037d41  jz      short loc_10037D57
0x10037d43  mov     eax, [ecx]
0x10037d45  push    ecx
0x10037d46  mov     esi, [eax+8]
0x10037d49  mov     ecx, esi; this
0x10037d4b  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037d51  call    esi
0x10037d53  mov     esi, [esp+40h+var_24]
0x10037d57  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x10037d5d  lea     ecx, [esp+40h+var_30]
0x10037d61  push    ecx
0x10037d62  push    0
0x10037d64  push    eax
0x10037d65  push    edi
0x10037d66  mov     ecx, esi; this
0x10037d68  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037d6e  call    esi
0x10037d70  mov     esi, eax
0x10037d72  test    esi, esi
0x10037d74  jns     short loc_10037D7D
0x10037d76  push    70h ; 'p'
0x10037d78  jmp     loc_10037C4E
0x10037d7d  mov     eax, [esp+40h+var_30]
0x10037d81  push    eax
0x10037d82  mov     ecx, [eax]
0x10037d84  mov     esi, [ecx+18h]
0x10037d87  mov     ecx, esi; this
0x10037d89  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037d8f  call    esi
0x10037d91  mov     esi, eax
0x10037d93  test    esi, esi
0x10037d95  jns     short loc_10037D9E
0x10037d97  push    73h ; 's'
0x10037d99  jmp     loc_10037C4E
0x10037d9e  push    0FFFFFFFFh; dwMilliseconds
0x10037da0  push    ebx; hHandle
0x10037da1  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x10037da7  mov     eax, [esp+40h+var_30]
0x10037dab  push    eax
0x10037dac  mov     ecx, [eax]
0x10037dae  mov     esi, [ecx+1Ch]
0x10037db1  mov     ecx, esi; this
0x10037db3  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037db9  call    esi
0x10037dbb  mov     esi, eax
0x10037dbd  test    esi, esi
0x10037dbf  jns     short loc_10037DD4
0x10037dc1  push    79h ; 'y'
0x10037dc3  mov     ecx, [ebp+4]
0x10037dc6  pop     edx
0x10037dc7  push    eax; void *
0x10037dc8  push    offset aMultimediaDsho; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10037dcd  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10037dd2  jmp     short loc_10037DD6
0x10037dd4  xor     esi, esi
0x10037dd6  lea     ecx, [esp+40h+var_30]
0x10037dda  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10037ddf  lea     ecx, [esp+40h+var_2C]
0x10037de3  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10037de8  lea     ecx, [esp+40h+var_28]
0x10037dec  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10037df1  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x10037df7  jmp     loc_10037C21
0x10037dfc  mov     ecx, 80070216h
0x10037e01  jmp     short loc_10037E05
0x10037e03  mov     ecx, eax
0x10037e05  call    ?RaiseException@Details@WRL@Microsoft@@YGXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

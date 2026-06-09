# EnrollEngine::BeginAADEnroll(AADEnrollInfoTag *,void * *,_GUID *)

- ea: `0x180035f30`
- end: `0x180036214`
- name: `?BeginAADEnroll@EnrollEngine@@UEAAJPEAUAADEnrollInfoTag@@PEAPEAXPEAU_GUID@@@Z`
- size: `740`
- prototype: `__int64 __fastcall(EnrollEngine *__hidden this, struct AADEnrollInfoTag *, void **, UUID *Uuid)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001058`
- `0x180001140`
- `0x1800071c0`
- `0x18000e0d0`
- `0x18002e1a0`
- `0x180033a3c`
- `0x180035f30`
- `0x180036f74`
- `0x18003a9b4`
- `0x18003b0bc`
- `0x180040168`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003602f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003602f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036077`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036110`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036077`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036110`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036176`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036176`

## pseudocode

```c
__int64 __fastcall EnrollEngine::BeginAADEnroll(EnrollEngine *this, struct AADEnrollInfoTag *a2, void **a3, UUID *Uuid)
{
  bool v4; // zf
  void **v6; // rdi
  __int64 result; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // r15d
  LSTATUS v14; // eax
  signed int v15; // ebx
  LSTATUS ValueW; // eax
  BOOL v17; // esi
  LSTATUS v18; // eax
  BOOL v19; // edi
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // rcx
  int pvData; // [rsp+40h] [rbp-29h] BYREF
  int v24; // [rsp+44h] [rbp-25h] BYREF
  HKEY *v25; // [rsp+48h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-11h] BYREF
  DWORD v28; // [rsp+5Ch] [rbp-Dh] BYREF
  HKEY hkey[2]; // [rsp+60h] [rbp-9h] BYREF

  v4 = (*((_DWORD *)a2 + 14) & 0x4000) == 0;
  v6 = a3;
  v25 = (HKEY *)a3;
  if ( v4 )
  {
    pvData = 0;
    *(_OWORD *)hkey = 0;
    result = CheckForExistingEnterpriseEnrollment(&pvData, hkey, 0);
    if ( (int)result < 0 )
      return result;
    if ( pvData )
    {
      if ( (unsigned int)dword_1800AF3E8 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1800AF3E8, 0x400000000000LL) )
        {
          v25 = hkey;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
            v10,
            (__int64)byte_18009E3D5,
            v11,
            v12,
            &v25);
        }
      }
      return 2149056522LL;
    }
  }
  hkey[0] = 0;
  pvData = 0;
  v13 = 1;
  pcbData = 4;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hkey,
    0);
  v14 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Policies\\Microsoft\\Windows\\CurrentVersion\\MDM",
          0,
          0x20119u,
          hkey);
  v15 = v14;
  if ( v14 > 0 )
    v15 = (unsigned __int16)v14 | 0x80070000;
  if ( v15 >= 0 )
  {
    ValueW = RegGetValueW(hkey[0], 0, L"DisableRegistration", 0x18u, 0, &pvData, &pcbData);
    v15 = ValueW;
    if ( ValueW > 0 )
      v15 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( v15 == -2147024894 || v15 == -2147023267 )
  {
    v17 = 0;
LABEL_18:
    hKey = 0;
    v24 = 0;
    v28 = 4;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v15 = EEDBManager::OpenEnrollmentsHKEY(0x20019u, &hKey);
    if ( v15 >= 0 )
    {
      v18 = RegGetValueW(hKey, 0, L"ExternallyManaged", 0x18u, 0, &v24, &v28);
      v15 = v18;
      if ( v18 > 0 )
        v15 = (unsigned __int16)v18 | 0x80070000;
    }
    if ( v15 == -2147024894 || v15 == -2147023267 )
    {
      v19 = 0;
      v15 = 0;
    }
    else
    {
      v19 = 1;
      if ( v15 >= 0 )
        v19 = v24 != 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v15 >= 0 && (v17 || v19) )
      v13 = 0;
    v6 = (void **)v25;
    goto LABEL_33;
  }
  if ( v15 >= 0 )
  {
    v17 = pvData != 0;
    goto LABEL_18;
  }
LABEL_33:
  if ( hkey[0] )
    RegCloseKey(hkey[0]);
  if ( v15 < 0 || !v13 )
    return 2149056550LL;
  if ( (*((_DWORD *)a2 + 14) & 4) == 0 && !*(_QWORD *)a2 )
    return 2147942487LL;
  *Uuid = GUID_NULL;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_EnrollmentFlag_Improvement>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_EnrollmentFlag_Improvement>::GetImpl'::`2'::impl) )
  {
    v21 = EEDBManager::SetMmpcEnrollmentFlag(0);
    if ( v21 < 0 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer(v22, EnterpriseDiagnosticsSetMmpcFlagFailed, (unsigned int)v21);
  }
  return EnrollEngine::BeginEnrollInternal<AADEnrollInfoTag>((__int64)this, (__int64)a2, v20, v6, Uuid);
}

```

## disassembly

```asm
0x180035f30  push    rbp
0x180035f32  push    rbx
0x180035f33  push    rsi
0x180035f34  push    rdi
0x180035f35  push    r12
0x180035f37  push    r13
0x180035f39  push    r14
0x180035f3b  push    r15
0x180035f3d  lea     rbp, [rsp-1Fh]
0x180035f42  sub     rsp, 88h
0x180035f49  mov     rax, cs:__security_cookie
0x180035f50  xor     rax, rsp
0x180035f53  mov     [rbp+57h+var_50], rax
0x180035f57  test    dword ptr [rdx+38h], 4000h
0x180035f5e  mov     r12, r9
0x180035f61  mov     rdi, r8
0x180035f64  mov     [rbp+57h+var_78], r8
0x180035f68  mov     r14, rdx
0x180035f6b  mov     r13, rcx
0x180035f6e  jnz     short loc_180035FE8
0x180035f70  xorps   xmm0, xmm0
0x180035f73  mov     [rbp+57h+var_80], 0
0x180035f7a  xor     r8d, r8d
0x180035f7d  lea     rdx, [rbp+57h+hkey]
0x180035f81  lea     rcx, [rbp+57h+var_80]
0x180035f85  movups  xmmword ptr [rbp+57h+hkey], xmm0
0x180035f89  call    CheckForExistingEnterpriseEnrollment
0x180035f8e  test    eax, eax
0x180035f90  js      loc_1800361F4
0x180035f96  cmp     [rbp+57h+var_80], 0
0x180035f9a  jz      short loc_180035FE8
0x180035f9c  mov     eax, cs:dword_1800AF3E8
0x180035fa2  cmp     eax, 5
0x180035fa5  jbe     short loc_180035FDE
0x180035fa7  mov     rdx, 400000000000h
0x180035fb1  lea     rcx, dword_1800AF3E8
0x180035fb8  call    _tlgKeywordOn
0x180035fbd  test    al, al
0x180035fbf  jz      short loc_180035FDE
0x180035fc1  lea     rax, [rbp+57h+hkey]
0x180035fc5  mov     [rbp+57h+var_78], rax
0x180035fc9  lea     rdx, byte_18009E3D5
0x180035fd0  lea     rax, [rbp+57h+var_78]
0x180035fd4  mov     [rsp+0C0h+phkResult], rax
0x180035fd9  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x180035fde  mov     eax, 8018000Ah
0x180035fe3  jmp     loc_1800361F4
0x180035fe8  xor     edx, edx
0x180035fea  mov     [rbp+57h+hkey], 0
0x180035ff2  lea     rcx, [rbp+57h+hkey]
0x180035ff6  mov     [rbp+57h+var_80], 0
0x180035ffd  mov     r15d, 1
0x180036003  mov     [rbp+57h+var_68], 4
0x18003600a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003600f  lea     rax, [rbp+57h+hkey]
0x180036013  mov     r9d, 20119h; samDesired
0x180036019  xor     r8d, r8d; ulOptions
0x18003601c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180036021  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180036028  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003602f  call    cs:__imp_RegOpenKeyExW
0x180036035  mov     ebx, eax
0x180036037  mov     esi, 80070000h
0x18003603c  test    eax, eax
0x18003603e  jle     short loc_180036045
0x180036040  movzx   ebx, ax
0x180036043  or      ebx, esi
0x180036045  test    ebx, ebx
0x180036047  js      short loc_180036088
0x180036049  mov     rcx, [rbp+57h+hkey]; hkey
0x18003604d  lea     rax, [rbp+57h+var_68]
0x180036051  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180036056  lea     r8, aDisableregistr; "DisableRegistration"
0x18003605d  lea     rax, [rbp+57h+var_80]
0x180036061  mov     r9d, 18h; dwFlags
0x180036067  mov     [rsp+0C0h+pvData], rax; pvData
0x18003606c  xor     edx, edx; lpSubKey
0x18003606e  mov     [rsp+0C0h+phkResult], 0; pdwType
0x180036077  call    cs:__imp_RegGetValueW
0x18003607d  mov     ebx, eax
0x18003607f  test    eax, eax
0x180036081  jle     short loc_180036088
0x180036083  movzx   ebx, ax
0x180036086  or      ebx, esi
0x180036088  cmp     ebx, 80070002h
0x18003608e  jz      short loc_1800360AB
0x180036090  cmp     ebx, 8007065Dh
0x180036096  jz      short loc_1800360AB
0x180036098  test    ebx, ebx
0x18003609a  js      loc_18003616D
0x1800360a0  xor     esi, esi
0x1800360a2  cmp     [rbp+57h+var_80], esi
0x1800360a5  setnz   sil
0x1800360a9  jmp     short loc_1800360AD
0x1800360ab  xor     esi, esi
0x1800360ad  xor     edx, edx
0x1800360af  mov     [rbp+57h+hKey], 0
0x1800360b7  lea     rcx, [rbp+57h+hKey]
0x1800360bb  mov     [rbp+57h+var_7C], 0
0x1800360c2  mov     [rbp+57h+var_64], 4
0x1800360c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800360ce  lea     rdx, [rbp+57h+hKey]; HKEY *
0x1800360d2  mov     ecx, 20019h; unsigned int
0x1800360d7  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x1800360dc  mov     ebx, eax
0x1800360de  test    eax, eax
0x1800360e0  js      short loc_180036125
0x1800360e2  mov     rcx, [rbp+57h+hKey]; hkey
0x1800360e6  lea     rax, [rbp+57h+var_64]
0x1800360ea  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800360ef  lea     r8, aExternallymana; "ExternallyManaged"
0x1800360f6  lea     rax, [rbp+57h+var_7C]
0x1800360fa  mov     r9d, 18h; dwFlags
0x180036100  mov     [rsp+0C0h+pvData], rax; pvData
0x180036105  xor     edx, edx; lpSubKey
0x180036107  mov     [rsp+0C0h+phkResult], 0; pdwType
0x180036110  call    cs:__imp_RegGetValueW
0x180036116  mov     ebx, eax
0x180036118  test    eax, eax
0x18003611a  jle     short loc_180036125
0x18003611c  movzx   ebx, ax
0x18003611f  or      ebx, 80070000h
0x180036125  cmp     ebx, 80070002h
0x18003612b  jz      short loc_180036147
0x18003612d  cmp     ebx, 8007065Dh
0x180036133  jz      short loc_180036147
0x180036135  mov     edi, r15d
0x180036138  test    ebx, ebx
0x18003613a  js      short loc_18003614B
0x18003613c  xor     edi, edi
0x18003613e  cmp     [rbp+57h+var_7C], edi
0x180036141  setnz   dil
0x180036145  jmp     short loc_18003614B
0x180036147  xor     edi, edi
0x180036149  xor     ebx, ebx
0x18003614b  mov     rcx, [rbp+57h+hKey]; hKey
0x18003614f  test    rcx, rcx
0x180036152  jz      short loc_18003615A
0x180036154  call    cs:__imp_RegCloseKey
0x18003615a  test    ebx, ebx
0x18003615c  js      short loc_180036169
0x18003615e  test    esi, esi
0x180036160  jnz     short loc_180036166
0x180036162  test    edi, edi
0x180036164  jz      short loc_180036169
0x180036166  xor     r15d, r15d
0x180036169  mov     rdi, [rbp+57h+var_78]
0x18003616d  mov     rcx, [rbp+57h+hkey]; hKey
0x180036171  test    rcx, rcx
0x180036174  jz      short loc_18003617C
0x180036176  call    cs:__imp_RegCloseKey
0x18003617c  test    ebx, ebx
0x18003617e  js      short loc_1800361EF
0x180036180  test    r15d, r15d
0x180036183  jz      short loc_1800361EF
0x180036185  mov     eax, [r14+38h]
0x180036189  test    al, 4
0x18003618b  jnz     short loc_18003619A
0x18003618d  cmp     qword ptr [r14], 0
0x180036191  jnz     short loc_18003619A
0x180036193  mov     eax, 80070057h
0x180036198  jmp     short loc_1800361F4
0x18003619a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800361a1  movdqu  xmmword ptr [r12], xmm0
0x1800361a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_EnrollmentFlag_Improvement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_EnrollmentFlag_Improvement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_EnrollmentFlag_Improvement> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_EnrollmentFlag_Improvement>::GetImpl(void)'::`2'::impl
0x1800361ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_EnrollmentFlag_Improvement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_EnrollmentFlag_Improvement>::__private_IsEnabled(void)
0x1800361b3  test    al, al
0x1800361b5  jz      short loc_1800361DA
0x1800361b7  xor     ecx, ecx; unsigned int
0x1800361b9  call    ?SetMmpcEnrollmentFlag@EEDBManager@@SAJK@Z; EEDBManager::SetMmpcEnrollmentFlag(ulong)
0x1800361be  test    eax, eax
0x1800361c0  jns     short loc_1800361DA
0x1800361c2  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800361c9  jz      short loc_1800361DA
0x1800361cb  mov     r8d, eax
0x1800361ce  lea     rdx, EnterpriseDiagnosticsSetMmpcFlagFailed
0x1800361d5  call    McTemplateU0d_EventWriteTransfer
0x1800361da  mov     r9, rdi; int
0x1800361dd  mov     [rsp+0C0h+phkResult], r12; Uuid
0x1800361e2  mov     rdx, r14; int
0x1800361e5  mov     rcx, r13; int
0x1800361e8  call    ??$BeginEnrollInternal@UAADEnrollInfoTag@@@EnrollEngine@@AEAAJPEAUAADEnrollInfoTag@@W4EntPlatStateMachine@@PEAPEAXPEAU_GUID@@@Z; EnrollEngine::BeginEnrollInternal<AADEnrollInfoTag>(AADEnrollInfoTag *,EntPlatStateMachine,void * *,_GUID *)
0x1800361ed  jmp     short loc_1800361F4
0x1800361ef  mov     eax, 80180026h
0x1800361f4  mov     rcx, [rbp+57h+var_50]
0x1800361f8  xor     rcx, rsp; StackCookie
0x1800361fb  call    __security_check_cookie
0x180036200  add     rsp, 88h
0x180036207  pop     r15
0x180036209  pop     r14
0x18003620b  pop     r13
0x18003620d  pop     r12
0x18003620f  pop     rdi
0x180036210  pop     rsi
0x180036211  pop     rbx
0x180036212  pop     rbp
0x180036213  retn
```

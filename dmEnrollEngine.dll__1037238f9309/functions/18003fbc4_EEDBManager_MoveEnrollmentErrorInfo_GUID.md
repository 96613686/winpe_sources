# EEDBManager::MoveEnrollmentErrorInfo(_GUID)

- ea: `0x18003fbc4`
- end: `0x18003fda9`
- name: `?MoveEnrollmentErrorInfo@EEDBManager@@QEAAJU_GUID@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(EEDBManager *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180042f90`
- `0x180077490`

## callees

- `0x180005cf0`
- `0x1800071c0`
- `0x18000de50`
- `0x18003fbc4`
- `0x18003fdb0`
- `0x18003fe7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fcfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fd51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fcfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fd51`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003fd0b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003fd62`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003fd0b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003fd62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fc27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fc4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fd72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fd96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fc27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fc4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fd72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fd96`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EEDBManager::MoveEnrollmentErrorInfo(EEDBManager *this, struct _GUID *a2)
{
  int v3; // ebx
  int String_0; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  int v8; // esi
  __int64 v9; // rdi
  __int64 v10; // rax
  struct _GUID v11; // [rsp+30h] [rbp-10h] BYREF
  HKEY v12; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF
  BYTE *v14; // [rsp+80h] [rbp+40h] BYREF
  BYTE *lpData; // [rsp+88h] [rbp+48h] BYREF

  v12 = 0;
  lpData = 0;
  v14 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v11 = *a2;
  v3 = EEDBManager::OpenEnrollmentKey(&v11, 0x2001Fu, L"Status", &hKey);
  if ( v3 >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v12,
      0);
    v11 = *a2;
    if ( EEDBManager::OpenEnrollmentKey(&v11, 0x20019u, 0, &v12) >= 0 )
    {
      String_0 = RegistryAllocAndGetString_0(v12, L"LastSoapErrorTraceId");
      LOBYTE(v6) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CustomServerError>::GetImpl'::`2'::impl,
        v6);
      v8 = RegistryAllocAndGetString_0(v12, L"LifecycleNotificationErrorContext");
      v9 = -1;
      if ( String_0 >= 0 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)&lpData[2 * v10] );
        RegSetValueExW(hKey, L"LastSoapErrorTraceId", 0, 1u, lpData, 2 * v10);
        RegDeleteValueW(v12, L"LastSoapErrorTraceId");
      }
      LOBYTE(v7) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CustomServerError>::GetImpl'::`2'::impl,
        v7);
      if ( v8 >= 0 )
      {
        do
          ++v9;
        while ( *(_WORD *)&v14[2 * v9] );
        RegSetValueExW(hKey, L"LifecycleNotificationErrorContext", 0, 1u, v14, 2 * v9);
        RegDeleteValueW(v12, L"LifecycleNotificationErrorContext");
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v14);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&lpData);
    if ( v12 )
      RegCloseKey(v12);
    return 0;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v14);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&lpData);
    if ( v12 )
      RegCloseKey(v12);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x18003fbc4  mov     [rsp-28h+arg_0], rcx
0x18003fbc9  push    rbp
0x18003fbca  push    rbx
0x18003fbcb  push    rsi
0x18003fbcc  push    rdi
0x18003fbcd  push    r14
0x18003fbcf  mov     rbp, rsp
0x18003fbd2  sub     rsp, 40h
0x18003fbd6  mov     rdi, rdx
0x18003fbd9  xor     r14d, r14d
0x18003fbdc  mov     [rbp+arg_0], r14
0x18003fbe0  mov     [rbp+arg_18], r14
0x18003fbe4  mov     [rbp+arg_10], r14
0x18003fbe8  mov     [rbp+hKey], r14
0x18003fbec  xor     edx, edx
0x18003fbee  lea     rcx, [rbp+hKey]
0x18003fbf2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003fbf7  movaps  xmm0, xmmword ptr [rdi]
0x18003fbfa  movdqa  xmmword ptr [rbp+var_10.Data1], xmm0
0x18003fbff  lea     r9, [rbp+hKey]; HKEY *
0x18003fc03  lea     r8, aStatus; "Status"
0x18003fc0a  mov     edx, 2001Fh; unsigned int
0x18003fc0f  lea     rcx, [rbp+var_10]; struct _GUID
0x18003fc13  call    ?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)
0x18003fc18  mov     ebx, eax
0x18003fc1a  test    eax, eax
0x18003fc1c  jns     short loc_18003FC58
0x18003fc1e  mov     rcx, [rbp+hKey]; hKey
0x18003fc22  test    rcx, rcx
0x18003fc25  jz      short loc_18003FC2E
0x18003fc27  call    cs:__imp_RegCloseKey
0x18003fc2d  nop
0x18003fc2e  lea     rcx, [rbp+arg_10]
0x18003fc32  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18003fc37  nop
0x18003fc38  lea     rcx, [rbp+arg_18]
0x18003fc3c  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18003fc41  nop
0x18003fc42  mov     rcx, [rbp+arg_0]; hKey
0x18003fc46  test    rcx, rcx
0x18003fc49  jz      short loc_18003FC51
0x18003fc4b  call    cs:__imp_RegCloseKey
0x18003fc51  mov     eax, ebx
0x18003fc53  jmp     loc_18003FD9E
0x18003fc58  xor     edx, edx
0x18003fc5a  lea     rcx, [rbp+arg_0]
0x18003fc5e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003fc63  movaps  xmm0, xmmword ptr [rdi]
0x18003fc66  movdqa  xmmword ptr [rbp+var_10.Data1], xmm0
0x18003fc6b  lea     r9, [rbp+arg_0]; HKEY *
0x18003fc6f  xor     r8d, r8d; unsigned __int16 *
0x18003fc72  mov     edx, 20019h; unsigned int
0x18003fc77  lea     rcx, [rbp+var_10]; struct _GUID
0x18003fc7b  call    ?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)
0x18003fc80  test    eax, eax
0x18003fc82  js      loc_18003FD69
0x18003fc88  lea     r8, [rbp+arg_18]
0x18003fc8c  lea     rdx, aLastsoaperrort; "LastSoapErrorTraceId"
0x18003fc93  mov     rcx, [rbp+arg_0]; hKey
0x18003fc97  call    RegistryAllocAndGetString_0
0x18003fc9c  mov     ebx, eax
0x18003fc9e  mov     dl, 1
0x18003fca0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CustomServerError@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CustomServerError@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError> `wil::Feature<__WilFeatureTraits_Feature_CustomServerError>::GetImpl(void)'::`2'::impl
0x18003fca7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CustomServerError@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003fcac  lea     r8, [rbp+arg_10]
0x18003fcb0  lea     rdx, aLifecyclenotif_3; "LifecycleNotificationErrorContext"
0x18003fcb7  mov     rcx, [rbp+arg_0]; hKey
0x18003fcbb  call    RegistryAllocAndGetString_0
0x18003fcc0  mov     esi, eax
0x18003fcc2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003fcc6  test    ebx, ebx
0x18003fcc8  js      short loc_18003FD11
0x18003fcca  mov     r8, [rbp+arg_18]
0x18003fcce  mov     rax, rdi
0x18003fcd1  inc     rax
0x18003fcd4  cmp     [r8+rax*2], r14w
0x18003fcd9  jnz     short loc_18003FCD1
0x18003fcdb  add     eax, eax
0x18003fcdd  mov     [rsp+40h+cbData], eax; cbData
0x18003fce1  mov     [rsp+40h+lpData], r8; lpData
0x18003fce6  mov     r9d, 1; dwType
0x18003fcec  xor     r8d, r8d; Reserved
0x18003fcef  lea     rdx, aLastsoaperrort; "LastSoapErrorTraceId"
0x18003fcf6  mov     rcx, [rbp+hKey]; hKey
0x18003fcfa  call    cs:__imp_RegSetValueExW
0x18003fd00  lea     rdx, aLastsoaperrort; "LastSoapErrorTraceId"
0x18003fd07  mov     rcx, [rbp+arg_0]; hKey
0x18003fd0b  call    cs:__imp_RegDeleteValueW
0x18003fd11  mov     dl, 1
0x18003fd13  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CustomServerError@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CustomServerError@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError> `wil::Feature<__WilFeatureTraits_Feature_CustomServerError>::GetImpl(void)'::`2'::impl
0x18003fd1a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CustomServerError@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003fd1f  test    esi, esi
0x18003fd21  js      short loc_18003FD69
0x18003fd23  mov     rax, [rbp+arg_10]
0x18003fd27  inc     rdi
0x18003fd2a  cmp     [rax+rdi*2], r14w
0x18003fd2f  jnz     short loc_18003FD27
0x18003fd31  lea     ecx, [rdi+rdi]
0x18003fd34  mov     [rsp+40h+cbData], ecx; cbData
0x18003fd38  mov     [rsp+40h+lpData], rax; lpData
0x18003fd3d  mov     r9d, 1; dwType
0x18003fd43  xor     r8d, r8d; Reserved
0x18003fd46  lea     rdx, aLifecyclenotif_3; "LifecycleNotificationErrorContext"
0x18003fd4d  mov     rcx, [rbp+hKey]; hKey
0x18003fd51  call    cs:__imp_RegSetValueExW
0x18003fd57  lea     rdx, aLifecyclenotif_3; "LifecycleNotificationErrorContext"
0x18003fd5e  mov     rcx, [rbp+arg_0]; hKey
0x18003fd62  call    cs:__imp_RegDeleteValueW
0x18003fd68  nop
0x18003fd69  mov     rcx, [rbp+hKey]; hKey
0x18003fd6d  test    rcx, rcx
0x18003fd70  jz      short loc_18003FD79
0x18003fd72  call    cs:__imp_RegCloseKey
0x18003fd78  nop
0x18003fd79  lea     rcx, [rbp+arg_10]
0x18003fd7d  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18003fd82  nop
0x18003fd83  lea     rcx, [rbp+arg_18]
0x18003fd87  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18003fd8c  nop
0x18003fd8d  mov     rcx, [rbp+arg_0]; hKey
0x18003fd91  test    rcx, rcx
0x18003fd94  jz      short loc_18003FD9C
0x18003fd96  call    cs:__imp_RegCloseKey
0x18003fd9c  xor     eax, eax
0x18003fd9e  add     rsp, 40h
0x18003fda2  pop     r14
0x18003fda4  pop     rdi
0x18003fda5  pop     rsi
0x18003fda6  pop     rbx
0x18003fda7  pop     rbp
0x18003fda8  retn
```

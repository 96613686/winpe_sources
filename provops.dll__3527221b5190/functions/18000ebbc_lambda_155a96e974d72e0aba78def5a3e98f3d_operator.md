# _lambda_155a96e974d72e0aba78def5a3e98f3d_::operator()

- ea: `0x18000ebbc`
- end: `0x18000ed17`
- name: `_lambda_155a96e974d72e0aba78def5a3e98f3d_::operator()`
- size: `347`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d42c`
- `0x180010b40`

## callees

- `0x18000ebbc`
- `0x180012e94`
- `0x180013e9c`
- `0x180018e80`
- `0x18001f8e4`
- `0x180020c5c`
- `0x180020e98`
- `0x180020fe0`
- `0x18002490c`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ecf1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ecf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ec80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ec80`
- `ntdll!RtlPublishWnfStateData` at `0x18000ec17`
- `ntdll!RtlPublishWnfStateData` at `0x18000ec17`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_155a96e974d72e0aba78def5a3e98f3d_::operator()(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // r8d
  void **ProvisioningDiagnosticsFolderPath; // rax
  void **v5; // rdx
  LPVOID pv; // [rsp+30h] [rbp-30h] BYREF
  void *Src[3]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v9; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  PostProvisioningActivities(**(struct IMVEngine ***)a1, **(_DWORD **)(a1 + 8));
  if ( **(_BYTE **)(a1 + 16) )
  {
    LODWORD(pv) = 1;
    v2 = RtlPublishWnfStateData(WNF_DEVM_PROVISIONING_COMPLETE, 0, &pv, 4);
    if ( v2 < 0 )
      wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0x2E0, v3, (const char *)(unsigned int)v2, 0);
  }
  if ( !**(_DWORD **)(a1 + 24) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::GetImpl'::`2'::impl) )
    {
      pv = 0;
      ProvOperations::GetOOBEProvisioningLogsPath((unsigned __int16 **)&pv);
      (*(void (__fastcall **)(_QWORD, LPVOID))(**(_QWORD **)(a1 + 32) + 80LL))(*(_QWORD *)(a1 + 32), pv);
      if ( pv )
        CoTaskMemFree(pv);
    }
    else
    {
      ProvisioningDiagnosticsFolderPath = (void **)ProvisioningPaths::GetProvisioningDiagnosticsFolderPath();
      v9 = 7;
      Src[2] = 0;
      LOWORD(Src[0]) = 0;
      std::wstring::assign(Src, ProvisioningDiagnosticsFolderPath, 0, 0xFFFFFFFFFFFFFFFFuLL);
      std::wstring::append(Src, L"DeviceProvisioning-Diagnostics-GetLogs.cab");
      v5 = Src;
      if ( v9 >= 8 )
        v5 = (void **)Src[0];
      (*(void (__fastcall **)(_QWORD, void **))(**(_QWORD **)(a1 + 32) + 80LL))(*(_QWORD *)(a1 + 32), v5);
      if ( v9 >= 8 )
        operator delete(Src[0]);
    }
  }
  return wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(*(_QWORD *)(a1 + 40));
}

```

## disassembly

```asm
0x18000ebbc  mov     [rsp-8+arg_8], rdi
0x18000ebc1  push    rbp
0x18000ebc2  mov     rbp, rsp
0x18000ebc5  sub     rsp, 60h
0x18000ebc9  mov     rax, cs:__security_cookie
0x18000ebd0  xor     rax, rsp
0x18000ebd3  mov     [rbp+var_8], rax
0x18000ebd7  mov     rdi, rcx
0x18000ebda  mov     rdx, [rcx+8]
0x18000ebde  mov     rcx, [rcx]
0x18000ebe1  mov     edx, [rdx]; unsigned int
0x18000ebe3  mov     rcx, [rcx]; struct IMVEngine *
0x18000ebe6  call    ?PostProvisioningActivities@@YAXPEAUIMVEngine@@K@Z; PostProvisioningActivities(IMVEngine *,ulong)
0x18000ebeb  mov     rax, [rdi+10h]
0x18000ebef  cmp     byte ptr [rax], 0
0x18000ebf2  jz      short loc_18000EC32
0x18000ebf4  mov     dword ptr [rbp+pv], 1
0x18000ebfb  mov     qword ptr [rsp+60h+var_40], 0; int
0x18000ec04  mov     r9d, 4
0x18000ec0a  lea     r8, [rbp+pv]
0x18000ec0e  xor     edx, edx
0x18000ec10  mov     rcx, cs:WNF_DEVM_PROVISIONING_COMPLETE
0x18000ec17  call    cs:__imp_RtlPublishWnfStateData
0x18000ec1d  mov     rcx, [rbp+8]; this
0x18000ec21  test    eax, eax
0x18000ec23  jns     short loc_18000EC32
0x18000ec25  mov     r9d, eax; char *
0x18000ec28  mov     edx, 2E0h; void *
0x18000ec2d  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18000ec32  mov     rax, [rdi+18h]
0x18000ec36  cmp     dword ptr [rax], 0
0x18000ec39  jnz     loc_18000ECF7
0x18000ec3f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix> `wil::Feature<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::GetImpl(void)'::`2'::impl
0x18000ec46  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::__private_IsEnabled(void)
0x18000ec4b  test    al, al
0x18000ec4d  jz      short loc_18000EC88
0x18000ec4f  mov     [rbp+pv], 0
0x18000ec57  lea     rcx, [rbp+pv]; unsigned __int16 **
0x18000ec5b  call    ?GetOOBEProvisioningLogsPath@ProvOperations@@SAJPEAPEAG@Z; ProvOperations::GetOOBEProvisioningLogsPath(ushort * *)
0x18000ec60  mov     rcx, [rdi+20h]
0x18000ec64  mov     rax, [rcx]
0x18000ec67  mov     rdx, [rbp+pv]
0x18000ec6b  mov     rax, [rax+50h]
0x18000ec6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec74  nop
0x18000ec75  cmp     [rbp+pv], 0
0x18000ec7a  jz      short loc_18000ECF7
0x18000ec7c  mov     rcx, [rbp+pv]; pv
0x18000ec80  call    cs:__imp_CoTaskMemFree
0x18000ec86  jmp     short loc_18000ECF7
0x18000ec88  call    ?GetProvisioningDiagnosticsFolderPath@ProvisioningPaths@@SAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvisioningPaths::GetProvisioningDiagnosticsFolderPath(void)
0x18000ec8d  mov     [rbp+var_10], 7
0x18000ec95  mov     [rbp+var_18], 0
0x18000ec9d  xor     ecx, ecx
0x18000ec9f  mov     word ptr [rbp+Src], cx
0x18000eca3  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000eca7  xor     r8d, r8d
0x18000ecaa  mov     rdx, rax
0x18000ecad  lea     rcx, [rbp+Src]; void *
0x18000ecb1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000ecb6  nop
0x18000ecb7  lea     rdx, aDeviceprovisio_0; "DeviceProvisioning-Diagnostics-GetLogs."...
0x18000ecbe  lea     rcx, [rbp+Src]; Src
0x18000ecc2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000ecc7  mov     rcx, [rdi+20h]
0x18000eccb  mov     rax, [rcx]
0x18000ecce  lea     rdx, [rbp+Src]
0x18000ecd2  cmp     [rbp+var_10], 8
0x18000ecd7  cmovnb  rdx, [rbp+Src]
0x18000ecdc  mov     rax, [rax+50h]
0x18000ece0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ece5  nop
0x18000ece6  cmp     [rbp+var_10], 8
0x18000eceb  jb      short loc_18000ECF7
0x18000eced  mov     rcx, [rbp+Src]
0x18000ecf1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ecf7  mov     rcx, [rdi+28h]
0x18000ecfb  call    ?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000ed00  mov     rcx, [rbp+var_8]
0x18000ed04  xor     rcx, rsp; StackCookie
0x18000ed07  call    __security_check_cookie
0x18000ed0c  mov     rdi, [rsp+60h+arg_8]
0x18000ed11  add     rsp, 60h
0x18000ed15  pop     rbp
0x18000ed16  retn
```

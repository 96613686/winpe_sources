# AlpcConnectionServer::Run(ushort const *)

- ea: `0x18007056c`
- end: `0x18007073f`
- name: `?Run@AlpcConnectionServer@@QEAAXPEBG@Z`
- size: `467`
- prototype: `void __fastcall(AlpcConnectionServer *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006eda0`

## callees

- `0x180003220`
- `0x180004100`
- `0x18001a234`
- `0x18001bae4`
- `0x18006fd44`
- `0x18006ffac`
- `0x18007056c`
- `0x180070a4c`

## import_xrefs

- `ntdll!TpAllocAlpcCompletion` at `0x1800706d0`
- `ntdll!TpAllocAlpcCompletion` at `0x1800706d0`
- `ntdll!NtAlpcCreatePort` at `0x180070695`
- `ntdll!NtAlpcCreatePort` at `0x180070695`
- `ntdll!RtlInitUnicodeString` at `0x1800705cb`
- `ntdll!RtlInitUnicodeString` at `0x1800705cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800706f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800706f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070709`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007071d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007071d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007061f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007061f`

## pseudocode

```c
void __fastcall AlpcConnectionServer::Run(AlpcConnectionServer *this, const unsigned __int16 *a2)
{
  void **v3; // rbx
  unsigned int v4; // r8d
  int v5; // r9d
  void *v6; // rcx
  void *v7; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-89h] BYREF
  __int128 v9; // [rsp+38h] [rbp-81h] BYREF
  __int128 v10; // [rsp+48h] [rbp-71h]
  __int128 v11; // [rsp+58h] [rbp-61h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-51h] BYREF
  int v13; // [rsp+80h] [rbp-39h] BYREF
  __int64 v14; // [rsp+84h] [rbp-35h]
  __int16 v15; // [rsp+8Ch] [rbp-2Dh]
  __int64 v16; // [rsp+90h] [rbp-29h]
  __int64 v17; // [rsp+98h] [rbp-21h]
  __int64 v18; // [rsp+A0h] [rbp-19h]
  __int64 v19; // [rsp+A8h] [rbp-11h]
  __int64 v20; // [rsp+B0h] [rbp-9h]
  __int64 v21; // [rsp+B8h] [rbp-1h]
  int v22; // [rsp+C0h] [rbp+7h]

  DestinationString = 0;
  memset_0(&v13, 0, 0x48u);
  v9 = 0;
  SecurityDescriptor = 0;
  v10 = 0;
  v11 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\RPC Control\\FconAlpcPort");
  v16 = 56;
  v18 = 0xFFFFFFFFLL;
  v19 = 0xFFFFFFFFLL;
  v21 = 0xFFFFFFFFLL;
  v20 = 0xFFFFFFFFLL;
  v22 = 0;
  v17 = 0;
  v14 = 12;
  v15 = 1;
  v13 = 0x20000;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:SYD:", 1u, &SecurityDescriptor, 0) )
  {
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      (char *)this + 48,
      1);
    if ( *((_QWORD *)this + 6) )
    {
      _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        (char *)this + 56,
        1);
      if ( *((_QWORD *)this + 7) )
      {
        LODWORD(v9) = 48;
        *(_QWORD *)&v10 = &DestinationString;
        v3 = (void **)((char *)this + 16);
        v11 = (unsigned __int64)SecurityDescriptor;
        *((_QWORD *)&v9 + 1) = 0;
        DWORD2(v10) = 64;
        if ( (int)NtAlpcCreatePort((char *)this + 16, &v9, &v13) >= 0 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix>::GetImpl'::`2'::impl) )
            _InterlockedExchange64((volatile __int64 *)this + 4, GetAlpcPortSequenceNumber(*v3));
          if ( (int)TpAllocAlpcCompletion(this, *v3, AlpcConnectionServer::ProcessMessageStatic, this, 0) >= 0 )
          {
            wil::handle_wait(*((wil **)this + 6), (void *)0xFFFFFFFFLL, v4, v5);
            AlpcConnectionServer::InitiateServerShutdown(this);
          }
        }
      }
    }
  }
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 3) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 2);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 2) = 0;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
}

```

## disassembly

```asm
0x18007056c  push    rbp
0x18007056e  push    rbx
0x18007056f  push    rsi
0x180070570  push    rdi
0x180070571  push    r12
0x180070573  push    r14
0x180070575  lea     rbp, [rsp-2Fh]
0x18007057a  sub     rsp, 0E8h
0x180070581  mov     rax, cs:__security_cookie
0x180070588  xor     rax, rsp
0x18007058b  mov     [rbp+57h+var_40], rax
0x18007058f  xor     edx, edx; Val
0x180070591  mov     rdi, rcx
0x180070594  xorps   xmm0, xmm0
0x180070597  lea     rcx, [rbp+57h+var_90]; void *
0x18007059b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18007059f  lea     r8d, [rdx+48h]; Size
0x1800705a3  call    memset_0
0x1800705a8  xorps   xmm0, xmm0
0x1800705ab  lea     rdx, aRpcControlFcon; "\\RPC Control\\FconAlpcPort"
0x1800705b2  xor     r14d, r14d
0x1800705b5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800705b9  movups  [rsp+110h+var_D8], xmm0
0x1800705be  mov     [rsp+110h+SecurityDescriptor], r14
0x1800705c3  movups  [rbp+57h+var_C8], xmm0
0x1800705c7  movups  [rbp+57h+var_B8], xmm0
0x1800705cb  call    cs:__imp_RtlInitUnicodeString
0x1800705d1  mov     r12d, 0FFFFFFFFh
0x1800705d7  mov     [rbp+57h+var_80], 38h ; '8'
0x1800705df  xor     r9d, r9d; SecurityDescriptorSize
0x1800705e2  mov     [rbp+57h+var_70], r12
0x1800705e6  lea     r8, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x1800705eb  mov     [rbp+57h+var_68], r12
0x1800705ef  lea     edx, [r14+1]; StringSDRevision
0x1800705f3  mov     [rbp+57h+var_58], r12
0x1800705f7  lea     rcx, aOSyd; "O:SYD:"
0x1800705fe  mov     [rbp+57h+var_60], r12
0x180070602  mov     [rbp+57h+var_50], r14d
0x180070606  mov     [rbp+57h+var_78], r14
0x18007060a  mov     [rbp+57h+var_8C], 0Ch
0x180070612  mov     [rbp+57h+var_84], 1
0x180070618  mov     [rbp+57h+var_90], 20000h
0x18007061f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180070625  test    eax, eax
0x180070627  jz      loc_1800706ED
0x18007062d  lea     rsi, [rdi+30h]
0x180070631  mov     rcx, rsi
0x180070634  lea     edx, [r14+1]
0x180070638  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18007063d  cmp     [rsi], r14
0x180070640  jz      loc_1800706ED
0x180070646  lea     edx, [r14+1]
0x18007064a  lea     rcx, [rdi+38h]
0x18007064e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180070653  cmp     [rdi+38h], r14
0x180070657  jz      loc_1800706ED
0x18007065d  lea     rax, [rbp+57h+DestinationString]
0x180070661  mov     dword ptr [rsp+110h+var_D8], 30h ; '0'
0x180070669  mov     qword ptr [rbp+57h+var_C8], rax
0x18007066d  lea     rbx, [rdi+10h]
0x180070671  mov     rax, [rsp+110h+SecurityDescriptor]
0x180070676  lea     r8, [rbp+57h+var_90]
0x18007067a  lea     rdx, [rsp+110h+var_D8]
0x18007067f  mov     qword ptr [rbp+57h+var_B8], rax
0x180070683  mov     rcx, rbx
0x180070686  mov     qword ptr [rbp+57h+var_D8+8], r14
0x18007068a  mov     dword ptr [rbp+57h+var_C8+8], 40h ; '@'
0x180070691  mov     qword ptr [rbp+57h+var_B8+8], r14
0x180070695  call    cs:__imp_NtAlpcCreatePort
0x18007069b  test    eax, eax
0x18007069d  js      short loc_1800706ED
0x18007069f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix>::GetImpl(void)'::`2'::impl
0x1800706a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix>::__private_IsEnabled(void)
0x1800706ab  test    al, al
0x1800706ad  jz      short loc_1800706BB
0x1800706af  mov     rcx, [rbx]; void *
0x1800706b2  call    ?GetAlpcPortSequenceNumber@@YA_KPEAX@Z; GetAlpcPortSequenceNumber(void *)
0x1800706b7  xchg    rax, [rdi+20h]
0x1800706bb  mov     rdx, [rbx]
0x1800706be  lea     r8, ?ProcessMessageStatic@AlpcConnectionServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_ALPC@@@Z; AlpcConnectionServer::ProcessMessageStatic(_TP_CALLBACK_INSTANCE *,void *,_TP_ALPC *)
0x1800706c5  mov     r9, rdi
0x1800706c8  mov     [rsp+110h+var_F0], r14
0x1800706cd  mov     rcx, rdi
0x1800706d0  call    cs:__imp_TpAllocAlpcCompletion
0x1800706d6  test    eax, eax
0x1800706d8  js      short loc_1800706ED
0x1800706da  mov     rcx, [rsi]; this
0x1800706dd  mov     edx, r12d; void *
0x1800706e0  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x1800706e5  mov     rcx, rdi; this
0x1800706e8  call    ?InitiateServerShutdown@AlpcConnectionServer@@AEAAXXZ; AlpcConnectionServer::InitiateServerShutdown(void)
0x1800706ed  mov     rcx, [rdi+18h]; hObject
0x1800706f1  test    rcx, rcx
0x1800706f4  jz      short loc_180070700
0x1800706f6  call    cs:__imp_CloseHandle
0x1800706fc  mov     [rdi+18h], r14
0x180070700  mov     rcx, [rdi+10h]; hObject
0x180070704  test    rcx, rcx
0x180070707  jz      short loc_180070713
0x180070709  call    cs:__imp_CloseHandle
0x18007070f  mov     [rdi+10h], r14
0x180070713  mov     rcx, [rsp+110h+SecurityDescriptor]; hMem
0x180070718  test    rcx, rcx
0x18007071b  jz      short loc_180070723
0x18007071d  call    cs:__imp_LocalFree
0x180070723  mov     rcx, [rbp+57h+var_40]
0x180070727  xor     rcx, rsp; StackCookie
0x18007072a  call    __security_check_cookie
0x18007072f  add     rsp, 0E8h
0x180070736  pop     r14
0x180070738  pop     r12
0x18007073a  pop     rdi
0x18007073b  pop     rsi
0x18007073c  pop     rbx
0x18007073d  pop     rbp
0x18007073e  retn
```

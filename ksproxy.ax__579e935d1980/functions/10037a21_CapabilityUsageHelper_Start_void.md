# CapabilityUsageHelper::Start(void)

- ea: `0x10037a21`
- end: `0x10037acf`
- name: `?Start@CapabilityUsageHelper@@QAEJXZ`
- size: `174`
- prototype: `int __thiscall(CapabilityUsageHelper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10015dd0`

## callees

- `0x100075ad`
- `0x1000f693`
- `0x1000f70b`
- `0x10037a21`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10037a94`
- `KERNEL32!GetLastError` at `0x10037a94`
- `KERNEL32!CreateThread` at `0x10037a7d`
- `KERNEL32!CreateThread` at `0x10037a7d`
- `KERNEL32!LeaveCriticalSection` at `0x10037ac2`
- `KERNEL32!LeaveCriticalSection` at `0x10037ac2`
- `KERNEL32!EnterCriticalSection` at `0x10037a30`
- `KERNEL32!EnterCriticalSection` at `0x10037a30`

## pseudocode

```c
int __thiscall CapabilityUsageHelper::Start(CapabilityUsageHelper *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // edi
  _DWORD *v3; // ebx
  int event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z; // esi
  HANDLE Thread; // eax
  signed int LastError; // eax
  int v8; // [esp-10h] [ebp-20h]
  int v9; // [esp-Ch] [ebp-1Ch]
  int v10; // [esp-8h] [ebp-18h]
  int v11; // [esp-4h] [ebp-14h]
  unsigned int v12; // [esp+0h] [ebp-10h]
  const char *v13; // [esp+4h] [ebp-Ch]
  int v14; // [esp+8h] [ebp-8h]
  LPVOID *v15; // [esp+Ch] [ebp-4h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 20);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 20));
  v3 = (_DWORD *)((char *)this + 16);
  if ( *((_DWORD *)this + 4) && *v3 != -1 )
  {
    event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z = -2147418113;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityusagehelper.cpp",
      (void *)event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z,
      v12,
      v13,
      v14);
    goto LABEL_11;
  }
  v15 = (LPVOID *)((char *)this + 12);
  event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z((char *)this + 12, v8, v9, v10, v11);
  if ( event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z < 0 )
    goto LABEL_10;
  event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z = 0;
  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CapabilityUsageHelper::StartInternal, *v15, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__stdcall *)(void *),&int CloseHandle(void *)>>::reset(Thread);
  if ( !*v3 || *v3 == -1 )
  {
    LastError = GetLastError();
    event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z = LastError;
    if ( event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z < 0 )
      goto LABEL_10;
  }
LABEL_11:
  if ( v2 )
    LeaveCriticalSection(v2);
  return event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z;
}

```

## disassembly

```asm
0x10037a21  mov     edi, edi
0x10037a23  push    ebp
0x10037a24  mov     ebp, esp
0x10037a26  push    ecx
0x10037a27  push    ebx; int
0x10037a28  push    esi; char *
0x10037a29  mov     esi, ecx
0x10037a2b  push    edi; unsigned int
0x10037a2c  lea     edi, [esi+14h]
0x10037a2f  push    edi; lpCriticalSection
0x10037a30  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10037a36  lea     ebx, [esi+10h]
0x10037a39  cmp     dword ptr [ebx], 0
0x10037a3c  jz      short loc_10037A4C
0x10037a3e  cmp     dword ptr [ebx], 0FFFFFFFFh
0x10037a41  jz      short loc_10037A4C
0x10037a43  mov     esi, 8000FFFFh
0x10037a48  push    1Fh
0x10037a4a  jmp     short loc_10037A64
0x10037a4c  lea     eax, [esi+0Ch]
0x10037a4f  sub     esp, 10h
0x10037a52  mov     ecx, eax
0x10037a54  mov     [ebp+var_4], eax
0x10037a57  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJW4EventOptions@2@PBGPAU_SECURITY_ATTRIBUTES@@PA_N@Z
0x10037a5c  mov     esi, eax
0x10037a5e  test    esi, esi
0x10037a60  jns     short loc_10037A6D
0x10037a62  push    23h ; '#'
0x10037a64  pop     edx
0x10037a65  push    esi
0x10037a66  push    offset aMultimediaDsho; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10037a6b  jmp     short loc_10037AB5
0x10037a6d  mov     eax, [ebp+var_4]
0x10037a70  xor     esi, esi
0x10037a72  push    esi; lpThreadId
0x10037a73  push    esi; dwCreationFlags
0x10037a74  push    dword ptr [eax]; lpParameter
0x10037a76  push    offset ?StartInternal@CapabilityUsageHelper@@CGKPAX@Z; lpStartAddress
0x10037a7b  push    esi; dwStackSize
0x10037a7c  push    esi; lpThreadAttributes
0x10037a7d  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x10037a83  push    eax
0x10037a84  mov     ecx, ebx
0x10037a86  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6GHPAX@Z$1?CloseHandle@@YGH0@Z@details@wil@@@details@wil@@QAEXPAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x10037a8b  cmp     [ebx], esi
0x10037a8d  jz      short loc_10037A94
0x10037a8f  cmp     dword ptr [ebx], 0FFFFFFFFh
0x10037a92  jnz     short loc_10037ABD
0x10037a94  call    ds:__imp__GetLastError@0; GetLastError()
0x10037a9a  movzx   esi, ax
0x10037a9d  or      esi, 80070000h
0x10037aa3  test    eax, eax
0x10037aa5  cmovle  esi, eax
0x10037aa8  test    esi, esi
0x10037aaa  jns     short loc_10037ABD
0x10037aac  push    esi; void *
0x10037aad  push    offset aMultimediaDsho; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10037ab2  push    26h ; '&'
0x10037ab4  pop     edx
0x10037ab5  mov     ecx, [ebp+4]
0x10037ab8  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10037abd  test    edi, edi
0x10037abf  jz      short loc_10037AC8
0x10037ac1  push    edi; lpCriticalSection
0x10037ac2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037ac8  pop     edi
0x10037ac9  mov     eax, esi
0x10037acb  pop     esi
0x10037acc  pop     ebx
0x10037acd  leave
0x10037ace  retn
```

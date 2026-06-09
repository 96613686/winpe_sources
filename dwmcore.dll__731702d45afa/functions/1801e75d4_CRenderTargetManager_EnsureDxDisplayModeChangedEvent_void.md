# CRenderTargetManager::EnsureDxDisplayModeChangedEvent(void)

- ea: `0x1801e75d4`
- end: `0x1801e76b4`
- name: `?EnsureDxDisplayModeChangedEvent@CRenderTargetManager@@AEAAJXZ`
- size: `224`
- prototype: `__int64 __fastcall(CRenderTargetManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016b10`

## callees

- `0x180050270`
- `0x18015adb4`
- `0x1801e75d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801e7686`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801e7686`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801e760f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801e760f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7631`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7631`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801e76a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801e76a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801e7627`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801e7627`

## pseudocode

```c
__int64 __fastcall CRenderTargetManager::EnsureDxDisplayModeChangedEvent(CRenderTargetManager *this)
{
  signed int v1; // ebx
  char *v2; // rdi
  unsigned __int64 v3; // rax
  signed int LastError; // eax
  HANDLE v5; // rax
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  v2 = (char *)this + 696;
  v3 = *((_QWORD *)this + 87) - 1LL;
  SecurityDescriptor = 0;
  if ( v3 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    *(_QWORD *)&EventAttributes.nLength = 24;
    EventAttributes.lpSecurityDescriptor = 0;
    *(_QWORD *)&EventAttributes.bInheritHandle = 0;
    SetLastError(0);
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;0x00100002;;;WD)", 1u, &SecurityDescriptor, 0) )
    {
      v5 = CreateEventW(&EventAttributes, 1, 0, L"DWM_DX_FULLSCREEN_TRANSITION_EVENT");
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v2,
        v5);
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( v1 >= 0 )
        v1 = -2003304445;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v1, 0x1Cu, 0);
    }
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1801e75d4  mov     r11, rsp
0x1801e75d7  mov     [r11+10h], rbx
0x1801e75db  push    rdi
0x1801e75dc  sub     rsp, 50h
0x1801e75e0  xor     ebx, ebx
0x1801e75e2  lea     rdi, [rcx+2B8h]
0x1801e75e9  mov     rax, [rdi]
0x1801e75ec  dec     rax
0x1801e75ef  mov     [r11+8], rbx
0x1801e75f3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e75f7  jbe     loc_1801E76A7
0x1801e75fd  xor     ecx, ecx; dwErrCode
0x1801e75ff  mov     qword ptr [r11-28h], 18h
0x1801e7607  mov     [r11-20h], rbx
0x1801e760b  mov     [r11-18h], rbx
0x1801e760f  call    cs:__imp_SetLastError
0x1801e7615  xor     r9d, r9d; SecurityDescriptorSize
0x1801e7618  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x1801e761d  lea     edx, [rbx+1]; StringSDRevision
0x1801e7620  lea     rcx, aDA0x00100002Wd; "D:(A;;0x00100002;;;WD)"
0x1801e7627  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801e762d  test    eax, eax
0x1801e762f  jnz     short loc_1801E7673
0x1801e7631  call    cs:__imp_GetLastError
0x1801e7637  mov     ebx, eax
0x1801e7639  test    eax, eax
0x1801e763b  jle     short loc_1801E7646
0x1801e763d  movzx   ebx, ax
0x1801e7640  or      ebx, 80070000h
0x1801e7646  test    ebx, ebx
0x1801e7648  mov     [rsp+58h+var_30], 0; void *
0x1801e7651  mov     eax, 88980003h
0x1801e7656  mov     [rsp+58h+var_38], 1Ch; unsigned int
0x1801e765e  cmovns  ebx, eax
0x1801e7661  xor     edx, edx; int *
0x1801e7663  mov     r9d, ebx; int
0x1801e7666  xor     r8d, r8d; unsigned int
0x1801e7669  lea     ecx, [rdx+14h]; unsigned int
0x1801e766c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801e7671  jmp     short loc_1801E7697
0x1801e7673  xor     r8d, r8d; bInitialState
0x1801e7676  lea     r9, aDwmDxFullscree; "DWM_DX_FULLSCREEN_TRANSITION_EVENT"
0x1801e767d  lea     rcx, [rsp+58h+EventAttributes]; lpEventAttributes
0x1801e7682  lea     edx, [r8+1]; bManualReset
0x1801e7686  call    cs:__imp_CreateEventW
0x1801e768c  mov     rdx, rax
0x1801e768f  mov     rcx, rdi
0x1801e7692  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801e7697  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x1801e769c  test    rcx, rcx
0x1801e769f  jz      short loc_1801E76A7
0x1801e76a1  call    cs:__imp_LocalFree
0x1801e76a7  mov     eax, ebx
0x1801e76a9  mov     rbx, [rsp+58h+arg_8]
0x1801e76ae  add     rsp, 50h
0x1801e76b2  pop     rdi
0x1801e76b3  retn
```

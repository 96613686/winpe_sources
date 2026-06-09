# Container::Manager::Core::Details::SystemConfigurationManager::Start(void)

- ea: `0x1800fbbfc`
- end: `0x1800fbeb9`
- name: `?Start@SystemConfigurationManager@Details@Core@Manager@Container@@QEAAJXZ`
- size: `701`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::SystemConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180075fb8`

## callees

- `0x18000dab0`
- `0x1800fbbfc`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbce7`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbdc9`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbe07`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbe36`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbe6c`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbe9b`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbce7`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbdc9`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbe07`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbe36`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbe6c`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800fbe9b`
- `ntdll!RtlQueryFeatureConfigurationChangeStamp` at `0x1800fbc72`
- `ntdll!RtlQueryFeatureConfigurationChangeStamp` at `0x1800fbc72`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800fbcb0`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800fbd92`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800fbcb0`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800fbd92`
- `ntdll!NtQueryWnfStateData` at `0x1800fbc45`
- `ntdll!NtQueryWnfStateData` at `0x1800fbd4a`
- `ntdll!NtQueryWnfStateData` at `0x1800fbc45`
- `ntdll!NtQueryWnfStateData` at `0x1800fbd4a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fbd06`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fbd06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbdf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbe5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbdf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbe5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fbe15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fbe7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fbe15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fbe7a`

## string_xrefs

- `0x1800fbc59`: `onecore\base\gendrv\silos\clem\core\lib\systemconfigurationmanager.cpp`
- `0x1800fbccd`: `onecore\base\gendrv\silos\clem\core\lib\systemconfigurationmanager.cpp`
- `0x1800fbda6`: `onecore\base\gendrv\silos\clem\core\lib\systemconfigurationmanager.cpp`

## pseudocode

```c
int __fastcall Container::Manager::Core::Details::SystemConfigurationManager::Start(
        Container::Manager::Core::Details::SystemConfigurationManager *this)
{
  int v2; // eax
  __int64 v4; // rax
  __int64 v5; // r8
  int v6; // eax
  __int64 v7; // rdx
  int v8; // ebx
  struct _TP_WORK *v9; // rcx
  int v10; // eax
  __int64 *v11; // rsi
  __int64 v12; // r14
  __int64 v13; // r15
  DWORD LastError; // ebx
  __int64 v15; // rcx
  __int64 *v16; // rdi
  __int64 v17; // rsi
  __int64 v18; // r14
  DWORD v19; // ebx
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-40h]
  __int64 v22; // [rsp+48h] [rbp-18h] BYREF
  __int64 v23; // [rsp+50h] [rbp-10h] BYREF
  int v24[2]; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned int v26; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v27; // [rsp+B0h] [rbp+50h] BYREF
  int v28; // [rsp+B8h] [rbp+58h]

  v28 = 8;
  v26 = 0;
  *(_QWORD *)v24 = 0;
  v2 = NtQueryWnfStateData(&WNF_CMFC_HOST_OS_FEATURE_CONFIGURATION_CHANGED, 0, 0, &v26);
  if ( v2 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x1B5,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
             (const char *)(unsigned int)v2,
             (int)v24);
  v4 = RtlQueryFeatureConfigurationChangeStamp();
  v5 = v26;
  *((_QWORD *)this + 13) = v4;
  v22 = 0;
  v21 = (int)this;
  v6 = RtlSubscribeWnfStateChangeNotification(
         &v22,
         WNF_CMFC_HOST_OS_FEATURE_CONFIGURATION_CHANGED,
         v5,
         Container::Manager::Core::Details::SystemConfigurationManager::FeaturesChangedWnfCallback);
  if ( v6 < 0 )
  {
    *((_QWORD *)this + 13) = 0;
    v7 = 463;
LABEL_5:
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v7,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
           (const char *)(unsigned int)v6,
           v21);
LABEL_6:
    if ( v22 )
      RtlUnsubscribeWnfStateChangeNotification(v22);
    return v8;
  }
  v9 = (struct _TP_WORK *)*((_QWORD *)this + 29);
  if ( v9 )
  {
    SubmitThreadpoolWork(v9);
  }
  else if ( *((_BYTE *)this + 153) )
  {
    v27 = 0;
    v21 = 0;
    v6 = NtQueryWnfStateData(&WNF_SPLT_SYSTEM_UPDATE, 0, 0, &v27);
    if ( v6 < 0 )
    {
      v7 = 483;
      goto LABEL_5;
    }
    v23 = 0;
    v10 = RtlSubscribeWnfStateChangeNotification(
            &v23,
            WNF_SPLT_SYSTEM_UPDATE,
            v27,
            Container::Manager::Core::Details::SystemConfigurationManager::SystemUpdateWnfCallback);
    if ( v10 < 0 )
    {
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x1EE,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
             (const char *)(unsigned int)v10,
             (int)this);
      if ( v23 )
        RtlUnsubscribeWnfStateChangeNotification(v23);
      goto LABEL_6;
    }
    v11 = (__int64 *)((char *)this + 128);
    if ( (__int64 *)((char *)this + 128) == &v23 )
    {
      v15 = v23;
    }
    else
    {
      v12 = *v11;
      v13 = v23;
      if ( *v11 )
      {
        LastError = GetLastError();
        RtlUnsubscribeWnfStateChangeNotification(v12);
        SetLastError(LastError);
      }
      v15 = 0;
      *v11 = v13;
      v23 = 0;
    }
    if ( v15 )
      RtlUnsubscribeWnfStateChangeNotification(v15);
  }
  v16 = (__int64 *)((char *)this + 96);
  if ( v16 == &v22 )
  {
    v20 = v22;
  }
  else
  {
    v17 = *v16;
    v18 = v22;
    if ( *v16 )
    {
      v19 = GetLastError();
      RtlUnsubscribeWnfStateChangeNotification(v17);
      SetLastError(v19);
    }
    v20 = 0;
    *v16 = v18;
    v22 = 0;
  }
  if ( v20 )
    RtlUnsubscribeWnfStateChangeNotification(v20);
  return 0;
}

```

## disassembly

```asm
0x1800fbbfc  push    rbp
0x1800fbbfe  push    rbx
0x1800fbbff  push    rsi
0x1800fbc00  push    rdi
0x1800fbc01  push    r12
0x1800fbc03  push    r14
0x1800fbc05  push    r15
0x1800fbc07  mov     rbp, rsp
0x1800fbc0a  sub     rsp, 60h
0x1800fbc0e  lea     rax, [rbp+arg_18]
0x1800fbc12  mov     [rbp+arg_18], 8
0x1800fbc19  mov     [rsp+60h+var_38], rax
0x1800fbc1e  lea     r9, [rbp+arg_8]
0x1800fbc22  lea     rax, [rbp+var_8]
0x1800fbc26  mov     rdi, rcx
0x1800fbc29  xor     r12d, r12d
0x1800fbc2c  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800fbc31  xor     r8d, r8d
0x1800fbc34  mov     [rbp+arg_8], r12d
0x1800fbc38  xor     edx, edx
0x1800fbc3a  mov     qword ptr [rbp+var_8], r12
0x1800fbc3e  lea     rcx, WNF_CMFC_HOST_OS_FEATURE_CONFIGURATION_CHANGED
0x1800fbc45  call    cs:__imp_NtQueryWnfStateData
0x1800fbc4c  nop     dword ptr [rax+rax+00h]
0x1800fbc51  test    eax, eax
0x1800fbc53  jns     short loc_1800FBC72
0x1800fbc55  mov     rcx, [rbp+38h]; this
0x1800fbc59  lea     r8, aOnecoreBaseGen_59; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fbc60  mov     r9d, eax; char *
0x1800fbc63  mov     edx, 1B5h; void *
0x1800fbc68  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800fbc6d  jmp     loc_1800FBEA9
0x1800fbc72  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1800fbc79  nop     dword ptr [rax+rax+00h]
0x1800fbc7e  mov     r8d, [rbp+arg_8]
0x1800fbc82  lea     r9, ?FeaturesChangedWnfCallback@SystemConfigurationManager@Details@Core@Manager@Container@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Container::Manager::Core::Details::SystemConfigurationManager::FeaturesChangedWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800fbc89  mov     [rsp+60h+var_28], r12d
0x1800fbc8e  lea     rcx, [rbp+var_18]
0x1800fbc92  mov     [rdi+68h], rax
0x1800fbc96  mov     rdx, cs:WNF_CMFC_HOST_OS_FEATURE_CONFIGURATION_CHANGED
0x1800fbc9d  mov     [rsp+60h+var_30], r12d
0x1800fbca2  mov     [rsp+60h+var_38], r12
0x1800fbca7  mov     [rbp+var_18], r12
0x1800fbcab  mov     qword ptr [rsp+60h+var_40], rdi; int
0x1800fbcb0  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800fbcb7  nop     dword ptr [rax+rax+00h]
0x1800fbcbc  test    eax, eax
0x1800fbcbe  jns     short loc_1800FBCFA
0x1800fbcc0  mov     [rdi+68h], r12
0x1800fbcc4  mov     edx, 1CFh; void *
0x1800fbcc9  mov     rcx, [rbp+38h]; this
0x1800fbccd  lea     r8, aOnecoreBaseGen_59; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fbcd4  mov     r9d, eax; char *
0x1800fbcd7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800fbcdc  mov     ebx, eax
0x1800fbcde  mov     rcx, [rbp+var_18]
0x1800fbce2  test    rcx, rcx
0x1800fbce5  jz      short loc_1800FBCF3
0x1800fbce7  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800fbcee  nop     dword ptr [rax+rax+00h]
0x1800fbcf3  mov     eax, ebx
0x1800fbcf5  jmp     loc_1800FBEA9
0x1800fbcfa  mov     rcx, [rdi+0E8h]; pwk
0x1800fbd01  test    rcx, rcx
0x1800fbd04  jz      short loc_1800FBD17
0x1800fbd06  call    cs:__imp_SubmitThreadpoolWork
0x1800fbd0d  nop     dword ptr [rax+rax+00h]
0x1800fbd12  jmp     loc_1800FBE42
0x1800fbd17  cmp     [rdi+99h], r12b
0x1800fbd1e  jz      loc_1800FBE42
0x1800fbd24  lea     rax, [rbp+var_20]
0x1800fbd28  mov     [rbp+arg_10], r12d
0x1800fbd2c  mov     [rsp+60h+var_38], rax
0x1800fbd31  lea     r9, [rbp+arg_10]
0x1800fbd35  xor     r8d, r8d
0x1800fbd38  mov     qword ptr [rsp+60h+var_40], r12
0x1800fbd3d  xor     edx, edx
0x1800fbd3f  mov     [rbp+var_20], r12d
0x1800fbd43  lea     rcx, WNF_SPLT_SYSTEM_UPDATE
0x1800fbd4a  call    cs:__imp_NtQueryWnfStateData
0x1800fbd51  nop     dword ptr [rax+rax+00h]
0x1800fbd56  test    eax, eax
0x1800fbd58  jns     short loc_1800FBD64
0x1800fbd5a  mov     edx, 1E3h
0x1800fbd5f  jmp     loc_1800FBCC9
0x1800fbd64  mov     r8d, [rbp+arg_10]
0x1800fbd68  lea     r9, ?SystemUpdateWnfCallback@SystemConfigurationManager@Details@Core@Manager@Container@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Container::Manager::Core::Details::SystemConfigurationManager::SystemUpdateWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800fbd6f  mov     rdx, cs:WNF_SPLT_SYSTEM_UPDATE
0x1800fbd76  lea     rcx, [rbp+var_10]
0x1800fbd7a  mov     [rsp+60h+var_28], r12d
0x1800fbd7f  mov     [rsp+60h+var_30], r12d
0x1800fbd84  mov     [rsp+60h+var_38], r12
0x1800fbd89  mov     qword ptr [rsp+60h+var_40], rdi; int
0x1800fbd8e  mov     [rbp+var_10], r12
0x1800fbd92  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800fbd99  nop     dword ptr [rax+rax+00h]
0x1800fbd9e  test    eax, eax
0x1800fbda0  jns     short loc_1800FBDDA
0x1800fbda2  mov     rcx, [rbp+38h]; this
0x1800fbda6  lea     r8, aOnecoreBaseGen_59; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fbdad  mov     r9d, eax; char *
0x1800fbdb0  mov     edx, 1EEh; void *
0x1800fbdb5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800fbdba  mov     rcx, [rbp+var_10]
0x1800fbdbe  mov     ebx, eax
0x1800fbdc0  test    rcx, rcx
0x1800fbdc3  jz      loc_1800FBCDE
0x1800fbdc9  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800fbdd0  nop     dword ptr [rax+rax+00h]
0x1800fbdd5  jmp     loc_1800FBCDE
0x1800fbdda  lea     rsi, [rdi+80h]
0x1800fbde1  lea     rax, [rbp+var_10]
0x1800fbde5  cmp     rsi, rax
0x1800fbde8  jz      short loc_1800FBE2D
0x1800fbdea  mov     r14, [rsi]
0x1800fbded  mov     r15, [rbp+var_10]
0x1800fbdf1  test    r14, r14
0x1800fbdf4  jz      short loc_1800FBE21
0x1800fbdf6  call    cs:__imp_GetLastError
0x1800fbdfd  nop     dword ptr [rax+rax+00h]
0x1800fbe02  mov     rcx, r14
0x1800fbe05  mov     ebx, eax
0x1800fbe07  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800fbe0e  nop     dword ptr [rax+rax+00h]
0x1800fbe13  mov     ecx, ebx; dwErrCode
0x1800fbe15  call    cs:__imp_SetLastError
0x1800fbe1c  nop     dword ptr [rax+rax+00h]
0x1800fbe21  mov     rcx, r12
0x1800fbe24  mov     [rsi], r15
0x1800fbe27  mov     [rbp+var_10], rcx
0x1800fbe2b  jmp     short loc_1800FBE31
0x1800fbe2d  mov     rcx, [rbp+var_10]
0x1800fbe31  test    rcx, rcx
0x1800fbe34  jz      short loc_1800FBE42
0x1800fbe36  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800fbe3d  nop     dword ptr [rax+rax+00h]
0x1800fbe42  add     rdi, 60h ; '`'
0x1800fbe46  lea     rax, [rbp+var_18]
0x1800fbe4a  cmp     rdi, rax
0x1800fbe4d  jz      short loc_1800FBE92
0x1800fbe4f  mov     rsi, [rdi]
0x1800fbe52  mov     r14, [rbp+var_18]
0x1800fbe56  test    rsi, rsi
0x1800fbe59  jz      short loc_1800FBE86
0x1800fbe5b  call    cs:__imp_GetLastError
0x1800fbe62  nop     dword ptr [rax+rax+00h]
0x1800fbe67  mov     rcx, rsi
0x1800fbe6a  mov     ebx, eax
0x1800fbe6c  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800fbe73  nop     dword ptr [rax+rax+00h]
0x1800fbe78  mov     ecx, ebx; dwErrCode
0x1800fbe7a  call    cs:__imp_SetLastError
0x1800fbe81  nop     dword ptr [rax+rax+00h]
0x1800fbe86  mov     rcx, r12
0x1800fbe89  mov     [rdi], r14
0x1800fbe8c  mov     [rbp+var_18], rcx
0x1800fbe90  jmp     short loc_1800FBE96
0x1800fbe92  mov     rcx, [rbp+var_18]
0x1800fbe96  test    rcx, rcx
0x1800fbe99  jz      short loc_1800FBEA7
0x1800fbe9b  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800fbea2  nop     dword ptr [rax+rax+00h]
0x1800fbea7  xor     eax, eax
0x1800fbea9  add     rsp, 60h
0x1800fbead  pop     r15
0x1800fbeaf  pop     r14
0x1800fbeb1  pop     r12
0x1800fbeb3  pop     rdi
0x1800fbeb4  pop     rsi
0x1800fbeb5  pop     rbx
0x1800fbeb6  pop     rbp
0x1800fbeb7  retn
```

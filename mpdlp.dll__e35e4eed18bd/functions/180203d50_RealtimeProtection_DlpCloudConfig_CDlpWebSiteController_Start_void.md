# RealtimeProtection::DlpCloudConfig::CDlpWebSiteController::Start(void)

- ea: `0x180203d50`
- end: `0x180203e8e`
- name: `?Start@CDlpWebSiteController@DlpCloudConfig@RealtimeProtection@@QEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpCloudConfig::CDlpWebSiteController *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180202f90`

## callees

- `0x18003d6c8`
- `0x1800809d0`
- `0x180094e70`
- `0x18010cb40`
- `0x180203960`
- `0x180203d50`

## import_xrefs

- `MpClient!MpConfigUnregisterNotifications` at `0x180203db0`
- `MpClient!MpConfigUnregisterNotifications` at `0x180203e29`
- `MpClient!MpConfigUnregisterNotifications` at `0x180203e6a`
- `MpClient!MpConfigUnregisterNotifications` at `0x180203db0`
- `MpClient!MpConfigUnregisterNotifications` at `0x180203e29`
- `MpClient!MpConfigUnregisterNotifications` at `0x180203e6a`
- `MpClient!MpConfigRegisterForNotifications` at `0x180203dd3`
- `MpClient!MpConfigRegisterForNotifications` at `0x180203dd3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180203d9c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180203e1a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180203e4e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180203d9c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180203e1a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180203e4e`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpCloudConfig::CDlpWebSiteController::Start(
        RealtimeProtection::DlpCloudConfig::CDlpWebSiteController *this)
{
  int v2; // edi
  bool v4; // zf
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-20h] BYREF
  char v6; // [rsp+38h] [rbp-18h]
  __int64 v7; // [rsp+40h] [rbp-10h] BYREF

  v7 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(
    &SRWLock,
    (char *)this + 8);
  if ( *((_BYTE *)this + 16) )
  {
    if ( v6 )
      ReleaseSRWLockExclusive(SRWLock);
LABEL_18:
    if ( v7 )
      MpConfigUnregisterNotifications();
    return 0;
  }
  if ( v7 )
    MpConfigUnregisterNotifications();
  v2 = MpConfigRegisterForNotifications(
         L"DLP Websites",
         this,
         RealtimeProtection::DlpCloudConfig::CDlpWebSiteController::OnDlpWebsitePolicyChange,
         0,
         &v7);
  if ( v2 >= 0 )
  {
    CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle>::Swap((char *)this + 24, &v7);
    v4 = v6 == 0;
    *((_BYTE *)this + 16) = 1;
    if ( !v4 )
      ReleaseSRWLockExclusive(SRWLock);
    RealtimeProtection::DlpCloudConfig::CDlpWebSiteController::OnDlpWebsitePolicyChange(this, 2);
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_bf893134e6c73598e2b22c11e9a66e6d_Traceguids, (unsigned int)v2);
  if ( v6 )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v7 )
    MpConfigUnregisterNotifications();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180203d50  mov     [rsp-8+arg_8], rbx
0x180203d55  mov     [rsp-8+arg_10], rdi
0x180203d5a  push    rbp
0x180203d5b  mov     rbp, rsp
0x180203d5e  sub     rsp, 50h
0x180203d62  mov     rax, cs:__security_cookie
0x180203d69  xor     rax, rsp
0x180203d6c  mov     [rbp+var_8], rax
0x180203d70  mov     rbx, rcx
0x180203d73  mov     [rbp+var_10], 0
0x180203d7b  lea     rdx, [rcx+8]
0x180203d7f  lea     rcx, [rbp+SRWLock]
0x180203d83  call    ??0?$CGenericAutoLock@U?$CMpWriteLockFunctor@VCMpSRWLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@AEAVCMpSRWLock@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(CommonUtil::CMpSRWLock &,CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::ENUM_LOCK_INITIAL_STATE)
0x180203d88  cmp     byte ptr [rbx+10h], 0
0x180203d8c  jz      short loc_180203DA7
0x180203d8e  cmp     [rbp+var_18], 0
0x180203d92  jz      loc_180203E61
0x180203d98  mov     rcx, [rbp+SRWLock]; SRWLock
0x180203d9c  call    cs:__imp_ReleaseSRWLockExclusive
0x180203da2  jmp     loc_180203E61
0x180203da7  mov     rcx, [rbp+var_10]
0x180203dab  test    rcx, rcx
0x180203dae  jz      short loc_180203DB6
0x180203db0  call    cs:__imp_MpConfigUnregisterNotifications
0x180203db6  lea     rax, [rbp+var_10]
0x180203dba  xor     r9d, r9d
0x180203dbd  lea     r8, ?OnDlpWebsitePolicyChange@CDlpWebSiteController@DlpCloudConfig@RealtimeProtection@@CAXPEAXW4tagMP_CONFIG_ORIGIN@@@Z; RealtimeProtection::DlpCloudConfig::CDlpWebSiteController::OnDlpWebsitePolicyChange(void *,tagMP_CONFIG_ORIGIN)
0x180203dc4  mov     [rsp+50h+var_30], rax
0x180203dc9  mov     rdx, rbx
0x180203dcc  lea     rcx, aDlpWebsites; "DLP Websites"
0x180203dd3  call    cs:__imp_MpConfigRegisterForNotifications
0x180203dd9  mov     edi, eax
0x180203ddb  test    eax, eax
0x180203ddd  jns     short loc_180203E33
0x180203ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x180203de6  lea     rax, WPP_GLOBAL_Control
0x180203ded  cmp     rcx, rax
0x180203df0  jz      short loc_180203E10
0x180203df2  test    byte ptr [rcx+1Ch], 1
0x180203df6  jz      short loc_180203E10
0x180203df8  mov     rcx, [rcx+10h]
0x180203dfc  lea     r8, WPP_bf893134e6c73598e2b22c11e9a66e6d_Traceguids
0x180203e03  mov     edx, 0Ah
0x180203e08  mov     r9d, edi
0x180203e0b  call    WPP_SF_d
0x180203e10  cmp     [rbp+var_18], 0
0x180203e14  jz      short loc_180203E20
0x180203e16  mov     rcx, [rbp+SRWLock]; SRWLock
0x180203e1a  call    cs:__imp_ReleaseSRWLockExclusive
0x180203e20  mov     rcx, [rbp+var_10]
0x180203e24  test    rcx, rcx
0x180203e27  jz      short loc_180203E2F
0x180203e29  call    cs:__imp_MpConfigUnregisterNotifications
0x180203e2f  mov     eax, edi
0x180203e31  jmp     short loc_180203E72
0x180203e33  lea     rcx, [rbx+18h]
0x180203e37  lea     rdx, [rbp+var_10]
0x180203e3b  call    ?Swap@?$CUniqueHandle@UCAutoCloseBCryptHashHandle@CommonUtil@@@CommonUtil@@QEAAXAEAV12@@Z; CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle>::Swap(CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle> &)
0x180203e40  cmp     [rbp+var_18], 0
0x180203e44  mov     byte ptr [rbx+10h], 1
0x180203e48  jz      short loc_180203E54
0x180203e4a  mov     rcx, [rbp+SRWLock]; SRWLock
0x180203e4e  call    cs:__imp_ReleaseSRWLockExclusive
0x180203e54  mov     edx, 2
0x180203e59  mov     rcx, rbx
0x180203e5c  call    ?OnDlpWebsitePolicyChange@CDlpWebSiteController@DlpCloudConfig@RealtimeProtection@@CAXPEAXW4tagMP_CONFIG_ORIGIN@@@Z; RealtimeProtection::DlpCloudConfig::CDlpWebSiteController::OnDlpWebsitePolicyChange(void *,tagMP_CONFIG_ORIGIN)
0x180203e61  mov     rcx, [rbp+var_10]
0x180203e65  test    rcx, rcx
0x180203e68  jz      short loc_180203E70
0x180203e6a  call    cs:__imp_MpConfigUnregisterNotifications
0x180203e70  xor     eax, eax
0x180203e72  mov     rcx, [rbp+var_8]
0x180203e76  xor     rcx, rsp; StackCookie
0x180203e79  call    __security_check_cookie
0x180203e7e  mov     rbx, [rsp+50h+arg_8]
0x180203e83  mov     rdi, [rsp+50h+arg_10]
0x180203e88  add     rsp, 50h
0x180203e8c  pop     rbp
0x180203e8d  retn
```

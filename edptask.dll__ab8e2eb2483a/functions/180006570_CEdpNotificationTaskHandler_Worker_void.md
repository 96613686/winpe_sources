# CEdpNotificationTaskHandler::Worker(void)

- ea: `0x180006570`
- end: `0x180006690`
- name: `?Worker@CEdpNotificationTaskHandler@@EEAAJXZ`
- size: `288`
- prototype: `__int64 __fastcall(CEdpNotificationTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005e44`
- `0x180006570`
- `0x180012e30`
- `0x180012eb4`
- `0x180012f48`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800065a2`
- `msvcrt!_wcsicmp` at `0x1800065bf`
- `msvcrt!_wcsicmp` at `0x1800065db`
- `msvcrt!_wcsicmp` at `0x1800065f7`
- `msvcrt!_wcsicmp` at `0x18000663a`
- `msvcrt!_wcsicmp` at `0x1800065a2`
- `msvcrt!_wcsicmp` at `0x1800065bf`
- `msvcrt!_wcsicmp` at `0x1800065db`
- `msvcrt!_wcsicmp` at `0x1800065f7`
- `msvcrt!_wcsicmp` at `0x18000663a`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180006618`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180006618`
- `ext-ms-win-security-efs-l1-1-1!FVE_LaunchSDCardUI` at `0x180006628`
- `ext-ms-win-security-efs-l1-1-1!FVE_LaunchSDCardUI` at `0x180006628`

## pseudocode

```c
__int64 __fastcall CEdpNotificationTaskHandler::Worker(CEdpNotificationTaskHandler *this)
{
  const wchar_t *v2; // rdi
  __int64 v3; // rcx
  unsigned int v4; // ebx
  int started; // eax
  int v7; // [rsp+30h] [rbp+8h] BYREF

  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) != 1 )
  {
    v2 = (const wchar_t *)*((_QWORD *)this + 1);
    v4 = 0;
    if ( !_wcsicmp(v2, L"ReAuth") )
    {
      v4 = 1;
      return (unsigned int)CEdpNotificationTaskHandler::ShowToast(v3, v4);
    }
    if ( !_wcsicmp(v2, L"MissingCredentials") )
    {
      v4 = 2;
      return (unsigned int)CEdpNotificationTaskHandler::ShowToast(v3, v4);
    }
    if ( !_wcsicmp(v2, L"BitLockerPolicy") )
    {
      v4 = 3;
      return (unsigned int)CEdpNotificationTaskHandler::ShowToast(v3, v4);
    }
    if ( _wcsicmp(v2, L"SDCardEncryptionPolicy") )
    {
      if ( _wcsicmp(v2, L"BitLockerEncryptAllDrives") )
        return (unsigned int)-2147024809;
      v7 = 0;
      started = BdeSvcApiStartService();
      if ( started < 0 )
        return (unsigned int)started;
      started = BdeSvcApiIsEncryptableFDVPresent(&v7);
      if ( started < 0 )
        return (unsigned int)started;
      if ( !v7 )
        return (unsigned int)CEdpNotificationTaskHandler::ShowToast(v3, v4);
      started = BdeSvcApiEnableSilentBitLocker();
    }
    else
    {
      v7 = 0;
      started = PolicyManager_GetPolicyInt(L"BitLocker", L"RequireStorageCardEncryption", &v7);
      if ( started < 0 )
        return (unsigned int)started;
      if ( v7 != 1 )
        return (unsigned int)CEdpNotificationTaskHandler::ShowToast(v3, v4);
      started = FVE_LaunchSDCardUI();
    }
    if ( started >= 0 )
      return (unsigned int)CEdpNotificationTaskHandler::ShowToast(v3, v4);
    return (unsigned int)started;
  }
  return 0;
}

```

## disassembly

```asm
0x180006570  mov     [rsp+arg_8], rbx
0x180006575  mov     [rsp+arg_10], rsi
0x18000657a  push    rdi
0x18000657b  sub     rsp, 20h
0x18000657f  mov     esi, 1
0x180006584  mov     eax, esi
0x180006586  lock cmpxchg [rcx+24h], esi
0x18000658b  jnz     short loc_180006594
0x18000658d  xor     ebx, ebx
0x18000658f  jmp     loc_18000667E
0x180006594  mov     rdi, [rcx+8]
0x180006598  lea     rdx, aReauth; "ReAuth"
0x18000659f  mov     rcx, rdi; String1
0x1800065a2  call    cs:__imp__wcsicmp
0x1800065a8  xor     ebx, ebx
0x1800065aa  test    eax, eax
0x1800065ac  jnz     short loc_1800065B5
0x1800065ae  mov     ebx, esi
0x1800065b0  jmp     loc_18000666E
0x1800065b5  lea     rdx, aMissingcredent; "MissingCredentials"
0x1800065bc  mov     rcx, rdi; String1
0x1800065bf  call    cs:__imp__wcsicmp
0x1800065c5  test    eax, eax
0x1800065c7  jnz     short loc_1800065D1
0x1800065c9  lea     ebx, [rax+2]
0x1800065cc  jmp     loc_18000666E
0x1800065d1  lea     rdx, aBitlockerpolic; "BitLockerPolicy"
0x1800065d8  mov     rcx, rdi; String1
0x1800065db  call    cs:__imp__wcsicmp
0x1800065e1  test    eax, eax
0x1800065e3  jnz     short loc_1800065ED
0x1800065e5  lea     ebx, [rax+3]
0x1800065e8  jmp     loc_18000666E
0x1800065ed  lea     rdx, aSdcardencrypti; "SDCardEncryptionPolicy"
0x1800065f4  mov     rcx, rdi; String1
0x1800065f7  call    cs:__imp__wcsicmp
0x1800065fd  test    eax, eax
0x1800065ff  jnz     short loc_180006630
0x180006601  lea     r8, [rsp+28h+arg_0]
0x180006606  mov     [rsp+28h+arg_0], ebx
0x18000660a  lea     rdx, aRequirestorage; "RequireStorageCardEncryption"
0x180006611  lea     rcx, aBitlocker; "BitLocker"
0x180006618  call    cs:__imp_PolicyManager_GetPolicyInt
0x18000661e  test    eax, eax
0x180006620  js      short loc_180006675
0x180006622  cmp     [rsp+28h+arg_0], esi
0x180006626  jnz     short loc_18000666E
0x180006628  call    cs:__imp_FVE_LaunchSDCardUI
0x18000662e  jmp     short loc_18000666A
0x180006630  lea     rdx, aBitlockerencry; "BitLockerEncryptAllDrives"
0x180006637  mov     rcx, rdi; String1
0x18000663a  call    cs:__imp__wcsicmp
0x180006640  test    eax, eax
0x180006642  jnz     short loc_180006679
0x180006644  mov     [rsp+28h+arg_0], ebx
0x180006648  call    ?BdeSvcApiStartService@@YAJXZ; BdeSvcApiStartService(void)
0x18000664d  test    eax, eax
0x18000664f  js      short loc_180006675
0x180006651  lea     rcx, [rsp+28h+arg_0]; int *
0x180006656  call    ?BdeSvcApiIsEncryptableFDVPresent@@YAJPEAH@Z; BdeSvcApiIsEncryptableFDVPresent(int *)
0x18000665b  test    eax, eax
0x18000665d  js      short loc_180006675
0x18000665f  cmp     [rsp+28h+arg_0], ebx
0x180006663  jz      short loc_18000666E
0x180006665  call    ?BdeSvcApiEnableSilentBitLocker@@YAJXZ; BdeSvcApiEnableSilentBitLocker(void)
0x18000666a  test    eax, eax
0x18000666c  js      short loc_180006675
0x18000666e  mov     edx, ebx
0x180006670  call    ?ShowToast@CEdpNotificationTaskHandler@@AEAAJW4EdpToastType@@@Z; CEdpNotificationTaskHandler::ShowToast(EdpToastType)
0x180006675  mov     ebx, eax
0x180006677  jmp     short loc_18000667E
0x180006679  mov     ebx, 80070057h
0x18000667e  mov     rsi, [rsp+28h+arg_10]
0x180006683  mov     eax, ebx
0x180006685  mov     rbx, [rsp+28h+arg_8]
0x18000668a  add     rsp, 20h
0x18000668e  pop     rdi
0x18000668f  retn
```

# CDplUser::SaveDplAccountAndKeys(CDplAccount *,int)

- ea: `0x1800bbae0`
- end: `0x1800bc2e6`
- name: `?SaveDplAccountAndKeys@CDplUser@@AEAAJPEAVCDplAccount@@H@Z`
- size: `2054`
- prototype: `__int64 __fastcall(CDplUser *__hidden this, struct CDplAccount *, int)`
- caller_count: `7`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a33f8`
- `0x1800a5bdc`
- `0x1800a9998`
- `0x1800ad2d0`
- `0x1800b0088`
- `0x1800b9364`
- `0x1800bc2ec`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800841d0`
- `0x180088808`
- `0x180095d4c`
- `0x1800961b0`
- `0x1800964ac`
- `0x18009652c`
- `0x1800a4840`
- `0x1800a59c8`
- `0x1800a7244`
- `0x1800a8660`
- `0x1800bbae0`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800d5af8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbf65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbf78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbf65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbf78`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800bc29d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800bc29d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bc06d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bc06d`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800bc207`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800bc263`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800bc2a7`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800bc207`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800bc263`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800bc2a7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bc1dc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bc22c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bc1dc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bc22c`

## pseudocode

```c
__int64 __fastcall CDplUser::SaveDplAccountAndKeys(CDplServiceImpl **this, struct CDplAccount *a2, int a3)
{
  WCHAR *v6; // r14
  WCHAR *v7; // r12
  unsigned __int16 *v8; // rsi
  int v9; // eax
  int v10; // ecx
  unsigned __int64 v11; // rbx
  unsigned int AccountPersistanceName; // ebx
  int v13; // r8d
  int v14; // ecx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  int v17; // ecx
  int v18; // ecx
  CDplServiceImpl *v19; // rcx
  int v20; // r9d
  int v21; // ecx
  CDplServiceImpl **v22; // rsi
  LSTATUS v24; // eax
  int v25; // ecx
  unsigned __int64 v26; // r9
  int v27; // eax
  int v28; // ecx
  const unsigned __int16 *v29; // rdx
  LSTATUS v30; // eax
  LSTATUS v31; // eax
  int v32; // eax
  char dwOptions; // [rsp+20h] [rbp-79h]
  HKEY v34; // [rsp+50h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-41h] BYREF
  int Data; // [rsp+60h] [rbp-39h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-35h] BYREF
  unsigned __int64 v38; // [rsp+68h] [rbp-31h]
  unsigned __int16 *v39; // [rsp+70h] [rbp-29h] BYREF
  LPCWSTR lpSubKey; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int64 v41; // [rsp+80h] [rbp-19h]
  LPCVOID lpData; // [rsp+88h] [rbp-11h] BYREF
  unsigned __int8 *v43; // [rsp+90h] [rbp-9h] BYREF
  unsigned int v44; // [rsp+98h] [rbp-1h] BYREF
  int v45; // [rsp+9Ch] [rbp+3h]
  LPCWSTR lpValueName; // [rsp+A0h] [rbp+7h] BYREF
  void *v47[9]; // [rsp+A8h] [rbp+Fh] BYREF
  unsigned int v49; // [rsp+108h] [rbp+6Fh] BYREF
  int v50; // [rsp+110h] [rbp+77h]
  DWORD dwDisposition; // [rsp+118h] [rbp+7Fh] BYREF

  v50 = a3;
  lpData = 0;
  cbData = 0;
  v6 = 0;
  lpSubKey = 0;
  v7 = 0;
  lpValueName = 0;
  v8 = 0;
  v34 = 0;
  hKey = 0;
  dwDisposition = 0;
  v43 = 0;
  v49 = 0;
  v39 = 0;
  v44 = 0;
  v47[0] = 0;
  Data = 0;
  if ( g_DplDbgBreakEnabled )
    __int2c();
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 121);
  v9 = CDplUser::UserSvcLock((CDplUser *)this);
  v11 = *((_QWORD *)a2 + 16);
  v41 = v11;
  v45 = v9;
  if ( !a3 && (*((_DWORD *)a2 + 41) || *((_DWORD *)a2 + 43)) )
  {
    AccountPersistanceName = -2147418113;
    dwOptions = -126;
    v13 = -2147418113;
LABEL_7:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v13, 40, dwOptions);
    goto LABEL_25;
  }
  if ( *((_DWORD *)a2 + 40) )
  {
    fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 158);
    v15 = *((_QWORD *)a2 + 16);
    v16 = -1;
    if ( v15 + 1 >= v15 )
      v16 = v15 + 1;
    v38 = v16;
    AccountPersistanceName = v15 + 1 < v15 ? 0x80070216 : 0;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                AccountPersistanceName,
                40,
                158) < 0 )
      goto LABEL_25;
    fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 165);
    AccountPersistanceName = CDplAccount::MakeAccountPersistanceName(a2, v38, (unsigned __int16 **)&lpSubKey);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                AccountPersistanceName,
                40,
                165) < 0 )
    {
LABEL_24:
      v6 = (WCHAR *)lpSubKey;
      goto LABEL_25;
    }
    *((_QWORD *)a2 + 16) = v38;
  }
  else
  {
    if ( !*((_DWORD *)a2 + 42) )
    {
      AccountPersistanceName = 1;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 40, 138);
      goto LABEL_25;
    }
    fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 150);
    AccountPersistanceName = CDplAccount::MakeAccountPersistanceName(a2, v11, (unsigned __int16 **)&lpSubKey);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                AccountPersistanceName,
                40,
                150) < 0 )
      goto LABEL_24;
    v38 = 0;
  }
  fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 183);
  AccountPersistanceName = CDplAccount::Serialize(a2, (unsigned __int8 **)&lpData, &cbData, &v43, &v49, 0, &Data);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AccountPersistanceName,
              40,
              183) < 0 )
    goto LABEL_24;
  fnEfsLogTrace1Strings(v18, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 189);
  AccountPersistanceName = CDplServiceImpl::Base64Encode(v19, v43, v49, v20, &v39, &v44);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AccountPersistanceName,
              40,
              189) < 0 )
  {
LABEL_23:
    v8 = v39;
    goto LABEL_24;
  }
  if ( *((_DWORD *)a2 + 51) )
  {
    fnEfsLogTrace1Strings(v21, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 198);
    v22 = this;
    AccountPersistanceName = CDplServiceImpl::RevertToSelf(this[6], v47);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                AccountPersistanceName,
                40,
                198) < 0 )
      goto LABEL_23;
  }
  else
  {
    v22 = this;
  }
  fnEfsLogTrace1Strings(v21, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 207);
  AccountPersistanceName = EdpCredSvcOpenUserCredStore((const unsigned __int16 *)v22[13], 0xF003Fu, &v34);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AccountPersistanceName,
              40,
              207) < 0 )
    goto LABEL_23;
  v6 = (WCHAR *)lpSubKey;
  v24 = RegCreateKeyExW(v34, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  AccountPersistanceName = v24;
  if ( v24 )
  {
    if ( v24 > 0 )
      AccountPersistanceName = (unsigned __int16)v24 | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, AccountPersistanceName, 40, 225);
    v8 = v39;
    goto LABEL_25;
  }
  fnEfsLogTrace1Strings(v25, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 237);
  v26 = v38;
  if ( !*((_DWORD *)a2 + 40) )
    v26 = v41;
  AccountPersistanceName = CDplAccount::SaveMetadata(a2, hKey, dwDisposition == 2, v26);
  v27 = fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          AccountPersistanceName,
          40,
          237);
  v8 = v39;
  if ( v27 >= 0 )
  {
    *((_DWORD *)a2 + 43) = 1;
    if ( *((_DWORD *)a2 + 40) )
    {
      fnEfsLogTrace1Strings(v28, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 251);
      AccountPersistanceName = CDplService::RegSetStringValue(hKey, v29, L"AccountHash", v8);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  AccountPersistanceName,
                  40,
                  251) < 0 )
        goto LABEL_25;
      v30 = RegSetKeyValueW(hKey, 0, L"DpapiProtected", 4u, &Data, 4u);
      AccountPersistanceName = v30;
      if ( v30 )
      {
        if ( v30 > 0 )
          AccountPersistanceName = (unsigned __int16)v30 | 0x80070000;
        dwOptions = 6;
LABEL_55:
        v13 = AccountPersistanceName;
        goto LABEL_7;
      }
      RegFlushKey(hKey);
      v31 = RegSetKeyValueW(v34, 0, v6, 3u, lpData, cbData);
      AccountPersistanceName = v31;
      if ( v31 )
      {
        if ( v31 > 0 )
          AccountPersistanceName = (unsigned __int16)v31 | 0x80070000;
        dwOptions = 29;
        goto LABEL_55;
      }
      *((_DWORD *)a2 + 41) = 1;
    }
    if ( v50 )
    {
      RegFlushKey(v34);
      if ( *((_DWORD *)a2 + 40) )
      {
        v32 = CDplAccount::MakeAccountPersistanceName(a2, v41, (unsigned __int16 **)&lpValueName);
        v7 = (WCHAR *)lpValueName;
        if ( v32 >= 0 )
        {
          CDplService::RegDeleteValueSecurely(v34, lpValueName);
          RegDeleteTreeW(v34, v7);
          RegFlushKey(v34);
        }
        v41 = v38;
        *((_DWORD *)a2 + 40) = 0;
      }
      *((_DWORD *)a2 + 42) = 0;
    }
    v8 = (unsigned __int16 *)_InterlockedExchange64((volatile __int64 *)a2 + 19, (__int64)v8);
    AccountPersistanceName = 0;
    if ( v8 )
      CDplAccount::ProcessRecoveryPolicyOnAccountSave(a2, v8);
  }
LABEL_25:
  *((_QWORD *)a2 + 16) = v41;
  CDplServiceImpl::RestoreImpersonation(this[6], v47);
  CDplUser::UserSvcUnlock((CDplUser *)this, v45);
  if ( lpData )
    DplibMemFree((void *)lpData);
  lpData = 0;
  if ( v6 )
    DplibMemFree(v6);
  if ( v7 )
    DplibMemFree(v7);
  if ( v43 )
    DplibMemFree(v43);
  v43 = 0;
  if ( v8 )
    DplibMemFree(v8);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v34 )
  {
    RegCloseKey(v34);
    v34 = 0;
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    AccountPersistanceName,
    40,
    127);
  return AccountPersistanceName;
}

```

## disassembly

```asm
0x1800bbae0  mov     [rsp-8+arg_10], r8d
0x1800bbae5  mov     [rsp-8+arg_0], rcx
0x1800bbaea  push    rbp
0x1800bbaeb  push    rbx
0x1800bbaec  push    rsi
0x1800bbaed  push    rdi
0x1800bbaee  push    r12
0x1800bbaf0  push    r13
0x1800bbaf2  push    r14
0x1800bbaf4  push    r15
0x1800bbaf6  lea     rbp, [rsp-1Fh]
0x1800bbafb  sub     rsp, 0B8h
0x1800bbb02  xor     r13d, r13d
0x1800bbb05  mov     r15d, r8d
0x1800bbb08  cmp     cs:?g_DplDbgBreakEnabled@@3IA, r13d; uint g_DplDbgBreakEnabled
0x1800bbb0f  mov     rdi, rdx
0x1800bbb12  mov     rbx, rcx
0x1800bbb15  mov     [rbp+57h+lpData], r13
0x1800bbb19  mov     [rbp+57h+cbData], r13d
0x1800bbb1d  mov     r14d, r13d
0x1800bbb20  mov     [rbp+57h+lpSubKey], r13
0x1800bbb24  mov     r12d, r13d
0x1800bbb27  mov     [rbp+57h+lpValueName], r13
0x1800bbb2b  mov     esi, r13d
0x1800bbb2e  mov     [rbp+57h+var_A0], r13
0x1800bbb32  mov     [rbp+57h+hKey], r13
0x1800bbb36  mov     [rbp+57h+dwDisposition], r13d
0x1800bbb3a  mov     [rbp+57h+var_60], r13
0x1800bbb3e  mov     [rbp+57h+arg_8], r13d
0x1800bbb42  mov     [rbp+57h+var_80], r13
0x1800bbb46  mov     [rbp+57h+var_58], r13d
0x1800bbb4a  mov     [rbp+57h+var_48], r13
0x1800bbb4e  mov     [rbp+57h+Data], r13d
0x1800bbb52  jz      short loc_1800BBB56
0x1800bbb54  int     2Ch; Windows NT - assertion failure
0x1800bbb56  mov     r9d, 28h ; '('
0x1800bbb5c  mov     [rsp+0F0h+dwOptions], 0D79h
0x1800bbb64  lea     r8, sourceString
0x1800bbb6b  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800bbb72  call    fnEfsLogTrace1Strings
0x1800bbb77  mov     rcx, rbx; this
0x1800bbb7a  call    ?UserSvcLock@CDplUser@@AEAAHXZ; CDplUser::UserSvcLock(void)
0x1800bbb7f  mov     rbx, [rdi+80h]
0x1800bbb86  mov     [rbp+57h+var_70], rbx
0x1800bbb8a  mov     [rbp+57h+var_54], eax
0x1800bbb8d  test    r15d, r15d
0x1800bbb90  jnz     short loc_1800BBBD5
0x1800bbb92  cmp     [rdi+0A4h], r13d
0x1800bbb99  jnz     short loc_1800BBBA4
0x1800bbb9b  cmp     [rdi+0ACh], r13d
0x1800bbba2  jz      short loc_1800BBBD5
0x1800bbba4  mov     ebx, 8000FFFFh
0x1800bbba9  mov     [rsp+0F0h+dwOptions], 0D82h
0x1800bbbb1  mov     r8d, 8000FFFFh
0x1800bbbb7  lea     rdx, EFS_TRACE_ERROR
0x1800bbbbe  mov     rcx, cs:g_hPublisher
0x1800bbbc5  mov     r9d, 28h ; '('
0x1800bbbcb  call    fnEfsLogTrace1
0x1800bbbd0  jmp     loc_1800BBEEA
0x1800bbbd5  cmp     [rdi+0A0h], r13d
0x1800bbbdc  jnz     loc_1800BBC89
0x1800bbbe2  cmp     [rdi+0A8h], r13d
0x1800bbbe9  jnz     short loc_1800BBC08
0x1800bbbeb  mov     r15d, 1
0x1800bbbf1  mov     [rsp+0F0h+dwOptions], 0D8Ah
0x1800bbbf9  mov     ebx, r15d
0x1800bbbfc  lea     rdx, EFS_TRACE_STATUS
0x1800bbc03  mov     r8d, r15d
0x1800bbc06  jmp     short loc_1800BBBBE
0x1800bbc08  mov     r15d, 28h ; '('
0x1800bbc0e  lea     r13, EFS_TRACE_START_EVENT
0x1800bbc15  mov     r14d, 0D96h
0x1800bbc1b  lea     r8, sourceString
0x1800bbc22  mov     r9d, r15d
0x1800bbc25  mov     [rsp+0F0h+dwOptions], r14d
0x1800bbc2a  mov     rdx, r13
0x1800bbc2d  call    fnEfsLogTrace1Strings
0x1800bbc32  lea     r8, [rbp+57h+lpSubKey]; unsigned __int16 **
0x1800bbc36  mov     rdx, rbx; unsigned __int64
0x1800bbc39  mov     rcx, rdi; this
0x1800bbc3c  call    ?MakeAccountPersistanceName@CDplAccount@@AEAAJ_KPEAPEAG@Z; CDplAccount::MakeAccountPersistanceName(unsigned __int64,ushort * *)
0x1800bbc41  mov     rcx, cs:g_hPublisher
0x1800bbc48  lea     r9, sourceString
0x1800bbc4f  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], r14d
0x1800bbc54  mov     ebx, eax
0x1800bbc56  mov     [rsp+0F0h+samDesired], r15d
0x1800bbc5b  lea     r14, EFS_TRACE_COMPLETE_EVENT
0x1800bbc62  lea     r15, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bbc69  mov     [rsp+0F0h+dwOptions], eax
0x1800bbc6d  mov     r8, r15
0x1800bbc70  mov     rdx, r14
0x1800bbc73  call    fnEfsLogTrace1String1Dword
0x1800bbc78  test    eax, eax
0x1800bbc7a  js      loc_1800BBEE3
0x1800bbc80  mov     [rbp+57h+var_88], rsi
0x1800bbc84  jmp     loc_1800BBD85
0x1800bbc89  lea     r13, EFS_TRACE_START_EVENT
0x1800bbc90  mov     r15d, 0D9Eh
0x1800bbc96  mov     rdx, r13
0x1800bbc99  mov     [rsp+0F0h+dwOptions], r15d
0x1800bbc9e  mov     r9d, 28h ; '('
0x1800bbca4  lea     r8, sourceString
0x1800bbcab  call    fnEfsLogTrace1Strings
0x1800bbcb0  mov     rcx, [rdi+80h]
0x1800bbcb7  lea     r9, sourceString
0x1800bbcbe  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bbcc2  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], r15d
0x1800bbcc7  lea     r15, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bbcce  mov     [rsp+0F0h+samDesired], 28h ; '('
0x1800bbcd6  mov     r8, r15
0x1800bbcd9  lea     rax, [rcx+1]
0x1800bbcdd  cmp     rax, rcx
0x1800bbce0  mov     rcx, cs:g_hPublisher
0x1800bbce7  cmovnb  rdx, rax
0x1800bbceb  sbb     ebx, ebx
0x1800bbced  mov     [rbp+57h+var_88], rdx
0x1800bbcf1  and     ebx, 80070216h
0x1800bbcf7  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bbcfe  mov     [rsp+0F0h+dwOptions], ebx
0x1800bbd02  call    fnEfsLogTrace1String1Dword
0x1800bbd07  test    eax, eax
0x1800bbd09  js      loc_1800BBEE7
0x1800bbd0f  mov     r14d, 0DA5h
0x1800bbd15  lea     r8, sourceString
0x1800bbd1c  mov     r9d, 28h ; '('
0x1800bbd22  mov     [rsp+0F0h+dwOptions], r14d
0x1800bbd27  mov     rdx, r13
0x1800bbd2a  call    fnEfsLogTrace1Strings
0x1800bbd2f  mov     rdx, [rbp+57h+var_88]; unsigned __int64
0x1800bbd33  lea     r8, [rbp+57h+lpSubKey]; unsigned __int16 **
0x1800bbd37  mov     rcx, rdi; this
0x1800bbd3a  call    ?MakeAccountPersistanceName@CDplAccount@@AEAAJ_KPEAPEAG@Z; CDplAccount::MakeAccountPersistanceName(unsigned __int64,ushort * *)
0x1800bbd3f  mov     rcx, cs:g_hPublisher
0x1800bbd46  lea     r9, sourceString
0x1800bbd4d  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], r14d
0x1800bbd52  mov     r8, r15
0x1800bbd55  lea     r14, EFS_TRACE_COMPLETE_EVENT
0x1800bbd5c  mov     [rsp+0F0h+samDesired], 28h ; '('
0x1800bbd64  mov     rdx, r14
0x1800bbd67  mov     [rsp+0F0h+dwOptions], eax
0x1800bbd6b  mov     ebx, eax
0x1800bbd6d  call    fnEfsLogTrace1String1Dword
0x1800bbd72  test    eax, eax
0x1800bbd74  js      loc_1800BBEE3
0x1800bbd7a  mov     rax, [rbp+57h+var_88]
0x1800bbd7e  mov     [rdi+80h], rax
0x1800bbd85  mov     r9d, 28h ; '('
0x1800bbd8b  mov     [rsp+0F0h+dwOptions], 0DB7h
0x1800bbd93  lea     r8, sourceString
0x1800bbd9a  mov     rdx, r13
0x1800bbd9d  call    fnEfsLogTrace1Strings
0x1800bbda2  lea     rax, [rbp+57h+Data]
0x1800bbda6  mov     rcx, rdi; this
0x1800bbda9  mov     [rsp+0F0h+lpSecurityAttributes], rax; int *
0x1800bbdae  lea     r9, [rbp+57h+var_60]; unsigned __int8 **
0x1800bbdb2  lea     rax, [rbp+57h+arg_8]
0x1800bbdb6  mov     [rsp+0F0h+samDesired], esi; int
0x1800bbdba  lea     r8, [rbp+57h+cbData]; unsigned int *
0x1800bbdbe  mov     qword ptr [rsp+0F0h+dwOptions], rax; unsigned int *
0x1800bbdc3  lea     rdx, [rbp+57h+lpData]; unsigned __int8 **
0x1800bbdc7  call    ?Serialize@CDplAccount@@AEAAJPEAPEAEPEAK01HPEAH@Z; CDplAccount::Serialize(uchar * *,ulong *,uchar * *,ulong *,int,int *)
0x1800bbdcc  mov     rcx, cs:g_hPublisher
0x1800bbdd3  lea     r9, sourceString
0x1800bbdda  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], 0DB7h
0x1800bbde2  mov     r8, r15
0x1800bbde5  mov     [rsp+0F0h+samDesired], 28h ; '('
0x1800bbded  mov     rdx, r14
0x1800bbdf0  mov     [rsp+0F0h+dwOptions], eax
0x1800bbdf4  mov     ebx, eax
0x1800bbdf6  call    fnEfsLogTrace1String1Dword
0x1800bbdfb  test    eax, eax
0x1800bbdfd  js      loc_1800BBEE3
0x1800bbe03  mov     esi, 0DBDh
0x1800bbe08  lea     r8, sourceString
0x1800bbe0f  mov     r9d, 28h ; '('
0x1800bbe15  mov     [rsp+0F0h+dwOptions], esi
0x1800bbe19  mov     rdx, r13
0x1800bbe1c  call    fnEfsLogTrace1Strings
0x1800bbe21  mov     r8d, [rbp+57h+arg_8]; unsigned int
0x1800bbe25  lea     rax, [rbp+57h+var_58]
0x1800bbe29  mov     rdx, [rbp+57h+var_60]; unsigned __int8 *
0x1800bbe2d  mov     qword ptr [rsp+0F0h+samDesired], rax; unsigned int *
0x1800bbe32  lea     rax, [rbp+57h+var_80]
0x1800bbe36  mov     qword ptr [rsp+0F0h+dwOptions], rax; unsigned __int16 **
0x1800bbe3b  call    ?Base64Encode@CDplServiceImpl@@AEAAJPEBEKHPEAPEAGPEAK@Z; CDplServiceImpl::Base64Encode(uchar const *,ulong,int,ushort * *,ulong *)
0x1800bbe40  mov     rcx, cs:g_hPublisher
0x1800bbe47  lea     r9, sourceString
0x1800bbe4e  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], esi
0x1800bbe52  mov     r8, r15
0x1800bbe55  mov     esi, 28h ; '('
0x1800bbe5a  mov     rdx, r14
0x1800bbe5d  mov     [rsp+0F0h+samDesired], esi
0x1800bbe61  mov     ebx, eax
0x1800bbe63  mov     [rsp+0F0h+dwOptions], eax
0x1800bbe67  call    fnEfsLogTrace1String1Dword
0x1800bbe6c  test    eax, eax
0x1800bbe6e  js      short loc_1800BBEDF
0x1800bbe70  cmp     [rdi+0CCh], r12d
0x1800bbe77  jz      loc_1800BBFCD
0x1800bbe7d  mov     r9d, esi
0x1800bbe80  mov     [rsp+0F0h+dwOptions], 0DC6h
0x1800bbe88  lea     r8, sourceString
0x1800bbe8f  mov     rdx, r13
0x1800bbe92  call    fnEfsLogTrace1Strings
0x1800bbe97  mov     rsi, [rbp+57h+arg_0]
0x1800bbe9b  lea     rdx, [rbp+57h+var_48]; void **
0x1800bbe9f  mov     rcx, [rsi+30h]; this
0x1800bbea3  call    ?RevertToSelf@CDplServiceImpl@@AEAAJPEAPEAX@Z; CDplServiceImpl::RevertToSelf(void * *)
0x1800bbea8  mov     rcx, cs:g_hPublisher
0x1800bbeaf  lea     r9, sourceString
0x1800bbeb6  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], 0DC6h
0x1800bbebe  mov     r8, r15
0x1800bbec1  mov     [rsp+0F0h+samDesired], 28h ; '('
0x1800bbec9  mov     rdx, r14
0x1800bbecc  mov     [rsp+0F0h+dwOptions], eax
0x1800bbed0  mov     ebx, eax
0x1800bbed2  call    fnEfsLogTrace1String1Dword
0x1800bbed7  test    eax, eax
0x1800bbed9  jns     loc_1800BBFD1
0x1800bbedf  mov     rsi, [rbp+57h+var_80]
0x1800bbee3  mov     r14, [rbp+57h+lpSubKey]
0x1800bbee7  xor     r13d, r13d
0x1800bbeea  mov     rax, [rbp+57h+var_70]
0x1800bbeee  lea     rdx, [rbp+57h+var_48]; void **
0x1800bbef2  mov     [rdi+80h], rax
0x1800bbef9  mov     rdi, [rbp+57h+arg_0]
0x1800bbefd  mov     rcx, [rdi+30h]; this
0x1800bbf01  call    ?RestoreImpersonation@CDplServiceImpl@@AEAAXPEAPEAX@Z; CDplServiceImpl::RestoreImpersonation(void * *)
0x1800bbf06  mov     edx, [rbp+57h+var_54]; int
0x1800bbf09  mov     rcx, rdi; this
0x1800bbf0c  call    ?UserSvcUnlock@CDplUser@@AEAAHH@Z; CDplUser::UserSvcUnlock(int)
0x1800bbf11  mov     rcx, [rbp+57h+lpData]; void *
0x1800bbf15  test    rcx, rcx
0x1800bbf18  jz      short loc_1800BBF1F
0x1800bbf1a  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800bbf1f  mov     [rbp+57h+lpData], r13
0x1800bbf23  test    r14, r14
0x1800bbf26  jz      short loc_1800BBF30
0x1800bbf28  mov     rcx, r14; void *
0x1800bbf2b  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800bbf30  test    r12, r12
0x1800bbf33  jz      short loc_1800BBF3D
0x1800bbf35  mov     rcx, r12; void *
0x1800bbf38  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800bbf3d  mov     rcx, [rbp+57h+var_60]; void *
0x1800bbf41  test    rcx, rcx
0x1800bbf44  jz      short loc_1800BBF4B
0x1800bbf46  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800bbf4b  mov     [rbp+57h+var_60], r13
0x1800bbf4f  test    rsi, rsi
0x1800bbf52  jz      short loc_1800BBF5C
0x1800bbf54  mov     rcx, rsi; void *
0x1800bbf57  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800bbf5c  mov     rcx, [rbp+57h+hKey]; hKey
0x1800bbf60  test    rcx, rcx
0x1800bbf63  jz      short loc_1800BBF6F
0x1800bbf65  call    cs:__imp_RegCloseKey
0x1800bbf6b  mov     [rbp+57h+hKey], r13
0x1800bbf6f  mov     rcx, [rbp+57h+var_A0]; hKey
0x1800bbf73  test    rcx, rcx
0x1800bbf76  jz      short loc_1800BBF82
0x1800bbf78  call    cs:__imp_RegCloseKey
0x1800bbf7e  mov     [rbp+57h+var_A0], r13
0x1800bbf82  mov     rcx, cs:g_hPublisher
0x1800bbf89  lea     r9, sourceString
0x1800bbf90  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], 0E7Fh
0x1800bbf98  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800bbf9f  mov     [rsp+0F0h+samDesired], 28h ; '('
0x1800bbfa7  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800bbfae  mov     [rsp+0F0h+dwOptions], ebx
0x1800bbfb2  call    fnEfsLogTrace1String1Dword
0x1800bbfb7  mov     eax, ebx
0x1800bbfb9  add     rsp, 0B8h
0x1800bbfc0  pop     r15
0x1800bbfc2  pop     r14
0x1800bbfc4  pop     r13
0x1800bbfc6  pop     r12
0x1800bbfc8  pop     rdi
0x1800bbfc9  pop     rsi
0x1800bbfca  pop     rbx
0x1800bbfcb  pop     rbp
0x1800bbfcc  retn
0x1800bbfcd  mov     rsi, [rbp+57h+arg_0]
0x1800bbfd1  mov     r9d, 28h ; '('
0x1800bbfd7  mov     [rsp+0F0h+dwOptions], 0DCFh
0x1800bbfdf  lea     r8, sourceString
0x1800bbfe6  mov     rdx, r13
0x1800bbfe9  call    fnEfsLogTrace1Strings
0x1800bbfee  mov     rcx, [rsi+68h]; unsigned __int16 *
0x1800bbff2  lea     r8, [rbp+57h+var_A0]; phkResult
0x1800bbff6  mov     edx, 0F003Fh; samDesired
0x1800bbffb  call    ?EdpCredSvcOpenUserCredStore@@YAJPEBGKPEAPEAUHKEY__@@@Z; EdpCredSvcOpenUserCredStore(ushort const *,ulong,HKEY__ * *)
0x1800bc000  mov     rcx, cs:g_hPublisher
0x1800bc007  lea     r9, sourceString
0x1800bc00e  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], 0DCFh
0x1800bc016  mov     esi, 28h ; '('
0x1800bc01b  mov     [rsp+0F0h+samDesired], esi
0x1800bc01f  mov     r8, r15
0x1800bc022  mov     rdx, r14
0x1800bc025  mov     [rsp+0F0h+dwOptions], eax
  ... truncated ...
```

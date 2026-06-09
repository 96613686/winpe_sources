# CDplUser::DeleteDuck(void)

- ea: `0x1800ada4c`
- end: `0x1800add96`
- name: `?DeleteDuck@CDplUser@@AEAAXXZ`
- size: `842`
- prototype: `void __fastcall(CDplUser *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009975c`
- `0x1800b5d70`

## callees

- `0x180001a7c`
- `0x180001b48`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180087d68`
- `0x1800964ac`
- `0x18009652c`
- `0x1800ada4c`
- `0x1800b0e7c`
- `0x1800b1f20`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800d5af8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800add2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800add2d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800adc64`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800adc64`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800add1e`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800add1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800adc20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800adc20`

## string_xrefs

- `0x1800adc93`: `Failed to delete subkey with user DUCK`

## pseudocode

```c
void __fastcall CDplUser::DeleteDuck(CDplUser *this)
{
  int v1; // r14d
  WCHAR *v2; // rsi
  int v4; // eax
  int v5; // r15d
  int v6; // ecx
  unsigned int CreateDuck; // ebx
  int v8; // ecx
  int v9; // ecx
  CDplUser *v10; // rcx
  int v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  int v14; // r8d
  int v15; // r9d
  LPCWSTR lpSubKey; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF
  struct CDplDuck *v18; // [rsp+90h] [rbp+50h] BYREF
  void *v19; // [rsp+98h] [rbp+58h] BYREF

  v1 = 0;
  hKey = 0;
  v2 = 0;
  v18 = 0;
  v19 = 0;
  lpSubKey = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 104);
  v4 = CDplUser::UserSvcLock(this);
  ++*((_DWORD *)this + 60);
  v5 = v4;
  fnEfsLogTrace1Strings(v6, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 124);
  CreateDuck = CDplUser::GetCreateDuck(this, 0, 0, &v18);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              CreateDuck,
              40,
              124) >= 0 )
  {
    *((_QWORD *)this + 20) = ReleaseIf<CDplKeyPair>(*((_QWORD *)this + 20));
    fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 136);
    CreateDuck = CDplServiceImpl::RevertToSelf(*((CDplServiceImpl **)this + 6), &v19);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                CreateDuck,
                40,
                136) >= 0 )
    {
      fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 142);
      CreateDuck = CDplUser::GetDuckPersistenceRoot(v10, (unsigned __int16 **)&lpSubKey, 0);
      v11 = fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              CreateDuck,
              40,
              142);
      v2 = (WCHAR *)lpSubKey;
      if ( v11 >= 0 )
      {
        v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
        if ( v12 )
        {
          if ( v12 > 0 )
            CreateDuck = (unsigned __int16)v12 | 0x80070000;
          else
            CreateDuck = v12;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, CreateDuck, 40, 152);
        }
        else
        {
          v13 = RegDeleteTreeW(hKey, *((LPCWSTR *)this + 13));
          if ( v13 )
          {
            if ( v13 > 0 )
              CreateDuck = (unsigned __int16)v13 | 0x80070000;
            else
              CreateDuck = v13;
            fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
              (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
              (unsigned int)L"Failed to delete subkey with user DUCK",
              CreateDuck,
              40,
              164);
          }
          else
          {
            v1 = 1;
          }
          --*((_DWORD *)this + 60);
        }
      }
    }
  }
  CDplUser::UserSvcUnlock(this, v5);
  if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    LODWORD(lpSubKey) = CreateDuck;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180114250,
      (unsigned int)&dword_180103714,
      v14,
      v15,
      (__int64)&lpSubKey);
  }
  v18 = (struct CDplDuck *)ReleaseIf<CDplKeyPair>(v18);
  if ( v1 )
    RegFlushKey(hKey);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CDplServiceImpl::RestoreImpersonation(*((CDplServiceImpl **)this + 6), &v19);
  if ( v2 )
    DplibMemFree(v2);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    CreateDuck,
    40,
    212);
}

```

## disassembly

```asm
0x1800ada4c  push    rbp
0x1800ada4e  push    rbx
0x1800ada4f  push    rsi
0x1800ada50  push    rdi
0x1800ada51  push    r12
0x1800ada53  push    r14
0x1800ada55  push    r15
0x1800ada57  mov     rbp, rsp
0x1800ada5a  sub     rsp, 40h
0x1800ada5e  xor     r14d, r14d
0x1800ada61  mov     [rbp+hKey], 0
0x1800ada69  xor     esi, esi
0x1800ada6b  mov     [rbp+arg_10], 0
0x1800ada73  lea     r8, sourceString
0x1800ada7a  mov     [rbp+arg_18], r14
0x1800ada7e  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800ada85  mov     [rbp+lpSubKey], rsi
0x1800ada89  lea     r9d, [r14+28h]
0x1800ada8d  mov     dword ptr [rsp+40h+phkResult], 668h
0x1800ada95  mov     rdi, rcx
0x1800ada98  call    fnEfsLogTrace1Strings
0x1800ada9d  mov     rcx, rdi; this
0x1800adaa0  call    ?UserSvcLock@CDplUser@@AEAAHXZ; CDplUser::UserSvcLock(void)
0x1800adaa5  inc     dword ptr [rdi+0F0h]
0x1800adaab  lea     r9d, [r14+28h]
0x1800adaaf  mov     r12d, 67Ch
0x1800adab5  lea     r8, sourceString
0x1800adabc  lea     rdx, EFS_TRACE_START_EVENT
0x1800adac3  mov     dword ptr [rsp+40h+phkResult], r12d
0x1800adac8  mov     r15d, eax
0x1800adacb  call    fnEfsLogTrace1Strings
0x1800adad0  lea     r9, [rbp+arg_10]; struct CDplDuck **
0x1800adad4  xor     r8d, r8d; int
0x1800adad7  xor     edx, edx; int
0x1800adad9  mov     rcx, rdi; this
0x1800adadc  call    ?GetCreateDuck@CDplUser@@AEAAJHHPEAPEAVCDplDuck@@@Z; CDplUser::GetCreateDuck(int,int,CDplDuck * *)
0x1800adae1  mov     rcx, cs:g_hPublisher
0x1800adae8  lea     r9, sourceString
0x1800adaef  mov     [rsp+40h+var_10], r12d
0x1800adaf4  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800adafb  lea     r12d, [r14+28h]
0x1800adaff  mov     ebx, eax
0x1800adb01  mov     [rsp+40h+var_18], r12d
0x1800adb06  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800adb0d  mov     dword ptr [rsp+40h+phkResult], eax
0x1800adb11  call    fnEfsLogTrace1String1Dword
0x1800adb16  test    eax, eax
0x1800adb18  js      loc_1800ADCB9
0x1800adb1e  mov     rcx, [rdi+0A0h]
0x1800adb25  call    ??$ReleaseIf@VCDplKeyPair@@@@YAPEAVCDplKeyPair@@PEAV0@@Z; ReleaseIf<CDplKeyPair>(CDplKeyPair *)
0x1800adb2a  mov     r12d, 688h
0x1800adb30  mov     [rdi+0A0h], rax
0x1800adb37  lea     r9d, [r14+28h]
0x1800adb3b  mov     dword ptr [rsp+40h+phkResult], r12d
0x1800adb40  lea     r8, sourceString
0x1800adb47  lea     rdx, EFS_TRACE_START_EVENT
0x1800adb4e  call    fnEfsLogTrace1Strings
0x1800adb53  mov     rcx, [rdi+30h]; this
0x1800adb57  lea     rdx, [rbp+arg_18]; void **
0x1800adb5b  call    ?RevertToSelf@CDplServiceImpl@@AEAAJPEAPEAX@Z; CDplServiceImpl::RevertToSelf(void * *)
0x1800adb60  mov     rcx, cs:g_hPublisher
0x1800adb67  lea     r9, sourceString
0x1800adb6e  mov     [rsp+40h+var_10], r12d
0x1800adb73  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800adb7a  lea     r12d, [r14+28h]
0x1800adb7e  mov     ebx, eax
0x1800adb80  mov     [rsp+40h+var_18], r12d
0x1800adb85  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800adb8c  mov     dword ptr [rsp+40h+phkResult], eax
0x1800adb90  call    fnEfsLogTrace1String1Dword
0x1800adb95  test    eax, eax
0x1800adb97  js      loc_1800ADCB9
0x1800adb9d  mov     esi, 68Eh
0x1800adba2  lea     r8, sourceString
0x1800adba9  mov     r9d, r12d
0x1800adbac  mov     dword ptr [rsp+40h+phkResult], esi
0x1800adbb0  lea     rdx, EFS_TRACE_START_EVENT
0x1800adbb7  call    fnEfsLogTrace1Strings
0x1800adbbc  xor     r8d, r8d; unsigned int *
0x1800adbbf  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x1800adbc3  call    ?GetDuckPersistenceRoot@CDplUser@@AEAAJPEAPEAGPEAK@Z; CDplUser::GetDuckPersistenceRoot(ushort * *,ulong *)
0x1800adbc8  mov     rcx, cs:g_hPublisher
0x1800adbcf  lea     r9, sourceString
0x1800adbd6  mov     [rsp+40h+var_10], esi
0x1800adbda  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800adbe1  mov     [rsp+40h+var_18], r12d
0x1800adbe6  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800adbed  mov     dword ptr [rsp+40h+phkResult], eax
0x1800adbf1  mov     ebx, eax
0x1800adbf3  call    fnEfsLogTrace1String1Dword
0x1800adbf8  mov     rsi, [rbp+lpSubKey]
0x1800adbfc  test    eax, eax
0x1800adbfe  js      loc_1800ADCB9
0x1800adc04  lea     rax, [rbp+hKey]
0x1800adc08  mov     r9d, 0F003Fh; samDesired
0x1800adc0e  xor     r8d, r8d; ulOptions
0x1800adc11  mov     [rsp+40h+phkResult], rax; phkResult
0x1800adc16  mov     rdx, rsi; lpSubKey
0x1800adc19  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800adc20  call    cs:__imp_RegOpenKeyExW
0x1800adc26  test    eax, eax
0x1800adc28  jz      short loc_1800ADC5C
0x1800adc2a  jg      short loc_1800ADC30
0x1800adc2c  mov     ebx, eax
0x1800adc2e  jmp     short loc_1800ADC39
0x1800adc30  movzx   ebx, ax
0x1800adc33  or      ebx, 80070000h
0x1800adc39  mov     rcx, cs:g_hPublisher
0x1800adc40  lea     rdx, EFS_TRACE_ERROR
0x1800adc47  mov     r9d, r12d
0x1800adc4a  mov     dword ptr [rsp+40h+phkResult], 698h
0x1800adc52  mov     r8d, ebx
0x1800adc55  call    fnEfsLogTrace1
0x1800adc5a  jmp     short loc_1800ADCB9
0x1800adc5c  mov     rdx, [rdi+68h]; lpSubKey
0x1800adc60  mov     rcx, [rbp+hKey]; hKey
0x1800adc64  call    cs:__imp_RegDeleteTreeW
0x1800adc6a  test    eax, eax
0x1800adc6c  jz      short loc_1800ADCAD
0x1800adc6e  jg      short loc_1800ADC74
0x1800adc70  mov     ebx, eax
0x1800adc72  jmp     short loc_1800ADC7D
0x1800adc74  movzx   ebx, ax
0x1800adc77  or      ebx, 80070000h
0x1800adc7d  mov     rcx, cs:g_hPublisher
0x1800adc84  lea     rdx, EFS_TRACE_MSG_ERROR_EVENT
0x1800adc8b  mov     [rsp+40h+var_10], 6A4h
0x1800adc93  lea     r9, aFailedToDelete; "Failed to delete subkey with user DUCK"
0x1800adc9a  mov     r8, rdx
0x1800adc9d  mov     [rsp+40h+var_18], r12d
0x1800adca2  mov     dword ptr [rsp+40h+phkResult], ebx
0x1800adca6  call    fnEfsLogTrace1String1Dword
0x1800adcab  jmp     short loc_1800ADCB3
0x1800adcad  mov     r14d, 1
0x1800adcb3  dec     dword ptr [rdi+0F0h]
0x1800adcb9  mov     edx, r15d; int
0x1800adcbc  mov     rcx, rdi; this
0x1800adcbf  call    ?UserSvcUnlock@CDplUser@@AEAAHH@Z; CDplUser::UserSvcUnlock(int)
0x1800adcc4  mov     eax, cs:dword_180114250
0x1800adcca  cmp     eax, 5
0x1800adccd  jbe     short loc_1800ADD08
0x1800adccf  mov     rdx, 400000000000h
0x1800adcd9  lea     rcx, dword_180114250
0x1800adce0  call    _tlgKeywordOn
0x1800adce5  test    al, al
0x1800adce7  jz      short loc_1800ADD08
0x1800adce9  lea     rax, [rbp+lpSubKey]
0x1800adced  mov     dword ptr [rbp+lpSubKey], ebx
0x1800adcf0  lea     rdx, dword_180103714
0x1800adcf7  mov     [rsp+40h+phkResult], rax
0x1800adcfc  lea     rcx, dword_180114250
0x1800add03  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800add08  mov     rcx, [rbp+arg_10]
0x1800add0c  call    ??$ReleaseIf@VCDplKeyPair@@@@YAPEAVCDplKeyPair@@PEAV0@@Z; ReleaseIf<CDplKeyPair>(CDplKeyPair *)
0x1800add11  mov     [rbp+arg_10], rax
0x1800add15  test    r14d, r14d
0x1800add18  jz      short loc_1800ADD24
0x1800add1a  mov     rcx, [rbp+hKey]; hKey
0x1800add1e  call    cs:__imp_RegFlushKey
0x1800add24  mov     rcx, [rbp+hKey]; hKey
0x1800add28  test    rcx, rcx
0x1800add2b  jz      short loc_1800ADD3B
0x1800add2d  call    cs:__imp_RegCloseKey
0x1800add33  mov     [rbp+hKey], 0
0x1800add3b  mov     rcx, [rdi+30h]; this
0x1800add3f  lea     rdx, [rbp+arg_18]; void **
0x1800add43  call    ?RestoreImpersonation@CDplServiceImpl@@AEAAXPEAPEAX@Z; CDplServiceImpl::RestoreImpersonation(void * *)
0x1800add48  test    rsi, rsi
0x1800add4b  jz      short loc_1800ADD55
0x1800add4d  mov     rcx, rsi; void *
0x1800add50  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800add55  mov     rcx, cs:g_hPublisher
0x1800add5c  lea     r9, sourceString
0x1800add63  mov     [rsp+40h+var_10], 6D4h
0x1800add6b  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800add72  mov     [rsp+40h+var_18], r12d
0x1800add77  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800add7e  mov     dword ptr [rsp+40h+phkResult], ebx
0x1800add82  call    fnEfsLogTrace1String1Dword
0x1800add87  add     rsp, 40h
0x1800add8b  pop     r15
0x1800add8d  pop     r14
0x1800add8f  pop     r12
0x1800add91  pop     rdi
0x1800add92  pop     rsi
0x1800add93  pop     rbx
0x1800add94  pop     rbp
0x1800add95  retn
```

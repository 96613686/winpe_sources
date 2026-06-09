# CPrepareUserOOBETask::_UpdateRegistry(void)

- ea: `0x18005400c`
- end: `0x18005422c`
- name: `?_UpdateRegistry@CPrepareUserOOBETask@@AEAAJXZ`
- size: `544`
- prototype: `__int64 __fastcall(CPrepareUserOOBETask *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180053f60`

## callees

- `0x180003470`
- `0x18000ac48`
- `0x1800230b0`
- `0x180031ff0`
- `0x180046e0c`
- `0x18005400c`
- `0x1800b8834`
- `0x1800bda90`
- `0x1800bdc68`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005411a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005411a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800540fd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800540fd`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x18005404b`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x18005404b`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x1800541b9`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x1800541e0`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x1800541f7`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x1800541b9`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x1800541e0`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x1800541f7`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x180054097`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x180054139`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x180054097`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x180054139`

## string_xrefs

- `0x180054128`: `DefaultAccountSID`
- `0x1800541e6`: `DefaultAccountSID`
- `0x18005416f`: `shell\oobe\machine\plugins\useroobepreparation\prepareuseroobetask.cpp`
- `0x180054197`: `CPrepareUserOOBETask::_UpdateRegistry succeeded`
- `0x180054200`: `CPrepareUserOOBETask::_UpdateRegistry failed with hr=0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPrepareUserOOBETask::_UpdateRegistry(CPrepareUserOOBETask *this)
{
  __int64 *v2; // rsi
  __int64 *v3; // rdi
  int v4; // eax
  signed int Error; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int ReferencedDomainName; // [rsp+20h] [rbp-99h]
  LPWSTR StringSid; // [rsp+40h] [rbp-79h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-71h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-6Dh] BYREF
  DWORD cbSid[4]; // [rsp+50h] [rbp-69h] BYREF
  _BYTE Sid[80]; // [rsp+60h] [rbp-59h] BYREF
  WCHAR v16[16]; // [rsp+B0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = (__int64 *)off_1801132A0;
  v3 = (__int64 *)off_1801132A0;
  while ( 1 )
  {
    v4 = SetPersistedRegistryDWORD(*v3, v3[1], v3[2], *((unsigned int *)v3 + 6));
    Error = v4;
    if ( v4 > 0 )
      Error = (unsigned __int16)v4 | 0x80070000;
    if ( Error < 0 )
      break;
    v3 += 4;
    if ( v3 == qword_180113320 )
    {
      v6 = SetPersistedRegistryString(
             L"OOBE",
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
             L"DefaultAccountSAMName",
             *((_QWORD *)this + 69));
      Error = v6;
      if ( v6 > 0 )
        Error = (unsigned __int16)v6 | 0x80070000;
      if ( Error >= 0 )
      {
        cbSid[0] = 68;
        cchReferencedDomainName = 16;
        peUse = 0;
        StringSid = 0;
        if ( LookupAccountNameW(0, *((LPCWSTR *)this + 69), Sid, cbSid, v16, &cchReferencedDomainName, &peUse)
          && (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &StringSid,
                0),
              ConvertSidToStringSidW(Sid, &StringSid)) )
        {
          v7 = SetPersistedRegistryString(
                 L"OOBE",
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
                 L"DefaultAccountSID",
                 StringSid);
          Error = v7;
          if ( v7 > 0 )
            Error = (unsigned __int16)v7 | 0x80070000;
        }
        else
        {
          Error = ResultFromKnownLastError();
        }
        if ( Error >= 0 )
        {
          v8 = _WriteSystemDataRegistryDWORDForUser(Sid);
          if ( v8 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x13C,
              (unsigned int)"shell\\oobe\\machine\\plugins\\useroobepreparation\\prepareuseroobetask.cpp",
              (const char *)(unsigned int)v8,
              ReferencedDomainName);
            DeleteSystemDataRegistryKeyForUser(Sid);
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(&StringSid);
        if ( Error >= 0 )
        {
          UnattendLogW(0, L"CPrepareUserOOBETask::_UpdateRegistry succeeded");
          return (unsigned int)Error;
        }
      }
      goto LABEL_19;
    }
  }
  do
  {
LABEL_19:
    DeletePersistedRegistryValue(*v2, v2[1], v2[2]);
    v2 += 4;
  }
  while ( v2 != qword_180113320 );
  DeletePersistedRegistryValue(L"OOBE", L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", L"DefaultAccountSAMName");
  DeletePersistedRegistryValue(L"OOBE", L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", L"DefaultAccountSID");
  UnattendLogW(0, L"CPrepareUserOOBETask::_UpdateRegistry failed with hr=0x%08X", (unsigned int)Error);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18005400c  push    rbp
0x18005400e  push    rbx
0x18005400f  push    rsi
0x180054010  push    rdi
0x180054011  push    r13
0x180054013  push    r14
0x180054015  lea     rbp, [rsp-2Fh]
0x18005401a  sub     rsp, 0E8h
0x180054021  mov     rax, cs:__security_cookie
0x180054028  xor     rax, rsp
0x18005402b  mov     [rbp+57h+var_40], rax
0x18005402f  mov     r14, rcx
0x180054032  lea     rsi, off_1801132A0; "OOBE"
0x180054039  mov     rdi, rsi
0x18005403c  mov     r9d, [rdi+18h]
0x180054040  mov     r8, [rdi+10h]
0x180054044  mov     rdx, [rdi+8]
0x180054048  mov     rcx, [rdi]
0x18005404b  call    cs:__imp_SetPersistedRegistryDWORD
0x180054051  mov     ebx, eax
0x180054053  test    eax, eax
0x180054055  jle     short loc_180054060
0x180054057  movzx   ebx, ax
0x18005405a  or      ebx, 80070000h
0x180054060  lea     r13, aOobe_0; "OOBE"
0x180054067  test    ebx, ebx
0x180054069  js      loc_1800541A7
0x18005406f  add     rdi, 20h ; ' '
0x180054073  lea     rax, qword_180113320
0x18005407a  cmp     rdi, rax
0x18005407d  jnz     short loc_18005403C
0x18005407f  mov     r9, [r14+228h]
0x180054086  lea     r8, aDefaultaccount_0; "DefaultAccountSAMName"
0x18005408d  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180054094  mov     rcx, r13
0x180054097  call    cs:__imp_SetPersistedRegistryString
0x18005409d  mov     ebx, eax
0x18005409f  test    eax, eax
0x1800540a1  jle     short loc_1800540AC
0x1800540a3  movzx   ebx, ax
0x1800540a6  or      ebx, 80070000h
0x1800540ac  test    ebx, ebx
0x1800540ae  js      loc_1800541A7
0x1800540b4  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800540bb  mov     [rbp+57h+var_C4], 10h
0x1800540c2  mov     [rbp+57h+var_C8], 0
0x1800540c9  mov     [rbp+57h+StringSid], 0
0x1800540d1  lea     rax, [rbp+57h+var_C8]
0x1800540d5  mov     [rsp+110h+peUse], rax; peUse
0x1800540da  lea     rax, [rbp+57h+var_C4]
0x1800540de  mov     [rsp+110h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800540e3  lea     rax, [rbp+57h+var_60]
0x1800540e7  mov     [rsp+110h+ReferencedDomainName], rax; int
0x1800540ec  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800540f0  lea     r8, [rbp+57h+Sid]; Sid
0x1800540f4  mov     rdx, [r14+228h]; lpAccountName
0x1800540fb  xor     ecx, ecx; lpSystemName
0x1800540fd  call    cs:__imp_LookupAccountNameW
0x180054103  test    eax, eax
0x180054105  jz      short loc_180054150
0x180054107  xor     edx, edx
0x180054109  lea     rcx, [rbp+57h+StringSid]
0x18005410d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180054112  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180054116  lea     rcx, [rbp+57h+Sid]; Sid
0x18005411a  call    cs:__imp_ConvertSidToStringSidW
0x180054120  test    eax, eax
0x180054122  jz      short loc_180054150
0x180054124  mov     r9, [rbp+57h+StringSid]
0x180054128  lea     r8, aDefaultaccount_1; "DefaultAccountSID"
0x18005412f  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180054136  mov     rcx, r13
0x180054139  call    cs:__imp_SetPersistedRegistryString
0x18005413f  mov     ebx, eax
0x180054141  test    eax, eax
0x180054143  jle     short loc_180054157
0x180054145  movzx   ebx, ax
0x180054148  or      ebx, 80070000h
0x18005414e  jmp     short loc_180054157
0x180054150  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180054155  mov     ebx, eax
0x180054157  test    ebx, ebx
0x180054159  js      short loc_18005418A
0x18005415b  lea     rcx, [rbp+57h+Sid]
0x18005415f  call    ?_WriteSystemDataRegistryDWORDForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@K_N@Z; _WriteSystemDataRegistryDWORDForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ulong,bool)
0x180054164  mov     rcx, [rbp+5Fh]; this
0x180054168  test    eax, eax
0x18005416a  jns     short loc_18005418A
0x18005416c  mov     r9d, eax; char *
0x18005416f  lea     r8, aShellOobeMachi_8; "shell\\oobe\\machine\\plugins\\useroobe"...
0x180054176  mov     edx, 13Ch; void *
0x18005417b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054180  lea     rcx, [rbp+57h+Sid]; void *
0x180054184  call    ?DeleteSystemDataRegistryKeyForUser@@YAJPEAX@Z; DeleteSystemDataRegistryKeyForUser(void *)
0x180054189  nop
0x18005418a  lea     rcx, [rbp+57h+StringSid]
0x18005418e  call    ??1?$unique_storage@U?$resource_policy@PEAU_STORAGE_DEVICE_DESCRIPTOR@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(void)
0x180054193  test    ebx, ebx
0x180054195  js      short loc_1800541A7
0x180054197  lea     rdx, aCprepareuseroo_0; "CPrepareUserOOBETask::_UpdateRegistry s"...
0x18005419e  xor     ecx, ecx
0x1800541a0  call    UnattendLogW
0x1800541a5  jmp     short loc_18005420E
0x1800541a7  lea     r13, qword_180113320
0x1800541ae  mov     r8, [rsi+10h]
0x1800541b2  mov     rdx, [rsi+8]
0x1800541b6  mov     rcx, [rsi]
0x1800541b9  call    cs:__imp_DeletePersistedRegistryValue
0x1800541bf  add     rsi, 20h ; ' '
0x1800541c3  cmp     rsi, r13
0x1800541c6  jnz     short loc_1800541AE
0x1800541c8  lea     r8, aDefaultaccount_0; "DefaultAccountSAMName"
0x1800541cf  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800541d6  lea     r13, aOobe_0; "OOBE"
0x1800541dd  mov     rcx, r13
0x1800541e0  call    cs:__imp_DeletePersistedRegistryValue
0x1800541e6  lea     r8, aDefaultaccount_1; "DefaultAccountSID"
0x1800541ed  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800541f4  mov     rcx, r13
0x1800541f7  call    cs:__imp_DeletePersistedRegistryValue
0x1800541fd  mov     r8d, ebx
0x180054200  lea     rdx, aCprepareuseroo; "CPrepareUserOOBETask::_UpdateRegistry f"...
0x180054207  xor     ecx, ecx
0x180054209  call    UnattendLogW
0x18005420e  mov     eax, ebx
0x180054210  mov     rcx, [rbp+57h+var_40]
0x180054214  xor     rcx, rsp; StackCookie
0x180054217  call    __security_check_cookie
0x18005421c  add     rsp, 0E8h
0x180054223  pop     r14
0x180054225  pop     r13
0x180054227  pop     rdi
0x180054228  pop     rsi
0x180054229  pop     rbx
0x18005422a  pop     rbp
0x18005422b  retn
```

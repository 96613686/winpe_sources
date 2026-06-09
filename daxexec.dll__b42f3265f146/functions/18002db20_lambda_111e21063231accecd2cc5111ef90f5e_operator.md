# _lambda_111e21063231accecd2cc5111ef90f5e_::operator()

- ea: `0x18002db20`
- end: `0x18002dc56`
- name: `_lambda_111e21063231accecd2cc5111ef90f5e_::operator()`
- size: `310`
- prototype: `unsigned int __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f408`

## callees

- `0x180001f74`
- `0x180011e9c`
- `0x18002db20`
- `0x180033630`
- `0x18003590c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dc2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dc41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dc2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dc41`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18002dbc1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18002dbc1`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002db6c`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002db6c`

## pseudocode

```c
unsigned int __fastcall lambda_111e21063231accecd2cc5111ef90f5e_::operator()(__int64 a1, const WCHAR *a2)
{
  DWORD NamedSecurityInfoW; // eax
  unsigned int result; // eax
  const char *v5; // r9
  LPWSTR v6; // rbx
  unsigned int *v7; // rcx
  int v8; // r9d
  unsigned int StringSecurityDescriptorLen; // [rsp+20h] [rbp-30h]
  const WCHAR *v10; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v12; // [rsp+70h] [rbp+20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+28h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+80h] [rbp+30h] BYREF
  LPWSTR v15; // [rsp+88h] [rbp+38h] BYREF

  v12 = a1;
  SecurityDescriptor = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 4u, 0, 0, 0, 0, &SecurityDescriptor);
  if ( NamedSecurityInfoW )
  {
    result = wil::details::in1diag3::Log_Win32(
               retaddr,
               (void *)0x7C7,
               (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
               (const char *)NamedSecurityInfoW,
               StringSecurityDescriptorLen);
  }
  else
  {
    LODWORD(v12) = 0;
    StringSecurityDescriptor = 0;
    if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(
            SecurityDescriptor,
            1u,
            4u,
            &StringSecurityDescriptor,
            (PULONG)&v12) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x7D2,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
        v5);
    v6 = StringSecurityDescriptor;
    v7 = (unsigned int *)*((_QWORD *)DesktopAppXProvider::Instance() + 1);
    result = *v7;
    if ( *v7 > 5 )
    {
      v15 = v6;
      v10 = a2;
      result = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                 (_DWORD)v7,
                 (unsigned int)word_1800E4E52,
                 0,
                 v8,
                 (__int64)&v10,
                 (__int64)&v15);
    }
    if ( StringSecurityDescriptor )
      result = (unsigned int)LocalFree(StringSecurityDescriptor);
  }
  if ( SecurityDescriptor )
    return (unsigned int)LocalFree(SecurityDescriptor);
  return result;
}

```

## disassembly

```asm
0x18002db20  mov     r11, rsp
0x18002db23  mov     [r11+8], rcx
0x18002db27  push    rbp
0x18002db28  push    rbx
0x18002db29  push    rdi
0x18002db2a  mov     rbp, rsp
0x18002db2d  sub     rsp, 50h
0x18002db31  mov     rdi, rdx
0x18002db34  mov     [rbp+SecurityDescriptor], 0
0x18002db3c  xor     r9d, r9d; ppsidOwner
0x18002db3f  lea     rax, [rbp+SecurityDescriptor]
0x18002db43  mov     [r11-30h], rax
0x18002db47  mov     rcx, rdi; pObjectName
0x18002db4a  mov     qword ptr [r11-38h], 0
0x18002db52  mov     qword ptr [r11-40h], 0
0x18002db5a  lea     ebx, [r9+4]
0x18002db5e  mov     qword ptr [r11-48h], 0
0x18002db66  mov     r8d, ebx; SecurityInfo
0x18002db69  lea     edx, [rbx-3]; ObjectType
0x18002db6c  call    cs:__imp_GetNamedSecurityInfoW
0x18002db73  nop     dword ptr [rax+rax+00h]
0x18002db78  test    eax, eax
0x18002db7a  jz      short loc_18002DB99
0x18002db7c  mov     rcx, [rbp+18h]; this
0x18002db80  lea     r8, aOnecoreBaseApp_43; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002db87  mov     r9d, eax; char *
0x18002db8a  mov     edx, 7C7h; void *
0x18002db8f  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18002db94  jmp     loc_18002DC38
0x18002db99  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002db9d  lea     rax, [rbp+arg_0]
0x18002dba1  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002dba5  mov     [rsp+50h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x18002dbaa  mov     r8d, ebx; SecurityInformation
0x18002dbad  mov     dword ptr [rbp+arg_0], 0
0x18002dbb4  mov     edx, 1; RequestedStringSDRevision
0x18002dbb9  mov     [rbp+StringSecurityDescriptor], 0
0x18002dbc1  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18002dbc8  nop     dword ptr [rax+rax+00h]
0x18002dbcd  test    eax, eax
0x18002dbcf  jnz     short loc_18002DBE6
0x18002dbd1  mov     rcx, [rbp+18h]; this
0x18002dbd5  lea     r8, aOnecoreBaseApp_43; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002dbdc  mov     edx, 7D2h; void *
0x18002dbe1  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002dbe6  mov     rbx, [rbp+StringSecurityDescriptor]
0x18002dbea  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x18002dbef  mov     rcx, [rax+8]
0x18002dbf3  mov     eax, [rcx]
0x18002dbf5  cmp     eax, 5
0x18002dbf8  jbe     short loc_18002DC23
0x18002dbfa  lea     rax, [rbp+arg_18]
0x18002dbfe  mov     [rbp+arg_18], rbx
0x18002dc02  mov     [rsp+50h+var_28], rax
0x18002dc07  lea     rdx, word_1800E4E52
0x18002dc0e  lea     rax, [rbp+var_10]
0x18002dc12  mov     [rbp+var_10], rdi
0x18002dc16  xor     r8d, r8d
0x18002dc19  mov     [rsp+50h+StringSecurityDescriptorLen], rax
0x18002dc1e  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002dc23  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18002dc27  test    rcx, rcx
0x18002dc2a  jz      short loc_18002DC38
0x18002dc2c  call    cs:__imp_LocalFree
0x18002dc33  nop     dword ptr [rax+rax+00h]
0x18002dc38  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18002dc3c  test    rcx, rcx
0x18002dc3f  jz      short loc_18002DC4D
0x18002dc41  call    cs:__imp_LocalFree
0x18002dc48  nop     dword ptr [rax+rax+00h]
0x18002dc4d  add     rsp, 50h
0x18002dc51  pop     rdi
0x18002dc52  pop     rbx
0x18002dc53  pop     rbp
0x18002dc54  retn
```

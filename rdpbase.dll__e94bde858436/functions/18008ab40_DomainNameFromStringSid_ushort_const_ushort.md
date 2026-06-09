# DomainNameFromStringSid(ushort const *,ushort * *)

- ea: `0x18008ab40`
- end: `0x18008acd8`
- name: `?DomainNameFromStringSid@@YAJPEBGPEAPEAG@Z`
- size: `408`
- prototype: `int(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18008ace0`

## callees

- `0x180001aa0`
- `0x18008a760`
- `0x18008ab40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ac3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ac3b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008ab64`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008ab64`

## string_xrefs

- `0x18008abde`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008ac8c`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008ac68`: `ConvertStringSidToSid failed`
- `0x18008abd3`: `DomainNameFromStringSid`
- `0x18008ac81`: `DomainNameFromStringSid`
- `0x18008abba`: `DomainNameFromSid failed`

## pseudocode

```c
__int64 __fastcall DomainNameFromStringSid(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  signed int LastError; // eax
  signed int v7; // ebx
  int *v8; // rdx
  const char **v9; // rax
  const char **v11; // [rsp+30h] [rbp-50h]
  const char **v12; // [rsp+40h] [rbp-40h]
  const char **v13; // [rsp+48h] [rbp-38h]
  PSID Sid; // [rsp+50h] [rbp-30h] BYREF
  const char *v15; // [rsp+58h] [rbp-28h] BYREF
  const char *v16; // [rsp+60h] [rbp-20h] BYREF
  const char *v17; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v18[2]; // [rsp+70h] [rbp-10h] BYREF
  int v19; // [rsp+A0h] [rbp+20h] BYREF
  signed int v20; // [rsp+A8h] [rbp+28h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
    goto LABEL_6;
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
    {
LABEL_6:
      v7 = DomainNameFromSid(Sid, a2);
      if ( v7 < 0 )
      {
        v3 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v19 = 1157;
          v18[0] = "DomainNameFromSid failed";
          v8 = (int *)byte_1801ACE53;
          v17 = "DomainNameFromStringSid";
          v16 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
          v15 = "Error HResult failed";
          v13 = (const char **)v18;
          v12 = &v17;
          v11 = &v16;
          v9 = &v15;
LABEL_9:
          v20 = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v3,
            (_DWORD)v8,
            v4,
            v5,
            (__int64)v9,
            (__int64)&v20,
            (__int64)v11,
            (__int64)&v19,
            (__int64)v12,
            (__int64)v13);
          goto LABEL_10;
        }
      }
      goto LABEL_10;
    }
  }
  else
  {
    v7 = -2147467259;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v19 = 1153;
    v15 = "ConvertStringSidToSid failed";
    v8 = &dword_1801ACEA4;
    v16 = "DomainNameFromStringSid";
    v17 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
    v18[0] = "Error HResult failed";
    v13 = &v15;
    v12 = &v16;
    v11 = &v17;
    v9 = (const char **)v18;
    goto LABEL_9;
  }
LABEL_10:
  if ( Sid )
    LocalFree(Sid);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18008ab40  mov     [rsp-8+arg_0], rbx
0x18008ab45  mov     [rsp-8+arg_8], rdi
0x18008ab4a  push    rbp
0x18008ab4b  mov     rbp, rsp
0x18008ab4e  sub     rsp, 80h
0x18008ab55  mov     rdi, rdx
0x18008ab58  mov     [rbp+Sid], 0
0x18008ab60  lea     rdx, [rbp+Sid]; Sid
0x18008ab64  call    cs:__imp_ConvertStringSidToSidW
0x18008ab6a  test    eax, eax
0x18008ab6c  jnz     short loc_18008AB99
0x18008ab6e  call    cs:__imp_GetLastError
0x18008ab74  test    eax, eax
0x18008ab76  jz      loc_18008AC58
0x18008ab7c  call    cs:__imp_GetLastError
0x18008ab82  mov     ebx, eax
0x18008ab84  test    eax, eax
0x18008ab86  jle     short loc_18008AB91
0x18008ab88  movzx   ebx, ax
0x18008ab8b  or      ebx, 80070000h
0x18008ab91  test    ebx, ebx
0x18008ab93  js      loc_18008AC5D
0x18008ab99  mov     rcx, [rbp+Sid]; Sid
0x18008ab9d  mov     rdx, rdi; unsigned __int16 **
0x18008aba0  call    ?DomainNameFromSid@@YAJPEAXPEAPEAG@Z; DomainNameFromSid(void *,ushort * *)
0x18008aba5  mov     ebx, eax
0x18008aba7  test    eax, eax
0x18008aba9  jns     loc_18008AC32
0x18008abaf  mov     ecx, cs:CallbackContext
0x18008abb5  cmp     ecx, 2
0x18008abb8  jbe     short loc_18008AC32
0x18008abba  lea     rax, aDomainnamefrom_0; "DomainNameFromSid failed"
0x18008abc1  mov     [rbp+arg_10], 485h
0x18008abc8  mov     [rbp+var_10], rax
0x18008abcc  lea     rdx, byte_1801ACE53
0x18008abd3  lea     rax, aDomainnamefrom_1; "DomainNameFromStringSid"
0x18008abda  mov     [rbp+var_18], rax
0x18008abde  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008abe5  mov     [rbp+var_20], rax
0x18008abe9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008abf0  mov     [rbp+var_28], rax
0x18008abf4  lea     rax, [rbp+var_10]
0x18008abf8  mov     [rsp+80h+var_38], rax
0x18008abfd  lea     rax, [rbp+var_18]
0x18008ac01  mov     [rsp+80h+var_40], rax
0x18008ac06  lea     rax, [rbp+arg_10]
0x18008ac0a  mov     [rsp+80h+var_48], rax
0x18008ac0f  lea     rax, [rbp+var_20]
0x18008ac13  mov     [rsp+80h+var_50], rax
0x18008ac18  lea     rax, [rbp+arg_18]
0x18008ac1c  mov     [rsp+80h+var_58], rax
0x18008ac21  lea     rax, [rbp+var_28]
0x18008ac25  mov     [rsp+80h+var_60], rax
0x18008ac2a  mov     [rbp+arg_18], ebx
0x18008ac2d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008ac32  mov     rcx, [rbp+Sid]; hMem
0x18008ac36  test    rcx, rcx
0x18008ac39  jz      short loc_18008AC41
0x18008ac3b  call    cs:__imp_LocalFree
0x18008ac41  lea     r11, [rsp+80h+var_s0]
0x18008ac49  mov     eax, ebx
0x18008ac4b  mov     rbx, [r11+10h]
0x18008ac4f  mov     rdi, [r11+18h]
0x18008ac53  mov     rsp, r11
0x18008ac56  pop     rbp
0x18008ac57  retn
0x18008ac58  mov     ebx, 80004005h
0x18008ac5d  mov     eax, cs:CallbackContext
0x18008ac63  cmp     eax, 2
0x18008ac66  jbe     short loc_18008AC32
0x18008ac68  lea     rax, aConvertstrings_0; "ConvertStringSidToSid failed"
0x18008ac6f  mov     [rbp+arg_10], 481h
0x18008ac76  mov     [rbp+var_28], rax
0x18008ac7a  lea     rdx, dword_1801ACEA4
0x18008ac81  lea     rax, aDomainnamefrom_1; "DomainNameFromStringSid"
0x18008ac88  mov     [rbp+var_20], rax
0x18008ac8c  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008ac93  mov     [rbp+var_18], rax
0x18008ac97  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008ac9e  mov     [rbp+var_10], rax
0x18008aca2  lea     rax, [rbp+var_28]
0x18008aca6  mov     [rsp+80h+var_38], rax
0x18008acab  lea     rax, [rbp+var_20]
0x18008acaf  mov     [rsp+80h+var_40], rax
0x18008acb4  lea     rax, [rbp+arg_10]
0x18008acb8  mov     [rsp+80h+var_48], rax
0x18008acbd  lea     rax, [rbp+var_18]
0x18008acc1  mov     [rsp+80h+var_50], rax
0x18008acc6  lea     rax, [rbp+arg_18]
0x18008acca  mov     [rsp+80h+var_58], rax
0x18008accf  lea     rax, [rbp+var_10]
0x18008acd3  jmp     loc_18008AC25
```

# AdvertisingIdHelpers::CheckChildAccount(bool *)

- ea: `0x180001d20`
- end: `0x180001e0d`
- name: `?CheckChildAccount@AdvertisingIdHelpers@@YAJPEA_N@Z`
- size: `237`
- prototype: `__int64 __fastcall(AdvertisingIdHelpers *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800011a0`

## callees

- `0x180001790`
- `0x180001d20`
- `0x180006324`
- `0x180007820`

## import_xrefs

- `ext-ms-win-familysafety-childaccount-l1-1-0!IsChildAccount` at `0x180001d63`
- `ext-ms-win-familysafety-childaccount-l1-1-0!IsChildAccount` at `0x180001d63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001dba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001df5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001dba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001df5`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::CheckChildAccount(AdvertisingIdHelpers *this, bool *a2)
{
  struct Windows::Internal::String *v3; // rdx
  int CurrentUserSid; // eax
  unsigned int v5; // ebx
  HSTRING v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v12; // [rsp+38h] [rbp+10h] BYREF
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF

  v12 = 0;
  if ( !(unsigned __int8)IsIsChildAccountPresent(this, a2) )
    goto LABEL_6;
  string = 0;
  CurrentUserSid = AdvertisingIdHelpers::GetCurrentUserSid(&string, v3);
  v5 = CurrentUserSid;
  if ( CurrentUserSid < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)CurrentUserSid,
      v10);
    if ( string )
      WindowsDeleteString(string);
    return v5;
  }
  else
  {
    v6 = string;
    v7 = IsChildAccount(string, &v12);
    v8 = v7;
    if ( v7 >= 0 )
    {
      if ( v6 )
        WindowsDeleteString(v6);
LABEL_6:
      *(_BYTE *)this = v12 != 0;
      return 0;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)v7,
      v10);
    if ( v6 )
      WindowsDeleteString(v6);
    return v8;
  }
}

```

## disassembly

```asm
0x180001d20  mov     [rsp+arg_0], rbx
0x180001d25  mov     [rsp+arg_18], rsi
0x180001d2a  push    rdi; int
0x180001d2b  sub     rsp, 20h
0x180001d2f  xor     ebx, ebx
0x180001d31  mov     rsi, rcx
0x180001d34  mov     [rsp+28h+arg_8], ebx
0x180001d38  call    IsIsChildAccountPresent
0x180001d3d  test    al, al
0x180001d3f  jz      short loc_180001D7D
0x180001d41  lea     rcx, [rsp+28h+string]; this
0x180001d46  mov     [rsp+28h+string], rbx
0x180001d4b  call    ?GetCurrentUserSid@AdvertisingIdHelpers@@YAJPEAVString@Internal@Windows@@@Z; AdvertisingIdHelpers::GetCurrentUserSid(Windows::Internal::String *)
0x180001d50  mov     ebx, eax
0x180001d52  test    eax, eax
0x180001d54  js      short loc_180001DD2
0x180001d56  mov     rbx, [rsp+28h+string]
0x180001d5b  lea     rdx, [rsp+28h+arg_8]
0x180001d60  mov     rcx, rbx
0x180001d63  call    cs:__imp_IsChildAccount
0x180001d69  mov     edi, eax
0x180001d6b  test    eax, eax
0x180001d6d  js      short loc_180001D99
0x180001d6f  test    rbx, rbx
0x180001d72  jz      short loc_180001D7D
0x180001d74  mov     rcx, rbx; string
0x180001d77  call    cs:__imp_WindowsDeleteString
0x180001d7d  cmp     [rsp+28h+arg_8], 0
0x180001d82  setnz   al
0x180001d85  mov     [rsi], al
0x180001d87  xor     eax, eax
0x180001d89  mov     rbx, [rsp+28h+arg_0]
0x180001d8e  mov     rsi, [rsp+28h+arg_18]
0x180001d93  add     rsp, 20h
0x180001d97  pop     rdi
0x180001d98  retn
0x180001d99  mov     rcx, [rsp+28h]; this
0x180001d9e  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001da5  mov     r9d, edi; char *
0x180001da8  mov     edx, 19Ch; void *
0x180001dad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001db2  test    rbx, rbx
0x180001db5  jz      short loc_180001DC0
0x180001db7  mov     rcx, rbx; string
0x180001dba  call    cs:__imp_WindowsDeleteString
0x180001dc0  mov     eax, edi
0x180001dc2  mov     rbx, [rsp+28h+arg_0]
0x180001dc7  mov     rsi, [rsp+28h+arg_18]
0x180001dcc  add     rsp, 20h
0x180001dd0  pop     rdi
0x180001dd1  retn
0x180001dd2  mov     rcx, [rsp+28h]; this
0x180001dd7  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001dde  mov     r9d, ebx; char *
0x180001de1  mov     edx, 19Bh; void *
0x180001de6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001deb  mov     rcx, [rsp+28h+string]; string
0x180001df0  test    rcx, rcx
0x180001df3  jz      short loc_180001DFB
0x180001df5  call    cs:__imp_WindowsDeleteString
0x180001dfb  mov     rsi, [rsp+28h+arg_18]
0x180001e00  mov     eax, ebx
0x180001e02  mov     rbx, [rsp+28h+arg_0]
0x180001e07  add     rsp, 20h
0x180001e0b  pop     rdi
0x180001e0c  retn
```

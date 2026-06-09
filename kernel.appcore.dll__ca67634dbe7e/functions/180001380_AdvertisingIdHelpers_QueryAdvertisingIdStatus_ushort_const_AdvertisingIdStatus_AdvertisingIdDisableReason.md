# AdvertisingIdHelpers::QueryAdvertisingIdStatus(ushort const *,AdvertisingIdStatus *,AdvertisingIdDisableReason *)

- ea: `0x180001380`
- end: `0x18000160a`
- name: `?QueryAdvertisingIdStatus@AdvertisingIdHelpers@@YAJPEBGPEAW4AdvertisingIdStatus@@PEAW4AdvertisingIdDisableReason@@@Z`
- size: `650`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, const unsigned __int16 *, enum AdvertisingIdStatus *, enum AdvertisingIdDisableReason *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009a60`

## callees

- `0x180001380`
- `0x180001610`
- `0x180001790`
- `0x180001920`
- `0x180001af0`
- `0x180006324`
- `0x180007820`

## import_xrefs

- `ext-ms-win-familysafety-childaccount-l1-1-0!IsChildAccount` at `0x180001415`
- `ext-ms-win-familysafety-childaccount-l1-1-0!IsChildAccount` at `0x180001415`
- `api-ms-win-privacy-coreprivacysettingsstore-l1-1-0!CPSSGetDwordSetting` at `0x18000152d`
- `api-ms-win-privacy-coreprivacysettingsstore-l1-1-0!CPSSGetDwordSetting` at `0x18000152d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001429`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001429`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001499`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000150f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000150f`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::QueryAdvertisingIdStatus(
        WCHAR *StringSid,
        bool *a2,
        enum AdvertisingIdStatus *a3,
        enum AdvertisingIdDisableReason *a4)
{
  int v5; // esi
  int v8; // eax
  unsigned int v9; // ebx
  struct Windows::Internal::String *v10; // rdx
  int CurrentUserSid; // eax
  unsigned int v12; // edi
  HSTRING v13; // rbx
  int v14; // eax
  int v15; // edi
  HSTRING v17; // rcx
  int v18; // eax
  PSID v19; // rdx
  int v20; // eax
  const unsigned __int16 *v21; // rdx
  int v22; // eax
  int v23; // [rsp+20h] [rbp-58h]
  _BYTE v24[4]; // [rsp+30h] [rbp-48h] BYREF
  int v25; // [rsp+34h] [rbp-44h] BYREF
  HSTRING string; // [rsp+38h] [rbp-40h] BYREF
  PSID Sid; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v29; // [rsp+98h] [rbp+20h] BYREF

  LOBYTE(v29) = 0;
  v5 = 1;
  v24[0] = 0;
  v25 = 1;
  v8 = AdvertisingIdHelpers::CheckGroupPolicy((AdvertisingIdHelpers *)&v29, a2);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x231,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)v8,
      v23);
    return v9;
  }
  if ( (_BYTE)v29 )
  {
    v15 = 2;
    goto LABEL_10;
  }
  v29 = 0;
  if ( !(unsigned __int8)IsIsChildAccountPresent() )
    goto LABEL_8;
  string = 0;
  CurrentUserSid = AdvertisingIdHelpers::GetCurrentUserSid(&string, v10);
  v12 = CurrentUserSid;
  if ( CurrentUserSid >= 0 )
  {
    v13 = string;
    v14 = IsChildAccount(string, &v29);
    v12 = v14;
    if ( v14 >= 0 )
    {
      if ( v13 )
        WindowsDeleteString(v13);
LABEL_8:
      v9 = 0;
      if ( v29 )
      {
        v15 = 2;
        v5 = 2;
        goto LABEL_10;
      }
LABEL_18:
      v18 = AdvertisingIdHelpers::CheckMsaChildAccount((AdvertisingIdHelpers *)v24, (bool *)v10);
      v9 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x24C,
          (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
          (const char *)(unsigned int)v18,
          v23);
      }
      else
      {
        if ( v24[0] )
        {
          v15 = 2;
          v5 = 2;
LABEL_10:
          *(_DWORD *)a2 = v15;
          if ( a3 )
            *(_DWORD *)a3 = v5;
          return v9;
        }
        v19 = 0;
        Sid = 0;
        if ( StringSid )
        {
          ConvertStringSidToSidW(StringSid, &Sid);
          v19 = Sid;
        }
        v20 = CPSSGetDwordSetting(1, v19, L"AdvertisingInfo", &v25);
        v9 = v20;
        if ( v20 >= 0 )
        {
          v5 = 0;
          v15 = v25 != 0;
          v22 = AdvertisingIdHelpers::EnsureAdvertisingIdAcl((AdvertisingIdHelpers *)StringSid, v21);
          if ( v22 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x273,
              (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
              (const char *)(unsigned int)v22,
              0);
          v9 = 0;
          goto LABEL_10;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x263,
          (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
          (const char *)(unsigned int)v20,
          0);
      }
      return v9;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)v14,
      v23);
    if ( !v13 )
      goto LABEL_17;
    v17 = v13;
    goto LABEL_16;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x19B,
    (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
    (const char *)(unsigned int)CurrentUserSid,
    v23);
  v17 = string;
  if ( string )
LABEL_16:
    WindowsDeleteString(v17);
LABEL_17:
  if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147221164 )
    goto LABEL_18;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x242,
    (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
    (const char *)v12,
    v23);
  return v12;
}

```

## disassembly

```asm
0x180001380  mov     rax, rsp
0x180001383  push    rbx
0x180001384  push    rbp
0x180001385  push    rsi
0x180001386  push    r14
0x180001388  push    r15
0x18000138a  sub     rsp, 50h
0x18000138e  mov     rbp, rcx
0x180001391  mov     byte ptr [rax+20h], 0
0x180001395  mov     esi, 1
0x18000139a  mov     byte ptr [rax-48h], 0
0x18000139e  lea     rcx, [rax+20h]; this
0x1800013a2  mov     [rax-44h], esi
0x1800013a5  mov     r14, r8
0x1800013a8  mov     r15, rdx
0x1800013ab  call    ?CheckGroupPolicy@AdvertisingIdHelpers@@YAJPEA_N@Z; AdvertisingIdHelpers::CheckGroupPolicy(bool *)
0x1800013b0  mov     ebx, eax
0x1800013b2  test    eax, eax
0x1800013b4  js      loc_180001590
0x1800013ba  cmp     byte ptr [rsp+78h+arg_18], 0
0x1800013c2  mov     [rsp+78h+arg_0], rdi
0x1800013ca  mov     [rsp+78h+arg_8], r12
0x1800013d2  jnz     loc_180001471
0x1800013d8  xor     r12d, r12d
0x1800013db  mov     [rsp+78h+arg_18], r12d
0x1800013e3  call    IsIsChildAccountPresent
0x1800013e8  test    al, al
0x1800013ea  jz      short loc_18000142F
0x1800013ec  lea     rcx, [rsp+78h+string]; this
0x1800013f1  mov     [rsp+78h+string], r12
0x1800013f6  call    ?GetCurrentUserSid@AdvertisingIdHelpers@@YAJPEAVString@Internal@Windows@@@Z; AdvertisingIdHelpers::GetCurrentUserSid(Windows::Internal::String *)
0x1800013fb  mov     edi, eax
0x1800013fd  test    eax, eax
0x1800013ff  js      loc_180001564
0x180001405  mov     rbx, [rsp+78h+string]
0x18000140a  lea     rdx, [rsp+78h+arg_18]
0x180001412  mov     rcx, rbx
0x180001415  call    cs:__imp_IsChildAccount
0x18000141b  mov     edi, eax
0x18000141d  test    eax, eax
0x18000141f  js      short loc_180001478
0x180001421  test    rbx, rbx
0x180001424  jz      short loc_18000142F
0x180001426  mov     rcx, rbx; string
0x180001429  call    cs:__imp_WindowsDeleteString
0x18000142f  cmp     [rsp+78h+arg_18], r12d
0x180001437  mov     ebx, r12d
0x18000143a  setnz   al
0x18000143d  test    al, al
0x18000143f  jz      short loc_1800014AB
0x180001441  mov     edi, 2
0x180001446  mov     esi, edi
0x180001448  mov     [r15], edi
0x18000144b  test    r14, r14
0x18000144e  jz      short loc_180001453
0x180001450  mov     [r14], esi
0x180001453  mov     eax, ebx
0x180001455  mov     rdi, [rsp+78h+arg_0]
0x18000145d  mov     r12, [rsp+78h+arg_8]
0x180001465  add     rsp, 50h
0x180001469  pop     r15
0x18000146b  pop     r14
0x18000146d  pop     rsi
0x18000146e  pop     rbp
0x18000146f  pop     rbx
0x180001470  retn
0x180001471  mov     edi, 2
0x180001476  jmp     short loc_180001448
0x180001478  mov     rcx, [rsp+78h]; this
0x18000147d  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001484  mov     r9d, eax; char *
0x180001487  mov     edx, 19Ch; void *
0x18000148c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001491  test    rbx, rbx
0x180001494  jz      short loc_18000149F
0x180001496  mov     rcx, rbx; string
0x180001499  call    cs:__imp_WindowsDeleteString
0x18000149f  mov     ecx, 80000000h
0x1800014a4  lea     eax, [rdi+rcx]
0x1800014a7  test    ecx, eax
0x1800014a9  jz      short loc_1800014D2
0x1800014ab  lea     rcx, [rsp+78h+var_48]; this
0x1800014b0  call    ?CheckMsaChildAccount@AdvertisingIdHelpers@@YAJPEA_N@Z; AdvertisingIdHelpers::CheckMsaChildAccount(bool *)
0x1800014b5  mov     ebx, eax
0x1800014b7  test    eax, eax
0x1800014b9  js      loc_1800015B0
0x1800014bf  cmp     [rsp+78h+var_48], r12b
0x1800014c4  jz      short loc_1800014FA
0x1800014c6  mov     edi, 2
0x1800014cb  mov     esi, edi
0x1800014cd  jmp     loc_180001448
0x1800014d2  cmp     edi, 80040154h
0x1800014d8  jz      short loc_1800014AB
0x1800014da  mov     rcx, [rsp+78h]; this
0x1800014df  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800014e6  mov     r9d, edi; char *
0x1800014e9  mov     edx, 242h; void *
0x1800014ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800014f3  mov     eax, edi
0x1800014f5  jmp     loc_180001455
0x1800014fa  mov     rdx, r12
0x1800014fd  mov     [rsp+78h+Sid], rdx
0x180001502  test    rbp, rbp
0x180001505  jz      short loc_18000151A
0x180001507  lea     rdx, [rsp+78h+Sid]; Sid
0x18000150c  mov     rcx, rbp; StringSid
0x18000150f  call    cs:__imp_ConvertStringSidToSidW
0x180001515  mov     rdx, [rsp+78h+Sid]
0x18000151a  lea     r9, [rsp+78h+var_44]
0x18000151f  mov     qword ptr [rsp+78h+var_58], r12; int
0x180001524  lea     r8, aAdvertisinginf; "AdvertisingInfo"
0x18000152b  mov     ecx, esi
0x18000152d  call    cs:__imp_CPSSGetDwordSetting
0x180001533  mov     ebx, eax
0x180001535  test    eax, eax
0x180001537  js      loc_1800015CE
0x18000153d  cmp     [rsp+78h+var_44], r12d
0x180001542  mov     edi, r12d
0x180001545  mov     rcx, rbp; this
0x180001548  mov     esi, r12d
0x18000154b  setnz   dil
0x18000154f  call    ?EnsureAdvertisingIdAcl@AdvertisingIdHelpers@@YAJPEBG@Z; AdvertisingIdHelpers::EnsureAdvertisingIdAcl(ushort const *)
0x180001554  test    eax, eax
0x180001556  js      loc_1800015EC
0x18000155c  mov     ebx, r12d
0x18000155f  jmp     loc_180001448
0x180001564  mov     rcx, [rsp+78h]; this
0x180001569  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001570  mov     r9d, eax; char *
0x180001573  mov     edx, 19Bh; void *
0x180001578  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000157d  mov     rcx, [rsp+78h+string]
0x180001582  test    rcx, rcx
0x180001585  jnz     loc_180001499
0x18000158b  jmp     loc_18000149F
0x180001590  mov     rcx, [rsp+78h]; this
0x180001595  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x18000159c  mov     r9d, ebx; char *
0x18000159f  mov     edx, 231h; void *
0x1800015a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800015a9  mov     eax, ebx
0x1800015ab  jmp     loc_180001465
0x1800015b0  mov     rcx, [rsp+78h]; this
0x1800015b5  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800015bc  mov     r9d, ebx; char *
0x1800015bf  mov     edx, 24Ch; void *
0x1800015c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800015c9  jmp     loc_180001453
0x1800015ce  mov     rcx, [rsp+78h]; this
0x1800015d3  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800015da  mov     r9d, ebx; char *
0x1800015dd  mov     edx, 263h; void *
0x1800015e2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800015e7  jmp     loc_180001453
0x1800015ec  mov     rcx, [rsp+78h]; this
0x1800015f1  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800015f8  mov     r9d, eax; char *
0x1800015fb  mov     edx, 273h; void *
0x180001600  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001605  jmp     loc_18000155C
```

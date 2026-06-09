# HrGetNlaSignatureProfile(HKEY__ *,tagNLA_SIGNATURE *,_GUID *,ulong *)

- ea: `0x1800386bc`
- end: `0x18003886f`
- name: `?HrGetNlaSignatureProfile@@YAJPEAUHKEY__@@PEAUtagNLA_SIGNATURE@@PEAU_GUID@@PEAK@Z`
- size: `435`
- prototype: `int(HKEY, struct tagNLA_SIGNATURE *, struct _GUID *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180072b30`
- `0x1800a6020`

## callees

- `0x18000fab0`
- `0x180014cc0`
- `0x1800307cc`
- `0x1800386bc`
- `0x180038950`
- `0x180047ff4`
- `0x18004c5bc`
- `0x1800a88a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180038756`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180038756`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003883f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003884d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003883f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003884d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800387e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800387e5`

## string_xrefs

- `0x1800387c1`: `onecore\net\netprofiles\service\src\host\lib\common.cpp`
- `0x1800387f3`: `onecore\net\netprofiles\service\src\host\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall HrGetNlaSignatureProfile(
        HKEY a1,
        struct tagNLA_SIGNATURE *a2,
        struct _GUID *a3,
        unsigned __int8 *a4)
{
  int v4; // esi
  unsigned int Value; // ebx
  int v8; // eax
  unsigned int v9; // eax
  unsigned int v11; // [rsp+20h] [rbp-59h]
  HKEY hKey; // [rsp+30h] [rbp-49h] BYREF
  HKEY v13; // [rsp+38h] [rbp-41h] BYREF
  unsigned int v14[4]; // [rsp+40h] [rbp-39h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = 0;
  v13 = a1;
  v14[0] = 0;
  if ( a4 )
    *(_DWORD *)a4 = 0;
  if ( !a1 )
  {
    Value = HrOpenSignatureKey(a2, 0x20019u, &v13);
    if ( Value )
      return Value;
    a1 = v13;
    v4 = 1;
  }
  v14[0] = 78;
  Value = HrRegQueryValueEx(a1, L"ProfileGuid", 0, (unsigned __int8 *)sz, v14);
  if ( !Value )
  {
    Value = IIDFromString(sz, a3);
    if ( !Value )
    {
      if ( a4 )
      {
        hKey = 0;
        Value = HrOpenProfileKey(sz, 0x20019u, &hKey);
        if ( !Value )
        {
          v14[0] = 4;
          v8 = HrRegQueryValueEx(hKey, L"Category", 0, a4, v14);
          if ( v8 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xA29,
              (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\common.cpp",
              (const char *)(unsigned int)v8,
              v11);
          if ( *(_DWORD *)a4 == 2 )
          {
            v9 = RegDeleteValueW(hKey, L"Category");
            if ( v9 )
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0xA2C,
                (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\common.cpp",
                (const char *)v9,
                v11);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
            *(_DWORD *)a4 = 0;
          }
          RegCloseKey(hKey);
        }
      }
    }
  }
  if ( v4 )
    RegCloseKey(v13);
  return Value;
}

```

## disassembly

```asm
0x1800386bc  push    rbp
0x1800386be  push    rbx
0x1800386bf  push    rsi
0x1800386c0  push    rdi
0x1800386c1  push    r14
0x1800386c3  lea     rbp, [rsp-37h]
0x1800386c8  sub     rsp, 0B0h
0x1800386cf  mov     rax, cs:__security_cookie
0x1800386d6  xor     rax, rsp
0x1800386d9  mov     [rbp+57h+var_30], rax
0x1800386dd  xor     esi, esi
0x1800386df  mov     [rbp+57h+var_98], rcx
0x1800386e3  mov     [rbp+57h+var_90], 0
0x1800386ea  mov     rdi, r9
0x1800386ed  mov     r14, r8
0x1800386f0  mov     rax, rdx
0x1800386f3  test    r9, r9
0x1800386f6  jz      short loc_1800386FB
0x1800386f8  mov     [r9], esi
0x1800386fb  test    rcx, rcx
0x1800386fe  jnz     short loc_180038722
0x180038700  lea     r8, [rbp+57h+var_98]; HKEY *
0x180038704  mov     edx, 20019h; unsigned int
0x180038709  mov     rcx, rax; struct tagNLA_SIGNATURE *
0x18003870c  call    ?HrOpenSignatureKey@@YAJPEAUtagNLA_SIGNATURE@@KPEAPEAUHKEY__@@@Z; HrOpenSignatureKey(tagNLA_SIGNATURE *,ulong,HKEY__ * *)
0x180038711  mov     ebx, eax
0x180038713  test    eax, eax
0x180038715  jnz     loc_180038853
0x18003871b  mov     rcx, [rbp+57h+var_98]; HKEY
0x18003871f  lea     esi, [rax+1]
0x180038722  lea     rax, [rbp+57h+var_90]
0x180038726  mov     [rbp+57h+var_90], 4Eh ; 'N'
0x18003872d  lea     r9, [rbp+57h+sz]; unsigned __int8 *
0x180038731  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int *
0x180038736  xor     r8d, r8d; unsigned int *
0x180038739  lea     rdx, aProfileguid; "ProfileGuid"
0x180038740  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEB_WPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,wchar_t const *,ulong *,uchar *,ulong *)
0x180038745  mov     ebx, eax
0x180038747  test    eax, eax
0x180038749  jnz     loc_180038845
0x18003874f  mov     rdx, r14; lpiid
0x180038752  lea     rcx, [rbp+57h+sz]; lpsz
0x180038756  call    cs:__imp_IIDFromString
0x18003875c  mov     ebx, eax
0x18003875e  test    eax, eax
0x180038760  jnz     loc_180038845
0x180038766  test    rdi, rdi
0x180038769  jz      loc_180038845
0x18003876f  lea     r8, [rbp+57h+hKey]; HKEY *
0x180038773  mov     [rbp+57h+hKey], 0
0x18003877b  mov     edx, 20019h; unsigned int
0x180038780  lea     rcx, [rbp+57h+sz]; wchar_t *
0x180038784  call    ?HrOpenProfileKey@@YAJPEB_WKPEAPEAUHKEY__@@@Z; HrOpenProfileKey(wchar_t const *,ulong,HKEY__ * *)
0x180038789  mov     ebx, eax
0x18003878b  test    eax, eax
0x18003878d  jnz     loc_180038845
0x180038793  mov     rcx, [rbp+57h+hKey]; HKEY
0x180038797  lea     rax, [rbp+57h+var_90]
0x18003879b  mov     r9, rdi; unsigned __int8 *
0x18003879e  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int
0x1800387a3  xor     r8d, r8d; unsigned int *
0x1800387a6  mov     [rbp+57h+var_90], 4
0x1800387ad  lea     rdx, aCategory; "Category"
0x1800387b4  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEB_WPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,wchar_t const *,ulong *,uchar *,ulong *)
0x1800387b9  test    eax, eax
0x1800387bb  jns     short loc_1800387D5
0x1800387bd  mov     rcx, [rbp+5Fh]; this
0x1800387c1  lea     r8, aOnecoreNetNetp_19; "onecore\\net\\netprofiles\\service\\src"...
0x1800387c8  mov     r9d, eax; char *
0x1800387cb  mov     edx, 0A29h; void *
0x1800387d0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800387d5  cmp     dword ptr [rdi], 2
0x1800387d8  jnz     short loc_18003883B
0x1800387da  mov     rcx, [rbp+57h+hKey]; hKey
0x1800387de  lea     rdx, aCategory; "Category"
0x1800387e5  call    cs:__imp_RegDeleteValueW
0x1800387eb  test    eax, eax
0x1800387ed  jz      short loc_180038807
0x1800387ef  mov     rcx, [rbp+5Fh]; this
0x1800387f3  lea     r8, aOnecoreNetNetp_19; "onecore\\net\\netprofiles\\service\\src"...
0x1800387fa  mov     r9d, eax; char *
0x1800387fd  mov     edx, 0A2Ch; void *
0x180038802  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180038807  mov     rcx, cs:WPP_GLOBAL_Control
0x18003880e  lea     rax, WPP_GLOBAL_Control
0x180038815  cmp     rcx, rax
0x180038818  jz      short loc_180038835
0x18003881a  test    byte ptr [rcx+1Ch], 2
0x18003881e  jz      short loc_180038835
0x180038820  mov     rcx, [rcx+10h]
0x180038824  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18003882b  mov     edx, 0AEh
0x180038830  call    WPP_SF_
0x180038835  mov     dword ptr [rdi], 0
0x18003883b  mov     rcx, [rbp+57h+hKey]; hKey
0x18003883f  call    cs:__imp_RegCloseKey
0x180038845  test    esi, esi
0x180038847  jz      short loc_180038853
0x180038849  mov     rcx, [rbp+57h+var_98]; hKey
0x18003884d  call    cs:__imp_RegCloseKey
0x180038853  mov     eax, ebx
0x180038855  mov     rcx, [rbp+57h+var_30]
0x180038859  xor     rcx, rsp; StackCookie
0x18003885c  call    __security_check_cookie
0x180038861  add     rsp, 0B0h
0x180038868  pop     r14
0x18003886a  pop     rdi
0x18003886b  pop     rsi
0x18003886c  pop     rbx
0x18003886d  pop     rbp
0x18003886e  retn
```

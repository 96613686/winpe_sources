# CUserProfileRoamingProvider::_SetServerNtUserIni(void)

- ea: `0x1800090e0`
- end: `0x180009274`
- name: `?_SetServerNtUserIni@CUserProfileRoamingProvider@@AEAAJXZ`
- size: `404`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008258`

## callees

- `0x180005130`
- `0x180005234`
- `0x180005424`
- `0x18000547c`
- `0x180006a9c`
- `0x1800090e0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180009250`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180009250`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1800091a8`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180009234`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1800091a8`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180009234`

## string_xrefs

- `0x18000913a`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800091b7`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180009211`: `Complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserProfileRoamingProvider::_SetServerNtUserIni(CUserProfileRoamingProvider *this)
{
  __int64 v2; // rax
  int v3; // eax
  unsigned int LastError; // ebx
  const WCHAR *v5; // rbx
  const WCHAR *v6; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rax
  CUserProfileRoamingProvider *v10; // rcx
  char v11; // al
  const WCHAR *v12; // r8
  LPCWSTR lpFileName[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  memset(lpFileName, 0, 24);
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
  v3 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpFileName,
         L"%s\\%s",
         v2,
         L"ntuser.ini");
  LastError = v3;
  if ( v3 >= 0 )
  {
    v5 = lpFileName[0];
    if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 104LL))(*((_QWORD *)this + 1))
      && *(_WORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 104LL))(*((_QWORD *)this + 1)) )
    {
      v6 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 104LL))(*((_QWORD *)this + 1));
    }
    else
    {
      v6 = 0;
    }
    if ( WritePrivateProfileStringW(L"General", L"ExclusionList", v6, v5) )
    {
      if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 8) == 0 )
      {
        v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
        if ( !(unsigned int)CUserProfileRoamingProvider::_IsPartialRoamingProfile(v10, v9) )
          goto LABEL_16;
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1));
      v12 = L"Partial";
      if ( (v11 & 4) == 0 )
        v12 = L"Complete";
      if ( !WritePrivateProfileStringW(L"ProfileLoadType", L"LastUploadState", v12, v5) )
      {
LABEL_16:
        SetFileAttributesW(v5, 2u);
        LastError = 0;
        goto LABEL_17;
      }
      v8 = 2688;
    }
    else
    {
      v8 = 2679;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                  v7);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA70,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v3,
      (int)lpFileName[0]);
  }
LABEL_17:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x1800090e0  mov     rax, rsp
0x1800090e3  mov     [rax+8], rbx
0x1800090e7  mov     [rax+10h], rsi
0x1800090eb  push    rdi
0x1800090ec  sub     rsp, 40h
0x1800090f0  mov     rdi, rcx
0x1800090f3  xor     esi, esi
0x1800090f5  mov     [rax-28h], rsi
0x1800090f9  mov     [rax-20h], rsi
0x1800090fd  mov     [rax-18h], rsi
0x180009101  mov     rcx, [rcx+8]
0x180009105  mov     rax, [rcx]
0x180009108  mov     rax, [rax+50h]
0x18000910c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009111  mov     r8, rax
0x180009114  lea     r9, ?c_szNTUserIni@@3QBGB; "ntuser.ini"
0x18000911b  lea     rdx, aSS; "%s\\%s"
0x180009122  lea     rcx, [rsp+48h+lpFileName]
0x180009127  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000912c  mov     ebx, eax
0x18000912e  test    eax, eax
0x180009130  jns     short loc_180009150
0x180009132  mov     rcx, [rsp+48h]; this
0x180009137  mov     r9d, eax; char *
0x18000913a  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180009141  mov     edx, 0A70h; void *
0x180009146  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000914b  jmp     loc_180009258
0x180009150  mov     rbx, [rsp+48h+lpFileName]
0x180009155  mov     rcx, [rdi+8]
0x180009159  mov     rax, [rcx]
0x18000915c  mov     rax, [rax+68h]
0x180009160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009165  test    rax, rax
0x180009168  jz      short loc_180009191
0x18000916a  mov     rcx, [rdi+8]
0x18000916e  mov     rax, [rcx]
0x180009171  mov     rax, [rax+68h]
0x180009175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000917a  cmp     [rax], si
0x18000917d  jz      short loc_180009191
0x18000917f  mov     rcx, [rdi+8]
0x180009183  mov     rax, [rcx]
0x180009186  mov     rax, [rax+68h]
0x18000918a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000918f  jmp     short loc_180009194
0x180009191  mov     rax, rsi
0x180009194  mov     r9, rbx; lpFileName
0x180009197  mov     r8, rax; lpString
0x18000919a  lea     rdx, aExclusionlist; "ExclusionList"
0x1800091a1  lea     rcx, aGeneral; "General"
0x1800091a8  call    cs:__imp_WritePrivateProfileStringW
0x1800091ae  test    eax, eax
0x1800091b0  jnz     short loc_1800091CF
0x1800091b2  mov     edx, 0A77h; void *
0x1800091b7  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800091be  mov     rcx, [rsp+48h]; this
0x1800091c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800091c8  mov     ebx, eax
0x1800091ca  jmp     loc_180009258
0x1800091cf  mov     rcx, [rdi+8]
0x1800091d3  mov     rax, [rcx]
0x1800091d6  mov     rax, [rax+10h]
0x1800091da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091df  test    al, 8
0x1800091e1  jnz     short loc_1800091FF
0x1800091e3  mov     rcx, [rdi+8]
0x1800091e7  mov     rax, [rcx]
0x1800091ea  mov     rax, [rax+50h]
0x1800091ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091f3  mov     rdx, rax; unsigned __int16 *
0x1800091f6  call    ?_IsPartialRoamingProfile@CUserProfileRoamingProvider@@AEAAHPEBG@Z; CUserProfileRoamingProvider::_IsPartialRoamingProfile(ushort const *)
0x1800091fb  test    eax, eax
0x1800091fd  jz      short loc_180009248
0x1800091ff  mov     rcx, [rdi+8]
0x180009203  mov     rax, [rcx]
0x180009206  mov     rax, [rax+8]
0x18000920a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000920f  test    al, 4
0x180009211  lea     rax, String; "Complete"
0x180009218  lea     r8, String2; "Partial"
0x18000921f  cmovz   r8, rax; lpString
0x180009223  mov     r9, rbx; lpFileName
0x180009226  lea     rdx, KeyName; "LastUploadState"
0x18000922d  lea     rcx, AppName; "ProfileLoadType"
0x180009234  call    cs:__imp_WritePrivateProfileStringW
0x18000923a  test    eax, eax
0x18000923c  jz      short loc_180009248
0x18000923e  mov     edx, 0A80h
0x180009243  jmp     loc_1800091B7
0x180009248  mov     edx, 2; dwFileAttributes
0x18000924d  mov     rcx, rbx; lpFileName
0x180009250  call    cs:__imp_SetFileAttributesW
0x180009256  mov     ebx, esi
0x180009258  lea     rcx, [rsp+48h+lpFileName]
0x18000925d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009262  mov     eax, ebx
0x180009264  mov     rbx, [rsp+48h+arg_0]
0x180009269  mov     rsi, [rsp+48h+arg_8]
0x18000926e  add     rsp, 40h
0x180009272  pop     rdi
0x180009273  retn
```

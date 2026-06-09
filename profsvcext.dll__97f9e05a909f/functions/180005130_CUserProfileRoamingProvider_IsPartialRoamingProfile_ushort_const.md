# CUserProfileRoamingProvider::_IsPartialRoamingProfile(ushort const *)

- ea: `0x180005130`
- end: `0x18000522d`
- name: `?_IsPartialRoamingProfile@CUserProfileRoamingProvider@@AEAAHPEBG@Z`
- size: `253`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800090e0`
- `0x180012314`

## callees

- `0x180005130`
- `0x180005234`
- `0x180005424`
- `0x18000a520`
- `0x18000fca8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800051f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800051f9`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800051d3`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800051d3`

## string_xrefs

- `0x180005181`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800051be`: `Complete`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::_IsPartialRoamingProfile(
        CUserProfileRoamingProvider *this,
        const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  int v3; // eax
  LPCWSTR lpFileName[3]; // [rsp+30h] [rbp-50h] BYREF
  WCHAR ReturnedString; // [rsp+48h] [rbp-38h] BYREF
  __int128 v7; // [rsp+4Ah] [rbp-36h]
  _BYTE v8[22]; // [rsp+5Ah] [rbp-26h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v2 = 0;
  memset(lpFileName, 0, sizeof(lpFileName));
  v3 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpFileName,
         L"%s\\%s",
         a2,
         L"ntuser.ini");
  if ( v3 >= 0 )
  {
    ReturnedString = 0;
    v7 = 0;
    memset(v8, 0, sizeof(v8));
    GetPrivateProfileStringW(L"ProfileLoadType", L"LastUploadState", L"Complete", &ReturnedString, 0x14u, lpFileName[0]);
    LOBYTE(v2) = CompareStringW(0x7Fu, 1u, &ReturnedString, -1, L"Partial", -1) == 2;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB88,
      (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v3);
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  return v2;
}

```

## disassembly

```asm
0x180005130  mov     [rsp-8+arg_0], rbx
0x180005135  push    rbp
0x180005136  mov     rbp, rsp
0x180005139  sub     rsp, 80h
0x180005140  mov     rax, cs:__security_cookie
0x180005147  xor     rax, rsp
0x18000514a  mov     [rbp+var_10], rax
0x18000514e  xor     ebx, ebx
0x180005150  mov     [rbp+var_50], rbx
0x180005154  mov     [rbp+var_48], rbx
0x180005158  mov     [rbp+var_40], rbx
0x18000515c  lea     r9, ?c_szNTUserIni@@3QBGB; "ntuser.ini"
0x180005163  mov     r8, rdx
0x180005166  lea     rdx, aSS; "%s\\%s"
0x18000516d  lea     rcx, [rbp+var_50]
0x180005171  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180005176  mov     rcx, [rbp+8]; this
0x18000517a  test    eax, eax
0x18000517c  jns     short loc_180005194
0x18000517e  mov     r9d, eax; char *
0x180005181  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180005188  mov     edx, 0B88h; void *
0x18000518d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005192  jmp     short loc_180005205
0x180005194  mov     [rbp+ReturnedString], bx
0x180005198  xorps   xmm0, xmm0
0x18000519b  xor     eax, eax
0x18000519d  movups  [rbp+var_36], xmm0
0x1800051a1  movups  xmmword ptr [rbp+var_26], xmm0
0x1800051a5  mov     qword ptr [rbp+var_26+0Eh], rax
0x1800051a9  mov     rax, [rbp+var_50]
0x1800051ad  mov     [rsp+80h+lpFileName], rax; lpFileName
0x1800051b2  mov     [rsp+80h+nSize], 14h; nSize
0x1800051ba  lea     r9, [rbp+ReturnedString]; lpReturnedString
0x1800051be  lea     r8, String; "Complete"
0x1800051c5  lea     rdx, KeyName; "LastUploadState"
0x1800051cc  lea     rcx, AppName; "ProfileLoadType"
0x1800051d3  call    cs:__imp_GetPrivateProfileStringW
0x1800051d9  or      r9d, 0FFFFFFFFh; cchCount1
0x1800051dd  mov     dword ptr [rsp+80h+lpFileName], r9d; cchCount2
0x1800051e2  lea     rax, String2; "Partial"
0x1800051e9  mov     qword ptr [rsp+80h+nSize], rax; lpString2
0x1800051ee  lea     r8, [rbp+ReturnedString]; lpString1
0x1800051f2  lea     edx, [r9+2]; dwCmpFlags
0x1800051f6  lea     ecx, [rdx+7Eh]; Locale
0x1800051f9  call    cs:__imp_CompareStringW
0x1800051ff  cmp     eax, 2
0x180005202  setz    bl
0x180005205  lea     rcx, [rbp+var_50]
0x180005209  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000520e  mov     eax, ebx
0x180005210  mov     rcx, [rbp+var_10]
0x180005214  xor     rcx, rsp; StackCookie
0x180005217  call    __security_check_cookie
0x18000521c  mov     rbx, [rsp+80h+arg_0]
0x180005224  add     rsp, 80h
0x18000522b  pop     rbp
0x18000522c  retn
```

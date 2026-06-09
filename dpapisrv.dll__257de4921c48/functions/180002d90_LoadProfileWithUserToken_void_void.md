# LoadProfileWithUserToken(void *,void * *)

- ea: `0x180002d90`
- end: `0x180002f12`
- name: `?LoadProfileWithUserToken@@YAKPEAXPEAPEAX@Z`
- size: `386`
- prototype: `__int64 __fastcall(HANDLE hToken, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028900`

## callees

- `0x180002d90`
- `0x180003080`
- `0x180007f10`
- `0x18001d810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002eb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002edf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002edf`
- `USERENV!LoadUserProfileW` at `0x180002ea1`
- `USERENV!LoadUserProfileW` at `0x180002ea1`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180002e60`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180002e60`

## string_xrefs

- `0x180002e0b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall LoadProfileWithUserToken(HANDLE hToken, void **a2)
{
  DWORD LastError; // eax
  __int64 v5; // r9
  DWORD v6; // ebx
  DWORD cchReferencedDomainName; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-CCh] BYREF
  PSID Sid; // [rsp+38h] [rbp-C8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-C0h] BYREF
  _PROFILEINFOW ProfileInfo; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+290h] [rbp+190h] BYREF

  cchName = 0;
  memset(&ProfileInfo, 0, sizeof(ProfileInfo));
  cchReferencedDomainName = 0;
  peUse = 0;
  Sid = 0;
  if ( !(unsigned int)GetTokenUserSid(hToken, &Sid) )
  {
    LastError = GetLastError();
    v5 = 2796;
LABEL_3:
    v6 = LastError;
    DebugTraceError(LastError, "dwStatus", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v5);
    goto LABEL_9;
  }
  cchName = 257;
  cchReferencedDomainName = 256;
  if ( LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    ProfileInfo.dwSize = 56;
    ProfileInfo.lpUserName = Name;
    ProfileInfo.dwFlags = 1;
    if ( !LoadUserProfileW(hToken, &ProfileInfo) )
    {
      LastError = GetLastError();
      v5 = 2815;
      goto LABEL_3;
    }
    v6 = 0;
    *a2 = ProfileInfo.hProfile;
  }
  else
  {
    v6 = GetLastError();
  }
LABEL_9:
  if ( Sid )
    LocalFree(Sid);
  return v6;
}

```

## disassembly

```asm
0x180002d90  mov     [rsp-8+arg_10], rbx
0x180002d95  mov     [rsp-8+arg_18], rsi
0x180002d9a  push    rbp
0x180002d9b  lea     rbp, [rsp-3A0h]
0x180002da3  sub     rsp, 4A0h
0x180002daa  mov     rax, cs:__security_cookie
0x180002db1  xor     rax, rsp
0x180002db4  mov     [rbp+3A0h+var_10], rax
0x180002dbb  xor     eax, eax
0x180002dbd  xorps   xmm0, xmm0
0x180002dc0  mov     rsi, rdx
0x180002dc3  mov     [rsp+4A0h+ProfileInfo.hProfile], rax
0x180002dc8  lea     rdx, [rsp+4A0h+Sid]
0x180002dcd  mov     [rsp+4A0h+cchName], eax
0x180002dd1  movups  xmmword ptr [rsp+4A0h+ProfileInfo.dwSize], xmm0
0x180002dd6  mov     [rsp+4A0h+var_470], eax
0x180002dda  mov     rbx, rcx
0x180002ddd  movups  xmmword ptr [rsp+4A0h+ProfileInfo.lpProfilePath], xmm0
0x180002de2  mov     [rsp+4A0h+var_460], eax
0x180002de6  movups  xmmword ptr [rsp+4A0h+ProfileInfo.lpServerName], xmm0
0x180002deb  mov     [rsp+4A0h+Sid], rax
0x180002df0  call    GetTokenUserSid
0x180002df5  test    eax, eax
0x180002df7  jnz     short loc_180002E27
0x180002df9  call    cs:__imp_GetLastError
0x180002e00  nop     dword ptr [rax+rax+00h]
0x180002e05  mov     r9d, 0AECh
0x180002e0b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180002e12  mov     ecx, eax
0x180002e14  lea     rdx, aDwstatus; "dwStatus"
0x180002e1b  mov     ebx, eax
0x180002e1d  call    DebugTraceError
0x180002e22  jmp     loc_180002ED2
0x180002e27  mov     rcx, [rsp+4A0h+Sid]; Sid
0x180002e2c  lea     rax, [rsp+4A0h+var_460]
0x180002e31  mov     [rsp+4A0h+peUse], rax; peUse
0x180002e36  lea     r9, [rbp+3A0h+ReferencedDomainName]; ReferencedDomainName
0x180002e3d  lea     rax, [rsp+4A0h+var_470]
0x180002e42  mov     [rsp+4A0h+cchName], 101h
0x180002e4a  lea     r8, [rsp+4A0h+cchName]; cchName
0x180002e4f  mov     [rsp+4A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180002e54  lea     rdx, [rbp+3A0h+Name]; Name
0x180002e58  mov     [rsp+4A0h+var_470], 100h
0x180002e60  call    cs:__imp_LookupAccountSidLocalW
0x180002e67  nop     dword ptr [rax+rax+00h]
0x180002e6c  test    eax, eax
0x180002e6e  jnz     short loc_180002E80
0x180002e70  call    cs:__imp_GetLastError
0x180002e77  nop     dword ptr [rax+rax+00h]
0x180002e7c  mov     ebx, eax
0x180002e7e  jmp     short loc_180002ED2
0x180002e80  lea     rax, [rbp+3A0h+Name]
0x180002e84  mov     [rsp+4A0h+ProfileInfo.dwSize], 38h ; '8'
0x180002e8c  lea     rdx, [rsp+4A0h+ProfileInfo]; lpProfileInfo
0x180002e91  mov     [rsp+4A0h+ProfileInfo.lpUserName], rax
0x180002e96  mov     rcx, rbx; hToken
0x180002e99  mov     [rsp+4A0h+ProfileInfo.dwFlags], 1
0x180002ea1  call    cs:__imp_LoadUserProfileW
0x180002ea8  nop     dword ptr [rax+rax+00h]
0x180002ead  test    eax, eax
0x180002eaf  jnz     short loc_180002EC8
0x180002eb1  call    cs:__imp_GetLastError
0x180002eb8  nop     dword ptr [rax+rax+00h]
0x180002ebd  mov     r9d, 0AFFh
0x180002ec3  jmp     loc_180002E0B
0x180002ec8  mov     rax, [rsp+4A0h+ProfileInfo.hProfile]
0x180002ecd  xor     ebx, ebx
0x180002ecf  mov     [rsi], rax
0x180002ed2  cmp     [rsp+4A0h+Sid], 0
0x180002ed8  jz      short loc_180002EEB
0x180002eda  mov     rcx, [rsp+4A0h+Sid]; hMem
0x180002edf  call    cs:__imp_LocalFree
0x180002ee6  nop     dword ptr [rax+rax+00h]
0x180002eeb  mov     eax, ebx
0x180002eed  mov     rcx, [rbp+3A0h+var_10]
0x180002ef4  xor     rcx, rsp; StackCookie
0x180002ef7  call    __security_check_cookie
0x180002efc  lea     r11, [rsp+4A0h+var_s0]
0x180002f04  mov     rbx, [r11+20h]
0x180002f08  mov     rsi, [r11+28h]
0x180002f0c  mov     rsp, r11
0x180002f0f  pop     rbp
0x180002f10  retn
```

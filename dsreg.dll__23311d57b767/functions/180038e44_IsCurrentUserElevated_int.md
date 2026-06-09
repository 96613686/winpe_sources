# IsCurrentUserElevated(int &)

- ea: `0x180038e44`
- end: `0x180038f38`
- name: `?IsCurrentUserElevated@@YAJAEAH@Z`
- size: `244`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800414f8`
- `0x180098940`
- `0x18009b940`
- `0x18009f520`
- `0x1800a20a4`
- `0x1800a523c`

## callees

- `0x1800084f4`
- `0x18001ecdc`
- `0x180038e44`
- `0x180044300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038eb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038eb0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180038f12`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180038f12`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180038ea6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180038ea6`

## string_xrefs

- `0x180038eee`: `CheckProcessForSid`
- `0x180038ec8`: `AllocateAndInitializeSid`

## pseudocode

```c
__int64 __fastcall IsCurrentUserElevated(PBOOL IsMember)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  int v4; // eax
  PSID pSid; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v7; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&v7.Value[4] = 1280;
  pSid = 0;
  *(_DWORD *)v7.Value = 0;
  if ( AllocateAndInitializeSid(&v7, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v4 = CheckProcessForSid(pSid, IsMember);
    v3 = v4;
    if ( v4 < 0 )
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"IsCurrentUserElevated",
        L"CheckProcessForSid",
        (unsigned int)v4);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"IsCurrentUserElevated",
      L"AllocateAndInitializeSid",
      v3);
  }
  if ( pSid )
    FreeSid(pSid);
  return v3;
}

```

## disassembly

```asm
0x180038e44  mov     r11, rsp
0x180038e47  mov     [r11+10h], rbx
0x180038e4b  push    rdi
0x180038e4c  sub     rsp, 80h
0x180038e53  mov     rax, cs:__security_cookie
0x180038e5a  xor     rax, rsp
0x180038e5d  mov     [rsp+88h+var_18], rax
0x180038e62  xor     edi, edi
0x180038e64  mov     [rsp+88h+var_1C], 500h
0x180038e6b  lea     rax, [r11-28h]
0x180038e6f  mov     [r11-28h], rdi
0x180038e73  mov     [r11-38h], rax
0x180038e77  mov     rbx, rcx
0x180038e7a  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x180038e7e  lea     rcx, [r11-20h]; pIdentifierAuthority
0x180038e82  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x180038e86  lea     r8d, [rdi+20h]; nSubAuthority0
0x180038e8a  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x180038e8e  mov     r9d, 220h; nSubAuthority1
0x180038e94  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x180038e98  mov     dl, 2; nSubAuthorityCount
0x180038e9a  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x180038e9e  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x180038ea2  mov     [rsp+88h+var_20], edi
0x180038ea6  call    cs:__imp_AllocateAndInitializeSid
0x180038eac  test    eax, eax
0x180038eae  jnz     short loc_180038ED8
0x180038eb0  call    cs:__imp_GetLastError
0x180038eb6  mov     ebx, eax
0x180038eb8  test    eax, eax
0x180038eba  jle     short loc_180038EC5
0x180038ebc  movzx   ebx, ax
0x180038ebf  or      ebx, 80070000h
0x180038ec5  mov     r9d, ebx
0x180038ec8  lea     r8, aAllocateandini; "AllocateAndInitializeSid"
0x180038ecf  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x180038ed6  jmp     short loc_180038EFC
0x180038ed8  mov     rcx, [rsp+88h+pSid]; SidToCheck
0x180038edd  mov     rdx, rbx; IsMember
0x180038ee0  call    ?CheckProcessForSid@@YAJPEAXAEAH@Z; CheckProcessForSid(void *,int &)
0x180038ee5  mov     ebx, eax
0x180038ee7  test    eax, eax
0x180038ee9  jns     short loc_180038F08
0x180038eeb  mov     r9d, eax
0x180038eee  lea     r8, aCheckprocessfo; "CheckProcessForSid"
0x180038ef5  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180038efc  lea     rdx, aIscurrentusere; "IsCurrentUserElevated"
0x180038f03  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180038f08  mov     rcx, [rsp+88h+pSid]; pSid
0x180038f0d  test    rcx, rcx
0x180038f10  jz      short loc_180038F18
0x180038f12  call    cs:__imp_FreeSid
0x180038f18  mov     eax, ebx
0x180038f1a  mov     rcx, [rsp+88h+var_18]
0x180038f1f  xor     rcx, rsp; StackCookie
0x180038f22  call    __security_check_cookie
0x180038f27  mov     rbx, [rsp+88h+arg_8]
0x180038f2f  add     rsp, 80h
0x180038f36  pop     rdi
0x180038f37  retn
```

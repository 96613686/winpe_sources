# TOKEN_CACHE::LogonUserW(ushort const *,ushort const *,ushort const *,ulong,ulong,void * *,void * *,void * *,ulong *,_QUOTA_LIMITS *,_TOKEN_GROUPS *)

- ea: `0x18005ef04`
- end: `0x18005f249`
- name: `?LogonUserW@TOKEN_CACHE@@QEAAHPEBG00KKPEAPEAX11PEAKPEAU_QUOTA_LIMITS@@PEAU_TOKEN_GROUPS@@@Z`
- size: `837`
- prototype: `int(TOKEN_CACHE *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, void **, void **, void **, unsigned int *, struct _QUOTA_LIMITS *, struct _TOKEN_GROUPS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005e468`

## callees

- `0x18005ef04`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f1f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f1f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005efb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005efb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f178`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f1da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f1da`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005f1ed`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005f210`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005f1ed`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005f210`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005f041`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005f041`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x18005efac`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x18005efac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f08f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f08f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f1c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f206`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f1c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f206`
- `iisutil!PuDbgPrintError` at `0x18005f002`
- `iisutil!PuDbgPrintError` at `0x18005f0df`
- `iisutil!PuDbgPrintError` at `0x18005f1c0`
- `iisutil!PuDbgPrintError` at `0x18005f002`
- `iisutil!PuDbgPrintError` at `0x18005f0df`
- `iisutil!PuDbgPrintError` at `0x18005f1c0`
- `SspiCli!LogonUserExExW` at `0x18005f16a`
- `SspiCli!LogonUserExExW` at `0x18005f16a`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18005ef9d`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18005ef9d`

## string_xrefs

- `0x18005eff7`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18005f0d8`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18005f1b5`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18005efe9`: `TOKEN_CACHE::LogonUserW`
- `0x18005f0c3`: `TOKEN_CACHE::LogonUserW`
- `0x18005f1a7`: `TOKEN_CACHE::LogonUserW`
- `0x18005f06c`: `AllocateAndInitializeSid failed\n`
- `0x18005f0b7`: `Unable to alloc token groups\n`

## pseudocode

```c
BOOL __fastcall TOKEN_CACHE::LogonUserW(
        TOKEN_CACHE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwLogonType,
        DWORD dwLogonProvider,
        void **phToken,
        void **a8,
        void **ppProfileBuffer,
        unsigned int *pdwProfileLength,
        struct _QUOTA_LIMITS *a11,
        struct _TOKEN_GROUPS *a12)
{
  BOOL result; // eax
  signed int v16; // eax
  DWORD v17; // ebx
  signed int v18; // eax
  _DWORD *v19; // rax
  _DWORD *v20; // rdi
  DWORD v21; // eax
  __int64 v22; // rcx
  signed int LastError; // eax
  PSID pSid; // [rsp+60h] [rbp-29h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-21h] BYREF
  struct _LUID Luid; // [rsp+70h] [rbp-19h] BYREF
  unsigned int *v27; // [rsp+78h] [rbp-11h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp-9h] BYREF

  v27 = pdwProfileLength;
  pSid = 0;
  hObject = 0;
  Luid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !a12 )
    return LogonUserExW(a2, a3, a4, dwLogonType, dwLogonProvider, phToken, 0, ppProfileBuffer, pdwProfileLength, 0);
  if ( AllocateLocallyUniqueId(&Luid) )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 3u, 5u, Luid.HighPart, Luid.LowPart, 0, 0, 0, 0, 0, &pSid) )
    {
      v19 = LocalAlloc(0x40u, 16LL * (a12->GroupCount + 1) + 24);
      v20 = v19;
      if ( v19 )
      {
        *v19 = a12->GroupCount + 1;
        *((_QWORD *)v19 + 1) = pSid;
        v21 = 0;
        for ( v20[4] = -1073741817; v21 < a12->GroupCount; ++v21 )
        {
          v22 = 2LL * (v21 + 1);
          *(_QWORD *)&v20[2 * v22 + 2] = a12->Groups[v21].Sid;
          v20[2 * v22 + 4] = a12->Groups[v21].Attributes;
        }
        if ( (unsigned int)LogonUserExExW(
                             a2,
                             a3,
                             a4,
                             dwLogonType,
                             dwLogonProvider,
                             v20,
                             &hObject,
                             0,
                             ppProfileBuffer,
                             v27,
                             0) )
        {
          LocalFree(v20);
          FreeSid(pSid);
          result = 1;
          *phToken = hObject;
          return result;
        }
        LastError = GetLastError();
        v17 = LastError;
        if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
            2043,
            "TOKEN_CACHE::LogonUserW",
            LastError,
            "LogonUser failed\n");
        }
        LocalFree(v20);
      }
      else
      {
        v17 = 8;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
            2001,
            "TOKEN_CACHE::LogonUserW",
            -2147024888,
            "Unable to alloc token groups\n");
      }
    }
    else
    {
      v18 = GetLastError();
      v17 = v18;
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
          1986,
          "TOKEN_CACHE::LogonUserW",
          v18,
          "AllocateAndInitializeSid failed\n");
      }
    }
  }
  else
  {
    v16 = GetLastError();
    v17 = v16;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
        1970,
        "TOKEN_CACHE::LogonUserW",
        v16,
        "AllocateLocallyUniqueId failed\n");
    }
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  SetLastError(v17);
  return 0;
}

```

## disassembly

```asm
0x18005ef04  mov     [rsp-8+arg_0], rbx
0x18005ef09  push    rbp
0x18005ef0a  push    rsi
0x18005ef0b  push    rdi
0x18005ef0c  push    r12
0x18005ef0e  push    r13
0x18005ef10  push    r14
0x18005ef12  push    r15
0x18005ef14  lea     rbp, [rsp-7]
0x18005ef19  sub     rsp, 90h
0x18005ef20  mov     rax, cs:__security_cookie
0x18005ef27  xor     rax, rsp
0x18005ef2a  mov     [rbp+37h+var_38], rax
0x18005ef2e  mov     rbx, [rbp+37h+arg_58]
0x18005ef35  xor     edi, edi
0x18005ef37  mov     rax, [rbp+37h+arg_48]
0x18005ef3e  mov     r12, r9
0x18005ef41  mov     rsi, [rbp+37h+arg_30]
0x18005ef45  mov     r15, r8
0x18005ef48  mov     r13, [rbp+37h+arg_40]
0x18005ef4f  mov     r14, rdx
0x18005ef52  mov     [rbp+37h+var_48], rax
0x18005ef56  mov     [rbp+37h+var_60], rdi
0x18005ef5a  mov     [rbp+37h+hObject], rdi
0x18005ef5e  mov     qword ptr [rbp+37h+Luid.LowPart], rdi
0x18005ef62  mov     dword ptr [rbp+37h+pIdentifierAuthority.Value], edi
0x18005ef65  mov     word ptr [rbp+37h+pIdentifierAuthority.Value+4], 500h
0x18005ef6b  test    rbx, rbx
0x18005ef6e  jnz     short loc_18005EFA8
0x18005ef70  mov     r9d, [rbp+37h+dwLogonType]; dwLogonType
0x18005ef74  mov     r8, r12; lpszPassword
0x18005ef77  mov     [rsp+0C0h+pQuotaLimits], rdi; pQuotaLimits
0x18005ef7c  mov     rdx, r15; lpszDomain
0x18005ef7f  mov     [rsp+0C0h+pdwProfileLength], rax; pdwProfileLength
0x18005ef84  mov     rcx, r14; lpszUsername
0x18005ef87  mov     eax, [rbp+37h+arg_28]
0x18005ef8a  mov     [rsp+0C0h+ppProfileBuffer], r13; ppProfileBuffer
0x18005ef8f  mov     [rsp+0C0h+ppLogonSid], rdi; ppLogonSid
0x18005ef94  mov     [rsp+0C0h+phToken], rsi; phToken
0x18005ef99  mov     [rsp+0C0h+dwLogonProvider], eax; dwLogonProvider
0x18005ef9d  call    cs:__imp_LogonUserExW
0x18005efa3  jmp     loc_18005F222
0x18005efa8  lea     rcx, [rbp+37h+Luid]; Luid
0x18005efac  call    cs:__imp_AllocateLocallyUniqueId
0x18005efb2  test    eax, eax
0x18005efb4  jnz     short loc_18005F00D
0x18005efb6  call    cs:__imp_GetLastError
0x18005efbc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005efc3  mov     ebx, eax
0x18005efc5  jz      loc_18005F1D1
0x18005efcb  test    eax, eax
0x18005efcd  jle     short loc_18005EFD7
0x18005efcf  movzx   eax, ax
0x18005efd2  or      eax, 80070000h
0x18005efd7  lea     rcx, aAllocatelocall; "AllocateLocallyUniqueId failed\n"
0x18005efde  mov     r8d, 7B2h
0x18005efe4  mov     [rsp+0C0h+phToken], rcx
0x18005efe9  lea     r9, aTokenCacheLogo; "TOKEN_CACHE::LogonUserW"
0x18005eff0  mov     rcx, cs:g_pDebug
0x18005eff7  lea     rdx, aServercommonIn_45; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18005effe  mov     [rsp+0C0h+dwLogonProvider], eax
0x18005f002  call    cs:__imp_PuDbgPrintError
0x18005f008  jmp     loc_18005F1D1
0x18005f00d  mov     r9d, [rbp+37h+Luid.HighPart]; nSubAuthority1
0x18005f011  lea     rax, [rbp+37h+var_60]
0x18005f015  mov     [rsp+0C0h+pSid], rax; pSid
0x18005f01a  lea     rcx, [rbp+37h+pIdentifierAuthority]; pIdentifierAuthority
0x18005f01e  mov     eax, [rbp+37h+Luid.LowPart]
0x18005f021  mov     r8d, 5; nSubAuthority0
0x18005f027  mov     dword ptr [rsp+0C0h+pQuotaLimits], edi; nSubAuthority7
0x18005f02b  mov     dl, 3; nSubAuthorityCount
0x18005f02d  mov     dword ptr [rsp+0C0h+pdwProfileLength], edi; nSubAuthority6
0x18005f031  mov     dword ptr [rsp+0C0h+ppProfileBuffer], edi; nSubAuthority5
0x18005f035  mov     dword ptr [rsp+0C0h+ppLogonSid], edi; nSubAuthority4
0x18005f039  mov     dword ptr [rsp+0C0h+phToken], edi; nSubAuthority3
0x18005f03d  mov     [rsp+0C0h+dwLogonProvider], eax; nSubAuthority2
0x18005f041  call    cs:__imp_AllocateAndInitializeSid
0x18005f047  test    eax, eax
0x18005f049  jnz     short loc_18005F07E
0x18005f04b  call    cs:__imp_GetLastError
0x18005f051  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005f058  mov     ebx, eax
0x18005f05a  jz      loc_18005F1D1
0x18005f060  test    eax, eax
0x18005f062  jle     short loc_18005F06C
0x18005f064  movzx   eax, ax
0x18005f067  or      eax, 80070000h
0x18005f06c  lea     rcx, aAllocateandini; "AllocateAndInitializeSid failed\n"
0x18005f073  mov     r8d, 7C2h
0x18005f079  jmp     loc_18005EFE4
0x18005f07e  mov     edx, [rbx]
0x18005f080  mov     ecx, 40h ; '@'; uFlags
0x18005f085  inc     edx
0x18005f087  shl     rdx, 4
0x18005f08b  add     rdx, 18h; uBytes
0x18005f08f  call    cs:__imp_LocalAlloc
0x18005f095  xor     r9d, r9d
0x18005f098  mov     rdi, rax
0x18005f09b  test    rax, rax
0x18005f09e  jnz     short loc_18005F0EA
0x18005f0a0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005f0a7  lea     ebx, [rax+8]
0x18005f0aa  jz      loc_18005F1CF
0x18005f0b0  mov     rcx, cs:g_pDebug
0x18005f0b7  lea     rax, aUnableToAllocT; "Unable to alloc token groups\n"
0x18005f0be  mov     [rsp+0C0h+phToken], rax
0x18005f0c3  lea     r9, aTokenCacheLogo; "TOKEN_CACHE::LogonUserW"
0x18005f0ca  mov     r8d, 7D1h
0x18005f0d0  mov     [rsp+0C0h+dwLogonProvider], 80070008h
0x18005f0d8  lea     rdx, aServercommonIn_45; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18005f0df  call    cs:__imp_PuDbgPrintError
0x18005f0e5  jmp     loc_18005F1CF
0x18005f0ea  mov     eax, [rbx]
0x18005f0ec  inc     eax
0x18005f0ee  mov     [rdi], eax
0x18005f0f0  mov     rax, [rbp+37h+var_60]
0x18005f0f4  mov     [rdi+8], rax
0x18005f0f8  mov     eax, r9d
0x18005f0fb  mov     dword ptr [rdi+10h], 0C0000007h
0x18005f102  cmp     [rbx], r9d
0x18005f105  jbe     short loc_18005F130
0x18005f107  lea     r8d, [rax+1]
0x18005f10b  mov     edx, eax
0x18005f10d  add     rdx, rdx
0x18005f110  mov     ecx, r8d
0x18005f113  add     rcx, rcx
0x18005f116  mov     rax, [rbx+rdx*8+8]
0x18005f11b  mov     [rdi+rcx*8+8], rax
0x18005f120  mov     eax, [rbx+rdx*8+10h]
0x18005f124  mov     [rdi+rcx*8+10h], eax
0x18005f128  mov     eax, r8d
0x18005f12b  cmp     r8d, [rbx]
0x18005f12e  jb      short loc_18005F107
0x18005f130  mov     rax, [rbp+37h+var_48]
0x18005f134  mov     r8, r12
0x18005f137  mov     [rsp+0C0h+pSid], r9
0x18005f13c  mov     rdx, r15
0x18005f13f  mov     [rsp+0C0h+pQuotaLimits], rax
0x18005f144  mov     rcx, r14
0x18005f147  mov     [rsp+0C0h+pdwProfileLength], r13
0x18005f14c  lea     rax, [rbp+37h+hObject]
0x18005f150  mov     [rsp+0C0h+ppProfileBuffer], r9
0x18005f155  mov     r9d, [rbp+37h+dwLogonType]
0x18005f159  mov     [rsp+0C0h+ppLogonSid], rax
0x18005f15e  mov     eax, [rbp+37h+arg_28]
0x18005f161  mov     [rsp+0C0h+phToken], rdi
0x18005f166  mov     [rsp+0C0h+dwLogonProvider], eax
0x18005f16a  call    cs:__imp_LogonUserExExW
0x18005f170  test    eax, eax
0x18005f172  jnz     loc_18005F203
0x18005f178  call    cs:__imp_GetLastError
0x18005f17e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005f185  mov     ebx, eax
0x18005f187  jz      short loc_18005F1C6
0x18005f189  test    eax, eax
0x18005f18b  jle     short loc_18005F195
0x18005f18d  movzx   eax, ax
0x18005f190  or      eax, 80070000h
0x18005f195  lea     rcx, aLogonuserFaile; "LogonUser failed\n"
0x18005f19c  mov     r8d, 7FBh
0x18005f1a2  mov     [rsp+0C0h+phToken], rcx
0x18005f1a7  lea     r9, aTokenCacheLogo; "TOKEN_CACHE::LogonUserW"
0x18005f1ae  mov     rcx, cs:g_pDebug
0x18005f1b5  lea     rdx, aServercommonIn_45; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18005f1bc  mov     [rsp+0C0h+dwLogonProvider], eax
0x18005f1c0  call    cs:__imp_PuDbgPrintError
0x18005f1c6  mov     rcx, rdi; hMem
0x18005f1c9  call    cs:__imp_LocalFree
0x18005f1cf  xor     edi, edi
0x18005f1d1  mov     rcx, [rbp+37h+hObject]; hObject
0x18005f1d5  test    rcx, rcx
0x18005f1d8  jz      short loc_18005F1E4
0x18005f1da  call    cs:__imp_CloseHandle
0x18005f1e0  mov     [rbp+37h+hObject], rdi
0x18005f1e4  mov     rcx, [rbp+37h+var_60]; pSid
0x18005f1e8  test    rcx, rcx
0x18005f1eb  jz      short loc_18005F1F7
0x18005f1ed  call    cs:__imp_FreeSid
0x18005f1f3  mov     [rbp+37h+var_60], rdi
0x18005f1f7  mov     ecx, ebx; dwErrCode
0x18005f1f9  call    cs:__imp_SetLastError
0x18005f1ff  xor     eax, eax
0x18005f201  jmp     short loc_18005F222
0x18005f203  mov     rcx, rdi; hMem
0x18005f206  call    cs:__imp_LocalFree
0x18005f20c  mov     rcx, [rbp+37h+var_60]; pSid
0x18005f210  call    cs:__imp_FreeSid
0x18005f216  mov     rcx, [rbp+37h+hObject]
0x18005f21a  mov     eax, 1
0x18005f21f  mov     [rsi], rcx
0x18005f222  mov     rcx, [rbp+37h+var_38]
0x18005f226  xor     rcx, rsp; StackCookie
0x18005f229  call    __security_check_cookie
0x18005f22e  mov     rbx, [rsp+0C0h+arg_0]
0x18005f236  add     rsp, 90h
0x18005f23d  pop     r15
0x18005f23f  pop     r14
0x18005f241  pop     r13
0x18005f243  pop     r12
0x18005f245  pop     rdi
0x18005f246  pop     rsi
0x18005f247  pop     rbp
0x18005f248  retn
```

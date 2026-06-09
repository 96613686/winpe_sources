# FwLookupAccountSid

- ea: `0x18001ff80`
- end: `0x180020190`
- name: `FwLookupAccountSid`
- size: `528`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800045f0`
- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180004870`
- `0x18001e1d0`
- `0x18001ff80`
- `0x18002f43c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002009d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002011b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002009d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002011b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001fff5`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002010a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001fff5`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002010a`

## string_xrefs

- `0x180020018`: `FwLookupAccountSid`
- `0x180020042`: `FwLookupAccountSid`
- `0x18002008a`: `FwLookupAccountSid`
- `0x180020124`: `FwLookupAccountSid`
- `0x18002015d`: `FwLookupAccountSid`
- `0x1800200ac`: `LookupAccountSidW`
- `0x180020114`: `LookupAccountSidW`

## pseudocode

```c
__int64 __fastcall FwLookupAccountSid(PSID Sid, WCHAR **a2, WCHAR **a3)
{
  WCHAR *v3; // rdi
  WCHAR *v4; // rsi
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  DWORD LastError; // eax
  __int64 v12; // rdx
  const char *v13; // rbx
  __int64 v14; // rdx
  WCHAR *v15; // rax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-20h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-1Ch] BYREF
  WCHAR ReferencedDomainName[2]; // [rsp+48h] [rbp-18h] BYREF
  WCHAR Name[2]; // [rsp+4Ch] [rbp-14h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-10h] BYREF

  v3 = Name;
  *a2 = 0;
  v4 = ReferencedDomainName;
  *a3 = 0;
  Name[0] = 0;
  ReferencedDomainName[0] = 0;
  peUse = 0;
  cchName = 1;
  cchReferencedDomainName = 1;
  if ( !LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    LastError = GetLastError();
    if ( LastError == 122 || !LastError )
    {
      v3 = (WCHAR *)FwAlloc(2LL * cchName, v12);
      if ( v3 && (v15 = (WCHAR *)FwAlloc(2LL * cchReferencedDomainName, v14), (v4 = v15) != 0) )
      {
        v9 = 0;
        if ( LookupAccountSidLocalW(Sid, v3, &cchName, v15, &cchReferencedDomainName, &peUse) )
          goto LABEL_27;
        v13 = "LookupAccountSidW";
        LastError = GetLastError();
      }
      else
      {
        v13 = "FwAlloc";
        LastError = 8;
      }
    }
    else
    {
      v13 = "LookupAccountSidW";
    }
    v9 = FwReportErrorAsWinError("FwLookupAccountSid", v13, LastError);
    if ( (v9 & 0x80000000) == 0 )
      return v9;
    goto LABEL_22;
  }
  v8 = FwStringCopy(Name);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = FwStringCopy(ReferencedDomainName);
    v9 = v10;
    if ( v10 < 0 )
    {
      FwReportReturnError("FwLookupAccountSid", (unsigned int)v10);
      v3 = Name;
      v4 = ReferencedDomainName;
      goto LABEL_22;
    }
    v3 = Name;
    if ( !Name )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v4 = ReferencedDomainName;
    if ( !ReferencedDomainName )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !Name || !ReferencedDomainName )
    {
      v9 = -2147418113;
      FwReportReturnError("FwLookupAccountSid", 2147549183LL);
      goto LABEL_22;
    }
LABEL_27:
    *a2 = v3;
    *a3 = v4;
    return v9;
  }
  FwReportReturnError("FwLookupAccountSid", (unsigned int)v8);
  v3 = Name;
LABEL_22:
  if ( v4 != ReferencedDomainName )
    FwFree(v4);
  if ( v3 != Name )
    FwFree(v3);
  return (unsigned int)FwReportReturnError("FwLookupAccountSid", v9);
}

```

## disassembly

```asm
0x18001ff80  push    rbp
0x18001ff82  push    rbx
0x18001ff83  push    rsi
0x18001ff84  push    rdi
0x18001ff85  push    r12
0x18001ff87  push    r14
0x18001ff89  push    r15
0x18001ff8b  mov     rbp, rsp
0x18001ff8e  sub     rsp, 60h
0x18001ff92  mov     rax, cs:__security_cookie
0x18001ff99  xor     rax, rsp
0x18001ff9c  mov     [rbp+var_8], rax
0x18001ffa0  xor     eax, eax
0x18001ffa2  lea     rdi, [rbp+Name]
0x18001ffa6  mov     [rdx], rax
0x18001ffa9  lea     rsi, [rbp+ReferencedDomainName]
0x18001ffad  mov     [r8], rax
0x18001ffb0  lea     r9, [rbp+ReferencedDomainName]; ReferencedDomainName
0x18001ffb4  mov     [rbp+Name], ax
0x18001ffb8  mov     r15, r8
0x18001ffbb  mov     [rbp+ReferencedDomainName], ax
0x18001ffbf  lea     r8, [rbp+cchName]; cchName
0x18001ffc3  mov     [rbp+var_10], eax
0x18001ffc6  mov     r14, rdx
0x18001ffc9  mov     eax, 1
0x18001ffce  mov     [rbp+var_30], rdi
0x18001ffd2  mov     [rbp+cchName], eax
0x18001ffd5  lea     rdx, [rbp+Name]; Name
0x18001ffd9  mov     [rbp+var_20], eax
0x18001ffdc  mov     r12, rcx
0x18001ffdf  lea     rax, [rbp+var_10]
0x18001ffe3  mov     [rbp+var_28], rsi
0x18001ffe7  mov     [rsp+60h+peUse], rax; peUse
0x18001ffec  lea     rax, [rbp+var_20]
0x18001fff0  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001fff5  call    cs:__imp_LookupAccountSidLocalW
0x18001fffb  test    eax, eax
0x18001fffd  jz      loc_18002009D
0x180020003  lea     rdx, [rbp+var_30]
0x180020007  lea     rcx, [rbp+Name]; Src
0x18002000b  call    FwStringCopy
0x180020010  mov     ebx, eax
0x180020012  test    eax, eax
0x180020014  jns     short loc_18002002D
0x180020016  mov     edx, eax
0x180020018  lea     rcx, aFwlookupaccoun_0; "FwLookupAccountSid"
0x18002001f  call    FwReportReturnError
0x180020024  mov     rdi, [rbp+var_30]
0x180020028  jmp     loc_180020139
0x18002002d  lea     rdx, [rbp+var_28]
0x180020031  lea     rcx, [rbp+ReferencedDomainName]; Src
0x180020035  call    FwStringCopy
0x18002003a  mov     ebx, eax
0x18002003c  test    eax, eax
0x18002003e  jns     short loc_18002005B
0x180020040  mov     edx, eax
0x180020042  lea     rcx, aFwlookupaccoun_0; "FwLookupAccountSid"
0x180020049  call    FwReportReturnError
0x18002004e  mov     rdi, [rbp+var_30]
0x180020052  mov     rsi, [rbp+var_28]
0x180020056  jmp     loc_180020139
0x18002005b  mov     rdi, [rbp+var_30]
0x18002005f  test    rdi, rdi
0x180020062  jnz     short loc_180020069
0x180020064  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "tmpUserName")
0x180020069  mov     rsi, [rbp+var_28]
0x18002006d  test    rsi, rsi
0x180020070  jnz     short loc_180020077
0x180020072  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "tmpDomainName")
0x180020077  test    rdi, rdi
0x18002007a  jz      short loc_180020085
0x18002007c  test    rsi, rsi
0x18002007f  jnz     loc_18002016D
0x180020085  mov     ebx, 8000FFFFh
0x18002008a  lea     rcx, aFwlookupaccoun_0; "FwLookupAccountSid"
0x180020091  mov     edx, ebx
0x180020093  call    FwReportReturnError
0x180020098  jmp     loc_180020139
0x18002009d  call    cs:__imp_GetLastError
0x1800200a3  cmp     eax, 7Ah ; 'z'
0x1800200a6  jz      short loc_1800200B5
0x1800200a8  test    eax, eax
0x1800200aa  jz      short loc_1800200B5
0x1800200ac  lea     rbx, aLookupaccounts_0; "LookupAccountSidW"
0x1800200b3  jmp     short loc_180020121
0x1800200b5  mov     ecx, [rbp+cchName]
0x1800200b8  add     rcx, rcx
0x1800200bb  call    FwAlloc
0x1800200c0  mov     rdi, rax
0x1800200c3  test    rax, rax
0x1800200c6  jnz     short loc_1800200D6
0x1800200c8  lea     rbx, aFwalloc_0; "FwAlloc"
0x1800200cf  mov     eax, 8
0x1800200d4  jmp     short loc_180020121
0x1800200d6  mov     ecx, [rbp+var_20]
0x1800200d9  add     rcx, rcx
0x1800200dc  call    FwAlloc
0x1800200e1  mov     rsi, rax
0x1800200e4  test    rax, rax
0x1800200e7  jz      short loc_1800200C8
0x1800200e9  lea     rax, [rbp+var_10]
0x1800200ed  mov     r9, rsi; ReferencedDomainName
0x1800200f0  mov     [rsp+60h+peUse], rax; peUse
0x1800200f5  lea     r8, [rbp+cchName]; cchName
0x1800200f9  lea     rax, [rbp+var_20]
0x1800200fd  mov     rdx, rdi; Name
0x180020100  mov     rcx, r12; Sid
0x180020103  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180020108  xor     ebx, ebx
0x18002010a  call    cs:__imp_LookupAccountSidLocalW
0x180020110  test    eax, eax
0x180020112  jnz     short loc_18002016D
0x180020114  lea     rbx, aLookupaccounts_0; "LookupAccountSidW"
0x18002011b  call    cs:__imp_GetLastError
0x180020121  mov     r8d, eax
0x180020124  lea     rcx, aFwlookupaccoun_0; "FwLookupAccountSid"
0x18002012b  mov     rdx, rbx
0x18002012e  call    FwReportErrorAsWinError
0x180020133  mov     ebx, eax
0x180020135  test    eax, eax
0x180020137  jns     short loc_180020173
0x180020139  lea     rax, [rbp+ReferencedDomainName]
0x18002013d  cmp     rsi, rax
0x180020140  jz      short loc_18002014A
0x180020142  mov     rcx, rsi
0x180020145  call    FwFree
0x18002014a  lea     rax, [rbp+Name]
0x18002014e  cmp     rdi, rax
0x180020151  jz      short loc_18002015B
0x180020153  mov     rcx, rdi
0x180020156  call    FwFree
0x18002015b  mov     edx, ebx
0x18002015d  lea     rcx, aFwlookupaccoun_0; "FwLookupAccountSid"
0x180020164  call    FwReportReturnError
0x180020169  mov     ebx, eax
0x18002016b  jmp     short loc_180020173
0x18002016d  mov     [r14], rdi
0x180020170  mov     [r15], rsi
0x180020173  mov     eax, ebx
0x180020175  mov     rcx, [rbp+var_8]
0x180020179  xor     rcx, rsp; StackCookie
0x18002017c  call    __security_check_cookie
0x180020181  add     rsp, 60h
0x180020185  pop     r15
0x180020187  pop     r14
0x180020189  pop     r12
0x18002018b  pop     rdi
0x18002018c  pop     rsi
0x18002018d  pop     rbx
0x18002018e  pop     rbp
0x18002018f  retn
```

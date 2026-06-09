# LA_PROTOCOL::GetIdentitySid(ushort const *,void * *)

- ea: `0x18001bdd0`
- end: `0x18001c056`
- name: `?GetIdentitySid@LA_PROTOCOL@@AEAAJPEBGPEAPEAX@Z`
- size: `646`
- prototype: `int(LA_PROTOCOL *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001cc3c`

## callees

- `0x18001bdd0`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bedb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bedb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bf07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bf07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c018`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c018`
- `iisutil!PuDbgPrintError` at `0x18001bed0`
- `iisutil!PuDbgPrintError` at `0x18001bed0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001c02a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001c02a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001bf59`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001bf59`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001be3d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001be3d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18001be85`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18001bfc0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18001be85`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18001bfc0`

## string_xrefs

- `0x18001bec9`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\la_protocol.cxx`
- `0x18001bec2`: `LA_PROTOCOL::GetIdentitySid`
- `0x18001bf35`: `Failed to allocate buffer for identity SID\n`
- `0x18001bfe5`: `Error getting the account SID for user account\n`

## pseudocode

```c
__int64 __fastcall LA_PROTOCOL::GetIdentitySid(LA_PROTOCOL *this, const unsigned __int16 *a2, void **a3)
{
  unsigned int v5; // ebx
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  DWORD cchReferencedDomainName; // [rsp+30h] [rbp-50h] BYREF
  DWORD cbSid; // [rsp+34h] [rbp-4Ch] BYREF
  PSID Sid; // [rsp+38h] [rbp-48h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v15[4]; // [rsp+48h] [rbp-38h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+68h] [rbp-18h]
  int v17; // [rsp+70h] [rbp-10h]
  __int16 v18; // [rsp+74h] [rbp-Ch]

  v15[0] = 0;
  v17 = 32;
  ReferencedDomainName = (LPWSTR)v15;
  v18 = 256;
  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(a2, &Sid) )
  {
    v5 = 0;
    *a3 = Sid;
    Sid = 0;
    goto LABEL_28;
  }
  cbSid = 0;
  cchReferencedDomainName = 0;
  if ( LookupAccountNameLocalW(a2, 0, &cbSid, 0, &cchReferencedDomainName, &peUse) )
  {
    v5 = -2147467259;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\la_protocol.cxx",
        1631,
        "LA_PROTOCOL::GetIdentitySid",
        -2147467259,
        "Did not error when we expected to\n");
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 == -2147024774 )
    {
      Sid = LocalAlloc(0x40u, cbSid);
      if ( !Sid )
      {
        v7 = GetLastError();
        v5 = v7;
        if ( v7 > 0 )
          v5 = (unsigned __int16)v7 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\la_protocol.cxx",
            1652,
            "LA_PROTOCOL::GetIdentitySid",
            v5,
            "Failed to allocate buffer for identity SID\n");
        goto LABEL_26;
      }
      if ( !BUFFER::Resize((BUFFER *)v15, 2 * cchReferencedDomainName) )
      {
        v8 = GetLastError();
        v5 = v8;
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\la_protocol.cxx",
            1664,
            "LA_PROTOCOL::GetIdentitySid",
            v5,
            "Failed to resize the buffer to the correct size\n");
        goto LABEL_26;
      }
      v5 = 0;
      if ( !LookupAccountNameLocalW(a2, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      {
        v9 = GetLastError();
        v5 = v9;
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\la_protocol.cxx",
            1685,
            "LA_PROTOCOL::GetIdentitySid",
            v5,
            "Error getting the account SID for user account\n");
        goto LABEL_26;
      }
    }
    *a3 = Sid;
    Sid = 0;
  }
LABEL_26:
  if ( Sid )
  {
    LocalFree(Sid);
    Sid = 0;
  }
LABEL_28:
  BUFFER::~BUFFER((BUFFER *)v15);
  return v5;
}

```

## disassembly

```asm
0x18001bdd0  mov     [rsp-18h+arg_0], rbx
0x18001bdd5  mov     [rsp-18h+arg_18], rsi
0x18001bdda  push    rbp
0x18001bddb  push    rdi
0x18001bddc  push    r15
0x18001bdde  mov     rbp, rsp
0x18001bde1  sub     rsp, 80h
0x18001bde8  mov     rax, cs:__security_cookie
0x18001bdef  xor     rax, rsp
0x18001bdf2  mov     [rbp+var_8], rax
0x18001bdf6  mov     rsi, rdx
0x18001bdf9  mov     [rbp+var_38], 0
0x18001be01  lea     rax, [rbp+var_38]
0x18001be05  mov     [rbp+var_10], 20h ; ' '
0x18001be0c  mov     rcx, rsi; StringSid
0x18001be0f  mov     [rbp+ReferencedDomainName], rax
0x18001be13  lea     rdx, [rbp+Sid]; Sid
0x18001be17  mov     [rbp+var_C], 100h
0x18001be1d  mov     rdi, r8
0x18001be20  mov     [rbp+cbSid], 0
0x18001be27  mov     [rbp+var_50], 0
0x18001be2e  mov     [rbp+var_40], 0
0x18001be35  mov     [rbp+Sid], 0
0x18001be3d  call    cs:__imp_ConvertStringSidToSidW
0x18001be43  test    eax, eax
0x18001be45  jz      short loc_18001BE59
0x18001be47  mov     rax, [rbp+Sid]
0x18001be4b  xor     ebx, ebx
0x18001be4d  mov     [rdi], rax
0x18001be50  mov     [rbp+Sid], rbx
0x18001be54  jmp     loc_18001C026
0x18001be59  lea     rax, [rbp+var_40]
0x18001be5d  mov     [rbp+cbSid], 0
0x18001be64  mov     [rsp+80h+peUse], rax; peUse
0x18001be69  lea     r8, [rbp+cbSid]; cbSid
0x18001be6d  lea     rax, [rbp+var_50]
0x18001be71  mov     [rbp+var_50], 0
0x18001be78  xor     r9d, r9d; ReferencedDomainName
0x18001be7b  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001be80  xor     edx, edx; Sid
0x18001be82  mov     rcx, rsi; lpAccountName
0x18001be85  call    cs:__imp_LookupAccountNameLocalW
0x18001be8b  test    eax, eax
0x18001be8d  jz      short loc_18001BEDB
0x18001be8f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001be96  mov     ebx, 80004005h
0x18001be9b  jz      loc_18001C00F
0x18001bea1  lea     rax, aDidNotErrorWhe; "Did not error when we expected to\n"
0x18001bea8  mov     r8d, 65Fh
0x18001beae  mov     [rsp+80h+peUse], rax
0x18001beb3  mov     dword ptr [rsp+80h+cchReferencedDomainName], 80004005h
0x18001bebb  mov     rcx, cs:g_pDebug
0x18001bec2  lea     r9, aLaProtocolGeti; "LA_PROTOCOL::GetIdentitySid"
0x18001bec9  lea     rdx, aServercommonIn_37; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001bed0  call    cs:__imp_PuDbgPrintError
0x18001bed6  jmp     loc_18001C00F
0x18001bedb  call    cs:__imp_GetLastError
0x18001bee1  mov     ebx, eax
0x18001bee3  mov     r15d, 80070000h
0x18001bee9  test    eax, eax
0x18001beeb  jle     short loc_18001BEF3
0x18001beed  movzx   ebx, ax
0x18001bef0  or      ebx, r15d
0x18001bef3  cmp     ebx, 8007007Ah
0x18001bef9  jnz     loc_18001C000
0x18001beff  mov     edx, [rbp+cbSid]; uBytes
0x18001bf02  mov     ecx, 40h ; '@'; uFlags
0x18001bf07  call    cs:__imp_LocalAlloc
0x18001bf0d  mov     [rbp+Sid], rax
0x18001bf11  test    rax, rax
0x18001bf14  jnz     short loc_18001BF50
0x18001bf16  call    cs:__imp_GetLastError
0x18001bf1c  mov     ebx, eax
0x18001bf1e  test    eax, eax
0x18001bf20  jle     short loc_18001BF28
0x18001bf22  movzx   ebx, ax
0x18001bf25  or      ebx, r15d
0x18001bf28  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001bf2f  jz      loc_18001C00F
0x18001bf35  lea     rax, aFailedToAlloca_4; "Failed to allocate buffer for identity "...
0x18001bf3c  mov     r8d, 674h
0x18001bf42  mov     [rsp+80h+peUse], rax
0x18001bf47  mov     dword ptr [rsp+80h+cchReferencedDomainName], ebx
0x18001bf4b  jmp     loc_18001BEBB
0x18001bf50  mov     edx, [rbp+var_50]
0x18001bf53  lea     rcx, [rbp+var_38]
0x18001bf57  add     edx, edx
0x18001bf59  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001bf5f  test    al, al
0x18001bf61  jnz     short loc_18001BF9D
0x18001bf63  call    cs:__imp_GetLastError
0x18001bf69  mov     ebx, eax
0x18001bf6b  test    eax, eax
0x18001bf6d  jle     short loc_18001BF75
0x18001bf6f  movzx   ebx, ax
0x18001bf72  or      ebx, r15d
0x18001bf75  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001bf7c  jz      loc_18001C00F
0x18001bf82  lea     rax, aFailedToResize; "Failed to resize the buffer to the corr"...
0x18001bf89  mov     r8d, 680h
0x18001bf8f  mov     [rsp+80h+peUse], rax
0x18001bf94  mov     dword ptr [rsp+80h+cchReferencedDomainName], ebx
0x18001bf98  jmp     loc_18001BEBB
0x18001bf9d  mov     r9, [rbp+ReferencedDomainName]; ReferencedDomainName
0x18001bfa1  lea     rax, [rbp+var_40]
0x18001bfa5  mov     rdx, [rbp+Sid]; Sid
0x18001bfa9  lea     r8, [rbp+cbSid]; cbSid
0x18001bfad  mov     [rsp+80h+peUse], rax; peUse
0x18001bfb2  mov     rcx, rsi; lpAccountName
0x18001bfb5  lea     rax, [rbp+var_50]
0x18001bfb9  xor     ebx, ebx
0x18001bfbb  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001bfc0  call    cs:__imp_LookupAccountNameLocalW
0x18001bfc6  test    eax, eax
0x18001bfc8  jnz     short loc_18001C000
0x18001bfca  call    cs:__imp_GetLastError
0x18001bfd0  mov     ebx, eax
0x18001bfd2  test    eax, eax
0x18001bfd4  jle     short loc_18001BFDC
0x18001bfd6  movzx   ebx, ax
0x18001bfd9  or      ebx, r15d
0x18001bfdc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001bfe3  jz      short loc_18001C00F
0x18001bfe5  lea     rax, aErrorGettingTh_1; "Error getting the account SID for user "...
0x18001bfec  mov     r8d, 695h
0x18001bff2  mov     [rsp+80h+peUse], rax
0x18001bff7  mov     dword ptr [rsp+80h+cchReferencedDomainName], ebx
0x18001bffb  jmp     loc_18001BEBB
0x18001c000  mov     rax, [rbp+Sid]
0x18001c004  mov     [rdi], rax
0x18001c007  mov     [rbp+Sid], 0
0x18001c00f  mov     rcx, [rbp+Sid]; hMem
0x18001c013  test    rcx, rcx
0x18001c016  jz      short loc_18001C026
0x18001c018  call    cs:__imp_LocalFree
0x18001c01e  mov     [rbp+Sid], 0
0x18001c026  lea     rcx, [rbp+var_38]
0x18001c02a  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001c030  mov     eax, ebx
0x18001c032  mov     rcx, [rbp+var_8]
0x18001c036  xor     rcx, rsp; StackCookie
0x18001c039  call    __security_check_cookie
0x18001c03e  lea     r11, [rsp+80h+var_s0]
0x18001c046  mov     rbx, [r11+20h]
0x18001c04a  mov     rsi, [r11+38h]
0x18001c04e  mov     rsp, r11
0x18001c051  pop     r15
0x18001c053  pop     rdi
0x18001c054  pop     rbp
0x18001c055  retn
```

# LOGON_USER_CONTEXT::ProcessCustomAuthentication(long,int *)

- ea: `0x18001c998`
- end: `0x18001cce5`
- name: `?ProcessCustomAuthentication@LOGON_USER_CONTEXT@@AEAAJJPEAH@Z`
- size: `845`
- prototype: `__int64 __fastcall(LOGON_USER_CONTEXT *__hidden this, int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ccec`

## callees

- `0x180002504`
- `0x18001a9ec`
- `0x18001c2fc`
- `0x18001c998`
- `0x18001d8a0`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001ca6a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001ca6a`
- `iisutil!PuDbgPrint` at `0x18001ca41`
- `iisutil!PuDbgPrint` at `0x18001caaa`
- `iisutil!PuDbgPrint` at `0x18001cb24`
- `iisutil!PuDbgPrint` at `0x18001cb76`
- `iisutil!PuDbgPrint` at `0x18001ca41`
- `iisutil!PuDbgPrint` at `0x18001caaa`
- `iisutil!PuDbgPrint` at `0x18001cb24`
- `iisutil!PuDbgPrint` at `0x18001cb76`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001cca9`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001cca9`

## string_xrefs

- `0x18001cc06`: `An error occurred during the authentication process.`
- `0x18001ca2f`: `LookupCredentialsCache() failed. hr=0x%x\n`
- `0x18001cb18`: `Custom authentication attempt failed with 0x%x.\n`

## pseudocode

```c
__int64 __fastcall LOGON_USER_CONTEXT::ProcessCustomAuthentication(LOGON_USER_CONTEXT *this, int a2, int *a3)
{
  __int64 v3; // rax
  const unsigned __int16 **v4; // rsi
  unsigned int v5; // r12d
  unsigned int v6; // edi
  unsigned int v10; // r13d
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // r8
  int v15; // eax
  const wchar_t *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rbx
  CEtwTracer *v19; // rax
  CREDENTIALS_CACHE_ENTRY *v21; // [rsp+30h] [rbp-39h] BYREF
  __int16 v22; // [rsp+40h] [rbp-29h] BYREF
  __int128 v23; // [rsp+42h] [rbp-27h]
  __int128 v24; // [rsp+52h] [rbp-17h]
  _BYTE v25[22]; // [rsp+62h] [rbp-7h]
  int v26; // [rsp+78h] [rbp+Fh]
  int v27; // [rsp+7Ch] [rbp+13h]

  v3 = *((_QWORD *)this + 25);
  v4 = 0;
  v5 = *((_DWORD *)this + 48);
  v6 = 0;
  v21 = 0;
  v10 = *(_DWORD *)(v3 + 8);
  *a3 = 0;
  if ( *((_DWORD *)this + 54) )
    goto LABEL_19;
  *((_DWORD *)this + 53) = 1;
  v11 = LOGON_USER_CONTEXT::LookupCredentialsCache(this, &v21);
  v6 = v11;
  if ( v11 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
        657,
        "LOGON_USER_CONTEXT::ProcessCustomAuthentication",
        "LookupCredentialsCache() failed. hr=0x%x\n",
        v11);
    v6 = 0;
  }
  v4 = (const unsigned __int16 **)v21;
  if ( v21 )
  {
    *((_DWORD *)this + 54) = 1;
    v12 = STRU::Copy((LOGON_USER_CONTEXT *)((char *)this + 136), v4[48]);
    v6 = v12;
    if ( v12 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
          681,
          "LOGON_USER_CONTEXT::ProcessCustomAuthentication",
          "SetCanonicalUserName() failed. hr = 0x%x\n",
          v12);
      v6 = 0;
    }
  }
  if ( *((_DWORD *)this + 54) )
    goto LABEL_37;
  if ( !LOGON_USER_CONTEXT::_fAuthenticateUserAsynchronously )
  {
    *a3 = 0;
    v13 = LOGON_USER_CONTEXT::SynchronousAuthenticateUser(this);
    v6 = v13;
    if ( v13 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v14 = 727;
LABEL_17:
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
          v14,
          "LOGON_USER_CONTEXT::ProcessCustomAuthentication",
          "Custom authentication attempt failed with 0x%x.\r\n",
          v13);
        goto LABEL_37;
      }
      goto LABEL_37;
    }
LABEL_19:
    if ( !*((_DWORD *)this + 54) )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
          745,
          "LOGON_USER_CONTEXT::ProcessCustomAuthentication",
          "Failed to authenticate user.\r\n");
      v15 = *((_DWORD *)this + 126);
      if ( a2 >= 0 )
      {
        if ( !v15 )
        {
          if ( v5 < v10 )
          {
            *((_DWORD *)this + 126) = 41;
            v16 = L"An error occurred during the authentication process.";
          }
          else
          {
            *((_DWORD *)this + 126) = 35;
            v16 = L"User failed to authenticate.";
          }
          *((_QWORD *)this + 64) = v16;
        }
        v6 = -2146893042;
        v17 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        if ( *(_DWORD *)(v17 + 8) && (*(_BYTE *)(v17 + 40) & 8) != 0 && *(_DWORD *)(v17 + 44) >= 3u )
        {
          v18 = *((_QWORD *)this + 1) + 1272LL;
          v19 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          v22 = 64;
          v23 = 0;
          WORD2(v23) = 1;
          *(_OWORD *)v25 = 0;
          *(_DWORD *)&v25[10] = 1703936;
          v27 = 0;
          BYTE2(v23) = 15;
          v24 = 0;
          *(_QWORD *)((char *)&v24 + 6) = &`FtpAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
          *(_QWORD *)&v25[14] = v18;
          v26 = 16;
          CEtwTracer::EtwTraceEvent(v19, (struct _EVENT_TRACE_HEADER *)&v22);
        }
      }
      else
      {
        v6 = a2;
        if ( !v15 )
        {
          *((_DWORD *)this + 126) = 35;
          *((_QWORD *)this + 64) = L"User failed to authenticate.";
        }
      }
    }
    goto LABEL_37;
  }
  if ( v5 >= v10 )
    goto LABEL_19;
  *((_DWORD *)this + 120) = 102;
  v13 = LOGON_USER_CONTEXT::AsyncHandleCustomAuthenticationLogon(this, a3);
  v6 = v13;
  if ( v13 < 0 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_37;
    v14 = 705;
    goto LABEL_17;
  }
  if ( !*a3 )
    goto LABEL_19;
LABEL_37:
  if ( v4 )
    CREDENTIALS_CACHE_ENTRY::DereferenceCacheEntry((CREDENTIALS_CACHE_ENTRY *)v4);
  return v6;
}

```

## disassembly

```asm
0x18001c998  mov     [rsp-8+arg_8], rbx
0x18001c99d  push    rbp
0x18001c99e  push    rsi
0x18001c99f  push    rdi
0x18001c9a0  push    r12
0x18001c9a2  push    r13
0x18001c9a4  push    r14
0x18001c9a6  push    r15
0x18001c9a8  lea     rbp, [rsp-27h]
0x18001c9ad  sub     rsp, 90h
0x18001c9b4  mov     rax, cs:__security_cookie
0x18001c9bb  xor     rax, rsp
0x18001c9be  mov     [rbp+57h+var_40], rax
0x18001c9c2  mov     rax, [rcx+0C8h]
0x18001c9c9  xor     esi, esi
0x18001c9cb  mov     r12d, [rcx+0C0h]
0x18001c9d2  xor     edi, edi
0x18001c9d4  mov     r14, r8
0x18001c9d7  mov     [rbp+57h+var_90], rsi
0x18001c9db  mov     r15d, edx
0x18001c9de  mov     rbx, rcx
0x18001c9e1  mov     r13d, [rax+8]
0x18001c9e5  mov     [r8], esi
0x18001c9e8  cmp     [rcx+0D8h], esi
0x18001c9ee  jnz     loc_18001CB39
0x18001c9f4  lea     rdx, [rbp+57h+var_90]; struct CREDENTIALS_CACHE_ENTRY **
0x18001c9f8  mov     dword ptr [rcx+0D4h], 1
0x18001ca02  call    ?LookupCredentialsCache@LOGON_USER_CONTEXT@@AEAAJPEAPEAVCREDENTIALS_CACHE_ENTRY@@@Z; LOGON_USER_CONTEXT::LookupCredentialsCache(CREDENTIALS_CACHE_ENTRY * *)
0x18001ca07  mov     edi, eax
0x18001ca09  test    eax, eax
0x18001ca0b  jns     short loc_18001CA49
0x18001ca0d  test    byte ptr cs:g_dwDebugFlags, 3
0x18001ca14  jz      short loc_18001CA47
0x18001ca16  mov     rcx, cs:g_pDebug
0x18001ca1d  lea     r9, aLogonUserConte_8; "LOGON_USER_CONTEXT::ProcessCustomAuthen"...
0x18001ca24  mov     [rsp+0C0h+var_98], eax
0x18001ca28  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001ca2f  lea     rax, aLookupcredenti; "LookupCredentialsCache() failed. hr=0x%"...
0x18001ca36  mov     r8d, 291h
0x18001ca3c  mov     [rsp+0C0h+var_A0], rax
0x18001ca41  call    cs:__imp_PuDbgPrint
0x18001ca47  xor     edi, edi
0x18001ca49  mov     rsi, [rbp+57h+var_90]
0x18001ca4d  test    rsi, rsi
0x18001ca50  jz      short loc_18001CAB2
0x18001ca52  mov     dword ptr [rbx+0D8h], 1
0x18001ca5c  lea     rcx, [rbx+88h]
0x18001ca63  mov     rdx, [rsi+180h]
0x18001ca6a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001ca70  mov     edi, eax
0x18001ca72  test    eax, eax
0x18001ca74  jns     short loc_18001CAB2
0x18001ca76  test    byte ptr cs:g_dwDebugFlags, 3
0x18001ca7d  jz      short loc_18001CAB0
0x18001ca7f  mov     rcx, cs:g_pDebug
0x18001ca86  lea     r9, aLogonUserConte_8; "LOGON_USER_CONTEXT::ProcessCustomAuthen"...
0x18001ca8d  mov     [rsp+0C0h+var_98], eax
0x18001ca91  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001ca98  lea     rax, aSetcanonicalus; "SetCanonicalUserName() failed. hr = 0x%"...
0x18001ca9f  mov     r8d, 2A9h
0x18001caa5  mov     [rsp+0C0h+var_A0], rax
0x18001caaa  call    cs:__imp_PuDbgPrint
0x18001cab0  xor     edi, edi
0x18001cab2  cmp     dword ptr [rbx+0D8h], 0
0x18001cab9  jnz     loc_18001CCAF
0x18001cabf  cmp     cs:?_fAuthenticateUserAsynchronously@LOGON_USER_CONTEXT@@0HA, 0; int LOGON_USER_CONTEXT::_fAuthenticateUserAsynchronously
0x18001cac6  jz      loc_18001CBAF
0x18001cacc  cmp     r12d, r13d
0x18001cacf  jnb     short loc_18001CB39
0x18001cad1  mov     rdx, r14; int *
0x18001cad4  mov     dword ptr [rbx+1E0h], 66h ; 'f'
0x18001cade  mov     rcx, rbx; this
0x18001cae1  call    ?AsyncHandleCustomAuthenticationLogon@LOGON_USER_CONTEXT@@AEAAJPEAH@Z; LOGON_USER_CONTEXT::AsyncHandleCustomAuthenticationLogon(int *)
0x18001cae6  mov     edi, eax
0x18001cae8  test    eax, eax
0x18001caea  jns     short loc_18001CB2F
0x18001caec  test    byte ptr cs:g_dwDebugFlags, 3
0x18001caf3  jz      loc_18001CCAF
0x18001caf9  mov     r8d, 2C1h
0x18001caff  mov     rcx, cs:g_pDebug
0x18001cb06  lea     r9, aLogonUserConte_8; "LOGON_USER_CONTEXT::ProcessCustomAuthen"...
0x18001cb0d  mov     [rsp+0C0h+var_98], eax
0x18001cb11  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001cb18  lea     rax, aCustomAuthenti_0; "Custom authentication attempt failed wi"...
0x18001cb1f  mov     [rsp+0C0h+var_A0], rax
0x18001cb24  call    cs:__imp_PuDbgPrint
0x18001cb2a  jmp     loc_18001CCAF
0x18001cb2f  cmp     dword ptr [r14], 0
0x18001cb33  jnz     loc_18001CCAF
0x18001cb39  cmp     dword ptr [rbx+0D8h], 0
0x18001cb40  jnz     loc_18001CCAF
0x18001cb46  test    byte ptr cs:g_dwDebugFlags, 3
0x18001cb4d  jz      short loc_18001CB7C
0x18001cb4f  mov     rcx, cs:g_pDebug
0x18001cb56  lea     rax, aFailedToAuthen; "Failed to authenticate user.\r\n"
0x18001cb5d  lea     r9, aLogonUserConte_8; "LOGON_USER_CONTEXT::ProcessCustomAuthen"...
0x18001cb64  mov     [rsp+0C0h+var_A0], rax
0x18001cb69  mov     r8d, 2E9h
0x18001cb6f  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001cb76  call    cs:__imp_PuDbgPrint
0x18001cb7c  mov     eax, [rbx+1F8h]
0x18001cb82  test    r15d, r15d
0x18001cb85  jns     short loc_18001CBE0
0x18001cb87  mov     edi, r15d
0x18001cb8a  test    eax, eax
0x18001cb8c  jnz     loc_18001CCAF
0x18001cb92  lea     rax, aUserFailedToAu; "User failed to authenticate."
0x18001cb99  mov     dword ptr [rbx+1F8h], 23h ; '#'
0x18001cba3  mov     [rbx+200h], rax
0x18001cbaa  jmp     loc_18001CCAF
0x18001cbaf  mov     rcx, rbx; this
0x18001cbb2  mov     dword ptr [r14], 0
0x18001cbb9  call    ?SynchronousAuthenticateUser@LOGON_USER_CONTEXT@@AEAAJXZ; LOGON_USER_CONTEXT::SynchronousAuthenticateUser(void)
0x18001cbbe  mov     edi, eax
0x18001cbc0  test    eax, eax
0x18001cbc2  jns     loc_18001CB39
0x18001cbc8  test    byte ptr cs:g_dwDebugFlags, 3
0x18001cbcf  jz      loc_18001CCAF
0x18001cbd5  mov     r8d, 2D7h
0x18001cbdb  jmp     loc_18001CAFF
0x18001cbe0  test    eax, eax
0x18001cbe2  jnz     short loc_18001CC14
0x18001cbe4  cmp     r12d, r13d
0x18001cbe7  jb      short loc_18001CBFC
0x18001cbe9  mov     dword ptr [rbx+1F8h], 23h ; '#'
0x18001cbf3  lea     rax, aUserFailedToAu; "User failed to authenticate."
0x18001cbfa  jmp     short loc_18001CC0D
0x18001cbfc  mov     dword ptr [rbx+1F8h], 29h ; ')'
0x18001cc06  lea     rax, aAnErrorOccurre; "An error occurred during the authentica"...
0x18001cc0d  mov     [rbx+200h], rax
0x18001cc14  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001cc1b  mov     edi, 8009030Eh
0x18001cc20  mov     rax, [rcx]
0x18001cc23  mov     rax, [rax+20h]
0x18001cc27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc2c  cmp     dword ptr [rax+8], 0
0x18001cc30  jz      short loc_18001CCAF
0x18001cc32  test    byte ptr [rax+28h], 8
0x18001cc36  jz      short loc_18001CCAF
0x18001cc38  cmp     dword ptr [rax+2Ch], 3
0x18001cc3c  jb      short loc_18001CCAF
0x18001cc3e  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001cc45  mov     rbx, [rbx+8]
0x18001cc49  add     rbx, 4F8h
0x18001cc50  mov     rax, [rcx]
0x18001cc53  mov     rax, [rax+20h]
0x18001cc57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc5c  xorps   xmm0, xmm0
0x18001cc5f  lea     rdx, [rbp+57h+var_80]
0x18001cc63  mov     ecx, 40h ; '@'
0x18001cc68  mov     [rbp+57h+var_80], cx
0x18001cc6c  mov     ecx, 1
0x18001cc71  movups  [rbp+57h+var_7E], xmm0
0x18001cc75  mov     word ptr [rbp+57h+var_7E+4], cx
0x18001cc79  lea     rcx, ?AreaGuid@?1??GetAreaGuid@FtpAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001cc80  movups  xmmword ptr [rbp+57h+var_5E], xmm0
0x18001cc84  mov     dword ptr [rbp+57h+var_5E+0Ah], 1A0000h
0x18001cc8b  movups  xmmword ptr [rbp+57h+var_5E+0Eh], xmm0
0x18001cc8f  mov     byte ptr [rbp+57h+var_7E+2], 0Fh
0x18001cc93  movups  [rbp+57h+var_6E], xmm0
0x18001cc97  mov     qword ptr [rbp+57h+var_6E+6], rcx
0x18001cc9b  mov     rcx, rax
0x18001cc9e  mov     qword ptr [rbp+57h+var_5E+0Eh], rbx
0x18001cca2  mov     [rbp+57h+var_48], 10h
0x18001cca9  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001ccaf  test    rsi, rsi
0x18001ccb2  jz      short loc_18001CCBC
0x18001ccb4  mov     rcx, rsi; this
0x18001ccb7  call    ?DereferenceCacheEntry@CREDENTIALS_CACHE_ENTRY@@QEAAXXZ; CREDENTIALS_CACHE_ENTRY::DereferenceCacheEntry(void)
0x18001ccbc  mov     eax, edi
0x18001ccbe  mov     rcx, [rbp+57h+var_40]
0x18001ccc2  xor     rcx, rsp; StackCookie
0x18001ccc5  call    __security_check_cookie
0x18001ccca  mov     rbx, [rsp+0C0h+arg_8]
0x18001ccd2  add     rsp, 90h
0x18001ccd9  pop     r15
0x18001ccdb  pop     r14
0x18001ccdd  pop     r13
0x18001ccdf  pop     r12
0x18001cce1  pop     rdi
0x18001cce2  pop     rsi
0x18001cce3  pop     rbp
0x18001cce4  retn
```

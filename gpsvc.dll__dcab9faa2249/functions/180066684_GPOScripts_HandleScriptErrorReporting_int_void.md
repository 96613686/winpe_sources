# GPOScripts::HandleScriptErrorReporting(int,void *)

- ea: `0x180066684`
- end: `0x180066abb`
- name: `?HandleScriptErrorReporting@GPOScripts@@AEAAKHPEAX@Z`
- size: `1079`
- prototype: `unsigned int __fastcall(GPOScripts *__hidden this, int, void *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180022d38`
- `0x180094498`
- `0x18009479c`

## callees

- `0x18001ee6c`
- `0x180022bd4`
- `0x18002c690`
- `0x18003d8d0`
- `0x180048790`
- `0x180066684`
- `0x180075ec0`
- `0x180094cb4`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800669c3`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800669c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006670d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006670d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066770`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066770`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066722`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066735`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066a67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066a77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066722`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066735`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066a67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066a77`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180066992`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180066992`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800667ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066826`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800668f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800669e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066a07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800667ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066826`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800668f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800669e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066a07`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180066703`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180066703`

## string_xrefs

- `0x18006685e`: `Error Opening registry key = %ws, with 0x%x`
- `0x1800668c0`: `Error Opening registry key = %ws, with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall GPOScripts::HandleScriptErrorReporting(GPOScripts *this, int a2, HKEY a3)
{
  unsigned __int16 *v6; // rbx
  unsigned int UserSid; // edi
  unsigned __int64 v8; // rdi
  __int64 v9; // rdi
  HLOCAL v10; // rax
  int v11; // eax
  unsigned __int64 v12; // rdx
  unsigned __int16 *v13; // rcx
  const unsigned __int16 *v14; // r8
  void (*v15)(unsigned int, const unsigned __int16 *, ...); // rax
  __int64 v16; // r8
  __int64 v17; // r8
  DWORD i; // r14d
  wchar_t *v19; // rax
  unsigned int v20; // eax
  HKEY v22[2]; // [rsp+60h] [rbp-19h] BYREF
  PSID Sid; // [rsp+70h] [rbp-9h] BYREF
  HKEY v24; // [rsp+78h] [rbp-1h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+Fh] BYREF
  LPCWSTR lpSubKey; // [rsp+90h] [rbp+17h] BYREF
  DWORD cSubKeys; // [rsp+E0h] [rbp+67h] BYREF
  LPWSTR StringSid; // [rsp+F8h] [rbp+7Fh] BYREF

  v24 = 0;
  hKey = 0;
  phkResult = 0;
  StringSid = 0;
  v6 = 0;
  lpSubKey = 0;
  if ( !*((_DWORD *)this + 4) )
  {
    v22[0] = (HKEY)&CToken::`vftable';
    v22[1] = a3;
    UserSid = 0;
    Sid = 0;
    StringSid = 0;
    if ( a3 )
    {
      UserSid = CToken::GetUserSid((CToken *)v22, &Sid);
      if ( !UserSid && !ConvertSidToStringSidW(Sid, &StringSid) )
      {
        UserSid = GetLastError();
        if ( UserSid )
        {
          if ( StringSid )
          {
            LocalFree(StringSid);
            StringSid = 0;
          }
        }
      }
    }
    if ( Sid )
      LocalFree(Sid);
    if ( UserSid )
      goto LABEL_51;
  }
  if ( *((_DWORD *)this + 4) )
  {
    v8 = 77;
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( StringSid[v9] );
    v8 = v9 + 70;
  }
  v10 = LocalAlloc(0x40u, 2 * v8);
  XPtrLF<unsigned short>::operator=((void **)&lpSubKey, v10);
  v6 = (unsigned __int16 *)lpSubKey;
  if ( !lpSubKey )
  {
    UserSid = 14;
    goto LABEL_51;
  }
  v11 = StringCchCopyW(
          (unsigned __int16 *)lpSubKey,
          v8,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\State\\");
  if ( v11 < 0 )
    goto LABEL_19;
  v12 = v8;
  v13 = v6;
  if ( *((_DWORD *)this + 4) )
  {
    v14 = L"Machine\\Scripts";
  }
  else
  {
    v11 = StringCchCatW(v6, v8, StringSid);
    if ( v11 < 0 )
      goto LABEL_19;
    v14 = L"\\Scripts";
    v12 = v8;
    v13 = v6;
  }
  v11 = StringCchCatW(v13, v12, v14);
  if ( v11 < 0 )
  {
LABEL_19:
    UserSid = (unsigned __int16)v11;
    goto LABEL_51;
  }
  UserSid = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
  if ( UserSid )
    goto LABEL_51;
  UserSid = RegOpenKeyExW(
              hKey,
              (LPCWSTR)*(&GPOScripts::ScriptParametersArray + 3 * *(int *)this + 2),
              0,
              0x20019u,
              &phkResult);
  if ( UserSid )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_51;
    v15 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v16 = (__int64)*(&GPOScripts::ScriptParametersArray + 3 * *(int *)this + 2);
LABEL_28:
      v15(2u, L"Error Opening registry key = %ws, with 0x%x", v16, UserSid);
      goto LABEL_51;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v17 = (__int64)*(&GPOScripts::ScriptParametersArray + 3 * *(int *)this + 2);
LABEL_34:
      RedirectDebugMsg(2u, L"Error Opening registry key = %ws, with 0x%x", v17, UserSid);
    }
  }
  else
  {
    UserSid = RegOpenKeyExW(
                *((HKEY *)this + 1),
                (LPCWSTR)*(&GPOScripts::ScriptParametersArray + 3 * *(int *)this),
                0,
                0x20019u,
                &v24);
    if ( UserSid )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v15 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v16 = (__int64)*(&GPOScripts::ScriptParametersArray + 3 * *(int *)this);
          goto LABEL_28;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v17 = (__int64)*(&GPOScripts::ScriptParametersArray + 3 * *(int *)this);
          goto LABEL_34;
        }
      }
    }
    else
    {
      cSubKeys = 0;
      UserSid = RegQueryInfoKeyW(v24, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      if ( !UserSid )
      {
        for ( i = 0; i < cSubKeys; ++i )
        {
          Sid = 0;
          v22[0] = 0;
          v19 = _itow(i, v6, 16);
          UserSid = RegOpenKeyExW(phkResult, v19, 0, 0x20019u, v22);
          if ( UserSid || (UserSid = RegOpenKeyExW(v24, v6, 0, 0x20019u, (PHKEY)&Sid)) != 0 )
          {
            XKey::Free((XKey *)v22);
            XKey::Free((XKey *)&Sid);
            break;
          }
          v20 = GPOScripts::HandleScriptsErrorCodeForEachGPO(this, (HKEY)Sid, v22[0], a2, a3);
          if ( v20 )
            UserSid = v20;
          XKey::Free((XKey *)v22);
          XKey::Free((XKey *)&Sid);
        }
      }
    }
  }
LABEL_51:
  if ( v6 )
    LocalFree(v6);
  if ( StringSid )
    StringSid = (LPWSTR)LocalFree(StringSid);
  XKey::Free((XKey *)&phkResult);
  XKey::Free((XKey *)&hKey);
  XKey::Free((XKey *)&v24);
  return UserSid;
}

```

## disassembly

```asm
0x180066684  mov     [rsp-8+arg_8], rbx
0x180066689  push    rbp
0x18006668a  push    rsi
0x18006668b  push    rdi
0x18006668c  push    r12
0x18006668e  push    r13
0x180066690  push    r14
0x180066692  push    r15
0x180066694  lea     rbp, [rsp-27h]
0x180066699  sub     rsp, 0A0h
0x1800666a0  mov     r15, r8
0x1800666a3  mov     r12d, edx
0x1800666a6  mov     rsi, rcx
0x1800666a9  xor     r13d, r13d
0x1800666ac  mov     [rbp+57h+var_58], r13
0x1800666b0  mov     [rbp+57h+hKey], r13
0x1800666b4  mov     [rbp+57h+var_50], r13
0x1800666b8  mov     [rbp+57h+StringSid], r13
0x1800666bc  mov     ebx, r13d
0x1800666bf  mov     [rbp+57h+lpSubKey], rbx
0x1800666c3  cmp     [rcx+10h], r13d
0x1800666c7  jnz     short loc_180066744
0x1800666c9  lea     rax, ??_7CToken@@6B@; const CToken::`vftable'
0x1800666d0  mov     [rbp+57h+var_70], rax
0x1800666d4  mov     [rbp+57h+var_68], r8
0x1800666d8  mov     edi, r13d
0x1800666db  mov     [rbp+57h+Sid], r13
0x1800666df  mov     [rbp+57h+StringSid], r13
0x1800666e3  test    r8, r8
0x1800666e6  jz      short loc_18006672C
0x1800666e8  lea     rdx, [rbp+57h+Sid]; void **
0x1800666ec  lea     rcx, [rbp+57h+var_70]; this
0x1800666f0  call    ?GetUserSid@CToken@@UEBAKPEAPEAX@Z; CToken::GetUserSid(void * *)
0x1800666f5  mov     edi, eax
0x1800666f7  test    eax, eax
0x1800666f9  jnz     short loc_18006672C
0x1800666fb  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800666ff  mov     rcx, [rbp+57h+Sid]; Sid
0x180066703  call    cs:__imp_ConvertSidToStringSidW
0x180066709  test    eax, eax
0x18006670b  jnz     short loc_18006672C
0x18006670d  call    cs:__imp_GetLastError
0x180066713  mov     edi, eax
0x180066715  test    eax, eax
0x180066717  jz      short loc_18006672C
0x180066719  mov     rcx, [rbp+57h+StringSid]; hMem
0x18006671d  test    rcx, rcx
0x180066720  jz      short loc_18006672C
0x180066722  call    cs:__imp_LocalFree
0x180066728  mov     [rbp+57h+StringSid], r13
0x18006672c  mov     rcx, [rbp+57h+Sid]; hMem
0x180066730  test    rcx, rcx
0x180066733  jz      short loc_18006673C
0x180066735  call    cs:__imp_LocalFree
0x18006673b  nop
0x18006673c  test    edi, edi
0x18006673e  jnz     loc_180066A5F
0x180066744  cmp     [rsi+10h], r13d
0x180066748  jz      short loc_180066751
0x18006674a  mov     edi, 4Dh ; 'M'
0x18006674f  jmp     short loc_180066767
0x180066751  mov     rax, [rbp+57h+StringSid]
0x180066755  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180066759  inc     rdi
0x18006675c  cmp     [rax+rdi*2], r13w
0x180066761  jnz     short loc_180066759
0x180066763  add     rdi, 46h ; 'F'
0x180066767  lea     rdx, [rdi+rdi]; uBytes
0x18006676b  mov     ecx, 40h ; '@'; uFlags
0x180066770  call    cs:__imp_LocalAlloc
0x180066776  mov     rdx, rax
0x180066779  lea     rcx, [rbp+57h+lpSubKey]
0x18006677d  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x180066782  mov     rbx, [rbp+57h+lpSubKey]
0x180066786  test    rbx, rbx
0x180066789  jnz     short loc_180066793
0x18006678b  lea     edi, [rbx+0Eh]
0x18006678e  jmp     loc_180066A5F
0x180066793  lea     r8, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006679a  mov     rdx, rdi; unsigned __int64
0x18006679d  mov     rcx, rbx; unsigned __int16 *
0x1800667a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800667a5  test    eax, eax
0x1800667a7  jns     short loc_1800667B1
0x1800667a9  movzx   edi, ax
0x1800667ac  jmp     loc_180066A5F
0x1800667b1  mov     rdx, rdi; unsigned __int64
0x1800667b4  mov     rcx, rbx; unsigned __int16 *
0x1800667b7  cmp     [rsi+10h], r13d
0x1800667bb  jz      loc_180066874
0x1800667c1  lea     r8, aMachineScripts; "Machine\\Scripts"
0x1800667c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800667cd  test    eax, eax
0x1800667cf  js      short loc_1800667A9
0x1800667d1  lea     rax, [rbp+57h+hKey]
0x1800667d5  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800667da  mov     r9d, 20019h; samDesired
0x1800667e0  xor     r8d, r8d; ulOptions
0x1800667e3  mov     rdx, rbx; lpSubKey
0x1800667e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800667ed  call    cs:__imp_RegOpenKeyExW
0x1800667f3  mov     edi, eax
0x1800667f5  test    eax, eax
0x1800667f7  jnz     loc_180066A5F
0x1800667fd  movsxd  rax, dword ptr [rsi]
0x180066800  lea     rdx, [rax+rax*2]
0x180066804  lea     r14, ?ScriptParametersArray@GPOScripts@@0PAU_ScriptParameters@@A; _ScriptParameters near * GPOScripts::ScriptParametersArray
0x18006680b  lea     rax, [rbp+57h+var_50]
0x18006680f  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180066814  mov     r9d, 20019h; samDesired
0x18006681a  xor     r8d, r8d; ulOptions
0x18006681d  mov     rdx, [r14+rdx*8+10h]; lpSubKey
0x180066822  mov     rcx, [rbp+57h+hKey]; hKey
0x180066826  call    cs:__imp_RegOpenKeyExW
0x18006682c  mov     edi, eax
0x18006682e  test    eax, eax
0x180066830  jz      loc_1800668D6
0x180066836  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006683d  jz      loc_180066A5F
0x180066843  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006684a  test    rax, rax
0x18006684d  jz      short loc_180066897
0x18006684f  movsxd  rcx, dword ptr [rsi]
0x180066852  lea     r8, [rcx+rcx*2]
0x180066856  mov     r8, [r14+r8*8+10h]
0x18006685b  mov     r9d, edi
0x18006685e  lea     rdx, aErrorOpeningRe; "Error Opening registry key = %ws, with "...
0x180066865  mov     ecx, 2
0x18006686a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006686f  jmp     loc_180066A5F
0x180066874  mov     r8, [rbp+57h+StringSid]; unsigned __int16 *
0x180066878  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006687d  test    eax, eax
0x18006687f  js      loc_1800667A9
0x180066885  lea     r8, aScripts; "\\Scripts"
0x18006688c  mov     rdx, rdi
0x18006688f  mov     rcx, rbx
0x180066892  jmp     loc_1800667C8
0x180066897  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006689e  jz      loc_180066A5F
0x1800668a4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800668ab  jz      loc_180066A5F
0x1800668b1  movsxd  rax, dword ptr [rsi]
0x1800668b4  lea     r8, [rax+rax*2]
0x1800668b8  mov     r8, [r14+r8*8+10h]
0x1800668bd  mov     r9d, edi
0x1800668c0  lea     rdx, aErrorOpeningRe; "Error Opening registry key = %ws, with "...
0x1800668c7  mov     ecx, 2; unsigned int
0x1800668cc  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800668d1  jmp     loc_180066A5F
0x1800668d6  movsxd  rax, dword ptr [rsi]
0x1800668d9  lea     rdx, [rax+rax*2]
0x1800668dd  lea     rax, [rbp+57h+var_58]
0x1800668e1  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800668e6  mov     r9d, 20019h; samDesired
0x1800668ec  xor     r8d, r8d; ulOptions
0x1800668ef  mov     rdx, [r14+rdx*8]; lpSubKey
0x1800668f3  mov     rcx, [rsi+8]; hKey
0x1800668f7  call    cs:__imp_RegOpenKeyExW
0x1800668fd  mov     edi, eax
0x1800668ff  test    eax, eax
0x180066901  jz      short loc_180066956
0x180066903  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006690a  jz      loc_180066A5F
0x180066910  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180066917  test    rax, rax
0x18006691a  jz      short loc_18006692C
0x18006691c  movsxd  rcx, dword ptr [rsi]
0x18006691f  lea     r8, [rcx+rcx*2]
0x180066923  mov     r8, [r14+r8*8]
0x180066927  jmp     loc_18006685B
0x18006692c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180066933  jz      loc_180066A5F
0x180066939  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180066940  jz      loc_180066A5F
0x180066946  movsxd  rax, dword ptr [rsi]
0x180066949  lea     r8, [rax+rax*2]
0x18006694d  mov     r8, [r14+r8*8]
0x180066951  jmp     loc_1800668BD
0x180066956  mov     [rbp+57h+cSubKeys], r13d
0x18006695a  mov     [rsp+0D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18006695f  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180066964  mov     [rsp+0D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180066969  mov     [rsp+0D0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18006696e  mov     [rsp+0D0h+lpcValues], r13; lpcValues
0x180066973  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180066978  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18006697d  lea     rax, [rbp+57h+cSubKeys]
0x180066981  mov     [rsp+0D0h+phkResult], rax; lpcSubKeys
0x180066986  xor     r9d, r9d; lpReserved
0x180066989  xor     r8d, r8d; lpcchClass
0x18006698c  xor     edx, edx; lpClass
0x18006698e  mov     rcx, [rbp+57h+var_58]; hKey
0x180066992  call    cs:__imp_RegQueryInfoKeyW
0x180066998  mov     edi, eax
0x18006699a  test    eax, eax
0x18006699c  jnz     loc_180066A5F
0x1800669a2  mov     r14d, r13d
0x1800669a5  cmp     r14d, [rbp+57h+cSubKeys]
0x1800669a9  jnb     loc_180066A5F
0x1800669af  mov     [rbp+57h+Sid], r13
0x1800669b3  mov     [rbp+57h+var_70], r13
0x1800669b7  mov     r8d, 10h; Radix
0x1800669bd  mov     rdx, rbx; Buffer
0x1800669c0  mov     ecx, r14d; Value
0x1800669c3  call    cs:__imp__itow
0x1800669c9  lea     rcx, [rbp+57h+var_70]
0x1800669cd  mov     [rsp+0D0h+phkResult], rcx; phkResult
0x1800669d2  mov     r9d, 20019h; samDesired
0x1800669d8  xor     r8d, r8d; ulOptions
0x1800669db  mov     rdx, rax; lpSubKey
0x1800669de  mov     rcx, [rbp+57h+var_50]; hKey
0x1800669e2  call    cs:__imp_RegOpenKeyExW
0x1800669e8  mov     edi, eax
0x1800669ea  test    eax, eax
0x1800669ec  jnz     short loc_180066A4B
0x1800669ee  lea     rax, [rbp+57h+Sid]
0x1800669f2  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800669f7  mov     r9d, 20019h; samDesired
0x1800669fd  xor     r8d, r8d; ulOptions
0x180066a00  mov     rdx, rbx; lpSubKey
0x180066a03  mov     rcx, [rbp+57h+var_58]; hKey
0x180066a07  call    cs:__imp_RegOpenKeyExW
0x180066a0d  mov     edi, eax
0x180066a0f  test    eax, eax
0x180066a11  jnz     short loc_180066A4B
0x180066a13  mov     [rsp+0D0h+phkResult], r15; void *
0x180066a18  mov     r9d, r12d; int
0x180066a1b  mov     r8, [rbp+57h+var_70]; HKEY
0x180066a1f  mov     rdx, [rbp+57h+Sid]; HKEY
0x180066a23  mov     rcx, rsi; this
0x180066a26  call    ?HandleScriptsErrorCodeForEachGPO@GPOScripts@@AEAAKPEAUHKEY__@@0HPEAX@Z; GPOScripts::HandleScriptsErrorCodeForEachGPO(HKEY__ *,HKEY__ *,int,void *)
0x180066a2b  test    eax, eax
0x180066a2d  cmovnz  edi, eax
0x180066a30  lea     rcx, [rbp+57h+var_70]; this
0x180066a34  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180066a39  nop
0x180066a3a  lea     rcx, [rbp+57h+Sid]; this
0x180066a3e  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180066a43  inc     r14d
0x180066a46  jmp     loc_1800669A5
0x180066a4b  lea     rcx, [rbp+57h+var_70]; this
0x180066a4f  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180066a54  nop
0x180066a55  lea     rcx, [rbp+57h+Sid]; this
0x180066a59  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180066a5e  nop
0x180066a5f  test    rbx, rbx
0x180066a62  jz      short loc_180066A6E
0x180066a64  mov     rcx, rbx; hMem
0x180066a67  call    cs:__imp_LocalFree
0x180066a6d  nop
0x180066a6e  mov     rcx, [rbp+57h+StringSid]; hMem
0x180066a72  test    rcx, rcx
0x180066a75  jz      short loc_180066A81
0x180066a77  call    cs:__imp_LocalFree
0x180066a7d  mov     [rbp+57h+StringSid], rax
0x180066a81  lea     rcx, [rbp+57h+var_50]; this
0x180066a85  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180066a8a  nop
0x180066a8b  lea     rcx, [rbp+57h+hKey]; this
0x180066a8f  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180066a94  nop
0x180066a95  lea     rcx, [rbp+57h+var_58]; this
0x180066a99  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180066a9e  mov     eax, edi
0x180066aa0  mov     rbx, [rsp+0D0h+arg_8]
0x180066aa8  add     rsp, 0A0h
0x180066aaf  pop     r15
0x180066ab1  pop     r14
0x180066ab3  pop     r13
0x180066ab5  pop     r12
0x180066ab7  pop     rdi
0x180066ab8  pop     rsi
0x180066ab9  pop     rbp
0x180066aba  retn
```

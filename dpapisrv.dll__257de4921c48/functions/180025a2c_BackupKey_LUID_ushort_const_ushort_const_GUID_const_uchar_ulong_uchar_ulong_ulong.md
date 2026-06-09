# BackupKey(_LUID *,ushort const *,ushort const *,_GUID const *,uchar *,ulong,uchar * *,ulong *,ulong)

- ea: `0x180025a2c`
- end: `0x1800261e0`
- name: `?BackupKey@@YAKPEAU_LUID@@PEBG1PEBU_GUID@@PEAEKPEAPEAEPEAKK@Z`
- size: `1972`
- prototype: `__int64 __fastcall(struct _LUID *, unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002677c`

## callees

- `0x180007f10`
- `0x180010d78`
- `0x1800123e8`
- `0x180013f2c`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x180025a2c`
- `0x18002635c`
- `0x180027f14`
- `0x180027f90`
- `0x18003b27c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180025fc0`
- `RPCRT4!NdrClientCall3` at `0x180025fc0`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180025de1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180025de1`
- `RPCRT4!RpcStringBindingComposeW` at `0x180025d7a`
- `RPCRT4!RpcStringBindingComposeW` at `0x180025d7a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180025f2e`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180025f2e`
- `RPCRT4!RpcNetworkIsProtseqValidW` at `0x180025cff`
- `RPCRT4!RpcNetworkIsProtseqValidW` at `0x180025cff`
- `RPCRT4!RpcStringFreeW` at `0x180025dfb`
- `RPCRT4!RpcStringFreeW` at `0x180025dfb`
- `RPCRT4!RpcEpResolveBinding` at `0x180025e4e`
- `RPCRT4!RpcEpResolveBinding` at `0x180025e4e`
- `RPCRT4!RpcBindingFree` at `0x180025ce0`
- `RPCRT4!RpcBindingFree` at `0x18002619a`
- `RPCRT4!RpcBindingFree` at `0x180025ce0`
- `RPCRT4!RpcBindingFree` at `0x18002619a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ae7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800260b8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800260b8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800260d0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180026164`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800260d0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180026164`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026098`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026098`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025c23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025c5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025c84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800261a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025c23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025c5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025c84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800261a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025bc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025bc9`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180025ad7`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180025ad7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002617d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002617d`
- `netutils!NetApiBufferFree` at `0x18002614e`
- `netutils!NetApiBufferFree` at `0x18002614e`
- `samcli!NetUserGetInfo` at `0x1800260fc`
- `samcli!NetUserGetInfo` at `0x1800260fc`

## string_xrefs

- `0x180025b04`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180025beb`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180025fe5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180026004`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`

## pseudocode

```c
__int64 __fastcall BackupKey(
        struct _LUID *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  DWORD LastError; // ebx
  __int64 v10; // r9
  const char *v11; // rdx
  __int64 v12; // rcx
  __int64 v14; // rcx
  int v15; // r12d
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rbx
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // r14
  unsigned int v21; // esi
  int Pointer; // ebx
  __int64 i; // r12
  __int64 v24; // r12
  RPC_STATUS IsProtseqValidW; // eax
  RPC_STATUS v26; // eax
  int v27; // r8d
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  unsigned int v31; // eax
  CLIENT_CALL_RETURN v32; // rax
  HANDLE CurrentThread; // rax
  LPBYTE v34; // rax
  RPC_SECURITY_QOS *SecurityQOS; // [rsp+30h] [rbp-158h]
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-138h] BYREF
  int v37; // [rsp+58h] [rbp-130h]
  LPBYTE bufptr; // [rsp+60h] [rbp-128h] BYREF
  int v39; // [rsp+68h] [rbp-120h]
  RPC_WSTR String; // [rsp+70h] [rbp-118h] BYREF
  RPC_WSTR NetworkAddr; // [rsp+78h] [rbp-110h]
  DWORD v42; // [rsp+80h] [rbp-108h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-100h] BYREF
  const struct _GUID *v44; // [rsp+90h] [rbp-F8h]
  unsigned __int8 *v45; // [rsp+98h] [rbp-F0h]
  unsigned __int8 **v46; // [rsp+A0h] [rbp-E8h]
  unsigned int *v47; // [rsp+A8h] [rbp-E0h]
  CLIENT_CALL_RETURN v48; // [rsp+B0h] [rbp-D8h]
  unsigned __int16 *v49; // [rsp+B8h] [rbp-D0h]
  unsigned __int16 *v50; // [rsp+C0h] [rbp-C8h]
  const struct _GUID *v51; // [rsp+C8h] [rbp-C0h]
  _DWORD AuthIdentity[14]; // [rsp+D0h] [rbp-B8h] BYREF
  const wchar_t *v53; // [rsp+108h] [rbp-80h]
  int v54; // [rsp+110h] [rbp-78h]
  RPC_SECURITY_QOS v55; // [rsp+120h] [rbp-68h] BYREF
  WCHAR username[20]; // [rsp+130h] [rbp-58h] BYREF

  v44 = a4;
  NetworkAddr = a2;
  v50 = a2;
  v51 = a4;
  v45 = a5;
  v46 = a7;
  v47 = a8;
  Binding = 0;
  String = 0;
  TokenHandle = 0;
  v42 = 17;
  *a7 = 0;
  *a8 = 0;
  if ( !GetComputerNameExW(ComputerNameNetBIOS, username, &v42) )
  {
    LastError = GetLastError();
    v10 = 2624;
    v11 = "dwRetVal";
    v12 = LastError;
LABEL_3:
    DebugTraceError(v12, v11, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", v10);
    return LastError;
  }
  if ( (unsigned int)IsLocal() )
    goto LABEL_14;
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_f4b69f1db01237bb0e3a2b08d8c2cb9e_Traceguids);
    v14 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
LABEL_11:
    if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 8) != 0 )
      WPP_SF_(*(_QWORD *)(v14 + 16), 20, WPP_f4b69f1db01237bb0e3a2b08d8c2cb9e_Traceguids);
LABEL_14:
    v15 = 1;
    LODWORD(bufptr) = 1;
    goto LABEL_15;
  }
  v15 = 0;
  LODWORD(bufptr) = 0;
  if ( CompareNameToDnsName(username, a2) )
  {
    v14 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
LABEL_15:
  if ( a2 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a2[v16] );
  }
  else
  {
    LODWORD(v16) = 0;
  }
  v17 = (unsigned int)(v16 + 18);
  v18 = (unsigned int)v17;
  v19 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v17);
  v20 = v19;
  v49 = v19;
  if ( !v19 )
  {
    DebugTraceError(8, "dwRetVal", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 2661);
    return 8;
  }
  if ( (unsigned int)StringCchCopyW(v19, v18, L"ProtectedStorage") )
  {
    LocalFree(v20);
    v10 = 2668;
LABEL_24:
    v11 = "ERROR_INSUFFICIENT_BUFFER";
    LastError = 122;
    v12 = 122;
    goto LABEL_3;
  }
  if ( StringCchCatW(v20, v18, L"/") )
  {
    LocalFree(v20);
    v10 = 2674;
    goto LABEL_24;
  }
  if ( StringCchCatW(v20, v18, a2) )
  {
    LocalFree(v20);
    v10 = 2680;
    goto LABEL_24;
  }
  v21 = 0;
  Pointer = 87;
  v39 = 87;
  for ( i = v15 ^ 1u; ; i = (unsigned int)(v37 + 1) )
  {
    v37 = i;
    if ( (unsigned int)i >= 3 )
      break;
    v55 = 0;
    memset_0(AuthIdentity, 0, 0x48u);
    if ( Binding )
    {
      RpcBindingFree(&Binding);
      Binding = 0;
    }
    v24 = 2 * i;
    IsProtseqValidW = RpcNetworkIsProtseqValidW((RPC_WSTR)*(&g_awzrBackupBindingList + v24));
    v21 = IsProtseqValidW;
    if ( IsProtseqValidW )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
        WPP_SF_SD(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          21,
          (unsigned int)WPP_f4b69f1db01237bb0e3a2b08d8c2cb9e_Traceguids,
          (unsigned int)*(&g_awzrBackupBindingList + v24),
          IsProtseqValidW);
    }
    else
    {
      v26 = RpcStringBindingComposeW(
              0,
              (RPC_WSTR)*(&g_awzrBackupBindingList + v24),
              NetworkAddr,
              (RPC_WSTR)*(&g_awzrBackupBindingList + v24 + 1),
              0,
              &String);
      v21 = v26;
      if ( v26 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
          WPP_SF_SSSD(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&g_awzrBackupBindingList,
            v27,
            (unsigned int)*(&g_awzrBackupBindingList + v24),
            (__int64)NetworkAddr,
            (__int64)*(&g_awzrBackupBindingList + v24 + 1),
            v26);
      }
      else
      {
        v21 = RpcBindingFromStringBindingW(String, &Binding);
        if ( String )
          RpcStringFreeW(&String);
        if ( v21 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
          {
            v29 = 23;
            v30 = v21;
            goto LABEL_47;
          }
        }
        else
        {
          v31 = RpcEpResolveBinding(Binding, qword_18003FFE0);
          v21 = v31;
          if ( v31 )
          {
            v28 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
            {
              v29 = 24;
              goto LABEL_52;
            }
          }
          else
          {
            v55.Version = 1;
            v55.Capabilities = 1;
            v55.IdentityTracking = 1;
            v55.ImpersonationType = 3;
            memset_0(AuthIdentity, 0, 0x48u);
            AuthIdentity[0] = 512;
            AuthIdentity[1] = 72;
            v53 = L"Kerberos,NTLM";
            v54 = 13;
            AuthIdentity[13] = 2;
            v31 = RpcBindingSetAuthInfoExW(Binding, v20, 6u, 9u, AuthIdentity, 0, &v55);
            v21 = v31;
            if ( !v31 )
            {
              v48.Simple = 0;
              LODWORD(SecurityQOS) = a6;
              v32.Pointer = NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0,
                              0,
                              Binding,
                              v44,
                              v45,
                              SecurityQOS,
                              v46,
                              v47,
                              0).Pointer;
              Pointer = (int)v32.Pointer;
              v48.Pointer = v32.Pointer;
              v39 = (int)v32.Pointer;
              if ( LODWORD(v32.Pointer) )
                DebugTraceError(
                  LODWORD(v32.Pointer),
                  "dwRetVal",
                  "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
                  2811);
              goto LABEL_74;
            }
            v28 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
            {
              v29 = 25;
LABEL_52:
              v30 = v31;
LABEL_47:
              WPP_SF_d(*(_QWORD *)(v28 + 16), v29, WPP_f4b69f1db01237bb0e3a2b08d8c2cb9e_Traceguids, v30);
              continue;
            }
          }
        }
      }
    }
  }
  if ( v21 )
  {
    if ( !(_DWORD)bufptr )
    {
      bufptr = 0;
      if ( !StringCchCatW(username, 0x11u, L"$") )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
        {
          if ( SetThreadToken(0, 0) )
          {
            if ( !NetUserGetInfo(NetworkAddr, username, 1u, &bufptr) )
            {
              v34 = bufptr;
              if ( (*((_DWORD *)bufptr + 10) & 0x80000) == 0 )
              {
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
                {
                  WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, WPP_f4b69f1db01237bb0e3a2b08d8c2cb9e_Traceguids);
                  v34 = bufptr;
                }
                v21 = -2146892987;
              }
              NetApiBufferFree(v34);
            }
            SetThreadToken(0, TokenHandle);
          }
        }
      }
    }
  }
LABEL_74:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( !v21 )
    v21 = Pointer;
  if ( Binding )
    RpcBindingFree(&Binding);
  LocalFree(v20);
  return v21;
}

```

## disassembly

```asm
0x180025a2c  mov     r11, rsp
0x180025a2f  mov     [r11+8], rbx
0x180025a33  push    rsi
0x180025a34  push    rdi
0x180025a35  push    r12
0x180025a37  push    r13
0x180025a39  push    r14
0x180025a3b  sub     rsp, 160h
0x180025a42  mov     rax, cs:__security_cookie
0x180025a49  xor     rax, rsp
0x180025a4c  mov     [rsp+188h+var_30], rax
0x180025a54  mov     rax, r9
0x180025a57  mov     [rsp+188h+var_F8], rax
0x180025a5f  mov     rsi, rdx
0x180025a62  mov     [rsp+188h+NetworkAddr], rdx
0x180025a67  mov     [rsp+188h+var_C8], rdx
0x180025a6f  mov     [rsp+188h+var_C0], rax
0x180025a77  mov     rax, [rsp+188h+arg_20]
0x180025a7f  mov     [rsp+188h+var_F0], rax
0x180025a87  mov     rax, [rsp+188h+arg_30]
0x180025a8f  mov     [rsp+188h+var_E8], rax
0x180025a97  mov     rcx, [rsp+188h+arg_38]
0x180025a9f  mov     [rsp+188h+var_E0], rcx
0x180025aa7  xor     edi, edi
0x180025aa9  mov     [rsp+188h+Binding], rdi
0x180025aae  mov     [rsp+188h+String], rdi
0x180025ab3  mov     [r11-100h], rdi
0x180025aba  mov     [rsp+188h+var_108], 11h
0x180025ac5  mov     [rax], rdi
0x180025ac8  mov     [rcx], edi
0x180025aca  lea     r8, [r11-108h]; nSize
0x180025ad1  lea     rdx, [r11-58h]; lpBuffer
0x180025ad5  xor     ecx, ecx; NameType
0x180025ad7  call    cs:__imp_GetComputerNameExW
0x180025ade  nop     dword ptr [rax+rax+00h]
0x180025ae3  test    eax, eax
0x180025ae5  jnz     short loc_180025B17
0x180025ae7  call    cs:__imp_GetLastError
0x180025aee  nop     dword ptr [rax+rax+00h]
0x180025af3  mov     ebx, eax
0x180025af5  mov     r9d, 0A40h
0x180025afb  lea     rdx, aDwretval; "dwRetVal"
0x180025b02  mov     ecx, eax
0x180025b04  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180025b0b  call    DebugTraceError
0x180025b10  mov     eax, ebx
0x180025b12  jmp     loc_1800261B7
0x180025b17  call    IsLocal
0x180025b1c  lea     r13, WPP_GLOBAL_Control
0x180025b23  test    eax, eax
0x180025b25  jnz     short loc_180025B9A
0x180025b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b2e  cmp     rcx, r13
0x180025b31  jz      short loc_180025B53
0x180025b33  test    byte ptr [rcx+1Ch], 8
0x180025b37  jz      short loc_180025B53
0x180025b39  lea     edx, [rax+13h]
0x180025b3c  lea     r8, WPP_f4b69f1db01237bb0e3a2b08d8c2cb9e_Traceguids
0x180025b43  mov     rcx, [rcx+10h]
0x180025b47  call    WPP_SF_
0x180025b4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b53  test    rsi, rsi
0x180025b56  jz      short loc_180025B7A
0x180025b58  mov     r12d, edi
0x180025b5b  mov     dword ptr [rsp+188h+bufptr], edi
0x180025b5f  mov     rdx, rsi; unsigned __int16 *
0x180025b62  lea     rcx, [rsp+188h+username]; SourceString
0x180025b6a  call    ?CompareNameToDnsName@@YAEPEBG0@Z; CompareNameToDnsName(ushort const *,ushort const *)
0x180025b6f  test    al, al
0x180025b71  jz      short loc_180025BA5
0x180025b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b7a  cmp     rcx, r13
0x180025b7d  jz      short loc_180025B9A
0x180025b7f  test    byte ptr [rcx+1Ch], 8
0x180025b83  jz      short loc_180025B9A
0x180025b85  mov     edx, 14h
0x180025b8a  lea     r8, WPP_f4b69f1db01237bb0e3a2b08d8c2cb9e_Traceguids
0x180025b91  mov     rcx, [rcx+10h]
0x180025b95  call    WPP_SF_
0x180025b9a  mov     r12d, 1
0x180025ba0  mov     dword ptr [rsp+188h+bufptr], r12d
0x180025ba5  test    rsi, rsi
0x180025ba8  jz      short loc_180025BB9
0x180025baa  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025bae  inc     rax
0x180025bb1  cmp     [rsi+rax*2], di
0x180025bb5  jnz     short loc_180025BAE
0x180025bb7  jmp     short loc_180025BBB
0x180025bb9  mov     eax, edi
0x180025bbb  add     eax, 12h
0x180025bbe  mov     ebx, eax
0x180025bc0  lea     rdx, [rax+rax]; uBytes
0x180025bc4  mov     ecx, 40h ; '@'; uFlags
0x180025bc9  call    cs:__imp_LocalAlloc
0x180025bd0  nop     dword ptr [rax+rax+00h]
0x180025bd5  mov     r14, rax
0x180025bd8  mov     [rsp+188h+var_D0], rax
0x180025be0  test    rax, rax
0x180025be3  jnz     short loc_180025C0A
0x180025be5  mov     r9d, 0A65h
0x180025beb  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180025bf2  lea     rdx, aDwretval; "dwRetVal"
0x180025bf9  lea     ecx, [rax+8]
0x180025bfc  call    DebugTraceError
0x180025c01  lea     eax, [r14+8]
0x180025c05  jmp     loc_1800261B7
0x180025c0a  lea     r8, aProtectedstora; "ProtectedStorage"
0x180025c11  mov     rdx, rbx; unsigned __int64
0x180025c14  mov     rcx, r14; unsigned __int16 *
0x180025c17  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025c1c  mov     rcx, r14; unsigned __int16 *
0x180025c1f  test    eax, eax
0x180025c21  jz      short loc_180025C48
0x180025c23  call    cs:__imp_LocalFree
0x180025c2a  nop     dword ptr [rax+rax+00h]
0x180025c2f  mov     r9d, 0A6Ch
0x180025c35  lea     rdx, aErrorInsuffici; "ERROR_INSUFFICIENT_BUFFER"
0x180025c3c  mov     ebx, 7Ah ; 'z'
0x180025c41  mov     ecx, ebx
0x180025c43  jmp     loc_180025B04
0x180025c48  lea     r8, asc_180041E70; "/"
0x180025c4f  mov     rdx, rbx; unsigned __int64
0x180025c52  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180025c57  mov     rcx, r14; unsigned __int16 *
0x180025c5a  test    eax, eax
0x180025c5c  jz      short loc_180025C72
0x180025c5e  call    cs:__imp_LocalFree
0x180025c65  nop     dword ptr [rax+rax+00h]
0x180025c6a  mov     r9d, 0A72h
0x180025c70  jmp     short loc_180025C35
0x180025c72  mov     r8, rsi; unsigned __int16 *
0x180025c75  mov     rdx, rbx; unsigned __int64
0x180025c78  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180025c7d  test    eax, eax
0x180025c7f  jz      short loc_180025C98
0x180025c81  mov     rcx, r14; hMem
0x180025c84  call    cs:__imp_LocalFree
0x180025c8b  nop     dword ptr [rax+rax+00h]
0x180025c90  mov     r9d, 0A78h
0x180025c96  jmp     short loc_180025C35
0x180025c98  mov     esi, edi
0x180025c9a  mov     ebx, 57h ; 'W'
0x180025c9f  mov     [rsp+188h+var_120], ebx
0x180025ca3  xor     r12d, 1
0x180025ca7  mov     [rsp+188h+var_130], r12d
0x180025cac  cmp     r12d, 3
0x180025cb0  jnb     loc_180026060
0x180025cb6  xorps   xmm0, xmm0
0x180025cb9  movups  xmmword ptr [rsp+188h+var_68.Version], xmm0
0x180025cc1  xor     edx, edx; Val
0x180025cc3  lea     r8d, [rdx+48h]; Size
0x180025cc7  lea     rcx, [rsp+188h+AuthIdentity]; void *
0x180025ccf  call    memset_0
0x180025cd4  cmp     [rsp+188h+Binding], rdi
0x180025cd9  jz      short loc_180025CF1
0x180025cdb  lea     rcx, [rsp+188h+Binding]; Binding
0x180025ce0  call    cs:__imp_RpcBindingFree
0x180025ce7  nop     dword ptr [rax+rax+00h]
0x180025cec  mov     [rsp+188h+Binding], rdi
0x180025cf1  add     r12, r12
0x180025cf4  lea     rax, ?g_awzrBackupBindingList@@3PAU_WZR_RPC_BINDING_LIST@@A; _WZR_RPC_BINDING_LIST near * g_awzrBackupBindingList
0x180025cfb  mov     rcx, [rax+r12*8]; Protseq
0x180025cff  call    cs:__imp_RpcNetworkIsProtseqValidW
0x180025d06  nop     dword ptr [rax+rax+00h]
0x180025d0b  mov     esi, eax
0x180025d0d  test    eax, eax
0x180025d0f  jz      short loc_180025D54
0x180025d11  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d18  cmp     rcx, r13
0x180025d1b  jz      loc_180026053
0x180025d21  test    byte ptr [rcx+1Ch], 8
0x180025d25  jz      loc_180026053
0x180025d2b  mov     edx, 15h
0x180025d30  mov     dword ptr [rsp+188h+Options], eax
0x180025d34  lea     rax, ?g_awzrBackupBindingList@@3PAU_WZR_RPC_BINDING_LIST@@A; _WZR_RPC_BINDING_LIST near * g_awzrBackupBindingList
0x180025d3b  mov     r9, [rax+r12*8]
0x180025d3f  lea     r8, WPP_f4b69f1db01237bb0e3a2b08d8c2cb9e_Traceguids
0x180025d46  mov     rcx, [rcx+10h]
0x180025d4a  call    WPP_SF_SD
0x180025d4f  jmp     loc_180026053
0x180025d54  lea     rax, [rsp+188h+String]
0x180025d59  mov     [rsp+188h+StringBinding], rax; StringBinding
0x180025d5e  mov     [rsp+188h+Options], rdi; Options
0x180025d63  lea     rax, ?g_awzrBackupBindingList@@3PAU_WZR_RPC_BINDING_LIST@@A; _WZR_RPC_BINDING_LIST near * g_awzrBackupBindingList
0x180025d6a  mov     r9, [rax+r12*8+8]; Endpoint
0x180025d6f  mov     r8, [rsp+188h+NetworkAddr]; NetworkAddr
0x180025d74  mov     rdx, [rax+r12*8]; ProtSeq
0x180025d78  xor     ecx, ecx; ObjUuid
0x180025d7a  call    cs:__imp_RpcStringBindingComposeW
0x180025d81  nop     dword ptr [rax+rax+00h]
0x180025d86  mov     esi, eax
0x180025d88  test    eax, eax
0x180025d8a  jz      short loc_180025DD7
0x180025d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d93  cmp     rcx, r13
0x180025d96  jz      loc_180026053
0x180025d9c  test    byte ptr [rcx+1Ch], 8
0x180025da0  jz      loc_180026053
0x180025da6  mov     dword ptr [rsp+188h+SecurityQOS], eax
0x180025daa  lea     rdx, ?g_awzrBackupBindingList@@3PAU_WZR_RPC_BINDING_LIST@@A; _WZR_RPC_BINDING_LIST near * g_awzrBackupBindingList
0x180025db1  mov     rax, [rdx+r12*8+8]
0x180025db6  mov     [rsp+188h+StringBinding], rax
0x180025dbb  mov     rax, [rsp+188h+NetworkAddr]
0x180025dc0  mov     [rsp+188h+Options], rax
0x180025dc5  mov     r9, [rdx+r12*8]
0x180025dc9  mov     rcx, [rcx+10h]
0x180025dcd  call    WPP_SF_SSSD
0x180025dd2  jmp     loc_180026053
0x180025dd7  lea     rdx, [rsp+188h+Binding]; Binding
0x180025ddc  mov     rcx, [rsp+188h+String]; StringBinding
0x180025de1  call    cs:__imp_RpcBindingFromStringBindingW
0x180025de8  nop     dword ptr [rax+rax+00h]
0x180025ded  mov     esi, eax
0x180025def  cmp     [rsp+188h+String], rdi
0x180025df4  jz      short loc_180025E07
0x180025df6  lea     rcx, [rsp+188h+String]; String
0x180025dfb  call    cs:__imp_RpcStringFreeW
0x180025e02  nop     dword ptr [rax+rax+00h]
0x180025e07  test    esi, esi
0x180025e09  jz      short loc_180025E42
0x180025e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e12  cmp     rcx, r13
0x180025e15  jz      loc_180026053
0x180025e1b  test    byte ptr [rcx+1Ch], 8
0x180025e1f  jz      loc_180026053
0x180025e25  mov     edx, 17h
0x180025e2a  mov     r9d, esi
0x180025e2d  lea     r8, WPP_f4b69f1db01237bb0e3a2b08d8c2cb9e_Traceguids
0x180025e34  mov     rcx, [rcx+10h]
0x180025e38  call    WPP_SF_d
0x180025e3d  jmp     loc_180026053
0x180025e42  lea     rdx, qword_18003FFE0; IfSpec
0x180025e49  mov     rcx, [rsp+188h+Binding]; Binding
0x180025e4e  call    cs:__imp_RpcEpResolveBinding
0x180025e55  nop     dword ptr [rax+rax+00h]
0x180025e5a  mov     esi, eax
0x180025e5c  test    eax, eax
0x180025e5e  jz      short loc_180025E84
0x180025e60  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e67  cmp     rcx, r13
0x180025e6a  jz      loc_180026053
0x180025e70  test    byte ptr [rcx+1Ch], 8
0x180025e74  jz      loc_180026053
0x180025e7a  mov     edx, 18h
0x180025e7f  mov     r9d, eax
0x180025e82  jmp     short loc_180025E2D
0x180025e84  mov     [rsp+188h+var_68.Version], 1
0x180025e8f  mov     [rsp+188h+var_68.Capabilities], 1
0x180025e9a  mov     [rsp+188h+var_68.IdentityTracking], 1
0x180025ea5  mov     [rsp+188h+var_68.ImpersonationType], 3
0x180025eb0  xor     edx, edx; Val
0x180025eb2  lea     r8d, [rdx+48h]; Size
0x180025eb6  lea     rcx, [rsp+188h+AuthIdentity]; void *
0x180025ebe  call    memset_0
0x180025ec3  mov     [rsp+188h+AuthIdentity], 200h
0x180025ece  mov     [rsp+188h+var_B4], 48h ; 'H'
0x180025ed9  lea     rax, aKerberosNtlm; "Kerberos,NTLM"
0x180025ee0  mov     [rsp+188h+var_80], rax
0x180025ee8  mov     [rsp+188h+var_78], 0Dh
0x180025ef3  mov     [rsp+188h+var_84], 2
0x180025efe  lea     rax, [rsp+188h+var_68]
0x180025f06  mov     [rsp+188h+SecurityQOS], rax; SecurityQOS
0x180025f0b  mov     dword ptr [rsp+188h+StringBinding], edi; AuthzSvc
0x180025f0f  lea     rax, [rsp+188h+AuthIdentity]
0x180025f17  mov     [rsp+188h+Options], rax; AuthIdentity
0x180025f1c  mov     r9d, 9; AuthnSvc
0x180025f22  lea     r8d, [r9-3]; AuthnLevel
0x180025f26  mov     rdx, r14; ServerPrincName
0x180025f29  mov     rcx, [rsp+188h+Binding]; Binding
0x180025f2e  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180025f35  nop     dword ptr [rax+rax+00h]
0x180025f3a  mov     esi, eax
0x180025f3c  test    eax, eax
0x180025f3e  jz      short loc_180025F64
0x180025f40  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f47  cmp     rcx, r13
0x180025f4a  jz      loc_180026053
0x180025f50  test    byte ptr [rcx+1Ch], 8
0x180025f54  jz      loc_180026053
0x180025f5a  mov     edx, 19h
0x180025f5f  jmp     loc_180025E7F
0x180025f64  mov     [rsp+188h+var_D8], rdi
0x180025f6c  mov     [rsp+188h+var_140], edi
0x180025f70  mov     rax, [rsp+188h+var_E0]
0x180025f78  mov     [rsp+188h+var_148], rax
0x180025f7d  mov     rax, [rsp+188h+var_E8]
0x180025f85  mov     [rsp+188h+var_150], rax
0x180025f8a  mov     eax, [rsp+188h+arg_28]
0x180025f91  mov     dword ptr [rsp+188h+SecurityQOS], eax
0x180025f95  mov     rax, [rsp+188h+var_F0]
0x180025f9d  mov     [rsp+188h+StringBinding], rax
0x180025fa2  mov     rax, [rsp+188h+var_F8]
0x180025faa  mov     [rsp+188h+Options], rax
0x180025faf  mov     r9, [rsp+188h+Binding]
0x180025fb4  xor     r8d, r8d; pReturnValue
0x180025fb7  xor     edx, edx; nProcNum
0x180025fb9  lea     rcx, pProxyInfo; pProxyInfo
0x180025fc0  call    cs:__imp_NdrClientCall3
0x180025fc7  nop     dword ptr [rax+rax+00h]
0x180025fcc  mov     rbx, rax
  ... truncated ...
```

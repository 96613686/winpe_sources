# GetTsgServerCert(ulong,ulong,ushort const *,ulong,ulong)

- ea: `0x14002bb28`
- end: `0x14002bfc6`
- name: `?GetTsgServerCert@@YAPEAU_CERT_CONTEXT@@KKPEBGKK@Z`
- size: `1182`
- prototype: `struct _CERT_CONTEXT *__fastcall(unsigned int, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14002b578`

## callees

- `0x140008a34`
- `0x14000b7d8`
- `0x14000d078`
- `0x14002bb28`
- `0x14009ea90`
- `0x14009eb18`
- `0x14010fd18`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002bd0a`
- `KERNEL32!GetLastError` at `0x14002bd7e`
- `KERNEL32!GetLastError` at `0x14002be30`
- `KERNEL32!GetLastError` at `0x14002bef9`
- `KERNEL32!GetLastError` at `0x14002bd0a`
- `KERNEL32!GetLastError` at `0x14002bd7e`
- `KERNEL32!GetLastError` at `0x14002be30`
- `KERNEL32!GetLastError` at `0x14002bef9`
- `WINHTTP!WinHttpQueryOption` at `0x14002bee6`
- `WINHTTP!WinHttpQueryOption` at `0x14002bee6`
- `WINHTTP!WinHttpOpen` at `0x14002bcf6`
- `WINHTTP!WinHttpOpen` at `0x14002bcf6`
- `WINHTTP!WinHttpConnect` at `0x14002bd70`
- `WINHTTP!WinHttpConnect` at `0x14002bd70`
- `WINHTTP!WinHttpOpenRequest` at `0x14002be22`
- `WINHTTP!WinHttpOpenRequest` at `0x14002be22`
- `WINHTTP!WinHttpSendRequest` at `0x14002bece`
- `WINHTTP!WinHttpSendRequest` at `0x14002bece`
- `WINHTTP!WinHttpCloseHandle` at `0x14002bf6a`
- `WINHTTP!WinHttpCloseHandle` at `0x14002bf78`
- `WINHTTP!WinHttpCloseHandle` at `0x14002bf86`
- `WINHTTP!WinHttpCloseHandle` at `0x14002bf6a`
- `WINHTTP!WinHttpCloseHandle` at `0x14002bf78`
- `WINHTTP!WinHttpCloseHandle` at `0x14002bf86`

## string_xrefs

- `0x14002bccc`: `StringCchCopy failed`
- `0x14002bd55`: `WinHttpOpen failed`
- `0x14002be76`: `WinHttpOpenRequest failed`

## pseudocode

```c
struct _CERT_CONTEXT *__fastcall GetTsgServerCert(
        unsigned int a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5)
{
  int EffectiveSettings; // eax
  signed int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  int PortNumberFromServerName; // eax
  INTERNET_PORT v11; // di
  int ServerNameFromFullAddress; // eax
  int v13; // eax
  void *v14; // r14
  signed int LastError; // eax
  void *v16; // rsi
  signed int v17; // eax
  signed int v18; // ebx
  unsigned int v19; // eax
  void *v20; // rdi
  signed int v21; // eax
  signed int v22; // ebx
  unsigned int v23; // eax
  signed int v24; // eax
  signed int v25; // ebx
  unsigned int v26; // eax
  unsigned __int16 *v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v29; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v30; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwBufferLength; // [rsp+58h] [rbp-A8h] BYREF
  __int64 Buffer; // [rsp+60h] [rbp-A0h] BYREF
  struct RdpXInterfaceGatewayProfile *v33; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pswzServerName[256]; // [rsp+70h] [rbp-90h] BYREF

  v30 = a2;
  v28 = a3;
  v29 = a4;
  Buffer = 0;
  dwBufferLength = 8;
  v33 = 0;
  EffectiveSettings = CTscProxyUtil::GetEffectiveSettings(a1, a5, &v30, (const unsigned __int16 **)&v28, &v29, &v33);
  LOBYTE(v6) = EffectiveSettings;
  if ( EffectiveSettings < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 10;
      v9 = "CTscProxyUtil::GetEffectiveSettings failed";
LABEL_6:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)WPP_926b5def226a3d724013ee6627af6987_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v9,
        v6);
      goto LABEL_57;
    }
    goto LABEL_57;
  }
  PortNumberFromServerName = CUT::GetPortNumberFromServerName(v28);
  v11 = PortNumberFromServerName;
  if ( PortNumberFromServerName == -1 )
  {
    v13 = StringCchCopyW(pswzServerName, 0x100u, v28);
    LOBYTE(v6) = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 12;
        v9 = "StringCchCopy failed";
        goto LABEL_6;
      }
      goto LABEL_57;
    }
    v11 = 443;
LABEL_19:
    v14 = WinHttpOpen(L"TSG connection", 1u, 0, 0, 0);
    if ( v14 )
      goto LABEL_27;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
    {
LABEL_27:
      v16 = WinHttpConnect(v14, pswzServerName, v11, 0);
      if ( v16 )
        goto LABEL_35;
      v17 = GetLastError();
      v18 = v17;
      if ( v17 > 0 )
        v18 = (unsigned __int16)v17 | 0x80070000;
      if ( v18 >= 0 )
      {
LABEL_35:
        v20 = WinHttpOpenRequest(v16, L"GET", 0, 0, 0, 0, 0x800000u);
        if ( v20 )
          goto LABEL_43;
        v21 = GetLastError();
        v22 = v21;
        if ( v21 > 0 )
          v22 = (unsigned __int16)v21 | 0x80070000;
        if ( v22 >= 0 )
        {
LABEL_43:
          WinHttpSendRequest(v20, 0, 0, 0, 0, 0, 0);
          if ( !WinHttpQueryOption(v20, 0x4Eu, &Buffer, &dwBufferLength) )
          {
            Buffer = 0;
            v24 = GetLastError();
            v25 = v24;
            if ( v24 > 0 )
              v25 = (unsigned __int16)v24 | 0x80070000;
            if ( v25 < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v26 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                (unsigned int)WPP_926b5def226a3d724013ee6627af6987_Traceguids,
                v26,
                (__int64)"WinHttpQueryOption failed",
                v25);
            }
          }
          if ( v20 )
            WinHttpCloseHandle(v20);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v23 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_926b5def226a3d724013ee6627af6987_Traceguids,
            v23,
            (__int64)"WinHttpOpenRequest failed",
            v22);
        }
        if ( v16 )
          WinHttpCloseHandle(v16);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_926b5def226a3d724013ee6627af6987_Traceguids,
          v19,
          (__int64)"WinHttpConnect failed",
          v18);
      }
      if ( v14 )
        WinHttpCloseHandle(v14);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 13;
      v9 = "WinHttpOpen failed";
      goto LABEL_6;
    }
    goto LABEL_57;
  }
  ServerNameFromFullAddress = CUT::GetServerNameFromFullAddress(v28, pswzServerName, 0x100u);
  LOBYTE(v6) = ServerNameFromFullAddress;
  if ( ServerNameFromFullAddress >= 0 )
    goto LABEL_19;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 11;
    v9 = "CUT::GetServerNameFromFullAddress failed!";
    goto LABEL_6;
  }
LABEL_57:
  if ( v33 )
    (*(void (__fastcall **)(struct RdpXInterfaceGatewayProfile *))(*(_QWORD *)v33 + 8LL))(v33);
  return (struct _CERT_CONTEXT *)Buffer;
}

```

## disassembly

```asm
0x14002bb28  push    rbp
0x14002bb2a  push    rbx
0x14002bb2b  push    rsi
0x14002bb2c  push    rdi
0x14002bb2d  push    r13
0x14002bb2f  push    r14
0x14002bb31  lea     rbp, [rsp-188h]
0x14002bb39  sub     rsp, 288h
0x14002bb40  mov     rax, cs:__security_cookie
0x14002bb47  xor     rax, rsp
0x14002bb4a  mov     [rbp+1B0h+var_40], rax
0x14002bb51  lea     rax, [rsp+2B0h+var_248]
0x14002bb56  mov     [rsp+2B0h+var_260], edx
0x14002bb5a  mov     edx, [rbp+1B0h+arg_20]; unsigned int
0x14002bb60  mov     [rsp+2B0h+ppwszAcceptTypes], rax; struct RdpXInterfaceGatewayProfile **
0x14002bb65  lea     rax, [rsp+2B0h+var_268]
0x14002bb6a  mov     [rsp+2B0h+var_270], r8
0x14002bb6f  lea     r8, [rsp+2B0h+var_260]; unsigned int *
0x14002bb74  mov     [rsp+2B0h+var_268], r9d
0x14002bb79  lea     r9, [rsp+2B0h+var_270]; unsigned __int16 **
0x14002bb7e  mov     qword ptr [rsp+2B0h+dwFlags], rax; unsigned int *
0x14002bb83  mov     [rsp+2B0h+Buffer], 0
0x14002bb8c  mov     [rsp+2B0h+dwBufferLength], 8
0x14002bb94  mov     [rsp+2B0h+var_248], 0
0x14002bb9d  call    ?GetEffectiveSettings@CTscProxyUtil@@SAJKKPEAKPEAPEBG0PEAPEAURdpXInterfaceGatewayProfile@@@Z; CTscProxyUtil::GetEffectiveSettings(ulong,ulong,ulong *,ushort const * *,ulong *,RdpXInterfaceGatewayProfile * *)
0x14002bba2  mov     ebx, eax
0x14002bba4  test    eax, eax
0x14002bba6  jns     short loc_14002BC0C
0x14002bba8  mov     rdx, cs:WPP_GLOBAL_Control
0x14002bbaf  lea     rcx, WPP_GLOBAL_Control
0x14002bbb6  cmp     rdx, rcx
0x14002bbb9  jz      loc_14002BF8C
0x14002bbbf  test    byte ptr [rdx+1Ch], 8
0x14002bbc3  jz      loc_14002BF8C
0x14002bbc9  cmp     byte ptr [rdx+19h], 2
0x14002bbcd  jb      loc_14002BF8C
0x14002bbd3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002bbd8  mov     edx, 0Ah
0x14002bbdd  lea     rcx, aCtscproxyutilG; "CTscProxyUtil::GetEffectiveSettings fai"...
0x14002bbe4  mov     dword ptr [rsp+2B0h+ppwszAcceptTypes], ebx
0x14002bbe8  lea     r8, WPP_926b5def226a3d724013ee6627af6987_Traceguids
0x14002bbef  mov     qword ptr [rsp+2B0h+dwFlags], rcx
0x14002bbf4  mov     r9d, eax
0x14002bbf7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bbfe  mov     rcx, [rcx+10h]
0x14002bc02  call    WPP_SF_DsD
0x14002bc07  jmp     loc_14002BF8C
0x14002bc0c  mov     rcx, [rsp+2B0h+var_270]; unsigned __int16 *
0x14002bc11  call    ?GetPortNumberFromServerName@CUT@@SAHPEBG@Z; CUT::GetPortNumberFromServerName(ushort const *)
0x14002bc16  mov     edi, eax
0x14002bc18  cmp     eax, 0FFFFFFFFh
0x14002bc1b  jz      short loc_14002BC7D
0x14002bc1d  mov     rcx, [rsp+2B0h+var_270]; unsigned __int16 *
0x14002bc22  lea     rdx, [rsp+2B0h+pswzServerName]; unsigned __int16 *
0x14002bc27  mov     r8d, 100h; unsigned int
0x14002bc2d  call    ?GetServerNameFromFullAddress@CUT@@SAJPEBGPEAGK@Z; CUT::GetServerNameFromFullAddress(ushort const *,ushort *,ulong)
0x14002bc32  mov     ebx, eax
0x14002bc34  test    eax, eax
0x14002bc36  jns     loc_14002BCDD
0x14002bc3c  mov     rdx, cs:WPP_GLOBAL_Control
0x14002bc43  lea     rcx, WPP_GLOBAL_Control
0x14002bc4a  cmp     rdx, rcx
0x14002bc4d  jz      loc_14002BF8C
0x14002bc53  test    byte ptr [rdx+1Ch], 8
0x14002bc57  jz      loc_14002BF8C
0x14002bc5d  cmp     byte ptr [rdx+19h], 2
0x14002bc61  jb      loc_14002BF8C
0x14002bc67  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002bc6c  mov     edx, 0Bh
0x14002bc71  lea     rcx, aCutGetserverna; "CUT::GetServerNameFromFullAddress faile"...
0x14002bc78  jmp     loc_14002BBE4
0x14002bc7d  mov     r8, [rsp+2B0h+var_270]; unsigned __int16 *
0x14002bc82  lea     rcx, [rsp+2B0h+pswzServerName]; unsigned __int16 *
0x14002bc87  mov     edx, 100h; unsigned __int64
0x14002bc8c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002bc91  mov     ebx, eax
0x14002bc93  test    eax, eax
0x14002bc95  jns     short loc_14002BCD8
0x14002bc97  mov     rdx, cs:WPP_GLOBAL_Control
0x14002bc9e  lea     rcx, WPP_GLOBAL_Control
0x14002bca5  cmp     rdx, rcx
0x14002bca8  jz      loc_14002BF8C
0x14002bcae  test    byte ptr [rdx+1Ch], 8
0x14002bcb2  jz      loc_14002BF8C
0x14002bcb8  cmp     byte ptr [rdx+19h], 2
0x14002bcbc  jb      loc_14002BF8C
0x14002bcc2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002bcc7  mov     edx, 0Ch
0x14002bccc  lea     rcx, aStringcchcopyF_1; "StringCchCopy failed"
0x14002bcd3  jmp     loc_14002BBE4
0x14002bcd8  mov     edi, 1BBh
0x14002bcdd  xor     r9d, r9d; pszProxyBypassW
0x14002bce0  mov     [rsp+2B0h+dwFlags], 0; dwFlags
0x14002bce8  xor     r8d, r8d; pszProxyW
0x14002bceb  lea     rcx, pszAgentW; "TSG connection"
0x14002bcf2  lea     edx, [r9+1]; dwAccessType
0x14002bcf6  call    cs:__imp_WinHttpOpen
0x14002bcfc  mov     r14, rax
0x14002bcff  mov     r13d, 80070000h
0x14002bd05  test    rax, rax
0x14002bd08  jnz     short loc_14002BD61
0x14002bd0a  call    cs:__imp_GetLastError
0x14002bd10  mov     ebx, eax
0x14002bd12  test    eax, eax
0x14002bd14  jle     short loc_14002BD1C
0x14002bd16  movzx   ebx, ax
0x14002bd19  or      ebx, r13d
0x14002bd1c  test    ebx, ebx
0x14002bd1e  jns     short loc_14002BD61
0x14002bd20  mov     rax, cs:WPP_GLOBAL_Control
0x14002bd27  lea     rcx, WPP_GLOBAL_Control
0x14002bd2e  cmp     rax, rcx
0x14002bd31  jz      loc_14002BF8C
0x14002bd37  test    byte ptr [rax+1Ch], 8
0x14002bd3b  jz      loc_14002BF8C
0x14002bd41  cmp     byte ptr [rax+19h], 2
0x14002bd45  jb      loc_14002BF8C
0x14002bd4b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002bd50  mov     edx, 0Dh
0x14002bd55  lea     rcx, aWinhttpopenFai; "WinHttpOpen failed"
0x14002bd5c  jmp     loc_14002BBE4
0x14002bd61  movzx   r8d, di; nServerPort
0x14002bd65  lea     rdx, [rsp+2B0h+pswzServerName]; pswzServerName
0x14002bd6a  xor     r9d, r9d; dwReserved
0x14002bd6d  mov     rcx, r14; hSession
0x14002bd70  call    cs:__imp_WinHttpConnect
0x14002bd76  mov     rsi, rax
0x14002bd79  test    rax, rax
0x14002bd7c  jnz     short loc_14002BDF8
0x14002bd7e  call    cs:__imp_GetLastError
0x14002bd84  mov     ebx, eax
0x14002bd86  test    eax, eax
0x14002bd88  jle     short loc_14002BD90
0x14002bd8a  movzx   ebx, ax
0x14002bd8d  or      ebx, r13d
0x14002bd90  test    ebx, ebx
0x14002bd92  jns     short loc_14002BDF8
0x14002bd94  mov     rax, cs:WPP_GLOBAL_Control
0x14002bd9b  lea     rcx, WPP_GLOBAL_Control
0x14002bda2  cmp     rax, rcx
0x14002bda5  jz      loc_14002BF7E
0x14002bdab  test    byte ptr [rax+1Ch], 8
0x14002bdaf  jz      loc_14002BF7E
0x14002bdb5  cmp     byte ptr [rax+19h], 2
0x14002bdb9  jb      loc_14002BF7E
0x14002bdbf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002bdc4  lea     rcx, aWinhttpconnect_0; "WinHttpConnect failed"
0x14002bdcb  mov     dword ptr [rsp+2B0h+ppwszAcceptTypes], ebx
0x14002bdcf  mov     qword ptr [rsp+2B0h+dwFlags], rcx
0x14002bdd4  lea     r8, WPP_926b5def226a3d724013ee6627af6987_Traceguids
0x14002bddb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bde2  mov     edx, 0Eh
0x14002bde7  mov     r9d, eax
0x14002bdea  mov     rcx, [rcx+10h]
0x14002bdee  call    WPP_SF_DsD
0x14002bdf3  jmp     loc_14002BF7E
0x14002bdf8  mov     [rsp+2B0h+var_280], 800000h; dwFlags
0x14002be00  lea     rdx, pwszVerb; "GET"
0x14002be07  mov     [rsp+2B0h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x14002be10  xor     r9d, r9d; pwszVersion
0x14002be13  xor     r8d, r8d; pwszObjectName
0x14002be16  mov     qword ptr [rsp+2B0h+dwFlags], 0; pwszReferrer
0x14002be1f  mov     rcx, rsi; hConnect
0x14002be22  call    cs:__imp_WinHttpOpenRequest
0x14002be28  mov     rdi, rax
0x14002be2b  test    rax, rax
0x14002be2e  jnz     short loc_14002BEAA
0x14002be30  call    cs:__imp_GetLastError
0x14002be36  mov     ebx, eax
0x14002be38  test    eax, eax
0x14002be3a  jle     short loc_14002BE42
0x14002be3c  movzx   ebx, ax
0x14002be3f  or      ebx, r13d
0x14002be42  test    ebx, ebx
0x14002be44  jns     short loc_14002BEAA
0x14002be46  mov     rax, cs:WPP_GLOBAL_Control
0x14002be4d  lea     rcx, WPP_GLOBAL_Control
0x14002be54  cmp     rax, rcx
0x14002be57  jz      loc_14002BF70
0x14002be5d  test    byte ptr [rax+1Ch], 8
0x14002be61  jz      loc_14002BF70
0x14002be67  cmp     byte ptr [rax+19h], 2
0x14002be6b  jb      loc_14002BF70
0x14002be71  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002be76  lea     rcx, aWinhttpopenreq_0; "WinHttpOpenRequest failed"
0x14002be7d  mov     dword ptr [rsp+2B0h+ppwszAcceptTypes], ebx
0x14002be81  mov     qword ptr [rsp+2B0h+dwFlags], rcx
0x14002be86  lea     r8, WPP_926b5def226a3d724013ee6627af6987_Traceguids
0x14002be8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002be94  mov     edx, 0Fh
0x14002be99  mov     r9d, eax
0x14002be9c  mov     rcx, [rcx+10h]
0x14002bea0  call    WPP_SF_DsD
0x14002bea5  jmp     loc_14002BF70
0x14002beaa  mov     qword ptr [rsp+2B0h+var_280], 0; dwContext
0x14002beb3  xor     r9d, r9d; lpOptional
0x14002beb6  mov     dword ptr [rsp+2B0h+ppwszAcceptTypes], 0; dwTotalLength
0x14002bebe  xor     r8d, r8d; dwHeadersLength
0x14002bec1  xor     edx, edx; lpszHeaders
0x14002bec3  mov     [rsp+2B0h+dwFlags], 0; dwOptionalLength
0x14002becb  mov     rcx, rdi; hRequest
0x14002bece  call    cs:__imp_WinHttpSendRequest
0x14002bed4  lea     r9, [rsp+2B0h+dwBufferLength]; lpdwBufferLength
0x14002bed9  mov     edx, 4Eh ; 'N'; dwOption
0x14002bede  lea     r8, [rsp+2B0h+Buffer]; lpBuffer
0x14002bee3  mov     rcx, rdi; hInternet
0x14002bee6  call    cs:__imp_WinHttpQueryOption
0x14002beec  test    eax, eax
0x14002beee  jnz     short loc_14002BF62
0x14002bef0  mov     [rsp+2B0h+Buffer], 0
0x14002bef9  call    cs:__imp_GetLastError
0x14002beff  mov     ebx, eax
0x14002bf01  test    eax, eax
0x14002bf03  jle     short loc_14002BF0B
0x14002bf05  movzx   ebx, ax
0x14002bf08  or      ebx, r13d
0x14002bf0b  test    ebx, ebx
0x14002bf0d  jns     short loc_14002BF62
0x14002bf0f  mov     rax, cs:WPP_GLOBAL_Control
0x14002bf16  lea     rcx, WPP_GLOBAL_Control
0x14002bf1d  cmp     rax, rcx
0x14002bf20  jz      short loc_14002BF62
0x14002bf22  test    byte ptr [rax+1Ch], 8
0x14002bf26  jz      short loc_14002BF62
0x14002bf28  cmp     byte ptr [rax+19h], 2
0x14002bf2c  jb      short loc_14002BF62
0x14002bf2e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002bf33  lea     rcx, aWinhttpqueryop_0; "WinHttpQueryOption failed"
0x14002bf3a  mov     dword ptr [rsp+2B0h+ppwszAcceptTypes], ebx
0x14002bf3e  mov     qword ptr [rsp+2B0h+dwFlags], rcx
0x14002bf43  lea     r8, WPP_926b5def226a3d724013ee6627af6987_Traceguids
0x14002bf4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bf51  mov     edx, 10h
0x14002bf56  mov     r9d, eax
0x14002bf59  mov     rcx, [rcx+10h]
0x14002bf5d  call    WPP_SF_DsD
0x14002bf62  test    rdi, rdi
0x14002bf65  jz      short loc_14002BF70
0x14002bf67  mov     rcx, rdi; hInternet
0x14002bf6a  call    cs:__imp_WinHttpCloseHandle
0x14002bf70  test    rsi, rsi
0x14002bf73  jz      short loc_14002BF7E
0x14002bf75  mov     rcx, rsi; hInternet
0x14002bf78  call    cs:__imp_WinHttpCloseHandle
0x14002bf7e  test    r14, r14
0x14002bf81  jz      short loc_14002BF8C
0x14002bf83  mov     rcx, r14; hInternet
0x14002bf86  call    cs:__imp_WinHttpCloseHandle
0x14002bf8c  mov     rcx, [rsp+2B0h+var_248]
0x14002bf91  test    rcx, rcx
0x14002bf94  jz      short loc_14002BFA2
0x14002bf96  mov     rax, [rcx]
0x14002bf99  mov     rax, [rax+8]
0x14002bf9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bfa2  mov     rax, [rsp+2B0h+Buffer]
0x14002bfa7  mov     rcx, [rbp+1B0h+var_40]
0x14002bfae  xor     rcx, rsp; StackCookie
0x14002bfb1  call    __security_check_cookie
0x14002bfb6  add     rsp, 288h
0x14002bfbd  pop     r14
0x14002bfbf  pop     r13
0x14002bfc1  pop     rdi
0x14002bfc2  pop     rsi
0x14002bfc3  pop     rbx
0x14002bfc4  pop     rbp
0x14002bfc5  retn
```

# WinHttpHelper::MmpcConnectToServer(ushort const *,ushort const *,ulong)

- ea: `0x18001eb04`
- end: `0x18001ed66`
- name: `?MmpcConnectToServer@WinHttpHelper@@QEAAJPEBG0K@Z`
- size: `610`
- prototype: `int(WinHttpHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f594`

## callees

- `0x1800141b0`
- `0x180019ec0`
- `0x18001eb04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ebf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ed1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ebf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ed1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ec92`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ec92`
- `DMCmnUtils!DmImpersonate` at `0x18001eb7d`
- `DMCmnUtils!DmImpersonate` at `0x18001eb7d`
- `WINHTTP!WinHttpCloseHandle` at `0x18001ebe8`
- `WINHTTP!WinHttpCloseHandle` at `0x18001ed0d`
- `WINHTTP!WinHttpCloseHandle` at `0x18001ebe8`
- `WINHTTP!WinHttpCloseHandle` at `0x18001ed0d`
- `WINHTTP!WinHttpOpen` at `0x18001ebc0`
- `WINHTTP!WinHttpOpen` at `0x18001ebc0`
- `WINHTTP!WinHttpSetTimeouts` at `0x18001ecb3`
- `WINHTTP!WinHttpSetTimeouts` at `0x18001ecb3`
- `WINHTTP!WinHttpConnect` at `0x18001ece4`
- `WINHTTP!WinHttpConnect` at `0x18001ece4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinHttpHelper::MmpcConnectToServer(
        WinHttpHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  signed int v8; // ebx
  int v9; // eax
  HINTERNET v10; // rsi
  void *v11; // r15
  DWORD LastError; // ebx
  HINTERNET v13; // rsi
  void *v14; // r14
  DWORD v15; // ebx
  int nSendTimeout; // [rsp+40h] [rbp-20h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-10h] BYREF
  signed int v21; // [rsp+A0h] [rbp+40h] BYREF

  v21 = 0;
  v20[0] = "WinHttpHelper::MmpcConnectToServer";
  v20[1] = &v21;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, ConnectingToServerEvent, a3);
  if ( !a3 )
  {
    v8 = -2147024809;
LABEL_24:
    v21 = v8;
    goto LABEL_25;
  }
  if ( a2 )
  {
    v8 = 0;
    if ( *((_BYTE *)this + 40) || (v9 = DmImpersonate(a2), v8 = v9, v9 < 0) )
    {
      v21 = v8;
      if ( v8 < 0 )
        goto LABEL_25;
    }
    else
    {
      *((_BYTE *)this + 40) = 1;
      *((_BYTE *)this + 42) = 1;
      v21 = v9;
    }
  }
  v10 = WinHttpOpen(L"MMP-C Discovery Client", 4u, 0, 0, 0);
  v11 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    WinHttpCloseHandle(v11);
    SetLastError(LastError);
  }
  *(_QWORD *)this = v10;
  if ( !v10 )
    goto LABEL_13;
  nSendTimeout = 0;
  pcbData = 4;
  pdwType = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Enrollments",
          L"HTTPTimeout",
          0x10u,
          &pdwType,
          &nSendTimeout,
          &pcbData)
    && !WinHttpSetTimeouts(*(HINTERNET *)this, 0, nSendTimeout, nSendTimeout, nSendTimeout) )
  {
    goto LABEL_13;
  }
  if ( a4 > 0xFFFF )
  {
    v8 = -2147024362;
    goto LABEL_24;
  }
  v21 = 0;
  v13 = WinHttpConnect(*(HINTERNET *)this, a3, a4, 0);
  v14 = (void *)*((_QWORD *)this + 1);
  if ( v14 )
  {
    v15 = GetLastError();
    WinHttpCloseHandle(v14);
    SetLastError(v15);
  }
  *((_QWORD *)this + 1) = v13;
  if ( !v13 )
  {
LABEL_13:
    if ( (int)GetLastError() > 0 )
      v8 = (unsigned __int16)GetLastError() | 0x80190000;
    else
      v8 = GetLastError();
    goto LABEL_24;
  }
  v8 = v21;
LABEL_25:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001eb04  mov     [rsp-28h+arg_0], rbx
0x18001eb09  mov     [rsp-28h+arg_8], rsi
0x18001eb0e  push    rbp
0x18001eb0f  push    rdi
0x18001eb10  push    r12
0x18001eb12  push    r14
0x18001eb14  push    r15
0x18001eb16  mov     rbp, rsp
0x18001eb19  sub     rsp, 60h
0x18001eb1d  mov     r12d, r9d
0x18001eb20  mov     r14, r8
0x18001eb23  mov     rsi, rdx
0x18001eb26  mov     rdi, rcx
0x18001eb29  mov     [rbp+arg_10], 0
0x18001eb30  lea     rax, aWinhttphelperM; "WinHttpHelper::MmpcConnectToServer"
0x18001eb37  mov     [rbp+var_10], rax
0x18001eb3b  lea     rax, [rbp+arg_10]
0x18001eb3f  mov     [rbp+var_8], rax
0x18001eb43  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18001eb4a  jz      short loc_18001EB5F
0x18001eb4c  lea     rdx, ConnectingToServerEvent
0x18001eb53  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18001eb5a  call    McTemplateU0z_EventWriteTransfer
0x18001eb5f  test    r14, r14
0x18001eb62  jnz     short loc_18001EB6E
0x18001eb64  mov     ebx, 80070057h
0x18001eb69  jmp     loc_18001ED3E
0x18001eb6e  test    rsi, rsi
0x18001eb71  jz      short loc_18001EBA7
0x18001eb73  xor     ebx, ebx
0x18001eb75  cmp     [rdi+28h], bl
0x18001eb78  jnz     short loc_18001EB9C
0x18001eb7a  mov     rcx, rsi
0x18001eb7d  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18001eb84  nop     dword ptr [rax+rax+00h]
0x18001eb89  mov     ebx, eax
0x18001eb8b  test    eax, eax
0x18001eb8d  js      short loc_18001EB9C
0x18001eb8f  mov     byte ptr [rdi+28h], 1
0x18001eb93  mov     byte ptr [rdi+2Ah], 1
0x18001eb97  mov     [rbp+arg_10], eax
0x18001eb9a  jmp     short loc_18001EBA7
0x18001eb9c  mov     [rbp+arg_10], ebx
0x18001eb9f  test    ebx, ebx
0x18001eba1  js      loc_18001ED41
0x18001eba7  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18001ebaf  xor     r9d, r9d; pszProxyBypassW
0x18001ebb2  xor     r8d, r8d; pszProxyW
0x18001ebb5  lea     edx, [r9+4]; dwAccessType
0x18001ebb9  lea     rcx, aMmpCDiscoveryC; "MMP-C Discovery Client"
0x18001ebc0  call    cs:__imp_WinHttpOpen
0x18001ebc7  nop     dword ptr [rax+rax+00h]
0x18001ebcc  mov     rsi, rax
0x18001ebcf  mov     r15, [rdi]
0x18001ebd2  test    r15, r15
0x18001ebd5  jz      short loc_18001EC02
0x18001ebd7  call    cs:__imp_GetLastError
0x18001ebde  nop     dword ptr [rax+rax+00h]
0x18001ebe3  mov     ebx, eax
0x18001ebe5  mov     rcx, r15; hInternet
0x18001ebe8  call    cs:__imp_WinHttpCloseHandle
0x18001ebef  nop     dword ptr [rax+rax+00h]
0x18001ebf4  mov     ecx, ebx; dwErrCode
0x18001ebf6  call    cs:__imp_SetLastError
0x18001ebfd  nop     dword ptr [rax+rax+00h]
0x18001ec02  mov     [rdi], rsi
0x18001ec05  test    rsi, rsi
0x18001ec08  jnz     short loc_18001EC47
0x18001ec0a  call    cs:__imp_GetLastError
0x18001ec11  nop     dword ptr [rax+rax+00h]
0x18001ec16  test    eax, eax
0x18001ec18  jg      short loc_18001EC2D
0x18001ec1a  call    cs:__imp_GetLastError
0x18001ec21  nop     dword ptr [rax+rax+00h]
0x18001ec26  mov     ebx, eax
0x18001ec28  jmp     loc_18001ED3E
0x18001ec2d  call    cs:__imp_GetLastError
0x18001ec34  nop     dword ptr [rax+rax+00h]
0x18001ec39  movzx   ebx, ax
0x18001ec3c  or      ebx, 80190000h
0x18001ec42  jmp     loc_18001ED3E
0x18001ec47  mov     [rbp+nSendTimeout], 0
0x18001ec4e  mov     [rbp+var_1C], 4
0x18001ec55  mov     [rbp+pdwType], 0
0x18001ec5c  lea     rax, [rbp+var_1C]
0x18001ec60  mov     [rsp+60h+pcbData], rax; pcbData
0x18001ec65  lea     rax, [rbp+nSendTimeout]
0x18001ec69  mov     [rsp+60h+pvData], rax; pvData
0x18001ec6e  lea     rax, [rbp+pdwType]
0x18001ec72  mov     qword ptr [rsp+60h+dwFlags], rax; pdwType
0x18001ec77  mov     r9d, 10h; dwFlags
0x18001ec7d  lea     r8, Value; "HTTPTimeout"
0x18001ec84  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Enrollments"
0x18001ec8b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ec92  call    cs:__imp_RegGetValueW
0x18001ec99  nop     dword ptr [rax+rax+00h]
0x18001ec9e  test    eax, eax
0x18001eca0  jnz     short loc_18001ECC7
0x18001eca2  mov     r8d, [rbp+nSendTimeout]; nConnectTimeout
0x18001eca6  mov     [rsp+60h+dwFlags], r8d; nReceiveTimeout
0x18001ecab  mov     r9d, r8d; nSendTimeout
0x18001ecae  xor     edx, edx; nResolveTimeout
0x18001ecb0  mov     rcx, [rdi]; hInternet
0x18001ecb3  call    cs:__imp_WinHttpSetTimeouts
0x18001ecba  nop     dword ptr [rax+rax+00h]
0x18001ecbf  test    eax, eax
0x18001ecc1  jz      loc_18001EC0A
0x18001ecc7  cmp     r12d, 0FFFFh
0x18001ecce  ja      short loc_18001ED39
0x18001ecd0  mov     [rbp+arg_10], 0
0x18001ecd7  xor     r9d, r9d; dwReserved
0x18001ecda  movzx   r8d, r12w; nServerPort
0x18001ecde  mov     rdx, r14; pswzServerName
0x18001ece1  mov     rcx, [rdi]; hSession
0x18001ece4  call    cs:__imp_WinHttpConnect
0x18001eceb  nop     dword ptr [rax+rax+00h]
0x18001ecf0  mov     rsi, rax
0x18001ecf3  mov     r14, [rdi+8]
0x18001ecf7  test    r14, r14
0x18001ecfa  jz      short loc_18001ED27
0x18001ecfc  call    cs:__imp_GetLastError
0x18001ed03  nop     dword ptr [rax+rax+00h]
0x18001ed08  mov     ebx, eax
0x18001ed0a  mov     rcx, r14; hInternet
0x18001ed0d  call    cs:__imp_WinHttpCloseHandle
0x18001ed14  nop     dword ptr [rax+rax+00h]
0x18001ed19  mov     ecx, ebx; dwErrCode
0x18001ed1b  call    cs:__imp_SetLastError
0x18001ed22  nop     dword ptr [rax+rax+00h]
0x18001ed27  mov     [rdi+8], rsi
0x18001ed2b  test    rsi, rsi
0x18001ed2e  jz      loc_18001EC0A
0x18001ed34  mov     ebx, [rbp+arg_10]
0x18001ed37  jmp     short loc_18001ED41
0x18001ed39  mov     ebx, 80070216h
0x18001ed3e  mov     [rbp+arg_10], ebx
0x18001ed41  lea     rcx, [rbp+var_10]; this
0x18001ed45  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001ed4a  mov     eax, ebx
0x18001ed4c  lea     r11, [rsp+60h+var_s0]
0x18001ed51  mov     rbx, [r11+30h]
0x18001ed55  mov     rsi, [r11+38h]
0x18001ed59  mov     rsp, r11
0x18001ed5c  pop     r15
0x18001ed5e  pop     r14
0x18001ed60  pop     r12
0x18001ed62  pop     rdi
0x18001ed63  pop     rbp
0x18001ed64  retn
```

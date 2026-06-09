# LoadProtocolEngines

- ea: `0x180017cfc`
- end: `0x1800180cf`
- name: `LoadProtocolEngines`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b570`

## callees

- `0x180007b7c`
- `0x180017cfc`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180017f51`
- `KERNEL32!GetProcAddress` at `0x180017f6d`
- `KERNEL32!GetProcAddress` at `0x180017f89`
- `KERNEL32!GetProcAddress` at `0x180017fa5`
- `KERNEL32!GetProcAddress` at `0x180017fc1`
- `KERNEL32!GetProcAddress` at `0x180017f51`
- `KERNEL32!GetProcAddress` at `0x180017f6d`
- `KERNEL32!GetProcAddress` at `0x180017f89`
- `KERNEL32!GetProcAddress` at `0x180017fa5`
- `KERNEL32!GetProcAddress` at `0x180017fc1`
- `KERNEL32!LoadLibraryExW` at `0x180017f33`
- `KERNEL32!LoadLibraryExW` at `0x180017f33`
- `KERNEL32!GetLastError` at `0x180017fd5`
- `KERNEL32!GetLastError` at `0x180017fd5`
- `ADVAPI32!RegOpenKeyExW` at `0x180017d92`
- `ADVAPI32!RegOpenKeyExW` at `0x180017d92`
- `ADVAPI32!RegQueryValueExW` at `0x180017dda`
- `ADVAPI32!RegQueryValueExW` at `0x180017dda`
- `ADVAPI32!RegCloseKey` at `0x180017e83`
- `ADVAPI32!RegCloseKey` at `0x180017e83`
- `rtutils!RouterLogEventStringW` at `0x180018009`
- `rtutils!RouterLogEventStringW` at `0x180018009`

## string_xrefs

- `0x180017df5`: `LoadProtocolEngine: Protocol Engine [%ws] registry key [%ws] = %d.\n`
- `0x180017eab`: `LoadProtocolEngine: Protocol Engine [%ws] is disabled\n`
- `0x180017f47`: `InitializeProtocolEngine`
- `0x180017f66`: `UninitializeProtocolEngine`
- `0x180017f82`: `InitializeServerProtocolEngine`
- `0x180017f9e`: `UninitializeServerProtocolEngine`
- `0x180017fba`: `SendMessageToProtocolEngine`
- `0x18001801d`: `LoadProtocolEngine: Failed to load/get Protocol Engine entry points [%ws] [%ws] Error:%d\n`

## pseudocode

```c
__int64 LoadProtocolEngines()
{
  __int64 v0; // r14
  __int64 v1; // rbx
  const WCHAR *v2; // rdx
  wchar_t *v3; // r9
  wchar_t *v4; // r8
  __int64 v5; // r8
  __int64 v6; // rax
  wchar_t *v7; // r8
  __int64 v8; // r8
  __int64 v9; // rax
  HMODULE Library; // rax
  wchar_t *ProcAddress; // rax
  wchar_t *v12; // rax
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  DWORD LastError; // eax
  DWORD v17; // edi
  wchar_t *v18; // r9
  wchar_t *v19; // r8
  __int64 v20; // r8
  __int64 v21; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v28[16]; // [rsp+58h] [rbp-A8h] BYREF
  int *v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+70h] [rbp-90h]
  int v31; // [rsp+74h] [rbp-8Ch]
  int v32; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  hKey = 0;
  v0 = 0;
  v1 = 0;
  do
  {
    v2 = protocolEngineParams[v1];
    protocolEngineParams[v1 + 3] = 0;
    protocolEngineParams[v1 + 4] = 0;
    protocolEngineParams[v1 + 5] = 0;
    protocolEngineParams[v1 + 6] = 0;
    protocolEngineParams[v1 + 7] = 0;
    protocolEngineParams[v1 + 8] = 0;
    protocolEngineParams[v1 + 9] = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x20019u, &hKey) )
    {
      Type = 0;
      cbData = 4;
      *(_DWORD *)Data = 0;
      if ( !RegQueryValueExW(hKey, L"Disabled", 0, &Type, Data, &cbData) )
      {
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v3 = protocolEngineParams[v1];
          v4 = protocolEngineParams[v1 + 1];
          LODWORD(phkResult) = *(_DWORD *)Data;
          LOWORD(v32) = 0;
          FormatRRASErrorString(
            &v32,
            L"LoadProtocolEngine: Protocol Engine [%ws] registry key [%ws] = %d.\n",
            v4,
            v3,
            phkResult);
          if ( (byte_1800C8404 & 0x10) != 0 )
          {
            v6 = -1;
            do
              ++v6;
            while ( *(_WORD *)&v33[2 * v6 - 4] );
            v31 = 0;
            v30 = 2 * v6 + 2;
            v29 = &v32;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v5, 2, v28);
          }
        }
        LODWORD(protocolEngineParams[v1 + 3]) = *(_DWORD *)Data != 0;
      }
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( LODWORD(protocolEngineParams[v1 + 3]) )
    {
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v7 = protocolEngineParams[v1 + 1];
        LOWORD(v32) = 0;
        FormatRRASErrorString(&v32, L"LoadProtocolEngine: Protocol Engine [%ws] is disabled\n", v7);
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v9 = -1;
          do
            ++v9;
          while ( *(_WORD *)&v33[2 * v9 - 4] );
          v31 = 0;
          v30 = 2 * v9 + 2;
          v29 = &v32;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v8, 2, v28);
        }
      }
    }
    else
    {
      Library = LoadLibraryExW((&off_1800C7490)[v1], 0, 0x1000u);
      protocolEngineParams[v1 + 4] = (wchar_t *)Library;
      if ( !Library )
        goto LABEL_23;
      ProcAddress = (wchar_t *)GetProcAddress(Library, "InitializeProtocolEngine");
      protocolEngineParams[v1 + 5] = ProcAddress;
      if ( !ProcAddress )
        goto LABEL_23;
      v12 = (wchar_t *)GetProcAddress((HMODULE)protocolEngineParams[v1 + 4], "UninitializeProtocolEngine");
      protocolEngineParams[v1 + 6] = v12;
      if ( !v12
        || (v13 = (wchar_t *)GetProcAddress((HMODULE)protocolEngineParams[v1 + 4], "InitializeServerProtocolEngine"),
            (protocolEngineParams[v1 + 7] = v13) == 0)
        || (v14 = (wchar_t *)GetProcAddress((HMODULE)protocolEngineParams[v1 + 4], "UninitializeServerProtocolEngine"),
            (protocolEngineParams[v1 + 8] = v14) == 0)
        || (v15 = (wchar_t *)GetProcAddress((HMODULE)protocolEngineParams[v1 + 4], "SendMessageToProtocolEngine"),
            (protocolEngineParams[v1 + 9] = v15) == 0) )
      {
LABEL_23:
        LastError = GetLastError();
        v17 = LastError;
        if ( dword_1800C84E4 )
          RouterLogEventStringW(hLogHandle, 1u, 0x4E5Fu, 1u, &(&off_1800C7490)[v1], LastError, 0);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v18 = protocolEngineParams[v1 + 2];
          v19 = protocolEngineParams[v1 + 1];
          LOWORD(v32) = 0;
          LODWORD(phkResult) = v17;
          FormatRRASErrorString(
            &v32,
            L"LoadProtocolEngine: Failed to load/get Protocol Engine entry points [%ws] [%ws] Error:%d\n",
            v19,
            v18,
            phkResult);
          if ( (byte_1800C8404 & 8) != 0 )
          {
            v21 = -1;
            do
              ++v21;
            while ( *(_WORD *)&v33[2 * v21 - 4] );
            v31 = 0;
            v30 = 2 * v21 + 2;
            v29 = &v32;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v20, 2, v28);
          }
        }
        LODWORD(protocolEngineParams[v1 + 3]) = 1;
      }
    }
    ++v0;
    v1 += 10;
  }
  while ( v0 != 3 );
  return 0;
}

```

## disassembly

```asm
0x180017cfc  push    rbp
0x180017cfe  push    rbx
0x180017cff  push    rsi
0x180017d00  push    rdi
0x180017d01  push    r12
0x180017d03  push    r14
0x180017d05  push    r15
0x180017d07  lea     rbp, [rsp-790h]
0x180017d0f  sub     rsp, 890h
0x180017d16  mov     rax, cs:__security_cookie
0x180017d1d  xor     rax, rsp
0x180017d20  mov     [rbp+7C0h+var_40], rax
0x180017d27  xor     r15d, r15d
0x180017d2a  lea     rcx, [rbp+7C0h+var_83C]; void *
0x180017d2e  xor     edx, edx; Val
0x180017d30  mov     [rbp+7C0h+var_840], r15d
0x180017d34  mov     r8d, 7FCh; Size
0x180017d3a  call    memset_0
0x180017d3f  mov     [rsp+8C0h+hKey], r15
0x180017d44  lea     r12, protocolEngineParams
0x180017d4b  mov     r14d, r15d
0x180017d4e  mov     ebx, r15d
0x180017d51  mov     rdx, [rbx+r12]; lpSubKey
0x180017d55  lea     rax, [rsp+8C0h+hKey]
0x180017d5a  mov     r9d, 20019h; samDesired
0x180017d60  mov     [rsp+8C0h+phkResult], rax; phkResult
0x180017d65  xor     r8d, r8d; ulOptions
0x180017d68  mov     [rbx+r12+18h], r15
0x180017d6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017d74  mov     [rbx+r12+20h], r15
0x180017d79  mov     [rbx+r12+28h], r15
0x180017d7e  mov     [rbx+r12+30h], r15
0x180017d83  mov     [rbx+r12+38h], r15
0x180017d88  mov     [rbx+r12+40h], r15
0x180017d8d  mov     [rbx+r12+48h], r15
0x180017d92  call    cs:__imp_RegOpenKeyExW
0x180017d98  test    eax, eax
0x180017d9a  jnz     loc_180017E8E
0x180017da0  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180017da5  lea     rax, [rsp+8C0h+cbData]
0x180017daa  mov     [rsp+8C0h+lpcbData], rax; lpcbData
0x180017daf  lea     r9, [rsp+8C0h+Type]; lpType
0x180017db4  lea     rax, [rsp+8C0h+Data]
0x180017db9  mov     [rsp+8C0h+Type], r15d
0x180017dbe  xor     r8d, r8d; lpReserved
0x180017dc1  mov     [rsp+8C0h+phkResult], rax; lpData
0x180017dc6  lea     rdx, aDisabled; "Disabled"
0x180017dcd  mov     [rsp+8C0h+cbData], 4
0x180017dd5  mov     dword ptr [rsp+8C0h+Data], r15d
0x180017dda  call    cs:__imp_RegQueryValueExW
0x180017de0  test    eax, eax
0x180017de2  jnz     loc_180017E7E
0x180017de8  test    cs:byte_1800C8404, 10h
0x180017def  jz      short loc_180017E6E
0x180017df1  mov     eax, dword ptr [rsp+8C0h+Data]
0x180017df5  lea     rdx, aLoadprotocolen_0; "LoadProtocolEngine: Protocol Engine [%w"...
0x180017dfc  mov     r9, [rbx+r12]
0x180017e00  lea     rcx, [rbp+7C0h+var_840]
0x180017e04  mov     r8, [rbx+r12+8]
0x180017e09  mov     dword ptr [rsp+8C0h+phkResult], eax
0x180017e0d  mov     word ptr [rbp+7C0h+var_840], r15w
0x180017e12  call    FormatRRASErrorString
0x180017e17  test    cs:byte_1800C8404, 10h
0x180017e1e  jz      short loc_180017E6E
0x180017e20  lea     rcx, [rbp+7C0h+var_840]
0x180017e24  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017e28  inc     rax
0x180017e2b  cmp     [rcx+rax*2], r15w
0x180017e30  jnz     short loc_180017E28
0x180017e32  lea     eax, ds:2[rax*2]
0x180017e39  mov     [rsp+8C0h+var_84C], r15d
0x180017e3e  lea     rcx, [rbp+7C0h+var_840]
0x180017e42  mov     [rsp+8C0h+var_850], eax
0x180017e46  lea     rax, [rsp+8C0h+var_868]
0x180017e4b  mov     [rsp+8C0h+var_858], rcx
0x180017e50  mov     r9d, 2
0x180017e56  mov     [rsp+8C0h+phkResult], rax
0x180017e5b  lea     rdx, RasDdmTraceInfo
0x180017e62  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017e69  call    McGenEventWrite_EventWriteTransfer
0x180017e6e  cmp     dword ptr [rsp+8C0h+Data], r15d
0x180017e73  mov     eax, r15d
0x180017e76  setnz   al
0x180017e79  mov     [rbx+r12+18h], eax
0x180017e7e  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180017e83  call    cs:__imp_RegCloseKey
0x180017e89  mov     [rsp+8C0h+hKey], r15
0x180017e8e  cmp     [rbx+r12+18h], r15d
0x180017e93  jz      loc_180017F20
0x180017e99  test    cs:byte_1800C8404, 10h
0x180017ea0  jz      loc_18001809B
0x180017ea6  mov     r8, [rbx+r12+8]
0x180017eab  lea     rdx, aLoadprotocolen; "LoadProtocolEngine: Protocol Engine [%w"...
0x180017eb2  lea     rcx, [rbp+7C0h+var_840]
0x180017eb6  mov     word ptr [rbp+7C0h+var_840], r15w
0x180017ebb  call    FormatRRASErrorString
0x180017ec0  test    cs:byte_1800C8404, 10h
0x180017ec7  jz      loc_18001809B
0x180017ecd  lea     rcx, [rbp+7C0h+var_840]
0x180017ed1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017ed5  inc     rax
0x180017ed8  cmp     [rcx+rax*2], r15w
0x180017edd  jnz     short loc_180017ED5
0x180017edf  lea     eax, ds:2[rax*2]
0x180017ee6  mov     [rsp+8C0h+var_84C], r15d
0x180017eeb  lea     rcx, [rbp+7C0h+var_840]
0x180017eef  mov     [rsp+8C0h+var_850], eax
0x180017ef3  lea     rax, [rsp+8C0h+var_868]
0x180017ef8  mov     [rsp+8C0h+var_858], rcx
0x180017efd  mov     r9d, 2
0x180017f03  mov     [rsp+8C0h+phkResult], rax
0x180017f08  lea     rdx, RasDdmTraceInfo
0x180017f0f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017f16  call    McGenEventWrite_EventWriteTransfer
0x180017f1b  jmp     loc_18001809B
0x180017f20  lea     rsi, [r12+10h]
0x180017f25  xor     edx, edx; hFile
0x180017f27  add     rsi, rbx
0x180017f2a  mov     r8d, 1000h; dwFlags
0x180017f30  mov     rcx, [rsi]; lpLibFileName
0x180017f33  call    cs:__imp_LoadLibraryExW
0x180017f39  mov     [rbx+r12+20h], rax
0x180017f3e  test    rax, rax
0x180017f41  jz      loc_180017FD5
0x180017f47  lea     rdx, aInitializeprot; "InitializeProtocolEngine"
0x180017f4e  mov     rcx, rax; hModule
0x180017f51  call    cs:__imp_GetProcAddress
0x180017f57  mov     [rbx+r12+28h], rax
0x180017f5c  test    rax, rax
0x180017f5f  jz      short loc_180017FD5
0x180017f61  mov     rcx, [rbx+r12+20h]; hModule
0x180017f66  lea     rdx, aUninitializepr; "UninitializeProtocolEngine"
0x180017f6d  call    cs:__imp_GetProcAddress
0x180017f73  mov     [rbx+r12+30h], rax
0x180017f78  test    rax, rax
0x180017f7b  jz      short loc_180017FD5
0x180017f7d  mov     rcx, [rbx+r12+20h]; hModule
0x180017f82  lea     rdx, aInitializeserv; "InitializeServerProtocolEngine"
0x180017f89  call    cs:__imp_GetProcAddress
0x180017f8f  mov     [rbx+r12+38h], rax
0x180017f94  test    rax, rax
0x180017f97  jz      short loc_180017FD5
0x180017f99  mov     rcx, [rbx+r12+20h]; hModule
0x180017f9e  lea     rdx, aUninitializese; "UninitializeServerProtocolEngine"
0x180017fa5  call    cs:__imp_GetProcAddress
0x180017fab  mov     [rbx+r12+40h], rax
0x180017fb0  test    rax, rax
0x180017fb3  jz      short loc_180017FD5
0x180017fb5  mov     rcx, [rbx+r12+20h]; hModule
0x180017fba  lea     rdx, aSendmessagetop; "SendMessageToProtocolEngine"
0x180017fc1  call    cs:__imp_GetProcAddress
0x180017fc7  mov     [rbx+r12+48h], rax
0x180017fcc  test    rax, rax
0x180017fcf  jnz     loc_18001809B
0x180017fd5  call    cs:__imp_GetLastError
0x180017fdb  cmp     cs:dword_1800C84E4, r15d
0x180017fe2  mov     edi, eax
0x180017fe4  jbe     short loc_18001800F
0x180017fe6  mov     rcx, cs:hLogHandle; hLogHandle
0x180017fed  mov     edx, 1; dwEventType
0x180017ff2  mov     [rsp+8C0h+dwErrorIndex], r15d; dwErrorIndex
0x180017ff7  mov     r9d, edx; dwSubStringCount
0x180017ffa  mov     dword ptr [rsp+8C0h+lpcbData], eax; dwErrorCode
0x180017ffe  mov     r8d, 4E5Fh; dwMessageId
0x180018004  mov     [rsp+8C0h+phkResult], rsi; plpszSubStringArray
0x180018009  call    cs:__imp_RouterLogEventStringW
0x18001800f  test    cs:byte_1800C8404, 8
0x180018016  jz      short loc_180018092
0x180018018  mov     r9, [rbx+r12+10h]
0x18001801d  lea     rdx, aLoadprotocolen_1; "LoadProtocolEngine: Failed to load/get "...
0x180018024  mov     r8, [rbx+r12+8]
0x180018029  lea     rcx, [rbp+7C0h+var_840]
0x18001802d  mov     word ptr [rbp+7C0h+var_840], r15w
0x180018032  mov     dword ptr [rsp+8C0h+phkResult], edi
0x180018036  call    FormatRRASErrorString
0x18001803b  test    cs:byte_1800C8404, 8
0x180018042  jz      short loc_180018092
0x180018044  lea     rcx, [rbp+7C0h+var_840]
0x180018048  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001804c  inc     rax
0x18001804f  cmp     [rcx+rax*2], r15w
0x180018054  jnz     short loc_18001804C
0x180018056  lea     eax, ds:2[rax*2]
0x18001805d  mov     [rsp+8C0h+var_84C], r15d
0x180018062  lea     rcx, [rbp+7C0h+var_840]
0x180018066  mov     [rsp+8C0h+var_850], eax
0x18001806a  lea     rax, [rsp+8C0h+var_868]
0x18001806f  mov     [rsp+8C0h+var_858], rcx
0x180018074  mov     r9d, 2
0x18001807a  mov     [rsp+8C0h+phkResult], rax
0x18001807f  lea     rdx, RasDdmTraceError
0x180018086  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001808d  call    McGenEventWrite_EventWriteTransfer
0x180018092  mov     dword ptr [rbx+r12+18h], 1
0x18001809b  inc     r14
0x18001809e  add     rbx, 50h ; 'P'
0x1800180a2  cmp     r14, 3
0x1800180a6  jnz     loc_180017D51
0x1800180ac  xor     eax, eax
0x1800180ae  mov     rcx, [rbp+7C0h+var_40]
0x1800180b5  xor     rcx, rsp; StackCookie
0x1800180b8  call    __security_check_cookie
0x1800180bd  add     rsp, 890h
0x1800180c4  pop     r15
0x1800180c6  pop     r14
0x1800180c8  pop     r12
0x1800180ca  pop     rdi
0x1800180cb  pop     rsi
0x1800180cc  pop     rbx
0x1800180cd  pop     rbp
0x1800180ce  retn
```

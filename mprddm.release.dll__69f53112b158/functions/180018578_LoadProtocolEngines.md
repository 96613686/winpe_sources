# LoadProtocolEngines

- ea: `0x180018578`
- end: `0x180018992`
- name: `LoadProtocolEngines`
- size: `1050`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bf40`

## callees

- `0x180007c0c`
- `0x180018578`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800187d6`
- `KERNEL32!GetProcAddress` at `0x1800187fa`
- `KERNEL32!GetProcAddress` at `0x18001881a`
- `KERNEL32!GetProcAddress` at `0x18001883a`
- `KERNEL32!GetProcAddress` at `0x18001885a`
- `KERNEL32!GetProcAddress` at `0x1800187d6`
- `KERNEL32!GetProcAddress` at `0x1800187fa`
- `KERNEL32!GetProcAddress` at `0x18001881a`
- `KERNEL32!GetProcAddress` at `0x18001883a`
- `KERNEL32!GetProcAddress` at `0x18001885a`
- `KERNEL32!LoadLibraryExW` at `0x1800187b3`
- `KERNEL32!LoadLibraryExW` at `0x1800187b3`
- `KERNEL32!GetLastError` at `0x180018873`
- `KERNEL32!GetLastError` at `0x180018873`
- `ADVAPI32!RegOpenKeyExW` at `0x18001860f`
- `ADVAPI32!RegOpenKeyExW` at `0x18001860f`
- `ADVAPI32!RegQueryValueExW` at `0x18001865d`
- `ADVAPI32!RegQueryValueExW` at `0x18001865d`
- `ADVAPI32!RegCloseKey` at `0x180018707`
- `ADVAPI32!RegCloseKey` at `0x180018707`
- `rtutils!RouterLogEventStringW` at `0x1800188c1`
- `rtutils!RouterLogEventStringW` at `0x1800188c1`

## string_xrefs

- `0x18001867e`: `LoadProtocolEngine: Protocol Engine [%ws] registry key [%ws] = %d.\n`
- `0x180018733`: `LoadProtocolEngine: Protocol Engine [%ws] is disabled\n`
- `0x1800187cc`: `InitializeProtocolEngine`
- `0x1800187f3`: `UninitializeProtocolEngine`
- `0x180018813`: `InitializeServerProtocolEngine`
- `0x180018833`: `UninitializeServerProtocolEngine`
- `0x180018853`: `SendMessageToProtocolEngine`
- `0x1800188da`: `LoadProtocolEngine: Failed to load/get Protocol Engine entry points [%ws] [%ws] Error:%d\n`

## pseudocode

```c
__int64 LoadProtocolEngines()
{
  unsigned int v0; // esi
  wchar_t **v1; // rbx
  const WCHAR *v2; // rdx
  wchar_t *v3; // r9
  wchar_t *v4; // r8
  __int64 v5; // r8
  __int64 v6; // rax
  wchar_t *v7; // r8
  __int64 v8; // r8
  __int64 v9; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  DWORD LastError; // edi
  wchar_t *v17; // r9
  wchar_t *v18; // r8
  __int64 v19; // r8
  __int64 v20; // rax
  PHKEY phkResult; // [rsp+28h] [rbp-E0h]
  BYTE Data[8]; // [rsp+48h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-ACh] BYREF
  _BYTE v27[16]; // [rsp+60h] [rbp-A8h] BYREF
  int *v28; // [rsp+70h] [rbp-98h]
  int v29; // [rsp+78h] [rbp-90h]
  int v30; // [rsp+7Ch] [rbp-8Ch]
  int v31; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v32[2044]; // [rsp+8Ch] [rbp-7Ch] BYREF

  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  hKey = 0;
  v0 = 0;
  v1 = protocolEngineParams;
  do
  {
    v2 = *v1;
    v1[3] = 0;
    v1[4] = 0;
    v1[5] = 0;
    v1[6] = 0;
    v1[7] = 0;
    v1[8] = 0;
    v1[9] = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x20019u, &hKey) )
    {
      Type = 0;
      cbData = 4;
      *(_DWORD *)Data = 0;
      if ( !RegQueryValueExW(hKey, L"Disabled", 0, &Type, Data, &cbData) )
      {
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          v3 = *v1;
          v4 = v1[1];
          LODWORD(phkResult) = *(_DWORD *)Data;
          LOWORD(v31) = 0;
          FormatRRASErrorString(
            &v31,
            L"LoadProtocolEngine: Protocol Engine [%ws] registry key [%ws] = %d.\n",
            v4,
            v3,
            phkResult);
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            v6 = -1;
            do
              ++v6;
            while ( *(_WORD *)&v32[2 * v6 - 4] );
            v30 = 0;
            v29 = 2 * v6 + 2;
            v28 = &v31;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v5, 2, v27);
          }
        }
        *((_DWORD *)v1 + 6) = *(_DWORD *)Data != 0;
      }
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( *((_DWORD *)v1 + 6) )
    {
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v7 = v1[1];
        LOWORD(v31) = 0;
        FormatRRASErrorString(&v31, L"LoadProtocolEngine: Protocol Engine [%ws] is disabled\n", v7);
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          v9 = -1;
          do
            ++v9;
          while ( *(_WORD *)&v32[2 * v9 - 4] );
          v30 = 0;
          v29 = 2 * v9 + 2;
          v28 = &v31;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v8, 2, v27);
        }
      }
    }
    else
    {
      Library = LoadLibraryExW(v1[2], 0, 0x1000u);
      v1[4] = (wchar_t *)Library;
      if ( !Library )
        goto LABEL_23;
      ProcAddress = GetProcAddress(Library, "InitializeProtocolEngine");
      v1[5] = (wchar_t *)ProcAddress;
      if ( !ProcAddress )
        goto LABEL_23;
      v12 = GetProcAddress((HMODULE)v1[4], "UninitializeProtocolEngine");
      v1[6] = (wchar_t *)v12;
      if ( !v12
        || (v13 = GetProcAddress((HMODULE)v1[4], "InitializeServerProtocolEngine"), (v1[7] = (wchar_t *)v13) == 0)
        || (v14 = GetProcAddress((HMODULE)v1[4], "UninitializeServerProtocolEngine"), (v1[8] = (wchar_t *)v14) == 0)
        || (v15 = GetProcAddress((HMODULE)v1[4], "SendMessageToProtocolEngine"), (v1[9] = (wchar_t *)v15) == 0) )
      {
LABEL_23:
        LastError = GetLastError();
        if ( dword_1800CF4E4 )
          RouterLogEventStringW(hLogHandle, 1u, 0x4E5Fu, 1u, &(&off_1800CE490)[10 * v0], LastError, 0);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v17 = v1[2];
          v18 = v1[1];
          LOWORD(v31) = 0;
          LODWORD(phkResult) = LastError;
          FormatRRASErrorString(
            &v31,
            L"LoadProtocolEngine: Failed to load/get Protocol Engine entry points [%ws] [%ws] Error:%d\n",
            v18,
            v17,
            phkResult);
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v20 = -1;
            do
              ++v20;
            while ( *(_WORD *)&v32[2 * v20 - 4] );
            v30 = 0;
            v29 = 2 * v20 + 2;
            v28 = &v31;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v19, 2, v27);
          }
        }
        *((_DWORD *)v1 + 6) = 1;
      }
    }
    ++v0;
    v1 += 10;
  }
  while ( v0 < 3 );
  return 0;
}

```

## disassembly

```asm
0x180018578  mov     rax, rsp
0x18001857b  mov     [rax+8], rbx
0x18001857f  mov     [rax+10h], rsi
0x180018583  mov     [rax+18h], rdi
0x180018587  push    rbp
0x180018588  push    r13
0x18001858a  push    r14
0x18001858c  lea     rbp, [rax-7A8h]
0x180018593  sub     rsp, 890h
0x18001859a  mov     rax, cs:__security_cookie
0x1800185a1  xor     rax, rsp
0x1800185a4  mov     [rbp+7A0h+var_20], rax
0x1800185ab  xor     r14d, r14d
0x1800185ae  lea     rcx, [rbp+7A0h+var_81C]; void *
0x1800185b2  xor     edx, edx; Val
0x1800185b4  mov     [rbp+7A0h+var_820], r14d
0x1800185b8  mov     r8d, 7FCh; Size
0x1800185be  call    memset_0
0x1800185c3  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800185c7  mov     [rsp+8A0h+hKey], r14
0x1800185cc  mov     esi, r14d
0x1800185cf  lea     rbx, protocolEngineParams
0x1800185d6  mov     rdx, [rbx]; lpSubKey
0x1800185d9  lea     rax, [rsp+8A0h+hKey]
0x1800185de  mov     r9d, 20019h; samDesired
0x1800185e4  mov     [rsp+8A0h+phkResult], rax; phkResult
0x1800185e9  xor     r8d, r8d; ulOptions
0x1800185ec  mov     [rbx+18h], r14
0x1800185f0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800185f7  mov     [rbx+20h], r14
0x1800185fb  mov     [rbx+28h], r14
0x1800185ff  mov     [rbx+30h], r14
0x180018603  mov     [rbx+38h], r14
0x180018607  mov     [rbx+40h], r14
0x18001860b  mov     [rbx+48h], r14
0x18001860f  call    cs:__imp_RegOpenKeyExW
0x180018616  nop     dword ptr [rax+rax+00h]
0x18001861b  test    eax, eax
0x18001861d  jnz     loc_180018718
0x180018623  mov     rcx, [rsp+8A0h+hKey]; hKey
0x180018628  lea     rax, [rsp+8A0h+cbData]
0x18001862d  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x180018632  lea     r9, [rsp+8A0h+Type]; lpType
0x180018637  lea     rax, [rsp+8A0h+Data]
0x18001863c  mov     [rsp+8A0h+Type], r14d
0x180018641  xor     r8d, r8d; lpReserved
0x180018644  mov     [rsp+8A0h+phkResult], rax; lpData
0x180018649  lea     rdx, aDisabled; "Disabled"
0x180018650  mov     [rsp+8A0h+cbData], 4
0x180018658  mov     dword ptr [rsp+8A0h+Data], r14d
0x18001865d  call    cs:__imp_RegQueryValueExW
0x180018664  nop     dword ptr [rax+rax+00h]
0x180018669  test    eax, eax
0x18001866b  jnz     loc_180018702
0x180018671  test    cs:byte_1800CF404, 10h
0x180018678  jz      short loc_1800186F4
0x18001867a  mov     eax, dword ptr [rsp+8A0h+Data]
0x18001867e  lea     rdx, aLoadprotocolen_0; "LoadProtocolEngine: Protocol Engine [%w"...
0x180018685  mov     r9, [rbx]
0x180018688  lea     rcx, [rbp+7A0h+var_820]
0x18001868c  mov     r8, [rbx+8]
0x180018690  mov     dword ptr [rsp+8A0h+phkResult], eax
0x180018694  mov     word ptr [rbp+7A0h+var_820], r14w
0x180018699  call    FormatRRASErrorString
0x18001869e  test    cs:byte_1800CF404, 10h
0x1800186a5  jz      short loc_1800186F4
0x1800186a7  lea     rcx, [rbp+7A0h+var_820]
0x1800186ab  mov     rax, r13
0x1800186ae  inc     rax
0x1800186b1  cmp     [rcx+rax*2], r14w
0x1800186b6  jnz     short loc_1800186AE
0x1800186b8  lea     eax, ds:2[rax*2]
0x1800186bf  mov     [rsp+8A0h+var_82C], r14d
0x1800186c4  lea     rcx, [rbp+7A0h+var_820]
0x1800186c8  mov     [rsp+8A0h+var_830], eax
0x1800186cc  lea     rax, [rsp+8A0h+var_848]
0x1800186d1  mov     [rsp+8A0h+var_838], rcx
0x1800186d6  mov     r9d, 2
0x1800186dc  mov     [rsp+8A0h+phkResult], rax
0x1800186e1  lea     rdx, RasDdmTraceInfo
0x1800186e8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800186ef  call    McGenEventWrite_EventWriteTransfer
0x1800186f4  cmp     dword ptr [rsp+8A0h+Data], r14d
0x1800186f9  mov     eax, r14d
0x1800186fc  setnz   al
0x1800186ff  mov     [rbx+18h], eax
0x180018702  mov     rcx, [rsp+8A0h+hKey]; hKey
0x180018707  call    cs:__imp_RegCloseKey
0x18001870e  nop     dword ptr [rax+rax+00h]
0x180018713  mov     [rsp+8A0h+hKey], r14
0x180018718  cmp     [rbx+18h], r14d
0x18001871c  jz      loc_1800187A7
0x180018722  test    cs:byte_1800CF404, 10h
0x180018729  jz      loc_180018954
0x18001872f  mov     r8, [rbx+8]
0x180018733  lea     rdx, aLoadprotocolen; "LoadProtocolEngine: Protocol Engine [%w"...
0x18001873a  lea     rcx, [rbp+7A0h+var_820]
0x18001873e  mov     word ptr [rbp+7A0h+var_820], r14w
0x180018743  call    FormatRRASErrorString
0x180018748  test    cs:byte_1800CF404, 10h
0x18001874f  jz      loc_180018954
0x180018755  lea     rcx, [rbp+7A0h+var_820]
0x180018759  mov     rax, r13
0x18001875c  inc     rax
0x18001875f  cmp     [rcx+rax*2], r14w
0x180018764  jnz     short loc_18001875C
0x180018766  lea     eax, ds:2[rax*2]
0x18001876d  mov     [rsp+8A0h+var_82C], r14d
0x180018772  lea     rcx, [rbp+7A0h+var_820]
0x180018776  mov     [rsp+8A0h+var_830], eax
0x18001877a  lea     rax, [rsp+8A0h+var_848]
0x18001877f  mov     [rsp+8A0h+var_838], rcx
0x180018784  mov     r9d, 2
0x18001878a  mov     [rsp+8A0h+phkResult], rax
0x18001878f  lea     rdx, RasDdmTraceInfo
0x180018796  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001879d  call    McGenEventWrite_EventWriteTransfer
0x1800187a2  jmp     loc_180018954
0x1800187a7  mov     rcx, [rbx+10h]; lpLibFileName
0x1800187ab  xor     edx, edx; hFile
0x1800187ad  mov     r8d, 1000h; dwFlags
0x1800187b3  call    cs:__imp_LoadLibraryExW
0x1800187ba  nop     dword ptr [rax+rax+00h]
0x1800187bf  mov     [rbx+20h], rax
0x1800187c3  test    rax, rax
0x1800187c6  jz      loc_180018873
0x1800187cc  lea     rdx, aInitializeprot; "InitializeProtocolEngine"
0x1800187d3  mov     rcx, rax; hModule
0x1800187d6  call    cs:__imp_GetProcAddress
0x1800187dd  nop     dword ptr [rax+rax+00h]
0x1800187e2  mov     [rbx+28h], rax
0x1800187e6  test    rax, rax
0x1800187e9  jz      loc_180018873
0x1800187ef  mov     rcx, [rbx+20h]; hModule
0x1800187f3  lea     rdx, aUninitializepr; "UninitializeProtocolEngine"
0x1800187fa  call    cs:__imp_GetProcAddress
0x180018801  nop     dword ptr [rax+rax+00h]
0x180018806  mov     [rbx+30h], rax
0x18001880a  test    rax, rax
0x18001880d  jz      short loc_180018873
0x18001880f  mov     rcx, [rbx+20h]; hModule
0x180018813  lea     rdx, aInitializeserv; "InitializeServerProtocolEngine"
0x18001881a  call    cs:__imp_GetProcAddress
0x180018821  nop     dword ptr [rax+rax+00h]
0x180018826  mov     [rbx+38h], rax
0x18001882a  test    rax, rax
0x18001882d  jz      short loc_180018873
0x18001882f  mov     rcx, [rbx+20h]; hModule
0x180018833  lea     rdx, aUninitializese; "UninitializeServerProtocolEngine"
0x18001883a  call    cs:__imp_GetProcAddress
0x180018841  nop     dword ptr [rax+rax+00h]
0x180018846  mov     [rbx+40h], rax
0x18001884a  test    rax, rax
0x18001884d  jz      short loc_180018873
0x18001884f  mov     rcx, [rbx+20h]; hModule
0x180018853  lea     rdx, aSendmessagetop; "SendMessageToProtocolEngine"
0x18001885a  call    cs:__imp_GetProcAddress
0x180018861  nop     dword ptr [rax+rax+00h]
0x180018866  mov     [rbx+48h], rax
0x18001886a  test    rax, rax
0x18001886d  jnz     loc_180018954
0x180018873  call    cs:__imp_GetLastError
0x18001887a  nop     dword ptr [rax+rax+00h]
0x18001887f  cmp     cs:dword_1800CF4E4, r14d
0x180018886  mov     edi, eax
0x180018888  jbe     short loc_1800188CD
0x18001888a  mov     ecx, esi
0x18001888c  lea     rax, off_1800CE490; "rasppp.dll"
0x180018893  mov     [rsp+8A0h+dwErrorIndex], r14d; dwErrorIndex
0x180018898  mov     r8d, 4E5Fh; dwMessageId
0x18001889e  mov     dword ptr [rsp+8A0h+lpcbData], edi; dwErrorCode
0x1800188a2  lea     rdx, [rcx+rcx*4]
0x1800188a6  mov     rcx, cs:hLogHandle; hLogHandle
0x1800188ad  shl     rdx, 4
0x1800188b1  add     rdx, rax
0x1800188b4  mov     [rsp+8A0h+phkResult], rdx; plpszSubStringArray
0x1800188b9  mov     edx, 1; dwEventType
0x1800188be  mov     r9d, edx; dwSubStringCount
0x1800188c1  call    cs:__imp_RouterLogEventStringW
0x1800188c8  nop     dword ptr [rax+rax+00h]
0x1800188cd  test    cs:byte_1800CF404, 8
0x1800188d4  jz      short loc_18001894D
0x1800188d6  mov     r9, [rbx+10h]
0x1800188da  lea     rdx, aLoadprotocolen_1; "LoadProtocolEngine: Failed to load/get "...
0x1800188e1  mov     r8, [rbx+8]
0x1800188e5  lea     rcx, [rbp+7A0h+var_820]
0x1800188e9  mov     word ptr [rbp+7A0h+var_820], r14w
0x1800188ee  mov     dword ptr [rsp+8A0h+phkResult], edi
0x1800188f2  call    FormatRRASErrorString
0x1800188f7  test    cs:byte_1800CF404, 8
0x1800188fe  jz      short loc_18001894D
0x180018900  lea     rcx, [rbp+7A0h+var_820]
0x180018904  mov     rax, r13
0x180018907  inc     rax
0x18001890a  cmp     [rcx+rax*2], r14w
0x18001890f  jnz     short loc_180018907
0x180018911  lea     eax, ds:2[rax*2]
0x180018918  mov     [rsp+8A0h+var_82C], r14d
0x18001891d  lea     rcx, [rbp+7A0h+var_820]
0x180018921  mov     [rsp+8A0h+var_830], eax
0x180018925  lea     rax, [rsp+8A0h+var_848]
0x18001892a  mov     [rsp+8A0h+var_838], rcx
0x18001892f  mov     r9d, 2
0x180018935  mov     [rsp+8A0h+phkResult], rax
0x18001893a  lea     rdx, RasDdmTraceError
0x180018941  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180018948  call    McGenEventWrite_EventWriteTransfer
0x18001894d  mov     dword ptr [rbx+18h], 1
0x180018954  inc     esi
0x180018956  add     rbx, 50h ; 'P'
0x18001895a  cmp     esi, 3
0x18001895d  jb      loc_1800185D6
0x180018963  xor     eax, eax
0x180018965  mov     rcx, [rbp+7A0h+var_20]
0x18001896c  xor     rcx, rsp; StackCookie
0x18001896f  call    __security_check_cookie
0x180018974  lea     r11, [rsp+8A0h+var_10]
0x18001897c  mov     rbx, [r11+20h]
0x180018980  mov     rsi, [r11+28h]
0x180018984  mov     rdi, [r11+30h]
0x180018988  mov     rsp, r11
0x18001898b  pop     r14
0x18001898d  pop     r13
0x18001898f  pop     rbp
0x180018990  retn
```

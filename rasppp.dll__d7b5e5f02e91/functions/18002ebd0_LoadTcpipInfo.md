# LoadTcpipInfo

- ea: `0x18002ebd0`
- end: `0x18002ef03`
- name: `LoadTcpipInfo`
- size: `819`
- prototype: `__int64 __fastcall(__int64 *, const wchar_t *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18001bab4`
- `0x18001dcb0`
- `0x180020920`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180020b1c`
- `0x18002b0dc`
- `0x18002e2a4`
- `0x18002ebd0`
- `0x18002ef0c`
- `0x18002f22c`
- `0x18003230c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002eccb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ed6f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002eccb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ed6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ecdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ecdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002eddb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ee6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002eddb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ee6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eea7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eebd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eea7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eebd`

## string_xrefs

- `0x18002ee14`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002ee2d`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002edbc`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18002ee59`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall LoadTcpipInfo(__int64 *a1, const wchar_t *a2, int a3)
{
  unsigned int TcpipParam; // ebx
  __int64 v7; // rdx
  const wchar_t *v8; // r8
  HLOCAL v9; // rax
  DWORD LastError; // eax
  __int64 v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rbx
  wchar_t *v14; // rcx
  const WCHAR *v15; // rdi
  unsigned int v16; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKey = 0;
  phkResult = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_18004D648 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        xmmword_18004D648,
        L"LoadTcpipInfo");
  }
  else
  {
    TraceHlp("LoadTcpipInfo");
  }
  if ( a2 )
  {
    *a1 = 0;
    v9 = LocalAlloc(0x40u, 0x80u);
    *a1 = (__int64)v9;
    if ( !v9 )
      goto LABEL_12;
    memset_0(v9, 0, 0x80u);
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    v13 = *a1;
    *(_QWORD *)(v13 + 8) = LocalAlloc(0x40u, 2 * v12 + 2);
    v14 = *(wchar_t **)(*a1 + 8);
    if ( !v14 )
    {
LABEL_12:
      LastError = GetLastError();
      TcpipParam = LastError;
      if ( !gIsIphlpEtwTracingAvailable )
      {
        TraceHlp("LocalAlloc failed and returned %d");
        goto LABEL_34;
      }
      if ( !qword_18004D640 )
        goto LABEL_34;
      LOWORD(v20) = 0;
      FormatRRASErrorString((wchar_t *)&v20, L"LocalAlloc failed and returned %d", LastError);
      goto LABEL_15;
    }
    TcpipParam = 0;
    do
      ++v11;
    while ( a2[v11] );
    StringCchCopyW(v14, v11 + 1, a2);
    if ( a3 )
      goto LABEL_34;
    v15 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
    v16 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
            0,
            0x20019u,
            &hKey);
    TcpipParam = v16;
    if ( v16 )
    {
      if ( v16 != 2 )
      {
LABEL_25:
        if ( !gIsIphlpEtwTracingAvailable )
        {
          TraceHlp("RegOpenKeyEx(%ws) failed and returned %d");
          goto LABEL_34;
        }
        if ( !qword_18004D640 )
          goto LABEL_34;
        LOWORD(v20) = 0;
        FormatRRASErrorString((wchar_t *)&v20, L"RegOpenKeyEx(%ws) failed and returned %d", v15, v16);
LABEL_15:
        v7 = qword_18004D640;
        v8 = (const wchar_t *)&v20;
LABEL_9:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(gIphlpEtwContext, v7, v8);
        goto LABEL_34;
      }
    }
    else
    {
      TcpipParam = LoadTcpipParam(hKey);
      if ( TcpipParam )
        goto LABEL_34;
    }
    v15 = L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces";
    v16 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces",
            0,
            0x20019u,
            &phkResult);
    TcpipParam = v16;
    if ( !v16 )
    {
      TcpipParam = LoadWinsParam(phkResult, *a1);
      goto LABEL_34;
    }
    if ( v16 == 2 )
    {
      TcpipParam = 0;
      goto LABEL_34;
    }
    goto LABEL_25;
  }
  TcpipParam = 87;
  if ( gIsIphlpEtwTracingAvailable )
  {
    v7 = qword_18004D640;
    if ( !qword_18004D640 )
      goto LABEL_34;
    v8 = L"wszAdapterName is NULL";
    goto LABEL_9;
  }
  TraceHlp("wszAdapterName is NULL");
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( TcpipParam )
    FreeTcpipInfo(a1);
  return TcpipParam;
}

```

## disassembly

```asm
0x18002ebd0  mov     [rsp-8+arg_10], rbx
0x18002ebd5  mov     [rsp-8+arg_18], rsi
0x18002ebda  push    rbp
0x18002ebdb  push    rdi
0x18002ebdc  push    r12
0x18002ebde  push    r14
0x18002ebe0  push    r15
0x18002ebe2  lea     rbp, [rsp-750h]
0x18002ebea  sub     rsp, 850h
0x18002ebf1  mov     rax, cs:__security_cookie
0x18002ebf8  xor     rax, rsp
0x18002ebfb  mov     [rbp+770h+var_30], rax
0x18002ec02  xor     r12d, r12d
0x18002ec05  mov     r15d, r8d
0x18002ec08  mov     r14, rdx
0x18002ec0b  mov     [rsp+870h+hKey], r12
0x18002ec10  mov     rsi, rcx
0x18002ec13  mov     [rsp+870h+var_838], r12
0x18002ec18  xor     edx, edx; Val
0x18002ec1a  mov     [rsp+870h+var_830], r12d
0x18002ec1f  mov     r8d, 7FCh; Size
0x18002ec25  lea     rcx, [rsp+870h+var_82C]; void *
0x18002ec2a  call    memset_0
0x18002ec2f  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18002ec36  jz      short loc_18002EC60
0x18002ec38  mov     rdx, qword ptr cs:xmmword_18004D648
0x18002ec3f  test    rdx, rdx
0x18002ec42  jz      short loc_18002EC6C
0x18002ec44  mov     rcx, cs:gIphlpEtwContext
0x18002ec4b  lea     r8, aLoadtcpipinfo; "LoadTcpipInfo"
0x18002ec52  mov     rax, cs:gIphlpTemplateFunc
0x18002ec59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec5e  jmp     short loc_18002EC6C
0x18002ec60  lea     rcx, aLoadtcpipinfo_0; "LoadTcpipInfo"
0x18002ec67  call    TraceHlp
0x18002ec6c  test    r14, r14
0x18002ec6f  jnz     short loc_18002ECBE
0x18002ec71  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18002ec78  lea     ebx, [r14+57h]
0x18002ec7c  jz      short loc_18002ECAD
0x18002ec7e  mov     rdx, cs:qword_18004D640
0x18002ec85  test    rdx, rdx
0x18002ec88  jz      loc_18002EE9D
0x18002ec8e  lea     r8, aWszadaptername; "wszAdapterName is NULL"
0x18002ec95  mov     rcx, cs:gIphlpEtwContext
0x18002ec9c  mov     rax, cs:gIphlpTemplateFunc
0x18002eca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eca8  jmp     loc_18002EE9D
0x18002ecad  lea     rcx, aWszadaptername_0; "wszAdapterName is NULL"
0x18002ecb4  call    TraceHlp
0x18002ecb9  jmp     loc_18002EE9D
0x18002ecbe  mov     ebx, 80h
0x18002ecc3  mov     [rsi], r12
0x18002ecc6  mov     edx, ebx; uBytes
0x18002ecc8  lea     ecx, [rbx-40h]; uFlags
0x18002eccb  call    cs:__imp_LocalAlloc
0x18002ecd2  nop     dword ptr [rax+rax+00h]
0x18002ecd7  mov     [rsi], rax
0x18002ecda  test    rax, rax
0x18002ecdd  jnz     short loc_18002ED41
0x18002ecdf  call    cs:__imp_GetLastError
0x18002ece6  nop     dword ptr [rax+rax+00h]
0x18002eceb  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18002ecf2  mov     ebx, eax
0x18002ecf4  jz      short loc_18002ED2E
0x18002ecf6  cmp     cs:qword_18004D640, r12
0x18002ecfd  jz      loc_18002EE9D
0x18002ed03  mov     r8d, eax
0x18002ed06  mov     word ptr [rsp+870h+var_830], r12w
0x18002ed0c  lea     rdx, aLocalallocFail_1; "LocalAlloc failed and returned %d"
0x18002ed13  lea     rcx, [rsp+870h+var_830]
0x18002ed18  call    FormatRRASErrorString
0x18002ed1d  mov     rdx, cs:qword_18004D640
0x18002ed24  lea     r8, [rsp+870h+var_830]
0x18002ed29  jmp     loc_18002EC95
0x18002ed2e  mov     edx, eax
0x18002ed30  lea     rcx, aLocalallocFail; "LocalAlloc failed and returned %d"
0x18002ed37  call    TraceHlp
0x18002ed3c  jmp     loc_18002EE9D
0x18002ed41  mov     r8, rbx; Size
0x18002ed44  xor     edx, edx; Val
0x18002ed46  mov     rcx, rax; void *
0x18002ed49  call    memset_0
0x18002ed4e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002ed52  mov     rdx, rdi
0x18002ed55  inc     rdx
0x18002ed58  cmp     [r14+rdx*2], r12w
0x18002ed5d  jnz     short loc_18002ED55
0x18002ed5f  mov     rbx, [rsi]
0x18002ed62  lea     rdx, ds:2[rdx*2]; uBytes
0x18002ed6a  mov     ecx, 40h ; '@'; uFlags
0x18002ed6f  call    cs:__imp_LocalAlloc
0x18002ed76  nop     dword ptr [rax+rax+00h]
0x18002ed7b  mov     [rbx+8], rax
0x18002ed7f  mov     rax, [rsi]
0x18002ed82  mov     rcx, [rax+8]; pszDest
0x18002ed86  test    rcx, rcx
0x18002ed89  jz      loc_18002ECDF
0x18002ed8f  mov     ebx, r12d
0x18002ed92  inc     rdi
0x18002ed95  cmp     [r14+rdi*2], r12w
0x18002ed9a  jnz     short loc_18002ED92
0x18002ed9c  lea     rdx, [rdi+1]; cchDest
0x18002eda0  mov     r8, r14; pszSrc
0x18002eda3  call    StringCchCopyW
0x18002eda8  test    r15d, r15d
0x18002edab  jnz     loc_18002EE9D
0x18002edb1  lea     rax, [rsp+870h+hKey]
0x18002edb6  mov     r14d, 20019h
0x18002edbc  lea     rdi, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002edc3  mov     [rsp+870h+phkResult], rax; phkResult
0x18002edc8  mov     r15, 0FFFFFFFF80000002h
0x18002edcf  mov     r9d, r14d; samDesired
0x18002edd2  mov     rdx, rdi; lpSubKey
0x18002edd5  mov     rcx, r15; hKey
0x18002edd8  xor     r8d, r8d; ulOptions
0x18002eddb  call    cs:__imp_RegOpenKeyExW
0x18002ede2  nop     dword ptr [rax+rax+00h]
0x18002ede7  mov     ebx, eax
0x18002ede9  test    eax, eax
0x18002edeb  jz      short loc_18002EE3E
0x18002eded  cmp     eax, 2
0x18002edf0  jz      short loc_18002EE51
0x18002edf2  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18002edf9  jz      short loc_18002EE2A
0x18002edfb  cmp     cs:qword_18004D640, r12
0x18002ee02  jz      loc_18002EE9D
0x18002ee08  mov     r9d, eax
0x18002ee0b  mov     word ptr [rsp+870h+var_830], r12w
0x18002ee11  mov     r8, rdi
0x18002ee14  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002ee1b  lea     rcx, [rsp+870h+var_830]
0x18002ee20  call    FormatRRASErrorString
0x18002ee25  jmp     loc_18002ED1D
0x18002ee2a  mov     r8d, eax
0x18002ee2d  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002ee34  mov     rdx, rdi
0x18002ee37  call    TraceHlp
0x18002ee3c  jmp     short loc_18002EE9D
0x18002ee3e  mov     rdx, [rsi]
0x18002ee41  mov     rcx, [rsp+870h+hKey]; hKey
0x18002ee46  call    LoadTcpipParam
0x18002ee4b  mov     ebx, eax
0x18002ee4d  test    eax, eax
0x18002ee4f  jnz     short loc_18002EE9D
0x18002ee51  lea     rax, [rsp+870h+var_838]
0x18002ee56  mov     r9d, r14d; samDesired
0x18002ee59  lea     rdi, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Ne"...
0x18002ee60  mov     [rsp+870h+phkResult], rax; phkResult
0x18002ee65  mov     rdx, rdi; lpSubKey
0x18002ee68  xor     r8d, r8d; ulOptions
0x18002ee6b  mov     rcx, r15; hKey
0x18002ee6e  call    cs:__imp_RegOpenKeyExW
0x18002ee75  nop     dword ptr [rax+rax+00h]
0x18002ee7a  mov     ebx, eax
0x18002ee7c  test    eax, eax
0x18002ee7e  jz      short loc_18002EE8E
0x18002ee80  cmp     eax, 2
0x18002ee83  jnz     loc_18002EDF2
0x18002ee89  mov     ebx, r12d
0x18002ee8c  jmp     short loc_18002EE9D
0x18002ee8e  mov     rdx, [rsi]
0x18002ee91  mov     rcx, [rsp+870h+var_838]; hKey
0x18002ee96  call    LoadWinsParam
0x18002ee9b  mov     ebx, eax
0x18002ee9d  mov     rcx, [rsp+870h+hKey]; hKey
0x18002eea2  test    rcx, rcx
0x18002eea5  jz      short loc_18002EEB3
0x18002eea7  call    cs:__imp_RegCloseKey
0x18002eeae  nop     dword ptr [rax+rax+00h]
0x18002eeb3  mov     rcx, [rsp+870h+var_838]; hKey
0x18002eeb8  test    rcx, rcx
0x18002eebb  jz      short loc_18002EEC9
0x18002eebd  call    cs:__imp_RegCloseKey
0x18002eec4  nop     dword ptr [rax+rax+00h]
0x18002eec9  test    ebx, ebx
0x18002eecb  jz      short loc_18002EED5
0x18002eecd  mov     rcx, rsi
0x18002eed0  call    FreeTcpipInfo
0x18002eed5  mov     eax, ebx
0x18002eed7  mov     rcx, [rbp+770h+var_30]
0x18002eede  xor     rcx, rsp; StackCookie
0x18002eee1  call    __security_check_cookie
0x18002eee6  lea     r11, [rsp+870h+var_20]
0x18002eeee  mov     rbx, [r11+40h]
0x18002eef2  mov     rsi, [r11+48h]
0x18002eef6  mov     rsp, r11
0x18002eef9  pop     r15
0x18002eefb  pop     r14
0x18002eefd  pop     r12
0x18002eeff  pop     rdi
0x18002ef00  pop     rbp
0x18002ef01  retn
```

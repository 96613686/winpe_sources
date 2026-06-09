# LoadTcpipInfo

- ea: `0x18002d904`
- end: `0x18002dc0c`
- name: `LoadTcpipInfo`
- size: `776`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18001b074`
- `0x18001d1d0`
- `0x18001fd58`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001ff50`
- `0x18002a138`
- `0x18002d08c`
- `0x18002d904`
- `0x18002dc14`
- `0x18002defc`
- `0x180030da4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d9ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002da97`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d9ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002da97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dafd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dafd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbcd`

## string_xrefs

- `0x18002db30`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002db49`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002dade`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18002db75`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`

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
    if ( qword_18004C648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C648,
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
      if ( !qword_18004C640 )
        goto LABEL_34;
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, L"LocalAlloc failed and returned %d", LastError);
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
        if ( !qword_18004C640 )
          goto LABEL_34;
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"RegOpenKeyEx(%ws) failed and returned %d", v15, v16);
LABEL_15:
        v7 = qword_18004C640;
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
      TcpipParam = LoadWinsParam(phkResult);
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
    v7 = qword_18004C640;
    if ( !qword_18004C640 )
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
0x18002d904  mov     [rsp-8+arg_10], rbx
0x18002d909  mov     [rsp-8+arg_18], rsi
0x18002d90e  push    rbp
0x18002d90f  push    rdi
0x18002d910  push    r12
0x18002d912  push    r14
0x18002d914  push    r15
0x18002d916  lea     rbp, [rsp-750h]
0x18002d91e  sub     rsp, 850h
0x18002d925  mov     rax, cs:__security_cookie
0x18002d92c  xor     rax, rsp
0x18002d92f  mov     [rbp+770h+var_30], rax
0x18002d936  xor     r12d, r12d
0x18002d939  mov     r15d, r8d
0x18002d93c  mov     r14, rdx
0x18002d93f  mov     [rsp+870h+hKey], r12
0x18002d944  mov     rsi, rcx
0x18002d947  mov     [rsp+870h+var_838], r12
0x18002d94c  xor     edx, edx; Val
0x18002d94e  mov     [rsp+870h+var_830], r12d
0x18002d953  mov     r8d, 7FCh; Size
0x18002d959  lea     rcx, [rsp+870h+var_82C]; void *
0x18002d95e  call    memset_0
0x18002d963  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18002d96a  jz      short loc_18002D994
0x18002d96c  mov     rdx, cs:qword_18004C648
0x18002d973  test    rdx, rdx
0x18002d976  jz      short loc_18002D9A0
0x18002d978  mov     rcx, cs:gIphlpEtwContext
0x18002d97f  lea     r8, aLoadtcpipinfo; "LoadTcpipInfo"
0x18002d986  mov     rax, cs:gIphlpTemplateFunc
0x18002d98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d992  jmp     short loc_18002D9A0
0x18002d994  lea     rcx, aLoadtcpipinfo_0; "LoadTcpipInfo"
0x18002d99b  call    TraceHlp
0x18002d9a0  test    r14, r14
0x18002d9a3  jnz     short loc_18002D9F2
0x18002d9a5  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18002d9ac  lea     ebx, [r14+57h]
0x18002d9b0  jz      short loc_18002D9E1
0x18002d9b2  mov     rdx, cs:qword_18004C640
0x18002d9b9  test    rdx, rdx
0x18002d9bc  jz      loc_18002DBB3
0x18002d9c2  lea     r8, aWszadaptername; "wszAdapterName is NULL"
0x18002d9c9  mov     rcx, cs:gIphlpEtwContext
0x18002d9d0  mov     rax, cs:gIphlpTemplateFunc
0x18002d9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9dc  jmp     loc_18002DBB3
0x18002d9e1  lea     rcx, aWszadaptername_0; "wszAdapterName is NULL"
0x18002d9e8  call    TraceHlp
0x18002d9ed  jmp     loc_18002DBB3
0x18002d9f2  mov     ebx, 80h
0x18002d9f7  mov     [rsi], r12
0x18002d9fa  mov     edx, ebx; uBytes
0x18002d9fc  lea     ecx, [rbx-40h]; uFlags
0x18002d9ff  call    cs:__imp_LocalAlloc
0x18002da05  mov     [rsi], rax
0x18002da08  test    rax, rax
0x18002da0b  jnz     short loc_18002DA69
0x18002da0d  call    cs:__imp_GetLastError
0x18002da13  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18002da1a  mov     ebx, eax
0x18002da1c  jz      short loc_18002DA56
0x18002da1e  cmp     cs:qword_18004C640, r12
0x18002da25  jz      loc_18002DBB3
0x18002da2b  mov     r8d, eax
0x18002da2e  mov     word ptr [rsp+870h+var_830], r12w
0x18002da34  lea     rdx, aLocalallocFail_1; "LocalAlloc failed and returned %d"
0x18002da3b  lea     rcx, [rsp+870h+var_830]
0x18002da40  call    FormatRRASErrorString
0x18002da45  mov     rdx, cs:qword_18004C640
0x18002da4c  lea     r8, [rsp+870h+var_830]
0x18002da51  jmp     loc_18002D9C9
0x18002da56  mov     edx, eax
0x18002da58  lea     rcx, aLocalallocFail; "LocalAlloc failed and returned %d"
0x18002da5f  call    TraceHlp
0x18002da64  jmp     loc_18002DBB3
0x18002da69  mov     r8, rbx; Size
0x18002da6c  xor     edx, edx; Val
0x18002da6e  mov     rcx, rax; void *
0x18002da71  call    memset_0
0x18002da76  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002da7a  mov     rdx, rdi
0x18002da7d  inc     rdx
0x18002da80  cmp     [r14+rdx*2], r12w
0x18002da85  jnz     short loc_18002DA7D
0x18002da87  mov     rbx, [rsi]
0x18002da8a  lea     rdx, ds:2[rdx*2]; uBytes
0x18002da92  mov     ecx, 40h ; '@'; uFlags
0x18002da97  call    cs:__imp_LocalAlloc
0x18002da9d  mov     [rbx+8], rax
0x18002daa1  mov     rax, [rsi]
0x18002daa4  mov     rcx, [rax+8]; pszDest
0x18002daa8  test    rcx, rcx
0x18002daab  jz      loc_18002DA0D
0x18002dab1  mov     ebx, r12d
0x18002dab4  inc     rdi
0x18002dab7  cmp     [r14+rdi*2], r12w
0x18002dabc  jnz     short loc_18002DAB4
0x18002dabe  lea     rdx, [rdi+1]; cchDest
0x18002dac2  mov     r8, r14; pszSrc
0x18002dac5  call    StringCchCopyW
0x18002daca  test    r15d, r15d
0x18002dacd  jnz     loc_18002DBB3
0x18002dad3  lea     rax, [rsp+870h+hKey]
0x18002dad8  mov     r14d, 20019h
0x18002dade  lea     rdi, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002dae5  mov     [rsp+870h+phkResult], rax; phkResult
0x18002daea  mov     r15, 0FFFFFFFF80000002h
0x18002daf1  mov     r9d, r14d; samDesired
0x18002daf4  mov     rdx, rdi; lpSubKey
0x18002daf7  mov     rcx, r15; hKey
0x18002dafa  xor     r8d, r8d; ulOptions
0x18002dafd  call    cs:__imp_RegOpenKeyExW
0x18002db03  mov     ebx, eax
0x18002db05  test    eax, eax
0x18002db07  jz      short loc_18002DB5A
0x18002db09  cmp     eax, 2
0x18002db0c  jz      short loc_18002DB6D
0x18002db0e  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18002db15  jz      short loc_18002DB46
0x18002db17  cmp     cs:qword_18004C640, r12
0x18002db1e  jz      loc_18002DBB3
0x18002db24  mov     r9d, eax
0x18002db27  mov     word ptr [rsp+870h+var_830], r12w
0x18002db2d  mov     r8, rdi
0x18002db30  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002db37  lea     rcx, [rsp+870h+var_830]
0x18002db3c  call    FormatRRASErrorString
0x18002db41  jmp     loc_18002DA45
0x18002db46  mov     r8d, eax
0x18002db49  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002db50  mov     rdx, rdi
0x18002db53  call    TraceHlp
0x18002db58  jmp     short loc_18002DBB3
0x18002db5a  mov     rdx, [rsi]
0x18002db5d  mov     rcx, [rsp+870h+hKey]; hKey
0x18002db62  call    LoadTcpipParam
0x18002db67  mov     ebx, eax
0x18002db69  test    eax, eax
0x18002db6b  jnz     short loc_18002DBB3
0x18002db6d  lea     rax, [rsp+870h+var_838]
0x18002db72  mov     r9d, r14d; samDesired
0x18002db75  lea     rdi, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Ne"...
0x18002db7c  mov     [rsp+870h+phkResult], rax; phkResult
0x18002db81  mov     rdx, rdi; lpSubKey
0x18002db84  xor     r8d, r8d; ulOptions
0x18002db87  mov     rcx, r15; hKey
0x18002db8a  call    cs:__imp_RegOpenKeyExW
0x18002db90  mov     ebx, eax
0x18002db92  test    eax, eax
0x18002db94  jz      short loc_18002DBA4
0x18002db96  cmp     eax, 2
0x18002db99  jnz     loc_18002DB0E
0x18002db9f  mov     ebx, r12d
0x18002dba2  jmp     short loc_18002DBB3
0x18002dba4  mov     rdx, [rsi]
0x18002dba7  mov     rcx, [rsp+870h+var_838]; hKey
0x18002dbac  call    LoadWinsParam
0x18002dbb1  mov     ebx, eax
0x18002dbb3  mov     rcx, [rsp+870h+hKey]; hKey
0x18002dbb8  test    rcx, rcx
0x18002dbbb  jz      short loc_18002DBC3
0x18002dbbd  call    cs:__imp_RegCloseKey
0x18002dbc3  mov     rcx, [rsp+870h+var_838]; hKey
0x18002dbc8  test    rcx, rcx
0x18002dbcb  jz      short loc_18002DBD3
0x18002dbcd  call    cs:__imp_RegCloseKey
0x18002dbd3  test    ebx, ebx
0x18002dbd5  jz      short loc_18002DBDF
0x18002dbd7  mov     rcx, rsi
0x18002dbda  call    FreeTcpipInfo
0x18002dbdf  mov     eax, ebx
0x18002dbe1  mov     rcx, [rbp+770h+var_30]
0x18002dbe8  xor     rcx, rsp; StackCookie
0x18002dbeb  call    __security_check_cookie
0x18002dbf0  lea     r11, [rsp+870h+var_20]
0x18002dbf8  mov     rbx, [r11+40h]
0x18002dbfc  mov     rsi, [r11+48h]
0x18002dc00  mov     rsp, r11
0x18002dc03  pop     r15
0x18002dc05  pop     r14
0x18002dc07  pop     r12
0x18002dc09  pop     rdi
0x18002dc0a  pop     rbp
0x18002dc0b  retn
```

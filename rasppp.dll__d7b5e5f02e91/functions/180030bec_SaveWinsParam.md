# SaveWinsParam

- ea: `0x180030bec`
- end: `0x18003100a`
- name: `SaveWinsParam`
- size: `1054`
- prototype: `__int64 __fastcall(HKEY hKey, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002fce0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180014b1c`
- `0x18002b0dc`
- `0x18002f480`
- `0x180030bec`
- `0x18003230c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030fbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030fbf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030ce2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030ce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030cf6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030e98`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030e98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030e5c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030f48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030e5c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030f48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030d87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030d87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030fd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030fd5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180030dad`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180030dad`

## string_xrefs

- `0x180030e0c`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x180030e1b`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x180030dd8`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x180030de7`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x180030e86`: `RegSetValueEx(%ws) failed: %d`
- `0x180030e8f`: `RegSetValueEx(%ws) failed: %d`
- `0x180030eba`: `RegDeleteValue(%ws) failed: %d`
- `0x180030ef8`: `RegDeleteValue(%ws) failed: %d`
- `0x180030f6f`: `RegSetValueEx(%ws) failed and returned %d`
- `0x180030fad`: `RegSetValueEx(%ws) failed and returned %d`

## pseudocode

```c
__int64 __fastcall SaveWinsParam(HKEY hKey, __int64 a2)
{
  int v4; // eax
  __int64 v5; // rax
  __int64 v6; // rax
  size_t v7; // rbx
  wchar_t *v8; // rdi
  DWORD LastError; // eax
  DWORD v10; // ebx
  unsigned int v11; // eax
  const WCHAR *v12; // r8
  const wchar_t *v13; // rdx
  const CHAR *v14; // rcx
  unsigned int v15; // eax
  const wchar_t *v16; // rdx
  const CHAR *v17; // rcx
  int *v18; // r8
  int v19; // eax
  const BYTE *v20; // r8
  HKEY hKeya; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  int v24; // [rsp+3Ch] [rbp-C4h] BYREF
  int v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKeya = 0;
  *(_DWORD *)Data = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v4 = gIsIphlpEtwTracingAvailable;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( !qword_18004D648 )
      goto LABEL_8;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      qword_18004D648,
      L"SaveWinsParam");
  }
  else
  {
    TraceHlp("SaveWinsParam");
  }
  v4 = gIsIphlpEtwTracingAvailable;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004D648 )
    {
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004D648,
        L"SaveWinsParam");
      goto LABEL_10;
    }
LABEL_8:
    if ( v4 )
      goto LABEL_10;
  }
  TraceHlp("SaveWinsParam");
LABEL_10:
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(*(_QWORD *)(a2 + 8) + 2 * v5) );
  v6 = (unsigned int)(v5 + 7);
  v7 = (unsigned int)v6;
  v8 = (wchar_t *)LocalAlloc(0x40u, 2 * v6);
  if ( !v8 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( !gIsIphlpEtwTracingAvailable )
    {
      TraceHlp("LocalAlloc failed and returned %d");
      goto LABEL_51;
    }
    if ( !qword_18004D640 )
      goto LABEL_51;
    LOWORD(v25) = 0;
    FormatRRASErrorString((wchar_t *)&v25, L"LocalAlloc failed and returned %d", LastError);
    goto LABEL_48;
  }
  StringCchPrintfW(v8, v7, L"%s%s", L"Tcpip_", *(_QWORD *)(a2 + 8));
  v11 = RegOpenKeyExW(hKey, v8, 0, 0x20006u, &hKeya);
  v10 = v11;
  if ( v11 )
  {
    if ( v11 != 2 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004D640 )
          goto LABEL_51;
        v12 = v8;
        v13 = L"RegOpenKeyEx(%ws) failed and returned %d";
        goto LABEL_47;
      }
      v14 = "RegOpenKeyEx(%ws) failed and returned %d";
      goto LABEL_50;
    }
    v11 = RegCreateKeyW(hKey, v8, &hKeya);
    v10 = v11;
    if ( v11 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004D640 )
          goto LABEL_51;
        v12 = v8;
        v13 = L"RegCreateKey(%ws) (v4) failed and returned %d";
LABEL_47:
        LOWORD(v25) = 0;
        FormatRRASErrorString((wchar_t *)&v25, v13, v12, v11);
LABEL_48:
        ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D640, &v25);
        goto LABEL_51;
      }
      v14 = "RegCreateKey(%ws) (v4) failed and returned %d";
      goto LABEL_50;
    }
  }
  if ( *(_DWORD *)(a2 + 4) )
  {
    *(_DWORD *)Data = 2;
    v15 = RegSetValueExW(hKeya, L"NetbiosOptions", 0, 4u, Data, 4u);
    if ( !v15 )
      goto LABEL_41;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004D640 )
        goto LABEL_41;
      v16 = L"RegSetValueEx(%ws) failed: %d";
LABEL_38:
      LOWORD(v25) = 0;
      FormatRRASErrorString((wchar_t *)&v25, v16, L"NetbiosOptions", v15);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D640, &v25);
      goto LABEL_41;
    }
    v17 = "RegSetValueEx(%ws) failed: %d";
  }
  else
  {
    v15 = RegDeleteValueW(hKeya, L"NetbiosOptions");
    if ( !v15 )
      goto LABEL_41;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004D640 )
        goto LABEL_41;
      v16 = L"RegDeleteValue(%ws) failed: %d";
      goto LABEL_38;
    }
    v17 = "RegDeleteValue(%ws) failed: %d";
  }
  TraceHlp(v17);
LABEL_41:
  v18 = *(int **)(a2 + 112);
  if ( !v18 )
  {
    v24 = 0;
    v18 = &v24;
  }
  v19 = MwszLength(v18);
  v11 = RegSetValueExW(hKeya, L"NameServerList", 0, 7u, v20, 2 * v19);
  v10 = v11;
  if ( v11 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004D640 )
        goto LABEL_51;
      v12 = L"NameServerList";
      v13 = L"RegSetValueEx(%ws) failed and returned %d";
      goto LABEL_47;
    }
    v14 = "RegSetValueEx(%ws) failed and returned %d";
LABEL_50:
    TraceHlp(v14);
  }
LABEL_51:
  LocalFree(v8);
  if ( hKeya )
    RegCloseKey(hKeya);
  return v10;
}

```

## disassembly

```asm
0x180030bec  mov     [rsp-8+arg_10], rbx
0x180030bf1  push    rbp
0x180030bf2  push    rsi
0x180030bf3  push    rdi
0x180030bf4  push    r14
0x180030bf6  push    r15
0x180030bf8  lea     rbp, [rsp-750h]
0x180030c00  sub     rsp, 850h
0x180030c07  mov     rax, cs:__security_cookie
0x180030c0e  xor     rax, rsp
0x180030c11  mov     [rbp+770h+var_30], rax
0x180030c18  xor     r15d, r15d
0x180030c1b  mov     rsi, rdx
0x180030c1e  mov     r14, rcx
0x180030c21  mov     [rsp+870h+hKey], r15
0x180030c26  xor     edx, edx; Val
0x180030c28  mov     dword ptr [rsp+870h+Data], r15d
0x180030c2d  lea     rcx, [rsp+870h+var_82C]; void *
0x180030c32  mov     [rsp+870h+var_830], r15d
0x180030c37  mov     r8d, 7FCh; Size
0x180030c3d  call    memset_0
0x180030c42  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x180030c48  test    eax, eax
0x180030c4a  jz      short loc_180030C74
0x180030c4c  mov     rdx, qword ptr cs:xmmword_18004D648
0x180030c53  test    rdx, rdx
0x180030c56  jz      short loc_180030CB2
0x180030c58  mov     rcx, cs:gIphlpEtwContext
0x180030c5f  lea     r8, aSavewinsparam; "SaveWinsParam"
0x180030c66  mov     rax, cs:gIphlpTemplateFunc
0x180030c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c72  jmp     short loc_180030C80
0x180030c74  lea     rcx, aSavewinsparam_0; "SaveWinsParam"
0x180030c7b  call    TraceHlp
0x180030c80  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x180030c86  test    eax, eax
0x180030c88  jz      short loc_180030CB6
0x180030c8a  mov     rdx, qword ptr cs:xmmword_18004D648
0x180030c91  test    rdx, rdx
0x180030c94  jz      short loc_180030CB2
0x180030c96  mov     rcx, cs:gIphlpEtwContext
0x180030c9d  lea     r8, aSavewinsparam; "SaveWinsParam"
0x180030ca4  mov     rax, cs:gIphlpTemplateFunc
0x180030cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cb0  jmp     short loc_180030CC2
0x180030cb2  test    eax, eax
0x180030cb4  jnz     short loc_180030CC2
0x180030cb6  lea     rcx, aSavewinsparam_0; "SaveWinsParam"
0x180030cbd  call    TraceHlp
0x180030cc2  mov     rcx, [rsi+8]
0x180030cc6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030cca  inc     rax
0x180030ccd  cmp     [rcx+rax*2], r15w
0x180030cd2  jnz     short loc_180030CCA
0x180030cd4  add     eax, 7
0x180030cd7  mov     ecx, 40h ; '@'; uFlags
0x180030cdc  mov     ebx, eax
0x180030cde  lea     rdx, [rax+rax]; uBytes
0x180030ce2  call    cs:__imp_LocalAlloc
0x180030ce9  nop     dword ptr [rax+rax+00h]
0x180030cee  mov     rdi, rax
0x180030cf1  test    rax, rax
0x180030cf4  jnz     short loc_180030D4C
0x180030cf6  call    cs:__imp_GetLastError
0x180030cfd  nop     dword ptr [rax+rax+00h]
0x180030d02  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030d09  mov     ebx, eax
0x180030d0b  jz      short loc_180030D39
0x180030d0d  cmp     cs:qword_18004D640, r15
0x180030d14  jz      loc_180030FBC
0x180030d1a  mov     r8d, eax
0x180030d1d  mov     word ptr [rsp+870h+var_830], r15w
0x180030d23  lea     rdx, aLocalallocFail_1; "LocalAlloc failed and returned %d"
0x180030d2a  lea     rcx, [rsp+870h+var_830]
0x180030d2f  call    FormatRRASErrorString
0x180030d34  jmp     loc_180030F89
0x180030d39  mov     edx, eax
0x180030d3b  lea     rcx, aLocalallocFail; "LocalAlloc failed and returned %d"
0x180030d42  call    TraceHlp
0x180030d47  jmp     loc_180030FBC
0x180030d4c  mov     rax, [rsi+8]
0x180030d50  lea     r9, aTcpip; "Tcpip_"
0x180030d57  lea     r8, aSS_0; "%s%s"
0x180030d5e  mov     [rsp+870h+phkResult], rax
0x180030d63  mov     rdx, rbx; cchDest
0x180030d66  mov     rcx, rdi; pszDest
0x180030d69  call    StringCchPrintfW
0x180030d6e  lea     rax, [rsp+870h+hKey]
0x180030d73  mov     r9d, 20006h; samDesired
0x180030d79  xor     r8d, r8d; ulOptions
0x180030d7c  mov     [rsp+870h+phkResult], rax; phkResult
0x180030d81  mov     rdx, rdi; lpSubKey
0x180030d84  mov     rcx, r14; hKey
0x180030d87  call    cs:__imp_RegOpenKeyExW
0x180030d8e  nop     dword ptr [rax+rax+00h]
0x180030d93  mov     ebx, eax
0x180030d95  test    eax, eax
0x180030d97  jz      loc_180030E27
0x180030d9d  cmp     eax, 2
0x180030da0  jnz     short loc_180030DF3
0x180030da2  lea     r8, [rsp+870h+hKey]; phkResult
0x180030da7  mov     rdx, rdi; lpSubKey
0x180030daa  mov     rcx, r14; hKey
0x180030dad  call    cs:__imp_RegCreateKeyW
0x180030db4  nop     dword ptr [rax+rax+00h]
0x180030db9  mov     ebx, eax
0x180030dbb  test    eax, eax
0x180030dbd  jz      short loc_180030E27
0x180030dbf  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030dc6  jz      short loc_180030DE4
0x180030dc8  cmp     cs:qword_18004D640, r15
0x180030dcf  jz      loc_180030FBC
0x180030dd5  mov     r8, rdi
0x180030dd8  lea     rdx, aRegcreatekeyWs_1; "RegCreateKey(%ws) (v4) failed and retur"...
0x180030ddf  jmp     loc_180030F76
0x180030de4  mov     rdx, rdi
0x180030de7  lea     rcx, aRegcreatekeyWs; "RegCreateKey(%ws) (v4) failed and retur"...
0x180030dee  jmp     loc_180030FB4
0x180030df3  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030dfa  jz      short loc_180030E18
0x180030dfc  cmp     cs:qword_18004D640, r15
0x180030e03  jz      loc_180030FBC
0x180030e09  mov     r8, rdi
0x180030e0c  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x180030e13  jmp     loc_180030F76
0x180030e18  mov     rdx, rdi
0x180030e1b  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x180030e22  jmp     loc_180030FB4
0x180030e27  lea     rbx, aNetbiosoptions; "NetbiosOptions"
0x180030e2e  mov     rcx, [rsp+870h+hKey]; hKey
0x180030e33  mov     rdx, rbx; lpValueName
0x180030e36  cmp     [rsi+4], r15d
0x180030e3a  jz      short loc_180030E98
0x180030e3c  mov     r9d, 4; dwType
0x180030e42  mov     dword ptr [rsp+870h+Data], 2
0x180030e4a  lea     rax, [rsp+870h+Data]
0x180030e4f  mov     [rsp+870h+cbData], r9d; cbData
0x180030e54  xor     r8d, r8d; Reserved
0x180030e57  mov     [rsp+870h+phkResult], rax; lpData
0x180030e5c  call    cs:__imp_RegSetValueExW
0x180030e63  nop     dword ptr [rax+rax+00h]
0x180030e68  test    eax, eax
0x180030e6a  jz      loc_180030F0A
0x180030e70  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030e77  jz      short loc_180030E8F
0x180030e79  cmp     cs:qword_18004D640, r15
0x180030e80  jz      loc_180030F0A
0x180030e86  lea     rdx, aRegsetvalueexW_2; "RegSetValueEx(%ws) failed: %d"
0x180030e8d  jmp     short loc_180030EC1
0x180030e8f  lea     rcx, aRegsetvalueexW_1; "RegSetValueEx(%ws) failed: %d"
0x180030e96  jmp     short loc_180030EFF
0x180030e98  call    cs:__imp_RegDeleteValueW
0x180030e9f  nop     dword ptr [rax+rax+00h]
0x180030ea4  test    eax, eax
0x180030ea6  jz      short loc_180030F0A
0x180030ea8  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030eaf  jz      short loc_180030EF8
0x180030eb1  cmp     cs:qword_18004D640, r15
0x180030eb8  jz      short loc_180030F0A
0x180030eba  lea     rdx, aRegdeletevalue_1; "RegDeleteValue(%ws) failed: %d"
0x180030ec1  mov     r8, rbx
0x180030ec4  mov     word ptr [rsp+870h+var_830], r15w
0x180030eca  mov     r9d, eax
0x180030ecd  lea     rcx, [rsp+870h+var_830]
0x180030ed2  call    FormatRRASErrorString
0x180030ed7  mov     rdx, cs:qword_18004D640
0x180030ede  lea     r8, [rsp+870h+var_830]
0x180030ee3  mov     rcx, cs:gIphlpEtwContext
0x180030eea  mov     rax, cs:gIphlpTemplateFunc
0x180030ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ef6  jmp     short loc_180030F0A
0x180030ef8  lea     rcx, aRegdeletevalue_0; "RegDeleteValue(%ws) failed: %d"
0x180030eff  mov     r8d, eax
0x180030f02  mov     rdx, rbx
0x180030f05  call    TraceHlp
0x180030f0a  mov     r8, [rsi+70h]
0x180030f0e  test    r8, r8
0x180030f11  jnz     short loc_180030F1D
0x180030f13  mov     [rsp+870h+var_834], r15d
0x180030f18  lea     r8, [rsp+870h+var_834]
0x180030f1d  mov     rcx, r8
0x180030f20  call    MwszLength
0x180030f25  mov     rcx, [rsp+870h+hKey]; hKey
0x180030f2a  lea     rsi, aNameserverlist; "NameServerList"
0x180030f31  add     eax, eax
0x180030f33  mov     r9d, 7; dwType
0x180030f39  mov     [rsp+870h+cbData], eax; cbData
0x180030f3d  mov     rdx, rsi; lpValueName
0x180030f40  mov     [rsp+870h+phkResult], r8; lpData
0x180030f45  xor     r8d, r8d; Reserved
0x180030f48  call    cs:__imp_RegSetValueExW
0x180030f4f  nop     dword ptr [rax+rax+00h]
0x180030f54  mov     ebx, eax
0x180030f56  test    eax, eax
0x180030f58  jz      short loc_180030FBC
0x180030f5a  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030f61  jz      short loc_180030FAA
0x180030f63  cmp     cs:qword_18004D640, r15
0x180030f6a  jz      short loc_180030FBC
0x180030f6c  mov     r8, rsi
0x180030f6f  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x180030f76  mov     r9d, eax
0x180030f79  mov     word ptr [rsp+870h+var_830], r15w
0x180030f7f  lea     rcx, [rsp+870h+var_830]
0x180030f84  call    FormatRRASErrorString
0x180030f89  mov     rdx, cs:qword_18004D640
0x180030f90  lea     r8, [rsp+870h+var_830]
0x180030f95  mov     rcx, cs:gIphlpEtwContext
0x180030f9c  mov     rax, cs:gIphlpTemplateFunc
0x180030fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030fa8  jmp     short loc_180030FBC
0x180030faa  mov     rdx, rsi
0x180030fad  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x180030fb4  mov     r8d, eax
0x180030fb7  call    TraceHlp
0x180030fbc  mov     rcx, rdi; hMem
0x180030fbf  call    cs:__imp_LocalFree
0x180030fc6  nop     dword ptr [rax+rax+00h]
0x180030fcb  mov     rcx, [rsp+870h+hKey]; hKey
0x180030fd0  test    rcx, rcx
0x180030fd3  jz      short loc_180030FE1
0x180030fd5  call    cs:__imp_RegCloseKey
0x180030fdc  nop     dword ptr [rax+rax+00h]
0x180030fe1  mov     eax, ebx
0x180030fe3  mov     rcx, [rbp+770h+var_30]
0x180030fea  xor     rcx, rsp; StackCookie
0x180030fed  call    __security_check_cookie
0x180030ff2  mov     rbx, [rsp+870h+arg_10]
0x180030ffa  add     rsp, 850h
0x180031001  pop     r15
0x180031003  pop     r14
0x180031005  pop     rdi
0x180031006  pop     rsi
0x180031007  pop     rbp
0x180031008  retn
```

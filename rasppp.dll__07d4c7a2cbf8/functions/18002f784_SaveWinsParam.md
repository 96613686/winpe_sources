# SaveWinsParam

- ea: `0x18002f784`
- end: `0x18002fb67`
- name: `SaveWinsParam`
- size: `995`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002e92c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180014434`
- `0x18002a138`
- `0x18002e12c`
- `0x18002f784`
- `0x180030da4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fb29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fb29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f87a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f888`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002fa0e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002fa0e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f9dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fab8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f9dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fab8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f913`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f913`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fb39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fb39`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002f933`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002f933`

## string_xrefs

- `0x18002f98c`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002f99b`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002f958`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x18002f967`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x18002f9fc`: `RegSetValueEx(%ws) failed: %d`
- `0x18002fa05`: `RegSetValueEx(%ws) failed: %d`
- `0x18002fa2a`: `RegDeleteValue(%ws) failed: %d`
- `0x18002fa68`: `RegDeleteValue(%ws) failed: %d`
- `0x18002fad9`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18002fb17`: `RegSetValueEx(%ws) failed and returned %d`

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
    if ( !qword_18004C648 )
      goto LABEL_8;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      qword_18004C648,
      L"SaveWinsParam");
  }
  else
  {
    TraceHlp("SaveWinsParam");
  }
  v4 = gIsIphlpEtwTracingAvailable;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004C648 )
    {
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C648,
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
    if ( !qword_18004C640 )
      goto LABEL_51;
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"LocalAlloc failed and returned %d", LastError);
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
        if ( !qword_18004C640 )
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
        if ( !qword_18004C640 )
          goto LABEL_51;
        v12 = v8;
        v13 = L"RegCreateKey(%ws) (v4) failed and returned %d";
LABEL_47:
        LOWORD(v25) = 0;
        FormatRRASErrorString(&v25, v13, v12, v11);
LABEL_48:
        ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C640, &v25);
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
      if ( !qword_18004C640 )
        goto LABEL_41;
      v16 = L"RegSetValueEx(%ws) failed: %d";
LABEL_38:
      LOWORD(v25) = 0;
      FormatRRASErrorString(&v25, v16, L"NetbiosOptions", v15);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C640, &v25);
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
      if ( !qword_18004C640 )
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
      if ( !qword_18004C640 )
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
0x18002f784  mov     [rsp-8+arg_10], rbx
0x18002f789  push    rbp
0x18002f78a  push    rsi
0x18002f78b  push    rdi
0x18002f78c  push    r14
0x18002f78e  push    r15
0x18002f790  lea     rbp, [rsp-750h]
0x18002f798  sub     rsp, 850h
0x18002f79f  mov     rax, cs:__security_cookie
0x18002f7a6  xor     rax, rsp
0x18002f7a9  mov     [rbp+770h+var_30], rax
0x18002f7b0  xor     r15d, r15d
0x18002f7b3  mov     rsi, rdx
0x18002f7b6  mov     r14, rcx
0x18002f7b9  mov     [rsp+870h+hKey], r15
0x18002f7be  xor     edx, edx; Val
0x18002f7c0  mov     dword ptr [rsp+870h+Data], r15d
0x18002f7c5  lea     rcx, [rsp+870h+var_82C]; void *
0x18002f7ca  mov     [rsp+870h+var_830], r15d
0x18002f7cf  mov     r8d, 7FCh; Size
0x18002f7d5  call    memset_0
0x18002f7da  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18002f7e0  test    eax, eax
0x18002f7e2  jz      short loc_18002F80C
0x18002f7e4  mov     rdx, cs:qword_18004C648
0x18002f7eb  test    rdx, rdx
0x18002f7ee  jz      short loc_18002F84A
0x18002f7f0  mov     rcx, cs:gIphlpEtwContext
0x18002f7f7  lea     r8, aSavewinsparam; "SaveWinsParam"
0x18002f7fe  mov     rax, cs:gIphlpTemplateFunc
0x18002f805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f80a  jmp     short loc_18002F818
0x18002f80c  lea     rcx, aSavewinsparam_0; "SaveWinsParam"
0x18002f813  call    TraceHlp
0x18002f818  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18002f81e  test    eax, eax
0x18002f820  jz      short loc_18002F84E
0x18002f822  mov     rdx, cs:qword_18004C648
0x18002f829  test    rdx, rdx
0x18002f82c  jz      short loc_18002F84A
0x18002f82e  mov     rcx, cs:gIphlpEtwContext
0x18002f835  lea     r8, aSavewinsparam; "SaveWinsParam"
0x18002f83c  mov     rax, cs:gIphlpTemplateFunc
0x18002f843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f848  jmp     short loc_18002F85A
0x18002f84a  test    eax, eax
0x18002f84c  jnz     short loc_18002F85A
0x18002f84e  lea     rcx, aSavewinsparam_0; "SaveWinsParam"
0x18002f855  call    TraceHlp
0x18002f85a  mov     rcx, [rsi+8]
0x18002f85e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f862  inc     rax
0x18002f865  cmp     [rcx+rax*2], r15w
0x18002f86a  jnz     short loc_18002F862
0x18002f86c  add     eax, 7
0x18002f86f  mov     ecx, 40h ; '@'; uFlags
0x18002f874  mov     ebx, eax
0x18002f876  lea     rdx, [rax+rax]; uBytes
0x18002f87a  call    cs:__imp_LocalAlloc
0x18002f880  mov     rdi, rax
0x18002f883  test    rax, rax
0x18002f886  jnz     short loc_18002F8D8
0x18002f888  call    cs:__imp_GetLastError
0x18002f88e  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f895  mov     ebx, eax
0x18002f897  jz      short loc_18002F8C5
0x18002f899  cmp     cs:qword_18004C640, r15
0x18002f8a0  jz      loc_18002FB26
0x18002f8a6  mov     r8d, eax
0x18002f8a9  mov     word ptr [rsp+870h+var_830], r15w
0x18002f8af  lea     rdx, aLocalallocFail_1; "LocalAlloc failed and returned %d"
0x18002f8b6  lea     rcx, [rsp+870h+var_830]
0x18002f8bb  call    FormatRRASErrorString
0x18002f8c0  jmp     loc_18002FAF3
0x18002f8c5  mov     edx, eax
0x18002f8c7  lea     rcx, aLocalallocFail; "LocalAlloc failed and returned %d"
0x18002f8ce  call    TraceHlp
0x18002f8d3  jmp     loc_18002FB26
0x18002f8d8  mov     rax, [rsi+8]
0x18002f8dc  lea     r9, aTcpip; "Tcpip_"
0x18002f8e3  lea     r8, aSS_0; "%s%s"
0x18002f8ea  mov     [rsp+870h+phkResult], rax
0x18002f8ef  mov     rdx, rbx; cchDest
0x18002f8f2  mov     rcx, rdi; pszDest
0x18002f8f5  call    StringCchPrintfW
0x18002f8fa  lea     rax, [rsp+870h+hKey]
0x18002f8ff  mov     r9d, 20006h; samDesired
0x18002f905  xor     r8d, r8d; ulOptions
0x18002f908  mov     [rsp+870h+phkResult], rax; phkResult
0x18002f90d  mov     rdx, rdi; lpSubKey
0x18002f910  mov     rcx, r14; hKey
0x18002f913  call    cs:__imp_RegOpenKeyExW
0x18002f919  mov     ebx, eax
0x18002f91b  test    eax, eax
0x18002f91d  jz      loc_18002F9A7
0x18002f923  cmp     eax, 2
0x18002f926  jnz     short loc_18002F973
0x18002f928  lea     r8, [rsp+870h+hKey]; phkResult
0x18002f92d  mov     rdx, rdi; lpSubKey
0x18002f930  mov     rcx, r14; hKey
0x18002f933  call    cs:__imp_RegCreateKeyW
0x18002f939  mov     ebx, eax
0x18002f93b  test    eax, eax
0x18002f93d  jz      short loc_18002F9A7
0x18002f93f  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f946  jz      short loc_18002F964
0x18002f948  cmp     cs:qword_18004C640, r15
0x18002f94f  jz      loc_18002FB26
0x18002f955  mov     r8, rdi
0x18002f958  lea     rdx, aRegcreatekeyWs_1; "RegCreateKey(%ws) (v4) failed and retur"...
0x18002f95f  jmp     loc_18002FAE0
0x18002f964  mov     rdx, rdi
0x18002f967  lea     rcx, aRegcreatekeyWs; "RegCreateKey(%ws) (v4) failed and retur"...
0x18002f96e  jmp     loc_18002FB1E
0x18002f973  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f97a  jz      short loc_18002F998
0x18002f97c  cmp     cs:qword_18004C640, r15
0x18002f983  jz      loc_18002FB26
0x18002f989  mov     r8, rdi
0x18002f98c  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002f993  jmp     loc_18002FAE0
0x18002f998  mov     rdx, rdi
0x18002f99b  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002f9a2  jmp     loc_18002FB1E
0x18002f9a7  lea     rbx, aNetbiosoptions; "NetbiosOptions"
0x18002f9ae  mov     rcx, [rsp+870h+hKey]; hKey
0x18002f9b3  mov     rdx, rbx; lpValueName
0x18002f9b6  cmp     [rsi+4], r15d
0x18002f9ba  jz      short loc_18002FA0E
0x18002f9bc  mov     r9d, 4; dwType
0x18002f9c2  mov     dword ptr [rsp+870h+Data], 2
0x18002f9ca  lea     rax, [rsp+870h+Data]
0x18002f9cf  mov     [rsp+870h+cbData], r9d; cbData
0x18002f9d4  xor     r8d, r8d; Reserved
0x18002f9d7  mov     [rsp+870h+phkResult], rax; lpData
0x18002f9dc  call    cs:__imp_RegSetValueExW
0x18002f9e2  test    eax, eax
0x18002f9e4  jz      loc_18002FA7A
0x18002f9ea  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f9f1  jz      short loc_18002FA05
0x18002f9f3  cmp     cs:qword_18004C640, r15
0x18002f9fa  jz      short loc_18002FA7A
0x18002f9fc  lea     rdx, aRegsetvalueexW_2; "RegSetValueEx(%ws) failed: %d"
0x18002fa03  jmp     short loc_18002FA31
0x18002fa05  lea     rcx, aRegsetvalueexW_1; "RegSetValueEx(%ws) failed: %d"
0x18002fa0c  jmp     short loc_18002FA6F
0x18002fa0e  call    cs:__imp_RegDeleteValueW
0x18002fa14  test    eax, eax
0x18002fa16  jz      short loc_18002FA7A
0x18002fa18  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002fa1f  jz      short loc_18002FA68
0x18002fa21  cmp     cs:qword_18004C640, r15
0x18002fa28  jz      short loc_18002FA7A
0x18002fa2a  lea     rdx, aRegdeletevalue_1; "RegDeleteValue(%ws) failed: %d"
0x18002fa31  mov     r8, rbx
0x18002fa34  mov     word ptr [rsp+870h+var_830], r15w
0x18002fa3a  mov     r9d, eax
0x18002fa3d  lea     rcx, [rsp+870h+var_830]
0x18002fa42  call    FormatRRASErrorString
0x18002fa47  mov     rdx, cs:qword_18004C640
0x18002fa4e  lea     r8, [rsp+870h+var_830]
0x18002fa53  mov     rcx, cs:gIphlpEtwContext
0x18002fa5a  mov     rax, cs:gIphlpTemplateFunc
0x18002fa61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa66  jmp     short loc_18002FA7A
0x18002fa68  lea     rcx, aRegdeletevalue_0; "RegDeleteValue(%ws) failed: %d"
0x18002fa6f  mov     r8d, eax
0x18002fa72  mov     rdx, rbx
0x18002fa75  call    TraceHlp
0x18002fa7a  mov     r8, [rsi+70h]
0x18002fa7e  test    r8, r8
0x18002fa81  jnz     short loc_18002FA8D
0x18002fa83  mov     [rsp+870h+var_834], r15d
0x18002fa88  lea     r8, [rsp+870h+var_834]
0x18002fa8d  mov     rcx, r8
0x18002fa90  call    MwszLength
0x18002fa95  mov     rcx, [rsp+870h+hKey]; hKey
0x18002fa9a  lea     rsi, aNameserverlist; "NameServerList"
0x18002faa1  add     eax, eax
0x18002faa3  mov     r9d, 7; dwType
0x18002faa9  mov     [rsp+870h+cbData], eax; cbData
0x18002faad  mov     rdx, rsi; lpValueName
0x18002fab0  mov     [rsp+870h+phkResult], r8; lpData
0x18002fab5  xor     r8d, r8d; Reserved
0x18002fab8  call    cs:__imp_RegSetValueExW
0x18002fabe  mov     ebx, eax
0x18002fac0  test    eax, eax
0x18002fac2  jz      short loc_18002FB26
0x18002fac4  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002facb  jz      short loc_18002FB14
0x18002facd  cmp     cs:qword_18004C640, r15
0x18002fad4  jz      short loc_18002FB26
0x18002fad6  mov     r8, rsi
0x18002fad9  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x18002fae0  mov     r9d, eax
0x18002fae3  mov     word ptr [rsp+870h+var_830], r15w
0x18002fae9  lea     rcx, [rsp+870h+var_830]
0x18002faee  call    FormatRRASErrorString
0x18002faf3  mov     rdx, cs:qword_18004C640
0x18002fafa  lea     r8, [rsp+870h+var_830]
0x18002faff  mov     rcx, cs:gIphlpEtwContext
0x18002fb06  mov     rax, cs:gIphlpTemplateFunc
0x18002fb0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb12  jmp     short loc_18002FB26
0x18002fb14  mov     rdx, rsi
0x18002fb17  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x18002fb1e  mov     r8d, eax
0x18002fb21  call    TraceHlp
0x18002fb26  mov     rcx, rdi; hMem
0x18002fb29  call    cs:__imp_LocalFree
0x18002fb2f  mov     rcx, [rsp+870h+hKey]; hKey
0x18002fb34  test    rcx, rcx
0x18002fb37  jz      short loc_18002FB3F
0x18002fb39  call    cs:__imp_RegCloseKey
0x18002fb3f  mov     eax, ebx
0x18002fb41  mov     rcx, [rbp+770h+var_30]
0x18002fb48  xor     rcx, rsp; StackCookie
0x18002fb4b  call    __security_check_cookie
0x18002fb50  mov     rbx, [rsp+870h+arg_10]
0x18002fb58  add     rsp, 850h
0x18002fb5f  pop     r15
0x18002fb61  pop     r14
0x18002fb63  pop     rdi
0x18002fb64  pop     rsi
0x18002fb65  pop     rbp
0x18002fb66  retn
```

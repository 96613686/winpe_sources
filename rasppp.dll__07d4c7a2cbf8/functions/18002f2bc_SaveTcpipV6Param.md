# SaveTcpipV6Param

- ea: `0x18002f2bc`
- end: `0x18002f77e`
- name: `SaveTcpipV6Param`
- size: `1218`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002f038`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x18002f2bc`
- `0x180030da4`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18002f35e`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18002f35e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f6ad`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f6ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f5dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f666`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f5dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f666`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f3c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f422`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f4ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f507`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f3c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f422`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f4ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f507`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f725`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f735`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f745`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f755`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f725`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f735`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f745`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f755`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002f525`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002f525`

## string_xrefs

- `0x18002f601`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18002f68c`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18002f610`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18002f695`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18002f6cb`: `RegDeleteValue(%ws) failed and returned %d`
- `0x18002f709`: `RegDeleteValue(%ws) failed and returned %d`
- `0x18002f3e6`: `RegOpenKeyEx(%ws) (v4) failed and returned %d`
- `0x18002f3f5`: `RegOpenKeyEx(%ws) (v4) failed and returned %d`
- `0x18002f4d1`: `RegOpenKeyEx(%ws) (v6) failed and returned %d`
- `0x18002f4e0`: `RegOpenKeyEx(%ws) (v6) failed and returned %d`
- `0x18002f54a`: `RegCreateKey(%ws) (v6) failed and returned %d`
- `0x18002f559`: `RegCreateKey(%ws) (v6) failed and returned %d`

## pseudocode

```c
__int64 __fastcall SaveTcpipV6Param(HKEY hKey, HKEY a2, __int64 a3)
{
  __int16 v6; // r8
  int v7; // r9d
  char v8; // dl
  unsigned int v9; // eax
  unsigned int v10; // ebx
  const WCHAR *v11; // r8
  const wchar_t *v12; // rdx
  const CHAR *v13; // rcx
  int v14; // r14d
  bool v15; // zf
  const BYTE *v16; // rcx
  __int64 v17; // rsi
  __int64 v18; // rax
  const BYTE *v19; // rcx
  wchar_t phkResult; // [rsp+20h] [rbp-E0h]
  long double cbData; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v24; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v25; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v26; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  hKeya = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  if ( gIsIphlpEtwTracingAvailable )
  {
    v8 = qword_18004C648;
    if ( qword_18004C648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C648,
        L"SaveTcpipV6Param");
  }
  else
  {
    TraceHlp("SaveTcpipV6Param");
  }
  o(*(_QWORD *)a3, v8, v6, v7, phkResult, cbData);
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004C648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C648,
        L"SaveTcpipV6Param");
  }
  else
  {
    TraceHlp("SaveTcpipV6Param");
  }
  v9 = RegOpenKeyExW(hKey, L"Interfaces", 0, 0x20006u, &hKeya);
  v10 = v9;
  if ( v9 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004C640 )
        goto LABEL_70;
      v11 = L"Interfaces";
LABEL_13:
      v12 = L"RegOpenKeyEx(%ws) (v4) failed and returned %d";
LABEL_67:
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, v12, v11, v9);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C640, &v28);
      goto LABEL_70;
    }
LABEL_14:
    v13 = "RegOpenKeyEx(%ws) (v4) failed and returned %d";
LABEL_69:
    TraceHlp(v13);
    goto LABEL_70;
  }
  v14 = 1;
  v9 = RegOpenKeyExW(hKeya, *(LPCWSTR *)a3, 0, 0x20006u, &v26);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 != 2 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004C640 )
          goto LABEL_70;
        v11 = *(const WCHAR **)a3;
        goto LABEL_13;
      }
      goto LABEL_14;
    }
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004C648 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
          gIphlpEtwContext,
          qword_18004C648,
          L"TcpIp V4 Interface sub-key not found continuing without it");
    }
    else
    {
      TraceHlp("TcpIp V4 Interface sub-key not found continuing without it");
    }
    v14 = 0;
  }
  v9 = RegOpenKeyExW(a2, L"Interfaces", 0, 0x20006u, &v25);
  v10 = v9;
  if ( v9 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004C640 )
        goto LABEL_70;
      v11 = L"Interfaces";
LABEL_30:
      v12 = L"RegOpenKeyEx(%ws) (v6) failed and returned %d";
      goto LABEL_67;
    }
    goto LABEL_31;
  }
  v9 = RegOpenKeyExW(v25, *(LPCWSTR *)a3, 0, 0x20006u, &v24);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 != 2 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004C640 )
          goto LABEL_70;
        v11 = *(const WCHAR **)a3;
        goto LABEL_30;
      }
LABEL_31:
      v13 = "RegOpenKeyEx(%ws) (v6) failed and returned %d";
      goto LABEL_69;
    }
    v9 = RegCreateKeyW(v25, *(LPCWSTR *)a3, &v24);
    v10 = v9;
    if ( v9 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004C640 )
          goto LABEL_70;
        v11 = *(const WCHAR **)a3;
        v12 = L"RegCreateKey(%ws) (v6) failed and returned %d";
        goto LABEL_67;
      }
      v13 = "RegCreateKey(%ws) (v6) failed and returned %d";
      goto LABEL_69;
    }
  }
  v15 = *(_QWORD *)(a3 + 16) == 0;
  v16 = (const BYTE *)&v23;
  v23 = 0;
  if ( !v15 )
    v16 = *(const BYTE **)(a3 + 16);
  v17 = -1;
  if ( v14 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)&v16[2 * v18] );
    v9 = RegSetValueExW(v26, L"Domain", 0, 1u, v16, 2 * v18 + 2);
    v10 = v9;
    if ( v9 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004C640 )
          goto LABEL_70;
        v11 = L"Domain";
        v12 = L"RegSetValueEx(%ws) failed and returned %d";
        goto LABEL_67;
      }
      v13 = "RegSetValueEx(%ws) failed and returned %d";
      goto LABEL_69;
    }
  }
  v19 = (const BYTE *)&v23;
  if ( *(_QWORD *)(a3 + 8) )
    v19 = *(const BYTE **)(a3 + 8);
  if ( *(_WORD *)v19 == 32 )
  {
    v9 = RegDeleteValueW(v24, L"NameServer");
    v10 = v9;
    if ( !v9 )
      goto LABEL_70;
    if ( !gIsIphlpEtwTracingAvailable )
    {
      v13 = "RegDeleteValue(%ws) failed and returned %d";
      goto LABEL_69;
    }
    if ( !qword_18004C640 )
      goto LABEL_70;
    v12 = L"RegDeleteValue(%ws) failed and returned %d";
    goto LABEL_66;
  }
  do
    ++v17;
  while ( *(_WORD *)&v19[2 * v17] );
  v9 = RegSetValueExW(v24, L"NameServer", 0, 1u, v19, 2 * v17 + 2);
  v10 = v9;
  if ( v9 )
  {
    if ( !gIsIphlpEtwTracingAvailable )
    {
      v13 = "RegSetValueEx(%ws) failed and returned %d";
      goto LABEL_69;
    }
    if ( !qword_18004C640 )
      goto LABEL_70;
    v12 = L"RegSetValueEx(%ws) failed and returned %d";
LABEL_66:
    v11 = L"NameServer";
    goto LABEL_67;
  }
LABEL_70:
  if ( v26 )
    RegCloseKey(v26);
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v24 )
    RegCloseKey(v24);
  if ( v25 )
    RegCloseKey(v25);
  return v10;
}

```

## disassembly

```asm
0x18002f2bc  push    rbp
0x18002f2be  push    rbx
0x18002f2bf  push    rsi
0x18002f2c0  push    rdi
0x18002f2c1  push    r12
0x18002f2c3  push    r14
0x18002f2c5  push    r15
0x18002f2c7  lea     rbp, [rsp-770h]
0x18002f2cf  sub     rsp, 870h
0x18002f2d6  mov     rax, cs:__security_cookie
0x18002f2dd  xor     rax, rsp
0x18002f2e0  mov     [rbp+7A0h+var_40], rax
0x18002f2e7  xor     r15d, r15d
0x18002f2ea  mov     rdi, r8
0x18002f2ed  mov     rsi, rdx
0x18002f2f0  mov     [rsp+8A0h+hKey], r15
0x18002f2f5  mov     rbx, rcx
0x18002f2f8  mov     [rsp+8A0h+var_858], r15
0x18002f2fd  xor     edx, edx; Val
0x18002f2ff  mov     [rsp+8A0h+var_860], r15
0x18002f304  mov     r8d, 7FCh; Size
0x18002f30a  mov     [rsp+8A0h+var_868], r15
0x18002f30f  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18002f314  mov     [rsp+8A0h+var_840], r15d
0x18002f319  call    memset_0
0x18002f31e  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f325  jz      short loc_18002F34F
0x18002f327  mov     rdx, cs:qword_18004C648
0x18002f32e  test    rdx, rdx
0x18002f331  jz      short loc_18002F35B
0x18002f333  mov     rcx, cs:gIphlpEtwContext
0x18002f33a  lea     r8, aSavetcpipv6par; "SaveTcpipV6Param"
0x18002f341  mov     rax, cs:gIphlpTemplateFunc
0x18002f348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f34d  jmp     short loc_18002F35B
0x18002f34f  lea     rcx, aSavetcpipv6par_0; "SaveTcpipV6Param"
0x18002f356  call    TraceHlp
0x18002f35b  mov     rcx, [rdi]
0x18002f35e  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18002f364  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f36b  jz      short loc_18002F395
0x18002f36d  mov     rdx, cs:qword_18004C648
0x18002f374  test    rdx, rdx
0x18002f377  jz      short loc_18002F3A1
0x18002f379  mov     rcx, cs:gIphlpEtwContext
0x18002f380  lea     r8, aSavetcpipv6par; "SaveTcpipV6Param"
0x18002f387  mov     rax, cs:gIphlpTemplateFunc
0x18002f38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f393  jmp     short loc_18002F3A1
0x18002f395  lea     rcx, aSavetcpipv6par_0; "SaveTcpipV6Param"
0x18002f39c  call    TraceHlp
0x18002f3a1  lea     rax, [rsp+8A0h+hKey]
0x18002f3a6  mov     r9d, 20006h; samDesired
0x18002f3ac  lea     r12, aInterfaces; "Interfaces"
0x18002f3b3  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18002f3b8  mov     rdx, r12; lpSubKey
0x18002f3bb  xor     r8d, r8d; ulOptions
0x18002f3be  mov     rcx, rbx; hKey
0x18002f3c1  call    cs:__imp_RegOpenKeyExW
0x18002f3c7  mov     ebx, eax
0x18002f3c9  test    eax, eax
0x18002f3cb  jz      short loc_18002F401
0x18002f3cd  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f3d4  jz      short loc_18002F3F2
0x18002f3d6  cmp     cs:qword_18004C640, r15
0x18002f3dd  jz      loc_18002F71B
0x18002f3e3  mov     r8, r12
0x18002f3e6  lea     rdx, aRegopenkeyexWs_1; "RegOpenKeyEx(%ws) (v4) failed and retur"...
0x18002f3ed  jmp     loc_18002F6D5
0x18002f3f2  mov     rdx, r12
0x18002f3f5  lea     rcx, aRegopenkeyexWs_4; "RegOpenKeyEx(%ws) (v4) failed and retur"...
0x18002f3fc  jmp     loc_18002F713
0x18002f401  mov     rdx, [rdi]; lpSubKey
0x18002f404  lea     rax, [rsp+8A0h+var_858]
0x18002f409  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002f40e  mov     r9d, 20006h; samDesired
0x18002f414  xor     r8d, r8d; ulOptions
0x18002f417  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18002f41c  mov     r14d, 1
0x18002f422  call    cs:__imp_RegOpenKeyExW
0x18002f428  mov     ebx, eax
0x18002f42a  test    eax, eax
0x18002f42c  jz      short loc_18002F493
0x18002f42e  cmp     eax, 2
0x18002f431  jz      short loc_18002F453
0x18002f433  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f43a  jz      short loc_18002F44E
0x18002f43c  cmp     cs:qword_18004C640, r15
0x18002f443  jz      loc_18002F71B
0x18002f449  mov     r8, [rdi]
0x18002f44c  jmp     short loc_18002F3E6
0x18002f44e  mov     rdx, [rdi]
0x18002f451  jmp     short loc_18002F3F5
0x18002f453  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f45a  jz      short loc_18002F484
0x18002f45c  mov     rdx, cs:qword_18004C648
0x18002f463  test    rdx, rdx
0x18002f466  jz      short loc_18002F490
0x18002f468  mov     rcx, cs:gIphlpEtwContext
0x18002f46f  lea     r8, aTcpipV4Interfa; "TcpIp V4 Interface sub-key not found co"...
0x18002f476  mov     rax, cs:gIphlpTemplateFunc
0x18002f47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f482  jmp     short loc_18002F490
0x18002f484  lea     rcx, aTcpipV4Interfa_0; "TcpIp V4 Interface sub-key not found co"...
0x18002f48b  call    TraceHlp
0x18002f490  mov     r14d, r15d
0x18002f493  lea     rax, [rsp+8A0h+var_860]
0x18002f498  mov     r9d, 20006h; samDesired
0x18002f49e  xor     r8d, r8d; ulOptions
0x18002f4a1  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18002f4a6  mov     rdx, r12; lpSubKey
0x18002f4a9  mov     rcx, rsi; hKey
0x18002f4ac  call    cs:__imp_RegOpenKeyExW
0x18002f4b2  mov     ebx, eax
0x18002f4b4  test    eax, eax
0x18002f4b6  jz      short loc_18002F4EC
0x18002f4b8  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f4bf  jz      short loc_18002F4DD
0x18002f4c1  cmp     cs:qword_18004C640, r15
0x18002f4c8  jz      loc_18002F71B
0x18002f4ce  mov     r8, r12
0x18002f4d1  lea     rdx, aRegopenkeyexWs_0; "RegOpenKeyEx(%ws) (v6) failed and retur"...
0x18002f4d8  jmp     loc_18002F6D5
0x18002f4dd  mov     rdx, r12
0x18002f4e0  lea     rcx, aRegopenkeyexWs_3; "RegOpenKeyEx(%ws) (v6) failed and retur"...
0x18002f4e7  jmp     loc_18002F713
0x18002f4ec  mov     rdx, [rdi]; lpSubKey
0x18002f4ef  lea     rax, [rsp+8A0h+var_868]
0x18002f4f4  mov     rcx, [rsp+8A0h+var_860]; hKey
0x18002f4f9  mov     r9d, 20006h; samDesired
0x18002f4ff  xor     r8d, r8d; ulOptions
0x18002f502  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18002f507  call    cs:__imp_RegOpenKeyExW
0x18002f50d  mov     ebx, eax
0x18002f50f  test    eax, eax
0x18002f511  jz      short loc_18002F58B
0x18002f513  cmp     eax, 2
0x18002f516  jnz     short loc_18002F565
0x18002f518  mov     rdx, [rdi]; lpSubKey
0x18002f51b  lea     r8, [rsp+8A0h+var_868]; phkResult
0x18002f520  mov     rcx, [rsp+8A0h+var_860]; hKey
0x18002f525  call    cs:__imp_RegCreateKeyW
0x18002f52b  mov     ebx, eax
0x18002f52d  test    eax, eax
0x18002f52f  jz      short loc_18002F58B
0x18002f531  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f538  jz      short loc_18002F556
0x18002f53a  cmp     cs:qword_18004C640, r15
0x18002f541  jz      loc_18002F71B
0x18002f547  mov     r8, [rdi]
0x18002f54a  lea     rdx, aRegcreatekeyWs_2; "RegCreateKey(%ws) (v6) failed and retur"...
0x18002f551  jmp     loc_18002F6D5
0x18002f556  mov     rdx, [rdi]
0x18002f559  lea     rcx, aRegcreatekeyWs_0; "RegCreateKey(%ws) (v6) failed and retur"...
0x18002f560  jmp     loc_18002F713
0x18002f565  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f56c  jz      short loc_18002F583
0x18002f56e  cmp     cs:qword_18004C640, r15
0x18002f575  jz      loc_18002F71B
0x18002f57b  mov     r8, [rdi]
0x18002f57e  jmp     loc_18002F4D1
0x18002f583  mov     rdx, [rdi]
0x18002f586  jmp     loc_18002F4E0
0x18002f58b  cmp     [rdi+10h], r15
0x18002f58f  lea     rcx, [rsp+8A0h+var_870]
0x18002f594  mov     [rsp+8A0h+var_870], r15d
0x18002f599  cmovnz  rcx, [rdi+10h]
0x18002f59e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002f5a2  test    r14d, r14d
0x18002f5a5  jz      short loc_18002F61C
0x18002f5a7  mov     rax, rsi
0x18002f5aa  inc     rax
0x18002f5ad  cmp     [rcx+rax*2], r15w
0x18002f5b2  jnz     short loc_18002F5AA
0x18002f5b4  lea     eax, ds:2[rax*2]
0x18002f5bb  mov     r9d, 1; dwType
0x18002f5c1  mov     dword ptr [rsp+8A0h+cbData], eax; cbData
0x18002f5c5  lea     r14, aDomain; "Domain"
0x18002f5cc  mov     [rsp+8A0h+phkResult], rcx; lpData
0x18002f5d1  xor     r8d, r8d; Reserved
0x18002f5d4  mov     rcx, [rsp+8A0h+var_858]; hKey
0x18002f5d9  mov     rdx, r14; lpValueName
0x18002f5dc  call    cs:__imp_RegSetValueExW
0x18002f5e2  mov     ebx, eax
0x18002f5e4  test    eax, eax
0x18002f5e6  jz      short loc_18002F61C
0x18002f5e8  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f5ef  jz      short loc_18002F60D
0x18002f5f1  cmp     cs:qword_18004C640, r15
0x18002f5f8  jz      loc_18002F71B
0x18002f5fe  mov     r8, r14
0x18002f601  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x18002f608  jmp     loc_18002F6D5
0x18002f60d  mov     rdx, r14
0x18002f610  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x18002f617  jmp     loc_18002F713
0x18002f61c  cmp     [rdi+8], r15
0x18002f620  lea     rcx, [rsp+8A0h+var_870]
0x18002f625  mov     eax, 20h ; ' '
0x18002f62a  cmovnz  rcx, [rdi+8]
0x18002f62f  cmp     ax, [rcx]
0x18002f632  jz      short loc_18002F69E
0x18002f634  inc     rsi
0x18002f637  cmp     [rcx+rsi*2], r15w
0x18002f63c  jnz     short loc_18002F634
0x18002f63e  lea     eax, ds:2[rsi*2]
0x18002f645  mov     r9d, 1; dwType
0x18002f64b  mov     dword ptr [rsp+8A0h+cbData], eax; cbData
0x18002f64f  lea     rdi, aNameserver; "NameServer"
0x18002f656  mov     [rsp+8A0h+phkResult], rcx; lpData
0x18002f65b  xor     r8d, r8d; Reserved
0x18002f65e  mov     rcx, [rsp+8A0h+var_868]; hKey
0x18002f663  mov     rdx, rdi; lpValueName
0x18002f666  call    cs:__imp_RegSetValueExW
0x18002f66c  mov     ebx, eax
0x18002f66e  test    eax, eax
0x18002f670  jz      loc_18002F71B
0x18002f676  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f67d  jz      short loc_18002F695
0x18002f67f  cmp     cs:qword_18004C640, r15
0x18002f686  jz      loc_18002F71B
0x18002f68c  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x18002f693  jmp     short loc_18002F6D2
0x18002f695  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x18002f69c  jmp     short loc_18002F710
0x18002f69e  mov     rcx, [rsp+8A0h+var_868]; hKey
0x18002f6a3  lea     rdi, aNameserver; "NameServer"
0x18002f6aa  mov     rdx, rdi; lpValueName
0x18002f6ad  call    cs:__imp_RegDeleteValueW
0x18002f6b3  mov     ebx, eax
0x18002f6b5  test    eax, eax
0x18002f6b7  jz      short loc_18002F71B
0x18002f6b9  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f6c0  jz      short loc_18002F709
0x18002f6c2  cmp     cs:qword_18004C640, r15
0x18002f6c9  jz      short loc_18002F71B
0x18002f6cb  lea     rdx, aRegdeletevalue; "RegDeleteValue(%ws) failed and returned"...
0x18002f6d2  mov     r8, rdi
0x18002f6d5  mov     r9d, eax
0x18002f6d8  mov     word ptr [rsp+8A0h+var_840], r15w
0x18002f6de  lea     rcx, [rsp+8A0h+var_840]
0x18002f6e3  call    FormatRRASErrorString
0x18002f6e8  mov     rdx, cs:qword_18004C640
0x18002f6ef  lea     r8, [rsp+8A0h+var_840]
0x18002f6f4  mov     rcx, cs:gIphlpEtwContext
0x18002f6fb  mov     rax, cs:gIphlpTemplateFunc
0x18002f702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f707  jmp     short loc_18002F71B
0x18002f709  lea     rcx, aRegdeletevalue_2; "RegDeleteValue(%ws) failed and returned"...
0x18002f710  mov     rdx, rdi
0x18002f713  mov     r8d, eax
0x18002f716  call    TraceHlp
0x18002f71b  mov     rcx, [rsp+8A0h+var_858]; hKey
0x18002f720  test    rcx, rcx
0x18002f723  jz      short loc_18002F72B
0x18002f725  call    cs:__imp_RegCloseKey
0x18002f72b  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002f730  test    rcx, rcx
0x18002f733  jz      short loc_18002F73B
0x18002f735  call    cs:__imp_RegCloseKey
0x18002f73b  mov     rcx, [rsp+8A0h+var_868]; hKey
0x18002f740  test    rcx, rcx
0x18002f743  jz      short loc_18002F74B
0x18002f745  call    cs:__imp_RegCloseKey
0x18002f74b  mov     rcx, [rsp+8A0h+var_860]; hKey
0x18002f750  test    rcx, rcx
0x18002f753  jz      short loc_18002F75B
0x18002f755  call    cs:__imp_RegCloseKey
0x18002f75b  mov     eax, ebx
0x18002f75d  mov     rcx, [rbp+7A0h+var_40]
0x18002f764  xor     rcx, rsp; StackCookie
0x18002f767  call    __security_check_cookie
0x18002f76c  add     rsp, 870h
0x18002f773  pop     r15
0x18002f775  pop     r14
0x18002f777  pop     r12
0x18002f779  pop     rdi
0x18002f77a  pop     rsi
0x18002f77b  pop     rbx
0x18002f77c  pop     rbp
0x18002f77d  retn
```

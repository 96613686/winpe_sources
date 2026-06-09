# SaveTcpipV6Param

- ea: `0x1800306d4`
- end: `0x180030be5`
- name: `SaveTcpipV6Param`
- size: `1297`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180030434`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x1800306d4`
- `0x18003230c`
- `0x180034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180030776`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180030776`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030af5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030af5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030a18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030aa8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030a18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030aa8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800307df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030846`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800308d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030937`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800307df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030846`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800308d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030937`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030bb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030bb5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003095b`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003095b`

## string_xrefs

- `0x180030a43`: `RegSetValueEx(%ws) failed and returned %d`
- `0x180030ad4`: `RegSetValueEx(%ws) failed and returned %d`
- `0x180030a52`: `RegSetValueEx(%ws) failed and returned %d`
- `0x180030add`: `RegSetValueEx(%ws) failed and returned %d`
- `0x180030b19`: `RegDeleteValue(%ws) failed and returned %d`
- `0x180030b57`: `RegDeleteValue(%ws) failed and returned %d`
- `0x18003080a`: `RegOpenKeyEx(%ws) (v4) failed and returned %d`
- `0x180030819`: `RegOpenKeyEx(%ws) (v4) failed and returned %d`
- `0x180030901`: `RegOpenKeyEx(%ws) (v6) failed and returned %d`
- `0x180030910`: `RegOpenKeyEx(%ws) (v6) failed and returned %d`
- `0x180030986`: `RegCreateKey(%ws) (v6) failed and returned %d`
- `0x180030995`: `RegCreateKey(%ws) (v6) failed and returned %d`

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
    v8 = qword_18004D648;
    if ( qword_18004D648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004D648,
        L"SaveTcpipV6Param");
  }
  else
  {
    TraceHlp("SaveTcpipV6Param");
  }
  o(*(_QWORD *)a3, v8, v6, v7, phkResult, cbData);
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004D648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004D648,
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
      if ( !qword_18004D640 )
        goto LABEL_70;
      v11 = L"Interfaces";
LABEL_13:
      v12 = L"RegOpenKeyEx(%ws) (v4) failed and returned %d";
LABEL_67:
      LOWORD(v28) = 0;
      FormatRRASErrorString((wchar_t *)&v28, v12, v11, v9);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D640, &v28);
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
        if ( !qword_18004D640 )
          goto LABEL_70;
        v11 = *(const WCHAR **)a3;
        goto LABEL_13;
      }
      goto LABEL_14;
    }
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004D648 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
          gIphlpEtwContext,
          qword_18004D648,
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
      if ( !qword_18004D640 )
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
        if ( !qword_18004D640 )
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
        if ( !qword_18004D640 )
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
        if ( !qword_18004D640 )
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
    if ( !qword_18004D640 )
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
    if ( !qword_18004D640 )
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
0x1800306d4  push    rbp
0x1800306d6  push    rbx
0x1800306d7  push    rsi
0x1800306d8  push    rdi
0x1800306d9  push    r12
0x1800306db  push    r14
0x1800306dd  push    r15
0x1800306df  lea     rbp, [rsp-770h]
0x1800306e7  sub     rsp, 870h
0x1800306ee  mov     rax, cs:__security_cookie
0x1800306f5  xor     rax, rsp
0x1800306f8  mov     [rbp+7A0h+var_40], rax
0x1800306ff  xor     r15d, r15d
0x180030702  mov     rdi, r8
0x180030705  mov     rsi, rdx
0x180030708  mov     [rsp+8A0h+hKey], r15
0x18003070d  mov     rbx, rcx
0x180030710  mov     [rsp+8A0h+var_858], r15
0x180030715  xor     edx, edx; Val
0x180030717  mov     [rsp+8A0h+var_860], r15
0x18003071c  mov     r8d, 7FCh; Size
0x180030722  mov     [rsp+8A0h+var_868], r15
0x180030727  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18003072c  mov     [rsp+8A0h+var_840], r15d
0x180030731  call    memset_0
0x180030736  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18003073d  jz      short loc_180030767
0x18003073f  mov     rdx, qword ptr cs:xmmword_18004D648
0x180030746  test    rdx, rdx
0x180030749  jz      short loc_180030773
0x18003074b  mov     rcx, cs:gIphlpEtwContext
0x180030752  lea     r8, aSavetcpipv6par; "SaveTcpipV6Param"
0x180030759  mov     rax, cs:gIphlpTemplateFunc
0x180030760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030765  jmp     short loc_180030773
0x180030767  lea     rcx, aSavetcpipv6par_0; "SaveTcpipV6Param"
0x18003076e  call    TraceHlp
0x180030773  mov     rcx, [rdi]
0x180030776  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18003077d  nop     dword ptr [rax+rax+00h]
0x180030782  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030789  jz      short loc_1800307B3
0x18003078b  mov     rdx, qword ptr cs:xmmword_18004D648
0x180030792  test    rdx, rdx
0x180030795  jz      short loc_1800307BF
0x180030797  mov     rcx, cs:gIphlpEtwContext
0x18003079e  lea     r8, aSavetcpipv6par; "SaveTcpipV6Param"
0x1800307a5  mov     rax, cs:gIphlpTemplateFunc
0x1800307ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307b1  jmp     short loc_1800307BF
0x1800307b3  lea     rcx, aSavetcpipv6par_0; "SaveTcpipV6Param"
0x1800307ba  call    TraceHlp
0x1800307bf  lea     rax, [rsp+8A0h+hKey]
0x1800307c4  mov     r9d, 20006h; samDesired
0x1800307ca  lea     r12, aInterfaces; "Interfaces"
0x1800307d1  mov     [rsp+8A0h+phkResult], rax; phkResult
0x1800307d6  mov     rdx, r12; lpSubKey
0x1800307d9  xor     r8d, r8d; ulOptions
0x1800307dc  mov     rcx, rbx; hKey
0x1800307df  call    cs:__imp_RegOpenKeyExW
0x1800307e6  nop     dword ptr [rax+rax+00h]
0x1800307eb  mov     ebx, eax
0x1800307ed  test    eax, eax
0x1800307ef  jz      short loc_180030825
0x1800307f1  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x1800307f8  jz      short loc_180030816
0x1800307fa  cmp     cs:qword_18004D640, r15
0x180030801  jz      loc_180030B69
0x180030807  mov     r8, r12
0x18003080a  lea     rdx, aRegopenkeyexWs_1; "RegOpenKeyEx(%ws) (v4) failed and retur"...
0x180030811  jmp     loc_180030B23
0x180030816  mov     rdx, r12
0x180030819  lea     rcx, aRegopenkeyexWs_4; "RegOpenKeyEx(%ws) (v4) failed and retur"...
0x180030820  jmp     loc_180030B61
0x180030825  mov     rdx, [rdi]; lpSubKey
0x180030828  lea     rax, [rsp+8A0h+var_858]
0x18003082d  mov     rcx, [rsp+8A0h+hKey]; hKey
0x180030832  mov     r9d, 20006h; samDesired
0x180030838  xor     r8d, r8d; ulOptions
0x18003083b  mov     [rsp+8A0h+phkResult], rax; phkResult
0x180030840  mov     r14d, 1
0x180030846  call    cs:__imp_RegOpenKeyExW
0x18003084d  nop     dword ptr [rax+rax+00h]
0x180030852  mov     ebx, eax
0x180030854  test    eax, eax
0x180030856  jz      short loc_1800308BD
0x180030858  cmp     eax, 2
0x18003085b  jz      short loc_18003087D
0x18003085d  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030864  jz      short loc_180030878
0x180030866  cmp     cs:qword_18004D640, r15
0x18003086d  jz      loc_180030B69
0x180030873  mov     r8, [rdi]
0x180030876  jmp     short loc_18003080A
0x180030878  mov     rdx, [rdi]
0x18003087b  jmp     short loc_180030819
0x18003087d  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030884  jz      short loc_1800308AE
0x180030886  mov     rdx, qword ptr cs:xmmword_18004D648
0x18003088d  test    rdx, rdx
0x180030890  jz      short loc_1800308BA
0x180030892  mov     rcx, cs:gIphlpEtwContext
0x180030899  lea     r8, aTcpipV4Interfa; "TcpIp V4 Interface sub-key not found co"...
0x1800308a0  mov     rax, cs:gIphlpTemplateFunc
0x1800308a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308ac  jmp     short loc_1800308BA
0x1800308ae  lea     rcx, aTcpipV4Interfa_0; "TcpIp V4 Interface sub-key not found co"...
0x1800308b5  call    TraceHlp
0x1800308ba  mov     r14d, r15d
0x1800308bd  lea     rax, [rsp+8A0h+var_860]
0x1800308c2  mov     r9d, 20006h; samDesired
0x1800308c8  xor     r8d, r8d; ulOptions
0x1800308cb  mov     [rsp+8A0h+phkResult], rax; phkResult
0x1800308d0  mov     rdx, r12; lpSubKey
0x1800308d3  mov     rcx, rsi; hKey
0x1800308d6  call    cs:__imp_RegOpenKeyExW
0x1800308dd  nop     dword ptr [rax+rax+00h]
0x1800308e2  mov     ebx, eax
0x1800308e4  test    eax, eax
0x1800308e6  jz      short loc_18003091C
0x1800308e8  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x1800308ef  jz      short loc_18003090D
0x1800308f1  cmp     cs:qword_18004D640, r15
0x1800308f8  jz      loc_180030B69
0x1800308fe  mov     r8, r12
0x180030901  lea     rdx, aRegopenkeyexWs_0; "RegOpenKeyEx(%ws) (v6) failed and retur"...
0x180030908  jmp     loc_180030B23
0x18003090d  mov     rdx, r12
0x180030910  lea     rcx, aRegopenkeyexWs_3; "RegOpenKeyEx(%ws) (v6) failed and retur"...
0x180030917  jmp     loc_180030B61
0x18003091c  mov     rdx, [rdi]; lpSubKey
0x18003091f  lea     rax, [rsp+8A0h+var_868]
0x180030924  mov     rcx, [rsp+8A0h+var_860]; hKey
0x180030929  mov     r9d, 20006h; samDesired
0x18003092f  xor     r8d, r8d; ulOptions
0x180030932  mov     [rsp+8A0h+phkResult], rax; phkResult
0x180030937  call    cs:__imp_RegOpenKeyExW
0x18003093e  nop     dword ptr [rax+rax+00h]
0x180030943  mov     ebx, eax
0x180030945  test    eax, eax
0x180030947  jz      short loc_1800309C7
0x180030949  cmp     eax, 2
0x18003094c  jnz     short loc_1800309A1
0x18003094e  mov     rdx, [rdi]; lpSubKey
0x180030951  lea     r8, [rsp+8A0h+var_868]; phkResult
0x180030956  mov     rcx, [rsp+8A0h+var_860]; hKey
0x18003095b  call    cs:__imp_RegCreateKeyW
0x180030962  nop     dword ptr [rax+rax+00h]
0x180030967  mov     ebx, eax
0x180030969  test    eax, eax
0x18003096b  jz      short loc_1800309C7
0x18003096d  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030974  jz      short loc_180030992
0x180030976  cmp     cs:qword_18004D640, r15
0x18003097d  jz      loc_180030B69
0x180030983  mov     r8, [rdi]
0x180030986  lea     rdx, aRegcreatekeyWs_2; "RegCreateKey(%ws) (v6) failed and retur"...
0x18003098d  jmp     loc_180030B23
0x180030992  mov     rdx, [rdi]
0x180030995  lea     rcx, aRegcreatekeyWs_0; "RegCreateKey(%ws) (v6) failed and retur"...
0x18003099c  jmp     loc_180030B61
0x1800309a1  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x1800309a8  jz      short loc_1800309BF
0x1800309aa  cmp     cs:qword_18004D640, r15
0x1800309b1  jz      loc_180030B69
0x1800309b7  mov     r8, [rdi]
0x1800309ba  jmp     loc_180030901
0x1800309bf  mov     rdx, [rdi]
0x1800309c2  jmp     loc_180030910
0x1800309c7  cmp     [rdi+10h], r15
0x1800309cb  lea     rcx, [rsp+8A0h+var_870]
0x1800309d0  mov     [rsp+8A0h+var_870], r15d
0x1800309d5  cmovnz  rcx, [rdi+10h]
0x1800309da  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800309de  test    r14d, r14d
0x1800309e1  jz      short loc_180030A5E
0x1800309e3  mov     rax, rsi
0x1800309e6  inc     rax
0x1800309e9  cmp     [rcx+rax*2], r15w
0x1800309ee  jnz     short loc_1800309E6
0x1800309f0  lea     eax, ds:2[rax*2]
0x1800309f7  mov     r9d, 1; dwType
0x1800309fd  mov     dword ptr [rsp+8A0h+cbData], eax; cbData
0x180030a01  lea     r14, aDomain; "Domain"
0x180030a08  mov     [rsp+8A0h+phkResult], rcx; lpData
0x180030a0d  xor     r8d, r8d; Reserved
0x180030a10  mov     rcx, [rsp+8A0h+var_858]; hKey
0x180030a15  mov     rdx, r14; lpValueName
0x180030a18  call    cs:__imp_RegSetValueExW
0x180030a1f  nop     dword ptr [rax+rax+00h]
0x180030a24  mov     ebx, eax
0x180030a26  test    eax, eax
0x180030a28  jz      short loc_180030A5E
0x180030a2a  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030a31  jz      short loc_180030A4F
0x180030a33  cmp     cs:qword_18004D640, r15
0x180030a3a  jz      loc_180030B69
0x180030a40  mov     r8, r14
0x180030a43  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x180030a4a  jmp     loc_180030B23
0x180030a4f  mov     rdx, r14
0x180030a52  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x180030a59  jmp     loc_180030B61
0x180030a5e  cmp     [rdi+8], r15
0x180030a62  lea     rcx, [rsp+8A0h+var_870]
0x180030a67  mov     eax, 20h ; ' '
0x180030a6c  cmovnz  rcx, [rdi+8]
0x180030a71  cmp     ax, [rcx]
0x180030a74  jz      short loc_180030AE6
0x180030a76  inc     rsi
0x180030a79  cmp     [rcx+rsi*2], r15w
0x180030a7e  jnz     short loc_180030A76
0x180030a80  lea     eax, ds:2[rsi*2]
0x180030a87  mov     r9d, 1; dwType
0x180030a8d  mov     dword ptr [rsp+8A0h+cbData], eax; cbData
0x180030a91  lea     rdi, aNameserver; "NameServer"
0x180030a98  mov     [rsp+8A0h+phkResult], rcx; lpData
0x180030a9d  xor     r8d, r8d; Reserved
0x180030aa0  mov     rcx, [rsp+8A0h+var_868]; hKey
0x180030aa5  mov     rdx, rdi; lpValueName
0x180030aa8  call    cs:__imp_RegSetValueExW
0x180030aaf  nop     dword ptr [rax+rax+00h]
0x180030ab4  mov     ebx, eax
0x180030ab6  test    eax, eax
0x180030ab8  jz      loc_180030B69
0x180030abe  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030ac5  jz      short loc_180030ADD
0x180030ac7  cmp     cs:qword_18004D640, r15
0x180030ace  jz      loc_180030B69
0x180030ad4  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x180030adb  jmp     short loc_180030B20
0x180030add  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x180030ae4  jmp     short loc_180030B5E
0x180030ae6  mov     rcx, [rsp+8A0h+var_868]; hKey
0x180030aeb  lea     rdi, aNameserver; "NameServer"
0x180030af2  mov     rdx, rdi; lpValueName
0x180030af5  call    cs:__imp_RegDeleteValueW
0x180030afc  nop     dword ptr [rax+rax+00h]
0x180030b01  mov     ebx, eax
0x180030b03  test    eax, eax
0x180030b05  jz      short loc_180030B69
0x180030b07  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030b0e  jz      short loc_180030B57
0x180030b10  cmp     cs:qword_18004D640, r15
0x180030b17  jz      short loc_180030B69
0x180030b19  lea     rdx, aRegdeletevalue; "RegDeleteValue(%ws) failed and returned"...
0x180030b20  mov     r8, rdi
0x180030b23  mov     r9d, eax
0x180030b26  mov     word ptr [rsp+8A0h+var_840], r15w
0x180030b2c  lea     rcx, [rsp+8A0h+var_840]
0x180030b31  call    FormatRRASErrorString
0x180030b36  mov     rdx, cs:qword_18004D640
0x180030b3d  lea     r8, [rsp+8A0h+var_840]
0x180030b42  mov     rcx, cs:gIphlpEtwContext
0x180030b49  mov     rax, cs:gIphlpTemplateFunc
0x180030b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b55  jmp     short loc_180030B69
0x180030b57  lea     rcx, aRegdeletevalue_2; "RegDeleteValue(%ws) failed and returned"...
0x180030b5e  mov     rdx, rdi
0x180030b61  mov     r8d, eax
0x180030b64  call    TraceHlp
0x180030b69  mov     rcx, [rsp+8A0h+var_858]; hKey
0x180030b6e  test    rcx, rcx
0x180030b71  jz      short loc_180030B7F
0x180030b73  call    cs:__imp_RegCloseKey
0x180030b7a  nop     dword ptr [rax+rax+00h]
0x180030b7f  mov     rcx, [rsp+8A0h+hKey]; hKey
0x180030b84  test    rcx, rcx
0x180030b87  jz      short loc_180030B95
0x180030b89  call    cs:__imp_RegCloseKey
0x180030b90  nop     dword ptr [rax+rax+00h]
0x180030b95  mov     rcx, [rsp+8A0h+var_868]; hKey
0x180030b9a  test    rcx, rcx
0x180030b9d  jz      short loc_180030BAB
0x180030b9f  call    cs:__imp_RegCloseKey
0x180030ba6  nop     dword ptr [rax+rax+00h]
0x180030bab  mov     rcx, [rsp+8A0h+var_860]; hKey
0x180030bb0  test    rcx, rcx
0x180030bb3  jz      short loc_180030BC1
0x180030bb5  call    cs:__imp_RegCloseKey
0x180030bbc  nop     dword ptr [rax+rax+00h]
0x180030bc1  mov     eax, ebx
0x180030bc3  mov     rcx, [rbp+7A0h+var_40]
0x180030bca  xor     rcx, rsp; StackCookie
0x180030bcd  call    __security_check_cookie
0x180030bd2  add     rsp, 870h
0x180030bd9  pop     r15
0x180030bdb  pop     r14
0x180030bdd  pop     r12
0x180030bdf  pop     rdi
0x180030be0  pop     rsi
0x180030be1  pop     rbx
0x180030be2  pop     rbp
0x180030be3  retn
```

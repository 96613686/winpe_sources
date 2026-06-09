# SaveTcpipParam

- ea: `0x18002ffa4`
- end: `0x18003042c`
- name: `SaveTcpipParam`
- size: `1160`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002fce0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x18002ffa4`
- `0x180031010`
- `0x18003230c`
- `0x180034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003003b`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003003b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030363`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030363`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800301c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030242`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800302bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030316`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800301c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030242`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800302bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030316`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003006a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800300c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003006a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800300c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800303e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800303f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800303e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800303f7`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800300f2`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800300f2`

## string_xrefs

- `0x180030095`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x1800300a4`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18003011e`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x18003012e`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x1800301f3`: `RegSetValueEx(%ws) failed and returned %d`
- `0x180030342`: `RegSetValueEx(%ws) failed and returned %d`
- `0x180030206`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18003034b`: `RegSetValueEx(%ws) failed and returned %d`
- `0x180030387`: `RegDeleteValue(%ws) failed and returned %d`
- `0x1800303c5`: `RegDeleteValue(%ws) failed and returned %d`

## pseudocode

```c
__int64 __fastcall SaveTcpipParam(HKEY hKey, __int64 a2)
{
  __int16 v4; // r8
  int v5; // r9d
  char v6; // dl
  unsigned int v7; // eax
  unsigned int v8; // ebx
  const WCHAR *v9; // r8
  const wchar_t *v10; // rdx
  const CHAR *v11; // rcx
  size_t v12; // rdx
  const wchar_t *v13; // r8
  __int64 v14; // rsi
  const BYTE *v15; // r11
  const BYTE *v16; // r14
  size_t v17; // rdx
  STRSAFE_LPCWSTR v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  const WCHAR *v21; // r14
  bool v22; // zf
  const BYTE *v23; // rcx
  __int64 v24; // rax
  const BYTE *v25; // rcx
  wchar_t phkResult; // [rsp+20h] [rbp-E0h]
  const BYTE *phkResulta; // [rsp+20h] [rbp-E0h]
  long double cbData; // [rsp+28h] [rbp-D8h]
  HKEY v30; // [rsp+30h] [rbp-D0h] BYREF
  int v31; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v34[2044]; // [rsp+54h] [rbp-ACh] BYREF

  hKeya = 0;
  v30 = 0;
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  if ( gIsIphlpEtwTracingAvailable )
  {
    v6 = qword_18004D648;
    if ( qword_18004D648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004D648,
        L"SaveTcpipParam");
  }
  else
  {
    TraceHlp("SaveTcpipParam");
  }
  o(*(_QWORD *)(a2 + 8), v6, v4, v5, phkResult, cbData);
  v7 = RegOpenKeyExW(hKey, L"Interfaces", 0, 0x20006u, &hKeya);
  v8 = v7;
  if ( v7 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004D640 )
        goto LABEL_62;
      v9 = L"Interfaces";
LABEL_9:
      v10 = L"RegOpenKeyEx(%ws) failed and returned %d";
LABEL_59:
      LOWORD(v33) = 0;
      FormatRRASErrorString((wchar_t *)&v33, v10, v9, v7);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D640, &v33);
      goto LABEL_62;
    }
LABEL_10:
    v11 = "RegOpenKeyEx(%ws) failed and returned %d";
LABEL_61:
    TraceHlp(v11);
    goto LABEL_62;
  }
  v7 = RegOpenKeyExW(hKeya, *(LPCWSTR *)(a2 + 8), 0, 0x20006u, &v30);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 != 2 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004D640 )
          goto LABEL_62;
        v9 = *(const WCHAR **)(a2 + 8);
        goto LABEL_9;
      }
      goto LABEL_10;
    }
    v7 = RegCreateKeyW(hKeya, *(LPCWSTR *)(a2 + 8), &v30);
    v8 = v7;
    if ( v7 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004D640 )
          goto LABEL_62;
        v9 = *(const WCHAR **)(a2 + 8);
        v10 = L"RegCreateKey(%ws) (v4) failed and returned %d";
        goto LABEL_59;
      }
      v11 = "RegCreateKey(%ws) (v4) failed and returned %d";
      goto LABEL_61;
    }
  }
  v14 = -1;
  if ( *(_DWORD *)a2 == 1 )
  {
    v15 = (const BYTE *)(a2 + 16);
    if ( !*(_WORD *)(a2 + 16) || (v16 = (const BYTE *)(a2 + 58), !*(_WORD *)(a2 + 58)) )
    {
      StringCbCopyW((STRSAFE_LPWSTR)(a2 + 16), v12, v13);
      v16 = (const BYTE *)(a2 + 58);
      StringCbCopyW((STRSAFE_LPWSTR)(a2 + 58), v17, v18);
    }
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)&v15[2 * v19] );
    v7 = RegSetValueExW(v30, L"DhcpIPAddress", 0, 1u, v15, 2 * v19);
    v8 = v7;
    if ( v7 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004D640 )
          goto LABEL_62;
        v9 = L"DhcpIPAddress";
LABEL_32:
        v10 = L"RegSetValueEx(%ws) failed and returned %d";
        goto LABEL_59;
      }
      goto LABEL_33;
    }
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)&v16[2 * v20] );
    phkResulta = v16;
    v21 = L"DhcpSubnetMask";
    v7 = RegSetValueExW(v30, L"DhcpSubnetMask", 0, 1u, phkResulta, 2 * v20);
    v8 = v7;
    if ( v7 )
      goto LABEL_37;
  }
  v22 = *(_QWORD *)(a2 + 120) == 0;
  v23 = (const BYTE *)&v31;
  v31 = 0;
  v24 = -1;
  if ( !v22 )
    v23 = *(const BYTE **)(a2 + 120);
  do
    ++v24;
  while ( *(_WORD *)&v23[2 * v24] );
  v21 = L"Domain";
  v7 = RegSetValueExW(v30, L"Domain", 0, 1u, v23, 2 * v24 + 2);
  v8 = v7;
  if ( v7 )
  {
LABEL_37:
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004D640 )
        goto LABEL_62;
      v9 = v21;
      goto LABEL_32;
    }
LABEL_33:
    v11 = "RegSetValueEx(%ws) failed and returned %d";
    goto LABEL_61;
  }
  v25 = (const BYTE *)&v31;
  if ( *(_QWORD *)(a2 + 104) )
    v25 = *(const BYTE **)(a2 + 104);
  if ( *(_WORD *)v25 == 32 )
  {
    v7 = RegDeleteValueW(v30, L"NameServer");
    v8 = v7;
    if ( !v7 )
      goto LABEL_62;
    if ( !gIsIphlpEtwTracingAvailable )
    {
      v11 = "RegDeleteValue(%ws) failed and returned %d";
      goto LABEL_61;
    }
    if ( !qword_18004D640 )
      goto LABEL_62;
    v10 = L"RegDeleteValue(%ws) failed and returned %d";
    goto LABEL_58;
  }
  do
    ++v14;
  while ( *(_WORD *)&v25[2 * v14] );
  v7 = RegSetValueExW(v30, L"NameServer", 0, 1u, v25, 2 * v14 + 2);
  v8 = v7;
  if ( v7 )
  {
    if ( !gIsIphlpEtwTracingAvailable )
    {
      v11 = "RegSetValueEx(%ws) failed and returned %d";
      goto LABEL_61;
    }
    if ( !qword_18004D640 )
      goto LABEL_62;
    v10 = L"RegSetValueEx(%ws) failed and returned %d";
LABEL_58:
    v9 = L"NameServer";
    goto LABEL_59;
  }
LABEL_62:
  if ( v30 )
    RegCloseKey(v30);
  if ( hKeya )
    RegCloseKey(hKeya);
  return v8;
}

```

## disassembly

```asm
0x18002ffa4  mov     [rsp-8+arg_10], rbx
0x18002ffa9  push    rbp
0x18002ffaa  push    rsi
0x18002ffab  push    rdi
0x18002ffac  push    r14
0x18002ffae  push    r15
0x18002ffb0  lea     rbp, [rsp-760h]
0x18002ffb8  sub     rsp, 860h
0x18002ffbf  mov     rax, cs:__security_cookie
0x18002ffc6  xor     rax, rsp
0x18002ffc9  mov     [rbp+780h+var_30], rax
0x18002ffd0  xor     r15d, r15d
0x18002ffd3  mov     rdi, rdx
0x18002ffd6  mov     rbx, rcx
0x18002ffd9  mov     [rsp+880h+hKey], r15
0x18002ffde  xor     edx, edx; Val
0x18002ffe0  mov     [rsp+880h+var_850], r15
0x18002ffe5  lea     rcx, [rsp+880h+var_82C]; void *
0x18002ffea  mov     [rsp+880h+var_830], r15d
0x18002ffef  mov     r8d, 7FCh; Size
0x18002fff5  call    memset_0
0x18002fffa  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030001  jz      short loc_18003002B
0x180030003  mov     rdx, qword ptr cs:xmmword_18004D648
0x18003000a  test    rdx, rdx
0x18003000d  jz      short loc_180030037
0x18003000f  mov     rcx, cs:gIphlpEtwContext
0x180030016  lea     r8, aSavetcpipparam; "SaveTcpipParam"
0x18003001d  mov     rax, cs:gIphlpTemplateFunc
0x180030024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030029  jmp     short loc_180030037
0x18003002b  lea     rcx, aSavetcpipparam_0; "SaveTcpipParam"
0x180030032  call    TraceHlp
0x180030037  mov     rcx, [rdi+8]
0x18003003b  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180030042  nop     dword ptr [rax+rax+00h]
0x180030047  lea     rax, [rsp+880h+hKey]
0x18003004c  mov     r14d, 20006h
0x180030052  lea     rsi, aInterfaces; "Interfaces"
0x180030059  mov     [rsp+880h+phkResult], rax; phkResult
0x18003005e  mov     r9d, r14d; samDesired
0x180030061  mov     rdx, rsi; lpSubKey
0x180030064  xor     r8d, r8d; ulOptions
0x180030067  mov     rcx, rbx; hKey
0x18003006a  call    cs:__imp_RegOpenKeyExW
0x180030071  nop     dword ptr [rax+rax+00h]
0x180030076  mov     ebx, eax
0x180030078  test    eax, eax
0x18003007a  jz      short loc_1800300B0
0x18003007c  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030083  jz      short loc_1800300A1
0x180030085  cmp     cs:qword_18004D640, r15
0x18003008c  jz      loc_1800303D7
0x180030092  mov     r8, rsi
0x180030095  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18003009c  jmp     loc_180030391
0x1800300a1  mov     rdx, rsi
0x1800300a4  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x1800300ab  jmp     loc_1800303CF
0x1800300b0  mov     rdx, [rdi+8]; lpSubKey
0x1800300b4  lea     rax, [rsp+880h+var_850]
0x1800300b9  mov     rcx, [rsp+880h+hKey]; hKey
0x1800300be  mov     r9d, r14d; samDesired
0x1800300c1  xor     r8d, r8d; ulOptions
0x1800300c4  mov     [rsp+880h+phkResult], rax; phkResult
0x1800300c9  call    cs:__imp_RegOpenKeyExW
0x1800300d0  nop     dword ptr [rax+rax+00h]
0x1800300d5  mov     ebx, eax
0x1800300d7  test    eax, eax
0x1800300d9  jz      loc_180030162
0x1800300df  cmp     eax, 2
0x1800300e2  jnz     short loc_18003013A
0x1800300e4  mov     rdx, [rdi+8]; lpSubKey
0x1800300e8  lea     r8, [rsp+880h+var_850]; phkResult
0x1800300ed  mov     rcx, [rsp+880h+hKey]; hKey
0x1800300f2  call    cs:__imp_RegCreateKeyW
0x1800300f9  nop     dword ptr [rax+rax+00h]
0x1800300fe  mov     ebx, eax
0x180030100  test    eax, eax
0x180030102  jz      short loc_180030162
0x180030104  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18003010b  jz      short loc_18003012A
0x18003010d  cmp     cs:qword_18004D640, r15
0x180030114  jz      loc_1800303D7
0x18003011a  mov     r8, [rdi+8]
0x18003011e  lea     rdx, aRegcreatekeyWs_1; "RegCreateKey(%ws) (v4) failed and retur"...
0x180030125  jmp     loc_180030391
0x18003012a  mov     rdx, [rdi+8]
0x18003012e  lea     rcx, aRegcreatekeyWs; "RegCreateKey(%ws) (v4) failed and retur"...
0x180030135  jmp     loc_1800303CF
0x18003013a  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030141  jz      short loc_180030159
0x180030143  cmp     cs:qword_18004D640, r15
0x18003014a  jz      loc_1800303D7
0x180030150  mov     r8, [rdi+8]
0x180030154  jmp     loc_180030095
0x180030159  mov     rdx, [rdi+8]
0x18003015d  jmp     loc_1800300A4
0x180030162  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180030166  cmp     dword ptr [rdi], 1
0x180030169  jnz     loc_180030274
0x18003016f  lea     r11, [rdi+10h]
0x180030173  cmp     r15w, [r11]
0x180030177  jz      short loc_180030183
0x180030179  lea     r14, [rdi+3Ah]
0x18003017d  cmp     r15w, [r14]
0x180030181  jnz     short loc_180030197
0x180030183  mov     rcx, r11; pszDest
0x180030186  call    StringCbCopyW
0x18003018b  lea     r14, [rdi+3Ah]
0x18003018f  mov     rcx, r14; pszDest
0x180030192  call    StringCbCopyW
0x180030197  mov     rax, rsi
0x18003019a  inc     rax
0x18003019d  cmp     [r11+rax*2], r15w
0x1800301a2  jnz     short loc_18003019A
0x1800301a4  mov     rcx, [rsp+880h+var_850]; hKey
0x1800301a9  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x1800301b0  add     eax, eax
0x1800301b2  mov     r9d, 1; dwType
0x1800301b8  mov     dword ptr [rsp+880h+cbData], eax; cbData
0x1800301bc  xor     r8d, r8d; Reserved
0x1800301bf  mov     [rsp+880h+phkResult], r11; lpData
0x1800301c4  call    cs:__imp_RegSetValueExW
0x1800301cb  nop     dword ptr [rax+rax+00h]
0x1800301d0  mov     ebx, eax
0x1800301d2  test    eax, eax
0x1800301d4  jz      short loc_180030212
0x1800301d6  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x1800301dd  jz      short loc_1800301FF
0x1800301df  cmp     cs:qword_18004D640, r15
0x1800301e6  jz      loc_1800303D7
0x1800301ec  lea     r8, aDhcpipaddress; "DhcpIPAddress"
0x1800301f3  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x1800301fa  jmp     loc_180030391
0x1800301ff  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x180030206  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x18003020d  jmp     loc_1800303CF
0x180030212  mov     rax, rsi
0x180030215  inc     rax
0x180030218  cmp     [r14+rax*2], r15w
0x18003021d  jnz     short loc_180030215
0x18003021f  mov     rcx, [rsp+880h+var_850]; hKey
0x180030224  add     eax, eax
0x180030226  mov     dword ptr [rsp+880h+cbData], eax; cbData
0x18003022a  mov     r9d, 1; dwType
0x180030230  mov     [rsp+880h+phkResult], r14; lpData
0x180030235  xor     r8d, r8d; Reserved
0x180030238  lea     r14, aDhcpsubnetmask; "DhcpSubnetMask"
0x18003023f  mov     rdx, r14; lpValueName
0x180030242  call    cs:__imp_RegSetValueExW
0x180030249  nop     dword ptr [rax+rax+00h]
0x18003024e  mov     ebx, eax
0x180030250  test    eax, eax
0x180030252  jz      short loc_180030274
0x180030254  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18003025b  jz      short loc_18003026F
0x18003025d  cmp     cs:qword_18004D640, r15
0x180030264  jz      loc_1800303D7
0x18003026a  mov     r8, r14
0x18003026d  jmp     short loc_1800301F3
0x18003026f  mov     rdx, r14
0x180030272  jmp     short loc_180030206
0x180030274  cmp     [rdi+78h], r15
0x180030278  lea     rcx, [rsp+880h+var_848]
0x18003027d  mov     [rsp+880h+var_848], r15d
0x180030282  mov     rax, rsi
0x180030285  cmovnz  rcx, [rdi+78h]
0x18003028a  inc     rax
0x18003028d  cmp     [rcx+rax*2], r15w
0x180030292  jnz     short loc_18003028A
0x180030294  lea     eax, ds:2[rax*2]
0x18003029b  mov     r9d, 1; dwType
0x1800302a1  mov     dword ptr [rsp+880h+cbData], eax; cbData
0x1800302a5  lea     r14, aDomain; "Domain"
0x1800302ac  mov     [rsp+880h+phkResult], rcx; lpData
0x1800302b1  xor     r8d, r8d; Reserved
0x1800302b4  mov     rcx, [rsp+880h+var_850]; hKey
0x1800302b9  mov     rdx, r14; lpValueName
0x1800302bc  call    cs:__imp_RegSetValueExW
0x1800302c3  nop     dword ptr [rax+rax+00h]
0x1800302c8  mov     ebx, eax
0x1800302ca  test    eax, eax
0x1800302cc  jnz     short loc_180030254
0x1800302ce  cmp     [rdi+68h], r15
0x1800302d2  lea     rcx, [rsp+880h+var_848]
0x1800302d7  lea     eax, [rbx+20h]
0x1800302da  cmovnz  rcx, [rdi+68h]
0x1800302df  cmp     ax, [rcx]
0x1800302e2  jz      short loc_180030354
0x1800302e4  inc     rsi
0x1800302e7  cmp     [rcx+rsi*2], r15w
0x1800302ec  jnz     short loc_1800302E4
0x1800302ee  lea     eax, ds:2[rsi*2]
0x1800302f5  mov     r9d, 1; dwType
0x1800302fb  mov     dword ptr [rsp+880h+cbData], eax; cbData
0x1800302ff  lea     rdi, aNameserver; "NameServer"
0x180030306  mov     [rsp+880h+phkResult], rcx; lpData
0x18003030b  xor     r8d, r8d; Reserved
0x18003030e  mov     rcx, [rsp+880h+var_850]; hKey
0x180030313  mov     rdx, rdi; lpValueName
0x180030316  call    cs:__imp_RegSetValueExW
0x18003031d  nop     dword ptr [rax+rax+00h]
0x180030322  mov     ebx, eax
0x180030324  test    eax, eax
0x180030326  jz      loc_1800303D7
0x18003032c  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180030333  jz      short loc_18003034B
0x180030335  cmp     cs:qword_18004D640, r15
0x18003033c  jz      loc_1800303D7
0x180030342  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x180030349  jmp     short loc_18003038E
0x18003034b  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x180030352  jmp     short loc_1800303CC
0x180030354  mov     rcx, [rsp+880h+var_850]; hKey
0x180030359  lea     rdi, aNameserver; "NameServer"
0x180030360  mov     rdx, rdi; lpValueName
0x180030363  call    cs:__imp_RegDeleteValueW
0x18003036a  nop     dword ptr [rax+rax+00h]
0x18003036f  mov     ebx, eax
0x180030371  test    eax, eax
0x180030373  jz      short loc_1800303D7
0x180030375  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18003037c  jz      short loc_1800303C5
0x18003037e  cmp     cs:qword_18004D640, r15
0x180030385  jz      short loc_1800303D7
0x180030387  lea     rdx, aRegdeletevalue; "RegDeleteValue(%ws) failed and returned"...
0x18003038e  mov     r8, rdi
0x180030391  mov     r9d, eax
0x180030394  mov     word ptr [rsp+880h+var_830], r15w
0x18003039a  lea     rcx, [rsp+880h+var_830]
0x18003039f  call    FormatRRASErrorString
0x1800303a4  mov     rdx, cs:qword_18004D640
0x1800303ab  lea     r8, [rsp+880h+var_830]
0x1800303b0  mov     rcx, cs:gIphlpEtwContext
0x1800303b7  mov     rax, cs:gIphlpTemplateFunc
0x1800303be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303c3  jmp     short loc_1800303D7
0x1800303c5  lea     rcx, aRegdeletevalue_2; "RegDeleteValue(%ws) failed and returned"...
0x1800303cc  mov     rdx, rdi
0x1800303cf  mov     r8d, eax
0x1800303d2  call    TraceHlp
0x1800303d7  mov     rcx, [rsp+880h+var_850]; hKey
0x1800303dc  test    rcx, rcx
0x1800303df  jz      short loc_1800303ED
0x1800303e1  call    cs:__imp_RegCloseKey
0x1800303e8  nop     dword ptr [rax+rax+00h]
0x1800303ed  mov     rcx, [rsp+880h+hKey]; hKey
0x1800303f2  test    rcx, rcx
0x1800303f5  jz      short loc_180030403
0x1800303f7  call    cs:__imp_RegCloseKey
0x1800303fe  nop     dword ptr [rax+rax+00h]
0x180030403  mov     eax, ebx
0x180030405  mov     rcx, [rbp+780h+var_30]
0x18003040c  xor     rcx, rsp; StackCookie
0x18003040f  call    __security_check_cookie
0x180030414  mov     rbx, [rsp+880h+arg_10]
0x18003041c  add     rsp, 860h
0x180030423  pop     r15
0x180030425  pop     r14
0x180030427  pop     rdi
0x180030428  pop     rsi
0x180030429  pop     rbp
0x18003042a  retn
```

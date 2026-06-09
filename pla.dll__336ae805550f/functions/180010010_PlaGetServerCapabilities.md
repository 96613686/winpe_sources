# PlaGetServerCapabilities

- ea: `0x180010010`
- end: `0x1800106c2`
- name: `PlaGetServerCapabilities`
- size: `1714`
- prototype: `HRESULT __stdcall(BSTR Server, PDWORD Capabilites)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000eb70`
- `0x1800cf740`
- `0x1800f7230`
- `0x1801022e0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180010010`
- `0x1800106d0`
- `0x180012ef0`
- `0x18002b3a0`
- `0x180074cf0`
- `0x18013aee0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800101d7`
- `msvcrt!_wcsicmp` at `0x1800105b0`
- `msvcrt!_wcsicmp` at `0x1800101d7`
- `msvcrt!_wcsicmp` at `0x1800105b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010603`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010603`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010146`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010146`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800100d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010677`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010689`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800106a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800106b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800100d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010677`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010689`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800106a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800106b7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800105f9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800105f9`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180010656`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180010656`

## string_xrefs

- `0x1800100f8`: `System\CurrentControlSet\Services\SysmonLog`
- `0x18001013f`: `SOFTWARE\CLASSES\CLSID\{9a5dd473-d410-11d1-b829-00c04f94c7c3}`
- `0x1800100ab`: `System\CurrentControlSet\Services\PLA`

## pseudocode

```c
HRESULT __stdcall PlaGetServerCapabilities(BSTR Server, PDWORD Capabilites)
{
  int v2; // esi
  int v5; // r15d
  DWORD v6; // ebx
  LSTATUS v7; // eax
  bool v8; // sf
  LSTATUS v9; // eax
  bool v10; // sf
  LSTATUS v11; // eax
  bool v12; // sf
  HRESULT ServerCapsNoRegistry; // edi
  int v15; // ebx
  __int64 v16; // rax
  bool v17; // zf
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  WCHAR *v21; // rax
  WCHAR *v22; // r13
  DWORD LastError; // eax
  int v24; // eax
  BSTR i; // rdx
  LSTATUS v26; // eax
  int v27; // eax
  int phkResult; // [rsp+28h] [rbp-E0h]
  int v29; // [rsp+78h] [rbp-90h] BYREF
  int v30; // [rsp+80h] [rbp-88h] BYREF
  HKEY v31; // [rsp+88h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-78h] BYREF
  DWORD nSize[4]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 v34[64]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 v35[64]; // [rsp+128h] [rbp+20h] BYREF
  unsigned __int16 v36[64]; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int16 v37[64]; // [rsp+228h] [rbp+120h] BYREF

  v2 = 1;
  v5 = 0;
  hKey = 0;
  v31 = 0;
  nSize[0] = 16;
  if ( !Server || !*Server || !_wcsicmp(Server, L".") )
    goto LABEL_3;
  v21 = (WCHAR *)PlaiAlloc(2LL * nSize[0], 1, 0, byte_180147320, phkResult);
  v22 = v21;
  v19 = -1;
  if ( !v21 )
  {
    ServerCapsNoRegistry = -2147024882;
    v30 = -2147024882;
    v29 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v34, 0x4000000000000800uLL);
      v16 = -1;
      do
        v17 = v34[++v16] == 0;
      while ( !v17 );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v30, 4, byte_180147320, 1, &v29, 4);
    }
    goto LABEL_50;
  }
  if ( !GetComputerNameW(v21, nSize) )
  {
    LastError = GetLastError();
    v24 = PlaiHResultFromWin32(LastError);
    ServerCapsNoRegistry = v24;
    if ( v24 < 0 )
    {
      v30 = 0;
      v29 = v24;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v35, 0x4000000000000800uLL);
        v18 = -1;
        do
          v17 = v35[++v18] == 0;
        while ( !v17 );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v29, 4, byte_180147320, 1, &v30, 4);
      }
      PlaiFree(v22, 1);
LABEL_50:
      v30 = 0;
      v29 = ServerCapsNoRegistry;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v36, 0x4000000000000800uLL);
        do
          v17 = v36[++v19] == 0;
        while ( !v17 );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v29, 4, byte_180147320, 1, &v30, 4);
      }
LABEL_25:
      if ( v2 )
        goto LABEL_26;
      goto LABEL_69;
    }
  }
  for ( i = Server; *i == 92; ++i )
    ;
  v15 = _wcsicmp(v22, i);
  LOBYTE(v5) = v15 == 0;
  PlaiFree(v22, 1);
  if ( !v15 )
  {
    v2 = v5;
LABEL_3:
    v6 = 0x10000000;
    hKey = HKEY_LOCAL_MACHINE;
    goto LABEL_4;
  }
  ServerCapsNoRegistry = PlaiGetServerCapsNoRegistry(Server, Capabilites);
  if ( ServerCapsNoRegistry < 0 )
  {
    v26 = RegConnectRegistryW(Server, HKEY_LOCAL_MACHINE, &hKey);
    v27 = PlaiHResultFromWin32(v26);
    ServerCapsNoRegistry = v27;
    if ( v27 >= 0 )
    {
      v6 = 0;
      v2 = v5;
LABEL_4:
      v7 = RegOpenKeyExW(hKey, L"System\\CurrentControlSet\\Services\\PLA", 0, 0x20019u, &v31);
      v8 = v7 < 0;
      if ( !v7 )
        goto LABEL_5;
      if ( v7 > 0 )
        v8 = 1;
      if ( !v8 )
LABEL_5:
        v6 |= 0x27u;
      if ( v31 )
      {
        RegCloseKey(v31);
        v31 = 0;
      }
      v9 = RegOpenKeyExW(hKey, L"System\\CurrentControlSet\\Services\\SysmonLog", 0, 0x20019u, &v31);
      v10 = v9 < 0;
      if ( !v9 )
        goto LABEL_12;
      if ( v9 > 0 )
        v10 = 1;
      if ( !v10 )
LABEL_12:
        v6 |= 0x10u;
      if ( v31 )
      {
        RegCloseKey(v31);
        v31 = 0;
      }
      v11 = RegOpenKeyExW(hKey, L"SOFTWARE\\CLASSES\\CLSID\\{9a5dd473-d410-11d1-b829-00c04f94c7c3}", 0, 0x20019u, &v31);
      v12 = v11 < 0;
      if ( !v11 )
        goto LABEL_19;
      if ( v11 > 0 )
        v12 = 1;
      if ( !v12 )
LABEL_19:
        v6 |= 8u;
      *Capabilites = v6;
      ServerCapsNoRegistry = 0;
      if ( !v6 )
        ServerCapsNoRegistry = -2147467262;
      goto LABEL_25;
    }
    v29 = v27;
    v30 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v37, 0x4000000000000800uLL);
      v20 = -1;
      do
        v17 = v37[++v20] == 0;
      while ( !v17 );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v29, 4, byte_180147320, 1, &v30, 4);
    }
  }
LABEL_69:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
LABEL_26:
  if ( v31 )
    RegCloseKey(v31);
  return ServerCapsNoRegistry;
}

```

## disassembly

```asm
0x180010010  mov     r11, rsp
0x180010013  push    rbp
0x180010014  push    rdi
0x180010015  lea     rbp, [r11-1E8h]
0x18001001c  sub     rsp, 2D8h
0x180010023  mov     rax, cs:__security_cookie
0x18001002a  xor     rax, rsp
0x18001002d  mov     [rbp+1E0h+var_40], rax
0x180010034  mov     [r11+18h], rbx
0x180010038  mov     [r11-18h], rsi
0x18001003c  mov     esi, 1
0x180010041  mov     [r11-20h], r12
0x180010045  mov     r12, rdx
0x180010048  mov     [r11-28h], r13
0x18001004c  mov     [r11-30h], r14
0x180010050  mov     r14, rcx
0x180010053  mov     [r11-38h], r15
0x180010057  xor     r15d, r15d
0x18001005a  mov     [rbp+1E0h+hKey], r15
0x18001005e  mov     [rbp+1E0h+var_260], r15
0x180010062  mov     [rbp+1E0h+nSize], 10h
0x180010069  test    rcx, rcx
0x18001006c  jz      short loc_180010078
0x18001006e  cmp     r15w, [rcx]
0x180010072  jnz     loc_1800105A9
0x180010078  mov     ebx, 10000000h
0x18001007d  mov     [rbp+1E0h+hKey], 0FFFFFFFF80000002h
0x180010085  mov     rcx, [rbp+1E0h+var_260]; hKey
0x180010089  test    rcx, rcx
0x18001008c  jnz     loc_180010677
0x180010092  xor     r15d, r15d
0x180010095  mov     rcx, [rbp+1E0h+hKey]; hKey
0x180010099  lea     rax, [rbp+1E0h+var_260]
0x18001009d  mov     r9d, 20019h; samDesired
0x1800100a3  mov     [rsp+2E0h+phkResult], rax; phkResult
0x1800100a8  xor     r8d, r8d; ulOptions
0x1800100ab  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\PL"...
0x1800100b2  call    cs:__imp_RegOpenKeyExW
0x1800100b8  test    eax, eax
0x1800100ba  jnz     short loc_1800100C1
0x1800100bc  or      ebx, 27h
0x1800100bf  jmp     short loc_1800100CF
0x1800100c1  jle     short loc_1800100CD
0x1800100c3  movzx   eax, ax
0x1800100c6  or      eax, 80070000h
0x1800100cb  test    eax, eax
0x1800100cd  jns     short loc_1800100BC
0x1800100cf  mov     rcx, [rbp+1E0h+var_260]; hKey
0x1800100d3  test    rcx, rcx
0x1800100d6  jz      short loc_1800100E2
0x1800100d8  call    cs:__imp_RegCloseKey
0x1800100de  mov     [rbp+1E0h+var_260], r15
0x1800100e2  mov     rcx, [rbp+1E0h+hKey]; hKey
0x1800100e6  lea     rax, [rbp+1E0h+var_260]
0x1800100ea  mov     r9d, 20019h; samDesired
0x1800100f0  mov     [rsp+2E0h+phkResult], rax; phkResult
0x1800100f5  xor     r8d, r8d; ulOptions
0x1800100f8  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sy"...
0x1800100ff  call    cs:__imp_RegOpenKeyExW
0x180010105  test    eax, eax
0x180010107  jnz     short loc_18001010E
0x180010109  or      ebx, 10h
0x18001010c  jmp     short loc_18001011C
0x18001010e  jle     short loc_18001011A
0x180010110  movzx   eax, ax
0x180010113  or      eax, 80070000h
0x180010118  test    eax, eax
0x18001011a  jns     short loc_180010109
0x18001011c  mov     rcx, [rbp+1E0h+var_260]; hKey
0x180010120  test    rcx, rcx
0x180010123  jnz     loc_180010689
0x180010129  mov     rcx, [rbp+1E0h+hKey]; hKey
0x18001012d  lea     rax, [rbp+1E0h+var_260]
0x180010131  mov     r9d, 20019h; samDesired
0x180010137  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18001013c  xor     r8d, r8d; ulOptions
0x18001013f  lea     rdx, aSoftwareClasse; "SOFTWARE\\CLASSES\\CLSID\\{9a5dd473-d41"...
0x180010146  call    cs:__imp_RegOpenKeyExW
0x18001014c  test    eax, eax
0x18001014e  jnz     short loc_180010155
0x180010150  or      ebx, 8
0x180010153  jmp     short loc_180010163
0x180010155  jle     short loc_180010161
0x180010157  movzx   eax, ax
0x18001015a  or      eax, 80070000h
0x18001015f  test    eax, eax
0x180010161  jns     short loc_180010150
0x180010163  test    ebx, ebx
0x180010165  mov     [r12], ebx
0x180010169  mov     edi, r15d
0x18001016c  mov     eax, 80004002h
0x180010171  cmovz   edi, eax
0x180010174  test    esi, esi
0x180010176  jz      loc_18001069B
0x18001017c  mov     rcx, [rbp+1E0h+var_260]; hKey
0x180010180  mov     r15, [rsp+2E0h+var_30]
0x180010188  mov     r14, [rsp+2E0h+var_28]
0x180010190  mov     r13, [rsp+2E0h+var_20]
0x180010198  mov     r12, [rsp+2E0h+var_18]
0x1800101a0  mov     rsi, [rsp+2E0h+var_10]
0x1800101a8  mov     rbx, [rsp+2E0h+arg_10]
0x1800101b0  test    rcx, rcx
0x1800101b3  jnz     loc_1800106B7
0x1800101b9  mov     eax, edi
0x1800101bb  mov     rcx, [rbp+1E0h+var_40]
0x1800101c2  xor     rcx, rsp; StackCookie
0x1800101c5  call    __security_check_cookie
0x1800101ca  add     rsp, 2D8h
0x1800101d1  pop     rdi
0x1800101d2  pop     rbp
0x1800101d3  retn
0x1800101d4  mov     rcx, r13; String1
0x1800101d7  call    cs:__imp__wcsicmp
0x1800101dd  mov     ebx, eax
0x1800101df  test    eax, eax
0x1800101e1  mov     edx, esi; int
0x1800101e3  mov     rcx, r13; lpMem
0x1800101e6  setz    r15b
0x1800101ea  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x1800101ef  test    ebx, ebx
0x1800101f1  jnz     loc_180010637
0x1800101f7  mov     esi, r15d
0x1800101fa  jmp     loc_180010078
0x1800101ff  mov     rax, cs:qword_180169748
0x180010206  and     rax, rdx
0x180010209  cmp     cs:qword_180169748, rax
0x180010210  jnz     loc_180010510
0x180010216  lea     rcx, [rbp+1E0h+var_240]; unsigned __int16 *
0x18001021a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001021f  lea     rcx, [rbp+1E0h+var_240]
0x180010223  mov     rax, rbx
0x180010226  nop     word ptr [rax+rax+00000000h]
0x180010230  cmp     [rcx+rax*2+2], r15w
0x180010236  lea     rax, [rax+1]
0x18001023a  jnz     short loc_180010230
0x18001023c  lea     ecx, [rax+rax]
0x18001023f  mov     r8d, 5
0x180010245  add     rcx, 2
0x180010249  lea     rax, [rbp+1E0h+var_240]
0x18001024d  mov     [rsp+2E0h+var_280], rcx
0x180010252  lea     r14, byte_180147320
0x180010259  mov     [rsp+2E0h+var_288], rax
0x18001025e  lea     r9, [rsp+2E0h+var_268]
0x180010263  mov     [rsp+2E0h+var_290], 12h
0x18001026c  lea     rax, aPlaiislocalser; "PlaiIsLocalServer"
0x180010273  mov     [rsp+2E0h+var_298], rax
0x180010278  lea     rdx, PLA_EVENT_ERROR
0x18001027f  mov     [rsp+2E0h+var_2A0], 4
0x180010288  lea     rax, [rsp+2E0h+var_270]
0x18001028d  mov     [rsp+2E0h+var_2A8], rax
0x180010292  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180010299  mov     [rsp+2E0h+var_2B0], rsi
0x18001029e  mov     [rsp+2E0h+var_2B8], r14
0x1800102a3  mov     [rsp+2E0h+phkResult], 4
0x1800102ac  call    EventingWriteEvent
0x1800102b1  mov     rdx, 4000000000000800h
0x1800102bb  jmp     loc_180010517
0x1800102c0  mov     rax, cs:qword_180169748
0x1800102c7  and     rax, rdx
0x1800102ca  cmp     cs:qword_180169748, rax
0x1800102d1  jnz     loc_180010568
0x1800102d7  lea     rcx, [rbp+1E0h+var_1C0]; unsigned __int16 *
0x1800102db  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800102e0  lea     rcx, [rbp+1E0h+var_1C0]
0x1800102e4  mov     rax, rbx
0x1800102e7  nop     word ptr [rax+rax+00000000h]
0x1800102f0  cmp     [rcx+rax*2+2], r15w
0x1800102f6  lea     rax, [rax+1]
0x1800102fa  jnz     short loc_1800102F0
0x1800102fc  lea     ecx, [rax+rax]
0x1800102ff  mov     r8d, 5
0x180010305  add     rcx, 2
0x180010309  lea     rax, [rbp+1E0h+var_1C0]
0x18001030d  mov     [rsp+2E0h+var_280], rcx
0x180010312  lea     r14, byte_180147320
0x180010319  mov     [rsp+2E0h+var_288], rax
0x18001031e  lea     r9, [rsp+2E0h+var_270]
0x180010323  mov     [rsp+2E0h+var_290], 12h
0x18001032c  lea     rax, aPlaiislocalser; "PlaiIsLocalServer"
0x180010333  mov     [rsp+2E0h+var_298], rax
0x180010338  lea     rdx, PLA_EVENT_ERROR
0x18001033f  mov     [rsp+2E0h+var_2A0], 4
0x180010348  lea     rax, [rsp+2E0h+var_268]
0x18001034d  mov     [rsp+2E0h+var_2A8], rax
0x180010352  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180010359  mov     [rsp+2E0h+var_2B0], rsi
0x18001035e  mov     [rsp+2E0h+var_2B8], r14
0x180010363  mov     [rsp+2E0h+phkResult], 4
0x18001036c  call    EventingWriteEvent
0x180010371  mov     edx, esi; int
0x180010373  mov     rcx, r13; lpMem
0x180010376  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18001037b  jmp     loc_1800102B1
0x180010380  mov     rax, cs:qword_180169748
0x180010387  and     rax, rdx
0x18001038a  cmp     cs:qword_180169748, rax
0x180010391  jnz     loc_180010174
0x180010397  lea     rcx, [rbp+1E0h+var_140]; unsigned __int16 *
0x18001039e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800103a3  lea     rax, [rbp+1E0h+var_140]
0x1800103aa  nop     word ptr [rax+rax+00h]
0x1800103b0  cmp     [rax+rbx*2+2], r15w
0x1800103b6  lea     rbx, [rbx+1]
0x1800103ba  jnz     short loc_1800103B0
0x1800103bc  lea     rax, [rbp+1E0h+var_140]
0x1800103c3  mov     r8d, 5
0x1800103c9  lea     ecx, [rbx+rbx]
0x1800103cc  add     rcx, 2
0x1800103d0  lea     r9, [rsp+2E0h+var_270]
0x1800103d5  mov     [rsp+2E0h+var_280], rcx
0x1800103da  lea     rdx, PLA_EVENT_ERROR
0x1800103e1  mov     [rsp+2E0h+var_288], rax
0x1800103e6  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800103ed  mov     [rsp+2E0h+var_290], 19h
0x1800103f6  lea     rax, aPlagetserverca_0; "PlaGetServerCapabilities"
0x1800103fd  mov     [rsp+2E0h+var_298], rax
0x180010402  lea     rax, [rsp+2E0h+var_268]
0x180010407  mov     [rsp+2E0h+var_2A0], 4
0x180010410  mov     [rsp+2E0h+var_2A8], rax
0x180010415  mov     [rsp+2E0h+var_2B0], rsi
0x18001041a  mov     [rsp+2E0h+var_2B8], r14
0x18001041f  mov     [rsp+2E0h+phkResult], 4
0x180010428  call    EventingWriteEvent
0x18001042d  jmp     loc_180010174
0x180010432  mov     rax, cs:qword_180169748
0x180010439  and     rax, rdx
0x18001043c  cmp     cs:qword_180169748, rax
0x180010443  jnz     loc_18001069B
0x180010449  lea     rcx, [rbp+1E0h+var_C0]; unsigned __int16 *
0x180010450  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180010455  lea     rcx, [rbp+1E0h+var_C0]
0x18001045c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180010463  cmp     [rcx+rax*2+2], r15w
0x180010469  lea     rax, [rax+1]
0x18001046d  jnz     short loc_180010463
0x18001046f  lea     ecx, [rax+rax]
0x180010472  mov     r8d, 5
0x180010478  add     rcx, 2
0x18001047c  lea     rax, [rbp+1E0h+var_C0]
0x180010483  mov     [rsp+2E0h+var_280], rcx
0x180010488  lea     r9, [rsp+2E0h+var_270]
0x18001048d  mov     [rsp+2E0h+var_288], rax
0x180010492  lea     rdx, PLA_EVENT_ERROR
0x180010499  mov     [rsp+2E0h+var_290], 19h
0x1800104a2  lea     rax, aPlagetserverca_0; "PlaGetServerCapabilities"
0x1800104a9  mov     [rsp+2E0h+var_298], rax
0x1800104ae  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800104b5  mov     [rsp+2E0h+var_2A0], 4
0x1800104be  lea     rax, [rsp+2E0h+var_268]
0x1800104c3  mov     [rsp+2E0h+var_2A8], rax
0x1800104c8  lea     rax, byte_180147320
0x1800104cf  mov     [rsp+2E0h+var_2B0], rsi
0x1800104d4  mov     [rsp+2E0h+var_2B8], rax
0x1800104d9  mov     [rsp+2E0h+phkResult], 4
0x1800104e2  call    EventingWriteEvent
0x1800104e7  jmp     loc_18001069B
0x1800104ec  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800104f3  mov     edi, 8007000Eh
0x1800104f8  mov     [rsp+2E0h+var_268], edi
0x1800104fc  mov     [rsp+2E0h+var_270], r15d
0x180010501  jz      short loc_180010510
0x180010503  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001050a  jnz     loc_1800101FF
0x180010510  lea     r14, byte_180147320
0x180010517  cmp     dword ptr cs:xmmword_180169738, r15d
0x18001051e  mov     [rsp+2E0h+var_268], r15d
0x180010523  mov     [rsp+2E0h+var_270], edi
0x180010527  jz      loc_180010174
0x18001052d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180010534  jz      loc_180010174
0x18001053a  jmp     loc_180010380
0x18001053f  cmp     dword ptr cs:xmmword_180169738, r15d
0x180010546  mov     [rsp+2E0h+var_268], r15d
0x18001054b  mov     [rsp+2E0h+var_270], eax
0x18001054f  jz      short loc_180010568
0x180010551  mov     rdx, 4000000000000800h; unsigned __int64
0x18001055b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180010562  jnz     loc_1800102C0
0x180010568  lea     r14, byte_180147320
0x18001056f  jmp     loc_180010371
0x180010574  xor     r15d, r15d
0x180010577  mov     [rsp+2E0h+var_270], eax
0x18001057b  cmp     dword ptr cs:xmmword_180169738, r15d
0x180010582  mov     [rsp+2E0h+var_268], r15d
0x180010587  jz      loc_18001069B
0x18001058d  mov     rdx, 4000000000000800h; unsigned __int64
0x180010597  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001059e  jz      loc_18001069B
0x1800105a4  jmp     loc_180010432
0x1800105a9  lea     rdx, String2; "."
0x1800105b0  call    cs:__imp__wcsicmp
0x1800105b6  test    eax, eax
0x1800105b8  jz      loc_180010078
0x1800105be  mov     ecx, [rbp+1E0h+nSize]
0x1800105c1  lea     r9, byte_180147320; char *
0x1800105c8  add     rcx, rcx; dwBytes
0x1800105cb  xor     r8d, r8d; int
0x1800105ce  mov     edx, esi; int
0x1800105d0  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800105d5  mov     r13, rax
  ... truncated ...
```

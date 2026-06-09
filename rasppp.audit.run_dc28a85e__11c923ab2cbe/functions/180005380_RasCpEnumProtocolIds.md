# RasCpEnumProtocolIds

- ea: `0x180005380`
- end: `0x1800055a5`
- name: `RasCpEnumProtocolIds`
- size: `549`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180005380`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000548f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000548f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180005435`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180005435`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005504`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005504`

## string_xrefs

- `0x1800053f4`: `RasCpEnumProtocolIds`
- `0x180005427`: `SYSTEM\CurrentControlSet\Services\RasMan\ppp\ControlProtocols\BuiltIn`
- `0x18000553d`: `Protocol %x`

## pseudocode

```c
__int64 __fastcall RasCpEnumProtocolIds(__int64 a1, _DWORD *a2)
{
  unsigned int i; // ebx
  __int64 v5; // rsi
  bool v6; // zf
  __int64 v7; // r8
  unsigned int j; // ebx
  __int64 v9; // r8
  __int64 v10; // r8
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[2044]; // [rsp+54h] [rbp-ACh] BYREF

  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  v16 = 0;
  cbData = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( (byte_18004DF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, L"RasCpEnumProtocolIds");
  *a2 = 0;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "SYSTEM\\CurrentControlSet\\Services\\RasMan\\ppp\\ControlProtocols\\BuiltIn",
          0,
          0x20019u,
          &hKey) )
  {
    for ( i = 0; i < 6; ++i )
    {
      v5 = 4LL * i;
      cbData = 4;
      if ( !RegQueryValueExA(hKey, (LPCSTR)BuiltInCps[v5 + 2], 0, &Type, Data, &cbData)
        && Type == 4
        && cbData == 4
        && !*(_DWORD *)Data )
      {
        v6 = (byte_18004DF34 & 1) == 0;
        LODWORD(BuiltInCps[v5 + 3]) = 0;
        if ( !v6 )
        {
          v7 = BuiltInCps[v5 + 2];
          LOWORD(v16) = 0;
          FormatRRASErrorString(&v16, L"%hs is FALSE", v7);
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v16);
        }
      }
    }
    RegCloseKey(hKey);
  }
  for ( j = 0; j < 6; ++j )
  {
    v9 = 4LL * j;
    if ( LODWORD(BuiltInCps[v9 + 3]) )
    {
      *(_DWORD *)(a1 + 4LL * (unsigned int)*a2) = BuiltInCps[v9];
      if ( (byte_18004DF34 & 1) != 0 )
      {
        v10 = LODWORD(BuiltInCps[v9]);
        LOWORD(v16) = 0;
        FormatRRASErrorString(&v16, L"Protocol %x", v10);
        if ( (byte_18004DF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v16);
      }
      ++*a2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005380  mov     [rsp-8+arg_10], rbx
0x180005385  push    rbp
0x180005386  push    rsi
0x180005387  push    rdi
0x180005388  push    r13
0x18000538a  push    r14
0x18000538c  lea     rbp, [rsp-760h]
0x180005394  sub     rsp, 860h
0x18000539b  mov     rax, cs:__security_cookie
0x1800053a2  xor     rax, rsp
0x1800053a5  mov     [rbp+780h+var_30], rax
0x1800053ac  mov     rdi, rdx
0x1800053af  mov     [rsp+880h+hKey], 0
0x1800053b8  mov     r14, rcx
0x1800053bb  mov     [rsp+880h+Type], 0
0x1800053c3  xor     eax, eax
0x1800053c5  mov     dword ptr [rsp+880h+Data], 0
0x1800053cd  xor     edx, edx; Val
0x1800053cf  mov     [rsp+880h+var_830], eax
0x1800053d3  lea     rcx, [rsp+880h+var_82C]; void *
0x1800053d8  mov     [rsp+880h+cbData], 0
0x1800053e0  mov     r8d, 7FCh; Size
0x1800053e6  call    memset_0
0x1800053eb  test    cs:byte_18004DF34, 1
0x1800053f2  jz      short loc_18000540E
0x1800053f4  lea     r8, aRascpenumproto_1; "RasCpEnumProtocolIds"
0x1800053fb  lea     rdx, RasPppTraceInfo
0x180005402  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005409  call    McTemplateU0z_EventWriteTransfer
0x18000540e  lea     rax, [rsp+880h+hKey]
0x180005413  mov     dword ptr [rdi], 0
0x180005419  mov     r9d, 20019h; samDesired
0x18000541f  mov     [rsp+880h+phkResult], rax; phkResult
0x180005424  xor     r8d, r8d; ulOptions
0x180005427  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18000542e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005435  call    cs:__imp_RegOpenKeyExA
0x18000543c  nop     dword ptr [rax+rax+00h]
0x180005441  lea     r13, BuiltInCps
0x180005448  test    eax, eax
0x18000544a  jnz     loc_180005510
0x180005450  xor     ebx, ebx
0x180005452  mov     rcx, [rsp+880h+hKey]; hKey
0x180005457  cmp     ebx, 6
0x18000545a  jnb     loc_180005504
0x180005460  lea     rax, [rsp+880h+cbData]
0x180005465  mov     esi, ebx
0x180005467  mov     [rsp+880h+lpcbData], rax; lpcbData
0x18000546c  lea     r9, [rsp+880h+Type]; lpType
0x180005471  lea     rax, [rsp+880h+Data]
0x180005476  shl     rsi, 5
0x18000547a  xor     r8d, r8d; lpReserved
0x18000547d  mov     [rsp+880h+cbData], 4
0x180005485  mov     [rsp+880h+phkResult], rax; lpData
0x18000548a  mov     rdx, [rsi+r13+10h]; lpValueName
0x18000548f  call    cs:__imp_RegQueryValueExA
0x180005496  nop     dword ptr [rax+rax+00h]
0x18000549b  test    eax, eax
0x18000549d  jnz     short loc_1800054FD
0x18000549f  cmp     [rsp+880h+Type], 4
0x1800054a4  jnz     short loc_1800054FD
0x1800054a6  cmp     [rsp+880h+cbData], 4
0x1800054ab  jnz     short loc_1800054FD
0x1800054ad  cmp     dword ptr [rsp+880h+Data], eax
0x1800054b1  jnz     short loc_1800054FD
0x1800054b3  test    cs:byte_18004DF34, 1
0x1800054ba  mov     [rsi+r13+18h], eax
0x1800054bf  jz      short loc_1800054FD
0x1800054c1  mov     r8, [rsi+r13+10h]
0x1800054c6  lea     rdx, aHsIsFalse; "%hs is FALSE"
0x1800054cd  lea     rcx, [rsp+880h+var_830]
0x1800054d2  mov     word ptr [rsp+880h+var_830], ax
0x1800054d7  call    FormatRRASErrorString
0x1800054dc  test    cs:byte_18004DF34, 1
0x1800054e3  jz      short loc_1800054FD
0x1800054e5  lea     r8, [rsp+880h+var_830]
0x1800054ea  lea     rdx, RasPppTraceInfo
0x1800054f1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800054f8  call    McTemplateU0z_EventWriteTransfer
0x1800054fd  inc     ebx
0x1800054ff  jmp     loc_180005452
0x180005504  call    cs:__imp_RegCloseKey
0x18000550b  nop     dword ptr [rax+rax+00h]
0x180005510  xor     ebx, ebx
0x180005512  cmp     ebx, 6
0x180005515  jnb     short loc_18000557C
0x180005517  mov     r8d, ebx
0x18000551a  shl     r8, 5
0x18000551e  cmp     dword ptr [r8+r13+18h], 0
0x180005524  jz      short loc_180005578
0x180005526  mov     ecx, [rdi]
0x180005528  mov     eax, [r8+r13]
0x18000552c  mov     [r14+rcx*4], eax
0x180005530  test    cs:byte_18004DF34, 1
0x180005537  jz      short loc_180005576
0x180005539  mov     r8d, [r8+r13]
0x18000553d  lea     rdx, aProtocolX; "Protocol %x"
0x180005544  xor     eax, eax
0x180005546  lea     rcx, [rsp+880h+var_830]
0x18000554b  mov     word ptr [rsp+880h+var_830], ax
0x180005550  call    FormatRRASErrorString
0x180005555  test    cs:byte_18004DF34, 1
0x18000555c  jz      short loc_180005576
0x18000555e  lea     r8, [rsp+880h+var_830]
0x180005563  lea     rdx, RasPppTraceInfo
0x18000556a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005571  call    McTemplateU0z_EventWriteTransfer
0x180005576  inc     dword ptr [rdi]
0x180005578  inc     ebx
0x18000557a  jmp     short loc_180005512
0x18000557c  xor     eax, eax
0x18000557e  mov     rcx, [rbp+780h+var_30]
0x180005585  xor     rcx, rsp; StackCookie
0x180005588  call    __security_check_cookie
0x18000558d  mov     rbx, [rsp+880h+arg_10]
0x180005595  add     rsp, 860h
0x18000559c  pop     r14
0x18000559e  pop     r13
0x1800055a0  pop     rdi
0x1800055a1  pop     rsi
0x1800055a2  pop     rbp
0x1800055a3  retn
```

# RasCpEnumProtocolIds

- ea: `0x1800051a0`
- end: `0x1800053b2`
- name: `RasCpEnumProtocolIds`
- size: `530`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800051a0`
- `0x18002a138`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800052a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800052a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180005255`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180005255`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005318`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005318`

## string_xrefs

- `0x180005214`: `RasCpEnumProtocolIds`
- `0x180005247`: `SYSTEM\CurrentControlSet\Services\RasMan\ppp\ControlProtocols\BuiltIn`
- `0x18000534b`: `Protocol %x`

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
  if ( (byte_18004CF34 & 1) != 0 )
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
        v6 = (byte_18004CF34 & 1) == 0;
        LODWORD(BuiltInCps[v5 + 3]) = 0;
        if ( !v6 )
        {
          v7 = BuiltInCps[v5 + 2];
          LOWORD(v16) = 0;
          FormatRRASErrorString(&v16, L"%hs is FALSE", v7);
          if ( (byte_18004CF34 & 1) != 0 )
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
      if ( (byte_18004CF34 & 1) != 0 )
      {
        v10 = LODWORD(BuiltInCps[v9]);
        LOWORD(v16) = 0;
        FormatRRASErrorString(&v16, L"Protocol %x", v10);
        if ( (byte_18004CF34 & 1) != 0 )
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
0x1800051a0  mov     [rsp-8+arg_10], rbx
0x1800051a5  push    rbp
0x1800051a6  push    rsi
0x1800051a7  push    rdi
0x1800051a8  push    r13
0x1800051aa  push    r14
0x1800051ac  lea     rbp, [rsp-760h]
0x1800051b4  sub     rsp, 860h
0x1800051bb  mov     rax, cs:__security_cookie
0x1800051c2  xor     rax, rsp
0x1800051c5  mov     [rbp+780h+var_30], rax
0x1800051cc  mov     rdi, rdx
0x1800051cf  mov     [rsp+880h+hKey], 0
0x1800051d8  mov     r14, rcx
0x1800051db  mov     [rsp+880h+Type], 0
0x1800051e3  xor     eax, eax
0x1800051e5  mov     dword ptr [rsp+880h+Data], 0
0x1800051ed  xor     edx, edx; Val
0x1800051ef  mov     [rsp+880h+var_830], eax
0x1800051f3  lea     rcx, [rsp+880h+var_82C]; void *
0x1800051f8  mov     [rsp+880h+cbData], 0
0x180005200  mov     r8d, 7FCh; Size
0x180005206  call    memset_0
0x18000520b  test    cs:byte_18004CF34, 1
0x180005212  jz      short loc_18000522E
0x180005214  lea     r8, aRascpenumproto_1; "RasCpEnumProtocolIds"
0x18000521b  lea     rdx, RasPppTraceInfo
0x180005222  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005229  call    McTemplateU0z_EventWriteTransfer
0x18000522e  lea     rax, [rsp+880h+hKey]
0x180005233  mov     dword ptr [rdi], 0
0x180005239  mov     r9d, 20019h; samDesired
0x18000523f  mov     [rsp+880h+phkResult], rax; phkResult
0x180005244  xor     r8d, r8d; ulOptions
0x180005247  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18000524e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005255  call    cs:__imp_RegOpenKeyExA
0x18000525b  lea     r13, BuiltInCps
0x180005262  test    eax, eax
0x180005264  jnz     loc_18000531E
0x18000526a  xor     ebx, ebx
0x18000526c  mov     rcx, [rsp+880h+hKey]; hKey
0x180005271  cmp     ebx, 6
0x180005274  jnb     loc_180005318
0x18000527a  lea     rax, [rsp+880h+cbData]
0x18000527f  mov     esi, ebx
0x180005281  mov     [rsp+880h+lpcbData], rax; lpcbData
0x180005286  lea     r9, [rsp+880h+Type]; lpType
0x18000528b  lea     rax, [rsp+880h+Data]
0x180005290  shl     rsi, 5
0x180005294  xor     r8d, r8d; lpReserved
0x180005297  mov     [rsp+880h+cbData], 4
0x18000529f  mov     [rsp+880h+phkResult], rax; lpData
0x1800052a4  mov     rdx, [rsi+r13+10h]; lpValueName
0x1800052a9  call    cs:__imp_RegQueryValueExA
0x1800052af  test    eax, eax
0x1800052b1  jnz     short loc_180005311
0x1800052b3  cmp     [rsp+880h+Type], 4
0x1800052b8  jnz     short loc_180005311
0x1800052ba  cmp     [rsp+880h+cbData], 4
0x1800052bf  jnz     short loc_180005311
0x1800052c1  cmp     dword ptr [rsp+880h+Data], eax
0x1800052c5  jnz     short loc_180005311
0x1800052c7  test    cs:byte_18004CF34, 1
0x1800052ce  mov     [rsi+r13+18h], eax
0x1800052d3  jz      short loc_180005311
0x1800052d5  mov     r8, [rsi+r13+10h]
0x1800052da  lea     rdx, aHsIsFalse; "%hs is FALSE"
0x1800052e1  lea     rcx, [rsp+880h+var_830]
0x1800052e6  mov     word ptr [rsp+880h+var_830], ax
0x1800052eb  call    FormatRRASErrorString
0x1800052f0  test    cs:byte_18004CF34, 1
0x1800052f7  jz      short loc_180005311
0x1800052f9  lea     r8, [rsp+880h+var_830]
0x1800052fe  lea     rdx, RasPppTraceInfo
0x180005305  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000530c  call    McTemplateU0z_EventWriteTransfer
0x180005311  inc     ebx
0x180005313  jmp     loc_18000526C
0x180005318  call    cs:__imp_RegCloseKey
0x18000531e  xor     ebx, ebx
0x180005320  cmp     ebx, 6
0x180005323  jnb     short loc_18000538A
0x180005325  mov     r8d, ebx
0x180005328  shl     r8, 5
0x18000532c  cmp     dword ptr [r8+r13+18h], 0
0x180005332  jz      short loc_180005386
0x180005334  mov     ecx, [rdi]
0x180005336  mov     eax, [r8+r13]
0x18000533a  mov     [r14+rcx*4], eax
0x18000533e  test    cs:byte_18004CF34, 1
0x180005345  jz      short loc_180005384
0x180005347  mov     r8d, [r8+r13]
0x18000534b  lea     rdx, aProtocolX; "Protocol %x"
0x180005352  xor     eax, eax
0x180005354  lea     rcx, [rsp+880h+var_830]
0x180005359  mov     word ptr [rsp+880h+var_830], ax
0x18000535e  call    FormatRRASErrorString
0x180005363  test    cs:byte_18004CF34, 1
0x18000536a  jz      short loc_180005384
0x18000536c  lea     r8, [rsp+880h+var_830]
0x180005371  lea     rdx, RasPppTraceInfo
0x180005378  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000537f  call    McTemplateU0z_EventWriteTransfer
0x180005384  inc     dword ptr [rdi]
0x180005386  inc     ebx
0x180005388  jmp     short loc_180005320
0x18000538a  xor     eax, eax
0x18000538c  mov     rcx, [rbp+780h+var_30]
0x180005393  xor     rcx, rsp; StackCookie
0x180005396  call    __security_check_cookie
0x18000539b  mov     rbx, [rsp+880h+arg_10]
0x1800053a3  add     rsp, 860h
0x1800053aa  pop     r14
0x1800053ac  pop     r13
0x1800053ae  pop     rdi
0x1800053af  pop     rsi
0x1800053b0  pop     rbp
0x1800053b1  retn
```

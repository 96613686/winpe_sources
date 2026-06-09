# LoadTcpipParam

- ea: `0x18002ef0c`
- end: `0x18002f225`
- name: `LoadTcpipParam`
- size: `793`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002ebd0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x18002ef0c`
- `0x18002fab4`
- `0x18003230c`
- `0x180034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18002efbb`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18002efbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f1cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f1e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f1cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f1e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002efea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f085`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002efea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f085`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f0fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f141`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f0fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f141`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f1a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f1bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f1a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f1bb`

## string_xrefs

- `0x18002f020`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002f05b`: `RegOpenKeyEx(%ws) failed and returned %d`

## pseudocode

```c
__int64 __fastcall LoadTcpipParam(HKEY hKey, __int64 a2)
{
  __int16 v4; // r8
  int v5; // r9d
  char v6; // dl
  unsigned int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  const WCHAR *v10; // r8
  _WORD *v11; // rsi
  void *v12; // rcx
  wchar_t phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY v18; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[2044]; // [rsp+54h] [rbp-ACh] BYREF

  hKeya = 0;
  v18 = 0;
  Type = 0;
  v20 = 0;
  cbData = 0;
  memset_0(v21, 0, sizeof(v21));
  if ( gIsIphlpEtwTracingAvailable )
  {
    v6 = xmmword_18004D648;
    if ( (_QWORD)xmmword_18004D648 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        xmmword_18004D648,
        L"LoadTcpipParam");
  }
  else
  {
    TraceHlp("LoadTcpipParam");
  }
  o(*(_QWORD *)(a2 + 8), v6, v4, v5, phkResult, *(long double *)&lpcbData);
  v7 = RegOpenKeyExW(hKey, L"Interfaces", 0, 0x20019u, &hKeya);
  v8 = v7;
  if ( v7 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004D640 )
        goto LABEL_23;
      v9 = v7;
      LOWORD(v20) = 0;
      v10 = L"Interfaces";
      goto LABEL_9;
    }
    goto LABEL_10;
  }
  v8 = RegOpenKeyExW(hKeya, *(LPCWSTR *)(a2 + 8), 0, 0x20019u, &v18);
  if ( v8 )
  {
    if ( !gIsIphlpEtwTracingAvailable )
    {
LABEL_10:
      TraceHlp("RegOpenKeyEx(%ws) failed and returned %d");
      goto LABEL_23;
    }
    if ( qword_18004D640 )
    {
      v10 = *(const WCHAR **)(a2 + 8);
      LOWORD(v20) = 0;
      v9 = v8;
LABEL_9:
      FormatRRASErrorString((wchar_t *)&v20, L"RegOpenKeyEx(%ws) failed and returned %d", v10, v9);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D640, &v20);
    }
  }
  else
  {
    v11 = (_WORD *)(a2 + 16);
    cbData = 42;
    if ( RegQueryValueExW(v18, L"DhcpIPAddress", 0, &Type, (LPBYTE)(a2 + 16), &cbData) || Type != 1 )
      *v11 = 0;
    cbData = 42;
    v8 = RegQueryValueExW(v18, L"DhcpSubnetMask", 0, &Type, (LPBYTE)(a2 + 58), &cbData);
    if ( v8 || Type != 1 )
    {
      v8 = 0;
      *(_WORD *)(a2 + 58) = 0;
      *v11 = 0;
    }
    RegQueryValueWithAllocW(v18, L"Domain", 1u, (HLOCAL *)(a2 + 120));
    RegQueryValueWithAllocW(v18, L"NameServer", 1u, (HLOCAL *)(a2 + 104));
  }
LABEL_23:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v18 )
    RegCloseKey(v18);
  if ( v8 )
  {
    LocalFree(*(HLOCAL *)(a2 + 120));
    v12 = *(void **)(a2 + 104);
    *(_QWORD *)(a2 + 120) = 0;
    LocalFree(v12);
    *(_QWORD *)(a2 + 104) = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18002ef0c  mov     [rsp-8+arg_10], rbx
0x18002ef11  mov     [rsp-8+arg_18], rsi
0x18002ef16  push    rbp
0x18002ef17  push    rdi
0x18002ef18  push    r14
0x18002ef1a  lea     rbp, [rsp-760h]
0x18002ef22  sub     rsp, 860h
0x18002ef29  mov     rax, cs:__security_cookie
0x18002ef30  xor     rax, rsp
0x18002ef33  mov     [rbp+770h+var_20], rax
0x18002ef3a  mov     rdi, rdx
0x18002ef3d  mov     [rsp+870h+hKey], 0
0x18002ef46  mov     rbx, rcx
0x18002ef49  mov     [rsp+870h+var_838], 0
0x18002ef52  xor     eax, eax
0x18002ef54  mov     [rsp+870h+Type], 0
0x18002ef5c  xor     edx, edx; Val
0x18002ef5e  mov     [rsp+870h+var_820], eax
0x18002ef62  lea     rcx, [rsp+870h+var_81C]; void *
0x18002ef67  mov     [rsp+870h+cbData], 0
0x18002ef6f  mov     r8d, 7FCh; Size
0x18002ef75  call    memset_0
0x18002ef7a  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002ef81  jz      short loc_18002EFAB
0x18002ef83  mov     rdx, qword ptr cs:xmmword_18004D648
0x18002ef8a  test    rdx, rdx
0x18002ef8d  jz      short loc_18002EFB7
0x18002ef8f  mov     rcx, cs:gIphlpEtwContext
0x18002ef96  lea     r8, aLoadtcpipparam; "LoadTcpipParam"
0x18002ef9d  mov     rax, cs:gIphlpTemplateFunc
0x18002efa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efa9  jmp     short loc_18002EFB7
0x18002efab  lea     rcx, aLoadtcpipparam_0; "LoadTcpipParam"
0x18002efb2  call    TraceHlp
0x18002efb7  mov     rcx, [rdi+8]
0x18002efbb  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18002efc2  nop     dword ptr [rax+rax+00h]
0x18002efc7  lea     rax, [rsp+870h+hKey]
0x18002efcc  mov     r14d, 20019h
0x18002efd2  lea     rsi, aInterfaces; "Interfaces"
0x18002efd9  mov     [rsp+870h+phkResult], rax; phkResult
0x18002efde  mov     r9d, r14d; samDesired
0x18002efe1  mov     rdx, rsi; lpSubKey
0x18002efe4  xor     r8d, r8d; ulOptions
0x18002efe7  mov     rcx, rbx; hKey
0x18002efea  call    cs:__imp_RegOpenKeyExW
0x18002eff1  nop     dword ptr [rax+rax+00h]
0x18002eff6  mov     ebx, eax
0x18002eff8  test    eax, eax
0x18002effa  jz      short loc_18002F06C
0x18002effc  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002f003  jz      short loc_18002F055
0x18002f005  cmp     cs:qword_18004D640, 0
0x18002f00d  jz      loc_18002F19B
0x18002f013  xor     ecx, ecx
0x18002f015  mov     r9d, eax
0x18002f018  mov     word ptr [rsp+870h+var_820], cx
0x18002f01d  mov     r8, rsi
0x18002f020  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002f027  lea     rcx, [rsp+870h+var_820]
0x18002f02c  call    FormatRRASErrorString
0x18002f031  mov     rdx, cs:qword_18004D640
0x18002f038  lea     r8, [rsp+870h+var_820]
0x18002f03d  mov     rcx, cs:gIphlpEtwContext
0x18002f044  mov     rax, cs:gIphlpTemplateFunc
0x18002f04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f050  jmp     loc_18002F19B
0x18002f055  mov     r8d, eax
0x18002f058  mov     rdx, rsi
0x18002f05b  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002f062  call    TraceHlp
0x18002f067  jmp     loc_18002F19B
0x18002f06c  mov     rdx, [rdi+8]; lpSubKey
0x18002f070  lea     rax, [rsp+870h+var_838]
0x18002f075  mov     rcx, [rsp+870h+hKey]; hKey
0x18002f07a  mov     r9d, r14d; samDesired
0x18002f07d  xor     r8d, r8d; ulOptions
0x18002f080  mov     [rsp+870h+phkResult], rax; phkResult
0x18002f085  call    cs:__imp_RegOpenKeyExW
0x18002f08c  nop     dword ptr [rax+rax+00h]
0x18002f091  mov     ebx, eax
0x18002f093  test    eax, eax
0x18002f095  jz      short loc_18002F0CA
0x18002f097  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002f09e  jz      short loc_18002F0C1
0x18002f0a0  cmp     cs:qword_18004D640, 0
0x18002f0a8  jz      loc_18002F19B
0x18002f0ae  mov     r8, [rdi+8]
0x18002f0b2  xor     eax, eax
0x18002f0b4  mov     word ptr [rsp+870h+var_820], ax
0x18002f0b9  mov     r9d, ebx
0x18002f0bc  jmp     loc_18002F020
0x18002f0c1  mov     rdx, [rdi+8]
0x18002f0c5  mov     r8d, ebx
0x18002f0c8  jmp     short loc_18002F05B
0x18002f0ca  mov     rcx, [rsp+870h+var_838]; hKey
0x18002f0cf  lea     rax, [rsp+870h+cbData]
0x18002f0d4  mov     [rsp+870h+lpcbData], rax; lpcbData
0x18002f0d9  lea     rsi, [rdi+10h]
0x18002f0dd  mov     ebx, 2Ah ; '*'
0x18002f0e2  mov     [rsp+870h+phkResult], rsi; lpData
0x18002f0e7  lea     r9, [rsp+870h+Type]; lpType
0x18002f0ec  mov     [rsp+870h+cbData], ebx
0x18002f0f0  xor     r8d, r8d; lpReserved
0x18002f0f3  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x18002f0fa  call    cs:__imp_RegQueryValueExW
0x18002f101  nop     dword ptr [rax+rax+00h]
0x18002f106  test    eax, eax
0x18002f108  jnz     short loc_18002F111
0x18002f10a  cmp     [rsp+870h+Type], 1
0x18002f10f  jz      short loc_18002F116
0x18002f111  xor     eax, eax
0x18002f113  mov     [rsi], ax
0x18002f116  mov     rcx, [rsp+870h+var_838]; hKey
0x18002f11b  lea     rax, [rsp+870h+cbData]
0x18002f120  mov     [rsp+870h+lpcbData], rax; lpcbData
0x18002f125  lea     r14, [rdi+3Ah]
0x18002f129  lea     r9, [rsp+870h+Type]; lpType
0x18002f12e  mov     [rsp+870h+phkResult], r14; lpData
0x18002f133  xor     r8d, r8d; lpReserved
0x18002f136  mov     [rsp+870h+cbData], ebx
0x18002f13a  lea     rdx, aDhcpsubnetmask; "DhcpSubnetMask"
0x18002f141  call    cs:__imp_RegQueryValueExW
0x18002f148  nop     dword ptr [rax+rax+00h]
0x18002f14d  mov     ebx, eax
0x18002f14f  test    eax, eax
0x18002f151  jnz     short loc_18002F15A
0x18002f153  cmp     [rsp+870h+Type], 1
0x18002f158  jz      short loc_18002F165
0x18002f15a  xor     ebx, ebx
0x18002f15c  xor     eax, eax
0x18002f15e  mov     [r14], ax
0x18002f162  mov     [rsi], ax
0x18002f165  mov     rcx, [rsp+870h+var_838]; hKey
0x18002f16a  lea     r9, [rdi+78h]
0x18002f16e  mov     r8d, 1
0x18002f174  lea     rdx, aDomain; "Domain"
0x18002f17b  call    RegQueryValueWithAllocW
0x18002f180  mov     rcx, [rsp+870h+var_838]; hKey
0x18002f185  lea     r9, [rdi+68h]
0x18002f189  mov     r8d, 1
0x18002f18f  lea     rdx, aNameserver; "NameServer"
0x18002f196  call    RegQueryValueWithAllocW
0x18002f19b  mov     rcx, [rsp+870h+hKey]; hKey
0x18002f1a0  test    rcx, rcx
0x18002f1a3  jz      short loc_18002F1B1
0x18002f1a5  call    cs:__imp_RegCloseKey
0x18002f1ac  nop     dword ptr [rax+rax+00h]
0x18002f1b1  mov     rcx, [rsp+870h+var_838]; hKey
0x18002f1b6  test    rcx, rcx
0x18002f1b9  jz      short loc_18002F1C7
0x18002f1bb  call    cs:__imp_RegCloseKey
0x18002f1c2  nop     dword ptr [rax+rax+00h]
0x18002f1c7  test    ebx, ebx
0x18002f1c9  jz      short loc_18002F1FB
0x18002f1cb  mov     rcx, [rdi+78h]; hMem
0x18002f1cf  call    cs:__imp_LocalFree
0x18002f1d6  nop     dword ptr [rax+rax+00h]
0x18002f1db  mov     rcx, [rdi+68h]; hMem
0x18002f1df  mov     qword ptr [rdi+78h], 0
0x18002f1e7  call    cs:__imp_LocalFree
0x18002f1ee  nop     dword ptr [rax+rax+00h]
0x18002f1f3  mov     qword ptr [rdi+68h], 0
0x18002f1fb  mov     eax, ebx
0x18002f1fd  mov     rcx, [rbp+770h+var_20]
0x18002f204  xor     rcx, rsp; StackCookie
0x18002f207  call    __security_check_cookie
0x18002f20c  lea     r11, [rsp+870h+var_10]
0x18002f214  mov     rbx, [r11+30h]
0x18002f218  mov     rsi, [r11+38h]
0x18002f21c  mov     rsp, r11
0x18002f21f  pop     r14
0x18002f221  pop     rdi
0x18002f222  pop     rbp
0x18002f223  retn
```

# LoadTcpipParam

- ea: `0x18002dc14`
- end: `0x18002def6`
- name: `LoadTcpipParam`
- size: `738`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002d904`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x18002dc14`
- `0x18002e720`
- `0x180030da4`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18002dcc3`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18002dcc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dead`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002debf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dead`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002debf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dcec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dd81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dcec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dd81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ddf0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002de31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ddf0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002de31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002de8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002de9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002de8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002de9f`

## string_xrefs

- `0x18002dd1c`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002dd57`: `RegOpenKeyEx(%ws) failed and returned %d`

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
    v6 = qword_18004C648;
    if ( qword_18004C648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C648,
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
      if ( !qword_18004C640 )
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
    if ( qword_18004C640 )
    {
      v10 = *(const WCHAR **)(a2 + 8);
      LOWORD(v20) = 0;
      v9 = v8;
LABEL_9:
      FormatRRASErrorString(&v20, L"RegOpenKeyEx(%ws) failed and returned %d", v10, v9);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C640, &v20);
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
    RegQueryValueWithAllocW(v18, L"Domain");
    RegQueryValueWithAllocW(v18, L"NameServer");
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
0x18002dc14  mov     [rsp-8+arg_10], rbx
0x18002dc19  mov     [rsp-8+arg_18], rsi
0x18002dc1e  push    rbp
0x18002dc1f  push    rdi
0x18002dc20  push    r14
0x18002dc22  lea     rbp, [rsp-760h]
0x18002dc2a  sub     rsp, 860h
0x18002dc31  mov     rax, cs:__security_cookie
0x18002dc38  xor     rax, rsp
0x18002dc3b  mov     [rbp+770h+var_20], rax
0x18002dc42  mov     rdi, rdx
0x18002dc45  mov     [rsp+870h+hKey], 0
0x18002dc4e  mov     rbx, rcx
0x18002dc51  mov     [rsp+870h+var_838], 0
0x18002dc5a  xor     eax, eax
0x18002dc5c  mov     [rsp+870h+Type], 0
0x18002dc64  xor     edx, edx; Val
0x18002dc66  mov     [rsp+870h+var_820], eax
0x18002dc6a  lea     rcx, [rsp+870h+var_81C]; void *
0x18002dc6f  mov     [rsp+870h+cbData], 0
0x18002dc77  mov     r8d, 7FCh; Size
0x18002dc7d  call    memset_0
0x18002dc82  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002dc89  jz      short loc_18002DCB3
0x18002dc8b  mov     rdx, cs:qword_18004C648
0x18002dc92  test    rdx, rdx
0x18002dc95  jz      short loc_18002DCBF
0x18002dc97  mov     rcx, cs:gIphlpEtwContext
0x18002dc9e  lea     r8, aLoadtcpipparam; "LoadTcpipParam"
0x18002dca5  mov     rax, cs:gIphlpTemplateFunc
0x18002dcac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcb1  jmp     short loc_18002DCBF
0x18002dcb3  lea     rcx, aLoadtcpipparam_0; "LoadTcpipParam"
0x18002dcba  call    TraceHlp
0x18002dcbf  mov     rcx, [rdi+8]
0x18002dcc3  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18002dcc9  lea     rax, [rsp+870h+hKey]
0x18002dcce  mov     r14d, 20019h
0x18002dcd4  lea     rsi, aInterfaces; "Interfaces"
0x18002dcdb  mov     [rsp+870h+phkResult], rax; phkResult
0x18002dce0  mov     r9d, r14d; samDesired
0x18002dce3  mov     rdx, rsi; lpSubKey
0x18002dce6  xor     r8d, r8d; ulOptions
0x18002dce9  mov     rcx, rbx; hKey
0x18002dcec  call    cs:__imp_RegOpenKeyExW
0x18002dcf2  mov     ebx, eax
0x18002dcf4  test    eax, eax
0x18002dcf6  jz      short loc_18002DD68
0x18002dcf8  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002dcff  jz      short loc_18002DD51
0x18002dd01  cmp     cs:qword_18004C640, 0
0x18002dd09  jz      loc_18002DE85
0x18002dd0f  xor     ecx, ecx
0x18002dd11  mov     r9d, eax
0x18002dd14  mov     word ptr [rsp+870h+var_820], cx
0x18002dd19  mov     r8, rsi
0x18002dd1c  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002dd23  lea     rcx, [rsp+870h+var_820]
0x18002dd28  call    FormatRRASErrorString
0x18002dd2d  mov     rdx, cs:qword_18004C640
0x18002dd34  lea     r8, [rsp+870h+var_820]
0x18002dd39  mov     rcx, cs:gIphlpEtwContext
0x18002dd40  mov     rax, cs:gIphlpTemplateFunc
0x18002dd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd4c  jmp     loc_18002DE85
0x18002dd51  mov     r8d, eax
0x18002dd54  mov     rdx, rsi
0x18002dd57  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002dd5e  call    TraceHlp
0x18002dd63  jmp     loc_18002DE85
0x18002dd68  mov     rdx, [rdi+8]; lpSubKey
0x18002dd6c  lea     rax, [rsp+870h+var_838]
0x18002dd71  mov     rcx, [rsp+870h+hKey]; hKey
0x18002dd76  mov     r9d, r14d; samDesired
0x18002dd79  xor     r8d, r8d; ulOptions
0x18002dd7c  mov     [rsp+870h+phkResult], rax; phkResult
0x18002dd81  call    cs:__imp_RegOpenKeyExW
0x18002dd87  mov     ebx, eax
0x18002dd89  test    eax, eax
0x18002dd8b  jz      short loc_18002DDC0
0x18002dd8d  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002dd94  jz      short loc_18002DDB7
0x18002dd96  cmp     cs:qword_18004C640, 0
0x18002dd9e  jz      loc_18002DE85
0x18002dda4  mov     r8, [rdi+8]
0x18002dda8  xor     eax, eax
0x18002ddaa  mov     word ptr [rsp+870h+var_820], ax
0x18002ddaf  mov     r9d, ebx
0x18002ddb2  jmp     loc_18002DD1C
0x18002ddb7  mov     rdx, [rdi+8]
0x18002ddbb  mov     r8d, ebx
0x18002ddbe  jmp     short loc_18002DD57
0x18002ddc0  mov     rcx, [rsp+870h+var_838]; hKey
0x18002ddc5  lea     rax, [rsp+870h+cbData]
0x18002ddca  mov     [rsp+870h+lpcbData], rax; lpcbData
0x18002ddcf  lea     rsi, [rdi+10h]
0x18002ddd3  mov     ebx, 2Ah ; '*'
0x18002ddd8  mov     [rsp+870h+phkResult], rsi; lpData
0x18002dddd  lea     r9, [rsp+870h+Type]; lpType
0x18002dde2  mov     [rsp+870h+cbData], ebx
0x18002dde6  xor     r8d, r8d; lpReserved
0x18002dde9  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x18002ddf0  call    cs:__imp_RegQueryValueExW
0x18002ddf6  test    eax, eax
0x18002ddf8  jnz     short loc_18002DE01
0x18002ddfa  cmp     [rsp+870h+Type], 1
0x18002ddff  jz      short loc_18002DE06
0x18002de01  xor     eax, eax
0x18002de03  mov     [rsi], ax
0x18002de06  mov     rcx, [rsp+870h+var_838]; hKey
0x18002de0b  lea     rax, [rsp+870h+cbData]
0x18002de10  mov     [rsp+870h+lpcbData], rax; lpcbData
0x18002de15  lea     r14, [rdi+3Ah]
0x18002de19  lea     r9, [rsp+870h+Type]; lpType
0x18002de1e  mov     [rsp+870h+phkResult], r14; lpData
0x18002de23  xor     r8d, r8d; lpReserved
0x18002de26  mov     [rsp+870h+cbData], ebx
0x18002de2a  lea     rdx, aDhcpsubnetmask; "DhcpSubnetMask"
0x18002de31  call    cs:__imp_RegQueryValueExW
0x18002de37  mov     ebx, eax
0x18002de39  test    eax, eax
0x18002de3b  jnz     short loc_18002DE44
0x18002de3d  cmp     [rsp+870h+Type], 1
0x18002de42  jz      short loc_18002DE4F
0x18002de44  xor     ebx, ebx
0x18002de46  xor     eax, eax
0x18002de48  mov     [r14], ax
0x18002de4c  mov     [rsi], ax
0x18002de4f  mov     rcx, [rsp+870h+var_838]; hKey
0x18002de54  lea     r9, [rdi+78h]
0x18002de58  mov     r8d, 1
0x18002de5e  lea     rdx, aDomain; "Domain"
0x18002de65  call    RegQueryValueWithAllocW
0x18002de6a  mov     rcx, [rsp+870h+var_838]; hKey
0x18002de6f  lea     r9, [rdi+68h]
0x18002de73  mov     r8d, 1
0x18002de79  lea     rdx, aNameserver; "NameServer"
0x18002de80  call    RegQueryValueWithAllocW
0x18002de85  mov     rcx, [rsp+870h+hKey]; hKey
0x18002de8a  test    rcx, rcx
0x18002de8d  jz      short loc_18002DE95
0x18002de8f  call    cs:__imp_RegCloseKey
0x18002de95  mov     rcx, [rsp+870h+var_838]; hKey
0x18002de9a  test    rcx, rcx
0x18002de9d  jz      short loc_18002DEA5
0x18002de9f  call    cs:__imp_RegCloseKey
0x18002dea5  test    ebx, ebx
0x18002dea7  jz      short loc_18002DECD
0x18002dea9  mov     rcx, [rdi+78h]; hMem
0x18002dead  call    cs:__imp_LocalFree
0x18002deb3  mov     rcx, [rdi+68h]; hMem
0x18002deb7  mov     qword ptr [rdi+78h], 0
0x18002debf  call    cs:__imp_LocalFree
0x18002dec5  mov     qword ptr [rdi+68h], 0
0x18002decd  mov     eax, ebx
0x18002decf  mov     rcx, [rbp+770h+var_20]
0x18002ded6  xor     rcx, rsp; StackCookie
0x18002ded9  call    __security_check_cookie
0x18002dede  lea     r11, [rsp+870h+var_10]
0x18002dee6  mov     rbx, [r11+30h]
0x18002deea  mov     rsi, [r11+38h]
0x18002deee  mov     rsp, r11
0x18002def1  pop     r14
0x18002def3  pop     rdi
0x18002def4  pop     rbp
0x18002def5  retn
```

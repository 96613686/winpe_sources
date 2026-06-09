# SaveTcpipV6Info

- ea: `0x18002f038`
- end: `0x18002f2b6`
- name: `SaveTcpipV6Info`
- size: `638`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18001ffc4`
- `0x18002038c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x18002f038`
- `0x18002f2bc`
- `0x180030da4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f14a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f1dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f14a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f1dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f27a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f28a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f27a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f28a`

## string_xrefs

- `0x18002f17e`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002f1aa`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002f1ce`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18002f1fd`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18002f214`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18002f13c`: `System\CurrentControlSet\Services\Tcpip6\Parameters`
- `0x18002f16f`: `System\CurrentControlSet\Services\Tcpip6\Parameters`
- `0x18002f1a3`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
__int64 __fastcall SaveTcpipV6Info(_QWORD *a1)
{
  int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // ebx
  const WCHAR *v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  const wchar_t *v8; // r8
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKey = 0;
  phkResult = 0;
  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  v2 = gIsIphlpEtwTracingAvailable;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( !qword_18004C648 )
      goto LABEL_8;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      qword_18004C648,
      L"SaveTcpipV6Info");
  }
  else
  {
    TraceHlp("SaveTcpipV6Info");
  }
  v2 = gIsIphlpEtwTracingAvailable;
  if ( !gIsIphlpEtwTracingAvailable )
  {
LABEL_9:
    TraceHlp("SaveTcpipV6Info");
    goto LABEL_10;
  }
  if ( qword_18004C648 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      qword_18004C648,
      L"SaveTcpipV6Info");
LABEL_10:
    v2 = gIsIphlpEtwTracingAvailable;
    goto LABEL_11;
  }
LABEL_8:
  if ( !v2 )
    goto LABEL_9;
LABEL_11:
  if ( a1 && *a1 )
  {
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters",
           0,
           0x20006u,
           &hKey);
    v4 = v3;
    if ( v3 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004C640 )
          goto LABEL_30;
        v5 = L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters";
        LOWORD(v12) = 0;
        v6 = v3;
LABEL_17:
        FormatRRASErrorString(&v12, L"RegOpenKeyEx(%ws) failed and returned %d", v5, v6);
        v7 = qword_18004C640;
        v8 = (const wchar_t *)&v12;
LABEL_28:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(gIphlpEtwContext, v7, v8);
        goto LABEL_30;
      }
    }
    else
    {
      v4 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
             0,
             0x20006u,
             &phkResult);
      if ( !v4 )
      {
        v4 = SaveTcpipV6Param(phkResult, hKey, (__int64)a1);
        goto LABEL_30;
      }
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004C640 )
          goto LABEL_30;
        v5 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
        LOWORD(v12) = 0;
        v6 = v4;
        goto LABEL_17;
      }
    }
    TraceHlp("RegOpenKeyEx(%ws) failed and returned %d");
    goto LABEL_30;
  }
  v4 = 87;
  if ( v2 )
  {
    v7 = qword_18004C640;
    if ( !qword_18004C640 )
      goto LABEL_30;
    v8 = L"pTcpipInfo or wszAdapterName is NULL";
    goto LABEL_28;
  }
  TraceHlp("pTcpipInfo or wszAdapterName is NULL");
LABEL_30:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v4;
}

```

## disassembly

```asm
0x18002f038  mov     [rsp-8+arg_8], rbx
0x18002f03d  mov     [rsp-8+arg_10], rdi
0x18002f042  push    rbp
0x18002f043  lea     rbp, [rsp-750h]
0x18002f04b  sub     rsp, 850h
0x18002f052  mov     rax, cs:__security_cookie
0x18002f059  xor     rax, rsp
0x18002f05c  mov     [rbp+750h+var_10], rax
0x18002f063  mov     rdi, rcx
0x18002f066  mov     [rsp+850h+hKey], 0
0x18002f06f  xor     eax, eax
0x18002f071  mov     [rsp+850h+var_818], 0
0x18002f07a  lea     rcx, [rsp+850h+var_80C]; void *
0x18002f07f  mov     [rsp+850h+var_810], eax
0x18002f083  xor     edx, edx; Val
0x18002f085  mov     r8d, 7FCh; Size
0x18002f08b  call    memset_0
0x18002f090  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18002f096  test    eax, eax
0x18002f098  jz      short loc_18002F0C2
0x18002f09a  mov     rdx, cs:qword_18004C648
0x18002f0a1  test    rdx, rdx
0x18002f0a4  jz      short loc_18002F100
0x18002f0a6  mov     rcx, cs:gIphlpEtwContext
0x18002f0ad  lea     r8, aSavetcpipv6inf; "SaveTcpipV6Info"
0x18002f0b4  mov     rax, cs:gIphlpTemplateFunc
0x18002f0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0c0  jmp     short loc_18002F0CE
0x18002f0c2  lea     rcx, aSavetcpipv6inf_0; "SaveTcpipV6Info"
0x18002f0c9  call    TraceHlp
0x18002f0ce  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18002f0d4  test    eax, eax
0x18002f0d6  jz      short loc_18002F104
0x18002f0d8  mov     rdx, cs:qword_18004C648
0x18002f0df  test    rdx, rdx
0x18002f0e2  jz      short loc_18002F100
0x18002f0e4  mov     rcx, cs:gIphlpEtwContext
0x18002f0eb  lea     r8, aSavetcpipv6inf; "SaveTcpipV6Info"
0x18002f0f2  mov     rax, cs:gIphlpTemplateFunc
0x18002f0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0fe  jmp     short loc_18002F110
0x18002f100  test    eax, eax
0x18002f102  jnz     short loc_18002F116
0x18002f104  lea     rcx, aSavetcpipv6inf_0; "SaveTcpipV6Info"
0x18002f10b  call    TraceHlp
0x18002f110  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18002f116  test    rdi, rdi
0x18002f119  jz      loc_18002F233
0x18002f11f  cmp     qword ptr [rdi], 0
0x18002f123  jz      loc_18002F233
0x18002f129  lea     rax, [rsp+850h+hKey]
0x18002f12e  mov     r9d, 20006h; samDesired
0x18002f134  xor     r8d, r8d; ulOptions
0x18002f137  mov     [rsp+850h+phkResult], rax; phkResult
0x18002f13c  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x18002f143  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f14a  call    cs:__imp_RegOpenKeyExW
0x18002f150  mov     ebx, eax
0x18002f152  test    eax, eax
0x18002f154  jz      short loc_18002F1BB
0x18002f156  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002f15d  jz      short loc_18002F1A0
0x18002f15f  cmp     cs:qword_18004C640, 0
0x18002f167  jz      loc_18002F270
0x18002f16d  xor     ecx, ecx
0x18002f16f  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x18002f176  mov     word ptr [rsp+850h+var_810], cx
0x18002f17b  mov     r9d, eax
0x18002f17e  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002f185  lea     rcx, [rsp+850h+var_810]
0x18002f18a  call    FormatRRASErrorString
0x18002f18f  mov     rdx, cs:qword_18004C640
0x18002f196  lea     r8, [rsp+850h+var_810]
0x18002f19b  jmp     loc_18002F24F
0x18002f1a0  mov     r8d, eax
0x18002f1a3  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x18002f1aa  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002f1b1  call    TraceHlp
0x18002f1b6  jmp     loc_18002F270
0x18002f1bb  lea     rax, [rsp+850h+var_818]
0x18002f1c0  mov     r9d, 20006h; samDesired
0x18002f1c6  xor     r8d, r8d; ulOptions
0x18002f1c9  mov     [rsp+850h+phkResult], rax; phkResult
0x18002f1ce  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002f1d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f1dc  call    cs:__imp_RegOpenKeyExW
0x18002f1e2  mov     ebx, eax
0x18002f1e4  test    eax, eax
0x18002f1e6  jz      short loc_18002F21D
0x18002f1e8  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002f1ef  jz      short loc_18002F211
0x18002f1f1  cmp     cs:qword_18004C640, 0
0x18002f1f9  jz      short loc_18002F270
0x18002f1fb  xor     eax, eax
0x18002f1fd  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002f204  mov     word ptr [rsp+850h+var_810], ax
0x18002f209  mov     r9d, ebx
0x18002f20c  jmp     loc_18002F17E
0x18002f211  mov     r8d, ebx
0x18002f214  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002f21b  jmp     short loc_18002F1AA
0x18002f21d  mov     rdx, [rsp+850h+hKey]; HKEY
0x18002f222  mov     r8, rdi
0x18002f225  mov     rcx, [rsp+850h+var_818]; hKey
0x18002f22a  call    SaveTcpipV6Param
0x18002f22f  mov     ebx, eax
0x18002f231  jmp     short loc_18002F270
0x18002f233  mov     ebx, 57h ; 'W'
0x18002f238  test    eax, eax
0x18002f23a  jz      short loc_18002F264
0x18002f23c  mov     rdx, cs:qword_18004C640
0x18002f243  test    rdx, rdx
0x18002f246  jz      short loc_18002F270
0x18002f248  lea     r8, aPtcpipinfoOrWs; "pTcpipInfo or wszAdapterName is NULL"
0x18002f24f  mov     rcx, cs:gIphlpEtwContext
0x18002f256  mov     rax, cs:gIphlpTemplateFunc
0x18002f25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f262  jmp     short loc_18002F270
0x18002f264  lea     rcx, aPtcpipinfoOrWs_0; "pTcpipInfo or wszAdapterName is NULL"
0x18002f26b  call    TraceHlp
0x18002f270  mov     rcx, [rsp+850h+hKey]; hKey
0x18002f275  test    rcx, rcx
0x18002f278  jz      short loc_18002F280
0x18002f27a  call    cs:__imp_RegCloseKey
0x18002f280  mov     rcx, [rsp+850h+var_818]; hKey
0x18002f285  test    rcx, rcx
0x18002f288  jz      short loc_18002F290
0x18002f28a  call    cs:__imp_RegCloseKey
0x18002f290  mov     eax, ebx
0x18002f292  mov     rcx, [rbp+750h+var_10]
0x18002f299  xor     rcx, rsp; StackCookie
0x18002f29c  call    __security_check_cookie
0x18002f2a1  lea     r11, [rsp+850h+var_s0]
0x18002f2a9  mov     rbx, [r11+18h]
0x18002f2ad  mov     rdi, [r11+20h]
0x18002f2b1  mov     rsp, r11
0x18002f2b4  pop     rbp
0x18002f2b5  retn
```

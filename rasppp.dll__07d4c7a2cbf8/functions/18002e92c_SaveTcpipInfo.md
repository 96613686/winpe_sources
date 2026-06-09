# SaveTcpipInfo

- ea: `0x18002e92c`
- end: `0x18002ebd1`
- name: `SaveTcpipInfo`
- size: `677`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18001b074`
- `0x18001d1d0`
- `0x18001fd58`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x18002e92c`
- `0x18002ebd8`
- `0x18002f784`
- `0x180030da4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ea3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002eaed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ea3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002eaed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eb95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eba5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eb95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eba5`

## string_xrefs

- `0x18002ea78`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002eaa4`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002ea31`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18002ea69`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18002ea9d`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18002eadf`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`
- `0x18002eb1a`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`
- `0x18002eb31`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall SaveTcpipInfo(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // ebx
  const WCHAR *v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  const wchar_t *v8; // r8
  unsigned int v9; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKey = 0;
  phkResult = 0;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  v2 = gIsIphlpEtwTracingAvailable;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( !qword_18004C648 )
      goto LABEL_8;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      qword_18004C648,
      L"SaveTcpipInfo");
  }
  else
  {
    TraceHlp("SaveTcpipInfo");
  }
  v2 = gIsIphlpEtwTracingAvailable;
  if ( !gIsIphlpEtwTracingAvailable )
  {
LABEL_9:
    TraceHlp("SaveTcpipInfo");
    goto LABEL_10;
  }
  if ( qword_18004C648 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      qword_18004C648,
      L"SaveTcpipInfo");
LABEL_10:
    v2 = gIsIphlpEtwTracingAvailable;
    goto LABEL_11;
  }
LABEL_8:
  if ( !v2 )
    goto LABEL_9;
LABEL_11:
  if ( a1 && *(_QWORD *)(a1 + 8) )
  {
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
           0,
           0x20006u,
           &hKey);
    v4 = v3;
    if ( v3 )
    {
      if ( v3 != 2 )
      {
        if ( gIsIphlpEtwTracingAvailable )
        {
          if ( !qword_18004C640 )
            goto LABEL_34;
          v5 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
          LOWORD(v13) = 0;
          v6 = v3;
LABEL_18:
          FormatRRASErrorString(&v13, L"RegOpenKeyEx(%ws) failed and returned %d", v5, v6);
          v7 = qword_18004C640;
          v8 = (const wchar_t *)&v13;
LABEL_32:
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(gIphlpEtwContext, v7, v8);
          goto LABEL_34;
        }
        goto LABEL_19;
      }
    }
    else
    {
      v4 = SaveTcpipParam(hKey, a1);
      if ( v4 )
        goto LABEL_34;
    }
    v9 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces",
           0,
           0x20006u,
           &phkResult);
    v4 = v9;
    if ( !v9 )
    {
      v4 = SaveWinsParam(phkResult, a1);
      goto LABEL_34;
    }
    if ( v9 == 2 )
    {
      v4 = 0;
      goto LABEL_34;
    }
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004C640 )
        goto LABEL_34;
      v5 = L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces";
      LOWORD(v13) = 0;
      v6 = v9;
      goto LABEL_18;
    }
LABEL_19:
    TraceHlp("RegOpenKeyEx(%ws) failed and returned %d");
    goto LABEL_34;
  }
  v4 = 87;
  if ( v2 )
  {
    v7 = qword_18004C640;
    if ( !qword_18004C640 )
      goto LABEL_34;
    v8 = L"pTcpipInfo or wszAdapterName is NULL";
    goto LABEL_32;
  }
  TraceHlp("pTcpipInfo or wszAdapterName is NULL");
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v4;
}

```

## disassembly

```asm
0x18002e92c  mov     [rsp-8+arg_8], rbx
0x18002e931  mov     [rsp-8+arg_10], rdi
0x18002e936  push    rbp
0x18002e937  lea     rbp, [rsp-750h]
0x18002e93f  sub     rsp, 850h
0x18002e946  mov     rax, cs:__security_cookie
0x18002e94d  xor     rax, rsp
0x18002e950  mov     [rbp+750h+var_10], rax
0x18002e957  mov     rdi, rcx
0x18002e95a  mov     [rsp+850h+hKey], 0
0x18002e963  xor     eax, eax
0x18002e965  mov     [rsp+850h+var_818], 0
0x18002e96e  lea     rcx, [rsp+850h+var_80C]; void *
0x18002e973  mov     [rsp+850h+var_810], eax
0x18002e977  xor     edx, edx; Val
0x18002e979  mov     r8d, 7FCh; Size
0x18002e97f  call    memset_0
0x18002e984  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18002e98a  test    eax, eax
0x18002e98c  jz      short loc_18002E9B6
0x18002e98e  mov     rdx, cs:qword_18004C648
0x18002e995  test    rdx, rdx
0x18002e998  jz      short loc_18002E9F4
0x18002e99a  mov     rcx, cs:gIphlpEtwContext
0x18002e9a1  lea     r8, aSavetcpipinfo_0; "SaveTcpipInfo"
0x18002e9a8  mov     rax, cs:gIphlpTemplateFunc
0x18002e9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9b4  jmp     short loc_18002E9C2
0x18002e9b6  lea     rcx, aSavetcpipinfo; "SaveTcpipInfo"
0x18002e9bd  call    TraceHlp
0x18002e9c2  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18002e9c8  test    eax, eax
0x18002e9ca  jz      short loc_18002E9F8
0x18002e9cc  mov     rdx, cs:qword_18004C648
0x18002e9d3  test    rdx, rdx
0x18002e9d6  jz      short loc_18002E9F4
0x18002e9d8  mov     rcx, cs:gIphlpEtwContext
0x18002e9df  lea     r8, aSavetcpipinfo_0; "SaveTcpipInfo"
0x18002e9e6  mov     rax, cs:gIphlpTemplateFunc
0x18002e9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9f2  jmp     short loc_18002EA04
0x18002e9f4  test    eax, eax
0x18002e9f6  jnz     short loc_18002EA0A
0x18002e9f8  lea     rcx, aSavetcpipinfo; "SaveTcpipInfo"
0x18002e9ff  call    TraceHlp
0x18002ea04  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18002ea0a  test    rdi, rdi
0x18002ea0d  jz      loc_18002EB4E
0x18002ea13  cmp     qword ptr [rdi+8], 0
0x18002ea18  jz      loc_18002EB4E
0x18002ea1e  lea     rax, [rsp+850h+hKey]
0x18002ea23  mov     r9d, 20006h; samDesired
0x18002ea29  xor     r8d, r8d; ulOptions
0x18002ea2c  mov     [rsp+850h+phkResult], rax; phkResult
0x18002ea31  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002ea38  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ea3f  call    cs:__imp_RegOpenKeyExW
0x18002ea45  mov     ebx, eax
0x18002ea47  test    eax, eax
0x18002ea49  jz      short loc_18002EAB5
0x18002ea4b  cmp     eax, 2
0x18002ea4e  jz      short loc_18002EACC
0x18002ea50  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002ea57  jz      short loc_18002EA9A
0x18002ea59  cmp     cs:qword_18004C640, 0
0x18002ea61  jz      loc_18002EB8B
0x18002ea67  xor     ecx, ecx
0x18002ea69  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002ea70  mov     word ptr [rsp+850h+var_810], cx
0x18002ea75  mov     r9d, eax
0x18002ea78  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002ea7f  lea     rcx, [rsp+850h+var_810]
0x18002ea84  call    FormatRRASErrorString
0x18002ea89  mov     rdx, cs:qword_18004C640
0x18002ea90  lea     r8, [rsp+850h+var_810]
0x18002ea95  jmp     loc_18002EB6A
0x18002ea9a  mov     r8d, eax
0x18002ea9d  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002eaa4  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002eaab  call    TraceHlp
0x18002eab0  jmp     loc_18002EB8B
0x18002eab5  mov     rcx, [rsp+850h+hKey]; hKey
0x18002eaba  mov     rdx, rdi
0x18002eabd  call    SaveTcpipParam
0x18002eac2  mov     ebx, eax
0x18002eac4  test    eax, eax
0x18002eac6  jnz     loc_18002EB8B
0x18002eacc  lea     rax, [rsp+850h+var_818]
0x18002ead1  mov     r9d, 20006h; samDesired
0x18002ead7  xor     r8d, r8d; ulOptions
0x18002eada  mov     [rsp+850h+phkResult], rax; phkResult
0x18002eadf  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Ne"...
0x18002eae6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002eaed  call    cs:__imp_RegOpenKeyExW
0x18002eaf3  mov     ebx, eax
0x18002eaf5  test    eax, eax
0x18002eaf7  jz      short loc_18002EB3D
0x18002eaf9  cmp     eax, 2
0x18002eafc  jnz     short loc_18002EB05
0x18002eafe  xor     ebx, ebx
0x18002eb00  jmp     loc_18002EB8B
0x18002eb05  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002eb0c  jz      short loc_18002EB2E
0x18002eb0e  cmp     cs:qword_18004C640, 0
0x18002eb16  jz      short loc_18002EB8B
0x18002eb18  xor     eax, eax
0x18002eb1a  lea     r8, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Ne"...
0x18002eb21  mov     word ptr [rsp+850h+var_810], ax
0x18002eb26  mov     r9d, ebx
0x18002eb29  jmp     loc_18002EA78
0x18002eb2e  mov     r8d, ebx
0x18002eb31  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Ne"...
0x18002eb38  jmp     loc_18002EAA4
0x18002eb3d  mov     rcx, [rsp+850h+var_818]; hKey
0x18002eb42  mov     rdx, rdi
0x18002eb45  call    SaveWinsParam
0x18002eb4a  mov     ebx, eax
0x18002eb4c  jmp     short loc_18002EB8B
0x18002eb4e  mov     ebx, 57h ; 'W'
0x18002eb53  test    eax, eax
0x18002eb55  jz      short loc_18002EB7F
0x18002eb57  mov     rdx, cs:qword_18004C640
0x18002eb5e  test    rdx, rdx
0x18002eb61  jz      short loc_18002EB8B
0x18002eb63  lea     r8, aPtcpipinfoOrWs; "pTcpipInfo or wszAdapterName is NULL"
0x18002eb6a  mov     rcx, cs:gIphlpEtwContext
0x18002eb71  mov     rax, cs:gIphlpTemplateFunc
0x18002eb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb7d  jmp     short loc_18002EB8B
0x18002eb7f  lea     rcx, aPtcpipinfoOrWs_0; "pTcpipInfo or wszAdapterName is NULL"
0x18002eb86  call    TraceHlp
0x18002eb8b  mov     rcx, [rsp+850h+hKey]; hKey
0x18002eb90  test    rcx, rcx
0x18002eb93  jz      short loc_18002EB9B
0x18002eb95  call    cs:__imp_RegCloseKey
0x18002eb9b  mov     rcx, [rsp+850h+var_818]; hKey
0x18002eba0  test    rcx, rcx
0x18002eba3  jz      short loc_18002EBAB
0x18002eba5  call    cs:__imp_RegCloseKey
0x18002ebab  mov     eax, ebx
0x18002ebad  mov     rcx, [rbp+750h+var_10]
0x18002ebb4  xor     rcx, rsp; StackCookie
0x18002ebb7  call    __security_check_cookie
0x18002ebbc  lea     r11, [rsp+850h+var_s0]
0x18002ebc4  mov     rbx, [r11+18h]
0x18002ebc8  mov     rdi, [r11+20h]
0x18002ebcc  mov     rsp, r11
0x18002ebcf  pop     rbp
0x18002ebd0  retn
```

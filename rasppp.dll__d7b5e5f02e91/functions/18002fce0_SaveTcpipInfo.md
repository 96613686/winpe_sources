# SaveTcpipInfo

- ea: `0x18002fce0`
- end: `0x18002ff9e`
- name: `SaveTcpipInfo`
- size: `702`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18001bab4`
- `0x18001dcb0`
- `0x180020920`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x18002fce0`
- `0x18002ffa4`
- `0x180030bec`
- `0x18003230c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fdf3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fea7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fdf3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fea7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ff55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ff6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ff55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ff6b`

## string_xrefs

- `0x18002fe32`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002fe5e`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002fde5`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18002fe23`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18002fe57`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18002fe99`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`
- `0x18002feda`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`
- `0x18002fef1`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`

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
    if ( !qword_18004D648 )
      goto LABEL_8;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      qword_18004D648,
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
  if ( qword_18004D648 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      qword_18004D648,
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
          if ( !qword_18004D640 )
            goto LABEL_34;
          v5 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
          LOWORD(v13) = 0;
          v6 = v3;
LABEL_18:
          FormatRRASErrorString((wchar_t *)&v13, L"RegOpenKeyEx(%ws) failed and returned %d", v5, v6);
          v7 = qword_18004D640;
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
      if ( !qword_18004D640 )
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
    v7 = qword_18004D640;
    if ( !qword_18004D640 )
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
0x18002fce0  mov     [rsp-8+arg_8], rbx
0x18002fce5  mov     [rsp-8+arg_10], rdi
0x18002fcea  push    rbp
0x18002fceb  lea     rbp, [rsp-750h]
0x18002fcf3  sub     rsp, 850h
0x18002fcfa  mov     rax, cs:__security_cookie
0x18002fd01  xor     rax, rsp
0x18002fd04  mov     [rbp+750h+var_10], rax
0x18002fd0b  mov     rdi, rcx
0x18002fd0e  mov     [rsp+850h+hKey], 0
0x18002fd17  xor     eax, eax
0x18002fd19  mov     [rsp+850h+var_818], 0
0x18002fd22  lea     rcx, [rsp+850h+var_80C]; void *
0x18002fd27  mov     [rsp+850h+var_810], eax
0x18002fd2b  xor     edx, edx; Val
0x18002fd2d  mov     r8d, 7FCh; Size
0x18002fd33  call    memset_0
0x18002fd38  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18002fd3e  test    eax, eax
0x18002fd40  jz      short loc_18002FD6A
0x18002fd42  mov     rdx, qword ptr cs:xmmword_18004D648
0x18002fd49  test    rdx, rdx
0x18002fd4c  jz      short loc_18002FDA8
0x18002fd4e  mov     rcx, cs:gIphlpEtwContext
0x18002fd55  lea     r8, aSavetcpipinfo_0; "SaveTcpipInfo"
0x18002fd5c  mov     rax, cs:gIphlpTemplateFunc
0x18002fd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd68  jmp     short loc_18002FD76
0x18002fd6a  lea     rcx, aSavetcpipinfo; "SaveTcpipInfo"
0x18002fd71  call    TraceHlp
0x18002fd76  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18002fd7c  test    eax, eax
0x18002fd7e  jz      short loc_18002FDAC
0x18002fd80  mov     rdx, qword ptr cs:xmmword_18004D648
0x18002fd87  test    rdx, rdx
0x18002fd8a  jz      short loc_18002FDA8
0x18002fd8c  mov     rcx, cs:gIphlpEtwContext
0x18002fd93  lea     r8, aSavetcpipinfo_0; "SaveTcpipInfo"
0x18002fd9a  mov     rax, cs:gIphlpTemplateFunc
0x18002fda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fda6  jmp     short loc_18002FDB8
0x18002fda8  test    eax, eax
0x18002fdaa  jnz     short loc_18002FDBE
0x18002fdac  lea     rcx, aSavetcpipinfo; "SaveTcpipInfo"
0x18002fdb3  call    TraceHlp
0x18002fdb8  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18002fdbe  test    rdi, rdi
0x18002fdc1  jz      loc_18002FF0E
0x18002fdc7  cmp     qword ptr [rdi+8], 0
0x18002fdcc  jz      loc_18002FF0E
0x18002fdd2  lea     rax, [rsp+850h+hKey]
0x18002fdd7  mov     r9d, 20006h; samDesired
0x18002fddd  xor     r8d, r8d; ulOptions
0x18002fde0  mov     [rsp+850h+phkResult], rax; phkResult
0x18002fde5  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002fdec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002fdf3  call    cs:__imp_RegOpenKeyExW
0x18002fdfa  nop     dword ptr [rax+rax+00h]
0x18002fdff  mov     ebx, eax
0x18002fe01  test    eax, eax
0x18002fe03  jz      short loc_18002FE6F
0x18002fe05  cmp     eax, 2
0x18002fe08  jz      short loc_18002FE86
0x18002fe0a  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002fe11  jz      short loc_18002FE54
0x18002fe13  cmp     cs:qword_18004D640, 0
0x18002fe1b  jz      loc_18002FF4B
0x18002fe21  xor     ecx, ecx
0x18002fe23  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002fe2a  mov     word ptr [rsp+850h+var_810], cx
0x18002fe2f  mov     r9d, eax
0x18002fe32  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002fe39  lea     rcx, [rsp+850h+var_810]
0x18002fe3e  call    FormatRRASErrorString
0x18002fe43  mov     rdx, cs:qword_18004D640
0x18002fe4a  lea     r8, [rsp+850h+var_810]
0x18002fe4f  jmp     loc_18002FF2A
0x18002fe54  mov     r8d, eax
0x18002fe57  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002fe5e  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002fe65  call    TraceHlp
0x18002fe6a  jmp     loc_18002FF4B
0x18002fe6f  mov     rcx, [rsp+850h+hKey]; hKey
0x18002fe74  mov     rdx, rdi
0x18002fe77  call    SaveTcpipParam
0x18002fe7c  mov     ebx, eax
0x18002fe7e  test    eax, eax
0x18002fe80  jnz     loc_18002FF4B
0x18002fe86  lea     rax, [rsp+850h+var_818]
0x18002fe8b  mov     r9d, 20006h; samDesired
0x18002fe91  xor     r8d, r8d; ulOptions
0x18002fe94  mov     [rsp+850h+phkResult], rax; phkResult
0x18002fe99  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Ne"...
0x18002fea0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002fea7  call    cs:__imp_RegOpenKeyExW
0x18002feae  nop     dword ptr [rax+rax+00h]
0x18002feb3  mov     ebx, eax
0x18002feb5  test    eax, eax
0x18002feb7  jz      short loc_18002FEFD
0x18002feb9  cmp     eax, 2
0x18002febc  jnz     short loc_18002FEC5
0x18002febe  xor     ebx, ebx
0x18002fec0  jmp     loc_18002FF4B
0x18002fec5  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18002fecc  jz      short loc_18002FEEE
0x18002fece  cmp     cs:qword_18004D640, 0
0x18002fed6  jz      short loc_18002FF4B
0x18002fed8  xor     eax, eax
0x18002feda  lea     r8, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Ne"...
0x18002fee1  mov     word ptr [rsp+850h+var_810], ax
0x18002fee6  mov     r9d, ebx
0x18002fee9  jmp     loc_18002FE32
0x18002feee  mov     r8d, ebx
0x18002fef1  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Ne"...
0x18002fef8  jmp     loc_18002FE5E
0x18002fefd  mov     rcx, [rsp+850h+var_818]; hKey
0x18002ff02  mov     rdx, rdi
0x18002ff05  call    SaveWinsParam
0x18002ff0a  mov     ebx, eax
0x18002ff0c  jmp     short loc_18002FF4B
0x18002ff0e  mov     ebx, 57h ; 'W'
0x18002ff13  test    eax, eax
0x18002ff15  jz      short loc_18002FF3F
0x18002ff17  mov     rdx, cs:qword_18004D640
0x18002ff1e  test    rdx, rdx
0x18002ff21  jz      short loc_18002FF4B
0x18002ff23  lea     r8, aPtcpipinfoOrWs; "pTcpipInfo or wszAdapterName is NULL"
0x18002ff2a  mov     rcx, cs:gIphlpEtwContext
0x18002ff31  mov     rax, cs:gIphlpTemplateFunc
0x18002ff38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff3d  jmp     short loc_18002FF4B
0x18002ff3f  lea     rcx, aPtcpipinfoOrWs_0; "pTcpipInfo or wszAdapterName is NULL"
0x18002ff46  call    TraceHlp
0x18002ff4b  mov     rcx, [rsp+850h+hKey]; hKey
0x18002ff50  test    rcx, rcx
0x18002ff53  jz      short loc_18002FF61
0x18002ff55  call    cs:__imp_RegCloseKey
0x18002ff5c  nop     dword ptr [rax+rax+00h]
0x18002ff61  mov     rcx, [rsp+850h+var_818]; hKey
0x18002ff66  test    rcx, rcx
0x18002ff69  jz      short loc_18002FF77
0x18002ff6b  call    cs:__imp_RegCloseKey
0x18002ff72  nop     dword ptr [rax+rax+00h]
0x18002ff77  mov     eax, ebx
0x18002ff79  mov     rcx, [rbp+750h+var_10]
0x18002ff80  xor     rcx, rsp; StackCookie
0x18002ff83  call    __security_check_cookie
0x18002ff88  lea     r11, [rsp+850h+var_s0]
0x18002ff90  mov     rbx, [r11+18h]
0x18002ff94  mov     rdi, [r11+20h]
0x18002ff98  mov     rsp, r11
0x18002ff9b  pop     rbp
0x18002ff9c  retn
```

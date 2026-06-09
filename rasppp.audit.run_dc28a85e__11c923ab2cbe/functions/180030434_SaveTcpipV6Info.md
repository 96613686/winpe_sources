# SaveTcpipV6Info

- ea: `0x180030434`
- end: `0x1800306cb`
- name: `SaveTcpipV6Info`
- size: `663`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180020b90`
- `0x180020f88`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x180030434`
- `0x1800306d4`
- `0x18003230c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030546`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800305de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030546`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800305de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030682`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030698`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030682`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030698`

## string_xrefs

- `0x180030580`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x1800305ac`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x1800305d0`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x180030605`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18003061c`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x180030538`: `System\CurrentControlSet\Services\Tcpip6\Parameters`
- `0x180030571`: `System\CurrentControlSet\Services\Tcpip6\Parameters`
- `0x1800305a5`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

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
    if ( !qword_18004D648 )
      goto LABEL_8;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      qword_18004D648,
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
  if ( qword_18004D648 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      qword_18004D648,
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
        if ( !qword_18004D640 )
          goto LABEL_30;
        v5 = L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters";
        LOWORD(v12) = 0;
        v6 = v3;
LABEL_17:
        FormatRRASErrorString(&v12, L"RegOpenKeyEx(%ws) failed and returned %d", v5, v6);
        v7 = qword_18004D640;
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
        if ( !qword_18004D640 )
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
    v7 = qword_18004D640;
    if ( !qword_18004D640 )
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
0x180030434  mov     [rsp-8+arg_8], rbx
0x180030439  mov     [rsp-8+arg_10], rdi
0x18003043e  push    rbp
0x18003043f  lea     rbp, [rsp-750h]
0x180030447  sub     rsp, 850h
0x18003044e  mov     rax, cs:__security_cookie
0x180030455  xor     rax, rsp
0x180030458  mov     [rbp+750h+var_10], rax
0x18003045f  mov     rdi, rcx
0x180030462  mov     [rsp+850h+hKey], 0
0x18003046b  xor     eax, eax
0x18003046d  mov     [rsp+850h+var_818], 0
0x180030476  lea     rcx, [rsp+850h+var_80C]; void *
0x18003047b  mov     [rsp+850h+var_810], eax
0x18003047f  xor     edx, edx; Val
0x180030481  mov     r8d, 7FCh; Size
0x180030487  call    memset_0
0x18003048c  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x180030492  test    eax, eax
0x180030494  jz      short loc_1800304BE
0x180030496  mov     rdx, cs:qword_18004D648
0x18003049d  test    rdx, rdx
0x1800304a0  jz      short loc_1800304FC
0x1800304a2  mov     rcx, cs:gIphlpEtwContext
0x1800304a9  lea     r8, aSavetcpipv6inf; "SaveTcpipV6Info"
0x1800304b0  mov     rax, cs:gIphlpTemplateFunc
0x1800304b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304bc  jmp     short loc_1800304CA
0x1800304be  lea     rcx, aSavetcpipv6inf_0; "SaveTcpipV6Info"
0x1800304c5  call    TraceHlp
0x1800304ca  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x1800304d0  test    eax, eax
0x1800304d2  jz      short loc_180030500
0x1800304d4  mov     rdx, cs:qword_18004D648
0x1800304db  test    rdx, rdx
0x1800304de  jz      short loc_1800304FC
0x1800304e0  mov     rcx, cs:gIphlpEtwContext
0x1800304e7  lea     r8, aSavetcpipv6inf; "SaveTcpipV6Info"
0x1800304ee  mov     rax, cs:gIphlpTemplateFunc
0x1800304f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304fa  jmp     short loc_18003050C
0x1800304fc  test    eax, eax
0x1800304fe  jnz     short loc_180030512
0x180030500  lea     rcx, aSavetcpipv6inf_0; "SaveTcpipV6Info"
0x180030507  call    TraceHlp
0x18003050c  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x180030512  test    rdi, rdi
0x180030515  jz      loc_18003063B
0x18003051b  cmp     qword ptr [rdi], 0
0x18003051f  jz      loc_18003063B
0x180030525  lea     rax, [rsp+850h+hKey]
0x18003052a  mov     r9d, 20006h; samDesired
0x180030530  xor     r8d, r8d; ulOptions
0x180030533  mov     [rsp+850h+phkResult], rax; phkResult
0x180030538  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x18003053f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030546  call    cs:__imp_RegOpenKeyExW
0x18003054d  nop     dword ptr [rax+rax+00h]
0x180030552  mov     ebx, eax
0x180030554  test    eax, eax
0x180030556  jz      short loc_1800305BD
0x180030558  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18003055f  jz      short loc_1800305A2
0x180030561  cmp     cs:qword_18004D640, 0
0x180030569  jz      loc_180030678
0x18003056f  xor     ecx, ecx
0x180030571  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x180030578  mov     word ptr [rsp+850h+var_810], cx
0x18003057d  mov     r9d, eax
0x180030580  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x180030587  lea     rcx, [rsp+850h+var_810]
0x18003058c  call    FormatRRASErrorString
0x180030591  mov     rdx, cs:qword_18004D640
0x180030598  lea     r8, [rsp+850h+var_810]
0x18003059d  jmp     loc_180030657
0x1800305a2  mov     r8d, eax
0x1800305a5  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x1800305ac  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x1800305b3  call    TraceHlp
0x1800305b8  jmp     loc_180030678
0x1800305bd  lea     rax, [rsp+850h+var_818]
0x1800305c2  mov     r9d, 20006h; samDesired
0x1800305c8  xor     r8d, r8d; ulOptions
0x1800305cb  mov     [rsp+850h+phkResult], rax; phkResult
0x1800305d0  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x1800305d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800305de  call    cs:__imp_RegOpenKeyExW
0x1800305e5  nop     dword ptr [rax+rax+00h]
0x1800305ea  mov     ebx, eax
0x1800305ec  test    eax, eax
0x1800305ee  jz      short loc_180030625
0x1800305f0  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x1800305f7  jz      short loc_180030619
0x1800305f9  cmp     cs:qword_18004D640, 0
0x180030601  jz      short loc_180030678
0x180030603  xor     eax, eax
0x180030605  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18003060c  mov     word ptr [rsp+850h+var_810], ax
0x180030611  mov     r9d, ebx
0x180030614  jmp     loc_180030580
0x180030619  mov     r8d, ebx
0x18003061c  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x180030623  jmp     short loc_1800305AC
0x180030625  mov     rdx, [rsp+850h+hKey]; HKEY
0x18003062a  mov     r8, rdi
0x18003062d  mov     rcx, [rsp+850h+var_818]; hKey
0x180030632  call    SaveTcpipV6Param
0x180030637  mov     ebx, eax
0x180030639  jmp     short loc_180030678
0x18003063b  mov     ebx, 57h ; 'W'
0x180030640  test    eax, eax
0x180030642  jz      short loc_18003066C
0x180030644  mov     rdx, cs:qword_18004D640
0x18003064b  test    rdx, rdx
0x18003064e  jz      short loc_180030678
0x180030650  lea     r8, aPtcpipinfoOrWs; "pTcpipInfo or wszAdapterName is NULL"
0x180030657  mov     rcx, cs:gIphlpEtwContext
0x18003065e  mov     rax, cs:gIphlpTemplateFunc
0x180030665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003066a  jmp     short loc_180030678
0x18003066c  lea     rcx, aPtcpipinfoOrWs_0; "pTcpipInfo or wszAdapterName is NULL"
0x180030673  call    TraceHlp
0x180030678  mov     rcx, [rsp+850h+hKey]; hKey
0x18003067d  test    rcx, rcx
0x180030680  jz      short loc_18003068E
0x180030682  call    cs:__imp_RegCloseKey
0x180030689  nop     dword ptr [rax+rax+00h]
0x18003068e  mov     rcx, [rsp+850h+var_818]; hKey
0x180030693  test    rcx, rcx
0x180030696  jz      short loc_1800306A4
0x180030698  call    cs:__imp_RegCloseKey
0x18003069f  nop     dword ptr [rax+rax+00h]
0x1800306a4  mov     eax, ebx
0x1800306a6  mov     rcx, [rbp+750h+var_10]
0x1800306ad  xor     rcx, rsp; StackCookie
0x1800306b0  call    __security_check_cookie
0x1800306b5  lea     r11, [rsp+850h+var_s0]
0x1800306bd  mov     rbx, [r11+18h]
0x1800306c1  mov     rdi, [r11+20h]
0x1800306c5  mov     rsp, r11
0x1800306c8  pop     rbp
0x1800306c9  retn
```

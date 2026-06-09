# rasStatCreatePoolListFromOldValues

- ea: `0x18005ec00`
- end: `0x18005ef1b`
- name: `rasStatCreatePoolListFromOldValues`
- size: `795`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005df7c`

## callees

- `0x18005c090`
- `0x18005de48`
- `0x18005ec00`
- `0x18006a7c0`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005eec5`
- `KERNEL32!LocalFree` at `0x18005eed6`
- `KERNEL32!LocalFree` at `0x18005eec5`
- `KERNEL32!LocalFree` at `0x18005eed6`
- `KERNEL32!LocalAlloc` at `0x18005ed20`
- `KERNEL32!LocalAlloc` at `0x18005ed20`
- `ADVAPI32!RegCloseKey` at `0x18005eeb4`
- `ADVAPI32!RegCloseKey` at `0x18005eeb4`
- `ADVAPI32!RegOpenKeyExA` at `0x18005ecb6`
- `ADVAPI32!RegOpenKeyExA` at `0x18005ecb6`
- `WS2_32!__imp_inet_addr` at `0x18005ed91`
- `WS2_32!__imp_inet_addr` at `0x18005ee0a`
- `WS2_32!__imp_inet_addr` at `0x18005ed91`
- `WS2_32!__imp_inet_addr` at `0x18005ee0a`
- `WS2_32!__imp_ntohl` at `0x18005ed9f`
- `WS2_32!__imp_ntohl` at `0x18005ee18`
- `WS2_32!__imp_ntohl` at `0x18005ed9f`
- `WS2_32!__imp_ntohl` at `0x18005ee18`

## string_xrefs

- `0x18005eca8`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x18005ecd3`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x18005ec82`: `rasStatCreatePoolListFromOldValues`
- `0x18005ecda`: `Couldn't open key %hs: %d`

## pseudocode

```c
__int64 __fastcall rasStatCreatePoolListFromOldValues(_QWORD *a1, _QWORD *a2)
{
  _DWORD *v4; // rdi
  unsigned int ValueWithAllocA; // eax
  const CHAR *v6; // r8
  const wchar_t *v7; // rdx
  __int64 v8; // rdx
  const wchar_t *v9; // r8
  const CHAR *v10; // rbx
  u_long v11; // eax
  u_long v12; // esi
  u_long v13; // eax
  u_long v14; // eax
  __int64 v15; // r9
  unsigned int v16; // ebx
  bool v17; // zf
  PHKEY phkResult; // [rsp+28h] [rbp-E0h]
  HKEY hKey; // [rsp+38h] [rbp-D0h] BYREF
  char *cp; // [rsp+40h] [rbp-C8h]
  HLOCAL hMem; // [rsp+48h] [rbp-C0h]
  _QWORD v23[3]; // [rsp+50h] [rbp-B8h] BYREF
  int v24; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v25[2044]; // [rsp+6Ch] [rbp-9Ch] BYREF

  hKey = 0;
  cp = 0;
  hMem = 0;
  v24 = 0;
  v4 = 0;
  memset_0(v25, 0, sizeof(v25));
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"rasStatCreatePoolListFromOldValues");
  ValueWithAllocA = RegOpenKeyExA(
                      HKEY_LOCAL_MACHINE,
                      "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
                      0,
                      0x20019u,
                      &hKey);
  if ( ValueWithAllocA )
  {
    if ( !(_QWORD)xmmword_1800D0740 )
      goto LABEL_23;
    v6 = "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip";
    v7 = L"Couldn't open key %hs: %d";
    goto LABEL_6;
  }
  v4 = LocalAlloc(0x40u, 0x18u);
  if ( !v4 )
  {
    v8 = *((_QWORD *)&xmmword_1800D0740 + 1);
    if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    {
      v9 = L"Out of memory";
      goto LABEL_8;
    }
    goto LABEL_23;
  }
  v10 = "IpAddress";
  ValueWithAllocA = RegQueryValueWithAllocA(hKey, "IpAddress");
  if ( ValueWithAllocA )
    goto LABEL_13;
  v11 = inet_addr(cp);
  v12 = ntohl(v11);
  if ( v12 == -1 )
  {
LABEL_16:
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"Bad value in %hs", v10);
      goto LABEL_7;
    }
    goto LABEL_23;
  }
  v10 = "IpMask";
  ValueWithAllocA = RegQueryValueWithAllocA(hKey, "IpMask");
  if ( !ValueWithAllocA )
  {
    v13 = inet_addr((const char *)hMem);
    v14 = ntohl(v13);
    if ( v14 != -1 )
    {
      v4[2] = v12;
      v4[5] = v12;
      v16 = v12 | ~v14;
      v4[4] = v14;
      v17 = (_QWORD)xmmword_1800D0740 == 0;
      v4[3] = v16;
      if ( !v17 )
      {
        LOWORD(v24) = 0;
        LODWORD(phkResult) = v14;
        FormatRRASErrorString(&v24, L"0x%x...0x%x/0x%x", v12, v16, phkResult);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v24);
      }
      LOBYTE(v15) = 1;
      *(GUID *)&v23[1] = GUID_NULL;
      RasStatComputeAcquiredAddressesCountForPool(&v23[1], v12, v16, v15);
      *a1 = v4;
      v4 = 0;
      *a2 = v16 - v12 + 1;
      goto LABEL_23;
    }
    goto LABEL_16;
  }
LABEL_13:
  if ( (_QWORD)xmmword_1800D0740 )
  {
    v6 = v10;
    v7 = L"RegQueryValueWithAllocA(%hs) failed: %d";
LABEL_6:
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, v7, v6, ValueWithAllocA);
LABEL_7:
    v8 = xmmword_1800D0740;
    v9 = (const wchar_t *)&v24;
LABEL_8:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      v8,
      v9);
  }
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
  LocalFree(cp);
  LocalFree(hMem);
  return RasStatFreeAddrPool(v4);
}

```

## disassembly

```asm
0x18005ec00  mov     rax, rsp
0x18005ec03  mov     [rax+18h], rbx
0x18005ec07  mov     [rax+20h], rsi
0x18005ec0b  push    rbp
0x18005ec0c  push    rdi
0x18005ec0d  push    r12
0x18005ec0f  push    r14
0x18005ec11  push    r15
0x18005ec13  lea     rbp, [rax-7A8h]
0x18005ec1a  sub     rsp, 880h
0x18005ec21  movaps  xmmword ptr [rax-38h], xmm6
0x18005ec25  mov     rax, cs:__security_cookie
0x18005ec2c  xor     rax, rsp
0x18005ec2f  mov     [rbp+7A0h+var_40], rax
0x18005ec36  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18005ec3d  xor     r12d, r12d
0x18005ec40  mov     r15, rdx
0x18005ec43  mov     r14, rcx
0x18005ec46  mov     [rsp+8A0h+hKey], r12
0x18005ec4b  xor     edx, edx; Val
0x18005ec4d  mov     [rsp+8A0h+cp], r12
0x18005ec52  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18005ec57  mov     [rsp+8A0h+hMem], r12
0x18005ec5c  mov     r8d, 7FCh; Size
0x18005ec62  mov     [rsp+8A0h+var_840], r12d
0x18005ec67  mov     edi, r12d
0x18005ec6a  call    memset_0
0x18005ec6f  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005ec76  test    rdx, rdx
0x18005ec79  jz      short loc_18005EC95
0x18005ec7b  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005ec82  lea     r8, aRasstatcreatep; "rasStatCreatePoolListFromOldValues"
0x18005ec89  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005ec90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ec95  lea     rax, [rsp+8A0h+hKey]
0x18005ec9a  mov     r9d, 20019h; samDesired
0x18005eca0  xor     r8d, r8d; ulOptions
0x18005eca3  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18005eca8  lea     rdx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x18005ecaf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ecb6  call    cs:__imp_RegOpenKeyExA
0x18005ecbd  nop     dword ptr [rax+rax+00h]
0x18005ecc2  test    eax, eax
0x18005ecc4  jz      short loc_18005ED18
0x18005ecc6  cmp     qword ptr cs:xmmword_1800D0740, r12
0x18005eccd  jz      loc_18005EEAA
0x18005ecd3  lea     r8, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x18005ecda  lea     rdx, aCouldnTOpenKey; "Couldn't open key %hs: %d"
0x18005ece1  mov     r9d, eax
0x18005ece4  mov     word ptr [rsp+8A0h+var_840], r12w
0x18005ecea  lea     rcx, [rsp+8A0h+var_840]
0x18005ecef  call    FormatRRASErrorString
0x18005ecf4  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005ecfb  lea     r8, [rsp+8A0h+var_840]
0x18005ed00  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005ed07  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005ed0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed13  jmp     loc_18005EEAA
0x18005ed18  mov     edx, 18h; uBytes
0x18005ed1d  lea     ecx, [rdx+28h]; uFlags
0x18005ed20  call    cs:__imp_LocalAlloc
0x18005ed27  nop     dword ptr [rax+rax+00h]
0x18005ed2c  mov     rdi, rax
0x18005ed2f  test    rax, rax
0x18005ed32  jnz     short loc_18005ED4D
0x18005ed34  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005ed3b  test    rdx, rdx
0x18005ed3e  jz      loc_18005EEAA
0x18005ed44  lea     r8, aOutOfMemory; "Out of memory"
0x18005ed4b  jmp     short loc_18005ED00
0x18005ed4d  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18005ed52  lea     rbx, aIpaddress; "IpAddress"
0x18005ed59  mov     rdx, rbx; lpValueName
0x18005ed5c  lea     r9, [rsp+8A0h+cp]
0x18005ed61  mov     r8d, 1
0x18005ed67  call    RegQueryValueWithAllocA
0x18005ed6c  test    eax, eax
0x18005ed6e  jz      short loc_18005ED8C
0x18005ed70  cmp     qword ptr cs:xmmword_1800D0740, r12
0x18005ed77  jz      loc_18005EEAA
0x18005ed7d  mov     r8, rbx
0x18005ed80  lea     rdx, aRegqueryvaluew_0; "RegQueryValueWithAllocA(%hs) failed: %d"
0x18005ed87  jmp     loc_18005ECE1
0x18005ed8c  mov     rcx, [rsp+8A0h+cp]; cp
0x18005ed91  call    cs:__imp_inet_addr
0x18005ed98  nop     dword ptr [rax+rax+00h]
0x18005ed9d  mov     ecx, eax; netlong
0x18005ed9f  call    cs:__imp_ntohl
0x18005eda6  nop     dword ptr [rax+rax+00h]
0x18005edab  mov     esi, eax
0x18005edad  cmp     eax, 0FFFFFFFFh
0x18005edb0  jnz     short loc_18005EDDE
0x18005edb2  cmp     qword ptr cs:xmmword_1800D0740, r12
0x18005edb9  jz      loc_18005EEAA
0x18005edbf  mov     r8, rbx
0x18005edc2  mov     word ptr [rsp+8A0h+var_840], r12w
0x18005edc8  lea     rdx, aBadValueInHs; "Bad value in %hs"
0x18005edcf  lea     rcx, [rsp+8A0h+var_840]
0x18005edd4  call    FormatRRASErrorString
0x18005edd9  jmp     loc_18005ECF4
0x18005edde  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18005ede3  lea     rbx, aIpmask; "IpMask"
0x18005edea  mov     rdx, rbx; lpValueName
0x18005eded  lea     r9, [rsp+8A0h+hMem]
0x18005edf2  mov     r8d, 1
0x18005edf8  call    RegQueryValueWithAllocA
0x18005edfd  test    eax, eax
0x18005edff  jnz     loc_18005ED70
0x18005ee05  mov     rcx, [rsp+8A0h+hMem]; cp
0x18005ee0a  call    cs:__imp_inet_addr
0x18005ee11  nop     dword ptr [rax+rax+00h]
0x18005ee16  mov     ecx, eax; netlong
0x18005ee18  call    cs:__imp_ntohl
0x18005ee1f  nop     dword ptr [rax+rax+00h]
0x18005ee24  cmp     eax, 0FFFFFFFFh
0x18005ee27  jz      short loc_18005EDB2
0x18005ee29  mov     ebx, eax
0x18005ee2b  mov     [rdi+8], esi
0x18005ee2e  not     ebx
0x18005ee30  mov     [rdi+14h], esi
0x18005ee33  or      ebx, esi
0x18005ee35  mov     [rdi+10h], eax
0x18005ee38  cmp     qword ptr cs:xmmword_1800D0740, r12
0x18005ee3f  mov     [rdi+0Ch], ebx
0x18005ee42  jz      short loc_18005EE84
0x18005ee44  mov     r9d, ebx
0x18005ee47  mov     word ptr [rsp+8A0h+var_840], r12w
0x18005ee4d  mov     r8d, esi
0x18005ee50  mov     dword ptr [rsp+8A0h+phkResult], eax
0x18005ee54  lea     rdx, a0xX0xX0xX; "0x%x...0x%x/0x%x"
0x18005ee5b  lea     rcx, [rsp+8A0h+var_840]
0x18005ee60  call    FormatRRASErrorString
0x18005ee65  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005ee6c  lea     r8, [rsp+8A0h+var_840]
0x18005ee71  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005ee78  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005ee7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee84  mov     r9b, 1
0x18005ee87  movdqa  xmmword ptr [rsp+8A0h+var_858+8], xmm6
0x18005ee8d  mov     r8d, ebx
0x18005ee90  lea     rcx, [rsp+8A0h+var_858+8]
0x18005ee95  mov     edx, esi
0x18005ee97  call    RasStatComputeAcquiredAddressesCountForPool
0x18005ee9c  mov     [r14], rdi
0x18005ee9f  sub     ebx, esi
0x18005eea1  mov     rdi, r12
0x18005eea4  lea     eax, [rbx+1]
0x18005eea7  mov     [r15], rax
0x18005eeaa  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18005eeaf  test    rcx, rcx
0x18005eeb2  jz      short loc_18005EEC0
0x18005eeb4  call    cs:__imp_RegCloseKey
0x18005eebb  nop     dword ptr [rax+rax+00h]
0x18005eec0  mov     rcx, [rsp+8A0h+cp]; hMem
0x18005eec5  call    cs:__imp_LocalFree
0x18005eecc  nop     dword ptr [rax+rax+00h]
0x18005eed1  mov     rcx, [rsp+8A0h+hMem]; hMem
0x18005eed6  call    cs:__imp_LocalFree
0x18005eedd  nop     dword ptr [rax+rax+00h]
0x18005eee2  mov     rcx, rdi; hMem
0x18005eee5  call    RasStatFreeAddrPool
0x18005eeea  mov     rcx, [rbp+7A0h+var_40]
0x18005eef1  xor     rcx, rsp; StackCookie
0x18005eef4  call    __security_check_cookie
0x18005eef9  lea     r11, [rsp+8A0h+var_20]
0x18005ef01  mov     rbx, [r11+40h]
0x18005ef05  mov     rsi, [r11+48h]
0x18005ef09  movaps  xmm6, xmmword ptr [r11-10h]
0x18005ef0e  mov     rsp, r11
0x18005ef11  pop     r15
0x18005ef13  pop     r14
0x18005ef15  pop     r12
0x18005ef17  pop     rdi
0x18005ef18  pop     rbp
0x18005ef19  retn
```

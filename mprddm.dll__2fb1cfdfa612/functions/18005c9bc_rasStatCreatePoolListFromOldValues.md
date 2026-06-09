# rasStatCreatePoolListFromOldValues

- ea: `0x18005c9bc`
- end: `0x18005ccd8`
- name: `rasStatCreatePoolListFromOldValues`
- size: `796`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005bd78`

## callees

- `0x18005bc4c`
- `0x18005c9bc`
- `0x180067e84`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005cc8f`
- `KERNEL32!LocalFree` at `0x18005cca2`
- `KERNEL32!LocalFree` at `0x18005cc8f`
- `KERNEL32!LocalFree` at `0x18005cca2`
- `KERNEL32!LocalAlloc` at `0x18005cad8`
- `KERNEL32!LocalAlloc` at `0x18005cad8`
- `ADVAPI32!RegCloseKey` at `0x18005cc84`
- `ADVAPI32!RegCloseKey` at `0x18005cc84`
- `ADVAPI32!RegOpenKeyExA` at `0x18005ca74`
- `ADVAPI32!RegOpenKeyExA` at `0x18005ca74`
- `WS2_32!__imp_inet_addr` at `0x18005cb77`
- `WS2_32!__imp_inet_addr` at `0x18005cbe3`
- `WS2_32!__imp_inet_addr` at `0x18005cb77`
- `WS2_32!__imp_inet_addr` at `0x18005cbe3`
- `WS2_32!__imp_ntohl` at `0x18005cb7f`
- `WS2_32!__imp_ntohl` at `0x18005cbeb`
- `WS2_32!__imp_ntohl` at `0x18005cb7f`
- `WS2_32!__imp_ntohl` at `0x18005cbeb`

## string_xrefs

- `0x18005ca66`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x18005ca8a`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x18005ca40`: `rasStatCreatePoolListFromOldValues`
- `0x18005ca96`: `Couldn't open key %hs: %d`

## pseudocode

```c
HLOCAL __fastcall rasStatCreatePoolListFromOldValues(char **a1, _QWORD *a2)
{
  unsigned int v4; // eax
  char *v5; // rbx
  __int64 v6; // rdx
  const wchar_t *v7; // r8
  const CHAR *v8; // rdi
  unsigned int ValueWithAllocA; // eax
  u_long v10; // eax
  u_long v11; // esi
  u_long v12; // eax
  u_long v13; // eax
  __int64 v14; // r9
  unsigned int v15; // edi
  bool v16; // zf
  char *v17; // rcx
  HLOCAL result; // rax
  PHKEY phkResult; // [rsp+28h] [rbp-E0h]
  HKEY hKey; // [rsp+38h] [rbp-D0h] BYREF
  char *cp; // [rsp+40h] [rbp-C8h]
  char *v22; // [rsp+48h] [rbp-C0h]
  _QWORD v23[3]; // [rsp+50h] [rbp-B8h] BYREF
  int v24; // [rsp+68h] [rbp-A0h] BYREF
  char v25[2044]; // [rsp+6Ch] [rbp-9Ch] BYREF

  hKey = 0;
  cp = 0;
  v22 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"rasStatCreatePoolListFromOldValues");
  v4 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
         0,
         0x20019u,
         &hKey);
  if ( v4 )
  {
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"Couldn't open key %hs: %d",
        "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
        v4);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v24);
    }
    v5 = 0;
    goto LABEL_23;
  }
  v5 = (char *)LocalAlloc(0x40u, 0x18u);
  if ( !v5 )
  {
    v6 = *((_QWORD *)&xmmword_1800C9740 + 1);
    if ( !*((_QWORD *)&xmmword_1800C9740 + 1) )
      goto LABEL_23;
    v7 = L"Out of memory";
    goto LABEL_10;
  }
  v8 = "IpAddress";
  ValueWithAllocA = RegQueryValueWithAllocA(hKey, "IpAddress");
  if ( ValueWithAllocA )
    goto LABEL_12;
  v10 = inet_addr(cp);
  v11 = ntohl(v10);
  if ( v11 == -1 )
    goto LABEL_16;
  v8 = "IpMask";
  ValueWithAllocA = RegQueryValueWithAllocA(hKey, "IpMask");
  if ( ValueWithAllocA )
  {
LABEL_12:
    if ( !(_QWORD)xmmword_1800C9740 )
      goto LABEL_23;
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"RegQueryValueWithAllocA(%hs) failed: %d", v8, ValueWithAllocA);
LABEL_14:
    v6 = xmmword_1800C9740;
    v7 = (const wchar_t *)&v24;
LABEL_10:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      v6,
      v7);
    goto LABEL_23;
  }
  v12 = inet_addr(v22);
  v13 = ntohl(v12);
  if ( v13 == -1 )
  {
LABEL_16:
    if ( !(_QWORD)xmmword_1800C9740 )
      goto LABEL_23;
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"Bad value in %hs", v8);
    goto LABEL_14;
  }
  *((_DWORD *)v5 + 2) = v11;
  *((_DWORD *)v5 + 5) = v11;
  v15 = v11 | ~v13;
  *((_DWORD *)v5 + 4) = v13;
  v16 = (_QWORD)xmmword_1800C9740 == 0;
  *((_DWORD *)v5 + 3) = v15;
  if ( !v16 )
  {
    LODWORD(phkResult) = v13;
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"0x%x...0x%x/0x%x", v11, v15, phkResult);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v24);
  }
  LOBYTE(v14) = 1;
  *(GUID *)&v23[1] = GUID_NULL;
  RasStatComputeAcquiredAddressesCountForPool(&v23[1], v11, v15, v14);
  *a1 = v5;
  v5 = 0;
  *a2 = v15 - v11 + 1;
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
  LocalFree(cp);
  v17 = v22;
  while ( 1 )
  {
    result = LocalFree(v17);
    if ( !v5 )
      break;
    v17 = v5;
    v5 = *(char **)v5;
  }
  return result;
}

```

## disassembly

```asm
0x18005c9bc  mov     rax, rsp
0x18005c9bf  mov     [rax+18h], rbx
0x18005c9c3  push    rbp
0x18005c9c4  push    rsi
0x18005c9c5  push    rdi
0x18005c9c6  push    r14
0x18005c9c8  push    r15
0x18005c9ca  lea     rbp, [rax-7A8h]
0x18005c9d1  sub     rsp, 880h
0x18005c9d8  movaps  xmmword ptr [rax-38h], xmm6
0x18005c9dc  mov     rax, cs:__security_cookie
0x18005c9e3  xor     rax, rsp
0x18005c9e6  mov     [rbp+7A0h+var_40], rax
0x18005c9ed  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18005c9f4  mov     r15, rdx
0x18005c9f7  mov     [rsp+8A0h+hKey], 0
0x18005ca00  mov     r14, rcx
0x18005ca03  mov     [rsp+8A0h+cp], 0
0x18005ca0c  xor     eax, eax
0x18005ca0e  mov     [rsp+8A0h+var_860], 0
0x18005ca17  xor     edx, edx; Val
0x18005ca19  mov     [rsp+8A0h+var_840], eax
0x18005ca1d  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18005ca22  mov     r8d, 7FCh; Size
0x18005ca28  call    memset_0
0x18005ca2d  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005ca34  test    rdx, rdx
0x18005ca37  jz      short loc_18005CA53
0x18005ca39  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005ca40  lea     r8, aRasstatcreatep; "rasStatCreatePoolListFromOldValues"
0x18005ca47  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005ca4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca53  lea     rax, [rsp+8A0h+hKey]
0x18005ca58  mov     r9d, 20019h; samDesired
0x18005ca5e  xor     r8d, r8d; ulOptions
0x18005ca61  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18005ca66  lea     rdx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x18005ca6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ca74  call    cs:__imp_RegOpenKeyExA
0x18005ca7a  test    eax, eax
0x18005ca7c  jz      short loc_18005CAD0
0x18005ca7e  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005ca86  jz      short loc_18005CAC9
0x18005ca88  xor     ecx, ecx
0x18005ca8a  lea     r8, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x18005ca91  mov     word ptr [rsp+8A0h+var_840], cx
0x18005ca96  lea     rdx, aCouldnTOpenKey; "Couldn't open key %hs: %d"
0x18005ca9d  lea     rcx, [rsp+8A0h+var_840]
0x18005caa2  mov     r9d, eax
0x18005caa5  call    FormatRRASErrorString
0x18005caaa  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005cab1  lea     r8, [rsp+8A0h+var_840]
0x18005cab6  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005cabd  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005cac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cac9  xor     ebx, ebx
0x18005cacb  jmp     loc_18005CC7A
0x18005cad0  mov     edx, 18h; uBytes
0x18005cad5  lea     ecx, [rdx+28h]; uFlags
0x18005cad8  call    cs:__imp_LocalAlloc
0x18005cade  mov     rbx, rax
0x18005cae1  test    rax, rax
0x18005cae4  jnz     short loc_18005CB15
0x18005cae6  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005caed  test    rdx, rdx
0x18005caf0  jz      loc_18005CC7A
0x18005caf6  lea     r8, aOutOfMemory; "Out of memory"
0x18005cafd  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005cb04  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005cb0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb10  jmp     loc_18005CC7A
0x18005cb15  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18005cb1a  lea     rdi, aIpaddress; "IpAddress"
0x18005cb21  mov     rdx, rdi; lpValueName
0x18005cb24  lea     r9, [rsp+8A0h+cp]
0x18005cb29  mov     r8d, 1
0x18005cb2f  call    RegQueryValueWithAllocA
0x18005cb34  test    eax, eax
0x18005cb36  jz      short loc_18005CB72
0x18005cb38  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005cb40  jz      loc_18005CC7A
0x18005cb46  xor     ecx, ecx
0x18005cb48  lea     rdx, aRegqueryvaluew_0; "RegQueryValueWithAllocA(%hs) failed: %d"
0x18005cb4f  mov     word ptr [rsp+8A0h+var_840], cx
0x18005cb54  mov     r9d, eax
0x18005cb57  lea     rcx, [rsp+8A0h+var_840]
0x18005cb5c  mov     r8, rdi
0x18005cb5f  call    FormatRRASErrorString
0x18005cb64  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005cb6b  lea     r8, [rsp+8A0h+var_840]
0x18005cb70  jmp     short loc_18005CAFD
0x18005cb72  mov     rcx, [rsp+8A0h+cp]; cp
0x18005cb77  call    cs:__imp_inet_addr
0x18005cb7d  mov     ecx, eax; netlong
0x18005cb7f  call    cs:__imp_ntohl
0x18005cb85  mov     esi, eax
0x18005cb87  cmp     eax, 0FFFFFFFFh
0x18005cb8a  jnz     short loc_18005CBB7
0x18005cb8c  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005cb94  jz      loc_18005CC7A
0x18005cb9a  xor     eax, eax
0x18005cb9c  lea     rdx, aBadValueInHs; "Bad value in %hs"
0x18005cba3  mov     r8, rdi
0x18005cba6  mov     word ptr [rsp+8A0h+var_840], ax
0x18005cbab  lea     rcx, [rsp+8A0h+var_840]
0x18005cbb0  call    FormatRRASErrorString
0x18005cbb5  jmp     short loc_18005CB64
0x18005cbb7  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18005cbbc  lea     rdi, aIpmask; "IpMask"
0x18005cbc3  mov     rdx, rdi; lpValueName
0x18005cbc6  lea     r9, [rsp+8A0h+var_860]
0x18005cbcb  mov     r8d, 1
0x18005cbd1  call    RegQueryValueWithAllocA
0x18005cbd6  test    eax, eax
0x18005cbd8  jnz     loc_18005CB38
0x18005cbde  mov     rcx, [rsp+8A0h+var_860]; cp
0x18005cbe3  call    cs:__imp_inet_addr
0x18005cbe9  mov     ecx, eax; netlong
0x18005cbeb  call    cs:__imp_ntohl
0x18005cbf1  mov     ecx, eax
0x18005cbf3  cmp     eax, 0FFFFFFFFh
0x18005cbf6  jz      short loc_18005CB8C
0x18005cbf8  mov     edi, eax
0x18005cbfa  mov     [rbx+8], esi
0x18005cbfd  not     edi
0x18005cbff  mov     [rbx+14h], esi
0x18005cc02  or      edi, esi
0x18005cc04  mov     [rbx+10h], eax
0x18005cc07  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005cc0f  mov     [rbx+0Ch], edi
0x18005cc12  jz      short loc_18005CC55
0x18005cc14  xor     eax, eax
0x18005cc16  mov     dword ptr [rsp+8A0h+phkResult], ecx
0x18005cc1a  lea     rcx, [rsp+8A0h+var_840]
0x18005cc1f  mov     word ptr [rsp+8A0h+var_840], ax
0x18005cc24  mov     r9d, edi
0x18005cc27  lea     rdx, a0xX0xX0xX; "0x%x...0x%x/0x%x"
0x18005cc2e  mov     r8d, esi
0x18005cc31  call    FormatRRASErrorString
0x18005cc36  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005cc3d  lea     r8, [rsp+8A0h+var_840]
0x18005cc42  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005cc49  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005cc50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc55  mov     r9b, 1
0x18005cc58  movdqa  xmmword ptr [rsp+8A0h+var_858+8], xmm6
0x18005cc5e  mov     r8d, edi
0x18005cc61  lea     rcx, [rsp+8A0h+var_858+8]
0x18005cc66  mov     edx, esi
0x18005cc68  call    RasStatComputeAcquiredAddressesCountForPool
0x18005cc6d  mov     [r14], rbx
0x18005cc70  xor     ebx, ebx
0x18005cc72  sub     edi, esi
0x18005cc74  lea     eax, [rdi+1]
0x18005cc77  mov     [r15], rax
0x18005cc7a  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18005cc7f  test    rcx, rcx
0x18005cc82  jz      short loc_18005CC8A
0x18005cc84  call    cs:__imp_RegCloseKey
0x18005cc8a  mov     rcx, [rsp+8A0h+cp]; hMem
0x18005cc8f  call    cs:__imp_LocalFree
0x18005cc95  mov     rcx, [rsp+8A0h+var_860]
0x18005cc9a  jmp     short loc_18005CCA2
0x18005cc9c  mov     rcx, rbx; hMem
0x18005cc9f  mov     rbx, [rbx]
0x18005cca2  call    cs:__imp_LocalFree
0x18005cca8  test    rbx, rbx
0x18005ccab  jnz     short loc_18005CC9C
0x18005ccad  mov     rcx, [rbp+7A0h+var_40]
0x18005ccb4  xor     rcx, rsp; StackCookie
0x18005ccb7  call    __security_check_cookie
0x18005ccbc  lea     r11, [rsp+8A0h+var_20]
0x18005ccc4  mov     rbx, [r11+40h]
0x18005ccc8  movaps  xmm6, xmmword ptr [r11-10h]
0x18005cccd  mov     rsp, r11
0x18005ccd0  pop     r15
0x18005ccd2  pop     r14
0x18005ccd4  pop     rdi
0x18005ccd5  pop     rsi
0x18005ccd6  pop     rbp
0x18005ccd7  retn
```

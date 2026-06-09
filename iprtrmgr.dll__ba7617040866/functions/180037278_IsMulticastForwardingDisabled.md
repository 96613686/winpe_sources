# IsMulticastForwardingDisabled

- ea: `0x180037278`
- end: `0x1800373cb`
- name: `IsMulticastForwardingDisabled`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a9b0`

## callees

- `0x18000ac60`
- `0x180037278`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180037380`
- `ADVAPI32!RegCloseKey` at `0x180037380`
- `ADVAPI32!RegOpenKeyExW` at `0x18003732b`
- `ADVAPI32!RegOpenKeyExW` at `0x18003732b`
- `ADVAPI32!RegQueryValueExW` at `0x180037367`
- `ADVAPI32!RegQueryValueExW` at `0x180037367`

## string_xrefs

- `0x18003731b`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`

## pseudocode

```c
_BOOL8 IsMulticastForwardingDisabled()
{
  BOOL v0; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v5; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v6[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKey = 0;
  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v5) = 0;
    FormatRRASErrorString(&v5, L"Entered: %ws", L"IsMulticastForwardingDisabled");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v5);
  }
  v0 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
          0,
          0x2001Fu,
          &hKey) )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DisableMulticastForwarding", 0, 0, Data, &cbData) )
      v0 = *(_DWORD *)Data != 0;
    RegCloseKey(hKey);
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: IsMulticastForwardingDisabled");
  return v0;
}

```

## disassembly

```asm
0x180037278  mov     [rsp-8+arg_0], rbx
0x18003727d  push    rbp
0x18003727e  lea     rbp, [rsp-750h]
0x180037286  sub     rsp, 850h
0x18003728d  mov     rax, cs:__security_cookie
0x180037294  xor     rax, rsp
0x180037297  mov     [rbp+750h+var_10], rax
0x18003729e  xor     eax, eax
0x1800372a0  mov     [rsp+850h+hKey], 0
0x1800372a9  xor     edx, edx; Val
0x1800372ab  mov     [rsp+850h+var_810], eax
0x1800372af  mov     r8d, 7FCh; Size
0x1800372b5  lea     rcx, [rsp+850h+var_80C]; void *
0x1800372ba  call    memset_0
0x1800372bf  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800372c6  jge     short loc_180037308
0x1800372c8  xor     eax, eax
0x1800372ca  lea     r8, aIsmulticastfor; "IsMulticastForwardingDisabled"
0x1800372d1  lea     rdx, aEnteredWs; "Entered: %ws"
0x1800372d8  mov     word ptr [rsp+850h+var_810], ax
0x1800372dd  lea     rcx, [rsp+850h+var_810]
0x1800372e2  call    FormatRRASErrorString
0x1800372e7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800372ee  jge     short loc_180037308
0x1800372f0  lea     r8, [rsp+850h+var_810]
0x1800372f5  lea     rdx, RasRtrmgrTraceInfo
0x1800372fc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180037303  call    McTemplateU0z_EventWriteTransfer
0x180037308  lea     rax, [rsp+850h+hKey]
0x18003730d  mov     r9d, 2001Fh; samDesired
0x180037313  xor     r8d, r8d; ulOptions
0x180037316  mov     [rsp+850h+phkResult], rax; phkResult
0x18003731b  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\Re"...
0x180037322  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037329  xor     ebx, ebx
0x18003732b  call    cs:__imp_RegOpenKeyExW
0x180037331  test    eax, eax
0x180037333  jnz     short loc_180037386
0x180037335  mov     rcx, [rsp+850h+hKey]; hKey
0x18003733a  lea     rax, [rsp+850h+cbData]
0x18003733f  mov     [rsp+850h+lpcbData], rax; lpcbData
0x180037344  lea     rdx, aDisablemultica; "DisableMulticastForwarding"
0x18003734b  lea     rax, [rsp+850h+Data]
0x180037350  mov     dword ptr [rsp+850h+Data], ebx
0x180037354  xor     r9d, r9d; lpType
0x180037357  mov     [rsp+850h+phkResult], rax; lpData
0x18003735c  xor     r8d, r8d; lpReserved
0x18003735f  mov     [rsp+850h+cbData], 4
0x180037367  call    cs:__imp_RegQueryValueExW
0x18003736d  test    eax, eax
0x18003736f  jnz     short loc_18003737B
0x180037371  cmp     dword ptr [rsp+850h+Data], ebx
0x180037375  lea     eax, [rbx+1]
0x180037378  cmova   ebx, eax
0x18003737b  mov     rcx, [rsp+850h+hKey]; hKey
0x180037380  call    cs:__imp_RegCloseKey
0x180037386  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18003738d  jz      short loc_1800373A9
0x18003738f  lea     r8, aLeavingIsmulti; "Leaving: IsMulticastForwardingDisabled"
0x180037396  lea     rdx, RasRtrmgrTraceInfo
0x18003739d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800373a4  call    McTemplateU0z_EventWriteTransfer
0x1800373a9  mov     eax, ebx
0x1800373ab  mov     rcx, [rbp+750h+var_10]
0x1800373b2  xor     rcx, rsp; StackCookie
0x1800373b5  call    __security_check_cookie
0x1800373ba  mov     rbx, [rsp+850h+arg_0]
0x1800373c2  add     rsp, 850h
0x1800373c9  pop     rbp
0x1800373ca  retn
```

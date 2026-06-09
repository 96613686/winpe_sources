# RestoreNetbtBcastForwardingMode

- ea: `0x180021220`
- end: `0x1800213a7`
- name: `RestoreNetbtBcastForwardingMode`
- size: `391`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c054`
- `0x180050b74`

## callees

- `0x18000ac60`
- `0x18001f994`
- `0x180021220`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002137f`
- `ADVAPI32!RegCloseKey` at `0x18002137f`
- `ADVAPI32!RegOpenKeyExW` at `0x1800212ab`
- `ADVAPI32!RegOpenKeyExW` at `0x1800212ab`
- `ADVAPI32!RegSetValueExW` at `0x180021328`
- `ADVAPI32!RegSetValueExW` at `0x180021328`

## string_xrefs

- `0x18002129d`: `System\CurrentControlSet\Services\Netbt\Parameters`
- `0x1800212c6`: `EnableNetbtBcastForwarding : error %d opening Netbt\Parameters key\n`

## pseudocode

```c
__int64 RestoreNetbtBcastForwardingMode()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v4; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v5[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKey = 0;
  v4 = 0;
  memset_0(v5, 0, sizeof(v5));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"RestoreNetbtBcastForwardingMode");
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Netbt\\Parameters", 0, 0x2001Fu, &hKey);
  v1 = v0;
  if ( v0 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_12;
    LOWORD(v4) = 0;
    FormatRRASErrorString(&v4, L"EnableNetbtBcastForwarding : error %d opening Netbt\\Parameters key\n", v0);
  }
  else
  {
    v1 = RegSetValueExW(hKey, L"EnableProxy", 0, 4u, &g_dwOldNetbtProxyMode, 4u);
    if ( !v1 )
    {
      v1 = ForceNetbtRegistryRead();
      goto LABEL_12;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_12;
    LOWORD(v4) = 0;
    FormatRRASErrorString(&v4, L"EnableNetbtBcastForwarding : error %d setting EnableProxy value\n", v1);
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v4);
LABEL_12:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: RestoreNetbtBcastForwardingMode");
  RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180021220  mov     [rsp-8+arg_0], rbx
0x180021225  push    rbp
0x180021226  lea     rbp, [rsp-750h]
0x18002122e  sub     rsp, 850h
0x180021235  mov     rax, cs:__security_cookie
0x18002123c  xor     rax, rsp
0x18002123f  mov     [rbp+750h+var_10], rax
0x180021246  xor     eax, eax
0x180021248  mov     [rsp+850h+hKey], 0
0x180021251  xor     edx, edx; Val
0x180021253  mov     [rsp+850h+var_810], eax
0x180021257  mov     r8d, 7FCh; Size
0x18002125d  lea     rcx, [rsp+850h+var_80C]; void *
0x180021262  call    memset_0
0x180021267  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002126e  jz      short loc_18002128A
0x180021270  lea     r8, aRestorenetbtbc; "RestoreNetbtBcastForwardingMode"
0x180021277  lea     rdx, RasRtrmgrTraceInfo
0x18002127e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180021285  call    McTemplateU0z_EventWriteTransfer
0x18002128a  lea     rax, [rsp+850h+hKey]
0x18002128f  mov     r9d, 2001Fh; samDesired
0x180021295  xor     r8d, r8d; ulOptions
0x180021298  mov     [rsp+850h+phkResult], rax; phkResult
0x18002129d  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ne"...
0x1800212a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800212ab  call    cs:__imp_RegOpenKeyExW
0x1800212b1  mov     ebx, eax
0x1800212b3  test    eax, eax
0x1800212b5  jz      short loc_180021302
0x1800212b7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800212be  jge     loc_180021357
0x1800212c4  xor     ecx, ecx
0x1800212c6  lea     rdx, aEnablenetbtbca_4; "EnableNetbtBcastForwarding : error %d o"...
0x1800212cd  mov     word ptr [rsp+850h+var_810], cx
0x1800212d2  mov     r8d, eax
0x1800212d5  lea     rcx, [rsp+850h+var_810]
0x1800212da  call    FormatRRASErrorString
0x1800212df  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800212e6  jge     short loc_180021357
0x1800212e8  lea     r8, [rsp+850h+var_810]
0x1800212ed  lea     rdx, RasRtrmgrTraceInfo
0x1800212f4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800212fb  call    McTemplateU0z_EventWriteTransfer
0x180021300  jmp     short loc_180021357
0x180021302  mov     rcx, [rsp+850h+hKey]; hKey
0x180021307  lea     rax, g_dwOldNetbtProxyMode
0x18002130e  mov     r9d, 4; dwType
0x180021314  lea     rdx, aEnableproxy; "EnableProxy"
0x18002131b  mov     [rsp+850h+cbData], r9d; cbData
0x180021320  xor     r8d, r8d; Reserved
0x180021323  mov     [rsp+850h+phkResult], rax; lpData
0x180021328  call    cs:__imp_RegSetValueExW
0x18002132e  mov     ebx, eax
0x180021330  test    eax, eax
0x180021332  jz      short loc_180021350
0x180021334  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18002133b  jge     short loc_180021357
0x18002133d  xor     eax, eax
0x18002133f  lea     rdx, aEnablenetbtbca_3; "EnableNetbtBcastForwarding : error %d s"...
0x180021346  mov     word ptr [rsp+850h+var_810], ax
0x18002134b  mov     r8d, ebx
0x18002134e  jmp     short loc_1800212D5
0x180021350  call    ForceNetbtRegistryRead
0x180021355  mov     ebx, eax
0x180021357  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002135e  jz      short loc_18002137A
0x180021360  lea     r8, aLeavingRestore_0; "Leaving: RestoreNetbtBcastForwardingMod"...
0x180021367  lea     rdx, RasRtrmgrTraceInfo
0x18002136e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180021375  call    McTemplateU0z_EventWriteTransfer
0x18002137a  mov     rcx, [rsp+850h+hKey]; hKey
0x18002137f  call    cs:__imp_RegCloseKey
0x180021385  mov     eax, ebx
0x180021387  mov     rcx, [rbp+750h+var_10]
0x18002138e  xor     rcx, rsp; StackCookie
0x180021391  call    __security_check_cookie
0x180021396  mov     rbx, [rsp+850h+arg_0]
0x18002139e  add     rsp, 850h
0x1800213a5  pop     rbp
0x1800213a6  retn
```

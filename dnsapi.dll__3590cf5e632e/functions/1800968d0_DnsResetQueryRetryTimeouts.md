# DnsResetQueryRetryTimeouts

- ea: `0x1800968d0`
- end: `0x18009697a`
- name: `DnsResetQueryRetryTimeouts`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180079794`
- `0x180083954`
- `0x18008b5f0`
- `0x1800968d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096958`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096958`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180096938`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180096938`

## pseudocode

```c
__int64 __fastcall DnsResetQueryRetryTimeouts(__int128 *a1)
{
  __int128 v1; // xmm0
  LSTATUS QueryRetryTimeoutsRegistryHandle; // eax
  unsigned int v4; // ebx
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  v1 = *a1;
  hKey = 0;
  v5 = v1;
  if ( g_fVelocityDisableInternalExports )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
    return 120;
  }
  else
  {
    QueryRetryTimeoutsRegistryHandle = DnsGetQueryRetryTimeoutsRegistryHandle((__int64)&v5, 0, &hKey);
    v4 = QueryRetryTimeoutsRegistryHandle;
    if ( QueryRetryTimeoutsRegistryHandle == 2 )
    {
      return 0;
    }
    else
    {
      if ( !QueryRetryTimeoutsRegistryHandle )
      {
        v4 = RegDeleteValueW(hKey, L"DNSQueryTimeoutsMB");
        if ( v4 == 2 )
          v4 = 0;
      }
      if ( hKey )
        RegCloseKey(hKey);
      return v4;
    }
  }
}

```

## disassembly

```asm
0x1800968d0  push    rbx
0x1800968d2  sub     rsp, 40h
0x1800968d6  mov     rax, cs:__security_cookie
0x1800968dd  xor     rax, rsp
0x1800968e0  mov     [rsp+48h+var_10], rax
0x1800968e5  cmp     cs:g_fVelocityDisableInternalExports, 0
0x1800968ec  movups  xmm0, xmmword ptr [rcx]
0x1800968ef  mov     [rsp+48h+hKey], 0
0x1800968f8  movdqu  [rsp+48h+var_28], xmm0
0x1800968fe  jz      short loc_18009690C
0x180096900  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180096905  mov     eax, 78h ; 'x'
0x18009690a  jmp     short loc_180096966
0x18009690c  lea     r8, [rsp+48h+hKey]
0x180096911  xor     edx, edx
0x180096913  lea     rcx, [rsp+48h+var_28]
0x180096918  call    DnsGetQueryRetryTimeoutsRegistryHandle
0x18009691d  mov     ebx, eax
0x18009691f  cmp     eax, 2
0x180096922  jnz     short loc_180096928
0x180096924  xor     eax, eax
0x180096926  jmp     short loc_180096966
0x180096928  test    eax, eax
0x18009692a  jnz     short loc_18009694E
0x18009692c  mov     rcx, [rsp+48h+hKey]; hKey
0x180096931  lea     rdx, Value; "DNSQueryTimeoutsMB"
0x180096938  call    cs:__imp_RegDeleteValueW
0x18009693f  nop     dword ptr [rax+rax+00h]
0x180096944  mov     ebx, eax
0x180096946  xor     eax, eax
0x180096948  cmp     ebx, 2
0x18009694b  cmovz   ebx, eax
0x18009694e  mov     rcx, [rsp+48h+hKey]; hKey
0x180096953  test    rcx, rcx
0x180096956  jz      short loc_180096964
0x180096958  call    cs:__imp_RegCloseKey
0x18009695f  nop     dword ptr [rax+rax+00h]
0x180096964  mov     eax, ebx
0x180096966  mov     rcx, [rsp+48h+var_10]
0x18009696b  xor     rcx, rsp; StackCookie
0x18009696e  call    __security_check_cookie
0x180096973  add     rsp, 40h
0x180096977  pop     rbx
0x180096978  retn
```

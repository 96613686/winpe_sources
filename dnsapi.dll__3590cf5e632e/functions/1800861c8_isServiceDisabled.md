# isServiceDisabled

- ea: `0x1800861c8`
- end: `0x180086281`
- name: `isServiceDisabled`
- size: `185`
- prototype: `__int64 __fastcall(SC_HANDLE hService)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18006cf08`
- `0x18008a138`

## callees

- `0x180029d80`
- `0x18002b050`
- `0x1800861c8`
- `0x18008b5f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008620d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008620d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800861fd`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18008623f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800861fd`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18008623f`

## pseudocode

```c
_BOOL8 __fastcall isServiceDisabled(SC_HANDLE hService)
{
  BOOL v2; // ebx
  struct _QUERY_SERVICE_CONFIGW *v3; // rax
  struct _QUERY_SERVICE_CONFIGW *v4; // rdi
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-18h] BYREF

  pcbBytesNeeded = 0;
  v2 = 0;
  if ( !QueryServiceConfigW(hService, 0, 0, &pcbBytesNeeded) && GetLastError() == 122 )
  {
    v3 = (struct _QUERY_SERVICE_CONFIGW *)Dns_Allocate(pcbBytesNeeded);
    v4 = v3;
    if ( v3 )
    {
      if ( QueryServiceConfigW(hService, v3, pcbBytesNeeded, &pcbBytesNeeded) )
        v2 = v4->dwStartType == 4;
      DnsApiFree(v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800861c8  mov     [rsp+arg_8], rbx
0x1800861cd  mov     [rsp+arg_10], rsi
0x1800861d2  push    rdi
0x1800861d3  sub     rsp, 30h
0x1800861d7  mov     rax, cs:__security_cookie
0x1800861de  xor     rax, rsp
0x1800861e1  mov     [rsp+38h+var_10], rax
0x1800861e6  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x1800861eb  mov     [rsp+38h+pcbBytesNeeded], 0
0x1800861f3  xor     r8d, r8d; cbBufSize
0x1800861f6  xor     edx, edx; lpServiceConfig
0x1800861f8  mov     rsi, rcx
0x1800861fb  xor     ebx, ebx
0x1800861fd  call    cs:__imp_QueryServiceConfigW
0x180086204  nop     dword ptr [rax+rax+00h]
0x180086209  test    eax, eax
0x18008620b  jnz     short loc_180086261
0x18008620d  call    cs:__imp_GetLastError
0x180086214  nop     dword ptr [rax+rax+00h]
0x180086219  cmp     eax, 7Ah ; 'z'
0x18008621c  jnz     short loc_180086261
0x18008621e  mov     ecx, [rsp+38h+pcbBytesNeeded]
0x180086222  call    Dns_Allocate
0x180086227  mov     rdi, rax
0x18008622a  test    rax, rax
0x18008622d  jz      short loc_180086261
0x18008622f  mov     r8d, [rsp+38h+pcbBytesNeeded]; cbBufSize
0x180086234  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x180086239  mov     rdx, rax; lpServiceConfig
0x18008623c  mov     rcx, rsi; hService
0x18008623f  call    cs:__imp_QueryServiceConfigW
0x180086246  nop     dword ptr [rax+rax+00h]
0x18008624b  test    eax, eax
0x18008624d  jz      short loc_180086259
0x18008624f  cmp     dword ptr [rdi+4], 4
0x180086253  lea     eax, [rbx+1]
0x180086256  cmovz   ebx, eax
0x180086259  mov     rcx, rdi; lpMem
0x18008625c  call    DnsApiFree
0x180086261  mov     eax, ebx
0x180086263  mov     rcx, [rsp+38h+var_10]
0x180086268  xor     rcx, rsp; StackCookie
0x18008626b  call    __security_check_cookie
0x180086270  mov     rbx, [rsp+38h+arg_8]
0x180086275  mov     rsi, [rsp+38h+arg_10]
0x18008627a  add     rsp, 30h
0x18008627e  pop     rdi
0x18008627f  retn
```

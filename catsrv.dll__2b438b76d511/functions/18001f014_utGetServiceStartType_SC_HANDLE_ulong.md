# utGetServiceStartType(SC_HANDLE__ *,ulong *)

- ea: `0x18001f014`
- end: `0x18001f0ad`
- name: `?utGetServiceStartType@@YAHPEAUSC_HANDLE__@@PEAK@Z`
- size: `153`
- prototype: `__int64 __fastcall(SC_HANDLE hService, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f0b4`

## callees

- `0x18001f014`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f04c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f08f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f04c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f08f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f05b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f05b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001f042`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001f079`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001f042`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001f079`

## pseudocode

```c
__int64 __fastcall utGetServiceStartType(SC_HANDLE hService, unsigned int *a2)
{
  unsigned int v4; // ebp
  struct _QUERY_SERVICE_CONFIGW *v5; // rax
  struct _QUERY_SERVICE_CONFIGW *v6; // rbx
  DWORD pcbBytesNeeded; // [rsp+50h] [rbp+8h] BYREF

  *a2 = 4;
  pcbBytesNeeded = 0;
  if ( !hService )
    return 0;
  v4 = 0;
  if ( !QueryServiceConfigW(hService, 0, 0, &pcbBytesNeeded) && GetLastError() == 122 )
  {
    v5 = (struct _QUERY_SERVICE_CONFIGW *)CoTaskMemAlloc(pcbBytesNeeded);
    v6 = v5;
    if ( v5 )
    {
      if ( QueryServiceConfigW(hService, v5, pcbBytesNeeded, &pcbBytesNeeded) )
      {
        v4 = 1;
        *a2 = v6->dwStartType;
      }
      else
      {
        GetLastError();
      }
      CoTaskMemFree(v6);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001f014  push    rbx
0x18001f016  push    rbp
0x18001f017  push    rsi
0x18001f018  push    rdi
0x18001f019  sub     rsp, 28h
0x18001f01d  mov     dword ptr [rdx], 4
0x18001f023  mov     rsi, rdx
0x18001f026  mov     [rsp+48h+pcbBytesNeeded], 0
0x18001f02e  mov     rdi, rcx
0x18001f031  test    rcx, rcx
0x18001f034  jz      short loc_18001F0A2
0x18001f036  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x18001f03b  xor     r8d, r8d; cbBufSize
0x18001f03e  xor     edx, edx; lpServiceConfig
0x18001f040  xor     ebp, ebp
0x18001f042  call    cs:__imp_QueryServiceConfigW
0x18001f048  test    eax, eax
0x18001f04a  jnz     short loc_18001F09E
0x18001f04c  call    cs:__imp_GetLastError
0x18001f052  cmp     eax, 7Ah ; 'z'
0x18001f055  jnz     short loc_18001F09E
0x18001f057  mov     ecx, [rsp+48h+pcbBytesNeeded]; cb
0x18001f05b  call    cs:__imp_CoTaskMemAlloc
0x18001f061  mov     rbx, rax
0x18001f064  test    rax, rax
0x18001f067  jz      short loc_18001F09E
0x18001f069  mov     r8d, [rsp+48h+pcbBytesNeeded]; cbBufSize
0x18001f06e  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x18001f073  mov     rdx, rax; lpServiceConfig
0x18001f076  mov     rcx, rdi; hService
0x18001f079  call    cs:__imp_QueryServiceConfigW
0x18001f07f  test    eax, eax
0x18001f081  jz      short loc_18001F08F
0x18001f083  mov     ecx, [rbx+4]
0x18001f086  mov     ebp, 1
0x18001f08b  mov     [rsi], ecx
0x18001f08d  jmp     short loc_18001F095
0x18001f08f  call    cs:__imp_GetLastError
0x18001f095  mov     rcx, rbx; pv
0x18001f098  call    cs:__imp_CoTaskMemFree
0x18001f09e  mov     eax, ebp
0x18001f0a0  jmp     short loc_18001F0A4
0x18001f0a2  xor     eax, eax
0x18001f0a4  add     rsp, 28h
0x18001f0a8  pop     rdi
0x18001f0a9  pop     rsi
0x18001f0aa  pop     rbp
0x18001f0ab  pop     rbx
0x18001f0ac  retn
```

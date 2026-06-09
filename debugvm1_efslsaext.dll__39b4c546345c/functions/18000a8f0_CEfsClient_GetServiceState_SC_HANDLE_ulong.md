# CEfsClient::GetServiceState(SC_HANDLE__ *,ulong *)

- ea: `0x18000a8f0`
- end: `0x18000a96b`
- name: `?GetServiceState@CEfsClient@@KAKPEAUSC_HANDLE__@@PEAK@Z`
- size: `123`
- prototype: `unsigned int __fastcall(struct SC_HANDLE__ *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000a974`

## callees

- `0x18000a8f0`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a944`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000a93a`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000a93a`

## pseudocode

```c
__int64 __fastcall CEfsClient::GetServiceState(SC_HANDLE a1, unsigned int *a2)
{
  unsigned int v3; // ecx
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v7; // [rsp+48h] [rbp-30h]
  int v8; // [rsp+58h] [rbp-20h]

  pcbBytesNeeded = 0;
  v8 = 0;
  *(_OWORD *)Buffer = 0;
  v7 = 0;
  if ( QueryServiceStatusEx(a1, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
  {
    v3 = 0;
    *a2 = *(_DWORD *)&Buffer[4];
  }
  else
  {
    return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x18000a8f0  push    rbx
0x18000a8f2  sub     rsp, 70h
0x18000a8f6  mov     rax, cs:__security_cookie
0x18000a8fd  xor     rax, rsp
0x18000a900  mov     [rsp+78h+var_18], rax
0x18000a905  xor     eax, eax
0x18000a907  mov     [rsp+78h+var_48], 0
0x18000a90f  xorps   xmm0, xmm0
0x18000a912  mov     [rsp+78h+var_20], eax
0x18000a916  lea     rax, [rsp+78h+var_48]
0x18000a91b  mov     rbx, rdx
0x18000a91e  mov     r9d, 24h ; '$'; cbBufSize
0x18000a924  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18000a929  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x18000a92e  xor     edx, edx; InfoLevel
0x18000a930  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x18000a935  movups  [rsp+78h+var_30], xmm0
0x18000a93a  call    cs:__imp_QueryServiceStatusEx
0x18000a940  test    eax, eax
0x18000a942  jnz     short loc_18000A94E
0x18000a944  call    cs:__imp_GetLastError
0x18000a94a  mov     ecx, eax
0x18000a94c  jmp     short loc_18000A956
0x18000a94e  mov     eax, dword ptr [rsp+78h+Buffer+4]
0x18000a952  xor     ecx, ecx
0x18000a954  mov     [rbx], eax
0x18000a956  mov     eax, ecx
0x18000a958  mov     rcx, [rsp+78h+var_18]
0x18000a95d  xor     rcx, rsp; StackCookie
0x18000a960  call    __security_check_cookie
0x18000a965  add     rsp, 70h
0x18000a969  pop     rbx
0x18000a96a  retn
```

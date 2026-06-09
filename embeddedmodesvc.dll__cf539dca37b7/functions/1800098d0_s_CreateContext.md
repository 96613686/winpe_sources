# s_CreateContext

- ea: `0x1800098d0`
- end: `0x1800099af`
- name: `s_CreateContext`
- size: `223`
- prototype: `signed int __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180002b10`
- `0x1800035a0`
- `0x1800098d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000990f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000990f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000996f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000996f`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180009965`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180009965`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000994b`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000994b`

## pseudocode

```c
signed int __fastcall s_CreateContext(__int64 a1, _QWORD *a2)
{
  _DWORD *v3; // rbx
  signed int result; // eax
  RPC_STATUS v5; // eax
  DWORD pSessionId[4]; // [rsp+20h] [rbp-98h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v8[56]; // [rsp+38h] [rbp-80h] BYREF
  DWORD dwProcessId; // [rsp+70h] [rbp-48h]

  pSessionId[0] = 0;
  memset_0(RpcCallAttributes, 0, 0x70u);
  v3 = malloc(4u);
  if ( !v3 )
    return -2147024882;
  memset_0(v8, 0, 0x68u);
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 16;
  v5 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v5 )
    return v5 | 0x80010000;
  if ( ProcessIdToSessionId(dwProcessId, pSessionId) )
  {
    result = 0;
    *v3 = pSessionId[0];
    *a2 = v3;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800098d0  mov     [rsp+arg_0], rbx
0x1800098d5  push    rdi
0x1800098d6  sub     rsp, 0B0h
0x1800098dd  mov     rax, cs:__security_cookie
0x1800098e4  xor     rax, rsp
0x1800098e7  mov     [rsp+0B8h+var_18], rax
0x1800098ef  mov     rdi, rdx
0x1800098f2  mov     [rsp+0B8h+pSessionId], 0
0x1800098fa  xor     edx, edx; Val
0x1800098fc  lea     rcx, [rsp+0B8h+RpcCallAttributes]; void *
0x180009901  lea     r8d, [rdx+70h]; Size
0x180009905  call    memset_0
0x18000990a  mov     ecx, 4; Size
0x18000990f  call    cs:__imp_malloc
0x180009915  mov     rbx, rax
0x180009918  test    rax, rax
0x18000991b  jnz     short loc_180009924
0x18000991d  mov     eax, 8007000Eh
0x180009922  jmp     short loc_18000998E
0x180009924  xor     edx, edx; Val
0x180009926  lea     rcx, [rsp+0B8h+var_80]; void *
0x18000992b  lea     r8d, [rdx+68h]; Size
0x18000992f  call    memset_0
0x180009934  lea     rdx, [rsp+0B8h+RpcCallAttributes]; RpcCallAttributes
0x180009939  mov     [rsp+0B8h+RpcCallAttributes], 3
0x180009941  xor     ecx, ecx; ClientBinding
0x180009943  mov     [rsp+0B8h+var_84], 10h
0x18000994b  call    cs:__imp_RpcServerInqCallAttributesW
0x180009951  test    eax, eax
0x180009953  jz      short loc_18000995C
0x180009955  or      eax, 80010000h
0x18000995a  jmp     short loc_18000998E
0x18000995c  mov     ecx, [rsp+0B8h+dwProcessId]; dwProcessId
0x180009960  lea     rdx, [rsp+0B8h+pSessionId]; pSessionId
0x180009965  call    cs:__imp_ProcessIdToSessionId
0x18000996b  test    eax, eax
0x18000996d  jnz     short loc_180009983
0x18000996f  call    cs:__imp_GetLastError
0x180009975  test    eax, eax
0x180009977  jle     short loc_18000998E
0x180009979  movzx   eax, ax
0x18000997c  or      eax, 80070000h
0x180009981  jmp     short loc_18000998E
0x180009983  mov     ecx, [rsp+0B8h+pSessionId]
0x180009987  xor     eax, eax
0x180009989  mov     [rbx], ecx
0x18000998b  mov     [rdi], rbx
0x18000998e  mov     rcx, [rsp+0B8h+var_18]
0x180009996  xor     rcx, rsp; StackCookie
0x180009999  call    __security_check_cookie
0x18000999e  mov     rbx, [rsp+0B8h+arg_0]
0x1800099a6  add     rsp, 0B0h
0x1800099ad  pop     rdi
0x1800099ae  retn
```

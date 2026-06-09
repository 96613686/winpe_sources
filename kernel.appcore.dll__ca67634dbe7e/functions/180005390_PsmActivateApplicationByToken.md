# PsmActivateApplicationByToken

- ea: `0x180005390`
- end: `0x1800054e7`
- name: `PsmActivateApplicationByToken`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005390`
- `0x18000772c`
- `0x180009d9e`
- `0x180009dd0`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x18000540b`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18000540b`
- `ntdll!NtQueryInformationToken` at `0x180005446`
- `ntdll!NtQueryInformationToken` at `0x180005446`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180005470`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180005470`
- `RPCRT4!NdrClientCall3` at `0x1800054a6`
- `RPCRT4!NdrClientCall3` at `0x1800054a6`
- `RPCRT4!RpcExceptionFilter` at `0x180009f4e`
- `RPCRT4!RpcExceptionFilter` at `0x180009f4e`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800054b9`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800054b9`

## pseudocode

```c
NTSTATUS __fastcall PsmActivateApplicationByToken(int a1, void *a2)
{
  int v4; // ebx
  NTSTATUS result; // eax
  __int64 v6; // rbx
  PULONG ReturnLength; // [rsp+20h] [rbp-2A8h]
  int v8; // [rsp+40h] [rbp-288h] BYREF
  ULONG v9; // [rsp+44h] [rbp-284h] BYREF
  _QWORD v10[2]; // [rsp+50h] [rbp-278h] BYREF
  _QWORD v11[2]; // [rsp+60h] [rbp-268h] BYREF
  _QWORD TokenInformation[12]; // [rsp+70h] [rbp-258h] BYREF
  _BYTE v13[464]; // [rsp+D0h] [rbp-1F8h] BYREF

  v10[0] = 0;
  v11[0] = qword_18000B020;
  v11[1] = PsmCltOpenActivationChannel;
  v8 = 0;
  v9 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  v4 = RtlRunOnceExecuteOnce(&PsmpActInitContext, PsmpAcquireContextHandle, v11, v10);
  if ( v4 >= 0 )
  {
    result = NtQueryInformationToken(a2, TokenUser, TokenInformation, 0x58u, &v9);
    if ( result >= 0 )
    {
      v6 = TokenInformation[0];
      v8 = 464;
      result = PsmGetKeyFromToken(a2, v13, &v8, 0);
      if ( result >= 0 )
      {
        v10[1] = 0;
        LODWORD(ReturnLength) = a1;
        return (unsigned int)NdrClientCall3(
                               (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                               0,
                               0,
                               v10[0],
                               ReturnLength,
                               v6,
                               v13).Pointer;
      }
    }
  }
  else
  {
    if ( !(unsigned __int8)IsShellExecuteWPresent() )
      return 0;
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180005390  mov     [rsp+arg_10], rbx
0x180005395  push    rsi
0x180005396  push    rdi
0x180005397  push    r14
0x180005399  sub     rsp, 2B0h
0x1800053a0  mov     rax, cs:__security_cookie
0x1800053a7  xor     rax, rsp
0x1800053aa  mov     [rsp+2C8h+var_28], rax
0x1800053b2  mov     rdi, rdx
0x1800053b5  mov     esi, ecx
0x1800053b7  xor     r14d, r14d
0x1800053ba  mov     [rsp+2C8h+var_278], r14
0x1800053bf  lea     rax, qword_18000B020
0x1800053c6  mov     [rsp+2C8h+var_268], rax
0x1800053cb  lea     rax, PsmCltOpenActivationChannel
0x1800053d2  mov     [rsp+2C8h+var_260], rax
0x1800053d7  mov     [rsp+2C8h+var_288], r14d
0x1800053dc  mov     [rsp+2C8h+var_284], r14d
0x1800053e1  xor     edx, edx; Val
0x1800053e3  mov     r8d, 58h ; 'X'; Size
0x1800053e9  lea     rcx, [rsp+2C8h+TokenInformation]; void *
0x1800053ee  call    memset_0
0x1800053f3  lea     r9, [rsp+2C8h+var_278]
0x1800053f8  lea     r8, [rsp+2C8h+var_268]
0x1800053fd  lea     rdx, PsmpAcquireContextHandle
0x180005404  lea     rcx, PsmpActInitContext
0x18000540b  call    cs:__imp_RtlRunOnceExecuteOnce
0x180005411  mov     ebx, eax
0x180005413  test    eax, eax
0x180005415  jns     short loc_180005429
0x180005417  call    IsShellExecuteWPresent
0x18000541c  test    al, al
0x18000541e  cmovz   ebx, r14d
0x180005422  mov     eax, ebx
0x180005424  jmp     loc_1800054C3
0x180005429  lea     rax, [rsp+2C8h+var_284]
0x18000542e  mov     [rsp+2C8h+ReturnLength], rax; ReturnLength
0x180005433  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180005439  lea     r8, [rsp+2C8h+TokenInformation]; TokenInformation
0x18000543e  mov     edx, 1; TokenInformationClass
0x180005443  mov     rcx, rdi; TokenHandle
0x180005446  call    cs:__imp_NtQueryInformationToken
0x18000544c  test    eax, eax
0x18000544e  js      short loc_1800054C3
0x180005450  mov     rbx, [rsp+2C8h+TokenInformation]
0x180005455  mov     [rsp+2C8h+var_288], 1D0h
0x18000545d  xor     r9d, r9d
0x180005460  lea     r8, [rsp+2C8h+var_288]
0x180005465  lea     rdx, [rsp+2C8h+var_1F8]
0x18000546d  mov     rcx, rdi
0x180005470  call    cs:__imp_PsmGetKeyFromToken
0x180005476  test    eax, eax
0x180005478  js      short loc_1800054C3
0x18000547a  mov     [rsp+2C8h+var_270], r14
0x18000547f  lea     rax, [rsp+2C8h+var_1F8]
0x180005487  mov     [rsp+2C8h+var_298], rax
0x18000548c  mov     [rsp+2C8h+var_2A0], rbx
0x180005491  mov     dword ptr [rsp+2C8h+ReturnLength], esi
0x180005495  mov     r9, [rsp+2C8h+var_278]
0x18000549a  xor     r8d, r8d; pReturnValue
0x18000549d  xor     edx, edx; nProcNum
0x18000549f  lea     rcx, pProxyInfo; pProxyInfo
0x1800054a6  call    cs:__imp_NdrClientCall3
0x1800054ac  mov     [rsp+2C8h+var_270], rax
0x1800054b1  mov     [rsp+2C8h+var_280], eax
0x1800054b5  jmp     short loc_1800054C3
0x1800054b7  mov     ecx, eax; Status
0x1800054b9  call    cs:__imp_I_RpcMapWin32Status
0x1800054bf  mov     [rsp+2C8h+var_280], eax
0x1800054c3  mov     rcx, [rsp+2C8h+var_28]
0x1800054cb  xor     rcx, rsp; StackCookie
0x1800054ce  call    __security_check_cookie
0x1800054d3  mov     rbx, [rsp+2C8h+arg_10]
0x1800054db  add     rsp, 2B0h
0x1800054e2  pop     r14
0x1800054e4  pop     rdi
0x1800054e5  pop     rsi
0x1800054e6  retn
0x180009f40  push    rbp
0x180009f42  sub     rsp, 40h
0x180009f46  mov     rbp, rdx
0x180009f49  mov     rcx, [rcx]
0x180009f4c  mov     ecx, [rcx]; ExceptionCode
0x180009f4e  call    cs:__imp_RpcExceptionFilter
0x180009f54  nop
0x180009f55  add     rsp, 40h
0x180009f59  pop     rbp
0x180009f5a  retn
```

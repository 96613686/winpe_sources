# PsmpQueryCallerInformation

- ea: `0x18002dab0`
- end: `0x18002dbc8`
- name: `PsmpQueryCallerInformation`
- size: `280`
- prototype: `RPC_STATUS __fastcall(_DWORD *, void *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002a3a0`
- `0x18002a630`
- `0x18002a7d0`
- `0x18002b200`

## callees

- `0x18001b7e0`
- `0x18001c10c`
- `0x18002dab0`
- `0x18002e17c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002db64`
- `ntdll!RtlLengthSid` at `0x18002db7d`
- `ntdll!RtlLengthSid` at `0x18002db64`
- `ntdll!RtlLengthSid` at `0x18002db7d`
- `ntdll!NtQueryInformationToken` at `0x18002db27`
- `ntdll!NtQueryInformationToken` at `0x18002db53`
- `ntdll!NtQueryInformationToken` at `0x18002db27`
- `ntdll!NtQueryInformationToken` at `0x18002db53`
- `RPCRT4!RpcImpersonateClient` at `0x18002db00`
- `RPCRT4!RpcImpersonateClient` at `0x18002db00`
- `RPCRT4!RpcRevertToSelf` at `0x18002db9b`
- `RPCRT4!RpcRevertToSelf` at `0x18002db9b`

## pseudocode

```c
RPC_STATUS __fastcall PsmpQueryCallerInformation(_DWORD *a1, void *a2)
{
  RPC_STATUS result; // eax
  NTSTATUS v5; // ebx
  ULONG v6; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-88h] BYREF
  _DWORD v8[3]; // [rsp+34h] [rbp-84h] BYREF
  const void *TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  v8[0] = 0;
  ReturnLength = 0;
  memset_0(TokenInformation, 0, 0x58u);
  result = RpcImpersonateClient(0);
  if ( result >= 0 )
  {
    v5 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenUser, TokenInformation, 0x58u, &ReturnLength);
    if ( v5 >= 0 )
    {
      v5 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenSessionId, v8, 4u, &ReturnLength);
      if ( v5 >= 0 )
      {
        RtlLengthSid((PSID)TokenInformation[0]);
        memset_0(a2, 0, 0x44u);
        v6 = RtlLengthSid((PSID)TokenInformation[0]);
        memcpy_0(a2, TokenInformation[0], v6);
        v5 = 0;
        *a1 = v8[0];
      }
    }
    RpcRevertToSelf();
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002dab0  mov     [rsp+arg_10], rbx
0x18002dab5  mov     [rsp+arg_18], rsi
0x18002daba  push    rdi
0x18002dabb  sub     rsp, 0B0h
0x18002dac2  mov     rax, cs:__security_cookie
0x18002dac9  xor     rax, rsp
0x18002dacc  mov     [rsp+0B8h+var_18], rax
0x18002dad4  mov     rdi, rdx
0x18002dad7  mov     [rsp+0B8h+var_84], 0
0x18002dadf  mov     rsi, rcx
0x18002dae2  mov     [rsp+0B8h+var_88], 0
0x18002daea  mov     ebx, 58h ; 'X'
0x18002daef  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x18002daf4  mov     r8d, ebx; Size
0x18002daf7  xor     edx, edx; Val
0x18002daf9  call    memset_0
0x18002dafe  xor     ecx, ecx; BindingHandle
0x18002db00  call    cs:__imp_RpcImpersonateClient
0x18002db06  test    eax, eax
0x18002db08  js      loc_18002DBA3
0x18002db0e  lea     rax, [rsp+0B8h+var_88]
0x18002db13  mov     r9d, ebx; TokenInformationLength
0x18002db16  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18002db1b  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18002db20  lea     edx, [rbx-57h]; TokenInformationClass
0x18002db23  lea     rcx, [rbx-5Dh]; TokenHandle
0x18002db27  call    cs:__imp_NtQueryInformationToken
0x18002db2d  mov     ebx, eax
0x18002db2f  test    eax, eax
0x18002db31  js      short loc_18002DB9B
0x18002db33  mov     r9d, 4; TokenInformationLength
0x18002db39  lea     rax, [rsp+0B8h+var_88]
0x18002db3e  lea     r8, [rsp+0B8h+var_84]; TokenInformation
0x18002db43  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18002db48  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18002db4f  lea     edx, [r9+8]; TokenInformationClass
0x18002db53  call    cs:__imp_NtQueryInformationToken
0x18002db59  mov     ebx, eax
0x18002db5b  test    eax, eax
0x18002db5d  js      short loc_18002DB9B
0x18002db5f  mov     rcx, [rsp+0B8h+TokenInformation]; Sid
0x18002db64  call    cs:__imp_RtlLengthSid
0x18002db6a  xor     edx, edx; Val
0x18002db6c  mov     rcx, rdi; void *
0x18002db6f  lea     r8d, [rdx+44h]; Size
0x18002db73  call    memset_0
0x18002db78  mov     rcx, [rsp+0B8h+TokenInformation]; Sid
0x18002db7d  call    cs:__imp_RtlLengthSid
0x18002db83  mov     rdx, [rsp+0B8h+TokenInformation]; Src
0x18002db88  mov     rcx, rdi; void *
0x18002db8b  mov     r8d, eax; Size
0x18002db8e  call    memcpy_0
0x18002db93  mov     eax, [rsp+0B8h+var_84]
0x18002db97  xor     ebx, ebx
0x18002db99  mov     [rsi], eax
0x18002db9b  call    cs:__imp_RpcRevertToSelf
0x18002dba1  mov     eax, ebx
0x18002dba3  mov     rcx, [rsp+0B8h+var_18]
0x18002dbab  xor     rcx, rsp; StackCookie
0x18002dbae  call    __security_check_cookie
0x18002dbb3  lea     r11, [rsp+0B8h+var_8]
0x18002dbbb  mov     rbx, [r11+20h]
0x18002dbbf  mov     rsi, [r11+28h]
0x18002dbc3  mov     rsp, r11
0x18002dbc6  pop     rdi
0x18002dbc7  retn
```

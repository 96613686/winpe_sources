# CPSImpersonateCallingClient(void *,int)

- ea: `0x18000dbd0`
- end: `0x18000dca1`
- name: `?CPSImpersonateCallingClient@@YAKPEAXH@Z`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010870`

## callees

- `0x180007f10`
- `0x18000dbd0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000dc7f`
- `RPCRT4!RpcImpersonateClient` at `0x18000dc7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc43`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000dbf1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000dc1b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000dbf1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000dc1b`

## string_xrefs

- `0x18000dc5f`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall CPSImpersonateCallingClient(_QWORD *a1, int a2)
{
  void *v2; // rdx
  DWORD v3; // ebx
  void *v5; // rdx
  DWORD LastError; // eax
  __int64 v7; // r9
  void *v8; // rcx

  if ( a1 )
  {
    if ( a2 && (v5 = (void *)a1[4]) != 0 )
    {
      if ( !SetThreadToken(0, v5) )
      {
        LastError = GetLastError();
        v7 = 736;
LABEL_12:
        v3 = LastError;
LABEL_13:
        DebugTraceError(
          LastError,
          "dwLastError",
          "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
          v7);
        return v3;
      }
    }
    else
    {
      v2 = (void *)a1[3];
      if ( !v2 )
      {
        v8 = (void *)a1[1];
        if ( !v8 )
          return 87;
        LastError = RpcImpersonateClient(v8);
        v3 = LastError;
        if ( LastError )
        {
          v7 = 768;
          goto LABEL_13;
        }
        return v3;
      }
      if ( !SetThreadToken(0, v2) )
      {
        LastError = GetLastError();
        v7 = 752;
        goto LABEL_12;
      }
    }
    return 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000dbd0  sub     rsp, 28h
0x18000dbd4  test    rcx, rcx
0x18000dbd7  jz      short loc_18000DC3F
0x18000dbd9  mov     [rsp+28h+var_8], rbx
0x18000dbde  test    edx, edx
0x18000dbe0  jnz     short loc_18000DC10
0x18000dbe2  mov     rdx, [rcx+18h]; Token
0x18000dbe6  test    rdx, rdx
0x18000dbe9  jz      loc_18000DC76
0x18000dbef  xor     ecx, ecx; Thread
0x18000dbf1  call    cs:__imp_SetThreadToken
0x18000dbf8  nop     dword ptr [rax+rax+00h]
0x18000dbfd  test    eax, eax
0x18000dbff  jz      short loc_18000DC43
0x18000dc01  xor     ebx, ebx
0x18000dc03  mov     eax, ebx
0x18000dc05  mov     rbx, [rsp+28h+var_8]
0x18000dc0a  add     rsp, 28h
0x18000dc0e  retn
0x18000dc10  mov     rdx, [rcx+20h]; Token
0x18000dc14  test    rdx, rdx
0x18000dc17  jz      short loc_18000DBE2
0x18000dc19  xor     ecx, ecx; Thread
0x18000dc1b  call    cs:__imp_SetThreadToken
0x18000dc22  nop     dword ptr [rax+rax+00h]
0x18000dc27  test    eax, eax
0x18000dc29  jnz     short loc_18000DC01
0x18000dc2b  call    cs:__imp_GetLastError
0x18000dc32  nop     dword ptr [rax+rax+00h]
0x18000dc37  mov     r9d, 2E0h
0x18000dc3d  jmp     short loc_18000DC55
0x18000dc3f  xor     eax, eax
0x18000dc41  jmp     short loc_18000DC0A
0x18000dc43  call    cs:__imp_GetLastError
0x18000dc4a  nop     dword ptr [rax+rax+00h]
0x18000dc4f  mov     r9d, 2F0h
0x18000dc55  mov     ebx, eax
0x18000dc57  jmp     short loc_18000DC5F
0x18000dc59  mov     r9d, 300h
0x18000dc5f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000dc66  mov     ecx, eax
0x18000dc68  lea     rdx, aDwlasterror; "dwLastError"
0x18000dc6f  call    DebugTraceError
0x18000dc74  jmp     short loc_18000DC03
0x18000dc76  mov     rcx, [rcx+8]; BindingHandle
0x18000dc7a  test    rcx, rcx
0x18000dc7d  jz      short loc_18000DC97
0x18000dc7f  call    cs:__imp_RpcImpersonateClient
0x18000dc86  nop     dword ptr [rax+rax+00h]
0x18000dc8b  mov     ebx, eax
0x18000dc8d  test    eax, eax
0x18000dc8f  jz      loc_18000DC03
0x18000dc95  jmp     short loc_18000DC59
0x18000dc97  mov     ebx, 57h ; 'W'
0x18000dc9c  jmp     loc_18000DC03
```

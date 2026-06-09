# CPSImpersonateClient(void *)

- ea: `0x1800063c0`
- end: `0x1800064fd`
- name: `?CPSImpersonateClient@@YAKPEAX@Z`
- size: `317`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `14`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004920`
- `0x180005880`
- `0x1800060e0`
- `0x180008498`
- `0x180008c3c`
- `0x18000e9c0`
- `0x18000fbb4`
- `0x180014c80`
- `0x180018a20`
- `0x1800193c0`
- `0x180019f40`
- `0x18002b0ec`
- `0x18002e310`
- `0x180038d40`

## callees

- `0x1800063c0`
- `0x180007f10`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180006497`
- `RPCRT4!RpcImpersonateClient` at `0x180006497`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180006462`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180006462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064cf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006404`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006404`

## string_xrefs

- `0x180006426`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x1800064af`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x1800064e5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall CPSImpersonateClient(_DWORD *a1)
{
  DWORD LastError; // ebx
  int v2; // edx
  void *v3; // rdx
  DWORD v4; // edi
  __int64 v5; // r9
  __int64 v6; // rcx
  void *v8; // rcx
  unsigned int v9; // eax

  if ( a1 )
  {
    LastError = 87;
    if ( *a1 == 624 )
    {
      if ( a1[4] || (v2 = a1[12]) != 0 && (unsigned int)(v2 - 90) > 1 && v2 != 99 )
      {
        if ( ImpersonateSelf(SecurityImpersonation) )
          return 0;
        LastError = GetLastError();
        v6 = LastError;
        v5 = 816;
LABEL_21:
        DebugTraceError(v6, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", v5);
        return LastError;
      }
      v3 = (void *)*((_QWORD *)a1 + 3);
      if ( !v3 )
      {
        v8 = (void *)*((_QWORD *)a1 + 1);
        if ( v8 )
        {
          v9 = RpcImpersonateClient(v8);
          v4 = v9;
          if ( !v9 )
            return 0;
          DebugTraceError(v9, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 768);
          LastError = v4;
          goto LABEL_9;
        }
LABEL_8:
        v4 = LastError;
LABEL_9:
        v5 = 825;
        v6 = v4;
        goto LABEL_21;
      }
      if ( SetThreadToken(0, v3) )
        return 0;
      LastError = GetLastError();
      DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 752);
      if ( LastError )
        goto LABEL_8;
    }
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x1800063c0  sub     rsp, 28h
0x1800063c4  test    rcx, rcx
0x1800063c7  jz      loc_180006486
0x1800063cd  cmp     dword ptr [rcx], 270h
0x1800063d3  mov     [rsp+28h+arg_0], rbx
0x1800063d8  mov     ebx, 57h ; 'W'
0x1800063dd  mov     [rsp+28h+var_8], rdi
0x1800063e2  jnz     loc_180006474
0x1800063e8  cmp     dword ptr [rcx+10h], 0
0x1800063ec  jnz     short loc_18000645D
0x1800063ee  mov     edx, [rcx+30h]
0x1800063f1  test    edx, edx
0x1800063f3  jnz     short loc_180006450
0x1800063f5  mov     rdx, [rcx+18h]; Token
0x1800063f9  test    rdx, rdx
0x1800063fc  jz      loc_18000648E
0x180006402  xor     ecx, ecx; Thread
0x180006404  call    cs:__imp_SetThreadToken
0x18000640b  nop     dword ptr [rax+rax+00h]
0x180006410  test    eax, eax
0x180006412  jnz     short loc_180006472
0x180006414  call    cs:__imp_GetLastError
0x18000641b  nop     dword ptr [rax+rax+00h]
0x180006420  mov     r9d, 2F0h
0x180006426  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000642d  mov     ecx, eax
0x18000642f  lea     rdx, aDwlasterror; "dwLastError"
0x180006436  mov     ebx, eax
0x180006438  call    DebugTraceError
0x18000643d  test    ebx, ebx
0x18000643f  jz      short loc_180006474
0x180006441  mov     edi, ebx
0x180006443  mov     r9d, 339h
0x180006449  mov     ecx, edi
0x18000644b  jmp     loc_1800064E5
0x180006450  lea     eax, [rdx-5Ah]
0x180006453  cmp     eax, 1
0x180006456  jbe     short loc_1800063F5
0x180006458  cmp     edx, 63h ; 'c'
0x18000645b  jz      short loc_1800063F5
0x18000645d  mov     ecx, 2; ImpersonationLevel
0x180006462  call    cs:__imp_ImpersonateSelf
0x180006469  nop     dword ptr [rax+rax+00h]
0x18000646e  test    eax, eax
0x180006470  jz      short loc_1800064CF
0x180006472  xor     ebx, ebx
0x180006474  mov     rdi, [rsp+28h+var_8]
0x180006479  mov     eax, ebx
0x18000647b  mov     rbx, [rsp+28h+arg_0]
0x180006480  add     rsp, 28h
0x180006484  retn
0x180006486  xor     eax, eax
0x180006488  add     rsp, 28h
0x18000648c  retn
0x18000648e  mov     rcx, [rcx+8]; BindingHandle
0x180006492  test    rcx, rcx
0x180006495  jz      short loc_180006441
0x180006497  call    cs:__imp_RpcImpersonateClient
0x18000649e  nop     dword ptr [rax+rax+00h]
0x1800064a3  mov     edi, eax
0x1800064a5  test    eax, eax
0x1800064a7  jz      short loc_1800064CB
0x1800064a9  mov     r9d, 300h
0x1800064af  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800064b6  lea     rdx, aDwlasterror; "dwLastError"
0x1800064bd  mov     ecx, eax
0x1800064bf  call    DebugTraceError
0x1800064c4  mov     ebx, edi
0x1800064c6  jmp     loc_180006443
0x1800064cb  mov     ebx, edi
0x1800064cd  jmp     short loc_180006474
0x1800064cf  call    cs:__imp_GetLastError
0x1800064d6  nop     dword ptr [rax+rax+00h]
0x1800064db  mov     ebx, eax
0x1800064dd  mov     ecx, eax
0x1800064df  mov     r9d, 330h
0x1800064e5  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800064ec  lea     rdx, aDwlasterror; "dwLastError"
0x1800064f3  call    DebugTraceError
0x1800064f8  jmp     loc_180006474
```

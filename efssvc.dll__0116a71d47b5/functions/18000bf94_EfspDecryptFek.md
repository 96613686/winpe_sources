# EfspDecryptFek

- ea: `0x18000bf94`
- end: `0x18000c0a6`
- name: `EfspDecryptFek`
- size: `274`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000b880`

## callees

- `0x18000bf94`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c020`
- `RPCRT4!RpcRevertToSelf` at `0x18000c08f`
- `RPCRT4!RpcRevertToSelf` at `0x18000c08f`
- `RPCRT4!RpcImpersonateClient` at `0x18000bfcb`
- `RPCRT4!RpcImpersonateClient` at `0x18000bfcb`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000bff9`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000c02c`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000c06a`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000bff9`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000c02c`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000c06a`
- `EFSCORE!EfsDllDecryptFek` at `0x18000c05a`
- `EFSCORE!EfsDllDecryptFek` at `0x18000c05a`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000c07f`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000c07f`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000c089`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000c089`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000bfe3`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000bfe3`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000c016`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000c016`

## pseudocode

```c
__int64 __fastcall EfspDecryptFek(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  DWORD v10; // eax
  DWORD LastError; // eax
  unsigned int v12; // eax
  _DWORD v13[4]; // [rsp+30h] [rbp-51h] BYREF
  _BYTE v14[144]; // [rsp+40h] [rbp-41h] BYREF

  v13[0] = 0;
  memset_0(v14, 0, 0x70u);
  if ( RpcImpersonateClient(0) )
    return 3221225506LL;
  if ( (unsigned __int8)EfsDllGetUserInfo(v14) )
  {
    if ( (unsigned int)EfsDllLoadUserProfile(v14, 0) )
    {
      v12 = EfsDllDecryptFek(v14, a1, a2, a3, a4, a5);
      if ( v12 && !(unsigned int)EfsDllErrorToNtStatus(v12, v13) )
        v13[0] = -1073741823;
      EfsDllUnloadUserProfile(v14);
    }
    else
    {
      LastError = GetLastError();
      if ( !(unsigned int)EfsDllErrorToNtStatus(LastError, v13) )
        v13[0] = -1073741823;
    }
    EfsDllFreeUserInfo(v14);
  }
  else
  {
    v10 = GetLastError();
    if ( !(unsigned int)EfsDllErrorToNtStatus(v10, v13) )
      v13[0] = -1073741823;
  }
  RpcRevertToSelf();
  return v13[0];
}

```

## disassembly

```asm
0x18000bf94  push    rbp
0x18000bf96  push    rbx
0x18000bf97  push    rsi
0x18000bf98  push    rdi
0x18000bf99  push    r14
0x18000bf9b  lea     rbp, [rsp-2Fh]
0x18000bfa0  sub     rsp, 0B0h
0x18000bfa7  mov     rsi, rdx
0x18000bfaa  mov     [rbp+4Fh+var_A0], 0
0x18000bfb1  xor     edx, edx; Val
0x18000bfb3  mov     rdi, r8
0x18000bfb6  mov     r14, rcx
0x18000bfb9  mov     rbx, r9
0x18000bfbc  lea     rcx, [rbp+4Fh+var_90]; void *
0x18000bfc0  lea     r8d, [rdx+70h]; Size
0x18000bfc4  call    memset_0
0x18000bfc9  xor     ecx, ecx; BindingHandle
0x18000bfcb  call    cs:__imp_RpcImpersonateClient
0x18000bfd1  test    eax, eax
0x18000bfd3  jz      short loc_18000BFDF
0x18000bfd5  mov     eax, 0C0000022h
0x18000bfda  jmp     loc_18000C098
0x18000bfdf  lea     rcx, [rbp+4Fh+var_90]
0x18000bfe3  call    cs:__imp_EfsDllGetUserInfo
0x18000bfe9  test    al, al
0x18000bfeb  jnz     short loc_18000C010
0x18000bfed  call    cs:__imp_GetLastError
0x18000bff3  mov     ecx, eax
0x18000bff5  lea     rdx, [rbp+4Fh+var_A0]
0x18000bff9  call    cs:__imp_EfsDllErrorToNtStatus
0x18000bfff  test    eax, eax
0x18000c001  jnz     loc_18000C08F
0x18000c007  mov     [rbp+4Fh+var_A0], 0C0000001h
0x18000c00e  jmp     short loc_18000C08F
0x18000c010  xor     edx, edx
0x18000c012  lea     rcx, [rbp+4Fh+var_90]
0x18000c016  call    cs:__imp_EfsDllLoadUserProfile
0x18000c01c  test    eax, eax
0x18000c01e  jnz     short loc_18000C03F
0x18000c020  call    cs:__imp_GetLastError
0x18000c026  mov     ecx, eax
0x18000c028  lea     rdx, [rbp+4Fh+var_A0]
0x18000c02c  call    cs:__imp_EfsDllErrorToNtStatus
0x18000c032  test    eax, eax
0x18000c034  jnz     short loc_18000C085
0x18000c036  mov     [rbp+4Fh+var_A0], 0C0000001h
0x18000c03d  jmp     short loc_18000C085
0x18000c03f  mov     rax, [rbp+4Fh+arg_20]
0x18000c043  lea     rcx, [rbp+4Fh+var_90]
0x18000c047  mov     [rsp+0D0h+var_A8], rax
0x18000c04c  mov     r9, rdi
0x18000c04f  mov     r8, rsi
0x18000c052  mov     [rsp+0D0h+var_B0], rbx
0x18000c057  mov     rdx, r14
0x18000c05a  call    cs:__imp_EfsDllDecryptFek
0x18000c060  test    eax, eax
0x18000c062  jz      short loc_18000C07B
0x18000c064  lea     rdx, [rbp+4Fh+var_A0]
0x18000c068  mov     ecx, eax
0x18000c06a  call    cs:__imp_EfsDllErrorToNtStatus
0x18000c070  test    eax, eax
0x18000c072  jnz     short loc_18000C07B
0x18000c074  mov     [rbp+4Fh+var_A0], 0C0000001h
0x18000c07b  lea     rcx, [rbp+4Fh+var_90]
0x18000c07f  call    cs:__imp_EfsDllUnloadUserProfile
0x18000c085  lea     rcx, [rbp+4Fh+var_90]
0x18000c089  call    cs:__imp_EfsDllFreeUserInfo
0x18000c08f  call    cs:__imp_RpcRevertToSelf
0x18000c095  mov     eax, [rbp+4Fh+var_A0]
0x18000c098  add     rsp, 0B0h
0x18000c09f  pop     r14
0x18000c0a1  pop     rdi
0x18000c0a2  pop     rsi
0x18000c0a3  pop     rbx
0x18000c0a4  pop     rbp
0x18000c0a5  retn
```

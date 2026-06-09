# EfspDecryptFek

- ea: `0x18000ccf8`
- end: `0x18000ce56`
- name: `EfspDecryptFek`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000c530`

## callees

- `0x18000ccf8`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cda5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cda5`
- `RPCRT4!RpcRevertToSelf` at `0x18000ce38`
- `RPCRT4!RpcRevertToSelf` at `0x18000ce38`
- `RPCRT4!RpcImpersonateClient` at `0x18000cd2f`
- `RPCRT4!RpcImpersonateClient` at `0x18000cd2f`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000cd6f`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000cdb7`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000ce01`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000cd6f`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000cdb7`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000ce01`
- `EFSCORE!EfsDllDecryptFek` at `0x18000cdeb`
- `EFSCORE!EfsDllDecryptFek` at `0x18000cdeb`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000ce1c`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000ce1c`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000ce2c`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000ce2c`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000cd4d`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000cd4d`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000cd95`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000cd95`

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
0x18000ccf8  push    rbp
0x18000ccfa  push    rbx
0x18000ccfb  push    rsi
0x18000ccfc  push    rdi
0x18000ccfd  push    r14
0x18000ccff  lea     rbp, [rsp-2Fh]
0x18000cd04  sub     rsp, 0B0h
0x18000cd0b  mov     rsi, rdx
0x18000cd0e  mov     [rbp+4Fh+var_A0], 0
0x18000cd15  xor     edx, edx; Val
0x18000cd17  mov     rdi, r8
0x18000cd1a  mov     r14, rcx
0x18000cd1d  mov     rbx, r9
0x18000cd20  lea     rcx, [rbp+4Fh+var_90]; void *
0x18000cd24  lea     r8d, [rdx+70h]; Size
0x18000cd28  call    memset_0
0x18000cd2d  xor     ecx, ecx; BindingHandle
0x18000cd2f  call    cs:__imp_RpcImpersonateClient
0x18000cd36  nop     dword ptr [rax+rax+00h]
0x18000cd3b  test    eax, eax
0x18000cd3d  jz      short loc_18000CD49
0x18000cd3f  mov     eax, 0C0000022h
0x18000cd44  jmp     loc_18000CE47
0x18000cd49  lea     rcx, [rbp+4Fh+var_90]
0x18000cd4d  call    cs:__imp_EfsDllGetUserInfo
0x18000cd54  nop     dword ptr [rax+rax+00h]
0x18000cd59  test    al, al
0x18000cd5b  jnz     short loc_18000CD8F
0x18000cd5d  call    cs:__imp_GetLastError
0x18000cd64  nop     dword ptr [rax+rax+00h]
0x18000cd69  mov     ecx, eax
0x18000cd6b  lea     rdx, [rbp+4Fh+var_A0]
0x18000cd6f  call    cs:__imp_EfsDllErrorToNtStatus
0x18000cd76  nop     dword ptr [rax+rax+00h]
0x18000cd7b  test    eax, eax
0x18000cd7d  jnz     loc_18000CE38
0x18000cd83  mov     [rbp+4Fh+var_A0], 0C0000001h
0x18000cd8a  jmp     loc_18000CE38
0x18000cd8f  xor     edx, edx
0x18000cd91  lea     rcx, [rbp+4Fh+var_90]
0x18000cd95  call    cs:__imp_EfsDllLoadUserProfile
0x18000cd9c  nop     dword ptr [rax+rax+00h]
0x18000cda1  test    eax, eax
0x18000cda3  jnz     short loc_18000CDD0
0x18000cda5  call    cs:__imp_GetLastError
0x18000cdac  nop     dword ptr [rax+rax+00h]
0x18000cdb1  mov     ecx, eax
0x18000cdb3  lea     rdx, [rbp+4Fh+var_A0]
0x18000cdb7  call    cs:__imp_EfsDllErrorToNtStatus
0x18000cdbe  nop     dword ptr [rax+rax+00h]
0x18000cdc3  test    eax, eax
0x18000cdc5  jnz     short loc_18000CE28
0x18000cdc7  mov     [rbp+4Fh+var_A0], 0C0000001h
0x18000cdce  jmp     short loc_18000CE28
0x18000cdd0  mov     rax, [rbp+4Fh+arg_20]
0x18000cdd4  lea     rcx, [rbp+4Fh+var_90]
0x18000cdd8  mov     [rsp+0D0h+var_A8], rax
0x18000cddd  mov     r9, rdi
0x18000cde0  mov     r8, rsi
0x18000cde3  mov     [rsp+0D0h+var_B0], rbx
0x18000cde8  mov     rdx, r14
0x18000cdeb  call    cs:__imp_EfsDllDecryptFek
0x18000cdf2  nop     dword ptr [rax+rax+00h]
0x18000cdf7  test    eax, eax
0x18000cdf9  jz      short loc_18000CE18
0x18000cdfb  lea     rdx, [rbp+4Fh+var_A0]
0x18000cdff  mov     ecx, eax
0x18000ce01  call    cs:__imp_EfsDllErrorToNtStatus
0x18000ce08  nop     dword ptr [rax+rax+00h]
0x18000ce0d  test    eax, eax
0x18000ce0f  jnz     short loc_18000CE18
0x18000ce11  mov     [rbp+4Fh+var_A0], 0C0000001h
0x18000ce18  lea     rcx, [rbp+4Fh+var_90]
0x18000ce1c  call    cs:__imp_EfsDllUnloadUserProfile
0x18000ce23  nop     dword ptr [rax+rax+00h]
0x18000ce28  lea     rcx, [rbp+4Fh+var_90]
0x18000ce2c  call    cs:__imp_EfsDllFreeUserInfo
0x18000ce33  nop     dword ptr [rax+rax+00h]
0x18000ce38  call    cs:__imp_RpcRevertToSelf
0x18000ce3f  nop     dword ptr [rax+rax+00h]
0x18000ce44  mov     eax, [rbp+4Fh+var_A0]
0x18000ce47  add     rsp, 0B0h
0x18000ce4e  pop     r14
0x18000ce50  pop     rdi
0x18000ce51  pop     rsi
0x18000ce52  pop     rbx
0x18000ce53  pop     rbp
0x18000ce54  retn
```

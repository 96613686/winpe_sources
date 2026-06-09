# CryptnetUrlCacheSvcAddHpkp

- ea: `0x18000fcd8`
- end: `0x18000fda6`
- name: `CryptnetUrlCacheSvcAddHpkp`
- size: `206`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800083d0`

## callees

- `0x180008330`
- `0x18000fcd8`
- `0x180010d3c`
- `0x180011390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fd11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fd11`
- `RPCRT4!RpcImpersonateClient` at `0x18000fd2a`
- `RPCRT4!RpcImpersonateClient` at `0x18000fd2a`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000fd59`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000fd8c`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000fd59`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000fd8c`

## pseudocode

```c
__int64 __fastcall CryptnetUrlCacheSvcAddHpkp(RPC_BINDING_HANDLE BindingHandle, __int64 a2, unsigned int a3)
{
  int v7; // esi
  DWORD v8; // ecx
  RPC_STATUS v9; // eax
  DWORD LastError; // ebx

  if ( !fUrlCacheSvcStarted )
    return 1062;
  v7 = 0;
  _InterlockedIncrement(&lUrlCacheSvcActiveRefCnt);
  if ( !BindingHandle )
  {
    v8 = 87;
LABEL_5:
    SetLastError(v8);
LABEL_15:
    LastError = GetLastError();
    if ( !LastError )
      LastError = -2147418113;
    if ( v7 )
      RpcRevertToSelfEx(BindingHandle);
    goto LABEL_19;
  }
  if ( !fUrlCacheSvcStarted )
  {
    v8 = 1062;
    goto LABEL_5;
  }
  v9 = RpcImpersonateClient(BindingHandle);
  if ( v9 )
    goto LABEL_9;
  if ( (unsigned int)I_CryptIsAppContainerToken(0) && !(unsigned int)I_CryptHasAppContainerUserCertCapability() )
  {
    v7 = 1;
    v8 = 4252;
    goto LABEL_5;
  }
  v9 = RpcRevertToSelfEx(BindingHandle);
  if ( v9 )
  {
LABEL_9:
    v8 = v9;
    goto LABEL_5;
  }
  LastError = 0;
  if ( !(unsigned int)CreateAndAddToBeRunAddHpkpJob(a2, a3) )
    goto LABEL_15;
LABEL_19:
  _InterlockedDecrement(&lUrlCacheSvcActiveRefCnt);
  return LastError;
}

```

## disassembly

```asm
0x18000fcd8  push    rbx
0x18000fcda  push    rbp
0x18000fcdb  push    rsi
0x18000fcdc  push    rdi
0x18000fcdd  push    r14
0x18000fcdf  sub     rsp, 20h
0x18000fce3  mov     eax, cs:?fUrlCacheSvcStarted@@3HC; int volatile fUrlCacheSvcStarted
0x18000fce9  mov     ebp, r8d
0x18000fcec  mov     r14, rdx
0x18000fcef  mov     rdi, rcx
0x18000fcf2  test    eax, eax
0x18000fcf4  jnz     short loc_18000FD00
0x18000fcf6  mov     eax, 426h
0x18000fcfb  jmp     loc_18000FD9B
0x18000fd00  xor     esi, esi
0x18000fd02  lock inc cs:?lUrlCacheSvcActiveRefCnt@@3JC; long volatile lUrlCacheSvcActiveRefCnt
0x18000fd09  test    rdi, rdi
0x18000fd0c  jnz     short loc_18000FD19
0x18000fd0e  lea     ecx, [rsi+57h]; dwErrCode
0x18000fd11  call    cs:__imp_SetLastError
0x18000fd17  jmp     short loc_18000FD73
0x18000fd19  mov     eax, cs:?fUrlCacheSvcStarted@@3HC; int volatile fUrlCacheSvcStarted
0x18000fd1f  test    eax, eax
0x18000fd21  jnz     short loc_18000FD2A
0x18000fd23  mov     ecx, 426h; BindingHandle
0x18000fd28  jmp     short loc_18000FD11
0x18000fd2a  call    cs:__imp_RpcImpersonateClient
0x18000fd30  test    eax, eax
0x18000fd32  jz      short loc_18000FD38
0x18000fd34  mov     ecx, eax
0x18000fd36  jmp     short loc_18000FD11
0x18000fd38  xor     ecx, ecx
0x18000fd3a  call    I_CryptIsAppContainerToken
0x18000fd3f  test    eax, eax
0x18000fd41  jz      short loc_18000FD56
0x18000fd43  call    I_CryptHasAppContainerUserCertCapability
0x18000fd48  test    eax, eax
0x18000fd4a  jnz     short loc_18000FD56
0x18000fd4c  lea     esi, [rax+1]
0x18000fd4f  mov     ecx, 109Ch
0x18000fd54  jmp     short loc_18000FD11
0x18000fd56  mov     rcx, rdi; BindingHandle
0x18000fd59  call    cs:__imp_RpcRevertToSelfEx
0x18000fd5f  test    eax, eax
0x18000fd61  jnz     short loc_18000FD34
0x18000fd63  mov     edx, ebp
0x18000fd65  mov     rcx, r14
0x18000fd68  xor     ebx, ebx
0x18000fd6a  call    CreateAndAddToBeRunAddHpkpJob
0x18000fd6f  test    eax, eax
0x18000fd71  jnz     short loc_18000FD92
0x18000fd73  call    cs:__imp_GetLastError
0x18000fd79  mov     ebx, eax
0x18000fd7b  mov     eax, 8000FFFFh
0x18000fd80  test    ebx, ebx
0x18000fd82  cmovz   ebx, eax
0x18000fd85  test    esi, esi
0x18000fd87  jz      short loc_18000FD92
0x18000fd89  mov     rcx, rdi; BindingHandle
0x18000fd8c  call    cs:__imp_RpcRevertToSelfEx
0x18000fd92  lock dec cs:?lUrlCacheSvcActiveRefCnt@@3JC; long volatile lUrlCacheSvcActiveRefCnt
0x18000fd99  mov     eax, ebx
0x18000fd9b  add     rsp, 20h
0x18000fd9f  pop     r14
0x18000fda1  pop     rdi
0x18000fda2  pop     rsi
0x18000fda3  pop     rbp
0x18000fda4  pop     rbx
0x18000fda5  retn
```

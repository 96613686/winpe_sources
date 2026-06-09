# SspiInitializeSecurityContextAsyncW

- ea: `0x180022d90`
- end: `0x180022e09`
- name: `SspiInitializeSecurityContextAsyncW`
- size: `121`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *AsyncContext, PCredHandle phCredential, PCtxtHandle phContext, PSECURITY_STRING pszTargetName, unsigned int fContextReq, unsigned int Reserved1, unsigned int TargetDataRep, PSecBufferDesc pInput, unsigned int Reserved2, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180022d90`
- `0x180024910`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiInitializeSecurityContextAsyncW(
        SspiAsyncContext *AsyncContext,
        PCredHandle phCredential,
        PCtxtHandle phContext,
        PSECURITY_STRING pszTargetName,
        unsigned int fContextReq,
        unsigned int Reserved1,
        unsigned int TargetDataRep,
        PSecBufferDesc pInput,
        unsigned int Reserved2,
        PCtxtHandle phNewContext,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        PTimeStamp ptsExpiry)
{
  if ( !AsyncContext || *((_DWORD *)AsyncContext + 5) == 590696 )
    return -2146892963;
  else
    return KsecProcessSecurityContext(
             (__int64)AsyncContext,
             (__int128 *)phCredential,
             (__int64 *)phContext,
             (__int64)pszTargetName,
             pInput,
             fContextReq,
             TargetDataRep,
             (__int128 *)phNewContext,
             (__int64)pOutput,
             pfContextAttr,
             (__int64)ptsExpiry);
}

```

## disassembly

```asm
0x180022d90  mov     r11, rsp
0x180022d93  sub     rsp, 68h
0x180022d97  test    rcx, rcx
0x180022d9a  jz      short loc_180022DFE
0x180022d9c  cmp     dword ptr [rcx+14h], 90368h
0x180022da3  jz      short loc_180022DFE
0x180022da5  mov     rax, [rsp+68h+ptsExpiry]
0x180022dad  mov     [r11-18h], rax
0x180022db1  mov     rax, [rsp+68h+pfContextAttr]
0x180022db9  mov     [r11-20h], rax
0x180022dbd  mov     rax, [rsp+68h+pOutput]
0x180022dc5  mov     [r11-28h], rax
0x180022dc9  mov     rax, [rsp+68h+phNewContext]
0x180022dd1  mov     [r11-30h], rax
0x180022dd5  mov     eax, [rsp+68h+TargetDataRep]
0x180022ddc  mov     [rsp+68h+var_38], eax
0x180022de0  mov     eax, [rsp+68h+fContextReq]
0x180022de7  mov     [rsp+68h+var_40], eax
0x180022deb  mov     rax, [rsp+68h+pInput]
0x180022df3  mov     [r11-48h], rax
0x180022df7  call    KsecProcessSecurityContext
0x180022dfc  jmp     short loc_180022E03
0x180022dfe  mov     eax, 8009035Dh
0x180022e03  add     rsp, 68h
0x180022e07  retn
```

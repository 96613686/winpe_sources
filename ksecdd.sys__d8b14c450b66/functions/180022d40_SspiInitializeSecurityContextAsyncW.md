# SspiInitializeSecurityContextAsyncW

- ea: `0x180022d40`
- end: `0x180022db9`
- name: `SspiInitializeSecurityContextAsyncW`
- size: `121`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *AsyncContext, PCredHandle phCredential, PCtxtHandle phContext, PSECURITY_STRING pszTargetName, unsigned int fContextReq, unsigned int Reserved1, unsigned int TargetDataRep, PSecBufferDesc pInput, unsigned int Reserved2, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180022d40`
- `0x1800248c0`

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
0x180022d40  mov     r11, rsp
0x180022d43  sub     rsp, 68h
0x180022d47  test    rcx, rcx
0x180022d4a  jz      short loc_180022DAE
0x180022d4c  cmp     dword ptr [rcx+14h], 90368h
0x180022d53  jz      short loc_180022DAE
0x180022d55  mov     rax, [rsp+68h+ptsExpiry]
0x180022d5d  mov     [r11-18h], rax
0x180022d61  mov     rax, [rsp+68h+pfContextAttr]
0x180022d69  mov     [r11-20h], rax
0x180022d6d  mov     rax, [rsp+68h+pOutput]
0x180022d75  mov     [r11-28h], rax
0x180022d79  mov     rax, [rsp+68h+phNewContext]
0x180022d81  mov     [r11-30h], rax
0x180022d85  mov     eax, [rsp+68h+TargetDataRep]
0x180022d8c  mov     [rsp+68h+var_38], eax
0x180022d90  mov     eax, [rsp+68h+fContextReq]
0x180022d97  mov     [rsp+68h+var_40], eax
0x180022d9b  mov     rax, [rsp+68h+pInput]
0x180022da3  mov     [r11-48h], rax
0x180022da7  call    KsecProcessSecurityContext
0x180022dac  jmp     short loc_180022DB3
0x180022dae  mov     eax, 8009035Dh
0x180022db3  add     rsp, 68h
0x180022db7  retn
```

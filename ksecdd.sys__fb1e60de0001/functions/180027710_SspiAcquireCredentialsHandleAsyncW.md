# SspiAcquireCredentialsHandleAsyncW

- ea: `0x180027710`
- end: `0x18002777f`
- name: `SspiAcquireCredentialsHandleAsyncW`
- size: `111`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *AsyncContext, PSECURITY_STRING pszPrincipal, PSECURITY_STRING pszPackage, unsigned int fCredentialUse, void *pvLogonId, void *pAuthData, SEC_GET_KEY_FN pGetKeyFn, void *pvGetKeyArgument, PCredHandle phCredential, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180027710`
- `0x180027788`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiAcquireCredentialsHandleAsyncW(
        SspiAsyncContext *AsyncContext,
        PSECURITY_STRING pszPrincipal,
        PSECURITY_STRING pszPackage,
        unsigned int fCredentialUse,
        void *pvLogonId,
        void *pAuthData,
        SEC_GET_KEY_FN pGetKeyFn,
        void *pvGetKeyArgument,
        PCredHandle phCredential,
        PTimeStamp ptsExpiry)
{
  if ( !AsyncContext || *((_DWORD *)AsyncContext + 5) == 590696 )
    return -2146892963;
  else
    return KsecAcquireCredentialsHandle(
             AsyncContext,
             pszPrincipal,
             pszPackage,
             fCredentialUse,
             pvLogonId,
             pAuthData,
             pGetKeyFn,
             pvGetKeyArgument,
             phCredential,
             ptsExpiry);
}

```

## disassembly

```asm
0x180027710  mov     r11, rsp
0x180027713  sub     rsp, 58h
0x180027717  test    rcx, rcx
0x18002771a  jz      short loc_180027778
0x18002771c  cmp     dword ptr [rcx+14h], 90368h
0x180027723  jz      short loc_180027778
0x180027725  mov     rax, [rsp+58h+ptsExpiry]
0x18002772d  mov     [r11-10h], rax
0x180027731  mov     rax, [rsp+58h+phCredential]
0x180027739  mov     [r11-18h], rax
0x18002773d  mov     rax, [rsp+58h+pvGetKeyArgument]
0x180027745  mov     [r11-20h], rax
0x180027749  mov     rax, [rsp+58h+pGetKeyFn]
0x180027751  mov     [r11-28h], rax
0x180027755  mov     rax, [rsp+58h+pAuthData]
0x18002775d  mov     [r11-30h], rax
0x180027761  mov     rax, [rsp+58h+pvLogonId]
0x180027769  mov     [r11-38h], rax
0x18002776d  call    KsecAcquireCredentialsHandle
0x180027772  add     rsp, 58h
0x180027776  retn
0x180027778  mov     eax, 8009035Dh
0x18002777d  jmp     short loc_180027772
```

# SspiAcquireCredentialsHandleAsyncW

- ea: `0x1800276c0`
- end: `0x18002772f`
- name: `SspiAcquireCredentialsHandleAsyncW`
- size: `111`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *AsyncContext, PSECURITY_STRING pszPrincipal, PSECURITY_STRING pszPackage, unsigned int fCredentialUse, void *pvLogonId, void *pAuthData, SEC_GET_KEY_FN pGetKeyFn, void *pvGetKeyArgument, PCredHandle phCredential, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800276c0`
- `0x180027738`

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
0x1800276c0  mov     r11, rsp
0x1800276c3  sub     rsp, 58h
0x1800276c7  test    rcx, rcx
0x1800276ca  jz      short loc_180027728
0x1800276cc  cmp     dword ptr [rcx+14h], 90368h
0x1800276d3  jz      short loc_180027728
0x1800276d5  mov     rax, [rsp+58h+ptsExpiry]
0x1800276dd  mov     [r11-10h], rax
0x1800276e1  mov     rax, [rsp+58h+phCredential]
0x1800276e9  mov     [r11-18h], rax
0x1800276ed  mov     rax, [rsp+58h+pvGetKeyArgument]
0x1800276f5  mov     [r11-20h], rax
0x1800276f9  mov     rax, [rsp+58h+pGetKeyFn]
0x180027701  mov     [r11-28h], rax
0x180027705  mov     rax, [rsp+58h+pAuthData]
0x18002770d  mov     [r11-30h], rax
0x180027711  mov     rax, [rsp+58h+pvLogonId]
0x180027719  mov     [r11-38h], rax
0x18002771d  call    KsecAcquireCredentialsHandle
0x180027722  add     rsp, 58h
0x180027726  retn
0x180027728  mov     eax, 8009035Dh
0x18002772d  jmp     short loc_180027722
```

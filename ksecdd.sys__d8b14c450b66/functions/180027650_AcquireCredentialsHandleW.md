# AcquireCredentialsHandleW

- ea: `0x180027650`
- end: `0x1800276ad`
- name: `AcquireCredentialsHandleW`
- size: `93`
- prototype: `SECURITY_STATUS __stdcall(PSECURITY_STRING pPrincipal, PSECURITY_STRING pPackage, unsigned int fCredentialUse, void *pvLogonId, void *pAuthData, SEC_GET_KEY_FN pGetKeyFn, void *pvGetKeyArgument, PCredHandle phCredential, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180027738`

## pseudocode

```c
SECURITY_STATUS __stdcall AcquireCredentialsHandleW(
        PSECURITY_STRING pPrincipal,
        PSECURITY_STRING pPackage,
        unsigned int fCredentialUse,
        void *pvLogonId,
        void *pAuthData,
        SEC_GET_KEY_FN pGetKeyFn,
        void *pvGetKeyArgument,
        PCredHandle phCredential,
        PTimeStamp ptsExpiry)
{
  return KsecAcquireCredentialsHandle(
           0,
           pPrincipal,
           pPackage,
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
0x180027650  mov     r11, rsp
0x180027653  sub     rsp, 58h
0x180027657  mov     rax, [rsp+58h+ptsExpiry]
0x18002765f  mov     [r11-10h], rax
0x180027663  mov     rax, [rsp+58h+phCredential]
0x18002766b  mov     [r11-18h], rax
0x18002766f  mov     rax, [rsp+58h+pvGetKeyArgument]
0x180027677  mov     [r11-20h], rax
0x18002767b  mov     rax, [rsp+58h+pGetKeyFn]
0x180027683  mov     [r11-28h], rax
0x180027687  mov     rax, [rsp+58h+pAuthData]
0x18002768f  mov     [r11-30h], rax
0x180027693  mov     [r11-38h], r9
0x180027697  mov     r9d, r8d
0x18002769a  mov     r8, rdx
0x18002769d  mov     rdx, rcx
0x1800276a0  xor     ecx, ecx
0x1800276a2  call    KsecAcquireCredentialsHandle
0x1800276a7  add     rsp, 58h
0x1800276ab  retn
```

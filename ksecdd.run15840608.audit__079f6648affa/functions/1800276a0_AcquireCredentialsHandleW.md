# AcquireCredentialsHandleW

- ea: `0x1800276a0`
- end: `0x1800276fd`
- name: `AcquireCredentialsHandleW`
- size: `93`
- prototype: `SECURITY_STATUS __stdcall(PSECURITY_STRING pPrincipal, PSECURITY_STRING pPackage, unsigned int fCredentialUse, void *pvLogonId, void *pAuthData, SEC_GET_KEY_FN pGetKeyFn, void *pvGetKeyArgument, PCredHandle phCredential, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180027788`

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
0x1800276a0  mov     r11, rsp
0x1800276a3  sub     rsp, 58h
0x1800276a7  mov     rax, [rsp+58h+ptsExpiry]
0x1800276af  mov     [r11-10h], rax
0x1800276b3  mov     rax, [rsp+58h+phCredential]
0x1800276bb  mov     [r11-18h], rax
0x1800276bf  mov     rax, [rsp+58h+pvGetKeyArgument]
0x1800276c7  mov     [r11-20h], rax
0x1800276cb  mov     rax, [rsp+58h+pGetKeyFn]
0x1800276d3  mov     [r11-28h], rax
0x1800276d7  mov     rax, [rsp+58h+pAuthData]
0x1800276df  mov     [r11-30h], rax
0x1800276e3  mov     [r11-38h], r9
0x1800276e7  mov     r9d, r8d
0x1800276ea  mov     r8, rdx
0x1800276ed  mov     rdx, rcx
0x1800276f0  xor     ecx, ecx
0x1800276f2  call    KsecAcquireCredentialsHandle
0x1800276f7  add     rsp, 58h
0x1800276fb  retn
```

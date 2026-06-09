# AddCredentialsW

- ea: `0x180021800`
- end: `0x1800218ad`
- name: `AddCredentialsW`
- size: `173`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle hCredentials, PSECURITY_STRING pPrincipal, PSECURITY_STRING pPackage, unsigned int fCredentialUse, void *pAuthData, SEC_GET_KEY_FN pGetKeyFn, void *pvGetKeyArgument, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001f9e4`
- `0x180021800`

## pseudocode

```c
SECURITY_STATUS __stdcall AddCredentialsW(
        PCredHandle hCredentials,
        PSECURITY_STRING pPrincipal,
        PSECURITY_STRING pPackage,
        unsigned int fCredentialUse,
        void *pAuthData,
        SEC_GET_KEY_FN pGetKeyFn,
        void *pvGetKeyArgument,
        PTimeStamp ptsExpiry)
{
  int v9; // r9d
  int v10; // r11d
  PTimeStamp v12; // rcx
  __int128 *v13; // r8
  char v14; // [rsp+50h] [rbp-28h] BYREF
  __int128 v15; // [rsp+58h] [rbp-20h] BYREF
  __int64 v16; // [rsp+90h] [rbp+18h] BYREF

  v9 = (int)pPackage;
  v10 = (int)hCredentials;
  v15 = 0;
  if ( !pPackage )
    return -1073741811;
  if ( !pPrincipal )
    v15 = xmmword_1800196F0;
  v12 = (PTimeStamp)&v14;
  LODWORD(v16) = 0;
  v13 = &v15;
  if ( ptsExpiry )
    v12 = ptsExpiry;
  if ( pPrincipal )
    LODWORD(v13) = (_DWORD)pPrincipal;
  return SecpAddCredentials(
           (int)v12,
           v10,
           (int)v13,
           v9,
           fCredentialUse,
           (unsigned __int8 *)pAuthData,
           (__int64)pGetKeyFn,
           (__int64)pvGetKeyArgument,
           (__int64)v12,
           (__int64)&v16);
}

```

## disassembly

```asm
0x180021800  sub     rsp, 78h
0x180021804  xorps   xmm0, xmm0
0x180021807  mov     r10d, r9d
0x18002180a  mov     r9, r8; int
0x18002180d  mov     r11, rcx
0x180021810  movups  [rsp+78h+var_20], xmm0
0x180021815  test    r8, r8
0x180021818  jnz     short loc_180021824
0x18002181a  mov     eax, 0C000000Dh
0x18002181f  jmp     loc_1800218A7
0x180021824  test    rdx, rdx
0x180021827  jnz     short loc_180021836
0x180021829  movups  xmm0, cs:xmmword_1800196F0
0x180021830  movdqu  [rsp+78h+var_20], xmm0
0x180021836  mov     rax, [rsp+78h+ptsExpiry]
0x18002183e  lea     rcx, [rsp+78h+var_28]
0x180021843  test    rax, rax
0x180021846  mov     dword ptr [rsp+78h+arg_10], 0
0x180021851  lea     r8, [rsp+78h+var_20]
0x180021856  cmovnz  rcx, rax; int
0x18002185a  test    rdx, rdx
0x18002185d  lea     rax, [rsp+78h+arg_10]
0x180021865  mov     [rsp+78h+var_30], rax; __int64
0x18002186a  cmovnz  r8, rdx; int
0x18002186e  mov     rax, [rsp+78h+pvGetKeyArgument]
0x180021876  mov     rdx, r11; int
0x180021879  mov     [rsp+78h+var_38], rcx; __int64
0x18002187e  mov     [rsp+78h+var_40], rax; __int64
0x180021883  mov     rax, [rsp+78h+pGetKeyFn]
0x18002188b  mov     [rsp+78h+var_48], rax; __int64
0x180021890  mov     rax, [rsp+78h+pAuthData]
0x180021898  mov     [rsp+78h+var_50], rax; unsigned __int8 *
0x18002189d  mov     [rsp+78h+var_58], r10d; int
0x1800218a2  call    SecpAddCredentials
0x1800218a7  add     rsp, 78h
0x1800218ab  retn
```

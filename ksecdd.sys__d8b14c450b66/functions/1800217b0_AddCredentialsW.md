# AddCredentialsW

- ea: `0x1800217b0`
- end: `0x18002185d`
- name: `AddCredentialsW`
- size: `173`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle hCredentials, PSECURITY_STRING pPrincipal, PSECURITY_STRING pPackage, unsigned int fCredentialUse, void *pAuthData, SEC_GET_KEY_FN pGetKeyFn, void *pvGetKeyArgument, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001f9e4`
- `0x1800217b0`

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
0x1800217b0  sub     rsp, 78h
0x1800217b4  xorps   xmm0, xmm0
0x1800217b7  mov     r10d, r9d
0x1800217ba  mov     r9, r8; int
0x1800217bd  mov     r11, rcx
0x1800217c0  movups  [rsp+78h+var_20], xmm0
0x1800217c5  test    r8, r8
0x1800217c8  jnz     short loc_1800217D4
0x1800217ca  mov     eax, 0C000000Dh
0x1800217cf  jmp     loc_180021857
0x1800217d4  test    rdx, rdx
0x1800217d7  jnz     short loc_1800217E6
0x1800217d9  movups  xmm0, cs:xmmword_1800196F0
0x1800217e0  movdqu  [rsp+78h+var_20], xmm0
0x1800217e6  mov     rax, [rsp+78h+ptsExpiry]
0x1800217ee  lea     rcx, [rsp+78h+var_28]
0x1800217f3  test    rax, rax
0x1800217f6  mov     dword ptr [rsp+78h+arg_10], 0
0x180021801  lea     r8, [rsp+78h+var_20]
0x180021806  cmovnz  rcx, rax; int
0x18002180a  test    rdx, rdx
0x18002180d  lea     rax, [rsp+78h+arg_10]
0x180021815  mov     [rsp+78h+var_30], rax; __int64
0x18002181a  cmovnz  r8, rdx; int
0x18002181e  mov     rax, [rsp+78h+pvGetKeyArgument]
0x180021826  mov     rdx, r11; int
0x180021829  mov     [rsp+78h+var_38], rcx; __int64
0x18002182e  mov     [rsp+78h+var_40], rax; __int64
0x180021833  mov     rax, [rsp+78h+pGetKeyFn]
0x18002183b  mov     [rsp+78h+var_48], rax; __int64
0x180021840  mov     rax, [rsp+78h+pAuthData]
0x180021848  mov     [rsp+78h+var_50], rax; unsigned __int8 *
0x18002184d  mov     [rsp+78h+var_58], r10d; int
0x180021852  call    SecpAddCredentials
0x180021857  add     rsp, 78h
0x18002185b  retn
```

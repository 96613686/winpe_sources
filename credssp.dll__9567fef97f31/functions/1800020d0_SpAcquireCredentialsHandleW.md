# SpAcquireCredentialsHandleW

- ea: `0x1800020d0`
- end: `0x18000231d`
- name: `SpAcquireCredentialsHandleW`
- size: `589`
- prototype: `SECURITY_STATUS __fastcall(LPWSTR pszPrincipal, wchar_t *String1, unsigned int fCredentialUse, void *pvLogonId, __int64, SEC_GET_KEY_FN pGetKeyFn, void *pvGetKeyArgument, __int64, SECURITY_INTEGER *ptsExpiry)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800020d0`
- `0x1800030cc`
- `0x180003e20`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180002159`
- `msvcrt!_wcsnicmp` at `0x180002159`
- `SspiCli!FreeCredentialsHandle` at `0x180002275`
- `SspiCli!FreeCredentialsHandle` at `0x1800022ce`
- `SspiCli!FreeCredentialsHandle` at `0x180002275`
- `SspiCli!FreeCredentialsHandle` at `0x1800022ce`
- `SspiCli!AcquireCredentialsHandleW` at `0x180002211`
- `SspiCli!AcquireCredentialsHandleW` at `0x180002264`
- `SspiCli!AcquireCredentialsHandleW` at `0x180002211`
- `SspiCli!AcquireCredentialsHandleW` at `0x180002264`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002285`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002285`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800022c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800022c3`

## pseudocode

```c
SECURITY_STATUS __fastcall SpAcquireCredentialsHandleW(
        LPWSTR pszPrincipal,
        wchar_t *String1,
        unsigned int fCredentialUse,
        void *pvLogonId,
        __int64 a5,
        SEC_GET_KEY_FN pGetKeyFn,
        void *pvGetKeyArgument,
        __int64 a8,
        SECURITY_INTEGER *ptsExpiry)
{
  SECURITY_STATUS result; // eax
  void *v13; // rbp
  _DWORD *pAuthData; // rbx
  int v15; // esi
  int v16; // edi
  struct _SecHandle *p_phCredential; // rcx
  HLOCAL v18; // rax
  struct _SecHandle *v19; // rsi
  struct _SecHandle phCredential; // [rsp+68h] [rbp-70h] BYREF
  struct _SecHandle v21; // [rsp+78h] [rbp-60h] BYREF

  phCredential = 0;
  v21 = 0;
  if ( _wcsnicmp(String1, L"CREDSSP", 8u) )
    return -2146893051;
  v13 = 0;
  pAuthData = 0;
  v15 = 0;
  if ( a5 )
  {
    if ( *(_DWORD *)a5 != 2 )
    {
      if ( *(_DWORD *)a5 == 4 )
      {
        pAuthData = (_DWORD *)a5;
LABEL_13:
        if ( *pAuthData == 5 )
        {
          v15 = pAuthData[13];
          pAuthData[13] = v15 | 0x1C00;
        }
        else
        {
          v15 = pAuthData[18];
          pAuthData[18] = v15 | 0x1C00;
        }
        goto LABEL_17;
      }
      if ( *(_DWORD *)a5 != 13 )
      {
        if ( *(_DWORD *)a5 == 100 )
        {
          pAuthData = *(_DWORD **)(a5 + 24);
          v13 = (void *)a5;
        }
        else
        {
          v13 = *(void **)(a5 + 16);
          pAuthData = *(_DWORD **)(a5 + 8);
        }
        if ( !pAuthData )
          goto LABEL_17;
        goto LABEL_13;
      }
    }
    v13 = (void *)a5;
  }
LABEL_17:
  result = AcquireCredentialsHandleW(
             pszPrincipal,
             (LPWSTR)L"Schannel",
             fCredentialUse,
             pvLogonId,
             pAuthData,
             pGetKeyFn,
             pvGetKeyArgument,
             &phCredential,
             ptsExpiry);
  if ( pAuthData )
  {
    if ( *pAuthData == 5 )
      pAuthData[13] = v15;
    else
      pAuthData[18] = v15;
  }
  if ( result >= 0 )
  {
    v16 = AcquireCredentialsHandleW(
            pszPrincipal,
            (LPWSTR)L"TSSSP",
            fCredentialUse,
            pvLogonId,
            v13,
            pGetKeyFn,
            pvGetKeyArgument,
            &v21,
            ptsExpiry);
    if ( v16 >= 0 )
    {
      v18 = LocalAlloc(0x40u, 0x30u);
      v19 = (struct _SecHandle *)v18;
      if ( v18 )
      {
        if ( (fCredentialUse & 1) == 0
          || (v16 = -2146892963, pAuthData)
          && (v16 = CredSSPGetCert((__int64)pAuthData, (_QWORD *)v18 + 5, (unsigned int *)v18 + 8), v16 >= 0) )
        {
          *v19 = phCredential;
          v19[1] = v21;
          *(_QWORD *)(a8 + 8) = v19;
          return v16;
        }
        LocalFree(v19);
      }
      else
      {
        v16 = -2146893056;
      }
      FreeCredentialsHandle(&phCredential);
      p_phCredential = &v21;
    }
    else
    {
      p_phCredential = &phCredential;
    }
    FreeCredentialsHandle(p_phCredential);
    return v16;
  }
  return result;
}

```

## disassembly

```asm
0x1800020d0  push    rbx
0x1800020d2  push    rbp
0x1800020d3  push    rsi
0x1800020d4  push    rdi
0x1800020d5  push    r12
0x1800020d7  push    r13
0x1800020d9  push    r14
0x1800020db  push    r15
0x1800020dd  sub     rsp, 98h
0x1800020e4  mov     rax, cs:__security_cookie
0x1800020eb  xor     rax, rsp
0x1800020ee  mov     [rsp+0D8h+var_50], rax
0x1800020f6  mov     rdi, [rsp+0D8h+arg_20]
0x1800020fe  mov     r15, rcx
0x180002101  mov     rcx, [rsp+0D8h+arg_30]
0x180002109  mov     rax, rdx
0x18000210c  mov     r13, [rsp+0D8h+arg_28]
0x180002114  lea     rdx, aCredssp; "CREDSSP"
0x18000211b  mov     [rsp+0D8h+var_80], rcx
0x180002120  mov     r14d, r8d
0x180002123  mov     rcx, [rsp+0D8h+arg_38]
0x18000212b  xorps   xmm0, xmm0
0x18000212e  mov     [rsp+0D8h+var_78], rcx
0x180002133  xorps   xmm1, xmm1
0x180002136  mov     rcx, [rsp+0D8h+arg_40]
0x18000213e  mov     r8d, 8; MaxCount
0x180002144  mov     [rsp+0D8h+var_88], rcx
0x180002149  mov     r12, r9
0x18000214c  mov     rcx, rax; String1
0x18000214f  movups  xmmword ptr [rsp+0D8h+var_70.dwLower], xmm0
0x180002154  movups  xmmword ptr [rsp+0D8h+var_60.dwLower], xmm1
0x180002159  call    cs:__imp__wcsnicmp
0x18000215f  test    eax, eax
0x180002161  jz      short loc_18000216D
0x180002163  mov     eax, 80090305h
0x180002168  jmp     loc_1800022F9
0x18000216d  xor     ebp, ebp
0x18000216f  xor     ebx, ebx
0x180002171  xor     esi, esi
0x180002173  test    rdi, rdi
0x180002176  jz      short loc_1800021D9
0x180002178  mov     ecx, [rdi]
0x18000217a  sub     ecx, 2
0x18000217d  jz      short loc_1800021D6
0x18000217f  sub     ecx, 2
0x180002182  jz      short loc_1800021B0
0x180002184  sub     ecx, 9
0x180002187  jz      short loc_1800021D6
0x180002189  sub     ecx, 25h ; '%'
0x18000218c  jz      short loc_1800021A1
0x18000218e  sub     ecx, 1
0x180002191  jz      short loc_1800021A1
0x180002193  cmp     ecx, 31h ; '1'
0x180002196  jnz     short loc_1800021A1
0x180002198  mov     rbx, [rdi+18h]
0x18000219c  mov     rbp, rdi
0x18000219f  jmp     short loc_1800021A9
0x1800021a1  mov     rbp, [rdi+10h]
0x1800021a5  mov     rbx, [rdi+8]
0x1800021a9  test    rbx, rbx
0x1800021ac  jz      short loc_1800021D9
0x1800021ae  jmp     short loc_1800021B3
0x1800021b0  mov     rbx, rdi
0x1800021b3  cmp     dword ptr [rbx], 5
0x1800021b6  jnz     short loc_1800021C7
0x1800021b8  mov     esi, [rbx+34h]
0x1800021bb  mov     eax, esi
0x1800021bd  or      eax, 1C00h
0x1800021c2  mov     [rbx+34h], eax
0x1800021c5  jmp     short loc_1800021D9
0x1800021c7  mov     esi, [rbx+48h]
0x1800021ca  mov     eax, esi
0x1800021cc  or      eax, 1C00h
0x1800021d1  mov     [rbx+48h], eax
0x1800021d4  jmp     short loc_1800021D9
0x1800021d6  mov     rbp, rdi
0x1800021d9  mov     rax, [rsp+0D8h+var_88]
0x1800021de  lea     rdx, pszPackageName; "Schannel"
0x1800021e5  mov     rdi, [rsp+0D8h+var_80]
0x1800021ea  mov     r9, r12; pvLogonId
0x1800021ed  mov     [rsp+0D8h+ptsExpiry], rax; ptsExpiry
0x1800021f2  mov     r8d, r14d; fCredentialUse
0x1800021f5  lea     rax, [rsp+0D8h+var_70]
0x1800021fa  mov     rcx, r15; pszPrincipal
0x1800021fd  mov     [rsp+0D8h+phCredential], rax; phCredential
0x180002202  mov     [rsp+0D8h+pvGetKeyArgument], rdi; pvGetKeyArgument
0x180002207  mov     [rsp+0D8h+pGetKeyFn], r13; pGetKeyFn
0x18000220c  mov     [rsp+0D8h+pAuthData], rbx; pAuthData
0x180002211  call    cs:__imp_AcquireCredentialsHandleW
0x180002217  test    rbx, rbx
0x18000221a  jz      short loc_180002229
0x18000221c  cmp     dword ptr [rbx], 5
0x18000221f  jnz     short loc_180002226
0x180002221  mov     [rbx+34h], esi
0x180002224  jmp     short loc_180002229
0x180002226  mov     [rbx+48h], esi
0x180002229  test    eax, eax
0x18000222b  js      loc_1800022F9
0x180002231  mov     rax, [rsp+0D8h+var_88]
0x180002236  lea     rdx, aTsssp; "TSSSP"
0x18000223d  mov     [rsp+0D8h+ptsExpiry], rax; ptsExpiry
0x180002242  mov     r9, r12; pvLogonId
0x180002245  lea     rax, [rsp+0D8h+var_60]
0x18000224a  mov     r8d, r14d; fCredentialUse
0x18000224d  mov     [rsp+0D8h+phCredential], rax; phCredential
0x180002252  mov     rcx, r15; pszPrincipal
0x180002255  mov     [rsp+0D8h+pvGetKeyArgument], rdi; pvGetKeyArgument
0x18000225a  mov     [rsp+0D8h+pGetKeyFn], r13; pGetKeyFn
0x18000225f  mov     [rsp+0D8h+pAuthData], rbp; pAuthData
0x180002264  call    cs:__imp_AcquireCredentialsHandleW
0x18000226a  mov     edi, eax
0x18000226c  test    eax, eax
0x18000226e  jns     short loc_18000227D
0x180002270  lea     rcx, [rsp+0D8h+var_70]; phCredential
0x180002275  call    cs:__imp_FreeCredentialsHandle
0x18000227b  jmp     short loc_1800022F7
0x18000227d  mov     edx, 30h ; '0'; uBytes
0x180002282  lea     ecx, [rdx+10h]; uFlags
0x180002285  call    cs:__imp_LocalAlloc
0x18000228b  mov     rsi, rax
0x18000228e  test    rax, rax
0x180002291  jnz     short loc_18000229A
0x180002293  mov     edi, 80090300h
0x180002298  jmp     short loc_1800022C9
0x18000229a  test    r14b, 1
0x18000229e  jz      short loc_1800022DB
0x1800022a0  mov     edi, 8009035Dh
0x1800022a5  test    rbx, rbx
0x1800022a8  jz      short loc_1800022C0
0x1800022aa  lea     r8, [rax+20h]
0x1800022ae  mov     rcx, rbx
0x1800022b1  lea     rdx, [rax+28h]
0x1800022b5  call    CredSSPGetCert
0x1800022ba  mov     edi, eax
0x1800022bc  test    eax, eax
0x1800022be  jns     short loc_1800022DB
0x1800022c0  mov     rcx, rsi; hMem
0x1800022c3  call    cs:__imp_LocalFree
0x1800022c9  lea     rcx, [rsp+0D8h+var_70]; phCredential
0x1800022ce  call    cs:__imp_FreeCredentialsHandle
0x1800022d4  lea     rcx, [rsp+0D8h+var_60]
0x1800022d9  jmp     short loc_180002275
0x1800022db  movups  xmm0, xmmword ptr [rsp+0D8h+var_70.dwLower]
0x1800022e0  mov     rax, [rsp+0D8h+var_78]
0x1800022e5  movdqu  xmmword ptr [rsi], xmm0
0x1800022e9  movups  xmm1, xmmword ptr [rsp+0D8h+var_60.dwLower]
0x1800022ee  movdqu  xmmword ptr [rsi+10h], xmm1
0x1800022f3  mov     [rax+8], rsi
0x1800022f7  mov     eax, edi
0x1800022f9  mov     rcx, [rsp+0D8h+var_50]
0x180002301  xor     rcx, rsp; StackCookie
0x180002304  call    __security_check_cookie
0x180002309  add     rsp, 98h
0x180002310  pop     r15
0x180002312  pop     r14
0x180002314  pop     r13
0x180002316  pop     r12
0x180002318  pop     rdi
0x180002319  pop     rsi
0x18000231a  pop     rbp
0x18000231b  pop     rbx
0x18000231c  retn
```

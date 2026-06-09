# AEUpdateDsOIDInfoCache

- ea: `0x180006ecc`
- end: `0x180006f72`
- name: `AEUpdateDsOIDInfoCache`
- size: `166`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003d10`

## callees

- `0x180003ac0`
- `0x180006ecc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f2c`
- `CRYPT32!CryptMemFree` at `0x180006f54`
- `CRYPT32!CryptMemFree` at `0x180006f54`
- `CRYPTNET!CryptRetrieveObjectByUrlW` at `0x180006f22`
- `CRYPTNET!CryptRetrieveObjectByUrlW` at `0x180006f22`
- `certca!__imp_CAOIDGetLdapURL` at `0x180006ee7`
- `certca!__imp_CAOIDGetLdapURL` at `0x180006ee7`
- `certca!__imp_CAOIDFreeLdapURL` at `0x180006f64`
- `certca!__imp_CAOIDFreeLdapURL` at `0x180006f64`

## pseudocode

```c
__int64 AEUpdateDsOIDInfoCache()
{
  unsigned int v0; // ebx
  DWORD LastError; // eax
  LPVOID pv; // [rsp+60h] [rbp+8h] BYREF
  LPCWSTR pszUrl; // [rsp+68h] [rbp+10h] BYREF

  v0 = 0;
  pv = 0;
  pszUrl = 0;
  if ( !(unsigned int)CAOIDGetLdapURL(0, 0, &pszUrl) )
  {
    if ( CryptRetrieveObjectByUrlW(pszUrl, 0, 0x1C00Du, 0x2710u, &pv, 0, 0, 0, 0)
      || (LastError = GetLastError(), LastError == 2)
      || LastError == -2146885628 )
    {
      v0 = I_CryptSetDsOIDInfoCache((__int64)pv);
    }
  }
  if ( pv )
    CryptMemFree(pv);
  if ( pszUrl )
    CAOIDFreeLdapURL();
  return v0;
}

```

## disassembly

```asm
0x180006ecc  push    rbx
0x180006ece  sub     rsp, 50h
0x180006ed2  xor     ebx, ebx
0x180006ed4  lea     r8, [rsp+58h+pszUrl]
0x180006ed9  xor     edx, edx
0x180006edb  mov     [rsp+58h+pv], rbx
0x180006ee0  xor     ecx, ecx
0x180006ee2  mov     [rsp+58h+pszUrl], rbx
0x180006ee7  call    cs:__imp_CAOIDGetLdapURL
0x180006eed  test    eax, eax
0x180006eef  jnz     short loc_180006F4A
0x180006ef1  mov     rcx, [rsp+58h+pszUrl]; pszUrl
0x180006ef6  lea     rax, [rsp+58h+pv]
0x180006efb  mov     [rsp+58h+pAuxInfo], rbx; pAuxInfo
0x180006f00  xor     edx, edx; pszObjectOid
0x180006f02  mov     [rsp+58h+pvVerify], rbx; pvVerify
0x180006f07  mov     r9d, 2710h; dwTimeout
0x180006f0d  mov     [rsp+58h+pCredentials], rbx; pCredentials
0x180006f12  mov     r8d, 1C00Dh; dwRetrievalFlags
0x180006f18  mov     [rsp+58h+hAsyncRetrieve], rbx; hAsyncRetrieve
0x180006f1d  mov     [rsp+58h+ppvObject], rax; ppvObject
0x180006f22  call    cs:__imp_CryptRetrieveObjectByUrlW
0x180006f28  test    eax, eax
0x180006f2a  jnz     short loc_180006F3E
0x180006f2c  call    cs:__imp_GetLastError
0x180006f32  cmp     eax, 2
0x180006f35  jz      short loc_180006F3E
0x180006f37  cmp     eax, 80092004h
0x180006f3c  jnz     short loc_180006F4A
0x180006f3e  mov     rcx, [rsp+58h+pv]
0x180006f43  call    I_CryptSetDsOIDInfoCache
0x180006f48  mov     ebx, eax
0x180006f4a  mov     rcx, [rsp+58h+pv]; pv
0x180006f4f  test    rcx, rcx
0x180006f52  jz      short loc_180006F5A
0x180006f54  call    cs:__imp_CryptMemFree
0x180006f5a  mov     rcx, [rsp+58h+pszUrl]
0x180006f5f  test    rcx, rcx
0x180006f62  jz      short loc_180006F6A
0x180006f64  call    cs:__imp_CAOIDFreeLdapURL
0x180006f6a  mov     eax, ebx
0x180006f6c  add     rsp, 50h
0x180006f70  pop     rbx
0x180006f71  retn
```

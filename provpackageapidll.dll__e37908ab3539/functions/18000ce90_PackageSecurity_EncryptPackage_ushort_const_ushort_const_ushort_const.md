# PackageSecurity::EncryptPackage(ushort const *,ushort const *,ushort const *)

- ea: `0x18000ce90`
- end: `0x18000ceed`
- name: `?EncryptPackage@PackageSecurity@@EEAAJPEBG00@Z`
- size: `93`
- prototype: `__int64 __fastcall(PackageSecurity *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006014`
- `0x18000b7b0`
- `0x18000ce90`

## string_xrefs

- `0x18000cead`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000ceb4`: `PackageSecurity::EncryptPackage`

## pseudocode

```c
__int64 __fastcall PackageSecurity::EncryptPackage(
        PackageSecurity *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  __int64 v6; // [rsp+20h] [rbp-18h]
  int v7; // [rsp+28h] [rbp-10h]

  result = PackageSecurity::CryptWrapper(this, a2, a3, a4, 1);
  v5 = result;
  if ( (int)result < 0 )
  {
    v7 = result;
    LODWORD(v6) = 304;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::EncryptPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      v6,
      v7);
    ProvPackageLog(3, L"    Failed to encrypt package");
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000ce90  push    rbx
0x18000ce92  sub     rsp, 30h
0x18000ce96  mov     dword ptr [rsp+38h+var_18], 1; int
0x18000ce9e  call    ?CryptWrapper@PackageSecurity@@AEAAJPEBG00H@Z; PackageSecurity::CryptWrapper(ushort const *,ushort const *,ushort const *,int)
0x18000cea3  mov     ebx, eax
0x18000cea5  test    eax, eax
0x18000cea7  jns     short loc_18000CEE7
0x18000cea9  mov     [rsp+38h+var_10], eax
0x18000cead  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000ceb4  lea     r8, aPackagesecurit_1; "PackageSecurity::EncryptPackage"
0x18000cebb  mov     dword ptr [rsp+38h+var_18], 130h
0x18000cec3  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000ceca  mov     ecx, 3
0x18000cecf  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000ced4  lea     rdx, aFailedToEncryp; "    Failed to encrypt package"
0x18000cedb  mov     ecx, 3
0x18000cee0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000cee5  mov     eax, ebx
0x18000cee7  add     rsp, 30h
0x18000ceeb  pop     rbx
0x18000ceec  retn
```

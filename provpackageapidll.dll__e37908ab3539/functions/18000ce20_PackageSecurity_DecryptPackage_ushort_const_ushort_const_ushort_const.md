# PackageSecurity::DecryptPackage(ushort const *,ushort const *,ushort const *)

- ea: `0x18000ce20`
- end: `0x18000ce7d`
- name: `?DecryptPackage@PackageSecurity@@EEAAJPEBG00@Z`
- size: `93`
- prototype: `__int64 __fastcall(PackageSecurity *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006014`
- `0x18000b7b0`
- `0x18000ce20`

## string_xrefs

- `0x18000ce3d`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000ce44`: `PackageSecurity::DecryptPackage`

## pseudocode

```c
__int64 __fastcall PackageSecurity::DecryptPackage(
        PackageSecurity *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  __int64 v6; // [rsp+20h] [rbp-18h]
  int v7; // [rsp+28h] [rbp-10h]

  result = PackageSecurity::CryptWrapper(this, a2, a3, a4, 0);
  v5 = result;
  if ( (int)result < 0 )
  {
    v7 = result;
    LODWORD(v6) = 318;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::DecryptPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      v6,
      v7);
    ProvPackageLog(3, L"    Failed to decrypt package");
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000ce20  push    rbx
0x18000ce22  sub     rsp, 30h
0x18000ce26  mov     dword ptr [rsp+38h+var_18], 0; int
0x18000ce2e  call    ?CryptWrapper@PackageSecurity@@AEAAJPEBG00H@Z; PackageSecurity::CryptWrapper(ushort const *,ushort const *,ushort const *,int)
0x18000ce33  mov     ebx, eax
0x18000ce35  test    eax, eax
0x18000ce37  jns     short loc_18000CE77
0x18000ce39  mov     [rsp+38h+var_10], eax
0x18000ce3d  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000ce44  lea     r8, aPackagesecurit_2; "PackageSecurity::DecryptPackage"
0x18000ce4b  mov     dword ptr [rsp+38h+var_18], 13Eh
0x18000ce53  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000ce5a  mov     ecx, 3
0x18000ce5f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000ce64  lea     rdx, aFailedToDecryp_0; "    Failed to decrypt package"
0x18000ce6b  mov     ecx, 3
0x18000ce70  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000ce75  mov     eax, ebx
0x18000ce77  add     rsp, 30h
0x18000ce7b  pop     rbx
0x18000ce7c  retn
```

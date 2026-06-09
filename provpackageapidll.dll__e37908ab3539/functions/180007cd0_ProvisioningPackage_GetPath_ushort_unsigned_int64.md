# ProvisioningPackage::GetPath(ushort *,unsigned __int64)

- ea: `0x180007cd0`
- end: `0x180007d3b`
- name: `?GetPath@ProvisioningPackage@@EEAAJPEAG_K@Z`
- size: `107`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, reparse_path, installer_update`

## callees

- `0x180006014`
- `0x180007cd0`
- `0x18000f040`

## string_xrefs

- `0x180007d02`: `ProvisioningPackage::GetPath`
- `0x180007d22`: `    Failed to copy path string`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::GetPath(
        const unsigned __int16 **this,
        unsigned __int16 *a2,
        unsigned __int64 a3)
{
  __int64 result; // rax
  unsigned int v4; // ebx
  int v5; // [rsp+20h] [rbp-18h]
  int v6; // [rsp+28h] [rbp-10h]

  result = PathCchCanonicalizeEx(a2, a3, this[3], PATHCCH_ALLOW_LONG_PATHS);
  v4 = result;
  if ( (int)result < 0 )
  {
    v6 = result;
    v5 = 422;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetPath",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v5,
      v6);
    ProvPackageLog(3, L"    Failed to copy path string");
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180007cd0  push    rbx
0x180007cd2  sub     rsp, 30h
0x180007cd6  mov     rax, r8
0x180007cd9  mov     r10, rdx
0x180007cdc  mov     r8, [rcx+18h]; unsigned __int16 *
0x180007ce0  mov     rdx, rax; unsigned __int64
0x180007ce3  mov     rcx, r10; unsigned __int16 *
0x180007ce6  mov     r9d, 1; enum PATHCCH_OPTIONS
0x180007cec  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x180007cf1  mov     ebx, eax
0x180007cf3  test    eax, eax
0x180007cf5  jns     short loc_180007D35
0x180007cf7  mov     [rsp+38h+var_10], eax
0x180007cfb  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007d02  lea     r8, aProvisioningpa_10; "ProvisioningPackage::GetPath"
0x180007d09  mov     [rsp+38h+var_18], 1A6h
0x180007d11  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007d18  mov     ecx, 3
0x180007d1d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007d22  lea     rdx, aFailedToCopyPa_2; "    Failed to copy path string"
0x180007d29  mov     ecx, 3
0x180007d2e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007d33  mov     eax, ebx
0x180007d35  add     rsp, 30h
0x180007d39  pop     rbx
0x180007d3a  retn
```

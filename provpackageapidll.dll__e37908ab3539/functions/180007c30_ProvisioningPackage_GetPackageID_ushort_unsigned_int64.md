# ProvisioningPackage::GetPackageID(ushort *,unsigned __int64)

- ea: `0x180007c30`
- end: `0x180007cc0`
- name: `?GetPackageID@ProvisioningPackage@@EEAAJPEAG_K@Z`
- size: `144`
- prototype: `__int64 __fastcall(ProvisioningPackage *this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180005424`
- `0x180006014`
- `0x180006648`
- `0x180007c30`

## string_xrefs

- `0x180007ca5`: `    Failed to copy string`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::GetPackageID(
        ProvisioningPackage *this,
        unsigned __int16 *a2,
        unsigned __int64 a3)
{
  __int64 v5; // rax
  __int64 result; // rax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-18h]
  int v9; // [rsp+28h] [rbp-10h]
  unsigned __int16 *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = L"PACKAGEID";
  v5 = std::map<unsigned short const *,std::wstring,stringCompare,std::allocator<std::pair<unsigned short const * const,std::wstring>>>::operator[](
         (__int64 *)this + 5,
         &v10);
  if ( *(_QWORD *)(v5 + 24) > 7u )
    v5 = *(_QWORD *)v5;
  result = StringCchCopyW(a2, a3, (const unsigned __int16 *)v5);
  v7 = result;
  if ( (int)result < 0 )
  {
    v9 = result;
    v8 = 522;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetPackageID",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v8,
      v9);
    ProvPackageLog(3, L"    Failed to copy string");
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180007c30  mov     [rsp+arg_8], rbx
0x180007c35  push    rdi
0x180007c36  sub     rsp, 30h
0x180007c3a  mov     rdi, rdx
0x180007c3d  lea     rax, aPackageid; "PACKAGEID"
0x180007c44  lea     rdx, [rsp+38h+arg_0]
0x180007c49  mov     [rsp+38h+arg_0], rax
0x180007c4e  add     rcx, 28h ; '('
0x180007c52  mov     rbx, r8
0x180007c55  call    ??A?$map@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAPEBG@Z; std::map<ushort const *,std::wstring,stringCompare,std::allocator<std::pair<ushort const * const,std::wstring>>>::operator[](ushort const * &&)
0x180007c5a  cmp     qword ptr [rax+18h], 7
0x180007c5f  jbe     short loc_180007C64
0x180007c61  mov     rax, [rax]
0x180007c64  mov     r8, rax; unsigned __int16 *
0x180007c67  mov     rdx, rbx; unsigned __int64
0x180007c6a  mov     rcx, rdi; unsigned __int16 *
0x180007c6d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007c72  mov     ebx, eax
0x180007c74  test    eax, eax
0x180007c76  jns     short loc_180007CB5
0x180007c78  mov     [rsp+38h+var_10], eax
0x180007c7c  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007c83  mov     edi, 3
0x180007c88  mov     [rsp+38h+var_18], 20Ah
0x180007c90  mov     ecx, edi
0x180007c92  lea     r8, aProvisioningpa_6; "ProvisioningPackage::GetPackageID"
0x180007c99  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007ca0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007ca5  lea     rdx, aFailedToCopySt; "    Failed to copy string"
0x180007cac  mov     ecx, edi
0x180007cae  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007cb3  mov     eax, ebx
0x180007cb5  mov     rbx, [rsp+38h+arg_8]
0x180007cba  add     rsp, 30h
0x180007cbe  pop     rdi
0x180007cbf  retn
```

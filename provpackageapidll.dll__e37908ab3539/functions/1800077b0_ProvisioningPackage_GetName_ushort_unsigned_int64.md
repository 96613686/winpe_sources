# ProvisioningPackage::GetName(ushort *,unsigned __int64)

- ea: `0x1800077b0`
- end: `0x180007840`
- name: `?GetName@ProvisioningPackage@@EEAAJPEAG_K@Z`
- size: `144`
- prototype: `__int64 __fastcall(ProvisioningPackage *this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180005424`
- `0x180006014`
- `0x180006648`
- `0x1800077b0`

## string_xrefs

- `0x180007825`: `    Failed to copy string`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::GetName(ProvisioningPackage *this, unsigned __int16 *a2, unsigned __int64 a3)
{
  __int64 v5; // rax
  __int64 result; // rax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-18h]
  int v9; // [rsp+28h] [rbp-10h]
  unsigned __int16 *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = L"NAME";
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
    v8 = 431;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetName",
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
0x1800077b0  mov     [rsp+arg_8], rbx
0x1800077b5  push    rdi
0x1800077b6  sub     rsp, 30h
0x1800077ba  mov     rdi, rdx
0x1800077bd  lea     rax, aName; "NAME"
0x1800077c4  lea     rdx, [rsp+38h+arg_0]
0x1800077c9  mov     [rsp+38h+arg_0], rax
0x1800077ce  add     rcx, 28h ; '('
0x1800077d2  mov     rbx, r8
0x1800077d5  call    ??A?$map@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAPEBG@Z; std::map<ushort const *,std::wstring,stringCompare,std::allocator<std::pair<ushort const * const,std::wstring>>>::operator[](ushort const * &&)
0x1800077da  cmp     qword ptr [rax+18h], 7
0x1800077df  jbe     short loc_1800077E4
0x1800077e1  mov     rax, [rax]
0x1800077e4  mov     r8, rax; unsigned __int16 *
0x1800077e7  mov     rdx, rbx; unsigned __int64
0x1800077ea  mov     rcx, rdi; unsigned __int16 *
0x1800077ed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800077f2  mov     ebx, eax
0x1800077f4  test    eax, eax
0x1800077f6  jns     short loc_180007835
0x1800077f8  mov     [rsp+38h+var_10], eax
0x1800077fc  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007803  mov     edi, 3
0x180007808  mov     [rsp+38h+var_18], 1AFh
0x180007810  mov     ecx, edi
0x180007812  lea     r8, aProvisioningpa_15; "ProvisioningPackage::GetName"
0x180007819  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007820  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007825  lea     rdx, aFailedToCopySt; "    Failed to copy string"
0x18000782c  mov     ecx, edi
0x18000782e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007833  mov     eax, ebx
0x180007835  mov     rbx, [rsp+38h+arg_8]
0x18000783a  add     rsp, 30h
0x18000783e  pop     rdi
0x18000783f  retn
```

# ProvisioningPackage::GetAuthor(ushort *,unsigned __int64)

- ea: `0x180007370`
- end: `0x180007400`
- name: `?GetAuthor@ProvisioningPackage@@EEAAJPEAG_K@Z`
- size: `144`
- prototype: `__int64 __fastcall(ProvisioningPackage *this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180005424`
- `0x180006014`
- `0x180006648`
- `0x180007370`

## string_xrefs

- `0x1800073e5`: `    Failed to copy string`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::GetAuthor(ProvisioningPackage *this, unsigned __int16 *a2, unsigned __int64 a3)
{
  __int64 v5; // rax
  __int64 result; // rax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-18h]
  int v9; // [rsp+28h] [rbp-10h]
  unsigned __int16 *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = L"AUTHOR";
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
    v8 = 458;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetAuthor",
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
0x180007370  mov     [rsp+arg_8], rbx
0x180007375  push    rdi
0x180007376  sub     rsp, 30h
0x18000737a  mov     rdi, rdx
0x18000737d  lea     rax, aAuthor_0; "AUTHOR"
0x180007384  lea     rdx, [rsp+38h+arg_0]
0x180007389  mov     [rsp+38h+arg_0], rax
0x18000738e  add     rcx, 28h ; '('
0x180007392  mov     rbx, r8
0x180007395  call    ??A?$map@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAPEBG@Z; std::map<ushort const *,std::wstring,stringCompare,std::allocator<std::pair<ushort const * const,std::wstring>>>::operator[](ushort const * &&)
0x18000739a  cmp     qword ptr [rax+18h], 7
0x18000739f  jbe     short loc_1800073A4
0x1800073a1  mov     rax, [rax]
0x1800073a4  mov     r8, rax; unsigned __int16 *
0x1800073a7  mov     rdx, rbx; unsigned __int64
0x1800073aa  mov     rcx, rdi; unsigned __int16 *
0x1800073ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800073b2  mov     ebx, eax
0x1800073b4  test    eax, eax
0x1800073b6  jns     short loc_1800073F5
0x1800073b8  mov     [rsp+38h+var_10], eax
0x1800073bc  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800073c3  mov     edi, 3
0x1800073c8  mov     [rsp+38h+var_18], 1CAh
0x1800073d0  mov     ecx, edi
0x1800073d2  lea     r8, aProvisioningpa_0; "ProvisioningPackage::GetAuthor"
0x1800073d9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800073e0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800073e5  lea     rdx, aFailedToCopySt; "    Failed to copy string"
0x1800073ec  mov     ecx, edi
0x1800073ee  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800073f3  mov     eax, ebx
0x1800073f5  mov     rbx, [rsp+38h+arg_8]
0x1800073fa  add     rsp, 30h
0x1800073fe  pop     rdi
0x1800073ff  retn
```

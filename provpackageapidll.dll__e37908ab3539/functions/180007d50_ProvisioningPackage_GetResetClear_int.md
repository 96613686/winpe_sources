# ProvisioningPackage::GetResetClear(int *)

- ea: `0x180007d50`
- end: `0x180007ed1`
- name: `?GetResetClear@ProvisioningPackage@@EEAAJPEAH@Z`
- size: `385`
- prototype: `__int64 __fastcall(ProvisioningPackage *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180006014`
- `0x180006648`
- `0x180007d50`

## string_xrefs

- `0x180007e05`: `    Failed to copy string`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::GetResetClear(ProvisioningPackage *this, int *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // rcx
  _WORD *v5; // r8
  __int64 v6; // rdx
  _WORD *v7; // rcx
  unsigned int v8; // edi
  __int64 v9; // rax
  _WORD v11[4]; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 *v12; // [rsp+50h] [rbp+18h] BYREF

  v12 = L"RESETCLEAR";
  v3 = (_QWORD *)std::map<unsigned short const *,std::wstring,stringCompare,std::allocator<std::pair<unsigned short const * const,std::wstring>>>::operator[](
                   (__int64 *)this + 5,
                   &v12);
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  v4 = 2147483646;
  v5 = v11;
  v6 = 2;
  do
  {
    if ( !v4 )
      break;
    if ( !*(_WORD *)v3 )
      break;
    *v5 = *(_WORD *)v3;
    v3 = (_QWORD *)((char *)v3 + 2);
    ++v5;
    --v4;
    --v6;
  }
  while ( v6 );
  v7 = v5 - 1;
  v8 = v6 == 0 ? 0x8007007A : 0;
  if ( v6 )
    v7 = v5;
  *v7 = 0;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v11[v9] );
    if ( v9 == 1 )
    {
      if ( v11[0] == 48 )
      {
        *a2 = 0;
      }
      else
      {
        if ( v11[0] != 49 )
        {
          v8 = -2147023092;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "ProvisioningPackage::GetResetClear",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
            515,
            -2147023092);
          ProvPackageLog(3, L"    Reset clear has unknown value");
          return v8;
        }
        *a2 = 1;
      }
      return 0;
    }
    v8 = -2147023092;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetResetClear",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      500,
      -2147023092);
    ProvPackageLog(3, L"    Reset clear out of range");
  }
  else
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetResetClear",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      496,
      -2147024774);
    ProvPackageLog(3, L"    Failed to copy string");
  }
  return v8;
}

```

## disassembly

```asm
0x180007d50  mov     [rsp+arg_8], rbx
0x180007d55  push    rdi
0x180007d56  sub     rsp, 30h
0x180007d5a  mov     rbx, rdx
0x180007d5d  lea     rax, aResetclear; "RESETCLEAR"
0x180007d64  lea     rdx, [rsp+38h+arg_10]
0x180007d69  mov     [rsp+38h+arg_10], rax
0x180007d6e  add     rcx, 28h ; '('
0x180007d72  call    ??A?$map@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAPEBG@Z; std::map<ushort const *,std::wstring,stringCompare,std::allocator<std::pair<ushort const * const,std::wstring>>>::operator[](ushort const * &&)
0x180007d77  cmp     qword ptr [rax+18h], 7
0x180007d7c  jbe     short loc_180007D81
0x180007d7e  mov     rax, [rax]
0x180007d81  mov     ecx, 7FFFFFFEh
0x180007d86  lea     r8, [rsp+38h+arg_0]
0x180007d8b  mov     edx, 2
0x180007d90  xor     r10d, r10d
0x180007d93  test    rcx, rcx
0x180007d96  jz      short loc_180007DB7
0x180007d98  movzx   r9d, word ptr [rax]
0x180007d9c  test    r9w, r9w
0x180007da0  jz      short loc_180007DB7
0x180007da2  mov     [r8], r9w
0x180007da6  add     rax, 2
0x180007daa  add     r8, 2
0x180007dae  dec     rcx
0x180007db1  sub     rdx, 1
0x180007db5  jnz     short loc_180007D93
0x180007db7  mov     rax, rdx
0x180007dba  lea     rcx, [r8-2]
0x180007dbe  neg     rax
0x180007dc1  sbb     edi, edi
0x180007dc3  not     edi
0x180007dc5  and     edi, 8007007Ah
0x180007dcb  test    rdx, rdx
0x180007dce  cmovnz  rcx, r8
0x180007dd2  mov     [rcx], r10w
0x180007dd6  jnz     short loc_180007E11
0x180007dd8  mov     ebx, 3
0x180007ddd  mov     [rsp+38h+var_10], edi
0x180007de1  mov     ecx, ebx
0x180007de3  mov     [rsp+38h+var_18], 1F0h
0x180007deb  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007df2  lea     r8, aProvisioningpa; "ProvisioningPackage::GetResetClear"
0x180007df9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007e00  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007e05  lea     rdx, aFailedToCopySt; "    Failed to copy string"
0x180007e0c  jmp     loc_180007EBD
0x180007e11  lea     rcx, [rsp+38h+arg_0]
0x180007e16  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007e1a  inc     rax
0x180007e1d  cmp     [rcx+rax*2], r10w
0x180007e22  jnz     short loc_180007E1A
0x180007e24  cmp     rax, 1
0x180007e28  jz      short loc_180007E65
0x180007e2a  mov     edi, 8007070Ch
0x180007e2f  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007e36  mov     ebx, 3
0x180007e3b  mov     [rsp+38h+var_10], edi
0x180007e3f  mov     ecx, ebx
0x180007e41  mov     [rsp+38h+var_18], 1F4h
0x180007e49  lea     r8, aProvisioningpa; "ProvisioningPackage::GetResetClear"
0x180007e50  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007e57  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007e5c  lea     rdx, aResetClearOutO; "    Reset clear out of range"
0x180007e63  jmp     short loc_180007EBD
0x180007e65  cmp     [rsp+38h+arg_0], 30h ; '0'
0x180007e6b  jnz     short loc_180007E74
0x180007e6d  mov     [rbx], r10d
0x180007e70  xor     eax, eax
0x180007e72  jmp     short loc_180007EC6
0x180007e74  cmp     [rsp+38h+arg_0], 31h ; '1'
0x180007e7a  jnz     short loc_180007E84
0x180007e7c  mov     dword ptr [rbx], 1
0x180007e82  jmp     short loc_180007E70
0x180007e84  mov     edi, 8007070Ch
0x180007e89  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007e90  mov     ebx, 3
0x180007e95  mov     [rsp+38h+var_10], edi
0x180007e99  mov     ecx, ebx
0x180007e9b  mov     [rsp+38h+var_18], 203h
0x180007ea3  lea     r8, aProvisioningpa; "ProvisioningPackage::GetResetClear"
0x180007eaa  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007eb1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007eb6  lea     rdx, aResetClearHasU; "    Reset clear has unknown value"
0x180007ebd  mov     ecx, ebx
0x180007ebf  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007ec4  mov     eax, edi
0x180007ec6  mov     rbx, [rsp+38h+arg_8]
0x180007ecb  add     rsp, 30h
0x180007ecf  pop     rdi
0x180007ed0  retn
```

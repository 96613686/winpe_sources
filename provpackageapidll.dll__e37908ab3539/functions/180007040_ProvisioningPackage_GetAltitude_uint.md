# ProvisioningPackage::GetAltitude(uint *)

- ea: `0x180007040`
- end: `0x180007189`
- name: `?GetAltitude@ProvisioningPackage@@EEAAJPEAI@Z`
- size: `329`
- prototype: `__int64 __fastcall(ProvisioningPackage *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001510`
- `0x180006014`
- `0x180006648`
- `0x180007040`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007129`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007129`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180007121`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180007121`

## string_xrefs

- `0x180007104`: `    Failed to copy string`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::GetAltitude(ProvisioningPackage *this, unsigned int *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // r8
  __int64 v5; // rcx
  wchar_t *v6; // rdx
  wchar_t *v7; // rcx
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-38h]
  int v11; // [rsp+20h] [rbp-38h]
  int v12; // [rsp+28h] [rbp-30h]
  int v13; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v14; // [rsp+30h] [rbp-28h] BYREF
  wchar_t String[8]; // [rsp+38h] [rbp-20h] BYREF

  v14 = L"ALTITUDE";
  v3 = (_QWORD *)std::map<unsigned short const *,std::wstring,stringCompare,std::allocator<std::pair<unsigned short const * const,std::wstring>>>::operator[](
                   (__int64 *)this + 5,
                   &v14);
  v4 = 7;
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  v5 = 2147483646;
  v6 = String;
  do
  {
    if ( !v5 )
      break;
    if ( !*(_WORD *)v3 )
      break;
    *v6 = *(_WORD *)v3;
    v3 = (_QWORD *)((char *)v3 + 2);
    ++v6;
    --v5;
    --v4;
  }
  while ( v4 );
  v7 = v6 - 1;
  v8 = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v7 = v6;
  *v7 = 0;
  if ( !v4 )
  {
    v12 = -2147024774;
    v10 = 479;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetAltitude",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v10,
      v12);
    ProvPackageLog(3, L"    Failed to copy string");
    return v8;
  }
  *a2 = wcstoul(String, 0, 10);
  if ( *(_DWORD *)_o__errno() == 34 )
  {
    v8 = -2147023092;
    v13 = -2147023092;
    v11 = 484;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetAltitude",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v11,
      v13);
    ProvPackageLog(3, L"    Altitude out of range");
    return v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180007040  mov     [rsp+arg_10], rbx
0x180007045  push    rdi
0x180007046  sub     rsp, 50h
0x18000704a  mov     rax, cs:__security_cookie
0x180007051  xor     rax, rsp
0x180007054  mov     [rsp+58h+var_10], rax
0x180007059  mov     rdi, rdx
0x18000705c  lea     rax, aAltitude; "ALTITUDE"
0x180007063  lea     rdx, [rsp+58h+var_28]
0x180007068  mov     [rsp+58h+var_28], rax
0x18000706d  add     rcx, 28h ; '('
0x180007071  call    ??A?$map@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAPEBG@Z; std::map<ushort const *,std::wstring,stringCompare,std::allocator<std::pair<ushort const * const,std::wstring>>>::operator[](ushort const * &&)
0x180007076  mov     r8d, 7
0x18000707c  cmp     [rax+18h], r8
0x180007080  jbe     short loc_180007085
0x180007082  mov     rax, [rax]
0x180007085  mov     ecx, 7FFFFFFEh
0x18000708a  lea     rdx, [rsp+58h+String]
0x18000708f  xor     r10d, r10d
0x180007092  test    rcx, rcx
0x180007095  jz      short loc_1800070B6
0x180007097  movzx   r9d, word ptr [rax]
0x18000709b  test    r9w, r9w
0x18000709f  jz      short loc_1800070B6
0x1800070a1  mov     [rdx], r9w
0x1800070a5  add     rax, 2
0x1800070a9  add     rdx, 2
0x1800070ad  dec     rcx
0x1800070b0  sub     r8, 1
0x1800070b4  jnz     short loc_180007092
0x1800070b6  mov     rax, r8
0x1800070b9  lea     rcx, [rdx-2]
0x1800070bd  neg     rax
0x1800070c0  sbb     ebx, ebx
0x1800070c2  not     ebx
0x1800070c4  and     ebx, 8007007Ah
0x1800070ca  test    r8, r8
0x1800070cd  cmovnz  rcx, rdx
0x1800070d1  mov     [rcx], r10w
0x1800070d5  jnz     short loc_180007116
0x1800070d7  mov     edi, 3
0x1800070dc  mov     [rsp+58h+var_30], ebx
0x1800070e0  mov     ecx, edi
0x1800070e2  mov     [rsp+58h+var_38], 1DFh
0x1800070ea  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800070f1  lea     r8, aProvisioningpa_9; "ProvisioningPackage::GetAltitude"
0x1800070f8  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800070ff  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007104  lea     rdx, aFailedToCopySt; "    Failed to copy string"
0x18000710b  mov     ecx, edi
0x18000710d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007112  mov     eax, ebx
0x180007114  jmp     short loc_180007171
0x180007116  xor     edx, edx; EndPtr
0x180007118  lea     rcx, [rsp+58h+String]; String
0x18000711d  lea     r8d, [rdx+0Ah]; Radix
0x180007121  call    cs:__imp_wcstoul
0x180007127  mov     [rdi], eax
0x180007129  call    cs:__imp__o__errno
0x18000712f  cmp     dword ptr [rax], 22h ; '"'
0x180007132  jnz     short loc_18000716F
0x180007134  mov     ebx, 8007070Ch
0x180007139  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007140  mov     edi, 3
0x180007145  mov     [rsp+58h+var_30], ebx
0x180007149  mov     ecx, edi
0x18000714b  mov     [rsp+58h+var_38], 1E4h
0x180007153  lea     r8, aProvisioningpa_9; "ProvisioningPackage::GetAltitude"
0x18000715a  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007161  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007166  lea     rdx, aAltitudeOutOfR; "    Altitude out of range"
0x18000716d  jmp     short loc_18000710B
0x18000716f  xor     eax, eax
0x180007171  mov     rcx, [rsp+58h+var_10]
0x180007176  xor     rcx, rsp; StackCookie
0x180007179  call    __security_check_cookie
0x18000717e  mov     rbx, [rsp+58h+arg_10]
0x180007183  add     rsp, 50h
0x180007187  pop     rdi
0x180007188  retn
```

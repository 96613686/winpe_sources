# PackageBuilder::SetPackageID(ushort const *)

- ea: `0x18000a040`
- end: `0x18000a1d9`
- name: `?SetPackageID@PackageBuilder@@EEAAJPEBG@Z`
- size: `409`
- prototype: `__int64 __fastcall(PackageBuilder *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001510`
- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x18000a040`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000a074`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000a074`

## string_xrefs

- `0x18000a1ae`: `    Failed to copy package ID string`

## pseudocode

```c
__int64 __fastcall PackageBuilder::SetPackageID(PackageBuilder *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rdi
  unsigned int v4; // edi
  _WORD *v6; // rdx
  void *v7; // rax
  const struct std::nothrow_t *v8; // rdx
  void *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r8
  _WORD *v12; // rcx
  int v13; // [rsp+20h] [rbp-38h]
  int v14; // [rsp+20h] [rbp-38h]
  int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+28h] [rbp-30h]
  int v17; // [rsp+28h] [rbp-30h]
  int v18; // [rsp+28h] [rbp-30h]
  IID iid; // [rsp+30h] [rbp-28h] BYREF

  v2 = a2;
  iid = 0;
  if ( IIDFromString(a2, &iid) < 0 )
  {
    v4 = -2147024809;
    v16 = -2147024809;
    v13 = 133;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetPackageID",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v13,
      v16);
    ProvPackageLog(3u, L"    Invalid GUID string");
    return v4;
  }
  v6 = (_WORD *)*((_QWORD *)this + 9);
  if ( !v6 )
  {
    v7 = operator new[](0x4Eu, (const struct std::nothrow_t *)&std::nothrow);
    v9 = (void *)*((_QWORD *)this + 9);
    *((_QWORD *)this + 9) = v7;
    if ( v9 )
      operator delete(v9, v8);
    v6 = (_WORD *)*((_QWORD *)this + 9);
    if ( !v6 )
    {
      v4 = -2147024882;
      v17 = -2147024882;
      v14 = 140;
      ProvPackageLog(
        3u,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageBuilder::SetPackageID",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
        v14,
        v17);
      ProvPackageLog(3u, L"    Failed to allocate _spPackageID.get()");
      return v4;
    }
  }
  v10 = 2147483646;
  v11 = 39;
  do
  {
    if ( !v10 )
      break;
    if ( !*v2 )
      break;
    *v6++ = *v2++;
    --v10;
    --v11;
  }
  while ( v11 );
  v12 = v6 - 1;
  v4 = v11 == 0 ? 0x8007007A : 0;
  if ( v11 )
    v12 = v6;
  *v12 = 0;
  if ( !v11 )
  {
    v18 = -2147024774;
    v15 = 144;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetPackageID",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v15,
      v18);
    ProvPackageLog(3u, L"    Failed to copy package ID string");
    return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a040  mov     [rsp+arg_10], rbx
0x18000a045  mov     [rsp+arg_18], rsi
0x18000a04a  push    rdi
0x18000a04b  sub     rsp, 50h
0x18000a04f  mov     rax, cs:__security_cookie
0x18000a056  xor     rax, rsp
0x18000a059  mov     [rsp+58h+var_18], rax
0x18000a05e  mov     rdi, rdx
0x18000a061  mov     rbx, rcx
0x18000a064  xorps   xmm0, xmm0
0x18000a067  lea     rdx, [rsp+58h+iid]; lpiid
0x18000a06c  mov     rcx, rdi; lpsz
0x18000a06f  movups  xmmword ptr [rsp+58h+iid.Data1], xmm0
0x18000a074  call    cs:__imp_IIDFromString
0x18000a07a  xor     esi, esi
0x18000a07c  test    eax, eax
0x18000a07e  jns     short loc_18000A0C5
0x18000a080  mov     edi, 80070057h
0x18000a085  lea     ebx, [rsi+3]
0x18000a088  mov     [rsp+58h+var_30], edi
0x18000a08c  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000a093  mov     ecx, ebx
0x18000a095  mov     [rsp+58h+var_38], 85h
0x18000a09d  lea     r8, aPackagebuilder_1; "PackageBuilder::SetPackageID"
0x18000a0a4  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000a0ab  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000a0b0  lea     rdx, aInvalidGuidStr; "    Invalid GUID string"
0x18000a0b7  mov     ecx, ebx
0x18000a0b9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000a0be  mov     eax, edi
0x18000a0c0  jmp     loc_18000A1BC
0x18000a0c5  mov     rdx, [rbx+48h]
0x18000a0c9  test    rdx, rdx
0x18000a0cc  jnz     short loc_18000A135
0x18000a0ce  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a0d5  mov     ecx, 4Eh ; 'N'; unsigned __int64
0x18000a0da  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a0df  mov     rcx, [rbx+48h]; void *
0x18000a0e3  mov     [rbx+48h], rax
0x18000a0e7  test    rcx, rcx
0x18000a0ea  jz      short loc_18000A0F1
0x18000a0ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a0f1  mov     rdx, [rbx+48h]
0x18000a0f5  test    rdx, rdx
0x18000a0f8  jnz     short loc_18000A135
0x18000a0fa  mov     edi, 8007000Eh
0x18000a0ff  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000a106  mov     ebx, 3
0x18000a10b  mov     [rsp+58h+var_30], edi
0x18000a10f  mov     ecx, ebx
0x18000a111  mov     [rsp+58h+var_38], 8Ch
0x18000a119  lea     r8, aPackagebuilder_1; "PackageBuilder::SetPackageID"
0x18000a120  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000a127  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000a12c  lea     rdx, aFailedToAlloca_33; "    Failed to allocate _spPackageID.get"...
0x18000a133  jmp     short loc_18000A0B7
0x18000a135  mov     eax, 7FFFFFFEh
0x18000a13a  mov     r8d, 27h ; '''
0x18000a140  test    rax, rax
0x18000a143  jz      short loc_18000A161
0x18000a145  movzx   ecx, word ptr [rdi]
0x18000a148  test    cx, cx
0x18000a14b  jz      short loc_18000A161
0x18000a14d  mov     [rdx], cx
0x18000a150  add     rdi, 2
0x18000a154  add     rdx, 2
0x18000a158  dec     rax
0x18000a15b  sub     r8, 1
0x18000a15f  jnz     short loc_18000A140
0x18000a161  mov     rax, r8
0x18000a164  lea     rcx, [rdx-2]
0x18000a168  neg     rax
0x18000a16b  sbb     edi, edi
0x18000a16d  not     edi
0x18000a16f  and     edi, 8007007Ah
0x18000a175  test    r8, r8
0x18000a178  cmovnz  rcx, rdx
0x18000a17c  mov     [rcx], si
0x18000a17f  jnz     short loc_18000A1BA
0x18000a181  mov     ebx, 3
0x18000a186  mov     [rsp+58h+var_30], edi
0x18000a18a  mov     ecx, ebx
0x18000a18c  mov     [rsp+58h+var_38], 90h
0x18000a194  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000a19b  lea     r8, aPackagebuilder_1; "PackageBuilder::SetPackageID"
0x18000a1a2  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000a1a9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000a1ae  lea     rdx, aFailedToCopyPa; "    Failed to copy package ID string"
0x18000a1b5  jmp     loc_18000A0B7
0x18000a1ba  xor     eax, eax
0x18000a1bc  mov     rcx, [rsp+58h+var_18]
0x18000a1c1  xor     rcx, rsp; StackCookie
0x18000a1c4  call    __security_check_cookie
0x18000a1c9  mov     rbx, [rsp+58h+arg_10]
0x18000a1ce  mov     rsi, [rsp+58h+arg_18]
0x18000a1d3  add     rsp, 50h
0x18000a1d7  pop     rdi
0x18000a1d8  retn
```

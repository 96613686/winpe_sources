# CreatePackageSecurity

- ea: `0x180005c30`
- end: `0x180005cb1`
- name: `CreatePackageSecurity`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002084`
- `0x180005c30`
- `0x180006014`

## string_xrefs

- `0x180005c85`: `CreatePackageSecurity`

## pseudocode

```c
__int64 __fastcall CreatePackageSecurity(_QWORD *a1)
{
  _QWORD *v2; // rax
  int v4; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+28h] [rbp-10h]

  *a1 = 0;
  v2 = operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
  {
    *v2 = &PackageSecurity::`vftable';
    *a1 = v2;
    return 0;
  }
  else
  {
    v5 = -2147024882;
    v4 = 78;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "CreatePackageSecurity",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packageapi.cpp",
      v4,
      v5);
    ProvPackageLog(3, L"    Failed to allocate ptr");
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180005c30  push    rbx
0x180005c32  sub     rsp, 30h
0x180005c36  mov     rbx, rcx
0x180005c39  mov     qword ptr [rcx], 0
0x180005c40  mov     ecx, 8; unsigned __int64
0x180005c45  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005c4c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005c51  test    rax, rax
0x180005c54  jz      short loc_180005C67
0x180005c56  lea     rcx, ??_7PackageSecurity@@6B@; const PackageSecurity::`vftable'
0x180005c5d  mov     [rax], rcx
0x180005c60  mov     [rbx], rax
0x180005c63  xor     eax, eax
0x180005c65  jmp     short loc_180005CAB
0x180005c67  mov     ebx, 3
0x180005c6c  mov     [rsp+38h+var_10], 8007000Eh
0x180005c74  mov     ecx, ebx
0x180005c76  mov     [rsp+38h+var_18], 4Eh ; 'N'
0x180005c7e  lea     r9, aOnecoreBaseNts_9; "onecore\\base\\ntsetup\\provpackageapi"...
0x180005c85  lea     r8, aCreatepackages_0; "CreatePackageSecurity"
0x180005c8c  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180005c93  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005c98  lea     rdx, aFailedToAlloca_0; "    Failed to allocate ptr"
0x180005c9f  mov     ecx, ebx
0x180005ca1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005ca6  mov     eax, 8007000Eh
0x180005cab  add     rsp, 30h
0x180005caf  pop     rbx
0x180005cb0  retn
```

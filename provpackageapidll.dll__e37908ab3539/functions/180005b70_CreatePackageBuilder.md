# CreatePackageBuilder

- ea: `0x180005b70`
- end: `0x180005c1b`
- name: `CreatePackageBuilder`
- size: `171`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180002084`
- `0x180005b70`
- `0x180006014`

## string_xrefs

- `0x180005bed`: `CreatePackageBuilder`

## pseudocode

```c
__int64 __fastcall CreatePackageBuilder(_QWORD *a1)
{
  _DWORD *v2; // rax
  int v4; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+28h] [rbp-10h]

  *a1 = 0;
  v2 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
  {
    v2[20] = 0;
    *(_QWORD *)v2 = &PackageBuilder::`vftable';
    *((_QWORD *)v2 + 1) = 0;
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
    *((_QWORD *)v2 + 4) = 0;
    *((_QWORD *)v2 + 5) = 0;
    *((_QWORD *)v2 + 6) = 0;
    *((_QWORD *)v2 + 7) = 0;
    *((_QWORD *)v2 + 8) = 0;
    *((_QWORD *)v2 + 9) = 0;
    *a1 = v2;
    return 0;
  }
  else
  {
    v5 = -2147024882;
    v4 = 21;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "CreatePackageBuilder",
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
0x180005b70  mov     [rsp+arg_0], rbx
0x180005b75  push    rdi
0x180005b76  sub     rsp, 30h
0x180005b7a  xor     edi, edi
0x180005b7c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005b83  mov     rbx, rcx
0x180005b86  mov     [rcx], rdi
0x180005b89  lea     ecx, [rdi+58h]; unsigned __int64
0x180005b8c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005b91  test    rax, rax
0x180005b94  jz      short loc_180005BCE
0x180005b96  mov     [rax+50h], edi
0x180005b99  lea     rcx, ??_7PackageBuilder@@6B@; const PackageBuilder::`vftable'
0x180005ba0  mov     [rax], rcx
0x180005ba3  mov     [rax+8], rdi
0x180005ba7  mov     [rax+10h], rdi
0x180005bab  mov     [rax+18h], rdi
0x180005baf  mov     [rax+20h], rdi
0x180005bb3  mov     [rax+28h], rdi
0x180005bb7  mov     [rax+30h], rdi
0x180005bbb  mov     [rax+38h], rdi
0x180005bbf  mov     [rax+40h], rdi
0x180005bc3  mov     [rax+48h], rdi
0x180005bc7  mov     [rbx], rax
0x180005bca  xor     eax, eax
0x180005bcc  jmp     short loc_180005C10
0x180005bce  mov     edi, 8007000Eh
0x180005bd3  lea     r9, aOnecoreBaseNts_9; "onecore\\base\\ntsetup\\provpackageapi"...
0x180005bda  mov     ebx, 3
0x180005bdf  mov     [rsp+38h+var_10], edi
0x180005be3  mov     ecx, ebx
0x180005be5  mov     [rsp+38h+var_18], 15h
0x180005bed  lea     r8, aCreatepackageb_0; "CreatePackageBuilder"
0x180005bf4  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180005bfb  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005c00  lea     rdx, aFailedToAlloca_0; "    Failed to allocate ptr"
0x180005c07  mov     ecx, ebx
0x180005c09  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005c0e  mov     eax, edi
0x180005c10  mov     rbx, [rsp+38h+arg_0]
0x180005c15  add     rsp, 30h
0x180005c19  pop     rdi
0x180005c1a  retn
```

# ProvisioningPackage::CreateElement(_PROVISIONINGELEMENTTYPE,IElement * *)

- ea: `0x180006790`
- end: `0x1800068b0`
- name: `?CreateElement@ProvisioningPackage@@EEAAJW4_PROVISIONINGELEMENTTYPE@@PEAPEAUIElement@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180002084`
- `0x180006014`
- `0x180006790`
- `0x180014f8c`
- `0x180019010`

## string_xrefs

- `0x180006848`: `ProvisioningPackage::CreateElement`
- `0x180006883`: `ProvisioningPackage::CreateElement`
- `0x18000685b`: `    Failed to create element`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::CreateElement(__int64 a1, int a2, _QWORD *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  int Element; // edi

  v6 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    v6[1] = 0;
    *v6 = &Element::`vftable';
    v6[2] = 0;
    v6[3] = 0;
    v6[4] = 0;
    v6[5] = 0;
    Element = Element::CreateElement((__int64)v6, a1, a2, *(_DWORD *)(a1 + 88));
    if ( Element < 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v7 + 80LL))(v7);
      v7 = 0;
    }
    ++*(_DWORD *)(a1 + 88);
    *a3 = v7;
    if ( Element < 0 )
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::CreateElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        603,
        Element);
      ProvPackageLog(3, L"    Failed to create element");
    }
  }
  else
  {
    Element = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::CreateElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      591,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate ptr");
  }
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180006790  push    rbx
0x180006792  push    rsi
0x180006793  push    rdi
0x180006794  push    r14
0x180006796  sub     rsp, 38h
0x18000679a  mov     edi, edx
0x18000679c  mov     rsi, rcx
0x18000679f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800067a6  mov     ecx, 30h ; '0'; unsigned __int64
0x1800067ab  mov     r14, r8
0x1800067ae  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800067b3  mov     [rsp+58h+arg_18], rax
0x1800067b8  mov     rbx, rax
0x1800067bb  test    rax, rax
0x1800067be  jz      loc_180006864
0x1800067c4  mov     qword ptr [rbx+8], 0
0x1800067cc  lea     rax, ??_7Element@@6B@; const Element::`vftable'
0x1800067d3  mov     [rbx], rax
0x1800067d6  mov     qword ptr [rbx+10h], 0
0x1800067de  mov     qword ptr [rbx+18h], 0
0x1800067e6  mov     qword ptr [rbx+20h], 0
0x1800067ee  mov     qword ptr [rbx+28h], 0
0x1800067f6  test    rbx, rbx
0x1800067f9  jz      short loc_180006864
0x1800067fb  mov     r9d, [rsi+58h]
0x1800067ff  mov     r8d, edi
0x180006802  mov     rdx, rsi
0x180006805  mov     rcx, rbx
0x180006808  call    ?CreateElement@Element@@QEAAJPEAVProvisioningPackage@@W4_PROVISIONINGELEMENTTYPE@@I@Z; Element::CreateElement(ProvisioningPackage *,_PROVISIONINGELEMENTTYPE,uint)
0x18000680d  mov     edi, eax
0x18000680f  test    eax, eax
0x180006811  jns     short loc_180006824
0x180006813  mov     rdx, [rbx]
0x180006816  mov     rcx, rbx
0x180006819  mov     rax, [rdx+50h]
0x18000681d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006822  xor     ebx, ebx
0x180006824  inc     dword ptr [rsi+58h]
0x180006827  mov     [r14], rbx
0x18000682a  test    edi, edi
0x18000682c  jns     short loc_1800068A4
0x18000682e  mov     ebx, 3
0x180006833  mov     [rsp+58h+var_30], edi
0x180006837  mov     ecx, ebx
0x180006839  mov     [rsp+58h+var_38], 25Bh
0x180006841  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006848  lea     r8, aProvisioningpa_1; "ProvisioningPackage::CreateElement"
0x18000684f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006856  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000685b  lea     rdx, aFailedToCreate_18; "    Failed to create element"
0x180006862  jmp     short loc_18000689D
0x180006864  mov     edi, 8007000Eh
0x180006869  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006870  mov     ebx, 3
0x180006875  mov     [rsp+58h+var_30], edi
0x180006879  mov     ecx, ebx
0x18000687b  mov     [rsp+58h+var_38], 24Fh
0x180006883  lea     r8, aProvisioningpa_1; "ProvisioningPackage::CreateElement"
0x18000688a  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006891  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006896  lea     rdx, aFailedToAlloca_0; "    Failed to allocate ptr"
0x18000689d  mov     ecx, ebx
0x18000689f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800068a4  mov     eax, edi
0x1800068a6  add     rsp, 38h
0x1800068aa  pop     r14
0x1800068ac  pop     rdi
0x1800068ad  pop     rsi
0x1800068ae  pop     rbx
0x1800068af  retn
```

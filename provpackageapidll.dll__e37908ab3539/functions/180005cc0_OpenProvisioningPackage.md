# OpenProvisioningPackage

- ea: `0x180005cc0`
- end: `0x180005e05`
- name: `OpenProvisioningPackage`
- size: `325`
- prototype: `__int64 __fastcall(unsigned __int16 *, ProvisioningPackage **)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002084`
- `0x180005cc0`
- `0x180006014`
- `0x180006140`
- `0x1800088dc`
- `0x180019010`

## string_xrefs

- `0x180005d7d`: `OpenProvisioningPackage`
- `0x180005dd2`: `OpenProvisioningPackage`
- `0x180005d52`: `    Failed to open provisioning package`
- `0x180005d9a`: `    Failed to open provisioning package`
- `0x180005d3f`: `ProvisioningPackage::OpenProvisioningPackage`

## pseudocode

```c
__int64 __fastcall OpenProvisioningPackage(unsigned __int16 *a1, ProvisioningPackage **a2)
{
  ProvisioningPackage *v4; // rax
  ProvisioningPackage *v5; // rax
  ProvisioningPackage *v6; // rbx
  int v7; // eax
  unsigned int v8; // esi
  int v10; // [rsp+20h] [rbp-18h]
  __int64 v11; // [rsp+20h] [rbp-18h]
  int v12; // [rsp+20h] [rbp-18h]
  int v13; // [rsp+28h] [rbp-10h]
  __int64 v14; // [rsp+28h] [rbp-10h]
  int v15; // [rsp+28h] [rbp-10h]

  *a2 = 0;
  v4 = (ProvisioningPackage *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 && (v5 = ProvisioningPackage::ProvisioningPackage(v4), (v6 = v5) != 0) )
  {
    v7 = ProvisioningPackage::OpenProvisioningPackage(v5, a1, 0xC0000000);
    v8 = v7;
    if ( v7 >= 0 )
    {
      *a2 = v6;
      return 0;
    }
    else
    {
      v13 = v7;
      v10 = 71;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::OpenProvisioningPackage",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        v10,
        v13);
      ProvPackageLog(3, L"    Failed to open provisioning package");
      (*(void (__fastcall **)(ProvisioningPackage *))(*(_QWORD *)v6 + 128LL))(v6);
      LODWORD(v14) = v8;
      LODWORD(v11) = 43;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "OpenProvisioningPackage",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packageapi.cpp",
        v11,
        v14);
      ProvPackageLog(3, L"    Failed to open provisioning package");
      return v8;
    }
  }
  else
  {
    v15 = -2147024882;
    v12 = 36;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "OpenProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packageapi.cpp",
      v12,
      v15);
    ProvPackageLog(3, L"    Failed to allocate ptr");
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180005cc0  mov     [rsp+arg_0], rbx
0x180005cc5  mov     [rsp+arg_8], rsi
0x180005cca  push    rdi
0x180005ccb  sub     rsp, 30h
0x180005ccf  mov     rdi, rdx
0x180005cd2  mov     qword ptr [rdx], 0
0x180005cd9  mov     rsi, rcx
0x180005cdc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005ce3  mov     ecx, 60h ; '`'; unsigned __int64
0x180005ce8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005ced  test    rax, rax
0x180005cf0  jz      loc_180005DB3
0x180005cf6  mov     rcx, rax; this
0x180005cf9  call    ??0ProvisioningPackage@@QEAA@XZ; ProvisioningPackage::ProvisioningPackage(void)
0x180005cfe  mov     rbx, rax
0x180005d01  test    rax, rax
0x180005d04  jz      loc_180005DB3
0x180005d0a  mov     r8d, 0C0000000h; unsigned int
0x180005d10  mov     rdx, rsi; unsigned __int16 *
0x180005d13  mov     rcx, rax; this
0x180005d16  call    ?OpenProvisioningPackage@ProvisioningPackage@@AEAAJPEBGK@Z; ProvisioningPackage::OpenProvisioningPackage(ushort const *,ulong)
0x180005d1b  mov     esi, eax
0x180005d1d  test    eax, eax
0x180005d1f  jns     loc_180005DAC
0x180005d25  mov     [rsp+38h+var_10], eax
0x180005d29  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180005d30  mov     edi, 3
0x180005d35  mov     dword ptr [rsp+38h+var_18], 47h ; 'G'
0x180005d3d  mov     ecx, edi
0x180005d3f  lea     r8, aProvisioningpa_17; "ProvisioningPackage::OpenProvisioningPa"...
0x180005d46  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180005d4d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005d52  lea     rdx, aFailedToOpenPr_0; "    Failed to open provisioning package"
0x180005d59  mov     ecx, edi
0x180005d5b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005d60  mov     rax, [rbx]
0x180005d63  mov     rcx, rbx
0x180005d66  mov     rax, [rax+80h]
0x180005d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d72  lea     r9, aOnecoreBaseNts_9; "onecore\\base\\ntsetup\\provpackageapi"...
0x180005d79  mov     [rsp+38h+var_10], esi
0x180005d7d  lea     r8, aOpenprovisioni_1; "OpenProvisioningPackage"
0x180005d84  mov     dword ptr [rsp+38h+var_18], 2Bh ; '+'
0x180005d8c  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180005d93  mov     ecx, edi
0x180005d95  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005d9a  lea     rdx, aFailedToOpenPr_0; "    Failed to open provisioning package"
0x180005da1  mov     ecx, edi
0x180005da3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005da8  mov     eax, esi
0x180005daa  jmp     short loc_180005DF5
0x180005dac  mov     [rdi], rbx
0x180005daf  xor     eax, eax
0x180005db1  jmp     short loc_180005DF5
0x180005db3  mov     ebx, 8007000Eh
0x180005db8  lea     r9, aOnecoreBaseNts_9; "onecore\\base\\ntsetup\\provpackageapi"...
0x180005dbf  mov     edi, 3
0x180005dc4  mov     [rsp+38h+var_10], ebx
0x180005dc8  mov     ecx, edi
0x180005dca  mov     dword ptr [rsp+38h+var_18], 24h ; '$'
0x180005dd2  lea     r8, aOpenprovisioni_1; "OpenProvisioningPackage"
0x180005dd9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180005de0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005de5  lea     rdx, aFailedToAlloca_0; "    Failed to allocate ptr"
0x180005dec  mov     ecx, edi
0x180005dee  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005df3  mov     eax, ebx
0x180005df5  mov     rbx, [rsp+38h+arg_0]
0x180005dfa  mov     rsi, [rsp+38h+arg_8]
0x180005dff  add     rsp, 30h
0x180005e03  pop     rdi
0x180005e04  retn
```

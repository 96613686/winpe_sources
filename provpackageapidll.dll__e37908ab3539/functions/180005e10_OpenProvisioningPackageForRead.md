# OpenProvisioningPackageForRead

- ea: `0x180005e10`
- end: `0x180005f55`
- name: `OpenProvisioningPackageForRead`
- size: `325`
- prototype: `__int64 __fastcall(unsigned __int16 *, ProvisioningPackage **)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002084`
- `0x180005e10`
- `0x180006014`
- `0x180006140`
- `0x1800088dc`
- `0x180019010`

## string_xrefs

- `0x180005ea2`: `    Failed to open provisioning package`
- `0x180005ecd`: `OpenProvisioningPackageForRead`
- `0x180005f22`: `OpenProvisioningPackageForRead`
- `0x180005eea`: `    Failed to open provisioning package for read`
- `0x180005e8f`: `ProvisioningPackage::OpenProvisioningPackageForRead`

## pseudocode

```c
__int64 __fastcall OpenProvisioningPackageForRead(unsigned __int16 *a1, ProvisioningPackage **a2)
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
    v7 = ProvisioningPackage::OpenProvisioningPackage(v5, a1, 0x80000000);
    v8 = v7;
    if ( v7 >= 0 )
    {
      *a2 = v6;
      return 0;
    }
    else
    {
      v13 = v7;
      v10 = 82;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::OpenProvisioningPackageForRead",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        v10,
        v13);
      ProvPackageLog(3, L"    Failed to open provisioning package");
      (*(void (__fastcall **)(ProvisioningPackage *))(*(_QWORD *)v6 + 128LL))(v6);
      LODWORD(v14) = v8;
      LODWORD(v11) = 64;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "OpenProvisioningPackageForRead",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packageapi.cpp",
        v11,
        v14);
      ProvPackageLog(3, L"    Failed to open provisioning package for read");
      return v8;
    }
  }
  else
  {
    v15 = -2147024882;
    v12 = 57;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "OpenProvisioningPackageForRead",
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
0x180005e10  mov     [rsp+arg_0], rbx
0x180005e15  mov     [rsp+arg_8], rsi
0x180005e1a  push    rdi
0x180005e1b  sub     rsp, 30h
0x180005e1f  mov     rdi, rdx
0x180005e22  mov     qword ptr [rdx], 0
0x180005e29  mov     rsi, rcx
0x180005e2c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005e33  mov     ecx, 60h ; '`'; unsigned __int64
0x180005e38  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005e3d  test    rax, rax
0x180005e40  jz      loc_180005F03
0x180005e46  mov     rcx, rax; this
0x180005e49  call    ??0ProvisioningPackage@@QEAA@XZ; ProvisioningPackage::ProvisioningPackage(void)
0x180005e4e  mov     rbx, rax
0x180005e51  test    rax, rax
0x180005e54  jz      loc_180005F03
0x180005e5a  mov     r8d, 80000000h; unsigned int
0x180005e60  mov     rdx, rsi; unsigned __int16 *
0x180005e63  mov     rcx, rax; this
0x180005e66  call    ?OpenProvisioningPackage@ProvisioningPackage@@AEAAJPEBGK@Z; ProvisioningPackage::OpenProvisioningPackage(ushort const *,ulong)
0x180005e6b  mov     esi, eax
0x180005e6d  test    eax, eax
0x180005e6f  jns     loc_180005EFC
0x180005e75  mov     [rsp+38h+var_10], eax
0x180005e79  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180005e80  mov     edi, 3
0x180005e85  mov     dword ptr [rsp+38h+var_18], 52h ; 'R'
0x180005e8d  mov     ecx, edi
0x180005e8f  lea     r8, aProvisioningpa_5; "ProvisioningPackage::OpenProvisioningPa"...
0x180005e96  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180005e9d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005ea2  lea     rdx, aFailedToOpenPr_0; "    Failed to open provisioning package"
0x180005ea9  mov     ecx, edi
0x180005eab  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005eb0  mov     rax, [rbx]
0x180005eb3  mov     rcx, rbx
0x180005eb6  mov     rax, [rax+80h]
0x180005ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec2  lea     r9, aOnecoreBaseNts_9; "onecore\\base\\ntsetup\\provpackageapi"...
0x180005ec9  mov     [rsp+38h+var_10], esi
0x180005ecd  lea     r8, aOpenprovisioni_2; "OpenProvisioningPackageForRead"
0x180005ed4  mov     dword ptr [rsp+38h+var_18], 40h ; '@'
0x180005edc  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180005ee3  mov     ecx, edi
0x180005ee5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005eea  lea     rdx, aFailedToOpenPr; "    Failed to open provisioning package"...
0x180005ef1  mov     ecx, edi
0x180005ef3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005ef8  mov     eax, esi
0x180005efa  jmp     short loc_180005F45
0x180005efc  mov     [rdi], rbx
0x180005eff  xor     eax, eax
0x180005f01  jmp     short loc_180005F45
0x180005f03  mov     ebx, 8007000Eh
0x180005f08  lea     r9, aOnecoreBaseNts_9; "onecore\\base\\ntsetup\\provpackageapi"...
0x180005f0f  mov     edi, 3
0x180005f14  mov     [rsp+38h+var_10], ebx
0x180005f18  mov     ecx, edi
0x180005f1a  mov     dword ptr [rsp+38h+var_18], 39h ; '9'
0x180005f22  lea     r8, aOpenprovisioni_2; "OpenProvisioningPackageForRead"
0x180005f29  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180005f30  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005f35  lea     rdx, aFailedToAlloca_0; "    Failed to allocate ptr"
0x180005f3c  mov     ecx, edi
0x180005f3e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180005f43  mov     eax, ebx
0x180005f45  mov     rbx, [rsp+38h+arg_0]
0x180005f4a  mov     rsi, [rsp+38h+arg_8]
0x180005f4f  add     rsp, 30h
0x180005f53  pop     rdi
0x180005f54  retn
```

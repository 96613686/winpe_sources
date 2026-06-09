# PackageBuilder::CreateProvisioningPackage(IProvisioningPackage * *)

- ea: `0x180009740`
- end: `0x180009af0`
- name: `?CreateProvisioningPackage@PackageBuilder@@EEAAJPEAPEAUIProvisioningPackage@@@Z`
- size: `944`
- prototype: `__int64 __fastcall(PackageBuilder *__hidden this, struct IProvisioningPackage **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180002110`
- `0x180005424`
- `0x180006014`
- `0x180006140`
- `0x1800068b8`
- `0x180009740`
- `0x18000e1cc`
- `0x180019010`

## string_xrefs

- `0x1800097ab`: `PackageBuilder::CreateProvisioningPackage`
- `0x1800097f6`: `PackageBuilder::CreateProvisioningPackage`
- `0x180009868`: `PackageBuilder::CreateProvisioningPackage`
- `0x1800098b6`: `PackageBuilder::CreateProvisioningPackage`
- `0x180009925`: `PackageBuilder::CreateProvisioningPackage`
- `0x180009973`: `PackageBuilder::CreateProvisioningPackage`
- `0x1800099e4`: `PackageBuilder::CreateProvisioningPackage`
- `0x180009a30`: `PackageBuilder::CreateProvisioningPackage`
- `0x180009aad`: `PackageBuilder::CreateProvisioningPackage`
- `0x1800098d0`: `    Failed to copy default altitude string`
- `0x18000998d`: `    Failed to copy default reset clear string`
- `0x180009a4a`: `    Failed to copy default version string`
- `0x180009ac7`: `    Failed to create provisioning package`

## pseudocode

```c
__int64 __fastcall PackageBuilder::CreateProvisioningPackage(PackageBuilder *this, struct IProvisioningPackage **a2)
{
  void *v4; // rax
  const struct std::nothrow_t *v5; // rdx
  void *v6; // rcx
  unsigned __int16 *v7; // rcx
  unsigned int v8; // edi
  __int64 result; // rax
  int Guid; // eax
  void *v11; // rax
  const struct std::nothrow_t *v12; // rdx
  void *v13; // rcx
  unsigned __int16 *v14; // rcx
  int v15; // eax
  void *v16; // rax
  const struct std::nothrow_t *v17; // rdx
  void *v18; // rcx
  unsigned __int16 *v19; // rcx
  int v20; // eax
  void *v21; // rax
  const struct std::nothrow_t *v22; // rdx
  void *v23; // rcx
  unsigned __int16 *v24; // rcx
  int v25; // eax
  ProvisioningPackage *v26; // rdi
  unsigned int v27; // esi
  int v28; // [rsp+20h] [rbp-28h]
  int v29; // [rsp+20h] [rbp-28h]
  int v30; // [rsp+20h] [rbp-28h]
  int v31; // [rsp+20h] [rbp-28h]
  int v32; // [rsp+20h] [rbp-28h]
  int v33; // [rsp+20h] [rbp-28h]
  int v34; // [rsp+20h] [rbp-28h]
  int v35; // [rsp+20h] [rbp-28h]
  int v36; // [rsp+20h] [rbp-28h]
  int v37; // [rsp+28h] [rbp-20h]
  int v38; // [rsp+28h] [rbp-20h]
  int v39; // [rsp+28h] [rbp-20h]
  int v40; // [rsp+28h] [rbp-20h]
  int v41; // [rsp+28h] [rbp-20h]
  int v42; // [rsp+28h] [rbp-20h]
  int v43; // [rsp+28h] [rbp-20h]
  int v44; // [rsp+28h] [rbp-20h]
  int v45; // [rsp+28h] [rbp-20h]
  ProvisioningPackage *v46; // [rsp+50h] [rbp+8h]

  if ( !*((_QWORD *)this + 9) )
  {
    v4 = operator new[](0x4Eu, (const struct std::nothrow_t *)&std::nothrow);
    v6 = (void *)*((_QWORD *)this + 9);
    *((_QWORD *)this + 9) = v4;
    if ( v6 )
      operator delete(v6, v5);
    v7 = (unsigned __int16 *)*((_QWORD *)this + 9);
    if ( !v7 )
    {
      v8 = -2147024882;
      v37 = -2147024882;
      v28 = 209;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageBuilder::CreateProvisioningPackage",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
        v28,
        v37);
      ProvPackageLog(3, L"    Failed to allocate _spPackageID.get()");
      return v8;
    }
    Guid = GetGuid(v7, (unsigned __int64)v5);
    v8 = Guid;
    if ( Guid < 0 )
    {
      v38 = Guid;
      v29 = 212;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageBuilder::CreateProvisioningPackage",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
        v29,
        v38);
      ProvPackageLog(3, L"    Failed to get GUID");
      return v8;
    }
  }
  if ( !*((_QWORD *)this + 7) )
  {
    v11 = operator new[](4u, (const struct std::nothrow_t *)&std::nothrow);
    v13 = (void *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v11;
    if ( v13 )
      operator delete(v13, v12);
    v14 = (unsigned __int16 *)*((_QWORD *)this + 7);
    if ( !v14 )
    {
      v8 = -2147024882;
      v39 = -2147024882;
      v30 = 219;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageBuilder::CreateProvisioningPackage",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
        v30,
        v39);
      ProvPackageLog(3, L"    Failed to allocate _spAltitude.get()");
      return v8;
    }
    v15 = StringCchCopyW(v14, 2u, L"0");
    v8 = v15;
    if ( v15 < 0 )
    {
      v40 = v15;
      v31 = 223;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageBuilder::CreateProvisioningPackage",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
        v31,
        v40);
      ProvPackageLog(3, L"    Failed to copy default altitude string");
      return v8;
    }
  }
  if ( !*((_QWORD *)this + 8) )
  {
    v16 = operator new[](4u, (const struct std::nothrow_t *)&std::nothrow);
    v18 = (void *)*((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = v16;
    if ( v18 )
      operator delete(v18, v17);
    v19 = (unsigned __int16 *)*((_QWORD *)this + 8);
    if ( !v19 )
    {
      v8 = -2147024882;
      v41 = -2147024882;
      v32 = 230;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageBuilder::CreateProvisioningPackage",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
        v32,
        v41);
      ProvPackageLog(3, L"    Failed to allocate _spResetClear.get()");
      return v8;
    }
    v20 = StringCchCopyW(v19, 2u, L"0");
    v8 = v20;
    if ( v20 < 0 )
    {
      v42 = v20;
      v33 = 234;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageBuilder::CreateProvisioningPackage",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
        v33,
        v42);
      ProvPackageLog(3, L"    Failed to copy default reset clear string");
      return v8;
    }
  }
  if ( !*((_QWORD *)this + 6) )
  {
    v21 = operator new[](8u, (const struct std::nothrow_t *)&std::nothrow);
    v23 = (void *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = v21;
    if ( v23 )
      operator delete(v23, v22);
    v24 = (unsigned __int16 *)*((_QWORD *)this + 6);
    if ( !v24 )
    {
      v8 = -2147024882;
      v43 = -2147024882;
      v34 = 241;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageBuilder::CreateProvisioningPackage",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
        v34,
        v43);
      ProvPackageLog(3, L"    Failed to allocate _spVersion.get()");
      return v8;
    }
    v25 = StringCchCopyW(v24, 4u, L"1.0");
    v8 = v25;
    if ( v25 < 0 )
    {
      v44 = v25;
      v35 = 245;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageBuilder::CreateProvisioningPackage",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
        v35,
        v44);
      ProvPackageLog(3, L"    Failed to copy default version string");
      return v8;
    }
  }
  v46 = (ProvisioningPackage *)operator new(0x60u);
  v26 = ProvisioningPackage::ProvisioningPackage(v46);
  result = ProvisioningPackage::CreateProvisioningPackage(v26, this);
  v27 = result;
  if ( (int)result >= 0 )
  {
    *a2 = v26;
  }
  else
  {
    (*(void (__fastcall **)(ProvisioningPackage *))(*(_QWORD *)v26 + 128LL))(v26);
    *a2 = 0;
    v45 = v27;
    v36 = 258;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::CreateProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v36,
      v45);
    ProvPackageLog(3, L"    Failed to create provisioning package");
    return v27;
  }
  return result;
}

```

## disassembly

```asm
0x180009740  mov     [rsp+arg_8], rbx
0x180009745  mov     [rsp+arg_10], rsi
0x18000974a  push    rdi
0x18000974b  push    r14
0x18000974d  push    r15
0x18000974f  sub     rsp, 30h
0x180009753  mov     r14, rdx
0x180009756  mov     rbx, rcx
0x180009759  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180009760  cmp     qword ptr [rcx+48h], 0
0x180009765  jnz     loc_180009819
0x18000976b  mov     rdx, rsi; struct std::nothrow_t *
0x18000976e  mov     ecx, 4Eh ; 'N'; unsigned __int64
0x180009773  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009778  mov     rcx, [rbx+48h]; void *
0x18000977c  mov     [rbx+48h], rax
0x180009780  test    rcx, rcx
0x180009783  jz      short loc_18000978A
0x180009785  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000978a  mov     rcx, [rbx+48h]; unsigned __int16 *
0x18000978e  test    rcx, rcx
0x180009791  jnz     short loc_1800097D8
0x180009793  mov     edi, 8007000Eh
0x180009798  mov     [rsp+48h+var_20], edi
0x18000979c  mov     [rsp+48h+var_28], 0D1h
0x1800097a4  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800097ab  lea     r8, aPackagebuilder_3; "PackageBuilder::CreateProvisioningPacka"...
0x1800097b2  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800097b9  lea     ebx, [rcx+3]
0x1800097bc  mov     ecx, ebx
0x1800097be  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800097c3  lea     rdx, aFailedToAlloca_33; "    Failed to allocate _spPackageID.get"...
0x1800097ca  mov     ecx, ebx
0x1800097cc  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800097d1  mov     eax, edi
0x1800097d3  jmp     loc_180009ADC
0x1800097d8  call    ?GetGuid@@YAJPEAG_K@Z; GetGuid(ushort *,unsigned __int64)
0x1800097dd  mov     edi, eax
0x1800097df  test    eax, eax
0x1800097e1  jns     short loc_180009819
0x1800097e3  mov     [rsp+48h+var_20], eax
0x1800097e7  mov     [rsp+48h+var_28], 0D4h
0x1800097ef  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800097f6  lea     r8, aPackagebuilder_3; "PackageBuilder::CreateProvisioningPacka"...
0x1800097fd  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009804  mov     ebx, 3
0x180009809  mov     ecx, ebx
0x18000980b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009810  lea     rdx, aFailedToGetGui; "    Failed to get GUID"
0x180009817  jmp     short loc_1800097CA
0x180009819  mov     r15d, 4
0x18000981f  cmp     qword ptr [rbx+38h], 0
0x180009824  jnz     loc_1800098DC
0x18000982a  mov     rdx, rsi; struct std::nothrow_t *
0x18000982d  mov     ecx, r15d; unsigned __int64
0x180009830  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009835  mov     rcx, [rbx+38h]; void *
0x180009839  mov     [rbx+38h], rax
0x18000983d  test    rcx, rcx
0x180009840  jz      short loc_180009847
0x180009842  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009847  mov     rcx, [rbx+38h]; unsigned __int16 *
0x18000984b  test    rcx, rcx
0x18000984e  jnz     short loc_18000988C
0x180009850  mov     edi, 8007000Eh
0x180009855  mov     [rsp+48h+var_20], edi
0x180009859  mov     [rsp+48h+var_28], 0DBh
0x180009861  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009868  lea     r8, aPackagebuilder_3; "PackageBuilder::CreateProvisioningPacka"...
0x18000986f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009876  lea     ebx, [rcx+3]
0x180009879  mov     ecx, ebx
0x18000987b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009880  lea     rdx, aFailedToAlloca_14; "    Failed to allocate _spAltitude.get("...
0x180009887  jmp     loc_1800097CA
0x18000988c  lea     r8, a0; "0"
0x180009893  mov     edx, 2; unsigned __int64
0x180009898  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000989d  mov     edi, eax
0x18000989f  test    eax, eax
0x1800098a1  jns     short loc_1800098DC
0x1800098a3  mov     [rsp+48h+var_20], eax
0x1800098a7  mov     [rsp+48h+var_28], 0DFh
0x1800098af  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800098b6  lea     r8, aPackagebuilder_3; "PackageBuilder::CreateProvisioningPacka"...
0x1800098bd  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800098c4  mov     ebx, 3
0x1800098c9  mov     ecx, ebx
0x1800098cb  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800098d0  lea     rdx, aFailedToCopyDe_1; "    Failed to copy default altitude str"...
0x1800098d7  jmp     loc_1800097CA
0x1800098dc  cmp     qword ptr [rbx+40h], 0
0x1800098e1  jnz     loc_180009999
0x1800098e7  mov     rdx, rsi; struct std::nothrow_t *
0x1800098ea  mov     rcx, r15; unsigned __int64
0x1800098ed  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800098f2  mov     rcx, [rbx+40h]; void *
0x1800098f6  mov     [rbx+40h], rax
0x1800098fa  test    rcx, rcx
0x1800098fd  jz      short loc_180009904
0x1800098ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009904  mov     rcx, [rbx+40h]; unsigned __int16 *
0x180009908  test    rcx, rcx
0x18000990b  jnz     short loc_180009949
0x18000990d  mov     edi, 8007000Eh
0x180009912  mov     [rsp+48h+var_20], edi
0x180009916  mov     [rsp+48h+var_28], 0E6h
0x18000991e  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009925  lea     r8, aPackagebuilder_3; "PackageBuilder::CreateProvisioningPacka"...
0x18000992c  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009933  lea     ebx, [rcx+3]
0x180009936  mov     ecx, ebx
0x180009938  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000993d  lea     rdx, aFailedToAlloca_1; "    Failed to allocate _spResetClear.ge"...
0x180009944  jmp     loc_1800097CA
0x180009949  lea     r8, a0; "0"
0x180009950  mov     edx, 2; unsigned __int64
0x180009955  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000995a  mov     edi, eax
0x18000995c  test    eax, eax
0x18000995e  jns     short loc_180009999
0x180009960  mov     [rsp+48h+var_20], eax
0x180009964  mov     [rsp+48h+var_28], 0EAh
0x18000996c  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009973  lea     r8, aPackagebuilder_3; "PackageBuilder::CreateProvisioningPacka"...
0x18000997a  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009981  mov     ebx, 3
0x180009986  mov     ecx, ebx
0x180009988  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000998d  lea     rdx, aFailedToCopyDe_0; "    Failed to copy default reset clear "...
0x180009994  jmp     loc_1800097CA
0x180009999  cmp     qword ptr [rbx+30h], 0
0x18000999e  jnz     loc_180009A56
0x1800099a4  mov     rdx, rsi; struct std::nothrow_t *
0x1800099a7  mov     ecx, 8; unsigned __int64
0x1800099ac  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800099b1  mov     rcx, [rbx+30h]; void *
0x1800099b5  mov     [rbx+30h], rax
0x1800099b9  test    rcx, rcx
0x1800099bc  jz      short loc_1800099C3
0x1800099be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800099c3  mov     rcx, [rbx+30h]; unsigned __int16 *
0x1800099c7  test    rcx, rcx
0x1800099ca  jnz     short loc_180009A08
0x1800099cc  mov     edi, 8007000Eh
0x1800099d1  mov     [rsp+48h+var_20], edi
0x1800099d5  mov     [rsp+48h+var_28], 0F1h
0x1800099dd  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800099e4  lea     r8, aPackagebuilder_3; "PackageBuilder::CreateProvisioningPacka"...
0x1800099eb  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800099f2  lea     ebx, [rcx+3]
0x1800099f5  mov     ecx, ebx
0x1800099f7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800099fc  lea     rdx, aFailedToAlloca_17; "    Failed to allocate _spVersion.get()"
0x180009a03  jmp     loc_1800097CA
0x180009a08  lea     r8, a10; "1.0"
0x180009a0f  mov     rdx, r15; unsigned __int64
0x180009a12  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009a17  mov     edi, eax
0x180009a19  test    eax, eax
0x180009a1b  jns     short loc_180009A56
0x180009a1d  mov     [rsp+48h+var_20], eax
0x180009a21  mov     [rsp+48h+var_28], 0F5h
0x180009a29  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009a30  lea     r8, aPackagebuilder_3; "PackageBuilder::CreateProvisioningPacka"...
0x180009a37  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009a3e  mov     ebx, 3
0x180009a43  mov     ecx, ebx
0x180009a45  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009a4a  lea     rdx, aFailedToCopyDe_2; "    Failed to copy default version stri"...
0x180009a51  jmp     loc_1800097CA
0x180009a56  mov     ecx, 60h ; '`'; Size
0x180009a5b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009a60  mov     [rsp+48h+arg_0], rax
0x180009a65  mov     rcx, rax; this
0x180009a68  call    ??0ProvisioningPackage@@QEAA@XZ; ProvisioningPackage::ProvisioningPackage(void)
0x180009a6d  mov     rdi, rax
0x180009a70  mov     rdx, rbx; struct PackageBuilder *
0x180009a73  mov     rcx, rax; this
0x180009a76  call    ?CreateProvisioningPackage@ProvisioningPackage@@QEAAJAEBVPackageBuilder@@@Z; ProvisioningPackage::CreateProvisioningPackage(PackageBuilder const &)
0x180009a7b  mov     esi, eax
0x180009a7d  test    eax, eax
0x180009a7f  jns     short loc_180009AD9
0x180009a81  mov     rcx, [rdi]
0x180009a84  mov     rax, [rcx+80h]
0x180009a8b  mov     rcx, rdi
0x180009a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a93  mov     qword ptr [r14], 0
0x180009a9a  mov     [rsp+48h+var_20], esi
0x180009a9e  mov     [rsp+48h+var_28], 102h
0x180009aa6  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009aad  lea     r8, aPackagebuilder_3; "PackageBuilder::CreateProvisioningPacka"...
0x180009ab4  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009abb  mov     ebx, 3
0x180009ac0  mov     ecx, ebx
0x180009ac2  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009ac7  lea     rdx, aFailedToCreate_16; "    Failed to create provisioning packa"...
0x180009ace  mov     ecx, ebx
0x180009ad0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009ad5  mov     eax, esi
0x180009ad7  jmp     short loc_180009ADC
0x180009ad9  mov     [r14], rdi
0x180009adc  mov     rbx, [rsp+48h+arg_8]
0x180009ae1  mov     rsi, [rsp+48h+arg_10]
0x180009ae6  add     rsp, 30h
0x180009aea  pop     r15
0x180009aec  pop     r14
0x180009aee  pop     rdi
0x180009aef  retn
```

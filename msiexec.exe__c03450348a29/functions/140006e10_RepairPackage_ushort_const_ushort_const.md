# RepairPackage(ushort const *,ushort const *)

- ea: `0x140006e10`
- end: `0x140007107`
- name: `?RepairPackage@@YAHPEBG0@Z`
- size: `759`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400011e4`

## callees

- `0x140003883`
- `0x140003ffc`
- `0x140004ca8`
- `0x140005490`
- `0x140006384`
- `0x140006e10`
- `0x1400087bc`
- `0x1400088c0`
- `0x14000894c`
- `0x140009820`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140006f35`
- `KERNEL32!GlobalFree` at `0x140006f9e`
- `KERNEL32!GlobalFree` at `0x140006f35`
- `KERNEL32!GlobalFree` at `0x140006f9e`
- `msvcrt!_wcsicmp` at `0x140007009`
- `msvcrt!_wcsicmp` at `0x140007009`
- `msi!__imp_MsiGetProductInfoW` at `0x140006ff1`
- `msi!__imp_MsiGetProductInfoW` at `0x140006ff1`
- `msi!__imp_MsiReinstallProductW` at `0x1400070d1`
- `msi!__imp_MsiReinstallProductW` at `0x1400070d1`
- `msi!__imp_MsiSetInternalUI` at `0x1400070c2`
- `msi!__imp_MsiSetInternalUI` at `0x1400070c2`
- `msi!__imp_MsiGetProductCodeFromPackageCodeW` at `0x14000704c`
- `msi!__imp_MsiGetProductCodeFromPackageCodeW` at `0x14000704c`

## string_xrefs

- `0x140006ea8`: `REINSTALL=ALL REINSTALLMODE=%s`

## pseudocode

```c
UINT __fastcall RepairPackage(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  const unsigned __int16 *i; // rax
  unsigned __int16 v5; // cx
  UINT result; // eax
  int v7; // ebx
  unsigned int PackageCodeFromPackage; // esi
  size_t *v9; // r8
  unsigned __int16 v10; // cx
  DWORD v11; // edi
  const wchar_t *v12; // rdx
  int v13; // r8d
  INSTALLUILEVEL v14; // ecx
  DWORD pcchValueBuf[4]; // [rsp+30h] [rbp-D0h] BYREF
  HGLOBAL hMem; // [rsp+40h] [rbp-C0h]
  int v17; // [rsp+48h] [rbp-B8h]
  int v18; // [rsp+4Ch] [rbp-B4h]
  _BYTE v19[528]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t String1[40]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t pszDest[40]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR ValueBuf[40]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v23[1032]; // [rsp+350h] [rbp+250h] BYREF

  if ( IsGUID(a2) )
  {
    if ( StringCchCopyW(pszDest, 0x27u, a2) < 0 )
      return 1627;
  }
  else
  {
    for ( i = a1; i; ++i )
    {
      v5 = *i;
      if ( !*i )
        break;
      if ( (v5 | 0x20) == 0x76 )
      {
        if ( !a1 || !*a1 )
          a1 = L"PECMS";
        if ( (int)StringCchPrintfW(v23, 0x401u, L"REINSTALL=ALL REINSTALLMODE=%s", a1) >= 0 )
        {
          v7 = DoInstallPackage(a2, v23, INSTALLUILEVEL_BASIC);
          if ( v7 == 2 )
          {
            v17 = 260;
            hMem = v19;
            v18 = 260;
            if ( (unsigned int)AppendExtension(a2) )
              return DoInstallPackage((const unsigned __int16 *)hMem, v23, INSTALLUILEVEL_BASIC);
          }
          return v7;
        }
        return 1627;
      }
    }
    PackageCodeFromPackage = GetPackageCodeFromPackage(a2, String1);
    if ( PackageCodeFromPackage == 2 )
    {
      v17 = 260;
      hMem = v19;
      v18 = 260;
      if ( (unsigned int)AppendExtension(a2) )
        PackageCodeFromPackage = GetPackageCodeFromPackage((const unsigned __int16 *)hMem, String1);
    }
    if ( PackageCodeFromPackage )
      return PackageCodeFromPackage;
    if ( g_szInstanceToConfigure[0] )
    {
      memset_0(ValueBuf, 0, 0x4Eu);
      pcchValueBuf[0] = 39;
      if ( !MsiGetProductInfoW(g_szInstanceToConfigure, L"PackageCode", ValueBuf, pcchValueBuf)
        && !_wcsicmp(String1, ValueBuf) )
      {
        StringCopyWorkerW(pszDest, 0x27u, v9, g_szInstanceToConfigure, 0x26u);
        goto LABEL_28;
      }
      return 1605;
    }
    result = MsiGetProductCodeFromPackageCodeW(String1, pszDest);
    if ( result )
      return result;
  }
LABEL_28:
  if ( !a1 || (v10 = *a1) == 0 )
  {
    v11 = 682;
LABEL_39:
    v14 = g_INSTALLUILEVEL;
    if ( g_INSTALLUILEVEL == -1 )
      v14 = INSTALLUILEVEL_BASIC;
    MsiSetInternalUI(v14, 0);
    result = MsiReinstallProductW(pszDest, v11);
    if ( !result )
      return 0x8000;
    return result;
  }
  v11 = 0;
LABEL_31:
  if ( !v10 )
    goto LABEL_39;
  v12 = L"rpoedcamusv";
  v13 = 1;
  while ( *v12 )
  {
    if ( (v10 | 0x20) == *v12 )
    {
      v11 |= v13;
      v10 = *++a1;
      goto LABEL_31;
    }
    v13 *= 2;
    ++v12;
  }
  return 87;
}

```

## disassembly

```asm
0x140006e10  mov     [rsp-8+arg_10], rbx
0x140006e15  push    rbp
0x140006e16  push    rsi
0x140006e17  push    rdi
0x140006e18  push    r14
0x140006e1a  push    r15
0x140006e1c  lea     rbp, [rsp-0A70h]
0x140006e24  sub     rsp, 0B70h
0x140006e2b  mov     rax, cs:__security_cookie
0x140006e32  xor     rax, rsp
0x140006e35  mov     [rbp+0A90h+var_30], rax
0x140006e3c  mov     rbx, rcx
0x140006e3f  mov     r14, rdx
0x140006e42  mov     rcx, rdx; unsigned __int16 *
0x140006e45  call    ?IsGUID@@YA_NPEBG@Z; IsGUID(ushort const *)
0x140006e4a  xor     r15d, r15d
0x140006e4d  test    al, al
0x140006e4f  jz      short loc_140006E6D
0x140006e51  mov     r8, r14; unsigned __int16 *
0x140006e54  lea     edx, [r15+27h]; unsigned __int64
0x140006e58  lea     rcx, [rbp+0A90h+pszDest]; unsigned __int16 *
0x140006e5f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140006e64  test    eax, eax
0x140006e66  js      short loc_140006EC4
0x140006e68  jmp     loc_14000705A
0x140006e6d  mov     rax, rbx
0x140006e70  test    rax, rax
0x140006e73  jz      loc_140006F42
0x140006e79  movzx   ecx, word ptr [rax]
0x140006e7c  test    cx, cx
0x140006e7f  jz      loc_140006F42
0x140006e85  add     rax, 2
0x140006e89  or      cx, 20h
0x140006e8d  cmp     cx, 76h ; 'v'
0x140006e91  jnz     short loc_140006E70
0x140006e93  test    rbx, rbx
0x140006e96  jz      short loc_140006E9E
0x140006e98  cmp     [rbx], r15w
0x140006e9c  jnz     short loc_140006EA5
0x140006e9e  lea     rbx, aPecms; "PECMS"
0x140006ea5  mov     r9, rbx
0x140006ea8  lea     r8, aReinstallAllRe; "REINSTALL=ALL REINSTALLMODE=%s"
0x140006eaf  mov     edx, 401h; unsigned __int64
0x140006eb4  lea     rcx, [rbp+0A90h+var_840]; unsigned __int16 *
0x140006ebb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140006ec0  test    eax, eax
0x140006ec2  jns     short loc_140006ECE
0x140006ec4  mov     eax, 65Bh
0x140006ec9  jmp     loc_1400070E1
0x140006ece  mov     esi, 3
0x140006ed3  lea     rdx, [rbp+0A90h+var_840]; unsigned __int16 *
0x140006eda  mov     r8d, esi; enum tagINSTALLUILEVEL
0x140006edd  mov     rcx, r14; unsigned __int16 *
0x140006ee0  call    ?DoInstallPackage@@YAHPEBG0W4tagINSTALLUILEVEL@@@Z; DoInstallPackage(ushort const *,ushort const *,tagINSTALLUILEVEL)
0x140006ee5  mov     ebx, eax
0x140006ee7  cmp     eax, 2
0x140006eea  jnz     short loc_140006F3B
0x140006eec  mov     edi, 104h
0x140006ef1  lea     rax, [rsp+0B90h+var_B40]
0x140006ef6  lea     r8, [rsp+0B90h+hMem]
0x140006efb  mov     [rsp+0B90h+var_B48], edi
0x140006eff  mov     rcx, r14; unsigned __int16 *
0x140006f02  mov     [rsp+0B90h+hMem], rax
0x140006f07  mov     [rsp+0B90h+var_B44], edi
0x140006f0b  call    ?AppendExtension@@YA?AW4Bool@@PEBG0AEAV?$CAPITempBufferRef@G@@@Z; AppendExtension(ushort const *,ushort const *,CAPITempBufferRef<ushort> &)
0x140006f10  test    eax, eax
0x140006f12  jz      short loc_140006F2A
0x140006f14  mov     rcx, [rsp+0B90h+hMem]; unsigned __int16 *
0x140006f19  lea     rdx, [rbp+0A90h+var_840]; unsigned __int16 *
0x140006f20  mov     r8d, esi; enum tagINSTALLUILEVEL
0x140006f23  call    ?DoInstallPackage@@YAHPEBG0W4tagINSTALLUILEVEL@@@Z; DoInstallPackage(ushort const *,ushort const *,tagINSTALLUILEVEL)
0x140006f28  mov     ebx, eax
0x140006f2a  cmp     [rsp+0B90h+var_B48], edi
0x140006f2e  jle     short loc_140006F3B
0x140006f30  mov     rcx, [rsp+0B90h+hMem]; hMem
0x140006f35  call    cs:__imp_GlobalFree
0x140006f3b  mov     eax, ebx
0x140006f3d  jmp     loc_1400070E1
0x140006f42  lea     rdx, [rbp+0A90h+String1]; unsigned __int16 *
0x140006f49  mov     rcx, r14; unsigned __int16 *
0x140006f4c  call    ?GetPackageCodeFromPackage@@YAIPEBGPEAG@Z; GetPackageCodeFromPackage(ushort const *,ushort *)
0x140006f51  mov     esi, eax
0x140006f53  cmp     eax, 2
0x140006f56  jnz     short loc_140006FA4
0x140006f58  mov     edi, 104h
0x140006f5d  lea     rax, [rsp+0B90h+var_B40]
0x140006f62  lea     r8, [rsp+0B90h+hMem]
0x140006f67  mov     [rsp+0B90h+var_B48], edi
0x140006f6b  mov     rcx, r14; unsigned __int16 *
0x140006f6e  mov     [rsp+0B90h+hMem], rax
0x140006f73  mov     [rsp+0B90h+var_B44], edi
0x140006f77  call    ?AppendExtension@@YA?AW4Bool@@PEBG0AEAV?$CAPITempBufferRef@G@@@Z; AppendExtension(ushort const *,ushort const *,CAPITempBufferRef<ushort> &)
0x140006f7c  test    eax, eax
0x140006f7e  jz      short loc_140006F93
0x140006f80  mov     rcx, [rsp+0B90h+hMem]; unsigned __int16 *
0x140006f85  lea     rdx, [rbp+0A90h+String1]; unsigned __int16 *
0x140006f8c  call    ?GetPackageCodeFromPackage@@YAIPEBGPEAG@Z; GetPackageCodeFromPackage(ushort const *,ushort *)
0x140006f91  mov     esi, eax
0x140006f93  cmp     [rsp+0B90h+var_B48], edi
0x140006f97  jle     short loc_140006FA4
0x140006f99  mov     rcx, [rsp+0B90h+hMem]; hMem
0x140006f9e  call    cs:__imp_GlobalFree
0x140006fa4  test    esi, esi
0x140006fa6  jz      short loc_140006FAF
0x140006fa8  mov     eax, esi
0x140006faa  jmp     loc_1400070E1
0x140006faf  cmp     cs:?g_szInstanceToConfigure@@3PAGA, r15w; ushort near * g_szInstanceToConfigure
0x140006fb7  jz      loc_14000703E
0x140006fbd  xor     edx, edx; Val
0x140006fbf  lea     rcx, [rbp+0A90h+ValueBuf]; void *
0x140006fc6  lea     r8d, [rdx+4Eh]; Size
0x140006fca  call    memset_0
0x140006fcf  lea     r9, [rsp+0B90h+pcchValueBuf]; pcchValueBuf
0x140006fd4  mov     [rsp+0B90h+pcchValueBuf], 27h ; '''
0x140006fdc  lea     r8, [rbp+0A90h+ValueBuf]; lpValueBuf
0x140006fe3  lea     rdx, aPackagecode; "PackageCode"
0x140006fea  lea     rcx, ?g_szInstanceToConfigure@@3PAGA; szProduct
0x140006ff1  call    cs:__imp_MsiGetProductInfoW
0x140006ff7  test    eax, eax
0x140006ff9  jnz     short loc_140007034
0x140006ffb  lea     rdx, [rbp+0A90h+ValueBuf]; String2
0x140007002  lea     rcx, [rbp+0A90h+String1]; String1
0x140007009  call    cs:__imp__wcsicmp
0x14000700f  test    eax, eax
0x140007011  jnz     short loc_140007034
0x140007013  lea     r9, ?g_szInstanceToConfigure@@3PAGA; pszSrc
0x14000701a  mov     [rsp+0B90h+cchToCopy], 26h ; '&'; cchToCopy
0x140007023  lea     edx, [rax+27h]; cchDest
0x140007026  lea     rcx, [rbp+0A90h+pszDest]; pszDest
0x14000702d  call    StringCopyWorkerW
0x140007032  jmp     short loc_14000705A
0x140007034  mov     eax, 645h
0x140007039  jmp     loc_1400070E1
0x14000703e  lea     rdx, [rbp+0A90h+pszDest]
0x140007045  lea     rcx, [rbp+0A90h+String1]
0x14000704c  call    cs:__imp_MsiGetProductCodeFromPackageCodeW
0x140007052  test    eax, eax
0x140007054  jnz     loc_1400070E1
0x14000705a  test    rbx, rbx
0x14000705d  jz      short loc_1400070AA
0x14000705f  movzx   ecx, word ptr [rbx]
0x140007062  test    cx, cx
0x140007065  jz      short loc_1400070AA
0x140007067  mov     edi, r15d
0x14000706a  test    cx, cx
0x14000706d  jz      short loc_1400070AF
0x14000706f  lea     rdx, aRpoedcamusv; "rpoedcamusv"
0x140007076  mov     r8d, 1
0x14000707c  cmp     [rdx], r15w
0x140007080  jz      short loc_1400070A3
0x140007082  movzx   eax, cx
0x140007085  or      ax, 20h
0x140007089  cmp     ax, [rdx]
0x14000708c  jz      short loc_140007097
0x14000708e  add     r8d, r8d
0x140007091  add     rdx, 2
0x140007095  jmp     short loc_14000707C
0x140007097  or      edi, r8d
0x14000709a  add     rbx, 2
0x14000709e  movzx   ecx, word ptr [rbx]
0x1400070a1  jmp     short loc_14000706A
0x1400070a3  mov     eax, 57h ; 'W'
0x1400070a8  jmp     short loc_1400070E1
0x1400070aa  mov     edi, 2AAh
0x1400070af  mov     ecx, cs:?g_INSTALLUILEVEL@@3W4tagINSTALLUILEVEL@@A; tagINSTALLUILEVEL g_INSTALLUILEVEL
0x1400070b5  mov     esi, 3
0x1400070ba  cmp     ecx, 0FFFFFFFFh
0x1400070bd  cmovz   ecx, esi; dwUILevel
0x1400070c0  xor     edx, edx; phWnd
0x1400070c2  call    cs:__imp_MsiSetInternalUI
0x1400070c8  mov     edx, edi; szReinstallMode
0x1400070ca  lea     rcx, [rbp+0A90h+pszDest]; szProduct
0x1400070d1  call    cs:__imp_MsiReinstallProductW
0x1400070d7  test    eax, eax
0x1400070d9  mov     ecx, 8000h
0x1400070de  cmovz   eax, ecx
0x1400070e1  mov     rcx, [rbp+0A90h+var_30]
0x1400070e8  xor     rcx, rsp; StackCookie
0x1400070eb  call    __security_check_cookie
0x1400070f0  mov     rbx, [rsp+0B90h+arg_10]
0x1400070f8  add     rsp, 0B70h
0x1400070ff  pop     r15
0x140007101  pop     r14
0x140007103  pop     rdi
0x140007104  pop     rsi
0x140007105  pop     rbp
0x140007106  retn
```

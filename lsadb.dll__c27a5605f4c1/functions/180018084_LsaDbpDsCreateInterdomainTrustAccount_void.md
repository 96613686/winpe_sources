# LsaDbpDsCreateInterdomainTrustAccount(void *)

- ea: `0x180018084`
- end: `0x180018196`
- name: `?LsaDbpDsCreateInterdomainTrustAccount@@YAJPEAX@Z`
- size: `274`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a2bc`
- `0x18000e9f0`

## callees

- `0x18000d680`
- `0x18000fd18`
- `0x18000fd40`
- `0x180018084`
- `0x18001819c`

## import_xrefs

- `LSASRV!LsaIIsTrustedDomainsEnabled` at `0x1800180c4`
- `LSASRV!LsaIIsTrustedDomainsEnabled` at `0x1800180c4`
- `LSASRV!LsapOpenSam` at `0x1800180d8`
- `LSASRV!LsapOpenSam` at `0x1800180d8`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180018156`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180018156`

## pseudocode

```c
__int64 __fastcall LsaDbpDsCreateInterdomainTrustAccount(_BYTE *a1)
{
  int v3; // eax
  unsigned int v4; // ebx
  char v5; // bl
  int InfoTrustedDomain; // eax
  unsigned int SetITAForTrustInfo; // edi
  struct _TRUSTED_DOMAIN_FULL_INFORMATION *v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids);
  if ( !(unsigned __int8)LsaIIsTrustedDomainsEnabled() )
    return 3221225659LL;
  v3 = LsapOpenSam();
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = a1[133];
    a1[133] = 1;
    InfoTrustedDomain = LsaDbrQueryInfoTrustedDomain(
                          a1,
                          TrustedDomainFullInformation,
                          (union _LSAPR_TRUSTED_DOMAIN_INFO **)&v8);
    a1[133] = v5;
    SetITAForTrustInfo = InfoTrustedDomain;
    if ( InfoTrustedDomain >= 0 )
      SetITAForTrustInfo = LsaDbpDsCreateSetITAForTrustInfo(v8);
    if ( v8 )
      LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(8, v8);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
        SetITAForTrustInfo);
    return SetITAForTrustInfo;
  }
  else
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
        (unsigned int)v3);
    return v4;
  }
}

```

## disassembly

```asm
0x180018084  mov     [rsp+arg_8], rbx
0x180018089  mov     [rsp+arg_10], rsi
0x18001808e  push    rdi
0x18001808f  sub     rsp, 20h
0x180018093  mov     rsi, rcx
0x180018096  mov     [rsp+28h+arg_0], 0
0x18001809f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180a6  test    dword ptr [rcx+1Ch], 100h
0x1800180ad  jz      short loc_1800180C4
0x1800180af  mov     rcx, [rcx+10h]
0x1800180b3  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x1800180ba  mov     edx, 2Dh ; '-'
0x1800180bf  call    WPP_SF_
0x1800180c4  call    cs:__imp_LsaIIsTrustedDomainsEnabled
0x1800180ca  test    al, al
0x1800180cc  jnz     short loc_1800180D8
0x1800180ce  mov     eax, 0C00000BBh
0x1800180d3  jmp     loc_180018186
0x1800180d8  call    cs:__imp_LsapOpenSam
0x1800180de  mov     ebx, eax
0x1800180e0  test    eax, eax
0x1800180e2  jns     short loc_180018110
0x1800180e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180eb  test    dword ptr [rcx+1Ch], 100h
0x1800180f2  jz      short loc_18001810C
0x1800180f4  mov     rcx, [rcx+10h]
0x1800180f8  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x1800180ff  mov     edx, 2Eh ; '.'
0x180018104  mov     r9d, eax
0x180018107  call    WPP_SF_d
0x18001810c  mov     eax, ebx
0x18001810e  jmp     short loc_180018186
0x180018110  mov     bl, [rsi+85h]
0x180018116  lea     r8, [rsp+28h+arg_0]; union _LSAPR_TRUSTED_DOMAIN_INFO **
0x18001811b  mov     edx, 8; enum _TRUSTED_INFORMATION_CLASS
0x180018120  mov     byte ptr [rsi+85h], 1
0x180018127  mov     rcx, rsi; void *
0x18001812a  call    ?LsaDbrQueryInfoTrustedDomain@@YAJPEAXW4_TRUSTED_INFORMATION_CLASS@@PEAPEAT_LSAPR_TRUSTED_DOMAIN_INFO@@@Z; LsaDbrQueryInfoTrustedDomain(void *,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO * *)
0x18001812f  mov     [rsi+85h], bl
0x180018135  mov     edi, eax
0x180018137  test    eax, eax
0x180018139  js      short loc_180018147
0x18001813b  mov     rcx, [rsp+28h+arg_0]; struct _TRUSTED_DOMAIN_FULL_INFORMATION *
0x180018140  call    ?LsaDbpDsCreateSetITAForTrustInfo@@YAJPEAU_TRUSTED_DOMAIN_FULL_INFORMATION@@@Z; LsaDbpDsCreateSetITAForTrustInfo(_TRUSTED_DOMAIN_FULL_INFORMATION *)
0x180018145  mov     edi, eax
0x180018147  mov     rdx, [rsp+28h+arg_0]
0x18001814c  test    rdx, rdx
0x18001814f  jz      short loc_18001815C
0x180018151  mov     ecx, 8
0x180018156  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO
0x18001815c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018163  test    dword ptr [rcx+1Ch], 100h
0x18001816a  jz      short loc_180018184
0x18001816c  mov     rcx, [rcx+10h]
0x180018170  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180018177  mov     edx, 2Fh ; '/'
0x18001817c  mov     r9d, edi
0x18001817f  call    WPP_SF_d
0x180018184  mov     eax, edi
0x180018186  mov     rbx, [rsp+28h+arg_8]
0x18001818b  mov     rsi, [rsp+28h+arg_10]
0x180018190  add     rsp, 20h
0x180018194  pop     rdi
0x180018195  retn
```

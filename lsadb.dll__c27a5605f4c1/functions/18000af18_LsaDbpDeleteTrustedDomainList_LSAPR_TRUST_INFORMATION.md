# LsaDbpDeleteTrustedDomainList(_LSAPR_TRUST_INFORMATION *)

- ea: `0x18000af18`
- end: `0x18000b03b`
- name: `?LsaDbpDeleteTrustedDomainList@@YAJPEAU_LSAPR_TRUST_INFORMATION@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(struct _LSAPR_TRUST_INFORMATION *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180013cbc`
- `0x180015bf0`

## callees

- `0x18000988c`
- `0x18000af18`
- `0x18000beb4`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fde0`
- `0x18002a7f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b029`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b029`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000b020`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000b020`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x18000afa1`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x18000afa1`
- `LSASRV!LsapDbExpIsCacheValid` at `0x18000af7f`
- `LSASRV!LsapDbExpIsCacheValid` at `0x18000af7f`

## pseudocode

```c
__int64 __fastcall LsaDbpDeleteTrustedDomainList(struct _LSAPR_TRUST_INFORMATION *a1)
{
  int v1; // edi
  struct _UNICODE_STRING *v4; // rbx
  __int64 v5; // rax
  FTCache *v6; // rcx
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  hMem = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids, a1);
  }
  LsaDbLogInfoTrustedDomainList();
  if ( (unsigned __int8)LsapDbExpIsCacheValid(2) )
  {
    v1 = LsaDbpLookupEntryTrustedDomainList(a1, (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **)&hMem);
    if ( v1 >= 0 )
    {
      v4 = (struct _UNICODE_STRING *)hMem;
      v5 = *(_QWORD *)hMem;
      if ( *(HLOCAL *)(*(_QWORD *)hMem + 8LL) != hMem || (v6 = (FTCache *)*((_QWORD *)hMem + 1), *(HLOCAL *)v6 != hMem) )
        __fastfail(3u);
      *(_QWORD *)v6 = v5;
      *(_QWORD *)(v5 + 8) = v6;
      --LsaDbpTrustedDomainList;
      if ( DcInRootDomain )
        FTCache::Remove(v6, v4 + 1);
      _fgu__LSAPR_TRUSTED_DOMAIN_INFO(&v4[1], 6);
      LocalFree(v4);
    }
    else
    {
      LsapDbExpMakeCacheInvalid(2);
    }
  }
  LsaDbLogInfoTrustedDomainList();
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
      (unsigned int)v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000af18  mov     [rsp+arg_0], rbx
0x18000af1d  push    rdi
0x18000af1e  sub     rsp, 20h
0x18000af22  xor     edi, edi
0x18000af24  mov     rbx, rcx
0x18000af27  mov     [rsp+28h+hMem], rdi
0x18000af2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af33  test    dword ptr [rcx+1Ch], 100h
0x18000af3a  jz      short loc_18000AF75
0x18000af3c  mov     rcx, [rcx+10h]
0x18000af40  lea     edx, [rdi+22h]
0x18000af43  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000af4a  call    WPP_SF_
0x18000af4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af56  test    dword ptr [rcx+1Ch], 100h
0x18000af5d  jz      short loc_18000AF75
0x18000af5f  mov     rcx, [rcx+10h]
0x18000af63  lea     edx, [rdi+23h]
0x18000af66  mov     r9, rbx
0x18000af69  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000af70  call    WPP_SF_Z
0x18000af75  call    ?LsaDbLogInfoTrustedDomainList@@YAXXZ; LsaDbLogInfoTrustedDomainList(void)
0x18000af7a  mov     ecx, 2
0x18000af7f  call    cs:__imp_LsapDbExpIsCacheValid
0x18000af85  test    al, al
0x18000af87  jz      short loc_18000AFA7
0x18000af89  lea     rdx, [rsp+28h+hMem]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18000af8e  mov     rcx, rbx; struct _LSAPR_TRUST_INFORMATION *
0x18000af91  call    ?LsaDbpLookupEntryTrustedDomainList@@YAJPEAU_LSAPR_TRUST_INFORMATION@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupEntryTrustedDomainList(_LSAPR_TRUST_INFORMATION *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18000af96  mov     edi, eax
0x18000af98  test    eax, eax
0x18000af9a  jns     short loc_18000AFE1
0x18000af9c  mov     ecx, 2
0x18000afa1  call    cs:__imp_LsapDbExpMakeCacheInvalid
0x18000afa7  call    ?LsaDbLogInfoTrustedDomainList@@YAXXZ; LsaDbLogInfoTrustedDomainList(void)
0x18000afac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afb3  test    dword ptr [rcx+1Ch], 100h
0x18000afba  jz      short loc_18000AFD4
0x18000afbc  mov     rcx, [rcx+10h]
0x18000afc0  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000afc7  mov     edx, 24h ; '$'
0x18000afcc  mov     r9d, edi
0x18000afcf  call    WPP_SF_d
0x18000afd4  mov     rbx, [rsp+28h+arg_0]
0x18000afd9  mov     eax, edi
0x18000afdb  add     rsp, 20h
0x18000afdf  pop     rdi
0x18000afe0  retn
0x18000afe1  mov     rbx, [rsp+28h+hMem]
0x18000afe6  mov     rax, [rbx]
0x18000afe9  cmp     [rax+8], rbx
0x18000afed  jnz     short loc_18000B034
0x18000afef  mov     rcx, [rbx+8]; this
0x18000aff3  cmp     [rcx], rbx
0x18000aff6  jnz     short loc_18000B034
0x18000aff8  mov     [rcx], rax
0x18000affb  mov     [rax+8], rcx
0x18000afff  dec     dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000b005  cmp     cs:?DcInRootDomain@@3EA, 0; uchar DcInRootDomain
0x18000b00c  jz      short loc_18000B017
0x18000b00e  lea     rdx, [rbx+10h]; struct _UNICODE_STRING *
0x18000b012  call    ?Remove@FTCache@@QEAAJPEAU_UNICODE_STRING@@@Z; FTCache::Remove(_UNICODE_STRING *)
0x18000b017  lea     rcx, [rbx+10h]
0x18000b01b  mov     edx, 6
0x18000b020  call    cs:__imp__fgu__LSAPR_TRUSTED_DOMAIN_INFO
0x18000b026  mov     rcx, rbx; hMem
0x18000b029  call    cs:__imp_LocalFree
0x18000b02f  jmp     loc_18000AFA7
0x18000b034  mov     ecx, 3
0x18000b039  int     29h; Win8: RtlFailFast(ecx)
```

# LsaDbpPurgeTrustedDomainCache(void)

- ea: `0x18000c400`
- end: `0x18000c4e9`
- name: `?LsaDbpPurgeTrustedDomainCache@@YAXXZ`
- size: `233`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180009b24`
- `0x1800136d4`
- `0x180016040`
- `0x180026810`

## callees

- `0x18000c400`
- `0x18000fd18`
- `0x180026594`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c478`
- `LSASRV!LsapDbExpIsCacheBuilding` at `0x18000c4a7`
- `LSASRV!LsapDbExpIsCacheBuilding` at `0x18000c4a7`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000c46f`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000c46f`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x18000c4b3`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x18000c4b3`

## pseudocode

```c
void LsaDbpPurgeTrustedDomainCache(void)
{
  char *v0; // rbx
  _QWORD *v1; // rax
  HLOCAL *v2; // rcx

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
  LsaDbpForestTrustCacheSetInvalid();
  while ( 1 )
  {
    v0 = (char *)hMem;
    if ( hMem == &hMem )
      break;
    v1 = *(_QWORD **)hMem;
    if ( *(HLOCAL *)(*(_QWORD *)hMem + 8LL) != hMem || (v2 = (HLOCAL *)*((_QWORD *)hMem + 1), *v2 != hMem) )
      __fastfail(3u);
    *v2 = v1;
    v1[1] = v2;
    --LsaDbpTrustedDomainList;
    _fgu__LSAPR_TRUSTED_DOMAIN_INFO(v0 + 16, 6);
    LocalFree(v0);
  }
  qword_1800480C0 = (__int64)&hMem;
  hMem = &hMem;
  LsaDbpTrustedDomainList = 0;
  if ( !(unsigned __int8)LsapDbExpIsCacheBuilding(2) )
    LsapDbExpMakeCacheInvalid(2);
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
}

```

## disassembly

```asm
0x18000c400  mov     [rsp+arg_0], rbx
0x18000c405  push    rdi
0x18000c406  sub     rsp, 20h
0x18000c40a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c411  test    dword ptr [rcx+1Ch], 100h
0x18000c418  jz      short loc_18000C42F
0x18000c41a  mov     rcx, [rcx+10h]
0x18000c41e  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000c425  mov     edx, 30h ; '0'
0x18000c42a  call    WPP_SF_
0x18000c42f  call    ?LsaDbpForestTrustCacheSetInvalid@@YAXXZ; LsaDbpForestTrustCacheSetInvalid(void)
0x18000c434  lea     rdi, hMem
0x18000c43b  mov     rbx, cs:hMem
0x18000c442  cmp     rbx, rdi
0x18000c445  jz      short loc_18000C487
0x18000c447  mov     rax, [rbx]
0x18000c44a  cmp     [rax+8], rbx
0x18000c44e  jnz     short loc_18000C480
0x18000c450  mov     rcx, [rbx+8]
0x18000c454  cmp     [rcx], rbx
0x18000c457  jnz     short loc_18000C480
0x18000c459  mov     [rcx], rax
0x18000c45c  mov     edx, 6
0x18000c461  mov     [rax+8], rcx
0x18000c465  lea     rcx, [rbx+10h]
0x18000c469  dec     dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000c46f  call    cs:__imp__fgu__LSAPR_TRUSTED_DOMAIN_INFO
0x18000c475  mov     rcx, rbx; hMem
0x18000c478  call    cs:__imp_LocalFree
0x18000c47e  jmp     short loc_18000C43B
0x18000c480  mov     ecx, 3
0x18000c485  int     29h; Win8: RtlFailFast(ecx)
0x18000c487  mov     ebx, 2
0x18000c48c  mov     cs:qword_1800480C0, rdi
0x18000c493  mov     ecx, ebx
0x18000c495  mov     cs:hMem, rdi
0x18000c49c  mov     cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A, 0; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000c4a7  call    cs:__imp_LsapDbExpIsCacheBuilding
0x18000c4ad  test    al, al
0x18000c4af  jnz     short loc_18000C4B9
0x18000c4b1  mov     ecx, ebx
0x18000c4b3  call    cs:__imp_LsapDbExpMakeCacheInvalid
0x18000c4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4c0  test    dword ptr [rcx+1Ch], 100h
0x18000c4c7  jz      short loc_18000C4DE
0x18000c4c9  mov     rcx, [rcx+10h]
0x18000c4cd  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000c4d4  mov     edx, 31h ; '1'
0x18000c4d9  call    WPP_SF_
0x18000c4de  mov     rbx, [rsp+28h+arg_0]
0x18000c4e3  add     rsp, 20h
0x18000c4e7  pop     rdi
0x18000c4e8  retn
```

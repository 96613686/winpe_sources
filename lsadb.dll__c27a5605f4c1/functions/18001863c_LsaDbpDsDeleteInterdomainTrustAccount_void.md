# LsaDbpDsDeleteInterdomainTrustAccount(void *)

- ea: `0x18001863c`
- end: `0x1800188a6`
- name: `?LsaDbpDsDeleteInterdomainTrustAccount@@YAJPEAX@Z`
- size: `618`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180015bf0`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000d680`
- `0x18000fd18`
- `0x18000fd40`
- `0x180012fa4`
- `0x180015748`
- `0x180015790`
- `0x18001863c`
- `0x180019c64`
- `0x18003ad30`

## import_xrefs

- `LSASRV!LsapOpenSam` at `0x1800186af`
- `LSASRV!LsapOpenSam` at `0x1800186af`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180018859`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180018859`
- `LSASRV!LsapAllocateLsaHeap` at `0x180018735`
- `LSASRV!LsapAllocateLsaHeap` at `0x180018735`
- `LSASRV!LsapFreeLsaHeap` at `0x18001883f`
- `LSASRV!LsapFreeLsaHeap` at `0x18001883f`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180018810`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180018810`
- `ntdll!RtlInitUnicodeString` at `0x18001878d`
- `ntdll!RtlInitUnicodeString` at `0x18001878d`
- `SAMSRV!SamrCloseHandle` at `0x18001881b`
- `SAMSRV!SamrCloseHandle` at `0x18001881b`
- `SAMSRV!SamrDeleteUser` at `0x1800187b4`
- `SAMSRV!SamrDeleteUser` at `0x1800187b4`

## pseudocode

```c
__int64 __fastcall LsaDbpDsDeleteInterdomainTrustAccount(_BYTE *a1)
{
  int v2; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  char v6; // bl
  int v7; // eax
  union _LSAPR_TRUSTED_DOMAIN_INFO *v8; // rdx
  __int64 v9; // rax
  __int64 LsaHeap; // rax
  _BYTE *v11; // rbx
  enum _SECPKG_NAME_TYPE v12; // edx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  union _LSAPR_TRUSTED_DOMAIN_INFO *v19; // [rsp+38h] [rbp-C8h] BYREF
  void *v20; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v22[528]; // [rsp+60h] [rbp-A0h] BYREF

  v18 = 0;
  DestinationString = 0;
  v20 = 0;
  v19 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids);
  v2 = LsapOpenSam();
  v18 = v2;
  if ( v2 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v4 = 56;
      v5 = (unsigned int)v2;
LABEL_27:
      WPP_SF_d(v3[2], v4, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids, v5);
      return v18;
    }
    return v18;
  }
  v6 = a1[133];
  a1[133] = 1;
  v7 = LsaDbrQueryInfoTrustedDomain(a1, TrustedDomainInformationEx, &v19);
  v18 = v7;
  a1[133] = v6;
  if ( v7 < 0 )
    goto LABEL_22;
  memset_0(v22, 0, 0x204u);
  v8 = v19;
  v9 = *((unsigned __int16 *)v19 + 8);
  if ( (unsigned __int16)v9 < 0x202u )
  {
    v11 = v22;
  }
  else
  {
    LsaHeap = LsapAllocateLsaHeap(v9 + 4);
    v8 = v19;
    v11 = (_BYTE *)LsaHeap;
    if ( !LsaHeap )
      v18 = -1073741670;
  }
  if ( (v18 & 0x80000000) == 0 )
  {
    memcpy_0(v11, *((const void **)v8 + 3), *((unsigned __int16 *)v8 + 8));
    *(_WORD *)&v11[2 * ((unsigned __int64)*((unsigned __int16 *)v19 + 8) >> 1)] = 36;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)v11);
    LsaDbpSaveDsThreadState();
    v13 = LsaDbpDsOpenSamUser(&DestinationString, v12, &v20);
    v18 = v13;
    if ( v13 < 0 )
    {
      if ( v13 == -1073741709 )
        v18 = 0;
    }
    else
    {
      v16 = SamrDeleteUser(&v20);
      v18 = v16;
      if ( v16 < 0 )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_ZD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            (unsigned int)&WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
            (unsigned int)&DestinationString,
            v16);
        SpmpEventWrite((const struct _EVENT_DESCRIPTOR *)LSAEVENT_ITA_NOT_DELETED, L"ub", v19, 4, &v18);
        SamrCloseHandle(&v20);
      }
    }
    if ( v11 != v22 )
      LsapFreeLsaHeap(v11, v14, v15);
    LsaDbpRestoreDsThreadState();
LABEL_22:
    v8 = v19;
  }
  if ( v8 )
    LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(6, v8);
  v3 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    v5 = v18;
    v4 = 58;
    goto LABEL_27;
  }
  return v18;
}

```

## disassembly

```asm
0x18001863c  push    rbp
0x18001863e  push    rbx
0x18001863f  push    rdi
0x180018640  push    r14
0x180018642  lea     rbp, [rsp-188h]
0x18001864a  sub     rsp, 288h
0x180018651  mov     rax, cs:__security_cookie
0x180018658  xor     rax, rsp
0x18001865b  mov     [rbp+1A0h+var_30], rax
0x180018662  xorps   xmm0, xmm0
0x180018665  mov     [rsp+2A0h+var_270], 0
0x18001866d  movups  xmmword ptr [rsp+2A0h+DestinationString.Length], xmm0
0x180018672  mov     rdi, rcx
0x180018675  mov     [rsp+2A0h+var_260], 0
0x18001867e  mov     [rsp+2A0h+var_268], 0
0x180018687  mov     rcx, cs:WPP_GLOBAL_Control
0x18001868e  mov     r14d, 100h
0x180018694  test    [rcx+1Ch], r14d
0x180018698  jz      short loc_1800186AF
0x18001869a  mov     rcx, [rcx+10h]
0x18001869e  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x1800186a5  mov     edx, 37h ; '7'
0x1800186aa  call    WPP_SF_
0x1800186af  call    cs:__imp_LsapOpenSam
0x1800186b5  mov     [rsp+2A0h+var_270], eax
0x1800186b9  test    eax, eax
0x1800186bb  jns     short loc_1800186DB
0x1800186bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186c4  test    [rcx+1Ch], r14d
0x1800186c8  jz      loc_180018886
0x1800186ce  mov     edx, 38h ; '8'
0x1800186d3  mov     r9d, eax
0x1800186d6  jmp     loc_180018876
0x1800186db  mov     bl, [rdi+85h]
0x1800186e1  lea     r8, [rsp+2A0h+var_268]; union _LSAPR_TRUSTED_DOMAIN_INFO **
0x1800186e6  mov     edx, 6; enum _TRUSTED_INFORMATION_CLASS
0x1800186eb  mov     byte ptr [rdi+85h], 1
0x1800186f2  mov     rcx, rdi; void *
0x1800186f5  call    ?LsaDbrQueryInfoTrustedDomain@@YAJPEAXW4_TRUSTED_INFORMATION_CLASS@@PEAPEAT_LSAPR_TRUSTED_DOMAIN_INFO@@@Z; LsaDbrQueryInfoTrustedDomain(void *,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO * *)
0x1800186fa  mov     [rsp+2A0h+var_270], eax
0x1800186fe  mov     [rdi+85h], bl
0x180018704  test    eax, eax
0x180018706  js      loc_18001884A
0x18001870c  xor     edx, edx; Val
0x18001870e  lea     rcx, [rsp+2A0h+var_240]; void *
0x180018713  mov     r8d, 204h; Size
0x180018719  call    memset_0
0x18001871e  mov     rdx, [rsp+2A0h+var_268]
0x180018723  mov     ecx, 202h
0x180018728  movzx   eax, word ptr [rdx+10h]
0x18001872c  cmp     ax, cx
0x18001872f  jb      short loc_180018752
0x180018731  lea     rcx, [rax+4]
0x180018735  call    cs:__imp_LsapAllocateLsaHeap
0x18001873b  mov     rdx, [rsp+2A0h+var_268]
0x180018740  mov     rbx, rax
0x180018743  test    rax, rax
0x180018746  jnz     short loc_180018757
0x180018748  mov     [rsp+2A0h+var_270], 0C000009Ah
0x180018750  jmp     short loc_180018757
0x180018752  lea     rbx, [rsp+2A0h+var_240]
0x180018757  cmp     [rsp+2A0h+var_270], 0
0x18001875c  jl      loc_18001884F
0x180018762  movzx   r8d, word ptr [rdx+10h]; Size
0x180018767  mov     rcx, rbx; void *
0x18001876a  mov     rdx, [rdx+18h]; Src
0x18001876e  call    memcpy_0
0x180018773  mov     rax, [rsp+2A0h+var_268]
0x180018778  mov     rdx, rbx; SourceString
0x18001877b  movzx   ecx, word ptr [rax+10h]
0x18001877f  shr     rcx, 1
0x180018782  mov     word ptr [rbx+rcx*2], 24h ; '$'
0x180018788  lea     rcx, [rsp+2A0h+DestinationString]; DestinationString
0x18001878d  call    cs:__imp_RtlInitUnicodeString
0x180018793  call    ?LsaDbpSaveDsThreadState@@YAXXZ; LsaDbpSaveDsThreadState(void)
0x180018798  lea     r8, [rsp+2A0h+var_260]; void **
0x18001879d  lea     rcx, [rsp+2A0h+DestinationString]; struct _UNICODE_STRING *
0x1800187a2  call    ?LsaDbpDsOpenSamUser@@YAJPEAU_UNICODE_STRING@@W4_SECPKG_NAME_TYPE@@PEAPEAX@Z; LsaDbpDsOpenSamUser(_UNICODE_STRING *,_SECPKG_NAME_TYPE,void * *)
0x1800187a7  mov     [rsp+2A0h+var_270], eax
0x1800187ab  test    eax, eax
0x1800187ad  js      short loc_180018823
0x1800187af  lea     rcx, [rsp+2A0h+var_260]
0x1800187b4  call    cs:__imp_SamrDeleteUser
0x1800187ba  mov     [rsp+2A0h+var_270], eax
0x1800187be  test    eax, eax
0x1800187c0  jns     short loc_180018832
0x1800187c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187c9  test    [rcx+1Ch], r14d
0x1800187cd  jz      short loc_1800187ED
0x1800187cf  mov     rcx, [rcx+10h]
0x1800187d3  lea     r9, [rsp+2A0h+DestinationString]
0x1800187d8  mov     edx, 39h ; '9'
0x1800187dd  mov     dword ptr [rsp+2A0h+var_280], eax
0x1800187e1  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x1800187e8  call    WPP_SF_ZD
0x1800187ed  mov     r8, [rsp+2A0h+var_268]
0x1800187f2  lea     rax, [rsp+2A0h+var_270]
0x1800187f7  mov     r9d, 4
0x1800187fd  mov     [rsp+2A0h+var_280], rax
0x180018802  lea     rdx, aUb; "ub"
0x180018809  lea     rcx, LSAEVENT_ITA_NOT_DELETED
0x180018810  call    cs:__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180018816  lea     rcx, [rsp+2A0h+var_260]
0x18001881b  call    cs:__imp_SamrCloseHandle
0x180018821  jmp     short loc_180018832
0x180018823  cmp     eax, 0C0000073h
0x180018828  jnz     short loc_180018832
0x18001882a  mov     [rsp+2A0h+var_270], 0
0x180018832  lea     rax, [rsp+2A0h+var_240]
0x180018837  cmp     rbx, rax
0x18001883a  jz      short loc_180018845
0x18001883c  mov     rcx, rbx
0x18001883f  call    cs:__imp_LsapFreeLsaHeap
0x180018845  call    ?LsaDbpRestoreDsThreadState@@YAXXZ; LsaDbpRestoreDsThreadState(void)
0x18001884a  mov     rdx, [rsp+2A0h+var_268]
0x18001884f  test    rdx, rdx
0x180018852  jz      short loc_18001885F
0x180018854  mov     ecx, 6
0x180018859  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO
0x18001885f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018866  test    [rcx+1Ch], r14d
0x18001886a  jz      short loc_180018886
0x18001886c  mov     r9d, [rsp+2A0h+var_270]
0x180018871  mov     edx, 3Ah ; ':'
0x180018876  mov     rcx, [rcx+10h]
0x18001887a  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180018881  call    WPP_SF_d
0x180018886  mov     eax, [rsp+2A0h+var_270]
0x18001888a  mov     rcx, [rbp+1A0h+var_30]
0x180018891  xor     rcx, rsp; StackCookie
0x180018894  call    __security_check_cookie
0x180018899  add     rsp, 288h
0x1800188a0  pop     r14
0x1800188a2  pop     rdi
0x1800188a3  pop     rbx
0x1800188a4  pop     rbp
0x1800188a5  retn
```

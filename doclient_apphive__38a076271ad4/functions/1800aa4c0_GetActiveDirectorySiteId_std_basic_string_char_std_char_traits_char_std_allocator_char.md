# GetActiveDirectorySiteId(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800aa4c0`
- end: `0x1800aa9f9`
- name: `?GetActiveDirectorySiteId@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1337`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d68a8`

## callees

- `0x18000a4fc`
- `0x18000a5e4`
- `0x18000ecf0`
- `0x18000ef98`
- `0x18001d5fc`
- `0x18003d7d4`
- `0x1800a1ea4`
- `0x1800a1f08`
- `0x1800aa4c0`
- `0x1800adfcc`
- `0x1800ae66c`
- `0x1800ae878`
- `0x1800d1bb0`
- `0x1800f82f0`
- `0x180108e50`
- `0x180109290`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa891`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa90d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa891`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa90d`
- `logoncli!DsGetDcNameW` at `0x1800aa52a`
- `logoncli!DsGetDcNameW` at `0x1800aa52a`
- `netutils!NetApiBufferFree` at `0x1800aa965`
- `netutils!NetApiBufferFree` at `0x1800aa965`

## string_xrefs

- `0x1800aa7e6`: `GetActiveDirectorySiteId`
- `0x1800aa8ee`: `GetActiveDirectorySiteId`
- `0x1800aa950`: `GetActiveDirectorySiteId`
- `0x1800aa97e`: `GetActiveDirectorySiteId`
- `0x1800aa9b3`: `GetActiveDirectorySiteId`
- `0x1800aa797`: `,cn=sites,cn=configuration,dc=`
- `0x1800aa8e1`: `IDirectoryObject::GetObjectAttributes failed; hr = %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetActiveDirectorySiteId(_QWORD *a1)
{
  _QWORD *v1; // rsi
  _BYTE *v2; // rax
  signed int DcNameW; // eax
  signed int v4; // ebx
  unsigned __int64 v5; // rdi
  LPWSTR DnsForestName; // rdx
  size_t v7; // r15
  __int64 v8; // r8
  __int64 v9; // r8
  __int128 *p_Src; // r14
  char *v11; // rbx
  __int64 traits_2_unsigned_short; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  __int128 *v15; // rax
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // r8
  __int128 *v18; // rax
  _QWORD *v19; // rcx
  unsigned __int64 v20; // r12
  wchar_t *v21; // rax
  wchar_t *v22; // r13
  const wchar_t *v23; // rdx
  __int64 v24; // r14
  __int64 v25; // rdx
  __int64 v26; // rax
  HLOCAL v27; // rcx
  CGuidToString *v28; // rax
  HLOCAL v29; // rcx
  _QWORD *v30; // rcx
  int DomainControllerInfo; // [rsp+30h] [rbp-D8h]
  HLOCAL *p_hMem; // [rsp+48h] [rbp-C0h] BYREF
  void *v34; // [rsp+50h] [rbp-B8h] BYREF
  char v35; // [rsp+58h] [rbp-B0h]
  _QWORD v36[7]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD *v37; // [rsp+B0h] [rbp-58h]
  PDOMAIN_CONTROLLER_INFOW v38; // [rsp+B8h] [rbp-50h] BYREF
  __int128 Src; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int64 v40; // [rsp+D0h] [rbp-38h]
  unsigned __int64 v41; // [rsp+D8h] [rbp-30h]
  HLOCAL hMem; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD *v43; // [rsp+E8h] [rbp-20h] BYREF
  int v44; // [rsp+F0h] [rbp-18h] BYREF
  _OWORD v45[2]; // [rsp+F8h] [rbp-10h] BYREF
  const wchar_t *v46; // [rsp+118h] [rbp+10h] BYREF

  v1 = a1;
  a1[2] = 0;
  v2 = a1;
  if ( a1[3] > 0xFu )
    v2 = (_BYTE *)*a1;
  *v2 = 0;
  v38 = 0;
  DcNameW = DsGetDcNameW(0, 0, 0, 0, 0x10u, &v38);
  v4 = (unsigned __int16)DcNameW | 0x80070000;
  if ( DcNameW <= 0 )
    v4 = DcNameW;
  if ( v4 >= 0 )
  {
    v4 = v38->ClientSiteName == 0 ? 0x80004005 : 0;
    if ( !v38->ClientSiteName )
    {
      LogMessage(
        3u,
        "GetActiveDirectorySiteId",
        0x94u,
        "DsGetDcName succeeded but no site is associated with the local subnet");
LABEL_58:
      NetApiBufferFree(v38);
      goto LABEL_60;
    }
    v5 = 0;
    DnsForestName = v38->DnsForestName;
    Src = 0;
    v40 = 0;
    v41 = 0;
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( DnsForestName[v8] );
    std::wstring::_Construct<1,wchar_t const *>(&Src);
    while ( 1 )
    {
      p_Src = &Src;
      if ( v41 > 7 )
        p_Src = (__int128 *)Src;
      if ( !v40 )
        break;
      if ( v5 > v40 - 1 )
        break;
      v11 = (char *)p_Src + 2 * v40;
      traits_2_unsigned_short = anonymous_namespace_::__std_search_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                  (char *)p_Src + 2 * v5,
                                  v11,
                                  v9,
                                  1);
      if ( (char *)traits_2_unsigned_short == v11 )
        break;
      v5 = (traits_2_unsigned_short - (__int64)p_Src) >> 1;
      if ( v5 == -1 )
        break;
      v13 = v40;
      if ( v40 < v5 )
        std::_String_val<std::_Simple_types<char>>::_Xran();
      v14 = 1;
      if ( v40 == v5 )
        v14 = v40 - v5;
      if ( v14 == 4 )
      {
        v15 = &Src;
        if ( v41 > 7 )
          v15 = (__int128 *)Src;
        *(_QWORD *)((char *)v15 + 2 * v5) = 0x3D00630064002CLL;
      }
      else
      {
        v16 = v40 - v14;
        v17 = v40 - v14 - v5;
        if ( v14 <= 4 )
        {
          v20 = 4 - v14;
          if ( 4 - v14 > v41 - v40 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__replace___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_KQEB_W0_Z__K_KPEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__replace_01_QEAAAEAV01_0_KQEB_W0_Z_11PEB_W1_Z(
              &Src,
              v14,
              DomainControllerInfo,
              4);
          }
          else
          {
            v40 += v20;
            v21 = (wchar_t *)&Src;
            if ( v41 > 7 )
              v21 = (wchar_t *)Src;
            v22 = &v21[v5];
            v23 = &v22[v14];
            if ( L"" <= v22 || L",dc=" > &v21[v13] )
            {
              v24 = 4;
            }
            else if ( v23 > L",dc=" )
            {
              v24 = v23 - L",dc=";
            }
            else
            {
              v24 = 0;
            }
            memmove((void *)&v23[v20], v23, 2 * v17 + 2);
            memmove(v22, L",dc=", 2 * v24);
            memmove(&v22[v24], &aDc[v24 + v20], 2 * (4 - v24));
          }
        }
        else
        {
          v18 = &Src;
          if ( v41 > 7 )
            v18 = (__int128 *)Src;
          v19 = (_QWORD *)((char *)v18 + 2 * v5);
          *v19 = 0x3D00630064002CLL;
          memmove(v19 + 1, (char *)v19 + 2 * v14, 2 * v17 + 2);
          v40 = v16 + 4;
        }
      }
    }
    memset(v45, 0, sizeof(v45));
    std::wstring::_Construct<1,wchar_t const *>(v45);
    std::wstring::append(v45, v38->ClientSiteName);
    std::wstring::append(v45, L",cn=sites,cn=configuration,dc=");
    std::wstring::operator+=(v45);
    v43 = 0;
    v36[0] = ___7___Func_impl_no_alloc_V_lambda_1___7__GetActiveDirectorySiteId__YAJAEAV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___Z_J__V_std__6B_;
    v36[1] = v45;
    v36[2] = &v43;
    v37 = v36;
    v4 = docli::CComTimeout::MakeComCall(
           v36,
           "CoGetObject(clientSiteDN.data(), nullptr, IID_PPV_ARGS(&spDirObj))",
           "GetActiveDirectorySiteId",
           119);
    if ( v37 )
    {
      LOBYTE(v25) = v37 != v36;
      (*(void (__fastcall **)(_QWORD *, __int64))(*v37 + 32LL))(v37, v25);
    }
    if ( v4 < 0 )
    {
LABEL_54:
      v30 = v43;
      if ( v43 )
      {
        v43 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
      }
      std::wstring::~wstring(v45);
      std::wstring::~wstring(&Src);
      goto LABEL_58;
    }
    v46 = L"objectGUID";
    v44 = 1;
    hMem = 0;
    v26 = *v43;
    p_hMem = &hMem;
    v34 = 0;
    v35 = 1;
    v4 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t **, __int64, void **, int *))(v26 + 32))(
           v43,
           &v46,
           1,
           &v34,
           &v44);
    if ( v35 )
    {
      v27 = *p_hMem;
      *p_hMem = v34;
      if ( v27 )
        LocalFree(v27);
    }
    if ( v4 >= 0 )
    {
      if ( hMem && *((_DWORD *)hMem + 3) == 8 )
      {
        v4 = 0;
        v28 = CGuidToString::CGuidToString(
                (CGuidToString *)&p_hMem,
                *(const struct _GUID **)(*((_QWORD *)hMem + 2) + 16LL));
        do
          ++v7;
        while ( *((_BYTE *)v28 + v7) );
        std::string::assign(v1, v28, v7);
LABEL_52:
        v29 = hMem;
        hMem = 0;
        if ( v29 )
          LocalFree(v29);
        goto LABEL_54;
      }
      v4 = -2147023728;
    }
    LogMessage(3u, "GetActiveDirectorySiteId", 0x8Eu, "IDirectoryObject::GetObjectAttributes failed; hr = %x", v4);
    goto LABEL_52;
  }
  LogMessage(3u, "GetActiveDirectorySiteId", 0x9Au, "DsGetDcName failed; hr = %x", v4);
LABEL_60:
  if ( v1[3] > 0xFu )
    v1 = (_QWORD *)*v1;
  LogResult(5u, "GetActiveDirectorySiteId", 0x9Cu, v4, "szID = %s", (const char *)v1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800aa4c0  mov     rax, rsp
0x1800aa4c3  mov     [rax+10h], rbx
0x1800aa4c7  mov     [rax+18h], rsi
0x1800aa4cb  mov     [rax+20h], rdi
0x1800aa4cf  push    rbp
0x1800aa4d0  push    r12
0x1800aa4d2  push    r13
0x1800aa4d4  push    r14
0x1800aa4d6  push    r15
0x1800aa4d8  lea     rbp, [rax-48h]
0x1800aa4dc  sub     rsp, 120h
0x1800aa4e3  mov     rax, cs:__security_cookie
0x1800aa4ea  xor     rax, rsp
0x1800aa4ed  mov     [rbp+40h+var_28], rax
0x1800aa4f1  mov     rsi, rcx
0x1800aa4f4  xor     r12d, r12d
0x1800aa4f7  mov     [rcx+10h], r12
0x1800aa4fb  mov     rax, rcx
0x1800aa4fe  cmp     qword ptr [rcx+18h], 0Fh
0x1800aa503  jbe     short loc_1800AA508
0x1800aa505  mov     rax, [rcx]
0x1800aa508  mov     [rax], r12b
0x1800aa50b  mov     [rbp+40h+var_90], r12
0x1800aa50f  lea     rax, [rbp+40h+var_90]
0x1800aa513  mov     [rsp+140h+DomainControllerInfo], rax; int
0x1800aa518  mov     [rsp+140h+Flags], 10h; Flags
0x1800aa520  xor     r9d, r9d; SiteName
0x1800aa523  xor     r8d, r8d; DomainGuid
0x1800aa526  xor     edx, edx; DomainName
0x1800aa528  xor     ecx, ecx; ComputerName
0x1800aa52a  call    cs:__imp_DsGetDcNameW
0x1800aa530  movzx   ebx, ax
0x1800aa533  or      ebx, 80070000h
0x1800aa539  test    eax, eax
0x1800aa53b  cmovle  ebx, eax
0x1800aa53e  test    ebx, ebx
0x1800aa540  js      loc_1800AA96D
0x1800aa546  mov     rcx, [rbp+40h+var_90]
0x1800aa54a  mov     rax, [rcx+48h]
0x1800aa54e  neg     rax
0x1800aa551  sbb     ebx, ebx
0x1800aa553  not     ebx
0x1800aa555  and     ebx, 80004005h
0x1800aa55b  cmp     [rcx+48h], r12
0x1800aa55f  jz      loc_1800AA943
0x1800aa565  mov     rdi, r12
0x1800aa568  mov     rdx, [rcx+30h]
0x1800aa56c  xorps   xmm0, xmm0
0x1800aa56f  movups  [rbp+40h+Src], xmm0
0x1800aa573  mov     [rbp+40h+var_78], r12
0x1800aa577  mov     [rbp+40h+var_70], r12
0x1800aa57b  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800aa57f  mov     r8, r15
0x1800aa582  inc     r8
0x1800aa585  cmp     [rdx+r8*2], r12w
0x1800aa58a  jnz     short loc_1800AA582
0x1800aa58c  lea     rcx, [rbp+40h+Src]
0x1800aa590  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800aa595  nop
0x1800aa596  mov     r13d, 1
0x1800aa59c  mov     r12, 3D00630064002Ch
0x1800aa5a6  lea     r14, [rbp+40h+Src]
0x1800aa5aa  cmp     [rbp+40h+var_70], 7
0x1800aa5af  cmova   r14, qword ptr [rbp+40h+Src]
0x1800aa5b4  mov     rcx, [rbp+40h+var_78]
0x1800aa5b8  cmp     rcx, r13
0x1800aa5bb  jb      loc_1800AA760
0x1800aa5c1  lea     rax, [rcx-1]
0x1800aa5c5  cmp     rdi, rax
0x1800aa5c8  ja      loc_1800AA760
0x1800aa5ce  lea     rbx, [r14+rcx*2]
0x1800aa5d2  lea     rcx, [r14+rdi*2]
0x1800aa5d6  mov     r9, r13
0x1800aa5d9  mov     rdx, rbx
0x1800aa5dc  call    _anonymous_namespace_____std_search_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800aa5e1  mov     rdi, rax
0x1800aa5e4  cmp     rax, rbx
0x1800aa5e7  jz      loc_1800AA760
0x1800aa5ed  sub     rdi, r14
0x1800aa5f0  sar     rdi, 1
0x1800aa5f3  cmp     rdi, r15
0x1800aa5f6  jz      loc_1800AA760
0x1800aa5fc  mov     rcx, [rbp+40h+var_78]
0x1800aa600  cmp     rcx, rdi
0x1800aa603  jb      loc_1800AA9F3
0x1800aa609  mov     rax, rcx
0x1800aa60c  sub     rax, rdi
0x1800aa60f  mov     rdx, r13
0x1800aa612  cmp     rax, r13
0x1800aa615  cmovb   rdx, rax
0x1800aa619  mov     r10d, 4
0x1800aa61f  cmp     rdx, r10
0x1800aa622  jnz     short loc_1800AA63B
0x1800aa624  lea     rax, [rbp+40h+Src]
0x1800aa628  cmp     [rbp+40h+var_70], 7
0x1800aa62d  cmova   rax, qword ptr [rbp+40h+Src]
0x1800aa632  mov     [rax+rdi*2], r12
0x1800aa636  jmp     loc_1800AA5A6
0x1800aa63b  mov     rbx, rcx
0x1800aa63e  sub     rbx, rdx
0x1800aa641  mov     r8, rbx
0x1800aa644  sub     r8, rdi
0x1800aa647  cmp     rdx, r10
0x1800aa64a  jbe     short loc_1800AA683
0x1800aa64c  lea     rax, [rbp+40h+Src]
0x1800aa650  cmp     [rbp+40h+var_70], 7
0x1800aa655  cmova   rax, qword ptr [rbp+40h+Src]
0x1800aa65a  lea     rcx, [rax+rdi*2]
0x1800aa65e  mov     [rcx], r12
0x1800aa661  lea     r8, ds:2[r8*2]; Size
0x1800aa669  lea     rdx, [rcx+rdx*2]; Src
0x1800aa66d  add     rcx, 8; void *
0x1800aa671  call    memmove
0x1800aa676  lea     rax, [rbx+4]
0x1800aa67a  mov     [rbp+40h+var_78], rax
0x1800aa67e  jmp     loc_1800AA5A6
0x1800aa683  mov     r12, r10
0x1800aa686  sub     r12, rdx
0x1800aa689  mov     rax, [rbp+40h+var_70]
0x1800aa68d  sub     rax, rcx
0x1800aa690  cmp     r12, rax
0x1800aa693  ja      loc_1800AA742
0x1800aa699  lea     rax, [rcx+r12]
0x1800aa69d  mov     [rbp+40h+var_78], rax
0x1800aa6a1  lea     rax, [rbp+40h+Src]
0x1800aa6a5  cmp     [rbp+40h+var_70], 7
0x1800aa6aa  cmova   rax, qword ptr [rbp+40h+Src]
0x1800aa6af  lea     r13, [rax+rdi*2]
0x1800aa6b3  lea     rdx, ds:0[rdx*2]
0x1800aa6bb  add     rdx, r13; Src
0x1800aa6be  lea     r9, aDc+8; ""
0x1800aa6c5  cmp     r9, r13
0x1800aa6c8  jbe     short loc_1800AA6EF
0x1800aa6ca  lea     rax, [rax+rcx*2]
0x1800aa6ce  lea     rcx, aDc; ",dc="
0x1800aa6d5  cmp     rcx, rax
0x1800aa6d8  ja      short loc_1800AA6EF
0x1800aa6da  cmp     rdx, rcx
0x1800aa6dd  ja      short loc_1800AA6E4
0x1800aa6df  xor     r14d, r14d
0x1800aa6e2  jmp     short loc_1800AA6F2
0x1800aa6e4  mov     r14, rdx
0x1800aa6e7  sub     r14, rcx
0x1800aa6ea  sar     r14, 1
0x1800aa6ed  jmp     short loc_1800AA6F2
0x1800aa6ef  mov     r14, r10
0x1800aa6f2  lea     r8, ds:2[r8*2]; Size
0x1800aa6fa  lea     rcx, [rdx+r12*2]; void *
0x1800aa6fe  call    memmove
0x1800aa703  lea     rbx, [r14+r14]
0x1800aa707  mov     r8, rbx; Size
0x1800aa70a  lea     rdx, aDc; ",dc="
0x1800aa711  mov     rcx, r13; void *
0x1800aa714  call    memmove
0x1800aa719  mov     r8d, 4
0x1800aa71f  sub     r8, r14
0x1800aa722  add     r8, r8; Size
0x1800aa725  lea     rax, [r14+r12]
0x1800aa729  lea     rcx, aDc; ",dc="
0x1800aa730  lea     rdx, [rcx+rax*2]; Src
0x1800aa734  lea     rcx, [rbx+r13]; void *
0x1800aa738  call    memmove
0x1800aa73d  jmp     loc_1800AA596
0x1800aa742  mov     [rsp+140h+var_110], r10; __int64
0x1800aa747  mov     qword ptr [rsp+140h+Flags], rdx; __int64
0x1800aa74c  mov     r9, rdi
0x1800aa74f  mov     rdx, r12
0x1800aa752  lea     rcx, [rbp+40h+Src]; Src
0x1800aa756  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_KQEB_W0@Z@_K_KPEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??replace@01@QEAAAEAV01@0_KQEB_W0@Z@11PEB_W1@Z; std::wstring::_Reallocate_grow_by<`std::wstring::replace(unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::replace(unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x1800aa75b  jmp     loc_1800AA59C
0x1800aa760  xorps   xmm0, xmm0
0x1800aa763  movups  [rbp+40h+var_50], xmm0
0x1800aa767  xorps   xmm1, xmm1
0x1800aa76a  movdqu  [rbp+40h+var_40], xmm1
0x1800aa76f  mov     r8d, 0Ah
0x1800aa775  lea     rdx, aLdapCn; "LDAP://cn="
0x1800aa77c  lea     rcx, [rbp+40h+var_50]
0x1800aa780  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800aa785  nop
0x1800aa786  mov     rdx, [rbp+40h+var_90]
0x1800aa78a  mov     rdx, [rdx+48h]; void *
0x1800aa78e  lea     rcx, [rbp+40h+var_50]; Src
0x1800aa792  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800aa797  lea     rdx, aCnSitesCnConfi; ",cn=sites,cn=configuration,dc="
0x1800aa79e  lea     rcx, [rbp+40h+var_50]; Src
0x1800aa7a2  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800aa7a7  lea     rdx, [rbp+40h+Src]
0x1800aa7ab  lea     rcx, [rbp+40h+var_50]; Src
0x1800aa7af  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x1800aa7b4  xor     r12d, r12d
0x1800aa7b7  mov     [rbp+40h+var_60], r12
0x1800aa7bb  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?7??GetActiveDirectorySiteId@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z@J$$V@std@@6B@; const std::_Func_impl_no_alloc<`GetActiveDirectorySiteId(std::string &)'::`8'::_lambda_1_,long,>::`vftable'
0x1800aa7c2  mov     [rsp+140h+var_D0], rax
0x1800aa7c7  lea     rax, [rbp+40h+var_50]
0x1800aa7cb  mov     [rsp+140h+var_C8], rax
0x1800aa7d0  lea     rax, [rbp+40h+var_60]
0x1800aa7d4  mov     [rbp+40h+var_C0], rax
0x1800aa7d8  lea     rax, [rsp+140h+var_D0]
0x1800aa7dd  mov     [rbp+40h+var_98], rax
0x1800aa7e1  lea     r9d, [r12+77h]
0x1800aa7e6  lea     r8, aGetactivedirec; "GetActiveDirectorySiteId"
0x1800aa7ed  lea     rdx, aCogetobjectCli; "CoGetObject(clientSiteDN.data(), nullpt"...
0x1800aa7f4  lea     rcx, [rsp+140h+var_D0]
0x1800aa7f9  call    ?MakeComCall@CComTimeout@docli@@SAJAEBV?$function@$$A6AJXZ@std@@PEBD1II@Z; docli::CComTimeout::MakeComCall(std::function<long (void)> const &,char const *,char const *,uint,uint)
0x1800aa7fe  mov     ebx, eax
0x1800aa800  mov     rcx, [rbp+40h+var_98]
0x1800aa804  test    rcx, rcx
0x1800aa807  jz      short loc_1800AA820
0x1800aa809  lea     rax, [rsp+140h+var_D0]
0x1800aa80e  cmp     rcx, rax
0x1800aa811  setnz   dl
0x1800aa814  mov     r8, [rcx]
0x1800aa817  mov     rax, [r8+20h]
0x1800aa81b  call    _guard_dispatch_icall
0x1800aa820  test    ebx, ebx
0x1800aa822  js      loc_1800AA914
0x1800aa828  lea     rax, aObjectguid; "objectGUID"
0x1800aa82f  mov     [rbp+40h+var_30], rax
0x1800aa833  mov     [rbp+40h+var_58], r13d
0x1800aa837  mov     [rbp+40h+hMem], r12
0x1800aa83b  mov     rcx, [rbp+40h+var_60]
0x1800aa83f  mov     rax, [rcx]
0x1800aa842  lea     rdx, [rbp+40h+hMem]
0x1800aa846  mov     [rsp+140h+var_100], rdx
0x1800aa84b  mov     [rsp+140h+var_F8], r12
0x1800aa850  mov     [rsp+140h+var_F0], r13b
0x1800aa855  lea     rdx, [rbp+40h+var_58]
0x1800aa859  mov     qword ptr [rsp+140h+Flags], rdx
0x1800aa85e  lea     r9, [rsp+140h+var_F8]
0x1800aa863  mov     r8d, r13d
0x1800aa866  lea     rdx, [rbp+40h+var_30]
0x1800aa86a  mov     rax, [rax+20h]
0x1800aa86e  call    _guard_dispatch_icall
0x1800aa873  mov     ebx, eax
0x1800aa875  cmp     [rsp+140h+var_F0], r12b
0x1800aa87a  jz      short loc_1800AA897
0x1800aa87c  mov     rdx, [rsp+140h+var_100]
0x1800aa881  mov     rcx, [rdx]; hMem
0x1800aa884  mov     rax, [rsp+140h+var_F8]
0x1800aa889  mov     [rdx], rax
0x1800aa88c  test    rcx, rcx
0x1800aa88f  jz      short loc_1800AA897
0x1800aa891  call    cs:__imp_LocalFree
0x1800aa897  test    ebx, ebx
0x1800aa899  js      short loc_1800AA8DD
0x1800aa89b  mov     rax, [rbp+40h+hMem]
0x1800aa89f  test    rax, rax
0x1800aa8a2  jz      short loc_1800AA8D8
0x1800aa8a4  cmp     dword ptr [rax+0Ch], 8
0x1800aa8a8  jnz     short loc_1800AA8D8
0x1800aa8aa  mov     ebx, r12d
0x1800aa8ad  mov     rdx, [rax+10h]
0x1800aa8b1  mov     rdx, [rdx+10h]; struct _GUID *
0x1800aa8b5  lea     rcx, [rsp+140h+var_100]; this
0x1800aa8ba  call    ??0CGuidToString@@QEAA@AEBU_GUID@@@Z; CGuidToString::CGuidToString(_GUID const &)
0x1800aa8bf  inc     r15
0x1800aa8c2  cmp     [rax+r15], r12b
0x1800aa8c6  jnz     short loc_1800AA8BF
0x1800aa8c8  mov     r8, r15; Size
0x1800aa8cb  mov     rdx, rax; Src
0x1800aa8ce  mov     rcx, rsi; void *
0x1800aa8d1  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800aa8d6  jmp     short loc_1800AA900
0x1800aa8d8  mov     ebx, 80070490h
0x1800aa8dd  mov     [rsp+140h+Flags], ebx
0x1800aa8e1  lea     r9, aIdirectoryobje; "IDirectoryObject::GetObjectAttributes f"...
0x1800aa8e8  mov     r8d, 8Eh; unsigned int
0x1800aa8ee  lea     rdx, aGetactivedirec; "GetActiveDirectorySiteId"
0x1800aa8f5  mov     ecx, 3; unsigned __int8
0x1800aa8fa  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800aa8ff  nop
0x1800aa900  mov     rcx, [rbp+40h+hMem]; hMem
0x1800aa904  mov     [rbp+40h+hMem], r12
0x1800aa908  test    rcx, rcx
0x1800aa90b  jz      short loc_1800AA914
0x1800aa90d  call    cs:__imp_LocalFree
0x1800aa913  nop
0x1800aa914  mov     rcx, [rbp+40h+var_60]
0x1800aa918  test    rcx, rcx
0x1800aa91b  jz      short loc_1800AA92E
0x1800aa91d  mov     [rbp+40h+var_60], r12
0x1800aa921  mov     rax, [rcx]
0x1800aa924  mov     rax, [rax+10h]
0x1800aa928  call    _guard_dispatch_icall
0x1800aa92d  nop
0x1800aa92e  lea     rcx, [rbp+40h+var_50]
0x1800aa932  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800aa937  nop
0x1800aa938  lea     rcx, [rbp+40h+Src]
0x1800aa93c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800aa941  jmp     short loc_1800AA961
0x1800aa943  lea     r9, aDsgetdcnameSuc; "DsGetDcName succeeded but no site is as"...
0x1800aa94a  mov     r8d, 94h; unsigned int
0x1800aa950  lea     rdx, aGetactivedirec; "GetActiveDirectorySiteId"
0x1800aa957  mov     ecx, 3; unsigned __int8
0x1800aa95c  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800aa961  mov     rcx, [rbp+40h+var_90]; Buffer
0x1800aa965  call    cs:__imp_NetApiBufferFree
0x1800aa96b  jmp     short loc_1800AA98F
0x1800aa96d  mov     [rsp+140h+Flags], ebx
  ... truncated ...
```

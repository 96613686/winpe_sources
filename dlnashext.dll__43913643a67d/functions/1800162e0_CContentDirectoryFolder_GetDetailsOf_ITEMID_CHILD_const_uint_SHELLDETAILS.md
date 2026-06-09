# CContentDirectoryFolder::GetDetailsOf(_ITEMID_CHILD const *,uint,_SHELLDETAILS *)

- ea: `0x1800162e0`
- end: `0x1800164c2`
- name: `?GetDetailsOf@CContentDirectoryFolder@@UEAAJPEFBU_ITEMID_CHILD@@IPEAU_SHELLDETAILS@@@Z`
- size: `482`
- prototype: `int(CContentDirectoryFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned int, struct _SHELLDETAILS *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180001710`
- `0x18000bc18`
- `0x18000da80`
- `0x180011930`
- `0x1800125c4`
- `0x180014a00`
- `0x1800158d4`
- `0x1800162e0`
- `0x180018018`
- `0x180019b84`
- `0x180025c58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800163be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800163be`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180016442`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180016442`
- `PROPSYS!PSGetPropertyDescription` at `0x1800163f3`
- `PROPSYS!PSGetPropertyDescription` at `0x1800163f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentDirectoryFolder::GetDetailsOf(
        CContentDirectoryFolder *this,
        const struct _ITEMID_CHILD *a2,
        unsigned int a3,
        struct _SHELLDETAILS *a4)
{
  __int64 v5; // r14
  HRESULT PropertyWithFallback; // ebx
  unsigned __int16 v9; // dx
  const struct tagPROPVARIANT *v10; // r8
  void *ppv; // [rsp+20h] [rbp-E0h] BYREF
  PROPVARIANT pvar; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR psz[128]; // [rsp+40h] [rbp-C0h] BYREF

  v5 = a3;
  PropertyWithFallback = -2147024809;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids);
  CContentDirectoryFolder::_EnsureColumnInfo((CContentDirectoryFolder *)((char *)this - 16));
  if ( (unsigned int)v5 < *((_DWORD *)this + 31) )
  {
    if ( a2 )
    {
      pvar.vt = 0;
      PropertyWithFallback = CContentDirectoryFolder::GetPropertyWithFallback(
                               (CContentDirectoryFolder *)((char *)this - 16),
                               a2,
                               *(const struct _tagpropertykey **)(*((_QWORD *)this + 16) + 24 * v5),
                               &pvar);
      if ( PropertyWithFallback >= 0 )
      {
        PropertyWithFallback = CPropVariant::ChangeType(&pvar, v9, v10);
        if ( PropertyWithFallback >= 0 )
        {
          a4->str.uType = 0;
          a4->str.pOleStr = pvar.bstrVal;
          pvar.hVal.QuadPart = 0;
          pvar.vt = 0;
        }
      }
      PropVariantClear(&pvar);
    }
    else
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&ppv);
      if ( PSGetPropertyDescription(
             *(const PROPERTYKEY *const *)(*((_QWORD *)this + 16) + 24 * v5),
             &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
             &ppv) < 0 )
      {
        memset_0(psz, 0, sizeof(psz));
        StringCchPrintfW(psz, 0x80u, L"Col %d", (unsigned int)v5);
        PropertyWithFallback = SHStrDupW(psz, &a4->str.pOleStr);
        if ( PropertyWithFallback >= 0 )
        {
          a4->fmt = 0;
          a4->str.uType = 0;
        }
      }
      else
      {
        PropertyWithFallback = ShellDetailsFromPropDesc((struct IPropertyDescription *)ppv, a4);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&ppv);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((PropertyWithFallback >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids,
      (unsigned int)PropertyWithFallback);
  }
  return (unsigned int)PropertyWithFallback;
}

```

## disassembly

```asm
0x1800162e0  push    rbp
0x1800162e2  push    rbx
0x1800162e3  push    rsi
0x1800162e4  push    rdi
0x1800162e5  push    r13
0x1800162e7  push    r14
0x1800162e9  push    r15
0x1800162eb  lea     rbp, [rsp-50h]
0x1800162f0  sub     rsp, 150h
0x1800162f7  mov     rax, cs:__security_cookie
0x1800162fe  xor     rax, rsp
0x180016301  mov     [rbp+80h+var_40], rax
0x180016305  mov     rdi, r9
0x180016308  mov     r14d, r8d
0x18001630b  mov     r15, rdx
0x18001630e  mov     rsi, rcx
0x180016311  mov     ebx, 80070057h
0x180016316  lea     r13, WPP_GLOBAL_Control
0x18001631d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016324  cmp     rcx, r13
0x180016327  jz      short loc_180016344
0x180016329  test    byte ptr [rcx+1Ch], 2
0x18001632d  jz      short loc_180016344
0x18001632f  mov     edx, 21h ; '!'
0x180016334  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x18001633b  mov     rcx, [rcx+10h]
0x18001633f  call    WPP_SF_
0x180016344  lea     rcx, [rsi-10h]; this
0x180016348  call    ?_EnsureColumnInfo@CContentDirectoryFolder@@AEAAJXZ; CContentDirectoryFolder::_EnsureColumnInfo(void)
0x18001634d  cmp     r14d, [rsi+7Ch]
0x180016351  jnb     loc_180016465
0x180016357  lea     rbx, [r14+r14*2]
0x18001635b  test    r15, r15
0x18001635e  jz      short loc_1800163C9
0x180016360  xor     eax, eax
0x180016362  mov     word ptr [rsp+180h+pvar], ax
0x180016367  mov     r8, [rsi+80h]
0x18001636e  lea     r9, [rsp+180h+pvar]; struct tagPROPVARIANT *
0x180016373  mov     r8, [r8+rbx*8]; struct _tagpropertykey *
0x180016377  mov     rdx, r15; struct _ITEMID_CHILD *
0x18001637a  lea     rcx, [rsi-10h]; this
0x18001637e  call    ?GetPropertyWithFallback@CContentDirectoryFolder@@QEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CContentDirectoryFolder::GetPropertyWithFallback(_ITEMID_CHILD const *,_tagpropertykey const &,tagPROPVARIANT *)
0x180016383  mov     ebx, eax
0x180016385  test    eax, eax
0x180016387  js      short loc_1800163B9
0x180016389  lea     rcx, [rsp+180h+pvar]; ppropvarDest
0x18001638e  call    ?ChangeType@CPropVariant@@QEAAJGPEBUtagPROPVARIANT@@@Z; CPropVariant::ChangeType(ushort,tagPROPVARIANT const *)
0x180016393  mov     ebx, eax
0x180016395  test    eax, eax
0x180016397  js      short loc_1800163B9
0x180016399  mov     dword ptr [rdi+8], 0
0x1800163a0  mov     rax, qword ptr [rsp+180h+pvar+8]
0x1800163a5  mov     [rdi+10h], rax
0x1800163a9  mov     qword ptr [rsp+180h+pvar+8], 0
0x1800163b2  xor     eax, eax
0x1800163b4  mov     word ptr [rsp+180h+pvar], ax
0x1800163b9  lea     rcx, [rsp+180h+pvar]; pvar
0x1800163be  call    cs:__imp_PropVariantClear
0x1800163c4  jmp     loc_180016465
0x1800163c9  mov     [rsp+180h+ppv], 0
0x1800163d2  lea     rcx, [rsp+180h+ppv]
0x1800163d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800163dc  mov     rcx, [rsi+80h]
0x1800163e3  lea     r8, [rsp+180h+ppv]; ppv
0x1800163e8  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x1800163ef  mov     rcx, [rcx+rbx*8]; propkey
0x1800163f3  call    cs:__imp_PSGetPropertyDescription
0x1800163f9  test    eax, eax
0x1800163fb  js      short loc_18001640E
0x1800163fd  mov     rdx, rdi; struct _SHELLDETAILS *
0x180016400  mov     rcx, [rsp+180h+ppv]; struct IPropertyDescription *
0x180016405  call    ?ShellDetailsFromPropDesc@@YAJPEAUIPropertyDescription@@PEAU_SHELLDETAILS@@@Z; ShellDetailsFromPropDesc(IPropertyDescription *,_SHELLDETAILS *)
0x18001640a  mov     ebx, eax
0x18001640c  jmp     short loc_18001645B
0x18001640e  xor     edx, edx; Val
0x180016410  mov     r8d, 100h; Size
0x180016416  lea     rcx, [rsp+180h+psz]; void *
0x18001641b  call    memset_0
0x180016420  mov     r9d, r14d
0x180016423  lea     r8, aColD; "Col %d"
0x18001642a  mov     edx, 80h; unsigned __int64
0x18001642f  lea     rcx, [rsp+180h+psz]; unsigned __int16 *
0x180016434  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016439  lea     rdx, [rdi+10h]; ppwsz
0x18001643d  lea     rcx, [rsp+180h+psz]; psz
0x180016442  call    cs:__imp_SHStrDupW
0x180016448  mov     ebx, eax
0x18001644a  test    eax, eax
0x18001644c  js      short loc_18001645B
0x18001644e  mov     dword ptr [rdi], 0
0x180016454  mov     dword ptr [rdi+8], 0
0x18001645b  lea     rcx, [rsp+180h+ppv]
0x180016460  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180016465  mov     rcx, cs:WPP_GLOBAL_Control
0x18001646c  cmp     rcx, r13
0x18001646f  jz      short loc_1800164A2
0x180016471  test    byte ptr [rcx+1Ch], 2
0x180016475  jz      short loc_1800164A2
0x180016477  mov     edx, ebx
0x180016479  sar     edx, 1Fh
0x18001647c  and     edx, 0FFFFFFFDh
0x18001647f  add     edx, 5
0x180016482  movzx   eax, byte ptr [rcx+19h]
0x180016486  cmp     eax, edx
0x180016488  jb      short loc_1800164A2
0x18001648a  mov     edx, 22h ; '"'
0x18001648f  mov     r9d, ebx
0x180016492  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x180016499  mov     rcx, [rcx+10h]
0x18001649d  call    WPP_SF_d
0x1800164a2  mov     eax, ebx
0x1800164a4  mov     rcx, [rbp+80h+var_40]
0x1800164a8  xor     rcx, rsp; StackCookie
0x1800164ab  call    __security_check_cookie
0x1800164b0  add     rsp, 150h
0x1800164b7  pop     r15
0x1800164b9  pop     r14
0x1800164bb  pop     r13
0x1800164bd  pop     rdi
0x1800164be  pop     rsi
0x1800164bf  pop     rbx
0x1800164c0  pop     rbp
0x1800164c1  retn
```

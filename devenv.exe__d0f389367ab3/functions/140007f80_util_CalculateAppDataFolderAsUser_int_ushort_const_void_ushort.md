# util_CalculateAppDataFolderAsUser(int,ushort const *,void *,ushort * *)

- ea: `0x140007f80`
- end: `0x140008119`
- name: `?util_CalculateAppDataFolderAsUser@@YAJHPEBGPEAXPEAPEAG@Z`
- size: `409`
- prototype: `int(int, const unsigned __int16 *, void *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000823c`
- `0x140009d80`
- `0x140013ba4`
- `0x14001a938`
- `0x140048600`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140007f70`
- `0x140007f80`
- `0x140008120`
- `0x140033ab0`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140007ff6`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140007ff6`
- `ADVAPI32!RevertToSelf` at `0x14000801e`
- `ADVAPI32!RevertToSelf` at `0x14000801e`
- `OLEAUT32!__imp_SysAllocString` at `0x1400080d0`
- `OLEAUT32!__imp_SysAllocString` at `0x1400080d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1400080a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1400080a6`
- `SHELL32!SHGetFolderPathW` at `0x140008012`
- `SHELL32!SHGetFolderPathW` at `0x140008012`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall util_CalculateAppDataFolderAsUser(
        unsigned int a1,
        const unsigned __int16 *a2,
        void *a3,
        unsigned __int16 **a4)
{
  unsigned __int64 v6; // rbx
  __int64 v8; // rcx
  BOOL v9; // esi
  HRESULT v10; // ebx
  struct ATL::IAtlStringMgr *Instance; // rax
  int v12; // eax
  const unsigned __int16 *v13; // r8
  OLECHAR *v14; // rbx
  unsigned __int16 *v15; // rax
  OLECHAR *psz; // [rsp+30h] [rbp-268h] BYREF
  wchar_t String2[12]; // [rsp+38h] [rbp-260h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-248h] BYREF

  v6 = (int)a1;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( a1 > 0x23 )
    return 2147942487LL;
  v8 = 0x814000000LL;
  if ( !_bittest64(&v8, v6) )
    return 2147942487LL;
  pszPath[0] = 0;
  v9 = 0;
  if ( a3 != (void *)-1LL )
    v9 = ImpersonateLoggedOnUser(a3);
  v10 = SHGetFolderPathW(0, v6, 0, 0, pszPath);
  if ( v9 )
    RevertToSelf();
  if ( v10 >= 0 )
  {
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    psz = (OLECHAR *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                    + 24);
    wcscpy(String2, L"Software\\");
    v12 = wcsnicmp_0(a2, String2, 9u);
    v13 = a2 + 9;
    if ( v12 )
      v13 = a2;
    ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Combine(
      &psz,
      pszPath,
      v13);
    v14 = psz;
    if ( psz )
    {
      v15 = SysAllocString(psz);
      if ( !v15 )
        ATL::AtlThrowImpl(-2147024882);
    }
    else
    {
      v15 = 0;
    }
    *a4 = v15;
    SysFreeString(0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
    }
    return 0;
  }
  else
  {
    _mm_lfence();
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x140007f80  push    rbx
0x140007f82  push    rbp
0x140007f83  push    rsi
0x140007f84  push    rdi
0x140007f85  push    r14
0x140007f87  sub     rsp, 270h
0x140007f8e  mov     rax, cs:__security_cookie
0x140007f95  xor     rax, rsp
0x140007f98  mov     [rsp+298h+var_38], rax
0x140007fa0  mov     rdi, r9
0x140007fa3  mov     rbp, rdx
0x140007fa6  movsxd  rbx, ecx
0x140007fa9  xor     r14d, r14d
0x140007fac  test    r9, r9
0x140007faf  jnz     short loc_140007FBB
0x140007fb1  mov     eax, 80004003h
0x140007fb6  jmp     loc_1400080E2
0x140007fbb  mov     [r9], r14
0x140007fbe  test    rbp, rbp
0x140007fc1  jz      loc_1400080DD
0x140007fc7  cmp     ebx, 23h ; '#'
0x140007fca  ja      loc_1400080DD
0x140007fd0  mov     rcx, 814000000h
0x140007fda  bt      rcx, rbx
0x140007fde  jnb     loc_1400080DD
0x140007fe4  mov     [rsp+298h+var_248], r14w
0x140007fea  mov     esi, r14d
0x140007fed  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140007ff1  jz      short loc_140007FFE
0x140007ff3  mov     rcx, r8; hToken
0x140007ff6  call    cs:__imp_ImpersonateLoggedOnUser
0x140007ffc  mov     esi, eax
0x140007ffe  lea     rax, [rsp+298h+var_248]
0x140008003  mov     [rsp+298h+pszPath], rax; pszPath
0x140008008  xor     r9d, r9d; dwFlags
0x14000800b  xor     r8d, r8d; hToken
0x14000800e  mov     edx, ebx; csidl
0x140008010  xor     ecx, ecx; hwnd
0x140008012  call    cs:__imp_SHGetFolderPathW
0x140008018  mov     ebx, eax
0x14000801a  test    esi, esi
0x14000801c  jz      short loc_140008024
0x14000801e  call    cs:__imp_RevertToSelf
0x140008024  test    ebx, ebx
0x140008026  jns     short loc_140008032
0x140008028  lfence
0x14000802b  mov     eax, ebx
0x14000802d  jmp     loc_1400080E2
0x140008032  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140008037  mov     rcx, rax
0x14000803a  test    rax, rax
0x14000803d  jz      loc_140008100
0x140008043  mov     rax, [rax]
0x140008046  call    qword ptr [rax+18h]
0x140008049  add     rax, 18h
0x14000804d  mov     [rsp+298h+psz], rax
0x140008052  movups  xmm0, xmmword ptr cs:aSoftware; "Software\\"
0x140008059  movups  xmmword ptr [rsp+298h+String2], xmm0
0x14000805e  mov     eax, dword ptr cs:aSoftware+10h; "\\"
0x140008064  mov     [rsp+298h+var_250], eax
0x140008068  mov     r8d, 9; MaxCount
0x14000806e  lea     rdx, [rsp+298h+String2]; String2
0x140008073  mov     rcx, rbp; String1
0x140008076  call    _wcsnicmp_0
0x14000807b  lea     r8, [rbp+12h]
0x14000807f  test    eax, eax
0x140008081  cmovnz  r8, rbp
0x140008085  lea     rdx, [rsp+298h+var_248]
0x14000808a  lea     rcx, [rsp+298h+psz]
0x14000808f  call    ?Combine@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXPEBG0@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Combine(ushort const *,ushort const *)
0x140008094  mov     rbx, [rsp+298h+psz]
0x140008099  test    rbx, rbx
0x14000809c  jnz     short loc_1400080CD
0x14000809e  mov     rax, r14
0x1400080a1  mov     [rdi], rax
0x1400080a4  xor     ecx, ecx; bstrString
0x1400080a6  call    cs:__imp_SysFreeString
0x1400080ac  lea     rdx, [rbx-18h]
0x1400080b0  or      eax, 0FFFFFFFFh
0x1400080b3  lock xadd [rdx+10h], eax
0x1400080b8  sub     eax, 1
0x1400080bb  jg      short loc_1400080C9
0x1400080bd  lfence
0x1400080c0  mov     rcx, [rdx]
0x1400080c3  mov     rax, [rcx]
0x1400080c6  call    qword ptr [rax+8]
0x1400080c9  xor     eax, eax
0x1400080cb  jmp     short loc_1400080E2
0x1400080cd  mov     rcx, rbx; psz
0x1400080d0  call    cs:__imp_SysAllocString
0x1400080d6  test    rax, rax
0x1400080d9  jz      short loc_14000810E
0x1400080db  jmp     short loc_1400080A1
0x1400080dd  mov     eax, 80070057h
0x1400080e2  mov     rcx, [rsp+298h+var_38]
0x1400080ea  xor     rcx, rsp; StackCookie
0x1400080ed  call    __security_check_cookie
0x1400080f2  add     rsp, 270h
0x1400080f9  pop     r14
0x1400080fb  pop     rdi
0x1400080fc  pop     rsi
0x1400080fd  pop     rbp
0x1400080fe  pop     rbx
0x1400080ff  retn
0x140008100  mov     ecx, 80004005h; int
0x140008105  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000810b  jmp     short $+2
0x14000810d  nop
0x14000810e  mov     ecx, 8007000Eh; int
0x140008113  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

# CAppIdExtImpl::SetProperty(long,tagVARIANT)

- ea: `0x14000905c`
- end: `0x14000936c`
- name: `?SetProperty@CAppIdExtImpl@@UEAAJJUtagVARIANT@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(CAppIdExtImpl *__hidden this, int, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007e20`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140004a0c`
- `0x14000905c`
- `0x1400287d4`
- `0x140033ab0`
- `0x14003a0c8`
- `0x14003a430`
- `0x140040b0c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400092ef`
- `ADVAPI32!RegCloseKey` at `0x14000932b`
- `ADVAPI32!RegCloseKey` at `0x1400092ef`
- `ADVAPI32!RegCloseKey` at `0x14000932b`
- `ADVAPI32!RegSetValueExW` at `0x1400092c0`
- `ADVAPI32!RegSetValueExW` at `0x1400092c0`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140009207`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140009229`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140009207`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140009229`
- `MSVCP140!_Mtx_lock` at `0x1400091fa`
- `MSVCP140!_Mtx_lock` at `0x1400091fa`
- `MSVCP140!_Mtx_unlock` at `0x140009338`
- `MSVCP140!_Mtx_unlock` at `0x140009338`

## pseudocode

```c
__int64 __fastcall CAppIdExtImpl::SetProperty(CAppIdExtImpl *this, int a2, struct tagVARIANT *a3)
{
  IRecordInfo *pRecInfo; // xmm1_8
  SAFEARRAY *parray; // rdx
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // ebx
  _QWORD *v11; // rdx
  HKEY v12; // rdx
  _QWORD *v13; // rdx
  HKEY v14; // rdx
  SHORT iVal; // r15
  int v16; // r14d
  __int64 v17; // rdx
  HKEY v18; // rbx
  LSTATUS v19; // eax
  unsigned __int16 *v20; // rdx
  struct tagVARIANT v21; // [rsp+30h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v24; // [rsp+60h] [rbp-10h] BYREF

  if ( a2 != -8653 )
  {
    if ( a2 != -8636 )
    {
      pRecInfo = a3->pRecInfo;
      *(_OWORD *)&v21.vt = *(_OWORD *)&a3->vt;
      v21.pRecInfo = pRecInfo;
      return CAppIdImpl::SetProperty(this, a2, &v21);
    }
    if ( !*((_QWORD *)this + 183) )
      return 2147500037LL;
    if ( a3->vt == 8200 )
    {
      parray = a3->parray;
      hKey = 0;
      anonymous_namespace_::ConvertBSTRArrayToSemicolonSeperatedCanonicalizedString(&hKey, parray);
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      v8 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance);
      v9 = *((_QWORD *)this + 183);
      *(_QWORD *)Data = v8 + 24;
      v10 = (*(__int64 (__fastcall **)(__int64, BYTE *, _QWORD))(*(_QWORD *)v9 + 72LL))(v9, Data, 0);
      if ( v10 < 0
        || (v10 = CAppIdExtImpl::SetExcludedDirectoriesList(
                    *(const unsigned __int16 **)Data,
                    (const unsigned __int16 *)hKey),
            v10 < 0) )
      {
        v13 = (_QWORD *)(*(_QWORD *)Data - 24LL);
        if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)Data - 24LL + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
        }
        v14 = hKey - 6;
        if ( _InterlockedDecrement((volatile signed __int32 *)hKey - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
        }
        return (unsigned int)v10;
      }
      else
      {
        v11 = (_QWORD *)(*(_QWORD *)Data - 24LL);
        if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)Data - 24LL + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
        }
        v12 = hKey - 6;
        if ( _InterlockedDecrement((volatile signed __int32 *)hKey - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
        }
        return 0;
      }
    }
    return 2147942487LL;
  }
  if ( a3->vt != 11 )
    return 2147942487LL;
  iVal = a3->iVal;
  if ( _Mtx_lock((_Mtx_t)&CAppIdImpl::s_stateLock) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_14009CFFC == 0x7FFFFFFF )
  {
    dword_14009CFFC = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  if ( (iVal != 0) == CAppIdExtImpl::m_enablePerMonitorAwareness )
  {
    v16 = 0;
  }
  else
  {
    v17 = *((_QWORD *)this + 24);
    hKey = 0;
    v24 = 0;
    CVsRegKeyW::Combine((unsigned int)&v24, v17, (unsigned int)L"General", 0);
    v16 = CVsRegKeyW::Open(&hKey, HKEY_CURRENT_USER, v24, 0x2001Fu);
    if ( v16 < 0 )
    {
      v18 = hKey;
    }
    else
    {
      *(_DWORD *)Data = iVal != 0;
      v18 = hKey;
      if ( hKey )
      {
        v19 = RegSetValueExW(hKey, L"IsPerMonitorAware", 0, 4u, Data, 4u);
        v16 = (unsigned __int16)v19 | 0x80070000;
        if ( v19 <= 0 )
          v16 = v19;
        if ( v16 >= 0 )
          CAppIdExtImpl::m_enablePerMonitorAwareness = iVal != 0;
      }
      else
      {
        v16 = -2147418113;
      }
      if ( v18 )
      {
        RegCloseKey(v18);
        v18 = 0;
      }
    }
    v20 = v24 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v24 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20);
    }
    if ( v18 )
      RegCloseKey(v18);
  }
  _Mtx_unlock((_Mtx_t)&CAppIdImpl::s_stateLock);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14000905c  mov     [rsp-28h+arg_8], rbx
0x140009061  push    rbp
0x140009062  push    rsi
0x140009063  push    rdi
0x140009064  push    r14
0x140009066  push    r15
0x140009068  mov     rbp, rsp
0x14000906b  sub     rsp, 70h
0x14000906f  mov     rax, cs:__security_cookie
0x140009076  xor     rax, rsp
0x140009079  mov     [rbp+var_8], rax
0x14000907d  mov     rsi, rcx
0x140009080  cmp     edx, 0FFFFDE33h
0x140009086  jz      loc_1400091D2
0x14000908c  cmp     edx, 0FFFFDE44h
0x140009092  jz      short loc_1400090B5
0x140009094  movups  xmm0, xmmword ptr [r8]
0x140009098  movsd   xmm1, qword ptr [r8+10h]
0x14000909e  lea     r8, [rbp+var_40]; struct tagVARIANT
0x1400090a2  movaps  xmmword ptr [rbp+var_40], xmm0
0x1400090a6  movsd   qword ptr [rbp+var_40+10h], xmm1
0x1400090ab  call    ?SetProperty@CAppIdImpl@@UEAAJJUtagVARIANT@@@Z; CAppIdImpl::SetProperty(long,tagVARIANT)
0x1400090b0  jmp     loc_140009341
0x1400090b5  xor     edi, edi
0x1400090b7  cmp     [rcx+5B8h], rdi
0x1400090be  jz      loc_1400091C8
0x1400090c4  mov     eax, 2008h
0x1400090c9  cmp     [r8], ax
0x1400090cd  jnz     loc_1400091D9
0x1400090d3  mov     rdx, [r8+8]
0x1400090d7  lea     rcx, [rbp+hKey]
0x1400090db  mov     [rbp+hKey], rdi
0x1400090df  call    _anonymous_namespace___ConvertBSTRArrayToSemicolonSeperatedCanonicalizedString
0x1400090e4  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400090e9  mov     rcx, rax
0x1400090ec  test    rax, rax
0x1400090ef  jz      loc_140009361
0x1400090f5  mov     rax, [rax]
0x1400090f8  call    qword ptr [rax+18h]
0x1400090fb  mov     rcx, [rsi+5B8h]
0x140009102  lea     rdx, [rbp+Data]
0x140009106  add     rax, 18h
0x14000910a  xor     r8d, r8d
0x14000910d  mov     qword ptr [rbp+Data], rax
0x140009111  mov     rax, [rcx]
0x140009114  call    qword ptr [rax+48h]
0x140009117  mov     ebx, eax
0x140009119  test    eax, eax
0x14000911b  js      short loc_14000917C
0x14000911d  mov     rdx, [rbp+hKey]; unsigned __int16 *
0x140009121  mov     rcx, qword ptr [rbp+Data]; unsigned __int16 *
0x140009125  call    ?SetExcludedDirectoriesList@CAppIdExtImpl@@KAJPEBG0@Z; CAppIdExtImpl::SetExcludedDirectoriesList(ushort const *,ushort const *)
0x14000912a  mov     ebx, eax
0x14000912c  test    eax, eax
0x14000912e  js      short loc_14000917C
0x140009130  mov     rdx, qword ptr [rbp+Data]
0x140009134  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009138  or      esi, 0FFFFFFFFh
0x14000913b  mov     eax, esi
0x14000913d  lock xadd [rdx+10h], eax
0x140009142  add     eax, esi
0x140009144  test    eax, eax
0x140009146  jg      short loc_140009154
0x140009148  lfence
0x14000914b  mov     rcx, [rdx]
0x14000914e  mov     rax, [rcx]
0x140009151  call    qword ptr [rax+8]
0x140009154  mov     rdx, [rbp+hKey]
0x140009158  mov     eax, esi
0x14000915a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000915e  lock xadd [rdx+10h], eax
0x140009163  add     eax, esi
0x140009165  test    eax, eax
0x140009167  jg      short loc_140009175
0x140009169  lfence
0x14000916c  mov     rcx, [rdx]
0x14000916f  mov     rax, [rcx]
0x140009172  call    qword ptr [rax+8]
0x140009175  xor     eax, eax
0x140009177  jmp     loc_140009341
0x14000917c  mov     rdx, qword ptr [rbp+Data]
0x140009180  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009184  or      esi, 0FFFFFFFFh
0x140009187  mov     eax, esi
0x140009189  lock xadd [rdx+10h], eax
0x14000918e  add     eax, esi
0x140009190  test    eax, eax
0x140009192  jg      short loc_1400091A0
0x140009194  lfence
0x140009197  mov     rcx, [rdx]
0x14000919a  mov     rax, [rcx]
0x14000919d  call    qword ptr [rax+8]
0x1400091a0  mov     rdx, [rbp+hKey]
0x1400091a4  mov     eax, esi
0x1400091a6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400091aa  lock xadd [rdx+10h], eax
0x1400091af  add     eax, esi
0x1400091b1  test    eax, eax
0x1400091b3  jg      short loc_1400091C1
0x1400091b5  lfence
0x1400091b8  mov     rcx, [rdx]
0x1400091bb  mov     rax, [rcx]
0x1400091be  call    qword ptr [rax+8]
0x1400091c1  mov     eax, ebx
0x1400091c3  jmp     loc_140009341
0x1400091c8  mov     eax, 80004005h
0x1400091cd  jmp     loc_140009341
0x1400091d2  cmp     word ptr [r8], 0Bh
0x1400091d7  jz      short loc_1400091E3
0x1400091d9  mov     eax, 80070057h
0x1400091de  jmp     loc_140009341
0x1400091e3  movzx   r15d, word ptr [r8+8]
0x1400091e8  lea     rcx, ?s_stateLock@CAppIdImpl@@1Vrecursive_mutex@std@@A; _Mtx_t
0x1400091ef  xor     edi, edi
0x1400091f1  test    r15w, r15w
0x1400091f5  mov     ebx, edi
0x1400091f7  setnz   bl
0x1400091fa  call    cs:__imp__Mtx_lock
0x140009200  test    eax, eax
0x140009202  jz      short loc_14000920E
0x140009204  lea     ecx, [rdi+5]
0x140009207  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14000920d  int     3; Trap to Debugger
0x14000920e  cmp     cs:dword_14009CFFC, 7FFFFFFFh
0x140009218  jnz     short loc_140009230
0x14000921a  mov     ecx, 6
0x14000921f  mov     cs:dword_14009CFFC, 7FFFFFFEh
0x140009229  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14000922f  int     3; Trap to Debugger
0x140009230  cmp     cs:?m_enablePerMonitorAwareness@CAppIdExtImpl@@0_NA, dil; bool CAppIdExtImpl::m_enablePerMonitorAwareness
0x140009237  mov     eax, edi
0x140009239  setnz   al
0x14000923c  cmp     ebx, eax
0x14000923e  jnz     short loc_140009248
0x140009240  mov     r14d, edi
0x140009243  jmp     loc_140009331
0x140009248  mov     rdx, [rsi+0C0h]
0x14000924f  lea     r8, aGeneral; "General"
0x140009256  xor     r9d, r9d
0x140009259  mov     [rbp+hKey], rdi
0x14000925d  lea     rcx, [rbp+var_10]
0x140009261  mov     [rbp+var_10], rdi
0x140009265  call    ?Combine@CVsRegKeyW@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG000@Z; CVsRegKeyW::Combine(ushort const *,ushort const *,ushort const *,ushort const *)
0x14000926a  mov     r8, [rbp+var_10]; unsigned __int16 *
0x14000926e  lea     rcx, [rbp+hKey]; this
0x140009272  mov     r9d, 2001Fh; unsigned int
0x140009278  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x14000927f  call    ?Open@CVsRegKeyW@@QEAAJPEAUHKEY__@@PEBGK@Z; CVsRegKeyW::Open(HKEY__ *,ushort const *,ulong)
0x140009284  mov     r14d, eax
0x140009287  test    eax, eax
0x140009289  js      short loc_1400092FA
0x14000928b  mov     dword ptr [rbp+Data], ebx
0x14000928e  mov     rbx, [rbp+hKey]
0x140009292  test    rbx, rbx
0x140009295  jnz     short loc_14000929F
0x140009297  mov     r14d, 8000FFFFh
0x14000929d  jmp     short loc_1400092E7
0x14000929f  mov     r9d, 4; dwType
0x1400092a5  lea     rax, [rbp+Data]
0x1400092a9  mov     [rsp+70h+cbData], r9d; cbData
0x1400092ae  lea     rdx, ValueName; "IsPerMonitorAware"
0x1400092b5  xor     r8d, r8d; Reserved
0x1400092b8  mov     [rsp+70h+lpData], rax; lpData
0x1400092bd  mov     rcx, rbx; hKey
0x1400092c0  call    cs:__imp_RegSetValueExW
0x1400092c6  movzx   r14d, ax
0x1400092ca  or      r14d, 80070000h
0x1400092d1  test    eax, eax
0x1400092d3  cmovle  r14d, eax
0x1400092d7  test    r14d, r14d
0x1400092da  js      short loc_1400092E7
0x1400092dc  test    r15w, r15w
0x1400092e0  setnz   cs:?m_enablePerMonitorAwareness@CAppIdExtImpl@@0_NA; bool CAppIdExtImpl::m_enablePerMonitorAwareness
0x1400092e7  test    rbx, rbx
0x1400092ea  jz      short loc_1400092FE
0x1400092ec  mov     rcx, rbx; hKey
0x1400092ef  call    cs:__imp_RegCloseKey
0x1400092f5  mov     rbx, rdi
0x1400092f8  jmp     short loc_1400092FE
0x1400092fa  mov     rbx, [rbp+hKey]
0x1400092fe  mov     rdx, [rbp+var_10]
0x140009302  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009306  or      esi, 0FFFFFFFFh
0x140009309  mov     eax, esi
0x14000930b  lock xadd [rdx+10h], eax
0x140009310  add     eax, esi
0x140009312  test    eax, eax
0x140009314  jg      short loc_140009323
0x140009316  lfence
0x140009319  mov     rcx, [rdx]
0x14000931c  mov     r8, [rcx]
0x14000931f  call    qword ptr [r8+8]
0x140009323  test    rbx, rbx
0x140009326  jz      short loc_140009331
0x140009328  mov     rcx, rbx; hKey
0x14000932b  call    cs:__imp_RegCloseKey
0x140009331  lea     rcx, ?s_stateLock@CAppIdImpl@@1Vrecursive_mutex@std@@A; _Mtx_t
0x140009338  call    cs:__imp__Mtx_unlock
0x14000933e  mov     eax, r14d
0x140009341  mov     rcx, [rbp+var_8]
0x140009345  xor     rcx, rsp; StackCookie
0x140009348  call    __security_check_cookie
0x14000934d  mov     rbx, [rsp+70h+arg_8]
0x140009355  add     rsp, 70h
0x140009359  pop     r15
0x14000935b  pop     r14
0x14000935d  pop     rdi
0x14000935e  pop     rsi
0x14000935f  pop     rbp
0x140009360  retn
0x140009361  mov     ecx, 80004005h; int
0x140009366  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

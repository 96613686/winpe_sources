# MMC21ADDREMOVEUI::CSnapinManager::ScGetSnapinInfo(ushort const *,MMC21ADDREMOVEUI::CSnapinInfo * *)

- ea: `0x1800ba3bc`
- end: `0x1800ba6b1`
- name: `?ScGetSnapinInfo@CSnapinManager@MMC21ADDREMOVEUI@@AEAA?AVSC@mmcerror@@PEBGPEAPEAVCSnapinInfo@2@@Z`
- size: `757`
- prototype: `struct mmcerror::SC __high(const unsigned __int16 *, struct CSnapinInfo **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800b9b10`

## callees

- `0x180013dac`
- `0x180016ba0`
- `0x18002a710`
- `0x1800304c0`
- `0x18003a698`
- `0x1800743b4`
- `0x18007675c`
- `0x180076d38`
- `0x180077478`
- `0x1800ba3bc`
- `0x180134540`

## import_xrefs

- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1800ba3f5`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1800ba3f5`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x1800ba4b8`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x1800ba4b8`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800ba4ae`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800ba658`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800ba4ae`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800ba658`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800ba47e`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800ba4dc`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800ba5e0`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800ba61b`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800ba664`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800ba47e`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800ba4dc`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800ba5e0`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800ba61b`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800ba664`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800ba42a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800ba565`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800ba42a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800ba565`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800ba407`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800ba407`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800ba43f`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800ba57a`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800ba43f`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800ba57a`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800ba435`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800ba570`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800ba68c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800ba435`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800ba570`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800ba68c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ba5b4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ba5b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
mmcerror::SC *__fastcall MMC21ADDREMOVEUI::CSnapinManager::ScGetSnapinInfo(
        __int64 a1,
        mmcerror::SC *a2,
        const unsigned __int16 *a3,
        _QWORD *a4)
{
  __int64 v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // rax
  const WCHAR *v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rdx
  const struct mmcerror::SC *v16; // rax
  __int64 v17; // rdx
  _QWORD v19[2]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v20[24]; // [rsp+40h] [rbp-69h] BYREF
  __int64 v21; // [rsp+58h] [rbp-51h] BYREF
  _QWORD v22[3]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v23; // [rsp+78h] [rbp-31h] BYREF
  _BYTE v24[24]; // [rsp+88h] [rbp-21h] BYREF
  PCNZWCH lpString1[4]; // [rsp+A0h] [rbp-9h] BYREF

  v21 = (__int64)a2;
  mmcerror::SC::SC((mmcerror::SC *)v20, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v20, L"CSnapinManager::ScFindSnapinAndInitSnapinInfo");
  v8 = ScCheckPointers(v22, a3, a4, 2147942487LL);
  mmcerror::SC::operator=(v20, v8);
  mmcerror::SC::~SC((mmcerror::SC *)v22);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v20) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 38, WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids);
    mmcerror::SC::SC(a2, (const struct mmcerror::SC *)v20);
  }
  else
  {
    v19[0] = &CSnapInReferencePtr::`vftable';
    v19[1] = 0;
    v9 = CSnapInReferencePtr::CreateFromOptionalProgID((CSnapInReferencePtr *)v19, a3);
    mmcerror::SC::operator=(v20, v9);
    if ( mmcerror::SC::IsError((mmcerror::SC *)v20) )
    {
      std::wstring::wstring(lpString1, a3);
      v10 = -(__int64)(*(_DWORD *)(a1 + 268) != 0);
      v21 = v10;
      while ( v10 )
      {
        v22[0] = &CSnapInReferencePtr::`vftable';
        v22[1] = 0;
        v23 = 0;
        CMap<CSnapInReferencePtr,CSnapInReferencePtr const &,MMC21ADDREMOVEUI::CSnapinInfo *,MMC21ADDREMOVEUI::CSnapinInfo *>::GetNextAssoc(
          a1 + 256,
          &v21,
          v22,
          &v23);
        v11 = v23;
        v12 = ScCheckPointers(v24, v23, 2147549183LL);
        mmcerror::SC::operator=(v20, v12);
        mmcerror::SC::~SC((mmcerror::SC *)v24);
        if ( (unsigned __int8)mmcerror::SC::operator bool(v20) )
        {
          mmcerror::SC::SC(a2, (const struct mmcerror::SC *)v20);
          v22[0] = &CSnapInReferencePtr::`vftable';
          CSnapInReferencePtr::Clear((CSnapInReferencePtr *)v22);
          LOBYTE(v15) = 1;
          std::wstring::_Tidy(lpString1, v15, 0);
          v19[0] = &CSnapInReferencePtr::`vftable';
          CSnapInReferencePtr::Clear((CSnapInReferencePtr *)v19);
          goto LABEL_18;
        }
        v13 = (const WCHAR *)lpString1;
        if ( lpString1[3] >= (PCNZWCH)8 )
          v13 = lpString1[0];
        if ( CompareStringW(0x400u, 1u, v13, -1, *(PCNZWCH *)(v11 + 8), -1) == 2 )
        {
          *a4 = v11;
          mmcerror::SC::SC(a2, (const struct mmcerror::SC *)v20);
          v22[0] = &CSnapInReferencePtr::`vftable';
          CSnapInReferencePtr::Clear((CSnapInReferencePtr *)v22);
          LOBYTE(v14) = 1;
          std::wstring::_Tidy(lpString1, v14, 0);
          v19[0] = &CSnapInReferencePtr::`vftable';
          CSnapInReferencePtr::Clear((CSnapInReferencePtr *)v19);
          goto LABEL_18;
        }
        v22[0] = &CSnapInReferencePtr::`vftable';
        CSnapInReferencePtr::Clear((CSnapInReferencePtr *)v22);
        v10 = v21;
      }
      v16 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v20, 14025);
      mmcerror::SC::SC(a2, v16);
      LOBYTE(v17) = 1;
      std::wstring::_Tidy(lpString1, v17, 0);
      v19[0] = &CSnapInReferencePtr::`vftable';
      CSnapInReferencePtr::Clear((CSnapInReferencePtr *)v19);
    }
    else
    {
      *a4 = CSnapinInfoCache::FindEntry((CSnapinInfoCache *)(a1 + 256), (const struct CSnapInReferencePtr *)v19);
      mmcerror::SC::SC(a2, (const struct mmcerror::SC *)v20);
      v19[0] = &CSnapInReferencePtr::`vftable';
      CSnapInReferencePtr::Clear((CSnapInReferencePtr *)v19);
    }
  }
LABEL_18:
  mmcerror::SC::~SC((mmcerror::SC *)v20);
  return a2;
}

```

## disassembly

```asm
0x1800ba3bc  push    rbp
0x1800ba3be  push    rbx
0x1800ba3bf  push    rsi
0x1800ba3c0  push    rdi
0x1800ba3c1  push    r14
0x1800ba3c3  push    r15
0x1800ba3c5  lea     rbp, [rsp-2Fh]
0x1800ba3ca  sub     rsp, 0D8h
0x1800ba3d1  mov     rax, cs:__security_cookie
0x1800ba3d8  xor     rax, rsp
0x1800ba3db  mov     [rbp+57h+var_40], rax
0x1800ba3df  mov     r14, r9
0x1800ba3e2  mov     rsi, r8
0x1800ba3e5  mov     rbx, rdx
0x1800ba3e8  mov     rdi, rcx
0x1800ba3eb  mov     [rbp+57h+var_A8], rdx
0x1800ba3ef  xor     edx, edx
0x1800ba3f1  lea     rcx, [rbp+57h+var_C0]
0x1800ba3f5  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1800ba3fb  nop
0x1800ba3fc  lea     rdx, aCsnapinmanager_8; "CSnapinManager::ScFindSnapinAndInitSnap"...
0x1800ba403  lea     rcx, [rbp+57h+var_C0]
0x1800ba407  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1800ba40d  mov     r9d, 80070057h
0x1800ba413  mov     r8, r14
0x1800ba416  mov     rdx, rsi
0x1800ba419  lea     rcx, [rbp+57h+var_A0]
0x1800ba41d  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBX0J@Z; ScCheckPointers(void const *,void const *,long)
0x1800ba422  nop
0x1800ba423  mov     rdx, rax
0x1800ba426  lea     rcx, [rbp+57h+var_C0]
0x1800ba42a  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1800ba430  nop
0x1800ba431  lea     rcx, [rbp+57h+var_A0]
0x1800ba435  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1800ba43b  lea     rcx, [rbp+57h+var_C0]
0x1800ba43f  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1800ba445  test    al, al
0x1800ba447  jz      short loc_1800BA489
0x1800ba449  lea     rax, WPP_GLOBAL_Control
0x1800ba450  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba457  cmp     rcx, rax
0x1800ba45a  jz      short loc_1800BA477
0x1800ba45c  cmp     byte ptr [rcx+19h], 2
0x1800ba460  jb      short loc_1800BA477
0x1800ba462  mov     edx, 26h ; '&'
0x1800ba467  lea     r8, WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids
0x1800ba46e  mov     rcx, [rcx+10h]
0x1800ba472  call    WPP_SF_
0x1800ba477  lea     rdx, [rbp+57h+var_C0]
0x1800ba47b  mov     rcx, rbx
0x1800ba47e  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1800ba484  jmp     loc_1800BA688
0x1800ba489  lea     r15, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x1800ba490  mov     [rbp+57h+var_D0], r15
0x1800ba494  mov     [rbp+57h+var_C8], 0
0x1800ba49c  mov     rdx, rsi; unsigned __int16 *
0x1800ba49f  lea     rcx, [rbp+57h+var_D0]; this
0x1800ba4a3  call    ?CreateFromOptionalProgID@CSnapInReferencePtr@@QEAAJPEBG@Z; CSnapInReferencePtr::CreateFromOptionalProgID(ushort const *)
0x1800ba4a8  mov     edx, eax
0x1800ba4aa  lea     rcx, [rbp+57h+var_C0]
0x1800ba4ae  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800ba4b4  lea     rcx, [rbp+57h+var_C0]
0x1800ba4b8  call    cs:__imp_?IsError@SC@mmcerror@@QEBA_NXZ; mmcerror::SC::IsError(void)
0x1800ba4be  test    al, al
0x1800ba4c0  jnz     short loc_1800BA4F6
0x1800ba4c2  lea     rdx, [rbp+57h+var_D0]; struct CSnapInReferencePtr *
0x1800ba4c6  lea     rcx, [rdi+100h]; this
0x1800ba4cd  call    ?FindEntry@CSnapinInfoCache@@QEAAPEAVCSnapinInfo@@AEBVCSnapInReferencePtr@@@Z; CSnapinInfoCache::FindEntry(CSnapInReferencePtr const &)
0x1800ba4d2  mov     [r14], rax
0x1800ba4d5  lea     rdx, [rbp+57h+var_C0]
0x1800ba4d9  mov     rcx, rbx
0x1800ba4dc  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1800ba4e2  nop
0x1800ba4e3  mov     [rbp+57h+var_D0], r15
0x1800ba4e7  lea     rcx, [rbp+57h+var_D0]; this
0x1800ba4eb  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x1800ba4f0  nop
0x1800ba4f1  jmp     loc_1800BA688
0x1800ba4f6  mov     rdx, rsi
0x1800ba4f9  lea     rcx, [rbp+57h+lpString1]
0x1800ba4fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800ba502  nop
0x1800ba503  mov     eax, [rdi+10Ch]
0x1800ba509  neg     eax
0x1800ba50b  sbb     rcx, rcx
0x1800ba50e  mov     [rbp+57h+var_A8], rcx
0x1800ba512  test    rcx, rcx
0x1800ba515  jz      loc_1800BA64F
0x1800ba51b  mov     [rbp+57h+var_A0], r15
0x1800ba51f  mov     [rbp+57h+var_98], 0
0x1800ba527  mov     [rbp+57h+var_88], 0
0x1800ba52f  lea     r9, [rbp+57h+var_88]
0x1800ba533  lea     r8, [rbp+57h+var_A0]
0x1800ba537  lea     rdx, [rbp+57h+var_A8]
0x1800ba53b  lea     rcx, [rdi+100h]
0x1800ba542  call    ?GetNextAssoc@?$CMap@VCSnapInReferencePtr@@AEBV1@PEAVCSnapinInfo@MMC21ADDREMOVEUI@@PEAV23@@@QEBAXAEAPEAU__POSITION@@AEAVCSnapInReferencePtr@@AEAPEAVCSnapinInfo@MMC21ADDREMOVEUI@@@Z; CMap<CSnapInReferencePtr,CSnapInReferencePtr const &,MMC21ADDREMOVEUI::CSnapinInfo *,MMC21ADDREMOVEUI::CSnapinInfo *>::GetNextAssoc(__POSITION * &,CSnapInReferencePtr &,MMC21ADDREMOVEUI::CSnapinInfo * &)
0x1800ba547  mov     r8d, 8000FFFFh
0x1800ba54d  mov     rsi, [rbp+57h+var_88]
0x1800ba551  mov     rdx, rsi
0x1800ba554  lea     rcx, [rbp+57h+var_78]
0x1800ba558  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x1800ba55d  nop
0x1800ba55e  mov     rdx, rax
0x1800ba561  lea     rcx, [rbp+57h+var_C0]
0x1800ba565  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1800ba56b  nop
0x1800ba56c  lea     rcx, [rbp+57h+var_78]
0x1800ba570  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1800ba576  lea     rcx, [rbp+57h+var_C0]
0x1800ba57a  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1800ba580  test    al, al
0x1800ba582  jnz     loc_1800BA614
0x1800ba588  mov     rax, [rsi+8]
0x1800ba58c  lea     r8, [rbp+57h+lpString1]
0x1800ba590  cmp     [rbp+57h+var_48], 8
0x1800ba595  cmovnb  r8, [rbp+57h+lpString1]; lpString1
0x1800ba59a  mov     [rsp+100h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800ba5a2  mov     [rsp+100h+lpString2], rax; lpString2
0x1800ba5a7  or      r9d, 0FFFFFFFFh; cchCount1
0x1800ba5ab  lea     edx, [r9+2]; dwCmpFlags
0x1800ba5af  mov     ecx, 400h; Locale
0x1800ba5b4  call    cs:__imp_CompareStringW
0x1800ba5ba  cmp     eax, 2
0x1800ba5bd  jz      short loc_1800BA5D6
0x1800ba5bf  mov     [rbp+57h+var_A0], r15
0x1800ba5c3  lea     rcx, [rbp+57h+var_A0]; this
0x1800ba5c7  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x1800ba5cc  nop
0x1800ba5cd  mov     rcx, [rbp+57h+var_A8]
0x1800ba5d1  jmp     loc_1800BA512
0x1800ba5d6  mov     [r14], rsi
0x1800ba5d9  lea     rdx, [rbp+57h+var_C0]
0x1800ba5dd  mov     rcx, rbx
0x1800ba5e0  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1800ba5e6  nop
0x1800ba5e7  mov     [rbp+57h+var_A0], r15
0x1800ba5eb  lea     rcx, [rbp+57h+var_A0]; this
0x1800ba5ef  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x1800ba5f4  nop
0x1800ba5f5  xor     r8d, r8d
0x1800ba5f8  mov     dl, 1
0x1800ba5fa  lea     rcx, [rbp+57h+lpString1]
0x1800ba5fe  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800ba603  nop
0x1800ba604  mov     [rbp+57h+var_D0], r15
0x1800ba608  lea     rcx, [rbp+57h+var_D0]; this
0x1800ba60c  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x1800ba611  nop
0x1800ba612  jmp     short loc_1800BA688
0x1800ba614  lea     rdx, [rbp+57h+var_C0]
0x1800ba618  mov     rcx, rbx
0x1800ba61b  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1800ba621  nop
0x1800ba622  mov     [rbp+57h+var_A0], r15
0x1800ba626  lea     rcx, [rbp+57h+var_A0]; this
0x1800ba62a  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x1800ba62f  nop
0x1800ba630  xor     r8d, r8d
0x1800ba633  mov     dl, 1
0x1800ba635  lea     rcx, [rbp+57h+lpString1]
0x1800ba639  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800ba63e  nop
0x1800ba63f  mov     [rbp+57h+var_D0], r15
0x1800ba643  lea     rcx, [rbp+57h+var_D0]; this
0x1800ba647  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x1800ba64c  nop
0x1800ba64d  jmp     short loc_1800BA688
0x1800ba64f  mov     edx, 36C9h
0x1800ba654  lea     rcx, [rbp+57h+var_C0]
0x1800ba658  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800ba65e  mov     rdx, rax
0x1800ba661  mov     rcx, rbx
0x1800ba664  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1800ba66a  nop
0x1800ba66b  xor     r8d, r8d
0x1800ba66e  mov     dl, 1
0x1800ba670  lea     rcx, [rbp+57h+lpString1]
0x1800ba674  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800ba679  nop
0x1800ba67a  mov     [rbp+57h+var_D0], r15
0x1800ba67e  lea     rcx, [rbp+57h+var_D0]; this
0x1800ba682  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x1800ba687  nop
0x1800ba688  lea     rcx, [rbp+57h+var_C0]
0x1800ba68c  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1800ba692  mov     rax, rbx
0x1800ba695  mov     rcx, [rbp+57h+var_40]
0x1800ba699  xor     rcx, rsp; StackCookie
0x1800ba69c  call    __security_check_cookie
0x1800ba6a1  add     rsp, 0D8h
0x1800ba6a8  pop     r15
0x1800ba6aa  pop     r14
0x1800ba6ac  pop     rdi
0x1800ba6ad  pop     rsi
0x1800ba6ae  pop     rbx
0x1800ba6af  pop     rbp
0x1800ba6b0  retn
```

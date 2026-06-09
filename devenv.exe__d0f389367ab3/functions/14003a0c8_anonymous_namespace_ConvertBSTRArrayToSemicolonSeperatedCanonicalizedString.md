# _anonymous_namespace_::ConvertBSTRArrayToSemicolonSeperatedCanonicalizedString

- ea: `0x14003a0c8`
- end: `0x14003a3c0`
- name: `_anonymous_namespace_::ConvertBSTRArrayToSemicolonSeperatedCanonicalizedString`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14000905c`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140002dd0`
- `0x140003160`
- `0x140004950`
- `0x14000fc60`
- `0x14001e390`
- `0x140033ab0`
- `0x14003a0c8`
- `0x14003b95c`
- `0x14003b9dc`
- `0x14003ba58`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14003a285`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14003a285`
- `OLEAUT32!__imp_SysStringLen` at `0x14003a205`
- `OLEAUT32!__imp_SysStringLen` at `0x14003a205`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14003a164`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14003a164`
- `OLEAUT32!__imp_SafeArrayLock` at `0x14003a194`
- `OLEAUT32!__imp_SafeArrayLock` at `0x14003a194`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14003a152`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14003a33b`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14003a152`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14003a33b`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x14003a17d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x14003a17d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14003a10e`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14003a10e`
- `SHLWAPI!PathCanonicalizeW` at `0x14003a278`
- `SHLWAPI!PathCanonicalizeW` at `0x14003a278`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall anonymous_namespace_::ConvertBSTRArrayToSemicolonSeperatedCanonicalizedString(
        _QWORD *a1,
        SAFEARRAY *a2)
{
  HRESULT Vartype; // eax
  VARTYPE v5; // cx
  HRESULT v6; // eax
  HRESULT v7; // eax
  HRESULT v8; // eax
  struct ATL::IAtlStringMgr *Instance; // rax
  int Count; // r14d
  unsigned int i; // edi
  BSTR *v12; // rax
  _QWORD *v13; // rax
  struct ATL::IAtlStringMgr *v14; // rax
  __int64 v15; // rax
  WCHAR *v16; // rbx
  int v17; // eax
  const unsigned __int16 *v18; // r8
  LPCWSTR v19; // rdx
  LPCWSTR pszPath; // [rsp+20h] [rbp-40h] BYREF
  int v22; // [rsp+28h] [rbp-38h]
  _QWORD v23[2]; // [rsp+30h] [rbp-30h] BYREF
  VARTYPE pvt; // [rsp+40h] [rbp-20h] BYREF
  SAFEARRAY *psa; // [rsp+48h] [rbp-18h] BYREF

  v23[1] = a1;
  v22 = 0;
  psa = 0;
  if ( !a2 )
    goto LABEL_32;
  Vartype = SafeArrayGetVartype(a2, &pvt);
  if ( Vartype < 0 )
    ATL::AtlThrowImpl(Vartype);
  v5 = pvt;
  if ( pvt == 13 && (a2->fFeatures & 0x440) == 0x440 )
  {
    v5 = 9;
    pvt = 9;
  }
  if ( v5 != 8 )
LABEL_32:
    ATL::AtlThrowImpl(-2147024809);
  if ( psa )
  {
    v6 = SafeArrayUnlock(psa);
    if ( v6 < 0 || (v6 = SafeArrayDestroy(psa), v6 < 0) )
      ATL::AtlThrowImpl(v6);
    psa = 0;
  }
  v7 = SafeArrayCopy(a2, &psa);
  if ( v7 < 0 )
    ATL::AtlThrowImpl(v7);
  if ( psa )
  {
    v8 = SafeArrayLock(psa);
    if ( v8 < 0 )
    {
      _mm_lfence();
      ATL::AtlThrowImpl(v8);
    }
  }
  *a1 = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  *a1 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  v22 = 1;
  Count = ATL::CComSafeArray<unsigned short *,8>::GetCount(&psa);
  for ( i = 0; (int)i < Count; ++i )
  {
    if ( *(_QWORD *)ATL::CComSafeArray<unsigned short *,8>::operator[](&psa, i) )
    {
      v12 = (BSTR *)ATL::CComSafeArray<unsigned short *,8>::operator[](&psa, i);
      if ( SysStringLen(*v12) )
      {
        pszPath = 0;
        v13 = (_QWORD *)ATL::CComSafeArray<unsigned short *,8>::operator[](&psa, i);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &pszPath,
          *v13);
        v14 = ATL::CAtlStringMgr::GetInstance();
        if ( !v14 )
          ATL::AtlThrowImpl(-2147467259);
        v15 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v14 + 24LL))(v14);
        v16 = (WCHAR *)(v15 + 24);
        v23[0] = v15 + 24;
        if ( ((1 - *(_DWORD *)(v15 + 16)) | (*(_DWORD *)(v15 + 12) - 260)) < 0 )
        {
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v23, 260);
          v16 = (WCHAR *)v23[0];
        }
        PathCanonicalizeW(v16, pszPath);
        v17 = wcsnlen(v16, *((int *)v16 - 3));
        if ( v17 < 0 || v17 > *((_DWORD *)v16 - 3) )
          ATL::AtlThrowImpl(-2147024809);
        *((_DWORD *)v16 - 4) = v17;
        v16[v17] = 0;
        ATL::CSimpleStringT<unsigned short,0>::operator=(&pszPath, v23);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v16 - 3) + 8LL))(*((_QWORD *)v16 - 3));
        }
        ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveBackslash(&pszPath);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&pszPath);
        v18 = L";";
        if ( !i )
          v18 = &WindowName;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a1,
          L"%s%s",
          v18,
          pszPath);
        v19 = pszPath - 12;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)pszPath - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19);
        }
      }
    }
  }
  SafeArrayUnlock(psa);
  return a1;
}

```

## disassembly

```asm
0x14003a0c8  mov     [rsp-28h+arg_10], rbx
0x14003a0cd  push    rbp
0x14003a0ce  push    rsi
0x14003a0cf  push    rdi
0x14003a0d0  push    r14
0x14003a0d2  push    r15
0x14003a0d4  mov     rbp, rsp
0x14003a0d7  sub     rsp, 60h
0x14003a0db  mov     rax, cs:__security_cookie
0x14003a0e2  xor     rax, rsp
0x14003a0e5  mov     [rbp+var_10], rax
0x14003a0e9  mov     rbx, rdx
0x14003a0ec  mov     rsi, rcx
0x14003a0ef  mov     [rbp+var_28], rcx
0x14003a0f3  xor     r15d, r15d
0x14003a0f6  mov     [rbp+var_38], r15d
0x14003a0fa  mov     [rbp+psa], r15
0x14003a0fe  test    rdx, rdx
0x14003a101  jz      loc_14003A36D
0x14003a107  lea     rdx, [rbp+pvt]; pvt
0x14003a10b  mov     rcx, rbx; psa
0x14003a10e  call    cs:__imp_SafeArrayGetVartype
0x14003a114  test    eax, eax
0x14003a116  js      loc_14003A365
0x14003a11c  movzx   ecx, [rbp+pvt]
0x14003a120  cmp     cx, 0Dh
0x14003a124  jnz     short loc_14003A13F
0x14003a126  movzx   eax, word ptr [rbx+2]
0x14003a12a  mov     edx, 440h
0x14003a12f  and     ax, dx
0x14003a132  cmp     ax, dx
0x14003a135  jnz     short loc_14003A13F
0x14003a137  lea     ecx, [r15+9]
0x14003a13b  mov     [rbp+pvt], cx
0x14003a13f  cmp     cx, 8
0x14003a143  jnz     loc_14003A36D
0x14003a149  mov     rcx, [rbp+psa]; psa
0x14003a14d  test    rcx, rcx
0x14003a150  jz      short loc_14003A176
0x14003a152  call    cs:__imp_SafeArrayUnlock
0x14003a158  test    eax, eax
0x14003a15a  js      loc_14003A380
0x14003a160  mov     rcx, [rbp+psa]; psa
0x14003a164  call    cs:__imp_SafeArrayDestroy
0x14003a16a  test    eax, eax
0x14003a16c  js      loc_14003A380
0x14003a172  mov     [rbp+psa], r15
0x14003a176  lea     rdx, [rbp+psa]; ppsaOut
0x14003a17a  mov     rcx, rbx; psa
0x14003a17d  call    cs:__imp_SafeArrayCopy
0x14003a183  test    eax, eax
0x14003a185  js      loc_14003A378
0x14003a18b  mov     rcx, [rbp+psa]; psa
0x14003a18f  test    rcx, rcx
0x14003a192  jz      short loc_14003A1A2
0x14003a194  call    cs:__imp_SafeArrayLock
0x14003a19a  test    eax, eax
0x14003a19c  js      loc_14003A388
0x14003a1a2  xor     eax, eax
0x14003a1a4  mov     [rsi], rax
0x14003a1a7  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14003a1ac  mov     rcx, rax
0x14003a1af  test    rax, rax
0x14003a1b2  jz      loc_14003A397
0x14003a1b8  mov     rax, [rax]
0x14003a1bb  call    qword ptr [rax+18h]
0x14003a1be  add     rax, 18h
0x14003a1c2  mov     [rsi], rax
0x14003a1c5  mov     [rbp+var_38], 1
0x14003a1cc  lea     rcx, [rbp+psa]
0x14003a1d0  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x14003a1d5  mov     r14d, eax
0x14003a1d8  mov     edi, r15d
0x14003a1db  test    eax, eax
0x14003a1dd  jle     loc_14003A337
0x14003a1e3  mov     edx, edi
0x14003a1e5  lea     rcx, [rbp+psa]
0x14003a1e9  call    ??A?$CComSafeArray@PEAG$07@ATL@@QEAAAEAVCComBSTR@1@H@Z; ATL::CComSafeArray<ushort *,8>::operator[](int)
0x14003a1ee  cmp     [rax], r15
0x14003a1f1  jz      loc_14003A32C
0x14003a1f7  mov     edx, edi
0x14003a1f9  lea     rcx, [rbp+psa]
0x14003a1fd  call    ??A?$CComSafeArray@PEAG$07@ATL@@QEAAAEAVCComBSTR@1@H@Z; ATL::CComSafeArray<ushort *,8>::operator[](int)
0x14003a202  mov     rcx, [rax]; pbstr
0x14003a205  call    cs:__imp_SysStringLen
0x14003a20b  test    eax, eax
0x14003a20d  jz      loc_14003A32C
0x14003a213  mov     [rbp+pszPath], r15
0x14003a217  mov     edx, edi
0x14003a219  lea     rcx, [rbp+psa]
0x14003a21d  call    ??A?$CComSafeArray@PEAG$07@ATL@@QEAAAEAVCComBSTR@1@H@Z; ATL::CComSafeArray<ushort *,8>::operator[](int)
0x14003a222  mov     rdx, [rax]
0x14003a225  lea     rcx, [rbp+pszPath]
0x14003a229  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14003a22e  nop
0x14003a22f  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14003a234  mov     rcx, rax
0x14003a237  test    rax, rax
0x14003a23a  jz      loc_14003A3B5
0x14003a240  mov     rax, [rax]
0x14003a243  call    qword ptr [rax+18h]
0x14003a246  lea     rbx, [rax+18h]
0x14003a24a  mov     [rbp+var_30], rbx
0x14003a24e  mov     ecx, 1
0x14003a253  sub     ecx, [rbx-8]
0x14003a256  mov     eax, [rbx-0Ch]
0x14003a259  mov     edx, 104h
0x14003a25e  sub     eax, edx
0x14003a260  or      eax, ecx
0x14003a262  jge     short loc_14003A271
0x14003a264  lea     rcx, [rbp+var_30]
0x14003a268  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14003a26d  mov     rbx, [rbp+var_30]
0x14003a271  mov     rdx, [rbp+pszPath]; pszPath
0x14003a275  mov     rcx, rbx; pszBuf
0x14003a278  call    cs:__imp_PathCanonicalizeW
0x14003a27e  movsxd  rdx, dword ptr [rbx-0Ch]; MaxCount
0x14003a282  mov     rcx, rbx; Source
0x14003a285  call    cs:__imp_wcsnlen
0x14003a28b  test    eax, eax
0x14003a28d  js      loc_14003A3A5
0x14003a293  cmp     eax, [rbx-0Ch]
0x14003a296  jg      loc_14003A3A5
0x14003a29c  mov     [rbx-10h], eax
0x14003a29f  cdqe
0x14003a2a1  mov     [rbx+rax*2], r15w
0x14003a2a6  lea     rdx, [rbp+var_30]
0x14003a2aa  lea     rcx, [rbp+pszPath]
0x14003a2ae  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14003a2b3  nop
0x14003a2b4  lea     rdx, [rbx-18h]
0x14003a2b8  or      eax, 0FFFFFFFFh
0x14003a2bb  lock xadd [rdx+10h], eax
0x14003a2c0  sub     eax, 1
0x14003a2c3  jg      short loc_14003A2D1
0x14003a2c5  lfence
0x14003a2c8  mov     rcx, [rdx]
0x14003a2cb  mov     rax, [rcx]
0x14003a2ce  call    qword ptr [rax+8]
0x14003a2d1  lea     rcx, [rbp+pszPath]
0x14003a2d5  call    ?RemoveBackslash@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveBackslash(void)
0x14003a2da  lea     rcx, [rbp+pszPath]
0x14003a2de  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x14003a2e3  lea     rax, WindowName
0x14003a2ea  lea     r8, asc_140071870; ";"
0x14003a2f1  test    edi, edi
0x14003a2f3  cmovz   r8, rax
0x14003a2f7  mov     r9, [rbp+pszPath]
0x14003a2fb  lea     rdx, aSS_3; "%s%s"
0x14003a302  mov     rcx, rsi
0x14003a305  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14003a30a  nop
0x14003a30b  mov     rdx, [rbp+pszPath]
0x14003a30f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14003a313  or      eax, 0FFFFFFFFh
0x14003a316  lock xadd [rdx+10h], eax
0x14003a31b  sub     eax, 1
0x14003a31e  jg      short loc_14003A32C
0x14003a320  lfence
0x14003a323  mov     rcx, [rdx]
0x14003a326  mov     rax, [rcx]
0x14003a329  call    qword ptr [rax+8]
0x14003a32c  inc     edi
0x14003a32e  cmp     edi, r14d
0x14003a331  jl      loc_14003A1E3
0x14003a337  mov     rcx, [rbp+psa]; psa
0x14003a33b  call    cs:__imp_SafeArrayUnlock
0x14003a341  nop
0x14003a342  mov     rax, rsi
0x14003a345  mov     rcx, [rbp+var_10]
0x14003a349  xor     rcx, rsp; StackCookie
0x14003a34c  call    __security_check_cookie
0x14003a351  mov     rbx, [rsp+60h+arg_10]
0x14003a359  add     rsp, 60h
0x14003a35d  pop     r15
0x14003a35f  pop     r14
0x14003a361  pop     rdi
0x14003a362  pop     rsi
0x14003a363  pop     rbp
0x14003a364  retn
0x14003a365  mov     ecx, eax; int
0x14003a367  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003a36d  mov     ecx, 80070057h; int
0x14003a372  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003a378  mov     ecx, eax; int
0x14003a37a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003a380  mov     ecx, eax; int
0x14003a382  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003a388  lfence
0x14003a38b  mov     ecx, eax; int
0x14003a38d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003a393  jmp     short loc_14003A396
0x14003a396  nop
0x14003a397  mov     ecx, 80004005h; int
0x14003a39c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003a3a2  jmp     short $+2
0x14003a3a4  nop
0x14003a3a5  mov     ecx, 80070057h; int
0x14003a3aa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003a3b0  jmp     short loc_14003A3B4
0x14003a3b4  nop
0x14003a3b5  mov     ecx, 80004005h; int
0x14003a3ba  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

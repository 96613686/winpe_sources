# ProblemInstance::SecondPassDiagnose(tagHypothesisResult *,ulong,int)

- ea: `0x18001421c`
- end: `0x1800144a0`
- name: `?SecondPassDiagnose@ProblemInstance@@QEAA?AW4tagDIAGNOSIS_STATUS@@PEAUtagHypothesisResult@@KH@Z`
- size: `644`
- prototype: `enum tagDIAGNOSIS_STATUS __fastcall(ProblemInstance *__hidden this, struct tagHypothesisResult *, unsigned int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ede4`

## callees

- `0x18000579c`
- `0x180006d58`
- `0x180006f04`
- `0x18000bca0`
- `0x180013794`
- `0x18001421c`
- `0x18002f010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180014249`
- `KERNEL32!GetTickCount` at `0x1800142cd`
- `KERNEL32!GetTickCount` at `0x180014249`
- `KERNEL32!GetTickCount` at `0x1800142cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014418`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014418`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProblemInstance::SecondPassDiagnose(
        ProblemInstance *this,
        struct tagHypothesisResult *a2,
        unsigned int a3,
        enum tagDIAGNOSIS_STATUS a4)
{
  enum tagDIAGNOSIS_STATUS v7; // esi
  int v8; // ebx
  _QWORD *v9; // r8
  __int64 v10; // rbx
  _QWORD *v11; // r8
  __int64 v12; // rbx
  int v13; // ecx
  _BYTE *v14; // rdx
  __int64 v15; // r8
  char **v16; // rcx
  _QWORD *v17; // r8
  __int64 v18; // rbx
  _QWORD v20[2]; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+30h] BYREF
  enum tagDIAGNOSIS_STATUS v22; // [rsp+98h] [rbp+48h] BYREF

  v22 = a4;
  v7 = DS_NOT_IMPLEMENTED;
  GetTickCount();
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 144LL))(*((_QWORD *)this + 9)) )
  {
    pv = 0;
    v22 = DS_NOT_IMPLEMENTED;
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagHypothesisResult *, LPVOID *, enum tagDIAGNOSIS_STATUS *))(**((_QWORD **)this + 9) + 152LL))(
           *((_QWORD *)this + 9),
           a3,
           a2,
           &pv,
           &v22);
    if ( v8 >= 0 )
    {
      if ( *((_QWORD *)this + 36) )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v20);
        GetTickCount();
        GetDiagnosisStatusString(v22);
        v9 = (_QWORD *)*((_QWORD *)this + 2);
        if ( !*((_DWORD *)v9 - 4) )
          v9 = *(_QWORD **)this;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          (__int64)v20,
          (__int64)L"'%s' ReconfirmLowHealth status %d [%s] HRESULT %X [%d ms] description: %s",
          v9);
        v10 = v20[0];
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 36) + 112LL))(
          *((_QWORD *)this + 36),
          0,
          v20[0],
          *((_QWORD *)this + 5));
        ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
      }
      if ( v22 == DS_DEFERRED )
      {
        if ( *((_QWORD *)this + 36) )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v20);
          v11 = (_QWORD *)*((_QWORD *)this + 2);
          if ( !*((_DWORD *)v11 - 4) )
            v11 = *(_QWORD **)this;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            (__int64)v20,
            (__int64)L"'%s' returned the unsupported state DS_DEFERRED. Second pass state not used.",
            v11);
          v12 = v20[0];
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 36) + 96LL))(
            *((_QWORD *)this + 36),
            0,
            v20[0]);
          ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
        }
        goto LABEL_28;
      }
      if ( v22 == DS_NOT_IMPLEMENTED )
      {
LABEL_28:
        CoTaskMemFree(pv);
        return (unsigned int)v7;
      }
      v7 = v22;
      if ( v22 == DS_INDETERMINATE )
      {
        v13 = 9;
      }
      else
      {
        v13 = 8;
        if ( v22 == DS_CONFIRMED )
          v13 = 10;
      }
      v14 = pv;
      if ( *((_DWORD *)this + 24) < *((_DWORD *)this + 25) )
      {
        *((_DWORD *)this + 25) = v13;
        if ( v14 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)&v14[2 * v15] );
          v16 = (char **)((char *)this + 88);
          goto LABEL_26;
        }
      }
      else
      {
        *((_DWORD *)this + 24) = v13;
        if ( v14 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)&v14[2 * v15] );
          v16 = (char **)((char *)this + 80);
LABEL_26:
          ATL::CSimpleStringT<unsigned short,0>::SetString(v16, v14, v15);
        }
      }
      *((_DWORD *)this + 59) = v7;
      goto LABEL_28;
    }
    if ( v8 != -2147467263 && *((_QWORD *)this + 36) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v20);
      v17 = (_QWORD *)*((_QWORD *)this + 2);
      if ( !*((_DWORD *)v17 - 4) )
        v17 = *(_QWORD **)this;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (__int64)v20,
        (__int64)L"'%s' ReconfirmLowHealth failed. HRESULT: 0x%x.",
        v17,
        (unsigned int)v8);
      v18 = v20[0];
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 36) + 112LL))(
        *((_QWORD *)this + 36),
        0,
        v20[0],
        *((_QWORD *)this + 5));
      ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001421c  mov     [rsp-28h+arg_8], rbx
0x180014221  mov     [rsp-28h+arg_10], rsi
0x180014226  mov     [rsp-28h+arg_18], r9d
0x18001422b  push    rbp
0x18001422c  push    rdi
0x18001422d  push    r12
0x18001422f  push    r14
0x180014231  push    r15
0x180014233  mov     rbp, rsp
0x180014236  sub     rsp, 50h
0x18001423a  mov     ebx, r8d
0x18001423d  mov     r14, rdx
0x180014240  mov     rdi, rcx
0x180014243  xor     r12d, r12d
0x180014246  mov     esi, r12d
0x180014249  call    cs:__imp_GetTickCount
0x18001424f  mov     r15d, eax
0x180014252  mov     rcx, [rdi+48h]
0x180014256  mov     rax, [rcx]
0x180014259  mov     rax, [rax+90h]
0x180014260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014265  test    eax, eax
0x180014267  jz      loc_180014485
0x18001426d  mov     [rbp+pv], r12
0x180014271  mov     [rbp+arg_18], r12d
0x180014275  mov     rcx, [rdi+48h]
0x180014279  mov     rax, [rcx]
0x18001427c  lea     rdx, [rbp+arg_18]
0x180014280  mov     [rsp+50h+var_30], rdx
0x180014285  lea     r9, [rbp+pv]
0x180014289  mov     r8, r14
0x18001428c  mov     edx, ebx
0x18001428e  mov     rax, [rax+98h]
0x180014295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001429a  mov     ebx, eax
0x18001429c  test    eax, eax
0x18001429e  js      loc_180014420
0x1800142a4  cmp     [rdi+120h], r12
0x1800142ab  jz      loc_180014345
0x1800142b1  lea     rcx, [rbp+var_10]
0x1800142b5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800142ba  nop
0x1800142bb  lea     rbx, dword_180033E1C
0x1800142c2  mov     rax, [rbp+pv]
0x1800142c6  test    rax, rax
0x1800142c9  cmovnz  rbx, rax
0x1800142cd  call    cs:__imp_GetTickCount
0x1800142d3  mov     edx, eax
0x1800142d5  sub     edx, r15d
0x1800142d8  mov     r10d, [rdi+0F0h]
0x1800142df  mov     r9d, [rbp+arg_18]
0x1800142e3  mov     ecx, r9d; enum tagDIAGNOSIS_STATUS
0x1800142e6  call    ?GetDiagnosisStatusString@@YAQEAGW4tagDIAGNOSIS_STATUS@@@Z; GetDiagnosisStatusString(tagDIAGNOSIS_STATUS)
0x1800142eb  mov     r8, [rdi+10h]
0x1800142ef  cmp     [r8-10h], r12d
0x1800142f3  jnz     short loc_1800142F8
0x1800142f5  mov     r8, [rdi]
0x1800142f8  mov     [rsp+50h+var_18], rbx
0x1800142fd  mov     [rsp+50h+var_20], edx
0x180014301  mov     [rsp+50h+var_28], r10d
0x180014306  mov     [rsp+50h+var_30], rax
0x18001430b  lea     rdx, aSReconfirmlowh_0; "'%s' ReconfirmLowHealth status %d [%s] "...
0x180014312  lea     rcx, [rbp+var_10]
0x180014316  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001431b  mov     rcx, [rdi+120h]
0x180014322  mov     rax, [rcx]
0x180014325  mov     r9, [rdi+28h]
0x180014329  mov     rbx, [rbp+var_10]
0x18001432d  mov     r8, rbx
0x180014330  xor     edx, edx
0x180014332  mov     rax, [rax+70h]
0x180014336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001433b  nop
0x18001433c  lea     rcx, [rbx-18h]; this
0x180014340  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014345  mov     eax, [rbp+arg_18]
0x180014348  cmp     eax, 4
0x18001434b  jnz     short loc_1800143A9
0x18001434d  cmp     [rdi+120h], r12
0x180014354  jz      loc_180014414
0x18001435a  lea     rcx, [rbp+var_10]
0x18001435e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180014363  nop
0x180014364  mov     r8, [rdi+10h]
0x180014368  cmp     [r8-10h], r12d
0x18001436c  jnz     short loc_180014371
0x18001436e  mov     r8, [rdi]
0x180014371  lea     rdx, aSReturnedTheUn; "'%s' returned the unsupported state DS_"...
0x180014378  lea     rcx, [rbp+var_10]
0x18001437c  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180014381  mov     rcx, [rdi+120h]
0x180014388  mov     rax, [rcx]
0x18001438b  mov     rbx, [rbp+var_10]
0x18001438f  mov     r8, rbx
0x180014392  xor     edx, edx
0x180014394  mov     rax, [rax+60h]
0x180014398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001439d  nop
0x18001439e  lea     rcx, [rbx-18h]; this
0x1800143a2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800143a7  jmp     short loc_180014414
0x1800143a9  test    eax, eax
0x1800143ab  jz      short loc_180014414
0x1800143ad  mov     esi, eax
0x1800143af  cmp     eax, 3
0x1800143b2  jnz     short loc_1800143B9
0x1800143b4  lea     ecx, [rax+6]
0x1800143b7  jmp     short loc_1800143C7
0x1800143b9  mov     ecx, 8
0x1800143be  lea     eax, [rcx+2]
0x1800143c1  cmp     esi, 1
0x1800143c4  cmovz   ecx, eax
0x1800143c7  mov     eax, [rdi+64h]
0x1800143ca  mov     rdx, [rbp+pv]
0x1800143ce  cmp     [rdi+60h], eax
0x1800143d1  jl      short loc_1800143EF
0x1800143d3  mov     [rdi+60h], ecx
0x1800143d6  test    rdx, rdx
0x1800143d9  jz      short loc_18001440E
0x1800143db  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800143df  inc     r8
0x1800143e2  cmp     [rdx+r8*2], r12w
0x1800143e7  jnz     short loc_1800143DF
0x1800143e9  lea     rcx, [rdi+50h]
0x1800143ed  jmp     short loc_180014409
0x1800143ef  mov     [rdi+64h], ecx
0x1800143f2  test    rdx, rdx
0x1800143f5  jz      short loc_18001440E
0x1800143f7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800143fb  inc     r8
0x1800143fe  cmp     [rdx+r8*2], r12w
0x180014403  jnz     short loc_1800143FB
0x180014405  lea     rcx, [rdi+58h]
0x180014409  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001440e  mov     [rdi+0ECh], esi
0x180014414  mov     rcx, [rbp+pv]; pv
0x180014418  call    cs:__imp_CoTaskMemFree
0x18001441e  jmp     short loc_180014485
0x180014420  cmp     ebx, 80004001h
0x180014426  jz      short loc_180014485
0x180014428  cmp     [rdi+120h], r12
0x18001442f  jz      short loc_180014485
0x180014431  lea     rcx, [rbp+var_10]
0x180014435  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001443a  nop
0x18001443b  mov     r8, [rdi+10h]
0x18001443f  cmp     [r8-10h], r12d
0x180014443  jnz     short loc_180014448
0x180014445  mov     r8, [rdi]
0x180014448  mov     r9d, ebx
0x18001444b  lea     rdx, aSReconfirmlowh; "'%s' ReconfirmLowHealth failed. HRESULT"...
0x180014452  lea     rcx, [rbp+var_10]
0x180014456  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001445b  mov     rcx, [rdi+120h]
0x180014462  mov     rdx, [rcx]
0x180014465  mov     rax, [rdx+70h]
0x180014469  mov     r9, [rdi+28h]
0x18001446d  mov     rbx, [rbp+var_10]
0x180014471  mov     r8, rbx
0x180014474  xor     edx, edx
0x180014476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001447b  nop
0x18001447c  lea     rcx, [rbx-18h]; this
0x180014480  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014485  mov     eax, esi
0x180014487  lea     r11, [rsp+50h+var_s0]
0x18001448c  mov     rbx, [r11+38h]
0x180014490  mov     rsi, [r11+40h]
0x180014494  mov     rsp, r11
0x180014497  pop     r15
0x180014499  pop     r14
0x18001449b  pop     r12
0x18001449d  pop     rdi
0x18001449e  pop     rbp
0x18001449f  retn
```

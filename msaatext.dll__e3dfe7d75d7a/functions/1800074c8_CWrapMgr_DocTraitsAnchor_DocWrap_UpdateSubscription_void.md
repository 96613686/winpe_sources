# CWrapMgr<DocTraitsAnchor>::DocWrap_UpdateSubscription(void)

- ea: `0x1800074c8`
- end: `0x1800077dd`
- name: `?DocWrap_UpdateSubscription@?$CWrapMgr@VDocTraitsAnchor@@@@QEAAJXZ`
- size: `789`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800056cc`
- `0x180005f90`
- `0x18000be80`

## callees

- `0x1800026d0`
- `0x180005350`
- `0x1800061e0`
- `0x1800074c8`
- `0x18000bfd4`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CWrapMgr<DocTraitsAnchor>::DocWrap_UpdateSubscription(__int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // rbx
  int v4; // ebp
  __int64 v5; // rdx
  char *v6; // rax
  unsigned int v7; // edx
  __int64 result; // rax
  _QWORD *v9; // rbx
  __int64 v10; // rbp
  _QWORD *v11; // r15
  int v12; // r14d
  unsigned int v13; // ebp
  int v14; // [rsp+20h] [rbp-68h]

  if ( (*(_DWORD *)(a1 + 48) & 0xFFFFFFE0) != 0 )
    InternalTrace(
      L"windows\\oleacc\\msaatext\\docwrap.cpp",
      0x19Eu,
      8u,
      0,
      v14,
      0,
      (wchar_t *)L"( m_dwSinkMask & ~ TS_AS_ALL_SINKS ) == 0");
  if ( !*(_DWORD *)(a1 + 52) && *(_DWORD *)(a1 + 48) )
    InternalTrace(
      L"windows\\oleacc\\msaatext\\docwrap.cpp",
      0x1A0u,
      8u,
      0,
      v14,
      0,
      (wchar_t *)L"m_fSinkActive || m_dwSinkMask == 0");
  v2 = 0;
  v3 = *(_QWORD *)(a1 + 56);
  v4 = 0;
  while ( v3 )
  {
    if ( *(_QWORD *)(v3 + 24) )
    {
      if ( (*(_DWORD *)(v3 + 48) & 0xFFFFFFE0) != 0 )
        InternalTrace(
          L"windows\\oleacc\\msaatext\\docwrap.cpp",
          0x1A9u,
          8u,
          0,
          v14,
          0,
          (wchar_t *)L"( i->m_Sink.m_dwMask & ~ TS_AS_ALL_SINKS ) == 0");
      v2 |= *(_DWORD *)(v3 + 48);
      v4 = 1;
    }
    v3 = *(_QWORD *)(v3 + 8);
  }
  if ( (v2 & 0xFFFFFFE0) != 0 )
    InternalTrace(
      L"windows\\oleacc\\msaatext\\docwrap.cpp",
      0x1AFu,
      8u,
      0,
      v14,
      0,
      (wchar_t *)L"( NewMask & ~ TS_AS_ALL_SINKS ) == 0");
  if ( !v4 && v2 )
    InternalTrace(
      L"windows\\oleacc\\msaatext\\docwrap.cpp",
      0x1B1u,
      8u,
      0,
      v14,
      0,
      (wchar_t *)L"NewfSinkActive || NewMask == 0");
  if ( v4 == *(_DWORD *)(a1 + 52) && v2 == *(_DWORD *)(a1 + 48) )
    return 0;
  if ( !v4 )
  {
    v5 = *(_QWORD *)(a1 + 40);
    *(_QWORD *)(a1 + 48) = 0;
    if ( v5 )
    {
      if ( (unsigned int)SEHWrap_TextStoreBase<BasicDocTraitsACP>::UnadviseSink(a1 + 16, v5 + 8) )
        InternalTrace(L"windows\\oleacc\\msaatext\\docwrap.cpp", 0x1D9u, 8u, 0, v14, 0, (wchar_t *)L"hr == S_OK");
      if ( !*(_QWORD *)(a1 + 40) )
        return 0;
      v6 = (char *)L"m_pSinkWrap == NULL";
      v7 = 477;
    }
    else
    {
      v6 = (char *)L"FALSE";
      v7 = 463;
    }
    InternalTrace(L"windows\\oleacc\\msaatext\\docwrap.cpp", v7, 8u, 0, v14, 0, (wchar_t *)v6);
    return 0;
  }
  if ( *(_DWORD *)(a1 + 52) && !*(_QWORD *)(a1 + 40) )
    InternalTrace(
      L"windows\\oleacc\\msaatext\\docwrap.cpp",
      0x1E7u,
      8u,
      0,
      v14,
      0,
      (wchar_t *)L"! m_fSinkActive || m_pSinkWrap");
  v9 = (_QWORD *)(a1 + 40);
  if ( *(_QWORD *)(a1 + 40) )
  {
    v12 = 0;
    v11 = (_QWORD *)(a1 + 40);
    goto LABEL_42;
  }
  result = CreateLocalInstance<CSinkWrapAnchor>((_QWORD *)(a1 + 40));
  if ( (_DWORD)result )
    return result;
  v10 = *v9;
  if ( *(_QWORD *)(*v9 + 32LL) )
  {
    v11 = (_QWORD *)(a1 + 40);
    goto LABEL_39;
  }
  if ( *(_QWORD *)(v10 + 40) )
  {
    v11 = (_QWORD *)(a1 + 40);
LABEL_39:
    InternalTrace(
      L"windows\\oleacc\\msaatext\\docwrap.cpp",
      0x7FEu,
      8u,
      0,
      v14,
      0,
      (wchar_t *)L"CSinkWrapBase::Init should only be called once when m_pMgr is NULL");
    goto LABEL_40;
  }
  v11 = (_QWORD *)(a1 + 40);
LABEL_40:
  *(_QWORD *)(v10 + 32) = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  *(_QWORD *)(v10 + 40) = a1 + 56;
  v12 = 1;
LABEL_42:
  v13 = SEHWrap_TextStoreBase<BasicDocTraitsACP>::AdviseSink(
          a1 + 16,
          &GUID_aa80e9fe_2021_11d2_93e0_0060b067b86e,
          (*v11 + 8LL) & -(__int64)(*v11 != 0),
          v2);
  if ( v13 )
    v13 = SEHWrap_TextStoreBase<BasicDocTraitsACP>::AdviseSink(
            a1 + 16,
            &GUID_aa80e905_2021_11d2_93e0_0060b067b86e,
            *v9,
            v2);
  if ( v12 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 16LL))(*v9);
  if ( v13 )
  {
    InternalTrace(L"windows\\oleacc\\msaatext\\docwrap.cpp", 0x216u, 8u, 0, v14, 0, (wchar_t *)L"AdviseSink failed");
  }
  else
  {
    *(_DWORD *)(a1 + 52) = 1;
    *(_DWORD *)(a1 + 48) = v2;
  }
  return v13;
}

```

## disassembly

```asm
0x1800074c8  push    rbx
0x1800074ca  push    rbp
0x1800074cb  push    rsi
0x1800074cc  push    rdi
0x1800074cd  push    r12
0x1800074cf  push    r13
0x1800074d1  push    r14
0x1800074d3  push    r15
0x1800074d5  sub     rsp, 48h
0x1800074d9  xor     r13d, r13d
0x1800074dc  lea     r15, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x1800074e3  test    dword ptr [rcx+30h], 0FFFFFFE0h
0x1800074ea  mov     rdi, rcx
0x1800074ed  lea     r14d, [r13+8]
0x1800074f1  jz      short loc_180007517
0x1800074f3  lea     rax, aMDwsinkmaskTsA; "( m_dwSinkMask & ~ TS_AS_ALL_SINKS ) =="...
0x1800074fa  xor     r9d, r9d
0x1800074fd  mov     [rsp+88h+var_58], rax; __int64
0x180007502  mov     r8d, r14d
0x180007505  mov     edx, 19Eh; Value
0x18000750a  mov     [rsp+88h+var_60], r13d; int
0x18000750f  mov     rcx, r15; unsigned __int16 *
0x180007512  call    InternalTrace
0x180007517  cmp     [rdi+34h], r13d
0x18000751b  jnz     short loc_180007547
0x18000751d  cmp     [rdi+30h], r13d
0x180007521  jz      short loc_180007547
0x180007523  lea     rax, aMFsinkactiveMD; "m_fSinkActive || m_dwSinkMask == 0"
0x18000752a  xor     r9d, r9d
0x18000752d  mov     [rsp+88h+var_58], rax; __int64
0x180007532  mov     r8d, r14d
0x180007535  mov     edx, 1A0h; Value
0x18000753a  mov     [rsp+88h+var_60], r13d; int
0x18000753f  mov     rcx, r15; unsigned __int16 *
0x180007542  call    InternalTrace
0x180007547  lea     r12, [rdi+38h]
0x18000754b  mov     esi, r13d
0x18000754e  mov     rbx, [r12]
0x180007552  mov     ebp, r13d
0x180007555  test    rbx, rbx
0x180007558  jz      short loc_18000759B
0x18000755a  cmp     [rbx+18h], r13
0x18000755e  jz      short loc_180007595
0x180007560  test    dword ptr [rbx+30h], 0FFFFFFE0h
0x180007567  jz      short loc_18000758D
0x180007569  lea     rax, aIMSinkMDwmaskT; "( i->m_Sink.m_dwMask & ~ TS_AS_ALL_SINK"...
0x180007570  xor     r9d, r9d
0x180007573  mov     [rsp+88h+var_58], rax; __int64
0x180007578  mov     r8d, r14d
0x18000757b  mov     edx, 1A9h; Value
0x180007580  mov     [rsp+88h+var_60], r13d; int
0x180007585  mov     rcx, r15; unsigned __int16 *
0x180007588  call    InternalTrace
0x18000758d  or      esi, [rbx+30h]
0x180007590  mov     ebp, 1
0x180007595  mov     rbx, [rbx+8]
0x180007599  jmp     short loc_180007555
0x18000759b  test    esi, 0FFFFFFE0h
0x1800075a1  jz      short loc_1800075C7
0x1800075a3  lea     rax, aNewmaskTsAsAll; "( NewMask & ~ TS_AS_ALL_SINKS ) == 0"
0x1800075aa  xor     r9d, r9d
0x1800075ad  mov     [rsp+88h+var_58], rax; __int64
0x1800075b2  mov     r8d, r14d
0x1800075b5  mov     edx, 1AFh; Value
0x1800075ba  mov     [rsp+88h+var_60], r13d; int
0x1800075bf  mov     rcx, r15; unsigned __int16 *
0x1800075c2  call    InternalTrace
0x1800075c7  test    ebp, ebp
0x1800075c9  jnz     short loc_1800075F3
0x1800075cb  test    esi, esi
0x1800075cd  jz      short loc_1800075F3
0x1800075cf  lea     rax, aNewfsinkactive; "NewfSinkActive || NewMask == 0"
0x1800075d6  xor     r9d, r9d
0x1800075d9  mov     [rsp+88h+var_58], rax; __int64
0x1800075de  mov     r8d, r14d
0x1800075e1  mov     edx, 1B1h; Value
0x1800075e6  mov     [rsp+88h+var_60], r13d; int
0x1800075eb  mov     rcx, r15; unsigned __int16 *
0x1800075ee  call    InternalTrace
0x1800075f3  cmp     ebp, [rdi+34h]
0x1800075f6  jnz     short loc_180007601
0x1800075f8  cmp     esi, [rdi+30h]
0x1800075fb  jz      loc_180007682
0x180007601  test    ebp, ebp
0x180007603  jnz     loc_180007689
0x180007609  mov     rdx, [rdi+28h]
0x18000760d  mov     [rdi+30h], r13
0x180007611  test    rdx, rdx
0x180007614  jnz     short loc_180007624
0x180007616  lea     rax, aFalse; "FALSE"
0x18000761d  mov     edx, 1CFh
0x180007622  jmp     short loc_18000766A
0x180007624  add     rdx, r14
0x180007627  lea     rcx, [rdi+10h]
0x18000762b  call    ?UnadviseSink@?$SEHWrap_TextStoreBase@VBasicDocTraitsACP@@@@QEAAJPEAUIUnknown@@@Z; SEHWrap_TextStoreBase<BasicDocTraitsACP>::UnadviseSink(IUnknown *)
0x180007630  test    eax, eax
0x180007632  jz      short loc_180007658
0x180007634  lea     rax, aHrSOk; "hr == S_OK"
0x18000763b  xor     r9d, r9d
0x18000763e  mov     [rsp+88h+var_58], rax; __int64
0x180007643  mov     r8d, r14d
0x180007646  mov     edx, 1D9h; Value
0x18000764b  mov     [rsp+88h+var_60], r13d; int
0x180007650  mov     rcx, r15; unsigned __int16 *
0x180007653  call    InternalTrace
0x180007658  cmp     [rdi+28h], r13
0x18000765c  jz      short loc_180007682
0x18000765e  lea     rax, aMPsinkwrapNull; "m_pSinkWrap == NULL"
0x180007665  mov     edx, 1DDh; Value
0x18000766a  mov     [rsp+88h+var_58], rax; __int64
0x18000766f  xor     r9d, r9d
0x180007672  mov     r8d, r14d
0x180007675  mov     [rsp+88h+var_60], r13d; int
0x18000767a  mov     rcx, r15; unsigned __int16 *
0x18000767d  call    InternalTrace
0x180007682  xor     eax, eax
0x180007684  jmp     loc_1800077CC
0x180007689  cmp     [rdi+34h], r13d
0x18000768d  jz      short loc_1800076B9
0x18000768f  cmp     [rdi+28h], r13
0x180007693  jnz     short loc_1800076B9
0x180007695  lea     rax, aMFsinkactiveMP; "! m_fSinkActive || m_pSinkWrap"
0x18000769c  xor     r9d, r9d
0x18000769f  mov     [rsp+88h+var_58], rax; __int64
0x1800076a4  mov     r8d, r14d
0x1800076a7  mov     edx, 1E7h; Value
0x1800076ac  mov     [rsp+88h+var_60], r13d; int
0x1800076b1  mov     rcx, r15; unsigned __int16 *
0x1800076b4  call    InternalTrace
0x1800076b9  lea     rbx, [rdi+28h]
0x1800076bd  cmp     [rbx], r13
0x1800076c0  jnz     short loc_180007736
0x1800076c2  mov     rcx, rbx
0x1800076c5  call    ??$CreateLocalInstance@VCSinkWrapAnchor@@@@YAJPEAPEAVCSinkWrapAnchor@@@Z; CreateLocalInstance<CSinkWrapAnchor>(CSinkWrapAnchor * *)
0x1800076ca  test    eax, eax
0x1800076cc  jnz     loc_1800077CC
0x1800076d2  mov     rbp, [rbx]
0x1800076d5  cmp     [rbp+20h], r13
0x1800076d9  jnz     short loc_1800076EC
0x1800076db  cmp     [rbp+28h], r13
0x1800076df  jz      short loc_1800076E7
0x1800076e1  lea     r15, [rdi+28h]
0x1800076e5  jmp     short loc_1800076EF
0x1800076e7  mov     r15, rbx
0x1800076ea  jmp     short loc_180007717
0x1800076ec  mov     r15, rbx
0x1800076ef  lea     rax, aCsinkwrapbaseI; "CSinkWrapBase::Init should only be call"...
0x1800076f6  xor     r9d, r9d
0x1800076f9  mov     [rsp+88h+var_58], rax; __int64
0x1800076fe  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x180007705  mov     edx, 7FEh; Value
0x18000770a  mov     [rsp+88h+var_60], r13d; int
0x18000770f  mov     r8d, r14d
0x180007712  call    InternalTrace
0x180007717  mov     [rbp+20h], rdi
0x18000771b  mov     rcx, rdi
0x18000771e  mov     rax, [rdi]
0x180007721  mov     rax, [rax+8]
0x180007725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000772a  mov     [rbp+28h], r12
0x18000772e  mov     r14d, 1
0x180007734  jmp     short loc_18000773C
0x180007736  mov     r14d, r13d
0x180007739  mov     r15, rbx
0x18000773c  mov     rax, [r15]
0x18000773f  lea     rcx, [rdi+10h]
0x180007743  mov     r9d, esi
0x180007746  lea     rdx, [rax+8]
0x18000774a  neg     rax
0x18000774d  sbb     r8, r8
0x180007750  and     r8, rdx
0x180007753  lea     rdx, _GUID_aa80e9fe_2021_11d2_93e0_0060b067b86e
0x18000775a  call    ?AdviseSink@?$SEHWrap_TextStoreBase@VBasicDocTraitsACP@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; SEHWrap_TextStoreBase<BasicDocTraitsACP>::AdviseSink(_GUID const &,IUnknown *,ulong)
0x18000775f  mov     ebp, eax
0x180007761  test    eax, eax
0x180007763  jz      short loc_18000777D
0x180007765  mov     r8, [rbx]
0x180007768  lea     rdx, _GUID_aa80e905_2021_11d2_93e0_0060b067b86e
0x18000776f  mov     r9d, esi
0x180007772  lea     rcx, [rdi+10h]
0x180007776  call    ?AdviseSink@?$SEHWrap_TextStoreBase@VBasicDocTraitsACP@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; SEHWrap_TextStoreBase<BasicDocTraitsACP>::AdviseSink(_GUID const &,IUnknown *,ulong)
0x18000777b  mov     ebp, eax
0x18000777d  test    r14d, r14d
0x180007780  jz      short loc_180007791
0x180007782  mov     rcx, [rbx]
0x180007785  mov     rax, [rcx]
0x180007788  mov     rax, [rax+10h]
0x18000778c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007791  test    ebp, ebp
0x180007793  jnz     short loc_1800077A1
0x180007795  mov     dword ptr [rdi+34h], 1
0x18000779c  mov     [rdi+30h], esi
0x18000779f  jmp     short loc_1800077CA
0x1800077a1  xor     r9d, r9d
0x1800077a4  lea     rax, aAdvisesinkFail; "AdviseSink failed"
0x1800077ab  mov     [rsp+88h+var_58], rax; __int64
0x1800077b0  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x1800077b7  mov     edx, 216h; Value
0x1800077bc  mov     [rsp+88h+var_60], r13d; int
0x1800077c1  lea     r8d, [r9+8]
0x1800077c5  call    InternalTrace
0x1800077ca  mov     eax, ebp
0x1800077cc  add     rsp, 48h
0x1800077d0  pop     r15
0x1800077d2  pop     r14
0x1800077d4  pop     r13
0x1800077d6  pop     r12
0x1800077d8  pop     rdi
0x1800077d9  pop     rsi
0x1800077da  pop     rbp
0x1800077db  pop     rbx
0x1800077dc  retn
```

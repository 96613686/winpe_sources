# CWrapMgr<DocTraitsACP>::DocWrap_UpdateSubscription(void)

- ea: `0x1800071ac`
- end: `0x1800074c1`
- name: `?DocWrap_UpdateSubscription@?$CWrapMgr@VDocTraitsACP@@@@QEAAJXZ`
- size: `789`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800055b4`
- `0x180005d40`
- `0x18000bd20`

## callees

- `0x1800026d0`
- `0x18000527c`
- `0x1800061e0`
- `0x1800071ac`
- `0x18000bfd4`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CWrapMgr<DocTraitsACP>::DocWrap_UpdateSubscription(__int64 a1)
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
  result = CreateLocalInstance<CSinkWrapACP>((_QWORD *)(a1 + 40));
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
          &GUID_aa80e901_2021_11d2_93e0_0060b067b86e,
          (*v11 + 8LL) & -(__int64)(*v11 != 0),
          v2);
  if ( v13 )
    v13 = SEHWrap_TextStoreBase<BasicDocTraitsACP>::AdviseSink(
            a1 + 16,
            &GUID_22d44c94_a419_4542_a272_ae26093ececf,
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
0x1800071ac  push    rbx
0x1800071ae  push    rbp
0x1800071af  push    rsi
0x1800071b0  push    rdi
0x1800071b1  push    r12
0x1800071b3  push    r13
0x1800071b5  push    r14
0x1800071b7  push    r15
0x1800071b9  sub     rsp, 48h
0x1800071bd  xor     r13d, r13d
0x1800071c0  lea     r15, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x1800071c7  test    dword ptr [rcx+30h], 0FFFFFFE0h
0x1800071ce  mov     rdi, rcx
0x1800071d1  lea     r14d, [r13+8]
0x1800071d5  jz      short loc_1800071FB
0x1800071d7  lea     rax, aMDwsinkmaskTsA; "( m_dwSinkMask & ~ TS_AS_ALL_SINKS ) =="...
0x1800071de  xor     r9d, r9d
0x1800071e1  mov     [rsp+88h+var_58], rax; __int64
0x1800071e6  mov     r8d, r14d
0x1800071e9  mov     edx, 19Eh; Value
0x1800071ee  mov     [rsp+88h+var_60], r13d; int
0x1800071f3  mov     rcx, r15; unsigned __int16 *
0x1800071f6  call    InternalTrace
0x1800071fb  cmp     [rdi+34h], r13d
0x1800071ff  jnz     short loc_18000722B
0x180007201  cmp     [rdi+30h], r13d
0x180007205  jz      short loc_18000722B
0x180007207  lea     rax, aMFsinkactiveMD; "m_fSinkActive || m_dwSinkMask == 0"
0x18000720e  xor     r9d, r9d
0x180007211  mov     [rsp+88h+var_58], rax; __int64
0x180007216  mov     r8d, r14d
0x180007219  mov     edx, 1A0h; Value
0x18000721e  mov     [rsp+88h+var_60], r13d; int
0x180007223  mov     rcx, r15; unsigned __int16 *
0x180007226  call    InternalTrace
0x18000722b  lea     r12, [rdi+38h]
0x18000722f  mov     esi, r13d
0x180007232  mov     rbx, [r12]
0x180007236  mov     ebp, r13d
0x180007239  test    rbx, rbx
0x18000723c  jz      short loc_18000727F
0x18000723e  cmp     [rbx+18h], r13
0x180007242  jz      short loc_180007279
0x180007244  test    dword ptr [rbx+30h], 0FFFFFFE0h
0x18000724b  jz      short loc_180007271
0x18000724d  lea     rax, aIMSinkMDwmaskT; "( i->m_Sink.m_dwMask & ~ TS_AS_ALL_SINK"...
0x180007254  xor     r9d, r9d
0x180007257  mov     [rsp+88h+var_58], rax; __int64
0x18000725c  mov     r8d, r14d
0x18000725f  mov     edx, 1A9h; Value
0x180007264  mov     [rsp+88h+var_60], r13d; int
0x180007269  mov     rcx, r15; unsigned __int16 *
0x18000726c  call    InternalTrace
0x180007271  or      esi, [rbx+30h]
0x180007274  mov     ebp, 1
0x180007279  mov     rbx, [rbx+8]
0x18000727d  jmp     short loc_180007239
0x18000727f  test    esi, 0FFFFFFE0h
0x180007285  jz      short loc_1800072AB
0x180007287  lea     rax, aNewmaskTsAsAll; "( NewMask & ~ TS_AS_ALL_SINKS ) == 0"
0x18000728e  xor     r9d, r9d
0x180007291  mov     [rsp+88h+var_58], rax; __int64
0x180007296  mov     r8d, r14d
0x180007299  mov     edx, 1AFh; Value
0x18000729e  mov     [rsp+88h+var_60], r13d; int
0x1800072a3  mov     rcx, r15; unsigned __int16 *
0x1800072a6  call    InternalTrace
0x1800072ab  test    ebp, ebp
0x1800072ad  jnz     short loc_1800072D7
0x1800072af  test    esi, esi
0x1800072b1  jz      short loc_1800072D7
0x1800072b3  lea     rax, aNewfsinkactive; "NewfSinkActive || NewMask == 0"
0x1800072ba  xor     r9d, r9d
0x1800072bd  mov     [rsp+88h+var_58], rax; __int64
0x1800072c2  mov     r8d, r14d
0x1800072c5  mov     edx, 1B1h; Value
0x1800072ca  mov     [rsp+88h+var_60], r13d; int
0x1800072cf  mov     rcx, r15; unsigned __int16 *
0x1800072d2  call    InternalTrace
0x1800072d7  cmp     ebp, [rdi+34h]
0x1800072da  jnz     short loc_1800072E5
0x1800072dc  cmp     esi, [rdi+30h]
0x1800072df  jz      loc_180007366
0x1800072e5  test    ebp, ebp
0x1800072e7  jnz     loc_18000736D
0x1800072ed  mov     rdx, [rdi+28h]
0x1800072f1  mov     [rdi+30h], r13
0x1800072f5  test    rdx, rdx
0x1800072f8  jnz     short loc_180007308
0x1800072fa  lea     rax, aFalse; "FALSE"
0x180007301  mov     edx, 1CFh
0x180007306  jmp     short loc_18000734E
0x180007308  add     rdx, r14
0x18000730b  lea     rcx, [rdi+10h]
0x18000730f  call    ?UnadviseSink@?$SEHWrap_TextStoreBase@VBasicDocTraitsACP@@@@QEAAJPEAUIUnknown@@@Z; SEHWrap_TextStoreBase<BasicDocTraitsACP>::UnadviseSink(IUnknown *)
0x180007314  test    eax, eax
0x180007316  jz      short loc_18000733C
0x180007318  lea     rax, aHrSOk; "hr == S_OK"
0x18000731f  xor     r9d, r9d
0x180007322  mov     [rsp+88h+var_58], rax; __int64
0x180007327  mov     r8d, r14d
0x18000732a  mov     edx, 1D9h; Value
0x18000732f  mov     [rsp+88h+var_60], r13d; int
0x180007334  mov     rcx, r15; unsigned __int16 *
0x180007337  call    InternalTrace
0x18000733c  cmp     [rdi+28h], r13
0x180007340  jz      short loc_180007366
0x180007342  lea     rax, aMPsinkwrapNull; "m_pSinkWrap == NULL"
0x180007349  mov     edx, 1DDh; Value
0x18000734e  mov     [rsp+88h+var_58], rax; __int64
0x180007353  xor     r9d, r9d
0x180007356  mov     r8d, r14d
0x180007359  mov     [rsp+88h+var_60], r13d; int
0x18000735e  mov     rcx, r15; unsigned __int16 *
0x180007361  call    InternalTrace
0x180007366  xor     eax, eax
0x180007368  jmp     loc_1800074B0
0x18000736d  cmp     [rdi+34h], r13d
0x180007371  jz      short loc_18000739D
0x180007373  cmp     [rdi+28h], r13
0x180007377  jnz     short loc_18000739D
0x180007379  lea     rax, aMFsinkactiveMP; "! m_fSinkActive || m_pSinkWrap"
0x180007380  xor     r9d, r9d
0x180007383  mov     [rsp+88h+var_58], rax; __int64
0x180007388  mov     r8d, r14d
0x18000738b  mov     edx, 1E7h; Value
0x180007390  mov     [rsp+88h+var_60], r13d; int
0x180007395  mov     rcx, r15; unsigned __int16 *
0x180007398  call    InternalTrace
0x18000739d  lea     rbx, [rdi+28h]
0x1800073a1  cmp     [rbx], r13
0x1800073a4  jnz     short loc_18000741A
0x1800073a6  mov     rcx, rbx
0x1800073a9  call    ??$CreateLocalInstance@VCSinkWrapACP@@@@YAJPEAPEAVCSinkWrapACP@@@Z; CreateLocalInstance<CSinkWrapACP>(CSinkWrapACP * *)
0x1800073ae  test    eax, eax
0x1800073b0  jnz     loc_1800074B0
0x1800073b6  mov     rbp, [rbx]
0x1800073b9  cmp     [rbp+20h], r13
0x1800073bd  jnz     short loc_1800073D0
0x1800073bf  cmp     [rbp+28h], r13
0x1800073c3  jz      short loc_1800073CB
0x1800073c5  lea     r15, [rdi+28h]
0x1800073c9  jmp     short loc_1800073D3
0x1800073cb  mov     r15, rbx
0x1800073ce  jmp     short loc_1800073FB
0x1800073d0  mov     r15, rbx
0x1800073d3  lea     rax, aCsinkwrapbaseI; "CSinkWrapBase::Init should only be call"...
0x1800073da  xor     r9d, r9d
0x1800073dd  mov     [rsp+88h+var_58], rax; __int64
0x1800073e2  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x1800073e9  mov     edx, 7FEh; Value
0x1800073ee  mov     [rsp+88h+var_60], r13d; int
0x1800073f3  mov     r8d, r14d
0x1800073f6  call    InternalTrace
0x1800073fb  mov     [rbp+20h], rdi
0x1800073ff  mov     rcx, rdi
0x180007402  mov     rax, [rdi]
0x180007405  mov     rax, [rax+8]
0x180007409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000740e  mov     [rbp+28h], r12
0x180007412  mov     r14d, 1
0x180007418  jmp     short loc_180007420
0x18000741a  mov     r14d, r13d
0x18000741d  mov     r15, rbx
0x180007420  mov     rax, [r15]
0x180007423  lea     rcx, [rdi+10h]
0x180007427  mov     r9d, esi
0x18000742a  lea     rdx, [rax+8]
0x18000742e  neg     rax
0x180007431  sbb     r8, r8
0x180007434  and     r8, rdx
0x180007437  lea     rdx, _GUID_aa80e901_2021_11d2_93e0_0060b067b86e
0x18000743e  call    ?AdviseSink@?$SEHWrap_TextStoreBase@VBasicDocTraitsACP@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; SEHWrap_TextStoreBase<BasicDocTraitsACP>::AdviseSink(_GUID const &,IUnknown *,ulong)
0x180007443  mov     ebp, eax
0x180007445  test    eax, eax
0x180007447  jz      short loc_180007461
0x180007449  mov     r8, [rbx]
0x18000744c  lea     rdx, _GUID_22d44c94_a419_4542_a272_ae26093ececf
0x180007453  mov     r9d, esi
0x180007456  lea     rcx, [rdi+10h]
0x18000745a  call    ?AdviseSink@?$SEHWrap_TextStoreBase@VBasicDocTraitsACP@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; SEHWrap_TextStoreBase<BasicDocTraitsACP>::AdviseSink(_GUID const &,IUnknown *,ulong)
0x18000745f  mov     ebp, eax
0x180007461  test    r14d, r14d
0x180007464  jz      short loc_180007475
0x180007466  mov     rcx, [rbx]
0x180007469  mov     rax, [rcx]
0x18000746c  mov     rax, [rax+10h]
0x180007470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007475  test    ebp, ebp
0x180007477  jnz     short loc_180007485
0x180007479  mov     dword ptr [rdi+34h], 1
0x180007480  mov     [rdi+30h], esi
0x180007483  jmp     short loc_1800074AE
0x180007485  xor     r9d, r9d
0x180007488  lea     rax, aAdvisesinkFail; "AdviseSink failed"
0x18000748f  mov     [rsp+88h+var_58], rax; __int64
0x180007494  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x18000749b  mov     edx, 216h; Value
0x1800074a0  mov     [rsp+88h+var_60], r13d; int
0x1800074a5  lea     r8d, [r9+8]
0x1800074a9  call    InternalTrace
0x1800074ae  mov     eax, ebp
0x1800074b0  add     rsp, 48h
0x1800074b4  pop     r15
0x1800074b6  pop     r14
0x1800074b8  pop     r13
0x1800074ba  pop     r12
0x1800074bc  pop     rdi
0x1800074bd  pop     rsi
0x1800074be  pop     rbp
0x1800074bf  pop     rbx
0x1800074c0  retn
```

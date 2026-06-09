# ProblemInstance::Repair(long *,tagPROBLEM_TYPE,uint)

- ea: `0x180013c3c`
- end: `0x180014176`
- name: `?Repair@ProblemInstance@@QEAA?AW4tagREPAIR_STATUS@@PEAJW4tagPROBLEM_TYPE@@I@Z`
- size: `1338`
- prototype: `enum tagREPAIR_STATUS __fastcall(ProblemInstance *__hidden this, int *, enum tagPROBLEM_TYPE, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18000e034`

## callees

- `0x18000579c`
- `0x180006d58`
- `0x18000bca0`
- `0x18000c42c`
- `0x1800121a8`
- `0x180013c3c`
- `0x180015308`
- `0x18001b3a8`
- `0x18002f010`

## string_xrefs

- `0x180013cf6`: `Repair Failed: Asked to perform repair #%i when there are only %i repairs.`
- `0x180013f68`: `%s repair status %d HRESULT %X `
- `0x180013fbd`: `Treating RS_USER_ACTION as RS_REPAIRED.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProblemInstance::Repair(ProblemInstance *this, int *a2, enum tagPROBLEM_TYPE a3, unsigned int a4)
{
  __int64 v4; // r14
  unsigned __int8 v8; // r12
  struct _FILETIME v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v14; // rbx
  __int64 v15; // r13
  int v16; // ecx
  int v17; // r14d
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  signed __int64 v24; // rdx
  int v25; // eax
  struct _FILETIME *TickCount; // rax
  struct _FILETIME v27; // r13
  signed __int64 v28; // r8
  int v29; // ecx
  struct _FILETIME *v30; // rax
  int v31; // eax
  __int64 v32; // r8
  __int64 v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // rax
  DWORD dwHighDateTime; // r9d
  DWORD dwLowDateTime; // ecx
  int v38; // ebx
  unsigned __int64 v39; // rcx
  __int64 v40; // r10
  unsigned int v41; // [rsp+34h] [rbp-34h] BYREF
  __int64 v42; // [rsp+38h] [rbp-30h] BYREF
  __int64 v43; // [rsp+40h] [rbp-28h] BYREF
  struct NetworkDiagnosticsEngine *v44; // [rsp+48h] [rbp-20h]
  struct _FILETIME v45[3]; // [rsp+50h] [rbp-18h] BYREF

  v4 = a4;
  v41 = 0;
  v42 = 0;
  v44 = NetworkDiagnosticsEngine::Instance();
  if ( !v44 )
    return 2;
  if ( !*((_QWORD *)this + 36) && NetworkDiagnosticsEngine::Instance() )
    *((_QWORD *)this + 36) = *(_QWORD *)NetworkDiagnosticsEngine::Instance();
  if ( ((a3 - 1) & 0xFFFFFFFC) != 0 || a3 == (PT_LOWER_HEALTH|PT_LOW_HEALTH) )
  {
    v8 = 0;
    v9 = (struct _FILETIME)*((_QWORD *)this + 24);
    v10 = 204;
    v11 = 100;
  }
  else
  {
    v8 = 1;
    v9 = (struct _FILETIME)*((_QWORD *)this + 23);
    v10 = 200;
    v11 = 96;
  }
  if ( (unsigned int)v4 >= *((_DWORD *)this + 26) )
  {
    if ( *((_QWORD *)this + 36) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v43);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (__int64)&v43,
        (__int64)L"Repair Failed: Asked to perform repair #%i when there are only %i repairs.",
        (unsigned int)v4,
        *((unsigned int *)this + 26));
      v12 = v43;
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 36) + 96LL))(
        *((_QWORD *)this + 36),
        2,
        v43);
      ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
    }
    return 2;
  }
  v14 = *((_QWORD *)this + 14) + 112 * v4;
  if ( !v14 )
  {
LABEL_14:
    if ( v8 )
      *((_DWORD *)this + 24) = 11;
    else
      *((_DWORD *)this + 25) = 11;
    return 2;
  }
  v15 = *((_QWORD *)this + (v8 ^ 1LL) + 23);
  v43 = v15;
  v16 = *(_DWORD *)((char *)this + v11);
  v17 = *(_DWORD *)((char *)this + v10);
  *((_QWORD *)this + 31) = v14;
  v18 = v16 - 3;
  if ( !v18 )
    goto LABEL_27;
  v19 = v18 - 2;
  if ( !v19 )
  {
    v28 = *(_QWORD *)ATL::CFileTime::GetTickCount(v45) - ((unsigned int)v15 | ((unsigned __int64)HIDWORD(v43) << 32));
    if ( v28 > 0x7FFFFFFF )
    {
      *a2 = 0;
      return 2;
    }
    v29 = 3 * *((_DWORD *)this + 58) - v28 / 0x989680uLL;
    *a2 = v29;
    if ( v29 <= 0 )
    {
      *a2 = 0;
      ProblemInstance::Cancel(this);
      goto LABEL_14;
    }
    return 3;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
    v24 = *(_QWORD *)ATL::CFileTime::GetTickCount(v45) - ((unsigned int)v15 | ((unsigned __int64)HIDWORD(v43) << 32));
    if ( v24 > 0x7FFFFFFF || (v25 = v17 - v24 / 0x989680uLL, *a2 = v25, v25 <= 0) )
    {
      *a2 = 0;
      goto LABEL_27;
    }
    return 3;
  }
  v21 = v20 - 1;
  if ( v21 )
  {
    v22 = v21 - 2;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( v23 )
      {
        if ( v23 == 2 )
          return 1;
        return 2;
      }
    }
  }
LABEL_27:
  *((_DWORD *)this + 58) = *(_DWORD *)(v14 + 36);
  if ( v8 )
  {
    *((_DWORD *)this + 24) = 5;
    TickCount = ATL::CFileTime::GetTickCount(v45);
    v27 = *TickCount;
    *((struct _FILETIME *)this + 23) = *TickCount;
  }
  else
  {
    *((_DWORD *)this + 25) = 5;
    v30 = ATL::CFileTime::GetTickCount(v45);
    v27 = *v30;
    *((struct _FILETIME *)this + 24) = *v30;
  }
  if ( *((_BYTE *)this + 220) )
    return 2;
  v31 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, unsigned int *))(**((_QWORD **)this + 9) + 72LL))(
          *((_QWORD *)this + 9),
          v14,
          a2,
          &v41);
  *((_DWORD *)this + 61) = v31;
  if ( v31 < 0 )
    v41 = v31 != -2147467263 ? 2 : 0;
  if ( *((_BYTE *)this + 220) )
    return 2;
  if ( *((_QWORD *)this + 36) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v43);
    v32 = *((_QWORD *)this + 2);
    if ( !*(_DWORD *)(v32 - 16) )
      v32 = *(_QWORD *)this;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      (__int64)&v43,
      (__int64)L"%s repair status %d HRESULT %X ",
      v32,
      v41,
      *((_DWORD *)this + 61));
    v33 = v43;
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 36) + 96LL))(*((_QWORD *)this + 36), 2, v43);
    ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
  }
  if ( v41 != 4 )
  {
LABEL_47:
    if ( v41 - 1 > 1 )
      goto LABEL_56;
    goto LABEL_48;
  }
  v41 = 1;
  v34 = *((_QWORD *)this + 36);
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v34 + 96LL))(
      v34,
      2,
      L"Treating RS_USER_ACTION as RS_REPAIRED.");
    goto LABEL_47;
  }
LABEL_48:
  if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 9) + 112LL))(*((_QWORD *)this + 9), &v42) >= 0 )
  {
    v35 = v42;
    if ( v41 == 1 )
    {
      *((struct _FILETIME *)this + 6) = v27;
    }
    else if ( v41 != 2 )
    {
LABEL_55:
      *((_QWORD *)this + 8) = v35;
      CProblemInstanceCache::Add(*((CProblemInstanceCache **)v44 + 6), (const FILETIME *)this);
      goto LABEL_56;
    }
    dwHighDateTime = HIDWORD(v42);
    dwLowDateTime = v35;
    if ( (v27.dwLowDateTime | ((unsigned __int64)v27.dwHighDateTime << 32)) >= ((unsigned int)v35
                                                                              | ((unsigned __int64)HIDWORD(v42) << 32)) )
    {
      dwHighDateTime = v27.dwHighDateTime;
      dwLowDateTime = v27.dwLowDateTime;
    }
    *((_DWORD *)this + 15) = dwHighDateTime;
    *((_DWORD *)this + 14) = dwLowDateTime;
    goto LABEL_55;
  }
LABEL_56:
  switch ( v41 )
  {
    case 0u:
      goto LABEL_65;
    case 1u:
      v38 = 12;
      goto LABEL_66;
    case 2u:
LABEL_65:
      v38 = 10;
      goto LABEL_66;
  }
  if ( v41 != 3 )
    return 0;
  if ( *a2 > 0 )
  {
    v9 = *ATL::CFileTime::GetTickCount(v45);
    v17 = *a2;
    v38 = 6;
  }
  else
  {
    v38 = 11;
    *a2 = 0;
    v41 = 2;
  }
LABEL_66:
  v39 = (*(_QWORD *)ATL::CFileTime::GetTickCount(v45)
       - (v27.dwLowDateTime | ((unsigned __int64)v27.dwHighDateTime << 32)))
      / 0x2710
      / 0x64;
  if ( v8 )
  {
    *((_DWORD *)this + 24) = v38;
    *((struct _FILETIME *)this + 23) = v9;
    *((_DWORD *)this + 50) = v17;
  }
  else
  {
    *((_DWORD *)this + 25) = v38;
    *((struct _FILETIME *)this + 24) = v9;
    *((_DWORD *)this + 51) = v17;
  }
  if ( v38 == 6 )
  {
    *((_DWORD *)this + 54) += v39 + 10 * v17;
  }
  else
  {
    v40 = *((_QWORD *)this + 42);
    *((_DWORD *)this + 54) = v39;
    if ( v40 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v40 + 64LL))(
        v40,
        *(_QWORD *)this,
        *((_QWORD *)this + 1),
        v41,
        v39);
  }
  return v41;
}

```

## disassembly

```asm
0x180013c3c  push    rbp
0x180013c3e  push    rbx
0x180013c3f  push    rsi
0x180013c40  push    rdi
0x180013c41  push    r12
0x180013c43  push    r13
0x180013c45  push    r14
0x180013c47  push    r15
0x180013c49  mov     rbp, rsp
0x180013c4c  sub     rsp, 68h
0x180013c50  mov     r14d, r9d
0x180013c53  mov     ebx, r8d
0x180013c56  mov     r15, rdx
0x180013c59  mov     rsi, rcx
0x180013c5c  xor     r13d, r13d
0x180013c5f  mov     [rbp+var_34], r13d
0x180013c63  mov     [rbp+var_30], r13
0x180013c67  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x180013c6c  mov     [rbp+var_20], rax
0x180013c70  test    rax, rax
0x180013c73  jz      loc_180013D2F
0x180013c79  cmp     [rsi+120h], r13
0x180013c80  jnz     short loc_180013C9B
0x180013c82  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x180013c87  test    rax, rax
0x180013c8a  jz      short loc_180013C9B
0x180013c8c  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x180013c91  mov     rcx, [rax]
0x180013c94  mov     [rsi+120h], rcx
0x180013c9b  lea     eax, [rbx-1]
0x180013c9e  test    eax, 0FFFFFFFCh
0x180013ca3  jnz     short loc_180013CBF
0x180013ca5  cmp     ebx, 3
0x180013ca8  jz      short loc_180013CBF
0x180013caa  mov     r12b, 1
0x180013cad  mov     rdi, [rsi+0B8h]
0x180013cb4  mov     edx, 0C8h
0x180013cb9  lea     r8d, [rdx-68h]
0x180013cbd  jmp     short loc_180013CD2
0x180013cbf  mov     r12b, r13b
0x180013cc2  mov     rdi, [rsi+0C0h]
0x180013cc9  mov     edx, 0CCh
0x180013cce  lea     r8d, [rdx-68h]
0x180013cd2  mov     [rbp+var_38], r12b
0x180013cd6  cmp     r14d, [rsi+68h]
0x180013cda  jb      short loc_180013D45
0x180013cdc  cmp     [rsi+120h], r13
0x180013ce3  jz      short loc_180013D2F
0x180013ce5  lea     rcx, [rbp+var_28]
0x180013ce9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013cee  nop
0x180013cef  mov     r9d, [rsi+68h]
0x180013cf3  mov     r8d, r14d
0x180013cf6  lea     rdx, aRepairFailedAs; "Repair Failed: Asked to perform repair "...
0x180013cfd  lea     rcx, [rbp+var_28]
0x180013d01  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180013d06  mov     rcx, [rsi+120h]
0x180013d0d  mov     rax, [rcx]
0x180013d10  mov     rbx, [rbp+var_28]
0x180013d14  mov     r8, rbx
0x180013d17  mov     edx, 2
0x180013d1c  mov     rax, [rax+60h]
0x180013d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d25  nop
0x180013d26  lea     rcx, [rbx-18h]; this
0x180013d2a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180013d2f  mov     eax, 2
0x180013d34  add     rsp, 68h
0x180013d38  pop     r15
0x180013d3a  pop     r14
0x180013d3c  pop     r13
0x180013d3e  pop     r12
0x180013d40  pop     rdi
0x180013d41  pop     rsi
0x180013d42  pop     rbx
0x180013d43  pop     rbp
0x180013d44  retn
0x180013d45  imul    rbx, r14, 70h ; 'p'
0x180013d49  add     rbx, [rsi+70h]
0x180013d4d  jnz     short loc_180013D61
0x180013d4f  test    r12b, r12b
0x180013d52  jz      loc_180013EB8
0x180013d58  mov     dword ptr [rsi+60h], 0Bh
0x180013d5f  jmp     short loc_180013D2F
0x180013d61  movzx   eax, r12b
0x180013d65  xor     rax, 1
0x180013d69  mov     r13, [rsi+rax*8+0B8h]
0x180013d71  mov     [rbp+var_28], r13
0x180013d75  mov     ecx, [r8+rsi]
0x180013d79  mov     r14d, [rdx+rsi]
0x180013d7d  mov     [rsi+0F8h], rbx
0x180013d84  sub     ecx, 3
0x180013d87  jz      loc_180013E15
0x180013d8d  sub     ecx, 2
0x180013d90  jz      loc_180013E46
0x180013d96  sub     ecx, 1
0x180013d99  jz      short loc_180013DBF
0x180013d9b  sub     ecx, 1
0x180013d9e  jz      short loc_180013E15
0x180013da0  sub     ecx, 2
0x180013da3  jz      short loc_180013E15
0x180013da5  sub     ecx, 1
0x180013da8  jz      short loc_180013E15
0x180013daa  sub     ecx, 1
0x180013dad  jz      short loc_180013D2F
0x180013daf  cmp     ecx, 1
0x180013db2  jnz     loc_180013D2F
0x180013db8  mov     eax, ecx
0x180013dba  jmp     loc_180013D34
0x180013dbf  lea     rcx, [rbp+var_18]
0x180013dc3  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x180013dc8  mov     edx, [rax+4]
0x180013dcb  shl     rdx, 20h
0x180013dcf  mov     eax, [rax]
0x180013dd1  or      rdx, rax
0x180013dd4  mov     ecx, dword ptr [rbp+var_28+4]
0x180013dd7  shl     rcx, 20h
0x180013ddb  mov     eax, r13d
0x180013dde  or      rcx, rax
0x180013de1  sub     rdx, rcx
0x180013de4  cmp     rdx, 7FFFFFFFh
0x180013deb  jg      short loc_180013E0E
0x180013ded  mov     rax, 0D6BF94D5E57A42BDh
0x180013df7  mul     rdx
0x180013dfa  shr     rdx, 17h
0x180013dfe  mov     eax, r14d
0x180013e01  sub     eax, edx
0x180013e03  mov     [r15], eax
0x180013e06  test    eax, eax
0x180013e08  jg      loc_180013EC4
0x180013e0e  mov     dword ptr [r15], 0
0x180013e15  mov     eax, [rbx+24h]
0x180013e18  mov     [rsi+0E8h], eax
0x180013e1e  lea     rcx, [rbp+var_18]
0x180013e22  test    r12b, r12b
0x180013e25  jz      loc_180013ECE
0x180013e2b  mov     dword ptr [rsi+60h], 5
0x180013e32  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x180013e37  mov     r13, [rax]
0x180013e3a  mov     [rsi+0B8h], r13
0x180013e41  jmp     loc_180013EE4
0x180013e46  lea     rcx, [rbp+var_18]
0x180013e4a  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x180013e4f  mov     r8d, [rax+4]
0x180013e53  shl     r8, 20h
0x180013e57  mov     ecx, [rax]
0x180013e59  or      r8, rcx
0x180013e5c  mov     edx, dword ptr [rbp+var_28+4]
0x180013e5f  shl     rdx, 20h
0x180013e63  mov     ecx, r13d
0x180013e66  or      rdx, rcx
0x180013e69  sub     r8, rdx
0x180013e6c  cmp     r8, 7FFFFFFFh
0x180013e73  jle     short loc_180013E81
0x180013e75  mov     dword ptr [r15], 0
0x180013e7c  jmp     loc_180013D2F
0x180013e81  mov     rax, 0D6BF94D5E57A42BDh
0x180013e8b  mul     r8
0x180013e8e  shr     rdx, 17h
0x180013e92  mov     eax, [rsi+0E8h]
0x180013e98  lea     ecx, [rax+rax*2]
0x180013e9b  sub     ecx, edx
0x180013e9d  mov     [r15], ecx
0x180013ea0  test    ecx, ecx
0x180013ea2  jg      short loc_180013EC4
0x180013ea4  mov     dword ptr [r15], 0
0x180013eab  mov     rcx, rsi; this
0x180013eae  call    ?Cancel@ProblemInstance@@QEAAXXZ; ProblemInstance::Cancel(void)
0x180013eb3  jmp     loc_180013D4F
0x180013eb8  mov     dword ptr [rsi+64h], 0Bh
0x180013ebf  jmp     loc_180013D2F
0x180013ec4  mov     eax, 3
0x180013ec9  jmp     loc_180013D34
0x180013ece  mov     dword ptr [rsi+64h], 5
0x180013ed5  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x180013eda  mov     r13, [rax]
0x180013edd  mov     [rsi+0C0h], r13
0x180013ee4  mov     r12, r13
0x180013ee7  shr     r12, 20h
0x180013eeb  cmp     byte ptr [rsi+0DCh], 0
0x180013ef2  jnz     loc_180013D2F
0x180013ef8  mov     rcx, [rsi+48h]
0x180013efc  mov     rax, [rcx]
0x180013eff  lea     r9, [rbp+var_34]
0x180013f03  mov     r8, r15
0x180013f06  mov     rdx, rbx
0x180013f09  mov     rax, [rax+48h]
0x180013f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f12  mov     [rsi+0F4h], eax
0x180013f18  test    eax, eax
0x180013f1a  jns     short loc_180013F2B
0x180013f1c  sub     eax, 80004001h
0x180013f21  neg     eax
0x180013f23  sbb     eax, eax
0x180013f25  and     eax, 2
0x180013f28  mov     [rbp+var_34], eax
0x180013f2b  cmp     byte ptr [rsi+0DCh], 0
0x180013f32  jnz     loc_180013D2F
0x180013f38  cmp     qword ptr [rsi+120h], 0
0x180013f40  jz      short loc_180013FA1
0x180013f42  lea     rcx, [rbp+var_28]
0x180013f46  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013f4b  nop
0x180013f4c  mov     eax, [rsi+0F4h]
0x180013f52  mov     r8, [rsi+10h]
0x180013f56  cmp     dword ptr [r8-10h], 0
0x180013f5b  jnz     short loc_180013F60
0x180013f5d  mov     r8, [rsi]
0x180013f60  mov     [rsp+68h+var_48], eax
0x180013f64  mov     r9d, [rbp+var_34]
0x180013f68  lea     rdx, aSRepairStatusD; "%s repair status %d HRESULT %X "
0x180013f6f  lea     rcx, [rbp+var_28]
0x180013f73  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180013f78  mov     rcx, [rsi+120h]
0x180013f7f  mov     rax, [rcx]
0x180013f82  mov     rbx, [rbp+var_28]
0x180013f86  mov     r8, rbx
0x180013f89  mov     edx, 2
0x180013f8e  mov     rax, [rax+60h]
0x180013f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f97  nop
0x180013f98  lea     rcx, [rbx-18h]; this
0x180013f9c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180013fa1  cmp     [rbp+var_34], 4
0x180013fa5  jnz     short loc_180013FD2
0x180013fa7  mov     [rbp+var_34], 1
0x180013fae  mov     rcx, [rsi+120h]
0x180013fb5  test    rcx, rcx
0x180013fb8  jz      short loc_180013FDC
0x180013fba  mov     rax, [rcx]
0x180013fbd  lea     r8, aTreatingRsUser; "Treating RS_USER_ACTION as RS_REPAIRED."
0x180013fc4  mov     edx, 2
0x180013fc9  mov     rax, [rax+60h]
0x180013fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fd2  mov     eax, [rbp+var_34]
0x180013fd5  dec     eax
0x180013fd7  cmp     eax, 1
0x180013fda  ja      short loc_180014053
0x180013fdc  mov     rcx, [rsi+48h]
0x180013fe0  mov     rax, [rcx]
0x180013fe3  lea     rdx, [rbp+var_30]
0x180013fe7  mov     rax, [rax+70h]
0x180013feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ff0  test    eax, eax
0x180013ff2  js      short loc_180014053
0x180013ff4  mov     rax, [rbp+var_30]
0x180013ff8  cmp     [rbp+var_34], 1
0x180013ffc  jnz     short loc_180014008
0x180013ffe  mov     [rsi+30h], r13d
0x180014002  mov     [rsi+34h], r12d
0x180014006  jmp     short loc_18001400E
0x180014008  cmp     [rbp+var_34], 2
0x18001400c  jnz     short loc_18001403F
0x18001400e  mov     r8d, r12d
0x180014011  mov     ecx, r13d
0x180014014  shl     r8, 20h
0x180014018  mov     r9d, dword ptr [rbp+var_30+4]
0x18001401c  or      r8, rcx
0x18001401f  mov     edx, r9d
0x180014022  mov     ecx, eax
0x180014024  shl     rdx, 20h
0x180014028  or      rdx, rcx
0x18001402b  cmp     r8, rdx
0x18001402e  mov     ecx, eax
0x180014030  cmovnb  r9d, r12d
0x180014034  cmovnb  ecx, r13d
0x180014038  mov     [rsi+3Ch], r9d
0x18001403c  mov     [rsi+38h], ecx
0x18001403f  mov     [rsi+40h], rax
0x180014043  mov     rdx, rsi; struct ProblemInstance *
0x180014046  mov     rcx, [rbp+var_20]
0x18001404a  mov     rcx, [rcx+30h]; this
0x18001404e  call    ?Add@CProblemInstanceCache@@QEAA_NPEAVProblemInstance@@@Z; CProblemInstanceCache::Add(ProblemInstance *)
0x180014053  mov     ecx, [rbp+var_34]
0x180014056  test    ecx, ecx
0x180014058  jz      short loc_1800140A8
0x18001405a  sub     ecx, 1
0x18001405d  jz      short loc_1800140A1
0x18001405f  sub     ecx, 1
0x180014062  jz      short loc_1800140A8
0x180014064  cmp     ecx, 1
0x180014067  jz      short loc_180014070
0x180014069  xor     eax, eax
0x18001406b  jmp     loc_180013D34
0x180014070  cmp     dword ptr [r15], 0
0x180014074  jg      short loc_18001408B
0x180014076  mov     ebx, 0Bh
0x18001407b  mov     dword ptr [r15], 0
0x180014082  mov     [rbp+var_34], 2
0x180014089  jmp     short loc_1800140AD
0x18001408b  lea     rcx, [rbp+var_18]
0x18001408f  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x180014094  mov     rdi, [rax]
0x180014097  mov     r14d, [r15]
0x18001409a  mov     ebx, 6
0x18001409f  jmp     short loc_1800140AD
0x1800140a1  mov     ebx, 0Ch
0x1800140a6  jmp     short loc_1800140AD
0x1800140a8  mov     ebx, 0Ah
0x1800140ad  lea     rcx, [rbp+var_18]
  ... truncated ...
```

# CParameters::Append(IDispatch *)

- ea: `0x18003d360`
- end: `0x18003d9ba`
- name: `?Append@CParameters@@UEAAJPEAUIDispatch@@@Z`
- size: `1626`
- prototype: `__int64 __fastcall(CParameters *__hidden this, struct IDispatch *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180079370`

## callees

- `0x180020fc0`
- `0x18003d360`
- `0x180042a04`
- `0x18006a22c`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x18003d4b2`
- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x18003d4b2`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x18003d4f2`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x18003d4f2`
- `KERNEL32!TlsSetValue` at `0x18003d3df`
- `KERNEL32!TlsSetValue` at `0x18003d59c`
- `KERNEL32!TlsSetValue` at `0x18003d3df`
- `KERNEL32!TlsSetValue` at `0x18003d59c`
- `KERNEL32!TlsGetValue` at `0x18003d39b`
- `KERNEL32!TlsGetValue` at `0x18003d39b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003d5d3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003d5d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CParameters::Append(CParameters *this, struct IDispatch *a2)
{
  _QWORD *v4; // r14
  char *v5; // r8
  _DWORD *Value; // rax
  int v7; // edi
  _QWORD *v8; // rcx
  _QWORD *v9; // rbx
  __int64 v10; // rsi
  bool v11; // r10
  __int64 v12; // r9
  unsigned int i; // ecx
  __int64 v14; // rdx
  unsigned int v15; // ebx
  _DWORD *v17; // rax
  IErrorInfo *v18; // rdx
  unsigned int v20; // eax
  unsigned int BidObjectID; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // ebx
  unsigned int v27; // eax
  __int64 v28; // [rsp+20h] [rbp-50h]
  __int64 v29; // [rsp+30h] [rbp-40h] BYREF
  _DWORD *TlsValue; // [rsp+38h] [rbp-38h] BYREF
  int v31; // [rsp+40h] [rbp-30h]
  __int64 v32; // [rsp+48h] [rbp-28h]
  int v33; // [rsp+50h] [rbp-20h]
  __int16 v34; // [rsp+54h] [rbp-1Ch]
  char v35; // [rsp+56h] [rbp-1Ah]
  char *v36; // [rsp+58h] [rbp-18h]
  int v37; // [rsp+60h] [rbp-10h]
  int v38; // [rsp+64h] [rbp-Ch]
  int v39; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v40; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v41; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v42; // [rsp+C8h] [rbp+58h] BYREF

  v4 = (_QWORD *)((char *)this + 24);
  v5 = (char *)this + 24;
  if ( !this )
    v5 = 0;
  v36 = v5;
  v38 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v37 = 0;
  v7 = 1;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v31 = 1;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v42 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AA58[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
    bidScopeEnterW(&v42, off_18012AA58[0], BidObjectID, a2, v28);
  }
  v29 = 0;
  v41 = 0;
  v8 = (_QWORD *)v4[4];
  if ( v4 == v8 )
    v8 = 0;
  v9 = v8 - 4;
  if ( !v8 )
    v9 = 0;
  v40 = 0;
  if ( a2 || (v39 = -2146824868, !(unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, &v39)) )
  {
    if ( v9 && *((_BYTE *)v9 + 544) == 1 )
    {
      v39 = -2146824577;
      CContext::FailedPushWarning((CContext *)&TlsValue, &v39);
      goto LABEL_32;
    }
    if ( ((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IADOParameter,
           &v29) < 0
      && (v39 = -2146825287, (unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, &v39)) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) == -1 )
        {
          bidTraceW(off_18012A1D0[0], 3733513, L"<CParameters::Append|ADO|ERR>  line %d\n", 3646);
        }
        else
        {
          v20 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
          LODWORD(v28) = 3646;
          bidTraceW(off_18012A1D0[0], 3733513, L"<CParameters::Append|ADO|ERR> %u#, line %d\n", v20, v28);
        }
      }
    }
    else if ( ((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                a2,
                &IID_IADOClass,
                &v41) < 0
           && (v39 = -2146825287, (unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, &v39)) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) == -1 )
        {
          bidTraceW(off_18012A1D0[0], 3736585, L"<CParameters::Append|ADO|ERR>  line %d\n", 3649);
        }
        else
        {
          v23 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
          LODWORD(v28) = 3649;
          bidTraceW(off_18012A1D0[0], 3736585, L"<CParameters::Append|ADO|ERR> %u#, line %d\n", v23, v28);
        }
      }
    }
    else
    {
      v37 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 24LL))(v41, &v40);
      if ( v37 < 0 )
      {
        CContext::PushError((CContext *)&TlsValue);
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) == -1 )
          {
            bidTraceW(off_18012A1D0[0], 3738633, L"<CParameters::Append|ADO|ERR>  line %d\n", 3651);
          }
          else
          {
            v24 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
            LODWORD(v28) = 3651;
            bidTraceW(off_18012A1D0[0], 3738633, L"<CParameters::Append|ADO|ERR> %u#, line %d\n", v24, v28);
          }
        }
      }
      else
      {
        if ( v40 )
          v10 = v40 + 24;
        else
          v10 = 0;
        v11 = CReaderWriterLock3AR::ReadOrWriteLock((CParameters *)((char *)this + 96));
        v12 = *((_QWORD *)this + 11);
        if ( v12 )
        {
          for ( i = 0; i < *(_DWORD *)(v12 + 16); ++i )
          {
            if ( *(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL * i) == v10 )
            {
              v7 = 0;
              break;
            }
          }
        }
        CReaderWriterLock3AR::ReadOrWriteUnlock((CParameters *)((char *)this + 96), v11);
        if ( v7 == 1 || (v39 = -2146824921, !(unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, &v39)) )
        {
          if ( v40 )
            v14 = v40 + 24;
          else
            v14 = 0;
          v37 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v4 + 264LL))(v4, v14);
          if ( v37 < 0 )
            CContext::PushError((CContext *)&TlsValue);
        }
        else if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) == -1 )
          {
            bidTraceW(off_18012A1D0[0], 3742729, L"<CParameters::Append|ADO|ERR>  line %d\n", 3655);
          }
          else
          {
            v25 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
            LODWORD(v28) = 3655;
            bidTraceW(off_18012A1D0[0], 3742729, L"<CParameters::Append|ADO|ERR> %u#, line %d\n", v25, v28);
          }
        }
      }
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) == -1 )
    {
      bidTraceW(off_18012A1D0[0], 3727369, L"<CParameters::Append|ADO|ERR>  line %d\n", 3640);
    }
    else
    {
      v22 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
      LODWORD(v28) = 3640;
      bidTraceW(off_18012A1D0[0], 3727369, L"<CParameters::Append|ADO|ERR> %u#, line %d\n", v22, v28);
    }
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
LABEL_32:
  if ( (bidGblFlags & 2) != 0 && off_18012A460[0] )
  {
    v26 = v37;
    v27 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
    LODWORD(v28) = v26;
    bidTraceW(off_18012A1D0[0], 3758080, off_18012A460[0], v27, v28);
  }
  if ( (bidGblFlags & 4) != 0 && v42 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v42);
  v15 = v37;
  if ( TlsValue[2]-- == 1 )
  {
    v17 = TlsValue;
    v18 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v18 )
    {
      SetErrorInfo(0, v18);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v17 = TlsValue;
    }
    if ( *((_BYTE *)v17 + 30) )
    {
      *((_QWORD *)v17 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v15;
}

```

## disassembly

```asm
0x18003d360  push    rbp
0x18003d362  push    rbx
0x18003d363  push    rsi
0x18003d364  push    rdi
0x18003d365  push    r12
0x18003d367  push    r14
0x18003d369  push    r15
0x18003d36b  mov     rbp, rsp
0x18003d36e  sub     rsp, 70h
0x18003d372  mov     rsi, rdx
0x18003d375  mov     r15, rcx
0x18003d378  lea     r14, [rcx+18h]
0x18003d37c  mov     r8, r14
0x18003d37f  xor     r12d, r12d
0x18003d382  test    rcx, rcx
0x18003d385  cmovz   r8, r12
0x18003d389  mov     [rbp+var_18], r8
0x18003d38d  mov     [rbp+var_C], r12d
0x18003d391  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18003d398  mov     ecx, [rcx+14h]; dwTlsIndex
0x18003d39b  call    cs:__imp_TlsGetValue
0x18003d3a2  nop     dword ptr [rax+rax+00h]
0x18003d3a7  mov     [rbp+TlsValue], rax
0x18003d3ab  mov     [rbp+var_10], r12d
0x18003d3af  mov     edi, 1
0x18003d3b4  test    rax, rax
0x18003d3b7  jnz     loc_18003D5BB
0x18003d3bd  mov     [rbp+var_30], edi
0x18003d3c0  mov     [rbp+var_28], r12
0x18003d3c4  mov     [rbp+var_20], r12d
0x18003d3c8  mov     [rbp+var_1C], r12w
0x18003d3cd  mov     [rbp+var_1A], r12b
0x18003d3d1  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x18003d3d5  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18003d3dc  mov     ecx, [rcx+14h]; dwTlsIndex
0x18003d3df  call    cs:__imp_TlsSetValue
0x18003d3e6  nop     dword ptr [rax+rax+00h]
0x18003d3eb  lea     rax, [rbp+TlsValue]
0x18003d3ef  mov     [rbp+TlsValue], rax
0x18003d3f3  mov     [rbp+arg_18], 0FFFFFFFFFFFFFFFFh
0x18003d3fb  test    byte ptr cs:_bidGblFlags, 4
0x18003d402  jnz     loc_18003D649
0x18003d408  mov     [rbp+var_40], r12
0x18003d40c  mov     [rbp+arg_10], r12
0x18003d410  mov     rcx, [r14+20h]
0x18003d414  cmp     r14, rcx
0x18003d417  cmovz   rcx, r12
0x18003d41b  lea     rbx, [rcx-20h]
0x18003d41f  test    rcx, rcx
0x18003d422  cmovz   rbx, r12
0x18003d426  mov     [rbp+arg_8], r12
0x18003d42a  test    rsi, rsi
0x18003d42d  jz      loc_18003D67D
0x18003d433  test    rbx, rbx
0x18003d436  jnz     loc_18003D708
0x18003d43c  mov     rax, [rsi]
0x18003d43f  lea     r8, [rbp+var_40]
0x18003d443  lea     rdx, IID_IADOParameter
0x18003d44a  mov     rcx, rsi
0x18003d44d  mov     rax, [rax]
0x18003d450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d455  test    eax, eax
0x18003d457  js      loc_18003D72E
0x18003d45d  mov     rax, [rsi]
0x18003d460  lea     r8, [rbp+arg_10]
0x18003d464  lea     rdx, IID_IADOClass
0x18003d46b  mov     rcx, rsi
0x18003d46e  mov     rax, [rax]
0x18003d471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d476  test    eax, eax
0x18003d478  js      loc_18003D772
0x18003d47e  mov     rcx, [rbp+arg_10]
0x18003d482  mov     rax, [rcx]
0x18003d485  lea     rdx, [rbp+arg_8]
0x18003d489  mov     rax, [rax+18h]
0x18003d48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d492  mov     [rbp+var_10], eax
0x18003d495  test    eax, eax
0x18003d497  js      loc_18003D7FD
0x18003d49d  mov     rax, [rbp+arg_8]
0x18003d4a1  test    rax, rax
0x18003d4a4  jz      loc_18003D875
0x18003d4aa  lea     rsi, [rax+18h]
0x18003d4ae  lea     rcx, [r15+60h]
0x18003d4b2  call    cs:__imp_?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ; CReaderWriterLock3AR::ReadOrWriteLock(void)
0x18003d4b9  nop     dword ptr [rax+rax+00h]
0x18003d4be  movzx   r10d, al
0x18003d4c2  mov     r9, [r15+58h]
0x18003d4c6  test    r9, r9
0x18003d4c9  jz      short loc_18003D4EA
0x18003d4cb  mov     ecx, r12d
0x18003d4ce  mov     r8d, [r9+10h]
0x18003d4d2  cmp     ecx, r8d
0x18003d4d5  jnb     short loc_18003D4EA
0x18003d4d7  mov     edx, ecx
0x18003d4d9  mov     rax, [r9+8]
0x18003d4dd  cmp     [rax+rdx*8], rsi
0x18003d4e1  jz      short loc_18003D4E7
0x18003d4e3  inc     ecx
0x18003d4e5  jmp     short loc_18003D4D2
0x18003d4e7  mov     edi, r12d
0x18003d4ea  movzx   edx, r10b
0x18003d4ee  lea     rcx, [r15+60h]
0x18003d4f2  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z; CReaderWriterLock3AR::ReadOrWriteUnlock(bool)
0x18003d4f9  nop     dword ptr [rax+rax+00h]
0x18003d4fe  cmp     edi, 1
0x18003d501  jnz     loc_18003D87D
0x18003d507  mov     rax, [r14]
0x18003d50a  mov     r8, [rax+108h]
0x18003d511  mov     rax, [rbp+arg_8]
0x18003d515  test    rax, rax
0x18003d518  jz      loc_18003D908
0x18003d51e  lea     rdx, [rax+18h]
0x18003d522  mov     rcx, r14
0x18003d525  mov     rax, r8
0x18003d528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d52d  mov     [rbp+var_10], eax
0x18003d530  test    eax, eax
0x18003d532  js      loc_18003D5C3
0x18003d538  mov     rcx, [rbp+var_40]
0x18003d53c  test    rcx, rcx
0x18003d53f  jnz     loc_18003D910
0x18003d545  mov     rcx, [rbp+arg_10]
0x18003d549  test    rcx, rcx
0x18003d54c  jnz     loc_18003D921
0x18003d552  test    byte ptr cs:_bidGblFlags, 2
0x18003d559  jnz     loc_18003D932
0x18003d55f  test    byte ptr cs:_bidGblFlags, 4
0x18003d566  jnz     loc_18003D972
0x18003d56c  mov     ebx, [rbp+var_10]
0x18003d56f  mov     rax, [rbp+TlsValue]
0x18003d573  add     dword ptr [rax+8], 0FFFFFFFFh
0x18003d577  jnz     short loc_18003D5A9
0x18003d579  mov     rax, [rbp+TlsValue]
0x18003d57d  mov     rdx, [rax+10h]; perrinfo
0x18003d581  test    rdx, rdx
0x18003d584  jnz     short loc_18003D5D1
0x18003d586  cmp     byte ptr [rax+1Eh], 0
0x18003d58a  jnz     loc_18003D9A8
0x18003d590  xor     edx, edx; lpTlsValue
0x18003d592  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18003d599  mov     ecx, [rcx+14h]; dwTlsIndex
0x18003d59c  call    cs:__imp_TlsSetValue
0x18003d5a3  nop     dword ptr [rax+rax+00h]
0x18003d5a8  nop
0x18003d5a9  mov     eax, ebx
0x18003d5ab  add     rsp, 70h
0x18003d5af  pop     r15
0x18003d5b1  pop     r14
0x18003d5b3  pop     r12
0x18003d5b5  pop     rdi
0x18003d5b6  pop     rsi
0x18003d5b7  pop     rbx
0x18003d5b8  pop     rbp
0x18003d5b9  retn
0x18003d5bb  inc     dword ptr [rax+8]
0x18003d5be  jmp     loc_18003D3F3
0x18003d5c3  lea     rcx, [rbp+TlsValue]; this
0x18003d5c7  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18003d5cc  jmp     loc_18003D538
0x18003d5d1  xor     ecx, ecx; dwReserved
0x18003d5d3  call    cs:__imp_SetErrorInfo
0x18003d5da  nop     dword ptr [rax+rax+00h]
0x18003d5df  mov     rax, [rbp+TlsValue]
0x18003d5e3  mov     rcx, [rax+10h]
0x18003d5e7  mov     rax, [rcx]
0x18003d5ea  mov     rax, [rax+10h]
0x18003d5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5f3  mov     rax, [rbp+TlsValue]
0x18003d5f7  jmp     short loc_18003D586
0x18003d5f9  test    byte ptr cs:_bidGblFlags, 2
0x18003d600  jz      loc_18003D538
0x18003d606  lea     rcx, [r15+70h]; this
0x18003d60a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18003d60f  cmp     eax, 0FFFFFFFFh
0x18003d612  jz      loc_18003D74F
0x18003d618  lea     rcx, [r15+70h]; this
0x18003d61c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18003d621  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18003d628  mov     [rsp+70h+var_50], 0E3Eh
0x18003d630  mov     r9d, eax
0x18003d633  lea     r8, aCparametersApp_3; "<CParameters::Append|ADO|ERR> %u#, line"...
0x18003d63a  mov     edx, 38F809h
0x18003d63f  call    _bidTraceW
0x18003d644  jmp     loc_18003D538
0x18003d649  mov     rax, cs:off_18012AA58; "<CParameters::Append|API|ADO> %u#, lpdi"...
0x18003d650  test    rax, rax
0x18003d653  jz      loc_18003D408
0x18003d659  lea     rcx, [r15+70h]; this
0x18003d65d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18003d662  mov     rdx, cs:off_18012AA58; "<CParameters::Append|API|ADO> %u#, lpdi"...
0x18003d669  mov     r9, rsi
0x18003d66c  mov     r8d, eax
0x18003d66f  lea     rcx, [rbp+arg_18]
0x18003d673  call    _bidScopeEnterW
0x18003d678  jmp     loc_18003D408
0x18003d67d  mov     [rbp+arg_0], 800A0D5Ch
0x18003d684  lea     rdx, [rbp+arg_0]; int *
0x18003d688  lea     rcx, [rbp+TlsValue]; this
0x18003d68c  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18003d691  test    eax, eax
0x18003d693  jz      loc_18003D433
0x18003d699  test    byte ptr cs:_bidGblFlags, 2
0x18003d6a0  jz      loc_18003D538
0x18003d6a6  lea     rcx, [r15+70h]; this
0x18003d6aa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18003d6af  cmp     eax, 0FFFFFFFFh
0x18003d6b2  jz      short loc_18003D6E5
0x18003d6b4  lea     rcx, [r15+70h]; this
0x18003d6b8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18003d6bd  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18003d6c4  mov     [rsp+70h+var_50], 0E38h
0x18003d6cc  mov     r9d, eax
0x18003d6cf  lea     r8, aCparametersApp_3; "<CParameters::Append|ADO|ERR> %u#, line"...
0x18003d6d6  mov     edx, 38E009h
0x18003d6db  call    _bidTraceW
0x18003d6e0  jmp     loc_18003D538
0x18003d6e5  mov     r9d, 0E38h
0x18003d6eb  lea     r8, aCparametersApp_0; "<CParameters::Append|ADO|ERR>  line %d"...
0x18003d6f2  mov     edx, 38E009h
0x18003d6f7  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18003d6fe  call    _bidTraceW
0x18003d703  jmp     loc_18003D538
0x18003d708  cmp     [rbx+220h], dil
0x18003d70f  jnz     loc_18003D43C
0x18003d715  mov     [rbp+arg_0], 800A0E7Fh
0x18003d71c  lea     rdx, [rbp+arg_0]; int *
0x18003d720  lea     rcx, [rbp+TlsValue]; this
0x18003d724  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18003d729  jmp     loc_18003D552
0x18003d72e  mov     [rbp+arg_0], 800A0BB9h
0x18003d735  lea     rdx, [rbp+arg_0]; int *
0x18003d739  lea     rcx, [rbp+TlsValue]; this
0x18003d73d  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18003d742  test    eax, eax
0x18003d744  jz      loc_18003D45D
0x18003d74a  jmp     loc_18003D5F9
0x18003d74f  mov     r9d, 0E3Eh
0x18003d755  lea     r8, aCparametersApp_0; "<CParameters::Append|ADO|ERR>  line %d"...
0x18003d75c  mov     edx, 38F809h
0x18003d761  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18003d768  call    _bidTraceW
0x18003d76d  jmp     loc_18003D538
0x18003d772  mov     [rbp+arg_0], 800A0BB9h
0x18003d779  lea     rdx, [rbp+arg_0]; int *
0x18003d77d  lea     rcx, [rbp+TlsValue]; this
0x18003d781  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18003d786  test    eax, eax
0x18003d788  jz      loc_18003D47E
0x18003d78e  test    byte ptr cs:_bidGblFlags, 2
0x18003d795  jz      loc_18003D538
0x18003d79b  lea     rcx, [r15+70h]; this
0x18003d79f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18003d7a4  cmp     eax, 0FFFFFFFFh
0x18003d7a7  jz      short loc_18003D7DA
0x18003d7a9  lea     rcx, [r15+70h]; this
0x18003d7ad  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18003d7b2  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18003d7b9  mov     [rsp+70h+var_50], 0E41h
0x18003d7c1  mov     r9d, eax
0x18003d7c4  lea     r8, aCparametersApp_3; "<CParameters::Append|ADO|ERR> %u#, line"...
0x18003d7cb  mov     edx, 390409h
0x18003d7d0  call    _bidTraceW
0x18003d7d5  jmp     loc_18003D538
0x18003d7da  mov     r9d, 0E41h
0x18003d7e0  lea     r8, aCparametersApp_0; "<CParameters::Append|ADO|ERR>  line %d"...
0x18003d7e7  mov     edx, 390409h
0x18003d7ec  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18003d7f3  call    _bidTraceW
0x18003d7f8  jmp     loc_18003D538
0x18003d7fd  lea     rcx, [rbp+TlsValue]; this
0x18003d801  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18003d806  test    byte ptr cs:_bidGblFlags, 2
0x18003d80d  jz      loc_18003D538
0x18003d813  lea     rcx, [r15+70h]; this
0x18003d817  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18003d81c  cmp     eax, 0FFFFFFFFh
0x18003d81f  jz      short loc_18003D852
0x18003d821  lea     rcx, [r15+70h]; this
0x18003d825  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18003d82a  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18003d831  mov     [rsp+70h+var_50], 0E43h
0x18003d839  mov     r9d, eax
0x18003d83c  lea     r8, aCparametersApp_3; "<CParameters::Append|ADO|ERR> %u#, line"...
0x18003d843  mov     edx, 390C09h
0x18003d848  call    _bidTraceW
0x18003d84d  jmp     loc_18003D538
0x18003d852  mov     r9d, 0E43h
0x18003d858  lea     r8, aCparametersApp_0; "<CParameters::Append|ADO|ERR>  line %d"...
0x18003d85f  mov     edx, 390C09h
0x18003d864  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18003d86b  call    _bidTraceW
0x18003d870  jmp     loc_18003D538
0x18003d875  mov     rsi, r12
0x18003d878  jmp     loc_18003D4AE
0x18003d87d  mov     [rbp+arg_0], 800A0D27h
0x18003d884  lea     rdx, [rbp+arg_0]; int *
0x18003d888  lea     rcx, [rbp+TlsValue]; this
0x18003d88c  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18003d891  test    eax, eax
  ... truncated ...
```

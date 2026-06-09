# CVortexReader::SubmitRead(ulong,ulong)

- ea: `0x1800590e0`
- end: `0x18005984c`
- name: `?SubmitRead@CVortexReader@@MEAAXKK@Z`
- size: `1900`
- prototype: `void __fastcall(CVortexReader *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008b70`
- `0x18000db20`
- `0x18000f5f0`
- `0x1800590e0`
- `0x1800670e0`
- `0x180084138`
- `0x180086a84`
- `0x18009c97c`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800a7558`
- `0x1800acacc`
- `0x1800ddbe4`
- `0x1800f9948`
- `0x1800f996c`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005941a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005941a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180059539`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180059602`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180059539`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180059602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800594c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800597fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800594c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800597fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800595d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005962c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800595d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005962c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800594bd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800594bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CVortexReader::SubmitRead(CVortexReader *this, int a2, unsigned int a3)
{
  unsigned __int64 v3; // r14
  int v6; // eax
  unsigned int v7; // r12d
  char *v8; // rdx
  __int64 v9; // rsi
  char *v10; // r15
  size_t v11; // rdi
  __int64 v12; // r8
  char *v13; // rax
  unsigned int v14; // edi
  __int64 v15; // rdi
  _DWORD *v16; // rax
  signed int LastError; // eax
  void *v18; // rcx
  void *v19; // rcx
  void **v20; // rcx
  unsigned int v21; // edx
  unsigned __int64 v22; // rdi
  unsigned int v23; // edi
  unsigned __int64 v24; // r12
  signed int v25; // eax
  bool v26; // sf
  void **pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  void *v28[2]; // [rsp+68h] [rbp-98h]
  void *v29; // [rsp+78h] [rbp-88h]
  void *v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  void *v32; // [rsp+90h] [rbp-70h]
  void **v33; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v34; // [rsp+C8h] [rbp-38h]
  int v35; // [rsp+D8h] [rbp-28h]
  int v36; // [rsp+DCh] [rbp-24h]
  int v37; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v38; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v39; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int64 v40; // [rsp+188h] [rbp+88h] BYREF

  v3 = a3;
  if ( *((_DWORD *)this + 158) != a2
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, this, a2);
  }
  *((_DWORD *)this + 158) = a2;
  *((_BYTE *)this + 56) = 0;
  *((_DWORD *)this + 65761) = -1091646260;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids,
      (unsigned int)v3);
  v6 = v3;
  v7 = 0x40000;
  if ( (unsigned int)v3 >= 0x40000 )
    v6 = 0x40000;
  *((_DWORD *)this + 51) = v6;
  v8 = (char *)*((_QWORD *)this + 32882);
  v9 = -897LL - (_QWORD)this;
  v10 = &v8[-897LL - (_QWORD)this];
  v11 = *((_QWORD *)this + 32881) - (_QWORD)v8;
  memmove_0((char *)this + 897, v8, v11);
  v13 = (char *)this + v11 + 897;
  *((_QWORD *)this + 32881) = v13;
  *((_QWORD *)this + 32882) = v13;
  if ( !v11 )
  {
    if ( v10 )
      goto LABEL_21;
    goto LABEL_16;
  }
  if ( !v10 )
  {
LABEL_16:
    if ( *((_BYTE *)this + 263097) )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids);
      *(_OWORD *)v28 = 0;
      pExceptionObject = &ComError::`vftable';
      v29 = (void *)0x3D78020001BLL;
      LODWORD(v30) = 1;
      throw (ComError *)&pExceptionObject;
    }
    goto LABEL_21;
  }
  if ( *((_DWORD *)this + 32) == 2 || v11 >= *((unsigned int *)this + 51) )
  {
    LOBYTE(v12) = 1;
    (*(void (__fastcall **)(CVortexReader *, _QWORD, __int64))(*(_QWORD *)this + 536LL))(this, 0, v12);
    (*(void (__fastcall **)(CVortexReader *))(*(_QWORD *)this + 584LL))(this);
    return;
  }
LABEL_21:
  if ( *((_QWORD *)this + 32920) && !CVortexReader::IsForceOrigin(this) )
  {
    v40 = 0;
    v38 = 0;
    v39 = 0;
    if ( v3 - v11 < 0x40000 )
      v7 = v3 - v11;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids, v7);
    CNestedImpersonation::CNestedImpersonation(
      (CNestedImpersonation *)&pExceptionObject,
      (CVortexReader *)((char *)this + 263304));
    PeerNetworkMonitor::TakeSnapshot((char *)this + 263424, 2);
    CHttpReader::IncrementPendingAsyncOpsCount(this);
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, _QWORD, int, unsigned int *, unsigned __int64 *, unsigned __int64 *, void (__fastcall *)(void *, unsigned int, unsigned int, unsigned __int64, unsigned __int64), CVortexReader *))(**((_QWORD **)this + 32917) + 56LL))(
            *((_QWORD *)this + 32917),
            *((_QWORD *)this + 32920),
            (char *)this + 897,
            v7,
            10000,
            &v39,
            &v40,
            &v38,
            CVortexReader::StaticOnP2pReadCompleted,
            this);
    CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&pExceptionObject);
    if ( v14 != 997 )
      CVortexReader::OnP2pReadCompleted(this, v14, v39, v40, v38);
    return;
  }
  v15 = *((_QWORD *)this + 32918);
  if ( !v15 )
    goto LABEL_85;
  CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&pExceptionObject);
  LOBYTE(v28[0]) = 0;
  v28[1] = *((void **)this + 32913);
  _InterlockedIncrement((volatile signed __int32 *)v28[1] + 2);
  v29 = 0;
  v16 = HeapAlloc(hBitsHeap, 8u, 4u);
  if ( !v16 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
    v34 = 0;
    v33 = &ComError::`vftable';
    v35 = -2147024882;
    v36 = 0;
    v37 = 1;
    throw (ComError *)&v33;
  }
  *v16 = 1;
  v30 = v16;
  v31 = 0;
  _InterlockedIncrement(&dword_180145058);
  v32 = &GenericStringHandle<unsigned short>::s_EmptyString;
  if ( !LOBYTE(v28[0]) )
  {
    if ( !ImpersonateLoggedOnUser(*(HANDLE *)v28[1]) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v34 = 0;
      v33 = &ComError::`vftable';
      v35 = LastError;
      v36 = 0;
      v37 = 1;
      throw (ComError *)&v33;
    }
    LOBYTE(v28[0]) = 1;
  }
  v39 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 32917) + 40LL))(
          *((_QWORD *)this + 32917),
          v15);
  if ( LOBYTE(v28[0]) )
  {
    SetThreadToken(0, *pExceptionObject);
    LOBYTE(v28[0]) = 0;
  }
  v18 = v32;
  if ( v32 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v32 + 2, 0xFFFFFFFF) == 1 )
      operator delete(v32, 0x10u);
    v32 = 0;
  }
  if ( v31 )
    std::default_delete<AppPackageInfo>::operator()(v18, v31);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v30, 0xFFFFFFFF) == 1 )
  {
    operator delete(v30, 4u);
    operator delete(v29, 0);
    v30 = 0;
    v29 = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28[1] + 2, 0xFFFFFFFF) == 1 )
  {
    v19 = v28[1];
    if ( (unsigned __int64)(*(_QWORD *)v28[1] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v28[1]);
      *(_QWORD *)v28[1] = 0;
      v19 = v28[1];
    }
    operator delete(v19, 0x10u);
    v28[1] = 0;
  }
  SetThreadToken(0, *pExceptionObject);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)pExceptionObject + 2, 0xFFFFFFFF) == 1 )
  {
    v20 = pExceptionObject;
    if ( (char *)*pExceptionObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(*pExceptionObject);
      *pExceptionObject = 0;
      v20 = pExceptionObject;
    }
    operator delete(v20, 0x10u);
  }
  if ( v39 )
  {
    if ( *((_QWORD *)this + 32919) )
    {
      v21 = v3;
LABEL_63:
      CHttpReader::InitiateRead(this, v21);
      return;
    }
    v40 = 0;
    v38 = 0;
    v39 = 0;
    v22 = v3 - v9 - *((_QWORD *)this + 32882);
    if ( v22 >= 0x40000 )
      LODWORD(v22) = 0x40000;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids,
        (unsigned int)v22);
    PeerNetworkMonitor::TakeSnapshot((char *)this + 263424, 2);
    CNestedImpersonation::CNestedImpersonation(
      (CNestedImpersonation *)&pExceptionObject,
      (CVortexReader *)((char *)this + 263304));
    CHttpReader::IncrementPendingAsyncOpsCount(this);
    v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, _QWORD, int, unsigned int *, unsigned __int64 *, unsigned __int64 *, void (__fastcall *)(void *, unsigned int, unsigned int, unsigned __int64, unsigned __int64), CVortexReader *))(**((_QWORD **)this + 32917) + 56LL))(
            *((_QWORD *)this + 32917),
            *((_QWORD *)this + 32918),
            (char *)this + 897,
            (unsigned int)v22,
            10000,
            &v39,
            &v40,
            &v38,
            CVortexReader::StaticOnP2pReadCompleted,
            this);
    *((_DWORD *)this + 65855) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 32917) + 88LL))(
                                  *((_QWORD *)this + 32917),
                                  *((_QWORD *)this + 32918));
    CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&pExceptionObject);
    if ( v23 != 997 )
      CVortexReader::OnP2pReadCompleted(this, v23, v39, v40, v38);
  }
  else
  {
LABEL_85:
    if ( *((_BYTE *)this + 263112) && !*((_BYTE *)this + 263132) )
    {
      v24 = 0x40000 - v9 - *((_QWORD *)this + 32881);
      if ( v24 >= v3 )
        LODWORD(v24) = v3;
      v21 = v24;
      goto LABEL_63;
    }
    if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 83) + 56LL))(*((_QWORD *)this + 83), 0) )
    {
      v25 = GetLastError();
      v26 = v25 < 0;
      if ( v25 > 0 )
      {
        v25 = (unsigned __int16)v25 | 0x80070000;
        v26 = v25 < 0;
      }
      if ( v26 )
      {
        v34 = 0;
        v33 = &ComError::`vftable';
        v35 = v25;
        v36 = 1134;
        v37 = 1;
        throw (ComError *)&v33;
      }
    }
  }
}

```

## disassembly

```asm
0x1800590e0  push    rbp
0x1800590e2  push    rbx
0x1800590e3  push    rsi
0x1800590e4  push    rdi
0x1800590e5  push    r12
0x1800590e7  push    r13
0x1800590e9  push    r14
0x1800590eb  push    r15
0x1800590ed  lea     rbp, [rsp-28h]
0x1800590f2  sub     rsp, 128h
0x1800590f9  mov     r14d, r8d
0x1800590fc  mov     edi, edx
0x1800590fe  mov     rbx, rcx
0x180059101  lea     rsi, WPP_GLOBAL_Control
0x180059108  cmp     [rcx+278h], edx
0x18005910e  jz      short loc_180059141
0x180059110  mov     rcx, cs:WPP_GLOBAL_Control
0x180059117  cmp     rcx, rsi
0x18005911a  jz      short loc_180059141
0x18005911c  test    dword ptr [rcx+1Ch], 800h
0x180059123  jz      short loc_180059141
0x180059125  mov     edx, 5Bh ; '['
0x18005912a  mov     dword ptr [rsp+160h+var_140], edi
0x18005912e  mov     r9, rbx
0x180059131  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180059138  mov     rcx, [rcx+10h]
0x18005913c  call    WPP_SF_qD
0x180059141  mov     [rbx+278h], edi
0x180059147  mov     byte ptr [rbx+38h], 0
0x18005914b  mov     dword ptr [rbx+40384h], 0BEEECCCCh
0x180059155  mov     rcx, cs:WPP_GLOBAL_Control
0x18005915c  cmp     rcx, rsi
0x18005915f  jz      short loc_180059182
0x180059161  test    dword ptr [rcx+1Ch], 800h
0x180059168  jz      short loc_180059182
0x18005916a  mov     edx, 2Dh ; '-'
0x18005916f  mov     r9d, r14d
0x180059172  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x180059179  mov     rcx, [rcx+10h]
0x18005917d  call    WPP_SF_d
0x180059182  mov     eax, r14d
0x180059185  mov     r12d, 40000h
0x18005918b  cmp     r14d, r12d
0x18005918e  cmovnb  eax, r12d
0x180059192  mov     [rbx+0CCh], eax
0x180059198  mov     rdx, [rbx+40390h]; Src
0x18005919f  mov     rsi, 0FFFFFFFFFFFFFC7Fh
0x1800591a6  sub     rsi, rbx
0x1800591a9  lea     r15, [rsi+rdx]
0x1800591ad  mov     rdi, [rbx+40388h]
0x1800591b4  sub     rdi, rdx
0x1800591b7  mov     r8, rdi; Size
0x1800591ba  lea     rcx, [rbx+381h]; void *
0x1800591c1  call    memmove_0
0x1800591c6  lea     rax, [rbx+381h]
0x1800591cd  add     rax, rdi
0x1800591d0  mov     [rbx+40388h], rax
0x1800591d7  mov     [rbx+40390h], rax
0x1800591de  test    rdi, rdi
0x1800591e1  jz      short loc_18005922E
0x1800591e3  test    r15, r15
0x1800591e6  jz      short loc_180059233
0x1800591e8  cmp     dword ptr [rbx+80h], 2
0x1800591ef  jz      short loc_180059200
0x1800591f1  mov     eax, [rbx+0CCh]
0x1800591f7  cmp     rdi, rax
0x1800591fa  jb      loc_1800592A7
0x180059200  mov     rax, [rbx]
0x180059203  mov     r8b, 1
0x180059206  xor     edx, edx
0x180059208  mov     rcx, rbx
0x18005920b  mov     rax, [rax+218h]
0x180059212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059217  mov     rax, [rbx]
0x18005921a  mov     rcx, rbx
0x18005921d  mov     rax, [rax+248h]
0x180059224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059229  jmp     loc_180059668
0x18005922e  test    r15, r15
0x180059231  jnz     short loc_1800592A7
0x180059233  cmp     byte ptr [rbx+403B9h], 0
0x18005923a  jz      short loc_1800592A7
0x18005923c  mov     rcx, cs:WPP_GLOBAL_Control
0x180059243  lea     rax, WPP_GLOBAL_Control
0x18005924a  cmp     rcx, rax
0x18005924d  jz      short loc_18005926A
0x18005924f  test    byte ptr [rcx+1Ch], 2
0x180059253  jz      short loc_18005926A
0x180059255  mov     edx, 2Eh ; '.'
0x18005925a  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x180059261  mov     rcx, [rcx+10h]
0x180059265  call    WPP_SF_
0x18005926a  xorps   xmm0, xmm0
0x18005926d  movups  xmmword ptr [rsp+160h+var_F8], xmm0
0x180059272  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180059279  mov     [rsp+160h+pExceptionObject], rcx
0x18005927e  mov     dword ptr [rsp+160h+var_E8], 8020001Bh
0x180059286  mov     dword ptr [rsp+160h+var_E8+4], 3D7h
0x18005928e  mov     dword ptr [rbp+60h+var_E0], 1
0x180059295  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005929c  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800592a1  call    _CxxThrowException_0
0x1800592a7  cmp     qword ptr [rbx+404C0h], 0
0x1800592af  jz      loc_1800593D0
0x1800592b5  mov     rcx, rbx; this
0x1800592b8  call    ?IsForceOrigin@CVortexReader@@QEBA_NXZ; CVortexReader::IsForceOrigin(void)
0x1800592bd  test    al, al
0x1800592bf  jnz     loc_1800593D0
0x1800592c5  xor     r15d, r15d
0x1800592c8  mov     [rbp+60h+arg_18], r15
0x1800592cf  mov     [rbp+60h+arg_0], r15
0x1800592d3  mov     [rbp+60h+arg_8], r15d
0x1800592d7  mov     rax, r14
0x1800592da  sub     rax, rdi
0x1800592dd  sub     rax, rsi
0x1800592e0  sub     rax, rbx
0x1800592e3  add     rax, 0FFFFFFFFFFFFFC7Fh
0x1800592e9  cmp     rax, r12
0x1800592ec  cmovb   r12d, eax
0x1800592f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800592f7  lea     rax, WPP_GLOBAL_Control
0x1800592fe  cmp     rcx, rax
0x180059301  jz      short loc_180059324
0x180059303  test    dword ptr [rcx+1Ch], 1000h
0x18005930a  jz      short loc_180059324
0x18005930c  mov     edx, 2Fh ; '/'
0x180059311  mov     r9d, r12d
0x180059314  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x18005931b  mov     rcx, [rcx+10h]
0x18005931f  call    WPP_SF_d
0x180059324  lea     rdx, [rbx+40488h]; struct TokenHandle *
0x18005932b  lea     rcx, [rsp+160h+pExceptionObject]; this
0x180059330  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x180059335  nop
0x180059336  lea     rcx, [rbx+40500h]
0x18005933d  mov     edx, 2
0x180059342  call    ?TakeSnapshot@PeerNetworkMonitor@@IEAAXW4SNAPSHOT@1@@Z; PeerNetworkMonitor::TakeSnapshot(PeerNetworkMonitor::SNAPSHOT)
0x180059347  mov     rcx, rbx; this
0x18005934a  call    ?IncrementPendingAsyncOpsCount@CHttpReader@@IEAAXXZ; CHttpReader::IncrementPendingAsyncOpsCount(void)
0x18005934f  mov     rcx, [rbx+404A8h]
0x180059356  mov     rax, [rcx]
0x180059359  mov     [rsp+160h+var_118], rbx
0x18005935e  lea     rdx, ?StaticOnP2pReadCompleted@CVortexReader@@KAXPEAXKK_K1@Z; CVortexReader::StaticOnP2pReadCompleted(void *,ulong,ulong,unsigned __int64,unsigned __int64)
0x180059365  mov     [rsp+160h+var_120], rdx
0x18005936a  lea     rdx, [rbp+60h+arg_0]
0x18005936e  mov     [rsp+160h+var_128], rdx
0x180059373  lea     rdx, [rbp+60h+arg_18]
0x18005937a  mov     [rsp+160h+var_130], rdx
0x18005937f  lea     rdx, [rbp+60h+arg_8]
0x180059383  mov     [rsp+160h+var_138], rdx
0x180059388  mov     dword ptr [rsp+160h+var_140], 2710h
0x180059390  mov     r9d, r12d
0x180059393  lea     r8, [rbx+381h]
0x18005939a  mov     rdx, [rbx+404C0h]
0x1800593a1  mov     rax, [rax+38h]
0x1800593a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800593aa  mov     edi, eax
0x1800593ac  lea     rcx, [rsp+160h+pExceptionObject]; this
0x1800593b1  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x1800593b6  cmp     edi, 3E5h
0x1800593bc  jz      loc_180059668
0x1800593c2  mov     rcx, [rbp+60h+arg_0]
0x1800593c6  mov     [rsp+160h+var_140], rcx
0x1800593cb  jmp     loc_18005979B
0x1800593d0  mov     rdi, [rbx+404B0h]
0x1800593d7  test    rdi, rdi
0x1800593da  jz      loc_1800597B5
0x1800593e0  lea     rcx, [rsp+160h+pExceptionObject]; this
0x1800593e5  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x1800593ea  nop
0x1800593eb  mov     byte ptr [rsp+160h+var_F8], 0
0x1800593f0  mov     rax, [rbx+40488h]
0x1800593f7  mov     [rsp+160h+var_F8+8], rax
0x1800593fc  lock inc dword ptr [rax+8]
0x180059400  xor     r15d, r15d
0x180059403  mov     [rsp+160h+var_E8], r15
0x180059408  mov     edx, 8; dwFlags
0x18005940d  mov     r8d, 4; dwBytes
0x180059413  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18005941a  call    cs:__imp_HeapAlloc
0x180059420  test    rax, rax
0x180059423  jnz     short loc_18005948E
0x180059425  mov     rcx, cs:WPP_GLOBAL_Control
0x18005942c  lea     rax, WPP_GLOBAL_Control
0x180059433  cmp     rcx, rax
0x180059436  jz      short loc_180059459
0x180059438  test    byte ptr [rcx+1Ch], 4
0x18005943c  jz      short loc_180059459
0x18005943e  mov     edx, 0Ah
0x180059443  mov     r9d, 4
0x180059449  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180059450  mov     rcx, [rcx+10h]
0x180059454  call    WPP_SF_d
0x180059459  xorps   xmm0, xmm0
0x18005945c  movups  [rbp+60h+var_98], xmm0
0x180059460  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180059467  mov     [rbp+60h+var_A0], rcx
0x18005946b  mov     [rbp+60h+var_88], 8007000Eh
0x180059472  mov     [rbp+60h+var_84], r15d
0x180059476  mov     [rbp+60h+var_80], 1
0x18005947d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180059484  lea     rcx, [rbp+60h+var_A0]; pExceptionObject
0x180059488  call    _CxxThrowException_0
0x18005948e  mov     dword ptr [rax], 1
0x180059494  mov     [rbp+60h+var_E0], rax
0x180059498  mov     [rbp+60h+var_D8], r15
0x18005949c  lock inc cs:dword_180145058
0x1800594a3  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x1800594aa  mov     [rbp+60h+var_D0], rax
0x1800594ae  cmp     byte ptr [rsp+160h+var_F8], 0
0x1800594b3  jnz     short loc_18005950F
0x1800594b5  mov     rcx, [rsp+160h+var_F8+8]
0x1800594ba  mov     rcx, [rcx]; hToken
0x1800594bd  call    cs:__imp_ImpersonateLoggedOnUser
0x1800594c3  test    eax, eax
0x1800594c5  jnz     short loc_18005950A
0x1800594c7  call    cs:__imp_GetLastError
0x1800594cd  test    eax, eax
0x1800594cf  jle     short loc_1800594D9
0x1800594d1  movzx   eax, ax
0x1800594d4  or      eax, 80070000h
0x1800594d9  xorps   xmm0, xmm0
0x1800594dc  movups  [rbp+60h+var_98], xmm0
0x1800594e0  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800594e7  mov     [rbp+60h+var_A0], rcx
0x1800594eb  mov     [rbp+60h+var_88], eax
0x1800594ee  mov     [rbp+60h+var_84], r15d
0x1800594f2  mov     [rbp+60h+var_80], 1
0x1800594f9  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180059500  lea     rcx, [rbp+60h+var_A0]; pExceptionObject
0x180059504  call    _CxxThrowException_0
0x18005950a  mov     byte ptr [rsp+160h+var_F8], 1
0x18005950f  mov     rcx, [rbx+404A8h]
0x180059516  mov     rax, [rcx]
0x180059519  mov     rdx, rdi
0x18005951c  mov     rax, [rax+28h]
0x180059520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059525  mov     [rbp+60h+arg_8], eax
0x180059528  cmp     byte ptr [rsp+160h+var_F8], 0
0x18005952d  jz      short loc_180059544
0x18005952f  mov     rdx, [rsp+160h+pExceptionObject]
0x180059534  mov     rdx, [rdx]; Token
0x180059537  xor     ecx, ecx; Thread
0x180059539  call    cs:__imp_SetThreadToken
0x18005953f  mov     byte ptr [rsp+160h+var_F8], 0
0x180059544  mov     rcx, [rbp+60h+var_D0]
0x180059548  mov     edi, 0FFFFFFFFh
0x18005954d  test    rcx, rcx
0x180059550  jz      short loc_180059570
0x180059552  mov     eax, edi
0x180059554  lock xadd [rcx+8], eax
0x180059559  cmp     eax, 1
0x18005955c  jnz     short loc_18005956C
0x18005955e  mov     edx, 10h; unsigned __int64
0x180059563  mov     rcx, [rbp+60h+var_D0]; void *
0x180059567  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005956c  mov     [rbp+60h+var_D0], r15
0x180059570  mov     rdx, [rbp+60h+var_D8]
0x180059574  test    rdx, rdx
0x180059577  jz      short loc_18005957E
0x180059579  call    ??R?$default_delete@UAppPackageInfo@@@std@@QEBAXPEAUAppPackageInfo@@@Z; std::default_delete<AppPackageInfo>::operator()(AppPackageInfo *)
0x18005957e  mov     rax, [rbp+60h+var_E0]
0x180059582  mov     ecx, edi
0x180059584  lock xadd [rax], ecx
0x180059588  cmp     ecx, 1
0x18005958b  jnz     short loc_1800595B0
0x18005958d  mov     edx, 4; unsigned __int64
0x180059592  mov     rcx, [rbp+60h+var_E0]; void *
0x180059596  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005959b  xor     edx, edx; unsigned __int64
0x18005959d  mov     rcx, [rsp+160h+var_E8]; void *
0x1800595a2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800595a7  mov     [rbp+60h+var_E0], r15
0x1800595ab  mov     [rsp+160h+var_E8], r15
0x1800595b0  mov     rcx, [rsp+160h+var_F8+8]
0x1800595b5  mov     eax, edi
0x1800595b7  lock xadd [rcx+8], eax
0x1800595bc  cmp     eax, 1
0x1800595bf  jnz     short loc_1800595F8
0x1800595c1  mov     rcx, [rsp+160h+var_F8+8]
0x1800595c6  mov     rdx, [rcx]
0x1800595c9  lea     rax, [rdx-1]
0x1800595cd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800595d1  ja      short loc_1800595E9
0x1800595d3  mov     rcx, rdx; hObject
0x1800595d6  call    cs:__imp_CloseHandle
0x1800595dc  mov     rax, [rsp+160h+var_F8+8]
0x1800595e1  mov     [rax], r15
0x1800595e4  mov     rcx, [rsp+160h+var_F8+8]; void *
0x1800595e9  mov     edx, 10h; unsigned __int64
0x1800595ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800595f3  mov     [rsp+160h+var_F8+8], r15
0x1800595f8  mov     rdx, [rsp+160h+pExceptionObject]
0x1800595fd  mov     rdx, [rdx]; Token
0x180059600  xor     ecx, ecx; Thread
0x180059602  call    cs:__imp_SetThreadToken
0x180059608  mov     rax, [rsp+160h+pExceptionObject]
0x18005960d  lock xadd [rax+8], edi
0x180059612  cmp     edi, 1
0x180059615  jnz     short loc_180059649
  ... truncated ...
```

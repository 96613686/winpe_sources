# BitsESE::BitsJetDatabaseSession::CreateOrMoveToEntityAndPrepareUpdate(tagPROPVARIANT const *,BitsESE::TableMapping const *,unsigned __int64)

- ea: `0x180040240`
- end: `0x1800407c1`
- name: `?CreateOrMoveToEntityAndPrepareUpdate@BitsJetDatabaseSession@BitsESE@@AEAAJPEBUtagPROPVARIANT@@PEBUTableMapping@2@_K@Z`
- size: `1409`
- prototype: `__int64 __fastcall(BitsESE::BitsJetDatabaseSession *__hidden this, const struct tagPROPVARIANT *, const struct BitsESE::TableMapping *, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003ecfc`

## callees

- `0x18000e370`
- `0x18003fee0`
- `0x180040240`
- `0x1800407d0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800df514`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004027c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004027c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180040772`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180040772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800403b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800403c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800403ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800403b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800403c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800403ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004038e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004078f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004038e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004078f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800403ac`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800403ac`
- `ESENT!JetPrepareUpdate` at `0x18004056e`
- `ESENT!JetPrepareUpdate` at `0x1800406f3`
- `ESENT!JetPrepareUpdate` at `0x18004056e`
- `ESENT!JetPrepareUpdate` at `0x1800406f3`
- `ESENT!JetSetColumn` at `0x180040607`
- `ESENT!JetSetColumn` at `0x180040607`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BitsESE::BitsJetDatabaseSession::CreateOrMoveToEntityAndPrepareUpdate(
        JET_SESID *this,
        const struct tagPROPVARIANT *a2,
        const struct BitsESE::TableMapping *a3,
        JET_TABLEID a4)
{
  volatile signed __int32 *v7; // rax
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 **v9; // rsi
  HANDLE *v10; // rcx
  unsigned int LastError; // ecx
  int v12; // esi
  unsigned __int8 v13; // cl
  EVENT_LOG *v14; // rcx
  VARTYPE vt; // ax
  BYTE *pbVal; // rsi
  LONG cbData; // r12d
  JET_ERR v18; // eax
  unsigned __int8 v19; // cl
  JET_ERR v20; // eax
  unsigned __int8 v21; // cl
  int v22; // esi
  JET_ERR v23; // eax
  unsigned __int8 v24; // cl
  int v25; // esi
  __int64 result; // rax
  const ComError *v27; // rbx
  int v28; // [rsp+40h] [rbp-2F8h] BYREF
  JET_COLUMNID columnid[2]; // [rsp+48h] [rbp-2F0h] BYREF
  volatile signed __int32 *v30; // [rsp+50h] [rbp-2E8h]
  const ComError *v31; // [rsp+58h] [rbp-2E0h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-2D8h] BYREF
  __int128 v33; // [rsp+68h] [rbp-2D0h]
  int v34; // [rsp+78h] [rbp-2C0h]
  int v35; // [rsp+7Ch] [rbp-2BCh]
  int v36; // [rsp+80h] [rbp-2B8h]
  void **v37; // [rsp+C0h] [rbp-278h] BYREF
  __int128 v38; // [rsp+C8h] [rbp-270h]
  unsigned int v39; // [rsp+D8h] [rbp-260h]
  int v40; // [rsp+DCh] [rbp-25Ch]
  int v41; // [rsp+E0h] [rbp-258h]
  void **v42; // [rsp+120h] [rbp-218h] BYREF
  __int128 v43; // [rsp+128h] [rbp-210h]
  int v44; // [rsp+138h] [rbp-200h]
  int v45; // [rsp+13Ch] [rbp-1FCh]
  int v46; // [rsp+140h] [rbp-1F8h]
  void **v47; // [rsp+180h] [rbp-1B8h] BYREF
  __int128 v48; // [rsp+188h] [rbp-1B0h]
  int v49; // [rsp+198h] [rbp-1A0h]
  int v50; // [rsp+19Ch] [rbp-19Ch]
  int v51; // [rsp+1A0h] [rbp-198h]
  void **v52; // [rsp+1E0h] [rbp-158h] BYREF
  __int128 v53; // [rsp+1E8h] [rbp-150h]
  int v54; // [rsp+1F8h] [rbp-140h]
  int v55; // [rsp+1FCh] [rbp-13Ch]
  int v56; // [rsp+200h] [rbp-138h]
  void **v57; // [rsp+240h] [rbp-F8h] BYREF
  __int128 v58; // [rsp+248h] [rbp-F0h]
  int v59; // [rsp+258h] [rbp-E0h]
  int v60; // [rsp+25Ch] [rbp-DCh]
  int v61; // [rsp+260h] [rbp-D8h]
  void **v62; // [rsp+2A0h] [rbp-98h] BYREF
  __int128 v63; // [rsp+2A8h] [rbp-90h]
  int v64; // [rsp+2B8h] [rbp-80h]
  int v65; // [rsp+2BCh] [rbp-7Ch]
  int v66; // [rsp+2C0h] [rbp-78h]

  v7 = (volatile signed __int32 *)HeapAlloc(hBitsHeap, 8u, 0x10u);
  try
  {
    v8 = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
      v33 = 0;
      pExceptionObject = &ComError::`vftable';
      v34 = -2147024882;
      v35 = 0;
      v36 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v30 = v7;
    *((_DWORD *)v7 + 2) = 1;
    *(_QWORD *)v7 = 0;
    v9 = (volatile signed __int32 **)CopyThreadToken(columnid);
    if ( *(_QWORD *)v8 != *(_QWORD *)*v9 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        if ( (unsigned __int64)(*(_QWORD *)v8 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(*(HANDLE *)v8);
          *(_QWORD *)v8 = 0;
        }
        operator delete((void *)v8, 0x10u);
      }
      v8 = *v9;
      v30 = v8;
      _InterlockedIncrement(v8 + 2);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)columnid + 8LL), 0xFFFFFFFF) == 1 )
    {
      v10 = *(HANDLE **)columnid;
      if ( (unsigned __int64)(**(_QWORD **)columnid - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(**(HANDLE **)columnid);
        **(_QWORD **)columnid = 0;
        v10 = *(HANDLE **)columnid;
      }
      operator delete(v10, 0x10u);
    }
    if ( !RevertToSelf() )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v38 = 0;
      v37 = &ComError::`vftable';
      v39 = LastError;
      v40 = 769;
      v41 = 1;
      throw (ComError *)&v37;
    }
    v12 = BitsESE::BitsJetDatabaseSession::MoveToEntity((BitsESE::BitsJetDatabaseSession *)this, a2, a3);
    columnid[0] = v12;
    if ( v12 >= 0 )
    {
      v23 = JetPrepareUpdate(this[3], a4, 2u);
      v25 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v23);
      columnid[0] = v25;
      if ( v25 < 0 )
      {
        v28 = 807;
        CTelemetry::DatabaseFailure<char const (&)[70],int,long &,enum MANAGER_STATE &>(
          v24,
          (unsigned int *)&v28,
          columnid);
        v63 = 0;
        v62 = &ComError::`vftable';
        v64 = v25;
        v65 = 807;
        v66 = 1;
        throw (ComError *)&v62;
      }
    }
    else
    {
      if ( v12 != (unsigned int)BitsESE::BitsJetDatabaseSession::JetErrToHR(-1601) )
      {
        v28 = 800;
        CTelemetry::DatabaseFailure<char const (&)[70],int,long &,enum MANAGER_STATE &>(
          v13,
          (unsigned int *)&v28,
          columnid);
        v58 = 0;
        v57 = &ComError::`vftable';
        v59 = v12;
        v60 = 801;
        v61 = 1;
        throw (ComError *)&v57;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
      vt = a2->vt;
      if ( a2->vt == 72 )
      {
        pbVal = a2->pbVal;
        cbData = 16;
      }
      else if ( vt )
      {
        if ( vt != 65 )
        {
          if ( v14 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)v14 + 2), 57, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids);
          v43 = 0;
          v42 = &ComError::`vftable';
          v44 = -2147418113;
          v45 = 785;
          v46 = 1;
          throw (ComError *)&v42;
        }
        pbVal = a2->bstrblobVal.pData;
        cbData = a2->lVal;
      }
      else
      {
        pbVal = 0;
        cbData = 0;
      }
      columnid[0] = (&off_180144210)[7 * *((unsigned int *)a3 + 1)][6 * *((unsigned int *)a3 + 2) + 3];
      v18 = JetPrepareUpdate(this[3], a4, 0);
      v28 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v18);
      if ( v28 < 0 )
      {
        columnid[0] = 787;
        CTelemetry::DatabaseFailure<char const (&)[70],int,long &,enum MANAGER_STATE &>(
          v19,
          columnid,
          (unsigned int *)&v28);
        v48 = 0;
        v47 = &ComError::`vftable';
        v49 = v28;
        v50 = 787;
        v51 = 1;
        throw (ComError *)&v47;
      }
      v20 = JetSetColumn(this[3], a4, columnid[0], pbVal, cbData, 0, 0);
      v22 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v20);
      columnid[0] = v22;
      if ( v22 < 0 )
      {
        v28 = 795;
        CTelemetry::DatabaseFailure<char const (&)[70],int,long &,enum MANAGER_STATE &>(
          v21,
          (unsigned int *)&v28,
          columnid);
        v53 = 0;
        v52 = &ComError::`vftable';
        v54 = v22;
        v55 = 795;
        v56 = 1;
        throw (ComError *)&v52;
      }
    }
    SetThreadToken(0, *(HANDLE *)v8);
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( (unsigned __int64)(*(_QWORD *)v8 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v8);
        *(_QWORD *)v8 = 0;
      }
      operator delete((void *)v8, 0x10u);
    }
    result = 0;
  }
  catch ( const ComError *v31 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v27 = v31;
    }
    else
    {
      v27 = v31;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids,
        *((unsigned int *)v27 + 6),
        *((_DWORD *)v27 + 7));
    }
    JetPrepareUpdate(this[3], a4, 3u);
    return *((unsigned int *)v27 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x180040240  mov     [rsp+arg_18], r9
0x180040245  mov     [rsp+arg_10], r8
0x18004024a  mov     [rsp+arg_0], rcx
0x18004024f  push    rbx
0x180040250  push    rsi
0x180040251  push    rdi
0x180040252  push    r12
0x180040254  push    r13
0x180040256  push    r14
0x180040258  push    r15
0x18004025a  sub     rsp, 300h
0x180040261  mov     r15, r9
0x180040264  mov     r12, rdx
0x180040267  mov     r14, rcx
0x18004026a  mov     edx, 8; dwFlags
0x18004026f  mov     r8d, 10h; dwBytes
0x180040275  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18004027c  call    cs:__imp_HeapAlloc
0x180040282  mov     rbx, rax
0x180040285  test    rax, rax
0x180040288  jnz     short loc_1800402FE
0x18004028a  lea     rsi, WPP_GLOBAL_Control
0x180040291  mov     rcx, cs:WPP_GLOBAL_Control
0x180040298  cmp     rcx, rsi
0x18004029b  jz      short loc_1800402BE
0x18004029d  test    byte ptr [rcx+1Ch], 4
0x1800402a1  jz      short loc_1800402BE
0x1800402a3  mov     edx, 0Ah
0x1800402a8  mov     r9d, 10h
0x1800402ae  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800402b5  mov     rcx, [rcx+10h]
0x1800402b9  call    WPP_SF_d
0x1800402be  xorps   xmm0, xmm0
0x1800402c1  movups  [rsp+338h+var_2D0], xmm0
0x1800402c6  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800402cd  mov     [rsp+338h+pExceptionObject], rax
0x1800402d2  mov     [rsp+338h+var_2C0], 8007000Eh
0x1800402da  xor     r13d, r13d
0x1800402dd  mov     [rsp+338h+var_2BC], r13d
0x1800402e2  mov     [rsp+338h+var_2B8], 1
0x1800402ed  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800402f4  lea     rcx, [rsp+338h+pExceptionObject]; pExceptionObject
0x1800402f9  call    _CxxThrowException_0
0x1800402fe  mov     [rsp+338h+var_2E8], rbx
0x180040303  mov     dword ptr [rax+8], 1
0x18004030a  xor     r13d, r13d
0x18004030d  mov     [rax], r13
0x180040310  lea     rcx, [rsp+338h+columnid]
0x180040315  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x18004031a  mov     rsi, rax
0x18004031d  mov     rcx, [rax]
0x180040320  mov     rdx, [rcx]
0x180040323  mov     edi, 0FFFFFFFFh
0x180040328  cmp     [rbx], rdx
0x18004032b  jz      short loc_180040368
0x18004032d  mov     ecx, edi
0x18004032f  lock xadd [rbx+8], ecx
0x180040334  cmp     ecx, 1
0x180040337  jnz     short loc_18004035C
0x180040339  mov     rcx, [rbx]; hObject
0x18004033c  lea     rax, [rcx-1]
0x180040340  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180040344  ja      short loc_18004034F
0x180040346  call    cs:__imp_CloseHandle
0x18004034c  mov     [rbx], r13
0x18004034f  mov     edx, 10h; unsigned __int64
0x180040354  mov     rcx, rbx; void *
0x180040357  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004035c  mov     rbx, [rsi]
0x18004035f  mov     [rsp+338h+var_2E8], rbx
0x180040364  lock inc dword ptr [rbx+8]
0x180040368  mov     rcx, qword ptr [rsp+338h+columnid]
0x18004036d  mov     eax, edi
0x18004036f  lock xadd [rcx+8], eax
0x180040374  cmp     eax, 1
0x180040377  jnz     short loc_1800403AC
0x180040379  mov     rcx, qword ptr [rsp+338h+columnid]
0x18004037e  mov     rdx, [rcx]
0x180040381  lea     rax, [rdx-1]
0x180040385  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180040389  ja      short loc_1800403A1
0x18004038b  mov     rcx, rdx; hObject
0x18004038e  call    cs:__imp_CloseHandle
0x180040394  mov     rax, qword ptr [rsp+338h+columnid]
0x180040399  mov     [rax], r13
0x18004039c  mov     rcx, qword ptr [rsp+338h+columnid]; void *
0x1800403a1  mov     edx, 10h; unsigned __int64
0x1800403a6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800403ab  nop
0x1800403ac  call    cs:__imp_RevertToSelf
0x1800403b2  test    eax, eax
0x1800403b4  jnz     short loc_180040424
0x1800403b6  call    cs:__imp_GetLastError
0x1800403bc  test    eax, eax
0x1800403be  jg      short loc_1800403CA
0x1800403c0  call    cs:__imp_GetLastError
0x1800403c6  mov     ecx, eax
0x1800403c8  jmp     short loc_1800403D9
0x1800403ca  call    cs:__imp_GetLastError
0x1800403d0  movzx   ecx, ax
0x1800403d3  or      ecx, 80070000h
0x1800403d9  xorps   xmm0, xmm0
0x1800403dc  movups  [rsp+338h+var_270], xmm0
0x1800403e4  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800403eb  mov     [rsp+338h+var_278], rax
0x1800403f3  mov     [rsp+338h+var_260], ecx
0x1800403fa  mov     [rsp+338h+var_25C], 301h
0x180040405  mov     [rsp+338h+var_258], 1
0x180040410  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180040417  lea     rcx, [rsp+338h+var_278]; pExceptionObject
0x18004041f  call    _CxxThrowException_0
0x180040424  mov     r8, [rsp+338h+arg_10]; struct BitsESE::TableMapping *
0x18004042c  mov     rdx, r12; struct tagPROPVARIANT *
0x18004042f  mov     rcx, r14; this
0x180040432  call    ?MoveToEntity@BitsJetDatabaseSession@BitsESE@@AEAAJPEBUtagPROPVARIANT@@PEBUTableMapping@2@@Z; BitsESE::BitsJetDatabaseSession::MoveToEntity(tagPROPVARIANT const *,BitsESE::TableMapping const *)
0x180040437  mov     esi, eax
0x180040439  mov     [rsp+338h+columnid], eax
0x18004043d  test    eax, eax
0x18004043f  jns     loc_1800406E6
0x180040445  mov     ecx, 0FFFFF9BFh; int
0x18004044a  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18004044f  cmp     esi, eax
0x180040451  jnz     loc_180040684
0x180040457  lea     rsi, WPP_GLOBAL_Control
0x18004045e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040465  cmp     rcx, rsi
0x180040468  jz      short loc_18004048C
0x18004046a  test    byte ptr [rcx+1Ch], 1
0x18004046e  jz      short loc_18004048C
0x180040470  mov     edx, 29h ; ')'
0x180040475  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x18004047c  mov     rcx, [rcx+10h]
0x180040480  call    WPP_SF_
0x180040485  mov     rcx, cs:WPP_GLOBAL_Control
0x18004048c  movzx   eax, word ptr [r12]
0x180040491  cmp     ax, 48h ; 'H'
0x180040495  jz      loc_18004052D
0x18004049b  test    ax, ax
0x18004049e  jz      loc_180040525
0x1800404a4  cmp     ax, 41h ; 'A'
0x1800404a8  jz      short loc_180040519
0x1800404aa  cmp     rcx, rsi
0x1800404ad  jz      short loc_1800404CA
0x1800404af  test    byte ptr [rcx+1Ch], 4
0x1800404b3  jz      short loc_1800404CA
0x1800404b5  mov     edx, 39h ; '9'
0x1800404ba  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x1800404c1  mov     rcx, [rcx+10h]
0x1800404c5  call    WPP_SF_
0x1800404ca  xorps   xmm0, xmm0
0x1800404cd  movups  [rsp+338h+var_210], xmm0
0x1800404d5  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800404dc  mov     [rsp+338h+var_218], rax
0x1800404e4  mov     [rsp+338h+var_200], 8000FFFFh
0x1800404ef  mov     [rsp+338h+var_1FC], 311h
0x1800404fa  mov     [rsp+338h+var_1F8], 1
0x180040505  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004050c  lea     rcx, [rsp+338h+var_218]; pExceptionObject
0x180040514  call    _CxxThrowException_0
0x180040519  mov     rsi, [r12+10h]
0x18004051e  mov     r12d, [r12+8]
0x180040523  jmp     short loc_180040538
0x180040525  mov     rsi, r13
0x180040528  mov     r12d, r13d
0x18004052b  jmp     short loc_180040538
0x18004052d  mov     rsi, [r12+8]
0x180040532  mov     r12d, 10h
0x180040538  mov     rcx, [rsp+338h+arg_10]
0x180040540  mov     eax, [rcx+4]
0x180040543  imul    rdx, rax, 38h ; '8'
0x180040547  lea     r8, off_180144210
0x18004054e  mov     eax, [rcx+8]
0x180040551  lea     rcx, [rax+rax*2]
0x180040555  add     rcx, rcx
0x180040558  mov     rax, [rdx+r8]
0x18004055c  mov     eax, [rax+rcx*8+18h]
0x180040560  mov     [rsp+338h+columnid], eax
0x180040564  xor     r8d, r8d; prep
0x180040567  mov     rdx, r15; tableid
0x18004056a  mov     rcx, [r14+18h]; sesid
0x18004056e  call    cs:__imp_JetPrepareUpdate
0x180040574  mov     ecx, eax; int
0x180040576  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18004057b  mov     [rsp+338h+var_2F8], eax
0x18004057f  test    eax, eax
0x180040581  jns     short loc_1800405E9
0x180040583  mov     [rsp+338h+columnid], 313h
0x18004058b  lea     r8, [rsp+338h+var_2F8]
0x180040590  lea     rdx, [rsp+338h+columnid]
0x180040595  call    ??$DatabaseFailure@AEAY0EG@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0EG@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[70],int,long &,MANAGER_STATE &>(char const (&)[70],int &&,long &,MANAGER_STATE &)
0x18004059a  xorps   xmm0, xmm0
0x18004059d  movups  [rsp+338h+var_1B0], xmm0
0x1800405a5  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800405ac  mov     [rsp+338h+var_1B8], rax
0x1800405b4  mov     eax, [rsp+338h+var_2F8]
0x1800405b8  mov     [rsp+338h+var_1A0], eax
0x1800405bf  mov     [rsp+338h+var_19C], 313h
0x1800405ca  mov     [rsp+338h+var_198], 1
0x1800405d5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800405dc  lea     rcx, [rsp+338h+var_1B8]; pExceptionObject
0x1800405e4  call    _CxxThrowException_0
0x1800405e9  mov     [rsp+338h+psetinfo], r13; psetinfo
0x1800405ee  mov     [rsp+338h+grbit], r13d; grbit
0x1800405f3  mov     [rsp+338h+cbData], r12d; cbData
0x1800405f8  mov     r9, rsi; pvData
0x1800405fb  mov     r8d, [rsp+338h+columnid]; columnid
0x180040600  mov     rdx, r15; tableid
0x180040603  mov     rcx, [r14+18h]; sesid
0x180040607  call    cs:__imp_JetSetColumn
0x18004060d  mov     ecx, eax; int
0x18004060f  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x180040614  mov     esi, eax
0x180040616  mov     [rsp+338h+columnid], eax
0x18004061a  test    eax, eax
0x18004061c  jns     loc_18004076D
0x180040622  mov     [rsp+338h+var_2F8], 31Bh
0x18004062a  lea     r8, [rsp+338h+columnid]
0x18004062f  lea     rdx, [rsp+338h+var_2F8]
0x180040634  call    ??$DatabaseFailure@AEAY0EG@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0EG@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[70],int,long &,MANAGER_STATE &>(char const (&)[70],int &&,long &,MANAGER_STATE &)
0x180040639  xorps   xmm0, xmm0
0x18004063c  movups  [rsp+338h+var_150], xmm0
0x180040644  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18004064b  mov     [rsp+338h+var_158], rax
0x180040653  mov     [rsp+338h+var_140], esi
0x18004065a  mov     [rsp+338h+var_13C], 31Bh
0x180040665  mov     [rsp+338h+var_138], 1
0x180040670  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180040677  lea     rcx, [rsp+338h+var_158]; pExceptionObject
0x18004067f  call    _CxxThrowException_0
0x180040684  mov     [rsp+338h+var_2F8], 320h
0x18004068c  lea     r8, [rsp+338h+columnid]
0x180040691  lea     rdx, [rsp+338h+var_2F8]
0x180040696  call    ??$DatabaseFailure@AEAY0EG@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0EG@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[70],int,long &,MANAGER_STATE &>(char const (&)[70],int &&,long &,MANAGER_STATE &)
0x18004069b  xorps   xmm0, xmm0
0x18004069e  movups  [rsp+338h+var_F0], xmm0
0x1800406a6  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800406ad  mov     [rsp+338h+var_F8], rax
0x1800406b5  mov     [rsp+338h+var_E0], esi
0x1800406bc  mov     [rsp+338h+var_DC], 321h
0x1800406c7  mov     [rsp+338h+var_D8], 1
0x1800406d2  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800406d9  lea     rcx, [rsp+338h+var_F8]; pExceptionObject
0x1800406e1  call    _CxxThrowException_0
0x1800406e6  mov     r8d, 2; prep
0x1800406ec  mov     rdx, r15; tableid
0x1800406ef  mov     rcx, [r14+18h]; sesid
0x1800406f3  call    cs:__imp_JetPrepareUpdate
0x1800406f9  mov     ecx, eax; int
0x1800406fb  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x180040700  mov     esi, eax
0x180040702  mov     [rsp+338h+columnid], eax
0x180040706  test    eax, eax
0x180040708  jns     short loc_18004076D
0x18004070a  mov     [rsp+338h+var_2F8], 327h
0x180040712  lea     r8, [rsp+338h+columnid]
0x180040717  lea     rdx, [rsp+338h+var_2F8]
0x18004071c  call    ??$DatabaseFailure@AEAY0EG@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0EG@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[70],int,long &,MANAGER_STATE &>(char const (&)[70],int &&,long &,MANAGER_STATE &)
0x180040721  xorps   xmm0, xmm0
0x180040724  movups  [rsp+338h+var_90], xmm0
0x18004072c  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180040733  mov     [rsp+338h+var_98], rax
0x18004073b  mov     [rsp+338h+var_80], esi
0x180040742  mov     [rsp+338h+var_7C], 327h
0x18004074d  mov     [rsp+338h+var_78], 1
0x180040758  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004075f  lea     rcx, [rsp+338h+var_98]; pExceptionObject
0x180040767  call    _CxxThrowException_0
0x18004076d  mov     rdx, [rbx]; Token
0x180040770  xor     ecx, ecx; Thread
0x180040772  call    cs:__imp_SetThreadToken
0x180040778  lock xadd [rbx+8], edi
0x18004077d  cmp     edi, 1
0x180040780  jnz     short loc_1800407A5
0x180040782  mov     rcx, [rbx]; hObject
0x180040785  lea     rax, [rcx-1]
0x180040789  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004078d  ja      short loc_180040798
0x18004078f  call    cs:__imp_CloseHandle
0x180040795  mov     [rbx], r13
0x180040798  mov     edx, 10h; unsigned __int64
0x18004079d  mov     rcx, rbx; void *
0x1800407a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800407a5  xor     eax, eax
0x1800407a7  jmp     short loc_1800407AD
0x1800407a9  mov     eax, [rsp+338h+columnid]
0x1800407ad  add     rsp, 300h
0x1800407b4  pop     r15
0x1800407b6  pop     r14
0x1800407b8  pop     r13
0x1800407ba  pop     r12
0x1800407bc  pop     rdi
0x1800407bd  pop     rsi
0x1800407be  pop     rbx
0x1800407bf  retn
```

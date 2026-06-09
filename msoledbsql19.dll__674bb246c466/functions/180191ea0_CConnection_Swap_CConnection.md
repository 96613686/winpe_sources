# CConnection::Swap(CConnection *)

- ea: `0x180191ea0`
- end: `0x1801923d0`
- name: `?Swap@CConnection@@QEAAJPEAV1@@Z`
- size: `1328`
- prototype: `__int64 __fastcall(CConnection *__hidden this, struct CConnection *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18001bd40`

## callees

- `0x180003030`
- `0x1800030c0`
- `0x180003d80`
- `0x180156820`
- `0x180159230`
- `0x180184820`
- `0x1801894d0`
- `0x180190390`
- `0x180190480`
- `0x180191ea0`
- `0x1801a65e1`
- `0x1801a6973`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x180191f24`
- `KERNEL32!InterlockedPopEntrySList` at `0x180191f24`
- `KERNEL32!GetTickCount` at `0x180192039`
- `KERNEL32!GetTickCount` at `0x180192039`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180192321`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180192321`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18019232d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18019232d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConnection::Swap(CConnection *this, struct CConnection *a2)
{
  unsigned int v4; // r12d
  int v5; // r15d
  __int64 v6; // rcx
  __int64 v7; // rdx
  BATCHCTX *v8; // rcx
  PSLIST_ENTRY v9; // rax
  char v10; // bl
  char *v11; // rax
  __int64 v12; // rbx
  __int64 v13; // r14
  signed __int32 v14; // ebp
  int v15; // eax
  _WORD *v16; // rcx
  __int64 v17; // rdx
  __int16 v18; // ax
  _WORD *v19; // rax
  _WORD *v20; // rcx
  __int64 v21; // rdx
  __int16 v22; // ax
  _WORD *v23; // rax
  _OWORD *v24; // rax
  _OWORD *v25; // rcx
  char *v26; // rdi
  __int64 v27; // r9
  char *v28; // rsi
  unsigned __int64 v29; // rcx
  _QWORD *v30; // r8
  __int64 v31; // r10
  __int64 v32; // rdx
  _QWORD *v33; // rdx
  _QWORD *v34; // rcx
  _QWORD *v35; // rax
  int v37; // [rsp+30h] [rbp-48h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    _InterlockedExchange((volatile __int32 *)(v6 + 32), 16);
    _InterlockedExchange((volatile __int32 *)(v6 + 36), 0);
    v7 = *(_QWORD *)(v6 + 64);
    if ( v7 )
      *(_BYTE *)(v7 + 1386) = 1;
    v8 = (BATCHCTX *)*((_QWORD *)this + 3);
    v5 = *((_DWORD *)v8 + 197);
    BATCHCTX::Release(v8);
    *((_QWORD *)this + 3) = 0;
  }
  if ( (*((_BYTE *)this + 416) & 1) != 0 )
  {
    while ( 1 )
    {
      v9 = InterlockedPopEntrySList((PSLIST_HEADER)this + 3);
      if ( !v9 || v9 == (PSLIST_ENTRY)16 )
        break;
      ((void (__fastcall *)(struct _SLIST_ENTRY *, __int64))v9[-1].Next->Next)(&v9[-1], 1);
    }
  }
  if ( *((_QWORD *)this + 2) )
  {
    v10 = 0;
    if ( !g_AllocatorInUse )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct ISOSHost *, int *))(*(_QWORD *)g_pISOSHost + 24LL))(g_pISOSHost, &v37);
      if ( !v37 )
      {
        (*(void (__fastcall **)(struct ISOSHost *))(*(_QWORD *)g_pISOSHost + 200LL))(g_pISOSHost);
        v10 = 1;
      }
    }
    SNIClose(*((SNI_Conn **)this + 2));
    *((_QWORD *)this + 2) = 0;
    if ( v10 )
      (*(void (__fastcall **)(struct ISOSHost *))(*(_QWORD *)g_pISOSHost + 208LL))(g_pISOSHost);
  }
  CConnection::CleanupFeatureExtensions(this);
  if ( *((_QWORD *)this + 61) )
  {
    (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
    *((_QWORD *)this + 61) = 0;
  }
  v11 = (char *)this + 1392;
  v12 = 0;
  if ( this != (CConnection *)-1392LL )
  {
    v12 = *(_QWORD *)v11;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v11 + 32LL) + 8LL))(*(_QWORD *)v11 + 32LL);
  }
  *((_QWORD *)this + 2) = *((_QWORD *)a2 + 2);
  *((_QWORD *)a2 + 2) = 0;
  v13 = 2;
  SNISetInfo(*((_QWORD *)this + 2), 2, this);
  *((_DWORD *)this + 350) = GetTickCount();
  *((_BYTE *)this + 1386) = 0;
  ++*((_DWORD *)this + 351);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v12 + 32) + 24LL))(v12 + 32);
  *((_DWORD *)this + 9) = *((_DWORD *)a2 + 9);
  *((_DWORD *)this + 8) = *((_DWORD *)a2 + 8);
  *((_QWORD *)this + 3) = *((_QWORD *)a2 + 3);
  CConnection::Release(*(CConnection **)(*((_QWORD *)a2 + 3) + 64LL));
  *((_QWORD *)a2 + 3) = 0;
  v14 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 345, 1u);
  if ( (bidGblFlags & 2) != 0 && `CConnection::AddRef'::`7'::_bidPtrSA_030_568[0] )
    bidTraceW(
      `CConnection::AddRef'::`7'::_bidSrcFileA[0],
      581632,
      `CConnection::AddRef'::`7'::_bidPtrSA_030_568[0],
      (unsigned int)(v14 + 1));
  *(_QWORD *)(*((_QWORD *)this + 3) + 64LL) = this;
  *(_DWORD *)(*((_QWORD *)this + 3) + 788LL) = v5;
  if ( (*((_BYTE *)this + 416) & 1) != 0 )
  {
    v15 = CConnection::OpenSMUXSession(this, *((struct BATCHCTX **)this + 3), 0);
    v4 = v15;
    if ( v15 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_180262660[0], 2691081, (unsigned int)v15);
      }
      return v4;
    }
  }
  *((_WORD *)this + 654) = *((_WORD *)a2 + 654);
  *((_BYTE *)this + 1311) = *((_BYTE *)a2 + 1311);
  *((_QWORD *)this + 50) = *((_QWORD *)a2 + 50);
  *((_QWORD *)a2 + 50) = 0;
  *((_DWORD *)this + 102) = *((_DWORD *)a2 + 102);
  *((_DWORD *)this + 103) = *((_DWORD *)a2 + 103);
  *((_DWORD *)this + 106) = *((_DWORD *)a2 + 106);
  *((_DWORD *)this + 107) = *((_DWORD *)a2 + 107);
  *((_DWORD *)this + 109) = *((_DWORD *)a2 + 109);
  *((_DWORD *)this + 108) = *((_DWORD *)a2 + 108);
  *((_QWORD *)this + 61) = *((_QWORD *)a2 + 61);
  *((_QWORD *)a2 + 61) = 0;
  *((_QWORD *)this + 62) = *((_QWORD *)a2 + 62);
  *((_QWORD *)a2 + 62) = 0;
  *((_DWORD *)this + 126) = *((_DWORD *)a2 + 126);
  *((_DWORD *)a2 + 126) = 0;
  *((_WORD *)this + 656) = *((_WORD *)a2 + 656);
  *((_DWORD *)this + 344) = *((_DWORD *)a2 + 344);
  v16 = (_WORD *)((char *)this + 508);
  v17 = 269;
  do
  {
    if ( v17 == -2147483377 )
      break;
    v18 = *(_WORD *)((char *)v16 + a2 - this);
    if ( !v18 )
      break;
    *v16++ = v18;
    --v17;
  }
  while ( v17 );
  v19 = v16 - 1;
  if ( v17 )
    v19 = v16;
  *v19 = 0;
  v20 = (_WORD *)((char *)this + 1046);
  v21 = 129;
  do
  {
    if ( v21 == -2147483517 )
      break;
    v22 = *(_WORD *)((char *)v20 + a2 - this);
    if ( !v22 )
      break;
    *v20++ = v22;
    --v21;
  }
  while ( v21 );
  v23 = v20 - 1;
  if ( v21 )
    v23 = v20;
  *v23 = 0;
  v24 = (_OWORD *)((char *)a2 + 100);
  v25 = (_OWORD *)((char *)this + 100);
  if ( this == (CConnection *)-100LL )
    goto LABEL_45;
  if ( a2 == (struct CConnection *)-100LL )
  {
    memset_0(v25, 0, 0x100u);
LABEL_45:
    *_errno() = 22;
    _invalid_parameter_noinfo();
    goto LABEL_46;
  }
  do
  {
    *v25 = *v24;
    v25[1] = v24[1];
    v25[2] = v24[2];
    v25[3] = v24[3];
    v25[4] = v24[4];
    v25[5] = v24[5];
    v25[6] = v24[6];
    v25 += 8;
    *(v25 - 1) = v24[7];
    v24 += 8;
    --v13;
  }
  while ( v13 );
LABEL_46:
  v26 = (char *)this + 1328;
  v27 = *(_QWORD *)v26;
  v28 = (char *)a2 + 1328;
  if ( v26 != v28 )
  {
    v29 = *((_QWORD *)v28 + 1);
    if ( v29 )
    {
      v30 = *(_QWORD **)v28;
      v31 = **(_QWORD **)v28;
      v32 = *((_QWORD *)v26 + 1);
      if ( 0xAAAAAAAAAAAAAAALL - v32 < v29 )
        std::_Xlength_error("list too long");
      *((_QWORD *)v26 + 1) = v29 + v32;
      *((_QWORD *)v28 + 1) -= v29;
      v33 = *(_QWORD **)(v31 + 8);
      *v33 = v30;
      v34 = (_QWORD *)v30[1];
      *v34 = v27;
      v35 = *(_QWORD **)(v27 + 8);
      *v35 = v31;
      *(_QWORD *)(v27 + 8) = v34;
      v30[1] = v33;
      *(_QWORD *)(v31 + 8) = v35;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180191ea0  mov     [rsp+arg_10], rbx
0x180191ea5  push    rbp
0x180191ea6  push    rsi
0x180191ea7  push    rdi
0x180191ea8  push    r12
0x180191eaa  push    r13
0x180191eac  push    r14
0x180191eae  push    r15
0x180191eb0  sub     rsp, 40h
0x180191eb4  mov     rax, cs:__security_cookie
0x180191ebb  xor     rax, rsp
0x180191ebe  mov     [rsp+78h+var_40], rax
0x180191ec3  mov     rsi, rdx
0x180191ec6  mov     rdi, rcx
0x180191ec9  xor     r13d, r13d
0x180191ecc  mov     r12d, r13d
0x180191ecf  mov     r15d, r13d
0x180191ed2  mov     rcx, [rcx+18h]
0x180191ed6  test    rcx, rcx
0x180191ed9  jz      short loc_180191F0D
0x180191edb  mov     eax, 10h
0x180191ee0  xchg    eax, [rcx+20h]
0x180191ee3  mov     eax, r13d
0x180191ee6  xchg    eax, [rcx+24h]
0x180191ee9  mov     rdx, [rcx+40h]
0x180191eed  test    rdx, rdx
0x180191ef0  jz      short loc_180191EF9
0x180191ef2  mov     byte ptr [rdx+56Ah], 1
0x180191ef9  mov     rcx, [rdi+18h]; this
0x180191efd  mov     r15d, [rcx+314h]
0x180191f04  call    ?Release@BATCHCTX@@QEAAKXZ; BATCHCTX::Release(void)
0x180191f09  mov     [rdi+18h], r13
0x180191f0d  mov     ebp, 1
0x180191f12  test    [rdi+1A0h], bpl
0x180191f19  jz      short loc_180191F48
0x180191f1b  nop     dword ptr [rax+rax+00h]
0x180191f20  lea     rcx, [rdi+30h]; ListHead
0x180191f24  call    cs:__imp_InterlockedPopEntrySList
0x180191f2a  test    rax, rax
0x180191f2d  jz      short loc_180191F48
0x180191f2f  lea     rcx, [rax-10h]
0x180191f33  test    rcx, rcx
0x180191f36  jz      short loc_180191F48
0x180191f38  mov     rax, [rcx]
0x180191f3b  mov     edx, ebp
0x180191f3d  mov     rax, [rax]
0x180191f40  call    cs:__guard_dispatch_icall_fptr
0x180191f46  jmp     short loc_180191F20
0x180191f48  cmp     [rdi+10h], r12
0x180191f4c  jz      short loc_180191FC2
0x180191f4e  xor     bl, bl
0x180191f50  cmp     cs:?g_AllocatorInUse@@3W4AllocatorEnum@@A, r12d; AllocatorEnum g_AllocatorInUse
0x180191f57  jnz     short loc_180191F99
0x180191f59  mov     [rsp+78h+var_48], r13d
0x180191f5e  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x180191f65  mov     rax, [rcx]
0x180191f68  lea     rdx, [rsp+78h+var_48]
0x180191f6d  mov     rax, [rax+18h]
0x180191f71  call    cs:__guard_dispatch_icall_fptr
0x180191f77  cmp     [rsp+78h+var_48], r12d
0x180191f7c  jnz     short loc_180191F99
0x180191f7e  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x180191f85  mov     rax, [rcx]
0x180191f88  mov     rax, [rax+0C8h]
0x180191f8f  call    cs:__guard_dispatch_icall_fptr
0x180191f95  movzx   ebx, bpl
0x180191f99  mov     rcx, [rdi+10h]; this
0x180191f9d  call    SNIClose
0x180191fa2  mov     [rdi+10h], r13
0x180191fa6  test    bl, bl
0x180191fa8  jz      short loc_180191FC2
0x180191faa  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x180191fb1  mov     rax, [rcx]
0x180191fb4  mov     rax, [rax+0D0h]
0x180191fbb  call    cs:__guard_dispatch_icall_fptr
0x180191fc1  nop
0x180191fc2  mov     rcx, rdi; this
0x180191fc5  call    ?CleanupFeatureExtensions@CConnection@@AEAAXXZ; CConnection::CleanupFeatureExtensions(void)
0x180191fca  mov     rdx, [rdi+1E8h]
0x180191fd1  test    rdx, rdx
0x180191fd4  jz      short loc_180191FF5
0x180191fd6  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180191fdd  mov     rax, [rcx]
0x180191fe0  mov     rax, [rax+80h]
0x180191fe7  call    cs:__guard_dispatch_icall_fptr
0x180191fed  nop
0x180191fee  mov     [rdi+1E8h], r13
0x180191ff5  lea     rax, [rdi+570h]
0x180191ffc  mov     rbx, r13
0x180191fff  test    rax, rax
0x180192002  jz      short loc_180192018
0x180192004  mov     rbx, [rax]
0x180192007  lea     rcx, [rbx+20h]
0x18019200b  mov     rax, [rcx]
0x18019200e  mov     rax, [rax+8]
0x180192012  call    cs:__guard_dispatch_icall_fptr
0x180192018  mov     rax, [rsi+10h]
0x18019201c  mov     [rdi+10h], rax
0x180192020  mov     [rsi+10h], r13
0x180192024  mov     r8, rdi
0x180192027  mov     r14d, 2
0x18019202d  mov     edx, r14d
0x180192030  mov     rcx, [rdi+10h]
0x180192034  call    SNISetInfo
0x180192039  call    cs:__imp_GetTickCount
0x18019203f  mov     [rdi+578h], eax
0x180192045  mov     byte ptr [rdi+56Ah], 0
0x18019204c  mov     eax, [rdi+57Ch]
0x180192052  inc     eax
0x180192054  mov     [rdi+57Ch], eax
0x18019205a  test    rbx, rbx
0x18019205d  jz      short loc_180192071
0x18019205f  lea     rcx, [rbx+20h]
0x180192063  mov     rax, [rcx]
0x180192066  mov     rax, [rax+18h]
0x18019206a  call    cs:__guard_dispatch_icall_fptr
0x180192070  nop
0x180192071  mov     eax, [rsi+24h]
0x180192074  mov     [rdi+24h], eax
0x180192077  mov     eax, [rsi+20h]
0x18019207a  mov     [rdi+20h], eax
0x18019207d  mov     rax, [rsi+18h]
0x180192081  mov     [rdi+18h], rax
0x180192085  mov     rcx, [rsi+18h]
0x180192089  mov     rcx, [rcx+40h]; this
0x18019208d  call    ?Release@CConnection@@QEAAKXZ; CConnection::Release(void)
0x180192092  mov     [rsi+18h], r13
0x180192096  lock xadd [rdi+564h], ebp
0x18019209e  test    byte ptr cs:_bidGblFlags, 2
0x1801920a5  jz      short loc_1801920DE
0x1801920a7  mov     rax, cs:?_bidPtrSA_030_568@?6??AddRef@CConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `CConnection::AddRef(void)'::`7'::_bidPtrSA_030_568
0x1801920ae  test    rax, rax
0x1801920b1  jz      short loc_1801920DE
0x1801920b3  mov     [rsp+78h+var_50], rdi
0x1801920b8  mov     eax, [rdi+560h]
0x1801920be  mov     [rsp+78h+var_58], eax
0x1801920c2  lea     r9d, [rbp+1]
0x1801920c6  mov     r8, cs:?_bidPtrSA_030_568@?6??AddRef@CConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `CConnection::AddRef(void)'::`7'::_bidPtrSA_030_568
0x1801920cd  mov     edx, 8E000h
0x1801920d2  mov     rcx, cs:?_bidSrcFileA@?6??AddRef@CConnection@@QEAAKXZ@4REBDEB; char const * const `CConnection::AddRef(void)'::`7'::_bidSrcFileA
0x1801920d9  call    _bidTraceW
0x1801920de  mov     rax, [rdi+18h]
0x1801920e2  mov     [rax+40h], rdi
0x1801920e6  mov     rax, [rdi+18h]
0x1801920ea  mov     [rax+314h], r15d
0x1801920f1  test    byte ptr [rdi+1A0h], 1
0x1801920f8  jz      short loc_180192139
0x1801920fa  xor     r8d, r8d; void *
0x1801920fd  mov     rdx, [rdi+18h]; struct BATCHCTX *
0x180192101  mov     rcx, rdi; this
0x180192104  call    ?OpenSMUXSession@CConnection@@QEAAJPEAVBATCHCTX@@PEAX@Z; CConnection::OpenSMUXSession(BATCHCTX *,void *)
0x180192109  mov     r12d, eax
0x18019210c  test    eax, eax
0x18019210e  jns     short loc_180192139
0x180192110  test    byte ptr cs:_bidGblFlags, 2
0x180192117  jz      loc_18019239B
0x18019211d  lfence
0x180192120  mov     r8d, eax
0x180192123  mov     edx, 291009h
0x180192128  mov     rcx, cs:off_180262660; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\td"...
0x18019212f  call    _bidTraceHR
0x180192134  jmp     loc_18019239B
0x180192139  movzx   eax, word ptr [rsi+51Ch]
0x180192140  mov     [rdi+51Ch], ax
0x180192147  movzx   eax, byte ptr [rsi+51Fh]
0x18019214e  mov     [rdi+51Fh], al
0x180192154  mov     rax, [rsi+190h]
0x18019215b  mov     [rdi+190h], rax
0x180192162  mov     [rsi+190h], r13
0x180192169  mov     eax, [rsi+198h]
0x18019216f  mov     [rdi+198h], eax
0x180192175  mov     eax, [rsi+19Ch]
0x18019217b  mov     [rdi+19Ch], eax
0x180192181  mov     eax, [rsi+1A8h]
0x180192187  mov     [rdi+1A8h], eax
0x18019218d  mov     eax, [rsi+1ACh]
0x180192193  mov     [rdi+1ACh], eax
0x180192199  mov     eax, [rsi+1B4h]
0x18019219f  mov     [rdi+1B4h], eax
0x1801921a5  mov     eax, [rsi+1B0h]
0x1801921ab  mov     [rdi+1B0h], eax
0x1801921b1  mov     rax, [rsi+1E8h]
0x1801921b8  mov     [rdi+1E8h], rax
0x1801921bf  mov     [rsi+1E8h], r13
0x1801921c6  mov     rax, [rsi+1F0h]
0x1801921cd  mov     [rdi+1F0h], rax
0x1801921d4  mov     [rsi+1F0h], r13
0x1801921db  mov     eax, [rsi+1F8h]
0x1801921e1  mov     [rdi+1F8h], eax
0x1801921e7  mov     [rsi+1F8h], r13d
0x1801921ee  movzx   eax, word ptr [rsi+520h]
0x1801921f5  mov     [rdi+520h], ax
0x1801921fc  mov     eax, [rsi+560h]
0x180192202  mov     [rdi+560h], eax
0x180192208  lea     rcx, [rdi+1FCh]
0x18019220f  mov     edx, 10Dh
0x180192214  mov     r8, rsi
0x180192217  sub     r8, rcx
0x18019221a  nop     word ptr [rax+rax+00h]
0x180192220  lea     rax, [rdx+7FFFFEF1h]
0x180192227  test    rax, rax
0x18019222a  jz      short loc_180192247
0x18019222c  movzx   eax, word ptr [rcx+r8+1FCh]
0x180192235  test    ax, ax
0x180192238  jz      short loc_180192247
0x18019223a  mov     [rcx], ax
0x18019223d  add     rcx, 2
0x180192241  sub     rdx, 1
0x180192245  jnz     short loc_180192220
0x180192247  lea     rax, [rcx-2]
0x18019224b  test    rdx, rdx
0x18019224e  cmovnz  rax, rcx
0x180192252  mov     [rax], r13w
0x180192256  lea     rcx, [rdi+416h]
0x18019225d  mov     edx, 81h
0x180192262  mov     r8, rsi
0x180192265  sub     r8, rcx
0x180192268  nop     dword ptr [rax+rax+00000000h]
0x180192270  lea     rax, [rdx+7FFFFF7Dh]
0x180192277  test    rax, rax
0x18019227a  jz      short loc_180192297
0x18019227c  movzx   eax, word ptr [rcx+r8+416h]
0x180192285  test    ax, ax
0x180192288  jz      short loc_180192297
0x18019228a  mov     [rcx], ax
0x18019228d  add     rcx, 2
0x180192291  sub     rdx, 1
0x180192295  jnz     short loc_180192270
0x180192297  lea     rax, [rcx-2]
0x18019229b  test    rdx, rdx
0x18019229e  cmovnz  rax, rcx
0x1801922a2  mov     [rax], r13w
0x1801922a6  lea     rax, [rsi+64h]
0x1801922aa  lea     rcx, [rdi+64h]; void *
0x1801922ae  test    rcx, rcx
0x1801922b1  jz      short loc_180192321
0x1801922b3  test    rax, rax
0x1801922b6  jz      short loc_180192314
0x1801922b8  nop     dword ptr [rax+rax+00000000h]
0x1801922c0  movups  xmm0, xmmword ptr [rax]
0x1801922c3  movups  xmmword ptr [rcx], xmm0
0x1801922c6  movups  xmm1, xmmword ptr [rax+10h]
0x1801922ca  movups  xmmword ptr [rcx+10h], xmm1
0x1801922ce  movups  xmm0, xmmword ptr [rax+20h]
0x1801922d2  movups  xmmword ptr [rcx+20h], xmm0
0x1801922d6  movups  xmm1, xmmword ptr [rax+30h]
0x1801922da  movups  xmmword ptr [rcx+30h], xmm1
0x1801922de  movups  xmm0, xmmword ptr [rax+40h]
0x1801922e2  movups  xmmword ptr [rcx+40h], xmm0
0x1801922e6  movups  xmm1, xmmword ptr [rax+50h]
0x1801922ea  movups  xmmword ptr [rcx+50h], xmm1
0x1801922ee  movups  xmm0, xmmword ptr [rax+60h]
0x1801922f2  movups  xmmword ptr [rcx+60h], xmm0
0x1801922f6  lea     rcx, [rcx+80h]
0x1801922fd  movups  xmm1, xmmword ptr [rax+70h]
0x180192301  movups  xmmword ptr [rcx-10h], xmm1
0x180192305  lea     rax, [rax+80h]
0x18019230c  sub     r14, 1
0x180192310  jnz     short loc_1801922C0
0x180192312  jmp     short loc_180192333
0x180192314  xor     edx, edx; Val
0x180192316  mov     r8d, 100h; Size
0x18019231c  call    memset_0
0x180192321  call    cs:__imp__errno
0x180192327  mov     dword ptr [rax], 16h
0x18019232d  call    cs:__imp__invalid_parameter_noinfo
0x180192333  add     rdi, 530h
0x18019233a  mov     r9, [rdi]
0x18019233d  add     rsi, 530h
0x180192344  cmp     rdi, rsi
0x180192347  jz      short loc_18019239B
0x180192349  mov     rcx, [rsi+8]
0x18019234d  test    rcx, rcx
0x180192350  jz      short loc_18019239B
0x180192352  mov     r8, [rsi]
0x180192355  mov     r10, [r8]
0x180192358  mov     rdx, [rdi+8]
0x18019235c  mov     rax, 0AAAAAAAAAAAAAAAh
0x180192366  sub     rax, rdx
0x180192369  cmp     rax, rcx
0x18019236c  jb      short loc_1801923C3
0x18019236e  lea     rax, [rcx+rdx]
0x180192372  mov     [rdi+8], rax
0x180192376  sub     [rsi+8], rcx
0x18019237a  mov     rdx, [r10+8]
0x18019237e  mov     [rdx], r8
0x180192381  mov     rcx, [r8+8]
0x180192385  mov     [rcx], r9
0x180192388  mov     rax, [r9+8]
0x18019238c  mov     [rax], r10
0x18019238f  mov     [r9+8], rcx
0x180192393  mov     [r8+8], rdx
0x180192397  mov     [r10+8], rax
0x18019239b  mov     eax, r12d
0x18019239e  mov     rcx, [rsp+78h+var_40]
0x1801923a3  xor     rcx, rsp; StackCookie
0x1801923a6  call    __security_check_cookie
0x1801923ab  mov     rbx, [rsp+78h+arg_10]
0x1801923b3  add     rsp, 40h
0x1801923b7  pop     r15
  ... truncated ...
```

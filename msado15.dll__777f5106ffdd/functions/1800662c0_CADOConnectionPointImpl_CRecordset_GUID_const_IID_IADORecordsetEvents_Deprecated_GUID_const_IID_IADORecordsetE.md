# CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Advise(IUnknown *,ulong *)

- ea: `0x1800662c0`
- end: `0x18006650f`
- name: `?Advise@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents_Deprecated@@3U_GUID@@B$1?IID_IADORecordsetEventsVt_Deprecated@@3U3@B@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `591`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009240`
- `0x180011530`
- `0x180020e20`
- `0x180027790`
- `0x18003c5f0`
- `0x1800662c0`
- `0x18006c4c8`
- `0x1800c5198`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800663c5`
- `MSDART!MpHeapAlloc` at `0x1800663c5`
- `KERNEL32!GetCurrentThreadId` at `0x18006642d`
- `KERNEL32!GetCurrentThreadId` at `0x18006642d`

## pseudocode

```c
__int64 __fastcall CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Advise(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, __int128 *, __int64 *),
        unsigned int *a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // eax
  char v10; // r14
  __int64 v11; // rax
  __int64 v12; // rbx
  unsigned int v13; // eax
  __int64 v14; // rcx
  _BOOL8 v15; // r8
  unsigned int v16; // ebx
  int v18; // [rsp+20h] [rbp-60h] BYREF
  __int64 v19; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v20[32]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+50h] [rbp-30h]
  unsigned int v22; // [rsp+58h] [rbp-28h]
  __int128 v23; // [rsp+60h] [rbp-20h] BYREF

  v6 = (a1 - 152) & -(__int64)(a1 != 0);
  if ( v6 )
    v7 = v6 + 32;
  else
    v7 = 0;
  v21 = v7;
  CContext::Init((CContext *)v20);
  v19 = 0;
  if ( !a2 || !a3 )
  {
    v18 = -2147467261;
    goto LABEL_23;
  }
  *a3 = 0;
  v8 = *(_QWORD *)a1;
  v23 = 0;
  (*(void (__fastcall **)(__int64, __int128 *))(v8 + 80))(a1, &v23);
  if ( (int)(**a2)(a2, &v23, &v19) >= 0 )
  {
    v10 = 0;
  }
  else
  {
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v23);
    v9 = (**a2)(a2, &v23, &v19);
    v18 = v9;
    v10 = 1;
    if ( v9 < 0 )
    {
      if ( v9 == -2147467262 )
        v18 = -2147220990;
      goto LABEL_23;
    }
  }
  v11 = MpHeapAlloc(g_hHeapHandle, 10485760, 56);
  v12 = v11;
  if ( !v11 )
  {
    v18 = -2147024882;
    goto LABEL_21;
  }
  *(_DWORD *)(v11 + 4) = 0;
  *(_QWORD *)(v11 + 8) = 0;
  *(_QWORD *)(v11 + 16) = 0;
  *(_DWORD *)(v11 + 28) = 0;
  *(_QWORD *)(v11 + 32) = 0;
  *(_QWORD *)(v11 + 40) = 0;
  *(_QWORD *)(v11 + 48) = 0;
  *(_DWORD *)(v11 + 24) = -1;
  *(_BYTE *)v11 = v10;
  *(_QWORD *)(v11 + 8) = v19;
  CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::InitAsyncEvents(a1);
  *(_DWORD *)(v12 + 4) = GetCurrentThreadId();
  v13 = ATL::CComDynamicUnkArray::Add((ATL::CComDynamicUnkArray *)(a1 + 8), (struct IUnknown *)v12);
  *a3 = v13;
  if ( !v13 )
  {
    v18 = -2147220991;
    operator delete((void *)v12);
LABEL_21:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    goto LABEL_23;
  }
  v15 = (unsigned int)InlineIsEqualGUID(&IID_IADORecordsetEvents_Deprecated, &IID_IADORecordsetEvents_Deprecated)
     || (unsigned int)InlineIsEqualGUID(v14, &IID_IADOConnectionEvents_Deprecated);
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, _BOOL8))(*(_QWORD *)a1 + 64LL))(a1, v12, v15);
  if ( v18 < 0 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, *a3);
LABEL_23:
  CContext::Failed((CContext *)v20, &v18);
  v16 = v22;
  CContext::~CContext((CContext *)v20);
  return v16;
}

```

## disassembly

```asm
0x1800662c0  push    rbp
0x1800662c2  push    rbx
0x1800662c3  push    rsi
0x1800662c4  push    rdi
0x1800662c5  push    r14
0x1800662c7  mov     rbp, rsp
0x1800662ca  sub     rsp, 80h
0x1800662d1  mov     rax, cs:__security_cookie
0x1800662d8  xor     rax, rsp
0x1800662db  mov     [rbp+var_10], rax
0x1800662df  mov     rax, rcx
0x1800662e2  mov     rdi, rcx
0x1800662e5  add     rcx, 0FFFFFFFFFFFFFF68h
0x1800662ec  mov     rsi, r8
0x1800662ef  neg     rax
0x1800662f2  mov     rbx, rdx
0x1800662f5  sbb     rax, rax
0x1800662f8  and     rax, rcx
0x1800662fb  jz      short loc_180066303
0x1800662fd  add     rax, 20h ; ' '
0x180066301  jmp     short loc_180066305
0x180066303  xor     eax, eax
0x180066305  lea     rcx, [rbp+var_50]; this
0x180066309  mov     [rbp+var_30], rax
0x18006630d  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180066312  mov     [rbp+var_58], 0
0x18006631a  test    rbx, rbx
0x18006631d  jz      loc_1800664D2
0x180066323  test    rsi, rsi
0x180066326  jz      loc_1800664D2
0x18006632c  mov     dword ptr [rsi], 0
0x180066332  lea     rdx, [rbp+var_20]
0x180066336  mov     rax, [rdi]
0x180066339  xorps   xmm0, xmm0
0x18006633c  mov     rcx, rdi
0x18006633f  movups  [rbp+var_20], xmm0
0x180066343  mov     rax, [rax+50h]
0x180066347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006634c  mov     rax, [rbx]
0x18006634f  lea     r8, [rbp+var_58]
0x180066353  lea     rdx, [rbp+var_20]
0x180066357  mov     rcx, rbx
0x18006635a  mov     rax, [rax]
0x18006635d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066362  test    eax, eax
0x180066364  jns     short loc_1800663B0
0x180066366  mov     rax, [rdi]
0x180066369  lea     rdx, [rbp+var_20]
0x18006636d  mov     rcx, rdi
0x180066370  mov     rax, [rax+18h]
0x180066374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066379  mov     rax, [rbx]
0x18006637c  lea     r8, [rbp+var_58]
0x180066380  lea     rdx, [rbp+var_20]
0x180066384  mov     rcx, rbx
0x180066387  mov     rax, [rax]
0x18006638a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006638f  mov     [rbp+var_60], eax
0x180066392  mov     r14b, 1
0x180066395  test    eax, eax
0x180066397  jns     short loc_1800663B3
0x180066399  cmp     eax, 80004002h
0x18006639e  jnz     loc_1800664D9
0x1800663a4  mov     [rbp+var_60], 80040202h
0x1800663ab  jmp     loc_1800664D9
0x1800663b0  xor     r14b, r14b
0x1800663b3  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800663ba  mov     edx, 0A00000h
0x1800663bf  mov     r8d, 38h ; '8'
0x1800663c5  call    cs:__imp_MpHeapAlloc
0x1800663cc  nop     dword ptr [rax+rax+00h]
0x1800663d1  mov     rbx, rax
0x1800663d4  test    rax, rax
0x1800663d7  jz      loc_1800664B9
0x1800663dd  mov     dword ptr [rax+4], 0
0x1800663e4  mov     qword ptr [rax+8], 0
0x1800663ec  mov     qword ptr [rax+10h], 0
0x1800663f4  mov     dword ptr [rax+1Ch], 0
0x1800663fb  mov     qword ptr [rax+20h], 0
0x180066403  mov     qword ptr [rax+28h], 0
0x18006640b  mov     qword ptr [rax+30h], 0
0x180066413  mov     dword ptr [rax+18h], 0FFFFFFFFh
0x18006641a  mov     [rax], r14b
0x18006641d  mov     rcx, [rbp+var_58]
0x180066421  mov     [rax+8], rcx
0x180066425  mov     rcx, rdi
0x180066428  call    ?InitAsyncEvents@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAXXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::InitAsyncEvents(void)
0x18006642d  call    cs:__imp_GetCurrentThreadId
0x180066434  nop     dword ptr [rax+rax+00h]
0x180066439  lea     rcx, [rdi+8]; this
0x18006643d  mov     rdx, rbx; struct IUnknown *
0x180066440  mov     [rbx+4], eax
0x180066443  call    ?Add@CComDynamicUnkArray@ATL@@QEAAKPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::Add(IUnknown *)
0x180066448  mov     [rsi], eax
0x18006644a  test    eax, eax
0x18006644c  jnz     short loc_18006645F
0x18006644e  mov     [rbp+var_60], 80040201h
0x180066455  mov     rcx, rbx; void *
0x180066458  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006645d  jmp     short loc_1800664C0
0x18006645f  lea     rcx, IID_IADORecordsetEvents_Deprecated
0x180066466  mov     rdx, rcx
0x180066469  call    InlineIsEqualGUID
0x18006646e  test    eax, eax
0x180066470  jnz     short loc_180066487
0x180066472  lea     rdx, IID_IADOConnectionEvents_Deprecated
0x180066479  call    InlineIsEqualGUID
0x18006647e  test    eax, eax
0x180066480  jnz     short loc_180066487
0x180066482  xor     r8d, r8d
0x180066485  jmp     short loc_18006648D
0x180066487  mov     r8d, 1
0x18006648d  mov     rax, [rdi]
0x180066490  mov     rdx, rbx
0x180066493  mov     rcx, rdi
0x180066496  mov     rax, [rax+40h]
0x18006649a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006649f  mov     [rbp+var_60], eax
0x1800664a2  test    eax, eax
0x1800664a4  jns     short loc_1800664D9
0x1800664a6  mov     rax, [rdi]
0x1800664a9  mov     rcx, rdi
0x1800664ac  mov     edx, [rsi]
0x1800664ae  mov     rax, [rax+30h]
0x1800664b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800664b7  jmp     short loc_1800664D9
0x1800664b9  mov     [rbp+var_60], 8007000Eh
0x1800664c0  mov     rcx, [rbp+var_58]
0x1800664c4  mov     rax, [rcx]
0x1800664c7  mov     rax, [rax+10h]
0x1800664cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800664d0  jmp     short loc_1800664D9
0x1800664d2  mov     [rbp+var_60], 80004003h
0x1800664d9  lea     rdx, [rbp+var_60]; int *
0x1800664dd  lea     rcx, [rbp+var_50]; this
0x1800664e1  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800664e6  mov     ebx, [rbp+var_28]
0x1800664e9  lea     rcx, [rbp+var_50]; this
0x1800664ed  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x1800664f2  mov     eax, ebx
0x1800664f4  mov     rcx, [rbp+var_10]
0x1800664f8  xor     rcx, rsp; StackCookie
0x1800664fb  call    __security_check_cookie
0x180066500  add     rsp, 80h
0x180066507  pop     r14
0x180066509  pop     rdi
0x18006650a  pop     rsi
0x18006650b  pop     rbx
0x18006650c  pop     rbp
0x18006650d  retn
```

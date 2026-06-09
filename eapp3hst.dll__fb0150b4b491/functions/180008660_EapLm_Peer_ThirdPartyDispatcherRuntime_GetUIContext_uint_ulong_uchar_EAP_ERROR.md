# EapLm::Peer::ThirdPartyDispatcherRuntime::GetUIContext(uint,ulong *,uchar * *,_EAP_ERROR * *)

- ea: `0x180008660`
- end: `0x1800088ba`
- name: `?GetUIContext@ThirdPartyDispatcherRuntime@Peer@EapLm@@UEAAJIPEAKPEAPEAEPEAPEAU_EAP_ERROR@@@Z`
- size: `602`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherRuntime *__hidden this, unsigned int, unsigned int *, unsigned __int8 **, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000439c`
- `0x180005894`
- `0x1800058cc`
- `0x180005d30`
- `0x180008660`
- `0x18000bf94`
- `0x180012c10`
- `0x180015534`
- `0x18002f4a4`
- `0x18002f4c8`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800087d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800087d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008881`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008881`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherRuntime::GetUIContext(
        EapLm::Peer::ThirdPartyDispatcherRuntime *this,
        unsigned int a2,
        unsigned int *a3,
        unsigned __int8 **a4,
        struct _EAP_ERROR **a5)
{
  LPVOID *v5; // rbx
  unsigned int *v6; // rdi
  ReferenceCounted *v8; // rdx
  volatile signed __int32 *v9; // rsi
  unsigned int v10; // eax
  SIZE_T v11; // r15
  void *v12; // r12
  void *v13; // rax
  void *v14; // r14
  __int64 v15; // rdx
  bool v16; // r8
  int *v17; // r9
  const ATL::CAtlException *v19; // [rsp+28h] [rbp-80h] BYREF
  const EapHost::EapException *v20; // [rsp+30h] [rbp-78h] BYREF
  const Exception *v21; // [rsp+38h] [rbp-70h] BYREF
  void *Src; // [rsp+40h] [rbp-68h] BYREF
  SIZE_T cb; // [rsp+48h] [rbp-60h]
  ReferenceCounted *v24[2]; // [rsp+50h] [rbp-58h] BYREF
  _QWORD pExceptionObject[9]; // [rsp+60h] [rbp-48h] BYREF
  struct _EAP_ERROR *v26; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int *v27; // [rsp+C0h] [rbp+18h]
  unsigned __int8 **v28; // [rsp+C8h] [rbp+20h]

  v28 = a4;
  v27 = a3;
  v5 = (LPVOID *)a4;
  v6 = a3;
  LODWORD(v26) = 0;
  if ( !a2 || !a3 || !a4 || !a5 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    *a4 = 0;
    EapHost::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>(
      v24,
      (EapLm::Peer::ThirdPartyDispatcherRuntime *)((char *)this - 88),
      a2);
    v8 = v24[0];
    if ( !v24[0] )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_bb903cf33960336db7d560c47724160a_Traceguids, a2);
      EapHost::EapException::Throw(L"Session missing in the session table", L"GetUIContext", -2147024809);
    }
    if ( !*((_QWORD *)v24[0] + 8) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_bb903cf33960336db7d560c47724160a_Traceguids, a2);
      EapHost::EapException::Throw(L"Session(%d)'s innersession is missing", L"GetUIContext", -2147024809);
    }
    v9 = (volatile signed __int32 *)*((_QWORD *)v24[0] + 9);
    if ( v9 )
      _InterlockedIncrement(v9 + 2);
    Src = 0;
    cb = 0;
    (*(void (__fastcall **)(volatile signed __int32 *, _QWORD, void **))(*(_QWORD *)v9 + 72LL))(
      v9,
      *((_QWORD *)v8 + 8),
      &Src);
    v10 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(cb);
    *v6 = v10;
    if ( v10 )
    {
      v11 = cb;
      v12 = Src;
      v13 = CoTaskMemAlloc(cb);
      v14 = v13;
      if ( !v13 )
      {
        pExceptionObject[2] = 0;
        pExceptionObject[1] = "bad allocation";
        pExceptionObject[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)pExceptionObject;
      }
      memcpy_0(v13, v12, v11);
    }
    else
    {
      v14 = 0;
    }
    *v5 = v14;
    HeapAllocator::Free(Src);
    if ( v9 )
      ReferenceCounted::Release((ReferenceCounted *)v9);
    EapHost::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>::~SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>(
      v24,
      v15,
      v16);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v26) = -2147024882;
    *a5 = 0;
    v5 = (LPVOID *)v28;
    v6 = v27;
    goto LABEL_27;
  }
  catch ( const ATL::CAtlException *v19 )
  {
    LODWORD(v26) = *(_DWORD *)v19;
    *a5 = 0;
    v5 = (LPVOID *)v28;
    v6 = v27;
  }
  catch ( const EapHost::EapException *v20 )
  {
    EapHost::EapException2EapErrorOle(v20, (const struct EapHost::EapException *)a5, &v26, v17);
    v5 = (LPVOID *)v28;
    v6 = v27;
  }
  catch ( const Exception *v21 )
  {
    EapHost::Exception2EapErrorOle(v21, (const struct Exception *)a5, &v26, v17);
    v5 = (LPVOID *)v28;
    v6 = v27;
  }
  if ( (int)v26 < 0 )
  {
LABEL_27:
    CoTaskMemFree(*v5);
    *v5 = 0;
    *v6 = 0;
  }
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x180008660  mov     rax, rsp
0x180008663  mov     [rax+8], rbx
0x180008667  mov     [rax+20h], r9
0x18000866b  mov     [rax+18h], r8
0x18000866f  push    rsi
0x180008670  push    rdi
0x180008671  push    r12
0x180008673  push    r14
0x180008675  push    r15
0x180008677  sub     rsp, 80h
0x18000867e  mov     rbx, r9
0x180008681  mov     rdi, r8
0x180008684  mov     esi, edx
0x180008686  mov     dword ptr [rax+10h], 0
0x18000868d  test    edx, edx
0x18000868f  jz      loc_18000889D
0x180008695  test    r8, r8
0x180008698  jz      loc_18000889D
0x18000869e  test    rbx, rbx
0x1800086a1  jz      loc_18000889D
0x1800086a7  cmp     [rsp+0A8h+arg_20], 0
0x1800086b0  jz      loc_18000889D
0x1800086b6  mov     dword ptr [r8], 0
0x1800086bd  mov     qword ptr [r9], 0
0x1800086c4  lea     rdx, [rcx-58h]
0x1800086c8  mov     r8d, esi
0x1800086cb  lea     rcx, [rax-58h]
0x1800086cf  call    ??0?$SessionAccessor@VThirdPartyDispatcherSession@Peer@EapLm@@@EapHost@@QEAA@AEAV?$Cache@V?$SessionTableOperation@VThirdPartyDispatcherSession@Peer@EapLm@@@EapHost@@@@I_N@Z; EapHost::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>(Cache<EapHost::SessionTableOperation<EapLm::Peer::ThirdPartyDispatcherSession>> &,uint,bool)
0x1800086d4  nop
0x1800086d5  mov     rdx, [rsp+0A8h+var_58]
0x1800086da  test    rdx, rdx
0x1800086dd  jnz     short loc_180008729
0x1800086df  lea     rax, WPP_GLOBAL_Control
0x1800086e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086ed  cmp     rcx, rax
0x1800086f0  jz      short loc_180008710
0x1800086f2  test    byte ptr [rcx+1Ch], 1
0x1800086f6  jz      short loc_180008710
0x1800086f8  mov     edx, 10h
0x1800086fd  mov     r9d, esi
0x180008700  lea     r8, WPP_bb903cf33960336db7d560c47724160a_Traceguids
0x180008707  mov     rcx, [rcx+10h]
0x18000870b  call    WPP_SF_d
0x180008710  mov     r8d, 80070057h; int
0x180008716  lea     rdx, aGetuicontext; "GetUIContext"
0x18000871d  lea     rcx, aSessionMissing; "Session missing in the session table"
0x180008724  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180008729  cmp     qword ptr [rdx+40h], 0
0x18000872e  jnz     short loc_18000877A
0x180008730  lea     rax, WPP_GLOBAL_Control
0x180008737  mov     rcx, cs:WPP_GLOBAL_Control
0x18000873e  cmp     rcx, rax
0x180008741  jz      short loc_180008761
0x180008743  test    byte ptr [rcx+1Ch], 1
0x180008747  jz      short loc_180008761
0x180008749  mov     edx, 11h
0x18000874e  mov     r9d, esi
0x180008751  lea     r8, WPP_bb903cf33960336db7d560c47724160a_Traceguids
0x180008758  mov     rcx, [rcx+10h]
0x18000875c  call    WPP_SF_d
0x180008761  mov     r8d, 80070057h; int
0x180008767  lea     rdx, aGetuicontext; "GetUIContext"
0x18000876e  lea     rcx, aSessionDSInner; "Session(%d)'s innersession is missing"
0x180008775  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x18000877a  mov     rsi, [rdx+48h]
0x18000877e  mov     [rsp+0A8h+var_88], rsi
0x180008783  test    rsi, rsi
0x180008786  jz      short loc_18000878C
0x180008788  lock inc dword ptr [rsi+8]
0x18000878c  mov     [rsp+0A8h+Src], 0
0x180008795  mov     [rsp+0A8h+cb], 0
0x18000879e  mov     rax, [rsi]
0x1800087a1  lea     r8, [rsp+0A8h+Src]
0x1800087a6  mov     rdx, [rdx+40h]
0x1800087aa  mov     rcx, rsi
0x1800087ad  mov     rax, [rax+48h]
0x1800087b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087b6  mov     rcx, [rsp+0A8h+cb]
0x1800087bb  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x1800087c0  mov     [rdi], eax
0x1800087c2  test    eax, eax
0x1800087c4  jz      short loc_180008822
0x1800087c6  mov     r15, [rsp+0A8h+cb]
0x1800087cb  mov     r12, [rsp+0A8h+Src]
0x1800087d0  mov     rcx, r15; cb
0x1800087d3  call    cs:__imp_CoTaskMemAlloc
0x1800087d9  mov     r14, rax
0x1800087dc  test    rax, rax
0x1800087df  jz      short loc_1800087F1
0x1800087e1  mov     r8, r15; Size
0x1800087e4  mov     rdx, r12; Src
0x1800087e7  mov     rcx, rax; void *
0x1800087ea  call    memcpy_0
0x1800087ef  jmp     short loc_180008825
0x1800087f1  xorps   xmm0, xmm0
0x1800087f4  movups  [rsp+0A8h+var_40], xmm0
0x1800087f9  lea     rax, aBadAllocation; "bad allocation"
0x180008800  mov     qword ptr [rsp+0A8h+var_40], rax
0x180008805  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000880c  mov     [rsp+0A8h+pExceptionObject], rax
0x180008811  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180008818  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18000881d  call    _CxxThrowException_0
0x180008822  xor     r14d, r14d
0x180008825  mov     [rbx], r14
0x180008828  mov     rcx, [rsp+0A8h+Src]; void *
0x18000882d  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180008832  nop
0x180008833  test    rsi, rsi
0x180008836  jz      short loc_180008841
0x180008838  mov     rcx, rsi; this
0x18000883b  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180008840  nop
0x180008841  lea     rcx, [rsp+0A8h+var_58]
0x180008846  call    ??1?$SessionAccessor@VThirdPartyDispatcherSession@Peer@EapLm@@@EapHost@@QEAA@XZ; EapHost::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>::~SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>(void)
0x18000884b  nop
0x18000884c  jmp     short loc_180008874
0x18000884e  mov     rbx, [rsp+0A8h+arg_18]
0x180008856  mov     rdi, [rsp+0A8h+arg_10]
0x18000885e  jmp     short loc_18000887E
0x180008860  jmp     short loc_180008864
0x180008862  jmp     short $+2
0x180008864  mov     rbx, [rsp+0A8h+arg_18]
0x18000886c  mov     rdi, [rsp+0A8h+arg_10]
0x180008874  cmp     dword ptr [rsp+0A8h+arg_8], 0
0x18000887c  jge     short loc_180008894
0x18000887e  mov     rcx, [rbx]; pv
0x180008881  call    cs:__imp_CoTaskMemFree
0x180008887  mov     qword ptr [rbx], 0
0x18000888e  mov     dword ptr [rdi], 0
0x180008894  mov     eax, dword ptr [rsp+0A8h+arg_8]
0x18000889b  jmp     short loc_1800088A2
0x18000889d  mov     eax, 80004003h
0x1800088a2  mov     rbx, [rsp+0A8h+arg_0]
0x1800088aa  add     rsp, 80h
0x1800088b1  pop     r15
0x1800088b3  pop     r14
0x1800088b5  pop     r12
0x1800088b7  pop     rdi
0x1800088b8  pop     rsi
0x1800088b9  retn
```

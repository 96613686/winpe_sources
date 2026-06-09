# CMessageTree::Load(int,IMoniker *,IBindCtx *,ulong)

- ea: `0x180047850`
- end: `0x180047a60`
- name: `?Load@CMessageTree@@UEAAJHPEAUIMoniker@@PEAUIBindCtx@@K@Z`
- size: `528`
- prototype: `int(CMessageTree *__hidden this, int, struct IMoniker *, struct IBindCtx *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002098`
- `0x180005748`
- `0x18000737c`
- `0x1800204bc`
- `0x18002223c`
- `0x180034288`
- `0x180047850`
- `0x18004b2a8`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180047a40`
- `KERNEL32!LeaveCriticalSection` at `0x180047a40`
- `KERNEL32!EnterCriticalSection` at `0x18004789d`
- `KERNEL32!EnterCriticalSection` at `0x18004789d`
- `urlmon!RegisterBindStatusCallback` at `0x180047945`
- `urlmon!RegisterBindStatusCallback` at `0x180047945`
- `ole32!CreateBindCtx` at `0x1800478eb`
- `ole32!CreateBindCtx` at `0x1800478eb`

## pseudocode

```c
__int64 __fastcall CMessageTree::Load(CMessageTree *this, __int64 a2, struct IMoniker *a3, struct IBindCtx *a4)
{
  CMessageTree *v4; // rsi
  HRESULT InitNew; // ebx
  int v8; // r15d
  int v9; // eax
  int v10; // eax
  __int64 v12; // [rsp+90h] [rbp+40h] BYREF
  char v13; // [rsp+A0h] [rbp+50h] BYREF
  LPBC ppbc; // [rsp+A8h] [rbp+58h] BYREF

  ppbc = a4;
  v4 = (CMessageTree *)((char *)this - 56);
  CStackRefCount<CAsyncConn>::CStackRefCount<CAsyncConn>(&v13);
  v12 = 0;
  if ( !a3 )
  {
    InitNew = -2147024809;
    goto LABEL_26;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  v8 = *((_DWORD *)this + 36);
  InitNew = CMessageTree::_HrLoadInitNew(v4);
  if ( InitNew >= 0 )
  {
    if ( (v8 & 0x200) != 0 )
      *((_DWORD *)this + 36) |= 0x200u;
    ReplaceInterface<IOleClientSite>((char *)this + 168, a3);
    if ( ppbc )
    {
      ((void (__fastcall *)(LPBC))ppbc->lpVtbl->AddRef)(ppbc);
    }
    else
    {
      InitNew = CreateBindCtx(0, &ppbc);
      if ( InitNew < 0 )
        goto LABEL_23;
    }
    ReplaceInterface<IOleClientSite>((char *)this + 392, ppbc);
    InitNew = CMessageTree::SetRootMoniker(v4, a3);
    if ( InitNew < 0 )
      goto LABEL_23;
    InitNew = RegisterBindStatusCallback(
                ppbc,
                (IBindStatusCallback *)(((unsigned __int64)this + 32) & -(__int64)(v4 != 0)),
                0,
                0);
    if ( InitNew < 0 )
      goto LABEL_23;
    *((_DWORD *)this + 36) &= ~0x40u;
    *((_DWORD *)this + 36) |= 0x180u;
    v9 = (*(__int64 (__fastcall **)(_QWORD, LPBC, _QWORD, GUID *, __int64 *))(**((_QWORD **)this + 21) + 72LL))(
           *((_QWORD *)this + 21),
           ppbc,
           0,
           &GUID_0000000c_0000_0000_c000_000000000046,
           &v12);
    InitNew = v9;
    if ( v9 < 0 || v9 == 262632 )
      goto LABEL_23;
    if ( *((int *)this + 53) >= 0 )
    {
      if ( (*((_BYTE *)this + 144) & 0x40) != 0 )
        goto LABEL_21;
      v10 = (*(__int64 (__fastcall **)(char *, __int64, _QWORD))(*((_QWORD *)this + 4) + 72LL))((char *)this + 32, 2, 0);
      InitNew = v10;
      if ( v10 < 0 || v10 == 262632 )
        goto LABEL_23;
      if ( (*((_BYTE *)this + 144) & 0x40) != 0 )
      {
LABEL_21:
        if ( *((int *)this + 53) < 0 )
          InitNew = *((_DWORD *)this + 53);
        goto LABEL_23;
      }
      InitNew = 262632;
    }
    else
    {
      InitNew = *((_DWORD *)this + 53);
    }
  }
LABEL_23:
  OE_SafeReleaseAndNullPtr<IStream>(&v12);
  if ( InitNew < 0 )
    (*(void (__fastcall **)(char *, _QWORD, _QWORD))(*((_QWORD *)this + 4) + 56LL))(
      (char *)this + 32,
      (unsigned int)InitNew,
      0);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppbc);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
LABEL_26:
  CStackRefCount<CMessageTree>::~CStackRefCount<CMessageTree>(&v13);
  return (unsigned int)InitNew;
}

```

## disassembly

```asm
0x180047850  mov     [rsp-38h+ppbc], r9
0x180047855  push    rbp
0x180047856  push    rbx
0x180047857  push    rsi
0x180047858  push    rdi
0x180047859  push    r12
0x18004785b  push    r14
0x18004785d  push    r15
0x18004785f  mov     rbp, rsp
0x180047862  sub     rsp, 50h
0x180047866  lea     rsi, [rcx-38h]
0x18004786a  mov     rdi, rcx
0x18004786d  mov     rdx, rsi
0x180047870  lea     rcx, [rbp+arg_10]
0x180047874  mov     r14, r8
0x180047877  call    ??0?$CStackRefCount@VCAsyncConn@@@@QEAA@PEAVCAsyncConn@@@Z; CStackRefCount<CAsyncConn>::CStackRefCount<CAsyncConn>(CAsyncConn *)
0x18004787c  mov     [rbp+arg_0], 0
0x180047884  test    r14, r14
0x180047887  jnz     short loc_180047893
0x180047889  mov     ebx, 80070057h
0x18004788e  jmp     loc_180047A46
0x180047893  lea     r12, [rdi+160h]
0x18004789a  mov     rcx, r12; lpCriticalSection
0x18004789d  call    cs:__imp_EnterCriticalSection
0x1800478a3  mov     r15d, [rdi+90h]
0x1800478aa  mov     rcx, rsi; this
0x1800478ad  call    ?_HrLoadInitNew@CMessageTree@@AEAAJXZ; CMessageTree::_HrLoadInitNew(void)
0x1800478b2  mov     ebx, eax
0x1800478b4  test    eax, eax
0x1800478b6  js      loc_180047A12
0x1800478bc  mov     eax, 200h
0x1800478c1  test    eax, r15d
0x1800478c4  jz      short loc_1800478CC
0x1800478c6  or      [rdi+90h], eax
0x1800478cc  lea     r15, [rdi+0A8h]
0x1800478d3  mov     rdx, r14
0x1800478d6  mov     rcx, r15
0x1800478d9  call    ??$ReplaceInterface@UIOleClientSite@@@@YAXAEAPEAUIOleClientSite@@PEAU0@@Z; ReplaceInterface<IOleClientSite>(IOleClientSite * &,IOleClientSite *)
0x1800478de  mov     rcx, [rbp+ppbc]; reserved
0x1800478e2  test    rcx, rcx
0x1800478e5  jnz     short loc_1800478FD
0x1800478e7  lea     rdx, [rbp+ppbc]; ppbc
0x1800478eb  call    cs:__imp_CreateBindCtx
0x1800478f1  mov     ebx, eax
0x1800478f3  test    eax, eax
0x1800478f5  js      loc_180047A12
0x1800478fb  jmp     short loc_180047909
0x1800478fd  mov     rax, [rcx]
0x180047900  mov     rax, [rax+8]
0x180047904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047909  mov     rdx, [rbp+ppbc]
0x18004790d  lea     rcx, [rdi+188h]
0x180047914  call    ??$ReplaceInterface@UIOleClientSite@@@@YAXAEAPEAUIOleClientSite@@PEAU0@@Z; ReplaceInterface<IOleClientSite>(IOleClientSite * &,IOleClientSite *)
0x180047919  mov     rdx, r14; struct IMoniker *
0x18004791c  mov     rcx, rsi; this
0x18004791f  call    ?SetRootMoniker@CMessageTree@@QEAAJPEAUIMoniker@@@Z; CMessageTree::SetRootMoniker(IMoniker *)
0x180047924  mov     ebx, eax
0x180047926  test    eax, eax
0x180047928  js      loc_180047A12
0x18004792e  mov     rcx, [rbp+ppbc]; pBC
0x180047932  lea     r14, [rdi+20h]
0x180047936  neg     rsi
0x180047939  sbb     rdx, rdx
0x18004793c  xor     r9d, r9d; dwReserved
0x18004793f  and     rdx, r14; pBSCb
0x180047942  xor     r8d, r8d; ppBSCBPrev
0x180047945  call    cs:__imp_RegisterBindStatusCallback
0x18004794b  mov     ebx, eax
0x18004794d  test    eax, eax
0x18004794f  js      loc_180047A12
0x180047955  and     dword ptr [rdi+90h], 0FFFFFFBFh
0x18004795c  lea     rdx, [rbp+arg_0]
0x180047960  or      dword ptr [rdi+90h], 180h
0x18004796a  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x180047971  mov     rcx, [r15]
0x180047974  xor     r8d, r8d
0x180047977  mov     [rsp+50h+var_30], rdx
0x18004797c  mov     rdx, [rbp+ppbc]
0x180047980  mov     rax, [rcx]
0x180047983  mov     rax, [rax+48h]
0x180047987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004798c  bt      eax, 1Fh
0x180047990  mov     ebx, eax
0x180047992  jb      short loc_180047A12
0x180047994  mov     esi, 401E8h
0x180047999  cmp     eax, esi
0x18004799b  jz      short loc_180047A12
0x18004799d  mov     eax, [rdi+0D4h]
0x1800479a3  test    eax, eax
0x1800479a5  jns     short loc_1800479AB
0x1800479a7  mov     ebx, eax
0x1800479a9  jmp     short loc_180047A12
0x1800479ab  test    byte ptr [rdi+90h], 40h
0x1800479b2  jnz     short loc_180047A07
0x1800479b4  mov     rax, [rbp+arg_0]
0x1800479b8  lea     rcx, [rbp+var_20]
0x1800479bc  mov     [rbp+var_18], rax
0x1800479c0  xor     r9d, r9d
0x1800479c3  mov     rax, [r14]
0x1800479c6  xor     r8d, r8d
0x1800479c9  mov     [rsp+50h+var_30], rcx
0x1800479ce  mov     rcx, r14
0x1800479d1  mov     [rbp+var_20], 4
0x1800479d9  lea     edx, [r9+2]
0x1800479dd  mov     [rbp+var_10], 0
0x1800479e5  mov     rax, [rax+48h]
0x1800479e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800479ee  bt      eax, 1Fh
0x1800479f2  mov     ebx, eax
0x1800479f4  jb      short loc_180047A12
0x1800479f6  cmp     eax, esi
0x1800479f8  jz      short loc_180047A12
0x1800479fa  test    byte ptr [rdi+90h], 40h
0x180047a01  jnz     short loc_180047A07
0x180047a03  mov     ebx, esi
0x180047a05  jmp     short loc_180047A12
0x180047a07  mov     eax, [rdi+0D4h]
0x180047a0d  test    eax, eax
0x180047a0f  cmovs   ebx, eax
0x180047a12  lea     rcx, [rbp+arg_0]
0x180047a16  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x180047a1b  test    ebx, ebx
0x180047a1d  jns     short loc_180047A34
0x180047a1f  lea     rcx, [rdi+20h]
0x180047a23  xor     r8d, r8d
0x180047a26  mov     rax, [rcx]
0x180047a29  mov     edx, ebx
0x180047a2b  mov     rax, [rax+38h]
0x180047a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a34  lea     rcx, [rbp+ppbc]
0x180047a38  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180047a3d  mov     rcx, r12; lpCriticalSection
0x180047a40  call    cs:__imp_LeaveCriticalSection
0x180047a46  lea     rcx, [rbp+arg_10]
0x180047a4a  call    ??1?$CStackRefCount@VCMessageTree@@@@QEAA@XZ; CStackRefCount<CMessageTree>::~CStackRefCount<CMessageTree>(void)
0x180047a4f  mov     eax, ebx
0x180047a51  add     rsp, 50h
0x180047a55  pop     r15
0x180047a57  pop     r14
0x180047a59  pop     r12
0x180047a5b  pop     rdi
0x180047a5c  pop     rsi
0x180047a5d  pop     rbx
0x180047a5e  pop     rbp
0x180047a5f  retn
```

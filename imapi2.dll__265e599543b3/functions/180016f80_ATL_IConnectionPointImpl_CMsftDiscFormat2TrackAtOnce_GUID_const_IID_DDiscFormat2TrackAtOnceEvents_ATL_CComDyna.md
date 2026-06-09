# ATL::IConnectionPointImpl<CMsftDiscFormat2TrackAtOnce,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,ATL::CComDynamicUnkArray>::Advise(IUnknown *,ulong *)

- ea: `0x180016f80`
- end: `0x180017094`
- name: `?Advise@?$IConnectionPointImpl@VCMsftDiscFormat2TrackAtOnce@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180016e38`
- `0x180016f80`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180017016`
- `KERNEL32!EnterCriticalSection` at `0x180017016`
- `KERNEL32!LeaveCriticalSection` at `0x180017040`
- `KERNEL32!LeaveCriticalSection` at `0x180017040`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CMsftDiscFormat2TrackAtOnce,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,ATL::CComDynamicUnkArray>::Advise(
        __int64 *a1,
        __int64 (__fastcall ***a2)(_QWORD, __int128 *, struct IUnknown **),
        _DWORD *a3)
{
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v9; // rdi
  int v10; // eax
  int v11; // ebx
  struct IUnknown *v13; // [rsp+20h] [rbp-38h] BYREF
  __int128 v14; // [rsp+28h] [rbp-30h] BYREF

  v13 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 && a3 )
  {
    v6 = *a1;
    v14 = 0;
    (*(void (__fastcall **)(__int64 *, __int128 *))(v6 + 24))(a1, &v14);
    v7 = (**a2)(a2, &v14, &v13);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( v7 == -2147467262 )
        v8 = -2147220990;
    }
    else
    {
      v9 = (__int64)(a1 + 12);
      if ( !a1 )
        v9 = 120;
      EnterCriticalSection((LPCRITICAL_SECTION)v9);
      v10 = ATL::CComDynamicUnkArray::Add((ATL::CComDynamicUnkArray *)(a1 + 1), v13);
      *a3 = v10;
      v11 = v10;
      v8 = v10 == 0 ? 0x80040201 : 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)v9);
      if ( v11 )
        return v8;
      ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->Release)(v13);
    }
    *a3 = 0;
    return v8;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180016f80  mov     [rsp+arg_18], rbx
0x180016f85  push    rsi
0x180016f86  push    rdi
0x180016f87  push    r14
0x180016f89  sub     rsp, 40h
0x180016f8d  mov     rax, cs:__security_cookie
0x180016f94  xor     rax, rsp
0x180016f97  mov     [rsp+58h+var_20], rax
0x180016f9c  mov     [rsp+58h+var_38], 0
0x180016fa5  mov     r14, r8
0x180016fa8  mov     rdi, rdx
0x180016fab  mov     rbx, rcx
0x180016fae  test    r8, r8
0x180016fb1  jz      short loc_180016FBA
0x180016fb3  mov     dword ptr [r8], 0
0x180016fba  test    rdi, rdi
0x180016fbd  jz      loc_180017074
0x180016fc3  test    r14, r14
0x180016fc6  jz      loc_180017074
0x180016fcc  mov     rax, [rcx]
0x180016fcf  lea     rdx, [rsp+58h+var_30]
0x180016fd4  xorps   xmm0, xmm0
0x180016fd7  movups  [rsp+58h+var_30], xmm0
0x180016fdc  mov     rax, [rax+18h]
0x180016fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe5  mov     rax, [rdi]
0x180016fe8  lea     r8, [rsp+58h+var_38]
0x180016fed  lea     rdx, [rsp+58h+var_30]
0x180016ff2  mov     rcx, rdi
0x180016ff5  mov     rax, [rax]
0x180016ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ffd  mov     esi, eax
0x180016fff  test    eax, eax
0x180017001  js      short loc_18001705D
0x180017003  mov     eax, 78h ; 'x'
0x180017008  lea     rdi, [rbx+60h]
0x18001700c  test    rbx, rbx
0x18001700f  cmovz   rdi, rax
0x180017013  mov     rcx, rdi; lpCriticalSection
0x180017016  call    cs:__imp_EnterCriticalSection
0x18001701c  mov     rdx, [rsp+58h+var_38]; struct IUnknown *
0x180017021  lea     rcx, [rbx+8]; this
0x180017025  call    ?Add@CComDynamicUnkArray@ATL@@QEAAKPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::Add(IUnknown *)
0x18001702a  mov     edx, eax
0x18001702c  mov     [r14], eax
0x18001702f  neg     edx
0x180017031  mov     rcx, rdi; lpCriticalSection
0x180017034  mov     ebx, eax
0x180017036  sbb     esi, esi
0x180017038  not     esi
0x18001703a  and     esi, 80040201h
0x180017040  call    cs:__imp_LeaveCriticalSection
0x180017046  test    ebx, ebx
0x180017048  jnz     short loc_180017070
0x18001704a  mov     rcx, [rsp+58h+var_38]
0x18001704f  mov     rax, [rcx]
0x180017052  mov     rax, [rax+10h]
0x180017056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001705b  jmp     short loc_180017069
0x18001705d  cmp     eax, 80004002h
0x180017062  jnz     short loc_180017069
0x180017064  mov     esi, 80040202h
0x180017069  mov     dword ptr [r14], 0
0x180017070  mov     eax, esi
0x180017072  jmp     short loc_180017079
0x180017074  mov     eax, 80004003h
0x180017079  mov     rcx, [rsp+58h+var_20]
0x18001707e  xor     rcx, rsp; StackCookie
0x180017081  call    __security_check_cookie
0x180017086  mov     rbx, [rsp+58h+arg_18]
0x18001708b  add     rsp, 40h
0x18001708f  pop     r14
0x180017091  pop     rdi
0x180017092  pop     rsi
0x180017093  retn
```

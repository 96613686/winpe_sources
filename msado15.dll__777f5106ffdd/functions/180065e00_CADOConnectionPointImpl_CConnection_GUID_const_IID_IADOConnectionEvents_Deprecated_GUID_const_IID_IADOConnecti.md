# CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents_Deprecated,&_GUID const IID_IADOConnectionEventsVt_Deprecated>::Advise(IUnknown *,ulong *)

- ea: `0x180065e00`
- end: `0x18006604f`
- name: `?Advise@?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents_Deprecated@@3U_GUID@@B$1?IID_IADOConnectionEventsVt_Deprecated@@3U3@B@@UEAAJPEAUIUnknown@@PEAK@Z`
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
- `0x180065e00`
- `0x18006c4c8`
- `0x1800c5198`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180065f05`
- `MSDART!MpHeapAlloc` at `0x180065f05`
- `KERNEL32!GetCurrentThreadId` at `0x180065f6d`
- `KERNEL32!GetCurrentThreadId` at `0x180065f6d`

## pseudocode

```c
__int64 __fastcall CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents_Deprecated,&_GUID const IID_IADOConnectionEventsVt_Deprecated>::Advise(
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

  v6 = (a1 - 144) & -(__int64)(a1 != 0);
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
  v15 = (unsigned int)InlineIsEqualGUID(&IID_IADOConnectionEvents_Deprecated, &IID_IADORecordsetEvents_Deprecated)
     || (unsigned int)InlineIsEqualGUID(v14, v14);
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
0x180065e00  push    rbp
0x180065e02  push    rbx
0x180065e03  push    rsi
0x180065e04  push    rdi
0x180065e05  push    r14
0x180065e07  mov     rbp, rsp
0x180065e0a  sub     rsp, 80h
0x180065e11  mov     rax, cs:__security_cookie
0x180065e18  xor     rax, rsp
0x180065e1b  mov     [rbp+var_10], rax
0x180065e1f  mov     rax, rcx
0x180065e22  mov     rdi, rcx
0x180065e25  add     rcx, 0FFFFFFFFFFFFFF70h
0x180065e2c  mov     rsi, r8
0x180065e2f  neg     rax
0x180065e32  mov     rbx, rdx
0x180065e35  sbb     rax, rax
0x180065e38  and     rax, rcx
0x180065e3b  jz      short loc_180065E43
0x180065e3d  add     rax, 20h ; ' '
0x180065e41  jmp     short loc_180065E45
0x180065e43  xor     eax, eax
0x180065e45  lea     rcx, [rbp+var_50]; this
0x180065e49  mov     [rbp+var_30], rax
0x180065e4d  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180065e52  mov     [rbp+var_58], 0
0x180065e5a  test    rbx, rbx
0x180065e5d  jz      loc_180066012
0x180065e63  test    rsi, rsi
0x180065e66  jz      loc_180066012
0x180065e6c  mov     dword ptr [rsi], 0
0x180065e72  lea     rdx, [rbp+var_20]
0x180065e76  mov     rax, [rdi]
0x180065e79  xorps   xmm0, xmm0
0x180065e7c  mov     rcx, rdi
0x180065e7f  movups  [rbp+var_20], xmm0
0x180065e83  mov     rax, [rax+50h]
0x180065e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e8c  mov     rax, [rbx]
0x180065e8f  lea     r8, [rbp+var_58]
0x180065e93  lea     rdx, [rbp+var_20]
0x180065e97  mov     rcx, rbx
0x180065e9a  mov     rax, [rax]
0x180065e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ea2  test    eax, eax
0x180065ea4  jns     short loc_180065EF0
0x180065ea6  mov     rax, [rdi]
0x180065ea9  lea     rdx, [rbp+var_20]
0x180065ead  mov     rcx, rdi
0x180065eb0  mov     rax, [rax+18h]
0x180065eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065eb9  mov     rax, [rbx]
0x180065ebc  lea     r8, [rbp+var_58]
0x180065ec0  lea     rdx, [rbp+var_20]
0x180065ec4  mov     rcx, rbx
0x180065ec7  mov     rax, [rax]
0x180065eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ecf  mov     [rbp+var_60], eax
0x180065ed2  mov     r14b, 1
0x180065ed5  test    eax, eax
0x180065ed7  jns     short loc_180065EF3
0x180065ed9  cmp     eax, 80004002h
0x180065ede  jnz     loc_180066019
0x180065ee4  mov     [rbp+var_60], 80040202h
0x180065eeb  jmp     loc_180066019
0x180065ef0  xor     r14b, r14b
0x180065ef3  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180065efa  mov     edx, 0A00000h
0x180065eff  mov     r8d, 38h ; '8'
0x180065f05  call    cs:__imp_MpHeapAlloc
0x180065f0c  nop     dword ptr [rax+rax+00h]
0x180065f11  mov     rbx, rax
0x180065f14  test    rax, rax
0x180065f17  jz      loc_180065FF9
0x180065f1d  mov     dword ptr [rax+4], 0
0x180065f24  mov     qword ptr [rax+8], 0
0x180065f2c  mov     qword ptr [rax+10h], 0
0x180065f34  mov     dword ptr [rax+1Ch], 0
0x180065f3b  mov     qword ptr [rax+20h], 0
0x180065f43  mov     qword ptr [rax+28h], 0
0x180065f4b  mov     qword ptr [rax+30h], 0
0x180065f53  mov     dword ptr [rax+18h], 0FFFFFFFFh
0x180065f5a  mov     [rax], r14b
0x180065f5d  mov     rcx, [rbp+var_58]
0x180065f61  mov     [rax+8], rcx
0x180065f65  mov     rcx, rdi
0x180065f68  call    ?InitAsyncEvents@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAXXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::InitAsyncEvents(void)
0x180065f6d  call    cs:__imp_GetCurrentThreadId
0x180065f74  nop     dword ptr [rax+rax+00h]
0x180065f79  lea     rcx, [rdi+8]; this
0x180065f7d  mov     rdx, rbx; struct IUnknown *
0x180065f80  mov     [rbx+4], eax
0x180065f83  call    ?Add@CComDynamicUnkArray@ATL@@QEAAKPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::Add(IUnknown *)
0x180065f88  mov     [rsi], eax
0x180065f8a  test    eax, eax
0x180065f8c  jnz     short loc_180065F9F
0x180065f8e  mov     [rbp+var_60], 80040201h
0x180065f95  mov     rcx, rbx; void *
0x180065f98  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180065f9d  jmp     short loc_180066000
0x180065f9f  lea     rdx, IID_IADORecordsetEvents_Deprecated
0x180065fa6  lea     rcx, IID_IADOConnectionEvents_Deprecated
0x180065fad  call    InlineIsEqualGUID
0x180065fb2  test    eax, eax
0x180065fb4  jnz     short loc_180065FC7
0x180065fb6  mov     rdx, rcx
0x180065fb9  call    InlineIsEqualGUID
0x180065fbe  test    eax, eax
0x180065fc0  jnz     short loc_180065FC7
0x180065fc2  xor     r8d, r8d
0x180065fc5  jmp     short loc_180065FCD
0x180065fc7  mov     r8d, 1
0x180065fcd  mov     rax, [rdi]
0x180065fd0  mov     rdx, rbx
0x180065fd3  mov     rcx, rdi
0x180065fd6  mov     rax, [rax+40h]
0x180065fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065fdf  mov     [rbp+var_60], eax
0x180065fe2  test    eax, eax
0x180065fe4  jns     short loc_180066019
0x180065fe6  mov     rax, [rdi]
0x180065fe9  mov     rcx, rdi
0x180065fec  mov     edx, [rsi]
0x180065fee  mov     rax, [rax+30h]
0x180065ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ff7  jmp     short loc_180066019
0x180065ff9  mov     [rbp+var_60], 8007000Eh
0x180066000  mov     rcx, [rbp+var_58]
0x180066004  mov     rax, [rcx]
0x180066007  mov     rax, [rax+10h]
0x18006600b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066010  jmp     short loc_180066019
0x180066012  mov     [rbp+var_60], 80004003h
0x180066019  lea     rdx, [rbp+var_60]; int *
0x18006601d  lea     rcx, [rbp+var_50]; this
0x180066021  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180066026  mov     ebx, [rbp+var_28]
0x180066029  lea     rcx, [rbp+var_50]; this
0x18006602d  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x180066032  mov     eax, ebx
0x180066034  mov     rcx, [rbp+var_10]
0x180066038  xor     rcx, rsp; StackCookie
0x18006603b  call    __security_check_cookie
0x180066040  add     rsp, 80h
0x180066047  pop     r14
0x180066049  pop     rdi
0x18006604a  pop     rsi
0x18006604b  pop     rbx
0x18006604c  pop     rbp
0x18006604d  retn
```

# CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::Advise(IUnknown *,ulong *)

- ea: `0x180066060`
- end: `0x1800662b0`
- name: `?Advise@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `592`
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
- `0x180066060`
- `0x18006c4c8`
- `0x1800c5198`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180066162`
- `MSDART!MpHeapAlloc` at `0x180066162`
- `KERNEL32!GetCurrentThreadId` at `0x1800661ca`
- `KERNEL32!GetCurrentThreadId` at `0x1800661ca`

## pseudocode

```c
__int64 __fastcall CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::Advise(
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

  v6 = (a1 - 104) & -(__int64)(a1 != 0);
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
  v15 = (unsigned int)InlineIsEqualGUID(&IID_IADORecordsetEvents, &IID_IADORecordsetEvents_Deprecated)
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
0x180066060  push    rbp
0x180066062  push    rbx
0x180066063  push    rsi
0x180066064  push    rdi
0x180066065  push    r14
0x180066067  mov     rbp, rsp
0x18006606a  sub     rsp, 80h
0x180066071  mov     rax, cs:__security_cookie
0x180066078  xor     rax, rsp
0x18006607b  mov     [rbp+var_10], rax
0x18006607f  mov     rax, rcx
0x180066082  mov     rdi, rcx
0x180066085  add     rcx, 0FFFFFFFFFFFFFF98h
0x180066089  mov     rsi, r8
0x18006608c  neg     rax
0x18006608f  mov     rbx, rdx
0x180066092  sbb     rax, rax
0x180066095  and     rax, rcx
0x180066098  jz      short loc_1800660A0
0x18006609a  add     rax, 20h ; ' '
0x18006609e  jmp     short loc_1800660A2
0x1800660a0  xor     eax, eax
0x1800660a2  lea     rcx, [rbp+var_50]; this
0x1800660a6  mov     [rbp+var_30], rax
0x1800660aa  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800660af  mov     [rbp+var_58], 0
0x1800660b7  test    rbx, rbx
0x1800660ba  jz      loc_180066273
0x1800660c0  test    rsi, rsi
0x1800660c3  jz      loc_180066273
0x1800660c9  mov     dword ptr [rsi], 0
0x1800660cf  lea     rdx, [rbp+var_20]
0x1800660d3  mov     rax, [rdi]
0x1800660d6  xorps   xmm0, xmm0
0x1800660d9  mov     rcx, rdi
0x1800660dc  movups  [rbp+var_20], xmm0
0x1800660e0  mov     rax, [rax+50h]
0x1800660e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660e9  mov     rax, [rbx]
0x1800660ec  lea     r8, [rbp+var_58]
0x1800660f0  lea     rdx, [rbp+var_20]
0x1800660f4  mov     rcx, rbx
0x1800660f7  mov     rax, [rax]
0x1800660fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660ff  test    eax, eax
0x180066101  jns     short loc_18006614D
0x180066103  mov     rax, [rdi]
0x180066106  lea     rdx, [rbp+var_20]
0x18006610a  mov     rcx, rdi
0x18006610d  mov     rax, [rax+18h]
0x180066111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066116  mov     rax, [rbx]
0x180066119  lea     r8, [rbp+var_58]
0x18006611d  lea     rdx, [rbp+var_20]
0x180066121  mov     rcx, rbx
0x180066124  mov     rax, [rax]
0x180066127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006612c  mov     [rbp+var_60], eax
0x18006612f  mov     r14b, 1
0x180066132  test    eax, eax
0x180066134  jns     short loc_180066150
0x180066136  cmp     eax, 80004002h
0x18006613b  jnz     loc_18006627A
0x180066141  mov     [rbp+var_60], 80040202h
0x180066148  jmp     loc_18006627A
0x18006614d  xor     r14b, r14b
0x180066150  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180066157  mov     edx, 0A00000h
0x18006615c  mov     r8d, 38h ; '8'
0x180066162  call    cs:__imp_MpHeapAlloc
0x180066169  nop     dword ptr [rax+rax+00h]
0x18006616e  mov     rbx, rax
0x180066171  test    rax, rax
0x180066174  jz      loc_18006625A
0x18006617a  mov     dword ptr [rax+4], 0
0x180066181  mov     qword ptr [rax+8], 0
0x180066189  mov     qword ptr [rax+10h], 0
0x180066191  mov     dword ptr [rax+1Ch], 0
0x180066198  mov     qword ptr [rax+20h], 0
0x1800661a0  mov     qword ptr [rax+28h], 0
0x1800661a8  mov     qword ptr [rax+30h], 0
0x1800661b0  mov     dword ptr [rax+18h], 0FFFFFFFFh
0x1800661b7  mov     [rax], r14b
0x1800661ba  mov     rcx, [rbp+var_58]
0x1800661be  mov     [rax+8], rcx
0x1800661c2  mov     rcx, rdi
0x1800661c5  call    ?InitAsyncEvents@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAXXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::InitAsyncEvents(void)
0x1800661ca  call    cs:__imp_GetCurrentThreadId
0x1800661d1  nop     dword ptr [rax+rax+00h]
0x1800661d6  lea     rcx, [rdi+8]; this
0x1800661da  mov     rdx, rbx; struct IUnknown *
0x1800661dd  mov     [rbx+4], eax
0x1800661e0  call    ?Add@CComDynamicUnkArray@ATL@@QEAAKPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::Add(IUnknown *)
0x1800661e5  mov     [rsi], eax
0x1800661e7  test    eax, eax
0x1800661e9  jnz     short loc_1800661FC
0x1800661eb  mov     [rbp+var_60], 80040201h
0x1800661f2  mov     rcx, rbx; void *
0x1800661f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800661fa  jmp     short loc_180066261
0x1800661fc  lea     rdx, IID_IADORecordsetEvents_Deprecated
0x180066203  lea     rcx, IID_IADORecordsetEvents
0x18006620a  call    InlineIsEqualGUID
0x18006620f  test    eax, eax
0x180066211  jnz     short loc_180066228
0x180066213  lea     rdx, IID_IADOConnectionEvents_Deprecated
0x18006621a  call    InlineIsEqualGUID
0x18006621f  test    eax, eax
0x180066221  jnz     short loc_180066228
0x180066223  xor     r8d, r8d
0x180066226  jmp     short loc_18006622E
0x180066228  mov     r8d, 1
0x18006622e  mov     rax, [rdi]
0x180066231  mov     rdx, rbx
0x180066234  mov     rcx, rdi
0x180066237  mov     rax, [rax+40h]
0x18006623b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066240  mov     [rbp+var_60], eax
0x180066243  test    eax, eax
0x180066245  jns     short loc_18006627A
0x180066247  mov     rax, [rdi]
0x18006624a  mov     rcx, rdi
0x18006624d  mov     edx, [rsi]
0x18006624f  mov     rax, [rax+30h]
0x180066253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066258  jmp     short loc_18006627A
0x18006625a  mov     [rbp+var_60], 8007000Eh
0x180066261  mov     rcx, [rbp+var_58]
0x180066265  mov     rax, [rcx]
0x180066268  mov     rax, [rax+10h]
0x18006626c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066271  jmp     short loc_18006627A
0x180066273  mov     [rbp+var_60], 80004003h
0x18006627a  lea     rdx, [rbp+var_60]; int *
0x18006627e  lea     rcx, [rbp+var_50]; this
0x180066282  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180066287  mov     ebx, [rbp+var_28]
0x18006628a  lea     rcx, [rbp+var_50]; this
0x18006628e  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x180066293  mov     eax, ebx
0x180066295  mov     rcx, [rbp+var_10]
0x180066299  xor     rcx, rsp; StackCookie
0x18006629c  call    __security_check_cookie
0x1800662a1  add     rsp, 80h
0x1800662a8  pop     r14
0x1800662aa  pop     rdi
0x1800662ab  pop     rsi
0x1800662ac  pop     rbx
0x1800662ad  pop     rbp
0x1800662ae  retn
```

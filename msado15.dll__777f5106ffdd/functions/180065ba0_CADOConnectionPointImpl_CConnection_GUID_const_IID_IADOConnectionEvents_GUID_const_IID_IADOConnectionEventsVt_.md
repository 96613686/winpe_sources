# CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Advise(IUnknown *,ulong *)

- ea: `0x180065ba0`
- end: `0x180065df0`
- name: `?Advise@?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@B$1?IID_IADOConnectionEventsVt@@3U3@B@@UEAAJPEAUIUnknown@@PEAK@Z`
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
- `0x180065ba0`
- `0x18006c4c8`
- `0x1800c5198`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180065ca2`
- `MSDART!MpHeapAlloc` at `0x180065ca2`
- `KERNEL32!GetCurrentThreadId` at `0x180065d0a`
- `KERNEL32!GetCurrentThreadId` at `0x180065d0a`

## pseudocode

```c
__int64 __fastcall CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Advise(
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

  v6 = (a1 - 96) & -(__int64)(a1 != 0);
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
  v15 = (unsigned int)InlineIsEqualGUID(&IID_IADOConnectionEvents, &IID_IADORecordsetEvents_Deprecated)
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
0x180065ba0  push    rbp
0x180065ba2  push    rbx
0x180065ba3  push    rsi
0x180065ba4  push    rdi
0x180065ba5  push    r14
0x180065ba7  mov     rbp, rsp
0x180065baa  sub     rsp, 80h
0x180065bb1  mov     rax, cs:__security_cookie
0x180065bb8  xor     rax, rsp
0x180065bbb  mov     [rbp+var_10], rax
0x180065bbf  mov     rax, rcx
0x180065bc2  mov     rdi, rcx
0x180065bc5  add     rcx, 0FFFFFFFFFFFFFFA0h
0x180065bc9  mov     rsi, r8
0x180065bcc  neg     rax
0x180065bcf  mov     rbx, rdx
0x180065bd2  sbb     rax, rax
0x180065bd5  and     rax, rcx
0x180065bd8  jz      short loc_180065BE0
0x180065bda  add     rax, 20h ; ' '
0x180065bde  jmp     short loc_180065BE2
0x180065be0  xor     eax, eax
0x180065be2  lea     rcx, [rbp+var_50]; this
0x180065be6  mov     [rbp+var_30], rax
0x180065bea  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180065bef  mov     [rbp+var_58], 0
0x180065bf7  test    rbx, rbx
0x180065bfa  jz      loc_180065DB3
0x180065c00  test    rsi, rsi
0x180065c03  jz      loc_180065DB3
0x180065c09  mov     dword ptr [rsi], 0
0x180065c0f  lea     rdx, [rbp+var_20]
0x180065c13  mov     rax, [rdi]
0x180065c16  xorps   xmm0, xmm0
0x180065c19  mov     rcx, rdi
0x180065c1c  movups  [rbp+var_20], xmm0
0x180065c20  mov     rax, [rax+50h]
0x180065c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c29  mov     rax, [rbx]
0x180065c2c  lea     r8, [rbp+var_58]
0x180065c30  lea     rdx, [rbp+var_20]
0x180065c34  mov     rcx, rbx
0x180065c37  mov     rax, [rax]
0x180065c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c3f  test    eax, eax
0x180065c41  jns     short loc_180065C8D
0x180065c43  mov     rax, [rdi]
0x180065c46  lea     rdx, [rbp+var_20]
0x180065c4a  mov     rcx, rdi
0x180065c4d  mov     rax, [rax+18h]
0x180065c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c56  mov     rax, [rbx]
0x180065c59  lea     r8, [rbp+var_58]
0x180065c5d  lea     rdx, [rbp+var_20]
0x180065c61  mov     rcx, rbx
0x180065c64  mov     rax, [rax]
0x180065c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c6c  mov     [rbp+var_60], eax
0x180065c6f  mov     r14b, 1
0x180065c72  test    eax, eax
0x180065c74  jns     short loc_180065C90
0x180065c76  cmp     eax, 80004002h
0x180065c7b  jnz     loc_180065DBA
0x180065c81  mov     [rbp+var_60], 80040202h
0x180065c88  jmp     loc_180065DBA
0x180065c8d  xor     r14b, r14b
0x180065c90  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180065c97  mov     edx, 0A00000h
0x180065c9c  mov     r8d, 38h ; '8'
0x180065ca2  call    cs:__imp_MpHeapAlloc
0x180065ca9  nop     dword ptr [rax+rax+00h]
0x180065cae  mov     rbx, rax
0x180065cb1  test    rax, rax
0x180065cb4  jz      loc_180065D9A
0x180065cba  mov     dword ptr [rax+4], 0
0x180065cc1  mov     qword ptr [rax+8], 0
0x180065cc9  mov     qword ptr [rax+10h], 0
0x180065cd1  mov     dword ptr [rax+1Ch], 0
0x180065cd8  mov     qword ptr [rax+20h], 0
0x180065ce0  mov     qword ptr [rax+28h], 0
0x180065ce8  mov     qword ptr [rax+30h], 0
0x180065cf0  mov     dword ptr [rax+18h], 0FFFFFFFFh
0x180065cf7  mov     [rax], r14b
0x180065cfa  mov     rcx, [rbp+var_58]
0x180065cfe  mov     [rax+8], rcx
0x180065d02  mov     rcx, rdi
0x180065d05  call    ?InitAsyncEvents@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAXXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::InitAsyncEvents(void)
0x180065d0a  call    cs:__imp_GetCurrentThreadId
0x180065d11  nop     dword ptr [rax+rax+00h]
0x180065d16  lea     rcx, [rdi+8]; this
0x180065d1a  mov     rdx, rbx; struct IUnknown *
0x180065d1d  mov     [rbx+4], eax
0x180065d20  call    ?Add@CComDynamicUnkArray@ATL@@QEAAKPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::Add(IUnknown *)
0x180065d25  mov     [rsi], eax
0x180065d27  test    eax, eax
0x180065d29  jnz     short loc_180065D3C
0x180065d2b  mov     [rbp+var_60], 80040201h
0x180065d32  mov     rcx, rbx; void *
0x180065d35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180065d3a  jmp     short loc_180065DA1
0x180065d3c  lea     rdx, IID_IADORecordsetEvents_Deprecated
0x180065d43  lea     rcx, IID_IADOConnectionEvents
0x180065d4a  call    InlineIsEqualGUID
0x180065d4f  test    eax, eax
0x180065d51  jnz     short loc_180065D68
0x180065d53  lea     rdx, IID_IADOConnectionEvents_Deprecated
0x180065d5a  call    InlineIsEqualGUID
0x180065d5f  test    eax, eax
0x180065d61  jnz     short loc_180065D68
0x180065d63  xor     r8d, r8d
0x180065d66  jmp     short loc_180065D6E
0x180065d68  mov     r8d, 1
0x180065d6e  mov     rax, [rdi]
0x180065d71  mov     rdx, rbx
0x180065d74  mov     rcx, rdi
0x180065d77  mov     rax, [rax+40h]
0x180065d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d80  mov     [rbp+var_60], eax
0x180065d83  test    eax, eax
0x180065d85  jns     short loc_180065DBA
0x180065d87  mov     rax, [rdi]
0x180065d8a  mov     rcx, rdi
0x180065d8d  mov     edx, [rsi]
0x180065d8f  mov     rax, [rax+30h]
0x180065d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d98  jmp     short loc_180065DBA
0x180065d9a  mov     [rbp+var_60], 8007000Eh
0x180065da1  mov     rcx, [rbp+var_58]
0x180065da5  mov     rax, [rcx]
0x180065da8  mov     rax, [rax+10h]
0x180065dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065db1  jmp     short loc_180065DBA
0x180065db3  mov     [rbp+var_60], 80004003h
0x180065dba  lea     rdx, [rbp+var_60]; int *
0x180065dbe  lea     rcx, [rbp+var_50]; this
0x180065dc2  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180065dc7  mov     ebx, [rbp+var_28]
0x180065dca  lea     rcx, [rbp+var_50]; this
0x180065dce  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x180065dd3  mov     eax, ebx
0x180065dd5  mov     rcx, [rbp+var_10]
0x180065dd9  xor     rcx, rsp; StackCookie
0x180065ddc  call    __security_check_cookie
0x180065de1  add     rsp, 80h
0x180065de8  pop     r14
0x180065dea  pop     rdi
0x180065deb  pop     rsi
0x180065dec  pop     rbx
0x180065ded  pop     rbp
0x180065dee  retn
```

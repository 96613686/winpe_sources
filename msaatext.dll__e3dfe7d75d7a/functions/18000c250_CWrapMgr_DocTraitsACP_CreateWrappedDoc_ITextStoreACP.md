# CWrapMgr<DocTraitsACP>::_CreateWrappedDoc(ITextStoreACP * *)

- ea: `0x18000c250`
- end: `0x18000c497`
- name: `?_CreateWrappedDoc@?$CWrapMgr@VDocTraitsACP@@@@AEAAJPEAPEAUITextStoreACP@@@Z`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006fe0`

## callees

- `0x180001370`
- `0x1800026d0`
- `0x180005b8c`
- `0x18000a300`
- `0x18000c250`
- `0x180014010`

## string_xrefs

- `0x18000c468`: `CreateLocalInstance`
- `0x18000c416`: `dl-addToHead(), link still on some other list?`

## pseudocode

```c
__int64 __fastcall CWrapMgr<DocTraitsACP>::_CreateWrappedDoc(_QWORD *a1, __int64 **a2)
{
  __int64 *v4; // rax
  __int64 *v5; // rdi
  int v6; // ecx
  __int64 v7; // rbp
  __int64 v8; // rax
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  _QWORD *v11; // rbx
  _QWORD *v12; // rax
  __int64 result; // rax
  const unsigned __int16 *v14; // [rsp+20h] [rbp-68h]
  int v15; // [rsp+20h] [rbp-68h]
  unsigned __int16 *v16; // [rsp+28h] [rbp-60h]
  struct IUnknown *v17; // [rsp+30h] [rbp-58h]
  struct _GUID v18; // [rsp+40h] [rbp-48h] BYREF

  *a2 = 0;
  v4 = (__int64 *)operator new(0xB8u);
  v5 = v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 20) = 0;
    v4[11] = 0;
    v4[12] = 0;
    v4[6] = 0;
    v4[7] = 0;
    v4[8] = 0;
    v4[13] = 0;
    v4[14] = 0;
    *((_DWORD *)v4 + 34) = 0;
    v4[18] = 0;
    v4[19] = 0;
    v4[20] = 0;
    v4[21] = 0;
    *((_BYTE *)v4 + 176) = 0;
    *v4 = (__int64)&ATL::CComObject<CDocWrapACP>::`vftable'{for `ITextStoreACP'};
    v4[1] = (__int64)&ATL::CComObject<CDocWrapACP>::`vftable'{for `ITextStoreACPEx'};
    v4[2] = (__int64)&ATL::CComObject<CDocWrapACP>::`vftable'{for `IClonableWrapper'};
    v4[3] = (__int64)&ATL::CComObject<CDocWrapACP>::`vftable'{for `IInternalDocWrap'};
    v4[4] = (__int64)&ATL::CComObject<CDocWrapACP>::`vftable'{for `ICoCreateLocally'};
    v4[5] = (__int64)&ATL::CComObject<CDocWrapACP>::`vftable'{for `CVersionInfo'};
    v4[9] = (__int64)&ATL::CComObject<CDocWrapACP>::`vftable'{for `IServiceProvider'};
    _InterlockedAdd(&dword_180024B28, 1u);
    v6 = *((_DWORD *)v4 + 20);
    if ( v6 != 0x7FFFFFFF )
    {
      *((_DWORD *)v4 + 20) = v6 + 1;
      if ( v6 != 2147483646 )
        *((_DWORD *)v4 + 20) = v6;
    }
    (*(void (__fastcall **)(__int64 *))(*v4 + 8))(v4);
    v7 = a1[2];
    if ( v5[19] )
      InternalTrace(L"windows\\oleacc\\msaatext\\docwrap.cpp", 0x41Fu, 8u, 0, (int)v14, 0, (wchar_t *)&stru_18001DFA0);
    v5[19] = (__int64)a1;
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
    v8 = *v5;
    v5[20] = v7;
    (*(void (__fastcall **)(__int64 *))(v8 + 8))(v5);
    v18 = (struct _GUID)xmmword_18001E248;
    CVersionInfo::Add((CVersionInfo *)(v5 + 5), &v18, v9, v10, v14, v16, v17);
    SEHWrap_IUnknown<ITextStoreACP>::QueryInterface(v5 + 20, &GUID_a2de3bc2_3d8e_11d3_81a9_f753fbe61a00, v5 + 21);
    v11 = (_QWORD *)((unsigned __int64)(v5 + 11) & -(__int64)(v5 != 0));
    if ( v11[1] || *v11 )
      InternalTrace(
        L"windows\\oleacc\\inc\\list_dl.h",
        0x47u,
        8u,
        0,
        v15,
        0,
        (wchar_t *)L"dl-addToHead(), link still on some other list?");
    *v11 = 0;
    *(_QWORD *)(((unsigned __int64)(v5 + 11) & -(__int64)(v5 != 0)) + 8) = a1[7];
    v12 = (_QWORD *)a1[7];
    if ( v12 )
      *v12 = v11;
    else
      a1[8] = v11;
    a1[7] = v11;
    result = 0;
    *a2 = v5;
  }
  else
  {
    InternalTrace(
      L"windows\\oleacc\\msaatext\\docwrap.cpp",
      0x71u,
      3u,
      1,
      (int)v14,
      -2147024882,
      (wchar_t *)L"CreateLocalInstance");
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000c250  push    rbx
0x18000c252  push    rbp
0x18000c253  push    rsi
0x18000c254  push    rdi
0x18000c255  push    r14
0x18000c257  push    r15
0x18000c259  sub     rsp, 58h
0x18000c25d  mov     rsi, rcx
0x18000c260  xor     r15d, r15d
0x18000c263  mov     ecx, 0B8h; Size
0x18000c268  mov     [rdx], r15
0x18000c26b  mov     r14, rdx
0x18000c26e  mov     ebx, 8007000Eh
0x18000c273  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c278  mov     [rsp+88h+arg_8], rax
0x18000c280  mov     rdi, rax
0x18000c283  lea     r9d, [r15+1]
0x18000c287  test    rax, rax
0x18000c28a  jz      loc_18000C463
0x18000c290  mov     [rax+50h], r15d
0x18000c294  mov     [rax+58h], r15
0x18000c298  mov     [rax+60h], r15
0x18000c29c  mov     [rax+30h], r15
0x18000c2a0  mov     [rax+38h], r15
0x18000c2a4  mov     [rax+40h], r15
0x18000c2a8  mov     [rax+68h], r15
0x18000c2ac  mov     [rax+70h], r15
0x18000c2b0  mov     [rax+88h], r15d
0x18000c2b7  mov     [rax+90h], r15
0x18000c2be  mov     [rax+98h], r15
0x18000c2c5  mov     [rax+0A0h], r15
0x18000c2cc  mov     [rax+0A8h], r15
0x18000c2d3  mov     [rax+0B0h], r15b
0x18000c2da  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BITextStoreACP@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `ITextStoreACP'}
0x18000c2e1  mov     [rdi], rax
0x18000c2e4  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BITextStoreACPEx@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `ITextStoreACPEx'}
0x18000c2eb  mov     [rdi+8], rax
0x18000c2ef  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BIClonableWrapper@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `IClonableWrapper'}
0x18000c2f6  mov     [rdi+10h], rax
0x18000c2fa  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BIInternalDocWrap@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `IInternalDocWrap'}
0x18000c301  mov     [rdi+18h], rax
0x18000c305  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BICoCreateLocally@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `ICoCreateLocally'}
0x18000c30c  mov     [rdi+20h], rax
0x18000c310  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BCVersionInfo@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `CVersionInfo'}
0x18000c317  mov     [rdi+28h], rax
0x18000c31b  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BIServiceProvider@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `IServiceProvider'}
0x18000c322  mov     [rdi+48h], rax
0x18000c326  lock add cs:dword_180024B28, r9d
0x18000c32e  test    rdi, rdi
0x18000c331  jz      loc_18000C463
0x18000c337  mov     ecx, [rdi+50h]
0x18000c33a  cmp     ecx, 7FFFFFFFh
0x18000c340  jz      short loc_18000C353
0x18000c342  lea     eax, [rcx+1]
0x18000c345  mov     [rdi+50h], eax
0x18000c348  cmp     ecx, 7FFFFFFEh
0x18000c34e  jz      short loc_18000C353
0x18000c350  mov     [rdi+50h], ecx
0x18000c353  mov     rax, [rdi]
0x18000c356  mov     rcx, rdi
0x18000c359  mov     rax, [rax+8]
0x18000c35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c362  mov     rbp, [rsi+10h]
0x18000c366  cmp     [rdi+98h], r15
0x18000c36d  jz      short loc_18000C398
0x18000c36f  xor     r9d, r9d
0x18000c372  lea     rax, stru_18001DFA0
0x18000c379  mov     [rsp+88h+var_58], rax; struct IUnknown *
0x18000c37e  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x18000c385  mov     edx, 41Fh; Value
0x18000c38a  mov     dword ptr [rsp+88h+var_60], r15d; unsigned __int16 *
0x18000c38f  lea     r8d, [r9+8]
0x18000c393  call    InternalTrace
0x18000c398  mov     [rdi+98h], rsi
0x18000c39f  mov     rcx, rsi
0x18000c3a2  mov     rax, [rsi]
0x18000c3a5  mov     rax, [rax+8]
0x18000c3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3ae  mov     rax, [rdi]
0x18000c3b1  lea     rbx, [rdi+0A0h]
0x18000c3b8  mov     rcx, rdi
0x18000c3bb  mov     [rbx], rbp
0x18000c3be  mov     rax, [rax+8]
0x18000c3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3c7  movups  xmm0, cs:xmmword_18001E248
0x18000c3ce  lea     rcx, [rdi+28h]; this
0x18000c3d2  lea     rdx, [rsp+88h+var_48]; struct _GUID
0x18000c3d7  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x18000c3dd  call    ?Add@CVersionInfo@@QEAAXU_GUID@@KKPEBG1PEAUIUnknown@@@Z; CVersionInfo::Add(_GUID,ulong,ulong,ushort const *,ushort const *,IUnknown *)
0x18000c3e2  lea     r8, [rdi+0A8h]
0x18000c3e9  mov     rcx, rbx
0x18000c3ec  lea     rdx, _GUID_a2de3bc2_3d8e_11d3_81a9_f753fbe61a00
0x18000c3f3  call    ?QueryInterface@?$SEHWrap_IUnknown@UITextStoreACP@@@@QEAAJAEBU_GUID@@PEAPEAX@Z; SEHWrap_IUnknown<ITextStoreACP>::QueryInterface(_GUID const &,void * *)
0x18000c3f8  mov     rax, rdi
0x18000c3fb  lea     rcx, [rdi+58h]
0x18000c3ff  neg     rax
0x18000c402  sbb     rbx, rbx
0x18000c405  and     rbx, rcx
0x18000c408  cmp     [rbx+8], r15
0x18000c40c  jnz     short loc_18000C413
0x18000c40e  cmp     [rbx], r15
0x18000c411  jz      short loc_18000C43B
0x18000c413  xor     r9d, r9d
0x18000c416  lea     rax, aDlAddtoheadLin; "dl-addToHead(), link still on some othe"...
0x18000c41d  mov     [rsp+88h+var_58], rax; __int64
0x18000c422  lea     rcx, aWindowsOleaccI; "windows\\oleacc\\inc\\list_dl.h"
0x18000c429  mov     dword ptr [rsp+88h+var_60], r15d; int
0x18000c42e  lea     edx, [r9+47h]; Value
0x18000c432  lea     r8d, [r9+8]
0x18000c436  call    InternalTrace
0x18000c43b  mov     [rbx], r15
0x18000c43e  mov     rax, [rsi+38h]
0x18000c442  mov     [rbx+8], rax
0x18000c446  mov     rax, [rsi+38h]
0x18000c44a  test    rax, rax
0x18000c44d  jz      short loc_18000C454
0x18000c44f  mov     [rax], rbx
0x18000c452  jmp     short loc_18000C458
0x18000c454  mov     [rsi+40h], rbx
0x18000c458  mov     [rsi+38h], rbx
0x18000c45c  xor     eax, eax
0x18000c45e  mov     [r14], rdi
0x18000c461  jmp     short loc_18000C48A
0x18000c463  mov     edx, 71h ; 'q'; Value
0x18000c468  lea     rcx, aCreatelocalins; "CreateLocalInstance"
0x18000c46f  mov     [rsp+88h+var_58], rcx; __int64
0x18000c474  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x18000c47b  mov     dword ptr [rsp+88h+var_60], ebx; int
0x18000c47f  lea     r8d, [rdx-6Eh]
0x18000c483  call    InternalTrace
0x18000c488  mov     eax, ebx
0x18000c48a  add     rsp, 58h
0x18000c48e  pop     r15
0x18000c490  pop     r14
0x18000c492  pop     rdi
0x18000c493  pop     rsi
0x18000c494  pop     rbp
0x18000c495  pop     rbx
0x18000c496  retn
```

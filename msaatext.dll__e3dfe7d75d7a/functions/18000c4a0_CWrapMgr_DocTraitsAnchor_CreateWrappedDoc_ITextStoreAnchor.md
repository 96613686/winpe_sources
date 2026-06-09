# CWrapMgr<DocTraitsAnchor>::_CreateWrappedDoc(ITextStoreAnchor * *)

- ea: `0x18000c4a0`
- end: `0x18000c703`
- name: `?_CreateWrappedDoc@?$CWrapMgr@VDocTraitsAnchor@@@@AEAAJPEAPEAUITextStoreAnchor@@@Z`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006ff0`

## callees

- `0x180001370`
- `0x1800026d0`
- `0x180005b8c`
- `0x18000a300`
- `0x18000c4a0`
- `0x180014010`

## string_xrefs

- `0x18000c6d4`: `CreateLocalInstance`
- `0x18000c682`: `dl-addToHead(), link still on some other list?`

## pseudocode

```c
__int64 __fastcall CWrapMgr<DocTraitsAnchor>::_CreateWrappedDoc(_QWORD *a1, __int64 **a2)
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
  v4 = (__int64 *)operator new(0xD8u);
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
    v4[23] = 0;
    v4[24] = 0;
    v4[25] = 0;
    v4[26] = 0;
    *v4 = (__int64)&ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ITextStoreAnchor'};
    v4[1] = (__int64)&ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ITextStoreAnchorEx'};
    v4[2] = (__int64)&ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IClonableWrapper'};
    v4[3] = (__int64)&ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IInternalDocWrap'};
    v4[4] = (__int64)&ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ICoCreateLocally'};
    v4[5] = (__int64)&ATL::CComObject<CDocWrapAnchor>::`vftable'{for `CVersionInfo'};
    v4[9] = (__int64)&ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IServiceProvider'};
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
    SEHWrap_IUnknown<ITextStoreACP>::QueryInterface(v5 + 20, &GUID_a2de3bc1_3d8e_11d3_81a9_f753fbe61a00, v5 + 21);
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
0x18000c4a0  push    rbx
0x18000c4a2  push    rbp
0x18000c4a3  push    rsi
0x18000c4a4  push    rdi
0x18000c4a5  push    r14
0x18000c4a7  push    r15
0x18000c4a9  sub     rsp, 58h
0x18000c4ad  mov     rsi, rcx
0x18000c4b0  xor     r15d, r15d
0x18000c4b3  mov     ecx, 0D8h; Size
0x18000c4b8  mov     [rdx], r15
0x18000c4bb  mov     r14, rdx
0x18000c4be  mov     ebx, 8007000Eh
0x18000c4c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c4c8  mov     [rsp+88h+arg_8], rax
0x18000c4d0  mov     rdi, rax
0x18000c4d3  lea     r9d, [r15+1]
0x18000c4d7  test    rax, rax
0x18000c4da  jz      loc_18000C6CF
0x18000c4e0  mov     [rax+50h], r15d
0x18000c4e4  mov     [rax+58h], r15
0x18000c4e8  mov     [rax+60h], r15
0x18000c4ec  mov     [rax+30h], r15
0x18000c4f0  mov     [rax+38h], r15
0x18000c4f4  mov     [rax+40h], r15
0x18000c4f8  mov     [rax+68h], r15
0x18000c4fc  mov     [rax+70h], r15
0x18000c500  mov     [rax+88h], r15d
0x18000c507  mov     [rax+90h], r15
0x18000c50e  mov     [rax+98h], r15
0x18000c515  mov     [rax+0A0h], r15
0x18000c51c  mov     [rax+0A8h], r15
0x18000c523  mov     [rax+0B0h], r15b
0x18000c52a  mov     [rax+0B8h], r15
0x18000c531  mov     [rax+0C0h], r15
0x18000c538  mov     [rax+0C8h], r15
0x18000c53f  mov     [rax+0D0h], r15
0x18000c546  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BITextStoreAnchor@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ITextStoreAnchor'}
0x18000c54d  mov     [rdi], rax
0x18000c550  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BITextStoreAnchorEx@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ITextStoreAnchorEx'}
0x18000c557  mov     [rdi+8], rax
0x18000c55b  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BIClonableWrapper@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IClonableWrapper'}
0x18000c562  mov     [rdi+10h], rax
0x18000c566  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BIInternalDocWrap@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IInternalDocWrap'}
0x18000c56d  mov     [rdi+18h], rax
0x18000c571  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BICoCreateLocally@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ICoCreateLocally'}
0x18000c578  mov     [rdi+20h], rax
0x18000c57c  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BCVersionInfo@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `CVersionInfo'}
0x18000c583  mov     [rdi+28h], rax
0x18000c587  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BIServiceProvider@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IServiceProvider'}
0x18000c58e  mov     [rdi+48h], rax
0x18000c592  lock add cs:dword_180024B28, r9d
0x18000c59a  test    rdi, rdi
0x18000c59d  jz      loc_18000C6CF
0x18000c5a3  mov     ecx, [rdi+50h]
0x18000c5a6  cmp     ecx, 7FFFFFFFh
0x18000c5ac  jz      short loc_18000C5BF
0x18000c5ae  lea     eax, [rcx+1]
0x18000c5b1  mov     [rdi+50h], eax
0x18000c5b4  cmp     ecx, 7FFFFFFEh
0x18000c5ba  jz      short loc_18000C5BF
0x18000c5bc  mov     [rdi+50h], ecx
0x18000c5bf  mov     rax, [rdi]
0x18000c5c2  mov     rcx, rdi
0x18000c5c5  mov     rax, [rax+8]
0x18000c5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5ce  mov     rbp, [rsi+10h]
0x18000c5d2  cmp     [rdi+98h], r15
0x18000c5d9  jz      short loc_18000C604
0x18000c5db  xor     r9d, r9d
0x18000c5de  lea     rax, stru_18001DFA0
0x18000c5e5  mov     [rsp+88h+var_58], rax; struct IUnknown *
0x18000c5ea  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x18000c5f1  mov     edx, 41Fh; Value
0x18000c5f6  mov     dword ptr [rsp+88h+var_60], r15d; unsigned __int16 *
0x18000c5fb  lea     r8d, [r9+8]
0x18000c5ff  call    InternalTrace
0x18000c604  mov     [rdi+98h], rsi
0x18000c60b  mov     rcx, rsi
0x18000c60e  mov     rax, [rsi]
0x18000c611  mov     rax, [rax+8]
0x18000c615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c61a  mov     rax, [rdi]
0x18000c61d  lea     rbx, [rdi+0A0h]
0x18000c624  mov     rcx, rdi
0x18000c627  mov     [rbx], rbp
0x18000c62a  mov     rax, [rax+8]
0x18000c62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c633  movups  xmm0, cs:xmmword_18001E248
0x18000c63a  lea     rcx, [rdi+28h]; this
0x18000c63e  lea     rdx, [rsp+88h+var_48]; struct _GUID
0x18000c643  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x18000c649  call    ?Add@CVersionInfo@@QEAAXU_GUID@@KKPEBG1PEAUIUnknown@@@Z; CVersionInfo::Add(_GUID,ulong,ulong,ushort const *,ushort const *,IUnknown *)
0x18000c64e  lea     r8, [rdi+0A8h]
0x18000c655  mov     rcx, rbx
0x18000c658  lea     rdx, _GUID_a2de3bc1_3d8e_11d3_81a9_f753fbe61a00
0x18000c65f  call    ?QueryInterface@?$SEHWrap_IUnknown@UITextStoreACP@@@@QEAAJAEBU_GUID@@PEAPEAX@Z; SEHWrap_IUnknown<ITextStoreACP>::QueryInterface(_GUID const &,void * *)
0x18000c664  mov     rax, rdi
0x18000c667  lea     rcx, [rdi+58h]
0x18000c66b  neg     rax
0x18000c66e  sbb     rbx, rbx
0x18000c671  and     rbx, rcx
0x18000c674  cmp     [rbx+8], r15
0x18000c678  jnz     short loc_18000C67F
0x18000c67a  cmp     [rbx], r15
0x18000c67d  jz      short loc_18000C6A7
0x18000c67f  xor     r9d, r9d
0x18000c682  lea     rax, aDlAddtoheadLin; "dl-addToHead(), link still on some othe"...
0x18000c689  mov     [rsp+88h+var_58], rax; __int64
0x18000c68e  lea     rcx, aWindowsOleaccI; "windows\\oleacc\\inc\\list_dl.h"
0x18000c695  mov     dword ptr [rsp+88h+var_60], r15d; int
0x18000c69a  lea     edx, [r9+47h]; Value
0x18000c69e  lea     r8d, [r9+8]
0x18000c6a2  call    InternalTrace
0x18000c6a7  mov     [rbx], r15
0x18000c6aa  mov     rax, [rsi+38h]
0x18000c6ae  mov     [rbx+8], rax
0x18000c6b2  mov     rax, [rsi+38h]
0x18000c6b6  test    rax, rax
0x18000c6b9  jz      short loc_18000C6C0
0x18000c6bb  mov     [rax], rbx
0x18000c6be  jmp     short loc_18000C6C4
0x18000c6c0  mov     [rsi+40h], rbx
0x18000c6c4  mov     [rsi+38h], rbx
0x18000c6c8  xor     eax, eax
0x18000c6ca  mov     [r14], rdi
0x18000c6cd  jmp     short loc_18000C6F6
0x18000c6cf  mov     edx, 71h ; 'q'; Value
0x18000c6d4  lea     rcx, aCreatelocalins; "CreateLocalInstance"
0x18000c6db  mov     [rsp+88h+var_58], rcx; __int64
0x18000c6e0  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x18000c6e7  mov     dword ptr [rsp+88h+var_60], ebx; int
0x18000c6eb  lea     r8d, [rdx-6Eh]
0x18000c6ef  call    InternalTrace
0x18000c6f4  mov     eax, ebx
0x18000c6f6  add     rsp, 58h
0x18000c6fa  pop     r15
0x18000c6fc  pop     r14
0x18000c6fe  pop     rdi
0x18000c6ff  pop     rsi
0x18000c700  pop     rbp
0x18000c701  pop     rbx
0x18000c702  retn
```

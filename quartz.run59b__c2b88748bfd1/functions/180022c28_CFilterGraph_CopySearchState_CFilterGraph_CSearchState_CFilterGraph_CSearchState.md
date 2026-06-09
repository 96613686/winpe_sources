# CFilterGraph::CopySearchState(CFilterGraph::CSearchState &,CFilterGraph::CSearchState &)

- ea: `0x180022c28`
- end: `0x18002313d`
- name: `?CopySearchState@CFilterGraph@@AEAAXAEAVCSearchState@1@0@Z`
- size: `1301`
- prototype: `void(CFilterGraph *__hidden this, struct CFilterGraph::CSearchState *, struct CFilterGraph::CSearchState *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x180029d8c`
- `0x18006b9a8`

## callees

- `0x1800078b0`
- `0x18000aa30`
- `0x1800135b0`
- `0x1800197c0`
- `0x180022c28`
- `0x180038458`
- `0x180038498`
- `0x1800384a4`
- `0x1800388a0`
- `0x180039250`
- `0x18006c324`
- `0x18006d060`
- `0x180139f68`
- `0x18015e010`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180022fba`
- `KERNEL32!lstrlenW` at `0x180022fba`
- `ole32!CoTaskMemFree` at `0x180022d15`
- `ole32!CoTaskMemFree` at `0x180022d2a`
- `ole32!CoTaskMemFree` at `0x180022d70`
- `ole32!CoTaskMemFree` at `0x180022d15`
- `ole32!CoTaskMemFree` at `0x180022d2a`
- `ole32!CoTaskMemFree` at `0x180022d70`

## pseudocode

```c
void __fastcall CFilterGraph::CopySearchState(
        CFilterGraph *this,
        struct __POSITION **a2,
        struct CFilterGraph::CSearchState *a3)
{
  struct __POSITION *v3; // rbx
  __int64 v5; // r14
  CBaseList *v6; // rcx
  _QWORD *v7; // rax
  CFilterGraph **v8; // r9
  struct __POSITION **v9; // rbx
  struct __POSITION *v10; // rax
  _QWORD *NextI; // rax
  _QWORD *v12; // rsi
  void *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  __int64 v18; // r15
  __int64 v19; // rsi
  char *v20; // rax
  CFilterGraph *v21; // rcx
  char *v22; // rbx
  __int128 v23; // xmm0
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r8
  void (*v28)(void); // rax
  bool v29; // zf
  __int128 v30; // xmm0
  __int64 v31; // rcx
  GUID *v32; // rdx
  const WCHAR *v33; // rcx
  unsigned int v34; // r14d
  unsigned __int16 *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // r8
  struct __POSITION *v38; // rdx
  struct __POSITION *v39; // rax
  struct __POSITION *v40; // rax
  struct __POSITION *v41; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v42; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v43[34]; // [rsp+30h] [rbp-D0h] BYREF

  v3 = *a2;
  a2[5] = (struct __POSITION *)0xBFF0000000000000LL;
  a2[6] = (struct __POSITION *)*((_QWORD *)a3 + 6);
  *((_DWORD *)a2 + 14) = *((_DWORD *)a3 + 14);
  *((_DWORD *)a2 + 15) = *((_DWORD *)a3 + 15);
  v5 = *(_QWORD *)a3;
  v41 = v3;
  if ( v5 )
  {
    this = v3;
    while ( 1 )
    {
      if ( !this )
        goto LABEL_30;
      CBaseList::GetI(this, (struct __POSITION *)v5);
      v7 = CBaseList::GetI(v6, v3);
      this = (CFilterGraph *)*(unsigned int *)v8;
      if ( (_DWORD)this != *(_DWORD *)v7 )
        break;
      if ( (_DWORD)this != 1 )
        break;
      this = (CFilterGraph *)v7[1];
      if ( v8[1] != this )
        break;
      v5 = *(_QWORD *)(v5 + 8);
      if ( v3 )
        v9 = (struct __POSITION **)((char *)v3 + 8);
      else
        v9 = a2;
      v3 = *v9;
      v41 = v3;
      this = v3;
      v10 = v3;
      if ( !v5 )
        goto LABEL_13;
    }
  }
  else
  {
    v10 = v3;
LABEL_13:
    if ( !v10 )
      goto LABEL_30;
  }
  do
  {
    NextI = CBaseList::GetNextI(this, &v41);
    v12 = NextI;
    if ( *(_DWORD *)NextI )
    {
      if ( *(_DWORD *)NextI == 1 )
      {
        v15 = NextI[2];
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        v16 = (void *)v12[5];
        if ( v16 )
          operator delete(v16);
      }
      else if ( *(_DWORD *)NextI == 2 )
      {
        v17 = (void *)NextI[5];
        if ( v17 )
          CoTaskMemFree(v17);
        if ( !*((_DWORD *)v12 + 4) )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12[1] + 16LL))(v12[1]);
      }
    }
    else
    {
      v13 = (void *)NextI[3];
      if ( v13 )
        CoTaskMemFree(v13);
      v14 = (void *)v12[4];
      if ( v14 )
        CoTaskMemFree(v14);
    }
    operator delete(v12);
    CBaseList::RemoveI((CBaseList *)a2, v3);
    v3 = v41;
  }
  while ( v41 );
LABEL_30:
  while ( v5 )
  {
    v18 = *(_QWORD *)(v5 + 8);
    v19 = *(_QWORD *)(v5 + 16);
    v20 = (char *)operator new(0x38u);
    v22 = v20;
    if ( !v20 )
      goto LABEL_68;
    *(_DWORD *)v20 = *(_DWORD *)v19;
    v23 = *(_OWORD *)(v19 + 8);
    if ( !*(_DWORD *)v19 )
    {
      *(_OWORD *)(v20 + 8) = v23;
      *(_OWORD *)(v20 + 24) = *(_OWORD *)(v19 + 24);
      v24 = *((_QWORD *)v20 + 1);
      *((_QWORD *)v20 + 4) = 0;
      *((_QWORD *)v20 + 3) = 0;
      if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v24 + 80LL))(v24) < 0 )
        goto LABEL_68;
      v25 = *((_QWORD *)v22 + 1);
      v41 = 0;
      if ( (*(int (__fastcall **)(__int64, struct __POSITION **))(*(_QWORD *)v25 + 48LL))(v25, &v41) < 0 )
        goto LABEL_68;
      v21 = v41;
      if ( !v41 )
        goto LABEL_68;
      if ( (*(int (__fastcall **)(struct __POSITION *, char *))(*(_QWORD *)v41 + 80LL))(v41, v22 + 32) < 0 )
        goto LABEL_68;
      memset_0(v43, 0, sizeof(v43));
      if ( (*(int (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)v22 + 1) + 64LL))(*((_QWORD *)v22 + 1), v43) < 0 )
        goto LABEL_68;
      *((_DWORD *)v22 + 4) = CFilterGraph::SearchIFilterToNumber(v21, a2, v43[0]);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( (*(int (__fastcall **)(struct __POSITION *, _QWORD *))(*(_QWORD *)v41 + 64LL))(v41, v43) < 0 )
        goto LABEL_68;
      *((_DWORD *)v22 + 5) = CFilterGraph::SearchIFilterToNumber(v21, a2, v43[0]);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v28 = *(void (**)(void))(*(_QWORD *)v41 + 16LL);
      goto LABEL_59;
    }
    v29 = *(_DWORD *)v19 == 1;
    *(_OWORD *)(v20 + 8) = v23;
    *(_OWORD *)(v20 + 24) = *(_OWORD *)(v19 + 24);
    if ( v29 )
    {
      v30 = *(_OWORD *)(v19 + 40);
      v42 = 0;
      *(_OWORD *)(v20 + 40) = v30;
      v31 = *((_QWORD *)v20 + 2);
      v20[48] = *(_BYTE *)(v19 + 48);
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      (***((void (__fastcall ****)(_QWORD, GUID *, __int64 *))v22 + 1))(*((_QWORD *)v22 + 1), &IID_IPersist, &v42);
      v32 = (GUID *)(v22 + 24);
      if ( v42 )
      {
        (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v42 + 24LL))(v42, v32);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      else
      {
        *v32 = GUID_NULL;
      }
      v33 = *(const WCHAR **)(v19 + 40);
      if ( v33 )
      {
        v34 = lstrlenW(v33) + 1;
        v35 = (unsigned __int16 *)operator new[](saturated_mul(v34, 2u));
        *((_QWORD *)v22 + 5) = v35;
        if ( v35 )
          StringCchCopyW(v35, v34, *(const unsigned __int16 **)(v19 + 40));
      }
    }
    else
    {
      *((_QWORD *)v20 + 5) = *(_QWORD *)(v19 + 40);
      v36 = *((_QWORD *)v20 + 3);
      *((_QWORD *)v20 + 5) = 0;
      if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v36 + 80LL))(v36) < 0
        || (memset_0(v43, 0, sizeof(v43)),
            (*(int (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)v22 + 3) + 64LL))(*((_QWORD *)v22 + 3), v43) < 0) )
      {
        *((_DWORD *)v22 + 4) = 1;
LABEL_68:
        CFilterGraph::FreeActionMemory(v21, (struct CFilterGraph::_Object *)v22);
        a2[6] = (struct __POSITION *)0xBFF0000000000000LL;
        return;
      }
      *((_DWORD *)v22 + 8) = CFilterGraph::SearchIFilterToNumber(v21, a2, v43[0]);
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      if ( !*((_DWORD *)v22 + 4) )
      {
        v28 = *(void (**)(void))(**((_QWORD **)v22 + 1) + 8LL);
LABEL_59:
        v28();
      }
    }
    v38 = a2[4];
    v5 = v18;
    if ( v38 )
    {
      v39 = (struct __POSITION *)*((_QWORD *)v38 + 1);
      --*((_DWORD *)a2 + 7);
      a2[4] = v39;
      goto LABEL_63;
    }
    v38 = (struct __POSITION *)operator new(0x18u);
    if ( v38 )
    {
LABEL_63:
      *((_QWORD *)v38 + 2) = v22;
      *((_QWORD *)v38 + 1) = 0;
      *(_QWORD *)v38 = a2[1];
      v40 = a2[1];
      if ( v40 )
        *((_QWORD *)v40 + 1) = v38;
      else
        *a2 = v38;
      ++*((_DWORD *)a2 + 4);
      a2[1] = v38;
    }
  }
}

```

## disassembly

```asm
0x180022c28  mov     [rsp-8+arg_0], rbx
0x180022c2d  push    rbp
0x180022c2e  push    rsi
0x180022c2f  push    rdi
0x180022c30  push    r14
0x180022c32  push    r15
0x180022c34  lea     rbp, [rsp-50h]
0x180022c39  sub     rsp, 150h
0x180022c40  mov     rax, cs:__security_cookie
0x180022c47  xor     rax, rsp
0x180022c4a  mov     [rbp+70h+var_30], rax
0x180022c4e  mov     rbx, [rdx]
0x180022c51  mov     rax, 0BFF0000000000000h
0x180022c5b  mov     [rdx+28h], rax
0x180022c5f  mov     rdi, rdx
0x180022c62  mov     rax, [r8+30h]
0x180022c66  mov     [rdx+30h], rax
0x180022c6a  mov     eax, [r8+38h]
0x180022c6e  mov     [rdx+38h], eax
0x180022c71  mov     eax, [r8+3Ch]
0x180022c75  mov     [rdx+3Ch], eax
0x180022c78  mov     r14, [r8]
0x180022c7b  mov     [rsp+170h+var_150], rbx
0x180022c80  test    r14, r14
0x180022c83  jz      short loc_180022CEE
0x180022c85  mov     rcx, rbx; this
0x180022c88  test    rcx, rcx
0x180022c8b  jz      loc_180022DB8
0x180022c91  mov     rdx, r14; struct __POSITION *
0x180022c94  call    ?GetI@CBaseList@@IEBAPEAXPEAU__POSITION@@@Z; CBaseList::GetI(__POSITION *)
0x180022c99  mov     rdx, rbx; struct __POSITION *
0x180022c9c  mov     r9, rax
0x180022c9f  call    ?GetI@CBaseList@@IEBAPEAXPEAU__POSITION@@@Z; CBaseList::GetI(__POSITION *)
0x180022ca4  mov     ecx, [r9]
0x180022ca7  cmp     ecx, [rax]
0x180022ca9  jnz     short loc_180022CFA
0x180022cab  cmp     ecx, 1
0x180022cae  jnz     short loc_180022CFA
0x180022cb0  mov     rcx, [rax+8]
0x180022cb4  cmp     [r9+8], rcx
0x180022cb8  jnz     short loc_180022CFA
0x180022cba  test    r14, r14
0x180022cbd  jnz     short loc_180022CC4
0x180022cbf  mov     r14, r8
0x180022cc2  jmp     short loc_180022CC8
0x180022cc4  add     r14, 8
0x180022cc8  mov     r14, [r14]
0x180022ccb  test    rbx, rbx
0x180022cce  jnz     short loc_180022CD5
0x180022cd0  mov     rbx, rdi
0x180022cd3  jmp     short loc_180022CD9
0x180022cd5  add     rbx, 8
0x180022cd9  mov     rbx, [rbx]
0x180022cdc  mov     [rsp+170h+var_150], rbx
0x180022ce1  mov     rcx, rbx; this
0x180022ce4  mov     rax, rbx
0x180022ce7  test    r14, r14
0x180022cea  jnz     short loc_180022C88
0x180022cec  jmp     short loc_180022CF1
0x180022cee  mov     rax, rbx
0x180022cf1  test    rax, rax
0x180022cf4  jz      loc_180022DB8
0x180022cfa  lea     rdx, [rsp+170h+var_150]; struct __POSITION **
0x180022cff  call    ?GetNextI@CBaseList@@IEBAPEAXAEAPEAU__POSITION@@@Z; CBaseList::GetNextI(__POSITION * &)
0x180022d04  mov     rsi, rax
0x180022d07  cmp     dword ptr [rax], 0
0x180022d0a  jnz     short loc_180022D38
0x180022d0c  mov     rcx, [rax+18h]; pv
0x180022d10  test    rcx, rcx
0x180022d13  jz      short loc_180022D21
0x180022d15  call    cs:__imp_CoTaskMemFree
0x180022d1c  nop     dword ptr [rax+rax+00h]
0x180022d21  mov     rcx, [rsi+20h]; pv
0x180022d25  test    rcx, rcx
0x180022d28  jz      short loc_180022D92
0x180022d2a  call    cs:__imp_CoTaskMemFree
0x180022d31  nop     dword ptr [rax+rax+00h]
0x180022d36  jmp     short loc_180022D92
0x180022d38  cmp     dword ptr [rax], 1
0x180022d3b  jnz     short loc_180022D62
0x180022d3d  mov     rcx, [rax+10h]
0x180022d41  test    rcx, rcx
0x180022d44  jz      short loc_180022D52
0x180022d46  mov     rax, [rcx]
0x180022d49  mov     rax, [rax+10h]
0x180022d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d52  mov     rcx, [rsi+28h]; Block
0x180022d56  test    rcx, rcx
0x180022d59  jz      short loc_180022D92
0x180022d5b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022d60  jmp     short loc_180022D92
0x180022d62  cmp     dword ptr [rax], 2
0x180022d65  jnz     short loc_180022D92
0x180022d67  mov     rcx, [rax+28h]; pv
0x180022d6b  test    rcx, rcx
0x180022d6e  jz      short loc_180022D7C
0x180022d70  call    cs:__imp_CoTaskMemFree
0x180022d77  nop     dword ptr [rax+rax+00h]
0x180022d7c  cmp     dword ptr [rsi+10h], 0
0x180022d80  jnz     short loc_180022D92
0x180022d82  mov     rcx, [rsi+8]
0x180022d86  mov     rax, [rcx]
0x180022d89  mov     rax, [rax+10h]
0x180022d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d92  mov     edx, 38h ; '8'
0x180022d97  mov     rcx, rsi; Block
0x180022d9a  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180022d9f  mov     rdx, rbx; struct __POSITION *
0x180022da2  mov     rcx, rdi; this
0x180022da5  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x180022daa  mov     rbx, [rsp+170h+var_150]
0x180022daf  test    rbx, rbx
0x180022db2  jnz     loc_180022CFA
0x180022db8  test    r14, r14
0x180022dbb  jz      loc_180023119
0x180022dc1  mov     r15, [r14+8]
0x180022dc5  mov     ecx, 38h ; '8'; Size
0x180022dca  mov     rsi, [r14+10h]
0x180022dce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022dd3  mov     rbx, rax
0x180022dd6  test    rax, rax
0x180022dd9  jz      loc_180023103
0x180022ddf  mov     ecx, [rsi]
0x180022de1  mov     [rax], ecx
0x180022de3  cmp     dword ptr [rsi], 0
0x180022de6  movups  xmm0, xmmword ptr [rsi+8]
0x180022dea  jnz     loc_180022F19
0x180022df0  movups  xmmword ptr [rax+8], xmm0
0x180022df4  lea     rdx, [rax+18h]
0x180022df8  movups  xmm1, xmmword ptr [rsi+18h]
0x180022dfc  movups  xmmword ptr [rax+18h], xmm1
0x180022e00  mov     rcx, [rax+8]
0x180022e04  mov     qword ptr [rax+20h], 0
0x180022e0c  mov     qword ptr [rdx], 0
0x180022e13  mov     rax, [rcx]
0x180022e16  mov     rax, [rax+50h]
0x180022e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e1f  test    eax, eax
0x180022e21  js      loc_180023103
0x180022e27  mov     rcx, [rbx+8]
0x180022e2b  lea     rdx, [rsp+170h+var_150]
0x180022e30  mov     [rsp+170h+var_150], 0
0x180022e39  mov     rax, [rcx]
0x180022e3c  mov     rax, [rax+30h]
0x180022e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e45  test    eax, eax
0x180022e47  js      loc_180023103
0x180022e4d  mov     rcx, [rsp+170h+var_150]
0x180022e52  test    rcx, rcx
0x180022e55  jz      loc_180023103
0x180022e5b  mov     rax, [rcx]
0x180022e5e  lea     rdx, [rbx+20h]
0x180022e62  mov     rax, [rax+50h]
0x180022e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e6b  test    eax, eax
0x180022e6d  js      loc_180023103
0x180022e73  xor     edx, edx; Val
0x180022e75  lea     rcx, [rsp+170h+var_140]; void *
0x180022e7a  mov     r8d, 110h; Size
0x180022e80  call    memset_0
0x180022e85  mov     rcx, [rbx+8]
0x180022e89  lea     rdx, [rsp+170h+var_140]
0x180022e8e  mov     rax, [rcx]
0x180022e91  mov     rax, [rax+40h]
0x180022e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e9a  test    eax, eax
0x180022e9c  js      loc_180023103
0x180022ea2  mov     r8, [rsp+170h+var_140]
0x180022ea7  mov     rdx, rdi
0x180022eaa  call    ?SearchIFilterToNumber@CFilterGraph@@AEAAHAEAV?$CGenericList@U_Object@CFilterGraph@@@@PEAUIBaseFilter@@@Z; CFilterGraph::SearchIFilterToNumber(CGenericList<CFilterGraph::_Object> &,IBaseFilter *)
0x180022eaf  mov     [rbx+10h], eax
0x180022eb2  test    r8, r8
0x180022eb5  jz      short loc_180022EC6
0x180022eb7  mov     rax, [r8]
0x180022eba  mov     rcx, r8
0x180022ebd  mov     rax, [rax+10h]
0x180022ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ec6  mov     rcx, [rsp+170h+var_150]
0x180022ecb  lea     rdx, [rsp+170h+var_140]
0x180022ed0  mov     rax, [rcx]
0x180022ed3  mov     rax, [rax+40h]
0x180022ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022edc  test    eax, eax
0x180022ede  js      loc_180023103
0x180022ee4  mov     r8, [rsp+170h+var_140]
0x180022ee9  mov     rdx, rdi
0x180022eec  call    ?SearchIFilterToNumber@CFilterGraph@@AEAAHAEAV?$CGenericList@U_Object@CFilterGraph@@@@PEAUIBaseFilter@@@Z; CFilterGraph::SearchIFilterToNumber(CGenericList<CFilterGraph::_Object> &,IBaseFilter *)
0x180022ef1  mov     [rbx+14h], eax
0x180022ef4  test    r8, r8
0x180022ef7  jz      short loc_180022F08
0x180022ef9  mov     rax, [r8]
0x180022efc  mov     rcx, r8
0x180022eff  mov     rax, [rax+10h]
0x180022f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f08  mov     rcx, [rsp+170h+var_150]
0x180022f0d  mov     rax, [rcx]
0x180022f10  mov     rax, [rax+10h]
0x180022f14  jmp     loc_180023097
0x180022f19  cmp     dword ptr [rsi], 1
0x180022f1c  movups  xmmword ptr [rax+8], xmm0
0x180022f20  movups  xmm1, xmmword ptr [rsi+18h]
0x180022f24  movups  xmmword ptr [rax+18h], xmm1
0x180022f28  jnz     loc_180023006
0x180022f2e  movups  xmm0, xmmword ptr [rsi+28h]
0x180022f32  mov     [rsp+170h+var_148], 0
0x180022f3b  movups  xmmword ptr [rax+28h], xmm0
0x180022f3f  mov     rcx, [rbx+10h]
0x180022f43  mov     al, [rsi+30h]
0x180022f46  mov     [rbx+30h], al
0x180022f49  test    rcx, rcx
0x180022f4c  jz      short loc_180022F5A
0x180022f4e  mov     rax, [rcx]
0x180022f51  mov     rax, [rax+8]
0x180022f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f5a  mov     rcx, [rbx+8]
0x180022f5e  lea     r8, [rsp+170h+var_148]
0x180022f63  lea     rdx, IID_IPersist
0x180022f6a  mov     rax, [rcx]
0x180022f6d  mov     rax, [rax]
0x180022f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f75  mov     rcx, [rsp+170h+var_148]
0x180022f7a  lea     rdx, [rbx+18h]
0x180022f7e  test    rcx, rcx
0x180022f81  jz      short loc_180022FA2
0x180022f83  mov     rax, [rcx]
0x180022f86  mov     rax, [rax+18h]
0x180022f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f8f  mov     rcx, [rsp+170h+var_148]
0x180022f94  mov     rax, [rcx]
0x180022f97  mov     rax, [rax+10h]
0x180022f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fa0  jmp     short loc_180022FAD
0x180022fa2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180022fa9  movdqu  xmmword ptr [rdx], xmm0
0x180022fad  mov     rcx, [rsi+28h]; lpString
0x180022fb1  test    rcx, rcx
0x180022fb4  jz      loc_18002309C
0x180022fba  call    cs:__imp_lstrlenW
0x180022fc1  nop     dword ptr [rax+rax+00h]
0x180022fc6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022fcd  lea     r14d, [rax+1]
0x180022fd1  mov     eax, 2
0x180022fd6  mul     r14
0x180022fd9  cmovb   rax, rcx
0x180022fdd  mov     rcx, rax; unsigned __int64
0x180022fe0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180022fe5  mov     [rbx+28h], rax
0x180022fe9  test    rax, rax
0x180022fec  jz      loc_18002309C
0x180022ff2  mov     r8, [rsi+28h]; unsigned __int16 *
0x180022ff6  mov     edx, r14d; unsigned __int64
0x180022ff9  mov     rcx, rax; unsigned __int16 *
0x180022ffc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023001  jmp     loc_18002309C
0x180023006  movsd   xmm0, qword ptr [rsi+28h]
0x18002300b  lea     rdx, [rax+28h]
0x18002300f  movsd   qword ptr [rax+28h], xmm0
0x180023014  mov     rcx, [rax+18h]
0x180023018  mov     qword ptr [rdx], 0
0x18002301f  mov     rax, [rcx]
0x180023022  mov     rax, [rax+50h]
0x180023026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002302b  test    eax, eax
0x18002302d  js      loc_1800230FC
0x180023033  xor     edx, edx; Val
0x180023035  lea     rcx, [rsp+170h+var_140]; void *
0x18002303a  mov     r8d, 110h; Size
0x180023040  call    memset_0
0x180023045  mov     rcx, [rbx+18h]
0x180023049  lea     rdx, [rsp+170h+var_140]
0x18002304e  mov     rax, [rcx]
0x180023051  mov     rax, [rax+40h]
0x180023055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002305a  test    eax, eax
0x18002305c  js      loc_1800230FC
0x180023062  mov     r8, [rsp+170h+var_140]
0x180023067  mov     rdx, rdi
0x18002306a  call    ?SearchIFilterToNumber@CFilterGraph@@AEAAHAEAV?$CGenericList@U_Object@CFilterGraph@@@@PEAUIBaseFilter@@@Z; CFilterGraph::SearchIFilterToNumber(CGenericList<CFilterGraph::_Object> &,IBaseFilter *)
0x18002306f  mov     [rbx+20h], eax
0x180023072  test    r8, r8
0x180023075  jz      short loc_180023086
0x180023077  mov     rax, [r8]
0x18002307a  mov     rcx, r8
0x18002307d  mov     rax, [rax+10h]
0x180023081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023086  cmp     dword ptr [rbx+10h], 0
0x18002308a  jnz     short loc_18002309C
0x18002308c  mov     rcx, [rbx+8]
0x180023090  mov     rax, [rcx]
0x180023093  mov     rax, [rax+8]
0x180023097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002309c  mov     rdx, [rdi+20h]
0x1800230a0  mov     r14, r15
0x1800230a3  test    rdx, rdx
0x1800230a6  jz      short loc_1800230B5
0x1800230a8  mov     rax, [rdx+8]
0x1800230ac  dec     dword ptr [rdi+1Ch]
0x1800230af  mov     [rdi+20h], rax
0x1800230b3  jmp     short loc_1800230CB
0x1800230b5  mov     ecx, 18h; Size
  ... truncated ...
```

# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x140009228`
- end: `0x14000938f`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `359`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1400083f0`
- `0x14001366c`
- `0x140022714`
- `0x140025e48`

## callees

- `0x140005c58`
- `0x1400070f0`
- `0x140008ce8`
- `0x140009228`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x140009294`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x140009294`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x14000927c`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x14000927c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
        __int64 *a1,
        _QWORD *a2,
        const wchar_t *a3,
        int *a4)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  const wchar_t *v10; // r15
  unsigned __int64 v11; // rbp
  int v12; // r12d
  const wchar_t *v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx

  v8 = *a4;
  if ( (int)v8 < 0 )
    ATL::AtlThrowImpl(0x80070057);
  if ( a3 && *a3 )
  {
    v9 = *a1;
    v10 = (const wchar_t *)(v9 + 2 * v8);
    v11 = v9 + 2LL * *(int *)(v9 - 16);
    if ( (unsigned __int64)v10 < v11 )
    {
      v12 = wcsspn(v10, a3);
      v13 = &v10[v12];
      if ( (unsigned __int64)v13 < v11 )
      {
        v14 = wcscspn(v13, a3);
        v15 = (unsigned int)(v12 + *a4);
        *a4 = v15 + v14 + 1;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
          a1,
          a2,
          v15,
          v14);
        return a2;
      }
    }
    goto LABEL_12;
  }
  v16 = *a1;
  if ( (int)v8 >= *(_DWORD *)(v16 - 16) )
  {
LABEL_12:
    *a4 = -1;
    v19 = *(_QWORD *)(*a1 - 24);
    if ( !v19 || (v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 32LL))(v19)) == 0 )
      v20 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
    if ( !v20 )
      ATL::AtlThrowImpl(0x80004005);
    *a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20) + 24;
    return a2;
  }
  v17 = *(_QWORD *)(v16 - 24);
  if ( !v17 || (v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17)) == 0 )
    v18 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a2,
    *a1 + 2LL * *a4,
    v18);
  return a2;
}

```

## disassembly

```asm
0x140009228  push    rbx
0x14000922a  push    rbp
0x14000922b  push    rsi
0x14000922c  push    rdi
0x14000922d  push    r12
0x14000922f  push    r13
0x140009231  push    r14
0x140009233  push    r15
0x140009235  sub     rsp, 38h
0x140009239  mov     r14, r9
0x14000923c  mov     rsi, r8
0x14000923f  mov     rbx, rdx
0x140009242  mov     rdi, rcx
0x140009245  xor     r13d, r13d
0x140009248  movsxd  rax, dword ptr [r9]
0x14000924b  test    eax, eax
0x14000924d  js      loc_140009384
0x140009253  test    r8, r8
0x140009256  jz      short loc_1400092BC
0x140009258  cmp     [r8], r13w
0x14000925c  jz      short loc_1400092BC
0x14000925e  mov     rcx, [rcx]
0x140009261  lea     r15, [rcx+rax*2]
0x140009265  movsxd  rax, dword ptr [rcx-10h]
0x140009269  lea     rbp, [rcx+rax*2]
0x14000926d  cmp     r15, rbp
0x140009270  jnb     loc_14000930C
0x140009276  mov     rdx, r8; Control
0x140009279  mov     rcx, r15; String
0x14000927c  call    cs:__imp_wcsspn
0x140009282  mov     r12, rax
0x140009285  movsxd  rcx, eax
0x140009288  lea     rcx, [r15+rcx*2]; String
0x14000928c  cmp     rcx, rbp
0x14000928f  jnb     short loc_14000930C
0x140009291  mov     rdx, rsi; Control
0x140009294  call    cs:__imp_wcscspn
0x14000929a  mov     r8d, [r14]
0x14000929d  add     r8d, r12d
0x1400092a0  lea     ecx, [rax+1]
0x1400092a3  add     ecx, r8d
0x1400092a6  mov     [r14], ecx
0x1400092a9  mov     r9d, eax
0x1400092ac  mov     rdx, rbx
0x1400092af  mov     rcx, rdi
0x1400092b2  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x1400092b7  jmp     loc_140009365
0x1400092bc  mov     rcx, [rcx]
0x1400092bf  cmp     eax, [rcx-10h]
0x1400092c2  jge     short loc_14000930C
0x1400092c4  mov     rcx, [rcx-18h]
0x1400092c8  test    rcx, rcx
0x1400092cb  jz      short loc_1400092DE
0x1400092cd  mov     rax, [rcx]
0x1400092d0  mov     rax, [rax+20h]
0x1400092d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092d9  test    rax, rax
0x1400092dc  jnz     short loc_1400092F5
0x1400092de  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400092e5  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400092ec  mov     rax, [rax+20h]
0x1400092f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092f5  movsxd  rdx, dword ptr [r14]
0x1400092f8  mov     rcx, [rdi]
0x1400092fb  lea     rdx, [rcx+rdx*2]
0x1400092ff  mov     r8, rax
0x140009302  mov     rcx, rbx
0x140009305  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGPEAUIAtlStringMgr@1@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,ATL::IAtlStringMgr *)
0x14000930a  jmp     short loc_140009365
0x14000930c  mov     dword ptr [r14], 0FFFFFFFFh
0x140009313  mov     rax, [rdi]
0x140009316  mov     rcx, [rax-18h]
0x14000931a  test    rcx, rcx
0x14000931d  jz      short loc_140009333
0x14000931f  mov     rax, [rcx]
0x140009322  mov     rax, [rax+20h]
0x140009326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000932b  mov     rcx, rax
0x14000932e  test    rax, rax
0x140009331  jnz     short loc_14000934D
0x140009333  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000933a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140009341  mov     rax, [rax+20h]
0x140009345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000934a  mov     rcx, rax
0x14000934d  test    rcx, rcx
0x140009350  jz      short loc_140009379
0x140009352  mov     rax, [rcx]
0x140009355  mov     rax, [rax+18h]
0x140009359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000935e  add     rax, 18h
0x140009362  mov     [rbx], rax
0x140009365  mov     rax, rbx
0x140009368  add     rsp, 38h
0x14000936c  pop     r15
0x14000936e  pop     r14
0x140009370  pop     r13
0x140009372  pop     r12
0x140009374  pop     rdi
0x140009375  pop     rsi
0x140009376  pop     rbp
0x140009377  pop     rbx
0x140009378  retn
0x140009379  mov     ecx, 80004005h; unsigned int
0x14000937e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140009384  mov     ecx, 80070057h; unsigned int
0x140009389  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

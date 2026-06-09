# CopyValueFromInitString(SStringSegment const &,CDSLPropertyInformation const &,_GUID const &,CDSLProperty &)

- ea: `0x180011034`
- end: `0x1800112aa`
- name: `?CopyValueFromInitString@@YAJAEBUSStringSegment@@AEBVCDSLPropertyInformation@@AEBU_GUID@@AEAVCDSLProperty@@@Z`
- size: `630`
- prototype: `int(const struct SStringSegment *, const struct CDSLPropertyInformation *, const struct _GUID *, struct CDSLProperty *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180015170`
- `0x180062670`

## callees

- `0x18000faf0`
- `0x180011034`
- `0x1800112b0`
- `0x180011bcc`
- `0x18001205c`
- `0x180013870`
- `0x180029560`
- `0x18007e700`
- `0x18007e7c0`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800110d0`
- `MSDART!MpHeapAlloc` at `0x1800110d0`
- `OLEAUT32!__imp_VariantClear` at `0x180011182`
- `OLEAUT32!__imp_VariantClear` at `0x180011182`
- `OLEAUT32!__imp_VariantChangeType` at `0x180011196`
- `OLEAUT32!__imp_VariantChangeType` at `0x180011196`

## string_xrefs

- `0x1800110fe`: `<CopyValueFromInitString|OLEDB|ERR> `
- `0x18001124f`: `<CopyValueFromInitString|OLEDB|ERR> `
- `0x18001126e`: `<CopyValueFromInitString|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CopyValueFromInitString(
        const struct SStringSegment *a1,
        const struct CDSLPropertyInformation *a2,
        const struct _GUID *a3,
        struct CDSLProperty *a4)
{
  int v8; // eax
  unsigned __int16 *v9; // rbx
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  unsigned __int16 *v17; // rdi
  __int64 v18; // rax
  unsigned int v19; // edi
  __int64 v20; // rdx
  __int64 v21; // rax
  VARIANTARG *v22; // r12
  const struct CDSLTextEquivalence *TextEquivalence; // rsi
  __int64 v24; // rcx
  unsigned __int16 *v25; // rcx
  unsigned __int16 i; // ax
  unsigned __int16 v28[4]; // [rsp+20h] [rbp+0h] BYREF

  v8 = *((_DWORD *)a1 + 2);
  v9 = 0;
  *(_QWORD *)v28 = 0;
  v10 = (unsigned int)(v8 + 2);
  v11 = 2 * v10;
  if ( (unsigned __int64)(2 * v10) > 0x200 )
  {
    v18 = 4 * v10;
    if ( !is_mul_ok(v11, 2u) )
      v18 = -1;
    v9 = (unsigned __int16 *)MpHeapAlloc(g_hHeapHandle, 19922944, v18);
    *(_QWORD *)v28 = v9;
    v17 = v9;
  }
  else
  {
    v12 = 4 * v10;
    v13 = v12 + 15;
    if ( v12 + 15 < v12 )
      v13 = 0xFFFFFFFFFFFFFF0LL;
    v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
    v15 = alloca(v14);
    v16 = alloca(v14);
    v17 = v28;
  }
  if ( v17 )
  {
    *v17 = 0;
    if ( *((_WORD *)a2 + 8) != 8 )
      goto LABEL_18;
    v21 = *(_QWORD *)&DBPROPSET_DBINIT.Data1 - *(_QWORD *)&a3->Data1;
    if ( *(_QWORD *)&DBPROPSET_DBINIT.Data1 == *(_QWORD *)&a3->Data1 )
      v21 = *(_QWORD *)DBPROPSET_DBINIT.Data4 - *(_QWORD *)a3->Data4;
    if ( v21 || *((_DWORD *)a2 + 2) != 160 )
      CopyUnQuotedValueString(v17, *(_QWORD *)a1);
    else
LABEL_18:
      StringCchCopyW(v17, (unsigned int)(*((_DWORD *)a1 + 2) + 1), *(const unsigned __int16 **)a1);
    v22 = (VARIANTARG *)((char *)a4 + 48);
    VariantClear(v22);
    VariantChangeType(v22, v22, 0, *((_WORD *)a2 + 8));
    TextEquivalence = CDSLTextEquivalenceAssociations::GetTextEquivalence(a3, *((_DWORD *)a2 + 2), *((_WORD *)a2 + 8));
    if ( TextEquivalence )
    {
      v24 = *(_QWORD *)&DBPROPSET_DBINIT.Data1 - *(_QWORD *)&a3->Data1;
      if ( *(_QWORD *)&DBPROPSET_DBINIT.Data1 == *(_QWORD *)&a3->Data1 )
        v24 = *(_QWORD *)DBPROPSET_DBINIT.Data4 - *(_QWORD *)a3->Data4;
      if ( !v24 && (*((_DWORD *)a2 + 2) == 200 || *((_DWORD *)a2 + 2) == 63 || *((_DWORD *)a2 + 2) == 248) )
      {
        v25 = v17;
        for ( i = *v17; i; i = *v25 )
        {
          if ( i == 124 )
            *v25 = 0;
          ++v25;
        }
        v25[1] = 0;
      }
      v19 = (*(__int64 (__fastcall **)(const struct CDSLTextEquivalence *, unsigned __int16 *, VARIANTARG *))(*(_QWORD *)TextEquivalence + 24LL))(
              TextEquivalence,
              v17,
              v22);
      (*(void (__fastcall **)(const struct CDSLTextEquivalence *))(*(_QWORD *)TextEquivalence + 40LL))(TextEquivalence);
    }
    else
    {
      v19 = -2147467259;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_38;
      OLEDBTraceErr(-2147467259, L"<CopyValueFromInitString|OLEDB|ERR> ", 0x3CCu);
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      v20 = 1000457;
      goto LABEL_37;
    }
  }
  else
  {
    v19 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<CopyValueFromInitString|OLEDB|ERR> ", 0x391u);
      if ( (bidGblFlags & 2) != 0 )
      {
        v20 = 934921;
LABEL_37:
        v19 = bidTraceHR(off_1800C8430[0], v20, L"<CopyValueFromInitString|Trace|HR> ", v19);
      }
    }
  }
LABEL_38:
  operator delete(v9);
  return v19;
}

```

## disassembly

```asm
0x180011034  push    rbp
0x180011036  push    rbx
0x180011037  push    rsi
0x180011038  push    rdi
0x180011039  push    r12
0x18001103b  push    r13
0x18001103d  push    r14
0x18001103f  push    r15
0x180011041  sub     rsp, 38h
0x180011045  lea     rbp, [rsp+20h]
0x18001104a  mov     rax, cs:__security_cookie
0x180011051  xor     rax, rbp
0x180011054  mov     [rbp+50h+var_48], rax
0x180011058  mov     r12, r9
0x18001105b  mov     r15, r8
0x18001105e  mov     r14, rdx
0x180011061  mov     rsi, rcx
0x180011064  mov     eax, [rcx+8]
0x180011067  xor     r13d, r13d
0x18001106a  mov     ebx, r13d
0x18001106d  mov     qword ptr [rbp+50h+var_50], rbx
0x180011071  add     eax, 2
0x180011074  lea     rcx, [rax+rax]
0x180011078  cmp     rcx, 200h
0x18001107f  ja      short loc_1800110AE
0x180011081  shl     rax, 2
0x180011085  lea     rcx, [rax+0Fh]
0x180011089  cmp     rcx, rax
0x18001108c  ja      short loc_180011098
0x18001108e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180011098  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001109c  mov     rax, rcx
0x18001109f  call    _alloca_probe
0x1800110a4  sub     rsp, rcx
0x1800110a7  lea     rdi, [rsp+70h+var_50]
0x1800110ac  jmp     short loc_1800110E0
0x1800110ae  mov     eax, 2
0x1800110b3  mul     rcx
0x1800110b6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800110bd  cmovb   rax, rcx
0x1800110c1  mov     r8, rax
0x1800110c4  mov     edx, 1300000h
0x1800110c9  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800110d0  call    cs:__imp_MpHeapAlloc
0x1800110d6  mov     rbx, rax
0x1800110d9  mov     qword ptr [rbp+50h+var_50], rax
0x1800110dd  mov     rdi, rax
0x1800110e0  test    rdi, rdi
0x1800110e3  jnz     short loc_180011124
0x1800110e5  mov     eax, cs:_bidGblFlags
0x1800110eb  mov     edi, 8007000Eh
0x1800110f0  test    al, 2
0x1800110f2  jz      loc_180011283
0x1800110f8  mov     r8d, 391h; unsigned int
0x1800110fe  lea     rdx, aCopyvaluefromi; "<CopyValueFromInitString|OLEDB|ERR> "
0x180011105  mov     ecx, edi; int
0x180011107  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001110c  mov     eax, cs:_bidGblFlags
0x180011112  test    al, 2
0x180011114  jz      loc_180011283
0x18001111a  mov     edx, 0E4409h
0x18001111f  jmp     loc_18001126B
0x180011124  mov     [rdi], r13w
0x180011128  mov     eax, 8
0x18001112d  cmp     ax, [r14+10h]
0x180011132  jnz     short loc_18001116B
0x180011134  mov     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x18001113b  sub     rax, [r15]
0x18001113e  jnz     short loc_18001114B
0x180011140  mov     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x180011147  sub     rax, [r15+8]
0x18001114b  test    rax, rax
0x18001114e  jnz     short loc_18001115A
0x180011150  cmp     dword ptr [r14+8], 0A0h
0x180011158  jz      short loc_18001116B
0x18001115a  mov     r8d, [rsi+8]
0x18001115e  mov     rdx, [rsi]
0x180011161  mov     rcx, rdi
0x180011164  call    CopyUnQuotedValueString
0x180011169  jmp     short loc_18001117B
0x18001116b  mov     edx, [rsi+8]
0x18001116e  inc     edx; unsigned __int64
0x180011170  mov     r8, [rsi]; unsigned __int16 *
0x180011173  mov     rcx, rdi; unsigned __int16 *
0x180011176  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001117b  add     r12, 30h ; '0'
0x18001117f  mov     rcx, r12; pvarg
0x180011182  call    cs:__imp_VariantClear
0x180011188  xor     r8d, r8d; wFlags
0x18001118b  movzx   r9d, word ptr [r14+10h]; vt
0x180011190  mov     rdx, r12; pvarSrc
0x180011193  mov     rcx, r12; pvargDest
0x180011196  call    cs:__imp_VariantChangeType
0x18001119c  movzx   r8d, word ptr [r14+10h]; unsigned __int16
0x1800111a1  mov     edx, [r14+8]; unsigned int
0x1800111a5  mov     rcx, r15; struct _GUID *
0x1800111a8  call    ?GetTextEquivalence@CDSLTextEquivalenceAssociations@@SAPEBVCDSLTextEquivalence@@AEBU_GUID@@KG@Z; CDSLTextEquivalenceAssociations::GetTextEquivalence(_GUID const &,ulong,ushort)
0x1800111ad  mov     rsi, rax
0x1800111b0  test    rax, rax
0x1800111b3  jz      loc_18001123B
0x1800111b9  mov     rcx, qword ptr cs:DBPROPSET_DBINIT.Data1
0x1800111c0  sub     rcx, [r15]
0x1800111c3  jnz     short loc_1800111D0
0x1800111c5  mov     rcx, qword ptr cs:DBPROPSET_DBINIT.Data4
0x1800111cc  sub     rcx, [r15+8]
0x1800111d0  test    rcx, rcx
0x1800111d3  jnz     short loc_180011213
0x1800111d5  cmp     dword ptr [r14+8], 0C8h
0x1800111dd  jz      short loc_1800111F0
0x1800111df  cmp     dword ptr [r14+8], 3Fh ; '?'
0x1800111e4  jz      short loc_1800111F0
0x1800111e6  cmp     dword ptr [r14+8], 0F8h
0x1800111ee  jnz     short loc_180011213
0x1800111f0  mov     rcx, rdi
0x1800111f3  movzx   eax, word ptr [rdi]
0x1800111f6  jmp     short loc_180011209
0x1800111f8  cmp     ax, 7Ch ; '|'
0x1800111fc  jnz     short loc_180011202
0x1800111fe  mov     [rcx], r13w
0x180011202  add     rcx, 2
0x180011206  movzx   eax, word ptr [rcx]
0x180011209  test    ax, ax
0x18001120c  jnz     short loc_1800111F8
0x18001120e  mov     [rcx+2], r13w
0x180011213  mov     rax, [rsi]
0x180011216  mov     r8, r12
0x180011219  mov     rdx, rdi
0x18001121c  mov     rcx, rsi
0x18001121f  mov     rax, [rax+18h]
0x180011223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011228  mov     edi, eax
0x18001122a  mov     rax, [rsi]
0x18001122d  mov     rcx, rsi
0x180011230  mov     rax, [rax+28h]
0x180011234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011239  jmp     short loc_18001125D
0x18001123b  mov     edi, 80004005h
0x180011240  test    byte ptr cs:_bidGblFlags, 2
0x180011247  jz      short loc_180011283
0x180011249  mov     r8d, 3CCh; unsigned int
0x18001124f  lea     rdx, aCopyvaluefromi; "<CopyValueFromInitString|OLEDB|ERR> "
0x180011256  mov     ecx, edi; int
0x180011258  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001125d  test    byte ptr cs:_bidGblFlags, 2
0x180011264  jz      short loc_180011283
0x180011266  mov     edx, 0F4409h
0x18001126b  mov     r9d, edi
0x18001126e  lea     r8, aCopyvaluefromi_0; "<CopyValueFromInitString|Trace|HR> "
0x180011275  mov     rcx, cs:off_1800C8430; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001127c  call    _bidTraceHR
0x180011281  mov     edi, eax
0x180011283  mov     rcx, rbx; void *
0x180011286  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001128b  mov     eax, edi
0x18001128d  mov     rcx, [rbp+50h+var_48]
0x180011291  xor     rcx, rbp; StackCookie
0x180011294  call    __security_check_cookie
0x180011299  lea     rsp, [rbp+18h]
0x18001129d  pop     r15
0x18001129f  pop     r14
0x1800112a1  pop     r13
0x1800112a3  pop     r12
0x1800112a5  pop     rdi
0x1800112a6  pop     rsi
0x1800112a7  pop     rbx
0x1800112a8  pop     rbp
0x1800112a9  retn
```

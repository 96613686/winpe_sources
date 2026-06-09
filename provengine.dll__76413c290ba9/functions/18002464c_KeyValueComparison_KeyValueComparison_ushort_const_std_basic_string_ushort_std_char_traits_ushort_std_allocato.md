# KeyValueComparison::KeyValueComparison(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002464c`
- end: `0x180024804`
- name: `??0KeyValueComparison@@QEAA@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `440`
- prototype: `__int64 __fastcall(__int64, _WORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180025210`

## callees

- `0x1800071a4`
- `0x18000af20`
- `0x18000b030`
- `0x180021cf4`
- `0x180022780`
- `0x18002464c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180024769`
- `msvcrt!_wcsnicmp` at `0x180024769`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall KeyValueComparison::KeyValueComparison(__int64 a1, _WORD *a2, __int64 a3)
{
  _QWORD *v5; // rcx
  __int64 v6; // r8
  _WORD *v7; // rcx
  bool v8; // zf
  __int64 v9; // rbp
  __int64 v10; // rax
  size_t v11; // r15
  int *v12; // rsi
  __int64 v13; // rax
  bool (*v14)(KeyValueComparison *__hidden, const unsigned __int16 *); // rax
  unsigned int v16; // eax
  int v17[2]; // [rsp+20h] [rbp-58h] BYREF
  const wchar_t *v18; // [rsp+28h] [rbp-50h]
  bool (__fastcall *v19)(KeyValueComparison *__hidden, const unsigned __int16 *); // [rsp+30h] [rbp-48h]
  const wchar_t *v20; // [rsp+38h] [rbp-40h]
  char v21; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int16 v23; // [rsp+88h] [rbp+10h] BYREF

  *(_BYTE *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v5 = (_QWORD *)(a1 + 16);
  v5[3] = 7;
  v5[2] = 0;
  *(_WORD *)v5 = 0;
  if ( *a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
  }
  std::wstring::assign(v5, a2);
  *(_QWORD *)(a1 + 72) = 7;
  *(_QWORD *)(a1 + 64) = 0;
  *(_WORD *)(a1 + 48) = 0;
  if ( *(_QWORD *)(a3 + 24) < 8u )
    v7 = (_WORD *)a3;
  else
    v7 = *(_WORD **)a3;
  v8 = *v7 == 33;
  *(_BYTE *)a1 = v8;
  v9 = v8;
  v23 = 58;
  v10 = std::wstring::find(a3, &v23, v8);
  if ( v10 == -1 )
  {
    v14 = KeyValueComparison::StringCompareWithoutCase;
  }
  else
  {
    v11 = v10 - v9;
    if ( v10 == v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\keys.cpp",
        (const char *)0x80070057LL,
        v17[0]);
    *(_QWORD *)v17 = KeyValueComparison::NumericCompareWithRange;
    v18 = L"range";
    v19 = KeyValueComparison::PatternCompare;
    v20 = L"pattern";
    v12 = v17;
    while ( 1 )
    {
      v13 = *(_QWORD *)(a3 + 24) < 8u ? a3 : *(_QWORD *)a3;
      if ( !_wcsnicmp((const wchar_t *)(v13 + 2 * v9), *((const wchar_t **)v12 + 1), v11) )
        break;
      v12 += 4;
      if ( v12 == (int *)&v21 )
      {
        v16 = wil::verify_hresult<long>(0x80070057);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x84,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\keys.cpp",
          (const char *)v16,
          v17[0]);
      }
    }
    v14 = *(bool (**)(KeyValueComparison *__hidden, const unsigned __int16 *))v12;
  }
  *(_QWORD *)(a1 + 8) = v14;
  std::wstring::assign((void *)(a1 + 48));
  return a1;
}

```

## disassembly

```asm
0x18002464c  mov     [rsp+arg_10], rbx
0x180024651  mov     [rsp+arg_0], rcx
0x180024656  push    rbp
0x180024657  push    rsi
0x180024658  push    rdi
0x180024659  push    r12
0x18002465b  push    r13
0x18002465d  push    r14
0x18002465f  push    r15
0x180024661  sub     rsp, 40h
0x180024665  mov     rbx, r8
0x180024668  mov     rdi, rcx
0x18002466b  xor     r12d, r12d
0x18002466e  mov     [rcx], r12b
0x180024671  mov     [rcx+8], r12
0x180024675  add     rcx, 10h; void *
0x180024679  lea     ebp, [r12+7]
0x18002467e  mov     [rcx+18h], rbp
0x180024682  mov     [rcx+10h], r12
0x180024686  mov     [rcx], r12w
0x18002468a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002468e  cmp     [rdx], r12w
0x180024692  jnz     short loc_180024699
0x180024694  mov     r8d, r12d
0x180024697  jmp     short loc_1800246A6
0x180024699  mov     r8, rsi
0x18002469c  inc     r8
0x18002469f  cmp     [rdx+r8*2], r12w
0x1800246a4  jnz     short loc_18002469C
0x1800246a6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800246ab  nop
0x1800246ac  lea     r14, [rdi+30h]
0x1800246b0  mov     [r14+18h], rbp
0x1800246b4  mov     [r14+10h], r12
0x1800246b8  mov     [r14], r12w
0x1800246bc  cmp     qword ptr [rbx+18h], 8
0x1800246c1  jb      short loc_1800246C8
0x1800246c3  mov     rcx, [rbx]
0x1800246c6  jmp     short loc_1800246CB
0x1800246c8  mov     rcx, rbx
0x1800246cb  mov     edx, 21h ; '!'
0x1800246d0  cmp     dx, [rcx]
0x1800246d3  setz    al
0x1800246d6  mov     [rdi], al
0x1800246d8  mov     rbp, r12
0x1800246db  setz    bpl
0x1800246df  lea     eax, [rdx+19h]
0x1800246e2  mov     [rsp+78h+arg_8], ax
0x1800246ea  mov     r8, rbp
0x1800246ed  lea     rdx, [rsp+78h+arg_8]
0x1800246f5  mov     rcx, rbx
0x1800246f8  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x1800246fd  mov     r13, rax
0x180024700  cmp     rax, rsi
0x180024703  jz      loc_180024790
0x180024709  mov     r15, rax
0x18002470c  sub     r15, rbp
0x18002470f  mov     rcx, [rsp+78h]; this
0x180024714  jz      loc_1800247C8
0x18002471a  lea     rax, ?NumericCompareWithRange@KeyValueComparison@@AEBA_NPEBG@Z; KeyValueComparison::NumericCompareWithRange(ushort const *)
0x180024721  mov     qword ptr [rsp+78h+var_58], rax; int
0x180024726  lea     rax, aRange; "range"
0x18002472d  mov     [rsp+78h+var_50], rax
0x180024732  lea     rax, ?PatternCompare@KeyValueComparison@@AEBA_NPEBG@Z; KeyValueComparison::PatternCompare(ushort const *)
0x180024739  mov     [rsp+78h+var_48], rax
0x18002473e  lea     rax, aPattern; "pattern"
0x180024745  mov     [rsp+78h+var_40], rax
0x18002474a  lea     rsi, [rsp+78h+var_58]
0x18002474f  cmp     qword ptr [rbx+18h], 8
0x180024754  jb      short loc_18002475B
0x180024756  mov     rax, [rbx]
0x180024759  jmp     short loc_18002475E
0x18002475b  mov     rax, rbx
0x18002475e  lea     rcx, [rax+rbp*2]; String1
0x180024762  mov     r8, r15; MaxCount
0x180024765  mov     rdx, [rsi+8]; String2
0x180024769  call    cs:__imp__wcsnicmp
0x18002476f  test    eax, eax
0x180024771  jz      short loc_180024783
0x180024773  add     rsi, 10h
0x180024777  lea     rax, [rsp+78h+var_38]
0x18002477c  cmp     rsi, rax
0x18002477f  jz      short loc_1800247E0
0x180024781  jmp     short loc_18002474F
0x180024783  mov     rax, [rsi]
0x180024786  lea     r8, [r13+1]
0x18002478a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002478e  jmp     short loc_18002479D
0x180024790  lea     rax, ?StringCompareWithoutCase@KeyValueComparison@@AEBA_NPEBG@Z; KeyValueComparison::StringCompareWithoutCase(ushort const *)
0x180024797  mov     r9, rsi
0x18002479a  mov     r8, rbp
0x18002479d  mov     [rdi+8], rax
0x1800247a1  mov     rdx, rbx
0x1800247a4  mov     rcx, r14; void *
0x1800247a7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800247ac  nop
0x1800247ad  mov     rax, rdi
0x1800247b0  mov     rbx, [rsp+78h+arg_10]
0x1800247b8  add     rsp, 40h
0x1800247bc  pop     r15
0x1800247be  pop     r14
0x1800247c0  pop     r13
0x1800247c2  pop     r12
0x1800247c4  pop     rdi
0x1800247c5  pop     rsi
0x1800247c6  pop     rbp
0x1800247c7  retn
0x1800247c8  mov     r9d, 80070057h; char *
0x1800247ce  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800247d5  mov     edx, 6Eh ; 'n'; void *
0x1800247da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800247e0  mov     ecx, 80070057h
0x1800247e5  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800247ea  mov     r9d, eax; char *
0x1800247ed  mov     rcx, [rsp+78h]; this
0x1800247f2  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800247f9  mov     edx, 84h; void *
0x1800247fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

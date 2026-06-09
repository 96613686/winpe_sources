# dwrite::text_analyzer::impl$17::new::AnalyzeScript_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_

- ea: `0x180002e30`
- end: `0x18000321a`
- name: `dwrite::text_analyzer::impl$17::new::AnalyzeScript_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_`
- size: `1002`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001850`
- `0x180002170`
- `0x180002e30`
- `0x180022de0`
- `0x18010e040`
- `0x18010e540`
- `0x18010e630`
- `0x180316190`
- `0x180316ae0`
- `0x180316ee0`

## import_xrefs

- `oleaut32!GetErrorInfo` at `0x180003142`
- `oleaut32!GetErrorInfo` at `0x1800031a3`
- `oleaut32!GetErrorInfo` at `0x180003142`
- `oleaut32!GetErrorInfo` at `0x1800031a3`

## string_xrefs

- `0x180003179`: `assertion failed: item.get_end_pos().get_text_pos() > pos.get_text_pos()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\unicode_analysis\src\script_analysis.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=2
__int64 __fastcall dwrite::text_analyzer::impl_17::new::AnalyzeScript_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  unsigned __int64 v5; // r13
  unsigned __int64 v6; // r12
  unsigned int v7; // r15d
  __int64 v8; // rdx
  unsigned int v9; // r15d
  unsigned int v10; // r15d
  __int64 v11; // rdx
  char v12; // r12
  unsigned __int64 v13; // r14
  int v14; // eax
  unsigned int v15; // esi
  __int32 v17; // esi
  __m256i v18; // [rsp+30h] [rbp-50h]
  __int128 v19; // [rsp+50h] [rbp-30h]
  __m256i v20; // [rsp+60h] [rbp-20h]
  __int128 v21; // [rsp+80h] [rbp+0h]
  __int64 *v22; // [rsp+98h] [rbp+18h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+20h] BYREF
  _WORD v24[2]; // [rsp+A8h] [rbp+28h] BYREF
  int v25; // [rsp+ACh] [rbp+2Ch]
  __m256i pperrinfo; // [rsp+C0h] [rbp+40h] BYREF
  __int128 v27; // [rsp+E0h] [rbp+60h]
  unsigned __int64 v28; // [rsp+F0h] [rbp+70h]
  unsigned __int64 v29; // [rsp+F8h] [rbp+78h]
  unsigned int v30; // [rsp+100h] [rbp+80h]
  char Script; // [rsp+108h] [rbp+88h]
  __int16 v32; // [rsp+109h] [rbp+89h]
  __int64 v33; // [rsp+118h] [rbp+98h]

  v33 = -2;
  if ( a2 && (v23 = a2, a5) )
  {
    v22 = &v23;
    pperrinfo.m256i_i64[0] = 2;
    *(_OWORD *)&pperrinfo.m256i_u64[1] = 0;
    pperrinfo.m256i_i64[3] = (__int64)&v22;
    *(_QWORD *)&v27 = a3;
    *((_QWORD *)&v27 + 1) = a3 + (unsigned __int64)a4;
    v30 = 0;
    v28 = a3;
    v29 = *((_QWORD *)&v27 + 1);
    unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_unicode_interop::BridgeAnalysisSource_dwrite::text_analyzer::IDWriteTextAnalysisSource_____(&pperrinfo);
    v21 = v27;
    v20 = pperrinfo;
    v5 = v28;
    v6 = v29;
    if ( v28 < v29 )
    {
      v7 = v30;
      do
      {
        v27 = v21;
        pperrinfo = v20;
        v28 = v5;
        v29 = v6;
        v30 = v7;
        v32 = 0;
        Script = GetScript(v7);
        if ( (unsigned __int8)(Script - 1) <= 1u && (unsigned __int8)GetBidiClass(v7, v8) <= 1u )
          Script = 3;
        if ( !(unsigned __int8)unicode_analysis::script_analysis::ScriptItemizer_unicode_analysis::text_iterator::TextIteratorImpl_unicode_analysis::text_iterator::char_source::AnalysisCharSource_unicode_interop::BridgeAnalysisSource_dwrite::text_analyzer::IDWriteTextAnalysisSource_______::parse_specific_unicode_analysis::text_iterator::TextIteratorImpl_unicode_analysis::text_iterator::char_source::AnalysisCharSource_unicode_interop::BridgeAnalysisSource_dwrite::text_analyzer::IDWriteTextAnalysisSource_______(&pperrinfo) )
        {
          if ( Script == 1 && (unsigned __int8)GetGeneralCategory(v30) <= 1u )
          {
            v32 = 257;
            do
            {
              unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_unicode_interop::BridgeAnalysisSource_dwrite::text_analyzer::IDWriteTextAnalysisSource_____(&pperrinfo);
              v9 = v30;
              Script = GetScript(v30);
            }
            while ( Script == 1 && v28 < v29 && (unsigned __int8)GetGeneralCategory(v9) < 2u );
          }
          else if ( v28 < v29 )
          {
            while ( 1 )
            {
              unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_unicode_interop::BridgeAnalysisSource_dwrite::text_analyzer::IDWriteTextAnalysisSource_____(&pperrinfo);
              v10 = v30;
              v12 = GetScript(v30);
              Script = v12;
              if ( (unsigned __int8)(v12 - 1) <= 1u && (unsigned __int8)GetBidiClass(v10, v11) <= 1u )
              {
                v12 = 3;
                if ( (_BYTE)v32 == 81 )
                  v12 = 81;
                Script = v12;
              }
              if ( v28 >= v29 )
                break;
              if ( v12 == 1 )
              {
                if ( (unsigned __int8)GetGeneralCategory(v10) < 2u )
                  break;
              }
              else if ( v12 != 2 )
              {
                break;
              }
            }
            unicode_analysis::script_analysis::ScriptItemizer_unicode_analysis::text_iterator::TextIteratorImpl_unicode_analysis::text_iterator::char_source::AnalysisCharSource_unicode_interop::BridgeAnalysisSource_dwrite::text_analyzer::IDWriteTextAnalysisSource_______::parse_specific_unicode_analysis::text_iterator::TextIteratorImpl_unicode_analysis::text_iterator::char_source::AnalysisCharSource_unicode_interop::BridgeAnalysisSource_dwrite::text_analyzer::IDWriteTextAnalysisSource_______(&pperrinfo);
          }
        }
        v19 = v27;
        v18 = pperrinfo;
        v13 = v28;
        if ( v28 <= v5 )
          core::panicking::panic(
            "assertion failed: item.get_end_pos().get_text_pos() > pos.get_text_pos()d:\\os\\src\\onecoreuap\\windows\\di"
            "rectwrite\\dwritecore-copy\\rust\\unicode_analysis\\src\\script_analysis.rs",
            72,
            &off_180337390);
        v6 = v29;
        v7 = v30;
        v24[0] = (unsigned __int8)v32;
        v25 = HIBYTE(v32) & 1;
        v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _WORD *))(*(_QWORD *)a5 + 24LL))(
                a5,
                (unsigned int)v5,
                (unsigned int)(v28 - v5),
                v24);
        if ( v14 < 0 )
        {
          pperrinfo.m256i_i64[0] = 0;
          v17 = v14;
          GetErrorInfo(0, (IErrorInfo **)&pperrinfo);
          pperrinfo.m256i_i32[2] = v17;
          core::result::unwrap_failed(
            (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
            43,
            (unsigned int)&pperrinfo,
            (unsigned int)&off_180348D30,
            (__int64)&off_180348DF8);
        }
        v21 = v19;
        v20 = v18;
        v5 = v13;
      }
      while ( v13 < v6 );
    }
    return 0;
  }
  else
  {
    pperrinfo.m256i_i64[0] = 0;
    GetErrorInfo(0, (IErrorInfo **)&pperrinfo);
    v15 = -2147024809;
    if ( pperrinfo.m256i_i64[0] )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)pperrinfo.m256i_i64[0] + 16LL))(pperrinfo.m256i_i64[0]);
  }
  return v15;
}

```

## disassembly

```asm
0x180002e30  push    rbp
0x180002e31  push    r15
0x180002e33  push    r14
0x180002e35  push    r13
0x180002e37  push    r12
0x180002e39  push    rsi
0x180002e3a  push    rdi
0x180002e3b  push    rbx
0x180002e3c  sub     rsp, 128h
0x180002e43  lea     rbp, [rsp+80h]
0x180002e4b  mov     [rbp+0E0h+var_48], 0FFFFFFFFFFFFFFFEh
0x180002e56  test    rdx, rdx
0x180002e59  jz      loc_180003134
0x180002e5f  mov     rsi, [rbp+0E0h+arg_20]
0x180002e66  mov     [rbp+0E0h+var_C0], rdx
0x180002e6a  test    rsi, rsi
0x180002e6d  jz      loc_180003134
0x180002e73  lea     rax, [rbp+0E0h+var_C0]
0x180002e77  mov     [rbp+0E0h+var_C8], rax
0x180002e7b  mov     eax, r8d
0x180002e7e  mov     ecx, r9d
0x180002e81  add     rcx, rax
0x180002e84  mov     [rbp+0E0h+pperrinfo], 2
0x180002e8c  xorps   xmm0, xmm0
0x180002e8f  movups  xmmword ptr [rbp+0E0h+pperrinfo+8], xmm0
0x180002e93  lea     rdx, [rbp+0E0h+var_C8]
0x180002e97  mov     [rbp+0E0h+var_88], rdx
0x180002e9b  mov     qword ptr [rbp+0E0h+var_80], rax
0x180002e9f  mov     qword ptr [rbp+0E0h+var_80+8], rcx
0x180002ea3  mov     [rbp+0E0h+var_60], 0
0x180002ead  mov     [rbp+0E0h+var_70], rax
0x180002eb1  mov     [rbp+0E0h+var_68], rcx
0x180002eb5  lea     rcx, [rbp+0E0h+pperrinfo]
0x180002eb9  call    unicode_analysis__text_iterator__impl$1__advance_unicode_analysis__text_iterator__char_source__AnalysisCharSource_unicode_interop__BridgeAnalysisSource_dwrite__text_analyzer__IDWriteTextAnalysisSource_____
0x180002ebe  movups  xmm0, xmmword ptr [rbp+0E0h+pperrinfo]
0x180002ec2  movups  xmm1, xmmword ptr [rbp+50h]
0x180002ec6  movups  xmm2, [rbp+0E0h+var_80]
0x180002eca  movaps  [rbp+0E0h+var_E0], xmm2
0x180002ece  movaps  [rbp+0E0h+var_F0], xmm1
0x180002ed2  movaps  [rbp+0E0h+var_100], xmm0
0x180002ed6  mov     r13, [rbp+0E0h+var_70]
0x180002eda  mov     r12, [rbp+0E0h+var_68]
0x180002ede  cmp     r13, r12
0x180002ee1  jnb     loc_180003130
0x180002ee7  mov     r15d, [rbp+0E0h+var_60]
0x180002eee  lea     rdi, [rbp+0E0h+pperrinfo]
0x180002ef2  lea     rbx, [rbp+0E0h+var_B8]
0x180002ef6  nop     word ptr [rax+rax+00000000h]
0x180002f00  movaps  xmm0, [rbp+0E0h+var_100]
0x180002f04  movaps  xmm1, [rbp+0E0h+var_F0]
0x180002f08  movaps  xmm2, [rbp+0E0h+var_E0]
0x180002f0c  movaps  [rbp+0E0h+var_80], xmm2
0x180002f10  movaps  xmmword ptr [rbp+50h], xmm1
0x180002f14  movaps  xmmword ptr [rbp+0E0h+pperrinfo], xmm0
0x180002f18  mov     [rbp+0E0h+var_70], r13
0x180002f1c  mov     [rbp+0E0h+var_68], r12
0x180002f20  mov     [rbp+0E0h+var_60], r15d
0x180002f27  mov     [rbp+0E0h+var_57], 0
0x180002f30  mov     ecx, r15d
0x180002f33  call    GetScript
0x180002f38  mov     [rbp+0E0h+var_58], al
0x180002f3e  dec     al
0x180002f40  cmp     al, 1
0x180002f42  ja      short loc_180002F57
0x180002f44  mov     ecx, r15d
0x180002f47  call    GetBidiClass
0x180002f4c  cmp     al, 1
0x180002f4e  ja      short loc_180002F57
0x180002f50  mov     [rbp+0E0h+var_58], 3
0x180002f57  mov     rcx, rdi
0x180002f5a  call    unicode_analysis__script_analysis__ScriptItemizer_unicode_analysis__text_iterator__TextIteratorImpl_unicode_analysis__text_iterator__char_source__AnalysisCharSource_unicode_interop__BridgeAnalysisSource_dwrite__text_analyzer__IDWriteTextAnalysisSource_________parse_specific_unicode_analysis__text_iterator__TextIteratorImpl_unicode_analysis__text_iterator__char_source__AnalysisCharSource_unicode_interop__BridgeAnalysisSource_dwrite__text_analyzer__IDWriteTextAnalysisSource_______
0x180002f5f  test    al, al
0x180002f61  jnz     loc_1800030A0
0x180002f67  cmp     [rbp+0E0h+var_58], 1
0x180002f6e  jnz     short loc_180002FE0
0x180002f70  mov     ecx, [rbp+0E0h+var_60]
0x180002f76  call    GetGeneralCategory
0x180002f7b  cmp     al, 1
0x180002f7d  ja      short loc_180002FE0
0x180002f7f  mov     [rbp+0E0h+var_57], 101h
0x180002f88  nop     dword ptr [rax+rax+00000000h]
0x180002f90  mov     rcx, rdi
0x180002f93  call    unicode_analysis__text_iterator__impl$1__advance_unicode_analysis__text_iterator__char_source__AnalysisCharSource_unicode_interop__BridgeAnalysisSource_dwrite__text_analyzer__IDWriteTextAnalysisSource_____
0x180002f98  mov     r15d, [rbp+0E0h+var_60]
0x180002f9f  mov     ecx, r15d
0x180002fa2  call    GetScript
0x180002fa7  mov     [rbp+0E0h+var_58], al
0x180002fad  cmp     al, 1
0x180002faf  jnz     loc_1800030A0
0x180002fb5  mov     rax, [rbp+0E0h+var_68]
0x180002fb9  cmp     [rbp+0E0h+var_70], rax
0x180002fbd  jnb     loc_1800030A0
0x180002fc3  mov     ecx, r15d
0x180002fc6  call    GetGeneralCategory
0x180002fcb  cmp     al, 2
0x180002fcd  jb      short loc_180002F90
0x180002fcf  jmp     loc_1800030A0
0x180002fe0  mov     rax, [rbp+0E0h+var_70]
0x180002fe4  cmp     rax, [rbp+0E0h+var_68]
0x180002fe8  jnb     loc_1800030A0
0x180002fee  mov     rcx, rdi
0x180002ff1  call    unicode_analysis__text_iterator__impl$1__advance_unicode_analysis__text_iterator__char_source__AnalysisCharSource_unicode_interop__BridgeAnalysisSource_dwrite__text_analyzer__IDWriteTextAnalysisSource_____
0x180002ff6  nop     word ptr [rax+rax+00000000h]
0x180003000  mov     r15d, [rbp+0E0h+var_60]
0x180003007  mov     ecx, r15d
0x18000300a  call    GetScript
0x18000300f  mov     r12d, eax
0x180003012  mov     [rbp+0E0h+var_58], al
0x180003018  dec     al
0x18000301a  cmp     al, 1
0x18000301c  ja      short loc_180003047
0x18000301e  mov     ecx, r15d
0x180003021  call    GetBidiClass
0x180003026  cmp     al, 1
0x180003028  ja      short loc_180003047
0x18000302a  cmp     byte ptr [rbp+0E0h+var_57], 51h ; 'Q'
0x180003031  mov     r12d, 3
0x180003037  mov     eax, 51h ; 'Q'
0x18000303c  cmovz   r12d, eax
0x180003040  mov     [rbp+0E0h+var_58], r12b
0x180003047  mov     rax, [rbp+0E0h+var_70]
0x18000304b  cmp     rax, [rbp+0E0h+var_68]
0x18000304f  jnb     short loc_180003089
0x180003051  cmp     r12b, 1
0x180003055  jz      short loc_180003070
0x180003057  movzx   eax, r12b
0x18000305b  cmp     eax, 2
0x18000305e  jz      short loc_18000307C
0x180003060  jmp     short loc_180003089
0x180003070  mov     ecx, r15d
0x180003073  call    GetGeneralCategory
0x180003078  cmp     al, 2
0x18000307a  jb      short loc_180003089
0x18000307c  mov     rcx, rdi
0x18000307f  call    unicode_analysis__text_iterator__impl$1__advance_unicode_analysis__text_iterator__char_source__AnalysisCharSource_unicode_interop__BridgeAnalysisSource_dwrite__text_analyzer__IDWriteTextAnalysisSource_____
0x180003084  jmp     loc_180003000
0x180003089  mov     rcx, rdi
0x18000308c  call    unicode_analysis__script_analysis__ScriptItemizer_unicode_analysis__text_iterator__TextIteratorImpl_unicode_analysis__text_iterator__char_source__AnalysisCharSource_unicode_interop__BridgeAnalysisSource_dwrite__text_analyzer__IDWriteTextAnalysisSource_________parse_specific_unicode_analysis__text_iterator__TextIteratorImpl_unicode_analysis__text_iterator__char_source__AnalysisCharSource_unicode_interop__BridgeAnalysisSource_dwrite__text_analyzer__IDWriteTextAnalysisSource_______
0x180003091  nop     word ptr [rax+rax+00000000h]
0x1800030a0  movaps  xmm0, xmmword ptr [rbp+0E0h+pperrinfo]
0x1800030a4  movaps  xmm1, xmmword ptr [rbp+50h]
0x1800030a8  movaps  xmm2, [rbp+0E0h+var_80]
0x1800030ac  movaps  [rbp+0E0h+var_110], xmm2
0x1800030b0  movaps  [rbp+0E0h+var_120], xmm1
0x1800030b4  movaps  [rbp+0E0h+var_130], xmm0
0x1800030b8  mov     r14, [rbp+0E0h+var_70]
0x1800030bc  cmp     r14, r13
0x1800030bf  jbe     loc_180003179
0x1800030c5  mov     r12, [rbp+0E0h+var_68]
0x1800030c9  mov     r15d, [rbp+0E0h+var_60]
0x1800030d0  movzx   eax, byte ptr [rbp+0E0h+var_57]
0x1800030d7  movzx   ecx, byte ptr [rbp+0E0h+var_57+1]
0x1800030de  and     ecx, 1
0x1800030e1  mov     [rbp+0E0h+var_B8], ax
0x1800030e5  mov     [rbp+0E0h+var_B4], ecx
0x1800030e8  mov     r8d, r14d
0x1800030eb  sub     r8d, r13d
0x1800030ee  mov     rax, [rsi]
0x1800030f1  mov     rax, [rax+18h]
0x1800030f5  mov     rcx, rsi
0x1800030f8  mov     edx, r13d
0x1800030fb  mov     r9, rbx
0x1800030fe  call    cs:__guard_dispatch_icall_fptr
0x180003104  test    eax, eax
0x180003106  js      loc_180003193
0x18000310c  movaps  xmm0, [rbp+0E0h+var_130]
0x180003110  movaps  xmm1, [rbp+0E0h+var_120]
0x180003114  movaps  xmm2, [rbp+0E0h+var_110]
0x180003118  movaps  [rbp+0E0h+var_E0], xmm2
0x18000311c  movaps  [rbp+0E0h+var_F0], xmm1
0x180003120  movaps  [rbp+0E0h+var_100], xmm0
0x180003124  mov     r13, r14
0x180003127  cmp     r14, r12
0x18000312a  jb      loc_180002F00
0x180003130  xor     esi, esi
0x180003132  jmp     short loc_180003163
0x180003134  mov     [rbp+0E0h+pperrinfo], 0
0x18000313c  lea     rdx, [rbp+0E0h+pperrinfo]; pperrinfo
0x180003140  xor     ecx, ecx; dwReserved
0x180003142  call    cs:__imp_GetErrorInfo
0x180003148  mov     rcx, [rbp+0E0h+pperrinfo]
0x18000314c  mov     esi, 80070057h
0x180003151  test    rcx, rcx
0x180003154  jz      short loc_180003163
0x180003156  mov     rax, [rcx]
0x180003159  mov     rax, [rax+10h]
0x18000315d  call    cs:__guard_dispatch_icall_fptr
0x180003163  mov     eax, esi
0x180003165  add     rsp, 128h
0x18000316c  pop     rbx
0x18000316d  pop     rdi
0x18000316e  pop     rsi
0x18000316f  pop     r12
0x180003171  pop     r13
0x180003173  pop     r14
0x180003175  pop     r15
0x180003177  pop     rbp
0x180003178  retn
0x180003179  lea     rcx, aAssertionFaile; "assertion failed: item.get_end_pos().ge"...
0x180003180  lea     r8, off_180337390; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x180003187  mov     edx, 48h ; 'H'
0x18000318c  call    core__panicking__panic
0x180003191  jmp     short loc_1800031DC
0x180003193  mov     [rbp+0E0h+pperrinfo], 0
0x18000319b  lea     rdx, [rbp+0E0h+pperrinfo]; pperrinfo
0x18000319f  xor     ecx, ecx; dwReserved
0x1800031a1  mov     esi, eax
0x1800031a3  call    cs:__imp_GetErrorInfo
0x1800031a9  mov     rax, [rbp+0E0h+pperrinfo]
0x1800031ad  mov     [rbp+0E0h+pperrinfo], rax
0x1800031b1  mov     dword ptr [rbp+0E0h+pperrinfo+8], esi
0x1800031b4  lea     rax, off_180348DF8; "rust\\unicode_interop\\src\\lib.rs"
0x1800031bb  mov     [rsp+160h+var_140], rax
0x1800031c0  lea     rcx, aAssertionFaile_1+1Eh; "called `Result::unwrap()` on an `Err` v"...
0x1800031c7  lea     r9, off_180348D30
0x1800031ce  lea     r8, [rbp+0E0h+pperrinfo]
0x1800031d2  mov     edx, 2Bh ; '+'
0x1800031d7  call    core__result__unwrap_failed
0x1800031dc  ud2
0x1800031de  mov     rax, [rbp+0E0h+var_A8]
0x1800031e2  mov     rax, [rax]
0x1800031e5  test    rax, rax
0x1800031e8  jz      short loc_1800031F4
0x1800031ea  mov     rcx, [rbp+0E0h+var_B0]
0x1800031ee  call    cs:__guard_dispatch_icall_fptr
0x1800031f4  mov     esi, 80004005h
0x1800031f9  mov     rax, [rbp+0E0h+var_A8]
0x1800031fd  cmp     qword ptr [rax+8], 0
0x180003202  jz      loc_180003163
0x180003208  mov     rdx, [rax+10h]
0x18000320c  mov     rcx, [rbp+0E0h+var_B0]
0x180003210  call    sub_180022DE0
0x180003215  jmp     loc_180003163
```

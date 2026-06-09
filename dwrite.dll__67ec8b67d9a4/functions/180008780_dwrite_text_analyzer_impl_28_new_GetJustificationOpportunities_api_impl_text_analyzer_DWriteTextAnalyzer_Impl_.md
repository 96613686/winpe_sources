# dwrite::text_analyzer::impl$28::new::GetJustificationOpportunities_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_

- ea: `0x180008780`
- end: `0x180008a4d`
- name: `dwrite::text_analyzer::impl$28::new::GetJustificationOpportunities_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_`
- size: `717`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180008780`
- `0x180022de0`
- `0x180057730`
- `0x180316190`
- `0x180316ae0`
- `0x180316ee0`

## import_xrefs

- `oleaut32!GetErrorInfo` at `0x180008809`
- `oleaut32!GetErrorInfo` at `0x1800089d2`
- `oleaut32!GetErrorInfo` at `0x180008809`
- `oleaut32!GetErrorInfo` at `0x1800089d2`

## string_xrefs

- `0x180008999`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall dwrite::text_analyzer::impl_28::new::GetJustificationOpportunities_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_(
        __int64 a1,
        __int64 a2,
        float a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v10; // rdi
  __int64 v11; // r10
  unsigned int v12; // esi
  __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rsi
  void (__fastcall *v17)(__int64); // rax
  __int64 *v18; // rcx
  char v19; // bl
  __int64 result; // rax
  int v21; // esi
  __int64 v22; // rdx
  __int64 v23; // [rsp+80h] [rbp+0h] BYREF
  __int64 v24; // [rsp+88h] [rbp+8h]
  __int64 v25; // [rsp+90h] [rbp+10h] BYREF
  __int64 v26; // [rsp+98h] [rbp+18h]
  IErrorInfo *pperrinfo; // [rsp+A0h] [rbp+20h] BYREF
  int v28; // [rsp+A8h] [rbp+28h]
  __int64 v29; // [rsp+B0h] [rbp+30h]
  char v30; // [rsp+BFh] [rbp+3Fh]
  __int64 v31; // [rsp+C0h] [rbp+40h]
  __int64 v32; // [rsp+C8h] [rbp+48h] BYREF

  v31 = -2;
  if ( a3 < 0.0 )
  {
LABEL_4:
    pperrinfo = 0;
    GetErrorInfo(0, &pperrinfo);
    v12 = -2147024809;
    if ( pperrinfo )
      ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
    goto LABEL_18;
  }
  if ( !a6 )
  {
LABEL_17:
    v12 = 0;
    goto LABEL_18;
  }
  v11 = a7;
  if ( a9 == 0 || a5 == 0 || a7 == 0 || a8 == 0 )
    goto LABEL_4;
  try
  {
    v25 = 0;
    if ( a2 )
    {
      v29 = a4;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
      v23 = 0;
      v14 = a2;
      v15 = (**(__int64 (__fastcall ***)(__int64, int *, __int64 *))a2)(a2, &dword_1803B3704, &v23);
      if ( v15 < 0 )
      {
        v29 = a2;
        v21 = v15;
      }
      else
      {
        v10 = v23;
        if ( v23 )
        {
          v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 544LL))(v23);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
          v17 = *(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL);
          v25 = v16;
          v17(v14);
          v18 = &v25;
          v19 = 1;
          LODWORD(a4) = v29;
          v11 = a7;
LABEL_11:
          if ( !a10 )
          {
            v24 = v16;
            v30 = v19;
            core::panicking::panic(
              "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\inte"
              "rop_utils\\src\\lib.rs",
              32,
              &off_180348CA0);
          }
          v24 = v16;
          v30 = v19;
          layout::justification::get_justification_opportunities(
            (_DWORD)v18,
            a10,
            a4,
            a5,
            a6,
            v11,
            a5,
            a8,
            a5,
            a9,
            a6,
            a10,
            a6);
          goto LABEL_29;
        }
        v29 = a2;
        v21 = -2147467261;
      }
      pperrinfo = 0;
      GetErrorInfo(0, &pperrinfo);
      v28 = v21;
      core::result::unwrap_failed(
        (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
        43,
        (unsigned int)&pperrinfo,
        (unsigned int)&off_180335008,
        (__int64)&off_1803350B8);
    }
    v16 = 0;
    v19 = 0;
    LODWORD(v18) = 0;
    goto LABEL_11;
  }
  catch ( __int64 v32 )
  {
    v26 = std::panicking::catch_unwind::cleanup(v32);
    v29 = v22;
    if ( *(_QWORD *)v29 )
      (*(void (__fastcall **)(__int64))v29)(v26);
    v12 = -2147467259;
    if ( *(_QWORD *)(v29 + 8) )
      sub_180022DE0(v26, *(_QWORD *)(v29 + 16));
LABEL_18:
    result = v12;
  }
  catch ( ... )
  {
    std::panicking::__rust_foreign_exception();
  }
LABEL_29:
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  goto LABEL_17;
}

```

## disassembly

```asm
0x180008780  push    rbp
0x180008781  push    r15
0x180008783  push    r14
0x180008785  push    r13
0x180008787  push    r12
0x180008789  push    rsi
0x18000878a  push    rdi
0x18000878b  push    rbx
0x18000878c  sub     rsp, 0E8h
0x180008793  lea     rbp, [rsp+80h]
0x18000879b  movaps  [rbp+0A0h+var_50], xmm6
0x18000879f  mov     [rbp+0A0h+var_60], 0FFFFFFFFFFFFFFFEh
0x1800087a7  xorps   xmm0, xmm0
0x1800087aa  ucomiss xmm2, xmm0
0x1800087ad  jb      short loc_1800087FB
0x1800087af  mov     r12d, [rbp+0A0h+arg_28]
0x1800087b6  test    r12d, r12d
0x1800087b9  jz      loc_180008972
0x1800087bf  mov     r15, [rbp+0A0h+arg_40]
0x1800087c6  mov     r14, [rbp+0A0h+arg_38]
0x1800087cd  mov     r10, [rbp+0A0h+arg_30]
0x1800087d4  mov     r13d, [rbp+0A0h+arg_20]
0x1800087db  test    r13d, r13d
0x1800087de  setnz   al
0x1800087e1  test    r10, r10
0x1800087e4  setnz   cl
0x1800087e7  and     cl, al
0x1800087e9  test    r14, r14
0x1800087ec  setnz   al
0x1800087ef  and     al, cl
0x1800087f1  test    r15, r15
0x1800087f4  setnz   cl
0x1800087f7  test    al, cl
0x1800087f9  jnz     short loc_180008833
0x1800087fb  mov     [rbp+0A0h+pperrinfo], 0
0x180008803  lea     rdx, [rbp+0A0h+pperrinfo]; pperrinfo
0x180008807  xor     ecx, ecx; dwReserved
0x180008809  call    cs:__imp_GetErrorInfo
0x18000880f  mov     rcx, [rbp+0A0h+pperrinfo]
0x180008813  mov     esi, 80070057h
0x180008818  test    rcx, rcx
0x18000881b  jz      loc_180008974
0x180008821  mov     rax, [rcx]
0x180008824  mov     rax, [rax+10h]
0x180008828  call    cs:__guard_dispatch_icall_fptr
0x18000882e  jmp     loc_180008974
0x180008833  mov     [rbp+0A0h+var_90], 0
0x18000883b  test    rdx, rdx
0x18000883e  jz      loc_1800088E7
0x180008844  movaps  xmm6, xmm2
0x180008847  mov     [rbp+0A0h+var_70], r9
0x18000884b  mov     rax, [rdx]
0x18000884e  mov     rax, [rax+8]
0x180008852  mov     rcx, rdx
0x180008855  mov     rsi, rdx
0x180008858  call    cs:__guard_dispatch_icall_fptr
0x18000885e  mov     [rbp+0A0h+var_A0], 0
0x180008866  mov     rax, [rsi]
0x180008869  mov     rax, [rax]
0x18000886c  lea     rdx, dword_1803B3704
0x180008873  mov     r8, rbp
0x180008876  mov     rbx, rsi
0x180008879  mov     rcx, rsi
0x18000887c  call    cs:__guard_dispatch_icall_fptr
0x180008882  test    eax, eax
0x180008884  js      loc_1800089B3
0x18000888a  mov     rdi, [rbp+0A0h+var_A0]
0x18000888e  test    rdi, rdi
0x180008891  jz      loc_1800089BB
0x180008897  mov     rax, [rdi]
0x18000889a  mov     rax, [rax+220h]
0x1800088a1  mov     rcx, rdi
0x1800088a4  call    cs:__guard_dispatch_icall_fptr
0x1800088aa  mov     rsi, rax
0x1800088ad  mov     rax, [rax]
0x1800088b0  mov     rax, [rax+8]
0x1800088b4  mov     rcx, rsi
0x1800088b7  call    cs:__guard_dispatch_icall_fptr
0x1800088bd  mov     rcx, rbx
0x1800088c0  mov     rax, [rbx]
0x1800088c3  mov     rax, [rax+10h]
0x1800088c7  mov     [rbp+0A0h+var_90], rsi
0x1800088cb  call    cs:__guard_dispatch_icall_fptr
0x1800088d1  lea     rcx, [rbp+0A0h+var_90]
0x1800088d5  mov     bl, 1
0x1800088d7  mov     r9, [rbp+0A0h+var_70]
0x1800088db  movaps  xmm2, xmm6
0x1800088de  mov     r10, [rbp+0A0h+arg_30]
0x1800088e5  jmp     short loc_1800088ED
0x1800088e7  xor     esi, esi
0x1800088e9  xor     ebx, ebx
0x1800088eb  xor     ecx, ecx
0x1800088ed  mov     rdx, [rbp+0A0h+arg_48]
0x1800088f4  test    rdx, rdx
0x1800088f7  jz      loc_18000898E
0x1800088fd  mov     r8d, r12d
0x180008900  mov     eax, r13d
0x180008903  mov     [rbp+0A0h+var_98], rsi
0x180008907  mov     [rbp+0A0h+var_A8], rdi
0x18000890b  mov     [rbp+0A0h+var_61], bl
0x18000890e  mov     [rsp+120h+var_C0], r8
0x180008913  mov     [rsp+120h+var_C8], rdx
0x180008918  mov     [rsp+120h+var_D0], r8
0x18000891d  mov     [rsp+120h+var_D8], r15
0x180008922  mov     [rsp+120h+var_E0], rax
0x180008927  mov     [rsp+120h+var_E8], r14
0x18000892c  mov     [rsp+120h+var_F0], rax
0x180008931  mov     [rsp+120h+var_F8], r10
0x180008936  mov     [rsp+120h+var_100], r8
0x18000893b  movaps  xmm1, xmm2
0x18000893e  mov     r8d, r9d
0x180008941  mov     r9, rax
0x180008944  call    layout__justification__get_justification_opportunities
0x180008949  test    bl, bl
0x18000894b  jz      short loc_18000895D
0x18000894d  mov     rax, [rdi]
0x180008950  mov     rax, [rax+10h]
0x180008954  mov     rcx, rdi
0x180008957  call    cs:__guard_dispatch_icall_fptr
0x18000895d  test    rsi, rsi
0x180008960  jz      short loc_180008972
0x180008962  mov     rax, [rsi]
0x180008965  mov     rax, [rax+10h]
0x180008969  mov     rcx, rsi
0x18000896c  call    cs:__guard_dispatch_icall_fptr
0x180008972  xor     esi, esi
0x180008974  mov     eax, esi
0x180008976  movaps  xmm6, [rbp+0A0h+var_50]
0x18000897a  add     rsp, 0E8h
0x180008981  pop     rbx
0x180008982  pop     rdi
0x180008983  pop     rsi
0x180008984  pop     r12
0x180008986  pop     r13
0x180008988  pop     r14
0x18000898a  pop     r15
0x18000898c  pop     rbp
0x18000898d  retn
0x18000898e  mov     [rbp+0A0h+var_98], rsi
0x180008992  mov     [rbp+0A0h+var_A8], rdi
0x180008996  mov     [rbp+0A0h+var_61], bl
0x180008999  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x1800089a0  lea     r8, off_180348CA0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x1800089a7  mov     edx, 20h ; ' '
0x1800089ac  call    core__panicking__panic
0x1800089b1  jmp     short loc_180008A0B
0x1800089b3  mov     [rbp+0A0h+var_70], rbx
0x1800089b7  mov     esi, eax
0x1800089b9  jmp     short loc_1800089C4
0x1800089bb  mov     [rbp+0A0h+var_70], rbx
0x1800089bf  mov     esi, 80004003h
0x1800089c4  mov     [rbp+0A0h+pperrinfo], 0
0x1800089cc  lea     rdx, [rbp+0A0h+pperrinfo]; pperrinfo
0x1800089d0  xor     ecx, ecx; dwReserved
0x1800089d2  call    cs:__imp_GetErrorInfo
0x1800089d8  mov     rax, [rbp+0A0h+pperrinfo]
0x1800089dc  mov     [rbp+0A0h+pperrinfo], rax
0x1800089e0  mov     [rbp+0A0h+var_78], esi
0x1800089e3  lea     rax, off_1803350B8; "rust\\api_impl\\src\\font_face.rs"
0x1800089ea  mov     [rsp+120h+var_100], rax
0x1800089ef  lea     rcx, aAssertionFaile_1+1Eh; "called `Result::unwrap()` on an `Err` v"...
0x1800089f6  lea     r9, off_180335008
0x1800089fd  lea     r8, [rbp+0A0h+pperrinfo]
0x180008a01  mov     edx, 2Bh ; '+'
0x180008a06  call    core__result__unwrap_failed
0x180008a0b  ud2
0x180008a0d  mov     rax, [rbp+0A0h+var_70]
0x180008a11  mov     rax, [rax]
0x180008a14  test    rax, rax
0x180008a17  jz      short loc_180008A23
0x180008a19  mov     rcx, [rbp+0A0h+var_88]
0x180008a1d  call    cs:__guard_dispatch_icall_fptr
0x180008a23  mov     esi, 80004005h
0x180008a28  mov     rax, [rbp+0A0h+var_70]
0x180008a2c  cmp     qword ptr [rax+8], 0
0x180008a31  jz      loc_180008974
0x180008a37  mov     rax, [rbp+0A0h+var_70]
0x180008a3b  mov     rdx, [rax+10h]
0x180008a3f  mov     rcx, [rbp+0A0h+var_88]
0x180008a43  call    sub_180022DE0
0x180008a48  jmp     loc_180008974
```

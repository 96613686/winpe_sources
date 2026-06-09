# DiagnosisTextBuilderImpl::GetXML(ushort * *)

- ea: `0x18000dec4`
- end: `0x18000e2bc`
- name: `?GetXML@DiagnosisTextBuilderImpl@@QEAAJPEAPEAG@Z`
- size: `1016`
- prototype: `__int64 __fastcall(DiagnosisTextBuilderImpl *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009700`

## callees

- `0x180008a4c`
- `0x18000db3c`
- `0x18000dd14`
- `0x18000dec4`
- `0x180011302`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000df77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000df77`

## string_xrefs

- `0x18000e06b`: `</Parameters><Extensions>`
- `0x18000e0aa`: `</Extensions></DiagnosticsText>`
- `0x18000e134`: `<Extension><Name><![CDATA[%s]]></Name><Value><![CDATA[%s]]></Value></Extension>`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DiagnosisTextBuilderImpl::GetXML(DiagnosisTextBuilderImpl *this, unsigned __int16 **a2)
{
  unsigned int v3; // r12d
  const unsigned __int16 *v4; // rsi
  __int64 *v5; // rbx
  const unsigned __int16 *v6; // rdi
  __int64 *v7; // rbx
  unsigned __int64 v8; // r14
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r11
  __int64 v13; // rax
  __int64 v14; // r11
  __int64 v15; // rax
  __int64 v16; // r11
  __int64 v17; // rax
  __int64 v18; // r11
  __int64 v19; // rax
  __int64 v20; // r11
  __int64 v21; // rax
  __int64 v22; // r11
  __int64 v23; // rax
  __int64 v24; // r11
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 *i; // rax
  __int64 *v28; // rcx
  __int64 v29; // rdi
  __int64 *j; // rax
  __int64 *v31; // rcx
  __int64 v33; // [rsp+20h] [rbp-48h] BYREF
  ATL::CAtlException *v34; // [rsp+28h] [rbp-40h] BYREF
  __int64 v36; // [rsp+80h] [rbp+18h] BYREF
  const unsigned __int16 *v37; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  v4 = (const unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v37 = v4;
  v5 = (__int64 *)**((_QWORD **)this + 3);
  try
  {
    while ( 1 )
    {
      if ( v5 == *((__int64 **)this + 3) )
      {
        v6 = (const unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        v36 = (__int64)v6;
        v7 = (__int64 *)**((_QWORD **)this + 5);
        while ( 1 )
        {
          if ( v7 == *((__int64 **)this + 5) )
          {
            v8 = *((int *)v6 - 4)
               + *(int *)(*((_QWORD *)this + 1) - 16LL)
               + 152LL
               + *(int *)(*((_QWORD *)this + 2) - 16LL)
               + *((int *)v4 - 4);
            v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
            v10 = v9;
            if ( v9 )
            {
              memset_0(v9, 0, 2 * v8);
              StringCchCopyW(v10, v8, L"<DiagnosticsText><Title><![CDATA[");
              v11 = -1;
              do
                ++v11;
              while ( v10[v11] );
              StringCchCopyW(&v10[v11], v8 - v11, *((const unsigned __int16 **)this + 1));
              v13 = v12;
              do
                ++v13;
              while ( v10[v13] );
              StringCchCopyW(&v10[v13], v8 - v13, L"]]></Title><Description><![CDATA[");
              v15 = v14;
              do
                ++v15;
              while ( v10[v15] );
              StringCchCopyW(&v10[v15], v8 - v15, *((const unsigned __int16 **)this + 2));
              v17 = v16;
              do
                ++v17;
              while ( v10[v17] );
              StringCchCopyW(&v10[v17], v8 - v17, L"]]></Description><Parameters>");
              v19 = v18;
              do
                ++v19;
              while ( v10[v19] );
              StringCchCopyW(&v10[v19], v8 - v19, v4);
              v21 = v20;
              do
                ++v21;
              while ( v10[v21] );
              StringCchCopyW(&v10[v21], v8 - v21, L"</Parameters><Extensions>");
              v23 = v22;
              do
                ++v23;
              while ( v10[v23] );
              StringCchCopyW(&v10[v23], v8 - v23, v6);
              v25 = v24;
              do
                ++v25;
              while ( v10[v25] );
              StringCchCopyW(&v10[v25], v8 - v25, L"</Extensions></DiagnosticsText>");
              *a2 = v10;
            }
            else
            {
              v3 = -2147024882;
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 - 2, 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 - 3) + 8LL))(*((_QWORD *)v6 - 3));
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 - 2, 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 - 3) + 8LL))(*((_QWORD *)v4 - 3));
            return v3;
          }
          v33 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &v33,
            L"<Extension><Name><![CDATA[%s]]></Name><Value><![CDATA[%s]]></Value></Extension>",
            v7[4],
            v7[5]);
          v26 = v33;
          ATL::CSimpleStringT<unsigned short,0>::Append(&v36, v33, *(unsigned int *)(v33 - 16));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 - 24 + 16), 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v26 - 24) + 8LL))(*(_QWORD *)(v26 - 24));
          if ( !*((_BYTE *)v7 + 25) )
          {
            i = (__int64 *)v7[2];
            if ( *((_BYTE *)i + 25) )
            {
              for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
                v7 = i;
LABEL_36:
              v7 = i;
              goto LABEL_37;
            }
            v28 = (__int64 *)*i;
            if ( *(_BYTE *)(*i + 25) )
              goto LABEL_36;
            do
            {
              v7 = v28;
              v28 = (__int64 *)*v28;
            }
            while ( !*((_BYTE *)v28 + 25) );
          }
LABEL_37:
          v6 = (const unsigned __int16 *)v36;
        }
      }
      v36 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v36,
        L"<Parameter><Name><![CDATA[%s]]></Name><Value><![CDATA[%s]]></Value></Parameter>",
        v5[4],
        v5[5]);
      v29 = v36;
      ATL::CSimpleStringT<unsigned short,0>::Append(&v37, v36, *(unsigned int *)(v36 - 16));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v29 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v29 - 24) + 8LL))(*(_QWORD *)(v29 - 24));
      if ( !*((_BYTE *)v5 + 25) )
      {
        j = (__int64 *)v5[2];
        if ( *((_BYTE *)j + 25) )
        {
          for ( j = (__int64 *)v5[1]; !*((_BYTE *)j + 25) && v5 == (__int64 *)j[2]; j = (__int64 *)j[1] )
            v5 = j;
LABEL_50:
          v5 = j;
          goto LABEL_51;
        }
        v31 = (__int64 *)*j;
        if ( *(_BYTE *)(*j + 25) )
          goto LABEL_50;
        do
        {
          v5 = v31;
          v31 = (__int64 *)*v31;
        }
        while ( !*((_BYTE *)v31 + 25) );
      }
LABEL_51:
      v4 = v37;
    }
  }
  catch ( ATL::CAtlException *v34 )
  {
    LODWORD(v36) = *(_DWORD *)v34;
    return (unsigned int)v36;
  }
  return v3;
}

```

## disassembly

```asm
0x18000dec4  mov     [rsp+arg_8], rdx
0x18000dec9  push    rbx
0x18000deca  push    rsi
0x18000decb  push    rdi
0x18000decc  push    r12
0x18000dece  push    r13
0x18000ded0  push    r14
0x18000ded2  push    r15
0x18000ded4  sub     rsp, 30h
0x18000ded8  mov     r13, rcx
0x18000dedb  xor     r14d, r14d
0x18000dede  mov     r12d, r14d
0x18000dee1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000dee8  lea     r15, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000deef  mov     rcx, r15
0x18000def2  mov     rax, [rax+18h]
0x18000def6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000defb  lea     rsi, [rax+18h]
0x18000deff  mov     [rsp+68h+arg_18], rsi
0x18000df07  mov     rbx, [r13+18h]
0x18000df0b  mov     rbx, [rbx]
0x18000df0e  cmp     rbx, [r13+18h]
0x18000df12  jnz     loc_18000E1D4
0x18000df18  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000df1f  mov     rcx, r15
0x18000df22  mov     rax, [rax+18h]
0x18000df26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df2b  lea     rdi, [rax+18h]
0x18000df2f  mov     [rsp+68h+arg_10], rdi
0x18000df37  mov     rbx, [r13+28h]
0x18000df3b  mov     rbx, [rbx]
0x18000df3e  cmp     rbx, [r13+28h]
0x18000df42  jnz     loc_18000E110
0x18000df48  mov     rax, [r13+10h]
0x18000df4c  movsxd  rdx, dword ptr [rax-10h]
0x18000df50  mov     rax, [r13+8]
0x18000df54  movsxd  rcx, dword ptr [rax-10h]
0x18000df58  add     rcx, 98h
0x18000df5f  movsxd  rax, dword ptr [rdi-10h]
0x18000df63  add     rdx, rcx
0x18000df66  movsxd  r14, dword ptr [rsi-10h]
0x18000df6a  add     rdx, rax
0x18000df6d  add     r14, rdx
0x18000df70  lea     r15, [r14+r14]
0x18000df74  mov     rcx, r15; cb
0x18000df77  call    cs:__imp_CoTaskMemAlloc
0x18000df7d  mov     rbx, rax
0x18000df80  test    rax, rax
0x18000df83  jz      loc_18000E0C3
0x18000df89  mov     r8, r15; Size
0x18000df8c  xor     edx, edx; Val
0x18000df8e  mov     rcx, rax; void *
0x18000df91  call    memset_0
0x18000df96  lea     r8, aDiagnosticstex; "<DiagnosticsText><Title><![CDATA["
0x18000df9d  mov     rdx, r14; unsigned __int64
0x18000dfa0  mov     rcx, rbx; unsigned __int16 *
0x18000dfa3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dfa8  or      r11, 0FFFFFFFFFFFFFFFFh
0x18000dfac  mov     rax, r11
0x18000dfaf  xor     r15d, r15d
0x18000dfb2  inc     rax
0x18000dfb5  cmp     [rbx+rax*2], r15w
0x18000dfba  jnz     short loc_18000DFB2
0x18000dfbc  mov     rdx, r14
0x18000dfbf  sub     rdx, rax; unsigned __int64
0x18000dfc2  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000dfc6  mov     r8, [r13+8]; unsigned __int16 *
0x18000dfca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dfcf  mov     rax, r11
0x18000dfd2  inc     rax
0x18000dfd5  cmp     [rbx+rax*2], r15w
0x18000dfda  jnz     short loc_18000DFD2
0x18000dfdc  mov     rdx, r14
0x18000dfdf  sub     rdx, rax; unsigned __int64
0x18000dfe2  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000dfe6  lea     r8, aTitleDescripti; "]]></Title><Description><![CDATA["
0x18000dfed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dff2  mov     rax, r11
0x18000dff5  inc     rax
0x18000dff8  cmp     [rbx+rax*2], r15w
0x18000dffd  jnz     short loc_18000DFF5
0x18000dfff  mov     rdx, r14
0x18000e002  sub     rdx, rax; unsigned __int64
0x18000e005  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000e009  mov     r8, [r13+10h]; unsigned __int16 *
0x18000e00d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e012  mov     rax, r11
0x18000e015  inc     rax
0x18000e018  cmp     [rbx+rax*2], r15w
0x18000e01d  jnz     short loc_18000E015
0x18000e01f  mov     rdx, r14
0x18000e022  sub     rdx, rax; unsigned __int64
0x18000e025  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000e029  lea     r8, aDescriptionPar; "]]></Description><Parameters>"
0x18000e030  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e035  mov     rax, r11
0x18000e038  inc     rax
0x18000e03b  cmp     [rbx+rax*2], r15w
0x18000e040  jnz     short loc_18000E038
0x18000e042  mov     rdx, r14
0x18000e045  sub     rdx, rax; unsigned __int64
0x18000e048  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000e04c  mov     r8, rsi; unsigned __int16 *
0x18000e04f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e054  mov     rax, r11
0x18000e057  inc     rax
0x18000e05a  cmp     [rbx+rax*2], r15w
0x18000e05f  jnz     short loc_18000E057
0x18000e061  mov     rdx, r14
0x18000e064  sub     rdx, rax; unsigned __int64
0x18000e067  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000e06b  lea     r8, aParametersExte; "</Parameters><Extensions>"
0x18000e072  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e077  mov     rax, r11
0x18000e07a  inc     rax
0x18000e07d  cmp     [rbx+rax*2], r15w
0x18000e082  jnz     short loc_18000E07A
0x18000e084  mov     rdx, r14
0x18000e087  sub     rdx, rax; unsigned __int64
0x18000e08a  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000e08e  mov     r8, rdi; unsigned __int16 *
0x18000e091  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e096  mov     rax, r11
0x18000e099  inc     rax
0x18000e09c  cmp     [rbx+rax*2], r15w
0x18000e0a1  jnz     short loc_18000E099
0x18000e0a3  sub     r14, rax
0x18000e0a6  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000e0aa  lea     r8, aExtensionsDiag; "</Extensions></DiagnosticsText>"
0x18000e0b1  mov     rdx, r14; unsigned __int64
0x18000e0b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e0b9  mov     r11, [rsp+68h+arg_8]
0x18000e0be  mov     [r11], rbx
0x18000e0c1  jmp     short loc_18000E0C9
0x18000e0c3  mov     r12d, 8007000Eh
0x18000e0c9  lea     rdx, [rdi-18h]
0x18000e0cd  or      eax, 0FFFFFFFFh
0x18000e0d0  lock xadd [rdx+10h], eax
0x18000e0d5  sub     eax, 1
0x18000e0d8  jg      short loc_18000E0EA
0x18000e0da  mov     rcx, [rdx]
0x18000e0dd  mov     rax, [rcx]
0x18000e0e0  mov     rax, [rax+8]
0x18000e0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0e9  nop
0x18000e0ea  lea     rdx, [rsi-18h]
0x18000e0ee  or      eax, 0FFFFFFFFh
0x18000e0f1  lock xadd [rdx+10h], eax
0x18000e0f6  sub     eax, 1
0x18000e0f9  jg      short loc_18000E10B
0x18000e0fb  mov     rcx, [rdx]
0x18000e0fe  mov     rax, [rcx]
0x18000e101  mov     rax, [rax+8]
0x18000e105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e10a  nop
0x18000e10b  jmp     loc_18000E2A9
0x18000e110  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e117  mov     rcx, r15
0x18000e11a  mov     rax, [rax+18h]
0x18000e11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e123  add     rax, 18h
0x18000e127  mov     [rsp+68h+var_48], rax
0x18000e12c  mov     r9, [rbx+28h]
0x18000e130  mov     r8, [rbx+20h]
0x18000e134  lea     rdx, aExtensionNameC; "<Extension><Name><![CDATA[%s]]></Name><"...
0x18000e13b  lea     rcx, [rsp+68h+var_48]
0x18000e140  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000e145  mov     rdi, [rsp+68h+var_48]
0x18000e14a  mov     r8d, [rdi-10h]
0x18000e14e  mov     rdx, rdi
0x18000e151  lea     rcx, [rsp+68h+arg_10]
0x18000e159  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000e15e  nop
0x18000e15f  lea     rdx, [rdi-18h]
0x18000e163  or      eax, 0FFFFFFFFh
0x18000e166  lock xadd [rdx+10h], eax
0x18000e16b  sub     eax, 1
0x18000e16e  jg      short loc_18000E17F
0x18000e170  mov     rcx, [rdx]
0x18000e173  mov     rax, [rcx]
0x18000e176  mov     rax, [rax+8]
0x18000e17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e17f  cmp     [rbx+19h], r14b
0x18000e183  jnz     short loc_18000E1AC
0x18000e185  mov     rax, [rbx+10h]
0x18000e189  cmp     [rax+19h], r14b
0x18000e18d  jnz     short loc_18000E1B9
0x18000e18f  mov     rcx, [rax]
0x18000e192  cmp     [rcx+19h], r14b
0x18000e196  jnz     short loc_18000E1A9
0x18000e198  mov     rbx, rcx
0x18000e19b  mov     rax, [rcx]
0x18000e19e  mov     rcx, rax
0x18000e1a1  cmp     [rax+19h], r14b
0x18000e1a5  jz      short loc_18000E198
0x18000e1a7  jmp     short loc_18000E1AC
0x18000e1a9  mov     rbx, rax
0x18000e1ac  mov     rdi, [rsp+68h+arg_10]
0x18000e1b4  jmp     loc_18000DF3E
0x18000e1b9  mov     rax, [rbx+8]
0x18000e1bd  jmp     short loc_18000E1CC
0x18000e1bf  cmp     rbx, [rax+10h]
0x18000e1c3  jnz     short loc_18000E1A9
0x18000e1c5  mov     rbx, rax
0x18000e1c8  mov     rax, [rax+8]
0x18000e1cc  cmp     [rax+19h], r14b
0x18000e1d0  jz      short loc_18000E1BF
0x18000e1d2  jmp     short loc_18000E1A9
0x18000e1d4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e1db  mov     rcx, r15
0x18000e1de  mov     rax, [rax+18h]
0x18000e1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1e7  add     rax, 18h
0x18000e1eb  mov     [rsp+68h+arg_10], rax
0x18000e1f3  mov     r9, [rbx+28h]
0x18000e1f7  mov     r8, [rbx+20h]
0x18000e1fb  lea     rdx, aParameterNameC; "<Parameter><Name><![CDATA[%s]]></Name><"...
0x18000e202  lea     rcx, [rsp+68h+arg_10]
0x18000e20a  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000e20f  mov     rdi, [rsp+68h+arg_10]
0x18000e217  mov     r8d, [rdi-10h]
0x18000e21b  mov     rdx, rdi
0x18000e21e  lea     rcx, [rsp+68h+arg_18]
0x18000e226  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000e22b  nop
0x18000e22c  lea     rdx, [rdi-18h]
0x18000e230  or      eax, 0FFFFFFFFh
0x18000e233  lock xadd [rdx+10h], eax
0x18000e238  sub     eax, 1
0x18000e23b  jg      short loc_18000E24C
0x18000e23d  mov     rcx, [rdx]
0x18000e240  mov     rax, [rcx]
0x18000e243  mov     rax, [rax+8]
0x18000e247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e24c  cmp     [rbx+19h], r14b
0x18000e250  jnz     short loc_18000E279
0x18000e252  mov     rax, [rbx+10h]
0x18000e256  cmp     [rax+19h], r14b
0x18000e25a  jnz     short loc_18000E286
0x18000e25c  mov     rcx, [rax]
0x18000e25f  cmp     [rcx+19h], r14b
0x18000e263  jnz     short loc_18000E276
0x18000e265  mov     rbx, rcx
0x18000e268  mov     rax, [rcx]
0x18000e26b  mov     rcx, rax
0x18000e26e  cmp     [rax+19h], r14b
0x18000e272  jz      short loc_18000E265
0x18000e274  jmp     short loc_18000E279
0x18000e276  mov     rbx, rax
0x18000e279  mov     rsi, [rsp+68h+arg_18]
0x18000e281  jmp     loc_18000DF0E
0x18000e286  mov     rax, [rbx+8]
0x18000e28a  jmp     short loc_18000E299
0x18000e28c  cmp     rbx, [rax+10h]
0x18000e290  jnz     short loc_18000E276
0x18000e292  mov     rbx, rax
0x18000e295  mov     rax, [rax+8]
0x18000e299  cmp     [rax+19h], r14b
0x18000e29d  jz      short loc_18000E28C
0x18000e29f  jmp     short loc_18000E276
0x18000e2a1  mov     r12d, dword ptr [rsp+68h+arg_10]
0x18000e2a9  mov     eax, r12d
0x18000e2ac  add     rsp, 30h
0x18000e2b0  pop     r15
0x18000e2b2  pop     r14
0x18000e2b4  pop     r13
0x18000e2b6  pop     r12
0x18000e2b8  pop     rdi
0x18000e2b9  pop     rsi
0x18000e2ba  pop     rbx
0x18000e2bb  retn
```

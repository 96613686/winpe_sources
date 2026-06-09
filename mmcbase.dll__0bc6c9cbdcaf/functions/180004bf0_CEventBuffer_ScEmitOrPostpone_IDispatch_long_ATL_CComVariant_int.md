# CEventBuffer::ScEmitOrPostpone(IDispatch *,long,ATL::CComVariant *,int)

- ea: `0x180004bf0`
- end: `0x180004e16`
- name: `?ScEmitOrPostpone@CEventBuffer@@QEAA?AVSC@mmcerror@@PEAUIDispatch@@JPEAVCComVariant@ATL@@H@Z`
- size: `550`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004bf0`
- `0x180004e20`
- `0x1800051c8`
- `0x180005290`
- `0x180006aa0`
- `0x18000763c`
- `0x180007a4c`
- `0x180009928`
- `0x1800121b4`
- `0x180013e78`
- `0x180014f00`
- `0x18001d010`

## import_xrefs

- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180004d30`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180004d30`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CEventBuffer::ScEmitOrPostpone(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5, int a6)
{
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rbx
  void *v14; // rcx
  _DWORD *v15; // rax
  int v17; // [rsp+38h] [rbp-31h] BYREF
  int v18; // [rsp+3Ch] [rbp-2Dh]
  unsigned __int16 *v19; // [rsp+40h] [rbp-29h]
  __int64 v20; // [rsp+48h] [rbp-21h]
  __int64 v21; // [rsp+50h] [rbp-19h] BYREF
  int v22; // [rsp+58h] [rbp-11h]
  __int128 v23; // [rsp+60h] [rbp-9h] BYREF
  __int64 v24; // [rsp+70h] [rbp+7h]
  __int64 v25; // [rsp+E0h] [rbp+77h]

  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  ++mmcerror::SC::s_CallDepth;
  *(_QWORD *)a2 = 3;
  *(_QWORD *)(a2 + 8) = L"CEventBuffer::ScEmitOrPostpone";
  v10 = mmcerror::SC::s_CallDepth + 1;
  mmcerror::SC::s_CallDepth = v10;
  if ( (unsigned int)v10 >= 0x28 )
    v10 = 40;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    WPP_SF_SS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      13,
      (unsigned int)WPP_edd4ab13a3af37eac42c4fe50b0cf993_Traceguids,
      (unsigned int)&asc_1800222E0[40 - v10],
      (__int64)L"CEventBuffer::ScEmitOrPostpone");
  v21 = 0;
  v23 = 0;
  v24 = 0;
  if ( a3 )
  {
    v21 = a3;
    _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::_AddRef(&v21, v10);
  }
  v22 = a4;
  std::vector<ATL::CComVariant>::_Insert<ATL::CComVariant *>(&v23, v23, a5, a5 + 24LL * a6);
  if ( *(_QWORD *)(a1 + 16) <= (unsigned __int64)(*(_QWORD *)(a1 + 32) + 1LL) )
    std::deque<CEventBuffer::DispCallStr>::_Growmap(a1);
  v12 = *(_QWORD *)(a1 + 16) - 1LL;
  *(_QWORD *)(a1 + 24) &= v12;
  v13 = v12 & (*(_QWORD *)(a1 + 32) + *(_QWORD *)(a1 + 24));
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v13) )
  {
    v14 = operator new(0x28u);
    if ( !v14 )
      std::_Xbad_alloc();
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v13) = v14;
  }
  v25 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v13);
  *(_QWORD *)v25 = v21;
  _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::_AddRef(v25, v11);
  *(_DWORD *)(v25 + 8) = v22;
  std::vector<ATL::CComVariant>::vector<ATL::CComVariant>(v25 + 16, &v23);
  ++*(_QWORD *)(a1 + 32);
  if ( !*(_DWORD *)(a1 + 40) )
  {
    v15 = (_DWORD *)CEventBuffer::ScFlushPostponed(a1, &v17);
    *(_DWORD *)a2 = *v15;
    *(_DWORD *)(a2 + 4) = v15[1];
    --mmcerror::SC::s_CallDepth;
    if ( v18 )
    {
      if ( v17 != 3 || v18 < 0 )
      {
        if ( v20 )
        {
          TraceSnapinError(&String, (const struct mmcerror::SC *)&v17);
        }
        else if ( v19 )
        {
          TraceError(v19, (const struct mmcerror::SC *)&v17);
        }
      }
    }
  }
  std::vector<ATL::CComVariant>::_Tidy(&v23);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return a2;
}

```

## disassembly

```asm
0x180004bf0  mov     [rsp-8+arg_8], rdx
0x180004bf5  push    rbp
0x180004bf6  push    rbx
0x180004bf7  push    rsi
0x180004bf8  push    rdi
0x180004bf9  push    r12
0x180004bfb  push    r14
0x180004bfd  lea     rbp, [rsp-1Fh]
0x180004c02  sub     rsp, 88h
0x180004c09  mov     r14d, r9d
0x180004c0c  mov     rbx, r8
0x180004c0f  mov     rsi, rdx
0x180004c12  mov     rdi, rcx
0x180004c15  mov     [rbp+47h+var_80], 0
0x180004c1c  mov     qword ptr [rdx+8], 0
0x180004c24  mov     qword ptr [rdx+10h], 0
0x180004c2c  inc     cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x180004c32  mov     qword ptr [rdx], 3
0x180004c39  mov     [rbp+47h+var_80], 1
0x180004c40  lea     r8, aCeventbufferSc; "CEventBuffer::ScEmitOrPostpone"
0x180004c47  mov     [rdx+8], r8
0x180004c4b  mov     edx, cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x180004c51  inc     edx
0x180004c53  mov     cs:?s_CallDepth@SC@mmcerror@@0IA, edx; uint mmcerror::SC::s_CallDepth
0x180004c59  mov     r12d, 28h ; '('
0x180004c5f  cmp     edx, r12d
0x180004c62  cmovnb  edx, r12d
0x180004c66  lea     rax, WPP_GLOBAL_Control
0x180004c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c74  cmp     rcx, rax
0x180004c77  jz      short loc_180004CAB
0x180004c79  cmp     byte ptr [rcx+19h], 5
0x180004c7d  jb      short loc_180004CAB
0x180004c7f  mov     eax, r12d
0x180004c82  sub     eax, edx
0x180004c84  mov     edx, eax
0x180004c86  lea     rax, asc_1800222E0; "                                       "...
0x180004c8d  lea     r9, [rax+rdx*2]
0x180004c91  lea     edx, [r12-1Bh]
0x180004c96  mov     [rsp+0B0h+var_90], r8
0x180004c9b  lea     r8, WPP_edd4ab13a3af37eac42c4fe50b0cf993_Traceguids
0x180004ca2  mov     rcx, [rcx+10h]
0x180004ca6  call    WPP_SF_SS
0x180004cab  mov     [rbp+47h+var_60], 0
0x180004cb3  xorps   xmm0, xmm0
0x180004cb6  movdqu  [rbp+47h+var_50], xmm0
0x180004cbb  mov     [rbp+47h+var_40], 0
0x180004cc3  test    rbx, rbx
0x180004cc6  jz      short loc_180004CD6
0x180004cc8  mov     [rbp+47h+var_60], rbx
0x180004ccc  lea     rcx, [rbp+47h+var_60]
0x180004cd0  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIDispatch@@$1?_GUID_00020400_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::_AddRef(void)
0x180004cd5  nop
0x180004cd6  mov     [rbp+47h+var_58], r14d
0x180004cda  movsxd  rax, [rbp+47h+arg_28]
0x180004cde  lea     rcx, [rax+rax*2]
0x180004ce2  mov     r8, [rbp+47h+arg_20]
0x180004ce6  lea     r9, [r8+rcx*8]
0x180004cea  mov     rdx, qword ptr [rbp+47h+var_50]
0x180004cee  lea     rcx, [rbp+47h+var_50]
0x180004cf2  call    ??$_Insert@PEAVCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCComVariant@ATL@@@std@@@std@@@1@PEAVCComVariant@ATL@@1Uforward_iterator_tag@1@@Z; std::vector<ATL::CComVariant>::_Insert<ATL::CComVariant *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComVariant>>>,ATL::CComVariant *,ATL::CComVariant *,std::forward_iterator_tag)
0x180004cf7  mov     rax, [rdi+20h]
0x180004cfb  inc     rax
0x180004cfe  cmp     [rdi+10h], rax
0x180004d02  ja      short loc_180004D0C
0x180004d04  mov     rcx, rdi
0x180004d07  call    ?_Growmap@?$deque@UDispCallStr@CEventBuffer@@V?$allocator@UDispCallStr@CEventBuffer@@@std@@@std@@IEAAX_K@Z; std::deque<CEventBuffer::DispCallStr>::_Growmap(unsigned __int64)
0x180004d0c  mov     r8, [rdi+10h]
0x180004d10  dec     r8
0x180004d13  and     [rdi+18h], r8
0x180004d17  mov     rbx, [rdi+18h]
0x180004d1b  add     rbx, [rdi+20h]
0x180004d1f  and     rbx, r8
0x180004d22  mov     rax, [rdi+8]
0x180004d26  cmp     qword ptr [rax+rbx*8], 0
0x180004d2b  jnz     short loc_180004D4C
0x180004d2d  mov     rcx, r12
0x180004d30  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004d36  mov     rcx, rax
0x180004d39  test    rax, rax
0x180004d3c  jnz     short loc_180004D44
0x180004d3e  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180004d44  mov     rax, [rdi+8]
0x180004d48  mov     [rax+rbx*8], rcx
0x180004d4c  mov     rax, [rdi+8]
0x180004d50  mov     rbx, [rax+rbx*8]
0x180004d54  mov     [rbp+47h+arg_20], rbx
0x180004d58  mov     rax, [rbp+47h+var_60]
0x180004d5c  mov     [rbx], rax
0x180004d5f  mov     rcx, rbx
0x180004d62  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIDispatch@@$1?_GUID_00020400_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::_AddRef(void)
0x180004d67  nop
0x180004d68  mov     eax, [rbp+47h+var_58]
0x180004d6b  mov     [rbx+8], eax
0x180004d6e  lea     rcx, [rbx+10h]
0x180004d72  lea     rdx, [rbp+47h+var_50]
0x180004d76  call    ??0?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<ATL::CComVariant>::vector<ATL::CComVariant>(std::vector<ATL::CComVariant> const &)
0x180004d7b  nop
0x180004d7c  inc     qword ptr [rdi+20h]
0x180004d80  cmp     dword ptr [rdi+28h], 0
0x180004d84  jnz     short loc_180004DE2
0x180004d86  lea     rdx, [rbp+47h+var_78]
0x180004d8a  mov     rcx, rdi
0x180004d8d  call    ?ScFlushPostponed@CEventBuffer@@AEAA?AVSC@mmcerror@@XZ; CEventBuffer::ScFlushPostponed(void)
0x180004d92  mov     ecx, [rax]
0x180004d94  mov     [rsi], ecx
0x180004d96  mov     eax, [rax+4]
0x180004d99  mov     [rsi+4], eax
0x180004d9c  dec     cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x180004da2  mov     eax, [rbp+47h+var_74]
0x180004da5  test    eax, eax
0x180004da7  jz      short loc_180004DE2
0x180004da9  cmp     [rbp+47h+var_78], 3
0x180004dad  jnz     short loc_180004DB6
0x180004daf  shr     eax, 1Fh
0x180004db2  test    al, al
0x180004db4  jz      short loc_180004DE2
0x180004db6  cmp     [rbp+47h+var_68], 0
0x180004dbb  jz      short loc_180004DCF
0x180004dbd  lea     rdx, [rbp+47h+var_78]; struct mmcerror::SC *
0x180004dc1  lea     rcx, String; unsigned __int16 *
0x180004dc8  call    ?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceSnapinError(ushort const *,mmcerror::SC const &)
0x180004dcd  jmp     short loc_180004DE2
0x180004dcf  mov     rcx, [rbp+47h+var_70]; unsigned __int16 *
0x180004dd3  test    rcx, rcx
0x180004dd6  jz      short loc_180004DE2
0x180004dd8  lea     rdx, [rbp+47h+var_78]; struct mmcerror::SC *
0x180004ddc  call    ?TraceError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceError(ushort const *,mmcerror::SC const &)
0x180004de1  nop
0x180004de2  lea     rcx, [rbp+47h+var_50]
0x180004de6  call    ?_Tidy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAAXXZ; std::vector<ATL::CComVariant>::_Tidy(void)
0x180004deb  nop
0x180004dec  mov     rcx, [rbp+47h+var_60]
0x180004df0  test    rcx, rcx
0x180004df3  jz      short loc_180004E02
0x180004df5  mov     rax, [rcx]
0x180004df8  mov     rax, [rax+10h]
0x180004dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e01  nop
0x180004e02  mov     rax, rsi
0x180004e05  add     rsp, 88h
0x180004e0c  pop     r14
0x180004e0e  pop     r12
0x180004e10  pop     rdi
0x180004e11  pop     rsi
0x180004e12  pop     rbx
0x180004e13  pop     rbp
0x180004e14  retn
```

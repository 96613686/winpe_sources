# CMMCToolBarCtrlEx::ScInitAccessibility(void)

- ea: `0x1400ae5d8`
- end: `0x1400ae9ae`
- name: `?ScInitAccessibility@CMMCToolBarCtrlEx@@AEAA?AVSC@mmcerror@@XZ`
- size: `982`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400adfa0`

## callees

- `0x14000c1d0`
- `0x140051704`
- `0x140057608`
- `0x1400598b4`
- `0x1400ae5d8`
- `0x1400af134`
- `0x1400f3010`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ae6fa`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ae744`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ae786`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ae7db`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ae989`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ae6fa`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ae744`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ae786`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ae7db`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ae989`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x1400ae610`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x1400ae66c`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400ae6ab`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400ae6ab`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400ae6ef`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400ae739`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400ae77b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400ae7d0`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400ae6ef`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400ae739`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400ae77b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400ae7d0`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400ae62d`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400ae62d`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x1400ae95b`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x1400ae95b`
- `ole32!CoCreateInstance` at `0x1400ae65e`
- `ole32!CoCreateInstance` at `0x1400ae65e`

## string_xrefs

- `0x1400ae623`: `CMMCToolBarCtrlEx::ScInitAccessibility`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMMCToolBarCtrlEx::ScInitAccessibility(_QWORD *a1, __int64 a2)
{
  _QWORD *v4; // r13
  HRESULT Instance; // eax
  unsigned int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  _QWORD *v13; // rsi
  __int64 v14; // rax
  int v15; // eax
  _OWORD *v16; // rdx
  __int64 v17; // r8
  __int64 i; // rcx
  _OWORD *v19; // rax
  __int64 v20; // r8
  _QWORD *v21; // rdi
  _OWORD *v22; // rcx
  int v23; // r15d
  __int64 v24; // rcx
  __int64 v25; // r13
  int v26; // eax
  __int64 v27; // r8
  _DWORD v29[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v30; // [rsp+58h] [rbp-28h]
  _BYTE v31[24]; // [rsp+68h] [rbp-18h] BYREF

  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  ++mmcerror::SC::s_CallDepth;
  *(_QWORD *)a2 = 3;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)a2, L"CMMCToolBarCtrlEx::ScInitAccessibility");
  v4 = a1 + 23;
  if ( !a1[23] )
  {
    Instance = CoCreateInstance(
                 &CLSID_AccPropServices,
                 0,
                 0x17u,
                 &GUID_6e26e776_04f0_495d_80e4_3330352e3169,
                 (LPVOID *)a1 + 23);
    v30 = 0;
    ++mmcerror::SC::s_CallDepth;
    v29[0] = 3;
    v29[1] = Instance;
    if ( Instance >= 0 )
    {
      v7 = ScCheckPointers(v31, *v4, 2147549183LL);
      mmcerror::SC::operator=(a2, v7);
      mmcerror::SC::~SC((mmcerror::SC *)v31);
      v8 = *(_DWORD *)(a2 + 4);
      if ( !v8 || *(_DWORD *)a2 == 3 && v8 >= 0 )
      {
        v9 = CTiedComObjectCreator<CMMCToolBarAccServer>::ScCreateAndConnect<CMMCToolBarCtrlEx,ATL::CComPtr<IAccPropServer>>(
               v31,
               a1,
               a1 + 24);
        mmcerror::SC::operator=(a2, v9);
        mmcerror::SC::~SC((mmcerror::SC *)v31);
        v10 = *(_DWORD *)(a2 + 4);
        if ( !v10 || *(_DWORD *)a2 == 3 && v10 >= 0 )
        {
          v11 = ScCheckPointers(v31, a1[24], 2147549183LL);
          mmcerror::SC::operator=(a2, v11);
          mmcerror::SC::~SC((mmcerror::SC *)v31);
          v12 = *(_DWORD *)(a2 + 4);
          if ( !v12 || *(_DWORD *)a2 == 3 && v12 >= 0 )
          {
            v13 = a1 + 25;
            v14 = (*(__int64 (__fastcall **)(_QWORD *, _BYTE *, _QWORD *))(*a1 + 456LL))(a1, v31, a1 + 25);
            mmcerror::SC::operator=(a2, v14);
            mmcerror::SC::~SC((mmcerror::SC *)v31);
            v15 = *(_DWORD *)(a2 + 4);
            if ( !v15 || *(_DWORD *)a2 == 3 && v15 >= 0 )
            {
              std::_Sort<_GUID *,__int64>(*v13, a1[26], (__int64)(a1[26] - *v13) >> 4);
              v16 = (_OWORD *)a1[26];
              v17 = *v13;
              if ( (_OWORD *)*v13 != v16 )
              {
                for ( i = v17 + 16; (_OWORD *)i != v16; i += 16 )
                {
                  if ( *(_QWORD *)v17 == *(_QWORD *)i && *(_QWORD *)(v17 + 8) == *(_QWORD *)(i + 8) )
                  {
                    while ( 1 )
                    {
                      i += 16;
                      if ( (_OWORD *)i == v16 )
                        break;
                      if ( *(_QWORD *)v17 != *(_QWORD *)i || *(_QWORD *)(v17 + 8) != *(_QWORD *)(i + 8) )
                      {
                        v17 += 16;
                        *(_OWORD *)v17 = *(_OWORD *)i;
                      }
                    }
                    v19 = (_OWORD *)(v17 + 16);
                    goto LABEL_25;
                  }
                  v17 = i;
                }
              }
              v19 = (_OWORD *)a1[26];
LABEL_25:
              v20 = *v13;
              v21 = a1 + 26;
              if ( v19 == (_OWORD *)*v13 && v16 == (_OWORD *)*v21 )
              {
                *v21 = v20;
              }
              else if ( v19 != v16 )
              {
                v22 = (_OWORD *)*v21;
                if ( v16 != (_OWORD *)*v21 )
                {
                  do
                    *v19++ = *v16++;
                  while ( v16 != v22 );
                  v20 = *v13;
                }
                *v21 = v19;
              }
              if ( (*v21 - v20) >> 4 )
              {
                v23 = 0;
                do
                {
                  v24 = *v4;
                  v25 = 16LL * v23;
                  v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64, int, _QWORD, int))(*(_QWORD *)v24 + 64LL))(
                          v24,
                          a1[8],
                          4294967292LL,
                          0,
                          v25 + v20,
                          1,
                          a1[24],
                          1);
                  *(_DWORD *)a2 = 3;
                  *(_DWORD *)(a2 + 4) = v26;
                  if ( v26 < 0 )
                  {
                    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
                    {
                      WPP_SF__guid_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, v27, v25 + *v13);
                    }
                    mmcerror::SC::TraceAndClear((mmcerror::SC *)a2);
                  }
                  ++v23;
                  v20 = *v13;
                  v4 = a1 + 23;
                }
                while ( v23 < (unsigned __int64)((__int64)(*v21 - *v13) >> 4) );
              }
            }
          }
        }
      }
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      v6 = mmcerror::SC::ToHr((mmcerror::SC *)a2);
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_86dbc93225c933df59f96a6093068c5a_Traceguids, v6);
    }
    mmcerror::SC::~SC((mmcerror::SC *)v29);
  }
  return a2;
}

```

## disassembly

```asm
0x1400ae5d8  mov     [rsp-38h+arg_10], rbx
0x1400ae5dd  mov     [rsp-38h+arg_8], rdx
0x1400ae5e2  push    rbp
0x1400ae5e3  push    rsi
0x1400ae5e4  push    rdi
0x1400ae5e5  push    r12
0x1400ae5e7  push    r13
0x1400ae5e9  push    r14
0x1400ae5eb  push    r15
0x1400ae5ed  mov     rbp, rsp
0x1400ae5f0  sub     rsp, 80h
0x1400ae5f7  mov     rbx, rdx
0x1400ae5fa  mov     r12, rcx
0x1400ae5fd  mov     edi, 1
0x1400ae602  mov     [rbp+arg_0], edi
0x1400ae605  xor     r14d, r14d
0x1400ae608  mov     [rdx+8], r14
0x1400ae60c  mov     [rdx+10h], r14
0x1400ae610  mov     rax, cs:__imp_?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x1400ae617  add     [rax], edi
0x1400ae619  lea     r15d, [rdi+2]
0x1400ae61d  mov     [rdx], r15
0x1400ae620  mov     [rbp+arg_0], edi
0x1400ae623  lea     rdx, aCmmctoolbarctr_1; "CMMCToolBarCtrlEx::ScInitAccessibility"
0x1400ae62a  mov     rcx, rbx
0x1400ae62d  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400ae633  lea     r13, [r12+0B8h]
0x1400ae63b  cmp     [r13+0], r14
0x1400ae63f  jnz     loc_1400AE990
0x1400ae645  mov     [rsp+80h+ppv], r13; ppv
0x1400ae64a  lea     r9, _GUID_6e26e776_04f0_495d_80e4_3330352e3169; riid
0x1400ae651  xor     edx, edx; pUnkOuter
0x1400ae653  lea     r8d, [rdi+16h]; dwClsContext
0x1400ae657  lea     rcx, CLSID_AccPropServices; rclsid
0x1400ae65e  call    cs:__imp_CoCreateInstance
0x1400ae664  xorps   xmm0, xmm0
0x1400ae667  movdqu  [rbp+var_28], xmm0
0x1400ae66c  mov     rcx, cs:__imp_?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x1400ae673  add     [rcx], edi
0x1400ae675  mov     [rbp+var_30], r15d
0x1400ae679  mov     [rbp+var_2C], eax
0x1400ae67c  test    eax, eax
0x1400ae67e  jz      short loc_1400AE6D3
0x1400ae680  shr     eax, 1Fh
0x1400ae683  test    al, al
0x1400ae685  jz      short loc_1400AE6D3
0x1400ae687  lea     r14, WPP_GLOBAL_Control
0x1400ae68e  mov     rax, cs:WPP_GLOBAL_Control
0x1400ae695  cmp     rax, r14
0x1400ae698  jz      loc_1400AE985
0x1400ae69e  cmp     byte ptr [rax+19h], 4
0x1400ae6a2  jb      loc_1400AE985
0x1400ae6a8  mov     rcx, rbx
0x1400ae6ab  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400ae6b1  lea     edx, [rdi+0Dh]
0x1400ae6b4  mov     r9d, eax
0x1400ae6b7  lea     r8, WPP_86dbc93225c933df59f96a6093068c5a_Traceguids
0x1400ae6be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ae6c5  mov     rcx, [rcx+10h]
0x1400ae6c9  call    WPP_SF_d
0x1400ae6ce  jmp     loc_1400AE985
0x1400ae6d3  mov     esi, 8000FFFFh
0x1400ae6d8  mov     r8d, esi
0x1400ae6db  mov     rdx, [r13+0]
0x1400ae6df  lea     rcx, [rbp+var_18]
0x1400ae6e3  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x1400ae6e8  nop
0x1400ae6e9  mov     rdx, rax
0x1400ae6ec  mov     rcx, rbx
0x1400ae6ef  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400ae6f5  nop
0x1400ae6f6  lea     rcx, [rbp+var_18]
0x1400ae6fa  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400ae700  mov     eax, [rbx+4]
0x1400ae703  test    eax, eax
0x1400ae705  jz      short loc_1400AE71B
0x1400ae707  cmp     [rbx], r15d
0x1400ae70a  jnz     loc_1400AE985
0x1400ae710  shr     eax, 1Fh
0x1400ae713  test    al, al
0x1400ae715  jnz     loc_1400AE985
0x1400ae71b  lea     rdi, [r12+0C0h]
0x1400ae723  mov     r8, rdi
0x1400ae726  mov     rdx, r12
0x1400ae729  lea     rcx, [rbp+var_18]
0x1400ae72d  call    ??$ScCreateAndConnect@VCMMCToolBarCtrlEx@@V?$CComPtr@UIAccPropServer@@@ATL@@@?$CTiedComObjectCreator@VCMMCToolBarAccServer@@@@SA?AVSC@mmcerror@@AEAVCMMCToolBarCtrlEx@@AEAV?$CComPtr@UIAccPropServer@@@ATL@@@Z; CTiedComObjectCreator<CMMCToolBarAccServer>::ScCreateAndConnect<CMMCToolBarCtrlEx,ATL::CComPtr<IAccPropServer>>(CMMCToolBarCtrlEx &,ATL::CComPtr<IAccPropServer> &)
0x1400ae732  nop
0x1400ae733  mov     rdx, rax
0x1400ae736  mov     rcx, rbx
0x1400ae739  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400ae73f  nop
0x1400ae740  lea     rcx, [rbp+var_18]
0x1400ae744  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400ae74a  mov     eax, [rbx+4]
0x1400ae74d  test    eax, eax
0x1400ae74f  jz      short loc_1400AE765
0x1400ae751  cmp     [rbx], r15d
0x1400ae754  jnz     loc_1400AE985
0x1400ae75a  shr     eax, 1Fh
0x1400ae75d  test    al, al
0x1400ae75f  jnz     loc_1400AE985
0x1400ae765  mov     r8d, esi
0x1400ae768  mov     rdx, [rdi]
0x1400ae76b  lea     rcx, [rbp+var_18]
0x1400ae76f  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x1400ae774  nop
0x1400ae775  mov     rdx, rax
0x1400ae778  mov     rcx, rbx
0x1400ae77b  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400ae781  nop
0x1400ae782  lea     rcx, [rbp+var_18]
0x1400ae786  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400ae78c  mov     eax, [rbx+4]
0x1400ae78f  test    eax, eax
0x1400ae791  jz      short loc_1400AE7A7
0x1400ae793  cmp     [rbx], r15d
0x1400ae796  jnz     loc_1400AE985
0x1400ae79c  shr     eax, 1Fh
0x1400ae79f  test    al, al
0x1400ae7a1  jnz     loc_1400AE985
0x1400ae7a7  lea     rsi, [r12+0C8h]
0x1400ae7af  mov     rax, [r12]
0x1400ae7b3  mov     r8, rsi
0x1400ae7b6  lea     rdx, [rbp+var_18]
0x1400ae7ba  mov     rcx, r12
0x1400ae7bd  mov     rax, [rax+1C8h]
0x1400ae7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ae7c9  nop
0x1400ae7ca  mov     rdx, rax
0x1400ae7cd  mov     rcx, rbx
0x1400ae7d0  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400ae7d6  nop
0x1400ae7d7  lea     rcx, [rbp+var_18]
0x1400ae7db  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400ae7e1  mov     eax, [rbx+4]
0x1400ae7e4  test    eax, eax
0x1400ae7e6  jz      short loc_1400AE7FC
0x1400ae7e8  cmp     [rbx], r15d
0x1400ae7eb  jnz     loc_1400AE985
0x1400ae7f1  shr     eax, 1Fh
0x1400ae7f4  test    al, al
0x1400ae7f6  jnz     loc_1400AE985
0x1400ae7fc  mov     rdx, [r12+0D0h]
0x1400ae804  mov     r8, rdx
0x1400ae807  sub     r8, [rsi]
0x1400ae80a  sar     r8, 4
0x1400ae80e  mov     rcx, [rsi]
0x1400ae811  call    ??$_Sort@PEAU_GUID@@_J@std@@YAXPEAU_GUID@@0_J@Z; std::_Sort<_GUID *,__int64>(_GUID *,_GUID *,__int64)
0x1400ae816  mov     rdx, [r12+0D0h]
0x1400ae81e  mov     r8, [rsi]
0x1400ae821  cmp     r8, rdx
0x1400ae824  jz      short loc_1400AE84A
0x1400ae826  lea     rcx, [r8+10h]
0x1400ae82a  jmp     short loc_1400AE845
0x1400ae82c  mov     rax, [r8]
0x1400ae82f  cmp     rax, [rcx]
0x1400ae832  jnz     short loc_1400AE83E
0x1400ae834  mov     rax, [r8+8]
0x1400ae838  cmp     rax, [rcx+8]
0x1400ae83c  jz      short loc_1400AE881
0x1400ae83e  mov     r8, rcx
0x1400ae841  add     rcx, 10h
0x1400ae845  cmp     rcx, rdx
0x1400ae848  jnz     short loc_1400AE82C
0x1400ae84a  mov     rax, rdx
0x1400ae84d  mov     r8, [rsi]
0x1400ae850  lea     rdi, [rsi+8]
0x1400ae854  cmp     rax, r8
0x1400ae857  jnz     short loc_1400AE890
0x1400ae859  cmp     rdx, [rdi]
0x1400ae85c  jnz     short loc_1400AE890
0x1400ae85e  mov     [rdi], r8
0x1400ae861  jmp     short loc_1400AE8B7
0x1400ae863  mov     rax, [r8]
0x1400ae866  cmp     rax, [rcx]
0x1400ae869  jnz     short loc_1400AE875
0x1400ae86b  mov     rax, [r8+8]
0x1400ae86f  cmp     rax, [rcx+8]
0x1400ae873  jz      short loc_1400AE881
0x1400ae875  add     r8, 10h
0x1400ae879  movups  xmm0, xmmword ptr [rcx]
0x1400ae87c  movdqu  xmmword ptr [r8], xmm0
0x1400ae881  add     rcx, 10h
0x1400ae885  cmp     rcx, rdx
0x1400ae888  jnz     short loc_1400AE863
0x1400ae88a  lea     rax, [r8+10h]
0x1400ae88e  jmp     short loc_1400AE84D
0x1400ae890  cmp     rax, rdx
0x1400ae893  jz      short loc_1400AE8B7
0x1400ae895  mov     rcx, [rdi]
0x1400ae898  cmp     rdx, rcx
0x1400ae89b  jz      short loc_1400AE8B4
0x1400ae89d  movups  xmm0, xmmword ptr [rdx]
0x1400ae8a0  movdqu  xmmword ptr [rax], xmm0
0x1400ae8a4  add     rax, 10h
0x1400ae8a8  add     rdx, 10h
0x1400ae8ac  cmp     rdx, rcx
0x1400ae8af  jnz     short loc_1400AE89D
0x1400ae8b1  mov     r8, [rsi]
0x1400ae8b4  mov     [rdi], rax
0x1400ae8b7  mov     rax, [rdi]
0x1400ae8ba  sub     rax, r8
0x1400ae8bd  sar     rax, 4
0x1400ae8c1  test    rax, rax
0x1400ae8c4  jz      loc_1400AE985
0x1400ae8ca  mov     r15d, r14d
0x1400ae8cd  lea     r14, WPP_GLOBAL_Control
0x1400ae8d4  mov     rcx, [r13+0]
0x1400ae8d8  movsxd  r13, r15d
0x1400ae8db  shl     r13, 4
0x1400ae8df  mov     rax, [rcx]
0x1400ae8e2  add     r8, r13
0x1400ae8e5  mov     [rsp+80h+var_48], 1
0x1400ae8ed  mov     rdx, [r12+0C0h]
0x1400ae8f5  mov     [rsp+80h+var_50], rdx
0x1400ae8fa  mov     [rsp+80h+var_58], 1
0x1400ae902  mov     [rsp+80h+ppv], r8
0x1400ae907  xor     r9d, r9d
0x1400ae90a  mov     r8d, 0FFFFFFFCh
0x1400ae910  mov     rdx, [r12+40h]
0x1400ae915  mov     rax, [rax+40h]
0x1400ae919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ae91e  mov     dword ptr [rbx], 3
0x1400ae924  mov     [rbx+4], eax
0x1400ae927  test    eax, eax
0x1400ae929  jz      short loc_1400AE961
0x1400ae92b  shr     eax, 1Fh
0x1400ae92e  test    al, al
0x1400ae930  jz      short loc_1400AE961
0x1400ae932  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ae939  cmp     rcx, r14
0x1400ae93c  jz      short loc_1400AE958
0x1400ae93e  cmp     byte ptr [rcx+19h], 5
0x1400ae942  jb      short loc_1400AE958
0x1400ae944  mov     r9, [rsi]
0x1400ae947  add     r9, r13
0x1400ae94a  mov     edx, 10h
0x1400ae94f  mov     rcx, [rcx+10h]
0x1400ae953  call    WPP_SF__guid_
0x1400ae958  mov     rcx, rbx
0x1400ae95b  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x1400ae961  inc     r15d
0x1400ae964  mov     r8, [rsi]
0x1400ae967  mov     rcx, [rdi]
0x1400ae96a  sub     rcx, r8
0x1400ae96d  sar     rcx, 4
0x1400ae971  movsxd  rax, r15d
0x1400ae974  cmp     rax, rcx
0x1400ae977  lea     r13, [r12+0B8h]
0x1400ae97f  jb      loc_1400AE8D4
0x1400ae985  lea     rcx, [rbp+var_30]
0x1400ae989  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400ae98f  nop
0x1400ae990  mov     rax, rbx
0x1400ae993  mov     rbx, [rsp+80h+arg_10]
0x1400ae99b  add     rsp, 80h
0x1400ae9a2  pop     r15
0x1400ae9a4  pop     r14
0x1400ae9a6  pop     r13
0x1400ae9a8  pop     r12
0x1400ae9aa  pop     rdi
0x1400ae9ab  pop     rsi
0x1400ae9ac  pop     rbp
0x1400ae9ad  retn
```

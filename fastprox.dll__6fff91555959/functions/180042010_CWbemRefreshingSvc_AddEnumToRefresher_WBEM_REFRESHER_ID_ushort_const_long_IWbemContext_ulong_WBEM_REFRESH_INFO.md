# CWbemRefreshingSvc::AddEnumToRefresher(_WBEM_REFRESHER_ID *,ushort const *,long,IWbemContext *,ulong,_WBEM_REFRESH_INFO *,ulong *)

- ea: `0x180042010`
- end: `0x180042452`
- name: `?AddEnumToRefresher@CWbemRefreshingSvc@@MEAAJPEAU_WBEM_REFRESHER_ID@@PEBGJPEAUIWbemContext@@KPEAU_WBEM_REFRESH_INFO@@PEAK@Z`
- size: `1090`
- prototype: `__int64 __fastcall(CWbemRefreshingSvc *this, struct _WBEM_REFRESHER_ID *, OLECHAR *psz, unsigned int, struct IWbemContext *, unsigned int, struct _WBEM_REFRESH_INFO *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180042000`
- `0x180089e60`

## callees

- `0x180037120`
- `0x18004132c`
- `0x180042010`
- `0x180042460`
- `0x180042490`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180042170`
- `wbemcomn!GetMemLogObject` at `0x1800422f8`
- `wbemcomn!GetMemLogObject` at `0x180042349`
- `wbemcomn!GetMemLogObject` at `0x18004239a`
- `wbemcomn!GetMemLogObject` at `0x1800423fb`
- `wbemcomn!GetMemLogObject` at `0x180042170`
- `wbemcomn!GetMemLogObject` at `0x1800422f8`
- `wbemcomn!GetMemLogObject` at `0x180042349`
- `wbemcomn!GetMemLogObject` at `0x18004239a`
- `wbemcomn!GetMemLogObject` at `0x1800423fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004217c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042308`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042359`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800423aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004240b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004217c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042308`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042359`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800423aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004240b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800420a0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800420a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800421ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800421ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemRefreshingSvc::AddEnumToRefresher(
        CWbemRefreshingSvc *this,
        struct _WBEM_REFRESHER_ID *a2,
        OLECHAR *psz,
        unsigned int a4,
        struct IWbemContext *a5,
        unsigned int a6,
        struct _WBEM_REFRESH_INFO *a7,
        unsigned int *a8)
{
  OLECHAR *v12; // rax
  int v13; // eax
  __int64 v14; // rbx
  int v15; // edi
  __int64 (__fastcall ***v16)(_QWORD, GUID *, struct CWbemObject **); // rdi
  int v17; // esi
  struct CWbemObject *v18; // rsi
  int v19; // r15d
  CMemoryLog *v20; // rax
  CMemoryLog *v22; // rax
  unsigned int v23; // ebx
  CWbemRefreshingSvc *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *MemLogObject; // rax
  struct CWbemObject *v30; // [rsp+40h] [rbp-40h] BYREF
  __int64 v31; // [rsp+48h] [rbp-38h] BYREF
  __int64 (__fastcall ***v32)(_QWORD, GUID *, struct CWbemObject **); // [rsp+50h] [rbp-30h] BYREF
  __int64 (__fastcall ***v33)(_QWORD, GUID *, struct CWbemObject **); // [rsp+58h] [rbp-28h]
  __int64 v34; // [rsp+60h] [rbp-20h]
  OLECHAR *v35; // [rsp+68h] [rbp-18h] BYREF
  struct CWbemObject *v36; // [rsp+70h] [rbp-10h]
  BSTR bstrString; // [rsp+78h] [rbp-8h]

  if ( !psz || !a7 || !a8 || !a2 )
  {
    MemLogObject = GetMemLogObject();
    v23 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v23;
    }
    v25 = 16;
    v26 = 2147749896LL;
    goto LABEL_53;
  }
  if ( (unsigned int)CWbemRefreshingSvc::IsWinmgmt(this, a2) )
  {
    v22 = GetMemLogObject();
    v23 = -2147217386;
    CMemoryLog::Write(v22, -2147217386);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v23;
    }
    v25 = 17;
    v26 = 2147749910LL;
    goto LABEL_53;
  }
  *a8 = 1;
  *(_OWORD *)a7 = 0;
  *((_OWORD *)a7 + 1) = 0;
  *((_OWORD *)a7 + 2) = 0;
  *((_QWORD *)a7 + 6) = 0;
  v31 = 0;
  v12 = SysAllocString(psz);
  bstrString = v12;
  if ( !v12 )
  {
    v27 = GetMemLogObject();
    v23 = -2147217402;
    CMemoryLog::Write(v27, -2147217402);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v23;
    }
    v25 = 18;
    v26 = 2147749894LL;
LABEL_53:
    WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids, v26);
    return v23;
  }
  v35 = v12;
  v13 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 4) + 48LL))(
          *((_QWORD *)this + 4),
          v12,
          a4,
          0,
          &v31,
          0);
  v14 = v31;
  v34 = v31;
  if ( v13 < 0 )
  {
    v28 = GetMemLogObject();
    v15 = -2147217392;
    CMemoryLog::Write(v28, -2147217392);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids, 2147749904LL);
    }
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v34 = 0;
    CSysFreeMe::~CSysFreeMe(&v35);
  }
  else
  {
    v32 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v31 + 120LL))(v31, 0, &v32);
    if ( v15 < 0 )
    {
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    else
    {
      v16 = v32;
      v33 = v32;
      v30 = 0;
      v17 = (**v32)(v32, &IID__IWmiObject, &v30);
      if ( v17 < 0 )
      {
        if ( v16 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct CWbemObject **)))(*v16)[2])(v16);
        v33 = 0;
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        v15 = v17;
      }
      else
      {
        v18 = v30;
        v36 = v30;
        v19 = (*(__int64 (__fastcall **)(struct CWbemObject *, _QWORD, _QWORD))(*(_QWORD *)v30 + 608LL))(
                v30,
                *((_QWORD *)this + 5),
                *((_QWORD *)this + 6));
        if ( v19 < 0
          || (v19 = CWbemRefreshingSvc::AddEnumToRefresher_(this, a6 != 0, a2, v30, psz, a4, a5, a7), v19 < 0) )
        {
          v20 = GetMemLogObject();
          CMemoryLog::Write(v20, v19);
        }
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids,
            (unsigned int)v19);
        }
        if ( v18 )
          (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v18 + 16LL))(v18);
        v36 = 0;
        if ( v16 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct CWbemObject **)))(*v16)[2])(v16);
        v33 = 0;
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        v15 = v19;
      }
    }
    v34 = 0;
    SysFreeString(bstrString);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180042010  mov     [rsp-38h+arg_0], rbx
0x180042015  mov     [rsp-38h+arg_18], r9d
0x18004201a  mov     [rsp-38h+arg_10], r8
0x18004201f  push    rbp
0x180042020  push    rsi
0x180042021  push    rdi
0x180042022  push    r12
0x180042024  push    r13
0x180042026  push    r14
0x180042028  push    r15
0x18004202a  mov     rbp, rsp
0x18004202d  sub     rsp, 80h
0x180042034  mov     esi, r9d
0x180042037  mov     rdi, r8
0x18004203a  mov     r12, rdx
0x18004203d  mov     r13, rcx
0x180042040  xor     r15d, r15d
0x180042043  test    r8, r8
0x180042046  jz      loc_1800423FB
0x18004204c  mov     r14, [rbp+arg_30]
0x180042050  test    r14, r14
0x180042053  jz      loc_1800423FB
0x180042059  mov     rbx, [rbp+arg_38]
0x18004205d  test    rbx, rbx
0x180042060  jz      loc_1800423FB
0x180042066  test    rdx, rdx
0x180042069  jz      loc_1800423FB
0x18004206f  call    ?IsWinmgmt@CWbemRefreshingSvc@@IEAAHPEAU_WBEM_REFRESHER_ID@@@Z; CWbemRefreshingSvc::IsWinmgmt(_WBEM_REFRESHER_ID *)
0x180042074  test    eax, eax
0x180042076  jnz     loc_1800422F8
0x18004207c  mov     dword ptr [rbx], 1
0x180042082  xorps   xmm0, xmm0
0x180042085  xor     eax, eax
0x180042087  movups  xmmword ptr [r14], xmm0
0x18004208b  movups  xmmword ptr [r14+10h], xmm0
0x180042090  movups  xmmword ptr [r14+20h], xmm0
0x180042095  mov     [r14+30h], rax
0x180042099  mov     [rbp+var_38], r15
0x18004209d  mov     rcx, rdi; psz
0x1800420a0  call    cs:__imp_SysAllocString
0x1800420a6  mov     rdx, rax
0x1800420a9  mov     [rbp+bstrString], rax
0x1800420ad  test    rax, rax
0x1800420b0  jz      loc_180042349
0x1800420b6  mov     [rbp+var_18], rax
0x1800420ba  mov     rcx, [r13+20h]
0x1800420be  mov     rax, [rcx]
0x1800420c1  mov     qword ptr [rsp+80h+var_58], r15
0x1800420c6  lea     r8, [rbp+var_38]
0x1800420ca  mov     [rsp+80h+psz], r8
0x1800420cf  xor     r9d, r9d
0x1800420d2  mov     r8d, esi
0x1800420d5  mov     rax, [rax+30h]
0x1800420d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800420de  mov     rbx, [rbp+var_38]
0x1800420e2  mov     [rbp+var_20], rbx
0x1800420e6  test    eax, eax
0x1800420e8  js      loc_18004239A
0x1800420ee  mov     [rbp+var_30], r15
0x1800420f2  mov     rcx, [rbp+var_38]
0x1800420f6  mov     rax, [rcx]
0x1800420f9  lea     r8, [rbp+var_30]
0x1800420fd  xor     edx, edx
0x1800420ff  mov     rax, [rax+78h]
0x180042103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042108  mov     edi, eax
0x18004210a  test    eax, eax
0x18004210c  js      loc_180042243
0x180042112  mov     rdi, [rbp+var_30]
0x180042116  mov     [rbp+var_28], rdi
0x18004211a  mov     [rbp+var_40], r15
0x18004211e  mov     rcx, [rbp+var_30]
0x180042122  mov     rax, [rcx]
0x180042125  lea     r8, [rbp+var_40]
0x180042129  lea     rdx, IID__IWmiObject
0x180042130  mov     rax, [rax]
0x180042133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042138  mov     esi, eax
0x18004213a  test    eax, eax
0x18004213c  js      loc_180042259
0x180042142  mov     rsi, [rbp+var_40]
0x180042146  mov     [rbp+var_10], rsi
0x18004214a  mov     rcx, [rbp+var_40]
0x18004214e  mov     rax, [rcx]
0x180042151  mov     r8, [r13+30h]
0x180042155  mov     rdx, [r13+28h]
0x180042159  mov     rax, [rax+260h]
0x180042160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042165  mov     r15d, eax
0x180042168  test    eax, eax
0x18004216a  jns     loc_18004228C
0x180042170  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042176  mov     edx, r15d
0x180042179  mov     rcx, rax
0x18004217c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042182  lea     rax, WPP_GLOBAL_Control
0x180042189  mov     rcx, cs:WPP_GLOBAL_Control
0x180042190  cmp     rcx, rax
0x180042193  jnz     short loc_180042212
0x180042195  test    rsi, rsi
0x180042198  jz      short loc_1800421A9
0x18004219a  mov     rax, [rsi]
0x18004219d  mov     rcx, rsi
0x1800421a0  mov     rax, [rax+10h]
0x1800421a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421a9  mov     [rbp+var_10], 0
0x1800421b1  test    rdi, rdi
0x1800421b4  jz      short loc_1800421C5
0x1800421b6  mov     rax, [rdi]
0x1800421b9  mov     rcx, rdi
0x1800421bc  mov     rax, [rax+10h]
0x1800421c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421c5  mov     [rbp+var_28], 0
0x1800421cd  test    rbx, rbx
0x1800421d0  jz      short loc_1800421E1
0x1800421d2  mov     rax, [rbx]
0x1800421d5  mov     rcx, rbx
0x1800421d8  mov     rax, [rax+10h]
0x1800421dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421e1  mov     edi, r15d
0x1800421e4  xor     r15d, r15d
0x1800421e7  mov     [rbp+var_20], r15
0x1800421eb  mov     rcx, [rbp+bstrString]; bstrString
0x1800421ef  call    cs:__imp_SysFreeString
0x1800421f5  mov     eax, edi
0x1800421f7  mov     rbx, [rsp+80h+arg_0]
0x1800421ff  add     rsp, 80h
0x180042206  pop     r15
0x180042208  pop     r14
0x18004220a  pop     r13
0x18004220c  pop     r12
0x18004220e  pop     rdi
0x18004220f  pop     rsi
0x180042210  pop     rbp
0x180042211  retn
0x180042212  test    byte ptr [rcx+1Ch], 1
0x180042216  jz      loc_180042195
0x18004221c  cmp     byte ptr [rcx+19h], 2
0x180042220  jb      loc_180042195
0x180042226  mov     edx, 14h
0x18004222b  mov     r9d, r15d
0x18004222e  lea     r8, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids
0x180042235  mov     rcx, [rcx+10h]
0x180042239  call    WPP_SF_d
0x18004223e  jmp     loc_180042195
0x180042243  test    rbx, rbx
0x180042246  jz      short loc_1800421E7
0x180042248  mov     rcx, [rbx]
0x18004224b  mov     rax, [rcx+10h]
0x18004224f  mov     rcx, rbx
0x180042252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042257  jmp     short loc_1800421E7
0x180042259  test    rdi, rdi
0x18004225c  jz      short loc_18004226D
0x18004225e  mov     rcx, [rdi]
0x180042261  mov     rax, [rcx+10h]
0x180042265  mov     rcx, rdi
0x180042268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004226d  mov     [rbp+var_28], r15
0x180042271  test    rbx, rbx
0x180042274  jz      short loc_180042285
0x180042276  mov     rax, [rbx]
0x180042279  mov     rcx, rbx
0x18004227c  mov     rax, [rax+10h]
0x180042280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042285  mov     edi, esi
0x180042287  jmp     loc_1800421E7
0x18004228c  xor     edx, edx
0x18004228e  cmp     [rbp+arg_28], 1
0x180042292  setnb   dl; int
0x180042295  mov     [rsp+80h+var_48], r14; struct _WBEM_REFRESH_INFO *
0x18004229a  mov     rax, [rbp+arg_20]
0x18004229e  mov     [rsp+80h+var_50], rax; struct IWbemContext *
0x1800422a3  mov     eax, [rbp+arg_18]
0x1800422a6  mov     [rsp+80h+var_58], eax; int
0x1800422aa  mov     rax, [rbp+arg_10]
0x1800422ae  mov     [rsp+80h+psz], rax; psz
0x1800422b3  mov     r9, [rbp+var_40]; struct CWbemObject *
0x1800422b7  mov     r8, r12; struct _WBEM_REFRESHER_ID *
0x1800422ba  mov     rcx, r13; this
0x1800422bd  call    ?AddEnumToRefresher_@CWbemRefreshingSvc@@IEAAJHPEAU_WBEM_REFRESHER_ID@@PEAVCWbemObject@@PEBGJPEAUIWbemContext@@PEAU_WBEM_REFRESH_INFO@@@Z; CWbemRefreshingSvc::AddEnumToRefresher_(int,_WBEM_REFRESHER_ID *,CWbemObject *,ushort const *,long,IWbemContext *,_WBEM_REFRESH_INFO *)
0x1800422c2  mov     r15d, eax
0x1800422c5  test    eax, eax
0x1800422c7  jns     loc_180042182
0x1800422cd  jmp     loc_180042170
0x1800422d2  test    rbx, rbx
0x1800422d5  jz      short loc_1800422E6
0x1800422d7  mov     rcx, [rbx]
0x1800422da  mov     rax, [rcx+10h]
0x1800422de  mov     rcx, rbx
0x1800422e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422e6  mov     [rbp+var_20], r15
0x1800422ea  lea     rcx, [rbp+var_18]; this
0x1800422ee  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x1800422f3  jmp     loc_1800421F5
0x1800422f8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800422fe  mov     ebx, 80041016h
0x180042303  mov     edx, ebx
0x180042305  mov     rcx, rax
0x180042308  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004230e  lea     rax, WPP_GLOBAL_Control
0x180042315  mov     rcx, cs:WPP_GLOBAL_Control
0x18004231c  cmp     rcx, rax
0x18004231f  jz      loc_18004244B
0x180042325  test    byte ptr [rcx+1Ch], 1
0x180042329  jz      loc_18004244B
0x18004232f  cmp     byte ptr [rcx+19h], 2
0x180042333  jb      loc_18004244B
0x180042339  mov     edx, 11h
0x18004233e  mov     r9d, 80041016h
0x180042344  jmp     loc_18004243B
0x180042349  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004234f  mov     ebx, 80041006h
0x180042354  mov     edx, ebx
0x180042356  mov     rcx, rax
0x180042359  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004235f  lea     rax, WPP_GLOBAL_Control
0x180042366  mov     rcx, cs:WPP_GLOBAL_Control
0x18004236d  cmp     rcx, rax
0x180042370  jz      loc_18004244B
0x180042376  test    byte ptr [rcx+1Ch], 1
0x18004237a  jz      loc_18004244B
0x180042380  cmp     byte ptr [rcx+19h], 2
0x180042384  jb      loc_18004244B
0x18004238a  mov     edx, 12h
0x18004238f  mov     r9d, 80041006h
0x180042395  jmp     loc_18004243B
0x18004239a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800423a0  mov     edi, 80041010h
0x1800423a5  mov     edx, edi
0x1800423a7  mov     rcx, rax
0x1800423aa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800423b0  lea     rax, WPP_GLOBAL_Control
0x1800423b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800423be  cmp     rcx, rax
0x1800423c1  jz      loc_1800422D2
0x1800423c7  test    byte ptr [rcx+1Ch], 1
0x1800423cb  jz      loc_1800422D2
0x1800423d1  cmp     byte ptr [rcx+19h], 2
0x1800423d5  jb      loc_1800422D2
0x1800423db  mov     edx, 13h
0x1800423e0  mov     r9d, 80041010h
0x1800423e6  lea     r8, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids
0x1800423ed  mov     rcx, [rcx+10h]
0x1800423f1  call    WPP_SF_d
0x1800423f6  jmp     loc_1800422D2
0x1800423fb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042401  mov     ebx, 80041008h
0x180042406  mov     edx, ebx
0x180042408  mov     rcx, rax
0x18004240b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042411  lea     rax, WPP_GLOBAL_Control
0x180042418  mov     rcx, cs:WPP_GLOBAL_Control
0x18004241f  cmp     rcx, rax
0x180042422  jz      short loc_18004244B
0x180042424  test    byte ptr [rcx+1Ch], 1
0x180042428  jz      short loc_18004244B
0x18004242a  cmp     byte ptr [rcx+19h], 2
0x18004242e  jb      short loc_18004244B
0x180042430  mov     edx, 10h
0x180042435  mov     r9d, 80041008h
0x18004243b  lea     r8, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids
0x180042442  mov     rcx, [rcx+10h]
0x180042446  call    WPP_SF_d
0x18004244b  mov     eax, ebx
0x18004244d  jmp     loc_1800421F7
```

# CRecordset::GetBookmarkInfo(unsigned __int64 *,uchar * *)

- ea: `0x180007900`
- end: `0x180007e87`
- name: `?GetBookmarkInfo@CRecordset@@AEAAJPEA_KPEAPEAE@Z`
- size: `1415`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, unsigned __int64 *, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18002f1e8`
- `0x18002f5e0`
- `0x1800b7c60`

## callees

- `0x180007900`
- `0x180009940`
- `0x180020fc0`
- `0x18004f2b0`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x180007985`
- `KERNEL32!TlsSetValue` at `0x180007b16`
- `KERNEL32!TlsSetValue` at `0x180007b4c`
- `KERNEL32!TlsSetValue` at `0x180007c77`
- `KERNEL32!TlsSetValue` at `0x180007985`
- `KERNEL32!TlsSetValue` at `0x180007b16`
- `KERNEL32!TlsSetValue` at `0x180007b4c`
- `KERNEL32!TlsSetValue` at `0x180007c77`
- `KERNEL32!TlsGetValue` at `0x180007942`
- `KERNEL32!TlsGetValue` at `0x180007942`
- `ole32!CoTaskMemFree` at `0x180007e15`
- `ole32!CoTaskMemFree` at `0x180007e15`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180007bc4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180007bef`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180007c8b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180007bc4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180007bef`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180007c8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRecordset::GetBookmarkInfo(CRecordset *this, unsigned __int64 *a2, unsigned __int8 **a3)
{
  char *v6; // rcx
  _DWORD *Value; // rax
  int DeferredHRow; // eax
  int v9; // esi
  __int64 v10; // rdx
  int v11; // edi
  unsigned __int8 *v12; // rdi
  __int64 v13; // r8
  int v14; // eax
  int v15; // r8d
  unsigned int v16; // ebx
  bool v17; // zf
  _DWORD *v18; // rax
  IErrorInfo *v19; // rdx
  _DWORD *v20; // rax
  IErrorInfo *v21; // rdx
  _DWORD *v23; // rax
  IErrorInfo *v24; // rdx
  __int64 v25; // rdi
  unsigned int BidObjectID; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  void *v29; // rcx
  __int64 v30; // [rsp+20h] [rbp-40h]
  _DWORD *TlsValue; // [rsp+30h] [rbp-30h] BYREF
  int v32; // [rsp+38h] [rbp-28h]
  __int64 v33; // [rsp+40h] [rbp-20h]
  int v34; // [rsp+48h] [rbp-18h]
  __int16 v35; // [rsp+4Ch] [rbp-14h]
  char v36; // [rsp+4Eh] [rbp-12h]
  char *v37; // [rsp+50h] [rbp-10h]
  int v38; // [rsp+58h] [rbp-8h]
  int v39; // [rsp+5Ch] [rbp-4h]
  unsigned __int64 v40; // [rsp+90h] [rbp+30h] BYREF
  __int64 v41; // [rsp+A8h] [rbp+48h] BYREF

  v6 = (char *)this + 32;
  if ( !this )
    v6 = 0;
  v37 = v6;
  v39 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v38 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v32 = 1;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v40 = 0;
  v41 = 0;
  DeferredHRow = CRecordGroup::GetDeferredHRow((CRecordset *)((char *)this + 736), *((_QWORD *)this + 91), &v40);
  v9 = DeferredHRow;
  if ( DeferredHRow < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && `CRecordset::GetDeferredHRow'::`10'::_bidPtrSA_030_367[0] )
    {
      v25 = *((_QWORD *)this + 91);
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      bidTraceW(
        `CRecordset::GetDeferredHRow'::`10'::_bidSrcFileA[0],
        375808,
        `CRecordset::GetDeferredHRow'::`10'::_bidPtrSA_030_367[0],
        BidObjectID,
        v9,
        v25);
    }
    v38 = v9;
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 9306121, L"<CRecordset::GetBookmarkInfo|ADO|ERR>  line %d\n", 9088);
      }
      else
      {
        v27 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v30) = 9088;
        bidTraceW(off_18012A208[0], 9306121, L"<CRecordset::GetBookmarkInfo|ADO|ERR> %u#, line %d\n", v27, v30);
      }
    }
    v16 = v38;
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v17 = TlsValue[2]-- == 1;
    if ( v17 )
    {
      v23 = TlsValue;
      v24 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
      if ( v24 )
      {
        SetErrorInfo(0, v24);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
        v23 = TlsValue;
      }
      if ( *((_BYTE *)v23 + 30) )
      {
        *((_QWORD *)v23 + 2) = 0;
        TlsValue[6] = 0;
      }
      else
      {
        TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
      }
    }
  }
  else
  {
    v38 = DeferredHRow;
    v41 = 0;
    v10 = *((_QWORD *)this + 141);
    if ( !v10 )
    {
      v38 = 0;
LABEL_10:
      if ( *((_BYTE *)this + 1256) == 1 )
      {
        v29 = (void *)*((_QWORD *)this + 146);
        if ( v29 )
        {
          CoTaskMemFree(v29);
          *((_QWORD *)this + 146) = 0;
          *((_QWORD *)this + 147) = 0;
        }
      }
      v12 = (unsigned __int8 *)this + 1168;
      *((_DWORD *)this + 296) = 0;
      v13 = *((_QWORD *)this + 150);
      if ( v13 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, char *))(*(_QWORD *)v41 + 32LL))(
                v41,
                v40,
                v13,
                (char *)this + 1168);
        if ( v14 == -2147217887 && *((_DWORD *)this + 296) == 8 )
        {
          *(_QWORD *)v12 = 0;
          *((_QWORD *)this + 147) = 0;
          v14 = 0;
        }
        v38 = v14;
        if ( v14 < 0 )
          CContext::PushError((CContext *)&TlsValue);
      }
      else
      {
        *(_QWORD *)v12 = 0;
        *((_QWORD *)this + 147) = 0;
        v38 = 0;
      }
      v15 = *((_DWORD *)this + 296);
      if ( v15 )
      {
        LODWORD(v40) = -2147217887;
        CContext::FailedDescription((CContext *)&TlsValue, (const int *)&v40, v15 + 2000);
      }
      *a2 = *((_QWORD *)this + 147);
      if ( (unsigned __int8)(*((_BYTE *)this + 1256) - 2) > 1u )
        v12 = *(unsigned __int8 **)v12;
      *a3 = v12;
      v16 = v38;
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      v17 = TlsValue[2]-- == 1;
      if ( v17 )
      {
        v18 = TlsValue;
        v19 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
        if ( v19 )
        {
          SetErrorInfo(0, v19);
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
          v18 = TlsValue;
        }
        if ( *((_BYTE *)v18 + 30) )
        {
          *((_QWORD *)v18 + 2) = 0;
          TlsValue[6] = 0;
        }
        else
        {
          TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
        }
      }
      return v16;
    }
    v11 = 0;
    if ( (*((_BYTE *)this + 1136) & 1) != 0 )
    {
      v41 = 0;
      if ( (_DWORD)v10 )
        v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, __int64 *))(**((_QWORD **)g_pStaticGlobals + 10) + 40LL))(
                *((_QWORD *)g_pStaticGlobals + 10),
                v10,
                &IID_IRowset,
                &v41);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(*((_QWORD *)this + 141));
      v41 = *((_QWORD *)this + 141);
    }
    v38 = v11;
    if ( v11 >= 0 )
      goto LABEL_10;
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 9307145, L"<CRecordset::GetBookmarkInfo|ADO|ERR>  line %d\n", 9089);
      }
      else
      {
        v28 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(off_18012A208[0], 9307145, L"<CRecordset::GetBookmarkInfo|ADO|ERR> %u#, line %d\n", v28, 9089);
      }
    }
    v16 = v38;
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v17 = TlsValue[2]-- == 1;
    if ( v17 )
    {
      v20 = TlsValue;
      v21 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
      if ( v21 )
      {
        SetErrorInfo(0, v21);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
        v20 = TlsValue;
      }
      if ( *((_BYTE *)v20 + 30) )
      {
        *((_QWORD *)v20 + 2) = 0;
        TlsValue[6] = 0;
      }
      else
      {
        TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
      }
    }
  }
  return v16;
}

```

## disassembly

```asm
0x180007900  mov     [rsp-28h+arg_8], rbx
0x180007905  mov     [rsp-28h+arg_10], rsi
0x18000790a  push    rbp
0x18000790b  push    rdi
0x18000790c  push    r12
0x18000790e  push    r14
0x180007910  push    r15
0x180007912  mov     rbp, rsp
0x180007915  sub     rsp, 60h
0x180007919  mov     r14, r8
0x18000791c  mov     r15, rdx
0x18000791f  mov     rbx, rcx
0x180007922  add     rcx, 20h ; ' '
0x180007926  xor     r12d, r12d
0x180007929  test    rbx, rbx
0x18000792c  cmovz   rcx, r12
0x180007930  mov     [rbp+var_10], rcx
0x180007934  mov     [rbp+var_4], r12d
0x180007938  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000793f  mov     ecx, [rcx+14h]; dwTlsIndex
0x180007942  call    cs:__imp_TlsGetValue
0x180007949  nop     dword ptr [rax+rax+00h]
0x18000794e  mov     [rbp+TlsValue], rax
0x180007952  mov     [rbp+var_8], r12d
0x180007956  test    rax, rax
0x180007959  jnz     loc_180007A69
0x18000795f  mov     [rbp+var_28], 1
0x180007966  mov     [rbp+var_20], r12
0x18000796a  mov     [rbp+var_18], r12d
0x18000796e  mov     [rbp+var_14], r12w
0x180007973  mov     [rbp+var_12], r12b
0x180007977  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x18000797b  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180007982  mov     ecx, [rcx+14h]; dwTlsIndex
0x180007985  call    cs:__imp_TlsSetValue
0x18000798c  nop     dword ptr [rax+rax+00h]
0x180007991  lea     rax, [rbp+TlsValue]
0x180007995  mov     [rbp+TlsValue], rax
0x180007999  mov     [rbp+arg_0], r12
0x18000799d  mov     [rbp+arg_18], r12
0x1800079a1  lea     rcx, [rbx+2E0h]; this
0x1800079a8  lea     r8, [rbp+arg_0]; unsigned __int64 *
0x1800079ac  mov     rdx, [rbx+2D8h]; __int64
0x1800079b3  call    ?GetDeferredHRow@CRecordGroup@@QEAAJ_JPEA_K@Z; CRecordGroup::GetDeferredHRow(__int64,unsigned __int64 *)
0x1800079b8  mov     esi, eax
0x1800079ba  test    eax, eax
0x1800079bc  js      loc_180007CB1
0x1800079c2  mov     [rbp+var_8], eax
0x1800079c5  mov     [rbp+arg_18], r12
0x1800079c9  mov     rdx, [rbx+468h]
0x1800079d0  test    rdx, rdx
0x1800079d3  jz      loc_180007DFC
0x1800079d9  mov     edi, r12d
0x1800079dc  test    byte ptr [rbx+470h], 1
0x1800079e3  jnz     short loc_180007A3B
0x1800079e5  mov     rax, [rdx]
0x1800079e8  mov     rcx, rdx
0x1800079eb  mov     rax, [rax+8]
0x1800079ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079f4  mov     rax, [rbx+468h]
0x1800079fb  mov     [rbp+arg_18], rax
0x1800079ff  mov     [rbp+var_8], edi
0x180007a02  test    edi, edi
0x180007a04  js      loc_180007B75
0x180007a0a  cmp     byte ptr [rbx+4E8h], 1
0x180007a11  jz      loc_180007E05
0x180007a17  lea     rdi, [rbx+490h]
0x180007a1e  mov     [rdi+10h], r12d
0x180007a22  mov     r8, [rbx+4B0h]
0x180007a29  test    r8, r8
0x180007a2c  jnz     short loc_180007A71
0x180007a2e  mov     [rdi], r12
0x180007a31  mov     [rdi+8], r12
0x180007a35  mov     [rbp+var_8], r12d
0x180007a39  jmp     short loc_180007A9E
0x180007a3b  mov     [rbp+arg_18], r12
0x180007a3f  test    edx, edx
0x180007a41  jz      short loc_1800079FF
0x180007a43  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180007a4a  mov     rcx, [rax+50h]
0x180007a4e  mov     rax, [rcx]
0x180007a51  lea     r9, [rbp+arg_18]
0x180007a55  lea     r8, IID_IRowset
0x180007a5c  mov     rax, [rax+28h]
0x180007a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a65  mov     edi, eax
0x180007a67  jmp     short loc_1800079FF
0x180007a69  inc     dword ptr [rax+8]
0x180007a6c  jmp     loc_180007999
0x180007a71  mov     rcx, [rbp+arg_18]
0x180007a75  mov     rax, [rcx]
0x180007a78  mov     r9, rdi
0x180007a7b  mov     rdx, [rbp+arg_0]
0x180007a7f  mov     rax, [rax+20h]
0x180007a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a88  cmp     eax, 80040E21h
0x180007a8d  jz      loc_180007E34
0x180007a93  mov     [rbp+var_8], eax
0x180007a96  test    eax, eax
0x180007a98  js      loc_180007BB4
0x180007a9e  mov     r8d, [rbx+4A0h]
0x180007aa5  test    r8d, r8d
0x180007aa8  jnz     loc_180007E4D
0x180007aae  mov     rax, [rbx+498h]
0x180007ab5  mov     [r15], rax
0x180007ab8  movzx   eax, byte ptr [rbx+4E8h]
0x180007abf  sub     al, 2
0x180007ac1  cmp     al, 1
0x180007ac3  ja      loc_180007E6D
0x180007ac9  mov     [r14], rdi
0x180007acc  mov     ebx, [rbp+var_8]
0x180007acf  mov     rcx, [rbp+arg_18]
0x180007ad3  test    rcx, rcx
0x180007ad6  jz      short loc_180007AE5
0x180007ad8  mov     rax, [rcx]
0x180007adb  mov     rax, [rax+10h]
0x180007adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ae4  nop
0x180007ae5  mov     rax, [rbp+TlsValue]
0x180007ae9  add     dword ptr [rax+8], 0FFFFFFFFh
0x180007aed  jnz     short loc_180007B23
0x180007aef  mov     rax, [rbp+TlsValue]
0x180007af3  mov     rdx, [rax+10h]; perrinfo
0x180007af7  test    rdx, rdx
0x180007afa  jnz     loc_180007BED
0x180007b00  cmp     byte ptr [rax+1Eh], 0
0x180007b04  jnz     loc_180007E75
0x180007b0a  xor     edx, edx; lpTlsValue
0x180007b0c  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180007b13  mov     ecx, [rcx+14h]; dwTlsIndex
0x180007b16  call    cs:__imp_TlsSetValue
0x180007b1d  nop     dword ptr [rax+rax+00h]
0x180007b22  nop
0x180007b23  jmp     short loc_180007B59
0x180007b25  mov     rax, [rbp+TlsValue]
0x180007b29  mov     rdx, [rax+10h]; perrinfo
0x180007b2d  test    rdx, rdx
0x180007b30  jnz     loc_180007BC2
0x180007b36  cmp     byte ptr [rax+1Eh], 0
0x180007b3a  jnz     loc_180007DEB
0x180007b40  xor     edx, edx; lpTlsValue
0x180007b42  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180007b49  mov     ecx, [rcx+14h]; dwTlsIndex
0x180007b4c  call    cs:__imp_TlsSetValue
0x180007b53  nop     dword ptr [rax+rax+00h]
0x180007b58  nop
0x180007b59  mov     eax, ebx
0x180007b5b  lea     r11, [rsp+60h+var_s0]
0x180007b60  mov     rbx, [r11+38h]
0x180007b64  mov     rsi, [r11+40h]
0x180007b68  mov     rsp, r11
0x180007b6b  pop     r15
0x180007b6d  pop     r14
0x180007b6f  pop     r12
0x180007b71  pop     rdi
0x180007b72  pop     rbp
0x180007b73  retn
0x180007b75  lea     rcx, [rbp+TlsValue]; this
0x180007b79  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180007b7e  test    byte ptr cs:_bidGblFlags, 2
0x180007b85  jnz     loc_180007D83
0x180007b8b  mov     ebx, [rbp+var_8]
0x180007b8e  mov     rcx, [rbp+arg_18]
0x180007b92  test    rcx, rcx
0x180007b95  jz      short loc_180007BA4
0x180007b97  mov     rax, [rcx]
0x180007b9a  mov     rax, [rax+10h]
0x180007b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba3  nop
0x180007ba4  mov     rax, [rbp+TlsValue]
0x180007ba8  add     dword ptr [rax+8], 0FFFFFFFFh
0x180007bac  jz      loc_180007B25
0x180007bb2  jmp     short loc_180007B59
0x180007bb4  lea     rcx, [rbp+TlsValue]; this
0x180007bb8  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180007bbd  jmp     loc_180007A9E
0x180007bc2  xor     ecx, ecx; dwReserved
0x180007bc4  call    cs:__imp_SetErrorInfo
0x180007bcb  nop     dword ptr [rax+rax+00h]
0x180007bd0  mov     rax, [rbp+TlsValue]
0x180007bd4  mov     rcx, [rax+10h]
0x180007bd8  mov     rax, [rcx]
0x180007bdb  mov     rax, [rax+10h]
0x180007bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007be4  mov     rax, [rbp+TlsValue]
0x180007be8  jmp     loc_180007B36
0x180007bed  xor     ecx, ecx; dwReserved
0x180007bef  call    cs:__imp_SetErrorInfo
0x180007bf6  nop     dword ptr [rax+rax+00h]
0x180007bfb  mov     rax, [rbp+TlsValue]
0x180007bff  mov     rcx, [rax+10h]
0x180007c03  mov     rax, [rcx]
0x180007c06  mov     rax, [rax+10h]
0x180007c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c0f  mov     rax, [rbp+TlsValue]
0x180007c13  jmp     loc_180007B00
0x180007c18  mov     [rbp+var_8], esi
0x180007c1b  lea     rcx, [rbp+TlsValue]; this
0x180007c1f  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180007c24  test    byte ptr cs:_bidGblFlags, 2
0x180007c2b  jnz     loc_180007D0A
0x180007c31  mov     ebx, [rbp+var_8]
0x180007c34  mov     rcx, [rbp+arg_18]
0x180007c38  test    rcx, rcx
0x180007c3b  jz      short loc_180007C4A
0x180007c3d  mov     rax, [rcx]
0x180007c40  mov     rax, [rax+10h]
0x180007c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c49  nop
0x180007c4a  mov     rax, [rbp+TlsValue]
0x180007c4e  add     dword ptr [rax+8], 0FFFFFFFFh
0x180007c52  jnz     short loc_180007C84
0x180007c54  mov     rax, [rbp+TlsValue]
0x180007c58  mov     rdx, [rax+10h]; perrinfo
0x180007c5c  test    rdx, rdx
0x180007c5f  jnz     short loc_180007C89
0x180007c61  cmp     byte ptr [rax+1Eh], 0
0x180007c65  jnz     loc_180007D72
0x180007c6b  xor     edx, edx; lpTlsValue
0x180007c6d  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180007c74  mov     ecx, [rcx+14h]; dwTlsIndex
0x180007c77  call    cs:__imp_TlsSetValue
0x180007c7e  nop     dword ptr [rax+rax+00h]
0x180007c83  nop
0x180007c84  jmp     loc_180007B59
0x180007c89  xor     ecx, ecx; dwReserved
0x180007c8b  call    cs:__imp_SetErrorInfo
0x180007c92  nop     dword ptr [rax+rax+00h]
0x180007c97  mov     rax, [rbp+TlsValue]
0x180007c9b  mov     rcx, [rax+10h]
0x180007c9f  mov     rax, [rcx]
0x180007ca2  mov     rax, [rax+10h]
0x180007ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cab  mov     rax, [rbp+TlsValue]
0x180007caf  jmp     short loc_180007C61
0x180007cb1  test    byte ptr cs:_bidGblFlags, 2
0x180007cb8  jz      loc_180007C18
0x180007cbe  mov     rcx, cs:?_bidPtrSA_030_367@?9??GetDeferredHRow@CRecordset@@QEAAJPEA_K@Z@4REBGEB; ushort const * const `CRecordset::GetDeferredHRow(unsigned __int64 *)'::`10'::_bidPtrSA_030_367
0x180007cc5  test    rcx, rcx
0x180007cc8  jz      loc_180007C18
0x180007cce  mov     rdi, [rbx+2D8h]
0x180007cd5  lea     rcx, [rbx+618h]; this
0x180007cdc  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180007ce1  mov     r8, cs:?_bidPtrSA_030_367@?9??GetDeferredHRow@CRecordset@@QEAAJPEA_K@Z@4REBGEB; ushort const * const `CRecordset::GetDeferredHRow(unsigned __int64 *)'::`10'::_bidPtrSA_030_367
0x180007ce8  mov     rcx, cs:?_bidSrcFileA@?9??GetDeferredHRow@CRecordset@@QEAAJPEA_K@Z@4REBDEB; char const * const `CRecordset::GetDeferredHRow(unsigned __int64 *)'::`10'::_bidSrcFileA
0x180007cef  mov     [rsp+60h+var_38], rdi
0x180007cf4  mov     dword ptr [rsp+60h+var_40], esi
0x180007cf8  mov     r9d, eax
0x180007cfb  mov     edx, 5BC00h
0x180007d00  call    _bidTraceW
0x180007d05  jmp     loc_180007C18
0x180007d0a  lea     rcx, [rbx+618h]; this
0x180007d11  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180007d16  cmp     eax, 0FFFFFFFFh
0x180007d19  jz      short loc_180007D4F
0x180007d1b  lea     rcx, [rbx+618h]; this
0x180007d22  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180007d27  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180007d2e  mov     dword ptr [rsp+60h+var_40], 2380h
0x180007d36  mov     r9d, eax
0x180007d39  lea     r8, aCrecordsetGetb_0; "<CRecordset::GetBookmarkInfo|ADO|ERR> %"...
0x180007d40  mov     edx, 8E0009h
0x180007d45  call    _bidTraceW
0x180007d4a  jmp     loc_180007C31
0x180007d4f  mov     r9d, 2380h
0x180007d55  lea     r8, aCrecordsetGetb; "<CRecordset::GetBookmarkInfo|ADO|ERR>  "...
0x180007d5c  mov     edx, 8E0009h
0x180007d61  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180007d68  call    _bidTraceW
0x180007d6d  jmp     loc_180007C31
0x180007d72  mov     [rax+10h], r12
0x180007d76  mov     rcx, [rbp+TlsValue]
0x180007d7a  mov     [rcx+18h], r12d
0x180007d7e  jmp     loc_180007C84
0x180007d83  lea     rcx, [rbx+618h]; this
0x180007d8a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180007d8f  cmp     eax, 0FFFFFFFFh
0x180007d92  jz      short loc_180007DC8
0x180007d94  lea     rcx, [rbx+618h]; this
0x180007d9b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180007da0  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180007da7  mov     dword ptr [rsp+60h+var_40], 2381h
0x180007daf  mov     r9d, eax
0x180007db2  lea     r8, aCrecordsetGetb_0; "<CRecordset::GetBookmarkInfo|ADO|ERR> %"...
0x180007db9  mov     edx, 8E0409h
0x180007dbe  call    _bidTraceW
0x180007dc3  jmp     loc_180007B8B
0x180007dc8  mov     r9d, 2381h
0x180007dce  lea     r8, aCrecordsetGetb; "<CRecordset::GetBookmarkInfo|ADO|ERR>  "...
0x180007dd5  mov     edx, 8E0409h
0x180007dda  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180007de1  call    _bidTraceW
0x180007de6  jmp     loc_180007B8B
0x180007deb  mov     [rax+10h], r12
0x180007def  mov     rcx, [rbp+TlsValue]
0x180007df3  mov     [rcx+18h], r12d
0x180007df7  jmp     loc_180007B59
0x180007dfc  mov     [rbp+var_8], r12d
0x180007e00  jmp     loc_180007A0A
0x180007e05  mov     rcx, [rbx+490h]; pv
  ... truncated ...
```

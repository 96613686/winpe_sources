# CRecordset::ReleaseBookmarkAccessor(void)

- ea: `0x18002ddd4`
- end: `0x18002e04a`
- name: `?ReleaseBookmarkAccessor@CRecordset@@AEAAJXZ`
- size: `630`
- prototype: `__int64 __fastcall(CRecordset *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18002adc0`

## callees

- `0x180020e20`
- `0x180020fc0`
- `0x18002ce00`
- `0x18002ddd4`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x18002de4a`
- `KERNEL32!TlsSetValue` at `0x18002e01e`
- `KERNEL32!TlsSetValue` at `0x18002de4a`
- `KERNEL32!TlsSetValue` at `0x18002e01e`
- `KERNEL32!TlsGetValue` at `0x18002de09`
- `KERNEL32!TlsGetValue` at `0x18002de09`
- `ole32!CoTaskMemFree` at `0x18002df9d`
- `ole32!CoTaskMemFree` at `0x18002df9d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002dfe8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002dfe8`

## string_xrefs

- `0x18002decd`: `<CRecordset::ReleaseBookmarkAccessor|ADO|ERR> %u#, line %d\n`
- `0x18002def3`: `<CRecordset::ReleaseBookmarkAccessor|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRecordset::ReleaseBookmarkAccessor(CRecordset *this)
{
  _DWORD *Value; // rax
  int Interface; // eax
  __int64 v4; // rbx
  unsigned int BidObjectID; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rdx
  void *v10; // rcx
  unsigned int v11; // edi
  _DWORD *v13; // rax
  IErrorInfo *v14; // rdx
  int v16; // [rsp+20h] [rbp-40h]
  _DWORD *TlsValue; // [rsp+30h] [rbp-30h] BYREF
  int v18; // [rsp+38h] [rbp-28h]
  __int64 v19; // [rsp+40h] [rbp-20h]
  int v20; // [rsp+48h] [rbp-18h]
  __int16 v21; // [rsp+4Ch] [rbp-14h]
  char v22; // [rsp+4Eh] [rbp-12h]
  __int64 v23; // [rsp+50h] [rbp-10h]
  int v24; // [rsp+58h] [rbp-8h]
  int v25; // [rsp+5Ch] [rbp-4h]
  int v26; // [rsp+80h] [rbp+20h] BYREF
  __int64 v27; // [rsp+88h] [rbp+28h] BYREF

  v23 = ((unsigned __int64)this + 32) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  v25 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v24 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v18 = 1;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v27 = 0;
  Interface = CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface((char *)this + 336, &v27);
  v4 = v27;
  if ( Interface < 0 )
  {
    v26 = -2146825037;
    if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v26) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_22;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v16 = 9054;
        v6 = 9271305;
LABEL_9:
        bidTraceW(
          off_18012A208[0],
          v6,
          L"<CRecordset::ReleaseBookmarkAccessor|ADO|ERR> %u#, line %d\n",
          BidObjectID,
          v16);
        goto LABEL_22;
      }
      v7 = 9054;
      v8 = 9271305;
LABEL_11:
      bidTraceW(off_18012A208[0], v8, L"<CRecordset::ReleaseBookmarkAccessor|ADO|ERR>  line %d\n", v7);
      goto LABEL_22;
    }
  }
  v9 = *((_QWORD *)this + 150);
  if ( !v9 )
    goto LABEL_19;
  v24 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, v9, 0);
  if ( v24 >= 0 )
  {
    *((_QWORD *)this + 150) = 0;
LABEL_19:
    if ( *((_BYTE *)this + 1256) == 1 )
    {
      v10 = (void *)*((_QWORD *)this + 146);
      if ( v10 )
      {
        CoTaskMemFree(v10);
        *((_QWORD *)this + 146) = 0;
        *((_QWORD *)this + 147) = 0;
      }
    }
    goto LABEL_22;
  }
  CContext::PushError((CContext *)&TlsValue);
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      v16 = 9063;
      v6 = 9280521;
      goto LABEL_9;
    }
    v7 = 9063;
    v8 = 9280521;
    goto LABEL_11;
  }
LABEL_22:
  v11 = v24;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( TlsValue[2]-- == 1 )
  {
    v13 = TlsValue;
    v14 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v14 )
    {
      SetErrorInfo(0, v14);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v13 = TlsValue;
    }
    if ( *((_BYTE *)v13 + 30) )
    {
      *((_QWORD *)v13 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18002ddd4  mov     [rsp-18h+arg_10], rbx
0x18002ddd9  push    rbp
0x18002ddda  push    rsi
0x18002dddb  push    rdi
0x18002dddc  mov     rbp, rsp
0x18002dddf  sub     rsp, 60h
0x18002dde3  mov     rdi, rcx
0x18002dde6  mov     rax, rcx
0x18002dde9  lea     r8, [rcx+20h]
0x18002dded  neg     rax
0x18002ddf0  sbb     rdx, rdx
0x18002ddf3  and     rdx, r8
0x18002ddf6  mov     [rbp+var_10], rdx
0x18002ddfa  xor     esi, esi
0x18002ddfc  mov     [rbp+var_4], esi
0x18002ddff  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002de06  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002de09  call    cs:__imp_TlsGetValue
0x18002de10  nop     dword ptr [rax+rax+00h]
0x18002de15  mov     [rbp+TlsValue], rax
0x18002de19  mov     [rbp+var_8], esi
0x18002de1c  test    rax, rax
0x18002de1f  jz      short loc_18002DE26
0x18002de21  inc     dword ptr [rax+8]
0x18002de24  jmp     short loc_18002DE5E
0x18002de26  mov     [rbp+var_28], 1
0x18002de2d  mov     [rbp+var_20], rsi
0x18002de31  mov     [rbp+var_18], esi
0x18002de34  mov     [rbp+var_14], si
0x18002de38  mov     [rbp+var_12], sil
0x18002de3c  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x18002de40  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002de47  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002de4a  call    cs:__imp_TlsSetValue
0x18002de51  nop     dword ptr [rax+rax+00h]
0x18002de56  lea     rax, [rbp+TlsValue]
0x18002de5a  mov     [rbp+TlsValue], rax
0x18002de5e  mov     [rbp+arg_8], rsi
0x18002de62  lea     rcx, [rdi+150h]
0x18002de69  lea     rdx, [rbp+arg_8]
0x18002de6d  call    ?GetInterface@?$CRsetOptionalInterface@UIAccessor@@$1?IID_IAccessor@@3U_GUID@@B@@QEAAJPEAPEAUIAccessor@@@Z; CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface(IAccessor * *)
0x18002de72  mov     rbx, [rbp+arg_8]
0x18002de76  test    eax, eax
0x18002de78  jns     loc_18002DF0B
0x18002de7e  mov     [rbp+arg_0], 800A0CB3h
0x18002de85  lea     rdx, [rbp+arg_0]; int *
0x18002de89  lea     rcx, [rbp+TlsValue]; this
0x18002de8d  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18002de92  test    eax, eax
0x18002de94  jz      short loc_18002DF0B
0x18002de96  test    byte ptr cs:_bidGblFlags, 2
0x18002de9d  jz      loc_18002DFB7
0x18002dea3  lea     rcx, [rdi+618h]; this
0x18002deaa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002deaf  cmp     eax, 0FFFFFFFFh
0x18002deb2  jz      short loc_18002DEE8
0x18002deb4  lea     rcx, [rdi+618h]; this
0x18002debb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002dec0  mov     [rsp+60h+var_40], 235Eh
0x18002dec8  mov     edx, 8D7809h
0x18002decd  lea     r8, aCrecordsetRele_5; "<CRecordset::ReleaseBookmarkAccessor|AD"...
0x18002ded4  mov     r9d, eax
0x18002ded7  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002dede  call    _bidTraceW
0x18002dee3  jmp     loc_18002DFB7
0x18002dee8  mov     r9d, 235Eh
0x18002deee  mov     edx, 8D7809h
0x18002def3  lea     r8, aCrecordsetRele_2; "<CRecordset::ReleaseBookmarkAccessor|AD"...
0x18002defa  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002df01  call    _bidTraceW
0x18002df06  jmp     loc_18002DFB7
0x18002df0b  mov     rdx, [rdi+4B0h]
0x18002df12  test    rdx, rdx
0x18002df15  jz      short loc_18002DF88
0x18002df17  mov     rax, [rbx]
0x18002df1a  xor     r8d, r8d
0x18002df1d  mov     rcx, rbx
0x18002df20  mov     rax, [rax+30h]
0x18002df24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df29  mov     [rbp+var_8], eax
0x18002df2c  test    eax, eax
0x18002df2e  jns     short loc_18002DF81
0x18002df30  lea     rcx, [rbp+TlsValue]; this
0x18002df34  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18002df39  test    byte ptr cs:_bidGblFlags, 2
0x18002df40  jz      short loc_18002DFB7
0x18002df42  lea     rcx, [rdi+618h]; this
0x18002df49  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002df4e  cmp     eax, 0FFFFFFFFh
0x18002df51  jz      short loc_18002DF71
0x18002df53  lea     rcx, [rdi+618h]; this
0x18002df5a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002df5f  mov     [rsp+60h+var_40], 2367h
0x18002df67  mov     edx, 8D9C09h
0x18002df6c  jmp     loc_18002DECD
0x18002df71  mov     r9d, 2367h
0x18002df77  mov     edx, 8D9C09h
0x18002df7c  jmp     loc_18002DEF3
0x18002df81  mov     [rdi+4B0h], rsi
0x18002df88  cmp     byte ptr [rdi+4E8h], 1
0x18002df8f  jnz     short loc_18002DFB7
0x18002df91  mov     rcx, [rdi+490h]; pv
0x18002df98  test    rcx, rcx
0x18002df9b  jz      short loc_18002DFB7
0x18002df9d  call    cs:__imp_CoTaskMemFree
0x18002dfa4  nop     dword ptr [rax+rax+00h]
0x18002dfa9  mov     [rdi+490h], rsi
0x18002dfb0  mov     [rdi+498h], rsi
0x18002dfb7  mov     edi, [rbp+var_8]
0x18002dfba  test    rbx, rbx
0x18002dfbd  jz      short loc_18002DFCF
0x18002dfbf  mov     rax, [rbx]
0x18002dfc2  mov     rcx, rbx
0x18002dfc5  mov     rax, [rax+10h]
0x18002dfc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfce  nop
0x18002dfcf  mov     rax, [rbp+TlsValue]
0x18002dfd3  add     dword ptr [rax+8], 0FFFFFFFFh
0x18002dfd7  jnz     short loc_18002E037
0x18002dfd9  mov     rax, [rbp+TlsValue]
0x18002dfdd  mov     rdx, [rax+10h]; perrinfo
0x18002dfe1  test    rdx, rdx
0x18002dfe4  jz      short loc_18002E00C
0x18002dfe6  xor     ecx, ecx; dwReserved
0x18002dfe8  call    cs:__imp_SetErrorInfo
0x18002dfef  nop     dword ptr [rax+rax+00h]
0x18002dff4  mov     rax, [rbp+TlsValue]
0x18002dff8  mov     rcx, [rax+10h]
0x18002dffc  mov     rax, [rcx]
0x18002dfff  mov     rax, [rax+10h]
0x18002e003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e008  mov     rax, [rbp+TlsValue]
0x18002e00c  cmp     [rax+1Eh], sil
0x18002e010  jnz     short loc_18002E02C
0x18002e012  xor     edx, edx; lpTlsValue
0x18002e014  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002e01b  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002e01e  call    cs:__imp_TlsSetValue
0x18002e025  nop     dword ptr [rax+rax+00h]
0x18002e02a  jmp     short loc_18002E037
0x18002e02c  mov     [rax+10h], rsi
0x18002e030  mov     rcx, [rbp+TlsValue]
0x18002e034  mov     [rcx+18h], esi
0x18002e037  mov     eax, edi
0x18002e039  mov     rbx, [rsp+60h+arg_10]
0x18002e041  add     rsp, 60h
0x18002e045  pop     rdi
0x18002e046  pop     rsi
0x18002e047  pop     rbp
0x18002e048  retn
```

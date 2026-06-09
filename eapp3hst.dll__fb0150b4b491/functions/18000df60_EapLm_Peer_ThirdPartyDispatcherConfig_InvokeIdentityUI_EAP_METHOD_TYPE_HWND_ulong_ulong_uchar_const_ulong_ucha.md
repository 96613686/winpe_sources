# EapLm::Peer::ThirdPartyDispatcherConfig::InvokeIdentityUI(_EAP_METHOD_TYPE *,HWND__ *,ulong,ulong,uchar const *,ulong,uchar const *,ulong *,uchar * *,wchar_t * *,_EAP_ERROR * *)

- ea: `0x18000df60`
- end: `0x18000e244`
- name: `?InvokeIdentityUI@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJPEAU_EAP_METHOD_TYPE@@PEAUHWND__@@KKPEBEK2PEAKPEAPEAEPEAPEA_WPEAPEAU_EAP_ERROR@@@Z`
- size: `740`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *__hidden this, struct _EAP_METHOD_TYPE *, HWND, unsigned int, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int *, unsigned __int8 **Src, wchar_t **, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000439c`
- `0x180005894`
- `0x1800067cc`
- `0x180006c0c`
- `0x18000c910`
- `0x18000df60`
- `0x18000ebe4`
- `0x18000ec84`
- `0x180012620`
- `0x180012c10`
- `0x180016e44`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::InvokeIdentityUI(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        struct _EAP_METHOD_TYPE *a2,
        HWND a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int8 *a6,
        unsigned int a7,
        const unsigned __int8 *a8,
        unsigned int *a9,
        unsigned __int8 **Src,
        wchar_t **a11,
        struct _EAP_ERROR **a12)
{
  EapLm::Peer::ThirdPartyDispatcherConfig *v13; // r9
  unsigned int v14; // edi
  unsigned __int8 **v15; // r12
  __int64 *v16; // rsi
  void *v17; // r13
  ReferenceCounted *v18; // r14
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  __int64 *v21; // rcx
  unsigned __int8 *v22; // r14
  int v23; // r8d
  int *v24; // r9
  struct _EAP_ERROR *v26; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int8 *v27; // [rsp+48h] [rbp-C0h] BYREF
  void *v28; // [rsp+50h] [rbp-B8h] BYREF
  size_t v29; // [rsp+58h] [rbp-B0h]
  ReferenceCounted *v30; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-A0h]
  void *v32; // [rsp+70h] [rbp-98h] BYREF
  BYTE type; // [rsp+78h] [rbp-90h]
  __int64 v34; // [rsp+7Ch] [rbp-8Ch]
  DWORD dwAuthorId; // [rsp+88h] [rbp-80h]
  __int64 v36; // [rsp+90h] [rbp-78h]
  void (__fastcall *v37)(ReferenceCounted *, _QWORD, __int64, __int64, HWND, void **, unsigned __int8 ***); // [rsp+98h] [rbp-70h]
  const ATL::CAtlException *v38; // [rsp+A0h] [rbp-68h] BYREF
  const EapHost::EapException *v39; // [rsp+A8h] [rbp-60h] BYREF
  const Exception *v40; // [rsp+B0h] [rbp-58h] BYREF
  void *v41; // [rsp+B8h] [rbp-50h] BYREF

  v13 = this;
  v14 = 0;
  LODWORD(v26) = 0;
  v15 = Src;
  if ( !Src )
    return 2147500035LL;
  v16 = (__int64 *)a11;
  if ( !a11 )
    return 2147500035LL;
  *Src = 0;
  *v16 = 0;
  v17 = 0;
  pv = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids, a5, a7);
    v13 = this;
  }
  type = a2->eapType.type;
  v34 = *(_QWORD *)&a2->eapType.dwVendorId;
  if ( type != 0xFE )
    v34 = 0;
  try
  {
    v32 = &EapHost::EapMethodType::`vftable';
    dwAuthorId = a2->dwAuthorId;
    EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(
      *((_QWORD **)v13 - 12),
      (ReferenceCounted *)&v30,
      (__int64)&v32);
    Src = 0;
    v18 = v30;
    v37 = *(void (__fastcall **)(ReferenceCounted *, _QWORD, __int64, __int64, HWND, void **, unsigned __int8 ***))(*(_QWORD *)v30 + 56LL);
    v36 = TempBuffer<0>::TempBuffer<0>((__int64)&v32, a7, a8);
    v19 = TempBuffer<0>::TempBuffer<0>((__int64)&v41, a5, a6);
    v37(v18, a4, v19, v36, a3, &v28, &Src);
    HeapAllocator::Free(v41);
    HeapAllocator::Free(v32);
    v20 = v29;
    if ( v29 )
    {
      com_ptr<unsigned char>::Assign(&v27, v28, v29);
      v21 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
      if ( Src )
        v21 = (__int64 *)Src;
      v17 = Copy<TaskAllocator>(v21);
      pv = v17;
      v22 = v27;
      v20 = v29;
    }
    else
    {
      *v15 = 0;
      v22 = 0;
    }
    *a9 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v20);
    v27 = 0;
    *v15 = v22;
    *v16 = (__int64)v17;
    HeapAllocator::Free(Src);
    Src = 0;
    if ( v30 )
      ReferenceCounted::Release(v30);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v26) = -2147024882;
    if ( a12 )
      *a12 = 0;
    v14 = (unsigned int)v26;
    goto LABEL_17;
  }
  catch ( const ATL::CAtlException *v38 )
  {
    LODWORD(v26) = *(_DWORD *)v38;
    if ( a12 )
      *a12 = 0;
    goto LABEL_16;
  }
  catch ( const EapHost::EapException *v39 )
  {
    EapHost::EapException2EapErrorOle(v39, (const struct EapHost::EapException *)a12, &v26, v24);
    goto LABEL_16;
  }
  catch ( const Exception *v40 )
  {
    EapHost::Exception2EapErrorOle(v40, (const struct Exception *)a12, &v26, v24);
LABEL_16:
    v14 = (unsigned int)v26;
    if ( (int)v26 < 0 )
LABEL_17:
      CoTaskMemFree(pv);
    v16 = (__int64 *)a11;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dSd(*((_QWORD *)WPP_GLOBAL_Control + 2), *v16, v23, *a9, *v16, v14);
  HeapAllocator::Free(v28);
  com_ptr<unsigned char>::Clear((void **)&v27);
  return v14;
}

```

## disassembly

```asm
0x18000df60  mov     [rsp+arg_18], r9d
0x18000df65  mov     [rsp+arg_10], r8
0x18000df6a  mov     [rsp+arg_0], rcx
0x18000df6f  push    rbx
0x18000df70  push    rsi
0x18000df71  push    rdi
0x18000df72  push    r12
0x18000df74  push    r13
0x18000df76  push    r14
0x18000df78  push    r15
0x18000df7a  sub     rsp, 0D0h
0x18000df81  mov     r14, rdx
0x18000df84  mov     r9, rcx
0x18000df87  xor     ebx, ebx
0x18000df89  mov     edi, ebx
0x18000df8b  mov     dword ptr [rsp+108h+var_C8], ebx
0x18000df8f  mov     r12, [rsp+108h+Src]
0x18000df97  test    r12, r12
0x18000df9a  jz      loc_18000E22C
0x18000dfa0  mov     rsi, [rsp+108h+arg_50]
0x18000dfa8  test    rsi, rsi
0x18000dfab  jz      loc_18000E22C
0x18000dfb1  mov     [r12], rbx
0x18000dfb5  mov     [rsi], rbx
0x18000dfb8  mov     r13d, ebx
0x18000dfbb  mov     [rsp+108h+pv], rbx
0x18000dfc0  mov     [rsp+108h+var_C0], rbx
0x18000dfc5  mov     [rsp+108h+var_B8], rbx
0x18000dfca  mov     [rsp+108h+var_B0], rbx
0x18000dfcf  lea     r15, WPP_GLOBAL_Control
0x18000dfd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfdd  cmp     rcx, r15
0x18000dfe0  jz      short loc_18000E016
0x18000dfe2  test    byte ptr [rcx+1Ch], 4
0x18000dfe6  jz      short loc_18000E016
0x18000dfe8  lea     edx, [rbx+0Ch]
0x18000dfeb  mov     eax, [rsp+108h+arg_30]
0x18000dff2  mov     dword ptr [rsp+108h+var_E8], eax
0x18000dff6  mov     r9d, [rsp+108h+arg_20]
0x18000dffe  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000e005  mov     rcx, [rcx+10h]
0x18000e009  call    WPP_SF_dd
0x18000e00e  mov     r9, [rsp+108h+arg_0]
0x18000e016  mov     cl, [r14]
0x18000e019  mov     [rsp+108h+var_90], cl
0x18000e01d  mov     eax, [r14+4]
0x18000e021  mov     dword ptr [rsp+108h+var_8C], eax
0x18000e025  mov     eax, [r14+8]
0x18000e029  mov     dword ptr [rsp+108h+var_8C+4], eax
0x18000e030  cmp     cl, 0FEh
0x18000e033  jz      short loc_18000E03A
0x18000e035  mov     [rsp+108h+var_8C], rbx
0x18000e03a  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000e041  mov     [rsp+108h+var_98], rax
0x18000e046  mov     eax, [r14+0Ch]
0x18000e04a  mov     [rsp+108h+var_80], eax
0x18000e051  lea     r8, [rsp+108h+var_98]
0x18000e056  lea     rdx, [rsp+108h+var_A8]
0x18000e05b  mov     rcx, [r9-60h]
0x18000e05f  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000e064  nop
0x18000e065  mov     [rsp+108h+Src], rbx
0x18000e06d  mov     r14, [rsp+108h+var_A8]
0x18000e072  mov     rax, [r14]
0x18000e075  mov     rax, [rax+38h]
0x18000e079  mov     [rsp+108h+var_70], rax
0x18000e081  mov     edx, [rsp+108h+arg_30]
0x18000e088  mov     r8, [rsp+108h+arg_38]
0x18000e090  lea     rcx, [rsp+108h+var_98]
0x18000e095  call    ??0?$TempBuffer@$0A@@@QEAA@_KPEBX@Z; TempBuffer<0>::TempBuffer<0>(unsigned __int64,void const *)
0x18000e09a  mov     [rsp+108h+var_78], rax
0x18000e0a2  mov     edx, [rsp+108h+arg_20]
0x18000e0a9  mov     r8, [rsp+108h+arg_28]
0x18000e0b1  lea     rcx, [rsp+108h+var_50]
0x18000e0b9  call    ??0?$TempBuffer@$0A@@@QEAA@_KPEBX@Z; TempBuffer<0>::TempBuffer<0>(unsigned __int64,void const *)
0x18000e0be  nop
0x18000e0bf  lea     rcx, [rsp+108h+Src]
0x18000e0c7  mov     [rsp+108h+var_D8], rcx
0x18000e0cc  lea     rcx, [rsp+108h+var_B8]
0x18000e0d1  mov     [rsp+108h+var_E0], rcx
0x18000e0d6  mov     rcx, [rsp+108h+arg_10]
0x18000e0de  mov     [rsp+108h+var_E8], rcx
0x18000e0e3  mov     r9, [rsp+108h+var_78]
0x18000e0eb  mov     r8, rax
0x18000e0ee  mov     edx, [rsp+108h+arg_18]
0x18000e0f5  mov     rcx, r14
0x18000e0f8  mov     rax, [rsp+108h+var_70]
0x18000e100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e105  nop
0x18000e106  mov     rcx, [rsp+108h+var_50]; void *
0x18000e10e  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000e113  nop
0x18000e114  mov     rcx, [rsp+108h+var_98]; void *
0x18000e119  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000e11e  mov     rcx, [rsp+108h+var_B0]
0x18000e123  test    rcx, rcx
0x18000e126  jz      short loc_18000E16B
0x18000e128  mov     r8, rcx
0x18000e12b  mov     rdx, [rsp+108h+var_B8]
0x18000e130  lea     rcx, [rsp+108h+var_C0]
0x18000e135  call    ?Assign@?$com_ptr@E@@QEAAXPEBE_K@Z; com_ptr<uchar>::Assign(uchar const *,unsigned __int64)
0x18000e13a  lea     rcx, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x18000e141  cmp     [rsp+108h+Src], rbx
0x18000e149  cmovnz  rcx, [rsp+108h+Src]; Src
0x18000e152  call    ??$Copy@VTaskAllocator@@@@YAPEA_WPEB_W@Z; Copy<TaskAllocator>(wchar_t const *)
0x18000e157  mov     r13, rax
0x18000e15a  mov     [rsp+108h+pv], rax
0x18000e15f  mov     r14, [rsp+108h+var_C0]
0x18000e164  mov     rcx, [rsp+108h+var_B0]
0x18000e169  jmp     short loc_18000E172
0x18000e16b  mov     [r12], rbx
0x18000e16f  mov     r14, rbx
0x18000e172  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000e177  mov     rcx, [rsp+108h+arg_40]
0x18000e17f  mov     [rcx], eax
0x18000e181  mov     [rsp+108h+var_C0], rbx
0x18000e186  mov     [r12], r14
0x18000e18a  mov     [rsi], r13
0x18000e18d  mov     rcx, [rsp+108h+Src]; void *
0x18000e195  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000e19a  mov     [rsp+108h+Src], rbx
0x18000e1a2  mov     rcx, [rsp+108h+var_A8]; this
0x18000e1a7  test    rcx, rcx
0x18000e1aa  jz      short loc_18000E1B2
0x18000e1ac  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000e1b1  nop
0x18000e1b2  jmp     short loc_18000E1E0
0x18000e1b4  mov     edi, dword ptr [rsp+108h+var_C8]
0x18000e1b8  jmp     short loc_18000E1C6
0x18000e1ba  jmp     short loc_18000E1BE
0x18000e1bc  jmp     short $+2
0x18000e1be  mov     edi, dword ptr [rsp+108h+var_C8]
0x18000e1c2  test    edi, edi
0x18000e1c4  jns     short loc_18000E1D1
0x18000e1c6  mov     rcx, [rsp+108h+pv]; pv
0x18000e1cb  call    cs:__imp_CoTaskMemFree
0x18000e1d1  mov     rsi, [rsp+108h+arg_50]
0x18000e1d9  lea     r15, WPP_GLOBAL_Control
0x18000e1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1e7  cmp     rcx, r15
0x18000e1ea  jz      short loc_18000E213
0x18000e1ec  test    byte ptr [rcx+1Ch], 4
0x18000e1f0  jz      short loc_18000E213
0x18000e1f2  mov     dword ptr [rsp+108h+var_E0], edi
0x18000e1f6  mov     rdx, [rsi]
0x18000e1f9  mov     [rsp+108h+var_E8], rdx
0x18000e1fe  mov     r9, [rsp+108h+arg_40]
0x18000e206  mov     r9d, [r9]
0x18000e209  mov     rcx, [rcx+10h]
0x18000e20d  call    WPP_SF_dSd
0x18000e212  nop
0x18000e213  mov     rcx, [rsp+108h+var_B8]; void *
0x18000e218  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000e21d  nop
0x18000e21e  lea     rcx, [rsp+108h+var_C0]
0x18000e223  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18000e228  mov     eax, edi
0x18000e22a  jmp     short loc_18000E231
0x18000e22c  mov     eax, 80004003h
0x18000e231  add     rsp, 0D0h
0x18000e238  pop     r15
0x18000e23a  pop     r14
0x18000e23c  pop     r13
0x18000e23e  pop     r12
0x18000e240  pop     rdi
0x18000e241  pop     rsi
0x18000e242  pop     rbx
0x18000e243  retn
```

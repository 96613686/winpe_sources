# CMqGenObj::InvokeTransactionalRuleHandlers(wchar_t *,wchar_t *,IUnknown *,ulong)

- ea: `0x14000d110`
- end: `0x14000d43a`
- name: `?InvokeTransactionalRuleHandlers@CMqGenObj@@UEAAJPEA_W0PEAUIUnknown@@K@Z`
- size: `810`
- prototype: `__int64 __fastcall(CMqGenObj *this, wchar_t *, wchar_t *, struct IUnknown *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140008c44`

## callees

- `0x140001cc6`
- `0x14000393c`
- `0x140003dc8`
- `0x1400046bc`
- `0x140004eb4`
- `0x140007e04`
- `0x140008034`
- `0x140008378`
- `0x140008520`
- `0x140008c04`
- `0x140009180`
- `0x14000cca0`
- `0x14000cf38`
- `0x14000d00c`
- `0x14000d110`
- `0x14000d648`
- `0x14000ec24`
- `0x140011ed0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14000d2e1`
- `KERNEL32!GetTickCount` at `0x14000d332`
- `KERNEL32!GetTickCount` at `0x14000d2e1`
- `KERNEL32!GetTickCount` at `0x14000d332`
- `ATL!__imp_AtlComPtrAssign` at `0x14000d26c`
- `ATL!__imp_AtlComPtrAssign` at `0x14000d26c`

## pseudocode

```c
__int64 __fastcall CMqGenObj::InvokeTransactionalRuleHandlers(
        CMqGenObj *this,
        wchar_t *a2,
        wchar_t *a3,
        struct IUnknown *a4,
        unsigned int a5)
{
  struct IMSMQPropertyBag *v8; // rbx
  int v9; // eax
  HRESULT v10; // eax
  signed int v11; // eax
  int v12; // esi
  int v13; // r14d
  unsigned int v14; // r13d
  CRuntimeTriggerInfo *v15; // rcx
  struct CRuntimeRuleInfo *Rule; // rax
  struct CRuntimeRuleInfo *v17; // rdi
  __int64 v18; // r10
  int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  struct IUnknown *v23; // rax
  struct IUnknown *v24; // rax
  int v25; // r8d
  __int64 result; // rax
  int v27; // eax
  unsigned int v28; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-B8h] BYREF
  struct IMSMQPropertyBag *v30; // [rsp+38h] [rbp-B0h] BYREF
  int v31; // [rsp+40h] [rbp-A8h] BYREF
  CRuntimeTriggerInfo *v32; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-98h] BYREF
  __int64 v34; // [rsp+58h] [rbp-90h] BYREF
  __int64 v35; // [rsp+60h] [rbp-88h] BYREF
  const _com_error *v36; // [rsp+68h] [rbp-80h] BYREF
  const bad_hresult *v37; // [rsp+70h] [rbp-78h] BYREF
  const bad_win32_error *v38; // [rsp+78h] [rbp-70h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v40[32]; // [rsp+A0h] [rbp-48h] BYREF
  struct IUnknown *v42; // [rsp+108h] [rbp+20h] BYREF

  v42 = a4;
  ppv = 0;
  v8 = 0;
  v30 = 0;
  if ( a4 )
  {
    v9 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::_QueryInterface<IUnknown *>(
           &v30,
           &v42);
    if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147467262 )
      _com_issue_error(v9);
    v8 = v30;
  }
  try
  {
    GetTriggerInfo(&v32, a2, a3);
    v10 = _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::CreateInstance(&ppv);
    if ( v10 < 0 )
    {
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v10);
      throw (bad_hresult *)pExceptionObject;
    }
    v42 = (struct IUnknown *)v8;
    _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(&v42);
    v11 = ReceiveMsgInTransaction(&v42);
    if ( v11 < 0 )
    {
      bad_win32_error::bad_win32_error((bad_win32_error *)v40, v11);
      throw (bad_hresult *)v40;
    }
    v12 = 0;
    v13 = 1;
    v14 = a5;
    v15 = v32;
    while ( v12 < *((_DWORD *)v15 + 532) )
    {
      if ( v12 >= 32 || (v13 & v14) != 0 )
      {
        Rule = CRuntimeTriggerInfo::GetRule(v15, v12);
        v17 = Rule;
        if ( *((_QWORD *)Rule + 135) )
        {
          v27 = _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_QueryInterface<ATL::CComPtr<IUnknown>>(
                  &ppv,
                  (char *)Rule + 1080);
          if ( ((v27 + 0x80000000) & 0x80000000) == 0 && v27 != -2147467262 )
            _com_issue_error(v27);
        }
        else
        {
          AtlComPtrAssign((char *)Rule + 1080, ppv);
          v18 = _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(&ppv);
          v19 = *((unsigned __int8 *)v17 + 1072);
          v20 = *((_QWORD *)v17 + 4);
          v33 = v20;
          if ( v20 )
            _InterlockedIncrement((volatile signed __int32 *)(v20 + 16));
          v21 = *((_QWORD *)v17 + 5);
          v34 = v21;
          if ( v21 )
            _InterlockedIncrement((volatile signed __int32 *)(v21 + 16));
          v22 = *(_QWORD *)v17;
          v35 = v22;
          if ( v22 )
            _InterlockedIncrement((volatile signed __int32 *)(v22 + 16));
          IMSMQRuleHandler::Init(v18, &v35, &v34, &v33, v19);
        }
        LODWORD(v42) = 0;
        GetTickCount();
        v31 = 1;
        if ( v12 <= 32
          || (v23 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(&ppv),
              IMSMQRuleHandler::CheckRuleCondition(v23, v8, &v31),
              v31) )
        {
          v24 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(&ppv);
          IMSMQRuleHandler::ExecuteRule(v24, v8, v25, (int *)&v42);
        }
        GetTickCount();
        if ( ((unsigned __int8)v42 & 2) != 0 )
        {
          CMqGenObj::AbortTransaction(this);
          SafeRelease<CQueue>(v32);
          R<IObjectContext>::~R<IObjectContext>(&v30);
          R<IObjectContext>::~R<IObjectContext>(&ppv);
          return 2147500037LL;
        }
        v13 *= 2;
        v15 = v32;
        if ( ((unsigned __int8)v42 & 1) != 0 )
          break;
      }
      else
      {
        v13 *= 2;
      }
      ++v12;
    }
    SafeRelease<CQueue>(v15);
    R<IObjectContext>::~R<IObjectContext>(&v30);
    R<IObjectContext>::~R<IObjectContext>(&ppv);
    result = 0;
  }
  catch ( const _com_error *v36 )
  {
    CMqGenObj::AbortTransaction(this);
    LODWORD(v42) = *((_DWORD *)v36 + 2);
    v28 = (unsigned int)v42;
    goto LABEL_35;
  }
  catch ( std::bad_alloc )
  {
    CMqGenObj::AbortTransaction(this);
    v28 = 1450;
    goto LABEL_35;
  }
  catch ( const bad_hresult *v37 )
  {
    CMqGenObj::AbortTransaction(this);
    LODWORD(v42) = (*(__int64 (__fastcall **)(const bad_hresult *))(*(_QWORD *)v37 + 16LL))(v37);
    v28 = (unsigned int)v42;
LABEL_35:
    R<IObjectContext>::~R<IObjectContext>(&v30);
    R<IObjectContext>::~R<IObjectContext>(&ppv);
    return v28;
  }
  catch ( const bad_win32_error *v38 )
  {
    CMqGenObj::AbortTransaction(this);
    LODWORD(v42) = (*(__int64 (__fastcall **)(const bad_win32_error *))(*(_QWORD *)v38 + 16LL))(v38);
    R<IObjectContext>::~R<IObjectContext>(&v30);
    R<IObjectContext>::~R<IObjectContext>(&ppv);
    return (unsigned int)v42;
  }
  GetTriggerInfo(&v32, a2, a3);
}

```

## disassembly

```asm
0x14000d110  mov     rax, rsp
0x14000d113  mov     [rax+10h], rbx
0x14000d117  mov     [rax+18h], rsi
0x14000d11b  mov     [rax+20h], r9
0x14000d11f  mov     [rax+8], rcx
0x14000d123  push    rdi
0x14000d124  push    r12
0x14000d126  push    r13
0x14000d128  push    r14
0x14000d12a  push    r15
0x14000d12c  sub     rsp, 0C0h
0x14000d133  mov     rdi, r8
0x14000d136  mov     rsi, rdx
0x14000d139  mov     r12, rcx
0x14000d13c  mov     [rsp+0E8h+ppv], 0
0x14000d145  xor     ebx, ebx
0x14000d147  mov     [rsp+0E8h+var_B0], rbx
0x14000d14c  test    r9, r9
0x14000d14f  jz      short loc_14000D184
0x14000d151  lea     rdx, [rax+20h]
0x14000d155  lea     rcx, [rsp+0E8h+var_B0]
0x14000d15a  call    ??$_QueryInterface@PEAUIUnknown@@@?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@AEAAJAEBQEAUIUnknown@@@Z; _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::_QueryInterface<IUnknown *>(IUnknown * const &)
0x14000d15f  mov     r15d, 80000000h
0x14000d165  lea     ecx, [rax+r15]
0x14000d169  test    r15d, ecx
0x14000d16c  jnz     short loc_14000D17D
0x14000d16e  cmp     eax, 80004002h
0x14000d173  jz      short loc_14000D17D
0x14000d175  mov     ecx, eax; int
0x14000d177  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000d17d  mov     rbx, [rsp+0E8h+var_B0]
0x14000d182  jmp     short loc_14000D18A
0x14000d184  mov     r15d, 80000000h
0x14000d18a  mov     r8, rdi
0x14000d18d  mov     rdx, rsi
0x14000d190  lea     rcx, [rsp+0E8h+var_A0]
0x14000d195  call    GetTriggerInfo
0x14000d19a  nop
0x14000d19b  mov     r9d, 17h
0x14000d1a1  lea     rcx, [rsp+0E8h+ppv]; ppv
0x14000d1a6  call    ?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEAAJPEB_WPEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::CreateInstance(wchar_t const *,IUnknown *,ulong)
0x14000d1ab  test    eax, eax
0x14000d1ad  jns     short loc_14000D1D2
0x14000d1af  mov     edx, eax; unsigned int
0x14000d1b1  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x14000d1b9  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x14000d1be  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x14000d1c5  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x14000d1cd  call    _CxxThrowException_0
0x14000d1d2  mov     [rsp+0E8h+arg_18], rbx
0x14000d1da  lea     rcx, [rsp+0E8h+arg_18]
0x14000d1e2  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(void)
0x14000d1e7  lea     rcx, [rsp+0E8h+arg_18]
0x14000d1ef  call    ReceiveMsgInTransaction
0x14000d1f4  test    eax, eax
0x14000d1f6  jns     short loc_14000D21B
0x14000d1f8  mov     edx, eax; unsigned int
0x14000d1fa  lea     rcx, [rsp+0E8h+var_48]; this
0x14000d202  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x14000d207  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x14000d20e  lea     rcx, [rsp+0E8h+var_48]; pExceptionObject
0x14000d216  call    _CxxThrowException_0
0x14000d21b  xor     esi, esi
0x14000d21d  lea     r14d, [rsi+1]
0x14000d221  mov     r13d, [rsp+0E8h+arg_20]
0x14000d229  mov     rcx, [rsp+0E8h+var_A0]; this
0x14000d22e  cmp     esi, [rcx+850h]
0x14000d234  jge     loc_14000D3BB
0x14000d23a  cmp     esi, 20h ; ' '
0x14000d23d  jge     short loc_14000D24C
0x14000d23f  test    r13d, r14d
0x14000d242  jnz     short loc_14000D24C
0x14000d244  add     r14d, r14d
0x14000d247  jmp     loc_14000D387
0x14000d24c  mov     edx, esi; int
0x14000d24e  call    ?GetRule@CRuntimeTriggerInfo@@QEAAPEAVCRuntimeRuleInfo@@J@Z; CRuntimeTriggerInfo::GetRule(long)
0x14000d253  mov     rdi, rax
0x14000d256  lea     rcx, [rax+438h]
0x14000d25d  cmp     qword ptr [rcx], 0
0x14000d261  jnz     loc_14000D38E
0x14000d267  mov     rdx, [rsp+0E8h+ppv]
0x14000d26c  call    cs:__imp_AtlComPtrAssign
0x14000d272  lea     rcx, [rsp+0E8h+ppv]
0x14000d277  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000d27c  mov     r10, rax
0x14000d27f  movzx   edx, byte ptr [rdi+430h]
0x14000d286  mov     rcx, [rdi+20h]
0x14000d28a  mov     [rsp+0E8h+var_98], rcx
0x14000d28f  test    rcx, rcx
0x14000d292  jz      short loc_14000D298
0x14000d294  lock inc dword ptr [rcx+10h]
0x14000d298  mov     rax, [rdi+28h]
0x14000d29c  mov     [rsp+0E8h+var_90], rax
0x14000d2a1  test    rax, rax
0x14000d2a4  jz      short loc_14000D2AA
0x14000d2a6  lock inc dword ptr [rax+10h]
0x14000d2aa  mov     rax, [rdi]
0x14000d2ad  mov     [rsp+0E8h+var_88], rax
0x14000d2b2  test    rax, rax
0x14000d2b5  jz      short loc_14000D2BB
0x14000d2b7  lock inc dword ptr [rax+10h]
0x14000d2bb  mov     [rsp+0E8h+var_C8], edx
0x14000d2bf  lea     r9, [rsp+0E8h+var_98]
0x14000d2c4  lea     r8, [rsp+0E8h+var_90]
0x14000d2c9  lea     rdx, [rsp+0E8h+var_88]
0x14000d2ce  mov     rcx, r10
0x14000d2d1  call    ?Init@IMSMQRuleHandler@@QEAAJV_bstr_t@@00J@Z; IMSMQRuleHandler::Init(_bstr_t,_bstr_t,_bstr_t,long)
0x14000d2d6  mov     dword ptr [rsp+0E8h+arg_18], 0
0x14000d2e1  call    cs:__imp_GetTickCount
0x14000d2e7  mov     [rsp+0E8h+var_A8], 1
0x14000d2ef  cmp     esi, 20h ; ' '
0x14000d2f2  jle     short loc_14000D315
0x14000d2f4  lea     rcx, [rsp+0E8h+ppv]
0x14000d2f9  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000d2fe  lea     r8, [rsp+0E8h+var_A8]; int *
0x14000d303  mov     rdx, rbx; struct IMSMQPropertyBag *
0x14000d306  mov     rcx, rax; this
0x14000d309  call    ?CheckRuleCondition@IMSMQRuleHandler@@QEAAJPEAUIMSMQPropertyBag@@PEAJ@Z; IMSMQRuleHandler::CheckRuleCondition(IMSMQPropertyBag *,long *)
0x14000d30e  cmp     [rsp+0E8h+var_A8], 0
0x14000d313  jz      short loc_14000D332
0x14000d315  lea     rcx, [rsp+0E8h+ppv]
0x14000d31a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000d31f  lea     r9, [rsp+0E8h+arg_18]; int *
0x14000d327  mov     rdx, rbx; struct IMSMQPropertyBag *
0x14000d32a  mov     rcx, rax; this
0x14000d32d  call    ?ExecuteRule@IMSMQRuleHandler@@QEAAJPEAUIMSMQPropertyBag@@JPEAJ@Z; IMSMQRuleHandler::ExecuteRule(IMSMQPropertyBag *,long,long *)
0x14000d332  call    cs:__imp_GetTickCount
0x14000d338  test    byte ptr [rsp+0E8h+arg_18], 2
0x14000d340  jz      short loc_14000D375
0x14000d342  mov     rcx, r12; this
0x14000d345  call    ?AbortTransaction@CMqGenObj@@AEAAXXZ; CMqGenObj::AbortTransaction(void)
0x14000d34a  nop
0x14000d34b  mov     rcx, [rsp+0E8h+var_A0]
0x14000d350  call    ??$SafeRelease@VCQueue@@@@YAXPEAVCQueue@@@Z; SafeRelease<CQueue>(CQueue *)
0x14000d355  nop
0x14000d356  lea     rcx, [rsp+0E8h+var_B0]
0x14000d35b  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000d360  nop
0x14000d361  lea     rcx, [rsp+0E8h+ppv]
0x14000d366  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000d36b  mov     eax, 80004005h
0x14000d370  jmp     loc_14000D41D
0x14000d375  add     r14d, r14d
0x14000d378  mov     rcx, [rsp+0E8h+var_A0]
0x14000d37d  test    byte ptr [rsp+0E8h+arg_18], 1
0x14000d385  jnz     short loc_14000D3BB
0x14000d387  inc     esi
0x14000d389  jmp     loc_14000D22E
0x14000d38e  mov     rdx, rcx
0x14000d391  lea     rcx, [rsp+0E8h+ppv]
0x14000d396  call    ??$_QueryInterface@V?$CComPtr@UIUnknown@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@AEAAJAEBV?$CComPtr@UIUnknown@@@ATL@@@Z; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_QueryInterface<ATL::CComPtr<IUnknown>>(ATL::CComPtr<IUnknown> const &)
0x14000d39b  lea     ecx, [rax+r15]
0x14000d39f  test    r15d, ecx
0x14000d3a2  jnz     loc_14000D2D6
0x14000d3a8  cmp     eax, 80004002h
0x14000d3ad  jz      loc_14000D2D6
0x14000d3b3  mov     ecx, eax; int
0x14000d3b5  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000d3bb  call    ??$SafeRelease@VCQueue@@@@YAXPEAVCQueue@@@Z; SafeRelease<CQueue>(CQueue *)
0x14000d3c0  nop
0x14000d3c1  lea     rcx, [rsp+0E8h+var_B0]
0x14000d3c6  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000d3cb  nop
0x14000d3cc  lea     rcx, [rsp+0E8h+ppv]
0x14000d3d1  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000d3d6  xor     eax, eax
0x14000d3d8  jmp     short loc_14000D41D
0x14000d3da  mov     ebx, dword ptr [rsp+0E8h+arg_18]
0x14000d3e1  lea     rcx, [rsp+0E8h+var_B0]
0x14000d3e6  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000d3eb  nop
0x14000d3ec  lea     rcx, [rsp+0E8h+ppv]
0x14000d3f1  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000d3f6  mov     eax, ebx
0x14000d3f8  jmp     short loc_14000D41D
0x14000d3fa  mov     ebx, 5AAh
0x14000d3ff  jmp     short loc_14000D3E1
0x14000d401  lea     rcx, [rsp+0E8h+var_B0]
0x14000d406  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000d40b  nop
0x14000d40c  lea     rcx, [rsp+0E8h+ppv]
0x14000d411  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000d416  mov     eax, dword ptr [rsp+0E8h+arg_18]
0x14000d41d  lea     r11, [rsp+0E8h+var_28]
0x14000d425  mov     rbx, [r11+38h]
0x14000d429  mov     rsi, [r11+40h]
0x14000d42d  mov     rsp, r11
0x14000d430  pop     r15
0x14000d432  pop     r14
0x14000d434  pop     r13
0x14000d436  pop     r12
0x14000d438  pop     rdi
0x14000d439  retn
```

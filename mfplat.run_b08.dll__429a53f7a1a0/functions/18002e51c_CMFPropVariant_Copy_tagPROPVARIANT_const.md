# CMFPropVariant::Copy(tagPROPVARIANT const *)

- ea: `0x18002e51c`
- end: `0x18002ea29`
- name: `?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z`
- size: `1293`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002dcc0`
- `0x180031cf0`
- `0x18013ec70`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x18002e51c`
- `0x180121581`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e9cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e9fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e9cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e9fb`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002e59c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002e59c`

## string_xrefs

- `0x18002e555`: `CMFPropVariant::Copy`
- `0x18002e7ee`: `CMFPropVariant::Copy`
- `0x18002e811`: `CMFPropVariant::Copy`
- `0x18002e893`: `CMFPropVariant::Copy`
- `0x18002e932`: `CMFPropVariant::Copy`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Copy(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)
{
  CallStackTracing *v3; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 m_dwDepth; // rcx
  __int64 v7; // rcx
  HRESULT v8; // ebx
  __int64 v10; // rdx
  struct CallStackContext *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  struct CallStackContext *v14; // rax
  struct CallStackContext *v15; // rax
  struct CallStackContext *v16; // rax
  struct CallStackContext *v17; // rax
  void *v18; // rax
  _QWORD *v19; // r14
  const void **v20; // rsi
  unsigned int i; // ebp
  void *v22; // rax
  CallStackScopeTrace v23; // [rsp+30h] [rbp-38h] BYREF

  v3 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v3 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v3 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v3->m_fEnabled )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v3);
    m_dwDepth = ThreadRelativeContext->m_dwDepth;
    if ( (unsigned int)m_dwDepth < ThreadRelativeContext->m_dwMaxDepth )
    {
      v7 = m_dwDepth;
      ThreadRelativeContext->m_rgInfo[v7].m_pszFunction = "CMFPropVariant::Copy";
      ThreadRelativeContext->m_rgInfo[v7].m_lineNumber = 181;
    }
    ++ThreadRelativeContext->m_dwDepth;
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( pvarDest == pvarSrc )
  {
    v8 = -2147467261;
    if ( !v3 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v3 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v3 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v3->m_fEnabled )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v3);
      if ( v11->m_result != -2147467261 )
        CallStackContext::TraceFailure(v11, "CMFPropVariant::Copy", 190, -2147467261);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_8;
    v10 = 15;
LABEL_33:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvarDest, v8);
    goto LABEL_8;
  }
  v8 = PropVariantCopy(pvarDest, pvarSrc);
  if ( v8 >= 0 )
    goto LABEL_8;
  if ( *(_WORD *)pvarSrc != 4161 )
  {
    v8 = -1072875800;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      v12 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( v12->m_result != -1072875800 )
        CallStackContext::TraceFailure(v12, "CMFPropVariant::Copy", 241, -1072875800);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        pvarDest,
        -1072875800);
LABEL_27:
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      v17 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( v17->m_result != v8 )
        CallStackContext::TraceFailure(v17, "CMFPropVariant::Copy", 247, v8);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_8;
    v10 = 20;
    goto LABEL_33;
  }
  *(_WORD *)pvarDest = 4161;
  *((_DWORD *)pvarDest + 2) = *((_DWORD *)pvarSrc + 2);
  v18 = CoTaskMemAlloc(16LL * *((unsigned int *)pvarSrc + 2));
  pvarDest[2] = v18;
  v19 = v18;
  if ( !v18 )
  {
    v8 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( v14->m_result != -2147024882 )
        CallStackContext::TraceFailure(v14, "CMFPropVariant::Copy", 224, -2147024882);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v13 = 16;
LABEL_56:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        pvarDest,
        -2147024882);
    }
    goto LABEL_27;
  }
  v20 = (const void **)pvarSrc[2];
  v8 = 0;
  for ( i = 0; *((_DWORD *)pvarSrc + 2) > i; ++i )
  {
    *(_DWORD *)v19 = *(_DWORD *)v20;
    v22 = CoTaskMemAlloc(*(unsigned int *)v20);
    v19[1] = v22;
    if ( !v22 )
    {
      v8 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
      if ( CallStackTracing::s_wpInstance->m_fEnabled )
      {
        v15 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( v15->m_result != -2147024882 )
          CallStackContext::TraceFailure(v15, "CMFPropVariant::Copy", 231, -2147024882);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          pvarDest,
          -2147024882);
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
      if ( CallStackTracing::s_wpInstance->m_fEnabled )
      {
        v16 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( v16->m_result != -2147024882 )
          CallStackContext::TraceFailure(v16, "CMFPropVariant::Copy", 236, -2147024882);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 18;
        goto LABEL_56;
      }
      goto LABEL_27;
    }
    memcpy_0(v22, v20[1], *(unsigned int *)v20);
    v19 += 2;
    v20 += 2;
  }
LABEL_8:
  CallStackScopeTrace::~CallStackScopeTrace(&v23);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002e51c  mov     [rsp+arg_10], rbx
0x18002e521  mov     [rsp+arg_18], rbp
0x18002e526  push    rsi
0x18002e527  push    rdi
0x18002e528  push    r13
0x18002e52a  push    r14
0x18002e52c  push    r15
0x18002e52e  sub     rsp, 40h
0x18002e532  mov     r15, rcx
0x18002e535  lea     rsi, stru_1801F8A30
0x18002e53c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e543  lea     rbp, stru_1801FC290
0x18002e54a  xor     r13d, r13d
0x18002e54d  mov     rdi, rdx
0x18002e550  test    rcx, rcx
0x18002e553  jz      short loc_18002E5D1
0x18002e555  lea     r14, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18002e55c  cmp     [rcx+8], r13b
0x18002e560  jz      short loc_18002E591
0x18002e562  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e567  mov     ecx, [rax+7C4h]
0x18002e56d  cmp     ecx, [rax+7C8h]
0x18002e573  jnb     short loc_18002E584
0x18002e575  add     rcx, rcx
0x18002e578  mov     [rax+rcx*8], r14
0x18002e57c  mov     dword ptr [rax+rcx*8+8], 0B5h
0x18002e584  inc     dword ptr [rax+7C4h]
0x18002e58a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e591  cmp     r15, rdi
0x18002e594  jz      short loc_18002E60F
0x18002e596  mov     rdx, rdi; pvarSrc
0x18002e599  mov     rcx, r15; pvarDest
0x18002e59c  call    cs:__imp_PropVariantCopy
0x18002e5a2  mov     ebx, eax
0x18002e5a4  test    eax, eax
0x18002e5a6  js      loc_18002E9AB
0x18002e5ac  lea     rcx, [rsp+68h+var_38]; this
0x18002e5b1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002e5b6  lea     r11, [rsp+68h+var_28]
0x18002e5bb  mov     eax, ebx
0x18002e5bd  mov     rbx, [r11+40h]
0x18002e5c1  mov     rbp, [r11+48h]
0x18002e5c5  mov     rsp, r11
0x18002e5c8  pop     r15
0x18002e5ca  pop     r14
0x18002e5cc  pop     r13
0x18002e5ce  pop     rdi
0x18002e5cf  pop     rsi
0x18002e5d0  retn
0x18002e5d1  mov     rax, cs:stru_1801FC290.__vftable
0x18002e5d8  mov     edx, 7F0h
0x18002e5dd  mov     rcx, rbp
0x18002e5e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e5e7  mov     rax, [rax+8]
0x18002e5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5f0  test    eax, eax
0x18002e5f2  jz      short loc_18002E600
0x18002e5f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e5fb  jmp     loc_18002E555
0x18002e600  mov     rcx, rsi
0x18002e603  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e60a  jmp     loc_18002E555
0x18002e60f  mov     ebx, 80004003h
0x18002e614  test    rcx, rcx
0x18002e617  jnz     short loc_18002E646
0x18002e619  mov     rax, cs:stru_1801FC290.__vftable
0x18002e620  mov     edx, 7F0h
0x18002e625  mov     rcx, rbp
0x18002e628  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e62f  mov     rax, [rax+8]
0x18002e633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e638  test    eax, eax
0x18002e63a  jnz     short loc_18002E663
0x18002e63c  mov     rcx, rsi; this
0x18002e63f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e646  cmp     [rcx+8], r13b
0x18002e64a  jnz     short loc_18002E66C
0x18002e64c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e653  jb      loc_18002E5AC
0x18002e659  mov     edx, 0Fh
0x18002e65e  jmp     loc_18002E75A
0x18002e663  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e66a  jmp     short loc_18002E646
0x18002e66c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e671  cmp     [rax+7CCh], ebx
0x18002e677  jz      short loc_18002E64C
0x18002e679  mov     r9d, ebx; int
0x18002e67c  mov     r8d, 0BEh; int
0x18002e682  mov     rdx, r14; char *
0x18002e685  mov     rcx, rax; this
0x18002e688  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e68d  jmp     short loc_18002E64C
0x18002e68f  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e696  mov     ebx, 0C00D36E8h
0x18002e69b  jnz     short loc_18002E6C7
0x18002e69d  mov     rax, cs:stru_1801FC290.__vftable
0x18002e6a4  mov     edx, 7F0h
0x18002e6a9  mov     rcx, rbp
0x18002e6ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e6b3  mov     rax, [rax+8]
0x18002e6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6bc  test    eax, eax
0x18002e6be  jnz     short loc_18002E6C7
0x18002e6c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e6c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e6ce  cmp     [rcx+8], r13b
0x18002e6d2  jnz     loc_18002E77D
0x18002e6d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e6df  jb      short loc_18002E704
0x18002e6e1  mov     edx, 13h
0x18002e6e6  mov     [rsp+68h+var_48], ebx
0x18002e6ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e6f1  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18002e6f8  mov     r9, r15
0x18002e6fb  mov     rcx, [rcx+10h]
0x18002e6ff  call    WPP_SF_qD
0x18002e704  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e70b  jnz     short loc_18002E737
0x18002e70d  mov     rax, cs:stru_1801FC290.__vftable
0x18002e714  mov     edx, 7F0h
0x18002e719  mov     rcx, rbp
0x18002e71c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e723  mov     rax, [rax+8]
0x18002e727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e72c  test    eax, eax
0x18002e72e  jnz     short loc_18002E737
0x18002e730  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e737  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e73e  cmp     [rcx+8], r13b
0x18002e742  jnz     loc_18002E981
0x18002e748  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e74f  jb      loc_18002E5AC
0x18002e755  mov     edx, 14h
0x18002e75a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e761  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18002e768  mov     r9, r15
0x18002e76b  mov     [rsp+68h+var_48], ebx
0x18002e76f  mov     rcx, [rcx+10h]
0x18002e773  call    WPP_SF_qD
0x18002e778  jmp     loc_18002E5AC
0x18002e77d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e782  cmp     [rax+7CCh], ebx
0x18002e788  jz      loc_18002E6D8
0x18002e78e  mov     r9d, ebx; int
0x18002e791  mov     r8d, 0F1h; int
0x18002e797  mov     rdx, r14; char *
0x18002e79a  mov     rcx, rax; this
0x18002e79d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e7a2  jmp     loc_18002E6D8
0x18002e7a7  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e7ae  mov     edi, 8007000Eh
0x18002e7b3  mov     ebx, edi
0x18002e7b5  jnz     short loc_18002E7E1
0x18002e7b7  mov     rax, cs:stru_1801FC290.__vftable
0x18002e7be  mov     edx, 7F0h
0x18002e7c3  mov     rcx, rbp
0x18002e7c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e7cd  mov     rax, [rax+8]
0x18002e7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7d6  test    eax, eax
0x18002e7d8  jnz     short loc_18002E7E1
0x18002e7da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e7e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e7e8  cmp     [rcx+8], r13b
0x18002e7ec  jnz     short loc_18002E80C
0x18002e7ee  lea     r14, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18002e7f5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e7fc  jb      loc_18002E704
0x18002e802  mov     edx, 10h
0x18002e807  jmp     loc_18002E918
0x18002e80c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e811  lea     r14, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18002e818  cmp     [rax+7CCh], edi
0x18002e81e  jz      short loc_18002E7F5
0x18002e820  mov     r9d, edi; int
0x18002e823  mov     r8d, 0E0h; int
0x18002e829  mov     rdx, r14; char *
0x18002e82c  mov     rcx, rax; this
0x18002e82f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e834  jmp     short loc_18002E7F5
0x18002e836  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e83d  lea     rbp, stru_1801FC290
0x18002e844  mov     edi, 8007000Eh
0x18002e849  mov     ebx, edi
0x18002e84b  jnz     loc_18002E921
0x18002e851  mov     rax, cs:stru_1801FC290.__vftable
0x18002e858  mov     edx, 7F0h
0x18002e85d  mov     rcx, rbp
0x18002e860  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e867  mov     rax, [rax+8]
0x18002e86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e870  lea     rsi, stru_1801F8A30
0x18002e877  test    eax, eax
0x18002e879  jnz     short loc_18002E882
0x18002e87b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e882  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e889  cmp     [rcx+8], r13b
0x18002e88d  jnz     loc_18002E92D
0x18002e893  lea     r14, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18002e89a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e8a1  jb      short loc_18002E8C6
0x18002e8a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e8aa  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18002e8b1  mov     edx, 11h
0x18002e8b6  mov     [rsp+68h+var_48], edi
0x18002e8ba  mov     r9, r15
0x18002e8bd  mov     rcx, [rcx+10h]
0x18002e8c1  call    WPP_SF_qD
0x18002e8c6  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e8cd  jnz     short loc_18002E8F9
0x18002e8cf  mov     rax, cs:stru_1801FC290.__vftable
0x18002e8d6  mov     edx, 7F0h
0x18002e8db  mov     rcx, rbp
0x18002e8de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e8e5  mov     rax, [rax+8]
0x18002e8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8ee  test    eax, eax
0x18002e8f0  jnz     short loc_18002E8F9
0x18002e8f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e8f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e900  cmp     [rcx+8], r13b
0x18002e904  jnz     short loc_18002E95E
0x18002e906  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e90d  jb      loc_18002E704
0x18002e913  mov     edx, 12h
0x18002e918  mov     [rsp+68h+var_48], edi
0x18002e91c  jmp     loc_18002E6EA
0x18002e921  lea     rsi, stru_1801F8A30
0x18002e928  jmp     loc_18002E882
0x18002e92d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e932  lea     r14, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18002e939  cmp     [rax+7CCh], edi
0x18002e93f  jz      loc_18002E89A
0x18002e945  mov     r9d, edi; int
0x18002e948  mov     r8d, 0E7h; int
0x18002e94e  mov     rdx, r14; char *
0x18002e951  mov     rcx, rax; this
0x18002e954  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e959  jmp     loc_18002E89A
0x18002e95e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e963  cmp     [rax+7CCh], edi
0x18002e969  jz      short loc_18002E906
0x18002e96b  mov     r9d, edi; int
0x18002e96e  mov     r8d, 0ECh; int
0x18002e974  mov     rdx, r14; char *
0x18002e977  mov     rcx, rax; this
0x18002e97a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e97f  jmp     short loc_18002E906
0x18002e981  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e986  cmp     [rax+7CCh], ebx
0x18002e98c  jz      loc_18002E748
0x18002e992  mov     r9d, ebx; int
0x18002e995  mov     r8d, 0F7h; int
0x18002e99b  mov     rdx, r14; char *
0x18002e99e  mov     rcx, rax; this
0x18002e9a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e9a6  jmp     loc_18002E748
0x18002e9ab  mov     eax, 1041h
0x18002e9b0  cmp     [rdi], ax
0x18002e9b3  jnz     loc_18002E68F
0x18002e9b9  mov     [r15], ax
0x18002e9bd  mov     eax, [rdi+8]
0x18002e9c0  mov     [r15+8], eax
0x18002e9c4  mov     ecx, [rdi+8]
0x18002e9c7  shl     rcx, 4; cb
0x18002e9cb  call    cs:__imp_CoTaskMemAlloc
0x18002e9d1  mov     [r15+10h], rax
0x18002e9d5  mov     r14, rax
0x18002e9d8  test    rax, rax
0x18002e9db  jz      loc_18002E7A7
0x18002e9e1  mov     rsi, [rdi+10h]
0x18002e9e5  mov     ebx, r13d
0x18002e9e8  mov     ebp, r13d
0x18002e9eb  cmp     [rdi+8], ebp
0x18002e9ee  jbe     loc_18002E5AC
0x18002e9f4  mov     eax, [rsi]
0x18002e9f6  mov     [r14], eax
0x18002e9f9  mov     ecx, [rsi]; cb
0x18002e9fb  call    cs:__imp_CoTaskMemAlloc
0x18002ea01  mov     [r14+8], rax
0x18002ea05  test    rax, rax
0x18002ea08  jz      loc_18002E836
0x18002ea0e  mov     r8d, [rsi]; Size
0x18002ea11  mov     rcx, rax; void *
0x18002ea14  mov     rdx, [rsi+8]; Src
0x18002ea18  call    memcpy_0
0x18002ea1d  add     r14, 10h
0x18002ea21  add     rsi, 10h
0x18002ea25  inc     ebp
0x18002ea27  jmp     short loc_18002E9EB
```

# CNodeMonitorNode::GetValueWrap(tagVARIANT *)

- ea: `0x1800588bc`
- end: `0x180058bd5`
- name: `?GetValueWrap@CNodeMonitorNode@@IEAAJPEAUtagVARIANT@@@Z`
- size: `793`
- prototype: `int(CNodeMonitorNode *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180058850`

## callees

- `0x18000caf4`
- `0x18000d4d4`
- `0x180025a78`
- `0x180025a9c`
- `0x18002dc38`
- `0x18002dc94`
- `0x18003fa90`
- `0x18003fb20`
- `0x18003fb44`
- `0x180041f2c`
- `0x180055de8`
- `0x1800588bc`
- `0x18005c628`
- `0x18005c930`
- `0x180060a78`
- `0x180060af0`
- `0x1800611c8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800588ff`
- `OLEAUT32!__imp_VariantInit` at `0x1800588ff`
- `dmxmlhelputils!XMLHEscapeString` at `0x180058a82`
- `dmxmlhelputils!XMLHEscapeString` at `0x180058a82`

## string_xrefs

- `0x1800588e9`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x1800589b7`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x180058a00`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x180058a9b`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x180058af2`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x180058b8f`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNodeMonitorNode::GetValueWrap(CNodeMonitorNode *this, struct tagVARIANT *a2)
{
  int CacheVersion; // ebx
  __int64 v5; // rdx
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rdx
  CNodeMonitorCsp *v9; // rbx
  int Session; // eax
  CNodeChangeSetBuilder *v11; // rcx
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rdx
  const unsigned __int16 *v17; // rbx
  int v18; // eax
  LONGLONG v19; // rcx
  unsigned __int16 *v20; // rax
  int v21; // [rsp+20h] [rbp-40h]
  int v22; // [rsp+20h] [rbp-40h]
  struct IConfigSession2 *v23; // [rsp+30h] [rbp-30h] BYREF
  LONGLONG v24; // [rsp+38h] [rbp-28h] BYREF
  const unsigned __int16 *v25; // [rsp+40h] [rbp-20h]
  struct tagSTGMEDIUM v26; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  unsigned __int16 *v28; // [rsp+98h] [rbp+38h] BYREF
  void *v29; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 *v30; // [rsp+A8h] [rbp+48h] BYREF

  if ( !a2 )
  {
    CacheVersion = -2147024809;
    v5 = 1313;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
      (const char *)(unsigned int)CacheVersion,
      v21);
    return (unsigned int)CacheVersion;
  }
  VariantInit(a2);
  switch ( *(_DWORD *)(*((_QWORD *)this + 7) + 4LL) )
  {
    case 2:
      v28 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v28,
        0);
      CacheVersion = CNodeCacheManager::GetCacheVersion((CNodeMonitorNode *)((char *)this + 8), &v28);
      if ( CacheVersion < 0 )
      {
        v8 = 1321;
        goto LABEL_40;
      }
LABEL_41:
      v20 = v28;
      a2->vt = 8;
      v28 = 0;
      a2->llVal = (LONGLONG)v20;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
      return 0;
    case 3:
      goto LABEL_16;
    case 6:
      v28 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v28,
        0);
      CacheVersion = CNodeCacheManager::GetNodesRegValueBstr((CNodeMonitorNode *)((char *)this + 8), v7, &v28);
      if ( CacheVersion < 0 )
      {
        v8 = 1384;
LABEL_40:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
          (const char *)(unsigned int)CacheVersion,
          v21);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
        return (unsigned int)CacheVersion;
      }
      goto LABEL_41;
    case 7:
    case 8:
      CacheVersion = CNodeCacheManager::GetExpectedValue((CNodeMonitorNode *)((char *)this + 8), a2);
      if ( CacheVersion < 0 )
      {
        v5 = 1395;
        goto LABEL_3;
      }
      return 0;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 7) + 4LL) != 9 )
  {
    CacheVersion = -2046820335;
    v5 = 1401;
    goto LABEL_3;
  }
LABEL_16:
  v23 = 0;
  v9 = (CNodeMonitorCsp *)*((_QWORD *)this + 10);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v23);
  Session = CNodeMonitorCsp::GetSession(v9, &v23);
  CacheVersion = Session;
  if ( Session < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x535,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
      (const char *)(unsigned int)Session,
      v21);
LABEL_36:
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v23);
    return (unsigned int)CacheVersion;
  }
  v12 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  v13 = (const unsigned __int16 *)*((_QWORD *)this + 5);
  v14 = *((_QWORD *)this + 7);
  v29 = 0;
  if ( *(_DWORD *)(v14 + 4) == 3 )
  {
    v15 = CNodeChangeSetBuilder::BuildChangeSet(v11, v13, v12, v23, &v29);
    CacheVersion = v15;
    if ( v15 < 0 )
    {
      v16 = 1340;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
        (const char *)(unsigned int)v15,
        v22);
LABEL_35:
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v29);
      goto LABEL_36;
    }
  }
  else
  {
    v15 = CNodeChangeSetBuilder::BuildChangeSetXml(v11, v13, v12, v23, &v29);
    CacheVersion = v15;
    if ( v15 < 0 )
    {
      v16 = 1344;
      goto LABEL_21;
    }
  }
  v30 = 0;
  if ( !v29 )
    goto LABEL_31;
  *(_QWORD *)&v26.tymed = 0;
  v26.pUnkForRelease = 0;
  v26.hBitmap = (HBITMAP)v29;
  wil::unique_hglobal_locked::unique_hglobal_locked((wil::unique_hglobal_locked *)&v24, &v26);
  v17 = v25;
  if ( v25 && *(_DWORD *)(*((_QWORD *)this + 7) + 4LL) == 9 )
  {
    LODWORD(v28) = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v30,
      0);
    v18 = XMLHEscapeString(v17, &v30, (unsigned int *)&v28);
    CacheVersion = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x552,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
        (const char *)(unsigned int)v18,
        v22);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
LABEL_34:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
      goto LABEL_35;
    }
    v17 = v30;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
  if ( !v17 )
LABEL_31:
    v17 = &Class;
  wil::make_bstr_nothrow(&v24, v17);
  v19 = v24;
  if ( !v24 )
  {
    CacheVersion = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
      (const char *)0x8007000ELL,
      v22);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
    goto LABEL_34;
  }
  a2->vt = 8;
  v24 = 0;
  a2->llVal = v19;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v29);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v23);
  return 0;
}

```

## disassembly

```asm
0x1800588bc  push    rbp
0x1800588be  push    rbx
0x1800588bf  push    rsi
0x1800588c0  push    rdi
0x1800588c1  push    r14
0x1800588c3  mov     rbp, rsp
0x1800588c6  sub     rsp, 60h
0x1800588ca  mov     rdi, rdx
0x1800588cd  mov     rsi, rcx
0x1800588d0  xor     r14d, r14d
0x1800588d3  test    rdx, rdx
0x1800588d6  jnz     short loc_1800588FC
0x1800588d8  mov     ebx, 80070057h
0x1800588dd  mov     edx, 521h; void *
0x1800588e2  mov     rcx, [rbp+28h]; this
0x1800588e6  mov     r9d, ebx; char *
0x1800588e9  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800588f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800588f5  mov     eax, ebx
0x1800588f7  jmp     loc_180058BC9
0x1800588fc  mov     rcx, rdi; pvarg
0x1800588ff  call    cs:__imp_VariantInit
0x180058906  nop     dword ptr [rax+rax+00h]
0x18005890b  mov     rcx, [rsi+38h]
0x18005890f  mov     edx, [rcx+4]
0x180058912  sub     edx, 2
0x180058915  jz      loc_180058B65
0x18005891b  sub     edx, 1
0x18005891e  jz      short loc_18005898D
0x180058920  sub     edx, 3
0x180058923  jz      short loc_18005895D
0x180058925  sub     edx, 1
0x180058928  jz      short loc_180058940
0x18005892a  sub     edx, 1
0x18005892d  jz      short loc_180058940
0x18005892f  cmp     edx, 1
0x180058932  jz      short loc_18005898D
0x180058934  mov     ebx, 86000011h
0x180058939  mov     edx, 579h
0x18005893e  jmp     short loc_1800588E2
0x180058940  lea     rcx, [rsi+8]; this
0x180058944  mov     rdx, rdi; struct tagVARIANT *
0x180058947  call    ?GetExpectedValue@CNodeCacheManager@@QEAAJPEAUtagVARIANT@@@Z; CNodeCacheManager::GetExpectedValue(tagVARIANT *)
0x18005894c  mov     ebx, eax
0x18005894e  test    eax, eax
0x180058950  jns     loc_180058BC7
0x180058956  mov     edx, 573h
0x18005895b  jmp     short loc_1800588E2
0x18005895d  mov     [rbp+arg_8], r14
0x180058961  xor     edx, edx
0x180058963  lea     rcx, [rbp+arg_8]
0x180058967  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005896c  lea     rcx, [rsi+8]; this
0x180058970  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x180058974  call    ?GetNodesRegValueBstr@CNodeCacheManager@@AEAAJPEBGPEAPEAG@Z; CNodeCacheManager::GetNodesRegValueBstr(ushort const *,ushort * *)
0x180058979  mov     ebx, eax
0x18005897b  test    eax, eax
0x18005897d  jns     loc_180058BAD
0x180058983  mov     edx, 568h
0x180058988  jmp     loc_180058B8C
0x18005898d  mov     [rbp+var_30], r14
0x180058991  mov     rbx, [rsi+50h]
0x180058995  lea     rcx, [rbp+var_30]
0x180058999  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005899e  lea     rdx, [rbp+var_30]; struct IConfigSession2 **
0x1800589a2  mov     rcx, rbx; this
0x1800589a5  call    ?GetSession@CNodeMonitorCsp@@QEAAJPEAPEAUIConfigSession2@@@Z; CNodeMonitorCsp::GetSession(IConfigSession2 * *)
0x1800589aa  mov     ebx, eax
0x1800589ac  test    eax, eax
0x1800589ae  jns     short loc_1800589CD
0x1800589b0  mov     rcx, [rbp+28h]; this
0x1800589b4  mov     r9d, eax; char *
0x1800589b7  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800589be  mov     edx, 535h; void *
0x1800589c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800589c8  jmp     loc_180058B21
0x1800589cd  mov     r8, [rsi+20h]; unsigned __int16 *
0x1800589d1  mov     rdx, [rsi+28h]; unsigned __int16 *
0x1800589d5  mov     rax, [rsi+38h]
0x1800589d9  mov     [rbp+arg_10], r14
0x1800589dd  mov     r9, [rbp+var_30]; struct IConfigSession2 *
0x1800589e1  cmp     dword ptr [rax+4], 3
0x1800589e5  lea     rax, [rbp+arg_10]
0x1800589e9  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800589ee  jnz     short loc_180058A18
0x1800589f0  call    ?BuildChangeSet@CNodeChangeSetBuilder@@QEAAJPEBG0PEAUIConfigSession2@@PEAPEAX@Z; CNodeChangeSetBuilder::BuildChangeSet(ushort const *,ushort const *,IConfigSession2 *,void * *)
0x1800589f5  mov     ebx, eax
0x1800589f7  test    eax, eax
0x1800589f9  jns     short loc_180058A2A
0x1800589fb  mov     edx, 53Ch; void *
0x180058a00  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180058a07  mov     r9d, eax; char *
0x180058a0a  mov     rcx, [rbp+28h]; this
0x180058a0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058a13  jmp     loc_180058B17
0x180058a18  call    ?BuildChangeSetXml@CNodeChangeSetBuilder@@QEAAJPEBG0PEAUIConfigSession2@@PEAPEAX@Z; CNodeChangeSetBuilder::BuildChangeSetXml(ushort const *,ushort const *,IConfigSession2 *,void * *)
0x180058a1d  mov     ebx, eax
0x180058a1f  test    eax, eax
0x180058a21  jns     short loc_180058A2A
0x180058a23  mov     edx, 540h
0x180058a28  jmp     short loc_180058A00
0x180058a2a  mov     [rbp+arg_18], r14
0x180058a2e  mov     rax, [rbp+arg_10]
0x180058a32  test    rax, rax
0x180058a35  jz      loc_180058ACA
0x180058a3b  mov     qword ptr [rbp+var_18.tymed], r14
0x180058a3f  mov     [rbp+var_18.pUnkForRelease], r14
0x180058a43  mov     qword ptr [rbp+var_18.8], rax
0x180058a47  lea     rdx, [rbp+var_18]; struct tagSTGMEDIUM *
0x180058a4b  lea     rcx, [rbp+var_28]; this
0x180058a4f  call    ??0unique_hglobal_locked@wil@@QEAA@AEAUtagSTGMEDIUM@@@Z; wil::unique_hglobal_locked::unique_hglobal_locked(tagSTGMEDIUM &)
0x180058a54  nop
0x180058a55  mov     rbx, [rbp+var_20]
0x180058a59  test    rbx, rbx
0x180058a5c  jz      short loc_180058ABC
0x180058a5e  mov     rax, [rsi+38h]
0x180058a62  cmp     dword ptr [rax+4], 9
0x180058a66  jnz     short loc_180058ABC
0x180058a68  mov     dword ptr [rbp+arg_8], r14d
0x180058a6c  xor     edx, edx
0x180058a6e  lea     rcx, [rbp+arg_18]
0x180058a72  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180058a77  lea     r8, [rbp+arg_8]
0x180058a7b  lea     rdx, [rbp+arg_18]
0x180058a7f  mov     rcx, rbx
0x180058a82  call    cs:__imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x180058a89  nop     dword ptr [rax+rax+00h]
0x180058a8e  mov     ebx, eax
0x180058a90  test    eax, eax
0x180058a92  jns     short loc_180058AB8
0x180058a94  mov     rcx, [rbp+28h]; this
0x180058a98  mov     r9d, eax; char *
0x180058a9b  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180058aa2  mov     edx, 552h; void *
0x180058aa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058aac  nop
0x180058aad  lea     rcx, [rbp+var_28]
0x180058ab1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?GlobalUnlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180058ab6  jmp     short loc_180058B0D
0x180058ab8  mov     rbx, [rbp+arg_18]
0x180058abc  lea     rcx, [rbp+var_28]
0x180058ac0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?GlobalUnlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180058ac5  test    rbx, rbx
0x180058ac8  jnz     short loc_180058AD1
0x180058aca  lea     rbx, Class
0x180058ad1  mov     rdx, rbx
0x180058ad4  lea     rcx, [rbp+var_28]
0x180058ad8  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180058add  mov     rcx, [rbp+var_28]
0x180058ae1  test    rcx, rcx
0x180058ae4  jnz     short loc_180058B2F
0x180058ae6  mov     rcx, [rbp+28h]; this
0x180058aea  mov     ebx, 8007000Eh
0x180058aef  mov     r9d, ebx; char *
0x180058af2  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180058af9  mov     edx, 55Dh; void *
0x180058afe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058b03  lea     rcx, [rbp+var_28]
0x180058b07  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058b0c  nop
0x180058b0d  lea     rcx, [rbp+arg_18]
0x180058b11  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058b16  nop
0x180058b17  lea     rcx, [rbp+arg_10]
0x180058b1b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?GlobalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180058b20  nop
0x180058b21  lea     rcx, [rbp+var_30]
0x180058b25  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180058b2a  jmp     loc_1800588F5
0x180058b2f  mov     word ptr [rdi], 8
0x180058b34  mov     [rbp+var_28], r14
0x180058b38  mov     [rdi+8], rcx
0x180058b3c  lea     rcx, [rbp+var_28]
0x180058b40  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058b45  nop
0x180058b46  lea     rcx, [rbp+arg_18]
0x180058b4a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058b4f  nop
0x180058b50  lea     rcx, [rbp+arg_10]
0x180058b54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?GlobalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180058b59  nop
0x180058b5a  lea     rcx, [rbp+var_30]
0x180058b5e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180058b63  jmp     short loc_180058BC7
0x180058b65  mov     [rbp+arg_8], r14
0x180058b69  xor     edx, edx
0x180058b6b  lea     rcx, [rbp+arg_8]
0x180058b6f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180058b74  lea     rcx, [rsi+8]; this
0x180058b78  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x180058b7c  call    ?GetCacheVersion@CNodeCacheManager@@QEAAJPEAPEAG@Z; CNodeCacheManager::GetCacheVersion(ushort * *)
0x180058b81  mov     ebx, eax
0x180058b83  test    eax, eax
0x180058b85  jns     short loc_180058BAD
0x180058b87  mov     edx, 529h; void *
0x180058b8c  mov     r9d, ebx; char *
0x180058b8f  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180058b96  mov     rcx, [rbp+28h]; this
0x180058b9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058b9f  lea     rcx, [rbp+arg_8]
0x180058ba3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058ba8  jmp     loc_1800588F5
0x180058bad  mov     rax, [rbp+arg_8]
0x180058bb1  mov     word ptr [rdi], 8
0x180058bb6  mov     [rbp+arg_8], r14
0x180058bba  mov     [rdi+8], rax
0x180058bbe  lea     rcx, [rbp+arg_8]
0x180058bc2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058bc7  xor     eax, eax
0x180058bc9  add     rsp, 60h
0x180058bcd  pop     r14
0x180058bcf  pop     rdi
0x180058bd0  pop     rsi
0x180058bd1  pop     rbx
0x180058bd2  pop     rbp
0x180058bd3  retn
```

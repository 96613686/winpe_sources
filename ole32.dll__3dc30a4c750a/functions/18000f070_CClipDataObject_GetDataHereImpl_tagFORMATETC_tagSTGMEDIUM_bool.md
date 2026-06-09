# CClipDataObject::GetDataHereImpl(tagFORMATETC *,tagSTGMEDIUM *,bool)

- ea: `0x18000f070`
- end: `0x18000f373`
- name: `?GetDataHereImpl@CClipDataObject@@IEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@_N@Z`
- size: `771`
- prototype: `HRESULT __fastcall(CClipDataObject *this, tagFORMATETC *pformatetc, tagSTGMEDIUM *pmedium, bool fTryWrappedObject)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d470`
- `0x1800908c0`

## callees

- `0x18000d38c`
- `0x18000d954`
- `0x18000e010`
- `0x18000e034`
- `0x18000e980`
- `0x18000ebc8`
- `0x18000ef7c`
- `0x18000efd0`
- `0x18000f070`
- `0x18000f49c`
- `0x180010098`
- `0x180031ff0`
- `0x1800405d4`
- `0x1800916a0`
- `0x180092e10`
- `0x1800a5740`
- `0x1800a57c4`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!Sleep` at `0x18000f268`
- `KERNELBASE!Sleep` at `0x18000f268`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18000f1d3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18000f1d3`
- `USER32!OpenClipboard` at `0x18000f191`
- `USER32!OpenClipboard` at `0x18000f271`
- `USER32!OpenClipboard` at `0x18000f191`
- `USER32!OpenClipboard` at `0x18000f271`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetClipboardAccessDeniedData` at `0x18000f2ec`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetClipboardAccessDeniedData` at `0x18000f2ec`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000f19f`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000f19f`

## pseudocode

```c
__int64 __fastcall CClipDataObject::GetDataHereImpl(
        CClipDataObject *this,
        tagFORMATETC *pformatetc,
        tagSTGMEDIUM *pmedium,
        bool fTryWrappedObject)
{
  FormatMatchFlag formatMatchFlag; // r12d
  unsigned int cfFormat; // ecx
  int v10; // edx
  HRESULT ClipboardAccessDeniedData; // ebx
  ClipboardDataObjectTask *ptr; // rcx
  CClipDataObject *v14; // rcx
  bool *p_m_fIsEdpAccessDenied; // rdi
  HWND PrivateClipboardWindow; // rax
  HWND v17; // rbx
  unsigned int v18; // edx
  unsigned int v19; // edx
  HRESULT v20; // eax
  ClipboardDataObjectTask *v21; // rdx
  IDataObject *m_pDataObject; // rcx
  void *handle; // [rsp+40h] [rbp-18h] BYREF
  Microsoft::WRL::ComPtr<ClipboardDataObjectTask> pTask; // [rsp+48h] [rbp-10h] BYREF
  OleClipboardLock clipLock; // [rsp+A0h] [rbp+48h] BYREF

  handle = 0;
  clipLock.m_locked = 0;
  if ( !CThreadCheck::VerifyThreadId(&this->CThreadCheck) )
  {
    ClipboardAccessDeniedData = -2147417842;
    goto LABEL_8;
  }
  formatMatchFlag = 0;
  CClipDataObject::CacheDataPointer(this, &pTask);
  if ( !fTryWrappedObject )
    goto LABEL_3;
  m_pDataObject = this->m_pDataObject;
  if ( !m_pDataObject )
    goto LABEL_3;
  ClipboardAccessDeniedData = ((__int64 (__fastcall *)(IDataObject *, tagFORMATETC *, tagSTGMEDIUM *))m_pDataObject->lpVtbl[1].AddRef)(
                                m_pDataObject,
                                pformatetc,
                                pmedium);
  if ( ClipboardAccessDeniedData >= 0 && pTask.ptr_ && MediumContainsObject(pmedium) )
    ClipboardDataObjectTask::RunToTimeLimit(v21);
  if ( ClipboardAccessDeniedData )
  {
LABEL_3:
    cfFormat = pformatetc->cfFormat;
    if ( cfFormat <= 0xE && (v10 = 16908, _bittest(&v10, cfFormat)) || (unsigned __int16)(cfFormat - 768) <= 0xFFu )
    {
      ClipboardAccessDeniedData = -2147221404;
      goto $logRtn_1;
    }
    formatMatchFlag = CClipDataObject::MatchFormatetc(this, pformatetc, 1, 0, 1);
    if ( formatMatchFlag == FORMAT_BADMATCH )
    {
      ClipboardAccessDeniedData = -2147221404;
      p_m_fIsEdpAccessDenied = &this->m_fIsEdpAccessDenied;
      goto $errRtn_8;
    }
    if ( !pmedium )
    {
      ClipboardAccessDeniedData = CClipDataObject::OleIsClipboardFormatAvailable(v14, pformatetc->cfFormat) == 0
                                ? 0x8004006A
                                : 0;
      goto $logRtn_1;
    }
    p_m_fIsEdpAccessDenied = &this->m_fIsEdpAccessDenied;
    if ( this->m_fIsEdpAccessDenied )
    {
      ClipboardAccessDeniedData = EdpGetClipboardAccessDeniedData(pformatetc->cfFormat, &handle);
      if ( !ClipboardAccessDeniedData )
      {
LABEL_18:
        v19 = 0;
        if ( pmedium->tymed == 8 || (v19 = GlobalSize(handle)) != 0 )
        {
          switch ( pmedium->tymed )
          {
            case 1u:
              v20 = UtHGLOBALtoHGLOBAL(handle, v19, pmedium->hBitmap);
              goto LABEL_24;
            case 2u:
              ClipboardAccessDeniedData = -2147467263;
              break;
            case 4u:
              v20 = UtHGLOBALtoStm(handle, v19, pmedium->pstm);
LABEL_24:
              ClipboardAccessDeniedData = v20;
              break;
            case 8u:
              v20 = UtHGLOBALtoStorage(handle, pmedium->pstg);
              goto LABEL_24;
            default:
              ClipboardAccessDeniedData = -2147221399;
              break;
          }
        }
        else
        {
          ClipboardAccessDeniedData = -2147221037;
        }
$errRtn_8:
        if ( !*p_m_fIsEdpAccessDenied && OleClipboardLock::Release(&clipLock) < 0 && !ClipboardAccessDeniedData )
          ClipboardAccessDeniedData = -2147221036;
        CClipDataObject::FreeResources(this, RESET_AND_FREE);
      }
    }
    else
    {
      PrivateClipboardWindow = GetPrivateClipboardWindow(CLIP_CREATEIFNOTTHERE);
      v17 = PrivateClipboardWindow;
      if ( PrivateClipboardWindow )
      {
        if ( !OpenClipboard(PrivateClipboardWindow) )
        {
          Sleep(0);
          if ( !OpenClipboard(v17) )
          {
            ClipboardAccessDeniedData = -2147221040;
            goto $logRtn_1;
          }
        }
        if ( (unsigned int)EdpGetIsManaged() )
          EdpInlSetCurrentThreadPolicyEvaluation(1);
        v18 = pformatetc->cfFormat;
        clipLock.m_locked = 1;
        ClipboardAccessDeniedData = CClipDataObject::OleGetClipboardData(this, v18, &handle);
        if ( ClipboardAccessDeniedData )
          goto $errRtn_8;
        goto LABEL_18;
      }
      ClipboardAccessDeniedData = -2147467259;
    }
  }
$logRtn_1:
  OleClipboardTracing::CClipDataObject_GetDataHereImplEtw(
    ClipboardAccessDeniedData,
    pformatetc,
    pmedium,
    fTryWrappedObject,
    formatMatchFlag,
    this->m_pDataObject,
    pTask.ptr_);
  ptr = pTask.ptr_;
  if ( pTask.ptr_ )
  {
    pTask.ptr_ = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITypeLibRegistrationReader,Microsoft::WRL::FtmBase>::Release((Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITypeLibRegistrationReader,Microsoft::WRL::FtmBase> *)ptr);
  }
LABEL_8:
  OleClipboardLock::Release(&clipLock);
  return (unsigned int)ClipboardAccessDeniedData;
}

```

## disassembly

```asm
0x18000f070  push    rbp
0x18000f072  push    rbx
0x18000f073  push    rsi
0x18000f074  push    rdi
0x18000f075  push    r12
0x18000f077  push    r13
0x18000f079  push    r14
0x18000f07b  push    r15
0x18000f07d  mov     rbp, rsp
0x18000f080  sub     rsp, 58h
0x18000f084  mov     rsi, this
0x18000f087  mov     [rbp+handle], 0
0x18000f08f  add     this, 10h; this
0x18000f093  mov     [rbp+clipLock.m_locked], 0
0x18000f097  mov     r13b, fTryWrappedObject
0x18000f09a  mov     r14, pmedium
0x18000f09d  mov     r15, pformatetc
0x18000f0a0  call    ?VerifyThreadId@CThreadCheck@@QEAAHXZ; CThreadCheck::VerifyThreadId(void)
0x18000f0a5  test    eax, eax
0x18000f0a7  jz      loc_18000F2B3
0x18000f0ad  lea     pformatetc, [rbp+pTask]; result
0x18000f0b1  mov     this, rsi; this
0x18000f0b4  xor     r12d, r12d
0x18000f0b7  call    ?CacheDataPointer@CClipDataObject@@QEAA?AV?$ComPtr@VClipboardDataObjectTask@@@WRL@Microsoft@@XZ; CClipDataObject::CacheDataPointer(void)
0x18000f0bc  test    r13b, r13b
0x18000f0bf  jnz     loc_18000F2BD
0x18000f0c5  movzx   ecx, word ptr [r15]
0x18000f0c9  cmp     ecx, 0Eh
0x18000f0cc  ja      short loc_18000F12D
0x18000f0ce  mov     edx, 420Ch
0x18000f0d3  bt      edx, ecx
0x18000f0d6  jnb     short loc_18000F12D
0x18000f0d8  mov     ebx, 80040064h
0x18000f0dd  mov     rax, [rbp+pTask.ptr_]
0x18000f0e1  mov     fTryWrappedObject, r13b; fTryWrappedObject
0x18000f0e4  mov     [rsp+58h+var_28], rax; pTask
0x18000f0e9  mov     pmedium, r14; pmedium
0x18000f0ec  mov     rax, [rsi+38h]
0x18000f0f0  mov     pformatetc, r15; pformatetc
0x18000f0f3  mov     [rsp+58h+pDataObject], rax; pDataObject
0x18000f0f8  mov     ecx, ebx; hr
0x18000f0fa  mov     [rsp+58h+formatMatchFlag], r12d; formatMatchFlag
0x18000f0ff  call    ?CClipDataObject_GetDataHereImplEtw@OleClipboardTracing@@SAXJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@_NW4FormatMatchFlag@@PEAUIDataObject@@PEAVClipboardDataObjectTask@@@Z; OleClipboardTracing::CClipDataObject_GetDataHereImplEtw(long,tagFORMATETC *,tagSTGMEDIUM *,bool,FormatMatchFlag,IDataObject *,ClipboardDataObjectTask *)
0x18000f104  mov     this, [rbp+pTask.ptr_]; this
0x18000f108  test    this, this
0x18000f10b  jnz     loc_18000F361
0x18000f111  lea     this, [rbp+clipLock]; this
0x18000f115  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000f11a  mov     eax, ebx
0x18000f11c  add     rsp, 58h
0x18000f120  pop     r15
0x18000f122  pop     r14
0x18000f124  pop     r13
0x18000f126  pop     r12
0x18000f128  pop     rdi
0x18000f129  pop     rsi
0x18000f12a  pop     rbx
0x18000f12b  pop     rbp
0x18000f12c  retn
0x18000f12d  mov     eax, 300h
0x18000f132  sub     cx, ax
0x18000f135  mov     eax, 0FFh
0x18000f13a  cmp     cx, ax
0x18000f13d  jbe     short loc_18000F0D8
0x18000f13f  mov     ebx, 1
0x18000f144  xor     r9d, r9d; ptymed
0x18000f147  mov     r8d, ebx; fNativeOnly
0x18000f14a  mov     [rsp+58h+formatMatchFlag], ebx; fAllowSynthesized
0x18000f14e  mov     pformatetc, r15; pformatetc
0x18000f151  mov     this, rsi; this
0x18000f154  call    ?MatchFormatetc@CClipDataObject@@AEAA?AW4FormatMatchFlag@@PEAUtagFORMATETC@@HPEAW4tagTYMED@@H@Z; CClipDataObject::MatchFormatetc(tagFORMATETC *,int,tagTYMED *,int)
0x18000f159  mov     r12d, eax
0x18000f15c  cmp     eax, 2
0x18000f15f  jz      loc_18000F25B
0x18000f165  test    r14, r14
0x18000f168  jz      loc_18000F241
0x18000f16e  lea     rdi, [rsi+45h]
0x18000f172  cmp     byte ptr [rdi], 0
0x18000f175  jnz     loc_18000F2E4
0x18000f17b  mov     ecx, ebx; fFlags
0x18000f17d  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x18000f182  mov     rbx, rax
0x18000f185  test    rax, rax
0x18000f188  jz      loc_18000F301
0x18000f18e  mov     this, rax; hWndNewOwner
0x18000f191  call    cs:__imp_OpenClipboard
0x18000f197  test    eax, eax
0x18000f199  jz      loc_18000F266
0x18000f19f  call    cs:__imp_EdpGetIsManaged
0x18000f1a5  test    eax, eax
0x18000f1a7  jnz     loc_18000F30B
0x18000f1ad  movzx   edx, word ptr [r15]; cf
0x18000f1b1  lea     pmedium, [rbp+handle]; phglobal
0x18000f1b5  mov     this, rsi; this
0x18000f1b8  mov     [rbp+clipLock.m_locked], 1
0x18000f1bc  call    ?OleGetClipboardData@CClipDataObject@@AEAAJIPEAPEAX@Z; CClipDataObject::OleGetClipboardData(uint,void * *)
0x18000f1c1  mov     ebx, eax
0x18000f1c3  test    eax, eax
0x18000f1c5  jnz     short $errRtn_8
0x18000f1c7  xor     edx, edx
0x18000f1c9  cmp     dword ptr [r14], 8
0x18000f1cd  jz      short loc_18000F1E4
0x18000f1cf  mov     this, [rbp+handle]; hMem
0x18000f1d3  call    cs:__imp_GlobalSize
0x18000f1d9  mov     pformatetc, rax; dwSize
0x18000f1dc  test    eax, eax
0x18000f1de  jz      loc_18000F31A
0x18000f1e4  mov     ecx, [r14]
0x18000f1e7  sub     ecx, 1
0x18000f1ea  jz      loc_18000F34F
0x18000f1f0  sub     ecx, 1
0x18000f1f3  jz      loc_18000F345
0x18000f1f9  sub     ecx, 2
0x18000f1fc  jnz     loc_18000F324
0x18000f202  mov     pmedium, [r14+8]; pstm
0x18000f206  mov     this, [rbp+handle]; hGlobalSrc
0x18000f20a  call    ?UtHGLOBALtoStm@@YAJPEAXKPEAUIStream@@@Z; UtHGLOBALtoStm(void *,ulong,IStream *)
0x18000f20f  mov     ebx, eax
0x18000f211  cmp     byte ptr [rdi], 0
0x18000f214  jz      short loc_18000F228
0x18000f216  mov     edx, 1; fFlags
0x18000f21b  mov     this, rsi; this
0x18000f21e  call    ?FreeResources@CClipDataObject@@AEAAXW4FreeResourcesFlags@@@Z; CClipDataObject::FreeResources(FreeResourcesFlags)
0x18000f223  jmp     $logRtn_1
0x18000f228  lea     this, [rbp+clipLock]; this
0x18000f22c  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000f231  test    eax, eax
0x18000f233  jns     short loc_18000F216
0x18000f235  test    ebx, ebx
0x18000f237  mov     eax, 800401D4h
0x18000f23c  cmovz   ebx, eax
0x18000f23f  jmp     short loc_18000F216
0x18000f241  movzx   edx, word ptr [r15]; cf
0x18000f245  call    ?OleIsClipboardFormatAvailable@CClipDataObject@@AEAAHI@Z; CClipDataObject::OleIsClipboardFormatAvailable(uint)
0x18000f24a  neg     eax
0x18000f24c  sbb     ebx, ebx
0x18000f24e  not     ebx
0x18000f250  and     ebx, 8004006Ah
0x18000f256  jmp     $logRtn_1
0x18000f25b  mov     ebx, 80040064h
0x18000f260  lea     rdi, [rsi+45h]
0x18000f264  jmp     short $errRtn_8
0x18000f266  xor     ecx, ecx; dwMilliseconds
0x18000f268  call    cs:__imp_Sleep
0x18000f26e  mov     this, rbx; hWndNewOwner
0x18000f271  call    cs:__imp_OpenClipboard
0x18000f277  test    eax, eax
0x18000f279  jnz     loc_18000F19F
0x18000f27f  mov     ebx, 800401D0h
0x18000f284  jmp     $logRtn_1
0x18000f289  mov     pformatetc, [rbp+pTask.ptr_]
0x18000f28d  test    pformatetc, pformatetc
0x18000f290  jz      short loc_18000F2A6
0x18000f292  mov     this, r14; pmedium
0x18000f295  call    ?MediumContainsObject@@YAHPEAUtagSTGMEDIUM@@@Z; MediumContainsObject(tagSTGMEDIUM *)
0x18000f29a  test    eax, eax
0x18000f29c  jz      short loc_18000F2A6
0x18000f29e  mov     this, pformatetc; this
0x18000f2a1  call    ?RunToTimeLimit@ClipboardDataObjectTask@@UEAAJXZ; ClipboardDataObjectTask::RunToTimeLimit(void)
0x18000f2a6  test    ebx, ebx
0x18000f2a8  jz      $logRtn_1
0x18000f2ae  jmp     loc_18000F0C5
0x18000f2b3  mov     ebx, 8001010Eh
0x18000f2b8  jmp     loc_18000F111
0x18000f2bd  mov     this, [rsi+38h]
0x18000f2c1  test    this, this
0x18000f2c4  jz      loc_18000F0C5
0x18000f2ca  mov     rax, [this]
0x18000f2cd  mov     pmedium, r14
0x18000f2d0  mov     pformatetc, r15
0x18000f2d3  mov     rax, [rax+20h]
0x18000f2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2dc  mov     ebx, eax
0x18000f2de  test    eax, eax
0x18000f2e0  js      short loc_18000F2A6
0x18000f2e2  jmp     short loc_18000F289
0x18000f2e4  movzx   ecx, word ptr [r15]
0x18000f2e8  lea     pformatetc, [rbp+handle]
0x18000f2ec  call    cs:__imp_EdpGetClipboardAccessDeniedData
0x18000f2f2  mov     ebx, eax
0x18000f2f4  test    eax, eax
0x18000f2f6  jz      loc_18000F1C7
0x18000f2fc  jmp     $logRtn_1
0x18000f301  mov     ebx, 80004005h
0x18000f306  jmp     $logRtn_1
0x18000f30b  mov     ecx, 1; EvaluationDisabled
0x18000f310  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18000f315  jmp     loc_18000F1AD
0x18000f31a  mov     ebx, 800401D3h
0x18000f31f  jmp     $errRtn_8
0x18000f324  cmp     ecx, 4
0x18000f327  jz      short loc_18000F333
0x18000f329  mov     ebx, 80040069h
0x18000f32e  jmp     $errRtn_8
0x18000f333  mov     pformatetc, [r14+8]; pStgTgt
0x18000f337  mov     this, [rbp+handle]; hGlobalSrc
0x18000f33b  call    ?UtHGLOBALtoStorage@@YAJPEAXPEAUIStorage@@@Z; UtHGLOBALtoStorage(void *,IStorage *)
0x18000f340  jmp     loc_18000F20F
0x18000f345  mov     ebx, 80004001h
0x18000f34a  jmp     $errRtn_8
0x18000f34f  mov     pmedium, [r14+8]; hGlobalTgt
0x18000f353  mov     this, [rbp+handle]; hGlobalSrc
0x18000f357  call    ?UtHGLOBALtoHGLOBAL@@YAJPEAXK0@Z; UtHGLOBALtoHGLOBAL(void *,ulong,void *)
0x18000f35c  jmp     loc_18000F20F
0x18000f361  mov     [rbp+pTask.ptr_], 0
0x18000f369  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITypeLibRegistrationReader@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITypeLibRegistrationReader,Microsoft::WRL::FtmBase>::Release(void)
0x18000f36e  jmp     loc_18000F111
```

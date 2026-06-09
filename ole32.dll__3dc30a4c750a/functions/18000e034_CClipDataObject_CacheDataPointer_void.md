# CClipDataObject::CacheDataPointer(void)

- ea: `0x18000e034`
- end: `0x18000e3ac`
- name: `?CacheDataPointer@CClipDataObject@@QEAA?AV?$ComPtr@VClipboardDataObjectTask@@@WRL@Microsoft@@XZ`
- size: `888`
- prototype: `Microsoft::WRL::ComPtr<ClipboardDataObjectTask> *__fastcall(CClipDataObject *this, Microsoft::WRL::ComPtr<ClipboardDataObjectTask> *result)`
- caller_count: `7`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d470`
- `0x18000dec0`
- `0x18000f070`
- `0x18000f3c0`
- `0x18000fbb0`
- `0x18001c0a8`
- `0x18003c480`

## callees

- `0x1800051e0`
- `0x18000d38c`
- `0x18000e034`
- `0x18000ebc8`
- `0x18000eed4`
- `0x18000fc40`
- `0x180031ff0`
- `0x180036d78`
- `0x1800387c8`
- `0x1800405d4`
- `0x180047080`
- `0x1800473d0`
- `0x180090128`
- `0x1800902b0`
- `0x180091d44`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!Sleep` at `0x18000e299`
- `KERNELBASE!Sleep` at `0x18000e299`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e391`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000e10c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000e10c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000e0fb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000e0fb`
- `USER32!GetPropW` at `0x18000e2e0`
- `USER32!GetPropW` at `0x18000e2e0`
- `USER32!IsClipboardFormatAvailable` at `0x18000e099`
- `USER32!IsClipboardFormatAvailable` at `0x18000e099`
- `USER32!GetClipboardData` at `0x18000e0ea`
- `USER32!GetClipboardData` at `0x18000e0ea`
- `USER32!OpenClipboard` at `0x18000e0bd`
- `USER32!OpenClipboard` at `0x18000e2a2`
- `USER32!OpenClipboard` at `0x18000e0bd`
- `USER32!OpenClipboard` at `0x18000e2a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e274`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e274`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000e0cb`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000e0cb`

## pseudocode

```c
Microsoft::WRL::ComPtr<ClipboardDataObjectTask> *__fastcall CClipDataObject::CacheDataPointer(
        CClipDataObject *this,
        Microsoft::WRL::ComPtr<ClipboardDataObjectTask> *result)
{
  void **p_m_pDataObject; // r12
  HWND PrivateClipboardWindow; // rax
  HWND v7; // rbx
  HRESULT PackagedPLMClipboardOwnerInternal; // ebx
  HWND__ *v9; // rsi
  HANDLE ClipboardData; // rax
  void *v11; // r15
  HWND__ **v12; // rax
  const _GUID *v13; // rdx
  ClipboardDataObjectTask *ptr; // rcx
  wchar_t *v15; // r15
  const _GUID *v16; // rdx
  wchar_t *v17; // r15
  Windows::Internal::Details::Git *v18; // rcx
  unsigned int v19; // r8d
  HRESULT TokenFromHwnd; // eax
  IDataObject **ppDataObj; // [rsp+20h] [rbp-38h]
  IDataObject **ppDataObja; // [rsp+20h] [rbp-38h]
  Windows::Internal::GitPtr GITSourceInnerDataObject; // [rsp+30h] [rbp-28h] BYREF
  CClipDataObject::CacheDataPointer::__l54::<lambda_27a1cab33e266522ee12881589f1a48d> v24; // [rsp+40h] [rbp-18h] BYREF
  void *hToken; // [rsp+A0h] [rbp+48h] BYREF
  IDataObject *pMTADataObj; // [rsp+A8h] [rbp+50h] BYREF
  IDataObject *pSourceDataObject; // [rsp+B0h] [rbp+58h] BYREF
  const wchar_t *pszPackageName; // [rsp+B8h] [rbp+60h] BYREF

  result->ptr_ = 0;
  if ( this->m_fIsEdpAccessDenied )
    goto LABEL_4;
  p_m_pDataObject = (void **)&this->m_pDataObject;
  if ( this->m_pDataObject )
  {
    if ( !this->m_dwPLMSourcePid )
      goto LABEL_4;
    PackagedPLMClipboardOwnerInternal = 0;
    Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,unsigned long &>(
      (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask> >)result,
      &this->m_dwPLMSourcePid);
    goto $logRtn_0;
  }
  if ( this->m_fTriedToGetDataObject == 1 || !IsClipboardFormatAvailable(g_cfDataObject) )
    goto LABEL_4;
  LOBYTE(hToken) = 0;
  PrivateClipboardWindow = GetPrivateClipboardWindow(CLIP_CREATEIFNOTTHERE);
  v7 = PrivateClipboardWindow;
  if ( !PrivateClipboardWindow )
  {
    PackagedPLMClipboardOwnerInternal = -2147467259;
    goto LABEL_38;
  }
  if ( !OpenClipboard(PrivateClipboardWindow) )
  {
    Sleep(0);
    if ( !OpenClipboard(v7) )
    {
      PackagedPLMClipboardOwnerInternal = -2147221040;
LABEL_38:
      OleClipboardLock::Release((OleClipboardLock *)&hToken);
      goto $logRtn_0;
    }
  }
  if ( (unsigned int)EdpGetIsManaged() )
    EdpInlSetCurrentThreadPolicyEvaluation(1);
  PackagedPLMClipboardOwnerInternal = 0;
  LOBYTE(hToken) = 1;
  v9 = 0;
  ClipboardData = GetClipboardData(g_cfDataObject);
  v11 = ClipboardData;
  if ( ClipboardData )
  {
    v12 = (HWND__ **)GlobalLock(ClipboardData);
    if ( v12 )
    {
      v9 = *v12;
      GlobalUnlock(v11);
    }
  }
  OleClipboardLock::Release((OleClipboardLock *)&hToken);
  if ( v9 )
  {
    if ( g_fIsClipboardBrokerHost )
    {
      pszPackageName = 0;
      LODWORD(pMTADataObj) = 0;
      LOBYTE(hToken) = 0;
      PackagedPLMClipboardOwnerInternal = GetPackagedPLMClipboardOwnerInternal(
                                            v9,
                                            (wchar_t **)&pszPackageName,
                                            (unsigned int *)&pMTADataObj,
                                            (bool *)&hToken);
      if ( PackagedPLMClipboardOwnerInternal >= 0 )
      {
        v15 = (wchar_t *)pszPackageName;
        if ( pszPackageName )
        {
          if ( (_BYTE)hToken )
          {
            this->m_dwPLMSourcePid = (unsigned int)pMTADataObj;
            Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,unsigned long &>(
              (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask> >)result,
              (unsigned int *)&pMTADataObj);
            CoTaskMemFree(v15);
            pSourceDataObject = 0;
LABEL_27:
            PackagedPLMClipboardOwnerInternal = GetInterfaceFromWindowProp(
                                                  v9,
                                                  v13,
                                                  result->ptr_ != 0,
                                                  &pSourceDataObject,
                                                  (wchar_t *)ppDataObj);
            if ( PackagedPLMClipboardOwnerInternal == -2147172351 )
            {
              pszPackageName = 0;
              LODWORD(pMTADataObj) = 0;
              LOBYTE(hToken) = 0;
              PackagedPLMClipboardOwnerInternal = GetPackagedPLMClipboardOwnerInternal(
                                                    v9,
                                                    (wchar_t **)&pszPackageName,
                                                    (unsigned int *)&pMTADataObj,
                                                    (bool *)&hToken);
              if ( PackagedPLMClipboardOwnerInternal >= 0 )
              {
                v17 = (wchar_t *)pszPackageName;
                if ( !pszPackageName
                  || !(_BYTE)hToken
                  || (this->m_dwPLMSourcePid = (unsigned int)pMTADataObj,
                      PackagedPLMClipboardOwnerInternal = Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,unsigned long &>(
                                                            (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask> >)result,
                                                            (unsigned int *)&pMTADataObj),
                      CoTaskMemFree(v17),
                      PackagedPLMClipboardOwnerInternal >= 0) )
                {
                  PackagedPLMClipboardOwnerInternal = GetInterfaceFromWindowProp(
                                                        v9,
                                                        v16,
                                                        1,
                                                        &pSourceDataObject,
                                                        (wchar_t *)ppDataObja);
                }
              }
            }
            if ( pSourceDataObject )
            {
              if ( this->m_fIsClientAppContainer )
              {
                pMTADataObj = (IDataObject *)GetPropW(v9, L"ClipboardDataObjectInterfaceMTA");
                if ( pMTADataObj )
                {
                  GITSourceInnerDataObject._cookie = 0;
                  GITSourceInnerDataObject._hrInitGit = Windows::Internal::Details::Git::Acquire(v18);
                  GITSourceInnerDataObject.__vftable = (Windows::Internal::GitPtr_vtbl *)Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
                  v24.pMTADataObj = &pMTADataObj;
                  v24.GITSourceInnerDataObject = &GITSourceInnerDataObject;
                  PackagedPLMClipboardOwnerInternal = RunSyncOnMTAThread__lambda_27a1cab33e266522ee12881589f1a48d_(&v24);
                  if ( PackagedPLMClipboardOwnerInternal >= 0 )
                    PackagedPLMClipboardOwnerInternal = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(
                                                          &GITSourceInnerDataObject,
                                                          &GUID_0000010e_0000_0000_c000_000000000046,
                                                          p_m_pDataObject);
                  Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(&GITSourceInnerDataObject);
                }
                else
                {
                  hToken = 0;
                  TokenFromHwnd = GetTokenFromHwnd(v9, &hToken, v19);
                  PackagedPLMClipboardOwnerInternal = 0;
                  if ( TokenFromHwnd != -2147024891 )
                    PackagedPLMClipboardOwnerInternal = TokenFromHwnd;
                  if ( PackagedPLMClipboardOwnerInternal >= 0 )
                    PackagedPLMClipboardOwnerInternal = CBrokeredClipDataObject::Create(
                                                          pSourceDataObject,
                                                          0,
                                                          0,
                                                          &hToken,
                                                          (IDataObject **)p_m_pDataObject);
                  if ( hToken )
                    CloseHandle(hToken);
                }
                ((void (__fastcall *)(IDataObject *))pSourceDataObject->lpVtbl->Release)(pSourceDataObject);
              }
              else
              {
                *p_m_pDataObject = pSourceDataObject;
                pSourceDataObject = 0;
              }
            }
            goto LABEL_16;
          }
        }
      }
    }
  }
  pSourceDataObject = 0;
  if ( PackagedPLMClipboardOwnerInternal >= 0 && v9 )
    goto LABEL_27;
LABEL_16:
  OleClipboardTracing::CClipDataObject_CacheDataPointerEtw(
    PackagedPLMClipboardOwnerInternal,
    (IDataObject *)*p_m_pDataObject,
    result->ptr_);
$logRtn_0:
  if ( PackagedPLMClipboardOwnerInternal < 0 )
  {
    ptr = result->ptr_;
    if ( result->ptr_ )
    {
      result->ptr_ = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITypeLibRegistrationReader,Microsoft::WRL::FtmBase>::Release((Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITypeLibRegistrationReader,Microsoft::WRL::FtmBase> *)ptr);
    }
  }
LABEL_4:
  this->m_fTriedToGetDataObject = result->ptr_ == 0;
  return result;
}

```

## disassembly

```asm
0x18000e034  push    rbp
0x18000e036  push    rbx
0x18000e037  push    rsi
0x18000e038  push    rdi
0x18000e039  push    r12
0x18000e03b  push    r13
0x18000e03d  push    r14
0x18000e03f  push    r15
0x18000e041  mov     rbp, rsp
0x18000e044  sub     rsp, 58h
0x18000e048  xor     r13d, r13d
0x18000e04b  mov     rdi, rdx
0x18000e04e  mov     [rdx], r13
0x18000e051  mov     r14, this
0x18000e054  cmp     [this+45h], r13b
0x18000e058  jnz     short loc_18000E071
0x18000e05a  lea     r12, [this+38h]
0x18000e05e  cmp     [r12], r13
0x18000e062  jnz     loc_18000E160
0x18000e068  lea     esi, [r13+1]
0x18000e06c  cmp     [this+40h], esi
0x18000e06f  jnz     short loc_18000E092
0x18000e071  cmp     [rdi], r13
0x18000e074  mov     eax, r13d
0x18000e077  setz    al
0x18000e07a  mov     [r14+40h], eax
0x18000e07e  mov     rax, rdi
0x18000e081  add     rsp, 58h
0x18000e085  pop     r15
0x18000e087  pop     r14
0x18000e089  pop     r13
0x18000e08b  pop     r12
0x18000e08d  pop     rdi
0x18000e08e  pop     rsi
0x18000e08f  pop     rbx
0x18000e090  pop     rbp
0x18000e091  retn
0x18000e092  movzx   ecx, cs:?g_cfDataObject@@3GA; format
0x18000e099  call    cs:__imp_IsClipboardFormatAvailable
0x18000e09f  test    eax, eax
0x18000e0a1  jz      short loc_18000E071
0x18000e0a3  mov     ecx, esi; fFlags
0x18000e0a5  mov     byte ptr [rbp+hToken], r13b
0x18000e0a9  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x18000e0ae  mov     rbx, rax
0x18000e0b1  test    rax, rax
0x18000e0b4  jz      loc_18000E2C3
0x18000e0ba  mov     this, rax; hWndNewOwner
0x18000e0bd  call    cs:__imp_OpenClipboard
0x18000e0c3  test    eax, eax
0x18000e0c5  jz      loc_18000E297
0x18000e0cb  call    cs:__imp_EdpGetIsManaged
0x18000e0d1  test    eax, eax
0x18000e0d3  jnz     loc_18000E2CA
0x18000e0d9  movzx   ecx, cs:?g_cfDataObject@@3GA; uFormat
0x18000e0e0  mov     ebx, r13d
0x18000e0e3  mov     byte ptr [rbp+hToken], sil
0x18000e0e7  mov     rsi, r13
0x18000e0ea  call    cs:__imp_GetClipboardData
0x18000e0f0  mov     r15, rax
0x18000e0f3  test    rax, rax
0x18000e0f6  jz      short loc_18000E112
0x18000e0f8  mov     this, rax; hMem
0x18000e0fb  call    cs:__imp_GlobalLock
0x18000e101  test    rax, rax
0x18000e104  jz      short loc_18000E112
0x18000e106  mov     rsi, [rax]
0x18000e109  mov     this, r15; hMem
0x18000e10c  call    cs:__imp_GlobalUnlock
0x18000e112  lea     this, [rbp+hToken]; this
0x18000e116  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000e11b  test    rsi, rsi
0x18000e11e  jnz     short loc_18000E17A
0x18000e120  mov     [rbp+pSourceDataObject], r13
0x18000e124  test    ebx, ebx
0x18000e126  js      short loc_18000E131
0x18000e128  test    rsi, rsi
0x18000e12b  jnz     loc_18000E1E4
0x18000e131  mov     r8, [rdi]; pTask
0x18000e134  mov     ecx, ebx; hr
0x18000e136  mov     rdx, [r12]; pDataObject
0x18000e13a  call    ?CClipDataObject_CacheDataPointerEtw@OleClipboardTracing@@SAXJPEAUIDataObject@@PEAVClipboardDataObjectTask@@@Z; OleClipboardTracing::CClipDataObject_CacheDataPointerEtw(long,IDataObject *,ClipboardDataObjectTask *)
0x18000e13f  test    ebx, ebx
0x18000e141  jns     loc_18000E071
0x18000e147  mov     this, [rdi]; this
0x18000e14a  test    this, this
0x18000e14d  jz      loc_18000E071
0x18000e153  mov     [rdi], r13
0x18000e156  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITypeLibRegistrationReader@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITypeLibRegistrationReader,Microsoft::WRL::FtmBase>::Release(void)
0x18000e15b  jmp     loc_18000E071
0x18000e160  lea     rdx, [this+48h]; <args_0>
0x18000e164  cmp     [rdx], r13d
0x18000e167  jz      loc_18000E071
0x18000e16d  mov     this, rdi; ppvObject
0x18000e170  mov     ebx, r13d
0x18000e173  call    ??$MakeAndInitialize@VClipboardDataObjectTask@@V1@AEAK@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VClipboardDataObjectTask@@@WRL@Microsoft@@@012@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,ulong &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask>>,ulong &)
0x18000e178  jmp     short $logRtn_0
0x18000e17a  cmp     cs:?g_fIsClipboardBrokerHost@@3_NA, r13b; bool g_fIsClipboardBrokerHost
0x18000e181  jz      short loc_18000E120
0x18000e183  lea     r9, [rbp+hToken]; pIsPLMManaged
0x18000e187  mov     [rbp+pszPackageName], r13
0x18000e18b  lea     r8, [rbp+pMTADataObj]; ppid
0x18000e18f  mov     dword ptr [rbp+pMTADataObj], r13d
0x18000e193  lea     rdx, [rbp+pszPackageName]; ppszPackageFullName
0x18000e197  mov     byte ptr [rbp+hToken], r13b
0x18000e19b  mov     this, rsi; hWndClipboardOwner
0x18000e19e  call    ?GetPackagedPLMClipboardOwnerInternal@@YAJPEAUHWND__@@PEAPEBGPEAKPEA_N@Z; GetPackagedPLMClipboardOwnerInternal(HWND__ *,ushort const * *,ulong *,bool *)
0x18000e1a3  mov     ebx, eax
0x18000e1a5  test    eax, eax
0x18000e1a7  js      loc_18000E120
0x18000e1ad  mov     r15, [rbp+pszPackageName]
0x18000e1b1  test    r15, r15
0x18000e1b4  jz      loc_18000E120
0x18000e1ba  cmp     byte ptr [rbp+hToken], r13b
0x18000e1be  jz      loc_18000E120
0x18000e1c4  mov     eax, dword ptr [rbp+pMTADataObj]
0x18000e1c7  lea     rdx, [rbp+pMTADataObj]; <args_0>
0x18000e1cb  mov     this, rdi; ppvObject
0x18000e1ce  mov     [r14+48h], eax
0x18000e1d2  call    ??$MakeAndInitialize@VClipboardDataObjectTask@@V1@AEAK@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VClipboardDataObjectTask@@@WRL@Microsoft@@@012@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,ulong &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask>>,ulong &)
0x18000e1d7  mov     this, r15; pv
0x18000e1da  call    cs:__imp_CoTaskMemFree
0x18000e1e0  mov     [rbp+pSourceDataObject], r13
0x18000e1e4  cmp     [rdi], r13
0x18000e1e7  lea     r9, [rbp+pSourceDataObject]; hWnd
0x18000e1eb  mov     r8d, r13d
0x18000e1ee  mov     this, rsi; hWnd
0x18000e1f1  setnz   r8b; ppunk
0x18000e1f5  call    ?GetInterfaceFromWindowProp@@YAJPEAUHWND__@@AEBU_GUID@@HPEAPEAUIUnknown@@PEAG@Z; GetInterfaceFromWindowProp(HWND__ *,_GUID const &,int,IUnknown * *,ushort *)
0x18000e1fa  mov     ebx, eax
0x18000e1fc  cmp     eax, 8004C001h
0x18000e201  jz      short loc_18000E227
0x18000e203  mov     rax, [rbp+pSourceDataObject]
0x18000e207  test    rax, rax
0x18000e20a  jz      loc_18000E131
0x18000e210  cmp     [r14+44h], r13b
0x18000e214  jnz     loc_18000E2D6
0x18000e21a  mov     [r12], rax
0x18000e21e  mov     [rbp+pSourceDataObject], r13
0x18000e222  jmp     loc_18000E131
0x18000e227  lea     r9, [rbp+hToken]; pIsPLMManaged
0x18000e22b  mov     [rbp+pszPackageName], r13
0x18000e22f  lea     r8, [rbp+pMTADataObj]; ppid
0x18000e233  mov     dword ptr [rbp+pMTADataObj], r13d
0x18000e237  lea     rdx, [rbp+pszPackageName]; ppszPackageFullName
0x18000e23b  mov     byte ptr [rbp+hToken], r13b
0x18000e23f  mov     this, rsi; hWndClipboardOwner
0x18000e242  call    ?GetPackagedPLMClipboardOwnerInternal@@YAJPEAUHWND__@@PEAPEBGPEAKPEA_N@Z; GetPackagedPLMClipboardOwnerInternal(HWND__ *,ushort const * *,ulong *,bool *)
0x18000e247  mov     ebx, eax
0x18000e249  test    eax, eax
0x18000e24b  js      short loc_18000E203
0x18000e24d  mov     r15, [rbp+pszPackageName]
0x18000e251  test    r15, r15
0x18000e254  jz      short loc_18000E27E
0x18000e256  cmp     byte ptr [rbp+hToken], r13b
0x18000e25a  jz      short loc_18000E27E
0x18000e25c  mov     eax, dword ptr [rbp+pMTADataObj]
0x18000e25f  lea     rdx, [rbp+pMTADataObj]; <args_0>
0x18000e263  mov     this, rdi; ppvObject
0x18000e266  mov     [r14+48h], eax
0x18000e26a  call    ??$MakeAndInitialize@VClipboardDataObjectTask@@V1@AEAK@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VClipboardDataObjectTask@@@WRL@Microsoft@@@012@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,ulong &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask>>,ulong &)
0x18000e26f  mov     this, r15; pv
0x18000e272  mov     ebx, eax
0x18000e274  call    cs:__imp_CoTaskMemFree
0x18000e27a  test    ebx, ebx
0x18000e27c  js      short loc_18000E203
0x18000e27e  lea     r9, [rbp+pSourceDataObject]; hWnd
0x18000e282  mov     r8d, 1; ppunk
0x18000e288  mov     this, rsi; hWnd
0x18000e28b  call    ?GetInterfaceFromWindowProp@@YAJPEAUHWND__@@AEBU_GUID@@HPEAPEAUIUnknown@@PEAG@Z; GetInterfaceFromWindowProp(HWND__ *,_GUID const &,int,IUnknown * *,ushort *)
0x18000e290  mov     ebx, eax
0x18000e292  jmp     loc_18000E203
0x18000e297  xor     ecx, ecx; dwMilliseconds
0x18000e299  call    cs:__imp_Sleep
0x18000e29f  mov     this, rbx; hWndNewOwner
0x18000e2a2  call    cs:__imp_OpenClipboard
0x18000e2a8  test    eax, eax
0x18000e2aa  jnz     loc_18000E0CB
0x18000e2b0  mov     ebx, 800401D0h
0x18000e2b5  lea     this, [rbp+hToken]; this
0x18000e2b9  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000e2be  jmp     $logRtn_0
0x18000e2c3  mov     ebx, 80004005h
0x18000e2c8  jmp     short loc_18000E2B5
0x18000e2ca  mov     ecx, esi; EvaluationDisabled
0x18000e2cc  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18000e2d1  jmp     loc_18000E0D9
0x18000e2d6  lea     rdx, aClipboarddatao; "ClipboardDataObjectInterfaceMTA"
0x18000e2dd  mov     this, rsi; hWnd
0x18000e2e0  call    cs:__imp_GetPropW
0x18000e2e6  mov     [rbp+pMTADataObj], rax
0x18000e2ea  test    rax, rax
0x18000e2ed  jz      short loc_18000E350
0x18000e2ef  lea     rax, ??_7?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable'
0x18000e2f6  mov     [rbp+GITSourceInnerDataObject._cookie], r13d
0x18000e2fa  mov     [rbp+GITSourceInnerDataObject.__vftable], rax
0x18000e2fe  call    ?Acquire@Git@Details@Internal@Windows@@QEAAJXZ; Windows::Internal::Details::Git::Acquire(void)
0x18000e303  mov     [rbp+GITSourceInnerDataObject._hrInitGit], eax
0x18000e306  lea     this, [rbp+var_18]
0x18000e30a  lea     rax, ??_7?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable'
0x18000e311  mov     [rbp+GITSourceInnerDataObject.__vftable], rax
0x18000e315  lea     rax, [rbp+pMTADataObj]
0x18000e319  mov     [rbp+var_18], rax
0x18000e31d  lea     rax, [rbp+GITSourceInnerDataObject]
0x18000e321  mov     [rbp+var_10], rax
0x18000e325  call    RunSyncOnMTAThread__lambda_27a1cab33e266522ee12881589f1a48d___; RunSyncOnMTAThread__lambda_27a1cab33e266522ee12881589f1a48d_
0x18000e32a  mov     ebx, eax
0x18000e32c  test    eax, eax
0x18000e32e  js      short loc_18000E345
0x18000e330  mov     r8, r12; ptr
0x18000e333  lea     rdx, _GUID_0000010e_0000_0000_c000_000000000046; riid
0x18000e33a  lea     this, [rbp+GITSourceInnerDataObject]; this
0x18000e33e  call    ?Localize@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(_GUID const &,void * *)
0x18000e343  mov     ebx, eax
0x18000e345  lea     this, [rbp+GITSourceInnerDataObject]; this
0x18000e349  call    ??1?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(void)
0x18000e34e  jmp     short loc_18000E397
0x18000e350  lea     rdx, [rbp+hToken]; phToken
0x18000e354  mov     [rbp+hToken], r13
0x18000e358  mov     this, rsi; hWnd
0x18000e35b  call    ?GetTokenFromHwnd@@YAJPEAUHWND__@@PEAPEAXK@Z; GetTokenFromHwnd(HWND__ *,void * *,ulong)
0x18000e360  cmp     eax, 80070005h
0x18000e365  mov     ebx, r13d
0x18000e368  cmovnz  ebx, eax
0x18000e36b  test    ebx, ebx
0x18000e36d  js      short loc_18000E388
0x18000e36f  mov     this, [rbp+pSourceDataObject]; pInnerDataObject
0x18000e373  lea     r9, [rbp+hToken]; phObjectOwnerToken
0x18000e377  xor     r8d, r8d; fOwnerIsPlmManaged
0x18000e37a  mov     [rsp+58h+ppDataObj], r12; ppDataObj
0x18000e37f  xor     edx, edx; dwSourceProcessId
0x18000e381  call    ?Create@CBrokeredClipDataObject@@SAJPEAUIDataObject@@K_NPEAPEAXPEAPEAU2@@Z; CBrokeredClipDataObject::Create(IDataObject *,ulong,bool,void * *,IDataObject * *)
0x18000e386  mov     ebx, eax
0x18000e388  mov     this, [rbp+hToken]; hObject
0x18000e38c  test    this, this
0x18000e38f  jz      short loc_18000E397
0x18000e391  call    cs:__imp_CloseHandle
0x18000e397  mov     this, [rbp+pSourceDataObject]
0x18000e39b  mov     rax, [this]
0x18000e39e  mov     rax, [rax+10h]
0x18000e3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3a7  jmp     loc_18000E131
```

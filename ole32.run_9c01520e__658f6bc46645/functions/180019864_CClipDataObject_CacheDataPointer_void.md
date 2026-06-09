# CClipDataObject::CacheDataPointer(void)

- ea: `0x180019864`
- end: `0x180019b82`
- name: `?CacheDataPointer@CClipDataObject@@QEAA?AV?$ComPtr@VClipboardDataObjectTask@@@WRL@Microsoft@@XZ`
- size: `798`
- prototype: `Microsoft::WRL::ComPtr<ClipboardDataObjectTask> *__fastcall(CClipDataObject *this, Microsoft::WRL::ComPtr<ClipboardDataObjectTask> *result)`
- caller_count: `7`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017800`
- `0x180018680`
- `0x180018950`
- `0x180018c70`
- `0x1800196d0`
- `0x180022cfc`
- `0x1800403c0`

## callees

- `0x18000d6f0`
- `0x180019864`
- `0x18001ac98`
- `0x18001b084`
- `0x18001b290`
- `0x18002e9dc`
- `0x180032b5c`
- `0x18003aac4`
- `0x18003c348`
- `0x1800455d4`
- `0x18008c16c`
- `0x18008c404`
- `0x18008c434`
- `0x18008f834`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b61`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180019925`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180019925`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001990e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001990e`
- `USER32!GetPropW` at `0x180019ab7`
- `USER32!GetPropW` at `0x180019ab7`
- `USER32!IsClipboardFormatAvailable` at `0x1800198c7`
- `USER32!IsClipboardFormatAvailable` at `0x1800198c7`
- `USER32!GetClipboardData` at `0x1800198f7`
- `USER32!GetClipboardData` at `0x1800198f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800199db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800199db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a76`

## pseudocode

```c
Microsoft::WRL::ComPtr<ClipboardDataObjectTask> *__fastcall CClipDataObject::CacheDataPointer(
        CClipDataObject *this,
        Microsoft::WRL::ComPtr<ClipboardDataObjectTask> *result)
{
  int v2; // ebx
  HWND__ *v5; // r14
  HRESULT PackagedPLMClipboardOwnerInternal; // edi
  IDataObject **p_m_pDataObject; // r13
  Microsoft::WRL::ComPtr<ClipboardDataObjectTask> *v8; // rax
  HWND__ *v9; // rdx
  HANDLE ClipboardData; // rax
  void *v11; // r12
  HWND__ **v12; // rax
  const _GUID *v13; // rdx
  const _GUID *v14; // rdx
  Windows::Internal::Details::Git *v15; // rcx
  unsigned int v16; // r8d
  HRESULT TokenFromHwnd; // eax
  IDataObject **ppDataObj; // [rsp+20h] [rbp-38h]
  IDataObject **ppDataObja; // [rsp+20h] [rbp-38h]
  Windows::Internal::GitPtr GITSourceInnerDataObject; // [rsp+30h] [rbp-28h] BYREF
  CClipDataObject::CacheDataPointer::__l54::<lambda_27a1cab33e266522ee12881589f1a48d> v21; // [rsp+40h] [rbp-18h] BYREF
  void *hToken; // [rsp+A0h] [rbp+48h] BYREF
  IDataObject *pMTADataObj; // [rsp+A8h] [rbp+50h] BYREF
  IDataObject *pSourceDataObject; // [rsp+B0h] [rbp+58h] BYREF
  const wchar_t *pszPackageName; // [rsp+B8h] [rbp+60h] BYREF

  v2 = 0;
  result->ptr_ = 0;
  v5 = 0;
  PackagedPLMClipboardOwnerInternal = 0;
  if ( this->m_fIsEdpAccessDenied )
    goto LABEL_4;
  p_m_pDataObject = &this->m_pDataObject;
  if ( this->m_pDataObject )
  {
    if ( !this->m_dwPLMSourcePid )
      goto LABEL_4;
    Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,unsigned long &>(
      (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask> >)result,
      &this->m_dwPLMSourcePid);
    goto $logRtn_1;
  }
  if ( this->m_fTriedToGetDataObject == 1 || !IsClipboardFormatAvailable(g_cfDataObject) )
    goto LABEL_4;
  LOBYTE(hToken) = 0;
  PackagedPLMClipboardOwnerInternal = OleClipboardLock::Lock((OleClipboardLock *)&hToken, v9, 0);
  if ( !PackagedPLMClipboardOwnerInternal )
  {
    ClipboardData = GetClipboardData(g_cfDataObject);
    v11 = ClipboardData;
    if ( ClipboardData )
    {
      v12 = (HWND__ **)GlobalLock(ClipboardData);
      if ( v12 )
      {
        v5 = *v12;
        GlobalUnlock(v11);
      }
    }
    OleClipboardLock::Release((OleClipboardLock *)&hToken);
    if ( v5
      && g_fIsClipboardBrokerHost
      && (pszPackageName = 0,
          LODWORD(pMTADataObj) = 0,
          LOBYTE(hToken) = 0,
          PackagedPLMClipboardOwnerInternal = GetPackagedPLMClipboardOwnerInternal(
                                                v5,
                                                (wchar_t **)&pszPackageName,
                                                (unsigned int *)&pMTADataObj,
                                                (bool *)&hToken),
          PackagedPLMClipboardOwnerInternal >= 0)
      && pszPackageName
      && (_BYTE)hToken )
    {
      this->m_dwPLMSourcePid = (unsigned int)pMTADataObj;
      Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,unsigned long &>(
        (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask> >)result,
        (unsigned int *)&pMTADataObj);
      CoTaskMemFree((LPVOID)pszPackageName);
      pSourceDataObject = 0;
    }
    else
    {
      pSourceDataObject = 0;
      if ( PackagedPLMClipboardOwnerInternal < 0 || !v5 )
      {
LABEL_13:
        OleClipboardTracing::CClipDataObject_CacheDataPointerEtw(
          PackagedPLMClipboardOwnerInternal,
          *p_m_pDataObject,
          result->ptr_);
        goto $logRtn_1;
      }
    }
    PackagedPLMClipboardOwnerInternal = GetInterfaceFromWindowProp(
                                          v5,
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
                                            v5,
                                            (wchar_t **)&pszPackageName,
                                            (unsigned int *)&pMTADataObj,
                                            (bool *)&hToken);
      if ( PackagedPLMClipboardOwnerInternal >= 0 )
      {
        if ( !pszPackageName
          || !(_BYTE)hToken
          || (this->m_dwPLMSourcePid = (unsigned int)pMTADataObj,
              PackagedPLMClipboardOwnerInternal = Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,unsigned long &>(
                                                    (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask> >)result,
                                                    (unsigned int *)&pMTADataObj),
              CoTaskMemFree((LPVOID)pszPackageName),
              PackagedPLMClipboardOwnerInternal >= 0) )
        {
          PackagedPLMClipboardOwnerInternal = GetInterfaceFromWindowProp(
                                                v5,
                                                v14,
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
        pMTADataObj = (IDataObject *)GetPropW(v5, L"ClipboardDataObjectInterfaceMTA");
        if ( pMTADataObj )
        {
          GITSourceInnerDataObject._cookie = 0;
          GITSourceInnerDataObject._hrInitGit = Windows::Internal::Details::Git::Acquire(v15);
          GITSourceInnerDataObject.__vftable = (Windows::Internal::GitPtr_vtbl *)Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
          v21.pMTADataObj = &pMTADataObj;
          v21.GITSourceInnerDataObject = &GITSourceInnerDataObject;
          PackagedPLMClipboardOwnerInternal = RunSyncOnMTAThread__lambda_27a1cab33e266522ee12881589f1a48d_(&v21);
          if ( PackagedPLMClipboardOwnerInternal >= 0 )
            PackagedPLMClipboardOwnerInternal = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(
                                                  &GITSourceInnerDataObject,
                                                  &GUID_0000010e_0000_0000_c000_000000000046,
                                                  (void **)p_m_pDataObject);
          Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(&GITSourceInnerDataObject);
        }
        else
        {
          hToken = 0;
          TokenFromHwnd = GetTokenFromHwnd(v5, &hToken, v16);
          PackagedPLMClipboardOwnerInternal = 0;
          if ( TokenFromHwnd != -2147024891 )
            PackagedPLMClipboardOwnerInternal = TokenFromHwnd;
          if ( PackagedPLMClipboardOwnerInternal >= 0 )
            PackagedPLMClipboardOwnerInternal = CBrokeredClipDataObject::Create(
                                                  pSourceDataObject,
                                                  0,
                                                  0,
                                                  &hToken,
                                                  p_m_pDataObject);
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
    goto LABEL_13;
  }
  OleClipboardLock::Release((OleClipboardLock *)&hToken);
$logRtn_1:
  if ( PackagedPLMClipboardOwnerInternal < 0 )
    Microsoft::WRL::ComPtr<ClipboardDataObjectTask>::InternalRelease(result);
LABEL_4:
  v8 = result;
  LOBYTE(v2) = result->ptr_ == 0;
  this->m_fTriedToGetDataObject = v2;
  return v8;
}

```

## disassembly

```asm
0x180019864  push    rbp
0x180019866  push    rbx
0x180019867  push    rsi
0x180019868  push    rdi
0x180019869  push    r12
0x18001986b  push    r13
0x18001986d  push    r14
0x18001986f  push    r15
0x180019871  mov     rbp, rsp
0x180019874  sub     rsp, 58h
0x180019878  xor     ebx, ebx
0x18001987a  mov     rsi, rdx
0x18001987d  mov     [rdx], rbx
0x180019880  mov     r15, this
0x180019883  mov     r14d, ebx
0x180019886  mov     edi, ebx
0x180019888  cmp     [this+45h], bl
0x18001988b  jnz     short loc_1800198A1
0x18001988d  lea     r13, [this+38h]
0x180019891  cmp     [r13+0], rbx
0x180019895  jnz     loc_180019973
0x18001989b  cmp     dword ptr [this+40h], 1
0x18001989f  jnz     short loc_1800198C0
0x1800198a1  cmp     [rsi], rbx
0x1800198a4  mov     rax, rsi
0x1800198a7  setz    bl
0x1800198aa  mov     [r15+40h], ebx
0x1800198ae  add     rsp, 58h
0x1800198b2  pop     r15
0x1800198b4  pop     r14
0x1800198b6  pop     r13
0x1800198b8  pop     r12
0x1800198ba  pop     rdi
0x1800198bb  pop     rsi
0x1800198bc  pop     rbx
0x1800198bd  pop     rbp
0x1800198be  retn
0x1800198c0  movzx   ecx, cs:?g_cfDataObject@@3GA; format
0x1800198c7  call    cs:__imp_IsClipboardFormatAvailable
0x1800198ce  nop     dword ptr [rax+rax+00h]
0x1800198d3  test    eax, eax
0x1800198d5  jz      short loc_1800198A1
0x1800198d7  xor     r8d, r8d; hClipWnd
0x1800198da  mov     byte ptr [rbp+hToken], bl
0x1800198dd  lea     this, [rbp+hToken]; this
0x1800198e1  call    ?Lock@OleClipboardLock@@QEAAJPEAUHWND__@@PEAPEAU2@@Z; OleClipboardLock::Lock(HWND__ *,HWND__ * *)
0x1800198e6  mov     edi, eax
0x1800198e8  test    eax, eax
0x1800198ea  jnz     loc_180019A9F
0x1800198f0  movzx   ecx, cs:?g_cfDataObject@@3GA; uFormat
0x1800198f7  call    cs:__imp_GetClipboardData
0x1800198fe  nop     dword ptr [rax+rax+00h]
0x180019903  mov     r12, rax
0x180019906  test    rax, rax
0x180019909  jz      short loc_180019931
0x18001990b  mov     this, rax; hMem
0x18001990e  call    cs:__imp_GlobalLock
0x180019915  nop     dword ptr [rax+rax+00h]
0x18001991a  test    rax, rax
0x18001991d  jz      short loc_180019931
0x18001991f  mov     r14, [rax]
0x180019922  mov     this, r12; hMem
0x180019925  call    cs:__imp_GlobalUnlock
0x18001992c  nop     dword ptr [rax+rax+00h]
0x180019931  lea     this, [rbp+hToken]; this
0x180019935  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18001993a  test    r14, r14
0x18001993d  jnz     short loc_180019989
0x18001993f  mov     [rbp+pSourceDataObject], rbx
0x180019943  test    edi, edi
0x180019945  js      short loc_180019950
0x180019947  test    r14, r14
0x18001994a  jnz     loc_1800199EB
0x180019950  mov     r8, [rsi]; pTask
0x180019953  mov     ecx, edi; hr
0x180019955  mov     rdx, [r13+0]; pDataObject
0x180019959  call    ?CClipDataObject_CacheDataPointerEtw@OleClipboardTracing@@SAXJPEAUIDataObject@@PEAVClipboardDataObjectTask@@@Z; OleClipboardTracing::CClipDataObject_CacheDataPointerEtw(long,IDataObject *,ClipboardDataObjectTask *)
0x18001995e  test    edi, edi
0x180019960  jns     loc_1800198A1
0x180019966  mov     this, rsi; this
0x180019969  call    ?InternalRelease@?$ComPtr@VClipboardDataObjectTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ClipboardDataObjectTask>::InternalRelease(void)
0x18001996e  jmp     loc_1800198A1
0x180019973  lea     rdx, [this+48h]; <args_0>
0x180019977  cmp     [rdx], ebx
0x180019979  jz      loc_1800198A1
0x18001997f  mov     this, rsi; ppvObject
0x180019982  call    ??$MakeAndInitialize@VClipboardDataObjectTask@@V1@AEAK@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VClipboardDataObjectTask@@@WRL@Microsoft@@@012@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,ulong &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask>>,ulong &)
0x180019987  jmp     short $logRtn_1
0x180019989  cmp     cs:?g_fIsClipboardBrokerHost@@3_NA, bl; bool g_fIsClipboardBrokerHost
0x18001998f  jz      short loc_18001993F
0x180019991  lea     r9, [rbp+hToken]; pIsPLMManaged
0x180019995  mov     [rbp+pszPackageName], rbx
0x180019999  lea     r8, [rbp+pMTADataObj]; ppid
0x18001999d  mov     dword ptr [rbp+pMTADataObj], ebx
0x1800199a0  lea     rdx, [rbp+pszPackageName]; ppszPackageFullName
0x1800199a4  mov     byte ptr [rbp+hToken], bl
0x1800199a7  mov     this, r14; hWndClipboardOwner
0x1800199aa  call    ?GetPackagedPLMClipboardOwnerInternal@@YAJPEAUHWND__@@PEAPEBGPEAKPEA_N@Z; GetPackagedPLMClipboardOwnerInternal(HWND__ *,ushort const * *,ulong *,bool *)
0x1800199af  mov     edi, eax
0x1800199b1  test    eax, eax
0x1800199b3  js      short loc_18001993F
0x1800199b5  cmp     [rbp+pszPackageName], rbx
0x1800199b9  jz      short loc_18001993F
0x1800199bb  cmp     byte ptr [rbp+hToken], bl
0x1800199be  jz      loc_18001993F
0x1800199c4  mov     eax, dword ptr [rbp+pMTADataObj]
0x1800199c7  lea     rdx, [rbp+pMTADataObj]; <args_0>
0x1800199cb  mov     this, rsi; ppvObject
0x1800199ce  mov     [r15+48h], eax
0x1800199d2  call    ??$MakeAndInitialize@VClipboardDataObjectTask@@V1@AEAK@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VClipboardDataObjectTask@@@WRL@Microsoft@@@012@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,ulong &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask>>,ulong &)
0x1800199d7  mov     this, [rbp+pszPackageName]; pv
0x1800199db  call    cs:__imp_CoTaskMemFree
0x1800199e2  nop     dword ptr [rax+rax+00h]
0x1800199e7  mov     [rbp+pSourceDataObject], rbx
0x1800199eb  cmp     [rsi], rbx
0x1800199ee  lea     r9, [rbp+pSourceDataObject]; hWnd
0x1800199f2  mov     r8d, ebx
0x1800199f5  mov     this, r14; hWnd
0x1800199f8  setnz   r8b; ppunk
0x1800199fc  call    ?GetInterfaceFromWindowProp@@YAJPEAUHWND__@@AEBU_GUID@@HPEAPEAUIUnknown@@PEAG@Z; GetInterfaceFromWindowProp(HWND__ *,_GUID const &,int,IUnknown * *,ushort *)
0x180019a01  mov     edi, eax
0x180019a03  cmp     eax, 8004C001h
0x180019a08  jz      short loc_180019A2E
0x180019a0a  mov     rax, [rbp+pSourceDataObject]
0x180019a0e  test    rax, rax
0x180019a11  jz      loc_180019950
0x180019a17  cmp     [r15+44h], bl
0x180019a1b  jnz     loc_180019AAD
0x180019a21  mov     [r13+0], rax
0x180019a25  mov     [rbp+pSourceDataObject], rbx
0x180019a29  jmp     loc_180019950
0x180019a2e  lea     r9, [rbp+hToken]; pIsPLMManaged
0x180019a32  mov     [rbp+pszPackageName], rbx
0x180019a36  lea     r8, [rbp+pMTADataObj]; ppid
0x180019a3a  mov     dword ptr [rbp+pMTADataObj], ebx
0x180019a3d  lea     rdx, [rbp+pszPackageName]; ppszPackageFullName
0x180019a41  mov     byte ptr [rbp+hToken], bl
0x180019a44  mov     this, r14; hWndClipboardOwner
0x180019a47  call    ?GetPackagedPLMClipboardOwnerInternal@@YAJPEAUHWND__@@PEAPEBGPEAKPEA_N@Z; GetPackagedPLMClipboardOwnerInternal(HWND__ *,ushort const * *,ulong *,bool *)
0x180019a4c  mov     edi, eax
0x180019a4e  test    eax, eax
0x180019a50  js      short loc_180019A0A
0x180019a52  cmp     [rbp+pszPackageName], rbx
0x180019a56  jz      short loc_180019A86
0x180019a58  cmp     byte ptr [rbp+hToken], bl
0x180019a5b  jz      short loc_180019A86
0x180019a5d  mov     eax, dword ptr [rbp+pMTADataObj]
0x180019a60  lea     rdx, [rbp+pMTADataObj]; <args_0>
0x180019a64  mov     this, rsi; ppvObject
0x180019a67  mov     [r15+48h], eax
0x180019a6b  call    ??$MakeAndInitialize@VClipboardDataObjectTask@@V1@AEAK@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VClipboardDataObjectTask@@@WRL@Microsoft@@@012@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<ClipboardDataObjectTask,ClipboardDataObjectTask,ulong &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ClipboardDataObjectTask>>,ulong &)
0x180019a70  mov     this, [rbp+pszPackageName]; pv
0x180019a74  mov     edi, eax
0x180019a76  call    cs:__imp_CoTaskMemFree
0x180019a7d  nop     dword ptr [rax+rax+00h]
0x180019a82  test    edi, edi
0x180019a84  js      short loc_180019A0A
0x180019a86  lea     r9, [rbp+pSourceDataObject]; hWnd
0x180019a8a  mov     r8d, 1; ppunk
0x180019a90  mov     this, r14; hWnd
0x180019a93  call    ?GetInterfaceFromWindowProp@@YAJPEAUHWND__@@AEBU_GUID@@HPEAPEAUIUnknown@@PEAG@Z; GetInterfaceFromWindowProp(HWND__ *,_GUID const &,int,IUnknown * *,ushort *)
0x180019a98  mov     edi, eax
0x180019a9a  jmp     loc_180019A0A
0x180019a9f  lea     this, [rbp+hToken]; this
0x180019aa3  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x180019aa8  jmp     $logRtn_1
0x180019aad  lea     rdx, aClipboarddatao; "ClipboardDataObjectInterfaceMTA"
0x180019ab4  mov     this, r14; hWnd
0x180019ab7  call    cs:__imp_GetPropW
0x180019abe  nop     dword ptr [rax+rax+00h]
0x180019ac3  mov     [rbp+pMTADataObj], rax
0x180019ac7  test    rax, rax
0x180019aca  jz      short loc_180019B21
0x180019acc  mov     [rbp+GITSourceInnerDataObject._cookie], ebx
0x180019acf  call    ?Acquire@Git@Details@Internal@Windows@@QEAAJXZ; Windows::Internal::Details::Git::Acquire(void)
0x180019ad4  mov     [rbp+GITSourceInnerDataObject._hrInitGit], eax
0x180019ad7  lea     this, [rbp+var_18]
0x180019adb  lea     rax, ??_7?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable'
0x180019ae2  mov     [rbp+GITSourceInnerDataObject.__vftable], rax
0x180019ae6  lea     rax, [rbp+pMTADataObj]
0x180019aea  mov     [rbp+var_18], rax
0x180019aee  lea     rax, [rbp+GITSourceInnerDataObject]
0x180019af2  mov     [rbp+var_10], rax
0x180019af6  call    RunSyncOnMTAThread__lambda_27a1cab33e266522ee12881589f1a48d___; RunSyncOnMTAThread__lambda_27a1cab33e266522ee12881589f1a48d_
0x180019afb  mov     edi, eax
0x180019afd  test    eax, eax
0x180019aff  js      short loc_180019B16
0x180019b01  mov     r8, r13; ptr
0x180019b04  lea     rdx, _GUID_0000010e_0000_0000_c000_000000000046; riid
0x180019b0b  lea     this, [rbp+GITSourceInnerDataObject]; this
0x180019b0f  call    ?Localize@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(_GUID const &,void * *)
0x180019b14  mov     edi, eax
0x180019b16  lea     this, [rbp+GITSourceInnerDataObject]; this
0x180019b1a  call    ??1?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(void)
0x180019b1f  jmp     short loc_180019B6D
0x180019b21  lea     rdx, [rbp+hToken]; phToken
0x180019b25  mov     [rbp+hToken], rbx
0x180019b29  mov     this, r14; hWnd
0x180019b2c  call    ?GetTokenFromHwnd@@YAJPEAUHWND__@@PEAPEAXK@Z; GetTokenFromHwnd(HWND__ *,void * *,ulong)
0x180019b31  cmp     eax, 80070005h
0x180019b36  mov     edi, ebx
0x180019b38  cmovnz  edi, eax
0x180019b3b  test    edi, edi
0x180019b3d  js      short loc_180019B58
0x180019b3f  mov     this, [rbp+pSourceDataObject]; pInnerDataObject
0x180019b43  lea     r9, [rbp+hToken]; phObjectOwnerToken
0x180019b47  xor     r8d, r8d; fOwnerIsPlmManaged
0x180019b4a  mov     [rsp+58h+ppDataObj], r13; ppDataObj
0x180019b4f  xor     edx, edx; dwSourceProcessId
0x180019b51  call    ?Create@CBrokeredClipDataObject@@SAJPEAUIDataObject@@K_NPEAPEAXPEAPEAU2@@Z; CBrokeredClipDataObject::Create(IDataObject *,ulong,bool,void * *,IDataObject * *)
0x180019b56  mov     edi, eax
0x180019b58  mov     this, [rbp+hToken]; hObject
0x180019b5c  test    this, this
0x180019b5f  jz      short loc_180019B6D
0x180019b61  call    cs:__imp_CloseHandle
0x180019b68  nop     dword ptr [rax+rax+00h]
0x180019b6d  mov     this, [rbp+pSourceDataObject]
0x180019b71  mov     rax, [this]
0x180019b74  mov     rax, [rax+10h]
0x180019b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b7d  jmp     loc_180019950
```

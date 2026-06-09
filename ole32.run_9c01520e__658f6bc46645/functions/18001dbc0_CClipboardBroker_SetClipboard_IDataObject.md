# CClipboardBroker::SetClipboard(IDataObject *)

- ea: `0x18001dbc0`
- end: `0x18001df03`
- name: `?SetClipboard@CClipboardBroker@@UEAAJPEAUIDataObject@@@Z`
- size: `835`
- prototype: `HRESULT __fastcall(CClipboardBroker *this, IDataObject *pDataObject)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18001c654`
- `0x18001c778`
- `0x18001dbc0`
- `0x18001e150`
- `0x18001e5b4`
- `0x18001e7f0`
- `0x18001eb6c`
- `0x180039dd4`
- `0x18003aac4`
- `0x18003d4f0`
- `0x180041f0c`
- `0x1800455d4`
- `0x180046460`
- `0x180047484`
- `0x180089ee8`
- `0x180089f24`
- `0x18008a418`
- `0x18008a4b4`
- `0x18008a56c`
- `0x18008a880`
- `0x18008be38`
- `0x18008c08c`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcfd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001dcd6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001dcd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dea3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dea3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001dc9f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001dc9f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001de18`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001de18`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001de6f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001de6f`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall CClipboardBroker::SetClipboard(CClipboardBroker *this, IDataObject *pDataObject)
{
  int v3; // esi
  HRESULT CallerPackageName; // edi
  void *v5; // rbx
  AppModelPolicy_Type v6; // edx
  HRESULT Policy; // eax
  signed int LastError; // eax
  Windows::Internal::Details::Git *v9; // rcx
  Windows::Internal::Details::Git *v10; // rcx
  char v11; // bl
  void *v12; // rcx
  int fAllowed; // [rsp+38h] [rbp-D0h] BYREF
  AppModelPolicy_PolicyValue lifecyclePolicy; // [rsp+3Ch] [rbp-CCh] BYREF
  Windows::Internal::GitPtr GITSourceDataObject; // [rsp+40h] [rbp-C8h] BYREF
  void *pMTAWrapperRawAddress; // [rsp+50h] [rbp-B8h]
  Microsoft::WRL::ComPtr<IDataObject> pWrappedDataObjectSTAProxy; // [rsp+58h] [rbp-B0h] BYREF
  void *hCallerToken; // [rsp+60h] [rbp-A8h] BYREF
  Windows::Internal::GitPtr GITWrappedDataObject; // [rsp+68h] [rbp-A0h] BYREF
  int v21; // [rsp+78h] [rbp-90h]
  HRESULT v22; // [rsp+7Ch] [rbp-8Ch]
  _QWORD v23[5]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE packagedProcessName[264]; // [rsp+B0h] [rbp-58h] OVERLAPPED BYREF

  GITWrappedDataObject.__vftable = 0;
  memset_0(&packagedProcessName[8], 0, 0x100u);
  v3 = 0x10000;
  LOWORD(fAllowed) = 0;
  lifecyclePolicy = 0;
  hCallerToken = 0;
  pWrappedDataObjectSTAProxy.ptr_ = 0;
  GITSourceDataObject.__vftable = (Windows::Internal::GitPtr_vtbl *)0x1000000000000LL;
  CallerPackageName = OleCheckClipboardCallerIntegrityLevel();
  if ( CallerPackageName >= 0 )
  {
    CallerPackageName = OleCheckCallerForClipboardAccess((int *)&GITSourceDataObject);
    if ( CallerPackageName >= 0 )
    {
      if ( LODWORD(GITSourceDataObject.__vftable) )
      {
        CallerPackageName = GetCallerPackageName(
                              (bool *)&fAllowed + 1,
                              (wchar_t (*)[128])&packagedProcessName[8],
                              (unsigned int *)&lifecyclePolicy);
        if ( CallerPackageName >= 0 )
        {
          *(_QWORD *)&GITWrappedDataObject._cookie = OpenProcess(0x400u, 0, lifecyclePolicy);
          v5 = *(void **)&GITWrappedDataObject._cookie;
          if ( *(_QWORD *)&GITWrappedDataObject._cookie )
          {
            *(_QWORD *)&GITSourceDataObject._cookie = 0;
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&GITSourceDataObject._cookie,
              0);
            if ( OpenProcessToken(v5, 8u, (PHANDLE)&GITSourceDataObject._cookie) )
            {
              Policy = AppModelPolicy_GetPolicy(
                         *(void **)&GITSourceDataObject._cookie,
                         v6,
                         (AppModelPolicy_PolicyValue *)&GITSourceDataObject.__vftable + 1);
              v3 = HIDWORD(GITSourceDataObject.__vftable);
              CallerPackageName = Policy;
            }
            else
            {
              LastError = GetLastError();
              CallerPackageName = LastError;
              if ( LastError > 0 )
                CallerPackageName = (unsigned __int16)LastError | 0x80070000;
              OleInternalOriginateError(CallerPackageName, 0x13Bu);
            }
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&GITSourceDataObject._cookie);
          }
          wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&GITWrappedDataObject._cookie);
          if ( CallerPackageName >= 0 )
          {
            if ( v3 == 65537 )
              LOBYTE(fAllowed) = 1;
            CallerPackageName = CaptureCallerToken((void **)&GITWrappedDataObject.__vftable);
            if ( CallerPackageName >= 0 )
            {
              if ( !pDataObject )
                goto LABEL_22;
              LODWORD(pMTAWrapperRawAddress) = 0;
              HIDWORD(pMTAWrapperRawAddress) = Windows::Internal::Details::Git::Acquire(v9);
              *(_QWORD *)&GITSourceDataObject._cookie = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
              v21 = 0;
              v22 = Windows::Internal::Details::Git::Acquire(v10);
              *(_QWORD *)&GITWrappedDataObject._cookie = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
              CallerPackageName = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Initialize<IDataObject>(
                                    (Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr> *)&GITSourceDataObject._cookie,
                                    pDataObject);
              if ( CallerPackageName >= 0 )
              {
                v23[0] = &GITSourceDataObject._cookie;
                v23[1] = &GITWrappedDataObject;
                v23[2] = &GITWrappedDataObject._cookie;
                v23[3] = &pWrappedDataObjectSTAProxy;
                v23[4] = &lifecyclePolicy;
                *(_QWORD *)packagedProcessName = &fAllowed;
                CallerPackageName = RunSyncOnMTAThread<_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_>((CClipboardBroker::SetClipboard::__l34::<lambda_be18d0e1c9460e7bb92c1a447c19d4fe> *)v23);
                if ( CallerPackageName >= 0 )
                  CallerPackageName = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyLocal<IDataObject>(
                                        (Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr> *)&GITWrappedDataObject._cookie,
                                        (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDataObject> >)&hCallerToken);
              }
              Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>((Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr> *)&GITWrappedDataObject._cookie);
              Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>((Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr> *)&GITSourceDataObject._cookie);
              if ( CallerPackageName >= 0 )
              {
LABEL_22:
                CallerPackageName = CoImpersonateClient();
                if ( CallerPackageName >= 0 )
                {
                  v11 = BYTE1(fAllowed);
                  CallerPackageName = OleSetClipboardInternal(
                                        (IDataObject *)hCallerToken,
                                        pDataObject,
                                        (void **)&pWrappedDataObjectSTAProxy.ptr_,
                                        (const wchar_t *)((unsigned __int64)&packagedProcessName[8]
                                                        & -(__int64)(BYTE1(fAllowed) != 0)),
                                        lifecyclePolicy);
                  OleFlushClipboardInternal(
                    (const wchar_t *)((unsigned __int64)&packagedProcessName[8] & -(__int64)(v11 != 0)),
                    1,
                    1);
                  CoRevertToSelf();
                  if ( CallerPackageName >= 0 )
                    MoniterBrokeredClipboardOwner(lifecyclePolicy);
                }
              }
            }
          }
        }
      }
      else
      {
        CallerPackageName = -2147024891;
        OleInternalOriginateError(-2147024891, 0x131u);
      }
    }
  }
  if ( pWrappedDataObjectSTAProxy.ptr_ )
    RunSyncOnMTAThread<_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_>((CClipboardBroker::SetClipboard::__l49::<lambda_ceb8f1db0b0f2dc512542b4e425d8ca5>)&pWrappedDataObjectSTAProxy);
  if ( GITWrappedDataObject.__vftable )
    CloseHandle(GITWrappedDataObject.__vftable);
  OleClipboardTracing::CClipboardBroker_SetClipboardEtw(CallerPackageName, pDataObject);
  v12 = hCallerToken;
  if ( hCallerToken )
  {
    hCallerToken = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)CallerPackageName;
}

```

## disassembly

```asm
0x18001dbc0  mov     rax, rsp
0x18001dbc3  mov     [rax+8], rbx
0x18001dbc7  mov     [rax+18h], rsi
0x18001dbcb  mov     [rax+20h], rdi
0x18001dbcf  push    rbp
0x18001dbd0  push    r14
0x18001dbd2  push    r15
0x18001dbd4  lea     rbp, [rax-0D8h]
0x18001dbdb  sub     rsp, 1C0h
0x18001dbe2  mov     rax, cs:__security_cookie
0x18001dbe9  xor     rax, rsp
0x18001dbec  mov     [rbp+0D0h+var_20], rax
0x18001dbf3  mov     r14, pDataObject
0x18001dbf6  lea     this, [rbp+0D0h+packagedProcessName+8]; void *
0x18001dbfa  xor     r15d, r15d
0x18001dbfd  xor     edx, edx; Val
0x18001dbff  mov     r8d, 100h; Size
0x18001dc05  mov     [rsp+1D0h+GITWrappedDataObject.__vftable], r15
0x18001dc0a  call    memset_0
0x18001dc0f  mov     esi, 10000h
0x18001dc14  mov     byte ptr [rsp+1D0h+fAllowed+1], r15b
0x18001dc19  mov     dword ptr [rsp+1D0h+GITSourceDataObject.__vftable+4], esi
0x18001dc1d  mov     byte ptr [rsp+1D0h+fAllowed], r15b
0x18001dc22  mov     [rsp+1D0h+lifecyclePolicy], r15d
0x18001dc27  mov     [rsp+1D0h+hCallerToken], r15
0x18001dc2c  mov     [rsp+1D0h+pWrappedDataObjectSTAProxy.ptr_], r15
0x18001dc31  mov     dword ptr [rsp+1D0h+GITSourceDataObject.__vftable], r15d
0x18001dc36  call    ?OleCheckClipboardCallerIntegrityLevel@@YAJXZ; OleCheckClipboardCallerIntegrityLevel(void)
0x18001dc3b  mov     edi, eax
0x18001dc3d  test    eax, eax
0x18001dc3f  js      loc_18001DE88
0x18001dc45  lea     this, [rsp+1D0h+GITSourceDataObject]; pfAllowed
0x18001dc4a  call    ?OleCheckCallerForClipboardAccess@@YAJPEAH@Z; OleCheckCallerForClipboardAccess(int *)
0x18001dc4f  mov     edi, eax
0x18001dc51  test    eax, eax
0x18001dc53  js      loc_18001DE88
0x18001dc59  cmp     dword ptr [rsp+1D0h+GITSourceDataObject.__vftable], r15d
0x18001dc5e  jnz     short loc_18001DC76
0x18001dc60  mov     edi, 80070005h
0x18001dc65  mov     edx, 131h; messageID
0x18001dc6a  mov     ecx, edi; hr
0x18001dc6c  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x18001dc71  jmp     loc_18001DE88
0x18001dc76  lea     r8, [rsp+1D0h+lifecyclePolicy]; pdwProcessId
0x18001dc7b  lea     pDataObject, [rbp+0D0h+packagedProcessName+8]; packagedProcessName
0x18001dc7f  lea     this, [rsp+1D0h+fAllowed+1]; pfHasPackageName
0x18001dc84  call    ?GetCallerPackageName@@YAJPEA_NAEAY0IA@GPEAK@Z; GetCallerPackageName(bool *,ushort (&)[128],ulong *)
0x18001dc89  mov     edi, eax
0x18001dc8b  test    eax, eax
0x18001dc8d  js      loc_18001DE88
0x18001dc93  mov     r8d, [rsp+1D0h+lifecyclePolicy]; dwProcessId
0x18001dc98  xor     edx, edx; bInheritHandle
0x18001dc9a  mov     ecx, 400h; dwDesiredAccess
0x18001dc9f  call    cs:__imp_OpenProcess
0x18001dca6  nop     dword ptr [rax+rax+00h]
0x18001dcab  mov     qword ptr [rsp+1D0h+GITWrappedDataObject._cookie], rax
0x18001dcb0  mov     rbx, rax
0x18001dcb3  test    rax, rax
0x18001dcb6  jz      short loc_18001DD2E
0x18001dcb8  xor     edx, edx; ptr
0x18001dcba  mov     qword ptr [rsp+1D0h+GITSourceDataObject._cookie], r15
0x18001dcbf  lea     this, [rsp+1D0h+GITSourceDataObject._cookie]; this
0x18001dcc4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001dcc9  lea     r8, [rsp+1D0h+GITSourceDataObject._cookie]; TokenHandle
0x18001dcce  mov     edx, 8; DesiredAccess
0x18001dcd3  mov     this, rbx; ProcessHandle
0x18001dcd6  call    cs:__imp_OpenProcessToken
0x18001dcdd  nop     dword ptr [rax+rax+00h]
0x18001dce2  test    eax, eax
0x18001dce4  jz      short loc_18001DCFD
0x18001dce6  mov     this, qword ptr [rsp+1D0h+GITSourceDataObject._cookie]; token
0x18001dceb  lea     r8, [rsp+1D0h+GITSourceDataObject.__vftable+4]; token
0x18001dcf0  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x18001dcf5  mov     esi, dword ptr [rsp+1D0h+GITSourceDataObject.__vftable+4]
0x18001dcf9  mov     edi, eax
0x18001dcfb  jmp     short loc_18001DD24
0x18001dcfd  call    cs:__imp_GetLastError
0x18001dd04  nop     dword ptr [rax+rax+00h]
0x18001dd09  mov     edi, eax
0x18001dd0b  test    eax, eax
0x18001dd0d  jle     short loc_18001DD18
0x18001dd0f  movzx   edi, ax
0x18001dd12  or      edi, 80070000h
0x18001dd18  mov     edx, 13Bh; messageID
0x18001dd1d  mov     ecx, edi; hr
0x18001dd1f  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x18001dd24  lea     this, [rsp+1D0h+GITSourceDataObject._cookie]; this
0x18001dd29  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001dd2e  lea     this, [rsp+1D0h+GITWrappedDataObject._cookie]; this
0x18001dd33  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001dd38  test    edi, edi
0x18001dd3a  js      loc_18001DE88
0x18001dd40  cmp     esi, 10001h
0x18001dd46  jnz     short loc_18001DD4D
0x18001dd48  mov     byte ptr [rsp+1D0h+fAllowed], 1
0x18001dd4d  lea     this, [rsp+1D0h+GITWrappedDataObject]; phToken
0x18001dd52  call    ?CaptureCallerToken@@YAJPEAPEAX@Z; CaptureCallerToken(void * *)
0x18001dd57  mov     edi, eax
0x18001dd59  test    eax, eax
0x18001dd5b  js      loc_18001DE88
0x18001dd61  test    r14, r14
0x18001dd64  jz      loc_18001DE18
0x18001dd6a  mov     dword ptr [rsp+1D0h+pMTAWrapperRawAddress], r15d
0x18001dd6f  call    ?Acquire@Git@Details@Internal@Windows@@QEAAJXZ; Windows::Internal::Details::Git::Acquire(void)
0x18001dd74  lea     rbx, ??_7?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable'
0x18001dd7b  mov     dword ptr [rsp+1D0h+pMTAWrapperRawAddress+4], eax
0x18001dd7f  mov     qword ptr [rsp+1D0h+GITSourceDataObject._cookie], rbx
0x18001dd84  mov     [rsp+1D0h+var_160], r15d
0x18001dd89  call    ?Acquire@Git@Details@Internal@Windows@@QEAAJXZ; Windows::Internal::Details::Git::Acquire(void)
0x18001dd8e  mov     pDataObject, r14; ptr
0x18001dd91  mov     [rsp+1D0h+var_15C], eax
0x18001dd95  lea     this, [rsp+1D0h+GITSourceDataObject._cookie]; this
0x18001dd9a  mov     qword ptr [rsp+1D0h+GITWrappedDataObject._cookie], rbx
0x18001dd9f  call    ??$Initialize@UIDataObject@@@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@QEAAJPEAUIDataObject@@@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Initialize<IDataObject>(IDataObject *)
0x18001dda4  mov     edi, eax
0x18001dda6  test    eax, eax
0x18001dda8  js      short loc_18001DE00
0x18001ddaa  lea     rax, [rsp+1D0h+GITSourceDataObject._cookie]
0x18001ddaf  mov     [rbp+0D0h+var_150], rax
0x18001ddb3  lea     this, [rbp+0D0h+var_150]
0x18001ddb7  lea     rax, [rsp+1D0h+GITWrappedDataObject]
0x18001ddbc  mov     [rbp+0D0h+var_148], rax
0x18001ddc0  lea     rax, [rsp+1D0h+GITWrappedDataObject._cookie]
0x18001ddc5  mov     [rbp+0D0h+var_140], rax
0x18001ddc9  lea     rax, [rsp+1D0h+pWrappedDataObjectSTAProxy]
0x18001ddce  mov     [rbp+0D0h+var_138], rax
0x18001ddd2  lea     rax, [rsp+1D0h+lifecyclePolicy]
0x18001ddd7  mov     [rbp+0D0h+var_130], rax
0x18001dddb  lea     rax, [rsp+1D0h+fAllowed]
0x18001dde0  mov     qword ptr [rbp+0D0h+packagedProcessName], rax
0x18001dde4  call    ??$RunSyncOnMTAThread@V_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_@@@@YAJV_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_@@@Z; RunSyncOnMTAThread<_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_>(_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_)
0x18001dde9  mov     edi, eax
0x18001ddeb  test    eax, eax
0x18001dded  js      short loc_18001DE00
0x18001ddef  lea     pDataObject, [rsp+1D0h+hCallerToken]; ptr
0x18001ddf4  lea     this, [rsp+1D0h+GITWrappedDataObject._cookie]; this
0x18001ddf9  call    ??$CopyLocal@UIDataObject@@@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@QEAAJV?$ComPtrRef@V?$ComPtr@UIDataObject@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyLocal<IDataObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDataObject>>)
0x18001ddfe  mov     edi, eax
0x18001de00  lea     this, [rsp+1D0h+GITWrappedDataObject._cookie]; this
0x18001de05  call    ??1?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(void)
0x18001de0a  lea     this, [rsp+1D0h+GITSourceDataObject._cookie]; this
0x18001de0f  call    ??1?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(void)
0x18001de14  test    edi, edi
0x18001de16  js      short loc_18001DE88
0x18001de18  call    cs:__imp_CoImpersonateClient
0x18001de1f  nop     dword ptr [rax+rax+00h]
0x18001de24  mov     edi, eax
0x18001de26  test    eax, eax
0x18001de28  js      short loc_18001DE88
0x18001de2a  mov     bl, byte ptr [rsp+1D0h+fAllowed+1]
0x18001de2e  lea     r8, [rsp+1D0h+pWrappedDataObjectSTAProxy]; ppDataObjectMTAAddress
0x18001de33  mov     this, [rsp+1D0h+hCallerToken]; pDataObject
0x18001de38  mov     al, bl
0x18001de3a  neg     al
0x18001de3c  mov     pDataObject, r14; pSourceDataObject
0x18001de3f  lea     rax, [rbp+0D0h+packagedProcessName+8]
0x18001de43  sbb     r9, r9
0x18001de46  and     r9, rax; pszCallerPackageFullName
0x18001de49  mov     eax, [rsp+1D0h+lifecyclePolicy]
0x18001de4d  mov     [rsp+1D0h+pid], eax; pid
0x18001de51  call    ?OleSetClipboardInternal@@YAJPEAUIDataObject@@0PEAPEAXPEBGK@Z; OleSetClipboardInternal(IDataObject *,IDataObject *,void * *,ushort const *,ulong)
0x18001de56  mov     edi, eax
0x18001de58  mov     r8b, 1; fTextOnly
0x18001de5b  lea     rax, [rbp+0D0h+packagedProcessName+8]
0x18001de5f  neg     bl
0x18001de61  mov     dl, r8b; fInBroker
0x18001de64  sbb     this, this
0x18001de67  and     this, rax; pszCallerPackgeFullName
0x18001de6a  call    ?OleFlushClipboardInternal@@YAJPEBG_N1@Z; OleFlushClipboardInternal(ushort const *,bool,bool)
0x18001de6f  call    cs:__imp_CoRevertToSelf
0x18001de76  nop     dword ptr [rax+rax+00h]
0x18001de7b  test    edi, edi
0x18001de7d  js      short loc_18001DE88
0x18001de7f  mov     ecx, [rsp+1D0h+lifecyclePolicy]; dwSourceProcessId
0x18001de83  call    ?MoniterBrokeredClipboardOwner@@YAXK@Z; MoniterBrokeredClipboardOwner(ulong)
0x18001de88  cmp     [rsp+1D0h+pWrappedDataObjectSTAProxy.ptr_], r15
0x18001de8d  jz      short loc_18001DE99
0x18001de8f  lea     this, [rsp+1D0h+pWrappedDataObjectSTAProxy]; operation
0x18001de94  call    ??$RunSyncOnMTAThread@V_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_@@@@YAJV_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_@@@Z; RunSyncOnMTAThread<_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_>(_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_)
0x18001de99  mov     this, [rsp+1D0h+GITWrappedDataObject.__vftable]; hObject
0x18001de9e  test    this, this
0x18001dea1  jz      short loc_18001DEAF
0x18001dea3  call    cs:__imp_CloseHandle
0x18001deaa  nop     dword ptr [rax+rax+00h]
0x18001deaf  mov     pDataObject, r14; pDataObject
0x18001deb2  mov     ecx, edi; hr
0x18001deb4  call    ?CClipboardBroker_SetClipboardEtw@OleClipboardTracing@@SAXJPEAUIDataObject@@@Z; OleClipboardTracing::CClipboardBroker_SetClipboardEtw(long,IDataObject *)
0x18001deb9  mov     this, [rsp+1D0h+hCallerToken]
0x18001debe  test    this, this
0x18001dec1  jz      short loc_18001DED4
0x18001dec3  mov     [rsp+1D0h+hCallerToken], r15
0x18001dec8  mov     rax, [this]
0x18001decb  mov     rax, [rax+10h]
0x18001decf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ded4  mov     eax, edi
0x18001ded6  mov     this, [rbp+0D0h+var_20]
0x18001dedd  xor     this, rsp; StackCookie
0x18001dee0  call    __security_check_cookie
0x18001dee5  lea     r11, [rsp+1D0h+var_10]
0x18001deed  mov     rbx, [r11+20h]
0x18001def1  mov     rsi, [r11+30h]
0x18001def5  mov     rdi, [r11+38h]
0x18001def9  mov     rsp, r11
0x18001defc  pop     r15
0x18001defe  pop     r14
0x18001df00  pop     rbp
0x18001df01  retn
```
